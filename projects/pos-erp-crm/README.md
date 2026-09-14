# POS / ERP / CRM 平台

[English](README.en.md)

**期間：** 2026/03 – 2026/09<br>
**專案類型：** 商業專案／全職工作<br>
**角色：** Full-stack Engineer<br>
**重點：** Legacy Modernization · ERP · 領域建模 · 系統整合

## 一、專案概述

多門市 POS、進銷存、製造、財務與 CRM 整合平台。

本案例只展示我負責的特定功能與工程決策，不包含完整商業系統。

## 二、專案背景

原有系統以 POS 與財務流程為主，後續增加多門市、倉庫調撥、商品變體、BOM、製造與 CRM 同步需求，因此需要重新整理既有資料模型與業務流程。

## 三、我的角色

我負責前後端開發、領域與資料建模、Legacy 流程重構、庫存與製造邏輯、POS 與 CRM 整合、部署腳本、問題排查與測試驗證。

## 四、負責範圍

- 整理商品、原料、分類與 Variant 資料模型
- 實作多層 BOM 展開與製造流程
- 處理採購、進貨、銷售、退貨、出貨、調撥與多倉庫庫存異動
- 整合財務、成本追蹤、多門市管理與交易回復流程
- 建立成本歷史與庫存變更記錄
- 開發條碼收貨與主檔資料匯入
- 建立 POS 與 CRM 商品、分類、原料及交易同步
- 使用 Outbox、Queue、Retry 與 Idempotency 處理跨系統同步
- 改善員工、報表、會計與營運管理介面
- 維護多門市部署與環境同步腳本

## 五、技術環境

- Backend：Laravel、PHP
- Frontend：HTML、JavaScript、Bootstrap-based UI
- Database：MySQL
- Integration：REST API、Database Queue、Outbox
- Runtime：Apache、Scheduler、Queue Worker、Print Adapter

**skills:** PHP, Laravel, JavaScript, MySQL, REST API, Multi-tenant, RBAC, Outbox Pattern, Queue, Idempotency, HMAC

外部整合包含 Google Calendar 雙向預約、電商訂單匯入、條碼收貨、LINE OA 出勤、電子發票，以及 USB／Wi-Fi 收據列印。

## 六、系統架構

![POS / ERP / CRM 架構](diagrams/system-architecture.svg)

- [Mermaid 原始圖](diagrams/system-architecture.mmd)
- [POS 與 CRM 同步流程](diagrams/pos-crm-sync.svg)
- [Item / BOM 領域模型](diagrams/item-bom-domain.svg)
- [製造流程](diagrams/manufacturing-flow.svg)

## 七、主要工程挑戰

### 統一商品與庫存概念

商品、原料、Variant 與 Legacy item 原本有不同的資料假設。我重新整理資料流，使採購、庫存、銷售、製造與外部同步可以使用一致的領域規則。

### 維持庫存一致性

製造、進貨、出貨、調撥與調整都可能影響相同庫存。我追蹤各種狀態轉換，處理重複扣庫存、漏扣庫存、成本記錄與調撥完成等問題。

### 表達多層 BOM 關係

BOM 可能包含巢狀元件與重複品項，因此使用樹狀走訪與排序，讓父子關係能正確呈現並支援後續製造與庫存作業。

### POS 與 CRM 同步

POS 的主要交易流程不能依賴 CRM 立即可用，因此將資料異動與背景同步拆開，並建立可追蹤的重試與冪等邊界。

## 八、技術決策

- 使用 Outbox，避免 POS 主交易流程依賴 CRM 即時可用。
- 明確區分 POS 擁有的欄位，避免外部同步覆蓋錯誤資料。
- 將庫存變更限制在明確的業務流程與狀態中。
- 使用樹狀走訪處理 BOM，而非依賴資料庫平面排序。
- 由目前部署網址推導 API 來源，避免寫死單一主機。

## 九、可靠性與安全性

- 租戶與門市範圍檢查
- Queue-based integration
- Retry 與重複事件防護
- 庫存預留與扣除邊界
- CSRF 與 Security Headers
- 匯入資料驗證
- 部署後快取與路由更新

RFID 實體讀卡器與付款流程僅記錄為整合邊界，不宣稱已完成正式硬體或付款 UAT。

## 十、重製畫面

- [POS Operations Dashboard](screenshots/pos-dashboard.svg)
- [BOM Editor](screenshots/bom-editor.svg)
- [Manufacturing Order](screenshots/manufacturing-order.svg)

以上均為去識別化重製畫面，使用範例資料，不是正式客戶截圖。

## 十一、取捨與限制

本案例只描述特定商業功能。正式網址、原始碼、憑證、客戶資料與正式部署證據不公開。

需要實體設備、付款服務商或正式資料驗證的功能，會標示為待驗證，不當作已完成的正式成果。

## 十二、成果

將平台從基本 POS 作業延伸至門市、倉庫、製造與 CRM 整合流程，並讓跨系統同步邊界更清楚、更容易維護。

## 十三、學習

這個專案讓我實際處理 Legacy 領域重構、庫存一致性、製造資料建模與商業系統同步的工程取捨。

## 保密聲明

這是商業專案。公開內容不包含正式原始碼、憑證、客戶資料或專有商業資訊。
