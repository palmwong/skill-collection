# Understand Anything 安装说明

本 skill 为完整插件工程（含 dashboard），不从本仓库复制文件，直接从原仓库安装。

原仓库：https://github.com/Egonex-AI/Understand-Anything

## Claude Code（原生推荐）

在 Claude Code 中执行：

```
/plugin marketplace add Lum1104/Understand-Anything
/plugin install understand-anything
```

安装后在项目目录下运行 `/understand` 开始扫描。

## Codex

对 Codex 说：

```
Fetch and follow instructions from https://raw.githubusercontent.com/Lum1104/Understand-Anything/refs/heads/main/.codex/INSTALL.md
```

## Cursor

克隆原仓库后用 Cursor 打开，Cursor 会通过 `.cursor-plugin/plugin.json` 自动识别插件，无需手动安装。

```powershell
git clone https://github.com/Egonex-AI/Understand-Anything.git
```

## OpenCode

在 `opencode.json` 中添加：

```json
{
  "plugin": ["understand-anything@git+https://github.com/Lum1104/Understand-Anything.git"]
}
```

## OpenClaw / Antigravity

分别让 AI 工具抓取并执行原仓库 `.openclaw/INSTALL.md` 或 `.antigravity/INSTALL.md` 中的说明（URL 格式同 Codex）。

## 使用流程速查

1. `/understand`：扫描项目，生成 `.understand-anything/knowledge-graph.json`
2. `/understand-dashboard`：打开交互式可视化面板
3. `/understand-chat <问题>`：基于图谱提问
4. `/understand-explain <文件路径>`：深入解析某模块
5. `/understand-onboard`：生成新人 onboarding 文档

## 试用

不想安装可先看在线 demo：https://understand-anything.com/demo/
