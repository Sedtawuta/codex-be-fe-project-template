# Project overview

Reusable instructions for an Angular frontend (`fe/`) and Spring Boot backend (`be/`). This template contains documentation and workflows; application scaffolding is a separate task.

## Start a project

1. Copy the entire `project-template` directory, including hidden directories and symlinks, to the new project folder. Open that folder as the project root.
2. Set the project identity below. For a new idea, follow [idea to release](workflow.md) to create an agreed [PRD](prd.md). Define canonical terms in root `GLOSSARY.md` and business/data rules in `docs/domain.md`.
3. Adapt `docs/architecture.md` where the project differs. Record installed versions and commands in build manifests/scripts rather than duplicating them here.
4. Select one feature using `docs/features/README.md`. For new or materially changed UI, use `design-feature` before dependent implementation planning; reuse agreed patterns for small changes. Then plan when needed, implement, and review it.

## Project fields

- Name: [project name]
- Product requirements: [PRD](prd.md), authoritative for users, scope, constraints, and success.
- Workflow and starter prompts: [idea to release](workflow.md).

## Codex wiring

Template workflow skills live in `.codex/skills/` as requested. Each folder is exposed through a relative symlink under `.agents/skills/` for Codex repository discovery. Preserve these links when copying; on systems without symlink support, move the workflow skills to `.agents/skills/` and update pointers rather than maintaining duplicate copies.

Installed backend skills live directly in `.agents/skills/`: `java-springboot` from `github/awesome-copilot` and `131-java-testing-unit-testing` from `jabrena/plinth`. `skills-lock.json` records installed skill sources and content hashes. Copy these folders, their references, and the lockfile with the template; no global installation is required. Select supporting skills by task. The unit-testing skill requires compilation before test changes and full verification afterward; use equivalent configured tasks with the project's Maven or Gradle wrapper. Project contracts and money/security rules override generic examples.

`.codex/agents/*.toml` define project-scoped custom agents named `backend`, `frontend`, and `reviewer`. The main agent selects the matching agent and supplies the feature path, owned paths, and acceptance criteria. Reviewer requests a read-only sandbox; active session permission overrides still apply. Model and reasoning settings inherit from the session unless overridden at spawn time. No account configuration or machine-specific paths are prescribed.

Frontend designs in workflow stage 4 and implements in stage 5. `design-feature` coordinates one adaptive design round using `interface-design` from `Dammyjay93/interface-design`. Main records agreed UI in the feature and reusable visual rules in `.interface-design/system.md` when established; prototypes live within `fe/`. Small changes reuse agreed patterns without a separate prototype. Its supporting skills are `angular-developer` and `angular-new-app` from `angular/skills`, `tailwind-css-patterns` from `giuseppe-trisciuoglio/developer-kit`, and `primeng` from `begj/agent-skills`. Use scaffolding, Tailwind, and PrimeNG skills only when relevant to existing or explicitly requested work. Adapt examples to Angular and installed library versions. These skills and their references are included under `.agents/skills/` and recorded in `skills-lock.json`.

Main agent handles small local changes directly and delegates when independent work or separate review earns the overhead. Nested `be/AGENTS.md` and `fe/AGENTS.md` carry project-specific constraints; supporting skills carry reusable framework guidance.

Main uses `domain-modeling` for changed terminology/domain relationships, and `plan-feature` for coordinated work within an agreed feature. Planning-stage skills and their activation conditions are listed in [workflow.md](workflow.md); local tracking is preconfigured in [issue-tracker.md](agents/issue-tracker.md). Installed skills live in `.agents/skills/`; template workflows live in `.codex/skills/` with discovery symlinks. Reading an existing definition alone does not require loading the modeling skill.

Root `GLOSSARY.md` is the only terminology source. Keep definitions and discouraged synonyms there; keep invariants, permissions, and money/date rules in `docs/domain.md`. When the modeling skill calls for a glossary update, update `GLOSSARY.md` rather than copying definitions into other documents. Create ADRs only for decisions meeting the skill's criteria.

Implementation plans use the project's installed stack, `fe/` and `be/` ownership, and the existing feature contract. `plan-feature` records outcomes, owners, blockers, acceptance criteria, and verification in the feature's Work split section; create `docs/features/<feature>-plan.md` only when a separate plan is useful. Simple local changes need no separate planning workflow, and planning requires no issue tracker.

Example request: “Implement `docs/features/<feature>.md` following AGENTS.md. Use the backend and frontend custom agents; review the resulting diff against the acceptance criteria.”

Discovery/configuration references: [Codex skills](https://learn.chatgpt.com/docs/build-skills), [Codex subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents).
