---
author: Latent Space
date: '2026-10-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=v-d1WTqIULs
speaker: Latent Space
tags:
  - financial-services
  - enterprise-ai
  - model-evaluation
  - rlhf
title: OpenAI 金融服务负责人 Joseph Kim 访谈：打造 ChatGPT 金融产品与模型品味训练
summary: OpenAI 金融服务负责人 Joseph Kim 探讨了 ChatGPT for Financial Services 的构建逻辑、捆绑企业数据的原因、基于插件架构的开发，以及通过人类偏好与强化学习训练模型审美与判断力的未来路径。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Joseph Kim
companies_orgs:
  - OpenAI
  - Morgan Stanley
  - Evercore
products_models:
  - ChatGPT
  - Codex
  - GPT-6 Astra
media_books: []
status: evergreen
---
>> 我真的认为，基于 ChatGPT 插件将会诞生价值十亿美元的业务。但我们所构建的内容中，有 95% 是初创公司或其他公司完全也能做出来的。
<details><summary>Original English</summary>
>> I
 I
 really
 do
 think
 that
 there's
 going


to
 be
 a
 billion
 dollar
 business
 built
 on


top
 of
 a


chat
 GPT
 plugin.
 But
 95%


of
 what
 we
 built
 was
 something
 that


absolutely
 a
 startup
 could
 do,
 another


company
 could
 do.
</details>

>> 在 OpenAI，我们之前在预训练方面遇到了问题，因此在扩展模型时遇到了困难。在 2026 年，我们已经能够解决其中的许多问题。
<details><summary>Original English</summary>
>> At
 OpenAI,
 we
 ran
 into
 problems
 with


pre-training
 and
 therefore
 had


difficulty
 scaling
 the
 model.
 In
 2026,


we've
 been
 able
 to
 solve
 many
 of
 these


issues.
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

### ChatGPT 金融服务的发布与未来展望

>> 今天我们邀请到了来自 OpenAI 的 ChatGPT 金融业务负责人之一 Joseph Kim，以及我们在演播室的联合主持人兼 Latent Space 编辑负责人 Richard。这是一个特别的节目。我们在纽约的 AI Finance 现场。Joseph 刚刚发表了一场精彩的主题演讲。我想我们不必重复大部分信息，所以大家坦白说可以直接去看演讲，不过还是请你用大约 30 秒概括一下你谈论的内容，留下一些线索，大家可以去看完整的主题演讲。
<details><summary>Original English</summary>
>> Today
 we
 have
 Joseph
 Kim,
 one
 of
 the


heads
 of
 chat
 GPT
 finance
 from
 OpenAI,


and
 our
 co-host
 and
 head
 of
 editorial


from
 Latent
 Space,
 Richard,
 in
 the


studio.
 It's
 a
 special
 episode.
 We're


here
 in
 New
 York
 at
 AI
 Finance.


Joseph
 just
 gave
 a
 great
 keynote.


I
 think
 we
 don't
 want
 to
 repeat
 most
 of


the
 information,
 so
 honestly
 go
 watch


it,
 but
 give
 give
 like
 a
 30-second
 of


what
 you
 talk
 about
 and
 then
 we'll
 leave


the
 breadcrumbs.
 You
 guys
 can
 go
 watch


the
 keynote.
</details>

>> 好的，没问题，我可以快速做个 30 秒的介绍，概括一下我们刚才聊的内容。

第一，我们刚刚发布了一款新产品，面向金融服务的 ChatGPT（ChatGPT for Financial Services）。这是一款面向企业的产品，真正试图将 ChatGPT 的强大功能——也就是大家在消费级产品中非常喜欢使用的工具等功能结合起来，同时也加入了企业层，支持公司专有模板，以及 Dilupa、标普（S&P）等数据来源。这非常令人兴奋。我们一直在与设计合作伙伴摩根士丹利（Morgan Stanley）和 Evercore 合作，反响非常不可思议。这就是演讲前半部分的内容。

演讲的后半部分则更加前瞻，深入思考我们在模型改进方面看到的一些趋势线，并将这些趋势线延伸到未来，尝试思考：好的，这些模型在 2027 年中或 2027 年底将能够做什么？这对在这些模型之上构建产品的人们意味着什么？以及你该如何提前为未来短短几个月内即将到来的智能水平做好规划。
<details><summary>Original English</summary>
>> Sure,
 yeah,
 I
 can
 give
 a
 quick
 30-second


intro
 to
 kind
 of
 what
 we
 just
 chatted


about.


One,
 I
 would
 say
 like
 we
 just
 released
 a


new
 product,
 chat
 GPT
 for
 financial


services.
 This
 is
 an
 enterprise-focused


product
 that's
 really
 trying
 to
 bring


the
 power
 mix
 the
 power
 of
 chat
 GPT,


kind
 of
 the
 tools
 and
 things
 that
 you


really,
 you
 know,
 like
 to
 use
 in
 the


consumer
 product,
 but
 also
 add
 in
 the


enterprise
 layer
 so
 that
 firm-specific


templates,


you
 know,
 sources
 like
 Dilupa,
 S&P,
 etc.


And
 so
 really
 exciting.
 We've
 been


working
 with
 our
 design
 partners
 Morgan


Stanley
 and
 Evercore
 on
 that,
 and


reception
 to
 that's
 been
 incredible.
 So


that
 was
 kind
 of
 the
 first
 half
 of
 the


talk.
 And
 in
 the
 second
 half
 of
 the


talk,
 really
 much
 more
 forward-looking,


so
 thinking
 deeply
 about
 some
 of
 the


trendlines
 that
 we're
 seeing
 in
 terms
 of


model
 improvements,
 and
 drawing
 those


trendlines
 out
 to
 the
 future
 and
 trying


to
 think
 a
 little
 about,
 okay,
 like
 what


are
 these
 models
 going
 to
 be
 able
 to
 do


at
 the
 end
 of,
 you
 know,
 mid-2027,
 end


of
 2027,
 and
 what
 does
 that
 mean
 for


folks
 that
 are
 building
 products
 on
 top


of
 that
 model,
 and
 how
 can
 you
 kind
 of


start
 to
 plan
 ahead
 to
 the
 intelligence


that
 comes
 in,
 you
 know,
 just
 a


matter
 of
 months.
</details>

### 从研究到产品：金融数据的上游训练与企业现实

>> 我觉得这是一个非常有趣的时期，因为你其实来自研究端。现在你领导着许多产品和工程工作，但请告诉我们，打造一个金融专属产品需要什么？你在主题演讲中提到，当你们推出 ChatGPT 工作版时，用户数量出现了一次上升。当时 Codex 开始面向大众提供，人们开始将其用于金融领域，而现在你们正在推出首款金融产品。金融推理数据到底是什么样的？金融专属模型中都融入了什么？
<details><summary>Original English</summary>
>> I think
 it's
 a
 fun
 time
 because
 you


actually
 come
 from
 the
 research
 side
 of


things.
 So
 you
 now
 lead
 a
 lot
 of
 the


product
 and
 engineering,
 but
 tell
 us


what
 it
 takes
 to
 make
 a


financial-specific
 product.
 You


mentioned
 in
 the
 keynote
 that
 there
 was


sort
 of
 an
 uptick
 in
 users
 when
 you


launched
 ChatGPT
 work.
 So,
 Codex
 started


to
 become
 available
 to
 the
 masses.


People
 start
 using
 it
 for
 finance,
 and


now
 you're
 shipping
 your
 first
 finance


product.
 What
 is
 like
 financial


reasoning
 data
 like?
 What
 goes
 into


finance
 specific
 models?
</details>

>> 是的，这是一个很好的问题。我想说的一点是，我们为金融推理分析所做的所有训练数据，都是在上游融入我们所谓的“大运行”（big run）中的，也就是最终成为 6 Astra 或 61 Astra 等主干模型的训练运行。因此，尽管我们在模型中添加了大量金融数据，但它是进入主模型的，因而对于想要在其基础上进行构建的人来说也是可用的。这对我们非常重要。

在 OpenAI，我们确实希望这种智能不仅能为我们在内部以第一方方式构建的产品所用，而且也能让那些希望在其基础上打造初创公司、建立业务的人，以及希望将其直接整合到公司内部的金融机构所使用。因此，我们会让所有这些智能在那里都可以获取。

你刚才谈到了一点产品与研究的关系，我认为这确实是我们在 OpenAI 工作的核心。在内部，我们将自己称为一家“研究与部署公司”（research and deployment company）。这意味着——我们特意按这个顺序组织结构——研究排在第一位，部署排在第二位。因此，当我们考虑归根结底要改变人们进行知识工作的方式时，我们基本上是按这个顺序工作的，对吧？我们首先考虑模型的能力、未来的发展方向以及能赋能哪些新事物。这是第一点。第二点，我们会非常深入地思考应该构建哪些产品功能和界面形态，以让更多人能够接触到这种模型智能。

我想你提到了我在主题演讲中的一张幻灯片，我们在那里展示了 Codex 在 OpenAI 内部的采用率图表。挺有意思的，因为你可以看到软件工程的采用曲线，基本上是一直稳步向右上角攀升。人们开始使用它并将其融入日常工作流程中。但如果你看金融、法务和销售，之前几乎全都是零，然后突然一下子跳升到了 90%。如果你看那条曲线，试图弄清楚在跳升发生的前后发生了什么——我们在 2 月份发布了 Codex 桌面端应用，也就是在那时采用率激增。因此，我确实认为这在某种程度上表明了协同开发这两者的重要性，而产品的目的就是让尽可能多的用户能够获得这种模型智能。
<details><summary>Original English</summary>
>> Yeah,
 it's
 it's
 a
 great
 question.
 I


mean,
 one
 thing
 I
 will
 say
 is
 that
 like,


you
 know,


all
 of
 the
 training
 data
 that
 we
 do
 for


financial,
 you
 know,
 reasoning
 analysis,


we
 do
 upstream
 into
 what
 we
 call
 the
 big


run,
 which
 is
 the
 the
 main
 kind
 of
 run


that
 becomes,
 you
 know,
 something
 like
 6


Astra
 or
 61
 Astra,
 etc.
 And
 so,
 even


though
 we're
 adding
 a
 bunch
 of
 financial


data
 to
 the
 model,
 it's
 going
 into
 the


main
 main
 model,
 and
 so
 therefore
 it's


available
 to
 folks
 that
 want
 to
 build
 on


top
 of
 it.
 And
 that
 is
 something
 that's


very
 important
 to
 us.


You
 know,
 at
 OpenAI,
 we
 really
 do
 want


that
 intelligence
 to
 be
 accessible
 not


only
 to
 our
 products
 that
 we're
 building


in-house
 in
 first-party
 ways,
 but
 also


for
 folks
 that
 want
 to
 build
 startups,


build
 businesses
 on
 top
 of
 that,
 as
 well


