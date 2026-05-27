# V2 全面调研执行计划

**日期**:2026-05-27  
**目的**:从真实用户痛点、竞品、B 端数据价值、合规、MVP 实验五个维度继续推进全面调研,避免把“能力镜子”当成未经验证的想象需求。

---

## 0. 总目标

验证一个核心问题:

> 是否存在一个真实 To C 的职业资产管理产品,能够给用户明确利好,从而让用户自愿、持续、高质量地提交和更新简历、技能、项目证据、AI 工作流和机会偏好,并最终形成 B 端 AI 招聘产品的数据生态。

---

## 1. 第一轮外部检索已经确认的事实

### 1.1 简历 / 求职工具是成熟真实需求

Teal、Huntr、Jobscan、Rezi、Kickresume 等产品都围绕以下功能展开:

- AI resume builder
- ATS checker
- resume-job match
- resume keyword scanner
- job tracker
- cover letter generator
- job application autofill
- personal website / resume-to-site

这说明用户愿意为了求职效率和简历优化导入简历、编辑经历、维护 job tracker。这是已验证需求,不是幻想。

### 1.2 但这个赛道已红海

如果我们只做 AI resume builder / ATS checker / cover letter,会直接进入红海。

这些产品的用户量已经很大:

- Teal 官网显示 loved by over 3.2M members, over 4M users。
- Huntr 官网显示 500,000+ job seekers。
- Rezi 官网显示 trusted by 4M+ job seekers。
- Kickresume 官网显示 trusted by 8M job seekers。

我们的差异化不能是“更好的 AI 简历”,而应是:

> 长期职业资产管理 + 能力证据 + 私密机会控制 + B 端授权生态。

### 1.3 AI 技能已成为真实招聘信号

第一轮检索显示:

- AI skills 在招聘市场中有工资溢价。
- AI roles 更偏技能招聘而非学历要求。
- 部分实验显示 AI skills 会提升面试机会。
- 但 AI skill exaggeration 也在出现。

因此“AI 能力证明”是一个真实但仍早期的机会。

### 1.4 机会市场已在向 AI economy 转向

Handshake 首页已经把自己定位为 “career network for the AI economy”,并强调 AI gigs、entry-level AI training jobs、1M+ companies ready to hire。

Wellfound 首页也已经强调 AI recruiter、RecruiterCloud、500M+ candidates、startup-ready candidates 等。

这说明招聘平台正在显式 AI 化。我们必须避免泛化,要找到 LinkedIn / Handshake / Wellfound 没有覆盖好的数据维度。

---

## 2. 需要继续执行的 8 条调研线

### Agent 1:真实用户痛点调研

目标:确认用户为什么愿意使用 C 端产品。

重点人群:

- AI-augmented marketing / GTM operator
- RevOps / marketing ops
- product / UX designer
- silent LinkedIn mid-level professional
- independent / fractional consultant

核心问题:

1. 用户多久更新一次简历 / LinkedIn?
2. 什么时候会觉得职业资料分散?
3. 是否会为不同 JD 改简历?
4. 是否用过 Teal / Huntr / Jobscan / Rezi / Kickresume?
5. 是否愿意导入简历给 AI 分析?
6. 是否愿意连接 GitHub / 个人站 / Substack / portfolio?
7. 是否愿意维护非公开的 opportunity preference?
8. AI 技能如何证明?是否担心“别人都在夸大”?

输出文件:

`v2_real_user_needs_research.md`

---

### Agent 2:竞品矩阵调研

目标:系统比较同质化产品。

产品分组:

1. AI resume / ATS tools: Teal, Huntr, Jobscan, Rezi, Kickresume, Resume.io, Zety, Novoresume。
2. Professional identity / portfolio: LinkedIn, Read.cv, Polywork, Bento, Behance, Dribbble, Contra。
3. Hiring marketplace / career network: Handshake, Wellfound, The Muse, Otta / Welcome to the Jungle, Y Combinator Work at a Startup。
4. Career data / skills graph adjacent: LinkedIn Skills, Workday Skills Cloud, Degreed, Eightfold, Gloat, SkyHive, Cornerstone。

需要比较:

