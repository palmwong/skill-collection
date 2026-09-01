# OfficeCLI

## 基本信息

- 来源地址：https://github.com/iOfficeAI/OfficeCLI
- 作者/组织：iOfficeAI 团队
- 收集日期：2026-08-19
- 协议：Apache 2.0

## 功能简介

全球第一个专为 AI 智能体设计的 Office 套件。单一二进制、零依赖、全平台（Mac/Windows/Linux），一行代码让任何 AI 完全掌控 Word、Excel、PowerPoint。核心创新是内置从零实现的 HTML 渲染引擎，把 docx/xlsx/pptx 高保真渲染成网页或 PNG，闭合"渲染 → 看 → 改"循环，让 AI 生成文档后能自己检查排版问题。

## 使用场景

- AI 生成 PPT/Word/Excel 后自动检查排版（标题溢出、形状重叠、配色崩坏）
- CI/Docker/无头服务器上的自动化文档生成
- 企业工作流中 AI 操作真实 Office 格式（不是 HTML 替代品）
- Excel 公式写入即自动求值、一条命令生成数据透视表
- 模板合并：设计一次，填充 N 次

## 核心设计

**三层命令**：

| 层级 | 作用 | 使用频率 |
|---|---|---|
| L1 读取 | 查看文档结构、内容 | 九成时间 |
| L2 DOM 操作 | 增删改元素 | 九成时间 |
| L3 原始 XML | 深度定制 | 少数情况 |

每个元素有稳定路径（如 `/slide[1]/shape[1]`），AI 用路径寻址不用懂 XML 命名空间。错误返回结构化错误码 + 修正建议，AI 自己纠错。

**Excel 能力**：350+ 函数写入即自动求值，不用切回 Office 重算。

## 文件说明

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：安装说明

本仓库采用"只登记 + 安装说明"方式收录，未克隆源码。原仓库为完整工程（单一二进制 + skill 文件 + SDK + 插件）。

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 依赖与环境要求

- 单一二进制，无需装 Office，零依赖
- 支持 Claude Code、Cursor、Windsurf、GitHub Copilot 等（通过 `officecli install` 自动检测安装 skill）
- 也提供 GUI 桌面应用 AionUi（https://github.com/iOfficeAI/AionUi）

## 备注

- 信息来源：用户提供的视频文案 + 原仓库 README
- 与本仓库其他 skill 的关系：bento-slides 是 HTML 演示文稿（文件即软件），OfficeCLI 是操作真实 Office 格式；lieflat-charts 是数据可视化图表，OfficeCLI 的 Excel 图表是 Office 原生图表
- 视频观点：AI 智能体从对话工具进化成数字员工，需要手和眼。OfficeCLI 不做编辑器，做的是 AI 操控 Office 的标准接口
- 待验证：尚未实际安装运行过
