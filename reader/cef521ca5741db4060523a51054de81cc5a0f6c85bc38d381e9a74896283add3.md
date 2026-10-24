---
author: AI Engineer
date: '2026-10-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-AOxpwVeIWw
speaker: AI Engineer
tags:
  - agentic-payment
  - agent-economy
  - micropayment
  - api-monetization
title: 为什么 AI Agent 仍未开始自主付费：智能体支付的漏斗瓶颈与演进路径
summary: 尽管各大科技巨头与区块链机构密集推出众多智能体支付协议，但链上实际交易量依然惨淡。Apify 创始人 Jan Curn 从双边工具市场的实践出发，剖析了限制 Agent 自主支付的核心瓶颈——API 密钥惯性、高昂的钱包配置门槛、去中心化信任缺失以及按需计费的结算挑战，并展望了未来解锁智能体经济的关键催化剂。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Apify
  - Coinbase
  - Stripe
products_models:
  - x402
media_books: []
status: evergreen
---
### 智能体支付协议井喷与链上冷清交易的现实反差

在 AI 智能体生态蓬勃发展的当下，赋予智能体自主消费预算已成为实现长链路复杂任务的关键共识。Gartner 曾预测到 2028 年，自主智能体将驱动数万亿美元规模的经济活动，并承载 80% 的企业间（B2B）商务交互。受此巨大前景驱动，传统金融机构与加密行业纷纷抢跑，密集推出了大量支付协议标准：从早期的 **L402**（基于比特币闪电网络与 HTTP 402 协议的微支付标准），到 Coinbase 推出的 **x402**，以及 Stripe 与 Tempo 联合打造的 **MPP**（Machine Payments Protocol: 机器支付协议），再加上 Google 的 AP2、UCP 与各类主流卡组织的规范，支付标准的竞争已进入白热化。

然而，协议层面的喧嚣与链上真实交易数据形成了鲜明对比。监控数据显示，作为当前最主流的两个标准，x402 近 30 天交易额仅有约 100 万美元，而 MPP 甚至只有 1500 美元左右，整体活跃度几乎趋近于零。在供给端并不匮乏（包括 **Apify**、Exa、Perplexity 等工具均已上线目录，月度调用收益数以百万计）的情况下，智能体并未通过自主发现与自主支付来使用工具，而是高度依赖人工预配置。智能体支付在真正落地之前，显然在用户与系统的决策漏斗中遭遇了结构性阻滞。

<details>
<summary>Original English Source</summary>

Hello everyone. Welcome to my session and today I'm going to talk about agentic payments and in particular the pressing question now that we have all the payment protocols: why is nobody using them? Why don't the agents pay?

Before I start, just a quick introduction: at Apify we're running a marketplace of tools for AI, we call these tools actors. We have about 80,000 of them and they cover use cases like extraction of data from social media sites, e-commerce, hospitality, travel, search engines and general automation. Basically they help you automate your work on the web, and these actors are created by a global community of creators. They build them, publish them on our store, and we sell them to the users, to the customers. Just last month we paid almost $2 million to the creators for their actors, so it's a thriving two-sided marketplace. Obviously, you can understand why we take great interest in agentic payments, because for us it's just another way how we can sell our actors, our tools and our creators to more people and agents.

Whenever there was a new way how we can integrate our system, our platform, our marketplace to let agents buy those tools, we went fast and added those things. Actually last year at AI Engineer World's Fair in San Francisco, I was the only one who was talking about this topic of agentic payments and agent economy more broadly, because back then it wasn't really well known. Over the last year and a half, there's been great progress; this year there was a dedicated track for agentic payments.

Now everyone understands that agents, in order to complete ever longer tasks, will actually need budget, because at some point they will ask you to approve something, and if you want them to be autonomous and really complete bigger tasks, you might need to give them money. Gartner predicts that by 2028 this will be like a $15 trillion economy and that 80% of B2B activity between companies will be done autonomously through agents. A lot of players in finance and fintech jumped on this bandwagon because they understand the size of this opportunity.

We saw a lot of different tools and payment standards appear: starting with L402 by Lightning Labs in mid-2020, Mastercard Agent Pay in April, Coinbase x402 in May 2025 (currently probably the most popular), KYA Pay by Skyfire with Visa, Agent Payments Protocol (AP2) by Google, Agent E-commerce Protocol (ACP) by OpenAI and Stripe, Trusted Agents Protocol (TAP) by Visa, Universal Commerce Protocol (UCP) by Google and Shopify, ACTP by Alipay, Machine Payments Protocol (MPP) by Stripe and Tempo, AMMP by Alipay, APOP by UnionPay, OKX Agent Payment Protocol, and Agent Pay for Machines by Mastercard. It became a heated battleground for the future of agent e-commerce.

