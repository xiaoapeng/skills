# Repository Guidelines

## Purpose
This repository is a multi-skill Git repository for reusable AI skills. The primary target is compatibility with `npx skills add <owner>/<repo> --skill <name>`, while allowing the same skill contents to be reused by Codex, Claude Code, Gemini CLI, Cursor, Cline, and similar tools.

## Repository Layout
- Put each installable skill under `skills/<skill-name>/`.
- Every installable skill must include `SKILL.md` at the skill root.
- Use lowercase kebab-case for skill directory names, for example `git-commit-cn-helper`.
- Recommended per-skill layout:

```text
skills/<skill-name>/
├── SKILL.md
├── agents/openai.yaml
├── prompts/
├── references/
├── scripts/
└── assets/
```

Create only the subdirectories a skill actually needs.

## Installation Model
- `npx skills add <owner>/<repo>` can install from a Git repo when it can find a valid `SKILL.md`.
- `npx skills add <owner>/<repo> --skill <name>` works best when the repository uses `skills/<name>/SKILL.md`.
- `agents/openai.yaml` is useful for OpenAI/Codex UI metadata, but it is not the core requirement for `skills add`.

## Skill Authoring Rules
- Keep `SKILL.md` short and trigger-focused.
- Put tool-agnostic procedures in `prompts/` or `references/`.
- If a skill targets multiple AI tools, keep one shared prompt entry and use `SKILL.md` as the Codex/OpenAI adapter.
- Avoid duplicating long rule blocks across `SKILL.md`, `README.md`, and reference files.
- Use imperative wording and concrete triggers in `description`.

## Initial Validation
When adding or editing a skill, check:

- `SKILL.md` has valid YAML frontmatter with `name` and `description`.
- The skill folder name matches the skill name.
- Referenced files in `agents/openai.yaml` or prompts actually exist.
- The repository layout remains compatible with `skills/<skill-name>/`.

## Growth Plan
- Add one skill directory at a time under `skills/`.
- Prefer stable, descriptive names like `git-commit-cn-helper`, `frontend-design`, or `api-doc-writer`.
- Move reusable long-form material into `prompts/`, `references/`, `scripts/`, or `assets/` as a skill matures.