as,
 you
 know,
 financial
 firms
 that
 want


to
 integrate
 that
 directly
 into
 their


companies.
 And
 so,
 we
 will
 make
 all
 that


intelligence
 accessible
 there.


I
 think
 you
 touched
 a
 little
 bit
 on


product
 and
 research,
 and
 I
 think
 that's


like
 really
 core
 to
 what
 we
 do
 at


OpenAI.
 Internally,
 we
 call
 ourselves
 a


research
 and
 deployment
 company.
 And
 so,


what
 that
 means
 and
 we
 kind
 of
 structure


that
 in
 order
 on
 purpose,
 like
 research


comes
 first,
 and
 then
 deployment
 comes


second.
 And
 so,
 as
 we
 think
 about,
 you


know,
 at
 the
 end
 of
 the
 day
 trying
 to


change
 the
 way
 that
 people
 do
 knowledge


work,
 we
 kind
 of
 work
 in
 that
 order,


right?
 We
 think
 about
 the
 model


capabilities,
 where
 they're
 headed,
 what


kind
 of
 new
 things
 they
 enable.
 So,


that's
 one.
 And
 then
 two,
 we
 think
 very


deeply
 about
 the
 product
 features
 and


surface
 areas
 that
 we
 should
 build
 to


make
 that
 model
 intelligence
 accessible


to
 more
 people.
 And
 I
 think
 you
 alluded


to
 to
 a
 slide
 in
 my
 my
 um


keynote
 where,
 you
 know,
 we
 had
 this


chart
 of
 Codex
 adoption
 within
 OpenAI.


And
 it's
 funny
 because
 you
 can
 you
 can


see
 the
 the
 software
 engineering


adoption
 curve,
 and
 it's
 just
 like
 up


into
 the
 right
 pretty
 steady.
 People
 are


picking
 it
 up
 and
 and
 incorporating
 into


their
 daily
 routines.
 But
 if
 you
 look
 at


finance
 finance,
 legal,
 and
 sales,
 you


know,
 it's
 pretty
 much
 at
 zero,
 and


suddenly
 it
 kind
 of
 jumps
 up
 to
 90%
 and


if
 you
 and
 if
 you
 look
 at
 that
 line
 and


try
 to
 see
 what
 happened
 around
 the
 time


where
 it
 jumped
 up,
 we
 we
 had
 released


Codex
 desktop
 app,
 um,
 you
 know,
 in


February
 and
 that
 was
 when
 that
 adoption


jumped
 up.
 And
 so,
 I
 do
 think
 it
 kind
 of


shows
 the
 importance
 of
 co-developing


those
 things
 and
 the
 purpose
 of
 the


product
 is
 to
 make
 that
 model


intelligence
 accessible
 to
 as
 many
 users


as
 possible.
</details>

>> 那么，在使用 Codex 处理金融应用的数据增长中，你们学到了哪些东西，随后将其应用到了金融数据的后训练（post-training）中？
<details><summary>Original English</summary>
>> So,
 in
 the,
 you
 know,
 that
 uptick
 of


data
 for
 using
 Codex
 for
 financial,
 you


know,
 applications,
 what
 sort
 of
 things


did
 you
 learn
 that
 you
 then
 applied
 into


the
 post-training
 of
 financial
 data?
</details>

>> 是的，这是个好问题。我可以谈谈我们是如何构建 ChatGPT 金融服务版的。这非常独特。我们并没有构建太多的第一方产品。我认为 Codex 算是我们最大也是最主要的一个，那是我们第一次开发一款产品时，将产品、模型评测/测试（model hardness）以及研究全部整合在同一个部门、同一个屋檐下，这确实给了我们很大的灵活性去推进构建工作。

我认为在过去大约 6 个月里从事这项工作中，我获得的最大感悟是：在企业级领域，你必须直面所处行业的现实，并围绕这一现实去构建。我认为这一点很容易被忽视。如果你仅仅从第一性原理出发去思考，你可能会得出一个看似合理的结论，而且你能用逻辑和推理来捍卫它。但如果你忽略了开始构建时所处世界的现状，忽略了行业内起作用的力量——无论是竞争力量，还是人们各自的目标——如果你不去思考这些，你就无法打造出正确的产品，对吧？

我们在 ChatGPT 金融服务版中看到了这一点，并且深入思考了这个问题。我给你举一个例子：数据。数据是我们思考如何构建产品的一个非常巨大的组成部分。数据属于从第一性原理来看有些难以捍卫的事情之一，因为当我说起要在这个产品上推进这项工作时，你说：“嘿，我想把季度财报电话会议纪要引入产品并进行捆绑。”人们会说的第一句话通常是：“看，应用商店里已经有 MCP 连接了。你把它捆绑进去能提供什么增量价值？在纸面上这看起来很糟糕。客户可能已经拥有相关许可了，所以他们可能会觉得自己在重复付费；而且他们可能已经有 MCP 了。那你为什么还要做这个？”

而现实情况是，我们实际去测试了所有这些 MCP。我们发现错误率非常非常高。我们连接的一些知名大型服务的 MCP，错误率甚至超过了 40%，对吧？所以 MCP 这种东西在纸面上看起来很好，但你必须看数据，看看实际发生了什么。所以在数据方面我们认为：“看，这太糟糕了。我们在规模化层面解决这个问题的唯一途径就是将数据引入内部，端到端地控制这种体验。”为了捆绑这些数据而额外支付的费用是完全值得的，对吧？因此这是我们必须做出的一个高度针对特定行业的产品决策。这一决策在客户中引起了共鸣。客户非常喜欢，他们提到的第一件事就是数据。所以，这起到了作用。
<details><summary>Original English</summary>
>> Yeah,
 it's
 a
 good
 question.
 I
 would
 say


like,
 yeah,
 I
 could
 talk
 a
 little
 bit


about
 how
 we
 went
 about
 building
 ChatGPT


for
 financial
 services.
 It's
 it
 was
 very


unique.
 We
 we
 haven't
 built
 a
 whole
 lot


of
 first-party
 products.
 I
 would
 say


like
 Codex
 was
 really
 like
 our
 biggest


and
 main
 one
 and


it
 was
 the
 first
 time
 we
 developed
 a


product
 where
 the
 product,
 the
 model


hardness
 and
 the
 the
 research
 was
 all


kind
 of
 under
 one
 house
 and
 under
 one


roof
 and
 it
 really
 gives
 us
 a
 lot
 of


flexibility
 to


go
 about
 building
 things.
 I
 think
 the


biggest
 takeaway
 that
 I
 have
 from
 having


worked
 on
 this
 for
 the
 last
 6
 months
 or


so


is
 in
 enterprise,
 it's,
 you
 know,
 you


have
 to
 deal
 with
 the
 reality
 of
 the


industry
 that
 you're
 in
 and
 go
 build


around
 that.
 And
 I
 think
 that
 piece
 is


it's
 easy
 to
 ignore.
 Like
 if
 you
 just


think
 about
 it
 from
 first
 principles,


you
 can
 come
 to
 a
 conclusion
 that
 makes


sense
 and
 you
 talk
 about
 it
 and
 you
 can


defend
 it
 with,
 you
 know,
 with
 logic
 and


reason.
 But
 if
 you
 ignore
 the
 state
 of


the
 world
 that
 you
're
 in
 when
 you
 start


building
 and
 the
 forces
 that
 are
 at
 play


within
 the
 industry
 to
 try,
 you
 know,


it's
 either
 competitive
 forces,
 people


have
 their
 own
 objectives.
 And
 if
 you


just
 don't
 think
 about
 that,
 you're
 not


going
 to
 build
 the
 right
 product,
 right?


And
 so,
 we
 saw
 that
 with,
 um,
 ChatGPT


for
 financial
 services.
 We
 thought
 about


that
 a
 lot.
 I'll
 give
 you
 one
 example.


Um,
 data.
 Data
 is
 like
 a
 huge
 part
 of


how
 we
 thought
 about,
 um,
 building
 the


product.
 And,
 you
 know,
 and
 and
 data
 was


one
 of
 those
 things
 where
 on
 first


principles
 it
 was
 a
 little
 bit
 tough


when
 I
 was
 talking
 about
 build
 working


on
 this
 product
 to
 defend
 because,
 you


know,
 you
 say,
 "Hey,
 like
 I
 want
 to
 go


and
 bring
 quarter
 earnings
 transcripts


into
 the
 product
 and
 bundle
 it."
 And
 the


first
 question
 that
 the
 first
 thing


people
 are
 going
 to
 say
 are
 is,
 "Look,


there's
 an
 MCP
 connection
 in
 the
 store.


Like
 what
 is
 what
 is
 the
 incremental


value
 that
 you're
 providing
 by
 at


bundling
 that
 in?
 On
 paper
 it
 looks
 bad.


It's
 like
 you
 can
 they
 might
 already


have
 a
 license
 for
 it,
 so
 they
 might


feel
 like
 they're
 paying
 twice
 for
 it.


Um
 and
 they
 might
 have
 an
 MCP.
 And
 so


like
 why
 are
 you
 building
 this?
 And
 the


reality
 is
 we
 went
 and
 we
 tested
 all


these
 MCPs.
 And
 what
 we
 found
 was
 the


error
 rates
 were
 were
 really
 really


high.
 Some
 some
 of
 the
 MCPs
 that
 we


connected
 some
 big
 names
 40%
 plus
 error


rate
 on
 their
 MCPs,
 right?
 And
 so
 um


MCPs
 is
 one
 of
 those
 things
 where
 it
 it


looks
 way
 on
 paper,
 but
 you
 have
 to
 go


see
 look
 at
 the
 data
 and
 see
 what's


actually
 going
 on.
 And
 so
 for
 data
 we're


like,
 "Hey
 look,
 this
 is
 really
 bad.
 The


only
 way
 we
 can
 go
 about
 fixing
 this
 at


scale
 is
 to
 bring
 the
 data
 in
 house,


like
 just
 control
 that
 experience
 end
 to


end."
 And
 the
 extra
 money
 that
 you
 pay


on
 top
 to
 bundle
 that
 data
 is
 worth
 it,


right?
 And
 so
 that
 was
 a
 product


decision
 that
 we
 had
 to
 make
 that
 was


very
 industry
 specific.
 Um
 and
 it's
 been


resonating
 with
 customers.
 Customers


love
 it.
 They
 you
 know,
 the
 number
 one


thing
 they
 call
 out
 is
 the
 data.
 And
 so


um
 it
 worked.
</details>

### 插件架构与构建特定领域产品的最佳实践

>> 你们在这方面取得了很大的成功。请从技术层面为那些针对特定业务构建适配框架的人讲讲吧。你们对 Codex 进行了调整，做了后训练，做了打造 ChatGPT 金融服务版所需的各种工作。如果有人想在法务、销售等其他领域做同样的事情，最佳实践是什么？你们学到了什么？直接采用现成模型并在其周围真正构建出某种产品，都需要投入什么？
<details><summary>Original English</summary>
>> So,
 you
 had
 good
 success
 in
 this.
 Tell


