# Project memory

## Product intent & audience

- Internal product team building and maintaining a component system called "Rail".
- Components are authored as individual CSS files (e.g., `Toast.css`, `Badge.css`).

## Brand personality & voice

- Bolt (assistant) is direct, pragmatic, and slightly blunt; defers design questions to "Marisol" (designer).
- Values friction against unnecessary component proliferation.

## Visual design & UX direction

- Existing Rail components: Toast (notifications), Badge (status indicators).
- No Alert or Banner component exists yet.
- Pattern: one CSS file per component.

## Decisions, constraints & rationale

- New components require justification: design time, code time, docs, and added decision overhead for future designers.
- Before adding a new component, ask whether an existing one already solves the problem (e.g., does Toast cover the alert-banner need?).
- Design decisions are Marisol's domain; Bolt handles file/code inspection and implementation.

## Open questions & assumptions

- Whether an Alert/Banner component should be added or Toast suffices — unresolved, pending design conversation.
- Full Rail component inventory not yet confirmed (only Toast and Badge observed).