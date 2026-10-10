---
layout: post.njk
source: https://yage.ai/share/agent-auth-gateway-not-crypto-20260814.html
speaker: yage.ai
title: Agent 授权的竞争，不在密码学，在信任的归属权
date: '2026-08-14'
summary: 文章探讨了Agent授权机制的演进，核心在于从传统的静态检查点授权转向沿着Agent工作生命周期的动态授权线。文章分析了平台托管派（如Vercel Connect）和客户边界派（如OpenAI/Ona）在凭证托管权上的分歧，以及由此带来的集中管理与锁定的权衡。最终指出，当前架构的空白在于凭证线与数据线的整合，以及信任机制在平台与客户边界之间的流动难题。
area: PAI
category: ai-tooling
tags:
  - agent-authorization
  - token-management
  - trust-model
  - lifecycle-management
  - lock-in
people: []
companies_orgs:
  - Vercel
  - Anthropic
  - OpenAI
  - Cloudflare
products_models:
  - Vercel Connect
  - Claude Tag
  - Ona
media_books: []
draft: true
status: evergreen
---

## 一个追问，和它意外戳破的东西

我第一次看 Vercel
Connect 的时候，有一个怀疑卡了很久。Vercel Connect 是 Vercel 2026 年
6 月发布的功能，给跑在 Vercel 上的 agent 使用。agent 调
Slack、GitHub、Notion
这些外部服务时，不再在环境变量里塞一个永不失效的全权限
token，而是在真正需要调 API 的那一刻，调一次 getToken()
拿一枚短命的、只够干这一件事的凭证。

我马上冒出一个怀疑：getToken
自己也需要认证，它拿什么证明自己有资格领这个短命凭证？如果这个认证用的也是长寿命、永不失效的东西，泄露之后和我原来那个全权限
token 泄露有什么区别？短命凭证可以撤销，原来的全权限 token
也能撤销。这个功能到底比原来改进了什么？

理解这个问题需要先看 OAuth
的常规流程。平时应用集成第三方服务，走完授权之后会拿到两样东西：一个短命的
access token，拿着它调 API；一个长命的 refresh token，access token
过期后拿它换新的 access token。refresh token
是真正的钥匙，平时不经常使用，但只要它在就能反复换出新的 access
token。常见的做法是把 refresh token
存在应用自己的环境变量或数据库里，需要换 token 的时候拿出来用一下。

Vercel Connect 做的第一步，是把 refresh token
从应用的环境变量里挪走。走完授权流程后，refresh token 存在 Vercel
的基础设施上，应用代码永远拿不到它。应用代码只能调用
getToken()，由 Vercel Connect 拿着 refresh token 换一枚短命
access token 给应用，用完即过期。getToken 自己的认证依靠
Vercel deployment 的 OIDC token。它短命（本地开发大约 12
小时过期，生产环境自动注入与轮换）、绑在具体 project 和 environment
上，证明的是这段代码属于哪个 Vercel project，并不证明拥有 Slack
权限。Connect 拿着这个身份去查 project link，确认 project
是否有权使用这个 connector、environment 是否在允许列表里，通过之后才发
access token。

危险的长寿命 refresh token 从应用环境里消失了。Vercel
官方文档里有一句话把这个差别说到了点子上：“A vault makes that token
harder to steal. It doesn’t make it less dangerous.” 他们没有给 token
加个保险柜，他们让危险的东西根本不出现在应用代码里。

到这一步我以为追问结束了。凭证挪走了，应用代码里没有长寿命的东西了，问题看起来解决了。但顺着这条线再推一步，事情并没有这么简单。

## 追问没结束：它到底好在哪

如果攻击者偷到了这个 OIDC token 呢？OIDC token
在过期之前，攻击者拿它去 Connect 请求短命 access token，Connect
照样会发。在这个维度上，一旦凭证泄露，新旧模型没有本质区别。攻击者在凭证有效窗口内拿到
access token，后果是一样的。传统模式下发现 refresh token
泄露，同样可以在 provider 端撤销授权。

那就只能看 scope 了。Connect 每次调用 getToken()
可以传入 scope 参数，把拿到的 access token
限制在只够干眼前这一件事的程度，这总该是它的技术创新了吧？

仔细看 OAuth 协议就会发现，事实依然不是这样。refresh token
能够换出多宽权限的 access token，在用户同意 OAuth
授权的那一刻就固定了。用户自己对接 OAuth 时，完全可以配置窄 scope，例如
GitHub fine-grained token 同样可以限制到单一仓库的只读权限。Connect
只是把 scope 暴露成每次 getToken()
的可选参数，并不会让权限神奇地变窄。如果两边都配置了相同的窄
scope，自己存 refresh token 和 Connect 替你存 refresh
token，在凭证泄露后的影响范围上没有任何本质差异。

