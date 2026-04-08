# Skill Routing

这套工作流不是单一 skill 完成的，而是多个 skill 串联。

## Core Routing

### 1. `brand-media-monitor`

作用：

- 统一任务定义
- 固定执行顺序
- 固定输出格式
- 固定分析口径

### 2. `agent-reach`

作用：

- 搜索公众号文章
- 作为公众号层的第一入口
- 回收更接近行业真实传播面的微信文章链接

### 3. `web-access`

作用：

- 搜索品牌相关公开信息
- 抓取官网、媒体站点、搜索结果页
- 在需要真实浏览器登录态时补抓内容

### 4. `wechat-article-extractor`

作用：

- 解析公众号文章链接
- 提取标题、正文、链接、封面等信息
- 补公众号原文层证据

## Optional Writing Routing

如果要把监测结果继续写成公众号文章，可再串联：

### 5. `c-account-manager`

作用：

- 把系统执行结果转成 C 账号可写素材

### 6. `dan-koe-coach-v2`

作用：

- 帮助把实操型结果写成更有观点、更有结构的长文

## Recommended Sequence

1. `brand-media-monitor`
2. `agent-reach`
3. `wechat-article-extractor`
4. `web-access`
5. raw table
6. analysis report
7. optional writing layer
