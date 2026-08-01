# Conclusion（结论）写作模板

> 基于课题组 21 篇论文结论语料深度蒸馏。
> **核心结构**：工作回顾 → 主要发现 → 数值总结 → 未来工作

## 一、标准结构模板

### 要素 1：开头句（必含）

**开头句式（语料实测分布，21 篇）：** 语料中不存在 "In this paper, we have investigated" 这一精确开头。实际开头以被动完成时回顾与 "This paper has + 过去分词" 两型主导：

**模式 1（最常见，约 48%）：被动完成时回顾**
```
In this paper, the [研究对象] has/have been investigated/studied/discussed [补语].
```
- "In this paper, the covert performance of ASTARS-NOMA networks was studied, where both reflection and transmission warden scenarios were taken into account."
- "In this paper, the secrecy performance of RIS-AmBC networks has been investigated in detail."

**模式 2（约 29%）：主语主动完成时**
```
This paper has investigated/studied [研究对象] [补语].
```
- "This paper has investigated the feasibility of the ASTARS uplink network utilizing OTA computing..."
- "This paper has studied the performance of RIS-TWR-NOMA networks, where a pair of users are able to exchange their information with the aid of a RIS."

**模式 3（约 10%）：第一人称一般过去时**
```
In this paper, we investigated/provided [研究对象].
```
- "In this paper, we investigated the outage probability of STARS-SGF-NOMA network with randomly distributed users."
- "In this paper, we provided both theoretical insights and practical guidelines for analyzing the physical layer secrecy of MF-RIS-assisted NOMA networks..."

**模式 4（约 14%）：This article 变体**
```
In this article, we have studied [研究对象] / the [研究对象] has been studied / [系统] are proposed ...
```
- "In this article, we have studied the novel ASTARS-NOMA networks with uniformly distributed paring users..."

**时态说明**：现在完成时在句中回顾具体动作时使用（"we have derived/investigated" 等，语料 9 处）；开头句本身以被动完成时（模式 1）与 "This paper has + 过去分词"（模式 2）为主。

### 要素 2：工作回顾（2-3 句）

**回顾核心句法模板：**
```
Specifically/More specifically, we have [动作1] [对象1] and [动作2] [对象2]. 
On this basis, we have [动作3] [对象3]. Furthermore/Additionally, we have [动作4].
```

**高频回顾动作库：**
| 动作 | 示例 |
|------|------|
| 推导表达式 | "derived the closed-form expressions of X for Y with ipSIC/pSIC" |
| 提出方案 | "proposed a novel X framework for Y" |
| 分析性能 | "analyzed the impact of X on Y in Z networks" |
| 优化问题 | "formulated the optimization problem to minimize X" |
| 验证结果 | "demonstrated the effectiveness of the proposed X" |

### 要素 3：主要发现（2-4 句，含数值支撑）

**发现陈述句式（语料中出现率 100%）：**
```
Numerical/Simulation results have demonstrated/shown/indicated that:
- [发现 1]
- [发现 2]
- [发现 3]
```

**发现三要素：**
1. **技术对比** — 本文方案 vs 基准方案
2. **参数影响** — 关键参数对性能的影响
3. **特殊洞察** — 非直观的观察或权衡

**发现句式模板（来自语料）：**

| 发现类型 | 句式模板 |
|----------|----------|
| **优势对比** | "The proposed X has achieved/outperformed Y by Z%..." |
| **参数影响** | "With the increasing of X, the Y is capable of achieving the enhanced Z..." |
| **特殊发现** | "Due to the balance between A and B, introducing excessive X is not helpful to reduce Y..." |
| **跨场景比较** | "The X of Y with ipSIC/pSIC outperforms that of Z at high SNRs..." |

### 要素 4：未来工作（1-2 句，约 70% 包含）

**标准句式：**
```
A promising future research direction is [具体方向].
```
或
```
Our future work will consider/investigate [具体方向].
```
或
```
Applying the X framework to [新场景] is capable of further providing additional 
design insights, which is one promising future research direction.
```

**课题组常用的未来方向（语料提取）：**
- 考虑非完美 CSI（imperfect CSI）的影响
- 扩展到宽带/多天线系统
- 优化反射/透射系数
- 结合人工智能/机器学习方法
- 研究更复杂的信道假设

---

## 二、课题组 Conclusion 写作特征

1. **时态：现在完成时主导**
   - 工作回顾：have investigated/have derived/have demonstrated
   - 发现陈述：Numerical results have demonstrated that...
   - 未来工作：一般将来时（"will consider"）或一般现在时（"is"）

2. **不分段**：约 80% 的结论为单一段落，200-400 词
3. **不出现新引用**：结论中不引入正文未讨论过的文献
4. **数值支撑**：主要发现通常有具体数值或百分比支撑
5. **与 Abstract 呼应但不同**：Abstract 用现在时，Conclusion 用现在完成时

## 三、写作检查清单
- [ ] 开头是否属于语料高频句式（"This paper has investigated/studied..." 或 "In this paper, the ... has been investigated..."）
- [ ] 时态是否正确（现在完成时回顾工作）
- [ ] 是否回顾了核心工作（做了什么）
- [ ] 是否总结了主要发现（发现了什么，含数值）
- [ ] 是否有与 Abstract 呼应的内容但不重复
- [ ] 是否有未来工作方向（1-2 句）
- [ ] 是否没有引入新信息
- [ ] 是否没有过度夸大研究的重要性
- [ ] 语气是否冷静客观
- [ ] 长度是否在 200-400 词范围内

## 四、第一轮蒸馏补充（语料发现的新模式）

### 4.1 多层数值对比（缺失21）
在要素3中新增多层对比模板：
```
[本文方案] has achieved [指标值], closely approaching [理想方案].
Compared to [基准A] and [基准B], [本文方案] has attained ~[X%] and [Y%], respectively.
Furthermore, [本文方案] has outperformed [基准C] by [百分比].
```
结论中的数值应比Abstract更具体（带百分比），比正文更精炼。

### 4.2 局限性→未来工作因果结构（缺失22）
```
[当前假设的局限性]: The setting of [假设] may give rise to overestimated performance.
[因果过渡]: hence our future work will [改进方向].
[第二个方向]: Another promising future research direction is [方向2].
```
常见局限来源：perfect CSI, single antenna, Rayleigh fading, pSIC assumption。

### 4.3 顺序词串联模式（缺失23）
替代编号列表的流畅风格：
```
Numerical results firstly demonstrated [发现1].
Secondly, [发现2].
Finally, [发现3].
```
适用于2-3个发现。

### 4.4 实际应用场景落点（缺失24）
在结论末尾新增落点句：
```
From the perspective of practical applicability, [本文系统] is capable of satisfying [实际需求],
where [用户X] can be [具体场景A] and [用户Y] can be [具体场景B].
```

### 4.5 被动语态确认句式（缺失25）
```
- "It has been shown that..."（现在完成时，确认已获得的结果）
- "It was demonstrated that..."（过去时，引用正文中的发现）
- "It can be confirmed that..."（情态被动，强调可信度）
```
