# Brand Media Monitor Kit

一个面向品牌团队的通用舆情监测工作流包。

它不是“帮某个品牌搜一下”的脚本，而是一套可以重复使用的执行框架。

## 这套工具解决什么问题

品牌监测最常见的问题不是不会搜索，而是：

- 每次监测范围都不同
- 官方内容、媒体转载、搜索结果混在一起
- 只有链接和截图，没有结构化输出
- 做完后无法指导媒体合作和下一阶段内容

这套工具把过程固定为：

1. 定义监测任务
2. 建立渠道注册表
3. 分渠道抓取
4. 归一化原始数据表
5. 输出分析报告
6. 提炼品牌动作建议

## 输入

每次运行至少提供：

- brand
- brand_keywords
- date_range
- topic_limiter
- channels

## 输出

- `raw_table.csv`
- `analysis_report.md`

## 推荐平台分工

### OpenClaw

适合：

- 长期监测
- 保存运行文件
- 自动化任务

### Codex

适合：

- 搭工作流
- 管理模板
- 生成结构化报告

### Claude Code

适合：

- 在 prompt 已经固定时执行单次任务

## 需要的 Skill

- `brand-media-monitor`
- `web-access`
- `wechat-article-extractor`

如果后续要把监测结果写成文章，可继续串联：

- `c-account-manager`
- `dan-koe-coach-v2`

## 目录

- `docs/workflow.md`
- `docs/prompts.md`
- `docs/platform-setup.md`
- `docs/skill-routing.md`
- `templates/monitoring-config.yaml`
- `templates/channel-registry-template.md`
- `examples/mindray-2026Q1-coagulation/`
- `examples/jq-2026Q1-coagulation/`

## 使用方式

1. 复制 `templates/monitoring-config.yaml`
2. 填写品牌、时间范围、主题和渠道
3. 按 `docs/workflow.md` 的 6 步执行
4. 在 `docs/prompts.md` 中直接复制对应 prompt
5. 输出原始表和分析报告

## 重要原则

- 低命中是有效结果
- 零命中必须记录
- 不能为了让报告更满而扩大范围
- “无明显负面”不能作为最终结论
