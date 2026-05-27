# V2 真实需求、竞品与多 Agent 调研 Brief

**日期**:2026-05-27  
**性质**:基于现有 raw_data / analysis + 2026-05-27 第一轮外部网页补充检索的研究补充。  
**目的**:回答初步设想的亮点、C 端用户为什么愿意用、哪些需求是真实需求 / 潜在需求、是否有创新、是否存在同质化竞品、竞品是否已经做出成绩,并给出下一轮多 Agent 调研方案。

---

## 0. 当前阶段最重要的结论

我们的初步设想有亮点,但不能只停留在“能力镜子”这个概念上。

它真正有机会的地方是:

> 用真实 C 端利好,驱动用户主动维护一个持续更新的职业资产档案;这个档案既能帮用户整理简历、证明能力、控制机会曝光,又能为 B 端招聘推荐提供比 LinkedIn / 静态简历更新、更细、更真实的数据。

这不是幻想需求。外部数据已经证明至少有三类真实需求存在:

1. **求职过程效率和 ATS 优化需求真实存在**。Teal、Huntr、Jobscan、Kickresume、Rezi 等工具都围绕 resume builder、job tracker、ATS checker、cover letter、job match 做出了用户规模。
2. **AI 技能成为招聘信号的需求真实存在**。多个劳动力市场研究显示 AI 技能有工资溢价、面试机会提升和职位要求变化;同时也出现“AI 能力夸大”问题,证明“能力证明”比“能力声明”更重要。
3. **被机会发现但不想公开求职的需求真实存在**。既有 raw data 已显示 LinkedIn OpenToWork 私密信号远大于公开 badge;这说明 C 端用户有强烈的私密机会控制需求。

但也有三类需求仍属于潜在需求,不能直接当作真实需求:

1. “用户每天看职业能力镜子”。
2. “用户愿意长期维护公开 proof page”。
3. “用户愿意为了 AI-search visibility 持续补充资料”。

这些必须通过用户访谈、landing page、MVP 行为数据验证。

---

## 1. 初步设想的亮点

### 1.1 亮点一:不是新 LinkedIn,而是职业资产管理层

现有 raw_data 已经反复证明,用户不会迁移出 LinkedIn。LinkedIn 是职业门面和默认身份层,但真实职业资产散落在简历、GitHub、Substack、个人网站、Behance、Dribbble、Notion、项目文档、工作流工具等地方。

我们的设想如果定位为“新 LinkedIn”,会高度同质化并且大概率失败。

但如果定位为“职业资产管理层”,逻辑就成立:

- 不替代 LinkedIn。
- 不逼用户发内容。
- 不做社交网络。
- 帮用户整理已有职业资产。
- 让用户需要时导出到 LinkedIn、简历、个人页、机会通道。

### 1.2 亮点二:从 claim 转向 proof

AI 时代 claim 变得更便宜。任何人都能在简历上写“会 AI”“会 automation”“会 prompt engineering”。外部新闻和研究已经显示,劳动者会夸大 AI 技能;如果招聘方无法区分真伪,传统简历价值会继续下降。

我们的创新点不是让用户写得更好,而是让用户证明得更真:

- 来源链接
- 时间戳
- 项目证据
- AI 工具栈
- workflow 过程
- human judgment 节点
- 结果指标
- 用户确认

这比普通 AI resume builder 更接近 B 端真正需要的数据。

### 1.3 亮点三:私密机会控制

用户不一定公开求职,但很多人愿意在更安全的前提下接触更好机会。

这个点非常关键,因为它连接 C 端利好和 B 端数据价值。

传统方式:

- 公开 Open to Work → 用户有社交风险。
- 猎头乱发 InMail → 用户体验差。
- B 端搜索简历库 → 数据陈旧。

我们的方式:

- 默认私密。
- 用户设置机会偏好。
- 系统只在匹配到明确机会时提醒。
- 用户同意后才开放资料。

这有机会成为区别于 LinkedIn 的核心体验。

### 1.4 亮点四:免费也能成立

这个产品不必依赖 C 端付费。

