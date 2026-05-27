# Phase 07 — 技术、合规、商业的真实约束

> 分析对象:跨平台职业数据聚合 + AI 生成个人身份 + B 端反哺的产品形态
> 目标市场:美国 + 欧盟(以 EU AI Act 为最严约束基准)
> 关键日期:2026-08-02(EU AI Act 高风险义务全面生效)

---

## TL;DR

5 条预先必须接受的硬约束。先看,再设计:

**1. EU AI Act 把"招聘 AI"列入 Annex III §4(a) 高风险类别(V637, V638),2026-08-02 enforcement。** 任何"AI 生成的职业画像被雇主用于评估候选人"的形态,在欧盟运营都必须满足风险管理、偏见测试、人工监督、6 个月日志、EU 数据库注册等全套义务,违规上限 €15M / 3% 全球营收。
→ **产品决策**:C 端"用户看自己"的洞察可以做(Art. 6(3) 程序性任务 escape);**B 端任何"雇主直接看 AI 评分"的形态必须在 2026-08-02 前要么合规要么改架构**,否则不能在欧盟运营。

**2. LinkedIn 对第三方实质关闭(V608-V611)。** OAuth 只给 `openid/profile/email`,Talent Solutions API 需要 partnership,hiQ 案 $500K 判决 + 2025-01 LinkedIn vs Proxycurl 诉讼证明 California 州 tort 法律仍然致命。
→ **产品决策**:**我们不能做"一键聚合用户的 LinkedIn 工作经历"**。LinkedIn 只能当 sign-in,职业数据必须从 GitHub / Substack / 个人站 / 用户自己上传的 LinkedIn export PDF 来。

**3. GitHub ToS 显式禁止"把 GitHub 用户数据卖给 recruiters / headhunters / job boards"(V602)。** 这条直接命中我们 B 端反哺模式。
→ **产品决策**:**B 端不能是"我们把 GitHub-derived 数据卖给雇主"**;只能是"用户主动把自己生成的 profile 推给特定雇主"。所有权和触发点必须在用户那一侧。

**4. CCPA "sale" 定义极广(Cal. Civ. Code §1798.140(ad), V635),B2B 豁免 2023-01-01 已过期(V636)。** 把用户职业数据传给雇主换取付费 = sale,必须提供 "Do Not Sell" opt-out。AI 推断出的职业画像(§1798.140(v)(1)(L))显式被列为 personal information。
→ **产品决策**:不能 silently 把 derived profile 给雇主,必须有 do-not-sell 链接 + 15 工作日响应 opt-out。

**5. 23andMe 2025-03 破产 + 1500 万用户基因数据被法院批准打包出售给 TTAM(V649, V650),28 州 AG 反对失败。** 即使账号创建时同意了"research use",事后 business model 变化或破产时,用户信任和舆论会爆炸。
→ **产品决策**:数据架构不能产生一个"可以脱离用户关系单独卖掉的 data asset"。需要 user-keyed encryption 或类似机制,并预写"我们倒闭怎么办"的用户协议。

> 这 5 条共同决定:**产品形态是"用户自己持有数据 + 用户主动 share 给雇主"的 user-initiated 路线,不能是"我们后台聚合 + 卖给雇主"的 silent broker 路线**。

---

## 1. 多平台数据聚合的真实门

### 1.1 主对比表

