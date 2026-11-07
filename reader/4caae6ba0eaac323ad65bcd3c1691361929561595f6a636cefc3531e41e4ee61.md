---
author: AI Engineer
date: '2026-11-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YX4Z4XqZ9Vo
speaker: AI Engineer
tags:
  - ai-agent
  - developer-documentation
  - crypto-payments
  - api-design
title: AI Agent 时代的文档与支付：Mintlify 与 Coinbase 对谈
summary: Mintlify 联合创始人 Hamby 与 Coinbase AI 产品负责人 Lincoln 探讨了面向 AI Agent 时代的基础设施变革。访谈涵盖 Agent 成为互联网主要交互者后文档对上下文窗口和准确性的新要求、Coinbase 如何通过加密货币与开放 API 支持 Agent 微支付与自主交易，以及自建与采购工具在维护成本上的权衡。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Mintlify
  - Coinbase
products_models: []
media_books: []
status: evergreen
---
### 介绍与 Agent 时代的文档转变

>> 嗨，很高兴见到大家。非常感谢各位的到来，希望大家今天都有一个美好的开始。很高兴认识大家，我是 Hamby，Mintlify 的联合创始人兼 CTO。Mintlify 是一家位于旧金山的 B 轮公司，我们为像 Coinbase 这样的公司提供开发者文档支持。你要做个自我介绍吗？
<details><summary>Original English</summary>
>> Hi.
 Nice
 to
 meet
 you
 all.
 Um,
 appreciate


you
 guys
 all
 coming.
 Um,
 hope
 everyone


is
 having
 a
 good
 start
 to
 their
 day.


Um,
 nice
 to
 meet
 you.
 I'm
 Hamby.
 I'm
 a


co-founder
 and
 CTO
 at
 Mintlify.


Uh,
 Mintlify
 is
 a
 series
 B
 company
 based


in
 San
 Francisco
 and
 we
 power
 developer


documentation
 for
 companies
 like


Coinbase.


Um,
 would
 you
 like
 to
 give
 an
 intro?
</details>

>> 好的，没问题。大家好，我叫 Lincoln，是 Coinbase 的 AI 产品负责人。大家可能知道 Coinbase 是一家加密货币公司，但它正在广泛拓展到各种资产以及支付领域，此外还有一个 Agent 视角，我们稍后很快会聊到这一点。
<details><summary>Original English</summary>
>> Yeah,
 sure.
 Everyone,
 my
 name
 is


Lincoln.
 I'm
 the
 head
 of
 AI
 product
 at


Coinbase,
 uh,
 which
 you
 might
 know
 as
 a


crypto
 company,
 but
 is
 widely
 expanding


into
 all
 sorts
 of
 assets
 and
 uh,


payments
 as
 well
 and
 there's
 also
 an


agentic
 angle,
 which
 we'll
 be
 talking


about
 here
 shortly.
</details>

>> 好。你想先来提第一个问题吗？
<details><summary>Original English</summary>
>> Yeah.


Um,


do
 you
 want
 to
 go
 and
 ask
 the
 first


question?
</details>

>> 好的。我们采用的形式就是炉边漫谈，来回交流，聊一聊我们如今如何看待这个世界，我们各自的公司如何为这个 Agent 化的未来构建产品，以及我们认为事情大概会朝什么方向发展。那么 Hamby，你能用一个问题来为我们开场吗？抱歉，我先……哦，对，就是这个。我们如何看待 Agent 正在成为互联网上的主要行动主体，以及成为人们互联网体验主要依赖的事物？比如我可以去告诉一个 Agent 帮我设置 Coinbase for Agents，它会找到我们的文档并完全替我搞定一切。当你思考如何构建文档时，这会怎样改变其中的重点？
<details><summary>Original English</summary>
>> Yeah,
 sure.
 So,
 the
 format
 was
 just
 kind


of
 kind
 of
 fireside
 chat
 back
 and
 forth,


talk
 a
 little
 bit
 about
 how
 how
 we
 view


the
 world
 today,
 how
 our
 respective


companies
 are
 building
 for
 this
 agentic


future
 and
 where
 we
 kind
 of
 think
 things


will
 will
 go.
 So,
 Hamby,
 can
 you
 kick
 us


off
 with
 uh,
 with
 a
 question
 here?


Sorry,
 I'm
 just


Oh,
 yeah,
 yeah,
 yeah.


This
 one.
 So,
 yeah,
 how
 how
 do
 we
 think


about
 agents
 becoming
 the
 the
 primary


actor
 on
 the
 internet
 and
 the
 primary


thing
 that
 people
 are
 using
 as
 as
 part


of
 the
 uh,
 their
 internet
 experience?
 I


can
 go
 tell
 an
 agent
 to
 go
 set
 up


Coinbase
 for
 agents.
 It's
 going
 to
 find


our
 docs
 and
 do
 it
 all
 entirely
 for
 me.


How
 does
 this
 change
 what's
 important


when
 you're
 thinking
 about
 how
 you're


building
 docs?
</details>

>> 当然可以。Mintlify 成立于 2022 年，可以说是在 ChatGPT 之前，特别是 GPT-3 之前。我觉得以前大家会更加看重设计和前端，我个人非常热爱设计，我们公司到现在也绝对是一家设计驱动的公司。所以老实说，这仍然让我感到有些遗憾——Agent 根本看不到你的网站，它们不在乎它长什么样，也不在乎它的品牌形象。因此，最终变得重要得多的反而是像页面大小这样的东西。比如，它是否占用了大量的上下文窗口？

还有内容是否准确，因为一个 Agent 在阅读你的文档并进行设置时，如果遇到一点小阻碍，它就会直接停下来，不会去试着排查调试。它可能会尝试去暴力破解解决，但它也同样容易流失并转向另一款产品。所以我确实认为，编程 Agent 让整个世界的运转变得快了许多，工程团队或具体到 EPD 团队正在看到巨大的生产力提升，而组织的其余部分也需要跟上节奏。我认为我们所有人跟上工程团队所展现出的生产力提升速度的唯一方法，就是利用 AI 来跟进。这意味着，当然，文档好不好要主观得多，比如 AI 写作——我个人目前也还在摸索。但我确实认为，建立自动化流程来确保内容不会过时是非常非常重要的。我也很好奇你的看法。既然现在 Agent 正在互联网上进行交易，这如何改变了 Coinbase 对交易本身的看法？
<details><summary>Original English</summary>
>> Yeah,
 of
 course.
 Um,
 so,
 Mintlify
 was


