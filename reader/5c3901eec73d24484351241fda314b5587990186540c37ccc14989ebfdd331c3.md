---
author: AI Engineer
date: '2026-05-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ON5LIT0M4do
speaker: AI Engineer
tags:
  - llm-integration
  - product-engineering
  - development-workflow
  - observability
  - desktop-app-dev
title: 产品工程中的 LLM 实践：Cronulla 的经验教训与创新之路
summary: 本文探讨了在产品工程中集成大型语言模型（LLM）所面临的挑战，特别是通用 LLM 功能在实际应用中的局限性，如输出不符需求、工具调用成本与稳定性问题。演讲者分享了 Cronulla 公司如何通过构建自定义追踪工具来增强 LLM 可观测性，以及如何为桌面应用开发创新的 Web Shell，实现高效测试和迭代。核心观点是，成功的 LLM 集成依赖于细致的迭代和反馈循环，而非简单的“一枪毙命”式优化，最终目标是为用户创造无缝、直观的体验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cronulla
products_models:
  - LLM
media_books: []
status: evergreen
---
### LLM 集成挑战：来自 Cronulla 的实战教训

Maddie 作为 Cronulla 的产品工程师，分享了公司在产品工程领域应用大型语言模型（LLM）的经验。她强调，尽管 LLM 技术日新月异，但在实际产品中集成 AI 功能并非易事。Cronulla 是一款旨在提高工作效率的会议笔记应用，它能够实时转录会议内容并生成摘要。公司一直致力于开发不干扰用户使用的 AI 功能。然而，当将一个看似简单的 AI 功能，如聊天功能，引入生产环境时，会遇到诸多挑战。

通用的聊天系统往往表现不佳，例如响应缓慢（“call me in a minute”）、网络搜索功能不理想（“web search is too slow”），无法按照用户习惯撰写邮件，甚至提供与会议无关的建议（如“meetings about my football coach”）。这表明，将 LLM 塑造成符合特定用例的工具极其困难。以网络搜索为例，LLM 提供商通常将其描绘成一个简单的集成，但实际操作中会产生高昂的 token 成本，可能大幅增加单个聊天对话的费用，在规模化应用时成本难以承受。此外，LLM 提供商的更新可能随时影响模型行为（如网络搜索功能的退化），开发者对此缺乏控制，严重依赖外部服务商。

另一个关键挑战在于输出的定制化。不同角色的用户（如销售、工程、HR）对 AI 输出的需求截然不同。单一的提示词（prompt）难以满足所有人的需求，而 LLM 的行为难以预测和控制，这使得实现定制化输出变得复杂。

<details>
<summary>Original English</summary>

>> Cool.
 How's
 it
 going,
 guys?
 I'm
 Maddie.


We're
 going
 to
 talk
 about
 some
 product


engineering
 stuff
 that
 we've
 been
 doing


at
 Cronulla.
 This
 is
 not
 going
 to
 go


deep
 into
 our
 engineering
 stuff.
 So,
 if


you
 have
 for
 me
 to
 like
 go
 into
 LLMs
 and


stuff,
 it's
 not
 going
 to
 happen.
 I'm


warning
 you
 right
 now.
 So,
 you
 know


what's
 coming.
 Cool.
 So,


I'm
 a
 product
 engineer
 at
 Cronulla.
 I've


been,
 you
 know,
 coding
 since
 jQuery
 was


cool.
 I've
 seen
 React
 kind
 of
 change


front-end
 engineering.
 And
 obviously
 now


experiencing
 LLMs
 change


engineering
 and
 everything
 else
 just


like
 many
 of
 you.
 For
 those
 of
 you
 who


don't
 know,
 Cronulla
 is
 an
 app
 for


getting
 your
 work
 done.
 Essentially,


we're
 a
 meeting
 notes
 app
 where
 we


sit
 on
 your
 doc


like
 it
 is
 doing
 right
 now.
 And
 it
 has


access
 to
 your
 system
 transcription


system
 audio
 as
 well
 as
 your
 microphone


audio,
 which
 means
 we
 have
 real-time


transcription.
 And
 then
 at
 the
 end
 of


your
 meeting,
 we
 can
 give
 you
 really


awesome
 notes.
 So,
 I'm
 just
 going
 to


give
 you
 a
 quick
 demo.
 So,
 I
 was


recording
 the
 previous
 um


