# 在 Trae 中为自定义智能体（Custom Agent）绑定 Skill 的方法

> 本文整理自社区经验与 Trae 当前版本（截至 2026-07-30）的常见做法。Trae 更新较快，部分路径和字段可能随版本变化，建议以实际界面为准。

## 核心思路

在 Trae 中，自定义智能体默认绑定 Skill 的方式主要有两种：

1. **通过 UI 勾选**：最稳定、最推荐，适合个人使用和快速验证
2. **通过配置文件声明**：适合团队协作、需要版本控制配置的场景

下面分别说明。

---

## 方法一：通过 Trae UI 绑定（推荐）

### 操作路径

1. 打开 Trae IDE
2. 进入左侧边栏的 **「智能体」/「Agents」** 面板
3. 点击 **「创建智能体」** 或编辑已有智能体
4. 在配置面板中找到 **「Skills / 工具」** 或类似区域
5. 勾选需要默认绑定的 Skill / 工具
6. 保存配置

### 验证是否生效

1. 在 Chat 或 Builder 模式中 `@` 该智能体
2. 查看输入框下方的工具栏
3. 已绑定的 Skill / 工具图标应处于激活或可见状态
4. 发送一条需要调用该 Skill 的测试消息，确认 Agent 能正确调用

---

## 方法二：通过配置文件绑定（进阶）

> 注意：以下路径和字段结构来自社区经验，Trae 官方文档可能未完全公开。如果路径不存在，说明当前版本不支持手动配置，请回退到 UI 方式。

### 1. 找到 Agent 配置文件

**项目级 Agent**（仅当前项目可用）：

```
项目根目录/.trae/agents/你的智能体名称.json
```

**全局 Agent**（所有项目可用）：

- Windows：`%APPDATA%/Trae/agents/你的智能体名称.json`
- macOS：`~/Library/Application Support/Trae/agents/你的智能体名称.json`

如果找不到上述目录，可以尝试在 Trae 中搜索 `agents` 或查看设置中的配置导出选项。

### 2. 在配置中添加 skills 字段

示例配置：

```json
{
  "name": "物流数据分析师",
  "description": "专注于 DN 数据匹配与车辆调度分析",
  "systemPrompt": "你是一个供应链物流分析助手...",
  "skills": [
    "file-search",
    "terminal",
    "python-exec",
    "mcp-excel-reader"
  ],
  "model": "kimi-k3",
  "temperature": 0.3
}
```

### 字段说明

| 字段 | 作用 | 备注 |
|---|---|---|
| `name` | 智能体显示名称 | 必填 |
| `description` | 智能体功能描述 | 必填，用于在列表中识别 |
| `systemPrompt` | 系统提示词 | 必填，决定智能体行为 |
| `skills` | 绑定的 Skill / 工具 ID 数组 | 具体 ID 取决于 Trae 版本 |
| `model` | 默认调用的模型 | 可选，未设置则使用全局默认 |
| `temperature` | 采样温度 | 可选 |

### 如何获取 Skill ID

1. 在 Trae 的 **Skill 市场 / 已安装 Skills** 中查看每个 Skill 的详情页
2. 查看 Skill 安装目录中的 `skill.json` 或 `SKILL.md` 文件
3. 如果文档未标明 ID，可尝试使用 Skill 的英文名称或文件夹名

---

## 方法三：自定义本地 Skill 后绑定

如果你有自定义 Skill（例如从本仓库收集的 skill），可以先放入项目级 Skill 目录，再在 Agent 配置中引用。

### 推荐目录结构

```
项目根目录/
├── .trae/
│   ├── agents/
│   │   └── 你的智能体.json       ← 在这里引用 skill
│   └── skills/
│       └── drawio-skill/
│           ├── skill.json        ← 自定义 skill 配置（如需要）
│           └── SKILL.md          ← skill 主定义文件
```

### Agent 配置示例

```json
{
  "name": "图表设计师",
  "description": "擅长生成 drawio 流程图",
  "systemPrompt": "你是一个流程图设计专家...",
  "skills": [
    "drawio-skill",
    "file-search",
    "terminal"
  ]
}
```

### 重要说明

- `.trae/skills/` 是否为 Trae 官方支持的 skill 加载路径，取决于具体版本
- 如果不生效，可尝试将 Skill 安装到 Trae 的 Skill 市场目录或全局 skill 目录
- 对于本仓库收集的 skill，更通用的做法是先按各 skill 的 INSTALL.md 安装到 Claude Code / Cursor 目录，再视 Trae 兼容情况迁移

---

## 常见 Skill / 工具 ID 参考

> 以下 ID 为常见命名，实际可用 ID 以 Trae 当前版本为准。

| 名称 | 常见 ID | 类型 |
|---|---|---|
| 文件搜索 | `file-search` | 内置工具 |
| 终端命令 | `terminal` | 内置工具 |
| 代码执行 | `python-exec` | 内置工具 |
| Web 搜索 | `web-search` | 内置工具 / Skill |
| MCP 工具 | `mcp-xxx` | MCP Server |
| 自定义 Skill | `your-skill-name` | Skill |

---

## 三种方式的选择建议

| 场景 | 推荐方式 |
|---|---|
| 个人快速试用 | UI 勾选 |
| 团队协作、配置需要版本控制 | 配置文件 |
| 使用本仓库收集的第三方 skill | 先按 skill 的 INSTALL.md 安装，再尝试在 UI 或配置中引用 |

---

## 常见问题排查

### 配置不生效

- 确认 Trae 版本支持自定义 Agent 和 Skill 绑定
- 重启 Trae 后重试
- 检查配置文件 JSON 语法是否正确
- 确认 `skills` 数组中的 ID 与实际安装的一致

### 找不到配置文件路径

- 可能是当前版本不支持手动配置
- 优先使用 UI 方式
- 可尝试在 Trae 设置中导出/导入 Agent 配置，观察实际存储位置

### Skill 图标未激活

- 某些 Skill 只在特定上下文触发时才显示激活状态
- 发送一条需要该 Skill 的实际请求进行测试

### 自定义 Skill 无法被识别

- 确认 skill 目录中包含 `SKILL.md` 或 `skill.json`
- 确认目录名称与 `skills` 数组中填写的 ID 一致
- 确认 Trae 当前版本支持加载本地自定义 Skill

---

## 与 MCP Server 的区别

如果你要绑定的是 **MCP Server**（如 Excel 读写、数据库查询等），配置逻辑不同，通常需要在 `mcpServers` 字段或 MCP 设置面板中单独声明，而不是放在 `skills` 数组里。

MCP Server 示例：

```json
{
  "mcpServers": {
    "mcp-excel-reader": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "d:/working"]
    }
  }
}
```

---

## 参考文档

- 本仓库技能安装说明：各 skill 目录下的 `INSTALL.md`
- Trae 官方文档（以最新版本为准）

---

> 最后更新：2026-07-30
> 如果你发现 Trae 新版本中有变化，欢迎更新本文。
