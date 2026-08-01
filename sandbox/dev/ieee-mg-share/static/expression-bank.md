# 通用句式库

> 基于课题组 21 篇论文语料提取的通用学术句式。不绑定特定章节，适用于全文各处的学术表达。
> 被 ieee-mg-writing 和 ieee-mg-polishing 共同引用。
> **标注体系（v1.2.0）**：每条句式标注 ① 约束等级——✅ 硬约束（语料高频或课题组规范，必须满足）、💡 软约束（建议优先使用，可视语境替换）；② 来源等级——语料实测（21 篇语料 grep + 人工核验）或 课题组规范（投稿要求/IEEE 惯例，语料无直接对应）。句式模板中的 [x] 为文献编号占位。

## 1. 文献引用句式

| 功能 | 句式模板 | 约束/来源 |
|------|----------|-----------|
| **正面引用** | "The authors in [x] proposed/investigated/studied..." | ✅ 语料实测（21 篇高频） |
| **归类引用** | "Prior studies have demonstrated that..." | 💡 语料实测（仅 1 处原文；"Prior works have demonstrated" 语料无完全同型，属课题组规范表述） |
| **现状描述** | "X has been extensively studied in the context of Y [x], [x]." | 💡 课题组规范（语料无完全同型句，近义表述 "the literature on X has become abundant" 见 PRIS-ARIS 篇） |
| **历史回顾** | "Early studies [x] focused on ..., while recent works [x] have shifted to..." | 💡 语料实测（while 分块对比为语料高频结构） |
| **对比引用** | "In contrast to [x] which considered ..., this paper..." | 💡 语料实测（同功能高频变体为 "Different from [x], [y], we..."） |
| **文献编号开头** | "In [x], the authors proposed/investigated/introduced..." | ✅ 语料实测（21 篇高频） |
| **开创性工作** | "A seminal work proposed X and designed Y [x]." | 💡 语料实测（ASTARS 篇原文 "A seminal work proposed a hardware model for ASTARS and designed an ASTARS-assisted downlink communication system"） |
| **被动语态引用** | "X was studied/analyzed/investigated in [x]." | 💡 语料实测（中频） |

## 2. 研究空白句式

> **实测口径（v1.2.0）**：约 67% 的论文含空白声明（13-14/21 篇，其中 "To the best of our knowledge" 精确模板 12/21，另有 covert 篇 "To our knowledge" 变体 1 篇及 first / not researched yet / have not been well evaluated 等非模板表述），**具体句式高度多样**；精确模板 "there is/are no ... to investigate" 仅 2-3 处。以下按语料实测频率排列。

| 句式模板 | 使用时机 | 约束/来源 |
|----------|----------|-----------|
| "To the best of our knowledge, there is/are no [已有工作] to investigate [缺口]." | 标准空白声明（精确模板 2-3/21 篇；"there is/are no existing work(s)" 全语料 3 处变体） | ✅ 语料实测 |
| "To the best of our knowledge, X has not been comprehensively explored in prior works." | 语料变体（ASTARS-FL 篇原文） | 💡 语料实测 |
| "To the best of our knowledge, the performance of X ... is not researched yet." | 语料变体（STAR-RIS 篇原文） | 💡 语料实测 |
| "To the best of our knowledge, this paper is the first to conduct an analysis of X." | 首创性声明（RIS-AmBC 篇原文；另 MF-RIS 篇用 "this paper presents the first comprehensive analysis of X"） | 💡 语料实测 |
| "To the best of our knowledge, there is no related work to analyze X." | 语料变体（U-NOMA-BH 篇原文；R-NOMA-BF 篇用 "there are no related works to consider the resource optimization of X"） | 💡 语料实测 |
| "To the best of our knowledge, X have not been well evaluated." | 语料变体（Satellite 篇原文 "the outage behaviors of terrestrial users with ipSIC have not been well evaluated"） | 💡 语料实测 |
| "To the best of our knowledge, existing works are based on pSIC [x], which are difficult to realise in practical applications." | 针对已有工作假设局限（SGF 篇原文） | 💡 语料实测 |
| "To our knowledge, ... there currently are no treatises on X." | 去 best of 变体（covert 篇原文） | 💡 语料实测 |
| "However, the unique advantages offered by X remain underutilized in Y scenarios." | 技术未充分利用（ASTARS 篇原文） | 💡 语料实测 |
| "While the aforementioned works have laid a solid foundation for X, [新问题] remains an emerging area of study." | 引出新方向（语料高频开场，多个变体） | ✅ 语料实测 |
| "X is far from being well understood." | 领域理解不足（3/21 篇） | 💡 语料实测 |
| "X is still in its infancy." | 领域刚起步（注意：单数主语配 its；语料 "integration ... is still in their infancy" 为语法瑕疵，polishing 应纠正为 its） | 💡 语料实测 |
| "Although X has been studied, the integration of X and Y is still in its infancy." | 交叉领域空白（its，非 their） | 💡 课题组规范 |
| "This paper presents the first comprehensive analysis of X." | 声称首创性 | 💡 语料实测（MF-RIS 篇） |

