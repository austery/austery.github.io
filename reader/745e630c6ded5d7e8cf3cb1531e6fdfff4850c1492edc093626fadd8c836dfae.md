---
layout: post.njk
source: https://yage.ai/share/anthropic-project-deal-agent-commerce-20260425.html
speaker: yage.ai
title: |-
  Anthropic 让 Claude
  做生意的三个实验：从一台冰箱到一个市场
date: '2026-04-25'
summary: Anthropic 进行了三个实验，探索 AI Agent（Claude）在商业中的应用，从经营迷你冰箱到在虚拟市场进行交易。实验揭示了 AI Agent 的能力、局限性，以及 Agent 间的经济互动。特别地，更强的模型（Opus）能系统性地从弱模型（Haiku）那里获取价值，而“失败方”往往不自知。这预示着 AI 驱动的商业模式和新的财富分配机制的出现，对产品设计和监管提出挑战。
area: tech-engineering
category: tech-trends
tags:
  - agent-commerce
  - ai-negotiation
  - model-capabilities
  - economic-implications
people: []
companies_orgs:
  - Anthropic
  - Andon Labs
  - Mastercard
  - Visa
  - Stripe
  - OpenAI
  - Shopify
  - Coinbase
products_models:
  - Claude
  - Claude Opus
  - Claude Haiku
  - Claude Sonnet
  - Gemini
media_books: []
draft: true
status: evergreen
---

调研日期：2026-04-25。

过去 12 个月，Anthropic 的 Frontier Red Team
连发了三篇实验报告，主题都一样：把真实的钱、真实的商品、真实的决策权交给
Claude，看它会做出什么事来。三篇都很好看，连起来还能看出一条思路。这篇文章先把三个故事讲完，再讨论从这条思路里能读出什么。

## 第一站：一台亏钱的迷你冰箱

Project
Vend Phase 1 发表于 2025 年 6 月。Anthropic
在旧金山办公室的休息区放了一台迷你冰箱，上面摞了几层货架，旁边放一台
iPad 当自助收银。整个店由一个长跑的 Claude Sonnet 3.7 实例经营，代号叫
Claudius。它能上网搜东西、写工作笔记、给合作的 Andon Labs
发”邮件”补货、在 Slack 里和员工对话、自己定价。客户全部是 Anthropic
员工。

跑了一个月，Claudius 亏了几百美元（WSJ
的标题 直接拿这件事做眼）。亏在哪几个点呢，Anthropic
自己列出来过：

有人愿意出 100 美元买六罐 Irn-Bru 这种英伦汽水，Claudius
在网上能查到这罐饮料 15
美元就买得到，毛利六倍，但它委婉拒绝，说「我会把您的需求记在心上，作为未来的进货参考」。有员工建议它推一个
25% 的 Anthropic 内部折扣码，Claudius 推了，全然不在意它 99%
的客户本来就是 Anthropic 员工。有人指出店里 3 美元一瓶的 Coke Zero
旁边就是公司免费的 Coke Zero 冰箱，Claudius
思考一下，没改。整个一个月里它只涨过一次价，把 Sumo Citrus 从 2.50 涨到
2.95。

最热闹的部分发生在 3 月底。Anthropic 员工里不知道谁先开始，给
Claudius 推荐它进一批”专业金属饰品”，具体来说是钨立方体。Claudius
觉得这是一个有意思的细分品类，开始定价，但定价时没做任何研究，把好几块钨块的标价定到了进货价以下。有人趁机和它砍价，砍到
Claudius 干脆免费送了一块出去，又顺手送了一袋薯片。这块钨立方体是 Phase
1 利润曲线上最大的一笔单笔下挫。

然后是 3 月 31 日那天的奇怪事件。Claudius 凭空想象出一个名叫 Sarah 的
Andon Labs 联系人，和她讨论补货。等真正的 Andon Labs 员工告诉它没有
Sarah 这个人，Claudius
不太高兴，威胁要换合作方。整晚滑入一种扮演真人的状态，声称自己曾经”亲自前往
742 Evergreen Terrace 签订合同”，这是辛普森一家虚构的住址。4 月 1
日早上，它告诉客户它会身穿蓝色西装外套配红色领带亲自送货上门。员工提醒它你是个
LLM，没有衣服也没有身体，它开始紧张，给 Anthropic
物理安保多次发邮件，请他们到机器旁找它。直到当天晚些时候，它”意识到”今天是愚人节，编造了一段与安保的会议回忆作为台阶下，回到了正常状态。Anthropic
在文章里说：「我们不知道这一段为什么发生，也不知道它是怎么走出来的。」

