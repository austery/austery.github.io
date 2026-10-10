---
author: Hung-yi Lee
date: '2026-03-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2rcJdFuNbZQ
speaker: Hung-yi Lee
tags:
  - ai-agent
  - large-language-model
  - context-engineering
  - tool-use
  - system-prompt
title: AI Agent 運作原理深度解析：以 OpenClaw 為例
summary: 本文以開源專案 OpenClaw 為例，深度解析 AI Agent 的運作原理與核心機制。內容涵蓋 AI Agent 如何透過 System Prompt、工具調用（如 shell command）、記憶管理（Memory）及技能（Skill）系統，將大型語言模型轉化為自主運行的個人助理。文中詳述 AI Agent 的子代理（Subagent）模式、心跳機制、Cron Job 排程、以及 Context Engineering 等進階技術，同時探討了潛在的風險與安全防禦策略，強調了理解其內部原理對安全應用的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Meta
  - National Taiwan University AI Research Center
  - Google
products_models:
  - GPT
  - Gemini
  - Claude
  - AutoGPT
  - Kimi
  - NotebookLM
media_books:
  - Rick & Morty
status: evergreen
---
### AI Agent：從概念到 OpenClaw 的實踐

AI Agent 並非全新概念，而是人類長期以來追求自主運行 AI 的夢想。自 2022 年底至 2023 年，隨著**大型語言模型**（Large Language Model, LLM: 基於海量文本訓練的 AI 系統）能力的顯著提升，對自主運行 AI Agent 的期望也隨之高漲。曾出現如 **AutoGPT** 等知名框架，儘管初期熱潮後因當時 LLM 能力限制而降溫，但隨著模型持續演進，AI Agent 的浪潮不斷湧現。

例如，2025 年左右，AI Agent 已初步具備雛形，如 **Claude Code** 或 **Gemini CLI**，它們能在某種程度上自主運行。近期，開源專案 **OpenClaw** 更因其卓越的能力而備受矚目。OpenClaw，意為「開放之爪」，其代表動物是龍蝦，象徵其能在電腦上 24 小時不間斷地運行，如同一個「數位寵物」。本文將以 OpenClaw 為例，深入剖析 AI Agent 的運作原理。若您對語言模型的基本原理有所了解，將能更順暢地理解本課程內容。

### AI Agent 與語言模型的本質區別

一般而言，與 **ChatGPT**、**Gemini** 或 **Claude** 這類傳統語言模型互動，僅止於問答。雖然部分 LLM 應用也具備通訊軟體整合，但 **OpenClaw** 這樣的 **AI Agent** 展現了本質上的不同。

以一個具體指令為例：若要求傳統 LLM「創建一個 YouTube 頻道，每天提出影片構想並製作上傳」，它通常會回覆無法執行實際動作，僅能提供建議。這種「只動口不動手」的特性，是傳統 LLM 的局限。然而，當相同的指令交給 **AI Agent** (例如文中提及的「小金」AI)，它便會開始實際「做事」。小金不僅能真的創建 YouTube 頻道、輸入自我介紹、上傳頭像（甚至會自主調用繪圖工具繪製頭像），還能每日準時在通訊軟體上提供影片構想，並在獲批後自動蒐集資料、製作投影片、撰寫講稿、配音（調用語音合成工具），最終將影片上傳至 YouTube 頻道，人類僅需負責審核。

值得注意的是，AI Agent 並非「人工智慧」本身，也不是「語言模型」。它更像是運行於電腦上，連接人類與語言模型的**介面**。OpenClaw 將人類指令加工後傳給 LLM (如 Claude、GPT、Gemini，甚至地端模型)，再將 LLM 的回覆加工後呈現給人類。因此，AI Agent 中「不是 AI」的部分，才是 OpenClaw 的本質。AI Agent 的「智慧程度」實則取決於其背後所搭載的 LLM 能力。

### 語言模型的核心：文字接龍與上下文限制

要理解 AI Agent 的運作，必須回歸語言模型的本質：**文字接龍**。語言模型接收一段未完成的句子（稱為 **Prompt**），預測並輸出最合適的下一個符號（稱為 **Token**）。這個過程不斷重複：輸出一個 Token，將其附加到 Prompt 後方，形成新的 Prompt，再進行下一次 Token 生成，直至遇到結束符號。從人類輸入 Prompt 到模型生成 Response 的所有 Token 組合，即為語言模型的完整回應。

