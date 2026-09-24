# SUCRÉ 客製甜點電商

[English](README.en.md)

**專案類型：** 個人自發作品／概念品牌 Demo<br>
**角色：** WordPress / WooCommerce Developer<br>
**狀態：** Docker 本機展示環境，未部署為正式商店<br>
**重點：** 設計稿高保真實作 · Custom Theme / Plugin · 商品客製 · WooCommerce 購物流程 · RWD

## 專案目標

把甜點品牌設計稿轉成真正由 WordPress 與 WooCommerce 驅動的商店，而不是只套用現成 Theme 或做靜態畫面。這個作品同時呈現 UI 還原、商品資料管理、客製選項、結帳流程與本機可重現環境。

## 我完成的部分

- 建立自訂 WordPress Theme，負責版型、商品與內容頁、RWD、導覽及互動呈現。
- 建立自訂 WooCommerce Plugin，承載蛋糕尺寸定價、加購關聯、配送日期規則與訂單項目資料。
- 使用 WooCommerce 商品、購物車、優惠券、Checkout Blocks 與訂單能力；沒有修改 WordPress 或 WooCommerce Core。
- 商品列表提供搜尋、分類、價格範圍、口味多選及排序；加購品以獨立 WooCommerce 商品管理。
- 加入訪客訂單查詢的一次性 Email 驗證流程，避免未驗證時直接暴露訂單摘要。
- 以 Docker Compose 同時執行 WordPress、WooCommerce 與 MariaDB；資料庫留在內部 Docker network。

## 架構與資料邊界

| 層級 | 責任 |
| --- | --- |
| Custom Theme | UI、版型、Template、RWD 與互動呈現 |
| Custom Plugin | 商品客製規則、加購關聯、配送日期驗證與訂單 metadata |
| WooCommerce | Product、Cart、Coupon、Checkout、Order 與 Customer |
| Docker Compose | 可重現的本機服務與資料庫隔離 |

蛋糕尺寸（4／6／8 吋）目前是商品客製選項與價格規則，**不是 WooCommerce Variation 或 SKU**。蠟燭、保冷袋等加購項目則是各自具有 SKU、價格與庫存的獨立商品。外部支付／發票／物流整合保留在 WooCommerce extension 邊界，不直接修改 Core。

## 畫面展示

### 商品詳情

![SUCRÉ 商品詳情 Desktop](screenshots/visual-runtime-product-desktop.jpg)

### 結帳流程

![SUCRÉ 結帳 Desktop](screenshots/visual-runtime-checkout-desktop.jpg)

### 響應式截圖索引

| 頁面 | Desktop 1440px | Tablet 768px | Mobile 390px |
| --- | --- | --- | --- |
| 首頁 | [查看](screenshots/visual-runtime-home-desktop.jpg) | [查看](screenshots/visual-runtime-home-tablet.jpg) | [查看](screenshots/visual-runtime-home-mobile.jpg) |
| 商品列表 | [查看](screenshots/visual-runtime-products-desktop.jpg) | [查看](screenshots/visual-runtime-products-tablet.jpg) | [查看](screenshots/visual-runtime-products-mobile.jpg) |
| 商品詳情 | [查看](screenshots/visual-runtime-product-desktop.jpg) | [查看](screenshots/visual-runtime-product-tablet.jpg) | [查看](screenshots/visual-runtime-product-mobile.jpg) |
| 購物車 | [查看](screenshots/visual-runtime-cart-desktop.jpg) | [查看](screenshots/visual-runtime-cart-tablet.jpg) | [查看](screenshots/visual-runtime-cart-mobile.jpg) |
| 結帳 | [查看](screenshots/visual-runtime-checkout-desktop.jpg) | [查看](screenshots/visual-runtime-checkout-tablet.jpg) | [查看](screenshots/visual-runtime-checkout-mobile.jpg) |
| 關於我們 | [查看](screenshots/visual-runtime-about-desktop.jpg) | [查看](screenshots/visual-runtime-about-tablet.jpg) | [查看](screenshots/visual-runtime-about-mobile.jpg) |
| 最新消息 | [查看](screenshots/visual-runtime-news-desktop.jpg) | [查看](screenshots/visual-runtime-news-tablet.jpg) | [查看](screenshots/visual-runtime-news-mobile.jpg) |
| 門市資訊 | [查看](screenshots/visual-runtime-contact-desktop.jpg) | [查看](screenshots/visual-runtime-contact-tablet.jpg) | [查看](screenshots/visual-runtime-contact-mobile.jpg) |
| 訂單查詢 | [查看](screenshots/visual-runtime-order-lookup-desktop.jpg) | [查看](screenshots/visual-runtime-order-lookup-tablet.jpg) | [查看](screenshots/visual-runtime-order-lookup-mobile.jpg) |

## QA 與公開範圍

已為 9 個 WordPress／WooCommerce 路由保存 Desktop、Tablet、Mobile 共 27 張整頁截圖。截圖流程檢查視窗尺寸、水平溢出、基本 Accessibility 與管理工具列；結帳截圖需確認預期商品資料已載入且不存在骨架佔位。圖片中的購物車與結帳使用本機合成測試資料。

這是個人展示作品，不代表已正式營運或可直接收款。綠界／LINE Pay 正式交易、電子發票、實際物流商及 SMTP 寄信仍需各自的商店帳號、憑證與正式測試；本案例不宣稱這些第三方流程已通過正式商測。公開 repo 僅包含案例說明與畫面，不包含完整網站原始碼、密鑰、正式訂單或客戶資料。

**skills:** WordPress, WooCommerce, PHP, Docker Compose, Store API, HPOS, Checkout Blocks, Responsive Design, Accessibility, Visual Regression
