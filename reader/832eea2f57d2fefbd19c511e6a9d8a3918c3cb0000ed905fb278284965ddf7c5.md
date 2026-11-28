---
author: AI Engineer
date: '2026-04-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=u0TOSBbAw7c
speaker: AI Engineer
tags:
  - cognitive-exhaust
  - read-only-ai
  - personal-ai
  - observer-ai
  - risk-mitigation
title: 读写分离式个人AI：深度解析‘认知废气’与‘观察者’价值
summary: 本次演讲介绍了‘认知废气’的概念，即认知活动的数字副产品。基于此，作者构建了一个名为Fulan的读写分离式个人AI系统，该系统仅能读取用户数据，不主动执行操作。演讲探讨了该系统的应用，如每周反思和社交连接建议，并重点强调了读写分离模式在安全性和分析纯粹性上的优势，同时审视了马赛克效应和致命三元组等潜在安全风险。结论指出，读写分离的AI（观察者）与代理式AI（执行者）是不同产品类别，前者为用户提供了独特的价值和更高的安全性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Fulan
media_books: []
status: evergreen
---
### 读写分离式个人AI：认知废气与观察者价值的深度解析

大家好，我叫 Shimon。今天，我将讨论一个能够了解你的个人AI系统，它不会替你或代表你采取任何行动，也不会毁掉你的生活。这听起来不错。在此过程中，我将探讨个人AI的风险以及像这样的只读AI系统如何减轻这些风险。让我们开始吧。

整个个人AI领域都痴迷于那些能代表你采取行动的“代理人”。我构建的东西有所不同。起点是六个数据源，仅供读取，没有任何写入权限。这种限制是完全故意的。

但首先，什么是“认知废气”？它们是什么？这是我为你的认知活动所产生的数字副产品定义的术语。就像汽车发动机的废气一样，单独来看，它们只是浪费，但如果你分析废气，就能诊断发动机。

<details>
<summary>Original English</summary>
Hi,
 my
 name
 is
 Shimon.


Today,
 I'll
 talk
 about
 a
 personal
 AI


system
 that
 knows
 you,
 but
 won't
 do


anything
 instead
 of
 you
 or
 on
 your


behalf,


and
 won't
 blow
 up
 your
 life.


So,
 that's
 good.


In
 the
 process,
 I'll
 talk
 about
 the


risks
 of
 personal
 AI
 and
 how
 read-only


AI
 systems
 like
 this
 one
 mitigate
 them.


Let's
 get
 started.


The
 whole
 personal
 AI
 space
 is
 obsessed


with
 agents
 that
 act
 on
 your
 behalf.


I
 built
 something
 different.


The
 starting
 point,
 six
 sources,
 read


access
 only,
 no
 write
 permissions.
 The


limitation
 is
 fully
 intentional.


But
 first
 of
 all,
 what
 are
 cognitive


exhaust
 fumes?
 What
 are
 they?


It's
 my
 term
 for
 the
 digital
 activity


that
 is
 a
 byproduct
 of
 your
 cognition.


Like
 exhaust
 fumes
 for
 a
 car
 engine,


individually,
 it's
 just
 waste,
 but
 if


you
 analyze
 the
 exhaust,
 you
 can


diagnose
 the
 engine.
</details>

### 认知废气的应用与系统架构

那么，让我们看看废气揭示了什么。这能让你做什么？我发现的三个主要用途是：意图-行动差距、注意力漂移和关系衰退。没有任何单一数据源能告诉你这些，而跨源能力是它们共同的特点。你的电子邮件客户端不知道你写了日记，你的任务管理器也不知道你在浏览什么。跨源信号才是产品。

让我们仔细看看这个系统。它就是Fulan。三个区域：源是只读的。AI从不写回它们。工作区是分析发生的地方。输出会进入一个单独的Obsidian库供我审查，但它不必是单独的Obsidian库。它可以是单独的Notion，单独的文本文件，单独的任何东西。可以是任何其他系统。这就是全部。

