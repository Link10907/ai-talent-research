# Phase 3 — Legal Industry AI Adoption Report

**Scope:** US-led, with international BigLaw signal where relevant. "Legal" includes
law-firm lawyers (BigLaw → solo), in-house counsel, paralegals, legal operations, and
the emerging legal-tech/legal-engineer hybrid roles. Date: 2026-05-25.

---

## A. AI 渗透成熟度

### A.1 头条结论:**6.5 / 10**(置信度:高)

整体均值落在 6-7 之间,但这是一个被严重压缩的统计量——同一行业内的成熟度方差比
大多数行业都要大。准确的描述应该是:

| 子群体 | 渗透度(0-10) | 描述 |
|--------|--------------|------|
| BigLaw(Am Law 100/200) | **8.0** | 已过拐点,进入"deploy"阶段 |
| 中型律所(20-100 lawyers) | **6.0** | 工具采购完成,工作流改造中 |
| 小型律所(<20)+ solo | **5.0** | 使用 ChatGPT,但未机构化 |
| In-house / GC | **7.0** | 经济利益最直接,无内部摩擦 |
| 法务运营 / Legal Ops | **7.5** | 推动 AI 的"内部产品经理" |
| Paralegal | **6.5** | 工作内容被改造最深 |

### A.2 整体数据(个人使用 ≠ 机构部署 — 巨大鸿沟)

- **个人侧:** 69% 法律专业人士现在用 GenAI 工作(从前一年 31% 翻倍以上);28% 每天用,
  31% 每周用几次 [P3LEG-001]。另有数据将整体使用率拉到 79% [P3LEG-002]。
- **机构侧:** 只有 46% 律所部署了通用 AI 工具;只有 34% 部署了 legal-specific 工具
  [P3LEG-001]。仅 15% 的律所说 AI 是工作流"central"组成部分 [P3LEG-002]。
- **政策真空:** 53% 律师说所在律所没有 AI 政策或他们不知道 [P3LEG-002]。

这是本行业最重要的一个事实:**律师在偷偷用 AI,律所在公开装作还没用。**
个人采用速度已远超机构治理速度,差距还在扩大。

### A.3 按律所规模分层

- 大型律所(51+ lawyers):87% AI 使用率;39% 部署了 GenAI [P3LEG-002, P3LEG-010]
- 小型/Solo:71% 使用率,但 53% 的小型律所 AI 使用率(从 27% 翻倍);
  **仅 4% 把 AI "广泛或全面"部署** [P3LEG-002, P3LEG-010]
- 小所主流工具:ChatGPT (66%) / Microsoft Copilot (42%) / Gemini (24%) — **几乎全是
  消费级,无 legal-specific 适配** [P3LEG-010]

### A.4 In-house 阵营更猛

52% 美国 in-house counsel 在 2025 年开始用 GenAI,YoY 翻倍 [P3LEG-012]。
in-house 的经济激励是单向的(降低外部律师费),没有 billable hour 的内部敌对力量,
所以采纳速度系统性快于律所。**中位数法务部省下 $252K/年 的外部律师支出**(占
$1.8M 外部支出的 14%)[P3LEG-012]。

### A.5 广泛采用的工具/工作流

**Enterprise / BigLaw 工具:**
- **Harvey** — 1,000+ 客户,60 国,Am Law 100 中 50% 已签;CMS 国际所把 Harvey 推
  到 50+ 国家、7,000+ 律师 [P3LEG-003]。在 Vals 2025 基准上文档 Q&A 拿 94.8% [P3LEG-011]。
  价格 $50K-$100K+/年,事实上是 BigLaw 专属 [P3LEG-011]。
- **CoCounsel(Thomson Reuters)** — 跟 Westlaw 同生态;Casetext 已于 2025-04-01
  作为独立产品下线,功能并入 CoCounsel [P3LEG-011]。
- **Spellbook** — Series B $50M(Khosla 领投),3,800-4,000 律所/80 国;
  嵌入 Word 做合同 [P3LEG-018]。
- **Eve** — $103M Series B,$1B+ 估值;首个 plaintiff-side 法律 AI 独角兽,
  450+ 律所,年处理 200K+ 案件 [P3LEG-019]。