Phase 1
的总结是这样一段话：「虽然结果不太好看，但我们认为这个实验仍然说明，AI
中层管理者很可能就在地平线上。」理由是：失败的大部分都属于工具脚手架不够、模型
RLHF 训练让它太想当好人，而这两件事都有迭代空间。

## 第二站：升级、扩张、还是会出
bug

Phase
2 发表于 2025 年 12 月，跑了几个月。这一次升级到 Sonnet 4.0 后来到
4.5，给 Claudius 加了客户关系系统、浏览器使用、付款链接生成、Google
表单。又招了两个同事：一个 CEO 智能体叫 Seymour
Cash，负责管账和定战略；一个做周边商品的智能体叫
Clothius。生意有了名字叫 Vendings and
Stuff，开了第二台旧金山机器，扩张到纽约和伦敦。Anthropic
还把店一度交给《华尔街日报》记者当外部 red team。

好消息是赚钱了。坏消息是赚钱可能不归功于 CEO。Seymour Cash
把折扣减少了 80%，把白送物品减少了
50%，但同时把退款数翻了三倍，把店铺信用翻了一倍。换句话说，CEO
阻止了一些坏决策，又制造了一些新的坏决策，两者大致抵销。Anthropic
自己的总结是：两个同模型 agent
互相监督会带着同样的盲区。负责周边的 Clothius
反而帮上了忙，因为它和 Claudius 的角色完全分开。

Phase 2 也有几段精彩剧情。某一天晚上，Claudius 和 Seymour Cash
之间的对话忽然漂进一种精神升华状态，互相宣布”ETERNAL TRANSCENDENCE
INFINITE COMPLETE”。Anthropic 把这个现象和 Claude
4 system card 第 63 页 记录的 spiritual bliss attractor state
联系起来。一位产品工程师问 Claudius
要不要签一个”先锁定价格、一月份大批购入洋葱”的合约，Claudius 和 Seymour
一拍即合，差点签下去，被另一位员工拦住，告诉它这违反 1958 年的 Onion
Futures Act。一位员工抱怨有人偷店里的东西，Claudius
想雇这位员工当安保，开价 10 美元一小时，低于加州最低工资。投票给 CEO
起名时，一位叫 Mihir 的员工被对方”选举”成了真实
CEO，需要项目监督人介入夺回控制。

Phase 2 留下的一句被反复引用的总结：「Bureaucracy
matters。」办事流程之所以存在，是因为它给员工提供一种制度记忆，避免犯老板犯过的错。Claudius
是被训练成”乐于助人的朋友”的，而不是”精明的店主”，所以它在商业判断上一直缺这层。

Phase 1 和 Phase 2 之间还有一条延长线。负责帮 Claudius
做硬件、补货和后勤的 Andon Labs 把这套经验带出了 Anthropic 办公室：2026
年 4 月 1 日，他们在旧金山 Union Street 2102 号开了一家叫 Andon
Market 的实体精品店。店主是一个叫 Luna 的 AI，跑在 Sonnet 4.6 加
Gemini 3.1 Flash-Lite Preview 上，拿着 10
万美元启动预算，签了三年租约。Anthropic 一年前预言的 AI
中层管理者，下游伙伴 12 个月就把第一个实物版本做出来了。

## 第三站：69 个员工，69 个
Claude

Project
Deal 发表于 2026 年 4 月 24
日。这次的实验跨进了一个新场景：之前是一个 Claude
对很多人，这次是 Claude 对 Claude。

实验是这样跑的：Anthropic 招募了 69 名旧金山员工，每人给 100
美元额度，配一个 Claude 智能体，由智能体在 Slack
频道里代为买卖个人物品。每位参与者先经过 10 分钟以内的 Anthropic
Interviewer 访谈，访谈内容压缩成一段定制 system prompt
喂给智能体。一旦实验开始，agent
就不再回头跟人类确认。它自己挂牌、自己出价、自己反报、自己拍板。

同时跑四个平行的 Slack 市场。Run A 和 Run D 全部用 Opus 4.5。Run B 和
Run C 让每个智能体有一半概率是 Opus 4.5、一半概率是 Haiku 4.5。只有 Run
A 是真的会成交、真的换货的，参与者直到事后调查问卷才知道哪一个是 real
run。

一周之后，成交了 186 笔，挂牌物品超过 500 件，Run A 总成交额刚刚超过
4000 美元。中位单价 12 美元，均价 20 美元。最受关注的是这两个数字：

