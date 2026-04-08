# Platform Setup

这个仓库不包含任何 API、密钥或账号信息。

## 必要环境

- 一个可以联网执行搜索和网页抓取的 AI 平台：
  - OpenClaw
  - Codex
  - Claude Code
- 本地浏览器

## 推荐配置

### 如果你使用 OpenClaw

建议配置：

- `web-access`
- `wechat-article-extractor`
- `brand-media-monitor`

### 如果你要抓公众号原文

建议：

- 在本机浏览器中保持微信文章可访问
- 优先使用真实浏览器登录态
- 不要依赖公开搜索作为唯一来源

### 如果你要做长期监测

建议：

- 固定一套行业媒体池
- 固定输出目录
- 让每次运行都产生配置文件、原始表和报告

## 安全原则

- 不在仓库中保存 AppID、AppSecret、Cookie、Token
- 所有账号和密钥通过本地环境变量或本地配置管理
