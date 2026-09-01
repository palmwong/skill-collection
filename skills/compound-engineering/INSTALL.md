# Compound Engineering 安装说明

本 skill 为完整插件（37 skills + 51 agents），不从本仓库复制文件，直接从原仓库安装。

原仓库：https://github.com/EveryInc/compound-engineering-plugin

## Claude Code（最简单）

```bash
/plugin marketplace add EveryInc/compound-engineering-plugin
/plugin install compound-engineering
```

安装后运行 `/ce-setup` 检查环境并初始化项目配置。

## Cursor

在 Cursor Agent 聊天中：

```
/add-plugin compound-engineering
```

或在插件市场搜索 "compound engineering"。

## GitHub Copilot（VS Code）

1. 打开 VS Code 命令面板
2. 运行 `Chat: Install Plugin from Source`
3. 输入 `EveryInc/compound-engineering-plugin`
4. 选择 `compound-engineering`

## Codex（需额外步骤）

Codex 原生插件规格支持 skills 但不支持自定义 agents，而 agents 是 `/ce-code-review` 和 `/ce-plan` 等命令的核心：

```bash
# Step 1: 注册 marketplace
codex plugin marketplace add EveryInc/compound-engineering-plugin

# Step 2: 通过 Bun 安装 agents
bunx @everyinc/compound-engineering-plugin install-agents

# Step 3: 验证
codex plugin list
```

## 快速验证

安装后运行：

```
/ce-setup
```

如果返回环境检查通过信息，说明安装成功。

## 核心工作流速查

```
/ce-strategy          # 创建产品战略文档（首次）
/ce-ideate            # 大格局构思（可选）
/ce-brainstorm "需求描述"   # 交互式需求文档
/ce-plan <需求文档路径>      # 生成实施计划
/ce-work              # 执行计划
/ce-code-review       # 多 agent 审查
/ce-compound          # 知识沉淀
/ce-debug             # 系统性 bug 排查
/ce-product-pulse     # 产品健康报告
```

## 使用提示

- 首次使用建议先运行 `/ce-strategy` 创建 STRATEGY.md，后续 brainstorm 和 plan 会自动读取作为 grounding
- `/ce-work` 使用 git worktree 隔离，不影响主分支
- `/ce-compound` 是核心差异化步骤，不要跳过
