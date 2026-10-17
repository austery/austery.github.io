---
author: AI Engineer
date: '2026-07-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9arM9b7JgOo
speaker: AI Engineer
tags:
  - agentic-workflow
  - sandbox-testing
  - terminal-multiplexing
  - model-selection
title: 研发效能革命：利用 Open Claw 与多 Agent 架构重构研发流程
summary: 本文基于 Jeffrey Lee-Chan 的分享，探讨了如何通过 Open Claw、多 Agent 编排系统以及终端多路复用器（tmux/Cmux）构建高度自治的开发与测试环境。内容涵盖了 Open Claw 的上下文隔离与记忆机制、多 Agent 并行开发（Worktrees）、Staging 沙箱测试策略，以及在成本约束下的模型选择策略。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Open Claw
  - Cmux
  - tmux
  - Codex 5.3
  - GPT-5.4
  - MiniMax
media_books: []
status: evergreen
---
### Staging 环境搭建与多路 Open Claw 实验
在本次分享中，主讲人探讨了 **Open Claw**（一种基于 AI 的代理协助工具）的部署与工作流搭建。针对不同水平的开发者，提供分层式的配置方案：初学者重点在于基础环境的安装与跑通；而高级开发者则可以尝试构建更复杂的实验性**双重 Staging 沙箱环境**（Double Open Claws Staging Setup），通过同时运行两个 Open Claw 实例来模拟分级部署和协作。分享的日程规划涵盖基础答疑、高级专题讨论（如 Staging 调试）及互动环节，旨在通过物理定时器的辅助来保持节奏，提升开发者的实际操作体验。

<details>
<summary>Original English</summary>

workshop
 setup,
 so
 um


there
 are
 some
 people
 who
 kind
 of
 have


like
 never
 installed
 open
 claw,
 and
 I


want
 to
 kind
 of
 get
 them
 set
 up.
 And


then
 the
 other
 people
 like


want
 to
 try
 an
 experimental
 thing,
 which


I
 haven't
 even
 fully
 gotten
 working,
 but


I
 think
 for
 more
 advanced
 people
 that'll


be
 cool
 um
 to
 get
 like
 a
 sort
 of
 staging


environment
 and
 run
 two
 open
 claws.
 So,


I
 think
 if
 I'm
 not,
 you
 know,
 too
 busy


helping
 new
 people
 set
 up,
 then
 I'll
 try


to
 help
 people
 like
 finish
 debugging
 the


last
 part,
 or
 maybe
 someone
 else
 will


get
 it.


And
 I
 think
 uh
 10
 minutes
 Q&A,
 10


minutes
 some
 more
 advanced
 topics,


and
 then
 just
 more
 Q&A.


And
 uh
 probably
 after
 every
 5
 minutes
 or


so,
 we
 can
 do
 a
 bit
 of
 a
 few
 minutes
 of


discussion.


So,
 I'll
 just
 set
 some
 timers
 to
 make


sure
 I
 don't
 go
 off
 track.


All
 right.


Let
 me
 start.


All
 right.
 Can
 everyone
 see
 this


presentation?


>> Yes.


>> All
 right,
 cool.


>> Yeah.

</details>

### 独立上下文与专业化记忆管理
**Open Claw** 的核心优势在于其**上下文隔离与专业化记忆机制**（Specialization & Context Management）。相较于直接在常规网页端或普通客户端使用 Claude，Open Claw 能够针对特定项目维护独立的任务上下文和历史记录。例如，开发者仅需发送一条极简的 Slack 消息（如“修复 skeptic 代理”），Open Claw 就能基于先前的对话上下文，准确识别并定位到专门用于代码审查的 **Skeptic 代理**（Skeptic Agent: 定制化的代码审查工具）。这种专门化设计极大地节省了宝贵的 Context Token——通常在普通 Claude 窗口中，系统规则、自定义技能和模型配置文件（如 `.cursorrules` 或 `CLAUDE.md`）会直接耗费约 25% 的上下文空间，而 Open Claw 将这些实现细节（How to do）与具体任务目标（What to do）相隔离，从而让开发者能够以极低的信息冗余进行高效的沟通与迭代。

<details>
<summary>Original English</summary>

So,
this
 kind
 of
 describes
 like
 my
 setup.
 Um
