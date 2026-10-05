# Architecture

[English](architecture.md) | [繁體中文](../zh-TW/architecture.md)

Start with one repository and independently bounded modules. Repository separation and microservices are not prerequisites for modularity. Language, database, and deployment technology are not selected yet.

| Component | Responsibility |
|---|---|
| Core | Identity, permissions, master-data references, audit conventions |
| Receiving | Receipt records and receipt-line lots |
| IQC | Inspection tasks, plan snapshots, evidence, quality decisions |
| Connectors | Map external identifiers and exchange data |

Standalone modules must provide or bundle minimal identity and master-data capabilities; they must not require all other modules. Integrated modules use documented contracts rather than direct access to another module's database.

Receiving owns receipt facts; IQC owns inspection results. An external ERP may own supplier, part, and PO master data. A connector maps authoritative records rather than creating a competing source.

Quality eligibility and physical inventory movement are separate. PASS makes material eligible for putaway; warehouse confirmation records actual putaway. HOLD prevents release. Partial acceptance requires explicit quantity allocations.

No SAP or MES connector is implemented. Each integration depends on the target product, version, interfaces, permissions, and site mapping.
