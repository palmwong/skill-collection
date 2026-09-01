# cangjie-skill 安装指南

本文件说明如何把 cangjie-skill 安装到不同 IDE 的 skill 目录，使其可以被 AI agent 调用。

## 目录速查

| IDE | 项目级目录 | 用户级目录 | 备注 |
|---|---|---|---|
| Claude Code | `.claude/skills/` | `~/.claude/skills/`（Windows：`%USERPROFILE%\.claude\skills\`） | 推荐项目级，避免全局污染 |
| Cursor | `.cursor/skills/` | 暂无 | 见 [Cursor Skills](https://docs.cursor.com/conte
xt/skill-library) |
| Trae | 暂无统一 skill 目录 | — | 可用 `.trae/rules/` 或项目级文档替代，视版本而定 |

## 方式一：手动复制

1. 进入本仓库的 skill 目录：`c:\Users\2027\Documents\Skill\skills\cangjie-skill`
2. 复制整个 `cangjie-skill` 文件夹
3. 粘贴到目标 IDE 的 skill 目录下（项目级或用户级）
4. 重启 IDE，确认 agent 已识别

## 方式二：PowerShell 命令

以安装到 Claude Code 项目级目录为例：

```powershell
$skill = "cangjie-skill"
$src = "c:\Users\2027\Documents\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

安装到 Claude Code 用户级目录（Windows）：

```powershell
$skill = "cangjie-skill"
$src = "c:\Users\2027\Documents\Skill\skills\$skill"
$dest = "$env:USERPROFILE\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

Cursor 只需把 `.claude` 替换为 `.cursor`。

## 方式三：符号链接（便于同步更新）

如果你希望本仓库更新后 IDE 中的 skill 也同步更新，可以使用符号链接：

```powershell
$skill = "cangjie-skill"
$src = "c:\Users\2027\Documents\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
# 如果目标已存在，先删除
Remove-Item -Path $dest -Recurse -Force -ErrorAction SilentlyContinue
New-Item -ItemType SymbolicLink -Path $dest -Target $src
```

注意：符号链接需要管理员权限或启用 Windows 开发者模式。

## 安装后验证

1. 重启 IDE
2. 在 agent 面板或 skill 列表中查看是否出现 cangjie-skill
3. 测试触发：输入 "帮我拆《穷查理宝典》" 或 "把这本书蒸馏成 skill"，确认 agent 调用该 skill

## 注意事项

- 安装前确认目标 IDE 版本支持 skill 功能
- 优先使用项目级目录，避免影响其他项目
- 本仓库仅归档了说明，未包含 cangjie-skill 的原始 methodology/、extractors/、templates/ 等文件。如需完整功能，建议先从源仓库 `https://github.com/kangarooking/cangjie-skill` 拉取全部内容。
