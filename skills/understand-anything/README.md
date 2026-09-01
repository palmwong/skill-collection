# Understand Anything

## 基本信息

- 来源地址：https://github.com/Egonex-AI/Understand-Anything（原始作者 Lum1104）
- 作者/组织：Egonex-AI / Lum1104
- 收集日期：2026-08-14
- 协议：以原仓库 LICENSE 为准

## 功能简介

Claude Code 插件：用多 agent 流水线扫描整个项目，把每个文件、函数、类、依赖构建成知识图谱（`knowledge-graph.json`），并提供交互式 web dashboard 可视化探索。目标不是炫复杂度，而是让图谱"悄悄教会你每个部分如何拼在一起"。支持 Claude Code、Codex、Cursor、OpenCode、OpenClaw、Antigravity 等多平台。

## 使用场景

- 新人加入团队，面对几十万行陌生代码库，需要按依赖顺序的引导式学习路径
- PM / 设计师想理解系统实际运作方式，但不读代码（直接问"认证流程怎么工作"）
- commit 前用 `/understand-diff` 分析改动影响范围和连锁反应
- 给 AI 工具提供项目级深度上下文，辅助 code review
- 对 Karpathy 风格 wiki 知识库生成概念图谱（`/understand-knowledge`）

## 命令体系

| 命令 | 作用 |
|---|---|
| `/understand` | 多 agent 流水线扫描全项目，生成知识图谱 |
| `/understand-dashboard` | 打开交互式 web dashboard，图谱可视化探索 |
| `/understand-chat <问题>` | 基于图谱问答 |
| `/understand-explain <文件>` | 深度解析某个文件/函数/模块 |
| `/understand-diff` | 分析当前改动的影响范围 |
| `/understand-onboard` | 生成新人 onboarding 指南（架构分层、复杂度热点） |
| `/understand-knowledge` | 对 wiki 知识库生成概念知识图谱 |

## 文件说明

本仓库采用"只登记 + 安装说明"方式收录，未复制插件源代码。

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：多平台一键安装说明（指向原仓库）

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。该插件为完整工程（含 dashboard），推荐通过 Claude Code 插件市场安装，而非复制 skill 目录。

## 依赖与环境要求

- Claude Code 插件市场（或其他支持平台的对应安装机制）
- 首次运行 `/understand` 会对项目做全量扫描，大项目耗时较长
- 在线 demo 可先体验：https://understand-anything.com/demo/

## 备注

- 收录方式：只登记 + 安装说明，未克隆源仓库（插件含 dashboard 工程代码，体量大）
- 与本仓库其他 skill 的差异：learn（方法论型，学任何领域）vs understand-anything（工具型，专精代码库理解，带 pipeline + dashboard）
- 待验证：尚未在实际项目中运行过 `/understand` 全流程
