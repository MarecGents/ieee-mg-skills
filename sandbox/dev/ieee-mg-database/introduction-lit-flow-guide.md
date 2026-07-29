# Introduction 文献综述段落：过渡多样化写作指导

> 基于 LaTeX_PASS_NOMA_PLS.tex Introduction 第二段润色实践凝练
>
> 适用场景：Introduction 中引用已有工作的文献综述段落（Literature Review Layer）
> 核心目标：消除"单词过渡词综合征"，让文献综述读起来自然流畅而非清单罗列

---

## 一、问题诊断：单词过渡词综合征

### 症状

段落中连续多句以**单一的单词过渡词**开头，形成机械的"首先…其次…再次…"模式：

```
Meanwhile, ... Furthermore, ... Additionally, ... Moreover, ...
Notably, ... In addition, ... Beyond ...
```

### 原文实例（修改前）

> **Meanwhile**, in \cite{Xu2026LoSBlockage}, the authors investigated... **Furthermore**, the authors of \cite{Li2026PASSSpatial} proposed... **Additionally**, a dual-scale antenna deployment framework... was developed... **Moreover**, a hybrid PASS architecture... was introduced... **Notably**, the waveguide power loss was explicitly considered... **In addition**, a downlink communication system... was studied... **Beyond** pure communication, the authors... proposed...

10 句中有 8 句以单词过渡词开头，段落读感 = **清单**。

### 病因

- 作者将"过渡 = 必须加过渡词"误解为"每句都需要"
- 所有过渡词都是递进/补充类（Meanwhile→Furthermore→Additionally→Moreover→In addition→Beyond），单调重复
- 忽略了"自然承接"和"主题短语引导"等更丰富的过渡手法

---

## 二、核心理念：过渡的动态多样化

### 核心原则

> **每句的过渡方式不重复，同一段落内交替使用不同手法；有时不过渡就是最好的过渡。**

### 三层认知

| 认知层 | 旧思维 | 新思维 |
|--------|--------|--------|
| 过渡是否必须？ | 每句都必须有过渡词 | 自然承接（无过渡词）也是手法 |
| 过渡词的种类？ | 词典式轮流（Meanwhile→Furthermore→Moreover） | 短语 > 单词，主题引导 > 机械递进 |
| 过渡的节奏？ | 均匀分配，每句开头都一样长 | 长短交替，轻重交替，有放有收 |

---

## 三、七种过渡手法库

| # | 手法 | 力度 | 示例 | 适用场景 | 推荐每段频率 |
|---|------|------|------|---------|:----------:|
| 1 | **自然承接（无过渡）** | 最轻 | `The authors of \cite{...} proposed...` | 同一子主题内连续引用多篇文献 | 2–3 次 |
| 2 | **主题引导短语** | 中 | `To exploit spatial degrees of freedom,` / `At the system architecture level,` / `From the perspective of network deployment,` | 从上一个子主题切换到下一个子主题 | 2–3 次 |
| 3 | **引用开头** | 中 | `In \cite{...}, the authors...` / `Reference \cite{...} examined...` | 单篇重要文献，需要主动聚焦 | 1–2 次 |
| 4 | **同位语嵌入强调** | 重 | `A critical yet previously overlooked factor—X—was...` | 某篇文献贡献独特，需要突出强调 | 0–1 次 |
| 5 | **场景引导短语** | 中 | `For downlink scenarios,` / `In the context of secure communications,` / `For practical deployments,` | 切换应用场景或信道条件 | 0–1 次 |
| 6 | **分词短语引导** | 中 | `Going beyond...,` / `Extending this direction,` / `Building on this foundation,` | 拓展到新领域或新维度 | 0–1 次 |
| 7 | **收束总结词** | 轻 | `Collectively,` / `Together,` / `Overall,` | 段落末句，收束上文引向结论 | 仅末句 |

### 力度说明

```
轻  ●○○○○  自然承接（几乎无存在感）
     ●●○○○  引用开头 / 收束总结词
     ●●●○○  主题引导短语 / 场景引导短语 / 分词短语引导
重  ●●●●●  同位语嵌入强调（刻意制造停顿和聚焦）
```

---

## 四、手法选择三原则

### 原则一：同种手法不邻

相邻两句不使用同一种过渡手法。例如：
- ~~`To exploit spatial degrees of freedom, ... To address this challenge, ...`~~ ❌ 相邻两个主题短语
- `To exploit spatial degrees of freedom, ... The authors of \cite{...} proposed...` ✅ 主题短语 → 自然承接

### 原则二：子主题内部承接，子主题切换时引导

```
子主题A打开（主题引导短语）→ 子主题A内部第2篇文献（自然承接）→
子主题A内部第3篇文献（自然承接）→
子主题B打开（主题引导短语）→ 子主题B内部第2篇文献（引用开头）→ ...
```

### 原则三：特殊贡献用同位语嵌入

