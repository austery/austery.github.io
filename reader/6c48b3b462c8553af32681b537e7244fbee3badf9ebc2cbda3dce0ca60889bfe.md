---
author: AI Engineer
date: '2026-11-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kIlVNGZZr8o
speaker: AI Engineer
tags:
  - autonomous-agent
  - cloud-computing
  - data-governance
  - financial-technology
  - process-automation
title: Nori Agentic：利用云端 Agent 重构金融证券主数据与后台数据核验
summary: Noriagentech 联合创始人 Amol Kapoor 与 Cliff 探讨了私募资产增长对资产管理机构证券主数据（SecMaster）带来的数据治理挑战。通过引入在云端或本地模型运行的自主 Agent，系统在底层数据变动时自动检索文档、生成引用与建议，并经由人工审核，将单次变更核对耗时从 1 小时压缩至 5 分钟。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Amol Kapoor
  - Cliff
companies_orgs:
  - Noriagentech
products_models: []
media_books: []
status: evergreen
---
### 私募资产激增与金融后台面临的数据挑战

**>>**: 大家好。非常非常高兴能来到 AIE 纽约的舞台。这真的很棒。嗯，今天我们要聊一聊 Agent 化的证券主数据库（SecMaster）。不过在开始自我介绍之前，我想先聊聊最近一直萦绕在我心头的一件事，尤其是在我准备这次演讲的时候，那就是——金融变得有点奇怪了，对吧？比如在我成长的年代，金融主要指的是公开市场，你知道的，交易大厅、敲钟仪式之类的。现在情况已经完全不是那样了。大量资本投资涌入了私募资产。其中一些数字对我来说简直令人震惊。显然在去年，也就是 2025 年，二级市场交易量达到了 2400 亿美元，比 2024 年增长了 50%。我敢肯定在 2026 年这个数字还会更多。而且人们现在预测，到 2030 年——距离现在只有 3 年了——我们将迎来 32 万亿美元的另类资产管理规模。

现在，为什么会发生这种情况？为什么这会成为金融界的重大焦点？嗯，部分原因似乎是因为 AI 越来越成为更广泛经济领域中唯一的增长点。所以越来越多的人在持有并投资于所有为 AI 领域提供支持的基础要素。那就是土地、能源、数据中心、GPU 集群。当然还有二级市场份额，对吧？所有人都在紧握着 OpenAI 和 Anthropic 的二级市场股权。它们无处不在。所有这些私营 AI 公司，每个人都在试图获得它们。

但这不仅是一个 AI 的故事。这也与监管有关，并且是一个关于追求超额收益（Alpha）的故事。

高增长型公司发现上市的理由越来越少了。他们宁愿再去融个 F 轮。创始人能保留更多控制权，需要向政府提交的文书工作也更少。而且如果有那些资金雄厚的庞大机构正在接管市场、榨干公开市场的油水，那么你就只能开始去其他地方寻找超额收益边缘了。

就像对所有事情的看法一样，我认为马特·莱文（Matt Levine）说得最透彻。他其实在一年前就写过这个。私募投资机构已经变得极其庞大，而公开市场与私募市场之间的法律界限已经变得远没有那么重要了。如果经济中越来越大的份额存在于私募资产中，投资者就无法仅仅依靠指数投资了。如果市场有一半实际上是私营公司，你不可能通过购买所有公开上市的股票来获得全市场的回报。因此，你陷入了这样一个循环：对私募资产的投资增多，这意味着更多的人必须投资于私募资产，仅仅为了确保他们能够获得来自更广阔市场的回报。

现在，有一件非常令人头疼的事情就是处理私募资产。这实际上非常非常困难。你如何管理私募资产？你如何追踪诸如你拥有多少股份，或者你的行权价是多少？我的意思是，我自己就是个初创公司创始人，哪怕只是为了我自己那一小点股权，我都觉得很头疼。而如果你投资了水力发电厂旁边的一块土地，事情就变得非常奇怪了。所有关于你付了多少钱、你拥有什么权利的信息都放在哪里呢？

嗯，很遗憾，它存在于 PDF 之中。它在 Box 文件夹里，或者在 Outlook 电子邮件中。它在 Zoom 通话记录里。有时候，它是在俯瞰哥伦布圆环的酒吧里、潦草签在餐巾纸上的字迹。

欢迎来到管理私募资产数据的噩梦世界，而这正是这个房间里越来越多的人以及纽约的大多数人过去几年一直在应对的现实。

我叫 Amol Kapoor。我是一家名为 Noriagentech 的公司的 CEO。我们构建云端 Agent，今天我们将讨论如何使用云端 Agent 以及通用的 AI，来让管理、记录和审计一家公司的投资变得更容易。特别是，一家公司的证券主数据库（security master database）。现在谈谈我的背景，实际上我一直从事 AI 领域。我做 AI 工程师大约有 12 年了。呃，其中有四年半是在 Google 度过的。所以有意思的是，我并不是解释什么是证券主数据（sec master）的最佳人选。但是，我非常荣幸能与我的 CTO 兼联合创始人 Cliff 一起同台，他确实在金融后台业务领域工作过一段时间，由他在我们深入探讨 AI 如何解决这些问题之前，来向大家稍微介绍一下什么是证券主数据。
<details><summary>Original English</summary>
**>>**: Hi
 everybody.
 It's
 really
 really
 great


to
 be
 here
 on
 stage
 at
 AIE
 New
 York.


This
 is
 kind
 of
 awesome.
 Um
 today
 we're


going
 to
 talk
 a
 little
 bit
 about
 the


Agentech
 SecMaster.
 But
 before
 I
 dive


into
 things
 like
 introductions,
 I
 want


to
 talk
 about
 something
 that's
 been
 on


my
 mind
 recently,
 especially
 as
 I
 was


preparing
 for
 this
 talk,
 which
 is


finance
 has
 gotten
 kind
 of
 weird,
 right?


Like
 when
 I
 was
 growing
 up,
 finance


mostly
 meant
 public
 markets,
 you
 know,


trading
 floors,
 ringing
 bells,
 things


like
 that.
 And
 that's
 not
 really
 what


happens
 anymore.
 There
 has
 been
 a
 huge


influx
 of
 capital
 investment
 into


private
 assets.
 And
 some
 of
 these


numbers
 are
 kind
 of
 staggering
 to
 me.


Apparently
 last
 year,
 there
 were
 $240


billion
 of
 secondaries
 volume
 in
 2025,


which
 is
 up
 50%
 from
 2024.
 I'm
 sure
 in


2026
 it's
 even
 more
 than
 that.
 And


people
 are
 now
 forecasting
 that
 we're


