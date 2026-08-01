# Numerical Results 审核清单

> **v1.2.0**：参数表 TABLE I/II 联动；基准 ≥1；图描述时态改现在时；低频手法合并为深度分析检查；致命问题全映射。

- [ ] 1. 是否以 "In this section..." 开头（21/21 语料实证；变体 6+ 种均可，模式匹配而非字面匹配）
- [ ] 2. 仿真参数表（TABLE I 或 TABLE II，与引言对比表编号联动）是否存在
- [ ] 3. 基准方案是否≥1个（约半数论文仅 1-2 个基准）
- [ ] 4. 每张图是否被 "Fig. X" 引用
- [ ] 5. 每张图分析是否≥4句（引入→观察→解释→对比；计数方法：图引用句计入，公式/图表标题不计）
- [ ] 6. 是否包含 "This is because/due to" 原因解释
- [ ] 7. 是否验证了理论推导（理论vs仿真比较）
- [ ] 8. 评价词是否准确（superior/robust/significant 优先；**"better" 本身不是错误**——语料大量使用 "provides better outage probability"，仅提示可升级用词）
- [ ] 9. **图描述时态是否为现在时**（"Fig. X plots..."；"Fig. X plotted" 判 🟡 错误；仿真过程描述过去时可选）
- [ ] 10. 是否避免单纯数据罗列
- [ ] 11. 是否包含深度分析手法（多因模式 "Another reason is that" / trade-off "does not necessarily translate" / 双面论证 "On the one hand... On the other hand" / 子图联合 "The main variation is that"，**任选其一即可**——均为低频手法，不要求全部出现）
- [ ] 12. 子场景是否按 A/B/C 或按图组织（💡 语料多篇实证 "A. Outage Probability / B. Ergodic Rate / C. System Throughput"）

## 常见致命问题（14 项全映射）
| 问题 | 触发检查项 | 严重性 |
|------|-----------|:------:|
| 无仿真参数表 | #2 | 🔴 |
| 图分析<4句 | #5 | 🟡 |
| 无原因解释 | #6 | 🟡 |
| 无理论-仿真对照 | #7 | 🟡 |
| 无任何基准方案 | #3 | 🔴 |
| 图描述用过去时（plotted） | #9 | 🟡 |
| 无标准开头 | #1 | 🟡 |
| 图未被 Fig. X 引用 | #4 | 🟡 |
| 单纯数据罗列 | #10 | 🟡 |
| 评价词模糊（good 类密集） | #8 | 🟢 |
| 无深度分析手法（多因/trade-off/双面/子图联合均无） | #11 | 🟢（低频手法，缺失不致命） |
| 子场景无组织 | #12 | 🟢 |
| 无多因解释 | #11a | 🟢（低频，非独立必查） |
| 无 trade-off 讨论 | #11b | 🟢（低频，非独立必查） |