I'll
 just
 keep
 it
 really
 high
 level
 for
this
 part
 where
when
 everything
 works,
 you
 know,
 maybe
like
 70%
 of
 the
 time,
 you
 describe
 your
task.


And
 then
 what's
 nice
 is
 open
 claw
 will
have
 like
 context
 and
 memory
 about
 what
you're
 talking
 about.


So,
 for
 example,
 like
 let's
 say
 I'm
like,
 "All
 right,
 fix
 this
 thing."


It's
 a
 very
 brief
 Slack
 message,
 but
open
 claw
 can
 remember
 like
 what
 I've
asked
 it
 to
 do
 before.


So,
 for
 example,
 I'm
 working
 on
 this
thing
 I'm
 calling
 a
 skeptic
 agent,
 and
it's
 a
 custom
 code
 review
 thing.


But
 if
 I'm
 like,
 "All
 right,
 fix
 the
skeptic
 agent."
 or
 whatever,
 right?
 It
kind
 of
 knows
 what
 that
 is,
 which
is
nice.
 You don't
 have
 to
 re-explain
 a
lot.


Um
 I
 use
 multiple
 agents
 with
 work
trees,
 that's
 very
 key
 for
parallelization.


Uh,
 CI
 code
good
 integration.


But
 you
 can
 kind
 of
 see
 you
 can
 talk
 to
it
 and
 be
 pretty
 brief
 and
 then,
you
 know,
 usually
 get
 reasonable
outcomes,
 but
 sometimes
 you'll
 have
 to
debug
 it.


So,
 then
 it's
 like,
 all
 right,
 there's
some
 time
 out
thing.
 I'm
 like,
 give
 it
 a
longer
 time
 out,
 right?


And
 then
 I
 asked
 that
 here
 like
 like
 uh,
you
 know,
 what
 are
 the
 priorities
 and
what
 we're
 working
 on.


And
 I'm
 reading
 it
 here.


And
 then
 I
 might
 have
 just
 said
 like,
 uh,
I
 just
 made
 code
 for
 it,
 right?


So,
 another
 interesting
 thing
 about
 this
is
 you
 can
 kind
 of
 see
 from
 like,
 um,
>> [clears throat]


>> the
 types
 of
 responses
 I
 give,
 they're
not
 that
 like,
 um,
special.
 As
 in
 I
 I
 actually
 think
 an
agent
 could
 replace
 me.


So,
 that's
 kind
 of
 what
 I'm
 working
 on
 right
 now
 to
 like
get
 things
 even
 more
 autonomous.
 You
 know,
 and
 you
 and
 you'll
 see
 this
with
 LLMs
 like
 you're
 working
 with
 them
and
 they'll
 be
 like,
"Hey,
 I've
 got
 this
 thing
 ready."
 And
I'm
 like,
 "Okay,
 we'll
 run
 the
 test,
right?"
 Uh,
 all
 right.
 So,
 I'll
 share
 the
 next
slide
 now.
 Oops.
 Okay.
 We're
 going
 to
 some
 concepts
 right
 now.
 Like,
 what
 is
 Open
 Claw?
 So,
I
 think
 what's
 cool
 about
 Open
 Claw
 is
it's
 not
 just
 about
 a
 particular
 repo
 or
the
 code,
 but
 more
 of
 the
 concept.
 So,
you
 know,
 I've
 got
 this
 cool
 super
diagram,
 but
first
 concept
 is
 frictionless
communication.


So,
 I
 know
 we
 have
 other
 things
 like
Claude
 co-work
 or
 whatever,
 but
 I
 think
they
 still
 have
 a
 similar
 concept
 where
it's
 like,
can
 you
 like
 easily
 talk
 to
 your
 AI
versus
 like
 you've
 got
 a,
um,
 remote
 desktop
 into
 your
 computer
 or
you
 have
 to
 go
 sit
 down.
 So,
 that
 kind
of
 enables
 certain
 really
 higher
 level
 of
 velocity.


Um
 then
 I
 think
 the
 central
 axis
 is
 very
important.
 So,
you
 know,
 there's
 a
 spectrum
 like
 I
 kind
 of
 go
 like
 a
 little
 more
 cowboy
 and
 I
 give
 it
 act.
 Open
 Claw
 has
 these
 agent
 orchestrator
