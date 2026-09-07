# Response 撰写核心原则

> **v0.0.5**：基于课题组 3 篇论文 Response Letter（TWC×2 + TGCN×1，共 73 条评审意见）蒸馏提炼。
> 语句模板库扩充至 80+ 条（语料实测 + AI 拓展），新增 Response LaTeX 模板、防御型句式库。

## 核心定位

Response Letter 是论文大修阶段与 Editor 和 Reviewer 沟通的核心文档。它的质量直接决定论文能否被接受。本技能的目标是：**逐条、礼貌、专业、可追溯**地回复每一条评审意见。

## 四铁律

### 铁律一：类型不可混淆 + 修改型必须询问

每条评审意见必须先分类再回应：

| 类型 | 判定标准 | 回应策略 | 禁止事项 |
|------|----------|----------|----------|
| **澄清型**（Clarification） | 审稿人误解或要求解释，正文无需修改 | 礼貌感谢 + 清晰解释 + 声明无需修改 | ❌ 不得附蓝色修改摘录 |
| **修改型**（Accept & Revise） | 审稿人指出合理问题，正文已修改 | **必须先询问用户策略** → 确认后撰写 | ❌ 不得在未询问时私自修改 |
| **部分接受型**（Partial Accept） | 多子问题，部分接受部分拒绝 | 逐子问题分别处理（接受的修改、拒绝的说明理由） | ❌ 不可笼统地"全部接受" |
| **拒绝型**（Defense/Rejection） | 审稿人建议不合理或超出范围 | 感谢 + 礼貌说明理由 + 提供证据/引用 | ❌ 不得无理强硬拒绝 |
| **宽泛型**（Broad/Vague） | 评论不指向具体位置（如"grammar needs improvement"） | 道歉 + 逐项拆解每个修正 | ❌ 不可一句话带过 |

**⚠ 修改型强制询问**（grill-me 模式）：对于每条修改型意见，必须逐条询问用户：
- 用户是否有明确的修改方案？
- 如有，是什么？（具体到修改位置和内容）
- 如无，AI 提供 2-3 个候选方案供选择
- **用户确认后才可撰写回应，绝不可私自决断并执行修改**

### 铁律二：修改必须同步

正文修改与 Response 中的蓝色摘录必须逐字一致：
- 正文中用 `\textcolor[rgb]{0.00,0.00,1.00}{蓝色}` 标记修改处
- Response 中用 `\begin{quote}...\underline{[位置]:}\\ \textcolor[rgb]{0.00,0.00,1.00}{蓝色修改}\end{quote}` 引用
- 两者内容**完全相同**

### 铁律三：宽泛评论必须逐项拆解

当审稿人给出"语法有误"、"表述不清晰"等宽泛评论时：
- ❌ **绝不能**写"The manuscript has been thoroughly proofread."一句带过
- ✅ **必须**逐个列出每个修正：每个修正对应正文中的一个具体位置

### 铁律四：先出清单，不直接写 tex

使用本技能时，**禁止直接在原文和 Response tex 中写入**。必须先输出清单文档，经过用户确认后再生成 tex。

### 铁律五：Editor 与 Reviewer 格式严格区分

| 维度 | Editor 回复 | Reviewer 回复 |
|------|------------|---------------|
| 格式 | 编号逐点 `1) 2) 3)...` | Comment/Response 分隔（`\mySep` + `\emph{}` + Response） |
| 评论引用 | 不引用原文（直接回应） | `\emph{}` 逐字引用原文 |
| 篇幅 | 3-5 条，较短 | 5-15 条/Reviewer |
| 换页 | 不单独换页 | 每个 Reviewer `\clearpage` |
| 段尾 | 简短致谢 + 签名 | `\bigskip` + 致谢段 + `\emph{作者}` |

详见 `section-editor-response.md`。

---

## 首句 / 第二句 / 末句写作套路

> 以下套路基于 3 篇语料（73 条评审意见）的统计提取。

### 首句（Response 第一句话）—— ~95% 以感谢开头

