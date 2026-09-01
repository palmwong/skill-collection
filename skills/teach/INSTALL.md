# Teach 安装说明

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

这是 Claude Code 官方插件市场，无需先添加，更新自动到达。

## Codex 及其他 agent

```bash
npx skills@latest add mattpocock/skills
```

安装器会让你选择要装哪些 skill（确保勾选 `setup-matt-pocock-skills`），以及装到哪些 coding agent。

## 手动安装

```bash
git clone https://github.com/mattpocock/skills.git
```

然后把 `skills/productivity/teach/` 目录复制到 IDE 的 skills 目录（如 `.claude/skills/teach/`）。

## 首次配置

安装后，在 agent 中运行一次（每个仓库一次）：

```
/setup-matt-pocock-skills
```

它会问你：用哪个 issue tracker（GitHub / Linear / 本地文件）、triage 标签、文档保存位置。

## 开始使用

进入一个空目录（将作为教学工作区），运行：

```
/teach 我想学魔方还原
```

agent 会引导你建立 mission、搜索资源、生成第一节 HTML 课程。

## 跨会话续学

下次打开 agent，告诉它"继续学魔方"，它会读 learning-records 判断进度并定做下一课。

## 安装后验证

运行 `/teach` 后检查当前目录是否生成了 MISSION.md 和 lessons/ 目录。如果有，说明安装成功。
