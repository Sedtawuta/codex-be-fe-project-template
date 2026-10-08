# Feature contracts

Create `<feature>.md` for each implementable slice. Keep one source of truth for backend/frontend contracts; use canonical terms from root `GLOSSARY.md` and link relevant domain rules instead of repeating them. Split work only when slices have independently testable outcomes.

Use these sections, omitting those that do not apply:

```markdown
# <Feature name>

Status: draft | ready | in-progress | blocked | done
Product outcome: [link to PRD outcome, or originating request for a standalone change]
Blocked by: [links to prerequisite features or required decisions; none if ready]

## Outcome and scope
Actor, user outcome, included behavior, explicit exclusions.

## Rules
Preconditions, allowed transitions, validation, ownership/permissions.
Link relevant domain.md sections; resolve required business choices before coding.

## API
Method/path; request/response fields, types, nullability, examples.
Success/error statuses; field errors; auth; pagination if applicable.
Money/date representation; retry/idempotency/concurrency if applicable.

## UI
Entry point and interactions; loading, empty, success, and error states.
Validation feedback, keyboard navigation, focus, labels, responsive behavior.

## Data
Business field meanings, relationships, required values, and invariants;
link shared domain rules. Follow Data design ownership in docs/architecture.md.
Identify changed entities/constraints and migration/backfill/compatibility needs;
backend refines storage details in code and migrations.

## Acceptance criteria
- AC1: Given [state], when [action], then [observable result].
- AC2: Invalid input and forbidden access have specified outcomes.
- AC3: Applicable boundary cases (money, dates, duplicate requests) are explicit.

## Verification
Checks proving criteria; required integration/browser checks and fixtures.

## Work split
Backend owns be/; frontend owns fe/; main agent owns shared docs.
Dependencies or contract decisions that must precede implementation.
```

Record only decisions and remaining blockers here. Put changed paths and check results in the agent's handoff, not a running transcript in this document.
