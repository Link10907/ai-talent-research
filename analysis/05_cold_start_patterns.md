# Phase 05 — 类似产品的冷启动真实路径

## TL;DR + 冷启动核心建议

我们的产品是"让欧美 Marketing / Design / Consulting 专业人士主动贡献职业产出"。在 9 个历史案例(4 成功 + 5 失败)拆解后,五条最关键判断如下,直接喂给决策。

**1. 第一批 100/1000 用户最可能从哪里来。** 不是 Product Hunt,不是 LinkedIn 公开 launch。是 **Lenny's Newsletter / MKT1 / Justin Welsh 的付费订户名单**(Marketing)+ **Dive Club / Femke van Schoonhoven 的 Maven 学员群**(Design)+ **Tom Critchlow / Paul Millerd 的 indie consultant newsletter 圈**(Consulting)。这是三个互不重叠、对"职业身份新工具"高敏感、又已被 KOL 反复"软化"过的窄社区。100 用户从 founder 自己 + 5 个 KOL 的朋友圈拿(GitHub 模式 [V400]、LinkedIn 模式 [V405]);1000 用户从 5 个 KOL 的 newsletter 一次性推送拿(Substack-Bishop 模式 [V404])。

**2. 邀请制 vs 公开注册。** **走"半邀请制":waitlist + KOL 携带式邀请,但不设 18 个月窗口。** 邀请制的本意是制造稀缺 + 控质量,但 Polywork 把它做成了 18 个月的私测黑洞,出来的时候 hype 已凉 [V411]。Substack 早期对"作者"侧邀请,对"读者"侧公开 [V404],这才是对的拆分。我们应该:**B 端(profile 被消费方)邀请制**,**C 端(贡献者)6 个月内向公开切换**,触发条件是 DAU/WAU > 25% 或第 200 个非 KOL 关系自然注册。

**3. 从 0 到 PM signal 时间窗。** 基于 GitHub 14 个月到 10 万用户 [V401]、LinkedIn 15 个月到 100 万 [V405]、Strava 头两年纯本地圈 [V403]、Substack 用 14 个月到 11K 付费订户 [V404] —— 真正 PM signal **最早 9 个月、合理 12-18 个月、悲观 24+ 个月**。承认不确定性:LinkedIn 是创始人 personal network 加成最大值,我们大概率拿不到那个 floor。

**4. 所需资金。** 6 个月 MVP + 12 个月冷启动 = **$1.5M-$3M**(团队 5-7 人,工程占 60%,内容/KOL outreach 占 20%,运营/合规占 20%)。这是 GitHub 早期 $0 VC [V402] 和 Substack 种子轮 ~$2M 之间的合理位置。Polywork $44.5M 和 Path $66.2M 的钱都没救活它们 [V411][V416]—— 资金不是核心瓶颈。

**5. 最可能死在哪一环。** 不是工程、不是融资。是**"激活贡献者发布第一条内容"和"第二条内容之间的 retention gap"**。Lunchclub 死于 transactional utility 无 retention [V414];Polywork 死于 vanity post → 没二次回访 [V409];Read.cv 死于 portfolio 静态展示无 daily loop [V412]。我们的死因画像 90% 在这条上。

---

## 1. 成功案例真实还原

四个成功案例没有任何一个是"产品好 → 用户来"。都是 founder 把分发问题先解决,产品才有机会被看见。

### GitHub(2007-2012):founder 已经是 Ruby 圈居民

Tom Preston-Werner 和 Chris Wanstrath 在 GitHub 之前就是 Ruby/Rails 社区里抱怨 contribution 流程的人,不是"看到机会"的外来者 [V402]。2008 年 4 月 10 日公开 launch 之前,他们花了 6 个月闭测,第一批用户全是个人朋友 [V402]。**真正的 jet fuel 是 RailsConf 2008(波特兰):四个创始人各自占一个 talk slot,在 Engine Yard 摊位发 t-shirt,然后 Rails 框架本身从 Subversion 迁移到 Git 并把仓库放上 GitHub** [V400]。这一步把 GitHub 从"一个 Ruby 圈的小工具"变成了"Ruby 圈的官方仓库托管"。第一付费用户 Geoffrey Grosenbach 是主动来要付费的 [V402],freemium 是被动反应不是预谋。100K 用户用了 14 个月,1M repo 用了 27 个月 [V401],a16z 那 $100M Series A 等到 2012 年才有 [V402]。**Lesson:cold start 要求 founder 自己就是社区成员 + 找到一个"承载体"项目把社区一次性灌入。**

