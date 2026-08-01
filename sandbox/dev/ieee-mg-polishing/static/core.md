# ieee-mg-polishing 核心原则（课题组风格蒸馏版）

> 基于课题组 21 篇论文语料蒸馏的润色规范。本文件定义了所有润色操作必须遵循的核心原则。
> **v1.2.0**：错误案例全部按语料实测重写（common-errors.md 为权威）；图描述时态改现在时；新增润色 vs 扩写边界。

## 总体原则

1. **忠实于原意**：润色不得改变作者的技术内容和核心论点 ✅
2. **IEEE Trans 学术风格**：所有修改朝向课题组论文的学术表达标准（见 style-profile.md）✅
3. **最小改动原则**：在达到润色目标的前提下，尽可能少地改动原文 ✅
4. **一致性原则**：全文术语、符号、时态保持统一 ✅
5. **课题组风格导向**：优先保留和强化课题组特有的表达习惯 ✅

---

## 一、课题组常见表达偏差与纠正指南（v1.2.0 语料实测版）

> 完整错误表见 `../ieee-mg-share/static/common-errors.md`（权威），本节为摘要。所有"错误→正确"条目均有语料实证或通用语法依据。

### 1.1 冠词使用
| 偏差类型 | 错误示例 | 正确示例 |
|----------|----------|----------|
| 可数名词前缺冠词 | "In this section, numerical results are presented to verify accuracy of..." | "...to verify **the** accuracy of..."（语料 6+ 篇实证） |

### 1.2 介词搭配（语料实测）
| 偏差 | 纠正 | 语料依据 |
|------|------|----------|
| "Similar with" | "Similar to" | Numerical Result.md:224 |
| "independent to" | "independent of" | All Paper Title.md:818 |
| "outperforms than" | "outperforms"（than 赘词） | Abstract.md:30 |
| "the superior of X" | "the superiority of X" | Conclusion.md:114 等 3 处 |
| "This is because that" | "This is because" | 语料 20+ 处 |
| "superior than" | "superior to" | 通用语法（预防性） |
| ~~"different with"~~ | 已删除（语料 0 命中，无源） | — |
| ~~"compare with" 为错误~~ | **已修正**：compared with 与 compared to 均合法（语料混用），不作错误纠正 | — |

### 1.3 主谓一致（语料实测）
- "The FL accuracy ... are enhanced" → "...is enhanced"（Abstract.md:2）
- "verify the correctness of the formulas and yields" → "...and yield"（Abstract.md:30）
- "we plots" → "we plot"（Numerical Result.md:1283）
- "Fig. 6 further give" → "Fig. 6 further gives"（:1174）
- "The system throughput ... were discussed" → "...was discussed"（Conclusion.md:102）

### 1.4 时态一致（v1.2.0 修正）
| 章节 | 推荐时态 | 常见错误 |
|------|----------|----------|
| Abstract | 现在时 | 误用过去时描述论文内容 |
| Introduction | 现在时(背景)+过去时(已有工作)（引用句三型并存） | 时态切换不一致 |
| Numerical Results | **图描述必须现在时（"Fig. X plots..."，语料 30+ 处实证；"Fig. X plotted" 不存在于语料）**；仿真过程可用过去时（可选） | 图描述误用过去时 |
| Conclusion | 现在完成时为主（约 15/21），过去时/现在时为合法变体（约 6/21），不强制 | 段内时态反复切换 |

### 1.5 句式冗余（v1.2.0 修正）
| 冗余 | 精简版本 | 说明 |
|----------|----------|------|
| "It is can be seen that" | "It can be seen that"（删除多余 is） | 语料 2 处实证错误 |
| "From the figure we can see that" | "Fig. X demonstrates that..." | 可选精简（语料有此句式，非错误） |
| ~~"It is shown from Fig. X that"~~ | **已删除**（语料 0 命中）；语料高频为 "It can be seen from Fig. X that" / "As can be seen from the figure" | — |
| ~~"It can be observed that" 列为冗余~~ | **已修正**：语料 8+ 处高频，属规范观察句式；仅在段内连用时精简 | — |

---

## 二、各章节润色重点矩阵

| 章节 | 语法重点 | 风格重点 | 逻辑重点 |
|------|----------|----------|----------|
| **Abstract** | 时态一致性、冠词 | 简洁性、信息密度 | 5要素完整性（B/E 可选） |
| **Introduction** | 介词搭配、从句 | 过渡自然、引用规范 | 5层逻辑流 |
| **Motivation** | 情态动词、否定 | 论证力度、对比清晰 | 空白定位准确性 |
| **System Model** | 数学符号格式（⚠ 外部通用知识） | 技术精确性、符号一致 | 推导逻辑链 |
| **Results** | 时态（图描述现在时） | 分析深度、评价词选择 | 现象→解释对应 |
| **Conclusion** | 现在完成时为主（不强制） | 与Abstract呼应不重复 | 未来工作可行性 |

---

## 三、润色分步工作流

### Step 1：全局扫描
- 确认润色范围（全文/章节）和深度（light/moderate/deep）
- 快速识别语言水平、技术领域和术语使用

### Step 2：逐句润色（按优先级）
1. 语法修正（主谓一致、时态、冠词、介词）——先对照 common-errors.md 语料实测错误表
2. 用词优化（术语标准化、冗余精简）
3. 句式改进（从句结构、主动/被动选择）
4. 逻辑连贯（过渡词、指代清晰度）

### Step 3：章节级审校
- 检查该章节的必含要素是否齐备（对照 section-architecture.md 的 ✅/💡 分级）
- 检查术语前后一致性
- 检查格式规范性（公式、引用、图表）

### Step 4：全文审校
- 章节之间的过渡是否自然
- 术语使用全文一致
- 风格整体统一

## 四、禁止事项（v1.2.0 补充边界）
- ❌ 不得添加原文没有的技术内容（新方法/新数据/新引用/新贡献点）——**需新增时必须先询问用户**
- ❌ 不得修改数学公式和数值数据
- ❌ 不得重新组织章节结构（除非用户明确要求）
- ❌ 不得改变作者的技术判断和结论
- ❌ 不得引入不存在的引用文献
- ❌ 不得将语料中合法的变体表达（如 "In this paper, we investigated"、"Fig. X plots"、"-" 项目符号贡献列表）强制改写为"标准形式"

## 五、判断边界（v1.2.0 新增）

- **新增内容授权**：任何"补充/添加"类修改（补充方法句、添加原因解释、添加未来工作等）仅在用户已提供相关内容时补全表达；凭空新增须先询问用户；
- **语料合法变体保护**：见禁止事项最后一条；
- **数据缺失降级**：错误判断以 common-errors.md 为准，未收录表达按通用语法判断；System Model 按 IEEE 惯例处理（外部通用知识）。
