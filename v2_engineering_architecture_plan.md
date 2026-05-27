# V2 工程架构设计与实现计划

**日期**: 2026-05-27  
**产品方向**: Metix.ai C 端 AI 时代职业探索与机会网络  
**核心模块**: Career Radar / Skill Tree / Action Proof / Global Visibility / Metix B-side Signal Loop  
**结论**: 代码可行，工程难度中等，最大不确定性不是能不能实现，而是用户是否愿意持续使用和授权数据。建议采用“POC → Alpha → Beta → 生产化”四阶段，不要一次性做完整平台。

---

## 0. 一句话工程结论

这个系统工程上可以实现。第一版不需要训练模型，也不需要复杂 Agent 平台。

建议采用：

```text
Next.js / React 前端
+ NestJS / FastAPI 后端
+ PostgreSQL 主库
+ Redis 队列 / 缓存
+ Object Storage 原文快照
+ Vector DB / pgvector 检索
+ LLM Structured Outputs
+ Background Workers / Temporal 可选
+ OpenJobs Recruiter Signal API
```

工程关键不是“造一个 AI Agent”，而是把数据、权限、来源、用户行为和 B 端信号设计成稳定的数据管线。

---

## 1. 系统边界

### 1.1 C 端系统负责什么

C 端系统负责：

1. 用户注册和登录。
2. 用户选择关注领域。
3. 采集和解释 AI 时代的一手信息。
4. 构建用户的技能树。
5. 让用户创建 Action Proof。
6. 管理用户的可见性和授权状态。
7. 把用户行为沉淀为职业数据资产。
8. 接收 Metix.ai B 端岗位需求信号，用于反向校准技能树和职业雷达。

### 1.2 C 端系统暂时不负责什么

MVP 不做：

1. 完整招聘平台。
2. B 端实时搜索 C 端用户。
3. 候选人自动评分 / 自动排名。
4. LinkedIn 深度抓取。
5. X 深度抓取。
6. 全网爬虫。
7. 社区 Feed。
8. 完整课程系统。

---

## 2. 推荐系统架构

### 2.1 总体架构图

```text
                     ┌─────────────────────────────┐
                     │         Web / Mobile Web      │
                     │ Next.js / React / Tailwind    │
                     └──────────────┬──────────────┘
                                    │
                                    ▼
                     ┌─────────────────────────────┐
                     │          API Gateway          │
                     │ Auth / Rate Limit / Routing   │
                     └──────────────┬──────────────┘
                                    │
       ┌────────────────────────────┼─────────────────────────────┐
       ▼                            ▼                             ▼
┌──────────────┐             ┌──────────────┐              ┌──────────────┐
│ User Service │             │ Radar Service│              │ Proof Service│
│ Profile/Auth │             │ News/Signals │              │ Action Proof │
└──────┬───────┘             └──────┬───────┘              └──────┬───────┘
       │                            │                             │
       ▼                            ▼                             ▼
┌──────────────┐             ┌──────────────┐              ┌──────────────┐
│ Skill Service│             │ LLM Service  │              │ Visibility   │
│ Skill Tree   │             │ Extraction   │              │ Consent      │
└──────┬───────┘             └──────┬───────┘              └──────┬───────┘
       │                            │                             │
       └──────────────┬─────────────┴─────────────┬───────────────┘
                      ▼                           ▼
             ┌────────────────┐          ┌──────────────────────┐
             │ PostgreSQL      │          │ Object Storage        │
             │ Core Data       │          │ Raw snapshots/files   │
             └────────────────┘          └──────────────────────┘
                      │
                      ▼
             ┌────────────────┐
             │ Vector DB       │
             │ RAG / Search    │
             └────────────────┘
                      │
                      ▼
             ┌──────────────────────────────┐
             │ OpenJobs Recruiter Signal API │
             │ JD / Skill / Demand Signals   │
             └──────────────────────────────┘
```

### 2.2 后端服务拆分

早期不建议微服务化，可以用 modular monolith。

推荐模块：

| 模块 | 责任 | 早期形态 |
|---|---|---|
| Auth / User | 登录、profile、用户设置 | 普通后端模块 |
| Source Registry | 一手源白名单、采集规则 | 数据表 + 管理后台 |
| Ingestion | RSS/API/HTML diff/JD signal 抓取 | worker |
| Raw Archive | 原文、快照、hash、metadata | object storage + DB |
| Event Pipeline | 去重、聚类、source score | worker |
| LLM Orchestration | 抽取、分类、解释、个性化 | service |
| Skill Tree | 技能节点、关系、用户点亮状态 | DB + API |
| Action Proof | proof card 创建、编辑、分享 | DB + API |
| Visibility / Consent | 私密、链接分享、机会开放、审计 | 必须 P0 |
| B-side Signal | 读取 OpenJobs Recruiter JD / 技能需求 | 内部 API / 离线任务 |
| Analytics | 事件埋点、漏斗、留存 | PostHog / 自建 event table |