### Strava(2008-2012):窄人群 + 真实社交 segment

Mark Gainey 和 Michael Horvath 是 Harvard 划船队队友,1995 年就写过"运动员虚拟更衣室"商业计划但技术不成熟 [V403]。2008 年 7 月环法期间,**他们用 Garmin GPS 招了 20 个 cyclist 朋友** [V403]。整个 2009 年"六个创始人手动给朋友注册账号,因为 self-signup 都没做完" [V403]。Segments 功能不是 spec,是从用户聊"哪段爬坡是经典"的对话里冒出来的 [V403]—— 即 Kitchel 90 年代末记得的一个本地车队非官方爬坡赛。Strava 用了 5 年才在 2011 年上手机 app,2012 年才加跑步从而把 TAM 扩大 3 倍 [V420]。"Inch wide, mile deep" 是创始人原话 [V403]。**Lesson:窄到不能再窄(SF cycling = MAMIL = 中年 lycra 男)+ 慢到不能再慢(5 年才扩品类)。** 同样是 cold start,这是"用户行为洞察"路线,不是"网络效应"路线。

### LinkedIn 早期(2003-2008):PayPal Mafia 的人际资本兑现

LinkedIn 2003 年 5 月 5 日 launch 第一天有 4500 用户,几乎全是 5 个 co-founder 的个人 + 职业关系 [V405][V406]。Reid Hoffman 是 PayPal 前 COO,Peter Thiel 是早期投资人 [V405]。15 个月到 100 万用户 [V405] —— 在所有 9 个案例里这是最快的,因为 Hoffman 的"启动加速度"是其他所有创始人都没有的。**真正的商业胜利在 2008 年 3 月 Recruiter 产品上线** [V407]—— 那是 5 年后的事,不是 cold start 阶段的事。早期是邀请机制驱动的纯增长,profitability 第一个月是 2006 年 3 月 [V405]。**Lesson:professional network 产品的 cold start = founder 的人际资本。**

> **对我们的诚实评估:** Reader 是 B2B AI recruiting 平台的 founder,在中国 / 英文圈 talent acquisition 圈有人脉,在欧美 marketing/design/consulting 创作者圈基本是观察者,不是居民。这是结构性短板,只能用"借力 KOL"补救,无法靠创始人 personal network 复制 LinkedIn 模式。

### Substack(2017-2021):Day 1 把巨型 power user 拉上船

Hamish McKenzie 是前 PandoDaily 记者,有媒体圈关系。**2017 年 10 月 18 日,他说服 Bill Bishop(Sinocism 中国新闻 newsletter,30K 订户)把付费墙搬到 Substack,Bishop 当天发邮件给 30K 订户,六位数收入当天到账** [V404]。这一击同时验证了 10% take rate 模型 + 给了创始人"我们能拿大牌"的 case story。后续 a16z 钱的一部分明确花在挖知名作者(Glenn Greenwald / Matt Taibbi / Matt Yglesias / Andrew Sullivan)[V404][V408]。付费订户从 11K(2018 年 7 月)→ 100K(2020 年 8 月)→ 1M(2021 年 11 月)[V404]。**Lesson:cold start 的 power user 必须自带 audience,产品只需要不挡道(10% 抽成、订户名单可导出 [V404])。** 这跟 Strava 路线相反 —— Strava 是 20 个无名 cyclist,Substack 是 1 个 30K-audience 写手。

### 综合 pattern

四个案例的共同结构:**creator-founder fit(founder 是社区里的人,或至少有强联系)+ 窄到极致的初始切入(Ruby / SF cycling / PayPal mafia / 中国新闻读者)+ 早期不是产品胜利,是分发胜利**。GitHub 靠 Rails 迁仓,LinkedIn 靠 Hoffman 通讯录,Substack 靠 Bishop 一封邮件。**三个都把第一个"可分发载体"押对了。** 慢是共性 —— 没有一个在 launch 24 个月内做到 100 万贡献者级别,LinkedIn 那种 15 个月到 100 万是 reader-side 计数,不是 contributor-side。我们的产品像 Substack-contributor side,不像 LinkedIn-reader side,这点对时间预期至关重要。

