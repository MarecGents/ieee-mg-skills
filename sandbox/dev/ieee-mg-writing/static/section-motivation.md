# Motivation & Contribution（动机与贡献）写作模板

> 基于课题组 20+ 篇论文的 Motivation & Contribution 语料深度蒸馏。
> **核心结构**：研究背景回顾 → 研究空白 → 尖锐问题 → 贡献列表(编号) → 对比表格

## 一、标准结构模板

### 要素 1：承上启下（1 段）
使用 While/Although 开头，回顾已有成果并引出不足。

**模板句式（语料中出现率 100%）：**
```
While the aforementioned works have laid a solid foundation for understanding 
[技术A] and [技术B], the promising integration of these two technologies is 
still in their infancy.
```
或
```
Although the aforementioned literature highlights the advantages of [技术A] 
in terms of [指标1] and [指标2], the [问题] inherent to [技术A] cannot be overlooked.
```

**变体句式：**
| 句式 | 使用场景 |
|------|----------|
| "While the above-mentioned research provides a solid foundation for comprehending X, Y remains an emerging area of study." | 引出新研究方向 |
| "To the best of our knowledge, existing works are based on X, which are difficult to realise in practical applications." | 指出现有方法不实际 |
| "Although X has been extensively studied, the impact of Y on Z remains underutilized." | 指出未充分利用的技术空间 |

### 要素 2：研究空白定位（1-2 句）

**核心句式（语料中出现率 95%+）：**
```
To the best of our knowledge, [研究空白] has not been comprehensively explored 
in prior works / existing literature.
```

**空白定位三要素：**
1. **已有研究做了什么** — "Prior research has addressed..."
2. **但缺少了什么** — "However, the unique advantages offered by X remain underutilized in Y scenarios"
3. **为什么这很重要** — "which is significant for Y because..."

### 要素 3：尖锐问题引导（可选，约 30%）
```
This paper aims to explore [topic] by seeking answers to these questions:
- Question 1: How does [核心问题] affect [性能]?
- Question 2: When comparing [A] and [B], which factor poses a greater risk to [目标]?
- Question 3: What are the disparities in [性能] across [不同场景]?
```

问题的三个设计原则：
1. **每个问题对应一个贡献点**
2. **问题要有技术深度**（不是 yes/no 问题）
3. **问题之间要有逻辑递进关系**

### 要素 4：贡献列表（编号 1)2)3)4)）

**标准模板：**
```
Based on the above explanations, the primary contributions of this manuscript 
are summarized as follows:

1) We propose [方案]. By introducing [技术], we explore the impact of [参数] on 
   [系统]. We further propose [方法] to [目标]. Moreover, we evaluate the 
   performance of [方案] over [信道模型].

2) We investigate [问题] and derive the [表达式] for [指标]. On this basis, we 
   analyze the [性能] and confirm that [结论]. From the simulation results we 
   can see that [发现].

3) We analyze the [特性] of [系统] at [条件]. We further derive the [渐近表达式] 
   of [指标] in [场景]. Moreover, we calculated the [指标] in [条件下]. Analytical 
   results show that [结论].

4) We selected different comparative baselines from the perspectives of [维度1], 
   [维度2], and [维度3] to reveal the performance advantages of the proposed 
   [方案]. We confirm that [结论]. By adjusting [参数], the performance can be 
   further enhanced. We finally demonstrate that [关键结论].
```

**贡献点四动作规范：**
| 动作 | 动词 | 句型模板 |
|:----:|------|----------|
| **1) 提出** | propose, introduce, develop | "We propose a novel X framework for Y..." |
| **2) 推导** | derive, establish, formulate | "We derive the closed-form expressions of X..." |
| **3) 分析/优化** | analyze, investigate, optimize | "We investigate the X optimization problem..." |
| **4) 验证** | demonstrate, confirm, validate | "We demonstrate that the proposed X outperforms Y..." |

### 要素 5：对比表格（可选，约 25% 使用）

**标准表头格式：**
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

**表格设计原则：**
- 左侧列：关键技术特征（4-8 行）
- 中间列：代表性的已有工作（3-5 篇）
- 右侧列：本文方案
- ✓ 表示具备该特征，× 表示不具备
- 本文应具备所有特征（全部 ✓）

---

## 二、课题组独有的 Motivation 写作特征

1. **"While" 开头占比最高**（约 60%），其次是 "Although"（约 25%）
2. **贡献点的四个动作为固定模式**：提出→推导→分析→验证
3. **对比表格**：特色元素，用于直观展示本文与已有工作的差异
4. **尖锐问题引导**：约 30% 的论文在 Motivation 中提出问题列表
5. **贡献点数量稳定在 4 个**：极少为 3 个或 5 个
6. **每个贡献点包含"做了什么 + 取得了什么"**

## 三、写作检查清单
- [ ] 是否以 "While/Although the aforementioned works..." 开头
- [ ] 研究空白是否明确（"To the best of our knowledge..."）
- [ ] 动机是否有充分的技术依据
- [ ] 贡献是否以编号 1)2)3)4) 列出
- [ ] 每个贡献点是否包含"动作(propose/derive/analyze/demonstrate)" + "成果"
- [ ] 是否有至少 3 个不同的贡献点
- [ ] 本文贡献与已有工作的差异是否清晰
- [ ] 贡献点之间是否有逻辑递进关系
- [ ] 对比表格（如使用）是否覆盖了关键特征
- [ ] 引用是否覆盖了关键和最新文献

## 四、第一轮蒸馏补充（语料发现的新模式）

### 4.1 贡献点三层递进结构（缺失11）
每个贡献点内部应遵循三层递进：
```
[动作层]: We propose/introduce [方案].
[工具层]: By [工具/方法], we explore/analyze [影响].
[结论层]: [结论句: We confirm/demonstrate that...].
```
语料中90%以上的贡献点遵循此结构。

### 4.2 研究空白句变体（缺失12）
新增空白句式：
- "To the best of our knowledge, there are no existing works to investigate X."
- "To the best of our knowledge, there is no existing work investigating X."
- "This paper presents the first comprehensive analysis of X."
- "X remains an emerging area of study / is still in its infancy."

### 4.3 尖锐问题-贡献点映射规则（缺失13）
设计原则：问题与贡献一一对应
- 问题1（技术挑战） → 贡献1（系统建模与推导）
- 问题2（关键因素对比） → 贡献2（对比分析）
- 问题3（不同场景差异） → 贡献3（场景差异研究）

### 4.4 对比表格特征行五维设计（缺失14）
表格特征行建议覆盖以下维度：
1. 空间/覆盖能力（full-space, half-space）
2. 硬件能力（amplification, passive/active）
3. 技术特性（OTA, NOMA, SIC）
4. 性能指标（能效、鲁棒性）
5. 实际应用（FL支持、硬件实现）