Crypto is very well positioned to win here. Without a single controlling owner, crypto avoids traditional credit card or PayPal friction, where micropayments are economically impossible due to fees, and chargebacks pose fatal risks in an agent world of infinite autonomous actors. On crypto, there are no chargebacks, only optional merchant refunds. The two most popular standards, Coinbase's x402 and Stripe's MPP on stablecoins, both leverage crypto.

Yet looking at X402scan and MPPscan, over the last 30 days x402 had only around $1 million in volume and MPP only $1,500. It's basically non-existent. Where is everyone? It's not a supply issue—services like Apify, Exa, Perplexity, and Firecrawl are all listed and earn millions monthly via agents, but through pre-shared API keys rather than autonomous discovery and payment. The bottleneck is entirely on the demand side.

</details>

### 支付漏斗上游：API 密钥的路径依赖与需求释放的前提

从支付转化漏斗的角度剖析，首要的阻力在于底层“需求”尚未真正确立。当前绝大多数开发者在构建智能体系统时，采用的依然是预置账户体系与 **API 密钥**（API Key: 用于验证调用方身份的凭证代码）机制，开发者在平台注册后将密钥写入本地配置或通过 **MCP**（Model Context Protocol: 开放模型上下文协议）进行服务挂载，账单由开发者绑定的常规信用卡兜底。这种操作不仅成熟稳定，而且完全避开了复杂的动态支付交互，使得智能体支付的直接竞争对手并非传统银行卡，而是早已根深蒂固的 API 密钥预付费模式。

要打破这种路径依赖并驱动开发者主动授权 Agent 进行自主发现与动态采购，必须依赖三项核心先决条件的成熟：
* **模型可靠度提升带来的资金信任**：随着基座模型推理链路的加长与鲁棒性提升，人类赋予智能体自主支配资金的意愿将逐步确立。相较于向智能体开放敏感系统的写入权限或邮箱访问权所带来的灾难性泄漏风险，设定小额资金预算（如从 5 美元、50 美元逐步递增至 500 美元）在安全上反而是可量化、可隔离的风险。
* **常驻智能体（Always-on Agents）的常态化普及**：具备自主执行能力的个人全天候助手将彻底打破一次性任务的局限，自主调用外部付费服务将成为刚需。
* **模型 Token 补贴时代的终结**：目前高额且廉价的订阅制上下文与算力倾销，客观上导致智能体倾向于“凡事现场从头写代码实现”而非“付费调用现成服务”。一旦主流大模型厂商结束亏损补贴走向盈利与上市，算力经济学将迫使智能体优先采购成熟的垂直微服务。

<details>
<summary>Original English Source</summary>

The best way to understand this is to look at agentic payments as a funnel: it starts with need, followed by setup, discovery, and finally the ability to buy. At every step, we have friction points.

First, the need: most people building agentic systems give them access to services through fixed accounts signed up beforehand via API keys. You create an account on Apify, put the API key into your code or connect via MCP, and pay through your credit card. Agentic payments are not competing with Visa; they are competing with API keys, which are simply far more convenient today.

For people to let their agents discover and buy new services autonomously, several prerequisites must happen:
First, better models: as models improve, agents complete longer tasks autonomously and earn greater trust. People already give agents write access to critical systems—which sometimes leads to disasters or data leaks. Giving an agent a $5, $50, or $500 budget is actually much safer than risking an email leak; losing $50 is sad, but not catastrophic.
Second, the rise of always-on agents: personal, continuous agents will inherently require operational budgets to accomplish real tasks without human stalling.
Third, the end of token subsidies: paying $100 a month for Claude can yield an absurd amount of token value if maxed out. Agents currently have zero incentive to purchase external services when they can write custom scrapers or tools from scratch at negligible token costs. Once IPO pressures or commercial realities end these heavy subsidies, buying specialized API services will become far more economical than re-inventing the wheel dynamically.

</details>

### 配置阻力与去中心化网络中的“信任中介”缺失

当开发者决定赋予智能体支付权限后，紧接着面临的是**配置流程**（Setup）的高摩擦。现阶段的智能体自主支付高度依赖区块链与加密货币底层，而对主流开发者而言，加密钱包的创建、链上 gas 费用管理以及私钥托管机制依然晦涩繁琐。唯有当底层开发工具链全面简化，或者头部智能体宿主平台直接打通原生充值接口（例如直接利用平台的全局订阅积分或统一授信额度向智能体划拨可支配资金），这种基建摩擦才能真正消除。

即便配置完成，智能体也将立刻直面**服务发现与网络信任**（Discovery & Trust）的深层断层。在人类商业历史中，交易信任历经了熟人协作、口碑推荐到现代权威中介（如市政集市、消费者评级、监管机构）的演变；但在机器自治的互联网环境中，智能体面对来自未经验证的第三方 URL 声明，无法判断其服务质量、响应可靠度以及报价真实性。这使得中立可信的聚合目录和平台（如 Anthropic 的验证连接器目录、ChatGPT 插件生态或 Apify 的 Actor 市场）成为不可或缺的信任背书层，充当机器经济里的可信撮合中介。

