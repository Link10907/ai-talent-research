# Phase 3 — Design Industry AI Penetration

调研对象:UX/UI 设计师、product designer、visual / brand designer、motion designer、
illustrator、design ops、design lead。覆盖 in-house product team / agency / freelance
三个市场。

---

## A. AI 渗透成熟度

### 总体评分:**7.5 / 10**

设计是 AI 渗透度最高、同时也是最分裂的行业之一。"AI 已成为日常工具"和
"AI 正在毁掉设计行业"两种声音并存,且都有数据支撑。

**采用率(quantified)**:
- Figma 对 2,500 名用户的调查显示,**85% 的设计师/开发者**认为学习使用 AI
  对未来事业是 essential 的;78% 同意 "AI 显著提升我的工作效率",但只有
  **32% 表示能够依赖 AI 的输出** [P3DSN-001]。
- Foundation Capital 对 400+ 设计师的调研:**96% 的设计师是自学发现 AI 工具**
  的;startup 比 enterprise 采用 AI 的速度快一倍 [P3DSN-002]。
- 2026 State of AI in Design 报告(906 名设计师 / 60+ 国家):设计师使用的
  AI 工具数量是 2025 年的两倍;约半数受访者 "已经将 AI 生成的代码推到生产环境"
  [P3DSN-003]。
- IAB 数据:到 2025 年中,**30% 的代理商 / 品牌 / 出版商已经把 AI 整合进
  工作流**;尚未整合的有一半预计明年完成;代理商比品牌方采用速度快近一倍
  [P3DSN-023]。

**广泛采用的工具/工作流**:
- **图像/视觉生成**:Midjourney(早期 mood / 风格探索)、Figma 原生 AI 图像生成、
  Adobe Firefly(品牌内容,因为训练数据合规)、DALL·E
- **UI 生成 / 原型**:Figma Make(2025-05 推出 prompt-to-code)、v0、Lovable、
  Bolt、Magic Patterns、Cursor;"vibe coding" 是 Collins 词典 2025-11 的
  年度词汇 [P3DSN-019]
- **运动/视频**:Runway Gen-4 + Sora 2 混合管线(Sora 做 cinematic ideation,
  Runway 做编辑细化)
- **DesignOps 杂活**:重命名图层、tag 资产、聚类 sticky notes、协作会议摘要

**AI 渗透最深的子岗位**:
1. **Motion / video designer**:Sora 2、Runway 已经能产出可用素材,
   Upwork 上 AI 视频生成/编辑技能 YoY +329%(增幅最大)[P3DSN-010]
2. **Illustration**:首当其冲被替代。Nature 杂志报道专业插画师公开点名
   科学期刊、新闻机构用 AI 图替代付费委托 [P3DSN-014];#notoaiart 运动
   在 DeviantArt / ArtStation 持续发声 [P3DSN-013]
3. **Junior / mid-level UI designer**:重复性、模板化的 banner、cropping、
   copy variant 等工作已经被 prompt 取代 [P3DSN-005]
4. **Brand designer**(在 AI-native startup):被要求用 AI 生成多变体 + 人来挑

**AI 渗透较浅的子岗位**:
- Senior product designer(战略 / 跨团队协作)
- UX research(91% 研究人员担心 AI 输出准确性)
- Design lead / design ops 战略决策层

### 拐点判断
**拐点已经过了**(2024 年中 ~ 2025 年初)。
证据:Indeed Hiring Lab 2025-09 报告指出 graphic design 已经出现 "增长低于
趋势,归因于 AI 效率"的现象 [P3DSN-017];美国 U Maryland Smith 商学院的
研究确认 design AI 对设计师就业构成可测量的威胁 [P3DSN-022];junior 岗位
SignalFire 数据显示 2019-2024 间 design new-hire 下降约 50%(跨职能均值)。

但要注意一个**反向证据**:Dezeen 报道(基于 Figma 数据)**81% 的设计师
认为 AI 钝化了创造力** [P3DSN-004]——这是所有创意职业里最高的比例。
这说明:渗透度高 ≠ 接受度高,设计师群体是"被迫接受"而不是"积极拥抱"。

---

## B. "AI 能力"在设计行业的具体定义

### 不再只是"会用 Midjourney"

招聘市场出现至少三层 AI 能力定义,且层次正在拉开:

**Layer 1 — 工具熟练度(table stakes)**:
- 熟悉 Figma AI、Midjourney、DALL·E、Firefly 等
- Adobe Suite + AI plugins
- 已经成为入门门槛而不是加分项 [P3DSN-020]

