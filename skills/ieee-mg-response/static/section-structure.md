# Response 固定结构模板

> 基于 `Latex_response_twc_R1_u1/Response_STAR_IRS_NOMA.tex` 和 `Latex_response_twc_R1_u2/Response_IRS_NOMA.tex` 提炼。

## 整体文档结构

一个完整的 Response Letter 文档包含以下部分，按顺序排列：

```
1. Cover Letter（致 Editor 的封面信）
2. Response to Editor（编号逐点格式）
3. Response to Reviewer 1（Comment/Response 逐条格式）
4. Response to Reviewer 2（Comment/Response 逐条格式）
5. Response to Reviewer N（Comment/Response 逐条格式）
```

每部分之间用 `\clearpage` 或 `\newpage` 分隔。

## LaTeX 文档模板

```latex
\documentclass[journal]{IEEEtran}
% 或 \documentclass[onecolumn,letterpaper,11pt]{article}（如参考文件格式）

\usepackage{graphicx}
\usepackage{color}
\usepackage{xcolor}
\usepackage{amssymb}
\usepackage{amsmath}
\usepackage{algorithm}
\usepackage{algorithmic}
\usepackage{subfigure}
\usepackage{framed}
\usepackage{caption}
\usepackage{amsthm}

% 关键自定义命令
\newcommand{\mySep}{\vspace{8pt}}

\begin{document}

% --- Cover Letter ---
Dear Prof. [Editor Name],

We thank the Editor and the Reviewers for their valuable and
constructive comments, which have helped us improve the quality
of this manuscript significantly. We have carefully considered
all the comments and revised the manuscript accordingly.

In this response, the reviewer comments are indicated in
\emph{italic}, and the revised texts in the manuscript are
highlighted in \textcolor[rgb]{0.00,0.00,1.00}{blue}.

Sincerely,
[Author List]

% --- Response to Editor ---
\begin{center}
{\Large \textbf{Response to Editor}}
\end{center}

\vspace{8pt}

% Editor 采用编号格式（详见 section-editor-response.md）

% --- Response to Reviewer 1 ---
\clearpage
\begin{center}
{\Large \textbf{Response to Reviewer 1}}
\end{center}

\vspace{8pt}

% Reviewer 采用 Comment/Response 格式

\mySep
\noindent \textsf{\textbf{Comment 1:}}
\noindent \emph{[审稿人原话]}

\mySep
\noindent \textsf{{\textbf{Response:}}}
[回复内容]

% ... 更多评论 ...

\bigskip
\noindent We sincerely thank the Reviewer for the insightful
comments, which have helped us to improve the quality of this
manuscript.
\vspace{8pt}
\noindent\emph{[Author List]}

% ... Reviewer 2, 3 ...

\end{document}
```

## Cover Letter 标准模板

### 格式 A：Dear Prof. 段落式（R1_u1、R1_u2 参考文件使用）
```latex
Dear Prof. [Editor Last Name],

We thank the Editor and the Reviewers for their valuable and
constructive comments. We have carefully considered all the
comments and revised the manuscript accordingly. Our
point-by-point responses to each comment are given below. In the
response, the reviewer comments are shown in \emph{italic}, and
the revised texts in the manuscript are highlighted in
\textcolor[rgb]{0.00,0.00,1.00}{blue}.

Sincerely,
[Full Author List]
```

### 格式 B：`\title+\maketitle` 标题页式（Response-TGCN-RP 实际项目使用）
```latex
\title{
    {\bfseries Response to Reviewers' Comments for Manuscript ID [稿件ID]}\\\vspace*{1.2cm}
    {\Large [论文标题]}\\\vspace*{1.2cm}
    \normalsize Addressed comments for publication to \textsc{[期刊全名]} by\vspace*{0.8cm}
}
[Author Line]
\maketitle\thispagestyle{empty}\newpage

\noindent Dear Dr.~[Editor Name] and Reviewers,

We sincerely thank you and the Reviewers for the time and effort
invested in reviewing our manuscript [稿件ID]. We have carefully
considered every comment and revised the manuscript accordingly.
All modifications in the revised manuscript are highlighted in
blue.

[格式说明段落]

Yours sincerely,
[Full Author List]
```

> **选择建议**：格式 B 更正式，包含稿件 ID 和期刊名，适合投稿系统要求的 Response Letter 格式。

### 格式说明段（可选，语料中有使用）
```latex
The format of this response document is as follows: the reviewer
comments are shown in \emph{italic}, the responses are given in
normal font, and the revised texts in the manuscript are
highlighted in \textcolor[rgb]{0.00,0.00,1.00}{blue}.
```

## Reviewer 段落标准头尾

### 段头（正式格式，语料实测）

语料中 Reviewer 段落的开头采用**居中块**，包含期刊名、稿件 ID、论文标题、回复标识（含轮次后缀）和作者列表：

```latex
\begin{center}
\textbf{\Large{IEEE Transactions on [Journal Name]\\
ID [稿件ID]\\[0.3cm]
[论文标题] \\[0.3cm]
Authors' Response to Reviewer [N].R[M]\\}
}
\vspace{0.3cm}
\emph{[Author List]}
\end{center}
```

> **轮次后缀说明**：`.R1` 表示第一轮大修回复，`.R2` 表示第二轮，以此类推。Editor 段头使用 `Authors' Response to Editor.R[M]`。

> **TWC 简化版**（当不需要展示稿件信息时）：
> ```latex
> \begin{center}
> {\Large \textbf{Response to Reviewer [N]}}
> \end{center}
> ```

### 段尾（语料实测格式）

语料中的段尾不使用 `---End of Response---` 格式，而是采用**致谢段 + 斜体作者签名**：

```latex
\bigskip

\noindent We sincerely thank the Reviewer for the insightful
comments, which have helped us to improve the quality of this
manuscript.

\vspace{8pt}

\noindent\textit{[Author List]}

[可选：The first author conducted this work while at [Affiliation].]
```

## Comment/Response 分隔格式（Reviewer 标准）

每条评论严格遵循以下格式：

```latex
\mySep
\noindent \textsf{\textbf{Comment N:}}
\noindent \emph{[审稿人原话——逐字引用，保留原始编号和措辞]}

\mySep
\noindent \textsf{{\textbf{Response:}}}
[礼貌感谢 + 具体回应]

[如需展示修改：]
\begin{quote}
\underline{[精确位置]:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[完整修改文本]}
\end{quote}

[如需插入图表：直接插入 figure/table 环境]
[如需引用文献：插入局部文献块]
```

## 关键格式细节

| 元素 | 写法 | 注意事项 |
|------|------|----------|
| 评论编号 | `\textsf{\textbf{Comment N:}}` | N 为该 Reviewer 内的连续编号（1, 2, 3...） |
| 回复标识 | `\textsf{{\textbf{Response:}}}` | 注意双重花括号 |
| 分隔符 | `\mySep` | 每条评论前使用，等同 `\vspace{8pt}` |
| 评论引用 | `\emph{}` | 审稿人原话必须斜体 |
| 修改高亮 | `\textcolor[rgb]{0.00,0.00,1.00}{}` | 仅蓝色，RGB 值固定 |
| 位置标注 | `\underline{[位置]:}` | 精确到小节/段落/图表，冒号后换行 |
| Reviewer 间分隔 | `\clearpage` | 每个 Reviewer 独占新页 |
