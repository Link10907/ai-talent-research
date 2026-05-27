# V2 Raw Data 综合审计与再判断

**日期**:2026-05-27  
**审计对象**:`raw_data/phase_01` ~ `raw_data/phase_07` 的搜索日志、关键原始汇总文件、V2 analysis 与 thesis。  
**目的**:在不只依赖 `analysis/` 二级归纳的情况下,回到 raw evidence,重新理解这个 C 端产品是否真实、客观、可行,以及它如何服务“构建生态,获取 C 端简历 / 能力 / 技能数据,反哺 B 端”的第一性目的。

---

## 0. 重要说明

本文件不是替代 `v2_final_report.md`,也不是替代 `v2_ecosystem_c_product_direction.md`。

它解决的是一个更基础的问题:

> 如果直接看 raw_data,而不是只看 analysis,之前的方向判断是否仍然站得住?

结论是:

**基本站得住,但必须进一步收敛。**

V2 原始资料并不支持“做一个泛职业身份平台”;也不支持“做一个纯能力镜子工具”;更不支持“做一个后台采集数据的 C 端壳”。

Raw data 支持的是一个更具体的方向:

> 做一个真实 To C 的职业资产管理产品,用免费或低门槛利好吸引用户持续整理和更新职业资料;产品底层把这些资料结构化成 B 端可用的人才数据资产;通过用户可控的机会通道,逐步打通 C 端和 B 端生态。

---

## 1. Phase 01 raw data:Newsletter 生态到底说明了什么

### 1.1 原始搜索覆盖

Phase 01 raw search log 覆盖了 Substack、Beehiiv、Kit、Ghost、LinkedIn Newsletter、Marketing Brew、Lenny、Justin Welsh、Demand Curve、RadReads、TLDR、设计 newsletter 等。搜索重点是平台规模、收入、转化率、订阅数、创作者经济和 newsletter 作为职业身份载体的可行性。

### 1.2 raw data 给出的真实信号

第一,newsletter 是成熟生态,不是空白市场。Substack、Beehiiv、Kit、Ghost 各有明确定位。Substack 有 discovery network,Beehiiv 有严肃运营工具,Kit 有 automation 和 creator commerce,Ghost 有 open-source / publisher 生态。

第二,newsletter 生态极度幂律。Lenny、Justin Welsh、Morning Brew、TLDR 这类头部案例不能代表普通专业人士。普通用户不可能像 creator 一样持续公开输出。

第三,newsletter 对我们更像渠道和信任层,不是产品主体。它可以帮助冷启动、触达 KOL 社区、承接行业信息源,但不能指望大多数 C 端用户通过“写 newsletter”来持续贡献职业数据。

### 1.3 对产品方向的影响

原先 V2 thesis 中“行业时报”可以保留,但它不能成为核心产品。更合理的定位是:

- 用 newsletter / 行业时报吸引用户回来。
- 用行业变化提醒用户更新自己的职业资产。
- 用内容触发技能补全、项目补全、机会偏好补全。

也就是说,内容不是目的,内容是职业数据更新的触发器。

---

## 2. Phase 02 raw data:职业身份产品真实景观

### 2.1 原始搜索覆盖

Phase 02 raw search log 覆盖 Read.cv、Polywork、Lunchclub、Bento.me、LinkedIn Creator Mode、build-in-public、个人网站、Lenny / Justin Welsh、Contra、Pieter Levels、Substack about page、Wellfound、Behance、Dribbble、Are.na、Notion public page、LinkedIn vs personal website 等。

同时 `people_sample.md` 收集了 42 个公开人物和中层匿名画像,覆盖 newsletter writer、indie hacker、tech founder、engineer、designer、marketing / GTM、consulting、mid-level professionals。

### 2.2 raw data 的关键发现

第一,LinkedIn 是 mandatory professional record,但不是大多数高活跃专业人士的真实主场。真实主场分散在 X、Substack、GitHub、personal site、Behance、YouTube 等。

第二,强职业身份用户通常维护 2-3 个平台。LinkedIn 是 front door 或 credential store,但 publishing first 通常发生在别处。

第三,mid-level professionals 是最关键但最难观察的人群。他们没有 newsletter,不 build in public,不高频发 LinkedIn,但他们是 B 端招聘最想触达的人。`people_sample.md` 把他们称为 Frozen LinkedIn,即 LinkedIn 是 frozen credentialing。

第四,Read.cv / Polywork / Bento.me 等产品的教训是:better profile 不够。没有持续使用理由、没有交易钩子、没有生态位,就会变成一次性页面。