going
 to
 do
 $32
 trillion
 of
 alternative


assets
 under
 management
 by
 2030,
 which


is
 only
 3
 years
 away.


Now,
 why
 is
 that
 happening?
 Why
 is
 this


the
 big
 story
 in
 the
 finance
 world?


Well,
 some
 of
 this
 is
 because
 AI
 seems


to
 increasingly
 be
 the
 only
 growth
 area


in
 the
 broader
 economy.
 So
 more
 and
 more


people
 are
 holding
 on
 to
 and
 investing


into
 all
 of
 the
 things
 that
 feed
 the
 AI


world.
 That's
 land,
 energy,
 data


centers,
 GPU
 clusters.
 And
 of
 course


secondaries,
 right?
 Everybody
 is
 holding


on
 to
 OpenAI
 and
 Anthropic
 secondaries.


They're
 everywhere.
 All
 of
 these
 private


AI
 companies,
 everybody's
 trying
 to
 get


a
 hold
 of
 them.


But
 it's
 not
 just
 an
 AI
 story.
 Some
 of


this
 is
 also
 a
 regulation
 story
 and
 a


story
 about
 seeking
 alpha.


High
 growth
 companies
 are
 finding
 less


and
 less
 reasons
 to
 go
 public.
 They


would
 rather
 just
 raise
 a
 series
 F.
 More


control
 for
 the
 founders,
 less
 paperwork


to
 do
 with
 the
 government.
 And
 if
 there


are
 these
 massive
 well-funded
 firms
 that


are
 taking
 over
 and
 squeezing
 the
 juice


out
 of
 public
 markets,
 well,
 you're
 just


going
 to
 start
 looking
 for
 edge


somewhere
 else.


As
 with
 all
 things,
 I
 think
 Matt
 Levine


said
 it
 best.
 He
 actually
 wrote
 this
 a


year
 ago.
 Private
 investment
 firms
 have


become
 huge,
 and
 the
 legal
 distinctions


between
 public
 and
 private
 markets
 have


become
 way
 less
 important.
 If
 an


increasing
 share
 of
 the
 economy
 is
 in


private
 assets,
 investors
 aren't
 able
 to


just
 index.
 You
 can't
 get
 the
 market


return
 by
 buying
 every
 public
 stock
 if


half
 of
 the
 market
 is
 actually
 in


private
 companies.
 So,
 you
 end
 up
 with


this
 cycle.
 There's
 more
 investment
 in


private
 assets,
 which
 means
 more
 people


have
 to
 invest
 in
 private
 assets
 just
 to


make
 sure
 that
 they're
 getting
 the


returns
 from
 the
 wider
 market.


Now,
 one
 thing
 that's
 really
 frustrating


is
 dealing
 with
 private
 assets.
 It's


actually
 really,
 really
 hard.
 How
 do
 you


manage
 private
 assets?
 How
 do
 you
 keep


track
 of
 things
 like
 how
 many
 shares
 you


own
 or
 what
 your
 strike
 price
 is?
 I


mean,
 I'm
 a
 startup
 founder,
 and
 I
 find


that
 frustrating
 just
 for
 my
 own
 little


bit
 of
 stock.
 And
 if
 you
 invest
 in
 a


plot
 of
 land
 next
 to
 a
 hydro
 plant,


things
 get
 really
 weird.
 Where
 is
 all
 of


the
 information
 about
 how
 much
 you
 paid


and
 what
 your
 rights
 are?


Well,
 unfortunately,
 it's
 in
 PDFs.
 It's


in
 a
 box
 folder
 or
 in
 an
 Outlook
 email.


It's
 in
 a
 Zoom
 call
 transcript.


Sometimes,
 it's
 on
 a
 napkin
 with
 a


hastily
 scribbled
 signature
 from
 a
 bar


overlooking
 Columbus
 Circle.


Welcome
 to
 the
 nightmare
 world
 that
 is


managing
 private
 asset
 data,
 something


that
 more
 and
 more
 people
 in
 this
 room


and
 in
 New
 York
 in
 general
 have
 been


dealing
 with
 over
 the
 last
 couple
 of


years.


My
 name
 is
 Amol
 Kapoor.
 I
 am
 the
 CEO
 of


a
 company
 called
 Noriagentech.
 We
 build


cloud
 agents,
 and
 today
 we're
 going
 to


talk
 about
 how
 you
 can
 use
 cloud
 agents


and
 AI
 in
 general
 to
 make
 it
 easier
 to


manage,
 record,
 and
 audit
 a
 company's


investments.
 In
 particular,
 a
 company's


security
 master
 database.
 Now,
 my


background
 is
 actually
 in
 AI.
 I've
 been


an
 AI
 engineer
 for
 about
 12
 years.
 Uh


four
 and
 a
 half
 of
 those
 years
 were
 at


Google.
 So,
 funny
 enough,
 I
 am
 not
 the


best
 person
 to
 actually
 talk
 about
 what


a
 sec
 master
 is.
 But,
 I'm
 very
 lucky
 to


be
 joined
 by
 my
 CTO
 and
 co-founder


Cliff,
 who
 actually
 has
 spent
 some
 time


in
 back
 office
 finance
 here
 to
 talk
 to


us
 a
 little
 bit
 about
 what
 a
 sec
 master


is
 before
 we
 dive
 into
 how
 AI
 can
 solve


those
 problems.
</details>

### 什么是证券主数据库（SecMaster）

**>>**: 很好。我认为在

在我们讨论为什么这是一个难题之前，了解一下全局背景会有所帮助。我们可以先谈谈公开市场股票这种更简单的例子，然后再来解决私募资产带来的复杂性。

目前，每一家资产管理公司都在依托证券主数据库（SecMaster）运行。

那么，让我们来定义一下它。

资产管理机构需要知道在他们的投资范围（investment universe）或可交易范围（tradeable universe）内存在什么。

这是后台的关键组成部分，它将工程、运营和数据汇集在一起。

你可以将其视为一个主数据库，包含了代表他们所持有资产的所有证券或金融工具。

对工程师来说，你可以把它看作类似任何主数据库一样，它是真实数据的单一来源（source of truth），而且通常是大多数业务关键型分析的起点。在投资领域，这些分析体现为风险管理、损益（P&L）核算、合规审计，以及所有对资产管理机构至关重要的职能。

假设两个不同的数据源对某些特定数值存在分歧。

理想情况下，

这种冲突在进入证券主数据库之前就会被标记出来。

你可以回溯到数据源头，准确找出特定数值上的分歧点；或者有时这是一个逻辑问题，你可以检查每一方是如何映射到那只特定证券上的。因此，如果处理得当，上游的问题在污染我们刚才谈到的所有业务关键分析之前就会被修复。

