---
author: AI Engineer
date: '2026-10-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LnQce-eHm8k
speaker: AI Engineer
tags:
  - model-context-protocol
  - database-security
  - text-to-sql
  - enterprise-ai
  - access-control
title: Oracle MCP 与数据库安全：为 AI Agent 筑牢数据防线
summary: Oracle 的 Jeff Smith 探讨了如何通过 MCP 将企业数据库安全连接至 AI Agent。他指出直接依赖自然语言生成 SQL 存在幻觉与成本风险，建议通过预制参数化报表、Schema 元数据注入与企业 SSO 角色绑定，在数据库层面实现深层数据安全过滤与高效运维。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Jeff Smith
companies_orgs:
  - Oracle
products_models:
  - Claude
  - Codex
  - Gemini
  - Data Guard
media_books: []
status: evergreen
---
### 开场与 Oracle AI 数据库的定位

>> 我是 Jeff，来自 Oracle。我的年龄几乎和 Oracle 公司一模一样。

有人知道 Oracle 是哪一年成立的吗？

和《星球大战》上映是同一年。

没错。

我从事数据库工具相关的工作大约有 25 年了。

我很早就明白了一个道理：无论你打造的工具多么出色，大家最终想要的还是 Excel 电子表格。

现在依然是这样吗？AI Agent 已经干掉 Excel 了吗？

他们之前发布了能对任何东西进行逆向工程的能力，对吧？然后他们立刻就对 Excel 进行了逆向工程。

所以，或许 Excel 依然地位稳固。

我们在展位上以及在街上遇到看到我穿 Oracle 夹克的路人时，被问到最多的问题——除了“我能要你身上这件夹克吗”之外——就是：究竟什么是 Oracle AI 数据库？

那么，现场有谁以前接触过、研究过或见过 Oracle 数据库吗？

现场有谁目前正在使用 Oracle 吗？

太棒了，谢谢大家。

那么，究竟什么是 Oracle AI 数据库？今天回答这个问题的唯一有效方式，其实就是去问 Claude。

我的 Agent 训练有素且表现规矩，所以它给出的回答相当不错。简单来说：数据库现在能够参与到你所有的 RAG 流水线中，因为我们在数据库内部原生支持了向量。

因此，无论你拥有的是财务数据、人力资源数据、ERP、物流运输、零售、政务还是医疗数据等等，只要你想在那个数据仓库、数据湖、数据泥潭，或是那个经过精细治理的数据库中查找信息，我们都可以在数据库内部直接将这些信息与数据一并向量化，并为你提供跨越所有这些数据的统一 SQL 接口。这样一来，你就不必仅仅为了 RAG 而把数据复制同步到八九个不同的平台上了。

刚才有人看到那个动作了吗？身手简直就像蜘蛛侠一样。

这意味着只需一个连接进数据库的 MCP 服务器，而我今天来这里正是为了聊聊 MCP。

刚才没接住，这次错过了。

我们为数据库添加的远不止向量能力。除了常规的关系表和列之外——非常感谢你，想要一双附赠的袜子吗？

谢谢大家。[笑声]

感觉你刚才那一下真该拿个奖品。

好的，谢谢。

30 年来，我们一直在向数据库添加各种数据类型和数据工作负载。因此我们支持所有这些特性，包括图。如果你热衷于 Graph RAG，我们同样可以在单个 Oracle 实例内部实现。

大家总喜欢拿 Oracle 开玩笑，觉得我们历史悠久；但这并不意味着我们停止了创新。我的意思是，我们每个月都在发明、构建和发布新功能。我们必须这么做，因为客户付给我们很多钱，他们期望获得相应的价值回报。

<details>
<summary>Original English</summary>
[music]

>> I'm
 Jeff.
 I'm
 from
 Oracle.
 I'm
 almost

[snorts]
 the
 exact
 same
 age
 as
 Oracle.

Does
 anyone
 know
 what
 year
 Oracle
 was

founded?

Same
 year
 Star
 Wars
 came
 out.

Yeah.

Um
 and
 I've
 been
 working
 with
 database

tools
 um

for
 about
 25
 years.

And
 I
 learned
 a
 truth
 very
 early
 on
 that

no
 matter
 how
 good
 of
 a
 tool
 you
 build,

at
 the
 end
 of
 the
 day
 what
 people
 want

are
 Excel
 spreadsheets.

Is
 that
 still
 true?

Has
 the
 agent
 killed
 Excel
 yet?

Well,
 they
 published
 the
 reverse

engineer
 anything,
 right?
 And
 then
 they

immediately
 reverse
 engineered
 Excel.

So,
 maybe
 Excel's
 still
 a
 thing.

Um
 the
 biggest
 question
 we've
 got
 at
 our

booth
 and
 from
 random
 people
 on
 the

street
 that
 see
 my
 Oracle
 jacket,
 other

than
 can
 I
 have
 your
 jacket,
 um
 is
 like

what
 is
 the
 Oracle
 AI
 database?
 So,
 who

in
 here
 has
 worked
 with
 or
 studied
 or

seen
 an
 Oracle
 database
 before?

Who
 in
 here
 is
 currently
 using
 Oracle?

Cool.
 Thank
 you.
 Um

so,
 what's
 an
 Oracle

AI
 database?
 Well,
 the
 only
 real
 way
 to

answer
 this
 question
 today
 is
 to
 ask

Claude.

Um

my
 agent's
 very
 well
 trained
 and

behaved.
 So,
 it
 actually
 had
 a
 pretty

good
 answer.
 The
 nutshell
 is

the
 database
 is
 now
 able
 to
 participate

in
 all
 of
 your
 rag
 pipelines
 because
 we

natively
 support
 vectors
 inside
 the

database.

So,
 if
 you've
 got
 financial
 data,
 HR

data,
 ERP,
 shipping,

um
 retail,

government,
 healthcare,
 whatever,
 if
 you

want
 to

look
 for
 information
 in
 that
 data

warehouse,
 that
 data
 lake,
 that
 data

sewer,
 that
 beautifully
 curated

database.

We
 can
 vectorize
 your
 information

alongside
 the
 data
 inside
 the
 database,

and
 we
 give
 you
 a
 single

SQL
 interface
 across
 all
 of
 that.
 So,

you
 don't
 have
 to
 replicate
 data
 across

eight
 or
 nine
 different
 platforms
 just

for
 your

Did
 you
 see
 that?
 That
 was
 like

Spider-Man.

