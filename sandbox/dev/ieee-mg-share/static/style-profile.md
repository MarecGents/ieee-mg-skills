# 课题组全局风格画像

> 基于课题组 21 篇 IEEE Trans/期刊论文语料蒸馏。本文件定义了所有写作/润色必须遵循的全局风格基准。
> 被 ieee-mg-writing 和 ieee-mg-polishing 共同引用。

## 1. 学术正式度

| 维度 | 定量特征 |
|------|----------|
| **被动语态比例** | 约 35%-45%（Abstract 中偏高 ~45%，Motivation 中偏低 ~35%） |
| **第一人称频率** | "we" 平均每千词出现 8-12 次，用于 propose/derive/formulate/demonstrate 等动作 |
| **主要情态动词** | can（可能性/能力）> may（许可）> could（委婉/假设）> might（低概率推测） |
| **否定表达** | 较少使用直接否定（"not"），更多使用委婉否定："remains unexplored"、"has not been comprehensively explored"、"is still in its infancy" |
| **缩略形式** | 禁止使用缩略形式（don't → do not, can't → cannot, it's → it is） |

## 2. 句式复杂度

| 维度 | 定量特征 |
|------|----------|
| **平均句长** | 18-25 词（Abstract ~18 词偏短，Introduction ~25 词偏长） |
| **从句密度** | 每句 0.8-1.5 个从句，which/that 引导的定语从句最常见（>60%） |
| **插入语** | 较少使用括号插入，更多使用逗号分隔的非限制性定语从句 |
| **典型复合句模式** | "By + V-ing ..., X is capable of ... while ..." |
| **平行结构** | 编号列表 (i)(ii)(iii) 和 1)2)3)4) 使用平行语法结构 |

## 3. 时态使用图谱

| 章节 | 主要时态 | 次要时态 | 例句 |
|------|----------|----------|------|
| **Abstract** | 一般现在时 | 现在完成时 | "This paper investigates... We derive..." / "X has attracted growing interest..." |
| **Introduction** | 一般现在时（背景/本文内容） | 一般过去时（已有工作） | "RIS has been deemed as... The authors in [x] proposed..." |
| **System Model** | 一般现在时 | — | "We consider a system where... The channel coefficient is given by..." |
| **Motivation** | 一般现在时 | 现在完成时 | "While prior works have laid... This paper seeks to investigate..." |
| **Numerical Results** | 一般过去时（描述仿真过程） | 一般现在时（观察/讨论） | "Fig. X plotted... It is observed that..." |
| **Conclusion** | 现在完成时（回顾工作） | 一般现在时（总结发现） | "We have investigated... Numerical results demonstrate that..." |

## 4. 高频词汇库

### 4.1 高频动词（按场景）

| 场景 | 高频动词 | 使用频率 |
|------|----------|----------|
| **提出方案** | propose, introduce, develop, design | ★★★★★ |
| **理论推导** | derive, obtain, formulate, establish | ★★★★★ |
| **分析评估** | investigate, analyze, study, examine, survey | ★★★★ |
| **性能验证** | demonstrate, validate, verify, confirm | ★★★★ |
| **性能对比** | outperform, surpass, exceed, achieve | ★★★ |
| **性能描述** | improve, enhance, reduce, mitigate | ★★★ |
| **问题公式化** | formulate, define, characterize, model | ★★★ |
| **讨论说明** | discuss, illustrate, indicate, reveal | ★★★ |

### 4.2 高频形容词/副词

| 词类 | 高频词（按频率降序） |
|------|----------------------|
| **形容词** | novel, superior, significant, robust, comprehensive, extensive, promising, effective, efficient, optimal, favorable, superior, inferior, tractable, closed-form |
| **副词** | significantly, substantially, remarkably, particularly, extensively, respectively, approximately, explicitly |

### 4.3 常用学术搭配

| 搭配 | 使用场景 |
|------|----------|
| "lay a solid foundation for" | 综述已有工作 |
| "to the best of our knowledge" | 引出研究空白 |
| "fill the gap / bridge the gap" | 指出本文贡献 |
| "shed light on" | 讨论研究发现 |
| "be in its infancy" | 描述新兴领域 |
| "be proportional to" | 描述线性关系 |
| "converge to an error floor" | 描述 ipSIC 影响 |
| "match perfectly with" | 描述理论与仿真吻合 |

## 5. 逻辑连接词网络

按使用频率降序排列：

| 功能 | 首选词 | 次选词 | 使用场景示例 |
|------|--------|--------|-------------|
| **因果** | due to / because of | owing to, as a result, as a consequence, thereby, hence | 结果解释、原因分析 |
| **转折** | however | nevertheless, although, whereas, in contrast, yet, while | 研究空白、结果对比 |
| **递进** | moreover | furthermore, in addition, additionally, besides, notably | 贡献列点、补充说明 |
| **对比** | compared to | in contrast, on the other hand, conversely, alternatively | 方案比较、基准对比 |
| **举例** | such as | e.g., for example, for instance, including | 技术列举 |
| **强调** | in particular | specifically, notably, particularly, especially | 重点发现 |
| **结论** | therefore | thus, consequently, accordingly, as a result | 总结推导 |
| **条件** | provided that | subject to, given that, under the condition that | 约束条件 |

## 6. 数学表达规范

- 变量：斜体 $x$
- 向量：粗体小写 $\mathbf{x}$
- 矩阵：粗体大写 $\mathbf{X}$
- 集合：花体 $\mathcal{X}$
- 复数/实数集：黑板粗体 $\mathbb{C}$、$\mathbb{R}$
- 期望/方差：$\mathbb{E}\{\cdot\}$、$\mathbb{D}\{\cdot\}$
- 转置/共轭转置：$(\cdot)^T$、$(\cdot)^H$
- 概率密度/累积分布函数：$f_X(\cdot)$、$F_X(\cdot)$
- 公式编号：全文章节内连续编号
- 公式后标点：每个公式后跟逗号或句号