所以我更愿意将其视为一个组织层面的基石（primitive），定义了你如何处理数据，从而赋能公司内部所有的数据使用者。

这一层将数据生产者与数据使用者隔离开来。因此，无论你是在包含许多不同数据表的复杂奖章式数据湖仓（medallion data lakehouse）上工作，还是它仅仅是一个单一番茄式的反规范化（denormalized）真实数据源，

这里都是你可以执行数据标准、可见性和质量检查的枢纽关口。

因此，取决于你在哪里投资，你需要运用这个简单的概念，并将其与世界上投资于该特定资产类别的其他所有人进行匹配——

这些人可能说着不同的语言，使用不同的货币进行结算，并在不同的监管体系下运作。

因此，对于公开资产，你可以受益于几个不同的中心化节点。

为了满足交易所和交易的需求，你有数据提供商来

提供不同的标识符。这些可能包括彭博的代码（FIGI）或伦敦证券交易所的 RIC 代码。

此外还有监管方面的需求。而这一中心化节点促使编码机构提供另一套标识符，例如 ISIN 或 CUSIP。

因此，你能够利用这些信息将任何人对特定资产的视角映射到你自己的视角中。这是你理解自身持仓的唯一方式，例如进行风险建模、汇报持仓、结合另类数据、创建财务模型。

我们来看一个非常简单的例子。

你持有某只公开发行的大盘股，比如 Google。

首先如果你看股票代码，这是 GOOG 还是 GOOGL？因为同一家交易所有两个不同的股份类别在交易。

假设你需要关联一些仅存在于法定实体层级的数据。那么，如果你是基于 ISIN 进行索引的，现在你就无法进行关联了。

或者可能你只交易一种股份类别且只持有一种，但你需要跨多个不同的交易所进行交易，因为你有针对不同基金的需求，为了满足多个基金或多个投资者的需求。

所以，这本身就已经变得相当复杂了。

对工程师来说，我喜欢把这比作一个处理日期时间的库。

当有人很好地解决了这个问题时，它看起来非常简单。

但是一旦你面临使用一种尚未实现完善日期时间处理的新语言，或者你只需要做一些修改、深入探究其内部工作原理时，就会发现里面全是边缘情况和复杂的本体结构（ontologies）。这就是那个 Google 的例子在实践中可能呈现的样子：这里有一个包含许多行的反规范化表，用来表示我们现在希望能够分析的那一只股票。

因此，如果有数据传入，即使它只包含标识符的一个子集，或者它所处的细粒度与你的证券主数据库不同，代码仍然可以对其进行映射。

有趣的地方就在这里：

如果传入的数据没有规律的标识符，

你该如何映射它？

在第一种情况下，AI 能提供怎样的帮助其实非常明晰，对吧？当数据具有结构时，对其进行推理是非常容易的。

代码 Agent 越来越擅长编写代码，如果你拥有关于公司业务关键数据的黄金标准本体作为源头，
<details><summary>Original English</summary>
**>>**: Great.
 So,
 I
 think
 it's
 helpful
 before


we


before
 we
 talk
 about
 where
 this
 is
 a


hard
 problem,
 I
 think
 we
 should
 get
 a


lay
 of
 the
 land.
 We
 can
 talk
 about
 a


simpler
 example
 with
 public
 equities,


then
 we
 can
 tackle
 some
 of
 the


complexity
 that
 comes
 with
 private


assets.


So,
 every
 asset
 manager
 right
 now


currently
 runs
 on
 a
 sec
 master.


So,
 let's
 define
 that.


Asset
 managers
 need
 to
 know
 what
 exists


in
 their
 investment
 universe
 or
 in
 their


tradeable
 universe.


This
 is
 a
 critical
 piece
 of
 back
 office,


brings
 together
 engineering,
 operations,


and
 data.


You
 can
 think
 of
 this
 as
 just
 a
 master


database
 of
 all
 securities
 or


instruments
 that
 represent
 the
 assets


they're
 holding.


For
 the
 engineers,
 you
 can
 think
 about


this
 like
 any
 master
 database,
 it's
 the


source
 of
 truth,
 and
 usually
 the


starting
 point
 for
 most
 of
 the
 business


critical
 analysis.
 An
 investment
 that


looks
 like
 risk
 management,
 P&L


accounting,
 regulatory
 compliance,


all
 these
 functions
 that
 are
 critical


for
 asset
 managers.


So,
 say
 two
 different
 sources
 of
 data


disagree
 about
 particular
 values.


Ideally,


that
 conflict
 doesn't
 get
 flagged
 before


it
 reaches
 the
 sec
 master.


You
 can
 go
 back
 to
 the
 sources
 and


pinpoint
 either
 the
 divergence
 in
 the


particular
 value,
 or
 sometimes
 it's
 a


logic
 problem
 and
 you
 can
 examine
 how


each
 one
 maps
 to
 that
 particular


security.
 So,
 when
 done
 correctly,


upstream
 problems
 are
 fixed
 before
 they


contaminate
 all
 the
 business
 critical


analysis
 we
 just
 talked
 about.


So,
 I
 like
 to
 think
 about
 this
 as
 an


organizational
 primitive
 for
 how
 you


handle
 data
 to
 enable
 all
 the
 consumers


of
 data
 at
 your
 company.


This
 layer
 separates
 the
 data
 producers


from
 the
 data
 consumers.
 So,
 whether


you're
 working
 on
 a
 complex
 medallion


data
 lake
 house
 that
 has
 many
 different


tables,
 or
 it's
 just
 a
 single


denormalized
 source
 of
 truth,


this
 is
 the
 bottleneck
 where
 you
 can


enforce
 the
 standards
 and
 the
 visibility


and
 the
 quality
 checks.


So,
 depending
 on
 where
 you
 invest,


you
 need
 to
 take
 this
 simple
 concept
 and


match
 it
 up
 with
 how
 everyone
 else
 in


the
 world
 who
 invests
 in
 this
 particular


asset
 class,


potentially
 speaking
 different
 languages


languages,
 settling
 in
 different


currencies,
 and
 operating
 in
 different


regulatory
 regimes.


So,
 for
 public
 assets,
 you
 benefit
 from


a
 couple
 different
 points
 of


centralization.


For
 the
 needs
 of
 exchange
 and


transactions,
 you
 have
 data
 vendors
 who


will


provide
 different
 identifiers.
 So,
 these


might
 be
 like
 Bloomberg
 figgies
 or
 LSE


RICS.


Then
 there's
 also
 regulatory
 needs.
 And


though
 that
 point
 of
 centralization


