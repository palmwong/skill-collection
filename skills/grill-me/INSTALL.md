# grill-me 安装指南

本文件说明如何把 grill-me skill 安装到不同 IDE 的 skill 目录。

## 目录速查

| IDE | 项目级目录 | 用户级目录 | 备注 |
|---|---|---|---|
| Claude Code | `.claude/skills/` | `~/.claude/skills/`（Windows：`%USERPROFILE%\.claude\skills\`） | 推荐项目级 |
| Cursor | `.cursor/skills/` | 暂无 | 见 Cursor 官方文档 |
| Trae | 暂无统一 skill 目录 | — | 参考本仓库 [trae-custom-agent-skill-guide.md](../../trae-custom-agent-skill-guide.md) |

## 方式一：PowerShell 一键安装到 Claude Code 项目级目录

```powershell
$skill = "grill-me"
$src = "\\192.168.10.49\sharepoint\obsidian\vault\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

安装到 Claude Code 用户级目录（Windows）：

```powershell
$skill = "grill-me"
$src = "\\192.168.10.49\sharepoint\obsidian\vault\Skill\skills\$skill"
$dest = "$env:USERPROFILE\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

Cursor 只需把 `.claude` 替换为 `.cursor`。

## 方式二：符号链接（便于同步更新）

```powershell
$skill = "grill-me"
$src = "\\192.168.10.49\sharepoint\obsidian\vault\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Remove-Item -Path $dest -Recurse -Force -ErrorAction SilentlyContinue
New-Item -ItemType SymbolicLink -Path $dest -Target $src
```

注意：符号链接需要管理员权限或启用 Windows 开发者模式。

## 安装后验证

1. 重启 IDE
2. 在 agent 面板或 skill 列表中查看是否出现 grill-me
3. 测试触发：输入 "grill me on this plan" 或 "帮我压力测试一下这个方案"，确认 agent 调用该 skill

## 触发方式

- "grill me"
- "压力测试这个方案"
- "连续追问我"
- "设计评审前自我挑战"
