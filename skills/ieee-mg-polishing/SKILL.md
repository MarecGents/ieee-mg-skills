---
name: ieee-mg-polishing
description: >
  IEEE Transactions 风格学术润色技能。面向 B5G/6G 无线移动通信、非正交多址接入（NOMA）、可重构复杂天线系统等方向。
  使用此技能对论文各章节进行语言润色和学术表达优化：
  - Abstract / Introduction / Motivation / System Model / Numerical Results / Conclusion
  也支持全文整体润色和投稿前的终稿审校。
  当用户提到"润色"、"修改语言"、"改进表达"、"polish"、"proofread"、"审校"等时触发。
version: 1.1.0
author: MarecGents Group
---

# ieee-mg-polishing — IEEE Transactions 风格学术润色

## 架构概览

本技能采用 **静态层（static/）+ 动态层（manifest.yaml）** 的分层架构：

| 层级 | 内容 | 加载时机 |
|------|------|----------|
| **共享层** | `../ieee-mg-share/static/style-profile.md` + `terminology.md` — 全局风格与术语 | 始终加载 |
| **核心层** | `static/core.md` — 润色核心原则 | 始终加载 |
| **工作流层** | `static/workflow.md` — 标准润色流程 | 始终加载 |
| **章节层** | `static/section-*.md` — 各章节润色规范 | 按检测的 `section` 轴加载 |


## 路由协议

按照以下 6 步流程执行：

### Step 0：加载共享层
立即加载 `../ieee-mg-share/static/style-profile.md` 和 `../ieee-mg-share/static/terminology.md`，
建立课题组全局风格画像和术语规范。共享层的内容被 ieee-mg-writing 和 ieee-mg-polishing 共同使用。

### Step 1：加载核心层
立即加载 `static/core.md`，建立本技能的润色核心原则。

### Step 2：检测请求轴
从用户请求中检测以下轴的值：

| 轴（Axis） | 检测目标 | 检测提示 |
|------------|----------|----------|
| `paper_type` | journal / conf / mag | 论文类型？默认 journal |
| `section` | abstract / introduction / motivation / system-model / numerical-results / conclusion / full | 需要润色哪个章节？默认 full（全文） |
| `language` | en / zh | 当前文本语言？默认 en |
| `polish_level` | light / moderate / deep | 润色深度？默认 moderate |

**润色深度说明：**
- **Light**: 仅修正语法错误、拼写错误和明显的表达问题，保留原意的最大程度
- **Moderate**: 在修正语法错误的基础上，优化句式结构、改进用词、增强逻辑连贯性
- **Deep**: 全面重写，在保留核心信息的前提下优化学术风格、提升技术表达的精确度和专业性

### Step 3：加载匹配片段
根据检测到的轴值，加载对应的润色规范：

- 如果 `section = abstract` → 加载 `static/section-abstract.md`
- 如果 `section = introduction` → 加载 `static/section-introduction.md`
- 如果 `section = motivation` → 加载 `static/section-motivation.md`
- 如果 `section = system-model` → 加载 `static/section-system-model.md`
- 如果 `section = numerical-results` → 加载 `static/section-numerical-results.md`
- 如果 `section = conclusion` → 加载 `static/section-conclusion.md`
- 如果 `section = full` → 依次加载所有章节润色规范

### Step 4：执行润色
按照以下优先级处理：
1. **核心原则**（`core.md`）优先 —— 所有润色必须符合核心原则
2. **章节规范**（`section-*.md`）其次 —— 遵循该章节的润色重点
3. **用户具体指示** —— 在规范基础上满足用户的特殊要求
4. **课题组风格** —— 从课题组语料库 `sandbox/dev/ieee-mg-database/` 中提取的风格特征（如可用）

### Step 5：输出润色结果
输出格式：
1. **修改后全文** — 应用所有修改的完整版本
2. **修改说明摘要** — 列出主要修改类型和数量（可选）
3. **重点修改标注** — 对关键修改给出简短的修改理由（可选）

## 边界说明

| 本技能负责 | 本技能不负责 |
|------------|-------------|
| 语言表达和学术风格的优化 | 技术内容的真实性验证 |
| 语法、拼写、标点的修正 | 实验数据的修改 |
| 句子结构和逻辑连贯性的改进 | 论文内容的核心修改（由 ieee-mg-writing 负责） |
| 学术用词的专业化提升 | 引用格式的修正（由 ieee-mg-citation 负责） |

## 设计原理

1. **分级润色**：根据用户需求提供不同深度的润色，从轻度修正到全面优化
2. **章节定制**：不同章节有不同润色重点（如 Abstract 侧重精炼，Introduction 侧重逻辑）
3. **风格保持**：在提升表达质量的同时，保留作者的核心表述和学术风格
4. **课题组导向**：优先采用课题组在 B5G/6G、NOMA、天线系统领域的术语和表达习惯