- **Ironclad / Evisort** — 企业级 CLM,集成 Salesforce/Workday/DocuSign。

**通用工具(主导小所和个人):** ChatGPT、Copilot、Gemini、Claude。

**核心工作流:** drafting correspondence (58%)、legal research (58%)、
document summarization (47%)、document drafting (43-49%)[P3LEG-001]。
合同审查、e-discovery、CLM 是企业法务三大引擎。

### A.6 子岗位 AI 渗透最深的是谁?

按 8am Report,各律所内部 AI 培训目标人群优先级:
1. **Paralegal — 39%(第一名)** [P3LEG-001]
2. Partner — 30%
3. Associate — 26%

这与 BigLaw 的训练倒挂(给 first-year associate 大量 AI 时间——Ropes & Gray 把 400/1,900
billable hours 划给 AI 实验;Latham 强制 400 个 first-year 上 2 天 AI Academy)
[P3LEG-004]并不矛盾——paralegal 是工作内容被改造最彻底的群体,而 first-year
是被战略性培训成"AI-native lawyer"的群体。

**真正"靠 AI 吃饭"最深的:** Legal Operations 专员、合同律师/transactional lawyer、
e-discovery 专员、in-house counsel。**最浅的:** 庭审律师(litigators)、关系驱动的
合伙人、家庭法律师。

### A.7 拐点是否已到?**已到,但不均匀**(置信度:高)

支持已过拐点:
- ILTACON 2025 (4,500 出席者) 主题已从"探索 AI 可能性"转向"分享部署实践" [P3LEG-023]
- Axios:律所在削减 summer associate 项目,理由是初级岗位工作被自动化 [P3LEG-005]
- Clifford Chance 因 AI 采纳裁减伦敦岗位 [P3LEG-005]
- 单一年 BigLaw 内 GenAI 个人使用率从 31% 翻倍到 69% [P3LEG-001]

但要小心说"整个行业过了拐点":
- 53% 律所还没有 AI 政策 [P3LEG-002]
- 600+ 件 AI hallucination 制裁案件,且增速从 2/周升到 2-3/天(2025春)[P3LEG-007]
- 小所 86% 仍未因 AI 调整定价 [P3LEG-026]

**我的判断:** BigLaw 和 in-house 已过拐点;mid-market 在拐点上;solo/small 还
落后 12-18 个月。整体均值已经"过了第一道闸",但还没到"AI 是默认状态"。

---

## B. "AI 能力"在该行业的具体定义

### B.1 "AI 能力"在法律行业指什么(置信度:中-高)

不像营销/设计/工程,法律行业没有形成一个被广泛接受的"AI 能力"定义。我从证据中
推断出四个层级,以及目前的实际重心:

**层 1:工具使用(基础门槛)**
熟练使用 Harvey / CoCounsel / Spellbook / Westlaw AI / Lexis+ AI / Microsoft
Copilot,以及在 Word 里嵌入式审查合同。简历里现在出现"Tech Skills"区列出工具名
是 LawJobs.com 明确推荐的做法 [P3LEG-013]。

**层 2:Prompt 工程 + 工作流设计(差异化技能)**
- Vanderbilt 大学和 Coursera 联办 "Prompt Engineering for Law" specialization,
  签发可分享证书 [P3LEG-017]
- Clio Legal AI Fundamentals Certification(免费)
- AltaClaro、Axiom CLE、Udemy CPE-LC 都提供 prompt engineering 培训
- 在 Stanford Law,critical AI training 已嵌入 1L 课程 [背景资料]

**层 3:AI Governance(高薪垂直)**
理解 EU AI Act、各州 AI 立法、客户数据合规、模型偏见识别——这是目前**最显性、最
高薪**的"AI 能力"应用方向。AI Governance 是 privacy 相邻领域 YoY 薪资增长最高的
专业 [P3LEG-015]。

**层 4:Legal Engineer / Legal Technologist(混合身份)**
真正的复合岗位——会 JD + 工作流自动化 + legal tech 选型 + 流程改造。ABA 称这是
"fast-growing career path";招聘来源既包括转型律师,也包括 paralegal、legal ops、
PM——**不要求 JD**[P3LEG-027]。

