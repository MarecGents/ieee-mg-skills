# ieee-mg 技能体系 v1.2.0 差距诊断报告

> 诊断对象：`sandbox/dev/` 下四个技能副本（share/writing/polishing/reviewer，v1.1.0）
> 诊断方法：四路只读子代理逐文件阅读，与 `sandbox/dev/ieee-mg-database/` 六个语料文件交叉核对（grep 计数 + 逐篇人工核验）
> 关键前提：`All Paper Title.md` 仅含 Abstract/Introduction/Numerical Results/Conclusion 四部分，**无 System Model 章节内容**
> 用途：阶段 3/4 优化执行的输入清单

---

## 〇、总览：六个质量维度问题分布

| 维度 | 严重度 | 典型问题 |
|------|:------:|----------|
| 反幻觉（语料溯源） | 高 | 多处占比/频次统计与语料矛盾；个别"语料中不存在 X"断言被语料反例直接证伪；错误案例伪造（语料无此错误） |
| 约束分级 | 中 | 检查清单无必须/建议/禁止分级；严重性映射覆盖率仅 43%；light/moderate/deep 无操作化边界 |
| 思考深度 | 中 | 缺决策树、推理链、证据引用规范（reviewer 报告无"依据"字段） |
| 判断边界 | 中 | 无"何时询问用户/何时停止"规则；润色 vs 扩写边界缺失（core 禁止添加 vs section 要求补充的冲突） |
| 灵活度 | 低 | journal/conf/mag 轴定义了但 static 无分支内容；zh 轴占位；reviewer 单章审核仍输出全章分布表 |
| 查漏补缺 | 低 | 语料高频模式未收录：结果引出词变体、贡献引导句 6+ 变体、"One phenomenon is that" 等 |

---

## 一、ieee-mg-share（共享层）

