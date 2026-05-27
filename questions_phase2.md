# Phase 2 — Open Questions for Human Review

Date: 2026-05-25
Agent: Phase 2 relay sub-agent

## Methodological gaps that need human confirmation

1. **Reddit data missing entirely**
   WebFetch is blocked from www.reddit.com and old.reddit.com. r/LinkedInLunatics, r/recruitinghell, r/cscareerquestions, r/jobs, r/freelance, r/digitalnomad are the highest-value direct user-voice sources for this phase and we have NO direct quotes from them — only indirect references in articles citing Reddit. If the human reviewer can manually pull 10-20 top posts/comments from these subreddits, the report's Section 1 frequency rankings could be substantially improved. Currently the rank order is best-effort triangulation from secondary sources.

2. **B 层 (AI-augmented traditional professionals) direct-voice gap**
   The most strategically important user segment per CONTEXT.md — lawyers, doctors, marketers, HR, finance, consultants who use AI as their differentiator — has the WEAKEST direct evidence in this phase. They don't write blogs, they don't post on HN. They are present in industry communities (Slack groups, industry-specific Substacks, regional Lunch Club meetings), which our tooling cannot reach. Phase 3 (industry deep-dives) should be designed to capture this voice directly.

3. **Quantitative dissatisfaction surveys: none found**
   No first-party survey data was located giving a clean "what % of LinkedIn users are dissatisfied to the point of considering leaving." The 6.5/10 score in this report is a synthesized judgement, not an empirical measurement. If a Pew / Edison / Gartner survey exists, it would replace this judgement with hard data.

4. **Geographic bias unaddressed**
   All evidence is US-skewed. Phase 5 should explicitly weight the report's conclusions against European GDPR-aware users, Asian region-specific platforms (LinkedIn loses share to Xiaohongshu among China-adjacent diaspora, to Wantedly in Japan), Latin America, etc.

5. **CNBC Open-to-Work article (403) and Loyolan "I hate LinkedIn" (429)**
   Both fetches failed. The CNBC piece was the original source for the "220M Open-to-Work users" stat and the Nolan Church quote — these are quoted in the report from search-result summaries, which is one level less verifiable than fetched primary content.

## Conceptual questions for the strategy team

6. **"Show, don't tell" thesis: how broadly does it generalize?**
   The phrase is from a designer (Matiaude on Read.cv) and resonates strongly in creative / dev circles. But a lawyer's "work" is not portfolio-able in the same way (most cases are confidential). Does the product need to redefine "work evidence" for non-creative professions? Examples:
   - Lawyers: speaking engagements, publications, expert witness work, bar association leadership
   - Doctors: research, clinical outcomes, conference talks
   - Salespeople: testimonials, case studies, deals won (but most are confidential)
   - HR: programs designed, books/courses written, conferences spoken at

   If "work evidence" for these groups looks remarkably like LinkedIn's existing "experience + recommendations + publications" format, the differentiation is weaker than it appears for designers/devs.

7. **The "AI competence as evidence" hypothesis from CONTEXT.md is underexplored**
   We have no direct evidence in Phase 2 of users in traditional professions wanting to display their AI-augmentation. This is the central insight of CONTEXT.md but Phase 2 (LinkedIn dissatisfaction) is the wrong lens to see it through. Phase 3 (industry AI penetration) should design its prompts explicitly around: "how do AI-augmented [lawyers/marketers/finance] currently display this fact to employers?"

8. **Trust / longevity moat for any new product**
   HN evidence (dorian-graph, pixeldrifter, elashri) suggests an alarming share of the most engaged users have been burned 2-3 times by acquisitions and shutdowns. Any pitch needs to address:
   - Data portability commitment (technical: open export, ideally self-hosted option)
   - Governance commitment ("we won't sell to a search engine")
   - Longevity signal (B-end revenue makes us not dependent on user-side monetization)

   These are product-design constraints from the user-voice evidence.

## Issues to flag in Phase 5 synthesis

9. **Migration willingness score (2.5/10) is the most contrarian finding**
   This contradicts an intuitive read of the data (LinkedIn is hated, surely people would switch). Phase 5 should not soften this — three failed serious attempts (Polywork, Read.cv, Bento) is hard quantitative evidence. The strategic implication: do not pitch the product as "LinkedIn replacement" — pitch as additive layer.

10. **LinkedIn's algorithm reform partially defuses the cultural critique**
    The 360Brew rollout and AI-content de-prioritization mean that by H2 2026, the "LinkedIn is full of slop" complaint may be substantially weaker than it was in 2024-2025. The market window for "better-curated LinkedIn alternative" is **closing**, not opening. Phase 5 should weigh this carefully.
