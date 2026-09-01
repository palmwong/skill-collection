# Logo Generator

## 基本信息

- 来源地址：https://github.com/op7418/logo-generator-skill
- 作者/组织：op7418
- 收集日期：2026-08-19
- 协议：MIT

## 功能简介

专业 SVG logo 生成 skill，生成 6+ 设计变体 + 12 种专业展示背景。核心特点：应用设计原则（极简、负空间、精确比例）、多方向探索、生产就绪的展示图（SVG 可编辑 + PNG 可直接用）。集成 Gemini 3.1 Flash Image Preview（Nano Banana）生成高端展示图，看起来像专业设计工作室出品。

## 使用场景

- 初创公司快速获得专业 logo
- 开发者做 side project 需要品牌标识
- 设计师探索初始概念
- 产品团队迭代品牌 identity

## 核心设计

**5 阶段工作流**：

1. **信息收集**：产品名、行业、核心概念、设计偏好
2. **模式匹配与 SVG 生成**：6+ 变体 + 交互式 HTML 展示 + 设计 rationale
3. **迭代细化**：选中最爱，调整参数（大小、间距、旋转），组合不同变体元素
4. **高端展示生成**：SVG 转 PNG（1024x1024），选 4 种展示风格，Nano Banana 生成展示图，最终展示网页
5. **交付**：交互式 HTML 展示页 + SVG 文件 + PNG 导出 + 展示图（4 种专业背景）

**12 种展示背景**：

- 暗色系（6 种）：The Void（纯黑+银微噪点）、Frosted、Fluid、Spotlight、Analog Liquid、LED Matrix
- 亮色系（6 种）：Editorial、Iridescent、Morning、Clinical、UI Container、Swiss Flat

## 文件说明

- `README.md`：本文件，skill 详细记录
- `INSTALL.md`：安装说明

本仓库采用"只登记 + 安装说明"方式收录，未克隆源码。

## 安装到 IDE

详见同目录下的 [INSTALL.md](./INSTALL.md)。

## 依赖与环境要求

- Claude Code / Cursor 等兼容 SKILL.md 的 agent
- Python 环境（`pip install -r requirements.txt`）
- Gemini API Key（用于 Nano Banana 展示图生成）

## 备注

- 信息来源：B 站视频 BV1YRVy6nE7q（嗨绘黄老师）+ 原仓库 README
- 视频提到的是"图叙AI"平台上的 logo 设计模板，本仓库收录的是 op7418 的开源替代品，功能定位相似但非同一产品
- 视频关键词"高级感"与本 skill 的 12 种专业展示背景 + Nano Banana 集成高度吻合
- 待验证：尚未实际运行过，依赖 Gemini API Key
