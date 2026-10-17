---
layout: post.njk
source: https://yage.ai/share/tavily-x402-agent-payments-20260603.html
speaker: yage.ai
title: |-
  Tavily 那一分钱：agent
  支付到底是不是又一个被吹爆的概念
date: '2026-06-03'
summary: 文章探讨了基于x402协议的agent支付，以Tavily搜索API为例，展示了agent如何通过机器对机器的微支付（如每搜索一分钱）实现自主获取服务，无需API key或人工干预。文章分析了该技术的工程可行性、安全风险及未来的商业场景，指出真正的agent支付需要解决授权、风控与微支付结合的挑战，而非仅仅是支付技术本身。
area: tech-engineering
category: ai-application
tags:
  - agent-payment
  - x402-protocol
  - micropayment
  - agentic-commerce
  - eip-3009
people: []
companies_orgs:
  - Tavily
  - Coinbase
  - Cloudflare
  - Stripe
products_models:
  - x402
  - Base
  - USDC
  - AP2
media_books: []
draft: true
status: evergreen
---

如果有人让你相信 agent 支付真的在发生，最好的证据不是协议白皮书，不是
demo 视频，不是 Twitter 上的截图。是一行 shell 命令跑通了。

```
<code class="sourceCode bash"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a><span class="ex">npx</span> awal@latest x402 pay https://x402.tavily.com/search <span class="dt">\</span></span>
<span id="cb1-2"><a href="#cb1-2" aria-hidden="true" tabindex="-1"></a>  <span class="at">-X</span> POST <span class="at">-h</span> <span class="st">'{"Content-Type":"application/json"}'</span> <span class="dt">\</span></span>
<span id="cb1-3"><a href="#cb1-3" aria-hidden="true" tabindex="-1"></a>  <span class="at">-d</span> <span class="st">'{"query":"Who is Lionel Messi?","search_depth":"advanced","max_results":5}'</span> <span class="dt">\</span></span>
<span id="cb1-4"><a href="#cb1-4" aria-hidden="true" tabindex="-1"></a>  <span class="at">--max-amount</span> 10000</span></code>
```

--max-amount 10000。USDC 的最小单位里，10000 就是 0.01
美元。整条链路跑在 Base 这条公链上：一个 agent
用自己的钱包签了一笔链上交易，付了一分钱，拿到了一组搜索结果。钱真的划到了
Tavily 的账上，不是模拟器，不是测试网，不是”未来上线”。

事情发生在 2026 年 5 月 27 日。Tavily 把它的搜索 API 接上了一个叫
x402 的新协议。x402 把 HTTP 标准里闲置了 30 年的
402 Payment Required 状态码终于用了起来，agent
请求一个资源时先收到 402、自动付钱、再拿到结果。Coinbase
牵头做的，Cloudflare、Google、Stripe、Visa、Mastercard 都跟进了。

拿这件事和 2024-2025 年圈子里吹的 “agentic commerce”
比，最大的差异不是协议更规范了，是钱数降下来了。Stripe
一笔信用卡扣费十几块到几百块，那是按人类的消费刻度设计的。一分钱一次搜索，那是按
agent 的消费刻度设计的。

Tavily 这一分钱是一个工程上能跑通的最小单位。agent
真的拿了真钱，买了真的服务。顺着这个案例往下走，能看到哪些 agent
场景确实需要机器支付、哪些只是把旧问题换了个新名字，也能想清楚自己做
agent 产品时要不要把这条线加进来。

## 它真做了

5 月 27 日的官宣博客说：Tavily
Search 现在通过 x402 协议对 agent 开放，不需要 API
key，不需要账号，不需要预付。

Tavily
x402 文档里的细节：

Endpoint: POST https://x402.tavily.com/search

价格: 每次 $0.01 USDC

网络: Base 主网

资产: USDC 合约 0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913

三个 HTTP header 走完全程：PAYMENT-REQUIRED 是服务器告诉客户端要付多少，PAYMENT-SIGNATURE 是客户端签完名回传付款凭证，PAYMENT-RESPONSE 是服务器确认结算后返回链上收据

上游失败时按 EIP-3009 nonce 自动退款

amount: "10000" 是 USDC 的六位小数单位，等于 0.01
美元。--max-amount 10000 是用户给 agent 设的硬上限。Tavily
一次性把 agent 自付搜索做成了产品，不是 PPT。

两个差别最关键。

第一个，它给的是生产 agent 用的，不是 demo 用的。Tavily
文档写明了所有标准搜索参数（query、max_results、time_range
等）照常可用，跑的是 advanced 搜索。对真在跑的研究
agent、coding agent
来说，这次付费调用是一个有价格的、可以审计的事件。

