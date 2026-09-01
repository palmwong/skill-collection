# Teach

## 基本信息

- 来源地址：https://github.com/mattpocock/skills（skills/productivity/teach/）
- 作者/组织：Matt Pocock（@mattpocockuk）
- 收集日期：2026-08-19
- 协议：MIT

## 功能简介

Stateful 教学 skill，把 AI agent 变成私人老师。在当前目录建立教学工作区（mission、resources、HTML 课程、learning records、glossary、reference），跨会话记住学习进度，按最近发展区（ZPD）精准定制每一课。与普通 chat 的本质区别：所有状态存文件系统，agent 记得你学到哪、卡在哪。

## 使用场景

- 长期学习任何技能或知识领域（视频演示：从零学会还原魔方）
- 跨会话学习，agent 根据进度诊断并定制下一课
- 团队新人 onboarding 到代码库（MISSION = 目标状态，lessons = 学习路径）
- 需要引用高可信资源而非 agent 参数化知识的场景
- 希望课程可交互（测验、模拟器、图解）而非纯文本

## 教学工作区结构

```
当前目录/
├── MISSION.md              # 学习目标（为什么学）
├── RESOURCES.md            # 高可信参考资料清单
├── NOTES.md                # agent 记事本
├── GLOSSARY.md             # 术语表
├── reference/*.html        # 参考文档（速查表、算法、语法）
├── lessons/*.html          # 课程（核心产出，编号递增）
├── learning-records/*.md   # 学习记录（编号递增）
└── assets/*                # 可复用组件（样式表、测验部件等）
```

## 核心设计取舍

- **Stateful（/teach）**：状态存文件系统，学习需要跟踪进度、计算 ZPD
- **Stateless（/grill-me）**：每次会话独立，追问不需要历史反而更彻底

## 教学哲学

- 深度学习三要素：Knowledge（高可信资源）、Skills（交互课程）、Wisdom（社区互动）
- 流畅强度 vs 存储强度：通过提取练习、间隔、交错建立长期保持
- 最近发展区：每节课"刚好被挑战到"
- 知识教学：困难是敌人（吃掉工做记忆）；技能教学：困难是工具（费力提取建立存储强度）
- 测验设计：选项单词数/字符数相同，不给格式线索

## 文件说明

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：安装说明

本仓库采用"只登记 + 安装说明"方式收录，未克隆源码。源文件为 mattpocock/skills 仓库中的 skills/productivity/teach/SKILL.md + 3 个格式模板。

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 依赖与环境要求

- Claude Code / Codex 等兼容 SKILL.md 的 coding agent
- 课程为 HTML 文件，浏览器打开即可

## 备注

- 完整培训文档（含全部格式模板和教学哲学）：[notes/teach-skill-training.md](../../notes/teach-skill-training.md)
- 配套视频：B 站 BV1xK3h6fE7a（中英字幕）/ YouTube 原版
- 作者介绍页：https://aihero.dev/s/1T2OM1
- 与本仓库 grill-me 的关系：同一作者，grill-me 是 stateless 追问，teach 是 stateful 教学，互补
- 待验证：尚未实际运行过 /teach
