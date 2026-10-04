---
author: TechButMakeItReal
date: '2026-04-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iGvDDmUDRv8
speaker: TechButMakeItReal
tags:
  - ai-economics
  - data-center
  - hyperscaler
  - gpu-compute
  - infrastructure
title: AI 淘金热下的铲子商：谁分走了你的 20 美元订阅费？
summary: 本文深度解析了 AI 产业背后的利益链条。当你按下回车键时，资金会流向边缘服务器、云服务商、GPU 厂商、数据中心业主和电力公司等六个层级。尽管 OpenAI 等模型公司面临巨大的波动风险，但处于底层的超大规模服务商和数据中心 landlords 却通过长期合约锁定了稳定利润，成为这场 AI 浪潮中真正的赢家。
insight: ''
draft: true
series: ''
category: business-entrepreneurship
area: finance-wealth
project: []
people: []
companies_orgs:
  - OpenAI
  - Microsoft
  - Microsoft Azure
  - AWS
  - CoreWeave
  - Cloudflare
products_models:
  - ChatGPT
  - Claude
  - Gemini
  - GPT-4
media_books: []
status: evergreen
---
### 淘金热与铲子商：AI 产业链的价值链条

**1849 年是淘金热，2026 年则是 GPU 热潮。** 正如历史所昭示的那样，卖铲子的人往往比挖金矿的人赚得更多。当你每月支付 20 或 30 美元的 AI 订阅费时，这笔钱会被拆解并流向半打你从未见过的企业。从你按下回车键的那一刻起，资金就开始在多个资产负债表之间发生连锁反应。

在 AI 产业链中，每一层都在分一杯羹，但利润分配并不均匀。最底层的**基础设施层**（Infrastructure Layer）——包括 GPU 租赁、数据中心容量和电力供应——拥有最稳定且持久的现金流。无论哪个模型在这个季度走红，无论用户选择哪个智能体，底层的“铲子商”都不在乎，他们只在乎用户在持续不断地消耗**分词**（Tokens: 模型处理文本的基本单位）。

<details><summary>Original English Source</summary>
Every time you send a message in Claude, Gemini, or GBT, multiple companies make money. Behind that one prompt, money goes out to half a dozen businesses you never see, and each layer gets paid, but not equally. 1849 had the gold rush. 2026 has GPUs. And just like then, the people selling the shovels are making more money than anyone digging for the gold. This is part two of our video, the business of data centers. By the end of this video, you'll be able to trace your own AI message all the way down that stack. Who gets paid on what terms? And how are all of these parties connected under the surface?
</details>

### 从请求到推理：资金如何流经云端？

当你输入指令并点击发送，请求会首先经过**边缘服务器**（Edge Server: 靠近用户的分布式服务器，用于加速数据传输）。这些服务器由 Cloudflare 或 AWS CloudFront 等提供商运营，OpenAI 会为此支付极小部分的费用。随后，请求进入 OpenAI 的 **API 网关**（API Gateway: 处理身份验证、配额检查和请求路由的系统），并转发至位于数据中心的**推理集群**（Inference Cluster）。

在这个阶段，大部分资金流向了**云服务提供商**（Cloud Provider）。以 OpenAI 为例，其主要合作伙伴是微软 Azure，双方签署了高达 2500 亿美元的计算合约。此外，OpenAI 还会向 CoreWeave 支付约 224 亿美元，向 AWS 支付约 380 亿美元。根据请求的具体调度情况，这些云巨头会赚取计算和网络时间的收入。

<details><summary>Original English Source</summary>
When you press enter, a request with your message, your authentication, your conversation ID, and the model that you selected travels over the internet to an edge server near you that processes your request. The edge server can be operated by different providers like Cloudflare or AWS CloudFront. The edge server receives your request and forwards it to the nearest OpenAI data center. Then, the request hits OpenAI's API gateway. It authenticates me as a legitimate user. It sends my request to a certain model and then forwards the request to an inference cluster. During this step, the money goes to the cloud provider. In OpenAI's case, it's usually Microsoft Azure. Because Microsoft is OpenAI's primary compute partner under a committed $250 billion contract. For some workloads, OpenAI can also round to Corewave because they have another $22.4 billion contract with Core Weave or to AWS. That's another $38 billion deal.
</details>

### 分词成本：为什么“礼貌”会让你变穷？

计算成本的核心单位是 **分词**（Token）。文本在进入模型前，由 **分词器算法**（Tokenizer Algorithm: 将原始文本转换为模型可识别的数字编号的程序）进行处理。不同的模型（如 Claude 和 GPT）使用不同的算法，因此相同的提示词价格各异。**基本规律是：分词越多，计算量越大，查询就越贵。**

一个有趣的洞察是：在与 AI 交流时保持“礼貌”（如说“请”或“谢谢”）实际上会增加你的成本。这些礼貌用语不仅消耗了输入分词，还会引导模型以更友好且更长的方式回复，从而产生更多的输出分词。因此，模型公司通常建议用户直接下令，因为你的礼貌正真金白银地燃烧着 GPU 时间。

