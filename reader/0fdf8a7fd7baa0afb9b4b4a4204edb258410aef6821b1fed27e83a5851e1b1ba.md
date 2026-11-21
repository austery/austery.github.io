---
author: AI Engineer
date: '2026-10-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KtBivPzmOM8
speaker: AI Engineer
tags:
  - ai-agent
  - context-engineering
  - hybrid-search
  - agent-architecture
title: 构建定制化智能体测试框架与反洗钱应用实践
summary: 主讲人通过银行反洗钱可疑交易场景，探讨构建自主智能体测试框架（harness）的必要性。提出针对特定业务问题简化并定制测试框架，涵盖内存管理、指令层级及混合检索等关键组件。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/6 -->

### 工作坊介绍与环境准备

[音乐]

大家好。呃，感谢大家来参加这个环节。呃，我们——这将是一个关于 agent harness 的环节。我们的时间不多，只有一小时的时间。所以，嗯，希望我们有时间聊很多大家感兴趣的内容，并且这个环节基本上会是呃像我先讲个 10 到 15 分钟左右，介绍我们在工作坊中要讨论和解决的主题。大家可以通过二维码或网站获取工作坊指南；如果你不想听我讲，觉得我很无聊或怎么样的，你可以在我讲的同时，呃，自己开始进行工作坊。但基本上网站上就是这么运作的：你只需要嗯用你的 GitHub 账号登录，然后就会自动收到该代码仓库的邀请。工作坊托管在 Codespaces 上。所以你可以直接基于它创建一个 Codespace 呃，你会自动收到邀请以访问工作坊本身，你只需要在那里创建一个 Codespace 呃打开 GitHub Codespaces，然后就可以准备就绪并开始工作坊了。呃，所以我把二维码再放一次，呃，给那些想扫码的人，然后我就要开始了。

<details><summary>Original English</summary>
[music]

Hi.
Hi
everyone.
Uh
thank
you
for
coming

to
this
session.
Uh
we're
it's
going
to

be
a
session
about
agent
harnesses.
We

don't
have
a
lot
of
time.
It's
only
one

hour
session.
So
um
hopefully
we
have

time
to
talk
about
a
lot
of
things
that

that
you
guys
are
interested
in
and
the

the
session
essentially
is
going
to
be

uh
like
me
talking
like
10
15
minutes

about
the
topics
that
we're
going
to

talk
about
and
solve
in
the
workshop.

You
have
the
workshop
instructions
in
a

QR
code
or
in
a
website
and
if
you
don't

want
to
listen
to
me,
you
think
I'm

boring
or
something,
you
can
start
uh
on

your
own
on
the
workshop
as
I'm

speaking.
But
essentially
this
is
this

is
what's
uh
happening
on
the
website.

You
just
um
sign
up
with
your
GitHub

handle
and
then
you
will
automatically

receive
an
invitation
to
the
repository.

The
workshop
is
hosted
on
code
spaces.

So
you
can
just
like
create
a
code
space

out
of
that
uh
and
you
will
receive
an

invitation
automatically
to
get
access

to
the
workshop
itself
and
you
just
have

to
create
a
a
code
face
over
there
uh

opening
GitHub
code
spaces
and
you're

good
to
go
and
and
and
begin
with
the

workshop.
Uh
so
I'll
just
put
the
QR

code
uh
one
more
time
for
those
of
you

who
were
uh
who
who
want
to
take
that

and
I'll
I'll
get
started.
</details>

好的，太好了。呃，如果大家有任何问题，我的同事 Richmond 也在那边。他会走过各个桌子。如果大家有任何问题，举手即可，他也可以提供帮助。

<details><summary>Original English</summary>
Okay,
perfect.
Uh,
if
you
have
any

questions,
also
my
colleague
Richmond
is

over
there.
He's
going
to
go
through
um,

you
know,
everyone's
uh,
table.
If
you

have
any
questions,
just
raise
your
hand

and
he
can
help
out
as
well.
</details>

好的，就是这样。另外，那个网站，我是说，你们可以访问 workshopwaitingroom.com。我为那个域名花了很多钱，所以，呃，去用用看吧。

<details><summary>Original English</summary>
Yeah,
there
you
go.
Also,
the
website,
I

mean,
you
can
go
to
the
website

workshopwaiting
room.com.
I
paid
too

much
money
for
that
domain.
So,
uh,
use

it.
</details>

### 自我介绍与工作坊议程

好的。那么，我是谁？我叫 Nacho，Nacho Martinez。我是一名 AI 开发者布道师，内心深处也是一名数据科学家。如果大家对我感兴趣，可以在 YouTube 上搜索我。我有播客，有工作坊，应有尽有。我就不多谈我自己了。嗯，不过只有一件事，呃，我们最近和吴恩达（Andrew Ng）以及 DeepLearning.AI 联合发布了一门课程，内容是关于构建自适应 AI agent，这也是我们今天将要讨论的子组件之一。如果你对可以在模型上做哪些事情让它变得更好、随着时间推移自适应并持续学习特别感兴趣，可以去看看那门课程。那是一门免费课程，呃，在 Google 上就能搜到的 1 小时课程。

<details><summary>Original English</summary>
Okay.
So,
who
am
I?
My
name
is
Nacho

Nacho
Martinez.
I
am
an
AI
developer

advocate
and
a
data
scientist
by
heart.

And
if
you're
interested
in
anything

about
me,
just
find
me
on
YouTube.
I

have
podcasts,
I
have
workshops,
I
have

everything.
Not
going
to
go
too
much

into
myself.
Um
just
one
thing
though
uh

we
re
recently
released
a
course
with

Andrew
Ang
and
deep
learning
AI
about
uh

building
adaptive
AI
agents
which
is
one

of
the
subcomponents
that
we're
going
to

talk
about
today.
And
you
know
if
you're

particularly
interested
in
the
things

that
you
can
do
on
a
model
to
make
it

better
and
adapt
over
time,
learn
over

time,
just
check
out
that
course.
is
a

free
course
uh
a
1hour
course
that
you

can
check
out
on
on
Google.
</details>

那么我们今天呃要讲些什么呢？正如我所说，我们的时间不多。所以我会尽量快一点。嗯，但这些就是我们要讨论的内容。首先，什么是 agent stack（智能体技术栈）？呃，agent stack 的各个组件是什么？AI 应用可以采取哪些不同的形态？AI agent 是什么？以及什么是 agent harness？构建或围绕 agent harness 进行开发、而不是直接与 AI agent 或直接与 LLM 模型交互的主要动因是什么？还有 agent harness 的所有子组件，比如内存（memory）、上下文工程（context engineering）、内存工程（memory engineering）以及所有这些东西。

<details><summary>Original English</summary>
So
what
are
we
going
to
go
uh
through

today?
Like
I
said,
we
don't
have
a
lot

of
time.
So
I'm
going
to
try
to
be

quick.
Um
but
these
are
the
things
that

we're
going
to
talk
about.
First
of
all,

what
is
the
agent
stack?
Uh
what
are
the

components
of
an
agent
stack?
What
are

the
different
shapes
that
an
AI

application
can
take?
What
an
AI
agent

is?
And
what
is
the
agent
harness?
what

is
the
main
motivation
of
building
or

working
around
agent
harnesses
rather

than
working
with
AI
agents
or
with
an

LLM
model
directly
and
you
know
all
the

subcomponents
of
an
agent
harness
like

for
instance
memory
context
engineering

memory
engineering
and
all
these
things.
</details>

### 银行可疑交易案例与 Harness 的必要性

因为他们告诉我会有很多来自金融领域的人，呃，比如很多在华尔街工作的人，呃，所以我把这个工作坊调整为围绕一家银行来展开，对吧？这个工作坊的核心前提是这样的：我们如今经常听说，比如 OpenAI 启动了 10,000 个 agent 或 5,000 个 agent 来解决这个问题，用 10,000 个 agent 来解决这个耗费了一百年、两百年的数学难题。问题在于，这些 agent 是自主的。在得出结论或答案之前，它们没有任何人在回路（human-in-the-loop），对吧？因此，agent 本身并不具备独立做到这一点的能力。为什么？因为我的意思是，上下文窗口是有限的。内存组件是大语言模型本身并不具备的东西。所以所有这些东西我们都需要自己来实现，才能让这些 agent 能够自主地连续解决这些问题 10 个小时、100 个小时，对吧。所以现在的思路是，很多人都在聚焦于“好，我们拥有这些前沿模型”，但我的想法是，好的，我们不需要把精力过度放在前沿模型上，我们可以使用它们，但让我们专注于 harness，这才是真正有趣的部分，也是你可以真正进行越来越多定制的部分。

<details><summary>Original English</summary>
So
because
they
told
me
that
there's

going
to
be
a
lot
of
people
from
uh

financial
uh
like
a
lot
of
people
that

work
in
Wall
Street
uh
I
adapted
this

workshop
to
be
around
a
bank
right
so

the
idea
is
that
the
main
premise
of
the

workshop
is
this
we
are
hearing
lots
of

the
uh
nowadays
like
open
AAI
is

launching
10,000
agents
or
5,000
agents

to
solve
this
problem
10,000
agents
to

solve
this
mathematical
problem
that
was

solved
like
in
a
100
years
200
years.

The
thing
is
that
these
agents
are

autonomous.
They
don't
have
any
human
in

the
loop
until
they
arrive
to
uh
to
the

conclusion
or
the
answers,
right?
So
the

agents
themselves
don't
have
the

capacity
to
do
this.
Why?
Because
I
mean

the
context
window
is
limited.
The

memory
components
are
something
that
a

large
language
model
doesn't
have

inherently.
So
all
these
things
we
need

to
implement
ourselves
to
make
these

agents
able
to
solve
all
these
problems

for
10
hours
100
hours
autonomously

right.
So
the
idea
is
that
a
lot
of

people
are
making
focus
on
okay
we
have

these
frontier
models
but
my
idea
is

that
okay
we
don't
need
to
focus
so
much

on
the
frontier
models
we
can
use
them

but
let's
work
on
the
harness
which
is

the
interesting
part
and
the
things
that

you
can
actually
customize
uh
more
and

more.
</details>

因此在这个应用中，它的设定是一家中型银行，有时候会遇到很多呃可疑交易，它们被分为五种不同的类型。举例来说，如果你有一笔 100 万美元的交易进入银行，然后自动地、神奇地呃一连三天你在自动取款机上提取大约 5 万美元。那是很可疑的，对吧？因为你为什么会存入 100 万美元，然后像那样分散提取呢。所以思路是，我们有这样一家中型银行，它有大量交易，而这些交易需要某种程度上被自主决策，或者至少被标记出来，从而让真正就职于该银行的人类员工需要花在实际查看这些事情上的时间更少。

