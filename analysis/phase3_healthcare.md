# Phase 3 — Healthcare Industry AI Adoption Report

**Scope:** US-led with UK/EU signal where relevant. "Healthcare" deliberately treated as
multiple sub-industries because the variance inside the sector is larger than the variance
between most other industries. Sub-groups assessed separately: (1) clinical physicians
(MD/DO), (2) clinical researchers / MD-PhDs, (3) nurses & NPs/PAs, (4) health informaticists
& CMIOs, (5) digital health startup employees, (6) health content creators / MD-influencers,
(7) aesthetic medicine providers, (8) mental health practitioners. Date: 2026-05-25.

---

## A. AI 渗透成熟度

### A.1 头条结论:**5.5 / 10**(置信度:中-高)

整体落在中间偏低,但和法律一样,均值掩盖了巨大的子群体方差。准确读法:

| 子群体 | 渗透度(0-10) | 描述 |
|--------|--------------|------|
| 大学术中心 academic medicine | **8.0** | 已部署 enterprise scribe + clinical decision support |
| 大型医院系统(>400 beds, system-affiliated)| **7.5** | 96% 部署 predictive AI,scribe 滚动中 |
| 独立中小医院 | **4.0** | 37% 独立医院部署 predictive AI |
| 临床医生(个人使用)| **7.0** | 81% 用 AI(主要 ChatGPT/scribe),但是私下用 |
| 临床研究员 / 学术 MD-PhD | **8.0** | 论文 / 蛋白结构 / 试验设计已被 AI 改造 |
| 护士 / NP / PA | **5.0** | 工具刚向他们开放,但工作流没改 |
| 健康信息学 / CMIO / digital health | **8.5** | 这就是他们的本职 |
| 数字健康初创员工 | **9.0** | 等同于科技行业 |
| 健康内容创作者(MD-influencer)| **6.0** | 用 AI 做选题 / 剧本,但身份核心仍是临床权威 |
| 医美 / med spa providers | **5.0** | 营销侧用 AI 重,临床侧基本不用 |
| 心理健康从业者 | **4.5** | BetterHelp/Talkspace 平台引入,个人执业者抵触 |

### A.2 个人采用 vs 机构部署:**全行业最大的鸿沟**

- **AMA 2026 年度调查**:81% 的医生职业上使用 AI(2023: 38% → 2024: 66% → 2025: 72% → 2026: 81%)
  [P3HLT-001]。
- **Doximity 2026 报告**:54% "正在临床实践中使用",但只有 8% 的医生说他们清楚所在
  机构的 AI 政策;47% 说政策"仍在演化中"[P3HLT-002]。
- **机构侧**:71% 的 non-federal 急性期医院使用预测性 AI(2024,从 2023 的 66% 提升),
  但部署率严重分层:大型医院(>400 beds)96%,小型 59%,critical access 50%,独立医院 37%
  vs system-affiliated 86% [P3HLT-005]。
- 这是本行业最重要的事实:**医生在偷偷用 ChatGPT,医院在公开部署 Abridge,中小型机构两者都没有。**

### A.3 拐点:**临床医生侧已过,机构侧未过**(置信度:中)

支持已过:
- 个人使用 38% → 81% 三年翻倍以上 [P3HLT-001]
- 100+ 健康系统部署 Abridge,包括 Hopkins(6,700 临床医生)、Mayo Clinic(2,000)、MSK [P3HLT-003]
- OpenAI 2026-04 直接为 verified 临床医生推出 ChatGPT for Clinicians [P3HLT-009]
- 数字健康融资 $14.2B(同比 +35%),AI 占 54%,15 个新独角兽 [P3HLT-004]
- Kaiser NorCal 单家系统 ambient AI 一年节省 15,700 临床医生小时 [P3HLT-008]

支持未过:
- 71% 医生把"准确性可靠性"列为最大顾虑(儿科 78%)[P3HLT-002, P3HLT-026]
- 88% 担心 AI 导致医学技能流失 [P3HLT-001]
- 47% 医生说所在机构 AI 政策仍在演化 [P3HLT-002]
- 50% 部署 AI 的医院没有系统性的 post-implementation monitoring [P3HLT-005]
- 学习医学系统(Learning Health Systems)2025 警告说目前还无法断言 AI 会减少 burnout [P3HLT-008]