founded
 in
 2022,
 so
 pre-chat
 chat
 GPT,


uh,
 GPT-3
 specifically,
 I
 would
 say.


Um,
 and
 I
 would
 say
 that
 previously


there
 was
 like
 much
 more
 of
 an
 emphasis


on
 design
 and
 front
 end,
 which
 I


personally
 love
 design
 and
 we
 are


definitely
 like
 a
 design-led
 company


still.
 So,
 it's
 kind
 of
 still
 it
 kind
 of


makes
 me
 sad.
 I'm
 not
 going
 to
 lie,
 the


fact
 that
 like
 the
 agents
 do
 not
 see


your
 website
 and
 they
 do
 not
 care
 what


it
 looks
 like
 or
 what
 the
 branding
 of


it.
 And
 so,
 what
 ends
 up
 mattering
 a
 lot


more
 is
 like
 things
 like
 page
 size.


Like,
 is
 it
 taking
 up
 a
 bunch
 of
 like


the
 context
 window?


Uh
 like
 the
 the
 content
 being
 accurate


because
 like
 an
 agent
 can
 like
 set
 like


read
 your
 docs
 and
 set
 it
 up,
 and
 then


if
 it
 runs
 into
 like
 a
 little
 friction


point,
 it's
 just
 going
 to
 stop.
 It's


just
 like
 it's
 not
 going
 to
 like
 debug


it.
 It's
 It
 might
 just
 like
 It
 might
 try


and
 try
 to
 like
 brute
 force
 it,
 but
 then


it
 can
 also
 just
 as
 easily
 churn
 to


another
 product.
 And
 so,
 I
 do
 think


like,
 you
 know,
 like
 coding
 agents
 have


made
 the
 world
 like
 move
 so
 much
 faster,


and
 it's
 important
 that
 like
 I
 like


engineering
 or
 EPD
 specifically
 is
 like


seeing
 so
 many
 like
 uh
 like
 productivity


gains,
 and
 uh
 like
 the
 rest
 of
 the
 org


kind
 of
 needs
 to
 catch
 up,
 you
 know?
 And


I
 I
 think
 the
 only
 way
 in
 order
 for
 us


to
 all
 move
 at
 the
 speed
 that
 like
 the


productivity
 gains
 that
 engineering
 is


seeing
 is
 to
 kind
 of
 use
 AI
 to
 kind
 of


keep
 up.
 And
 that
 means
 like,
 of
 course,


it's
 a
 lot
 more
 subjective
 like
 whether


the
 docs
 are
 good
 or
 like,
 you
 know,


writing
 AI
 writing
 I
 I
 like
 I
 personally


like
 I'm
 still
 figuring
 that
 out.
 Um
 but


I
 do
 think
 like
 setting
 up
 automations


in
 order
 to
 ensure
 that
 like
 uh
 like


things
 like
 do
 not
 go
 stale
 is
 like
 a


very
 very
 important.
 Um
 and
 I'm
 curious


for
 yourself.
 So,
 now
 that
 like
 uh


agents
 are
 making
 transactions
 on
 the


internet,
 how
 does
 that
 change
 how


Coinbase
 thinks
 about
 uh
 like


the
 like


like
 just
 transactions
 in
 general?
</details>

>> [笑声]
<details><summary>Original English</summary>
>> [laughter]
</details>

### 加密货币与 Agent 支付的交汇

>> 是的，AI Agent 与作为支付轨道的稳定币的交汇几乎是同时发生的。传统上，在以往的技术时代，你会看到两个转折点结合在一起，比如智能手机与 4G LTE 同时出现。这开启了许多新机遇，但也给我们带来被新兴初创公司颠覆或去中介化的可能。所以我们主要从两个方面来思考：其一是我们能构建并推广哪些专门面向 Agent 的创新产品，为它们构建出在以往互联网时代完全不可能实现的原生体验；其二则是 Coinbase 的哪些核心业务需要让 Agent 能够访问，从而让人们在交易、资金管理等我们的核心基本用例中继续使用 Coinbase。

我看待这两件事的方式，归结于我们如何通过 API 让整个业务变得可用。也就是说，我们如何把所有提供给人类的功能，转化为一个 Agent 能够交互的世界。虽然通过操作浏览器也可以做到，但那并不是最理想的情况。尤其在涉及金融时，存在大量的身份验证和安全顾虑。你不会想给 Agent 毫无限制的账户访问权限，你希望设置合适的防护边界、限制等等。因此，为了给公司建立防守护城河并在 AI 时代生存下去，我们正在经历这种转变——就像当年从网页端转向移动端一样，现在则是从移动端转向 Agent 端。把十年前移动用户在手机上能用的一切都开放出来——那时人们还会说：“我绝不可能在手机上用网银，那听起来太疯狂了。”而现在每个人在手机上做这件事比在网页浏览器上还频繁。

我们正在做同样的事，让这一切对 Agent 可用，并加入所有必要的安全机制细节。以至于今天你可能会说：“我怎么可能把账户权限给一个 AI 去管钱？”但十年后，你甚至根本不会去看你的账户，一切都会通过你的 Agent 来完成。
<details><summary>Original English</summary>
>> Yeah,
 the
 the
 the
 intersection
 of
 AI


agents
 and
 and
 stablecoins
 as
 a
 as
 a


payment
 rail
 have
 sort
 of
 happened
 at


the
 same
 time.
 And
 traditionally,
 you


see
 two
 inflection
 points
 come
 together


in
 in
 previous
 eras
 of
 technology,
 like


for
 example,
 mobile
 phones
 at
 the
 same


time
 that
 you
 have
 4G
 LTE.
 And
 this


opens
 up
 a
 lot
 of
 new
 opportunities,
 but


it
 also
 opens
 up
 an
 opportunity
 for
 us


to
 be
 disintermediated
 or
 disrupted
 by
 a


new
 nascent
 startup
 or
 company.
 So,


there's
 there's
 really
 two
 ways
 that
 we


think
 about
 it.
 One
 is
 what
 are
 these


innovative
 products
 that
 we
 can
 build


and
 use
 uh
 and
 and
 market
 specifically


toward
 agents
 and
 build
 for
 agents
 so


that
 they
 have
 this
 experience
 that
 is


otherwise
 completely
 not
 possible
 in
 the


previous
 era
 of
 the
 internet.
 But
 then


also
 too,
 what
 are
 the
 core
 parts
 of


Coinbase's
 business
 that
 we
 need
 to
 make


accessible
 to
 agents
 such
 that
 people