<details><summary>Original English Source</summary>
Now my raw text is passed to the model. And the model takes the input and turns my words into tokens because the model can only work with numbers. Different LLMs use different tokenizer algorithms which is the reason why the same prompt can be priced differently on claude versus GBT. But the rule of thumb is the more tokens, the more compute and the more expensive the query. For example, a typical message plus response is roughly 500 tokens combined. The extra please and thank you add tokens to your prompt. And when you add those words, it also makes the model respond in a friendlier and longer way, which adds the number of output tokens. This is why you can read in multiple resources that the model companies ask people to not be polite with LLMs and say hello or thank you because your politeness costs quite a bit.
</details>

### 推理的物理极限：GPU 内存与预填充 phase

一旦文本转换为数字列表，CPU 会将其复制到 GPU 的 **高带宽内存**（High Bandwidth Memory, HBM）中。这里涉及到一个关键的物理组件：模型权重。**模型权重**（Model Weights: 神经网络中决定信息传递强度的参数）在加载后会一直常驻在 GPU 内存中，这就是为什么 AI 推理需要昂贵的专用芯片，而不是普通的笔记本内存。

推理分为两个昂贵的阶段：
1. **预填充阶段**（Prefill Phase）: 所有输入分词并行推过模型层，并生成 **键值缓存**（KV Cache: 存储已处理分词的中间计算结果以加速后续生成的缓存）。这会消耗大量高速内存。
2. **解码阶段**（Decode Phase）: 这是最烧钱的步骤。模型必须逐个生成分词（Token 1, 2, 3...），无法并行化。这也是为什么你会看到“打字机效果”。**解码阶段是真正的“计费器”在疯狂转动。**

<details><summary>Original English Source</summary>
The CPU copies that into the GPU's high bandwidth memory so that the model can process your request. Every model requires a certain amount of memory in a chip for model weights. Those weights were loaded once and they never get unloaded. They sit in the GPU memory continuously. Once the prompt is in the GPU memory, the model runs the prefill phase. The model writes key and value vectors for each token into the key value cache in high bandwidth memory. The key value cache grows with the number of layers and with the number of tokens. Then decode. This is where the most money is being spent. This is the step when the model generates output and this process cannot be parallelized. From a money perspective, the decode step is the meter really running. This is where you burn most of your GPU time.
</details>

### 超大规模服务商：AI 时代的数字地主

处于产业链最顶端的是 **超大规模服务商**（Hyperscalers: 指 AWS、Azure 和 Google Cloud 等拥有海量计算和网络资源的云巨头）。虽然表面上是云公司，但从经济角度看，他们更像是电力公用事业、地主和批发商的混合体。他们与数据中心运营商签署 10-15 年的租约，与发电厂签署 20 年的购电协议。

通过这种方式，超大规模服务商控制了稀缺的电力和土地资源，并将其包装成高利润的云服务。对于像 OpenAI 这样的公司，他们面临着使用量波动、市场竞争和模型过时的风险；而对于微软 Azure 而言，只要有 OpenAI 这样的长期承诺客户，无论市场如何波动，其收入线都是锁定的。这种风险特征的**完全倒置**，使得基础设施层成为了最稳固的盈利点。

<details><summary>Original English Source</summary>
Layer three, the infrastructure, all of these AWS, Azure, Google Cloud, all of them are hyperscalers. They're cloud companies on paper, but economically they're closer to a mix of utility, a landlord, and a wholesaler. They sign 10 to 15-year leases with data center operators and 20-year purchase agreements with power plants. When OpenAI commits to spend $250 billion on Azure, these become financial instruments. The risk profile on each side is almost inverted because OpenAI faces usage volatility, pricing, model update risk, whereas Microsoft Azure faces none of that. A hyperscaler profits from every AI query at multiple levels simultaneously: raw compute, key value cache storage, API gateway bandwidth, service fees.
</details>

### 数据中心租赁：以“电力”为单位的商业模式

在数据中心行业，租金不是按平方英尺计算的，而是按**千瓦**（Kilowatt）或**兆瓦**（Megawatt）计价。本质上，他们卖的是**保证用电权**。一个典型的超大规模数据中心通常签约 200 兆瓦的容量，按每兆瓦 1000 万至 1400 万美元计算，单体租金往往超过 10 亿美元。

这个行业的**护城河**（Moat）既不是土地也不是建筑，而是**电网容量**（Grid Capacity）。获取大规模、稳定的电力供应许可需要数年时间。即使有充足的资本，也无法快速逾越这个障碍。有趣的是，许多云巨头为了优化资产负债表，会通过**特殊目的实体**（Special Purpose Vehicles: 为特定资产或融资目的而成立的独立法律实体）来处理沉重的债务和租赁义务，使得这些巨额负债往往隐藏在财报的脚注中。

<details><summary>Original English Source</summary>
The second player in the infrastructure game is the data center landlord. Rents are quoted per kilowatt or a megawatt. They're selling the right to draw a guaranteed amount of electricity. The building, the cooling, and fiber are all parts of the infrastructure wrapped around the power contract. The barrier to entry is not the land or the building, but the power contract. Obtaining a grid connection that can deliver firm power at scale takes years. Data center operators who already hold interconnection rights have a solid structural moat. Oftentimes when a hyperscaler builds their own data center, they do it off their balance sheets through special purpose vehicles. Economically, the commitments are there, but accounting pushes a lot of that liability into the future.
</details>