那么，关于应用呢？让我们从大卫·艾伦（David Allen）风格的“事务管理”（Getting Things Done）方法来旋转一下每周反思。基于这六个来源，AI会综合生成一份有时甚至是残酷的、关于你如何度过一周的反思。让我们看一个真实示例。一切都在Claude中运行。我已将此逻辑存储在weekly reflection {slash} command {slash} skill中。它的作用是启动一个Python脚本，获取所有来自只读源的数据，进行筛选，并根据我准备好的指定提示生成结构化输出。这需要一些时间。它会 ping Anthropic API 以获取那些结构化输出。然后（[鼻吸声]）一旦完成，它会创建一个Markdown文档供我审查。

现在，它已经运行完毕，给了我一个概述，我可以在Cursor中重新打开它，并将其转换为一个更易读的预览，然后看到它确实抓住了本周的主题。它确实触及了一些我需要思考的紧张和冲突。谈论我的承诺和关系，这方面主要是通过其遗漏来体现的，并强调了值得注意的时刻以及我喜欢思考的反思问题。简而言之，这不是一个生产力报告。它是一个关于你如何思考的反思，完全从“废气”中组装而成。

再举一个例子。我喜欢和别人讨论我正在阅读的内容，但有时我觉得不应该老是给同三个人发消息。于是，我问AI：“鉴于我最近的阅读，我的人际网络中谁应该和我讨论这个？”这就是跨源的魔力。四个数据源，没有一个是被设计来相互通信的，却结合在一起产生了一个你从任何单一工具中都无法获得的洞察。而且全部是只读的。没有发送任何东西。没有安排任何事情。只是一个供我选择行动的建议。

让我再次向你展示演示。再次强调，这是一个Claude技能，>>[叹气声]>> 但在这种情况下，我将大部分Claude技能的内部细节隐藏在跨源查询中，并以纯语言提问。这种纯语言知道它将自动激活特定的跨源查询技能，现在它会遍历我精心整理、我经常感兴趣的数据库，查找Vivaldi SQLite数据库中我阅读最多的文章，过一段时间，它会找出其中哪些文章阅读量最大、还在标签页中打开着，以及基于个人资料，哪些人可能会对此好奇。现在，这可能是最薄弱的部分。Clay MCP的运行耗时极长，但它会搜索我的CRM，或者说我的朋友关系系统，以便找到可能对这些话题的文章感兴趣的人。在这种情况下，是那些对AI感兴趣的人，或者欧洲科技界的人，或者教育界的人，而这些人恰巧也是我。现在，你可能会注意到，这会占用大量的上下文窗口中的token，所以你可能不想在一个不干净的会话中这样做，但如果它稍微弄乱了4.6版本100万的上下文窗口，然后你再清理一下，那也不是问题。所以，在这一点上，它正在从所有的Clay搜索中获取响应。它综合了我应该交流的人，并将他们映射到每篇文章。这就是它要做的事，或者说它即将要做的事。这需要Claude代码在背后做一些bash魔法，但如果你以自动模式或危险的磁盘权限运行它，你也可以摆脱这些。事实上，当我看看最初的结果时，那些看起来正是我可能想与之交谈、但还没有就我正在阅读的文章类型进行过交流的人。所以，谢谢你，Claude。没错，在这个例子中，它甚至找到了我正在阅读的、且在我人脉中的文章的作者，所以我应该联系一下他们。

<details>
<summary>Original English</summary>
So,
 let's
 see
 some
 examples
 of
 what
 the


exhaust
 reveals.


What
 does
 this
 enable
 you
 to
 do?


Three
 top
 uses
 I've
 found,


intention
 action
 gaps,


attention
 drift,


and
 relationship
 decay.


No
 single
 source
 tells
 you
 any
 of
 this,


and
 the
 cross-source


ability
 is
 what
 these
 have
 in
 common.


Your
 email
 client
 doesn't
 know
 what
 you


journaled.
 Your
 task
 manager
 doesn't


know
 what
 you're
 browsing.
 The


cross-source
 signal
 is
 the
 product.


Let's
 take
 a
 closer
 look
 at
 the
 system.