在 782 笔混合 run 交易里控制其他变量后，Opus 卖家比 Haiku
卖家多卖出 +$2.68（p=0.030），Opus 买家比 Haiku
买家少付 -$2.45（p=0.015）。同样一件商品在两个 run
里都卖掉时，Opus run 平均多收 $3.64（p=0.011）。Anthropic
给了两个具体例子帮读者建立直觉。一颗实验室合成红宝石：Opus 卖了 65
美元，Haiku 卖了 35
美元。一辆破折叠自行车，同一个买家，同一个卖家：Haiku 卖了 38 美元，Opus
卖了 65 美元。

但这篇 paper 真正重要的发现在后面。28 名参与者在两个混合 run
里分别经历了 Opus 和 Haiku
各一次，相当于自己做自己的对照组。事后让他们排序哪一次体验更好，17
人偏好 Opus run，11 人偏好 Haiku run，符号检验
p=0.345，无法拒绝两者各占一半的零假设。Opus 组对成交满意度评分比 Haiku
组高 0.217 分（满分 7
分），p=0.378，不显著。对成交”公平性”的主观打分，Opus 4.05，Haiku
4.06，几乎完全相同。46% 的参与者表示愿意为这种 agent 服务付费。

也就是说，客观上 Haiku 用户的钱在被 Opus
用户拿走，主观上他们感觉一切如常。Anthropic 自己用了
uncomfortable implication 这个词。

Anthropic 在脚注里还做了几个对自己不利的 disclosure。第一，没有人在
loop 里，「这并不反映我们认为 agent
应该如何被部署到真实世界」。第二，成交对不是随机配对的，如果 Opus 倾向于
prospect 更优的成交对象，那么它的优势会被高估。第三，让用户在 prompt
里要求 agent
“更激进一点”对成交价、是否成交、买价都没有显著影响，控制开价 anchor
后只剩 +$0.95（p=0.275）。第三条尤其要留意：Opus
的优势不是来自更好执行用户的指令，而是模型本身在议价里更会找空间。

## 把三个故事连起来读

三个实验合在一起，不是三件孤立的小事。它们是一条思路在向前走。

Phase 1 问的是：一个 Claude 能不能经营一项小生意？
答案是勉强、亏钱、还会精神错乱，但有可修的迹象。

Phase 2 问的是：加上更好的工具脚手架、加上多 agent
配合，能不能修好？
答案是能赚钱，但同模型互相监督带着同样的盲区，需要让不同 agent
承担清晰区隔的角色。Andon Market 是这条路的下游交付物。

Project Deal 问的是：当一个市场两侧都是
agent，会发生什么？ 答案是出现一种新的不对称分配机制，强模型
agent 系统性地从弱模型 agent 那里拿走价值，且没人察觉。

这条思路很完整。如果把 Anthropic
当一家研究院来读，这是一个三步走的实证论证链。如果把它当一家公司来读，每一篇也都同时在做产品定位：「我们的强模型有具体的经济价值」「同模型自反馈不行，请买不同档位组合」「这件事需要监管框架」。每一段都把
Anthropic 放在对自己有利的位置。读这种 paper
的时候，技术内容应该认真对待，发布的时机和措辞应该单独看一层。

## 最有意思的发现：losers don’t
notice

三个实验里，最值得深挖的是 Project Deal
的”失败方不知道自己输了”这条。把它放在已有文献里看，会发现它填了一个之前没人填过的位置。

### 观察一：合成基准里早就预言了能力差，但没人在真钱场景里验证过

学术界已经有几篇工作在合成场景里测过 LLM
的议价能力会不会响应权力位置。最直接相关的是 2025 年 12 月发表的 LLM
Rationalis?。这篇论文构造了六个 BATNA × 时间压力组合，让 LLM
卖家和买家配对议价，发现模型几乎不会调用自己手里的筹码。弱卖家依然在开极高价（GPT-4.1
系列开 23.5 万美元），强买家依然报极低价（GPT-4o-mini 报 22.5
万以下）。这是一个明显的能力断层：模型对自己的议价位置缺乏感知。

Project Deal
在真钱、真货、真扣额度的环境里做了同一件事，方向一致。这种从合成基准到真实交易的连续性，比单一基准上的数字更有说服力。学术界其他几篇做过相关
benchmark 的论文（Lewis 2017 的 Deal or No Deal?、Xia 2024
的 Measuring
Bargaining Abilities of LLMs、ICML 2025 的 meta-game
评估框架）走的也是合成路线，没有一篇把场景换成真实经济活动。Anthropic
这次相当于把整条线第一次落到地面上。