### 2.3 对产品方向的影响

这组 raw data 直接否定“做另一个职业主页”。

真正机会在于:

- 帮用户把多平台职业资产聚合回来。
- 帮 frozen LinkedIn 人群更新自己的职业事实。
- 帮 B 端看到 LinkedIn 看不到的技能变化、项目证据、AI workflow。

因此,产品不能从“展示页”出发,而要从“职业资产整理 + 数据更新 + 可控展示”出发。

---

## 3. Phase 03 raw data:目标人群日常画像

### 3.1 原始搜索覆盖

Phase 03 raw search log 分三组:Marketing、Design、Consulting。

Marketing 搜了 Lenny、Justin Welsh、Ann Handley、Rand Fishkin、Katelyn Bourgoin、Harry Dry、Emily Kramer、Codie Sanchez、Wes Kao、Anthony Pierri 等。

Design 搜了 Femke、Tobias van Schneider、Frank Chimero、John Maeda、Jenny Wen、Ridd、Linus Lee、Soleio 等。

Consulting 搜了 Tom Critchlow、Paul Millerd、Khe Hy、Brian Balfour、Sari Azout、Polina Pompliano、MBB / Big 4 中层等。

同时还搜索了 TAM 数据、LinkedIn 创作者比例、区域文化差异。

### 3.2 raw data 的真实信号

第一,Marketing 不是因为“最大”而最适合首切,而是因为它最愿意公开讨论 AI 工作流。Marketing 人天然习惯工具、内容、增长、案例、课程、newsletter 和 LinkedIn 表达。

第二,Marketing 头部 creator 已经被服务得很好。Lenny、Justin Welsh、Codie Sanchez、Katelyn Bourgoin 等不是我们的主要用户。他们更像渠道、标杆和生态节点。

第三,真正目标用户应该是中层 marketer:已经用 AI 做了实际工作,但还没建立个人媒体公司,也没能力持续输出。

第四,Design 对产品差异化重要,但文化更克制。设计师有作品集传统,但 AI 让“视觉结果”证明力下降,更需要展示 process、judgment 和 workflow。

第五,Consulting 不适合首切。raw data 很清楚:能观察到的 consulting 公开人物大多已经离职做 creator / independent consultant;在岗顾问受 NDA / 客户保密限制,公开证据少。

### 3.3 对产品方向的影响

首切人群应是:

> AI-augmented mid-level marketing / GTM operator。

但必须防止误切成 creator 工具。我们不是帮 Justin Welsh 做更好的页面,而是帮一个 SaaS marketing manager 把真实做过的 AI workflow、campaign、growth experiment、automation、content system 变成可更新、可证明、可授权的数据资产。

---

## 4. Phase 04 raw data:私密 vs 展示模式

### 4.1 原始搜索覆盖

Phase 04 raw search log 覆盖 Notion、Obsidian、Roam、Mem.ai、23andMe、LinkedIn、GitHub、Substack、Whoop、Strava、Otter.ai、Instagram、Behance、Dribbble、Apple Health、Day One、Bear 等。

`comparison_data.md` 汇总了用户规模、增长、ARPU、公开比例、B-side fit、设计模式等。

`b_side_feedback_fit.md` 对比了 23andMe 和 LinkedIn 两种 B 端反哺模式。

### 4.2 raw data 的真实信号

第一,纯私密产品可以赚钱,但很难形成 B 端人才数据生态。Notion、Obsidian、Roam、Day One、Bear 都说明了这一点。

第二,纯公开产品更容易 B 端化。LinkedIn、GitHub、Behance、Dribbble、Strava 都在不同程度上证明了公开数据可以形成网络效应或 B 端价值。

第三,23andMe 是重要反例。它有 80% research opt-in 和真实 B2B pharma value,但由于数据敏感、用途不透明、破产出售等问题,最终出现严重信任风险。

第四,LinkedIn 的 B2B 模式之所以能被接受,是因为用户心智里知道“我公开 profile 是为了被职业机会看到”。但即便如此,LinkedIn 用用户内容训练 AI 仍然引发反弹。

### 4.3 对产品方向的影响

产品不能默认全部公开,也不能默认全部私密。

更准确的是三层可见性:

1. 原始资料默认私密。
2. 用户确认后的职业档案 / 能力证据可公开。
3. B 端机会通道默认关闭,由用户主动开启。

这不是单纯的隐私设计,而是生态信任基础。

---

## 5. Phase 05 raw data:冷启动路径

### 5.1 原始搜索覆盖

