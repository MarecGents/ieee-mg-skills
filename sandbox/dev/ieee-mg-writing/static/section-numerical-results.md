# Numerical Results（数值结果）写作模板

> 基于课题组 21 篇论文仿真结果部分语料深度蒸馏。
> **核心结构**：参数设置 → 基准方案 → 子场景分析(A/B/C) → 洞察总结

## 一、标准结构模板

### 要素 1：章节开头（1 段）

**标准开头句式（语料中出现率 95%+）：**
```
In this section, numerical/simulation experiments/results are presented 
to verify the accuracy of [理论分析/推导] in comparison with the performance 
of [本文方案]. Unless stated otherwise, the simulation parameters are 
presented in [Table X].
```

**变体句式：**
```
This section conducts simulation experiments to validate the accuracy of 
performance analysis results in comparison with the performance of [本文方案].
```

### 要素 2：仿真参数表（TABLE II 标准格式）

**课题组标准表格式样：**
```
TABLE II
SIMULATION PARAMETERS / TABLE OF PARAMETERS FOR NUMERICAL RESULTS

| Parameter | Value |
|-----------|-------|
| Monte Carlo simulations repeated | \(10^5\) iterations |
| Carrier frequency | 1 GHz |
| Rician factor | \(\kappa = 5\) dB |
| Pass loss exponent | \(\alpha = 2\) |
| Noise power | \(\sigma^2 = -90\) dBm |
| Number of reflecting elements | \(M = 30\) |
| Power allocation coefficients | \(a_1 = 0.8, a_2 = 0.2\) |
| Target data rates | \(R_1 = R_2 = 0.01\) BPCU |
```

**必含参数项（语料统计）：**
| 参数类别 | 必含项 |
|----------|--------|
| 仿真方法 | Monte Carlo iterations |
| 信道参数 | Rician factor / Path loss exponent |
| 系统参数 | Bandwidth / Carrier frequency / Noise power |
| 方案参数 | Number of elements / Power allocation / Target rates |
| 比较方案 | List of benchmark schemes |

### 要素 3：基准方案说明（1 段）

**标准句式：**
```
For the purpose of comparisons, we consider the following baselines:
1) **[Baseline A]**: [简要描述]
2) **[Baseline B]**: [简要描述]
3) **[Baseline C]**: [简要描述]
```

**课题组常用基准方案**（基于语料提取）：
| 基准类型 | 典型方案 |
|----------|----------|
| **OMA 对照** | OMA, TDMA, FDMA |
| **无 RIS 对照** | Without RIS, Direct transmission |
| **被动 RIS 对照** | PRIS, PSTARS |
| **其他 RIS 变体** | STAR-RIS, Double RIS |
| **传统中继** | AF, DF, HD-DF, FD-DF |
| **算法对比** | MM algorithm, DC algorithm, SCA variants |

### 要素 4：子场景分析（2-5 段，核心内容）

**课题组标准组织方式：**

**方式 A：按图组织（最常见）**
```
A. [Scenario Name 1]
  → Fig. X: [图描述]
  → Fig. Y: [图描述]
B. [Scenario Name 2]
  → Fig. Z: [图描述]
```

**方式 B：按性能指标组织**
```
A. Outage Probability
B. Ergodic Data Rate
C. System Throughput
```

**方式 C：按参数影响组织**
```
A. Impact of Transmit SNR
B. Impact of Number of Elements
C. Impact of Power Allocation
```

### 要素 5：图分析标准三段式（必用）

**Step 1：引入图（1-2 句）**
```
Fig. X plots the [指标名] versus the [变量名], with [参数设置].
```

**Step 2：观察现象（2-3 句）**
```
It is observed from Fig. X that [趋势描述].
Another observation is that [对比发现].
As can be observed from the figure, [额外发现].
```

**Step 3：解释原因（1-2 句）**
```
This is because/due to the fact that [原因分析].
The reason is that [进一步解释].
This behavior is caused by [根本原因].
```

**完整分析段落示例（来自语料）：**
> Fig. 2 plots the COP versus the transmit SNR with ipSIC/pSIC, where K = 2. Obviously, the exact outage probability curves match perfectly with Monte Carlo simulations results. It is observed that the outage performance of OMA is inferior to the n-th user with pSIC and superior to the m-th user. This is due to the fact that NOMA is capable of providing better fairness since multiple users are served simultaneously. Additionally, as can be observed from figure, the dashed curves represent the asymptotic COP of the m-th user and n-th user with pSIC. One can observe that the asymptotic outage probabilities are approximated to the analytical results in the high SNR regime.

