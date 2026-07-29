# System Model（系统模型）写作模板

> 基于课题组论文系统模型部分的语料分析。
> **核心结构**：系统场景 → 信道模型 → 信号模型 → 问题公式化 → 解决方案

## 一、标准结构模板

### 要素 1：系统场景描述（1-2 段）

**坐标系统建模模板（课题组标准格式）：**
```
Consider a Cartesian 3D coordinate system with the [BS/AP] located at 
\((x_1, y_1, z_1)\) and the [RIS/STARS] positioned at \((x_2, y_2, z_2)\).
The [用户设备] in the [区域A] are evenly distributed in region 
\(I_1 \triangleq \{(x, y, z) : \text{...}\}\), and similarly the [用户设备] 
in the [区域B] are evenly distributed in \(I_2 \triangleq \{\text{...}\}\).
```

**系统参数声明标准句式：**
```
Unless stated otherwise, the [关键参数] are presented in [Table X].
We assume that [假设条件1] and [假设条件2].
```

**典型假设条件（语料中常见）：**
- 所有信道为准静态衰落（quasi-static fading）
- 信道状态信息（CSI）在 BS 处完美已知
- 用户间通过正交资源进行信道估计
- 反射/透射系数相互独立

### 要素 2：信道模型（1-2 段）

**课题组使用的主要信道模型：**

| 信道模型 | 适用场景 | 典型参数 |
|----------|----------|----------|
| **Rician 衰落** | RIS/STARS 辅助通信（最常见） | Rician 因子 \(\kappa\) |
| **Nakagami-m 衰落** | 级联信道、双 RIS 场景 | 衰落参数 \(m\) |
| **瑞利衰落** | 非视距场景 | \(\sigma^2\) |
| **级联 Rician** | 双 RIS/ARIS-PRIS 场景 | \(\kappa_1, \kappa_2\) |

**信道建模标准句式：**
```
The channel coefficient between [节点A] and [节点B] is given by
\[
\mathbf{h}_{AB} = \sqrt{\frac{\beta(d)}{K+1}} \left( \sqrt{K} \mathbf{h}_{LOS} + \sqrt{1} \mathbf{h}_{NLOS} \right)
\]
where \(\beta(d) = \beta_0 d^{-\alpha}\) denotes the path loss with 
reference distance \(d_0 = 1\) m and path loss exponent \(\alpha\).
```

### 要素 3：信号模型（1-2 段）

**NOMA 信号模型核心表达式：**

**发送信号：**
```
The superimposed signal transmitted by [BS/用户] is
\[
x = \sum_{i=1}^{N} \sqrt{P a_i} s_i
\]
where \(P\) is the total transmit power, \(a_i\) is the power allocation 
coefficient satisfying \(\sum_{i=1}^{N} a_i = 1\), and \(s_i\) is the 
message signal of user \(i\).
```

**接收信号（RIS/STARS 辅助）：**
```
The received signal at user \(i\) is
\[
y_i = \mathbf{h}_{RU,i}^H \mathbf{\Theta} \mathbf{H}_{BR} x + n_i
\]
where \(\mathbf{\Theta} = \text{diag}(\beta_1 e^{j\theta_1}, ..., \beta_M e^{j\theta_M})\) 
is the phase shift matrix of RIS, \(\mathbf{H}_{BR}\) is the channel from BS to RIS, 
\(\mathbf{h}_{RU,i}\) is the channel from RIS to user \(i\), and \(n_i\) is the AWGN.
```

**SIC 过程描述标准句式：**
```
According to the NOMA principle, user \(i\) first decodes the message of user \(j\) 
(with higher power) and then cancels it from the received signal before decoding 
its own message. The received signal-to-interference-plus-noise ratio (SINR) for 
user \(i\) to decode user \(j\)'s message is given by
\[
\text{SINR}_{i\to j} = \frac{P |\mathbf{h}_{i,j}|^2 a_j}{P |\mathbf{h}_{i,j}|^2 \sum_{k<j} a_k + \sigma^2}
\]
```

### 要素 4：问题公式化（1 段）

**优化问题的标准表述格式：**
```
\begin{align}
&\max_{\mathbf{X}} \; R_{\text{sum}}(\mathbf{X}) \\
\text{s.t.}\quad & C1: \sum_{i=1}^{N} P_i \leq P_{\max}, \\
& C2: R_i \geq R_{\min}, \forall i, \\
& C3: 0 \leq \theta_m \leq 2\pi, \forall m.
\end{align}
```

**常见优化变量：**
| 变量 | 说明 | 约束类型 |
|------|------|----------|
| \(\mathbf{\Theta}\) | RIS/STARS 相移矩阵 | 单位模约束 |
| \(\mathbf{P}\) | 功率分配向量 | 和功率约束 |
| \(\mathbf{w}\) | 波束成形向量 | 范数约束 |
| \(\mathbf{f}\) | 接收波束分配 | 离散/连续 |

**常见目标函数：**
- 最大化可达和速率（Max-SR）
- 最小化中断概率（Min-OP）
- 最大化能量效率（Max-EE）
- 最大化学习效率（FL 场景）
- 最大化隐蔽传输速率（Covert 场景）

### 要素 5：解决方案（可选，1-2 段）

**算法伪代码标准格式：**
```
Algorithm 1 [算法名称]
Require: [输入参数]
Ensure: [输出结果]
1: Initialize [初始值]
2: repeat
3:   Update [变量1] via [方法1]
4:   Update [变量2] via [方法2]
5: until convergence
6: return [最优解]
```

**复杂度分析句式：**
```
The computational complexity of the proposed Algorithm 1 is analyzed as follows. 
The update of [变量1] involves [计算量], and the update of [变量2] requires 
[计算量]. Thus, the total complexity is \(\mathcal{O}(I \cdot [总复杂度])\), 
where \(I\) is the number of iterations.
```

---

## 二、课题组 System Model 写作习惯

1. **符号定义详细**：约 60% 的论文有独立的符号说明段落（Notations）
2. **坐标系统建模**：多数论文使用 3D 笛卡尔坐标描述系统布局
3. **级联信道计算**：RIS/STARS 场景中通道的级联表示是核心
4. **问题公式化标准化**：使用 align 环境列出目标函数和约束
5. **算法伪代码规范**：使用 Algorithm 环境，有输入/输出声明

## 三、写作检查清单
- [ ] 系统场景是否清晰描述（坐标/拓扑）
- [ ] 所有数学符号首次使用时是否定义
- [ ] 信道模型是否明确（Rician/Nakagami/Rayleigh）
- [ ] 信号模型是否包含完整的收发表达式
- [ ] SIC 过程是否描述清楚
- [ ] 优化问题的目标函数和约束是否完整
- [ ] 问题是否注明凸/非凸性
- [ ] 算法步骤是否可复现
- [ ] 复杂度分析是否提供
- [ ] 符号是否符合 IEEE 规范（斜体/粗体/花体）
- [ ] 公式编号是否连续
