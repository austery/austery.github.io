---
author: AI Engineer
date: '2026-04-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ClWD8OEYgp8
speaker: AI Engineer
tags:
  - agentic-development
  - collaborative-ai
  - software-development-tools
  - team-alignment
  - developer-productivity
title: AI 协作工程：弥合智能体与人类团队之间的鸿沟
summary: 本文深入探讨了智能体（Agent）在软件开发中的挑战，揭示了当前智能体能力扩展与团队协作需求之间的脱节。文章介绍了 GitHub Next 推出的全新原型工具 ACE（Agent Collaboration Environment），它旨在通过提供一个集成的云端协作空间，促进跨职能团队在规划、编码和沟通上的同步，从而提升软件质量和团队效率，最终将开发时间用于更深入的思考和精湛的工艺。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - GitHub
products_models:
  - ACE
media_books: []
status: evergreen
---
### AI 协作工程：个体赋能与团队协作的挑战

当前，AI 智能体（Agent）技术正以前所未有的速度发展，预示着“一人掌握数十个智能体”的开发模式。这种模式的核心承诺是极大地提升个体开发者的生产力，期望一个开发者能够配备一群智能体来完成过去需要整个开发团队才能完成的工作。然而，这种“一骑绝尘”的个体效率提升，仅仅解决了软件开发流程中的一个维度，却忽视了软件开发本质上是一项**团队运动**。软件的成功并非源于个体输出的简单叠加，而是依赖于团队成员之间对目标、愿景和具体实现的**共识与协调**。将个体生产力视为最终目标，如同“九女能在一个月内生下一个孩子”的逻辑，忽略了复杂系统所需的时间、沟通和协同。当个体输出的“量”增加时，如果缺乏有效的沟通和协调，原本就存在的问题只会加剧，而非解决。

<details>
<summary>Original English</summary>

Okay.
 Are
 we
 all
 good?
 Right.
 Uh
 so
 yes,


this
 talk
 uh
 is
 called
 uh
 one
 developer,


two
 dozen
 agents,
 zero
 alignment.
 Uh


this
 is
 the
 case
 for
 why
 we
 need


collaborative
 AI
 engineering.
 So
 first
 a


very
 quick
 intro.
 I'm
 Maggie.
 I
 work
 uh


at
 GitHub
 as
 a
 staff
 researcher


engineer.
 Uh
 at least
 that's
 my
 title.


I'm
 actually
 a
 designer
 back
 when
 that


was
 like
 a
 separate
 thing
 to
 engineer.


Um
 and
 next
 is
 the
 labs
 team
 within


GitHub.
 So
 we
 work
 on
 kind
 of
 more


experimental
 risky
 bets
 than
 the
 rest
 of


the
 organization.
 We
 like
 to
 call
 it
 the


department
 of
 [ __ ]
 around
 and
 find
 out.


Um
 and
 like
 everyone
 else,
 we
 are
 of


course
 trying
 to
 shape
 new
 developer


agentic
 tools.


So
 I
 think
 this
 is
 what
 many
 people


think
 peak
 developer
 productivity
 looks


like
 right
 now,
 right?
 This
 is
 like
 a


wall
 of
 terminal
 based
 coding
 agents
 all


running
 in
 parallel
 on
 one
 person's


machine.


I
 like
 to
 call
 this
 the
 one
 man
 two


dozen
 claudes
 theory
 of
 the
 future.
 Uh


so
 the
 promise
 that
 we're
 given
 here
 is


that
 one
 person
 with
 a
 fleet
 of
 agents


will
 do
 the
 work
 of
 an
 entire
 team
 of


developers.


The
 main
 problem
 with
 this
 dream
 is
 it


assumes
 that
 software
 is
 made
 by
 one


person.
 All
 of
 these
 tools
 are
 single


player
 interfaces
 and
 they
 focus
 on


scaling
 up
 the
 work
 of
 the
 individual.


But
 there
 is
 limited
 value
 in
 scaling
 up


one
 individual
 because
 software
 is
 not


made
 by
 one
 person
 in
 a
 vacuum.
 It
 is
 a


team
 sport
 and
 everyone
 building
 it


needs
 to
 agree
 on
 what
 they're
 building


and
 why.
 Believing
 individual


productivity
 leads
 to
 great
 software
 is


nine
 maybe
 nine
 women
 make
 a
 baby
 in
 one


month
 logic.
 uh
 more
 individual
 output


doesn't
 solve
 problems
 that
 require


communication
 and
 coordination.
 It
 makes


them
 worse.
</summary>
</details>

### 开发流程的塌陷与对齐成本的放大

随着技术的发展，**代码实现**本身正迅速成为一个“已解决”的问题。无论是开发速度、成本还是代码质量，都在不断优化。这使得软件开发的核心挑战从“如何构建”转向了“**是否应该构建**”。而“**就构建什么达成一致**”成为了新的瓶颈。传统上，软件开发流程包含清晰的**规划（Planning）**、**构建（Building）**和**评审（Review）**阶段，每个阶段都有重要的**对齐（Alignment）**触点。然而，AI 智能体极大地压缩了“构建”阶段的时间，使得原有的规划和评审节点变得稀疏，开发流程的“窗口期”发生了塌陷。

原本用于在开发周期早期进行沟通和对齐的会议、评论、草稿 PR 等环节，因**实现成本的降低**而被简化甚至省略。开发者倾向于快速输入指令，让智能体生成代码，而忽略了对计划的细致审查或与团队的深入讨论。这种“**本地化规划模式**”，即智能体独立执行规划且不与团队共享，导致了更多对齐点的缺失。最终，所有对齐的压力被推到了**代码审查（Pull Request）**阶段，而 PR 本身并非为承担如此重大的早期对齐任务而设计，导致其在这一功能上的表现不佳。