causes
 numbering
 agencies
 to
 offer
 a


different
 set
 of
 identifiers,
 like
 ISINs


or
 CUSIPs.


So,
 you're
 able
 to
 use
 this
 information


to
 map
 anyone's
 view
 of
 a
 particular


asset
 into
 your
 own
 view.
 And
 that's
 the


only
 way
 you
 can
 understand
 your


positions,
 like
 modeling
 risk
 or


reporting
 holdings,
 joining
 alternative


data,
 creating
 financial
 models.


So,
 let's
 take
 a
 very
 simple
 example.


You
 hold
 some
 mega-cap
 publicly
 traded


stock
 like
 Google.


So,
 already
 if
 you
 know
 the
 tickers,


is
 this
 GOOG
 or
 is
 this
 GOOGL?
 Because


there
 are
 two
 different
 share
 classes


traded
 on
 the
 same
 exchange.


Let's
 say
 you
 need
 to
 join
 in
 some
 data


that
 exists
 only
 at
 the
 level
 of
 the


legal
 entity.
 Well,
 if
 you're
 indexing


based
 off
 of
 ISIN,
 now
 you
 can't
 join


that
 anymore.


Or
 maybe
 you
 only
 trade
 one
 share
 class


and
 you
 only
 hold
 one,
 but
 you
 need
 to


trade
 it
 across
 multiple
 different


exchanges
 because
 you
 have
 different


funds
 for
 the
 needs
 of
 multiple


multiple
 funds
 or
 multiple
 investors.


So,
 already
 this
 is
 getting
 pretty


complex.


I
 like
 to
 think
 about
 this
 kind
 of
 like


a
 daytime
 library
 as
 a
 comparison
 for


the
 engineers.


It
 seems
 very
 simple
 when
 someone
 solved


the
 problem
 well.


But
 the
 moment
 you're
 either,
 you
 know,


working
 with
 a
 new
 language
 that
 hasn't


implemented
 good
 daytime
 yet,
 or
 you


just
 need
 to
 make
 some
 modifications
 and


peel
 back
 how
 it
 works
 inside,
 it's
 all


edge
 cases
 and
 complex
 ontologies.
 So,


this
 is
 what
 that
 Google
 example
 might


look
 like
 in
 practice.
 Here's
 a


denormalized
 table
 with
 many
 rows
 for


that
 one
 equity
 we
 want
 to
 uh
 able
 to


now
 analyze.


So,
 if
 some
 data
 comes
 in,
 even
 if
 it


only
 has
 a
 subset
 of
 identifiers
 or


exists
 at
 a
 different
 granularity
 than


your
 Sec
 Master,
 the
 code
 can
 still
 map


it.


So,
 here's
 where
 it
 gets
 interesting.


If
 the
 code
 if
 the
 data
 coming
 in


doesn't
 have
 regular
 identifiers,


how
 do
 you
 map
 it?


It's
 actually
 pretty
 clear
 how
 AI
 helps


in
 the
 first
 case,
 right?
 It's
 very
 easy


to
 reason
 about
 this
 data
 with


structure.


The
 coding
 agents
 are
 increasingly
 good


at
 writing
 code
 and
 if
 you
 have
 the


source
 of
 kind
 of
 gold
 standard
 ontology


about
 the
 business
 critical
 data
 for


your
 company,
</details>

**>>**: [嗤笑]
<details><summary>Original English</summary>
**>>**: [snorts]
</details>

### 私募资产带来的映射断裂

**>>**: AI 可以非常轻松地赋能新的应用场景。

但是在非结构化、可能缺乏标识符的数据源面前，你就背负了巨大的人工核查和人工映射负担。

因此，当私募资产进入证券主数据时，顺畅的处理路径就此中断了。

当你购买 Google 股票时，你知道自己支付了多少，

你知道自己买到了什么，

在进入交易时，每个人都拥有通用的标识符语言可以使用。

设想一下，你要向一家在某些数据中心开发项目附近建设发电厂的公司提供贷款，或者你在该发电厂附近投资土地，

以备将来可能的

呃，自行开发。

进入这笔交易时，不存在大家都认可的统一标识符。

没有人能对你最终可能获得的信息的整体结构进行监管规范。也没有哪家数据供应商提供统一的 API，在其中专门梳理并规划了这些实体的本体结构。

从还款计划到抵押安排，所有这一切都存在于单独的定制协议或补充条款中。它不具备可替代性（not fungible）。

这项资产完全是由这些文档来记录和定义的。

这就很有意思了，因为现在数据几乎是随着资产呈一对一线性增长的，

而扩展证券主数据本身的负担也在持续增加。
<details><summary>Original English</summary>
**>>**: AI
 can
 enable
 new
 use
 cases
 very
 easily.


But
 with
 unstructured,
 potentially
 not


identified
 data
 sources,
 you
 have
 a
 huge


burden
 of
 manual
 verification
 and
 manual


mapping.


So,
 this
 is
 where
 the
 happy
 path
 breaks


down
 when
 private
 assets
 come
 into
 the


Sec
 Master.


So,
 when
 you're
 buying
 the
 Google
 stock,


you
 know
 what
 you're
 paying,


you
 know
 what
 you're
 getting,


and
 going
 into
 the
 transaction,
 everyone


has
 a
 shared
 language
 of
 different


identifiers
 that
 they
 can
 speak.


Let's
 imagine
 you're
 going
 to
 lend
 some


money
 to
 a
 company
 building
 a
 power


plant
 near
 some
 data
 center
 developments


or
 you're
 investing
 in
 land
 near
 the


power
 plant


for
 potential
 future


uh
 development
 itself.


There's
 no
 identifiers
 everyone
 shares


going
 into
 that
 deal.


There
 are
 no
 one
 that
 regulates
 the
 entire


structure
 of
 information
 you
 might
 get


out
 the
 other
 end.
 And
 there's
 no
 one


data
 vendor
 that
 has
 a
 single
 API
 where


they've
 thought
 through
 the
 ontology
 of


these
 entities
 in
 particular.


Everything
 from
 the
 repayment
 schedule


to
 the
 collateralization,
 all
 of
 this


lives
 in
 one-off
 agreements
 or


amendments.
 It's
 not
 fungible.


The
 asset
 is
 captured
 and
 defined


entirely
 by
 the
 documentation.


And
 this
 is
 interesting
 because
 now
 the


data
 scales
 almost
 one-to-one
 with
 the


assets


and
 the
 burden
 to
 scale
 the
 the
 Sec


Master
 itself
 is
 constantly
 increasing.
</details>

### 云端 Agent 的引入与财富 200 强资管案例

