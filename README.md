# Skills Repository

This repository is organized as a multi-skill Git repo for AI tools that can install or reuse skills from GitHub.

## Layout

```text
skills/
  <skill-name>/
    SKILL.md
    agents/openai.yaml
    prompts/
    references/
    scripts/
    assets/
```

## Install

```bash
npx skills add <owner>/<repo> --skill <skill-name>
```

Example:

```bash
npx skills add <your-github-user>/skills --skill git-commit-cn-helper
```

Keep `SKILL.md` concise and move shared or tool-agnostic procedures into `prompts/` and `references/`.
