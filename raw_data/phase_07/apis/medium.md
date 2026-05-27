# Medium API — Data Collection Notes

## TL;DR (150-250 words)
Medium has an official OAuth2 API (v1), though its development has been largely stagnant since 2018-2019. The API primarily supports publishing (creating posts) rather than reading — there is no public endpoint for reading another user's full article list, follower counts, or engagement metrics via the official API. The official API base URL is `https://api.medium.com/v1`. For reading purposes, Medium's RSS feeds are more useful: every user has a public RSS feed at `https://medium.com/feed/@{username}`. Browser-based OAuth is "supported for existing integrations only" as of 2025 — new developers are directed to use self-issued integration tokens generated from Medium account settings. OAuth2 access to Medium's API requires emailing publications@medium.com for credentials. In practice, many developers use the unofficial MediumAPI.com service (a third-party wrapper around Medium's undocumented web API) to fetch article lists, claps, publication data, and follower information. However, using unofficial APIs carries ToS risk. For our product, the most viable path is reading a user's public Medium RSS feed for topic/frequency signals, and potentially using user-issued integration tokens to access their own article data. Medium is a secondary signal source — useful for understanding a person's writing topics, but not as rich as GitHub for technical contributors. Citation range: V620-V621.

---

## API Status (2025-2026)
- **Official API v1**: Active but largely stagnant since ~2019
- **Base URL**: `https://api.medium.com/v1`
- **Development status**: No new official endpoints added in years; largely write-focused
- **RSS Feeds**: Available at `https://medium.com/feed/@{username}` (public, no auth needed)

## Official API Capabilities

### What the Official API Supports (Write-focused)
- Create a post (article)
- Create a post under a publication
- Get authenticated user's basic info
- Get user's publications list

### What the Official API Does NOT Support
- Reading another user's full article list programmatically
- Fetching clap (engagement) counts
- Follower/following counts
- Reading comments
- Search functionality

## OAuth 2.0 Authentication

**Methods**:
1. **Self-issued access tokens** (recommended): Generated from Medium Settings → Integration Tokens
2. **Browser-based OAuth**: Supported for existing integrations only (not recommended for new apps)

**OAuth endpoint**: `https://medium.com/m/oauth/authorize`

**To obtain OAuth credentials**: Email [email protected] — there is no self-service developer registration portal.

**Scopes**:
- `basicProfile` — Read basic user profile data
- `listPublications` — Read publications list
- `publishPost` — Create posts
- `uploadImage` — Upload images

**Note**: No read scope for accessing other users' content.

## RSS Feeds (Most Useful for Reading)

Every Medium user has a public RSS feed:
- `https://medium.com/feed/@{username}` — Posts by a specific user
- Publications also have RSS feeds

**RSS provides**:
- Post titles, publish dates
- Post descriptions/excerpts
- Tags/topics
- Author information
- Full content for **free posts only** (not Medium Members-only content)

## Rate Limits
- Official API: Not publicly documented; general throttling applies
- RSS feeds: No published rate limits; standard crawl-delay best practices apply

## Pricing
- No API fee for approved developer access
- Medium membership ($5/month or $50/year) unlocks paywalled content reading for individual users, but does not grant API access to that content

## ToS Restrictions
- Medium does not have a detailed public API ToS document
- General Terms of Service prohibit scraping and automated data collection
- Official API is limited to approved integrations

## Third-Party Unofficial API (Risk Assessment)
- **MediumAPI.com** (unofficial): Provides endpoints for fetching user articles, tags, followers, publications
- **Risk**: Uses Medium's undocumented internal web API; ToS violation risk similar to Substack's unofficial API
- **Credibility of data**: Generally accurate but unreliable for production use

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's own posts via integration token | ✅ Allowed | User generates their own token |
| Read another user's public RSS feed | ✅ Low risk | Public data; free posts only |
| Read paywalled Medium content via API | ❌ Not possible | No official endpoint |
| Use unofficial MediumAPI for bulk reads | ⚠️ ToS risk | Not recommended for production |
| Aggregate Medium profiles for B-side | ❌ Likely ToS violation | No official support |

**Recommended approach**: Accept user's Medium username → read public RSS for topic/frequency signals → optionally prompt user to generate and share their own Medium integration token for deeper analysis.

---
*Sources: V620, V621*
