# Code Simplifier Skill

An OpenAI Codex skill for simplifying and refactoring recently changed code
without changing behavior.

This Codex version is inspired by Anthropic's public
[code-simplifier agent prompt](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/code-simplifier/agents/code-simplifier.md),
but is written as a standalone Codex skill.

It helps Codex run a surgical cleanup pass:

- Preserve exact functionality.
- Scope changes to the current diff, recently touched files, or named files.
- Follow repository-specific rules before generic preferences.
- Prefer clarity over cleverness or fewer lines.
- Verify behavior with the narrowest meaningful checks.

## Use cases

- Simplify code after a feature or bug fix.
- Refactor touched files for readability.
- Run a final code quality pass before review.

## Install

Copy the skill directory into your Codex skills folder:

```bash
mkdir -p ~/.codex/skills
cp -R code-simplifier ~/.codex/skills/
```

Then invoke it in Codex:

```text
Use $code-simplifier to simplify my recent code changes without changing behavior.
```

## Contents

```text
code-simplifier/
├── SKILL.md
└── agents/
    └── openai.yaml
```

## License

MIT