**>>**: 很好。那我接着这里继续讲。

Cliff 提出了一个非常好的观点。私募资产在管理上是十足的痛点。它们就是无法很好地适应证券主数据库。但是所有这些信息仍然需要以某种方式被整理汇总。你的审计要求、清洗要求和标准化要求并不会凭空消失。如果说有什么改变的话，实际上是现在变得糟糕得多，因为它的标准化程度太低了。你不能指望负责风险建模的人知道该数据是否就是真实基准（ground truth）。你当然也不希望由他们来逐个查阅并整理你所有的文档。因此，不管怎样，躺在某处 PDF 里的那些数据信息，最终都必须进入你的证券主数据库。

而眼下，这完全是一项极高强度的体力劳动。我的意思是，通常这需要耗费大量的人力和大量的领域专长。顺便我得快速把这个鼠标挪开，它刚才一直挡着我。

好的。

所以，我想用一个具体的例子来说明。我们与纽约本地一家财富 200 强的资产管理公司紧密合作，这也是身处纽约本地的优势之一。他们最近开始持有大量私募资产——谁又不是呢——而这给他们的数据工程团队带来了很多问题，也就是维护他们证券主数据库的那群人。当他们证券主数据库中的任何资产发生变化时，他们必须确保该变更是正确的。因此，他们建立了一套机制：对他们的数据表进行按日维度的变化分析（day-over-day change analysis）。

如果你的表里有 50,000 项资产，而其中每一项资产大概有 200 个字段列，即使低频的变动也会按某种每日节奏频繁发生。

然后，每一个发生变动的单元格都会被发送给一个人工团队去分流处理，因为再次强调，所有这些数据都极其非结构化。它就散落在某些文档之中。

因此，那个团队需要负责查阅文档以及各种数据源，以确定任何给定的变动是有效还是无效，因为上游数据提供商可能会误输入（fat-fingered）某些内容，或者可能会搞错某些信息，或者可能单纯就是数据冲突。

而且我想强调的是，这不仅仅是每一行、每一列，而是字面意义上的每一个单元格。所以，如果一项资产变更了价格，或者资产变更了名称，或者一家公司破产了，或者所有权发生了变更，或者你重新谈判了一份合同等等，该投资范围内的每一个变动，背后平均都要耗费一小时的工时。耗费某个人一小时的时间，一个你付薪水的人，专门去数据堆里摸爬翻找。每个月加起来就是成百上千个小时。几百或几千，抱歉说成了数十万。

那么，既然我们在 AIE，AI 工程师会如何解决这个问题呢？

两个词。

云端 Agent（Cloud agents）。

什么是云端 Agent？这主要是向在场的金融界朋友解释的。简单来说，云端 Agent 就是像 Claude Code 或 ChatGPT 那样的代码 Agent，但它不是运行在你的本地机器上，而是驻留并运行在远程环境中，而不是在你的电脑上。

正因为它驻留在云端，我们可以做很多非常有趣的事情。我们可以断言一堆审计要求，我们可以获得可审计性和透……透明度，我们可以获得可观测性，更重要的是，我们可以让它按计划启动并执行工作，而无需人工干预。

例如，当新数据写入证券主数据库时。

因此，每当该特定资产管理机构的投资范围发生变动时，一个 Nori 云端 Agent 就会启动。在这个案例中，底层运行的是一个本地部署的开源模型，因此所有数据都保留在本地内网（on prem）。根本无需担心信息会泄露到底层环境之外。这里的 Agent 拥有明确的指令，去弄清楚这笔变动的来源。同时它还可以访问一些实用的工具：用于读取 PDF 的 Box、像彭博这样的公开 API，甚至是限定范围的一小部分电子邮件。

随后，Agent 会整理出关于该变动的解释，收集该变动为何发生的引用出处，然后提供保留还是丢弃该变更的建议。最后，它会在 Slack 中向发生变更的那个单元格对应的负责人发送提示以供复核。

因此，你拥有了一个基本完全自主运行的 Agent，它为人类准备好任务，而人类只需做出同意或否定的决断。当然，如有必要，人类也可以去做进一步调查，以确保所提供的信息准确无误。

现在，你仍然需要一个人来审核这些变更。当然，出于合规问责等诸多原因，这是必要的。但是，这种工作模式大幅缩短了响应时间，因为过去的大部分延迟只是因为人们不得不手动检索大量文档。

Agent 在这方面非常、非常、非常擅长，而人类在这方面表现相当差。所以，如果大部分时间只是在搜集拼凑事实依据，那么你就可以把曾经需要花费一小时的事情，变成仅需 5 分钟的人工工作。
<details><summary>Original English</summary>
**>>**: Great.
 So,
 I'll
 pick
 up
 back
 here.


Now,
 Cliff
 makes
 a
 really
 good
 point.


The
 private
 assets
 are
 an
 absolute
 pain


to
 manage.
 They
 just
 don't
 fit
 into
 the


Sec
 Master
 all
 that
 well.
 But
 all
 that


information
 still
 needs
 to
 actually
 be


collated
 in
 some
 way.
 It's
 not
 like
 your


audit
 requirements
 and
 your
 cleaning


requirements
 and
 your
 standardization


requirements
 disappear.
 If
 anything,


it's
 actually
 a
 lot
 worse
 now
 because


it's
 just
 so
 much
 less
 standardized.
 You


can't
 rely
 on
 the
 people
 who
 are
 doing


your
 risk
 modeling
 to
 know
 whether
 or


not
 that
 data
 is
 ground
 truth.
 You


certainly
 don't
 want
 them
 to
 be
 the
 ones


going
 through
 and
 munging
 through
 all


your
 documents.
 So,
 somehow
 the
 data


that
 lives
 in
 that
 PDF
 somewhere,
 that


information
 needs
 to
 make
 its
 way
 back


into
 your
 SecMaster.


And
 right
 now,
 that
 is
 just
 an
 extremely


high
 labor
 task.
 I
 mean,
 generally
 it


just
 takes
 a
 lot
 of
 people
 hours
 and
 a


lot
 of
 domain
 expertise.
 I'm
 also
 going


to
 really
 quickly
 move
 this
 mouse
 out
 of


the
 way.
 It's
 been
 bothering
 me.


All
 right.


So,
 I
 want
 to
 ground
 this
 in
 a
 specific


example.
 We
 work
 closely
 with
 a
 Fortune


200
 asset
 manager
 here
 in
 New
 York,
 one


of
 the
 benefits
 of
 being
 New
 York
 local.


They
 recently
 started
 owning
 a
 bunch
 of


private
 assets,
 who
 hasn't,
 and
 it
 was


causing
 a
 lot
 of
 problems
 for
 their
 data