talk
 right
 here
 and
 you
 can
 see
 picked


up
 literally
 everything
 the
 presenter


said.
 And
 the
 cool
 thing
 about
 Cronulla


is
 that
 you
 can
 also
 write
 your
 own


notes
 on
 top
 of
 what
 the
 transcription


is
 saying.
 So,
 the
 final
 result
 is
 more


aligned
 to
 like
 what
 you'd
 normally


actually
 write
 on
 a
 notepad.
 So,
 I'll
 go


ahead
 and
 generate
 the
 notes
 here.
 And


you'll
 see
 that
 this
 will
 go
 ahead
 and


write
 a
 really
 good
 summary.


And
 as
 you
 can
 see
 like
 I
 wrote
 down


this
 20%
 overlap
 thing
 and
 it
 focused


more
 on
 the
 output,
 right?
 So,
 this
 is


Cronulla.
 We
 have
 the
 best-in-class


meeting
 notes
 no
 matter
 what
 role
 you're


in
 and
 it
 doesn't
 get
 in
 your
 way.
 And


that's
 been
 like
 our
 product
 philosophy


since
 day
 one.


So,
 we
 ship
 a
 lot
 of
 AI
 features
 in


Cronulla
 and
 our
 product
 is
 known
 to
 be


again
 not
 to
 get
 in
 your
 way.
 So,
 let's


see
 what
 happens
 when
 you
 put
 a
 simple


AI
 feature
 into
 prod.


I'm
 going
 to
 kind
 of
 give
 you
 an
 example


with
 this
 chat
 feature
 that
 we
 have.


This
 is
 a
 feature
 that
 already
 exists
 in


Cronulla.
 You
 can
 ask
 questions
 about
 a


meeting
 that
 you
 just
 had
 and
 across
 a


bunch
 of
 different
 meetings
 or
 like


shared
 context
 as
 well.
 And
 Cronulla


will
 try
 answer
 it
 to
 the
 best
 of
 your


ability.
 So,
 let's
 say
 I
 built,
 you


know,
 like
 a
 one-shot
 this
 chat
 system.


It's
 very
 easy
 to
 do.
 And
 I
 put
 it
 into


production
 in
 my
 fake
 Cronulla
 app.


And
 then
 as
 soon
 as
 users
 hear,
 you


know,
 it's
 like
 a
 call
 me
 in
 a
 minute.


So,
 give
 me
 a
 list
 of
 cities.
 Web
 search


is
 too
 slow.
 It's
 not
 writing
 follow-up


emails
 how
 I
 normally
 write
 my
 emails.
 I


asked
 it
 to
 coach
 me
 about
 my
 meetings


and
 it's
 telling
 me
 meetings
 about
 my


football
 coach.
 Obviously,
 these
 are


very


very
 common
 problems
 that
 you're
 going


to
 run
 into
 when
 you
 make
 a
 generic


chatbot.
 So,
 how
 do
 we
 get
 around
 this,


right?


So,
 what
 we've
 seen
 is
 like
 molding
 the


LLM
 to
 work
 to
 your
 specific
 use
 case


can
 be
 super
 hard.


And
 one
 of
 the
 examples
 is
 is
 web


search.
 So,
 web
 search
 for
 most
 LLM


providers
 looks
 like
 a
 line
 of
 code.
 You


simply
 add
 the
 web
 search
 tool
 and
 you


expect
 it
 to
 just
 work.
 That's
 what
 the


labs
 want
 you
 to
 believe,
 but
 once
 you


get
 into
 it,
 there's
 lots
 of
 other


complications.
 So,
 for
 example,
 the


token
 usage
 and
 token
 cost
 can
 bubble
 up


quite
 a
 lot,
 especially
 for
 complex


queries.
 It's
 going
 to
 blow
 up
 your


context.
 And
 each
 chat
 could
 be
 costing


you
 like
 10
 pence.
 Obviously,
 at
 scale


when
 you
 have
 millions
 of
 users,
 this
 is


not
 really
 feasible.


And
 then,
 you
 know,
 like
 the
 web
 search


providers
 are
 also
 like
 completely
 up
 to


the
 labs
 as
 well.
 So,
 for
 example,
 in
 in


our
 development,
 what
 we
 see
 was
 like


was
 we
 were
 using
 a
 model
 for
 a
 good


amount
 of
 time.
 And
 then
 overnight,
 they


