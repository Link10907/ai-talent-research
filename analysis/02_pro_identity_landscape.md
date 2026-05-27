# Phase 02 — 海外职业身份/展示产品真实景观

## TL;DR

1. **Western professionals 的展示形态总体趋势是"客厅 / 门面"双层分离 — LinkedIn 退化为强制性的门面层,真正的"客厅"(首发新内容、被同行认真阅读的地方)迁移到了 X、Substack、个人网站、GitHub 等 owned audience 资产上。** 任何号称"一站式职业身份"的新产品都在试图把这两层重新合并,这与用户的实际行为相反 [V107][V109]。
2. **Read.cv / Polywork / Lunchclub / Path / Bento.me 五个连续死亡告诉我们一件事:"design-forward 的 better LinkedIn"是结构性死局。** 没有 transactional hook(招聘、客户、付费支持)的纯身份展示产品,无论团队多优秀、设计多漂亮、投资人多豪华,都跑不通 unit economics [V100][V102][V103][V123]。
3. **"AI 帮你聚合多平台职业身份"这个赛道目前是真空的 — 但不是因为大家没想到,而是因为这是一个被多重护城河保护的"看似空白"。** API 限制、用户对身份失控的不适、缺乏 transactional layer,这三层共同压制 [无独立 citation,推断]。
4. **核心被低估的用户群是"Frozen LinkedIn 中层"** — Director / Senior Manager 级别的人,他们不发内容、没有 owned audience、LinkedIn 是唯一在线身份,但又对 LinkedIn 的 cringe 文化高度敏感。42 个样本里这一层被刻意补全成 anonymized rows,真实信号稀疏,但这是 B 端招聘价值最高、C 端最未被服务的人群。
5. **文化方向上,personal branding 已从 Gary Vee "to everywhere" → Justin Welsh "one platform deep" → 2024+ "authenticity premium + AI 去魅"演化** [V114][V122]。下一代有机会的产品大概率不是"帮你建另一个 profile",而是"帮你管理已经存在的 owned audience"或"让 LinkedIn 不那么 cringe 地用"。

---

## 1. 产品 / 形态全景

不要把这些产品当独立 SKU 比较;它们各自占据 Western professional 身份栈的一个层。同一个人通常同时使用 3-4 个,且每个层承担的工作不同。

| 层 | 代表产品 | 谁用 | 为什么用 | 典型用法 | 维护成本 | 用户得到什么 |
|---|---|---|---|---|---|---|
| **默认平台层** | LinkedIn | 1.01B 用户,几乎所有职业人 [V107] | 招聘方在这里,简历的 ground truth,被搜索 | 月度/低于月度更新;偶发 post;接 InMail | Low(基础) / High(Creator) | 被发现,passive job market presence |
| **个人网站(高 craft)** | Cargo / Framer / Webflow / 自建 | Designer / 资深 Engineer / 一部分 founder | 表达 taste、控制版式、不靠平台算法 | Portfolio + 长文 + curated thinking | Medium-High | 同行尊重、客户转化、永久存档 [V108][V109] |
| **个人网站(frictionless)** | Carrd / Squarespace / Notion public | Consultant / Solopreneur / 不care 设计的人 | 30 分钟搞定,有个 URL 就够 | Bio + 几个链接 + about | Very Low | "存在一个网站"的合格证 |
| **链接聚合 / 名片层** | Linktree(吃掉 Bento) / About.me | Creator / Influencer 偏多,Professional 偏少 | bio 一行写不下,需要一个跳转中转 | IG/TikTok bio link | Very Low | 一个中性的 landing,但被打上"creator-coded"标签 [V123] |
| **内容创作平台层** | Substack about / Medium author / Mirror→Paragraph | Newsletter writer / Consultant / Researcher | 内容本身就是身份,about 页就是简历 | Bio + mission + best pieces | Low(about 页) / High(发 newsletter) | 订阅数即 social proof;owned audience [V111][V118][V119] |
| **作品展示层** | Behance / Dribbble / Are.na / GitHub README | Designer / Engineer / Researcher / 艺术家 | 必须 show、not tell | Case study / shot / repo / 视觉收藏 | Medium | demonstrable skill;同行圈层身份 [V110] |
| **招聘 / 创业向** | Wellfound (AngelList) / LinkedIn Creator Mode features | 找 startup job 的人;LinkedIn 上做 thought leadership 的人 | 行业聚焦的求职;创作者特权 feed visibility | profile + apply;newsletter + Live + analytics | Low / High | 行业内可见性 [V121][V124] |
| **创作者支持型** | GitHub Sponsors / Patreon / Buy Me a Coffee | OSS maintainer / Independent creator | 不是身份,是 "支持我"的入口 | 项目列表 + 目标 + tier | Low | 经济基础设施 |

