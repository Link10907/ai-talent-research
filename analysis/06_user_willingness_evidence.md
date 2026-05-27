# Phase 06 — 目标用户真实意愿的证据基础

> 模型选择:Opus(高复杂度归纳判断)
> 数据基础:5 个领域、44 个文件、71 条引用(V500–V570),Sonnet 收集
> 写作日期:2026-05-26

---

## TL;DR + 用户意愿模型一句话总结

**5 条核心判断,先看这里:**

1. **用户意愿模型骨架(一句话)**:目标用户(美国 tech/PM/设计/营销专业人士)**约 5–8% 会愿意付 $20/月**,换"AI 加持的可见性与匹配 + 周期化的职业洞察(career Wrapped)",**前提是**:(a) 数据贡献是连续小步而非一次性大块,(b) 可见性默认私密、可一键开关,(c) 产品有持续可观察的 ROI 信号(类 Cursor / Whoop 的"每日反馈"),(d) 破产/出售时数据销毁承诺写进合同。

2. **付费的真实价格锚已经迁移到 $20/月**。ChatGPT Plus、Claude Pro、Cursor、Perplexity Pro 都锁在 $20/月点位 [V511, V513, V514, V551]。这是 AI 时代新的"高频专业 SaaS"价格锚 — 高于 Spotify($10),低于 LinkedIn Premium Career($40)。低于 $20 用户感觉"不严肃",高于 $40 切个人 daily-use 心理上限。

3. **"迁移"几乎不会发生**。Mastodon 90% 注册账号不活跃 [V521, V563],Threads 启动 1 个月 DAU 跌 75% [V524],Bluesky 大选峰值后 likes 跌 64% [V523]。Read.cv [V516]、Polywork [V518]、Bento.me [V520] 三个"更好的 LinkedIn / 链接页"全部关停,**没有任何一个继任者承接用户**。用户不会从 LinkedIn 迁移到我们这里 — 他们只会**叠加**。

4. **"被发现"的隐性需求 5 倍于显性需求**。LinkedIn 220M 总 open-to-work 信号,其中只有 28–40M(约 18%)愿意公开打 #OpenToWork 徽章 [V509, V510]。**约 180M 用户(约 20% LinkedIn 会员)私下愿意被招聘者搜索,但拒绝向同事/朋友公开**。这是产品最大的杠杆点 — 任何把"social cost of being open"降到零的机制都能解锁 5 倍 latent supply。

5. **数据交换的成败定律已经清楚**:**连续反馈 > 一次性报告**(Whoop > 23andMe),**社交身份 > 私密健康**(Wrapped 病毒 > Whoop 年度报告无人晒),**默认私密+逐步 opt-in > 默认公开+一次同意**(Apple Health > Strava 默认 public),**清晰的二次使用披露 > 不透明企业交易**(GSK 事件埋下 23andMe 信任崩塌的种子 [V534, V535])。这四条直接构成我们数据合约的边界。

---

## 1. 付费意愿(按产品类分组,不按文件)

### 1.1 知识/课程类(Lenny、Maven、Reforge、Pavilion、Hampton)

| 产品 | 价格 | 用户/付费 | 完成/留存 | 引用 |
|---|---|---|---|---|
| Lenny's Newsletter | $15/月 = $150/年 | 1M 订阅,~18K 付费(2023),~4–5% 转化 | 无 | [V500, V501] |
| Maven 课程 | $500–$2,000/课 | 20K 学生(2025) | 75% 完成(cohort)vs 5–15% 自学 | [V527, V528] |
| Reforge 会员 | $1,995/年个人,$9,995/10 席 | 50K+ 会员 | 90% 收入来自订阅,15% YoY 增长 | [V529, V530, V549] |
| Pavilion(GTM 高管) | 不公开 | 10K+ | 不公开 | [V554] |
| Hampton(创始人) | $8,500/年 | 1,000+ 会员,$8M ARR | 5–8 人小组,高续费(隐含) | [V531, V532, V570] |

**信号**:
- Marketing/PM/GTM 类专业人士在课程/会员上付费意愿明确**强**,但有显著的"价格-完成率-粘性"梯度:
  - $150/年(Lenny):付费门槛低,4–5% 转化是健康行业基准
  - $2,000/年(Reforge):付费门槛已经是"职业投入",90% 收入来自订阅说明续费高
  - $8,500/年(Hampton):彻底变成"圈层入门费",1,000 个高净值用户撑 $8M ARR,小组化(5–8 人)是粘性核心
