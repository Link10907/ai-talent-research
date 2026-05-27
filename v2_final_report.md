# V2 Final Report — AI 时代职业能力镜子产品决策报告

**日期**:2026-05-27  
**输入文件**: `analysis/01_*` ~ `analysis/07_*`、`product_thesis_v2.md`、`final_report.md`、`v2_progress.md`、`citations/citations_v2.json`  
**报告性质**:基于 V2 已完成数据收集和 7 份 Phase 分析的综合决策报告。本文不是继续做信息罗列,而是给出产品方向、MVP 范围、风险边界和 90 天执行方案。

---

## 0. 一句话结论

**V2 方向值得继续,但必须从“泛职业身份产品”收缩为“AI 时代职业能力镜子 + 可验证能力证据层 + 用户主动授权的机会通道”。**

推荐度:**7 / 10**。  
如果坚持做“新的 LinkedIn / 新的公开职业主页 / 新的作品集社区”,推荐度降到 **3 / 10**。  
如果按本报告建议,先从 **AI-augmented marketing operator** 和部分 **design-adjacent operator** 切入,用私密能力镜子承接日常价值,用可验证证据页承接外部展示,用用户主动授权承接 B 端反哺,则值得进入 90 天原型验证。

核心判断有三点。

第一,**市场窗口真实存在,但不是“大家要迁移出 LinkedIn”。**V2 证据反复显示,用户不会迁移,只会叠加。LinkedIn 是默认门面层,但真正的工作产出、观点、受众和能力证据正在分散到 X、Substack、GitHub、个人网站、Behance、Dribbble、Notion 等多处。[V107][V109]

第二,**V2 的“职业能力镜子”命题比 V1 的“能力证据层”更接近 C 端动机,但还需要修正。**能力镜子可以解决“我为什么每天回来”的问题;能力证据层可以解决“我为什么愿意公开/分享”的问题;B 端机会通道可以解决“这对公司为什么有商业价值”的问题。三者必须是一体化闭环,不能拆成三个产品。

第三,**绝对不能走后台静默反哺 B 端的路线。**EU AI Act、CCPA、GitHub ToS、LinkedIn API 关闭、23andMe 破产数据转让事件共同指向同一个结论:未来可持续的架构只能是 user-initiated,即用户持有、用户授权、用户可撤回、用户可观测。[V637][V638][V602][V635][V649][V650]

---

## 1. V2 相比 V1 到底新增了什么判断

V1 已经回答了“不要做新 LinkedIn,要做 LinkedIn 结构性做不到的能力证据层”。V2 的贡献不是重复这个结论,而是进一步回答:这个能力证据层如何让 C 端用户愿意持续贡献数据。

### 1.1 Newsletter 调研给出的纠偏

Newsletter 生态已经很成熟,但它不是一个大众职业身份产品市场。Substack 已经有 50M 活跃订阅、5M 付费订阅,50+ 创作者年收入超过 $1M,但中位创作者年收入约 $4,000,接近一半创作者年收入低于 $500。[V001][V024]

这说明两件事。

第一,不要把“让用户像 newsletter 创作者一样持续输出”作为普适产品假设。持续公开输出是极少数人的能力,不是普通专业人士的日常。

第二,newsletter 更适合作为 **获客渠道、信任背书、内容分发网络**。它不适合作为我们产品的核心产出模块。Phase 01 对我们的直接建议是:不要内置 newsletter 生产工具,而是把 newsletter 当作高信任渠道和行业信息源。

因此,V2 thesis 里“行业时报”这个 hook 可以保留,但必须降级为 **contextual sidebar**:它让用户有理由回来,但产品的主价值不是读资讯,而是看见自己的能力变化。

### 1.2 职业身份景观调研给出的纠偏

V2 Phase 02 最重要的发现是:Western professionals 正在形成“门面 / 客厅”分离。LinkedIn 是门面,必须有;但真正认真表达、沉淀观点、展示作品的“客厅”,正在迁移到 X、Substack、GitHub、个人网站等 owned audience 资产。[V107][V109]

Read.cv、Polywork、Lunchclub、Path、Bento.me 的失败说明,“设计更好看的职业主页”不是未被满足的强需求,而是一个没有交易钩子的中间层。没有招聘、客户、收入、机会、工作流增益,纯展示产品就会变成静态名片。[V100][V102][V103][V123]

