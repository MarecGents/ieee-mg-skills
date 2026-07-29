# Conclusion / Motivation / System Model 润色规范

> 结论、动机和系统模型的润色规范合辑。每节含案例和决策树。

## Conclusion 润色

### 常见问题
❌ 时态错误："In this paper, we studied the performance..."（应用现在完成时）
✅ "In this paper, we have investigated the performance..."

❌ 无未来工作
✅ 添加 "A promising future research direction is to extend X to Y by considering Z."

❌ 完全复制 Abstract
✅ 重新组织语言，从"已完成"的角度总结

### 决策树
```
结论 →
  ├─ 是否以 "have investigated" 开头？ → 否：改为现在完成时
  ├─ 是否有具体数值？ → 否：补充性能数据
  ├─ 是否有未来工作？ → 否：添加1-2句
  └─ 是否引入了新引用？ → 是：删除引用
```

## Motivation 润色

### 常见问题
❌ "Some works studied X." → 太模糊
✅ "The authors in [x] proposed an adaptive FL algorithm, reducing communication overhead in mobile edge computing."

❌ 贡献点无区分度
✅ 确保四个点分别覆盖：提出→推导→分析→验证

### 决策树
```
动机 →
  ├─ 是否以 "While/Although" 开头？ → 否：添加过渡句
  ├─ 研究空白是否明确？ → 否：补充 "To the best of our knowledge"
  └─ 贡献点是否≥3个？ → 否：扩充或合并
```

## System Model 润色

### 常见问题
❌ 符号未定义就使用
✅ 每个符号首次出现时定义

❌ 变量格式不规范
✅ 变量斜体 $x$，向量粗体 $\mathbf{x}$

❌ 无复杂度分析
✅ 补充 "The computational complexity is O(...)"

### 决策树
```
系统模型 →
  ├─ 所有符号是否已定义？ → 否：逐个检查并定义
  ├─ 公式后是否有标点？ → 否：加逗号或句号
  ├─ 是否有假设声明段落？ → 否：添加 "We assume that..."
  └─ 算法步骤是否清晰？ → 否：添加伪代码
```
