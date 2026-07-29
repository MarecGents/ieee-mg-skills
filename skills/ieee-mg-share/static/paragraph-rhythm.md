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

## 4. 段落长度分布

| 章节 | 推荐段长（词数） | 原因 |
|------|:----------------:|------|
| Abstract | 全部100-250词 | 单一段落 |
| Introduction Layer 1 | 80-150 | 开阔背景，不宜太短 |
| Introduction Layer 3 | 100-200 | 文献综述，需要充分展开 |
| System Model | 60-120 | 数学密集，段内自然短 |
| Results 单图分析 | 80-150 | ≥4句，约100词 |
| Conclusion | 全部200-400词 | 单一段落（多数情况） |

## 5. 节奏变奏技巧

### 5.1 短句突击
在连续长句（>25词）后插入短句（<12词），制造停顿和强调：
```
[长句]: "This is due to the fact that the MCS protocol has a more flexible decoding strategy, which can effectively reduce the interference between GFU and GBU."
[短句]: "This phenomenon is critical in practical deployments."
```

### 5.2 并列三连
用三个平行短句制造节奏感和说服力：
```
"Compared to PSTARS, ASTARS offer several advantages: 
It provides larger coverage areas, mitigates transmission errors, and exhibits higher energy efficiency."
```

### 5.3 问答节奏
用 Rhetorical Question 打破叙述单调：
```
"The main questions are then: How does ASTARS affect the model aggregation? 
What is the optimal phase shift design? This paper aims to answer these questions by..."
```
