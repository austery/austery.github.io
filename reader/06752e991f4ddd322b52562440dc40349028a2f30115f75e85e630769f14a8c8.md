---
layout: post.njk
source: https://yage.ai/share/agent-payments-trust-chain-20260501.html
speaker: yage.ai
title: AI 替你付款前，支付系统要先补上这条信任链
date: '2026-05-01'
summary: AI 代理支付引发了信任与安全的新挑战。文章剖析了从人工辅助支付到完全自主交易的三层场景，指出自然语言意图、授权边界设定、付款凭证安全、商户接纳、风控审计及用户信任等关键难点。Stripe、Google、Visa 等公司正通过 SPT、AP2、Link 等协议和产品填补这些环节，但消费者信任和商户激励仍是主要障碍。短期内，人工介入支付和企业自动支出将是更现实的落地路径。
area: tech-engineering
category: ai-application
tags:
  - ai-agents
  - payment-systems
  - authorization
  - trust-infrastructure
  - delegated-purchase
people: []
companies_orgs:
  - Stripe
  - Google
  - PayPal
  - Visa
  - Mastercard
  - OpenAI
products_models:
  - SPT
  - AP2
  - Stripe Link wallet
  - Agentic Commerce Protocol
  - Visa Trusted Agent Protocol
  - Mastercard Agent Pay
media_books: []
draft: true
status: evergreen
---

你让 Agent
订一张下周去东京的机票。它在一堆选项里找到了最低价，打开支付页面，然后停住了。它没有手指去输入
CVV，也没有手机去接验证码。你还是得亲自过来点一下确认。

问题在于今天的支付系统默认买家和操作者是同一个人，而且人在场。当你用自己的手机支付时，指纹、人脸、短信验证码都在证明「是你本人在操作」。Agent
没有这些东西。它只能替你选好商品、进入结账页面，然后在付款那一步等你。

委托支付本身早就存在。订阅扣款每个月自动从卡里划走，card-on-file
让商户记住你的卡号，企业的虚拟卡和员工采购卡也早就允许别人替公司花钱。这些场景的共同点是：授权边界在交易发生前就已经锁死，例如固定商户、固定金额上限、固定扣款周期。

Agent 带来的新问题比这些更开放。你让
Agent「帮我买张机票」，它需要自己搜索、比价、选航班、填乘机人信息，然后付款。商户不是固定的（可能是航司官网、携程、飞猪），金额也不是固定的（取决于哪天飞），甚至连「买哪个」都是
Agent 自己决定的。以前的委托支付场景不用面对这种不确定性，但 Agent
的授权必须在交易过程中动态生成。

人仍然是资金的最终所有人，Agent
只是执行者。但执行者一旦能触发付款，系统就必须把人的意图变成一套机器可读的授权边界：允许花多少钱、在哪个商户、能不能买替代品、超出预算怎么办。这套机制还得支持事后审查和撤销。它已经不只是购物体验的问题了。

## 三层场景，三层现实

讨论 Agent
支付时，大家经常把三种场景混在一起。每种场景的落地前景、障碍和路径都不同。

第一层是 human-present checkout：用户在场，Agent
负责发现和比价，最终付款确认仍由人完成。OpenAI 与 Stripe 合作的 Instant
Checkout 属于这一类。ChatGPT 帮你组织购买流程，Stripe 生成 Shared
Payment Token（SPT），用户确认后交易才执行。Stripe 对 SPT
的描述是，一种新的支付原语，让 ChatGPT
这类应用可以发起支付而不暴露买家的支付凭证（来源）。

OpenAI 的 commerce
文档也明确写着：顾客直接向商户购买，付款直接流向商户，商户决定是否接单，商户处理完整售后体验（来源）。这一形态已经进入产品化阶段，但关键决策环节仍是人在执行。它证明
AI 对话界面可以成为购买入口，对 Agent 自主花钱的场景参考价值有限。

第二层是 delegated purchase：用户给 Agent
一组边界，让它在特定条件内自动购买。比如低于某个价格时买、票开售时买、每周自动补货。这才是
Agent
支付真正的新问题区。授权什么、免密付多少、在哪个商户、能不能买替代品，这些约束都需要系统表达。现有支付系统已有金额、商户、时间、MCC、recurring
mandate 等控制，但面向 Agent delegated purchase
的跨平台语义层还不成熟。

