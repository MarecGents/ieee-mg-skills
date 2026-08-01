# 常见表达错误与纠正表

> 从课题组 21 篇论文语料中提取的反复出现的小错误。供 writing 避坑和 polishing 纠错参考。
> 被 ieee-mg-polishing 引用。

## 1. 冠词错误

| 错误类型 | 错误示例 | 正确版本 | 频率 |
|----------|----------|----------|:----:|
| 可数名词缺冠词 | "in this section, numerical results are presented to verify accuracy of..." | "...the accuracy of..." | ★★★ |
| 多余定冠词 | "the performance of the proposed X is superior than the OMA" | "...superior to that of OMA" | ★★ |
| 抽象名词不用 the | "the fractional order calculus is used" | "fractional order calculus is used" | ★ |
| 序数词/最高级缺 the | "first step is to" | "the first step is to" | ★ |

## 2. 介词搭配

| 错误 | 正确 | 频率 |
|------|------|:----:|
| "compare with" (对比差异) | "compared to" (用于一般比较) | ★★★ |
| "superior than" | "superior to" | ★★ |
| "different with" | "different from" | ★★ |
| "in the basis of" | "on the basis of" | ★ |
| "independent from" | "independent of" | ★ |
| "dependent to" | "dependent on" | ★ |

## 3. 主谓一致

| 错误 | 正确 |
|------|------|
| "the performance of X are" | "the performance of X is" |
| "the results of X shows" | "the results of X show" |
| "a set of users is" | "a set of users are" (英式用 is，美式/工程用 are) |
| "the number of elements are" | "the number of elements is" |

## 4. 时态混用

| 错误场景 | 正确时态 |
|----------|----------|
| Abstract 中用过去时描述论文内容 | 用一般现在时："This paper investigates..." |
| Introduction 中描述已有工作用现在时 | 用一般过去时："The authors in [x] proposed..." |
| Results 中用现在时描述仿真过程 | 用一般过去时："Fig. X plotted..." |
| Conclusion 中用一般过去时回顾工作 | 用现在完成时："We have investigated..." |
| 同一段落内时态反复切换 | 按功能分句保持时态一致 |

## 5. 缩略语不规范

| 错误 | 正确 |
|------|------|
| 正文首次出现用缩略语 | 正文首次出现必须用全称 + 缩略语 |
| "We study NOMA (Non-orthogonal Multiple Access)" | "Non-orthogonal Multiple Access (NOMA)" |
| Abstract 中定义了但正文不再定义 | 正文首次出现仍需定义（Abstract 独立于正文） |
| 标题中使用缩略语 | 标题中尽量不用缩略语 |

## 6. 数学符号不规范

| 错误 | 正确 |
|------|------|
| 变量用正体 x | 变量用斜体 $x$ |
| 向量用大写 X | 向量用粗体小写 $\mathbf{x}$ |
| 矩阵用普通斜体 | 矩阵用粗体大写 $\mathbf{X}$ |
| 尚未定义就使用符号 | 每个符号首次使用时立即定义 |
| 期望写作 E{x} | 应写作 $\mathbb{E}\{x\}$ |
| 无公式编号 | 每个关键公式都应有编号 |

## 7. 冗余表达

| 冗余 | 精简 |
|------|------|
| "It is shown from Fig. X that..." | "Fig. X shows that..." |
| "It can be observed that from the figure" | 直接陈述观察结果 |
| "From the figure we can see that" | "Fig. X demonstrates that..." |
| "In the following section, we will discuss" | "Section III discusses..." |
| "It should be noted that" | 直接陈述即可 |
| "At this point in time" | "Currently" 或 "Now" |

## 8. 词汇使用不精确

| 模糊/不准确用词 | 精确用词 |
|----------------|----------|
| "good performance" | 具体指标："achieves 30% higher SE" |
| "very important" | "critical / essential / crucial" |
| "a lot of" | "a significant number of / substantial" |
| "big difference" | "considerable difference / significant discrepancy" |
| "things" | 具体名词：factors, elements, components |
| "get better results" | "achieve superior performance" |

## 9. 引用格式错误

| 错误 | 正确 |
|------|------|
| 引用未编号："(Smith et al., 2020)" | "[1]" |
| 引用太密："[1][2][3][4][5]" | "[1]-[5]" 或 "[1],[2],[3]" |
| 引用在句号之外 | 引用在句号之内："...was proposed [1]." |
| 人名直接出现在正文中 | 使用编号引用："The authors in [1]..." |
