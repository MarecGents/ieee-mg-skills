# 段落节奏控制

> 基于课题组 21 篇论文的段落统计与节奏分析。控制学术写作的呼吸感和流畅度。
> 被 ieee-mg-writing 共同引用。

## 1. 各章节段落节奏基准

| 章节 | 推荐段数 | 推荐句数/段 | 首段特殊性 |
|------|:-------:|:----------:|-----------|
| **Abstract** | 1 | 5-10 | 单一段落，不分段 |
| **Introduction** | 5-10 | 3-8 | 第一段最宽（大背景），最后段最窄（论文组织） |
| **Motivation** | 2-4 | 3-6 | 首段衔接已有工作，末段列贡献 |
| **System Model** | 5-8 | 3-6 | 每段一个独立主题（场景→信道→信号→问题→算法） |
| **Numerical Results** | 4-8 | 4-6 | 每张图至少4句分析 |
| **Conclusion** | 1-2 | 5-10 | 80%为单一段落 |

## 2. Topic Sentence 规则

每个段落的第一句应为 **topic sentence**，概括本段内容。课题组语料中 90%+ 的段落遵循此规则。

### 各章节 Topic Sentence 模式

| 章节 | Topic Sentence 模式 |
|------|---------------------|
| **Introduction** | "X has been deemed/regarded as..." / "To tackle these challenges..." / "In [x], the authors..." |
| **System Model** | "We consider a system where..." / "The channel between X and Y is..." / "The optimization problem is formulated as..." |
| **Numerical Results** | "In this section, numerical results are presented..." / "Fig. X plots..." / "Another observation is..." |
| **Conclusion** | "In this paper, we have investigated..." / "Specifically, we have derived..." |

## 3. 段落间过渡策略

### 3.1 逻辑过渡（词组连接）
| 上段内容 | 过渡方式 | 下段内容 |
|----------|----------|----------|
| 已有工作回顾 | "However, / Nevertheless," | 指出不足 |
| 提出系统架构 | "Based on this model," | 信号模型推导 |
| 问题公式化 | "To this end, / To solve this," | 提出算法 |
| 算法描述 | "Furthermore, / In addition," | 复杂度分析 |
| 仿真参数 | "For the purpose of comparisons," | 基准方案说明 |
| 子场景A分析 | "Another important observation is" | 子场景B分析 |
| 各发现总结 | "From the perspective of practical applicability," | 实际应用讨论 |

### 3.2 句式过渡（复用关键术语）
上段末句的关键词 → 下段首句重复/指代：
```
[上段末句]: ...achieving the maximum learning efficiency with ASTARS.
[下段首句]: The integration of ASTARS enables simultaneous transmission
of signals from a large set of users to the BS...
```

## 4. 段落内部句间过渡多样化

> **核心目标**：消除"单词过渡词综合征"，让文献综述段落读起来是流畅叙述而非清单罗列。

### 4.1 问题定义：单词过渡词综合征

段落中连续 ≥3 句以**单一的递进/补充类单词过渡词**开头，形成机械模式：

```
Meanwhile, ... Furthermore, ... Additionally, ... Moreover, ...
Notably, ... In addition, ... Beyond ...
```

**病因**：作者将"过渡 = 必须加过渡词"误解为"每句都需要"，且所有过渡词都是递进/补充类，单调重复。

### 4.2 七种过渡手法库

| # | 手法 | 力度 | 示例 | 适用场景 | 每段频次 |
|---|------|:----:|------|---------|:--------:|
| 1 | **自然承接（无过渡）** | 轻 | The authors of \cite{...} proposed... | 同一子主题内连续引用多篇文献 | 2–3次 |
| 2 | **主题引导短语** | 中 | To exploit spatial degrees of freedom, / At the system architecture level, | 从上一个子主题切换到下一个子主题 | 2–3次 |
| 3 | **引用开头** | 中 | In \cite{...}, the authors... / Reference \cite{...} examined... | 单篇重要文献，需要主动聚焦 | 1–2次 |
| 4 | **同位语嵌入强调** | 重 | A critical yet previously overlooked factor—X—was... | 某篇文献贡献独特，需要突出强调 | 0–1次 |
| 5 | **场景引导短语** | 中 | For downlink scenarios, / In the context of secure communications, | 切换应用场景或信道条件 | 0–1次 |
| 6 | **分词短语引导** | 中 | Going beyond..., / Extending this direction, | 拓展到新领域或新维度 | 0–1次 |
| 7 | **收束总结词** | 轻 | Collectively, / Together, / Overall, | 段落末句，收束上文引向结论 | 仅末句 |

