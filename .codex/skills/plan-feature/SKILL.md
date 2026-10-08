---
name: plan-feature
description: Plan an agreed feature with multiple steps or backend/frontend dependencies from its feature contract.
---

# Plan feature

Main-agent workflow; all paths are relative to the project root. Produce a plan, not implementation.

1. Read the assigned feature contract and relevant architecture/domain rules. Use `GLOSSARY.md` for terminology. For unresolved new or materially changed UI, use `.codex/skills/design-feature/SKILL.md` before planning dependent implementation. Read linked design artifacts as needed. Inspect implementation only to resolve a concrete dependency; ask only for missing decisions that block planning.
2. Identify the smallest verifiable slices covering the acceptance criteria. Within each slice, assign backend work to `be/`, frontend work to `fe/`, and shared contract/docs to main. Include required migrations and verification; reuse the installed stack and existing tools.
3. For each task, record its outcome, owner/owned paths, true blockers, acceptance criteria covered, and verification. Apply `docs/architecture.md` Data design ownership for entity/field changes; settle business data meanings and shared API/UI decisions before dependent work. Assign persistence design and migrations to backend. Parallelize only tasks with no unmet blockers and no overlapping file ownership.
4. Write a compact table in the feature's `Work split` section: task/outcome, owner/paths, blocked by, done when, verification. Link criteria rather than restating requirements. Create `docs/features/<feature>-plan.md` only when a separate plan materially improves readability; link it from the feature and keep one authoritative plan.
5. Confirm every acceptance criterion has an owner and a check, dependencies have no cycles, and the plan fits the requested scope. Report unresolved blockers. Omit speculative tasks, unrelated refactors, mandatory diagrams, and external tracker setup.
