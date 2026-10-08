---
name: grill-with-docs
description: Clarify a project idea or design while maintaining canonical domain terms and shared rules.
---

# Grill with docs

1. Read `.agents/skills/grilling/SKILL.md` and
   `.agents/skills/domain-modeling/SKILL.md`; follow their interview and modeling
   disciplines. In Codex, read the files directly; a separate Skill tool is not
   required.
2. Read project identity and relevant domain sections. Update root `GLOSSARY.md`
   as terms settle; keep shared business/data rules in `docs/domain.md`. Create
   an ADR only when the modeling skill's durable trade-off criteria hold.
3. For a new product, settle the first usable MVP and critical integration or
   business choices. Record unresolved choices with owners and blockers. For an
   existing feature, keep discovery scoped to the requested change.
4. Summarize the agreed scope. When a PRD is requested, hand the settled context
   to `to-spec` through document pointers; otherwise finish the interview.

Adapted from [grill-with-docs](https://github.com/mattpocock/skills/blob/main/skills/engineering/grill-with-docs/SKILL.md) for this template.
