# Abstract（摘要）写作模板

> 基于课题组 21 篇 IEEE Trans 期刊论文摘要的深度语料蒸馏。
> **核心结构**：背景 → 问题 → 方法 → 结果(编号) → 意义（5 要素漏斗式）
> **约束分级（v1.2.0）**：✅ 硬约束 / 💡 软约束（可选要素）。

## 一、标准结构模板

### 要素 A：背景句（第 1 句）
引出研究领域，点明重要性和趋势。语料开头模式实测分布（21 篇逐篇核验）：

**模式 1："This paper/This article investigates/proposes/introduces..."（约 43%，9/21）**
```
This paper investigates / proposes / introduces [topic] in [scenario].
```
- "This paper investigates the performance of simultaneously transmitting and reflecting surface assisted semi-grant-free non-orthogonal multiple access network..."
- "This paper introduces the ASTARS to assist non-orthogonal multiple access communications..."

**模式 2：技术主语式（约 38%-52%，最常见变体组合）**
```
[Technology] has attracted growing research interest / received a lot of attention
due to its ability / capability to [核心优势].
```
- "Active simultaneously transmitting and reflecting surfaces (ASTARS) have attracted growing research interest due to its ability to alleviate multiplicative fading..."
- "Reconfigurable intelligent surface (RIS) has been regarded as a promising technology since it has ability to create the favorable channel conditions."
- "As a revolutionary technology, reconfigurable intelligent surface (RIS) has been deemed as an indispensable part of the 6th generation communications..."

**模式 3：被动式（"A X system is investigated/proposed"）**
```
A [系统] system is investigated, where [场景描述].
```
- "A two-way relay non-orthogonal multiple access (TWR-NOMA) system is investigated, where two groups of NOMA users exchange messages..."

**模式 4：让步式（约 5%，1/21）**
```
Although [Technology] can improve [性能], it still faces challenges such as [限制].
To address these issues, in this paper, we utilize [新型技术] to [目标].
```
- "Although reconfigurable intelligent surface (RIS) can improve the secrecy communication performance of wireless users, it still faces challenges such as limited coverage and double-fading effect."

### 要素 B：问题/动机句（第 2 句，💡 可选，实测约 10-20%）
指出现有方法的不足。典型过渡：

| 过渡词 | 频次 | 示例 |
|--------|------|------|
| However, | 中 | "However, existing approaches suffer from..." |
| To address these issues, | 低 | "To address these issues, we utilize..." |
| To tackle this problem, | 低 | "To tackle this problem, active RIS has been proposed..." |

> 注：多数摘要（约 80-90%）无独立问题句，直接从背景进入方法（方法句内含 "To address this issue, we..." 类过渡）。问题句不是必含要素。

### 要素 C：方法句（2-3 句，✅ 100% 出现）

**核心动作三连：**

| 动作 | 标准句式 | 示例 |
|------|----------|------|
| **提出** | "In this paper, we propose/investigate..." | "In this paper, we utilise ASTARS to assist the federated learning uplink model transfer..." |
| **推导** | "We derive/obtain/formulate..." | "We derive an upper bound on the aggregation error..." |
| **优化** | "We further propose/design..." | "We define the performance as a joint optimization problem..." |

**高频句式库：**
- "More specifically, we derive the expressions of X for Y with pSIC/ipSIC."
- "We further design a X strategy to eliminate the Y and improve the Z."
- "By applying X and Y, the asymptotic expressions of Z are attained."
- "The impact of X on Y is characterized/investigated."
- "On top of these, ... / As a further development, ..."（递进过渡，语料实测）

### 要素 D：结果句（1-3 句，✅ 100% 以编号列表呈现）

**标准引出句式：**
```
Numerical results show/demonstrate/indicate that:
i) [第一个发现];
ii) [第二个发现]; and
iii) [第三个发现].
```

**结果句三大类别（语料统计）：**

| 类别 | 常用表达 | 示例 |
|------|----------|------|
| **比较结果** | outperforms, exceeds, is superior to | "The SOP of X exceeds that of Y..." |
| **参数影响** | with the increasing of, by adjusting | "With the increasing of K, X is able to achieve the enhanced performance..." |
| **特殊发现** | due to, because of | "Due to the balance between A and B, introducing excess X is not helpful to reduce Y..." |

编号列表内容规律：第 1 条多为方案优势对比，第 2 条多为参数影响，第 3 条多为特殊发现或权衡。

**双编号组模式（语料实测，约 2/21 篇）**：先 "Our analytical results reveal that: i)... ii)..."，再 "Finally, simulation results demonstrate that: 1)... 2)..."。

