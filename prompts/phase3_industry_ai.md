# Phase 3: 跨行业 AI 渗透调研(行业模板)

## 目标
对单个行业,调研 AI 在该行业的渗透程度、AI 能力如何被定义和评估、
该行业的 professional 如何展示 AI 能力、是否是产品的好切入点。

## 使用方式
这是模板。10 个行业各启动一个 sub-agent,把 <INDUSTRY> 替换为:
legal / marketing / design / sales / operations / education / 
healthcare / finance / consulting / hr

每个 sub-agent 独立执行,产出存到 analysis/phase3_<INDUSTRY>.md 和 
raw_data/phase3/<INDUSTRY>/

## 对每个行业,需要回答

### A. AI 渗透成熟度
- 该行业目前 AI 使用普及度(0-10)
- 哪些具体工具/工作流被广泛采用
- 哪些子岗位 AI 渗透最深
- 该行业的 AI 拐点是否已到

### B. "AI 能力"在该行业的具体定义
- 这个行业的"AI 能力"具体指什么(工具掌握?prompt 能力?工作流设计?)
- 招聘方如何评估这种能力
- 已经有显性 AI 要求的 JD 长什么样

### C. 用户行为
- 这个行业的人如何展示自己的 AI 能力
- 是否有行业专属的展示平台
- 他们的痛点是什么

### D. 作为切入点的评估
- 用户可触达性(在哪里能找到他们)
- 用户付费/分享意愿(基于该行业特征推断)
- 市场规模
- 推荐切入优先级(0-10)+ 理由

## 数据源
- 该行业的专业 subreddit
- 该行业的行业媒体 / Substack / newsletter
- X 上该行业的 KOL
- 该行业 AI 工具的 Product Hunt 页面
- Indeed/LinkedIn 上该行业的 JD 抽样

## 输出格式
analysis/phase3_<INDUSTRY>.md,按上面 A/B/C/D 结构。

## 主 agent 的汇总任务
所有 10 个行业完成后,生成 analysis/phase3_overview.md:
- 10 个行业对比矩阵(成熟度、用户特征、切入优先级)
- Top 3 推荐切入行业 + 理由
- 跨行业的共性观察
- 调研局限性
