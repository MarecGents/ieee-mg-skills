# ieee-mg-skills

[![skills.sh](https://skills.sh/b/MarecGents/ieee-mg-skills)](https://skills.sh/MarecGents/ieee-mg-skills)

A curated collection of Agent Skills for IEEE-compliant academic paper writing, polishing, reviewing, and data management — tailored for high-impact engineering journal submissions.

Skills follow the [Agent Skills](https://agentskills.io/) format and are designed for AI coding agents.

## Installation

```bash
npx skills add MarecGents/ieee-mg-skills
```

## Available Skills

*(Skills are under development — check back soon.)*

This repository will host the following skill families:

### IEEE MG Writing Pipeline

End-to-end skills for producing IEEE期刊-compliant manuscripts:

- **writing** — Structured IEEE paper drafting with section-by-section guided writing
- **polishing** — Academic language polishing to IEEE publication standards
- **reviewer** — Multi-perspective peer review simulation for pre-submission quality check
- **citation** — IEEE-compliant citation management and reference formatting
- **database** — Structured academic data management and experiment logging
- **share** — Shared terminology, expression banks, and reusable components

### Supporting Skills

- *(更多技能即将添加)*

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

## Sandbox (Skill Development Area)

`sandbox/` is a development sandbox isolated from the published `skills/` directory, allowing skill creation and testing without affecting released skills.

```
sandbox/
├── dev/              # Skills in development
│   └── my-skill/
│       ├── SKILL.md
│       ├── scripts/
│       └── references/
└── tests/            # Test environment
    ├── README.md
    └── fixtures/     # Optional: test data
```

### Workflow

1. **Develop** — Create new skills under `sandbox/dev/` following the skill specification
2. **Test** — Write and run test scripts in `sandbox/tests/`
3. **Publish** — Move the skill to `skills/` once it passes testing

## License

MIT