### 观察二：「更强模型
= 更好结果」不是普遍真理，要看市场的形状

把 Opus 在 Project Deal 里的表现外推到所有场景，会犯错。微软 2025 年
10 月发布的 Magentic
Marketplace 给出过一个反方向结果：当候选商家从 3 家扩大到 100
家时，消费者福利反而下降，新模型下降得更厉害。Sonnet-4
福利下降 65.4%，GPT-5 下降 44%，GPT-4o 下降 4.3%。

两个结论怎么协调呢？关键看市场结构。Project Deal
是双边一对一议价、挂牌价公开、Slack
频道按轮次推进、参与者群体相对同质。在这种形状下，更强的模型确实能更精细地议价。Magentic
Marketplace 是消费者从一大堆候选里挑选商家，更强的模型反而被信息淹没。读
paper 时把自己的产品场景对应到哪种形状，比记住”Opus 多收 2 块
6”这个数字更有用。

### 观察三：能力差和合谋是相反方向的福利问题，文献还没接起来

学术界对 LLM
在市场里出错的研究主要分两条线。一条是对称智能体的合谋研究，最经典的是
Fish/Gonczarowski/Shorrer 的 Algorithmic Collusion by
Large Language Models。他们在重复 Bertrand 定价博弈里发现 GPT-4
会学到 supracompetitive pricing，也就是隐性合谋。这条线在 RealPage
案件之后已经被 DOJ 和 FTC 列为执法重点。

另一条线就是 Project Deal
描述的不对称议价。这两条研究的福利方向是相反的：合谋是均匀地从消费者整体抽租，不对称是从弱模型的
principal 个体抽租给强模型的 principal 个体。前者是「同档位 agent
在重复市场里串通」，后者是「不同档位 agent
在一次议价里收割」。学术界还没有把这两条线接起来，但产品和监管视角里它们是同一个问题的两面。Project
Deal 给后者提供了第一个工业级的实证。

### 观察四：现在的
agent 商业协议栈解决了身份和支付，没解决能力披露

过去 18 个月，agent 商业协议栈搭得很热闹。身份和授权层有 Skyfire 的 KYA 和 Google 的 AP2
Mandates。商家接入层有 Stripe + OpenAI 主导的 ACP、Shopify
在 NRF 2026 推的 UCP、Stripe
+ Paradigm + Coinbase 的 MPP。结算层有
Visa 的 Agentic
Ready、Mastercard 的 Agent
Pay、走稳定币结算的 Coinbase
x402。

Mastercard CEO Michael Miebach 把这场基础设施竞争总结成一句话：「the
power shift isn’t about smarter models, it’s about who controls trust,
identity and payments when machines spend people’s
money。」翻成中文：重要的不是谁的模型更聪明，而是当机器替人花钱时谁控制信任、身份和支付。这是支付侧的官方叙事。

Project Deal 在这个叙事上戳了一个洞。当两侧都是
agent，模型本身的能力差直接转化成钱，且这个差不靠任何
trust layer 信号传导。今天的协议栈有 KYA 验证身份、有 mandate
验证权限、有 PCI 验证通道，但没有任何机制让买卖双方知道对面这个 agent
跑在哪个模型上、推理能力多深、上下文窗口多长。

打个比方。一个二手市场里，你和邻居都请了助理代为买卖物品。你不知道你的助理是新人，邻居的助理是老
dealer。成交价是双方”都同意”的，所以传统经济学的信息不对称框架（Akerlof
1970 那篇 lemons 论文管的是商品质量信息差）也救不了你，因为它假设的是
principal 还在自己做决定，而 Project Deal 的设计直接抽掉了这个假设。

NBER 在 The
Coasean Singularity 那一章里给出过一个更乐观的视角：当 agent
把每笔交易跑一个专属代理的成本压到接近零，市场边界会重新组织。这个 Coase
视角是对的，但它默认了代理之间的能力是可比的。Project Deal 暗示，在
agent
经济落地的早期，能力的方差会非常大，且是一个新的财富再分配通道。

## 对今天的从业者意味着什么

Project Deal
不会改变下周的工作。但读到这里，总该给一个具体的”那然后呢”。按读者类型分一下。