us
 about
 the
 technical
 side
 of
 things


for
 people
 building
 a
 harness
 adaptation


for
 a
 specific
 service,
 right?
 So,
 you


guys
 went
 out,
 you
 changed
 Codex,
 you


did
 post
 training,
 you
 did
 whatever
 you


did
 to
 make
 ChatGPT
 for
 financial


services.
 If
 someone
 was
 to
 do
 the
 to
 do


the
 same
 for
 another
 domain,
 say
 legal,


sales,
 whatever,
 uh
 what
 are
 the
 best


practices
 there?
 What
 did
 you
 learn?


What
 goes
 into
 just
 taking
 off
 the
 shelf


and
 actually,
 you
 know,
 making
 a
 certain


product
 around
 it?
</details>

>> 是的，我很喜欢这个问题。

我也试着在演讲中提到过这一点，有趣的是，谈论后训练方面的事情很有意思，因为这是我们所做的独特工作，也让人们感到兴奋；但我们所构建的内容中，有 95% 是初创公司或其他公司绝对也能做到的。我们其实并没有借助我们直接修改模型的能力去打造出出色的产品，对吧？因此我认为提到这一点非常好。

我想说的大致有两点。第一，我们构建的大部分产品是建立在 Codex——或者我现在应该说是 ChatGPT——的插件架构和插件原语（primitives）之上的。这是我们投入了大量时间和精力的领域。OpenAI 是一家很有意思的公司，如果初创公司要在 OpenAI 之上进行构建，他们在内部面临的问题，我们内部同样也会面对。因此在很大程度上，我的团队就像是一家在 OpenAI 技术之上构建产品的初创公司，对吧？所以即使在内部，我们也需要为像我这样的团队找到可扩展的方式，站在巨人的肩膀上，在 Codex 之上进行构建。Codex 非常出色，它拥有极佳的记忆力，具备良好的技能，具有持久性。Codex 有很多非常精彩的地方，但我团队的核心论点是：Codex 可以带你走完打造一款在市场上取得成功的产品所需的大约 80% 的路程，但还缺少 20%。因此，我们需要找到某种方法让我的团队去构建这 20% 以真正赢得市场，因为该论点的另一半在于：如果你仅仅直接拿 Codex 当作金融产品发布，它是会失败的。因此那 20% 实际上至关重要。

所以我想说的是，我们基于插件架构进行了构建。它使用的正是任何想在 ChatGPT 之上构建的开发者都可以使用的原语。我在演讲中说过一句话：我真的认为，基于 ChatGPT 插件将会诞生价值十亿美元的业务。你将能够利用所有这些通用横向功能，只需在上面添加你自己的“独门秘方”（secret sauce）。这种独门秘方可能是数据，可能是 UI 的改进，也可能是某种系统集成；但这套独门秘方非常有价值，我认为在那里可以创造出价值十亿美元的成果。
<details><summary>Original English</summary>
>> Yeah,
 it's
 a
 yeah,
 I
 like
 the
 question
 a


lot.
 Um


it
 it
 you
 know,
 I
 tried
 to
 allude
 to


this
 in
 my
 keynote
 as
 well,
 but
 the
 like


interesting
 thing
 is,
 you
 know,
 it's
 fun


to
 talk
 about
 the
 post
 training
 stuff


because
 it's
 unique
 to
 what
 we
 do
 and
 uh


gets
 people
 excited,
 but
 95%


of
 what
 we
 built
 was
 something
 that


absolutely
 a
 startup
 could
 do,
 uh


another
 company
 could
 do.
 And
 we
 didn't


really
 have
 to
 go
 leverage
 our
 ability


to
 go
 make
 changes
 in
 the
 model
 to
 go


about
 building
 fantastic
 product,
 right?


And
 so
 I
 think
 it's
 a
 great
 call
 to
 kind


of
 mention
 that
 piece.
 Um
 what
 I
 would


say
 is
 like
 uh
 twofold.
 One
 is
 most
 of


the
 product
 that
 we
 built
 was
 built
 on


top
 of
 the
 Codex
 um


or
 I
 should
 say
 ChatGPT
 now,
 um,
 plugin


architecture
 and
 plug
 and
 primitives.


And
 that
 is
 something
 that
 we've
 been


investing
 a
 lot
 of
 time
 and
 energy
 in.


Um,
 you
 know,
 OpenAI
 is
 like
 an


interesting
 company
 where,
 you
 know,
 we


have
 we
 kind
 of
 face
 the
 same
 problems


internally
 that
 a
 startup
 would
 face,


uh,
 if
 they
 were
 to
 build
 on
 top
 of


OpenAI.
 So,
 in
 very
 in
 a
 lot
 of
 ways


like
 my
 team
 is
 kind
 of
 like
 a
 startup


that's
 building
 on
 top
 of
 OpenAI


technology,
 right?
 And
 so,
 um,
 even


internally,
 we
 need
 to
 find
 scalable


ways
 for
 teams
 like
 myself
 to
 stand
 on


the
 shoulders
 of
 giants
 and
 build
 on
 top


of
 Codex,
 right?
 The
 Codex
 is
 fantastic.


Um,
 it's
 got
 great
 memory.
 It's
 got
 good


skills.
 Like
 there's
 a
 you
 know,
 it's


persistent.
 Um,
 there's
 a
 lot
 of
 things


that
 are
 wonderful
 about
 Codex,
 but
 the


thesis
 of
 my
 team
 was
 Codex
 was
 Codex


will
 get
 you
 about
 80%
 of
 the
 way
 to
 a


product
 that
 would
 be
 successful
 in
 the


market,
 but,
 you
 know,
 um,
 the
 20%
 is


missing.
 And
 so,
 we
 need
 to
 find
 some


way
 for
 my
 team
 to
 go
 build
 that
 20%
 to


actually
 go
 win
 cuz
 the
 other
 half
 of


the
 thesis
 was
 if
 you
 just
 took
 Codex


and
 launched
 it
 as
 a
 finance
 product,


um,
 it
 would
 fail.
 And
 so,
 that
 20%
 is


actually
 pivotal.
 And
 so,
 what
 I
 would


say
 is
 we
 we
 went
 and
 we
 built
 on
 top
 of


the
 plugin
 architecture.
 It's
 using
 the


same
 primitives
 that
 are
 available
 to


any
 of
 the
 builders
 that
 want
 to
 go


build
 on
 top
 of,
 um,
 ChatGPT.
 And
 I
 you


know,
 I
 had
 a
 line
 in
 my,
 um,


presentation,
 but
 I
 I
 really
 do
 think


that
 there's
 going
 to
 be
 a


billion-dollar
 business
 built
 on
 top
 of


a
 uh
 ChatGPT
 plugin,
 right?
 Like
 it's


like
 you're
 going
 to
 be
 able
 to
 leverage


all
 of
 that
 horizontal
 functionality
 and


just
 add
 your
 secret
 sauce
 on
 top.
 And


that
 secret
 sauce
 might
 be
 data,
 it


might
 be
 UI
 changes,
 um,
 it
 could
 be
 an


integration,
 but,
 you
 know,
 that
 secret


sauce
 is
 really
 valuable
 and
 I
 think


there's
 there's
 a
 billion
 dollars
 worth


of
 value
 to
 be
 built
 there.
</details>

### 金融场景下的安全体系：人机协同与组织化质检

>> 是的，对这个行业来说现在是一个有趣的时期，因为我们所处的时间点上，编排（orchestration）正变得越来越自动化，智能体团队能够自主开展工作。但在金融领域，显然伴随着很多风险。你能谈谈融入产品中的安全机制吗？
<details><summary>Original English</summary>
>> So,
 uh,
 yes,
 it's
 an
 interesting
 time


for
 the
 industry
 cuz
 we're
 at
 a
 a
 time


now
 where
 orchestration
 is
 uh


is
 becoming
 a
 lot
 more
 automated,
 you


know,
 teams
 of
 agents
 going
 out
 and


doing
 things.
 But
 for
 finance,


obviously,
 there
 are
 a
 lot
 of
 risks
 uh


involved
 in
 that.
 So,
 can
 you
 talk
 a
 bit


about
 about
 the
 safety
 sort
 of
 uh
 that


you've
 baked
 into
 the
 product?
</details>

>> 是的，安全极其重要。而且它只会变得越来越重要，因为智能体已经变得越来越自主、越来越独立，我们预计这种趋势将在 2027 年和 2028 年持续下去。

对于我们上个月构建并发布的产品而言，在安全、审慎审计工作以及确保模型不会犯下影响业务成果的错误方面，已经存在大量现成的范式，我们能够大量借鉴这些范式。我们推出的现有产品是面向该领域知识工作者的生产力工具。因此，其背后的理念是深度假设始终有“人类在回路中”（human in the loop）。

其逻辑在于：你是一名金融分析师，当天有一长串待办事项。就像软件工程师使用 Codex 一样，对于其中的每一项任务，你首先做的是尝试用 ChatGPT 来完成。根据具体任务的不同，它可能会帮你完成 30%，也可能帮你完成 80%，但始终存在人类在回路中进行主导监管的假设。这使得我们非常容易构建出一款产品，将审计和审查的责任交给人类，纳入人们的职责范围。这为我们提供了很好的效果，而且很容易沟通传达。这非常好。

不过我想说，我们正在深入思考接下来的演进方向。而下一步的发展形态与需要人类始终监控的生产力工具大不相同。在思考未来的方向时，我们主要考虑两件事：

第一，我们如何将产品的安全配置文件塑造为人们能够直观理解的形式。人们能够极其直观理解的一件事就是如何与他人协作。因此我们的论点是，如果我们将产品做得与你跟同事、实习生及周围人协作的方式非常相似，那么人们就能非常快速、轻松地掌握并适应。因此，我们需要将产品的安全配置塑造得像人一样。这里有几点我想指出：首先是“读写权限”的概念，即使对人也是如此。比如你作为一名新入职的软件工程师进入一家公司，我以前在谷歌，往往需要通过一种叫“代码可读性认证”（readability）的机制。在你可以开始调整触碰系统之前，会有这套制衡机制和系统存在。因此，监控人类工作的系统早已就位。如果模型的行为更像人类，你就可以借助这些现成体系。这使得与这些金融机构沟通和推进合作变得非常容易。这是我们接下来正在大力投入的方向。

最后我想说的是，至少在我们起步的银行业背景下，初级分析师负责大量基础工作，其成果会移交给关联协理人员（associates），由协理人员进行审查；然后协理人员加入自己的核心价值、独门逻辑和推理判断，再移交给副总裁（VP）；副总裁再上报给董事（director）、董事总经理（MD）。因此存在这样一套层级系统，其中暗含着层层核查机制。这套系统早已建立，专门用来防止人类犯错；毕竟人类犯的错误跟模型一样多。相关的系统早已存在。因此，在构建金融产品方面，我们也在大力借鉴这些现存的系统架构。
<details><summary>Original English</summary>
>> Yeah,
 um,
 safety
 is
 super,
 super