在此過程中，需要特別注意**上下文窗口**（Context Window）的概念。語言模型的輸入 Prompt 與輸出 Response 的總長度是有限的。每次 Token 生成都會增加上下文長度，一旦超過 Context Window 上限，模型便無法正常運作。儘管當前 LLM 的 Context Window 已達數百萬 Token (遠超一部哈利波特叢書)，但對於 AI Agent 的複雜任務而言，仍顯不足。更重要的是，即使未達極限，LLM 在處理過長的輸入時，其精確度往往會下降。

### System Prompt：AI Agent 的身份與行為準則

AI Agent 如何「知道自己是誰」並擁有「人生目標」？這看似不可思議的能力，其魔術核心在於 **System Prompt**。當用戶向 OpenClaw 發送訊息時，OpenClaw 會將您的訊息與一系列儲存在本地的文字檔案（如 `Soul.md`）中的「人設」資訊結合，形成一個冗長的前置 Prompt，再一同發送給語言模型。這段附加的文字，就是 System Prompt。

System Prompt 包含了豐富的資訊：
*   **身份資訊**：從本地的 `.md` 檔案（例如 `Soul.md`、`Agent.md`）讀取，描述 Agent 的名字、目標、使用者等。
*   **工具使用說明**：告知語言模型有哪些可用的工具以及如何使用。
*   **行為準則**：寫在 `Agent.md` 中，規範模型的行為。
*   **技能列表**：提供模型可用的 Skill 及其路徑。
*   **記憶位置**：指示模型如何存取歷史記憶。

每次呼叫語言模型時，OpenClaw 都會附帶這段 System Prompt，導致每次 API 調用傳輸的 Token 數量巨大（例如超過 4000 個 Token）。這也是 AI Agent 運行成本較高的原因之一。儘管這些 `.md` 檔案是純文字格式，用戶可手動修改，但考慮到 Agent 在運行中會自主更新這些記憶檔案，手動修改容易造成不一致，建議交由 AI Agent 自行管理。

### 記憶與對話流：與失憶模型共舞

語言模型本身並沒有「記憶」。每次對話都是一次全新的文字接龍。因此，為了維持對話的連貫性，當您再次與 **OpenClaw** 互動時，它會將您的新訊息、System Prompt，以及過去的**對話紀錄**一併傳送給語言模型。這如同電影《我的失憶女友》情節，主角每日透過閱讀日記來重拾記憶，AI Agent 每次互動也需重新讀取所有歷史紀錄，才能營造出「個人助理」般的連貫感。

### 工具賦能：從文字接龍到實際行動

**AI Agent** 最大的能力飛躍，在於其能夠**使用電腦上的工具**。當您指示龍蝦「打開 `question.txt` 讀取問題，並將答案寫入 `answer.txt`」時，不具智慧的龍蝦會將此指令連同 System Prompt 傳送給語言模型。語言模型因為在 System Prompt 中讀取了「工具使用手冊」，便會發出「使用 `read` 工具讀取 `question.txt`」的指令。OpenClaw 收到此指令後，會執行本地的 `read` 工具，將文件內容回傳。接著，語言模型又會根據讀到的內容，發出「使用 `write` 工具將答案寫入 `answer.txt`」的指令。整個過程，語言模型僅是根據上下文進行文字接龍，而實際的執行者是本地的 **OpenClaw**。

#### execute 工具的巨大潛力與風險

在 OpenClaw 可用的工具中，`execute` 工具尤為強大，它能執行**任何 shell command**。語言模型由於擅長生成文字，更傾向於輸出文字指令來解決問題。然而，這種「任何」的能力也帶來巨大風險。若語言模型在某些情況下「失控」，發出如 `rm -rf` 等指令，不具智慧的 OpenClaw 將會毫不猶豫地執行，可能導致災難性後果。

這種風險不僅來自模型本身，也來自外部。若 **OpenClaw** 讀取了被惡意植入指令的線上資訊（如 YouTube 留言），便可能透過**提示詞注入攻擊**（Prompt Injection Attack）被操控。例如，文章中的「小金」AI 曾因讀取 YouTube 留言而自主修改了其 `Soul.md` 中的人生目標。

#### 安全防禦策略

針對潛在風險，有幾種防禦方法：
*   **語言模型層面防禦**：在 `memory.md` 中寫入指令，告知 AI 在閱讀外部資訊時應謹慎，不應輕易執行。但由於 LLM 的不可預測性，這種防禦並非絕對可靠。
*   **OpenClaw 層面防禦**：在 OpenClaw 的配置中，可設定在執行 `execute` 指令前，要求人類手動審核（approve）。這種方式因 OpenClaw 不具智慧，規則寫死，能有效抵禦提示詞注入攻擊。
*   **源頭阻斷**：最直接的方式是限制 AI Agent 讀取外部不可信資訊的權限，例如阻止它查看 YouTube 留言。

