# 各章节标准结构定义

> 基于课题组 21 篇论文的语料分析，定义各章节的必含要素和标准结构。
> 本文件仅包含结构模板，不含写作指导或句式库（那些在 expression-bank.md 和 section-*.md 中）。
> 被 ieee-mg-writing 和 ieee-mg-polishing 共同引用作为结构基准。
> **标注体系（v1.2.0）**：✅ = 必须（21 篇语料高覆盖或课题组规范）；💡 = 可选（语料部分覆盖，按论文需要取舍）。统计口径：21 篇语料人工逐篇核验（All Paper Title.md 篇级计数，21 篇确认）；与 quantitative-baseline.md 冲突处以实测为准并注明。

## Abstract（摘要）

### 5 要素漏斗式结构
```
要素 A: 背景句        (1句) → 领域重要性和趋势                 ✅ 必须（21/21）
要素 B: 背景/问题句   (0-1句) → 已有工作不足或待解决问题        💡 可选（实测 2/21 ≈ 10%，区间 10-20%）
要素 C: 方法句        (2-3句) → 本文方案                       ✅ 必须（21/21，100%）
要素 D: 结果句        (1-3句) → 关键发现，常以 i)/1) 无括号编号  ✅ 必须（实测 21/21 = 100%）
要素 E: 意义句        (0-1句) → 价值与影响                     💡 可选（实测极少：21 篇中独立意义句 0-2 篇，约 5-15%；多数论文以结果编号句收尾，不单独写意义句）
```

### 约束
- 词数：85-280 词（实测区间，与 quantitative-baseline.md 一致；典型 130-260，均值 170±45，中位 ~165）✅
- 句数：5-10 句（课题组规范，语料多数 6-8 句）💡
- 段落：1 段 ✅ 必须（21/21）

## Introduction（引言）

### 5 层漏斗式宏观架构
```
Layer 1: 大背景         (1-2段) → 领域广阔背景
Layer 2: 技术演进       (1-2段) → 从传统到最新
Layer 3: 文献综述       (2-4段) → 语料两种组织方式：A. "### A. Previous Works" 子节式（SGF 篇等，含 "### A. Existing Work" 变体）；B. "1) Related Works on X:" 编号段落式（STAR-RIS 篇 "1) Related Works on RIS:" / "2) Related Works on RIS-NOMA:"）
Layer 4: 研究空白+动机  (1-2段) → "To the best of our knowledge..."（12/21 ≈ 57% 精确模板；约 67% 论文含空白声明）
Layer 5: 贡献列表+组织  (1-2段) → 1)2)3) 编号或 "-" 项目符号（FL 篇）贡献
```

### 子章节（语料实测）
- "Motivations and Contributions" 类子节：19/21 ≈ 90%（含全部变体），💡 推荐（非强制，2 篇无此子节）。全部标题变体（实测逐篇核验）：
  - "Motivations and Contributions"：11 篇（最常用）
  - "Motivation and Contributions"：6 篇
  - "Motivations and Related Works"：1 篇
  - "Motivations" + "Contributions" 拆分两节：1 篇（MF-RIS 篇 "### A. Motivations" + "### B. Contributions"）
- "Organization and Notation" 节：17/21 ≈ 81%（含变体），💡 推荐（约 1/5 论文省略）。变体：精确 "Organization and Notation(s)" 16 篇（其中 "Notations" 复数 10 篇）、"Organizations and Notations" 1 篇、"Organization"（无 Notation）1 篇

## Motivation & Contribution

### 标准结构
```
要素 1: 承上启下     (1段) → While/Although 开头（实测 While 类约 8/15 篇≈53%，全 21 篇口径≈38%；分母 15 为含完整 Motivation 段落的论文数，其余论文以其他方式开头；另有 The aforementioned / Building upon / As previously mentioned 等变体，非唯一模式）💡
要素 2: 研究空白定位  (1-2句) → "To the best of our knowledge..."（精确模板 12/21 ≈ 57%；约 67% 论文含空白声明，含 To our knowledge 等变体）
要素 3: 尖锐问题引导  (可选, 约 10%) → "How does...?"（实测 2/21）💡
要素 4: 贡献列表     (3-5 点) → 1)2)3) 编号或 "-" 项目符号（FL 篇）均可 ✅
要素 5: 对比表格     (可选, 约 5%) → TABLE I（实测 1/21，非必须）💡
```

### 贡献点动作规范（💡 推荐而非强制）
1) 提出 (propose/introduce)
2) 推导 (derive/establish)
3) 分析/优化 (analyze/investigate)
4) 验证 (demonstrate/confirm)
> 实测：贡献点 3-5 点不等，动作顺序与数量灵活（如 ASTARS covert 篇 propose→derive→derive→derive 四点）；最低要求为动作动词多样性 ≥3 类（见 reviewer check-motivation）。推荐"提出/推导/优化/验证"四动作模板，但不强制顺序与数量。

## System Model