### 我看到的总体演化

**(a) 默认层在退化,owned audience 在升级。** LinkedIn 仍是 unavoidable(90%+ recruiter 在用 [V107][V109]),但它正在 commodify 成一个"必须挂着的姓名贴" — 用户不在那里 think,只在那里 list。同时 Substack(Lenny 1.2M 订阅,$500K+/年 [V119])、个人网站(patrickcollison.com 的 curated sections [V117])、X(levelsio 600K followers [V113])这种 owned audience 资产,越来越被视为"真简历"。

**(b) 中间层在崩塌。** Read.cv / Polywork / Bento.me 三个本来想占据"比 LinkedIn 好看 + 比个人网站省事"的中间地带,过去 18 个月内全部死亡 [V100][V102][V123]。不是没人爱,是这层没有商业模式。

**(c) 视觉创意端反而最稳定。** Behance / Dribbble / Cargo / Framer 这一栈活了 10+ 年,因为它们绑定 transactional purpose(client work、hiring)— 不只是身份展示 [V110]。

**(d) AI 聚合层还没出现。** 这是 2024-2026 最该出现却没出现的一层(详见第 4 节)。

反例 / 张力:LinkedIn 不会简单消亡。它正在通过 Creator Mode 整合 newsletter / Live / 分析后台,把 Substack 的功能吞回自己平台 [V124]。如果它做成了,上面这套"客厅 / 门面分离"叙事可能在 5 年内被部分回退。

---

## 2. 真实人物展示分布 — 从 42 个样本归纳

### 方法与样本偏差(必须先说)

42 人覆盖 Newsletter writer / Indie hacker / Tech founder / Engineer / Designer / Marketer / Consultant 六类 + 一个 anonymized 的中层兜底类。**显著偏差有三:**

- **Public figure 偏向**:为了能 verify、能引用,样本严重偏向有公开作品的人。Visakan Veerasamy、Pieter Levels、DHH 这种人不能代表大部分用户。
- **Mid-level 信号弱**:Category H 只能用 role description 填(Director of Marketing / Senior Engineer FAANG / VP Product Series B etc.),因为非公众人物的展示数据无法 verify。这是最重要的人群,数据最稀。
- **Western / English-first**:几乎没有 DE / NL / FR / Nordic 的样本,文化对比基本是文献推断。

下面 5 个模式是从样本里能站得住的真分布;每个带具体人名作为锚。

### 模式 1:Living Room vs Front Door 分离

最强的发现 — 几乎对每一个 active 自我展示的人都成立:**他们首发新东西的地方,和别人最常通过哪找到他们,通常不是同一个平台。**

- Lenny Rachitsky:首发 Substack(lennysnewsletter.com),front door 也是 Substack,但 LinkedIn 是 amplification — 反例边界 [V119]
- Patrick Collison:首发 X,front door 是 patrickcollison.com(因为 google "patrick collison" 第一个跳出来的就是它)[V117]
- Pieter Levels:首发 X,front door 也是 X(@levelsio),但 levels.io 作为"产品 portfolio 索引"被 google 引导 [V113]
- Andrew Chen:首发 Substack/andrewchen.com,front door 是 andrewchen.com — 但他保留 LinkedIn 作为 a16z body 的 official 角色页 [V115]
- Tom Critchlow:首发 tomcritchlow.com,front door 也是个人网站,Substack(SEO MBA)是 deepener [V127]

**对产品的含义**:任何强行让用户"在一个地方同时做客厅和门面"的产品,都在和这个分离对抗。Read.cv 实际上是企图重建一个 unified profile 层,失败了。

### 模式 2:开发者的 "GitHub / X / LinkedIn 三明治"

技术人的展示有一套相对稳定的三层结构:GitHub 是技能证据,X 是个性与观点,LinkedIn 是 fallback 凭证。