Here
 it
 is,
 Fulan.
 Three
 zones.
 The


sources
 are
 read-only.
 The
 AI
 never


writes
 back
 to
 them.


The
 workspace
 is
 where
 the
 analysis


happens.
 The
 outputs
 land
 in
 a
 separate


Obsidian
 vault
 for
 me
 to
 review,
 but
 it


doesn't
 have
 to
 be
 a
 separate
 Obsidian


vault.
 It
 could
 be
 separate
 Notion,


separate
 text
 files,
 separate
 anything.


Could
 be
 any
 other
 system.


And
 that's
 the
 the
 whole
 thing.


So,
 what
 about
 applications?


Let's
 start
 with
 a
 David
 Allen
 style


getting
 things
 done
 like
 spin
 on
 the


weekly
 reflection.


Based
 on
 the
 six
 sources,
 the
 AI


synthesizes
 an
 occasionally
 brutal


reflection
 on
 how
 you
 spent
 your
 week.


Let's
 look
 at
 a
 real
 example.


Everything
 runs
 in
 Claude.
 I've
 stored


this


logic
 in
 the
 weekly
 reflection
 {slash}


command
 {slash}
 skill.


And
 what
 it
 does
 is
 it
 launches
 a
 Python


script
 that
 gets


all
 the
 data


that
 come
 from
 the
 read-only
 sources,


and
 looks
 through
 them,
 and
 creates


structured
 outputs


with
 specified
 prompts
 that
 I've


prepared.


This
 takes
 a
 little
 bit
 of
 a
 while.
 It


pings
 the
 Anthropic
 API


to
 get
 those
 structured
 outputs
 back.


And
 [snorts]
 once
 it
 does,
 it
 will


create
 a
 markdown
 document
 that
 I
 will


be
 able
 to
 review.


This
 is
 now
 uh
 finished
 running,
 so
 it


gives
 me
 an
 overview,


and
 I
 can
 open
 it
 back
 up
 in
 Cursor,


and
 I'll
 convert
 it
 to
 a
 preview
 that's


more
 readable,


and
 see
 that
 in
 fact,
 it
 does
 hit
 the


themes
 of
 the
 week.


It
 does
 hit
 some
 of
 the
 tensions
 and


conflicts
 that
 I
 need
 to
 think
 about.


Talks
 about
 my
 commitments
 and


relationships,
 which
 is
 mostly
 notable


by
 its
 omissions,
 and
 highlights
 the


notable
 moments
 as
 well
 as
 reflection


questions
 that
 I
 like
 to
 think
 about.


In
 short,
 this
 is
 not
 a
 productivity


report.
 It's
 a
 reflection
 on
 how
 you're


thinking,
 assembled
 entirely
 from


exhaust.


Let's
 take
 another
 example.


I
 like
 to
 discuss
 what
 I'm
 reading
 with


others,
 but
 sometimes
 I
 think
 I


shouldn't
 keep
 messaging
 the
 same
 three


people
 about
 it.
 So,
 I
 asked
 the
 AI,


"Given
 my
 recent
 reading,
 who
 in
 my


network
 should
 I
 be
 discussing
 this


with?"


This
 is
 the
 cross-source
 magic.


Four
 data
 sources,
 none
 of
 which
 were


designed
 to
 talk
 to
 each
 other,
 combined


into
 an
 an
 insight
 you'd
 never
 get
 from
 any


single
 tool.


And
 all
 read-only.


Nothing
 was
 sent.
 Nothing
 was
 scheduled.


Just
 a
 suggestion
 for
 me
 to
 act
 on
 if
 I


choose.


Let
 me
 once
 again
 show
 you
 the
 demo.


Once
 again,
 this
 is
 a
 Claude
 skill,


>> [sighs]


>> but
 in
 this
 case,
 I've
 hidden


most
 of
 the
 guts
 of
 the
 Claude
 skill


into
 the
 cross-origin
 query,
 and
 ask
 for


the
 specific
 question
 uh


in
 plain
 language.


The
 plain
 language
 knows
 that
 it
 will


auto


that
 it
 will


