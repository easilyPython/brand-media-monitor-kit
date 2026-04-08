# Prompts

## Prompt 1：定义监测任务

```text
你现在要执行一个通用品牌舆情监测任务。

请先不要抓取任何内容，而是把任务标准化成一份 monitoring spec。

必须包含：
- 品牌
- 品牌关键词
- 时间范围
- 主题限制
- 官方渠道
- 外部渠道
- 输出要求

规则：
- 不要自动扩大时间范围
- 不要自动扩大主题
- 如果用户给的窗口很窄，也保持这个窗口不变
- 如果某些渠道后续可能零命中，也不要修改任务定义
```

## Prompt 2：建立渠道注册表

```text
请根据 monitoring spec 建立一份 channel registry。

对每个渠道输出：
- channel_name
- channel_group
- platform
- collection_method
- reading_count_available
- evidence_priority
- notes
```

## Prompt 3：分渠道抓取

```text
请按 channel registry 对指定品牌执行舆情监测抓取。

抓取范围限制：
- 只保留与品牌相关的内容
- 只保留与主题限制直接相关的内容
- 只保留在指定时间范围内的内容

抓取字段：
- publish_date
- title
- link
- platform
- media_name
- channel_type
- reading_count
- reading_count_note
- content_type
- sentiment
- keyword_hit
- notes

规则：
- 官方渠道和外部媒体分开记录
- 阅读量拿不到时写 NA，并解释原因
- 零命中渠道必须单独记录
- 不允许为了凑样本加入弱相关内容
- 公众号层必须优先通过 agent-reach 搜索
- 命中的公众号链接必须继续解析出标题、账号名、发布时间
- 百度只作为补面渠道，不能替代公众号原文证据
```

## Prompt 4：分析报告

```text
请根据原始数据表输出品牌舆情分析报告。

必须回答：
1. 在指定时间里，这个品牌真正发布了什么
2. 哪些是官方主线，哪些被外部媒体放大
3. 有没有明确负面，或者潜在风险
4. 如果没有负面，内容结构是否仍然存在弱点
5. 哪些媒体值得继续合作
6. 下一阶段品牌内容应该补什么
```
