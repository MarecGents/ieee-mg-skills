# Numerical Results 润色规范（深度蒸馏版）

> 基于课题组语料的仿真结果润色规范，含案例库、对比示例和决策树。
> **v1.2.0**：图描述时态修正为现在时（原 Q3 错误示范已纠正）；参数表 TABLE I/II 联动；MC 次数修正。

## 一、润色重点
1. **分析深度**：每张图≥4句分析（引入→观察→解释→对比；计数方法：图引用句计入，公式/图表标题不计）
2. **多因一释**：检查是否需补充 "Another reason is that" 多因模式（低频可选）
3. **权衡表达**：检查是否包含 trade-off 讨论（"does not necessarily translate to better"）
4. **双面论证**：对非单调现象使用 "On the one hand... On the other hand"
5. **子图联合分析**：多个子图之间是否有对比分析（"Fig. X(a)... Fig. X(b)... The main variation is that"）
6. **基准方案详细描述**：每个基准应包含设计原理+对比差异+使用条件（💡）
7. **时态统一**：**图描述一律现在时**（"Fig. X plots..."）；仿真过程描述过去时可选
8. **评价词精准**：使用课题组标准评价词汇
9. **理论-仿真对照**：验证理论推导的准确性
10. **蒙特卡洛迭代次数**：主流 10^6（7/12 篇），次主流 10^5（4/12），FL 场景 10 iterations（1/12）

## 二、常见问题案例库

### Q1：分析浅尝辄止（moderate）
❌ "Fig. 2 shows the outage probability. As SNR increases, the OP decreases."
✅ "Fig. 2 plots the COP versus SNR. The exact curves match perfectly with simulations. It is observed that the n-th user with pSIC outperforms OMA. This is due to the fact that NOMA provides better fairness. Another observation is that the n-th user with ipSIC converges to an error floor in the high SNR region."

### Q2：缺少原因解释（moderate）
❌ "The performance of X is better than Y."
✅ "The performance of X exceeds Y. This is because X is capable of mitigating multiplicative fading through signal amplification, while Y relies on passive elements which exacerbate channel cascade fading."

### Q3：图描述时态错误（✅ 硬性纠正）
❌ "Fig. 3 plotted the BER. It was observed that the BER decreased significantly."（过去时错误示范）
✅ "Fig. 3 plots the BER. It can be observed that the BER decreases significantly."（现在时；语料 30+ 处实证 "Fig. X plots"，"plotted" 0 处）

### Q4：评价词不够学术（light）
❌ "The proposed method is better than others."
✅ "The proposed scheme is superior to all baselines, achieving a significant improvement in spectral efficiency."
> 注："better" 本身不是错误（语料大量使用），仅在提升表达精度时替换。

### Q5：缺少多因解释（💡 低频可选）
❌ "This is due to the fact that X causes interference."
✅ "This is due to the fact that X causes interference. Another reason is that Y introduces additional noise, which further degrades the SNR."
> 注：多因模式语料约 1-2 篇使用，属低频手法，非每图必查。

### Q6：缺少权衡讨论（💡 语料实测）
❌ "Increasing X always improves performance."
✅ "X does not necessarily translate to better performance. Hence, it is crucial to consider the trade-off between X and Y."

## 三、润色前后对比

### 示例 1
**Before**: "As shown in Fig. 4, the proposed system has better performance. It can be seen that increasing antennas improves the rate. This is because more antennas help."
**After**: "Fig. 4 plots the ergodic rate versus the number of antennas. It can be observed that the proposed ASTARS-NOMA achieves the highest rate. This is due to the fact that ASTARS mitigates multiplicative fading through signal amplification. Moreover, the rate increases monotonically with the number of antennas, validating the theoretical diversity order derived in Section III."

## 四、润色决策树
```
检查Results →
  ├─ 是否以 "In this section..." 开头？ → 否：添加标准开头（用户内容允许时） (light)
  ├─ 仿真参数表(TABLE I 或 TABLE II，与引言对比表联动)是否存在？
  │   └─ 否 → 提示用户补写（写作任务） (moderate)
  ├─ 每张图分析是否≥4句？
  │   └─ 否 → 扩充分析（基于已有观察与原因，不虚构数据） (deep)
  ├─ 是否包含 "This is because/due to" 原因解释？
  │   └─ 否 → 添加原因解释（须基于用户技术内容） (moderate)
  ├─ 是否使用多因模式（"Another reason is that"）？
  │   └─ 仅单原因且可多因 → 补充第二原因 (moderate)
  ├─ 是否有 trade-off 权衡讨论？
  │   └─ 存在非单调现象但无权衡分析 → 补充权衡句 (moderate)
  ├─ 子图间是否有联合分析？
  │   └─ 多子图但无对比 → 添加 "The main variation is that..." (moderate)
  ├─ 基准方案描述是否详细？
  │   └─ 仅列名称 → 补充设计原理和使用条件（用户已提供时） (moderate)
  ├─ 评价词是否精准？
  │   └─ 否 → 替换为学术评价词（better 非错误，仅提升精度） (light)
  └─ 是否验证了理论推导？
      └─ 否 → 添加理论-仿真对比句 (moderate)
```
> 注：图描述时态为硬性检查——全文 "Fig. X plotted" 一律改 "Fig. X plots"（现在时）。
