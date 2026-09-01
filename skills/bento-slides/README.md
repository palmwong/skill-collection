# Bento Slides

## 基本信息

- 来源地址：https://github.com/nyblnet/bento
- 作者/组织：nyblnet
- 收集日期：2026-08-19
- 协议：以原仓库 LICENSE 为准

## 功能简介

Bento 是一个"文件即软件"的单文件 HTML 演示工具（约 560KB），一个 `.bento.html` 文件同时装下演示文稿、编辑器、查看器、演示器。`bento-slides` 是其配套的 Claude Code skill，让 AI 直接理解和修改结构化 JSON 文档来生成/编辑演示文稿，而不是模拟鼠标操作传统 PPT。核心理念：AI 时代的 PPT 不再属于某个软件，而是一个开放、可编程、浏览器直接运行的文件。

## 使用场景

- AI 生成完整演示文稿（含 Morph 过渡、图表、演讲备注），生成后仍可手动编辑
- 航班上等无网环境做演示文稿（本地模型 Ollama / LM Studio 完全离线可用）
- 需要长期保存的演示文档（2026 年的文件 2036 年照样打开，无供应商锁定）
- 端到端加密协作（密钥在文件里，中继服务器只看密文）
- 技术演示（图表链接表格，改表格自动更新图表）

## 核心架构

- 文档数据以纯 JSON 块（`<bento-doc>`）存在文件顶部，"源代码级诚实"
- File System Access API 原地保存，不支持时回退为下载
- 自研引擎：Morph 动画（同 id 元素跨页平滑变形）、无依赖 SVG 图表引擎（柱/线/饼/散点）、自研 CRDT（6-8KB，字符级合并）
- E2EE 协作（AES-GCM），离线编辑精确合并

## AI 交互方式

- 文件级直接编辑：Claude Code / Cursor / Aider 直接读写 `.bento.html` 中的 JSON 块，无需插件或 API
- 聊天式往返：复制文档 JSON 给任何 LLM 改完再粘回
- agent 指南单页文档：https://bento.page/agents.md（可丢进任何模型上下文）

## 文件说明

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：安装说明

本仓库采用"只登记 + 安装说明"方式收录，未克隆源码。原仓库为完整工程（含编辑器、图表引擎、协作服务器、CRDT 实现），skill 只是入口。

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 依赖与环境要求

- Claude Code（skill 通过插件市场安装）
- 也可不用 skill：任何能读写文件的 AI 助手直接操作 `.bento.html` 的 JSON 块即可
- 生成物为 HTML，浏览器打开即可

## 备注

- 信息来源：B 站视频 BV1tebi6oEYV + 原仓库 README + 第三方介绍（houdao.com、aitoolnet.com）
- 与本仓库其他 skill 的关系：lieflat-charts 是数据可视化图表，bento-slides 是演示文稿整体方案（自带图表引擎）；guizang-material-illustration 是静态插画配图，bento 是可交互演示文稿
- 在线试用（无需安装）：https://bento.page/slides
- 待验证：尚未实际安装运行过 bento-slides skill