| 模式 | 频率 | 语料原文 |
|------|:----:|----------|
| **We appreciate sincerely your...** | 8/73 | `We appreciate sincerely your insightful comments.` |
| **Sincere thanks for seeking/your...** | 9/73 | `Sincere thanks for seeking explicit clarity.` / `Sincere thanks for your significant comments.` |
| **Many thanks for the reviewer's kind...** | 7/73 | `Many thanks for the reviewer's kind comments.` / `...kind clarifications.` / `...kind clarity.` |
| **We much value your quest for explicit clarity.** | 6/73 | 用于澄清型回复 |
| **Thank you for seeking/your/raising...** | 5/73 | `Thank you for seeking further clarifications.` / `Thank you for your insightful comments.` |
| **We sincerely appreciate the editor allow us to give more clarifications.** | 3/73 | 专用于 Editor 回复 |
| **We thank the reviewer for this [X].** | 15/73 | TGCN 语料主模板 |
| **As you kindly suggested, we have...** | 2/73 | 直接行动式开头（仅用于简单修改） |

**首句选择指南**：
- 澄清型 → "Sincere thanks for seeking explicit clarity." 或 "We much value your quest for explicit clarity."
- 修改型 → "Many thanks for the reviewer's kind comments." 或 "We appreciate sincerely your insightful comments."
- 简单修改 → "As you kindly suggested, we have corrected..."

### 第二句 —— 承上启下

| 模式 | 频率 | 适用场景 |
|------|:----:|----------|
| **We would like to clarify that [技术解释].** | 29/73 | 澄清型首选（最高频） |
| **As suggested, we have [修改动作].** | 7/73 | 修改型首选 |
| **We agree with the reviewer that [承认问题].** | 8/73 | 部分接受型 |
| **We acknowledge that [承认局限].** | 3/73 | TGCN 语料特有 |
| **[直接技术解释，无过渡]** | 12/73 | 技术含量高的回应 |
| **We apologize that [错误描述]...** | 7/73 | 语法/拼写修正 |

### 末句（引出 quote 块前的过渡句）

| 模式 | 频率 | 示例 |
|------|:----:|------|
| **To address your [形容词] comments, we have revised the manuscript as follows:** | 35/73 | 最常用 |
| **As suggested, we have revised the manuscript as follows:** | 5/73 | 简洁版 |
| **As you kindly suggested, we have revised/updated...** | 3/73 | 强调审稿人建议 |
| **The relevant revised text is reproduced below...** | 3/73 | 不引出 quote 的直接展示 |

**形容词频率**：significant(17) > helpful(10) > important(9) > insightful(6) > constructive(2) > critical(1) > acute(1) > astute(1) > pivotal(1)

---

## 引用逻辑

### 核心规则：零 `\cite{}` 命令

语料中两份 Response 均**不使用 `\cite{}` 命令**。所有引用采用**纯文本格式**。

### 两种引用格式

| 格式 | 标识 | 来源 | 使用场景 |
|------|------|------|----------|
| **正文已有文献** | `[N]`（数字） | 主论文参考文献列表 | 正文中已引用的文献 |
| **审稿人建议文献** | `[RN]`（R 前缀） | 审稿人推荐的新文献 | 仅在 Response 中引用 |

### 正文已有文献 `[N]` 的使用

在 Response 正文中直接引用：
```latex
as stated in [16], ... / with the help of [56, Eq. (2.76)], ...
applied in many contributions [R3,R4,10,45], ...
```

在末尾插入完整文献块：
```latex
\begin{quote}
{\footnotesize
[16] A.~Author, B.~Author, and C.~Author, ``Title of the paper,''
\emph{IEEE Trans. Wireless Commun.}, vol. XX, no. YY,
pp. ZZ--WW, Mon. Year.}
\end{quote}
```

### 审稿人建议文献 `[RN]` 的使用

审稿人建议引用的新文献使用 `[R]` 前缀标识：

```latex
\begin{quote}
{\footnotesize
[R1] J.~Choi, ``Non-orthogonal multiple access in downlink
systems with successive interference cancellation,''
\emph{IEEE Trans. Wireless Commun.}, vol. XX, no. YY,
pp. ZZ--WW, Mon. Year.}
\end{quote}
```

**⚠ 引用规则**：
- 同一文献可能在不同 Response 中重复出现（语料实测），可复用
- `[RN]` 文献仅出现在 `{\footnotesize{}}` 块中，不在正文文献列表中
- 引用时注意 `[N]` 是文档内编号，不同论文的编号不通用

---

## 蓝色高亮命令规范

### 方式一：原始 `\textcolor`（R1_u1、R1_u2 参考文件使用）

```latex
\textcolor[rgb]{0.00,0.00,1.00}{[修改文本]}
```

### 方式二：`\RevisedExcerpt` 宏（Response-TGCN-RP 实际项目使用）

```latex
% 在 preamble 中定义
\newcommand{\RevisedExcerpt}[1]{\textit{\textcolor[rgb]{0.00,0.00,1.00}{#1}}}

% 使用时
\RevisedExcerpt{[修改文本]}  % 等价于 \textit{\textcolor[rgb]{0.00,0.00,1.00}{...}}
```

**区别**：`\RevisedExcerpt` 额外包裹了 `\textit{}`（斜体），使得摘录在视觉上更醒目。两种方式 RGB 值完全相同，**可任选其一**。

### 使用场景统计（3 篇语料合并）

| 场景 | 占比 | 说明 |
|------|:----:|------|
| `\begin{quote}` 内的修改文本 | ~70% | Response 中引用的正文修改 |
| `\caption*{}` 内的新图标题 | ~20% | Response 中插入的新图 |
| Cover Letter 中的格式说明 | ~5% | "revised texts highlighted in blue" |
| 表格单元格 | ~5% | 极少，仅用于新增表格内容 |

### 关键规则

- **100% 的修改型 Response 都使用蓝色高亮**——只要正文有修改，Response 中必有 `\textcolor`
- **澄清型 Response 不使用蓝色高亮**——无正文修改时不出现 `\textcolor`

---

## Response 长度模式

| 指标 | 数值 |
|------|------|
| 总 Response 块数 | 73（TWC u1: 29 + TWC u2: 25 + TGCN-RP: 19） |
| 含 quote 块的 Response | 68/73（93.2%） |
| 平均 quote 块数/Response | 2.0 |
| 澄清型平均句数 | 1-2 句 |
| 修改型平均句数 | 5-11 句（1 个 quote） / 10-29 句（2+ 个 quote） |

---

## 正文高亮宏 vs Response 高亮命令（重要区别）

> 语料实测发现：正文和 Response 使用**不同的高亮语法**，但功能等价。

### 正文中的高亮宏（用户编辑论文时使用）

```latex
% 定义在论文 preamble 中
\newcommand{\textdelete}[1]{\textcolor{red}{#1}}  % 删除文本 — 红色
\newcommand{\textadd}[1]{\textcolor{blue}{#1}}    % 新增文本 — 蓝色
```

- 正文使用 `\textadd{...}` 包裹所有新增/修改的文本（语料中 34 处）
- `\textdelete{...}` 定义了但仅使用 1 次——实际删除操作通常用 `%` 注释掉
- 正文不使用 `\textcolor[rgb]{0.00,0.00,1.00}{}` 直接写法

### Response 中的高亮命令（撰写回复时使用）

```latex
% Response 文档中直接使用原始 \textcolor
\textcolor[rgb]{0.00,0.00,1.00}{[修改文本]}
```

- Response 使用原始 `\textcolor[rgb]{0.00,0.00,1.00}{}` 而非 `\textadd{}`
- 语料中 74 处全部使用此格式，零例外
- Response 中**不使用** `\textdelete{}`——回复中不展示删除的文本

### 公式在 Response 中的特殊处理

```latex
% 正文中使用 \eqref{label} 或 \ref{label}
Eq.~\eqref{eq:main} ... Fig.~\ref{fig:sop}

% Response 中转换为字面编号
Eq.~(10) ... Fig.~3
```

- Response 中**不使用** `\ref{}` 或 `\eqref{}`，全部转为字面编号
- 公式展示可用两种格式：
  - `\begin{equation}...\end{equation}`（简单单行公式）
  - `\begin{align}...\tag{N}...\end{align}`（多行公式或需手动编号时）
- 一个 Response quote 块中可包含多个公式

### 交叉验证规则

正文中的每个 `\textadd{...}` 块必须在 Response 中有对应的蓝色摘录。语料实测：
- 正文 55 个 `\textadd` 块 ↔ Response 49 个摘录（部分简单修改不需在 Response 中展示）
- 两者之间必须**逐字一致**——包括公式符号、变量名、缩写全称

**常见不一致陷阱**：
1. 公式符号不一致（如 `$T_{\mathrm{system}}^{\varsigma}$` vs `$T_{\mathrm{system}}(R)$`）
2. 术语缩写不一致（如 "EE" vs "secrecy energy efficiency"——正文用全称时 Response 也必须用全称）
3. 图表编号格式不一致（正文 `Fig.~\ref{label}` vs Response `Fig.~3`——这是正确的差异，不是错误）

---

## 写作风格要求

### 语气
- **全程礼貌**：每条回复以感谢开头（96.3% 率）
- **专业自信**：对拒绝型意见，用事实和引用支撑立场
- **清晰简洁**：不写无关内容，不重复审稿意见

### 语言
- 全文使用**学术正式英语**
- 与 `ieee-mg-share/style-profile.md` 全局风格画像保持一致
- 术语使用与 `ieee-mg-share/terminology.md` 一致

### 篇幅
- 每条回复长度应与审稿意见的复杂度匹配
- 总篇幅：通常 8-15 页（取决于审稿意见数量和复杂度）

---

## 与共享层的衔接

| 场景 | 引用来源 | 用途 |
|------|----------|------|
| 术语一致性 | `terminology.md` | 确保 Response 中使用的术语与正文一致 |
| 表达选择 | `expression-bank.md` | 选择回应句式 |
| 逻辑连接 | `logic-connectors.md` | 澄清/转折/递进的连接词 |
| 风格一致 | `style-profile.md` | Response 语言风格与论文正文保持统一 |
| 量化参考 | `quantitative-baseline.md` | 引用论文中具体数值时确保准确 |
| 错误避免 | `common-errors.md` | 避免 Response 语言中的常见错误 |
