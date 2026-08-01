# ieee-mg-writing 核心原则（课题组风格蒸馏版）

> 基于课题组 21 篇 IEEE Trans/期刊论文语料蒸馏。本文件定义了所有写作必须遵循的核心风格原则。
> **统计口径（v1.2.0）**：占比/频次为 grep 行级计数估算或逐篇人工核验（已标注）；与 quantitative-baseline.md 冲突处以后者为准。
> **约束分级（v1.2.0）**：✅ 硬约束（必须遵守）/ 💡 软约束（建议，可依上下文调整）/ ❌ 禁止。

## 总体原则

1. **IEEE Transactions 学术规范**：所有写作遵循 IEEE Trans 系列期刊的精确、严谨、客观、简洁风格 ✅
2. **课题组研究特色**：内容聚焦 B5G/6G 无线移动通信、非正交多址接入（NOMA）、RIS/STARS/可重构天线系统 ✅
3. **读者意识**：目标读者是通信与信号处理领域的研究者，默认具备随机过程、信息论、优化理论等基础知识 ✅
4. **可复现性**：所有技术描述应足够详细，使同行研究者能够复现 ✅

---

## 一、课题组全局风格画像（语料蒸馏结果）

### 1.1 学术正式度

| 维度 | 定量特征 | 约束 |
|------|----------|------|
| **被动语态比例** | Abstract 40%-50%，其余章节 30%-40%（估算值，无 POS 统计佐证，与 quantitative-baseline.md 一致） | 💡 |
| **第一人称频率** | "we" 平均每千词约 6-8 次（Abstract 实测 6.5/千词，16/21 篇使用 ≈76%），用于 propose/derive/formulate 等动作 | 💡 |
| **主要情态动词** | can > may > could > might（定性印象，无计数依据） | 💡 |
| **否定表达** | 较少直接否定，更多使用委婉否定："there is no existing work..."、"is not researched yet" | 💡 |
| **缩略形式** | 禁止使用缩略形式（don't → do not, it's → it is）；语料偶见反例（doesn't/it's），写作时不模仿 | ✅ |

### 1.2 句式复杂度

| 维度 | 定量特征 | 约束 |
|------|----------|------|
| **平均句长** | 定性：Abstract 偏短、Introduction 偏长（抽样口径：Abstract 约 25-29 词/句）；句子控制在 15-30 词为宜 | 💡 |
| **从句密度** | 每句 0.8-1.5 个从句（印象分），which/that 引导的定语从句最常见 | 💡 |
| **插入语** | 较少使用括号插入，更多使用逗号分隔的非限制性定语从句 | 💡 |
| **典型复合句** | "By + V-ing ..., X is capable of ... while ..."（语料实测高频） | 💡 |

### 1.3 时态使用图谱

| 章节 | 主要时态 | 次要时态 | 例句 | 约束 |
|------|----------|----------|------|------|
| **Abstract** | 一般现在时 | 现在完成时 | "This paper investigates... We derive..." | ✅ |
| **Introduction** | 一般现在时 | 一般过去时（已有工作）；引用句三型并存（过去时 proposed / 现在完成时 have demonstrated / 现在时 demonstrate） | "RIS has been deemed as... The authors in [x] proposed..." | ✅ |
| **System Model** | 一般现在时 | — | "We consider a system where..."（⚠ 外部通用知识，非语料蒸馏） | ✅ |
| **Numerical Results** | **一般现在时（图描述 "Fig. X plots..."，语料 30+ 处实证）** | 一般过去时（仿真过程，可选） | "Fig. X plots the OP versus the SNR..." | ✅ |
| **Conclusion** | 现在完成时（约 15/21 篇） | 一般现在时；过去时/现在时为合法变体（约 6/21 篇） | "This paper has investigated..." | 💡 |

### 1.4 逻辑连接词网络

按功能分类，按使用频率降序（实测，详见 logic-connectors.md）：

| 功能 | 首选词 | 次选词 | 使用场景 |
|------|--------|--------|----------|
| **因果** | due to | owing to, as a result, thereby | 结果解释、原因分析 |
| **转折** | however | although, whereas, in contrast | 研究空白、结果对比 |
| **递进** | furthermore | in addition, additionally, moreover | 贡献列点、补充说明 |
| **对比** | compared to / compared with | in contrast, on the other hand | 方案比较、基准对比 |
| **举例** | such as | e.g., for example | 技术列举 |
| **强调** | specifically | in particular, notably | 重点发现 |

