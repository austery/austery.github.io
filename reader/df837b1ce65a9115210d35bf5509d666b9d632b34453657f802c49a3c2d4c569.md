---
layout: post.njk
source: https://yage.ai/share/anthropic-compute-strategy-xai-colossus-20260507.html
speaker: yage.ai
title: |-
  Anthropic 锁死了所有算力渠道，xAI
  把城堡租给了对手
date: '2026-05-07'
summary: 文章分析了 Anthropic、xAI 和 OpenAI 的 AI 算力策略。Anthropic 推动算力商品化；xAI 建设超需求，成为算力提供商；OpenAI 押注算力稀缺。核心观点是：AI 算力正从护城河转为大宗商品，公司策略反映了对这一趋势的不同判断。
area: tech-engineering
category: tech-trends
tags:
  - compute-resources
  - ai-infrastructure
  - commoditization
  - ai-strategy
  - gpu
people:
  - Elon Musk
  - Dario Amodei
  - Krishna Rao
  - Michael Nicolls
companies_orgs:
  - Anthropic
  - xAI
  - SpaceXAI
  - Amazon
  - Google
  - Broadcom
  - CoreWeave
  - OpenAI
  - Microsoft
  - Cursor
products_models:
  - Claude
  - Grok
  - NVIDIA GPU
  - Trainium
  - TPU
  - Composer 2.5
media_books: []
draft: true
status: evergreen
---

二月份 Elon Musk 还在 X 上把 Anthropic
称为”最虚伪的公司”、“仇恨西方文明”。五月份他说”上周和 Anthropic
团队待了很多时间，印象深刻，没有人触发我的恶魔探测器”。这个 180
度转弯的直接原因是一笔交易：Anthropic 签下了 SpaceXAI 旗下 Colossus 1
数据中心的全部算力——300 兆瓦、22 万张 NVIDIA GPU（CNBC）。整座超算中心，租给了竞争对手。

把这条新闻放进过去六个月的序列里看，会浮现两个互相镜像的故事。表面看，一个关于锁死供给，一个关于产能过剩。但它们的底层逻辑指向同一个方向——算力正在从护城河变成大宗商品。两家公司的行为模式暴露了行业一个深层的分歧：对算力本质的判断不同。

## 四笔交易，一个策略

过去半年，Anthropic
签下了四笔算力合同。把它们铺开来看，覆盖了几乎每一种可获得的芯片架构和云渠道。

第一笔是 Amazon 的 Project Rainier。2025 年 10
月，这座位于印第安纳州的超算中心上线时已经部署了近 50 万张 Trainium2
芯片，全部为 Anthropic 训练 Claude 专用；Amazon 说年底前会翻到 100
万张（CNBC）。这笔交易的规模在今年
4 月被大幅加码：Amazon 追加投资到 250 亿美元，Anthropic 承诺未来十年在
AWS 上支出超过 1000 亿美元，总容量达到 5 吉瓦（CNBC）。Trainium
是 Amazon
自研芯片，不对外出售，只在自己的数据中心里跑——也就是说，Anthropic 在 AWS
这个渠道里锁死了一套其他公司根本买不到的算力。

第二笔是 Google 的 TPU，通过 Broadcom 落地。2025 年 10
月的初始协议给了超过 1 吉瓦的 TPU 算力。2026 年 4 月 Broadcom 的 SEC
文件披露，这个数字已经扩大到约 3.5 吉瓦的下一代 TPU，2027 年开始交付（Broadcom
8-K）。加上初始部分，来自 Google 的总容量接近 5 吉瓦——和 Amazon
那笔规模相当。Anthropic CFO Krishna Rao
的说法是”我们对算力做出了有史以来最大规模的承诺”（TechCrunch）。The
Information 报道 Anthropic 在 Google Cloud 上的总承诺达到 2000
亿美元。

第三笔是今天的 SpaceXAI Colossus 1。和 Amazon 与 Google
不同，这座数据中心用的是 NVIDIA 的 GPU——H100、H200 和 GB200 混搭，一共约
22 万张（WIRED）。容量
300 兆瓦，Anthropic 全部吃下。加上 Anthropic 还”表达了兴趣”与 SpaceXAI
合作开发太空数据中心。