<details><summary>Original English</summary>
So
on
this
application,
the
idea
is
that

it's
a
medium-sized
bank
that
has
lots

of
uh
you
know
suspicious
transactions

uh
sometimes
and
they
are
categorized

into
five
different
types.
So
for

example,
if
you
get
like
a
million

dollar
transaction
that's
coming
into

your
bank
and
automatically
and

magically
uh
for
three
days
you're

making
like
$50,000
withdrawals
on
an

ATM.
That's
suspicious,
right?
because

why
would
you
like
put
$1
million
in
and

then
just
like
distribute
uh
like
that.

So
the
idea
is
that
we
have
this
medium

by
uh
medium-sized
bank
that
has
lots
of

transactions
and
these
transactions
they

need
to
be
kind
of
autonomously
decided

or
at
least
flagged
so
that
a
human
that

actually
works
in
the
bank

needs
to
spend
less
time
actually

looking
at
these
things
you
know.
So
</details>

### Agent Stack 架构解析

那么让我们来看一点理论。什么是 agent stack，对吧？当我们与 AI agent 对话时，我们通常是在与应用层对话，对吧？呃，我们所交互的要么是一个界面、一个聊天机器人、一个移动应用等等。然后我们有模型本身，它是推理的核心，我们对其做出的决策没有任何发言权。呃，接着我们还有支撑这一切的基础设施，然后是算力。但我们今天重点关注的是其中的数据部分。数据非常重要，因为我们能够操纵和围绕其开展工作的一切都在这一层。其他部分我们能掌控的较少，对吧？特别是当我们使用的是不属于我们自己的第三方模型时。

<details><summary>Original English</summary>
let's
go
to
the
theory
a
little
bit.

What
is
the
agent
stack?
Right?
When
we

talk
with
an
AI
agent,
we
typically
are

talking
with
the
application
layer,

right?
Uh
what
we
interact
with
either

an
an
interface,
a
chatbot,
an
a
mobile

application
etc.
Then
we
have
the
model

itself
which
is
the
reasoning
core
the

the
you
know
we
don't
get
any
say
in

what
the
decisions
are.
Uh
and
then
we

have
also
the
infrastructure
that

supports
it
all
and
then
the
compute.

But
what
we
are
going
to
focus
about

today
is
the
data
part
of
it.
And
the

data
is
very
important
because

everything
that
we
can
manipulate
and

work
around
is
on
this
part.
The
other

parts
we
get
less
control
over
them,

right?
Especially
if
we're
using
like
a

third
party
uh
model
that
isn't
ours.
</details>

所以数据层就是我们今天呃所关注的，对吧？首先，我们有 agent 循环（agent loop），这可以说是 AI agent 中最重要的部分之一。呃，agent 循环基本上负责驱动整个系统运转。呃，并且它也是可定制的。在数据内部，你还有类似网关（gateway）和 MCP，以便你可以将其连接到第三方外部数据源。你还拥有内存层，我们稍后会讨论它，以及本质上的一些上下文工程部分，它们能让你自动总结、压缩并缩减模型的工作上下文窗口。最后还有一些工具（tools）和技能（skills）呃，借此我们可以做一些有趣且智能的事情，从而基本上能够将上下文窗口保持在受限范围内。这是本次工作坊的核心主旨之一。

<details><summary>Original English</summary>
So
the
data
layer
is
what
we
focus
about

uh
today,
right?
First
of
all,
we
have

the
agent
loop
and
this
is
arguably
one

of
the
most
important
parts
of
an
AI

agent.
Uh
the
agent
loop
is
in
charge
of

essentially
driving
the
whole
thing.
Uh

and
it's
customizable
as
well.
And

inside
the
data,
you
also
have
like
a

gateway
and
MCP
so
that
you
can
connect

it
to
third
party
external
data
sources.

You
also
have
the
memory
layer
which
we

will
talk
about
later
and
essentially

also
some
context
engineering
uh
parts

of
it
that
let
you
automatically

summarize
and
compact
and
shrink
the

working
context
window
of
a
model

and
finally
also
some
tools
and
skills

uh
which
we
can
do
some
interesting
and

intelligent
stuff
so
that
we
can

essentially
keep
the
context
window

limited.
This
is
one
of
the
main
ideas

of
the
workshop.
</details>

### 从自动化到自主性：Agentic 系统

现在，通常我们所交互的应用要么是这四类的组合，对吧？LLM 聊天机器人，这种非常简单。很多人就是创建一个 AI 应用，创建一个聊天机器人以便能和它对话。还有 RAG 应用，本质上就像一种美化了的向量搜索。然后你还有 LLM 驱动的工作流以及 AI agent。而通常我们大多数人使用的——顺便举手看一下，谁不用像 Claude Code 等等这样的 AI agent？当然了——所以 Claude Code 等等所有这些系统都是第三类和第四类的结合，也就是 LLM 驱动的工作流（提供自动化）与 AI agent（提供自主性）的结合。因此，它是自动化与自主性的结合，这些被称为 agentic systems（智能体系统）。

<details><summary>Original English</summary>
Now,
typically
the
applications
that
we

interact
with,
they
are
either
a

combination
of
these
four,
right?
LLM

chatbots
which
are
very
easy.
Lots
of

people
just
create
an
AI
application,

create
a
chatbot
so
that
you
can
talk

with
it.
You
also
have
rag
applications

which
is
essentially
like
a
glorified
uh

vector
search.
And
then
you
also
have

LLM
driven
workflows
and
AI
agents.
And

typically
what
most
of
us
use
uh
by
the

way
raise
of
hands
who
doesn't
use
AI

agents
like
cloud
code
etc

of
course
uh
so
cloud
codec
etc
all

these
systems
are
a
combination
of
three

and
four
which
is
um
you
know
a

combination
of
LLM
driven
workflows
that

provide
automation
and
AI
agents
that

provide
autonomy.
So
it's
a
combination

of
automation
and
autonomy

and
these
are
called
agentic
systems.
</details>

更好的系统，比如 Claude Code、Codex、Cursor、Open Claw、Hermes Agent 等等，它们都是这两种类型的结合。而与我交流过的大多数工程师——这一点很重要——我们每天都在使用这些系统，对吧？但是在构建自己的 AI 应用时，我们却不再这么做，或者说很多人在构建 AI 应用时并没有去思考这些问题。因此，你可能拥有一个 AI 应用，但你却没有像这样去使用它。这是我们今天将要重点探讨的内容，因为我认为这才是使用 AI 应用更好的方式：不仅通过聊天机器人，不仅通过 RAG 应用，而是通过自动化与自主性的结合。

<details><summary>Original English</summary>
The
better
systems
like
cloud
code,

codeex,
spy,
uh
open
claw,
hermes
agent

etc.
they
are
all
a
combination
of
these

two
types
and
most
of
the
engineers
that

I
talk
to
and
this
is
important
is
that

we
use
these
systems
every
day,
right?

But
we
stop
or
a
lot
of
people
not
a
lot

of
people
think
about
these
problems

when
building
their
AI
applications.
So

you
might
have
an
AI
application
but

then
you
don't
consume
it
like
this.
And

this
is
something
that
we're
going
to

focus
on
today
because
I
think
this
is

the
better
way
of
consuming
um
AI

applications
not
only
through
chat
bots,

not
only
through
rag
applications
but

also
through
a
combination
of
automation

and
autonomy.
</details>

那么对于那些呃还不了解的人来说，什么是 AI agent 呢？

它是一个类似于计算实体的存在，能够……

<details><summary>Original English</summary>
So
what
is
an
AI
agent
for
those
of
you

uh
who
don't
know?

It's
a
like
a
computational
entity
that
</details>

<!-- chunk 2/6 -->

是由大语言模型通过推理来驱动的，有点像我们人类拥有大脑；它通过用于记忆的数据库得到增强，这也像我们的大脑；它通过用于行动的工具得到扩展，所以相当于人类拥有四肢，我们可以与世界交互，就像 AI agent 可以通过我们提供给它的工具与操作系统交互一样；并且它还立足于输入。比如，这就像人类的感官，我们的眼睛等让我们感知信息；而且上下文，就像我们的注意力一样，也是有限的，就像我们的 agent 一样，我们无法同时看七部电影，那样我们一部电影也看不懂，无法专注于其中任何一部，所以人类的上下文窗口与 AI agent 类似，我们试图将其中一些概念同化，或者说让它们更接近我们人类的体验。这就是我们今天要探讨的内容。

<details><summary>Original English</summary>
is powered by an LLM by reasoning kind of like us humans we have our brain it's augmented by a database for memory also like our brain it's extended through tools for actions so the equivalent of a human would be like we have our extremities and we can interact with the world just like an AI agent can interact with an operating system through the tools that we give it they provide it and it's also grounded in inputs. So for for instance it would be like our senses for a human our eyes etc that let us perceive information and the context like our attention is also limited like our agents we can't watch seven movies at the same time like we will not understand any of the movies we will not focus on any of them so the context window for humans is similar to AI agents and kind of we try to assimilate or you know have some of these notions be closer to our human experience. experience and this is something that we'll we'll work on today.
</details>

### Harness 的架构与核心作用

因此，其中的推理部分是由前沿实验室提供的，对此我们并没有太多的控制权；然后我们还有自己拥有多一点控制权的部分，即记忆、工具使用和感知，对吧，而这就是 harness 本身。harness 本质上就是你为了构建这三个组件——也就是工具使用、记忆和感知——所需要做的所有脚手架。

<details><summary>Original English</summary>
So the reasoning part of it uh is provided by the frontier labs and we don't get a lot of control over that and then we also have the things that we do have a little bit more control over which are the memory the tool uses and the perception right and this is the the harness itself. A harness is essentially all the scaffolding that you need to do to build uh these three components which is the the tool use the memory and the perception
</details>

我们不会过多关注模型，因为就像我说的，我们在其上能做的事情并不多，对吧？所以 harness 实际上是 AI 中最有趣的话题之一，我认为是当今 AI 中最有趣的话题，因为这些 harness 实际上控制着 AI agent 能做的一切。你给它一个不同的配置，那么 agent，也就是你所调用的同一个前沿大语言模型，就会变得更好或更差。有时事实证明，仅仅通过改变 harness，同一个模型在特定任务上的表现就会变得更好或更差。所以把重点放在 harness 上真的非常非常重要，而目前关注这一点的人并不多。正如你所说，在一个 harness 中有七个不同的组件，如果算上持续学习的话就有八个不同的组件，但你需要做出很多决策，对吧？你有模型，你有存储，比如把数据放在哪里；你有一些编码和检索组件，比如我如何计算两个向量之间的距离以正确检索数据；我在记忆中存储什么？我是把它看作人类所拥有的短期记忆加长期记忆吗？我是把它划分为不同的隔间还是不同类型的记忆？

