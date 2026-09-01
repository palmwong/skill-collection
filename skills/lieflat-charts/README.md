# Lieflat Charts

## 基本信息

- 来源地址：https://github.com/larashero3-dotcom/lieflat-charts
- 作者/组织：larashero3-dotcom（在 moxt.ai 制作）
- 收集日期：2026-08-18
- 协议：PolyForm 非商业（个人学习和内容创作友好，商用需确认）

## 功能简介

遵循 Agent Skills 格式的数据可视化与报告生成 skill。不是传统 JS 图表库，而是一套设计规则文档 + 48 个图表模板，装进 Claude Code、Codex 等兼容 SKILL.md 的 AI agent 后，用自然语言描述需求即可生成专业图表。核心理念：图表的好看不在工具在品味——先判数据形状再选图型，明度即数据，一张图只讲一件事。

## 使用场景

- 研究者做论文配图（Lupi 编辑叙事型，细线点阵慢读）
- 运营做公众号年报、周报汇报（Glance 快速判断型，粗柱大数字）
- 文科做历史数据可视化
- 明确要求时生成整页 HTML 报告（12 套中英文模板：调研报告、财报、dashboard、海报、年度生活记录等）
- 复杂关系数据用交互大图（力导向星系图、路径图、多段流向图）

## 视觉体系

四种"阅读速度"模板：

| 类型 | 特点 | 适用场景 |
|---|---|---|
| Lupi（编辑叙事型） | 细线、点阵、逐条记录、大量留白 | 论文、长文、年报 |
| Glance（快速判断型） | 粗柱、大数字、色块、清晰排序 | 周报、汇报、dashboard |
| Basics（基础编辑型） | 柱/线/面积/环形等基础图型 + 编辑排版 | 结构简单或数据量少的内容 |
| Interactive（交互大图） | 网络、路径、多段流向 | 复杂关系数据 |

色彩系统：Mono 黑白灰为保底方案，另有青瓷蓝（有序单序列）、椰林绿（少量无序类目）、编辑部红（受控视线落点）三种彩色预设，agent 按数据结构和场景自动选择，不明确时回到 Mono。用户提供品牌色时可建 custom 色板。同一份 HTML 只用一种色彩系统。

## 设计哲学（四条）

1. 柱状图绝对不断轴（长度必须等于数值，断轴就是撒谎）
2. 标题写结论，不写图型名
3. 一张图只讲一件事
4. 默认优先推荐慢读的 Lupi，快读的 Glance 是降级方案

## 文件说明

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：一键安装到 Claude Code 的说明

本仓库采用"只登记 + 安装说明"方式收录，未克隆源码。原仓库结构：SKILL.md（主定义）、templates/（48 个图表模板）、agents/、examples/、scripts/、catalog.md（模板目录）、report-catalog.md（报告模板目录）、mono-tokens.js / color-presets.js（色彩系统）。

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 依赖与环境要求

- 兼容 SKILL.md 的 AI agent：Claude Code、Codex、moxt 等
- 生成物为 HTML，浏览器打开即可查看

## 备注

- 信息来源：B 站视频 BV1DiGG6JEAo（UP 主"AI技术投降派"）+ 原仓库 README
- 视频发布于 2026-08-02，仓库最新版已增加彩色模式和报告模式，比视频内容更丰富
- 与本仓库 guizang-material-illustration 的差异：歸藏是概念插画，lieflat-charts 是数据图表，互补不冲突
- 待验证：尚未在实际场景中生成过图表
