# Motivation 润色规范（深度蒸馏版）

> 基于课题组语料的动机部分润色规范。While/Although开头→空白定位→贡献列表。

## 润色重点
1. **论证力度**：从已有工作到研究空白的过渡是否有说服力
2. **贡献点三层递进**：每个贡献点应包含 动作层→工具层→结论层
3. **贡献句式**：4个贡献点是否覆盖提出→推导→分析→验证
4. **研究空白变体**：检查是否使用了多种空白句式（"there are no existing works" / "remains unexplored" / "is still in its infancy"）
5. **尖锐问题映射**：如有问题列表，每个问题是否与贡献点一一对应
6. **对比表格**：Table I 格式和内容完整性（特征行建议覆盖5个维度）

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

### Q4：研究空白句式单一
❌ 始终重复 "To the best of our knowledge, X has not been comprehensively explored"
✅ 交替使用 "there are no existing works to investigate X"、"X remains an emerging area of study"、"This paper presents the first comprehensive analysis of X"

### Q5：问题-贡献不匹配
❌ 问题列表和贡献点没有对应关系
✅ 问题1（技术挑战）→ 贡献1（建模与推导）；问题2（对比）→ 贡献2（对比分析）

## 润色前后对比

**Before**: "X has been studied by many works. We propose a new method. We also derive some expressions."
**After**: "While X has been extensively studied, the integration of X and Y remains unexplored. To the best of our knowledge, this paper presents the first analysis of... The main contributions are: 1) We propose... 2) We derive... 3) We investigate... 4) We demonstrate..."

## 润色决策树
```
Motivation →
  ├─ 是否以 "While/Although" 开头？ → 否：添加标准过渡
  ├─ 是否有 "To the best of our knowledge"？ → 否：补充空白句
  ├─ 空白句式是否多样化？ → 仅用一种：换用其他变体
  ├─ 贡献点是否≥3个？ → 否：补充贡献点
  ├─ 每个贡献点是否含三层递进（动作→工具→结论）？ → 否：补充工具层/结论层
  ├─ 问题-贡献是否一一映射（如有问题列表）？ → 否：调整对应关系
  └─ Table I（如有）特征行是否≥5个维度？ → 否：扩充特征维度
```
