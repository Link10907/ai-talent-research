# 调研中遇到的问题(各 Phase 汇总)

主 Claude 在 Wave 3 准备阶段合并自 questions_phase*.md。
所有问题保留原文,按 phase / industry 分组。Phase 5 综合报告应基于此列表
整理待人工决策清单。

---
## phase1

# Phase 1 — Open Questions for Human Review

接力 agent 在 Phase 1 完成时仍存在的待确认问题。这些问题不影响 Phase 1 报告交付,但应在 Phase 2/3/5 时回头校准。

## 数据冲突

1. **Wall Street junior 招聘**: Fortune (2025-06) 说大行考虑砍 junior 招聘 2/3 [P1-007];Fortune (2025-12) 说 Goldman 实际加了 1,800 人、JPM 加了 2,000、整体 headcount 稳中略升 [P1-008]。**6 个月时差是否解释这个矛盾?还是前者是 narrative、后者是事实?** 倾向后者,但需要 Phase 3 金融行业调研单独验证。

2. **候选人 AI 能力造假率**: Greenhouse (2025-07) 说 32% [P1-010];GCheck (2026-05) 说 63% [P1-019]。这个翻倍是真实加速?还是 GCheck (背调商) 有利益偏向夸大?需要 Phase 5 看是否有第三方独立交叉来源。

3. **PwC 56% wage premium**: 一年从 25% 跳到 56% 显著太大 [P1-003]。是 composition effect (AI 岗 skew senior 拉高均值)?还是采样方法变化?PwC 报告本身没充分披露。

## 信息缺口

4. **欧洲大陆 / 亚洲数据**: 全部数据是 US/UK 视角。海外市场以欧美为主 (按 CONTEXT.md),但欧洲大陆 (德国/法国/北欧) 的招聘趋势没单独取证。

5. **JD 文本样本**: 没有直接抓取 LinkedIn/Indeed 上"requires AI proficiency" 类岗位的样本——靠的是 Lightcast/PwC 的二手聚合。如有 API/抓取能力,直接拉 200 个 JD 做文本分析会显著加强证据。

6. **小企业 vs 大企业**: HR Dive 提到大公司 65% 中型 45% 的 AI 要求差异 [P1-036],但小企业 (<200 人) 完全没数据。我们的目标用户群更可能在小公司工作。

7. **"AI 能力如何具体被评估" 实操**: 找不到一个广泛部署的、结构化的 AI 能力测评方法。雇主用什么标准筛?面试用什么任务?待 Phase 4 (竞品分析) 或专门搜索补充。

## 判断的不确定性

8. **趋势 1 评分 4/10 vs 5/10**: 关键依赖未来 6-18 月的加速度判断。如果"junior pipeline 压缩"在律所/投行真的兑现,4/10 可能保守;如果不兑现,4/10 偏高。

9. **"portfolio over resume" 在非创意/非技术岗位是否真的能成立**: 律师 portfolio 长什么样?会计师 portfolio 长什么样?医生 portfolio 长什么样?概念上有,实操中没看到任何例子。Phase 3 行业调研里需要逐行业问。

10. **AI-generated portfolio 造假的解决方案**: Greenhouse 已经发现 28% 候选人用 AI 生成假作品集 [P1-029]。如果作品集本身可造假,所谓"portfolio over resume"的产品命题需要新的信任层 (provenance, AI-usage logging, real-time co-creation 记录)。这是产品级问题,Phase 1 只能 flag。

---

## phase2

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

---

## phase3_consulting

# Open Questions - Phase 3 Consulting

These are items I could not resolve during desk research; flagging for human follow-up.

1. **Real fractional revenue concentration**: 110K LinkedIn profiles claim "fractional" but how many earn >$100K/year actually working as fractionals? Median revenue? Without this, pricing decisions are blind.

2. **Reddit r/consulting voice**: WebSearch could not surface r/consulting threads. Worth a targeted manual scrape of:
   - Threads about Lilli / Deckster / Sage from junior consultants
   - Threads about "leaving for indie consulting"
   - Threads about LinkedIn marketing for consulting

3. **NDA tolerance for sanitized case studies**: Anecdotal evidence says firms tolerate anonymized cases; but is there a real legal-risk study quantifying this? Affects how aggressive product can be on case-study features.

4. **Maven / Substack consultant economics**: Jason Liu's "five-figure deals + waitlist" - how representative is this? Is there a creator-economy-style power law (top 1% earn 80%) or a flatter distribution?

5. **Catalant / Toptal churn**: how often do consultants who join these marketplaces leave or stop using them? Indicates whether marketplaces are sticky or transactional.

