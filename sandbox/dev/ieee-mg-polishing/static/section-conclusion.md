# Conclusion 润色规范

> 结论润色规范，含常见问题、润色重点和决策树。Motivation / System Model 的润色规范见独立文件 section-motivation.md / section-system-model.md。
> **v1.2.0**：开头句式注明合法变体；被动确认句式修正（It can be confirmed that 语料 0 处）；数值总结降为可选项；词数 80-200。

## Conclusion 润色

### 常见问题
❌ 时态混用："In this paper, we have investigated the performance of X and derive the closed-form expressions..."（have investigated 与 derive 混用）
✅ "In this paper, we have investigated the performance of X and derived the closed-form expressions..."（保持现在完成时一致）

❌ 未来工作不具体
✅ 从当前假设局限性出发："The setting of X may give rise to overestimated performance, hence our future work will..."（语料实证句式）

❌ 完全复制 Abstract
✅ 重新组织语言，从"已完成"的角度总结

❌ 长度超限（>200 词）
✅ 精简至 80-200 词（语料实测 0 篇超 200，均值约 145），单段

### 润色重点
1. **开头句**：使用语料高频开头句式——被动完成时（"In this paper, the ... has/have been investigated/studied..."，约 48%）、"This paper has investigated/studied..."（约 29%）、"In this paper, we investigated..."（约 10%）、"This article..." 变体（约 14%）；**四型均为语料实证合法开头，不强制改写**（语料中不存在 "In this paper, we have investigated" 这一精确开头，但近邻形式 "In this paper, we investigated" 存在）
2. **数值对比**：💡 可选项（语料仅 1/21 篇结论含数值）；使用多层对比句式（"Compared to A and B, X has attained Y% and Z%"）仅当用户已提供数值
3. **顺序词串联**：💡 低频可选（约 1/21 篇），用 "Firstly... Secondly... Finally" 替代编号列表
4. **实际应用落点**：💡 低频可选（约 2/21 篇），添加 "From the perspective of practical applicability..." 句
5. **被动确认句式**：使用语料实证句式 "It has been shown that..."（2-3 处）/ "It was demonstrated that..."；**"It can be confirmed that" 语料 0 处，勿用**
6. **未来工作**：💡 约 48% 论文写，非必须；从局限性出发引出未来方向

### 决策树
```
结论 →
  ├─ 开头是否属于语料四型之一（被动完成时 / "This paper has investigated" / "In this paper, we investigated" / This article 变体）？
  │   └─ 否且开头口语化 → 调整为语料高频句式 (moderate)；是 → 保留（不强制改写）
  ├─ 长度是否在 80-200 词内？ → 超限：删除冗余（不删技术信息） (deep)
  ├─ 是否复述了关键发现？ → 否：补全发现总结（基于正文内容） (moderate)
  ├─ 数值总结？ → 💡 可选项：仅当用户已提供数值时使用多层对比（不编造数值）
  ├─ 是否使用被动确认句式？ → 💡 可用 "It has been shown that..." / "It was demonstrated that..."
  ├─ 未来工作是否从局限性引出？ → 💡 建议（约 48% 论文写）
  ├─ 是否有未来工作？ → 💡 建议添加 1-2 句（非强制）
  └─ 是否引入了新引用？ → 是：删除引用（✅ 硬性）
```
