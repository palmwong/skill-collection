# skill-collection

集中存放从 GitHub 收集的各类 skill，并做统一登记、安装说明和交接。

这不是结论库，也不是火花箱。这里只收可安装、可复用的 skill 底稿：源文件、功能说明、来源地址、登记清单。

- 仓库: https://github.com/palmwong/skill-collection
- 本地路径: `D:\working\Inbox\skill-collection`
- 口令: 见下方「口令」；以本页为准
- 清单总表: `memo.md`
- 协作规范: `AGENTS.md`
- 交接状态: `handoff.md`

三个 Grok 项目（grok-notes / spark / skill-collection）共用同一套口令。去哪个库，由当前所在项目决定。`daily` 已并入 `grok-notes`。

## 口令

| 口令 | 做什么 |
| --- | --- |
| （无口令，丢文档/链接） | 只在对话里整理阅读，不写仓库、不 push |
| **归档** / **上传** | 把本轮已整理内容写入本仓库并 git push |
| **整理** | 把本库待归位项聚类、合并进正式文件；确认后 push |
| **回归** | 回顾近期条目、状态、未决；只报告，不擅自大改 |
| **同步** | `git pull` 到 `D:\working\Inbox\skill-collection` |

「上传 git」「写进仓库」视为 **归档**。

旧词只作兼容，不再作为主口令：蒸馏 / 整理上传 / 写进 grok-notes / 上传笔记 / 记一下 → **归档**；整理一下 → **整理**。

## 本库落点

归档写入的是本轮已经整理过的 skill 记录，不是聊天全文。

- 可登记的 skill：`skills/<name>/`（`README.md` + `INSTALL.md` + 源文件）+ `memo.md` 一行
- 还没验证、只记来源：`memo.md` 状态为待验证；源码未克隆也先登记
- 方法论、学习笔记等非 skill：`notes/`
- 不修改已收录 skill 的原始文件；要定制就另存副本

新增 skill 的完整步骤见 `AGENTS.md`。

## 怎么用

1. 把 skill 链接、说明、安装方式丢进本 Grok 项目，先在对话里整理阅读。
2. 可以说落盘时发 **归档** 或 **上传**。
3. 先看 `memo.md` 是否已有同名项，避免重复登记。
4. 定期发 **整理** 把待验证项补齐 `INSTALL.md` / 源码状态。
5. 定期发 **回归** 看哪些待验证、哪些该废弃。
6. 本地要对齐时发 **同步**。
