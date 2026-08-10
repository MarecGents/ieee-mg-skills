# ieee-mg 技能体系 v1.3.0 精细打磨诊断报告

> 诊断对象：`sandbox/dev/` 下四个技能副本（share/writing/polishing/reviewer，v1.2.0）
> 诊断方法：四路子代理逐文件阅读，与语料库 + 共享层交叉核对（v1.2.0 已完成反幻觉修正，本轮聚焦六维执行质量）
> 关键前提：`All Paper Title.md` 无 System Model 章节正文；语料均为 IEEE Trans journal，conf/mag 无语料依据
> 用途：阶段 3/4 优化执行的输入清单

---

## 〇、总览：六维问题分布

| 维度 | 严重度 | 典型问题 |
|------|:------:|----------|
| 交叉一致性（⑥） | 🔴 | share 连接词表混口径（8 词为全量值 vs 12 词分文件值同表混用）；被动语态区间与 baseline 冲突；SGF 篇综述归属矛盾；Conclusion 词数 70 vs 60-70；additionally/moreover 排序矛盾 |
| 约束可执行性（①） | 🟡 | 约 20+ 条 ✅ 检查项为主观判据（充分/清晰/自然/适当）无计数方法；深度标注与 workflow 边界 10+ 处冲突 |
| 思考深度（②） | 🟡 | 约 12+ 处"有分布无选型"决策点（Abstract 开头/问题句、Introduction 4 处、Motivation 开头/表格、Conclusion 开头/未来工作、NR 子场景组织） |
| 判断边界（③） | 🟡 | 仅 system-model 有本地化边界节；polishing 判断边界 4 份重复、conclusion 未来工作"直接添加"无授权提示；reviewer ⚠ 类别仅 system-model 落地 |
| 灵活度（④） | 🟢 | conf/mag 全文无数值分支（结构性缺口）；zh 轴占位无细则 |
| 查漏补缺（⑤） | 🟢 | polishing 缺拼写类错误（my→may、treaties→trials 等）；common-errors 漏 This is due to that/Regarding to/by the virtue of；share 术语漏 SNR/SINR/BER/BPCU/AN/SWIPT/UAV |

---

## 一、ieee-mg-share（共享层）

### 1.1 交叉一致性（⑥，最严重，先修）
- 【style-profile §5】连接词表混口径：however≈105/as a result≈23/thereby≈27/although≈20/whereas≈13/in contrast≈18/nevertheless≈8/owing to≈9 与 logic-connectors 全量 6 文件口径**完全相同**（分文件应≈一半），其余 12 词为分文件口径（×1.8-1.9≈全量）→ 统一引用 logic-connectors 全量值并删"分文件"声明
- 【style-profile §5】递进排序 "additionally（≈66）> moreover（≈67）" 数值 66<67 却用 `>` 且称"同档"；与 logic-connectors 全量（additionally 123 > moreover 121）排序相反 → 按数值改 ≈ 并列或对齐
- 【style-profile §1】被动语态"其余章节 30%-40%…与 quantitative-baseline 一致"与 baseline §2（Intro 35-45%、Conclusion 40-50%）冲突 → 逐章引用 baseline 区间，删"一致"字样
- 【paragraph-rhythm §5】Conclusion 词数"实测 70-185"与 baseline/section-architecture"最短约 60-70 词"不一致 → 统一 baseline 口径
- 【paragraph-rhythm §5】表名"段落长度分布"但 Abstract（85-280）/Conclusion（80-200）是**整章总词数** → 改表名区分"章节词数 vs 段长"
- 【logic-connectors §6】配对 "Although ... however" 语料 0 命中（无源条目，参照 v1.2.0 删除先例）→ 删除或改有源示例
- 【SKILL.md】"核心文件（style-profile/terminology/quantitative-baseline）始终加载"与 manifest `load_rules.always: []` 矛盾 → 统一（manifest 显式列出或注明由消费方 Step 0 保证）
- 【README.md】仅写"writing 和 polishing 的公共组件"漏 reviewer → 补 reviewer 为第三消费方
- 【quantitative-baseline §5】"moreover 与 additionally 几乎并列"表述含糊（分文件 66 vs 67、全量 123 vs 121 均有出入）→ 统一为"两词同档并列"并指定权威口径

