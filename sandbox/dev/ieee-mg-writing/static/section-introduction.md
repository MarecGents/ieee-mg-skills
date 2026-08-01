# Introduction（引言）写作模板

> 基于课题组 21 篇 IEEE Trans 论文引言语料深度蒸馏。
> **核心结构**：5 层漏斗式宏观架构 + 文献综述（编号段落式或子节式）+ 编号贡献列表
> **约束分级（v1.2.0）**：✅ 硬约束 / 💡 软约束。

## 一、5 层宏观架构

### Layer 1：大背景（1-2 段）
引出领域的广阔背景和发展趋势。

**典型打开方式（语料实测，21 篇逐篇核验）：**

| 模式 | 实测占比 | 示例 |
|------|:--------:|------|
| **"With the development/advance of X..."** | ~52%（11/21，居首） | "With the rapid development of machine learning and artificial intelligence technologies..." |
| **"As X advances..."** | ~24%（5/21） | "As wireless communication technology rapidly advances, considerable challenges related to extensive connectivity..." |
| **直接陈述** | ~14%（3/21） | "Building upon the previous sections, the literature on single RIS analysis has become abundant..." |
| **"X has been deemed as..."** | ~10%（2/21） | "RIS has been deemed as one of the promising wireless technologies for 6G networks..." |
| **"The novel X has recently..."** | 0（示例实出自 Abstract，勿用于引言） | — |

**Layer 1 必备要素：**
- [✅] 点明领域的重要性和发展背景
- [✅] 引用 2-5 篇宏观综述/背景文献（实测可更多：FL 篇首段 [1]-[6]、STARS-SGF 背景段 [1]-[17]）
- [✅] 引出本文涉及的核心技术方向

### Layer 2：技术演进（1-2 段）
从传统技术到最新进展的 S 曲线叙述。

**叙述策略（语料中三种模式）：**

**模式 A：问题驱动**（最常见）
```
[传统方法] → [局限性] → [逐步改进] → [最新进展]
```

**模式 B：对比驱动**
```
[方法 A：优点&局限] → [方法 B：优点&局限] → [方法 C：最新方案]
```

**模式 C：时间线驱动**
```
[早期工作] → [近期进展] → [最新突破]
```

**Layer 2 核心技术词汇：**
- 传统方法：traditional, conventional, classical
- 局限性：however, suffer from, be limited by, face challenges
- 改进：to address these challenges, researchers have proposed
- 最新：recently, more recently, state-of-the-art

**引用密度（💡 局部适用）**：技术演进段保持高引用密度（每句至少 1 个引用，关键句可叠加 2-3 个；段落总引用 8-15 个）。注意：此密度要求仅适用于综述密集段落，不适用于全文。

### Layer 3：文献综述（2-4 段）

**课题组两种标准组织方式（语料实测）：**

**方式 A：编号段落式（1) [Category]: ...）**（约 10%，2/21 篇，如 SGF 篇 "1) SGF-NOMA Networks: ..."）
```
1) [Category Name]: ... [x], [x], [x] ...
2) [Category Name]: ... [x], [x], [x] ...
3) [Category Name]: ... [x], [x], [x] ...
```

**方式 B：子节式（### A. Previous Works + 编号段落）**（SGF 篇等）
```
### A. Previous Works
**1) [Category A]:** [正文段落，引用3-8篇文献]
**2) [Category B]:** [正文段落，引用3-8篇文献]
**3) [A+B Integration]:** [交叉研究段落]
```

**引用句式库（语料实测）：**

| 功能 | 句式 | 示例 |
|------|------|------|
| **正面介绍** | "The authors in [x] proposed/investigated..." | "The authors in [15] proposed an adaptive FL algorithm..." |
| **归类引用** | "Prior studies have demonstrated..." | "Prior studies have demonstrated that RIS can reduce errors..." |
| **研究现状** | "X has been extensively studied..." / "the literature on X has become abundant" | "the literature on single RIS analysis has become abundant..." |
| **文献编号开头** | "In [x], the authors proposed/investigated..." | "In [16], the authors introduced a distributed stochastic gradient descent approach..." |
| **开创性工作** | "A seminal work proposed X [x]." | "A seminal work proposed a hardware model for ASTARS..." |
| **被动语态引用** | "X was studied/analyzed/investigated in [x]." | "the outage probability of SGF-NOMA networks under the dynamic protocol was analyzed in two scenarios" |
| **过渡到空白** | "However, ... is not researched yet" | "However, the integration of X in Y is not researched yet" |

**综述段内部过渡**：交替使用自然承接（无过渡词）、主题引导短语、引用开头、同位语嵌入等 ≥5 种手法，避免 ≥3 句连续以单词过渡词开头（详见 ../ieee-mg-share/static/paragraph-rhythm.md 第 4 节）。

