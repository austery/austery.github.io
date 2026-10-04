---
author: Hung-yi Lee
date: '2026-03-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Ll-wk8x3G_g
speaker: Hung-yi Lee
tags:
  - positional-embedding
  - transformer-architecture
  - rope
  - context-window-extrapolation
  - self-attention
title: Transformer 位置編碼深度解析：從絕對、相對到旋轉編碼與長度外推
summary: 本課程深入探討了 Transformer 模型中位置編碼技術的演進。內容涵蓋了位置編碼的數學原理、Self-Attention 的置換不變性、絕對與相對位置編碼（如 Sinusoidal 與 ALiBi）、當前主流的旋轉位置編碼（RoPE）及其長度外推策略（如 NTK-aware、YARN），最後討論了位置編碼在訓練中的必要性及 DroPE 策略。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Transformer
  - LLaMA
  - Qwen
  - Gemma
  - T5
media_books: []
status: evergreen
---
### 置換不變性：為什麼 Transformer 需要位置資訊？

大型語言模型背後的核心架構是 **Transformer**。在處理輸入的 **Token**（最小語言單位）時，Transformer 會先將其轉換為 **Embedding**（向量：代表語義的高維度數值列表）。然而，Transformer 內部最關鍵的 **Self-Attention**（自注意力機制：讓模型在處理某個字時能參考上下文的模組）在計算過程中其實存在一個本質上的缺陷：它無法感知順序。

在 **Self-Attention** 的運算中，每個向量會分別乘上三個矩陣轉成 **Query**（查詢）、**Key**（鍵）與 **Value**（值）。當我們計算某個位置的輸出時，是將該位置的 Query 與所有位置的 Key 做內積算出 **Attention Weight**（注意力權重），再對 Value 進行加權總和。這個過程本質上是與位置無關的。舉例來說，如果我們將輸入順序從“你打我”對調成“我打你”，對於最後一個位置算出來的 Embedding 結果竟然是一模一樣的。這種 **置換不變性**（Permutation Invariance：輸入順序改變而輸出結果不變的特性）會導致模型無法區分語義完全不同的句子。因此，我們必須人為地引入 **位置編碼**（Positional Embedding: 用於標記序列中位置資訊的附加向量），讓模型知道 Token 之間的先後順序。

### 絕對位置編碼：Sinusoidal 的指針智慧

最早解決這個問題的方法是 **絕對位置編碼**（Absolute Positional Embedding）。其核心思想是對序列中的每一個位置（如位置 0、1、2...）設計一個獨特的向量，並將這個向量直接加到 Token Embedding 上。當同一個詞出現在不同位置時，加上去的編碼不同，模型看到的輸入也就不同。在 Transformer 誕生之初，作者採行了著名的 **正弦位置編碼**（Sinusoidal Positional Embedding：利用三角函數週期性生成的編碼方式）。

這套編碼系統雖然數學公式看起來複雜，但我們可以將其視覺化為一組由“指針”組成的系統。如果一個位置向量有 128 個維度，每兩個維度可以組成一個二維平面上的指針。**Sinusoidal 編碼** 實際上是為模型提供了 64 個轉動速度完全不同的指針。最前面的維度像“秒針”，轉動極快，大約每 6.3 個 Token 就轉一圈；最後面的維度則像“時針”甚至更緩慢的指針，可能需要五萬多個 Token 才會轉一圈。當模型看著這 64 個指針的不同夾角時，它就能精確地定位出當前 Token 在句子中的位置。

### 策略性臨在：從絕對位置轉向相對關係

雖然 Sinusoidal 是一種絕對編碼，但 Transformer 的作者在論文中提到一個微言大義的設計初衷：他們希望位置編碼能考慮 **相對位置**（Relative Position）。在理解語言時，絕對位置（它是第 100 個字）往往不如相對位置（這兩個字中間隔了兩個詞）來得重要。無論“貓吃了魚”這句話出現在小說的開頭還是結尾，貓與魚之間的語法關係應該保持一致。

