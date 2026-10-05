# Data principles

[English](data-principles.md) | [繁體中文](../zh-TW/data-principles.md)

1. Use a stable internal ID and a unique external key: source_system + external_receipt_id + external_line_id + external_lot_id.
2. Store quantities with units and exact decimal representation. Do not combine incompatible units without an approved conversion.
3. Keep receipt facts, inspection decisions, disposition approvals, and warehouse movements distinct.
4. Snapshot drawing revision, inspection plan revision, and sampling basis when a task starts. Later document changes must not silently alter historical evidence.
5. Record actor, timestamp, reason, record version, and before/after values for changes. Corrections create traceable revisions.
6. Repeated imports and API retries must not duplicate receipts or tasks. Conflicting repeats must be reported.
7. Split lots and partial dispositions retain parent links. Accepted + held + rejected quantities must reconcile to the applicable lot quantity; sampling is recorded separately.
8. Authorization is checked on the server. Inspection permission does not automatically grant concession approval.
9. Use synthetic examples only in the public repository.