- Linus Lee (thesephist):thesephist.com + github.com/thesephist(100+ projects)+ LinkedIn — 个人网站是核心,GitHub 是 backing [V116]
- DHH:dhh.dk + github.com/dhh + X — 完全跳过 LinkedIn 的 active 使用 [V125]
- Simon Willison:simonwillison.net(blog + projects)+ GitHub + X/Mastodon — 个人网站和 GitHub 是同一个生态
- Guillermo Rauch:rauchg.com + GitHub + X — 同上
- Amelia Wattenberger:wattenberger.com + GitHub — 设计 + 代码混合

资深开发者越往上越不依赖 LinkedIn。但中层开发者(Senior Engineer at FAANG)仍然 LinkedIn + GitHub 两件套,GitHub 经常只有 forks 和少量 personal repo。

### 模式 3:内容创作者的 "Substack about 作为事实简历"

Newsletter 圈这条更明显:Substack about 页就是他们的简历,LinkedIn 是没人看的备份。

- Sahil Bloom(The Curiosity Chronicle):Substack 是首发 + front door [V118]
- Sari Azout(Check Your Pulse):Substack 主场,LinkedIn 几乎不维护
- Khe Hy(RadReads):Substack + radreads.co
- Paul Millerd(The Pathless Path):Substack + pmillerd.com + podcast
- Ethan Mollick(One Useful Thing):Substack + X(@emollick)— Wharton 教授身份,但他自己的公开身份是 Substack

这群人的 LinkedIn URL 在样本里多数显示为空("—"),不是因为没有,是因为他们已经 outgrew LinkedIn。

### 模式 4:Indie / Freelance 的 "个人网站作为主入口"

独立工作者把个人网站当 hub,所有其他渠道都指向它。这是和 employed professional 最大的行为差异。

- Pieter Levels:levels.io 极简风,只列产品和 X 链接 [V113]
- Marc Lou:个人站 + ShipFast + X — X 是首发,个人站是商品 [V126]
- Ben Tossell:个人网站 + X + newsletter
- Jules Forrest:julesforrest.com 是 freelance design 的 hub
- Tobias van Schneider:vanschneider.com + DESK newsletter,跨过 LinkedIn

**临界点**:一旦一个人开始独立接单或卖产品,LinkedIn 的相对重要性就大幅下降,因为 LinkedIn 的搜索流量并不进入他们的销售漏斗。

### 模式 5:Frozen LinkedIn 中层(关键发现,但证据弱)

样本 H 类的 5 行是 role description 而非真名,因为这群人公开数据稀薄 — 这本身就是发现。他们:

- 只在换工作时更新 LinkedIn
- 没有 owned audience
- 不在 X、不写 newsletter、不维护个人网站
- 在 r/LinkedInLunatics 的影响下,对发任何 LinkedIn 内容都有 cringe-risk 警觉
- 是 B 端招聘真正想触达的人

这一层是"沉默大多数",他们的 front door 和唯一 door 是同一个:基本静态的 LinkedIn profile。任何 C 端身份产品如果只盯 public figure(Pieter Levels、Lenny),就 miss 了真正未被服务的市场。

### 这些模式对"我们产品该放在哪一层"的含义

样本里 active 自我展示的人(模式 2-4 那群)其实已经 well-served — 他们有个人网站 + GitHub / Substack / X,组合起来就是完整身份。如果我们给他们"再做一个 profile",会重蹈 Read.cv / Polywork 覆辙。

**真正未被服务的是模式 5 的 frozen 中层**:他们既不想做 personal brand,又不想完全靠静态 LinkedIn 被找到。但他们也最难拉动 — 因为他们对"职业内容输出"本身就有抵触。这意味着我们的产品不能要求他们 publish,只能是 passive aggregation 或 private mirror。这是核心定位约束。

---

## 3. 文化与心理

### Personal Branding 三阶段演变

- **2015 Gary Vee 阶段**:"Document, don't create" / "Be everywhere" — 数量即美德,平台覆盖即胜利。让 personal branding 这个词变成主流职业词汇 [V122]。
- **2020-2023 Justin Welsh 阶段**:从"覆盖"转为"系统" — 选一个平台(LinkedIn for B2B),每天一篇,build owned email list,变现成 course / consulting / product。Welsh 自己 472M+ impressions,$12M profit [V114]。这是把 personal branding 从 hustle 变成 ops。
- **2024-2026 AI 阶段**:AI 可以批量生产 LinkedIn 帖、个人网站文案、professional summary,导致受众产生 authenticity premium — 真实数字、真实争议、真实失败更被信任。Welsh 自己 2025 newsletter headline 改成"Don't build a brand. Live a life." [V114],是这个转向的直接信号。Substack 因为"我拥有受众"被视为 authenticity proof。

