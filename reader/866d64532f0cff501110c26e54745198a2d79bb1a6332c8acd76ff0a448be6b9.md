---
author: How I AI
date: '2026-05-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=efVfydaUIrM
speaker: How I AI
tags:
  - agentic-workflow
  - developer-tools
  - automation
  - ai-agents
title: Anthropic's Claude Code 重大更新：Agentic 工作流新纪元
summary: 本次更新概述了 Anthropic 在 'Code with Claude' 活动上发布的五项重要功能，旨在增强开发者使用 Claude Code 和 Claude API 的能力。主要包括：Claude Code 应用中的 'Routines' 功能，实现任务的自动化调度；Claude API 中的 'Outcomes'，允许代理根据预设的 Rubric 自我评估和迭代；'Multi-agent Framework'，支持构建包含多达25个代理的协作团队；'Dreams'，一种用于整合和管理代理长期记忆的机制；以及整体使用限额的提升，使开发者能更频繁、更深入地使用这些工具。这些更新共同指向 Anthropic 致力于成为领先的 Agentic 平台。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
products_models:
  - Claude Code
  - Claude API
  - Claude managed agents
media_books: []
status: evergreen
---
### Anthropic“Code with Claude”活动发布五大Agentic新能力

本次“Code with Claude”开发者活动聚焦于增强开发者在代码编写和 Agentic 系统构建方面的能力。Anthropic 发布了多项重要更新，旨在提供更强大、更灵活的工具集，涵盖任务自动化、代理智能迭代、多代理协作以及记忆管理等方面，并提升了整体使用额度，以支持更广泛和深入的 AI 应用开发。

<details>
<summary>Original English</summary>

Welcome
 back
 to
 How
 I
 AI.
 I'm
 Claire
 Vo,


product
 leader
 and
 AI
 obsessive
 here
 on


a
 mission
 to
 help
 you
 build
 better
 with


these
 new
 tools.
 Today
 I
 attended
 Code


with
 Claude,
 Anthropic's
 first
 developer


event,
 and
 they
 announced
 some
 things
 in


Claude
 Code
 and
 Claude
 managed
 agents
 I


think
 you
 want
 to
 know
 about.
 I'm
 going


to
 walk
 you
 through
 five
 things
 that


launched
 today,
 how
 they
 work,
 what
 they


are,
 and
 what
 I
 might
 build
 with
 them.


We're
 going
 to
 keep
 it
 under
 10
 minutes


and
 this
 is
 going
 to
 be
 a
 quick
 preview


of
 what
 you'll
 see
 in
 your
 new
 Claude


Code
 and
 Claude
 API
 products
 experience.

</details>

### Claude Code 应用更新：引入“Routines”实现任务自动化调度

Claude Code 应用迎来重大更新，其中最受期待的是 **“Routines”** 功能。这项新能力允许用户设置事件或动作的自动触发，能够基于预设的**计划（cron）**、**HTTP 请求**或 **GitHub Webhook** 来执行。例如，用户可以配置一个每周自动生成邮件通讯的 Routine，根据 `docs/change-log.md` 文件内容，撰写一份面向客户的、突出新功能的周报。该功能支持在云端或本地机器上运行，并能集成已有的 Connectors（如 Slack、GitHub），极大地提升了开发工作流的自动化水平。

<details>
<summary>Original English</summary>

Okay,
 the
 first
 thing
 that
 shipped
 at


Code
 with
 Claude
 that
 I
 think
 you
 want


to
 know
 about
 are
 some
 updates
 to
 the


Claude
 Code
 app.
 And
 one
 of
 the
 updates


that
 I
 know
 we've
 all
 been
 waiting
 for


is
 routines,
 the
 ability
 to
 trigger


events
 or
 actions
 on
 a
 schedule.
 We
 love


it.
 You
 know
 I
 love
 Open
 Claude
 and
 what


I
 love
 about
 Open
 Claude
 are
 the
 crons.


And
 so
 now
 Claude
 Code
 has
 that
 built
 in