### Layer 4：研究空白 & 动机（1-2 段）

**研究空白声明句式（语料实测，12/21 篇精确使用 "To the best of our knowledge"，约 67% 论文含空白声明）：**
```
To the best of our knowledge, there is/are no [已有工作] to investigate/consider [研究空白].
```
- "To the best of our knowledge, there are no existing works to investigate the RS scheme for FD cooperative NOMA networks."
- "To the best of our knowledge, there is no existing work investigating the impact of the direct link for FD user relaying on the network performance."
- "To the best of our knowledge, the performance of STAR-RIS-NOMA with ipSIC/pSIC over Rician fading channels is not researched yet."
- "To the best of our knowledge, this paper is the first to conduct an analysis of the physical layer security performance of RIS-AmBC networks."

**空白句式变体（语料实测，均可用）：**
- "To the best of our knowledge, X has not been comprehensively explored in prior works."（ASTARS-FL 篇原文）
- "To the best of our knowledge, there is no related work to analyze X."
- "To the best of our knowledge, X have not been well evaluated."
- "To our knowledge, ... there currently are no treatises on X."（去 best of 变体）

**动机扩展句式：**
| 句式 | 频率 | 示例 |
|------|:----:|------|
| "While the aforementioned works..." | 高 | "While the aforementioned works have laid a solid foundation for understanding SGF-NOMA and STARS, the promising integration is still in their infancy." |
| "Motivated by this gap/inspiration..." | 中 | "Motivated by this gap in existing literature, this paper seeks to investigate..." |
| "Although X has been studied, Y remains..." | 低 | "Although the above research provides a solid foundation, ASTARS-assisted FL remains an emerging area." |

**尖锐问题引导模式（💡 低频可选，约 10%，2/21 篇）：**
```
[直接问句1]? [直接问句2]? This paper aims to answer these questions by [方案].
```
- "Will FD NOMA relaying bring performance gains compared to HD NOMA relaying? If yes, what is the condition?"（语料原文，注意原文为 FD 非 NOMA）
- "by seeking answers to these questions:" 框架亦见于语料（MF-RIS 篇），两种引导均可

### Layer 5：贡献列表 & 论文组织（1-2 段）

**贡献列表标准引导句（语料约 15/21 篇）：**
```
The main contributions of this paper can be summarized as follows:
1) We propose [方案] and derive [结果].
2) We establish [理论] and provide [分析].
3) We investigate [优化] and propose [算法].
4) We demonstrate [验证] that [新发现].
```

**贡献点四种动作类型（💡 推荐组合，非强制顺序）：**

| 编号 | 动作 | 典型句式 |
|:----:|------|----------|
| 1) | **提出** | "We propose/introduce a novel X framework for Y..." |
| 2) | **推导** | "We derive/establish the closed-form expressions of X..." |
| 3) | **优化** | "We investigate/develop an algorithm to jointly optimize X and Y..." |
| 4) | **验证** | "We demonstrate/confirm that the proposed X outperforms Y..." |

> 实测：贡献点 3-5 点不等（FL 篇用 "-" 项目符号列表亦可），动作顺序与数量灵活；最低要求动作动词多样性 ≥3 类。

**论文组织段落模板：**
```
The rest of this paper is organized as follows. Section II presents the system model of X. 
In Section III, the performance of Y is examined. Section IV provides the simulation results 
and numerical analysis. Finally, Section V concludes this paper.
```

**符号说明段落（✅ 约 81%，17/21 篇包含；位于 Introduction 的 Organization and Notation 子节，而非 System Model）：**
```
Notations: Scalars, vectors, and matrices are denoted by lower-case, bold-face lower-case, 
and bold-face upper-case letters, respectively. (·)^T and (·)^H denote the transpose and 
conjugate transpose operations, respectively. E{·} denotes the expectation operation.
```

---

## 二、引言段落过渡逻辑流

```
[Layer 1: 大背景]
"With the development of X..." / "As X advances..."
    ↓
[Layer 2: 技术演进]
"X has been regarded as..."
"However, traditional X suffers from..."
"To tackle this problem, Y has been proposed..."
    ↓
[Layer 3: 文献综述]
"1) X Network: ... The authors in [x] proposed... "
"2) Y Network: ... Prior studies have demonstrated... "
"3) X-Y Integrated Networks: ... Recent studies have shown... "
    ↓
[Layer 4: 研究空白]
"While the aforementioned works have laid a solid foundation..."
"To the best of our knowledge, there is no existing work investigating..."
"Motivated by this gap, this paper seeks to investigate..."
    ↓
[Layer 5: 贡献 + 组织]
"The main contributions of this paper can be summarized as follows:
1) We propose... 2) We derive... 3) We develop... 4) We demonstrate..."
"The remainder of this paper is organized as follows..."
```

