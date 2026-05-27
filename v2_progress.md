# V2 执行进度 + 模型决策日志

## 元决策
- v1 文件保留原位,v2 用 `v2_` 前缀 + 新 phase 编号(01..08)避免冲突。理由:auto classifier 阻止了 v1 文件大规模移动,且 v1 是有价值的参考资料,不应覆盖。
- 引用 ID 从 V001 开始(v1 用 C001),全局唯一,避免命名冲突。

## 时间线
- 2026-05-26 项目启动,搭建骨架。

## 模型决策日志
(每次切换或派发 sub-agent 在此追加一行)

| 时间 | Phase | sub-agent 名 | 模型 | 任务类型 | 理由 |
|------|-------|--------------|------|----------|------|
| 2026-05-26 | meta | (主 agent) | opus | 项目规划 | 用户要我设计整个项目结构,需要判断 |
| 2026-05-26 | meta | 决策 | — | 命名空间 | 采用 v2_ 前缀避免覆盖 v1 |
| 2026-05-26 | meta | 决策 | — | 引用 ID 分段 | V001-099 (P01), V100-199 (P02), V200-299 (P03), V300-399 (P04), V400-499 (P05), V500-599 (P06), V600-699 (P07);避免并行写冲突 |
| 2026-05-26 | meta | 决策 | — | citations 分文件写 | 每个 phase 写 citations_v2_phaseXX.json,最后合并到 citations_v2.json |
| 2026-05-26 | meta | 决策 | — | 每 phase 两步 | collector(sonnet)→ analyzer(opus),最大化省成本同时保证判断质量 |

## Wave 1 — Phase 01 / 02 / 07

### Wave 1A — Collectors (sonnet, parallel)
| Phase | Files | Citations | Notes |
|-------|-------|-----------|-------|
| 01 | 12 | V001-V035 | Substack 50% annual paid churn 关键发现;Beehiiv $3M→$30M ARR 24 个月;design newsletter 子数据稀疏 |
| 02 | 7 | V100-V127 | Polywork 创始人 Peter Johnston "the world needs a new standard" 引语;Bento.me 已被 Linktree 收购并杀死(2025);"front door vs living room"是真实人物的常态分离 |
| 07 | 18 | V600-V662 | EU AI Act Annex III §4 把招聘 AI 列为高风险;2026-08-02 生效;LinkedIn 实际上对第三方关闭;GDPR Art.22 + SCHUFA 案对"AI 生成职业洞察"有直接 implication |

### Wave 1B — Analyzers (opus, parallel) — DONE

| Phase | Output | 关键判断 |
|-------|--------|----------|
| 01 | `analysis/01_newsletter_ecosystem.md` (~5,200 字) | 1) Newsletter 已是事实上的"轻量职业身份产品"但只对头部 5K-20K 独立专业人士; 2) 不要内置 newsletter 输出能力(50% 年流失 + 中位 $4K 收入 = 持续运营业务,不是轻量贡献); 3) 渠道策略是 PR/case study 而非付费广告(Lenny:word of mouth 是唯一杠杆) |
| 02 | `analysis/02_pro_identity_landscape.md` (~13K 字) | 1) Western pros 的"living room vs front door 分离"是趋势; 2) 5 个死亡产品的共同结构性死因是"transactional hook 缺失"; 3) Frozen LinkedIn Middle (Director 级中层非创作者) 是未被服务的灰色市场; 4) 倾向私密能力镜子 + opt-in surface 路径(4/5 死的都是公开身份方向) |
| 07 | `analysis/07_technical_constraints.md` (~22K 字) | 1) B 端反哺必须从"platform AI ranking"转成"user-controlled push" — 同时解 EU AI Act §4(a) + GDPR Art.22 + CCPA "sale" + 23andMe 教训; 2) C 端干净 MVP 路径:GitHub + Substack RSS + Dribbble OAuth + 用户提供个人站 URL,LinkedIn 仅 Sign-in; 3) 数据架构需 user-keyed encryption + 破产销毁承诺 |