continue
 using
 Coinbase
 as
 for
 our
 bread


and
 butter
 use
 case
 of
 of
 trading
 and


money
 management
 and
 whatnot.
 And
 the


way
 that
 I
 view
 those
 two
 things
 is


around
 how
 we
 make
 our
 entire
 business


accessible
 via
 APIs.
 So,
 how
 can
 we
 take


all
 of
 the
 functionality
 that's


available
 to
 humans
 and
 translate
 that


into
 a
 world
 where
 agents
 can
 interact


with
 it.
 And
 though
 that's
 possible
 with


browser
 use,
 it's
 not
 exactly
 the
 most


ideal
 situation.
 There's
 a
 lot
 of


authentication
 and
 and
 security


concerns,
 especially
 when
 you're
 dealing


with
 finances.
 You
 don't
 want
 to
 give


your
 agent
 sort
 of
 unfettered
 access
 to


your
 account.
 You
 want
 the
 right


guardrails,
 limitations,
 all
 of
 that
 in


place.
 So,
 to
 to
 to
 build
 this
 defensive


hedge
 for
 our
 company
 and
 allow
 us
 to


survive
 in
 the
 AI
 era,
 we
 are
 taking


this
 it's
 sort
 of
 an
 analog
 to
 web


shifting
 to
 mobile,
 but
 now
 mobile


shifting
 to
 agents
 and
 making
 everything


that
 was
 accessible
 for
 mobile
 users


inside
 their
 their
 phone
 back
 a
 decade


ago
 when
 people
 were
 saying,
 "I
 would


never
 bank
 on
 my
 phone.
 That
 sounds


crazy."
 Now
 everyone
 does
 it
 more
 than


they
 do
 even
 on
 their
 on
 their
 web


browser.


Doing
 that
 same
 thing,
 but
 now
 making
 it


available
 to
 agents
 adding
 in
 all
 of
 the


safety
 nuances
 that
 you
 would
 need
 such


that
 today
 you
 may
 say,
 "Why
 would
 I


ever
 give
 an
 AI
 access
 to
 my
 account
 to


manage
 money?"
 And
 10
 years
 from
 now,


you
 won't
 even
 be
 looking
 at
 your


account
 at
 all,
 just
 be
 happening


through
 your
 through
 your
 agent.
</details>

>> 我很好奇，加密货币作为这套方案有什么特别的优势吗？
<details><summary>Original English</summary>
>> I'm
 curious,
 is
 there


like
 specific
 advantages
 of
 crypto
 being


the
 solution
 for
 this?
</details>

>> 我认为在支付层面绝对有。我们在 X402 的早期势头中看到了很多体现，那是我们的互联网原生支付标准，现在我们已经将其独立出来，设立了单独的基金会，由 Cloudflare、Stripe、Amex、Mastercard、Visa 等共同运营和治理。加密货币的切入点，我认为主要在于数字美元可以在全球范围内廉价、快速、无需许可地转移。任何经营业务并希望自己的 AI Agent 接收交易的人都可以做到这一点。尽管我们在现有的基于银行卡或 Stripe 链接这类解决方案中见过很多应用，但我认为加密货币尤为适合发挥作用的领域之一是微支付，即让 Agent 能够无缝且轻松地花费千分之一美分、甚至百万分之一美分去访问一个 API、一项服务甚至一个有付费墙的网站。
<details><summary>Original English</summary>
>> I
 think
 on
 the
 payment
 side,
 absolutely.


So,
 a
 lot
 of
 what
 we've
 seen
 with
 early


traction
 around
 X402,
 which
 is
 our


internet
 native
 payment
 standard
 that
 we


have
 now
 externalized
 into
 its
 own


separate
 foundation.
 That's
 that's


co-run
 and
 governed
 by
 Cloudflare,


Stripe,
 Amex,
 Mastercard,
 Visa,
 and
 so


on.
 The
 the
 crypto
 angle,
 I
 think
 is


primarily
 around
 the
 ability
 for
 digital


dollars
 to
 be
 sent
 uh
 cheap,
 fast,


permissionlessly
 anywhere
 in
 the
 world.


So,
 anyone
 who's
 running
 a
 business
 and


wants
 their
 AI
 agent
 to
 accept
 a


transaction
 can
 do
 so.
 And
 though
 we've


seen
 this
 a
 lot
 with
 existing
 sort
 of


card-based
 or
 stripe
 link
 style


solutions,
 one
 of
 the
 areas
 where
 I


think
 crypto
 has
 a
 particular
 role
 to


play
 is
 around
 micro
 transactions
 and


the
 ability
 for
 an
 agent
 to
 spend
 1/1000


of
 a
 cent,
 even
 1/1000000
 of
 a
 cent,
 to


access
 an
 API
 or
 a
 service
 or
 even
 a


paywalled
 website
 very,
 very
 seamlessly


and
 and
 trivially.
</details>

>> 我很好奇，那个未来已经到来了吗？我们现在已经看到 Agent 通过加密货币进行交易了吗？
<details><summary>Original English</summary>
>> And
 I'm
 curious,
 is
 that
 future
 already


here?
 Like
 are
 we
 already
 seeing
 agents


making
 transactions
 via
 crypto?
 Like
</details>

>> 是的，绝对如此。我们看到交易量正在呈指数级增长。过去一年中，我们实际上看到了大约 1 亿笔 Agent 交易，全部发生在链上，所有人都可以公开审计。

所有这些交易主要都针对与 API 交互这一用例。在之前的世界版本中，你必须访问你想使用的服务网站，给该账户充值，获取 API 密钥，然后将其交给你的 Agent。只有这样你才能真正开始与事物交互。但现在我们看到的世界是，只要你给 Agent 一个钱包或某种金融账户，它就可以自己去为不同的 API 进行单次按需付费。对于 Agent 支付的早期采用者这个核心群体来说，这是一个非常有吸引力的用例。
<details><summary>Original English</summary>
>> Yeah,
 absolutely.
 We're
 we're
 seeing
 a


pretty


pretty


exponential
 increase
 in
 the
 amount
 of


transactions
 that
 are
 being
 made.
 In
 the


past
 year,
 we've
 seen
 around
 100
 million


agentic
 transactions
 actually,
 all


happening
 on
 chain,
 all
 publicly


available
 for
 anyone
 to
 audit.


Uh
 all
 of
 those
 are
 are
 primarily
 for


this
 use
 case
 of
 of
 interacting
 with


APIs.
 So
 in
 this
 previous
 version
 of
 the


