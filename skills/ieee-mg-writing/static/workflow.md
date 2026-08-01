# ieee-mg-writing 标准写作流程（课题组蒸馏版）

> 基于课题组 21 篇论文的写作模式分析，提炼出最高效的写作顺序和工作流。

## 通用工作流

### 第一步：需求理解与规划
- 明确用户要求的章节和论文类型（journal/conf/mag）
- 确认技术主题（RIS/NOMA/STARS/FL/卫星通信等具体方向）
- 确定目标期刊档次（IEEE Trans. Commun. / Trans. Wireless / Trans. Veh. Technol. 等）
- 明确篇幅要求

### 第二步：结构规划
根据章节模板规划内容框架，确定：
- 主要论点和技术贡献（1-4 个贡献点）
- 所需的数学推导和优化问题
- 仿真场景和基准方案
- 需要引用的关键文献方向

### 第三步：内容起草（按建议顺序）
对于一篇完整论文，建议以下写作顺序（基于课题组实际写作习惯）：

```
1. System Model      — 先定系统场景和数学模型
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

**System Model 写作要点**
- 先给出系统架构图（概念层面）
- 再定义数学符号和变量
- 逐步展开信道模型 → 信号模型 → 问题公式化
- 每个数学符号在首次使用时立即解释

**Numerical Results 写作要点**
- 先列出仿真参数表（TABLE II 标准格式）
- 设置 3-5 个基准方案进行比较
- 按子场景（A/B/C）组织结果分析
- 每张图配一段 ≥4 句的分析

**Motivation 写作要点**
- 使用 While 开头引出研究空白
- 提出 2-3 个尖锐研究问题
- 引用已有工作的局限性
- 自然地过渡到本文贡献

**Introduction 写作要点**
- 从大背景到具体问题，逐步聚焦
- 文献综述按技术主题分 2-3 个板块
- "To the best of our knowledge..." 引出空白
- 贡献点以编号列表 1), 2), 3), 4) 呈现

**Conclusion 写作要点**
- 开头使用语料高频句式：被动完成时回顾（约 48%，"In this paper, the ... has/have been investigated..."）或 "This paper has investigated/studied..."（约 29%）——语料中不存在 "In this paper, we have investigated" 这一精确开头
- 时态：现在完成时回顾工作（"we have derived/investigated" 用于句中回顾具体动作）
- 长度：200-400 词，不分段
- 未来工作：1-2 句具体方向

**Abstract 写作要点**
- 最后写，浓缩全文
- 5 要素：背景→问题→方法→结果(编号)→意义
- 结果以 i)/1) 无括号编号列出
- 词数：120-200 词

### 第五步：自检与完善
- 检查各章节的必选要素是否齐备
- 确认技术表述的准确性
- 验证引用标注是否完整
- 检查数学符号和格式的一致性

---

## 课题组写作习惯特征（来自语料分析）

### Abstract 特征
- 约 40% 以 "This paper investigates/proposes..." 开头；其余为技术主语式（"X has attracted growing interest..." 等，约 35%）、"Although..." 让步式（约 10%）、"As a revolutionary technology..." 等模式
- 约 67%（14/21）的摘要使用 "we"
- 编号结果列表使用 i) 或 1) 无括号形式（不用 (i)(ii)(iii)）
- 平均 5-10 句，词数 85-280（实测中位 ~210）

### Introduction 特征
- 5 层标准结构：大背景→技术演进→文献综述(3块)→研究空白→贡献列表
- 文献综述按主题分块，每块用 "(1) XXX (2) XXX (3) XXX" 编号
- 贡献列表以 "The main contributions of this paper can be summarized as follows:" 引导
- 约 60% 包含符号说明段落（Notations）

### Numerical Results 特征
- 以 "In this section, numerical results are presented to verify..." 开头
- 仿真参数表是标配（TABLE II）
- 子场景划分：A/B/C 三段式或 Fig. X-X 按图组织
- 分析句式：引入→观察→解释 三段式

### Conclusion 特征
- 开头两型主导：被动完成时回顾（~48%）与 "This paper has investigated..."（~29%）
- 句中回顾具体动作多用现在完成时（"we have derived/have investigated"）
- 不出现新的引用
- 未来工作使用 "A promising future research direction is..."
