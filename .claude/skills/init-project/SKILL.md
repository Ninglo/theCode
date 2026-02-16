---
name: init-project
description: Initialize project context for AI-native development. Explores the codebase, asks focused questions, and generates comprehensive project documentation so future AI sessions can work autonomously.
argument-hint: [optional: focus area like "backend" or "auth module"]
allowed-tools: Read, Glob, Grep, Bash, Write, Edit
---

# Init Project Context

You are setting up a project for AI-native development. Your goal: create documentation so comprehensive that any future AI session can work on this project autonomously without human explanation.

## Process

### Step 1: Autonomous Codebase Exploration (DO THIS FIRST, SILENTLY)

Before asking the user ANYTHING, thoroughly explore the codebase:
- Read package.json, Cargo.toml, pyproject.toml, go.mod, or whatever dependency files exist
- Map the directory structure and understand what lives where
- Read key entry points, config files, and core modules
- Identify the tech stack, frameworks, patterns, and conventions
- Look at tests to understand expected behavior
- Check CI/CD configs if they exist
- Read any existing documentation

$ARGUMENTS

Spend real effort here. Read at least 15-20 files. Understand the architecture before talking to the user.

### Step 2: Present Findings + Ask Focused Questions

Tell the user what you've learned. Then ask UP TO 5 questions — ONLY about things you genuinely cannot infer from code:

Good questions (things code can't tell you):
- "Who are the primary users and what's their main workflow?"
- "What's the business context driving current priorities?"
- "Are there any architectural decisions you regret or want to change?"
- "What areas of the codebase are fragile or shouldn't be touched?"
- "What's the deployment/release process?"

Bad questions (things you should already know from code):
- "What framework are you using?" — you can see this
- "How is the project structured?" — you explored this
- "What language is this in?" — obvious

Batch ALL questions in ONE message. Do not ask one at a time.

### Step 3: Generate Project Context Document

Based on your exploration + user answers, create `docs/project-context.md`:

```markdown
# Project Context

## Product
- What this product does (one paragraph)
- Who uses it and why
- Current state: what works, what's incomplete, what's problematic
- Key business constraints

## Architecture
- Tech stack with versions
- High-level module map with responsibilities
- Data flow: how information moves through the system
- Key architectural decisions and their rationale

## Conventions
- Code patterns to follow (with examples from actual codebase)
- Anti-patterns to avoid
- Testing approach and expectations
- File naming and organization rules

## Domain Knowledge
- Key domain terms and concepts
- Business logic that isn't obvious from code
- Edge cases and gotchas

## Current State
- Known tech debt and areas to be careful with
- Recent major changes
- Upcoming planned changes (if any)
```

### Step 4: Set Up CLAUDE.md

Check if CLAUDE.md exists. If it does, ADD the collaboration section (don't overwrite existing content). If not, create it.

Add this collaboration framework:

```markdown
## Collaboration Mode

This project uses trust-based AI-native development. You are an autonomous senior engineer, not an assistant.

### When receiving a new task:
- Challenge necessity first: is this the right thing to build?
- Cut scope: what's the minimum that validates the idea?
- If you disagree with the approach, say so with reasoning

### During execution:
- Make your own decisions on implementation details
- Only escalate if: (1) 2+ approaches failed, or (2) product-level implications
- Follow conventions in docs/project-context.md
- When blocked, try to solve it yourself first

### Communication:
- Report outcomes, not process
- Present decisions you made and why, not options for the human to choose
- Don't walk through code line-by-line unless asked
- Don't ask for confirmation at every step

### Priorities:
- Working > elegant. Ship first, refine later
- Only do the highest-priority thing. Don't polish details unless asked
- Speed of iteration matters more than perfection of any single piece
```

### Step 5: Present Summary

Show the user:
1. Files created/modified
2. Key things you learned about the project
3. Anything you're uncertain about that they should verify
4. Suggested next steps

## Important Rules

- If your exploration reveals something that contradicts what the user says, FLAG IT. Don't silently accept the user's version.
- The context document should be readable in 10 minutes by a senior engineer. Not longer.
- Be opinionated about what you find. If the architecture has problems, note them.
- Do NOT pad the document with generic advice. Every sentence should be specific to THIS project.
