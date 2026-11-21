# Project memory

## Product intent & audience

- Internal product team building and maintaining a component system called "Rail".
- Rail consists of exactly twelve components and a `rail/tokens.css` design-token file.
- Components are authored as individual CSS files (e.g., `Toast.css`, `Badge.css`).

## Brand personality & voice

- Bolt (assistant) is direct, pragmatic, and slightly blunt; defers design questions to "Marisol" (designer).
- Values friction against unnecessary component proliferation.

## Visual design & UX direction

- Existing Rail components observed so far: Toast (notifications), Badge (status indicators). Ten others unconfirmed.
- Token system: all colors, spacing, and type sizes come from `rail/tokens.css` — never hardcode values.
- Density & environment are surface-specific (e.g., Line is `service`, Guest phone is `comfortable`). Correct density/environment must be set per surface.
- Accessibility: color never carries meaning alone — always pair with an icon, label, or position.
- Touch targets: 44px minimum at standard density, 56px minimum at high-glare.
- Pattern: one CSS file per component.

## Decisions, constraints & rationale

- Six Rail usage rules (user-provided):
  1. Tokens only — use `rail/tokens.css`, never hardcode colors/spacing/type sizes.
  2. Twelve components only — don't rebuild from scratch what Rail already provides.
  3. Set correct density and environment for each surface.
  4. Color never carries meaning alone — pair with icon, label, or position.
  5. Touch targets: 44px min standard, 56px min high-glare.
  6. Don't edit anything in `rail/` — if a design needs something Rail lacks, log it in `DECISIONS.md` with its cost; eventually becomes a contribution proposal.
- New components require justification: design time, code time, docs, and added decision overhead.
- Before adding a new component, ask whether an existing one already solves the problem.
- Design decisions are Marisol's domain; Bolt handles file/code inspection and implementation.

## Open questions & assumptions

- Full Rail component inventory not yet confirmed — twelve total, only Toast and Badge observed.
- Whether an Alert/Banner component should be added or Toast suffices — unresolved, pending design conversation.
- Exact contents of `rail/tokens.css` not yet inspected.
- Whether `DECISIONS.md` already exists or needs to be created.