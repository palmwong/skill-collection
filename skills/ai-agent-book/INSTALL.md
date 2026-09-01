# ai-agent-book 使用/安装指南

## 重要说明

`ai-agent-book` 不是传统意义上的 IDE skill（没有 SKILL.md 可被 Claude Code / Cursor 直接调用），而是一本开源图书 + 93 个配套实验项目。因此它**不适合**放进 `.claude/skills/` 或 `.cursor/skills/` 这类目录。

本文件说明如何把它作为学习和复现项目使用。

## 方式一：克隆仓库直接阅读

```powershell
# 克隆到本地
$dest = "$PWD\ai-agent-book"
git clone https://github.com/bojieli/ai-agent-book.git $dest

# 在线阅读（推荐，支持多语言、全文搜索）
# https://bojieli.github.io/ai-agent-book/
```

克隆后：

- 正文源码：`book/introduction.md`、`book/chapter1.md` ~ `book/chapter10.md`
- 配套实验：`chapter1/` ~ `chapter10/`
- 多语言版本：`book-en/`、`book-zhtw/` 等

## 方式二：把某一章实验变成 IDE 可调用的 skill

如果你希望把书中的某个实验/方法封装成 agent 可调用的 skill，建议：

1. 在 `c:\Users\2027\Documents\Skill\skills\` 下新建一个 skill 子目录，例如 `ai-agent-book-chapter3-rag`
2. 把书中相关章节的核心方法论整理成 `SKILL.md`
3. 按本仓库模板补充 `README.md` 和 `INSTALL.md`
4. 将该 skill 安装到 IDE：

```powershell
$skill = "ai-agent-book-chapter3-rag"
$src = "c:\Users\2027\Documents\Skill\skills\$skill"
$dest = "$PWD\.claude\skills\$skill"
New-Item -ItemType Directory -Path (Split-Path $dest) -Force | Out-Null
Copy-Item -Path $src -Destination $dest -Recurse -Force
```

## 方式三：作为项目级规则（Rules）在 Trae/Cursor 中使用

如果你希望 IDE 在回答 Agent 相关问题时参考这本书的知识，可以把本书目录作为项目上下文：

1. 在目标项目根目录创建 `.cursor/rules/` 或 `.trae/rules/`
2. 将 `book/` 下的关键章节复制进去，或写一个索引文件指向 `ai-agent-book` 本地路径
3. 重启 IDE，agent 即可在上下文窗口中引用这些内容

## 依赖与环境要求

- 阅读正文：任意 Markdown 阅读器
- 运行实验：各章节依赖不同，通常需要 Python 3.x、pip、相关 AI 平台 API Key
- 编译 PDF/EPUB：pandoc、xelatex、ElegantBook 文档类与相关字体

## 外部仓库获取

第 6、7、9、10 章有 19 个外部仓库未内置，需按源仓库 README 的「一键克隆脚本」单独克隆。

## 学习建议

1. 先读 `book/chapter1.md`，理解 Agent = LLM + 上下文 + 工具
2. 选择感兴趣的章节，进入对应 `chapterX/` 跑实验
3. 遇到问题参考在线文档：https://bojieli.github.io/ai-agent-book/