managers
 that
 manage
 your
 workers
 for
you.
 Uh
 or
 sometimes
 when
 I
 want
 more
personal
 control,
 I
 use
 tmux
 terminals.


So
 tmux
 is
 like
 a
 terminal
 program,
 but
it's
 pretty
 good
 for
 parallelization
 and
AI
 development.


Then
 I
 use
 the
 open
 source
 framework
that
 I
 forked
 agent
 orchestrator
 to
 do
the
 workers.


And
 then
 once
 it
 gets
 to
 here,
 this
 part
is
 like
 not
 really
 controlled
 by
 me
 as
much
 anymore.
 Um
 so,
I'm
 calling
 them
 managed
 agents,
 but
basically
 like
you
 have
 a
 worker
 that
 runs
 Claude
 code
and
 Claude
 code
 itself
 can
 run
 agents
and
 those
 can
 have
 sub
 agents.
 So
 once
 you
 get
 to
 this
 Claude
 code
part,
 right?
 This
 part
 is
 not
 exactly
 my
stack,
 just
 stuff
 I
 use,
 but
 this
 part
of
 the
 stack
 I'm
 changing
 a
 lot
 more.
 Um
 I'll
 pause
 here
 to
 see
 if
 anyone
 has
any
 questions
 or
 thoughts.


>> Um
 can
 you
 hear
 me?
 So
 I
 I
 have
 a
question.
 So
the
 the
 real
 question
 is,
 you
 know,
 why
why
 use
 Open
 Claw
 versus
directly
 use
 Claude?


>> So
 yeah,
 that's
 that's
 definitely
 a
 good
question.
 Um


>> [clears throat]


>> The
 reason
 I
 use
 Open
 Claw
 as
specialization.


So
 when
 Open
 Claw
 makes
 a
 decision,
 I
want
 that
 context
 to
 be
 more
 about
 like
the
 spec
 or
 the
 goals
 or
 like
 the
history
 of
 what
 I
 want
 in
 the
 task
rather
 than
 the
 code.


And
 you
 can
 just
 imagine
 this,
 right?
 As
soon
 as
 you
 open
 up
 Claude,
 it
 reads
Claude
 MDs,
 it
 reads
 skills,
 it
 reads
 um
MCPs.
 A
 lot
 of
 those
 things
 are
 sort
 of
independent
 of
 like
 the
 actual
 task.
 It's
 more
 about
 how
 to
 do
 the
 task.
 Um
 so
 imagine
 like
 25%
 of
 your
 context
already
 taken
 up
 by
 implementation.
 Versus
 like
 when
 you
 think
 about
 open
claw,
 you're
 like,
 okay.
 I
 want
 to
 think
 about
exactly
 what
 I
 want
 to
 do
 and
 how
 it
relates
 to
 all
 the
 other
 slacks
 Jeffrey
sent
 me
 in
 the
 last
 2
 weeks
 and
 put
 it
all
 together
 and
 give
 me
 like
 a
reasonable
 spec.

</details>

### 并行研发基建：工作树与终端复用器
为了实现开发效率的最大化，本系统引入了**多代理并行工作流**（Multi-Agent Parallel Workflows），其底层核心在于 **Git 工作树**（Git Worktree: 允许在多个独立目录中同时检出多个分支的技术）与持续集成（CI）的深度整合。在开发控制权的设计上，系统呈现出一个从“手动干预”到“完全自治”的光谱：开发者既可以在需要个人掌控时，通过 **tmux/Cmux** 终端复用器直接操作独立的终端窗口；也可以将管理权移交给**代理编排管理器**（Agent Orchestrator Manager），由其自动调度下属的托管代理（Managed Agents）。这些托管代理本身能够运行复杂的 AI 工具（如 Claude Code），并能进一步向下级派生子代理（Sub-agents），形成树状的自主执行结构。通过将不同的开发任务分发至独立的 Git 工作树，并由多级代理并发执行，整个系统的研发吞吐量和并行度得到了本质上的提升。

<details>
<summary>Original English</summary>

Does
 every
 single
 thing
 a
 player
 does,
but
 it
 does
 it
 without
 a
 browser,
 right?
So
you
 could
 use
 MCP,
 which
 usually
 is
 JSON
