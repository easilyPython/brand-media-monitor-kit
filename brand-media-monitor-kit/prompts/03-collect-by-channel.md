# Prompt 03: Collect by Channel

```text
请按 channel registry 对指定品牌执行分渠道抓取。

抓取范围限制：
- 只保留与品牌相关内容
- 只保留与 topic_limiter 直接相关内容
- 只保留在 date_range 内的内容

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
- 官方渠道与外部媒体分开记录
- 阅读量拿不到时写 NA，并说明原因
- 零命中渠道必须单独记录
- 不允许为了凑样本加入弱相关内容
- 公众号层优先通过 agent-reach 搜索
- 命中公众号链接后继续用 wechat-article-extractor 解析标题、账号名、发布时间
- 搜索引擎仅作为补面，不能替代公众号原文证据
```