### 1.5 高频动词库

按使用场景分类（语料频次排序，星级为印象分）：

| 场景 | 高频动词 |
|------|----------|
| **提出方案** | propose, introduce, develop, design |
| **理论推导** | derive, obtain, formulate, establish |
| **分析评估** | investigate, analyze, study, examine, survey |
| **性能验证** | demonstrate, validate, verify, confirm, substantiate |
| **性能对比** | outperform, surpass, exceed, achieve, precede |
| **性能描述** | improve, enhance, reduce, mitigate |

### 1.6 高频形容词/副词

| 词类 | 高频词（按频率降序） |
|------|----------------------|
| **形容词** | novel, superior, significant, robust, comprehensive, extensive, promising, effective, efficient, optimal |
| **副词** | significantly, substantially, remarkably, particularly, extensively, respectively |

---

## 二、语言风格规范

### 2.1 必守规则（✅）
- ✅ 首次出现的缩略语给出全称，格式：full name (Abbrev.)，如 "imperfect successive interference cancellation (ipSIC)"；Abstract 与正文各自首次定义
- ✅ 使用 IEEE 数学符号惯例：变量斜体 $x$、向量粗体小写 $\mathbf{x}$、矩阵粗体大写 $\mathbf{X}$
- ✅ 所有声明必须引用支撑文献（通用知识除外）
- ✅ 使用 IEEE 编号引用格式 [1], [2]–[5]
- ✅ **图描述用现在时**："Fig. X plots the ... versus the ..."（语料实测；"Fig. X plotted" 不存在于语料）
- ✅ **仿真参数表编号联动**：若引言已用 TABLE I 作贡献对比表，参数表用 TABLE II；否则参数表用 TABLE I（语料 TABLE I 11 篇 / TABLE II 8 篇）

### 2.2 推荐规则（💡）
- 💡 优先主动语态（"We propose..." > "It is proposed..."）
- 💡 句子长度控制在 15-30 词
- 💡 每个段落以 topic sentence 开头
- 💡 结果句优先与基准比较（"outperforms that of OMA"），有数据时给出具体数值（注意：语料摘要本身 0 数值，数值优先放正文与结论；摘要以定性比较为主）

### 2.3 禁止规则（❌）
- ❌ 不得使用口语化和非正式表达（含缩略形式）
- ❌ 不得编造文献引用
- ❌ 不得在 Abstract 和 Conclusion 引入正文未讨论的新内容
- ❌ 不得过度使用 "very", "obviously", "clearly" 等弱化副词（注：此为通用写作建议，非语料特征；语料中 "better" 合法可用）

---

## 三、课题组术语规范

### 3.1 核心术语标准写法（完整清单见 ../ieee-mg-share/static/terminology.md）
| 术语 | 标准写法 |
|------|----------|
| 非正交多址接入 | Non-orthogonal Multiple Access (NOMA) |
| 可重构智能表面 | Reconfigurable Intelligent Surface (RIS) |
| 活跃 RIS | Active RIS (ARIS) |
| 无源 RIS | Passive RIS (PRIS) |
| 同时透射反射表面 | Simultaneously Transmitting and Reflecting Surface (STARS) |
| 活跃 STARS | Active STARS (ASTARS) |
| 串行干扰消除 | Successive Interference Cancellation (SIC) |
| 非完美 SIC | imperfect SIC (ipSIC) |
| 完美 SIC | perfect SIC (pSIC) |
| 中断概率 | Outage Probability（语料未用 "(OP)" 缩写，建议不用或按期刊要求） |
| 遍历速率 | Ergodic Data Rate（语料未用 "(EDR)" 缩写） |

### 3.2 研究领域标签
- B5G/6G 无线通信
- 非正交多址接入（NOMA）网络
- RIS/STARS 辅助通信
- 物理层安全通信
- 隐蔽通信（Covert Communication）
- 卫星通信与 LEO 星座
- 联邦学习（Federated Learning）
- 环境反向散射通信（AmBC）

---

## 四、判断边界（v1.2.0 新增）

### 何时询问用户
- 技术主题/场景信息不足时（见 SKILL.md"判断边界"节）；
- 词数/篇幅要求与模板默认冲突（如期刊限 150 词摘要）时，以期刊要求为准并确认。

### 何时停止
- 章节检查清单全部通过即完成；输出前自检，未满足项标注 [待补]。

### 数据缺失降级
- 模板统计与稿件实测冲突以稿件为准；System Model 内容标注"外部通用知识"。