第四笔是 CoreWeave。2026 年 4 月，CoreWeave 宣布与 Anthropic
签订多年期协议，算力今年晚些时候上线（CoreWeave）。CoreWeave
是独立的 GPU 云，以 NVIDIA GPU 为主。

四笔交易覆盖了 AWS 自研芯片（Trainium）、Google
自研芯片（TPU）、NVIDIA 商用 GPU（Colossus 1 +
CoreWeave）三种芯片架构，同时覆盖了三大云厂和两家独立 GPU 云。没有哪家
AI 公司需要为了”分散风险”去锁 5 吉瓦的
TPU——这三家芯片架构各自需要独立的适配工程。Anthropic
的做法本质是供给侧的系统性控制。

## 对应物：xAI 的两条反向信号

xAI 那一边的画风完全不同。两条独立信息拼在一起，指向同一个方向。

第一条是今天这笔交易本身。Colossus 1 是 xAI 花了 122
天建成的超算中心，号称全球最大的 AI
超算之一。它全程使用权被让给了竞争对手。xAI
为此拿到的是什么呢？Anthropic
表达了合作开发太空数据中心的兴趣——这件事还属于未来阶段，技术可行性上还有很多问题（太空散热、碎片防护等物理问题仍未解决）。

第二条来自 Business Insider 的报道：xAI 把算力租给了 Cursor，让
Cursor 在自己的 GPU 上训练 Composer 2.5，使用了数万张卡（Business
Insider）。这件事把 xAI
变成了一个事实上的云提供商。同一篇报道还提到，xAI 总统 Michael Nicolls
在内部备忘录中说公司的 GPU 利用率”低得尴尬”——只有 11%，目标是短期内拉到
50%。行业平均水平是 35% 到 45%。

两件事的共同指向：xAI 的算力建设速度跑在了模型需求前面。Colossus 1
建得太大、太快，Grok
的用户量和利用率都跟不上，于是过剩产能只能外销。先卖给
Cursor，再整座卖给 Anthropic。

## 稀缺叙事已经不够用了

过去两年的主流叙事是：GPU
供不应求，谁能抢到更多算力谁就领先。这套叙事在今天仍然部分成立——Anthropic
确实在抢。但抢的方式和动机需要重新理解。

Anthropic 的 ARR 已经从 2025 年底的 90 亿美元增长到超过 300
亿美元（CNBC）。年化增长超过
3 倍。CEO Dario Amodei 说一季度增长 80 倍（CNBC）。Claude
Code 上线两个月就做到 5
亿美元年化收入。用户抱怨高峰期速率限制和停服——这个问题的根因是需求增长太快，Anthropic
的基础设施建设追不上用户增速。

但 xAI 这边的情况说明另一件事：并不是所有建好的算力都能被填满。xAI
的扩张速度和 Elon 的工程风格一脉相承——先建再找需求。122 天把 Colossus 1
从破土到上线，紧跟着把目标放到 100 万张 GPU，但 Grok
的用户规模远没有跟上这个基建节奏。结果是 Colossus 1 这座为 xAI
自己建的算力堡垒，今天运行着竞争对手的模型。

如果把 OpenAI 放进这个框架对比：OpenAI 签了 AMD 6 吉瓦的 GPU（CNBC），做了
Oracle 的 Stargate
合作，但它在自研芯片（Trainium、TPU）这个维度上没有布局。xAI
的角色则像一个反向指标——它的过剩是行业产能建设节奏与需求开始错位的第一批证据。三家公司做了完全不同的算力布局，但对”算力会变成什么”这个问题，它们的选择揭示了比数量差异更本质的分歧。

## 算力正在从护城河变成大宗商品

三个公司面对的是同一个算力市场，但它们的行为模式暴露了一个深层分歧：对算力本质的判断不同。

