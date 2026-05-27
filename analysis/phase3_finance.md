# Phase 3 Industry Report — Finance

**Scope**: investment banking, equity research, asset management, PE/VC, quant/hedge funds, FP&A and corporate finance, accounting & audit, financial analyst, fintech.
**Date**: 2026-05-25
**Author**: Phase 3 finance sub-agent

---

## A. AI 渗透成熟度

**Overall score: 7 / 10** — but the headline number hides large variance across subgroups. The shape is bimodal: aggressive enterprise rollouts at the very top (BB IB, top quant, Big 4) combined with shallow ChatGPT-as-faster-Excel adoption among the broad professional middle, plus a long tail (community banking, traditional accounting practices) that is barely touched.

### Subgroup-level breakdown

| Subgroup | Penetration | Where AI is deepest |
|---|---|---|
| Investment banking (BB analyst/associate) | 7-8 | Pitchbook generation, doc summarization, comp tables, deal research drafting [P3FIN-001, P3FIN-022] |
| PE / VC associates | 8-9 | Deal sourcing, memo drafting, due diligence, portfolio data ops [P3FIN-003] |
| Equity research (sell-side) | 7 | Earnings summaries, data extraction, broader coverage with smaller teams [P3FIN-013, P3FIN-012] |
| Asset management / buy-side traders | 5-6 | 85% use AI somewhere, but only ~25% in actual trading decisions [P3FIN-012, P3FIN-021] |
| Quant / multi-strat hedge funds | 9 | AI/ML is the product; recruiting from DeepMind/OpenAI [P3FIN-006, P3FIN-016] |
| FP&A / corporate finance | 6-7 | 79% adopted, but mostly Excel automation & report polish [P3FIN-002] |
| CFO office (enterprise) | 6 | 59% function-level adoption, plateauing; 87% leadership intent for 2026 [P3FIN-009] |
| Big 4 audit / accounting | 7 (intent), 5 (workflow) | Doc review, research drafting, compliance checks — grad pipeline collapsing in response [P3FIN-004] |

### Concrete signals of an industrial-scale inflection

- **Goldman Sachs** rolled out **GS AI Assistant firmwide** mid-2025 after a ~10,000-employee pilot; model-agnostic across GPT/Gemini/Claude inside an audited env [P3FIN-022].
- **JPMorgan** runs multiple IB CoPilots and a Virtual Assistant that fields queries like "What wires cleared yesterday?" [P3FIN-022].
- Industry refrain: "A first-year analyst can now supervise AI to do work that once required three analysts" [P3FIN-001, P3FIN-022].
- **Bessemer** reclaimed **234 hours/analyst/year** post-AI integration; **BlackRock** hit **5x research throughput** [P3FIN-003].
- **Big 4 grad intake collapsed**: KPMG -29%, Deloitte -18%, EY -11%, PwC -6%; accountancy grad listings down 44% YoY; AI-related job postings now ~7% of all Big 4 ads vs <3% audit [P3FIN-004].
- **Numerai** raised $30M in 2025 with J.P. Morgan providing up to $500M capacity. YC's Spring 2026 RFS explicitly calls for AI-native hedge fund agent swarms [P3FIN-016].

### Where the inflection has **not** happened

- Buy-side trading desks (only 25% considering AI for actual execution) [P3FIN-012].
- Mid-market FP&A: 68% spend ≤5 hrs/month on AI upskilling; 15% spend zero. AI is "faster Excel," not strategic [P3FIN-002].
- Function-level CFO adoption has flatlined: 59% (2025) vs 58% (2024) [P3FIN-009].

**My interpretation**: the inflection has arrived in research/document/data tasks across the entire stack, but real strategic AI use (modeling decisions, capital allocation, trading) is still well behind because of regulatory, data-trust, and liability constraints — 75% of CFOs cite security/privacy as a major worry; only 10% fully trust their enterprise data [P3FIN-009].

---

## B. "AI 能力" 在该行业的具体定义

In finance, "AI capability" splits into **three distinct meanings** depending on the level of the role:

### Layer 1 — Tool fluency (analyst / associate / FP&A)
This is the dominant meaning today and the one nearest to becoming **table stakes**:
- Comfort using ChatGPT, Claude, Copilot, BloombergGPT, internal CoPilots for drafting, summarization, comp tables.
- Pairing GenAI with VBA / Python / Excel to automate formatting and basic modeling [P3FIN-005].
- Verifying AI outputs against source documents — increasingly framed as "data verification" rather than data gathering [P3FIN-001].
- Indeed/CFI job specs codify it: "AI-Powered Financial Analyst, $95k–$150k, Python + Bloomberg + GenAI tools" [P3FIN-008].

### Layer 2 — Workflow design (senior analyst, VP, PM, controller)
Mid-career professionals are evaluated on the ability to **redesign processes around AI**:
- Designing repeatable AI prompts/agents for due diligence, memo drafting, variance analysis.
- Choosing vendor stack (Drivetrain, Concourse, Affinity, Harmonic) and integrating outputs into governance [P3FIN-002, P3FIN-003].
- Knowing the failure modes — being able to articulate when AI shouldn't be used (compliance, audit trail) [P3FIN-010].

### Layer 3 — Domain prompt engineering / hybrid quant (specialist)
A narrow but well-compensated emerging role:
- **JPMorgan prompt engineer**: $110k-$220k. **Goldman**: $115k-$235k. Project Pluto Financial Prompt Engineer requires 1-4 yrs front-office + GenAI tool expertise [P3FIN-007].
- Hedge fund hybrid quants: cross-functional squads of quant researcher + SWE + ML expert + PM are replacing siloed roles. Demand outpaces supply in NY/London/Amsterdam [P3FIN-006].

### How recruiters actually evaluate it
- Mostly through **proxies**: LinkedIn course badges (Columbia, IMA, MIT CSAIL, Wharton, CFI) and creator credentials (e.g., AI Finance Club membership) [P3FIN-017, P3FIN-011].
- Stronger signal: **prior firm experience deploying AI** (e.g., "led implementation of Copilot in our FP&A close cycle"). This shows up in headlines and JD bullets, not in portfolios.
- Almost never via portfolio of real work — because real work touches confidential data and bank policies prohibit public sharing [P3FIN-010].
- For prompt-engineer-with-finance-domain roles: take-home prompt design exercises during interviews [P3FIN-007].

**Critical observation**: AI capability has become a **new baseline credential**, not a pedigree replacement. Workers with AI skills earn 56% more than peers in same jobs (up from 25% premium just a year prior) [P3FIN-014]. But the same article notes banks chasing fewer associate seats will look for "top 0.1% not top 1%" — pedigree filter **hardens** while AI skill becomes table stakes [P3FIN-014, P3FIN-015]. The hypothesis "AI replaces pedigree" does not hold in finance.

---

## C. 用户行为

### How finance professionals display AI capability today

1. **LinkedIn headlines and skill tags** — most common, lowest-information channel. "AI-enabled FP&A leader" or "ChatGPT for Finance" badges from CFI/IMA/Columbia [P3FIN-017].
2. **Course credentials and certifications** — Columbia 8-week, MIT CSAIL, IMA Micro-credential. These are widely promoted, easy to acquire, but increasingly noisy [P3FIN-017].
3. **Newsletter / Substack / X for select subgroups**:
   - **VC partners and associates**: Highly active. Andreessen, Andrew Chen, Brad Feld, Josh Kopelman, Mike Seibel are all public AI commentators with deal-flow incentive to be visible [P3FIN-018].
   - **FP&A creator economy**: Nicolas Boucher reaches 1M+ across LinkedIn/Substack; AI Finance Club has 1,500+ paying members. Christian Martinez, Anders Liu-Lindberg, the FP&A Guy are similar voices [P3FIN-011].
   - **FinTwit**: Vibrant but composed of retail traders, journalists, economists, advisors — **not** sell-side analysts or IB juniors [P3FIN-018].
4. **WSO and r/FPandA forums**: Discussions of practical AI use (VBA + ChatGPT for Excel automation) happen here, but almost always anonymous [P3FIN-005, P3FIN-020].

### Why displaying AI capability is hard in finance specifically

