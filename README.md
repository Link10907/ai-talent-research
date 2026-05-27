# AI 时代职业身份产品 - 市场调研项目

## 项目目标
验证一个 C 端职业身份产品的市场可行性,产出可指导产品决策的综合战略报告。

## 项目结构
- `CONTEXT.md` — 项目背景(必读)
- `EXECUTION_PLAN.md` — 执行计划
- `prompts/` — 5 个 Phase 的执行 prompt
- `raw_data/` — 原始搜索结果和抓取内容
- `analysis/` — 每个 Phase 的分析报告
- `citations/citations.json` — 所有引用追溯
- `final_report.md` — 最终综合报告(执行完后生成)
- `questions.md` — 中途记录的待决策问题

## 如何启动调研
告诉 Claude:
"按照 EXECUTION_PLAN.md 执行完整调研,从 Wave 1 开始,自动推进到 Wave 3。
中途问题记到 questions.md,最终产出 final_report.md。"

## 质量原则
- 所有结论可追溯到原始引用
- 主动寻找反对证据
- 区分事实与推断
- 承认调研局限