engineering
 teams,
 the
 people
 who
 were


maintaining
 their
 SecMaster.
 Now,
 when


any
 assets
 in
 their
 SecMaster
 changed,


they
 had
 to
 make
 sure
 that
 change
 was


correct.
 So,
 they
 had
 a
 system.
 They
 did


a
 day-over-day
 change
 analysis
 of
 their


table.


If
 you
 have
 a
 table
 with
 50,000
 assets


and
 each
 one
 of
 those
 assets
 has


something
 like
 200
 columns,
 even


infrequent
 changes
 are
 going
 to
 happen


on
 some
 daily
 cadence.


And
 every
 single
 one
 of
 those
 changed


cells
 was
 then
 sent
 to
 a
 team
 of
 people


to
 triage
 because,
 again,
 all
 of
 this


data
 is
 super
 unstructured.
 It
 just


lives
 in
 documents
 somewhere.


So,
 that
 team
 was
 then
 responsible
 for


going
 through
 docs
 and
 going
 through


various
 data
 sources
 to
 determine
 if
 any


given
 change
 was
 good
 or
 bad
 because


upstream
 data
 providers
 may
 have


fat-fingered
 something
 or
 may
 have


gotten
 something
 incorrect
 or
 they
 may


have
 just
 been
 conflict.


And
 I
 want
 to
 highlight
 that
 this
 is
 not


just
 every
 row,
 not
 every
 column,


literally
 every
 single
 cell.
 So,
 if
 an


asset
 changed
 price
 or
 if
 an
 asset


changed
 its
 name
 or
 if
 a
 company
 went


bankrupt
 or
 if
 it
 changed
 ownership
 or


you
 renegotiated
 a
 contract
 or
 whatever,


every
 single
 one
 of
 those
 changes
 in


that
 investment
 universe
 would
 have,
 on


average,
 an
 hour
 of
 work
 behind
 it.
 An


hour
 of
 somebody
 somebody's
 time,


somebody
 that
 you're
 paying
 to
 go
 and


just
 lunge
 through
 data.
 That
 is


hundreds
 of
 thousands
 of
 hours
 every


single
 month.
 Hundreds
 or
 thousands,


sorry.


So,
 we're
 at
 AIE,
 how
 would
 an
 AI


engineer
 solve
 this
 problem?


Two
 words.


Cloud
 agents.


What
 are
 cloud
 agents?
 This
 is
 more
 for


the
 finance
 folks
 in
 the
 room.
 In


simplest
 terms,
 a
 cloud
 agent
 is
 a


coding
 agent
 like
 Claude
 Code
 or


ChatGPT,
 but
 instead
 of
 running
 on
 your


local
 machine,
 it
 lives
 and
 runs
 in
 a


remote
 environment
 instead
 of
 on
 your


computer.


Because
 it
 lives
 on
 the
 cloud,
 we
 can
 do


a
 lot
 of
 really
 interesting
 things.
 We


can
 uh
 assert
 a
 bunch
 of
 audit


requirements,
 we
 can
 get
 auditability


and
 trans
 um
 transparency,
 we
 can
 get


observability,
 and
 more
 importantly,
 we


can
 have
 it
 spin
 up
 and
 do
 work
 on
 a


schedule
 without
 a
 person
 being


involved.


For
 example,
 when
 new
 data
 hits
 the
 SEC


master.


So,
 whenever
 there
 is
 a
 change
 in
 the


investment
 universe
 for
 this
 particular


asset
 manager,
 a
 Nori
 cloud
 agent
 will


spin
 up,
 in
 this
 case
 running
 a
 locally


deployed
 open
 source
 model
 under
 the


hood,
 so
 all
 of
 the
 data
 stays
 on
 prem.


There
 is
 no
 concerns
 about
 information


getting
 out
 of
 the
 underlying


environment.
 The
 agent
 here
 has
 explicit


instructions
 to
 figure
 out
 how
 the


source
 uh
 figure
 out
 the
 source
 of
 this


change.
 And
 it
 also
 has
 access
 to
 a
 few


useful
 tools,
 Box
 for
 PDFs,
 public
 APIs


like
 Bloomberg,
 and
 even
 a
 small
 segment


of
 email.


The
 agent
 then
 assembles
 an
 explanation


of
 the
 change,
 gets
 citations
 for
 why


that
 change
 happened,
 and
 then
 provides


a
 recommendation
 for
 whether
 to
 keep
 or


discard
 it.
 And
 finally,
 it
 pings
 the


owner
 of
 whichever
 cell
 changed
 in
 Slack


for
 review.


So,
 you
 have
 this
 agent
 that
 is


operating
 basically
 entirely


autonomously,
 providing
 tasks
 for
 a


human
 that
 the
 human
 just
 has
 to
 say
 yes


or
 no
 to.
 And
 of
 course,
 if
 necessary,


the
 human
 can
 go
 and
 do
 further
 research


to
 make
 sure
 that
 the
 information


provided
 was
 correct.


Now,
 you
 still
 need
 a
 human
 to
 review


those
 changes.
 Of
 course,
 this
 is


necessary
 just
 for
 accountability
 among


other
 things.
 But,
 this
 kind
 of
 work


dramatically
 cuts
 down
 the
 response
 time


because
 most
 of
 the
 previous
 slowness


was
 just
 people
 having
 to
 manually


search
 through
 a
 bunch
 of
 documents.


Agents
 are
 really,
 really,
 really
 good


at
 that,
 and
 humans
 are
 pretty
 bad
 at


that.
 So,
 if
 most
 of
 the
 time
 is
 just


assembling
 a
 case,
 well,
 you
 can
 take


something
 that
 used
 to
 take
 an
 hour
 and


make
 it
 just
 5
 minutes
 of
 human
 work.
</details>

### 通用 Agent 架构与企业级落地启示

**>>**: 但是，等等。这里值得停下来问一下：Agent 究竟是如何获取领域专长的？它怎么知道一个合理的变更应该是什么样子？我担心台下的一些人可能会想：“天哪，我难道必须去构建这么一套定制化的 Agent 基础设施，专门来做这件非常非常特定的独立事情吗？”

嗯，我认为实际情况不应该是这样运作的。

Agent 获取信息的方式与新入职的分析师完全相同：通过书面指示，说明文档放在哪里、信任哪些数据源，以及如何评判一项变更，所有这些都用英文撰写。如今的 Agent 非常擅长自我调整。所以，你只需编辑自然语言的英文 Markdown 文件，就能改变 Agent 的行为。你使用像 Claude Code、Open Code 或像 Pi 这样的任何开源通用 Agent，然后用类似 skills 或 agent.md 文件这样的配置去给这些 Agent 套上外壳。大部分的定制化实际上来自 Agent 运行的环境，这当然就取决于你在机器上放入了什么样的配置和什么样的凭据。

