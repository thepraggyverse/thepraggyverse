# Thepraggyverse Project Workflow

Use this as the fresh-chat continuation prompt and phase contract for Thepraggyverse.

## New Project Start

First bootstrap the repo with:

```bash
new-project.sh "Thepraggyverse" app
```

Then work inside:

```text
/Users/praggy/Developer/thepraggyverse
```

Use this workflow:

Keep one long-running orchestrator chat for this project. The orchestrator chat is the project control room: it tracks phase, decisions, latest docs, blockers, and the next handoff in `docs/handoffs/orchestrator.md`.

Default to separate execution chats by phase unless the user explicitly asks to continue in one chat:

- Orchestrator chat: coordinates the project and updates `docs/handoffs/orchestrator.md`.
- Brainstorm chat: bootstrap, `ce-brainstorm`, requirements, and `VISION.md` only.
- Plan chat: `ce-plan` only, ending at user confirmation.
- Work chat: `ce-work` only after the plan is confirmed.

At the end of each execution chat, update `docs/handoffs/orchestrator.md` and return to the orchestrator chat with the next recommended prompt. The orchestrator chat should remind the user when the next phase belongs in a fresh chat.

1. Use `compound-engineering:ce-brainstorm` in the first chat.
   - Explore the product.
   - Ask clarifying questions one at a time.
   - Write requirements under `docs/brainstorms/`.
   - Capture durable product taste, vocabulary, and tradeoffs in `OPINIONS.md` when they appear.
   - Capture stable project facts in `MEMORY.md` when they appear.
   - Do not write application code.

2. Create or update `VISION.md` after requirements are captured in the first chat.
   - Capture the long-term north star.
   - Capture roadmap horizons.
   - Capture safety and philosophy.
   - Capture deferred ideas.
   - Capture what is explicitly not in v1.
   - Treat `VISION.md` as direction, not implementation scope.
   - Create or update a handoff in `docs/handoffs/` telling the next chat to run `ce-plan`.
   - Update `docs/handoffs/orchestrator.md` with current phase, latest docs, open questions, and next prompt.

3. Use `compound-engineering:ce-plan` in the next chat.
   - Read `AGENTS.md`, `README.md`, `VISION.md`, `OPINIONS.md`, `MEMORY.md`, `DESIGN.md` when UI is involved, and the requirements doc.
   - Create a structured implementation plan under `docs/plans/`.
   - Create or update root `ARCHITECTURE.md` only if the next slice needs real system structure.
   - Create or update `DESIGN.md` before UI implementation when visual direction matters.
   - Decide the smallest useful implementation slice.
   - Do not implement code.
   - Stop and wait for user confirmation.
   - Create or update a handoff in `docs/handoffs/` telling the next chat to run `ce-work` only after confirmation.
   - Update `docs/handoffs/orchestrator.md` with the active plan, confirmation status, blockers, and next prompt.

4. Use `compound-engineering:ce-work` in a later chat only after the user confirms the plan.
   - Implement only the confirmed plan.
   - Keep changes scoped.
   - Run verification.
   - Run an autoreview-style closeout after non-trivial code changes when available.
   - Report changed files, tests, blockers, and next steps.
   - Update `docs/handoffs/orchestrator.md` with implementation status, verification, and next milestone options.

Do not write application code until:

- `AGENTS.md` exists.
- `README.md` exists.
- `VISION.md` exists.
- `OPINIONS.md` exists.
- `MEMORY.md` exists.
- `DESIGN.md` exists.
- Requirements are captured.
- An implementation plan is written.
- The user confirms the plan.

## Brainstorm Only

Use this in the brainstorm execution chat. This phase is for product shaping only.

Read first:

- `AGENTS.md`
- `README.md`
- `VISION.md` if it exists
- `OPINIONS.md` if it exists
- `MEMORY.md` if it exists

Output:

- Write the requirements doc under `docs/brainstorms/`.
- If long-term ideas come up, create or update `VISION.md` instead of putting all future ambition into v1 requirements.
- If durable taste, tradeoffs, vocabulary, or owner preferences come up, create or update `OPINIONS.md`.
- If stable facts, constraints, commands, or verified project knowledge come up, create or update `MEMORY.md`.
- Create or update a handoff in `docs/handoffs/` for the next chat to run `ce-plan`.
- Update `docs/handoffs/orchestrator.md`.
- Remind the user: this chat was brainstorm/planning prep only; implementation has not started.
- Do not write application code.

## Plan From Requirements

Use this in the plan execution chat. This phase is for planning only.

Read first:

- `AGENTS.md`
- `README.md`
- `VISION.md`
- `OPINIONS.md`
- `MEMORY.md`
- `DESIGN.md` if UI is involved
- Requirements: `docs/brainstorms/<requirements-file>.md`