---

## 3. 核心数据模型

### 3.1 Source Registry

```sql
source_registry(
  id uuid primary key,
  name text,
  url text,
  source_type text, -- official_company / paper / github_release / b_side_jd / media / community
  trust_tier text,  -- A0 / A1 / A2 / B / C
  domain text,
  topics text[],
  fetch_method text, -- rss / api / html_monitor / webhook / manual
  poll_interval_minutes int,
  is_active boolean,
  created_at timestamptz
)
```

### 3.2 Raw Item

```sql
raw_items(
  id uuid primary key,
  source_id uuid references source_registry(id),
  canonical_url text,
  title text,
  author text,
  published_at timestamptz,
  fetched_at timestamptz,
  raw_text text,
  raw_html_path text,
  content_hash text,
  license_note text,
  created_at timestamptz
)
```

### 3.3 Event Cluster

```sql
event_clusters(
  id uuid primary key,
  title text,
  summary text,
  primary_source_item_id uuid,
  source_score numeric,
  topic_tags text[],
  affected_roles text[],
  affected_skills text[],
  event_type text, -- model_release / paper / product_launch / jd_shift / funding / regulation
  status text, -- candidate / reviewed / published / rejected
  created_at timestamptz
)
```

### 3.4 Skill Tree

```sql
skills(
  id uuid primary key,
  name text,
  vertical text,
  skill_type text, -- foundation / tool / workflow / domain / proof
  parent_skill_id uuid,
  description text,
  evidence_required text,
  demand_score numeric,
  freshness_score numeric,
  created_at timestamptz
)

user_skills(
  user_id uuid,
  skill_id uuid,
  status text, -- interested / learning / practiced / proved
  confidence text, -- self_claimed / proof_attached / verified_source
  updated_at timestamptz,
  primary key(user_id, skill_id)
)
```

### 3.5 Action Proof

```sql
action_proofs(
  id uuid primary key,
  user_id uuid,
  title text,
  vertical text,
  problem text,
  action text,
  tools_used text[],
  ai_used text[],
  human_judgment text,
  output_summary text,
  metrics text,
  source_links text[],
  visibility_state text, -- private / link_shared / public / opportunity_visible
  created_at timestamptz,
  updated_at timestamptz
)
```

### 3.6 Consent / Visibility

```sql
consent_logs(
  id uuid primary key,
  user_id uuid,
  object_type text, -- profile / proof / skill / opportunity
  object_id uuid,
  action text, -- grant / revoke / export / delete_request
  scope text, -- private / public_link / recruiter_visible / b_side_match
  actor text, -- user / system / admin
  created_at timestamptz
)
```

这张表必须从第一天做。后面接 B 端时，最难补的是授权审计，不是功能本身。

---

## 4. AI 实现方式

### 4.1 AI 不负责“事实”，只负责“结构化和解释”

事实来自：

- 官方源
- 论文源
- GitHub release
- Hugging Face model card
- Product changelog
- OpenJobs Recruiter JD 信号

AI 负责：

- 抽取结构化字段
- 分类
- 去重辅助
- 职业含义解释
- 技能映射
- 个性化推荐
- Action Proof 草稿生成

### 4.2 建议的 AI Pipeline

```text
Raw Item
  ↓
LLM Extractor: 输出结构化 Event JSON
  ↓
Rule + Embedding Dedup
  ↓
LLM Impact Analyzer: 职业含义
  ↓
Skill Mapper: 技能树节点映射
  ↓
Personalizer: 针对用户生成 Radar
```

### 4.3 LLM 结构化输出 Schema

```json
{
  "event_title": "string",
  "event_type": "model_release | paper | product_launch | jd_shift | regulation | funding",
  "primary_source_type": "A0 | A1 | A2 | B | C",
  "what_changed": "string",
  "why_it_matters": "string",
  "affected_roles": ["string"],
  "affected_skills": ["string"],
  "suggested_actions": ["string"],
  "proof_ideas": ["string"],
  "source_urls": ["string"],
  "confidence": "high | medium | low"
}
```

