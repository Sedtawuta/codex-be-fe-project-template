# Working agreement

- Main agent: coordinate scope, contracts, and results. Handle small local changes directly using the matching role; read only affected implementation. For delegated work, inspect implementation only for a concrete blocker or integration question.
- Delegate when independent work or a separate review justifies another agent. Use `backend`, `frontend`, or `reviewer` from `.codex/agents/*.toml`; provide the feature path, owned paths, and acceptance criteria. Never assign overlapping files concurrently. If delegation is unavailable, apply the scoped role locally.
- Read `docs/overview.md` for project scope; `docs/features/<feature>.md` for the assigned feature. Read `docs/architecture.md` for cross-layer/API decisions and `docs/domain.md` for business/data rules. Load only relevant sections.
- Use root `GLOSSARY.md` as the single source of domain terminology; read only relevant entries. Main: when defining/changing terms or domain relationships, use `.agents/skills/domain-modeling/SKILL.md`.
- Main: for a project idea, PRD, or MVP decomposition, follow `docs/workflow.md`; load only the current stage's skill.
- Main: when an agreed feature needs multiple steps or coordinated dependencies, use `.codex/skills/plan-feature/SKILL.md`; handle a simple local change directly.
- Search with scoped `rg`; open matching files and required callers. Expand scope only for a named dependency or failing check. Summarize findings instead of pasting files/logs.
- Follow nested `AGENTS.md` and the matching workflow in `.codex/skills/`. Use installed versions and existing build scripts. For framework/API syntax, resolve and query Context7 when available; otherwise consult official version-matched docs.
- Preserve unrelated work. Prefer native features and existing dependencies; add abstractions only for a demonstrated need. Keep secrets and personal data out of code, logs, and prompts.

## Definition of Done

Acceptance criteria met; affected API/docs synchronized; relevant tests and build/type checks pass. Report changed paths, exact checks/results, and any blocked verification or remaining risk. Never label an unrun check as passed.
