# X (Twitter) API — Data Collection Notes

## TL;DR (150-250 words)
X (formerly Twitter) underwent the most dramatic API monetization shift of any major platform between 2023 and 2026. What was free for most developers is now pay-per-use or tiered at high price points. As of early 2026, X has moved to a pay-per-use default ($0.005/post read, $0.01/post created), with legacy Basic ($200/month) and Pro ($5,000/month) tiers remaining only for existing subscribers. Enterprise starts around $42,000/month. The free tier has been eliminated. OAuth 2.0 is the standard auth method; key scopes for reading user data are `tweet.read` and `users.read`. Rate limits use 15-minute rolling windows and are applied per-endpoint. X's ToS explicitly prohibits scraping, and while X v. CCDH (2024) was dismissed on free-speech grounds, X's ToS clause against scraping remains contractually active. Meta v. Bright Data (Jan 2024) established that logged-out scraping of public data may not be a ToS violation — but X can argue a user who ever created an account agreed to its ToS. For a C-side product with user OAuth authorization, the cost structure is manageable for limited reads. For a B-side aggregation product, the cost is prohibitive and the ToS is hostile. Citation range: V604-V607.

---

## API Status (2025-2026)
- **API v2**: Active. Current production version.
- **Legacy v1.1**: Officially deprecated, some endpoints disabled
- **Status**: Highly restricted; significant monetization changes since Feb 2023

## Pricing Tiers (as of early 2026)

| Tier | Monthly Cost | Status |
|---|---|---|
| Free | $0 | Eliminated for most; limited write-only for bots |
| Pay-Per-Use | $0 base + per-call | Default for new developers as of 2026 |
| Basic | $200/month | Legacy only (existing subscribers) |
| Pro | $5,000/month | Legacy only (existing subscribers) |
| Enterprise | ~$42,000+/month | Custom pricing |

**Pay-per-use model (2026 default)**:
- $0.005 per post read
- $0.01 per post created
- Capped at 2 million reads/month on base tier

## Rate Limits (v2 API, per 15-minute window)

| Endpoint | Per App (Bearer) | Per User (OAuth) |
|---|---|---|
| `/2/users/:id/tweets` (user timeline) | 10,000/15min | 900/15min |
| `/2/users/:id/mentions` | 450/15min | 300/15min |
| `/2/users/by/username/:username` (lookup) | 300/15min | 900/15min |
| POST `/2/users/:id/likes` | N/A (removed Aug 2025) | N/A (removed Aug 2025) |
| POST `/2/users/:id/follows` | N/A (removed Aug 2025) | N/A (removed Aug 2025) |

**Source**: https://docs.x.com/x-api/fundamentals/rate-limits (checked 2026-05-26)

## OAuth 2.0 Scopes for Reading User Data

| Scope | What it grants |
|---|---|
| `tweet.read` | Read tweets (also required for user lookups) |
| `users.read` | Read user profile information |
| `offline.access` | Required to get refresh tokens |
| `users.email` | Read user email address |

**Key finding**: As of 2025, `tweet.read` is required even for `/users/me` endpoint lookups. Default user object returns only `id`, `name`, `username`. To get additional fields (created_at, location, description, public_metrics), developers must explicitly request field expansions.

**What you CAN read via OAuth on behalf of a user**:
- Profile: name, username, description, location, created_at, profile_image_url
- Tweet history (public tweets via `tweet.read`)
- Follower/following counts (but not full lists on lower tiers)
- Public metrics (tweet count, follower count, following count, listed count)

**What you CANNOT read (per tier/ToS)**:
- Private bookmarks removed from lower tier access (Aug 2025)
- DMs require elevated access and specific ToS exception
- Deleted tweet history is not accessible

## ToS Restrictions

**Key clause** (X User Agreement):
> "You may not... scrape [X's] Services in any form, for any purpose without [X's] prior written consent."

**Key clause** (X Developer Agreement):
> Prohibits building tools that aggregate user data at scale for resale or recruitment purposes

**Case law context**:
- **X v. CCDH (2024)**: X sued the Center for Countering Digital Hate for scraping public tweets via a third-party tool (Brandwatch, which had API access). Judge Breyer dismissed the case, noting "this case is about punishing the Defendants for their speech" and that CCDH accessed data via a licensed API tool, not direct scraping. The ToS clause against scraping remains in effect contractually.
- **Meta v. Bright Data (Jan 2024)**: While not a Twitter case directly, the ruling that logged-out scraping of public data doesn't necessarily bind the scraper to ToS has been noted as potentially applicable to X.

**Implication for our product**:
- ❌ **Dead end**: Scraping X profiles without user OAuth authorization
- ❌ **Very expensive**: B-side aggregation of X data at scale — cost and ToS prohibitive
- ✅ **Viable but costly**: User-consented OAuth to read their own tweet history for C-side insight
- ⚠️ **Cost modeling needed**: Even with user OAuth, reading a user's tweet history at scale across many users incurs significant per-call costs

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's profile via OAuth | ✅ Allowed | User must authorize; per-call cost |
| Read user's tweet timeline via OAuth | ✅ Allowed (costly) | User must authorize; $0.005/tweet read |
| Aggregate X profiles for B-side recruiter feed | ❌ Prohibited + costly | ToS + cost structure both hostile |
| Scrape public profiles without API | ❌ Prohibited by ToS | X actively litigates this |
| Generate AI insights from user's X activity | ✅ Possible with consent | Cost management critical |

---
*Sources: V604, V605, V606, V607*