**Layer 2 — AI 工作流设计(differentiator)**:
- Parallel HQ 招聘指南给出的 AI-native designer 标准:
  "Idea → AI generation → Human judgment → AI iteration → Outcome"
  这套循环能否被设计师拆解、optimize、复现 [P3DSN-012]
- Prompt engineering 能力 — 美国 prompt engineer 平均年薪约 $136K
  (Glassdoor Feb 2025)
- 能"用 AI 出可上线 prototype"而不只是 mockup — Lovable / Cursor / v0
  已是 AI-native startup 招 designer 时的 standard expectation [P3DSN-018][P3DSN-019]
- ZipRecruiter 显示 Gen AI UX Designer 薪资带 $91k–$170k,
  JD 明确要求:"Experience with RAG, LLMs, designing UIs that maximize UX"
  "Conversation design principles and interaction patterns for AI interfaces"
  [P3DSN-016]

**Layer 3 — 为 AI 产品做设计(specialist track)**:
- Indeed 上 900+ 个 "AI Graphics Designer" 岗位,392+ 个 "AI Image Graphic
  Designer";部分岗位明确招人 "去训练 AI 模型,评估 AI 输出的美学/可用性/
  创意质量" [P3DSN-015]
- Agent Experience (AX) / Machine Experience (MX) — 新出现的能力维度,
  指为 AI agent 而非人类用户做设计 [P3DSN-006]
- Design Lead AI Strategy 类岗位(如 Dynatrace)要求 8+ 年产品设计经验
  + 3+ 年 leadership + 2+ 年 hands-on AI-feature design

### 招聘方如何评估

证据显示评估方式正在崩坏:

- **传统 portfolio 评估失效**:作品是 AI 生成还是设计师做的?静态图无法
  显示 prompt iteration、judgment call、决策依据。Quora、Behance 上正在
  形成共识 — "声明 AI 使用 + 解释自己贡献"是必须的 [P3DSN-021]
- **新的 signal**:Jenny Wen 总结的招聘三类型(senior strategists / 
  code-adjacent builders / "cracked new grads")暗示企业在用**间接信号**
  评估 — 是否能写代码、是否在 X 上 build in public、是否能讲明白 AI 在
  workflow 中的位置 [P3DSN-006]
- **73% 的招聘经理希望候选人 AI 工具熟练**,但具体怎么测,没有标准答案 [P3DSN-006]

### 典型 JD 长什么样(综合 2025 样本)

> "Required: 5+ years product design experience. Demonstrated proficiency
> with generative AI tools (Midjourney, Figma AI, Firefly). Ability to
> design AI-powered features including conversational interfaces and
> intelligent automation. Experience prototyping in code with Cursor /
> v0 / Lovable preferred. Portfolio must include at least one AI-augmented
> project with explanation of human vs. AI contribution."

[综合 P3DSN-012, P3DSN-015, P3DSN-016, P3DSN-018]

---

## C. 用户行为

### 设计行业的 AI 态度光谱(必须呈现张力)

这是本调研最关键的发现:**设计行业对 AI 不是 single attitude**,而是
至少四个互相冲突的群体并存:

1. **AI 拥抱派(builders)**:多在 AI-native startup、tech-forward 
   product company。把 AI 当作生产力放大器,主动 build in public,
   作品中明确标注 AI 使用。预计占行业 20-30%。
2. **务实派(pragmatists)**:用 AI 做杂活,但核心创作仍保留手工 + 判断。
   是 mainstream,预计占 40-50%。Smashing Magazine 的 practitioner 视角
   是典型代表:"AI is only as good as the questions you ask it...It doesn't
   replace your thinking" [P3DSN-007]。NN/Group 的 "future-proof designer"
   论述支持这一派:focus 在战略、判断、storytelling [P3DSN-008]
3. **焦虑派(anxious)**:81% 的设计师认为 AI 钝化创造力 [P3DSN-004];
   junior 设计师面对 "entry-level void" 找不到工作 [P3DSN-005];
   "It's a bit of a 'dog eat dog world'-type vibe" — Naheel Jawaid。
4. **抵制派(resisters)**:#notoaiart 运动、DeviantArt opt-out 抗议、
   illustrators 公开点名媒体不当使用 AI 图。情感上敌对,职业上感到被
   剥夺 [P3DSN-013][P3DSN-014]。

