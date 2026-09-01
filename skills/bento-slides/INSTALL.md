# Bento Slides 安装说明

本 skill 为完整工程（含编辑器、图表引擎、协作服务器），不从本仓库复制文件，直接从原仓库安装。

原仓库：https://github.com/nyblnet/bento

## Claude Code（推荐）

在 Claude Code 中执行：

```
/plugin marketplace add nyblnet/bento
```

安装后 skill 会自动处理 Bento 应用的下载。对 agent 说需求即可，例如：

```
根据项目笔记做一份技术演示文稿，包含部署指标的图表
```

## 不用 skill 的替代方式

Bento 文档本身就是纯 JSON，任何能读写文件的 AI 助手都能直接操作，无需安装 skill：

- Claude Code / Cursor / Aider：直接让 agent 读写 `.bento.html` 文件顶部的 `<bento-doc>` JSON 块
- 任何聊天式 LLM：在 Bento 编辑器中 Save → Copy document JSON，粘贴给 LLM 改完再粘回
- 本地模型（Ollama / llama.cpp / LM Studio）：完全离线，数据不出机器

agent 指南（可丢进任何模型上下文）：https://bento.page/agents.md

## 单独获取 Bento 应用

不用 skill 也可以直接下载 Bento 应用本体：

- 在线试用（无需下载）：https://bento.page/slides
- 下载单文件应用（约 560KB）：https://bento.page/releases/slides/Bento_Slides.bento.html
- 或从 GitHub Releases 获取：https://github.com/nyblnet/bento/releases

下载后用浏览器打开就是完整编辑器，保存时文件重写自身。

## 安装后验证

在 Claude Code 中输入：

```
/bento-slides 做一份关于 XX 的三页演示
```

如果 agent 自动下载 Bento 应用并生成 `.bento.html` 文件，说明安装成功。用浏览器打开生成的文件即可查看和继续手动编辑。