Phase 05 raw search log 覆盖 GitHub、Strava、LinkedIn、Substack、Polywork、Read.cv、Lunchclub、Path、Contra 等。

重点不是产品功能,而是第一批用户如何来、增长如何发生、失败在哪里。

### 5.2 raw data 的真实信号

第一,成功产品冷启动靠窄社区和 founder/community fit。GitHub 靠 Ruby / Rails 圈和 RailsConf;Strava 靠 SF cycling;LinkedIn 靠 Reid Hoffman 和 PayPal Mafia;Substack 靠 Bill Bishop / Sinocism 等早期 power writer。

第二,失败产品常死于没有第二次使用。Polywork 有 hype,Read.cv 有设计圈好评,Bento.me 有工具价值,但都缺持续回访理由。

第三,资金不是核心。Polywork 和 Path 都融了很多钱,但没有解决网络和留存问题。

第四,第一批用户不能靠大众 launch。要靠 KOL、窄社区、已有信任网络。

### 5.3 对产品方向的影响

我们必须接受:

- 冷启动不是 product launch,是社区进入。
- 90 天不要追大规模,要追高质量种子用户。
- 第一批用户必须是可访谈、可共创、愿意反馈的人。
- 不要一开始做多行业横向产品。

首批 100 人应该从 marketing / growth / GTM 的窄社区来,尤其是已经被 AI workflow 教育过的人。

---

## 6. Phase 06 raw data:用户意愿

### 6.1 原始搜索覆盖

Phase 06 raw search log 覆盖 Lenny、Substack、LinkedIn Premium、ChatGPT Plus、Claude Pro、Read.cv、Bluesky、LinkedIn OpenToWork、23andMe、Maven、Strava、Whoop、Spotify Wrapped、Figma、Notion、Reforge、Polywork、Threads、Mastodon、Pavilion、Bento、Cursor、Hampton 等。

### 6.2 raw data 的真实信号

第一,$20/月是专业 AI 工具的价格锚,但这不意味着我们应该早期强行收费。

第二,迁移几乎不会发生。Mastodon、Threads、Bluesky、Read.cv、Polywork、Bento 都说明用户很难从既有网络迁移。

第三,隐性被发现需求巨大。LinkedIn OpenToWork 私密信号远大于公开 badge,说明用户希望被机会看到,但不愿公开求职。

第四,用户愿意交换数据,但前提是获得连续反馈。Whoop、Spotify Wrapped、Cursor 等都说明,用户愿意为可见反馈持续提供数据。

### 6.3 对产品方向的影响

C 端可以免费。早期甚至应该免费。

真正要验证的不是“用户会不会付 $20”,而是:

- 用户会不会导入简历?
- 用户会不会确认技能?
- 用户会不会连接证据源?
- 用户会不会更新机会偏好?
- 用户会不会 30 天后回来?

C 端收费只是辅助验证,不是第一目标。

---

## 7. Phase 07 raw data:技术、合规、平台约束

### 7.1 原始搜索覆盖

Phase 07 raw search log 覆盖 GitHub API / ToS、X API、LinkedIn API、Behance、Dribbble、Substack、Medium、Notion、Mirror / Paragraph、GDPR、CCPA / CPRA、EU AI Act、数据本地化、hiQ、Meta v Bright Data、X v CCDH、LinkedIn Recruiter、Handshake、23andMe、Spotify Wrapped、Strava review、Barnum effect、personal site scraping law 等。

### 7.2 raw data 的真实信号

第一,LinkedIn 数据不能作为可抓取基础。OAuth 只剩基础身份能力,工作经历不能指望 API。

第二,GitHub 可作为 C 端用户自拉数据源,但不能直接把 GitHub-derived personal data 卖给 recruiter / job board。

第三,X API 成本和限制都很高,不能作为主数据源。

第四,Substack 没有官方 API,主要只能靠 RSS / 用户导出。

第五,EU AI Act、GDPR、CCPA 都要求用户知情、授权、可撤回,尤其是招聘相关 AI 评估要极其谨慎。

### 7.3 对产品方向的影响

平台架构必须 user-initiated。

最干净的路径是:

- 用户导入简历 / LinkedIn export。
- 用户主动连接 GitHub / portfolio / Substack RSS / personal site。
- 用户确认 AI 抽取出的技能和证据。
- 用户选择哪些内容公开。
- 用户选择是否开放机会通道。

不能做:

- 批量抓 LinkedIn。
- 后台卖 GitHub-derived 数据。
- 不透明地把 C 端数据给 B 端。
- 给 B 端 AI 候选人评分并作为招聘决策依据。