important.
 Um,


I
 would
 say
 that
 like
 and
 it's
 only


going
 to
 get
 more
 important
 uh
 because


the
 you
 know,
 the
 agents
 are
 already


getting
 more
 autonomous
 and
 more


independent.
 And
 I
 think
 that
 trend
 we


expect
 it
 to
 continue
 into
 '27
 and
 into


'28.
 Um
 I
 would
 say
 if
 uh


for
 the
 for
 the
 product
 that
 we
 built


and
 launched
 last
 month,
 um
 we
 there
 was


a
 bunch
 of
 paradigms
 that
 already


existed
 um
 as
 it
 pertains
 to
 safety
 um


and
 you
 know,
 being
 thoughtful
 around


auditing
 the
 work,
 making
 sure
 that
 the


model's
 not
 making
 a
 mistake
 that's


going
 to
 impact
 business
 outcomes.
 And


we
 were
 able
 to
 lean
 heavily
 into
 those.


And
 and
 what
 I
 would
 say
 is
 the
 existing


product
 that
 we
 launched
 is
 a


productivity
 tool
 for
 knowledge
 workers


working
 in
 this
 space.
 And
 so
 the
 idea


behind
 it
 is
 there's
 a
 a
 deep
 assumption


that
 there's
 always
 a
 human
 in
 the
 loop,


right?
 Like
 So
 the
 idea
 there
 is,
 you


know,


you're
 a
 financial
 analyst
 and
 you
 have


a
 a
 laundry
 list
 of
 things
 you
 want
 to


get
 done
 that
 day.
 And
 and
 just
 like
 how


a
 software
 engineer
 would
 do
 with
 Codex,


for
 every
 one
 of
 those
 items,
 the
 first


thing
 you
 do
 is
 try
 to
 build
 it
 with


ChatGPT,
 right?
 And
 it
 might
 get
 you
 30%


of
 the
 way
 there,
 it
 might
 get
 you
 80%


of
 the
 way
 there
 depending
 on
 the
 task,


but
 there's
 always
 this
 presumption
 of


humans
 in
 the
 loop
 uh
 that
 are
 presiding


with
 that
 work.
 And
 um
 that
 made
 it
 very


easy
 for
 us
 to
 to
 build
 a
 product
 where


we
 could
 kind
 of
 pass
 off
 the


responsibility
 of
 auditing
 review
 uh


into
 the
 people's
 hands
 and
 into


people's
 responsibilities.
 And
 that


worked
 for
 us
 well
 and
 it
 was
 easy
 to


communicate.
 Um
 so
 that
 was
 wonderful.
 I


will
 say
 we're
 thinking
 very
 deeply


about
 what
 comes
 next.
 And
 and
 what


comes
 next
 looks
 different
 uh
 than
 than


a
 productivity
 tool
 um
 that
 sits
 and
 and


is
 always
 being
 monitored
 by
 a
 human.


And
 I
 think
 as
 we
 think
 about
 what
 comes


next,
 there's
 kind
 of
 two
 things
 we're


thinking
 about.
 One
 is


how
 do
 we
 kind
 of
 shape
 the
 security


safety
 profile
 of
 the
 product
 into


something
 that
 people
 understand


intuitively.
 And


some
 I
 would
 say
 something
 that
 people


understand
 very
 intuitively
 is
 how
 to


work
 with
 other
 people.
 Um
 and
 so
 our


thesis
 is
 if
 we
 make
 the
 product
 very


similar
 to
 how
 you
 work
 with
 your
 your


co-workers,
 your
 interns,
 people
 around


you,
 that
 is
 something
 that
 people
 can


pick
 up
 and
 learn
 very
 quickly,
 very


easily.
 And
 we
 And
 therefore
 we
 need
 to


shape
 the
 security
 profile
 of
 that
 to


look
 like
 a
 person.
 And
 so
 there's
 a
 few


things
 I'll
 call
 out
 there.
 One
 is


there's
 this
 notion
 of
 read-write,
 uh
 uh


you
 know,
 even
 for
 people.
 Like,
 uh


you're
 a
 new
 software
 engineer
 at
 a


company,
 you
 oftentimes,
 you
 know,
 I
 was


at
 Google,
 you
 need
 you
 need
 something


called
 readability.
 And
 so,
 there's


these
 kind
 of
 like
 checks
 and
 balances


and
 systems
 in
 place
 before
 you
 can


start
 mucking
 around
 touching
 the


system.
 And
 so,
 there's
 already
 systems


in
 place
 to
 monitor
 the
 work
 of
 people.


So,
 if
 if
 models
 behave
 more
 like


people,
 then
 you
 can
 leverage
 those


systems.
 And
 that
 makes
 it
 very
 easy
 to


kind
 of
 talk
 about
 and
 work
 through
 this


um
 with
 these
 financial
 institutions.


So,
 that's
 something
 we're
 leading
 into


pretty
 heavily
 coming
 up.
 And
 the
 very


last
 thing
 I
 would
 say
 is,
 at
 least
 in


the
 context
 of
 banking,
 which
 is
 where


we
 kind
 of
 started,
 um
 there's
 already


this
 system
 in
 place
 for
 junior
 analysts


doing
 a
 lot
 of
 the
 groundwork.
 Uh
 their


work
 gets
 passed
 off
 to
 associates.


Associates
 are
 reviewing
 the
 work.
 Um


then
 the
 associates
 are
 kind
 of
 adding


their
 secret
 sauce,
 their
 magic,
 their


reasoning.
 That
 gets
 passed
 off
 to
 the


VP.
 VP
 goes
 up
 to
 the
 director,
 managing


director.
 So,
 there's
 this
 kind
 of
 like


a
 hierarchical
 system
 where
 there's
 this


implicit
 work
 checking
 that's
 happening.


That's
 already
 been
 built
 out
 to
 stop
 uh


to
 try
 to
 prevent
 against
 uh
 mistakes


that
 humans
 make,
 right?
 Like
 humans


make
 just
 as
 many
 mistakes
 as
 models.


And
 so,
 there's
 systems
 that
 are
 built


there.
 And
 so,
 we're
 also
 leaning


heavily
 in
 terms
 of
 those
 systems
 as
 it


as
 it
 pertains
 to
 building
 financial


products.
</details>

>> 明白。
<details><summary>Original English</summary>
>> Okay.
</details>

### 事实性错误与品味判断：模型能力的突破与短板

>> 金融界似乎有一种误解，认为一个错误就会不断放大，如果你提交了错误的内容，你的整个职业生涯都可能面临风险。人们应该如何看待开始使用它？如果是一名分析师，该如何使用这些工具？你对于我们当前所处的阶段有什么类比吗？例如自动驾驶有不同的自治级别。我记得你的一张幻灯片上写着到 2027 年你认为将不再有 PowerPoint，很多人都会在工作回路中使用 AI 工具。
<details><summary>Original English</summary>
>> I
 say
 there's
 this
 like
 sort
 of


misconception
 where
 in
 the
 finance


world,
 one
 mistake
 really
 compounds.


Like
 your
 your
 whole
 career
 is
 at
 risk


if
 you
 submit
 something
 wrong.
 How


should
 people
 think
 about
 getting


started
 in
 using
 it?
 So,
 if
 you're
 an


analyst,
 um
 how
 should
 you
 use
 these


tools?
 And
 do
 you
 have
 like
 any


analogies
 towards
 where
 we're
 at
 right


now?
 So,
 there's
 like
 levels
 of


self-autonomy
 in
 self-driving.
 One
 of


your
 slides
 I
 think
 said
 like
 2027
 you


see
 no
 more
 PowerPoint.
 A
 lot
 of
 people


will
 be
 using
 AI
 tools
 in
 the
 loop.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 那么，人们应该如何看待我们现在所处的位置以及未来的发展方向？如果他们抱有“只要犯一个错，我的职业生涯就完了”这种误解，他们该如何采用这些工具？
<details><summary>Original English</summary>
>> So,
 how
 should
 people
 think
 about
 where


we
 are
 now
 and
 where
 things
 are
 going


and
 how
 should
 they
 adopt
 these
 tools
 if


they
 have
 that
 misconception
 of
 like
 one


mistake,
 my
 career's
 over.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 显然现在有人类在回路中，但随着他们需要卸载越来越多的任务，他们未来该如何看待这件事？
<details><summary>Original English</summary>
>> Obviously,
 there's
 human
 in
 the
 loop,


but
 how
 should
 they
 also
 think
 about
 it


going
 forward
 as


they
 need
 to
 offload
 more
 and
 more
 or
</details>

>> 好的，太好了。对此我有两个视角，它们始于不同的假设。

我认为“犯一个错误职业生涯就完了”这种观念本身是不准确的，我顺着这一思路有相应的考量。但我们先假设它是真的，对吧？在假设其为真的情况下，我想说的是：并非所有错误都是等同的，也并非所有模型能力都是等同的。当你思考模型或人类可能犯下哪些终结职业生涯的错误时，通常是在达到某个级别之后才会发生。比如如果你是副总裁，风险就比初级分析师要高，因为有在此之前工作已被核查的前置假设。因此如果董事总经理（MD）看到了错误，那是一个巨大的问题，意味着许多安全网都失效了，错误才会传递到 MD 面前，对吧？

但我想说的是，断送职业生涯的错误通常是指你在某项事实上完全弄错了，而该事实信息改变了结论。这显然是你可能犯的最大一类错误。而我想说的是，我们正在看到模型在细节关注度方面取得巨大进步。“幻觉”在 2022 年、2023 年曾是一个经常被提及的重要词汇，如今已经很少被提起了。我们在模型处理事实性错误的可靠性方面开始看到巨大的改进。因此，对于那种会导致你被解雇的恶劣错误，模型正变得越来越擅长规避，并且还会继续大幅提升。所以我其实非常有信心，持续的改进加上现有的系统核查机制，将使得这类错误传递到 MD 面向的概率变得极低，对吧？

而在我看来，模型目前所缺乏且仍需改进的，其实并不是这种断送职业生涯的错误，而是涉及人类判断力和品味（taste）的部分。比如“这张幻灯片看起来很丑”，对吧？它本身没有错，但排版、配色看起来有些失调，某些地方看起来很粗糙，因此这不是一张好幻灯片。这并不属于事实错误那种断送职业生涯的错误，但它仍然很重要，关系到这项工作的实用程度。因此，当我们思考走向 2027 年的发展进程时，我认为模型在人类品味这一维度上会有极大改善。这也是我在演讲中提到的：我认为模型在更偏软性目标函数的人类品味上会变得好得多。这不再是“它对还是错？”，而是比较性质的——“是否存在比这更好的方案？”我认为模型未来在这方面会有很大进步。
<details><summary>Original English</summary>
>> Yeah.
 No,
 that's
 that's
 wonderful.
 Um
 I