如果公司第一性目标是 B 端数据生态,那么 C 端早期免费是合理的。真正交换是:

> 用户获得职业资产整理、简历更新、能力证明、机会控制;平台获得用户授权的、持续更新的职业数据。

这比“让用户付 $20/月”更接近生态建设。

---

## 2. 为什么 C 端用户可能愿意用

### 2.1 真实动机一:求职和职业资料整理很麻烦

现有竞品已经验证这是真实需求。

Teal 官网显示其核心卖点是 AI resume builder、job tracker、resume-job match、ATS resume checker、cover letter、job board 保存和管理。Teal 自称有超过 4M users / 3.2M+ members,并强调免费开始使用。

Huntr 的产品同样围绕 job tracker、AI resume builder、tailored resume、autofill applications、contact tracker、interview tracker,并自称有 500,000+ job seekers 使用。

这说明“求职资料管理 + 简历定制 + 投递追踪”不是幻想需求。

我们的区别应是:不只服务“正在求职的人”,还服务“未来可能被机会发现的人”。

### 2.2 真实动机二:ATS / resume optimization 焦虑真实存在

Jobscan 的核心产品就是 ATS resume checker、match report、one-click optimize、LinkedIn optimization、job tracker。其页面强调 99% Fortune 500 使用 ATS,并围绕“让简历被系统读到”构建产品。

这说明用户愿意上传简历换取优化建议。对我们来说,这意味着“上传简历 / 导入 profile”可以成为低门槛入口。

但我们不能只做 ATS 优化。ATS 优化太红海,而且容易变成关键词堆砌。

我们的升级点是:

> 先帮用户整理职业资产和能力证据,再生成不同场景的简历 / profile / 证据页。

### 2.3 真实动机三:AI 技能正在变成职业竞争信号

学术和市场数据都在支持这个方向。

UK 约 1100 万职位广告研究显示,AI 相关岗位中雇主开始更强调技能而非学历;AI 技能有显著工资溢价,且教育要求在 AI 岗位中下降。

2026 年 recruiter conjoint experiment 显示,AI skills 能把候选人的 interview invitation probability 提升约 8-15 个百分点,并在某些场景中部分抵消年龄或学历劣势。

这说明 C 端用户有动机证明自己的 AI 能力。但问题是:他们不是只想写“我会 AI”,而是要证明“我如何用 AI 做出真实价值”。

### 2.4 真实动机四:AI 技能存在夸大和信任危机

最近新闻报道显示,大量 workers 承认夸大 AI skills,且只有少数人对自己声称的 AI 技能真正有信心。

这反而强化了我们的产品逻辑:

- 如果每个人都能 claim,claim 就贬值。
- 如果 claim 贬值,proof 就升值。
- 如果 proof 升值,职业证据层就有机会。

### 2.5 潜在动机:职业能力镜子

用户可能愿意周期性查看自己的技能变化、能力缺口、职业方向。但这目前更多是潜在需求。

它的证据来自 Whoop / Strava / Spotify Wrapped / GitHub Wrapped 等“数据反馈型产品”,但还没有直接证明 professional 用户愿意每周查看 career mirror。

所以它适合作为产品留存假设,但必须用 MVP 验证。

---

## 3. 哪些是真的需求,哪些是潜在需求

### 3.1 真实需求

| 需求 | 证据基础 | 对产品含义 |
|---|---|---|
| 简历 / Profile 整理 | Teal、Huntr、Rezi、Kickresume、Jobscan 已有用户规模 | MVP 必须支持简历导入、编辑、自动更新 |
| ATS / JD 匹配优化 | Jobscan、Teal、Huntr 均围绕此点 | 可作为入口,但不能做成唯一卖点 |
| 求职流程管理 | Teal / Huntr 都做 job tracker | 可借鉴,但我们不应做完整求职 CRM |
| AI 技能证明 | AI skills 有工资和面试机会价值;也存在夸大问题 | 需要从 claim 转 proof |
| 私密机会控制 | raw data 中 LinkedIn private open-to-work 信号强 | Opportunity Graph 是核心资产 |
| 多平台职业资产分散 | raw_data 42 人样本证明真实职业身份散落多处 | 需要聚合,但不能期待用户迁移 |

