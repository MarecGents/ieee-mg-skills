# Motivation & Contribution（动机与贡献）写作模板

> 基于课题组 21 篇论文的 Motivation & Contribution 语料深度蒸馏。
> **核心结构**：研究背景回顾 → 研究空白 → 贡献列表(编号) →（可选）对比表格
> **约束分级（v1.2.0）**：✅ 硬约束 / 💡 软约束（可选要素）。

## 一、标准结构模板

### 要素 1：承上启下（1 段，💡 推荐）
回顾已有成果并引出不足。**开头模式实测（21 篇逐篇核验）：While 类约 38%（8/21）、Although 类约 5%（1/21）、其余为 The aforementioned / Building upon / As previously mentioned 等变体或直接陈述。承上启下是高频模式但非强制。**

**模板句式（语料实测高频）：**
```
While the aforementioned works have laid a solid foundation for understanding 
[技术A] and [技术B], the promising integration of these two technologies is 
still in its infancy.
```
或
```
While the above-mentioned research provides a solid foundation for comprehending 
X, Y remains an emerging area of study.
```

**变体句式：**
| 句式 | 使用场景 |
|------|----------|
| "While the above-mentioned research provides a solid foundation for comprehending X, Y remains an emerging area of study." | 引出新研究方向 |
| "To the best of our knowledge, existing works are based on X, which are difficult to realise in practical applications." | 指出现有方法不实际 |
| "Building upon the previous sections, the literature on X has become abundant..." | 综述回顾式开头 |
| "As previously mentioned, ..." | 回指式开头 |

### 要素 2：研究空白定位（1-2 句，✅ 约 67% 论文含空白声明）

**核心句式（语料实测，12/21 篇精确使用 "To the best of our knowledge"）：**
```
To the best of our knowledge, there is/are no [已有工作] to investigate/consider [研究空白].
```

**空白句式变体（语料实测）：**
- "To the best of our knowledge, X has not been comprehensively explored in prior works."（ASTARS-FL 篇原文，注意：该句式存在于语料，可用）
- "To the best of our knowledge, the performance of X ... is not researched yet."
- "To the best of our knowledge, this paper is the first to conduct an analysis of X."
- "To the best of our knowledge, there is no related work to analyze X."
- "To the best of our knowledge, existing works are based on pSIC [x], which are difficult to realise in practical applications."
- "To our knowledge, ... there currently are no treatises on X."（去 best of 变体）

**空白定位三要素：**
1. **已有研究做了什么** — "Prior research has addressed..."
2. **但缺少了什么** — "However, the unique advantages offered by X remain underutilized in Y scenarios"
3. **为什么这很重要** — "which is significant for Y because..."

### 要素 3：尖锐问题引导（💡 低频可选，实测约 10%，2/21 篇）
```
[直接问句 1]? [直接问句 2]? This paper aims to answer these questions by [方案].
```
- "Will FD NOMA relaying bring performance gains compared to HD NOMA relaying? If yes, what is the condition?"（语料原文，注意原文为 FD 非 NOMA）
- "by seeking answers to these questions:" 框架（MF-RIS 篇）亦可用

问题的三个设计原则：
1. **每个问题对应一个贡献点**
2. **问题要有技术深度**（不是 yes/no 问题）
3. **问题之间要有逻辑递进关系**

### 要素 4：贡献列表（✅ 3-5 点，编号 1)2)3) 或 "-" 项目符号均可）

**标准模板：**
```
Based on the above explanations, the primary contributions of this manuscript 
are summarized as follows:

1) We propose [方案]. By introducing [技术], we explore the impact of [参数] on 
   [系统]. We further propose [方法] to [目标]. Moreover, we evaluate the 
   performance of [方案] over [信道模型].

2) We investigate [问题] and derive the [表达式] for [指标]. On this basis, we 
   analyze the [性能] and confirm that [结论].

3) We analyze the [特性] of [系统] at [条件]. We further derive the [渐近表达式] 
   of [指标] in [场景]. Analytical results show that [结论].

4) We confirm that [结论]. By adjusting [参数], the performance can be further 
   enhanced. We finally demonstrate that [关键结论].
```

**贡献点动作规范（💡 推荐组合，非强制顺序与数量）：**
| 动作 | 动词 | 句型模板 |
|:----:|------|----------|
| **1) 提出** | propose, introduce, develop | "We propose a novel X framework for Y..." |
| **2) 推导** | derive, establish, formulate | "We derive the closed-form expressions of X..." |
| **3) 分析/优化** | analyze, investigate, optimize | "We investigate the X optimization problem..." |
| **4) 验证** | demonstrate, confirm, validate | "We demonstrate that the proposed X outperforms Y..." |

