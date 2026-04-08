# Platform Setup

本仓库不包含任何 API、密钥或账号信息。

## Minimum Requirements

- 可联网执行的 AI 平台（OpenClaw / Codex / Claude Code）
- 本地浏览器
- 公众号访问能力（用于原文层证据）

## Recommended Setup

### OpenClaw

建议启用：

- `brand-media-monitor`
- `agent-reach`
- `wechat-article-extractor`
- `web-access`

### Codex / Claude Code

建议用途：

- 执行固定 prompt
- 产出原始表与报告
- 批量更新样例与模板

## WeChat Collection Notes

- 公众号层优先使用 `agent-reach` 发现链接
- 链接命中后再用 `wechat-article-extractor` 解析
- 公开搜索只能补面，不能替代公众号主证据

## Security Rules

- 不提交任何 AppID、AppSecret、Token、Cookie
- 所有凭据通过本地环境变量或本地配置注入
