# cangjie-skill（仓颉）

## 基本信息

- 来源地址：https://github.com/kangarooking/cangjie-skill
- 作者/组织：袋鼠帝 kangarooking（AI 博主、独立开发者，公众号「袋鼠帝 AI 客栈」主理人）
- 收集日期：2026-07-30
- 协议：MIT
- 语言/形态：Prompt 定义型 skill（Markdown 为主，Python 辅助脚本）

## 功能简介

一个"元 skill"：把书籍、长视频转写、播客文字稿、课程、访谈等长内容中沉淀的方法论，蒸馏成一组原子化、可被 AI agent 在真实场景中调用的 skill 工具包。解决"看了很多但用不起来"的痛点——不是做摘要，而是结构化复用。

## 核心方法论：RIA-TV++ 流水线

- 阶段 0：Adler 整书理解，产出 BOOK_OVERVIEW.md（结构/解释/批判/应用四步）
- 阶段 1：5 个 sub-agent 并行提取（框架、原则、案例、反例、术语）
- 阶段 1.5：三重验证筛选（跨域佐证、预测力、独特性），通过率约 25-50%
- 阶段 2：RIA++ 构造 skill，每个 skill 含 R/I/A1/A2/E/B 六段
- 阶段 3：Zettelkasten 链接，生成 INDEX.md 引用图和 GLOSSARY.md
- 阶段 4：压力测试（含诱饵题、跨 skill 混淆测试），输出 darwin-skill 兼容的 test-prompts.json
- 阶段 5：交付，生成 DIGEST.md 精华长文并安装到 Claude Code / Cursor 的 skills 目录

RIA 来自赵周《这样读书就够了》便签拆书法；TV 即三重验证；++ 指面向 agent 执行的 E（可执行步骤）+ B（边界与盲点）扩展。

## 使用场景

- 把一本书（如《穷查理宝典》《影响力》）拆成可调用的决策/写作/判断 skill
- 把 B 站/YouTube 长视频、播客、课程的字幕转写蒸馏成 skill（建议搭配作者的 video-downloader skill 先拿转写文本）
- 产出可直接喂给 darwin-skill 做自动进化

## 边界（明确不做的）

- 不做书摘、读后感、简单摘要
- 不做作者人设角色扮演（那是 nuwa-skill 的职责）
- 不凭记忆拆书——没有文本来源会停下来问用户要

## 仓库结构（源仓库）

- `SKILL.md`：元 skill 完整执行规范（触发条件、输入要求、输出结构、质量红线）
- `methodology/`：各阶段方法论文档（00-overview 至 07-stage5-deliver）
- `extractors/`：5 个并行提取器的 prompt 定义
- `templates/`：SKILL.md / INDEX.md / BOOK_OVERVIEW.md / DIGEST.md / test-prompts.json 模板

## 生态定位

- nuwa-skill：蒸馏人（思维方式、表达 DNA）
- cangjie-skill（本项目）：蒸馏书/长内容（方法论、框架、原则）
- darwin-skill：进化任意 skill（本项目的 test-prompts.json 与其格式兼容）

## 已生成的衍生 skill packs（部分）

官方已蒸馏 15+ 个 skill 包，包括：巴菲特致股东的信（20 个）、《认知红利》（15 个）、段永平投资问答录（15 个）、《影响力》（12 个）、《毛泽东选集》（25 个）、《黄帝内经》（22 个）、吴恩达《AI for Everyone》视频课（25 个）等；另有 qbdx-hub、book2startup、book2skill 等社区贡献的蒸馏仓库。

## 依赖与环境要求

- 需要支持 sub-agent 并行的 agent 环境（Claude Code / Cursor 等）；不支持时可降级为串行执行
- 需要用户提供内容文本来源（PDF/EPUB/TXT/字幕/转写稿）
- 蒸馏视频需先自行获取转写文本

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 备注

- 本地仅归档本说明，未克隆源仓库；如需使用，克隆源仓库后按 SKILL.md 执行
- 质量红线值得借鉴：每个 skill 必须通过三重验证、含诱饵测试、description 必须明确触发条件
