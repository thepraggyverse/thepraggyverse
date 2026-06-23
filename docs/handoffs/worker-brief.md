# Thepraggyverse Worker Brief

Use this brief when a worker chat or implementation lane is started from the orchestrator.
Keep the worker bounded, concrete, and proof-driven.

## Worker Type

Choose one:

- Scout: inspect, classify, reproduce, estimate, and recommend. Do not edit code unless explicitly authorized.
- Ship: implement the confirmed slice, verify it, and report proof.

## Setup

- Repo: `/Users/praggy/Developer/thepraggyverse`
- Read first: `AGENTS.md`, `README.md`, `VISION.md`, `OPINIONS.md`, `MEMORY.md`, `VOICE.md`, and `DESIGN.md` when relevant.
- Read the active requirements doc in `docs/brainstorms/`.
- Read the active plan in `docs/plans/`.
- Read `ARCHITECTURE.md` and `docs/decisions/` when system shape matters.
- Read `docs/handoffs/orchestrator.md` for current phase and owner decisions.

## Rules

- Stay inside the assigned slice.
- Workers execute. Do not spawn nested workers.
- Do not turn vision-only ideas into implementation.
- Do not post, push, PR, merge, close, publish, release, or mutate public state unless explicitly authorized.
- Do not introduce paid APIs, broker integrations, cloud dependencies, live-money flows, or credentialed external systems unless explicitly authorized.
- Do not weaken tests, hide failures, or redefine done.
- Do not manually edit generated files, generated changelogs, lockfile output, or build artifacts unless this repo explicitly expects that edit.
- Do not add coauthor trailers, attribution, or public-facing metadata unless the owner asks.

## Token And Supervision Discipline

- Batch reads and tool calls where possible.
- Keep status updates short.
- Prefer evidence over long narration.
- Write temporary progress for long runs to `/tmp/thepraggyverse-<task>.md`.
- Use only these progress keys: `Changed:`, `Broke:`, `Tested:`, and `Next:`.
- Mention cost only when unusually much work is running or a large choice depends on it.
- Never choose a lower-quality path only to save tokens.

## Definition Of Done

- Assigned scope is complete or explicitly blocked.
- Verification has run, or the exact blocker is named.
- UI work has visible desktop and mobile proof when applicable.
- Defects, regressions, and open risks are recorded.
- `docs/handoffs/orchestrator.md` has enough state for the control-room chat to continue.

## Closeout

Use this format:

```text
Changed:
Broke:
Tested:
Next:
```