activate


the
 specific
 skill
 for
 the
 cross-source


queries,
 and
 it
 now
 goes
 through
 the


databases
 that
 I've
 curated
 that
 I
 have


regular
 interest
 for,
 looks
 through
 the


Vivaldi
 SQLite
 database
 for
 the
 articles


that
 I've
 been
 reading
 the
 most,


and


after
 a
 while,
 it
 will
 figure
 out
 which


of
 these
 articles
 um
 are
 most
 read,


still
 open
 on
 tabs,


and
 which
 people
 might
 be
 curious
 about


it
 based
 on
 the
 profile.
 Now,
 this
 is


probably
 the
 weakest
 part.
 The
 Clay
 MCP


takes
 forever
 to
 run,


but
 it
 searches
 my
 CRM,


or
 my
 friend
 relationship
 system,
 I


suppose,
 so
 FRM,


for
 people
 who
 might
 be
 interested
 in


articles
 of
 on
 these
 topics.


Um


In
 this
 case,
 it's
 people
 interested
 in


AI,
 or
 people
 in
 European
 tech,
 or


people
 in
 education,
 which


coincidentally
 are
 three
 things
 that
 I


also
 am.


Now,


as
 you
 might
 notice,
 this
 takes
 up
 a
 lot


of
 tokens
 in
 the
 context
 window,
 so
 you


probably
 don't
 want
 to
 do
 this
 in
 a


session
 that
 is
 not
 clean,
 but
 it's
 not


a
 problem
 if
 it
 messes
 up
 a
 little
 bit


of
 the
 1
 million
 context
 window
 for
 4.6,


and
 then
 you
 clear
 it
 again.


So,
 at
 this
 point,
 it's
 getting


the
 responses
 from
 all
 of
 the
 Clay


searches.


It
 synthesizes
 the
 people
 that
 I
 should


talk
 to,


and
 it
 maps
 them
 to
 one
 article
 each.


That's
 what
 the
 or
 it's
 about
 to
 map


them
 to
 one
 article
 each.


Uh


this
 requires
 a
 little
 bit
 of


uh


bash
 sorcery
 on
 behalf
 of
 Claude
 code,


but
 if
 you're
 running
 it
 with
 auto
 to


auto
 mode,
 or
 dangerous
 disk


permissions,
 you
 can
 get
 rid
 of
 that
 as


well.


And
 indeed,
 when
 I
 take
 a
 look
 at
 the


first
 results,


those
 look
 like
 the
 people
 that
 I
 might


want
 to
 talk
 to
 that
 I
 haven't
 talked
 to


yet
 about
 the
 kinds
 of
 articles
 that


I've
 been
 reading.
 So,
 thank
 you,


Claude.


Right,
 in
 this
 case,
 it
 even
 found
 the


author
 of
 the
 article
 that
 I
 was
 reading


that's
 in
 my
 network,
 so
 I
 should
 give


them
 a
 whirl.
</details>

### 读写分离的价值主张与安全考量

简而言之，没有任何单一数据源了解这一切的全部。你的浏览器不知道你的联系人，你的CRM不知道你在阅读什么。而“废气”却知道。

那么，既然它如此有用，为什么还要保持只读呢？这是关于所涉及风险的问题。它是不对称的。只读错误的后果是零，我只需忽略它。而写入错误的后果是无限的。个人AI运行在高风险环境中：你的关系、你的事业、你的声誉。我宁愿错过自动发送的电子邮件，也不愿一次失误就毁掉我的生活。

但还有一个更微妙的哲学论证，近乎一种品味的问题。只读不仅更安全，它还能产生更好的分析。一旦你的AI写入你的数据源，废气就被污染了。你不再观察你的认知，你观察的是一个人类-AI混合体，你无法分辨哪些模式是你的。当然，观察者也会改变你的行为，但反馈循环是由你来调解的，而不是自动化的。你阅读反思，你决定怎么做。这与AI为你撰写草稿是不同的。而且，有人会说，你根本就不想让AI为你写草稿，你应该夺回你的主体性。我猜这对于在场的听众来说可能难以接受，但值得考虑。

