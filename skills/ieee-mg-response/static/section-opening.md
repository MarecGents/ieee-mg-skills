# 礼貌开场用语库（v0.1.2 完整版）

> 基于 3 篇语料（TWC u1: 29 条 + TWC u2: 25 条 + TGCN-RP: 19 条 = 73 条评审意见）蒸馏。
> 语料实测模式 + AI 拓展模板，共 9 大类、80+ 条句式。

## A. 通用感谢（适用于大多数情况）

### A1. 感谢型（语料实测，6 种核心变体 + 8 种拓展）

**核心变体（语料直接出现）**：

| # | 句式 | 频率 | 场景 |
|:--:|------|:----:|------|
| A1-1 | `We appreciate sincerely your insightful comments.` | 8/73 | 通用，最安全 |
| A1-2 | `Many thanks for the reviewer's kind comments.` | 7/73 | 通用，温和 |
| A1-3 | `We much value your quest for explicit clarity.` | 6/73 | 澄清型偏好 |
| A1-4 | `Sincere thanks for seeking explicit clarity.` | 6/73 | 澄清型偏好 |
| A1-5 | `Sincere thanks for seeking further clarifications.` | 5/73 | 多处澄清时 |
| A1-6 | `We thank the reviewer for this [valuable/important/suggestion].` | 15/73 | TGCN 专用模式 |

**AI 拓展变体（基于语料模式生成）**：

| # | 句式 | 基于 |
|:--:|------|------|
| A1-7 | `We appreciate sincerely your helpful suggestions.` | A1-1 变体 |
| A1-8 | `Many thanks for the reviewer's insightful observations.` | A1-2 变体 |
| A1-9 | `We greatly appreciate your thorough reading of our manuscript.` | A1-1 拓展 |
| A1-10 | `We would like to express our sincere gratitude for your constructive comments.` | A1-2 拓展 |
| A1-11 | `Many thanks for the reviewer's meticulous review and valuable feedback.` | A1-2 拓展 |
| A1-12 | `We sincerely thank you for the careful evaluation of our work.` | A1-4 变体 |
| A1-13 | `We deeply appreciate your time and effort in reviewing this manuscript.` | A1-1 拓展 |
| A1-14 | `Thank you for your constructive and detailed review.` | A1-5 变体 |

### A2. Editor 专用感谢

| # | 句式 | 频率 |
|:--:|------|:----:|
| A2-1 | `We sincerely appreciate the editor allow us to give more clarifications.` | 3/73 |
| A2-2 | `We sincerely thank you and the Reviewers for the time and effort invested in reviewing our manuscript.` | 1/73 |

---

## B. 澄清型开场（无正文修改）

### B1. 标准澄清

| # | 句式 | 频率 |
|:--:|------|:----:|
| B1-1 | `Sincere thanks for giving us the opportunity to clarify this point.` | 语料模板 |
| B1-2 | `We greatly appreciate the Reviewer's request for further clarification.` | 语料模板 |
| B1-3 | `Thank you for seeking further clarification on this important issue.` | 语料模板 |
| B1-4 | `We appreciate the Reviewer's comment and would like to clarify the following point.` | 语料模板 |

**AI 拓展**：

| # | 句式 |
|:--:|------|
| B1-5 | `We thank the reviewer for this clarification request.` |
| B1-6 | `We appreciate the Reviewer's keen observation, and we would like to provide further clarification.` |
| B1-7 | `This is a very pertinent question, and we would like to clarify it as follows.` |
| B1-8 | `We are grateful for this opportunity to provide additional clarification.` |

### B2. 澄清 + 技术解释衔接

| # | 句式 | 频率 |
|:--:|------|:----:|
| B2-1 | `We would like to clarify that [技术解释].` | 29/73（最高频句式） |
| B2-2 | `To clarify this point, [技术解释].` | AI 拓展 |
| B2-3 | `We would like to clarify the two points raised by the reviewer as follows.` | TGCN 语料 |
| B2-4 | `We would like to clarify the three aspects raised by the reviewer as follows.` | TGCN 语料 |

**AI 拓展**：

| # | 句式 |
|:--:|------|
| B2-5 | `The clarification is as follows. [技术解释]` |
| B2-6 | `In response to this query, we provide the following clarification.` |
| B2-7 | `We elaborate on this point below. [技术解释]` |

### B3. 澄清标准结尾

