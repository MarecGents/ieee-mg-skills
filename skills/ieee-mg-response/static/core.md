# Response 撰写核心原则

> **v0.1.2**：基于课题组 3 篇论文 Response Letter（TWC×2 + TGCN×1，共 73 条评审意见）蒸馏提炼。
> 语句模板库扩充至 80+ 条（语料实测 + AI 拓展），新增 Response LaTeX 模板、防御型句式库。

## 核心定位

Response Letter 是论文大修阶段与 Editor 和 Reviewer 沟通的核心文档。它的质量直接决定论文能否被接受。本技能的目标是：**逐条、礼貌、专业、可追溯**地回复每一条评审意见。

## 七铁律

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
- 正文中用 `\textadd{...}` 标记修改处（论文 preamble 定义的高亮宏）
- Response 中用 `\begin{quote}...\underline{[位置]:}\\ \RevisedExcerpt{...}\end{quote}` 引用
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

### 铁律六：高亮粒度三原则（语料实测反复纠正）

| 修改对象 | 高亮粒度 | 反例（禁止） |
|----------|----------|--------------|
| **段落中的局部修改** | 整句话 或 整个自然段（一个 `\textadd{}`） | 一句话内出现 5 处分散的 `\textadd{}` |
| **公式中的局部修改** | 整个公式（一个 `\textadd{}` 包裹全式） | 只高亮公式中变化的那个变量（如仅 `\xi_e^r`） |
| **表格中的局部修改** | 单元格所在行（该行整体）或新增/修改的单元格 | 只高亮单元格中的一个符号 |

**判定方法**：修改一处 → 向上找到"可独立阅读的最小完整单元"（句子/公式/表格行），高亮该单元整体。

### 铁律七：替换 = 修改高亮，纯删除 = 叙述说明

| 情形 | 判定 | Response 处理 |
|------|------|---------------|
| 原文本被新文本**替换**（同位置有更正/延伸） | **修改型** | 新文本蓝色高亮 + 摘录展示新文本 |
| 原文本被删除且该位置**无替代内容**（信息消失） | **删除型** | Response 叙述文字中直接说明，**不展示删除高亮** |

**删除说明的三种写法**（语料实测）：
1. **只说明不展示**（推荐）：`Accordingly, the sentence ``[被删原文]'' has been removed from [位置], since [删除理由].`
2. **交叉引用他处**（当删除是其他 comment 的连带结果）：`...as its content is already covered by the revised statement under Reviewer~N Comment~M.`
3. **源码保留备查**：用 `%` 逐行注释掉，不进入编译输出。

**禁止**：❌ 对被删除内容使用蓝色高亮。❌ 只用一句"we have removed it"而不引用原文。

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

**⚠ [RN] 编号管理规程（避免语料中的教训）**：
1. **全局连续编号**：同一份 Response 文档中 [R1]、[R2]、[R3]... 严格递增，不复用
2. **每个编号只定义一次**：在首次引用处附近插入文献块；后续引用直接写 `[RN]`，不再重复列条目
3. **引用即定义**：凡是文档中出现的 `[RN]`，必须在某处有对应的文献块，不可有孤儿引用
4. **编号与正文 [N] 混排时**：写作 `[R3,R4,10,45]`（R 前缀在前，正文编号在后）

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

**区别**：`\RevisedExcerpt` 额外包裹了 `\textit{}`（斜体），使得摘录在视觉上更醒目。

**选择规则**（按内容类型，不可混用）：

| 摘录内容 | 命令 | 原因 |
|----------|------|------|
| 文字（句子/段落） | `\RevisedExcerpt{}` | 斜体增强辨识度 |
| 公式（align/行内） | `\textcolor[rgb]{0.00,0.00,1.00}{}` | `\textit` 会破坏数学排版 |
| 表格单元格 / caption | `\textcolor[rgb]{0.00,0.00,1.00}{}` | 同上 |

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
- **公式格式（语料零例外）**：一律使用 `\begin{align}...\tag{N}...\end{align}`
  - 单行公式：`\begin{align} 公式 ,\tag{N} \end{align}`
  - 多行公式：中间行 `\nonumber`，最后一行 `\tag{N}`
  - **公式展示不使用** `\begin{equation}`、也不放进 `\begin{center}`（`center` 仅用于段头和 figure 内部）
  - 编号一律 `\tag{}` 手动指定（与正文实际编号对应）
- 一个 Response quote 块中可包含多个公式

### 交叉验证规则

正文中的每个 `\textadd{...}` 块应在 Response 中有对应的蓝色摘录；但不能简单按数量配平——两者数量不等是**正常现象**：

| 差异方向 | 原因 | 是否合法 |
|----------|------|:--------:|
| 正文高亮 > Response 摘录 | 简单修改（个别符号/词）未在 Response 中展示 | ✅ |
| Response 摘录 > 正文高亮 | ① 同一高亮在多个 Rx-Cx 下重复摘录 ② 一个高亮的多个部分分列为多个摘录块 | ✅ |

**唯一判据**：逐块内容比对——**每一个正文高亮必须在 Response 找到内容一致的摘录；每一个 Response 摘录必须在正文找到对应的高亮文本**（除删除说明外）。

**常见不一致陷阱**：
1. 公式符号不一致（如 `$T_{\mathrm{system}}^{\varsigma}$` vs `$T_{\mathrm{system}}(R)$`）
2. 术语缩写不一致（如 "EE" vs "secrecy energy efficiency"——正文用全称时 Response 也必须用全称）
3. 图表编号格式不一致（正文 `Fig.~\ref{label}` vs Response `Fig.~3`——这是正确的差异，不是错误）

---

## 写作风格要求

### 语气
- **全程礼貌**：每条回复以感谢开头（约 95% 率）
- **专业自信**：对拒绝型意见，用事实和引用支撑立场
- **清晰简洁**：不写无关内容，不重复审稿意见

### 语言
- 全文使用**学术正式英语**
- 与 `ieee-mg-share/style-profile.md` 全局风格画像保持一致
- 术语使用与 `ieee-mg-share/terminology.md` 一致

### 篇幅
- 每条回复长度应与审稿意见的复杂度匹配
- 总篇幅：通常 8-15 页（取决于审稿意见数量和复杂度）

### 正文修改文本的自然度约束（⚠ 语料实测反复纠正）

Response 中展示的正文修改，**首先服务于论文读者，其次才是审稿人**。写作时必须通过"读者检验"：

| 检验项 | 通过标准 | 反例（用户驳回的写法） |
|--------|----------|------------------------|
| **前文呼应** | 新增句引用的概念在前文已出现 | 突然解释"stochastic geometry 在此指..."（前文从未提及该术语需要澄清） |
| **后文承接** | 新增句提到的内容后文有对应展开 | 声明"某分析留待未来工作"，而后文无任何铺垫 |
| **无辩解语气** | 用陈述句说明做法 | "only for the completeness of the signal model" / "rather than the cascaded-only form" |
| **无对抗性** | 与其他 comment 的修改不相矛盾 | R3-C4 声明"级联主导"而 R2-C6 声明"直射+级联" |

**自检问句**：把这段修改读给一个没看过审稿意见的同行听，他会不会问"为什么突然说这个？"——如果会，就必须改写。

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