追到这里，才看清 Connect 真正的落脚点。它没有让应用变得更安全，scope
照样需要手动配置，安全 best practice 一点也不能少。它的真实价值是把所有
provider 的凭证请求聚到一个出口，卖的是集中管理。

这和 OpenRouter 聚合模型访问是同一种模式。OpenRouter
没有让模型调用变得更聪明，它让开发者只需要维护一个 API 端点。Connect
之于 OAuth 集成，就相当于 OpenRouter 之于模型
API。它没有省去安全判断的力气，省去的是管道对接的力气，代价是需要学习多一层抽象概念，例如
project link、environment 和 authorizationDetails。

理清这个框架之后，2026
年十几家公司的动作就有了统一的读法。它们没有一家在发明新的密码学机制，争夺的是谁来托管、谁来记账、谁来定边界。归属权之所以有得争，是因为谁占领了
gateway，谁就锁住了未来的迁移成本。这是 business model 的创新，并不属于
engineering practice 的创新。

## 授权从一个点变成一条线

授权从一个检查点变成一条生命周期线，各家占其中一段

理清 gateway
这个框架之后，我顺着这些公司的动作看下去，发现一个更意外的结构：授权的形状变了。之前做
agent 的时候，咱们习惯把授权当成一个发生在瞬间的静态检查点。agent 调外部
API 的那一刻，网关或者 MCP
校验一次身份，放行就结束了。校验发生的瞬间，数据读取完毕，生成产物，授权动作也随之宣告结束。后续数据去了哪里、谁能看到、什么时候收回，当时都没有跟踪。

但顺着 2026
年这一波公司的动作追踪下去，我发现授权已经从过去的一个点，延伸成了一条沿着
agent 干活的物理动作推进的生命周期线：先获取凭证，再调用
API，读到的数据落入工作区或产物中，这些产物接着分享、导出或交给其他
agent，最后还需要支持撤销。每一个环节都变成了可以单独把守、单独记账的地方。把这些公司的方案排在这条线上，我发现它们每家其实只占领了其中一段。

我把这两个产品放在一起看，各段管理的具体对象差异非常明确。Vercel
Connect 管理的是凭证本身：一枚 token
何时签发、权限多窄、何时撤销、谁请求过它，2026 年 8 月 11 日更新的
Observability tab 就是给这个环节记账。Cloudflare OS 在 2026 年 8 月 5
日开源，它管理的是凭证换来的数据：agent
每次读取外部数据源，必须调用 authorizeObservation()
向内核报备数据源 ID 和所需权限，内核存在 Overseer
的持久化清单中，如果有同伴尝试打开或分享这个工作区，拿这个人的身份逐一重验清单上的每个数据源，缺乏权限就会拦截。Cloudflare
官方有一句话把这两段的区别说到了点子上：MCP 告诉你 agent
能调哪些工具，但不告诉你 agent
实际读了哪些行、哪些文件、哪些仓库（“which tools an agent is allowed to
invoke. It does not tell you which rows, files, or repositories the
agent actually
read”）。一个记录凭证存活时间和调用动作，一个记录数据来源与分享后的访问权限。同一条线上，不同段管理着不同的对象。

顺着这条线看下去，其他环节也有公司在占据。GitHub Copilot
把守的是入口准入，它的 MCP allowlist 限制开发者只能使用企业 registry
里的 server，不在名单上的 runtime 直接阻断，audit log
记录配置变更，但明确不记录具体 session 和 tool call 细节。Microsoft 和
Google 占据的是身份环节，给 agent 分配独立的非人类身份（Entra Agent ID
或基于 SPIFFE 的 Google Cloud Agent Identity），分别接入已有的
Conditional Access
和审计体系，贯穿全线但落脚在调用发生之前。每家只占领一段，没有哪一家从头管到尾。

我梳理时间线时注意到，这些动作的同步发生不是巧合。2026 年 3 月到 8
月，五家平台加上一排 IAM 厂商，在五个月里密集发布面向 agent
的凭证与授权能力。仅在 8 月的前两个星期，Cloudflare 开源 OS、GitHub 增加
agent 活动指标、Vercel 增加 Observability
三件事情叠在一起。起点虽然不同，但落脚点都在同一条生命周期线上的不同段落。这种每家只管一段的现状，也直接引出了下一个更深的问题。

## 真正的分歧：信任放在哪

信任落在哪：平台托管派与客户边界派的两极

看到每家只占一段，我顺着这条线往下想，碰到了一个更深的分歧。比起具体管哪一段，真正决定架构走向的，是那个能直接操作内部系统的凭证到底该交给谁保管。追看这些公司的方案，我发现它们清晰地分化成了两极：一派选择交给平台，一派选择留在自己手里。

