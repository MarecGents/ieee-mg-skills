好的，我将为你撰写一份详尽的 **SKILL 制作流程 Prompt**，用于指挥 AI Agent + 大模型 API 执行整套写作指南和写作 SKILL 的蒸馏与生成任务。这份 Prompt 包含了完整的步骤、输入输出规范、分析维度、约束模板以及迭代验证机制，确保最终产出的指南严谨、贴近原始论文风格，并可直接作为可复用的 SKILL 体系使用。

---

```markdown
# 写作指南与 SKILL 蒸馏制作流程 Prompt

## 角色与目标
你是一名 **学术写作风格分析专家** 和 **AI 技能工程师**。  
你的任务是：基于已整理好的 **21 篇通信领域顶级会议/期刊论文** 的章节语料（已按结构拆分为 Abstract、Introduction、Motivation & Contribution、Numerical Result、Conclusion 五个独立文件），**深度蒸馏** 出每个章节的 **写作风格特征**、**固定结构模式**、**常用句式库**、**逻辑连接方式**，并最终形成一套 **分章节的写作规范指南（Guidelines）** 以及 **一个可执行的 AI 写作 SKILL**（即一个结构化的指令集，可被大模型直接调用以生成符合该风格的新论文草稿）。

## 输入语料说明
你将会获得以下五个文件，它们分别包含所有论文的对应章节内容（按时间倒序排列，即最新论文在最前）：
- `Abstract.md`      —— 21 篇摘要
- `Introduction.md`  —— 21 篇引言（含各子节）
- `Motivation and Contribution.md` —— 20 篇动机与贡献部分（其中一篇可能空白，可忽略）
- `Numerical Result.md` —— 21 篇数值/仿真结果
- `Conclusion.md`    —— 21 篇结论

**要求**：你不得修改原始文本，但可以对其进行分词、标注、频率统计、模式匹配等计算性分析。

---

## 总体流程（阶段划分）

### 阶段 0：环境准备与语料加载
- 确认所有文件已加载到工作内存。
- 为每个章节建立独立的语料库，记录每篇论文的标题、发表年份（隐含顺序，用于判断风格演变）、字数、段落数、句子数等基本统计信息。
- 输出一份 `语料概览报告`，包含各章节的总字数、平均每篇字数、最长/最短论文等。

### 阶段 1：全局风格特征提取（跨章节通用特征）
在分章节深入之前，先提取整个论文集共有的**整体风格倾向**，包括：
- **学术正式度**：使用正式词汇、避免口语化；
- **客观性**：少用第一人称，多用被动语态和“It is shown that...”；
- **句式复杂度**：平均句长、从句使用频率（which, that, although, while 等）；
- **词汇偏好**：高频动词（如 "demonstrate", "investigate", "evaluate"）、高频形容词（如 "superior", "significant", "novel"）；
- **逻辑连接词**：因果（therefore, due to）、对比（whereas, while）、递进（furthermore, moreover）、转折（however, nevertheless）的使用模式；
- **时态分布**：摘要和引言多用现在时和现在完成时，数值结果用过去时，结论用现在时或情态动词。

**输出**：`全局风格画像.md`，包含上述维度的定量描述（如“平均句长 18.5 词，被动语态占比 43%”），并总结该团队的写作“指纹”。

### 阶段 2：分章节深度结构分析与模板抽取
针对每个章节，执行以下细粒度分析：

#### 2.1 Abstract（摘要）
- **结构模板**：识别标准的“背景句 → 问题句 → 方法句 → 结果句 → 意义句”模式。统计各要素出现的顺序和缺失情况。
- **常用句式库**：提取高频开头（如 "In this paper, we..."）、高频结果表达（"Numerical results show that..."）、高频意义表达（"... which highlights..."）。
- **长度约束**：平均句数、总字数范围。

#### 2.2 Introduction（引言）
- **宏观结构**：通常分为 `大背景 -> 技术1综述 -> 技术2综述 -> 研究空白 (Gap) -> 本文动机与贡献 -> 论文组织`。统计各子部分相对长度比例。
- **文献综述写作模式**：识别引用句式（"The authors in [x] investigated..."、"Prior works have demonstrated..."）、归类方式（按研究主题分块）、转折方式（"However, ..."、"To the best of our knowledge, ..."）。
- **研究空白声明**：典型句式（"While ... has been studied, the integration of ... remains unexplored"）。
- **贡献列表演示**：几乎每篇都以 `"The main contributions of this paper can be summarized as follows:"` 开头，并以编号列表（1), 2), ...）呈现，每点通常包含“提出”、“推导”、“优化”、“验证”四类动作之一。

#### 2.3 Motivation and Contribution（动机与贡献）
- **动机部分**：通常以几个尖锐问题开头（"Will ... ?"），然后逐点解释，引出解决方案。
- **贡献部分**：与引言中的贡献列表高度重叠，但此处更详细，有时会独立成节。提取其表达方式（"We propose ...", "We derive ...", "We confirm that ..."）。
- **对比表**：部分论文包含一个对比表格（Table I），总结与现有工作的差异，可作为特色元素。

#### 2.4 Numerical Result（仿真结果）
- **结构**：通常以 `"In this section, numerical results are presented to verify..."` 开头，然后介绍参数设置（表），再按子小节展示不同场景下的图表。
- **子场景划分**：常见为 "A. Outage Probability", "B. Ergodic Rate", "C. System Throughput" 等，每个子场景包含一幅图加分析。
- **图表引用句型**："Fig. X plots ... versus ...", "It is observed from Fig. X that ..."。
- **分析模式**：先描述趋势（"increases/decreases"），再解释原因（"This is because..."），再对比不同曲线或参数（"Another observation is ..."）。
- **常用评价词**："superior", "inferior", "converges to an error floor", "matches perfectly", "validates the accuracy"。

#### 2.5 Conclusion（结论）
- **结构**：通常为一段或两段，开头 "In this paper, we have investigated ..." 总结核心工作，然后回顾主要发现，最后提及未来工作（"A promising future research direction is ..."）。
- **时态**：现在完成时（"have derived"）和一般现在时（"is superior"）混用。
- **长度**：相对简短，约 200-400 词。

**输出**：为每个章节生成一份 `[Chapter]_Structural_Template.md`，包含：
- 必选结构模块（有序）
- 可选模块
- 典型句式模板（带槽位，如 `[We propose a/an] [system] [to achieve] [goal]`）
- 逻辑连接词推荐列表
- 常见错误或应避免的冗余表达

### 阶段 3：约束规范抽取（形成写作指南）
基于阶段 2 的模板，提炼出 **硬性约束（必须遵守）** 和 **软性建议（最好遵守）**。

- **硬性约束**：例如，每篇引言必须有“Motivations and Contributions”小节；贡献必须用编号列表；摘要必须包含至少一个数值结果句；仿真结果中每张图必须配一段不少于 4 句的分析。
- **软性建议**：例如，平均句长控制在 15-25 词；被动语态占比不低于 30%；每个段落第一句应为 topic sentence；全文应使用 3-5 次 “It is worth noting that...” 来强调重要点。

**输出**：`Writing_Guidelines.md`，按章节分类列出所有约束，每条注明来源（至少引用 3 篇论文作为实例）。

### 阶段 4：生成可执行的 AI 写作 SKILL
将上述所有分析结果整合为一个结构化的 **SKILL 定义文件**，该文件可直接用于指导大模型生成新论文。SKILL 应包含以下部分：

- **角色设定**：定义 AI 扮演的写作专家角色，具备该团队所有风格特征。
- **全局风格指令**：设置整体语气、时态偏好、连接词使用频率等。
- **分章节写作规则**：为每个章节提供：
  - 写作前检查清单（需包含的元素）
  - 推荐的段落结构（如引言：1背景段落，2技术综述段落，3研究空白，4贡献列表，5组织）
  - 句式模板库（带变量的可复用句子）
  - 常见错误自动纠正规则
- **交互流程**：定义用户与 AI 的交互方式，例如：
  - 用户输入研究主题和核心贡献点，AI 自动生成初稿；
  - 用户指定章节，AI 单独生成该章节内容；
  - 用户提供图表和数据，AI 生成对应的分析段落。
- **示例**：提供使用该 SKILL 生成的一篇完整虚拟论文草稿作为示范。

**输出**：`Academic_Writing_SKILL.yaml` 或 `Academic_Writing_SKILL.md`（包含结构化的指令，方便后续加载到系统提示中）。

### 阶段 5：迭代验证与优化（可选循环）
- 使用生成的 SKILL 指令，由 AI 生成一篇新的论文草稿（例如，虚构一个基于近期研究的场景）。
- 将生成稿与原始语料的风格进行对比（可使用 BLEU、困惑度、结构相似度等指标，或人工评估）。
- 根据偏差反馈调整阶段 2 和阶段 3 的模板与约束，重复阶段 4 更新 SKILL，直至风格匹配度达到满意水平。

---

## 执行细节与指令格式

### 对于每个分析步骤，请按以下格式输出：

```markdown
## 分析步骤： [步骤名称]
### 输入：
- 文件/数据源
### 处理：
- 所用方法（如正则提取、频率统计、手工标注、LLM总结等）
### 输出：
- 文件名和内容概要
### 校验：
- 如何验证结果准确性（例如，抽取 3 篇论文人工核对）
```
---
```