- **Compliance walls**: JPM, DB, WF, BofA, Citi, GS, MS all banned public ChatGPT for confidential work. Sharing real workflow examples is a fireable offense [P3FIN-010].
- **Competitive culture / information advantage**: IB and buy-side analysts have strong cultural and economic disincentives to publicly share methods. Equity research alpha is a depleting asset when broadcast.
- **Pedigree fixation**: identity in finance is still "where I worked" — Goldman, McKinsey, Sequoia. Practitioners optimize LinkedIn for firm logos, not skill demonstrations [P3FIN-015].
- **AI errors create cleanup tax**: WSO threads show consistent complaint that fact-checking AI outputs takes longer than original work, eroding enthusiasm to share [P3FIN-005].

### Pain points
- The **gap between "I use AI" (cheap claim) and "I demonstrably ship better work with AI" (hard to prove)** is widening. Every analyst now claims AI fluency; few have a way to show it.
- The **AI-skill premium is real but illegible**: 56% pay bump for AI skills [P3FIN-014], but recruiters can't reliably tell who has it without proxies.
- **Displaced Big 4 grads and accounting professionals** are facing the worst pipeline collapse in years and have the strongest motivation to find an alternative identity channel — but they're also the most pedigree-conditioned [P3FIN-004].
- **FP&A creator audiences exist but the format is "course / Substack"** — there's no profile platform that captures workflow demonstrations.

### Subgroup behavior summary

| Subgroup | Public-AI-display willingness | Existing channel |
|---|---|---|
| IB juniors | Very low | Anonymous WSO |
| Sell-side equity research | Low | Reports (firm-owned) |
| Buy-side analyst / PM | Very low | None |
| Quant / hedge fund | Low (IP-protected) | GitHub for hobbyists only |
| PE associate | Low-medium | Substack, X |
| **VC associate / partner** | **High** | **X, Substack, LinkedIn** |
| FP&A / corp finance | Medium | LinkedIn, Substack, AI Finance Club |
| Accounting / Big 4 | Low | LinkedIn course badges |
| Fintech | High | GitHub, X, Substack |

---

## D. 作为切入点的评估

