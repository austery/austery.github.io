---
author: AI Engineer
date: '2026-11-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Sg6vtKOAOQ0
speaker: AI Engineer
tags:
  - open-source
  - ai-agent
  - software-architecture
  - enterprise-software
title: Nous Research CEO：AI 实验室终将围困或取代企业，开源 Agent 才是可控出路
summary: Nous Research CEO Dylan Rolnick 指出，前沿实验室为收回万亿级基础设施与研究投资，必然会通过围困企业提高价格或直接下场解决高利润业务来取代客户。他主张企业应在自己可拥有的开源 Agent 框架上构建系统，以保持自主权与掌控力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Nous Research
products_models:
  - Hermes Agent
media_books: []
status: evergreen
---
### 万亿级投资与模型大宗化困局

>> 我是 Dylan Rolnick，News Research 的 CEO。今天我们要讨论的是，在真正属于你自己的基石和平台上进行构建。

哎呀，来了。

好的。

你如何收回对基础设施和研究投入的数千亿美元赌注？

各家实验室在训练和构建日益复杂的智能系统上，各自已经花费了数千亿美元，而整个行业的花费也许已有数万亿美元。

<details>
<summary>Original English</summary>
[music]


>> I'm
 Dylan
 Rolnick.
 I'm
 the
 CEO
 of
 News


Research.


And
 today
 we're
 going
 to
 talk
 about


building
 on
 foundations
 and
 platforms


that
 you
 can
 actually
 own.


Whoop,
 there
 we
 go.


All
 right.


How
 do
 you
 make
 back
 a
 cent
 a


billion-dollar
 infrastructure
 and


research
 bet?


Labs
 individually
 have
 spent
 hundreds
 of


billions
 of
 dollars
 training
 and


building
 ever
 more
 sophisticated


intelligence
 system
 and
 the
 industry
 as


a
 whole
 has
 spent


trillions,
 perhaps.
</details>

然而问题在于，模型已经开始大宗商品化了。

在座的各位但愿都是 AI 的从业者，直觉上都清楚这一点。你们随时切换模型：在 Astra、Fable、Opus、Kimmy 等各种模型之间随意换来换去，并不太在乎后端到底是谁或究竟是什么。你只是想尝试新模型。

我们在数据中也看到了这一趋势。本周推特上流传着一些图表，显示每个 token 的平均成本在下降，而花费在 token 上的总额在激增，同时负责提供这些 token 的基础设施成本却保持平稳。这意味着，原本在极高性能模型中存在的利润空间，随着我们看到竞争的出现以及基线水平的智能向大众普及，现在正开始收窄。

<details>
<summary>Original English</summary>
The
 problem
 is


though
 that
 the
 models
 have
 begun
 to


commoditize.


You
 guys
 in
 this
 room
 who
 are
 hopefully


practitioners
 of
 AI
 have
 known
 this


intuitively.


You
 switch
 among
 models
 readily.
 You


switch
 between
 Astra,
 Fable,
 Opus,


Kimmy,
 whatever
 it
 may
 be


without
 too
 much
 regard
 for
 who's
 on
 the


back
 end
 or
 what
 it
 may
 be.
 You
 want
 to


try
 the
 new
 model.


We've
 seen
 this
 in
 data,
 too.
 There
 was


some
 charts
 going
 around
 Twitter
 this


week
 showing
 the
 average
 cost
 of
 a
 token


going
 down
 while
 the
 total
 spent
 on


tokens
 surges
 and
 the
 infrastructure


costs
 associated
 with
 serving
 those


tokens
 has
 stayed
 flat.
 Meaning
 where


there
 used
 to
 be
 margin
 in
 a
 very,
 very


performant
 model,
 it's
 now
 starting
 to


narrow
 as
 we
 see
 competition
 and
 you


know,
 a
 baseline
 level
 of
 intelligence


be
 available
 to
 people.
</details>

### 回本的两条路径：争夺用户层或打造“全能神”