**重要张力**:同一个人可能同时属于多个群体——比如一个 illustrator 早上
用 Midjourney 探索风格,下午在 X 上骂 AI 取消他的 commission。这种
**职业现实与情感立场的撕裂**是设计行业独有的。

### 作品 vs 能力的关系复杂化

设计师有强 portfolio 文化(Behance / Dribbble / 个人站),但 AI 让
"作品是谁的"变得模糊:

- **Dribbble 正在死去** [P3DSN-009][P3DSN-024]。2025-03 强制 marketplace
  化、80% 的 job request 是 scam、AI-influenced "uncanny polish" 内容
  泛滥。Gleb Kuznetsov 被封事件 "crystallized what many designers were
  already feeling: that the trust was gone."
- **迁移方向**:Contra(更接近原 Dribbble 精神)、X / Twitter(直接展示
  + 拿机会)、Read.cv(more thoughtful resume)、个人站(完全自主)。
  没有一个新的主导者
- **portfolio 内容形式正在变化**:静态图不够了,招聘方要看
  - 你的 prompt 历史和 iteration 思路
  - 你的判断为什么停在这个结果
  - 你做的是 mockup 还是可交互的 working prototype(Lovable / v0)
  - 你的 AI workflow 是怎么搭的

这是一个**作品形态正在重塑**的窗口期,旧平台衰退、新平台未定。

### 痛点(按重要性)

1. **junior / mid 找不到入门 / 上升通道**:portfolios 投出去 "into an
   empty void",500+ 次冷启动联系才有一次面试 [P3DSN-005]
2. **如何向招聘方证明"我用 AI 用得好"**:目前没有标准 artifact 格式;
   prompt + 决策 + 迭代过程难以打包展示
3. **作品归属和披露困境**:声明 AI 用太多怕被认为"不会自己设计";
   不声明怕被视为不诚实 [P3DSN-021]
4. **焦虑与现实撕裂**:理性知道要拥抱 AI,情感上感到被取代 / 创造力被
   蚕食 [P3DSN-004]
5. **Dribbble 替代品分散**:没有新的事实标准聚合平台 [P3DSN-009]

### 行业专属展示平台现状

- Behance(Adobe,仍然主流但偏被动展示)
- Dribbble(衰退中)
- Read.cv(被 Perplexity 收购后产品收缩,失去信任)
- Contra(自由设计师向,接近原 Dribbble 精神,小)
- X(事实上的高 signal designer 社交,build in public)
- 个人站(art-directed personal sites,maintenance heavy)
- LinkedIn(被动 — 招聘方在这查背景但作品展示薄)

**结论**:没有一个平台同时解决 (a) 展示 AI workflow / 判断、(b) 信任问题、
(c) 招聘对接。这是产品空白。

---

## D. 作为切入点的评估

### 用户可触达性:**8.5 / 10**

