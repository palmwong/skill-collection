# <Skill 名称>

## 基本信息

- 来源地址：<GitHub URL>
- 作者/组织：<作者>
- 收集日期：<YYYY-MM-DD>
- 协议：<License，如 MIT>

## 功能简介

<一段话说明这个 skill 做什么、解决什么问题>

## 使用场景

- <场景 1>
- <场景 2>

## 文件说明

- `SKILL.md`：<该 skill 的主定义文件>
- `INSTALL.md`：<如何一键安装到 IDE（Claude Code / Cursor / Trae 等）>
- <其他文件>：<说明>

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。如果该 skill 只需简单复制，可在此直接写命令。

通用命令示例（以 Claude Code 项目级目录为例）：

```powershell
$skill = "<skill-name>"
$src = "c:\Users\2027\Documents\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

## 依赖与环境要求

<如：需要特定运行时、API Key、MCP 服务等，无则填"无">

## 备注

<验证情况、已知问题、定制改动等>
