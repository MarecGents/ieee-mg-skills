# 逻辑连接词详细指南

> 基于课题组 21 篇论文语料的逻辑连接词使用分析，含使用频率、场景和例句。
> 被 ieee-mg-writing 和 ieee-mg-polishing 共同引用。
> **统计口径（v1.2.0）**：以下星级按 grep 行级计数（6 个语料文件全量，不区分大小写，每行最多计 1 次）。星级映射：★=1-5 行、★★=6-15 行、★★★=16-35 行、★★★★=36-70 行、★★★★★=71+ 行。All Paper Title.md 为汇总快照（与分章节文件有重复行），本表计数含重复；5 个章节分文件口径约为本表 0.5-0.6 倍，相对排序一致。

## 0. 连接词实测总排序（v1.2.0）

| 排名 | 连接词 | 行数 | 星级 | 功能 |
|:----:|--------|:----:|:----:|------|
| 1 | due to | 222 | ★★★★★ | 因果 |
| 2 | furthermore | 169 | ★★★★★ | 递进 |
| 3 | while | 161 | ★★★★★ | 转折/对比 |
| 4 | in addition | 156 | ★★★★★ | 递进 |
| 5 | additionally | 123 | ★★★★★ | 递进 |
| 6 | moreover | 121 | ★★★★★ | 递进 |
| 7 | however | 105 | ★★★★★ | 转折 |
| 8 | specifically | 102 | ★★★★★ | 强调 |
| 9 | hence | 83 | ★★★★★ | 结论 |
| 10 | thus | 52 | ★★★★ | 结论 |
| 11 | therefore | 42 | ★★★★ | 结论 |
| 12 | in particular | 30 | ★★★ | 强调 |
| 13 | such as | 29 | ★★★ | 举例 |
| 14 | thereby | 27 | ★★★ | 因果 |
| 15 | on the other hand | 25 | ★★★ | 对比 |
| 16 | as a result | 23 | ★★★ | 因果 |
| 17 | although | 20 | ★★★ | 转折 |
| 18 | in contrast | 18 | ★★★ | 对比 |
| 19 | consequently | 16 | ★★★ | 结论 |
| 20 | as a consequence | 15 | ★★ | 结论 |
| 21 | whereas | 13 | ★★ | 对比 |
| 22 | owing to | 9 | ★★ | 因果 |
| 23 | nevertheless | 8 | ★★ | 转折 |
| 24 | e.g. | 8 | ★★ | 举例 |
| 25 | besides | 8 | ★★ | 递进 |
| 26 | for example | 6 | ★★ | 举例 |
| 27 | because of | 6 | ★★ | 因果 |
| 28 | notably | 4 | ★ | 强调 |

## 1. 因果连接词

| 连接词 | 语料频率 | 使用场景 | 例句 |
|--------|----------|----------|------|
| **due to** | ★★★★★（222 行，全库最高频连接词） | 原因解释（置于句首或句中） | "Due to the influence of RI, the outage behavior of the n-th user with ipSIC is inferior to OMA." |
| **because of** | ★★（6 行） | 原因解释（口语化稍强，语料低频，慎用） | "This is because of the balance between thermal noise and residual interference." |
| **owing to** | ★★（9 行） | 正式书面原因 | "Owing to the multiplicative fading, the performance of PRIS is limited." |
| **as a result** | ★★★（23 行） | 结果引出（句首） | "As a result, the diversity order of the n-th user with ipSIC is zero." |
| **thereby** | ★★★（27 行） | 表示由此导致 | "The signals can be amplified, thereby overcoming multiplicative fading." |
| **hence** | ★★★★★（83 行） | 正式推导结论（结论词第一） | "Hence, CD-NOMA is capable of providing better fairness than OMA." |

## 2. 转折/对比连接词

| 连接词 | 语料频率 | 使用场景 | 例句 |
|--------|----------|----------|------|
| **however** | ★★★★★（105 行） | 句首转折，引出相反观点 | "However, the unique advantages offered by ASTARS remain underutilized in FL scenarios." |
| **nevertheless** | ★★（8 行） | 正式转折，让步之后 | "Nevertheless, the massive influx of users will lead to QoS degradation." |
| **although** | ★★★（20 行） | 从句开头，让步 | "Although X has been studied, the integration of X and Y is still in its infancy."（注意：单数主语 integration 配 its，非 their） |
| **whereas** | ★★（13 行） | 并列对比两个事实 | "The n-th user with pSIC can attain diversity order of nK, whereas the m-th user obtains nM." |
| **while** | ★★★★★（161 行） | 多种功能（转折/时间/对比） | "While the aforementioned works have laid a solid foundation, ASTARS-FL remains emerging." |
| **in contrast** | ★★★（18 行） | 强烈的对比对照 | "In contrast, the proposed ASTARS-SCA-FL has outperformed other ASTARS variants." |
| **on the other hand** | ★★★（25 行） | 平衡地引出另一方面（常与 On the one hand 配对） | "On the other hand, the impact of thermal noise on secure transmission remains unknown." |