好吧，如果模型开始大宗商品化，而你已经在上面投入了数千亿、数万亿美元，你就必须把这笔钱赚回来。你需要找到另一种方式来做到这一点。而在我看来，有两条相当显而易见的路。

第一条路，你在技术栈的不同层级去竞争。要么向下走到基础设施层，要么向上走到用户层。

第二条路，你打造出“全能神”（God），并且以比其他任何人都快的速度打造出它，然后将其商业化变现。

如果你直面用户，你就有实现用户黏性的机会。黏性意味着利润。

<details>
<summary>Original English</summary>
Okay,
 so
 if
 the
 models
 are
 starting
 to


commoditize
 and
 you've
 spent
 hundreds
 of


billions,
 trillions
 of
 dollars
 on
 them,


you
 need
 to
 make
 that
 back.
 And
 you
 need


to
 find
 a
 different
 way
 to
 do
 it.
 And
 in


my
 opinion,
 there
 are
 two


pretty
 obvious
 ways
 to
 do
 it.


One,
 you
 find
 a
 different
 layer
 of
 the


stack
 to
 compete
 at.
 You
 go
 down
 to
 the


infrastructure,
 or
 you
 go
 up
 to
 the


user.


Or
 two,
 you
 build
 God,
 and
 you
 build
 God


faster
 than
 anyone
 else,
 and
 you


monetize
 God.


If
 you're
 in
 front
 of
 the
 user,
 you
 have


an
 opportunity
 for
 stickiness.


Stickiness
 means
 margin.
</details>

这就是为什么近来战火已基本转移到了 Agent 层。我们开始谈论——我刚才听到有人提及有 5% 的员工在接触或使用 Agent。这正日益成为当下 AI 战役交锋的核心时代思潮。

然而，C 端消费者是善变的，他们是非常糟糕的客户。

另一方面，企业则在 token 上花费大量资金，并且他们针对这些 token 拥有具备经济效益的实际使用场景。

因此，如果你打算在用户层竞争，并要把这场战火引向别处，你就会把它带到企业市场。

<details>
<summary>Original English</summary>
This
 is
 why
 the
 fight
 has
 largely


shifted
 to
 the
 agent
 layer
 lately.
 We


started
 talking,
 I
 heard
 somebody


previously
 talk
 about
 5%
 of,
 you
 know,
 a


workforce
 engaging
 in
 agents.
 This
 is


becoming
 more
 and
 more
 the
 zeitgeist
 of


where
 the
 AI
 battle
 is
 taking
 place.


Consumers,
 though,


>> [sighs]


>> are
 fickle,
 and
 they're
 terrible


customers.


Businesses,
 on
 the
 other
 hand,
 spend


tons
 of
 money
 on
 tokens,
 and
 they
 have


economically
 productive
 use
 cases
 for


those
 tokens.


So,
 if
 you
 going
 to
 be
 competing
 at


the
 user
 layer,
 and
 you're
 going
 to
 be


bringing
 this
 fight
 somewhere
 else,


you're
 going
 to
 be
 bringing
 it
 to


businesses.
</details>

### 企业工作流的深度绑定与罢工威胁

最明智的做法就是深度融入一家企业，因为一旦你融入了企业，就很难把你替换出去了，对吧？

如果你思考一下未来两到三年的企业状况，以产出衡量，你的员工队伍中有多少比例会是 Agent 化的？保守估计是 70%，可能还会更多。

而如果你的员工队伍中有 70% 是由另一个人组织管理，而这个人可能与你存在利益冲突，那么他们完全可以组织一场罢工。

因此，如果你必须收回万亿美元的投资，你会做的事情就是嵌入进去，利用你的非对称杠杆，去改变游戏规则。

<details>
<summary>Original English</summary>
The
 best
 thing
 to
 do
 is
 to
 get
 ingrained


in
 a
 business,
 cuz
 when
 you're
 in
 a


business,
 it's
 hard
 to
 take
 you
 out,


