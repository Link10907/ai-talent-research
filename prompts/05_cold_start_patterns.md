# Phase 05 — 类似产品的冷启动真实路径

## 模型选择
- 搜集 sub-agent:**sonnet**
- 分析 sub-agent:**opus**(归纳冷启动 pattern,给具体策略建议)

## 目标
**回答"如果是我们,第一批 1000 用户从哪来,需要多久,需要多少钱"。**
不要泛泛而谈 "build a community"。

## 调研内容

### A. 成功案例:深度还原冷启动路径

1. **GitHub(2008-2012)**
   - 第一批用户:Ruby 社区(Tom Preston-Werner 在 Ruby on Rails 圈)
   - 早期增长:Rails Conf / 邮件列表 / 开源项目"上 GitHub"成为社区行为
   - 关键决策:免费 + paid private repo;公开默认
   - 到 100 万用户用了多少时间(2009 → 2011 100 万 repo)
   - 是否邀请制(否)

2. **Strava(2009-2014)**
   - 创始团队背景:Mark Gainey + Michael Horvath
   - 第一批用户:旧金山自行车俱乐部(湾区 cycling 圈)
   - 关键决策:Segments(让活动可比);Kudos(轻社交)
   - 到 100 万 active users 用了多少时间
   - 早期变现:premium subscription

3. **LinkedIn 早期(2003-2008)**
   - 第一批用户:Reid Hoffman 个人网络(PayPal 黑帮)
   - 邀请制:是 — 早期纯邀请,后变为 freemium
   - 到 100 万、500 万、5000 万的时间表
   - 关键变现:Recruiter 产品启动时间(2005-2008)

4. **Substack(2017-2021)**
   - 第一批 newsletter 创作者:Hamish McKenzie 邀请的 power users(Bill Bishop / Sinocism、Matt Taibbi)
   - 关键决策:10% take rate;creator-friendly;不广告
   - 到 100 万付费订阅时间(2021 年报告)
   - 邀请制?不是,但有"邀请大牌"策略

### B. 失败 / 挣扎案例:深度分析

1. **Polywork($44.5M 烧光)**
   - 估值峰值:$1.45B(2021)
   - 真实月活峰值(可知吗)
   - 死因假说:产品定位不清?TAM 错?LinkedIn 阴影?Bullhorn 收购的隐情
   - **关键 lesson(给我们)**

2. **Read.cv**
   - 2020-2024 路径
   - Perplexity 收购:为什么 Perplexity 要 acqui-hire
   - 用户体感:Reddit / X 上的真实反应
   - 死因(产品负责人复盘?)
   - **关键 lesson**

3. **Lunchclub**(连接 1-on-1 meetings)
   - 2017-2023 路径
   - 死因
   - **关键 lesson**

4. **Path**(社交身份,Dave Morin,2010-2018)
   - 死因复盘(已有公开复盘文章?)
   - **关键 lesson**

5. **Contra**
   - 目前状况
   - "freelance 职业身份产品"为什么没起来

### C. 冷启动 pattern 归纳
基于以上案例,提取 5-8 个真实可复用的 pattern。例如:
- "Niche 死忠社区先占,再扩"(GitHub-Ruby、Strava-旧金山 cycling)
- "邀请制+大牌"(LinkedIn、Substack)
- "用户产品和创作者产品的不同冷启动"
- "B 端 / C 端双轮驱动"(LinkedIn)
- "病毒系数 vs Daily Active"

### D. 对我们的具体启示
**关键问题**(必须回答):
1. 第一批 1000 用户从哪来?给出 3-5 个具体的、可执行的渠道(不要写"通过社交媒体"这种空话)。可能候选:
   - 海外 AI + Marketing newsletter 读者(Lenny / Justin Welsh 受众)
   - 海外 design + AI 推特圈(如 Linus Lee 周边)
   - r/marketing、r/userexperience 等 subreddit
   - HN Show / Product Hunt(适合吗?)
   - YC + a16z portfolio 的 marketing/design head
   - 收购小社区流量(可能性极低)
   - 邀请知名 Marketing/Design KOL 试用 + 推荐
   - 招 community manager(创业初期不现实)
   - **请给具体的 5 个名字(谁能成为第一个 100 用户)**

2. 邀请制 vs 公开注册?**给明确答案**+ 理由 + 时间窗(什么时候切换)

3. 冷启动期长度:从 launch 到 product-market signal 多久?给出基于历史案例的估算区间

4. 所需资金:6 个月 MVP + 冷启动期需要多少?(产品工程 + 内容 + community + 运营)

5. **如果我们失败了,最可能死在哪个环节?**(诚实)

## 数据源指引
- 创始人公开访谈(Lenny's Pod、Acquired、How I Built This)
- Crunchbase 融资轮 + 估值
- 公司 official blog 的里程碑
- HN 上的 Show HN 帖 + early users 评论
- 失败复盘:Sebastian Marshall / Failory.com / Indie Hackers 失败访谈
- 媒体:TechCrunch / The Verge / Forbes 关于这些产品的报道
- 创始人 X/Twitter 的复盘 thread

## 输出要求

### 结构
保存到 `analysis/05_cold_start_patterns.md`,章节:
1. TL;DR + 我们冷启动的最高优先级建议(前置)
2. 成功案例真实还原(A,4 个,每个含真实数字)
3. 失败案例真实还原(B,5 个,每个含真实数字 + lesson)
4. Pattern 归纳(C)
5. **对我们的具体启示**(D — 必须回答全部 5 个问题,带 5 个具体人/社区名)
6. **调研局限性**(冷启动数据往往后期粉饰)

### 质量底线
- 不要写"focus on community"这种空话。每条建议必须可执行
- 每个案例的死因要承认"多因素",不要单因
- 估算数字(资金、时间)要有 sanity check 区间
- 必须给出 5 个具体的"谁能成为第一个 100 用户"的人名或社区

## 数据存储
- 成功案例:`raw_data/phase_05/success/`
- 失败案例:`raw_data/phase_05/failures/`
- 搜索日志:`raw_data/phase_05/searches.md`

## 期望页面规模
6-9 页(4500-6500 字)+ 时间线表。