**力度说明**：轻（自然承接，几乎无存在感）→ 中（主题短语/引用开头/场景短语/分词短语）→ 重（同位语嵌入，刻意制造停顿和聚焦）。

### 4.3 手法选择三原则

**原则一：同种手法不邻**
相邻两句不使用同一种过渡手法：
- ❌ To exploit spatial degrees of freedom, ... To address this challenge, ...（相邻两个主题短语）
- ✅ To exploit spatial degrees of freedom, ... The authors of \cite{...} proposed...（主题短语 → 自然承接）

**原则二：子主题内部承接，切换时引导**
```
子主题A打开（主题引导短语）→ 子主题A续引（自然承接）→ 
子主题B打开（主题引导短语）→ 子主题B续引（引用开头）→ ...
```

**原则三：特殊贡献用同位语嵌入强调**
首次提出、颠覆性发现或关键转折点——不要用 Notably 一带而过，改为同位语嵌入主语：
- ❌ Notably, the waveguide power loss was explicitly considered...
- ✅ A critical yet previously overlooked factor—waveguide power loss—was explicitly considered...

### 4.4 文献综述段落典型节奏模型

```
句① Topic sentence（自然陈述）
句② 子主题A续引（自然承接 / 引用开头）
句③ 子主题B打开（主题引导短语）          ← 子主题切换标记
句④ 子主题B续引（自然承接）
句⑤ 子主题C打开（主题引导短语）          ← 子主题切换标记
句⑥ 子主题C续引（自然承接）
句⑦ 特殊贡献强调（同位语嵌入）            ← 特殊强调标记
句⑧ 拓展方向（分词短语 / 场景短语）       ← 拓展标记
句⑨ 段落收束（Collectively / 总结词）     ← 段落结束标记
```

**节奏原则**：9 个句位使用 ≥5 种手法，每种最多出现 2 次，无相邻重复。

### 4.5 自查清单

写作或润色文献综述段落时，逐项检查：
- [ ] 相邻两句是否使用了同一种过渡手法？
- [ ] 段落中是否有 ≥3 句连续以单词过渡词（Meanwhile/Furthermore/Additionally/Moreover/Notably/In addition/Besides）开头？
- [ ] 主题切换处是否使用了主题引导短语（而非简单递进词）？
- [ ] 是否有至少一处使用了自然承接（无过渡词）？
- [ ] 是否需要同位语嵌入代替 Notably 来强调特殊贡献？
- [ ] 全文的过渡手法种类是否 ≥ 4 种？

## 5. 段落长度分布

| 章节 | 推荐段长（词数） | 原因 |
|------|:----------------:|------|
| Abstract | 全部100-250词 | 单一段落 |
| Introduction Layer 1 | 80-150 | 开阔背景，不宜太短 |
| Introduction Layer 3 | 100-200 | 文献综述，需要充分展开 |
| System Model | 60-120 | 数学密集，段内自然短 |
| Results 单图分析 | 80-150 | ≥4句，约100词 |
| Conclusion | 全部200-400词 | 单一段落（多数情况） |

## 6. 节奏变奏技巧

### 6.1 短句突击
在连续长句（>25词）后插入短句（<12词），制造停顿和强调：
```
[长句]: "This is due to the fact that the MCS protocol has a more flexible decoding strategy, which can effectively reduce the interference between GFU and GBU."
[短句]: "This phenomenon is critical in practical deployments."
```

### 6.2 并列三连
用三个平行短句制造节奏感和说服力：
```
"Compared to PSTARS, ASTARS offer several advantages: 
It provides larger coverage areas, mitigates transmission errors, and exhibits higher energy efficiency."
```

### 6.3 问答节奏
用 Rhetorical Question 打破叙述单调：
```
"The main questions are then: How does ASTARS affect the model aggregation? 
What is the optimal phase shift design? This paper aims to answer these questions by..."
```