**这是延续还是反弹?** 是延续 + 内部转向:personal branding 没死,但工具化 / 模板化的玩法收益递减,直接展示工作过程("build in public 2.0")变成新的真实信号。

### Build in Public 当前状态

Pieter Levels 仍是标杆:Photo AI $132K/月 + Nomad List $5.3M 年收入 + Remote OK + Interior AI,合计 ~$250K+/月,600K X followers,levels.io 只是产品索引 [V113]。Marc Lou 接过传承,2025 年 1 月公开 $124,772 月收入 [V126]。

**但运动正在分层:** Indie Hackers 社区 2024 观察到,$10K-30K MRR 以上的顶部玩家很多停止公开数字,原因是 copycat、个人安全、心理负担、家庭关系 [V112]。Marc Lou 继续披露,所以他成了"剩下的代表"。

**含义:** Build in public 不是单调的"越透明越好",而是已经分裂为"未到天花板的人靠透明拉关注"vs"过了天花板的人转入半透明"。任何鼓励透明的 C 端产品需要默认 default 是私密 / 用户可控显示粒度。

### LinkedInLunatics 现象

r/LinkedInLunatics 嘲讽 LinkedIn 上 over-performative 的内容 — 把日常工作事件包装成励志故事、显摆型 humble-brag、为了 engagement 过度暴露私事的帖子。

**讽刺点:** 这些被嘲讽的帖子在 LinkedIn 算法上确实跑得好。Cringe content works algorithmically。

**真实文化效应:** 创造了 chilling effect — 凡是知道这个 sub 的 tech-adjacent 专业人士,写 LinkedIn 都会自我审查。结果:不知道 / 不在乎的人继续 post,继续拿 engagement;知道的人不 post,reach 持续下降。**这是一种 LinkedIn 上的双层文化分裂。**

对我们产品的含义:有市场需求是"我想被人看到我的能力,但不想以 LinkedIn cringe 的方式"。这是一个真实情感缺口。

### 区域差异(证据弱,需要明说)

raw data 在这点上明确标注"no quantitative primary source found",所以下面都是 directional inference [V*推断]:

- **US**:self-promotion tolerance 最高,personal brand 是 socially acceptable 词汇
- **DE / DACH**:"Angeberei"(吹嘘)的文化排斥,XING 仍存在但衰退,LinkedIn 用得更正式
- **Nordic**:Janteloven 压制公开个人成就声明,身份多通过 role / org 表达
- **UK**:US 和 DE 中间,British understatement
- **FR**:LinkedIn 渗透高,personal branding 弱,grandes écoles 学历优先于 personal brand

**坦白说**:这一节如果要在产品决策里被引用,需要做一次 quantitative 补研(survey 或 LinkedIn / X 的 active user 占比 by country)。当前证据等级是"行业 lore + 二手文献",不是"测量"。

---

## 4. 2024-2026 新产品扫描

### "AI 帮你聚合多平台职业身份"赛道当前真实状态

**没有 dominant player。** 现有的尝试:

- **LinkedIn 内置 AI features**:profile improvement、post drafting、job matching — 是 incremental,不是新产品。
- **Portfolio generator**(给 LinkedIn URL → 生成个人网站):多个 ProductHunt launch 存在,无 breakout。
- **Resume AI**(Enhancv / Kickresume / Rezi):AI 简历优化,不是身份聚合。
- **Linktree / About.me**:链接聚合但没有 AI synthesis。
- **Lessie.ai 类小实验**:status 不明,未规模化。

### 为什么没有规模化产品出现 — 这个空白真实存在吗?

我倾向认为**这个空白是 partially 真空白,partially 有看不见的护城河**:

1. **API 限制**:LinkedIn 长期 hostile to scraping,Substack 数据零碎,X 自 2023 起 API 收紧。要做"自动聚合多平台"在合规层面就很难。
2. **用户对"我的身份被 AI 自动综合"的不适**:Reid Hoffman 自己做 AI deepfake 访谈需要 20 年 public data + 个人 consent + 个人深度参与。这对普通用户不可复制。
3. **缺乏 transactional layer**:即使聚合成功,展示页给谁看?recruiter 还是看 LinkedIn,客户还是看个人网站。聚合页本身没有自然受众。
4. **真空白的部分**:针对 frozen LinkedIn 中层的 passive aggregation(用户不发内容,但能 surfaces 他能做什么)— 这层确实没有产品。但它的 monetization 路径仍未解决。

