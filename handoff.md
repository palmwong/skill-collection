# 交接文档（Handoff）

## 仓库用途

集中管理从 GitHub 收集的各类 skill，包含 skill 源文件、功能说明、来源地址和登记清单。

## 当前状态

- 更新日期：2026-08-19
- 已收录 skill 数量：14（其中 understand-anything、lieflat-charts、bento-slides、teach、officecli、logo-generator、writing-for-agents、compound-engineering 为只登记，状态：待验证）
- 已收录清单：
  - cangjie-skill（袋鼠帝）：元 skill，把书/长视频/播客蒸馏成可调用 skills，RIA-TV++ 流水线，详见 skills/cangjie-skill/README.md
  - ai-agent-book（李博杰）：开源图书《深入理解 AI Agent：设计原理与工程实践》+ 93 个配套实验项目，详见 skills/ai-agent-book/README.md
  - guizang-material-illustration（op7418）：Claude Code / Codex 配图 Skill，生成带中文标签的歸藏材质插画，详见 skills/guizang-material-illustration/README.md
  - skill-designer（本仓库整理）：基于知乎 Skill 设计实战指南，帮助判断任务是否值得 Skill 化并生成第一版 SKILL.md，详见 skills/skill-designer/README.md
  - consultant（用户在其他对话中创建）：咨询顾问协作模式，通过仪式化协作防止上下文漂移，详见 skills/consultant/README.md
  - grill-me（用户自建）：压力测试面试 skill，通过连续追问暴露设计/计划中的假设、理清决策树，详见 skills/grill-me/README.md
  - understand-anything（Egonex-AI / Lum1104）：Claude Code 插件，多 agent 流水线把代码库构建成知识图谱 + 交互式 dashboard，只登记未收录源码，详见 skills/understand-anything/README.md
  - lieflat-charts（larashero3-dotcom）：数据可视化 skill，48 个图表模板 + 四套色彩体系，说人话出专业图表，只登记未收录源码，详见 skills/lieflat-charts/README.md
  - bento-slides（nyblnet）：单文件 HTML 演示工具 + Claude Code skill，文件即软件，AI 直接编辑结构化 JSON 生成演示文稿，只登记未收录源码，详见 skills/bento-slides/README.md
  - teach（Matt Pocock）：stateful 教学 skill，把 AI agent 变成私人老师，跨会话按最近发展区定制课程，只登记未收录源码，详见 skills/teach/README.md
  - officecli（iOfficeAI）：专为 AI 智能体设计的 Office 套件，单一二进制零依赖全平台，内置 HTML 渲染引擎闭合"渲染→看→改"循环，只登记未收录源码，详见 skills/officecli/README.md
  - logo-generator（op7418）：专业 SVG logo 生成 skill，6+ 设计变体 + 12 种专业展示背景，集成 Gemini Nano Banana，只登记未收录源码，详见 skills/logo-generator/README.md
  - writing-for-agents（Matt Pocock）：元方法论 skill，教你怎么写 agent 能可靠执行的文档，涵盖 context pointer、信息层级、完成标准、引导词、修剪纪律，只登记未收录源码，详见 skills/writing-for-agents/README.md
  - compound-engineering（Every Inc）：AI 原生工程哲学插件，80% 精力投入计划与审查、20% 用于执行与沉淀，四步循环 Plan→Work→Review→Compound，只登记未收录源码，详见 skills/compound-engineering/README.md
- 已完成的工作：
  - 建立目录结构：`skills/` 子文件夹
  - 创建 `memo.md`（skill 登记总表）
  - 创建 `AGENTS.md`（协作规范）
  - 创建 `skills/_template.md`（单个 skill 记录模板，含安装说明占位）
  - 收录 `skills/cangjie-skill/`（README.md + INSTALL.md）
  - 收录 `skills/ai-agent-book/`（README.md + INSTALL.md）
  - 收录 `skills/guizang-material-illustration/`（README.md + INSTALL.md）
  - 创建 `trae-custom-agent-skill-guide.md`（Trae 自定义 Agent 绑定 Skill 指南）
  - 在 `AGENTS.md` 和 `memo.md` 中增加了 Trae 指南链接
  - 创建 `notes/skill-design-guide.md`（知乎 Skill 设计实战指南整理）
  - 收录 `skills/skill-designer/`（README.md + INSTALL.md + SKILL.md），将知乎 Skill 设计方法论沉淀为可用 skill
  - 在 `memo.md` 中登记 skill-designer
  - 收录 `skills/grill-me/`：将散落的 `skills/grill-me.md` 迁移到子目录，修复 SKILL.md 中 ``\---`` 为 ``---``，补齐 README.md 与 INSTALL.md，并在 `memo.md` 登记
  - 2026-08-09：仓库从 `d:\working\Skill` 迁移到 `c:\Users\2027\Documents\Skill`，批量替换 AGENTS.md / memo.md / skills\_template.md / 各 skill 的 INSTALL.md / consultant 的 README.md 中的旧路径，原文件已备份至 `history/`（时间戳 20260809-1135）
  - 2026-08-14：收录 `skills/understand-anything/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证）
  - 2026-08-18：收录 `skills/lieflat-charts/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证），信息来源为 B 站视频 BV1DiGG6JEAo + 原仓库 README
  - 2026-08-19：收录 `skills/bento-slides/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证），信息来源为 B 站视频 BV1tebi6oEYV + 原仓库 README
  - 2026-08-19：收录 `skills/teach/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证），源文件来自 mattpocock/skills 仓库的 skills/productivity/teach/，培训文档见 notes/teach-skill-training.md
  - 2026-08-19：收录 `skills/officecli/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证），信息来源为用户提供的视频文案 + 原仓库 README
  - 2026-08-19：收录 `skills/logo-generator/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证），信息来源为 B 站视频 BV1YRVy6nE7q + 原仓库 README，注意视频实际指向图叙AI平台模板，本仓库收录的是 op7418 的开源替代品
  - 2026-08-19：收录 `skills/writing-for-agents/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证），源文件来自 mattpocock/skills 仓库的 skills/productivity/writing-for-agents/
  - 2026-08-19：收录 `skills/compound-engineering/`（README.md + INSTALL.md，只登记未克隆源码），在 `memo.md` 登记（状态：待验证），信息来源为原仓库 README + Every.to 官方指南 + 第三方评测

## 待办事项

- 开始收集更多 skill，按 `AGENTS.md` 中的流程登记
- 收集到一定数量后，可考虑按类别（如开发、写作、办公、可视化）在 `skills/` 下增设分类子目录
- 后续每个 skill 都必须包含 `INSTALL.md`，说明如何一键安装到常用 IDE
- 根据实际使用情况，验证和更新 `trae-custom-agent-skill-guide.md` 中的路径与字段

## 上手指引

1. 先读 `AGENTS.md` 了解目录结构和新增 skill 的流程
2. 查看 `memo.md` 了解已收录的 skill 清单
3. 新增 skill 时复制 `skills/_template.md` 填写详细记录