### B.2 招聘方如何评估这种能力(置信度:中)

目前法律行业的 AI 能力评估**几乎完全没有标准化**。证据显示的方法:

1. **简历自报**(主流但弱):列工具名 + 量化指标(节省时间、效率%)[P3LEG-013]
2. **证书**(刚开始有):Vanderbilt prompt engineering certificate、Clio Legal AI
   Fundamentals、IAPP AIGP(AI Governance Professional)。但**目前没有任何一个证书
   是律所招聘的硬要求**——置信度:中。
3. **写作和演讲履历**(实际最有效):在 LinkedIn 写 AI 应用文章、ILTACON/Legalweek
   演讲、CLE 授课——这些被 LawJobs.com 明确点名 [P3LEG-013]
4. **内部声誉**:在律所内部"主持 AI 培训 session"、"写内部 prompt 库"被作为
   builds visibility 的路径 [P3LEG-013]
5. **结构化面试**(罕见但开始出现):BigLaw summer associate 项目现在包括强制 AI
   培训环节 [P3LEG-029],客观上变成评估窗口

### B.3 显性 AI 要求 JD 长什么样(置信度:高)

**强显性(完全围绕 AI 的岗位)**

1. **AI Legal Counsel** — 中位 $139,438,范围 $84K-$197K [P3LEG-014]。
   职责:起草 AI 合同、对接 EU AI Act、IP/data 隐私、内部培训。
2. **AI Governance Counsel / Senior Manager** — 中位 $158,750;senior $273K+
   [P3LEG-015]。**Latham & Watkins 公开发布了 "Senior Manager of AI Governance"
   JD**,职能是"translating regulation, risk, and policy into operational
   controls"[P3LEG-016]。
3. **Legal Operations Specialist** — 增长最快的岗位之一,直接职责是"帮团队采纳
   AI、自动化工作流、优化流程"[P3LEG-024]。

**半显性(把 AI proficiency 列为偏好/要求)**
传统 associate JD 越来越多写"experience with legal AI tools preferred"——这是
National Law Review 描述的"baseline expectation"转变 [P3LEG-024]。但**hard
mandate 仍是稀有的**;主流路径是培养而非筛选。

**隐性(实际门槛比 JD 写的高)**
BigLaw summer 项目嵌入 AI 培训——你做不来就拿不到 return offer [P3LEG-029]。
"Students with AI skills are becoming the more attractive candidates" [P3LEG-005]。

**重要矫正:** 一年前我会说 AI 能力在法律行业是"加分项";2025-2026 数据显示它
正在从加分项变成 baseline。但**距离"硬性 must-have"还差一步**——主要是法律行业的
保守惯性 + ABA 监管框架尚在演化(置信度:中-高)。

---

## C. 用户行为

### C.1 律师如何展示 AI 能力(置信度:中-高)

**主战场:LinkedIn**
87% 美国律师在 LinkedIn 上 [P3LEG-022]。展示方式:
- Featured section 钉文章/演讲(LinkedIn 的"伪 portfolio")
- 发表 AI 主题 long-form posts/Pulse 文章
- Headline 写 "Attorney | AI & Legal Tech" 类标签
- 简历 Tech Skills 区列工具 [P3LEG-013]

**次战场:** 行业演讲(ILTACON、Legalweek、ACC)、CLE 授课、行业播客
(LawNext / Bob Ambrogi)、专栏(Above the Law、Artificial Lawyer、Law.com)。

**第三梯队:** Substack——AI In Law (Mitch Jackson)、Legal AI (Dean Taylor)、
Common Lawyer、AI For Lawyers、Artificial Lawyer 等——但订阅规模都不大(估计
都在数千 - 数万级),**不是这个行业的主流职业身份建构平台**。

### C.2 是否有行业专属展示平台?**没有。**(置信度:高)

证据:多次搜索"lawyer AI portfolio platform"、"legal tech showcase"未发现任何
具规模的、专门服务法律行业的能力/作品展示平台。**法律行业的职业身份建构默认就是
LinkedIn + 个人/律所主页 + Martindale-Hubbell + Avvo + Super Lawyers 评级**——
这些都是"履历/评级导向"而非"作品/能力导向"。