---

## 2. 失败案例真实还原

五个失败案例不是单一死因。把它们摆在一起看,会发现 cold start 的 failure mode 高度结构化。

### Polywork(2021-2025):$44.5M、18 个月闭测、pivot 失败

Peter Johnston 2021 年创立 [V409]。**2021 年靠 invite-only waitlist 制造 hype,拿到 Product Hunt Golden Kitty Award 2022** [V409]。2022 年 9 月 launch 出私测 + Caffeinated Capital 领投 $28M Series B [V411],累计融资约 $41.5-44.5M。投资人阵容豪华:Stripe Collison 兄弟、Alexis Ohanian、Elad Gil [V409]。**2023 年下半年困惑地 pivot 到 website builder,2025 年 1 月 31 日关闭** [V409]。

Peter Johnston 的复盘原话(X @multiplay3r,2024 年 12 月,从二手 source 重构,中等置信度 [V410]):

> "after 3.5 years, I made the call to shut @Polywork down and return the remaining capital to investors"
>
> "building consumer social is like doing a startup on Level 900 Difficulty Mode"
>
> "no longer saw a viable path to Polywork becoming a gigantic business — and that was what we signed up for"

多因素死因:**Product** — "我的 multi-hyphenate identity 全貌"定位永远没找到 daily utility,vanity post 不带来回访 [V409]。**Market** — LinkedIn 网络效应在 recruiter 端不可撼动,所有招聘者都在 LinkedIn,Polywork 的"职业身份"没有需求侧支撑 [V409]。**Team/Capital** — $44.5M 制造了估值压力,但 B2B 货币化路径从未公开浮现 [V409]。**Timing** — 2021 hype cycle 在 2022-2023 蒸发,二级融资没救了。

**给我们的 lesson:** Polywork 是 5 个案例里最接近我们要做的产品 —— 同样是"职业身份 / 多元工作展示",同样想 LinkedIn 替代,同样定位欧美 marketing/design 创意人群。Polywork 烧光 $44.5M 没解决的问题是"为什么用户每周回来一次而不是每年更新简历一次"。**我们必须从 Day 1 设计 daily/weekly utility loop,不能只是"展示作品"**—— 那是死路。

### Read.cv(2020-2025):$3 人小团队 + acqui-hire 给用户的伤害

Andy Chung(前 Facebook / Mozilla / Quip 设计师)2020 年创立 [V412]。极简 portfolio/CV 工具,在设计师圈口碑很好,逐步加 Sites、teams、社区功能 [V412]。2023 年自报 100K+ community members [V412]。**2025 年 1 月 17 日被 Perplexity 收购,实质是 acqui-hire**(Aravind Srinivas 公开说要 Andy 的"consumer/social design talent" [V412]),团队 3 人 + 平台同日宣布 wind down [V412]。

HN 用户反应负面占绝大多数 [V413]。JadoJodo 原话:"users are increasingly treated like stepping stools for founders... users help grow a product... get comfortable with that product, integrate it into their lives... and then it's yanked out from under them" [V413]。pixeldrifter 直接称之为"a betrayal" [V413]。dorian-graph:"Yet again, let down by a centralised platform" [V413]。Andy Chung 自己说"incredibly bittersweet" [V413]。

多因素死因:**Product** — portfolio 是静态展示物,没有内在 daily loop;Sites 功能没解决核心网络效应问题 [V412]。**Market** — 设计师 + engineer 的 portfolio TAM 浅,Recruiter 不会为此付费 [V412]。**Team/Capital** — 3 人团队不可能跟 LinkedIn 全功能图竞争,小融资 (F7 / Fanjul) 没续命空间 [V412]。**Timing** — 2024-2025 AI wave 让加入 Perplexity 比继续单干更理性 [V412]。

**给我们的 lesson:** 美学和设计品质是必要不充分。**3 人团队打不动网络效应**,但更深层教训是:**用户被 acqui-hire 抛下,行业整体信任受损,以后所有同类产品都背着这道伤疤启动**。我们需要从 Day 1 想清楚 ethics: 用户的 portfolio 数据是不是可导出 / 是不是开放标准 / 我们关门的时候用户的反应应该长什么样。

### Lunchclub(2017-2024):AI 匹配但没 retention

