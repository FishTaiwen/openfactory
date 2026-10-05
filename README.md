# OpenFactory

[English](README.md) | [繁體中文](README.zh-TW.md)

An open-source, modular manufacturing ERP platform. Use only what you need, integrate with what you already have.

**Enter once. Flow everywhere.**

## Project status

Design stage. This repository contains bilingual draft specifications, not runnable software. No modules or connectors are implemented yet.

## First milestone

Receiving → IQC → warehouse eligibility, with Excel/CSV exchange and a REST API. Warehouse receipt data is reused by IQC; authorized quality decisions flow back without re-entry. Physical putaway remains a separate warehouse action.

## Documentation

- [Vision](docs/en/vision.md)
- [Architecture](docs/en/architecture.md)
- [Data principles](docs/en/data-principles.md)
- [Module specification](docs/en/module-specification.md)
- [Integration specification](docs/en/integration-specification.md)

## Roadmap

1. Review contracts, permissions, lot lifecycle, and MVP acceptance scenarios.
2. Choose a stack and implement receiving, IQC, and Excel/CSV exchange.
3. Validate the complete workflow with synthetic data and publish a tested release.
4. Add inventory, NCR, supplier, purchasing, production, and shipping modules as separately scoped milestones.

SAP/MES integration is planned and requires system-specific adapters. A complete ERP is a long-term objective.

## Contributing and license

See [contribution guidelines](CONTRIBUTING.md). English and Traditional Chinese documents are maintained together. Licensed under [Apache License 2.0](LICENSE).