Use `VISION.md` for direction, but plan only the next confirmed implementation slice. Do not turn roadmap ideas into current work unless the requirements explicitly include them.

Output:

- Write the plan under `docs/plans/`.
- If the slice has meaningful system structure, create or update root `ARCHITECTURE.md` using `/Users/praggy/Developer/templates/ARCHITECTURE.template.md` as the shape.
- If the slice changes UI or UX, create or update `DESIGN.md` before implementation.
- If the plan makes an important hard-to-reverse architecture choice, add an ADR under `docs/decisions/`.
- Stop and wait for user confirmation.
- Create or update a handoff in `docs/handoffs/` for the next confirmed implementation chat.
- Update `docs/handoffs/orchestrator.md`.
- Remind the user: `ce-work` should start in a fresh chat after plan confirmation.
- Do not write application code.

## Work From Plan

Use this in a work execution chat, only after the user confirms the plan.

Read first:

- `AGENTS.md`
- `README.md`
- `VISION.md`
- `OPINIONS.md`
- `MEMORY.md`
- `DESIGN.md` if UI is involved
- Requirements: `docs/brainstorms/<requirements-file>.md`
- Plan: `docs/plans/<plan-file>.md`

Treat the plan as the implementation boundary. Do not implement vision-only ideas.

Output:

- Implement only the confirmed plan.
- Update root `ARCHITECTURE.md` only if the implementation changes the actual system shape.
- Update `DESIGN.md` only if the implementation changes the actual visual or UX system.
- Update `MEMORY.md` only with durable verified facts, not progress.
- Add or update ADRs in `docs/decisions/` only for important hard-to-reverse choices.
- Run verification.
- Run autoreview after non-trivial code changes when available.
- Report changed files, tests, blockers, and next steps.
- Update `docs/handoffs/orchestrator.md`.

## Orchestrator Chat

Use the orchestrator chat to keep continuity across the whole project.

Read first:

- `AGENTS.md`
- `README.md`
- `VISION.md`
- `OPINIONS.md`
- `MEMORY.md`
- `DESIGN.md`
- `docs/handoffs/project-workflow.md`
- `docs/handoffs/orchestrator.md`
- Latest relevant docs in `docs/brainstorms/` and `docs/plans/`
- `docs/loops/` and `docs/qa/` when validation or recurring work is involved

The orchestrator chat may:

- Track current phase and next action.
- Decide whether the next phase should be brainstorm, plan, or work.
- Prepare the exact prompt for a fresh phase chat.
- Record links to latest requirements, vision, plans, verification, blockers, and decisions.
- Track latest OPINIONS, MEMORY, DESIGN, loop, QA, and autoreview evidence when relevant.
- Track optional maturity docs such as `ARCHITECTURE.md`, `docs/decisions/`, `ROADMAP.md`, `CHANGELOG.md`, `SECURITY.md`, and `LICENSE`.
- Remind the user when implementation is not allowed yet.

The orchestrator chat must not quietly become the work chat. Do not run `ce-work` or implement code from the orchestrator unless the user explicitly confirms that this chat should switch into work mode.

## Architecture

Architecture is conditional. Do not create architecture docs before requirements exist.

Create or update root `ARCHITECTURE.md` during `ce-plan` when the project has meaningful structure, such as:

- App layers or multiple modules.
- Data model or persistence.
- Auth, privacy, storage, sync, background jobs, or deployment.
- Provider integrations, APIs, external services, or automation.
- Cross-platform or frontend/backend boundaries.

Use architecture as explanation, not permission. If architecture implies new product behavior, update requirements first. If architecture implies implementation work, update the plan first.

Use `docs/decisions/` for ADR-style notes only when a choice is important and hard to reverse.

## Design

`DESIGN.md` is conditional but first-class. Keep it at the project root so agents see it quickly.

Create or update `DESIGN.md` during brainstorm or planning when:

- The project has user-facing screens.
- A UI change needs visual direction.
- The owner references a design style, product, screenshot, or brand.
- Existing UI quality is inconsistent enough that future agents need design guardrails.

Use design as visual direction, not permission to implement UI beyond the active plan. If design implies new behavior, update requirements first. If design implies implementation work, update the plan first.

## Quality Loop

Use `repo-quality-loop` when the project needs a feature, test, defect, or regression sweep.

Read first:

- `AGENTS.md`
- `README.md`
- `VISION.md`
- `OPINIONS.md`
- `MEMORY.md`
- `DESIGN.md` when UI is involved
- `ARCHITECTURE.md` when present
- active requirements and plans
- `docs/qa/`

Default mode is report-only. The quality loop may discover features, propose test cases, execute safe local checks, and record defects in `docs/qa/`. It may not remediate defects unless the user authorizes remediation or a confirmed plan covers the fix.