所以，我想退后一步，稍微把视角放宽一些。

到目前为止我们所讨论的一切——这种 Agent 化的证券主数据库概念——本质上就是一个数据库，外加一群像清洁鱼一样的自动程序在动态确保所有内容都是最新的。

它们可以快速发现问题并主动提请注意，在某些情况下甚至可以自主解决问题。

而且我想强调的一点是，这项技术不仅限于证券主数据库，甚至不仅限于一般的数据清洗。它可以在整个公司范围内发挥作用，因为这是一种通用的基石架构，我们借此让 Agent 去承担以往压在人类身上的工作。

在我看来，AI 工具在金融领域的巨大潜力在于，它们能够让大范围的任务从被动响应转变为主动发起。目前，每当有任何事情需要发生时，都需要人类花费时间和精力去评估该任务是否值得执行，然后把工作派发给一个 Agent。如果你问我，企业级 AI 的未来绝不是在你的笔记本电脑上使用一个机器人去解决某个问题。而是让机器人们主动带着任务、建议、分析和推荐来找你。

我认为，为了让这一未来成为现实，你需要使用能够适用于任何任务的灵活基础设施，并且让修改其适用的任务类型变得非常非常容易。你的证券运维主数据 Agent 不应该是一个孤立专属的 Agent。它实际上应该与你的审计 Agent、你的代码审查 Agent，或者你的工程师日常工作中使用的任何 Agent 运行在同一套云端 Agent 基础设施之上。

这些 Agent 中的每一个都将拥有不同的指令、工具和触发器，以及不同的上下文。这些当然是由你们自己、由企业所拥有的。

但是编排调度、安全性、集成整合，所有这一切跨越不同任务时实际上应该是完全相同的。而且在我看来，这真的应该由外部供应商来承担，因为每个人都在同一个组织内反复发明同样的问题或解决同样的问题。

那么，通过为金融领域构建 AI，我们学到了什么？我想留下我们总结出的三条经验，希望能分享给在座的各位。

第一，如果你问我，AI 的采纳本质上是一个协作问题。

业务人员想买成熟解决方案，工程师想卖底层构件。我们必须找到折中的契合点。当我们与业务领域的卓越专家合作时，取得了最大的成功——他们能够实现跨越，从云端 Agent 产生直觉上的飞跃并意识到：“等等，这正好能解决我现在面临的问题。”

第二，我认为将目标定为 95% 的自动化非常重要，而且保留人机协同（human in the loop）是完全可以接受的。人们总想用 AI 做到 100% 全流程自动化，但这行不通。这在软件领域行不通——我们在“软件工厂”模式上一次又一次看到了这一点——在金融领域更是完全行不通。

保留人工在流程中是完全没问题的。事实上，我认为我们应该积极拥抱这一点。如果你能接受让人花 5 分钟审阅某项内容，而不是试图让 Agent 每次都 100% 端到端地全盘处理，你能解决的问题要多得多。

最后，我想指出的是，偶然复杂性（accidental complexity）的成本已经大幅下降。

弗雷德·布鲁克斯（Fred Brooks）曾用“偶然复杂性”这个短语来描述由于系统的构建方式所带来的困难，而不是问题本身的本质复杂性。我认为在后台业务中，很多工作实际上就属于这种形态。不同团队以不同的方式记录相同的数据，不同供应商使用不同的格式，主要只是因为事情就是这样自然演变而来的。

我认为 Agent 非常非常擅长处理这类工作，即这种低复杂度、高耗费精力的工作，从而让人们能够将更多时间投入到具有本质复杂性的问题上，那些真正困难的问题上。

以上就是我要分享的全部内容，各位。非常感谢大家的光临。呃，在我离开之前，我想快速强调两点。

第一，如果你对更多此类演讲感兴趣，我们运营着一个名为 Agentics NYC 的社区。这是纽约最大的 Agent 工程社区。我们定期举办关于使用 Agent 构建系统的活动，面向从初学者到专家的各类人群。

第二，如果你对云端 Agent、软件工厂、Agent 化后台、证券主数据库等所有这些不同的方向感兴趣，呃，欢迎与我们联系。在此之后，Cliff 和我马上会在会场走廊交流区等候大家。呃，当然，你也可以通过 noriagentic.com 了解我们。非常感谢大家。
<details><summary>Original English</summary>
**>>**: But,
 wait.
 It's
 worth
 pausing
 just
 to


ask,
 how
 does
 the
 agent
 actually
 get


domain
 expertise?
 How
 does
 it
 know
 what


a
 good
 change
 looks
 like?
 I'm
 concerned


that
 some
 of
 the
 folks
 in
 the
 room
 might


think,
 "Oh
 man,
 I
 have
 to
 go
 and
 build


this
 like
 custom
 agent
 infrastructure


that
 going
 to
 do
 this
 really,
 really


specific
 one-off
 thing."


Well,
 I
 don't
 think
 that's
 actually
 how


these
 things
 should
 work.


Agents
 get
 information
 the
 same
 way
 a


new
 analyst
 does,
 from
 written


instructions
 about
 where
 documents
 live,


which
 sources
 to
 trust,
 and
 how
 to
 judge


a
 change,
 all
 in
 English.
 Agents
 are


pretty
 good
 at
 self-modification
 these


days.
 So,
 you
 can
 change
 how
 an
 agent


behaves
 by
 just
 editing
 natural
 language


English
 markdown
 files.
 You
 use
 a


generic
 agent
 like
 Claude
 Code
 or
 Open


Code
 or
 anything
 that's
 open
 source
 like


Pi,
 and
 then
 you
 skin
 those
 agents
 with


configs
 like
 skills
 or
 agent
 MD
 files.


And
 most
 of
 the
 customization
 actually


comes
 from
 the
 environment
 in
 which
 the


agent
 is
 running
 in,
 which
 of
 course
 is


just
 about
 what
 kind
 of
 configs
 and
 what


kind
 of
 credentials
 you're
 dropping
 on


the
 machine.


So,
 I
 want
 to
 take
 a
 step
 back
 and
 zoom


out
 a
 little
 bit.


Everything
 that
 we've
 talked
 about
 so


far,
 this
 agentic
 SecMaster
 concept,


this
 is
 essentially
 a
 database
 with
 a


bunch
 of
 cleaner
 fish
 automatons
 that


are
 dynamically
 making
 sure
 that


everything
 is
 up
 to
 date.


They
 can
 spot
 problems
 quickly
 and


