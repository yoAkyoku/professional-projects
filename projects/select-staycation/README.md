# Select Staycation 多站旅宿官網與內容管理系統

[English](README.en.md) · [公開網站：Select Staycation](https://selectstaycation.com)

![Select Staycation portfolio cover](../../assets/project-covers/select-staycation-cover.png)

**專案類型：** 客戶專案／旅宿網站與 CMS  
**角色：** Full-stack Engineer  
**重點：** 多站內容管理 · 住宿篩選 · 中英管理介面 · 詢問型預訂

## 專案概覽

為旅宿品牌建立可管理多個站點的網站與內容管理系統。公開官網呈現 Select Staycation 的品牌、住宿與服務資訊；管理平台可建立品牌站點，並維護住宿、頁面、媒體與行銷內容。

## 官網畫面

以下截圖呈現 Select Staycation 的品牌首頁、住宿篩選、空間展示與餐宴服務。

### 1. 品牌首頁與預約入口

全幅旅宿影像搭配品牌介紹、網站導覽與預約入口。

![Select Staycation 品牌首頁與預約入口](screenshots/01-home-hero.png)

### 2. 住宿篩選與品牌介紹

依縣市、地區、人數、服務設施與體驗條件探索住宿，並透過圖文區塊介紹品牌。

![Select Staycation 住宿篩選與品牌介紹](screenshots/02-stay-search-and-brand.png)

### 3. 空間影像與聯絡引導

以泳池、浴室與室內空間照片呈現住宿環境，搭配需求諮詢與住宿瀏覽入口。

![Select Staycation 空間影像與聯絡引導](screenshots/03-gallery-and-contact.png)

### 4. 餐宴與服務內容

以分類與卡片整理私廚晚宴、外燴服務、烤肉及戶外餐飲企劃。

![Select Staycation 餐宴與服務內容](screenshots/04-dining-services.png)

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

公開連結與截圖展示 Select Staycation 官網前台。本案例說明多站 CMS 與詢問流程的功能範圍，不包含正式環境原始碼、資料庫、帳號、密鑰或住客資料。
