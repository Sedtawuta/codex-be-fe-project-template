# Domain and data rules

Replace bracketed project fields as real requirements become known; omit irrelevant sections. Business behavior belongs here or in its feature file, never in agent role descriptions.

Terminology is defined only in [GLOSSARY.md](../GLOSSARY.md). Refer to canonical terms here; keep definitions in the glossary.

## Business rules

- Actors and permissions: [roles, ownership, tenant boundaries]
- State transitions: [allowed transitions and preconditions]
- Uniqueness and lifecycle: [identifiers, archival/deletion rules]
- Audit and retention: [events, protected fields, retention requirements]

## Money, when applicable

- Represent amounts with currency. Backend uses `BigDecimal` and database decimal columns, or integer minor units with an explicit currency exponent; never binary floating point for authoritative calculations.
- Define precision, allowed sign/range, scale, rounding mode, and the stage where rounding occurs per operation. Do not assume every currency has two decimal places.
- API uses decimal strings or explicitly specified minor units. Frontend preserves exact values; use JavaScript numbers only within a documented safe range and precision. Formatting is separate from calculation; backend validates and calculates authoritative totals.
- Test rounding boundaries, overflow/range limits, and currency mismatch. Specify duplicate-processing protection for financial commands when needed.

## Other data

- Use ISO 8601 timestamps with an offset, normally UTC, for instants; use `YYYY-MM-DD` for date-only values. Record business timezone where calendar rules apply.
- Distinguish missing, null, zero, and empty values. Define units, precision, and valid ranges for measurements.
- Enforce persistent invariants with database constraints as well as boundary validation. Use reviewed, versioned migrations; handle existing records before tightening constraints.
- Define concurrency behavior for shared updates. Minimize personal data and document retention before adding destructive cleanup.