- C 端价值主张
- 用户规模
- 是否免费
- 数据输入类型
- 是否生成结构化技能
- 是否连接 B 端
- 是否服务 active / passive candidate
- 是否有 proof / evidence 层
- 是否有 opportunity preference
- 是否有公开页
- 商业模式

输出文件:

`v2_competitor_matrix.md`

---

### Agent 3:B 端数据价值调研

目标:判断我们采集的数据到底是否比 LinkedIn / 简历库更有价值。

需要回答:

1. B 端 recruiter / sourcer 当前最缺什么候选人数据?
2. LinkedIn profile 最大问题是什么?
3. 哪些数据能提升推荐准确度?
4. 哪些数据能提升 passive candidate 回复率?
5. AI workflow proof 对 hiring manager 是否有用?
6. Opportunity preference 是否能减少无效触达?

输出文件:

`v2_b_side_data_value.md`

---

### Agent 4:数据源与合规调研

目标:确定哪些数据可以合法、稳定、低成本获取。

数据源:

- resume PDF / DOCX
- LinkedIn export
- GitHub OAuth
- GitHub public profile
- personal website / RSS
- Substack RSS
- Behance / Dribbble
- Notion page授权
- X API / 用户导入
- Google Drive / Docs 手动授权

要回答:

- 能否通过 API 获取
- 是否需要用户授权
- 是否可用于 B 端
- 是否需要删除 / 导出 / opt-out
- 是否受 EU AI Act 招聘高风险限制

输出文件:

`v2_data_source_compliance_matrix.md`

---

### Agent 5:产品价值主张调研

目标:确定用户最愿意点击和使用的表达。

测试方向:

1. 自动更新你的职业能力档案。
2. 把简历、项目和 AI 工作流整理成持续更新的职业资产库。
3. 证明你真的会 AI,而不是只在简历上写会 AI。
4. 默认私密,合适机会来时由你决定是否开放。
5. 让你的 LinkedIn 不再停留在上一份工作。
6. 为每个机会生成可信、可验证的职业证明。

输出文件:

`v2_messaging_research.md`

---

### Agent 6:MVP 行为实验设计

目标:验证用户是否会行动。

必须验证的行为:

- 导入简历
- 连接至少一个证据源
- 确认 AI 抽取技能
- 修正自己的能力标签
- 生成证据卡
- 设置机会偏好
- 30 天内回来更新

输出文件:

`v2_mvp_experiment_design.md`

---

### Agent 7:数据模型设计

目标:把 C 端行为转化为 B 端可用结构化数据。

核心数据对象:

1. Candidate Profile
2. Skill Graph
3. Evidence Graph
4. Opportunity Graph
5. Consent State
6. Freshness Signal
7. Proof Confidence Score

输出文件:

`v2_data_model.md`

---

### Agent 8:行业切入调研

目标:确定第一批 ICP。

候选行业:

- Marketing / GTM
- RevOps / marketing ops
- Product / PM
- Design / UX
- Consulting
- Sales
- HR / People Ops
- Finance / Legal / Healthcare 暂缓

输出文件:

`v2_icp_prioritization.md`

---

## 3. 下一步执行顺序

优先顺序:

1. `v2_competitor_matrix.md`
2. `v2_real_user_needs_research.md`
3. `v2_b_side_data_value.md`
4. `v2_mvp_experiment_design.md`
5. `v2_data_model.md`

理由:先搞清楚竞品和真实需求,再做 B 端价值和 MVP 实验,最后落到数据模型。

---

## 4. 当前临时判断

目前外部证据已经足够支持继续调研,但还不足以直接开发完整产品。

更准确的阶段判断:

> 不是验证“这个方向有没有市场”,而是验证“我们能否找到一个不与 Teal / Huntr / Jobscan / Rezi / LinkedIn 同质化的 C 端切入点,并让用户持续更新 B 端有价值的数据”。

最需要警惕的同质化陷阱:

- 做成 AI resume builder。
- 做成 ATS checker。
- 做成 job tracker。
- 做成 Read.cv 式公开主页。
- 做成 LinkedIn profile optimizer。

最应该保留的差异化:

- 半被动职业资产维护。
- AI workflow proof。
- 私密 opportunity preference。
- 用户授权式 B 端机会通道。
- 持续更新的数据生态。
