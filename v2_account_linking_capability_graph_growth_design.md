# V2 账号连接、能力图谱与成长打卡设计补充

**日期**: 2026-05-27  
**对象**: Metix.ai C 端职业探索与机会网络  
**目的**: 补充产品设计中关于账号连接、作品证明、全面技能图谱、现有能力 / 潜在能力 / 可泛化能力，以及成长打卡体系的设计。

---

## 0. 核心修正

当前产品不能只讲 Career Radar、Skill Tree、Action Proof。还需要一个更底层的机制：

> 用户连接自己的职业资产来源，系统构建全方位能力图谱，再基于图谱给出知识推荐、Proof Prompt 和成长打卡。

这会让产品更像一个持续成长系统，而不是一次性 proof 生成器。

完整链路应改为：

```text
连接职业资产
  ↓
抽取能力线索
  ↓
构建能力图谱
  ↓
识别现有能力 / 潜在能力 / 可泛化能力
  ↓
推荐知识、技能路径和 Proof Prompt
  ↓
用户持续打卡、补证据、更新职业资产
  ↓
反哺 Metix.ai B 端候选人搜索与匹配
```

---

## 1. 为什么要做账号连接

C 端用户不会愿意一开始手动填大量技能和经历。

更自然的入口是：

> 把你已经做过的东西接进来，我们帮你整理成能力图谱。

这比“完善简历”更有吸引力，因为用户感受到的是：

- 我不用从零填写。
- 我的已有作品和行动被看见。
- 系统帮我总结我现在会什么。
- 系统还能告诉我哪些能力可以迁移。
- 系统知道我接下来该补什么证据。

---

## 2. 可连接的数据源

### 2.1 GitHub

适合证明：工程能力、开源参与、自动化能力、AI agent / tool building、代码质量、持续迭代。

可抽取：

- repository
- commit
- pull request
- issue
- release
- language
- README
- topics
- contribution timeline
- commit author / date / message
- commit signature verification 状态

证据价值：高。尤其适合工程、AI 工具、自动化、data / ML、developer marketing 等方向。

### 2.2 Portfolio / Design

适合证明：设计能力、创意表达、产品感、视觉系统、交互设计、品牌建设。

可接入：

- 个人网站
- Behance
- Dribbble
- Figma share link
- Framer / Webflow / portfolio URL

证据价值：中到高。多数需要用户确认和解释自己的贡献角色。

### 2.3 Writing / Research

适合证明：观点判断、研究能力、结构化表达、行业理解、内容能力。

可接入：

- Substack
- Medium
- 个人博客
- arXiv / Google Scholar 手动链接
- Notion public page
- 技术文章

证据价值：中。需要判断文章是否原创、是否长期持续、是否与技能树有关。

### 2.4 Project / Workflow

适合证明：业务解决能力、AI workflow、运营能力、营销自动化、流程设计。

可接入：

- Notion
- Google Docs
- Google Slides
- Loom
- 脱敏截图
- CSV 样例
- workflow diagram
- CRM / marketing ops 导出样例

证据价值：中。很多真实工作无法完全公开，所以第一版要支持脱敏证明。

### 2.5 Resume / Profile

适合构建基础候选人档案。

可接入：

- PDF / DOCX 简历
- LinkedIn export
- 手动经历
- 个人主页 About

证据价值：基础。它不是产品核心卖点，但对 B 端候选人搜索是必要底层字段。

---

## 3. 能力图谱如何设计

能力图谱不应只是技能标签列表，而应区分三层。

### 3.1 现有能力 Existing Capability

定义：用户已有明确证据支持的能力。

来源：

- GitHub commit / repo
- 作品链接
- 文章
- 项目文档
- 简历经历
- 第三方背书
- B 端结果反馈

用途：

- 用户知道自己已经能证明什么。
- B 端匹配中作为高置信字段。
- 生成 proof card 和 profile 摘要。

示例：

```text
Python automation: GitHub repo + commits
AI content workflow: Notion doc + output sample
B2B growth writing: 12 篇 Substack 文章
```

### 3.2 潜在能力 Potential Capability

定义：用户可能具备基础，但证据还不完整的能力。

来源：

- 相邻技能
- 学习记录
- 关注领域
- 职业雷达阅读行为
- 类似项目经验
- 用户自我选择的方向

用途：

- 推荐学习内容。
- 推荐 Proof Prompt。
- 做成长打卡。
- 不直接作为强招聘证明。

示例：

```text
用户会 Python automation + 关注 AI agents + 做过 API integration
→ 潜在能力：AI agent orchestration
```

### 3.3 可泛化能力 Generalizable Capability

定义：可以跨岗位、跨行业迁移的能力模式。

来源：

- 多个项目中的共同结构
- 多种技能之间的重复行为模式
- 用户解决问题的方式
- 工具使用习惯
- 产出类型

用途：

- 帮用户理解自己可以去哪些新方向。
- 支持跨行业推荐。
- 帮 B 端发现非传统背景候选人。

示例：

```text
系统拆解能力
自动化思维
结构化表达
数据判断
产品化能力
快速学习能力
跨工具整合能力
```

---

## 4. 能力图谱的数据结构建议