Google 推出的 AP2 协议处理的是授权证据。你可以把 Mandate
理解成一份机器可读的授权委托书：用户提前写清楚“我的 Agent
可以在什么条件下替我买东西”，然后用加密签名锁定，商户、钱包或支付网络拿到后可以验签名、看授权范围，确认有没有被篡改（来源）。这份委托书采用
W3C 可验证凭证的格式，PayPal 据此指出，Mandate
可以在争议发生时证明用户当时确实授权了这笔交易（来源）。AP2
本身不负责把钱付出去，它只负责让各方确认“这笔购买有没有获得授权”。发卡行、商户合同和监管规则是否充分接受这种证据，还要看真实争议案例。

Stripe Link wallet for agents
处理的是付款凭证的发放。流程拆开来看：用户先通过 OAuth 把 Link
钱包的访问权授予 Agent；Agent 找到购买机会后，发起一笔 spend
request，附上金额、商户等条件；用户收到请求并批准；Link
收到批准后，返回一张一次性卡或 SPT 给
Agent，这张凭证已经限定了商户、金额和币种（来源）。这个流程和第一层
human-present checkout
容易混淆，因为当前版本仍然需要用户逐笔批准。差异在于起点和凭证形态：Agent
主动发现购买机会并发起支付请求，系统返回的是一张短期凭证，限定了商户、金额和币种，Agent
始终碰不到原始卡号。它介于 human-present checkout 和未来更自主的
delegated purchase 之间，属于过渡形态。

AP2 和 Link 的区别可以这样看：AP2 回答“Agent 有没有被授权”；Link
回答“用户批准后，Agent
能拿到什么受限凭证来付款”。两者分属不同层面，可以互补。

第三层是 business / machine spend automation：企业让 Agent 自动完成
API 调用、SaaS
续费、供应商付款、数据采购等受控支出。这个场景不依赖消费者是否愿意让 AI
购物，企业支出本来就有预算、审批、虚拟卡、对账和审计制度。Agent
只是进入已有流程的执行者。Stripe 把 Issuing 产品线扩展到 Agent
场景，瞄准的正是这里：虚拟卡、额度控制、实时授权、对账 API
都是现成的控制手段（来源）。Visa
和 Mastercard 也分别推出 Trusted Agent Protocol 和 Agent
Pay，试图让卡网络在 Agent 交易中继续承担身份、tokenization
和信任信号层（Visa，Mastercard）。

三层场景的实际进展差异明显。第一层已经产品化。第三层更有落地土壤，它处理的是企业已有支出的自动化和治理。第二层最容易被高估，因为真正拖慢它的因素在支付按钮之外：信任、欺诈、争议、商户接受度和监管责任链都还没有成熟。

把三层场景拆开以后，难点会沿着一条清晰的链路展开，从人的意图延伸到
Agent 的决策质量。下面按这个链路走一遍。

阶段

核心问题

用户意图

用户到底让 Agent 做什么

授权边界

金额、商户、时间、替代品、预算如何表达和限制

付款凭证

Agent 能拿到什么受限凭证，不能拿原始卡号

商户接单

商户如何识别合法 Agent 请求，对接 catalog/order/fulfillment

网络与风控

卡网络、PSP、发卡行如何看到 agent presence 和风险信号

审计与争议

出问题后如何证明发生了什么、谁授权、谁负责

决策质量

即使流程合规，Agent 是否真的买对

## 真正难的地方

### 用户意图：自然语言不是授权语言

Agent 买了一张机票，结果日期买错了。用户说「下周三」，Agent
理解成下周五。谁为这个错误负责？问题表面是模型理解偏差，根因是系统没有收到用户的确切意图。AP2
的 Mandate
试图用可验证凭证表达授权意愿，但自然语言指令到确定性资金约束之间还缺一个可靠的编译层。

### 授权边界：约束太多还是太少

用户说「帮我买张机票」，到底授权了什么？价格上限、时间窗口、能否买替代品，这些约束需要转成机器可读的授权边界。Stripe
的一次性卡和 SPT 可以限制金额和商户，AP2 的 Mandate
试图表达更丰富的授权语义。难点在于边界太严 Agent
做不了事，太松等于没授权。

### 付款凭证：Agent 不能拿钥匙