Um

So,
 that
 means
 one
 MCP
 server

um
 into
 the
 database,
 and
 I'm
 here
 to

talk
 about
 MCP.

So,
 um

just
 see
 Oh,
 missed
 it
 that
 time.

It's
 not
 just
 vector
 that
 we've
 added
 to

the
 database.
 So,
 in
 addition
 to
 your

relational
 tables
 and
 columns,
 thank
 you

so
 much.
 Would
 you
 like
 a
 complimentary

pair
 of
 socks?

Yeah.
 [laughter]

Feel
 like
 you
 should
 have
 won
 a
 prize

for
 that.

Um

Yes,
 thank
 you.

Um

For
 30
 years,
 we've
 been
 adding
 um

data
 types
 and
 data
 workloads
 to
 the

database.
 So,
 we
 support
 all
 of
 these

things.
 Um
 also,
 graph.
 So,
 if
 you're
 a

fan
 of
 graph
 rag,

um

we
 can
 do
 that
 as
 well
 inside
 the
 single

instance
 of
 Oracle.

So,

people
 like
 to
 dig
 on
 Oracle
 cuz
 we're

old,
 that
 doesn't
 mean
 we've
 stopped

innovating.
 I
 mean,
 we
 we're
 inventing,

building,
 publishing
 new
 stuff

uh
 every
 month.
 We
 have
 to
 because

people
 are
 giving
 us
 lots
 of
 money,
 they

expect
 value
 in
 return
 for
 that.
</details>

### MCP 与数据库在 Agent 时代的核心价值

好，那么我今天真正想谈的，是关于 MCP 的内容。我们将探讨一些实际应用案例，因为我经常被问到的最大疑问就是：Agent、大语言模型和 MCP 固然很棒，但谁在乎数据库呢？这里的核心意义到底是什么？

对我来说，答案非常显而易见：你所有的业务数据、信息和知识都存放在数据库中，而 Agent 正是靠数据滋养的。那么，我们如何才能安全地将这些信息提供给它们，而不至于因为泄漏个人身份信息（PII）或酿成可怕后果而导致公司垮掉、最终不得不去国会听证会上接受质询？

我还想谈谈我们正在推动的技术进展。大家知道，MCP 是一个全新的协议，但他们几乎每三个月就会添加新特性。因此 Oracle 一直在与技术委员会保持沟通，并在新功能发布时第一时间跟进支持。

今天我们没有安排现场问答的时间，但我带了一些周边礼品。我想大部分应该已经发完了，如果你想要个包或袜子，后台还有一些数据库小毛绒玩偶，我们可以直接扔给你。

另外我也会分享一些产品路线图方面的内容。

原本这是一场一小时的演讲，但我被告知只有 20 分钟，实际上只有 18 分钟。我们在台上已经耽误了 2 分钟，接下来看看能讲多快。

好的。

我希望大家今天能带走的三点核心收获是：我们构建了什么、自然语言转 SQL（NL2SQL）存在的问题以及我们为提高其可靠性所做的尝试，最后是任何能帮助大家进行 Token 优化的经验分享。

<details>
<summary>Original English</summary>
All
 right.
 So,
 what
 I
 want
 to
 actually

talk
 about
 today

MCP,
 we're
 going
 to
 cover
 some
 uh

real-life
 use
 cases
 cuz
 that's
 the

biggest
 question
 I
 get
 is
 like

agents,
 LLMs,
 MCP
 great,
 who
 cares
 about

databases?
 Like,
 what
 what's
 the
 point

here?
 It
 And
 for
 me,
 it's
 very
 obvious.

I
 mean,
 like
 all
 of
 your
 data,

information,
 knowledge
 is
 inside
 a

database,
 and
 the
 agents
 thrive
 on
 on

data.
 So,
 how
 can
 we
 get
 that

information
 to
 them
 safely

without
 bringing
 the
 company
 down

because
 we've
 leaked
 PII
 or
 done

something
 horrible
 and
 end
 up
 in
 front

of
 Congress
 testifying
 about
 it.

I
 want
 to
 talk
 about
 uh
 the
 advancements

that
 we're
 pushing.
 You
 know,
 MCP
 is

brand
 new
 protocol,
 but
 they
 add
 stuff

almost
 every
 3
 months.
 So,

Oracle
 is
 there
 having
 these

conversations
 with
 the
 board
 and
 we're

trying
 to
 pick
 up
 the
 new
 features
 as

they
 come
 out.

And
 we
 don't
 have
 time
 for
 Q&A
 today,

but
 I
 do

I
 did
 bring
 some
 swag.
 I
 think
 most
 of

it's
 gone.
 If
 you
 want
 a
 bag
 or
 socks,

oh,
 we
 have
 some
 DB
 stuffies
 in
 the

back.
 We
 can

throw
 those
 at
 you.

Um
 I'll
 share
 some
 roadmap
 stuff
 as

well.

So,
 this
 is
 an
 hour
 talk
 and
 I
 was
 told

I
 have
 20
 minutes
 and
 then
 not
 really

just
 18.
 Let's
 see
 how
 fast
 we
 can
 go

cuz
 I've
 wasted
 2
 minutes
 on
 the
 podium.

All
 right.

So,
 the
 three
 things
 I
 want
 you
 to
 be

able
 to
 walk
 away
 with,
 what
 we've

built,
 um
 the
 problems
 with
 natural

language
 to
 SQL,
 and
 some
 things
 that

we're
 trying
 to
 make
 that
 more

trustworthy,

and
 then
 anything
 I
 can
 share
 with
 you

folks
 that
 might
 help
 with
 token

optimization.
</details>

### 业务报表工具化：规避 NL2SQL 风险的报表方案

好，来看应用场景。

我认为这往往是企业最后才会着手实施的场景，但我同样认为它是投资回报率最高的场景。

通常来说，负责管理数据库周边基础设施的人，才是最早去接入新技术的人群。所以，当我问“嘿，你想试试 MCP 服务器吗？”时，通常只有数据库管理员、网络管理员、系统管理员或 DevOps 工程师首先具备这种操作权限。因此他们会利用这些工具来简化自己的工作。

但如果你审视一家企业内部，会发现更多的是另一种角色——那些不断接到高级副总裁（SVP）、执行副总裁（EVP），甚至是最高管理层（CXO）夺命连环问的人：
- “我们上个月卖出了多少个零件？”
- “我们在这个地区的业绩表现如何？”
- “我们应该推行什么样的折扣率才能最大化促成用户清空购物车？”