### 要素 E：意义句（💡 可选，实测约 5-15%）
```
[This work] provides/presents a promising solution for [application].
```
- 语料中独立意义句极少（多数以结果编号句收尾），无需强求。示例句 "presents a promising solution for enhancing modern communication networks" 实际出自引言语料，非摘要，勿照抄为摘要例句。

---

## 二、课题组摘要语法特征

### 2.1 开头动词分布
| 动词 | 按篇频次 | 示例 |
|------|:--------:|------|
| investigates | 6/21（"This paper investigates" 4 + "This article investigates" 2） | "This paper investigates..." |
| proposes | 2/21 | "This article proposes..." |
| introduces | 1/21 | "This paper introduces X to assist..." |
| studies | 0（未见于开头句） | — |
| analyzes | 0（未见于开头句） | — |

> 注：合计约 43%（9/21）以 This paper/This article 系开头；"studies"/"analyzes" 未见于摘要开头句。

### 2.2 结果引出词分布（语料实测，21 篇逐篇）
| 引出词 | 实测篇数 | 占比 |
|--------|:--------:|:----:|
| "Numerical results show/demonstrate/indicate that" | 12 | ~57% |
| "Simulation results verify/confirm/demonstrate that" | 8 | ~38% |
| "The experimental simulation results are presented to confirm that" | 1 | ~5% |

> 其他单篇变体：manifest that（1 篇）、presented to substantiate（1 篇）、reveal（1 篇）、"Simulation results are provided to verify the accuracy ... and demonstrate/indicate that"（多篇）。

### 2.3 编号结果格式规范（语料实测）
- 使用无括号编号：小写罗马 "i)" 或阿拉伯 "1)"（语料中不存在 "(i)(ii)(iii)" 括号形式；按编号组计 i) 系 9 组 / 1) 系 14 组）
- 每条结尾使用分号（;）
- 最后一条前加 "and" 或 "and finally"
- 最后一条以句号（.）结束
- 每条建议 15-30 词（估算）
- 通常 2-4 条（3 条最常见；4 条：Double RIS 篇）
- 条目可小写开头（"1) the gap between traffic requests..."）或单条内嵌转折（"However, ..."）

### 2.4 时态规则
| 位置 | 时态 | 示例 |
|------|------|------|
| 背景/问题句 | 现在完成时 / 一般现在时 | "X have attracted... X is..." |
| 方法句 | 一般现在时 | "We propose/derive/formulate..." |
| 结果句 | 一般现在时 | "Numerical results demonstrate..." |
| 意义句 | 一般现在时 | "This presents a promising..." |

### 2.5 段落过渡逻辑流
```
[背景] X has attracted growing interest due to... 
    ↓ (However/To address this)
[问题] However, existing approaches suffer from...（可选）
    ↓ (In this paper)
[方法] In this paper, we propose Y to...
    ↓ (Numerical results show)
[结果] Numerical results demonstrate that: i)... ii)... iii)...
    ↓ (可选)
[意义] This work provides a promising solution for...
```

---

## 三、课题组独有的摘要写作习惯

1. **第一人称使用**：约 76%（16/21）的摘要使用 "we"（we propose/derive/formulate/investigate），密度约 6.5 次/千词
2. **技术术语首次全称定义**：所有缩略语在摘要中首次出现时必须给出全称（语料实测 Abstract 内即定义，如 ipSIC 12/21、pSIC 11/21 篇）
3. **性能比较全覆盖**：几乎所有结果句都在与某种基准方案比较（100% 覆盖）；**具体数值/百分比极少出现在摘要**（0/21 篇），数值优先放正文与结论
4. **比较型结果占主导**：几乎所有结果句都在与某种基准方案比较
5. **编号列表结果高度规律**：第 1 条多为方案优势对比，第 2 条多为参数影响，第 3 条多为特殊发现或权衡

## 四、篇幅规范（v1.2.0 与 quantitative-baseline.md 统一）
| 指标 | 范围 | 中位数 |
|------|------|--------|
| 总词数 | 85-280 词（典型 130-260） | ~165 词 |
| 总句数 | 5-10 句 | ~7 句 |
| 平均句长 | 约 25-29 词/句（抽样 6 篇） | — |