### A.4 广泛采用的工具

**Ambient AI scribe**(目前医疗 AI 的旗舰用例):
- **Abridge** — 100+ 健康系统,2025 KLAS 第一,$250M Series D [P3HLT-003]
- **Suki** — 通过 athenahealth 全网铺开,$70M Series D
- **Microsoft Nuance DAX** — 企业现任领导者
- **Nabla** — 欧洲入美

**临床决策支持**:
- **OpenEvidence** — 临床问答,刚拿 $200M 融资,被 Reddit r/medicine 反复推荐
- **UpToDate AI**
- **Aidoc** — 影像

**通用工具**(临床医生个人最主要的工具):
- ChatGPT(主导,40%+ 使用)
- ChatGPT for Clinicians(2026-04 推出,verified-only)[P3HLT-009]
- Microsoft Copilot
- Claude(被部分专科医生用于文献综合)

### A.5 子岗位 AI 渗透最深的是谁?

Doximity 2026 按专科:Neurology 64% / Gastro 61% / Internal Medicine 60% / Family Med + Cardio 58% / Oncology 57% [P3HLT-002]。
Burning Glass 2025 后半年:AI/ML 招聘标签 YoY +42%,但增速最快的是 nursing、health
administration、pharmacy(不是临床医生)[P3HLT-012]。

**真正"被 AI 改造最深的"** 不是临床医生本人:
- 病历记录 / 编码(医院计费 80% 已自动化)[P3HLT-005]
- Radiology 影像读片
- Sepsis 等高危预警
- 临床试验 protocol 设计
- 药物发现(Insilico / Recursion 等)

**最浅的:** 外科手术(高 stakes / 触觉)、急诊一线、 hands-on procedure-heavy 子专科、
精神科治疗师(治疗联盟核心)、小儿科(更高谨慎)。

### A.6 Cap money 信号

Rock Health 2025 年报:$14.2B 数字健康融资,AI 占 54%(YoY 37% → 54%),AI 公司平均
轮次规模 $34.4M(非 AI:$18.8M,溢价 83%),Series C 阶段溢价 61% [P3HLT-004]。26 笔
mega deal,15 个新独角兽 [P3HLT-027]。**资本严重集中在头部企业**,这意味着"懂 AI 的
healthcare professional"在劳动力市场上是稀缺品但买方集中。

---

## B. "AI 能力"在医疗行业的具体定义

### B.1 这个行业的 AI 能力指什么?

医疗 vs 其他行业有一个**关键反差**:在大多数行业(legal、marketing、design),"会用 AI"
是个加分项,是新形态生产力的代名词。**在临床医疗里,"会用 AI"既是加分也是潜在风险。**

显性能力维度:
1. **Ambient documentation 工具掌握**(基础) — Epic + DAX/Abridge/Suki 的工作流熟练度
2. **临床文献综合 prompt 能力** — 把 ChatGPT 用作 UpToDate 的延伸,识别幻觉的能力
3. **clinical informatics 技能** — Python/R/SQL,SNOMED/LOINC,HL7/FHIR,AI 模型评估 [P3HLT-018]
4. **AI governance & post-implementation monitoring** — CMIO/Chief AI Officer 的核心 [P3HLT-017]
5. **临床研究里的 AI** — 试验设计、特征工程、患者分层、新药发现 [P3HLT-012]

隐性能力维度(常常被忽略但更值钱):
6. **判断 AI 何时不可信** — JAMA 数据显示 AI 临床推理已超越 attending [P3HLT-013],
   但医生的核心价值正从"推理"转向"判断 AI 推理什么时候靠谱"
7. **解释 AI 决策给患者** — FSMB 明确要求医生"必须能向患者解释 AI 如何工作" [P3HLT-006]
8. **AI-related malpractice / 合规判断** — 这越来越成为 in-house 法务的姐妹技能