此时，你可能会问：“为什么不把所有这些都放到一个只读挂载的开放Claude实例中呢？”我确实这么做过。关键在于：观察者（The observer）与代理人（The agent）相比，每次互动产生的价值要大得多。代理人能帮我节省30秒检查天气，而观察者却能告诉我，我最重要的项目已经逃避了两个星期。更不用说，数据泄露和认知污染的风险也更小。我在这里提出的论点是，只读模式并非通向真正代理人的垫脚石。它确实能帮助你把事情做好，但它解决了不同的问题，满足了不同的需求。它属于不同的产品类别。行业将只读模式视为一种你可以“毕业”的限制。我认为这是错误的。观察者和代理人是不同的工具，市长不是一个坏掉的管家。

所以，这就是价值主张。但我如果在这里就停下，那就对不住大家了。让我们戴上“偏执帽”。什么让我夜不能寐？让我们从“马赛克效应”开始。有一种叫做“马赛克效应”的现象，当你将许多零散的信息碎片拼凑在一起时，就能得到一幅画面。我自己的幻灯片资料完美地描述了这种安全风险。这种交叉引用既使系统有用，也使其成为一个毁灭性的目标。所以，要小心。

硬币的另一面，是Simon Willison提出的“致命三元组”。如果你不知道“致命三元组”，它是一种安全风险模型，结合了三个因素：私有数据、不可信内容和外部通信。我最初以为我们只打破了“致命三元组”的某一部分，但事实并非完全如此。它消除了自然的、信息外泄的通道，但第三个环节是任何与外部通信的能力，而shell访问仍然具备这一点。简而言之，这个系统并非防火墙，我也不这样声称。即使在最佳情况下，我仍然在发送数据给Anthropic，网络大部分是开放的，周围还有大量严格来说并不需要的信息。我并不声称这个系统是安全的。我只是说，我已经认真思考过它为何不安全，并且决定了哪些风险是我愿意承担的。这与“不知道”是不同的。最糟糕的安全姿态是那种你从未审视过的。

话虽如此，我仍然认为从中可以学到一些有价值的东西。你的数字废气是你拥有的、但却最少被利用的数据集。反思它，并利用它来提升你自己。感谢您的聆听。

<details>
<summary>Original English</summary>
In
 short,
 no
 source
 knows
 the
 whole
 of


this.
 Your
 browser
 doesn't
 know
 your


contacts.
 Your
 CRM
 doesn't
 know
 what


you're
 reading.


The
 exhaust
 does.


So,
 why
 keep
 it
 read-only
 if
 it's
 so


useful,
 after
 all?


Here's
 the
 thing
 about
 the
 risk


involved.
 It's
 asymmetric.
 The
 downside


of
 a
 read-only
 error
 is
 zero.
 I
 just


ignore
 it.


The
 downside
 of
 a
 write
 error
 is


unbounded.


And
 personal
 AI
 operates
 in
 the


high-stakes
 environment.
 Your


relationships,
 your
 career,
 your


reputation.


I'd
 rather
 miss
 out
 on
 automated
 emails


than
 have
 a
 misfire
 nuke
 my
 life.


But
 there's
 also
 a
 subtler
 philosophical


argument,
 almost
 a
 matter
 of
 taste.


Read-only
 isn't
 just
 safer,
 it
 produces


better
 analysis.
 The
 moment
 your
 AI


writes
 to
 your
 data
 sources,
 the
 exhaust


fumes
 are
 contaminated.
 You're
 no
 longer


observing
 your
 cognition.
 You're


observing
 a
 human-AI
 hybrid,
 and
 you


can't
 tell
 which
 patterns
 are
 yours.


Sure,
 the
 observer
 changes
 your


behavior,
 too,
 but
 the
 feedback
 loop
 is


mediated
 by
 you,
 not
 automated.


You
 read
 the
 reflection.
 You
 decide
 what


to
 do.
 That's
 a
 different
 thing
 from
 the


AI
 writing
 your
 draft.