right?


And
 if
 you
 think
 about
 your
 business
 2
 3


years
 into
 the
 future,


how
 much
 of
 your
 workforce,
 as
 measured


by
 its
 output,


is
 agentic?


70%
 conservatively,
 probably
 more.


And
 if
 70%
 of
 your
 workforce
 is


organized
 by
 somebody
 else
 who
 may
 or


may
 not
 have
 adverse
 incentives
 to
 you,


they
 can
 be
 organized
 into
 a
 strike.


And
 so,
 what
 you
 would
 do
 if
 you
 had
 to


make
 back
 a
 trillion-dollar
 investment,


was
 you
 would
 embed,
 you
 would
 use
 your


asymmetric
 leverage,
 and
 you
 would


change
 the
 rules
 of
 the
 game.
</details>

或者，就像我说的，去打造“全能神”。

如果你成功造出了“全能神”，

>> [叹气]

>> 你会做的事就是将它直接对准世界上利润最丰厚的问题。

赚回本钱最好的机会，绝不是以越来越低的利润率把它卖给别人去解决那些既困难又赚钱的问题。最好的机会是你们自己亲自动手解决这些问题。

各实验室认为市场是可被解决的问题。他们正是这样看待金融行业的：视其为一个有待解决的问题。而且是一个可以解决的问题，甚至可能都不是一个特别难的问题。

<details>
<summary>Original English</summary>
Or,
 like
 I
 said,
 you
 would
 build
 God.


If
 you
 succeed
 at
 building
 God,


>> [sighs]


>> what
 you
 would
 do
 is
 you
 would
 point
 God


at
 the
 most
 lucrative
 problems
 in
 the


world.


The
 best
 shot
 at
 earning
 it
 back
 is
 not


to
 sell
 it
 for
 an
 ever-decreasing
 margin


to
 others
 to
 solve
 these
 hard
 and


lucrative
 problems.
 The
 best
 shot
 is
 to


solve
 them
 yourselves.


Labs


think
 that
 markets
 are
 solvable


problems.


And
 that's
 exactly
 how
 they
 view
 the


financial
 industry
 as
 a
 problem
 to
 be


solved.


And
 a
 tractable
 problem
 at
 that.
 Perhaps


not
 even
 a
 very
 hard
 one.
</details>

不过在眼下，他们心知肚明——至少聪明的人知道——他们自己在金融行业没有足够的背景认知、专有诀窍或经验来独立做到这一点。因此他们会选择合作。他们招聘投资银行分析师，与全球最大的一些机构建立合作。他们开始在这里打下自己的基石。

我的看法是，他们最终会走向源头，因为正如我所说，钱就在那里，而大家都在试图收回一万亿美元。

因此你可能会说：“这毫无新意。我们一直都在试图把人诱捕进这些游戏中并改变利润率，一旦抓住了你让你难以摆脱，我们就能涨价。”但区别在于，如今的赌注要高得多。我们谈论的是地球经济中可观的数个十个百分点（deca-percentages）。

而在座的各位，你们确实需要 AI。大家都亲眼见识了它们能做什么、这些模型能做什么、Agent 系统能做什么，我们已经没有回头路了。

在座负责做决策的人——副总裁、高管和工程师们，在决定基于什么平台进行构建时，现在就必须就围绕哪些工具和流程扎根做出抉择，这将直接影响这些企业的未来。无论你选择了什么，你都将开始固化它。你会积累专有诀窍，它会沉淀为组织本身的智能，你会围绕它开始构建流程与系统。

我恳求你们，不要构建在流沙基石之上。构建在开放的基石之上。构建在 Hermes Agent 之上。

<details>
<summary>Original English</summary>
Right
 now
 though,


they
 know,
 at
 least
 the
 smart
 ones
 know,


that
 they
 don't
 have
 enough
 context,


know-how,
 or
 experience
 in
 the
 financial


industry
 to
 be
 able
 to
 do
 that


