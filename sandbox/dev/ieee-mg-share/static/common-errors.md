# 常见表达错误与纠正表（v1.2.0）

> 来源：21 篇论文语料 grep 逐行复核 + 逐篇人工核验。未在语料出现者标注"通用语法知识 / 课题组规范"。
> 分级：**✅ 硬性纠正**（语料实证错误或通用语法错误，polishing 必须改）｜**💡 建议**（规范或密度优化，可改可不改）
> 每条附"错误来源"（语料文件:行号）；无来源者注明依据类型。
> 被 ieee-mg-polishing 引用；与 polishing core.md 同源条目以本文件实测为准。

## 1. 冠词错误

| 错误类型 | 错误示例 | 正确版本 | 分级 | 错误来源 |
|----------|----------|----------|:----:|----------|
| 可数名词缺冠词 | "Numerical results are presented to verify accuracy of..." | "...to verify **the** accuracy of..." | ✅ | 语料 6+ 篇均为 "verify the accuracy of"（Abstract.md:22, 26, 42, 62 等）；缺冠词形式 0 命中 |
| 多余定冠词 | "the performance of the proposed scheme is superior than the OMA" | "...is superior **to that of** the OMA" | ✅ | "superior to that of" 语料高频（Abstract.md:18, 46, 54 等）；superior than 见 §2 |
| 抽象名词不用 the | "the fractional order calculus is used" | "fractional order calculus is used" | 💡 | 通用语法知识 |
| 序数词/最高级缺 the | "first step is to" | "the first step is to" | 💡 | 通用语法知识 |

## 2. 介词搭配（v1.2.0 语料实测重写）

| 错误 | 正确 | 分级 | 错误来源 |
|------|------|:----:|----------|
| "Similar with" | "Similar **to**" | ✅ | Numerical Result.md:224（"Similar with the principle of the Doppler-shift-based algorithm"） |
| "independent to" | "independent **of**" | ✅ | All Paper Title.md:818 / Introduction.md:214（"Each reflecting element is independent to adjust..."） |
| "outperforms than" | "outperforms"（than 为赘词） | ✅ | Abstract.md:30（"The outage behaviors ... outperforms than that of OMA"） |
| "the superior of X" | "the **superiority** of X" | ✅ | Conclusion.md:114；另 Numerical Result.md:1162, 1194（共 3 处） |
| "compare to"（动词原形缺 -d） | "compared **to**" | ✅ | Numerical Result.md:1223（"the performance of NOMA compare to the ipSIC"） |
| "superior than" | "superior **to**" | ✅ | 通用语法知识（语料 0 命中，预防性） |
| "This is because that" | "This is because" | ✅ | 语料 20+ 处（All Paper Title.md:306, 569, 680, 782, 875, 893, 1002, 1103, 1111, 1115, 1221；Numerical Result.md:769, 773, 797, 879, 991, 1077, 1174, 1305, 1359 等） |

> **说明（v1.2.0 修正）**："compared with" 与 "compared to" **均合法**——compared with 强调对比差异、compared to 强调类比/比较。语料二者混用（compared with：Abstract.md:50, 74、All Paper Title.md:433 等；compared to：Abstract.md:2, 58, 62, 66 及 Numerical Result.md 大量），**不作为错误纠正**。真正的错误是动词原形 "compare to"（缺 -d，Numerical Result.md:1223）。
>
> **已删除条目（v1.2.0）**：以下条目语料 0 命中，属无源伪造，删除："different with"（正确形式 different from 见 All Paper Title.md:324, 441、Numerical Result.md:151, 224）、"in the basis of"（正确形式 on the basis of 见 All Paper Title.md:423, 445, 1006, 1464）、"independent from"、"dependent to"。

## 3. 主谓一致

| 错误 | 正确 | 分级 | 错误来源 |
|------|------|:----:|----------|
| "the performance of X are" | "the performance of X is" | ✅ | 通用规则（语料同源错误见下） |
| "the results of X shows" | "the results of X show" | ✅ | 通用规则 |
| "the number of elements are" | "the number of elements is" | ✅ | 通用规则 |
| "The FL accuracy ... are enhanced" | "...**is** enhanced" | ✅ | Abstract.md:2 |
| "verify the correctness of the formulas and yields" | "...formulas and **yield**"（and 并列接动词原形） | ✅ | Abstract.md:30 |
| "we plots" | "we **plot**" | ✅ | Numerical Result.md:1283 |
| "Fig. 6 further give" | "Fig. 6 further **gives**" | ✅ | Numerical Result.md:1174 |
| "The system throughput ... were discussed" | "...**was** discussed" | ✅ | Conclusion.md:102 |

## 4. 时态混用（v1.2.0 修正）