诸如此类我假装自己理解的各种业务问题。通常发生的情况是，他们打开 BI Publisher，进入数据集市，开始制作电子表格，计算出答案并提交到某个会议上；然后某人便依据整理出的透视表和 Excel 电子表格做出极其重大的决策。

而且这类问题是永无休止的。大家并不是没有问题可问，而是根本没有足够的时间和人手来回答这些问题。每一秒都会冒出类似“如果我们尝试这个会怎样？尝试那个又会怎样？”的想法。生成式 AI 的绝妙之处就在于它是一个力量倍增器，对吧？我们现在终于有了时间和资源去回答这些无穷无尽的问题。

但问题在于：数据都留在数据库里，而整理这些报表表格的人，往往并不是 SQL 专家或数据建模架构师。他们理解业务逻辑，但他们根本看不出来笛卡尔积（cross join）在当前场景下完全不合逻辑。

因此，自然语言生成 SQL 虽然很棒，但我认为它也十分危险。大家听过那句“只要能编译通过，就直接发布上线”的玩笑话吗？工程师对此付之一笑，我们也跟着附和笑笑。我写了一条 SQL 查询，拿到了返回数据，太棒了，我查对了——不，你根本没有查出你以为自己想查的内容。大模型会频繁跑出看起来返回了正确数据、但实际上完全错误的查询。

尽管大语言模型在这方面越来越成熟，但依然会因为各种原因翻车。例如，我绝不会仅仅根据一段提示词以及模型返回的结果，就去信任 Codex、Claude、Gemini 或其中任何一个模型来决定我们要投资哪条业务线。

而且让它们这么做成本也很高，因为它们会通过暴力遍历你的数据字典和数据库，去搜寻回答这些问题所需的数据。所以这不仅不可靠，而且业务人员也并不清楚 Agent 和 MCP 代表我们在背后做了什么，同时获取这些数据还会耗费大量的 Token 和时间。

因此，我们在 Oracle 所做的一件事就是提出：作为一家企业、一个团队或一个群组，你们拥有 SharePoint、网络共享盘等各种载体，里面存放着多年积累下来的层层报表文件夹。每当有人提出这些业务问题时，你们查阅的就是这些既有报表。

既然如此，为什么不设法将它们接入到数据库和/或 MCP 服务器中，并像 Agent 可以调用的工具或 API 那样直接呈现出来呢？这样一来，Agent 就不必让大模型去凭空生成 SQL 查询，而是直接告知模型：“这里有现成可用的报表，你想要查看哪一个？”

这正是我们在 Oracle 实现的方案。我们允许你按需接入任意数量的报表。当然，你确实需要为此投入一些时间：你需要为这些报表撰写描述，而且我喜欢在描述中包含类似“这是一些示例问题”的内容，这样 Agent 就能判断“如果你遇到关于这方面的问题，这是一份很适合调用的报表”。我会对报表的含义以及所有入参进行详细描述，因此参数自然都是参数化的。

但是，报表底层运行的代码基本上是硬编码固定的。因此，大模型可能会因为选错报表而犯错，但它绝不会因为生成错误的 SQL 而捅娄子。这就直接减少了一个出错的环节。

在 MCP 工具的设计层面，我提供了名为 `list_reports` 和 `execute_reports` 的工具。即便我拥有 500 份报表，那也不会直接暴露为 500 个独立工具——否则会撑爆上下文窗口，Agent 也会觉得“这内容太多了，根本没法用”。

因此，当我提出一个问题时，模型可以说：“根据这个关键词短语，把所有符合条件的报表提供给我。”我拿到报表列表后，便可以执行其中某一份报表以获取返回数据。

这是在纯自然语言生成 SQL 之上的另一种方案。我们的 MCP 服务器不仅支持接收任意临时 SQL 和存储过程代码并在数据库中即时执行，同时也支持彻底关闭该功能，严格限制你只能调用自定义工具和预制报表。

对于上下文工程师而言，这里还有另一种工作模式：这些报表实际上代表了业务运作逻辑和数据模型的蓝图。因此，如果在通过 OAuth 2 认证的会话中具备相应的权限范围或角色，工具还可以向 Agent 展示该报表背后的 SQL 代码。这样一来，它就能学习到数据在系统中是如何组织的，从而在后续需要生成查询时，有大得多的概率能够一次性生成完全正确的 SQL。这基本上相当于你提供了一份 Markdown 文档，向它解释“我们上个月卖出的零件数量是如何统计出来的”。

最终查询结果顺利返回，我们的 Agent 会对其进行美观的格式化呈现。

现场有谁已经开始尝试 MCP 应用了吗？

看来有。我认为这个概念是在 7 月份的规范中引入的。根据我台上的小闹钟，这部分我大概 5 分钟之后会展开讲讲。

<details>
<summary>Original English</summary>
All
 right,
 use
 cases.

I
 think
 this
 is
 the
 last

use
 case
 that
 businesses
 end
 up

undertaking,
 but
 I
 also
 think
 it
 is
 the

biggest
 return
 for
 your
 buck.
 Um

generally
 the
 people
 managing
 the

infrastructure
 around
 the
 database
 are

the
 ones
 that
 get
 to
 hook
 up
 the
 new

technology.
 So,

when
 I
 say,
 "Hey,
 do
 you
 want
 to
 try
 an

MCP
 server?"

It's
 usually
 a
 database
 administrator,
 a

network
 administrator,
 a
 sysadmin,
 a

DevOps
 engineer
 that
 going
 to
 have
 the

ability
 to
 do
 that
 in
 the
 first
 place.

So,
 they'll
 use
 these
 tools
 to
 make

their
 lives
 easier.
 But
 if
 you
 look
 in
 a

company,

there
 are
 way
 more
 of
 these
 types
 of

people,
 the
 people
 that

get
 the
 questions
 from
 the
 SVP,
 the
 EVP,

God
 forbid
 the
 CXO
 saying,

"How
 many
 widgets
 did
 we
 sell
 last

month?
 How
 are
 we
 performing
 in
 this

region?

Um
 what
 discount
 rate
 should
 we
 run
 to

maximize
 um

people
 closing
 out
 their
 carts?
 All
 all

that
 fun
 stuff
 that
 I
 pretend
 to

understand."
 And
 so,
 what
 generally
 what

happens,
 they
 go
 into
 their
 BI

Publisher,
 they
 go
 into
 their
 data