### 1.1 反幻觉（统计/断言无源或与语料矛盾）
- 【style-profile】情态动词排序 "can > may > could > might" 无计数依据；Introduction 中 may/could/might 用例极少
- 【style-profile】被动语态 "约 35%-45%（Abstract ~45%）" 与 quantitative-baseline "Abstract 40%-50%" 区间不一致，均无 POS 统计佐证 → 统一数值并标注为估算
- 【style-profile】"禁止缩略形式"宣称源自语料不实：语料含 "doesn't"（Numerical Result.md:330）、"it's"（:636）→ 改为"课题组规范（语料偶见反例，polishing 需纠正）"
- 【style-profile】"Abstract 平均句长 ~18 词" 与实测（抽样 6 篇均值 25-29 词/句）不符；quantitative-baseline 又写 18-22 → 统一并降级为定性
- 【style-profile】高频动词星级（★★★-★★★★★）无计数依据；"性能对比 outperform"远高于 ★★★ 档；"reveal/indicate"未收录 → 给出计数或注明印象分
- 【style-profile】§4.2 形容词表 "superior" 重复出现两次 → 去重
- 【style-profile】§4.3 "bridge the gap → 指出本文贡献"场景错误：语料 3 处均为描述 ipSIC 性能差距（"a larger κ is required to bridge the gap caused by ipSIC"）→ 改为"描述残余干扰造成的性能差距"
- 【style-profile】§5 连接词：实测 furthermore≈86 > in addition≈70 > additionally≈67 > moreover≈56，"递进首选 moreover"错误；"because of"全库仅 3 行 → 按实测重排
- 【style-profile】§5 强调首选 "in particular"，与 logic-connectors（specifically ★★★★★，实测 48 vs 13）矛盾 → 统一
- 【style-profile】§3 Introduction 时态表不完整：引用句还有现在完成时（"have demonstrated"）与现在时变体（"the authors of [14] demonstrate"）→ 补全三型
- 【style-profile】§3 Conclusion "现在完成时回顾"过严：约 6/21 篇用过去时或现在时 → 降为软性多数派并给反例
- 【terminology】"(EDR)"：全库无 "Ergodic Data Rate (EDR)" 缩写定义；"(SE)"/"(EE)"/"(OP)" 同样无定义 → 删除或标注"课题组建议缩写，语料未实际使用"
- 【terminology】"Detection Error Probability (DEP)"：语料 Abstract 只用全称，正文才定义 → 规范调整
- 【terminology】"Over-the-Air (OTA) Computation"与语料 "over-the-air (OTA) computing techniques" 写法不一致 → 统一
- 【terminology】"标题中尽量不使用缩略语"与语料 18/21 篇标题含缩略语矛盾 → 改写为课题组投稿规范
- 【expression-bank】"空白句式 there is/are no ... to investigate 约 70%"：精确模板仅 2-3 处，实际主流是变体（"has not been comprehensively explored"、"is not researched yet"、"this paper is the first"、"there is no related work to analyze"）→ 补全变体清单并注明口径
- 【logic-connectors】星级表约 70% 与实测不符（moreover ★★★★★ 实际第四、such as ★★★★★ 实际 13 行、hence 35 行应为 ★★★★ 等）→ 按实测重算并注明统计口径
- 【logic-connectors】"单词过渡词综合征"例词 Notably（2 行）/Besides（4 行）/Meanwhile（1 行）几乎不出现在语料 → 按实测高频词重写（Furthermore/In addition/Additionally/Moreover）
- 【logic-connectors】§2 例句 "Although X has been studied, the integration of X and Y is still in their infancy." 单数主语配 their → 改 "its"
- 【logic-connectors】连接词密度 "Introduction 每段 3-5 个"与 quantitative-baseline "15-25/千词" 矛盾（实测约 7.7/千词）→ 统一重测
- 【section-architecture】Abstract 5 要素比例严重失真：要素 B"已有工作不足"声称 86% 实测 2-3/21（10-20%）；要素 D 实测 100%（声称 90% 低估）；要素 E 意义句实测 5-15%（声称 30% 高估）
- 【section-architecture】Abstract 词数 "100-250（典型 120-200）"与 quantitative-baseline "85-280" 矛盾，实测 130-260 → 统一
- 【section-architecture】"Motivations and Contributions 节约 70%"实测 ~57%（含变体）；"Organization and Notation 约 60%"实测 17/21≈81%
- 【section-architecture】Motivation "尖锐问题引导 30%"实测 2/21≈10%；"对比表格 25%"实测 1/21≈5%
- 【section-architecture】"贡献列表（4 点）"过严：语料 3-5 点不等；动作顺序不严格 → 改"3-5 点，推荐四动作"
- 【section-architecture】"仿真参数表（TABLE II）"不准确：语料 TABLE I（11 篇）与 TABLE II（8 篇）并存，取决于引言是否已用 TABLE I 作对比表
- 【section-architecture】Conclusion "未来工作 70%"实测 10/21≈48%；"不分段 80%"实测 100%；词数 "200-400"实测 70-185（0 篇达 200）→ 统一改实测区间
- 【common-errors】"in the basis of"、"different with"、"dependent to"、"independent from" 语料均无出现（语料实际错误是 "independent to"）；"从语料提取"声称不成立 → 删除无源条目，替换为语料实测错误
- 【SKILL.md】"约 40% 内容在 writing/polishing 间共享"无法核验 → 删除数字或注明维护估算

### 1.2 约束分级 / 判断边界 / 灵活度
- 【SKILL.md】仅职责边界表，无运行时判断边界：何时该用/不该用本层数据、语料与目标期刊规范冲突时怎么办
- 【manifest.yaml】system-model 轴无任何语料数据 → 标注"外部通用知识，非语料蒸馏"
- 【manifest.yaml】paper_type 三值定义了但全部 static 无分支内容；language zh 轴占位无中文内容
- 【quantitative-baseline】声明被 reviewer 使用却从未被任何技能加载 → 接入加载协议（本次修复重点）

### 1.3 查漏补缺（语料高频未收录）
- 【expression-bank】结果句式缺："One phenomenon is that / Another phenomenon is that"、"One can observe that / As can be observed from the figure"、"The reason is that / The reason behind this phenomenon is that"、"This comes from the fact that"、"This is attributed to"
- 【expression-bank】贡献引导句缺："The main contributions of this paper can be summarized as follows" 及 6+ 变体（约 15/21 篇）→ 新增类别
- 【expression-bank】未来工作/过渡缺："which motivates us to develop this treatise"、"On this basis, ..."、"Based on the analytical/asymptotic results, ..."
- 【terminology】高频术语未收录：Eve/Eves、I-Eve、warden（Willie）、legitimate user (LU)、hardware impairments (HIS)、Shadowed-Rician fading、LEO、decode-and-forward relay、full-duplex/half-duplex、two-way relay、throughput ceiling/error floor
- 【expression-bank】§3 贡献陈述无量化自查清单 → 加"动词+方法+结论"核对
- 【common-errors】"This is because that"（≥3 处语料错误变体）未收录

---