- **完成率断崖**:cohort-based 75–96% 完成 vs MOOC 5–15% [V527, V528]。意味着"asynchronous learning"作为产品是死的;professional 用户买的不是内容,是**社交承诺 + 时间表**。
- Lenny 的 bundle 策略($200/$350 多产品 bundle)单封 email $1M+ 收入 [V564] — 说明付费用户对"打包升级"非常 receptive,横向延伸空间大。

### 1.2 内容订阅类(Substack)

- Substack 平台:50M 活跃订阅,5M 付费 = **平台层 10% 转化** [V504]。
- 单个 publication 中位转化:**3%**(实测,非 Substack 宣传的 5–10%)[V503]。
- Tech niche 最高:**8%**;只有 top 20% publication 超过 5% [V503]。
- 头部分布:0.05% 创作者赚 $1M+;5M 付费但 100,000 publication 中只 17,000 有 recurring 收入 [V505]。

**信号**:付费意愿在 content 类**不算低,但 ARPU 分布极度长尾**。中位创作者实际付费转化 3%,远低于 Substack 自己宣传的 5–10%。对我们的意义:**"内容订阅"作为商业模式不要押在中位数,要押在 niche-top-quartile**(tech 8%)。

### 1.3 工具类(Figma、Notion、LinkedIn Premium)

| 产品 | 价格 | 付费转化/ARPU | 引用 |
|---|---|---|---|
| Figma | $12–45/编辑/月 | $749M 收入(2024),13M MAU,NDR 134%。**Org+Enterprise 占 70% 收入** | [V546, V547, V548] |
| Notion | $10–15/座/月 | 100M 用户,~4M 付费(~4% 付费率,行业估算) | [V555] |
| LinkedIn Premium | $40–170/月分级 | $2B+ 收入,175M Premium 订阅(估)— **LinkedIn 900M 会员中约 ~19% Premium** | [V506, V507, V508] |

**信号**:工具类付费转化 **3–5%**(Notion ~4%, Figma 隐含个人编辑席占 MAU 小比例),**ARPU $120–$540/年**。LinkedIn Premium 19% 渗透率是**离群值** — 因为它直接绑职业身份+招聘者通讯,效用是"必须",不是"想要"。

### 1.4 AI 类(ChatGPT、Claude、Cursor)

- **ChatGPT**:15.5M 付费(2024 末,从 5.8M 翻 3 倍)[V511];50M+ 付费(2025 H2)[V512];$20/月 Plus,$200→$100/月 Pro。**隐含转化:5%**(15.5M / ~300M 注册)。
- **Claude**:订阅人数不公开;~80% 收入来自 API/B2B,~20% 来自消费者订阅 [V515];2026 H1 付费翻倍 [V551]。
- **Cursor**:$20/月 Pro,360K+ 付费用户(2025 初),$4M→$1B ARR 18 个月 [V513, V514, V561]。**36% freemium 转化** — 完全是 outlier。

**关键发现(也是 Phase 06 最重要的发现)**:Cursor 36% 转化 vs 行业 freemium 2–5% **不是因为 AI 神奇,而是因为 ROI 在第一次使用时即刻可见**(代码补全马上看到 productivity 增益)。同样是 $20/月,ChatGPT Plus 只有 ~5% 转化,因为价值更分散。**这给我们的隐含 lesson:转化率不取决于品类,取决于"用户多快感受到 ROI"。**

### 1.5 对我们定价的综合建议(300 字)

把上面四组合在一起看,**对我们的定价含义**:

- **价格锚就是 $20/月**。不要选 $5、不要选 $50。$20 是 ChatGPT、Claude、Cursor、Perplexity Pro、近似 LinkedIn Premium Career 入门档(实际 $40 但促销 $20 常见)、近似 Whoop 中档($16–$20/月)的密集锚点。任何高于 $20 的定价需要专门论证为什么用户接受。
- **免费层是默认**。LinkedIn、Wellfound、GitHub、Substack 都是 free-as-default 才能让"被发现"机制运转。付费是给"想被更精准匹配/想看洞察/想去除限速"的高意愿用户。
- **预期付费转化区间:3–8%**(基础场景,类似 Substack tech niche、Notion、ChatGPT Plus)。**目标值:8–15%**(类似 Lenny 顶部 + Cursor 因素,需要做到"ROI 即刻可见")。
- **不要照搬 Cursor 的 36%**(那是 outlier,需要 IDE 那种秒级生产力反馈,我们做不到)。
- **Team / Enterprise tier 必要**。Figma 70% 收入来自 Org+Enterprise [V546];我们要为 B2B 招聘端预留 $500–$2,000/座/年定价空间(类 Reforge Teams 模型)。这才是规模化营收 — 个人付费是 top-of-funnel + lock-in。

