# Graphify 安装说明

形态是 **先装 CLI，再注册 skill**。不要只把 `SKILL.md` 拷进 `.claude/skills/`。

原仓库：https://github.com/Graphify-Labs/graphify  
PyPI：https://pypi.org/project/graphifyy/（包名 `graphifyy`，命令仍是 `graphify`）

## 1. 安装 CLI

需要 Python 3.10+。推荐用 uv：

```powershell
winget install astral-sh.uv
uv tool install graphifyy
uv tool update-shell
```

备选：

```powershell
pipx install graphifyy
# 或（不推荐，PATH / 环境容易错）
pip install graphifyy
```

临时跑一次（注意 `--from` 必须是包名）：

```powershell
uvx --from graphifyy graphify --help
```

Windows 若提示找不到 `graphify`，把 `%APPDATA%\Python\Python3xx\Scripts` 或 uv 的 tool bin 加进 PATH。

## 2. 把 skill 装进助手

用户级（默认检测 Claude Code）：

```powershell
graphify install
```

项目级（写入当前仓库，可提交）：

```powershell
graphify install --project
graphify install --project --platform agents
```

指定平台示例：

```powershell
graphify install --platform cursor
graphify install --platform gemini
graphify install --platform copilot
graphify cursor install
graphify vscode install
graphify antigravity install
```

Grok / 走 Agent Skills 规范的助手用：

```powershell
graphify install --platform agents
# 或项目内：
graphify install --project --platform agents
```

会写到 `~/.agents/skills/graphify/` 或 `./.agents/skills/graphify/`（含 `SKILL.md` 和 `references/`）。

Codex 用 `$graphify` 而不是 `/graphify`，且建议在 `~/.codex/config.toml` 的 `[features]` 里设 `multi_agent = true`。

PowerShell 里不要把 `/graphify` 当命令执行，斜杠会被当成路径。

## 3. 建图与验证

在目标仓库：

```powershell
graphify .
# 或在助手里对 Claude Code 说：/graphify .
```

应出现：

```
graphify-out/
  graph.html
  GRAPH_REPORT.md
  graph.json
```

查询：

```powershell
graphify explain "某个符号"
graphify path "A" "B"
graphify query "认证是怎么串起来的"
```

可选：提交后自动重建。

```powershell
graphify hook install
```

## 4. 可选 extras

按需，例如：

```powershell
uv tool install "graphifyy[pdf]"
uv tool install "graphifyy[mcp]"
uv tool install "graphifyy[all]"
```

## 不要做的

- 不要 `pip install graphify`（那是别人的包）
- 不要只复制 skill 文件却不装 CLI
- 不要用 `uvx graphify`（uvx 把第一个词当包名，包名是 `graphifyy`）
