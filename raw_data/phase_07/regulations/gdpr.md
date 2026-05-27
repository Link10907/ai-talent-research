# GDPR — Data Collection Notes

## TL;DR (150-250 words)
The General Data Protection Regulation (GDPR, Regulation EU 2016/679) is the primary privacy framework governing our product's EU users. Three provisions are directly product-shaping. First, "personal data" is defined broadly (Art. 4) to include any information relating to an identifiable natural person — meaning GitHub usernames, Substack publication URLs, portfolio URLs, and work histories all qualify. Second, Art. 6 requires a lawful basis for processing; for our C-side product, explicit user consent (Art. 6(1)(a)) is the cleanest basis. Third, and most critically for the "AI generates personal insights" feature: Art. 22 restricts "solely automated decision-making... which produces legal effects or similarly significantly affects" the data subject. The CJEU's SCHUFA ruling (December 2023) extended Art. 22 to situations where AI output significantly influences downstream human decisions — meaning an AI-generated "talent score" visible to employers falls squarely under Art. 22 scrutiny. Safeguards required: human review, right to contest, right to explanation. Real enforcement context: Meta's €1.2B fine (May 2023) for EU-US data transfers without adequate mechanism; TikTok's €345M fine (September 2023) for children's data failures. Any EU-serving product must treat GDPR compliance not as optional but as a design constraint from day one. Citation range: V629-V633.

---

## Key Definitions (Art. 4 GDPR)

### Personal Data
> "Any information relating to an identified or identifiable natural person ('data subject'); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, psychological, genetic, mental, economic, cultural or social identity of that natural person."

**Implications for our product**:
- GitHub username → personal data (identifiable natural person)
- Substack publication URL → personal data
- Portfolio URL → personal data
- Work history inferred from GitHub commit messages → personal data
- AI-generated career "persona" description → personal data
- ETH wallet address (Mirror.xyz) → personal data (identifiable in most cases)

### Processing
"Any operation... performed on personal data... including collection, recording, organisation, structuring, storage, adaptation or alteration, retrieval, consultation, use, disclosure, erasure or destruction."

**Implication**: Fetching a user's GitHub data, storing it, running it through an LLM, and displaying the output are ALL "processing" steps, each requiring lawful basis.

## Art. 6 — Lawful Basis for Processing

Six lawful bases exist. Most relevant for our product:

| Basis | Art. 6 Clause | Our Product Applicability |
|---|---|---|
| Consent | (1)(a) | ✅ Primary basis — user explicitly connects accounts |
| Contract performance | (1)(b) | ✅ Secondary — processing necessary to deliver service |
| Legitimate interests | (1)(f) | ⚠️ Available but must pass balancing test |
| Legal obligation | (1)(c) | ❌ Not applicable |
| Vital interests | (1)(d) | ❌ Not applicable |
| Public task | (1)(e) | ❌ Not applicable |

**Recommended approach**: Build on Art. 6(1)(a) consent as primary basis. This requires:
- Freely given, specific, informed, and unambiguous indication of agreement
- Granular consent per data source (GitHub consent ≠ Twitter consent)
- Easy withdrawal mechanism (Art. 7(3))
- Records of when consent was given (Art. 7(1))

## Art. 22 — Automated Decision-Making

**Full text of Art. 22(1)**:
> "The data subject shall have the right not to be subject to a decision based solely on automated processing, including profiling, which produces legal effects concerning him or her or similarly significantly affects him or her."

**Three narrow exceptions** (Art. 22(2)):
- (a) Necessary for entering/performing a contract
- (b) Authorized by EU/Member State law
- (c) Based on explicit consent

**When exceptions apply**, the controller must implement safeguards including:
> "the right to obtain human intervention on the part of the controller, to express his or her point of view and to contest the decision."

**Special category data** (Art. 22(4)): If the automated decision involves special categories (race, health, sexual orientation, religion, union membership, biometric/genetic data), additional restrictions apply.

