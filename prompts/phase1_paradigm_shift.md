# Phase 1: 范式转移验证(招聘端视角)

## 目标
验证两个趋势在海外是否真实发生,以及发生到什么程度、在哪些领域最明显:
1. 招聘从"看经历"转向"看作品/能力"
2. "AI 能力"成为显性招聘要求

## 数据源(按优先级)
1. Hacker News:搜索 "hiring", "resume", "portfolio", "AI hiring", 
   "github over resume" 等,聚焦最近 18 个月
2. Reddit 子版:r/recruiting, r/cscareerquestions, r/ExperiencedDevs, 
   r/marketing, r/sales, r/AskHR
3. X/Twitter:招聘方、HR thought leaders 的相关 thread
4. 行业报告:LinkedIn Talent Insights, Indeed Hiring Lab, Lightcast, 
   Handshake 的年度报告
5. 风投/咨询观点:a16z, Sequoia, McKinsey, BCG 关于 AI 改变工作的报告

## 搜索策略
分批次发起搜索,每批 5-10 个查询。建议查询包括但不限于:
- "AI changed hiring 2024 2025"
- "portfolio over resume hiring"
- "github profile hiring decision"
- "AI skills required job posting"
- "linkedin resume obsolete"
- "show your work hiring"
- "skills based hiring AI"
- "non-traditional candidates AI"

每个搜索后,挑选 top 5-10 个最有信息量的链接 web_fetch 详读。

## 输出要求

写入 analysis/phase1_report.md,结构:

```
# Phase 1 Report: 范式转移验证

## 执行摘要(200 字内)
- 趋势 1 强度评分(0-10)+ 一句话依据
- 趋势 2 强度评分(0-10)+ 一句话依据
- 最重要的 3 个发现

## 一、"作品/能力主导取代经历主导"的证据
### 支持证据(分类整理,每个结论带引用)
### 反对/质疑声音(必须有)
### 在哪些行业/岗位最明显

## 二、"AI 能力作为招聘要素"的证据
### 哪些行业开始把 AI 能力写进 JD
### 招聘方如何评估候选人的 AI 能力(具体方法)
### 反对声音

## 三、关键招聘方观点摘录
(挑 10-15 条最有信息量的原始引用,完整保留语境)

## 四、调研局限性
- 样本偏差说明
- 没覆盖到的领域
- 不确定的判断
```

## 数据存储
- 关键页面抓取存到 raw_data/phase1/
- 搜索日志存到 raw_data/phase1/searches.md
- 引用追加到 citations/citations.json
