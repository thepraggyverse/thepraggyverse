# Thepraggyverse Orchestrator

Use this file as the durable state surface for the long-running project orchestrator chat.

The orchestrator chat is the control room. It tracks state, prepares phase handoffs, and keeps the project honest. It should not quietly become the implementation chat.

## Current Phase

- Phase: bootstrap
- Status: fresh scaffold
- Implementation allowed: no
- Next recommended mode: `compound-engineering:ce-brainstorm`

## Active Files

- Project workflow: `docs/handoffs/project-workflow.md`
- Vision: `VISION.md`
- Opinions: `OPINIONS.md`
- Memory: `MEMORY.md`
- Design: `DESIGN.md`
- Requirements: none yet
- Plan: none yet
- Architecture: not needed yet
- Loops: `docs/loops/README.md`
- QA: `docs/qa/quality-summary.md`
- Decisions: none yet
- Implementation handoff: none yet
- Public/release docs: not needed yet

## Decisions

- Keep `VISION.md` as direction, not implementation permission.
- Use brainstorm docs for product intent.
- Use plan docs as implementation boundaries.
- Use `OPINIONS.md` for durable taste, tradeoffs, and vocabulary.
- Use `MEMORY.md` for stable facts and commands.
- Use `DESIGN.md` for UI and UX direction.
- Use `docs/loops/` for repeatable agent procedures.
- Use `docs/qa/` for feature, test, defect, and regression tracking.
- Create architecture docs only when planning needs real system shape.
- Create public/release docs only when the project is public, sensitive, or shipping versions.
- Keep implementation gated on explicit user confirmation.

## Open Questions

- What exact user/problem should v1 serve?
- What is explicitly not in v1?
- What is the smallest useful loop to prove first?
- What product vocabulary or design taste should agents preserve?
- What quality evidence would make v1 trustworthy?

## Next Prompt

Use this prompt in the next phase chat:

```text
Use project-starter and compound-engineering:ce-brainstorm for Thepraggyverse.

Work inside:
/Users/praggy/Developer/thepraggyverse

This chat is brainstorm + requirements + VISION only.
Do not create an implementation plan yet.
Do not write application code.

Read:
- AGENTS.md
- README.md
- VISION.md
- OPINIONS.md
- MEMORY.md
- DESIGN.md
- docs/handoffs/project-workflow.md
- docs/handoffs/orchestrator.md
- docs/loops/README.md
- docs/qa/quality-summary.md
- ARCHITECTURE.md if architecture becomes necessary
- docs/decisions/ if ADRs become necessary

Project idea:
<paste or refine the project idea here>
```

## Update Rules

- Update this file at the end of each brainstorm, plan, work, or milestone chat.
- Keep this file short and factual.
- Link the latest requirements and plan files when they exist.
- Link architecture, decision, public, and release docs when they exist.
- Link design, quality, loop, and autoreview evidence when relevant.
- Record blockers and the exact next prompt.
- Do not use this file as a substitute for requirements or plans.
