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

### 🖊️ ieee-mg-writing — IEEE Trans 风格学术写作

Structured IEEE paper drafting with section-by-section guided templates. Covers **Abstract, Introduction, Motivation & Contribution, System Model, Numerical Results, and Conclusion** — each with deep style distillation from 21 real IEEE Trans papers in B5G/6G, NOMA, RIS/STARS domains.

**Keywords:** `paper writing` `IEEE template` `section drafting` `academic writing` `NOMA` `RIS`

### ✨ ieee-mg-polishing — IEEE Trans 风格学术润色

Academic language polishing to IEEE publication standards. Supports **light/moderate/deep** polish levels with section-aware correction rules, case libraries, and style decision trees.

**Keywords:** `paper polishing` `proofreading` `language editing` `IEEE style` `academic English`

### 🔍 ieee-mg-reviewer — IEEE Trans 风格论文审核

Multi-perspective peer review simulation using the group's style profile as a benchmark. Generates detailed Review Reports with severity-tagged issues, per-sentence annotations, and concrete rewrite suggestions.

**Keywords:** `paper review` `peer review simulation` `pre-submission check` `quality audit`

### 📚 ieee-mg-share — 课题组共享风格层

Shared style profile, terminology, expression bank, and logic connectors distilled from the group's paper corpus. Serves as the common reference layer for writing/polishing/reviewer skills.

**Keywords:** `shared resources` `terminology` `style guide` `expression library`

---

## Repository Structure

```
ieee-mg-skills/
├── skills/                    # Published skills
│   ├── ieee-mg-writing/       # IEEE Trans 风格写作
│   ├── ieee-mg-polishing/     # IEEE Trans 风格润色
│   ├── ieee-mg-reviewer/      # IEEE Trans 风格审核
│   └── ieee-mg-share/         # 共享风格层
├── sandbox/
│   ├── dev/                   # Skills in development
│   │   ├── ieee-mg-database/  # Raw paper corpus (21 papers)
│   │   ├── ieee-mg-citation/  # Citation manager (WIP)
│   │   └── ...                # Other dev skills
│   └── tests/                 # Test environment
├── docs/                      # Audit reports and logs
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