**判断**:这不是没人想到,是"想得到的人都看清了三重护城河,选择不做"。对我们而言,这是机会但不是 obvious win — 需要明确避开过去失败者踩过的坑。

---

## 5. 死亡案例的真实教训 — 5 个产品的 cause-of-death

### 5.1 Read.cv(2021 启动 → 2025-01 Perplexity acqui-hire,2025-05 数据导出截止)

**时间线**:2021 Andy Chung(ex-Facebook/Mozilla/Quip)启动 → 2022-2024 凭设计赢得 design-conscious tech 圈口碑 → 加入 Posts.cv、Sites(.cv 自定义域名)→ 2025-01-17 Perplexity 收购 3 人团队,平台 wind down [V100]。

**死因(多因素)**:
- *Product*:beloved 但 love ≠ revenue。Sites feature 是最清晰的 monetization 但来太晚,要和 Squarespace / Carrd / Webflow 同台。
- *Market*:bilateral network effect 缺一边 — recruiter 从未真正到场。
- *Team*:3 人,极简,无 funding 披露,无试错余地。
- *Capital*:soft exit 形式 — Perplexity 想要的是会做 consumer/social UX 的 designer,产品本身是副产品。

**Andy Chung 原话**:"incredibly bittersweet" [V100]。

**HN 社区反应**:"Yet again, let down by a centralised platform." 用户迁往 Reactive Resume(self-hosted)或退回 LinkedIn [V101]。

**对我们的 lesson**:design-forward 在没有 transactional layer 时不可持续。如果我们的产品最终也是"展示页",需要在第一天就回答 monetization 问题,不能"network 起来再说"。

### 5.2 Polywork(2021 → 2025-01-31 主动关闭)

**时间线**:2021 launch → 2022 Product Hunt Golden Kitty → $13M raised(Collison brothers、Ohanian、Elad Gil)→ 2023 末 pivot 到 AI website builder → 2025-01-31 关闭并向投资人返还剩余资本 [V102][V103][V105]。

**死因(多因素)**:
- *Product*:multi-identity 的承诺真实,但 most professional 不想再多维护一个 profile — 他们想现有的 profile 更好。
- *Market*:regional network effect 残酷 — US 早期火,出 SF/NYC 就是 ghost town [V104]。
- *Pivot*:从"better LinkedIn"到"AI website builder"是两个完全不同的 user job,把核心用户搞糊涂,也没有理由让 Squarespace 用户切过来。
- *Capital*:**chosen** shutdown — 还有钱返还。Johnston 自己读出了"做不成 gigantic business"的信号。

**Peter Johnston 原话**(2025-01)[V102]:
> "Building consumer social is like doing a startup on Level 900 Difficulty Mode... we were unable to sustain our growth and no longer saw a viable path to Polywork becoming a gigantic business. **I still really believe the world needs a new standard in professional identity and discovery**, and so I am hopeful that one day, another team takes a crack at this problem again."

**张力直面**:他说"world still needs this"。这不是 sour grapes — 是创始人对问题真实存在的判断,跟"我们做不下去"是两回事。问题在;路径错。

**对我们的 lesson**:
- 不要 pivot 到 commoditized space(website builder 已经红海)
- "star investor logos"(Collison + Ohanian)替代不了 PMF
- 如果我们要做"new standard in professional identity",必须从一开始就回答"为什么这次能跑通而 Polywork 当年没跑通"

### 5.3 Lunchclub(2018 → 2025-2026 zombie state)

**时间线**:2018 founded → a16z-led ~$4M → COVID 期间峰值 ~1M+ 用户 → 2025-2026 仍在线但 activity 显著下降,无正式关闭公告。

**死因**:
- *Product*:engagement cliff 残酷 — 头几次匹配新奇高价值,之后变成每周一次的 scheduling burden。1:1 视频通话本身 coordination overhead 太高。
- *Market*:match quality 取决于 active 用户池,池子一缩水 match 就烂,然后用户进一步流失 — 自反馈死亡螺旋。
- *Capital / Team*:种子轮规模不足以撑过 COVID 红利消退。
- *Macro*:COVID-era 行为变化的产品需要 hybrid work 回归后的 plan B,Lunchclub 没有。