### B.2 招聘方如何评估?

按 JD scan(Indeed/ZipRecruiter,Phase 3 healthcare 抽样 [P3HLT-018, P3HLT-024]):

- **临床岗(physician,nurse)JD 中 explicit AI 要求 < 5%**。绝大多数仍以 ABMS/state license/
  residency 描述身份。**"AI 能力" 在临床 JD 里几乎不出现。**
- **CMIO / 临床信息化 leader JD**:几乎 100% 提及"AI/ML strategy"、"clinical decision support
  deployment"、"governance framework" [P3HLT-017]
- **Healthcare AI engineer / data scientist JD**:技术栈 + 临床 domain knowledge(HIPAA、
  SNOMED、LOINC、HL7/FHIR),薪资 $90K-$200K+ [P3HLT-018]
- **Hippocratic AI 模式**:digital health 企业反向招临床人员当"clinical safety reviewer"
  和"clinical content lead",**临床信用是 AI 公司的护城河,而不是相反**[P3HLT-024]

ABMS 仍是定义医生身份的核心 — 24 个 board,38 specialties,89 subspecialties,~100 万
持证医生,每日更新的公开 verifiable 数据库 [P3HLT-011]。**这是行业的"GitHub":每一个医生
都已经有一个权威平台在公开承载其专业身份的硬证据。**任何外部职业身份产品都在 ABMS 的
阴影下竞争。

### B.3 招聘方对"AI 能力"的真实评估方式

**对临床岗**:基本不评估。看 board cert、看 residency、看 publications、看推荐信。
"会用 AI" 是 nice to have,不是 must。**显性炫耀 AI 能力反而可能引发"医生想偷懒"
或"敢于走 AI 边缘"的红旗解读**(配合 FSMB 把医生置于 AI 错误第一责任人的规则 [P3HLT-006])。

**对 CMIO / informaticist 岗**:核心评估。看以往部署案例、看 publications on health
informatics、看 AMIA / HIMSS 认证(CAHIMS, CPHIMS, CPHI, CHDA)、看 governance experience。

**对 digital health startup 岗**:类似科技行业。LinkedIn 项目展示、GitHub、博客、
学术 citation,但加 + clinical credibility 作为差异化。

---

## C. 用户行为

### C.1 医疗专业人士如何展示自己的能力(包括 AI)?

**临床医生的真实身份展示路径**(按重要性):
1. ABMS board certification(公开 verifiable)[P3HLT-011]
2. Hospital privileges(私下,但是 referral 网络可见)
3. Doximity 主页(80% 医生已有 verified profile)[P3HLT-010]
4. UpToDate / Medscape / 期刊作者
5. LinkedIn(主要 for 跨行业 mobility,如转去 industry / pharma / startup)
6. KevinMD / Substack / Medium / X 博文(thought leadership 子集)
7. TikTok / YouTube / Instagram(MD-influencer 子集 [P3HLT-019, P3HLT-021])

**关于 AI 的展示**:**几乎不存在专门的"AI 能力展示"行为**。原因:
- FSMB 规则把医生置于 AI 错误第一责任人 [P3HLT-006],公开 boast "我用 AI"
  即把自己暴露在未来 malpractice 案件的证据链上
- 患者侧研究显示 AI 让 trust 系数下降(参见 TikTok AI doctor deepfake 现象 [P3HLT-020])
- ABMS 不为 AI proficiency 颁发任何认证;没有 AI 板的"medical board"

**MD-influencer 的例外**:KevinMD(2004 至今),SoMeDocs(Dana Corriel,physician-turned-
entrepreneur,specifically 帮医生做 LinkedIn 品牌)[P3HLT-021]。但这个生态的核心是
**clinical thought leadership 或 wellness/lifestyle/entrepreneurship 品牌,不是 AI proficiency**。

**唯一可见的 high-end MD-with-AI brand 是 Eric Topol**(Substack Writer in Residence,
hundreds of thousands of subscribers)[P3HLT-016]。Topol 是 academic cardiologist /
Scripps Research,不是开业医生。**这个模型不向 community physician 下放**。

