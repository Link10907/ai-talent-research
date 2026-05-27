# V2 执行计划

## 命名空间
v1 已占用根目录的 README.md / EXECUTION_PLAN.md / questions.md / final_report.md / citations/citations.json。
v2 采用并存命名:

| v2 文件 | 路径 |
|--------|------|
| 总览 | `v2_README.md` |
| 执行计划 | `v2_EXECUTION_PLAN.md`(本文件) |
| 执行 + 模型决策日志 | `v2_progress.md` |
| 遗留问题 | `v2_questions.md` |
| 引用 | `citations/citations_v2.json` |
| 最终报告 | `v2_final_report.md` |
| 各 Phase prompt | `prompts/01_*.md` ~ `prompts/08_*.md` |
| 各 Phase 分析 | `analysis/01_*.md` ~ `analysis/07_*.md` |
| 各 Phase 原始资料 | `raw_data/phase_01/` ~ `raw_data/phase_07/` |

## 三波并行调度

### Wave 1(并行)
- Phase 01 newsletter 生态全景
- Phase 02 职业身份/展示产品真实景观
- Phase 07 技术、合规、商业约束

为什么:这三个 Phase 互相之间没有依赖,且 02 + 07 的事实基础对 Wave 2 的 Phase 03/04/05/06 有用。

### Wave 2(并行)
- Phase 03 三个目标人群日常画像
- Phase 04 私密 vs 展示模式对比
- Phase 05 类似产品冷启动路径
- Phase 06 用户真实意愿证据

可以在 Wave 1 完成后开,但每个 Phase 仍是独立 sub-agent。

### Wave 3
- Phase 08 综合(opus 全程)
读 analysis/01-07 + citations_v2.json,产出 v2_final_report.md。

## 每个 Phase 的内部流水线
1. **搜集 sub-agent**(默认 sonnet)
   - 跑 web_search、web_fetch,把关键页面存为 `raw_data/phase_0X/YYYYMMDD_<source>_<topic>.md`
   - 每个文件开头 200 字 TL;DR
   - 搜索日志 → `raw_data/phase_0X/searches.md`
   - 将引用追加进 `citations/citations_v2.json`(ID 从 V001 全局递增)
2. **分析 sub-agent**(默认 opus)
   - 读 raw_data/phase_0X/ 的 TL;DR 与关键摘录
   - 产出 `analysis/0X_<topic>.md`
   - 必含结尾两节:"对我们产品的启示" + "调研局限性"

## 质量审计
执行完后,在 v2_progress.md 中:
- 总成本估算(基于每次 sub-agent 调用的模型 × 工作量)
- 哪些 Phase 数据不足
- 哪些结论证据等级低

## 不做什么
- 不复述 v1 已有结论(假设 v1 已读)
- 不堆砌罗列,要有立场
- 不为了"看起来全面"而把弱证据包装成强结论
