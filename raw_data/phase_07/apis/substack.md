# Substack API — Data Collection Notes

## TL;DR (150-250 words)
Substack has no official public API for developers. Every newsletter does have an automatically generated RSS feed at `{publication}.substack.com/feed`, which provides access to post titles, publish dates, descriptions, and (for free posts) full content. For paywalled posts, the RSS feed contains only the excerpt/teaser. Substack allows writers to export their own data (posts, subscribers, comments) from the backend dashboard, but this export does not include a subscriber's reading history or engagement metrics from the reader perspective. The Substack ToS prohibits "copying" and "scraping," which puts any programmatic third-party aggregation of Substack content in legal gray territory — though Substack has not been known to aggressively litigate against small-scale RSS readers. There exist unofficial Substack APIs discovered by reverse-engineering the platform (accessible at `{publication}.substack.com/api/v1/posts`), but using these is almost certainly a ToS violation. For our product, the most viable path is: (1) user provides their Substack publication URL; (2) we read their public RSS feed to understand their writing topics and frequency; (3) for full content access, user exports and uploads their own data. This approach relies on user consent and public data, minimizing legal risk. Citation range: V612-V614.

---

## API Status (2025-2026)
- **Official API**: Does NOT exist. Substack has not announced any developer API program.
- **RSS Feeds**: Available for every newsletter at `https://{publication}.substack.com/feed`
- **Unofficial/Undocumented API**: Exists (community-discovered), but ToS-hostile to use
- **User Data Export**: Available via Substack Settings → Exports (posts, comments, subscribers in CSV/ZIP)

## What RSS Provides
- Post titles
- Publish dates
- Author information
- Post descriptions/excerpts
- Full content for **free posts only**
- Post URLs
- **Does NOT provide**: subscriber counts, open rates, engagement metrics, paid subscriber data

## What User Export Provides (Self-Initiated)
- All published posts (full content)
- Comments (if enabled)
- Subscriber list (email addresses, join date, status)
- **Does NOT export**: reading history, engagement with other newsletters, follower data

## Unofficial API Endpoints (ToS Risk)
Community developers have discovered undocumented endpoints:
- `https://{publication}.substack.com/api/v1/posts` — list of posts
- `https://{publication}.substack.com/api/v1/posts/{slug}` — individual post
- Various subscriber-facing endpoints

**Risk**: Using these endpoints almost certainly violates Substack's ToS prohibiting "copying" and "scraping" platform data programmatically.

## ToS Restrictions
Substack's Terms of Use prohibit:
- Scraping or copying content programmatically without authorization
- Using platform data for commercial purposes outside the intended use
- Building services that aggregate Substack newsletters at scale

**Note**: Substack has not published specific cease-and-desist actions or lawsuits against RSS aggregators or small-scale developers. However, the ToS restriction exists and creates legal exposure.

## No Rate Limits (No Official API)
RSS feeds follow standard HTTP conventions. Substack has not published crawl rate limits. Best practice: respect standard crawl delays (1 request/second or slower).

## Pricing
- Substack charges no API fees (because there is no official API)
- RSS is free and public
- User data export is free and user-initiated

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's public Substack RSS feed | ✅ Viable (low risk) | Public data, limited to free posts |
| Use official Substack API for reading | ❌ No API exists | N/A |
| Use unofficial API endpoints | ❌ ToS violation risk | Avoid |
| User uploads their own Substack export | ✅ Allowed | User-initiated, requires export step |
| Aggregate all Substack newsletters at scale | ❌ ToS violation risk | Scraping prohibition |
| Read paywalled post content without subscription | ❌ Not possible | Paywall enforced at RSS level |

**Recommended approach**: Accept user's Substack publication URL → read RSS for topic/frequency metadata → optionally prompt user to upload their own Substack data export for deeper analysis.

---
*Sources: V612, V613, V614*
