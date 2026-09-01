# Skill 收集清单（Memo）

本文件登记从 GitHub 收集到的各类 skill，包含名称、地址、功能简介等核心信息。
新增 skill 时，请先复制 `skills/_template.md` 创建该 skill 的详细记录，再在下表登记一行。

## 清单总览

| 名称 | 来源地址 | 功能简介 | 本地目录 | 收集日期 | 状态 |
|---|---|---|---|---|---|
| （示例）example-skill | https://github.com/user/repo | 示例：用于演示登记格式 | skills/example-skill/ | 2026-07-30 | 已收录 |
| cangjie-skill | https://github.com/kangarooking/cangjie-skill | 元 skill：把书/长视频/播客的方法论蒸馏成可调用的 AI skills（RIA-TV++ 流水线） | skills/cangjie-skill/ | 2026-07-30 | 已收录 |
| ai-agent-book | https://github.com/bojieli/ai-agent-book | 开源图书《深入理解 AI Agent：设计原理与工程实践》+ 93 个配套实验项目 | skills/ai-agent-book/ | 2026-07-30 | 已收录 |
| guizang-material-illustration | https://github.com/op7418/guizang-material-illustration | Claude Code / Codex 配图 Skill：把文章/概念/图表转成带中文标签的歸藏材质插画 | skills/guizang-material-illustration/ | 2026-07-30 | 已收录 |
| skill-designer | 本仓库整理（基于知乎 Skill 设计实战指南） | 帮助判断任务是否值得做成 Skill，并生成第一版工作流卡片和最小 SKILL.md | skills/skill-designer/ | 2026-07-30 | 已收录 |
| consultant | 用户在其他对话中创建，源文件 `c:\Users\2027\Documents\Skill\consultant_SKILL.md` | 咨询顾问协作模式：通过开工/挂起/换脑/记教训/入库仪式，把项目状态外化到文件，防止上下文漂移 | skills/consultant/ | 2026-07-30 | 已收录 |
| grill-me | 用户在其他对话中创建，原始文件 `skills/grill-me.md` | 压力测试面试 skill：通过连续追问暴露设计/计划中的假设、理清决策树，直到达成共识 | skills/grill-me/ | 2026-08-09 | 已收录 |
| understand-anything | https://github.com/Egonex-AI/Understand-Anything | Claude Code 插件：多 agent 流水线把代码库构建成知识图谱 + 交互式 dashboard 可视化探索（只登记，未收录源码） | skills/understand-anything/ | 2026-08-14 | 待验证 |
| lieflat-charts | https://github.com/larashero3-dotcom/lieflat-charts | 数据可视化 skill：48 个图表模板 + 设计语法，单色/青瓷蓝/椰林绿/编辑部红四套色彩体系，说人话出专业图表（只登记，未收录源码） | skills/lieflat-charts/ | 2026-08-18 | 待验证 |
| bento-slides | https://github.com/nyblnet/bento | 单文件 HTML 演示工具 + Claude Code skill：文件即软件（560KB 装下编辑器/查看器/演示器），AI 直接编辑结构化 JSON 生成演示文稿（只登记，未收录源码） | skills/bento-slides/ | 2026-08-19 | 待验证 |
| teach | https://github.com/mattpocock/skills | stateful 教学 skill：把 AI agent 变成私人老师，在当前目录建教学工作区（mission/resources/lessons/learning-records），跨会话按最近发展区定制课程（只登记，未收录源码） | skills/teach/ | 2026-08-19 | 待验证 |
| officecli | https://github.com/iOfficeAI/OfficeCLI | 专为 AI 智能体设计的 Office 套件：单一二进制零依赖全平台，内置 HTML 渲染引擎让 AI 生成文档后能自己检查排版，闭合"渲染→看→改"循环（只登记，未收录源码） | skills/officecli/ | 2026-08-19 | 待验证 |
| logo-generator | https://github.com/op7418/logo-generator-skill | 专业 SVG logo 生成 skill：6+ 设计变体 + 12 种专业展示背景，集成 Gemini Nano Banana 生成高端展示图（只登记，未收录源码） | skills/logo-generator/ | 2026-08-19 | 待验证 |
| writing-for-agents | https://github.com/mattpocock/skills | 元方法论 skill：教你怎么写 agent 能可靠执行的文档（skill、AGENTS.md、CLAUDE.md），涵盖 context pointer、信息层级、完成标准、引导词、修剪纪律（只登记，未收录源码） | skills/writing-for-agents/ | 2026-08-19 | 待验证 |
| compound-engineering | https://github.com/EveryInc/compound-engineering-plugin | AI 原生工程哲学插件：80% 精力投入计划与审查、20% 用于执行与沉淀，四步循环 Plan→Work→Review→Compound，让每个工程单元都比上一个更容易（只登记，未收录源码） | skills/compound-engineering/ | 2026-08-19 | 待验证 |

## 登记说明

- 名称：skill 的正式名称，与 `skills/` 下的子文件夹同名
- 来源地址：GitHub 仓库或具体 skill 文件的 URL
- 功能简介：一句话说明该 skill 解决什么问题
- 本地目录：该 skill 在本仓库中的存放位置
- 状态：已收录 / 待验证 / 已废弃

## 如何使用收录的 skill

每个 skill 的安装方式略有不同（取决于源仓库的交付形式和目标 IDE）。具体安装步骤请查看该 skill 文件夹下的 `README.md` 中的「安装到 IDE」章节，或同目录下的 `INSTALL.md`，例如 [cangjie-skill/INSTALL.md](file:///c:/Users/2027/Documents/Skill/skills/cangjie-skill/INSTALL.md)。

通用原则是：把 skill 目录复制或符号链接到 IDE 的 skill 目录（Claude Code 为 `.claude/skills/` 或 `~/.claude/skills/`，Cursor 为 `.cursor/skills/`），然后重启 IDE。

### 在 Trae 中为自定义 Agent 绑定 Skill

如果你想在 Trae 的自定义 Agent 中默认加载某个 skill，可参考 [trae-custom-agent-skill-guide.md](file:///c:/Users/2027/Documents/Skill/trae-custom-agent-skill-guide.md)。该文档整理了 UI 勾选、配置文件、`skills` 字段和 MCP Server 的区别，以及常见问题排查。