交给平台这一派，Vercel Connect 和 Anthropic 的 Claude Tag
是典型代表。Vercel 把 refresh token 存在自己的基础设施上，审计账本停留在
Observability tab 里，长期留存靠 Drain 转发到 SIEM。Anthropic 在 2026 年
6 月发布 Claude Tag，给 agent
一个专属身份，凭证绑定在身份上，撤销靠禁用身份，所有动作记录在身份名下。这两者的共同逻辑是：开发者信任平台来保管危险凭证，换取省事和现成的工具。

我顺着这一派看下来，发现它出售的核心价值偏向集中管理，而非更强的安全性，因为
scope 依然需要开发者自己配置。它卖的是集中管理，把管道对接的力气从 N
套降低到 1 套。而这正是 lock-in 的入口：一旦中间人成为 N
个集成的唯一出入口，迁移成本就从 1 变成了 N，需要重新在 N 个 provider 接
OAuth 并重建审计管道。lock-in
是这个模式的引擎，并不是无意产生的副作用。应用使用得越深，迁移的门槛就越高。

而看到 OpenAI 宣布收购 Ona 的时候，我看到了完全不同的另一套解法。2026
年 6 月 11 日，OpenAI 宣布收购 Ona。Ona
的模式是 customer-controlled execution：agent
运行在客户自己的云环境里，凭证、数据、审计全留在客户侧，OpenAI
只提供智能与编排。OpenAI 在收购声明中列出了一串企业需要控制的要素：agent
跑在哪、能访问什么、凭证怎么 scope、活动怎么记日志、工作怎么过审（“where
they run, what they can access, how credentials are scoped, how activity
is logged, and how work moves through
review”）。每一项的答案都落在客户的边界之内。这条路线押注的是：受监管的企业不会把能直接操作系统的凭证交给第三方平台。

Cloudflare OS
的位置更微妙一些。它是开源项目，开发者可以自建，凭证和审计理论上都能留在自己的基础设施里。但我看它的底层架构时发现，它的
Gatekeeper、Overseer 和沙箱基于 Cloudflare Workers 和 Durable Objects
构建，默认运行在 Cloudflare
的平台上。有独立文章对这一点提出了批评：这套不信任任何人的架构，最终建立在信任那个浇筑了地基的单一方之上（“the
architecture that trusts no one rests entirely on trusting the one party
that poured the ground beneath it”，来源）。机制虽然开源，但如果不进行彻底自建，信任的基础依然建立在
Cloudflare 的底层服务之上。

把这两条路线放在一起对比，能看清它们权衡的焦点在于是否愿意用 lock-in
换取省事，而不是哪一方的加密更安全。平台托管派用让渡凭证托管权和承受 N
倍迁移成本为代价，换来管理成本从 N 降到
1；客户边界派将控制权和合规边界留在自己手中，代价则是自行搭建执行环境、自行维护审计管道以及编写
N 套
OAuth。这种两极分化的选型对立，在接下来归纳它们的底层信念时表现得更加明显。

## 四个信念，不是十几家公司

把这些公司的动作放在一起看，我发现它们背后其实是四个信念。每一个信念决定了一把尺子：它相信什么，就会把力气花在哪个环节；而顺着它的设计往下看，就能看到它留下的盲区。

第一种思路相信管好凭证就足够了，Vercel Connect 和 MCP
授权规范属于这一类。它相信安全风险主要来自长寿命的全权限 token，换成短命
scoped token、运行时交换以及审计账本，问题就能解决。它的力气全部花在
token 的 mint、scope、revoke
和事件记录上。但我观察到它的盲区在于凭证使用之后的环节：token
换来的数据落入工作区、分享出去或导出时，这个机制不再干预。Vercel
自己也承认这一边界，撤销是否真正生效取决于 provider 是否提供撤销
API，若无此 API，已签发的 token 在 provider
端会继续维持有效直至自然过期。管好凭证环节，并不意味着数据环节获得了安全保证。

第二种思路相信凭证管好依然不够，必须管控数据的去向，Cloudflare OS
属于这一类。它相信真正的泄漏发生在数据读取之后：agent
读取了一张敏感数据表并生成看板发给未经授权的同事，在那个瞬间凭证校验早已通过，前端关卡无法拦截。它的力气集中在观察记录与共享准入校验上。但我看它的架构时发现，它的盲区在于凭证本身的签发与
scope 设置，它依赖现有的 MCP 或 API
网关在调用前把关，自己不触碰凭证生命周期。此外，完整的报备依赖于每个驱动程序的准确实现，内核无法强制保证分页、子
session、缓存等边缘路径绝无遗漏。数据环节得到管控，凭证环节与出口环节依然属于其他系统的职责。