| # | 句式 | 说明 |
|:--:|------|------|
| B3-1 | `We hope that this clarification addresses the Reviewer's concern.` | 推荐使用 |
| B3-2 | `This point concerns the interpretation of the existing model and does not require a modification to the manuscript.` | 声明无需修改 |

---

## C. 修改型开场（接受并修改）

| # | 句式 | 频率 |
|:--:|------|:----:|
| C1 | `We agree with the Reviewer that this issue requires further clarification. As suggested, we have revised the relevant part of the manuscript accordingly.` | 13/73 |
| C2 | `As you kindly suggested, we have added the requested discussion and highlighted the revised text in blue.` | 5/73 |
| C3 | `We thank the Reviewer for catching this inconsistency. We have corrected the relevant notation and carefully checked the associated expressions.` | 语料模板 |
| C4 | `As suggested, we have revised the manuscript in line with the Reviewers' comments by improving both the clarity and contributions of the paper.` | TWC 总起 |
| C5 | `We have provided a per-user quantitative justification... and added a qualitative clarification together with an explicit conservativeness statement in Section II.` | TGCN 语料 |
| C6 | `We agree with the Reviewer that this issue requires further adding a brief note...` | TGCN 语料 |

**AI 拓展**：

| # | 句式 |
|:--:|------|
| C7 | `We fully agree with the Reviewer's assessment. In response, we have [具体修改].` |
| C8 | `Following the Reviewer's suggestion, we have revised the manuscript by [具体修改].` |
| C9 | `We acknowledge the validity of this comment and have made the following revision.` |
| C10 | `This is an excellent point. We have revised the manuscript to address this concern.` |
| C11 | `We thank the Reviewer for identifying this issue. We have corrected it as follows.` |
| C12 | `To address this concern, we have revised the relevant part of the manuscript as follows.` |
| C13 | `The relevant revised text is reproduced below for the Reviewer's convenience.` |

---

## D. 道歉型开场

### D1. 标准道歉（语料实测）

| # | 句式 | 频率 |
|:--:|------|:----:|
| D1-1 | `We apologize that the improper writing style of [X] leads to ambiguous understanding.` | 7/73 |
| D1-2 | `We apologize for the ambiguity caused by the previous wording.` | 语料模板 |
| D1-3 | `We apologize that the previous presentation was not sufficiently clear.` | 语料模板 |
| D1-4 | `We apologize for the typographical and grammatical errors in the previous version.` | 语料模板 |
| D1-5 | `We sincerely apologize for this oversight.` | TGCN 语料 |
| D1-6 | `We apologize for the parameter-setting error in [X].` | TGCN 语料 |
| D1-7 | `We apologize for the typographical inconsistency in the previous version.` | TGCN 语料 |

### D2. 感谢 + 道歉组合（TGCN 语料特有）

| # | 句式 | 说明 |
|:--:|------|------|
| D2-1 | `We thank the reviewer and apologize for the confusing wording.` | 感谢 + 道歉合一 |
| D2-2 | `We thank the reviewer for pointing out this gap, and we apologize for the inconsistency in the manuscript.` | 感谢 + 道歉 + 技术说明 |
| D2-3 | `We thank the reviewer for this suggestion. We apologize that the improper figure style of the explanations for the system model leads to ambiguous understanding.` | 三句组合 |

**AI 拓展**：

| # | 句式 |
|:--:|------|
| D2-4 | `We are grateful for the Reviewer's careful observation and sincerely apologize for this error.` |
| D2-5 | `We thank the Reviewer for bringing this to our attention. We acknowledge the mistake and have corrected it.` |
| D2-6 | `We deeply apologize for the oversight and appreciate the Reviewer's diligence in identifying this issue.` |

---

## E. 拒绝型/防御型开场

### E1. 超出范围（语料实测）

| # | 句式 | 频率 |
|:--:|------|:----:|
| E1-1 | `However, these considerations are beyond the scope of this work.` | 4/73 |
| E1-2 | `Since the estimation and feedback process is not the focus of this work, we ignore [具体假设].` | 2/73 |
| E1-3 | `It is worth pointing that [建议] can further enrich the contents of the paper, which is beyond the scope of the treatise.` | 2/73 |

### E2. 未来工作转嫁（语料实测）

| # | 句式 | 频率 |
|:--:|------|:----:|
| E2-1 | `Furthermore, our future work will relax this idealized assumption.` | 3/73 |
| E2-2 | `which will be considered in our future work.` | 1/73 |
| E2-3 | `which is set aside for our future treatise.` | 2/73 |

