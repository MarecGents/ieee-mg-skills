# System Model 润色规范（深度蒸馏版）

> 基于课题组语料的系统模型润色规范。符号一致性、公式规范、逻辑完整性。

## 润色重点
1. **符号一致性**：全文数学符号统一
2. **公式表述**：LaTeX 格式符合 IEEE 规范
3. **逻辑完整性**：场景→信道→信号→问题→算法 逻辑链完整

## 常见问题案例库

### Q1：符号未定义
❌ "The received signal is y = hx + n."
✅ "The received signal at user i is y_i = h_i x + n_i, where h_i denotes the channel coefficient, x is the transmit signal, and n_i ~ CN(0,σ²) is the AWGN."

### Q2：变量格式不规范
❌ "where x is the signal"（未用斜体）
✅ "where $x$ is the signal"（变量用斜体）

### Q3：信道模型未明确
❌ "We consider fading channels."
✅ "We consider Rician fading channels with factor κ = 5 dB, where the channel coefficient is given by h = √(β/(K+1))(√K·h_LOS + h_NLOS)."

## 润色前后对比

**Before**: "The system has a BS and users. The channel is h. The received signal is y."
**After**: "We consider a downlink NOMA system consisting of a base station (BS) equipped with N antennas and M single-antenna users. The channel between the BS and user i is denoted by h_i ~ CN(0, β_i), where β_i = d_i^(-α) is the path loss. The received signal at user i is given by y_i = h_i Σ√(P a_k) s_k + n_i."

## 润色决策树
```
System Model →
  ├─ 所有符号是否首次使用时已定义？ → 否：逐个补充定义
  ├─ 变量是否用斜体 $x$？ → 否：改为斜体
  ├─ 向量是否用粗体 $\mathbf{x}$？ → 否：改为粗体
  ├─ 信道模型是否明确命名？ → 否：添加 "Rician/Nakagami/Rayleigh"
  ├─ 优化问题是否完整（目标+约束）？ → 否：补充目标函数和约束
  ├─ 公式后是否有标点？ → 否：加逗号或句号
  └─ 算法是否有复杂度分析？ → 否：添加 O(...) 复杂度
```
