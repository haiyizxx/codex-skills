# Codex Skills

A small collection of OpenAI Codex skills.

## Skills

- [Code Simplifier](code-simplifier/) - simplify and refactor recently changed
  code without changing behavior.
- [Karpathy Guidelines](karpathy-guidelines/) - keep coding-agent changes
  cautious, simple, surgical, and verifiable.

## Code Simplifier

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

Copy any skill directory into your Codex skills folder:

```bash
mkdir -p ~/.codex/skills
cp -R code-simplifier karpathy-guidelines ~/.codex/skills/
```

Then invoke a skill in Codex:

```text
Use $code-simplifier to simplify my recent code changes without changing behavior.
Use $karpathy-guidelines while making this code change.
```

## Contents

```text
karpathy-guidelines/
├── SKILL.md
└── agents/
    └── openai.yaml
code-simplifier/
├── SKILL.md
└── agents/
    └── openai.yaml
```

## License

MIT