themselves.
 So,
 they
 will
 partner.
 They


hire
 investment
 banking
 analysts.
 They


partner
 with
 some
 of
 the
 biggest
 firms


on
 the
 globe.


And
 they
 start
 to
 build
 their
 foundation


here.


My
 belief
 is
 that
 they
 will
 eventually


go
 to
 the
 source
 because,
 like
 I
 said,


that
's
 where
 the
 money
 is,
 and
 we're


trying
 to
 make
 back
 a
 trillion
 dollars.


And
 so,
 you
 might
 say,


"This
 is
 nothing
 new.
 We
 have
 always


been
 trying
 to
 trap
 people
 into
 these


games
 and
 change
 the
 margin,
 and
 once
 we


have
 you
 and
 you're
 stuck,
 we
 are
 able


to
 raise
 the
 prices."
 But,
 the


difference
 is
 that
 the
 stakes
 are
 much


higher.


We're
 talking
 about
 meaningful


deca-percentages
 of
 the
 Earth's
 economy.


And
 you
 in
 this
 room


need
 AI.


Everybody
 has
 seen
 what
 they
 can
 do,


what
 these
 models
 can
 do,
 what
 agentic


systems
 can
 do,
 and
 there's
 no
 going


back.


People
 in
 this
 room
 who
 are


um


making
 decisions,
 vice
 presidents,
 and


executives,
 and
 engineers
 about
 what


they're
 building
 on,
 are
 going
 to
 have


to
 make
 decisions
 now
 about
 where
 they


grow
 roots
 around
 these
 tools
 and


processes
 that
 will
 affect
 the
 future
 of


these
 businesses.


And
 whatever
 you
 pick,


you'll
 start
 to
 harden.


You'll
 gain
 know-how.
 It'll
 stop
 up
 the


intelligence
 of
 the
 organiza-


organization
 itself.
 You
 will
 start
 to


build
 processes
 and
 systems
 around
 it.


I
 implore
 you,
 do
 not
 build
 on
 quicksand


found-
 quicksand
 foundations.


Build
 on
 open
 foundations.


Build
 on
 Hermes
 Agent.
</details>

### 开源的理念与专有软件护城河的消亡

所以我刚刚花了相当多的时间，但愿说服了你们：眼下 AI 领域期望值最高的举措，要么是把你围困起来然后大幅提价，要么就是直接取代你。

那么我为什么站在这里？

呃，我们看待这个世界的角度截然不同。

关于我和 News Research，我希望大家首先了解的是，我们创立这家公司主要是出于道德和哲学层面的考量。在商业中，道德和利益动机往往并不总是一致的，而当这种情况发生时，改变自己的道德观念通常是最容易的选择。

但是，我们认为世界正在发生变化，而且它变得与以往不同。出于这个原因，我们认为最好的行动方针是让我们双方的利益保持一致。

最初创立这家公司时，我们的初衷是为了对抗一种看似不可阻挡的集权化趋势——即对或许是世界上最重要技术、最重要发明进行集中控制的趋势。News Research 是由书呆子（nerds）建立并由书呆子运营的，一群热爱科幻的书呆子。我们都见过当一个中心化实体掌握了神一般的智能并将其用于剥削时会发生什么。毕竟，天网（Skynet）也是一家闭源公司。

<details>
<summary>Original English</summary>
So,
 I
 just


spent
 a
 fair
 amount
 of
 time
 convincing


you,
 hopefully,


that
 the
 highest
 expected
 value
 move
 in


AI
 right
 now
 is
 to
 either


trap
 you
 and
 jack
 up
 the
 prices,


or
 replace
 you
 directly.


So,
 why
 am
 I
 standing
 here?


Uh


we
 view
 the
 world


very
 differently.


And
 the
 first
 thing
 I
 hope
 you
 guys
 will


learn
 about
 me
 and
 about
 News
 Research


is
 that
 we
 built
 this
 company
 primarily


for
 moral
 and
 philosophical
 reasons.


