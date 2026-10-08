---
name: implement-frontend
description: Implement or fix Angular frontend behavior in fe/ from a scoped feature and API contract.
---

# Implement frontend

All paths below are relative to the project root.

1. Read root `AGENTS.md`, `fe/AGENTS.md`, the assigned feature contract, and only relevant architecture/domain sections. Identify UI acceptance criteria and the agreed API; report contract gaps to the main agent before dependent work.
2. Locate affected files and nearby tests. Trace the changed flow across routes, components, state, and API calls; identify async updates and state ownership. Discover versions and checks in manifests.
3. Resolve required UI decisions against existing components and design conventions. Specify changed layouts and loading/empty/error/success states, responsive behavior, and keyboard/focus interactions. For design-only tasks, return concrete screen/component guidance and unresolved decisions without editing implementation.
4. For implementation tasks, make the smallest change, including behavioral tests. Use existing mock/test mechanisms while an agreed backend is pending.
5. Run focused tests and required build/type checks. Verify the exact changed user flow and one relevant high-risk transition (such as stale responses, duplicate submission, or conditional rendering). Inspect layout at supported screen sizes and keyboard/focus behavior in a browser when practical; disclose unavailable verification. Distinguish mock checks from real API integration.
6. Return changed paths, criteria covered, UI/API implications, exact checks/results, and residual UI/accessibility/integration risks. Include screenshots only when useful to assess the change.