| 平台 | API 状态 | OAuth 用户可读 | Rate Limit | 成本 | ToS 对第三方聚合 | 关键案例 / 法律 | 给我们的结论 |
|---|---|---|---|---|---|---|---|
| **GitHub** | ✅ REST + GraphQL 稳定 | `read:user` + `public_repo`:profile、repos、commits、languages、pinned、README | 5,000 req/hr (auth) | 免费 | ToS 显式禁止"selling personal info to recruiters, headhunters, job boards" (V602) | D.9 AI-training reciprocity 条款 (gray) | **开放公路(C 端)/ 死路(B 端 silent resale)** |
| **X (Twitter)** | ⚠️ 高度商业化 | `tweet.read` + `users.read`:profile + timeline | 10,000 app/15min;900 user/15min | $0.005/post read,Basic $200/mo,Pro $5K/mo,Enterprise ~$42K/mo (V604) | ToS 明禁 scraping;禁止 aggregation for resale | X v. CCDH (2024) 被驳回但 ToS 仍生效;Meta v. Bright Data (2024) logged-out scraping 边界 | **窄道**:用户 OAuth 可读但贵;**死路**:任何 scraping 或 B 端规模化聚合 |
| **LinkedIn** | ❌ 严重关闭 | `openid` + `profile` + `email` only(姓名、邮箱、头像) | 未公布 | Recruiter Corporate $10,800-$12,960/seat/yr (V646) | 显式禁止 scraping、聚合、resale | hiQ v. LinkedIn $500K 判决(2022 settlement);LinkedIn v. Proxycurl 2025-01 起诉 (V610) | **死路**:仅可做 sign-in;工作经历数据须靠用户上传自己的 LinkedIn data export |
| **Substack** | ❌ 无官方 API | N/A — 仅 RSS | 未公布 | 免费(RSS) | ToS 禁止 "scraping" 和 "copying" | 无主流诉讼,但 ToS 风险存在 | **窄道**:RSS 抓 free posts + 标题/频率/topic;paywalled 内容必须靠 user export |
| **Behance** | ⚠️ Adobe API,需审批 | OAuth:projects, profile, WIP, stats | 未公布(~60-100/min 估) | 免费(需 Adobe Developer Console 批准) | 禁止 talent reselling;禁止未授权 scraping | 无显著诉讼 | **窄道**:必须提前申请;**死路**:bulk scraping |
| **Dribbble** | ✅ v2 API 稳定 | `public` scope:shots, tags, stats, profile | 60 req/min,1,440 req/day | 免费(application required,通常自动批准) | **显式**:"Scraping...is strictly prohibited";禁止 "competing designer hiring service" | 无主流诉讼 | **窄道(C 端)**;**显式死路**:B 端 hiring tool |
| **Medium** | ⚠️ 官方 API 偏写,几乎停滞 | `basicProfile` + `listPublications`(自己的);其它用户读不到 | 未公布 | 免费 | ToS 通用禁 scraping | 无主流诉讼 | **窄道**:RSS @username 拿 topic 信号;深度只能让用户给自己的 integration token |
| **Notion** | ✅ API 2025-09-03 | OAuth + 用户**逐页授权**;读 blocks, properties, comments | 未公布(general throttling) | 免费 | ToS 标准:no resale, 30 天删除响应;架构上即 consent-first | 无主流诉讼 | **窄道**:数据质量取决于用户主动 share 多少页;non-Notion 用户无效 |
| **Mirror / Paragraph** | ❌ 无 API,但**数据在 Arweave 公链** | 任何人都能读(无需 auth) | Arweave gateway 无明确限制 | 免费 | 链上数据无 ToS;但作者 ETH 地址 + 内容 GDPR 仍适用 | 无诉讼;PIPL/GDPR identifiable natural person 风险 | **开放公路**(法律上)/ **窄道**(身份匹配难,niche) |
| **个人站** | ❌ 无统一 | HTTP GET + Readability.js;WordPress `wp-json` / Ghost Content API 公开 | 无 | 免费 | 视站点 robots.txt + ToS | hiQ(Ninth Cir. 2022)+ Meta v. Bright Data(N.D. Cal. 2024)给 logged-out scraping 留窗口;但 GDPR 仍需 lawful basis | **开放(user-provided URL)**;**死路**:bulk crawl without consent → GDPR violation |

### 1.2 三类路况判断

**开放公路**:
- **GitHub** — API 干净、数据丰富、OAuth scope 清楚、ToS 对 C 端"user pulls his own data"几乎无障碍。MVP 主入口。
- **Mirror/Paragraph** — 链上公开,reading 完全合法;但 niche,身份匹配需用户主动 link ETH 地址。
- **个人站(user-provided)** — Meta v. Bright Data 后 logged-out 公共读取的 ToS 风险大幅降低;只要用户主动提供 URL + 我们尊重 robots.txt,法律风险 LOW。

**窄道**(可做,有具体约束):
- **Substack** — 只能 RSS;只能 free posts;paywalled 必须 user export。"我们做不到自动读取用户的 paid posts。"
- **Behance** — 必须先申请 Adobe Developer Console,不能假设可以快速接入;要有 portfolio URL fallback。
- **Dribbble** — C 端干净,但 ToS **显式**禁止"competing designer hiring service" → 我们不能让雇主在产品里直接搜索 Dribbble designers。
- **Medium** — RSS 拿到 topic 信号已够;深度只能靠用户提供自己的 integration token。
- **Notion** — 只对"已经把 portfolio 存在 Notion 里"的用户有意义;每个页面都要单独授权,UX 复杂。
- **X (Twitter)** — 成本是杀手:$0.005/post read,如果一个用户有 5000 条 tweet,单用户 reads = $25。规模化必须做用户级 rate cap。