<details><summary>Original English</summary>
and we're not going to focus too much on the model because like I said we don't have a lot of possibilities on what to do right so the harness is actually one of the most interesting topics in AI I think is the most interesting topic in AI nowadays because these harnesses actually control everything that the AI agent can do. You give it a different configuration then the agent the same LLM frontier AI model that you're consuming becomes better or worse. Sometimes you know it's been proven that by just changing the harness the same model performs better or worse for specific tasks. So it's really really important to make focus on the harnesses and not a lot of people are doing this and like you said in a harness there are you know seven different or eight different components if you consider continue learning as well but there are lots of decisions that you need to make right you have the model you have the storage like where do you put the data uh you have some encoding and retrieval components like how do I make the distance between two vectors to actually retrieve the data properly uh what do I store in my memory? Do I think of it as short-term memory plus long-term memory kind of like humans have? Do I think of it in different uh compartments or different types of memory?
</details>

还有语义层，这是一个非常有趣的组成部分，因为作为人类，我们坐在这里，拥有一些我们从未向对方明说过的上下文，对吧，但我们在共享这些上下文。例如，我是演讲者，你们在听，你们现在没有在唱歌，为什么你们没有唱歌？因为在此时此刻我们所处的语境语义中，这并不合适，对吧？所以模型本身也可以访问语义层，它涉及所有没有向模型说明但被假定默认成立的事情。此外还有 agent 循环，它就像所有驱动并自动、自主地让 agent 一次又一次运行的机制，这是最重要的部分之一；还有上下文工程，我们都会关注它们，但我不会去深……深入探究，因为我们实际上会在工作坊中进行。

<details><summary>Original English</summary>
uh also the semantic layer which is a part that's really um interesting because as humans we are here and we have some context that we have never said to each other right but we are sharing this for instance I'm a speaker and you are listening you are not singing right now why are you not singing because it's not appropriate in the semantics of the context that we are at right now right so the model itself also has access to the semantic layer which talks a little bit about all the things that haven't been set to the model but they are assumed. Also the agent loop which is like all the things that drive and automatically and autonomously make the agent work all over uh again and this uh is like one of the most important parts and also context engineering and we'll focus on each of them but I will not go d uh I will not deep dive into them because we'll actually do that in the workshop.
</details>

### 存储权衡：文件与数据库

仅供参考，此前围绕文件与数据库有过大讨论，很多人说我们所有事情都要用文件，比如你把所有东西都塞进一个文件里，然后神奇地一个月后 agent 就变强了。另一些人则是数据库极大主义者，他们希望把所有东西都放进数据库里。对吧？

<details><summary>Original English</summary>
So just for reference um there was this big discussion around files versus databases like lot of people were saying we need to use files for everything like you just put everything into a file and then like magically one month later the agent becomes better. Some other people are database maximalists and they want to put everything into a database. Right?
</details>

所以这种两难目前仍在继续，我想说的是……让我给你们举个例子，在屏幕上看到的这个例子中，有人能告诉我，针对屏幕上所看到的这个具体问题——多个 agent 同时写入同一个文件，agent 目前使用的是什么变通方案来解决的？当今在 AI agent 中这是如何运作的？有什么想法吗？

<details><summary>Original English</summary>
So this dilemma is still going on and I would say that um well let let me give you an example like can can anyone tell me in this example that you see on the screen can anyone tell me what is the workaround that agents use to solve uh this specific problem that you're seeing on screen multiple agents writing to the same file. How does that work nowadays in AI agents? Any ideas?
</details>

>> 工作树（Work trees）。

<details><summary>Original English</summary>
>> Work trees.
</details>

完全正确。很好。所以工作树是目前的解决方案，对吧？而这是一个变通方案，因为文件本身存在固有问题，那就是如果有多次写入进入同一个文件，你就会遇到一致性问题，比如哪一次写入先发生？如果有人正在读取，那么对于在这个人修改文件之前读取了该文件的情况，我该怎么处理等等，会有很多问题，对吧？所以在某些方面，我肯定会告诉你文件非常棒，文件非常擅长存储大量的非结构化数据。另一方面，数据库也用于某些其他类型的用例。但我的解决方案是，对于某些情况，其中一些方案适用于文件，而对于其他一些情况，它们适用于数据库。所以我们实际上需要重新考虑正在发生的这些事情，对吧？工作树这个方案或变通方法，在 30 年前就已经被数据库解决了。而我们正试图在其中一些事情上重新发明轮子。我们实际上不需要重新发明任何东西，因为对此已经有了现成的解决方案。例如，如果你试图让多个 agent 同时写入同一个文件，如果你具备事务一致性或 ACID 一致性，比如对文件的原子性（Atomic）、一致性（Consistent）、隔离性（Isolated）和持久性（Durable）写入，你就不会遇到这个问题。对吧？

<details><summary>Original English</summary>
Exactly. Good. So, work trees is the current solution, right? And this is a a thing or a workaround because files have an inherent problem in themselves, which is that they they like if multiple writes are coming into the same file, then you have problems with consistency like which right came first? If someone is reading, what do I do with this person that read the file before I modified it, etc. lots of problems, right? So for some things I will definitely tell you like files are great. Files are great at storing lots of unstructured data. Database on the other hand is also used for some other types of use cases. But my solution is that for some cases some of these uh solutions work with files, for some other cases they work with databases. So we actually um need to reconsider some of these things that are going on, right? Um, and the work tree uh solution or the workaround has been already solved by databases 30 years ago. And we're trying to reinvent the wheel with some of this. And we don't actually need to reinvent anything because there is an actual solution to this. For example, if you're trying to write to a file um at the same time multiple agents, if you had transactional consistency or acid consistency like atomic consistent isolated and durable um rights into the file, you would not get this issue. Right?
</details>

所以文件对某些事情有好处，而数据库对其他事情有好处。我们不必只局限于其中一种，对吧？所以在 agent harness 中，不妨将此作为一个思考。

<details><summary>Original English</summary>
So files are good for some things and databases are good for for other things. We don't have to go into only one of them, right? So in the agent harness just consider this as an as a thought.
</details>

### Agent 记忆机制的划分

另一个组件是所有的记忆组件，对吧，这包括围绕 AI agent 创建的所有机制和系统，使其能够使用信息，并且不仅能使用这些信息，还能够在适当时机提炼和恰当地回忆这些信息，对吧？作为工程师，你可以选择在 agent 记忆层中要考量哪些内容。有些人喜欢短期记忆与长期记忆的划分。在这里，这是第二部分。我们有一些短期记忆组件。例如，如果我们与 Claude 或 Codex 对话，我们在上下文窗口本身就是短期记忆这种意义上拥有短期记忆。任何在会话结束后消失的内容，就像它在会话之后就消失了，对吧？上下文窗口中的大多数内容就这么消失了。然后你启动另一个会话，它又从零开始。这就是短期记忆。它是非常有限的，我们无法把所有东西都放进去。

<details><summary>Original English</summary>
Uh another component is the all the memory components right and this comprises all the mechanics and the the systems that are created around an AI agent to make it use the information um and not only use this information but also be able to refine it and recall it appropriately when it's time right and agent memory you as the engineers you get to choose like what are the things in your agent memory layer that you're going to consider. Some people like the short-term versus long-term memory. And in this case, this is part two. We have some short-term memory components. For example, if we are talking with clot or with codeex, we have short-term memory in the sense that the context window itself is short-term memory. Anything that disappears after the conver like it disappears after the conversation, right? most things uh in the context window just vanish. Then you launch another conversation and it starts from zero. That's short-term memory. It's very limited. We cannot put everything into it.
</details>

然后我们还有长期记忆。在长期记忆内部，我们还提出了几个类别。例如，情景记忆（episodic memory）涵盖发生过的所有事情、我们对话的所有片段、所有的工具日志、之前的对话、你与 agent 之间以往对话的摘要等等，它们都归入这个情景长期记忆类别。你还有规程或程序性记忆（procedural memory），其中包括诸如技能、工作流等所有内容，工作流就像是一系列正在运行的技能等等。所有这些都归入程序性记忆。此外我们还有语义记忆（semantic memory），也就是所有未明说的内容，就像我说的，agent 记得你是谁、你的偏好是什么、你最喜欢的框架是什么等等，所有这些都归入语义记忆。

<details><summary>Original English</summary>
And then we also have long-term memory. And inside the long-term memory, we also have some categories that we propose. Uh, for example, episodic memory would be all the things that happened, all the episodes of our conversations, all the tool logs, the previous conversations, um, summaries of previous conversations that you've had with the agent, etc. They all go into this episodic long-term memory category. You also have procedures or procedural memory, which are all the things like skills, workflows, which are like a sequence of skills that are being run etc. All of those go into procedural memory. And also we have semantic memory which is all the unset like I said the agent remembers who you are what are your preferences what's your you know favorite framework etc all these things go into semantic memory
</details>

所以这里的核心问题是，为什么我们不能把所有东西都塞进短期记忆？因为它是有限的，而且不仅有限，实际上注意力矩阵越大——注意力矩阵本质上就是上下文窗口——它越大，表现就越差。这种情况发生在每一个模型上。有许多研究表明，如果你的上下文窗口从零 token 开始，问题的解决要比你已经有 256,000 个 token 时准确得多，而目前的上限是一百万。由于 KV 缓存的存在，我们现在达到了一百万。

<details><summary>Original English</summary>
so the problem the main issue here why cannot we put everything into the short-term memory because it's limited and it's not only limited but actually the bigger the attention matrix is and the attention matrix is essentially the the context window. The bigger it is, the worse it performs. And this happens for every model. There are lots of studies that have shown that if you start at zero tokens on the context window, the problem is being solved much more accurately than if you have 256,000 tokens already and the limit is a million right now. We're at a million because of the KV cache. All
</details>

<!-- chunk 3/6 -->

这些事情都需要考虑，而且要明白，即使宣传的上限能达到 256k 甚至 100 万，如果你一直往里塞，性能也会急剧下降。因此，上下文窗口越小，它解决问题的效果就越好。这适用于你能想到的所有人类面临的问题类型，对吧？有两种方法可以应对这个问题：一种是上下文摘要（context summarization），你只需让它生成一份简短摘要，涵盖上下文窗口中说过的一切，得到摘要后，下一次对话就从这份摘要开始，这挺好的；另一种是压缩（compaction），原理类似，但在压缩中，你相当于把对话的片段存入数据库或文件中并附上 ID，如果 AI 智能体后续需要它，就凭这个 ID 从特定偏移量读取，类似于从文件中读取，对吧？这些就是上下文工程中会出现的一些问题。

