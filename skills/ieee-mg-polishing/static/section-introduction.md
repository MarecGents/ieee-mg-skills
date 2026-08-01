# Introduction 润色规范（深度蒸馏版）

> 基于课题组语料特征的引言润色规范，含案例库、对比示例和决策树。

## 一、润色重点
1. **5层架构完整性**：大背景→技术演进→文献综述(3块)→研究空白→贡献
2. **文献综述结构**：是否使用嵌套子节（### A. Previous Works 内嵌 1)2)3) 分类）
3. **引用表达多样性**：混合使用 "The authors in [x]"、"In [x]"、被动语态 "X was studied in [x]"
4. **引用密度**：技术演进段落每句至少1个引用，关键句可叠加2-3个
5. **贡献列表格式**：1)2)3)4) 编号是否正确
6. **研究空白句式**："To the best of our knowledge" 的准确使用
7. **符号说明段落**：如有大量数学符号，应包含 Notations 段落
8. **过渡手法多样化**：文献综述段内部避免连续 ≥3 句以 Meanwhile/Furthermore/Additionally/Moreover/Notably/In addition/Besides 等单词过渡词开头，交替使用自然承接、主题引导短语、引用开头、同位语嵌入等手法。详见 ieee-mg-share/static/paragraph-rhythm.md 第 4 节。

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
✅ 添加 "To the best of our knowledge, there is no existing work investigating X."（语料主流空白句式）

### Q5：单词过渡词综合征
❌ "Meanwhile, in [x], the authors investigated... Furthermore, the authors of [y] proposed... Additionally, a framework [z] was developed... Moreover, a hybrid architecture [w] was introduced..."
✅ "The channel characteristics were initially analyzed in [x]. To exploit spatial degrees of freedom, the authors of [y] proposed a novel scheme. At the system architecture level, a hybrid architecture [w] was introduced."

**诊断**：段落中 ≥3 句连续以递进/补充类单词过渡词开头，形成机械清单式叙述。应交替使用主题引导短语、自然承接、引用开头等手法（详见 paragraph-rhythm.md 第 4 节）。

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
  ├─ Layer 2: 引用密度是否足够（每句≥1个引用）？
  │   └─ 否 → 补充关键引用 (moderate)
  ├─ Layer 3: 文献综述是否按主题分类？
  │   └─ 否 → 重新组织文献引用 (moderate)
  ├─ Layer 3: 文献综述段内部过渡手法是否多样化（避免 ≥3 句连续单词过渡词）？
  │   └─ 否 → 重写过渡，交替使用自然承接/主题引导短语/引用开头/同位语嵌入 (moderate)
  ├─ Layer 3: 是否使用嵌套子节结构（### A/B/C + 编号1)2)3)）？
  │   └─ 否 → 建议使用嵌套分类 (moderate)
  ├─ Layer 4: 是否有 "To the best of our knowledge" 空白句？
  │   └─ 否 → 补充研究空白 (moderate)
  ├─ Layer 5: 贡献是否编号？
  │   └─ 否 → 改为 1)2)3)4) 列表 (light)
  ├─ 引用句式是否多样化？
  │   └─ 检查是否混用 "The authors in [x]"、"In [x]"、"X was studied" → 如单一则丰富 (light)
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
- [ ] 文献综述段内部过渡手法是否多样化（避免 ≥3 句连续单词过渡词）