**死路**:
- **LinkedIn 大规模聚合** — hiQ 案 $500K judgment + 2025 Proxycurl 诉讼 + ToS 显式禁止。我推断:即便用户 OAuth 给我们,LinkedIn 都不会通过 OpenID 之外的 scope。
- **X scraping 或 B 端聚合** — ToS + cost 双重 hostile。
- **任何平台的 B 端 silent resale** — GitHub ToS 显式点名 "recruiters, headhunters, job boards"(V602)。Dribbble 同。Behance/X/LinkedIn 隐含。
- **bulk-crawl 个人站 without 用户提供 URL** — 即便美国 CFAA 不适用,EU GDPR 要 lawful basis,这就是 dead。

### 1.3 对产品形态的最大约束(raw data 直接支持)

1. **我们不能做"一键聚合用户的 LinkedIn"。** LinkedIn 工作经历只能靠用户自己上传 LinkedIn 的 PDF/CSV export(LinkedIn 的"Data Export"是 user-initiated,V611)。
2. **X 数据要么用户自己复制,要么放弃。** OAuth 可以,但成本不允许"读所有 tweets",必须限定最近 N 条或 user-curated。
3. **Substack 只能 RSS** + free posts;深度文章质量分析需要用户主动 export。
4. **B 端不能直接消费 GitHub-derived 数据卖给雇主。** GitHub ToS V602 直接命中。

> **反偏误检查**:hiQ 案确实建立了"public data scraping 不违反 CFAA"的判例(V609),所以 LinkedIn 公开 profile 的 scraping 不是"刑事违法";但 LinkedIn 用 California 州 tort 法(trespass to chattels, misappropriation)+ ToS 违约赢了。我没有 over-claim "完全违法",而是说"商业上 deadly + 法律风险 high"。

---

## 2. 隐私法规

### 2.1 GDPR(EU)

**personal data 范围(Art. 4 GDPR, V629)**:GitHub username、Substack URL、portfolio URL、AI 生成的 career persona、甚至 ETH 钱包地址 —— 全是 personal data,因为都"directly or indirectly identify 自然人"。这意味着我们处理的所有数据 都受 GDPR 管。

**lawful basis(Art. 6, V630)**:
- 最干净的是 **Art. 6(1)(a) Consent** — 用户显式连接平台、勾选授权。要求 freely given, specific, informed, unambiguous + 易撤销(Art. 7(3))。每个数据源必须独立 consent(GitHub ≠ Substack ≠ Twitter)。
- Art. 6(1)(f) Legitimate Interest 理论上可用于 B 端反哺,但必须过 balancing test,而我们的场景(把职业 profile 给雇主)balancing 大概率不利,**我推断这条不能依赖**。

**Art. 22 自动化决策 + SCHUFA(V631, V632)**:
- 原文:"data subject shall have the right not to be subject to a decision based solely on automated processing... which produces legal effects... or similarly significantly affects him or her。"
- CJEU SCHUFA 案(2023-12)扩展了 Art. 22:**即便最终决策由人做,只要 AI 输出 "significantly influence" 下游人类决策,Art. 22 就适用**。
- 直接含义:**C 端"用户看自己的洞察"可以,不触发 Art. 22**;但**一旦 AI 生成的 talent profile / score 被雇主看到并影响"要不要联系这个候选人"的判断,Art. 22 立刻触发** → 必须有人工介入权、解释权、申诉权。
- 我推断:即使我们说"雇主自己决定",只要雇主习惯性按 AI 排序联系候选人,SCHUFA 推理就把我们拉进监管。

**用户权利(Art. 15-22)**:必须建 data export(Art. 15+20)、deletion(Art. 17,30 天)、correction(Art. 16)。这些不是 nice-to-have,是法定。

**真实 fines(V633)**:Meta €1.2B(2023-05,EU-US 传输无 mechanism);TikTok €345M(2023-09,儿童数据);Amazon €746M(2021);WhatsApp €225M(2021);累计 €5.88B+。**上限**:€20M 或全球营收 4%(取大者)。

> **反偏误**:GDPR 不是 deal-breaker,数千家美国 SaaS 在 EU 合规运营。问题是设计成本和"Art. 22 是否触发"。我没把 GDPR 描述成"无法克服",而是说"设计要从 day 1 考虑"。

### 2.2 CCPA / CPRA(加州)

