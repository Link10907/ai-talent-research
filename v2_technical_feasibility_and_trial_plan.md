# V2 技术可行性与试错计划

**日期**: 2026-05-27  
**对象**: Metix.ai C 端职业探索与机会网络  
**结论**: 技术上可行，但必须分阶段做。不要一开始做完整平台，应先做 2-4 周可验证原型，再做 8-12 周 Alpha。真正难点不是 UI，也不是 LLM，而是数据源稳定性、个性化质量、隐私授权、B 端闭环和安全合规。

---

## 0. 一句话判断

这个产品可以试，而且有低成本试错空间。

但正确试法不是直接开发“大产品”，而是先验证三个最小事实：

1. 用户愿不愿意选择关注领域，并持续看职业雷达。
2. 用户愿不愿意点亮技能树，并留下技能 / 兴趣 / 学习意图数据。
3. 用户愿不愿意把一个想法、项目或 AI workflow 变成 Action Proof，并选择是否开放给全球机会。

只要这三件事成立，后续再接 Metix.ai / OpenJobs Recruiter 的 B 端机会反馈才有意义。

---

## 1. 按模块拆解技术可行性

| 模块 | 技术难度 | MVP 可行性 | 主要风险 | 建议做法 |
|---|---:|---:|---|---|
| Career Radar 职业雷达 | 中 | 高 | 新闻质量差、同质化 | 先用白名单 source + RSS + 搜索 API，不做全网爬虫 |
| Skill Tree 技能树 | 中-高 | 中 | 技能 taxonomy 不准 | 先做 2-3 个 vertical 的人工半自动技能树 |
| Action Proof 行动证明 | 中 | 高 | 变成简历包装或内容灌水 | 用结构化模板 + 来源 / 时间戳 / 用户确认 |
| Global Visibility 全球可见性 | 中 | 高 | 隐私、误公开 | 默认私密，share link 和 B 端 open toggle 分开 |
| B 端机会反馈 | 中 | 高 | 与现有 Recruiter 数据模型对接 | 先用离线 job demand signal，不急实时推荐 |
| 数据授权中心 | 中 | 高 | 忽略后会返工 | MVP Day 1 做 consent state / export / delete |
| 多源账号连接 | 高 | 中 | LinkedIn / X 限制大 | 第一版只用稳定源，不依赖 LinkedIn / X 主数据 |
| AI 个性化与总结 | 中 | 高 | 幻觉、过度自信 | RAG + 引用 + 低风险建议，不做招聘决策 |

---

## 2. 哪些功能容易做，哪些功能难

### 2.1 容易做的部分

#### A. 职业雷达

可用技术：RSS 抓取、白名单网站、搜索 API、LLM 摘要、用户兴趣标签。

MVP 不需要全网实时新闻，只需要做 2-3 个领域的高质量 source list，例如 AI Marketing、AI Design、AI Operations。系统每天抓取文章、报告、产品发布、岗位样本，然后用 LLM 转成“职业含义”。

工程量：1-2 名工程师 1-2 周可以做出可用原型。

#### B. 技能树第一版

MVP 不需要构建完整 ontology。先做人工 seed skill map，再用 LLM 辅助维护。

每个领域只需要：

- 核心技能
- 工具栈
- 典型项目
- 证明方式
- 对应岗位关键词

工程量：1 名产品 / 研究 + 1 名工程师，2 周可以做出 demo。

#### C. Action Proof

本质是结构化表单 + AI 改写 + 证据卡生成。第一版不需要复杂验证系统。

关键字段：

- 我关注的问题
- 我做了什么
- 使用了哪些 AI / 工具
- 人的判断在哪里
- 结果或输出是什么
- 可以公开什么
- 需要隐藏什么

工程量：1-2 周。

#### D. Global Visibility 的 share link

公开页 / 私密链接 / 选择性展示是常规 Web 产品能力。难点不在技术，而在默认权限设计。

工程量：1 周可出 alpha。

---

### 2.2 中等难度部分

#### A. 个性化 Radar

真正难的是“别像通用 AI 新闻摘要”。要从用户选择的领域、点亮的技能、过往 proof，生成和用户相关的职业解释。

建议先用规则 + prompt 实现：

```
用户关注领域 + 技能树状态 + 最近 proof + B 端岗位需求关键词
→ 生成今日 3 条职业含义
```

不要一开始训练模型。

#### B. 技能树动态更新

如果想让技能树来自真实市场需求，需要接入岗位数据。你们 B 端已经有 JD 录入和 JD 结构化能力，可以把 B 端岗位关键词先以离线方式反哺 C 端技能树。

第一版不需要实时同步，只要每周离线导出 Top skills / emerging skills。

#### C. B 端机会反馈

