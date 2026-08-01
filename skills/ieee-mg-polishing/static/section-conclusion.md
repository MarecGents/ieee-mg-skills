# Conclusion 润色规范

> 结论润色规范，含常见问题、润色重点和决策树。Motivation / System Model 的润色规范见独立文件 section-motivation.md / section-system-model.md。

## Conclusion 润色

### 常见问题
❌ 时态混用："In this paper, we have investigated the performance of X and derive the closed-form expressions..."（have investigated 与 derive 混用）
✅ "In this paper, we have investigated the performance of X and derived the closed-form expressions..."（保持现在完成时一致）

❌ 无未来工作
✅ 添加 "A promising future research direction is to extend X to Y by considering Z."

❌ 完全复制 Abstract
✅ 重新组织语言，从"已完成"的角度总结

❌ 发现陈述无数值支撑
✅ 使用多层数值对比："Compared to A and B, achieved X% and Y%, respectively"

❌ 未来工作不具体
✅ 从当前假设局限性出发："The setting of X may give rise to overestimated performance, hence our future work will..."

### 润色重点
1. **开头句**：使用语料高频开头句式——被动完成时（"In this paper, the ... has/have been investigated/studied..."，约 48%）或 "This paper has investigated/studied..."（约 29%）；语料中不存在 "In this paper, we have investigated" 这一精确开头
2. **数值对比**：使用多层对比句式（"Compared to A and B, X has attained Y% and Z%"）
3. **顺序词串联**：用 "Firstly... Secondly... Finally" 替代编号列表
4. **实际应用落点**：添加 "From the perspective of practical applicability..." 句
5. **被动确认句式**：交替使用 "It has been shown that..." / "It can be confirmed that..."
6. **未来工作**：从局限性出发引出未来方向

### 决策树
```
结论 →
  ├─ 开头是否为语料高频句式（被动完成时 / "This paper has investigated"）？ → 否：调整为高频句式
  ├─ 是否有具体数值？ → 否：补充性能数据
  ├─ 数值是否多层对比？（与多个基准比较） → 否：补充多层对比
  ├─ 是否使用顺序词串联发现？ → 如用 "Firstly... Secondly... Finally" 更流畅
  ├─ 是否有实际应用落点？ → 否：添加 "From the perspective of practical applicability"
  ├─ 是否使用被动确认句式？ → 否：交替使用 "It has been shown that..." / "It can be confirmed that..."
  ├─ 未来工作是否从局限性引出？ → 否：先指出假设局限，再引出方向
  ├─ 是否有未来工作？ → 否：添加1-2句
  └─ 是否引入了新引用？ → 是：删除引用
```