<details>
<summary>Original English Source</summary>

The second step in the funnel is setup. For many, crypto remains fairly opaque with intimidating terminology. Most people have never set up an independent crypto wallet for an autonomous agent; it requires friction compared to entering a credit card. This will improve with better tooling, and the ultimate unlock will occur when major agent platforms natively integrate balance delegation—allowing users to assign $50 directly from their main Claude or ChatGPT account balance.

Once set up, the next question is discovery and trust. If you buy a service, you need assurance that the provider will deliver what they promise at the agreed price. Historically, human trade evolved from transacting with familiar peers, to personal recommendations, to trusted middlemen like town squares, consumer protection agencies, and marketplace ratings.

In the agent world, there are no innate signals to determine whether an arbitrary API endpoint offering weather data is legitimate or malicious. The same trust architecture is mandatory: either curated networks of known entities, or verified marketplaces. We see this unfolding through Anthropic's directory of reviewed connectors, OpenAI's app store, and Apify's actor marketplace, acting as trusted brokers ensuring transactional integrity.

</details>

### 从固定单价到按量计费：批量结算协议的技术演进

在漏斗的最底端，**履约与支付机制**（Buy / Settlement）本身经历着严苛的技术适配挑战。初期的智能体支付协议几乎完全假定单次 API 调用的固定单价场景（例如查询一次天气扣除固定微额代币），但这远远无法支撑真实的生产级需求。复杂的智能体任务（例如拉起高算力批处理、运行容器或嵌套调用底层推理模型）必须依赖**按量计费**（Pay-per-use: 依据实际计算时长与资源消耗波动态额扣费）模型。

Coinbase 主导的 x402 协议在实现动态可变成本支持的过程中，揭示了底层清算架构的典型演化轨迹：
* **精确支付（Exact Scheme）的局限**：基于 HTTP 402 状态码触发即时签名与结算，仅能锁定固定单价，完全无法适应运行前无法预估实际消耗的长耗时任务。
* **预授权扣费（Up-to Scheme）引发的双花风险**：该机制允许服务商扣除上限以内的动态费用，但由于链上结算存在确认延迟，在缺乏即时锁定的情况下，买方智能体极易在链上清算完成前将钱包余额转移，引发恶意“双重支付”（Double Spending）。
* **充值退款权宜方案的系统摩擦**：为规避双花损失，服务商不得不采用“预先足额扣款，任务结束退款”的折衷路线，这不仅将信任风险逆向转嫁给买方智能体，还导致链上交易频次与 Gas 手续费成倍激增。
* **批量结算（Batch Settlement）的密码学托管破局**：最新推出的结算方案通过在链上构建条件式托管通道，既在链下保障了细粒度微交易的高频流式扣款，又在链上杜绝了资金违约风险，彻底扫清了复杂长效计算任务的技术计费障碍。随着支付漏斗各环节的阻碍被逐一拆解，面向智能体原生经济体系的基础设施已基本就绪。

<details>
<summary>Original English Source</summary>

The final step is to buy. Traditional agentic payment systems only supported fixed price per API call. That is insufficient in practice; you cannot run complex compute or LLM-driven pipelines with fixed costs, you require dynamic pay-per-use billing.

Earlier this year, x402 added batch settlement and MPP added sessions to solve this. The journey of implementing pay-per-use in x402 illustrates the hurdles early adopters faced:

Under basic x402, an API request returns a 402 Payment Required header. The client signs a payment request with funds, the facilitator (e.g., Coinbase) verifies it, the server performs the job, the facilitator settles it on-chain, and a settled response confirms the transfer. If the merchant performs expensive work before settlement confirms and funds fail to arrive, they absorb the loss.

To accommodate variable pricing, x402 first launched the "exact" scheme for fixed pricing, followed by the "up-to" scheme for variable charges. However, "up-to" allowed buyers to double-spend funds before the transaction settled on-chain. As a workaround, Apify implemented an "exact and refund" flow: charging an upfront deposit (e.g., $10), deducting actual consumption (e.g., $2), and refunding the remainder. But this forced agents to place absolute trust in merchants and doubled blockchain transactions and fees.

Recently, the batch settlement scheme solved this by using cryptographic escrow on-chain, enabling safe, low-fee off-chain microtransactions that settle collectively.

The agent payment funnel is finally being fully unlocked. Substantial transaction volumes and the true agent economy are on the verge of starting. Now is the ideal window to prepare your service monetization architecture, as implementation contains subtle complexities, and waiting too long means missing the market shift.

</details>