此外，**AI 生成代码的评审时间反而增加**，因为它们可能引入不必要的复杂性或超出预期的功能。这种“**非对齐的加速**”不仅不会解决问题，反而会使其恶化，导致大量的**无效工作**，例如开发了无人需求的特性，或者在收到关键反馈后不得不完全推翻重写。更严重的是，**协调深度（Coordination Depths）**加剧，表现为：由于多个智能体或开发者可能同时修改相同文件，导致棘手的**合并冲突（Merge Conflicts）**；重复开发同一功能；以及堆积如山的、缺乏上下文的 PR 待评审。这一切都源于当前主流的协作工具，如 GitHub、Slack、Jira 等，它们大多诞生于**过时的软件开发范式**，并未为智能体驱动的、高度并行的开发环境做好准备。

<details>
<summary>Original English</summary>

An
 implementation
 is
 rapidly
 becoming
 a


solved
 problem,
 right?
 Probably
 everyone


here
 believes
 that.
 Uh
 writing
 code
 is


now
 fast.
 It's
 getting
 cheaper
 and


quality
 is
 going
 up
 and
 to
 the
 right.


The
 hard
 question
 is
 no
 longer
 how
 to


build
 it.
 It's
 should
 we
 build
 it.


Agreeing
 on
 what
 to
 build
 is
 the
 new


bottleneck.
 So
 everyone
 on
 your
 team


needs
 to
 be
 involved
 in
 asking,
 are
 we


making
 the
 right
 thing?
 Are
 we
 spending


our
 energy
 in
 the
 right
 place?
 And
 how


do
 we
 have
 the
 most
 impact?
 When


production
 is
 cheap,
 opportunity
 cost


becomes
 the
 real
 cost.
 You
 can't
 build


everything
 and
 whatever
 you
 pick
 comes


at
 the
 cost
 of
 everything
 else.


Anyone
 who
 ships
 software
 on
 a
 team


knows
 that
 this
 isn't
 a
 new
 problem.
 Um,


alignment
 has
 always
 been
 a
 bottleneck,


but
 agents
 have
 made
 the
 cost
 of
 not


being
 aligned
 as
 a
 team
 much,
 much


higher.


What
 makes
 it
 worse
 is
 that
 all
 our


coordination
 tools
 are
 still
 from


another
 era.
 So,
 GitHub,
 Slack,
 Jira,


Linear,
 and
 the
 like
 are
 as
 they


currently
 stand
 are
 not
 designed
 for
 the


agentic
 development
 worlds.
 We
 are


funneling
 masses
 of
 agentic
 outputs
 into


platforms
 that
 were
 built
 for
 an


outdated
 way
 of
 building
 software.


Um
 he
 I
 know
 like
 I
 work
 at
 GitHub
 so


that
 might
 sound
 heretical
 for
 me
 to


say.
 Um
 but
 I
 promise
 it's
 not


controversial.
 There
 are
 very
 few
 people


internally
 who
 believe
 that
 the
 PR
 and


the
 issue
 are
 the
 future
 of
 software


development.
 And
 there
 are
 lots
 of
 us


inside
 the
 machine
 trying
 to
 explore


what
 comes
 next.


So
 this
 is
 how
 the
 development
 process


used
 to
 look
 right.
 We
 had
 a
 planning


phase,
 a
 building
 phase,
 and
 a
 review


phase.
 And
 we
 had
 all
 of
 these
 touch


points
 of
 alignment
 along
 the
 way.
 And


it
 was
 slow
 enough
 that
 we
 had
 time
 for


conversations
 in
 Slack
 and
 Zoom


meetings,
 comments
 on
 issues
 and
 draft


PR
 so
 you
 could
 discuss
 the
 details
 and


everyone
 could
 give
 their
 two
 cents
 and


get
 advice
 from
 expertise
 across
 your


team
 and
 seniors
 and
 catch
 mistakes
 uh


and
 course
 correct
 if
 things
 were
 going


wrong.
 But
 by
 the
 time
 the
 code
 was


reviewed
 and
 merged,
 the
 whole
 team
 had


seen
 the
 work
 right
 happening
 and
 they


were
 roughly
 on
 the
 same
 page.


But
 that
 implementation
 window
 has
 now


collapsed.
 And
 because
 implementation
 is


no
 longer
 as
 expensive
 and
 timeconuming,


we
 think
 we
 don't
 need
 to
 plan
 as
 much.


So
 most
 of
 those
 early
 touch
 points


actually
 disappear.


And
 we
 know
 the
 review
 time
 for


generated
 code
 is
 actually
 increased.
 So


that
 creates
 more
 points
 of
 alignment,


but
 they're
 actually
 on
 the
 wrong
 side


of
 the
 implementation.


The
 time
 between
 logging
 an
 issue
 and
 an


agent
 opening
 a
 PR
 is
 now
 a
 couple
 of


minutes.
 The
 code
 is
 so
 cheap
 that
 we


don't
 properly
 stop
 to
 think
 before
 we


prompt
 it.


Unhelpfully,
 most
 coding
 agents
 also


have
 this
 local
 plan
 mode
 that
 is


completely
 unshared
 with
 other
 people.


So,
 you're
 not
 even
 checking
 with
 your


team
 on
 whether
 the
 plan
 it
 made
 is
 good


before
 you
 ship
 it,
 if
 you
 even
 read
 it.


