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
| 多門市 POS／ERP／CRM | Full-stack Engineer | 領域建模、BOM、庫存、跨系統同步 |
| LINE 多租戶 AI 智能客服 | AI / Backend Engineer | LangGraph、RAG、Hybrid Retrieval |
| Memoa AI 語音陪伴與 Agent | Full-stack / AI Engineer | 即時語音、WebSocket、Agent |
| 智慧旅運與 AI 派車 | Full-stack Engineer | Web、Mobile、派車、GPS |
| Factory Pro Chinese | Full-stack Engineer | 多租戶學習平台、Analytics |

## 精選案例

- [多門市 POS／ERP／CRM 平台](projects/pos-erp-crm/README.md)
- [LINE 多租戶 AI 智能客服](projects/ai-customer-service/README.md)
- [Memoa AI 語音陪伴與 Agent](projects/memoa-ai-agent/README.md)
- [智慧旅運與 AI 派車平台](projects/smart-travel/README.md)
- [Factory Pro Chinese 越南工廠中文學習平台](projects/factory-pro-chinese/README.md)

## 如何閱讀

每個案例只展示特定功能，不代表完整系統：

1. 專案背景
2. 我的負責範圍
3. 特定功能
4. 架構圖與重要流程
5. 工程挑戰
6. 技術決策
7. 可靠性與安全性
8. 取捨與限制

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