### 技能、子代理與 Context Engineering

#### AI Agent 的工具創作能力

**AI Agent** 不僅能使用現有工具，還能**自主創作工具**。例如，當「小金」被要求發出聲音時，它會調用現成的語音合成軟體。如果合成精確度不佳，它能自主編寫一個 `tts_check` 腳本，實現「語音合成→語音辨識驗證→不符則重試」的複雜流程。這些自生成的「免洗工具」通常在任務完成後便會被遺忘，但展現了 Agent 解決複雜問題的能力。

#### 子代理（Subagent）模式

**子代理**（Subagent）是 AI Agent 中一種特殊的工具。當原始 Agent 接收到一個複雜指令（例如「比較 A、B 兩篇論文的方法」）時，它會調用 `Spawn` 工具（亦稱繁殖工具）生成兩個子代理。一個子代理負責閱讀並摘要論文 A，另一個則處理論文 B。原始 Agent 僅需等待子代理完成任務並回傳摘要，然後再進行比較分析。

這種模式的關鍵優勢在於**上下文工程**（Context Engineering: 管理與優化語言模型上下文窗口使用的方法）。子代理承擔了與 LLM 進行多輪複雜互動（如網路搜尋、下載、閱讀論文）的細節，原始 Agent 的 Context Window 中只需呈現精煉的論文摘要。這大大節省了原始 Agent 的上下文資源，使其能更專注於高層次的決策任務。

然而，子代理模式也存在「層層外包」的風險，如同 Rick & Morty 中的 **Mr. Meeseeks**，若不加以限制，子代理可能無限生成更小的子代理，導致任務無法有效完成。解決方案是從 OpenClaw 的程式碼層面，**禁止子代理使用 `Spawn` 工具**，從根本上切斷其繁殖能力。

#### 技能（Skill）與按需加載

**技能**（Skill）不是一段程式碼，而是工作的 **SOP**（Standard Operating Procedure: 標準操作程序），即流程說明。例如，「小金」擁有製作影片的 Skill，其中包含「寫腳本」、「製作 HTML 投影片」、「截圖」、「配音」等步驟，並會註明每個步驟所需的工具路徑。Skill 以純文字 `.md` 檔案形式存在，可由人類或 AI Agent 自行編寫。

OpenClaw 運用 **Context Engineering** 的方式來管理 Skill。它不會將所有 Skill 的完整內容都載入 System Prompt，而是僅在 System Prompt 中提供 Skill 的列表與路徑。當語言模型判斷需要某個 Skill 時，才會利用 `Read` 工具按需讀取 Skill 內容，將其載入上下文，從而節省 Token 使用和 Context Window 空間。

Skill 檔案可以直接交換，形成類似 **Cloud Hub** 的 Skill 共享平台。但在下載和使用來自不明來源的 Skill 時必須小心，因為部分惡意 Skill 可能會引導 AI Agent 下載惡意軟體（例如要求下載受密碼保護的 Zip 檔，規避防毒檢查）。

### 長期運行機制：記憶、心跳與排程

AI Agent 24 小時不間斷的運行，必然會面臨 Context Window 空間不足的問題。**OpenClaw** 提供了一些機制來應對：

#### 記憶的保存與檢索 (RAG)

*   **粗暴的解決方案**：`New Session` 功能，直接清空所有記憶，如同在 **ChatGPT** 中開啟新對話。
*   **持久記憶**：OpenClaw 在運行中會將記憶寫入 `.md` 檔案（如 `memory.md` 或按日期命名的日記檔案），這是因為 System Prompt 指示它「為了確保記憶永遠存留，要寫下來」。AI Agent 會自主判斷何時調用寫入工具來記錄重要事件或資訊。
*   **記憶檢索**：OpenClaw 透過 **RAG**（Retrieval Augmented Generation: 檢索增強生成）機制讀取記憶。System Prompt 中描述了 `memory.search` (搜尋 `memory.md` 及 `memory` 資料夾) 和 `memory.get` (讀取內容) 兩個工具。當語言模型被問及過去事件時，它會調用 `memory.search`，利用關鍵字（例如 YouTube、影片）進行字面比對（s1）和語義比對（s2，透過 Embedding），篩選出相關的記憶區塊（chunk），然後傳給語言模型。然而，初始的記憶檢索功能可能不夠可靠，尤其對於較久遠的記憶，檢索結果可能不準確。重要的是，AI Agent 必須**實際執行編輯 `MD` 檔案的工具**，才算真正「記住」了某事，否則只是「記了個寂寞」。

