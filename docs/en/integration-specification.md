# Integration specification

[English](integration-specification.md) | [繁體中文](../zh-TW/integration-specification.md)

Draft v0.1. REST routes and executable OpenAPI schemas will be designed during implementation.

Inbound receipt fields: source_system, external_receipt_id, external_line_id, external_lot_id, supplier_code, part_no, quantity (decimal string), unit, received_at (ISO 8601 with offset); optional po_no and supplier_lot_no. Codes are strings so leading zeros survive.

Outbound decision fields: lot_id, source identifiers, decision_id, decision_version, quality_status, quantity allocations with units, decided_by, decided_at, and approval reference when required. A quality decision is not a stock-posting confirmation.

CSV/Excel adapters must support a preview, field mapping, required-field validation, row-level error reports, and duplicate detection. Dates, units, decimal separators, and blank cells require explicit handling. Unknown supplier or part mappings block the affected row. Imported content is data, never executable formulas or macros; exports must neutralize spreadsheet formula injection.

REST design must include authentication, scoped authorization, schema versions, idempotency keys, optimistic concurrency, pagination, structured errors, and retry rules. Repeated identical requests return the existing result; incompatible repeats return a conflict. Retried outbound deliveries keep the same decision ID and expose failure/reconciliation status.

Excel/CSV is the first planned connector. SAP and MES connectors require target-specific adapters and are not promised as plug-and-play.