所以,产品不能说“来这里建立你的新主页”。更好的切入语言是:

> 把你已经散落在各处的职业证据整理成一个你自己能看懂、也能在需要时给别人看的能力镜子。

这句话的重点不是“展示”,而是“整理 + 看懂 + 必要时给别人看”。

### 1.3 目标用户调研给出的纠偏

Marketing 是首切方向,但不是因为它最大,而是因为它最暴露。Marketing 人群公开承认 AI 工具、公开讨论 AI workflow、公开用 newsletter / LinkedIn / course / cohort 变现。Emily Kramer 的判断很直接:“你的 job description 已经因为 AI 改变了,不管你知不知道。”[V201]

但 V2 同时指出,头部 marketing creator 已经过度被服务。Lenny、Justin Welsh、Harry Dry、Codie Sanchez、Anthony Pierri 等人已经拥有成熟的 newsletter、LinkedIn、course、community、sponsorship 组合。[V200][V218][V223][V228][V213]

真正应该服务的不是这些头部 creator,而是比他们小两个数量级的中层专业人士:在 SaaS、agency、B2B 公司、AI startup 内部工作,已经开始用 AI 改造自己的工作,但没有时间和能力把这些东西变成公开影响力的人。

Design 是产品差异化的重要方向,但不是最适合冷启动的 ICP。设计师有 portfolio 传统,但 AI 让 portfolio 的证明力变弱。图片本身越来越难证明“这是我做的”,更需要展示“我如何判断、如何迭代、如何组织 AI 工作流”。[V231][V233]

Consulting 则不适合作为第一冷启动人群。公开样本几乎都是离职后做内容的人,真正还在 MBB / Big 4 / 企业内部的 consultant 基本不可见。原因不是数据没抓到,而是客户保密、NDA、公司规范决定他们不适合公开发声。[V271]

### 1.4 私密 vs 展示调研给出的关键修正

Phase 04 给出一个和 V2 thesis 有张力的结论:纯默认私密虽然让用户更安心,但很难反哺 B 端;纯默认公开虽然更利于 B 端,但容易引发信任焦虑。

Notion、Obsidian、Roam 证明私密工具能赚钱,但 B 端数据网络效应很弱。Notion 可以做到 100M 用户和 $500M–$600M ARR,但它赚的是 SaaS 订阅,不是职业数据反哺。[V300][V302][V303]

23andMe 是“私密 + B 端反哺”最强对照。它有 80% research opt-in,有 GSK $300M 合作,有 40+ 药物程序,但在 2025 年破产和数据转让时仍引发信任崩塌,28 个州 AG 反对数据转让,大量用户删除账号。[V309][V310][V312][V329]

LinkedIn 和 GitHub 则说明另一条路更稳:用户知道自己公开是为了被发现,平台用公开资料形成 B 端价值。LinkedIn Talent Solutions 是 $10B 级收入线;GitHub 公开代码生态又反向支撑 Copilot 的开发者价值。[V316][V317]

因此,本报告建议的最终模式不是“默认全部私密”,也不是“默认全部公开”,而是三层结构:

1. **原始数据层默认私密**。连接 GitHub、Substack、X、个人站之后,原始抓取内容和行为信号只给用户自己看。
2. **证据卡片层用户确认后公开**。AI 可以自动生成 evidence card / workflow case study,但发布必须由用户审核。
3. **机会通道层默认关闭**。B 端只有在用户主动打开 opportunity channel 后才能触达。

这个结构同时保住 C 端信任和 B 端商业路径。

### 1.5 冷启动调研给出的现实约束

Phase 05 的冷启动结论很明确:第一批用户不可能靠 Product Hunt 或公开发布获得。应该从已经被 KOL 教育过的窄社区进入。Marketing 从 Lenny's Newsletter、MKT1、Justin Welsh 周边来;Design 从 Dive Club、Femke 社区来;Consulting 从 Tom Critchlow、Paul Millerd 等独立咨询圈来。[V400][V404][V405]

PM signal 的时间窗不能幻想 3 个月。GitHub 14 个月到 10 万用户,LinkedIn 15 个月到 100 万用户,Strava 头两年都在本地圈层内,Substack 14 个月到 11K 付费订户。[V401][V403][V404][V405]

