# LaTeX 格式规范

> Response Letter 的 LaTeX 格式必须精确统一。以下规范基于语料中两份 TWC Response 的实际代码提炼。

## 文档预设

### 标准 preamble（与语料一致）

```latex
% 语料中两份 TWC Response 均使用 article 类（非 IEEEtran）
\documentclass[onecolumn,letterpaper,11pt]{article}
% 或（部分期刊接受）：\documentclass[journal]{IEEEtran}

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
\usepackage{cite}      % 可选：引用排序
\usepackage{citesort}  % 可选：引用排序（语料使用）
```

> **注意**：Response Letter 通常是独立文档（非论文正文），因此多用 `article` 类。如期刊有特殊要求，可改用 `IEEEtran`。

### 自定义命令（必须包含）

```latex
\newcommand{\mySep}{\vspace{8pt}}
```

**推荐添加**（语料实测：Response-TGCN-RP 项目使用）：

```latex
% 蓝色斜体摘录宏——比纯 \textcolor 更醒目
\newcommand{\RevisedExcerpt}[1]{\textit{\textcolor[rgb]{0.00,0.00,1.00}{#1}}}

% 使用示例
\begin{quote}
\underline{Location:}\\
\RevisedExcerpt{[revised manuscript text]}
\end{quote}
```

语料中还使用了以下自定义环境（按需引入）：

```latex
% 正文中的高亮宏（定义在论文 preamble，非 Response 中）
% \newcommand{\textadd}[1]{\textcolor{blue}{#1}}  % 蓝色高亮
% \newcommand{\textdelete}[1]{\textcolor{red}{#1}}  % 红色删除线

% 用于引理/定理框（如需展示数学证明）
% \newenvironment{lemmabox}{\begin{framed}}{\end{framed}}
```

` \mySep` 是 Response 中最核心的分隔符，等同于 `\vspace{8pt}`，用于：
- 每条评论之间
- Comment 与 Response 之间

## 格式元素详解

### 1. 评论编号与引用

```latex
\mySep
\noindent \textsf{\textbf{Comment N:}}
\noindent \emph{[审稿人原文逐字引用]}
```

| 元素 | LaTeX | 说明 |
|------|-------|------|
| 编号标题 | `\textsf{\textbf{Comment N:}}` | 无衬线 + 粗体 |
| 审稿人原话 | `\emph{[原文]}` | 斜体，逐字引用 |
| 分隔符 | `\mySep` | 评论前使用 |

**⚠ 重要**：审稿人原文必须**逐字引用**，不可改写或缩写。保留原始编号（如 "(a)"、"(i)"）、措辞和标点。

### 2. 回复标识

```latex
\mySep
\noindent \textsf{{\textbf{Response:}}}
```

**⚠ 注意**：Response 标识使用**双重花括号** `\textsf{{\textbf{Response:}}}`。

### 3. 修改高亮（蓝色）

```latex
\textcolor[rgb]{0.00,0.00,1.00}{[修改后的文本]}
```

**RGB 值固定为 `(0.00, 0.00, 1.00)`**，即纯蓝色。不可使用其他颜色或 RGB 值。

**使用场景**：
- ✅ 正文中已修改的文本
- ✅ Response 中引用的修改内容
- ✅ 新增图表的 caption
- ❌ 不可用于澄清型回复（无正文修改时）
- ❌ 不可用于拒绝型回复的正文（未修改时）

### 4. 修改位置标注

```latex
\underline{[精确位置]:}
```

**格式**：`\underline{}` 包裹位置描述，末尾加冒号。

**位置描述必须精确到**：
- 小节编号（Section III-B）
- 段落序号（first/second paragraph）
- 元素编号（Eq.~(3), Fig.~5, Table~I, Theorem 2）

**语料中的标准格式**：
```
First paragraph of ``Motivation and Novelty'' in Section I-A
Second sentence of the first paragraph of Section IV-B
Caption of Fig.~8 in ``Secrecy System Throughput'' in Section IV
After the ipSIC SOP expression in Section III
```

### 5. Quote 块（修改展示）

```latex
\begin{quote}
\underline{[位置]:}\\
\textcolor[rgb]{0.00,0.00,1.00}{[完整修改文本]}
\end{quote}
```