shipped
 an
 update
 and
 for
 some
 reason


web
 search
 degraded
 and
 it
 was


completely
 out
 of
 our
 control.
 And
 we


generally
 had
 no
 idea
 like
 what
 was


going
 on
 apart
 from
 just
 like
 switching


providers.
 But
 we
 want
 to
 have
 more


control
 over
 that
 because
 it
 affects
 our


user
 user
 experience.


And
 you
 know,
 like
 there's
 literally


billion-dollar
 companies
 who
 do
 web


search.
 So,
 that
 kind
 of
 tells
 you
 that


it's
 what's
 much
 more
 than
 just
 adding
 a


web
 search
 tool
 to
 your
 LLM
 pipeline.


The
 other
 thing
 that's
 super
 important


for
 apps
 like
 Cronulla
 is
 the
 output.


So,
 the
 summary
 that
 you
 saw
 was
 pretty


good
 for
 what
 I
 would
 expect,
 but


someone
 in
 sales
 might
 expect
 more
 of
 a


deal
 focus.
 Someone
 in
 engineering
 might


expect
 like
 action
 items,
 blockers,
 or


like
 linear
 tickets.
 HR
 might
 want


something
 completely
 different.
 And
 the


thing
 is
 that
 one
 prompt
 can't
 generally


serve
 everyone.
 And
 you
 know,
 LLMs
 are


stubborn
 and
 we
 need
 to
 figure
 out
 how


to
 get
 inside
 them
 and
 make
 them
 work


how
 we
 want
 it
 to
 work.


And
 yeah,
 as
 you
 as
 you
 know,
 like
 LLM


behavior
 is
 largely
 seen
 as
 like
 a
 black


box,
 but
 we
 want
 to
 kind
 of
 go
 very
 deep


into
 the
 details
 and
 figure
 out
 exactly


what's
 going
 on.
 So,
 what
 we
 did


recently
 at
 Cronulla
 is
 we
 started


building
 our
 own
 tracing
 tools.
 And


obviously,
 thanks
 to
 LLMs,
 you
 can


actually
 one-shot
 these
 things.
 And
 this


is
 where
 one-shotting
 is
 kind
 of
 nice.


And
 so,
 we
 built
 our
 tooling
 tracing


tools
 here
 where
 we
 basically
 have


complete
 visibility
 on
 the
 tool
 calls


straight
 from
 the
 beginning
 to
 the
 end.


So,
 we
 have
 full
 visibility
 over
 the


individual
 tool
 calls,
 why
 it's
 making


those
 tool
 calls,
 the
 search
 tools,
 the


reasoning
 tools,
 the
 cost
 structured


exactly
 how
 we
 want
 it.
 And
 the
 most


useful
 part
 of
 this
 is
 that
 we


structured
 the
 data
 exactly
 how
 we
 want


it.
 And
 the
 UI
 is
 built
 to
 like
 serve


our
 our
 employees
 internally,
 not
 just


like
 engineers,
 but
 also
 product,


data,
 and
 like
 CX,
 and
 everyone.
 So,
 you


don't
 have
 to
 like,
 you
 know,
 go
 into


CloudWatch
 and
 do
 like
 very
 complex


queries
 to
 figure
 out
 why
 something


failed.
 And
 that's
 been
 like
 the
 key
 for


us
 in
 like
 figuring
 out
 this
 black
 box.


And
 previously,
 obviously,
 building
 this


kind
 of
 tools
 would
 be
 like
 up
 to
 using


a
 SaaS
 provider.


And
 it
 simply
 wouldn't
 you
 simply


wouldn't
 have
 the
 time.
 But
 now
 you


actually
 can
 spend
 time
 building
 this


tracing
 tool
 that
 actually
 serves
 what


you
 need.


And
 this
 is
 obviously
 a
 very
 basic


example,
 but
 obviously
 you
 can
 use


OpenTelemetry
 or
 like
 other
 providers.


But
 we
 essentially
 just
 like
 save
 things


to
 a
 DB,
 wrap
 around
 like
 AI
 SDK,
 and


then
 the
 front-end
 is
 like
 kind
 of
 like


the
 most
 important
 part
 cuz
 that's
 what


people
 are
 going
 to
 use
 to
 figure
 out


what
 breaks
 and
 what
 doesn't.
 And
 we