由于 OpenJobs Recruiter 已经有招聘任务、JD 结构化、候选人深度搜索、触达、落地页、面试、权益和订阅闭环，因此 C 端系统不需要从零构建招聘闭环，只需要把 C 端新增数据变成 Recruiter 可消费的候选人特征。

第一阶段可以只做：

- 从 B 端 JD 抽取技能趋势
- 给 C 端显示“这个领域近期被招聘方关注的技能”
- 不直接开放候选人给 B 端

---

### 2.3 难度较高部分

#### A. 多平台数据连接

GitHub 技术可行性较高。GitHub REST API 对认证用户通常有 5,000 requests/hour 的主限额，足够做早期 MVP。

LinkedIn 不能作为主数据源。LinkedIn OAuth 可以请求用户授权访问账号数据，但实际可访问字段取决于 scope 和平台授权，不应假设能拿到完整经历、活动和人脉。

X / Twitter API 近年价格和规则变化大，不适合作为早期核心依赖。

Substack 可通过 RSS 和用户手动输入链接做第一版，不应依赖非官方抓取。

#### B. 可信证明系统

如果只是让用户写 proof，容易变成新的“AI 包装内容”。真正可信需要：

- 来源链接
- 时间戳
- 用户确认
- 公开 / 私密字段分离
- 可撤回
- 未来可增加 OAuth / 文件 metadata / 第三方证明

第一版做“弱验证”即可，不要一开始承诺 strong verification。

#### C. 招聘相关合规

如果系统把 C 端用户数据用于 B 端招聘推荐、排名、筛选，就会进入更高合规风险。EU AI Act 的 Annex III 将 employment / worker management 场景列为高风险领域，GDPR 也要求可删除、可导出、可撤回。

因此，MVP 不应做候选人自动排序，不应给 B 端“AI 分数”，只做用户授权的资料展示和机会提醒。

---

## 3. 推荐技术架构

### 3.1 最小架构

```text
Frontend
  ├─ Onboarding: 选择关注领域
  ├─ Career Radar: 领域变化 + 职业含义
  ├─ Skill Tree: 技能路径 + 点亮状态
  ├─ Action Proof: 项目 / 想法 / workflow 证明
  ├─ Visibility Control: 私密 / 链接分享 / 机会开放
  └─ Data Control: 导出 / 删除 / 授权记录

Backend
  ├─ User/Profile Service
  ├─ Content Ingestion Service
  ├─ Skill Taxonomy Service
  ├─ Proof Service
  ├─ Consent & Privacy Service
  ├─ LLM Orchestration Service
  └─ B-side Signal Sync Service

Data
  ├─ PostgreSQL: 用户、技能、proof、权限
  ├─ Object Storage: 附件、截图、导出包
  ├─ Vector DB: 内容检索、proof 检索、领域知识
  └─ Analytics/Event Store: 行为埋点
```

### 3.2 与 Metix.ai / OpenJobs Recruiter 的关系

C 端系统不应该直接写入 Recruiter 的核心任务流。更稳的方式是先建设一个中间层：

```text
C 端用户行为
  ↓
Career Data Layer
  ↓
Skill / Interest / Proof / Opportunity Graph
  ↓
B-side Signal API
  ↓
OpenJobs Recruiter 候选人搜索、匹配、触达、落地页
```

这样可以避免 C 端实验影响现有 B 端产品稳定性。

---

## 4. 工程量评估

### 4.1 POC：2-4 周

目标：证明这个叙事能跑通。

功能：

- 选择领域
- 生成 Career Radar
- 展示静态技能树
- 生成 1 张 Action Proof
- 简单分享页
- 手动导入 5-10 条 B 端岗位需求作为趋势反馈

团队：

- 1 full-stack engineer
- 1 product / researcher
- 0.5 designer

产出：可演示，不保证大规模稳定。

### 4.2 Alpha：8-12 周

目标：让 50-100 个真实用户使用。

功能：

- 账号系统
- 领域选择
- Radar 内容管线
- Skill Tree 状态管理
- Proof 创建 / 编辑 / 分享
- 权限控制
- 基础数据导出 / 删除
- B 端岗位需求离线同步
- 基础埋点

团队：

- 2 full-stack engineers
- 1 AI / data engineer
- 1 product designer
- 1 product / growth

产出：可给种子用户试用。

### 4.3 Beta：3-6 个月

目标：形成可持续验证的产品。

新增：

- 多 vertical 技能树
- 个性化 Radar
- GitHub / RSS / 个人站连接
- Proof provenance 第一版
- OpenJobs Recruiter signal API
- 候选人 opportunity preference
- 管理后台
- 安全审计和数据权限日志

团队：