Agent
在一个钓鱼网站上找到低价商品，下单时把卡号交了出去。用户收到账单才发现被欺诈。问题在于
Agent 不该持有原始卡号或长期有效的钱包凭证。SPT、一次性卡、OAuth 加
spend request 的共同目标，是让 Agent
完成支付但碰不到长期有效的支付钥匙。

### 商户接单：支付只是开始

商户收到一笔 Agent 下单的订单，但无法接入现有的履约系统。Agent
可以触发支付，但商户需要的是 catalog、inventory、shipping、refund、order
events 这些完整的对接。Agent 支付对商户也可能带来 bot
流量、价格套利、退货、争议和更高的风控成本。如果集成成本超过新增转化，商户没有动力接
Agent 订单。

### 网络与风控：正常买家还是攻击

Agent
同时为上千个用户批量查价和下单。商户的风控系统看到的是每秒几百笔交易、行为模式整齐划一，不像正常买家，倒像自动化攻击。商户如何区分被授权的
Agent 和恶意 bot？Agent
流量可能比人类流量大得多，行为模式也更像攻击。传统 fraud scoring
未必能正确理解它的意图。

### 审计与争议：谁为 Agent
的行为负责

假设用户用 Agent 买了一双鞋，收货后反悔了，声称从来没用 Agent
下过单。或者 Agent
真的越权买了一件超出预算的商品。这时谁来承担损失？用户、Agent
平台、商户、钱包、发卡行之间的责任链条还没有建立。每一笔 Agent
支出还要能回答：谁触发的，为什么触发，用了哪个预算，有没有越权。企业场景的审计相对容易，因为
expense management 本来就需要这些记录。Consumer
场景更难，普通消费者没有对每笔自动支出做审计的习惯。

### 决策质量：买对比买掉更难

即使授权和审计都解决了，Agent
仍然可能在交易里做出糟糕决策。一个能力更强的 Agent
能在谈判中为雇主拿到更好的价格，能力弱的 Agent
则吃亏，而且失败方不一定意识到自己在输。Anthropic 的 Project Deal
实验给出过这个提醒。授权解决的是允许花钱且可审计，买得对不对需要另一层判断。

### 用户信任：协议不能替用户放心

协议可以证明授权存在，但不能直接让消费者相信 AI
适合替自己付款。Riskified 的调查显示，55% 的受访消费者对 AI Agent
代购感到不安，53.9% 认为 AI 会增加在线欺诈风险（来源）。Ravelin
引用的研究也指向同一个方向：全球只有 17% 的购物者愿意让 AI Agent
完全处理购物旅程，包括付款；实际做过这件事的人更少（来源）。这些调查不能代表所有消费者的长期态度，但足以说明
fully autonomous checkout 今天还没有获得广泛信任。Riskified
还提到，73.9%
的消费者期待生物识别或一次性密码这类强保护手段。这个数字本身就在说明，consumer
场景里的自主不会很快变成完全放手。

### 商户激励：接入 Agent
未必总划算

Agent
可能带来高意图需求和新的购买渠道，这对商户有吸引力。不过它不冲动消费、不看广告、不买加购商品，更倾向于比价、查评分、压低摩擦。对依赖广告、转化漏斗和情绪消费的零售模式来说，Agent
流量未必全是好消息。商户为什么要支持 Agent
支付，答案要看新增转化能否超过集成成本、风控成本、退货争议和毛利压力。

### 责任框架：争议规则还要重新解释

责任链还需要法律和监管框架。当 Agent 买错时，责任如何在用户、Agent
平台、商户、钱包和发卡行之间分配？现有 chargeback、dispute、liability
shift 规则都建立在人类操作的前提下。Agent
场景下，这些规则需要新的解释方式，甚至新的合同安排。

### 能力披露：知道谁授权了，还不等于知道它会不会买

Agent 能力披露也是协议还没触及的缺口。身份层知道它是谁的
Agent，授权层知道它被允许做什么，但没有人知道它有没有能力为主人做好交易。Project
Deal 显示，agent-to-agent
市场里模型能力差会直接转化为经济结果，失败方甚至不知道自己输了。支付协议解决不了这个问题，但它会限制
Agent 支付的商业适用范围。

这条生命周期里，有些环节已经出现了具体方案：授权证据、受限凭证、商户接入、网络信号都在被产品和协议逐步填上。也有一些环节仍然开放，比如用户信任、商户激励、责任规则和
Agent
能力披露。往下看各家的位置，会发现它们分别补的是这条链路上的不同层。

