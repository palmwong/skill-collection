# skill-designer

## 基本信息

- 来源地址：基于知乎文章整理自制（https://zhuanlan.zhihu.com/p/2066536287952286744）
- 作者/组织：本仓库整理
- 收集日期：2026-07-30
- 协议：MIT（本仓库原创内容）
- 语言/形态：Claude Code / Cursor / Trae 等支持 skills 的 IDE 可用的 SKILL.md

## 功能简介

帮助用户判断一个任务是否值得做成 Skill，并生成第一版可用的工作流卡片和最小 SKILL.md。解决"想写 Skill 但不知道从何下手"的痛点，把 Skill 设计的方法论封装成可调用工具。

## 使用场景

- 用户有一个重复任务，想判断适不适合做成 Skill
- 用户想快速生成一个 Skill 的第一版结构
- 用户想学习 Skill 设计的工作流卡片写法

## 文件说明

- `SKILL.md`：主 skill 定义，包含触发条件、执行流程、输出规范和示例

## 依赖与环境要求

- 需要支持 skill 的 Agent 环境（Claude Code / Cursor / Trae 等）
- 无需额外 API 或脚本

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 备注

- 本 skill 为原创整理，基于知乎 Skill 设计实战指南的核心方法论
- 生成的 SKILL.md 为第一版最小可用结构，后续需根据实际测试迭代