```json
{
  "user_id": "u_123",
  "capabilities": [
    {
      "capability_id": "gtm_automation",
      "name": "GTM Automation",
      "type": "existing",
      "confidence": "medium",
      "evidence_level": "artifact_linked",
      "evidence_items": ["proof_001", "github_repo_002", "notion_doc_003"],
      "last_seen_at": "2026-05-27"
    },
    {
      "capability_id": "agent_workflow_design",
      "name": "Agent Workflow Design",
      "type": "potential",
      "confidence": "low",
      "basis": ["adjacent_skill", "interest_signal", "radar_reading"],
      "recommended_proof_prompt": "Build or document a small agent workflow for lead routing"
    },
    {
      "capability_id": "structured_problem_solving",
      "name": "Structured Problem Solving",
      "type": "generalizable",
      "confidence": "medium",
      "basis": ["multiple_projects", "workflow_pattern", "writing_structure"]
    }
  ]
}
```

---

## 5. 知识推荐如何基于能力图谱产生

知识推荐不是泛泛推荐课程，而是围绕三类缺口：

### 5.1 Knowledge Gap

用户关注某方向，但基础知识不足。

例子：用户关注 AI Operations，但缺少 queue / workflow / API basics。

推荐：基础文章、工具教程、案例拆解。

### 5.2 Proof Gap

用户可能有能力，但缺少证据。

例子：用户简历写了 marketing automation，但没有项目证明。

推荐：Proof Prompt、脱敏案例模板、可提交证据类型。

### 5.3 Opportunity Gap

用户想进入某类岗位，但缺少岗位常见技能。

例子：AI GTM Ops 岗位频繁要求 Clay、CRM enrichment、Zapier、prompt QA。

推荐：技能树路径和优先补充的 proof。

---

## 6. 成长打卡体系

打卡不是签到，而是职业资产更新。

### 6.1 每周打卡内容

用户每周看到：

1. 你关注的领域发生了什么变化。
2. 哪些技能和你现有能力最接近。
3. 哪些技能正在被 Metix.ai B 端岗位需求频繁提到。
4. 你本周可以补充哪一条 proof。
5. 你的能力图谱本周有什么变化。

### 6.2 用户打卡动作

用户可以完成轻量动作：

- 收藏一个 Radar 事件。
- 标记一个技能为 Interested / Learning。
- 添加一条项目链接。
- 补充一张截图或文件。
- 回答一个 Proof Prompt。
- 更新机会偏好。

### 6.3 平台获得的数据

- Freshness Signal: 用户是否仍然活跃。
- Learning Intent: 用户正在往哪里成长。
- Proof Growth: 用户是否在补证据。
- Skill Transition: 用户能力是否发生迁移。
- Opportunity Preference: 用户是否愿意看新机会。

---

## 7. 与 B 端的关系

C 端能力图谱可以补全 Metix.ai 的候选人画像。

### 7.1 对 openjobs-recruiter 的价值

- 搜索不只依赖简历关键词。
- 匹配可考虑现有能力、潜在能力、可泛化能力。
- recruiter 可以看到候选人 proof，而不是只看自我描述。
- 对非传统背景候选人更友好。
- 对 AI 时代的新岗位更敏感。

### 7.2 B 端使用原则

早期不要直接给 B 端一个“搜索所有 C 端用户”的入口。

推荐路径：

```text
B 端岗位需求
  ↓
聚合成 demand signal
  ↓
反向校准 C 端技能树和知识推荐
  ↓
用户选择是否完善 proof / 打开 opportunity_visible
  ↓
具体机会出现时，用户先确认，再开放资料
```

---

## 8. 展示文档应补充的页面

主 HTML 应新增三页：

### Page A: 账号连接与证据源

核心句：

> 用户不用从零填写资料。先把 GitHub、作品集、文章、项目和简历接进来，系统从已有职业资产中识别能力线索。

### Page B: 全面能力图谱

核心句：

> 我们不只识别用户现在会什么，也识别他可能具备什么、哪些能力可以迁移到新行业。

### Page C: 成长打卡

核心句：

> 简历是低频更新，成长打卡让职业资产持续变新。

---

## 9. 工程实现优先级

### P0

- 简历 / 手动 profile 输入
- GitHub OAuth / repo link
- 作品 / 文章 / 项目链接手动提交
- 能力抽取
- Evidence item 数据结构
- Existing Capability 图谱

### P1

- Potential Capability 推断
- Generalizable Capability 标签
- Proof Gap 检测
- 每周 Growth Check-in
- B 端 JD demand signal 离线同步

### P2

- Behance / Dribbble / Medium / Substack 等自动连接
- Notion / Google Drive OAuth
- 第三方背书
- VC / Open Badge 导出
- 更完整的 opportunity_visible 闭环

---

## 10. 最终判断

这个补充会让产品更完整。

如果只有 Career Radar，产品像内容产品。  
如果只有 Proof，产品像包装工具。  
如果只有技能树，产品像学习平台。  

加入账号连接、能力图谱和成长打卡后，产品变成：

> 一个持续更新的职业成长与能力证明系统。

这更符合 C 端长期价值，也更符合 B 端候选人数据生态目的。
