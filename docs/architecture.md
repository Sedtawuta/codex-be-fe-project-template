# Architecture defaults

These are starting conventions. Preserve existing project contracts; record deviations here once agreed. Choose framework/runtime versions when scaffolding, then use manifests and lockfiles as the source of truth.

## Boundaries

- `be/`: Spring Boot application; group by feature, keeping controller/DTO, service, and persistence responsibilities distinct. Services own use cases and transaction boundaries; controllers adapt HTTP; repositories handle persistence.
- `fe/`: Angular application; group by feature and colocate related UI, data access, and tests. Prefer standalone components for new code supported by the installed version. Share code only after real reuse appears.
- `docs/features/<feature>.md`: authoritative feature behavior and API contract. Backend and frontend consume this contract without reading each other's internals. Main agent owns shared document changes during delegated work.

## Data design ownership

- Main agrees with the user on domain concepts, relationships, field meanings,
  required business values, lifecycle, and invariants. Keep terminology in
  `GLOSSARY.md`, shared rules in `docs/domain.md`, and feature-specific decisions
  in the feature's `Data` section.
- Backend owns the persistence design in `be/`: entities, field types,
  nullability, precision/scale, keys, relationships, database constraints,
  query-driven indexes, and migrations/backfills. Return decisions affecting
  business behavior or the shared contract to Main for resolution and recording.
- Frontend owns input/display needs and interaction feedback. Main coordinates
  API DTO fields with backend/frontend; UI fields and API DTOs need not match
  persistence entities one-to-one.

During Design and plan, resolve data decisions affecting UI/API or business
behavior before dependent work. Backend can refine persistence details during
implementation within the agreed contract; ordinary storage choices need no
additional approval. Main records material contract changes before dependent
implementation continues. Code and migrations remain the source of storage
details; use diagrams only when they clarify a real relationship.

## API contract

- Use resource-oriented JSON HTTP endpoints, explicit DTOs, and appropriate status codes; avoid a universal response wrapper unless already required.
- Specify methods/paths, field types, nullability, validation, success/error examples, authorization, and pagination/sort bounds in the feature file before cross-layer work.
- Use a consistent safe error shape; for new APIs prefer Problem Details when supported. Field errors identify the input field; responses exclude stack traces and internal database details.
- Document decimal/currency and date/time formats using `domain.md`. Preserve compatibility; coordinate breaking changes and caller updates explicitly.
- Bound list queries. Define idempotency or optimistic concurrency for operations where duplicate submission or lost updates cause harm.

## Security

- Backend enforces authentication, authorization, ownership, and tenant scope on every protected operation. Route guards and hidden controls provide UX only.
- Validate untrusted inputs at the boundary; use parameterized persistence queries. Allowlist sort/filter fields and constrain upload size/type where applicable.
- Externalize secrets; redact sensitive data in errors/logs. Use least privilege and explicit CORS origins. Keep CSRF protection appropriate to the authentication mechanism; never disable security just to pass tests.

## Verification

Use the existing wrapper/package scripts and test runner. Start with changed behavior: unit tests for rules, focused HTTP/persistence tests for boundaries, component/form/HTTP tests for frontend behavior. Add an integration or end-to-end check when the feature crosses boundaries that unit tests cannot verify. Build/type-check affected layers; run repository-required checks. Report unavailable infrastructure precisely.

## Documentation references

Consult only for relevant version/API questions: [Angular style guide](https://angular.dev/style-guide), [typed forms](https://angular.dev/guide/forms/typed-forms), [Angular security](https://angular.dev/best-practices/security), [Spring Boot structure](https://docs.spring.io/spring-boot/reference/using/structuring-your-code.html), [Spring Boot testing](https://docs.spring.io/spring-boot/reference/testing/spring-boot-applications.html).
