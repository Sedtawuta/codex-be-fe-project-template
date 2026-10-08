---
name: to-spec
description: Synthesize agreed product requirements into a concise PRD or update an explicitly named feature contract.
---

# To spec

Use the settled discussion and relevant project documents. Produce requirements;
implementation is a later stage. Tracking conventions live in
`docs/agents/issue-tracker.md`.

1. Default to `docs/prd.md` for a project/MVP. If the user names a feature contract,
   update that file using `docs/features/README.md`. Preserve existing agreements
   and scope reads to the decisions being documented; inspect code only for a
   concrete compatibility question. No codebase is required for a new project.
2. For the PRD, use its existing sections: problem/users, observable outcomes with
   stable P1/P2 IDs, MVP journeys, scope/exclusions, constraints, open decisions,
   and a linked feature index. Include important failure paths. Keep stories
   limited to the agreed MVP; distinguish facts, assumptions, and unresolved
   business decisions with owners and blockers. Produce a draft when decisions
   remain rather than inventing answers or restarting an interview.
3. Link glossary terms, shared rules, and agreed architecture. Keep detailed
   API/UI/data requirements and AC identifiers in feature contracts; the PRD
   names outcomes and links them. Preserve IDs when wording changes.
4. Check that each agreed outcome has an observable success condition, scope is
   bounded, and every critical open choice identifies its affected work. Report
   the draft and blockers for review. Mark it agreed only with user authorization;
   preserve an already agreed status only if scope and business decisions hold.

Adapted from [to-spec](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md) for this template.