---

## 2. 迁移意愿(关键发现:迁移几乎不发生)

### 2.1 5 个"X 替代品"案例数据

| 平台 | 触发事件 | 峰值 | 留存 | 引用 |
|---|---|---|---|---|
| Mastodon | Musk 收购 X(Nov 2022) | 5.8M 注册,1.8M MAU(2022 末);75K 新增/日 | **10.5M 注册,~1M MAU = 90% 弃用** | [V521, V563] |
| Threads | Meta 启动 + IG 整合(Jul 2023) | 41M DAU 首日,100M 用户 1 个月 | 1 个月后 DAU 跌 75% 到 10.3M;2025 恢复到 400M MAU/150M DAU(靠 IG 持续灌注)| [V524, V560] |
| Bluesky | 美国大选 + X 政策(Nov 2024) | 13M→27M 6 周内;Nov 18 峰值 2.79M likes/日 | June 2025 跌到 998K likes/日 = **-64%** | [V522, V523, V559] |
| Read.cv | 自然死亡(Perplexity 收购团队后关停 May 2025) | 用户数从未公开 | **用户分散,无单一继任者** | [V516, V517] |
| Polywork | 转 website builder 失败,关停 Jan 2025 | 用户数从未公开,$13M 融资退还投资人 | 用户分散到 LinkedIn / 个人站 | [V518, V519] |
| Bento.me | Linktree 收购后弃养,关停 Feb 2026 | 用户数从未公开 | 分散到 Linktree / Carrd / 个人站 | [V520] |
| Twitter→Substack | 2022–2024 持续 | Substack ~1M→5M 付费 4 年 4× 增长 | **是 spillover 不是替代** — 创作者保留 X presence 同时迁移付费层 | [V525, V504] |

### 2.2 综合 lessons

**5 个迁移案例平均留存约 10–25%。重点不是数字,而是模式**:

1. **迁移是 event-driven 不是 product-driven**。Mastodon 因 Musk 收购涨,Bluesky 因大选涨,Threads 因 IG 灌注涨。**没有任何一个平台是因为"产品更好"涨的**。
2. **"更好的 LinkedIn"是产品坟场**。Read.cv [V516]、Polywork [V518] 都死了。Bento.me [V520] 这种"更美的链接页"也死了。**没有 LinkedIn killer 成功过**。原因:LinkedIn 的护城河是双边网络(求职者 + 招聘者 + 商务联系)+ 数据沉淀(简历就是个人资本),aesthetic differentiation alone 无法穿透。
3. **Twitter→Substack 是少见的成功迁移 — 因为它不是替代,而是 spillover**。Creators 没有"离开 X",他们用 X 做 top-of-funnel,把付费层挪到 Substack。**用户保留了原平台的网络效应,只把"变现层"换了**。
4. **关停后用户不去单一继任者,而是分散**。Read.cv 关停后用户去了 LinkedIn / Threads / 个人站,**没有任何产品承接整批用户**。意味着"等竞品死了我捡用户"是 fallacy。

### 2.3 对我们的含义(200 字)

我们**不能假设用户会"迁移"**。这是 Phase 06 最硬的一个 reality check。具体含义:

- 不要做"better LinkedIn"。设计师/PM/marketer 不会因为我们 UI 漂亮就迁移。
- 必须是**附加层**(类似 Substack 之于 X — 用户保留 LinkedIn 资料,把某个特定功能挪到我们这里)。**那个"特定功能"是什么是 Phase 08 必须回答的设计问题**。候选:AI-driven 匹配 / 半私密的"被发现"信道 / 周期性 career Wrapped / 项目级 portfolio。
- 或者:**替代一个不存在的 thing**。Cursor 不替代 VS Code(很多人同时用),Substack 不替代 Twitter,Notion 不替代 Google Docs(开始时)。我们要找的是 LinkedIn **不能**做的事 — 比如"私密 + AI 解释的匹配","按项目而非按职位的能力呈现","非求职状态下的被动可见"。

---

## 3. "被发现"诉求强度

### 3.1 核心证据:5:1 比

**LinkedIn 数据(2024–2025 官方/CNBC)** [V509, V510]:
- 总 open-to-work 信号:**220M+**(35% YoY)
- 公开 #OpenToWork 徽章:**28–40M**(约 18% 显性 / 占 LinkedIn 900M 会员的 3–4%)
- 私下"open to recruiters"(仅招聘者后台可见):**~180–200M**(约 22% LinkedIn 会员)
- **比例**:私下 ÷ 公开 ≈ **5:1**
- 使用徽章 → 招聘者联系率翻倍 [V509]

