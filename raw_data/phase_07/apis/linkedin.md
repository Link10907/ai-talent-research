# LinkedIn API — Data Collection Notes

## TL;DR (150-250 words)
LinkedIn is the most hostile major platform for third-party API access. The company has systematically locked down its API since 2015, and by 2025-2026 essentially the only APIs available without enterprise partnership agreements are the OpenID Connect sign-in flow (which yields only basic profile: name, email, profile picture) and limited content-sharing endpoints. The legacy `r_liteprofile` and `r_emailaddress` scopes are deprecated; new apps use OpenID Connect scopes (`openid`, `profile`, `email`). Reading full profile data — work history, skills, endorsements, connections — requires LinkedIn's Talent Solutions API, which is a paid enterprise product ($8,400-$10,800+/seat/year for Recruiter, with API access requiring a partnership agreement). The hiQ v. LinkedIn case (settled 2022 with $500K judgment against hiQ) definitively ended the era of scraping LinkedIn's public profiles as a viable business model. LinkedIn actively filed suit against Nubela/Proxycurl in January 2025. The CFAA question was resolved — scraping public LinkedIn data without authorization doesn't violate CFAA — but LinkedIn won on California tort law grounds (trespass to chattels, misappropriation). Our product cannot legally or practically aggregate LinkedIn profiles at scale without a formal LinkedIn partnership. Citation range: V608-V611.

---

## API Status (2025-2026)
- **Status**: Extremely restricted. API access requires explicit LinkedIn approval for almost all non-trivial endpoints.
- **OpenID Connect (Sign-In with LinkedIn)**: Available to all developers. Returns: `openid`, `profile`, `email` scopes only.
- **Talent Solutions API**: Enterprise only. Requires partnership agreement. Not accessible to startups without LinkedIn contract.
- **Legacy APIs**: r_liteprofile / r_emailaddress deprecated in 2026; replaced by OpenID Connect.

## Available OAuth Scopes (2025-2026)

| Scope | Status | What it Returns |
|---|---|---|
| `openid` | Open (no approval needed) | Required for OpenID Connect |
| `profile` | Open (no approval needed) | Name, profile picture, headline |
| `email` | Open (no approval needed) | Primary email address |
| `r_basicprofile` | Approval required | Extended profile fields |
| `r_fullprofile` | Partner-only | Full work history, education, skills |
| `w_member_social` | Approval required | Post on behalf of user |
| `r_liteprofile` | **Deprecated 2026** | (Legacy — replaced by `profile`) |
| `r_emailaddress` | **Deprecated 2026** | (Legacy — replaced by `email`) |

**Token lifespan**: LinkedIn access tokens expire after 60 days. No long-lived tokens are issued.

**Key restriction**: Profile data is retrieved via `/v2/userinfo` endpoint for authenticated members only. Full profile (work history, skills, connections) not accessible to third parties without partnership.

## Rate Limits
- LinkedIn does not publish specific rate limits publicly for their restricted APIs
- General guidance: app-level throttling based on approved use case
- Sign-In with LinkedIn: standard OAuth flow, no published rate limits

## Pricing for B-Side Access (Recruiter Products)

| Plan | Annual Cost Per Seat |
|---|---|
| LinkedIn Recruiter Lite | ~$1,680/seat/year (single) |
| LinkedIn Recruiter Lite (2-5 seats) | ~$2,670/seat/year |
| LinkedIn Recruiter Corporate | ~$10,800-$12,960/seat/year (2026) |
| Enterprise (with API partnership) | Custom, significantly higher |

LinkedIn raised Recruiter Corporate pricing ~15% in 2026. Renewal invoices landing at $10,800-$12,960/seat. Users report declining effectiveness despite rising costs.

## ToS Restrictions

**Key clauses (LinkedIn User Agreement + API Terms)**:
> "Members must not... Scrape or copy profiles and information of others through any means (including crawlers, browser plugins, or add-ons, or any other technology)"

> LinkedIn prohibits "selling access to an aggregated collection of Member profiles... or any social activity such as posts, likes, or shares by Members."

> LinkedIn prohibits "using APIs to retrieve content that is then aggregated with third party data in such a way that a User cannot attribute the Content to LinkedIn."

**Enforcement track record (2025)**:
- January 2025: LinkedIn filed suit against Nubela (Proxycurl) — a popular LinkedIn data enrichment API
- Early 2025: Apollo.io and Seamless.ai both had company pages removed for ToS violations
- LinkedIn actively sends cease-and-desist letters to any startup attempting to aggregate profile data

## Key Case Law

### hiQ v. LinkedIn (2017-2022)
- **2022 Ninth Circuit ruling**: Scraping public LinkedIn data does not violate CFAA's "without authorization" provision
- **2022 Settlement**: hiQ agreed to $500,000 judgment, liability under California torts (trespass to chattels, misappropriation), and permanent injunction against scraping LinkedIn
- **Bottom line**: CFAA is not the weapon LinkedIn uses — California state tort law is. Scraping LinkedIn data, even if technically public, creates significant legal exposure even post-hiQ.

### SCOTUS Cert Denied (2022)
- Supreme Court declined to review — Ninth Circuit's narrow CFAA interpretation stands
- But settlement means the case never produced a definitive ruling on state tort claims

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Sign-In with LinkedIn to get basic profile | ✅ Allowed | OpenID scopes only (name, email, photo) |
| Read full LinkedIn work history via API | ❌ Not accessible | Requires partner agreement (Talent Solutions) |
| Aggregate LinkedIn profiles for B-side feed | ❌ Prohibited + litigated | ToS hostile; active enforcement in 2025 |
| Scrape LinkedIn profiles | ❌ Prohibited + litigated | $500K judgment precedent; active suits 2025 |
| User exports their own LinkedIn data | ✅ Possible | LinkedIn's "Data Export" feature (PDF/CSV); must be user-initiated |
| Build recruiter tool accessing LinkedIn at scale | ❌ Dead end | Requires $10K+/seat LinkedIn partnership |

**Recommended approach**: Use LinkedIn only for Sign-In (OAuth identity verification). For career data, rely on GitHub, Substack, Behance/Dribbble. If user wants LinkedIn data included, prompt them to upload their own LinkedIn data export.

---
*Sources: V608, V609, V610, V611*
