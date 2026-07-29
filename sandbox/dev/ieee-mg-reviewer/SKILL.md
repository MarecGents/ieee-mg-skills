---
name: ieee-mg-reviewer
description: >
  IEEE Transactions 风格论文审核技能。基于 ieee-mg-share/writing/polishing 的课题组写作规范，
  审核一篇论文是否符合课题组风格。生成详细的 Review Report，逐句标注问题和重构建议。
  当用户提到"审核"、"review"、"检查论文"、"审稿"、"是否符合风格"、"写作问题"等时触发。
version: 1.0.0
author: MarecGents Group
---

# ieee-mg-reviewer — IEEE Transactions 风格论文审核

## 架构概览

| 层级 | 内容 | 加载时机 |
|------|------|----------|
| **共享层** | `../ieee-mg-share/static/` 全部规范 — 风格基准 | 始终加载 |
| **核心层** | `static/core.md` — 审核核心原则 | 始终加载 |
| **工作流层** | `static/workflow.md` + `static/report-template.md` | 始终加载 |
| **章节层** | `static/check-*.md` — 各章节审核清单 | 按审核范围加载 |

## 路由协议

### Step 0：加载审核基准
加载 `../ieee-mg-share/static/style-profile.md` 和 `../ieee-mg-share/static/terminology.md` 作为审核基准。

### Step 1：加载核心层
加载 `static/core.md` 和 `static/workflow.md`，建立审核框架。

### Step 2：确定审核范围
检测用户提供的论文范围（全文/特定章节）。

### Step 3：逐章审核
按照 `static/check-*.md` 的清单，逐章审核并标记问题。每个问题标注：
- **严重性**：🔴严重 / 🟡中等 / 🟢建议
- **类别**：结构性 / 风格性 / 语言性 / 格式性
- **位置**：精确到句
- **建议**：具体的重构方案

### Step 4：生成审核报告
按照 `static/report-template.md` 格式生成最终报告。

## 边界说明

| 本技能负责 | 本技能不负责 |
|------------|-------------|
| 论文写作规范审核 | 技术内容的真实性验证 |
| 风格符合度检查 | 抄袭检测 |
| 逐句问题标注和重构建议 | 论文排版/格式转换 |
