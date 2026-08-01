# 课题组术语规范

> 被 ieee-mg-writing、ieee-mg-polishing 和 ieee-mg-reviewer 共同引用。

## 1. 缩略语定义规则

**首次出现格式**：full name (Abbrev.)
- 示例：imperfect successive interference cancellation (ipSIC)
- 示例：Reconfigurable Intelligent Surface (RIS)

**第二次及以后**：仅用 Abbrev.
- 示例：the outage probability of RIS-NOMA networks

**约束**：
- 每篇论文中每个缩略语仅在首次出现时定义一次
- Abstract 中定义过的缩略语，正文首次出现时仍需再定义（因为 Abstract 独立于正文）
- 标题中尽量不使用缩略语

## 2. 核心术语标准写法

### 2.1 多址接入技术
| 中文 | 英文标准写法 |
|------|-------------|
| 非正交多址接入 | Non-orthogonal Multiple Access (NOMA) |
| 正交多址接入 | Orthogonal Multiple Access (OMA) |
| 码域 NOMA | Code-Domain NOMA (CD-NOMA) |
| 功率域 NOMA | Power-Domain NOMA (PD-NOMA) |
| 稀疏码多址接入 | Sparse Code Multiple Access (SCMA) |
| 半授权 NOMA | Semi-Grant-Free NOMA (SGF-NOMA) |

### 2.2 RIS/STARS 相关
| 中文 | 英文标准写法 |
|------|-------------|
| 可重构智能表面 | Reconfigurable Intelligent Surface (RIS) |
| 无源 RIS | Passive RIS (PRIS) |
| 活跃 RIS | Active RIS (ARIS) |
| 多功能 RIS | Multi-Functional RIS (MF-RIS) |
| 同时透射反射表面 | Simultaneously Transmitting and Reflecting Surface (STARS) |
| 无源 STARS | Passive STARS (PSTARS) |
| 活跃 STARS | Active STARS (ASTARS) |
| 同时透射反射 RIS | STAR-RIS |
| 双级联 RIS | Double Cascaded RIS |
| 反射/透射系数 | Reflection/Transmission Coefficients |
| 相移矩阵 | Phase Shift Matrix (\(\mathbf{\Theta}\)) |
| 有源放大因子 | Amplification Factor (\(\lambda\)) |

### 2.3 干扰消除
| 中文 | 英文标准写法 |
|------|-------------|
| 串行干扰消除 | Successive Interference Cancellation (SIC) |
| 完美 SIC | perfect SIC (pSIC) |
| 非完美 SIC | imperfect SIC (ipSIC) |
| 残留干扰 | Residual Interference (RI) |

### 2.4 性能指标
| 中文 | 英文标准写法 |
|------|-------------|
| 中断概率 | Outage Probability (OP) |
| 遍历速率 | Ergodic Data Rate (EDR) |
| 可达和速率 | Achievable Sum Rate |
| 频谱效率 | Spectral Efficiency (SE) |
| 能量效率 | Energy Efficiency (EE) |
| 分集阶数 | Diversity Order |
| 复用增益 | Multiplexing Gain |
| 保密中断概率 | Secrecy Outage Probability (SOP) |
| 检测错误概率 | Detection Error Probability (DEP) |
| 系统吞吐量 | System Throughput |
| 连接中断概率 | Connection Outage Probability (COP) |

### 2.5 通信场景
| 中文 | 英文标准写法 |
|------|-------------|
| 授权用户 | Grant-Based User (GBU) |
| 免授权用户 | Grant-Free User (GFU) |
| 物理层安全 | Physical Layer Security |
| 隐蔽通信 | Covert Communication |
| 空中计算 | Over-the-Air (OTA) Computation |
| 环境反向散射通信 | Ambient Backscatter Communication (AmBC) |
| 联邦学习 | Federated Learning (FL) |
| 波束跳变 | Beam Hopping (BH) |
| 多输入多输出 | Multiple-Input Multiple-Output (MIMO) |
| 信道状态信息 | Channel State Information (CSI) |

## 3. 信道模型术语

| 术语 | 标准写法 |
|------|----------|
| 瑞利衰落 | Rayleigh Fading |
| 莱斯衰落 | Rician Fading |
| Nakagami-m 衰落 | Nakagami-\(m\) Fading |
| 级联信道 | Cascaded Channel |
| 乘性衰落 | Multiplicative Fading |
| 路径损耗指数 | Path Loss Exponent (\(\alpha\)) |
| 莱斯因子 | Rician Factor (\(\kappa\)) |
| 参考距离 | Reference Distance (\(d_0\)) |

## 4. 常用数学符号规范

| 符号 | 含义 | 规范 |
|------|------|------|
| \(\mathbf{h}_{AB}\) | 信道系数向量 | 粗体小写，下标为节点对 |
| \(\mathbf{H}_{BR}\) | BS-RIS 信道矩阵 | 粗体大写 |
| \(\mathbf{\Theta}\) | RIS/STARS 相移矩阵 | 花体大写 |
| \(\mathbb{E}\{\cdot\}\) | 期望运算 | 黑板粗体 |
| \(\mathbb{D}\{\cdot\}\) | 方差运算 | 黑板粗体 |
| \(f_X(\cdot)\) | 概率密度函数 (PDF) | 普通斜体 |
| \(F_X(\cdot)\) | 累积分布函数 (CDF) | 普通斜体大写 |

## 5. 研究领域标签

- B5G/6G 无线通信
- 非正交多址接入（NOMA）网络
- RIS/STARS 辅助通信
- 物理层安全通信
- 隐蔽通信（Covert Communication）
- 卫星通信与 LEO 星座
- 联邦学习（Federated Learning）
- 环境反向散射通信（AmBC）
