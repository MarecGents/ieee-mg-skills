# 评论分类与处理策略

> 审稿意见的类型判断和处理策略，是 Response 质量的关键。

## 五维分类体系

### 1. 澄清型（Clarification）
审稿人对论文内容有误解，或要求更清晰的解释。

**判定标准**：
- 审稿人说 "Please clarify..." / "The authors should explain..." / "What is the meaning of..."
- 审稿人的理解有偏差，但论文内容本身正确
- 只需文字解释，无需修改正文

**处理策略**：
```latex
[开场：B1/B2/B3] + [清晰解释：直接回应问题] + [结尾：声明无需修改]

示例：
Sincere thanks for giving us the opportunity to clarify this
point. [具体解释 2-4 句话] We hope that this clarification
addresses the Reviewer's concern.
```

**⚠ 严格禁令**：
- ❌ 不得在澄清型回复中附任何蓝色修改摘录
- ❌ 不得写 "we have revised" / "we have added" 等暗示正文修改的措辞

### 2. 修改型（Accept & Revise）
审稿人指出合理问题，论文已做相应修改。

**判定标准**：
- 审稿人说 "The authors should revise..." / "This needs to be corrected..." / "Please add..."
- 审稿人的批评是合理的
- 已在正文中做相应修改

**处理策略**：
```latex
[开场：C1-C13 选择] + [承认问题] + [说明修改内容] + [引出 quote 块]

示例：
We agree with the Reviewer that this issue requires further
clarification. As suggested, we have revised the relevant part
of the manuscript accordingly.

\begin{quote}
\underline{[精确位置]:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[完整修改内容]}
\end{quote}
```

**必检项**：
- ✅ 正文对应位置是否已同步修改
- ✅ 蓝色摘录与正文是否逐字一致
- ✅ 位置标注是否精确

### 3. 部分接受型（Partial Accept）
审稿人提出多个子问题，部分接受、部分拒绝或保留。

**判定标准**：
- 审稿人提出复合建议（A + B + C），其中部分合理
- 需要区分对待每个子建议

**处理策略**：
```latex
[开场：E1-E4 选择] + [逐子问题处理]

示例：
We appreciate the Reviewer's constructive comment. For the first
part regarding [A], we have [具体修改]. For the second part
regarding [B], we respectfully note that [拒绝理由].
```

**多子问题的组织方式**（两种，按子问题性质选择）：

| 方式 | 适用 | 示例结构 |
|------|------|----------|
| **编号式 `1) 2) 3)`** | 子问题相互独立、可平行回答 | `1) We would like to point out that...` / `2) Based on point 1), ...` / `3) Likewise, ...` |
| **序数式 `First/Second/Third`** | 子问题有递进/依赖关系 | `First, ...` / `Second, ...` / `Third, we have corrected...` |

**共同约束**：每个子问题独立成段（空行分隔）；最后一段统一引出 quote 块。

### 跨评论引用惯例

当同一处正文修改回应了多个 comment，或某 comment 的修改连带影响其他 comment 时：

1. **主 comment**（修改的主要归属）：完整展示摘录 + 完整论证
2. **关联 comment**：展示摘录（内容与主 comment 一致），并在段落中加括号说明：
   `(The change of X to Y is addressed under Reviewer~N Comment~M.)`
3. **禁止**在关联 comment 中重复长篇论证（避免两处说法不一致）

**摘录重复是合法的**——不同审稿人提出相似意见，或一个修改覆盖多个意见时，同一高亮文本可在多个 Rx-Cx 下出现。这是特性，不是冗余。

### 4. 拒绝型（Defense/Rejection）
审稿人建议不合理，或超出论文范围。

**判定标准**：
- 审稿人的建议与论文假设/范围冲突
- 技术上不可行或不合理
- 需要论文范围外的大量工作

**处理策略**：
```latex
[开场：E1-E4 选择] + [礼貌说明理由] + [提供证据/引用]

示例：
We appreciate the Reviewer's valuable comment. However, we
respectfully note that [理由 1]. Moreover, as demonstrated
in [reference], [理由 2]. Therefore, we have retained the
original approach in the manuscript.
```

