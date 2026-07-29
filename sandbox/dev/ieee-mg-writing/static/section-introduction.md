# Introduction（引言）写作模板

> 基于课题组 21 篇 IEEE Trans 论文引言语料深度蒸馏。
> **核心结构**：5 层漏斗式宏观架构 + 3 块文献综述 + 编号贡献列表

## 一、5 层宏观架构

### Layer 1：大背景（1-2 段）
引出领域的广阔背景和发展趋势。

**典型打开方式（语料统计）：**

| 模式 | 占比 | 示例 |
|------|------|------|
| **"As X advances..."** | ~35% | "As wireless communication technology rapidly advances, considerable challenges related to extensive connectivity..." |
| **"X has been deemed as..."** | ~25% | "RIS has been deemed as one of the promising wireless technologies for 6G networks..." |
| **"With the development of X..."** | ~20% | "With the rapid development of machine learning and artificial intelligence technologies..." |
| **"The novel X has recently..."** | ~15% | "The novel active STARS has recently received a lot of attention due to its capability to conquer multiplicative fading loss..." |
| **直接陈述** | ~5% | "Reconfigurable intelligent surface (RIS) has been regarded as a promising technology..." |

**Layer 1 必备要素：**
- [ ] 点明领域的重要性和发展背景
- [ ] 引用 2-5 篇宏观综述/背景文献
- [ ] 引出本文涉及的核心技术方向

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

### Layer 3：文献综述（2-4 段）
**课题组标准模式：3 块式分类综述**

```
块 1：[技术方向一] 的已有研究
  ↓
块 2：[技术方向二] 的已有研究
  ↓
块 3：两个技术的交叉/结合研究
```

**标准编号格式（约 70% 使用）：**
```
1) [Category Name]: ... [x], [x], [x] ...
2) [Category Name]: ... [x], [x], [x] ...
3) [Category Name]: ... [x], [x], [x] ...
```

**引用句式库：**

| 功能 | 句式 | 示例 |
|------|------|------|
| **正面介绍** | "The authors in [x] proposed/investigated..." | "The authors in [15] proposed an adaptive FL algorithm..." |
| **归类引用** | "Prior works have demonstrated..." | "Prior works have demonstrated that RIS can reduce errors..." |
| **研究现状** | "X has been extensively studied..." | "X has been extensively studied in the context of Y..." |
| **过渡到空白** | "However, ... remains unexplored" | "However, the integration of X in Y remains unexplored" |

### Layer 4：研究空白 & 动机（1-2 段）

**研究空白声明核心句式（语料中出现率 100%）：**
```
To the best of our knowledge, [研究空白] has not been comprehensively explored in prior works.
```

**动机扩展句式：**
| 句式 | 频率 | 示例 |
|------|------|------|
| "While the aforementioned works..." | ★★★★★ | "While the aforementioned works have laid a solid foundation for understanding SGF-NOMA and STARS, the promising integration is still in their infancy." |
| "Motivated by this gap/inspiration..." | ★★★★ | "Motivated by this gap in existing literature, this paper seeks to investigate..." |
| "Although X has been studied, Y remains..." | ★★★ | "Although the above research provides a solid foundation, ASTARS-assisted FL remains an emerging area." |

**尖锐问题引导模式（约 30% 的论文使用）：**
```
This paper aims to explore [topic] by seeking answers to these questions:
- How does the significant X affect Y?
- When comparing A and B, which factor poses a greater risk?
- What are the disparities in X across different scenarios?
```

### Layer 5：贡献列表 & 论文组织（1-2 段）

**贡献列表标准模板（语料中出现率 100%）：**
```
The main contributions of this paper can be summarized as follows:
1) We propose [方案] and derive [结果].
2) We establish [理论] and provide [分析].
3) We investigate [优化] and propose [算法].
4) We demonstrate [验证] that [新发现].
```

**贡献点四种动作类型（语料统计）：**

| 编号 | 动作 | 典型句式 |
|:----:|------|----------|
| 1) | **提出** | "We propose/introduce a novel X framework for Y..." |
| 2) | **推导** | "We derive/establish the closed-form expressions of X..." |
| 3) | **优化** | "We investigate/develop an algorithm to jointly optimize X and Y..." |
| 4) | **验证** | "We demonstrate/confirm that the proposed X outperforms Y..." |