> 实测：贡献点 3-5 点不等（ASTARS covert 篇为 propose→derive→derive→derive 四点，无独立分析/验证动作）；最低要求动作动词多样性 ≥3 类。FL 篇用 "-" 项目符号列表。

**贡献点量化自查（✅ 每条）**：动作动词 + 方法/对象 + 成果/结论 三要素齐全。

### 要素 5：对比表格（💡 低频可选，实测约 5%，1/21 篇）

**标准表头格式（语料实证 FL 篇）：**
```
TABLE I
OUR CONTRIBUTIONS IN CONTRAST TO THE STATE-OF-THE-ART
```

**表格结构模板：**
| Feature | [Ref A] | [Ref B] | [Ref C] | [Ref D] | Proposed |
|---------|---------|---------|---------|---------|----------|
| Feature 1 | ✓ | × | ✓ | × | ✓ |
| Feature 2 | × | ✓ | × | ✓ | ✓ |
| Feature 3 | × | × | ✓ | × | ✓ |

**表格设计原则（源自 FL 篇 Table I 样例，非强制）：**
- 左侧列：关键技术特征（4-8 行）
- 中间列：代表性的已有工作（3-5 篇）
- 右侧列：本文方案
- ✓ 表示具备该特征，× 表示不具备；单元格亦可含 "✓, but not mentioned" 类注释（语料实证）
- 本文应具备所有特征（全部 ✓）

---

## 二、课题组独有的 Motivation 写作特征

1. **承上启下开头**：While 类约 38%（8/21），另有 The aforementioned / Building upon / As previously mentioned 等变体——**非唯一模式**
2. **贡献点动作组合灵活**：提出→推导→分析→验证 为推荐模板，实测顺序与数量多变
3. **对比表格**：特色元素（约 5% 论文使用），用于直观展示本文与已有工作的差异
4. **尖锐问题引导**：约 10% 的论文在 Motivation 中提出问题列表
5. **贡献点数量**：3-5 个（"4 个固定"不成立）
6. **每个贡献点包含"做了什么 + 取得了什么"**

**差异列点式动机（语料变体，covert 篇）：**
```
this paper has three main differences. Firstly, ... Secondly, ... Thirdly, ...
```

## 三、写作检查清单（✅ 必须 / 💡 建议）
- [💡] 是否以承上启下模式开头（While/Although/前述综述回顾，非强制）
- [✅] 研究空白是否明确（"To the best of our knowledge..." 或变体；约 67% 论文含空白声明）
- [✅] 动机是否有充分的技术依据
- [✅] 贡献是否以编号 1)2)3)4) 或等价列表格式列出
- [✅] 每个贡献点是否包含"动作(propose/derive/analyze/demonstrate)" + "方法/对象" + "成果"三要素
- [✅] 是否有至少 3 个不同的贡献点
- [💡] 本文贡献与已有工作的差异是否清晰
- [💡] 贡献点之间是否有逻辑递进关系
- [💡] 对比表格（如使用）是否覆盖了关键特征（源自 FL 篇样例，非强制）
- [✅] 引用是否覆盖了关键和最新文献

## 四、第一轮蒸馏补充（语料发现的新模式）

### 4.1 贡献点三层递进结构（💡 推荐）
每个贡献点内部可遵循三层递进：
```
[动作层]: We propose/introduce [方案].
[工具层]: By [工具/方法], we explore/analyze [影响].
[结论层]: [结论句: We confirm/demonstrate that...].
```

### 4.2 研究空白句变体（语料实测全收录）
- "To the best of our knowledge, there are no existing works to investigate X."
- "To the best of our knowledge, there is no existing work investigating X."
- "To the best of our knowledge, X has not been comprehensively explored in prior works."
- "To the best of our knowledge, this paper is the first to conduct an analysis of X."
- "X remains an emerging area of study / is still in its infancy."（注意单数主语配 its）

### 4.3 尖锐问题-贡献点映射规则（💡）
设计原则：问题与贡献一一对应
- 问题1（技术挑战） → 贡献1（系统建模与推导）
- 问题2（关键因素对比） → 贡献2（对比分析）
- 问题3（不同场景差异） → 贡献3（场景差异研究）

### 4.4 对比表格特征行五维设计（💡 源自 FL 篇样例）
表格特征行建议覆盖以下维度：
1. 空间/覆盖能力（full-space, half-space）
2. 硬件能力（amplification, passive/active）
3. 技术特性（OTA, NOMA, SIC）
4. 性能指标（能效、鲁棒性）
5. 实际应用（FL支持、硬件实现）