right
 here
 in
 the
 app.
 All
 you
 have
 to


do
 is
 click
 new
 routine.
 You
 can
 either


run
 it
 locally
 or
 remote.
 I'm
 going
 to


run
 it


locally.
 And
 I'm
 going
 to
 say
 weekly


newsletter.
 This
 is
 something
 that
 I


haven't
 been
 doing.
 I'm
 sorry
 if
 you're


a
 Chat
 Period
 customer.
 I
 know
 I
 haven't


done
 my
 newsletter.
 And
 I'm
 going
 to


say,
 "Look
 at
 our
 change
 log
 and
 draft
 a


newsletter
 for
 us
 to
 send
 weekly."
 And


then
 I'm
 going
 to
 go
 in
 here
 and
 just


say,
 "We
 have
 a
 change
 log.md
 in
 the


docs
 folder.


Review
 it
 every
 Monday
 and
 write
 a


customer-facing
 newsletter


based
 on
 the
 best
 customer-facing


features
 we
 shipped.


Don't
 talk
 about
 behind-the-scenes


things
 like
 tech
 debt
 or
 security
 unless


they
 really
 impress
 customers."
 Okay,
 so


I'm
 going
 to
 do
 that.
 I'm
 going
 to
 run


it
 daily
 or
 no,
 sorry,
 I'm
 going
 to
 run


it
 weekly


on
 Mondays
 at
 6:00
 a.m.


And
 I
 think
 that's
 all
 I
 need
 to
 do.


Oh,
 I'm
 going
 to
 select
 my
 folder


um
 where
 my
 project
 is
 and
 then
 I'm


going
 to
 create
 create.
 And
 now


Claude
 Code
 will
 run
 my
 newsletter
 draft


cron
 every
 week
 and
 then
 I
 can
 come
 back


in
 here,
 grab
 the
 HTML.
 If
 I
 were
 being


really
 fancy,
 I
 would
 hook
 this
 up
 to
 my


newsletter
 platform,
 I
 would
 hook
 it
 up


to
 my
 Slack
 and
 ping
 us,
 but
 again,
 this


is
 very
 useful
 to
 me.
 This
 is
 something


that
 I
 used
 to
 kick
 off
 manually
 in


Claude
 Code
 every
 Monday,
 and
 now
 I
 can


do
 that
 here
 in
 Claude
 Code
 on
 a


schedule.


So,
 how
 does
 that
 work?
 There
 are
 three


trigger
 types.
 You
 can
 trigger
 them
 on
 a


cron,
 which
 is
 a
 schedule,


um
 HTTP
 or
 a
 GitHub
 web
 hook.
 So,
 you


can
 do
 sort
 of
 a
 normal
 web
 hook
 or
 a


GitHub
 web
 hook.
 You
 can
 trigger
 these


three
 ways.


Scheduled,
 like
 I
 just
 did,
 off
 of
 a


GitHub
 action
 or
 a
 general
 web
 hook.
 So,


you
 can
 hook
 it
 up
 to
 other
 systems
 to


kick
 off
 a
 routine.


All
 the
 stuff
 in
 connectors
 come
 along.


So,
 I
 have
 Slack
 connected,
 I
 have


GitHub
 connected,
 so
 you
 can
 use
 those


things
 as
 part
 of
 your
 routine.
 And
 it


can
 run
 in
 the
 cloud
 or
 it
 can
 run
 on


your
 laptop,
 like
 I
 showed.
 And
 this
 is


an
 example
 of
 a
 use
 case
 where
 you
 could


say,
 "Weekly,
 I
 want
 you
 to
 check
 every


PRD
 modified
 this
 week
 and
 check
 if
 it


matches
 our
 rubric
 and
 post
 a
 summary
 to


the
 team
 channel."
 So,
 that's
 item
 one.

</details>

### Claude API 增强：引入“Outcomes”实现代理智能迭代