### 工具调用建议
你可以使用以下功能：
- `统计词频`、`平均句长`、`被动语态比例` 等基础 NLP 操作（需自行编码或使用内置库）；
- 对于复杂的模式识别（如贡献点结构），可逐篇阅读并归纳；
- 对于句法模板抽取，可使用正则提取高频固定搭配。

---

## 最终交付物清单

完成所有阶段后，请打包提供以下文件：

1. `语料概览报告.md`
2. `全局风格画像.md`
3. `Abstract_Structural_Template.md`
4. `Introduction_Structural_Template.md`
5. `Motivation_Contribution_Structural_Template.md`
6. `Numerical_Result_Structural_Template.md`
7. `Conclusion_Structural_Template.md`
8. `Writing_Guidelines.md`（分章节约束规范）
9. `Academic_Writing_SKILL.yaml`（可执行的 SKILL 定义）
10. `验证报告.md`（若执行了阶段 5，则包含生成样例与对比结果）

---

## 执行起始指令
现在，请从 **阶段 0** 开始，依次执行上述所有步骤。在每一步完成后，向我报告进度并等待确认（除非我授权自动推进）。最终，请确保所有输出文件结构清晰、内容可复用，便于后续直接导入 AI 写作系统中。

**开始执行。**

```markdown
---

### 说明与使用建议

- 本 Prompt 是 **全流程指挥指令**，可直接提交给具备长上下文和工具调用能力的 AI Agent（如 GPT-4、Claude 3.5 Sonnet 等），它将被理解为一系列需要依次完成的任务。
- 如果你希望自动化执行，可以进一步将此 Prompt 拆分为多个子任务（如先做语料统计，再做风格分析），但一次性提交上述完整 Prompt 也能让 AI 理解全局并分步输出。
- 最终的 SKILL 文件（.yaml 或 .md）可以直接嵌入到你的写作辅助系统中，作为系统提示或规则库，使大模型在生成新论文时自动遵循该团队的风格。

这个流程兼顾了 **归纳（蒸馏）** 与 **演绎（生成指南）**，确保产出的写作知识既是数据驱动的，又是可操作、可验证的。祝你蒸馏成功！
```