world,
 you
 would
 have
 to
 go
 to
 whatever


website
 you
 wanted
 to
 interact
 with
 the


service,
 you'd
 have
 to
 fund
 that


account,
 you'd
 have
 to
 get
 an
 API
 key,


and
 then
 hand
 that
 to
 your
 agent.
 Only


then
 you
 can
 really
 start
 to
 interact


with
 things.
 But
 now
 we're
 seeing
 a


world
 where
 if
 you
 just
 give
 an
 agent
 a


wallet
 or
 some
 sort
 of
 financial


account,
 it
 can
 go
 off
 and
 pay
 in
 a


one-off
 basis
 for
 different
 APIs.
 And


that's
 been
 a
 really
 resonant
 use
 case


with
 with
 this
 core
 audience
 of
 of
 early


adopters
 of
 agentic
 payments.
</details>

>> 所以你指的是人们通过 API 连接到你的钱包，或者是 Agent 自己去购买 API 吗？
<details><summary>Original English</summary>
>> So
 you're
 talking
 about
 like
 basically


people
 connecting
 to
 your
 wallet
 via
 API


or
 like
 the
 agent
 purchasing
 APIs
 or
</details>

>> 是的，就像是 Agent 购买 API。
<details><summary>Original English</summary>
>> Yeah,
 it's
 like
 the
 agent
 purchasing


APIs.
 So
</details>

>> 哦，明白了。
<details><summary>Original English</summary>
>> Oh, okay.
</details>

### API 优先与 Agent 财务自主权

>> 我喜欢用的类比是，当前互联网的运作方式就好比每次你去杂货店，都必须走进去，买一张该杂货店专用的礼品卡，注册他们的会员账户，然后才能开始买东西。这就是你每次访问网站时的感受：必须获取 API 密钥，必须专门给该账户充值，然后你的 Agent 才能开始交互。但随着我们赋予这些 Agent 更多的财务独立性和自主权，它们无需经过这种繁琐的人工阻塞流程就能做事情。就像我如果不能使用资金，在互联网上能做的事情也非常有限一样，Agent 很大程度上也是如此。赋予它们获取资金的途径，就是提升它们自主权的方式，并最终达到这样的程度：如果你告诉你的云端 Agent“我想生成一张图片”，即使它目前没有该服务的连接，它也应该能做到；它只需自己为那项服务付费，付上 25 美分或者不管多少费用就行。
<details><summary>Original English</summary>
>> The
 the
 analogy
 I
 like
 to
 use
 is
 it'd
 be


like
 if
 every
 the
 the
 current
 way
 the


internet
 works
 is
 every
 time
 you
 uh


it'd
 be
 like
 if
 every
 time
 you
 went
 to
 a


grocery
 store,
 you
 had
 to
 walk
 in,
 you


had
 to
 buy
 a
 gift
 card
 for
 that
 specific


grocery
 store,
 you
 had
 to
 sign
 up
 for


their
 loyalty
 account,
 and
 only
 then
 you


can
 start
 paying
 for
 stuff.
 And
 that's


how
 it
 feels
 whenever
 you
 go
 to
 a


website,
 you
 have
 to
 get
 API
 keys,
 you


have
 to
 fund
 that
 account
 specifically,


and
 only
 then
 your
 agent
 can
 start


interacting.
 But
 as
 we
 give
 these
 agents


more
 financial
 independence
 and


autonomy,
 they're
 able
 to
 do
 things


without
 having
 to
 go
 through
 this


arduous
 human
 blocking
 process.
 And
 in


the
 same
 way
 that
 I
 can
 only
 do
 so
 much


on
 the
 internet
 without
 having
 access
 to


money,
 agents
 are
 very
 much
 the
 same


way.
 Giving
 them
 access
 to
 money
 is
 how


you
 increase
 their
 autonomy
 and


ultimately
 get
 to
 the
 point
 where
 they


can
 go
 do
 things
 if
 you
 just
 tell
 your


cloud
 agent,
 I
 want
 to
 go
 generate
 an


image,
 it
 should
 be
 able
 to
 do
 that
 even


if
 it
 doesn't
 have
 a
 connection
 to
 that


today.
 It
 should
 just
 pay
 for
 that


service,
 pay
 the
 25
 cents
 or
 whatever
 it


might
 be.
</details>

>> 所以可以说 Coinbase 正在全面押注 API，让它对 Agent 更友好？
<details><summary>Original English</summary>
>> So,
 Coinbase
 is
 like
 doubling
 down
 on


APIs
 in
 general,
 would
 you
 say,
 to
 make


it
 more
 agent
 friendly?
</details>

>> 是的，绝对如此。我认为 API 是核心关键。你可以把它封装在一个 MCP 里，这非常好也很棒；如果未来某个时候有所改变，我们走着瞧，但真正核心的还是 API 以及对你底层服务的访问能力，以一种安全、友好、直观的方式让人们更容易获取。
<details><summary>Original English</summary>
>> Yeah,
 absolutely.
 I
 think
 APIs
 are
 the


name
 of
 the
 game.
 You
 can
 wrap
 that
 in


an
 MCP
 and
 that's
 all
 fine
 and
 dandy
 if


that
 changes
 at
 some
 point
 in
 the


future.
 We'll
 see,
 but
 uh
 it's
 it's


really
 the
 the
 the
 APIs
 and
 that


underlying


uh


access
 to
 your
 service
 in
 a
 way
 that


gives
 makes
 it
 so
 much
 more
 accessible


to
 people
 in
 like
 a
 safe,
 friendly,


intuitive
 manner.
</details>

>> 我正想问你对于 MCP、CLI 和 API 的看法。
<details><summary>Original English</summary>
>> I
 was
 going
 to
 ask
 if
 you
 have
 any
 takes


on
 like
 MCP
 versus
 CLI
 versus
 API.
</details>

>> 是的，我认为 API 永远是这一切底部的基础层。MCP 非常适合在自然语言风格的环境中添加所需的额外上下文和细节；CLI 大体上也类似，只是多了需要关联终端的要求。但在它们之间，我认为你全部都需要具备。随着 AI 辅助开发变得如此简单，感觉上你基本上只是以 Agent 能够使用的任何形式或结构将它们包装起来。除此之外，它们各自都有优缺点，但我认为对于这些工具如何演进以及它们将走向何方，我们距离最终形态还很远。
<details><summary>Original English</summary>
>> Yeah,
 I
 just
 uh
 I
 think
 API's
 always


going
 to
 be
 that
 fundamental
 layer


