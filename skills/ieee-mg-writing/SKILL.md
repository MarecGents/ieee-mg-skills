---
name: ieee-mg-writing
description: >
  IEEE Transactions 风格学术写作技能。面向 B5G/6G 无线移动通信、非正交多址接入（NOMA）、可重构复杂天线系统等方向。
  使用此技能进行论文各章节的起草和写作：
  - Abstract / Introduction / Motivation / System Model / Numerical Results / Conclusion
  当用户提到"写论文"、"写摘要"、"写引言"、"写方法"、"写仿真结果"、"写结论"等时触发。
  特别适用于 IEEE 期刊/会议论文的初稿撰写。
version: 1.0.0
author: MarecGents Group
---

# ieee-mg-writing — IEEE Transactions 风格学术写作

## 架构概览

本技能采用 **静态层（static/）+ 动态层（manifest.yaml）** 的分层架构：

| 层级 | 内容 | 加载时机 |
|------|------|----------|
| **共享层** | `../ieee-mg-share/static/style-profile.md` + `terminology.md` — 全局风格与术语 | 始终加载 |
| **核心层** | `static/core.md` — 写作核则 | 始终加载 |
| **工作流层** | `static/workflow.md` — 标准写作流程 | 始终加载 |
| **章节层** | `static/section-*.md` — 各章节专项模板 | 按检测的 `section` 轴加载 |
| **参考层** | `references/` — 按需参考资料 | 仅当用户明确要求或需要参考时加载 |
| **脚本层** | `scripts/` — 辅助脚本 | 按需调用 |

## 路由协议

按照以下 6 步流程执行：

### Step 0：加载共享层
立即加载 `../ieee-mg-share/static/style-profile.md` 和 `../ieee-mg-share/static/terminology.md`，
建立课题组全局风格画像和术语规范。共享层的内容被 ieee-mg-writing 和 ieee-mg-polishing 共同使用。

### Step 1：加载核心层
立即加载 `static/core.md`，建立本技能的写作核心原则。

### Step 2：检测请求轴
从用户请求中检测以下轴的值：

| 轴（Axis） | 检测目标 | 检测提示 |
|------------|----------|----------|
| `paper_type` | journal / conf / mag | 用户是否指定了论文类型？默认 journal（期刊） |
| `section` | abstract / introduction / motivation / system-model / numerical-results / conclusion | 用户要求写哪个章节？ |
| `language` | en / zh | 用户使用哪种语言？默认 en（英语） |

使用自然语言推断，不要显式询问用户 —— 从请求中直接判断。如果有歧义，根据上下文做出合理默认选择。

### Step 3：加载匹配片段
根据检测到的轴值，加载对应的章节模板：

- 如果 `section = abstract` → 加载 `static/section-abstract.md`
- 如果 `section = introduction` → 加载 `static/section-introduction.md`
- 如果 `section = motivation` → 加载 `static/section-motivation.md`
- 如果 `section = system-model` → 加载 `static/section-system-model.md`
- 如果 `section = numerical-results` → 加载 `static/section-numerical-results.md`
- 如果 `section = conclusion` → 加载 `static/section-conclusion.md`

如果请求涉及多个章节，按章节顺序依次处理。

### Step 4：按优先级起草
遵循以下优先级起草内容：
1. **核心原则**（`core.md`）优先 —— 所有写作必须符合核心原则
2. **章节模板**（`section-*.md`）其次 —— 遵循该章节的结构和风格
3. **用户具体要求** —— 在模板基础上满足用户的定制需求
4. **课题组风格** —— 从 `ieee-mg-database/` 中提取的风格特征（如可用）

### Step 5：按需取用参考
如果写作过程中需要参考外部资料（如引用格式、术语表），从 `references/` 或 `ieee-mg-database/` 中取用。不要随意编造参考文献信息。

## 边界说明

| 本技能负责 | 本技能不负责 |
|------------|-------------|
| IEEE Trans 风格各章节的初稿写作 | 文献引用验证（由 ieee-mg-citation 负责） |
| 基于课题组风格的内容起草 | 论文内容的学术润色（由 ieee-mg-polishing 负责） |
| 章节结构的规范化建议 | 实验数据的生成或修改 |
| 学术表达的规范化 | 论文图表的制作 |

## 设计原理

1. **静态/动态分离**：章节模板独立于路由逻辑，新增章节无需修改路由器
2. **轴驱动**：通过 paper_type / section / language 三个轴精准匹配用户需求
3. **课题组风格优先**：所有模板和示例优先反映 MarecGents 课题组在 B5G/6G、NOMA、可重构天线系统的研究特色
4. **分章节聚焦**：每章节独立模板，避免跨章节风格污染
