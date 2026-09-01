# Logo Generator 安装说明

本 skill 为开源项目，不从本仓库复制文件，直接从原仓库安装。

原仓库：https://github.com/op7418/logo-generator-skill

## 方式一：自动安装（推荐）

```bash
npx skills add https://github.com/op7418/logo-generator-skill.git
```

自动安装到正确的 skills 目录。

## 方式二：Git Clone

```bash
git clone https://github.com/op7418/logo-generator-skill.git ~/.claude/skills/logo-generator
```

## 方式三：手动安装

1. 下载原仓库
2. 复制 `logo-generator` 文件夹到 Claude Code skills 目录：
   - macOS/Linux: `~/.claude/skills/`
   - Windows: `%USERPROFILE%\.claude\skills\`
3. 确保文件夹结构包含 `SKILL.md` 和 `README.md`

## 安装后配置

```bash
cd ~/.claude/skills/logo-generator
pip install -r requirements.txt
```

配置 Gemini API Key：

```bash
cp .env.example .env
# 编辑 .env 添加 GEMINI_API_KEY
```

重启 Claude Code，输入 `/logo-generator` 验证。

## 使用方式

基本工作流：

1. 开始 logo 项目：`Generate a logo for my AI product called "DataFlow"`
2. 提供上下文（agent 会问）：行业/类别、核心概念、设计偏好
3. 审阅变体：agent 生成 6+ SVG logo 变体 + 设计 rationale
4. 选择并细化：选中最爱，请求调整
5. 生成展示：用多种背景风格创建专业展示图

示例命令：

```
Create a logo for a blockchain security platform
Generate 6 logo variants for "CloudSync" - a file sync tool
Show me the logo in different background styles
Export the logo as PNG at 2048x2048
```

## 依赖提醒

- 需要 Python 环境和 `pip install -r requirements.txt`
- 需要 Gemini API Key（用于 Nano Banana 展示图生成）
- 如果不需要展示图，基础 SVG 生成功能可能无需 API Key（待验证）