2017 年 11 月 Vladimir Novakovski / Scott Wu / Hayley Leibson 创立 [V415]。a16z $4M seed + Coatue/Lightspeed 2020 年 9 月 $24M Series A,估值过 $100M [V415]。COVID 期间靠加视频聊天爆涨 [V415]。**2022-2024 in-person networking 回归后,gradual fade,网站仍在但实质废了** [V414]。没有大新闻 shutdown,LinkedIn Pulse 分析文章题目就叫"the quiet demise" [V414]。

Tony Shepherd 分析里最尖锐的一句:**"AI can match profiles. It struggles to convey reputational signal"** [V414]。还有 "maturity often looks like subtraction, not replacement"—— 资深用户没换平台,只是停了行为 [V414]。

多因素死因:**Product** — 每个 match 都是冷启动,无关系沉淀,senior pro 需要的是 trust through context,不是算法 serendipity [V414]。**Market** — networking-as-app 天花板低,你不需要每天被介绍 [V414]。**Team/Capital** — 15 人团队,Series A 后没法 enterprise sales pivot [V415]。**Timing** — COVID 给了假信号,后疫情核心 use case 消失 [V414]。

**给我们的 lesson:** **transactional utility 没 retention,没 retention 就没 community**。我们如果定位"把作品丢这里然后等机会来"就是 Lunchclub。必须让用户产生持续行为 —— 不是被动等匹配。

### Path(2010-2018):$66.2M、拒绝 Google $100M、隐私丑闻

Dave Morin(前 Facebook 设计 lead)2010 年 11 月创立,Dustin Mierau + Shawn Fanning 共同创办 [V416]。**3 周内 1.5M downloads,3 个月时 Google 出价 $100M 收购被 Morin 拒绝** [V416]。2011 年 11 月改版后 2M 用户 [V416]。**2012 年 2 月隐私丑闻 — Path 在未经许可情况下上传整个通讯录到服务器** [V416]。2013 年 2 月 FTC 罚 $80 万 [V416]。后续在西方市场流失,转印尼 / 韩国 [V416]。**2015 年 5 月卖给 Daum Kakao(价格未披露;研究简报里的 $80M 数字未在任何 primary source 核实)**[V417]。2018 年 9 月平台关闭 [V416]。累计烧 $66.2M [V416]。

多因素死因:**Product** — "150 人亲密圈"概念封死内容传播 loop,不像 Twitter/Instagram 有公开传播 [V416]。**Market** — 想要"intimate social"的人群太小,Facebook 已经覆盖 casual social [V416]。**Team/Capital** — 拒绝 $100M 是最贵的决定之一;Morin 的奢侈品设计美学限制了产品适应力 [V416]。**Timing** — Facebook 主导期,niche 概念不够抗衡 [V416];隐私丑闻早于 GDPR 那种结构性合规要求,太早不能"被验证",太晚不能恢复 [V416]。

**给我们的 lesson:** 不要拒绝合理的早期收购(我们大概率拿不到这个 offer,但万一);**privacy 作为品牌承诺需要绝对完美 — 一次丑闻清零**;小圈封闭传播会断 viral loop。我们的"贡献职业产出"如果设计成默认私密,会重蹈 Path 的传播断点。

### Contra(2019-?):commission-free 是增长 hack 不是商业模式

Ben Huffman(早期 Stripe 员工)+ Gajus Kuizinas 2019 年创立 [V418][V419]。NEA + Unusual Ventures $14.5M Series A,2022 年 1 月 NEA $30M Series B,累计约 $44.5M [V418]。2021 年 11 月推 100% commission-free 作差异化 [V418]。Series B 时自称 1M+ 注册用户 [V418]。2024-2026:Trustpilot 评分下滑,引入 fees 后用户原话"it was nice when it started — a platform with no fees... clearly too good to be true, and only to build up a userbase"。

多因素死因:**Product** — commission-free 一收费,核心 value prop 蒸发;portfolio 层和 Polywork/Read.cv 撞车,job matching 层和 Upwork/Fiverr 撞车,没有任一深耕。**Market** — Upwork($1.5B market cap)/ Fiverr / Toptal 已有网络效应;2022-2024 tech layoff 让 freelancer supply 过剩。**Team/Capital** — $44.5M 不足以打 Upwork 那种级别的 talent graph(Upwork 花了好几亿)。**Timing** — 2020-2021 remote work 高峰红利退潮。

