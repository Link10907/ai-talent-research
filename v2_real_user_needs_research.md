# V2 真实用户需求调研:哪些是真需求,哪些是假设

**日期**:2026-05-27  
**调研目标**:从真实用户痛点出发,判断 C 端用户为什么会愿意使用我们的产品,哪些需求已经被市场验证,哪些仍是潜在假设,哪些是弱需求或伪需求。  
**产品背景**:我们要做一个真实 To C 产品,通过给 C 端用户明确职业利好,让用户自愿、持续、高质量地更新简历、技能、项目证据、AI 工作流和机会偏好,最终形成 B 端 AI 招聘产品的数据生态。

---

## 0. 核心结论

C 端用户愿意使用产品的原因,不能靠“职业能力镜子”这个抽象概念本身。

更真实的用户动机来自五个已经存在的痛点:

1. **职业资料分散,简历难维护**。
2. **求职过程低效,需要 JD 匹配、ATS 优化和 job tracker**。
3. **AI 技能越来越重要,但用户缺少可信证明方式**。
4. **用户希望被更好机会发现,但不愿公开求职**。
5. **招聘流程让用户不信任,包括 ghost jobs、ATS 过滤、AI 筛选、长流程和无反馈**。

这些是真实需求。

但以下需求目前仍是潜在假设:

1. 用户会每周主动查看 career mirror。
2. 用户会长期维护公开 proof page。
3. 用户会为了 AI-search visibility 持续更新 profile。
4. 非求职状态用户愿意持续维护完整职业档案。

所以 MVP 不应从“镜子”作为主入口,而应从更确定的用户动作开始:

> 导入简历 / LinkedIn profile → AI 整理职业资产 → 用户确认技能和项目 → 生成能力证据 → 设置私密机会偏好。

---

## 1. 已被市场验证的真实需求

### 1.1 简历 / Profile 整理是真需求

Teal、Rezi、Kickresume 等产品的存在和用户规模说明,用户愿意上传职业资料,使用 AI 生成或优化简历。

Teal 官网显示其核心功能包括 AI resume builder、job tracker、matching mode、resume job description match、resume keyword scanner、ATS resume checker、job application tracker、cover letter generator,并显示 over 4M users / over 3.2M members。

Rezi 官网定位为 ATS-optimized AI resume builder,强调 resume import、keyword targeting、AI writer/editor、ATS-friendly templates,并显示 trusted by 4M job seekers。

Kickresume 官网提供 AI resume builder、AI cover letter、resume checker、personal website,并显示 trusted by 8M job seekers。

**判断**:用户愿意为了更好的职业呈现而交出简历数据。这是我们 C 端产品最稳的入口。

**对我们的含义**:

- 第一屏可以允许用户上传简历 / 导入 LinkedIn export / 粘贴 LinkedIn URL。
- 不应一开始要求连接多个账号。
- 先给低风险价值,再请求更高授权。

---

### 1.2 ATS / JD 匹配焦虑是真需求

Jobscan、Teal、Huntr 等都围绕 ATS checker、resume match、keyword scanner 做产品。Jobscan 官网强调 ATS resume checker、match report、one-click optimize、LinkedIn optimization、job tracker,并宣称 99% Fortune 500 使用 ATS。

近期媒体报道也显示,求职者普遍担心简历无法到达人类招聘者手中。TechRadar 2026 报道提到,许多 job seekers 认为 resume 被 ATS 或 AI gatekeeper 过滤,并围绕关键词、格式和 JD 术语进行优化。

**判断**:ATS 优化需求真实存在,但已经红海。

**对我们的含义**:

- 可以把 JD match / ATS readiness 作为 onboarding 利好。
- 不能把它作为核心差异化。
- 我们要从 “怎么过 ATS” 升级到 “怎么持续证明能力”。

---

### 1.3 求职流程管理是真需求

Huntr 和 Teal 都做 job tracker。Huntr 提供 job tracker、contact tracker、interview tracker、autofill applications、AI resume builder、tailored resume 等,并显示 500,000+ job seekers。

这说明 active job seeker 有明确的流程管理需求。

**判断**:job search CRM 是真实需求,但不适合成为我们的主战场。

**对我们的含义**:

- 我们可以借鉴 job tracker 里的“职位-简历-证据”结构。
- 但不要做完整求职 CRM,否则会和 Huntr / Teal 正面竞争。
- 我们应服务 active + semi-passive 用户,尤其是后者。

---

### 1.4 AI 技能作为职业竞争力是真需求

AI skills 已经成为招聘市场信号。

外部研究显示,AI skills 能提升候选人的面试邀请概率,并在某些情况下抵消学历或年龄劣势。另有基于 UK 大规模职位广告的研究显示,AI 相关职位更强调技能而非学历,且 AI skills 存在工资溢价。

同时,新闻报道显示,部分员工会夸大自己的 AI skills。这说明市场出现了两个同时存在的现象:

- AI skills 有价值。
- AI skills claim 不可信。

**判断**:我们的“AI workflow proof”方向有真实基础。

**对我们的含义**:

- 不能只让用户写 “I use ChatGPT / Claude / Cursor”。
- 要记录使用场景、输入、过程、判断、产出、结果。
- 需要区分 AI contribution 和 human judgment。

---

### 1.5 私密被机会发现是真需求

既有 raw_data 已经显示,LinkedIn OpenToWork 私密信号远大于公开 badge。大量用户愿意被 recruiter 发现,但不愿公开向同事、老板、朋友表示求职。

当前 job hugging、低跳槽信心和招聘不确定性环境下,这个需求会更强。用户可能不主动求职,但愿意保持机会雷达。

**判断**:Opportunity Graph 是核心资产,不是附加功能。

**对我们的含义**:

- 默认不公开求职状态。
- 提供私密 opportunity preference。
- B 端机会必须先给用户看,用户同意后再开放。
- 这会比公开 OpenToWork 更适合 passive candidates。

---

### 1.6 招聘流程不信任是真需求

2025-2026 年求职环境中,ghost jobs、AI/ATS 筛选、无反馈、过长流程、批量申请导致双方都不信任。

外部报道和研究指出,ghost jobs 已成为明显问题,有报道称约 1/5 online job postings 是 fake 或 never filled。Business Insider 也讨论了求职者把拒信归因于 AI 的现象,同时指出真实问题常常是申请量过大、招聘者处理不过来、人工和系统共同造成的黑箱。

**判断**:用户需要更可信、更低噪声、更可控的机会入口。

**对我们的含义**:

- 不要把产品做成又一个 job board。
- 要强调 verified opportunity / user-reviewed opportunity / low-noise matching。
- 用户开放资料前必须看到机会质量。

---

## 2. 仍需验证的潜在需求

### 2.1 Career Mirror 周活需求

“能力镜子”有逻辑吸引力,但还没有直接市场证据证明普通 professional 会每周查看职业能力变化。

它的类比对象包括:

- Spotify Wrapped
- Strava Year in Sport
- GitHub Wrapped
- Whoop health insights

但这些都是音乐、运动、代码、健康等高频行为。职业资产更新频率更低。

**验证方法**:

- MVP 30 天内观察用户是否回来看能力变化。
- 比较 weekly insight email vs no email 的回访率。
- 观察用户是否主动补充证据。

### 2.2 Proof Page 发布需求

用户可能愿意创建可分享 proof page,但不一定愿意公开。

公开页面会触发:

- 被同事看到的风险
- 被老板误解的风险
- 自我展示焦虑
- 内容不够好看的羞耻感

**验证方法**:

- 区分 private proof card、share-by-link proof card、public indexed proof page。
- 分别测创建率和分享率。

### 2.3 非求职状态下持续更新需求

这是本项目最关键的假设。Active job seeker 更新简历是确定需求;semi-passive professional 是否愿意更新,还未被验证。

**验证方法**:

- 找不求职但愿意被机会发现的人。
- 提供“职业档案自动更新”价值。
- 观察 30 / 60 天更新率。

### 2.4 AI-search visibility 需求

“让 ChatGPT / Perplexity 能找到你”可能对 creator / consultant 有吸引力,但对普通中层用户未必成立。

**验证方法**:

- Landing page A/B 测试。
- 对 creator、consultant、mid-level marketer 分组测试。

---

## 3. 伪需求和弱需求

### 3.1 新 LinkedIn

用户不会迁移,招聘方也不会迁移。这个方向应彻底排除。

### 3.2 纯公开主页

Read.cv、Polywork、Bento.me 已经证明,更美观的职业主页缺少持续回访和商业闭环。