**SCHUFA Ruling (CJEU, December 2023)**: The CJEU ruled that credit scoring algorithms fall under Art. 22 when they "significantly influence" a downstream human decision — even if the final decision is made by a human. This is directly relevant to our product: if we generate a "talent profile" that an employer views and uses to decide whether to contact a candidate, Art. 22 applies.

**Product implication**:
- ❌ **Dead end**: Fully automated scoring that produces a "talent tier" visible to employers without human review
- ✅ **Viable**: AI-generated insights presented as "personal reflection tools" to the user (C-side only; user controls visibility to employers)
- ✅ **Viable with safeguards**: If employer-visible scores exist, must implement: (1) human oversight mechanism, (2) explanation of how score was derived, (3) right for the scored person to contest

## User Rights Under GDPR

| Right | Article | Key Requirement |
|---|---|---|
| Access | Art. 15 | User can request all data held about them |
| Rectification | Art. 16 | User can correct inaccurate data |
| Erasure ("right to be forgotten") | Art. 17 | User can request deletion; must delete from all systems within 30 days |
| Restriction of processing | Art. 18 | User can pause processing while disputing accuracy |
| Data portability | Art. 20 | User can request data in machine-readable format (JSON, CSV) |
| Objection | Art. 21 | User can object to processing based on legitimate interests |
| Automated decision-making | Art. 22 | See above |

**Product implications**:
- Must build user data download feature (Art. 15 + 20)
- Must build user data deletion feature (Art. 17) — including from all connected platform caches
- Must provide human review channel if employer-visible automated scores exist (Art. 22)

## Art. 5 — Data Minimization Principle
> "Personal data shall be... adequate, relevant and limited to what is necessary in relation to the purposes for which they are processed ('data minimisation')."

**Product implication**: Do not store raw GitHub repos or full tweet archives if you only need summary statistics. Process and store derived insights, not raw data dumps.

## Data Transfers Outside EU (Chapter V)

| Mechanism | Basis | Status |
|---|---|---|
| Adequacy Decision | Art. 45 | US → EU-US Data Privacy Framework (July 2023) — US companies that self-certify can receive EU data |
| Standard Contractual Clauses (SCCs) | Art. 46 | Most widely used; requires Transfer Impact Assessment (TIA) |
| Binding Corporate Rules (BCRs) | Art. 47 | For intra-group transfers in multinationals |
| Consent | Art. 49 | One-time transfers only; explicit consent required |

**Schrems II (CJEU, 2020)**: Invalidated EU-US Privacy Shield. Transfers to US required either SCCs + TIA, or reliance on the successor framework (EU-US Data Privacy Framework, 2023).

**Practical implication**: If product is US-hosted and EU users connect their accounts, either:
- Use EU-US Data Privacy Framework (self-certify with DoC), OR
- Use SCCs with TIA for US data processing

## Real GDPR Enforcement Examples

| Company | Fine | Date | Reason |
|---|---|---|---|
| Meta (Ireland DPC) | **€1.2 billion** | May 2023 | EU-US personal data transfers without adequate protection mechanism |
| TikTok (Ireland DPC) | **€345 million** | September 2023 | Children's data processing failures |
| Meta (Ireland DPC) | €91 million | September 2024 | Storing user passwords in plaintext |
| Google (CNIL, France) | €90 million | December 2021 | Cookie consent failures |
| Amazon (Luxembourg) | €746 million | July 2021 | Cookie consent failures |
| WhatsApp (Ireland DPC) | €225 million | September 2021 | Transparency failures |

**Cumulative GDPR fines** as of January 2025: approximately €5.88 billion total across all enforcement actions.

**Maximum fine levels**:
- Tier 1 (serious violations): Up to €20 million or 4% of global annual turnover (whichever is higher)
- Tier 2 (less serious violations): Up to €10 million or 2% of global annual turnover

---
*Sources: V629, V630, V631, V632, V633*