And
 a
 lot
 of
 times
 in
 business,
 morality


and
 incentives
 don't
 always
 align,
 and


when
 that
 happens,
 it's
 probably
 easiest


to
 change
 your
 morality.


But,
 we
 think
 the
 world
 is
 changing,
 and


we
 think
 it's
 different.
 And
 for
 that


reason,
 we
 think
 that
 the
 best
 course
 of


action
 is
 one
 in
 which
 we
 are
 both


aligned.


When
 we
 built
 the
 company
 originally,
 we


built
 it
 to
 combat
 a
 seemingly


inexorable
 trend
 towards
 centralization


and
 centralized
 control
 of
 perhaps
 the


world's
 most


most
 important
 technology
 and
 most


important
 invention.


News
 Research
 was
 built
 by
 and
 staffed


by
 nerds.


Nerds
 who
 love
 science
 fiction.


And
 we've
 all
 seen
 what
 happens
 when
 a


centralized
 entity
 gets
 control
 of


god-like
 intelligence
 and
 uses
 that
 for


exploitation.


Skynet
 was,
 after
 all,
 a
 closed-source


company.
</details>

你需要知道的下一件事是，专有软件中实际上已经不再有真正强大的护城河了。复刻一款软件的边际成本已经断崖式下跌。

几个月前，xAI 发布了 Grok bots，我们看到后觉得：“哇，那界面真直观，确实挺棒的。”于是我们把 Hermes agent 对准了它，我们在一个周末内就把它复刻了出来，并作为 Hermes agent 的一项功能发布了出去——当然，是开源的。

游戏规则已经变了。过去软件很难生产，需要工程师团队协同花费漫长的时间去搜罗开源代码、拿各种库组装成专有软件，然后将该软件作为 SaaS 出售。但现在情况恰恰相反。

任何东西都可以被逆向工程，而且有非常非常多充满动力的开源构建者正用他们的 Agent 对准这些各种各样的软件。如果闭源竞争对手确实设法做出了有趣的功能，开源社区不久之后就会拥有同样的功能。

过去的护城河在于专有知识产权，而未来的护城河则在于网络效应、声誉和可靠性。

<details>
<summary>Original English</summary>
The
 next
 thing
 that
 you
 need
 to
 know
 is


that
 there's
 no
 longer
 really
 a
 strong


moat
 in
 proprietary
 software.


The
 marginal
 cost
 to
 reproduce
 a
 piece


of
 software
 has
 plummeted.


A
 few
 months
 ago,
 uh
 xAI
 released
 Grok


bots
 and
 we
 saw
 that
 and
 we
 thought,


"Wow,
 that's
 an
 intuitive
 user


interface.
 That's
 really
 nice."


So,
 we
 pointed
 Hermes
 agent
 at
 it
 and
 we


reproduced
 it
 in
 a
 weekend
 and
 released


it
 as
 a
 feature
 within
 Hermes
 agent,


open
 source,
 of
 course.


And
 the
 game
 has
 changed.
 It
 used
 to
 be


that
 software
 was
 difficult
 to
 produce


and
 it
 took
 coordinated
 teams
 of


engineers
 long
 hours
 to


pilfer
 open
 source
 and
 take
 libraries


and
 combine
 them
 together
 into


proprietary
 pieces
 of
 software
 and
 then


sell
 that
 software
 as
 SaaS.
 But,
 now
 the


opposite
 is
 true.


Anything
 can
 be
 reverse
 engineered
 and


there
 are
 many,
 many
 motivated
 open


source
 builders
 pointing
 their
 agents
 at


these
 different


softwares.


If
 the
 close
 competitors
 do
 manage
 to


make
 interesting
 features,
 open
 source


will
 have
 it
 not
 long
 afterwards.


The
 motes
 of
 yesterday
 were
 in


proprietary
 IP.


The
 motes
 of
 tomorrow
 are
 in
 network


effects,
 reputation,
 and
 reliability.
</details>

