# Platform API Summary Table

## TL;DR (150-250 words)
This table synthesizes findings across all 10 platforms in scope, showing for each: API availability and stability, cost structure, what can be read via OAuth user authorization, ToS stance on third-party aggregation, and what our product can and cannot legally do. The clearest pattern: platforms built on transparency (GitHub, Dribbble, Mirror) offer the cleanest data access paths for user-consented C-side products. Platforms protecting network-effect moats (LinkedIn, X/Twitter) have systematically closed their APIs and aggressively litigate against third-party aggregation. Platforms without APIs (Substack, Medium-readable-only) require RSS or user-export flows. The universal constraint: **no platform with significant professional data allows that data to be aggregated at scale for B-side resale** — this is either ToS-prohibited (GitHub, Dribbble, X, LinkedIn), technically impossible (Notion requires individual page shares), or legally gray at best (personal sites under GDPR without individual consent). The only viable B-side path is one where users explicitly authorize sharing their aggregated profile with specific employers — maintaining user control at the moment of sharing, not just at account creation. Platforms most suitable for our MVP: GitHub (best data quality + reasonable ToS for C-side), Dribbble/Behance (creative work portfolios), Substack/Medium RSS (writing topics), personal sites (user-provided URLs). LinkedIn: sign-in only. Citation range: V660-V662.

---

## Master Platform Comparison Table

| Platform | API Status | Cost | Auth Method | Key Scopes (Reading) | Rate Limit | ToS: 3rd Party Aggregation | ToS: B-Side Resale | What We CAN Do | What We CANNOT Do |
|---|---|---|---|---|---|---|---|---|---|
| **GitHub** | ✅ Stable REST + GraphQL | Free (no API cost) | OAuth 2.0 | `read:user`, `public_repo` | 5,000 req/hr (authenticated) | Allowed with purpose restrictions | ❌ Explicitly prohibited: "selling... to recruiters, headhunters, and job boards" | User-consented C-side insights; reading public repos via user OAuth | Aggregating profiles for B-side recruiter feed; selling GitHub user data |
| **X (Twitter)** | ⚠️ Available but expensive | Pay-per-use ($0.005/read); legacy tiers $200-$5,000/mo | OAuth 2.0 | `tweet.read`, `users.read` | 10,000 app/15min, 900 user/15min | ❌ ToS prohibits scraping; API resale restricted | ❌ ToS prohibits aggregation for resale | User-consented C-side; reading own tweet history via OAuth | Scraping; bulk aggregation; B-side talent feed; cost is prohibitive at scale |
| **LinkedIn** | ❌ Severely restricted | $1,680-$12,960/seat/year (Recruiter); API partnership required for full access | OAuth 2.0 (OpenID only) | `openid`, `profile`, `email` only | Not published | ❌ Explicitly prohibited; active litigation (Proxycurl 2025) | ❌ Prohibited; must be LinkedIn Talent Solutions partner | Sign-in authentication (name, email, photo only); user uploads own data export | Full profile reads; B-side aggregation; scraping (hiQ settlement: $500K judgment) |
| **Substack** | ❌ No official API | Free (RSS only) | RSS (no auth) | N/A — RSS only | Not published | ⚠️ Gray; ToS prohibits "scraping" | ❌ No path for B-side resale | Read public RSS (free posts); user exports own data | Access paywalled content; systematic aggregation of newsletters |
| **Behance** | ⚠️ Available but gated | Free (Adobe API key required; approval process slow) | OAuth 2.0 + API key | Read public projects, user profiles | Not published | ⚠️ Likely prohibited for talent resale; approval required | ❌ Likely prohibited under Adobe ToS | User-consented portfolio reading; public project metadata | Unapproved scraping; B-side talent aggregation |
| **Dribbble** | ✅ Active v2 API | Free (application required; generally approved) | OAuth 2.0 | `public` scope | 60 req/min, 1,440 req/day | ❌ Explicitly prohibited: competing designer hiring service | ❌ Explicitly prohibited | User-consented C-side portfolio insights; shot metadata, tags, view counts | Building competing designer hiring tool; scraping ("strictly prohibited") |
| **Medium** | ⚠️ Official API write-only | Free | Self-issued token or OAuth (email required) | `basicProfile`, `listPublications` | Not published | ❌ General ToS prohibits scraping | ❌ No path for B-side resale | Read public RSS (free posts); user shares own integration token | Read paywalled content; systematic profile aggregation |
| **Notion** | ✅ Active API v2025-09-03 | Free | OAuth 2.0 (page-scoped) | Page-level consent model | Not published (general throttling) | ✅ API design inherently consent-first | ❌ Not feasible (access gated by user per-page consent) | User-shared pages (portfolio, projects, writing); AI insights on consented content | Read public Notion pages (API returns 404); aggregate without per-page consent |
| **Mirror / Paragraph** | ❌ No official API; on-chain | Free (Arweave reads) | None needed (blockchain) | N/A — public ledger | None published | ✅ Public blockchain — legal to read | ⚠️ Identity matching challenge; GDPR applies to EU users | Read all public on-chain posts; full content access | Identify authors from ETH address without user consent; EU GDPR compliance required |
| **Personal Sites** | ❌ No unified API | Free (HTTP reads) | None for public sites | N/A | Not published | ✅ Low risk if user-provided URL; CFAA doesn't apply to public data | ❌ Bulk aggregation without consent is GDPR violation | Read user-provided site URL; WordPress/Ghost public APIs; Readability.js parsing | Bulk scrape without consent; use for B-side without individual consent; ignore robots.txt |