**Sinusoidal 編碼** 具備一個巧妙的數學性質：第 $K+R$ 個位置的編碼 $P_{K+R}$ 可以透過第 $K$ 個位置的編碼 $P_K$ 乘上一個只與相對距離 $R$ 有關的矩陣 $M_R$ 來得到。這意味著在計算內積（Attention）時，結果中會包含一項直接反映相對距離的資訊。基於對相對關係的重視，後來發展出了 **ALiBi**（Attention with Linear Biases: 帶有線性偏置的注意力機制）。ALiBi 採取了更簡單粗暴的做法：直接捨棄位置向量，在計算 Attention 分數時，根據 Token 之間的物理距離直接減去一個常數偏置。距離越遠，Attention 分數就越小。實驗證明，這種簡單的規則在處理長文本時，效果竟然全面碾壓了複雜的 Sinusoidal 編碼。

### 旋轉位置編碼：RoPE 的印記與優勢

在位置編碼的演進史上，**RoPE**（Rotary Positional Embedding：旋轉位置編碼）最終成為了當前 LLaMA、Qwen 等主流模型的核心技術。RoPE 的做法不再是簡單地“加”一個向量，而是將旋轉的角度作為位置的印記。它將 Query 和 Key 向量兩兩分組，根據所在的位置對其進行不同角度的旋轉。

RoPE 之所以強大，是因為它完美地融合了絕對編碼的形式與相對編碼的特點。它在數學上保證了兩個向量做內積時，結果只取決於它們之間的相對角度差（即相對距離），且完全不影響原有的 Attention 運算流程。這使得它能與 **Flash Attention**（加速注意力運算的技術）或 **KV Cache**（鍵值緩存：提升推理速度的緩存機制）等優化手段無縫相容。此外，RoPE 雖然在趨勢上會讓遠距離的權重變小，但它不像 ALiBi 那樣強迫權重必須隨著距離遞減，這賦予了模型更細緻的表達能力，例如模型可以學會跳過無意義的虛詞，直接關注到數個位置之前的核心動詞。

### 長度外推挑戰：如何讓模型處理未見之長？

在實際應用中，我們經常面臨 **Train Short Test Long** 的困境：模型在訓練時只看過 2048 個 Token，但測試時我們希望它能讀完一整本書。如果直接給 RoPE 超過訓練長度的 index，模型會看到從未見過的旋轉角度而“發瘋”。為了擴張 **Context Window**（上下文窗口：模型能同時處理的最大文本長度），研究者提出了多種縮放策略。

最直覺的方法是 **位置插值**（Position Interpolation: 將長序列的位置索引縮放到訓練範圍內）。例如要處理兩倍長的文本，就將所有編號除以 2。然而，後來的研究發現不同頻率的維度應該採取不同策略，這促成了 **NTK-aware Scaling**（基於神經切線核理論的縮放方法）。其核心邏輯是：對於旋轉極快的高頻指針（秒針），即便索引超過範圍，它也只是在圓圈內多轉幾圈，模型仍能處理；但對於旋轉極慢的低頻指針，必須進行壓縮。後續的 **YARN** 則進一步優化了這種頻率分布的縮放曲線。此外，**Dynamic Scaling**（動態縮放）則主張在推理時根據實際輸入長度動態調整縮放倍率，確保短文本時性能不下降，長文本時能舉一反三。

### 靈魂叩問：我們真的需要位置編碼嗎？

在課程的最後，講師提出了一個顛覆性的觀點：**Self-Attention** 其實可能自帶位置資訊。根據 **NoPE**（No Positional Embedding）的研究，即使不加任何編碼，Transformer 只要堆疊超過一層，第二層的 Token Embedding 就已經融合了周圍的資訊，從而產生了隱含的位置特徵。

既然如此，為何主流模型仍堅持使用位置編碼？答案在於訓練效率。雖然模型最終能學會隱含位置，但在訓練初期，如果不提供明確的導航（位置編碼），模型會學得非常慢且效果較差。最新的研究 **DroPE** 提出了一個如《金剛經》般富有哲理的策略：“法尚應捨，何況非法”。位置編碼就像是一條載人過河的船（筏），在訓練初期它至關重要，但當模型學到一定程度後，將位置編碼“丟掉”反而能解除長度的束縛，讓模型展現出超越訓練長度的外推能力。這暗示了位置編碼的終極形態，或許是作為訓練的輔助工具，而非模型永久的枷鎖。