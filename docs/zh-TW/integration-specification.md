# 介接規格

[English](../en/integration-specification.md) | [繁體中文](integration-specification.md)

草案 v0.1。REST 路徑與可執行 OpenAPI 結構於實作階段制定。

收料輸入欄位：source_system、external_receipt_id、external_line_id、external_lot_id、supplier_code、part_no、quantity（十進位字串）、unit、received_at（含時區偏移的 ISO 8601）；po_no 與 supplier_lot_no 可選。代碼以字串處理，保留開頭的零。

判定輸出欄位：lot_id、來源識別欄位、decision_id、decision_version、quality_status、各處置數量與單位、decided_by、decided_at，以及必要的核准參照。品質判定不代表庫存已過帳。

CSV／Excel 介接須有預覽、欄位對應、必填驗證、逐列錯誤報告與重複檢查。日期、單位、小數分隔符與空白值須明確處理；未對應的供應商或料號阻擋該列。匯入內容僅作為資料，禁止執行公式或巨集；匯出須防範試算表公式注入。

REST 設計須涵蓋身分驗證、權限範圍、結構版本、冪等鍵（重送不重複建單）、樂觀鎖定、分頁、結構化錯誤與重試規則。同一內容重送回傳既有結果，衝突內容回報衝突；輸出重送沿用同一判定 ID，並提供失敗與對帳狀態。

Excel／CSV 為第一個規劃介接器。SAP 與 MES 需各自開發對應介接器，尚未提供即插即用功能。
