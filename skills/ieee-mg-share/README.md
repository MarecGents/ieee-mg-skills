# ieee-mg-share — MarecGents 课题组共享学术风格层

## 用途

本技能是 **ieee-mg-writing** 和 **ieee-mg-polishing** 的公共组件层。所有两个技能共用的语料蒸馏成果（全局风格画像、术语规范、句式库、逻辑连接词、章节结构定义）集中存放于此，避免重复维护。

## 架构关系

```
ieee-mg-database/     ← 原始语料（你的材料）
    ↓ (蒸馏)
ieee-mg-share/        ← 共享层（风格画像、术语、句式、结构）
    ↓          ↓           ↓
ieee-mg-writing/  ieee-mg-polishing/  ieee-mg-reviewer/
(写作专用模板)   (润色专用规范)     (审核清单)
```

## 文件说明

| 文件 | 内容 |
|------|------|
| `manifest.yaml` | 共享轴定义（paper_type / section / language） |
| `static/style-profile.md` | 全局风格画像（正式度、句式、时态、高频词汇、连接词、数学规范） |
| `static/terminology.md` | 术语规范（缩略语规则、核心术语、信道模型、数学符号） |
| `static/expression-bank.md` | 通用句式库（引用、空白、贡献、结果、过渡等7类句式） |
| `static/logic-connectors.md` | 逻辑连接词详细指南（因果/转折/递进/举例/结论，含频率和例句） |
| `static/section-architecture.md` | 各章节标准结构定义（仅结构模板，不含写作指导） |
| `static/common-errors.md` | 常见语言错误与纠正（polishing 使用） |
| `static/paragraph-rhythm.md` | 段落节奏与过渡指南（polishing 使用） |
| `static/quantitative-baseline.md` | 定量分析基线参考（reviewer 使用） |

## 使用方式

ieee-mg-writing、ieee-mg-polishing 和 ieee-mg-reviewer 的 SKILL.md 在路由协议中应增加 Step 0：
> "加载 ieee-mg-share 的 style-profile.md 和 terminology.md，建立共享风格基准。"

相关技能文件的 manifest.yaml 中的 fragment 路径应指向 ieee-mg-share/static/。