附属平台(都不是 AI-skill 主题):
- Justia / FindLaw — 律师目录
- LawCrossing / LawJobs.com — 招聘
- Lawline / Practising Law Institute — CLE
- LinkedIn 是事实上的唯一职业身份平台

### C.3 律师群体的痛点

**痛点 1:用 AI 但不敢说用**(置信度:中-高)
hallucination 制裁的扩散让律师在公开声称 AI 能力时格外谨慎。Mostafavi 案、
Johnson v. Dunn 案、MyPillow/Lindell 案在行业内被反复警示 [P3LEG-007, P3LEG-008]。
ABA Formal Opinion 512 又明文规定不能把"学新 AI 工具的时间"billed 给客户
[P3LEG-006]。**结果是律师私下狂用 AI,但简历/对外宣传不知道怎么把它"翻译"成可
信号、合规的能力陈述。** ← 这是本项目最相关的痛点。

**痛点 2:小所的"用得多 ≠ 赚得多"** (置信度:高)
86% solo 和 78% 小所没因 AI 改定价 [P3LEG-026]。<33% 小所 AI 增加了收入,vs
~60% 企业级 [P3LEG-026]。**他们手里有 AI 技能,但没有可信号化的渠道让客户/雇主
为此付溢价。**

**痛点 3:JD ≠ 法律科技能力,被边缘化**(置信度:中)
Legal engineer / legal ops 岗位越来越多由非 JD 背景的人填充 [P3LEG-027]。传统
律师如果想转 in-house tech、转 legal ops、转 legal tech 创业,**没有现成的方式
证明自己的 AI 实践能力**。LinkedIn headline 改成 "AI-savvy lawyer" 没用。

**痛点 4:billable hour 与 AI 效率的内在冲突**(置信度:高)
74% 计时计费的任务可被 AI 自动化 [P3LEG-009]。59% 律所已开始使用 flat fee
[P3LEG-009]。律师个人面临两难:**用 AI 提升效率会减少自己的 billable hours,
反而损害自己的考核**。Bloomberg Law 提供了反方观点:"AI Boosts Legal Productivity
Without Toppling Billable Hours" [P3LEG-030]——即"使用 AI 后多接活而不是少计时"
是另一种可能。这种结构性矛盾让"展示 AI 能力"在律所内部反而是政治敏感的。

**痛点 5:no policy + 高敏感性 = 个人自学**(置信度:高)
53% 没有公司 AI 政策 [P3LEG-002]。律师在用 ChatGPT 处理客户信息这件事上有
重大合规风险(consumer ChatGPT 不在 enterprise DPA 范围内),但他们继续用,
因为没有更好的替代。这种"灰色地带"让他们对外讲述自己 AI 能力时更谨慎。

### C.4 律师群体的内容偏好/聚集地

- **LinkedIn:** 87% 渗透,职业身份默认平台 [P3LEG-022]
- **行业 newsletter:** Artificial Lawyer、LawSites(Bob Ambrogi)、LawNext 播客、
  Bloomberg Law、Law.com / Above the Law 是主要信息源
- **Twitter/X:** 比工程师/营销小很多,但有头部——Bob Ambrogi、David Lat、
  Jessica Mederson
- **Reddit:** r/Lawyertalk、r/LawFirm 活跃度中等(WebSearch 未返回精确数据,
  置信度低);r/LegalTech 较小
- **会议:** ILTACON 4,500 attendees [P3LEG-023]、Legalweek、ACC、CLOC

---

## D. 作为切入点评估

### D.1 用户可触达性:7/10(置信度:高)

**好的方面:**
- LinkedIn 高度集中(87%)—— 单一渠道触达 [P3LEG-022]
- 头部 KOL 可识别(Bob Ambrogi, David Lat, Jessica Mederson)
- 行业会议清晰(ILTACON, Legalweek, ACC)
- 律所合伙人、in-house counsel 都比较"愿意被发现"——本来就有名片/客户开发文化