第二个，它不绕着现有的 agent 工具栈走。Coinbase 的 Agentic
Wallet MCP 已经在 Claude Code、Cursor、Codex 里能直接用了，agent
收到 402 响应时自动付款。Cloudflare 的 Agents
SDK 也是原生支持。Tavily 接上了这条链，意味着一个 agent 在 runtime
里自己想”现在需要查一下
X”，就能付钱、拿结果、继续推理。任务流不被中断。

能试。

## 它怎么做到的

HTTP 协议 1996 年就把 402
写进了标准，备注是”留给未来的支付场景用”。30
年没人用，因为那时候没有能撑住的支付基础设施。信用卡按次扣手续费划不来，PayPal
也没法让机器自动调。2025 年 5 月 Coinbase 重新捡起这件事，起了
x402，逻辑就四步：

客户端（agent 或脚本）请求一个 URL。

服务器返回 402 Payment Required，response header 里写明价格、收什么币、在哪条链、收款地址是什么。Tavily 的那个响应里，accepts[0].amount 是 "10000"，network 是 "eip155:8453"，也就是 Base 主网，asset 是 "0x8335..."，USDC。

客户端用钱包签名付款，走的是 EIP-3009 标准的 USDC transfer authorization，签名放在 PAYMENT-SIGNATURE header 里，重发请求。

服务器验证签名、链上结算、返回 200 和实际结果，同时在 PAYMENT-RESPONSE header 里附上链上交易 hash 当收据。

EIP-3009 是整条链路的关键。它是 USDC
合约支持的离线签名标准：agent
在本地签名然后广播交易，私钥不交给任何中间人。为什么 x402
能在几秒内走完”agent 发起、链上结算、拿到结果”的全程，EIP-3009
是答案。

链路里还夹着一个叫 facilitator
的角色，帮服务器做验证签名、广播交易这两件事。Coinbase 跑了一个公共的 facilitator，其他公链和钱包厂商也在跑自己的。Tavily
文档建议用 Coinbase 的。Facilitator
不持币，纯粹是技术中介。这件事的意义在于，服务器不用自己去碰区块链，降低了接
x402 的门槛。

把这几样东西对应到读者已经知道的：

EIP-3009 签名，功能上接近信用卡的 CVV 验证

facilitator，角色上接近信用卡的收单行

Base 主网，可以理解成一条交易费趋近于零的支付专线

USDC，美元稳定币，1 USDC 约等于 1 美元，不波动

0.01 美元 + 几乎为零的链上开销 + 几秒钟结算。这个组合撑住了
agent 时代按次付费粒度。Stripe
那种按每笔交易收手续费的定价模型，根本撑不到这个粒度。

## 为什么是 Tavily

把搜索这类工具拿出来做 x402 的试水，不是随便选的。Tavily
本来就有两条产品线：API key 路径是传统 SaaS，人注册账号、拿 key、塞进
agent、按月结账；Keyless 路径是发一个
X-Tavily-Access-Mode: keyless header
直接调，免费，主要给开发者本地测试用。

x402 是第三条线。文档里写的是：

> “Pay per request for Advanced Search in USDC on Base — no API key, no
> account, no human in the loop.”

搜索特别适合 agent 自付，因为它是一个 agent
最频繁调用的动作。一个长跑的 research agent 不知道下一秒要不要查某个
API、某个数据库、某个垂直数据源。它只知道”现在我需要 X
信息”。如果每一个潜在的搜索和数据服务都需要人预先注册、塞
key、绑卡，agent 就没办法独立运行。

Tavily 这次动作的战略分量比那行 $0.01/search
重很多。第一，它把自己卡进了 agent 工具市场的入口。Tavily 已经上了 agentic.market（agent 的应用商店）和
x402scan（x402 资源浏览器）。agent 启动后想临时找搜索服务，搜 “web
search” 就能看到 Tavily，按次付钱就行。第二，agent
自付这条线跑通，意味着 Tavily 后面的
/crawl、/map、/research
这些更高价的能力，可以陆续按同一条线商业化，不用依赖人类订阅。第三，搜索
API 行业里它第一个动。Parallel、Exa、Brave 大部分还在 API key
模式，少数开始接 x402，但 Tavily 是第一个把 agent
自付做成明确产品线、进了 bazaar、配套文档全做齐的。

搜索还有一层不那么显然的好处：试错成本低。结果错了，浪费一分钱。agent
被诱导付了款，一分钱乘几万次也就几百块。这比让 agent 自己去刷 Stripe 买
SaaS 订阅、做 KYC、签合同的成本低至少一个数量级。

