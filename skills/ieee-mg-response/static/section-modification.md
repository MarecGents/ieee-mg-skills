# 正文修改模板

> 当审稿人意见属于"修改型"时，Response 中展示修改的标准格式。

## 核心原则

正文修改在 Response 中的展示遵循 **"位置 + 内容"** 模式：先用 `\underline{}` 标注精确位置，再用 `\RevisedExcerpt{...}` 或 `\textcolor[rgb]{0.00,0.00,1.00}{...}` 高亮完整修改内容。**位置必须精确，内容必须完整**——不可只高亮单个单词。

> **推荐使用** `\RevisedExcerpt{...}` 宏（= `\textit{\textcolor[rgb]{0.00,0.00,1.00}{...}}`），比纯 `\textcolor` 更醒目。宏定义见 `section-latex-format.md`。

## 修改展示模板

### 模板 A：文字修改（最常见）

```latex
\begin{quote}
\underline{[具体位置：精确到小节/段落/句子序号]:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[包含修改词的完整句子——不是片段，是完整的句子]}
\end{quote}
```

**位置标注示例**（从语料中提炼）：
```latex
\underline{First paragraph of ``Motivation and Novelty'' in Section I-A:}\\
\underline{Second sentence of the first paragraph of Section IV-B:}\\
\underline{Caption of Fig.~8 in ``Secrecy System Throughput'' in Section IV:}\\
\underline{Renamed subsection ``Motivation and Novelty'' of Introduction in Section I-A:}\\
\underline{Theorem 2, after the ipSIC SOP expression, in Section III:}\\
```

### 模板 B：段落修改（整段替换或新增段落）

```latex
\begin{quote}
\underline{New paragraph added after Eq.~(N) in Section III-B:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[完整新增段落]}
\end{quote}
```

### 模板 C：公式修改

**公式摘录三类格式（⚠ 三者的格式不可混用）**：

| 类型 | 判定 | 正文格式 | Response 摘录格式 |
|------|------|----------|-------------------|
| **独立编号公式** | 正文中是 `\begin{align}...\end{align}` 独立公式 | `\textadd{公式整体}` | `\begin{align} 公式 \tag{N} \end{align}` 包在 `\textcolor` 内（**不含** `\label`） |
| **where 块行内公式** | 公式在 where 块中，形如 `$...$,` 逐项排列 | `\textadd{$...$}` 逐项 | **行内 `$...$`**，用逗号分隔，**不可**放进 align 环境 |
| **公式内符号引用** | 正文中引用公式编号（`\eqref{}`） | — | 转为字面编号 `Eq.~(N)` |

**独立编号公式示例**：
```latex
\begin{quote}
\underline{Eq.~(N) in Section III:}\\
\textcolor[rgb]{0.00,0.00,1.00}{\begin{align} 公式内容 ,\tag{N} \end{align}}
\end{quote}
```

**where 块行内公式示例**：
```latex
\begin{quote}
\underline{Definition of $\xi_r$ in Section II:}\\
\textcolor[rgb]{0.00,0.00,1.00}{$\xi_r = f(\mathbf{h}_{br}, \mathbf{h}_{re})$, where $\mathbf{h}_{br}$ denotes...}
\end{quote}
```

**公式修正引导语**（语料原句风格）：
```latex
As suggested, we have corrected Eq.~(N) and added the corresponding
explanation below the equation. The derivation structure remains unchanged.
```

### 模板 D：表格修改

```latex
To address this concern, we have added the following table in
Section IV to provide additional simulation details.

\begin{table}[t!]
\centering
\caption{\textcolor[rgb]{0.00,0.00,1.00}{TABLE III: [新增表格标题]}}
\label{tab:new}
\begin{tabular}{lcc}
\hline
\textbf{Parameter} & \textbf{Value 1} & \textbf{Value 2} \\
\hline
[数据行]
\hline
\end{tabular}
\end{table}
```