## 3. 递进/补充连接词

| 连接词 | 语料频率 | 使用场景 | 例句 |
|--------|----------|----------|------|
| **furthermore** | ★★★★★（169 行，递进词第一） | 进一步补充 | "Furthermore, the proposed ASTARS-assisted system outperforms state-of-the-art baselines." |
| **in addition** | ★★★★★（156 行） | 附加信息 | "In addition, the ASCA algorithm is applied to jointly optimize the ASTARS phase shift." |
| **additionally** | ★★★★★（123 行） | 同 in addition | "Additionally, the system throughput in delay-limited mode is discussed." |
| **moreover** | ★★★★★（121 行） | 递进补充 | "Moreover, we also evaluate the impact of total power budget on secure communication." |
| **besides** | ★★（8 行） | 补充（语料低频） | "Besides, the number of RIS elements has an optimal value." |
| **notably** | ★（4 行） | 强调重要补充（语料极少，慎用） | "Notably, the outage behaviors of CD-NOMA is superior to PD-NOMA." |

> **⚠ 单词过渡词综合征警示（v1.2.0 例词按实测高频重写）**
>
> **问题**：连续 ≥3 句以 Furthermore / In addition / Additionally / Moreover / However 等单一连接词开头，段落读感变为机械清单。
>
> **危害**：递进补充连接词是最易滥用的类别。它们"存在感强但信息量低"——读者读到的是"又有另一个工作"，而非"这个工作在这个子主题下处于什么位置"。
>
> **正确做法**：在文献综述段落（Introduction Layer 3）中，交替使用**主题引导短语**（To exploit spatial degrees of freedom,）、**自然承接**（无过渡词）、**引用开头**（In \cite{...},），将单词过渡词使用限制在每段 ≤1 次。详见 paragraph-rhythm.md 第 4 节。
>
> **判定方法**：逐句取句首 1-3 词，落在 {Furthermore, In addition, Additionally, Moreover, However, Meanwhile, Notably, Besides} 即计为过渡词开头；连续 ≥3 句命中即违规。

## 4. 举例/说明连接词

| 连接词 | 语料频率 | 使用场景 |
|--------|----------|----------|
| **such as** | ★★★（29 行） | 举例列举 | "Various scenarios such as artificial intelligence, smart cities..." |
| **for example** | ★★（6 行） | 举例 | "For example, by adopting a channel-aware client selection strategy..." |
| **e.g.** | ★★（8 行） | 正式举例（括号中） | "the impact of system parameters (e.g., number of elements, power allocation)" |
| **in particular** | ★★★（30 行） | 强调特定方面 | "In particular, the impacts of ipSIC on MCS protocol are taken into account." |
| **specifically** | ★★★★★（102 行，强调词第一） | 具体说明（"More specifically" 高频变体） | "More specifically, we derive the expressions of outage probability for X." |

## 5. 结论/总结连接词

| 连接词 | 语料频率 | 使用场景 |
|--------|----------|----------|
| **hence** | ★★★★★（83 行） | 正式推导结论（结论词第一） | "Hence, CD-NOMA is capable of providing better fairness than OMA." |
| **thus** | ★★★★（52 行） | 正式结论 | "Thus, the total complexity is O(I·MN), where I is the number of iterations." |
| **therefore** | ★★★★（42 行） | 逻辑推导结论 | "Therefore, the deployment of STARS effectively extends the service area of BS." |
| **consequently** | ★★★（16 行） | 结果必然性 | "Consequently, design of effective multiuser receiver algorithm is significant." |
| **as a consequence** | ★★（15 行） | 强烈因果关系 | "As a consequence, the RI signal from imperfect cancelation operation is the dominant impact factor." |

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

### 连接词密度控制（v1.2.0 按实测修正）
- Introduction 连接词密度约 7-10 个/千词（实测约 7.7/千词，grep 核心连接词计数；与 quantitative-baseline.md §5 同一口径）
- Abstract 连接词密度最低（每段 1-2 个）
- 避免连续两句使用同一连接词；同段内同功能词不超过 2 次