**拒绝型回应的三要素**：
1. **感谢**：承认审稿人的观点有价值
2. **解释**：用事实/理论/引用说明为什么不适合修改
3. **坚守**：明确表示保留原文（"we have retained..."）

**⚠ 拒绝的边界**：
- 拒绝必须有充分理由（不能只说"我们不同意"）
- 拒绝必须礼貌（不能用 "We disagree" 这样生硬的措辞）
- 如果审稿人强烈要求且理由充分，应考虑接受（而非固执拒绝）

### 5. 宽泛型（Broad/Vague）
审稿人给出模糊的、涉及面广的评论，如"grammar needs improvement"。

**判定标准**：
- 评论不指向具体位置或具体问题
- 可能涉及多处修改

**处理策略**：
```latex
[开场：D1-D2 选择] + [声明逐项检查] + [逐项列举每个修正]

示例：
We sincerely apologize for the typographical and grammatical
errors in the previous version. We have carefully checked the
entire manuscript and corrected each issue as follows.

[每个修正一个 quote 块，逐项列出]
```

**⚠ 严格规则**：
- ❌ 不得写 "The manuscript has been thoroughly proofread." 一句带过
- ✅ 必须逐个列出每个修正位置和内容
- ✅ 每个修正对应正文中的一个完整句子

## 评论类型速查表

| 审稿人常用措辞 | 典型类型 | 优先级 |
|----------------|----------|:------:|
| "Please clarify..." / "What is the meaning of..." | 澄清型 | 中 |
| "The authors should revise..." / "Please correct..." | 修改型 | 高 |
| "This is incorrect / wrong" | 修改型（严重） | 🔴 |
| "The authors should add..." / "Please include..." | 修改型 | 中 |
| "Please explain why..." / "The rationale is unclear" | 澄清型 | 中 |
| "I suggest..." / "It would be better if..." | 部分接受/拒绝 | 低 |
| "Grammar/typos need improvement" | 宽泛型 | 中 |
| "This is outside the scope" / "Not relevant" | 拒绝型 | 低 |
| "The comparison with [X] is missing" | 修改型 | 高 |
| "The authors should provide more references" | 修改型 | 中 |
| "The simulation is insufficient" | 修改型（严重） | 🔴 |
| "This assumption is too strong" / "unrealistic assumption" | 部分接受/拒绝 | 中 |
| "Not convincing" / "the claim is not supported" | 拒绝型（需论证） | 中 |
| "Why not compare with [method]?" | 修改型 | 中 |
| "The novelty is limited" / "incremental" | 部分接受/拒绝 | 中 |
| "Please provide the proof in the appendix" | 修改型 | 中 |

## 技术类别标签

除类型外，每条评论还应标注技术类别：

| 类别 | 说明 | 示例 |
|------|------|------|
| **motivation** | 动机/创新性 | "What is the novelty?" |
| **model** | 系统模型/假设 | "Why assume perfect CSI?" |
| **derivation** | 数学推导/公式 | "Please prove Theorem 2" |
| **simulation** | 仿真/参数/基准 | "Please add more benchmarks" |
| **writing** | 语言/格式/拼写 | "Grammar needs improvement" |
| **reference** | 参考文献 | "Please cite [X]" |
| **comparison** | 对比分析 | "Compare with [method X]" |
| **scope** | 范围/适用性 | "Does this apply to [scenario]?" |

## 组合处理示例

当一条评论同时涉及多个子问题时：

```latex
\noindent \textsf{\textbf{Comment 3:}}
\noindent \emph{[审稿人原文：包含子问题 a) 和 b)]}

\mySep
\noindent \textsf{{\textbf{Response:}}}

% 子问题 a)：修改型
We appreciate the Reviewer's comment. Regarding part (a), we
agree and have revised the manuscript accordingly.

\begin{quote}
\underline{[位置 a]:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[修改内容 a]}
\end{quote}

% 子问题 b)：拒绝型
Regarding part (b), we respectfully note that [理由]. After
careful consideration, we have retained the original approach.
```
