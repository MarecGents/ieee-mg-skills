# Abstract 润色规范（深度蒸馏版）

> 基于课题组语料特征的摘要润色规范，含案例库、对比示例和决策树。

## 一、润色重点（按优先级）
1. **5要素完整性**：背景→问题→方法→结果→意义
2. **结果编号规范**：(i)(ii)(iii) 格式、分号分隔、and 连接
3. **时态一致性**：全文一般现在时 + 现在完成时
4. **信息密度**：每句都有实质信息，删除冗余

## 二、常见问题案例库

### Q1：被动开头 → 主动开头
❌ "In this paper, the performance of ASTARS-NOMA is studied."
✅ "This paper investigates the performance of ASTARS-NOMA networks."

### Q2：缺少方法细节
❌ "This paper studies the outage probability of RIS-NOMA."
✅ "This paper investigates the outage probability of RIS-NOMA networks, where we derive closed-form expressions of SOP for users with ipSIC/pSIC."

### Q3：结果模糊
❌ "Numerical results show that the proposed system has good performance."
✅ "Numerical results demonstrate that: i) The proposed scheme achieves 30% higher SE compared to OMA; ii) With increasing elements, the outage probability reduces significantly."

### Q4：编号结果格式错误
❌ "Numerical results show: 1) X outperforms Y, 2) Z is better."
✅ "Numerical results demonstrate that: i) X outperforms Y; ii) Z is significantly improved; and iii) the trade-off between A and B is revealed."

### Q5：缺结果编号
❌ "Simulation results verify the correctness and show that the proposed system is superior."
✅ "Simulation results verify the correctness of the theoretical analyses and demonstrate that: i) X outperforms Y by Z%; ii) ...; and iii) ..."

## 三、润色前后对比示例

### 示例 1
**Before**: "This paper introduces STAR-RIS to NOMA networks. The performance is studied. Simulation results show the proposed system is better."
**After**: "This paper introduces STAR-RIS to assist NOMA communications, where pairing users are uniformly distributed. We derive new approximate expressions of outage probability with ipSIC/pSIC. Numerical results demonstrate that: i) STAR-RIS-NOMA outperforms STAR-RIS-OMA in outage probability; and ii) the system throughput of STAR-RIS-NOMA is superior to that of OMA."

### 示例 2
**Before**: "In this article, a new system is proposed. We derive the outage probability. Results show good performance."
**After**: "This article proposes a relay satellite assisted LEO constellation NOMA combined beamforming communication system. We formulate the resource allocation problem and jointly optimize the satellite-cell assignment, NOMA power, and BF vector. Numerical results show that: i) the proposed algorithms are superior to OMA-based schemes; and ii) with increasing antennas, user satisfaction is expanded."

## 四、润色决策树

```
检查摘要 →
  ├─ 首句是否为主动语态开头或让步转折结构？
  │   └─ 模式A: "This paper investigates/proposes" (标准)
  │   └─ 模式B: "Although... + To address these issues" (让步转折)
  │   └─ 都不是 → 改写为模式A或B (light)
  ├─ 是否包含方法细节（we derive/propose/formulate）？
  │   └─ 否 → 补充方法句 (moderate)
  ├─ 方法句是否为"总-分"结构展开？
  │   └─ 如用 "Specifically/More precisely" 展开细节 → 更优 (moderate)
  ├─ 结果是否以(i)(ii)(iii)编号列出？
  │   └─ 否 → 改为编号列表 (moderate)
  ├─ 结果前是否有总起句？
  │   └─ 如用 "The simulation results verify the correctness and yield the following insights:" → 更优 (moderate)
  ├─ 缩略语首次出现是否已定义？
  │   └─ 否 → 添加全称定义 (light)
  ├─ 词数是否在85-280范围内？（中位数~175）
  │   ├─ 过长(>280) → 删除冗余句 (deep)
  │   └─ 过短(<90) → 补充方法/结果细节 (deep)
  └─ 时态是否统一（现在时）？
      └─ 否 → 统一时态 (light)
```

## 五、批量检查自动规则

- [ ] 首句动词：是否为 "investigates/proposes/introduces/studies" 或 "Although..." 让步转折
- [ ] "Numerical results" / "Simulation results" / "Simulation findings" 短语：是否出现在结果句之前
- [ ] 结果引出词是否多样化（show/demonstrate/indicate/verify/confirm/manifest）
- [ ] 编号格式：是否使用 (i)(ii)(iii) 或 1)2)3)
- [ ] 比较动词是否多样（outperform/exceed/superior to/precede）
- [ ] 缩略语检测：每个全大写词首次出现前是否已有全称
- [ ] 词数统计：100-250 词
- [ ] 时态检测：是否包含过去时动词（不应出现）
- [ ] 方法动词检测：是否至少包含一个 "we propose/derive/formulate"
- [ ] 方法展开是否使用 "More specifically" / "To be specific" 等过渡词
