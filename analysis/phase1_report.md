# Phase 1 Report: 范式转移验证(招聘端视角)

调研日期: 2026-05-25
分析师: Phase 1 接力 agent(基于前任 32 次搜索 + 10 份 raw_data + 接力 18 次搜索 / 7 次 WebFetch)
引用条数: 42 (P1-001 … P1-042)
对应 raw_data: `F:\ai-talent-research\raw_data\phase1\` 共 19 个文件

---

## 执行摘要

**趋势 1(作品/能力主导取代经历主导)强度评分: 4/10**
证据显示一个真实但**被严重夸大**的趋势。在工程师、设计师、AI-native 创业公司这些细分群体里,portfolio/GitHub 已是事实上的硬要求 [P1-014, P1-026, P1-034];但在宏观经济层面,Harvard/Burning Glass 的 11,300 个去学位职位研究显示,十年间宣布"技能优先"的岗位实际非学位录用率只多了 0.14 个百分点——仅每 700 个录用中多 1 人 [P1-013, P1-027]。"resume is dead" 的叙事强度远大于实际经济动作。

**趋势 2(AI 能力作为显性招聘要素)强度评分: 8/10**
极强,且在多个独立数据集上收敛: Lightcast 显示 GenAI 岗位从 2021 年的 55 个长到 2025 年 5 月的约 10,000 个,涨 180 倍;非 IT 岗位 AI 要求 2022-2024 年涨 9 倍 [P1-001]。PwC 1B+ 招聘广告显示 AI 岗位工资溢价从 25% 跳到 56%,需求年增 7.5% 而总岗位下降 11.3% [P1-003]。GTM 角色里 AI 要求贴文 24 个月内涨 1,438% [P1-004]。但**含 hype 折扣**:候选人这边 32→63% 在简历上夸大 AI 能力 [P1-010, P1-019],企业实际 AI 落地价值有 95% 实施零回报的争议 [P1-018]。

**Top 3 发现**
1. **真正的范式转移不是"经历→作品",而是"静态简历→可三角验证的多源身份"**。LinkedIn 没死,简历没死;变化的是招聘方现在会同时打开 LinkedIn + Google + GitHub + 个人站,**横向对照**几个来源决定真伪 [P1-011, P1-032]。这对我们的产品意味着——目标不是替代 LinkedIn,而是成为"recruiter 三角验证时最值得跳转过去的那个面"。
2. **AI 能力要求最快渗透在 GTM / 营销 / 内容 / 设计 / 中级法律金融岗位,而不在 AI 工程师岗位**。这恰好命中 CONTEXT.md 假设的"AI 受益者"群体——但他们既无 GitHub 也无 LinkedIn 之外的展示渠道 [P1-001, P1-004, P1-015, P1-024]。
3. **整个招聘信号系统正在崩溃,trust 是更大的问题而不是 features**。70% 招聘经理信 AI 筛选,只有 8% 候选人觉得公平;41% 候选人承认用 prompt injection 绕过 ATS;28% 用 AI 生成假作品集 [P1-011, P1-012, P1-029]。任何新身份产品如果不解决**可验证性(provenance)**,只会成为新的造假表面。

---

## 一、"作品/能力主导取代经历主导"的证据

### 1.1 支持证据

**工程师岗位的"GitHub-as-resume"已是事实标准。** HN Trends 显示 2026 年 5 月 25% 的 "Who is hiring" 帖明确把 AI 列为顶级技术词,大量帖直接要求"public GitHub or portfolio with shipped projects" [P1-034, P1-035]。HN 高分讨论"With AI written resumes, what are the new hiring signals?" 中 top 评论 scarface_74 写道:"If you are blindly submitting your resume to an ATS, you've already lost." 他的经验是作为某热门 AWS 官方方案"second highest contributor"打开了门——而其他 OSS 贡献无人问津。换句话说:**portfolio 不是"有就行",signal density 才决定一切** [P1-014]。

**设计领域的 portfolio-leads-resume 在 2025 被明确表达。** UX/UI hiring blog 给出 2025 的标准做法:portfolio 装载 case study(problem-process-impact)、协作证据、metrics、prototype、video walkthrough、design philosophy;resume 退到"补充"地位 [P1-016]。Figma 自家 2025 数据: 73% 招聘经理表示 AI 工具熟练度需求上升,79% 表示"为 AI 产品做设计"是必需 [P1-015]。但这两个都是 vendor/recruiting 出版物,商业偏向需折扣。

**新职位的入口直接要求 portfolio**。Indeed 标准化的"Prompt Engineer"JD 模板明确写"no required computer-related degree... what matters most: demonstrable skill with AI tools and a portfolio showcasing prompt engineering abilities" [P1-026]。这是少见的、由主流 JD 平台官方表达的"portfolio over credential"立场。

**学位要求的真实软化(在 AI 暴露岗位)**。PwC 跨 1B 招聘广告分析: AI-augmented 岗位中要求学位的比例从 66%(2019)降到 59%(2024),AI-automated 岗位从 53% 降到 44% [P1-003, P1-038]。这是有具体百分点的、跨大样本的硬证据——但注意是"-7pp / -9pp",是缓慢漂移而非崩塌。

**Skills-Based Hiring Leaders 的成绩单**。在真正实施了 skills-based hiring 的 37% 公司里,非学位录用比例约多 20pp,留存率比有学位同侪高 10pp,薪资增 25% [P1-013, P1-033]。证明"能力优先"在执行良好时确实更优——但全经济层面只有 37% 的实施者真的做到了。

### 1.2 反对 / 质疑声音(强,必须重视)

**Burning Glass × HBS 的冷数据**:十年间 ~400% 的岗位移除了学位要求,但非学位录用比例只增长了 3.5pp;全经济范围年度增量仅 0.14pp、77M 录用中约 97,000 个——**少于每 700 个录用 1 个** [P1-013]。Joseph Fuller(HBS):"We found measurable but pretty modest changes... Changing your hiring policy is, at best, the end of the beginning." 三分类: 37% Leaders、45% In-Name-Only(只发声明)、18% Backsliders(撤回)[P1-013, P1-027]。

**LinkedIn / resume 都没死,只是变成多源三角验证的一环**。多个招聘咨询源(2025)的一致说法: recruiter "almost never reads your resume without LinkedIn open on the second monitor",87% recruiter 用 LinkedIn 主动 sourcing,简历 6 秒扫描决定 shortlist [P1-032]。HN 高分 thread 里 portfolio 也不能单独取胜——"signal density"是关键,小项目不算 [P1-014]。

**AI-generated portfolio 本身已是造假表面**。Greenhouse: 28% 候选人承认用 AI 生成假作品集,32% 谎报 AI 能力 [P1-010, P1-029]。GCheck 2026 年 5 月: 63% 工作者承认在简历上夸大 AI 技能 [P1-019]。换句话说,把 portfolio 当 ground truth 是天真的——这恰恰说明**需要可验证的、有 provenance 的作品身份**,而不只是"上传 PDF"。

**信号系统全面崩溃**。LinkedIn 申请量 YoY +45%,2025 年 6 月峰值 11,000/分钟 [P1-011]。同一份调查里 65% 招聘经理抓到 AI 作弊申请,74% 比一年前更担心欺诈 [P1-012]。Daniel Chait(Greenhouse CEO):"You end up basically not being able to tell anyone apart." [P1-011] 在这种环境下,无论是 resume 还是 portfolio,任何 PDF/网页形式的"静态展示"都在快速贬值。

**GitHub 不是公平评价器**。Shubham Sharma(2025):"GitHub contributions should not be the sole determinant... especially for junior developers... should be used as one piece of a larger puzzle." [P1-037] 这反映了一种成熟的妥协:portfolio 是输入而不是判决。

### 1.3 在哪些行业 / 岗位最明显

**显性 portfolio 取向最强(已经发生)**:
- 软件工程,尤其 AI-native 创业公司——Augment Code 已把评价从"会不会写代码"转到"能不能驾驭 AI agent"和"system judgment" [P1-005]
- UX/UI 设计——portfolio 决定面试入口,Figma 数据显示 56% 公司在抢资深(对应 25% 招初级,junior pipeline 在压缩) [P1-015, P1-016]
- Prompt engineer / AI content writer / AI marketing manager 等新类目——这些是 portfolio-first 而非 credential-first 设计的 [P1-022, P1-024, P1-026]

**软化中但仍以经历为主**:
- AI-augmented 普通岗位整体(PwC -7pp/-9pp 学位要求降幅是确认的,但绝对仍是大头) [P1-003]

**几乎没变(credential gate 仍然主导)**:
- Big Law(JD + Bar 必需,只是"AI 能力"层叠加进入选择函数) [P1-006]
- 投行 / 临床医生 / RN(license 必需;AI 能力是 ON TOP,不替代) [P1-006, P1-007, P1-023, P1-042]

**关键洞察:在所有这些"AI 能力是 ON TOP"的行业,目前根本不存在合适的展示工具**——你怎么向 Skadden 律所 partner 展示你做的"用 GPT-5 构建合同条款比对工作流"?LinkedIn 表达不了,GitHub 律师不会上,blog 太重。这就是我们假设的市场空白的真实形状。

---

## 二、"AI 能力作为招聘要素"的证据

### 2.1 哪些行业开始把 AI 能力写进 JD

**宏观: 现在是跨行业默认。** Lightcast 1.3B 招聘广告分析: 2024 年 51% 的 AI 岗位发生在 IT/CS 之外(2019 是 39%);非 IT 岗位的 AI 要求 2022-2024 涨 9 倍;非科技行业的 GenAI 岗位 2022 以来涨 800% [P1-001]。Axios 2025-11: "AI 能力是黯淡就业市场的唯一亮点。"[P1-020]

**行业级数据 (2024-2025 增长率,Lightcast)**: HR +66%(领先所有行业),Education/Training +200%,Finance +40%(低基线),Marketing/PR 8% 的岗位现在要 AI,年增 50% [P1-001]。

**GTM(销售/营销): 三位数增长在两年内**。Growth Unhinged 数据: tech GTM 岗位中要 AI 技能的从 65 (Jul 2023) 涨到 ~1,000 (Jul 2025) —— 1,438% 涨幅 [P1-004]。受影响角色范围广泛: 社媒制作人、付费搜索专员、BDR、营销分析师、内容营销 manager、产品营销、CMO。

**具体 JD 措辞样本** (Growth Unhinged 收集):
- 底端: "working proficiency of AI tools like ChatGPT"
- 顶端: "skills using AI copilots and agents to personalize messaging, automate outreach, and surface insights from CRM data" [P1-004]

**新职位类别的诞生**:
- Stripe: "AEO/GEO Marketing Manager"(Answer/Generative Engine Optimization)—— 这个角色 18 个月前根本不存在 [P1-021]
- OpenAI: "Product Marketing Manager, ChatGPT for Work" —— AI 公司自己定义的 AI 营销岗 [P1-025]
- Kevan Lee 公开的"AI Marketing Manager" JD 模板,要求 AI 工作流改造的可证案例 [P1-022]
- Indeed 把"Prompt Engineer"列入标准化 JD 模板 [P1-026]

**法律/金融的"layered AI 要求"模式**: Big Law 不再雇这么多初级,转向能 day one 处理 live matter 的 lateral——其中 AI 熟练度被 Stanford Law 招聘 administrator 直接称为"makes more attractive candidates" [P1-006]。Wall Street 顾问 Christoph Rabenseifner(Deutsche Bank): "The easy idea is you just replace juniors with an AI tool." 大行考虑 junior banker 招聘最多砍 2/3 [P1-007]。

**医疗 (credential-gated 极端)**: AAACN 在 2025 Essentials framework 中加入 AI/informatics 强制能力;71% 美国医院已部署预测性 AI;Nursing Outlook 的 N.U.R.S.E.S. 框架要求 RN 掌握 AI 工具评估 [P1-023, P1-042]。但 license 仍是入门门槛——这是"AI ON TOP" 最纯的例证。

### 2.2 招聘方如何评估候选人的 AI 能力

**实际方法仍然原始**。前任 raw_data + 我的补采都没找到一个具体的、广泛部署的"AI 能力评估方法论"。最常见的实际做法:
- 在面试中要求候选人"现场用 AI 工具完成一个真实任务"——Augment Code 描述的"agent leverage"评估属于这类 [P1-005]
- 看是否有可指认的 AI 改造案例——Growth Unhinged 提到"curiosity + practical experimentation > specific certifications";Zapier 报告 89% 员工"AI-fluent"作为雇主标签 [P1-004]
- 标准化测验(HackerRank, CodeSignal 等)接受 AI 工具使用,转而看"how you use it"——技术招聘 take-home 邀请 2023 Jul-Oct 涨 86%

**问题: 自报 AI 能力是噪声极大的信号**。Greenhouse: 32% 谎报 AI 能力 [P1-010];GCheck 2026: 63% 在简历上夸大 [P1-019]。

**这是产品机会的核心**: 既然自报不可信、portfolio 易被 AI 伪造,真正稀缺的是"可验证的 AI 工作流证据"——比如 GitHub commit + AI 辅助记录、对话过程、迭代 trace。这正是 LinkedIn 无法服务、portfolio 网站不会做的东西。

### 2.3 反对声音 / Hype 折扣

**MIT Tech Review (2025-12)** :"95% of businesses trying AI implementations discovered zero value"(注:仅 measured bespoke systems past 6 months,排除了 informal employee use)[P1-018]。整年是"hype correction" [P1-018]。

**Fortune (2025-12-21)**: Wall Street 的"AI 杀岗位"故事大半是 narrative。Robert Seamans (NYU Stern):"AI is often a scapegoat for things, because it's easier to blame AI than softening consumer demand." Goldman Sachs 实际 headcount 反而从 46,500 (Sept 2024) 涨到 48,300 (Sept 2025);JPMorgan 加了 2,000 人;BoA 加了 4 人 [P1-008]。Pim Hilbers (BCG): "The general headcount trend in banking over the last decade is stable to slightly declining." [P1-008]

**Goldman 自己的判断 (Joseph Briggs, Lightcast/CBS)**: "AI is definitely visible in the micro labor market data, but it doesn't look like it's driving the overall labor market dynamic." [P1-028]

**Metaview 报告 (2025)**: 招聘方自己也对 AI hiring 警觉——40% 担心 AI 让候选人体验冷漠,35% 担心 AI 会漏掉独特能力者。LinkedIn 2025 内部研究: AI-assisted messaging 只带来 9% 的 quality-hire 提升——modest 而非革命 [P1-017]。

**HR Dive**: AI 技能要求的 JD 比例在大公司 65% vs 中型 45%——存在公司规模合成效应,聚合数据放大了"AI 已渗透到处"的印象 [P1-036]。

**净判断**: 趋势 2 评分 8/10 而非 10/10 的原因——language 涨得快,实际操作和价值兑现差很多。我们的产品不能假设企业 AI 渗透率与 JD 上"requires AI" 标签同步——后者比前者快得多。

---

## 三、关键招聘方观点摘录

1. **Daniel Chait, Greenhouse CEO**: "Trust is at an all-time low for both job seekers and recruiters... You end up basically not being able to tell anyone apart... Intent will be the new differentiator in hiring." [P1-011, P1-040]

2. **scarface_74 (HN top comment)**: "If you are blindly submitting your resume to an ATS, you've already lost." [P1-014]

3. **Stanford Law admin (paraphrased via Axios)**: "Students without prowess using AI risk being left behind." [P1-006]

4. **Augment Code (招聘宣言)**: "The highest-leverage engineer isn't the one who writes the most code. It's the one who ensures the team is solving the right problem... Think of [AI agents] as delegation — except your reports are incredibly fast and occasionally confidently wrong." [P1-005]

5. **Kyle Poyar (Growth Unhinged) on Zapier**: "89% of its employees are now AI-fluent." [P1-004]

6. **Robert Seamans (NYU Stern)**: "AI is often a scapegoat for things, because it's easier to blame AI than softening consumer demand." [P1-008]

7. **Christoph Rabenseifner (Deutsche Bank)**: "The easy idea is you just replace juniors with an AI tool." [P1-007]

8. **Joseph Fuller (HBS) on skills-based hiring**: "We found measurable but pretty modest changes... Changing your hiring policy is, at best, the end of the beginning." [P1-013]

9. **Elena Magrini (Lightcast)** on AI hiring breadth: "[The range is] from advanced AI-specific roles, such as AI engineers, to more general AI-related positions such as software developers." [P1-031]

10. **Paddy Lambros, Dex CEO**: "AI usage in first-round interviews is downright insulting and inhumane." [P1-011]

11. **Pim Hilbers, BCG**: "The general headcount trend in banking over the last decade is stable to slightly declining." [P1-008]

12. **Joseph Briggs, Goldman Sachs**: "AI is definitely visible in the micro labor market data, but it doesn't look like it's driving the overall labor market dynamic." [P1-028]

13. **Nik Guggenberger (U. Houston Law)**: "If more and more of that work that trains junior associates is being automated, then there's no real material anymore for them to train on." [P1-006]

14. **Paaras Parker (Greenhouse CPO)**: "Transparency, communication, and fairness are competitive advantages." [P1-030]

15. **UX/UI hiring blog prescription**: "Employers want designers who can demonstrate WHY a design decision was made, not just how it looks." [P1-016]

---

## 四、综合判断与对产品的启示(不在 prompt 强制清单内,但有强相关)

把三类证据放在一起:

- **趋势 1 是"两个事件"的混合**: (a) credential 软化在 AI 暴露岗位上真实发生但缓慢 (PwC -7pp/-9pp);(b) 在工程/设计/AI-native 公司 + 律师/银行家中高端 + 营销内容里,**多源证据三角验证**成为新的录用机制——而不是"portfolio 取代 resume"。这两个事件被叙事简化成"resume is dead"是错的。
- **趋势 2 强,但 AI-skill premium 是雇主"挂出来"的速度快于"实际筛选"的速度**。语言层渗透 8/10,操作层兑现仍只有 5-6/10。
- **真正的稀缺品不是"作品集",而是"可信的、有迹可循的能力证明"**。Greenhouse 28% 候选人用 AI 造假作品集 + 63% GCheck 数据告诉我们: 任何只是"上传更多东西"的产品都会被 AI 注水拖垮。

对我们 C 端产品的几个最具体的启示(超出本 phase 范围的需在 Phase 5 整合):
- 服务非工程师非设计师的"AI 受益者"群体——他们既无现成展示渠道,招聘方又显性需要他们的能力证据
- 必须解决 provenance / verifiability —— 不是"展示作品",而是"证明作品是你做的、AI 参与到什么程度"
- 不要碰 LinkedIn 的核心战场(身份+网络+主动 sourcing),而要成为 LinkedIn 之外 recruiter "triangulate to" 的那个面

---

## 五、调研局限性

### 5.1 样本偏差
- **HN/Reddit/X 高度不代表中位职业人群**。scarface_74 类的 AWS 顶级贡献者拿到 offer,不能推广到沃尔玛中层运营经理 [P1-014]
- **HR Dive 等行业媒体偏向大公司角度**。Burning Glass 数据只覆盖大型雇主,中小企业 skills-based 实施情况不明 [P1-013]
- **几乎所有数据偏 US/UK,欧洲大陆和亚洲(我们的目标市场之一)覆盖不足**

### 5.2 数据完整性
- **未访问 CNN 的"AI 招聘悲惨"文章**(WebFetch 返回 451 Legal),靠搜索引擎摘要补——可能错过细节 quotes
- **没有触达 Reddit 的具体 thread**(WebSearch 没返回相关链接)——招聘端 voice-of-recruiter 主要靠 HN + 报告而非 Reddit
- **没有逐行做 JD 文本扫描**。Indeed/LinkedIn 没开放底层数据,我们靠 Lightcast/PwC 等第三方加工后的数字,无法独立验证
- **GitHub-as-portfolio 讨论的具体 HN/Reddit 高分帖没找到**——Shubham Sharma Medium 是替代物,但是个人 blog credibility 较低 [P1-037]

### 5.3 不确定的判断
- **趋势 2 评分 8 vs 7**: AI-skill JD 涨幅数据强 (1438% / 9x / 800%),但操作落地有 95% zero value 的 MIT 数据反对 [P1-018]。我倾向把语言层趋势记为强,操作层折扣放到产品设计假设里
- **PwC 56% 工资溢价从 25% 跳起**:这跳得太大,部分是 composition effect(AI-required 角色 skews senior),需要 Phase 5 进一步交叉检验
- **"junior banker 砍 2/3"的预测 vs Goldman/JPM 实际加人**: 同一 6 个月窗口里两边数据对立。我倾向后者(实际行动)的可信度更高,因此 Big Law/Wall Street 的"AI 砍 junior" 故事在我报告里只作为**叙事/雇主希望**而非已发生事实
- **设计领域的"portfolio-leads-resume" prescription**: 来源 hubbedin 和 Figma 均有商业偏向。证据 medium 而非 high

### 5.4 没覆盖到的领域
- **教育行业** —— Lightcast 显示 200% 增长但未单独深入研究
- **政府/公部门** —— Burning Glass 提到 Minnesota 和 Denver 是 leaders,但具体岗位没看
- **小企业 (<200 人)** —— 数据几乎都来自大企业,对我们的潜在用户而言可能完全不同
- **欧洲大陆/亚洲** —— 主市场之一,本 phase 几乎完全没覆盖
- **HR / 招聘官自己的招聘**: 一个有趣的 meta 现象,Lightcast 显示 HR 是 AI 增长最快的行业(+66%),但没看到具体如何展开

### 5.5 自我评估
本 phase 整体置信度: 中-高。趋势 2 的存在性 (8/10) 我有高置信;趋势 2 的实际操作兑现度 (估 5-6/10) 置信中等。趋势 1 的"4/10"评分置信中等——我相信"被夸大"的判断,但具体在 4 还是 5,与对"未来 6-18 月加速度"的预测高度相关,本 phase 数据不能独立回答。

最该被 Phase 2(用户痛点)和 Phase 3(行业渗透)校准的: **"AI 受益者群体在不同行业里到底有没有展示需求 / 焦虑 / 主动行为"**——只有当个体侧需求与企业侧 JD 趋势对应,我们的市场假设才同时双向成立。
