# theCode

AI-native development workflow as Claude Code skills. Stop reviewing code line-by-line. Start operating as a product owner.

## What This Is

Two Claude Code skills that restructure how you work with AI:

- **`/init-project`** — AI explores your codebase, asks you 5 focused questions, generates comprehensive project context docs. Future sessions start informed without explanation.
- **`/new-feature`** — Structured feature workflow: AI challenges the idea first, cuts scope, plans, then executes autonomously. You review outcomes, not process.

The core insight: model intelligence is no longer the bottleneck. Your cognitive load is. These skills shift you from "programmer who uses AI" to "product owner who delegates execution."

## Install

Copy the skills into your project:

```bash
# Clone this repo
git clone https://github.com/Ninglo/theCode.git

# Copy skills into your project
cp -r theCode/.claude/skills/init-project your-project/.claude/skills/
cp -r theCode/.claude/skills/new-feature your-project/.claude/skills/
```

Or with [gh-upskill](https://github.com/trieloff/gh-upskill):
```bash
gh extension install trieloff/gh-upskill
```

## Usage

### First time setup
```
/init-project
```
AI explores your codebase, asks focused questions, generates `docs/project-context.md` and sets up `CLAUDE.md` with trust-based collaboration principles.

### Building features
```
/new-feature add user authentication with OAuth
```
AI challenges the idea, proposes minimum scope, drafts a plan for your approval, then executes autonomously.

## Philosophy

- **Trust-based**: AI makes autonomous implementation decisions. You only engage on product-level choices.
- **Challenge-first**: AI argues against your idea before building it. Prevents wasted work.
- **Async-native**: AI works for extended periods without checking in. You pull updates when ready.
- **Speed over polish**: Ship working code, iterate later. Every task should be the current highest priority.

## Docs

- [Summary](docs/summary.md) — Full framework: thesis, workflow phases, operating principles
- [Validation SOP](docs/validation-sop.md) — How to test this workflow on your projects

## Status

Early prototype. Skills are functional. Looking for early adopters to validate and iterate.