合理预期是:9 个月看到早期信号,12–18 个月看到可信 PMF 迹象,悲观情况下 24 个月以上。

资金也不是越多越好。Polywork 融资 $44.5M 仍然没有解决 weekly utility loop,最后关停。Path 融资 $66.2M 也未能建立可持续网络。Phase 05 估算,6 个月 MVP + 12 个月冷启动需要 $1.5M–$3M,关键不是多融资,而是把第一批人群和第一条留存回路做对。[V411][V416]

### 1.6 用户意愿调研给出的定价和动机边界

Phase 06 认为,目标用户中大约 5%–8% 愿意为“AI 加持的可见性、匹配和周期化职业洞察”付 $20/月,前提是产品有连续反馈、透明授权和可撤回机制。[V511][V513][V514][V551]

$20/月是当前 AI 专业工具的核心价格锚。ChatGPT Plus、Claude Pro、Cursor、Perplexity Pro 都在这个价格附近。低于 $20 会显得不够严肃,高于 $40 则会触及个人 daily-use 心理上限。

更重要的是,Phase 06 给出一个关键需求:隐性被发现需求远大于显性求职需求。LinkedIn 有 220M open-to-work 信号,但只有约 28M–40M 用户愿意公开打 #OpenToWork 徽章。约 180M 用户愿意私下被招聘者搜索,但不愿向同事和朋友公开。[V509][V510]

这就是“职业能力镜子”最应该抓住的心理空间:用户不想公开说“我在找工作”,但希望在合适机会出现时被看见。

### 1.7 技术和合规调研给出的硬边界

Phase 07 是 V2 最重要的风险边界文件。结论很硬:不能做 silent broker,只能做 user-initiated profile push。

原因有五个。

第一,EU AI Act 把招聘 AI 列入高风险类别。2026-08-02 之后,任何被雇主用于候选人评估的 AI 职业画像,在欧盟都要面对风险管理、偏见测试、人工监督、日志和注册义务。[V637][V638]

第二,LinkedIn 对第三方基本关闭。OAuth 只给 `openid/profile/email`,Talent API 需要 partnership。hiQ 和 Proxycurl 相关诉讼说明,商业化抓取 LinkedIn 是高风险路径。[V608][V609][V610][V611]

第三,GitHub ToS 明确禁止把 GitHub 用户数据卖给 recruiters、headhunters、job boards。这直接命中“把 GitHub-derived 数据卖给雇主”的设想。[V602]

第四,CCPA 对 sale 的定义很广。把职业数据传给雇主换取付费,很容易落入 sale 范畴,必须提供 do-not-sell 机制。[V635][V636]

第五,23andMe 说明,即便早期用户同意了某种用途,公司破产、出售、业务改变时,原同意会在用户心智中失效。[V649][V650]

所以,B 端商业化必须改成:

> 用户主动生成 profile → 用户主动选择是否开放机会通道 → 平台只在用户授权范围内为其推送机会 → B 端不能直接购买后台数据池。

---

## 2. 最终产品定义

### 2.1 产品名称占位

建议暂定为:**Career Mirror** 或 **WorkProof**。中文内部称为“职业能力镜子”。

这不是最终品牌,但能帮助团队避免滑向“职业社交平台”“在线简历”“作品集网站”这些旧范式。

### 2.2 产品一句话

**一个面向 AI-augmented professionals 的职业能力镜子:自动聚合用户分散在多平台的真实产出,生成私密能力地图和可验证证据卡片,在用户主动授权后形成对外展示和机会匹配。**

### 2.3 产品不是哪些东西

它不是 LinkedIn 替代品。用户不会迁移。

它不是 Read.cv / Polywork 的复刻。漂亮 profile 没有 retention。

它不是 newsletter 工具。newsletter 是渠道和信息源,不是核心产物。

它不是 AI 简历生成器。AI 简历生成器会加剧造假,不解决信任。

它不是后台人才数据库。后台静默聚合会踩中 ToS、CCPA、EU AI Act 和用户信任风险。

### 2.4 产品由三层组成

#### 第一层:私密能力镜子