And
 so,
 we
 lose
 even
 more
 alignment


points.
 This
 leaves
 the
 weight
 uh
 of
 all


that
 alignment
 um
 to
 sit
 on
 the
 pull


request.
 All
 those
 checkpoints
 now
 come


after
 the
 implementation
 at
 the
 end
 of


the
 process
 when
 it's
 too
 late.
 And
 it's


never
 what
 PRs
 were
 really
 designed
 to


do
 in
 the
 first
 place.
 So,
 they
 perform


poorly
 at
 it.


None
 of
 our
 current
 tools
 give
 teams
 a


shared
 space
 to
 discuss
 plans,
 gather


the
 right
 context,
 and
 work
 with
 agents


as
 a
 collective.


We're
 all
 experiencing
 the
 repercussions


of
 this.
 Going
 fast
 without
 good


alignment
 leads
 to
 wasted
 work.
 So
 this


is
 like
 features
 no
 one
 asked
 for
 and


that
 don't
 actually
 solve
 real
 problems.


And
 receiving
 critical
 feedback
 after


you
 finish
 something
 that
 ends
 up


meaning
 you
 have
 to
 toss
 the
 whole
 thing


out.
 And
 also
 coordination
 depths.
 This


is
 when
 you
 get
 really
 hairy
 merge


conflicts
 because
 agents
 were
 all


touching
 the
 same
 files
 or
 developers


even
 doing
 duplicated
 work
 because
 they


both
 picked
 up
 a
 thing
 and
 tried
 to


finish
 it
 in
 one
 day.
 Um,
 or
 as
 we
 all


know,
 we
 all
 have
 giant
 stacks
 of
 PRs
 to


review
 that
 nobody
 has
 any
 context
 for


and
 don't
 even
 know
 what's
 in
 them.
 So,
</summary>
</details>

### ACE：重塑协作模式，整合开发与沟通

为了解决上述挑战，我们迫切需要能够**聚合规划、上下文收集、决策制定和开发执行**的工具，将它们整合到一个统一的平台上。软件开发所需的关键上下文信息，远不止代码本身，它还包括：**业务背景、财务资源、产品愿景、用户研究洞察**以及**组织的历史经验**。这些信息往往蕴藏在团队成员的头脑中，是 AI 智能体难以独立发现的。因此，亟需一种方式，能够让**人类成员自然而然地、早期地分享这些宝贵的上下文信息，且不增加额外的流程负担**。

GitHub Next 团队正是在此背景下，构建了一个名为 **ACE（Agent Collaboration Environment）** 的研究原型。ACE 并非一个已上线的产品，其界面和功能尚显粗糙，但它代表了对未来协作模式的一种探索。ACE 的设计理念是将**通信（如 Slack）与开发（如 GitHub Copilot）**结合，并运行在一个**云端的沙盒化计算机（microVM）**上。

ACE 的核心是“**会话（Session）**”概念，它本质上是一个**多人聊天室**，并由一个独立的 Git 分支和隔离的云端计算环境支撑。这意味着：

1.  **隔离性与并行性**：在一个会话中进行的更改是隔离的，允许团队成员并行处理不同任务，并能在它们之间**即时切换**。
2.  **上下文共享**：当一名成员希望了解另一位同事的工作时，无需切换分支或处理本地工作目录的复杂性，即可**一键进入其会话**，并查看其完整的**提示历史（Prompting History）**，从而快速获得上下文。
3.  **实时终端与预览**：会话内支持运行终端命令（如 `bun install`、`bundev`），并提供**实时浏览器预览**。这消除了“在我机器上能运行”的问题，所有成员都在同一个云端环境中协作。
4.  **多方参与**：ACE 不仅支持开发者，还欢迎**设计师、产品经理（PM）和客户支持人员**等非开发者成员进入同一对话空间，实时了解功能开发进展。
5.  **向 GitHub PR 的集成**：ACE 支持直接从环境中创建 PR，并能链接回 ACE 会话，实现**向现有工作流程的兼容**。
6.  **协作计划制定**：对于更复杂的特性，ACE 支持智能体生成**可供团队共同编辑的计划**，促进成员在早期就对需求和实现方案达成一致。

<details>
<summary>Original English</summary>

The
 time
 between
 logging
 an
 issue
 and
 an


agent
 opening
 a
 PR
 is
 now
 a
 couple
 of


minutes.
 The
 code
 is
 so
 cheap
 that
 we


don't
 properly
 stop
 to
 think
 before
 we


prompt
 it.


Unhelpfully,
 most
 coding
 agents
 also


have
 this
 local
 plan
 mode
 that
 is


completely
 unshared
 with
 other
 people.


So,
 you're
 not
 even
 checking
 with
 your


team
 on
 whether
 the
 plan
 it
 made
 is
 good


before
 you
 ship
 it,
 if
 you
 even
 read
 it.


And
 so,
 we
 lose
 even
 more
 alignment


points.
 This
 leaves
 the
 weight
 uh
 of
 all


that
 alignment
 um
 to
 sit
 on
 the
 pull


request.
 All
 those
 checkpoints
 now
 come


after
 the
 implementation
 at
 the
 end
 of


the
 process
 when
 it's
 too
 late.
 And
 it's


never
 what
 PRs
 were
 really
 designed
 to


do
 in
 the
 first
 place.
 So,
 they
 perform


poorly
 at
 it.


None
 of
 our
 current
 tools
 give
 teams
 a


shared
 space
 to
 discuss
 plans,
 gather


the
 right
 context,
 and
 work
 with
 agents


as
 a
 collective.


