# Abstract 润色规范（深度蒸馏版）

> 基于课题组语料特征的摘要润色规范，含案例库、对比示例和决策树。
> **v1.2.0**：首句模式修正（技术主语式/被动式均为合法开头，不强制改写）；词数口径统一 85-280。

## 一、润色重点（按优先级）
1. **5要素完整性**：背景→问题→方法→结果→意义（要素 B 问题句与 E 意义句为可选，约 10-20% 与 5-15% 论文包含）
2. **结果编号规范**：i)/1) 无括号编号格式、分号分隔、and 连接
3. **时态一致性**：全文一般现在时 + 现在完成时
4. **信息密度**：每句都有实质信息，删除冗余

## 二、常见问题案例库

### Q1：被动开头（💡 可改可不改）
❌ "In this paper, the performance of ASTARS-NOMA is studied."
✅ "This paper investigates the performance of ASTARS-NOMA networks."
> 注：语料中被动式开头（"A two-way relay NOMA system is investigated"）为合法变体，非硬性错误；仅在 moderate 及以上深度建议改写。

### Q2：缺少方法细节（moderate）
❌ "This paper studies the outage probability of RIS-NOMA."
✅ "This paper investigates the outage probability of RIS-NOMA networks, where we derive closed-form expressions of SOP for users with ipSIC/pSIC."
> 注：补充方法细节须基于用户已提供的内容（用户在正文/其他章节有该方法），不得凭空虚构。

### Q3：结果模糊（moderate）
❌ "Numerical results show that the proposed system has good performance."
✅ "Numerical results demonstrate that: i) The proposed scheme achieves higher SE compared to OMA; ii) With increasing elements, the outage probability reduces significantly."
> 注：语料摘要 0 数值，"30% higher" 类具体数值若用户未提供不得编造；性能比较（superior to/outperforms）为 100% 覆盖模式。

### Q4：编号结果格式错误（light）
❌ "Numerical results show: 1) X outperforms Y, 2) Z is better."
✅ "Numerical results demonstrate that: i) X outperforms Y; ii) Z is significantly improved; and iii) the trade-off between A and B is revealed."
> 注：i) 与 1) 均可（无括号）；"(i)(ii)(iii)" 括号形式语料不存在。

### Q5：缺结果编号（moderate）
❌ "Simulation results verify the correctness and show that the proposed system is superior."
✅ "Simulation results verify the correctness of the theoretical analyses and demonstrate that: i) X outperforms Y; ii) ...; and iii) ..."

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
  ├─ 首句是否属于语料合法开头？（"This paper investigates/proposes" 约 43% / 技术主语式 "X has attracted growing interest" / 被动式 "A X system is investigated" / "Although..." 让步式约 5%）
  │   └─ 是 → 保留（不强制改写；语料无唯一标准开头）
  │   └─ 否且首句明显口语化/非学术 → 改写为学术化开头 (light)
  ├─ 是否包含方法细节（we derive/propose/formulate）？
  │   └─ 否且用户已提供方法 → 补充方法句 (moderate)；用户未提供 → 标注待补并询问
  ├─ 方法句是否为"总-分"结构展开？
  │   └─ 如用 "More specifically" 展开细节 → 更优 (moderate)
  ├─ 结果是否以 i)/1) 无括号编号列出？
  │   └─ 否 → 改为编号列表（结果内容不增删） (moderate)
  ├─ 缩略语首次出现是否已定义？
  │   └─ 否 → 添加全称定义 (light)
  ├─ 词数是否在85-280范围内？（典型 130-260）
  │   ├─ 过长(>280) → 删除冗余句 (deep，仅删冗余不删技术信息)
  │   └─ 过短(<85) → 与用户确认后补充方法/结果细节 (deep，新增须授权)
  └─ 时态是否统一（现在时）？
      └─ 否 → 统一时态 (light)
```

## 五、批量检查自动规则

- [✅] 首句动词：是否为 "investigates/proposes/introduces" 或技术主语式/被动式/让步式（语料合法开头之一）
- [✅] "Numerical results" / "Simulation results" / "Simulation findings" 短语：是否出现在结果句之前
- [✅] 结果引出词是否多样化（show/demonstrate/indicate/verify/confirm/manifest）
- [✅] 编号格式：是否使用 i)/1) 无括号编号（不用 (i)(ii)(iii)）
- [✅] 比较动词是否多样（outperform/exceed/superior to/precede）
- [✅] 缩略语检测：每个全大写词首次出现前是否已有全称
- [✅] 词数统计：85-280 词（典型 130-260）
- [✅] 时态检测：是否包含过去时动词（描述论文内容不应出现）
- [✅] 方法动词检测：是否至少包含一个 "we propose/derive/formulate"
- [💡] 方法展开是否使用 "More specifically" / "To be specific" 等过渡词
