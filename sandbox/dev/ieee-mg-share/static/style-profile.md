# 课题组全局风格画像

> 基于课题组 21 篇 IEEE Trans/期刊论文语料蒸馏。本文件定义了所有写作/润色必须遵循的全局风格基准。
> 被 ieee-mg-writing、ieee-mg-polishing 和 ieee-mg-reviewer 共同引用。
> **统计口径（v1.2.0）**：本文频次/占比均为 grep 行级计数估算（6 个语料文件；All Paper Title.md 为汇总快照，与各章节文件存在重复行，数字含重复计数），部分为课题组印象分，均已逐条标注；与 quantitative-baseline.md 冲突处以后者为准；与目标稿件实测冲突时以稿件实测为准。
> **约束等级（v1.2.0）**：✅ = 硬约束（写作/润色必须遵守）；💡 = 软约束（风格建议，可依上下文调整）。

## 1. 学术正式度

| 维度 | 定量特征 | 约束 |
|------|----------|------|
| **被动语态比例** | Abstract 40%-50%，其余章节（Introduction/Motivation/Numerical Results/Conclusion）30%-40%。估算值（无 POS 标注统计佐证），与 quantitative-baseline.md 一致 | 💡 |
| **第一人称频率** | "we" 平均每千词约 6-8 次（Abstract 实测 6.5/千词），16/21 篇摘要使用（≈76%），用于 propose/derive/formulate/demonstrate 等动作 | 💡 |
| **主要情态动词** | can（可能性/能力）使用最普遍 > may（许可）> could（委婉/假设）> might（低概率推测）。该排序为课题组定性印象，无计数依据；Introduction 内 may/could/might 用例极少 | 💡 |
| **否定表达** | 较少使用直接否定（"not"），更多使用委婉否定："there is no existing work..."、"is not researched yet"、"is still in its infancy"（语料实测高频） | 💡 |
| **缩略形式** | 课题组规范：禁止使用缩略形式（don't → do not, can't → cannot, it's → it is）。注：语料偶见反例（doesn't、it's 各 1 句，见 Numerical Result.md:330/636），polishing 环节需纠正为规范形式 | ✅ |

## 2. 句式复杂度

| 维度 | 定量特征 | 约束 |
|------|----------|------|
| **平均句长** | 定性：Abstract 偏短、Introduction 偏长。抽样口径：6 篇 Abstract 抽样均值约 25-29 词/句（含编号结果长句），未做全量统计，不作精确断言 | 💡 |
| **从句密度** | 每句 0.8-1.5 个从句（课题组印象分），which/that 引导的定语从句最常见 | 💡 |
| **插入语** | 较少使用括号插入，更多使用逗号分隔的非限制性定语从句 | 💡 |
| **典型复合句模式** | "By + V-ing ..., X is capable of ... while ..."（语料实测高频） | 💡 |
| **平行结构** | 编号列表 i) ii) iii) 和 1) 2) 3) 4)（无括号）使用平行语法结构（语料实测标准格式） | ✅ |

## 3. 时态使用图谱

| 章节 | 主要时态 | 次要时态 | 例句 | 约束 |
|------|----------|----------|------|------|
| **Abstract** | 一般现在时 | 现在完成时 | "This paper investigates... We derive..." / "X has attracted growing interest..." | ✅ |
| **Introduction** | 一般现在时（背景/本文内容） | 一般过去时（已有工作） | "RIS has been deemed as... The authors in [x] proposed..." | ✅ |
| **Introduction 引用句三型** | 三型并存：① 一般过去时 "The authors in [x] proposed/investigated..."；② 现在完成时 "Prior studies have demonstrated..." / "have proposed"；③ 一般现在时 "the authors of [14] demonstrate/model..." | — | 语料实测三型均高频，写作时按语境自然选择 | 💡 |
| **System Model** | 一般现在时 | — | "We consider a system where..."（⚠ 本节无对应语料，为外部通用知识，非语料蒸馏） | ✅ |
| **Motivation** | 一般现在时 | 现在完成时 | "While prior works have laid... This paper seeks to investigate..." | ✅ |
| **Numerical Results** | 一般现在时（图描述/观察） | 一般过去时（仿真过程，可选） | **图描述必须现在时："Fig. X plots the ... versus the ..."（语料 30+ 处实证，plotted 0 处）**；观察句 "It is observed that..."（语料低频变体，高频为 "It can be observed that / One can observe that"） | ✅ |
| **Conclusion** | 现在完成时（回顾工作，约 15/21 篇） | 一般现在时（总结发现）；一般过去时/现在时为合法变体（约 6/21 篇） | "This paper has investigated... Numerical results demonstrate that..."。注：不强制现在完成时开头，"In this paper, we investigated..."（2 篇）等变体语料实证合法 | 💡 |

## 4. 高频词汇库

### 4.1 高频动词（按场景；星级为课题组印象分，非精确计数）

| 场景 | 高频动词 | 使用频率 |
|------|----------|----------|
| **提出方案** | propose, introduce, develop, design | ★★★★★ |
| **理论推导** | derive, obtain, formulate, establish | ★★★★★ |
| **分析评估** | investigate, analyze, study, examine, survey | ★★★★ |
| **性能验证** | demonstrate, validate, verify, confirm, substantiate | ★★★★ |
| **性能对比** | outperform, surpass, exceed, achieve, precede | ★★★★（outperform 语料高频，高于早期 ★★★ 档） |
| **性能描述** | improve, enhance, reduce, mitigate | ★★★ |
| **问题公式化** | formulate, define, characterize, model | ★★★ |
| **讨论说明** | discuss, illustrate, indicate, reveal, manifest | ★★★（indicate/reveal/manifest 为语料实测高频结果引出词） |