---

## 三、文献综述段内部句级过渡多样化

> 核心目标：消除"单词过渡词综合征"，让文献综述读起来是流畅叙述而非清单罗列。

### 3.1 七种过渡手法库（压缩版）

| 手法 | 力度 | 示例 | 适用场景 |
|-----------|:---------:|-----------|-----------------|
| **自然承接（无过渡）** | 轻 | The authors of \cite{...} proposed... | 同一子主题内连续引用 |
| **主题引导短语** | 中 | To exploit spatial degrees of freedom, | 子主题切换 |
| **引用开头** | 中 | In \cite{...}, the authors... | 单篇重要文献聚焦 |
| **同位语嵌入强调** | 重 | A critical yet previously overlooked factor—X—was... | 特殊贡献强调 |
| **场景引导短语** | 中 | For downlink scenarios, / In the context of... | 切换应用场景 |
| **分词短语引导** | 中 | Going beyond..., / Extending this direction, | 拓展到新领域 |
| **收束总结词** | 轻 | Collectively, / Together, / Overall, | 段落末句收束 |

### 3.2 手法选择三原则

1. **同种手法不邻**：相邻两句不使用同一种过渡手法。
2. **子主题内部承接，切换时引导**：同一子主题内多篇文献用自然承接，切换子主题时用主题引导短语。
3. **特殊贡献用同位语嵌入**：首次提出或关键转折点，不要用 Notably 一带而过，改为同位语嵌入主语中。

## 四、引言写作检查清单（✅ 必须 / 💡 建议）

### Layer 1-2 检查
- [✅] 背景是否有足够的广度和领域相关性
- [✅] 是否从宏观到微观逐层聚焦
- [✅] 是否引用了足够的背景文献（5-10 篇；Layer 1 实测可更多）

### Layer 3 检查
- [✅] 文献综述是否按技术主题分类（≥2 个类别）
- [✅] 每类是否覆盖了关键文献（3-5 篇/类）
- [💡] 是否包含最新研究（近 2-3 年）
- [✅] 对已有工作的评述是否客观，避免过度批评
- [✅] 文献综述段内部过渡手法是否多样化（避免 ≥3 句连续单词过渡词）

### Layer 4 检查
- [✅] 研究空白是否明确具体
- [✅] 动机是否有充分的技术依据
- [💡] 是否使用了 "To the best of our knowledge" 句式（约 57% 论文使用，非强制）
- [✅] 动机部分是否自然地导向了本文的贡献

### Layer 5 检查
- [✅] 贡献是否以编号列表 1)2)3)4) 或等价列表格式呈现（FL 篇 "-" 项目符号亦可）
- [✅] 每个贡献点是否包含"做了什么"和"取得了什么"（动作动词 + 方法/对象 + 成果/结论）
- [💡] 贡献点是否与已有工作形成对比
- [✅] 论文组织段落是否清晰交代了后续章节

### 整体检查
- [✅] 全篇是否使用 IEEE 编号引用格式 [1], [2]-[5]
- [✅] 首次引用的缩略语是否已定义
- [✅] 段落之间是否有自然的过渡和连接
- [💡] 引言长度是否适当（通常为全文 15-25%）
- [✅] 符号说明段落（如包含）是否位于 Organization and Notation 子节

## 五、第一轮蒸馏补充（语料发现的新模式）

### 5.1 文献综述组织变体
- 编号段落式（1) [Category]: ...）约 10%（2/21 篇）
- 子节式（### A. Previous Works + **1) 2) 3)** 编号段落）少量使用（SGF 篇）
- 分块综述替代编号（"The first aspect... The second aspect..."，FD/HD 篇）约 5%
- 综述段内混合使用 "The authors in [x]" 与 "In [x]" 两种引用格式

### 5.2 技术演进段落高引用密度
Layer 2 段落保持高引用密度（每句至少 1 个引用，关键句可叠加 2-3 个；段落总引用 8-15 个；引用群格式 [1]-[5] 或 [1],[2],[3]）。此要求仅适用于综述密集段落。

### 5.3 引用句式变体
- "In [x], the authors proposed/investigated..."（文献编号开头）
- "A seminal work proposed X [x]."（开创性工作）
- "X was studied/analyzed/investigated in [x]."（被动语态）
- "Prior studies have demonstrated..."（归类引用，语料实证；"Prior works have demonstrated" 语料无此精确句式，勿用）

### 5.4 符号说明段落呈现方式
1. "Notations: Scalars, vectors, and matrices..."（标准版）
2. "The key notations in this paper are presented as follows..."（关键词版）
3. 分项说明版（每个符号一行）
