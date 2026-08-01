# 各章节标准结构定义

> 基于课题组 21 篇论文的语料分析，定义各章节的必含要素和标准结构。
> 本文件仅包含结构模板，不含写作指导或句式库（那些在 expression-bank.md 和 section-*.md 中）。
> 被 ieee-mg-writing 和 ieee-mg-polishing 共同引用作为结构基准。

## Abstract（摘要）

### 5 要素漏斗式结构
```
要素 A: 背景句        (1句) → 领域重要性和趋势
要素 B: 问题/动机句   (1句) → 已有工作不足 (出现率 86%)
要素 C: 方法句        (2-3句) → 本文方案 (出现率 100%)
要素 D: 结果句        (1-3句) → 关键发现，常以 i)/1) 无括号编号 (出现率 90%)
要素 E: 意义句        (可选) → 价值与影响 (出现率 30%)
```

### 约束
- 词数：100-250 词（典型 120-200）
- 句数：5-10 句
- 段落：1 段

## Introduction（引言）

### 5 层漏斗式宏观架构
```
Layer 1: 大背景         (1-2段) → 领域广阔背景
Layer 2: 技术演进       (1-2段) → 从传统到最新
Layer 3: 文献综述       (2-4段) → 以 3 块式分类
Layer 4: 研究空白+动机  (1-2段) → "To the best of our knowledge..."
Layer 5: 贡献列表+组织  (1-2段) → 1)2)3)4) 编号贡献
```

### 可选的子章节
- "Motivations and Contributions" 节（约 70% 的论文有）
- "Organization and Notation" 节（约 60% 的论文有）

## Motivation & Contribution

### 标准结构
```
要素 1: 承上启下     (1段) → While/Although 开头
要素 2: 研究空白定位  (1-2句) → "To the best of our knowledge..."
要素 3: 尖锐问题引导  (可选, 30%) → "How does...?"
要素 4: 贡献列表     (4点) → 1)2)3)4) 编号 (提出→推导→分析→验证)
要素 5: 对比表格     (可选, 25%) → TABLE I
```

### 贡献点四动作规范
1) 提出 (propose/introduce)
2) 推导 (derive/establish)
3) 分析/优化 (analyze/investigate)
4) 验证 (demonstrate/confirm)

## System Model

### 标准结构链
```
要素 1: 系统场景     (1-2段) → 坐标/拓扑/假设
要素 2: 信道模型     (1-2段) → Rician/Nakagami/Rayleigh
要素 3: 信号模型     (1-2段) → 收发/干扰/SINR
要素 4: 问题公式化   (1段) → 目标+约束
要素 5: 解决方案     (可选) → 算法+复杂度
```

### 必含内容
- 假设条件声明
- 所有符号定义
- 信道建模方程
- 优化问题（如果适用）

## Numerical Results

### 标准结构
```
要素 1: 章节开头     (1段) → "In this section..."
要素 2: 仿真参数表   (TABLE II)
要素 3: 基准方案     (1段) → 3-5个比较方案
要素 4: 子场景分析   (2-5段) → A/B/C 三段式
```

### 子场景常见划分方式
- 方式 A：按图组织（Fig. X→分析，Fig. Y→分析）
- 方式 B：按性能指标（Outage / Ergodic Rate / Throughput）
- 方式 C：按参数影响（SNR / Elements / Power）

### 每张图分析结构
1. 引入图（1-2句）
2. 观察现象（2-3句）
3. 解释原因（1-2句）

## Conclusion

### 标准结构
```
要素 1: 开头句       → "This paper has investigated..." / "In this paper, the ... has been investigated..."（语料实测两型主导）
要素 2: 工作回顾     (2-3句) → 做了什么
要素 3: 主要发现     (2-4句) → 发现了什么（含数值）
要素 4: 未来工作     (1-2句) → 展望 (出现率 70%)
```

### 约束
- 不分段（80% 的论文结论为单一段落）
- 200-400 词
- 不引入新引用
- 使用现在完成时回顾工作
