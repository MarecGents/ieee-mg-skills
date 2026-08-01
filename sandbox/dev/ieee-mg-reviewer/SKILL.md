---
name: ieee-mg-reviewer
description: >
  IEEE Transactions 风格论文审核技能。基于 ieee-mg-share/writing/polishing 的课题组写作规范，
  审核一篇论文是否符合课题组风格。生成详细的 Review Report，逐句标注问题和重构建议。
  当用户提到"审核"、"review"、"检查论文"、"审稿"、"是否符合风格"、"写作问题"等时触发。
version: 1.2.0
author: MarecGents Group
---

# ieee-mg-reviewer — IEEE Transactions 风格论文审核

## 架构概览

| 层级 | 内容 | 加载时机 |
|------|------|----------|
| **共享层** | `../ieee-mg-share/static/style-profile.md` + `terminology.md` + `quantitative-baseline.md` — 风格基准与定量口径 | 始终加载 |
| **核心层** | `static/core.md` — 审核核心原则 | 始终加载 |
| **工作流层** | `static/workflow.md` + `static/report-template.md` | 始终加载 |
| **章节层** | `static/check-*.md` — 各章节审核清单 | 按审核范围加载 |

## 路由协议

### Step 0：加载审核基准
加载 `../ieee-mg-share/static/style-profile.md`、`../ieee-mg-share/static/terminology.md` 和 `../ieee-mg-share/static/quantitative-baseline.md` 作为审核基准。**量化检查项（词数、we 密度、连接词密度、MC 次数、编号结果条数）的数值判定一律引用 quantitative-baseline.md，不得自行另设区间。**

### Step 1：加载核心层
加载 `static/core.md` 和 `static/workflow.md`，建立审核框架。

### Step 2：确定审核范围
检测用户提供的论文范围（scope 轴：full/abstract/introduction/motivation/system-model/results/conclusion），检测审核报告语言（language 轴：en/zh，默认 zh）与严格度（severity 轴：strict/normal/light，默认 normal）。**单章审核时报告只输出对应章节的检查结果与分布表，不输出其他章节。**

### Step 3：逐章审核
按照 `static/check-*.md` 的清单，逐章审核并标记问题。每个问题标注：
- **严重性**：🔴严重 / 🟡中等 / 🟢建议
- **类别**：结构性 / 风格性 / 语言性 / 格式性
- **位置**：精确到句
- **依据**：触发该问题的 check 项编号 + 对应语料模式/quantitative-baseline 数值（**必填**，保证可审计性）
- **建议**：具体的重构方案

### Step 4：生成审核报告
按照 `static/report-template.md` 格式生成最终报告（按 scope 动态裁剪章节分布表；语言按 language 轴）。

## 判断边界（v1.2.0 新增）

### 审核范围
- 本技能审核**写作规范与风格符合度**，不审核技术内容真实性、不查重、不做排版转换；
- 审核范围外的发现（如技术错误、数据可疑）在报告中单独标注"⚠ 技术问题（超出本技能范围，建议人工复核）"，不纳入风格问题统计。

### 证据不足标注
- 对无语料依据的规范（如 System Model 相关检查）在报告中标注"存疑/通用规范"；
- 无法客观判定的检查项标注"需人工复核"，不强行给结论。

### 停止/降级条件
- 用户只要求检查某章节时，不审核其他章节（scope 裁剪）；
- severity=light 时仅报告 🔴；severity=normal 报告 🔴+🟡；severity=strict 全部报告；
- 审核中遇到通篇性错误（如全文时态混乱）时，在总体评价中概括说明，不逐句重复列举。

## 边界说明

| 本技能负责 | 本技能不负责 |
|------------|-------------|
| 论文写作规范审核 | 技术内容的真实性验证 |
| 风格符合度检查 | 抄袭检测 |
| 逐句问题标注和重构建议 | 论文排版/格式转换 |