### 3.2 其他平台

- **Wellfound**:12M 候选人,**100% 公开 open-to-work**(平台设计强制)[V526, V568]。
- **GitHub "Available for hire"**:估算 2–5% 活跃开发者用 — 没有官方数据 [hire_me_tags.md]。
- **X bio "open to opportunities"**:估算 1–3% 技术账号 — 没有数据 [V x_bio]。

### 3.3 关键 insight 与对我们的含义

**关键发现:社交成本压制了 80% 的 latent supply**。

- 180M 用户私下愿意被找,但公开会"显得 desperate" — 这是 LinkedIn 反复尝试 destigmatize 但只缓解部分的根本问题。
- Wellfound 12M 100% 公开,**证明只要平台 context 本身是"找工作 native",social risk 就消失**(因为没有同事/老板在那里看到你)。这是产品设计的关键杠杆。

**对我们的产品含义**:
- 任何"零社交成本"的可见性机制能解锁 **5x latent supply**。具体可能形态:
  1. **半私密信道**:个人资料默认对招聘者方可见 + AI 匹配,对同事/朋友隐藏(LinkedIn 已部分这样做但不彻底)。
  2. **"非求职状态下的被发现"**:用户不打"open to work"标签,而是展示"我做过什么项目 / 我用什么 AI 工具 / 我擅长什么",由 AI 主动匹配,**不需要用户主动 signal availability**。这绕开了 stigma。
  3. **Context-isolated visibility**:像 Wellfound 一样,平台本身的语境就是"匹配",所以打开 = 默认可见,不打开 = 完全不在。中间没有"既要又要"的尴尬。

**风险点**:解决了 social risk,**就解决了产品的根本机会**。如果做不到,我们只是另一个 LinkedIn 复制品。

---

## 4. niche 工具 + 社区留存

### 4.1 数据

| 平台 | 模型 | 留存指标 | 引用 |
|---|---|---|---|
| Maven cohort | 4–6 周直播课 | 75% 完成 | [V527, V528] |
| Lenny's Slack | 付费订阅赠送 | 30K+ 成员,DAU 未公开;estimated 健康社区 DAU/MAU 10–20% | [lenny_slack.md] |
| Reforge | 年会员 | 50K+ 会员,90% 收入续费,15% YoY 增长 | [V530] |
| Hampton | $8.5K/年 + 5–8 人小组 | 1,000+ 会员,$8M ARR,小组化高续费(隐含) | [V531, V532] |
| South Park Commons | 6 个月驻留,基金支持免费 | 1,000+ 历史成员,70% 创业 | [V533, V556] |
| Indie Hackers | 免费论坛 | 500K–1M 月访问(估),DAU 未公开;2022 后衰落 | [indie_hackers.md] |
| Product Hunt | 免费 launch | 4–5M 月访问,但是 **launch 渠道不是留存平台**;30 天留存 1–5% | [product_hunt.md] |

### 4.2 模式

- **付费 + 小组 = 高留存**(Hampton, Maven cohort, Reforge)。
- **免费论坛留存差且不可持续**(Indie Hackers, Product Hunt)。
- **DAU 不是关键指标 — 专业社区不应该追求 DAU**。Lenny 的 Slack、Hampton 的小组、Reforge 的课程 — 用户**不需要每天来**,但每月来 4–8 次就足够维持价值感。
- **重要的不是日活,而是"在用户需要时,我们是 default"**。Lenny 找新工作 → 进 Slack 看 job board。Hampton 月度 → 小组聚会。Reforge 季度 → 升级技能。

### 4.3 对我们的含义

- **不要追 DAU 数据 — 我们的用户是高价值低频用户**。专业人士不会每天打开"职业平台",但会在职业决策点(找工作、跳槽、起新项目)集中使用。
- **MAU 是合适指标,但加权"决策点 MAU"更准**。
- **付费的留存机制不是内容(内容会衰减),是社区或匹配**。Lenny 留存靠 Slack [lenny_slack.md];Hampton 留存靠小组 [V531];Cursor 留存靠"每次写代码必用"。我们的留存机制是什么?候选:AI 主动给的匹配通知 / 半年一次的 career Wrapped / 项目协作工具内嵌。

---

## 5. 数据交换意愿(重点)

### 5.1 五个案例的核心数据

