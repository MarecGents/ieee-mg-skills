---
name: ieee-mg-share
description: >
  IEEE Transactions 风格学术写作共享层。本技能是 ieee-mg-writing、ieee-mg-polishing、ieee-mg-reviewer 的前置共享依赖，
  提供统一的课题组风格画像、术语规范、句式库、逻辑连接词和章节结构定义。
  所有依赖此共享层的技能在路由 Step 0 中自动加载本技能的内容。
  当用户需要查询写作风格规范、术语标准、学术句式或逻辑连接词用法时触发。
version: 1.2.0
author: MarecGents Group
---

# ieee-mg-share — MarecGents 课题组共享学术风格层

## 角色定位

本技能是 **ieee-mg-writing**、**ieee-mg-polishing** 和 **ieee-mg-reviewer** 的**前置共享依赖层**。它不是独立使用的技能，而是被其他技能在路由协议 Step 0 中自动加载的公共组件。

### 架构位置

```
ieee-mg-share/         ← 共享层（本技能）
    ↙        ↓        ↘
writing     polishing    reviewer
(写作)      (润色)       (审核)
```

## 共享内容清单

| 文件 | 内容 | 被引用方 |
|------|------|----------|
| `static/style-profile.md` | 全局风格画像（正式度、句式、时态、高频词汇、连接词、数学规范） | writing, polishing, reviewer |
| `static/terminology.md` | 术语规范（缩略语规则、核心术语、信道模型、数学符号） | writing, polishing, reviewer |
| `static/expression-bank.md` | 通用句式库（引用、空白、贡献、结果、过渡等7类句式） | writing, polishing |
| `static/logic-connectors.md` | 逻辑连接词详细指南（因果/转折/递进/举例/结论，含频率和例句） | writing, polishing |
| `static/section-architecture.md` | 各章节标准结构定义 | writing, polishing |
| `static/common-errors.md` | 常见语言错误与纠正 | polishing |
| `static/paragraph-rhythm.md` | 段落节奏与过渡指南 | polishing |
| `static/quantitative-baseline.md` | 定量分析基线参考（词数/密度/频率权威口径） | writing, polishing, reviewer |

## 使用方法

### 作为前置依赖（自动加载）

其他技能的 SKILL.md 在路由协议的 **Step 0** 中加载本技能：

```markdown
### Step 0：加载共享层
立即加载 `../ieee-mg-share/static/style-profile.md` 和 `../ieee-mg-share/static/terminology.md`，
建立课题组全局风格画像和术语规范。
```

### 按需引用

在 manifest.yaml 中定义 fragment 指向本技能的 static/ 文件：

```yaml
fragments:
  style-profile: ../ieee-mg-share/static/style-profile.md
  terminology: ../ieee-mg-share/static/terminology.md
```

## 边界说明

| 本技能负责 | 本技能不负责 |
|------------|-------------|
| 提供统一的风格基准和术语标准 | 论文各章节的具体写作指导（由 ieee-mg-writing 负责） |
| 提供通用句式库和连接词指南 | 论文语言润色和修改（由 ieee-mg-polishing 负责） |
| 维护课题组独有的学术表达习惯 | 论文内容的审核和评估（由 ieee-mg-reviewer 负责） |
| 定义章节标准结构模板 | 原始语料的更新和管理（由 ieee-mg-database 负责） |

## 使用边界（v1.2.0 新增）

本层数据源自 21 篇课题组论文语料蒸馏，使用时请注意以下边界：

### 何时该用 / 不该用本层数据

- ✅ **该用**：目标论文属于 IEEE Trans/期刊风格的 NOMA/RIS/STARS、物理层安全、隐蔽通信等本语料覆盖领域时，本层风格画像、术语、句式、连接词可直接作为基准。
- ❌ **不该用**：目标期刊/会议风格与本语料差异大（如 Nature 系、计算机顶会）、主题超出语料领域、或语料明确无对应数据时，不得将本层特征冒充为"语料实测"。

### 数据缺失降级策略

- 语料无对应章节数据（如 **System Model**：语料仅含 Abstract/Introduction/Numerical Results/Conclusion 四部分）时，相关模板须标注"外部通用知识，非语料蒸馏"，不得写成语料特征。
- static 文件中的频次/占比均为 grep 行级计数的估算值（部分为课题组印象分，已逐条标注），引用时注明口径；与目标稿件实测冲突时以稿件实测为准。

### conf / mag 适配

- static 内容以 **journal**（IEEE Transactions）为基准；**conf** 场景篇幅更紧凑（摘要/引言压缩、贡献列点简短）；**mag** 场景可含教程式/综述式说明。适配分支不改变硬约束（缩略形式禁令、时态主框架等）。

### 语料与目标期刊规范冲突

- 当语料习惯与目标期刊官方规范（如 IEEE 作者指南）冲突时，**以目标期刊规范为准**，并在交付物中标注差异（如"语料习惯 X，已按 IEEE 规范改为 Y"）。

## 设计原理

1. **单一真实来源**：所有技能共享同一份风格画像和术语规范，修改一处即同步更新所有技能
2. **避免重复维护**：约四成内容在 writing 和 polishing 间共享（维护估算，未做精确比对），集中存放减少冗余
3. **一致性保证**：writing（写作）、polishing（润色）、reviewer（审核）三个环节使用完全相同的风格基准
4. **渐进式加载**：核心文件（style-profile, terminology, quantitative-baseline）始终加载，其他文件按需引用
