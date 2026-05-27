# Phase 2: 用户痛点验证(候选人视角)

## 目标
验证目标用户对现有职业身份产品(LinkedIn 为主)的真实不满,以及他们如何
尝试展示自己。重点关注:海外年轻 professional(25-35 岁)。

## 数据源
1. Reddit:r/LinkedInLunatics, r/recruitinghell, r/cscareerquestions, 
   r/jobs, r/digitalnomad, r/freelance
2. X/Twitter:对 LinkedIn 的吐槽 thread、个人网站/portfolio 优于 LinkedIn 的讨论
3. Indie Hackers / Build in Public 社区
4. Read.cv / Polywork / Contra 的用户反馈(Reddit、X、Product Hunt 评论)
5. 个人博客:"why I left LinkedIn", "alternatives to LinkedIn" 类文章

## 搜索策略
- "LinkedIn is broken / dead / useless / cringe"
- "alternative to LinkedIn"
- "personal website over LinkedIn"
- "show portfolio instead of resume"
- "how to showcase work outside LinkedIn"
- "linkedin algorithm complaint"
- "professional identity not linkedin"

## 输出要求

写入 analysis/phase2_report.md,结构:

```
# Phase 2 Report: 用户痛点验证

## 执行摘要
- 用户不满程度评分(0-10)
- 用户迁移意愿评分(0-10,从 LinkedIn 迁移到新产品的可能性)
- 最重要的 3 个发现

## 一、LinkedIn 被诟病的具体维度(按提及频率排序)
Top 10 痛点,每个带:
- 痛点描述
- 提及频率(相对)
- 典型用户原话引用
- 受影响最深的用户群

## 二、用户当前的替代方案
- 个人网站(占比、用法、不足)
- Bento / Linktree / Notion 主页
- X / Twitter profile 作为主要身份
- Substack / 博客
- GitHub(技术人)
- 其他

## 三、目标用户群体特征(用真实样本归纳)
- 他们是谁(行业、年龄、职业阶段)
- 他们在哪里聚集
- 他们的核心诉求
- 他们愿意付出什么(时间/数据/钱)

## 四、关键用户原声摘录
(挑 15-20 条最有代表性的原始引用)

## 五、调研局限性
```

## 数据存储
关键页面 → raw_data/phase2/,搜索 → raw_data/phase2/searches.md,
引用 → citations.json
