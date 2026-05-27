# EU AI Act — Data Collection Notes

## TL;DR (150-250 words)
The EU AI Act (Regulation EU 2024/1689) entered into force in August 2024, with phased enforcement milestones. The most critical milestone for our product is **August 2, 2026** — the date when full compliance obligations for Annex III high-risk AI systems become enforceable. Employment and recruitment AI is explicitly listed in Annex III, Section 4, as a high-risk category. This includes: AI systems used "to place targeted job advertisements, to analyse and filter job applications, and to evaluate candidates" (Section 4(a)), and AI systems used "to make decisions affecting terms of work-related relationships... to allocate tasks based on individual behaviour or personal traits or characteristics or to monitor and evaluate the performance and behaviour" (Section 4(b)). Our B-side product — where AI-generated career profiles are visible to employers and influence hiring decisions — almost certainly qualifies as a high-risk AI system under Section 4(a). C-side personal insight tools (where the user sees AI-generated career reflection only for their own use) may qualify as lower risk, but this depends on how the output is framed. High-risk system obligations include: mandatory risk assessments, bias testing, human oversight, transparency disclosures (Article 26(7)), record-keeping for 6 months, and registration in the EU AI Act database. Fines: up to €15 million or 3% of global annual turnover for non-compliance. Citation range: V637-V640.

---

## Timeline and Enforcement Milestones

| Date | Milestone |
|---|---|
| August 1, 2024 | EU AI Act entered into force (publication in Official Journal) |
| February 2, 2025 | Chapter I (definitions) and Chapter II (prohibited AI practices) enforceable |
| August 2, 2025 | GPAI model provisions (Chapter V) enforceable |
| **August 2, 2026** | **Full Annex III high-risk system obligations enforceable** ← our product |
| August 2, 2027 | High-risk AI systems embedded in regulated products (medical, transport, etc.) |

## Annex III — High-Risk AI Systems Directly Relevant to Our Product

**Section 4: Employment, workers management and access to self-employment**

**(a) Recruitment and selection:**
> "AI systems intended to be used for the recruitment or selection of natural persons, in particular to place targeted job advertisements, to analyse and filter job applications, and to evaluate candidates"

**(b) Work-related decisions and monitoring:**
> "AI systems intended to be used to make decisions affecting terms of work-related relationships, the promotion or termination of work-related contractual relationships, to allocate tasks based on individual behaviour or personal traits or characteristics or to monitor and evaluate the performance and behaviour of persons in such relationships"

**Related recital**: Recital 57 provides context on why employment AI is high-risk (significant power imbalances, potential for discrimination, irreversible impact on livelihoods).

## How Our Product Maps to Annex III

| Product Feature | Annex III Applies? | Analysis |
|---|---|---|
| C-side: AI generates career insights for user's own reflection | Likely NO (or lower risk) | Not used for recruitment decisions; user sees own data; no employer involvement |
| B-side: AI-generated career profiles visible to employers | **YES — HIGH RISK** | "Evaluate candidates" — directly covered by Section 4(a) |
| B-side: Employer search using AI-generated tags/skills | **YES — HIGH RISK** | "Filter job applications" and "analyse and evaluate candidates" |
| Matching users to job opportunities via AI | **YES — HIGH RISK** | "Place targeted job advertisements" and candidate evaluation |
| B-side: AI scores a user's professional development | **YES — HIGH RISK** | "Evaluate candidates" / "monitor and evaluate performance" |

## Compliance Requirements for High-Risk Systems (Art. 9-17)

If our B-side product qualifies as a high-risk AI system, the following must be in place by **August 2, 2026**:

### Art. 9 — Risk Management System
- Establish, implement, document, and maintain a risk management system throughout the AI system's lifecycle
- Identify and analyze known and reasonably foreseeable risks
- Implement risk management measures

### Art. 10 — Data Governance
- Training, validation, and testing datasets must meet quality criteria
- Datasets must be relevant, representative, and free of errors
- Bias monitoring required

### Art. 11 — Technical Documentation
- Detailed documentation: purpose, design, data used, performance metrics, architecture
- Must be maintained throughout lifecycle and updated when system changes

### Art. 13 — Transparency and Information Provision
> Deployers and users must be "informed about the system they are using, the capability and limitations of that system, and the human oversight measures in place"

### Art. 14 — Human Oversight
> "High-risk AI systems shall be designed and developed... in such a way... that they can be effectively overseen by natural persons"
- No final placement, rejection, or evaluation decision should be made by AI alone
- Qualified human must be "in the loop" for decisions affecting individuals

### Art. 26(7) — Transparency to Workers (Key for Employment AI)
> "Deployers shall inform workers' representatives and affected workers... who have a right to know that AI is being used, how it functions, and what role it plays in decisions that affect them"

In the context of a talent platform: job candidates must be informed that an AI system was used to evaluate their profile before employer contact.

### Record-Keeping
- Deployers must keep logs generated by high-risk AI systems for **at least 6 months**

### Registration
- High-risk AI systems must be registered in the EU AI Act database (managed by Commission)

## Penalties

| Violation Type | Maximum Fine |
|---|---|
| Using prohibited AI (Chapter II) | €35 million or 7% of global annual turnover |
| Non-compliance with Annex III high-risk obligations | **€15 million or 3% of global annual turnover** |
| Providing incorrect/misleading information to authorities | €7.5 million or 1.5% of global annual turnover |

## Art. 6 — Classification Rules

To determine if an AI system falls under Annex III:
1. Is it explicitly listed in Annex III? (YES for employment/recruitment AI)
2. Does it pose significant risk of harm to health, safety, or fundamental rights? (YES — employment decisions)

An AI system is NOT high-risk if it is a "narrow procedural task" or if it "does not materially influence the outcome of the decision-making" (Art. 6(3)). This is the potential escape hatch for C-side tools that only give the user their own insights without influencing third-party decisions.

## Product Architecture Implications

**C-side design (potentially lower risk)**:
- User connects their own accounts → AI generates personal career narrative → user sees output → user controls what, if anything, to share with employers
- The AI system's output does not directly influence employer decisions
- May qualify as Art. 6(3) exception: "does not materially influence the outcome of the decision-making"

**B-side design (high-risk)**:
- Employer searches → AI-ranked profiles displayed → employer contacts candidates
- The AI system IS materially influencing employer hiring decisions
- Full Annex III compliance required by August 2, 2026

**Recommended architecture**: Keep C-side (personal insights) and B-side (employer-facing) as distinct product modes with clearly documented different risk classifications. Design C-side first; delay B-side until compliance infrastructure is built.

---
*Sources: V637, V638, V639, V640*