| 产品 | 用户给 | 用户得 | 同意率/规模 | 反弹 | 引用 |
|---|---|---|---|---|---|
| 23andMe | DNA 样本 | 一次性祖源+健康报告 | 15M 用户,**80% opt-in 研究** | **灾难** — 2025 破产,15M 基因数据被 TTAM $305M 买走,28 州 AG 提起诉讼,用户无法删除 | [V534, V535, V536, V537, V566, V569] |
| Strava | 持续 GPS + 心率 + 路径 | 朋友比赛 + Segments + Kudos | 180M 注册,2% 付费 | **小到中等** — 2018 军事基地泄露事件;隐私评分 F(32/100)[V539];默认 public 引发持续抱怨 | [V538, V539, V540, V552] |
| Whoop | 24/7 生物特征 | 每日 Recovery + Strain 评分 | 2.5M 付费成员,$200–360/年 | **几乎没有** — 用户付费且没有 negative event | [V541, V542, V565] |
| Apple Health | 多类健康数据 | 自查 + 选择性分享 | 1B+ iPhone 用户(被动安装);ResearchKit 心脏研究 400K+ 主动报名 | **几乎没有** — 默认 on-device 不上云,信任最高 | [apple_health.md] |
| Spotify Wrapped | 12 个月听歌历史 | 年度个性化故事 | **200M 24 小时内打开**(2024),250M 3 天内(2025) | **零** — 反而是 PR 财富 | [V543, V544, V545, V567] |

### 5.2 五条 lessons(直接构成我们数据合约的边界)

**Lesson 1(23andMe):同意是 context-bound 不可转移,bankruptcy 风险必须设计进产品**

23andMe 用户当初同意"为了拿到基因报告,提供 DNA + 80% opt-in 研究"。他们**没有**同意"破产时被卖给买家"。但隐私条款里写了 [V536, V537],法律上 binding,实际上 catastrophic。Harvard Gazette 和 NEJM 都明说:**联邦法律对私营公司的基因数据保护不足** [V536, V537]。28 州 AG 提起诉讼试图阻止 [V553]。

→ **对我们**:用户同意"AI 看我的项目数据来匹配工作"≠ 同意"被卖给猎头 SaaS"。必须在产品端:
- 数据使用范围 explicitly enumerated,改变 use case 必须 re-consent。
- **破产/出售时的数据销毁承诺必须在 ToS 里 explicit、可执行**。
- 提供持续可用的"导出 + 删除"按钮,且实测可用(23andMe 用户在破产中报告无法删除是信任崩塌的导火索)。

**Lesson 2(Strava):默认 public 是短期增长长期债务**

Strava 默认 activities public [V540],换来快速 social graph growth 和 leaderboard 病毒性,但**隐私评分 F** [V539] 是长期债务。**军事基地事件** [V538] 显示一旦"隐藏的二次使用"曝光,反弹强烈。

→ **对我们**:任何 visibility 设计的**默认值要保守**(默认私密,主动 opt-in 公开),否则会复制 LinkedIn OpenToWork 的"显得 desperate"问题。

**Lesson 3(Whoop):连续反馈使用户愿意付费 + 持续给数据**

Whoop 2.5M 用户 $200–360/年,**几乎没有 backlash** [V541, V542]。原因:每天看到 Recovery 评分 = data 的价值连续可见。

→ **对我们**:用户给我们数据(项目、技能、工作流)必须**每天或每周返回价值**。一次性年度报告不够(那是 Spotify 的玩法,见 Lesson 5)。**候选机制**:每周 AI matching summary(类似 Cursor 每次写代码即刻反馈),每月技能成长报告,每次 AI 摘要"你这个项目用上的能力"。

**Lesson 4(Apple Health):默认私密+逐步 opt-in 反而让用户给更多**

Apple Health 默认数据**留在设备上**不上云 [apple_health.md]。结果:用户信任最高,愿意往里塞更多数据(ResearchKit 心脏研究 400K+ 报名)。**但变现路径几乎没有** — Apple 不卖数据 / 不基于数据做广告,所以变现靠硬件,不靠数据。

→ **对我们**:privacy-first 设计能 unlock 更多数据贡献,但**必须在产品架构上想清楚变现路径不依赖数据出售**。变现靠订阅(用户付钱看 AI 洞察)或 B2B 招聘端订阅(招聘者付钱用 AI 搜索)— 不靠卖数据。

**Lesson 5(Spotify Wrapped):surveillance reframed as gift — 给我们的最大灵感**

12 个月持续听歌监控,被包装成年度礼物,200M 用户 24 小时打开 + 500M 分享 [V543, V544]。**这是数据收集的最佳公关化** — 用户不感觉被监控,只感觉得到 identity confirmation。原因:
1. 音乐 = identity signal,可炫耀
2. 故事化呈现 + 出人意料的具体性("4,382 分钟")
3. FOMO(12 月所有人都在分享)
4. 零额外努力(数据已经收集)

