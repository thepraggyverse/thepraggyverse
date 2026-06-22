# Thepraggyverse Design

This file is the agent-readable design system for Thepraggyverse.
Agents should read it before creating or changing UI.

If this project has no UI yet, keep this file as a placeholder and fill it during planning before visual implementation.

## Design Intent

- Product mood:
- Audience:
- Density:
- Platform feel:
- What the UI should make easy:
- What the UI should never feel like:

## Visual Theme And Atmosphere

Describe the overall feel in plain language.

- Surfaces:
- Motion:
- Imagery:
- Icon style:
- Data density:

## Color Palette And Roles

| Token | Hex | Role | Usage |
| --- | --- | --- | --- |
| `background` | `#ffffff` | Page background | Replace when design is chosen |
| `foreground` | `#111111` | Primary text | Replace when design is chosen |
| `accent` | `#2563eb` | Primary action | Replace when design is chosen |

## Typography Rules

| Role | Size | Weight | Line Height | Usage |
| --- | --- | --- | --- | --- |
| Page title | 32 | 700 | 1.15 | Main page heading |
| Section title | 20 | 600 | 1.25 | Section labels |
| Body | 16 | 400 | 1.5 | Normal reading text |
| Caption | 13 | 400 | 1.35 | Secondary details |

## Component Rules

Document expected styling and states for common components.

- Buttons:
- Inputs:
- Navigation:
- Cards:
- Tables/lists:
- Empty states:
- Error states:
- Loading states:

## Layout Principles

- Breakpoints:
- Spacing scale:
- Grid:
- Page width:
- Mobile behavior:
- Touch target minimum:

## Depth And Elevation

- Shadow rules:
- Border rules:
- Layering rules:
- Modal/popover behavior:

## Interaction Rules

- Primary action behavior:
- Keyboard behavior:
- Hover/focus behavior:
- Animation limits:

## Accessibility Rules

- Preserve semantic HTML or native platform semantics.
- Keep contrast, focus states, labels, and error messages visible.
- Do not rely on color alone to communicate state.
- Verify keyboard and screen-reader paths when relevant.

## Do And Do Not

| Do | Do Not |
| --- | --- |
| Build the real workflow first | Hide missing behavior behind marketing copy |
| Keep text within its container | Let labels overlap controls |
| Verify mobile and desktop | Assume responsive behavior from desktop only |

## Reference Styles

Add references only when they genuinely express the intended direction.

| Reference | Why It Matters | What To Borrow | What To Avoid |
| --- | --- | --- | --- |

## Agent Prompt Guide

When asking an agent to build UI, include:

```text
Read DESIGN.md first.
Preserve the design intent, tokens, component rules, responsive behavior, and accessibility rules.
If the UI request conflicts with DESIGN.md, call out the conflict before implementing.
```