**注意**：在 Response 文档中，表格标题使用字面 `Table~I`（而非 `\ref{tab:label}`），因为 Response 通常是独立文档。

### 模板 D 附注：表格高亮的技术限制

LaTeX 的 `table` 是浮动体，**无法**用 `\textadd{}` 整体包裹。替代方案：
1. **单元格级高亮**（推荐）：对新增/修改的每个单元格用 `\textcolor[rgb]{0.00,0.00,1.00}{}` 包裹
2. **caption 高亮**：`\caption{\textcolor[rgb]{0.00,0.00,1.00}{...}}`
3. **放弃表格高亮**：仅在 Response 叙述中说明"新增表格"（用户可接受时最简方案）

### 模板 E：新增图表

```latex
Thank you for this helpful suggestion. As suggested, we have
added/redrawn Fig.~N to illustrate the impact of [parameter]
on [metric]. The corresponding discussion has also been revised
in [section].

\begin{figure}[t!]
    \begin{center}
        \includegraphics[width=3.48in,height=2.8in]{[filename].eps}
        \caption*{\textcolor[rgb]{0.00,0.00,1.00}{Fig.~N: [caption text]}}
        \label{fig:new}
    \end{center}
\end{figure}
```

**关键区别**：
- Response 中用 `\caption*{}`（无编号）而非 `\caption{}`（自动编号）
- caption 文本用蓝色高亮，表明这是新增内容

### 模板 F：参考文献插入

当需要引用新文献来支撑回应时，在该 Comment 的末尾插入：

```latex
\begin{quote}
{\footnotesize
[N] Author1, Author2, and Author3, ``Title of the paper,''
\emph{Journal Name}, vol. X, no. Y, pp. Z--W, Month Year.}
\end{quote}
```

## 修改位置标注规范

### 标注格式
```
\underline{[层次1] of/after/in [层次2] in Section [编号]:}
```

### 层次结构（从大到小）
1. **Section**（章节）：Section I, Section II-B, Section IV-A
2. **Subsection**（小节）：the first/second paragraph, subsection title
3. **Element**（元素）：Eq.~(N), Fig.~N, Table~I, Theorem N, Lemma N
4. **Sentence**（句子）：the Nth sentence, the first/second paragraph

### 位置标注示例库（语料原句）

```latex
% 段落级别
\underline{First paragraph of ``Motivation and Novelty'' in Section I-A:}
\underline{Last paragraph of Section II:}

% 句子级别
\underline{Second sentence of the first paragraph of Section IV-B:}

% 公式级别
\underline{Eq.~(3) in Section II:}
\underline{After the ipSIC SOP expression in Section III:}

% 图表级别
\underline{Caption of Fig.~8 in ``Secrecy System Throughput'' in Section IV:}

% 章节重命名
\underline{Renamed subsection ``Motivation and Novelty'' of Introduction in Section I-A:}
```

## 多处修改的处理

当一条评论导致多处修改时，**每处修改独立一个 quote 块**：

```latex
As suggested, we have revised the manuscript in multiple places:

\begin{quote}
\underline{Caption of Fig.~2 in Section II:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[完整的新 caption]}
\end{quote}

\begin{quote}
\underline{Second paragraph of Section III-B:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[修改后的完整句子]}
\end{quote}
```

**末句保护规则**：插入删除说明或补充说明时，应插入到 Response 段落中部（正文解释之后、引出 quote 块的过渡句之前）。**必须保持原段落的末句不变**——末句通常是 "To address your.../The relevant...below" 的引出句，改动会破坏段落收束感。

## 语法/拼误修正的逐项列举

当审稿人给出宽泛语法评论时（如"typos and grammar issues"），**必须逐项拆解**：