### 3.2 潜在需求

| 需求 | 当前证据 | 如何验证 |
|---|---|---|
| 每周看 career mirror | 类比 Strava / Spotify Wrapped,没有直接证据 | 30 天 MVP 行为数据 |
| 公开 AI workflow proof page | 有逻辑,但用户未验证 | 访谈 + 发布率 |
| AI-search visibility | consulting / creator 圈有信号,但仍早期 | landing page A/B test |
| 被动候选人愿意填 opportunity preference | 逻辑强,但需验证 | 私密 toggle 转化率 |
| 非求职状态下愿意更新简历 | 重要但未验证 | 30 / 60 天更新率 |

### 3.3 弱需求或伪需求

| 需求 | 为什么弱 |
|---|---|
| 新 LinkedIn | 用户不会迁移,LinkedIn 网络效应太强 |
| 纯公开职业主页 | Read.cv / Polywork / Bento 证明留存和商业化困难 |
| 人人持续创作 newsletter | newsletter 生态幂律明显,不适合大众 professional |
| 通用作品集平台 | 对非设计 / 非工程岗位不自然 |
| 简历美化工具 | 红海,且与 B 端数据护城河关系弱 |

---

## 4. 同质化产品和成绩

### 4.1 Resume / job-search assistant 类

| 产品 | 已有成绩 | 说明 | 对我们的启发 |
|---|---|---|---|
| Teal | 官网称超过 4M users / 3.2M+ members | AI resume builder + job tracker + match + ATS checker | 简历和求职管理是真实需求,但偏 active job seeker |
| Huntr | 官网称 500,000+ job seekers | job tracker + AI resume + autofill + contact / interview tracker | 用户愿意为求职流程管理建立工作台 |
| Jobscan | 强调 ATS / match / LinkedIn optimization | 99% Fortune 500 ATS、3x callbacks 等营销主张 | ATS 焦虑强,但产品红海 |
| Kickresume | 官网称帮助 2M+ people get hired | resume / cover letter / website builder / GDPR trust | 简历转个人网站已有产品,不是我们的差异化 |
| Rezi | 官网称 trusted by 4M job seekers | ATS-optimized AI resume builder | AI 简历生成高度同质化 |

判断:这一类产品验证了 C 端愿意导入职业数据,但它们主要服务 active job seeker。我们的创新空间在 passive / semi-passive professional、AI workflow proof、长期职业数据更新和 B 端生态反哺。

### 4.2 Professional identity / portfolio 类

| 产品 | 结果 | 说明 | 对我们的启发 |
|---|---|---|---|
| LinkedIn | 最大职业身份平台 | B 端 Recruiter 商业化成熟 | 不能正面对抗,只能补 LinkedIn 缺失数据 |
| Read.cv | 被 Perplexity 收购后关闭 | 设计好、用户喜欢,但独立平台不可持续 | 纯 profile 不够 |
| Polywork | 关停 / 返还资本 | 多元职业身份叙事强,但缺 daily utility | 不能只做身份表达 |
| Bento.me | 被 Linktree 收购后停用 | link-in-bio 工具层被聚合平台吃掉 | 轻量主页不构成护城河 |
| Behance / Dribbble | 设计作品集平台仍有生命力 | 因为绑定作品展示和招聘 / 客户 | 作品展示只适合部分垂直人群 |

判断:公开身份产品风险很高。只有当展示直接连接交易、客户、招聘或强社区时才成立。

### 4.3 Career marketplace / hiring ecosystem 类

| 产品 | 已有成绩 | 说明 | 对我们的启发 |
|---|---|---|---|
| Handshake | 学生 / early career 招聘生态 | 学校、学生、雇主三边网络 | 生态能成立,但需要明确人群和场景 |
| WayUp | 学生 / recent grads,曾有数百万用户 | profile + matching | 泛职业人群较难,垂直人群更清晰 |
| The Muse | 公司内容 + job board + coaching | 用内容降低求职信息不对称 | 内容可服务决策,但不是数据护城河核心 |
| Contra | freelancer / independent work | 有一定规模但未成为主流 LinkedIn 替代 | demand-side flywheel 很难 |