## 二、ieee-mg-writing

### 2.1 反幻觉（占比失真，按文件）
- 【section-abstract】结果引出词 "Numerical results show/demonstrate ~67%" 实测 12/21≈57%（Simulation 系 8/21≈38% 而非 ~19%）；"experimental ~14%" 实测 1/21；四个变体各 ~10-15% 实测各 1 篇（~5%）
- 【section-abstract】要素 E 意义句例句 "...presents a promising solution for enhancing modern communication networks" 实为 **Introduction 语料** 的句子，Abstract 语料无 "promising solution" → 换例句
- 【section-abstract】"Although 让步式约 10%" 实测 1/21（~5%）；"yields/yield 两种形式均有" 实测仅单数；词数四处矛盾（85-280 / min166/max273 / ~210 / 100-250 / 120-200）→ 统一
- 【section-abstract】"约 40% 总-分结构" 无统计依据；"14/21 用 we" 实测 16/21≈76%
- 【section-introduction】Layer 1 开头模式失真：实测 With 系 11/21≈52%（居首）、As 系 5/21≈24%、deemed 2/21≈10%、The novel 0 篇（示例取自 Abstract）、直接陈述 3/21≈14% → 按实测重排
- 【section-introduction】Layer 3 "1) [Category] 编号约 70%" 实测 2/21≈10%；"嵌套子节 ### A. Previous Works 约 60%" 实测仅 1 篇
- 【section-introduction】Layer 4 "21 篇引言均以 To the best of our knowledge 引出空白" 实测 12/21；"尖锐问题约 15%" 实测 2/21；示例 "Will NOMA relaying..." 语料原文为 "Will **FD** NOMA relaying..."
- 【section-introduction】**证伪断言**："语料中不存在 has not been comprehensively explored" ← Motivation 语料 FL 篇存在该句；"问题为直接问句而非 seeking answers 框架" ← MF-RIS 篇即 "by seeking answers to these questions:"
- 【section-introduction】引用句式库 "Prior works have demonstrated..."、"X has been extensively studied..." 语料无此两句式（仅一处 "Prior studies have demonstrated"）
- 【section-introduction】"符号说明段落约 60%" 实测 17/21≈81%，且位于 Introduction 而非 System Model
- 【section-motivation】"While 模板 100%" 实测 While 8/21≈38%、Although 1/21≈5%（12 篇不用）；"尖锐问题 30%" 实测 2/21≈10%；"对比表 25%" 实测 1/21≈5%
- 【section-numerical-results】"TABLE II 标准格式" ← 语料参数表以 TABLE I 为主（11 篇）；示例行 "κ=5 dB、M=30、10^5 次" 与语料（κ 多为 -5/-7 dB、MC 主流 10^6）不符；"基准 3-5 个" 实测多篇仅 1-2 个
- 【section-numerical-results】"多因一果 25%" 实测仅 SGF 1 处
- 【section-conclusion】"未来工作约 70%" 实测 10/21≈48%；"200-400 词" 实测 70-185（0 篇达 200）
- 【core.md】被动 35-45%、句长 18-25、从句密度 0.8-1.5 无统计证据；we 14/21 实测 16/21

### 2.2 system-model 模板（无语料依据的推测，需标注口径）
- 坐标系统模板仅 FL 篇 Numerical Results 开头一段 Cartesian 3D 描述，被升格为"课题组标准格式" → 属推测性泛化
- 假设清单（quasi-static fading、正交资源、反射/透射系数独立）全语料无此词；仅 "CSI 完美已知" 可间接溯源
- 信号模型公式（x=Σ√(Pa_i)s_i、y_i=h^HΘHx+n、Θ=diag(βe^{jθ})、SINR）语料无任何公式原文 → 标注"外部通用知识"
- SIC 描述句式、align 优化问题格式、Algorithm 伪代码、复杂度分析句式均无语料依据（仅 R-NOMA-BF 结论提及 "procedure and complexity"）
- 信道模型类型（Rician 最常见 ✓、Nakagami-m 级联 ✓、Rayleigh 非视距无直接依据）

### 2.3 约束分级 / 判断边界缺失
- 仅 core.md 有 ✅/推荐/❌ 三级；其余 7 个模板检查清单全部为无分级 [ ] 项（约 70 项）
- 无"何时询问用户"规则：词数超限、主题超出领域、缺仿真参数/基准/图表、目标期刊未知、要求编造引用/数据
- 无"何时停止"规则：无完成条件、无输出前确认、无数据不足时占位/标注待补的决策规则
- 无置信度降级机制：统计声明与语料不符时如何处理未定义

