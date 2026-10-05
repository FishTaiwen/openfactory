# Module specification

[English](module-specification.md) | [繁體中文](../zh-TW/module-specification.md)

Draft v0.1; not an implemented feature list.

Receiving records supplier, part, PO reference (optional), receipt line, supplier lot, quantity, unit, and receipt time. Confirming a receipt requests an IQC task using the same lot ID. Draft receipts do not create tasks.

IQC lists pending tasks and records plan revision, sampling basis, measurements, defects, evidence, inspector, and result. Missing required inspection criteria block finalization. NG creates a quality hold and disposition request; supplier follow-up belongs to a future NCR/SQE workflow.

| Role | Allowed actions |
|---|---|
| Warehouse | Confirm receipts; confirm authorized putaway or returns |
| Inspector | Record evidence and permitted inspection results |
| Quality reviewer | Review ambiguous results and request disposition |
| Designated approver | Approve concession or disposition within configured authority |
| Administrator | Configure access; no implicit quality approval |

Proposed quality states: PENDING_INSPECTION, IN_INSPECTION, ACCEPTED, QUALITY_HOLD, REJECTED. CONCESSION_ACCEPTED requires an approval reference. Physical movement states are tracked separately.

MVP acceptance: repeat a receipt import without duplicates; complete PASS and see warehouse eligibility; complete NG and block release; reject unauthorized approvals; reconcile a partial disposition; preserve history after a plan revision; export results without manual re-entry.