> **⚠ 本节为外部通用知识（IEEE 惯例），语料无对应章节数据，非语料蒸馏。** 21 篇语料仅含 Abstract/Introduction/Numerical Results/Conclusion 四部分，无 System Model 章节原文（All Paper Title.md 含 21 篇四部分，无 System Model 内容）；以下结构链为 IEEE 论文通用写作惯例与课题组投稿经验，引用时勿标注"语料实测"。

### 标准结构链
```
要素 1: 系统场景     (1-2段) → 坐标/拓扑/假设        ✅ 课题组规范
要素 2: 信道模型     (1-2段) → Rician/Nakagami/Rayleigh ✅ 课题组规范
要素 3: 信号模型     (1-2段) → 收发/干扰/SINR        ✅ 课题组规范
要素 4: 问题公式化   (1段) → 目标+约束              💡 课题组规范
要素 5: 解决方案     (可选) → 算法+复杂度           💡 课题组规范
```

### 必含内容（课题组规范）
- 假设条件声明 ✅
- 所有符号定义 ✅
- 信道建模方程 ✅
- 优化问题（如果适用）💡

## Numerical Results

### 标准结构
```
要素 1: 章节开头     (1段) → "In this section..."           ✅ 语料实测（21/21）
要素 2: 仿真参数表   (TABLE I 或 TABLE II)                  ✅ 语料实测
要素 3: 基准方案     (1段) → ≥1 个明确基准                   ✅ 语料实测（约半数论文仅 1-2 个基准，"3-5 个"并非必需）
要素 4: 子场景分析   (2-5段) → A/B/C 三段式                  💡 语料实测
```

### 仿真参数表编号规则（✅ 语料实测）
- 语料中参数表独立标题行计数：TABLE I 11 篇 / TABLE II 8 篇（11+8=19，2 篇无参数表）
- **联动规则**：若 Introduction 已用 TABLE I 作贡献对比表（如 ASTARS-FL 篇 "TABLE I: OUR CONTRIBUTIONS IN CONTRAST TO THE STATE-OF-THE-ART"），则参数表用 TABLE II；否则参数表用 TABLE I。写作时先检查引言是否已有对比表，再定参数表编号。

### 子场景常见划分方式
- 方式 A：按图组织（Fig. X→分析，Fig. Y→分析）
- 方式 B：按性能指标（Outage / Ergodic Rate / Throughput）——语料实测（多篇 "A. Outage Probability / B. Ergodic Rate / C. System Throughput" 子节）
- 方式 C：按参数影响（SNR / Elements / Power）

### 每张图分析结构
1. 引入图（1-2句）——语料高频 "Fig. X plots the ... versus the ..."（现在时，语料 30+ 处全为现在时，非过去时）
2. 观察现象（2-3句）——语料高频 "One can observe that / It can be observed that / Another phenomenon is that"
3. 解释原因（1-2句）——语料高频 "The reason is that / This is attributed to / This is due to the fact that"

## Conclusion

### 标准结构
```
要素 1: 开头句       → "This paper has investigated..." / "In this paper, the ... has been investigated..."（语料实测两型主导；另有约 5/21 篇用过去时或现在时开头，非强制现在完成时）
要素 2: 工作回顾     (2-3句) → 做了什么
要素 3: 主要发现     (2-4句) → 复述关键发现（含具体数值为可选项，实测 1/21 篇含数值）
要素 4: 未来工作     (1-2句) → 展望（实测 10/21 ≈ 48%，约半数论文写，非必须）💡
```

### 约束
- 不分段：✅ 必须（实测 21/21 = 100%，全部为单一段落）
- 词数：80-200 词（实测：21 篇 0 篇超过 200 词，均值约 145；最短一篇约 60-70 词（Shadowed-Rician 篇）；80 为去极值建议下限，quantitative-baseline.md 已同步）✅
- 不引入新引用 ✅ 课题组规范（语料 0 引用）
- 回顾时态：现在完成时为主（约 15/21），过去时/现在时为合法变体（约 6/21），不强制（见 style-profile §3）💡

## 全文件检查清单（✅ 必须 / 💡 可选）

写作或审核本节时逐项核对：
- [✅] Abstract：单段；含方法句（100%）与结果句（100%）；85-280 词（典型 130-260）
- [💡] Abstract：背景/问题句（约 10%）与意义句（约 5-15%），可省略
- [✅] Introduction：贡献列表（3-5 点，编号或项目符号）与组织说明
- [💡] Introduction：Motivation(s) 子节（90%）与 Organization and Notation 节（81%），推荐但不强制
- [💡] Motivation：尖锐问题（约 10%）与对比表（约 5%），可选
- [✅] Numerical Results：参数表（TABLE I 或 TABLE II，与引言对比表联动）；≥1 个明确基准
- [✅] Conclusion：单段（100%）；80-200 词；无新引用
- [💡] Conclusion：未来工作（约 48% 论文有）
- [✅] 全篇：图描述用现在时（Fig. X plots）
