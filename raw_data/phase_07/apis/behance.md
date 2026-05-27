# Behance API — Data Collection Notes

## TL;DR (150-250 words)
Behance has an official API, but it has been in a transitional state since Adobe acquired Behance and began migrating developer tooling to the Adobe Developer Console (adobe.io). As of 2025-2026, the original Behance API (which provided endpoints for projects, users, collections, and work-in-progress) is technically accessible but requires API key approval through Adobe, and the approval process has been described by the community as slow or opaque. Adobe's stated goal was to migrate the Behance API fully to the adobe.io developer ecosystem, but no specific public launch date has been confirmed. The original API did support OAuth for user authorization and offered read access to public portfolio data including projects, user profiles, and work-in-progress pieces. The platform's overall design goal was "to provide just about every function of Behance through the API, both read and write." However, practical access is gated by Adobe's approval process, making it unreliable as a core data source for a startup without an established Adobe partnership. For our product, the most feasible approach is: user provides their Behance profile URL, we use whatever public API access is available under approved terms, or fall back to user-exported portfolio data. Citation range: V615-V616.

---

## API Status (2025-2026)
- **Original Behance API**: Available in principle, requires Adobe API key approval
- **Migration to adobe.io**: Ongoing — Adobe has moved developer tooling to the Adobe Developer Console but the Behance-specific API documentation is sparse
- **Approval process**: Required via Adobe Developer Console; described as slow/opaque by the developer community
- **Status**: Transitional — less reliable than GitHub or Dribbble for startup integration

## Available Endpoints (Original API)
- Projects (portfolio pieces)
- Users (profiles)
- Collections (curated groups)
- Comments
- Work in Progress (WIP)
- Statistics (views, appreciations)

The API provides "granular access to projects, users and works in progress by searching a number of different criteria such as popularity, tags, location, creative fields, and more."

## OAuth and Authentication
- **Authentication**: API key (for public data) + OAuth 2.0 (for user-specific data)
- **OAuth redirect URI**: Optional unless user authentication is required
- **Scope**: Read and write capabilities; specifics depend on approved use case

## What Can Be Read with API Access
- Public user profile: name, bio, location, URL, occupation
- Public projects: title, description, cover image, tags, tools used, views, appreciations, comments
- Portfolio collections
- Work in progress entries

**Not accessible**: Private projects, follower/following lists (in full), direct messages

## Rate Limits
- Not publicly documented in current Adobe documentation
- Legacy Behance API documentation cited standard HTTP rate limiting
- Recommend treating it as ~60-100 requests/minute (conservative estimate)

## ToS Restrictions
- Data must be used for purposes that enhance the Behance community or creative ecosystem
- Reselling profile data for recruitment purposes likely prohibited under both Behance ToS and Adobe's general API terms
- No explicit scraping prohibition language found, but unauthorized scraping violates general Adobe ToS

## Pricing
- No public API fee for approved developers
- Adobe Developer Console access is free for basic API integrations
- Commercial applications may require partnership agreement with Adobe

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read public user portfolio via API | ✅ Possible | Requires Adobe API key approval |
| OAuth login to read user's private projects | ✅ Possible | OAuth + API approval needed |
| Aggregate Behance profiles for B-side feed | ⚠️ Gray area | ToS likely prohibits talent reselling |
| Scrape Behance without API | ❌ ToS violation risk | Adobe ToS prohibits unauthorized scraping |
| User-initiated data connection | ✅ Best approach | OAuth flow + API key |

**Recommended approach**: Apply for Adobe Developer Console API key early in product development. Design for OAuth user authorization flow. Do not rely on Behance as a primary data source given API instability.

---
*Sources: V615, V616*
