# Motivation 润色规范（深度蒸馏版）

> 基于课题组语料的动机部分润色规范。While/Although开头→空白定位→贡献列表。

## 润色重点
1. **论证力度**：从已有工作到研究空白的过渡是否有说服力
2. **贡献句式**：4个贡献点是否覆盖提出→推导→分析→验证
3. **对比表格**：Table I 格式和内容完整性

## 常见问题案例库

### Q1：动机不充分
❌ "X is important. We study X."
✅ "While the aforementioned works have laid a solid foundation for understanding SGF-NOMA and STARS, the promising integration is still in their infancy. To the best of our knowledge, existing works are based on pSIC, which are difficult to realise in practice."

### Q2：贡献点动词重复
❌ "1) We propose... 2) We propose... 3) We propose..."
✅ "1) We propose... 2) We derive... 3) We analyze... 4) We demonstrate..."

### Q3：贡献点没有结论句
❌ "1) We propose a new scheme."
✅ "1) We propose a new scheme. Analytical results show that the diversity order is proportional to the number of elements."

## 润色前后对比

**Before**: "X has been studied by many works. We propose a new method. We also derive some expressions."
**After**: "While X has been extensively studied, the integration of X and Y remains unexplored. To the best of our knowledge, this paper presents the first analysis of... The main contributions are: 1) We propose... 2) We derive... 3) We investigate... 4) We demonstrate..."

## 润色决策树
```
Motivation →
  ├─ 是否以 "While/Although" 开头？ → 否：添加标准过渡
  ├─ 是否有 "To the best of our knowledge"？ → 否：补充空白句
  ├─ 贡献点是否≥3个？ → 否：补充贡献点
  ├─ 每个贡献点是否有结论句？ → 否：添加 "Analytical results show..."
  └─ Table I（如有）特征行是否≥4个？ → 否：扩充特征维度
```