**规则**：
- 每个修改一个 quote 块
- quote 块内必须包含：位置标注 + 蓝色高亮文本
- 位置标注后用 `\\` 换行

### 6. 图表插入

#### 新增图表（Response 中）

```latex
\begin{figure}[t!]
    \begin{center}
        \includegraphics[width=3.48in,height=2.8in]{[filename].eps}
        \caption*{\textcolor[rgb]{0.00,0.00,1.00}{Fig.~N: [caption text]}}
        \label{fig:new}
    \end{center}
\end{figure}
```

**关键区别**：
| 元素 | 正文中 | Response 中 |
|------|--------|------------|
| 图表标题 | `\caption{}` | `\caption*{}` |
| caption 文本 | 正常颜色 | 蓝色高亮 |
| 编号 | 自动编号 | 字面编号（Fig.~N） |
| 引用方式 | `\ref{fig:label}` | 字面引用（Fig.~5） |

#### 表格插入

```latex
To provide the requested comparison details, we have added the
following table in Section IV.

\begin{table}[t!]
\centering
\caption{\textcolor[rgb]{0.00,0.00,1.00}{TABLE III: [新增表格标题]}}
\label{tab:new}
\begin{tabular}{lcc}
\hline
\textbf{Parameter} & \textbf{Value 1} & \textbf{Value 2} \\
\hline
[数据]
\hline
\end{tabular}
\end{table}
```

### 7. 参考文献局部引用

当需要引用文献来支撑回应时：

```latex
\begin{quote}
{\footnotesize
[X] A. Author, B. Author, and C. Author, ``Title of the paper,''
\emph{IEEE Trans. Wireless Commun.}, vol. XX, no. YY,
pp. ZZ--WW, Mon. Year.}
\end{quote}
```

**注意**：
- 使用 `{\footnotesize ...}` 缩小字号（外层花括号为分组，非必须双花括号）
- 文献格式遵循 IEEE 标准
- 局部文献仅在该 Comment 末尾出现

### 8. 分隔与换页

| 元素 | LaTeX | 用途 |
|------|-------|------|
| 条间分隔 | `\mySep` | 同一 Reviewer 内各条评论之间 |
| Reviewer 间分隔 | `\clearpage` 或 `\newpage` | 不同 Reviewer 之间换页 |
| 段首间距 | `\vspace{8pt}` | Reviewer 段头后 |

### 9. Reviewer 段尾格式（语料实测）

语料中不使用 `---End of Response to Reviewer [N]---` 居中标记格式。实际使用的段尾为：

```latex
\bigskip

\noindent We sincerely thank the Reviewer for the insightful
comments, which have helped us to improve the quality of this
manuscript.

\vspace{8pt}

\noindent\textit{[Author List]}
```

> **注**：简化版 `---End of Response to Reviewer [N]---` 仍可作为通用替代，但语料中未出现此格式。

### 10. 列表格式

当 Response 中需要列举多项内容时：

#### Editor 回复（编号列表）
```latex
1) [回应点 1]
2) [回应点 2]
3) [回应点 3]
```

#### Reviewer 回复（引用列表或文字描述）
```latex
% 在 Response 正文中直接用文字描述，不使用 itemize/enumerate
We have addressed each issue as follows: [描述修改 A], [描述修改 B],
and [描述修改 C].
```

## 常见格式错误

| 错误 | 正确写法 | 说明 |
|------|----------|------|
| `\textcolor{blue}{...}` | `\textcolor[rgb]{0.00,0.00,1.00}{...}` | 必须用 RGB 值 |
| `\caption{...}` | `\caption*{...}` | Response 中用无编号版本 |
| `\ref{fig:label}` | `Fig.~5` | Response 中用字面编号 |
| `\textbf{Response:}` | `\textsf{{\textbf{Response:}}}` | 必须无衬线 + 双花括号 |
| `Comment N:`（无格式） | `\textsf{\textbf{Comment N:}}` | 必须无衬线 + 粗体 |
| 蓝色高亮片段 | 蓝色高亮完整句子 | 不可只高亮单词 |
| 无位置标注 | `\underline{[位置]:}` | 每个修改必须标注位置 |
