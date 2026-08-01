# Motivation 润色规范（深度蒸馏版）

> 基于课题组语料的动机部分润色规范。承上启下开头→空白定位→贡献列表。
> **v1.2.0**：开头模式降级（While 类约 38%，非强制）；贡献点动作多样性 ≥3 类；"in their infancy" 语法提醒。

## 润色重点
1. **论证力度**：从已有工作到研究空白的过渡是否有说服力
2. **贡献点三层递进**：每个贡献点可包含 动作层→工具层→结论层（推荐非强制）
3. **贡献句式**：贡献点动作多样性 ≥3 类（提出/推导/分析/验证 推荐组合，顺序与数量可灵活）
4. **研究空白变体**：检查是否使用了多种空白句式（"there is/are no existing works" / "is not researched yet" / "has not been comprehensively explored" / "this paper is the first" 等）
5. **尖锐问题映射**：如有问题列表，每个问题是否与贡献点一一对应（约 10% 论文使用问题引导）
6. **对比表格**：Table I 格式和内容完整性（约 5% 论文使用，源自 FL 篇样例，非强制）

## 常见问题案例库

### Q1：动机不充分（moderate，基于用户已提供内容）
❌ "X is important. We study X."
✅ "While the aforementioned works have laid a solid foundation for understanding SGF-NOMA and STARS, the promising integration is still in its infancy. To the best of our knowledge, existing works are based on pSIC, which are difficult to realise in practice."
> 语法提醒：单数主语（integration）配 its，非 their；语料 "integration ... is still in their infancy" 为语法瑕疵，润色时纠正为 its。

### Q2：贡献点动词重复（light）
❌ "1) We propose... 2) We propose... 3) We propose..."
✅ "1) We propose... 2) We derive... 3) We analyze... 4) We demonstrate..."
> 注：动词多样性 ≥3 类即可；动作顺序不强制（语料实证 propose→derive→derive→derive 亦可，但润色时鼓励多样化）。

### Q3：贡献点没有结论句（💡 建议，非强制）
❌ "1) We propose a new scheme."
✅ "1) We propose a new scheme. Analytical results show that the diversity order is proportional to the number of elements."
> 注：语料部分贡献点无结论句（FL 篇第 3 点），此为建议非硬性。

### Q4：研究空白句式单一（light）
❌ 每篇都用同一种空白句式（如 "there is no existing work investigating X" 连续使用）
✅ 交替使用 "there is/are no existing works to investigate X"、"X is not researched yet"、"has not been comprehensively explored"、"This paper presents the first comprehensive analysis of X"（均为语料实测句式）

### Q5：问题-贡献不匹配（moderate）
❌ 问题列表和贡献点没有对应关系
✅ 问题1（技术挑战）→ 贡献1（建模与推导）；问题2（对比）→ 贡献2（对比分析）

## 润色前后对比

**Before**: "X has been studied by many works. We propose a new method. We also derive some expressions."
**After**: "While X has been extensively studied, the integration of X and Y is still in its infancy. To the best of our knowledge, this paper presents the first analysis of... The main contributions are: 1) We propose... 2) We derive... 3) We investigate... 4) We demonstrate..."

## 润色决策树
```
Motivation →
  ├─ 是否以承上启下模式开头（While/Although/前述综述回顾）？ → 否且开头突兀：建议添加过渡（moderate；非强制，语料约 38% 用 While）
  ├─ 是否有研究空白句（"To the best of our knowledge" 或变体）？ → 否：与用户确认空白后补充 (moderate)
  ├─ 空白句式是否多样化？ → 仅用一种：换用其他语料变体 (light)
  ├─ 贡献点是否≥3个？ → 否：提示用户（不凭空新增贡献点） (moderate)
  ├─ 贡献点动词是否多样化（≥3类）？ → 否：调整动词表达 (light)
  ├─ 每个贡献点是否含结论层？ → 否：💡 建议补充（非强制）
  ├─ 问题-贡献是否一一映射（如有问题列表）？ → 否：调整对应关系 (moderate)
  └─ Table I（如有）特征行是否覆盖关键维度？ → 否：建议扩充（源自 FL 篇样例，非强制） (moderate)
```