or
 whatever
 or
 HTTP.
 Doesn't
 really
matter
 actually.
And
 then
 the
 final
 thing
 is
 the
 browser
test.
 So
 some
 things
 like
 are
 visual.
 I
mean,
 maybe
 you
 could
 even
 have
 CSS
tests
 or
 JS
 tests,
 right?
 And
 that
 kind
of
 goes
 here.
 But
 then
 the
 final
 thing
is
 visual.
So
 I
 would
 recommend
 you
 like
 try
 um
similar
 approaches
 to
 this
 and
 be
 like,
okay,
 like
 which
 problems
 truly
 needed
that
 human
 or
 not.
Um
 and
 I
 think
 what's
 kind
 of
 cool
 is
like
every
 quarter
 or
 you
 maybe
 even
 every
month
 like
 it
 improves.
So
 before
 like
 I
 had
 to
 really
 manually
test
 a
 lot
 because
 like
you
 know,
 this
 worked
 fine,
 right?
 But
these
 things
 didn't
 work
 that
 well
 with
agents
 like
 last
 year
 but
 like
 a
 year
ago
 even
 6
 months
 ago.
But
 now
 like
 um
 agents
 are
 pretty
 good
at
 like
 nailing
 down
 a
 lot
 of
 browser
tests
 for
 me.
 Versus
 like
 when
 I
 started
my
 agent
 would
 have
 a
 lot
 of
 problems,
you
 know,
 finding
 a
 pop-up
 and
 entering
a
 password.
 Now
 no
 problem.
Um
 that
 was
 a
 little
 long,
 but
 does
 that
kind
 of
 address
 the
 theme
 of
 your
question?


>> Yeah,
 I
 think
 this
 is
 good.
 Good.
 Thank
you.


>> Okay.


>> Thank
 you
 very


>> Just
 just
 remind
 me
 for
 all
 these
 slash
commands.
 I'll
 put
 um
 links
 here
instead.
All
 right,
 cool.
 Anyone
 have
 any
 other
questions
 related
 to
 some
 of
 that
 stuff?
All
 right.
 If
 not,
 I
 will
 go
 here.
All
 right.
 So,
 here's
 a
two
 websites
 that
 I've
 built.


>> [clears throat]


>> Yeah,
 while
 that
 loads,
 I'll
 show
 this
one.
So,
 this
 is
 like
 a
 AI
 RPG.
 Um
 what's
cool
 about
 this
 is
 you
 can
I've
 got
 a
 default
 campaign,
 for
example.


Um


>> [clears throat]


>> Yeah,
 pick
 some
 options.
 You've
 got
 a
avatar.
And
 uh
 what's
 cool
 about
 this
 is
 it
builds
 a
 custom
 world
 for
 you
 that
reacts
 to
 you.
 So,
 you
 can
 like
 kind
 of
say
 whatever
 you
 want,
 do
 whatever
 you
want,
 you'll
 get
 a
 story
 back.
Um
 the
 main
 difference
 between
 playing
this
 versus
 like
 um
 you
 know,
 you
 could
just
 always
 go
 into
 the
 Gemini
 chat
 or
or
 chat
 GPT
 or
 or
 whatever
 is
 that
um
 I
 have
 like
 a
 D&D
 system.
So,
 if
 you
 play
 your
 own
 like
 games
 or
novels,
 like
 you
 kind
 of
 just
 win
 too
much.
 Versus
 like
 with
 this,
 you'll
actually
 do
 like
 dice
 rolls
 and
 be
 like,
you
 know,
 did
 the
 person
 actually
 um
did
 you
 actually
 succeed
 in
 your
 action
or
 not?
All
 right.
 So,
 while
 this
 is
 going,
 I'll
also
 um
 show
 this
 thing.
Yeah,
 so
 this
 is
 funny.
Um
 website
 is
 like
 a
 multi-AI
analysis
 website.
 Um
so,
 what
 I
 found
 was
 like
whenever
 I
 was
 doing
 research
 or
 or
whatever,
 I
 would
 go
 to
 multiple
 models
and
 I'd
 be
 like,
 what's
 the
 answer?
 Then
I
 copy
 and
 paste
 them
 all.
 I
 put
 them
into
 one
 model.
