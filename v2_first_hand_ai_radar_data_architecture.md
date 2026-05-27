# V2 一手 AI Radar 数据获取与实现架构

**日期**: 2026-05-27  
**对象**: Metix.ai C 端 Career Radar / Skill Tree / Action Proof 方向  
**核心问题**: 如何获取数据，如何保证 AI 新闻尽可能是一手信息，是否需要用 AI Agent 实现。

---

## 0. 一句话结论

AI Radar 不能靠“让 AI Agent 上网搜新闻”来保证质量。

正确架构应是：

> 白名单一手源 + API / RSS / webhook / 官方页面监控 + 原文归档 + provenance 评分 + AI Agent 解释职业含义。

AI Agent 不应是信息源本身。Agent 的职责是发现、分类、去重、验证、解释和个性化，而不是凭空“找新闻”。

---

## 1. 什么叫“一手 AI 新闻”

我们内部需要把新闻分级，不要把媒体转述、KOL 解读、二手 newsletter 都叫一手。

### 1.1 来源等级

| 等级 | 定义 | 示例 | 是否进入 Radar 主流 |
|---|---|---|---|
| A0 官方原始源 | 发布者自己宣布或更新 | OpenAI / Anthropic / Google DeepMind 官方 blog、模型文档、pricing、changelog | 是 |
| A1 项目 / 作者原始源 | 项目维护者或论文作者发布 | GitHub release、arXiv paper、OpenReview submission、Hugging Face model card | 是 |
| A2 我们自有一手源 | Metix.ai B 端招聘需求和 JD 信号 | OpenJobs Recruiter 中岗位技能变化、招聘方搜索行为 | 是 |
| B 权威二手解释 | 媒体、分析师、newsletter 解读 | The Verge、TechCrunch、Ben Thompson、Lenny 等 | 只做补充 |
| C 社交热度 | X、HN、Reddit、LinkedIn 讨论 | 热帖、评论、转发 | 只做热度和情绪 |

Radar 页面里要明确区分：

- “First-hand source”
- “Analysis / commentary”
- “Community signal”

用户看到的每条内容都应该能点开原始出处。

---

## 2. 数据从哪里来

### 2.1 官方 AI 公司 / 产品源

适合采集：

- 官方 blog
- docs / changelog
- pricing page 变化
- model card
- API release notes
- safety report
- developer docs

第一批 source list 应人工维护，不要自动全网发现。

示例：

- OpenAI news / docs / platform changelog
- Anthropic news / Claude docs
- Google DeepMind blog / Google AI blog
- Meta AI blog
- Microsoft AI blog / Copilot changelog
- GitHub Copilot changelog
- NVIDIA blog
- Hugging Face blog / model cards

### 2.2 研究源

适合采集：

- arXiv: cs.AI, cs.CL, cs.LG, stat.ML, cs.HC
- OpenReview: NeurIPS / ICLR / ICML / ACL 等会议
- Semantic Scholar / OpenAlex metadata
- 重点实验室 blog

研究源的价值不是让普通用户读 paper，而是把 paper 翻译成“这个方向可能影响哪些岗位和技能”。

### 2.3 开源 / 工具源

适合采集：

- GitHub releases
- GitHub trending / stars 变化
- package registry: npm, PyPI
- Hugging Face models / datasets / spaces
- Product Hunt launch
- AI tool changelog

注意：GitHub 和 Product Hunt 等平台有 API 和使用限制，商业化使用前要确认条款。

### 2.4 社区源

适合采集：

- Hacker News top / new / show HN
- Reddit 行业社区
- X posts / lists
- LinkedIn posts
- Discord / Slack 社区人工观察

社区源不是一手事实来源，更多用于判断“这件事有没有被从业者讨论”。

### 2.5 Metix.ai 自有 B 端源

这是我们最独特的数据源。

OpenJobs Recruiter 中已经有：

- JD 文本
- JD 结构化结果
- 招聘方搜索行为
- 候选人匹配维度
- 触达结果
- 招聘任务上下文

C 端 Skill Tree 应该优先被 B 端真实需求校准，而不是只靠新闻和课程目录。

---

## 3. 技术实现架构

### 3.1 总体流水线

```text
Source Registry
  ↓
Ingestion Workers
  ↓
Raw Archive
  ↓
Parser / Extractor
  ↓
Dedup & Event Clustering
  ↓
First-hand Source Scoring
  ↓
LLM Impact Analysis
  ↓
Skill Mapping
  ↓
Personalized Career Radar
```

### 3.2 Source Registry

每个来源都要登记成结构化记录。

字段建议：

```json
{
  "source_id": "openai_news",
  "name": "OpenAI News",
  "url": "https://openai.com/news/",
  "source_type": "official_company",
  "domain": "openai.com",
  "topics": ["frontier_model", "api", "agents"],
  "fetch_method": "rss_or_html_monitor",
  "trust_tier": "A0",
  "poll_interval": "1h",
  "allowed_use": "summary_with_link",
  "commercial_use_note": "check_terms"
}
```

### 3.3 Ingestion Workers

这里不需要复杂 Agent。普通定时任务即可。

- RSS worker
- API worker
- HTML diff worker
- GitHub release worker
- arXiv worker
- B-side JD signal worker

### 3.4 Raw Archive

所有原始内容必须保存快照：

- canonical_url
- fetched_at
- published_at
- raw_html / raw_text
- content_hash
- source_id
- license / robots 备注

这样后续才能证明：这条 Radar 不是 AI 编的，而是从某个原始来源生成的。

### 3.5 First-hand Source Scoring

每个 event 算一个 source score。

建议维度：

