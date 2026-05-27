# Phase 04 — "默认私密" vs "默认展示" 两种产品模式深度对比

## 模型选择
- 搜集 sub-agent:**sonnet**
- 分析 sub-agent:**opus**(全程)— 这是要给出明确推荐路径的关键 Phase

## 目标
不是空谈"私密好还是展示好",而是基于两组案例的真实数据,得出**对我们的明确推荐路径 + 理由**。Phase 08 综合时会依赖这一份。

## 调研内容

### A. 私密模式案例(深度分析)
对以下逐个回答:增长曲线、留存(D30/D90)、变现路径、数据真实性、用户公开比例、与"反哺 B 端"目标的契合度:

1. **Notion** — 部分公开但默认私密;3000 万+ 用户,如何变现
2. **Obsidian** — 极度私密,本地优先;真实用户规模(他们公布过吗?),变现(sync $)
3. **Strava — 私密配置部分** — 70% 用户 default public,但仍有重要的私密层(heart rate, 病史)。注意 Strava 的特殊性
4. **Roam Research** — 兴起、衰落
5. **Mem** — AI 笔记,defunct?或转 pivot
6. **Apple Health** — 极致私密,但作为系统级,无可比性
7. **Day One**、**Bear** 等纯日记类
8. **Whoop** — 私密健康数据 → 部分 social feed
9. **Otter.ai** — 录音 / 转写,默认私密

### B. 展示模式案例(深度分析)
同样字段:

1. **LinkedIn** — 1B 用户,但留存和"public ratio"几何?
2. **Instagram** — 高度展示,真实性争议
3. **X (Twitter)** — 公开默认,但 follower 比例与"展示意愿"
4. **Substack** — 内容创作 = 展示
5. **Behance / Dribbble** — 视觉作品展示
6. **GitHub** — 公开代码,默认 public(但有 private repo);开发者的"展示"含义
7. **Strava — 公开模式** — 70%+ 默认 public,Activity Feed

### C. 关键交叉对比表
列一张表:产品 × [增长曲线斜率 / D30 留存 / D90 留存 / ARPU / 用户公开比例 / "我们能从中复制的设计" / "与 B 端反哺契合度"]。

数据来源诚实:能找到就标真实数字,找不到就标"unknown"或"基于 X 推断"。

### D. 混合模式可行性
- **Strava 模式**:私密录入 + 公开 feed,用户自选。Strava 的成功是不是混合的胜利?
- **LinkedIn 模式**:默认展示 + 部分私密(salary info)。
- **GitHub 模式**:public 是默认状态,private 是 paid feature(对个人)。
- **Notion 模式**:私密为主,public publishing 是 escape valve。

对我们,哪种混合最契合?具体设计是什么(默认状态、私密层、公开层的形态)?

### E. 与 B 端反哺契合度
- 私密模式下,用户数据 → B 端的路径(自愿 opt-in / 匿名聚合 / 不能反哺)
- 展示模式下,用户数据 → B 端的路径(几乎天然反哺,但有隐私顾虑)
- 23andMe(私密数据 + B 端医药公司变现)的真实历史 + 2025 破产前后的争议
- LinkedIn(公开数据 + Recruiter 产品反哺)的真实路径

## 数据源指引
- 公司 IR / SEC filings(LinkedIn S-1 当年、Strava 私募信息、Notion 估值轮)
- a16z / Sequoia 公开 portfolio company 分析
- Stratechery / Lenny 关于产品模式的文章
- Tom Tunguz、Reforge 关于留存的数据
- HN 讨论:"why Notion / Strava / GitHub model works"
- 23andMe 破产报道(2025)
- Lenny 关于 retention 的文章

## 输出要求

### 结构
保存到 `analysis/04_private_vs_public_products.md`,章节:
1. TL;DR + **明确推荐路径**(放最前面)
2. 私密模式案例(A,带数据)
3. 展示模式案例(B,带数据)
4. 交叉对比表(C)
5. 混合模式可行性 + 我们的具体设计建议(D)
6. 与 B 端反哺契合度(E)
7. **决策矩阵 — 我们应该选哪条**(opus 必须明确表态,不骑墙)
8. **对我们产品的启示**(具体到产品决策)
9. **调研局限性**(尤其留存/ARPU 数据多为非公开数据)

### 质量底线
- 必须给出明确推荐(可以是"私密为主+公开 escape valve""展示为主+私密 dashboard""完全公开""完全私密"中的一种或两种的具体组合)
- 推荐必须给出 3 条以上具体理由,且承认 trade-off
- 必须有反对意见模拟:如果选 A,持 B 派的人会怎么反驳?如何应对?
- 警觉:23andMe 案例(私密 → B 端)是个特殊的复杂故事,不要简单类比

### 引用
ID 从 citations_v2.json 当前最大值 +1

## 数据存储
- 私密案例:`raw_data/phase_04/private_cases/`
- 展示案例:`raw_data/phase_04/public_cases/`
- 数据表 csv-like:`raw_data/phase_04/comparison_data.md`
- 搜索日志:`raw_data/phase_04/searches.md`

## 期望页面规模
6-9 页(4500-7000 字)+ 对比表 + 决策矩阵。