Anthropic 在 Claude API 中引入了 **“Outcomes”** 功能，作为对现有代理模型（如 Codex 的“goal”）的类似增强。该功能允许用户定义代理完成任务的“完成标准”——一个 **Rubric**（以 Markdown 文件形式上传或内嵌）。代理会根据此 Rubric 进行自我评估和迭代，最多可进行 20 次尝试，直到达到预期的“完成”状态。这一机制特别适用于需要严格遵循规范的场景，如生成一份“ship-ready”的 PRD（产品需求文档），代理能够反复迭代，确保其输出符合所有优先级和技术能力要求。

<details>
<summary>Original English</summary>

The
 second
 one
 is
 in
 Claude
 manage


agents
 in
 the
 API.
 If
 you
 haven't
 paid


attention,
 opening
 I
 released
 something


in
 Codex
 called
 goal.
 You
 can
 do
 {slash}


goal
 in
 beta
 in
 Codex
 and
 it'll


basically
 bang
 its
 head
 against
 the


problem,
 do
 what's
 called
 a
 rough
 loop,


against
 the
 problem
 until
 it
 actually


hits
 the
 goal.
 Anthropic
 released


something
 very
 similar
 in
 the
 Claude
 API


called
 outcomes.
 You
 define
 what
 done


looks
 like
 for
 an
 agent,
 it
 can


self-grade
 and
 iterate
 until
 it
 gets


there.
 There's
 a
 couple
 interesting


things
 you
 need
 to
 know
 about
 how


outcomes
 are
 defined.
 They
 all
 anchor
 on


what's
 called
 a
 rubric.
 So,
 there's
 a


markdown
 file
 that's
 uploaded
 either


through
 the
 files
 API
 or
 in
 line,
 and


it's
 going
 to
 tell
 your
 agent
 what


success
 looks
 like.
 Then,
 there
 is
 a


grader,
 and
 it
 can
 do
 up
 to
 20


iterations
 on
 the
 task
 to
 get
 to
 the


outcome
 that
 you're
 going
 for.
 I
 want
 to


walk
 through
 this
 one
 in
 a
 very
 specific


example
 to
 make
 this
 just
 a
 little
 bit


more
 concrete
 for
 folks.
 So,
 so
 imagine


that
 I
 want
 you
 to
 ship
 a
 ship-ready


PRD,
 and
 I
 don't
 know
 if
 you
 can
 relate


to
 this.
 Often,
 you
 go
 through
 feedback


cycles.
 You
 have
 to
 check
 it
 against


priorities.
 You
 have
 to
 check
 it
 against


technical
 capabilities.
 Now,
 using
 a


Claude
 managed
 agent,
 you
 could
 in


theory
 write
 a
 rubric,
 which
 is
 what


does
 a
 good
 ship-ready
 um
 PRD
 look
 like,


and
 then
 the
 agent
 can
 just
 take
 your


PRD
 or
 your
 idea
 and
 iterate
 over
 and


over
 and
 over
 again
 until
 it's
 fixed.
 Of


course,
 you
 could
 expect


Of
 course,
 you
 could
 expose
 this
 to
 your


customers
 in
 an
 app
 like
 I
 might
 do
 for


Chat
 PRD.
 But
 again,
 this
 idea
 of


outcome
 is
 define
 a
 rubric,


give
 the
 agent
 the
 task,
 let
 it
 bang
 its


head
 against
 that
 at
 least
 20
 times
 till


it
 gets
 it
 right.
 I
 think
 this
 really


interesting
 model
 for
 agenda
 products


and
 something
 I
 suspect
 many
 of
 us
 will


use.

</details>

### Claude API 增强：支持强大的“Multi-agent Framework”

Claude API 现在支持一个强大的 **“Multi-agent Framework”**，允许开发者通过 API 定义一个包含最多 25 个代理的协作团队。该框架具有明确的**层级结构**，包括一个**编排者（Orchestrator）**和多个**委托者（Delegates）**。每个代理都可以拥有自己独特的**工具集**。这种能力使得构建复杂的 Agentic 应用成为可能，例如，可以创建一个 PRD 编排者，并配备策略代理（模拟 CPO 声音）、评论代理（找出 PRD 中的漏洞）和评审代理（可能访问 GitHub 以优化技术实现）等子代理。这种团队协作模式为 Agentic 产品提供了前所未有的灵活性。