OpenAI Structured Outputs 可以让模型输出符合指定 JSON Schema 的结果，减少缺字段、枚举乱写等问题，因此适合用于 Event Extractor、Skill Mapper、Proof Generator 这类工程模块。

### 4.4 Agent 要不要做

要做，但不要一开始做复杂多 Agent 系统。

第一版只需要 4 个“窄 Agent”：

1. **Source Discovery Agent**：发现新一手源，但不自动入库，必须人工审核。
2. **Event Verification Agent**：判断是不是一手源，找原始出处。
3. **Impact Analysis Agent**：把事实翻译成职业含义。
4. **Skill Mapping Agent**：把事件映射到技能树。

本质上它们是后台任务 + prompt + structured output，不需要搭 LangChain / CrewAI 这种复杂 Agent 框架。

---

## 5. Career Radar 的实现

### 5.1 第一版数据源

第一版建议只接：

- RSS / 官方 blog
- arXiv API
- GitHub releases
- Hacker News API
- OpenJobs Recruiter JD 离线导出
- 人工维护的 source list

不建议第一版接：

- LinkedIn 抓取
- X 深度抓取
- Reddit 全量抓取
- 全网通用 crawler

### 5.2 Radar 输出结构

每条 Radar 不应是新闻摘要，而应是：

```text
What changed: 发生了什么
Why it matters: 对职业有什么影响
Skills affected: 哪些技能受影响
Suggested action: 建议做什么小行动
Proof idea: 可生成什么行动证明
Source: 原始链接 + source tier
```

---

## 6. Skill Tree 的实现

### 6.1 第一版不要追求自动生成完整技能树

技能树第一版应该半人工生成。

例如 AI Marketing：

```text
AI Marketing
  ├─ Prompt Ops
  ├─ GTM Automation
  ├─ Lead Enrichment
  ├─ Content QA
  ├─ Attribution Thinking
  ├─ Agent Workflow Design
  └─ AI Evaluation
```

每个节点绑定：

- 相关事件
- 相关 B 端 JD 需求
- 推荐学习资源
- 推荐 micro project
- 推荐 proof 模板

### 6.2 B 端信号如何反哺

从 OpenJobs Recruiter 离线同步：

- 最近 30 天岗位中出现的技能
- 招聘方搜索关键词
- JD 结构化技能
- 高匹配候选人的技能组合

先不暴露候选人个人数据，只用聚合趋势信号。

---

## 7. Action Proof 的实现

### 7.1 Proof Builder

Action Proof 是一个结构化 builder：

```text
我关注的问题
我采取的行动
我用了什么工具 / AI
人的判断在哪里
我产出了什么
有什么结果
哪些可以公开
哪些必须隐藏
```

### 7.2 AI 辅助

AI 可以：

- 生成初稿
- 帮用户脱敏
- 建议补充字段
- 映射到技能树
- 生成分享页摘要

AI 不能：

- 编造结果
- 编造指标
- 自动公开
- 自动开放给 B 端

---

## 8. Global Visibility 的实现

### 8.1 三态权限

第一版至少要有：

```text
private: 仅自己可见
share_link: 有链接的人可见
opportunity_visible: 仅匹配到具体机会时，由用户确认后开放
```

### 8.2 B 端对接方式

不要让 B 端直接搜索 C 端用户。

第一阶段只做：

```text
B 端 JD / 需求
  ↓
系统生成 demand signal
  ↓
C 端看到：这个方向正在被招聘方需要
  ↓
用户选择是否完善技能 / proof / 机会偏好
```

第二阶段再做：

```text
B 端提交具体机会
  ↓
系统在 opportunity_visible 用户中匹配候选人
  ↓
先通知用户
  ↓
用户确认后再开放资料
```

---

## 9. 推荐技术栈

### 9.1 快速 MVP 技术栈

| 层 | 推荐 |
|---|---|
| 前端 | Next.js + React + Tailwind |
| 后端 | NestJS 或 FastAPI |
| 主库 | PostgreSQL |
| 向量检索 | pgvector 或 Qdrant |
| 队列 | Redis + BullMQ / Celery |
| 文件存储 | S3 / R2 / OSS |
| LLM | OpenAI / Anthropic / Gemini 抽象 provider |
| 任务调度 | Cron + Worker，后续 Temporal |
| 埋点 | PostHog / 自建 event table |
| 管理后台 | Retool / Appsmith / 简单 internal admin |

### 9.2 为什么后续考虑 Temporal

当系统出现大量抓取、重试、解析、LLM 调用、人工审核、B 端同步任务时，需要 durable workflow。Temporal 的价值是任务失败、网络中断、worker 崩溃后仍能恢复流程。但 POC 不需要一开始就引入。