```latex
We sincerely appreciate the Reviewer's careful observation. We
apologize for the typographical and notation inconsistencies in
the previous version. We have carefully checked the manuscript
and corrected each issue as follows.

\begin{quote}
\underline{Caption of Fig.~3 in Section II:}\\
\textcolor[rgb]{0.00,0.00,1.00}{BCPU $\rightarrow$ BPCU}
\end{quote}

\begin{quote}
\underline{Title of Table~I in Section IV:}\\
\textcolor[rgb]{0.00,0.00,1.00}{ASTRS $\rightarrow$ ASTARS}
\end{quote}

\begin{quote}
\underline{First paragraph of Section III-A:}\\
\textcolor[rgb]{0.00,0.00,1.00}{amplitude $\rightarrow$ power-splitting}
\end{quote}

\begin{quote}
\underline{Notation table in Section II:}\\
\textcolor[rgb]{0.00,0.00,1.00}{$\rho$ $\rightarrow$ $\rho_e$}
\end{quote}

\begin{quote}
\underline{Caption of Fig.~5 in Section IV:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[Eve 侧 $\varepsilon$ 符号修正的完整 caption]}
\end{quote}
```

**⚠ 严格规则**：
- 每个修正对应**一个** quote 块
- 正文中高亮包含该修改的**完整句子**（不是单个单词）
- 不可合并为 "We have proofread the entire manuscript." 一句带过

## 禁止事项

- ❌ 不可在 quote 块中只展示片段（必须是完整句子或完整 caption）
- ❌ 不可遗漏位置标注
- ❌ 不可使用 `\caption{}` 代替 `\caption*{}` 插入 Response 中的新图
- ❌ 不可在 Response 中使用 `\ref{}` 引用正文 label（用字面编号）

## Future Work 与脚注处理

### 原则

**小型修改立即实施**：凡是可以通过修改正文或新增仿真完成的，优先接受意见并在本轮修改中落地，**不要泛泛地写入 future work**。

**确实超出范围时使用脚注**：只有真正超出本轮修改范围的内容，才可使用脚注说明。

### 脚注模板（语料实测）

```latex
% 正文中使用（仅在论文正文 .tex 中）
\textadd{A complete cross-region analysis involving [具体范围]
is left for future work.\footnote{Future work will consider
[具体内容] under [具体条件] conditions.}}

% Response 中展示时使用蓝色高亮（与正文修改同步）
\begin{quote}
\underline{New footnote added at the end of Section IV:}\\
\RevisedExcerpt{A complete cross-region analysis involving [scope]
is left for future work.\footnote{Future work will consider
[details] under [conditions] conditions.}}
\end{quote}
```

### 正文脚注 + Response 摘录的对应写法

**正文**：`\textadd{...文本\footnote{脚注内容}}`（`\footnote` 在 `\textadd` 内）
**Response 摘录**：推荐用上标替代 `\footnote`（避免 Response 文档中脚注排版不受控）：

```latex
\begin{quote}
\underline{[位置]:}\\
\RevisedExcerpt{...文本${}^1$.\\
${}^1$ [脚注内容]}
\end{quote}
```

**注意**：脚注内容也是正文修改的一部分，必须在 Response 中完整展示（不可省略）。

## 删除内容的 Response 处理

当正文删除了某段文本（非替换，而是彻底移除），Response 中**不使用蓝色高亮删除**，而是用叙述文字说明：

**删除说明的三种写法**：

1. **只说明不展示**（推荐，最常见）：
```latex
Accordingly, the sentence ``[被删原文的前几个关键词]...'' has been
removed from [位置], since [删除理由].
```

2. **交叉引用他处**（当删除是其他 comment 的连带结果）：
```latex
...as its content is already covered by the revised statement under
Reviewer~N Comment~M.
```

3. **源码保留备查**（仅源码层面）：用 `%` 逐行注释掉，不进入编译输出。

**禁止**：❌ 对被删除内容使用蓝色高亮。❌ 只用一句"we have removed it"而不引用原文（审稿人无法核对删了什么）。