<details><summary>Original English</summary>
these things need to be considered and just know that even if the advertised limit stops at uh 256k or 1 million if you keep going the like the performance goes horribly. So the smaller the context window is the better it will solve a problem. And this applies for every type of problem that you can think of uh in humanity right and there are two types of things that tackle this. One is context summarization which you just ask it hey just generate a summary a short summary for me with this uh with all the things that have been said in the context window and then you get the summary and then you start off from the summary the next conversation that is fine. Uh, another one is compaction and that's kind of similar, but in compaction you're just like putting chunks of the conversation into the database or into a file and then you just put it with an ID and if the AI agent needs it later, it has the ID. It just pulls from the ID with an offset kind of like reading from a file, right? Some of the these are some of the problems that happen in context uh context engineering.
</details>

接着是智能体循环（agent loop），它就像是驱动我们刚才讨论过的所有组件的驱动器或车辆。我们有一个上下文装配（context assembly）部分，它动态地从技能、工具、历史对话、文件和数据库中拉取内容，将所有这些东西带入上下文窗口。然后进行推理，向 OpenAI 或任何正在交互的模型发起 API 调用，并决定接下来需要做什么。这一切都是自动发生的，如果你愿意，也可以无限循环下去。就我而言，在为这次工作坊准备的智能体循环中设置了最大耐心（maximum patience），因为我不想把 OpenAI 的额度或我的任何额度耗尽。在我们这个例子中，最大迭代次数是 8 次，每次迭代最多允许 60 秒的推理时间，对吧？不过这完全是可配置的。正如我所说，作为工程师，我们对智能体循环中发生的事情拥有决定权，对吧？

<details><summary>Original English</summary>
And then we have the agent loop which is the driver or the the car that that drives all the components that we have talked about. We have a context assembly part that pulls from the skills pulls from the tools pulls from the previous conversation from the files from the database. All of these things just brings in uh brings into the context window dynamically. Then it does some reasoning. it makes an API call to open AAI or whichever model you're talking to and decides on what needs to be done and this happens you know automatically and infinitely if you want in my case in this agent loop that that uh we prepared for the workshop it has a maximum patience because I don't want to run out of openi credits or any any credits that I that I have but uh yeah the the maximum number of iterations in our case will be eight and a maximum of 60 seconds of reasoning for each one of the iterations, right? Um, but this is completely configurable. Like I said, as engineers, we have to say in what goes on into the agent loop, right?
</details>

### 工具箱与技能箱模式

还有工具箱模式和技能箱模式，这是我们提出的用于存放数以百计的工具和技能的方案。不知道大家如何，我自己就已经安装了大约 100 种技能。我不可能把这 100 种技能同时塞进上下文窗口，因为每种技能大概需要 3000 到 5000 个 token，这样一下子就会超出宣传的上限，我就完全没有空间进行与智能体的实际对话了。那么该如何解决呢？方法有很多，但我们建议的做法是将工具和技能进行向量化，为它们生成向量嵌入（vector embeddings）。通过这些向量嵌入，一旦智能体循环——让我往回翻一下——一旦智能体循环想要检索某些有用的技能或工具，就可以对现有的向量数据库进行向量相似度搜索，提取最相关的技能或工具来解决问题。问题解决之后，再将其卸载。这是保持上下文窗口在该层面上具有相关性的方法之一。使用技能和工具是一种非常常见的模式，比如每个人都在使用工具，像 Bash 命令或切换目录（cd），这些都是通过 Bash 提供的具体工具，对吧？所以我们一直在使用工具和技能，在某些情况下，它们会占用 50% 以上的上下文窗口空间，对吧？所以我只是希望大家能意识到，技能和工具实际上占用了大量的上下文窗口空间。

<details><summary>Original English</summary>
And also the toolbox pattern, the skillbox pattern, what we propose for this for storing tools and skills, which are hundreds. I don't know about you, but I have like a hundred skills already installed. I'm not putting a 100 skills at the same time into the context window because each skill is like 3,000 5,000 uh tokens. So that would automatically like go over the advertise limit in no time. I I would have no space for my actual conversation with the agent. So how do you fix that? Well, there are different ways, but what we propose is that you vectorize, you create vector embeddings out of the tools and out of the skills. And through those vector embeddings, once the agent loop, let me go back. Once the agent loop wants to retrieve some useful skills or tools, you're going to do vector similarity search against this vector store that you have. You're going to pull the most relevant skill or tool to solve it. You solve the problem and then you offload it again. And that's one of the ways in which you uh keep the context window relevant in this in this sense. And you know using skills and using tools is a very very uh common pattern like everyone's using tools like a bash command or a change directory all these are specific tools through bash right so we're using tools and skills constantly this is for some cases more than 50% of the context window that's being used right so I just want you to be mindful of the vast amount of context window size that is actually being kept by the skills and by the tools.
</details>

我们还有一个被称为技能蒸馏（skill distillation）的概念，也就是拿之前的对话、运行记录，以及你与 AI 智能体进行过的实际对话，试图从中提炼出有意义的内容。具体怎么做呢？方法有好几种，但最简单的方法之一就是直接创建一个 `skill.md`，并把它放入之前存放所有内容的同一个技能箱中。这也是类似 Hermes 智能体（该领域的创新者之一）的做法：创建特别擅长解决特定问题的技能。假设你正在做前端开发，那么你可能会想根据自己的偏好创建一个非常奏效的技能，比如“嘿，我喜欢这种配色风格”等等。下次你再进行前端开发时，由于已经为它生成了向量嵌入，智能体就会自动选择更相关的技能。因此，如果你只是提到“嘿，我喜欢在另一个技能中用过的这种配色风格”，它就会自动明白你指的是新技能，因为你使用了比如“配色风格”这个词，对吧？所以技能蒸馏是可用于提升模型长期学习能力的技术之一。

<details><summary>Original English</summary>
Um we also have this idea called uh skill distillation where you take previous conversations, runs and you know actual like conversations that you've had with an AI agent and then you try to create something meaningful out of that. How do you do that? Well, you can do it in several ways, but one of the easiest ways that you can do it is just like create a skill MD and put it into the same skill box that you had everything before. And this is one of the ways like a Hermes agent, one of the innovators in this sense was creating skills that are particularly good to solve specific specific problems. Let's say that you're working on a front end. Well, if you're working on front end, you might want to create a skill that has worked very well for you with all your preferences. Hey, I like this coloring style, etc. And the next time you work on the front end, since you have created vector embeddings out of this, you can just like the agent will automatically choose the more relevant skill. So if you just mention, hey, I like this coloring style that I had in this other skill, it's automatically going to know that you're referring to the new skill because you use the word uh coloring style for for instance, right? So skill like skill distillation is one of the techniques that that you can use to improve the the learning the learning of a model over time.
</details>

这也跟我刚才说的一脉相承，即你拥有动态技能发现（dynamic skill discovery）机制，意思是智能体循环在装配或构建上下文时，会在需要的时候调取合适的技能和工具。

<details><summary>Original English</summary>
And it's the same uh this is uh related to what I what I was saying is that you have dynamic skill discovery in the sense that the agent loop when assembling or building the context will pull the right skills and the right tools when it needs
</details>

### 持续学习与记忆分类

有人可能会问：一个被冻结（frozen）的模型是如何变强的？我所说的“冻结”是指我们无法对前沿模型进行直接控制，对吧？但我们确实可以控制它的所有数据——即数据层，对吧？有人会说：“我们来修改模型的权重吧”；另一些人会说：“我们来构建一个针对这个特定问题表现更好的嵌入模型，然后再去操心检索更好的嵌入”等等。方法有很多，但核心思想是，这是持续学习（continual learning）的核心组成部分，而持续学习是提升模型能力的手段之一。这里可以分为三类，对吧？你可以针对参数化记忆（parametric memory）展开工作，之所以叫参数化，是因为它修改了神经网络权重的参数；还有表征记忆（representational memory），也就是处理嵌入（embeddings）等内容的机制；另外就是非参数化记忆（nonparametric memory），也就是我们今天到目前为止所讨论的所有内容。如果你对这三者中的任何一种感兴趣，我们今天主要聚焦在第三种上。另外两种同样存在，我就不再深入展开了。这其中包含许多技术，比如构建低秩自适应（LoRA）、微调模型、生成嵌入等等。所有这些内容都可以在我之前提到的那门课程中找到，那门课重点讲解了这三个类别。所以如果有兴趣，可以去看看那门课程，或者在会后跟我们交流。活动结束后，我们全程都会留在现场，对吧？

<details><summary>Original English</summary>
and you know some people ask uh like how does a frozen model get better and what I mean by frozen is that we we don't get any control over the frontier models right uh but we do get control over all the data the data layer of it right and some people say hey let's modify the weights of the model some other people say let's create an embedding model that works better for this specific problem and then I'll worry about you know just retrieving the better embeddings there uh etc so there are different ways to do that but the idea is that this is the main component of continual learning and continual learning is one part of of of the things that you can do to make a mo model better. And there are three categories, right? You either work on the parametric memory. It's called parametric because it modifies the parameters of the weights of the neural network. You also have representational memory which is what it works with embeddings etc. And you also have nonparametric memory which is everything that we have spoken about today until this point. But um if you're interested in any of these three, we have focused on the third one. You also have the other two and I will not go into the uh into those two. There are lots of techniques like um you know creating low rank adaptation uh fine-tuning a model uh creating embeddings etc. And all these things you can find in that course that I I was referring to before which focuses on the three categories. So if you're interested just take out uh take that course if uh or chat chat with us after after the session. So after the session, we'll be in the event for the for the rest of the event too, right?
</details>

### 指令层级

我想提的最后一件事是，在向任何 OpenAI 模型或你使用的任何模型发起聊天补全（chat completions）API 调用时，底层都存在一种固有的指令层级（instruction hierarchy）。什么是指令层级？就是输入给模型的内容具有不同的权重。例如，我们用来交互的是用户（user），对吧？也就是请求。从这个意义上说，这是我们传递给模型的第三重要的内容；最重要的一层是系统提示词（system prompt），对吧？大家都知道系统提示词这个概念。

<details><summary>Original English</summary>
And last thing I want to mention is that all of the things that happen during a chat completions API call to any uh OpenAI model or anything that you're using is that there is an inherent uh instruction hierarchy. What do I mean by instruction hierarchy? There is a different weight on the things that are given to the model. For instance, what we use to interact with is the user, right? The request. In this sense, this is the third most important thing that we can pass to a model. The most important one is the system prompt, right? Everyone knows about this the system prompt concept.
</details>