- 3-5 engineers
- 1 AI / data engineer
- 1 designer
- 1 PM
- 1 growth / community

### 4.4 生产化：6-12 个月

目标：能够承接较大用户量和 B 端闭环。

新增：

- 稳定内容管线
- 多源 OAuth
- 推荐系统
- 搜索和索引优化
- B 端实时反馈
- 完整合规流程
- 监控、告警、权限审计

团队：

- 6-10 人产品工程小队

---

## 5. 最大技术风险排序

### 风险 1：个性化内容质量不足

如果 Career Radar 只是普通 AI 新闻摘要，用户不会持续回来。

缓解：第一版用人工精选 source + 半自动编辑，不追求全自动。

### 风险 2：技能树不可信

如果技能树像课程平台目录，用户不会认为它代表真实机会。

缓解：用 Metix.ai B 端 JD 和 recruiter demand signal 校准技能树。

### 风险 3：Action Proof 太像包装

如果 proof 只是 AI 帮用户写得漂亮，就会变成简历优化器。

缓解：Proof 必须绑定行动、项目、来源、时间、工具、人的判断。

### 风险 4：数据授权设计返工

如果 MVP 不做 consent state，后续接 B 端时会大返工。

缓解：MVP 第一版就建立 visibility_state、consent_log、data_export、delete_request。

### 风险 5：平台 API 不稳定

LinkedIn、X 不适合作为早期核心依赖。

缓解：第一版只做用户自填、RSS、GitHub、个人站和 B 端岗位信号。

### 风险 6：招聘合规风险

如果过早做候选人评分 / 排名 / 自动推荐给招聘方，可能触发高风险监管。

缓解：早期只做用户侧建议和用户授权展示，不做自动 hiring decision。

---

## 6. 低成本试错机会

### 6.1 Figma / HTML 原型测试

不用开发完整系统，先做 5 页：

1. 首页：AI 时代职业雷达
2. 选择领域
3. 技能树
4. Action Proof
5. Global Visibility

用 20 个目标用户访谈，验证是否能讲通。

### 6.2 手工 Radar Newsletter

选 3 个领域，每周人工生成 1 期：

- AI Marketing Radar
- AI Design Radar
- AI Operations Radar

每期都包含：发生了什么、意味着什么技能、可以做什么小行动。

成本极低，可以验证用户是否愿意订阅和回访。

### 6.3 No-code Proof Card

用 Notion / Typeform / Airtable + LLM 人工生成 proof card。

验证用户是否愿意把“我做过什么”结构化表达出来。

### 6.4 B 端岗位信号离线实验

从 OpenJobs Recruiter 里人工抽取 20-50 个 JD，提取高频技能，反向生成 skill tree。

验证 C 端用户是否觉得“这比普通学习路径更贴近真实市场”。

### 6.5 机会开放 toggle 测试

在用户完成 proof 后问：

> 如果有全球 recruiter 正在找这个方向的人，你是否愿意在看到具体机会后决定是否开放资料？

只测意愿，不真正开放 B 端。

---

## 7. 建议的 MVP 取舍

### 第一版必须做

- 领域选择
- Career Radar
- Skill Tree
- Action Proof
- 私密 / 分享 / 开放机会三态权限
- 数据导出 / 删除
- B 端岗位信号离线反哺

### 第一版不要做

- 社区 feed
- 全网爬虫
- LinkedIn 数据抓取
- X 深度数据抓取
- 自动候选人排名
- B 端实时搜索 C 端用户
- 完整 job board
- 完整学习课程系统

---

## 8. 最终结论

技术上，这个方向不是高不可攀的大工程。最小版本更像“内容管线 + 技能图谱 + proof builder + 权限系统 + B 端信号回流”。

真正难点是产品验证，而不是工程实现。

最推荐的路径是：

```text
2-4 周 POC
  ↓
20 个用户访谈 + 手工 Radar
  ↓
8-12 周 Alpha
  ↓
50-100 个真实用户验证
  ↓
再决定是否接入更深的 B 端机会通道
```

如果团队现在直接做完整平台，风险很高。  
如果团队先用半手工方式验证用户是否真的会看、点亮、证明、开放机会，风险可控。

---

## 9. 参考资料

- GitHub REST API Rate Limits: https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api
- LinkedIn OAuth Authorization Code Flow: https://learn.microsoft.com/en-us/linkedin/shared/authentication/authorization-code-flow
- X API Documentation: https://docs.x.com/x-api/introduction
- EU AI Act Annex III: https://artificialintelligenceact.eu/annex/3/
- GDPR Article 17 Right to Erasure: https://gdpr-info.eu/art-17-gdpr/
- GDPR Article 20 Right to Data Portability: https://gdpr-info.eu/art-20-gdpr/
