# Thepraggyverse Opinions

This file captures durable product and engineering judgment for Thepraggyverse.
It is project-local taste, not a task list.

Use it when an agent needs to make choices about product feel, tradeoffs, language, or quality without asking the owner to repeat themselves.

## How To Use

- Read this file before product, UX, architecture, or copy decisions.
- Treat these opinions as defaults, not absolute law.
- If an opinion conflicts with `AGENTS.md`, the active requirements doc, the active plan, or an explicit user instruction, follow the more specific instruction.
- Do not add one-off ideas, transient TODOs, raw prompts, or implementation recipes here.
- Update this file only when a durable preference, principle, or tradeoff becomes clear.

## Product Beliefs

- Preserve the smallest useful product loop before adding adjacent systems.
- Make user-facing behavior understandable without hidden project history.
- Prefer clear language over clever language.
- Keep private/local-first defaults unless the owner explicitly reopens scope.

## Engineering Taste

- Prefer boring, inspectable implementation choices until the product loop proves value.
- Prefer quality, simplicity, robustness, scalability, and long-term maintainability over short-term development cost.
- Do not introduce paid APIs, broker integrations, cloud dependencies, live-money flows, or credentialed external systems unless explicitly authorized.
- Reproduce bugs in an end-user-like path before fixing when feasible.

## UX And Design Taste

- Build the actual usable workflow before decorative landing pages.
- Keep screens scannable, responsive, and accessible.
- Use `DESIGN.md` as the source of truth for visual language when UI exists.
- Treat visual regressions, awkward copy, layout overlap, and confusing empty/error states as real defects.

## Vocabulary

Document project-specific words here when they matter.

| Term | Use This Way | Avoid | Notes |
| --- | --- | --- | --- |
| Example | Plain-language meaning | Confusing synonym | Why it matters |

## Tradeoffs

Record durable tradeoffs here.

| Decision Area | Prefer | Avoid | Reason |
| --- | --- | --- | --- |
| Example | Local-first flow | Hosted dependency too early | Keeps early iteration private and cheap |

## Changed Views

If the project changes direction, preserve the old view and why it changed.

| Date | Old View | New View | Reason |
| --- | --- | --- | --- |

<!-- BEGIN PRAGGY LOOP GUARDRAILS -->
## Praggy Loop Guardrails

- Prefer controlled loops over one-off giant prompts.
- Prefer quality, simplicity, robustness, scalability, and long-term maintainability over short-term development cost.
- Treat lint failures, flaky tests, broken checks, and visual regressions as real signals even when they look adjacent to the requested task.
- Reproduce bugs through the closest end-user path before fixing when feasible.
- Do not manually edit generated files, generated changelogs, lockfile output, or build artifacts unless the repo explicitly expects that edit.
- Do not add coauthor trailers, attribution, or public-facing metadata unless the owner asks.
- Prefer one complete sentence per physical line in long-form markdown.
<!-- END PRAGGY LOOP GUARDRAILS -->