### 2.4 查漏补缺（语料高频未覆盖模式）
- Abstract 篇 18/21 双编号结果组（"Our analytical results reveal that: i)... ii)..." + "Finally, simulation results demonstrate that: 1)..."）；篇 13 编号条目小写开头；篇 15 单条内嵌 However 转折
- Introduction FD/HD 篇 "The first aspect... The second aspect..." 分块综述替代编号；R-NOMA-BF 篇 "The basic contributions of the thesis are summarized as follows."
- Motivation covert 篇 "To our knowledge, ... there currently are no treatises..."（去 best of 变体）；"this paper has three main differences. Firstly... Secondly... Thirdly..." 差异列点式
- Motivation FL 篇贡献列表用 "-" 项目符号；对比表单元格含 "✓, but not mentioned"
- Conclusion 篇 16 被动现在时开头；篇 2 "warranting consideration in future research" 间接式未来工作
- Numerical Result FD/HD 篇 "1) Outage Probability: Fig. 2 plots..." 场景标题式；参数表标题变体 "TABLE II: Table of Parameters for numerical results."

---

## 三、ieee-mg-polishing

### 3.1 反幻觉（错误案例伪造 / 与语料矛盾）
- 【最严重·三文件同源】图描述时态规则：core.md 1.4 + common-errors §4 + style-profile §3 + section-numerical-results Q3 全部规定用过去时（"Fig. X plotted"），语料 30+ 处全部为现在时 "Fig. X plots"，"plotted" 0 命中 → 全部改为现在时
- 【core.md 1.5 + common-errors §7】"It is shown from Fig. X that" 语料 0 命中；语料高频是 "It can be seen from Fig. X that" / "As can be seen from the figure"
- 【core.md 1.5】"It can be observed that" 列为冗余应删 ← 语料 8+ 处高频，且 paragraph-rhythm §2 自己把 "Another observation is" 列为 Results 标准 Topic Sentence（内部冲突）
- 【core.md 1.1 + common-errors §1】缺冠词示例 "to verify accuracy of" 伪造：语料 6+ 篇全部为 "verify the accuracy of"
- 【core.md 1.2 + common-errors §2】"different with → different from" 语料 0 命中；真实错误是 "Similar with"（Numerical Result.md:224）
- 【common-errors §2】"compare with → compared to（★★★）"：语料 "compared with" 高频（8+ 处）且标准英语，core.md 1.2 自己承认其合法 → 共享层两文件互相矛盾
- 【common-errors §2】"independent from" 语料 0 命中；真实错误是 "independent to"（All Paper Title.md:818）
- 【section-numerical-results】"蒙特卡洛 FL 场景 10^3-10^4"：语料唯一 FL 篇为 "10 iterations"
- 【section-abstract 决策树】首句非模式 A/B → 改写（light）：语料 21 篇中 11 篇（52%）为背景式/被动式/技术主语式开头，决策树无此分支，实操会改写语料主流开头
- 【section-conclusion 决策树】强制非高频开头改写：语料 4/21 篇（19%）以 "In this paper, we investigated" 等合法开头
- 【section-conclusion】"被动完成时开头约 48%" 严格口径仅 8/21≈38%（把被动过去时计入才 48%，口径含糊）
- 【section-conclusion】"语料中不存在 In this paper, we have investigated 精确开头" 字面成立但近邻形式存在，且制作流程文档自身用该句式 → 声明有误导性
- 【section-system-model】全部内容无法从语料溯源（同 writing 2.2）

### 3.2 语料实测错误但未收录（查漏补缺，13 条）
- "outperforms than"（Abstract.md:30）；"Similar with"（Numerical Result.md:224）；"Numerical results are present to confirm"（present→presented，Abstract.md:62）
- 主谓一致："The FL accuracy ... are enhanced"（Abstract.md:2）、"verify the correctness of the formulas and yields"（:30）、"we plots"（:1283）、"Fig. 6 further give"（:1174）、"the system throughput ... are evaluated"（Conclusion.md:42）、"were discussed"（:102）
- 缩略 "doesn't"（:330）、"it's"（:636）；"It is can be seen from the figure"（:391）
- "the superior of FD NOMA was not apparent"（Conclusion.md:114）superior→superiority；"the preponderance of ipSIC is inexistent"（:910,1231）inexistent→nonexistent
- "The setup of perfect CSI my bring about"（:60,84,102 共 3 篇）may 笔误（高频）
- "while it is still in their infancy to survey"（Introduction.md:418）is/their 数不一致

