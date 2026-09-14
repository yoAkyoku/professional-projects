# Memoa AI 語音 Agent

[English](README.en.md)

**期間：** 2026/08 – 2026/09<br>
**專案類型：** 商業專案／全職工作<br>
**角色：** Full-stack / AI Application Engineer<br>
**重點：** Realtime Voice Agent · WebSocket · STT → LLM → TTS · Privacy

## 一、專案概述

結合即時語音互動、記憶、知識檢索與家屬／照護人員存取的語音陪伴與照護平台。

## 二、專案背景

語音互動比一般頁面請求更重視狀態協調。系統需要同時處理麥克風、轉錄、生成、播放、取消、重新連線與對話擁有權，並且不能遺失使用者上下文。

## 三、我的角色

我負責 TypeScript 應用、LIFF 與 Web 介面、Gateway、WebSocket 語音流程、STT → LLM → TTS、對話與記憶、家屬／照護存取，以及可靠性、隱私與資源限制。

## 四、負責範圍

- 建立語音對話生命週期
- 管理轉錄擁有權與 utterance 狀態
- 處理 generation cancellation 與播放狀態
- 支援斷線後的 Session Continuity
- 開發後台動態啟用 MCP、Tools、Skills、Knowledge Base 與外部搜尋的設定流程
- 實作語音與辨識設定
- 改善長者易讀與易操作介面
- 支援回放、閱讀模式與語音控制
- 分離長者、家屬與照護人員資料權限
- 管理記憶、知識、保留與刪除流程
- 加入 Socket、Log、Container Resource 與 Request 限制
- 整合自架外部搜尋，並明確區分 Provider 邊界

## 五、技術環境

- Applications：TypeScript、LIFF、Fastify、Admin Web、Family Web
- Realtime：WebSocket
- AI：Speech-to-text、LLM、Text-to-speech、Agent Tools
- Data：PostgreSQL、Redis
- Infrastructure：Docker、Shared Search Gateway、External AI Providers

**skills:** Node.js, Fastify, React, WebSocket, LLM, Agent, MCP, Tools, Skills, STT, TTS, SearXNG, ElevenLabs

## 六、系統架構

![Memoa 架構](diagrams/system-architecture.svg)

- [Mermaid 原始圖](diagrams/system-architecture.mmd)
- [語音 Agent Pipeline](diagrams/voice-agent-pipeline.svg)
- [Agent Runtime](diagrams/agent-runtime.svg)

## 七、主要工程挑戰

### 協調即時語音回合

一段對話可能同時包含錄音、部分轉錄、最終轉錄、生成、播放與取消。我將這些狀態拆開，並綁定至正確的 utterance 與 generation。

### 斷線後恢復對話

WebSocket 斷線不應直接遺失長者正在進行的對話，因此建立 Session Continuity，並明確定義恢復、結束與錯誤提示。

### 避免不同 Session 互相影響

系統不能回答錯誤房間、使用別人的轉錄，也不能讓舊 Socket 關閉新的對話，因此強化 identity、expiry 與 generation ownership 檢查。

### 讓複雜設定容易理解

語音、節奏、校正、閱讀模式與回放功能需要適合長者使用，因此簡化互動方式並改善狀態回饋。

## 八、技術決策

- 將每個 conversation turn 與 generation 視為明確單位。
- 讓播放與取消只作用於產生該回覆的 generation。
- 在保留上下文的同時維持權限邊界。
- 將記憶保留與刪除設計成明確的資料生命週期操作。
- 將搜尋 Provider 細節封裝，避免對話流程直接耦合外部服務。

## 九、可靠性與安全性

- Session 與 Identity 驗證
- Reconnect 與 Stale Socket 處理
- Request 與 Socket 限制
- Container Memory 與 Log 限制
- Care Panel Authorization
- Retention 與資料刪除
- Outbound Tool Argument 保護
- External Provider Failure State

## 十、重製畫面

- [Voice Conversation](screenshots/conversation.svg)
- [Voice Settings](screenshots/voice-settings.svg)

以上均為去識別化重製畫面，使用範例資料，不是正式客戶截圖。

## 十一、取捨與限制

即時語音品質會受到瀏覽器權限、網路與外部語音服務影響。本案例聚焦於應用程式層的流程協調與恢復行為，不宣稱第三方 Provider 的正式 SLA。

## 十二、成果

將語音助手從單純互動擴展為具備狀態管理、斷線恢復、播放控制、記憶邊界與照護權限的對話 Runtime。

## 十三、學習

這個專案讓我實際理解即時系統的正確性不只取決於模型輸出，也取決於擁有權、取消、時序、資源限制與使用者能否理解目前狀態。

## 保密聲明

這是商業專案。公開內容不包含正式原始碼、憑證、個人資料或專有商業資訊。