<details>
<summary>Original English</summary>

The
 second
 thing
 I
 really
 love
 is
 a


multi-agent
 framework
 supported
 in


Claude
 managed
 agent.
 So,
 now
 you
 can


through
 the
 API
 explicitly
 define
 a


multi-agent
 team
 that's
 going
 to
 work


against
 the
 same
 container,
 the
 same


file
 system,
 up
 to
 25,
 which
 is
 kind
 of


amazing.


You
 can
 have
 a
 a
 orchestrator
 and
 then


delegates,
 and
 so
 there's
 explicit


hierarchy,
 and
 each
 agent
 can
 have
 its


own
 tool
 set.
 I
 think
 this
 is
 really


cool
 cuz
 now
 you're
 able
 to
 define
 not


just
 individual
 agents,
 but
 teams
 of


agents
 programmatically
 through
 the
 API.


And
 so,
 the
 example
 I
 would
 give
 for


something
 like
 Chat
 PRD
 is
 you
 could


have
 a
 PRD
 orchestrator.
 This
 is
 sort
 of


like
 the
 master
 agent
 that
 is
 intended


to
 define
 and
 drive
 the
 work
 across
 the


team.
 And
 then
 you
 could
 have
 three


pieces
 or
 three
 sub
 agents.


A
 strategy
 agent
 that
 reflects
 the
 CPO


voice,
 the
 critic
 agent
 that's
 sort
 of


like
 supposed
 to
 poke
 at
 the
 holes
 in


the
 PRD.
 I
 like
 being
 the
 critic
 agent.


And
 then
 end
 review
 that
 can
 maybe
 have


access
 to
 something
 like
 GitHub
 to


optimize
 the
 technical
 implementation
 of


the
 PRD.
 And
 so,
 you
 can
 define
 this
 as


you
 see
 over
 here
 in
 the
 API.
 You
 define


an
 agent
 in
 the
 API,
 you
 give
 it
 um


a
 orchestrator
 level
 set
 of
 tools,
 and


then
 you
 can
 define
 the
 sub
 agents
 um
 in


the
 in
 the
 API
 with
 their
 own
 set
 of


tools.
 And
 then
 you
 could
 expose
 that,


as
 you
 can
 see
 here
 on
 the
 right,


as


three
 agents
 all
 working
 in
 parallel


against
 the
 same
 problem
 owned
 by
 the


coordinator
 or
 orchestrator
 level.


Again,
 I
 think
 this
 is
 an
 interesting


enhancement
 on
 the
 primitives
 of
 agents


that
 people
 are
 going
 to
 be
 using
 quite


a
 bit.

</details>

### “Dreams”功能：Agentic 记忆管理新原语

Anthropic 推出了名为 **“Dreams”** 的新功能，专注于 Agentic 系统的**记忆管理**。它提供了一个原语（primitive），可以作用于一系列 Agent session，用于整合和提炼这些会话中的关键信息，并将其以 Markdown 文件形式写入磁盘，供代理未来参考。该功能比喻为人类的“做梦”，即回顾白天的经历并选择性地固化重要记忆。虽然目前处于研究预览阶段，但“Dreams”预示着 Agentic 平台将集成更智能、更主动的记忆生成和管理机制，并可能进一步发展出“遗忘”能力。

<details>
<summary>Original English</summary>

Okay,
 the
 next
 one
 I
 really
 like.
 It
 is


Dreams.
 So,
 this
 is
 all
 about
 agent


memory.
 Just
 to
 make
 it
 simple
 for


folks,
 memory
 is
 basically
 the
 idea
 of


writing
 markdown
 files
 to
 the
 file


system
 your
 agent
 uses
 that
 helps
 it
 do


a
 better
 job
 the
 next
 time.
 It's
 not