We're
 all
 experiencing
 the
 repercussions


of
 this.
 Going
 fast
 without
 good


alignment
 leads
 to
 wasted
 work.
 So
 this


is
 like
 features
 no
 one
 asked
 for
 and


that
 don't
 actually
 solve
 real
 problems.


And
 receiving
 critical
 feedback
 after


you
 finish
 something
 that
 ends
 up


meaning
 you
 have
 to
 toss
 the
 whole
 thing


out.
 And
 also
 coordination
 depths.
 This


is
 when
 you
 get
 really
 hairy
 merge


conflicts
 because
 agents
 were
 all


touching
 the
 same
 files
 or
 developers


even
 doing
 duplicated
 work
 because
 they


both
 picked
 up
 a
 thing
 and
 tried
 to


finish
 it
 in
 one
 day.
 Um,
 or
 as
 we
 all


know,
 we
 all
 have
 giant
 stacks
 of
 PRs
 to


review
 that
 nobody
 has
 any
 context
 for


and
 don't
 even
 know
 what's
 in
 them.
 So,


how
 do
 we
 solve
 this?
 We
 need
 tools
 that


help
 everyone
 on
 the
 team
 align
 before


the
 agents
 start
 working,
 not
 after.


That
 alignment
 needs
 to
 happen


constantly
 alongside
 the
 implementation.


Planning
 and
 building
 are
 no
 longer


separate
 phases.
 They
 are
 now
 a
 cycle.


The
 tools
 of
 the
 future
 need
 to
 bring


planning,
 context
 gathering,
 and


decision-making
 and
 development


underneath
 one
 roof.


This
 is
 especially
 true
 because
 most
 of


the
 context
 that
 you
 need
 for
 alignment


and
 to
 build
 the
 right
 thing
 is
 not
 in


the
 codebase.
 It's
 in
 people's
 heads.


The
 business
 context
 and
 the
 financial


resources
 determine
 what
 the
 correct


thing
 to
 build
 is.
 The
 political


dynamics
 of
 who's
 in
 charge
 and
 who
 gets


to
 make
 decisions.
 the
 product
 vision


from
 leaders,
 the
 user
 research
 insight


from
 designers,
 and
 the
 organization's


history
 on
 what
 you've
 built
 before.


These
 all
 matter
 immensely
 when
 you're


deciding
 what
 the
 right
 thing
 for
 your


team
 to
 build
 is.
 And
 the
 agents
 can


never
 discover
 this
 context
 on
 their


own.
 You
 need
 a
 way
 to
 get
 humans
 to


share
 it
 early
 and
 naturally
 without


adding
 process
 and
 overhead.


So,
 all
 of
 this
 has
 been
 very
 clear
 to


us
 on
 the
 next
 team.
 Um,
 and
 we've
 been


building
 a
 new
 research
 prototype
 that


explores
 how
 we
 might
 solve
 some
 of


these
 problems.
 It's
 called
 ACE.
 Stands


for
 agent
 collaboration
 environment.
 Uh,


it's
 not
 a
 prime
 time
 product
 yet.
 So,


like
 if
 it
 looks
 pretty
 rough
 around
 the


edges,
 it's
 because
 it
 is.
 Um,
 we're


about
 to
 go
 into
 technical
 preview
 and


we're
 going
 to
 user
 test
 it
 with
 a
 few


thousand
 people.
 Um,
 then
 we're
 going to


learn
 how
 people
 collaborate
 in
 it
 and


iterate
 from
 there.


So,
 here
 we
 are
 in
 ACE.
 It
 probably


looks
 pretty
 familiar.
 We're
 not


reinventing
 any
 more
 wheels
 than
 we
 have


to.
 Uh
 it
 looks
 a
 bit
 like
 Slack,


GitHub,
 Copilot,
 and
 a
 bunch
 of
 cloud


computers
 had
 a
 baby.
 So
 we
 have
 our


sessions
 list
 here
 on
 the
 left.
 And


sessions
 are
 where
 you
 do
 work,
 right?


It's
 a
 multiplayer
 chat.
 It's
 like
 a


Slack
 channel.
 I
 have
 team
 teammates
 in


here,
 and
 I
 can
 talk
 to
 them
 about
 the


work
 we're
 doing.
 But
 I
 also
 have
 my


coding
 agents
 in
 here.


Each
 session
 is
 more
 than
 a
 chat


channel,
 though.
 It
 is
 also
 backed
 by
 a


microVM,
 so
 a
 sandboxed
 computer
 in
 the


cloud
 on
 its
 own
 git
 branch.
 The
 changes


we
 make
 in
 each
 session
 are
 isolated,
 so


we
 can
 work
 on
 parallel
 tasks
 and


instantly
 switch
 between
 them.
 If
 I
 want


to
 tap
 one
 of
 my
 teammates
 on
 the


shoulder
 and
 get
 their
 thoughts
 on
 a


feature
 I'm
 building,
 nobody
 has
 to


stash
 their
 git
 changes
 and
 like
 pull


down
 a
 new
 branch
 or
 like
 wrestle
 with


local
 work
 trees,
 I
 just
 jump
 into
 their


session
 and
 I
 see
 what
 they're
 doing
 in


a
 click.
 And
 this
 includes
 their
 entire


prompting
 history
 with
 the
 agent.
 So
 I


have
 the
 context
 about
 how
 they
 got
 to


the
 current
 outputs.


Just
 like
 a
 local
 machine,
 I
 can
 run


terminal
 commands
 in
 this
 session.
 Here,


I'm
 going
 to
 run
 bun
 install
 and
 bundev


