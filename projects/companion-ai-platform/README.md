# 陪伴型 AI 語音與 Agent 平台

[English](README.en.md)

**期間：** 2026/08 – 2026/09<br>
**專案類型：** 商業專案／全職工作<br>
**角色：** Full-stack / AI Application Engineer<br>
**重點：** 即時語音 · WebSocket · Agent Runtime · 記憶與權限

## 這個專案在做什麼

這是一套陪伴型 AI 平台，除了語音對話，也處理記憶、知識檢索，以及家屬和照護人員的存取。前端包含 LIFF、一般 Web 與管理介面，後端則透過 Gateway 維持即時語音 Session。

## 我實際做的部分

- 串起 STT → LLM → TTS 的語音對話生命週期
- 管理 utterance、transcript、generation 與播放狀態
- 處理 WebSocket 斷線後的 Session Continuity、回放和取消
- 讓後台可以設定 MCP、Tools、Skills、Knowledge Base 與外部搜尋
- 分開長者、家屬與照護人員的資料權限、記憶保留和刪除流程
- 加入 Socket、Request、Log 與 Container Resource 限制
- 維護較容易理解的語音、閱讀模式與回放操作

## 真正麻煩的不是 STT → LLM → TTS

語音功能真正麻煩的不是三個服務串起來，而是中間的狀態。使用者可能還在錄音，上一段語音正在播放，又剛好斷線重連。如果只用一個 conversation state，很容易互相蓋掉，所以後來把 utterance、generation 和播放狀態分開管理。

### 轉錄回來的順序不能直接當成回答順序

部分轉錄、最終轉錄和 generation 可能不是按照畫面收到的順序完成。我把 turn 和 generation 綁在一起，讓晚到的舊轉錄不會啟動錯誤的回答，也不會讓舊 Socket 取消新的 generation。

### 斷線不能讓目前的對話消失

WebSocket 斷線後，系統要知道目前是可以恢復、應該停止，還是需要提示使用者重新開始。我把 Session Continuity、identity、expiry 和 stale socket 檢查放在同一組規則裡處理。

### Agent 能力要能被控制

MCP、Tools、Skills、Knowledge Base 和外部搜尋不是每個情境都要開啟，所以把它們放在後台設定與 Provider 邊界中。對話流程不直接綁死某一個搜尋服務，工具參數也要先經過限制。

## 架構與流程

![陪伴型 AI 架構](diagrams/system-architecture.svg)

- [語音 Agent Pipeline](diagrams/voice-agent-pipeline.svg)
- [Agent Runtime](diagrams/agent-runtime.svg)
- [Mermaid 原始圖](diagrams/system-architecture.mmd)

## 畫面展示

以下畫面展示陪伴型 AI 的語音入口、文字互動與回憶功能；未包含正式使用者資料或服務品牌。

![陪伴型 AI 首頁](screenshots/companion-home.png)

![陪伴型 AI 文字對話](screenshots/companion-chat.png)

## 技術

應用層使用 TypeScript、LIFF、Fastify、React 與管理／家屬 Web；即時通訊使用 WebSocket；AI 流程包含 STT、LLM、TTS、Agent Tools 與知識檢索；資料使用 PostgreSQL、Redis，部署以 Docker 為主。

**skills:** Node.js, Fastify, React, WebSocket, LLM, Agent, MCP, Tools, Skills, STT, TTS, SearXNG, ElevenLabs

## 取捨與公開範圍

即時語音仍會受到瀏覽器權限、網路和外部語音服務影響。公開內容只描述應用程式層的狀態協調、恢復、權限與資源控制，不包含正式個人資料、憑證或第三方 Provider 的 SLA 承諾。
