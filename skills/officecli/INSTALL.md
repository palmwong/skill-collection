# OfficeCLI 安装说明

本 skill 为单一二进制 + skill 文件形态，不从本仓库复制文件，直接从原仓库安装。

原仓库：https://github.com/iOfficeAI/OfficeCLI

## 方式一：对 AI Agent（最简单）

把以下命令粘贴到 AI agent 的聊天中，agent 会读 skill 文件并自动安装一切：

```bash
curl -fsSL https://officecli.ai/SKILL.md
```

## 方式二：对人类（CLI）

```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/iOfficeAI/OfficeCLI/main/install.sh | bash

# Windows (PowerShell)
irm https://raw.githubusercontent.com/iOfficeAI/OfficeCLI/main/install.ps1 | iex

# 或
brew install officecli
npm install -g @officecli/officecli
```

安装后运行：

```bash
officecli install
```

自动检测已装的 AI 工具（Claude Code、Cursor、Windsurf、GitHub Copilot 等），装好技能文件，零配置。

## 方式三：GUI 桌面应用

安装 AionUi（https://github.com/iOfficeAI/AionUi），通过自然语言创建和编辑 Office 文档，底层由 OfficeCLI 驱动。

## 快速验证

```bash
# 创建 PPT
officecli create deck.pptx

# 实时预览（浏览器打开 localhost:26315）
officecli watch deck.pptx

# 添加幻灯片（另一个终端，浏览器实时更新）
officecli add deck.pptx / --type slide --prop title="Hello, World!"

# 查看大纲
officecli view deck.pptx outline

# 查看 HTML 渲染
officecli view deck.pptx html
```

## 使用提示

- 命令分三层：L1 读取、L2 DOM 操作、L3 原始 XML，九成时间停在 L1 和 L2
- 元素路径稳定：`/slide[1]/shape[1]`，AI 用路径寻址
- 错误返回结构化错误码 + 修正建议，AI 可自己纠错
- Excel 公式写入即自动求值，不用切回 Office 重算
