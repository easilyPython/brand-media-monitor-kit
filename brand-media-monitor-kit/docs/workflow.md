# Workflow

## Step 1: Define Monitoring Spec

先固定任务定义，不要直接抓取。

必填：

- `brand`
- `brand_keywords`
- `date_range`
- `topic_limiter`
- `official_channels`
- `external_channels`
- `outputs`

建议使用 `prompts/01-define-monitoring-spec.md`。

## Step 2: Build Channel Registry

把松散渠道清单变成可执行注册表。

每个渠道至少记录：

- `channel_name`
- `channel_group`
- `platform`
- `collection_method`
- `reading_count_available`
- `evidence_priority`
- `notes`

模板见 `templates/channel-registry-template.md`。

## Step 3: Collect by Channel

推荐顺序：

1. 官方官网/官方新闻
2. 官方公众号
3. 行业媒体公众号池
4. 站点资讯页
5. 搜索补面

执行规则：

- 严格受 `date_range` 与 `topic_limiter` 约束
- 官方与外部媒体分开记录
- 零命中渠道也要记录
- 公众号优先走 `agent-reach`，命中后用 `wechat-article-extractor` 解析
- 百度或网页搜索只能补面，不能替代公众号主证据

## Step 4: Normalize Raw Table

固定字段：

- `publish_date`
- `title`
- `link`
- `platform`
- `media_name`
- `channel_type`
- `reading_count`
- `reading_count_note`
- `content_type`
- `sentiment`
- `keyword_hit`
- `notes`

缺失值请保留 `NA`，禁止补造数据。

## Step 5: Write Analysis Report

报告必须回答：

- 监测期内品牌实际讲了什么
- 官方叙事与媒体放大如何协同
- 主题结构、节奏、风险与空位
- 哪些媒体可继续合作
- 下一阶段内容该补什么

建议使用 `prompts/05-generate-analysis-report.md`。

## Step 6: Convert to Action Plan

最终交付不止“监测结果”，还应包含：

- 媒体合作建议
- 下一阶段内容建议
- 后续监测重点
- 监测边界说明