marts,
 they
 they
 start
 building
 their

spreadsheets,
 they
 they
 pop
 out
 the

answer,
 and
 that
 ends
 up
 in
 a

in
 a
 meeting
 somewhere,
 and
 someone

makes
 very
 important
 decisions
 based
 on

the
 pivot
 tables
 and
 Excel
 spreadsheets

that
 have
 been
 compiled.

And
 these
 questions
 are

endless.
 Like

it's
 not
 that
 people
 run
 out
 of

questions
 [clears throat]
 to
 ask.
 They

don't
 have
 enough
 time
 and
 people
 to

answer
 those
 questions.

Like
 every
 second
 there's
 like,
 "Oh,

there's
 What
 if
 we
 try
 this?
 What
 if
 we

try
 that?"
 So,
 the
 beauty
 of

generative
 AI
 is
 like
 it's
 a
 force

multiplier,
 right?
 So,
 we
 had
 now
 have

the
 time
 and
 the
 resources
 to
 ask
 these

endless
 questions.

The
 problem
 is
 the
 data's
 in
 the

database,

and
 the
 people
 putting
 together
 these

spreadsheets,

>> [snorts]

>> they're
 not
 necessarily
 SQL

experts,
 data
 model
 architects.
 They

understand
 the
 business,

but
 they
 wouldn't
 recognize
 that
 a
 cross

join
 doesn't
 make
 sense
 for
 this

scenario.

So,

natural
 language
 to
 SQL
 is
 amazing,

but
 I
 think
 it's
 dangerous.
 Have
 you

ever
 heard
 the
 phrase,
 "If
 it
 compiles,

ship
 it?"

Engineers
 laugh
 about
 this.

We
 pretend
 to
 laugh
 along.
 Um

I
 wrote
 a
 SQL
 query,
 data
 came
 back.

Awesome,
 I
 got
 it
 right.
 No.

You
 didn't
 actually
 ask
 what
 you
 thought

you
 asked.
 The
 LLMs
 are
 going
 to

frequently
 run
 queries
 that
 look
 like

they're
 returning
 the
 right
 data,
 but

they're
 not.
 And
 there
 are
 various

reasons
 why
 the
 LLMs,
 although
 they're

getting
 better
 and
 better
 at
 this,
 are

still
 going
 to
 fall
 short.
 Like
 I
 would

not
 trust

Codex
 or
 Claude
 or
 Gemini
 or
 any
 of

these
 two
 decide

what
 business
 branch
 that
 we're
 going
 to

invest
 in
 XYZ
 just
 based
 on
 a
 prompt
 and

a
 and
 a
 thing
 that
 pops
 back.

It's
 also
 expensive
 to
 ask
 them
 to
 do

this
 stuff,
 too,
 cuz
 they're
 going
 to

brute
 force

your
 dictionary
 your
 your
 database

looking
 for
 the
 right
 data
 to
 answer

these
 questions.
 So,
 not
 only
 is
 going

to
 be
 unreliable
 and
 the
 people
 using

this
 these
 tools
 don't
 necessarily

understand
 what
 the
 the
 agents
 and
 MCPs

are
 doing
 on
 our
 behalf,
 but
 it's
 going

to
 take
 a
 lot
 of
 tokens
 and
 time
 to
 get

that
 data.
 So,
 one
 of
 the
 things
 we've

done
 at
 Oracle
 is
 said,
 "Hey,

as
 a
 business,
 as
 a
 team,
 as
 a
 group,

you've
 got
 a
 SharePoint,
 you've
 got
 a

network
 drive,
 you've
 got
 something

where
 there's

folders
 and
 folders
 and
 folders
 of

reports
 that
 you've
 compiled
 over
 the

years.

And
 these
 are
 the
 things
 that
 you
 look

at
 when
 people
 ask
 these
 questions.
 So,

why
 not
 find
 a
 way

to
 pipeline
 them
 into
 the
 database

and/or
 MCP
 server
 and
 present
 those

almost
 as
 like
 tools
 or
 APIs
 that
 the

agent
 can
 call.
 So,
 instead
 of
 the
 agent

tasking
 an
 LLM
 to
 generate
 a
 query,
 you

say,
 "Hey,
 these
 are
 the
 reports

available
 to
 you.
 Which
 of
 these
 would

you
 like
 to
 look
 at?"

So,
 that's
 what
 we've
 done
 at
 Oracle.

We
 allow
 you
 to
 take
 as
 many
 of
 these
 as

you
 want.
 Now,
 you
 do
 have
 to
 put
 some

time
 into
 this.

You'll
 need
 to
 describe
 the
 reports
 and

I
 like
 to
 include
 like,
 "Hey,
 here's

sample
 questions."
 You
 know,
 the
 agent

can
 say,
 "Hey,
 if
 you
 got
 a
 question

about
 this,
 this
 is
 a
 good
 report
 to

run."
 I
 describe
 what
 the
 report
 means.

I
 describe
 all
 the
 inputs,
 so
 of
 course

they're
 parameterized.

But,
 the
 code
 underneath
 the
 report
 is

more
 or
 less
 hard-coded.

So,
 the
 LLM
 might
 screw
 up
 by
 picking

the
 wrong
 report,
 but
 the
 LLM's
 not

going
 to
 screw
 up
 by
 generating
 the

wrong
 SQL.

So,
 it's
 just
 one
 less

plus
 place
 it
 can
 mess
 up.

Now,
 in
 terms
 of
 MCP
 tools,

I
 present

I
 present
 a
 tool
 called
 list
 reports
 and

execute
 reports.

So,
 I
 could
 have
 500
 reports,
 that's
 not

500
 tools.

That
 would
 That
 would
 blow
 out
 context

and
 then
 agent
 would
 be
 like,
 "This
 is

This
 is
 too
 much.
 This
 isn't
 useful."

So,
 when
 I
 ask
 a
 question,
 it
 can
 say,

"Using
 this
 key
 phrase,
 give
 me
 any

report
 that
 looks
 like
 this."
 I'll
 get
 a

report
 list
 back
 and
 then
 I
 can
 execute

one
 of
 those
 reports
 to
 get
 the
 data

back.

This
 is
 an
 option
 above

natural
 language
 to
 SQL.
 So,
 our
 MCP

servers
 definitely
 support
 taking

arbitrary
 ad-hoc
 SQL
 stored
 procedure

code
 and
 executing
 it
 on
 the
 fly
 against

