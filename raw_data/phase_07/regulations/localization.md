# Data Localization & Cross-Border Transfer — Data Collection Notes

## TL;DR (150-250 words)
Data localization requirements affect where we can store and process user data. GDPR does not mandate EU data residency, but requires a legal transfer mechanism for data leaving the EEA. The most practical 2025 pathway for US-hosted products serving EU users is the EU-US Data Privacy Framework (DPF, July 2023), which restored a legal mechanism after Schrems II invalidated the EU-US Privacy Shield in 2020. US companies that self-certify with the Department of Commerce can receive EU personal data without needing Standard Contractual Clauses (SCCs). However, the DPF faces ongoing political risk (a Schrems III challenge is expected). The safest long-term path is EU data residency (hosting in AWS eu-west, Google Cloud europe-west, or Azure westeurope). China's PIPL (effective 2021, updated 2024) is the most restrictive: any Chinese user data generally requires a CAC security assessment before leaving China's borders, though a 2024 exemption applies for HR management and transfers involving fewer than 100,000 individuals. Brazil's LGPD adopted mandatory SCCs in August 2024 with a grace period that ended August 23, 2025. US state laws (Virginia VCDPA, Colorado CPA, Connecticut CTDPA, Utah UCPA) are generally less prescriptive on data localization but have employment data carve-outs that expired for California and remain in some other states. Citation range: V641-V645.

---

## GDPR + Standard Contractual Clauses

### Key Principle
GDPR (Chapter V, Art. 44-49) does not prohibit transferring EU personal data outside the EEA, but requires a legal transfer mechanism that ensures "essentially equivalent protection."

### Transfer Mechanisms Available

| Mechanism | Basis | Practical Status (2025) |
|---|---|---|
| Adequacy Decision | Art. 45 | US (EU-US DPF, July 2023); UK; Switzerland; Japan; South Korea; Canada (commercial); 14 others |
| Standard Contractual Clauses (SCCs) | Art. 46(2)(c) | Most widely used; 2021 versions required; + Transfer Impact Assessment (TIA) |
| Binding Corporate Rules (BCRs) | Art. 47 | Intra-group only; requires DPA approval |
| Derogations (consent, contract necessity) | Art. 49 | One-time/occasional transfers only; not for systematic processing |

### EU-US Data Privacy Framework (DPF)
- Adopted July 10, 2023, replacing the invalidated EU-US Privacy Shield
- US companies self-certify with the US Department of Commerce
- Once certified: EU data can flow to the US company without SCCs
- **Risk**: The DPF faces a legal challenge before the CJEU (expected "Schrems III"). The NOYB advocacy group has pledged to challenge it. DPF may be invalidated within 2-5 years of adoption.

### Standard Contractual Clauses (SCCs)
- Updated versions adopted June 2021; required for all new contracts from December 2022
- Must be used with a **Transfer Impact Assessment (TIA)**: analysis of whether the receiving country's laws (e.g., US government surveillance under FISA Section 702) undermine the SCC protections
- US transfers under SCCs require TIA acknowledging US surveillance law risks + supplementary measures (encryption, pseudonymization, etc.)

### Practical Implications
- **Simplest path**: Host in EU (eliminates need for transfer mechanism entirely)
- **Acceptable path**: US hosting + DPF self-certification (risk: possible Schrems III invalidation)
- **Fallback path**: US hosting + SCCs + TIA (legally defensible but administratively burdensome)

---

## China PIPL (Personal Information Protection Law)

### Effective Date
- PIPL effective: November 1, 2021
- Cross-border transfer regulations updated: 2022-2024

### Key Requirements for Cross-Border Transfer (Art. 38 PIPL)

Three pathways for transferring personal information outside China:
1. **CAC Security Assessment**: Required for processors who handle personal information of 1 million+ individuals, or transfer 100,000+ individuals' data cross-border in one year, or transfer 10,000+ "sensitive personal information" records
2. **Certification**: By a certified professional institution approved by the CAC
3. **Standard Contract**: Sign the CAC-approved standard contract with the foreign recipient