| 场景 | 正确时态 | 分级 | 错误来源 |
|------|----------|:----:|----------|
| Abstract 中描述论文内容 | 一般现在时："This paper investigates..." | ✅ | 21 篇摘要主流 |
| Introduction 中描述已有工作 | 一般过去时为主，另有现在完成时（"have demonstrated"）与现在时（"the authors of [14] demonstrate"）三型并存 | ✅ | Introduction.md 语料 |
| **图描述（主语式）** | **一般现在时："Fig. X plots/illustrates..."**——语料 30+ 处（Fig. 2/3/4/5/6/7/8/9/10/11/12 plots、Fig. 2(a) plots、Fig. 3 compares、Fig. 4 depicts 等）；"Fig. X plotted" 0 命中 | ✅ | Numerical Result.md / All Paper Title.md 全文 |
| 曲线绘制依据（被动分词） | "are plotted according to (X)" 为合法结构，非时态错误 | ✅ | Numerical Result.md:1158, 1223, 1267, 1283 等 |
| 仿真过程描述 | 可用过去时："The simulation was conducted"（标准学术惯例）；语料 Results 章节开头亦常用现在时 "This section conducts simulation experiments" | 💡 | All Paper Title.md:58 |
| Conclusion 回顾工作 | 现在完成时为主流（约 15/21 篇），过去时/现在时亦合法（约 6/21 篇），不强制 | 💡 | Conclusion.md:6, 12, 24 等 |
| 同一段落内时态反复切换 | 按功能分句保持时态一致 | ✅ | 通用规则 |

## 5. 缩略语不规范

| 错误 | 正确 | 分级 | 错误来源 |
|------|------|:----:|----------|
| 正文首次出现用缩略语 | 正文首次出现必须用全称 + 缩略语 | ✅ | 通用规范（语料一致遵循） |
| "We study NOMA (Non-orthogonal Multiple Access)" | "Non-orthogonal Multiple Access (NOMA)" | ✅ | Abstract.md 全文 |
| Abstract 中定义了但正文不再定义 | 正文首次出现仍需定义（Abstract 独立于正文） | ✅ | 通用规范 |
| 标题中使用缩略语 | 课题组投稿规范：标题可含缩略语（语料 18/21 篇标题含缩略语），但正文首次出现处仍需全称定义 | 💡 | 课题组规范（非语料规律） |
| 缩略形式 "doesn't" / "it's" | 学术写作禁用缩略形式 → "does not" / "it is" | ✅ | All Paper Title.md:593（doesn't）、:1115（it's）——课题组规范，语料偶见反例，polishing 需纠正 |

## 6. 数学符号不规范（通用排版规范）

| 错误 | 正确 | 分级 |
|------|------|:----:|
| 变量用正体 x | 变量用斜体 $x$ | 💡 |
| 向量用大写 X | 向量用粗体小写 $\mathbf{x}$ | 💡 |
| 矩阵用普通斜体 | 矩阵用粗体大写 $\mathbf{X}$ | 💡 |
| 尚未定义就使用符号 | 每个符号首次使用时立即定义 | 💡 |
| 期望写作 E{x} | 应写作 $\mathbb{E}\{x\}$ | 💡 |
| 无公式编号 | 每个关键公式都应有编号 | 💡 |

> 本节为期刊排版通用知识（语料为纯文本无法 grep 验证），不做硬性纠正。

## 7. 冗余表达（v1.2.0 修正）

| 冗余 | 精简 | 分级 | 错误来源 |
|------|------|:----:|----------|
| "It is can be seen that" | "It **can** be seen that"（删除多余 is） | ✅ | Numerical Result.md:391, 1251（另 "it is can be observed" :423） |
| "It can be observed that ..." | 可精简为直接陈述以提升密度——**注意：语料 8+ 处高频，属规范观察句式，不是错误**，仅在段内连用时精简 | 💡 | All Paper Title.md:206, 208, 224, 310, 487, 573 等 |
| "From the figure we can see that" | "Fig. X demonstrates that..."（可选精简） | 💡 | "From the figure we can observe/see" 语料多处（All Paper Title.md:212, 230） |
| "In the following section, we will discuss" | "Section III discusses..." | 💡 | 通用知识 |
| "It should be noted that" | 语料高频变体为 "It is worth noting that"（Numerical Result.md 多处）；两者均合法，仅密度优化时精简 | 💡 | 通用知识 |

> **图引用句式（语料实证，v1.2.0 替换原 "It is shown from Fig. X that" 条目）**：
> "It is shown from Fig. X that" 语料 0 命中，勿用。语料高频句式：
> - "It can be seen from Fig. X that ..."（Numerical Result.md:999, 1283；All Paper Title.md:328）
> - "As can be seen from the figure, ..."（Numerical Result.md:1198, 1223）
> - "As can be observed from the figure, ..."（Numerical Result.md:1077, 1223 等）
> "It is shown that" 仅用于从句（Numerical Result.md:1166, 1267），不作图引用句。

## 8. 词汇使用不精确（风格建议）

| 模糊/不准确用词 | 精确用词 | 分级 |
|----------------|----------|:----:|
| "good performance" | 具体指标："achieves 30% higher SE" | 💡 |
| "very important" | "critical / essential / crucial" | 💡 |
| "a lot of" | "a significant number of / substantial" | 💡 |
| "big difference" | "considerable difference / significant discrepancy" | 💡 |
| "things" | 具体名词：factors, elements, components | 💡 |
| "get better results" | "achieve superior performance" | 💡 |

> 本节为通用风格建议（语料无法直接计数），不做硬性纠正。注意：**"better" 本身不是错误**（语料大量使用 "provides better outage probability"），仅建议优先使用 superior/significant 等更精确词。

## 9. 引用格式错误（通用规范）

| 错误 | 正确 | 分级 |
|------|------|:----:|
| 引用未编号："(Smith et al., 2020)" | "[1]" | ✅ |
| 引用太密："[1][2][3][4][5]" | "[1]-[5]" 或 "[1],[2],[3]" | ✅ |
| 引用在句号之外 | 引用在句号之内："...was proposed [1]." | ✅ |
| 人名直接出现在正文中 | 使用编号引用："The authors in [1]..." | ✅ |