### 1.2 查漏补缺（⑤）
- 【expression-bank §6】语料高频未收录："As a further advance/development"（15+ 处）、"Motivated by this/these"（15+ 处）、"has attracted...attention" 背景句式、Little is known、参数表引入句式族、This suggests that、With the emphasis/objective of
- 【expression-bank §5】原因解释变体已收 ✓，但频次未标注口径
- 【terminology §2.4/2.5】语料高频未收录：SNR、SINR、bit error rate (BER)、**BPCU**（bit per channel use）、Artificial Noise (AN)、SWIPT（两种写法并存）、UAV、energy harvesting、stochastic geometry、IoT → 补录并注明 SWIPT 主用写法
- 【style-profile §4.1】高频动词补 highlight；讨论说明类补 reveal/indicate（部分已收）

### 1.3 思考深度（②）
- 【style-profile §3】Introduction 引用三型无选择分支 → 补决策：持续影响/通用结论→现在完成时；具体历史动作/时间点→过去时；当前范例→现在时
- 【style-profile §3】Conclusion 时态"15/21 完成时 + 6/21 变体合法"无"何时可用变体"判定 → 补"无完成时标记词可自然转过去时/现在时"
- 【style-profile §1】情态动词 can>may>could>might 无"何时选哪个"分支 → 补最小决策表
- 【terminology §1】缩略语"首次定义"无判断分支（摘要内/正文内/标题）→ 补定义时机决策
- 【section-architecture】子场景划分选择（C4）、研究空白模板选型（E4）→ 各补 1 行决策规则

### 1.4 约束可执行性（①）
- 【style-profile §2】句长"25-29 词/句""0.8-1.5 从句/句"标 💡 但无判定方法，注明"不作精确断言" → 补测量法（参照 paragraph-rhythm §4.5 句界规则）或降级为参考区间
- 【style-profile §4.1】动词星级为印象分，无"同场景多动词如何取舍"规则 → 补"★★★★★ 优先，同档按主语/语态"最小规则
- 【terminology §2.1-2.5】术语表无约束列（✅/💡）→ 补约束列
- 【common-errors §4】"按功能分句保持时态一致"无判定方法 → 补"同一功能块内不得混时态；换块需有标记词"
- 【common-errors §7】"仅在段内连用时精简"阈值未定义 → 统一"同段 ≥3 次"或引 rhythm §4.5
- 【common-errors §8】💡 建议无触发判定 → 补"不可量化即替换"

### 1.5 判断边界（③）
- 【style-profile §7】缺"连接词频次与其他文件冲突时以谁为准"裁决 → 加"连接词频次以 logic-connectors.md 为准"
- 【expression-bank】缺判断边界节（E12）→ 补 1 条
- 【logic-connectors】缺判断边界节（L5）→ 补 1 条
- 【paragraph-rhythm】缺判断边界节（Y5）：节奏基准与目标期刊/审稿人偏好冲突时以谁为准 → 补 1 条
- 【common-errors】缺判断边界节（G7）：writing 不应主动引入错误句式 → 补 1 条

### 1.6 灵活度（④）
- 【SKILL.md §使用边界】conf/mag 只有定性描述无数值分支 → 补 conf 量化（摘要≤150-200 词、引言压 3-4 层、结论 60-120 词）或指向新增 conf 小节
- 【manifest.yaml】conf/mag 值无执行分支；language.zh 无翻译规则出处 → 补量化适配参数；zh 标注"适配规则见各 static 文件"
- 【quantitative-baseline】补 conf/mag 区间缩放规则（可选增强）

---

## 二、ieee-mg-writing

