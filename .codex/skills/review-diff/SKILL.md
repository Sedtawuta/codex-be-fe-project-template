---
name: review-diff
description: Review a scoped git diff against feature requirements for actionable correctness, security, and regression issues.
---

# Review diff

All paths below are relative to the project root. Review is read-only unless fixes are explicitly assigned.

1. Read the assigned feature acceptance criteria and applicable root/nested AGENTS.md. Confirm the review range: supplied base/commit, branch merge-base, staged changes, or working tree. If missing, review current staged and unstaged changes plus relevant untracked files; state that scope. If no Git repository exists, report that limitation and review only explicitly supplied files.
2. Inspect change names/statistics, then scoped diff hunks. Read extra definitions, callers, contract sections, and tests only to verify a specific concern; avoid whole-repository scans.
3. Trace relevant input/output paths for incorrect behavior, API mismatch, unauthorized access, destructive migrations, money/date errors, and uncovered acceptance criteria. Use version-matched official docs or Context7 for uncertain framework semantics.
4. Validate each finding against the actual path and triggering condition. Report severity, file/line, impact, and a concrete correction. Prefer observable issues over speculative refactors or style comments.
5. Return actionable findings first, then check evidence and verification gaps. If none, say “No actionable findings” and describe review scope; passing review does not substitute for unrun tests.
