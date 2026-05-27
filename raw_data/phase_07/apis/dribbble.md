# Dribbble API — Data Collection Notes

## TL;DR (150-250 words)
Dribbble maintains a functioning v2 API as of 2025-2026 with a clear OAuth 2.0 authentication flow and well-documented endpoints. The API covers Shots (portfolio pieces), Users, Projects, Attachments, and Jobs. Rate limits are reasonable for a startup: 60 requests/minute and 1,440 requests/day per authenticated user. All data is served as JSON over HTTPS. However, Dribbble's API Terms are unusually explicit about prohibitions: "Scraping, copying, saving, or storing our data is strictly prohibited" — all data must flow exclusively through the official API. Building a competing designer search or hiring service is also explicitly prohibited. This directly limits B-side aggregation use cases. The good news: a user-consented C-side product where the user connects their Dribbble account via OAuth to get portfolio insights is well within the ToS. Designers using Dribbble are typically open to having their portfolio work visible (it's already public by design), but the consent must come from the user, not from a scrape. The platform is particularly strong for visual/creative professional data: shot metadata, tags, tools used, view and like counts, and project organization give meaningful signal about a designer's specialty and style. Citation range: V617-V619.

---

## API Status (2025-2026)
- **API v2**: Active and maintained
- **Base URL**: `https://api.dribbble.com/v2/`
- **Format**: JSON over HTTPS
- **Status**: Stable; v2 launched 2016, no major breaking changes since

## Available Endpoints (v2)
- `/shots` — Portfolio pieces (individual design works)
- `/user` — Authenticated user's profile
- `/users/{id}` — Public user profiles
- `/projects` — Project collections (groupings of shots)
- `/attachments` — File attachments to shots
- `/jobs` — Job listings (separate product vertical)

## OAuth 2.0 Authentication

**Flow**: Standard OAuth 2.0 authorization code flow

**Available Scopes** (per OAuth docs):
- `public` — Read public data (shots, user profiles)
- `write` — Create/update shots and comments
- `comment` — Create and delete comments
- `upload` — Upload shots

**For reading public portfolio data**: `public` scope is sufficient.

## Rate Limits

| Metric | Limit |
|---|---|
| Requests per minute | 60 (per authenticated user) |
| Requests per day | 1,440 (per authenticated user) |
| HTTP status on breach | 429 (Too Many Requests) |
| Rate limit headers | `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset` |

**Pagination**: Default 30 items/page, maximum 100 items/page (JSON response with `total`, `per_page`, `page`)

## What Can Be Read with Public Scope

**User data**:
- Name, username, avatar URL
- Bio, location, website URL, Twitter username
- Follower and following counts
- Shot counts, likes given/received
- Pro membership status
- Skills, teams

**Shot data**:
- Title, description
- Tags (design tools and topics)
- View count, like count, comments count, attachments count
- Publish date, update date
- Images (multiple sizes: teaser, normal, hidpi, original)
- Animated (boolean — GIF shots)

**Project data**:
- Title, description
- Shot count within project

## ToS Key Restrictions

Directly from Dribbble API Terms (`developer.dribbble.com/terms/`):

> **"Scraping, copying, saving, or storing our data is strictly prohibited"** — all data must come from the official API

> **Prohibited**: "A website that replicates or replaces the essential user experience of dribbble.com"

> **Prohibited**: Competing designer search or hiring services

> **Prohibited**: Building portfolios for designers without their OAuth authorization

> **Prohibited**: "Community or social networks for designers"

> **Data must be removed within 24 hours** if the user or Dribbble requests removal

> **No automated actions** without explicit user request: cannot auto-post, auto-like, auto-follow on behalf of a user

## Pricing
- **No API fee** for approved access
- Dribbble requires application at developer.dribbble.com (typically auto-approved for standard use cases)
- Pro account (~$5/month) may be required for some developer features

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's public shots via OAuth | ✅ Allowed | User must authorize |
| Read user's portfolio metadata (tags, views) | ✅ Allowed | `public` scope sufficient |
| Aggregate Dribbble profiles for B-side feed | ❌ Prohibited | Competing hiring service prohibition |
| Scrape Dribbble without API | ❌ Explicitly prohibited | "Strictly prohibited" in ToS |
| Generate AI insights from user's Dribbble data | ✅ Allowed | User consent + data minimization |
| Build a designer search tool for employers | ❌ Prohibited | Competes with Dribbble Pro |

**Recommended approach**: OAuth user authorization to read their own shots, tags, and project structure. Use shot tags and descriptions as inputs for AI career insight. Do NOT build employer-facing search on top of Dribbble data.

---
*Sources: V617, V618, V619*
