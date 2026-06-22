# Hi, I'm Praggy

## Project Overview

- Path: `/Users/praggy/Developer/thepraggyverse`
- Detected stack: docs/reference
- Summary: I am an indie dev building iOS apps, AI-assisted workflows, and small local-first tools. Most of my projects start as a personal itch: I build apps and tools to fix my own problems, then keep using them until they bec...

## Current Status

- local git checkout.
- markers: README.md.
- Existing local context should be treated as the source of truth before making product or architecture claims.

## Product or Tool Intent

- I am an indie dev building iOS apps, AI-assisted workflows, and small local-first tools. Most of my projects start as a personal itch: I build apps and tools to fix my own problems, then keep using them until they bec...
- Preserve the smallest working loop first: install/read the project, make one focused change, run the closest verification, and document what changed.
- If this is only a reference mirror, prefer documentation-only or clearly requested edits over broad source changes.

## Project Structure

```text
.
- README.md
```

Update this section when major folders are added or removed.

## Setup / Build / Test Commands

No standard build or test command was detected. Start by reading `README.md` and local scripts before inventing a workflow.

```bash
# no verified command detected yet
```

## Core Project Rules

- Read `README.md` and nearby docs before changing behavior.
- Follow the existing project shape and naming before adding new abstractions.
- Keep changes close to the requested behavior; avoid opportunistic rewrites.

## Ambition and Scope Discipline

- Keep ambition high, but execute in lake-sized slices: one concrete loop, one sharp prototype, one verified improvement. Capture bigger boil-the-ocean ideas in docs/brainstorms or docs/plans, then return to the current executable slice.
- Write down larger ideas instead of smuggling them into the current implementation pass.
- Prefer one complete, reviewed slice over several half-wired directions.

## Scope Boundaries / Do Not Build Yet

- Do not add production infrastructure, billing, auth, telemetry, external integrations, or deployment automation unless explicitly requested.
- Do not create networked/cloud behavior from a local-first prototype without a clear product decision.
- Do not rewrite imported upstream/reference material simply to match personal style.
- If the project purpose is unclear, make the smallest cautious doc or code change and call out the assumption in the handoff.

## Coding and UX Guidance

- Prefer boring, inspectable implementation choices until the core loop proves value.
- Keep user-facing copy concrete and avoid explaining implementation details in the UI.
- For skill/docs work, make instructions easy to scan and keep examples runnable or clearly marked as illustrative.

## Testing and Verification

- Run the narrowest meaningful verifier after changes.
- If verification cannot run, report the exact command attempted, the blocker, and what remains unverified.
- For generated docs-only changes, at minimum read the changed file back and check for wrong project names or copied irrelevant text.

## Security and Privacy Hygiene

- Do not commit secrets, tokens, cookies, private keys, personal data, or local-only credentials.
- Use `.env.example` or documented placeholders for required environment variables.
- Treat logs, transcripts, screenshots, and sample data as potentially sensitive until proven otherwise.

## Git / Commit / Review Expectations

- Check `git status --short --branch` before editing and before final handoff.
- Commit only files that belong to the requested change; keep unrelated local work intact.
- Use scoped, descriptive commit messages and do not push unless explicitly asked.
- For non-trivial changes, include files changed, commands run, verification results, blockers, and suggested next step.

## Agent Workflow Notes

- Start by reading this file, then `README.md`, then relevant docs or scripts.
- Prefer `rg`/`rg --files` for search and inspect real files before editing.
- Ask before changing protected config, credentials, release settings, generated artifacts, or external service behavior.
- If context grows large, write a short handoff with completed work, changed files, verification, blockers, and the exact next action.

<!-- BEGIN PRAGGY LOOP GUARDRAILS -->
## Praggy Loop Guardrails

- Treat `VISION.md` as direction, not implementation permission.
- Treat requirements as product intent and plans as implementation boundaries.
- Do not implement vision-only ideas until they become requirements, then a plan, then receive user confirmation.
- Treat lint failures, flaky tests, unrelated broken checks, visual regressions, layout overlap, and accessibility regressions as real signals. Report scope clearly instead of ignoring them.
- Do not manually edit generated files, generated changelogs, lockfile output, or build artifacts unless this repo explicitly expects that edit.
- Do not add coauthor trailers, attribution, or public-facing metadata unless the owner asks.
- In long-form markdown, prefer one complete sentence per physical line so review diffs stay clean.
- Autoreview, browser proof, lavish artifacts, and no-mistakes gates are evidence, not permission to push, PR, merge, release, publish, or comment publicly.
<!-- END PRAGGY LOOP GUARDRAILS -->