### C.2 行业专属展示平台:**已经被 Doximity 占据**

Doximity 反复在 marketing 中讲自己"不是新 LinkedIn",而是临床用 messaging + 转诊
+ 行业内 reputation 工具 [P3HLT-010]。

- 80%+ 美国医生 verified
- HIPAA 合规 messaging
- 期刊 newsfeed
- Telehealth Dialer
- Talent Finder($12K/seat/year 卖给招聘方)
- 平均 $375/小时的 in-platform consulting 报价

**任何 "physician identity product" 必须解释为什么用户会同时维护 ABMS + Doximity + 我们的产品**。
这是本行业最大的 distribution moat。

护士 / NP / PA 没有等价 Doximity(Doximity 收他们但不为核心);心理治疗师有
Psychology Today directory;医美没有等价物;digital health 员工就在 LinkedIn 上。

### C.3 痛点

- **Pajama time**:医生每天在 EHR 里花 4.5 小时,延伸进晚间 / 周末 [P3HLT-008]。
  Ambient AI scribe 减少 30 min/day(UW Health 随机对照试验)[P3HLT-008]。**这是
  目前 #1 痛点**,但被 Abridge/Suki/DAX 收割中。
- **Trust gap with AI**:71% 把准确性可靠性列为最大顾虑 [P3HLT-002, P3HLT-026]。
- **Skill loss 焦虑**:88% 担心住院医生/学生因为依赖 AI 而流失基本临床推理能力 [P3HLT-001]。
- **Career sidestep 焦虑**:Bay Area 医生因债务和成本压力,去 Mercor 做 RLHF 标注
  专科 prompt,$80-$200/小时 [P3HLT-014, P3HLT-015]。这是一个非常具体的 AI 时代的
  侧业经济。
- **Identity ambiguity**:从临床医生 → digital health startup 员工 / 顾问 / AI 公司
  safety reviewer,身份切换难以表达。LinkedIn 太宽泛,Doximity 太临床。**这是产品空白**。
- **小型 / independent / rural 医院的 AI exclusion**:他们的医生用 ChatGPT 但没有
  Abridge,没有 Epic Copilot,事实上处于 second class 状态 [P3HLT-005, P3HLT-023]。

### C.4 generational gradient(关键)

JMIR 早期数据:对 ChatGPT 用于临床实践,医学生 68% 正面 vs 毕业医生 42% 正面 [P3HLT-025]。
Doximity 2026:Under-30 医生采用 61% vs 60+ 显著低 [P3HLT-002]。

**这个 gradient 是产品入口最干净的信号:服务的应该是医学生 + 住院医师 + early-career
attending(0-10 年从医)**,这是 AI 适应度高、Doximity-loyalty 还未固化、跨行业 mobility
意愿强、对 LinkedIn 不满的群体。

---

## D. 作为切入点的评估

### D.1 用户可触达性

**可触达性中等偏低,且非常分层。**

- 临床医生:Doximity 已占领;LinkedIn 渗透浅(50-60% 注册但活跃度低);
  X 上的医生是一个小圈子;Reddit r/medicine(2.1M+)聚集但 anonymity 高;
  KevinMD / Substack 受众已经被瓜分。
- Clinical researcher:Twitter/X(被严重削弱),Mastodon-bio(小众),ResearchGate,
  期刊网站。
- Healthcare AI engineer / digital health startup 员工:LinkedIn 完全主导,GitHub 部分。
- MD-influencer:Instagram/TikTok/YouTube/Substack,但已有 MedFluencers/SoMeDocs 等
  代理商在服务 [P3HLT-021]。
- 医美 / med spa:Instagram + Google Maps + 本地 SEO,与"职业身份"概念离得远。
- Mental health 治疗师:Psychology Today directory,保险面板,本地诊所网站。

**用户难找。临床医生隐藏在医院体系内,LinkedIn 不是他们的主要 channel。**

### D.2 付费意愿

- **临床医生(attending)收入高 $250K-$500K+,付费能力强,但**:对 in-clinical 工具
  的付费决策权在医院 / IT 部门,不在自己;对 personal brand 付费意愿低
  (SoMeDocs/MedFluencers 模式 working 但小盘子,几千-万级用户)。