### 3.3 约束分级 / 判断边界缺失
- 【light/moderate/deep 无操作化边界】workflow 深度表只有"修改范围"短语，无"各深度能改/不能改"清单；section 决策树标注与 workflow 冲突（首句改写标 light 属句式级重写、"添加标准开头"标 light 属添加内容）；同一深度内相反操作（deep 并列"删除冗余句"与"补充细节"）
- 【润色 vs 扩写边界缺失（系统性冲突）】core.md 禁止事项 1"不得添加原文没有的技术内容" vs 6 个 section 决策树全部要求"补充"（方法句/引用/空白/贡献点/原因解释/性能数据/未来工作）→ 整个技能包无边界
- 【无询问机制】8 个文件均无"改动涉及新增技术内容/结构时先询问用户"的触发条件
- 【唯一删除授权】仅 section-conclusion "引入新引用→删除"，无对称的"新增内容需授权"规则

### 3.4 与共享层重复/冲突
- core.md 1.1-1.5 与 common-errors §1/§2/§3/§4/§7 几乎逐条照抄（共同携带 4 处同源错误）
- paragraph-rhythm §4 与 section-introduction Q5+决策树重复定义
- 冲突① Abstract 词数（85-280 vs 100-250）；冲突② 图描述时态；冲突③ It can be observed；冲突④ compare with

---

## 四、ieee-mg-reviewer

### 4.1 反幻觉
- 【check-abstract #12】we 密度 "8-15/千词"与 quantitative-baseline（6-8）、style-profile（6-8）、writing 模板（6.5）全部矛盾，疑似错位抄取 System Model 区间 → 改 6-8
- 【check-abstract #8 vs 致命问题表】"100-250 词" vs "词数<80 或 >280 🟡" 同文件自相矛盾；baseline 为 85-280 → 统一
- 【check-abstract #15】"含具体数值/百分比"：语料 21 篇摘要 **0 篇**包含数值 → 删除或改为"含性能比较（100% 覆盖）"
- 【check-abstract #1】"Although... + To address these issues" 仅 1/21（~5%）列为高频夸大 → 标注低频变体
- 【check-introduction #2】Layer 1 引用 "2-5 篇"实测远超（FL 首段 [1]-[6]、STARS-SGF 背景 [1]-[17]）→ 改 "≥2 篇"
- 【check-introduction #8】"贡献必须 1)2)3)4) 编号"：FL 篇用 "- " 项目符号 → 改"编号或等价列表"
- 【check-motivation #1】"While 开头必查"：语料约 8/15 篇 While（含完整 Motivation 段落口径 ≈53%，全 21 篇 ≈38%），另有 The aforementioned/Building upon/As previously mentioned 变体 → 改"承上启下模式"并列变体
- 【check-motivation #4】"四动作全覆盖"语料不成立（ASTARS covert 篇 propose→derive→derive→derive）→ 改"动词多样性 ≥3 类"
- 【check-motivation #6】"对比表 ≥4 维度"仅 FL 一篇 Table I，无统计依据 → 注明非强制
- 【check-results #2】"仿真参数表 TABLE II"写死 → 语料 TABLE I 为主 → 改"Table I 或 Table II 是否存在"
- 【check-results #3】"基准 ≥3"：约半数论文仅 1-2 个 → 改"≥1 个明确基准"
- 【check-results #8】"better/good 禁令"与语料矛盾（"provides better outage probability" 大量使用）→ 改"优先 superior/significant，better 不作错误项"
- 【check-conclusion #9】"200-400 词"：21 篇 0 篇达 200 → 改实测区间 80-200（均值 ~145），并同步上游 section-architecture/writing 模板
- 【check-conclusion #4】"含数值"仅 FL 1/21 篇 → 改"是否复述关键发现（数值可选项）"
- 【check-conclusion #11/#12/#13】"Firstly...Secondly...Finally"仅 1/21；"From the perspective of practical applicability"仅 2/21；"It can be confirmed that"语料 0 篇（"It has been shown that" 2 篇成立）→ 标注低频可选
- 【check-results #11-14】低频/单篇模式当 4 个独立必查项（"Another reason is that" 1-2 篇等）→ 合并为"深度分析手法任选其一"
- 【check-abstract #14】"避免 very/obviously/clearly"无依据且语料有 "It is obvious to see that" → 删除或降级