- 设计师群体高度网络化、可被找到:
  - X / Twitter(top KOL: Mike Mihalyov, Pablo Stanley, Soren Iverson 等)
  - Substack / newsletter(UX Collective, Smashing, Sidebar)
  - 设计社区(Designer Hangout Slack, Femke's Design Buddies Discord)
  - Behance / Dribbble / Contra
  - 设计 bootcamp 校友网络(Designlab, BrainStation 等)
- Reddit(r/UI_Design, r/UX_Design, r/graphic_design)活跃度高,有强讨论文化
- Top 50 设计 KOL 的关注者覆盖大部分活跃设计师人口

### 付费 / 分享意愿:**6 / 10**

- **付费意愿**:中等。设计师习惯付费(Figma $15/mo, Adobe CC $60/mo,
  Midjourney $30/mo)— 工具付费文化存在,但已经被多个工具瓜分。新平台
  要进入 wallet share 不容易。Bento 简单付费版本可行,Pro 功能可能 $10-20/mo
- **分享意愿**:高。设计行业有强烈的 "show your work" 文化,build in 
  public 在 X 上是 norm。但需要解决:作品归属、AI 使用披露的标准化

### 市场规模

- 美国 BLS 数据:Graphic Designers ~270,000 人;Web/Digital Designers
  ~200,000+ 人;Industrial Designers ~32,000 人;加上 UX 研究员、Motion、
  Brand、Product Designer 等估计美国总量 **80-100 万**
- 欧洲(英德法荷北欧)再加约 60-80 万
- 全球(含中印)2-3 百万,但海外 TAM 约 150 万职业设计师 + 类似规模的
  半专业 / freelance / hybrid 角色
- Upwork 上 AI 相关 freelance 技能 +109% YoY [P3DSN-010]——市场在扩张,
  不是萎缩

### 推荐切入优先级:**8.5 / 10**

**理由**:

1. **范式转移正在发生且急迫**:旧 portfolio 平台衰退、新 portfolio 形态
   未成型、招聘方在用 AI 能力筛人但没有评估 artifact —— 这是 product
   shaped hole [P3DSN-006][P3DSN-009]
2. **junior pipeline 已经破碎**:就业市场倒逼新形态出现 [P3DSN-005]
3. **目标用户的复合身份强**:同时是"传统专业 + AI 应用者",符合 CONTEXT
   洞察 2 的"在传统行业里用 AI 创造新价值的人"画像
4. **可触达性极高**:设计师在 X / Twitter、Behance、Substack 等平台高度
   集中,冷启动相对可行
5. **作品文化深厚**:不同于销售、运营、HR 等没有天然 portfolio 的职业,
   设计师天然认同 "show your work" 范式
6. **AI 能力可视化的需求最强**:prompt + iteration + judgment 都需要新形
   态展示,而设计师对"展示形式本身"敏感、愿意付费

**主要风险**:
- 设计师对 AI 态度分裂,产品定位若过分 AI-centric 会得罪抵制派
- 已有竞品多(Dribbble、Behance、Contra、Read.cv)虽都不完美,但用户惯性强
- 设计师对 "design 的设计"挑剔,产品体验要求极高
- 仅服务 AI 拥抱派的话 TAM 缩到 20-30%

**减分项**:
- 不是首选切入点的两个理由:(1) 设计师群体被 well-served by tools(虽不
  perfect),不是 underserved;(2) 设计行业对 AI 的态度分裂可能让产品
  messaging 难做

### 建议切入策略(若选择设计)

1. **不要做"为 AI 拥抱派服务的 portfolio"** — TAM 太小且偏激
2. **做"AI 时代的能力证明型职业身份"** — 让务实派(40-50%)和拥抱派
   (20-30%)都能用,焦虑派 / 抵制派暂不强求
3. **核心产品形态**:可交互的"能力 + 作品 + 工作流"页面,支持展示
   prompt 历史、判断节点、人/AI 贡献划分、interactive prototypes
4. **冷启动切入**:UX/product designer @ AI-native startup(20K-30K 人)
   作为 alpha;motion + AI video 子群体作为高 LTV 早期付费用户
5. **不要直接和 LinkedIn 竞争** — 做 LinkedIn 链接出去的"作品证明型"
   补充,不做替代

---

## 调研局限性

1. **样本偏差**:本调研依赖的几乎所有数据源(Figma、Foundation Capital、
   State of AI in Design、Adobe、Upwork)都是 AI-positive 利益相关方,
   会放大采用率、低估抵制度。Dezeen / Nature / itsnicethat 等第三方
   来源部分校准了这种偏差,但仍可能高估"AI 已经渗透"的事实。
2. **地理偏差**:大部分数据来自美国 + 西欧。日本、印度、东欧、拉美设计师
   群体的 AI 态度和工具采用模式可能显著不同,本报告无法覆盖。
3. **薪资 / 失业数据的归因问题**:graphic design 行业增长低于趋势,
   归因于 AI 是一个 plausible 解释,但 2024-2025 也叠加了 marketing
   budget 收缩、tech layoff 等其他因素,纯 AI 影响无法干净分离 [P3DSN-017]。
4. **未直接抓取 Reddit/X 一手讨论**:WebSearch 在 Reddit 上命中率低,
   时间约束下未做深度 r/UX_Design / r/graphic_design 的帖子级别分析。
   一线情绪可能比报告呈现得更分裂、更负面。
5. **没有访谈 in-house 招聘方 / hiring manager**:JD 文本是间接信号,
   真实的"AI 能力如何被评估"需要 hiring manager interviews 来验证。
6. **Read.cv / Polywork / Contra 等竞品深度分析不足**:这部分留待
   Phase 4 处理。
7. **Behance Adobe / Dribbble Tiny 等平台战略未来动作不可知**:它们
   可能主动迭代成为新形态的承担者,挤压新进入者空间。
8. **20-30% / 40-50% / etc. 的态度群体占比是基于现有数据的合理推断,
   不是测量值**,需要后续定量调研验证。
