# AGENTS.md — 仓库使用指南（给 AI Agent / 协作者）

## 仓库定位

本仓库用于集中存放和管理从 GitHub 收集的各类 skill，并提供统一的登记、说明和交接文档。

## 目录结构

```
c:\Users\2027\Documents\Skill\
├── AGENTS.md            # 本文件：仓库结构与协作规范
├── memo.md              # Skill 清单总表（登记入口）
├── handoff.md           # 交接文档：当前状态与待办
├── trae-custom-agent-skill-guide.md  # Trae 自定义 Agent 绑定 Skill 指南
├── notes/               # 方法论、学习笔记等非 skill 类资料
│   └── skill-design-guide.md  # Skill 设计实战指南（知乎文章整理）
└── skills/              # 各 skill 的实际存放目录
    ├── _template.md     # 单个 skill 的记录模板
    └── <skill-name>/    # 每个 skill 一个子文件夹
        ├── README.md    # 按模板填写的 skill 详细记录
        ├── INSTALL.md   # 一键安装到 IDE 的说明
        └── ...          # skill 源文件（如 SKILL.md、脚本等）
```

## 常用参考文档

- 三个库通用口令：见 [README.md](README.md)（归档 / 上传 / 整理 / 回归 / 同步）。`daily` 已并入 grok-notes。
- 单个 skill 安装方法：查看该 skill 目录下的 `INSTALL.md` 或 `README.md` 中的「安装到 IDE」章节
- Trae 自定义 Agent 绑定 Skill：参考 [trae-custom-agent-skill-guide.md](file:///c:/Users/2027/Documents/Skill/trae-custom-agent-skill-guide.md)
- 通用 IDE 目录速查：Claude Code 为 `.claude/skills/`（或 `~/.claude/skills/`），Cursor 为 `.cursor/skills/`

## 新增 skill 的标准流程

1. 在 `skills/` 下以 skill 名称新建子文件夹（全小写、单词用 `-` 连接）。
2. 将 skill 源文件（SKILL.md、相关脚本等）放入该文件夹。
3. 复制 `skills/_template.md` 为该文件夹下的 `README.md`，填写完整信息。
4. **创建 `INSTALL.md`**：在该 skill 文件夹下编写一键安装到 Claude Code / Cursor / Trae 等 IDE 的说明和命令。README.md 中也要链接到 INSTALL.md。
5. 在 `memo.md` 的清单总表中登记一行。
6. 如有未完成的验证或待办事项，更新 `handoff.md`。

## 维护规范

- 不修改已收录 skill 的原始文件；如需定制，在子文件夹中另存副本并注明。
- 废弃的 skill 不直接删除，在 memo.md 中将状态改为"已废弃"并注明原因。
- 每次批量变更后，同步更新 handoff.md 的"当前状态"部分。
