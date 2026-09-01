# Writing for Agents 安装说明

本 skill 为 mattpocock/skills 仓库中的一个子目录，不从本仓库复制文件，直接从原仓库安装。

原仓库：https://github.com/mattpocock/skills

## Claude Code（推荐，自动更新）

```bash
claude plugins install mattpocock-skills
```

或在会话内：

```
/plugin install mattpocock-skills
```

安装后 writing-for-agents 作为 model-invoked skill 自动可用，agent 在写 skill 或编辑 AGENTS.md 时会自动触发。

## Codex 及其他 agent

```bash
npx skills@latest add mattpocock/skills
```

选择要安装的 skill（确保勾选 `setup-matt-pocock-skills`），以及装到哪些 coding agent。

## 手动安装

```bash
git clone https://github.com/mattpocock/skills.git
```

然后把 `skills/productivity/writing-for-agents/` 目录复制到 IDE 的 skills 目录（如 `.claude/skills/writing-for-agents/`）。

## 使用方式

这个 skill 是 model-invoked，不需要手动调用。当你：

- 创建新 skill 文件
- 编辑 AGENTS.md 或 CLAUDE.md
- 优化现有 skill 的 description 或内容结构

agent 会自动应用 writing-for-agents 的方法论。

也可以显式触发：

```
请用 writing-for-agents 的原则审查我的 SKILL.md
```

## 相关文档

- SKILL-MECHANICS.md（frontmatter、invocation choice、router skills）：https://github.com/mattpocock/skills/blob/main/skills/productivity/writing-for-agents/SKILL-MECHANICS.md