判断:生态型产品能成立,但必须选择窄场景和明确交易。不能一开始做全职业全人群。

---

## 5. 我们的逻辑是否有创新

有创新,但创新不是单点功能,而是组合架构。

### 5.1 不创新的部分

以下都不创新:

- AI resume builder
- cover letter generator
- ATS checker
- job tracker
- portfolio website
- LinkedIn profile optimization
- generic career advice

这些已经有成熟产品,且不少有百万级用户。

### 5.2 真正可能创新的部分

真正有机会的是以下组合:

1. **从 active job seeker 扩展到 semi-passive professional**。不只服务正在找工作的人,还服务“未来可能被机会发现”的人。
2. **从 resume optimization 扩展到 career asset management**。不是为某个 JD 改简历,而是长期维护职业资产。
3. **从 skill claim 扩展到 skill proof**。把 AI workflow、项目证据、来源时间戳、结果指标沉淀下来。
4. **从公开求职扩展到私密机会控制**。用户先审机会,再决定是否开放资料。
5. **从 C 端工具扩展到 B 端数据生态**。C 端免费使用,B 端获得更高质量、更实时、更细维度的人才数据。

这套组合如果执行好,有差异化。

---

## 6. 多 Agent 调研方案

当前最好不要急着写最终产品 spec。应该开一轮更细的多模块调研。可以按 8 个 agent 分工。

### Agent 1:真实用户痛点调研

目标:确认 C 端用户到底痛在哪。

研究对象:

- mid-level marketer / GTM operator
- product / UX designer
- RevOps / marketing ops
- fractional / independent consultant
- silent LinkedIn professionals

要回答:

1. 他们多久更新一次简历 / LinkedIn?
2. 最近一次需要证明能力是什么场景?
3. AI 技能怎么写进简历?是否焦虑真假?
4. 是否愿意导入简历和连接账号?
5. 不求职时是否愿意维护职业档案?
6. 什么利好能让他们持续更新?

产出:

- 真实需求清单
- 伪需求清单
- 用户原话
- ICP 优先级

### Agent 2:竞品和同质化产品调研

目标:搞清楚已经有人做了什么,做到什么程度。

覆盖:

- Teal
- Huntr
- Jobscan
- Rezi
- Kickresume
- Resume.io / Zety / Novoresume
- LinkedIn Premium / Career Explorer
- Read.cv / Polywork / Bento
- Contra / Wellfound / Handshake / The Muse

要回答:

1. 他们服务 active 还是 passive 用户?
2. 他们采集哪些职业数据?
3. 是否有 B 端数据闭环?
4. 用户规模 / 付费 / 增长如何?
5. 哪些功能已红海?
6. 哪些空白没被解决?

产出:

- 竞品矩阵
- 差异化机会
- 不应进入的红海功能

### Agent 3:B 端数据价值调研

目标:判断 C 端采集的数据对 B 端是否真的有用。

研究对象:

- recruiter
- sourcer
- TA leader
- hiring manager
- AI recruiting platform buyer

要回答:

1. LinkedIn profile 最大问题是什么?
2. 哪些字段最能提升推荐?
3. AI workflow proof 是否有价值?
4. passive candidate 的 opportunity preference 是否能提升转化?
5. B 端是否愿意为 user-authorized intro 付费?

产出:

- B 端字段优先级
- 数据价值评分
- 付费意愿初判

### Agent 4:平台和合规约束调研

目标:防止产品路径踩死路。

覆盖:

- LinkedIn export / API
- GitHub ToS
- X API cost
- Substack / RSS / export
- Behance / Dribbble API
- GDPR / CCPA / EU AI Act
- data deletion / portability

产出:

- 可接数据源清单
- 禁止路径清单
- MVP 合规边界