当某篇文献的贡献是**首次提出**、**颠覆性发现**或**关键的转折点**时，不要用 Notably 一带而过，改为同位语嵌入主语中：

| ❌ 较弱的处理 | ✅ 更强的处理 |
|-------------|-------------|
| `Notably, the waveguide power loss was explicitly considered...` | `A critical yet previously overlooked factor—waveguide power loss—was explicitly considered...` |

同位语嵌入在句子层面制造了**停顿-聚焦**的节奏效果，读者自然意识到"这里有重点"。

---

## 五、文献综述段落的典型节奏模型

### 本段的节奏图谱

```
句①  Topic sentence（自然陈述）
       ↓
句②  子主题A：信道传播（自然承接）
       ↓
句③  子主题A续：阻塞影响（引用开头）
       ↓
句④  子主题B：空间自由度（主题短语引导 [To exploit...]）
       ↓
句⑤  子主题B续：部署框架（自然承接，与④同句合并）
       ↓
句⑥  子主题C：系统架构（主题短语引导 [At the system...]）
       ↓
句⑦  子主题C续：波束赋形鲁棒性（自然承接）
       ↓
句⑧  强调点：波导损耗（同位语嵌入强调）
       ↓
句⑨  子主题D：下行链路增强（场景引导短语 [For downlink...]）
       ↓
句⑩  子主题E：感知通信一体化（分词短语引导 [Going beyond...]）
       ↓
句⑪  段落收束（总结词 [Collectively]）
```

### 手法分布热力图

```
句①: 自然承接（主题句，无需过渡）
句②: 自然承接
句③: 引用开头
句④: 主题引导短语    ← 子主题切换标记
句⑤: 自然承接（与④合并）
句⑥: 主题引导短语    ← 子主题切换标记
句⑦: 自然承接
句⑧: 同位语嵌入强调  ← 特殊强调
句⑨: 场景引导短语    ← 子主题切换标记
句⑩: 分词短语引导    ← 拓展标记
句⑪: 收束总结词      ← 段落结束标记
```

**11 个句位使用 7 种手法，每种最多出现 2 次（自然承接2次，主题短语2次），无相邻重复。**

### 通用模型

将此节奏抽象为可复用的模板：

```
[Topic sentence — 自然陈述]
[子主题A引导 — 主题短语 / 引用开头]
[子主题A续引 — 自然承接]
[子主题B引导 — 主题短语 / 场景短语]
[子主题B续引 — 自然承接 / 引用开头]
[特殊强调 — 同位语嵌入（可选）]
[子主题C引导 — 分词短语 / 场景短语]
[子主题C续引 — 自然承接]
[收束 — Collectively / 总结词]
```

---

## 六、逐句对比案例

### 原文 → 改文 → 手法标注

| # | 原文 | 改文（.tex 终版） | 使用手法 |
|---|------|------------------|---------|
| ① | `As a representative...various fundamental perspectives.` | `As a representative...various fundamental perspectives \cite{Xu...}` | 自然承接（主题句） |
| ② | `The channel characteristics...were analyzed by considering...Meanwhile, in \cite{Xu2026LoSBlockage}...` | `The channel characteristics...were initially analyzed...In \cite{Xu2026LoSBlockage}, the impact...was examined.` | 引用开头（替换 Meanwhile） |
| ③ | `Furthermore, the authors of \cite{Li2026PASSSpatial} proposed...` | `To exploit spatial degrees of freedom, the authors of \cite{Li2026PASSSpatial} proposed...` | **主题引导短语**（替换 Furthermore） |
| ④ | `Additionally, a dual-scale...was developed...` | `And a dual-scale...was developed...` | 自然承接（与上句 and 合并） |
| ⑤ | `Moreover, a hybrid PASS architecture...was introduced...` | `At the system architecture level, a hybrid PASS architecture...was introduced...` | **主题引导短语**（替换 Moreover） |
| ⑥ | `The authors of \cite{Sun2026PASSBeam} further proposed...` | `The authors of \cite{Sun2026PASSBeam} further proposed...` | 自然承接（保留原文） |
| ⑦ | `Notably, the waveguide power loss was explicitly considered...` | `A critical yet previously overlooked factor—waveguide power loss—was explicitly considered...` | **同位语嵌入强调**（替换 Notably） |
| ⑧ | `In addition, a downlink communication system...was studied...` | `For downlink enhancements, a downlink communication system...was studied...` | **场景引导短语**（替换 In addition） |
| ⑨ | `Beyond pure communication, the authors...proposed...` | `Going beyond conventional communication functionalities, the authors...proposed...` | **分词短语引导**（替换 Beyond） |
| ⑩ | `These studies have established...` | `Collectively, these studies have established...` | **收束总结词**（新增） |

### 过渡手法汇总对比