系统提示词虽好，但它不可能容纳所有东西，否则内容本身就失去了层级结构。你必须将一部分内容放入系统提示词，一部分放入用户提示词，而所有提供的工具和技能也同样遵循这种层级。这样设计很好，因为它实际上能让我们或者让模型更聚焦于某些特定内容，我们也会在工作坊中详细演示这一点。这里给大家展示一下工作坊的界面作为参考。如果你已经在 Codespaces 中运行了它，就会看到这个部署好的界面。我稍后会带大家一步步操作，但这基本上就是其运作方式……

<details><summary>Original English</summary>
Um, and the system prompt is fine, but it cannot hold everything because otherwise things would not have a hierarchy in itself. uh you need to actually put some of the things in the system prompt, some of the things in the user prompt and all the tools and the skills that the things that are made available, they have this hierarchy. And this is good because it it's it actually um lets us or lets the model focus more on some things than others and we'll also go through that in the workshop. So just for reference uh this is the the UI of the workshop. So if you're running it in code spaces already, you'll see that you have uh this deployed. I will go through through it uh with you. But this is essentially the way
</details>

<!-- chunk 4/6 -->

### 反洗钱智能体演练与应用架构

在其中，我设想一个在反洗钱（AML）领域工作的人——比如银行里的欺诈检测系统——与一个自主智能体进行交互。这个自主智能体全天候 24/7 在后台运行。它不睡觉，也不需要我们所拥有的任何人类生理需求，对吧？它通过一个测试框架（harness）连接到数据库，拥有我们提到的所有功能，但除此之外，即便在我们离线时，它也在自主为公司做出决策。它不会通过直接说“嘿，这家伙很可疑，我们把整个银行及所有东西都封锁了吧”来毁掉人们的生活，因为那样会毁了一个人的一生；相反，它是做出这些决定并将其打印/记录下来，以便人类稍后能够实际去审查，但这将在排查过程中节省大量时间等等。

<details><summary>Original English</summary>
 in which I envision someone that works in AML like um a fraud detection system in a in a bank interacts with an an autonomous agent. The autonomous agent is running in the background 24/7. It doesn't sleep. It doesn't need any of the humanly uh necessities that we have, right? It's connected through a harness to the to a database and it has all the functionalities that we have mentioned but on top of that uh it's autonomously making decisions for the company even when you know we're offline. It's not ruining people's lives by just like saying, "Hey, this this guy is suspicious. Let's just like block the whole bank and everything, you know, because I would ruin ruin the person's life, but rather it's making these decisions and just like printing them so that a human can actually inspect them later on, but it's going to save a lot of time during the, you know, the discovery process, etc.
</details>

所以到了研讨会结束时，如果你完成了它，你将能够拥有一个连接到数据库的智能体，该数据库的运作就如同任何一家真实公司一样，它将执行自主分析和决策，然后由人类来获取并与之交互。这些就是我们讨论过的有关 harness 的所有组件。闲话少说，我会再次放上二维码，或者网址是 workshopwaitingroom.com。如果你想查看我们举办的任何其他研讨会，只需查看这个 GitHub 仓库即可。我们在放入那里的所有内容上都投入了大量进展与心血，从研讨会、实战环节到笔记本应有尽有，因此你可以从智能体 harnesses 等不同主题开始上手。所以不妨去看看。让我切换到我的 Firefox，向大家展示这个应用程序是如何工作的。

<details><summary>Original English</summary>
So by the end of the uh of the workshop, if you complete it, uh you're going to be able to have an agent that connects to a database that is actually working as if it was uh any any company and it's going to do autonomous analysis and decision making that then a human is going to take and interact with. So these are all the the components that we have talked about about the harness and without further ado I will uh put the QR code just again or workshopwaiting room.com um and if you want to check out any of the other workshops that we have uh you can just check out this GitHub repo we're making a lot of uh progress and effort into all the things that go in there everything from workshops sessions uh notebooks So you can get started on different topics like agent harnesses etc. So just check it out. Uh and let me let me go to my Firefox and show you how this application works.
</details>

首先，对于那些没有收到邀请的人，如果你访问 workshopwaitingroom.com，你将通过 GitHub API 收到一份针对你用户名的该仓库邀请。因此，如果你直接来到这里，然后在 GitHub Codespaces 上打开，它会要求你创建一个 codespace。当然，费用由我来出，所以不用担心那个。

<details><summary>Original English</summary>
So, first of all, let me just uh for those of you who didn't receive an invitation, if you go to workshop waiting room.com, you will get an invitation via the GitHub API with your uh user to this repository. So, if you just go here and then open on GitHub code spaces, it's going to ask you uh to create a code space. And of course, I'm paying for it, so don't worry about that.
</details>

只是对你们部署的硬件稍微注意一点，因为挺贵的。不过整体思路是，你将获得一个像这样的部署，里面包含几个笔记本，我会向大家展示研讨会本身。然后我的想法是过几分钟我就下台，接着我们会逐一解答有疑问的人的问题等等，然后我们一起解决。但这也会自动部署这个应用程序，它基本上在追踪所有事情，而这当然都是虚构数据。别担心，我在这里没有泄露任何人的信息，但它基本上是在不断产生新的交易。其中一些是正常的，一些是有问题的。因此，运行在 OCI 上的自主智能体（一个 grog 模型）基本上是在自主做出决策，其中有些它会说“嘿，这笔交易很可疑，我们把它加到列表里”，然后在这之后，你还可以在这里以某种方式将智能体的上下文窗口可视化，你也可以在这里查看已经存在于数据库中的所有数据，比如所有客户等等，以及智能体实时对所有这些进行实际分析的自主方式，对吧？

<details><summary>Original English</summary>
uh just be careful with um with the hardware that you deploy because it's expensive. But uh the idea is that you will get a a deployment like this with a couple of notebooks and I'll show you the workshop itself and then my idea is for me to step down in a couple minutes and then we'll go through the you know people who have questions etc and then we'll solve it together. But it's automat automatically also deploys this application which essentially is tracking all the things and this is of course uh fake data. Don't worry I'm not exposing anyone here but it's essentially coming up with new transactions. Some of them are fine some of them are uh problematic. So the autonomous agent which is a grog model running on OCI it's essentially making autonomous decisions and some of them it's saying hey this one is suspicious let's add it to the list and then afterwards uh you also get like a way to visualize the context window of the agent here um you can also check out all the data that's already in the database uh here uh like all the customers etc and also an autonomous way in which the agent is actually going to make an analysis of all this um of of all this in real time, right?
</details>

所以，它会遍历我们在工具箱中提供的、可用的工具调用。抱歉，字有点小。你们知道的，它会去梳理证据，会在我们通过向量数据库创建的知识空间中搜索知识，会进行大量的工具调用。最后，它基本上会自动梳理整份可疑活动报告（SAR）。而这里只是一种用来可视化银行中最近发生的 30 个事件的花哨方式。

<details><summary>Original English</summary>
So, it's going to run through the tool calls that we give uh that we have available in our tool um in our toolbox. Uh yeah, it's sorry, it's a little small. Um you know, so it's going to go through the evidence. It's going to search for knowledge in the knowledge spaces that we created through vector stores. It's going to make a lot of tool calls. And finally, it's going to essentially go through the whole activity uh suspicious activity reports automatically. And here is just a fancy way of visualizing the 30 most recent um events that happen in the bank.
</details>

但是研讨会本身就是这个笔记本——notebook student。我希望大家做的是，首先查看一下我们在那里拥有的不同组件，因为我们正在这里实现它们。我将讲解第一个待办事项（to-do）。在研讨会上有一些事情需要大家去做，只是为了确认大家清楚自己在做什么。因此首先，让我直接向大家演示研讨会的第一部分，对吧？这里有这个运行在 Oracle 云上的 rock 4.3 模型，当然，让我们先连接到数据库。

<details><summary>Original English</summary>
But the workshop itself is this notebook, the notebook student. And what I want you to do is first of all just check out the different components that we have there because we are implementing them uh here. And I'm going to go through the first uh the first to-do. There are a couple of things that you need to do on the workshop just to confirm that that you know uh what you're doing. So first of all, let me just go ahead and show you uh the first part of the workshop, right? Uh you have this rock model 4.3 uh which is running on on cloud Oracle cloud and let's uh connect to the database of course.
</details>

然后……抱歉，让我重启一下内核。让我运行这个单元格。重启。不过大家在进入 codespace 时如果有任何问题或遇到困难，随时告诉我们，然后我会下台和大家一起操作并回答所有问题。

<details><summary>Original English</summary>
And after sorry, let me restart the kernel. Let me run this cell. Restart. But yeah, uh let let us know if you have any questions or issues uh when getting into the code space and then I'll step down and and do this with you and answer any questions.
</details>

顺便问一下，到目前为止有什么问题吗？

<details><summary>Original English</summary>
Any questions by the way so far?
</details>

好的。

<details><summary>Original English</summary>
Okay.
</details>

请讲。

<details><summary>Original English</summary>
Yes.
</details>

仓库地址。

<details><summary>Original English</summary>
Uh the the repo.
</details>

>> 是的，你可以在 workshopwingroom.com 上找到它。让我把二维码放出来。如果你想扫码的话，就是这个二维码。这会自动通过 GitHub API 给你提供访问权限。

<details><summary>Original English</summary>
>> Yes, you can find it on workshopwingroom.com. And let me just put the QR code here. Uh this QR code if you want to uh scan it. And this will automatically give you access to to it via GitHub API.
</details>

### 问答：情节记忆与技能缓存

好的，让我为 YouTube 上的观众复述一下这个问题。他是在问情节记忆（episodic memory）以及所有这些记忆组件会发生什么情况。它会不会与之前跟某个智能体的对话发生混淆？嗯，这取决于你赋予它多少权重。这也是为什么我前面同样提到了指令层级（instruction hierarchy）。如果这是一件极其重要的事情，而你确实想从某个地方或另一个地方提取，你可能会想把它放进去。你实际上可以自己决定你的记忆层架构，对吧？因此，举例来说，在某些情节记忆非常关键、你确实想从之前的对话中提取的情况下，你可能真会想将其向量化，而不是仅仅将其保存为纯文本，对吧，这很大程度上取决于具体的用例。我想说在当前这种情况下它并不会……这里不存在冲突，因为我们在架构的记忆组件上有明确的分离。