that
 fancy.
 Often
 those
 files
 have
 a


date
 on
 them,
 but
 you
 don't
 really
 have


to
 overthink
 it.
 But,
 creating
 those


memories
 is
 a
 little
 hard.
 And
 often
 a


lot
 of
 the
 harnesses
 right
 now
 write


memory
 on
 a
 hook.
 They
 write
 that
 on
 an


event.
 And
 so,
 what
 they
 do
 is
 like
 when


you
 close
 a
 session,
 it
 writes
 memory
 or


when
 something
 happens,
 it
 writes


memory.
 Or
 like
 with
 Open
 Claw,
 you
 can


explicitly
 tell
 it
 to
 write
 memory.


But,
 what
 I
 like
 about
 dreams,
 which
 is


a
 very
 funny
 brand
 for
 an
 agentic
 memory


product,
 but
 we'll
 allow
 it,
 is
 it's
 a


primitive
 to
 call
 against
 a
 list
 of


agent
 sessions.
 So,
 let's
 say
 you've


done
 50
 things
 with
 your
 agent,
 it's
 an


explicit
 call
 to
 take
 those
 50
 sessions,


review
 them,
 and
 then
 come
 up
 with


important
 memories
 to
 write
 to
 disk.
 And


as
 I'm
 saying
 this,
 I
 guess
 this
 is
 what


we
 do
 when
 we
 dream.
 We
 go
 through
 our


day,


we
 review
 it
 silently,
 and
 then
 we


decide
 what
 to
 commit
 to
 memory.
 I
 don't


know.
 I
 don't
 know
 if
 this
 is
 the


perfect
 metaphor,
 but
 it's
 the
 one
 we


got,
 and
 it
 looks
 great
 on
 a


on
 a
 branded
 website.
 This
 one's
 in


research
 preview,
 so
 I
 don't
 think


everybody
 has
 access
 to
 this
 through


API.
 I
 certainly
 don't
 have
 access
 to


it,
 so
 I'm
 looking
 forward
 to
 touching


it.
 But,
 why
 I
 think
 this
 one's


important
 to
 know
 is
 it
 just
 gives
 you
 a


frame
 of
 reference
 for
 how
 Anthropic
 and


these
 labs
 are
 thinking
 about
 the


primitives
 again
 of
 agents
 and
 agent


memory,
 and
 you
 can
 predict
 that
 some


framework
 like
 this
 is
 going
 to
 be


integrated
 into
 agentic
 platforms
 or


agentic
 products,
 where
 on
 some
 action


or
 some
 regular
 cadence,


you're
 going
 to
 review
 past
 sessions,


and
 you're
 going
 to
 explicitly
 write
 the


right
 things
 to
 disk
 so
 they
 can
 be


referred
 to
 moving
 forward.
 Side
 note,
 I


think
 we
 think
 a
 lot
 about
 agent
 memory,


but
 not
 a
 lot
 about
 agent
 forget


getting,
 so
 I'm
 looking
 forward
 to
 like


the
 purge
 version
 of
 this,
 which
 is


dreams
 that
 tell
 you
 what
 to
 forget.
 I


don't
 know
 if
 that's
 like
 trauma
 erasure


or
 whatever,
 but
 I
 think
 there's


something
 interesting
 here.

</details>

### 使用限制提升：扩大 Claude Code 与 API 的使用额度

此次更新还包括对 **Claude Code 和 Claude API 的使用限制进行显著提升**。具体而言：
*   **Claude Code** 的 Pro、Max、Team 和企业版 5 小时使用限制翻倍。
*   Pro 和 Max 计划的**峰值时段限制**将被取消。
*   API 中 **Opus 模型**的速率限制也将提高。
这些调整意味着开发者将能够更频繁、更深入地使用这些工具，从而加速开发进程和 AI 应用的探索。

<details>
<summary>Original English</summary>

Okay,
 and


then
 number
 five,
 the
 only
 announcement


people
 really
 care
 about,
 which
 is
 usage


limits
 are
 up.
 So,
 starting
 today,