the
 database,
 but
 they
 also
 support

turning
 that
 off
 and
 limiting
 you
 to

custom
 tools
 and
 reports.

And
 there's
 another
 mode

for
 the
 context
 engineers
 out
 there.

These
 reports
 represent
 like

the
 blueprint
 for
 how
 the
 the
 business

works,
 for
 how
 the
 data
 model
 works.
 So,

if
 you
 have
 the
 proper
 scope
 or
 role
 in

your
 OAuth
 2
 authenticated
 session,
 the

tool
 will
 also
 offer
 to
 show
 the
 agent

the
 SQL
 behind
 the
 report.

So,
 it
 can
 learn
 how
 your
 data
 is

organized
 in
 the
 system
 and
 then
 it's

going
 to
 have
 a
 much
 better
 chance
 at

one-shotting
 the
 right
 query
 when
 it

goes
 to
 generate
 it.
 So,
 you're

basically
 say,
 "Here's
 some
 markdown

explaining
 how
 we
 find
 out
 the
 number
 of

widgets
 we
 sold
 last
 month."

And
 of
 course,
 here
 comes
 the
 results

back
 and
 our

agent
 nicely
 formats
 that.

Who
 in
 here
 started
 playing
 with
 MCP

apps?

Yeah.
 So,
 that
 was
 I
 think
 you're

introduced
 in
 the
 spec
 in
 July.
 That's

something
 I'm
 going
 to
 talk
 about

later
 on,
 like
 5
 minutes
 based
 on
 this

little
 clock.

Um
</details>

### DevOps 与运维排障：只读权限与数据库层安全

好，第二个使用场景。对于 DevOps 工程师和技术支持人员来说，我们的平台非常知名，存在时间也很长了。相关的文档、PDF、GitHub 项目、Stack Overflow 提问以及我的博客文章都在网上公开着。大语言模型已经学习了所有这些资料，如果一条查询运行缓慢，它们很清楚该去排查什么。但我绝不会信任大模型去直接替我删除索引、甚至去创建索引，或者在数据库里擅自执行任何操作。我希望它给我提供建议，然后由我亲自去执行这些建议。

更有甚者，如果非必要，我根本不会让大语言模型或 Agent 进入生产环境。这听起来很疯狂吗？

那么，面对运行缓慢的生产系统，我该如何利用 Agent 或大模型来获取帮助呢？

在座的各位都有一个完全镜像生产环境的测试环境，对吧？

没有吗？

我们在 Oracle 有一项名为 Data Guard 的技术，它允许你配置一个只读的备用实例，你可以把报表和只读查询卸载分流到那里。因此，生产环境出现的性能问题极大概率也能在那里复现。你可以让你的 Agent 去发起攻击——不，攻击这个词不合适；不过有时候确实贴切——你可以让 Agent 去对那个更安全的环境进行盘问调查，尝试各种性能调优技巧。

因此，我倾向于给大模型只读权限，但这还远远不够。我还必须对它们进入系统后能做的事情加以严密限制，因为即便它们只能读取数据，也可能会读取到你不希望它们看见的内容。

我们可以通过几种不同的方式来实现这一点，但对我来说，实施数据库安全防护的最佳位置永远是在哪里？

在数据库本身。

如果你只在客户端工具层面构建安全机制，那么当某个积极过头的工程师决定换用另一个工具直接连上数据库时，会发生什么？他们直接就长驱直入了，对吧？但如果你把安全防护做在数据库层，在绝大多数情况下你都是安全无虞的。

Agent 和大语言模型非常擅长发现和解决性能瓶颈。这可能是我做起来最简单的一个演示，虽然今天没时间演示，但我已经写好了一个自定义工具。

这个工具包含 6 个不同的操作，允许 Agent 代表我去执行，其中之一就是收集基本用于分析数据画像的统计信息（statistics）。

我们拥有一个被称为基于成本的优化器（CBO）的组件。当你执行查询时，执行计划的生成并不是基于经验法则，而是根据数据的画像特征（例如某一列中有多少唯一值等等）计算出来的。统计信息越新、越准确，系统生成优质执行计划并获得良好运行时性能表现的概率就越高。

因此，我不会针对单一用途去生成 15 个零散的工具，而是创建三到四个跨分类的复合工具，每个工具都包含多个选项。

这样我的 Agent 就能识别出：“哦，这里有一个性能调优工具，它能做六件事。”其中一件事就是生成性能画像报告。我们有一项名为 AWR 的功能，我会允许它去生成一份报告；我允许它做的另一件事就是生成统计信息。

<details>
<summary>Original English</summary>
Okay.
 Use
 case
 number
 two.
 So,
 for

DevOps
 engineers,
 support
 folks,

our
 platform
 is
 very
 well
 known.
 It's

been
 around
 for
 a
 long
 time.
 The
 docs,

the
 PDFs,
 the
 GitHub
 projects,
 the
 Stack

Overflow
 questions,
 my
 blog
 posts,

they're
 all
 out
 there.
 The
 LLM's
 been

trained
 on
 it.
 They
 know
 what
 to
 look
 at

if
 a
 query
 is
 slow.
 But,
 I
 don't
 trust

an
 LLM
 to
 drop
 an
 index,
 to

build
 an
 index
 even,
 to
 do
 anything
 in

the
 database
 for
 me.
 I
 want
 it
 to
 give

me
 advice
 and
 then
 I'll
 action

that
 advice.

And
 then
 if
 anything,
 I'm
 not
 going
 to

let
 the
 LLM
 or
 the
 agent
 into
 production

at
 all
 if
 I
 don't
 have
 to.

Does
 that
 sound
 crazy?

So,
 how
 do
 I
 use
 an
 agent
 or
 LLM
 to
 get

help
 with
 a
 production
 system
 that's

running
 slow?

Everyone
 here
 has
 a
 test
 environment

that
 mirrors
 production,
 right?

No?

Um

we
 have
 a
 technology
 at
 Oracle
 called

Data
 Guard
 that
 allows
 you
 to
 have
 a

read-only
 standby
 instance
 where
 you
 can

offload
 like
 reports
 and
 read-only

queries
 to.
 So,
 there's
 a
 good
 chance

your
 performance
 issue
 would
 replicate

over
 there.
 You
 can
 have
 your
 agent
 go

attack,
 not
 attack,
 that
 not
 the
 right

word.
 That's
 the
 right
 word
 actually

sometimes.
 You
 can
 have
 your
 agent
 go

