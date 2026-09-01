# grill-me

## 基本信息

- 来源地址：用户在其他对话中创建，原始文件 `skills/grill-me.md`
- 作者/组织：用户自建
- 收集日期：2026-08-09
- 协议：未声明

## 功能简介

压力测试面试 skill，通过连续追问帮助用户在设计/计划阶段暴露假设、理清决策树，直到双方对计划达成共识。

## 使用场景

- 用户有一个初步方案，想被连续追问挑战
- 设计评审前自我压力测试
- 复杂需求分解时暴露依赖关系

## 文件说明

- `SKILL.md`：该 skill 的主定义文件
- `INSTALL.md`：如何一键安装到 IDE（Claude Code / Cursor / Trae 等）

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

通用命令示例（以 Claude Code 项目级目录为例）：

```powershell
$skill = "grill-me"
$src = "\\192.168.10.49\sharepoint\obsidian\vault\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

## 依赖与环境要求

无

## 备注

原始文件为 `skills/grill-me.md`，本次按 AGENTS.md 规范迁移到子目录并补齐 README/INSTALL。