Um
 so,
 pretty
 simple
 concept,
 but
 this
does
 it
 for
 you.
 So,
 usually
 I
 like
these
 answers
 better
 than
 like
 asking
one
 model.
 And
 I'm
 like,
 okay,
 how
 do
 I
do
 this
 workshop?
So,
 I
 can
 be
 like,
 okay,
 what's
 the
status?
Uh
 what's
 the
 latest
 PR
 now?
And
 um
what
 I
 like
 about
 this
 is
 it
 has
 that
sort
 of
 vertical
 tab
 type
 of
 thing.
 Cuz
when
 you
 go
 horizontal,
 it's
 really
 easy
to
 lose
 track
 of
 your
 tabs.
 Um
but
 we've
 got
 notifications,
 too.
 So,
when
 this
 thing
 is
 finished
 or
 this
 is
finished
 and
 I
 need
 to
 look,
 it'll
 give
me
 a
 notification.
 And
 I
 can
 just
 focus
on
 clearing
 the
 notifications.
So,
 here
 um
the
 way
 of
 using
 these
 terminals,
usually
 it's
 more
 like
 a
 manager
 rather
than
 a
 coder.
 Um
 and
 it's
 kind
 of
interesting,
 but
 it
 gives
 you
 a
 certain
benefit
 where
I
 feel
 I
 feel
 like
 the
 work
 is
 not
biased
 anymore.
 So,
 when
 I
 when
 I
 code
with
 these
 directly,
 um
I
 usually
 feel
 like
 there's
 a
 bias,
where
 it
 wants
 to
 say
 things
 are
 really
working
 or
 whatever,
 right?
 Versus
 like,
you
 know,
um
I'll
 show
 this.
 Let's
 look.
If
 this
 had
 been
 working
 on
 PR
 294
 by
itself,
 I
 think
 it
 would
 have
 been
 like,
"This
 PR
 is
 amazing.
 Like,
 we
 got
 to
merge
 it,
 right?"
 But
 then
 this
 one
was
like,
 "No,
 like,
 there's
 another
 PR
 that
should
 supersede
 it,
 and
 probably
 we
should
 just
 close
 this
 PR."
 Right?
 So,
that's
 kind
 of
 the
 benefit
 you
 get,
where
 the
 manager
 has
 a
 different
context
um
 than
 the
 workers.

</details>

### 终端多路复用与多模型评估平台
在工具链生态方面，项目深度整合了 **Cmux/tmux** 终端生态，并引入了多模型协同评估的设计思想。tmux 联创 Austin 分享了最新的技术演进，包括 **Cloud Code Teams 集成**（支持自动为协作会话生成终端）以及 **Cmux SSH**（支持通过 Tailscale 跨设备无缝管理 Mac Mini 等本地 staging 设备）。在实际研发中，开发者通过自建的**多模型联合分析平台**（Multi-AI Analysis Platform）来进行方案比对。该平台采用高效的**垂直标签页布局**（Vertical Tab Layout），将开发者提出的技术问题分发至不同厂商的模型，并将结果汇聚于统一视角中进行比对。同时，系统在执行浏览器自动化测试或视觉 CSS 测试时，能够将执行完毕的信号以异步通知的形式推送给开发者，使其能够像“管理者”而非“打字员”一样，只需关注并清理通知队列，极大地缓解了上下文切换的疲劳。

<details>
<summary>Original English</summary>

>> [snorts]


>> Uh
 let's
 see.
All
 right,
 so
 this
 is
 compacting
whatever.
So,
 it
 will
 take
 some
 time
 to
 complete.
Don't
 want
 to
 wait
 for
 it,
 but
 when
 it
completes,
 you
 see
 these
 notifications,
and
 I
 think
 my
 efficiency
 has
 improved
 a
lot
 with
 tmux.
 Um
I
 think
 is
 Austin
 or
 someone
 from
 tmux
here?


>> Yeah,
 here.
 What's
 up?
 Go.


>> Yeah,
 so
 Austin
 is
 uh


>> [clears throat]


>> one
 of
 the
 guys
 behind
 tmux.
Um
 you
 know,
 big
 fan
 of
 it,
 and
 I'm
 not
I'm
 not
 paid
 to
 say
 this
 or
 anything,
