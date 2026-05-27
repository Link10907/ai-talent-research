# Phase 01 — Newsletter 生态全景

## 模型选择(给主 agent)
本 Phase 派发 sub-agent 时,主 agent 自主选择模型,遵循 v2_README 的 auto mode 原则。
- **搜集 sub-agent**:sonnet(忠实搜索、抓取、归类)
- **分析 sub-agent**:opus(归纳 pattern + 立场)

## 目标
让一个完全不懂海外 newsletter 生态的人(项目负责人)看完后,具备有质感的认知。
**这不是综述文章**,是让一个产品决策者读完后能判断"newsletter 生态对我们意味着什么"。

## 调研内容(分 6 块)

### A. 生态是什么 / 为什么重要(产品负责人视角)
- 海外 newsletter 在 2020-2026 的发展曲线(Substack 上市预期、Beehiiv 出现、ConvertKit 转型 Kit、Ghost 增长)
- 它和 Twitter/X、LinkedIn 长文、博客的差异和定位
- 为什么 newsletter 在职业内容生态成为"主理人经济"主战场之一
- 对一个职业身份产品的三种意义:**竞品 / 渠道 / 内容形式**

### B. 平台层对比
对 Substack / Beehiiv / ConvertKit (Kit) / Ghost / Bulletin (Meta 已死) / Revue (Twitter 已死) / LinkedIn Newsletter / Medium Newsletter 各回答:
- 创立年份、所有权、估值/营收(如可知)
- 商业模式:订阅分成、SaaS 月费、广告等
- 目标用户(创作者画像)
- 杀手锏与短板
- 2024-2026 的关键事件

### C. 商业模式真实数据
- Top newsletter 的付费转化率(行业基准:1-10%,但具体多少?)
- ARPU、留存、流失
- Substack 公开过哪些数字?Beehiiv 的官方/非官方数据?
- 创作者实际能赚多少(中位数 vs 头部)

### D. Marketing / Design / Consulting 三领域 Top Newsletter
每个领域列 8-15 个真正有影响力的 newsletter,字段:
- 名称、主理人、平台、订阅量(尽可能真实数字)
- 主题、定价(免费 / 付费 tier)
- 起步时间、关键增长事件
- 真实读者画像(主理人自述或第三方观察)

参考清单(可扩展,但要核实):
- Marketing:Lenny Rachitsky、Marketing Brew(morning brew 系)、 Demand Curve、Stacked Marketer、Marketing Examined、Reforge 系
- Design:Refactoring UI / 已散落的设计 newsletter、Femke、Jules Forrest 等。注意 design 领域 newsletter 没 marketing 多
- Consulting:Strategy Toolkit、Lenny(部分覆盖)、HBR 系、McKinsey 公开内容、A Smart Bear、StrategyU
**要求**:用真实订阅量和真实主理人数据,不要瞎编。如不可得,标 "TBD" 并在 questions 中记。

### E. 对我们产品的三种意义
- **作为竞品**:Substack about 页是不是事实上的"轻量职业身份"?Lenny 的 newsletter + 个人品牌是不是已经是一种职业身份?
- **作为渠道**:第一批 1000 用户能否通过被相关 newsletter 提及而来?
- **作为内容形式**:我们的产品是否要内置 newsletter 输出能力?

### F. 30 分钟阅读清单
推荐 5 个"必订" + 30 分钟读物,让产品负责人快速 onboarding。

## 数据源指引
- 平台官网 (substack.com, beehiiv.com, kit.com, ghost.org)
- Substack discover / Top in Business / Top in Marketing / Top in Design
- substackrankings.com、 newsletter.com、buttondown 类聚合
- 创作者公开年终复盘(Lenny 年终、Justin Welsh "Saturday Solopreneur")
- Reddit:r/Substack, r/newsletters, r/Entrepreneur
- HN:搜索 "newsletter", "Substack", "Beehiiv"
- Twitter/X:相关主理人公开账号
- 媒体报道:The Verge、TechCrunch、Axios 关于 Substack/Beehiiv 的报道

## 输出要求

### 结构(分析 sub-agent 用)
保存到 `analysis/01_newsletter_ecosystem.md`,章节:
1. TL;DR(<400 字)
2. 生态全景(A 部分)
3. 平台层对比(B,可用表格)
4. 商业模式真实数据(C,真实数字 + 误差区间)
5. 三领域 Top Newsletter(D,带订阅量)
6. 对我们产品的三种意义(E,明确立场)
7. 30 分钟 onboarding 清单(F)
8. **对我们产品的启示**(3-5 条带具体行动可能)
9. **调研局限性**(诚实)

### 引用规范
- 每个数字、每个主张后必须有 `[VXXX]`
- 引用追加到 `citations/citations_v2.json`,新 ID 从当前最大值 +1 递增

### 质量底线
- 不堆砌:不要把 20 个 newsletter 名字一字排开,要选出"对产品负责人最有信号价值"的
- 必须区分"事实"vs"我推断"
- 必须主动找反对证据:newsletter 是否被高估了?是不是 Substack 自己宣传的回声室?
- 标注证据强弱(high / medium / low)

## 数据存储
- 抓取:`raw_data/phase_01/YYYYMMDD_<source>_<topic>.md`,文件开头 200 字 TL;DR
- 搜索日志:`raw_data/phase_01/searches.md`
- 关键 newsletter 信息可整理为 `raw_data/phase_01/newsletters_index.md`

## 期望页面规模
analysis/01 报告 4-7 页正文(2500-5000 字)+ 数据表格,不超过 8 页。
