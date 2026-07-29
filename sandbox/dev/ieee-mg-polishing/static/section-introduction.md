# Introduction 润色规范（深度蒸馏版）

> 基于课题组语料特征的引言润色规范，含案例库、对比示例和决策树。

## 一、润色重点
1. **5层架构完整性**：大背景→技术演进→文献综述(3块)→研究空白→贡献
2. **引用表达多样性**：避免重复 "the authors in [x] investigated"
3. **贡献列表格式**：1)2)3)4) 编号是否正确
4. **研究空白句式**："To the best of our knowledge" 的准确使用

## 二、常见问题案例库

### Q1：背景太窄/太宽
❌ "RIS is a new technology for 6G."
✅ "RIS has been deemed as a cornerstone in the advancements toward 6G, promising substantial improvements in system capacity and coverage expansion [1]-[3]."

### Q2：文献综述未分类
❌ "Many works have studied RIS [1]-[15]."
✅ "1) RIS-NOMA Networks: The authors in [x] proposed... 2) STAR-RIS Networks: Prior works have demonstrated... 3) RIS-STARS Integration: Recent studies have shown..."

### Q3：贡献列表无编号
❌ "We propose a new system and derive the expressions."
✅ "The main contributions can be summarized as follows: 1) We propose... 2) We derive... 3) We investigate... 4) We demonstrate..."

### Q4：缺少研究空白
❌ 直接从文献综述跳到贡献列表
✅ 添加 "To the best of our knowledge, X has not been comprehensively explored in prior works."

## 三、润色前后对比

### 示例 1：文献综述分类优化
**Before**: "Several works studied security in NOMA [1]-[20]."
**After**: "Several works have investigated the security of NOMA networks. Focusing on external eavesdropping, the authors in [x] derived the SOP for NOMA. For internal eavesdropping, [y] analyzed the secrecy throughput. In addition, [z] investigated the impact of RIS on the secrecy performance."

### 示例 2：贡献列表格式化
**Before**: "We propose a new scheme. The expression is derived. Performance is analyzed."
**After**: "The main contributions are: 1) We propose a novel ASTARS-assisted NOMA framework; 2) We derive closed-form expressions of SOP; 3) We analyze the impact of ipSIC on secrecy diversity; and 4) We demonstrate that the proposed scheme outperforms benchmarks."

## 四、润色决策树
```
检查Introduction →
  ├─ Layer 1: 背景是否从宏观到微观？
  │   └─ 否 → 重写背景段 (deep)
  ├─ Layer 3: 文献综述是否按主题分类？
  │   └─ 否 → 重新组织文献引用 (moderate)
  ├─ Layer 4: 是否有 "To the best of our knowledge" 空白句？
  │   └─ 否 → 补充研究空白 (moderate)
  ├─ Layer 5: 贡献是否编号？
  │   └─ 否 → 改为 1)2)3)4) 列表 (light)
  ├─ 符号说明段是否存在？
  │   └─ 缺失且论文含大量数学符号 → 添加符号段 (moderate)
  └─ 引用格式是否统一为 IEEE 编号格式？
      └─ 否 → 统一引用格式 (light)
```

## 五、批量检查
- [ ] "To the best of our knowledge" 是否出现（≥1次）
- [ ] 贡献是否使用 1)2)3)4) 或 "first/second/third"
- [ ] 文献引用是否全是 IEEE 编号格式 [x], [x]-[y]
- [ ] 每个首次引用的缩略语是否已定义
- [ ] 论文组织段落是否存在（"The rest of this paper is organized..."）