### E3. 惯例引用防御（TGCN 语料特有）

| # | 句式 | 说明 |
|:--:|------|------|
| E3-1 | `This is a common convention in the physical-layer security analysis of NOMA networks: the focus is on [X] rather than on [Y].` | 引用领域惯例 |
| E3-2 | `In particular, the same treatment is adopted in [ref], where [具体说明].` | 引用同类文献 |
| E3-3 | `To the best of our knowledge, our contribution is the new combination of [列表] with [创新点].` | 重新定义贡献 |

### E4. 承认但限定（TGCN 语料特有）

| # | 句式 | 说明 |
|:--:|------|------|
| E4-1 | `Although it is a special case, this setup captures the essential [X] of [Y] and represents the majority of practical deployment scenarios.` | 承认局限但强调价值 |
| E4-2 | `We acknowledge that several individual ingredients... have appeared in prior works. To the best of our knowledge, our contribution is the new combination of these ingredients with [具体创新].` | 承认部分重叠但强调组合创新 |
| E4-3 | `We acknowledge that a full [方法] treatment would further enrich this work, and we have explicitly listed it as future work.` | 承认不足并标注为未来工作 |
| E4-4 | `This is an inherent property of the analytical approximation rather than a modeling error; the simulation results are exact.` | 区分近似属性与建模错误 |

**AI 拓展**：

| # | 句式 |
|:--:|------|
| E4-5 | `We respectfully note that [理由]. After careful consideration, we have retained the original approach.` |
| E4-6 | `While we appreciate the suggestion, we believe that [理由] based on [证据].` |
| E4-7 | `We have carefully considered this suggestion. However, we believe the current formulation is more appropriate because [理由].` |
| E4-8 | `This suggestion is valuable. Although we have not adopted it in this revision, we have noted it for future investigation.` |

---

## F. 引出修改（过渡到 quote 块前）

### F1. 标准引出句（语料实测 + 高频形容词统计）

| # | 句式 | 频率 |
|:--:|------|:----:|
| F1-1 | `To address your [adj] comments, we have revised the manuscript as follows:` | 35/73 |
| F1-2 | `To address your [adj] comments, we have revised and updated our manuscript as follows:` | 5/73 |
| F1-3 | `To address your [adj] comments, we have revised and highlighted the manuscript as follows:` | 4/73 |
| F1-4 | `The relevant revised text is reproduced below for the Reviewer's convenience.` | 3/73 |
| F1-5 | `The relevant changes are provided below, with the modified sentences highlighted in blue.` | 3/73 |
| F1-6 | `The corresponding figure and the revised discussion are provided below.` | 2/73 |

**形容词频率排名**（与 "comments" 搭配）：

| 形容词 | 频率 | 语气 |
|--------|:----:|------|
| significant | 17 | 最强 |
| helpful | 10 | 中等 |
| important | 9 | 中等 |
| insightful | 6 | 中等 |
| critical | 1 | 强 |
| acute | 1 | 强 |
| astute | 1 | 强 |
| pivotal | 1 | 强 |
| constructive | 2 | 通用 |

**AI 拓展引出句**：

| # | 句式 |
|:--:|------|
| F1-7 | `To address your insightful comments, we have updated the figures and revised our paper as follows:` |
| F1-8 | `To better address your concerns, we have made the following revisions:` |
| F1-9 | `In response to your constructive feedback, we have revised the manuscript as follows:` |
| F1-10 | `To address the points raised, we provide our detailed response below:` |
| F1-11 | `As requested, we have revised the manuscript. The changes are highlighted below.` |
| F1-12 | `We have carefully addressed each comment and summarize the revisions below.` |

### F2. 多重修改引出（含新增图表/脚注）

| # | 句式 | 说明 |
|:--:|------|------|
| F2-1 | `Finally, to address your helpful comments, we have revised the manuscript and highlighted it as follows:` | 最后一条修改 |
| F2-2 | `To address your [adj] comments, we have updated the figures and revised our paper as follows:` | 含图表更新 |
| F2-3 | `To address your comments, we have added one footnote and pointed this in the manuscript as follows:` | 含脚注新增 |
| F2-4 | `To address your [adj] comments, we have revised and pointed out it in the manuscript as follows:` | TGCN 语料 |
| F2-5 | `The relevant revised paragraph is reproduced below for the Reviewer's convenience.` | 仅段落修改 |
| F2-6 | `This is copied here for your convenience:` | 简洁版 |