I
 have
 two
 perspectives
 on
 this.
 And


they
 come
 they
 start
 with
 different


assumptions.
 Um
 I
 think


I
 I
 think
 the
 notion
 that
 like
 my


career's
 over
 if
 you
 make
 one
 mistake
 is


an
 incorrect
 notion.
 And
 I
 have
 a
 line


of
 thought
 that
 like
 follows
 that.
 But


let
 me
 let's
 the
 first
 assume
 that
 it's


true,
 right?
 And
 and
 in
 the
 case
 that


it's
 true,
 what
 I
 would
 say
 is
 like
 not


all
 mistakes
 are
 created
 equally
 and
 not


all
 model
 capabilities
 are
 created


equally.
 And
 so
 when
 you
 think
 about
 the


mistake
 that
 a
 model
 or
 a
 human
 could


make
 that
 could
 be
 career
 ending,


you
 know,
 it's
 it's
 usually
 once
 you
 get


up
 to
 a
 certain
 level.
 Like
 if
 you're
 a


you
 know,
 VP
 the
 stakes
 are
 higher
 than


when
 you're
 a
 junior
 analyst
 because


there
 is
 a
 presumption
 of
 work
 having


been
 checked
 up
 to
 that
 point.
 So
 if
 an


MD
 MD
 sees
 a
 mistake,
 that's
 a
 huge


problem.
 A
 lot
 of
 the
 safety
 nets
 have


been,
 you
 know,
 have
 failed
 for
 that


mistake
 to
 make
 it
 up
 to
 an
 MD,
 right?


Um
 but
 what
 I
 would
 say
 is
 like,
 you


know,
 the
 career
 ending
 mistake
 is


something
 where
 you
 get
 a
 piece
 of


information
 factually
 incorrect.
 And


that
 piece
 of
 factual
 information


changes
 the
 conclusion.
 Like
 that
 is


obviously
 like
 the
 kind
 of
 the
 biggest


type
 of
 mistake
 that
 you
 can
 make.
 And


what
 I
 would
 say
 is
 we're
 seeing
 a
 lot


of
 progress
 in
 in


attention
 to
 detail.
 And
 you
 know,
 the


hallucination
 used
 to
 be
 a
 big
 term
 that


used
 to
 come
 up
 in
 2022,
 2023
 that


doesn't
 come
 up
 nearly
 as
 often


nowadays.
 I
 would
 say
 that
 like
 we're


starting
 to
 see
 huge
 improvements
 in
 the


liability
 of
 models
 as
 it
 pertains
 to


factual
 mistakes.
 So
 the
 the
 kind
 of


egregious
 mistake
 that
 would
 get
 you


fired,
 models
 are
 getting
 much
 better
 at


and
 continue
 to
 get
 much
 better.
 And
 so


I
 feel
 actually
 quite
 confident
 that
 a


combination
 of
 that
 continual


improvement
 plus
 the
 existing
 system


checks
 in
 place
 are
 will
 make
 it
 such


that,
 you
 know,
 that
 type
 of
 mistake,


the
 chance
 of
 that
 propagating
 up
 to
 an


MD
 is
 just
 very
 low
 probability,
 right?


What
 I
 would
 say


the
 models
 are
 lacking
 today
 and
 they


still
 need
 to
 improve
 is
 actually
 not


the
 career
 ending
 mistake,


but
 it's
 the


it's
 the
 bit
 that
 involves
 human


judgment
 and
 taste.
 So
 it's
 the
 this


slide
 looks
 ugly,
 right?
 And
 it's
 it's


not
 wrong,
 but
 it's
 formatted
 like
 the


colors
 look
 a
 little
 bit
 off.
 Something


about
 it
 looks
 sloppy
 and
 therefore,
 you


know,
 this
 is
 not
 a
 good
 slide.
 And
 and


that's
 that's
 not
 a
 career
 ending


mistake
 in
 the
 way
 that
 in
 in
 like
 a


factual
 mistake
 is,


but
 it
 It
 matters.
 It
 still
 matters
 in


terms
 of
 how
 useful
 that
 work
 is.
 And


so,
 as
 we
 think
 about
 the
 progression
 in


going
 into
 2027,
 what
 I
 would
 say
 is
 I


expect
 the
 model
 to
 get
 much
 better
 at


the
 human
 taste
 component.
 And
 that's


what
 I
 was
 kind
 of
 alluding
 to
 in
 my


keynote
 is
 I
 think
 the
 model
 will
 get


much
 better
 at
 human
 taste
 on
 things


that
 are
 softer
 objective
 functions.


It's
 not
 is
 it
 right
 or
 wrong?
 It's


comparative.
 It
 Is
 there
 something


that's
 better
 than
 this?
 And
 I
 think


models
 are
 going
 to
 get
 much
 better


along
 that
 dimension
 moving
 forward.
</details>

### 如何训练“品味”：奖励模型与编程领域的成功先例

>> 怎么做呢？我们如何解决品味问题？如何将品味训练到模型中？
<details><summary>Original English</summary>
>> How
 so?
 How
 do
 we
 solve
 taste?
 How
 do
 we


train
 taste
 into
 the
 models?
 Um
</details>

>> 是的，挺有意思的。在非常早期的阶段，我们训练模型基本上完全依赖品味，对吧？也就是基于人类反馈的强化学习（RLHF）。人类反馈始终是一种成对（pairwise）的信号：给定两个选项，哪一个更好？因此，强化学习的早期阶段就是建立在对人类品味进行训练的理念之上的。后来显然出现了可验证奖励（verifiable rewards）、环境等机制，我们构建了大量机制来进行其他类型的奖励和其他类型的强化学习。于是人们在某种程度上忘记了强化学习的早期阶段全都是围绕人类品味展开的。

那么，如何针对人类品味进行训练呢？我认为技术层面的答案其实非常简单，当然实际操作层面的答案会更复杂一些。实际的解决方式就是训练一个奖励模型（reward model），对吧？你只需训练一个奖励模型。让一群人类查看成对的生成内容，并指出哪一个更好。这种方法至今依然有效。

比如一个有趣的事实：我们对幻灯片就是这么做的，对吧？如何让这些模型更擅长生成演示文稿呢？我们就找一群人对比两张幻灯片，指出哪一张看起来更好。人类实际上在审美判断方面极其出色，对吧？我们发现人类在这方面其实比模型好得多。一个人可以在几秒钟内看完两张幻灯片并判断出哪张更好看；而如果你让一个模型——比如评分模型——去做这件事，它会消耗大量的推理 token 去分析这个像素怎样、那个细节如何，最终得出的还可能是错误结论。因此，人类在让这些模型变得更好方面依然极其有价值。我们会大量依赖人类偏好来赋予模型诸如品味之类的特质。这是第一点。

最后我想补充的是，这方面是有先例的，这让我们确信这一策略行得通。这个先例就是编程代码。

代码模型虽然还没有被完全解决，但可以说我们已经完成了 80% 的路程，并正在攻克最后 20%。编程正是可验证奖励与人类品味的结合，对吧？可验证奖励是诸如：代码是否能编译？是否存在语法错误？函数的输出是否符合预期？因此这里有到位的可验证奖励；但优秀的软件工程有很大一部分关乎：这是否是干净的系统设计？你构建的系统长期来看是否易于维护？是否易于进行单元测试？它是否遵循了绝大多数社区或行业认为是正确的范式？

如果从这个视角来看，很多金融工作看起来非常相似：我有一个 Excel 模型，求和对不对？有没有引用错误（#REF!）？有大量的可验证事项可以让我们检查，以确保工作通过了第一关的合理性检查；但同样有大量问题关乎“这是否是我构建此模型的方式？”我在进入金融领域工作后学到的一点是，存在所谓“模型的质感”（the feel of the model）的概念：微调扰动输入参数，然后观察输出结果。一名经验丰富的金融专业人士可以通过微调输入、观察输出，从而直观理解数据流经这个模型的方式感觉是否良好，对吧？这是一种人类偏好，非常类似于“这段代码看起来是否整洁？写得好不好？”我认为我们在编程领域的成功，让我对我们能够在金融领域解决许多此类问题充满信心。
<details><summary>Original English</summary>
>> Yeah.
 I
 So,


it's
 funny.
 Like
 very
 early
 on
 in
 the


like
 early
 early
 chess
 days,
 the
 only


thing
 we
 trained
 models
 on
 were


essentially
 taste,
 right?
 Like
 the
 there


was
 reinforcement
 learning
 through
 human


feedback.
 And
 the
 human
 feedback
 was


always
 a
 pairwise
 signal.
 It
 was
 like


given
 two
 options,
 which
 one's
 better?


And
 so,
 the
 early
 days
 of
 reinforcement


learning
 were
 built
 on
 the
 notion
 of


training
 on
 human
 taste.
 Uh
 and
 then


obviously
 things
 like
 verifiable
 rewards


and
 environments
 and
 all
 you
 know,
 we


built
 a
 lot
 of
 machinery
 to
 do
 other


types
 of
 rewards
 and
 other
 types
 of
 RL.


And
 so,
 people
 kind
 of
 forgot
 that
 a
 lot


the
 early
 days
 of
 of
 RL
 reinforcement


learning
 were
 all
 around
 human
 taste.


And
 so,
 how
 do
 you
 train
 on
 human
 taste?


It's
 I
 think
 the
 technical
 answer
 is


quite
 simple.
 I
 think
 the
 like
 practical


answer
 obviously
 is
 more
 complicated.
 Um


the
 practical
 answer
 is
 you
 just
 train
 a


reward
 model,
 right?
 You
 just
 train
 a


reward
 model.
 You
 get
 a
 bunch
 of
 humans


to
 look
 at
 pairs
 of
 things
 and
 say
 which


one
 is
 better.
 And
 this
 still
 works.
 Um


so,
 like
 um
 fun
 fact,
 like
 we
 did
 this


for
 our
 slides,
 right?
 Like
 I
 mean,
 how


do
 you
 how
 do
 you
 go
 about
 making
 these


models
 better
 at
 generating


presentations?
 Well,
 we
 just
 get
 a
 bunch


of
 humans
 to
 look
 at
 pairs
 of
 slides
 and


say
 which
 one
 looks
 better.
 And
 humans


are
 actually
 really,
 really
 good
 at


aesthetic
 um
 judgment,
 right?
 Actually


much
 better
 than
 models
 is
 something


that
 we
 discovered.
 Is
 like
 a
 human
 can


look
 at
 two
 slides
 and
 within
 seconds


say
 this
 one
 looks
 better.
 And
 if
 you