---

## 8. 对之前工作的总体理解

现在把 raw_data 和 analysis 合在一起看,之前工作的主线是清楚的。

### 8.1 V1 的主线

V1 解决的是大方向:

- AI 能力正在变成招聘要素。
- 但“作品取代经历”被夸大。
- LinkedIn 不会被替代。
- 真机会是能力证据层。
- Marketing / Design / Consulting 是初步方向。

### 8.2 V2 thesis 的主线

V2 thesis 进一步提出:

- 公司真正要的是 B 端数据护城河。
- LinkedIn 在规模和真实性上强,我们只能在新鲜度和维度上找机会。
- 产品应从“能力证据层”升级成“能力镜子”,让用户为自己使用。

### 8.3 V2 raw_data 的纠偏

Raw data 进一步告诉我们:

- Newsletter 不是产品主体,只是渠道和触发器。
- Better profile / portfolio 不是强需求。
- Head creator 不是 ICP,中层专业人士才是。
- 纯私密不利于 B 端,纯公开伤信任。
- 用户不迁移,只能叠加。
- 平台和合规限制决定必须 user-authorized。
- 早期 C 端可以免费,关键是数据生态形成。

### 8.4 当前最准确的方向

最准确的方向不是“职业能力镜子”四个字本身,而是:

> 一个真实服务 C 端的职业资产管理产品,通过职业整理、能力地图、简历自动更新、证据卡、私密机会控制等利好,让用户持续贡献和更新高质量职业数据;这些数据在用户授权下进入 B 端 AI 招聘生态,提升推荐、匹配和触达。

---

## 9. 需要改掉的旧表述

### 9.1 “能力镜子是前台外壳”

这句话容易让人误以为 C 端只是伪装。应改成:

> 能力镜子是 C 端真实价值,也是数据生态入口。

### 9.2 “C 端收费是验证目标”

应改成:

> C 端付费是可选验证项,不是核心。早期更重要的是数据授权率、更新率、完整度和 B 端增量价值。

### 9.3 “只做 evidence card MVP”

应改成:

> MVP 要同时做基础 profile、技能图谱、证据卡、机会偏好。Evidence card 只是其中一层。

### 9.4 “行业时报是 hook”

应改成:

> 行业时报是职业数据更新触发器,不是内容产品。

---

## 10. 最终建议版本

建议把产品方向正式改成:

> **C-side Career Ecosystem for AI Recruiting**  
> 面向 C 端用户的职业资产管理产品。用户获得简历更新、能力地图、能力证明和私密机会控制;平台获得持续更新、用户授权、结构化的候选人职业数据,反哺 B 端 AI 招聘产品。

对外一句话:

> 自动整理你的简历、项目和 AI 工作流,生成持续更新的职业能力档案。默认私密,需要时分享,合适机会来时由你决定是否开放。

对内一句话:

> 用真实 C 端利好换取用户持续授权,构建 LinkedIn 无法提供的新鲜、多维、可验证候选人数据生态。

---

## 11. 下一步建议

### 11.1 建议新增产品 spec

基于本审计,应新增一份 `v2_mvp_ecosystem_spec.md`,不要再只写战略。

这份 spec 应包括:

1. 用户 onboarding。
2. 简历 / LinkedIn export / profile 导入。
3. 技能抽取与用户确认。
4. 外部证据源连接。
5. Evidence card 生成。
6. 机会偏好设置。
7. 数据权限控制。
8. B 端如何消费授权数据。
9. 90 天数据指标。

### 11.2 建议重写 90 天实验

90 天实验应从“产品好不好用”改成“生态能否成立”。

关键问题:

- 用户是否愿意给职业数据?
- 用户是否愿意更新职业数据?
- 用户是否愿意授权特定机会使用?
- B 端是否认为这些数据比 LinkedIn 更有增量?

### 11.3 建议补充 primary research

Raw data 最大不足仍然是缺用户访谈。尤其要访谈:

- 中层 marketer
- 不发 LinkedIn 的 silent professionals
- recruiter / sourcer
- B 端 TA buyer
- 已经用 AI 改造工作但没有公开展示的人

---

## 12. 最终一句话

全面读 raw_data 后,最清晰的判断是:

> 这个项目不能被理解为“做一个 C 端工具顺便采数据”,也不能被理解为“为了 B 端采数据做一个 C 端壳”。正确理解是:通过真实有利于 C 端用户的职业资产管理产品,建立一个用户自愿持续更新的职业数据生态;这个生态的最终商业价值在 B 端 AI 招聘推荐和候选人触达。