---

## G. 段首过渡（Reviewer 段落开头总起）

| # | 句式 | 频率 |
|:--:|------|:----:|
| G1 | `We would like to thank you for your valuable comments and constructive suggestions. We have revised the paper in line with your comments, thereby improving both the contribution and the clarity of the paper.` | 6/73（TWC 3 审稿人 × 2 文件） |
| G2 | `We sincerely thank Reviewer~N for the [positive assessment/careful reading/insightful comments]. We have revised the manuscript in line with all comments, which has [improved/clarified] [具体内容].` | 3/73（TGCN） |
| G3 | `We would like to thank you and the Reviewers for the precious time and efforts invested in reviewing our manuscript. According to your suggestions, we have updated the original manuscript and submitted a revised version.` | 2/73（Editor 段首） |

**AI 拓展**：

| # | 句式 |
|:--:|------|
| G4 | `We sincerely thank Reviewer~N for the thorough review and constructive suggestions, which have significantly improved the quality of this manuscript.` |
| G5 | `We are grateful to Reviewer~N for the detailed comments and insightful recommendations.` |

---

## H. 段尾（Reviewer 段落结束）

| # | 句式 | 频率 | 说明 |
|:--:|------|:----:|------|
| H1 | `Thanking you again for your generosity with your valuable time invested in improving our submission, sincerely.` | 8/73 | TWC 语料（4 处 × 2 文件） |
| H2 | 无显式段尾，直接 `\clearpage` | 19/73 | TGCN 语料 |
| H3 | `\noindent\textit{[Author List]}` | 8/73 | TWC 语料斜体签名 |

---

## I. 拒绝/防御型过渡（中段转折）

| # | 句式 | 频率 |
|:--:|------|:----:|
| I1 | `It is worth pointing out that [积极面]. However, [拒绝理由].` | 3/73 |
| I2 | `Furthermore, our future work will relax this idealized assumption.` | 3/73 |
| I3 | `Since [X] is not the focus of this work, we [简化处理].` | 2/73 |
| I4 | `In addition, we would like to clarify that [澄清内容].` | 3/73 |
| I5 | `Moreover, we would like to clarify that [补充说明].` | 1/73 |
| I6 | `For clarity of exposition, we have added [图表/说明] to illustrate [内容].` | 3/73 |
| I7 | `It is also worth noting that [补充说明].` | 3/73 |
| I8 | `As a result, we consider the application of [方法] to [场景] in this manuscript.` | 2/73 |
| I9 | `More specifically, we assume that [具体假设].` | 6/73 |

**AI 拓展**：

| # | 句式 |
|:--:|------|
| I10 | `While we acknowledge the validity of this suggestion, we respectfully maintain our original approach for the following reasons.` |
| I11 | `We have carefully considered this alternative. However, we believe our current formulation better captures [理由].` |
| I12 | `This is an important observation. We address it by [方法].` |
| I13 | `We appreciate this suggestion and note that [积极面]. However, [限定].` |
| I14 | `To provide additional context, [技术说明]. This is consistent with [文献/惯例].` |

---

## 场景组合速查表

### 澄清型标准三句组合
```
[A1-1] We appreciate sincerely your insightful comments.
[B2-1] We would like to clarify that [技术解释].
[B3-1] We hope that this clarification addresses the Reviewer's concern.
```

### 修改型标准三句组合
```
[C1] We agree with the Reviewer that this issue requires further clarification.
     As suggested, we have revised the relevant part of the manuscript accordingly.
[F1-1] To address your [significant] comments, we have revised the manuscript as follows:
```

### 道歉 + 修改型三句组合
```
[D1-5] We sincerely apologize for this oversight.
[C2] As you kindly suggested, we have added the requested discussion and
      highlighted the revised text in blue.
```

### 拒绝型三句组合
```
[E1-1] However, these considerations are beyond the scope of this work.
[E2-1] Furthermore, our future work will relax this idealized assumption.
[F1-1] To address your [significant] comments, we have revised the manuscript as follows:
```

### 感谢 + 道歉 + 澄清组合（TGCN 模式）
```
[D2-1] We thank the reviewer and apologize for the confusing wording.
[B2-1] We would like to clarify that [技术解释].
[F1-1] To address your [significant] comments, we have revised the manuscript as follows:
```