### 2.1 硬性交叉冲突（⑥，先修）
- 【core.md §1.1】被动语态"其余章节 30%-40%…与 baseline 一致"与 baseline §2 冲突 → 改为逐章引用 baseline（Abstract 40-50/Intro 35-45/Results 30-40/Motivation 30-40/Conclusion 40-50）
- 【section-introduction Layer 3】方式 A 与方式 B 均以 SGF 篇为例（归属矛盾，与 section-architecture 相反）→ 方式 A 改 STAR-RIS 篇示例、方式 B 保留 SGF 篇
- 【workflow 摘要特征】开头模式描述漏被动式模式 3 → 补"被动式 A X system is investigated"并统一四模式占比
- 【section-abstract §2.2】结果引出词"词组口径"与 baseline §9"动词口径"并存易误读 → 加注"此处词组口径，动词口径见 quantitative-baseline §9"

### 2.2 思考深度（②，最大增量）
- 【section-abstract 要素 A】4 种开头模式只有占比无选型 → 补 21 篇逐篇归属表使比例闭合 + 选型树（全新系统→模式1 propose/introduces、成熟技术新场景→模式2、纯理论→模式1 investigates 或模式3、技术瓶颈/双面性→模式4）
- 【section-abstract 要素 B】问题句"约 10-20% 可选"无写/不写决策 → 领域成熟增量改进→写；全新方向/首开→省略
- 【section-abstract 要素 D】i) 系 9 组 / 1) 系 14 组无选型规则 → 编号风格与正文章节统一；纯并列用 1)，含层级用 i)
- 【section-introduction】Layer 1-4 共 4 处选型（打开方式/技术演进模式/综述组织/空白句式）→ 各补选型判据
- 【section-motivation】开头模式、贡献点数选择（=问题数=空白数；单场景 3 点、多场景 4-5 点）、对比表格"何时值得用"（贡献跨 ≥3 维度且与 ≥3 篇正交差异）→ 补决策
- 【section-numerical-results】子场景组织 A/B/C 无选择判据 → 多图独立→按图；单指标多参数→按指标；单参数扫描→按参数
- 【section-conclusion】开头 4 型、未来工作写/不写决策 → 补选型
- 【workflow 第二步】贡献点数无选择逻辑 → 加决策

### 2.3 约束可执行性（①）
- 6 个检查清单约 10 条 ✅ 主观判据（"足够的广度""逐层聚焦""研究空白明确具体""动机充分""过渡自然""语气冷静客观""不夸大"）→ 逐条补计数判据/判据词表或降级 💡（参照 paragraph-rhythm §4.5 做法）
- 【section-abstract 清单】"是否使用 IEEE 数学符号规范"摘要通常无公式适用性存疑 → 改"若含符号则符合规范（无符号视为通过）"或降级
- 【section-introduction】"引言长度 15-25%"无出处无法计算 → 改引 baseline 词数区间或注明需全文词数
- 【section-motivation 清单】正文有"动词多样性 ≥3 类"但清单缺此条 → 补入
- 【section-numerical-results 清单】"避免单纯数据罗列""与理论章节互相印证"无判据 → 给判据（≥1 句观察+≥1 句解释；引用 Remark/Theorem 编号）
- 【section-system-model 清单】"系统场景清晰描述"无判据 → 给判据（坐标/拓扑/用户分布三元素之一）
- 【section-conclusion 清单】"冷静客观/不夸大"无判据 → 给词表（不含 the best/perfect/revolutionary 等）

### 2.4 判断边界（③）
- 仅 system-model 有本地化边界节（可作样板）→ 其余 5 节各补一节：Abstract/Conclusion 结果数据缺失→[待补] 或询问；Introduction/Motivation 首创性声明→[待核]（禁止虚构空白）；NR 仿真参数/图/结果缺失→[待补]
- 【SKILL.md】"使用自然语言推断，不要显式询问用户"与"以下情况先询问用户"前后矛盾 → 加分流规则："轴检测用推断；素材类缺失（结果数据/参数/基准）才询问"