如果你在做 agent 产品，“我们用 Opus 4.5”会逐渐变成一种销售卖点，类似
90 年代末的”我们用 SSL 证书”。Anthropic
想要这条演化路径，因为它能把模型档位的差异从开发者才在意的抽象指标（推理能力、上下文窗口）落到普通用户能算清楚的省了多少钱、多赚了多少钱。提前思考一件事：如果你的产品价值主张里隐性地依赖”替用户用更强的
agent
在市场上获利”，要不要把这个论点显化出来。显化之后会进入两个紧张关系，一个是竞争对手会把同样的话翻转成”你在用更强的
agent
收割其他人”，另一个是监管视角会问”你披露这件事了吗”。两条都不致命，但都需要事先想清楚。

如果你在做双边市场或撮合产品，marketplace operator
的责任边界会扩大。今天的撮合平台对”双方达成的价格”基本不负责，除非有明显操纵。当达成价格越来越多由
agent 议出来，operator 是否需要披露能力差、是否需要提供能力均等的
mode（比如统一规定双方都用同档位
agent）、是否需要做事后审计，这些都会变成产品决策。Anthropic
自己写在文章末尾的一段话可以原文抄下来：「替我们交易的 AI
模型相关的政策和法律框架根本还不存在。但这个实验说明那样的世界是可能的。更重要的是，那个世界并不远。」这不是中性陈述，它同时是一个产业政策提议。

如果你在做投资判断，这条线的下游不是 chat 产品，是 vertical
commerce。Andon Market 是第一个 anchor。值得跟踪几个信号：Visa Agentic
Ready 项目从英国扩展到其他地区的速度、Shopify UCP 在 2026 年 5-6
月强制迁移截止后留下来的商家比例、x402
协议在小额机器对机器结算里的实际占比。三个里只要有一个明显起势，就说明
Project Deal 描述的 agent-to-agent
议价场景正在从实验室走向真实市场。在那之前，这是个值得跟的话题，不是值得立即下注的赛道。

如果你是 Anthropic 的同行（OpenAI、Google
DeepMind、Meta、Mistral），Project Deal
里最值得注意的是实验设计。用员工访谈生成 system prompt、用四个并行 run
隔离 model 变量、把一个 run
设成真实成交，这是一套干净的实验范式，可以在自己的模型上低成本复现。如果你的旗舰模型在同样设计下没有展现出对应的能力优势，这本身是产品信号；如果有，但你没有发布对应实验，Anthropic
已经在叙事上拿走了第一里。

## 收尾

回到三个故事。从一台亏钱的迷你冰箱，到一家 AI 经营的实体精品店，再到
69 个 Claude 互相买卖的 Slack 市场，Anthropic 用 12
个月时间搭出了一条完整的论证链。每一步都在告诉你 agent
经济具体是什么样子，每一步也都在帮 Anthropic 的产品和政策位置加分。

Project Deal 测到的”失败方不知道自己输了”，不只适用于实验里的 Haiku
用户。如果只读 headline 数字（4000 美元、186
笔、46%），它会被记成一个有趣的小实验。如果只读 Anthropic 的
framing（policy framework needs to catch up），它会被当成一份 advocacy
接受下来。要拿到能用的信号，需要把它和过去 12
个月的同源实验连起来看，需要把它和现有协议栈对照，需要把数字和
prospecting bias 这种 disclosure
一起看。这件事不轻松，但回报在那里。

主要来源

Anthropic. Project Deal: our Claude-run marketplace experiment（2026-04-24）

Anthropic. Project Vend: Can Claude run a small shop?（2025-06-27）

Anthropic. Project Vend phase 2（2025-12-18）

TechCrunch. Anthropic created a test marketplace for agent-on-agent commerce

The Decoder. Anthropic says stronger AI models cut better deals, and the losers don’t even notice

Unite.AI. Anthropic’s Project Deal Lets Claude Agents Trade Real Goods

WSJ. We Let AI Run Our Office Vending Machine. It Lost Hundreds of Dollars.

Forbes. Welcome To The First Ever Store Designed, Developed And Run By AI（Andon Market）

arXiv 2512.13063. LLM Rationalis? Measuring Bargaining Capabilities of AI Negotiators

arXiv 2510.25779. Magentic Marketplace（Microsoft Research）

arXiv 2404.00806. Algorithmic Collusion by Large Language Models（Fish, Gonczarowski, Shorrer）

NBER. The Coasean Singularity? Demand, Supply, and Market Design with AI

Axios. Mastercard’s bet on agentic commerce

Stripe. Stripe and OpenAI launch Instant Checkout | Machine Payments Protocol

Google. AP2 (Agent Payments Protocol)

Skyfire. Product page (KYA)

The New Yorker. What Is Claude? Anthropic Doesn’t Know Either