# Response LaTeX 模板（v0.0.5 完整版）

> 基于 3 篇语料（TWC u1 + TWC u2 + TGCN-RP）最佳实践整合生成。
> 可直接复制为起点，替换 `[方括号内容]` 即可使用。

## 完整 LaTeX 文档模板

```latex
\documentclass[onecolumn,letterpaper,11pt]{article}
% 注：Response Letter 通常使用 article 类（非 IEEEtran）。
% 如期刊有特殊要求，可改用 \documentclass[journal]{IEEEtran}。

% ─── 基础包（仅加载实际使用的） ───
\usepackage{graphicx,color,xcolor}
\usepackage{amssymb,amsmath,amsthm}
\usepackage{algorithm,algorithmic}
\usepackage{subfigure}
\usepackage{framed,caption}
\usepackage{cite}
\usepackage{placeins,float}
\usepackage{tabularx,colortbl}
\usepackage{url,lscape,multirow}
\usepackage{mathrsfs,epstopdf}
\usepackage{fancyhdr}

% ─── 定理环境 ───
\newtheorem{theorem}{Theorem}
\newtheorem{lemma}{Lemma}
\newtheorem{corollary}{Corollary}
\newtheorem{remark}{Remark}

% ─── Response 专用命令 ───
\newcommand{\mySep}{\vspace{8pt}}
\newcommand{\RevisedExcerpt}[1]{\textit{\textcolor[rgb]{0.00,0.00,1.00}{#1}}}

% ─── 页面设置 ───
\textwidth 15cm
\oddsidemargin 0.46cm

\begin{document}

% ═══════════════════════════════════════════
%  封面页（Cover Letter）
% ═══════════════════════════════════════════

\title{%
    {\bfseries Response to Reviewers' Comments for Manuscript ID [稿件ID]}\\[1.2cm]
    {\Large [论文标题]}\\[1.2cm]
    \normalsize Addressed comments for publication to
    \textsc{[期刊全称]} by\vspace*{0.8cm}
}
[Author List]
\maketitle\thispagestyle{empty}\newpage

\setlength{\parskip}{4ex plus0.5ex minus0.2ex}

\noindent Dear Dr.~[Editor Name] and Reviewers,

We sincerely thank you and the Reviewers for the time and effort
invested in reviewing our manuscript [稿件ID]. We have carefully
considered every comment and revised the manuscript accordingly.
All modifications in the revised manuscript are highlighted in
blue.

In this response report, each Reviewer's comments are reproduced
in \emph{italic font} and our responses follow in plain font.
Revised manuscript excerpts are shown in
\emph{\textcolor[rgb]{0.00,0.00,1.00}{blue italics}} with the
revised location underlined.

Yours sincerely,
[Author List]

\setlength{\parskip}{0pt}
\clearpage

% ═══════════════════════════════════════════
%  Response to Editor
% ═══════════════════════════════════════════

\begin{center}
\textbf{\Large{[期刊缩写]\\ID [稿件ID]\\[0.3cm]
[论文标题] \\[0.3cm]
Authors' Response to Editor.R1\\}
}
\vspace{0.3cm}
\emph{[Author List]}
\end{center}

\vspace{8pt}

\noindent We sincerely appreciate the editor allow us to give
more clarifications.

1) [回应第 1 点]

2) [回应第 2 点]

3) [回应第 3 点]

\clearpage

% ═══════════════════════════════════════════
%  Response to Reviewer 1
% ═══════════════════════════════════════════

\begin{center}
\textbf{\Large{[期刊缩写]\\ID [稿件ID]\\[0.3cm]
[论文标题] \\[0.3cm]
Authors' Response to Reviewer 1.R1\\}
}
\vspace{0.3cm}
\emph{[Author List]}
\end{center}

\vspace{8pt}

\noindent We sincerely thank Reviewer~1 for the [positive
assessment and the constructive suggestions]. We have revised the
manuscript in line with all comments, which has improved both
the contribution clarity and the presentation.

% ─── Comment 1 ───
\mySep
\noindent \textsf{\textbf{Comment 1:}}
\noindent \emph{[审稿人原文逐字引用]}

\mySep
\noindent \textsf{{\textbf{Response:}}}
[We thank the reviewer for this valuable suggestion.]

[技术回应内容...]

[如有修改：]
To address your [significant] comments, we have revised the
manuscript as follows:

\begin{quote}
\underline{[精确位置]:}\\
\RevisedExcerpt{[完整修改文本]}
\end{quote}

% ─── Comment 2 ───
\mySep
\noindent \textsf{\textbf{Comment 2:}}
\noindent \emph{[审稿人原文逐字引用]}

\mySep
\noindent \textsf{{\textbf{Response:}}}
[技术回应...]

\begin{quote}
\underline{[位置]:}\\
\RevisedExcerpt{[修改文本]}
\end{quote}

% 如有参考文献
{\footnotesize{
\noindent [N] Author, ``Title,'' \emph{Journal}, vol.~X,
pp.~Y, Year.\\
}}

% ─── 更多 Comments ───
% ... 重复上述模式 ...

% ─── Reviewer 1 结束 ───
\bigskip
\noindent We sincerely thank the Reviewer for the insightful
comments, which have helped us to improve the quality of this
manuscript.

\vspace{8pt}
\noindent\emph{[Author List]}

\clearpage

% ═══════════════════════════════════════════
%  Response to Reviewer 2（格式同上）
% ═══════════════════════════════════════════

% ═══════════════════════════════════════════
%  Response to Reviewer N（格式同上）
% ═══════════════════════════════════════════

\end{document}
```

## 各元素速查

| 元素 | LaTeX | 来源语料 |
|------|-------|----------|
| 分隔符 | `\mySep` = `\vspace{8pt}` | 三篇通用 |
| 评论标签 | `\noindent \textsf{\textbf{Comment N:}}` | 三篇通用 |
| 回复标签 | `\noindent \textsf{{\textbf{Response:}}}` | 三篇通用 |
| 评论引用 | `\noindent \emph{[原文]}` | 三篇通用 |
| 蓝色摘录 | `\RevisedExcerpt{...}` 或 `\textcolor[rgb]{0.00,0.00,1.00}{...}` | TGCN 用宏 / TWC 用原始 |
| 位置标注 | `\underline{[位置]:}\\` | 三篇通用 |
| 新图 | `\caption*{\textcolor[rgb]{0.00,0.00,1.00}{Fig.~N: ...}}` | 三篇通用 |
| 参考文献 | `{\footnotesize{[N] Author, ...}}` | 三篇通用 |
| 公式 | `\begin{equation}` 或 `\begin{align}+\tag{N}` | 两种均可用 |
| 段头 | 居中 5 行块（期刊+ID+标题+回复标识+作者） | TGCN 模式 |
| 段尾 | `\bigskip` + 致谢 + `\emph{作者}` | TWC 模式 |
| 换页 | `\clearpage` | 三篇通用 |