**对我们的 lesson**:任何依赖"frequent active engagement"的设计在新奇消退后会塌。如果我们的产品要求用户高频回访填东西,会面临同样的曲线。passive 数据流入 + 偶发 surface 可能是更稳的设计。

### 5.4 Path(2010 → 2018 关闭)

**时间线**:2010 Dave Morin 启动,Max Levchin、Marc Andreessen、Greylock 投资,raised ~$55M → 2013 因未经父母同意收集未成年人通讯录信息被 FTC 罚 $800K → 2015 卖给 Kakao → 2018 关闭。

**死因**:
- *Market*:Facebook + Instagram 已经吃下注意力主流,privacy-first 是 niche
- *Product / Capital*:无 ads + 无 data selling 的隐私优先 consumer social 没有规模化收入模型;Path for Work 没跑通
- *Trust*:FTC $800K 罚单,对 privacy-positioned 产品是致命公关
- *Timing*:2010 隐私焦虑还没起来,2015 隐私焦虑高峰时它已经无力

**对我们的 lesson**:"better design + more privacy"不是商业模型。Dunbar 数(150)作为 cap 制造了 network growth 天花板。如果我们想做 privacy-first,必须从第一天就 design 一个不依赖 ads / data selling 的 revenue model。

### 5.5 Contra(2018 → 2026 仍活着,repositioned)

**时间线**:启动作为 freelancer 职业身份/portfolio 平台 → $45M raised(NEA)→ 2025 launched Indy AI(AI 找客户)→ Q1 2025 用户增长 20%,1M+ professionals [V106]。

**为什么 Contra 活了而其他人死了**:它把定位从"professional identity display"转到"commission-free freelance marketplace + tools",找到了具体的 transactional 价值主张(对抗 Upwork 20% 抽成)。Profile 页仍是 selling point,但**目的从 expressive 变 transactional**。

**对我们的 lesson**:能活下来的 identity 平台一定有 transactional layer — GitHub 之于 hiring,Behance 之于 client work,Wellfound 之于 startup jobs,Contra 之于 commission-free freelance。**Pure identity display without transactional purpose 没有活路。**

### 综合:5 个案例的共同死因模式

| 因素 | Read.cv | Polywork | Lunchclub | Path | Contra |
|---|---|---|---|---|---|
| Network effect 困境 | 高 | 高 | 中 | 高 | 中(已绕过)|
| Revenue model 不清 | 是 | 是 | 是 | 是 | 已解决(marketplace)|
| Pivot 毁了核心价值 | 否 | 是 | 否 | 否 | 否(doubling down) |
| LinkedIn 是默认对手 | 是 | 是 | 否 | 否 | 部分 |
| Acqui-hire 出口 | 是 | 否 | 否 | 是 | 否 |
| 2026 状态 | 死 | 死 | 僵尸 | 死 | 活 |

**共同结构性死因**(我们改变不了的)**:
1. Professional identity 产品的 passion users 数量 ≪ VC-scale business 所需 user 数量。死的几个都是"小众挚爱"但跑不到 mass。
2. 没有 transactional hook 时,monetization 永远是远期承诺。
3. LinkedIn 的网络效应不是"做得更好就能取代"的对手。

**可避免的死因**(我们可以选择不重蹈)**:
1. 不做 pivot 到红海(Polywork → website builder)
2. 不依赖 high-frequency engagement(Lunchclub)
3. 不靠"design 取胜"作为唯一差异化(Read.cv)
4. 第一天就明确 revenue path,不寄望于"先把网络做起来"

---

## 6. 对我们产品的启示