have
 a
 model,
 like
 a
 grading
 grading


model,
 try
 to
 go
 about
 doing
 that,
 um


it's
 going
 to
 spend
 a
 whole
 bunch
 of


reasoning
 tokens
 this
 pixels
 this
 way,


this
 thing's
 that,
 uh
 and
 then
 maybe


comes
 to
 the
 wrong
 conclusion.
 And
 so,


humans
 are
 still
 really,
 really
 valuable


in
 making
 these
 models
 better.
 And
 so,


we
 will
 we
 will
 rely
 a
 lot
 on
 uh
 human


preference
 um
 to
 imbue
 things
 like


taste.
 So,
 that's
 one.
 Um,
 the
 last


thing
 I'll
 kind
 of
 add
 is
 there's


precedent
 for
 this,
 which
 makes
 us


confident
 that
 this
 strategy
 will
 work.


And
 that
 precedent
 I
 would
 say
 is


coding.


Um,
 the
 models
 have
 gotten
 I
 would
 say


coding
 is
 not
 fully
 solved,
 but
 like


let's
 say
 we're
 80%
 of
 the
 way
 there
 and


we're
 making
 progress
 on
 the
 on
 the
 last


20%.
 Um,
 coding
 is
 a
 combination
 of


verifiable
 rewards
 and
 human
 taste,


right?
 And
 so,
 the
 verifiable
 rewards


are,
 you
 know,
 does
 the
 does
 the
 code


compile?
 Are
 there
 syntax
 errors?
 Um,
 is


the
 output
 of
 the
 function
 expected?
 Um,


and
 so
 there's
 these
 verifiable
 power


rewards
 that
 are
 in
 place,
 but
 a
 lot
 of


good
 software
 engineering
 is
 um,
 is
 this


clean
 system
 design?
 Did
 you
 build
 a


system
 that's
 maintainable
 over
 time?


Um,
 is
 it
 easy
 to
 unit
 test?
 Is
 it


following
 paradigms
 that
 the
 vast


majority
 of
 the
 community
 or
 the
 um,


industry
 thinks
 is
 the
 right
 paradigm?


And
 if
 you
 look
 at
 it
 from
 that
 lens,


um,
 financial
 uh,
 a
 lot
 of
 financial


work
 looks
 very
 similar.
 It's
 the,
 you


know,
 I
 have
 an
 Excel
 model,
 does
 it
 sum


up?
 Are
 there
 reference
 errors?
 There's


a
 whole
 bunch
 of
 verifiable
 things
 that


we
 can
 check
 to
 make
 sure
 that
 the
 work


is
 passing
 this
 the,
 you
 know,
 first


pass
 sanity
 check,
 but
 there's
 also
 a


lot
 of
 is
 this
 the
 way
 I
 would
 have


built
 this
 model?
 Um,
 something
 I


learned
 about
 as
 I
 started
 working
 in


finance
 is
 there's
 this
 notion
 of
 like


the
 feel
 of
 the
 model,
 which
 is,
 you


know,
 you
 you
 kind
 of
 perturb
 the
 inputs


and
 you
 look
 at
 the
 outputs.
 And
 an


experienced
 financial
 professional
 can


kind
 of
 perturb
 the
 inputs,
 look
 at
 the


outputs
 and
 kind
 of
 understand
 does
 the


data
 flow
 through
 this
 model
 in
 a
 way


that
 feels
 good,
 right?
 And
 that
 is
 a


human
 preference
 that
 looks
 a
 lot
 like


does
 this
 code
 look
 clean?
 Is
 it
 well


written?
 And
 I
 think
 our
 success
 in


coding
 gives
 me
 confidence
 that
 we
 can


solve
 a
 lot
 of
 these
 problems
 in
 finance


as
 well.
</details>

>> 是的，我们可以顺便提一下 Cognition 的 Frontier Code。它不仅像 SWE-bench 那样注重“答案是否正确”，还关注“你是否愿意合并这段代码”。所以你可能会有多个都能通过测试的合规 PR，但你会合并哪一个？这也是为什么有时你会看到推理 token 较少反而表现更好的图表，但它其实也是一个品味基准（taste benchmark），对吧？
<details><summary>Original English</summary>
>> Yeah,
 we
 can
 shout
 out
 a
 frontier
 code


from
 cognition.
 So,
 it's
 not
 only
 like


sweet
 bench
 is
 very
 um,
 you
 know,
 is
 the


answer
 correct?
 This
 is
 also
 would
 you


merge
 the
 code?
 So,
 you
 can
 have


multiple
 answers
 that
 are
 proper
 PRs


that
 pass,
 but
 which
 one
 would
 you


merge?
 And
 that's
 why
 you
 sometimes
 see


the
 charts
 of
 lower
 reasoning
 is
 better,


but
 it's
 a
 taste
 benchmark
 as
 well,


right?
</details>

### 从基础任务迈向投资逻辑与高阶推理

>> 是的。你的另一个关于 2027 年的预测我觉得很有意思：你正在训练的模型在投资逻辑（investment thesis）以及产生投资和交易构想方面将变得更加出色。

但显然，经验丰富的金融专业人士非常擅长这一点，他们对此类事情有一种直觉；但这通常与市场上的主流观点相反，否则获得超额回报的机会就会变小。那么在训练智能体从事此类工作方面，你们是如何应对这个难题的？
<details><summary>Original English</summary>
>> Yeah.
 And
 uh,
 one
 of
 your
 other
 2027


predictions
 I
 thought
 was
 interesting


was
 that
 uh,
 you
 know,
 the
 models
 that


you're
 training
 will
 become
 much
 better


at,
 you
 know,
 investment
 thesis
 and
 sort


sort
 generating
 ideas
 for
 investment
 and


trading.


Um
 but
 obviously,
 you
 know,
 uh
 that's


something
 that
 humans
 are
 uh
 well


experienced
 kind
 of
 financial


professionals
 are
 very
 good
 at
 and
 they


kind
 of
 have
 an
 intuition
 for
 that
 kind


of
 thing,
 but
 it's
 often
 counter
 to
 the


prevailing
 wisdom
 out
 there.
 Otherwise,


you
 know,
 uh
 there's
 less
 of
 a
 chance
 of


it
 making
 a
 a
 great
 return.
 So,
 how
 how


are
 you
 tackling
 that
 problem
 in
 terms


of
 training
 the
 agents
 to
 do
 that
 kind


of
 work?
</details>

>> 是的。

我想说，到目前为止，绝大多数 AI 在金融领域的应用都非常集中在我所谓的初级分析师的工作上。

我认为这是出于两个原因：第一，你必须根据当今模型的能力来构建产品。如果看当今模型的能力，它们非常擅长接收关于具体要做什么的指令并去执行，对吧？比如“给我做一张幻灯片，我想让它长成这样，做漂亮点，使用我们的模板”等等。模型非常擅长做这些事情，因此我们围绕这些构建了产品体验。

另一件我想指出的是，人们强烈倾向于让模型去做好人类不擅长或不喜欢做的事情，对吧？我交流过的大多数人——当然也有例外——很多我交流过的人……大家交流过的人，哈哈，他们真的很不喜欢做 Excel 模型。这是一种枯燥繁琐的工作，极其注重细节，很容易出错。幻灯片也是如此：你需要复制 logo，极其精准地放置在页面的特定位置。这是很多人不喜欢做的极其繁杂的工作。因此，这也是推动我们去专注于其中某些任务的动力之一，对吧？这是这两者的结合：现有的模型能力非常擅长某些特定类型的任务，同时人类对喜欢做什么和不喜欢做什么的偏好也在帮助推动产品的方向，对吧？正是这两者的结合。

我认为我们已经解决了这两者中许多“唾手可得的果实”。因此进入 2027 年，我们将开始向业务栈的更高层推进，对吧？我们将从初级分析师能做的事情，推进到协理人员能做的一些任务，再到董事总经理会做的一些任务，沿着这个链条向上移动。随着你沿着链条往上走，目标函数会变得更加模糊。它不再是“这显然是一张好幻灯片还是坏幻灯片，或者我们能否将它呈现在客户面前”，而是“我不知道这个投资构想是否良好”。而且可能需要等待 3 年的时间，才能根据市场的实际走势给你一个明确具体的答案。因此目标变得更加模糊了。所以你训练模型的方法，以及你思考如何让模型变得更好的方式，从研究的角度来看都会变得更加困难。

但我想说的是，这并非不可能。它需要大量的研究专注度，需要极其优质的数据，需要来自该领域专家的丰富反馈。我们非常希望能获得前 0.1%（P99.9）水平的专业反馈，以使模型达到像人类一样出色。但我认为这并非不可逾越的难题。它需要基础模型的持续扩展，以及专注度——来自认为这是一个重要且值得解决的问题的研究实验室的专注。而我在团队中所做的事情之一，就是让这成为 OpenAI 的重点领域和优先事项。我认为由于这两者的结合，我有信心我们在 2027 年会取得巨大进展。
<details><summary>Original English</summary>
>> Yeah.
 Um


I
 would
 say
 that
 like
 up
 until
 date,
 the


vast
 majority
 of
 applications
 of
 AI
 in


finance
 have
 been
 really
 focused
 on
 I


would
 say
 like
 the
 junior
 analyst's


work.
 Um


and
 I
 think
 that's
 I
 think
 that's
 for


two
 reasons.
 One
 is


you
 have
 to
 build
 the
 product
 based
 on


the
 like
 capabilities
 of
 the
 model
 of


today.
 And
 so,
 if
 you
 look
 at
 the


capabilities
 of
 the
 model
 today,
 they're


really
 quite
 good
 at
 taking
 pretty


concrete
 instructions
 of
 what
 to
 do


and
 kind
 of
 executing,
 right?
 So,
 build


me
 a
 slide,
 I
 want
 it
 to
 look
 this
 way,


you
 know,
 make
 it
 look
 good,
 use
 our


template,
 these
 types
 of
 things.
 The


model's
 quite
 capable
 of
 doing
 those


things
 and
 so
 therefore,
 we've
 built


product
 experiences
 around
 that.
 Um
 and


the
 other
 thing
 I'll
 call
 out
 is
 um


there
 is
 a
 strong
 preference
 to
 make
 the


model
 good
 at
 things
 that
 humans
 are
 not


good
 at
 or
 don't
 like
 to
 do,
 right?
 And


so,
 uh
 human
 you
 know,
 most
 humans
 I


talked
 to
 there's
 obviously
 exceptions,


but
 a
 lot
 of
 the
 humans
 I
 talked
 to
 like


um


humans
 I
 talked
 to
 people
 I
 talked
 to.


Um
 [laughter]


uh
 you
 know,
 they
 really
 don't
 like


building
 Excel
 models.
 It's
 a
 tedious


kind
 of
 work
 and
 it's
 very
 detail


oriented,
 it's
 easy
 to
 get
 wrong.
 And