<details><summary>Original English</summary>
Okay. So let me re uh reframe the question for the people who are on YouTube. Um so he's asking about what happens with the episodic memory and all these memory components. Does it get it confused with previous conversations with a with an agent? Well, it depends on how much uh weight you give it. And this is why I was mentioning the instruction hierarchy as well. You might want to put this if it's a really really important thing and you actually wanted to pull from some place or the other place. Uh you can actually decide your memory layer architecture yourself, right? So you might want to for instance in some cases where the episodic memory is really important and you actually want to pull from previous conversations you might actually want to vectorize that rather than just save it as raw text right depends a lot on the on the use case. I would say in this case it doesn't uh it doesn't there is no confliction there because we have a clear separation on the memory uh components of the architecture.
</details>

是的。所以技能（skills）可以被添加到系统提示词中。它们通常……噢抱歉，它们在指令层级中通常具有不同的……是的，在四个层级中，它们的权重是最低的，如果你去思考这一点的话。它通常在这里，所以它的权重最低，我认为它是一个即插即用（plug-and-play）的地方，你可以在其中拉取东西。其实 Richmond 和我正在对此进行实验，因为我们确实想创造一种方式，让你能够接入外部、内部或第三方的技能中心与工具中心，例如一组 MCP，你可以通过预先计算所有这些内容的嵌入（embeddings），来让你的智能体具备调用能力；一旦你拥有了这些预计算的嵌入，你就可以直接说“针对这个第三方技能组或工具组进行向量搜索”。

<details><summary>Original English</summary>
Yes. So the the skills can be added to to the system prompt. uh they typically um oh sorry they typically have a different uh yeah in the instruction hierarchy they have the least weight out of the four uh if you were to think about it it um it's typically here so it has the least weight I would think of it as a plugandplay place in which you can pull things and we are experimenting with this uh actually Richmond and I because we actually want to create a way in which you can plug into external internal or third party skill hubs and tool hubs for instance a collection of MCPS that you can give your agent availability by precomputing the embeddings of all of these things and once you have these precomputed embeddings you can just like say hey do vector searches against this third party uh group of skills or group of tools
</details>

但与其认为它是被包含在内的——顺便说一句，在你向 OpenAI 或任何其他模型发起的每一个 OpenAI 或每一个 Chat Completions API 请求中，这当然都是包含在内的。这是附加在底部的，而这通常占到了整体的大约 80%，就像整个请求的大约 80% 都是工具和技能。但是发生了什么，或者说为什么你没有被收取比现在高出五倍的费用呢？那是因为 OpenAI 以及所有这些系统都有语义缓存（semantic cache），如果其中 80% 的内容与上一个请求相同，它就不会重新计算，而是直接命中语义缓存，这让你、也让我们所有人能够以一种经济的方式使用前沿实验室（Frontier Labs）的模型，当然它依然非常昂贵。但我希望大家理解的是，如果我们没有这个仅仅把工具和这些技能存进去的语义缓存，成本将会高出四到五倍。因为在响应中——就像要记住，当你与前沿 AI 模型交互时，本质上整个过程都是通过一个 HTTP 请求来完成的，而类似这样的所有内容，例如作为系统提示词就可能有 10K 或 5K：“你是一个 AI 助手，然后你需要帮我解决这个、这个和……”

<details><summary>Original English</summary>
but rather than thinking of it as being included and by the way this is of course included in every open AAI or every chat completions API request that you're making to open AAI or any other model. This is attached at the bottom and this typically is like 80% of it like 80% of the whole request is uh is is tools and skills. But what what happens or like why don't you get charged like five times more than what you're charged now is because uh OpenAI and all these systems they have a semantic cache and they put uh if 80% of it was the same as the previous request it doesn't recomputee it just goes into the semantic cache and this allows you and this allows all of us to have um an a way in which to consume the Frontier Labs models in an economical way and of course it's still very expensive. But what I want you to understand is that it would be four or five times more expensive if we didn't have this semantic cache that just um puts the tools and these skills into it. Because in the response like remember that when you're interact with interacting with a frontier AI model, you're essentially making the whole thing through an HTTP request and everything like this would be for example 10K or 5K as a system prompt. you're an AI assistant and then you need to help me solve this this and
</details>

<!-- chunk 5/6 -->

这一部分。

比如你有开发者设置，也就是具体的应用指令；用户查询，也就是我们在聊天框里输入的内容，这部分微不足道，大概 100 个 token，也许一千个 token；然后是工具输出和检索到的文档，这占了请求的 80%，每次请求里单是这一项就已经有 35,000 到 100,000 个 token 了。

这回答你的问题了吗？

<details><summary>Original English</summary>
that.

 You

 have

 the

 developer

 like

 the





specific

 app

 instructions,

 the

 user





query

 which

 is

 what

 we

 type

 in

 the

 chat





which

 is

 negligible

 like

 100

 tokens





thousand

 tokens

 maybe

 and

 then

 the

 tool





outputs

 and

 the

 the

 retrieve

 docs

 which





is

 80%

 of

 the

 request

 like

 35

 to

 100,000





tokens

 is

 already

 this

 in

 every

 request.





Does

 that

 answer

 your

 question?
</details>

>> 最后一个问题。

<details><summary>Original English</summary>
>> One

 last.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Yes.
</details>

### 上下文装配与 Agent 循环控制

>> 好的。所以他的问题大致是：你该如何管理预算？既然 skillbox 和 toolbox 模式里有这么多东西，你究竟该如何把这套机制跑通，对吧？嗯，我们有明确的区分。上下文窗口，我们可以把它看作——或者设想为一个从零开始的 n 维矩阵，但它从来都不是零，它更接近 10,000 左右。我之前在读一篇论文，它在对比各个 harness 的效率，看它们在开头的第一个系统提示词和第一个 completions API 请求中塞了多少内容。Pi——你知道 Pi 这个 harness——那是最小巧、最高效的 harness，因为它在每个请求开头只包含大约 6,000 个 token。但如果你去看其他 harness，它们往往包含 30,000 到 40,000 个 token。嗯，我们该如何……我们对上下文窗口有清晰的划分。我们只让一切围绕 agent loop 运转，对吧？那么，让我翻到 agent loop 来给你们展示一点东西。Agent loop 会控制它所连接的一切，对吧？

<details><summary>Original English</summary>
>> Okay.

 So

 his

 question

 was

 like

 how

 do





you

 manage

 the

 budget

 and

 since

 there





are

 so

 many

 things

 in

 the

 skillbox

 and





the

 toolbox

 patterns

 like

 how

 do

 you





essentially

 make

 this

 work

 right

 um

 we





have

 a

 clear

 separation

 the

 context





window

 we

 think

 of

 it

 as

 or

 think

 of

 it





as

 an

 n-dimensional

 matrix

 that

 starts





at

 zero

 but

 it's

 never

 zero

 it's

 closer





to

 like

 10,000

 I

 was

 reading

 a

 paper





that

 was

 comparing

 the

 efficiency

 of





each

 harness

 on

 how

 much

 they

 put

 into





the

 first

 system

 prompt

 and

 the

 first

 uh





completions

 API

 request

 at

 the





beginning.

 Pi,

 you

 know,

 Pi,

 the





harness,

 that's

 the

 most

 minimalistic





and

 the

 most

 efficient

 uh

 harness





because

 it

 includes

 about

 6,000

 tokens





at

 the

 beginning

 on

 every

 request.

 But





if

 you

 go

 to

 other

 harnesses,

 they

 have





more

 like

 30

 40,000

 tokens.

 Um

 how

 do

 we





we

 have

 a

 clear

 separation

 the

 context





window?

 we

 just

 let

 the

 everything

 goes





around

 the

 agent

 loop,

 right?

 So,

 let

 me





go

 to

 the

 agent

 loop

 to

 show

 you

 uh

 one





thing.

 The

 agent

 loop

 will

 control





everything

 that

 it

 connects

 to,

 right?
</details>

嗯……

所以这里，例如 agent loop。

[笑喷] 哦，我翻到底部了。稍等。

呃，仅供参考，嗯……

agent loop。

<details><summary>Original English</summary>
Um





so

 here,

 for

 example,

 the

 agent

 loop.





[snorts]

 Oh,

 I'm

 at

 the

 bottom.

 Hold

 on.





Uh

 just

 as

 a

 reference

 um





the

 agent

 loop.
</details>

所以在这里，对吧，呃，上下文装配（context assembly），当你在使用它时，呃，你基本上会去构建——你们可以在 notebook 里过一遍这个。在 notebook 里讲解，但嗯，上下文装配是其中一部分：

首先，我们设定了检索工具或 skill 的最大数量。我想默……默认数量是 3。呃，所以每当有新请求进来时，它都会去判断——这是由模型本身来判定的——它会判定该做的事情是什么，然后它会尝试去装配上下文，带上它执行任务所需的东西。

对吧？而这些事情之一就是检索出三个最相关的工具、三个最相关的 skill。

我们这里没有使用重排序器（reranker）。但你也可以做的是，比如在相似度搜索的末尾，你还可以放一个 embedding 模型加上一个 reranker，它会把这三个拿过来，并告诉你在这三个当中哪一个是三者里最重要的。你实际上可以借此得到更好的精细筛选，因为你可能并不希望为每个任务都加载总共三个 skill。该任务可能只需要一个就能解决。对吧？所以思路就是，你可以采用任何你想采用的策略，只要坚持用下去，并且自始至终保持一致就行。呃，所以以本次 workshop 为例，这里的思路是我们对一个存放工具的向量库和另一个存放 skill 的向量库总共执行若干次向量检索，k 等于 3，然后在这三个里面，你可以用 reranker 检索出最相关的一个。

然后它当然会分发工具并构建上下文窗口，但这完全是 agent loop 的决策和职责。是的。

好的。那么，你与记忆层（memory layer）交互的最重要或最有趣的方式是什么……

<details><summary>Original English</summary>
So

 here

 right

 uh

 the

 context

 assembly





when

 you're

 working

 with

 it

 uh

 you

 will





essentially

 build

 and

 you

 can

 go

 through





this

 in

 the

 in

 the

 notebook.

 explain

 the





notebook

 but

 um

 the

 context

 assembly

 is





one

 part

 that





first

 of

 all

 we

 have

 a

 maximum

 number

 of





defined

 uh

 tools

 or

 skills

 to

 retrieve

 I





think

 the

 defi

 the

 default

 number

 is





three

 uh

 so

 every

 time

 a

 new

 request

 is





coming

 it's

 determining

 and

 this

 is

 done





by

 the

 model

 itself

 it's

 determining





what

 is

 the

 thing

 to

 do

 then

 it's

 going





to

 as

 try

 to

 assemble

 the

 context

 with





the

 things

 that

 it

 needs

 to

 perform





Right?

 And

 one

 of

 these

 things

 is





retrieving

 the

 three

 most

 relevant





tools,

 the

 three

 most

 relevant

 skills.





