# Git 仓库文件分布整理与建议

**日期**: 2026-05-27  
**用途**: 给 `Link10907/ai-talent-research` 做文件导航，避免 V1、V2、raw data、阶段报告和汇报材料混在一起。

---

## 1. 当前文件类型分布

### 1.1 项目背景与执行计划

| 文件 | 作用 | 建议状态 |
|---|---|---|
| `CONTEXT.md` | 项目一阶背景：B 端 AI 招聘产品，C 端产品用于持续获取高质量职业信息，反哺 B 端数据库 | 保留为总入口 |
| `README.md` | V1 项目说明 | 可归入 V1 |
| `EXECUTION_PLAN.md` | V1 执行计划 | 可归入 V1 |
| `v2_README.md` | V2 项目说明 | 保留 |
| `v2_EXECUTION_PLAN.md` | V2 执行计划 | 保留 |
| `v2_progress.md` | V2 进展记录 | 保留 |
| `v2_questions.md` | V2 待确认问题 | 保留 |

### 1.2 V1 调研与问题文件

| 文件 | 作用 | 建议状态 |
|---|---|---|
| `final_report.md` | V1 综合报告 | 归档为 V1 最终报告 |
| `questions.md` | 汇总问题 | 可归入 V1 / cross-phase |
| `questions_phase1.md` | Phase 1 问题 | 归档 |
| `questions_phase2.md` | Phase 2 问题 | 归档 |
| `questions_phase3_*.md` | Phase 3 各行业问题：sales / healthcare / consulting / finance / operations / HR 等 | 归档 |

### 1.3 V2 战略与方向修正文件

| 文件 | 作用 | 当前判断 |
|---|---|---|
| `product_thesis_v2.md` | V2 初始 thesis：能力镜子、阶段路径、信任模型 | 重要基础 |
| `v2_final_report.md` | V2 第一版综合报告 | 已有价值，但叙事偏“职业能力镜子” |
| `v2_report_review_and_direction.md` | 对 V2 报告做业务目标审计 | 保留 |
| `v2_ecosystem_c_product_direction.md` | 明确“真实 To C 产品 + B 端数据生态目的” | 保留 |
| `v2_raw_data_comprehensive_audit.md` | 回到 raw_data 后的总审计 | 保留 |
| `v2_real_needs_competitor_research_brief.md` | 第一轮真实需求 / 竞品调研 brief | 保留 |
| `v2_full_research_execution_plan.md` | 后续全面调研执行计划 | 保留 |
| `v2_competitor_matrix.md` | 竞品矩阵：AI resume / ATS / career network / skills intelligence | 保留 |
| `v2_real_user_needs_research.md` | 真实用户需求与伪需求判断 | 保留，但需按新叙事继续修正 |
| `v2_narrative_repositioning_ai_age.md` | 最新叙事：AI 时代职业雷达、技能树、行动证明、全球可见性 | 当前应作为新主线 |

### 1.4 二级分析文件

| 目录 / 文件 | 作用 | 建议状态 |
|---|---|---|
| `analysis/01_newsletter_ecosystem.md` | Newsletter 生态分析 | 保留 |
| `analysis/02_pro_identity_landscape.md` | 职业身份产品格局 | 保留 |
| `analysis/03_target_users_daily_life.md` | 目标用户日常与行业画像 | 保留 |
| `analysis/04_private_vs_public_products.md` | 私密产品 vs 公开产品分析 | 保留 |
| `analysis/05_cold_start_patterns.md` | 冷启动模式 | 保留 |
| `analysis/06_user_willingness_evidence.md` | 用户意愿和付费 / 分享证据 | 保留 |
| `analysis/07_technical_constraints.md` | 技术、合规、API 约束 | 保留 |

### 1.5 原始数据文件

| 目录 / 文件 | 作用 | 建议状态 |
|---|---|---|
| `raw_data/phase_01/searches.md` | Newsletter / 内容渠道原始搜索日志 | 保留 |
| `raw_data/phase_02/searches.md` | 职业身份产品原始搜索日志 | 保留 |
| `raw_data/phase_02/people_sample.md` | 42 个真实职业身份样本 | 重要 |
| `raw_data/phase_03/searches.md` | Marketing / Design / Consulting 目标用户搜索 | 保留 |
| `raw_data/phase_04/searches.md` | 私密 vs 公开产品搜索 | 保留 |
| `raw_data/phase_04/comparison_data.md` | 私密 / 公开 / B 端适配对比表 | 重要 |
| `raw_data/phase_04/b_side_feedback_fit.md` | 23andMe vs LinkedIn B 端反哺案例 | 重要 |
| `raw_data/phase_05/searches.md` | 冷启动案例搜索 | 保留 |
| `raw_data/phase_06/searches.md` | 用户意愿、付费、迁移、隐性机会需求搜索 | 保留 |
| `raw_data/phase_07/searches.md` | API / 合规 / 数据源 / B 端约束搜索 | 保留 |

### 1.6 汇报材料

| 文件 | 作用 | 建议状态 |
|---|---|---|
| `metix_ai_career_ecosystem_presentation.html` | 本次生成的 HTML 展示文档：产品构想、市场证据、Metix.ai B 端优势、产品形态 | 建议作为当前汇报主文件 |

---

## 2. 建议的后续目录结构

目前根目录文件过多，建议后续整理为下面结构。暂时不建议马上移动文件，先用本文件做索引；等报告稳定后再批量移动，避免引用路径混乱。

```text
ai-talent-research/
├── 00_context/
│   ├── CONTEXT.md
│   └── recruiter-business-capabilities.md
│
├── 01_v1_archive/
│   ├── README.md
│   ├── EXECUTION_PLAN.md
│   ├── final_report.md
│   ├── questions.md
│   ├── questions_phase1.md
│   ├── questions_phase2.md
│   └── questions_phase3_*.md
│
├── 02_v2_research/
│   ├── raw_data/
│   └── analysis/
│
├── 03_v2_strategy/
│   ├── product_thesis_v2.md
│   ├── v2_final_report.md
│   ├── v2_report_review_and_direction.md
│   ├── v2_ecosystem_c_product_direction.md
│   ├── v2_raw_data_comprehensive_audit.md
│   ├── v2_real_needs_competitor_research_brief.md
│   ├── v2_competitor_matrix.md
│   ├── v2_real_user_needs_research.md
│   └── v2_narrative_repositioning_ai_age.md
│
├── 04_execution/
│   ├── v2_EXECUTION_PLAN.md
│   ├── v2_progress.md
│   ├── v2_questions.md
│   └── v2_full_research_execution_plan.md
│
├── 05_presentation/
│   └── metix_ai_career_ecosystem_presentation.html
│
└── REPO_FILE_MAP.md
```

---

## 3. 当前主线建议

现在不应继续把产品讲成“简历优化”或“职业能力镜子”。

推荐当前主线：

> **AI 时代职业探索与机会网络：从一手信息到技能路径，从行动证明到全球可见性。**

文件优先级建议：

1. `v2_narrative_repositioning_ai_age.md`
2. `v2_raw_data_comprehensive_audit.md`
3. `v2_competitor_matrix.md`
4. `v2_real_user_needs_research.md`
5. `metix_ai_career_ecosystem_presentation.html`

---

## 4. 后续整理建议

1. 不要删除旧文件，全部保留为研究轨迹。
2. 后续新增文件尽量放到规划目录，不再堆到根目录。
3. 如果要重构目录，先开分支，不要直接 main 移动。
4. 汇报材料优先维护 HTML，不再继续在多个 markdown 中反复改同一套叙事。