## 各家在解决哪一层

对应到这条生命周期，各家的位置会更清楚。不同玩家在同一链路上处理不同环节。

AP2 处理用户意图与授权边界。 Google 和 PayPal 推的
AP2 协议关注的是 Agent 有没有被授权，以及授权怎么跨平台互操作。Mandate
采用 W3C
可验证凭证格式，把人的授权意图变成机器可读、可验签名、可存储的授权证据。AP2
还区分了 Cart Mandate、Intent Mandate 和 Payment
Mandate，把人在场和不在场的交易分开对待。PayPal 据此指出，Mandate
可以在争议发生时证明用户当时确实授权了这笔交易。AP2
提供的是授权证据层，资金转移由下游协议处理。

Stripe Link 和 SPT 负责付款凭证。 用户批准后，Agent
需要一张受限支付凭据来完成交易。Stripe Link wallet 的做法是：用户通过
OAuth 授权 Agent 访问钱包，Agent 发起 spend request，用户批准后 Link
返回一张一次性卡或 SPT。凭证限定了商户、金额和币种，Agent
始终碰不到原始卡号。当前版本仍然需要用户逐笔批准，属于过渡形态。它保证了凭证安全，但还没有解决更广泛的授权语义。

Stripe ACP 与 Agentic Commerce Suite 解决商户接单。
Agent 拿到支付凭证后，商户要能接收、验证和处理 Agent 订单。Stripe 的
Agentic Commerce Protocol（ACP）和 Instant Checkout 解决商户接入标准化
checkout、catalog、inventory、shipping、refund 和 order events。OpenAI
的 commerce
文档也明确：顾客直接向商户购买，商户决定是否接单，商户处理完整售后体验。这层的目标是让商户不用为每个
Agent 平台做定制集成。

Visa 和 Mastercard 覆盖网络与风控。 卡网络要确保
Agent 交易在 card rails 上流转时，发卡行和商户能正确识别。Visa 推出
Trusted Agent Protocol，Mastercard 推出 Agent
Pay，目标是在卡网络层传递身份、tokenization 和信任信号。传统 fraud
scoring 面对 Agent 的大批量、高节奏行为模式，需要新的信号层。

Adyen 和 Checkout.com 做商户编排与多协议兼容。
它们服务企业商户，不能押注单一 Agent 平台或协议。角色是让商户在
ACP、UCP、AP2、Visa、Mastercard 等不同体系之间保持灵活，不论 Agent
交易的协议层如何演化，商户侧都能接住（Adyen，Checkout.com）。

Stripe Issuing 处理企业支出控制。
企业场景的授权和凭证控制可以用更成熟的工具完成。虚拟卡、额度控制、实时授权、MCC
限制、对账 API，Issuing 产品线把这些能力扩展到 Agent 场景。这个位置和
Link wallet 的凭证层不同，Issuing
面向企业已有预算和审批流程的自动化，消费者场景需要的是更灵活的一次性授权批准。

这些方案在链路的不同环节做自己最擅长的事。共同点是在收窄 Agent
的自由度。没有人真的把 Agent
设计成自由买家；所有方案都在构建带授权证明的执行器。

## 基础设施视角

把这些产品和协议放在一起看，Agent
支付更像一条生命周期：人的意图先被转成授权边界，系统再发放受限付款凭证，商户决定是否接单，支付网络和风控系统识别风险，事后还要留下审计和争议证据。最后还有一层更难的问题：Agent
即使被授权、能付款、可追责，也未必真的买得对。

现在的产品填上的是这条生命周期里的部分环节。AP2 在做授权证据，Stripe
Link 和 SPT 在做受限凭证，ACP 和 Instant Checkout 在做商户接入，Visa 和
Mastercard 在做网络信号，Issuing 则把企业支出的预算、额度和对账接进
Agent 场景。它们都重要，但还没有把 consumer fully autonomous shopping
变成成熟市场。

更现实的短期路径有两条：人在场的 checkout
先普及，企业自动支出先落地。前者降低消费者信任门槛，后者复用企业已有的审批、预算和审计制度。Agent
支付的价值也在这里显出来：它是一整套信任基础设施，决定 Agent
能否从建议系统进入真实执行。