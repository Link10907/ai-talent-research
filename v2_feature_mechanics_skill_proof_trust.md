# V2 功能机制细化：技能树、行动证明与可信度系统

**日期**: 2026-05-27  
**对象**: Metix.ai C 端 AI 时代职业探索与机会网络  
**目的**: 把“点亮技能树”“生成行动证明”“可信度保证”从概念落到具体产品机制、数据结构和工程实现。

---

## 0. 核心结论

展示材料不能只说“点亮技能树”和“行动证明”。必须说明用户到底做了什么，系统如何判断，以及这些判断的可信度边界。

推荐原则：

> 不要声称“用户掌握了某技能”，而要展示“用户为该技能提供了哪些证据，证据可信等级是多少”。

换句话说，产品不应该做一个粗糙的“技能认证平台”，而应该做一个“能力证据账本”。

技能状态从低到高分成五级：

1. **Interested**：用户感兴趣。
2. **Learning**：用户正在学习。
3. **Practiced**：用户完成过练习或 micro project。
4. **Proved**：用户提交过可展示行动证明。
5. **Verified / Endorsed**：证据来自可信来源或获得第三方背书。

只有第 3 级以上才能叫“点亮”。第 1、2 级只能叫“关注”或“学习中”。

---

## 1. 技能树到底怎么点亮

### 1.1 用户侧体验

用户看到一个领域技能树，例如 AI Marketing：

```text
AI Marketing
  ├─ Prompt Ops
  ├─ GTM Automation
  ├─ Lead Enrichment
  ├─ AI Content QA
  ├─ Agent Workflow Design
  └─ AI Evaluation
```

每个技能节点有四个按钮或状态：

1. **我感兴趣**：收藏技能。
2. **我要学习**：加入学习路径。
3. **我做过一次**：提交练习或 micro project。
4. **我要证明**：生成 Action Proof。

用户不能只靠点击按钮就“点亮技能”。点击只是表达兴趣。真正点亮必须上传或生成行动证据。

### 1.2 点亮条件

每个技能节点都有 evidence requirement。

示例：AI Marketing / Lead Enrichment

| 状态 | 用户动作 | 系统判断 |
|---|---|---|
| Interested | 收藏技能 | 记录兴趣信号 |
| Learning | 收藏 2 个资源或阅读 Radar 相关内容 | 记录学习意图 |
| Practiced | 完成一个 lead enrichment workflow 小任务 | 可点亮为 practiced |
| Proved | 提交 workflow、工具栈、样例输出和反思 | 可生成 proof card |
| Verified | 绑定来源链接、GitHub/Notion/HubSpot 截图、第三方确认或 B 端结果 | 提升可信等级 |

### 1.3 技能节点数据结构

```json
{
  "skill_id": "ai_marketing_lead_enrichment",
  "name": "Lead Enrichment with AI",
  "vertical": "AI Marketing",
  "prerequisites": ["Prompt Ops", "CRM Basics"],
  "evidence_requirements": {
    "practiced": ["workflow_description", "sample_input_output"],
    "proved": ["tool_chain", "human_judgment", "result_summary", "source_link_or_artifact"],
    "verified": ["oauth_source", "third_party_endorsement", "b_side_outcome"]
  },
  "suggested_micro_projects": [
    "Build a 20-lead enrichment workflow using public company data",
    "Compare AI-generated lead scoring against manual scoring"
  ]
}
```

---

## 2. 怎么判断用户真的掌握了技能

### 2.1 不直接判断“掌握”，而是判断“证据强度”

系统不应该说：

> 你已经掌握了 Agent Workflow Design。

应该说：

> 你已为 Agent Workflow Design 提供 2 个行动证明，其中 1 个有外部来源链接，可信度为 Medium。

原因是职业能力不能只靠平台自动判断。W3C Verifiable Credentials 2.0 也强调，credential 的可验证性不等于 claim 一定为真；verifier 仍需根据 issuer、proof、subject、claims 和自身规则判断是否信任。

### 2.2 证据等级

| 等级 | 名称 | 说明 | 示例 |
|---|---|---|---|
| L0 | Self-claimed | 用户自己说会 | 勾选“我会 Prompt Ops” |
| L1 | Structured self-report | 用户按模板说明做过什么 | 填写 workflow 表单 |
| L2 | Artifact-linked | 有链接、截图、文件或输出 | Notion 页面、GitHub repo、Figma link |
| L3 | Source-verified | 通过 OAuth、API、metadata 或时间戳确认来源 | GitHub commit、公开博客、产品 changelog |
| L4 | Third-party endorsed | 被他人或机构确认 | 同事背书、客户评价、mentor review |
| L5 | Outcome-validated | 有真实结果或 B 端反馈 | 被招聘方收藏、面试邀请、客户采用、指标提升 |

