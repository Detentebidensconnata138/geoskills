# geoskills — AI Agent Guide

## Repository Overview

geoskills is a **multi-skill monorepo** for Generative Engine Optimization (GEO). Each skill follows the open [AgentSkills](https://agentskills.io) standard and is compatible with Claude Code, OpenCode, OpenClaw, Codex CLI, Cursor, GitHub Copilot, and other AgentSkills-compatible agents.

## Directory Structure

```
geoskills/
├── .gitignore
├── CLAUDE.md                       ← You are here
├── README.md                       # Monorepo-level docs
├── LICENSE
├── package.json
├── skills/
│   ├── geo-audit/                  # Full GEO audit skill
│   │   ├── SKILL.md                # Skill definition (frontmatter + prompt)
│   │   ├── README.md               # Skill documentation
│   │   ├── references/             # Scoring rubrics, data & subagent definitions
│   │   │   ├── scoring-guide.md
│   │   │   └── agents/             # Subagent instruction files
│   │   │       ├── geo-technical.md
│   │   │       ├── geo-citability.md
│   │   │       ├── geo-schema.md
│   │   │       └── geo-brand.md
│   │   └── evals/                  # Evaluation test cases
│   │       └── evals.json
│   ├── geo-fix-llmstxt/            # llms.txt generator skill
│   │   ├── SKILL.md
│   │   ├── README.md
│   │   └── references/
│   │       └── llmstxt-spec.md     # llms.txt specification reference
│   └── geo-fix-schema/             # JSON-LD schema generator skill
│       ├── SKILL.md
│       ├── README.md
│       └── references/
│           └── schema-templates.md # JSON-LD template patterns
└── raw/                            # Research data (not a skill)
```

## Skill Internal Structure

Every skill under `skills/` MUST follow this structure:

```
skills/<skill-name>/
├── SKILL.md          # Required — skill definition with frontmatter
├── README.md         # Required — human-readable documentation
├── references/       # Optional — scoring guides, rubrics, subagent instructions
│   └── agents/       # Optional — subagent instruction files
├── scripts/          # Optional — executable helper scripts
└── evals/            # Optional — evaluation test cases
    └── evals.json
```

### SKILL.md Conventions

- **Frontmatter** is YAML between `---` fences at the top
- Required fields: `name`, `description`
- Recommended fields: `version` (semver, e.g., `1.0.0`)
- `name` MUST match the directory name (e.g., `skills/geo-audit/` → `name: geo-audit`)
- `description` should include trigger phrases (20-40 words), use "Use when..." pattern
- Body contains the full system prompt for the skill
- Body MUST use tool-agnostic natural language (no platform-specific tool names like `WebFetch`, `Bash`, `Agent`)

### Subagent Instruction Files (references/agents/*.md)

- Each file defines one subagent's instructions
- Frontmatter fields: `name`, `description`
- `name` format: `geo-<domain>` (e.g., `geo-technical`, `geo-citability`)
- Body contains the subagent's system prompt with scoring rubrics
- Instructions must be tool-agnostic (no platform-specific tool names)

## Writing Style Guide

- **Tone**: Professional, technical, concise
- **Audience**: Developers and SEO professionals
- **Formatting**: Use tables for structured data, code blocks for examples
- **Scoring**: Always use 0-100 scale with sub-dimension breakdowns
- **References**: Cite research sources when making claims
- **No emojis** unless explicitly part of a UI element

## Git Workflow

- Branch naming: `feat/<skill-name>-<description>`, `fix/<skill-name>-<description>`
- Commit messages: Conventional Commits format (`feat:`, `fix:`, `docs:`, `refactor:`)
- One skill per PR when adding new skills
- Always update root README "Available Skills" table when adding a new skill

## Adding a New Skill

1. Create `skills/<skill-name>/` directory
2. Add `SKILL.md` with proper frontmatter (`name`, `description`, `version`)
3. Add `README.md` with skill documentation
4. Add `references/`, `scripts/`, `evals/` as needed
5. Subagent instructions go in `references/agents/` (not a top-level `agents/` dir)
6. Update root `README.md` Available Skills table
7. Update this file's directory structure diagram