**给我们的 lesson:** **不要用"免费 / 0 commission"作 cold start hook**—— 引来的是占便宜的用户,他们在你引入正常商业模式那天集体倒戈。**广泛定位("creators, developers, designers, marketers")没有杀手垂直,$44.5M 也烧不出来。**

### 五个失败案例的共同死因模式

把 5 个失败案例的死因维度抽出来,会看到 structural vs avoidable 的清晰分野:

**Structural(行业本身的难,我们躲不开但要正视):**
- 职业身份产品对抗 LinkedIn 网络效应几乎不可能(Polywork、Read.cv、Contra 都败在这)。
- "social-but-professional" 产品 retention 天然低:不是娱乐 daily-driven,不是工具 task-driven。
- Recruiter 需求侧 = LinkedIn 垄断,新平台没有 B 端货币化路径。

**Avoidable(产品 / 团队层面,我们能控制):**
- Polywork 18 个月闭测窗口期错过 hype(节奏问题)。
- Read.cv 3 人团队 + 没找货币化(资源配置问题)。
- Lunchclub 算法匹配但没 retention loop(产品架构问题)。
- Path 拒绝 Google + 隐私丑闻(决策与执行问题)。
- Contra commission-free 做品牌承诺然后反悔(诚信问题)。

**特别警告(给我们):** 我们的产品蓝图最像 Polywork + Read.cv 的混合。**Polywork 的死因 60% 是 structural,40% 是 avoidable。** 我们必须假设自己也会面对那 60% structural 死亡概率 —— 这意味着 B 端必须从 Day 1 介入设计,不能等 5 年(LinkedIn 等到 Recruiter 是 2008 年,但 LinkedIn 不会再给我们这种 grace period)。

---

## 3. 冷启动 Pattern 归纳

从 9 个案例提取 7 条可复用 pattern,每条带至少一个案例引证。

**Pattern 1 — Creator-founder fit > 任何 GTM strategy。** GitHub founder 是 Ruby 圈居民 [V400][V402];Strava founder 是 cycling 圈成员 [V403];LinkedIn Hoffman 是 PayPal mafia 中心 [V405];Substack McKenzie 是媒体圈记者 [V404]。**反例:Polywork Peter Johnston 是 Irish founder,在欧美 multi-hyphenate creator 圈不是居民。Lunchclub 创始人是 ML/AI 背景,不是 networking 圈居民。** 这条 pattern 解释了 9 个案例 70% 的成败方差。

**Pattern 2 — 窄到不能再窄 + 后扩。** Strava 用了 5 年才从 cycling 扩到 running [V420];GitHub 直到 2010 年仍以 Ruby/Rails 为核心 [V401]。**反例:Contra "creators, developers, designers, marketers" 全要,谁都没占住。** 我们的"Marketing + Design + Consulting + maybe more" 已经超过单 niche 临界,危险信号。

**Pattern 3 — "邀请制+大牌"在 Substack 行,在 Polywork 不行,区别在 power user 自带 audience 还是只带 vanity。** Substack Bishop 一人 30K 订户带过来转化为付费 [V404];Polywork 拿了一堆 Product Hunt-style 用户但没 audience 转化 [V409]。**判断标准:你邀请的"大牌"自己 push 的时候,有没有人买单?有 → 走;没有 → 是装饰品。**

**Pattern 4 — B 端 + C 端双轮,但 B 端来得越晚越好。** LinkedIn Recruiter 2008 年才上线,距 launch 5 年 [V407];Substack 至今没有传统 B 端产品,take rate 即货币化 [V404];GitHub freemium 第一个月就有 [V402](但那是 C 端 self-serve,不是企业销售)。**对我们:B 端已经有 traction(B2B AI recruiting 平台),C 端是新加 — 这是 LinkedIn 的反向路径,可能反而是优势(B 端 demand 在,C 端 supply 是关键瓶颈)。**

**Pattern 5 — 冷启动期的 viral coefficient 没意义,sticky retention 才有意义。** Path 3 周 1.5M downloads [V416] 但 3 年内崩盘;Lunchclub COVID 期暴涨 [V414] 但 in-person 回归后蒸发;Polywork 2021 病毒 [V409] 但留不住人。**反例:Strava 头 1 年只有"六个创始人加他们的朋友" [V403] 但 retention 高到无敌。**