interrogate
 that
 safer
 environment
 to

investigate
 and
 try
 out
 different

performance

um

tricks.

So,
 I
 am
 looking
 to
 give
 the
 LLM's

read-only
 access,
 but
 that's
 not
 enough.

I
 also
 need
 to
 lock
 down
 what
 they
 can

do
 once
 they're
 in
 there
 cuz
 even
 if
 you

can
 only
 read
 the
 data,
 you
 might
 be

able
 to
 read
 the
 data
 you
 don't
 want

them
 to
 see.

Um

we
 can
 do
 that
 a
 couple
 different
 ways,

but
 for
 me,
 the
 best
 place
 to
 always

implement
 security
 for
 the
 database
 is

where?

At
 the
 database.

If
 you
 build
 security
 only
 into
 your

tools,
 what
 happens
 when

a
 zealous
 engineer
 decides
 to
 go
 pick
 up

another
 tool
 and
 point
 it
 at
 your

database,
 they
 just
 go
 straight
 in,

right?
 But
 if
 you
 put
 security
 at
 the

database
 layer,

more
 times
 than
 not
 you're
 going
 to
 be

okay.

The
 agents
 and
 LLMs
 are
 really,
 really

good
 at
 finding
 and
 fixing
 performance

issues.

This
 is
 probably
 the
 easiest
 demo
 for
 me

to
 do.
 I
 don't
 have
 time
 to
 do
 demo,
 but

I've
 written
 a
 custom
 tool.

This
 tool
 has
 six

different
 actions
 that
 I'm
 a
 cool
 with

it
 to
 do
 on
 my
 behalf,
 and
 one
 of
 those

is
 to
 collect
 statistics

that
 basically
 profiles
 the
 data.

We
 have
 something
 called
 a
 cost-based

optimizer.
 So,
 when
 you
 ask
 queries,
 the

plans
 that
 get
 generated,
 they
 don't
 get

generated
 based
 on
 rules
 of
 thumb.
 We

look
 at
 the
 profile
 of
 the
 data,
 like

how
 many
 unique
 values
 are
 in
 this

column.

Yada
 yada
 yada.
 The
 fresher
 and
 the

better
 the
 statistics
 are,
 the
 better

chance
 it's
 going
 to
 generate
 a
 good

execution
 plan
 and
 have
 a
 good

performance
 profile
 runtime.

So,
 I'm
 not
 generating
 15
 tools
 that
 are

single-use
 tools.
 I'll
 generate
 three
 or

four
 tools
 that
 cross
 categories,
 and

each
 of
 those
 tools
 have
 options.

So,
 my
 agent
 can
 see,
 oh,
 here's
 a

performance
 tuning
 tool.
 It
 can
 do
 six

things.
 One
 of
 those
 is
 like
 generating

uh

a
 performance
 profile
 report.
 We
 have
 a

feature
 called
 um
 AWR.
 I'll
 let
 it

generate
 a
 report.
 One
 of
 the
 other

things
 I'll
 let
 it
 do
 is
 is
 generate

statistics.
</details>

### Schema 探索与元数据注解：为 Agent 补全上下文

这与第一个使用场景紧密相关：即 Schema 探索与文档化。

天哪，我的时间快用完了。

自然语言生成 SQL 确实非常惊艳，围绕 AI 和数据库的大部分兴奋点也都集中在此。这完全合乎情理，因为 SQL 是从数据库获取信息最流行的方式，我们需要这些数据。但这在很多系统中也是一场噩梦。

在座的各位有谁是在过去 6 个月内入职新工作的吗？

你们茶水间的墙角里，难道贴着一张图表，上面把所有晦涩的概念都定义清楚、列出所有暗语代号、记录了所有内部笑话，并把数据模型讲解得明明白白吗？比如注明“嘿，我们的销售数据不在销售表里，而是在一张叫 `XHR_123` 的表里，因为 30 年前有个工程师觉得这样命名很酷”。

没错，通常这只是一个庞大的 Confluence 页面。

我们现在有了相应的工具，可以读取解析这些 Confluence 页面，生成上下文并在数据库已有的元数据之上，进一步构建 Schema 元数据文档。

所以这又是上下文工程的一项实践。我们希望能够直接向大语言模型提供你所交互的数据库环境的上下文信息，而不是指望它自行生成各种探测查询去逆向工程、渗透你的数据库以寻找数据。

如果你让它去找，它确实能找到数据，但这会花费很长时间，而且它会反反复复地搜寻。除非你们在所有人的 Agent 和大模型之间搭建了共享的企业团队级记忆，否则这纯粹是一种巨大的浪费。不知为何，新员工入职组织时遭受这种折磨，以前似乎并不是什么大问题；30 年前这还没有重要到非解决不可的地步，但现在既然有了 AI，我们就不能让可怜的机器人们受罪了。因此我们必须为它们提供所需的信息，降低使用数据库的门槛。这个功能的好处在于，这些信息全部采用通俗易懂的自然语言保存在数据库中，同样也能造福人类。

当你查看我们的工具时，会发现我们提供了一项名为 `schema_information` 的功能。比如我会说：“Codex 或 Claude，我现在有一个新环境，需要你去调查一下它的结构布局，找到这些内容并对信息进行总结。”

它会发现自己拥有一个 Schema 信息工具并开始调用。该工具返回的是压缩字典形式的 JSON 属性集合，而不需要模型亲自去跑一系列繁杂的查询——比如“展示所有表、展示所有列、展示所有注释，再从每张表里读取 5 行数据来看看数据长什么样”。我们直接把这些能力内置到工具中并做了优化，它始终返回格式一致的数据，并提供多种运行模式。

你可以选择详细、精简或中等模式——就像我的裤子尺码一样；同时它还支持过滤，你可以传入关键词，它就会专门检索数据中的特定内容。

>> [吸气声]

>> 然后我可以通过另一个名为 `retrieve_context` 的工具将这些内容提取出来，用这些信息进行 AI 向量检索；此外我还有一个新工具叫 `generate_annotations`。我可以将它指向你们现有的 SharePoint 站点，扫描你的 PDF、PPT、Excel 和 Word 文档，提取文本并归纳整理，然后再存回数据库中。

当你进行自然语言转 SQL 操作时，这也使得一次性生成正确 SQL 变得更加容易。

这就是在对数据表进行规范注解之后，数据在数据库中呈现的样子。