## 五、写作检查清单（✅ 必须 / 💡 建议）
- [✅] 开头是否属于语料高频模式（"This paper investigates/proposes" 约 43%；或技术主语式 "X has attracted growing interest..."；或被动式 "A X system is investigated"；或 "Although..." 让步式约 5%）
- [✅] 背景句是否点明了研究领域的重要性
- [💡] 是否包含 "However" 类过渡指出已有工作不足（可选，约 10-20% 论文有独立问题句）
- [✅] 方法部分是否包含 "we propose/derive/formulate" 等动作
- [✅] 结果是否以 "Numerical/Simulation results ... that:" 引出（引出词变体 6+ 种均可）
- [✅] 结果是否以 i)/1) 编号列出（2-4 条，每条 15-30 词）
- [✅] 所有缩略语首次出现时是否已定义全称（如 "imperfect SIC (ipSIC)"）
- [✅] 是否包含至少一个性能比较（与 OMA/PRIS/传统方案等基准对比）
- [✅] 词数是否在 85-280 词范围内（典型 130-260）
- [✅] 是否使用 IEEE 数学符号规范
- [✅] 时态是否统一（现在时 + 现在完成时）
- [💡] 是否在一条结果中指出了特殊发现或权衡关系（语料高频特色）
- [❌] 是否未引入正文未讨论的新内容

## 六、第一轮蒸馏补充（语料发现的新模式）

### 6.1 让步-转折一体化背景句
要素 A 模式 4（见上），使用频率约 5%（1/21），适用于有明确技术瓶颈的研究场景。

### 6.2 "总-分"式方法展开
要素 C 中展开结构（语料多篇使用，印象分）：
```
We investigate [问题] in [系统].
Specifically/More specifically/To be specific, we derive [表达式1] and [表达式2].
Additionally, we examine the impact of [参数] on [性能].
```

### 6.3 编号结果前总起句
要素 D 中总起+编号结构：
```
[总起句: 声明验证目的] + Numerical results show/demonstrate/indicate that:
i) [发现1];
ii) [发现2]; and
iii) [发现3].
```
总起句库："The simulation results verify the correctness of the formulas and yield the following insights:"（语料原句为单数 "yields"，主语 results 复数规范应为 "yield"，写作时用 "yield"）

### 6.4 实际篇幅分布
| 指标 | 范围 | 中位数 | 备注 |
|------|------|--------|------|
| 总词数 | 85-280 | ~165 | 避免<85词（信息不足）或>280词（超限）；实测中位数约 165（quantitative-baseline 口径） |

## 七、第二轮蒸馏补充（语料深度对比新增模式）

### 7.1 "More specifically" 方法展开高频过渡词
要素 C 中的"总-分"展开，语料中 "More specifically" 出现频率远高于 "Specifically" 和 "More precisely"。建议优先使用 "More specifically" 作为方法展开的过渡词。

### 7.2 结果引出词变体库（各为单篇/低频变体，~5%）
| 变体 | 使用频率 | 示例 |
|------|----------|------|
| "The simulation findings are presented to demonstrate that" | 1/21 | "The simulation findings are presented to demonstrate that: i)..." |
| "The experimental simulation results are presented to confirm that" | 1/21 | "The experimental simulation results are presented to confirm that: i)..." |
| "Simulation results are provided to verify the accuracy of the theoretical analyses and demonstrate that" | 中频 | 长变体，适用于强调理论与仿真的一致性 |
| "Numerical results are presented to verify the theoretical analyses and indicate that" | 中频 | 同时完成验证和结果呈现 |

### 7.3 "manifest that" 结果引出词补充
语料 1 篇使用 "manifest that"（语气强于 show，强调发现的确凿性）：
```
Numerical results are provided to verify the accuracy of theoretical analyses and manifest that:
i) [发现1]; ii) [发现2]; and iii) [发现3].
```

### 7.4 总起句库
- "The simulation results verify the correctness of the formulas and yield the following insights:"（语料原句 "yields"，主语 results 复数规范为 "yield"，写作时用 "yield"）

### 7.5 "On top of these" / "As a further development" 递进过渡词
| 过渡词 | 使用场景 | 示例 |
|--------|----------|------|
| "On top of these" | 在已有分析基础上进一步推导 | "On top of these, the secrecy diversity order of legitimate user is obtained..." |
| "As a further development" | 引入进一步的理论扩展 | "As a further development, the closed-form and asymptotic expressions are derived..." |
| "To be specific" | 具体展开（与 "More specifically" 互换） | "To be specific, the closed-form expressions of SOP are derived..." |

### 7.6 "precede that of" 比较动词变体
| 动词 | 语气强度 | 示例 |
|------|----------|------|
| precede that of | 中等 | "The outage behaviors of X precede that of Y" |
| exceed that of | 强 | "The SOP of X exceeds that of Y" |
| be superior to | 强 | "X is superior to Y" |