## 谁在抢这条线

x402 不是 Tavily
一个人在搞，它属于一个正在快速成型的栈。放大了看，能避开”是不是被 Tavily
PR 带着走”的疑问。

支付结算层至少有三家在动。

x402 是 Coinbase 牵头、Cloudflare 深度支持的协议，在 HTTP 402
上用稳定币按次结算。Solana 上已经跑过 35M+ 笔交易，全网大概跑出了 10
亿美元年化稳定币结算量。Cloudflare 的数据显示他们的边缘网络每天处理大约
10 亿个 402 响应，里面绝大多数是历史遗留的错误响应，但这条 status code
现在确实在被真正使用。

和它对着的是 Stripe 和 Tempo 做的 MPP。MPP 兼容 x402 的
exact charge
流程，但多了几样东西：支持多支付方式（卡、钱包、稳定币、Lightning），走
IETF 标准化（已经提交 Internet-Draft），有 streaming session 机制（agent
预存一笔钱，后续调用走链下 voucher，不用每次上链）。Stripe 既加入了 x402
Foundation 又在推 MPP，姿态很清楚：x402 是开放协议，加入没坏处；MPP 是
Stripe 主导的，是他们想押的那个未来。

斜上方还有 Google 的 AP2。AP2 解决的不是”怎么付钱”，是”谁授权了 agent
付钱”。用 mandates（加密签名的授权契约）回答三个问题：用户有没有授权
agent 做这件事、agent 的请求是不是真实反映了用户意图、出了错谁来担。x402
已经被作为 crypto payment 扩展接进了 AP2。Google 在 2026 年 4 月把 AP2
捐给了 FIDO Alliance，等于承认这一层是公共协议，不是哪家公司的私货。

这三层之外，需要看一眼整条链路才能把 x402 的位置放对。之前在 《AI
替你付款前，支付系统要先补上这条信任链》 里分析过 agent
支付的全生命周期，从用户意图到授权边界，再到凭证发放、商户接单、网络风控、审计争议，最后还有个”Agent
即使被授权、能付款、可追责，也未必真的买得对”的问题。x402
补的是这条链路上的付款凭证与结算那一环，是
AP2（授权）和商户接单之间的那段。Tavily
这一分钱的价值，不在它填了整条链，而在它让你看到其中一个环节在真实环境里跑了。

短期看，x402 抢的是先发优势。CryptoSlate 行业数据显示 x402
调整后月交易额从 2025 年 11 月的 $5.15M 峰值跌到 2026 年 5 月的
$1.19M，跌了 77%。同期 raw 交易数反弹到了 2.89M。先发不一定是终局。

中期看，6 到 18 个月内，谁能解决高频小额这个场景谁就赢。MPP 的
streaming session 走的是预存加链下 voucher 的路，x402 的
upto scheme
是按结算时实际消耗付费。这两个细节决定了哪条协议能撑住每秒上千次 agent
调用。

长期看，18 个月以后，最关键的已经不是支付层，是授权和风控。AP2 加上
policy engine 加上 identity layer，一起决定这条栈能不能生产化。x402
是必要条件，但远远不够。

## 真实的担忧

如果有人觉得”钱包里有 USDC，agent 就能付钱”就够了，那 Tavily
这件事会被用错。把 Tavily docs 和 Halborn
的 x402
安全分析放在一起读，能拉出六条要么已经发生要么高概率要发生的风险。

第一条，prompt injection 诱导 agent 乱付钱。这是最现实的一条。agent
在读一个网页，网页里藏了一条指令让它调用某个 API 查天气。agent
一执行，付款地址已经换成了攻击者的钱包。Halborn 的分析里直接写了：“A
malicious 402 page could be used to trick an autonomous agent into
paying more than intended for a particular resource.”

第二条，付款回放。同一笔签名被复制粘贴反复用。Tavily 用 EIP-3009
nonce 挡住了一部分，但前提是服务器自己维护 nonce
数据库。实现偷懒的话，攻击者可以拿一次付款无限次调用。

第三条，中间人篡改 402 响应。攻击者把 payTo
地址换成自己的，agent 照样签、照样付。HTTPS/TLS 加上 header 内的 payload
签名是必要条件，缺一不可。

第四条，钱包被盗。agent 跑的那台机器被攻破，钱包里的 USDC
一次被掏空。这不算协议漏洞，是工程问题：需要给 agent
单独开小钱包，余额小到即使被偷了损失也可控。