## 3. 贡献陈述句式

| 动作 | 句式模板 | 约束/来源 |
|------|----------|-----------|
| **提出** | "We propose a novel X framework for Y, leveraging Z to achieve..." | ✅ 语料实测 |
| **推导** | "We derive the closed-form/asymptotic expressions of X for Y under Z conditions." | ✅ 语料实测 |
| **分析** | "We investigate/analyze the impact of X on Y in Z networks." | ✅ 语料实测 |
| **优化** | "We formulate the optimization problem to minimize/maximize X subject to..." | 💡 语料实测 |
| **验证** | "We demonstrate/confirm that the proposed X outperforms Y by Z% in terms of..." | 💡 语料实测 |
| **对比** | "Compared to/with X, the proposed Y..." | 💡 语料实测（语料高频形式） |
| **贡献三层递进** | "1) We [动作] [方案]. By [工具/方法], we [进一步动作]. [结论句]." | 💡 语料实测（编号结果组 i)/1) 高频） |

### 贡献点量化自查清单（✅ 每条贡献点必须自查）
每条贡献陈述应同时回答三个问题，缺一不可：
1. **动作动词**：propose / derive / investigate / formulate / demonstrate / confirm（避免无动词的名词化表述）；
2. **方法/对象**：对什么系统/指标/条件（如 "for STAR-RIS-NOMA networks with ipSIC/pSIC over Rician fading channels"）；
3. **成果/结论**：得到什么（closed-form expressions / diversity order / outperforms X by Z%）。
> 语料实测：21 篇贡献点均含"动作动词 + 方法/对象 + 成果/结论"三要素；仅含前两者的句子会被 reviewer 判定为贡献陈述不完整。

## 4. 贡献列表引导句（v1.2.0 新增）

> **实测口径**：约 15/21 篇在贡献列表前使用引导句，句式高度多样，均以 "summarized / are as follows" 收束。置于 Motivation 子节贡献列表之前。

| 句式模板 | 语料出处/说明 | 约束/来源 |
|----------|--------------|-----------|
| "The main contributions of this paper can be summarized as follows:" | 语料最高频（多篇原文，ASTARS-FL 篇用 "summarized below, which are explicitly contrasted to ... in Table I" 变体） | ✅ 语料实测 |
| "The primary contributions of this manuscript are summarized as follows:"（含 "... can be summarized in detail as follows:" 变体） | SGF 篇 / RIS-NOMA On-Off 篇原文 | 💡 语料实测 |
| "The major contributions of this paper can be summarized as follows:" | MF-RIS 篇原文 | 💡 语料实测 |
| "The essential contributions of our paper/article are summarized as follows:" | unified NOMA / U-NOMA-BH 篇原文 | 💡 语料实测 |
| "The basic contributions of the thesis are summarized as follows:" | R-NOMA-BF 篇原文（thesis 表述，学位论文风格） | 💡 语料实测 |
| "In summary, the following are the primary contributions of this paper:" | ASTARS-NOMA 篇原文（无 summarized 变体） | 💡 语料实测 |

## 5. 结果呈现句式

| 功能 | 句式模板 | 约束/来源 |
|------|----------|-----------|
| **章节开头** | "In this section, numerical/simulation results are presented to verify the accuracy of..." | ✅ 语料实测 |
| **引入图表** | "Fig. X plots the Y versus the Z, with [参数]."（**现在时**，语料 30+ 处全为现在时，plotted 0 处） | ✅ 语料实测 |
| **引入图表(变体)** | "Figure X illustrates/depicts/shows the Y versus the Z." | 💡 语料实测 |
| **趋势描述(上升)** | "The Y increases/improves/enhances with the increasing of X." | ✅ 语料实测 |
| **趋势描述(下降)** | "The Y decreases/reduces/deteriorates as X increases." | 💡 语料实测 |
| **趋势描述(趋近)** | "The Y converges to an error floor / approaches X in the high SNR region." | 💡 语料实测 |
| **趋势描述(匹配)** | "The exact analytical curves match perfectly with Monte Carlo simulations." | 💡 语料实测 |
| **观察发现** | "It can be observed from Fig. X that [发现]." | ✅ 语料实测（全语料 32 行；"It is observed from Fig. X that" 为低频变体） |
| **观察发现(高频变体)** | "One can observe that ... / As can be observed from the figure, ..." | ✅ 语料实测（One can observe 全语料 56 行、As can be observed 48 行） |
| **现象列举** | "One phenomenon is that ... Another phenomenon is that ..." | 💡 语料实测（Numerical Result 节高频） |
| **另一观察** | "Another observation is that [额外发现]." | 💡 语料实测（全语料 19 行） |
| **原因解释** | "This is because / This is due to the fact that [原因]." | ✅ 语料实测（注意：语料高频错误变体 "This is because that" 须纠正） |
| **原因解释(高频变体)** | "The reason is that ..." | ✅ 语料实测（全语料 40 行，Numerical Result 节最高频原因句式） |
| **原因解释(变体)** | "The reason behind this phenomenon is that ... / The basic reason for this phenomenon is that ..." | 💡 语料实测（各 2 行） |
| **多原因解释** | "The reasons are that: 1) ... 2) ... 3) ..." | 💡 语料实测（2 行） |
| **多原因解释(变体)** | "This is due to the fact that [原因1]. Another reason is that [原因2]." | 💡 语料实测 |
| **归因句式** | "This comes from the fact that ... / This is attributed to ..." | 💡 语料实测（This is attributed to 全语料 12 行） |
| **结果引出(编号)** | "Numerical results indicate that: i)... ii)... iii)..." | ✅ 语料实测 |
| **结果总起句** | "The simulation results verify the correctness of the formulas and yield the following insights: 1)... 2)... 3)..." | 💡 语料实测（PRIS-ARIS 篇原文） |
| **验证结论** | "Numerical results verify the correctness of the theoretical analyses and demonstrate that..." | ✅ 语料实测 |
| **双面论证** | "On the one hand, [正面效应]. This is because [解释]. On the other hand, [负面效应]." | 💡 语料实测（on the other hand 全语料 25 行） |
| **trade-off 权衡** | "[参数A] does not necessarily translate to better [性能]. Hence, it is crucial to consider the trade-off between [A] and [B]." | 💡 语料实测（"Due to the balance between X and Y, ... is not helpful" 为语料高频同义结构） |
| **顺序词串联** | "Numerical results firstly demonstrated [发现1]. Secondly, [发现2]. Finally, [发现3]." | 💡 语料实测 |

