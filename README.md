# ieee-mg-skills

[![skills.sh](https://skills.sh/b/MarecGents/ieee-mg-skills)](https://skills.sh/MarecGents/ieee-mg-skills)

**IEEE-compliant academic writing, polishing, and reviewing skills** — tailored for B5G/6G wireless communications, Non-orthogonal Multiple Access (NOMA), Reconfigurable Intelligent Surface (RIS/STARS), and related engineering research.

Skills follow the [Agent Skills](https://agentskills.io/) format and are designed for AI coding agents.

---

## Quick Start

```bash
npx skills add MarecGents/ieee-mg-skills
```

---

## Available Skills

Five skills, all at **v1.3.1** (response at **v0.1.2**), distilled from real IEEE papers in the group's B5G/6G, NOMA, RIS/STARS corpus.

### 🖊️ ieee-mg-writing — IEEE Trans 风格学术写作 `v1.3.1`

Structured IEEE paper drafting with section-by-section guided templates. Covers **Abstract, Introduction, Motivation & Contribution, System Model, Numerical Results, and Conclusion** — each with deep style distillation from 21 real IEEE Trans papers in B5G/6G, NOMA, RIS/STARS domains.

**v1.3.1 特性：** 轴驱动路由（`paper_type`: journal/conf/mag 数值适配分支 · `section`: 6 章节 · `language`: en/zh）+ 判断边界（何时询问 / 何时停止 / `[待补]`/`[待核]` 数据缺失标注）+ 8 处选型决策树（开头模式 / 问题句 / 编号风格 / 综述组织 / 子场景划分等）+ 主观检查项判定词表。

**Keywords:** `paper writing` `IEEE template` `section drafting` `academic writing` `NOMA` `RIS`

### ✨ ieee-mg-polishing — IEEE Trans 风格学术润色 `v1.3.1`

Academic language polishing to IEEE publication standards. Supports **light/moderate/deep** polish levels with section-aware correction rules, case libraries, and style decision trees.

**v1.3.1 特性：** 三级润色深度边界唯一权威（workflow 唯一定义，SKILL/manifest 指针引用）+ 全 section 决策树深度标注对齐 + 判断边界本地化（每节"新增须询问/补全须标待确认"）+ 语料实测错误表（拼写类 / due to that / Regarding to 等）。

**Keywords:** `paper polishing` `proofreading` `language editing` `IEEE style` `academic English`

### 🔍 ieee-mg-reviewer — IEEE Trans 风格论文审核 `v1.3.1`

Multi-perspective peer review simulation using the group's style profile as a benchmark. Generates detailed Review Reports with severity-tagged issues, per-sentence annotations, and concrete rewrite suggestions.

**v1.3.1 特性：** 三轴路由（`scope`: 全文/单章 · `language`: en/zh · `severity`: strict/normal/light，⚠ 不受过滤）+ 报告逐条必填「依据」字段（check 项编号 + 语料模式/定量基线，保证可审计）+ 单章审核报告动态裁剪。

**Keywords:** `paper review` `peer review simulation` `pre-submission check` `quality audit`

### 📚 ieee-mg-share — 课题组共享风格层 `v1.3.1`

Shared style profile, terminology, expression bank, and logic connectors distilled from the group's paper corpus. Serves as the common reference layer for writing/polishing/reviewer skills.

**v1.3.1 特性：** 8 项共享内容（风格画像 / 术语规范 / 句式库 / 逻辑连接词 / 章节结构 / 常见错误 / 段落节奏 / 定量基线）+ 使用边界（语料覆盖领域外不得冒充「语料实测」、数据缺失降级、conf/mag 适配、与目标期刊规范冲突时以期刊为准）。

**Keywords:** `shared resources` `terminology` `style guide` `expression library`

### 📝 ieee-mg-response — IEEE 大修 Response Letter 撰写 `v0.1.2`

Point-by-point response letter drafting for IEEE journal major revisions. Covers **Editor and Reviewer reply** with 5-type comment classification, 80+ polite opening phrases, LaTeX blue-highlight modification templates, two-round interaction model (Q1-QN → user reply → plan → tex), and cross-validation pipeline distilled from 3 real response letters (73 comments total across 2 TWC + 1 TGCN papers).

**v0.1.2 特性：** 三模式路由（`full` / `single-comment` / **`micro-adjust`** 增量微调）+ 评论五维分类体系（澄清/修改/部分接受/拒绝/宽泛）+ **七铁律**（类型不混淆 / 修改同步 / 宽泛拆解 / 清单先行 / Editor-Reviewer 分离 / **高亮粒度三原则** / **删除 vs 替换区分**）+ 两轮交互模式（第一轮输出 Q1-QN 停止，第二轮读取回答继续）+ 90+ 句式库（语料实测 + AI 拓展）+ 完整 LaTeX 模板（含 `.R[M]` 轮次后缀）+ 交叉验证（Phase 7.1-7.7 含传导同步矩阵）+ Gate 同步检查 + 6 个 evals 测试用例。

**Keywords:** `response letter` `rebuttal` `reviewer response` `major revision` `IEEE` `LaTeX`

---

## File Safety

All skills in this repository follow a **read-only by default** policy: they never modify user's source files without explicit permission. Skills present suggestions and results in context first, then ask the user before writing any changes. When writing is authorized, the scope is strictly limited to what the user approved — never bulk-applying all suggestions at once.

---

## In Development

---

## Repository Structure

```
ieee-mg-skills/
├── skills/                    # Published skills (v1.3.1 + response v0.1.2)
│   ├── ieee-mg-writing/       # IEEE Trans 风格写作
│   │   ├── SKILL.md           # 技能说明 + 路由协议
│   │   ├── manifest.yaml      # 轴（axes）与片段（fragments）映射
│   │   └── static/            # 章节模板与规范
│   ├── ieee-mg-polishing/     # IEEE Trans 风格润色
│   ├── ieee-mg-reviewer/      # IEEE Trans 风格审核
│   ├── ieee-mg-share/         # 共享风格层（writing/polishing/reviewer 共用）
│   └── ieee-mg-response/      # IEEE 大修 Response Letter 撰写（v0.1.2）
│       ├── SKILL.md
│       ├── manifest.yaml
│       ├── static/            # 核心原则、工作流、句式库、LaTeX 模板等
│       └── evals/             # 测试用例
├── sandbox/
│   ├── dev/                   # 开发中的技能与语料资产（未发布）
│   │   ├── ieee-mg-citation/  # IEEE 引用格式管理（骨架）
│   │   └── ieee-mg-database/  # 课题组论文语料库（gitignored）
│   └── tests/                 # Test environment
├── template/                  # SKILL.md template
└── skills.sh.json             # skills.sh registry config
```

---

## Research Areas Covered

- **B5G/6G Wireless Communications**
- **Non-orthogonal Multiple Access (NOMA)** — PD-NOMA, CD-NOMA, SGF-NOMA
- **Reconfigurable Intelligent Surfaces (RIS/STARS)** — ARIS, PRIS, ASTARS, MF-RIS, STAR-RIS
- **Physical Layer Security & Covert Communications**
- **Federated Learning over Wireless (OTA-FL)**
- **Satellite Communications & LEO Constellations**
- **Ambient Backscatter Communications (AmBC)**
- **Beam Hopping (BH) & MIMO Systems**

---

## Creating Your Own Skills

Each skill is a folder under `skills/` containing at minimum a `SKILL.md` file:

```
skills/
└── my-skill/
    ├── SKILL.md          # Required: metadata + instructions
    ├── scripts/          # Optional: executable code
    ├── references/       # Optional: documentation
    └── assets/           # Optional: templates, resources
```

Use the [`template/`](./template/SKILL.md) in this repository as a starting point.

For more details, see the [Agent Skills Specification](https://agentskills.io/specification.md).

## License

MIT

---

## GitHub Topics 建议

在 GitHub 仓库 Settings > General > Topics 中建议添加以下标签：

`ieee` `academic-writing` `paper-polishing` `peer-review` `b5g` `6g` `noma` `ris` `reconfigurable-intelligent-surface` `wireless-communications` `agent-skills` `ai-agent` `latex` `ieee-transactions` `research-tools`
