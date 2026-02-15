# Validation SOP — Testing the AI-Native Workflow

## Objective

Validate the core thesis: can a human provide structured context + requirements, then let AI design and execute autonomously, with significantly less human time than the current workflow?

## Test Setup

Pick a real feature/requirement from an existing business project. Non-trivial but bounded scope.

## Step 1: Prepare Context Docs (15-30 min)

Write 3 short documents:

### Doc A — Repo Architecture (~200 words)
- Tech stack and key frameworks
- Directory structure and what lives where
- Core patterns/conventions the codebase follows
- Key modules and their responsibilities (one line each)

### Doc B — Product Context (~300 words)
- What the product does, who it's for
- Current state: what works, what doesn't
- Business constraints that affect technical decisions

### Doc C — This Requirement (~200 words)
- What you want to achieve (outcome, not implementation)
- Why it matters (motivation)
- Constraints and non-negotiables
- What "done" looks like

## Step 2: Launch Session

Open a new AI session. Provide Docs A/B/C. Include this prompt:

> You are an autonomous senior engineer on this project. Read the context docs thoroughly. Based on the requirement, design a complete technical solution. Make your own decisions on implementation details — only ask me if you've tried 2+ approaches and both failed, or if the decision has product-level implications. When your plan is ready, present: (1) what you'll build, (2) key technical decisions and why, (3) risks or tradeoffs I should know about. After I approve the plan direction, execute fully without checking in. Commit when done.

## Step 3: Measure

Track during the experiment:

| Metric | Target | What it tells you |
|--------|--------|------------------|
| Time before first AI question | >30 min | Context doc quality |
| Total AI questions | <3 | Autonomy level achieved |
| Human active time | <30% of normal | Workflow efficiency gain |
| Plan quality | Viable without major correction | AI's independent judgment |
| Code output | Runs and roughly works | End-to-end capability |

## Step 4: Evaluate

After the experiment, answer honestly:

1. Did the context docs give AI enough to work autonomously?
2. Where did it get stuck — context gap or capability gap?
3. Would old workflow have been faster for this specific task?
4. What would you change in the docs for next time?

## Failure Signals and Diagnosis

| Signal | Diagnosis |
|--------|-----------|
| AI asks >5 questions | Context docs too sparse |
| AI builds the wrong thing | Requirement doc was ambiguous |
| AI stuck on codebase specifics | Architecture doc missed key patterns |
| You keep wanting to intervene | Trust threshold not calibrated yet |

## Iteration

After the first run, update the context docs based on what was missing. Run a second experiment with a different feature. Compare metrics. The workflow is validated when you consistently hit the targets above across 3+ different features.
