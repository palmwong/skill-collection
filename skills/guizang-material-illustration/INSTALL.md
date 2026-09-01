# guizang-material-illustration 安装指南

本文件说明如何把 guizang-material-illustration skill 安装到 Claude Code / Codex 等支持 skills 的 IDE。

## 目录速查

| IDE | 项目级目录 | 用户级目录 | 备注 |
|---|---|---|---|
| Claude Code | `.claude/skills/` | `~/.claude/skills/`（Windows：`%USERPROFILE%\.claude\skills\`） | 推荐项目级 |
| Codex / OpenAI Agent | 通过 `npx skills add` 管理 | — | 见方式一 |
| Cursor | `.cursor/skills/` | 暂无 | Cursor 的 skill 支持可能需确认版本 |

## 方式一：官方一行命令（推荐，支持 npx skills 的环境）

```bash
npx skills add https://github.com/op7418/guizang-material-illustration --skill guizang-material-illustration
```

## 方式二：PowerShell 一键安装到 Claude Code 项目级目录

```powershell
$skill = "guizang-material-illustration"
$src = "c:\Users\2027\Documents\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

安装到 Claude Code 用户级目录（Windows）：

```powershell
$skill = "guizang-material-illustration"
$src = "c:\Users\2027\Documents\Skill\skills\$skill"
$dest = "$env:USERPROFILE\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

## 方式三：git clone 到用户级 skill 目录

```bash
# macOS / Linux
git clone https://github.com/op7418/guizang-material-illustration.git ~/.claude/skills/guizang-material-illustration

# Windows PowerShell
New-Item -ItemType Directory -Path "$env:USERPROFILE\.claude\skills" -Force
git clone https://github.com/op7418/guizang-material-illustration.git "$env:USERPROFILE\.claude\skills\guizang-material-illustration"
```

## 安装后验证

检查目录下是否包含：

- `SKILL.md`
- `assets/`
- `references/`

```powershell
Get-ChildItem -Path "$env:USERPROFILE\.claude\skills\guizang-material-illustration"
```

## 触发方式

安装完成后，对 Agent 说以下任意一种即可触发：

- "帮我生成一张配图"
- "做一张带字解释图"
- "把这个概念画成图解插画"
- "把这张图表美化一下"
- "给这段工作汇报做一张材质风配图"
- "这个概念比较冷门，先搜参考信息再生成图"
- "给这篇小学科学课文做一张解释图"
- "做一张能放进小红书卡片里的中心图"

## 注意事项

- 本 skill 只生成中心配图，完整卡片排版请配合 `guizang-social-card-skill` 使用
- 需要当前 Agent 环境支持图像生成（GPT-Image / imagegen 等）
- 仓库未显示明确 LICENSE，商业使用前建议向作者确认授权
