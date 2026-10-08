---
name: to-tickets
description: Split an agreed PRD or MVP into verifiable feature contracts with acceptance criteria and genuine dependencies.
---

# To tickets

Read `docs/agents/issue-tracker.md`, the requested PRD, and
`docs/features/README.md`. Local tickets are the feature contracts themselves.

1. Identify the smallest complete slices covering the MVP outcomes. Each slice
   delivers verifiable behavior across the applicable UI/API/data boundaries and
   fits a focused implementation session. Separate foundational or research work
   only when it genuinely blocks a slice; business choices stay marked as choices.
2. Draft a compact list of feature outcomes, covered product outcome IDs, and true
   blockers. Obtain agreement on material scope or business decisions; use existing
   authorization rather than asking again for routine document edits.
3. Create or update one stable `docs/features/<feature>.md` per slice using the
   feature template. Define actor, scope, rules, AC1/AC2 criteria, verification,
   product outcome links, and Blocked by links. Specify required API/UI/data
   decisions before implementation; mark unknowns and their owner. Keep files
   draft or blocked until required decisions and criteria are agreed.
4. Update only the PRD's Features index with links. Use canonical terms and link
   shared rules. Maintain one feature body rather than a second ticket copy.
   Check every MVP outcome has criteria, prerequisite links exist, and dependencies
   have no cycles. Report uncovered outcomes and unresolved choices.
5. Hand the selected feature to `.codex/skills/plan-feature/SKILL.md` to resolve
   design/contract blockers and assign backend/frontend tasks in Work split.
   Keep unresolved blockers explicit; only ready tasks proceed to implementation.
   A simple agreed local change can proceed directly when implementation is authorized.

Adapted from [to-tickets](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md) for this template.