proactively
 surface
 them
 and
 even
 solve


them
 in
 some
 cases,
 all
 autonomously.


And
 one
 of
 the
 things
 I
 want
 to


highlight
 is
 that
 this
 technology
 is
 not


limited
 to
 SecMasters
 or
 even
 data


cleaning
 in
 general.
 It
 can
 be
 useful


across
 a
 firm
 because
 it
 is
 a
 generic


primitive
 in
 which
 we
 are
 having
 agents


do
 work
 that
 was
 previously
 loaded
 onto


humans.


In
 my
 mind,
 the
 incredible
 potential
 of


AI
 tools
 in
 finance
 is
 that
 they
 can


make
 a
 huge
 range
 of
 tasks
 proactive


instead
 of
 reactive.
 Right
 now,
 every


time
 anything
 needs
 to
 happen,
 and
 a


human
 has
 to
 spend
 time
 and
 energy


evaluating
 whether
 or
 not
 that
 task
 is


worthwhile
 and
 then
 sending
 that
 work
 to


an
 agent.
 If
 you
 ask
 me,
 the
 future
 of


enterprise
 AI
 is
 not
 use
 a
 robot
 on
 your


laptop
 to
 solve
 a
 problem.
 It's
 having


the
 robots
 come
 to
 you
 with
 tasks,


advice,
 analysis,
 and
 recommendations.


I
 think
 that
 in
 order
 to
 make
 that


future
 a
 reality,
 you
 need
 to
 use


flexible
 infrastructure
 that
 can
 be
 used


for
 any
 task
 and
 make
 it
 really,
 really


easy
 to
 modify
 what
 kind
 of
 tasks
 it's


being
 used
 for.
 Your
 SecOps
 master
 agent


shouldn't
 be
 a
 one-off
 unique
 agent.
 It


should
 actually
 be
 running
 on
 the
 same


cloud
 agent
 infrastructure
 as
 your
 audit


agent
 or
 your
 code
 review
 agent
 or
 any


of
 the
 agents
 that
 your
 engineers
 are


using
 for
 their
 day-to-day
 job.


Each
 of
 the
 Each
 of
 these
 agents
 will


have
 different
 instructions
 and
 tools


and
 triggers,
 different
 context.
 That,


of
 course,
 is
 owned
 by
 you,
 by
 the


company.


But
 the
 orchestration,
 the
 security,
 the


integrations,
 all
 of
 that
 should


actually
 just
 be
 the
 same
 across
 these


different
 tasks.
 And
 really,
 in
 my
 mind,


should
 just
 be
 owned
 by
 a
 vendor
 because


everybody
 is
 inventing
 these
 problems
 or


solving
 these
 problems
 over
 and
 over


again
 in
 the
 same
 organizations.


So,
 what
 were
 the
 things
 that
 we
 learned


by
 building
 AI
 for
 finance?
 I
 want
 to


leave
 with
 three
 lessons
 that
 we
 that
 we


had
 that
 I
 want
 to
 impart
 on
 everybody


here.


First,
 if
 you
 ask
 me,
 AI
 adoption
 is


primarily
 a
 collaboration
 problem.


People
 want
 to
 buy
 solutions,
 engineers


want
 to
 sell
 building
 blocks.
 We
 have
 to


find
 a
 way
 to
 meet
 in
 the
 middle.
 We


found
 the
 most
 success
 when
 we
 work
 with


brilliant
 folks
 who
 are
 experts
 in
 their


domain,
 who
 are
 able
 to
 make
 the
 leap,


that
 intuitive
 leap
 from
 cloud
 agents
 to


wait,
 this
 actually
 fits
 into
 a
 problem


that
 I
 have
 right
 now
 today.


Second,
 I
 think
 it's
 really
 important
 to


aim
 for
 95%
 automation
 and
 it's
 okay
 to


keep
 a
 human
 in
 the
 loop.
 People
 want
 to


use
 AI
 to
 do
 100%
 of
 everything
 and
 this


doesn't
 work.
 It
 doesn't
 work
 in


software,
 we've
 seen
 that
 with
 software


factories
 over
 and
 over
 again,
 but
 it


really
 doesn't
 work
 in
 finance.


It's
 okay
 to
 have
 a
 human
 in
 the
 loop.


In
 fact,
 I
 think
 we
 should
 lean
 into
 it.


There
 are
 way
 more
 problems
 that
 you
 can


solve
 if
 you're
 okay
 with
 having
 one


human
 spend
 5
 minutes
 looking
 at


something
 than
 trying
 to
 have
 an
 agent


do
 something
 100%
 end-to-end
 every


single
 time.


And
 finally,
 I
 want
 to
 point
 out
 that


the
 cost
 of
 accidental
 complexity
 has


dropped
 significantly.


Fred
 Brooks
 used
 the
 phrase
 accidental


complexity
 to
 describe
 the
 difficulty


that
 comes
 from
 how
 a
 system
 was
 built


as
 opposed
 to
 the
 problem
 it
 solves.
 And


I
 think
 in
 the
 back
 office,
 a
 lot
 of


work
 is
 actually
 shaped
 like
 this.
 Teams


record
 the
 same
 data
 in
 different
 ways,


and
 vendors
 use
 different
 formats,


mostly
 because
 that's
 just
 how
 things


evolved
 organically.


I
 think
 agents
 are
 really,
 really
 good


at
 handling
 this
 kind
 of
 work,
 this


low-complexity,
 high-effort
 work,
 which


actually
 then
 allows
 people
 to
 spend


more
 time
 on
 the
 problems
 that
 are


essentially
 complex,
 the
 problems
 that


are
 actually
 hard.


So,
 that's
 all
 I
 got,
 guys.
 Thank
 you
 so


much
 for
 coming.
 Uh
 before
 I
 go,
 I
 want


to
 just
 quickly
 highlight
 two
 things.


One
 is
 if
 you're
 interested
 in
 more


talks
 like
 this,
 we
 run
 a
 community


called
 Agentics
 NYC.
 It
 is
 New
 York's


largest
 agentic
 engineering
 community.


We
 run
 regular
 events
 on
 building
 with


agents
 for
 beginners
 through
 experts.


And
 second,
 if
 you
 are
 interested
 in


cloud
 agents,
 software
 factories,


agentic
 back
 office,
 SecMasters,
 all


these
 different
 things,
 uh
 you
 should


reach
 out.
 Cliff
 and
 I
 will
 be
 in
 the


hallway
 track
 immediately
 after
 this.
 Uh


and
 of
 course,
 you
 can
 check
 us
 out
 at


noriagentic.com.
 Thank
 you
 so
 much.
</details>