→ **对我们**:做一个 **"Career Wrapped"** 是几乎免费的产品杠杆。每年 12 月:"You shipped X projects, used Y AI tools, your top skill was Z" — 这类似 GitHub 年度 PR 数据,可分享到 LinkedIn。**它把"surveillance"重新框架成"gift",**且是 viral 渠道。Phase 08 应该把这个作为 candidate feature。

### 5.3 我们的数据交换合约的具体设计(400 字)

基于以上 5 条 lessons,我们的数据合约必须满足:

**a. 数据类型分级 — 明确收什么、不收什么**
- **收(默认):公开产出**(GitHub 项目、blog post、portfolio 链接)、**自报技能与目标**(用户主动填的能力/愿意做的工作)。这些用户已经在公开,我们只是聚合 + AI 解读。
- **可选 opt-in:私密工作流**(允许我们读用户 IDE/Notion/Figma 元数据来推断"实际在做什么")。这是产品最有差异化的能力来源,但**只能 explicit opt-in**,且每次新增数据源必须单独授权。
- **不收**:雇主邮件、薪水(自报除外)、当前公司内部文档。任何会"威胁到当前雇主关系"的数据是红线 — 这是用户最不愿付出的(类比:Strava 默认 public 引发的"为什么我同事看得到我去哪儿"问题)。

**b. 我们给用户什么**
- **持续(每周/每月)**:AI matching 通知("有 3 个 role 匹配你最近 3 个月做的项目")。
- **半周期(每季度)**:技能成长报告(类 Whoop monthly review)。
- **年度(12 月)**:Career Wrapped(类 Spotify Wrapped)— 主推社交分享机制。
- **随时**:免费用户也能看到的"你在 talent pool 中的位置"(类似 Github contribution graph)。

**c. Transparency 必须 visible 不能 footer**
- 首页明显的"我们看你的什么数据 / 谁能看到 / 你随时能关闭"面板,不藏在 settings 第 4 级菜单。
- 每次数据被用于 AI 匹配,**告诉用户**(类似 LinkedIn 的"someone viewed your profile")— 让用户**看到** AI 在做什么。这是 Apple-style 的 trust building。

**d. 终止 / bankruptcy 条款**
- 用户随时可一键导出全部数据(JSON + human-readable)。
- 公司被收购/破产时,**默认行为是销毁所有 raw data**,只保留用户**主动选择保留**的衍生数据(类似 PoA: power of attorney)。
- 这一条**写进 ToS 第 1 页**,且产品页面有专门 trust 页面解释。**这是 23andMe 没做、我们必须做的事**。

证据强度:medium-high(基于 23andMe / Strava / Whoop / Spotify / Apple 5 个明确案例)。

---

## 6. 用户意愿模型 — 综合(Phase 06 最核心产出)

### 6.1 付费意愿模型

> **目标用户中约 5–8% 会愿意付 $20/月 换"AI matching + 周期化职业洞察 + 可见性管理"**。
> 价格锚 $20/月(AI 时代新常态)。年付选项 $200/年(8.3% 折扣,标准做法)。
> Team / B2B 招聘端订阅:$500–$2,000/座/年(类 Reforge Teams 模型),这是规模化营收来源。

**分人群拆分**:
- 高意愿付费用户(8–15% 转化潜力):正在或考虑换工作 + 受过 AI 工具教育 + 收入 $100K+ 的 tech/PM/设计/营销专业人士。约目标人群的 15–25%。
- 中意愿付费用户(3–5% 转化潜力):有职业焦虑但不主动找工作的同类人群。约目标人群的 40–50%。
- 低意愿付费用户(<1% 转化潜力):仅用免费层、不分享数据、不愿可见的用户。

**证据强度:high**(基于 Cursor [V513]、ChatGPT [V511]、Substack tech niche [V503]、Lenny [V500]、LinkedIn Premium [V506] 多源交叉)。

**反偏误声明**:
- ChatGPT/Cursor 是"日常 daily-use 工具"。我们如果是"低频职业平台",转化率可能更接近 LinkedIn Premium(2.5–5% 估)。
- 5–8% 是**上端估计**;保守取 3% 是合理的 floor。
- Team 端 $500–$2,000 区间假设我们做 B2B 招聘端 — 如果纯 C2C,这条不成立。

### 6.2 数据贡献意愿模型

