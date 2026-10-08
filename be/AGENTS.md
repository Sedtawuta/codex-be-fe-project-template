# Backend

- Endpoint/authorization changes follow the contract and security rules in `docs/architecture.md`; backend enforces ownership and permissions.
- Money, precision, date/time, and persistent invariants follow relevant `docs/domain.md` rules. Schema changes preserve existing records through versioned migrations.
- Add project-specific backend exceptions here; reusable framework guidance belongs in supporting skills.