### 2024 Regulatory Updates
- CAC issued Provisions on Promoting and Regulating Cross-Border Data Flows (March 2024), creating exemptions:
  - HR management exemption: Transfers for HR management of employees based outside China
  - Small volume exemption: Fewer than 100,000 individuals — no mechanism required
  - Contractual necessity: Transfer necessary to perform a contract with the individual

### Landmark Court Decision (September 2024)
- Guangzhou Internet Court ruled: Company need not obtain individual consent to transfer data cross-border if transfer is necessary to perform its contract with that individual
- First-ever PIPL court decision on cross-border transfers

### Implication for Our Product
- If we have Chinese users: their data flowing to US servers requires either:
  - A formal CAC security assessment (complex, slow), OR
  - Reliance on the contractual necessity exception (contract with the user), OR
  - Storing Chinese user data in China (data residency in China)
- Our primary market appears to be international (non-China), minimizing this risk
- If we reach 100,000+ Chinese users, must implement PIPL transfer mechanism

---

## Brazil LGPD (Lei Geral de Proteção de Dados)

### Effective Date
- LGPD enacted: August 14, 2018
- Enforcement: August 2020
- International transfer regulations: August 2024 (Resolution CD/ANPD No. 19/2024)
- Grace period ended: **August 23, 2025** — mandatory SCCs now required for international transfers

### Key Requirements (2025 onward)
- International transfers of personal data from Brazil to foreign recipients require one of:
  - ANPD adequacy decision (none exist yet for most countries)
  - **ANPD-approved Standard Contractual Clauses** (mandatory since August 23, 2025)
  - Other ANPD-authorized mechanisms
- Non-compliance: administrative and civil sanctions under LGPD Art. 52

### Implication for Our Product
- Any Brazilian users' data being processed outside Brazil requires ANPD-approved SCCs
- These are similar to GDPR SCCs but Brazil-specific
- Grace period ended August 23, 2025 — no more delay is available

---

## US State Privacy Laws

### Overview: 22 States with Comprehensive Privacy Laws (as of May 2026)

Key active laws and their stance on employment/professional data:

| State | Law | Effective | Employment Data Exemption |
|---|---|---|---|
| California | CCPA/CPRA | Jan 1, 2020 / Jan 1, 2023 | **Expired January 1, 2023** — fully covered |
| Virginia | VCDPA | January 1, 2023 | Yes — "consumer" excludes individuals acting in employment context |
| Colorado | CPA | July 1, 2023 | Yes — employment/commercial context excluded |
| Connecticut | CTDPA | July 1, 2023 | Yes — employment context excluded |
| Utah | UCPA | December 31, 2023 | Yes — employment/commercial context excluded |
| Texas | TDPSA | July 1, 2024 | Partial — employee data of the controller's own employees |
| Montana | MCDPA | October 1, 2024 | Yes — employment context excluded |
| Delaware | DPDPA | January 1, 2025 | Yes — employment context excluded |

### Key Finding
- California (CPRA) is the outlier: **no employment data exemption since 2023**
- Most other state laws exempt professional/employment data when individuals act in an employment capacity
- This creates a two-tier compliance landscape: California requires full CCPA compliance for professional data; most other states have lower thresholds
- **Bottom line**: Design for California-level compliance and you cover all other states

### Data Localization Requirements Under US State Laws
- **No US state law mandates data localization** (unlike EU GDPR or China PIPL)
- US state laws focus on consumer rights (access, deletion, opt-out) rather than where data is stored
- This makes US hosting simpler from a data residency perspective

---

## Summary: Data Storage Recommendations

| Scenario | Recommended Approach |
|---|---|
| EU users (primary market) | EU data residency (simplest) OR EU-US DPF self-certification (simpler than SCCs) |
| US users | No localization requirement; standard US hosting OK |
| Brazilian users | Brazil-compliant hosting OR ANPD SCCs for international transfer (mandatory since Aug 2025) |
| Chinese users (if applicable) | China data residency OR PIPL standard contract; evaluate volume against exemptions |
| Global product with <100K users per jurisdiction | Most PIPL exemptions apply; GDPR DPF path viable; LGPD SCCs required |

---
*Sources: V641, V642, V643, V644, V645*
