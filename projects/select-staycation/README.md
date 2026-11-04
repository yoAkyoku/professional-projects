# Select Staycation 多站旅宿官網與內容管理系統

[English](README.en.md) · [公開網站：Villa Samaya Awan](https://selectstaycation.com)

![Select Staycation portfolio cover](../../assets/project-covers/select-staycation-cover.png)

**專案類型：** 客戶專案／旅宿網站與 CMS  
**角色：** Full-stack Engineer  
**重點：** 多站內容管理 · 住宿篩選 · 中英管理介面 · 詢問型預訂

## 專案概覽

為旅宿品牌建立可管理多個站點的網站與內容管理系統。此案例連到 Select Staycation 旗下 Villa Samaya Awan 的公開官網；管理平台可建立品牌站點，並維護住宿、頁面、媒體與行銷內容。

## 我完成的範圍

- 建立父站、範本與子站的管理流程；子站建立後，可獨立維護自己的內容與設定。
- 製作住宿列表與詳細頁面，整理房型、價格說明、設施、常見問題、地點與聯絡資訊，並提供住宿條件篩選。
- 提供中文與英文的管理介面；站內內容由管理者分別維護，切換管理介面語言不會自動翻譯內容。
- 建立頁面、橫幅、文章與媒體的 CMS 流程，支援預覽、審核、發布及封存。
- 建立詢問型預訂流程，讓旅客提交需求後由營運人員在後台處理；管理端可更新狀態、加註內部備註及匯出 CSV。
- 加入電子報訂閱與寄送佇列，並提供取消訂閱流程及各站點的 SMTP 設定。

## 設計取捨

### 預訂需求先進入人工處理佇列

這套流程用來收集住宿詢問與安排後續聯繫。它不會即時鎖定房間，也不處理房態庫存、線上付款、正式訂單或取消作業；這些不屬於目前版本的功能範圍。

### 子站建立後各自維護

子站從範本建立後，文案、圖片、SEO 與站點設定可分開調整。這讓品牌能沿用共同結構，同時保留各站營運內容的自主性。

## 技術

Next.js · TypeScript · React · FastAPI · SQLAlchemy · PostgreSQL · Alembic · Docker Compose

## 公開範圍

公開連結展示 Villa Samaya Awan 官網。本案例說明多站 CMS 與詢問流程的功能範圍，不包含正式環境原始碼、資料庫、帳號、密鑰或住客資料。