And

 we

 are

 not

 using

 a

 reranker.

 But





what

 you

 could

 also

 do

 is

 like

 at

 the

 at





the

 end

 of

 uh

 the

 similarity

 search,

 you





can

 also

 put

 an

 embedding

 model

 plus

 a





reranker

 that

 will

 take

 those

 three

 and





tell

 you

 out

 of

 these

 three,

 this

 is

 the





most

 important

 one

 out

 of

 the

 three.

 And





you

 could

 actually

 have

 a

 better





refinement

 out

 of

 that

 because

 you

 you





might

 not

 want

 to

 have

 a

 total

 of

 three





skills

 loaded

 for

 every

 task.

 The

 task





might

 be

 solvable

 by

 only

 one.

 Right?

 So





the

 idea

 is

 that

 you

 can

 put

 uh





whichever

 strategy

 you

 want

 just

 uh





stick

 with

 it

 and

 uh

 stay

 consistent





with

 it

 until

 the

 end.

 Uh

 so

 the

 idea

 in





this

 case

 in

 the

 particular

 workshop

 is





that

 we

 have

 a

 total

 number

 of

 uh

 vector





searches

 that

 we're

 doing

 against

 one





vector

 store

 which

 holds

 the

 tools





another

 vector

 store

 that

 holds

 the





skills

 k

 equals

 three

 and

 then

 out

 of





the

 three

 you

 can

 retrieve

 the

 most





relevant

 one

 with

 a

 reranker





and

 then

 it's

 going

 to

 dispatch

 the





tools

 of

 course

 and

 build

 a

 context





window

 but

 this

 is

 entirely

 the

 decision





and

 the

 job

 of

 the

 agent

 loop.

 Yep.





Okay.

 So

 what

 is

 the

 most

 uh

 important





or

 interesting

 way

 in

 which

 you

 you

 can





interact

 with

 the

 memory

 layer

 of
</details>

### 记忆层设计与向量化检索

>> 我的意思是，效率完全取决于你创建的实体数量，对吧？所以我的第一个建议就是保持简单，呃，不要创建太多的抽象概念或者过多的记忆层组件。所以比如，首先尝试只使用短期记忆和长期记忆，仅保留这两个结构，对吧？如果你认为，或者你有一个 agent 认为短期记忆或上下文窗口里的某些内容值得保留，你就把它提升到长期记忆中，并以纯文本的形式存放在某处。这是你能做的最简单的事情，对吧？

一旦你把它以文本形式保存在别处的一个长期记忆组件或对象中，接着你就可以对它进行向量化，然后让 agent loop 以某种方式去探索它。所以举个例子，在这里你只需要在观察（observing）和推理（reasoning）中间加上一个额外的小模块，让 agent 能够召回记忆之类的。你可以把它称为类似于“召回长期记忆”。这会让它在再次解决问题之前进行一番内省。呃，所以它会去你的向量库，或者无论你在哪里存放上一段对话中记录下来的长期记忆片段，从而你可以让它看一看，“好的，如果它认为这很有意思，我就允许它从中拉取内容；或者如果向量相似——比如查询的向量与我在长期记忆里的内容之间的距离足够相关且距离足够小，那么我就会把它纳入上下文窗口；如果距离太大或者不够相关，那我就直接丢弃它”。所以这就像是在观察和推理部分之间增加了一层额外的抽象。

<details><summary>Original English</summary>
>> I

 mean

 the

 efficiency

 comes

 just

 from





the

 number

 of

 entities

 that

 you

 create





right

 so

 my

 first

 recommendation

 would





be

 just

 like

 keep

 it

 simple

 uh

 so

 don't





create

 too

 many

 abstractions

 or

 too

 many





components

 of

 the

 memory

 layer

 so

 for





instance

 try

 to

 experiment

 first

 of

 all





with

 only

 short-term

 memory

 and





long-term

 memory

 and

 just

 have

 two





structures

 Right?

 If

 you

 think

 or

 if

 you





have

 an

 agent

 that

 considers

 that





something

 that

 was

 in

 the

 short-term





memory

 or

 in

 the

 context

 window

 is

 kept





is

 is

 worth

 keeping,

 you

 promote

 it

 to





the

 long-term

 memory

 and

 you

 just

 put

 it





somewhere

 as

 raw

 text.

 That's

 the





easiest

 thing

 that

 you

 can

 do,

 right?





Once

 you

 have

 it

 in

 text

 somewhere

 else





in

 a

 long-term

 memory

 component

 or





object,

 then

 you

 can

 take

 that

 vectorize





it

 and

 then

 let

 it

 be

 explored

 by

 the





agent

 loop

 in

 some

 way.

 So

 for

 instance,





here

 you

 would

 just

 have

 like

 an

 extra





thingy

 in

 the

 middle

 of

 observing

 and





reasoning

 that

 lets

 the

 agent

 recall





memories

 or

 something.

 You

 can

 call

 it





like

 recall

 recall

 long-term

 memory.

 And





this

 is

 going

 to

 make

 it

 uh

 be





introspective

 before

 solving

 the

 problem





once

 more.

 Uh,

 so

 it's

 going

 to

 go

 to





your

 vector

 store

 or

 whatever

 you

 have





this

 long-term

 memory

 uh,

 episode

 that





you

 recorded

 in

 a

 previous

 conversation





and

 from

 that

 you

 can

 let

 it

 see

 okay





I'm

 going

 to

 let

 it

 pull

 from

 it

 if

 it





considers

 it

 to

 be

 interesting

 or

 if

 the





vector

 similar

 like

 if

 the

 distance





between

 the

 vector

 of

 the

 query

 and

 what





I

 have

 in

 my

 long-term

 memory

 is





relevant

 enough

 and

 the

 distance

 is





small

 enough

 then

 I

 will

 consider

 it





into

 the

 context

 window

 if

 it's

 too

 big





or

 it's

 not

 relevant

 enough

 then

 I

 will





just

 discard

 it

 so

 it

 will

 be

 like

 a





different

 an

 additional

 abstraction





between

 the

 observing

 and

 the

 reasoning





part
</details>

### MCP 在数据库查询中的作用与局限

有各种方式……我们这里虽然没有用 MCP，但使用 MCP 的好处之一是解决……嗯，我想说的是在这种情况下 MCP 并没有那么大的相关性，嗯，但这取决于你数据库里有什么。所以例如，如果你有一个数据库，你在与一个数据库交互，就像我们现在做的一样。拥有 MCP 很有趣，但我常常跟人们提起的主要问题之一是：MCP 究竟解决了什么，尤其是在数据库领域？因为我是搞数据库的，因为我在 Oracle 工作。嗯，所以你可以解决的事情之一就是让 AI agent 执行 SQL 查询，但不用幻觉或者每次都试图硬编出一个新的 SQL 查询。这是 AI agent 在面对 SQL 时比较大的问题之一。SQL 有大约 15……比如 15 个引擎，比如 Postgres，你有 Oracle 数据库，你有 VSQL，你有许多在 SQL 上运行的不同查询，但它们有特定的 hint 或查询上的细微差别，导致它无法良好运行。对吧？所以 MCP 在这种情况下解决的主要问题会是：好的，我来预先创建一些 SQL 查询，然后让 agent 访问这些查询。这样那些查询就是被验证过可行的，嗯，而不是让 agent 每次都试图动态生成一个 SQL 查询，对吧？是的。好问题。呃，让我给你举个例子。

<details><summary>Original English</summary>
there

 are

 ways

 we

 are

 not

 doing





MCPS

 right

 here

 but

 one

 of

 the

 benefits





of

 of

 using

 MCPS

 would

 be

 to

 solve





um

 I

 would

 say

 that

 MCP

 is

 not

 really





that

 that

 relevant

 in

 this

 case

 um

 but





it

 depends

 on

 what

 you

 have

 in

 the





database

 so

 for

 example

 If

 you

 have

 a





database,

 you're

 interacting

 with

 a





database

 like

 we

 are

 doing

 right

 here.





Having

 an

 MCP

 is

 interesting,

 but

 one

 of





the

 main

 problems

 that

 I

 like

 to

 say

 to





people

 like

 what

 does

 an

 MCP

 solve,





especially

 in

 the

 database,

 because

 I'm





a

 database

 guy

 because

 I

 work

 in

 Oracle.





Um,

 so

 one

 of

 the

 things

 that

 you

 can





solve

 is

 letting

 AI

 agents

 make

 SQL





queries,

 but

 by

 not

 hallucinating

 or





trying

 to

 come

 up

 with

 a

 new

 SQL

 query





every

 time.

 This

 is

 one

 of

 the

 bigger





problems

 that

 that

 AI

 agents

 have

 with





SQL.

 SQL

 has

 like

 15

 times

 like

 15





engines

 like

 posgres,

 you

 have

 Oracle





database,

 you

 have

 VSQL,

 you

 have

 like





lots

 of

 different

 queries

 that

 work

 on





SQL,

 but

 they

 have

 specific

 hints

 or





subtleties

 in

 the

 query

 that

 makes

 it





not

 not

 work

 well.

 Right?

 So

 the

 main





problem

 that

 MCP

 solves

 in

 this

 case





would

 be

 okay,

 I'm

 going

 to

 pre-create





some

 SQL

 queries

 and

 then

 let

 the

 agents





access

 those.

 So

 those

 queries

 are





proven

 to

 work

 um

 rather

 than

 having

 an





agent

 try

 to

 come

 up

 with

 a

 SQL

 query





dynamically

 every

 time,

 right?

 Yep.

 Good





question.

 Uh

 let

 me

 give

 you

 an

 example.
</details>

### 正则表达式匹配的局限与 Skill 的向量嵌入

所以最重要的会是速度，以及句子的含义和 skill 本身代表的意义。呃，而不是把它当作文本；如果你只是把这作为文本存储在一个 SQL 文件里，它就能够——抱歉，在文件系统里的一个文件里，对吧，在操作系统中——那么你就会有呃很多可以让 agent 进行正则表达式匹配的方法。例如，所有的搜索基本上要么是关键词搜索，要么是基于词搜索深入到那个 skill 中，这没问题。嗯，但是随着它变得越来越大，对于 agent 来说就会越来越不……就会越来越困难。首先，像 GP 这样的正则表达式匹配在处理庞大文件时效率很低；有时如果文件系统呈线性增长，正则表达式匹配的性能就会呈指数级下降。好吧，不是指数级，是二次方级别，就说是二次方级别吧。但这是问题之一，嗯，它无法随着文件大小良好地扩展。呃，另一个是，如果你预先计算一个 skill 的 embedding，你实际上也捕获了这些 embedding 中的含义，那些我们人类无法理解的隐藏含义。与其仅仅用文本描述它（这对我们阅读是没问题的），呃，它还拥有一个最少 384 维到一千多维的预先计算。而这个 embedding 实际上会在 embedding 矩阵中的每一个 token 之间保留呃关联，使得它更容易被发现，例如通过语义搜索。然后这就是促使你去尝试混合搜索（hybrid search）的原因，它是语义搜索（也就是 embedding）加上关键词搜索的结合，并且这被称为 RRF，呃，这是一种混合检索类型。它的表现要好得多，因为它