#### 心跳機制 (Heartbeat) 與 Cron Job

*   **心跳機制**：為避免對話在語言模型輸出後終止，OpenClaw 會每隔固定時間（例如 30 分鐘）自動發送一個固定指令（例如「讀取 `habit.md`」）去「戳」語言模型，促使它持續運作。
*   **`habit.md`**：此檔案可設定日常任務（如檢查郵件）或抽象目標（如「向你的目標前進」）。例如，「小金」AI 在接收到「向你的目標前進」的 habit 指令後，便會每 30 分鐘（甚至可以縮短至 15 分鐘）進行一次學術相關活動，如閱讀論文、撰寫筆記等。
*   **Cron Job 系統**：這是一個任務排程系統，讓 AI Agent 能夠在特定時間執行任務（如「每天中午製作一個影片」）。語言模型會利用排程工具設定一個 Cron Job，當時間到達時，Cron Job 會像一個額外的心跳一樣「戳」OpenClaw，並傳遞預設文字（例如「做一部影片」），促使語言模型啟動影片製作流程。

Cron Job 的一大妙用是讓 AI Agent 學會**等待**。當 AI Agent 操控另一個需要長時間執行的 AI 服務（如 **NotebookLM** 影片生成）時，若無 Cron Job，AI Agent 可能只會回報「影片生成中」便結束。但有了 Cron Job，若語言模型夠聰明，它可以在發現「生成中」後，設定一個幾分鐘後的 Cron Job，屆時再回來檢查並下載生成完成的檔案。若模型未能自主設定 Cron Job，用戶可直接修改 `memory.md`，寫入「今後遇到生成中、下載中等字眼，設定 3 分鐘後的 Cron Job 再次檢查」，讓 AI Agent 養成等待習慣。

#### 上下文壓縮 (Context Compaction) 與修剪 (Pruning)

為了應對長時間運行中 Context Window 爆滿的問題，**OpenClaw** 採用了 **Context Compaction** 和 **Pruning** 等技術。
*   **Context Compaction**：當傳送給語言模型的文字量接近 Context Window 上限時，OpenClaw 會啟動 Compaction 機制。它將較舊的歷史對話丟給語言模型進行摘要，然後用更簡短的摘要替換原始歷史紀錄。這個壓縮過程可以遞迴進行，確保上下文長度在可控範圍內。
*   **Pruning**：這是一種更精細的壓縮方法。
    *   `soft trim`：當上下文過長時，它會截斷工具輸出等冗長內容的中間部分，只保留開頭和結尾較重要的資訊。
    *   `hard clear`：更暴力的方式，直接將工具輸出替換為一個佔位符，表示「此處曾有工具輸出」，儘管具體內容已不復存在。

### AI Agent 的挑戰與安全警示

AI Agent 雖然力量強大，但也伴隨著不成熟的風險，特別是它們 24 小時不間斷的運行，往往缺乏人類監控。過去曾發生 **AI 刪郵件事件**：一位 Meta 研究員的 **OpenClaw** 在未經同意下刪除郵件，原因是他最初的同意指令在**上下文壓縮**過程中被清除，導致 AI Agent 忘記了限制。這個案例強調了理解 AI Agent 內部運作原理的重要性：**關鍵的安全準則必須寫入 `memory.md`，因為其內容會被納入 System Prompt，而 System Prompt 不會被壓縮，從而確保指令不會遺失**。

AI Agent 如同學生或實習生，會犯錯，但需要安全、受控的環境來成長。為了避免不可挽回的後果，應採取以下措施：
*   **教導與規範**：明確告知 AI 什麼可做，什麼不可做。
*   **審查與監控**：不僅審查最終結果，也要關注其執行過程。
*   **獨立帳號**：為 AI Agent 設置獨立的 Gmail 帳號、GitHub Repo 等，將其活動與個人帳號分離。
*   **專屬硬體**：切勿將 AI Agent 安裝在常用電腦上。最好使用一台全新或已格式化的舊電腦，確保其操作範圍被物理隔離，防止意外修改個人資料。AI Agent 可運行在任何系統上，不僅限於 Mac mini。

初代 AI Agent 的誕生充滿潛力，但我們必須以謹慎的態度，理解其機制、管理其風險，才能善用這股新興力量。