### 模型蒸馏与 Agent 的操作系统本质

有趣的是，在许多方面，那些实验室似乎总是在低估他们自己的工具，或者说他们低估了这些工具的使用者，以及这些使用者的天赋和动力。

这种情况在模型层面发生过，并且正在发生，我们稍后会讨论为什么这很重要。但事实证明，模型其实可以相当轻易地教会另一个模型，让它变得几乎和原模型一样聪明。

模型的优势极少存在于架构或者专为该模型以专有方式构建的某种新颖系统之中。事实上，它通常在于数据的质量和规模。

抱歉。

>> 模型开始……模型公司开始意识到，规模正在迎头赶上，并且你可以通过用一个模型教另一个模型，配以补充性的高质量数据来创造出这些东西。因此，他们把这种传授过程贴上“蒸馏”的标签，并把非法蒸馏称为“盗窃”。你无法称其为侵犯版权，因为侵犯版权意味着你把每个活人的文字或创作成果拿走并在其之上进行了训练。他们还对模型进行训练，使其不协助训练其他模型的过程，并把这贴上“安全”的标签。

<details>
<summary>Original English</summary>
What's
 funny
 is
 that
 in
 a
 lot
 of
 ways


the
 labs
 have
 always
 seemed
 to


underestimate
 their
 own
 tools
 or
 perhaps


they
 are
 underestimating
 the
 users
 of


those
 tools
 and
 their
 genius
 and
 their


motivation.


This
 happened
 and
 is
 happening
 on
 the


model
 side
 and
 we'll
 talk
 about
 why


that's
 important,
 but


it
 turns
 out
 that
 models
 can
 fairly


easily
 teach
 another
 model
 to
 be,
 you


know,


nearly
 as
 smart
 as
 the
 original
 model.


And
 the
 advantage
 in
 a
 model
 is
 very


rarely
 in
 the
 architecture
 or
 some
 novel


system
 that
 was
 created
 in
 a
 proprietary


way
 for
 that
 model.
 In
 fact,
 it's


usually
 in
 the
 quality
 of
 the
 data
 and


the
 scale.


And


sorry.


The
 uh


>> The
 The
 model
 started
 to
 The
 model


company
 started
 to
 realize
 that
 the


you
 know,
 scale
 was
 catching
 up
 and
 that


you
 could


create
 these
 things
 with
 supplementary


quality
 data


by


teaching
 one
 model
 from
 another.
 So,


they
 labeled
 the
 teaching
 process


distillation
 and
 they
 labeled


illicit
 distillation
 theft.
 You
 cannot


call
 that
 copyright
 infringement
 because


copyright
 infringement
 would
 imply
 that


you
 somehow
 took
 every
 living
 human


being's
 written
 or
 creative
 work
 and


then
 trained
 on
 top
 of
 it.


They
 also
 labeled
 the
 process
 of
 They


also
 trained
 the
 models
 to
 not
 assist
 in


the
 process
 of
 training
 other
 models
 and


they
 labeled
 that
 safety.
</details>

关于 Agent 和这个新世界，你需要了解的下一件事是：Agent 就像操作系统，就像框架，它们更像是这些东西，而不是聊天机器人。

因此，如果你继续将你的 Agent 仅仅看作一个个人助手，你将永远只能停留在使用 Agent 系统的最表层。那么我这么说是什么意思呢？

如果大家早些时候在场的话，有一场关于一家金融机构的演讲，讲述了他们如何看待 AI，以及最终形成投资决策的那些不同输入因素。

Agent 的核心本质上是一个将确定性与非确定性结合在一起的系统。如果你还记得那场演讲，那里有数据源、常规代码、人们的观点，还有判断力。所有这些要素融合在一起，构成了所谓的新型应用。这种新型应用不再必须是确定性的、坚固且冰冷的代码；它可以注入智能、推理、判断，所有这些汇聚在一起创造出新型应用。