**Pattern 6 — 资金 ≠ 成败,但烧错钱必死。** GitHub 头 4 年 0 VC [V402];Substack 头 2 年 ~$2M [V404];vs Polywork $44.5M 死 [V411]、Path $66.2M 死 [V416]、Contra $44.5M 挣扎 [V418]。**Pattern:钱用在分发(KOL outreach、conference、内容)是有效的,用在闭测期延寿 / 估值维持 / 多元化人员扩张是无效的。**

**Pattern 7 — 慢是 feature,不是 bug。** GitHub 14 个月到 100K 用户 [V401];LinkedIn 是异常值(Hoffman 加成);Strava 5 年扩品类 [V420];Substack 4 年到 1M 付费订户 [V404]。**Pattern:cold start 期间用户增长曲线不应该是 hockey stick,应该是 staircase。看到 hockey stick 要警惕(可能是 Polywork-style virality 不带 retention)。**

---

## 4. 对我们产品的具体冷启动启示

### 4.1 第一批 1000 用户从哪里来?

5 个具体渠道,按 confidence 降序:

**(a) Marketing 侧:Lenny's Newsletter / MKT1 / Justin Welsh 三大 newsletter 的付费订户名单。** Lenny ~1.1-1.2M subscribers [Phase 03];Justin Welsh ~200K [Phase 03];MKT1 Emily Kramer 长期长文读者 [Phase 03]。这三家 audience 重叠度低、对"职业身份新工具"高敏感、对 AI workflow 主动尝试。**触达方式:** 不是买广告,是付费 sponsorship + 给 Lenny / Kramer 提供 exclusive early access (10-20 个邀请码),让他们以"我朋友在做的事"形式 organic 提到。预算 $15-30K/家,3 家约 $50-90K。**反偏误:Lenny 已经被无数 SaaS sponsorship 轰炸,价格虚高 / 转化下降,可能效果不如预期。**

**(b) Design 侧:Dive Club + Femke van Schoonhoven 的 Maven course 学员群。** Ridd 的 Dive Club 是 designer + AI 圈最高质量交叉社区 [Phase 03];Femke 的 Maven "Product Strategy for Designers" 学员是付费学习 + 想转 senior 的人群 [Phase 03],他们是最有动机"展示职业产出"的人。**触达方式:** Founder 亲自上 Dive Club podcast(Ridd 主动找客)+ 给 Femke 一批早期访问权给她课程学员。约 $5-15K(主要是 founder 时间)。

**(c) Consulting 侧:Tom Critchlow / Paul Millerd 的 indie consultant newsletter 圈。** Tom Critchlow [Phase 03] 是 indie consulting 圈的 voice,Paul Millerd 是"the pathless path"作者 [Phase 03] —— 他们的读者都是从大公司 / 大咨询所离开做独立的 consultant,需要新的职业身份载体而 LinkedIn 不能给。**触达方式:** Newsletter sponsorship + cross-post 一篇"why marketing/design/consulting professionals need a new portfolio layer"的 founder essay。约 $5-10K。

**(d) Reddit:r/marketing(~1.5M users)+ r/userexperience(~600K)+ r/freelance / r/consulting。** 不要直接 launch post(会被 ban),而是 founder 长期(3+ 月)以个人身份回答专业问题,在简介里挂产品 link。这是 Substack 早期 Hamish McKenzie 在媒体圈"先成为 trusted voice 再 monetize"的模式。**反偏误:r/marketing 类 sub 对 SaaS launch 极反感,做不好会反噬。**

**(e) HN Show + Product Hunt:做,但不指望。** HN Show 适合工具型产品,我们这种"职业身份"类基本会被 HN community 怀疑(他们见太多 Read.cv 类产品)。Product Hunt 的 Golden Kitty 是 Polywork 拿过的奖 [V409] —— 拿了反而是警钟。**判断:做发布动作占位,不投入精力,真实流量靠 (a)(b)(c)。**

**5 个具体 KOL 名字(谁能成为第一批 100 用户的种子节点 / 提议邀请试用的人):**

