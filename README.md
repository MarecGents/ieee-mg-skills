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

Four skills, all at **v1.2.0**, distilled from 21 real IEEE Trans papers in the group's B5G/6G, NOMA, RIS/STARS corpus.

### 🖊️ ieee-mg-writing — IEEE Trans 风格学术写作 `v1.2.0`

Structured IEEE paper drafting with section-by-section guided templates. Covers **Abstract, Introduction, Motivation & Contribution, System Model, Numerical Results, and Conclusion** — each with deep style distillation from 21 real IEEE Trans papers in B5G/6G, NOMA, RIS/STARS domains.

**v1.2.0 特性：** 轴驱动路由（`paper_type`: journal/conf/mag 适配分支 · `section`: 6 章节 · `language`: en/zh）+ 判断边界（何时询问用户 / 何时停止 / 数据缺失降级，System Model 明确标注为外部通用知识）。

**Keywords:** `paper writing` `IEEE template` `section drafting` `academic writing` `NOMA` `RIS`

### ✨ ieee-mg-polishing — IEEE Trans 风格学术润色 `v1.2.0`

Academic language polishing to IEEE publication standards. Supports **light/moderate/deep** polish levels with section-aware correction rules, case libraries, and style decision trees.

**v1.2.0 特性：** 三级润色深度操作化边界（light 仅语法拼写 / moderate 句式用词 / deep 全面优化，均明确「能改/不能改」清单）+ 润色 vs 扩写边界（新增技术内容须询问用户）+ 语料实测错误表。

**Keywords:** `paper polishing` `proofreading` `language editing` `IEEE style` `academic English`

### 🔍 ieee-mg-reviewer — IEEE Trans 风格论文审核 `v1.2.0`

Multi-perspective peer review simulation using the group's style profile as a benchmark. Generates detailed Review Reports with severity-tagged issues, per-sentence annotations, and concrete rewrite suggestions.

**v1.2.0 特性：** 三轴路由（`scope`: 全文/单章 · `language`: en/zh · `severity`: strict/normal/light）+ 报告逐条必填「依据」字段（check 项编号 + 语料模式/定量基线，保证可审计）+ 单章审核报告动态裁剪。

**Keywords:** `paper review` `peer review simulation` `pre-submission check` `quality audit`

### 📚 ieee-mg-share — 课题组共享风格层 `v1.2.0`

Shared style profile, terminology, expression bank, and logic connectors distilled from the group's paper corpus. Serves as the common reference layer for writing/polishing/reviewer skills.

**v1.2.0 特性：** 8 项共享内容（风格画像 / 术语规范 / 句式库 / 逻辑连接词 / 章节结构 / 常见错误 / 段落节奏 / 定量基线）+ 使用边界（语料覆盖领域外不得冒充「语料实测」、数据缺失降级、conf/mag 适配、与目标期刊规范冲突时以期刊为准）。

**Keywords:** `shared resources` `terminology` `style guide` `expression library`

---

## Repository Structure

```
ieee-mg-skills/
├── skills/                    # Published skills (v1.2.0)
│   ├── ieee-mg-writing/       # IEEE Trans 风格写作
│   │   ├── SKILL.md           # 技能说明 + 路由协议
│   │   ├── manifest.yaml      # 轴（axes）与片段（fragments）映射
│   │   └── static/            # 章节模板与规范
│   ├── ieee-mg-polishing/     # IEEE Trans 风格润色
│   ├── ieee-mg-reviewer/      # IEEE Trans 风格审核
│   └── ieee-mg-share/         # 共享风格层（writing/polishing/reviewer 共用）
├── sandbox/
│   ├── dev/                   # 开发中的技能与语料资产（未发布）
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