underneath
 it
 all
 and
 then
 the
 MCP
 is


nice
 for
 adding
 additional
 context
 and


nuance
 that
 required
 within
 like
 a


natural
 language
 style
 setting
 and
 and


CLI
 is
 is
 broadly
 the
 same
 with
 the


additional
 requirement
 of
 having
 like
 a


terminal
 associated
 with
 it,
 but
 between


all
 of
 them,
 I
 think
 it's
 kind
 of
 like
 a


you
 have
 to
 have
 all
 of
 them
 and
 it's


how
 easy
 AI
 assisted
 development
 has


gotten.
 It
 kind
 of
 feels
 like
 you're


just
 fundamentally
 wrapping
 them
 in
 in


whatever
 way,
 shape,
 or
 form
 that
 the


agent
 can
 can
 use.
 And
 beyond
 that,


there's,
 you
 know,
 pros
 and
 cons
 to
 each


of
 them
 individually,
 but
 I
 think
 we're


we're
 far
 from
 the
 end
 game
 of
 how
 these


tools
 evolve
 and
 and
 where
 they
 start


going.
</details>

>> 是的，这就引出了我的下一个问题：你认为世界将会走向何方？
<details><summary>Original English</summary>
>> Yeah,
 that
 leads
 to
 my
 next
 question.


Like,
 where
 do
 you
 think
 the
 world
 is


going
 to
 be
 headed
 towards?
</details>

>> 嗯，嗯。
<details><summary>Original English</summary>
>> Mhm.
 Mhm.
</details>

>> [清嗓子]
<details><summary>Original English</summary>
>> [clears throat]
</details>

>> 特别是在 Agent 支付方面，我的核心基本信念是：通过赋予 Agent 资金获取渠道并授权它们支出，从而给予它们更多的财务独立性，这就是我们提升自主权水平、打造能运行更长时间的 Agent 的方式，而这最终会带来更好的成果。如果我能让我的 Agent 有能力去购买以往无法获取的付费墙网站信息，那就能让它通宵运行，进行比我仅给它公开互联网访问权限更深入的研究。同样，在未来的世界中，假设我想让我的 Agent 替我设立一家公司并成立一家有限责任公司（LLC），也许它无法完全独立完成，但也许它可以去类似 Fiverr 的平台上雇佣一名律师，或者使用“租用人类”等各种服务，并聘请一名会计师来处理这项工作。加密货币领域有一个非常有趣的概念叫做 DAO，即去中心化自治组织。这已经存在好几年了，但它实际上的体现形式基本上只是另一种官僚机构——少数几个人试图做决策，而且往往会土崩瓦解，从未真正实现完整的愿景。其最初的愿景是核心高度自动化，边缘由人类参与，以此方式运营一个组织。我认为拥有资金使用权限的 Agent，正是我们将看到该愿景最终成真的一个非常清晰的范例。
<details><summary>Original English</summary>
>> I
 On
 the
 agentic
 payment
 side


particularly,
 my
 my
 sort
 of
 core


fundamental
 belief
 is
 that
 granting


agents
 more
 financial
 independence
 by


giving
 them
 access
 to
 money
 and
 and


authorizing
 them
 to
 spend
 that
 is
 how
 we


create
 increasing
 levels
 of
 autonomy
 and


long-running
 agents
 that
 just
 lead


ultimately
 to
 better
 outcomes.
 If
 I
 can


get
 my
 agent
 uh
 the
 ability
 to
 go
 pay


for
 information
 on
 paywalled
 sites
 that


otherwise
 wouldn't
 previously
 be


available,
 that
 would
 allow
 it
 to
 run


overnight
 and
 do
 even
 deeper
 research


settings
 that
 I
 could
 do
 if
 I
 just
 gave


it
 access
 to
 the
 public
 open
 internet.


Similarly,
 if
 I
 allow
 my
 agent
 to
 in
 a


in
 a
 future
 version
 of
 the
 world,
 say
 I


want
 my
 agent
 to
 go
 set
 up
 a
 company
 for


me
 and
 form
 an
 LLC.
 Maybe
 it
 can't
 do


that
 entirely
 on
 its
 own,
 but
 maybe
 it


can
 go
 hire
 a
 lawyer
 off
 of
 a
 you
 know
 a


Fiverr
 equivalent
 or
 or
 rent
 a
 human
 or


any
 one
 of
 these
 services
 and
 and
 an


accountant
 to
 handle
 this
 work.
 It


there's
 a
 really
 interesting
 concept


from
 the
 crypto
 space.
 It's
 called
 a
 DAO


like
 a
 DAO.
 It's
 a
 decentralized


autonomous
 organization.
 And
 this
 has


been
 around
 for
 for
 several
 years
 now,


but
 it's
 really
 manifested
 itself
 as


basically
 just


another
 form
 of
 bureaucracy
 where


there's
 a
 handful
 of
 people
 trying
 to


make
 decisions
 and
 it
 just
 it
 just


always
 kind
 of
 crumbled.
 It
 never
 really


achieved
 that
 whole
 vision.
 And
 the


original
 vision
 was
 automation
 at
 the


core
 and
 humans
 at
 the
 edges
 and
 you
 run


an
 organization
 that
 way.
 And
 I
 think


agents
 with
 access
 to
 money
 are
 a
 very


clear
 example
 of
 how
 we're
 going
 to
 see


that
 vision
 finally
 come
 to
 life.
</details>

>> 我由衷带着好奇问这些问题，因为我个人不太懂加密货币，看到以前建立的很多设想随着 AI 的介入而逐步成为现实，这非常有趣。
<details><summary>Original English</summary>
>> I
 genuinely
 ask
 these
 questions
 with


curiosity
 cuz
 I
 personally
 do
 not
 know


crypto
 very
 well
 and
 it's
 very


interesting
 to
 see
 how
 like
 I
 guess
 like


a
 lot
 of
 these
 theses
 that
 were
 like


kind
 of
 built
 previously
 are
 kind
 of


coming
 into
 fruition
 with
 AI
 in
 play.
</details>

>> 是的，看到这一点真的很有趣。在很多层面上这都得到了印证，比如你根本不能直接把银行账户权限给 AI。加密钱包是一种向其可证明地提供访问权和资金所有权的良好方式。不过，我也很想听听你的视角和设想：随着 Agent 成为文档的主要采用者和摄取者，世界会如何演变，这又如何改变了 Mintlify 的战略？
<details><summary>Original English</summary>
>> Yeah,
 it's
 been
 really
 fun
 to
 see.
 It's