用户连接 GitHub、个人站、Substack RSS、Behance / Dribbble、Notion 页面、手动上传的项目材料。系统自动生成:

- 能力地图
- 技能演化时间线
- AI workflow 指纹
- 近期产出摘要
- 职业兴趣变化
- “本季度你在变成什么样”复盘

这一层默认私密。它解决 daily / weekly utility。

#### 第二层:可验证能力证据

系统从私密能力镜子中生成 evidence card,但必须由用户审核后发布。证据卡片不是简单列作品,而是包括:

- 产出来源
- 时间戳
- 关联链接
- 用户角色
- AI 工具参与程度
- 人类判断节点
- 结果指标
- 脱敏说明

这一层解决外部信任和可展示性。

#### 第三层:用户主动授权的机会通道

用户可以打开 opportunity channel。打开后,平台可以在用户许可范围内把其证据页推给特定 B 端需求方。B 端必须提交具体机会,包括角色、预算、地点、薪酬区间、合作方式或招聘需求。

这一层解决 B 端反哺和商业化,但不能在阶段一作为核心卖点。

---

## 3. 首切用户选择

### 3.1 第一优先级:AI-augmented marketing operator

最先服务的人不是 marketing creator,而是中层营销专业人士。

典型画像:

- 25–40 岁
- 3–10 年经验
- 在 B2B SaaS、AI startup、agency、growth team 工作
- 已经用 ChatGPT、Claude、Jasper、Copy.ai、Notion AI、Clay、Zapier、n8n、HubSpot AI 等工具改造工作
- 有真实 workflow,但没有系统沉淀
- LinkedIn 上不想高频发帖,但希望被看见
- 未来 12–24 个月可能跳槽、接咨询、做副业、进入 AI-native 公司

选择这个人群的理由:

1. AI 使用不羞耻。Marketing 人群公开 flex AI 工具,不会像法律、医疗、金融那样强监管。
2. 输出形态相对可脱敏。campaign、landing page、growth workflow、content system、lead gen pipeline 可以做案例。
3. 付费习惯存在。Marketing 人群已经为 newsletter、course、AI tools、社群和 SaaS 付费。[V500][V529][V531]
4. KOL 渠道可达。Lenny、MKT1、Justin Welsh、Emily Kramer 等可以作为种子入口。
5. B 端价值清楚。企业需要“会用 AI 做增长/营销的人”,但 LinkedIn 简历无法证明 workflow 能力。

### 3.2 第二优先级:design-adjacent operator

不是全部设计师,而是以下人群:

- product designer in AI-native startup
- design engineer
- AI video / motion designer
- no-code / prototype-heavy designer
- Figma + v0 / Lovable / Framer / Webflow 工作流使用者

这类人群适合作为差异化方向,但不建议作为第一冷启动 ICP。原因是 design 公开表达更克制,行业文化更重作品质量,对“AI 生成”更敏感。[V231]

产品上需要支持两种证据:

1. 传统作品链接。
2. AI 参与后的设计决策过程。

### 3.3 第三优先级:independent / fractional consultant

咨询人群应该在 6–12 个月后进入,不要一开始就做。原因很现实:在岗咨询顾问受 NDA 和客户保密限制,可公开材料很少。公开样本多数是离职后独立创作者,不能代表在岗咨询人群。[V271]

但这个群体后续商业价值很高。独立顾问、fractional CMO、ex-MBB indie consultant 需要被客户发现,而 LinkedIn 页面同质化严重。对他们来说,AI-search visibility 和 sanitized workflow proof 很有价值。

### 3.4 暂不服务的人群

HR 不作为 C 端首切。HR 更像 B 端买家。HR 细分中的 fractional CHRO / People-Ops creator 可以观察,但市场很小。

医疗、法律、金融不作为第一阶段首切。它们有真实需求,但合规、保密、职业风险太高。更适合在产品证明基础能力后做 vertical expansion。

Sales / RevOps / Operations 暂不作为首切。它们存在 AI workflow proof 需求,但真实公开意愿和 artifact 形态仍不清楚。Sales 中还需要验证“quota 被 AI 稀释后是否真的要证明人机协作能力”。Operations 还需要验证是否愿意发布脱敏流程。

学生和 fresh grad 暂不服务。他们缺少足够真实产出,容易把产品拖回“简历优化器”。