**"sale" 定义极广(§1798.140(ad), V635)**:"selling, renting, releasing, disclosing, disseminating, making available, transferring, or otherwise communicating... to a third party for monetary or other valuable consideration。" 把用户 career profile 给雇主换取付费 = sale,**几乎确定**。

**B2B 豁免 2023-01-01 过期(§1798.145(m)/(n), V636)**:这是关键。曾经"员工数据"和"B2B 联系人数据"是豁免的,2023 后全部纳入。我们处理的是职业数据,**100% 直接适用**。

**Sensitive PI 类别**:**职业数据 NOT 在 sensitive 列表**(V635)— SSN、健康、基因、精确地理位置才是。这意味着我们不触发 "Right to Limit Use of Sensitive PI"(§1798.121),但所有标准权利(know/delete/correct/opt-out)适用。

**AI 推断显式覆盖**:§1798.140(v)(1)(L) **明文**:"inferences drawn... to create a profile about a consumer's professional or employment-related information, preferences, characteristics, psychological trends, predispositions, behavior, attitudes, intelligence, abilities, and aptitudes" 都是 personal information。我们 AI 生成的 career persona **就是** 这条 covered 对象。

**操作义务**:Do Not Sell or Share 链接 / 15 工作日响应 opt-out / 12 个月 lookback 审计 / 不能因用户行权而歧视。

**enforcement**:CAG 可罚 $2,500/violation(无意)或 $7,500(故意);CPPA 自 2023 开始 active enforcement,signaled AI profiling 是重点。

### 2.3 EU AI Act(重点)

**timeline(V637)**:
- 2024-08-01 entered into force
- 2025-02-02 Chapter I + II(禁止类 AI)生效
- 2025-08-02 GPAI 模型条款生效
- **2026-08-02 — Annex III 高风险义务全面 enforceable** ← 我们
- 2027-08-02 嵌入式高风险(医疗、交通等)

**Annex III §4(a) 招聘 AI(V638)**:原文 "AI systems intended to be used for the recruitment or selection of natural persons, in particular to **place targeted job advertisements**, to **analyse and filter job applications**, and to **evaluate candidates**" 是 high-risk。
**§4(b)** 工作关系决策、任务分配、绩效监控也 high-risk。

**我们的产品映射(raw data 直接支持)**:
- C 端用户看自己的洞察 → likely **NOT** high-risk(可能可用 Art. 6(3) 程序性任务 escape:"does not materially influence the outcome of decision-making")
- **B 端 AI-generated profiles 被雇主看到 → HIGH RISK,§4(a) "evaluate candidates" 直接命中**
- Matching users to job opportunities via AI → HIGH RISK
- AI 排序 / 评分给雇主 → HIGH RISK

**高风险义务(Art. 9-17 + 26(7))**:
- Art. 9 风险管理系统(全 lifecycle 文档化)
- Art. 10 数据治理(training/validation/testing set 质量 + bias monitoring)
- Art. 11 技术文档(架构、性能指标、可更新)
- Art. 13 透明度(用户/deployer 必须知道在用 AI、能力、限制、人工监督机制)
- Art. 14 **Human Oversight** — AI 不能独自做最终 evaluation 决策
- Art. 26(7) — 必须告知工人代表和受影响的工人 AI 在用、怎么用、扮演什么角色 → **候选人必须被告知"你被 AI 评估过"才能给雇主**
- 日志保留 **至少 6 个月**
- 在 EU AI Act 数据库 **注册**
- 上市后监控

**罚款(V639)**:
- 违反 prohibited AI(Ch. II):€35M 或 7% 全球营收
- 违反 Annex III 高风险义务:**€15M 或 3% 全球营收**
- 提供误导信息:€7.5M 或 1.5%

**关键判断(我推断)**:
**我们 B 端产品如果维持现有形态("AI-derived 候选人画像直接呈现给雇主用于评估"),2026-08-02 后基本不能在欧盟运营,除非完成 Annex III 全套合规** —— 风险评估 + bias 测试 + 人工监督 + 候选人通知 + 6 个月日志 + EU 数据库注册。这是 6-12 个月的工程 + legal + ops 工作,不是 Q3 hackathon 能做完的。

**调整方向**:
1. **拆分 C/B 风险类别**:C 端坚定走 Art. 6(3) "不实质影响第三方决策" 路线 — 用户看自己,不上 Annex III。
2. **B 端转 "user-controlled push"**:候选人主动决定"我把这份 profile 推给这个雇主";呈现的不是 AI 评分,而是用户自己 curate 的 profile + 可选的 AI-suggested talking points。这样产品形态从"AI 评估候选人给雇主"变成"用户管理自己呈现给雇主的形象"—— **可能(我推断,需法律确认)避开 §4(a)"evaluate candidates" 的核心定义**。
3. **如果要做"AI rank candidates"功能**:接受 high-risk 分类,从 day 1 建合规体系。

