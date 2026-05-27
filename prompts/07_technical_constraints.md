# Phase 07 — 技术、合规、商业的真实约束

## 模型选择
- 搜集 sub-agent:**sonnet**(查 API 文档、读 GDPR/CCPA 法条、查 ToS 等忠实工作)
- 分析 sub-agent:**opus**(判断这些约束如何 reshape 产品形态)

## 目标
**让产品方在动手设计前,清楚知道哪些路是死路、哪些路是窄道、哪些路是宽路。**
约束不是 deal-breaker 列表,是设计 brief。

## 调研内容

### A. 多平台数据聚合的真实门
**这是产品形态的核心约束**。对每个平台,具体回答:[API 现状 / OAuth scope / rate limit / 成本 / ToS 限制 / 数据完整性]:

1. **GitHub**
   - REST + GraphQL API,免费 5000 req/hr(认证后)
   - OAuth scopes 中"读取 user public repo + bio + README"是可以的
   - ToS 允许聚合自己的数据吗?第三方代查呢?
   - 数据完整性:很高
2. **X (Twitter)**
   - 2023 以来 API 大幅收费,Basic $200/月(rate limit?),Pro $5000/月
   - 用户能授权第三方读取自己的 timeline / bookmarks 吗
   - 通过用户授权(OAuth)能拿到什么 vs 通过 paid scraping
   - ToS 明确禁止 scraping(legal cases:Meta v. Bright Data)
3. **Substack**
   - **无官方 API**。RSS 是有的。能通过 RSS 抓 newsletter 内容
   - 用户能"导出"自己的 Substack content 吗(yes,后台可导出)
   - ToS 限制
4. **Behance**
   - Adobe API:有,但需要审批
   - OAuth + Read scope
5. **Dribbble**
   - API 2024 仍可用,有限的 endpoint
6. **个人网站**
   - 无统一,scraping 是技术上的选项,但 ToS 不一定允许
   - Reader API 类工具(Readability)
7. **LinkedIn**
   - 极度封闭。Sign-In with LinkedIn 只给基本字段。Talent Solutions API 要企业账号
   - **大规模个人 profile 数据获取基本不可能合法**
8. **Medium**:有 API,基础
9. **Notion**:Public API,但 user 数据获取要他们 share token
10. **Mirror / Paragraph**(Web3)— 公开链上数据

**总结表**:平台 × [API 可用性 / 成本 / OAuth 用户授权可拿到的字段 / 我们的 product 在这平台上能做什么]

### B. 隐私法规
1. **GDPR(欧盟)**
   - 个人数据定义、合法基础、用户权利(access / portability / erasure / objection)
   - "聚合用户多平台数据"这件事在 GDPR 下:用户明确同意 + 数据最小化 + 目的限定
   - 对"AI 生成个人洞察"的 implications:Automated Decision-Making (Art. 22)
   - 数据本地化:EU data residency 要求
   - 违反 GDPR 的真实 fines(Meta、Google 历史)

2. **CCPA / CPRA(加州)**
   - "sale of data" 定义,我们如果反哺 B 端是否构成 sale
   - opt-out 要求
   - "Sensitive Personal Information" 类别(职业信息算吗?需查)
   - 12 个月数据留存

3. **EU AI Act(2024 通过,2026 关键 deadline)**
   - "高风险"AI 系统定义:**人才招聘** 是明确列出的高风险类别
   - 对我们 B 端产品的直接影响(可能极大)
   - 对 C 端"AI 生成职业洞察"的影响
   - 时间表:2026-2027 关键 milestone

4. **数据本地化**
   - GDPR:数据可以在 EU 外存,但要 SCC + adequacy
   - 中国 PIPL(我们海外为主,但如果有中国用户呢)
   - 美国各州法律(VA, CO, CT, UT 类 CCPA)
   - 巴西 LGPD

### C. B 端反哺商业模式的历史
这一节看似离技术远,但其实是商业约束。
1. **LinkedIn — Recruiter 产品**
   - 怎么定价(seat 制,$8400-$10000/年/seat,变动)
   - 用户感知:LinkedIn 用户知道自己被 recruiter 搜索
   - 抗议历史
2. **Handshake — 大学就业服务**
   - 学生数据如何被企业方使用
3. **23andMe — DNA + 药企**
   - 2025 破产 + 用户数据被打包出售的舆论事件
   - 启示:**用户数据被卖给第三方时,即使最初有同意,事后舆论也会爆炸**
4. **早期 Facebook 广告变现路径**
   - 用户感知 vs 实际数据使用的脱节
5. **23andMe 的"自愿研究 opt-in"**(Sample, GSK $300M deal 2018)— 怎么设计的同意

### D. LLM 用于"个人洞察生成"的真实能力 + 设计模式
1. **Spotify Wrapped** — 怎么设计:数据 → 故事化呈现
2. **GitHub Wrapped / Year in Review** — 设计要点
3. **Strava 年度总结** — 设计要点
4. **Reddit Recap** — 怎么避免空洞
5. **Apple Wrapped(没做)** — 为什么 Apple 不做这个
6. **Notion AI、Mem.ai 等"个人 AI"** — 真实能力 vs 营销话术
7. **Barnum effect(巴纳姆效应)** — 避免方法:
   - 必须用户专属真数据(不能 generic 占星)
   - 必须有 falsifiable 细节(可验证的具体声明)
   - 必须留 escape hatch(用户能不同意 AI 推断)

## 数据源指引
- 平台官方 API 文档(developers.github.com, dev.twitter.com, developers.behance.com 等)
- GDPR.eu 官方解读、ICO(UK)指南、CNIL(法国)指南
- EUR-Lex 上的 GDPR Art. 22 / EU AI Act 全文
- CCPA / CPRA:oag.ca.gov
- 律所公开 blog:Cooley、Fenwick、WilmerHale、A&O Shearman 关于 AI Act + GDPR + employment
- TechCrunch / The Verge 关于 GDPR fines 报道
- 23andMe 破产 + 数据出售报道(2025)
- Stratechery、Ben Thompson 关于平台 API closure 的分析
- HN 讨论:"GDPR for startups", "X API pricing 2024", "Read.cv data export"
- 学术:Daniel Solove(隐私法权威)

## 输出要求

### 结构
保存到 `analysis/07_technical_constraints.md`,章节:
1. TL;DR(<500 字)
2. 多平台数据聚合约束(A,带完整对比表 + 每个平台具体可做/不可做)
3. 隐私法规(B,GDPR / CCPA / EU AI Act / 本地化各一节)
4. B 端反哺商业模式的历史教训(C)
5. AI 个人洞察的真实能力 + 设计模式(D)
6. **对我们产品的启示**(具体到产品形态约束:哪些功能可做,哪些会触发监管)
7. **调研局限性**

### 质量底线
- API 数据要查到 2025-2026 最新文档(API 政策变化快)
- 法规解读要附条款引用(Art. X 或 Section Y)
- 不要 over-claim 合规风险,也不要 under-claim
- 用真实 fine 数字让风险有"质感"(e.g., Meta GDPR €1.2B、TikTok €345M)

## 数据存储
- API 调研:`raw_data/phase_07/apis/`(每个平台一文件)
- 法规调研:`raw_data/phase_07/regulations/{gdpr,ccpa,euaiact,localization}.md`
- B 端反哺历史:`raw_data/phase_07/btc_history.md`
- AI 洞察设计模式:`raw_data/phase_07/ai_wrapped_patterns.md`
- 搜索日志:`raw_data/phase_07/searches.md`

## 期望页面规模
7-10 页(5500-7500 字)+ API 对比表 + 法规摘要表。