6. **AI-visibility metrics**: is there empirical evidence that consultants get clients via ChatGPT/Perplexity recommendations yet, or is this still hypothesis? P3CON-014 claims it but with vendor incentive.

7. **MBB junior attrition rates 2024-2025**: HBR claims AI is changing the pyramid, but I could not find hard attrition-rate deltas. Are juniors leaving faster or being hired less?

8. **Geography**: are fractional/indie trends as strong in EU and APAC as in US? Affects market sizing.

9. **B-side recruiter willingness**: would corporate hiring managers actually use a consultant-identity database to source fractional/indie talent, or are they wedded to LinkedIn + referrals?

10. **Big-firm consultant data restrictions**: how aggressive are McKinsey/BCG/Bain about restricting employee external content? This determines whether they can use any external identity product at all.

---

## phase3_finance

# Phase 3 Finance — Open Questions

## Tactical questions surfaced during research

1. **Is the pedigree filter actually loosening at the margin?** Source [P3FIN-014] suggests the opposite — pedigree filter hardens while AI becomes table stakes. But I have only one commentary-grade source. Need: harder Bureau-of-Labor or recruiter-firm data on (a) % of analyst hires from non-target schools in 2020 vs 2025, (b) % of mid-career lateral hires citing AI experience.

2. **What % of finance job descriptions explicitly list AI skills?** I have anecdotal data (CFI says "now preferred over Excel-only" but they're a vendor). A structured Indeed/LinkedIn scrape of 50+ JDs from each subgroup would yield a defensible quantitative answer.

3. **What does the Big 4 alumni network actually look like online?** If KPMG cut 29% of grad intake [P3FIN-004], where do those rejected/displaced grads go and how do they identify themselves? LinkedIn searches for "ex-KPMG" or "former Big 4" in 2025 cohorts would reveal whether they're already a coherent group.

4. **Is the FP&A creator economy concentrated or distributed?** Nicolas Boucher dominates. Are there 5 Bouchers or 50? If it's a power law, partnership economics differ vs broad bottoms-up acquisition.

5. **How does compliance treat AI workflow artifacts shared anonymously / abstractly?** A junior IB analyst can't share a real pitchbook, but could they share an anonymized prompt template? Banks' employee policies on personal blogging about AI are unclear from public sources.

6. **What is the actual willingness to pay for FP&A community products?** AI Finance Club's pricing/retention is private. If 1,500 members pay ~$50/month, that's $900k/yr — modest. If they pay $200/month, that's $3.6M/yr — meaningful. Need: pricing intel.

7. **How big is the "fintech operator" subgroup really?** This is more PM/ops/growth than engineer — different from the GitHub-served dev population. Sizing is loose.

8. **Substack vs LinkedIn as the right surface for finance creators**: Nicolas Boucher publishes on both. Which converts to paid community better? This is meta for product design.

9. **Compliance-safe portfolio formats**: Could a product offer "anonymized engagement summary" formats (e.g., "led close cycle automation reducing time 4 hours → 45 minutes" with timestamps and tool stack but no client data)? Need legal review of what's actually shareable.

10. **The "VC associate" beachhead may be saturated**: VCs already have X, Substack, LP letters, Twitter Spaces, podcasts. What unmet need do they have for another identity platform? This question undercuts my recommendation if the answer is "none."

## Questions to escalate

- Should we restrict scope to "AI-fluent finance professionals" (smaller, more coherent) or include "all finance professionals" (larger, more diffuse)?
- For B2B monetization, which finance recruiter customer segment is most willing to pay for enriched profiles: BB hiring desks, PE/HF talent partners, fintech recruiters, or accounting firms?

---

## phase3_healthcare

# Phase 3 Healthcare — 待人工确认的问题清单

1. **Doximity 与本产品的位置关系**:如果 Doximity 已经 verify 80%+ 美国医生,
   且与 ABMS 数据同源,我们的产品在医生侧的真实切入点是什么?是否值得放弃这个
   群体而专注 digital health professionals + informaticists?

2. **FSMB AI 责任规则的反向利用**:既然医生不能轻易公开 AI 能力,产品是否应该
   做"私下记录、机构内验证"的功能,而不是公开 portfolio?这与"反哺 B 端数据库"
   的核心商业逻辑是否冲突?

3. **医美 / mental health 是否进入主战场**:这两个子群体行为更像 small business
   owner / creator,不像传统 professional,但仍属于"healthcare"。要不要单独拆
   出来在另一份报告里评估?

4. **国际市场优先级**:NHS clinician 似乎在 AI 采用上比美国更慢(机构规范更紧),
   但 TikTok 已经在 UK 建 Clinician Creator Network。是否英国是 MD-influencer
   方向的更好切入点?

5. **资源验证缺口**:Doximity 2026 报告原文、AMA 完整 PDF、FSMB recommendation 原文
   都因 403 没读到。建议主 agent 后续重新尝试或换 user-agent / 用其他 fetch 工具。

6. **临床信息学子群体的真实可触达性**:AMIA 4000 会员 + Chartis / Epic UGM 等线下
   pool,本报告把这个群体列为重点之一,但没有直接评估他们对 "另一个职业身份产品"
   的开放度(他们都在 LinkedIn + AMIA 上很满意)。需要 Phase 2 类型的用户访谈
   补强。

---

## phase3_hr

# HR Phase 3 — Open Questions for Human Review

1. **Reddit ground truth gap.** WebFetch blocked Reddit; my read on frontline recruiter sentiment is inferred. Worth a 30-min manual pass on r/recruiting, r/humanresources, r/AskHR specifically searching: "AI sourcer layoff", "ChatGPT recruiter", "fake candidate", "AI generated resume." Findings could materially shift the C-side priority score.

2. **Should we have a separate sub-priority for "fractional CHRO / People-Ops creator" niche?** That cohort (~1-5K globally) is small but high-trust, AI-curious, status-hungry, and visible. They could be a credible early-adopter beachhead for an HR-flavored variant of our product. Worth a strategic-yes/no decision before Phase 5.

3. **Confirmation needed: is our B-side product positioned to absorb the candidate-fraud tailwind?** I claim Gartner's "1 in 4 fake by 2028" + Amazon's blocked NK-linked hires creates massive demand for verified-identity data. This needs to be validated against our actual B-side architecture: do we have identity-verification primitives, or just data scale?

4. **EU AI Act exposure for our own product.** If we build C-side ranking/recommendation features that B-side buyers use for hiring decisions, we may fall under EU AI Act "high-risk" classification (Feb 2 2025 enforcement on banned practices, broader compliance ramping). Legal review needed before EU launch.

5. **Agency-recruiter angle was thin in my research.** They have different economics (BD pressure, success-fee model, smaller tool budgets per seat). If they're a relevant buyer/user, a focused half-day is warranted.

6. **Should HR people-analytics tier be served by a separate product line?** Chief People Analytics Officers at $200-275K+ have a real "demonstrate AI-augmented impact" need, but their data is corporate-confidential. A SaaS or community for this thin upper tier could be high-margin but tiny.

7. **The "I Hate It Here" precedent.** Hebba Youssef built 136K subs on Substack+podcast WITHOUT building a new platform — she stayed on LinkedIn for distribution and used external media for depth. Is this evidence that HR audiences fundamentally don't migrate platforms? If yes, our C-side strategy for this segment should be "creator-channel partnership" not "user acquisition."

---

## phase3_operations

# Phase 3 Operations — Open Questions for Human Review

These are the questions/uncertainties I could not resolve via desk research that the
team should consider before product decisions on the Operations vertical.

## High-stakes inferences (need primary research to confirm)

1. **Will ops people actually publish?** The entire thesis depends on whether
   BizOps/CoS/RevOps practitioners would *publicly* share AI workflows / playbooks
   when given a polished venue. I have no direct data — only the negative signal
   that WizOps (9,400 members) shows no public AI positioning [P3OPS-007] and ops
   thought leaders are scarce. Recommend 10-20 user interviews before commitment.

2. **Employer IP constraint severity.** Senior ops people's most valuable AI work
   is built on proprietary frameworks and customer data. How much can they
   credibly *sanitize and publish*? If the answer is "almost nothing," the
   product fundamentally cannot work for this segment.

3. **AI-CoS / AI-BizOps title is the right wedge?** The role exists [P3OPS-004,
   P3OPS-005] but is still small (50 listings via Evan Lee, hundreds globally).
   Is this the right MVP segment, or should we target the broader "ops generalist
   wanting to upskill" market (much larger, much fuzzier)?

## Data gaps

4. **Raw JD scrape needed.** Evan Lee's 50-job roundup [P3OPS-005] doesn't publish
   full JDs. A direct LinkedIn/Greenhouse scrape of 30-50 AI-CoS / BizOps roles
   would let us build a real skill-frequency map.

5. **Cross-consulting-firm layoff data.** McKinsey's 200 cuts + 10%-by-2027 is one
   data point [P3OPS-009]. BCG, Bain, Deloitte, Accenture comparable signals would
   strengthen (or weaken) the "junior ops compression" thesis.

6. **Geographic split.** All sources US-centric. European/APAC ops norms around
   self-promotion and public writing may differ materially.

## Product-design questions

7. **Should ops have its own vertical product or live inside a multi-industry one?**
   Ops sociology (private Slack, anti-self-promotion, fragmented sub-roles) differs
   enough from designers/engineers that a dedicated UX may be warranted — but the
   smaller TAM may not support a standalone product.

8. **What's the *unit of artifact* for an ops portfolio?** Candidates: (a) an n8n /
   Zapier workflow with anonymized data, (b) a Notion AI Workflow OS template
   [P3OPS-018], (c) a "personal AI CoS" markdown KB [P3OPS-006], (d) a case-study
   write-up with before/after metrics, (e) a Loom of a working agent. We need to
   pick a hero artifact for MVP and I don't have enough user evidence to choose.

9. **How do we prevent the product from looking like a vendor-marketing site for
   Zapier/n8n/Notion templates?** If the artifact unit is "automations," the
   product risks reducing to a template marketplace rather than an identity venue.

---

## phase3_sales

# Phase 3 Sales — Open Questions Surfaced During Research

These are questions that emerged during the sales-industry investigation that could not be
fully answered with desk research and would benefit from primary user research,
sales-rep interviews, or hiring-manager surveys.

## A. Quota-attainment as signal — how broken is it really?

- Different sources report wildly different quota-attainment numbers (16%, 33%, 42%
  hitting quota in 2024-2025). Which is the truth in the AI-augmented cohort?
- More importantly: are hiring managers actually discounting quota numbers now, or
  do they still treat "Achieved 124% of quota at Snowflake" as a strong signal even
  when the rep used AI tooling? Need to interview 5-10 SaaS sales hiring managers.

## B. "Did you or did Alice?" — is it really a felt problem?

- The whole product premise that "reps will want to prove their AI orchestration"
  rests on this being a felt pain. But my data is from vendor blogs and analyst
  newsletters. Need to validate via: (1) Reddit r/sales sentiment, (2) actual
  rep interviews, (3) hiring-manager interviews. My Reddit searches did not
  surface enough direct rep voices.

## C. Clay Slack community — actual portfolio behavior?

- Clay Slack is described as the "closest analogue to GitHub for GTM." But is
  there actually a culture of *showing off* tables/workflows there, or is it
  mostly help-requests and job posts? Need direct community lurking to verify.
- If portfolio behavior exists organically there, that's the strongest signal
  for a "GitHub-for-GTM" product. If not, the cultural foundation is weaker
  than my report implies.

## D. GTM Engineer trajectory beyond the hype

- GTM Engineer postings grew 205% YoY 2024-2025. Is this a one-year hype spike or
  a structural new role? Postings could re-flatten if "GTM Engineer" gets
  re-absorbed into RevOps / Marketing Ops.
- Also: 5,075 profiles in Nov 2025 is a tiny pool. Could it plateau at <20K?

## E. LinkedIn substitutability for sales — any signal of erosion?

- Sales reps' LinkedIn dependency is described as the deepest of any white-collar
  function. Is there *any* erosion signal — e.g., reps complaining about LinkedIn
  algorithm changes, ad-load, declining inMail response rates?
- The 18-25% LinkedIn InMail response rate stat is from LinkedIn-sourced material;
  in 2026 with AI-driven messaging, the real response rate may be much lower.

## F. Sales rep willingness to maintain a portfolio venue

- Sales reps are time-poor. They will not invest 1-2 hr/week in a portfolio venue
  unless it produces leads, job offers, or comp upside. What's the minimum viable
  loop that produces that signal? This needs prototype testing, not desk research.

## G. AI SDR collapse — is the narrative settled?

- Public coverage in 2025-2026 is dominated by "AI SDR failing" stories
  (11x, Artisan). But a16z, Benchmark, etc. still have capital deployed and will
  push successors. Could a second-wave AI SDR (better personalization, smaller
  send volume, hybrid by design) flip the narrative back? My report assumes the
  "human-orchestrating-AI" identity is durable; if AI SDRs get genuinely good,
  the identity premium collapses.

## H. International (EMEA / APAC) sales practice

- I did not investigate non-US sales practice at all. Quota culture is weaker
  in Europe; LinkedIn dominance is also weaker; AI SDR adoption is later.
  Recommended sample: UK, Germany, India, Singapore sales-rep interviews.

## I. Sub-industry differentiation

- I treated "sales" as one block but enterprise sales, mid-market SaaS, SMB
  outbound, and inside sales have very different AI exposure and identity
  pressures. The product implications could differ a lot. Worth a follow-up
  Phase 3.5 focused on the sub-segments.

---