> **反偏误**:我没说"EU AI Act 让我们无法运营"。我说的是"现有 B 端 silent matching 形态在 2026-08-02 后基本不可行 — 要么改架构,要么承担 high-risk 合规成本"。这两条都是可执行的产品路径。

### 2.4 数据本地化与跨境(短)

- **GDPR Chapter V**:数据可出 EEA,但需 transfer mechanism。**EU-US Data Privacy Framework(2023-07,V641)** 是当前最简路径(美国公司 DoC 自证)。**风险**:NOYB 已宣布会发起 Schrems III 挑战,2-5 年内可能被废,我们要做好"DPF 倒了就切 SCCs + TIA"的预案。
- **最安全**:EU 数据 residency(AWS eu-west / GCP europe-west / Azure westeurope)直接消除传输问题。
- **中国 PIPL**(V643):目标市场欧美,但若意外有 China 用户,>100,000 触发 CAC 评估;有 HR 管理豁免和合同必要例外。短期不优先。
- **Brazil LGPD**(V644):2025-08-23 grace period 已过,必须 ANPD-approved SCCs。
- **美国其它州**:VCDPA/CPA/CTDPA/UCPA 都有 employment context 豁免(V645)— 加州是唯一例外。**结论**:按加州合规设计,自动覆盖其它州。

---

## 3. B 端反哺商业模式的历史教训

### 3.1 LinkedIn Recruiter — 用户接受的反面参照(V646)

**为什么 LinkedIn 用户能接受被搜索**:
- 透明性:用户**知道**自己被 recruiter 搜索 — 这是 LinkedIn 价值主张的一部分("be found for jobs")。
- 用户 opt-in:profile 字段、"open to opportunities" 信号都是用户主动控制。
- 利益对齐:用户也想要工作机会。

**LinkedIn 模式的疲态(对我们的反向警示)**:
- Recruiter Corporate 2025 → 2026 涨价 ~15%,$10,800-$12,960/seat/yr
- 91% 用户(2026 一项 survey)减少或停用 LinkedIn Recruiter
- 平台对 recruiter 价值下降但价格上升,信任在崩塌

**教训**:**模式能成立靠的是用户感知的 reciprocal benefit + 透明性,不是 ToS 里埋的 consent**。我们如果做 B 端,必须让用户在数据被给雇主的**那一刻**看到、并能取消。

### 3.2 Handshake — 学校强制下的同意,模型对我们不直接通(V647)

**架构**:学生 profile 默认 Private(由学校创建时);学生必须主动 opt-in employer 可见性;ToS **禁止雇主把数据 disclose 给其它第三方** 或用于 data analytics / marketing。

**为什么数据问题不大**:学校强制创建 + 学生显式 opt-in employer visibility + 雇主下游 resale ban。

**模型对我们不通**:我们没有"学校强制"这个 funnel;用户是 self-motivated 来的。但**两个特性可借鉴**:
- **多档可见性**(Community / Employers / Private)
- **employer 下游 ToS resale 禁令**(防止 cascade leakage)

### 3.3 23andMe + GSK $300M + 2025 破产 + 用户数据出售 —— 我们最大的警示(V648, V649)

**Timeline(raw data 直接支持)**:
- 2017-2018:用户 opt-in 同意"research use of anonymized genetic data"。
- 2018:23andMe 与 GSK 签 **$300M** 协议,GSK 拿数据库做药物研发。
- 2023:**6.9M 用户数据 breach**,集体诉讼。
- 2025-03:**Chapter 11 破产**。
- 2025-07:破产法院批准把**1500 万用户**的基因数据打包卖给 **TTAM Research Institute**(创始人 + 前 CEO 的非营利)。
- **28 州 AG 反对**,法院驳回。
- Consumer Privacy Ombudsman 报告:"现有法律不足以保护用户。"

**用户原始同意覆盖的不包括**:
- 破产中数据被卖
- 继承组织对数据的未来决策权
- 转移给毫无关系的第三方

**对我们的教训(关键)**:
> **Consent at account creation ≠ consent for what happens 5 年后。** 即便最初是 "opt-in research",business model 变化 / 公司易主 / 破产时,数据会被当成 asset 出售,即便法律允许,舆论也会爆炸。