> **用户愿意贡献"公开产出 + 自报技能 + 项目元数据"**,换"AI 解读的可见性 + 持续匹配通知 + 年度 Wrapped",**前提是**:
> (1) **逐步 opt-in,不要 all-at-once**(Apple Health 模型,反 23andMe 一次性 80% opt-in 模型)。
> (2) **每周/每月有看得见的反馈**(Whoop 模型,反 23andMe 一次性报告)。
> (3) **二次使用边界 explicit**(GSK 事件埋雷,我们必须避免)。
> (4) **破产/出售时数据销毁承诺写进 ToS 第 1 页**。
>
> **不愿贡献的红线**:
> - 当前雇主邮件、内部文档(会威胁现有工作)
> - 精确薪水(自报除外)
> - 可被同事/老板检索到的"open to work"状态(reset Phase 6.3)

**证据强度:medium-high**。基于 23andMe(灾难) / Strava(部分负反馈) / Whoop(成功) / Apple Health(成功) / Spotify(成功)5 个明确案例。**不确定性**:这些案例都是 B2C consumer 数据,**职业数据是否同样敏感未经验证**。我的判断是**职业数据对当前雇主关系敏感(类 DNA 对家族关系敏感),但对陌生招聘者反而不敏感**(类音乐对陌生人不敏感)。

### 6.3 公开意愿强度分布

> 在目标用户中(美国 tech/PM/设计/营销专业人士):
> - **~3–5% 用户**愿主动公开展示"open to work"或 portfolio,**不在乎社交成本**。(基于 LinkedIn 公开徽章 3–4% [V509, V510])
> - **~20–25% 用户**接受 **passive 被招聘者搜索到**,但不愿对同事/老板可见。(基于 LinkedIn 私下 open-to-work 22%)
> - **~70–75% 用户**默认拒绝任何 visibility,但会在特定生命周期事件(被裁、跳槽 trigger)时**短期切换**到上面 2 个类别。

**关键比例:5:1 latent:visible**(LinkedIn 数据 [V509, V510])。任何把 social cost 降到零的机制能解锁这 5×。

**证据强度:medium-high**(LinkedIn 是直接数据;Wellfound 12M 100% 公开是 context-isolated 实证 [V526])。
**不确定性**:LinkedIn 数据混合了所有职业类别。**Tech / 创意类用户的公开意愿可能更高**(GitHub 文化、X 文化、Read.cv 受欢迎说明 5% 估值可能偏低,真值可能 8–12%)。

### 6.4 迁移成本模型

> **"迁移"几乎不发生**(Mastodon 90% 弃用 [V521, V563],Threads 75% 首月 DAU 跌 [V524],Bluesky 64% 后续 likes 跌 [V523],Read.cv/Polywork/Bento 全部死亡且无继任者)。
>
> **"附加"可能发生**,if:
> (1) 我们提供 LinkedIn **不能**做的事(私密 AI matching、项目级 portfolio、半私密可见性),
> (2) 加入成本是 < 5 分钟(类 Cursor "open VS Code style"),
> (3) 不要求用户立即弃 LinkedIn,而是 LinkedIn 之外的补充(类 Substack 之于 X)。
>
> **"替代不存在的 thing"是唯一突破口**:
> - 不存在的 thing 候选 A:"AI explained matching"(LinkedIn 招聘者不会解释为什么推荐你)
> - 不存在的 thing 候选 B:"Project-level rather than role-level identity"(LinkedIn 是 title,我们是 portfolio)
> - 不存在的 thing 候选 C:"Half-private discoverability"(默认仅 AI 搜索可见,opt-in 才公开)

**证据强度:high**(基于 5 个失败案例 + 1 个成功 spillover 案例,模式一致)。

### 6.5 模型间的 trade-off

四个子模型有内部张力,**Phase 08 必须做的取舍**:

- **付费(5–8%)需要"daily ROI"**(类 Cursor)。**但职业平台天然低频**。→ 取舍:做"高频功能 hook"(AI 工作流嵌入)或者接受 3% 转化做大基数。
- **数据贡献(深度 opt-in)需要持续反馈**。**但持续反馈需要持续数据**。→ chicken-and-egg,启动期需要"轻量数据 + 重量反馈"(类 Cursor:只要打开 IDE 就反馈)。
- **公开意愿低(5%) vs 隐性需求高(25%)** → 必须设计"private-default, AI-mediated discovery",这是产品的核心 wedge。
- **迁移不发生 + 必须附加** → 必须 import LinkedIn / GitHub / Notion 等数据,不要让用户从头填资料。

---

## 7. 对我们产品的启示

