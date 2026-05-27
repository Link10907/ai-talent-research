# GitHub API — Data Collection Notes

## TL;DR (150-250 words)
GitHub offers one of the most developer-friendly public APIs among all platforms in scope. The REST API and GraphQL API both allow reading public user profile data, public repositories, commit activity, and README files with an authenticated token at 5,000 requests/hour. OAuth apps acting on behalf of a user inherit that user's rate limit and scope. The critical ToS restriction: GitHub explicitly prohibits using API data "for the purposes of selling GitHub users' personal information, such as to recruiters, headhunters, and job boards." This directly closes the door on any B-side recruiter-feed product built on GitHub data without user consent. However, the same ToS does NOT forbid reading public repository data for purposes other than talent reselling — meaning a user-consented "AI career insight" tool (C-side) is a viable path, provided the user authorizes the OAuth flow. Data completeness is high: GitHub is transparent by design. Public repos, starred repos, contribution graphs, language usage stats, pinned repos, and profile READMEs are all accessible. The main constraint is purpose, not technical access. Any product must be built on user OAuth authorization (user pulls their own data), not scraping or third-party aggregation. Citation range: V600-V603.

---

## API Status (2025-2026)
- **REST API**: Active, stable. Base URL: `https://api.github.com`
- **GraphQL API**: Active, stable. Endpoint: `https://api.github.com/graphql`
- **Status**: GitHub APIs are among the most stable in the industry; no major breaking changes since 2022

## Rate Limits

### REST API
| Authentication Method | Requests/Hour |
|---|---|
| Unauthenticated (IP-based) | 60 |
| Personal Access Token / OAuth App / GitHub App | 5,000 |
| GitHub Enterprise Cloud | 15,000 |
| GitHub Actions GITHUB_TOKEN | 1,000/repo/hour |

### GraphQL API
- 5,000 points/hour for authenticated users and OAuth apps
- 10,000 points/hour for OAuth apps owned by a GitHub Enterprise Cloud org (when using client ID + secret to request public data)
- Secondary limits: max 100 concurrent requests; max 900 points/minute (REST); max 2,000 points/minute (GraphQL)
- Max 2,000 OAuth access token requests/hour for GitHub/OAuth Apps

**Source**: https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api (checked 2026-05-26)

## OAuth Scopes for Reading Public Data

For reading public user data (profile, public repos, README), no special scopes are required — public data is readable without any scope. For more detailed data:

| Scope | What it grants |
|---|---|
| `read:user` | Read all user profile data |
| `user:email` | Read user email addresses |
| `public_repo` | Read access to public repositories |
| `read:org` | Read org membership and team data |
| `repo` | Full repo access (overkill for our use case) |

For a career-insight product: `read:user` + `public_repo` is sufficient to read contribution history, languages, pinned repos, bio, and README.

## ToS Restrictions on Third-Party Aggregation

**Key clause (GitHub ToS, Acceptable Use Policies)**:
> "You may not use information from the Service (whether scraped, collected through the API, or obtained otherwise) for spamming purposes, including for the purposes of sending unsolicited emails to users or **selling personal information, such as to recruiters, headhunters, and job boards**."

**Key clause (Section D.9 — AI training reciprocity)**:
> If you use automated means to collect publicly accessible content to develop commercial AI systems, you must waive restrictions on GitHub's access to your own products' data — with exceptions for academic research and services under 700 million monthly active users.

**Implication**: 
- ❌ **Dead end**: Building a B-side recruiter product that aggregates GitHub profiles and sells access to employers — explicitly prohibited
- ✅ **Viable**: User-consented OAuth flow where the user pulls their own data for a C-side personal insight tool
- ✅ **Viable**: Reading public repos for product functionality when user has authorized access
- ⚠️ **Gray zone**: The AI training reciprocity clause (D.9) could theoretically apply to an LLM-powered insight product — needs legal review

## Data Completeness Assessment
- **High**: Public profile (name, bio, location, avatar, website URL, social links)
- **High**: Public repositories (languages, stars, forks, descriptions, README content)
- **High**: Contribution graph (commit frequency, streak, active days)
- **High**: Pinned repos, starred repos, organization memberships
- **Medium**: Private repo metadata (requires `repo` scope — user must explicitly grant)
- **Low**: Email (many users hide it; requires `user:email` scope)

## Pricing
- **Free tier**: 5,000 req/hr for authenticated apps
- **No API cost for reading public data** — GitHub charges only for GitHub Enterprise Cloud features, not API access
- **No pay-per-call model** — significantly more cost-friendly than X/Twitter

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's public profile via OAuth | ✅ Allowed | User must authorize |
| Read user's public repos and commit history | ✅ Allowed | User must authorize or data is public |
| Aggregate GitHub profiles for B-side recruiter feed | ❌ Prohibited | ToS explicitly forbids selling to recruiters |
| Generate AI insights from user's own GitHub data | ✅ Likely allowed | User consent + data minimization needed |
| Scrape GitHub profiles without API | ⚠️ Gray/risky | Technically possible, ToS hostile to it |

---
*Sources: V600, V601, V602, V603*