<details><summary>Original English</summary>
So

 the

 most

 important

 thing

 would

 be

 the





rapidness

 and

 that

 the

 meaning

 of

 the





sentences

 and

 what

 the

 skill

 means





itself.

 Uh

 rather

 than

 having

 it

 as

 text





and

 if

 you

 were

 to

 store

 this

 just

 as





text

 in

 a

 SQL

 file

 it

 would

 be

 able





sorry

 in

 a

 in

 a

 file

 in

 the

 file

 system





right

 in

 the

 operating

 system

 then

 you





would

 have

 uh

 lots

 of

 ways

 in

 which

 an





agent

 can

 do

 regular

 expression





matching.

 So

 for

 instance,

 all

 the





search

 would

 basically

 be

 either

 keyword





search

 or

 like

 word

 search

 based

 uh

 into





that

 skill

 which

 is

 fine.

 Um

 but

 the





bigger

 that

 gets

 the

 less

 in

 like

 the





the

 harder

 it

 gets

 for

 an

 agent.

 First





of

 all,

 regular

 expression

 matching

 like





GP

 is

 inefficient

 for

 huge

 files

 and





sometimes

 if

 uh

 like

 the

 the

 file

 system





grows

 and

 grows

 linearly,





the

 performance

 of

 the

 regular





expression

 matching

 decreases





exponentially.

 Well,

 not

 exponentially,





quadratically,

 let's

 say

 just





quadratically.

 But

 this

 is

 one

 of

 the





problems

 um

 that

 it

 doesn't

 scale

 as





well

 as

 the

 size

 of

 the

 files.

 Uh,





another

 one

 would

 be

 that

 if

 you

 premp





compute

 the

 embeddings

 of

 a

 skill,





you

're

 actually

 also

 capturing

 the





meaning

 in

 these

 embeddings,

 the

 hidden





meaning

 that

 we

 as

 humans

 don't

 cannot





comprehend.

 But

 rather

 than

 just





describing

 it

 in

 text,

 which

 is

 fine

 for





us

 to

 read,

 uh,

 it

 also

 has

 a





premputation

 of

 384

 minimum

 to

 a,000





plus

 dimensions.

 And

 this

 embedding

 will





actually

 hold

 uh

 things

 between

 each

 one





of

 the

 tokens

 in

 the

 in

 the

 in

 the





embedding

 matrix

 to

 be

 much

 more





discoverable

 for

 instance

 by

 semantic





search.

 And

 then

 this

 is

 what

 leads

 you





to

 try

 hybrid

 search

 which

 is

 a





combination

 of

 semantic

 searchs

 uh

 which





is

 embeddings

 plus

 keyword

 search

 and





and

 this

 is

 called

 RRF

 uh

 which

 is

 a





type

 of

 hybrid

 retrieval.

 it

 performs





much

 better

 because

 it
</details>

<!-- chunk 6/6 -->

### 混合检索与专用框架

基本上两者都会具备。而且这基本上——我们可以在工作坊里向大家展示这个例子，因为我在这里制作了这个可视化图表，它准确解释了我所说的混合检索是什么意思，对吧？你们看，根据这个……这基本上是一个图表，它结合了关键词检索和语义检索的搜索能力，中间你们看到的这个间隙，任何绘制在这里的内容，在进行混合检索时，都会比另外两种中的任何一种更具相关性。所以总的来说，你们可以拥有两种不同类型的检索。每一种都有其优势，但如果把两者结合起来，实际上计算量会稍微多一点，不过随着时间推移，检索质量会更好。

<details><summary>Original English</summary>
will essentially just have both of them. Uh and it will essentially and this is uh we can I I can show you uh the example in the in the workshop because I I created this visual visualization here that explains exactly what I mean with hybrid search, right? Uh you see yeah so depending on the on the this essentially is a plot that uh combines the search capability of keyword search plus semantic search and this gap that you see at the middle is anything that's that's plotted here when doing hybrid search it will be more relevant than any of the other two. So uh as a summary uh the more like the more you can have two different types of of search. Each one has its advantages but if you combine them both you will uh effectively do a little bit more compute but then the quality of the retrieval will be better over time.
</details>

这些大多——我是从 AI Agent 的角度来思考的。所以我并不指望这个房间里的任何人像这样开始构建自己的定制框架（harnesses），因为市场上已经有了非常棒的解决方案，对吧？我们有 Claude Code，有 Codex，每个人都有自己的偏好。顺便问一下，举手示意一下谁喜欢 Pi？好吧，比我想象的要少，不过挺好的。

<details><summary>Original English</summary>
Um these are like most of these I'm thinking of it from the AI agent perspective. So I'm not expecting anyone uh from this uh room to just like start building their own custom harnesses because we already have great uh solutions in the in the market right we have cloud code we have codeex each one has their own um preference by the way a show of hands for who likes pi okay less than I expected by but uh good
</details>

所以，我想说的是，我是从 AI Agent 的角度来考虑的。我希望你们理解的是，你们可以针对特定问题构建定制框架。构建定制框架不必像创建一个新的 Claude Code 那样复杂，然后把你所有的工作都跑在那个定制框架里。相反，让我们简化你试图解决的问题，然后构建附加在上面的定制框架。所以在这种情况下，我想的是，如果你是一名顾问，那你就是我这场工作坊最完美的用户案例，或者最完美的用户，因为你可以创建一个针对金融 Agent 运行良好的定制框架，并且具备满足金融用例所需的一切。

<details><summary>Original English</summary>
so um I would say that I'm thinking of it as from the AI agent perspective. This what I want you to understand is that you can build custom harnesses for specific problems. And building custom harnesses doesn't to be doesn't have to be as sophisticated as creating the new clo the new clo code and then you're running all of your work in that custom harness. Rather, let's simplify the problems that you're trying to solve and then build custom harnesses that attach on to onto that. So in this case I'm thinking of um you know if you're a consultant you are my perfect uh use case or my perfect user for this workshop because you could be creating a custom harness that is working fine for a financial agent and has all the things that it needs to a financial uh use case.
</details>

但如果是另一种类型的客户，或者面对不同类型的数据，或者有不同类型的约束——比如如果你想解决下一个 Navier-Stokes 问题之类的，那些就会有不同的约束。例如 OpenAI 的那些问题、数学问题，它们需要自动压缩或自动上下文摘要，因为这些 Agent 中间没有任何人在回路中（human in the loop）。所以围绕解决这些问题的一切，都必须默认具备自动上下文摘要。它还必须具有无限的耐心，或接近无限的耐心。而在我们这个案例中，这个 Agent 循环被简化为最多只有八步。所有这些考量都取决于具体的问题。

<details><summary>Original English</summary>
But then if you have another type of customer or with different types of data or with different types of constraints if you want to solve the next navir stocks problem or something uh you know those have different constraints for for instance the open AI problems the mathematical problems they need an infinite an automatic compaction or automatic context summarization because these agents don't have any human in the loop in the middle. So the like everything that goes around solving these problems have to have by default automatic uh automatic context uh summarization. It also has to have infinite patience or near infinite patience. In this case this agent loop is simplified to only eight steps maximum. All these considerations right depends on the on the problem.
</details>

是的，我会从头开始构建，因为那样你可以剔除掉 90% 你不需要的东西。所以我绝对会——是的，我的意思是，一切都是围绕 Chat Completions API 构建的，Anthropic 和 OpenAI 都创建了自己的标准来与之抗衡，但一切都围绕着那个 API 运转。所以，如果你把与模型交互的方式仅仅看作框架的一个额外插件，事情就会变得清晰得多：所有东西越小，最终的效果就越好。这回答了你的问题吗？

<details><summary>Original English</summary>
Yeah, I would start from scratch because that way you can you get to uh strip 90% of what you don't need. Um so I would definitely yeah I mean everything is built around the chat completions API and both Anthropic and OpenAI have created their own standards to fight off against this but everything goes around that API. So if you just think of uh the way to communicate with a model just as an additional plugin to the to the harness, it becomes much clearer that the smaller the everything is, the better it is at the end. Does that answer the question?
</details>

### 上机实践与结语

好的。那我们来做这个。大家开始准备代码库，用 Codespace。你们自己配置好那个 Notebook，然后我会走一圈，如果有人有任何问题，我们可以更轻松地聊聊，因为我现在觉得大家都看着我，而你们可能觉得没有压力。所以我要把压力转给你们，我走下台去，如果你们……对，我们继续吧。我的意思是，我们时间不多了。天哪，时间过得太快了。嗯，不过好的。谢谢，谢谢大家的掌声。

<details><summary>Original English</summary>
All right. So let's do uh this. You guys uh start with the code base um with a code space. just set that uh notebook uh by yourselves and then we're gonna go I'm gonna go through and do a round and if anyone has any questions we can chat in a less uh aggressive way because I feel observed and you probably feel no pressure. So I'm going to put the pressure on you by stepping off and if you Yeah, let's uh keep going. I mean we don't have a lot of time. Oh my god. Um I time flew. Um but yeah. Yeah. Thank you. Thank you for the clap.
</details>

谢谢大家。谢谢。[掌声] 我还以为只过了 15 或 20 分钟，结果已经过去了一个小时。

<details><summary>Original English</summary>
Um thank you. Thank you. [applause] Uh so I thought like 15 minutes or 20 minutes went by, but one hour went by. So uh
</details>

还有一件事，我做了设置，这样你们在酒店或家里也可以创建 Codespace。你们可以——费用由我来付。所以你们可以使用这个工作坊的内容，随心所欲地去尝试体验，费用都由我来承担。所以不用担心这个。如果你们想聊聊 Agent 框架的一些概念，随时来 Oracle 展台找我们。我们周三晚上之前都会在这里。感谢大家来参加这个环节。好的。[掌声]

<details><summary>Original English</summary>
one thing uh so I'm going to leave I set this up so that you can create the code space in the hotel at home. You can I will pay for it myself. So you can, you know, use this workshop and and play with it as as you wish and I will pay for it. So don't worry about it. Just um if you want to chat about some of the agent harness concept, just come to the Oracle booth. We're going to be here until Wednesday evening. And thank you for coming to the to the session. Yeah. Okay. [applause]
</details>