very
 validated
 in
 a
 lot
 of
 senses
 where


it's
 like
 you
 simply
 can't
 just
 give
 an


AI
 access
 to
 a
 bank
 account.
 A
 crypto


wallet
 is
 a
 nice
 way
 to
 provably
 give
 it


access
 and
 and
 ownership
 over
 over


money,
 but
 I
 would
 love
 to
 hear
 your


your
 perspective
 and
 vision
 on
 how
 the


world
 evolves
 as
 well
 as
 as
 agents


becoming
 the
 primary
 adopters
 and


ingesters
 of
 of


documentation
 and
 how
 that
 changes
 your


strategy
 at
 Menthafy.
</details>

### 文档消费者的结构性逆转：从人类到 Agent

>> 是的，我很喜欢你对 API 的强调，因为我也是这么认为的。感觉很多软件公司都在变得更加以开发者为中心。我们确实设想了一个所有人都在使用这种技术的未来，但现在最早的采用者是开发者，而且 Agent 说的其实就是开发者的语言，因为这一切都体现在代码中，对吧？它们非常擅长 Bash，非常擅长 CLI 命令。所以至少在目前，我绝对认为应该这么做，所有软件公司都应该认真投资于 API 以及这些老实说看起来稍微有点传统的事物。

而且我认为，你说的也印证了前端变得没那么重要的事实。通过创建 API，从本质上让所有东西都可被 Agent 访问。

我想分享一个有趣的数据：今年年初，在所有 Mintlify 站点中，大约有 10% 的浏览量来自 Agent，而现在这一比例接近 80%。这挺有意思的，我们公司内部有一个追踪看板，专门追踪这个百分比；我们在内部还会打赌它会涨到多少，而它的增长速度甚至超出了我们的预期。这并不是说人类的浏览量在下降，而是 Agent 的浏览量增长得实在太快了。我总是觉得很奇妙，因为 Agent 在很多方面的行为与人类有些相似，但在许多方面又大相径庭。我喜欢用 Agent 的术语来描述人类——比如与 Agent 相比，我们人类的上下文窗口非常小；而 Agent 有多得多的时间去摄取海量内容并能很好地理解。我认为这正是我们所有人目前看到的、关于 Agent 如何影响业务和我们工作方式的巨大浪潮的核心所在。

这真的很不可思议，过去一年的增长简直不可思议。OpenClaw[注：ASR 原词 open claw] 实际上就是今年出现的，现在感觉却像是很久以前的事了。
<details><summary>Original English</summary>
>> Yeah,
 I
 love
 how
 much
 of
 an
 emphasis
 you


had
 on
 APIs
 cuz
 that's
 also
 my
 take.


Like
 it's
 it
 feels
 like
 a
 lot
 of


software
 companies
 are
 kind
 of
 becoming


more
 developer-centric.
 And
 you
 know,
 we


do
 envision
 a
 world
 where
 everybody
 is


using
 like
 this
 technology,
 but
 right


now
 like
 the
 earliest
 adopters
 are


developers
 and
 also
 the
 agents
 actually


speak
 like
 the
 language
 of
 developers


because


like
 it's
 all
 in
 code,
 right?
 And
 like


they
 they're
 really
 good
 at
 bash.


They're
 really
 good
 at
 CLI
 commands.
 And


so
 definitely
 think
 at
 least
 like
 for


now
 like
 doing
 that
 and
 all
 like


software
 companies
 should
 be
 really


investing
 in
 APIs
 and


uh
 these
 things
 that
 like
 seem
 a
 little


bit
 traditional
 honestly.


Um
 and
 also
 I
 I
 think
 like
 what
 you
 said


also
 reinforces
 the
 fact
 that
 the
 like


front
 end
 is
 not
 mattering
 as
 much


either.
 Like


make
 make
 everything
 avail-
 accessible


to
 agents
 by
 like


by
 creating
 APIs
 essentially.


Um
 one
 interesting
 statistic
 that
 I
 want


to
 share
 is
 that
 at
 the
 beginning
 of
 the


year
 across
 all
 Netlify
 sites,
 we
 had


around
 like
 10%
 of
 like
 the
 viewership


was
 agents
 and
 now
 uh
 we're
 closer
 to


like
 80%.
 Um
 and
 it's
 kind
 of
 funny
 we


have
 like
 this
 internal
 tracker
 at
 our


company
 where
 we
 uh
 we
 just
 track
 like


how
 what
 what
 the
 percentage
 is
 and


we're
 like
 we
 internally
 like
 take
 bets


on
 like
 where
 we
 think
 it's
 going
 to
 go


and
 it's
 been
 growing
 faster
 than
 we


even
 think.
 And
 it's
 not
 like
 human


viewership
 is
 going
 down,
 but
 I
 think


that
 like
 the
 agent
 viewership
 is
 just


going
 so
 much
 higher.
 Um
 I
 always
 like


to
 like
 it's
 it's
 weird
 because
 like


agents
 act
 kind
 of
 similarly
 to
 humans


and
 uh
 and
 different
 in
 in
 many


different
 ways,
 but
 like
 I
 like
 kind
 of


using
 like
 the
 agent
 terms
 on
 humans
 in


the
 sense
 that
 like
 we
 as
 humans
 have


very
 small
 context
 windows
 in
 comparison


to
 the
 agents
 like
 and
 they
 have
 much


more
 like
 you
 know,
 time
 to
 just
 like


like
 ingest
 so
 much
 more
 content
 and
 be


able
 to
 grok
 that
 well
 and
 I
 think


that's
 like
 really
 the
 the
 crux
 of
 like


the
 big
 surge
 that
 we're
 all
 just
 like


seeing
 right
 now
 with
 like
 how
 agents


are
 impacting
 businesses
 and
 like
 how
 we


work.
 Um


it's
 it's
 it's
 insane
 like
 the
 like
 the


the
 growth
 like
 over
 the
 past
 years
 is


insane.
 Uh
 like
 uh
 open
 claw
 like
 was


literally
 like
 this
 year
 and
 that's
 that


also
 kind
 of
 feels
 like
 forever
 ago.
</details>

### 人工撰写与技术写作自动化的边界

>> 这太引人入胜了。我想深入探讨一下你提到的关于企业投资传统事物这一点，以及你之前提到的人类撰写文档与 AI 撰写文档的对比。我非常想多了解一些你对此的看法：我们是否始终需要这种人工参与来撰写文档，或者提供细微的语境供 Agent 去吸收？还是说未来会有这样一个世界——对团队而言这开始变成一个更自动化的流程？目前团队又是如何与这种模式互动的？
<details><summary>Original English</summary>
>> That
 that's
 fascinating.
 I
 want
 to
 drill