MVP 先做到 L0-L2。Alpha 做 L3 的一部分。Beta 后再做 L4-L5。

### 2.3 自动判断规则

系统可计算一个 evidence confidence，不是 skill score。

示例规则：

```text
confidence = source_strength + artifact_completeness + recency + cross_source_consistency + human_review
```

字段：

- source_strength：来源强度。
- artifact_completeness：证据完整度。
- recency：证据新鲜度。
- cross_source_consistency：跨源一致性。
- human_review：人工或第三方审核。

---

## 3. Action Proof 怎么生成

### 3.1 Action Proof 不是简历段落

Action Proof 应该是一个结构化证据单元。

每张 proof card 包含：

1. **Context**：背景。
2. **Problem**：问题。
3. **Action**：我做了什么。
4. **Tools / AI Used**：用了哪些工具或 AI。
5. **Human Judgment**：人的判断在哪里。
6. **Output**：产出是什么。
7. **Result / Signal**：结果或早期信号。
8. **Evidence**：链接、截图、repo、文件、时间戳。
9. **Visibility**：哪些公开，哪些脱敏。
10. **Mapped Skills**：映射到哪些技能树节点。

### 3.2 生成流程

```text
用户选择技能节点
  ↓
选择 proof 类型：项目 / 想法 / workflow / 学习实验
  ↓
填写结构化问题
  ↓
上传或粘贴证据
  ↓
AI 生成 proof 草稿
  ↓
系统提示缺失字段
  ↓
用户确认、脱敏、发布或保持私密
```

### 3.3 Proof 类型

#### A. Project Proof

适合已经做过实际项目的人。

例子：

> 我为一个 SaaS 产品设计了 AI-assisted lead qualification workflow。

证据：workflow 图、样例数据、工具栈、输出结果、指标变化。

#### B. Workflow Proof

适合不能公开最终产物的人。

例子：

> 我用 Claude + Clay + Zapier 设计了一个线索清洗流程，但客户数据不可公开。

证据：脱敏流程图、工具链、决策节点、模拟样例。

#### C. Idea Proof

适合探索新领域的人。

例子：

> 我认为 AI SDR 的下一个瓶颈不是生成邮件，而是 lead scoring feedback loop。

证据：观点、实验设计、数据假设、公开研究来源。

#### D. Learning Proof

适合刚进入某领域的人。

例子：

> 我用 7 天复现了一个 AI content QA workflow。

证据：学习路径、复现步骤、结果、反思。

---

## 4. 信息可信度如何保证

### 4.1 可信度来自 provenance，不来自 AI 文笔

AI 可以帮助整理，但不能成为可信来源。

可信度来自：

- 原始链接
- 时间戳
- 来源类型
- 内容快照
- API / OAuth metadata
- 文件 hash
- 第三方背书
- 结果反馈

GitHub 的 commits API、releases API 等可以为工程类或开源类行动提供时间、作者、提交记录等结构化 evidence。对于非工程岗位，则先通过 source link、文件、截图、人工确认和脱敏 proof 实现弱验证。

### 4.2 Proof Card 可信度展示

每张 proof card 不显示一个夸张分数，而是显示 evidence checklist。

示例：

```text
Evidence confidence: Medium
✓ Structured workflow provided
✓ Tool chain provided
✓ Source link attached
✓ Human judgment explained
— No OAuth-verified source
— No third-party endorsement
— No outcome signal yet
```

这种表达比“92 分”可信，因为它告诉招聘方和用户证据到底强在哪里、弱在哪里。

### 4.3 公开页展示方式

公开页不应写：

> Certified AI Marketing Expert

应该写：

> Proof attached for: Lead Enrichment, GTM Automation, AI Content QA
> Evidence level: Artifact-linked
> Last updated: 2026-05-27
> Sources: 2 links, 1 workflow, 1 output sample

---

## 5. Skill Tree、Proof 和 B 端数据如何闭环

### 5.1 用户行为产生的数据

| 用户行为 | 沉淀数据 | B 端价值 |
|---|---|---|
| 关注技能 | Interest signal | 用户未来方向 |
| 加入学习 | Learning intent | 转型意愿 |
| 完成 micro project | Practice signal | 行动力 |
| 提交 proof | Evidence graph | 能力证据 |
| 添加来源 | Provenance signal | 可信度 |
| 打开 visibility | Opportunity signal | 可触达性 |

