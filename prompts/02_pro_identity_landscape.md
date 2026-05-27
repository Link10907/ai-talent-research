# Phase 02 — 海外职业身份/展示产品真实景观

## 模型选择
- 搜集 sub-agent:**sonnet**
- 分析 sub-agent:**opus**(需要从 30-50 个真实人物归纳出 pattern,需立场)

## 目标
超越"LinkedIn 是 X / Y 是 Z"的肤浅产品对比,得到对"海外 professionals 如何展示自己"这件事的真实经验性认知。要回答:**真实世界里,一个目标用户的展示分布长什么样?他们用什么、不用什么、为什么。**

## 调研内容

### A. 主流产品/形态列表
对以下逐个回答 [谁用、为什么用、典型用法、维护成本、用户得到什么]:

1. **LinkedIn** — 默认平台,工作经历+人脉
2. **个人网站**:
   - Cargo, Carrd, Squarespace(创意端)
   - Bento.me(链接聚合,2024-2026 起势)
   - Notion 公开页(轻量,quasi-personal site)
   - Webflow,Framer(更专业)
3. **X (Twitter) profile** — bio + pinned tweet 作为名片
4. **Substack about 页** — 内容创作者的 de facto 简介
5. **Behance / Dribbble / Are.na** — 视觉创意端
6. **GitHub Profile README** — 开发者的展示新形态
7. **Read.cv**(2024 关闭,Perplexity 收购,值得深入"为什么"分析)
8. **AngelList / Wellfound** — startup-oriented
9. **Polywork**(已沉寂,值得分析"为什么死")
10. **LinkedIn Creator Mode**(默认在 LinkedIn 上,但是一种新身份形态)
11. **Medium author page、Mirror、Paragraph** — 内容平台 author 页
12. **GitHub Sponsors profile、Patreon、Buy Me a Coffee profile** — 创作者支持型展示页
13. **About.me、Crunchbase Person、Wikipedia(对极少数人)**

### B. 真实人物展示分布
找 30-50 个真实人物(覆盖 Marketing / Design / Consulting / Engineering / AI + 创业者 / 大厂员工 / 独立工作者)。
对每个:
- 名字、岗位、所在组织(或独立)
- 他们公开使用的展示渠道清单
- 主"客厅"是哪个(发新东西第一时间发哪)
- 哪个是"门面"(别人最常通过哪找到他们)

从中归纳 4-7 个真实模式(例如:"开发者的双面性 — GitHub 是作品,X 是个性,LinkedIn 是 fallback")。

### C. 文化与心理
- "Personal Branding" 在海外的演变(2015 Gary Vee → 2020 Justin Welsh → 2024-2026 AI 影响)
- "Build in Public" 文化:谁在做、为什么、有什么真实代价
- LinkedInLunatics 现象(reddit r/LinkedInLunatics):它代表了什么样的文化反弹
- 隐私偏好的地区差异:欧美 vs 北欧 vs 德语区
- 自我展示意愿的代际差异

### D. 2024-2026 新出现的产品
扫描:Bento.me / Linktree(职业向延伸)/ Reflect / Tldraw / Famous AI 等。
"AI + 职业身份"赛道新玩家(GenAI 兴起后)。
重点:是否有"AI 帮你聚合多平台产出"型产品已经出现?他们活得怎样?

### E. Read.cv / Polywork / Bento 的死因(或挣扎)分析
- Read.cv 为什么 2024 关闭,被 Perplexity 收购后的处境
- Polywork 为何从估值 $1.45B 跌入沉寂
- Contra 现在状况
- Lunchclub 死因
- Path(社交身份,Dave Morin),为何死
- 关键 lesson(给我们)

## 数据源指引
- 各产品官网 + Crunchbase
- HN 搜索:"Read.cv shutdown", "Polywork", "career identity product"
- TechCrunch / The Verge / Wired 历史报道
- 创始人/产品负责人公开访谈(Lenny's Pod、Ben Tossell、Pieter Levels 等)
- Reddit:r/marketing, r/design, r/consulting, r/cscareerquestions, r/freelance
- X/Twitter:相关产品创始人的复盘 thread
- LinkedIn Lunatics subreddit(为文化反弹证据)
- product hunt 历史 launches

## 输出要求

### 结构
保存到 `analysis/02_pro_identity_landscape.md`,章节:
1. TL;DR(<500 字)— 用 5 句话说清"海外 professionals 怎么展示自己"
2. 产品/形态全景(A,带"谁用、为什么、典型用法、维护成本、用户得到什么"字段)
3. 真实人物展示分布与归纳(B,带 30-50 人样本表 + 4-7 个模式)
4. 文化与心理(C)
5. 新出现的产品(D)
6. 死亡案例的真实教训(E)
7. **对我们产品的启示**
8. **调研局限性**

### 质量底线
- 不要做 LinkedIn 的产品 review。重点是"用户的展示分布",产品列表是为这个服务的
- 30-50 个真实人物画像必须有名字(公开人物),不能编造
- 死亡案例分析必须区分"产品问题"vs"市场问题"vs"团队问题"
- 标注"我观察到"vs"我推断"
- 关键结论必须有反对证据扫描

### 引用与样本警觉
- 引用 ID 从 citations_v2.json 当前最大值 +1 继续
- 警觉:产品死因解释往往事后合理化,要谨慎

## 数据存储
- 抓取:`raw_data/phase_02/YYYYMMDD_<source>_<topic>.md`
- 真实人物样本:`raw_data/phase_02/people_sample.md`
- 死亡案例:`raw_data/phase_02/dead_products.md`
- 搜索日志:`raw_data/phase_02/searches.md`

## 期望页面规模
analysis/02 报告 5-8 页(3500-6000 字)+ 表格。
