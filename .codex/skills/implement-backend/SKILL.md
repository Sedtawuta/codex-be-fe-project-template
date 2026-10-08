---
name: implement-backend
description: Implement or fix Spring Boot backend behavior in be/ from a scoped feature contract.
---

# Implement backend

All paths below are relative to the project root.

1. Read root `AGENTS.md`, `be/AGENTS.md`, the assigned feature contract, and only relevant architecture/domain sections. Identify backend acceptance criteria; report contract gaps to the main agent before dependent work.
2. Locate affected files and nearby tests. Trace the changed request/event through business rules to persistence and external side effects; inspect only dependencies needed to understand that path. Discover versions and checks in build manifests and wrappers.
3. Implement the smallest change satisfying the criteria, including necessary migrations and behavioral tests. For Java unit-test changes, follow the supporting testing skill's compile-before-change and full-verification-after requirements using the project's Maven or Gradle wrapper and configured tasks; do not introduce Maven into a Gradle project. Report an existing compilation blocker before dependent test edits.
4. Run focused tests and required affected-layer checks. Verify a critical success path and a relevant failure path. For changed writes, check persistence and rollback behavior; for external effects, verify failure/retry handling rather than assuming a database rollback undoes them. Disclose failed or unavailable checks.
5. Return changed paths, criteria covered, API/migration effects, exact checks/results, and blockers or residual risks. Summarize logs; include excerpts only to explain a failure.