literally
 have
 like
 our
 founder


literally
 goes
 into
 like
 the
 details


like
 following
 the
 agent
 loop
 completely


front
 to
 back
 to
 figure
 out
 exactly
 what


went
 wrong.
 So,
 then
 at
 the
 end
 of
 this,


you
 can
 actually
 figure
 out
 like,
 you


know,
 this
 output
 feels
 off
 to
 like


exactly
 what
 failed.
 And
 then
 when
 you


iterate,
 you
 can
 improve
 on
 those


things.


But
 as
 I
 said
 earlier,
 this
 is
 going
 to


be
 more
 more
 than
 just
 like
 basic
 LLM


stuff.


And
 LLM
 behavior
 is
 obviously
 part
 of


the
 picture.
 The
 how
 users
 interact
 and


experiences
 your
 product
 is
 also
 very


important.


So,
 with
 LLMs,
 you
 can
 one-shot
 more


things
 and
 you
 can
 have
 more
 variants,


which
 we
 like
 cuz
 we
 can
 experiment
 with


different
 features.
 We
 can
 experiment


with
 like
 one
 feature
 looking
 very


different
 in
 four
 different
 users.
 But


the
 problem
 for
 us
 specifically
 at


Cronulla
 was
 that
 we
 are
 a
 desktop
 app,


which
 means
 you
 can
 only
 run
 one


instance
 of
 the
 app
 at
 a
 time.
 And
 there


was
 a
 lot
 of
 friction
 when
 it
 came
 to


like
 testing
 new
 features,
 different


variants,
 and
 actually
 testing
 those
 in


parallel.


>> [clears throat]


>> So,
 before,
 you
 know,


before
 you'd
 have
 to
 like
 run
 the


Electron
 app
 locally,
 install
 the


dependencies,
 and
 test
 things.
 If
 you


wanted
 a
 coworker
 to
 to
 test
 those


changes,
 you'd
 have
 to
 get
 them
 to
 do


those
 things
 as
 well.
 We
 We
 didn't
 have


the
 same
 luxuries
 as
 like
 web
 apps
 do.


So,
 essentially,
 what
 we
 did
 is
 we
 took


our
 Electron
 app
 and
 we
 turned
 the


front-end
 of
 the
 Electron
 app
 into
 a
 web


shell.
 And
 this
 was
 deployed
 online.
 So,


now
 our
 CI,
 whenever
 we
 open
 a
 PR,
 we


get
 a
 preview
 link
 and
 we
 can
 go
 and


test
 those
 things.
 And
 this
 generally


sped
 up
 our
 development
 time
 so
 much


more.
 And
 like
 the
 cooler
 part
 of
 this


is
 that
 because
 LLMs
 can
 now
 self-verify


their
 work,
 these
 guys
 are
 now
 like
 once


we
 open
 a
 PR,
 Cursor
 goes
 and
 tests
 it,


uploads
 a
 screenshot
 into
 our
 PRs,
 which


speeds
 up
 the
 testing
 so
 much
 more.


And
 again,
 this
 is
 like
 you
 might
 think


that
 this
 is
 a
 lot
 of
 work,
 but
 it's


actually
 quite
 simple.
 So,
 what
 we
 did


is
 for
 those
 of
 you
 are
 not
 familiar


with
 Electron,
 there's
 obviously
 a
 main


process


and
 a
 render
 process.
 The
 main
 process


works
 with
 the
 system
 APIs
 and
 the


render
 process
 is
 basically
 your


front-end.
 And
 essentially,
 we


abstracted
 our
 IPC
 APIs,
 which
 is
 the


system
 APIs,


to
 fall
 back
 to
 web
 standards
 when
 we're


in
 the
 web
 environment.
 And
 similarly


with
 React
 APIs
 as
 well,
 like
 routers,


sessions,
 and
 query
 layer,
 we
 move
 those


to
 the


web
 standards.
 And
 essentially,
 this


just
 made
 the
 render
 agnostic
 of
 of


Electron.
 And
 we
 can
 just
 simply
 run
 it


as
 a
 web
 app.
 So,


this
 has
 helped
 us
 on
 top
 of
 the
 LLM


improvements
 was
 like
 we
 were
 able
 to


just
 like
 change
 and
 like
 test
 like
 one


feature
 in
 like
 multiple
 different


variants.
 So,
 like
 whatever
 the
 end


