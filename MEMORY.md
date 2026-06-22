# Thepraggyverse Memory

This file is durable project memory for Thepraggyverse.
It records stable facts an agent should not have to rediscover.

It is not a progress log, not a backlog, and not a replacement for requirements or plans.

## How To Use

- Read this file before large edits, handoffs, QA loops, or repo triage.
- Add only stable facts, decisions, constraints, and verified project knowledge.
- Do not store secrets, private user data, raw transcripts, temporary TODOs, or generated runtime data.
- Do not use this file to track day-to-day progress. Use `docs/handoffs/orchestrator.md` or a temporary `/tmp/<project>-<task>.md` log instead.

## Stable Project Facts

- Project name: Thepraggyverse
- Project slug: thepraggyverse
- Project type: app
- Default location: `/Users/praggy/Developer/thepraggyverse`

## Owner Defaults

- Report-only unless action is explicitly authorized.
- No push, PR creation, public comment, merge, close, release, or destructive operation unless explicitly authorized for that item.
- Keep private/local-first defaults until scope is reopened.
- Treat `VISION.md` as direction, not implementation permission.

## Important Paths

| Path | Purpose |
| --- | --- |
| `AGENTS.md` | Agent rules |
| `README.md` | Current overview and commands |
| `VISION.md` | Long-term direction |
| `OPINIONS.md` | Project-local durable taste and tradeoffs |
| `DESIGN.md` | Visual system and UX guardrails |
| `docs/handoffs/orchestrator.md` | Control-room state |
| `docs/qa/` | Feature, test, defect, and regression ledgers |
| `docs/loops/` | Repeatable loop definitions |

## Known Commands

Update once the stack exists.

```bash
# install

# run

# verify
```

## Known Constraints

- Application code is gated on requirements, a plan, and user confirmation.
- Large new ideas go to `VISION.md` first, then requirements, then a plan.
- Remediation work should be tied to a documented defect or confirmed plan.

## Open Questions

- What is the smallest useful v1 loop?
- Which workflows must be proven with live or end-to-end testing?
- Which parts of the project should remain private even if the repo becomes public?