| 维度 | 说明 |
|---|---|
| ownership_match | 事件主体是否就是发布域名所有者 |
| original_artifact | 是否有 paper / repo / docs / model card / changelog |
| timestamp_priority | 是否是最早出现的一批来源 |
| source_tier | A0 / A1 / A2 / B / C |
| citation_completeness | 是否能展示原文、链接、发布时间 |
| cross_source_confirmed | 是否被其他源确认或讨论 |

评分不是为了给用户看复杂数字，而是为了决定哪些内容能进入“First-hand Radar”。

---

## 4. AI Agent 应该做什么

### 4.1 不建议让 Agent 做的事

不要让 Agent 自由上网搜全网新闻，然后直接生成日报。

原因：

- 容易抓到二手新闻
- 容易漏掉官方源
- 容易幻觉
- 难以追溯
- 难以合规控制
- 成本不可控

### 4.2 Agent 适合做的事

#### Agent 1: Source Discovery Agent

每周运行一次，发现新的一手源候选。

任务：

- 找新 AI lab / product changelog
- 找新 conference / paper feed
- 找新 vertical tool source
- 提交给人工审核，不自动进入 production

#### Agent 2: Event Verification Agent

对候选新闻做验证。

输出：

- 这是不是一手源
- 原始出处是什么
- 是否有二手来源误读
- 关键变化是什么
- 可信等级是多少

#### Agent 3: Impact Analysis Agent

把原始事件翻译成职业含义。

例如：

> OpenAI 发布新的 Agents SDK

不要只写新闻摘要，而要输出：

- 对 AI Marketing 意味着什么
- 对 GTM Ops 意味着什么
- 哪些技能会变重要
- 用户可以做什么 micro project
- 哪类 proof 可以展示

#### Agent 4: Skill Mapping Agent

把事件映射到技能树。

输出：

- 新增技能
- 相关工具
- 相关岗位
- 推荐 proof 类型
- 与 B 端 JD 信号是否一致

#### Agent 5: Personalization Agent

根据用户关注领域、已点亮技能、已创建 proof，生成个人化 Radar。

---

## 5. 怎么保证“一手”

不能承诺 100% 绝对一手，但可以做到“可审计的一手优先”。

### 5.1 产品规则

1. 每条 Radar 必须有 primary source link。
2. 没有 A0 / A1 / A2 来源的内容不能进入 First-hand Radar。
3. B / C 来源只能作为“community reaction”或“analysis”。
4. 每条内容显示 source type。
5. AI 生成内容必须显示“based on these sources”。
6. 用户可以点开原文。
7. 任何不确定内容标记为 “unverified / commentary”。

### 5.2 系统规则

1. 原文快照归档。
2. 内容 hash 去重。
3. canonical URL 归一化。
4. event clustering。
5. source ownership matching。
6. source whitelist。
7. 人工审核高影响事件。

### 5.3 用户侧展示

每条 Radar 建议展示：

```text
What changed
Why it matters
Skills affected
Suggested action
Source: Official / Paper / Release / B-side demand / Community
Original link
```

这样用户会感觉这不是 AI 胡说，而是“有出处的职业解释”。

---

## 6. POC 怎么做

### Week 1: 手工 source registry

先只做 3 个 vertical：

- AI Marketing
- AI Design
- AI Operations

每个 vertical 选 30-50 个源：

- 10 个官方 AI lab / tool changelog
- 10 个研究 / paper 源
- 10 个开源 / product launch 源
- 10 个行业 newsletter / KOL 解释源
- 10 个 B 端 JD / recruiter demand signal

### Week 2: 半自动抓取 + 人工审核

每天抓取并生成：

- 10-20 条候选事件
- 人工筛到 3-5 条
- 每条都必须有原始链接
- 用 LLM 生成职业含义

### Week 3: 做用户版 Radar

让用户选择领域和技能方向。

每天或每周给用户：

- 3 条变化
- 3 个受影响技能
- 1 个建议行动
- 1 个 proof card 模板

### Week 4: 验证数据价值

关键指标：

- 用户是否觉得信息比普通 AI newsletter 更有用
- 用户是否收藏技能
- 用户是否愿意做 micro project
- 用户是否愿意生成 proof
- 用户是否愿意留下 opportunity preference

---

## 7. 重点结论

### 7.1 不要从“AI 新闻”做起

新闻本身不稀缺。

稀缺的是：

> 这条变化对我的职业意味着什么，我应该学什么，我能做什么证明自己，我有没有机会被看到。

### 7.2 不要把 Agent 当作可信来源

Agent 是处理器，不是事实源。

可信来源必须来自：

- 官方发布
- 作者 / 项目发布
- 研究论文
- 开源仓库
- 产品 changelog
- 我们自己的 B 端 JD 数据

### 7.3 我们真正的优势是 B 端信号

多数 AI newsletter 只能告诉用户“世界发生了什么”。

我们可以告诉用户：

> 招聘方正在找什么技能，这件新变化与真实岗位需求有什么关系。

这就是 Metix.ai 的差异化。

---

## 8. 参考资料

- GitHub REST API Rate Limits: https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api
- GitHub REST API Releases: https://docs.github.com/en/rest/releases/releases
- Hacker News Official API: https://github.com/HackerNews/API
- arXiv API Access: https://info.arxiv.org/help/api/index.html
- Product Hunt API Documentation: https://api.producthunt.com/v2/docs
- OpenAlex Developers: https://developers.openalex.org
- LinkedIn OAuth Overview: https://learn.microsoft.com/en-us/linkedin/shared/authentication/authentication
- X API Documentation: https://docs.x.com/x-api/getting-started/about-x-api