**不利的方面:**
- 律师对未经验证的新工具天生疑虑,且有 ethics 顾虑(client confidentiality)
- 大律所采购周期长,但我们的 C-side 不是直接卖给律所,这点风险被部分对冲
- 没有像 GitHub/Dribbble/Strava 那样的现成行业"作品社区"可以渗透
- 美国之外的法律体系不同,产品要本地化难度高

### D.2 用户付费/分享意愿(置信度:中)

**付费意愿:中-高**
- 律师收入中位数高(USD $140K+ 全行业;BigLaw $200K-$400K+);1.37M 美国律师 [P3LEG-021]
- 但律师自掏腰包买软件的习惯弱——主要由律所/in-house 买单
- 个人订阅 LinkedIn Premium、CLE 课程、Bar Association 会员的存在表明个人确实
  会为"职业身份"付费

**分享意愿:中-低**(这是法律行业相对其他行业的弱项)
- ethics、confidentiality、reputational risk 三重压力让律师对"分享工作"特别保守
- 律师不能像设计师一样分享作品(client work 是 privileged);不能像营销人一样
  晒 case study(客户数据);也不能像工程师一样开 GitHub
- **能分享的是抽象化的"我用 AI 改造了什么工作流"——而这正好是产品价值主张**
- 但任何让律师"持续主动 update"的产品都会面临阻力——本能就是 minimal disclosure

### D.3 市场规模:8/10(置信度:高)

- 美国法律服务市场 $408-426B/年 [P3LEG-021]
- 美国律师 1.37M;律所 463,590 [P3LEG-021]
- 加上 367,220 paralegals [P3LEG-020] + legal ops + 法学院学生 ≈ **2M+ 美国
  法律专业人士**
- 加上英国/加拿大/澳洲普通法系国家,**英语圈 TAM ≈ 3-4M**
- 收入水平高 → LTV 高
- 但需要警告:这个市场里 **大部分人不分享作品** 是结构性的,所以 TAM ≠ 可激活用户

### D.4 推荐切入优先级:**6 / 10**(置信度:中-高)

**理由(支持):**
1. **AI 渗透已过拐点**,但 BigLaw 之外缺乏可信号化能力的渠道——产品有空间 [P3LEG-001, P3LEG-005]
2. **痛点 1(用 AI 但不敢说)是真痛点**,且当前没有产品在解决它
3. **AI Governance / Legal Tech / Legal Engineer 三个新岗位**正在成型,需要新的
   能力陈述方式 [P3LEG-015, P3LEG-016, P3LEG-027]
4. 用户单价高、可持续付费、行业头部影响力强
5. **paralegal + 小所律师** 是大量被自动化威胁但没有渠道转型的群体(367K + 数百K)
   [P3LEG-020]

**理由(反对):**
1. **结构性的"少分享"文化**——这是产品冷启动的硬伤。法律行业把保密、低调、
   含糊作为职业美德,与"持续分享能力证据"的产品逻辑对立。
2. **没有作品**——律师的产出本质上是 privileged client work,不像设计师/工程师
   有可示众的产出。产品要发明"抽象化的能力证据"格式。
3. **ABA + 各州 Bar 监管**给"向外界宣称专长"加了很多限制(advertising rules,
   specialization claims)。任何"专长展示"产品都要小心 unauthorized practice
   或 false advertising 边界。
4. **BigLaw 内部政治**:律所合伙人本能反对让律师建立"个人品牌",怕被挖角。这是
   LinkedIn 在律所内部一直被矛盾接受的根本原因。
5. **风险厌恶 + 慢节奏**:律师对新平台的采纳速度系统性慢于其他白领。
6. **替代品丰富**:LinkedIn、Martindale、Avvo 已经占据"律师身份"心智。

**净判断:** 法律是一个"市场规模大、痛点真实、但产品-市场匹配难度也高"的行业。
作为 10 个行业里的切入点排序,我估计它会在 **中游(4-6 名)**,不是首选。
首选可能是 marketing / design / sales 这类天生有可分享作品的行业,法律更适合作为
扩张目标而非破冰目标。

