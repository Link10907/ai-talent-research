# Personal Sites — Data Collection Notes

## TL;DR (150-250 words)
Personal websites (portfolio sites, personal blogs, developer homepages) have no unified API. Scraping is the technical option, but the legal landscape is nuanced. The CFAA ("without authorization") has been narrowed by the Ninth Circuit to not apply to public data that doesn't require a password — so scraping a public personal website is generally not a CFAA violation. Meta v. Bright Data (Jan 2024) reinforced that logged-out scraping of public data may not be a ToS violation, particularly if the scraper has no contractual relationship with the site owner. For a personal portfolio site with no login requirement and no explicit ToS, the legal risk of reading publicly accessible content is low. The technical approach: use HTTP(S) requests + HTML parsing (e.g., Mozilla's Readability.js algorithm) to extract text content from personal sites. The key legal safeguard: respect robots.txt (not legally binding, but demonstrates good faith and avoids bot-detection issues), rate-limit crawling, and only use data the user has explicitly pointed you to (i.e., the user provides their personal site URL). This is fundamentally different from bulk-crawling the web without user consent. For our product, the user-consent flow — user provides their site URL → we read it on their behalf → we generate insights — is legally clean and user-aligned. Citation range: V626-V628.

---

## Technical Access Methods

### 1. Direct HTTP Fetch + HTML Parsing
- Fetch page HTML via HTTP(S) GET request
- Parse with a DOM library (Cheerio, BeautifulSoup, Readability.js)
- Extract: main content, headings, meta description, links, structured data (schema.org)
- **Pros**: Works on any public site; no API key needed
- **Cons**: HTML structure varies; requires maintenance for different site templates

### 2. Readability.js / Mozilla Readability
- Mozilla's open-source article extraction algorithm (powers Firefox Reader Mode)
- Strips navigation, ads, boilerplate; extracts main content text
- **Best for**: Blog posts, articles, portfolio case studies
- **Not great for**: Single-page apps (SPAs) with JavaScript-rendered content

### 3. Structured Data / Schema.org
- Many portfolio sites include schema.org markup (`Person`, `CreativeWork`, `Article`)
- Machine-readable: `<script type="application/ld+json">` blocks
- **Best for**: Extracting structured professional info when available

### 4. robots.txt
- Not legally binding, but:
  - Best practice to respect it (demonstrates good faith)
  - Ignoring it signals bad faith in litigation
  - `User-agent: *` / `Disallow: /` means the owner doesn't want crawlers

## Legal Status of Scraping Personal Sites (2024-2026)

### CFAA (Computer Fraud and Abuse Act)
- Ninth Circuit (hiQ v. LinkedIn, 2022): Scraping publicly accessible data does not constitute "unauthorized access" under CFAA
- If the site requires no password to access, the CFAA "without authorization" prong does not apply
- SCOTUS declined cert (2022) — Ninth Circuit interpretation stands in Ninth Circuit jurisdiction

### Meta v. Bright Data (Jan 2024, N.D. Cal.)
- Judge Chen: "The Facebook and Instagram Terms do not bar logged-off scraping of public data"
- A party with no account on a site is not bound by that site's ToS
- A "survival" clause purporting to bind scrapers in perpetuity is unenforceable
- **Bottom line**: For personal sites with no login requirement and no enforceable contract with the crawler, public scraping is generally lawful

### GDPR / Privacy Law
- Even if scraping is technically legal under CFAA/ToS law, EU GDPR applies if the site owner is an EU natural person
- Personal website content (name, contact info, employment history) qualifies as personal data under GDPR
- Reading it for commercial analysis requires a lawful basis
- **User consent flow** (user provides their own site URL for analysis) = explicit consent = valid GDPR basis

## Common Personal Site Platforms

| Platform | CMS | API Access | Notes |
|---|---|---|---|
| GitHub Pages | Static HTML | None (just HTTP) | Often hosts developer portfolios |
| Webflow | Proprietary CMS | Webflow Data API (private) | No public read API |
| Squarespace | Proprietary | Commerce API only | No public read API |
| WordPress | Open source | WordPress REST API (public by default) | `{site}/wp-json/wp/v2/posts` |
| Ghost | Open source | Ghost Content API (public) | `{site}/ghost/api/content/posts/` |
| Notion (public page) | Notion | No (Notion API won't read public pages) | Must scrape or use Notion OAuth |
| Substack | Hosted | RSS (see Substack file) | |
| Custom static site | HTML | None | HTTP fetch + parse |

**WordPress REST API** (significant finding): WordPress sites expose a public REST API by default at `{site}/wp-json/wp/v2/posts`. This provides machine-readable access to all public posts without auth. Ghost similarly has a public Content API. These are genuinely API-first approaches for personal blogs on those platforms.

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's own personal site (user-provided URL) | ✅ Low risk | User consent via URL provision; respects robots.txt |
| Scrape personal sites at bulk scale without user consent | ❌ GDPR risk | No lawful basis without consent |
| Read WordPress/Ghost site via public API | ✅ Allowed | Public APIs by design |
| Render JavaScript-heavy SPAs for content | ⚠️ Technical complexity | Requires headless browser (Playwright/Puppeteer) |
| Use content for B-side aggregation | ❌ GDPR + ToS risk | No individual consent established |

**Recommended approach**: 
1. User provides their personal site URL
2. Product fetches the URL with a polite crawl (respect robots.txt, rate limit)
3. Use Readability.js or similar to extract main content
4. If WordPress or Ghost: use their public APIs for cleaner data
5. Store only what is needed for the analysis (GDPR data minimization)
6. Do not use fetched content for any purpose other than the user's own insights

---
*Sources: V626, V627, V628*