### 5.2 B 端反向校准技能树

OpenJobs Recruiter 的 JD 和搜索行为可以反向影响技能树：

```text
B 端 JD / recruiter search
  ↓
抽取岗位技能
  ↓
聚合成 demand signal
  ↓
更新技能树热度
  ↓
告诉用户：这个技能正在被真实招聘需求关注
```

这样 Skill Tree 不是课程平台自说自话，而是被真实招聘需求校准。

---

## 6. MVP 应如何落地

### 6.1 第一版点亮规则

MVP 不做复杂验证，只做三步：

1. 用户选择技能。
2. 用户完成一个 micro action。
3. 用户生成一张 proof card。

点亮条件：

- 至少填写 Context / Action / Tools / Output。
- 至少关联一个 skill。
- 至少提供一个 evidence item，哪怕是文字、链接或文件。

### 6.2 第一版可信度

MVP 只区分三档：

- Self-claimed
- Proof attached
- Source-linked

不要一开始做 Verified badge。Verified badge 必须等到 OAuth / 第三方背书 / B 端结果闭环做起来后再开放。

### 6.3 第一版 UI 文案

推荐文案：

```text
点亮技能不是声明你已经精通，而是为这个技能添加一条行动证据。
```

```text
你的 proof 越具体，越容易被真实机会理解。
```

```text
默认私密。你可以选择把这张 proof 公开，或只在匹配到机会时展示。
```

---

## 7. 示例：AI Marketing 用户完整路径

### Step 1: 用户选择领域

用户选择：AI Marketing。

系统展示技能树：Prompt Ops、GTM Automation、Lead Enrichment、AI Content QA、Agent Workflow Design。

### Step 2: 用户点击 Lead Enrichment

页面显示：

```text
这个技能为什么重要：过去 30 天 B 端 JD 中，AI GTM / Growth Ops 相关岗位多次出现 lead enrichment、Clay、CRM automation。
你可以做的行动：构建一个 20 条线索的 enrichment workflow。
需要提交的证据：workflow、工具栈、样例输入输出、你的判断节点。
```

### Step 3: 用户完成 micro project

用户提交：

- 使用 Clay + ChatGPT + Google Sheets。
- 输入 20 条公司线索。
- 输出 ICP 标签、优先级、个性化开场白。
- 说明哪些步骤由 AI 生成，哪些由人判断。

### Step 4: 系统生成 proof card

```text
Title: Built an AI-assisted lead enrichment workflow for B2B SaaS prospecting
Mapped skills: Lead Enrichment, GTM Automation, Prompt Ops
Evidence: workflow description, sample output, tool chain
Confidence: Proof attached
Visibility: Private by default
```

### Step 5: 用户选择可见性

用户可以选择：

- 保持私密。
- 生成分享链接。
- 开启机会可见性。

如果开启机会可见性，B 端只能在具体机会匹配时请求展示，用户确认后才开放。

---

## 8. 和标准体系的关系

Open Badges 3.0 和 W3C Verifiable Credentials 2.0 都可以作为后续设计参考。

- Open Badges 适合“技能成就 / 证明单元”的数据模型。
- W3C Verifiable Credentials 适合“issuer-holder-verifier”三方信任模型。

但早期不建议直接上完整 VC / DID 体系。MVP 先用内部 evidence ledger，后续如果要开放给第三方验证，再把 high-confidence proof 转成 Open Badge / Verifiable Credential。

---

## 9. 最终建议

汇报文档里应该把每个功能说成“机制”，不要只写名词。

推荐表达：

> Skill Tree 不是用户点一下就亮。每个技能节点都有证据要求。用户通过 micro project、workflow、想法实验或真实项目生成 Action Proof，系统根据证据来源、时间戳、完整度和第三方信号给出 evidence confidence。我们不声称用户一定掌握某技能，而是展示他为这个技能提供了什么证据。

这句话应该进入下一版 HTML 首页之后的产品机制部分。

---

## 10. 参考资料

- W3C Verifiable Credentials Data Model 2.0: https://www.w3.org/TR/vc-data-model-2.0/
- 1EdTech Open Badges 3.0 Specification: https://www.imsglobal.org/spec/ob/v3p0/
- GitHub REST API Commits: https://docs.github.com/en/rest/commits/commits
- OpenAI Structured Outputs: https://platform.openai.com/docs/guides/structured-outputs