1. **Lenny Rachitsky**(Lenny's Newsletter,~1.1M subscribers,SF)[Phase 03]
2. **Emily Kramer**(MKT1 co-founder,前 Asana/Carta/Amplitude VP Marketing)[Phase 03]
3. **Femke van Schoonhoven**(Gusto Design Manager,femke.design,Amsterdam,30K designers following)[Phase 03]
4. **Ridd / Richard Ekwonye**(Dive Club founder,designer + AI workflow voice)[Phase 03]
5. **Tom Critchlow**(Brooklyn indie consultant,前 Google Creative Lab,清楚 indie consulting pain)[Phase 03]

可选第六:**Justin Welsh**(solopreneur,Phoenix,200K newsletter)[Phase 03],但他的 audience 偏 LinkedIn brand-building,可能跟我们的"作品贡献"调性有错位。

### 4.2 邀请制 vs 公开注册

**直接答案:半邀请制。** 具体形式:

- **C 端贡献者侧**:**头 6 个月 waitlist + 邀请码,每月放 200-500 个 slot**。机制不是闭门,而是节奏控制 + 制造稀缺。每个早期用户给 3 个邀请额度,可以推荐到 marketing/design/consulting 朋友。第 6 个月或 DAU/WAU > 25% 时切换公开注册。
- **B 端消费侧**:**永远邀请制 + 销售对接**,这是 B2B AI recruiting 平台原本就在做的事,不变。
- **KOL 通道**:**给 5 个核心 KOL 每人 50-100 个邀请额度**,让他们以个人身份分发。这是 Substack 大牌作者邀请制的变体 [V404]。

**理由:** Polywork 18 个月闭测的失败 [V411] 是"窗口太长导致 hype 过期";Substack 几个月闭测 → 公开 [V404] 是合理节奏。我们要避免 Polywork mode,采用 Substack mode。

**反偏误:** 半邀请制如果运营不好会两头不讨好 —— 既制造不了稀缺感(用户进不来就走了),又比开放阻力大。判断信号:waitlist 转化率(发出邀请码到注册比)如果低于 40%,说明已经凉了,要立刻切换公开。

### 4.3 冷启动期长度

基于历史案例 + 我们特殊性的时间估算:

- **GitHub: 14 个月到 100K 用户** [V401],27 个月到 1M repo
- **LinkedIn: 15 个月到 1M(reader 端,有 Hoffman 加成)** [V405]
- **Strava: 头 2-3 年纯本地 cycling 圈** [V403][V420]
- **Substack: 14 个月到 11K 付费订户** [V404]

**我们的预测:从 launch 到 PM signal**(定义为 1000 个 weekly active contributors + 30%+ M1 retention)
- **最早可能:9 个月**(KOL 通道一切顺利 + 产品 first-week activation 跑通)
- **合理预期:12-18 个月**
- **悲观预期:24+ 个月**(KOL 通道转化低 + retention loop 没找到)

**承认不确定性:** 我们的 founder 在欧美 marketing/design/consulting 圈不是 native(不像 GitHub-Ruby、Strava-cycling、Substack-媒体),这是 LinkedIn 模式之外所有成功案例都有的优势,我们没有。所以 9 个月 floor 大概率拿不到,实际可能更接近 18 个月。

### 4.4 所需资金

**6 个月 MVP + 12 个月冷启动 = 总周期 18 个月,目标融资区间 $1.5M-$3M。**

拆解:
- **工程(60%)= $900K-$1.8M**:5-7 人团队(2-3 senior eng + 1 designer + 1 PM + 1 data + 1 founder)。SF/NYC 标准是 $200K all-in 一年,远程团队 $120-160K all-in。
- **内容 + KOL outreach(20%)= $300-600K**:5 个 KOL sponsorship 各 $20-50K + 内容生产(founder essay、case study)+ 1 名 part-time content/community $80-100K。
- **运营 + 合规 + 法务 + 工具(20%)= $300-600K**:LLM API cost(profile parsing / matching)+ Stripe + 隐私合规(GDPR / CCPA,特别针对欧美 marketing/design)+ admin。

**Sanity check:** GitHub 头 4 年 0 VC,但他们是 dev tool,自身就是用户,工具复用率极高,我们做不到。Substack 头 2 年 ~$2M 然后 a16z [V404]—— 这是最接近的参照。Polywork 把 $44.5M [V411] 烧光是反面教材,资金 ≠ 成败,但烧错地方必死。

**反偏误:** $1.5M 可能不够 —— 如果 6 个月 MVP 拖到 9 个月(常见情况),冷启动期被压缩到 9 个月,大概率拿不到 PM signal,要么 burn 续 6 个月($500K-$1M)要么估值低位融资。Plan B 应该是预留 $500K runway extension capacity。

### 4.5 最可能死在哪

诚实排列 3 个最大死因 + 防范方法:

**死因 1(概率 45%):贡献者激活后第二条内容前流失(retention gap)。** Polywork、Read.cv、Lunchclub 都死在这。**防范:** 把"激活第二条内容"作为 north star metric,产品设计上第一周必须有 5+ 次有意义触发 —— 不是 notification spam,是真实价值(有人看了、有人评论、AI 给了 insight、有 lookalike profile 出现)。提前承认:如果第 100 个用户的 W4 retention < 25%,产品概念错了,必须 pivot 而不是加 feature。

**死因 2(概率 25%):KOL 通道转化失败,backup 渠道没建。** 我们重押 5 个 KOL,但 Lenny / Justin 已经被 sponsorship 轰炸,转化可能远低于预期。**防范:** 不要把 5 个 KOL 当一个 channel,要当 5 个独立实验,每个跑 6 周看转化率。同时第 1-3 月并行启动 Reddit + indie consultant newsletter long-tail 实验。Backup plan:founder 自己 build in public(在 LinkedIn + X 上连续 6 个月发 daily 创业过程),自己变 micro-KOL。

**死因 3(概率 20%):B 端 demand 没及时给 C 端正反馈,贡献者 motivation 下降。** 我们的差异化在于"贡献作品 → 被 recruiter / B 端发现 → 真实机会"。如果 B 端虽然有 traction 但没把 demand 喂回 C 端(用户感受不到"我的作品被人看了"),整个 value prop 崩塌。**防范:** 设计 B-to-C 反馈循环 from Day 1—"你的 profile 被 3 家公司查看 / 1 个 recruiter 收藏",哪怕一开始要人工 seed B 端行为也得有。这是 Polywork 没解决的核心问题之一。

**死因 4(概率 10%):隐私 / 合规 / Trust 事件。** Path 的 2012 通讯录丑闻 [V416] 在 marketing/design 圈一样会发生 —— 我们要处理用户上传的 portfolio + 工作 history + 客户 case,GDPR 一旦做错,品牌承诺归零。**防范:** Day 1 雇 GDPR/CCPA 合规顾问;数据导出 + 用户删除 / opt-out 必须做到 industry-best;关门 ethics 提前公开(Read.cv [V412] 至少给了 Next.js 导出,这点是它做对的)。

---

## 5. 调研局限性

本报告基于 V400-V420 的 9 个案例,但以下不确定性必须承认:

- **冷启动数据多为后期粉饰。** GitHub / LinkedIn / Substack 的早期增长叙事都经过创始人多轮访谈打磨,实际"第一批 100 用户怎么来"细节往往美化。Strava 的"20 个 cyclist 朋友"是创始人 talking point [V403],真实的混乱、运气、个案巧合无从核实。
- **Polywork peak metrics 从未公开。** $1.45B 估值 [Phase 05 brief] 在公开 source 找不到确证;Series B $28M [V411] 是唯一硬数字。用户峰值、MRR 全程黑箱。
- **Path 收购价 $80M 未在任何 primary source 核实。** 任何 source 都说 undisclosed [V417]。
- **Peter Johnston X post 原文** 因 paywall 无法直接 fetch,引用是 secondary source 重构(citation 标 medium confidence)[V410]。
- **创始人复盘的 hindsight bias。** Johnston "level 900 difficulty mode" [V410]、Andy Chung "bittersweet" [V413] 都是事后包装。真实决策时刻的 reasoning 我们看不到。
- **我们 founder 的特殊性 case 不能直接对标。** B 端已有 traction → cold start C 端 — 这是 9 个案例都没有的起点。最接近的是 LinkedIn(C 端 → 5 年后 B 端),方向相反。所以时间预期、资金区间都是"借鉴 + 调整",不是 direct prediction。
- **5 个失败案例没有"还活着但没爆"的样本。** 我们把 Contra 归为"挣扎"是基于 Trustpilot + 没有新 round 的间接信号,不是 official 状态。
- **样本生存偏差:** 我们只研究了被报道的 case,有大量"安静死亡"的同类产品(invite-only 闭测 6 个月就关的 ProductHunt 一类项目)没有公开 record,这意味着 cold start failure rate 真实数字可能比 5/9 更高。