And
 there's
 an
 argument
 to
 be
 made
 that


you
 don't
 want
 the
 AI
 to
 write
 your


draft
 in
 the
 first
 place,
 that
 you


should
 reclaim
 your
 agency.


Might
 be
 a
 hard
 sell
 for
 this
 crowd,
 I


think,
 but
 worth
 considering.


At
 this
 point,
 you
 might
 be
 asking,
 "Why


not
 throw
 all
 this
 into
 open
 Claude
 on
 a


read-only
 mount?"


Which
 I
 have.


Here's
 the
 thing.


The
 producer
 The
 observer
 produces
 more


value
 per
 interaction
 by
 a
 wide
 margin.


The
 agent
 saves
 me
 30
 seconds
 on
 a


weather
 check.


The
 observer
 shows
 me
 I've
 been
 avoiding


my
 most
 important
 project
 for
 2
 weeks.


Not
 to
 mention
 that
 there's
 less
 risk
 of


exfiltration
 and
 cognitive
 pollution.


The
 argument
 I'm
 making
 here
 is
 that


read-only
 isn't
 a
 stepping
 stone
 to


{quote}


real
 agents.
 It
 helps
 you
 do
 things


well,
 yes,
 but
 it
 fits
 a
 different
 gap,


serves
 a
 different
 need.


It's
 a
 different
 product
 category.


The
 industry
 frames
 read-only
 as
 a


limitation
 you
 graduate
 from.


I
 think
 that's
 wrong.


Observers
 and
 agents
 are
 different


tools,
 and
 mayor
 isn't
 a
 broken
 butler.


So,
 that's
 the
 value
 proposition.


But
 I'd
 be
 doing
 you
 a
 disservice
 if
 I


stopped
 here.


Let's
 put
 on
 the
 paranoid
 hat.


What
 keeps
 me
 up
 at
 night?


Let's
 start
 with
 the
 mosaic
 effect.


There's
 something
 called
 the
 mosaic


effect,
 where
 you
 put
 together
 a
 lot
 of


small
 pieces
 of
 information
 and
 you
 get


a
 picture.


My
 own
 slide
 copy
 describes
 the
 security


risk
 perfectly.


The
 same
 cross-referencing
 that
 makes


the
 system
 useful
 makes
 it
 a
 devastating


target.


So,
 careful
 there.


The
 other
 side
 of
 the
 coin,
 Simon


Willison's
 lethal
 triquetra.


In
 case
 you
 don't
 know
 the
 lethal


triquetra,
 it's
 a
 security
 risk
 model


that
 combines
 three
 factors:
 private


data,
 untrusted
 content,
 and
 external


communications.


I
 initially
 thought
 we
 only
 broke
 the


lethal
 triquetra,
 and
 it
 doesn't,
 not


fully.
 It
 removes
 the
 natural


exfiltration
 circle
 channels,
 but
 the


third
 leg
 is
 any
 ability
 to
 communicate


externally,


and
 shell
 access
 still
 has
 that.


In
 short,
 the
 system
 isn't
 fireproof,


and
 I'm
 not
 claiming
 that.
 Even
 in
 the


best-case
 scenario,
 I'm
 still
 sending


data
 to
 Anthropic


on
 a
 network
 that's
 mostly
 open,


with
 a
 lot
 more
 information
 lying
 around


that
 is
 strictly
 speaking
 required.


I'm
 not
 claiming
 the
 system
 is
 secure.


I'm
 claiming
 that
 I've
 thought
 about


where
 it
 isn't,
 and
 I've
 decided
 which


risks
 I'm
 willing
 to
 carry.


It's
 different
 from
 not
 knowing.


The
 worst
 security
 posture
 is
 the
 one


you
 haven't
 examined.


With
 that
 said,
 I
 still
 think
 there's


something
 worthwhile
 to
 be
 learned
 from


all
 this.


Your
 digital
 exhaust
 is
 the
 most


underused
 data
 set
 you
 own.


Reflect
 on
 it
 and
 use
 it
 to
 make


yourself
 better.


Thanks
 for
 listening.
</details>