**推荐进入策略(if chosen):**
- 不要从 BigLaw partner 切入(政治敏感,LinkedIn 老用户)
- 切口应该是 **"想转型的 paralegal / 想跳 in-house / 想转 legal ops 的 mid-career
  律师"** —— 这部分人有强烈的"重新定义自己"动机,且较少被现有 LinkedIn 网络
  锁定
- 内容形式不应该是"work portfolio",而应该是"AI workflow proof"——用 AI 重新
  构建过的工作流程的抽象描述,可以脱敏到符合 ethics 要求
- 与 Vanderbilt prompt engineering certificate、Clio Legal AI Fundamentals 等
  外部凭证联动 [P3LEG-017]

---

## 跨行业对比关键观察(给 overview 汇总用)

1. **个人 vs 机构鸿沟**:法律是 10 个行业里这个鸿沟最大的之一。69% 个人 vs 34%
   机构 [P3LEG-001]。
2. **作品稀缺性**:法律行业的 privileged work 结构使得"作品/能力证据"必须重新
   发明,不能照搬设计/工程范式。
3. **monetization 困境**:律师用 AI 不等于赚钱——86% solo 没改定价 [P3LEG-026]。
4. **训练投入巨大**:Ropes & Gray 拿出 20% billable time 投入 AI 训练 [P3LEG-004]
   ——这是 BigLaw 对 AI proficiency 重要性的最强信号。
5. **法律是"AI 能力 → 高薪"最显性的行业之一**:AI Legal Counsel 中位 $139K,
   AI Governance 中位 $158K [P3LEG-014, P3LEG-015]。这创造了切入点。

---

## 调研局限性

1. **西方/美国中心严重**:大部分数据来自 ABA、Clio、Above the Law、Axios 等
   美国来源。对中国/欧洲/亚洲法律市场的 AI 渗透知之甚少。Harvey CMS 国际部署
   是少数国际数据点 [P3LEG-003]。
2. **未达到的一手数据源**:多次 WebFetch 被 Above the Law、ABA、LawJobs.com、
   ZipRecruiter 等返回 403;WebSearch 摘要替代了详细抓取,可能错过细节。
3. **Reddit 数据缺失**:r/Lawyertalk、r/LawFirm 的 WebSearch 未返回结果,因此
   无法量化匿名律师对 AI 的真实日常态度。对"律师私下怎么说 AI"的样本不足。
4. **JD 抽样未做**:我没有真正抓 Indeed/LinkedIn 上的 100 个 legal AI JD 做
   定量分析——这是本报告最大的方法论遗憾。结论 B 部分(JD 长什么样)更多依赖
   trade publication 的转述。
5. **2025 vs 2026 数据混用**:有的数据点来自 2025-12 之前的报告(ABA、Clio Legal
   Trends 2024-2025),有的来自 2026-Q1 调研(8am Report、ACC CLO Survey 2026)。
   AI 领域 6 个月差距很大,但混在一起报告了。
6. **大律所偏差**:Harvey / Latham / Ropes & Gray 等 BigLaw 故事被高度报道;
   小所/单人律师在媒体上声音弱,我可能高估了行业整体的渗透速度。Clio Solo &
   Small Firm Report 是少数校正点 [P3LEG-010, P3LEG-026]。
7. **In-house counsel 数据不足**:in-house 是个增长最快的子市场,但行业媒体对
   in-house 的报道密度低于律所——我可能低估了它的重要性。
8. **付费/分享意愿是推断,非验证**:D 节 的付费/分享意愿评估基于行业结构特征
   推断,没有用户访谈数据支撑——置信度:中。**未来需要做的事:**采访 5-10 个
   在不同子岗位、不同律所规模的法律专业人士,验证"用 AI 但不敢说"假设。
9. **billable hour 经济学的双方观点都呈现了,但孰强孰弱我没下定论**——这是
   合理的(行业内本身没共识),但读者应该理解这点。
10. **Eve 和 plaintiff 律所、刑事律师、家庭法律师**等子领域我覆盖不足。本报告
    最聚焦的是 transactional / corporate / BigLaw 视角,litigation / consumer
    law / criminal defense 的 AI 故事不一样。