in
 on
 something
 you
 said
 about
 uh


companies
 investing
 in
 like
 the


traditional
 things
 and
 also
 what
 you


made
 previously
 around
 humans
 writing


documentation
 as
 opposed
 to
 AI.
 I'm


really
 curious
 to
 learn
 a
 little
 bit


more
 about
 your
 perspective
 on
 that
 and


if
 we'll
 always
 sort
 of
 need
 this
 human


touch
 to
 to
 write
 documentation
 or
 or
 or


provide
 a
 nuance
 that
 then
 an
 agent
 can


go
 ingest
 or
 if
 there's
 a
 world
 where


this
 starts
 to
 become
 a
 a
 more
 automated


process
 for
 teams
 and
 how
 teams
 are


interacting
 with
 this
 uh
 this
 uh
 pattern


today.
</details>

>> 是的，我花了很多时间思考人工写作与 AI 生成写作的对比，以及我在这当中的立场。我确实认为，对于创意散文或叙事性写作，拥有人工参与是非常重要的。我不知道台下各位在网上有多重度活跃，但我自己是非常深度的网民。网上有很多讨论，比如软件工程师全用 AI 来写所有代码，但写文章时却极其虔诚地坚持纯手写。比如当你给团队内的其他人提供一份文档时，你会决定用 AI 生成还是决定自己亲自写？现在开始出现文档等级的划分和分化。所以我确实觉得，自己总是在走向传统还是走向“一切都在改变、我们需要改变思维方式”的新范式之间徘徊。我认为大家都是边走边摸索。老实说，我确实曾经有过一段时间陷入轻微的“AI 精神病态”，觉得“哦，我不需要和任何人交谈，我只要和我的 MCP 对话就能获得所有洞察和一切”。但作为产品人员，我也很好奇你的想法——尽管发生着这么多技术创新，与人沟通并找出当今真正的痛点和用例依然很重要。

不过回到你的问题，我认为特别是对于技术写作，存在一个收集信息并将其沉淀的过程，而我认为技术写作的这一部分是可以自动化的。比如，去找出所有相关的 PR、找出所有相关的上下文背景、梳理 Slack 内部发生的所有事情、所有制定的决策，然后将这些凝练成简洁的内容，再确定在庞大的内容库中应该将其注入到哪里——我认为所有这些都可以实现自动化。
<details><summary>Original English</summary>
>> Yeah,
 I
 spend
 a
 lot
 of
 time
 thinking


about
 like
 human
 writing
 versus
 like


AI-generated
 writing
 and
 where
 my
 takes


fall
 in
 that.
 And
 I
 do
 think
 that
 for


creative
 prose
 or
 narrative
 writing,


uh
 it's
 very
 important
 to
 have
 that


human
 touch.
 And
 I
 don't
 know
 how


terminally
 online
 this
 room
 is,
 but
 I
 am


quite
 terminally
 online.
 And
 there
 is
 so


much
 conversation
 about
 uh
 you
 know,


like
 uh
 software
 engineers
 like
 using
 uh


coding
 for
 writing
 all
 their
 code,
 but


then
 religiously
 like
 writing
 like
 uh


prose
 by
 hand.
 Like,
 you
 know,
 when


you're
 like
 giving
 a
 document
 to


somebody
 else
 within
 the
 team,
 like
 do


you
 decide
 to
 AI-generate
 it
 or
 do
 you


decide
 to
 write
 it
 yourself?
 There's


starting
 to
 become
 like
 a
 class
 of


documents
 and
 like
 division
 happening


now.
 And
 so,
 I
 definitely
 think
 like


um
 it's


I
 like


I
 always
 kind
 of
 like
 uh
 teeter
 around


like,
 you
 know,
 going
 towards
 tradition


versus
 like
 going
 towards
 like
 a
 new


paradigm
 of
 like
 everything
 is
 changing


and
 we
 need
 to
 change
 the
 way
 that
 we


think.
 And
 I
 think
 that
 it's
 we're
 all


figuring
 it
 out
 as
 we
 go.
 I
 I
 I'm
 not


going
 to
 lie,
 I
 do
 think
 I
 had
 a
 point


in
 time
 where
 I
 was
 like
 feeling
 a


little
 AI
 psychosis,
 where
 I
'm
 like,
 oh,


like,
 I
 don't
 need
 to
 talk
 to
 anyone.


Like,
 I'll
 just
 talk
 to
 my
 MCPs
 and
 I'll


be
 able
 to
 get
 all
 the
 insights
 and


everything.
 I
 definitely
 think,


especially
 as
 a
 product
 person,
 I'm
 also


curious
 to
 hear
 your
 thoughts
 on
 that.


Like,
 it's
 still
 important
 to
 talk
 to


people
 and
 figure
 out
 like
 what
 what


what
 the
 real
 pain
 points
 and
 use
 cases


are
 today
 uh
 in
 spite
 of
 all
 the


innovations
 that
 are
 changing.


Um
 but
 uh


yeah,
 to
 to
 kind
 of
 go
 back
 to
 your


question,


um
 like


I
 think
 for
 technical
 writing


particularly,
 like
 there
 is
 like
 a


process
 of
 gathering
 the
 insights
 and


then
 like
 putting
 it
 in,
 in
 which
 I
 do


think
 like
 the
 technical
 writing
 like


portion
 of
 it
 can
 be
 automated.
 Like,
 I


think
 it's
 very
 tedious
 to
 find
 all
 the


related
 PRs,
 find
 all
 the
 related


context,
 all
 everything
 that
's
 happening


within
 Slack,
 all
 the
 decisions
 being


made,
 and
 then
 like
 put
 that
 into


something
 succinct,
 and
 then
 figure
 out


like
 where
 uh
 and
 like
 amidst
 your


corpus
 of
 like
 content
 like
 you
 need
 to


like
 inject
 it
 in.
 I
 think
 like
 all
 of


that
 can
 be
 automated.
</details>

### 自建与采购的权衡及常见陷阱

>> 很有意思。从产品角度来看，正如你所指出的，我也注意到仅仅通过与 Agent 交互是很难获得任何洞察或收获的。如果说有什么不同的话，它往往只会产生幻觉，并让你优先考虑错误的事情。