比如我每次跑步或骑行的数据都会同步到我的 Strava 账户中。作为一个技术宅，我针对这些数据开发了 API 并存储在我的数据库里。虽然他们的 Schema 已经描述得相当清晰，但它经常在不同的度量单位和时间格式之间来回切换，而且某些列包含的内容根本不是你望文生义所想的那样。因此我给全部字段都打上了注解。这样当我提问“下周我应该做哪种锻炼”时，它在查阅我个人历史运动记录时，凭借这些信息就能轻松得多地得出答案。

利用 MCP 实现这一点的绝妙之处在于：它是独立于具体 AI 和大模型的。只要 MCP 服务器和工具到位，它能无缝兼容所有大模型。

<details>
<summary>Original English</summary>
This
 ties
 in
 closely
 to
 the
 first
 use

case,
 schema
 exploration
 and

documentation.

Man,
 I'm
 running
 out
 of
 time.

So,

natural
 language
 to
 SQL
 is
 really

awesome.
 It's
 where
 most

of
 the
 excitement
 around
 AI
 and

databases
 lie,

which
 makes
 sense
 cuz
 SQL's
 the

most
 popular
 way
 to
 get
 stuff
 out
 of
 a

database.
 We
 need
 that
 data,

but
 it's
 a
 nightmare
 for
 a
 lot
 of
 these

systems.

Has
 anyone
 started
 a
 job
 in
 the
 last
 6

months?

Is
 there
 like
 a
 place
 in
 the
 break
 room

where
 they
 put
 on
 the
 corner
 like
 a
 a

diagram
 where
 all
 of
 the
 hard
 stuff
 is

defined,
 all
 of
 the
 code
 words
 are

listed,
 all
 of
 the

all
 of
 the
 inside
 jokes
 are
 documented,

where
 the
 data
 model
 is
 explained.
 Hey,

our
 sales
 aren't
 in
 a
 sales
 table,

they're
 in
 a
 table
 called
 XHR_123

because
 an
 engineer
 30
 years
 ago
 thought

that
 would
 be
 cool.

Yeah,
 it's
 a
 big
 Confluence
 page.

We
 have
 tools
 now
 that
 will
 let
 you

consume
 those
 Confluence
 pages
 and

generate
 context
 and
 document
 uh

schema

metadata
 over
 top
 of
 the
 metadata
 that's

already
 in
 your
 database.

So,
 it's
 another
 context
 engineering

exercise.
 We
 want
 to
 be
 able
 to
 deliver

to
 the
 LLM
 the
 information
 about
 the

database
 environment
 you're
 talking
 to

instead
 of
 relying
 on
 it
 to
 generate

queries
 to
 reverse
 engineer
 hack
 your

database
 to
 look
 for
 data.

It
 will
 find
 the
 data
 if
 you
 ask
 it,

it'll
 just
 take
 a
 long
 time,
 and
 it'll

look
 for
 it

multiple
 times,
 and
 unless
 you
 have

shared
 team
 enterprise
 memory
 across

everyone's
 agents
 and
 LLMs,
 it's
 just
 a

it's
 just
 just
 a
 huge
 waste.
 So,
 what

we're
 like
 with

for
 some
 reason
 it
 wasn't
 a
 big
 problem

to
 let
 new
 employees
 suffer
 when
 they

joined
 an
 org.

Like
 it
 wasn't
 it
 wasn't
 a
 big
 enough

problem
 to
 fix
 this
 issue
 30
 years
 ago,

but
 now
 that
 AI
 is
 a
 thing,
 we
 can't
 let

the
 poor
 bots
 suffer.
 So,
 we
 got
 to
 get

them
 the
 information
 they
 need
 to

to
 make
 it
 easier
 to
 use
 our
 databases.

The
 The
 nice
 thing
 about
 this
 feature
 is

it's
 all
 in
 plain
 English,
 it's
 in
 the

database,
 it
 it's
 going
 to
 help
 the

humans,
 too.

So,
 when
 you
 go
 look
 at
 our
 tools,
 we

have
 something
 called
 schema

information.
 So,
 I'll
 say,
 "Hey,

Codex,
 Claude,
 whatever,
 I've
 got
 a
 new

um
 environment.
 I
 need
 you
 to
 go
 look

into
 it
 and
 see
 how
 laid
 out,
 find
 this,

and
 let's
 go
 summarize
 the
 information.

It'll
 see
 that
 it
 has
 a
 schema
 info

tool,
 and
 it'll
 start
 using
 that,
 and

that
 returns
 back
 a
 compressed

dictionary

a
 set
 of
 attributes
 in
 JSON
 versus
 it

running
 queries.
 Hey,
 show
 me
 all
 the

tables,
 show
 me
 all
 the
 columns,
 show
 me

all
 of
 the
 comments.
 Let's
 go
 read
 five

rows
 out
 of
 each
 table
 to
 see
 if
 the

data
 has
 what
 we
 looks
 like.
 You
 know,

we
 just
 kind
 of
 built
 that
 into
 the

tool,

optimized
 it,
 and
 it
 always
 returns
 the

same
 data,
 and
 it
 has
 multiple
 modes.

You
 can
 go
 verbose,
 slim,
 medium,
 just

like
 my
 pants,
 and
 uh

it's
 got
 filtering.
 So,
 you
 can
 give
 it

keywords,
 and
 it
 just
 looks
 for
 specific

things
 in
 the
 data.

>> [snorts]

>> And
 then
 I
 can
 pull
 that
 back
 out

with
 another
 tool
 called
 retrieve

context,
 where
 I
 can
 use
 that

information
 to

do
 AI
 vector
 search,
 but
 I
 have
 another

new
 tool
 called
 generate
 annotations.

So,
 I
 can
 point
 it
 to
 that
 SharePoint

site
 that
 you
 have,
 scan
 in
 your
 PDFs,

your
 PowerPoints,
 your
 Excel,
 your
 Word

docs,

um
 and
 store
 those
 in
 um
 or
 pull
 the

text
 out,
 organize
 it,
 and
 and
 put
 it

back
 into
 the
 database.

This
 is
 also
 it's
 easier
 to
 one-shot
 SQL

queries
 when
 you
 have
 natural
 language

to
 SQL
 exercises.

This
 is
 what
 the
 data
 looks
 like
 in
 the

database
 after
 I've
 properly
 annotated
 a

table.

So,
 anytime
 I
 do
 a
 run
 or
 a
 bike
 ride
 or

whatever,
 it
 goes
 into
 my
 Strava