### Reachability
- VC and fintech subgroups are the **most reachable** — already on X/Substack/Product Hunt, used to demonstrating thesis publicly [P3FIN-018].
- FP&A creator community concentrates around named KOLs (Nicolas Boucher's AI Finance Club has 1,500+ paying members). Reachable via partnership but small absolute size [P3FIN-011].
- IB/PE/buy-side are gated communities reached through traditional channels (recruiters, WSO, alumni networks).
- Accounting/Big 4 grads reachable via LinkedIn at high volume.

### Willingness to pay / share data
- VC associates: high willingness to share, low willingness to pay (they're employed at high-margin firms; tool is overhead).
- FP&A pros: medium willingness to pay for tools that demonstrably improve work (Boucher charges for courses and his community fills up).
- IB/PE juniors: very low willingness to share due to compliance, but high latent willingness to pay for **career mobility** signals.
- Big 4 displaced grads / mid-level accountants: high willingness to share AND pay because the alternative is unemployment or offshore-displacement [P3FIN-004].

### Market size (rough order-of-magnitude, global)
- IB analysts/associates: ~150k-300k.
- PE/VC professionals: ~200k-400k (LPs included, lower in pure VC).
- Equity research analysts: ~70k-100k.
- Hedge fund / asset management front office: ~200k-400k.
- **FP&A and corporate finance**: 3-5M+ globally — by far the largest segment.
- **Accountants (incl. Big 4 alumni and current)**: 10M+ globally; CPAs in US alone ~650k+.
- Fintech engineers/operators: 1-2M globally.

So the volume centers are FP&A + accounting + fintech, NOT IB or VC despite their visibility.

### Subgroup-level priority recommendation

| Subgroup | Reachability | Pay/Share willingness | Size | **Priority (0-10)** |
|---|---|---|---|---|
| **VC associate / partner** | 9 | 5 (share) / 3 (pay) | 4 | **8** — best beachhead; reach & creator culture |
| **FP&A / corporate finance** | 7 | 7 | 9 | **8** — biggest volume + active creator community |
| Fintech operator | 8 | 5 | 6 | **7** — but overlaps with existing dev identity products (GitHub) |
| Big 4 / accounting (esp. displaced) | 6 | 8 | 10 | **7** — large + motivated, but pedigree-conditioned |
| Equity research analyst | 4 | 4 | 3 | 4 |
| IB junior | 3 (compliance walled) | 2 (share) / 7 (pay for mobility) | 5 | 3 |
| Buy-side analyst / PM | 3 | 2 | 6 | 3 |
| Quant / hedge fund | 3 (IP-walled) | 3 | 3 | 2 |

### **Overall finance industry priority: 6.5 / 10**

**Reasoning**:
- AI inflection has clearly arrived in finance, *and* AI skill commands an unambiguous wage premium (+56%) [P3FIN-014].
- But three structural barriers reduce the addressable opportunity:
  1. **Compliance**: regulated subgroups (IB, buy-side, banking) physically can't share most AI workflow artifacts [P3FIN-010].
  2. **Pedigree obsession**: finance professional identity is still firm-name-anchored; "where I worked" beats "what I built" in hiring [P3FIN-014, P3FIN-015].
  3. **Audit-trail expectation**: real finance work outputs (a financial model, a memo, a deal book) are not naturally shareable artifacts.

- The realistic entry strategy is **VC + FP&A creator community first**, then expand to **fintech operators**, then opportunistically into **displaced accountants / Big 4 alumni** as a re-identification product.
- IB / buy-side / quant should be deprioritized as launch wedges (interesting later via passive enrichment or premium B2B channels).

### Why not higher
- LinkedIn is sticky in finance because firm logos = currency. Disrupting this requires either (a) bypassing the hiring funnel (impossible at the bulge bracket level) or (b) targeting the subset where firm logos no longer fully signal value — which is mostly fintech and AI-native finance.

### Why not lower
- FP&A creator economy proves there is genuine appetite for skill-based identity in finance.
- 56% AI-skill wage premium creates real economic incentive for employees to invest in demonstrable AI competence.
- The Big 4 grad collapse is a once-in-a-generation displacement event creating millions of professionals who need a new way to signal value — even if they don't realize it yet.

---

## 调研局限性

1. **English-language and US/UK source bias**: Almost all sources are Anglo-American. Asian finance hubs (Hong Kong, Singapore, Tokyo) and continental European banks may have very different AI adoption curves and cultural attitudes toward public skill display.
2. **Compliance-driven invisibility**: The most senior and most-impacted finance professionals are precisely the ones who can't talk publicly about their AI workflows. This research is structurally biased toward visible voices (creators, VCs, journalists) and away from the silent majority.
3. **Vendor-conflicted sources**: A large fraction of AI-in-finance research is published by vendors (Drivetrain, Affinity, Kyriba, Workday) with commercial incentive to inflate adoption numbers. I weighted multiple sources but cannot fully correct for this.
4. **Time series fragility**: 2024-vs-2025 adoption stats are very close (58% → 59% in Gartner's CFO data [P3FIN-009]), suggesting either real plateau or measurement noise. Hard to tell which.
5. **Reddit/forum access blocked**: Several WSO threads returned 403 to direct fetch; I relied on summarized search snippets, which are softer evidence than direct excerpts. r/FPandA, r/FinancialCareers should be re-scraped with a real browser session for richer qualitative data.
6. **Sample bias toward "AI in finance" narrative**: My search terms surface optimistic AI-in-finance content; I tried to balance with skeptical sources (Fortune Dec 2025 "more hype than takeover", WSO bear takes) but the corpus tilts pro-adoption.
7. **Specific JD review skipped**: I did not pull a structured sample of 30-50 Indeed/LinkedIn job descriptions to quantify how often AI skill is *required* vs *preferred* vs *bonus*. This would be the highest-value follow-up.
8. **Subgroup boundaries blur**: Where does "fintech AI engineer" end and "quant" begin? Where does "FP&A analyst" end and "data analyst at a fintech" begin? Aggregating size estimates is rough.
9. **No primary practitioner interviews**: All evidence is secondary. A handful of 30-min conversations with FP&A managers, VC associates, and Big 4 displaced grads would substantially sharpen the prioritization.
