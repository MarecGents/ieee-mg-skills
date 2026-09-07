# Editor 回复专用模板

> Editor 回复的格式与 Reviewer 不同——采用**编号逐点格式**，而非 Comment/Response 分隔格式。

## Editor 回复特点

| 特征 | 说明 |
|------|------|
| 格式 | 编号逐点（1), 2), 3)...） |
| 语气 | 最为礼貌（对 Editor 保持最高敬意） |
| 篇幅 | 通常 3-5 条，较 Reviewer 简短 |
| 内容 | 回应格式要求、大修要求、Summary of Changes 等 |
| 位置 | Cover Letter 之后、Reviewer 回复之前 |

## Editor 回复标准结构

### 段头

```latex
\begin{center}
{\Large \textbf{Response to Editor}}
\end{center}

\vspace{8pt}

\noindent We sincerely thank the Editor for the careful evaluation
and constructive suggestions, which have helped us improve the
quality of this manuscript.
```

### 正文（编号逐点格式）

```latex
1) [回应第一点]

2) [回应第二点]

3) [回应第三点]
```

### 段尾

```latex
\vspace{8pt}

\noindent We hope that the above revisions adequately address
all the concerns raised by the Editor.

Sincerely,
[Author List]
```

## 常见 Editor 评论类型及回应模板

### 类型 A：要求修改格式/排版

```latex
1) We have carefully revised the manuscript to comply with the
journal formatting requirements. All figures have been resized
to the proper width, and the reference style has been updated
to follow the IEEE format.
```

### 类型 B：要求增加 Motivation/Contribution

```latex
2) As suggested, we have revised the introduction to better
highlight the novelty and contributions of this work. The
revised motivation and contribution paragraph is reproduced
below.

\begin{quote}
\underline{Revised ``Motivation and Novelty'' paragraph in
Section I:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[完整修订段落]}
\end{quote}
```

### 类型 C：要求补充仿真/验证

```latex
3) We appreciate the suggestion. We have conducted additional
simulations to validate the theoretical analysis. The new
results have been included in Section IV and are shown in
Fig.~N.
```

### 类型 D：要求修改语言/表述

```latex
4) We have thoroughly proofread the manuscript and corrected
all the grammatical and typographical errors. The revised
text has been highlighted in blue where applicable.
```

### 类型 E：要求上传修改说明（Summary of Changes）

```latex
5) A detailed summary of all changes has been prepared and
will be uploaded as a separate document, as requested. The
summary includes:
   - A list of all revisions made in response to each comment
   - The location of each change in the manuscript
   - A brief description of the nature of each change
```

## Editor 回复中的 Summary of Changes

Editor 经常要求单独提交 "Summary of Changes"。此部分通常**直接展开**，不写 "See page X"：

```latex
\begin{center}
{\Large \textbf{Summary of Changes}}
\end{center}

\vspace{8pt}

The following summarizes the major changes made in this revision:

\begin{enumerate}
\item \textbf{Introduction (Section I):} Revised the motivation
and contribution paragraph to better highlight the novelty of
this work [see page X, lines Y--Z].

\item \textbf{System Model (Section II):} Added the detailed
description of the channel model [see page X, lines Y--Z].

\item \textbf{Numerical Results (Section IV):} Added new
simulation results comparing with [method] [see Fig.~N and
Table~I].

\item \textbf{Conclusion (Section V):} Revised the conclusion
to reflect the additional results.

\item \textbf{Throughout:} Corrected grammatical errors and
improved the overall writing quality.
\end{enumerate}
```

## 特殊情况

### Editor 转达 Reviewer 意见

有时 Editor 会转达 Reviewer 的意见（而非直接要求你回复 Reviewer）。此时：
- 在 Editor 段落中简要回应
- 在对应的 Reviewer 段落中详细展开

```latex
% 在 Editor 回复中
3) We thank the Editor for bringing this to our attention.
We have addressed this concern in detail in our response to
Reviewer [N] (Comment [M]).

% 在 Reviewer 回复中详细展开
```

### Editor 要求"逐条回复所有 Reviewer"

```latex
% 在 Editor 回复中简要声明
2) We have provided detailed point-by-point responses to all
three Reviewers below. Each reviewer comment is quoted in
\emph{italic}, and our responses are given in normal font,
with revised text highlighted in blue.
```

## 与 Reviewer 回复的格式对比

| 元素 | Editor 回复 | Reviewer 回复 |
|------|------------|---------------|
| 格式 | 编号逐点 `1) 2) 3)` | Comment/Response 分隔 |
| 篇幅 | 3-5 条 | 5-15 条（每 Reviewer） |
| 分隔符 | 无特殊分隔符 | `\mySep` |
| 换页 | 不单独换页 | 每个 Reviewer 换页 |
| 结尾 | 简短致谢 + 签名 | `\bigskip` + 致谢段 + `\emph{作者}` |
| 评论引用 | 直接回应（不引用原文） | `\emph{}` 引用原文 |