account.
 I'm
 a
 nerd,
 so
 I
 have
 an
 API
 on

that
 data,
 and
 I
 store
 it
 in
 my

database.
 And
 their
 schema
 is
 fairly

well
 described,
 but

it
 jumps
 between
 like
 units
 of
 measure

and
 time,
 and
 some
 of
 the
 columns
 don't

have
 what
 you
 think
 they
 do.
 So,
 I
 just

have
 that
 all
 annotated,
 and
 so
 when
 I

start
 asking
 questions
 about,
 "Hey,
 what

kind
 of
 workout
 should
 I
 do
 next
 week?"

and
 it
 looks
 at
 my
 personal
 workout

history,
 it
 it
 gets
 to
 that
 much
 easier

with
 this
 with
 this
 info.

And
 the
 nice
 thing
 about
 this
 with
 MCP

is
 AI
 and
 LLM
 agnostic.
 It's
 going
 to

work
 for
 everything
 as
 long
 as
 the
 MCP

server
 and
 the
 tools
 are
 there.
</details>

### 数据安全与权限管控：深层数据安全与未来展望

好的，接下来可能是我今天讲的最重要的内容：安全。

我只剩 40 秒了，那我们就以安全收尾。

在向用户返回任何数据之前，我们必须清楚到底是谁在查看数据库中的信息。我被允许查看的信息，与我的同事 Tara 能够查看的数据将大不相同。

当我在数据库中使用 Claude、Codex、Gemini 或我自己搭建的 LangChain 框架时，我们不会使用数据库本地认证来放行 Agent 去执行操作，而是将你接入到企业的单点登录（SSO）中——例如 Azure AD。它会返回一组权限范围（scopes）和角色列表，明确你在组织内的职能。这样数据库便可以通过代码设定规则：“哦，Jeff 是一名 HR 经理，他有权查看所有人的薪资。”

但组织外的任何其他人都无权查看。

因此，当自然语言问题被转化为 SQL 并在数据库上执行时，数据库会在结果集返回给 Agent 之前，动态剥离掉敏感数据。我们把这项能力称为“深层数据安全”（deep data security）。

我的时间到了。核心内容我都讲完了。我们在 Oracle 对安全性进行了深入的思考。我们希望这一切变得简单，但更要确保其足够安全。

我们正在构建 MCP 应用，以便让数据库图形界面能够直接嵌入到你的 Agent 内部，这将在今年晚些时候推出。

>> [吸气声]

>> 我们还支持 Skills，并且 Skills 可以通过工具来提供。我们支持自动化 RAG 流水线：你可以通过命令行将文档摄入进来，然后通过 MCP 工具将向量和文档切片直接传送回你的 Agent。

如果你想深入了解相关内容，我们的网址非常好记：`oracle.com/mcp`。

我马上要去赶飞机回北卡罗来纳州的罗利市了。如果你在 LinkedIn 上搜我，我就是那个 Jeff Smith。我的同事们都在 Oracle 展位上，那里还有更多周边礼品。如果刚才没领到小玩偶，现场还有很多。

谢谢大家！

>> [掌声与音乐]

<details>
<summary>Original English</summary>
Okay,
 so
 this
 might
 be
 the
 most

important
 thing
 I
 talk
 about,
 security.

So,
 I
 got
 40
 seconds.
 We'll
 just
 end
 on

this.

Um

we
 need
 to
 know
 who
 is
 looking
 at
 the

information
 in
 the
 database
 before
 we

return
 any
 data
 back
 to
 them.

The
 information
 I'm
 allowed
 to
 see
 is

going
 to
 be
 much
 different
 than
 what
 the

data
 my
 colleague
 Tara
 is
 going
 to
 be

able
 to
 see.
 And
 when
 I'm
 in
 the

database
 using
 Claude
 or
 Codex
 or
 Gemini

or
 my
 own
 homegrown
 LangChain
 framework,

we
 don't
 use
 database
 authentication
 to

let
 the
 agent
 go
 in
 and
 do
 stuff.
 We

pipe
 you
 through
 your

organization
 single
 sign-on.
 So,
 like

Azure
 AD,
 which
 is
 going
 to
 return
 a

list
 of
 scopes,
 which
 is
 going
 to
 return

a
 list
 of
 roles
 that
 describe
 your
 role

in
 the
 organization,
 and
 the
 database

can
 be
 coded
 to
 say,
 "Oh,
 Jeff
 is
 an
 HR

manager.
 He's
 allowed
 to
 see
 everyone's

salary."

But
 no
 one
 else
 outside
 that
 org
 can.

So,
 when
 we
 the
 natural
 language

questions
 get
 generated
 to
 SQL,
 when

that
 SQL
 runs
 against
 the
 database,
 the

database
 dynamically
 strips
 data
 from

the
 result
 set
 before
 it
 comes
 back
 down

to
 the
 agent.
 We
 call
 that
 deep
 data

security.

I'm
 out
 of
 time.

I
 covered
 the
 big
 stuff.

We
 thought
 a
 lot
 about
 security
 at

Oracle.
 We
 want
 this
 stuff
 to
 be
 easy,

but
 we
 want
 it
 to
 be
 safe.

We
 are
 building
 MCP
 apps,

so
 you
 can
 have
 the
 database
 interface

GUI
 directly
 in
 your
 agent.
 That's

coming
 later
 this
 year.

>> [snorts]

>> We
 have
 skills.

The
 skills
 can
 be
 delivered
 via
 tools.

We
 support
 automated
 rag
 pipelines.
 You

can
 use
 a
 command
 line
 to
 suck
 documents

in
 and
 then
 an
 MCP
 tool

pipe
 the
 the
 vectors
 and
 the

the
 snippets
 of
 the
 the
 documents
 back

to
 your
 agents.

And
 when
 you
 want
 to
 learn
 more
 about

any
 of
 this
 stuff,
 we
 have
 the
 easiest

URL
 oracle.com/mcp.

I'm
 leaving
 to
 get
 on
 a
 plane
 to
 fly

back
 to
 Raleigh,
 North
 Carolina,
 but
 if

you
 find
 me
 on
 LinkedIn,
 I'm
 that
 Jeff

Smith
 and
 my
 colleagues
 are
 down
 at
 the

Oracle
 booth
 and
 they
 have
 more
 swags.

If
 you
 missed
 out
 on
 the
 plushy,
 we
 have

more.
 Thanks,
 everyone.

>> [applause and music]
</details>