### Wave 1B 待解决
- Phase 02 报告中 raw_data 引用了 V128-V138,但 citations 文件只有 V100-V127。需要补登或确认这些是 placeholder。已记入 v2_questions.md
- v2_final_report.md 还在占位状态

### Wave 1 元决策
- 单 phase 两步(sonnet collector → opus analyzer)效果好:collector 一次到位的原始信息密度高,analyzer 不需要补漏。继续 Wave 2 用同模式。
- Phase 07 输出 22K 字远超目标 6-8K 字。判断:不删,因为约束清单本质上需要每条都翻译成产品决策语言;后续 Phase 08 综合时按需引用而非整段读。

## Wave 2 — Phase 03 / 04 / 05 / 06

### Wave 2A — Collectors (sonnet, parallel) — DONE
| Phase | Files | Citations | 备注 |
|-------|-------|-----------|------|
| 03 | 19 | V200-V273 (74) | collector 在收尾被 API 529 砍掉,citations 文件由独立 sonnet 恢复 agent 重建 |
| 04 | 34 | V300-V333 (34) | D30/D90 retention 全部不公开,改用 Lenny benchmark 参照 |
| 05 | 25 | V400-V420 (20) | Path $80M 收购价 + Polywork $1.45B 估值 未在 primary source 核实 |
| 06 | 44 | V500-V570 (71) | 价格锚 $20/月被 ChatGPT/Claude/Cursor 锁定;Cursor 36% 转化 outlier |

### Wave 2B — Analyzers (opus, parallel) — DONE
| Phase | Output | 关键判断 |
|-------|--------|----------|
| 03 | `analysis/03_target_users_daily_life.md` (~13K 字) | 1) Marketing 是冷启动 ICP 但要 target mid-level 不是 famous creator; 2) **Consulting 公开样本 100% 是离职后内容创作者**,真正 in-firm consultant 完全不可见 — 这是产品决策含义(consulting 不能用展示型触达); 3) 狭义 SAM ~50K-180K 撑不起 venture-scale,广义 SAM 1.5-3M 但要求产品突破"必须公开发声"假设 |
| 04 | `analysis/04_private_vs_public_products.md` (~13K 字) | **明确推荐**:Strava 模式骨架 + LinkedIn 模式引导话术(22 分最高);23andMe 教训 — 同意是 context-bound 不可转移;D30/D90 数据全部不公开是结构性 limitation |
| 05 | `analysis/05_cold_start_patterns.md` (~10-11K 字) | 1) 第一批 1K 用户从 Lenny/MKT1/Justin Welsh + Dive Club/Femke + Critchlow/Millerd 圈来 (5 个真名); 2) Semi-invite-only(B-side invite + 6 个月内 C-side 开放); 3) 12-18 月到 PM signal,$1.5-3M 资金; 4) 最可能死在 first→second 贡献之间的 retention gap; 5) **founder-fit gap 是结构性的**(reader 不是 native 欧美创作者圈),需用 KOL 借力补偿 |
| 06 | `analysis/06_user_willingness_evidence.md` (~13K 字) | 用户意愿模型一句话:5-8% 目标用户愿付 $20/月换 AI matching + visibility + career Wrapped,前提:opt-in / 持续反馈 / 透明 / bankruptcy 销毁条款。**5:1 latent-to-visible ratio**(OpenToWork)是最大产品杠杆;迁移策略已死 — 必须 additive layer 不是 replacement |

### Wave 2 元决策
- API 529 outage 导致 Phase 03 collector 中断,但 raw data 已落盘。恢复 agent 重建 citations 用了 ~28 个工具调用,成本可控。**lesson**:对长跑 collector,要求"先写 citations 再做最后的格式化"。
- 7 个 phase 分析报告全部落地。citation 总数 V001-V662 之间分布,但有跳号(不是 V001-V662 连续 662 个,实际约 350 条)。

## Wave 3 — Phase 08 综合(opus 全程)

(dispatching)