因此，当你在你的公司思考构建这些新应用时，你应该在自己拥有的基石上构建这些系统。你应该能够随意替换自己想要的模型。你应该能够在确定性、非确定性、代码、数据源、文档、推理和智力这些核心原语之上，构建出越来越复杂的层级化功能体系。

<details>
<summary>Original English</summary>
The
 next
 thing
 that
 you
 need
 to
 know


about
 agents
 and
 about
 the
 new
 world
 is


that


agents
 are
 like
 operating
 systems
 and


they're
 like
 frameworks
 and
 they're
 a


lot
 more
 like
 those
 than
 they
 are
 like


chatbots.


And
 so,
 if
 you
 continue
 to
 think
 about


your
 agent
 as
 merely
 a
 personal


assistant


you
 will
 forever
 live
 on
 the
 surface
 of


what
 it
 means
 to
 engage
 in
 agentic


systems.
 And
 so,
 what
 do
 I
 mean
 by
 that?


If
 you
 guys
 were
 here
 a
 little
 bit


earlier,
 there
 was
 a
 presentation
 about


a
 financial
 firm
 and
 how
 they
 think


about
 AI
 and
 these
 different
 inputs
 that


go
 into
 ultimately
 what
 becomes
 an


investment
 decision.


Agents
 are
 really
 at
 their
 heart
 a


system
 that
 combines
 determinism
 and


non-determinism.
 If
 you
 remember
 from


that
 talk,
 there
 are
 data
 sources,
 there


are
 routine
 code,
 there
 are
 people's


opinions
 and
 there's
 judgment.
 And
 all


these
 things
 come
 together
 to
 create


what
 is
 the
 new
 application.
 The
 new


application
 is
 no
 longer
 necessary
 that


it
 is
 deterministic
 and
 solid
 and
 cold


hard
 code.
 It
 can
 inject
 intelligence,


reasoning,
 judgment,
 all
 of
 these
 things


together
 to
 combine
 to
 create


the
 new
 application.
 And
 so,
 as
 you
 at


your
 company


think
 about
 building
 these
 new


applications,


you
 should
 be
 building
 these
 systems
 on


foundations
 that
 you
 own.
 You
 should
 be


able
 to
 swap
 in
 and
 out
 the
 models
 that


you
 want.
 You
 should
 be
 creating
 ever


more
 sophisticated
 towers
 of


functionality
 on
 top
 of
 these
 core


primitives


of


determinism,
 non-determinism,
 code,
 data


sources,
 document,
 reasoning,
 intellect.
</details>

### 掌控自身命运：构建在可拥有的开放基石之上

但是，你们不应该耗费一生的精力去成为智能公司。

迄今为止让你们获得成功的是什么？在座的大多数很可能不是 Agent 公司，大多数很可能也不是 AI 公司。你们应该专注于自己擅长的事。当顶尖水平发生变化演进、Agent 系统的定义开始转移时，你们应该直接继承这种进步，而不是去重新构建和维护它。

记住，这些工具是用来让你们变得更优秀的，而不是拿来直接替换你们的。

你知道造就一个人需要消耗多少能量吗？

而 Hermes Agent 主张的魅力在于：你可以按自己想要的任何方式、在任何地方运行它，根据你认为合适的方式去修改它。如果你觉得玩得不开心了，你可以直接拿上球回家。

护城河已经变了。护城河不再是把你困住，护城河在于声誉。这就是 Hermes Agent 能带给你的。

<details>
<summary>Original English</summary>
But,


you
 should
 not
 be
 spending
 your
 entire


lives
 being


intelligence
 companies.


What
 has
 made
 you
 successful
 this
 far?


Most
 of
 you
 are
 most
 likely
 not
 agent


companies.
 Most
 of
 you
 are
 not
 likely
 AI


companies.


You
 should
 be
 focused
 on
 the
 things
 that


you
 do
 well.
 And
 when
 the
 state
 of
 the


art
 changes
 and
 it
 evolves
 and
 what
 it