- **CMIO / informaticist**:付费能力强,但他们买的是企业级工具,不是 personal identity。
- **Digital health startup 员工**:科技行业行为模式,付费意愿与软件工程师相当。
- **Resident / early-career**:负债重($200K+ 平均医学院贷款),付费能力低。
- **MD-influencer**:头部赚得多但小盘子。
- **Aesthetic providers**:营销付费意愿高($1K-$10K/月 ad spend);职业身份产品付费意愿不明。

**总体付费意愿评估:中性偏低,且付费来源严重分裂(机构买 vs 个人买)。**

### D.3 分享意愿

医疗是**全行业最低**。原因:
- HIPAA / 患者隐私:不能晒"作品"。临床案例如果不脱敏严格违规。SoMeDocs 训练
  physician influencer 的第一课就是隐私边界 [P3HLT-021]。
- FSMB AI 责任规则:不能晒 "用 AI 做的事" 因为这会成为未来 disciplinary / malpractice
  证据 [P3HLT-006]
- ABMS 已经垄断身份认证;晒"自己被认证为什么 specialty"在 ABMS 已经做了
- TikTok AI-doctor deepfake 问题让公众信任降低,clinician 不愿在低-trust 平台暴露
  [P3HLT-020]
- 临床医生职业文化偏向 conservative,公开 self-promotion 仍带有 stigma

**Exception sub-groups(分享意愿高)**:
- Digital health startup 员工 — 科技行业行为模式
- 临床研究员 / academic — 已经 incentivized to publish
- MD-influencer — 但已经在 IG/TikTok/Substack 上做了
- 部分早期-career 医生 — eager to build profile

### D.4 市场规模

如果"healthcare professional with AI literacy"算总池:
- 美国 ABMS 持证医生 ~100 万 [P3HLT-011]
- 美国 NP/PA 合计 ~40 万
- 美国 RN ~430 万
- 美国 health informaticists ~10-15 万(估算,基于 AMIA 会员 + Burning Glass 标签)
- 美国 digital health 全员工 ~30-50 万(Rock Health 50+ 独角兽 × ~hundreds 员工/家
  + long tail [P3HLT-004])
- 全球可扩展约 5-8x(英国 GMC + 欧盟 + 加拿大 + 澳新)

**可触达 + 愿付费 + 愿分享 的交集**(我们真正的 TAM):
- Digital health startup 员工(完全 tech-industry 行为模式):**美国 30-50 万**
- 临床信息学专业人士(career identity 与 AI 完全对齐):**美国 10-15 万**
- Early-career physicians(0-5 年 attending)做 side hustle / 想跨界:**美国 ~15-25 万**
- MD-influencer 候选人(目前 IG/TikTok 上活跃):**全球 ~10-20 万**
- 临床研究员 / MD-PhD:**美国 ~5-10 万**

**真正可服务的核心:75-130 万人,全球可能 4-6 倍**。比律师小,但绝对数字仍 healthy。

### D.5 推荐切入优先级:**4.5 / 10**

**理由:**

**赞成切入的因素(支持优先级)**:
- AI 渗透真实且快速(81% 医生,$14.2B 数字健康融资)[P3HLT-001, P3HLT-004]
- 存在清晰的 "hybrid identity 缺口":临床信用 + AI 流畅度的人是 Hippocratic AI
  等公司的金矿 [P3HLT-024]
- 跨界路径越来越普遍:Mercor RLHF / Sermo / startup advisor [P3HLT-014, P3HLT-015]
- Early-career 群体确实有展示需求且对 Doximity 的临床聚焦不满
- 全球可扩展性高(GMC / EUMS 等同结构)

