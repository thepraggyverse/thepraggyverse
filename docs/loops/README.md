# Thepraggyverse Loops

This file defines repeatable agent loops for Thepraggyverse.
Loops are not big prompts. They are bounded operating procedures with triggers, context, verification, and stop rules.

## Loop Principles

- Every loop must say what it is trying to accomplish.
- Every loop must say how success is verified.
- Every loop must have a budget or stop condition.
- Every loop must say when to ask the owner for help.
- Loops should save what worked into the right durable doc.
- Workers execute. The orchestrator coordinates. Workers should not recursively spawn more workers.

## Loop Inventory

| Loop | Trigger | Reads | Writes | Verifier | Budget | Stop / Ask For Help |
| --- | --- | --- | --- | --- | --- | --- |
| Project orchestrator | Owner asks for status or next step | Root docs, handoffs, plans | `docs/handoffs/orchestrator.md` | Owner decision | One turn | Missing permission or unclear phase |
| Quality loop | Owner asks for feature/test/defect sweep | Code, docs, `docs/qa/` | `docs/qa/` ledgers | Tests, live checks, autoreview | Bounded pass | Missing setup, credentials, or risky fix |

## Loop Types

### Goal

A goal is a bounded objective with a clear done condition.

Use for one substantial outcome:

```text
Run the repo-quality-loop for this repo in report-only mode.
Discover features, propose test cases, identify defects, and recommend the safest first fix.
Do not edit code until I authorize remediation.
```

### Loop

A loop repeats a small cycle until a stop condition is hit.

Use for quality, review, validation, or follow-up:

```text
Repeat: inspect one feature, add/update its ledger row, identify missing tests, run available verification, record defects.
Stop after one bounded pass or when blocked by setup/access.
```

### Routine

A routine is a recurring maintenance action.

Use only when the owner explicitly asks for an automation or reminder.

```text
Every weekday morning, run report-only repo triage and prepare a decision brief.
Do not push, comment, merge, close, or release.
```

## Anti-Spin Rules

- Stop after repeated no-progress iterations.
- Stop when the next action needs product direction, credentials, paid services, public mutation, destructive operations, or release approval.
- Do not rewrite tests to hide failures.
- Do not expand scope because the loop discovered interesting adjacent work.
- Report remaining risk plainly.

## Closeout Format

Use this compact format for long-running loops:

```text
Changed:
Broke:
Tested:
Next:
```