### 4.2 约束分级
- 严重性映射覆盖率仅 43%（39/90 项）；各 check 致命问题表未覆盖的检查项失败时无法定级 → 补全映射
- 量化检查项（词数、密度）无计数方法 → 每条注明判定方法（人工数/脚本/正则）
- 风格符合度 "预估 XX%" 无计算方法和输入 → 给出换算规则或改定性

### 4.3 思考深度
- 【报告模板缺"依据"字段（核心缺口）】条目字段为 位置/原文/问题/建议，缺"触发哪个 check 项 + 对应语料模式/baseline 数值" → 报告可审计性为零
- workflow 无"问题→证据→依据"推理链规范

### 4.4 判断边界
- 缺"边界外发现处理规则"、"停止/降级条件"、"证据不足标注机制"（System Model 无语料支撑时如何声明）
- 报告无"存疑/需人工复核"条目类型

### 4.5 灵活度
- 单章审核（scope=abstract）仍输出全部 6 章节分布表 → 按 scope 动态裁剪
- severity 轴、language=en 轴"定义了但未接线"（无过滤逻辑、无英文模板）
- journal/conf 适配完全缺失（共享层 paper_type 轴未继承）
- quantitative-baseline 声明被 reviewer 使用却从未被加载 → 接入 SKILL.md Step 0

### 4.6 查漏补缺
- 语料可量化但未入 check：编号结果 2-4 条/每条 15-30 词、结果引出词变体库（6+ 种）、Results 子节三段式（A/B/C）、"Fig. X plots ... versus" 引入句、被动语态比例区间、连接词密度、引用密度（Intro 30-60/千词）、图表密度、Conclusion 单段结构、未来工作三型
- check-introduction 缺 "Motivations and Contributions 节"与 "Organization and Notation 节"存在率检查、贡献引导句模式
- check-conclusion 缺"不分段（~100%）"检查、未来工作句式全收录

---

## 五、优先级排序（执行阶段修复顺序）

| 优先级 | 修复项 | 涉及文件 |
|:------:|--------|----------|
| P0 | 图描述时态改现在时（Fig. X plots） | style-profile / common-errors / polishing core / section-numerical-results（writing 与 reviewer 同步） |
| P0 | Conclusion 词数改实测区间（80-200） | section-architecture / quantitative-baseline / section-conclusion（writing）/ check-conclusion |
| P0 | Abstract 词数统一（85-280） | section-architecture / quantitative-baseline / section-abstract / check-abstract / paragraph-rhythm |
| P0 | 删除证伪断言（"不存在 has not been comprehensively explored"、"非 seeking answers 框架"） | section-introduction / section-motivation |
| P0 | TABLE II 写死 → Table I/II 联动 | section-architecture / section-numerical-results / check-results / workflow |
| P0 | we 密度 8-15 → 6-8 | check-abstract |
| P1 | 占比类统计按实测修正（开头模式、To the best 12/21、1) 编号 10%、While 38%、未来工作 48%、要素比例、基准 ≥1） | section-architecture / section-introduction / section-motivation / section-conclusion / section-abstract / check-* |
| P1 | 连接词星级/排序按实测重算并注明口径 | style-profile / logic-connectors |
| P1 | 删除伪造错误案例，补 13 条语料实测错误 | common-errors / polishing core |
| P1 | quantitative-baseline 接入 reviewer Step 0 加载协议 | reviewer SKILL.md / manifest |
| P1 | 报告模板加"依据"字段 | report-template / reviewer workflow |
| P2 | 约束分级：全部检查清单标 ✅必须/💡建议/❌禁止 | writing/polishing/reviewer 全部 check/section 文件 |
| P2 | 判断边界：询问用户/停止/降级规则 + 润色 vs 扩写边界 | 各 SKILL.md / core.md / workflow.md |
| P2 | light/moderate/deep 操作化边界 | polishing workflow / section 决策树 |
| P2 | system-model 全系列标注"外部通用知识，非语料蒸馏" | section-system-model ×2 / check-system-model / section-architecture / manifest |
| P3 | 查漏补缺：结果句式、贡献引导句、术语补录、变体模式 | expression-bank / terminology / 各 section / check 文件 |
| P3 | 灵活度：conf/mag 分支、scope 动态裁剪、英文报告模板 | manifest / reviewer workflow / report-template |
| P3 | 交叉一致性修复（in particular vs specifically、compared with、词数、时态） | style-profile / logic-connectors / common-errors / core.md |