## 6. 过渡衔接句式

| 逻辑关系 | 句式模板 | 约束/来源 |
|----------|----------|-----------|
| **因果** | "Due to the balance between X and Y, introducing excessive Z is not helpful to reduce..." | ✅ 语料实测 |
| **转折** | "However, this approach can result in larger errors from users with poor channel conditions." | ✅ 语料实测 |
| **递进** | "Furthermore/Moreover, we also evaluate the impact of X on Y." | ✅ 语料实测 |
| **对比** | "Compared to X, the proposed Y achieves superior Z at high SNRs." | 💡 语料实测 |
| **举例** | "For example, by adopting X strategy, the Y can effectively reduce Z." | 💡 语料实测 |
| **强调** | "It is worth noting that / It is worth pointing out that [重要发现]." | 💡 语料实测 |
| **总结** | "In summary / To summarize, [关键结论]." | 💡 语料实测 |
| **动机过渡** | "... which motivates us to develop this treatise / which prompts us to develop this article / which motivates us to elaborate it." | 💡 语料实测（FD/HD、FD relay、U-NOMA-BH、R-NOMA-BF 篇原文） |
| **理论到讨论** | "On this basis, ... / Based on the analytical results, ... / Based on the asymptotic results, ..." | ✅ 语料实测（On this basis 全语料 21 行；Based on the analytical/asymptotic results 在 Abstract/Conclusion 高频） |

## 7. 论文组织句式

| 位置 | 句式模板 | 约束/来源 |
|------|----------|-----------|
| **论文结构** | "The rest of this paper is organized as follows. Section II presents... Section III discusses... Finally, Section V concludes this paper." | ✅ 语料实测（"The rest of this paper is organized as follows" 5+ 篇） |
| **符号说明(标准版)** | "Notations: Scalars, vectors, and matrices are denoted by lower-case, bold-face lower-case, and bold-face upper-case letters, respectively." | ✅ 课题组规范（IEEE 惯例；语料 17/21 篇含符号说明段落，位于 Introduction 的 Organization and Notation 子节） |
| **符号说明(续)** | "f_X(·) and F_X(·) denote the probability density function (PDF) and cumulative distribution function (CDF), respectively." | ✅ 课题组规范 |
| **未来工作(标准)** | "A promising future research direction is to extend the proposed framework to [新场景] by considering [新因素]." | ✅ 语料实测（Conclusion 节 7 行；10/21 篇含未来工作句） |
| **未来工作(续)** | "Our future work will consider the impact of imperfect CSI and take into account more complex assumptions." | ✅ 语料实测（ARIS-NOMA-HIS 篇原文；covert 篇用 "In our future work, we will explore..."） |
| **未来工作(间接)** | "... warranting consideration in future research." | 💡 语料实测（SGF 篇结尾） |

## 8. 特殊表达（语料实测高频）

| 表达 | 使用场景 | 约束/来源 |
|------|----------|-----------|
| "shed light on" | 讨论研究发现（语料 3 处） | 💡 语料实测 |
| "It is worth pointing out that" | 强调重要点 | 💡 语料实测 |
| "To reap more insights" | 引出深入分析 | 💡 语料实测 |
| "For the purpose of comparisons" | 引入基准对比 | 💡 语料实测 |
| "In light of the above works" | 总结已有工作 | 💡 语料实测 |
| "To be specific / More specifically" | 细化说明 | 💡 语料实测 |
| "From the perspective of practical applicability" | 实践意义讨论 | 💡 语料实测 |
| "It has been shown that / It was demonstrated that" | 被动确认句式（Conclusion 高频） | 💡 语料实测 |