to
 get
 my
 current
 project
 running.
 And


you're
 going
 to
 see
 in
 a
 minute,
 uh,
 my


live
 preview
 in
 the
 browser
 on
 the
 side


is
 going
 to
 pop
 up
 when
 I
 open
 the
 port.


Um,
 the
 demo
 project
 we
 have
 here
 is
 a


calm
 version
 of
 hacken
 news.
 So,
 it
 only


shows
 you
 the
 top
 three
 stories
 from
 the


last
 top
 stories
 from
 the
 last
 three


months,
 which
 is
 a
 bit
 more
 chill
 than


every
 day.
 Um,
 and
 I'm
 going
 to
 ask
 the


agent
 to
 change
 the
 color
 theme
 to


purple
 here.
 And
 you'll
 see
 in
 a
 second


it
 instantly
 appears
 in
 my
 preview,


right?
 It's
 just
 running
 the
 code.
 Uh,


and
 the
 agent
 has
 also
 made
 an
 automatic


commit
 for
 me
 with
 a
 nice
 commit
 message


and
 I
 can
 open
 the
 diffs
 and
 see
 the


diffs.
 All
 the
 kind
 of
 standard
 things


you'd
 expect
 from
 coding
 agents.


So,
 let's
 say
 we
 want
 to
 do
 some
 real


work.
 Uh,
 I
 have
 my
 teammates
 here
 in


this
 session
 with
 me.
 Uh,
 and
 I'm
 going


to
 ask
 Ace
 to
 add
 some
 additional
 color


themes
 to
 my
 app.
 We're
 going
 to
 um
 pick


which
 model
 we
 want
 to
 use
 and
 obviously


it's
 Opus
 4.6.
 And
 then
 Ace
 is
 going
 to


get
 started.
 Um,
 we
 also
 have
 this
 handy


summary
 block
 block
 in
 the
 top
 right


hand
 corner.
 Uh,
 this
 keeps
 me
 up
 to


date
 with
 the
 latest
 changes
 in
 this


session,
 whether
 they're
 from
 me
 or


someone
 else,
 which
 means
 I
 can
 switch


between
 lots
 of
 people's
 sessions
 that


are
 running
 in
 parallel
 and
 always
 stay


oriented
 about
 what's
 happening
 so
 that


you
 don't
 get
 overwhelmed
 with
 the


amount
 of
 noise
 and
 activity.


But
 the
 more
 important
 thing
 is
 I
 want


to
 talk
 to
 my
 teammates,
 right?
 I
 want


to
 discuss
 what
 changes
 we're
 making.
 So


I
 can
 ask
 them
 what
 they
 think
 of
 the


current
 changes.
 they
 can
 spin
 up
 the


dev
 server
 themselves
 because
 remember


we're
 all
 working
 on
 the
 same
 computer


in
 the
 cloud.
 This
 is
 no
 problem.
 We
 can


all
 see
 the
 same
 preview.
 We
 can
 all


write
 terminal
 commands
 and
 see
 the


shared
 outputs.
 No
 one
 is
 going
 to
 say


this
 doesn't
 work
 on
 my
 machine.


So
 my
 teammates
 Nate
 and
 Dan,
 they're


jumping
 in
 here.
 They've
 taken
 some


screenshots.
 They're
 suggesting
 some


alternative
 features,
 asking
 questions.


And
 now
 what
 we're
 about
 to
 see
 is
 that


a
 um
 Nate
 is
 going
 to
 ask
 the
 ACE
 agent


to
 make
 changes
 in
 a
 minute.
 Where's


Nate?
 There's
 Nate.
 So
 he
 said
 ace,


let's
 add
 a
 teal
 theme,
 too.
 Um
 so
 I


actually
 kicked
 off
 this
 session,
 but


Nate
 is
 now
 prompting
 the
 agent.
 So
 this


is
 truly
 multiplayer.
 Both
 of
 us
 are


sharing
 this
 uh
 coding
 session.
 Uh
 the


agent
 can
 also
 read
 our
 whole


conversation.
 That
 is
 all
 input
 to
 the


prompt.
 So
 we
 can
 talk
 about
 things
 up


ahead
 and
 just
 say
 at
 Ace,
 do
 it.


They'll
 go
 do
 it.
 This
 kind
 of


accessible
 Slack-like
 interface
 means


that
 um
 access
 to
 a
 coding
 agent
 is
 um


brings
 everyone
 in
 who's
 creating


software.
 So,
 not
 just
 developers,
 but


designers
 and
 PMs
 and
 customer
 support


people
 can
 all
 be
 in
 the
 same


conversation
 seeing
 what's
 happening
 in


real
 time
 as
 a
 feature
 gets
 built.


Because
 if
 you're
 thinking,
 you
 know,


like
 why
 wouldn't
 we
 just
 use
 Slack
 for


this?
 I
 think
 it's
 because
 Slack
 is


never
 going
 to
 become
 a
 fully
 featured


software
 development
 tool
 unless
 they


sincerely
 pivot
 from
 their
 current


business.
 Um,
 so
 it's
 never
 going
 to


have
 the
 right
 primitives
 and
 I
 really


doubt
 it's
 going
 to
 add
 them.
 You
 know,


diffs
 and
 terminal
 commands
 and
 that


sort
 of
 thing
 is
 not
 Slack's
 business.


Um,
 we
 wanted
 ACE
 because
 it's


explicitly
 designed
 for
 software


development,
 but
 it's
 much
 more


welcoming
 to
 other
 team
 members
 than


your
 terminal.


Anyway,
 we're
 back
 to
 shipping
 our


