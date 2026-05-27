# Phase 06 — 目标用户真实意愿的证据基础

## 模型选择
- 搜集 sub-agent:**sonnet**(收集真实数字)
- 分析 sub-agent:**opus**(从离散证据归纳"用户意愿模型",这是高复杂度判断)

## 目标
在动手做产品前,基于**公开真实数据**校准用户意愿:
- 他们愿意付钱吗?多少?
- 他们愿意从一个平台迁移到新平台吗?
- 他们"想被发现"的诉求强度?
- niche 工具 + 社区的留存看起来怎样?
- 他们愿意付出什么(数据/时间)换什么?

产出:**基于真实证据的"用户意愿模型"** — Phase 04 / 08 会依赖。

## 调研内容

### A. 付费意愿(真实数字)
1. **Lenny's Newsletter** — 付费订阅人数(公开过?)、价格、转化率
2. **Maven / Reforge / Pavilion** — course / membership 价格、报名人数、完成率
3. **Substack 付费转化率** — 行业平均(Substack 公布过 5-10% 的 paid conversion 区间)
4. **Figma 等设计工具 ARPU** — 设计师愿意为工具付多少
5. **Notion personal pro / Bear / Obsidian sync** — 知识工具个人付费 ARPU
6. **LinkedIn Premium** — Career / Business / Sales Navigator 付费用户数 + ARPU
7. **AI 工具个人付费**(ChatGPT Plus、Claude Pro、Cursor、Perplexity Pro)— 付费率

### B. 迁移意愿(真实数字)
1. **Read.cv** — 用户数峰值 / 关闭前活跃数,被关闭后用户去哪了
2. **Polywork** — peak users,user retention 数据
3. **Bento.me** — 当前用户数,留存
4. **Mastodon vs Threads vs Bluesky** — 从 X 迁移意愿的真实数据(Bluesky 用户数曲线、Threads 启动 1 亿之后的留存)
5. **Twitter → Substack 迁移**(2022-2024)— 真实数据

### C. "被发现"诉求强度
1. **LinkedIn #OpenToWork** — 用户比例(LinkedIn 官方数据 + LinkedIn talent reports)
2. **"Hire me" 标签使用频率**(GitHub / Twitter bio / personal sites)
3. **X bio "open to opportunities"** — 估算数
4. **Wellfound / AngelList Talent** — 用户主动公开 looking for work 的比例
5. **真实用户 self-reported job search 状态** — Glassdoor / LinkedIn talent insights

### D. niche 工具 + 社区的留存
1. **Maven** — 课程完成率、复购率
2. **Lenny's Slack / Pavilion / Reforge community** — 日活 / 月活
3. **Indie Hackers** — DAU、留存
4. **Product Hunt** — 用户留存
5. **Hampton / South Park Commons** — 付费 community 留存

### E. 用户愿意付出什么换什么(数据交换意愿)
1. **23andMe** — 用户为了基因报告愿意提供 DNA(然后被打包卖给 GSK),用户的事后反弹
2. **Strava** — 用户为了"和朋友比较"提供心率/GPS,被研究人员买数据
3. **Whoop** — 月费 $30 换"完整健康分析"
4. **Apple Health / Health Mate** — 用户上传健康数据换什么
5. **Spotify / Apple Music** — 用户上传听歌记录,换 Wrapped 等"年度报告"

**这是 Phase 06 最重要的一节**。归纳出"用户愿意付出 X 换 Y"的几个组合。

### F. 用户意愿模型(归纳)
基于以上证据,构建一个简单的用户意愿模型,例如:
- **付费意愿**:professional 类付费 SaaS / Newsletter ARPU 中位数大约 $X-$Y
- **数据贡献意愿**:用户愿意贡献 [类型 X] 数据,换 [类型 Y] 价值,前提是 [条件 Z]
- **公开意愿强度**:大约 [N%] 用户会公开主动展示,[M%] 会被动接受被搜索到,[K%] 拒绝任何 visibility
- **迁移成本**:从 [现有平台] 迁移到新平台,需要 [触发条件]

这个模型必须基于真实数字(D-level evidence 的也行,但要标注证据强度)。

## 数据源指引
- 公司 IR / earnings transcripts / S-1
- a16z / Sequoia / Reforge 公开数据
- LinkedIn workforce reports / talent insights
- Substack 公开 metrics
- 创始人复盘 thread(X)
- HN 讨论:"how many open to work users", "Substack conversion rate"
- 学术研究(Pew / 牛津 / 哈佛 商学院 case studies)
- Stratechery / Tom Tunguz 关于 SaaS 留存的文章
- 23andMe 破产报道(2025)关于用户数据观感
- Reddit:r/Substack 创作者复盘、r/SideProject、r/Entrepreneur

## 输出要求

### 结构
保存到 `analysis/06_user_willingness_evidence.md`,章节:
1. TL;DR
2. 付费意愿数据(A,带真实数字)
3. 迁移意愿数据(B)
4. "被发现"诉求强度(C)
5. niche 工具 + 社区留存数据(D)
6. 数据交换意愿(E)
7. **用户意愿模型**(F — 这是给 Phase 08 / 04 用的关键产出)
8. **对我们产品的启示**(具体决策建议:免费/付费、定价区间、数据收集策略)
9. **调研局限性**(尤其留存数据多为非公开)

### 质量底线
- 每个数字必须有出处和年份
- 区分"真实公开数据"vs"行业估算"vs"我推断"
- 用户意愿模型必须明确证据强度(high / medium / low / inferred)
- 警觉:专业 SaaS / newsletter 用户的付费意愿,显著高于一般 C 端用户

## 数据存储
- 各类数据收集:`raw_data/phase_06/{pricing,migration,visibility,retention,data_exchange}/`
- 搜索日志:`raw_data/phase_06/searches.md`
- 用户意愿模型草稿:`raw_data/phase_06/willingness_model_draft.md`

## 期望页面规模
6-8 页(4500-6000 字)+ 数据表。
