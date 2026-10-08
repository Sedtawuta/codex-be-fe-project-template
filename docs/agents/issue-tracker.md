# Work tracking

Mode: local Markdown.

- Product requirements: `docs/prd.md`.
- Ticket identity and content: `docs/features/<feature>.md`, following
  `docs/features/README.md`. Create stable slugs; preserve existing feature files.
- Parent/outcome and Blocked by links live in each feature. A blocker gates a
  specific outcome; unresolved decisions identify their owner and affected work.
- Status: draft, ready, in-progress, blocked, or done. Ready means criteria and
  required decisions are agreed; done requires the project's Definition of Done.
- Main owns shared docs/status; owners report checks for Main to record a result.
- The PRD's Features section indexes the feature files; link instead of copying.

This is the authoritative tracker configuration. Local tracking needs no labels
or remote publishing. Adopt an external tracker only when requested; use this
file to identify whether remote tickets mirror links or become authoritative.