changes
 here.
 We
 like
 how
 this
 looks,
 so


we're
 going to
 create
 a
 PR
 um
 because


eventually
 all
 this
 code
 does
 have
 to
 go


back
 to
 GitHub,
 right?
 So,
 we
 create


this
 PR
 from
 directly
 inside
 ACE.
 Uh,
 we


give
 it
 a
 minute
 and
 it's
 going
 to
 show


us
 the
 preview
 of
 the
 the
 PR
 and
 then
 we
 can


click
 a
 link
 that
 goes
 to
 it
 over
 here


in
 a
 second.
 Adon's
 gonna
 click.
 There


we
 go.
 So,
 there's
 our
 PR.
 It
 all
 works,


right?
 This
 is
 backwards
 compatible.
 It


has
 a
 link
 back
 to
 the
 ACE
 session


within
 the
 description.
 Like
 people


don't
 all
 have
 to
 be
 in
 ACE
 to
 use
 this.


You
 could
 have
 a
 few
 members
 of
 your


team
 in
 ACE
 and
 the
 rest
 stay
 in


whatever
 else
 they're
 using.


And
 sometimes,
 you
 know,
 you
 still
 need


to
 touch
 code.
 Like
 I
 do
 a
 lot
 of
 front


end
 and
 agents
 are
 [ __ ]
 at
 CSS.
 They


never
 do
 what
 I
 want.
 So,
 we
 can
 of


course
 open
 our
 project
 in
 VS
 Code
 here.


Um,
 and
 we
 have
 real
 time
 multiplayer


editing
 because
 again
 this
 is
 just
 a


microVM
 cloud
 computer.
 Everyone's
 on


the
 same
 computer.
 I
 can
 close
 my
 laptop


on
 this
 and
 work
 can
 continue.
 Um,
 my


session
 doesn't
 die.
 My
 teammates
 can


keep
 prompting
 ACE
 um
 and
 making


progress.
 We
 don't
 have
 a
 mobile


interface
 yet,
 but
 we're
 building
 it.


But
 this
 microVM
 architecture
 means
 that


that
 will
 work
 seamlessly.
 Like
 I
 don't


have
 to
 use
 my
 phone
 to
 somehow
 SSH
 into


a
 terminal
 or
 my
 computer.
 computer


doesn't
 need
 to
 be
 alive
 and
 I
 don't


need
 to
 go
 buy
 a
 Mac
 Mini
 to
 keep
 things


available.
 I
 just
 talk
 to
 my
 always
 on


agent
 in
 the
 cloud.


For
 bigger,
 more
 complex
 features,


you'll
 of
 course
 want
 your
 agent
 to


write
 a
 plan.
 That's
 a
 very
 standard


workflow
 at
 this
 point.
 So
 here
 we're


chatting
 about
 adding
 uh
 variable
 time


frames
 to
 our
 hacker
 news
 comm
 app.
 And


then
 I've
 gone
 ahead
 and
 asked
 Ace
 to


make
 a
 plan,
 which
 it's
 going
 to
 do


quite
 quickly.
 And
 so
 we
 can
 go
 open


that
 plan,
 right?
 And
 here
 we
 all
 are
 in


our
 plan.
 I
 can
 see
 my
 teammates's


cursors.
 We
 can
 collaboratively
 edit
 it


together.
 We
 can
 decide
 if
 we
 like
 this


plan,
 if
 it's
 any
 good
 at
 all,
 if
 it


achieves
 our
 intent.
 Um,
 my
 teammate


Nate
 here
 is
 making
 suggestions
 about


maybe
 using
 a
 drop
 down
 for
 the


interface
 instead
 of
 a
 segmented


control.
 And
 then
 Adan's
 come
 in
 and


updated
 the
 requirements
 so
 the
 agent


knows
 to
 do
 that.
 Uh,
 and
 once
 we're
 all


happy
 with
 the
 details,
 we
 go
 back
 to


the
 chat
 and
 we
 can
 just
 say
 at
 ace
 do


this
 and
 it
 knows
 what
 the
 context
 is.


So
 I'm
 now
 going
 to
 jump
 over
 to
 our


dashboard
 in
 ACE.
 Uh
 a
 lot
 of
 the


planning
 and
 discussion
 that
 would


otherwise
 happen
 in
 Slack
 or
 GitHub
 or


Linear
 is
 now
 happening
 in
 our
 ACE


sessions.
 So
 we
 have
 a
 lot
 of
 access
 to


rich
 context
 on
 what
 work
 is
 underway


and
 can
 helpfully
 summarize
 it
 for
 you.


So,
 here
 it's
 Monday
 morning
 and
 I've


been
 trying
 to
 remember
 what
 I
 left


unfinished
 last
 Friday
 and
 ACE
 is


prompting
 me
 to
 keep
 working
 on
 some


React
 hooks
 I
 was
 making
 as
 part
 of
 a


big
 refactor,
 which
 is
 helpful
 since
 I


have
 very
 crappy
 human
 memory
 after
 a


long
 weekend.
 And
 from
 here,
 I
 can
 start


a
 new
 session
 or
 in
 this
 pick
 backup


section
 in
 one
 click,
 I
 can
 open
 the


session
 to
 keep
 going
 on
 my
 unmmerged


PR.
 I
 can
 also
 see
 a
 list
 of
 my
 recently


completed
 PRs
 and
 issues
 to
 stroke
 my


ego
 and
 make
 me
 feel
 productive.


And
 on
 the
 right
 here,
 we
 have
 a
 team


pulse
 section.
 So,
 this
 summarizes
 what


