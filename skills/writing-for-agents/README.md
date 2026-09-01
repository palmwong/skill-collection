# Writing for Agents

## 基本信息

- 来源地址：https://github.com/mattpocock/skills（skills/productivity/writing-for-agents/）
- 作者/组织：Matt Pocock（@mattpocockuk）
- 收集日期：2026-08-19
- 协议：MIT

## 功能简介

元方法论 skill：教你怎么写 agent 能可靠执行的文档（skill、AGENTS.md、CLAUDE.md 等）。核心洞察：同样的写作原则适用于所有 agent 消费的文档，因为 agent 每次运行走同样的 process，而不是产生同样的输出。涵盖 context pointer、信息层级、完成标准、引导词、修剪纪律等完整框架。

## 使用场景

- 写新 skill 时判断内容该放 in-file step、in-file reference 还是 disclosed reference
- 优化 AGENTS.md / CLAUDE.md 的 context load
- 设计 skill 的 description（context pointer 的措辞）
- 判断何时该拆分文档（by sequence / by invocation）
- 用引导词（leading words）替代重复表述，减少 token 消耗
- 删除文档中的 no-op 和 sediment

## 核心框架

**两个预算**：
- Context load：常驻 agent 上下文的内容成本，越少越好
- Cognitive load：人类记住文档体系的成本，是人类判断力的价格

**信息层级**（从高到低）：
1. In-file step：agent 按顺序执行的动作
2. In-file reference：按需查阅的定义、规则
3. Disclosed reference：推到外部文件，通过 pointer 按需加载

**完成标准两个属性**：Clarity（可区分完成/未完成）+ Demand（要求的工作量）

**引导词**：模型预训练中已有的紧凑概念，作为 token 重复锚定行为区域。否定是失败模式，用正面表述。

**修剪**：single source of truth、environment 也是 source of truth、relevance 检查、no-op 删除。

## 文件说明

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：安装说明

本仓库采用"只登记 + 安装说明"方式收录，未克隆源码。源文件为 mattpocock/skills 仓库中的 skills/productivity/writing-for-agents/SKILL.md + SKILL-MECHANICS.md。

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 依赖与环境要求

- Claude Code / Codex 等兼容 SKILL.md 的 coding agent
- 纯方法论，无额外依赖

## 备注

- 与本仓库 skill-designer 的关系：skill-designer 是"要不要做 skill"，writing-for-agents 是"怎么做 skill"
- 与本仓库其他 Matt Pocock skill（grill-me、teach、handoff）的关系：writing-for-agents 是写这些 skill 的方法论
- 源文件还包含 SKILL-MECHANICS.md（frontmatter、invocation choice、router skills），本 README 未覆盖，需要时查阅原仓库
- 待验证：尚未实际用于写 skill
