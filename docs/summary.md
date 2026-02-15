# AI-Native Development Workflow — Summary

## Core Thesis

Model intelligence is no longer the bottleneck. The bottleneck is the human's cognitive load — frequent context switches, information overload, and being pulled into implementation details that don't require human judgment. The workflow must be redesigned around **human cognitive ergonomics**, not model convenience.

## The Shift

Human moves from "programmer who uses AI" to "product owner who delegates execution." Human provides vision, motivation, and key constraints. AI executes autonomously. Human reviews outcomes, not process. The relationship is trust-based: as long as direction is correct, AI can make different detail-level choices than the human would.

## Workflow Phases

| Phase | Mode | Human Role | AI Role |
|-------|------|-----------|---------|
| 0. Context Loading | One-time heavy + ongoing | Write project knowledge into repo docs | Consume and internalize |
| 1. Idea + Challenge | Sync, focused | State idea and motivation | Challenge necessity, cut scope |
| 2. Alignment + Plan | Sync→Async | Review direction, not detail | Draft full plan with decisions |
| 3. MVP Execution | Async, autonomous | Don't review code | Code independently, self-verify |
| 4. Validation | Sync | Evaluate the product | Present results |
| 5. Production | Async + review | Review architecture and code quality | Full implementation with quality |

## Operating Principles

- **Trust-based delegation**: Accept AI making different choices on details. Only intervene on direction.
- **Human at decision nodes only**: Discussion, not instruction. The human is a partner, not a supervisor.
- **Speed over polish**: Ship first, refine only where ROI is clear. Every task should be the current highest priority.
- **Context-as-infrastructure**: Well-maintained project docs eliminate repeated explanation. One-time heavy investment, ongoing light maintenance.
- **Async-first**: Human pulls updates when ready. AI doesn't push interruptions except for true blockers.

## Key Risks Acknowledged

- Context docs need ongoing maintenance — they rot if treated as one-time
- Models won't genuinely challenge you unless explicitly engineered to (anti-sycophancy must be prompted)
- Cross-session coordination becomes a real problem at 10+ parallel streams
- "Trust the model completely" is overconfident — humans still own taste under ambiguity, cross-domain judgment, and knowing when the spec itself is wrong
- Feedback loops must be explicit: validation can invalidate the plan, MVP can reveal the idea was wrong