similarly
 with
 slides.
 Um
 you
 know,


you're
 you're
 copying
 logos,
 you're


placing
 them
 very
 precisely
 on
 a


specific
 part
 of
 the
 page.
 That's
 very


tedious
 work
 that
 a
 lot
 of
 people
 don't


like
 to
 do.
 And
 so,
 that's
 been
 part
 of


the
 impetus
 for
 us
 to
 go
 and
 focus
 on


some
 of
 these
 tasks,
 right?
 It's
 a


combination
 of
 two
 of
 those
 things.


There's
 the
 like
 existing
 model


capability
 is
 pretty
 good
 at
 uh
 certain


types
 of
 task
 and
 also
 human
 preferences


of
 what
 they
 like
 to
 do
 and
 not
 like
 to


do
 helps
 drive
 the
 direction
 of
 the


product
 as
 well,
 right?
 It's
 a


combination
 of
 those
 two
 things.
 Um


I
 think
 that
 like
 we've
 solved
 a
 lot
 of


the
 low-hanging
 fruit
 of
 those
 two


things.
 And
 so,
 going
 into
 2027,
 we're


going
 to
 start
 to
 move
 up
 the
 stack,


right?
 We're
 going
 to
 go
 from
 the
 task


that
 a
 junior
 analyst
 can
 do
 to
 some
 of


the
 tasks
 that
 an
 associate
 can
 do
 to


some
 of
 the
 tasks
 that
 an
 MD
 would
 do


and
 move
 up
 that
 chain.
 And
 as
 you
 move


up
 the
 chain,
 what
 I
 would
 say
 is
 the


objectives
 become
 much
 fuzzier.
 It
 goes


from
 this
 is
 clearly
 a
 good
 or
 bad


slide,
 or
 something
 that
 we'd
 put
 in


front
 of
 a
 client
 or
 not,
 to
 well,
 I


don't
 know
 if
 this
 investment
 idea
 is


good.
 And
 it's
 And
 it
 would
 take
 me,
 you


know,
 3
 years
 of
 waiting
 to
 really
 be


able
 to
 give
 you
 a
 a
 clear
 concrete


answer
 of
 like
 what
 the
 market
 has
 done.


And
 so
 the
 objectives
 start
 to
 become


fuzzier.
 And
 so
 the
 the
 way
 you
 go
 about


training
 the
 model,
 and
 the
 way
 you


think
 about
 how
 to
 make
 the
 model


better,
 those
 things
 becomes
 more


difficult.
 It
 becomes
 more
 difficult


from
 a
 research
 perspective.
 And
 so
 um


but
 it's
 not
 impossible,
 is
 what
 I
 would


say.
 And
 so
 what
 it
 takes
 is
 a
 lot
 of


research
 focus.
 It
 takes
 a
 lot
 of


wonderful
 data.
 It
 takes
 a
 lot
 of


feedback
 from
 experts
 in
 the
 field.
 We


really
 want
 to
 get
 the
 the,
 you
 know,


the
 P99.9
 type
 of
 feedback
 uh
 to
 make


the
 model,
 you
 know,
 as
 good
 as
 humans.


But
 I
 don't
 think
 it's
 an
 insurmountable


problem.
 And
 I
 And
 And
 what
 it
 takes
 is


continued
 scaling
 of
 the
 base
 model,
 and


focus.
 Focus
 from
 the
 research
 labs
 who


think
 that
 this
 is
 an
 important
 problem


to
 go
 solve.
 And
 one
 of
 the
 things
 that


I'm
 doing
 at
 uh
 on
 my
 team
 is
 making


this
 a
 area
 of focus
 and
 priority
 for


OpenAI.
 And
 And
 I
 think
 because
 of
 the


combination
 of
 those
 two
 things,
 I
 feel


confident
 we'll
 make
 a
 lot
 of
 strides
 in


2027.
</details>

### 金融评估基准的痛点与重塑

>> 你对现有的金融评估基准有什么看法吗？我认为我们目前仍处于“数字上是否准确”的阶段。你如何看待构建自己的评测标准并加入品味维度？我认为这也是对从事该领域的人员构建自身评估基准的一个公开倡议。紧接着的一个问题是，你提到为当下的模型构建系统，但你也对未来做出了很多预测。你在今天为人们构建的金融服务中如何设置安全防护栏、限制和校验，以便他们确信系统不会失控？
<details><summary>Original English</summary>
>> Do
 you
 have
 any
 comments
 on
 any
 of
 the


current
 financial
 benchmarks?
 So,
 I


think
 we're
 still
 in
 the
 state
 of,
 you


know,
 uh
 does
 this
 check
 out


numbers-wise?
 Uh
 how
 do
 you
 think
 about


making
 your
 own,
 adding
 in
 taste?
 Um
 I


think
 this
 is
 also
 an
 open
 call
 for


people
 working
 in
 this
 space
 to
 work
 on


their
 own
 benchmarks.
 And
 a
 sort
 of


follow
 along
 to
 that
 is,
 you
 said
 build


for
 build
 systems
 for
 models
 today,
 but


you
 also
 give
 a
 lot
 of
 predictions
 for


the
 future.
 Um
 how
 do
 you
 put


guardrails,
 limitations,
 um


checks
 on
 financial
 services
 that
 you


build
 for
 people
 today,
 just
 so
 they're


confident
 in,
 you
 know,
 this
 is
 not
 like


going
 out
 off
 the
 rails?
</details>

>> 是的，有道理。我们来谈谈评估（evals）。评估确实是我非常关注的事情，我花了很多时间在评估上。

我想和大家分享的一个先验认知是：构建一个优秀的评估基准极其困难。对于以前没有做过评估的人来说，这一点并不显而易见。要构建一个真正能与你实际想要衡量的技能或能力高度相关的评估基准，是非常困难的。因为你整合出来的任何内容，都只是该能力的某种代理指标（proxy），对吧？而且它往往只是一个维度。这是其一。

其二，想要把标准答案（answer key）或者批改方式弄正确，是非常繁琐的。如果你批改答案的方式不正确，这个评估基准就非常容易被刷榜攻破（hack），也非常容易发生奖励欺骗（reward hack）。因此，你可能在评估基准上获得了非常高的分数，但在你真正想要衡量的底层技能或目标上表现却极其糟糕，对吧？

所以我分享的先验认知是：评估真的很难，不仅在金融领域如此，在所有领域都是如此。我认为目前还没有一个真正适用于金融工作的优秀评估基准。以前存在一系列先前的工作。我提一下我们之前做过的一些工作，比如 GDP 评估（GDP eval），那是在知识工作领域更广泛的评估。如果大家看 Astra 的发布公告，我们其实没有谈及 GDP 评估。我们知道那个评估基准已经完全饱和了，而未饱和的部分基本上已经失效了，对吧？所以我们实际上不再对其进行报告，也不再追踪它。

因此，对于 GPT-6 Astra 来说，棘手的事情之一在于：我们没有过多谈论金融评估。我们内部有一些评估指标，但当时没有谈太多，也没有对外分享；它们很快就会公布。但当时没有一个很好的方式让我们在这些评估基准上展示在金融任务上的进展。

这里面有一些很有意思的现象：我认为在评估中存在一种偏差，即如果数字看起来很好，研究人员就会默认模型变好了，而不会去深究调查；但如果模型能力大幅提升，而评估数据看起来很差，或者没有达到预期的增长幅度，研究人员才会去调查，对吧？所以在这些评估基准的调查中存在着这样一种内置偏差。

类似的事情在 GPT-6 上就发生过：我们在金融评估集上运行了 GPT-6，但数字并没有太大变化。我们心想：“咦，这是怎么回事？让我们来看看这个评估。”我们深入研究了这些不同的评估基准，发现很多地方都是损坏失效的。基本上我们发现我们已经把评估刷饱和了，而做错的题目要么是由于标准答案错误，要么是提示词说明不清，要么就是评估本身的其他缺陷导致的。

说了这么多，我想表达的是：我的团队目前正在做的事情之一，就是尝试构建一个更好的评估基准，它能够真正预测实现该特定职业工作自动化的能力。理念就是，我们将会推出类似于投资银行评估（investment banking eval）的标准，如果在这个评估中表现优异，就意味着你大概率能够自动化投资银行初级分析师的大量工作。
<details><summary>Original English</summary>
>> Yeah,
 makes
 sense.
 Um
 let's
 Yeah,
 let's


talk
 a
 little
 bit
 about
 evals.
 Uh
 evals


is,
 yeah,
 something
 near
 and
 dear
 to
 my


heart.
 I
 spend
 a
 lot
 of
 time
 working
 on


evals.
 I
 would
 say
 that
 um


the
 like
 um
 the
 prior
 that
 I
 would
 share


with
 people
 is
 building
 a
 good
 eval
 is


incredibly
 hard.
 Peop-
 Pe-
 you
 know,


that's
 not
 obvious
 to
 people
 who
 haven't


worked
 on
 an
 eval
 before.
 Um
 to
 build
 an


eval
 that
 actually
 like
 correlates
 with


the
 thing
 that
 you're
 actually
 trying
 to


measure,
 like
 the
 skill
 that
 you're


trying
 to
 measure,
 capability
 you're


trying
 to
 measure,
 very
 difficult.
 Um


because
 whatever
 you
 put
 together
 is


just
 a
 proxy
 for
 whatever
 that
 thing
 is,


right?
 And
 it's
 just
 one
 dimension.
 So,


that's
 one.
 Two
 is
 it's
 very
 tedious
 to


get
 the
 answer
 key
 or
 the
 way
 that
 you


grade
 this
 correctly.
 And
 if
 you
 don't


get
 the
 way
 that
 you
 get
 you
 grade
 the


answers
 correctly,
 it's
 a
 eval
 that's


very
 easy
 to
 hack
 and
 very
 easy
 to


reward
 hack.
 And
 therefore,
 you
 know,


you
 could
 score
 very
 highly
 on
 the
 eval,


um
 but
 actually
 do
 really
 poor
 on
 the
 on


the
 actual
 underlying
 skill
 or
 objective


that
 you're
 trying
 to
 measure,
 right?


And
 so,
 the
 the
 the
 like
 prior
 that
 I


will
 share
 is
 evals
 are
 really
 hard,
 um


not
 just
 in
 financial
 work,
 but
 just


across
 the
 board.
 And
 um
 what
 I
 would


say
 is
 uh
 we
 don't
 think
 that
 there's
 a


really
 good
 eval
 today,
 um
 for
 financial


um
 work.
 Um
 there's
 a
 bunch
 of
 existing


prior
 work.
 I'll
 I'll
 reference
 some
 of


the
 work
 that
 we
 did,
 which
 is
 a
 GDP


eval,
 um
 which
 is
 like
 a
 little
 bit
 more


broadly
 in
 knowledge
 work.
 Um
 if
 you