### 4.2 高频形容词/副词

| 词类 | 高频词（按频率降序） |
|------|----------------------|
| **形容词** | novel, superior, significant, robust, comprehensive, extensive, promising, effective, efficient, optimal, favorable, inferior, tractable, closed-form |
| **副词** | significantly, substantially, remarkably, particularly, extensively, respectively, approximately, explicitly |

### 4.3 常用学术搭配

| 搭配 | 使用场景 |
|------|----------|
| "lay a solid foundation for" | 综述已有工作（语料 6+ 处） |
| "to the best of our knowledge" | 引出研究空白（12/21 篇精确模板，另有 To our knowledge 变体） |
| "be in its infancy" | 描述新兴领域（语料 5+ 处；注意单数主语配 its） |
| "bridge the gap caused by X" | **描述残余干扰/非理想因素造成的性能差距**（语料 3 处均为此义，如 "a larger κ is required to bridge the gap caused by ipSIC"；勿用于贡献声明） |
| "shed light on" | 讨论研究发现（语料 3 处） |
| "be proportional to" | 描述线性关系 |
| "converge to an error floor" | 描述 ipSIC 等造成的性能平层（语料高频） |
| "match perfectly with" | 描述理论与仿真吻合 |
| "converge to a throughput ceiling" | 描述吞吐量上限 |

## 5. 逻辑连接词网络

> 按功能分类，按使用频率降序（grep 行级计数，5 个章节分文件口径；全语料含 Title 快照约为 1.5-2 倍，相对排序一致）。

| 功能 | 首选词 | 次选词 | 使用场景示例 | 约束 |
|------|--------|--------|-------------|------|
| **因果** | due to（≈117 行） | because of（≈3 行，少用）, owing to（≈9 行）, as a result（≈23 行）, thereby（≈27 行） | 结果解释、原因分析 | 💡 |
| **转折** | however（≈105 行） | although（≈20 行）, whereas（≈13 行）, in contrast（≈18 行）, nevertheless（≈8 行）, while | 研究空白、结果对比 | 💡 |
| **递进** | furthermore（≈90 行） | in addition（≈84 行）> additionally（≈66 行）> moreover（≈67 行，与 additionally 同档）> besides, notably（语料极少） | 贡献列点、补充说明 | 💡 |
| **对比** | compared to / compared with（两者均高频，均为规范英语） | in contrast, on the other hand, conversely, alternatively | 方案比较、基准对比 | 💡 |
| **举例** | such as（≈15 行） | e.g., for example（≈6 行）, for instance, including | 技术列举 | 💡 |
| **强调** | specifically（≈57 行） | in particular（≈16 行）> particularly, especially, notably（语料极少） | 重点发现 | 💡 |
| **结论** | hence（≈44 行）/ thus（≈27 行）/ therefore（≈21 行） | consequently（≈9 行）, accordingly, as a result | 总结推导 | 💡 |
| **条件** | provided that | subject to, given that, under the condition that | 约束条件 | 💡 |

> 注：连接词选择以功能与上下文为准，不必刻意堆砌高频词；同段内同功能词不超过 2 次（详见 logic-connectors.md）。本表为 5 章节分文件口径，logic-connectors.md 为全语料 6 文件口径（约 1.5-2 倍），数值不同系口径差异，相对排序一致。

## 6. 数学表达规范

- 变量：斜体 $x$ ✅
- 向量：粗体小写 $\mathbf{x}$ ✅
- 矩阵：粗体大写 $\mathbf{X}$ ✅
- 集合：花体 $\mathcal{X}$ ✅
- 复数/实数集：黑板粗体 $\mathbb{C}$、$\mathbb{R}$ ✅
- 期望/方差：$\mathbb{E}\{\cdot\}$、$\mathbb{D}\{\cdot\}$ ✅
- 转置/共轭转置：$(\cdot)^T$、$(\cdot)^H$ ✅
- 概率密度/累积分布函数：$f_X(\cdot)$、$F_X(\cdot)$ ✅
- 公式编号：全文章节内连续编号 ✅
- 公式后标点：每个公式后跟逗号或句号 ✅
- （本节为 IEEE 排版规范，语料为纯文本无法 grep 验证，属外部通用知识）✅

## 7. 判断边界（v1.2.0 新增）

### 何时该用 / 不该用本层数据

- ✅ **该用**：目标论文属语料覆盖领域（NOMA/RIS/STARS、物理层安全、隐蔽通信等 IEEE Trans 风格）时，本画像可直接作为风格基准。
- ❌ **不该用**：主题超出语料领域、或目标期刊风格差异大时，不得将本画像特征冒充"语料实测"。

### 数据缺失降级策略

- 本文件无计数依据的条目（情态动词排序、动词星级、句长等"印象分"）不得升级为精确统计，引用时注明"估算/印象"。
- 语料无对应数据时（如 System Model 时态行），以通用 IEEE 学术写作规范兜底，并标注"非语料蒸馏"。

### 语料与目标期刊规范冲突

- 语料习惯与目标期刊官方规范（如 IEEE 作者指南）冲突时，以目标期刊为准，并在交付物中标注差异（如"语料习惯 X，已按 IEEE 规范改为 Y"）。