### Agent 5:Messaging 和 Landing Page 调研

目标:验证用户被哪种利好打动。

测试文案方向:

1. “自动更新你的职业能力档案”
2. “证明你的 AI 工作流,不是只写会 AI”
3. “默认私密,合适机会来时由你决定”
4. “把简历、项目和作品整理成一个持续更新的职业资产库”
5. “让你的 LinkedIn 不再停留在上一份工作”

产出:

- CTR / signup / import intent
- 哪种价值主张最强

### Agent 6:MVP 行为实验设计

目标:验证用户是否真的行动,不是口头喜欢。

核心实验:

1. 简历导入转化率
2. AI 抽取技能后的确认率
3. 连接外部证据源转化率
4. evidence card 生成率
5. opportunity preference 填写率
6. D30 更新率

产出:

- MVP 指标框架
- 失败判定标准

### Agent 7:数据模型与 B 端闭环设计

目标:把 C 端行为转成 B 端可用数据。

数据对象:

- Candidate Profile
- Skill Graph
- Evidence Graph
- Opportunity Graph
- Consent / Visibility State

产出:

- 数据 schema
- 事件埋点
- B 端推荐字段映射

### Agent 8:行业切入优先级调研

目标:确定第一批用户到底是谁。

比较:

- Marketing / GTM
- Design / UX
- RevOps / Sales Ops
- Product Manager
- Consulting
- HR / People Ops
- Finance / Legal / Healthcare 暂缓

产出:

- ICP 排序
- 每个人群的真实痛点
- 冷启动渠道

---

## 7. 下一步仓库应补充的文件

建议后续新增或更新这些文件:

1. `v2_real_user_needs_research.md`  
   专门放真实用户需求和痛点。

2. `v2_competitor_matrix.md`  
   专门放 Teal / Huntr / Jobscan / Rezi / Kickresume / LinkedIn / Read.cv / Polywork 等竞品矩阵。

3. `v2_b_side_data_value.md`  
   专门分析哪些 C 端数据能提升 B 端推荐质量。

4. `v2_mvp_experiment_design.md`  
   专门定义 90 天实验和指标。

5. `v2_interview_script.md`  
   专门给真实用户访谈用。

---

## 8. 第一轮外部补充来源

本 brief 第一轮外部网页检索使用了以下来源,后续应继续扩展和校验:

- Teal 官网: https://www.tealhq.com/
- Huntr 官网: https://huntr.co/
- Jobscan 官网: https://www.jobscan.co/
- Kickresume 官网: https://www.kickresume.com/
- Rezi 官网: https://www.rezi.ai/
- Reuters, 2026-05-25, Global firms rethink GCC hiring in India as AI shifts skill demand: https://www.reuters.com/world/india/global-firms-rethink-gcc-hiring-india-ai-shifts-skill-demand-2026-05-25/
- arXiv, Skills or Degree? The Rise of Skill-Based Hiring for AI and Green Jobs: https://arxiv.org/abs/2312.11942
- arXiv, AI Skills Improve Job Prospects: Causal Evidence from a Hiring Experiment: https://arxiv.org/abs/2601.13286
- arXiv, Multidimensional Skills as a Measure of Human Capital: Evidence from LinkedIn Profiles: https://arxiv.org/abs/2409.18638
- TechRadar / GCheck AI skill exaggeration report summary: https://www.techradar.com/pro/its-not-just-you-nearly-two-thirds-of-workers-say-theyve-exaggerated-ai-skills-to-get-ahead-at-their-company

---

## 9. 当前判断

我们的逻辑有创新,但不能以“能力镜子”作为唯一卖点。

真正应该验证的是:

> 用户是否愿意因为职业资产整理、简历自动更新、能力证明、私密机会控制这些实际利好,持续给我们最新职业数据。

如果答案是 yes,这个项目有生态价值。

如果用户只觉得“页面好看”“洞察有趣”,但不愿导入简历、不愿确认技能、不愿连接证据源、不愿更新机会偏好,那这个方向就只是 another profile tool,不值得继续。