### 要素 6：高频分析用语库

**趋势描述：**
| 趋势 | 动词 | 示例 |
|------|------|------|
| 上升 | increases, improves, enhances | "The SE increases with the number of antennas" |
| 下降 | decreases, reduces, deteriorates | "The OP decreases as SNR increases" |
| 趋近 | converges to, approaches | "The SOP converges to an error floor" |
| 匹配 | matches perfectly, agrees with | "The exact curves match perfectly with simulation" |

**对比表达：**
| 比较级别 | 表达 |
|----------|------|
| 优于 | outperforms, is superior to, exceeds, has an advantage over |
| 次于 | is inferior to, underperforms |
| 相似 | is comparable to, is similar to |

**评价词汇：**
| 正面 | 负面 | 中性 |
|------|------|------|
| superior, robust, significant | inferior, degraded | comparable, similar |
| enhanced, improved, effective | deteriorated, limited | observable, noticeable |
| promising, efficient | challenging, problematic | gradual, consistent |

**特殊发现表达：**
- "It is worth pointing out that..."
- "It is interesting to note that..."
- "This phenomenon indicates that..."
- "To illustrate the impact of X..."

---

## 二、课题组 Numerical Results 写作特征

1. **每张图配一段分析**：最小长度 4 句（引入+观察+解释+对比）
2. **三段式分析为标配**：引入图→观察现象→解释原因
3. **理论曲线与仿真曲线对比**：几乎每篇都验证理论推导的准确性
4. **使用多种基准方案**：通常 3-5 个，覆盖不同技术维度
5. **结果与理论分析互相印证**："which verifies the conclusion in Remark X"

## 三、写作检查清单
- [ ] 是否以 "In this section, numerical results are presented to verify..." 开头
- [ ] 仿真参数表是否完整（TABLE II）
- [ ] 是否列出了足够的基准方案（≥3 个）
- [ ] 每张图的引用是否使用 "Fig. X" 格式
- [ ] 每张图是否有 ≥4 句的分析
- [ ] 分析是否包含三段式（引入→观察→解释）
- [ ] 理论曲线与仿真曲线是否进行了对比
- [ ] 是否包含 "This is because/due to the fact that" 原因解释
- [ ] 结果是否与纯理论分析章节互相印证
- [ ] 是否避免了单纯的图表数据罗列

## 四、第一轮蒸馏补充（语料发现的新模式）

### 4.1 蒙特卡洛迭代次数分布（缺失15）
| 迭代次数 | 使用频率 | 典型场景 |
|----------|----------|----------|
| \(10^6\) | ~50% | 标准通信系统仿真 |
| \(10^5\) | ~30% | 复杂系统/高复杂度场景 |
| \(10^4\) 或 \(10\)（FL） | ~10% | 机器学习/FL训练 |

### 4.2 "多因一果"解释模式（缺失16）
在Step 3原因解释中新增多原因句式：
```
[现象陈述]. 
This is due to the fact that [原因1]. 
Another reason is that [原因2].
```
约25%的图分析使用多原因解释。

### 4.3 trade-off权衡表达（缺失17）
```
[参数A] does not necessarily translate to better [性能].
Therefore, it is crucial to consider the trade‑off between [参数A] and [参数B].
This suggests that optimizing [参数X] could be a promising direction.
```

### 4.4 "On the one hand... On the other hand"双面论证（缺失18）
```
On the one hand, [因素A的正面作用]. This is because [解释].
On the other hand, [因素A的负面作用]. This is due to [解释].
Hence, the optimization of [系统] is a balance between [A] and [B].
```
适用于非单调现象解释。

### 4.5 子图联合分析模式（缺失19）
```
Fig. X(a): [条件A下的结果] — [分析]
Fig. X(b): [条件B下的结果] — [分析]
The main variation is that [两个子图的对比发现].
```

### 4.6 基准方案详细描述风格（缺失20）
在要素3中新增详细风格：
```
1) **[Baseline A]**: [设计原理 + 对比差异 + 使用条件]
2) **[Baseline B]**: [设计原理 + 对比差异 + 使用条件]
```