Anthropic
的策略是最反直觉的一条路。表面看，她是在囤积——签了三种芯片架构、五家供应商、几百亿美元的长期合同。但如果只是”买更多算力”，签一家就够了。签三家，而且包括了
Trainium 和 TPU 这两种 NVIDIA GPU
之外的架构，是在做另一件事：用适配能力抹平硬件差异，主动把算力推向商品化。

当 Anthropic 证明自己的模型可以在 Trainium、TPU 和 GPU
三种架构上高效运行（甚至在不同架构之间分配训练和推理负载），NVIDIA
对算力定价的单极控制就被打破了。只要 Amazon 和 Google
的自研芯片产能跟得上，Anthropic
就有了在不同供应商之间压价的筹码。她在做的事不是单纯囤货，而是构建一个多头竞价的格局，扮演一个主动改造市场结构的参与者。

xAI 那边做的事情恰好构成这个叙述的另一半。11% 的 GPU 利用率和
Colossus 1 整座出租，不能简单读成”Grok
不行了”。在马斯克的第一性原理框架下，闲置算力不是失败，而是没被定价的资产。把
Colossus 1 租给 Cursor 和
Anthropic，本质是在做算力套利：用建设速度和规模优势建成集群，然后卖给那些不想自己建或来不及建的人。这已经把
xAI 从单一的 AGI
角逐者，变成了双重身份：既是一个模型公司，也是一个云厂商。

但这层身份有内在矛盾。当你的竞争对手在你最好的基础设施上训练比你自己更好的模型，而且你还在收租金，你的竞争位置就进入了一种自我削弱的循环。Musk
说 xAI 会”作为一个独立公司解散”归入 SpaceXAI，这个合并的实际效果就是把
Grok
从独立赛道上撤下来。算力套利的生意也许能回收投资，但靠出租算力建不起模型竞争力。

OpenAI
在这幅图景里的位置最为特殊，也最容易被低估。她的双轨采购（NVIDIA +
AMD）看起来是中间路线，没有 Anthropic 那么激进，也没有 xAI
那么反转。但风险恰恰隐藏在这个”正常”里面。如果 Anthropic
成功把算力推向商品化，NVIDIA
的定价权被削弱，算力租赁价格出现系统性下降——那么 OpenAI
与微软深度绑定的长期、高价算力合同，就会从一份保障变成一份锁定了高成本的历史包袱。当别人的边际算力成本在下行，而你的固定成本锁在上行周期的高点，你在
token margin 上的劣势会被持续放大。

“token margin
只会越来越薄”——把这个判断作为棱镜，三家公司策略差异就有了统一的解释框架。

Anthropic
在做的，是用固定支出买一个期权。这个期权的内容是：当算力商品化发生的时候，她已经在所有架构上都有了部署能力，可以最低成本地选择在那时最便宜的芯片。5
吉瓦的 TPU 承诺不是今天要用的，是为了让 Google 愿意为她在 2027
年留出产能。成本在今天，收益在 2027 年之后的每一个推理 token 上。

xAI 在做的，是用建设速度套利——别人还在规划的时候她已经建成了，但 Grok
的质量和用户规模没有跟上这个速度。超额产能没有浪费，而是直接在市场上变现。问题是，这个模式的可持续性取决于
Grok 能不能在某个节点追上来。如果 Grok 一直落后，xAI
就会做一家永远为竞争对手提供基础设施的公司。

OpenAI 的风险在于，她目前的算力策略隐含了一个前提：GPU
会持续稀缺。如果这个前提不成立——Anthropic 的 commoditization
策略成功，算力真的从稀缺资源变成价低者得的水电——那 OpenAI
今天的最大优势（巨量优先供应的 GPU）就会变成成本结构上的最大劣势。

所以最后的判断不是”谁的模式会赢”，而是”算力会不会从护城河变成大宗商品”。如果会，那
Anthropic
的策略是对这个趋势的赌注正向的——她自己在推动这个趋势，同时做好了准备。xAI
的策略是对这个趋势的中性反应——她已经把自己放在了卖方。OpenAI
的策略隐含了对这个趋势的否定——她假定算力会持续稀缺，而这是三个假设里风险最大的一个。