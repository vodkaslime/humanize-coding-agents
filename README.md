# Humanize Coding Agents

Make coding agents sound like competent human teammates.

![A friendly coding agent in front of flowing code with the message “Here’s what matters — in plain language.”](assets/readme-hero.jpg)

`humanize-coding-agents` is an Agent Skill for implementation updates, debugging, code review, code explanations, comments, commits, and PR descriptions. It removes generic, over-structured AI prose without hiding uncertainty or cutting technical detail.

## Before and after

Before:

> The configuration subsystem implements a sophisticated, multi-layered resolution paradigm in which input sources are dynamically reconciled through a precedence-aware normalization process, enabling context-sensitive values to propagate seamlessly across the application while preserving flexible override semantics.

After:

> `resolveConfig()` reads the user settings first, then the repository settings, and finally the command-line flags. Each step overwrites matching values from the previous one, so `--timeout 30` takes priority over both configuration files.

The second version states the precedence rule, follows the data through the code, and shows one concrete result.

## What it changes

- Answers the question before explaining the process.
- Replaces generic judgments with code, behavior, evidence, and consequences.
- Rewrites empty contrasts, dramatic closers, and mechanical symmetry at the level of the underlying claim instead of swapping flagged words.
- Makes a recommendation when the evidence supports one.
- Separates verified facts, inference, assumptions, and unknowns.
- Uses only as much structure as the answer needs.
- Keeps material failures, risks, and untested areas visible.
- Checks rewritten prose against the original facts, confidence, causality, scope, and exact technical literals.

The skill does not manufacture a human voice with slang, fake anecdotes, deliberate roughness, or banned-word lists. Its working definition of natural prose is simpler: make a situated judgment for this reader and this repository.

## Install

### Codex

Clone the repository into the Codex skills directory:

```bash
git clone https://github.com/vodkaslime/humanize-coding-agents.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/humanize-coding-agents"
```

### Other Agent Skills clients

Clone or copy the repository into the skills directory configured by your client. The entry point is [`SKILL.md`](SKILL.md).

## Use

Invoke the skill explicitly with `$humanize-coding-agents`:

```text
Use $humanize-coding-agents to explain how this queue handles retries.
```

```text
Use $humanize-coding-agents to review this PR and report only actionable findings.
```

```text
Use $humanize-coding-agents to rewrite this implementation update without losing test results or risks.
```

## Scope

The skill includes separate guidance for:

- plans, progress updates, and completion reports;
- code review and code explanations;
- commit messages and PR descriptions;
- comments, docstrings, TODOs, and architectural notes.

Detailed examples live in [`references/examples.md`](references/examples.md).

## License

Licensed under the [Apache License 2.0](LICENSE).
