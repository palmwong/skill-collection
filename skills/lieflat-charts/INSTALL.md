# Lieflat Charts 安装说明

本 skill 为"规则文档 + 模板"形态，需要时将原仓库克隆/下载到本仓库，再复制到 IDE 的 skills 目录。

原仓库：https://github.com/larashero3-dotcom/lieflat-charts

## 方式一：克隆原仓库到本仓库（推荐）

把源码收纳进本仓库，保持仓库作为统一入口：

```powershell
cd c:\Users\2027\Documents\Skill\skills
git clone https://github.com/larashero3-dotcom/lieflat-charts.git lieflat-charts-src
```

克隆后把 `lieflat-charts-src` 作为安装源（见下方"安装到 IDE"）。

## 方式二：直接克隆到 IDE skills 目录（跳过本仓库）

### Claude Code（项目级）

```powershell
cd <你的项目目录>
git clone https://github.com/larashero3-dotcom/lieflat-charts.git .claude\skills\lieflat-charts
```

### Claude Code（用户级，所有项目可用）

```powershell
git clone https://github.com/larashero3-dotcom/lieflat-charts.git "$env:USERPROFILE\.claude\skills\lieflat-charts"
```

### Cursor

```powershell
cd <你的项目目录>
git clone https://github.com/larashero3-dotcom/lieflat-charts.git .cursor\skills\lieflat-charts
```

## 安装到 IDE（方式一克隆后，从本仓库复制）

以 Claude Code 项目级目录为例：

```powershell
$skill = "lieflat-charts"
$src = "c:\Users\2027\Documents\Skill\skills\lieflat-charts-src"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

## 安装后验证

在 Claude Code / Codex 中输入：

```
把这季度的转化数据画一下，发公众号用
```

如果 agent 按设计语法生成图表（黑白灰或青瓷蓝/椰林绿/编辑部红之一），说明安装成功。

## 使用提示

- 默认只生成单张图表；明确要求"报告/年报/月报/白皮书/海报/brief"时才走 12 套整页报告模板
- 生成物为 HTML，浏览器打开即可
- 想换色系可直接说"用青瓷蓝"或"用编辑部红"，不用重新生成结构
- 交互大图模板可先在浏览器体验：https://larashero3-dotcom.github.io/lieflat-charts/templates/big-force.html

## 协议提醒

PolyForm 非商业协议：个人学习、论文配图、公众号内容创作均可；商用前请查看原仓库 LICENSE 确认范围。