my
 co-workers
 have
 been
 up
 to
 for
 the


last
 couple
 of
 days.
 I
 can
 see
 Nate
 has


been
 shipping
 a
 lobby
 channel
 and
 David


has
 been
 fixing
 access
 token
 issues.
 Um,


there's
 also
 a
 raw
 feed
 of
 recent
 issues


and
 PRs
 on
 this
 repo,
 but
 I
 personally


find
 the
 summary
 much
 more
 helpful.
 Um,


one
 of
 the
 biggest
 challenges
 of
 agentic


development
 is
 that
 the
 speed
 and
 volume


of
 work
 makes
 it
 really
 hard
 to
 keep
 up


with
 what
 your
 co-workers
 are
 doing.


They're
 now
 shipping
 five
 features
 a
 day


instead
 of
 half
 of
 one.
 This
 dashboard


is
 our
 first
 pass
 at
 trying
 to
 make


agents
 proactive
 in
 bringing
 that
 social


context
 to
 you.
 If
 all
 your


conversations
 around
 the
 code
 are


available
 to
 agents,
 it
 gives
 them


access
 to
 a
 social
 information
 fabric


where
 they
 can
 help
 get
 you
 oriented


every
 morning
 and
 stay
 aligned
 with
 your


team.
 They
 could
 notify
 you
 about


decisions
 being
 made
 or
 pull
 you
 into
 a


conversation
 where
 someone
 is
 about
 to


extend
 a
 feature
 that
 you
 originally


built.


So
 this
 is
 no
 longer
 a
 bunch
 of
 solo


disconnected
 terminal
 instances
 on


individual
 computers.
 This
 becomes
 a


living
 intelligent
 environment
 where


everyone
 shares
 the
 same
 workspace
 and


context.


So
 all
 of
 this
 is
 actually
 about


reclaiming
 time.
 Right?
 Before
 coding


agents
 came
 along,
 none
 of
 us
 had
 enough


time
 and
 energy
 to
 make
 our
 products
 the


way
 we
 wanted
 to.
 I
 guarantee
 everyone


in
 this
 room
 has
 shipped
 software


they're
 not
 proud
 of.
 Maybe
 you
 didn't


have
 enough
 time
 to
 do
 user
 research
 or


consider
 design
 details
 or
 think
 through


the
 implications
 of
 your
 architecture


choices.
 Um,
 not
 because
 you
 didn't
 want


to,
 but
 because
 there
 simply
 wasn't


enough
 time
 because
 implementation
 took


up
 so
 much
 of
 that
 time
 and
 effort.
 But


we've
 been
 gifted
 a
 lot
 of
 that
 time


back.
 We
 have
 an
 opportunity
 to
 not
 just


go
 faster
 and
 build
 a
 giant
 pile
 of
 the


same
 crappy
 software,
 but
 instead
 to


make
 much
 better
 software
 through
 much


more
 rigorous
 critical
 thinking
 and


better
 alignment
 in
 the
 planning
 stage


by
 doing
 more
 exploration,
 more


research,
 and
 thinking
 through
 problems


more
 deeply
 than
 we
 could
 have
 before.


Agents
 allow
 us
 to
 scale
 up
 ourselves


and
 our
 teams
 in
 a
 way
 that
 if
 done


right
 should
 lead
 to
 better
 quality


software.


I
 think
 many
 people
 are
 now
 realizing


that
 in
 a
 world
 of
 fast
 cheap
 software


quality
 becomes
 the
 new
 differentiator.


The
 bar
 is
 being
 set
 much
 higher
 and


craftsmanship
 is
 what
 set
 you
 what
 will


set
 you
 apart
 from
 vibecoded
 slop.
 Um


but
 craft
 still
 costs
 time
 and
 energy.


It's
 not
 free
 and
 in
 order
 to
 buy
 the


time
 and
 energy
 you
 need
 for
 it,
 you


need
 to
 do
 fewer
 things
 better
 which


requires
 lots
 of
 strong
 alignment.


There
 are
 also
 more
 distractions
 than


ever.
 It's
 very
 easy
 to
 prompt
 your
 way


to
 the
 wrong
 thing
 or
 to
 add
 lots
 of


unnecessarily
 unhelpful
 features
 to
 your


product.
 I
 think
 the
 dream
 for
 me
 is


that
 we
 end
 up
 with
 tools,
 whether
 it's


ACE
 or
 others,
 that
 create
 environments


where
 teams
 can
 think
 rigorously


together
 about
 hard
 problems.
 Our


agentic
 tools
 should
 help
 us
 do
 higher


quality
 work,
 get
 aligned
 faster,
 and


build
 a
 few
 exceptional
 things
 rather


than
 a
 thousand
 crappy
 ones.


Thank
 you
 very
 much
 for
 listening.
 Um,


uh,
 if
 you
 do
 want
 early
 access
 to
 ACE,


we
 should
 have
 it
 out
 within
 a
 couple


months
 at
 the
 very
 latest.
 Uh,
 this
 QR


code
 will
 take
 you
 to
 a
 form
 where
 you


put
 in
 your
 GitHub
 username
 and
 then


we'll
 give
 you
 early
 access
 as
 soon
 as


it
 comes
 out.
 Um,
 you
 can
 read
 more


about
 the
 GitHub
 Next
 team
 and
 their


research
 on
 github
 next.com
 and
 all
 my


work
 in
 writing
 is
 on
 maggieappleton.com


and
 I'll
 have
 the
 slides
 and
 notes
 for


this
 up
 there
 in
 a
 day
 or
 two.


Thanks,
</summary>
</details>