**产品架构含义**:
1. **不要让"用户数据"成为一个可以脱离用户关系单独卖掉的 data asset**。考虑 user-keyed encryption — 没有用户的 key,买家拿到也没用。
2. **明确写"我们倒闭怎么办"** 的用户协议:"In the event of bankruptcy or acquisition, your data will be deleted, not transferred."(这条本身需要 corp structure 配合 — 比如把数据销毁义务写进 articles of incorporation)。
3. **每次实际数据使用都重新触发 micro-consent**,而不是依赖 onboarding 时的 blanket consent。

### 3.4 早期 Facebook 广告 — opacity 的反例(V651)

**模式**:用户"自愿"分享 + 广告主付费定向 + 用户"免费"用。

**问题**:targeting 系统可推断 sensitive 类别(政治、性取向、宗教、健康)— 用户从未显式提供。Cambridge Analytica(2018)显示第三方 app 不仅采集授权用户,还采集其朋友 — 朋友毫不知情。

**Solove 的 "aggregation problem"**:**单独无害的数据点(姓名 + 雇主 + GitHub + 写作主题 + portfolio)组合起来,是比任何单一数据点更具侵入性的 profile**。用户对每个零散同意,可能对组合的 profile 不舒服 — 尤其当组合 profile 被给第三方(雇主)而 用户实时不知道。

**对我们的含义**:
- 必须让用户在 profile 被给雇主前**看到完整组合**。
- 不要从行为数据推断 sensitive 属性(宗教、健康、政治、性取向),即便技术上可以。
- 设计 user agency:"This is what employers see. Edit or hide any section."

### 3.5 综合:用户数据"卖给雇主"的红线(我推断 + raw data 综合)

**红线 1:任何对雇主的数据呈现,用户必须能直接看见。** 不是 ToS 里埋的,是 UI 里显式的"This is what [Company X] is about to see"。
**红线 2:在数据实际流向雇主的那一刻,而不是 onboarding 时,触发用户同意。** 23andMe 教训。
**红线 3:雇主对我们提供的数据有合同性的"no downstream resale" 约束。** Handshake 模式。
**红线 4:数据不能成为可单独出售的 asset。** 用户持密钥 / 死亡开关 / 公司章程级的销毁承诺。
**红线 5:不从行为数据推断敏感属性。** 即便能。
**红线 6:Reverse auction visibility** — 用户能看见"有哪些雇主在 view / 拒绝 / 联系我的 profile",对称信息流。

---

## 4. AI 个人洞察的真实能力 + 设计模式

### 4.1 Wrapped 范式的工程化(V652-V658)

**Spotify Wrapped 关键设计原则**:
- **anchor 到具体数字**:"You listened to [Artist] 847 times" — 可证伪,可对照。
- **创建 hierarchy**:#1 song, #1 artist, top genre — 排名让事情个人化。
- **time-bound narrative**:年度结构 = 自然 story arc。
- **shareable card**:9:16 Instagram Stories 优化。
- **emotional resonance over information density**:少说,每条都重。

**2024 新点**:Spotify Wrapped 用 Google NotebookLM 生成**个人化 AI podcast** — 第一次大规模消费级 generative AI narrative。

**GitHub-style Wrapped(V654)**:
- streak 机制(longest streak X days)
- 语言饼图(自我认知 vs 数据)
- top project highlight + 外部验证(stars)
- year-over-year growth framing

**Strava 教训(V655)**:
- 不只是 totals,要找 **peak moments**("Your best climb was X on [date]")
- **vivid metaphor**:"You climbed the equivalent of 14 Mount Everests" — 把抽象数字翻译到人类尺度
- **peer comparative**:"top 15% of cyclists for elevation gain"

**Reddit Recap 失败教训(V656)**:平台无关的标签("curious explorer")空洞;**平台特定**("67% 时间在 r/[specificNiche]")真实。

### 4.2 Barnum 效应 —— 我们的头号失败模式(V658, V659)

**Barnum 句**:"You have a great need for other people to like and admire you。"(几乎对所有人成立,但感觉个人化。)

**LLM 让它更糟**:LLM 训练成 agreeable + affirming,默认产 Barnum:
- "You're a creative problem-solver who thrives in ambiguous environments"
- "Your diverse skill set makes you adaptable"
- "You have strong communication skills"

—— 这些对任何专业人士都成立。

**"Sophisticated Barnum"(2024-2025 文献)**:"AI projects specificity which you accept as validation... AI fills in blanks with plausible-sounding specifics that happen to agree with you."

### 4.3 避免 Barnum 的强制设计要求