product
 is
 actually
 feels
 super
 good
 cuz


we
 know
 that
 we've
 tried
 so
 many


different
 variants.


And
 we
 actually
 felt
 those
 products
 in


in
 like
 in
 practice
 rather
 than
 just


like
 seeing
 it
 in
 Figma.


So,
 essentially,
 this
 this
 is
 basically


a
 long
 talk
 to
 tell
 you
 that
 the
 answer


isn't
 to
 one-shot
 better.
 It's
 about


figuring
 out
 how
 you
 can
 make
 that


feedback
 loop
 where
 it
 kind
 of
 feels


like
 playing
 a
 tennis
 game
 with
 LLM.
 So,


the
 end
 product
 feels
 more
 like
 magic


rather
 than
 just
 like
 a
 black
 box
 and


hoping
 that
 the
 feature
 that
 you're


going
 to
 release
 works
 well
 with


customers
 and
 having
 that
 conviction


that
 what
 you're
 shipping
 is
 actually


going
 to
 connect
 to
 the
 users.


Thank
 you.
 Any
 questions?


>> [applause]


>> What
 do
 you
 think
 about
 re-platforming


from
 Electron
 to
 Tauri?


We've
 thought
 about
 moving
 to
 Tauri
 a


couple
 times.


Um


I
 think
 the
 way
 Electron
 serves
 us
 right


now
 has
 been
 super
 nice.
 Like
 the
 APIs


changing
 quite
 a
 quite
 a
 lot.
 We've


tried
 Tauri
 before
 as
 well
 and
 we
 didn't


really
 see
 massive
 performance
 gains,


which
 we
 which
 is
 what
 we
 care
 about
 the


most.


So,
 yeah,
 it's
 been
 discussed
 before.


We've
 played
 around
 with
 it,
 but
 haven't


shipped
 it.


Cool.


Thank
 you,
 guys.


>> [applause]


>> Yay!


>> [music]
</details>

### 提升 LLM 可观测性：自研追踪工具的重要性

LLM 的行为常被视为一个“黑箱”，理解其内部运作机制至关重要。Cronulla 公司着手构建自定义的追踪工具，以获得对 LLM 工具调用（从开始到结束）的全面可见性。这些工具提供了对单个工具调用、推理过程、搜索工具、成本结构等各个环节的深入洞察，并允许按照需求进行数据结构化。

该工具的 UI 设计旨在服务内部所有团队，包括工程师、产品、数据和客户体验（CX）人员，使他们无需进行复杂的 CloudWatch 查询即可快速诊断问题。这极大地简化了对 LLM“黑箱”的理解过程。过去，构建此类工具可能需要依赖第三方 SaaS 提供商，耗时耗力。如今，借助 LLM 的能力，开发者可以更高效地构建内部工具，满足自身特定需求。

虽然可以利用 OpenTelemetry 等框架，并结合 AI SDK 将数据保存到数据库，但前端界面的重要性不容忽视，它直接影响用户如何查找和解决问题。例如，公司创始人会利用这些工具深入分析代理循环（agent loop），精确找出问题所在，从而在迭代中进行改进。

<details>
<summary>Original English</summary>

And
yeah,
as
you
as
you
know,
like
LLM


behavior
is
largely
seen
as
like
a
black


box,
but
we
want
to
kind
of
go
very
deep


into
the
details
and
figure
out
exactly


what's
going
on.
So,
what
we
did


recently
at
Cronulla
is
we
started


building
our
own
tracing
tools.
And


obviously,
thanks
to
LLMs,
you
can


actually
one-shot
these
things.
And
this


is
where
one-shotting
is
kind
of
nice.


And
so,
we
built
our
tooling
tracing


tools
here
where
we
basically
have


complete
visibility
on
the
tool
calls


straight
from
the
beginning
to
the
end.


So,
we
have
full
visibility
over
the


individual
tool
calls,
why
it's
making


those
tool
calls,
the
search
tools,
the


reasoning
tools,
the
cost
structured


exactly
how
we
want
it.
And
the
most


useful
part
of
this
is
that
we


structured
the
data
exactly
how
we
want


it.
And
the
UI
is
built
to
like
serve


our
our
employees
internally,
not
just


like
engineers,
but
also
product,


data,
and
like
CX,
and
everyone.
So,
you


don't
have
to
like,
you
know,
go
into


