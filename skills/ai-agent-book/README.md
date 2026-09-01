# ai-agent-book（深入理解 AI Agent）

## 基本信息

- 来源地址：https://github.com/bojieli/ai-agent-book
- 作者/组织：李博杰（bojieli）
- 收集日期：2026-07-30
- 协议：Apache-2.0
- 语言/形态：开源技术图书 + 93 个配套实验项目（Python 为主）

## 功能简介

一本系统讲解 AI Agent 设计与工程实践的原创中文书籍，围绕核心公式 **Agent = LLM + 上下文 + 工具** 展开，从基础概念讲到生产落地，并配套大量可运行代码实验。

## 内容结构（第 1–10 章）

| 章 | 主题 | 一句话核心 |
|---|---|---|
| 1 | Agent 基础知识 | Agent = LLM + 上下文 + 工具；Harness 工程才是竞争力 |
| 2 | 上下文工程 | 上下文决定能力上限：KV Cache、提示工程、Agent Skills、上下文压缩 |
| 3 | 用户记忆和知识库 | 跨会话记住用户、接入外部知识：用户记忆、RAG、结构化索引、知识图谱 |
| 4 | 工具 | 工具是 Agent 的双手：MCP 协议、感知/执行/协作三类工具、事件驱动异步 Agent、主动工具发现 |
| 5 | Coding Agent 与代码生成 | 代码是「能创造新工具的工具」，生产级 Coding Agent 全景 |
| 6 | Agent 的评估 | 把表现变成可比较信号：评估环境、指标、统计显著性、评估驱动选型 |
| 7 | 模型后训练 | 预训练/SFT/RL 三阶段：何时选 SFT、何时选 RL，工具调用内化、样本效率 |
| 8 | Agent 的持续进化 | 从运行轨迹获得学习信号，更新知识、指令、程序与参数 |
| 9 | 多模态与实时交互 | 从文本扩展到语音、GUI、物理世界：语音三范式、Computer Use、机器人 |
| 10 | 多 Agent 协作 | 群体智能高于个体：协作框架、上下文共享/隔离、涌现的「Agent 社会」 |

## 使用场景

- 系统学习 AI Agent 原理与工程实现
- 作为课程教材或团队技术分享材料
- 复现 93 个配套实验，理解关键概念
- 查找具体技术点（如 MCP、RAG、RL、多 Agent 协作）的参考实现

## 仓库结构

- `book/`：中文正文源码（introduction.md、chapter1.md ~ chapter10.md、afterword.md）
- `book-en/`、`book-ar/`、`book-zhtw/`、`book-ru/`、`book-ta/`、`book-vi/`、`book-ja/`、`book-tr/`：社区翻译版本
- `chapter1/` ~ `chapter10/`：各章配套实验代码
- `docs/`：在线文档站点源码与学习建议
- `scripts/`：构建与维护脚本
- `EPUB.md`、`build_epub.sh`：电子书构建说明

## 依赖与环境要求

- 阅读正文：任意 Markdown 阅读器或浏览器在线阅读
- 运行实验：各章节项目依赖不同，通常需要 Python 3.x、相关 AI 平台 API Key
- 编译 PDF/EPUB：需 pandoc、xelatex、ElegantBook 文档类与相关字体

## 安装到 IDE

本项目不是传统意义上的「skill 包」，而是一本书和实验集合，因此不适合放入 `.claude/skills/` 这类 IDE skill 目录。通常用法是克隆仓库后直接阅读或运行实验。详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 备注

- 本地仅归档本说明，未克隆源仓库；如需阅读或复现实验，建议从源仓库拉取完整内容
- 第 6、7、9、10 章的 19 个外部仓库未内置，需按 README 中的一键克隆脚本单独获取
- 在线阅读地址：https://bojieli.github.io/ai-agent-book/