下面 4 条决策建议,每条带反对意见(devil's advocate)。

### 决策 A:产品定位为"私密能力镜子"而非"公开职业身份"

我倾向 **"私密能力镜子"**,因为:
- 5 个死亡案例里 4 个死在"做公开职业身份" — 这个池子已经验证过了
- 用户对 LinkedIn cringe 高度敏感,公开自我展示有真实心理代价(LinkedInLunatics 效应)
- B 端我们已经有招聘数据,C 端真正需要的是"用户愿意 voluntarily 给我们更多信号"
- Reader 提示中也明确:"用户不感觉被 exploit",私密镜像最容易满足

**反对意见(Polywork 反例)**:Peter Johnston 至今认为"the world still needs a new standard in professional identity and discovery"[V102]。他没说"我们应该做私密的"— 他说的是 discovery。如果完全 private,我们就放弃了 viral 传播和 discovery 价值。

**和解方式**:第一阶段 default 私密(用户填能力 → AI 镜像给用户看自己) → 第二阶段 opt-in 可选择性公开(用户选择性 surfaces 给特定受众,如 recruiter 或 collaborator)。私密是 default,公开是 user-controlled action,不是平台 push。

### 决策 B:邀请制 vs 公开注册

我倾向 **早期严格邀请制**,因为:
- Read.cv / Polywork 的早期 community 都是被 design-conscious 用户自发拉进来 — 邀请制可以保留这种 quality,避免被低质量 LinkedIn-style 内容污染
- 邀请制天然过滤出 "lurker quality" 高的人,这对样本 mode 5 的 frozen 中层尤其重要(他们对环境质量敏感)
- Mid-level professional 不会主动注册一个 unknown 产品,但会被同事/朋友推荐进去

**反对意见**:邀请制几乎一定让我们 miss "gigantic business" 路径 — Polywork 教训。要 1M+ 用户需要 frictionless onboarding。

**和解方式**:邀请制不是终态,是"前 10K 用户"阶段的策略。10K 之后开放注册,但保留"被引荐"作为一种用户路径选项。Notion 走过类似路。

### 决策 C:聚合自动化 vs 用户手动填写

我倾向 **"AI-assisted manual + 用户拒绝权"**,因为:
- "AI 自动聚合多平台"在 API、隐私、用户信任上都有结构性阻力(见第 4 节)
- 用户手动填能制造 commitment effect,数据质量更高(对 B 端价值更大)
- 完全自动聚合会让用户觉得"我的身份被偷了" — 这是 Reader 明确要避开的失败模式

**反对意见**:Lunchclub 教训告诉我们 high-friction 维护一定会被用户放弃。手动填写就是 high-friction。

**和解方式**:AI 做 prompt(基于公开数据建议:"你 LinkedIn 上写了 X,要不要展开说说?")— 用户回答的形式是 conversational 而非 form-fill,数据从对话里抽取。这样 friction 低,但用户始终是 driver,数据是 voluntary contribute。

### 决策 D:目标用户优先打 frozen 中层而非 indie creator

我倾向 **frozen 中层(Director / Senior Manager / 非 public figure)**,因为:
- Public-figure indie creator 已经 well-served(他们有 X + Substack + 个人网站组合)
- Frozen 中层是 B 端招聘价值最高 / C 端最未被服务的人(模式 5)
- 我们 B 端业务的 ground truth 数据(简历)正好覆盖这群人,可以 build 一个 cold-start 优势

**反对意见**:frozen 中层最难拉动 — 他们不主动 publish,对新工具警惕。indie creator 反而是更愿意试新工具的 early adopter。

**和解方式**:Early adopter 用 indie creator(获得 demo + 口碑),但产品的 design system / 价值主张围绕 frozen 中层(冷启动后规模来自这里)。这是 Notion 走过的路径(早期 Pieter Levels 用,长期是 office worker)。

---

## 7. 调研局限性

1. **死因复盘的事后合理化偏差严重**。创始人公开说"为什么我们死了"几乎一定是经过 narrative shaping 的版本 — 投资人体面、团队体面、自己体面。Peter Johnston 说"the world still needs this"既可能是真信念,也可能是公关姿态。我们 cite 时已经标注,但读者必须保留 30%-50% 的折扣。

2. **42 人样本严重偏向 public figures**。Pieter Levels、DHH、Lenny 这类人不能代表 Western professional 主体。真正的中层信号(模式 5)用 anonymized role 兜底,这是不得已 — 但意味着对"frozen LinkedIn 中层是机会"这个结论的证据是间接的,不是 measured。建议下一阶段做 quantitative survey(50-200 个非公众 Director / Senior Manager 的展示行为)。

3. **文化差异(US/UK/DE/NL/FR/Nordic)的量化证据近乎为零**。本报告第 3 节 D 部分的所有区域结论都是 secondary / lore-based。如果产品决策要押注于"美国市场和欧洲市场需要不同 onboarding 策略",必须先做区域 user research,不能用本报告作为依据。

4. **没有 first-party 用户访谈**。整份报告基于公开二手资料 + 平台数据 + 一手公开内容,没有跟 5-10 个目标用户做 1:1 访谈。Phase 03 之后的产品 hypothesis 必须先经过用户访谈 validation,再 push 到 build 阶段。