CloudWatch
and
do
like
very
complex


queries
to
figure
 out
why
something


failed.
And
that's
been
like
the
key
for


us
in
like
figuring
out
this
black
box.


And
previously,
obviously,
building
this


kind
of
tools
would
be
like
up
 to
using


a
SaaS
provider.


And
it
simply
wouldn't
you
simply


wouldn't
have
the
time.
But
now
you


actually
can
spend
time
building
this


tracing
tool
that
actually
serves
what


you
need.


And
this
is
obviously
a
very
basic


example,
but
obviously
you
can
use


OpenTelemetry
or
like
other
providers.


But
we
essentially
just
like
save
things


to
a
DB,
wrap
around
like
AI
SDK,
and


then
the
front-end
is
like
kind
of
like


the
most
important
part
cuz
that's
what


people
are
going
to
use
to
figure
 out


what
 breaks
 and
 what
 doesn't.
 And
 we


literally
 have
 like
 our
 founder


literally
 goes
 into
 like
 the
 details


like
 following
 the
 agent
 loop
 completely


front
 to
 back
 to
 figure
 out
 exactly
 what


went
 wrong.
 So,
 then
 at
 the
 end
 of
 this,


you
 can
 actually
 figure
 out
 like,
 you


know,
 this
 output
 feels
 off
 to
 like


exactly
 what
 failed.
 And
 then
 when
 you


iterate,
 you
 can
 improve
 on
 those


things.
</details>

### 桌面应用中的 LLM 创新：Electron 至 Web Shell 的演进

除了 LLM 本身的行为，用户交互和体验也是产品成功的关键。LLM 允许产品进行更多样化的实验和功能变体，但对于 Cronulla 这样的桌面应用而言，一次只能运行一个实例，这给同时测试新功能、不同变体带来了摩擦，尤其是在并行测试方面，不如 Web 应用灵活。

为了解决这个问题，Cronulla 将其 Electron 应用的前端转变为一个“Web Shell”，并将其部署到线上。现在，当团队打开一个拉取请求（PR）时，CI 系统会自动生成一个预览链接，允许所有团队成员方便地进行测试。这一改变极大地加速了开发周期。

更令人兴奋的是，随着 LLM 能够进行自我验证，像 Cursor 这样的工具可以在 PR 打开后自动测试代码，上传截图，进一步加速了测试流程。实现这一点的技术并不复杂：Electron 应用包含主进程（Main Process）和渲染进程（Render Process）。Cronulla 团队抽象了 IPC API，使其在 Web 环境下能回退到 Web 标准。同样，React API（如路由、会话、查询层）也迁移到了 Web 标准。这样一来，渲染层就与 Electron 解耦，能够独立作为 Web 应用运行。

这种架构上的转变，结合 LLM 本身的进步，使得团队能够更灵活地测试单个功能的不同变体，从而确保最终产品在用户体验上更加优化，这是仅凭 Figma 静态设计难以实现的。

<details>
<summary>Original English</summary>

But
as
I
said
earlier,
this
is
going
to


be
more
more
than
just
like
basic
LLM


stuff.


And
LLM
behavior
is
obviously
part
of


the
picture.
The
how
users
interact
and


experiences
your
product
is
also
very


important.


So,
with
LLMs,
you
can
one-shot
more


things
and
you
can
have
more
variants,


which
we
like
cuz
we
can
experiment
with


different
features.
We
can
experiment


with
like
one
feature
looking
very


different
in
four
different
users.
But


the
problem
for
us
specifically
at


Cronulla
was
that
we
are
a
desktop
app,


which
means
you
can
only
run
one


instance
of
the
app
at
a
time.
And
there


was
a
lot
of
friction
when
it
came
to


like
testing
new
features,
different


variants,
and
actually
testing
those
in


parallel.


>> [clears throat]


>> So,
before,
you
know,


before
you'd
have
to
like
run
the


Electron
app
locally,
install
the


dependencies,
and
test
things.
If
you


wanted
a
coworker
to
to
test
those


changes,
you'd
have
to
get
them
to
do


those
things
as
well.
We
We
didn't
have


the
same
luxuries
as
like
web
apps
do.


So,
essentially,
what
we
did
is
we
took


our
Electron
app
and
we
turned
the


front-end
of
the
Electron
app
into
a
web


shell.
And
this
was
deployed
online.
So,