---

## 4. MVP 应该做什么

### 4.1 MVP 不做完整平台

MVP 不应该做 feed、社区、评论、关注、私信、招聘搜索、简历投递、AI 评分、企业 dashboard。

这些功能会让产品过早进入 LinkedIn / Polywork / Wellfound 的死亡区。

### 4.2 MVP 的核心闭环

MVP 只验证一个闭环:

> 连接数据源 → 产生私密能力洞察 → 生成证据卡片 → 用户愿意发布/分享 → 用户愿意回来更新第二次。

这个闭环里,最关键不是第一张卡片,而是第二次回访。

### 4.3 MVP 功能范围

#### 功能 1:账号和数据源连接

优先级:

1. GitHub
2. 个人网站 / RSS
3. Substack RSS
4. 手动添加项目链接
5. Notion 页面授权
6. Behance / Dribbble
7. X 只做最近 N 条或用户精选导入
8. LinkedIn 只做 sign-in,不抓经历

这样设计是因为 LinkedIn API 不可依赖,X 成本过高,GitHub 和个人站是相对干净的数据源。[V608][V604][V602]

#### 功能 2:30 秒 Magic Moment

用户连接第一个数据源后,30 秒内必须看到一个具体、有依据、带轻微惊讶感的洞察。

Marketing 版本示例:

- “你过去 90 天公开内容里,AI workflow 相关主题从 12% 上升到 41%。你已经在从 content marketer 转向 AI workflow marketer。”
- “你最近 6 个项目中有 4 个都在围绕 lead qualification 自动化,但你的 LinkedIn profile 仍然只写 demand generation。”
- “你的案例里多次出现 Clay + Zapier + HubSpot 组合,这更像 GTM systems operator,不是普通 marketer。”

Design 版本示例:

- “你的最近 5 个作品不再以视觉稿为中心,而是以 prototype 和 interaction 为中心。这说明你正在向 design engineer 靠近。”
- “你公开作品的 AI 参与点没有被说明,这会让作品证明力下降。建议补充 human judgment 节点。”

#### 功能 3:AI workflow case study builder

这是 MVP 的主功能。模板不要太复杂,但要能沉淀非开发者的 commit。

建议字段:

- Context
- Problem
- Workflow
- Tools
- Human judgment
- AI contribution
- Output
- Metrics
- What I learned
- What can be public
- What must stay private

这比“上传作品图”更适合 AI 时代的复合型工作。

#### 功能 4:私密能力地图

用户创建证据卡片后,系统自动维护能力地图。

第一版不需要复杂图谱,只需要:

- 核心能力标签
- AI 工具标签
- 行业标签
- 产出类型
- 最近 30 / 90 天变化
- 建议补充的证据缺口

#### 功能 5:可分享证据页

用户可以一键生成公开页面,但默认只是草稿。用户确认后可以发布。

页面需要支持:

- 公开链接
- LinkedIn Featured 区域可粘贴
- 个人网站 embed
- JSON-LD / schema.org
- robots/indexing 控制
- 删除和撤回

#### 功能 6:数据控制中心

第一天就要做,不能后补。

至少包括:

- 每个数据源的授权状态
- 读取了哪些数据
- 生成了哪些推断
- 哪些内容公开
- 哪些内容私密
- 一键导出
- 一键删除
- B 端机会通道状态

---

## 5. 商业模式建议

### 5.1 阶段一:个人免费 + Pro $20/月

免费层:

- 连接 1–2 个数据源
- 生成基础能力镜子
- 创建 1–3 张证据卡片
- 公开基础页面

Pro 层:$20/月。

Pro 提供:

- 更多数据源
- 无限证据卡片
- 高级能力地图
- 月度 career Wrapped
- AI-search visibility 检查
- 多版本公开页面
- 自定义域名或高级 embed
- 导出包

这个定价符合 AI 专业工具 $20/月价格锚。[V511][V513][V514][V551]

### 5.2 阶段二:团队版和 creator / consultant 版

团队版不是给企业 HR 的,而是给小团队、agency、consulting boutique、founder-led studio。

他们可能需要:

- 团队成员能力图谱
- 项目案例库
- 对外 credentials page
- 客户案例脱敏模板
- 团队级公开页面