but
 big
 fan
 of
 tmux.
 Uh
 been
 using
 it
 a
lot.
I
 don't
 know,
 you
 can
 spend
 a
 minute
 if
you
 want
 to
talk
 about
 anything
 cool
 about
 tmux.


>> Yeah,
 so
 yeah,
 one
 of
 the
 creators
 of
tmux.
 Really
 happy
 to
 have
 Jeff
 as
 one
of
 our
 power
 users.
 And
 also
 like
 kind
of
 endorsing
 it
 for
 free.
But
 yeah,
 lots
 of
uh
 yeah,
 lots
 of
 things
 that
 we're
shipping.
 We
 shipped
 a
 Cloud
 Code
 Teams
integration.
 So,
 if
 anyone
 is
 using
Cloud
 Code
 Teams
 and
 wants
 to
 actually
see
 what
 the
 salvations
 are
 doing,
 we'll
automatically
 spawn
 terminals
 for
 that.
We
 also
 shipped
 Cmux
 SSH.
 So,
 if
 you
 do
any
 SSH
 work,
you
 can
 use
 our
 native
 Cmux
 SSH
 to
 you
know,
 do
 your
 tailscale
 and
 etc.
To
 other
 computers.
 You
 can
 even
 use
 it
to
 run
 your
 own
 open
 claw
 in
 your
 Mac
minis.
But
 yeah,
 just
 one
 of
 the
 creators.
Please
 feel
 free
 to
 email
 me
 if
 you
 have
anything
 that
 you
 think
 is
 a
 bug
 or
 any
feedback,
 feature
 requests.
I'm
 always
 available
 and
 yeah,
 just
 love
seeing
 people
 using
 Cmux
 and
 always
 want
to
 take
 as
 much
 feedback
 as
 I
 can
 to
like
 get
 them
 as
 get
 them
 as


>> Okay,
 so
 just
 download
 that.


>> Yeah.
They
 actually
 have
 an
 app
 too.
 So,
 the
app
 might
 be
 nice.


>> Yeah.
 Okay.
And
 then
 use
 that
 to
 help
 me
 get
 back
 in
and
 set
 set
 up.


>> Exactly.
 Yeah.


>> Okay.
 Okay,
 cool.
 Thanks.

</details>

### 隔离沙箱环境下的测试与双重 Token 策略
针对开发者普遍关心的**沙箱与 Staging 环境部署**（Staging Sandbox Setup），Aaron 提出了关于 Token 消耗与多环境运行的疑问。在最佳实践中，运行 staging 实例确实会因为对两套系统发送相同指令而增加 Token 消耗，但其带来的系统鲁棒性与开发隔离性远超成本支出。推荐的规范化流水线为：开发者首先在本地环境进行自主编码与局部调试，随后将代码推送至基于 Docker 或隔离分区的 **Staging 沙箱环境**运行全面的自动化集成测试，验证通过后，最后合并分支并正式部署至生产环境。这种双重 Staging 架构既规避了直接在生产环境调试导致的服务中断风险，又合理地分摊了 Token 的使用成本。

<details>
<summary>Original English</summary>

>> All
 right.
 Is
 using
 the
 sandbox,
 it
should
 not.
 Where
 would
 you
Have
 you
 had
 Have
 you
 run
 into
 any
troubles
 Aaron
 about
 sandbox
 token
usage?


>> Uh
 no.
 I'm
 just
 I'm
 not
 technical
 at
all.
I
 have
 open
 claw
 installed,
 so
 I'm
>> Okay.


>> very
 newbie
 questions.


>> No
 no
no
 bad
 questions.
 All
 good.
 Yeah.
 Uh
they're
 not
 the
 sandbox
 wouldn't
 do
that.
I
 think
 if
 if
 everything's
 working
 well
for
 you,
 you
 know,
 keep
 using
 the
sandbox.
 For
 me,
 I
 just
 you
 know,
 don't
 use
 a
sandbox
 and
 so
 so
 far
 nothing
 bad
 has
happened.
 But
 I
 think
 if
 I
 had
 an
external
 bot,
 then
 I
 would
 use
 a
 sandbox
too.


>> You
 changing
 the
 model
 testing
 a
 new
model
 like
 it'll
 go
 down
 then
 I
 have
 to
