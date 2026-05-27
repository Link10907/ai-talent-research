# V2 调研项目总览

> v1 调研已完成,v1 文件保留在原位(prompts/phase*.md、analysis/phase*.md、citations.json、final_report.md 等)。
> v2 使用 `v2_` 前缀的顶层文件 + 新前缀的 phase 文件(`01_*` ~ `08_*`)与 v1 共存,不覆盖任何 v1 产出。

## 项目目的
为一个面向海外的 B 端 AI 招聘产品扩展一个 C 端产品。C 端目标:让用户自愿、持续、高质量地贡献职业信息,反哺 B 端数据库,但不能让用户感觉被利用,且不能与 LinkedIn / BOSS 同质化。

v1 已扫描宏观市场。v2 是**对市场认知和真实信息的补充**,目的是让项目负责人(对海外 newsletter 生态、职业产品生态完全不了解)读完后能做产品方向决策。

## 八个 Phase

| Phase | 主题 | 模型策略 |
|-------|------|----------|
| 01 | Newsletter 生态全景 | 搜集 sonnet → 分析 opus |
| 02 | 海外职业身份/展示产品真实景观 | 搜集 sonnet → 分析 opus |
| 03 | 三个目标人群的真实日常画像 | 搜集 sonnet → 分析 opus |
| 04 | "默认私密" vs "默认展示" 模式对比 | 搜集 sonnet → 分析 opus(立场重) |
| 05 | 类似产品的冷启动真实路径 | 搜集 sonnet → 分析 opus |
| 06 | 目标用户真实意愿的证据基础 | 搜集 sonnet → 分析 opus |
| 07 | 技术、合规、商业的真实约束 | 搜集 sonnet → 分析 opus |
| 08 | 综合(给项目负责人的决策输入) | 全程 opus |

## Auto Mode 模型选择原则
- 需要判断 / 归纳 / 立场 / 决策依据 → **opus**
- 需要忠实记录 / 搜索 / 抓取 / 整理 / 中间产物 → **sonnet**
- 不确定 → **sonnet**(便宜)
- 不使用 haiku
- 总成本目标:$30-60。超支记入 progress,不停。

## Wave 调度
- **Wave 1**(并行):Phase 01 + 02 + 07
- **Wave 2**(并行):Phase 03 + 04 + 05 + 06
- **Wave 3**:Phase 08

## 关键产出
- **v2_final_report.md** — 决策输入(我最关心这份)
- **analysis/01_*.md ~ 07_*.md** — 七份支撑性 Phase 报告
- **raw_data/phase_0X/** — 原始资料
- **citations/citations_v2.json** — 引用库,ID 全局唯一(从 V001 递增)
- **v2_progress.md** — 执行 + 模型决策日志
- **v2_questions.md** — 遗留问题

## 质量底线
1. 每个结论后引用 ID(`[V001]`),引用追加到 citations_v2.json
2. 不堆砌 — 每份 analysis 必须有判断和立场
3. 反偏误 — 每个结论主动找反对证据
4. 区分事实与推断
5. 样本警觉 — HN/Reddit/X 上声音不代表沉默多数
6. 每份报告末尾"调研局限性"章节
7. 不复述 v1 — 假设 v1 已读
8. 具体例子优先,真实数字优先
9. Phase 08 明确推荐路径,不骑墙