第三种思路相信核心问题在于管在何处，不在于管什么，OpenAI 宣布收购 Ona
属于这一类。它相信凭证、数据、审计的具体细节不是决定性因素，关键在于这些资产在物理上落在谁的边界之内。agent
运行在客户的云端，凭证存放在客户侧，审计保存在客户侧，平台仅提供智能服务。它的力气集中在执行环境的归属权上。但顺着实际落地的过程看，我发现它的盲区在于这条路线要求客户自行搭建执行环境与审计管道，实施门槛明显高于平台托管方案，而且
Ona 的收购尚未正式交割，相应能力还没有全面落地。

第四种思路相信核心问题在于 agent 缺乏独立身份，Anthropic 的 Claude
Tag、Microsoft 的 Entra Agent ID 以及基于 SPIFFE 的 Google Cloud Agent
Identity 属于这一类。它相信只要赋予 agent 一等公民身份，现有的
IAM、Conditional Access 和审计体系就能顺畅延伸过来。它的力气集中在把
agent 纳入既有的身份基础设施中。但我注意到它的盲区在于，身份明确了 agent
的归属，却无法直接解决 agent
代表谁读取了哪些具体数据，也无法追踪读取后数据的去向。身份是贯穿全线的基准锚点，但拥有锚点并不等同于把守住了全线的每一个环节。

这四个信念并非完全互斥，看了一圈下来，目前还没有一家公司能够仅凭单一信念覆盖完整的生命周期。Vercel
管理凭证但不管理数据流，Cloudflare 管理数据流但不管理凭证签发，Ona
强调归属权但机制成熟度尚需时日，身份派定义主体但无法全面管控行为。这种各个玩家分别占据一角的格局，恰恰说明整个领域还处于非常早期的拼图阶段。

## 空白在哪

把这些方案拆开看完，最明显的空白在于凭证线与数据线至今还没有整合到一起。Vercel
Connect 能够记录 token 何时请求、分配了什么 scope
以及何时撤销，但它无法追踪这个 token
换来的数据落入工作区后接触了哪些敏感源，也无法感知产物分享给其他人时谁依然具备查看权限。Cloudflare
OS 能够记录 agent
读取过哪些数据源并在分享时重验权限，但它无法告知调用的凭证是如何签发的、scope
约束有多窄以及授权来自何处。一个负责凭证，一个负责数据，各自独立运行，尚无单一方案能够完整回答
agent 代表谁、使用了什么凭证、读取了什么内容以及读取后交付给了谁。况且
Cloudflare OS
自身也指出统一的出口检查机制尚未完成，数据读取完毕后向外发送请求的那道卡口仍需补充。

第二个空白在于跨越边界的信任机制。平台托管派的审计账本保存在平台侧，若要长期留存必须将数据拉取至自身的
SIEM，但在拉取之前数据依然处于平台的管控下。客户边界派将账本保留在客户侧，但
Ona 尚未完成交割，自建 Cloudflare OS
的技术门槛依然偏高。目前尚无产品能够顺畅解决信任在平台与客户边界之间流动的难题。

面对这些未解决的空白，咱们做架构选型时其实只需要沿着两条核心轴线来画框。第一，需要管控到生命周期线的哪一个环节？如果
agent 仅仅用来调用 API
而不涉及产物落盘与分享，聚焦凭证环节可能就已经足够，Vercel Connect 或
MCP 规范层就是合适的落脚点。如果 agent
会读取敏感数据、生成分析看板并分享给同事，仅靠凭证环节显然不够，Cloudflare
OS 所采用的读取报备与共享重验才是需要评估的方向。

第二，希望将信任建立在何处？如果接受将凭证托管给平台以换取开发便利，Vercel
和 Anthropic
提供了现成的基础设施。如果处于严格监管行业、凭证不能离开自身边界，则需要考虑
Ona 所代表的客户边界路线，或者选择自行搭建 Cloudflare OS。

管到哪一步、信任放哪里，是这个领域里真正重要的两条选型轴线。记诵十几个产品名称并无实质帮助，把握这两条轴线，面对任何新出现的架构方案都能迅速完成定位。而眼下的行业现状是：尚未有任何一家玩家能够全面覆盖这两条轴线。

追到这里，我能说一句总结性的话了：这些产品没有一款能让系统变得更安全，它们带来的改变是让管理变得更集中。gateway
聚合是它们出售的核心价值，lock-in
是随之而来的代价，而更安全只是营销层面的叙事。能够清晰分辨这三点，咱们在选型时就不会轻易顺着任何一家厂商的宣发话术走。