| 指标 | 修改前 | 修改后 |
|------|:-----:|:-----:|
| 单词过渡词占比 | 8/10 句（80%） | 0/10 句（0%） |
| 使用的手法种类 | 2 种（Meanwhile/Furthermore/Additionally/Moreover/Notably/In addition/Beyond 全是递进补充类 + These 自然收束） | 7 种（自然承接/主题短语/引用开头/同位语/场景短语/分词短语/总结词） |
| 相邻两句手法重复 | 是（连续多句递进补充词） | 否（每种手法最多连续使用 1 次） |
| 读者阅读感受 | 清单罗列，机械生硬 | 流畅叙述，自然有节奏 |

---

## 七、完整修改前后对照

### 修改前

> As a representative flexible-antenna architecture, PASS have been extensively investigated from various fundamental perspectives. The channel characteristics of PASS \cite{Xu2026RandomLoSNLoS} were analyzed by considering random line-of-sight (LoS) and non-line-of-sight (NLoS) propagation. Meanwhile, in \cite{Xu2026LoSBlockage}, the authors investigated the impact of LoS blockage with in-waveguide attenuation. Furthermore, the authors of \cite{Li2026PASSSpatial} proposed a PASS-aided spatial multiplexing scheme leveraging waveguide-induced phase variations. Additionally, a dual-scale antenna deployment framework \cite{Gan2026DualScale} was developed for PASS balancing coarse-grained movement and fine-grained positioning for coverage optimization. Moreover, a hybrid PASS architecture with beamforming design was introduced in \cite{Chen2026HPASS} significantly improving the sum rate of PASS networks. The authors of \cite{Sun2026PASSBeam} further proposed a robust beamforming framework for both lossy and lossless waveguides for analysing the impact of channel uncertainty. Notably, the waveguide power loss was explicitly considered for the first time, thereby revealing the fundamental trade-off between waveguide loss and free-space path loss \cite{Chen2026WaveguideLoss}. In addition, a downlink communication system utilizing a single-waveguide PASS assisted by a reconfigurable intelligent surface was studied in \cite{Fu2026RISPASS} to optimize the achievable rate maximization. Beyond pure communication, the authors of \cite{Yu2026ISACDiscrete} proposed a discrete activation framework to achieve equivalent radiation control for PASS-enabled integrated sensing and communication. These studies have established a solid foundation for PASS from architecture, channel, and optimization perspectives, paving the way for more advanced multi-user communication paradigms.

### 修改后

> As a representative flexible-antenna architecture, PASS have been extensively investigated from various fundamental perspectives \cite{Xu2026RandomLoSNLoS,Xu2026LoSBlockage,Li2026PASSSpatial,Gan2026DualScale}. The channel characteristics of PASS \cite{Xu2026RandomLoSNLoS} were initially analyzed by considering random line-of-sight (LoS) and non-line-of-sight (NLoS) propagation. In \cite{Xu2026LoSBlockage}, the impact of LoS blockage with in-waveguide attenuation was examined. To exploit spatial degrees of freedom, the authors of \cite{Li2026PASSSpatial} proposed a PASS-aided spatial multiplexing scheme leveraging waveguide-induced phase variations. And a dual-scale antenna deployment framework \cite{Gan2026DualScale} was developed for PASS balancing coarse-grained movement and fine-grained positioning for coverage optimization. At the system architecture level, a hybrid PASS architecture with beamforming design was introduced in \cite{Chen2026HPASS}, significantly improving the sum rate of PASS networks. The authors of \cite{Sun2026PASSBeam} further proposed a robust beamforming framework for both lossy and lossless waveguides for analysing the impact of channel uncertainty. A critical yet previously overlooked factor---waveguide power loss---was explicitly considered for the first time \cite{Chen2026WaveguideLoss}, revealing the fundamental trade-off between waveguide loss and free-space path loss. For downlink enhancements, a downlink communication system utilizing a single-waveguide PASS assisted by a reconfigurable intelligent surface \cite{Fu2026RISPASS} was studied to maximize the achievable rate. Going beyond conventional communication functionalities, the authors of \cite{Yu2026ISACDiscrete} proposed a discrete activation framework to achieve equivalent radiation control for PASS-enabled integrated sensing and communication. Collectively, these studies have established a solid foundation for PASS from the perspectives of architecture, channel, and optimization, paving the way for more advanced multi-user communication paradigms.

---

## 八、快速自查清单

写作或润色文献综述段落时，逐项检查：

- [ ] 相邻两句是否使用了同一种过渡手法？
- [ ] 段落中是否有三句以上连续以单词过渡词（Meanwhile/Furthermore/Additionally/Moreover/Notably/In addition/Besides）开头？
- [ ] 主题切换处是否使用了主题引导短语（而非简单递进词）？
- [ ] 是否有至少一处使用了自然承接（无过渡词）？
- [ ] 是否有需要特殊强调的文献？如使用同位语嵌入代替 Notably？
- [ ] 段落末句是否有收束感（Collectively/Together/Overall）？
- [ ] 全文的过渡手法种类是否 ≥ 4 种？

> 如果以上全部满足，你的文献综述段落已经具备了流畅、自然、有节奏的专业学术叙述风格。