| 不可证伪(Barnum) | 可证伪(我们要做的) |
|---|---|
| "You're a creative thinker" | "You started 7 experimental repos in categories you hadn't worked in before" |
| "Passionate about tech" | "847 days straight contributing to open source" |
| "You communicate clearly" | "Substack posts average 1,847 words, Grade 10 Flesch-Kincaid" |
| "Continuous learner" | "In 2024 you added TypeScript and Rust after 4 years of pure Python" |
| "Strong professional presence" | "Your 3 most-engaged Substack posts were all about [topic]" |

**强制清单**:
1. 每条 AI 洞察必须 cite 一个具体数据点。
2. 每条 claim 必须可被用户核对(可证伪)。
3. 必须包含 **surprising findings** — 如果 AI 只 confirm 用户已知,无价值。
4. 提供 escape hatch:"Does this match your self-perception? [Yes / Partially / Not really]"。
5. 区分 fact vs inference 的 UI 标签。
6. **不**推断 sensitive 类别(personality disorder、心理健康、性取向、政治信仰)。

### 4.4 Apple 不做 Wrapped 的含义(V657)

Apple 在 Music/Fitness/Health/Maps 有海量行为数据,**不做** Wrapped,因为分析行为数据"feels invasive even if technically consented"。**这是真实的市场细分**:存在一群隐私敏感、技术 savvy 用户,会对 on-device 处理、不上服务器的 Wrapped-style 产品有强烈正向反应。

**对我们的差异化机会**:"AI insights generated on-device, never sent to our servers, you choose what to share" 是一条 viable positioning,虽然工程复杂(LLM 多大?能跑在端上吗?2026 看到 MLX / Gemini Nano / Apple Intelligence 让 7-12B 模型在 端上 可行)。

---

## 5. 对我们产品的启示

### 5.1 用产品语言重述约束

**约束 1 → 产品形态:user-initiated pull,而非 silent aggregate**
- **依据**:LinkedIn 实际关闭(V608-V611)+ GDPR Art. 6 consent 要求 specific/granular(V630)+ 23andMe 教训(V649)。
- **决策**:聚合必须是 **user-initiated OAuth** + 每个平台独立 consent + 用户能看到 / 编辑 / 删除 AI 推断结果。**不能**做后台 silent scraping 或预填。
- **可做**:GitHub OAuth、Dribbble OAuth、Substack RSS(用户提供 URL)、Notion 逐页授权。
- **不可做**:silent LinkedIn scrape、X bulk read without user-level cap、个人站 bulk crawl。

**约束 2 → B 端转 "user-controlled push" 而非 "platform-mediated match"**
- **依据**:EU AI Act Annex III §4(a)(V638)2026-08-02 + GDPR Art. 22 + SCHUFA(V631-V632)+ CCPA "sale" 定义(V635)+ 23andMe 教训。
- **决策**:**B 端反哺路径不能是"我们后台 rank 候选人,把 top N 给雇主"**;必须是"用户主动 curate 一份 profile + 主动选择推给特定雇主"。这把 Annex III §4(a)"evaluate candidates" 的核心动作还给用户。
- **具体实现**:雇主侧看到的是用户已经 curate 过的 profile,不是 AI 排名;AI 在 C 端帮用户优化、给 talking points;AI 不在 B 端给 score。
- **如果实在要做"AI rank for employers"**:那从 day 1 就建 Annex III 合规栈(预算 6-12 个月 + 律师 + bias auditor)。

**约束 3 → 数据架构必须防止 "data asset" 积累**
- **依据**:23andMe 破产数据出售(V649)+ 28 州 AG 反对失败 → 现有法律不够。
- **决策**:**用户数据加密用 user-derived key**(passkey / 用户密码 derived);我们持有的是 ciphertext + AI 推断结果。卖出去也不可读。
- **附带承诺**:写"破产/收购时数据销毁"到 corp structure + 用户协议。这是 Patagonia-style 的硬承诺,**会成为营销资产** —— 因为没人这么做,所以做了就有差异化。

**约束 4 → AI 洞察必须 falsifiable + escape hatch**
- **依据**:Barnum 效应(V658)+ Sophisticated Barnum 文献 + Reddit Recap 失败教训(V656)+ GDPR Art. 22(V631)需要"right to contest"。
- **决策**:每条 AI 推断必须 cite 数据点 + 用户能 "this doesn't feel right" + AI 在用户拒绝时不能 silently overrule。这同时满足 anti-Barnum(产品质量)和 Art. 22 safeguard(合规)。

