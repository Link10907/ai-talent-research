# 执行计划

## 总体策略
最大化并行,最小化等待。Phase 1 / 2 / 4 之间无依赖,可全并行。
Phase 3 内部 10 个行业可全并行。Phase 5 依赖前四个 Phase 完成。

## 阶段总览

| Phase | 内容 | 并行性 | 预估耗时 |
|-------|------|--------|---------|
| Phase 1 | 范式转移验证(招聘端) | 与 2/4 并行 | 1-2 小时 |
| Phase 2 | 用户痛点验证(候选人端) | 与 1/4 并行 | 1-2 小时 |
| Phase 4 | 竞品和邻近产品分析 | 与 1/2 并行 | 1-2 小时 |
| Phase 3 | 跨行业 AI 渗透调研 | 10 个行业并行 | 2-3 小时 |
| Phase 5 | 综合分析与战略建议 | 串行 | 30-60 分钟 |

## 执行顺序

### Wave 1:Phase 1 + Phase 2 + Phase 4 并行
启动 3 个 sub-agent,分别执行 prompts/phase1_paradigm_shift.md、
prompts/phase2_user_pain.md、prompts/phase4_competitors.md。
三个全部完成后进入 Wave 2。

### Wave 2:Phase 3 行业并行调研
启动 10 个 sub-agent,每个负责一个行业(法律/营销/设计/销售/运营/教育/医疗/
金融/咨询/HR),使用 prompts/phase3_industry_ai.md 作为统一模板。
所有行业完成后,主 agent 汇总成 analysis/phase3_overview.md。

### Wave 3:Phase 5 综合分析
读取所有 analysis/*.md 和 citations.json,按 prompts/phase5_synthesis.md
生成 final_report.md。

## 质量要求(所有 Phase 必须遵守)

1. **可追溯**:每个结论必须有引用支撑,引用 ID 在 citations.json 里
2. **反偏误**:主动寻找反对证据,不做单向论证
3. **区分推断与事实**:明确标注"证据显示"vs"我推断"
4. **样本警觉**:HN/Reddit/X 上的声音不代表沉默的多数,要主动校准
5. **承认局限**:每份报告末尾必须有"调研局限性"章节
6. **不堆砌**:有判断、有取舍,不做信息搬运工

## 数据管理规范

### raw_data/ 目录
- 每个 web_fetch 抓取的关键页面,存成 .md 文件,命名格式:
  `YYYYMMDD_<source>_<topic>.md`
- 每个搜索查询的结果列表存成 `searches.md`,追加写入
- 大体量内容可以摘录关键段落,不必全文存

### citations.json 格式
```json
{
  "C001": {
    "url": "完整 URL",
    "title": "页面/帖子标题",
    "source_type": "hackernews_comment / reddit_post / x_thread / article / report",
    "date": "YYYY-MM-DD 或 unknown",
    "author": "如可知",
    "excerpt": "200-500 字关键摘录,保留原文",
    "used_in": ["phase1_report.md#section-2"],
    "relevance": "一句话说明这个引用支持什么结论",
    "credibility": "high / medium / low + 简短理由"
  }
}
```

引用 ID 全局唯一,从 C001 递增。

### 报告中的引用方式
每个结论后追加 `[C001]` 或 `[C001, C003, C007]`。

## 中途遇到问题的处理

不要中断执行。把问题记到 questions.md,继续往下做。最终在 final_report.md
里附上"待人工确认的问题清单"。