figure
 out
 how
 to
 get
 it
 back
 up
 again.
So
 I
 think
 I
 want
 to
 set
 up
 this
 sandbox
because


>> Oh,
 sorry.
 Sorry.
 Um
 okay,
 wait.
 There's
two
 kinds
 of
 things.
 Okay.
The
 sandbox
 that
 most
 people
 talk
 about
means
 like
 they
 run
 it
 in
 Docker
 or
 they
like
 have
 it
 running
 in
 isolated
 part
 of
their
 system.
But
 the
 other
 one
 was
 the
 one
 where
 I
made
 the
 staging
 instructions
 where
 I
was
 like
 oh


>> Yeah.


>> Okay.
 So
that
 could
 double
 your
 token
 usage
 if
you
 send
 the
 same
 work
 to
 both
 of
 them.
If
 you
 have
 two
 of
 them,
 right?
 Um
 but
 I
think
 the
 way
 I
 would
 use
 it
 is
 not
 like
 that.
 Like
I
 think
 I
 would
 do
 local
 development
 and
then
 I
 would
 run
 integration
 tests
 on
the
 um
 sandbox
 or
 staging
 one,
 right?
 So
I
 have
 two
 of
 them.
 And
 then
 once
 like
everything's
 good,
 then
 I
 would
 merge
the
 code
 and
 deploy
 to
 the
 production
one.


>> I
 see.


>> It
 wouldn't
 double
 your
 usage,
 but
 it
would
 definitely
 increase
 it.
 But
 then
the
 benefit
 is
 you
 might
 have
 some
 more
reliability.
 So


>> Yeah.


>> I
 I
 made
 some
 instructions
 and
 I
 was
kind
 of
 in
 the
 middle
 of
 setting
 it
 up,
but
 then,
 you
 know,
 it's
 like
 competing
with
 the
 other
 one,
 so
 I
 got
 to
 debug
it.


>> Yeah.


>> But
 I
 think,
 you
 know,
 it's
 it's
 worth
trying
 out
 though.
 So
 I
 had
 that
 for
more
 advanced
 people
 to
 give
 it
 a
 give
it
 a
 try.


>> Cool.
 Thanks.
 What

</details>

### 成本敏感型模型路由与降级策略
在最终的模型路由与调用链设计中，**成本敏感型模型选择策略**（Cost-Aware Model Routing）是保障系统长期运行的关键。在实际的代理编排中，虽然 GPT-5.4 拥有强大的推理能力，但其极高的 Token 消耗往往会导致研发预算迅速枯竭。因此，系统默认采用 **Codex 5.3** 作为核心编排模型，它在复杂任务逻辑的处理与 Token 消耗之间取得了较好的平衡。当 Codex 5.3 的 Token 额度临近耗尽时，系统将动态平滑降级至 **MiniMax** 等高性价比的备用模型。这种基于配额 and 成本的动态路由机制，在确保基础代码生成和编排质量的同时，大幅优化了多 Agent 并行研发的整体经济效益。

<details>
<summary>Original English</summary>

>> Or if
 you're
 not
 as
 advanced,
 if
 you
want
 it,
 you
 know,
 you
 can
 try
 it.


>> Yeah,
 I
 am
 definitely
 going
 to
 play
around.
 But
 what
 a
 what
 model
 do
 you
use?
 Like
 do
 you
 have
 a
something
 that
 like
 a
 default
orchestrator
 model
 and
 then
 you
say
 for
 this
 you
 use


>> use
 Codex
 53.
 Um
I
 found
 I
 found
 uh
 GPT
 54
 to
 just
 use
more
 tokens.
 Um
and
 even
 53
 like
like
 I
 I
 just
 get
 destroyed
 all
 the
time,
 right?
 So
 I
 might
 have
 to
 adjust
that.
 Um
 so
 basically
 I
 use
 this
 until
like
this
 is
 getting
 low
 and
 then
 I
 just
switch
 to
 MiniMax,
 which
is
 not
 as
 good,
 but
 it
 kind
 of
 gets
 the
job
 done.
And
 then
 this
 is
 more
 about
 money
 than
like
 preference,
 but
some
 some
 work
 I
 can
 still
 kind
 of
 just
do
 um
 um
 here.
 So,
 I
 don't
 always
 have
to

</details>