### 软件开发的时间价值：从“快”到“好”的回归

AI 智能体极大地**解放了开发者的时间**。过去，受限于实现成本和时间投入，许多产品未能达到我们期望的质量标准。开发者可能因为时间不足，而无法进行充分的用户研究、深入设计细节，或仔细考量架构选择的长期影响。如今，智能体将大量原本用于编码的时间和精力返还给我们。这提供了一个**前所未有的机会**：我们不再仅仅是追求“更快”地堆砌软件，而是可以转向**更高质量的软件**。

这种转变要求我们进行**更严格的批判性思维**，并在**规划阶段实现更好的对齐**。这意味着需要投入更多时间进行**探索、研究，并更深入地思考问题**。ACE 等工具的目标，是帮助团队在协作环境中**共同思考复杂问题**，从而提升工作质量，更快地达成一致。当软件开发速度和成本普遍降低时，**质量**将成为真正的**差异化竞争优势**。**精湛的工艺（Craftsmanship）**将是区分优秀产品与“有感知编码”（vibecoded slop）的关键。然而，精湛的工艺本身并非免费，它依然需要时间与精力。为了获得并投入这些宝贵的时间和精力，我们需要学会“**少做，但做得更好**”，这反过来又**依赖于强大的团队对齐**。

在这个充斥着各种干扰和诱惑的时代，很容易被引导去开发错误的方向，或为产品添加大量不必要的、低价值的功能。ACE 的愿景，以及它所代表的未来工具，是创造一个环境，让**团队能够协同思考、深入钻研难题**。智能体工具应帮助我们实现**更高质量的工作**，**更快地实现团队对齐**，并最终**打造少数真正卓越的产品，而非大量平庸之作**。

<details>
<summary>Original English</summary>

So
 all
 of
 this
 is
 actually
 about


reclaiming
 time.
 Right?
 Before
 coding


agents
 came
 along,
 none
 of
 us
 had
 enough


time
 and
 energy
 to
 make
 our
 products
 the


way
 we
 wanted
 to.
 I
 guarantee
 everyone


in
 this
 room
 has
 shipped
 software


they're
 not
 proud
 of.
 Maybe
 you
 didn't


have
 enough
 time
 to
 do
 user
 research
 or


consider
 design
 details
 or
 think
 through


the
 implications
 of
 your
 architecture


choices.
 Um,
 not
 because
 you
 didn't
 want


to,
 but
 because
 there
 simply
 wasn't


enough
 time
 because
 implementation
 took


up
 so
 much
 of
 that
 time
 and
 effort.
 But


we've
 been
 gifted
 a
 lot
 of
 that
 time


back.
 We
 have
 an
 opportunity
 to
 not
 just


go
 faster
 and
 build
 a
 giant
 pile
 of
 the


same
 crappy
 software,
 but
 instead
 to


make
 much
 better
 software
 through
 much


more
 rigorous
 critical
 thinking
 and


better
 alignment
 in
 the
 planning
 stage


by
 doing
 more
 exploration,
 more


research,
 and
 thinking
 through
 problems


more
 deeply
 than
 we
 could
 have
 before.


Agents
 allow
 us
 to
 scale
 up
 ourselves


and
 our
 teams
 in
 a
 way
 that
 if
 done


right
 should
 lead
 to
 better
 quality


software.


I
 think
 many
 people
 are
 now
 realizing


that
 in
 a
 world
 of
 fast
 cheap
 software


quality
 becomes
 the
 new
 differentiator.


The
 bar
 is
 being
 set
 much
 higher
 and


craftsmanship
 is
 what
 set
 you
 what
 will


set
 you
 apart
 from
 vibecoded
 slop.
 Um


but
 craft
 still
 costs
 time
 and
 energy.


It's
 not
 free
 and
 in
 order
 to
 buy
 the


time
 and
 energy
 you
 need
 for
 it,
 you


need
 to
 do
 fewer
 things
 better
 which


requires
 lots
 of
 strong
 alignment.


There
 are
 also
 more
 distractions
 than


ever.
 It's
 very
 easy
 to
 prompt
 your
 way


to
 the
 wrong
 thing
 or
 to
 add
 lots
 of


unnecessarily
 unhelpful
 features
 to
 your


product.
 I
 think
 the
 dream
 for
 me
 is


that
 we
 end
 up
 with
 tools,
 whether
 it's


ACE
 or
 others,
 that
 create
 environments


where
 teams
 can
 think
 rigorously


together
 about
 hard
 problems.
 Our


agentic
 tools
 should
 help
 us
 do
 higher


quality
 work,
 get
 aligned
 faster,
 and


build
 a
 few
 exceptional
 things
 rather


than
 a
 thousand
 crappy
 ones.


Thank
 you
 very
 much
 for
 listening.
 Um,


uh,
 if
 you
 do
 want
 early
 access
 to
 ACE,


we
 should
 have
 it
 out
 within
 a
 couple


months
 at
 the
 very
 latest.
 Uh,
 this
 QR


code
 will
 take
 you
 to
 a
 form
 where
 you


put
 in
 your
 GitHub
 username
 and
 then


we'll
 give
 you
 early
 access
 as
 soon
 as


it
 comes
 out.
 Um,
 you
 can
 read
 more


about
 the
 GitHub
 Next
 team
 and
 their


research
 on
 github
 next.com
 and
 all
 my


work
 in
 writing
 is
 on
 maggieappleton.com


and
 I'll
 have
 the
 slides
 and
 notes
 for


this
 up
 there
 in
 a
 day
 or
 two.


Thanks,
</summary>
</details>