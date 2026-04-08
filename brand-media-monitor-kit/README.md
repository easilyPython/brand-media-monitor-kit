# Brand Media Monitor Kit

面向品牌、市场、竞品分析团队的通用品牌内容监测系统。

这不是“帮你搜几条链接”的脚本，而是可复用的完整工作流：

1. 定义监测任务
2. 建立渠道注册表
3. 分渠道抓取
4. 归一化原始数据表
5. 输出结构化分析报告
6. 转化为品牌动作建议

## 这套系统解决什么问题

品牌监测常见痛点：

- 每次监测范围不同，季度之间无法比较
- 官方内容和媒体内容混在一起，判断容易偏
- 交付只有链接和截图，无法指导下一步动作
- 最终结论停在“无明显负面”，没有策略价值

这套系统的目标是：

从“信息搜集”升级为“品牌内容判断”。

## 快速开始

1. 复制 [templates/monitoring-config.yaml](templates/monitoring-config.yaml)
2. 填写品牌、时间范围、主题限制、渠道列表
3. 按 [docs/workflow.md](docs/workflow.md) 执行 6 步
4. 在 [prompts/](prompts/) 里按步骤复制提示词
5. 交付 `raw-table.csv` 与 `analysis-report.md`

## 仓库结构

- `docs/`
- `prompts/`
- `skills/brand-media-monitor/`
- `templates/`
- `examples/mindray-2026Q1-fullbrand/`
- `examples/jq-2026Q1-reference/`

## 推荐技能路由

- 核心编排：`brand-media-monitor`
- 公众号检索：`agent-reach`
- 公众号解析：`wechat-article-extractor`
- 官网与网页补抓：`web-access`

详细见 [docs/skill-routing.md](docs/skill-routing.md)。

## 当前主样例

- 主样例：`mindray-2026Q1-fullbrand`
- 对照样例：`jq-2026Q1-reference`

## 安全与边界

- 本仓库不包含任何 AppID、AppSecret、Token、Cookie
- 账号和密钥请走本地环境配置
- 低命中与零命中是有效结果，不应人为扩窗凑样本