**约束 5 → 透明度作为产品功能,不是 footer 链接**
- **依据**:Facebook Cambridge Analytica 教训(V651)+ GDPR Art. 13 transparency + EU AI Act Art. 26(7) 工人通知 + CCPA "Do Not Sell" 显式要求。
- **决策**:UI 主路径展示 "this is what employer [X] sees" preview、"who has viewed my profile" log、"opt out of all employer visibility" toggle。透明度 = product feature,放在主导航。

### 5.2 路线建议(我推断,基于 raw data)

**Phase A(MVP,2026 Q2-Q3)**:C 端 personal insights only。
- GitHub + Substack RSS + 用户提供个人站 URL + (optional) Dribbble OAuth
- LinkedIn 仅作 sign-in
- AI 洞察展示给用户自己,不可见于第三方
- 对 EU 用户:hosted in eu-west 或 DPF + SCCs 双保险
- **触发的合规义务**:GDPR 全套 + CCPA 全套 + EU AI Act **NOT** high-risk(Art. 6(3) escape)
- 风险:LOW-MEDIUM,完全可执行

**Phase B(2026 Q4 起)**:user-controlled push 反哺。
- 用户主动决定"把我的 profile 推送给 [Company X] 这个具体 opportunity"
- 雇主看到的是用户 curate + 我们 facilitate 的 profile,不是 AI ranked 列表
- 雇主对接 ToS:no downstream resale、no further inference、24-hour deletion on request
- 用户实时看到 "viewed by / contacted by" log,可以撤销 visibility
- **触发**:CCPA "sale" → 需要 Do Not Sell 链接;但若设计成 "user-requested service" 可能避开。AI Act:**possibly avoid §4(a)** 因为雇主不是看 AI score,但需 legal review。

**Phase C(2027+,如果要做 employer-side AI ranking)**:Annex III 全套合规。

### 5.3 不能做清单

- ❌ 一键聚合 LinkedIn 工作经历
- ❌ silent scraping 任何平台
- ❌ X bulk read without user-level cost cap
- ❌ 把 GitHub-derived profiles 卖给 recruiters / job boards(GitHub ToS V602)
- ❌ Dribbble-based designer search 给雇主(Dribbble ToS)
- ❌ 推断 sensitive 类别(种族、宗教、性取向、政治、健康)
- ❌ "AI scores candidates for employers" 在 EU 不做合规栈就开
- ❌ Onboarding 时 blanket consent 试图覆盖未来所有用途
- ❌ 数据架构允许"我们倒闭/被收购后 data 可单独卖"

---

## 6. 调研局限性

1. **法规执法实践仍在演化**:GDPR Art. 22 SCHUFA(2023-12)之后,CJEU 仍在产生新判例;EU AI Act 2026-08-02 之后头 12 个月 enforcement 会怎么落地、how strict the "materially influence" 测试,raw data 截至 2026-05-26 还看不到实战。
2. **X API 政策变化频繁**:2023 以来已大改三次,raw data 取自 2026-05-26 文档,6-12 个月信息半衰期。每 quarter 须重检。
3. **ToS 文本不总能直接获得**:Behance、Medium 的 ToS 细节是律师 / 开发者社区拼出来的;有些条款可能已变。
4. **法律意见非法律建议**:本报告基于公开文档分析,在正式投资 / 设计 / 上线前,必须做正式 legal review(尤其 EU AI Act 风险分类、CCPA "sale" 边界、user-keyed encryption 的破产法效力)。
5. **样本偏向英文 / 美国 / 欧盟**:对 LATAM、东南亚、印度等市场的法规(LGPD 已覆盖,但巴西之外的拉美没覆盖;印度 DPDP Act 2023 没覆盖)研究有限。
6. **Bright Data / hiQ 判例的射程**:这些判例都是 Ninth Circuit 或 N.D. Cal,不一定 binding 别的 circuit。我们如果在 New York / Texas 被诉,法律风险曲线不同。
7. **B 端反哺案例都是大平台**:LinkedIn / Handshake / 23andMe / Facebook 都是 unicorn 级公司,小公司的 baseline 监管关注度可能不同(可能更宽松,但也可能因为没资源应对而更脆弱)。
8. **AI 洞察的"用户体验测试"在 raw data 中缺失**:Wrapped 设计原则是从公开报道反推的,没有 A/B 数据;我们的"falsifiable + escape hatch" hypothesis 在自己产品上需要实测。

---

*Citations: V600-V662(完整 raw_data/phase_07 范围)*
