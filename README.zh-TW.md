# OpenFactory

[English](README.md) | [繁體中文](README.zh-TW.md)

開源、模組化的製造管理平台：只使用你需要的模組，並與既有系統整合。

**資料只輸入一次，之後隨流程流動。**

## 專案狀態

目前為設計階段，Repository 提供英文與繁體中文規格草案，尚無可執行軟體，模組與介接器尚未實作。

## 第一階段

完成「倉庫收料 → IQC 檢驗 → 倉庫取得品質放行狀態」，並提供 Excel／CSV 資料交換與 REST API。IQC 接續使用倉庫收料資料，經授權完成的品質判定自動回傳，不需重複輸入；實際入庫由倉庫另行確認。

## 說明文件

- [願景](docs/zh-TW/vision.md)
- [架構](docs/zh-TW/architecture.md)
- [資料原則](docs/zh-TW/data-principles.md)
- [模組規格](docs/zh-TW/module-specification.md)
- [介接規格](docs/zh-TW/integration-specification.md)

## 開發路線

1. 確認資料契約、權限、批次生命週期與 MVP 驗收情境。
2. 選定技術，實作收料、IQC 與 Excel／CSV 交換。
3. 用虛構資料驗證完整流程，發布經測試的版本。
4. 逐階段加入庫存、異常管理、供應商、採購、生產與出貨模組。

SAP／MES 介接屬規劃，需要依個別系統開發；完整 ERP 為長期目標。

## 參與與授權

請參閱[貢獻指南](CONTRIBUTING.zh-TW.md)。英文與繁體中文文件同步維護。採用 [Apache License 2.0](LICENSE)。
