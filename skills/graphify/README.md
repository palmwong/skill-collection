# Graphify

## 基本信息

- 来源地址：https://github.com/Graphify-Labs/graphify
- 官网：https://www.graphify.com
- 作者/组织：Graphify Labs（YC S26；原作者 safishamsi）
- 收集日期：2026-09-20
- 协议：Apache 2.0（另有 LICENSE-MIT）
- 形态：**CLI + Skill（一体）**。PyPI 包 `graphifyy` 提供 `graphify` 命令；`graphify install` 把 `graphify/skill.md` 写入各助手的 skill 目录。不是「只复制 SKILL.md 就能跑」的纯 skill。

## 功能简介

把任意目录里的代码、文档、PDF、图片、视频建成可查询知识图谱。代码用 tree-sitter 本地解析（不调 LLM）；文档/媒体才走助手模型或 API。边带 `EXTRACTED` / `INFERRED` 标签。助手里 `/graphify .`（Codex 为 `$graphify`），之后用 `query` / `path` / `explain` 走图而不是 grep。另有商业平台 app.graphify.com。

## 使用场景

- 陌生仓库先建图，再问架构、调用链、两概念怎么连
- 代码 + README + PDF/论文混在同一张图里查
- 给 Claude Code / Cursor / Codex / Gemini CLI 等提供项目级图上下文
- git hook / `--watch` 在提交或切分支后增量重建

## 和「纯 skill」的关系

| 层 | 是什么 | 作用 |
|---|---|---|
| CLI | `uv tool install graphifyy` → 命令 `graphify` | 抽 AST、建 `graphify-out/`、query/path/explain |
| Skill | 仓库内 `graphify/skill.md`；安装后如 `.claude/skills/graphify/SKILL.md` | 教助手何时调 CLI、有图时先查图 |
| MCP（可选） | `graphifyy[mcp]` | 把图当 MCP 工具暴露 |

没有 CLI 的 skill 文件只是说明书，建不出图。

## 文件说明

本仓库采用「只登记 + 安装说明」，未克隆上游（Python 工程体量大，以 PyPI 安装为准）。

- `README.md`：本文件
- `INSTALL.md`：安装与验证
- 上游 skill 底稿：https://github.com/Graphify-Labs/graphify/blob/v8/graphify/skill.md

## 安装到 IDE

详见 [INSTALL.md](./INSTALL.md)。推荐：`uv tool install graphifyy` 然后 `graphify install`（或 `--platform` / `--project`）。

## 依赖与环境要求

- Python 3.10+
- 推荐 `uv` 或 `pipx`，避免裸 `pip` 导致 skill 找不到包
- 纯代码抽取可不配 API key；文档/PDF/图需要后端
- Windows：装完若找不到 `graphify`，把 Scripts 加进 PATH；PowerShell 用 `graphify .` 不要写成 `/graphify .`
- PyPI 包名是 **`graphifyy`**（两个 y）；CLI 仍叫 `graphify`

## 备注

- 默认分支 `v8`，收录时最新发行 v0.9.64（2026-09-18）
- 与 understand-anything 都做代码知识图谱：Graphify 偏本地 AST + 持久 `graph.json` + 多助手 skill；Understand Anything 偏多 agent 流水线 + dashboard 插件
- 与 molio 都强调「图而不是向量库」：Graphify 面向代码仓；molio 面向个人 Markdown 知识库
- 待验证：尚未在本机对真实仓库跑通 `/graphify .`