### 3.3 人人 build in public

极少数 creator 能持续输出,多数 professional 不愿意也做不到。

### 3.4 人人写 newsletter

Newsletter 是渠道和触发器,不是大多数 C 端用户的职业数据更新机制。

### 3.5 简历美化工具

模板和美化已高度商品化,不能形成数据护城河。

---

## 4. 目标用户分层

### 4.1 Layer 1:Active Job Seeker

痛点明确:

- 简历优化
- JD 匹配
- ATS 通过
- job tracker
- cover letter

问题:

- 竞品太多
- 用户生命周期短
- 数据新鲜但容易一次性使用

策略:

- 可以作为入口,但不是唯一 ICP。

### 4.2 Layer 2:Semi-passive Professional

痛点:

- 不想公开求职
- 不想频繁更新 LinkedIn
- 希望好机会来时被看到
- 职业资料分散
- AI 能力不知道如何表达

这是最符合我们生态目的的人群。

策略:

- 首批 MVP 要重点验证。

### 4.3 Layer 3:Creator / Consultant

痛点:

- 需要展示可信能力
- 需要 inbound leads
- 需要 AI-search visibility
- 有多平台资产

问题:

- 这群人已有工具和个人品牌方法
- 不是规模最大人群

策略:

- 适合做早期传播和案例,但不能只服务他们。

### 4.4 Layer 4:Corporate Silent Majority

痛点:

- LinkedIn frozen
- 不公开发声
- 工作成果受保密限制
- 可能有机会意愿但不表达

价值:

- B 端最想要
- 最难触达

策略:

- 长期最重要,但冷启动最难。

---

## 5. 对产品设计的直接建议

### 5.1 第一入口:职业资料整理,不是职业镜子

用户更容易理解:

> 上传简历,生成持续更新的职业能力档案。

而不是:

> 来看你的职业能力镜子。

后者抽象,前者具体。

### 5.2 第二价值:证明 AI 工作流

当用户完成基本档案后,再引导:

> 添加一个你用 AI 改造工作的案例,生成可分享证据卡。

### 5.3 第三价值:私密机会控制

当用户看到档案价值后,再引导:

> 你是否愿意在不公开求职的情况下,接收匹配机会?

这比一开始问 “Are you open to work?” 更自然。

### 5.4 第四价值:持续更新提醒

每 2-4 周提示用户:

- 你最近新增了什么项目?
- 你的技能图谱缺少什么证据?
- 你的目标岗位最近要求什么新技能?
- 有哪些机会偏好需要更新?

---

## 6. MVP 需求优先级

### P0 必须做

1. 简历 / LinkedIn profile 导入。
2. AI 抽取经历、技能、项目。
3. 用户确认和修正。
4. 基础职业档案。
5. AI workflow proof card。
6. 私密 opportunity preference。
7. 数据权限控制。

### P1 可做

1. JD match。
2. ATS readiness。
3. LinkedIn About 优化。
4. 多版本简历导出。
5. 证据源连接。

### P2 暂缓

1. 社区 / feed。
2. 公开主页 SEO。
3. newsletter 工具。
4. job board。
5. 完整 job tracker。

---

## 7. 90 天用户研究问题

必须用真实用户回答以下问题:

1. 不求职的人是否愿意上传简历?
2. 用户是否愿意让 AI 抽取并结构化技能?
3. 用户是否觉得 AI 抽取结果“比 LinkedIn 更像我”?
4. 用户是否愿意补充 AI workflow 案例?
5. 用户是否愿意设置私密机会偏好?
6. 用户是否愿意 30 天后回来更新?
7. 用户最担心什么? 数据隐私、老板看到、平台卖数据、结果不准,还是麻烦?
8. 哪种利好最强? 简历更新、能力地图、机会控制、AI proof,还是 ATS 优化?

---

## 8. 当前阶段判断

可以继续推进,但产品叙事要调整。

不要说:

> 我们做职业能力镜子。

应该说:

> 我们做一个免费的职业资产管理产品,帮你持续更新简历、整理技能、证明 AI 工作流,并在你允许时把合适机会带到你面前。

内部再补一句:

> 这个 To C 产品的最终商业价值是构建 B 端无法从 LinkedIn 获得的实时、多维、用户授权的人才数据生态。
