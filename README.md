# Humanize Coding Agents

Make coding agents sound like competent teammates, not report generators.

`humanize-coding-agents` is an Agent Skill for implementation updates, debugging, code review, code explanations, comments, commits, and PR descriptions. It removes generic, over-structured AI prose without hiding uncertainty or cutting technical detail.

## Before and after

Before:

> I have completed a comprehensive analysis of the retry mechanism. The implementation is generally robust, but there are several areas that could potentially benefit from further improvement.

After:

> Retries lose the original error in `worker.go:84`, so the final failure only reports `context deadline exceeded`. Preserve the first error and add a three-attempt regression test.

The second version makes a claim, points to the relevant code, explains the consequence, and stops.

## What it changes

- Answers the question before explaining the process.
- Replaces generic judgments with code, behavior, evidence, and consequences.
- Makes a recommendation when the evidence supports one.
- Separates verified facts, inference, assumptions, and unknowns.
- Uses only as much structure as the answer needs.
- Keeps material failures, risks, and untested areas visible.

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
