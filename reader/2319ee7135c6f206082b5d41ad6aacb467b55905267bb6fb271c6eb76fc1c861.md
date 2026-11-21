---
author: Hung-yi Lee
date: '2025-12-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ccqCDD9LqCA
speaker: Hung-yi Lee
tags:
  - autoregressive-model
  - flow-matching
  - diffusion-model
  - tokenization
  - vector-quantization
title: 影像與聲音的生成策略：擴散模型與自回歸架構的深度匯聚
summary: 本講由李宏毅教授解析生成式 AI 在影像與語音領域的核心技術演進。內容涵蓋從早期的像素與取樣點接龍，到現代離散與連續 Token 的表徵技術，並重點探討了 Flow Matching 與擴散模型如何與自回歸架構結合，揭示 2025 年跨模態生成技術的前沿趨勢。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - 李宏毅 (Hung-yi Lee)
companies_orgs:
  - Google
  - OpenAI
  - Meta
products_models:
  - NanoBanana
  - Sora
  - Flow Matching
  - MaskGIT
  - VAR
media_books: []
status: evergreen
---
### 生成新紀元：從文字接龍到多模態模擬

目前為止，生成式人工智慧的討論核心大多集中在**語言模型**（Language Model: 處理文本輸入與輸出的系統），其本質是透過文字接龍來預測下一個字。然而，生成技術的邊界已延伸至影像、影片與聲音。以 Google 的 **NanoBanana** 為例，它能根據指令生成極其逼真的 PTT 八卦板貼文截圖，甚至能模擬螢幕呈現的微小瑕疵與像素模糊；在語音領域，**語音合成**（Speech Synthesis: 將文字轉換為人工語音的技術）已進步到僅需輸入一段參考音頻，即可模仿特定語者的音色與情感進行跨語言配音。

這種能力的躍遷不僅限於靜態內容。**Sora** 等模型展示了文字生影片的驚人潛力，它能理解物理邏輯並生成帶有環境音效的動態畫面。有趣的是，這些模型甚至開始展現出某種「世界模型」的雛形，例如能自動補全線性代數考卷的解答，或模擬教授授課的場景。在這些表象背後，影像與聲音生成的底層邏輯正發生深刻變革：從傳統的擴散模型（Diffusion Model）轉向一種結合了**自回歸**（Auto-Regressive: 基於過去預測未來的序列生成方法）與**流匹配**（Flow Matching: 透過向量場指引機率分布轉換的技術）的新路徑。

### 數位原子：像素、取樣點與 Token 的層級演進

要理解生成策略，必須先定義生成的基本單位。在影像中，最小單位是**像素**（Pixel: 構成數位影像的最小點），每個像素由 RGB 三個數值組成；在聲音中，則是**取樣點**（Sampling Point: 對連續聲波進行離散化取樣後的數值點）。早在 2016 年的「寒武紀時期」，**Pixel RNN** 與 **WaveNet** 就嘗試以像素或取樣點進行接龍。然而，这种微觀層級的生成效率極低——生成一秒鐘的音頻可能需要 90 分鐘的運算，因為取樣點過於細碎。

為了提升效率，研究者引入了 **Token**（權標：資訊處理的基本語意單位）的概念。這就像人體由細胞而非原子構成一樣，影像與語音也需要更大的「細胞」來作為生成單位。透過 **Tokenization**（符號化：將連續信號轉換為離散符號的過程），我們可以將 320 個取樣點壓縮為一個語音 Token。這通常依賴於 **VQ-VAE**（Vector Quantized Variational Autoencoder: 向量量化的變分自編碼器）技術，將連續的信號映射到有限的編碼本中。儘管這種離散化過程會帶來一定的資訊失真，但它賦予了影像與聲音像文字一樣進行高效接龍的可能性。

### 語意建模：從 Raster Order 到隨機生成的邏輯轉向

在具備了 Token 之後，生成的順序成為關鍵。傳統做法是遵循 **Raster Order**（柵欄式順序：由左至右、由上而下的掃描順序），但這並不符合人類創作的邏輯。**MaskGIT** 提出了一種全新的策略：**掩碼生成**（Masked Generation: 隨機遮蓋部分內容並預測剩餘部分的技術）。在訓練時，模型學習如何還原被蓋住的圖片區域；在生成時，模型先產生全局草圖，再逐步細化高信心的區域，最終達成非固定順序的並行生成。

這種「層級化」的思想在 **VAR**（Visual Auto-Regressive: 視覺自回歸建模）中得到了進一步發揮。模型不再是一步到位生成高清圖像，而是先生成低解析度的「草圖」，再根據草圖逐步預測更高比例尺的細節。這種從小圖到大圖的 **Next-Scale Prediction**（跨尺度預測），不僅提升了生成品質，也讓模型能更好地捕捉全局語意與局部特徵之間的關聯。然而，隨著對解析度要求的提高，離散 Token 的壓縮極限（如蒙娜麗莎畫像中的臉部扭曲）成為了技術瓶頸。

### 範式匯聚：連續 Token 與流匹配的向量博弈

為了解決離散 Token 的失真問題，2025 年的前沿趨勢是轉向 **連續 Token**（Continuous Token: 以實數向量而非離散索引表示的單位）。但連續空間的生成面臨一個巨大挑戰：**均方誤差**（Mean Square Error: 預測值與真實值差距的平方均值）在多目標場景下失效。如果一隻狗既可以出現在左邊也可以在右邊，MSE 會引導模型生成一個模糊的雙頭狗。因此，我們需要模型輸出的是一個**機率分布**而非單一向量。

這正是 **Flow Matching**（流匹配）發揮作用的地方。它定義了一個**向量場**（Vector Field: 空間中每一點及其移動方向的集合），像一位嚮導般指引點從原始分布（Source Distribution）平滑地移動到目標分布（Target Distribution）。這與擴散模型在數學上互補，但在實作上更為高效。透過將這種生成能力植入 Transformer 架構的 **Generation Head**（生成頭：模型末端負責特定模態輸出的組件），我們實現了兩條世界線的匯聚：Transformer 負責宏觀的語意接龍，而 Generation Head 負責微觀的機率分布採樣。這種結合了自回歸深度與生成式廣度的架構，正成為 Video VAR 與語音語意模型（Speech Language Model）的標準範式。