价格可以从 $99/月团队起步。

### 5.3 阶段三:B 端机会通道

B 端不能购买后台数据库,只能发起具体机会。

候选模式:

- per qualified intro
- per opportunity posting
- success fee
- subscription + contact credit

但所有模式都必须满足:

1. 用户默认关闭。
2. 用户可见是哪家公司、什么机会、为什么匹配。
3. 用户决定是否回应。
4. 用户关闭后立刻停止。
5. 原始数据不出售。

---

## 6. 关键指标体系

### 6.1 90 天验证指标

最重要的不是注册量,而是行为质量。

| 指标 | 合格线 | 优秀线 |
|---|---:|---:|
| Landing signup | 5% | 8%+ |
| OAuth 完成率 | 35% | 50%+ |
| Magic Moment positive | 50% | 70%+ |
| 创建首张证据卡 | 30% | 45%+ |
| 发布或分享证据页 | 15% | 30%+ |
| 连接 2+ 数据源 | 25% | 40%+ |
| 第 4 周回访 | 25% | 40%+ |
| 愿付 $20/月 | 3% | 8%+ |

### 6.2 不应该过早追的指标

不要过早追求 MAU、总用户数、公开页面数、B 端收入、SEO 流量、社交分享量。

这些指标可能会诱导团队做“漂亮公开主页”和“内容社区”,从而重复 Polywork / Read.cv 的路径。

### 6.3 最重要的定性信号

用户是否说出类似的话:

- “这个比我的 LinkedIn 更像我现在真实在做的事。”
- “我不知道我已经在向这个方向转型。”
- “这张卡我愿意发给招聘方/客户/朋友看。”
- “我愿意每个月回来更新一次。”
- “我希望它下个月告诉我我变成了什么样。”

如果用户只说“页面挺好看”,那不是好信号。

---

## 7. 90 天执行计划

### 第 1–2 周:访谈和概念验证

目标是验证用户是否真的有能力沉淀需求。

访谈对象:

- 8 个 mid-level marketer
- 4 个 design-adjacent operator
- 4 个 independent / fractional consultant
- 2 个 HR / recruiter
- 2 个反向样本,如律师、金融或医疗从业者

核心问题:

1. 过去 12 个月你做过哪些 AI 改造工作?
2. 你现在如何向别人证明这些能力?
3. LinkedIn 能不能表达这些变化?
4. 你有没有过“想被发现但不想公开求职”的时刻?
5. 你愿意连接哪些账号?哪些绝对不愿意?
6. 如果产品给你一份私密能力地图,你会每月看吗?
7. 如果产品帮你生成公开证据页,你愿意发给谁?
8. 你对 B 端机会通道的底线是什么?

### 第 3–4 周:Magic Moment prototype

不用先做完整产品。先做半自动原型即可。

流程:

1. 用户提交 GitHub / Substack / 个人站 / LinkedIn URL。
2. 人工或脚本抓取有限数据。
3. 生成 3 条能力洞察。
4. 访谈中观察用户反应。

成功标准:

- 70% 用户认为至少 1 条洞察“有点准且有启发”。
- 50% 用户愿意补充第二个数据源。
- 30% 用户愿意把某条洞察转成公开证据卡。

### 第 5–8 周:MVP Alpha

做最小产品:

- 登录
- 数据源连接
- 30 秒洞察
- workflow case study builder
- 私密能力地图
- 证据页发布
- 数据控制中心

Alpha 限 50–100 人。

不要加社交功能。

### 第 9–12 周:KOL 小规模冷启动

渠道不要广撒。

建议找 3–5 个 KOL / 社群:

- Lenny's 周边
- MKT1
- Growth Unhinged
- Dive Club
- Femke 社区
- 一个独立顾问 newsletter

形式不是广告投放,而是“邀请 50 个读者体验一个 AI workflow proof 工具”。

90 天末需要回答 5 个问题:

1. 用户是否愿意连接至少 1 个真实数据源?
2. Magic Moment 是否足够强?
3. 用户是否愿意创建第二张证据卡?
4. 用户是否愿意公开或分享证据页?
5. 用户是否愿意为高级能力镜子付 $20/月?

只要前 4 个都不成立,就不要进入产品开发加速。

---