**论文组织段落模板：**
```
The rest of this paper is organized as follows. Section II presents the system model of X. 
In Section III, the performance of Y is examined. Section IV provides the simulation results 
and numerical analysis. Finally, Section V concludes this paper.
```

**符号说明段落模板（约 60% 论文包含）：**
```
Notations: Scalars, vectors, and matrices are denoted by lower-case, bold-face lower-case, 
and bold-face upper-case letters, respectively. (·)^T and (·)^H denote the transpose and 
conjugate transpose operations, respectively. E{·} denotes the expectation operation.
```

---

## 二、引言段落过渡逻辑流

```
[Layer 1: 大背景]
"As wireless communication technology rapidly advances..."
    ↓
"With the development of X..."
    ↓
[Layer 2: 技术演进]
"X has been regarded as..."
"However, traditional X suffers from..."
"To tackle this problem, Y has been proposed..."
    ↓
[Layer 3: 文献综述]
"1) X Network: ... The authors in [x] proposed... "
"2) Y Network: ... Prior works have demonstrated... "
"3) X-Y Integrated Networks: ... Recent studies have shown... "
    ↓
[Layer 4: 研究空白]
"While the aforementioned works have laid a solid foundation..."
"To the best of our knowledge, ... has not been comprehensively explored..."
"Motivated by this gap, this paper seeks to investigate..."
    ↓
[Layer 5: 贡献 + 组织]
"The main contributions of this paper can be summarized as follows:
1) We propose... 2) We derive... 3) We develop... 4) We demonstrate..."
"The remainder of this paper is organized as follows..."
```

---

## 三、引言写作检查清单

### Layer 1-2 检查
- [ ] 背景是否有足够的广度和领域相关性
- [ ] 是否从宏观到微观逐层聚焦
- [ ] 是否引用了足够的背景文献（5-10 篇）

### Layer 3 检查
- [ ] 文献综述是否按技术主题分类（≥2 个类别）
- [ ] 每类是否覆盖了关键文献（3-5 篇/类）
- [ ] 是否包含最新研究（近 2-3 年）
- [ ] 对已有工作的评述是否客观，避免过度批评

### Layer 4 检查
- [ ] 研究空白是否明确具体
- [ ] 动机是否有充分的技术依据
- [ ] 是否使用了 "To the best of our knowledge" 句式
- [ ] 动机部分是否自然地导向了本文的贡献

### Layer 5 检查
- [ ] 贡献是否以编号列表 1)2)3)4) 呈现
- [ ] 每个贡献点是否包含"做了什么"和"取得了什么"
- [ ] 贡献点是否与已有工作形成对比
- [ ] 论文组织段落是否清晰交代了后续章节

### 整体检查
- [ ] 全篇是否使用 IEEE 编号引用格式 [1], [2]-[5]
- [ ] 首次引用的缩略语是否已定义
- [ ] 段落之间是否有自然的过渡和连接
- [ ] 引言长度是否适当（通常为全文 15-25%）

## 四、第一轮蒸馏补充（语料发现的新模式）

### 4.1 文献综述嵌套子节结构（缺失7）
在Layer 3中新增嵌套结构：
```
### A. Previous Works
**1) [Category A]:** [正文段落，引用3-8篇文献]
**2) [Category B]:** [正文段落，引用3-8篇文献]
**3) [A+B Integration]:** [交叉研究段落]
```
约60%的论文在Layer 3内部采用此结构。每个子节内混合使用 "The authors in [x]" 和 "In [x]" 两种引用格式。

### 4.2 技术演进段落高密度引用（缺失10）
Layer 2段落保持高引用密度：每句至少1个引用，关键句可叠加2-3个引用。引用群格式 [1]-[5] 或 [1],[2],[3]。段落整体引用数建议8-15个。

### 4.3 引用句式变体（缺失8）
新增引用句式：
- "In [x], the authors proposed/investigated..."（文献编号开头）
- "A seminal work proposed X [x]."（开创性工作）
- "X was studied/analyzed/investigated in [x]."（被动语态）

### 4.4 符号说明段落呈现方式（缺失9）
在Layer 5中补充符号说明的三种风格：
1. "Notations: Scalars, vectors, and matrices..."（标准版，模板已有）
2. "The key notations in this paper are presented as follows..."（关键词版）
3. 分项说明版（每个符号一行）