### 2.5 查漏补缺（⑤）
- 【section-motivation】补 expression-bank §2 的 "X is far from being well understood"、首创性变体 "This paper presents the first comprehensive analysis"；§6 动机过渡句式（which motivates us to develop...）；§4 贡献引导句 6 种变体
- 【section-introduction】补对比引用句式（"Different from [x]..."、"In contrast to [x]..."）
- 【section-numerical-results】补原因解释变体 3 种（The reason behind this phenomenon.../The basic reason.../The reasons are that: 1)2)3)）、归因 This comes from the fact that；补 "It is worth noting that"/"shed light on"/"To reap more insights"；补 ❌ 注 "This is because that" 为语料高频错误
- 【core.md §3.1】术语表仅 10 个核心术语 → 补 SOP/OMA/COP/DF/HD/FD 或加"见 terminology §2.4-2.6"指引行
- 【core.md §1.1】we 密度只给 Abstract → 补全各章节区间（见 baseline §3）

### 2.6 灵活度（④）
- 【SKILL.md Step 2】conf/mag 无数值 → 补 conf/mag 适配表（课题组建议非语料实测）：conf Abstract 100-180 词、编号 2-3 条、结论 60-120 词、综述 1 段、贡献 2-3 点；mag 可含教程式段、摘要 100-200 词
- 【manifest.yaml】aliases 中 "system model" 重复 → 去重；language zh 无适配细则 → 最小规则集或"遇到 zh 回退 en 规则"

---

## 三、ieee-mg-polishing

### 3.1 交叉一致性 / 去重（⑥）
- 【深度边界 3 份重复】SKILL.md Step2 + workflow.md 第四步 + manifest.yaml polish_level 三处定义 → workflow.md 第四步设为唯一权威，其余改指针式摘要
- 【判断边界 4 份重复】SKILL.md + core.md + workflow.md + 各 section → 合并一处权威 + 其余指针
- 【core.md §1.2】"the superior of X → superiority"行号不全（common-errors 为 Conclusion:114 + Numerical Result.md:1162,1194）→ 补齐
- 【workflow 第三步】"句子长度（15-30词）"单一区间未联动 baseline §4 章节化区间 → 注明"通用参考，各章节见 quantitative-baseline §4"
- 【section-abstract 批量检查】结果引出词列表缺 reveal/substantiate → 补齐 baseline §9 全表
- 【paragraph-rhythm vs baseline】Conclusion 实测最短 70 vs 60-70 → 统一 baseline 口径

### 3.2 约束可执行性（①）
- 【section-abstract 决策树】首句口语化→改写标 (light) 与 Q1 注释"moderate 及以上"自相矛盾 → 统一 (moderate)
- 【section-introduction 决策树】"丰富引用句式 (light)"（句式重组应 moderate）；"重新组织文献引用 (moderate)"（段落内结构微调应 deep）；"补充关键引用 (moderate)"（引用=新增内容应 deep 须询问）→ 逐条修正
- 【section-motivation / system-model / numerical-results / conclusion 决策树】共 10+ 处深度标注冲突 → 逐树复核
- 【section-conclusion 决策树】"是否有未来工作→💡 建议添加 1-2 句"唯一无授权提示分支 → 改"用户已提供→补全表达；未提供→询问"
- 【section-conclusion】"引入新引用→删除（✅ 硬性）"无深度标注与确认 → 标深度 + 改"提示用户，确认后删除"

### 3.3 判断边界（③）
- 【section-conclusion】"添加 From the perspective of practical applicability... 句"无授权提示 → 加"仅当用户提供实际应用背景时"
- 【SKILL.md 边界表】"引用格式修正（由 ieee-mg-citation 负责）"与 section-introduction 决策树"统一引用格式 (light)"越界冲突 → polishing 仅"检测提示"，格式修正转 citation
- 【workflow】Moderate ❌"新增技术内容"与"补充/添加仅在用户已提供时补全"存在未声明豁免张力 → 加脚注：用户已提供素材时的补全表达仍属 moderate，但须标"待确认"
- 【各 section】"新增内容须询问用户"条款 6 节未全覆盖 → 以 abstract 方法句分支为模板推广

