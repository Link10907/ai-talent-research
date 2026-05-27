# Notion API — Data Collection Notes

## TL;DR (150-250 words)
Notion has a well-documented public API (current version: 2025-09-03) that follows OAuth 2.0 for public integrations. However, the API is architecturally designed around a page-scoped consent model — users must explicitly select which pages and databases to share with an integration during the authorization flow. The integration does not automatically gain access to the entire workspace. This is both a privacy strength and a product design challenge: to read a user's Notion data, they must individually select which pages to share. The critical limitation: the Notion API cannot access public Notion pages without OAuth — attempting to access publicly shared pages that aren't shared with the integration returns a 404 error. This makes Notion fundamentally different from GitHub (where public data is truly public via API). For our product, Notion is useful only if the user actively wants to share their workspace content — such as a professional portfolio, writing samples, or project documentation they've stored in Notion. The use case is narrower than GitHub or Behance. Notion is primarily useful for knowledge workers who store their professional portfolio in Notion and want AI insights about their work style. Citation range: V622-V623.

---

## API Status (2025-2026)
- **Notion API**: Active and well-maintained
- **Current Version**: 2025-09-03 (set via `Notion-Version` header)
- **Base URL**: `https://api.notion.com/v1/`
- **Status**: Production-ready; regularly updated

## Authentication Model

**Public Integrations (OAuth 2.0)**:
- Users authorize via standard OAuth flow
- Users explicitly select pages and databases to share during auth
- Integration does not receive blanket workspace access
- Access is limited to pages the user has explicitly shared

**Internal Integrations (API key)**:
- Workspace admins create integration tokens
- Access limited to pages connected to the integration
- Not suitable for a public product (requires workspace admin rights)

**Personal Access Tokens (PAT)**:
- Available for individual developer use
- User generates from account settings
- Can be shared with third-party services (with user consent)

## Available Capabilities (Read)

| Capability | Status |
|---|---|
| Read page content (blocks) | ✅ Allowed (if shared) |
| Read database records | ✅ Allowed (if shared) |
| Read page properties and metadata | ✅ Allowed (if shared) |
| Read comments | ✅ Allowed (if shared) |
| Read workspace structure | ✅ Allowed (if shared) |
| Read user profile | ✅ Basic info (name, avatar, email) |
| Read public pages without auth | ❌ Not possible (404) |
| Read unshared pages | ❌ Not accessible |

## Key Limitation: Page-Scoped Consent

> "Users select specific pages and databases to share with the integration during authorization, and the integration does not automatically gain access to all content in the workspace."

This is a critical design constraint: unlike GitHub where "authorize once and access all public repos," Notion requires page-level sharing decisions from the user.

## Rate Limits
- Not published in detail by Notion
- General rate limiting applies; standard REST API throttling
- Notion API is not intended for high-volume bulk reads

## What User Data Is Practically Available

For a user who actively shares their Notion workspace:
- **Portfolio pages**: Written case studies, design documentation
- **Project databases**: Project histories with dates, statuses, tags
- **Writing samples**: Blog drafts, articles, notes
- **Skill/tool databases**: If user maintains skill inventories in Notion

**Signal quality for career insights**: HIGH for knowledge workers who actively use Notion for professional documentation. ZERO for users who don't use Notion or haven't shared relevant pages.

## Pricing
- **No API fee** for approved integrations
- Notion's own free tier allows API access
- Business/Enterprise Notion plans have higher API rate limits

## ToS Restrictions
- Notion's API terms follow standard patterns: no data resale, respect user consent, remove data within 30 days of user deletion request
- Data obtained via API must be used for the purpose the user authorized

## Our Product Assessment
| Action | Status | Condition |
|---|---|---|
| Read user's shared Notion pages via OAuth | ✅ Allowed | User must explicitly share pages |
| Read public Notion pages without auth | ❌ Not possible | API returns 404 |
| Aggregate Notion data for B-side | ❌ Not feasible | Access inherently user-consented |
| Generate AI insights from user's Notion | ✅ Allowed | User consent + data minimization |
| Access entire workspace automatically | ❌ Not allowed | Page-scoped consent model |

**Recommended approach**: Offer Notion as an optional connection. User connects via OAuth and selects specific pages to share (e.g., their professional portfolio pages). Use this to augment career insight with writing style and project diversity data.

---
*Sources: V622, V623*