如果我没算错时间的话，我们可能还有时间回答最后一个问题。我非常想听听你的看法：在为 AI 构建能力以及为 AI 构建文档的团队中，你见过的最常见陷阱是什么？这又如何影响了他们试图推动 AI 去做的事情？你有什么建议能让整个流程变得更加顺畅？
<details><summary>Original English</summary>
>> Interesting.
 Yeah,
 I
 I
 I've
 noticed
 from


the
 product
 perspective
 to
 your
 point


that
 it's
 it's
 very
 difficult
 to
 find


any
 sort
 of
 insights
 or
 takeaways
 from


just
 interacting
 with
 an
 agent.
 And
 if


anything
 it
 just
 hallucinates
 and
 make


you
 prioritize
 the
 wrong
 wrong
 things.


Um
 if
 my


reckoning
 of
 time
 is
 right
 we
 probably


have
 time
 for
 one
 more
 question.
 So
 I'd


be
 I'd
 be
 very
 curious
 to
 hear
 from
 you


what
 is
 the
 most
 common
 fit
 fitfall
 you


see
 teams
 who
 are
 building
 for
 AI
 and


building
 documentation
 for
 AI
 uh
 fall


into
 and
 and
 and
 how
 that
 sort
 of


impacts
 what
 they're
 attempting
 to
 drive


the
 AI
 to
 do
 and
 what
 you
 would


recommend
 to
 to
 make
 this
 whole
 process


much
 more
 seamless.
</details>

>> 嗯，好的。这听起来可能有点像在给我自己打广告，但我确实认为这是经典的“自建还是采购”（build versus buy）问题。我认为这是每个人在面对软件产品时不断在问的问题。当你决定要做什么时，无论是文档还是公司内部用于提高生产力或非主营业务的其他 SaaS，你面临的选择要么是自己去维护它，要么是将其外包给另一个把醒着的每一小时都花在思考这件事上的团队。

在 AI 时代，竞争变得越来越激烈，节奏也越来越快，我认为每家公司都应该专注于自己的头号核心价值主张，而人们太容易忽视事物的维护成本了。我认为我们在企业销售中也经常看到这种情况，比如大家会说：“嘿，各位，这是我们在黑客马拉松期间做出来的，但没人愿意去维护它。”如果我们的业务是去做你们正在做的事，那我们就是在做你们的公司业务了，对吧？所以要切实牢记这一点——其实一直以来都是如此，只是 AI 让这一点更加突显了：“我们可以构建它，但我们愿意去维护它吗？”我们在打造产品时也会问自己这个问题，因为我们完全有可能把所有东西都做一遍。
<details><summary>Original English</summary>
>> Mm
 yeah.


Okay,
 this
 is
 going
 to
 sound
 like
 a
 a
 my


own
 plug,
 but
 I
 do
 think
 that
 uh
 like


it's
 the
 whole
 like
 build
 versus
 buy.
 I


think
 is
 like
 the
 question
 that
 everyone


is
 constantly
 asking
 for
 software


products.
 And
 I
 do
 think
 that
 you
 know,


when
 you're
 deciding
 what
 to
 do
 whether


it's
 documentation
 or
 any
 other
 SAS
 that


you
 have
 within
 your
 company
 to
 like


improve
 your
 productivity
 or
 like
 not


your
 main
 thing,
 I
 do
 think
 that
 there


is
 like
 it's
 you're
 either
 deciding
 to


maintain
 something
 yourself
 or
 uh
 like


offload
 that
 to
 another
 team
 that's


literally
 spending
 like
 every
 waking


hour
 thinking
 about
 it.
 Um
 and
 so
 I
 do


think
 like
 things
 are
 getting
 more


competitive
 with
 AI,
 things
 are
 moving


faster
 with
 AI
 and
 I
 think
 like
 every


company
 should
 be
 focused
 on
 whatever


their
 number
 one
 value
 proposition
 is


and
 it's
 so
 easy
 to
 kind
 of
 forget
 about


uh
 the
 maintenance
 costs
 of
 things,
 you


know?
 I
 think
 that's
 like
 what
 we're


kind
 of
 seeing
 a
 lot
 in
 enterprise
 sales


as
 well
 where
 it's
 like
 "Hey
 guys,
 we


built
 this
 during
 a
 hackathon
 and
 nobody


wants
 to
 maintain
 it."
 Like
 what
 like


like
 if
 we
 were
 in
 the
 business
 of
 doing


what
 you
 guys
 are
 doing,
 we
 would
 be


building
 your
 business,
 you
 know?
 Um
 and


so
 I
 think
 that
 like
 uh
 really


remembering
 and
 I
 think
 this
 has
 always


been
 the
 case.
 I
 think
 just
 AI
 like


accentuates
 this
 a
 lot
 more.
 It's
 like


"Hey,
 we
 could
 build
 it,
 but
 like
 do
 we


want
 to
 maintain
 it?"
 Um
 and
 I
 think


that
 uh
 this
 is
 a
 question
 that
 we
 also


ask
 ourselves
 when
 building
 products.


Cuz
 we
 could
 be
 building
 everything.
</details>

>> 是的，非常有道理。特别是考虑到 Agent 领域发展如此之快，以及它们抓取网站等行为的方式。感觉目前有上百万种不同的标准。因此，既能时刻掌握最前沿的行业现状，又能把这些问题处理好而无需自己承担维护工作——我在黑客马拉松项目等场景中亲身体会过这种情况。所以是的，完全赞同。
<details><summary>Original English</summary>
>> Yeah,
 that
 that
 makes
 a
 lot
 of
 sense.


And
 especially
 with
 how
 fast-moving
 the


agent
 space
 is
 and
 and
 and
 the
 way
 and


manner
 in
 which
 they
 crawl
 sites
 and


whatnot.
 It
 feels
 like
 there's
 a
 million


different
 standards
 and
 whatnot.
 So,


having
 just
 like
 a


constant
 view
 on
 what
 the
 state
 of
 the


art
 is
 and
 having
 that
 handled
 without


having
 to
 do
 the
 maintenance.
 I've
 seen


that
 firsthand
 with
 hackathon
 projects


and
 whatnot.
 So,
 yeah,
 couldn't
 agree


more.
</details>

>> 太棒了。非常感谢你的时间，Lincoln。
<details><summary>Original English</summary>
>> Awesome.
 Thanks
 so
 much
 for
 your
 time,


Lincoln.
</details>

>> 好的，非常感谢大家坐在这里听我们分享。谢谢大家。
<details><summary>Original English</summary>
>> Yeah,
 absolutely.
 Appreciate
 everyone
 uh


sitting
 through
 this.
 Thank
 you.
</details>