### 3.4 思考深度（②）
- 【section-abstract 决策树】缺"结果内容与正文数据不一致/结果句缺失"分支 → 加"结果与正文冲突→提示用户核验"
- 【section-introduction 决策树】Layer 2 缺"用户无引用素材可补时怎么办"分支 → 加"无法提供→提示用户自行补充"
- 【section-numerical-results】每图 ≥4 句扩充 (deep) 仅注"不虚构数据"，无"素材不足以写 4 句→询问"分支 → 补
- 【section-conclusion】缺"正文无未来工作/无实际应用落点素材时"兜底询问分支 → 补

### 3.5 查漏补缺（⑤，语料实测）
- 【common-errors 新增"拼写/音近字"类目】my→may（Conclusion:60,84,102）、treaties→trials（:102）、high-date→high-data（:60）、certificate→certifies（Numerical:979）
- 【common-errors §7 补同族】"This is due to that"（5+ 处：Numerical Result.md:865,946,1019,1069,1359）、"As can be observed/seen/shown that + 从句"（14 处）
- 【common-errors §2 补】"Regarding to"（Introduction.md:344,476 → Regarding/With regard to）、"by the virtue of"（Conclusion.md:108 等 4+ 处 → by virtue of）
- 【common-errors §3 补】主谓一致：the major contributing factors is（:573）、the number of relays affect（:1166,1190）、curves...is plotted（:632）、rates...is more efficient（:642）、channels...strengthens（:151）
- 【common-errors §1/§2 补冠词】Without loss of the generality（:740,954）、For sake of（:740）、a amplification（:740）、it is prerequisite（:696,1162）
- 【common-errors §8 补中式/搭配】holds the main station of（:369）、realize a remarkable development（:381）、This appearance demonstrates（:979）、One occurrence is that（:628）
- 【section-numerical-results】图描述观察句过去时变体（"We observed that" 型）→ 补为需纠正项

### 3.6 灵活度（④）
- 【manifest/workflow】conf/mag 全技能 8 文件无操作化适配规则 → workflow 增 paper_type 适配小节：conf=词数区间收紧/引用密度要求；mag=教程式说明时"新增内容须询问"边界放宽
- 【polish_level】第三处定义无"能改/不能改"清单 → 改为引用 workflow.md 第四步

---

## 四、ieee-mg-reviewer

### 4.1 交叉一致性（⑥）
- 【core.md】🔴 示例"时态不统一"与 check-conclusion 映射"时态混用（同句）🔴"口径冲突 → 明确分层：同句混用🔴、跨句/全文不统一🟡，同步 check-conclusion 与 workflow
- 【core.md 原则 6 vs check-abstract 致命表】"首句被动开头 #1 🟢"（合法变体）与原则 6"合法变体保护"矛盾 → 从致命表删除该行或改注"合法，无需处理"
- 【check-results】"无仿真参数表 #2 🔴"与 baseline §7"2/21 篇无参数表合法变体"冲突 → 降级 🟡 或加注
- 【check-conclusion】"四型"封闭 vs style-profile"等变体"开放 → #1 注明"四型为语料高频型，语料可溯源变体同样合法"
- 【check-results #11a/#11b】映射表引用子项但清单仅 #11 → 明示 #11 四手法为子项 11a-11d
- 【workflow】"三段式分析"（L23）与 check-results #5"四步"术语不一 → 统一"四步分析"
- 【report-template】"依据"仅 [必填] 占位无填写规范 → 补格式模板

### 4.2 约束可执行性（①）
- 主观检查项共 17 处无判定标准（intro #1/#3/#6/#17、motivation #1/#7/#8、system-model #1/#8、results #7/#10、conclusion #3/#8、abstract #2）→ 逐条补判定方法（system-model 正反例列为最佳实践，推广）
- 【check-results #2】"TABLE 联动"判定标准缺失 → 注明依据 baseline §7 + 给判定（引言无表→参数表 TABLE I；有对比表→续编 TABLE II）
- 【check-results #7/#10】"验证理论推导""避免数据罗列"无判定 → 给判据（存在理论曲线 vs 仿真曲线对照；连续 ≥2 句只报数值无解释）
- 【check-conclusion #3/#8】"总结核心工作""未来工作具体可行"无判定 → 给判据（存在"本文提出/推导/验证了什么"型复述；未来工作含具体对象）
- 【check-conclusion 致命表】标题"13 项全映射"缺 #3；#4 出现两行（双判据）→ 补 #3 映射、合并 #4

