# ieee-mg-writing 标准写作流程（课题组蒸馏版）

> 基于课题组 21 篇论文的写作模式分析，提炼出最高效的写作顺序和工作流。
> **v1.2.0**：数值口径与 quantitative-baseline.md 统一（Conclusion 80-200 词、Abstract 85-280 词、参数表 TABLE I/II 联动、基准 ≥1）。

## 通用工作流

### 第一步：需求理解与规划
- 明确用户要求的章节和论文类型（journal/conf/mag）
- 确认技术主题（RIS/NOMA/STARS/FL/卫星通信等具体方向）
- 确定目标期刊档次（IEEE Trans. Commun. / Trans. Wireless / Trans. Veh. Technol. 等）
- 明确篇幅要求
- **信息缺失处置**：用户未提供技术主题/场景/目标期刊时，先询问用户（见 SKILL.md 判断边界）；不虚构内容

### 第二步：结构规划
根据章节模板规划内容框架，确定：
- 主要论点和技术贡献（3-5 个贡献点，推荐 提出/推导/优化/验证 四动作，顺序与数量可灵活）
- 所需的数学推导和优化问题
- 仿真场景和基准方案（≥1 个明确基准即可，语料约半数论文仅 1-2 个）
- 需要引用的关键文献方向

### 第三步：内容起草（按建议顺序）
对于一篇完整论文，建议以下写作顺序（基于课题组实际写作习惯）：

```
1. System Model      — 先定系统场景和数学模型（⚠ 外部通用知识，非语料蒸馏）
   ↓
2. Numerical Results — 基于模型做仿真，边做边写
   ↓
3. Motivation        — 根据结果反推动机
   ↓
4. Introduction      — 构建完整故事线
   ↓
5. Conclusion        — 总结核心发现
   ↓
6. Abstract          — 最后浓缩全文
```

这种"从具体到抽象"的顺序确保了技术内容的一致性。

### 第四步：各章节写作要点

**System Model 写作要点（⚠ 外部通用知识）**
- 先给出系统架构图（概念层面）
- 再定义数学符号和变量
- 逐步展开信道模型 → 信号模型 → 问题公式化
- 每个数学符号在首次使用时立即解释

**Numerical Results 写作要点**
- 先列出仿真参数表（TABLE I 或 TABLE II，与引言对比表编号联动；语料 TABLE I 11 篇 / TABLE II 8 篇）
- 设置基准方案进行比较（≥1 个；语料常用 OMA/PRIS/无 RIS 对照等）
- 按子场景（A/B/C）组织结果分析
- 每张图配一段 ≥4 句的分析（计数方法：图引用句计入，公式与图表标题不计）
- **图描述用现在时**："Fig. X plots the ... versus the ..."（语料 30+ 处实证）

**Motivation 写作要点**
- 承上启下开头（While/Although/前述综述回顾均可；语料 While 类约 8/15 篇≈53%，全 21 篇口径≈38%；分母 15 为含完整 Motivation 段落的论文数；非强制）
- 提出研究空白（"To the best of our knowledge..." 约 12/21 篇精确模板；空白句式多样）
- 引用已有工作的局限性
- 自然地过渡到本文贡献

**Introduction 写作要点**
- 从大背景到具体问题，逐步聚焦
- 文献综述按技术主题分 2-3 个板块（编号 1)2)3) 或子节式均可）
- 研究空白引出（To the best of our knowledge / 变体）
- 贡献点以编号列表 1), 2), 3), 4) 或等价列表格式呈现

**Conclusion 写作要点**
- 开头使用语料高频句式：被动完成时回顾（约 48%，"In this paper, the ... has/have been investigated..."）或 "This paper has investigated/studied..."（约 29%）；"In this paper, we investigated"（约 10%）等亦为语料实证合法开头
- 时态：现在完成时回顾工作为主（约 15/21 篇），过去时/现在时为合法变体（约 6/21 篇）
- 长度：80-200 词（实测 0 篇超 200 词，均值约 145），不分段（21/21 篇单段）
- 未来工作：1-2 句具体方向（约 48% 论文写，非必须）
- 数值总结为可选项（语料仅 1/21 篇结论含具体数值）

**Abstract 写作要点**
- 最后写，浓缩全文
- 5 要素：背景→问题→方法→结果(编号)→意义（要素 B 与 E 为可选）
- 结果以 i)/1) 无括号编号列出（2-4 条，每条 15-30 词）
- 词数：85-280 词（典型 130-260）

### 第五步：自检与完善
- 检查各章节的必选要素是否齐备（见各 section 检查清单，✅/💡 分级）
- 确认技术表述的准确性
- 验证引用标注是否完整
- 检查数学符号和格式的一致性
- 输出前列出未满足的 [待补] 项

---

## 课题组写作习惯特征（来自语料分析）

### Abstract 特征
- 约 43%（9/21）以 "This paper/This article investigates/proposes/introduces..." 开头；其余为技术主语式（"X has attracted growing interest..."）、"Although..." 让步式（约 5%）等
- 约 76%（16/21）的摘要使用 "we"
- 编号结果列表使用 i) 或 1) 无括号形式（不用 (i)(ii)(iii)）
- 平均 5-10 句，词数 85-280（实测典型 130-260，中位 ~165）

### Introduction 特征
- 5 层标准结构：大背景→技术演进→文献综述→研究空白→贡献列表
- 文献综述按主题分块（编号段落式或子节式两种组织）
- 贡献列表以 "The main contributions of this paper can be summarized as follows:" 引导（约 15/21 篇）
- 约 81%（17/21）包含符号说明段落（Notations，位于 Introduction 的 Organization and Notation 子节）

### Numerical Results 特征
- 以 "In this section, numerical results are presented to verify..." 开头（21/21）
- 仿真参数表是标配（TABLE I 或 TABLE II）
- 子场景划分：A/B/C 三段式或按图组织
- 分析句式：引入→观察→解释 三段式

### Conclusion 特征
- 开头两型主导：被动完成时回顾（~48%）与 "This paper has investigated..."（~29%）
- 句中回顾具体动作多用现在完成时（"we have derived/have investigated"）
- 不出现新的引用
- 未来工作使用 "A promising future research direction is..."（约 48% 论文包含）
