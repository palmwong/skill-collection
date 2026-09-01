# Compound Engineering

## 基本信息

- 来源地址：https://github.com/EveryInc/compound-engineering-plugin
- 作者/组织：Every Inc（Kieran Klaassen 等）
- 收集日期：2026-08-19
- 协议：以原仓库 LICENSE 为准

## 功能简介

AI 原生工程哲学插件：通过将 80% 精力投入计划与审查、20% 用于执行与沉淀，让每个工程单元都比上一个更容易，而非累积技术债务。核心循环 Plan → Work → Review → Compound → Repeat，第四步 Compound（知识沉淀）是灵魂——前三步产出功能，第四步产出"能更好构建功能的系统"。

## 使用场景

- 单人或小型团队维护多个产品（Every.to 用此系统以单人团队运营 5 个产品）
- 希望 AI 辅助开发不随时间衰减，而是持续积累上下文和判断力
- 需要结构化工作流：需求 brainstorm → 计划 → 执行 → 多 agent 审查 → 知识沉淀
- 大型功能开发前的系统性规划和审查

## 核心循环（80/20 原则）

| 步骤 | 时间占比 | 作用 | 关键动作 |
|---|---|---|---|
| Plan | 40% | 把想法变成蓝图 | 理解需求、研究代码库、研究外部文档、设计方案、验证计划 |
| Work | 10% | 执行计划 | 隔离环境（git worktree）、逐步实施、运行验证、跟踪进度 |
| Review | 40% | 审查捕获问题 | 多 agent 并行审查（12 个视角）、优先级标记（P1/P2/P3）、修复验证、捕获模式 |
| Compound | 10% | 知识沉淀（灵魂） | 捕获解决方案、YAML frontmatter 标记、更新知识库、让下次更容易 |

## 命令体系（37 skills + 51 agents）

**核心循环**：
```
/ce-brainstorm → /ce-plan → /ce-work → /ce-code-review → /ce-compound
```

**扩展命令**：

| 命令 | 作用 |
|---|---|
| `/ce-strategy` | 创建/维护 STRATEGY.md（产品战略锚点） |
| `/ce-ideate` | 大格局构思，生成并评估多个想法 |
| `/ce-debug` | 系统性复现 bug、追踪根因、修复 |
| `/ce-product-pulse` | 生成产品使用/性能/错误报告 |
| `/ce-setup` | 首次安装后环境检查和配置 |

**多 Agent 审查**：12 个子 agent 并行审查，各自专注不同角度（安全、性能、过度设计等）。

## 关键机制

- **Git worktrees**：隔离工作环境，不影响主分支
- **YAML frontmatter**：给知识打标签，便于检索复用
- **STRATEGY.md**：产品战略文档，brainstorm 和 plan 时自动读取作为 grounding
- **知识沉淀**：每次循环的 learnings 写入知识库，下次类似工作自动复用

## 文件说明

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：安装说明

本仓库采用"只登记 + 安装说明"方式收录，未克隆源码。原仓库为完整插件（37 skills + 51 agents）。

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 依赖与环境要求

- Claude Code / Cursor / Codex / GitHub Copilot
- Claude Code 和 Cursor 直接插件市场安装；Codex 需额外步骤安装 agents
- 安装后运行 `/ce-setup` 检查环境

## 备注

- 信息来源：原仓库 README + Every.to 官方指南 + 第三方评测（readerfi.com、ai-uchi.ru、tonybai.com）
- 与本仓库其他 skill 的关系：这是一个完整工作流框架，可整合 grill-me（需求对齐）、understand-anything（代码研究）、writing-for-agents（知识沉淀写作）
- 与 teach 的关系：teach 是教学场景，compound-engineering 是工程场景，都强调状态沉淀
- 待验证：尚未实际安装运行过