**反对切入的因素(降低优先级)**:
- **Doximity 占据 80%+ 美国医生** [P3HLT-010],distribution 几乎不可能反超
- **ABMS 已经是 verifiable canonical 身份** [P3HLT-011],我们的"身份产品"价值就被压缩
- **FSMB 规则**让"晒 AI 能力"在临床岗本身就是 career risk [P3HLT-006]
- **HIPAA + 患者隐私**让"晒作品"在临床场景结构性不可能
- 医生付费意愿对 personal brand 较弱(SoMeDocs/MedFluencers 都是小生意)
- 资本和注意力集中在 enterprise B2B(Abridge/Suki),C 端 physician-identity
  历史上没有大成功(Doximity 是唯一一个,且通过 enterprise tilted 模式)
- 监管路径长,任何"职业身份产品"如果暗示帮 verify AI proficiency 都会触发
  ABMS / FSMB / FDA 的目光

**最务实切入路径**(如果真要切入):
1. **不要面向临床医生本人**。面向 digital health professionals + healthcare AI
   engineers + clinical informaticists — 这些群体是 tech-industry-style 用户,
   付费 + 分享 + 触达都更好,但他们的"healthcare-ness"已经被 LinkedIn + GitHub
   服务了
2. **如果要面向临床医生,只面向 early-career + 跨界意图明确者**,做的事是"为想跳
   出临床岗的医生准备的 hybrid identity 工具",主打 AI side hustle / startup
   advisor / consultant 跨界路径,而不是临床能力
3. **绝对避免 "show off AI in your clinical work"** 这个 angle,FSMB 规则下这是
   反向卖点
4. 医美 / mental health / wellness 因为身份逻辑更接近 small business,不在职业
   身份产品的核心命题里

### D.6 子结论

医疗对本产品的吸引力呈"中等偏低"。**核心问题不是 AI 渗透不够(渗透很高了),而是
"职业身份"在这个行业已经被 ABMS + Doximity + state license 高度产品化,且 FSMB/HIPAA
的规则结构性压制 AI 能力的公开展示**。

医疗里的 AI 转移机会真实存在 — 但它不是"医生 + AI = 新身份",而是 "从医生转去 AI"
的轨迹。如果做产品,应该服务那条 reverse career path,而不是 enhance 临床岗本身。

---

## 调研局限性

1. **缺乏一手 raw 数据**:Doximity 报告页面和 AMA 报告页面对 WebFetch 403,主要数据
   来自 search snippets 和 trade press summaries。直接读全文可能改变 use case 占比、
   demographic skew 等具体数字。
2. **未深度抽样 JD**:Phase 3 healthcare 没有逐条爬 100+ Indeed/LinkedIn JD,JD 分析
   基于汇总文章而非 first-pass scrape。临床岗里 AI 要求"< 5%"是估计,可能有误差。
3. **Reddit 一手观察缺失**:r/medicine / r/Residency / r/nursing 一手帖子搜索受限,
   分析基于 secondary write-ups(如 DeepCura 的 reddit aggregation)。可能错过 reddit
   原生的反 AI 情绪。
4. **国际数据不足**:报告以美国为锚,英国 NHS / 加拿大 / 澳新 / 欧盟数据点不足。
   可能低估或高估全球可扩展性。
5. **数据时序混杂**:同一行业里 2025-04 / 2025-09 / 2026-02 / 2026-04 的数据点并存,
   而本行业的 AI 渗透 6 个月就能变化 10+ 百分点。"81% 医生用 AI"是 2026-02 数字,
   不一定到 2026-05 仍稳定。
6. **付费意愿是推断而非验证**:用户付费 / 分享意愿基于行业文化 / 已有产品定价信号
   推断,没有针对本产品概念的一手 user research(那是 Phase 2 任务,不是 Phase 3 任务)。
7. **可能低估了 mental health / aesthetic 子群体**:这两个子群体在本报告内不是焦点,
   但 mental health 是 BetterHelp/Talkspace 等大平台的强 use case,aesthetic 是
   Instagram-native 的小商业 — 我可能漏估了 mental health 心理治疗师作为"verified
   creator"的潜在市场。
8. **prompt injection 注意**:在抓取 IntuitionLabs 页面时遇到一段嵌入式 plan-mode
   触发 prompt injection。已识别并忽略,但提示后续 Phase 应该警惕第三方网页可能含有
   对抗性指令。