Claude
 Code's
 5-hour
 limits
 are
 now


doubled
 across
 Pro,
 Max,
 Team,
 and


seat-based
 enterprise
 platforms.
 Peak


hours
 are
 going
 away
 for
 Pro
 and
 Max


plans,
 and
 the
 rate
 limits
 for
 Opus


models
 in
 the
 API
 are
 going
 up.
 So,
 we


can
 all
 use
 these
 products
 more.

</details>

### 总结与未来展望

总而言之，Anthropic 在“Code with Claude”活动上推出的一系列更新，包括自动化的“Routines”、智能迭代的“Outcomes”、强大的“Multi-agent Framework”以及 Agentic 记忆管理的原语“Dreams”，并结合使用限额的提升，共同构建了一个更完善、更易于使用的 Agentic 开发平台。这些实用且前瞻性的功能表明 Anthropic 致力于成为开发者构建下一代 AI 应用的首选平台。

<details>
<summary>Original English</summary>

Again,
 what
 do
 we
 see
 today
 at
 Code
 with


Claude?
 Lots
 of
 other
 stuff.
 They
 might


put
 data
 centers
 in
 space.


There
 was
 a
 partnership
 with
 SpaceX.
 All


sorts
 of
 fun
 things
 are
 happening,
 but


the
 things
 that
 I
 think
 you
 can
 use


immediately


routines
 for
 scheduling
 tasks
 in
 Claude


code,
 so
 you
 can
 get
 things
 done
 either


on
 a
 webhook
 or
 on
 a
 schedule.
 Outcomes,


which
 is
 the
 ability
 to
 set
 a
 rubric
 and


task
 and
 have
 an
 agent
 work
 against
 that


task
 at
 least
 20
 times
 to
 nail
 the


rubric.


Multi-agent
 orchestration,
 which
 allows


you
 in
 the
 API
 to
 define
 an
 orchestrator


role
 and
 sub-agents,
 I
 think
 up
 to
 25,


to
 get
 work
 done
 from
 different
 points


of
 view
 with
 different
 tools.
 Dreams,


which
 are
 a
 way
 to
 consolidate
 agent


memory
 over
 sessions,
 over
 time,
 and
 do


that
 on
 demand.
 And
 then
 finally,
 we
 can


all
 use


more
 Claude
 code,
 which
 makes
 everyone


happy.
 I
 do
 not
 know
 if
 these
 limit


increases
 apply
 to
 Claude
 design.
 I


suspect
 they
 do
 not,
 but
 I
 hope
 they


will.
 I
 think
 they
 launched
 a
 lot
 of


stuff
 that
 we
 can
 use
 practically
 right


now
 in
 Claude
 code
 and
 gave
 me
 some
 good


ideas
 for
 what
 the
 future
 of
 agentic


products
 look
 like.
 None
 of
 this
 was


mind-blowing,
 but
 I
 think
 it's
 all


really
 practical,
 and
 it
 just
 gives
 you


the
 idea
 that
 Anthropic
 is
 trying
 to
 be


the
 agent
 platform
 of
 choice
 for


builders.
 I
 look
 forward
 to
 seeing
 what


you
 build
 with
 it,
 and
 I'm
 going
 to
 go


play
 with
 the
 API.


Bye.


Thanks
 so
 much
 for
 watching.
 [music]
 If


you
 enjoyed
 this
 show,
 please
 like
 and


subscribe
 here
 on
 YouTube
 or
 even


better,
 leave
 us
 a
 comment
 with
 your


thoughts.


You
 can
 also
 find
 this
 podcast
 on
 Apple


Podcasts,
 Spotify,
 or
 your
 [music]


favorite
 podcast
 app.
 Please
 consider


leaving
 us
 a
 rating
 and
 review,
 which


will
 help
 others
 find
 the
 show.


You
 can
 see
 all
 our
 episodes
 and
 learn


more
 about
 the
 show
 at
 howiai.com.


See
 you
 [music]
 next
 time.
</details>