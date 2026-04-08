# Workflow

## Step 1：定义监测任务

先把需求固定成 monitoring spec。

必须明确：

- brand
- brand_keywords
- date_range
- topic_limiter
- official_channels
- external_channels

## Step 2：建立渠道注册表

对每个渠道记录：

- channel_name
- channel_group
- platform
- collection_method
- reading_count_available
- evidence_priority

## Step 3：分渠道抓取

推荐顺序：

1. 官网 / 官方新闻
2. 官方公众号
3. 行业媒体公众号池
4. 站点资讯页
5. 百度补面

公众号层要求：

- 优先通过 `agent-reach` 搜索
- 命中链接后继续用 `wechat-article-extractor` 解析
- 百度不能替代公众号原文层

## Step 4：归一化原始数据表

固定字段：

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

## Step 5：输出分析报告

至少覆盖：

- 官方输出主线
- 外部媒体放大关系
- 情绪与风险
- 合作媒体建议
- 下一阶段内容建议

## Step 6：转化为品牌动作

输出：

- 媒体合作建议
- 下一阶段内容建议
- 监测盲区提示
