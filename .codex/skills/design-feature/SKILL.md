---
name: design-feature
description: Resolve UX flow and screen design for a new or materially changed feature before dependent implementation planning.
---

# Design feature

Main coordinates; frontend owns design artifacts within `fe/`. All paths are
relative to the project root. Design is one adaptive round, not five approval gates.

Read the selected feature's outcome, UI, and acceptance criteria plus relevant
domain rules. Inspect existing screens/components and `.interface-design/system.md`
if present. Use `.agents/skills/interface-design/SKILL.md` for hierarchy, visual
direction, and consistency; adapt examples to the installed Angular stack.

For a small change following an agreed pattern, reuse that pattern and go directly
to implementation. For a new or uncertain journey, resolve the user flow, screen
map/layout, and visual direction together. Show one recommended design; create a
clickable prototype only when interaction or cross-screen behavior needs to be
experienced. Use the existing app or a small HTML prototype in `fe/design/<feature>/`;
do not scaffold an application just for a mockup. Mark simulated data/actions clearly.

Cover the critical journey and relevant loading, empty, error, validation, and
permission states. Include responsive behavior, readable content, keyboard/focus,
and accessible controls. Check the visible result at relevant viewport sizes with
available browser tools; report any unavailable visual verification.

Show the concrete proposal before asking about unresolved decisions that affect
dependent work. Reuse prior agreement; do not request approval for every substep
or component. Main records agreed flow, states, and prototype links in the feature's
`UI` section; save reusable design decisions only in `.interface-design/system.md`
when established. Frontend returns these decisions for Main to record unless given
explicit ownership of shared files. Avoid duplicate wireframe/design documents.

Then use `.codex/skills/plan-feature/SKILL.md` if coordinated work needs planning.
Design blockers stop dependent UI work; independent backend work may proceed.