---

## Detailed Notes by Platform

### GitHub — Best in Class for C-Side
- **Why**: Most developer-transparent API; public profile data is genuinely public; ToS is clear about what's allowed (user data for user's own benefit) vs. prohibited (talent resale)
- **MVP recommendation**: Start with GitHub as primary data source
- **Risk level**: LOW for user-consented C-side; HIGH for any B-side aggregation attempt

### X (Twitter) — Cost Is the Kill Shot
- **Why**: Even if ToS allows limited use, $0.005/tweet read at scale makes meaningful career insight data collection prohibitively expensive
- **MVP recommendation**: Optional/low-priority; user-provided OAuth for tweet history if they request it
- **Risk level**: MEDIUM (ToS risk) + VERY HIGH (cost risk)

### LinkedIn — Dead End for Third-Party
- **Why**: Actively litigates; API closed; only viable as sign-in mechanism
- **MVP recommendation**: Use for sign-in only; prompt user to upload LinkedIn data export (PDF) for manual processing
- **Risk level**: VERY HIGH for any profile aggregation attempt

### Substack — RSS Only
- **Why**: No API; RSS provides useful topic/frequency signals for free posts
- **MVP recommendation**: Accept publication URL → read RSS → extract topics and posting cadence
- **Risk level**: LOW for RSS reading of public posts

### Behance — Apply Early, Manage Risk
- **Why**: Adobe approval process is slow; integrate early or not at all
- **MVP recommendation**: Apply for Adobe API access immediately; build fallback for portfolio URL manual input
- **Risk level**: MEDIUM (approval gating)

### Dribbble — Clean for C-Side, Hard Stop for B-Side
- **Why**: v2 API is well-documented and accessible; ToS is explicit about competing hiring service prohibition
- **MVP recommendation**: Include as creative professional data source; design shots and tags provide rich signal
- **Risk level**: LOW for C-side; HIGH for any B-side hire-tool framing

### Medium — RSS + User Token
- **Why**: Official API is write-focused; RSS provides reading; user can generate their own token
- **MVP recommendation**: RSS for topic signals; optional token for deeper analysis
- **Risk level**: LOW for RSS; MEDIUM for unofficial API use

### Notion — Power Tool for Active Users
- **Why**: API is robust but requires per-page user consent; only useful for users who actively use Notion
- **MVP recommendation**: Optional advanced integration; not a universal data source
- **Risk level**: LOW (inherently consent-first design)

### Mirror/Paragraph — Niche but Clean
- **Why**: Blockchain data is genuinely public; no legal risk comparable to scraping; GDPR applies for EU users
- **MVP recommendation**: Include as optional connection for Web3-native creators
- **Risk level**: LOW (legal); MEDIUM (identity matching challenge)

### Personal Sites — User-Initiated Only
- **Why**: Post-Meta v. Bright Data, public sites can be legally read; risk is in bulk/non-consensual aggregation
- **MVP recommendation**: Accept user-provided URL; read with Readability.js; respect robots.txt
- **Risk level**: LOW for user-provided; HIGH for bulk scraping without consent

---

## Platform Ranking for Our Product (C-Side MVP Priority)

| Rank | Platform | Rationale |
|---|---|---|
| 1 | **GitHub** | Best data quality; clean OAuth; rich career signal; free API |
| 2 | **Dribbble** | Creative portfolio data; accessible v2 API; no cost |
| 3 | **Personal site** | User-provided URL; no API cost; broad coverage |
| 4 | **Substack** | Topic/frequency signal via RSS; free |
| 5 | **Behance** | Adobe API (if approved); visual work portfolio |
| 6 | **Mirror/Paragraph** | Web3-native niche; clean legal status |
| 7 | **Medium** | Topic signal via RSS; lower quality than Substack |
| 8 | **Notion** | Optional; only for power Notion users |
| 9 | **X (Twitter)** | Optional; cost-constrained; user-consented only |
| 10 | **LinkedIn** | Sign-in only; no profile data access |

---
*Sources: V660, V661, V662*