第五条，链上隐私泄露。所有 402 付款都在 Base
链上公开可查。谁付了多少钱、付给了哪个服务商、查了什么，关联起来能画出
agent 的行为画像。Halborn 的建议是用一次性地址打断这种可关联性。

第六条，facilitator 中心化。一个 facilitator 挂了或者被审查，整条
x402 流程可能跟着断。生产系统需要支持多个
facilitator，或者服务器自己直接做 on-chain 验证。

落到自己产品上，该做的事是这几件。给 agent 单独开钱包，主钱包不要碰
agent 的调用流程。agent 的钱包只放够一两个 session 的 USDC（Tavily
文档里直接提示了这一点）。强制硬上限，--max-amount 10000
这种 flag 不是可选的，是必须的。白名单收款地址，对
accepts.payTo 字段做 policy engine 校验，新地址强制走
human-in-the-loop。审批分层：小额自动过，中额确认，大额走独立审批流。AWS
的 sample architecture 给了一种工程模板，agent 提议付款，Spend
Governor 查 policy 才放行。最后，所有 402
challenge、所有付款、所有失败都进日志，链上交易可回查。

这些不该叫建议。该叫”没做就别上生产”。

## 对你意味着什么

做 agent 产品的人要不要接 x402 这种支付层，看 agent 长什么样。

短期，6 个月内，大概率不用。Tavily 这种 agent
自付搜索对你用户的当前价值是 demo 级的，不算生产价值。生产 agent 用 API
key 还是更便宜、更可控、更可审计。$0.01/call
听上去便宜，一个 agent 一次任务可能调几十次，再加链上开销和 prompt
injection 风险，总成本和管理负担会超过省下来的免 key 的便利。

但短期 x402
对你有一个非技术的、单独成立的价值：用来给非技术的人讲清楚 agent
时代长什么样。让一个 PM 或 CEO 亲眼看到 Claude Code 自己拿钱包调
Tavily，比任何路演 slide 都管用。

这里有一点值得和 信任链那篇
的结论对照着看。信任链那篇说 agent 支付短期内最现实的两条路径是人在场的
checkout 先普及、企业自动支出先落地。Tavily 的 x402
是这两条路径之外第三条正在成型的线：不是 consumer
端替人买东西，也不是企业端虚拟卡自动采购，而是机器对机器的 API
级微支付。这条路目前体量最小，但它对 agent builder
的适配度可能最高。你就是做 agent 的人，你的 agent 每天要调几十个
API，其中一些不是你自己管理的。x402 解决的是这件事。

中期，6 到 18 个月，三种场景会让你必须接 x402 或同类方案。第一种，多
agent 协作系统，主 agent
临时需要调一个它没见过的工具，比如某个垂直数据源、一个 fine-tuned model
API、一个特定的 scraper，按次付钱比提前注册五十个 API key
干净一个量级。第二种，agent marketplace
启动以后，x402scan、agentic.market 这类目录会变成 agent
真正的应用商店，你的工具不在上面就缺席了一个分发渠道。第三种，企业做
agent 部署，用 x402 替代内部 API gateway 加 key
管理这套东西做轻量采购，按次结算天然和 P&L 对齐。

长期，18 个月以后，别把注意力盯在支付层上，盯在授权和风控上。AP2 加
policy engine 加 identity layer 一起决定这个栈能不能走成生产级。你的
agent 钱包策略、budget cap、allowlist
机制，比”接哪个支付协议”重要至少一个数量级。

## 怎么看真伪

怎么分辨一条 agent 支付新闻是炒作还是真进展，看三样东西。

第一，它真的花了一笔真钱。demo 视频和”$0.01 到账了”是两码事。Tavily
这次发的是真产品、真 endpoint、真 Base 链上的真交易。

第二，它解决的是 agent 时代特有的问题，不是把旧问题换了个名字。“用
stablecoin 跨境汇款”不算，PayPal 早就在做。“agent
在运行时自动发现一个陌生 API 并付费调用”才算。

第三，它的钱数和频率接近 agent 真实工作流的形状。$50 月费不是按 agent
的消费模式设计的，agent 跑三十分钟就花完了。$0.01/call
才是。一次研究任务可能调 50 到 200
次搜索，一次一分钱，总成本一到两美元，agent 自己的预算能 cover。

三条全中，可以认真看。只中一条，大概率是 PR。

Tavily 这一分钱是一个工程上能跑通的最小单位。它说清楚了一件事：agent
时代花钱这件事，钱数很小，速度很快，不需要人介入，事后可以审计。这套组合以前在生产里没有真正出现过。现在出现了。