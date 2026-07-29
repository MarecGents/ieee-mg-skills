# Numerical Results 润色规范（深度蒸馏版）

> 基于课题组语料的仿真结果润色规范，含案例库、对比示例和决策树。

## 一、润色重点
1. **分析深度**：每张图≥4句分析（引入→观察→解释→对比）
2. **时态统一**：描述仿真过程用一般过去时
3. **评价词精准**：使用课题组标准评价词汇
4. **理论-仿真对照**：验证理论推导的准确性

## 二、常见问题案例库

### Q1：分析浅尝辄止
❌ "Fig. 2 shows the outage probability. As SNR increases, the OP decreases."
✅ "Fig. 2 plots the COP versus SNR. The exact curves match perfectly with simulations. It is observed that the n-th user with pSIC outperforms OMA. This is due to the fact that NOMA provides better fairness. Another observation is that the n-th user with ipSIC converges to an error floor in the high SNR region."

### Q2：缺少原因解释
❌ "The performance of X is better than Y."
✅ "The performance of X exceeds Y. This is because X is capable of mitigating multiplicative fading through signal amplification, while Y relies on passive elements which exacerbate channel cascade fading."

### Q3：时态混用
❌ "Fig. 3 plots the BER. It can be seen that the BER decreases."
✅ "Fig. 3 plotted the BER. It is observed that the BER decreased significantly."

### Q4：评价词不够学术
❌ "The proposed method is better than others."
✅ "The proposed scheme is superior to all baselines, achieving a 30% improvement in spectral efficiency."

## 三、润色前后对比

### 示例 1
**Before**: "As shown in Fig. 4, the proposed system has better performance. It can be seen that increasing antennas improves the rate. This is because more antennas help."
**After**: "Fig. 4 plots the ergodic rate versus the number of antennas. It is observed that the proposed ASTARS-NOMA achieves the highest rate. This is due to the fact that ASTARS mitigates multiplicative fading through signal amplification. Moreover, the rate increases monotonically with the number of antennas, validating the theoretical diversity order derived in Section III."

## 四、润色决策树
```
检查Results →
  ├─ 是否以 "In this section, numerical results are presented..." 开头？
  │   └─ 否 → 添加标准开头 (light)
  ├─ 仿真参数表(TABLE II)是否存在？
  │   └─ 否 → 补充参数表 (moderate)
  ├─ 每张图分析是否≥4句？
  │   └─ 否 → 扩充分析 (deep)
  ├─ 是否包含 "This is because/due to" 原因解释？
  │   └─ 否 → 添加原因解释 (moderate)
  ├─ 评价词是否精准？
  │   └─ 否 → 替换为学术评价词 (light)
  └─ 是否验证了理论推导？
      └─ 否 → 添加理论-仿真对比句 (moderate)
```
