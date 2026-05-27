# Phase 03 — 三个目标人群的真实日常画像

## 模型选择
- 搜集 sub-agent:**sonnet**(收集 podcast 摘录、newsletter 文章、reddit 帖、LinkedIn 帖)
- 分析 sub-agent:**opus**(归纳画像、判断 TAM、识别"沉默多数")

## 目标
对 Marketing / Design / Consulting 三个目标群体,基于公开真实素材构建 3 套各 10 人的画像,得到对真实 professional 日常的有质感认知。
**不是营销 persona** — 不要写"Sarah, 28, marketing manager, drinks oat milk"。是基于真实人物的真实素材的归纳。

## 调研内容

### A. 每个领域选 10 个真实人物(共 30 个)
每个人物字段:
- 名字、岗位、所在组织、所在地
- 公开背景(可被验证的来源:LinkedIn / podcast / Substack)
- 他们使用什么工具(尤其 AI 工具)
- 公开发言中显示的动机和痛点
- 典型行为(频率发什么内容、在哪发、为什么发)
- 来源:1-2 个具体公开素材(URL + 引用)

**Marketing 候选**(实际选 10):
- Lenny Rachitsky、Justin Welsh、Anne Handley、Amanda Goetz、Katelyn Bourgoin、Rand Fishkin、Harry Dry、Sahil Bloom、Codie Sanchez(创业 marketing),以及 2-3 个非 famous 但有公开足迹的中层 marketer

**Design 候选**:
- Jules Forrest、Femke、Linus Lee(设计 + AI)、Soleio、Tobias Van Schneider、Frank Chimero(回归)、John Maeda、Jenny Wen、Ridd(Dive Club)、加上 2-3 个非 famous 的中层 designer

**Consulting 候选**:
- 难找:咨询行业的人公开发言相对少
- 类型:
  - 大厂内的 strategy/ops 但公开 newsletter:e.g., Tom Critchlow、Anthony Pierri(从 marketing 角度)、Roger Martin(retired Dean)
  - Indie consultant:Tom Critchlow、Paul Millerd、Khe Hy、Justin Welsh(也算)、Sari Azout
  - McKinsey/BCG/Bain 公开 LinkedIn 创作者:难,但存在
  - 创业咨询:Brian Balfour、Brian Halligan(更产品)
- 注意:这一组也要有 2-3 个非 famous 的中层

### B. 三个群体的对比维度
对三个群体回答:
1. **"被看见"意愿强度** — 在 1-10 上:谁更愿意公开?
2. **公开发言的具体内容类型** — 思考、教程、案例、自我营销?
3. **平台偏好** — Marketing 偏 LinkedIn+X;Design 偏 Twitter+Behance+个人站;Consulting 偏 newsletter+LinkedIn(假设,需验证)
4. **变现方式** — 怎么把"被看见"转化成收入(课程、咨询、付费 newsletter、Job offer)
5. **AI 使用程度** — 公开承认用什么 AI 工具,频率,场景

### C. 沉默的多数
**这是 Phase 03 的核心任务**:HN/Reddit/X/LinkedIn 上发声的人不代表所有 Marketing/Design/Consulting 从业者。要主动识别"我们看见的样本偏在哪一头"。

证据:
- LinkedIn 上发原创内容的活跃创作者占比(LinkedIn 公开过吗?)
- Twitter Marketing 圈 ≠ 全部 marketers
- r/marketing 的活跃用户 vs LinkedIn 上的 marketing manager:重叠多少
- Substack marketing newsletter 订阅者 vs 总 marketing 从业人口:百分比

明确表达:**我们的产品,如果只服务"公开发声的人",TAM 是多少?如果要服务沉默多数,产品形态会变成什么?**

### D. 可触达 TAM(基于真实数据)
- 美国 + 西欧 marketing professionals 总人数(BLS / Eurostat / LinkedIn talent reports)
- 同上 designers
- 同上 management consultants
- 其中"AI early adopters"占比(各种调研:Edelman、McKinsey、a16z 公开数据)
- "在 newsletter / X / LinkedIn 上公开发声"的占比(可用 Lenny's Newsletter 订阅量 / marketing PM 总数 估算)

### E. 文化差异
美国 vs 英国 vs 德国 vs 法国 vs 北欧 vs 加拿大:
- "公开自我营销"接受度差异
- 隐私敏感度差异
- 平台偏好差异
- 给我们的具体意义(launch 区域优先级)

## 数据源指引
- LinkedIn talent reports、Glassdoor、BLS、Eurostat
- Lenny's Newsletter 的 audience reports / Substack 公开数据
- HN 讨论:"How marketers use AI", "design portfolio in 2025"
- Reddit:r/marketing(800k+)、r/userexperience、r/web_design、r/consulting(360k+)、r/managementconsulting
- Podcast:Lenny's Pod、Design Details、Strong Opinions Loosely Held、Acquired(高质量真实人物)
- Substack:Marketing/Design/Consulting 头部 newsletters 的 audience 调研

## 输出要求

### 结构
保存到 `analysis/03_target_users_daily_life.md`,章节:
1. TL;DR
2. Marketing 10 人画像 + 群体特征
3. Design 10 人画像 + 群体特征
4. Consulting 10 人画像 + 群体特征
5. 三群体对比矩阵(B)
6. **沉默的多数**(C — 给我们具体警觉)
7. 可触达 TAM(D — 真实数字)
8. 文化差异(E)
9. **对我们产品的启示**(应该优先服务哪个群体?为什么?)
10. **调研局限性**(诚实:30 个样本不能代表数百万)

### 质量底线
- 真实人物必须有公开来源(LinkedIn / podcast / Substack URL)
- 不能"为了写报告"扭曲人物形象
- 每个 TAM 数字必须有出处和年份
- 必须明说"我们看见的样本偏在哪一头"

## 数据存储
- 每个人物:`raw_data/phase_03/people_marketing.md`、`people_design.md`、`people_consulting.md`
- TAM 数据:`raw_data/phase_03/tam_data.md`
- 搜索日志:`raw_data/phase_03/searches.md`

## 期望页面规模
6-9 页(4500-7000 字)+ 画像表 + 对比矩阵。
