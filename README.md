# 商業工程專案案例集

[English](README.en.md)

這個 Repository 用來整理我在全職工作、接案與客戶專案中參與的商業軟體工程案例。

內容聚焦於特定功能與工程決策，不包含完整產品原始碼：

- 企業系統
- AI 與 Agent 應用
- 系統整合
- 多租戶與權限設計
- 可靠性與安全性
- 資料與領域模型
- 以實際部署為導向的開發

案例內容整理 **2026 年 3 月至 2026 年 9 月** 的商業開發工作。

> 商業專案的原始碼與正式資料不公開。
> 所有內容均已簡化、去識別化或使用重製資料。

## 專案總覽

| 專案 | 角色 | 主要工程重點 |
| --- | --- | --- |
| 多門市 POS／ERP／CRM 整合平台 | Full-stack Engineer | 商品、BOM、庫存、製造、跨系統同步 |
| 民宿 AI 客服與知識庫平台 | AI / Backend Engineer | LINE OA、Intent Routing、RAG、Hybrid Retrieval |
| 陪伴型 AI 語音與 Agent 平台 | Full-stack / AI Engineer | 即時語音、WebSocket、Agent Runtime |
| 智慧旅運訂單與派車平台 | Full-stack Engineer | 訂單、派車、GPS、行動端 |
| 工廠中文學習與企業管理平台 | Full-stack Engineer | 多租戶學習、在地化、匯入、Analytics |

## 精選案例

- [多門市 POS／ERP／CRM 整合平台](projects/multi-store-pos-erp-crm/README.md)
- [民宿 AI 客服與知識庫平台](projects/guesthouse-ai-support/README.md)
- [陪伴型 AI 語音與 Agent 平台](projects/companion-ai-platform/README.md)
- [智慧旅運訂單與派車平台](projects/travel-operations-dispatch/README.md)
- [工廠中文學習與企業管理平台](projects/workplace-chinese-learning/README.md)

## 個人作品

### SUCRÉ 客製甜點電商

以設計稿實作的 WordPress + WooCommerce 個人作品，展示自訂 Theme／Plugin、Docker、響應式商品頁與本機購物流程；此案例為自發展示作品，**不是客戶商業專案**。

**重點：** WordPress · WooCommerce · Custom Theme / Plugin · Docker Compose · RWD · Store API · Checkout Blocks

[案例研究](./projects/sucre-woocommerce/README.md)

## 如何閱讀

每篇會依專案的實際工作內容整理，通常會包含：

1. 我接手時的狀況
2. 我實際處理的功能
3. 遇到的問題與處理方式
4. 架構圖與流程圖
5. 取捨、限制與公開範圍

每張圖都同時保留 Mermaid 原始檔與 SVG：

```text
diagrams/system-architecture.mmd
diagrams/system-architecture.svg
```

## 保密範圍

本 Repository 不包含：

- 正式環境原始碼
- 帳號、密鑰或 Token
- 正式資料庫
- 客戶與使用者資料
- 內部網址、IP 或伺服器資訊
- 未去識別化的截圖或 Log
- 客戶專屬商業規則

架構圖、畫面與實作說明均已簡化或去識別化，僅供作品展示與技術討論。