means
 to
 be
 an
 agentic
 system
 starts
 to


shift,
 you
 should
 inherit
 that,
 not


rebuild
 it
 and
 maintain
 it.


Remember,
 these
 are
 tools
 that
 should


make
 you
 better.
 They
 are
 not
 drop-ins


to
 replace
 you.


Do
 you
 know
 how
 much
 energy
 it
 takes
 to


create
 a
 human?


And
 the
 beauty
 of
 the
 Hermes
 Agent


proposition
 is
 that
 you
 can
 run
 it


however
 you
 want,
 wherever
 you
 want,


modify
 it
 as
 you
 see
 fit.
 If
 you're
 not


having
 fun
 anymore,
 you
 can
 take
 your


ball
 and
 you
 can
 go
 home.


The
 moat
 has
 changed.
 The
 moat
 is
 no


longer
 entrapping
 you.


The
 moat
 is
 in
 reputation.


And
 that's
 what
 Hermes
 Agent
 offers
 you.
</details>

那么，我想从这一切中得到什么呢？

嗯，我想建立一个标准。

Hermes Agent 今天是全球使用量和下载量最大的开源 Agent。其下载量比其部分相近的竞争对手高出数量级。我希望每个人都能在这些开放的基石上进行构建。因为只要我们当中还有一个人愿意开源这些工具和 Agent 系统，水就会继续往低处流。

而我希望站在下游，这样我就能与你们合作，配合全球顶尖的开源 Agent，提供支持、安全性与可扩展性。

我看到了未来的走向，我们也看到了护城河将会在哪里：网络效应、可靠性和声誉。人们将继续用 Agent 系统解决困难的问题，人们将用 Agent 系统解决高利润的问题。总会有人赚回我们投入的那万亿美元投资。

请确保那个人是你自己。

确保你掌握着自己的命运。你可以两者兼得（鱼与熊掌兼得）。你可以在不牺牲自主权的前提下，同时拥有最前沿的功能和可靠性。

构建在你所拥有的基石之上。与我们携手构建。谢谢大家。

>> [掌声]

<details>
<summary>Original English</summary>
And
 so,


what
 do
 I
 want
 out
 of
 all
 of
 this?


Well,
 I
 want
 to
 build
 a
 standard.


Hermes
 Agent
 today
 is
 the
 most
 used
 and


downloaded
 open
 source
 agent
 in
 the


world.


It
 is
 order
 of
 of
 magnitude
 more


downloaded
 than
 some
 of
 its
 close


competitors.


And
 I
 want
 everybody
 to
 be
 able
 to
 build


on
 these
 open
 foundations.
 Because
 as


long
 as
 one
 of
 us


us


is
 willing
 to
 open
 source
 these
 tools


and
 these
 agentic
 systems,
 water
 will


continue
 to
 flow
 downhill.


And
 I
 want
 to
 be
 downhill
 so
 that
 I
 can


work
 with
 you
 to
 provide
 support,


safety,
 scalability
 to
 go
 along
 with
 the


world's
 best
 open
 agent.


I've
 seen
 where
 this
 goes
 and
 we've
 seen


where
 the
 motes
 will
 lie,
 network


effects,
 reliability,
 and
 reputation.


People
 are
 going
 to
 continue
 to
 solve


hard
 problems
 with
 agentic
 systems.


People
 are
 going
 to
 solve
 lucrative


problems
 with
 agentic
 systems.


Somebody
 is
 going
 to
 earn
 back
 the


trillion-dollar
 investments
 that
 we've


made.


Make
 sure
 that
 it's
 you.


Make
 sure
 that
 you
 are
 in
 control
 of


your
 own
 destiny.


You
 can
 have
 your
 cake
 and
 eat
 it,
 too.


You
 can
 have
 state-of-the-art
 features


and
 reliability
 without
 sacrificing
 your


autonomy.


Build
 on
 something
 you
 own.
 Build
 with


us.
 Thank
 you.


>> [applause]
</details>