**启示 1:定价锁定 $20/月,但不要靠它生存**
- 个人付费 $20/月 × 5% 转化 = top-of-funnel,不是商业模式核心。
- 核心营收应是 B2B 招聘端订阅($500–$2,000/座/年,Reforge Teams 模型)。
- **反对意见**:如果我们只做 C 端,$20/月 × 100K 付费用户 = $24M ARR,够大。但 100K 付费用户需要 1.5M+ 免费用户 — 在没有 LinkedIn 级别 distribution 的情况下难达到。结论:**C+B 双端是更稳妥路径**。

**启示 2:核心 wedge = "Private-default, AI-mediated discoverability"**
- 用户**默认私密**,**AI 在用户授权范围内**主动匹配 jobs/人/项目。
- 用户**永远看不到"open to work"按钮**(因为有 stigma),而是"What I'm building" / "What I'm interested in" — 由 AI 翻译成 matching signal。
- **反对意见**:用户不主动 signal,招聘者怎么找到他们?答:招聘者搜索是 AI-driven semantic match,不是按 boolean filter。这是 AI 时代独有的能力,LinkedIn 难复制(他们的 graph 太老,AI infra 是 bolt-on)。

**启示 3:Career Wrapped 是必须做的 viral 杠杆**
- Spotify Wrapped 模型 [V543, V544, V545] 几乎免费但 viral 极强。
- 我们的 Wrapped:用户一年的项目 / AI 工具使用 / skill 成长 → 1 个 shareable story。
- **反对意见**:第一年没有足够 data 做 Wrapped。答:可以 import GitHub / LinkedIn 历史一次性补齐,且年度 release 是 12 月,我们如果 Q1 启动,12 月正好首发。

**启示 4:Cohort / 小组化 community 是 retention 杠杆**
- Lenny's Slack [lenny_slack.md] / Hampton 小组 [V531] / Maven cohort [V527] 都证明小组化 retention 强。
- 不要做 Indie Hackers 式开放论坛(衰落且 DAU 难维持)。
- **反对意见**:小组化运营成本高,需要 community manager。答:启动期接受这个成本,把它包进高单价 tier(类似 Hampton);中长期通过 AI 工具(自动推荐小组、AI 摘要讨论)降本。

**启示 5:数据合约写在 ToS 第 1 页**
- 23andMe 教训 [V534, V536, V537]:数据归属、二次使用边界、破产销毁承诺,**全写进 ToS 第 1 页 + 主页 trust 板块**。
- 这是产品最容易但最 underrated 的差异化 — 因为 LinkedIn 没做,Wellfound 没做,我们做了就拿走"trust" positioning。
- **反对意见**:这种 transparency 会限制未来商业灵活性(比如未来想训练 AI 模型)。答:把"用户数据 anonymized 用于产品改进 / AI 训练"明确列在 ToS,**不要 surprise**,用户接受度反而高(Apple Health 模式 [apple_health.md])。

---

## 8. 调研局限性

1. **留存数据多为非公开**。Mastodon 90% 弃用是粗略测算(注册 ÷ MAU),Indie Hackers / Product Hunt / Lenny's Slack 都没有真实 DAU/MAU。Hampton 续费率从未披露,只能从"$8M ARR ÷ 1K × $8,500"反推。我们的模型在 retention 数字上**置信区间宽**。
2. **Cursor 36% 转化是极端 outlier**[V513]。AI 编辑器的 ROI 即刻可见性是独特的;不能假设我们也能做到。**保守假设付费转化 3–5%**,8% 是 stretch 目标。
3. **23andMe 是 DNA 类敏感数据,职业数据是不是同样敏感未知**。我的判断(职业数据对当前雇主关系敏感,对陌生招聘者不敏感)需要 Phase 07/08 用户访谈验证。
4. **公开人物 / B2C SaaS 数据不直接适用于专业人群**。Spotify / Strava / Whoop 用户 ≠ 我们的"专业 tech/PM/设计/营销"用户。专业人群对"被同事看到"的敏感度可能比一般消费者高得多 — 隐含的"职业 stake"提高了 social risk。
5. **数据多为美国市场**。LinkedIn 数据是全球,但 220M open-to-work 信号没有按地区拆分;Substack / Cursor / ChatGPT 偏美国;中国 / 印度 / 欧洲 willingness 可能差异显著。**目前模型仅适用美国 + 英语 tier-1 市场**。
6. **2026 H1 时点**:AI 工具付费爆发期。$20/月锚定可能在 1–2 年内随着 AI 工具竞争压价而下移到 $10–15。模型需要每年 review。

---

*本报告基于 71 条引用 [V500–V570],5 个 raw_data 子目录共 24 个文件 + 1 个 collector draft。所有数字带来源 ID。证据强度区分 high/medium/low/inferred。Phase 04 已交付,本报告作为 Phase 08(产品设计)的 user-willingness 约束输入。*
