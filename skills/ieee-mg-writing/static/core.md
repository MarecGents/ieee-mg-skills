# ieee-mg-writing 核心原则（课题组风格蒸馏版）

> 基于课题组 21 篇 IEEE Trans/期刊论文语料蒸馏。本文件定义了所有写作必须遵循的核心风格原则。

## 总体原则

1. **IEEE Transactions 学术规范**：所有写作遵循 IEEE Trans 系列期刊的精确、严谨、客观、简洁风格
2. **课题组研究特色**：内容聚焦 B5G/6G 无线移动通信、非正交多址接入（NOMA）、RIS/STARS/可重构天线系统
3. **读者意识**：目标读者是通信与信号处理领域的研究者，默认具备随机过程、信息论、优化理论等基础知识
4. **可复现性**：所有技术描述应足够详细，使同行研究者能够复现

---

## 一、课题组全局风格画像（语料蒸馏结果）

### 1.1 学术正式度

| 维度 | 定量特征 |
|------|----------|
| **被动语态比例** | 约 35%-45%（Abstract 中偏高，Motivation 中偏低） |
| **第一人称频率** | "we" 平均每千词出现约 6-8 次（Abstract 实测 6.5/千词，14/21 篇使用），用于 propose/derive/formulate 等动作 |
| **主要情态动词** | can（可能性/能力）> may（许可）> could（委婉）> might（低概率） |
| **否定表达** | 较少直接否定，更多使用委婉否定："there is no existing work..."、"is not researched yet" |

### 1.2 句式复杂度

| 维度 | 定量特征 |
|------|----------|
| **平均句长** | 18-25 词（Abstract 偏短，Introduction 偏长） |
| **从句密度** | 每句 0.8-1.5 个从句，which/that 引导的定语从句最常见 |
| **插入语** | 较少使用括号插入，更多使用逗号分隔的非限制性定语从句 |
| **典型复合句** | "By + V-ing ..., X is capable of ... while ..." |

### 1.3 时态使用图谱

| 章节 | 主要时态 | 次要时态 | 例句 |
|------|----------|----------|------|
| **Abstract** | 一般现在时 | 现在完成时 | "This paper investigates... We derive..." |
| **Introduction** | 一般现在时 | 一般过去时 | "RIS has been deemed as... The authors in [x] proposed..." |
| **System Model** | 一般现在时 | — | "We consider a system where..." |
| **Numerical Results** | 一般过去时 | 一般现在时 | "Fig. X plotted... It is observed that..." |
| **Conclusion** | 现在完成时 | 一般现在时 | "We have investigated... Numerical results demonstrate..." |

### 1.4 逻辑连接词网络

按功能分类，按使用频率降序排列：

| 功能 | 首选词 | 次选词 | 使用场景 |
|------|--------|--------|----------|
| **因果** | due to | because of, owing to, as a result | 结果解释、原因分析 |
| **转折** | however | nevertheless, although, whereas | 研究空白、结果对比 |
| **递进** | moreover | furthermore, in addition, additionally | 贡献列点、补充说明 |
| **对比** | compared to | in contrast, on the other hand | 方案比较、基准对比 |
| **举例** | such as | e.g., for example | 技术列举 |
| **强调** | in particular | specifically, notably | 重点发现 |

### 1.5 高频动词库

按使用场景分类（语料频次排序）：

| 场景 | 高频动词 |
|------|----------|
| **提出方案** | propose, introduce, develop, design |
| **理论推导** | derive, obtain, formulate, establish |
| **分析评估** | investigate, analyze, study, examine, survey |
| **性能验证** | demonstrate, validate, verify, confirm |
| **性能对比** | outperform, surpass, exceed, achieve |
| **性能描述** | improve, enhance, reduce, mitigate |

### 1.6 高频形容词/副词

| 词类 | 高频词（按频率降序） |
|------|----------------------|
| **形容词** | novel, superior, significant, robust, comprehensive, extensive, promising, effective, efficient, optimal |
| **副词** | significantly, substantially, remarkably, particularly, extensively, respectively |

---

## 二、语言风格规范

### 2.1 必守规则
- ✅ 首次出现的缩略语给出全称，格式：full name (Abbrev.)，如 "imperfect successive interference cancellation (ipSIC)"
- ✅ 使用 IEEE 数学符号惯例：变量斜体 $x$、向量粗体小写 $\mathbf{x}$、矩阵粗体大写 $\mathbf{X}$
- ✅ 所有声明必须引用支撑文献（通用知识除外）
- ✅ 使用 IEEE 编号引用格式 [1], [2]–[5]

### 2.2 推荐规则
- 优先主动语态（"We propose..." > "It is proposed..."）
- 句子长度控制在 15-30 词
- 每个段落以 topic sentence 开头
- 结果句使用具体数值而非模糊副词（"30% improvement" > "significant improvement"）

### 2.3 禁止规则
- ❌ 不得使用口语化和非正式表达
- ❌ 不得编造文献引用
- ❌ 不得在 Abstract 和 Conclusion 引入正文未讨论的新内容
- ❌ 不得过度使用 "very", "obviously", "clearly" 等弱化副词

---

## 三、课题组术语规范

### 3.1 核心术语标准写法
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
| 中断概率 | Outage Probability (OP) |
| 遍历速率 | Ergodic Data Rate (EDR) |
| 分集阶数 | Diversity Order |
| 空中计算 | Over-the-Air (OTA) Computation |

### 3.2 研究领域标签
- B5G/6G 无线通信
- 非正交多址接入（NOMA）网络
- RIS/STARS 辅助通信
- 物理层安全通信
- 隐蔽通信（Covert Communication）
- 卫星通信与 LEO 星座
- 联邦学习（Federated Learning）
- 环境反向散射通信（AmBC）
