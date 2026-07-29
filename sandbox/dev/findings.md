# 语料 vs 模板：蒸馏对比发现记录

> 生成时间：基于 Phase 2 第一轮蒸馏对比分析

## 对比矩阵总览

| 章节 | 结构变体缺失 | 句式/用词缺失 | 段落组织缺失 | 定量特征缺失 | 特殊技巧缺失 | 总计 |
|------|:---:|:---:|:---:|:---:|:---:|:---:|
| Abstract | ①⑥ | ③ | ② | ⑤ | ④ | **6** |
| Introduction | ⑧ | — | ⑦⑨⑩ | — | — | **4** |
| Motivation | ⑪ | ⑫ | — | — | ⑬⑭ | **4** |
| Numerical Results | ⑯⑱ | — | ⑲ | ⑮ | ⑳ | **5** |
| Conclusion | ㉓ | ㉕ | — | — | ㉑㉔㉒ | **6** |
| **总计** | **8** | **3** | **5** | **2** | **7** | **25** |

## 缺失详情速查

### Abstract（6处）
1. **让步-转折一体化背景句** — "Although RIS can improve..., it still faces challenges..."
2. **"总-分"式方法展开** — "Specifically, we derive..."
3. **结果引出词"indicate that"变体** — 模板只收录了show/demonstrate
4. **结果句条件限定修饰** — "especially when..."
5. **定量词数分布** — 实际最短85词，最长280词
6. **编号结果前总起句** — "The simulation results verify the correctness and yields the following insights:"

### Introduction（4处）
7. **文献综述嵌套子节结构** — "1) XXX: ... 2) YYY: ... 3) ZZZ: ..."
8. **引用句式"In [x], the authors..."变体** — "In [16], the authors introduced..."
9. **符号说明段落多种呈现方式** — 有3种不同风格
10. **技术演进段落高密度引用特征** — 每句1-3个引用

### Motivation（4处）
11. **贡献点三层递进结构** — 动作→工具→结论
12. **研究空白句"there are no existing works"变体**
13. **尖锐问题与贡献的一一映射关系**
14. **对比表格特征行五维设计清单**

### Numerical Results（5处）
15. **蒙特卡洛迭代次数实际分布** — 10^6最常见，FL场景10^3-10^4
16. **"多因一果"解释模式** — "Another reason is that..."
17. **trade-off权衡表达** — "does not necessarily translate to better..."
18. **"On the one hand... On the other hand"双面论证**
19. **子图联合分析模式** — "Fig. X(a)... Fig. X(b)... The main variation is that..."

### Conclusion（6处）
20. **基准方案详细描述风格** — 含设计原理和使用条件
21. **多层数值对比** — "Compared to A and B, achieved X% and Y%, respectively"
22. **"当前假设局限→未来工作"因果结构** — "The setting of X may give rise to overestimated performance, hence..."
23. **"Firstly... Secondly... Finally"顺序词串联**
24. **实际应用场景落点** — "From the perspective of practical applicability..."
25. **"It has been shown that..."确认性被动句式**

---

# 第二轮蒸馏对比发现（2026-07-15）

> 基于交叉一致性审计 + 语料深度重读的新增发现。

## Abstract 新增发现（6项）

| 编号 | 缺失 | 描述 | 状态 |
|:----:|------|------|:----:|
| 26 | "More specifically"过渡词 | 语料中"More specifically"频率远高于"Specifically"，建议优先使用 | ✅ 已补充 |
| 27 | 结果引出词变体库 | 补充"The simulation findings are presented to demonstrate"等4种变体 | ✅ 已补充 |
| 28 | "manifest that"引出词 | 语气比"show"更强，适用于强调发现确凿性 | ✅ 已补充 |
| 29 | 总起句"yield the following insights" | 语料中出现"yields/yield"混用，建议统一"yield" | ✅ 已补充 |
| 30 | "On top of these"递进过渡 | 在已有分析基础上进一步推导的过渡词 | ✅ 已补充 |
| 31 | "precede that of"比较动词 | 作为 outperform/exceed/superior to 的补充变体 | ✅ 已补充 |

## 交叉一致性审计修复（2026-07-15）

### Reviewer 检查项补充（8项）
| 编号 | 章节 | 补充内容 | 状态 |
|:----:|:----:|----------|:----:|
| R1 | Abstract | 检查项1放宽，支持让步转折句式 | ✅ 已修复 |
| R2 | Results | 补充多因一释检查（"Another reason is that"） | ✅ 已修复 |
| R3 | Results | 补充 trade-off 权衡表达检查 | ✅ 已修复 |
| R4 | Results | 补充双面论证检查 | ✅ 已修复 |
| R5 | Results | 补充子图联合分析检查 | ✅ 已修复 |
| R6 | Conclusion | 补充顺序词串联检查 | ✅ 已修复 |
| R7 | Conclusion | 补充实际应用落点检查 | ✅ 已修复 |
| R8 | Conclusion | 补充被动确认句式检查 | ✅ 已修复 |

### Polishing 同步更新摘要
- **section-abstract**: 决策树新增让步句式/总-分展开/总起句/词数范围 + 批量检查新增6项规则
- **section-introduction**: 润色重点从4项扩至7项，决策树从6分支扩至9分支
- **section-motivation**: 润色重点从3项扩至6项，新增Q4/Q5案例，决策树从5分支扩至7分支
- **section-numerical-results**: 润色重点从4项扩至10项，新增Q5/Q6案例，决策树从6分支扩至10分支
- **section-conclusion**: 新增润色重点6项，决策树从4分支扩至8分支