After a non-trivial remediation pass, run verification and autoreview when available, then update `docs/handoffs/orchestrator.md`.

## Opinions And Memory

- Use `OPINIONS.md` for durable taste, vocabulary, tradeoffs, and recurring owner preferences.
- Use `MEMORY.md` for stable project facts, constraints, commands, and verified knowledge.
- Do not use either file as a progress tracker.
- If a public article, screenshot, or reference reveals a durable preference, distill the preference rather than pasting the source.

## Next Milestone Planning

Read first:

- `AGENTS.md`
- `README.md`
- `VISION.md`
- `OPINIONS.md`
- `MEMORY.md`
- `DESIGN.md` when UI is involved
- Existing docs in `docs/brainstorms/`
- Existing docs in `docs/plans/`
- Existing docs in `docs/loops/` and `docs/qa/` when relevant

If the milestone changes long-term direction, update `VISION.md`.
If it changes product behavior, write or update a requirements doc.
If it changes product taste or vocabulary, update `OPINIONS.md`.
If it creates stable facts or commands, update `MEMORY.md`.
If it changes visual direction, update `DESIGN.md`.
If it is ready to build, write a plan.
Update `docs/handoffs/orchestrator.md`.
Do not implement until the user confirms.

## Open Source Release Guard

Before publishing this project as open source, create or update `CONTRIBUTING.md` and `.github/pull_request_template.md`.

If bootstrapping a new public repo, use:

```bash
new-project.sh "Thepraggyverse" app --open-source
```

If converting an existing private project to public, make sure contribution docs clearly state:

- What can merge by default.
- What needs maintainer sign-off.
- Which roadmap ideas are still `Later` or `Not V1`.
- Which privacy, auth, storage, dependency, release, or integration changes need explicit approval.

Do not treat stars, forks, issues, or drive-by PRs as permission to expand scope. `VISION.md` remains direction. `CONTRIBUTING.md` is the public contribution boundary. New public work still needs requirements, a plan, and maintainer confirmation when it crosses the sign-off boundary.

Public/release maturity docs:

- `LICENSE`: create only after the user chooses the license.
- `SECURITY.md`: create when the project is public, handles user data/secrets, or needs vulnerability reporting.
- `CHANGELOG.md`: create when shipping named versions or releases.
- `ROADMAP.md`: create when public upcoming work becomes too detailed for `VISION.md`.

Use these optional templates when creating maturity docs:

- `/Users/praggy/Developer/templates/ROADMAP.template.md`
- `/Users/praggy/Developer/templates/CHANGELOG.template.md`
- `/Users/praggy/Developer/templates/SECURITY.template.md`

Do not template `LICENSE`; ask the user to choose a license and use the canonical license text.

## Add AGENTS.md To Existing Repo

If the project has or needs long-term direction, create or reference `VISION.md`.

Document how files work together.

Use the safe retrofitter for missing docs:

```bash
/Users/praggy/Developer/scripts/retrofit-project-contract.sh <repo>
```

After review and authorization:

```bash
/Users/praggy/Developer/scripts/retrofit-project-contract.sh --write <repo>
```

The retrofitter creates missing docs only and never overwrites existing files.

Root files are high-signal orientation or public/release files:

- `VISION.md` = long-term direction
- `README.md` = current overview and commands
- `AGENTS.md` = agent rules
- `OPINIONS.md` = durable project taste and tradeoffs
- `MEMORY.md` = stable project facts
- `DESIGN.md` = visual and UX source of truth
- `CONTRIBUTING.md` = public contribution boundaries when open source
- `ARCHITECTURE.md` = current/planned system shape when structure is non-trivial
- `ROADMAP.md` = public sequenced upcoming work when needed
- `CHANGELOG.md` = release history when shipping versions
- `SECURITY.md` = vulnerability reporting/security policy when public or sensitive
- `LICENSE` = project license after user choice

`docs/` contains working project memory:

- `docs/brainstorms/` = requirements
- `docs/plans/` = implementation plans
- `docs/decisions/` = hard-to-reverse architecture decisions
- `docs/loops/` = repeatable agent loops
- `docs/qa/` = quality ledgers and regression state
- `docs/handoffs/` = orchestrator state and fresh-chat prompts

## Mental Model

- `VISION.md` = where this could go.
- `OPINIONS.md` = how this project should think and feel.
- `MEMORY.md` = facts agents should not rediscover.
- `DESIGN.md` = how the UI should look and behave.
- `ce-brainstorm` = what we mean.
- `ce-plan` = how to build the next slice.
- `ce-work` = build only the confirmed slice.
- `repo-quality-loop` = discover, test, record defects, fix only with permission, and regress.
