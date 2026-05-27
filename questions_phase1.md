# Phase 1 — Open Questions for Human Review

接力 agent 在 Phase 1 完成时仍存在的待确认问题。这些问题不影响 Phase 1 报告交付,但应在 Phase 2/3/5 时回头校准。

## 数据冲突

1. **Wall Street junior 招聘**: Fortune (2025-06) 说大行考虑砍 junior 招聘 2/3 [P1-007];Fortune (2025-12) 说 Goldman 实际加了 1,800 人、JPM 加了 2,000、整体 headcount 稳中略升 [P1-008]。**6 个月时差是否解释这个矛盾?还是前者是 narrative、后者是事实?** 倾向后者,但需要 Phase 3 金融行业调研单独验证。

2. **候选人 AI 能力造假率**: Greenhouse (2025-07) 说 32% [P1-010];GCheck (2026-05) 说 63% [P1-019]。这个翻倍是真实加速?还是 GCheck (背调商) 有利益偏向夸大?需要 Phase 5 看是否有第三方独立交叉来源。

3. **PwC 56% wage premium**: 一年从 25% 跳到 56% 显著太大 [P1-003]。是 composition effect (AI 岗 skew senior 拉高均值)?还是采样方法变化?PwC 报告本身没充分披露。

## 信息缺口

4. **欧洲大陆 / 亚洲数据**: 全部数据是 US/UK 视角。海外市场以欧美为主 (按 CONTEXT.md),但欧洲大陆 (德国/法国/北欧) 的招聘趋势没单独取证。

5. **JD 文本样本**: 没有直接抓取 LinkedIn/Indeed 上"requires AI proficiency" 类岗位的样本——靠的是 Lightcast/PwC 的二手聚合。如有 API/抓取能力,直接拉 200 个 JD 做文本分析会显著加强证据。

6. **小企业 vs 大企业**: HR Dive 提到大公司 65% 中型 45% 的 AI 要求差异 [P1-036],但小企业 (<200 人) 完全没数据。我们的目标用户群更可能在小公司工作。

7. **"AI 能力如何具体被评估" 实操**: 找不到一个广泛部署的、结构化的 AI 能力测评方法。雇主用什么标准筛?面试用什么任务?待 Phase 4 (竞品分析) 或专门搜索补充。

## 判断的不确定性

8. **趋势 1 评分 4/10 vs 5/10**: 关键依赖未来 6-18 月的加速度判断。如果"junior pipeline 压缩"在律所/投行真的兑现,4/10 可能保守;如果不兑现,4/10 偏高。

9. **"portfolio over resume" 在非创意/非技术岗位是否真的能成立**: 律师 portfolio 长什么样?会计师 portfolio 长什么样?医生 portfolio 长什么样?概念上有,实操中没看到任何例子。Phase 3 行业调研里需要逐行业问。

10. **AI-generated portfolio 造假的解决方案**: Greenhouse 已经发现 28% 候选人用 AI 生成假作品集 [P1-029]。如果作品集本身可造假,所谓"portfolio over resume"的产品命题需要新的信任层 (provenance, AI-usage logging, real-time co-creation 记录)。这是产品级问题,Phase 1 只能 flag。
