# 逻辑连接词详细指南

> 基于课题组 21 篇论文语料的逻辑连接词使用分析，含使用频率、场景和例句。
> 被 ieee-mg-writing 和 ieee-mg-polishing 共同引用。

## 1. 因果连接词

| 连接词 | 语料频率 | 使用场景 | 例句 |
|--------|----------|----------|------|
| **due to** | ★★★★★ | 原因解释（置于句首或句中） | "Due to the influence of RI, the outage behavior of the n-th user with ipSIC is inferior to OMA." |
| **because of** | ★★★ | 原因解释（口语化稍强） | "This is because of the balance between thermal noise and residual interference." |
| **owing to** | ★★ | 正式书面原因 | "Owing to the multiplicative fading, the performance of PRIS is limited." |
| **as a result** | ★★★ | 结果引出（句首） | "As a result, the diversity order of the n-th user with ipSIC is zero." |
| **thereby** | ★★★ | 表示由此导致 | "The signals can be amplified, thereby overcoming multiplicative fading." |
| **hence** | ★★ | 正式推导结论 | "Hence, CD-NOMA is capable of providing better fairness than OMA." |

## 2. 转折/对比连接词

| 连接词 | 语料频率 | 使用场景 | 例句 |
|--------|----------|----------|------|
| **however** | ★★★★★ | 句首转折，引出相反观点 | "However, the unique advantages offered by ASTARS remain underutilized in FL scenarios." |
| **nevertheless** | ★★★ | 正式转折，让步之后 | "Nevertheless, the massive influx of users will lead to QoS degradation." |
| **although** | ★★★★ | 从句开头，让步 | "Although X has been studied, the integration of X and Y remains unexplored." |
| **whereas** | ★★★ | 并列对比两个事实 | "The n-th user with pSIC can attain diversity order of nK, whereas the m-th user obtains nM." |
| **while** | ★★★★★ | 多种功能（转折/时间/对比） | "While the aforementioned works have laid a solid foundation, ASTARS-FL remains emerging." |
| **in contrast** | ★★★ | 强烈的对比对照 | "In contrast, the proposed ASTARS-SCA-FL has outperformed other ASTARS variants." |
| **on the other hand** | ★★ | 平衡地引出另一方面 | "On the other hand, the impact of thermal noise on secure transmission remains unknown." |

## 3. 递进/补充连接词

| 连接词 | 语料频率 | 使用场景 | 例句 |
|--------|----------|----------|------|
| **moreover** | ★★★★★ | 递进补充（最常用） | "Moreover, we also evaluate the impact of total power budget on secure communication." |
| **furthermore** | ★★★★ | 进一步补充 | "Furthermore, the proposed ASTARS-assisted system outperforms state-of-the-art baselines." |
| **in addition** | ★★★ | 附加信息 | "In addition, the ASCA algorithm is applied to jointly optimize the ASTARS phase shift." |
| **additionally** | ★★★ | 同 in addition | "Additionally, the system throughput in delay-limited mode is discussed." |
| **besides** | ★ | 非正式补充（建议少用） | "Besides, the number of RIS elements has an optimal value." |
| **notably** | ★★ | 强调重要补充 | "Notably, the outage behaviors of CD-NOMA is superior to PD-NOMA." |

> **⚠ 单词过渡词综合征警示**
>
> **问题**：连续 ≥3 句以 Meanwhile / Furthermore / Additionally / Moreover / In addition / Notably / Besides 等单一递进补充词开头，段落读感变为机械清单。
>
> **危害**：递进补充连接词是所有连接词类别中最易滥用的。它们“存在感强但信息量低”——读者读到的是“又有另一个工作”，而非“这个工作在这个子主题下处于什么位置”。
>
> **正确做法**：在文献综述段落（Introduction Layer 3）中，交替使用**主题引导短语**（To exploit spatial degrees of freedom,）、**自然承接**（无过渡词）、**引用开头**（In \cite{...},），将单词过渡词使用限制在每段 ≤1 次。详见 paragraph-rhythm.md 第 4 节。
>

## 4. 举例/说明连接词

| 连接词 | 语料频率 | 使用场景 |
|--------|----------|----------|
| **such as** | ★★★★★ | 举例列举 | "Various scenarios such as artificial intelligence, smart cities..." |
| **for example** | ★★★ | 举例 | "For example, by adopting a channel-aware client selection strategy..." |
| **e.g.** | ★★★ | 正式举例（括号中） | "the impact of system parameters (e.g., number of elements, power allocation)" |
| **in particular** | ★★★★ | 强调特定方面 | "In particular, the impacts of ipSIC on MCS protocol are taken into account." |
| **specifically** | ★★★★★ | 具体说明 | "More specifically, we derive the expressions of outage probability for X." |

## 5. 结论/总结连接词

| 连接词 | 语料频率 | 使用场景 |
|--------|----------|----------|
| **therefore** | ★★★★ | 逻辑推导结论 | "Therefore, the deployment of STARS effectively extends the service area of BS." |
| **thus** | ★★★ | 正式结论 | "Thus, the total complexity is O(I·MN), where I is the number of iterations." |
| **consequently** | ★★ | 结果必然性 | "Consequently, design of effective multiuser receiver algorithm is significant." |
| **as a consequence** | ★ | 强烈因果关系 | "As a consequence, the RI signal from imperfect cancelation operation is the dominant impact factor." |

## 6. 连接词组合使用规范

### 常用配对
| 配对 | 模式 |
|------|------|
| "Although ... however" | "Although X has been studied, however, ..."（少用，口语化） |
| "While ... in contrast" | While 从句 + 主句 + in contrast 对比 |
| "Due to ... therefore" | Due to X, therefore Y...（不应同时使用，重复因果） |

### 连接词在句中的位置
- **句首**：however, moreover, furthermore, therefore, in addition, notably
- **句中**：due to, because of, compared to, such as
- **从句首**：although, while, whereas, because

### 连接词密度控制
- Introduction 中连接词密度最高（每段 3-5 个）
- Abstract 中连接词密度最低（每段 1-2 个）
- 避免连续两句使用同一连接词