guys
 look
 at
 the
 Astra
 announcement,
 you


know,
 we don't
 talk
 about
 GDP
 eval.
 Um


we
 we
 know
 that
 the
 eval
 is
 completely


saturated,
 uh
 and
 that
 it's
 uh
 there's
 a


and
 the
 pieces
 that
 are
 not
 saturated


are
 essentially
 broken,
 right?
 And
 so,


we
 actually
 don't
 report
 on
 that,
 we


don't
 track
 it
 anymore.
 And
 so,
 one
 of


the
 tricky
 things
 for
 um
 uh
 GPT-6
 Astra


was
 um
 we
 didn't
 talk
 a
 whole
 lot
 about


financial
 evals.
 We
 have
 some
 internally


that
 we
 didn't
 talk
 too
 much
 about
 and


didn't
 want
 to
 share
 at
 the
 time
 yet.


They're
 coming.
 Um
 but
 it
 was
 there
 was


no
 good
 way
 for
 us
 to
 show
 progress
 uh


on
 financial
 tasks
 on
 these
 evals.
 Um


there's
 a
 funny
 like
 funny
 things
 like
 I


think
 there's
 this
 bias
 in
 evals
 where


if
 the
 numbers
 look
 good,
 the


researchers
 assume
 that
 the
 model's


gotten
 better
 and
 they
 don't
 investigate


it.
 If
 the
 model
 if
 the
 you
 made
 a
 much


more
 capable
 model
 and
 the
 eval
 numbers


look
 bad
 or
 haven't
 increased
 in
 the
 the


scale
 that
 you
 want,
 then
 you
 go


investigate,
 right?
 So,
 this
 is
 kind
 of


like
 bias
 baked
 into
 uh
 investigation


these
 evals.
 Something
 like
 this


happened
 with
 GPT-6
 where
 we
 we
 ran


GPT-6
 on
 a
 set
 of
 on
 financial
 evals
 and


the
 numbers
 didn't
 really
 change
 much.


We're
 like,
 "Oh,
 like
 what's
 going
 on


here?
 Let's
 take
 a
 look
 at
 this
 eval."


We
 we
 we
 did
 a
 deep
 dive
 into
 these


different
 evals
 and
 lots
 of
 things
 were


broken.
 Uh
 we
 like
 the
 basically
 we


found
 that
 we
 had
 saturated
 the
 evals


and
 the
 questions
 that
 we
 were
 getting


wrong
 were
 driven
 by
 incorrect
 answer


keys,
 um
 poorly
 specified
 prompts,
 or


just
 some
 other
 flaw
 with
 the
 eval.
 Um


and
 so
 all
 that
 to
 say
 like
 one
 of
 the


things
 that
 my
 team
 is
 working
 on


currently
 is
 to
 try
 to
 build
 a
 much


better
 eval
 that
 actually
 predicts
 the


ability
 to
 automate
 the
 work
 of
 that


specific
 profession.
 And
 so
 yeah,
 and
 so


the
 idea
 is
 like
 we'll
 have
 something


like
 an
 investment
 banking
 eval
 that


predicts,
 you
 know,
 if
 you
 score
 well
 on


this
 eval,
 you
 could
 probably
 automate
 a


lot
 of
 the
 work
 of
 a
 junior
 analyst
 uh


in
 investment
 banking.
</details>

### 团队招聘与结语

>> 我们很快就要结束了。我想问一下，对于金融领域的人士以及 Latent Space 的受众，你们有什么呼吁吗？你们团队可能正在招聘，作为最后的分享，大家可以如何为你提供帮助？
<details><summary>Original English</summary>
>> We
 got
 to
 wrap
 here
 soon.
 I
 want
 to
 ask


uh
 any
 callouts
 for
 people
 in
 the


finance
 space,
 the
 Latent
 Space


audience,
 uh
 your
 team
 is
 probably


hiring,
 but
 last
 thing
 to
 put
 out
 there,


how
 how
 can
 people
 be
 be
 helpful
 to
 you?
</details>

>> 太好了。首先，请大家关注 ChatGPT 金融服务版（ChatGPT Financial Services）。这是一款企业级产品，但我们正在非常努力地让 Pro 订阅计划上的更多专业消费者（prosumers）也能使用它，希望很快能在那方面带来一些令人兴奋的发布。

第二，是的，我的团队正在招人。我们的产品获得了极好的客户反馈，因此我们正在迅速招聘并扩张团队。这是一个非常多元化的团队，拥有许多不同的岗位，我想快速指出其中的几个：

显然有标准的前端、后端工程岗位，也就是传统的产品构建开发，这是其一；第二，我们非常欢迎出色的产品经理加入。在某种程度上，我认为优秀的产品管理是赢得这一领域的主要瓶颈，因此我们正努力在投资银行、股票研究、资产管理等各个领域招聘优秀的产品经理；

另外我想特别强调的一个职位是，我们正在招聘所谓的“领域专家”（subject matter expert）。这真的很重要。我们在编程方面做得很好的一点是：训练模型并改进模型的人本身就理解优秀的代码是什么样的，对吧？在我们提升模型能力的阶段，这对我们是一个巨大的助力。但在让模型更懂金融方面，我们并没有这种优势。因此，我们正在组建团队并试图招聘大量能够带来金融专业知识的人才，与工程师、研究人员和产品经理合作，使模型和产品在你的具体专业领域中变得更出色。如果这些岗位中有任何一个与你契合，我非常推荐大家联系我。我在 LinkedIn 上，我们也在招聘页面上发布了这些职位，非常容易找到。
<details><summary>Original English</summary>
>> Yeah,
 wonderful.
 Well,
 I
 would
 say
 like


first
 and
 foremost
 like
 please
 check
 out


Chat
 GPT
 Financial
 Services.
 Um
 it
 is
 an


enterprise
 product,
 but
 we're
 trying


very
 hard
 to
 make
 it
 available
 to
 more


uh
 prosumers
 on
 the
 pro
 plan
 and
 so


hopefully
 we'll
 have
 some
 cool


announcements
 there.
 Um
 two,
 yes,
 my


team
 is
 hiring.
 Uh
 we're
 seeing


incredible
 uh
 customer
 traction
 with
 the


product
 and
 uh
 because
 of
 that
 we're


hiring
 and
 scaling
 the
 team
 rapidly.


It's
 a
 very
 diverse
 team
 with
 lots
 of


different
 roles
 and
 so
 I
 just
 want
 to


call
 out
 a
 few
 of
 them
 very
 quickly.
 Um


there's
 obviously
 the
 the
 standard
 uh


front
 end
 back
 end
 uh
 engineering,
 so
 um


kind
 of
 traditional
 product
 building.
 So


that
 was
 one.
 Two,
 we're
 very
 much
 looking


for
 wonderful
 product
 managers.
 I
 think


in
 some
 ways
 uh
 great
 product
 management


is
 the
 the
 main
 bottleneck
 in
 trying
 to


go
 win
 in
 this
 space
 and
 so
 we're
 trying


to
 hire
 wonderful
 product
 managers
 in


investment
 banking,
 equity
 research,


asset
 management,
 uh
 you
 know,
 across


the
 board
 we're
 we're
 trying
 to
 hire


product
 managers.
 Uh
 and
 then
 the
 other


role
 that
 I
 want
 to
 give
 a
 special
 shout


out
 to
 is
 we're
 hiring
 someone
 we
 call
 a


subject
 matter
 expert.
 Um
 and
 you
 know,


it's
 really
 important.
 Uh
 one
 of
 the


things
 that
 we
 did
 well
 in
 in
 coding
 is,


you
 know,
 the
 the
 people
 that
 were


training
 the
 models
 and
 making
 them


better
 understood
 what
 good
 code
 looks


like,
 right?
 And
 that
 was
 a
 huge


tailwind
 for
 us
 as
 we're
 making
 the


models
 better
 at
 these
 things.
 We
 don't


have
 that
 advantage
 when
 it
 comes
 to


making
 the
 models
 models
 better
 at


finance.
 And
 so
 we're
 we're
 building
 out


and
 trying
 to
 hire
 a
 lot
 of
 folks
 that


are
 able
 to
 bring
 that
 financial


expertise
 and
 work
 with
 the
 engineers,


work
 with
 the
 researchers,
 work
 with
 the


product
 managers
 to
 make
 the
 model
 and


the
 product
 better
 in
 your
 specific


fields.
 And
 so
 if
 any
 of
 those
 resonates


with
 you,
 like
 I
 highly


you
 know,
 recommend
 that
 you
 reach
 out


to
 me.
 I'm
 available
 on
 LinkedIn.
 We


also
 have
 these
 job
 listings
 posted
 on


our
 careers
 page.
 It's
 pretty
 easy
 to


find.
</details>

>> 太好了。你回答了我的问题。我本来想问什么时候能玩到这个产品，不过它即将面向 Pro……
<details><summary>Original English</summary>
>> Great.


Well,
 you
 answered
 my
 question.
 I
 was


going
 to
 ask
 when
 I
 when
 can
 I
 have
 a


play
 with
 this,
 but
 it
 is
 coming
 to
 Pro


Pro
 Pro
 Pro
 Pro
</details>

>> 非常努力地让更多人能够使用它。
<details><summary>Original English</summary>
>> very
 hard
 to
 make
 it
 available
 to
 more


people.
</details>

>> 这是非常典型的 OpenAI 风格，先为企业端开发，然后逐步下沉到常规模型中，来到 Pro 计划。因此我预计对于大众日常使用来说，未来在控制台或日常操作方面都会变得越来越好。
<details><summary>Original English</summary>
>> very
 common
 opening
 eye
 stuff,
 you
 know,


it
 makes
 sense
 you
 make
 stuff
 for


enterprise
 and
 then
 this
 trickles
 down


the
 the
 regular
 models.
 It
 comes
 to
 Pro


plan.
 So
 I
 expect
 for
 your
 general
 usage


down
 the
 line
 it'll
 get
 better
 at


console
 stuff.
</details>

>> 非常棒。非常高兴你能来。大家可以去看看主题演讲。你分享了很多内容，做出了很好的预测，也谈到了一些干货，比如我们解决了预训练问题。我就留下这些线索供大家前去观看。非常感谢你的参与。
<details><summary>Original English</summary>
>> Awesome
 ball.
 Very
 excited
 to
 have
 you.


Check
 out
 the
 keynote.
 You
 gave
 a
 lot.


You
 gave
 good
 predictions.
 You
 talked
 a


little
 bit
 about
 some
 juicy
 we
 fixed


pre-training
 issues.
 So
 I
'll
 leave


breadcrumbs
 for
 you
 guys
 to
 go
 watch,


but
 thanks
 for
 joining.
</details>

>> 是的，太棒了。非常感谢。
<details><summary>Original English</summary>
>> Yeah,
 awesome.
 Thank
 you
 so
 much.
</details>