## 8. 产品风险和应对

### 风险 1:产品滑向“更好看的 LinkedIn”

这是最大风险。团队一旦开始做 profile 美化、feed、关注、评论,就会进入已被证明失败的路径。[V100][V102][V123]

应对:所有功能必须回答“它是否提升用户看见自己 / 证明自己 / 控制授权的能力”。不能回答就不做。

### 风险 2:用户只创建一次,不会回来

Polywork、Read.cv、Bento 的共同问题是静态展示无 daily / weekly loop。[V409][V412]

应对:能力镜子必须周期性更新。每周给用户一条“能力变化 / 证据缺口 / 行业机会”反馈。

### 风险 3:原始数据太难接

LinkedIn 不开放,X 太贵,Substack 无 API,GitHub ToS 限制 B 端 resale。[V604][V608][V602]

应对:首期只做干净数据源和 user-provided URL。不要承诺“一键聚合全网职业身份”。

### 风险 4:隐私信任崩塌

用户对职业数据非常敏感。23andMe 证明,即便用户早期同意,公司出售或破产时也会引爆信任危机。[V649][V650]

应对:Day 1 做数据控制中心、删除、导出、撤回、用途日志、倒闭处理条款。

### 风险 5:AI 生成内容导致证据贬值

如果证据卡片全靠 AI 写,会变成新一代虚假作品集。

应对:所有 evidence card 必须绑定来源、时间戳、链接、指标和用户审核。AI 只负责整理,不负责凭空生成。

### 风险 6:目标用户太小

如果只服务公开 creator,SAM 会太小。LinkedIn 上真正发内容的人约 1%,这不是 venture-scale 基础。[V205][V258]

应对:产品必须对沉默多数也有用,即私密能力镜子 + 必要时开放,而不是要求每个人持续公开发声。

### 风险 7:B 端变现被合规限制

EU AI Act 可能把招聘相关 AI 画像列为高风险。如果产品给雇主展示 AI score,风险很高。[V637][V638]

应对:不要做候选人评分。只做用户授权的证据展示和机会介绍。欧盟先谨慎,美国/英国先试点。

### 风险 8:founder-market fit 不足

Phase 05 明确指出,冷启动依赖社区原住民。团队如果不是欧美 marketing / design / consulting 圈原住民,需要借 KOL 的 trust。[V400][V404][V405]

应对:不要自己硬推。找 KOL 联合、顾问、社区 host,让他们成为第一批分发节点。

---

## 9. 对 V2 product_thesis 的修订建议

V2 thesis 的大方向对,但需要做 5 个修正。

### 修正 1:从“默认私密”改为“三层可见性”

原始数据默认私密。证据卡片默认草稿。公开页面由用户确认发布。机会通道默认关闭。

这比“全部默认私密”更利于 B 端价值,也比“全部默认公开”更可信。

### 修正 2:行业时报不能做主产品

行业时报可以做 onboarding 和 weekly loop,但不能做 destination。Newsletter 生态已经成熟且强幂律,中位创作者留存和收入并不理想。[V001][V024]

应把行业时报改成:

- 每周职业雷达
- 行业变化对我能力地图的影响
- 我应该补哪张证据卡
- 哪些机会正在靠近我的能力方向

### 修正 3:首切人群进一步收窄

不要同时做 Marketing / Design / Consulting。90 天内只做 **AI-augmented marketing operator**。

Design 做共创样本。Consulting 只做访谈,不做产品功能优先级。

### 修正 4:Magic Moment 从“酷炫洞察”改成“身份变化证据”

不是告诉用户“你常用 Python / 你常写 AI”。这种太浅。

要告诉用户:

- 你的实际工作已经从 A 转向 B。
- 你的公开身份还停留在 A。
- 你缺少证明 B 的证据。
- 我可以帮你生成一张证据卡。

### 修正 5:B 端反哺从“隐性沉淀”改成“透明可控”

“隐性”只应该体现在首页营销不强调求职,不能体现在数据使用不透明。真正可持续的 B 端反哺必须用户可见、可控、可撤回。

---

## 10. 最终建议

### 10.1 做,但只做一个很窄的版本

建议进入 90 天验证,但不建议直接开发完整平台。

90 天目标不是做出产品,而是证明:

1. 用户愿意连接数据源。
2. Magic Moment 足够强。
3. 用户愿意生成证据卡。
4. 用户愿意第二次回来。
5. 用户愿意为 $20/月高级版表达付费意愿。

### 10.2 不要把 B 端放到第一阶段台前

第一阶段不卖“找工作”。不卖“被招聘”。不卖“AI 匹配”。

第一阶段卖:

- 看清自己
- 证明自己
- 管理职业证据
- 控制何时被看见

B 端只做访谈和 LOI,不做产品入口。

### 10.3 最小团队建议

90 天验证团队:

- 1 个产品负责人
- 1 个 full-stack engineer
- 1 个 AI / data engineer
- 0.5 个 designer
- 0.5 个 growth / community
- 1 个欧美 marketing 圈顾问或 KOL partner

不要一开始组大团队。

### 10.4 进入下一阶段的硬门槛

90 天后,只有满足以下条件才进入 6–12 个月 MVP:

- 100 个 Alpha 用户中,40 个完成至少 1 个数据源连接。
- 30 个创建至少 1 张证据卡。
- 15 个发布或分享证据页。
- 20 个在第 4 周回访。
- 至少 8 个明确愿意为 Pro 付费。
- 至少 3 个 B 端买家愿意继续讨论 user-authorized opportunity channel。

如果达不到,不要用“市场教育还不够”自我安慰。应该回到用户需求重验。

---

## 11. 待人工决策问题

### 11.1 战略问题

1. 是否接受前 90 天只做 AI-augmented marketing operator?
2. 是否接受第一阶段不做 B 端收入?
3. 是否接受 LinkedIn 只做导出 / sign-in,不做聚合?
4. 是否接受产品定位不是“职业身份平台”,而是“能力镜子 + 证据卡片工具”?
5. 是否接受美国/英国先行,欧盟延后合规进入?

### 11.2 产品问题

1. Magic Moment 是否由 AI 自动生成,还是半自动人工校验?
2. Evidence card 的公开程度默认如何设计?
3. 用户上传材料是否允许进入能力地图?
4. 是否允许用户导入 LinkedIn export?
5. 是否做 AI-search visibility score?

### 11.3 商业问题

1. Pro 是否直接定 $20/月?
2. 免费层证据卡限制设为几张?
3. 是否允许早期用户 lifetime deal?
4. B 端机会通道按 intro 收费还是订阅收费?
5. 是否给用户机会收益分成?

---

## 12. 结语

V2 数据没有推翻 V1,而是把 V1 的方向收窄了。

真正可做的不是“职业身份产品”,而是一个更具体的东西:一个让 AI-augmented professionals 持续看见自己能力变化、沉淀真实工作证据、在合适时刻可控地对外开放的职业能力镜子。

这个产品的难点不在 AI 生成页面,也不在数据抓取,而在三个旧问题:

第一,用户为什么第一次愿意连接数据源。  
第二,用户为什么第二次回来。  
第三,用户为什么相信你不会把他卖给 B 端。

只要这三个问题没有被真实用户验证,就不要大规模开发。只要这三个问题被验证,这个方向就有机会成为 LinkedIn 之外的一层新职业基础设施。

---

## 附录 A:报告依赖的 V2 Phase 结论

- Phase 01:Newsletter 是成熟生态和高信任渠道,不是大众职业身份产品。
- Phase 02:职业身份正在“门面 / 客厅”分离;better LinkedIn 路线已被多次证伪。
- Phase 03:Marketing 可首切,Design 可差异化,Consulting 不适合冷启动。
- Phase 04:纯私密不利于 B 端,纯公开伤信任,应采用三层可见性。
- Phase 05:冷启动靠 KOL 和窄社区,PM signal 需要 12–18 个月。
- Phase 06:$20/月是合理价格锚;迁移不会发生;隐性被发现需求强。
- Phase 07:技术和合规决定产品必须走 user-initiated 路线。

## 附录 B:建议下一步文件

建议在仓库中继续补充 3 个文件:

1. `v2_mvp_spec.md` — 90 天 MVP 产品规格。
2. `v2_interview_script.md` — 用户访谈提纲。
3. `v2_data_compliance_architecture.md` — 数据授权、删除、导出、B 端调用架构。