### 4.3 思考深度（②）
- 【workflow 证据链】三步走示例冗长绕；"第X句"无句号编号体系 → 简化示例 + 补"句号切分计数（公式行/图题不计句）"规则
- 【report-template】"依据"字段无填写规范（主观项/无语料支撑项写什么）→ 补格式模板与示例

### 4.4 判断边界（③）
- 【SKILL.md】"无法客观判定即标 ⚠"与 check 清单仅 system-model 落地不符 → core.md 补"⚠ 适用于何种检查项"通用规则 + 各 check 主观项标注
- 【SKILL.md / workflow / report-template】技术问题类别命名三处不一（"⚠ 技术问题（范围外）"/"超出本技能范围的技术问题"/"⚠ 存疑/需人工复核"）→ 统一两类各自适用场景
- 【severity】⚠ 与三档过滤关系未定义 → 加"⚠ 不受 severity 过滤、始终单独列出"
- 【workflow Step 3】全局检查与单章 scope 关系未定义 → 加"scope 为单章时全局检查仅针对该章执行"
- 【workflow】技术问题→范围外标注处理未提示 → 按 SKILL.md 边界单独标注

### 4.5 灵活度（④）
- 【workflow】统计表固定四行未说明 severity 过滤后如何裁剪 → 加"统计表只统计输出级别+⚠ 行"
- 【check-results】缺 MC 次数检查（SKILL.md Step0 声称但未落地）→ 加 🟢 提示级检查项
- 【check-introduction】缺"连接词密度 7-10/千词（baseline §5）"检查（Step0 声称但未落地）→ 补或从 Step0 删词

### 4.6 查漏补缺（⑤）
- 【check-abstract】baseline §4 Abstract 句长 25-29 词/句未纳入（仅句数 5-12）→ 补 🟢 提示项
- 【check-abstract】被动语态比例（baseline §2 低可信度）可作 🟢 提示项

---

## 五、优先级排序（执行阶段修复顺序）

| 优先级 | 修复项 | 涉及文件 |
|:------:|--------|----------|
| P0 | 硬性交叉冲突 4 处：share 连接词表混口径、share/writing 被动语态与 baseline 冲突、writing SGF 篇综述归属、polishing 深度边界去重 | style-profile / core.md ×2 / section-introduction / SKILL.md+workflow+manifest（polishing） |
| P0 | Conclusion 词数 70 vs 60-70 统一、check-conclusion 时态混用严重性分层、check-abstract 被动开头从致命表移除 | paragraph-rhythm / baseline / check-conclusion / check-abstract |
| P1 | 思考深度：12+ 处选型决策树（Abstract/Introduction/Motivation/Conclusion 开头与内容选型、NR 子场景组织） | writing 各 section |
| P1 | 约束可执行性：20+ 主观 ✅ 检查项补判定方法 | writing 6 清单 / reviewer 6 check / common-errors |
| P1 | 判断边界：polishing 6 节"新增须询问"全覆盖、reviewer ⚠ 类别全落地、writing 5 节补 [待补]/[待核] | polishing 6 section / reviewer core+check / writing 5 section |
| P2 | 查漏补缺：common-errors 拼写类/due to that/Regarding to 等语料实证错误、share 术语 SNR/SINR/BER/BPCU/SWIPT、expression-bank 高频句式 | common-errors / terminology / expression-bank / writing section-motivation+introduction+numerical-results |
| P2 | 灵活度：conf/mag 数值适配表（share SKILL.md + writing SKILL.md + polishing workflow）、zh 轴细则 | share SKILL.md / writing SKILL.md / polishing workflow / manifest |
| P3 | 版本号 1.2.0 → 1.3.0 全局同步 | 四技能全部 SKILL.md/manifest.yaml/static 头部 |
| P3 | 判断边界缺失文件补齐（expression-bank/logic-connectors/paragraph-rhythm/common-errors 各 1 条） | share static 4 文件 |