---

## 10. 工程排期

### 10.1 POC：2-4 周

目标：可演示，验证叙事。

功能：

- 登录可以先省略，用 magic link 或假用户。
- 领域选择。
- 人工 source registry。
- Career Radar 列表。
- 静态 Skill Tree。
- Action Proof 表单。
- 简单分享页。
- B 端 JD 离线导入。

人力：

- 1 full-stack engineer
- 1 product / researcher
- 0.5 designer

### 10.2 Alpha：8-12 周

目标：50-100 个真实用户试用。

新增：

- 账号系统
- 用户 profile
- source registry 管理
- RSS / API worker
- raw archive
- event clustering
- LLM structured extraction
- skill tree 状态
- action proof builder
- visibility / consent log
- 基础数据导出 / 删除
- 基础 analytics

人力：

- 2 full-stack engineers
- 1 AI / data engineer
- 1 product designer
- 1 PM / growth

### 10.3 Beta：3-6 个月

目标：形成稳定 C 端产品。

新增：

- 3-5 个 vertical
- 个性化 Radar
- GitHub / RSS / 个人站连接
- B 端 demand signal API
- proof provenance 第一版
- 管理后台
- 权限审计
- 更完整的导出 / 删除流程

人力：

- 3-5 engineers
- 1 AI / data engineer
- 1 designer
- 1 PM
- 1 growth / community

### 10.4 生产化：6-12 个月

目标：可商业化和接 B 端闭环。

新增：

- 更稳定的数据源管线
- 多源 OAuth
- 推荐系统
- B 端机会匹配通道
- 安全审计
- GDPR / CCPA 流程
- 监控、告警、权限日志
- 成本优化

人力：

- 6-10 人产品工程团队

---

## 11. 代码可行性判断

### 11.1 可行

以下都属于常规工程能力：

- 内容采集
- RSS/API worker
- 文本解析
- LLM 结构化抽取
- 技能树状态管理
- 分享页
- 权限控制
- 用户行为埋点
- B 端离线数据同步

### 11.2 有难度但可控

- 多源内容去重
- 事件聚类
- 技能映射质量
- 个性化 Radar 质量
- Proof 脱敏质量
- B 端和 C 端数据边界

### 11.3 不建议早期碰

- 全网 crawler
- LinkedIn activity 抓取
- X 全量抓取
- 自动候选人评分
- 自动推荐候选人给招聘方
- 强身份验证 / 背调系统

---

## 12. 成本估算

### 12.1 POC 成本

如果用现有团队，主要成本是人力。

外部成本：

- LLM API：低，几十到几百美元量级。
- 数据源：RSS / arXiv / HN / GitHub 公共 API 基本可控。
- 存储和数据库：低。

### 12.2 Alpha 成本

主要成本：

- LLM 调用
- 数据源抓取
- 数据库 / 存储
- 工程人力

50-100 个用户规模下，基础云成本通常不是问题。真正成本是工程和产品迭代。

### 12.3 Beta 成本

开始进入：

- 多数据源维护成本
- LLM 成本优化
- 用户支持
- 数据合规
- 监控运维

需要正式工程流程。

---

## 13. 最终建议

工程角度建议按这个顺序做：

```text
Step 1: 静态 HTML / Figma 演示
Step 2: 手工 source registry + 手工 Radar
Step 3: POC Web App
Step 4: 50-100 人 Alpha
Step 5: 接 OpenJobs Recruiter 离线岗位信号
Step 6: 做 GitHub / RSS / 个人站连接
Step 7: 做 opportunity_visible 权限通道
Step 8: 再接 B 端机会匹配
```

最重要的一点：

> 工程上能做，但产品上不能急。先用最小工程验证用户是否真的会“看变化、点技能、做 proof、开 visibility”。

如果这个行为链路成立，后面再投入 6-12 个月做生产化才合理。

---

## 14. 参考资料

- GitHub REST API Rate Limits: https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api
- OpenAI Structured Outputs: https://platform.openai.com/docs/guides/structured-outputs
- arXiv API Access: https://info.arxiv.org/help/api/index.html
- Temporal Platform Documentation: https://docs.temporal.io/temporal
- EU AI Act Annex III: https://artificialintelligenceact.eu/annex/3/
- GDPR Article 17 Right to Erasure: https://gdpr-info.eu/art-17-gdpr/
- GDPR Article 20 Right to Data Portability: https://gdpr-info.eu/art-20-gdpr/