now
our
CI,
whenever
we
open
a
PR,
we


get
a
preview
link
and
we
can
go
and


test
those
things.
And
this
generally


sped
up
our
development
time
so
much


more.
And
like
the
cooler
part
of
this


is
that
because
LLMs
can
now
self-verify


their
work,
these
guys
are
now
like
once


we
open
a
PR,
Cursor
goes
and
tests
it,


uploads
a
screenshot
into
our
PRs,
which


speeds
up
the
testing
so
much
more.


And
again,
this
is
like
you
might
think


that
this
is
a
lot
of
work,
but
it's


actually
quite
simple.
So,
what
we
did


is
for
those
of
you
are
not
familiar


with
Electron,
there's
obviously
a
main


process


and
a
 render
 process.
The
main
process


works
with
the
system
APIs
and
the


render
process
is
basically
your


front-end.
And
essentially,
we


abstracted
our
IPC
APIs,
which
is
the


system
APIs,


to
 fall
 back
 to
 web
 standards
 when
 we're


in
 the
 web
 environment.
And
 similarly


with
 React
 APIs
 as
 well,
 like
 routers,


sessions,
 and
 query
 layer,
 we
 move
 those


to
 the


web
 standards.
And
essentially,
this


just
made
the
render
agnostic
of
of


Electron.
And
we
can
just
simply
run
it


as
a
 web
 app.
So,


this
 has
 helped
 us
 on
 top
of
 the
 LLM


improvements
 was
 like
 we
 were
 able
 to


just
 like
 change
 and
 like
 test
 like
 one


feature
 in
 like
 multiple
 different


variants.
So,
 like
 whatever
 the
 end


product
 is
 actually
 feels
 super
 good
 cuz


we
 know
 that
 we've
 tried
 so
 many


different
 variants.


And
 we
 actually
 felt
 those
 products
 in


in
 like
 in
 practice
 rather
 than
 just


like
 seeing
 it
 in
 Figma.
</details>

### 迭代反馈与用户体验：打造“魔法般”的 LLM 产品

总而言之，解决 LLM 集成问题的答案并非仅仅是“一枪毙命”（one-shot better），而是要建立一个持续的反馈循环，让与 LLM 的互动过程感觉像是“玩网球”，用户能够感受到他们正在发送的指令和 LLM 的响应之间存在一种动态的、富有成效的交互。这样的过程能够创造出更具“魔法感”的用户体验，而不是依赖于一个难以捉摸的“黑箱”来判断所发布的 LLM 功能是否能真正与用户产生共鸣。

在问答环节中，有观众询问了关于从 Electron 迁移到 Tauri 的看法。演讲者表示，公司曾多次考虑过 Tauri，但目前 Electron 的运行方式对他们来说非常理想。尽管 API 变化频繁，他们曾尝试过 Tauri，但并未看到显著的性能提升，而性能是他们最关心的。因此，尽管 Tauri 被讨论过且有所尝试，但尚未正式发布。

<details>
<summary>Original English</summary>

So,
essentially,
this
this
is
basically


a
long
talk
to
tell
you
that
the
answer


isn't
to
one-shot
better.
It's
about


figuring
out
how
you
can
make
that


feedback
loop
where
it
kind
of
feels


like
playing
a
tennis
game
with
LLM.
So,


the
end
product
feels
more
like
magic


rather
than
just
like
a
black
box
and


hoping
that
the
feature
that
you're


going
to
release
works
well
with


customers
and
having
that
conviction


that
what
you're
shipping
is
actually


going
to
connect
to
the
users.


Thank
you.
Any
questions?


>> [applause]


>> What
 do
 you
 think
 about
 re-platforming


from
 Electron
 to
 Tauri?


We've
 thought
 about
 moving
 to
 Tauri
 a


couple
 times.


Um


I
 think
 the
 way
 Electron
 serves
 us
 right


now
 has
 been
 super
 nice.
Like
 the
 APIs


changing
 quite
 a
 quite
 a
 lot.
We've


tried
 Tauri
before
as
well
and
we
didn't


really
see
massive
performance
gains,


which
we
which
is
what
we
care
about
the


most.


So,
yeah,
it's
been
discussed
before.


We've
played
around
with
it,
but
haven't


shipped
it.


Cool.


Thank
 you,
 guys.


>> [applause]


>> Yay!


>> [music]
</details>