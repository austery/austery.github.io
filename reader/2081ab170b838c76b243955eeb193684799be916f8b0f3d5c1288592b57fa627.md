---
author: AI Engineer
date: '2026-10-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wP3P89YB9fA
speaker: AI Engineer
tags:
  - ai-code-review
  - code-verification
  - ci-cd-automation
  - automated-repair
  - developer-tools
title: Sonar 团队展示代码变更验证智能体 Guitar：结合上下文自动诊断与修复 PR
summary: Sonar 开发者内容团队的 Taylor Luttrell 与 Kilian Carlson 演示了代码变更验证智能体 Guitar（Git Guardian）。针对 AI 生成代码带来的审查瓶颈与生产事故问题，Guitar 结合 PR 差异、业务规则与 CI 日志实现意图分析，能够自主诊断 CI 失败、推送修复提交并自动合并，同时支持跨仓库与跨 PR 验证。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Sonar
products_models:
  - SonarQube
  - Git Guardian
  - Guitar
media_books: []
status: evergreen
---
### 工作坊开场与环境准备

**>>**: [音乐]
<details><summary>Original English</summary>
[music]
</details>

**>>**: 我叫 Taylor Luttrell，和我一起的是 Kilian Carlson。我们一起在 SonarQube 的开发商 Sonar 制作开发者内容。但今天，我们特别激动——甚至可以说是迫不及待——带领大家上手 Git Guardian，让你们能够在 AI 生成的代码中发现并关键性地修复问题，赶在这些问题真正出现之前。

在深入动手演示之前，请大家看向这个房间两侧的任意一块屏幕，我们为大家准备了一个二维码以及下方的链接。访问后，你可以设置一个免费的——需要强调是免费的——为期 14 天的 Git Guardian 专业版试用。

如果你想一步一步紧跟本次工作坊的每一步实操，这会非常重要，你需要有 Git Guardian。所以如果你愿意的话，我们给大家一分钟时间来完成设置。

与此同时，趁着大家配置的当口，我想在现场举手统计一下：你们当中有谁已经在 CI 流程里使用 AI 代码审查工具了？

好的，看来有不少人已经用上了，这正是我们乐意看到的。无论你目前用过还是没用过，我们都希望大家能从今天的环节中有所收获。我们再给大家一分钟时间登录 Git Guardian 并开启试用。

接下来我还有另一个二维码给大家——我保证这次演讲并不全都是二维码——但这个确实非常重要，因为它会带你进入我们专门创建的 GitHub 工作坊代码仓库，以便大家能上手 Guitar。

这个项目将帮助大家演练 Guitar 一些非常棒的功能，待会儿坐在这里的 Kilian 先生将带大家一步步操作。但在大家配置的同时，我想指出：我们在本次环节中所做的一切都将在浏览器中进行。所以，你不需要安装任何本地工具，也不需要配置任何本地环境。

你只需要一个 GitHub 账号以及访问 Guitar 的权限，就能一步步跟上进度。在大家登录和准备的时候，先交代几项事务性的注意事项。在本次工作坊中，我们将引导大家完成几件事：首先是将 Guitar 安装为 GitHub App。为此你需要有 GitHub 的访问权限。

然后，关键是在几种不同的拉取请求（PR）场景下运用 Guitar。我们在这个演示中为大家准备了三个场景，用来展示 Guitar 的验证如何超越普通的单纯代码审查。

不用担心，如果你技术背景不是特别强，这个过程是非常对初学者友好的。我们将从 Guitar 开箱即用的验证功能起步，放慢节奏，然后逐渐深入到一些更高级的特性。实际上我们还会创建一个项目专属的配置，用来教会 Guitar 了解你项目的规范约定。最后，我们将以 CI 失败诊断来收尾，大家将亲眼看到自动修复直接应用在你的 PR 上。

因此，如果你跟着 Guitar 以及这个代码仓库一起操作，那么在本次工作坊结束时，你不仅能安装好 Guitar，完成三个经过验证的 PR，还能对诸多内容建立起实用的理解，包括但不限于验证指令、代码仓库规则以及 CI 失败分析。

我希望现在大家都已经配置好了 Guitar，并登录了 GitHub。先不要急着 fork 代码仓库，因为 Kilian 马上会引导大家完成针对我们配置的具体步骤。
<details><summary>Original English</summary>
>> My
 name
 is
 Taylor
 Luttrell
 and
 I'm


joined
 here
 by
 Kilian
 Carlson.


Together
 we
 make
 developer
 content
 at


Sonar,
 the
 maker
 of
 SonarQube.
 But


today,
 in
 particular,
 we
 are
 jazzed,


dare
 I
 say,


to
 get
 you
 all
 up
 and
 running
 with
 Git


Guardian
 so
 that
 you
 can
 both
 find
 and


critically
 fix
 issues


in
 your
 AI-generated
 code


before
 they
 ever
 emerge.


Now,
 before
 we
 dive
 into
 the
 hands-on


demo
 itself,


if
 you
 would
 please
 direct
 your


attention
 to
 one
 of
 the
 screens
 on


either
 side
 of
 this
 room,


we've
 provided
 for
 you
 a
 QR
 code
 and


also
 a
 link
 there
 below


which,
 once
 followed,
 you
 can
 use
 to
 set


up
 a
 free,
 I
 should
 note
 free,
 14-day


pro
 trial
 for
 Git
 Guardian.


So,
 this
 is
 going
 to
 be
 really
 important


if
 you
 want
 to
 follow
 along
 step-by-step


and
 play-by-play
 with
 this
 workshop,


you're
 going
 to
 need
 Git
 Guardian.
 So,


we'll
 give
 you
 all
 a
 minute
 to
 get
 that


set
 up,
 should
 you
 like.


And
 just
 in
 the
 meantime,
 while
 you
 do


configure
 that,
 if
 I
 could
 get
 a
 quick


show
 of
 hands
 from
 the
 audience,


who
 amongst
 you
 is
 already
 using
 an
 AI


code
 reviewer
 as
 part
 of
 your
 CI


process?


Okay,
 so
 that's
 a
 fair
 number
 of
 you
 all


and
 that
 portion
 what
 we
 like
 to
 see.


And
 whether
 you
 are
 or
 you're
 not,
 we


hope
 that
 you
 will
 be
 able
 to
 derive


some
 utility
 from
 today's
 session.
 We'll


give
 you
 all
 just
 another
 minute
 as
 you


sign
 in
 to
 Git
 Guardian
 and
 set
 up
 that


trial.


Next
 I
 have
 for
 you


another
 QR
 code
 and
 I
 promise
 this


presentation
 is
 not
 exclusively
 QR


codes,
 but
 this
 one
 is
 in
 fact
 very


important
 as
 this
 will
 take
 you
 to
 the


dedicated
 GitHub
 workshop
 repo
 that
 we


have
 created
 so
 that
 you
 can
 get
 up
 and


running
 with
 Guitar.


This
 project
 is
 going
 to
 help
 exercise


some
 of
 Guitar's
 incredible
 capabilities


and
 Mr.
 Killian
 here
 is
 going
 to
 walk


you
 all
 through
 that
 in
 a
 minute,
 but
 as


you
 get
 set
 up,
 I
 do
 want
 to
 note
 that


everything
 we
 do
 in
 this
 session
 is


going
 to
 occur
 in
 the
 browser.
 So,


you're
 not
 going
 to
 need
 to
 set
 up
 any


local
 tools,
 install
 any
 local


environments.


All
 you
 need
 is
 a
 GitHub
 account
 and


access
 to
 Guitar
 to
 follow
 along
 play
 by


play.
 Uh
 just
 a
 couple
 of
 housekeeping


notes
 as
 y'all
 are
 getting
 signed
 in
 and


set
 up.
 Uh
 in
 this
 workshop,
 we're
 going


to
 guide
 you
 through
 a
 few
 different


things,
 namely
 installing
 Guitar
 as
 a


GitHub
 app.


Going
 to
 need
 access
 to
 GitHub
 for
 that.


And
 then
 critically
 utilizing
 Guitar


across
 a
 few
 different
 pull
 request


scenarios.
 We
 have
 three
 prepared
 for


you
 in
 this
 demonstration
 that
 are
 going


to
 demonstrate
 how
 verification
 with


Guitar
 goes
 beyond
 simply
 code
 review.


And
 don't
 worry,
 this
 is
 very


beginner-friendly
 if
 you're
 not


especially
 technical.
 We're
 going
 to


start
 slow
 with
 Guitar's
 out-of-the-box


verification
 and
 then
 we're
 slowly
 going


to
 ramp
 and
 build
 into
 some
 of
 the
 more


advanced
 features.
 We're
 actually
 going


to
 create
 a
 project-specific


configuration
 that
 teaches
 Guitar
 your


project's
 conventions.
 And
 then
 lastly,


we're
 going
 to
 round
 things
 out
 with
 a


CI


uh
 failure
 diagnosis
 and
 you're
 going
 to


watch
 some
 automated
 fixes
 occur


directly
 on
 your
 PRs.


So,
 if
 you
 follow
 along
 with
 Guitar
 and


with
 this
 repository,
 then
 by
 the
 end
 of


this
 workshop,
 you're
 going
 to
 walk
 away


with
 Guitar
 installed,


three
 verified
 pull
 requests,
 as
 well
 as


a
 practical
 understanding
 of


a
 number
 of
 things
 such
 as,
 but
 not


limited
 to,
 verification
 instructions,


rules
 for
 your
 repositories,
 as
 well
 as


CI
 failure
 analysis.


I
 hope
 by
 now
 you're
 all
 set
 up
 with


guitar.
 You've
 logged
 into
 GitHub.
 Go


ahead
 and
 refrain
 from
 forking
 the


repository
 right
 now,
 as
 Killian's
 going


to
 walk
 you
 through
 the
 steps
 uh


specific
 for
 our
 configuration.
</details>

### AI 编码时代的审查瓶颈与 Guitar 的定位

**>>**: 我想先从一个场景开始谈起，我相信很多人——如果不是大多数人的话——对这个场景都再熟悉不过，同时也感到无比沮丧：我们都知道 AI 编码智能体在编写代码方面极其高效，无论是速度还是数量。

但当这些智能体赋能团队以更快的速度编写更多代码时，我们应该停下来问问自己：到底由谁或什么工具来真正验证我们这些智能体交付的代码？随之而来的问题是：我们的智能体交付的代码，不仅是否安全、可维护、可靠，而且在实际业务层面上是否正确，而不仅仅是在功能或技术层面上正确？

我们知道，随着智能体生成的代码越来越多，生成速度快到任何人实际上都来不及审查，几个严重的问题开始浮现。

首先是显而易见的审查瓶颈。团队的人数是固定的，但面对 AI 智能体提交的变更数量却在激增。他们被排山倒海般需要审查的代码淹没，结果导致审查队列越积越长，合并请求搁置无人问津，审查本质上变成了一件没有人愿意做、也没有时间和资源去应对的苦差事。

第二点是，我们注意到生产环境故障的数量在上升。随着事故发生率随着变更速度的提升而同步扩大，因为编码智能体并不总是尊重大家花费大量心血设计的项目架构，也不了解团队、公司或组织制定的编码标准或任何既定指导方针。它们对这些一无所知，缺乏相应的背景上下文。

随着这些问题可能抹杀编码智能体带来的效率提升，应对之策的速度必须超过人类能做到的极限，而且在审查质量上也必须优于人类审查，这样才能跟上这些智能体引入变更的速度。因此，我们为大家带来的就是 Guitar——一款代码变更验证智能体。它在许多方面脱颖而出、超越其他工具：

首先，它具有高信噪比，能有效减少误报数量，从而提高修复率并降低 token 开销。

它能诊断 CI 失败。这一点非常独特。它能把真正的代码破坏与偶发性波动（flaky noise）或基础设施噪音区分开来。更关键的是，它还能相应地修复这些问题。

而且它能够自主进行修复。这样你就可以尽可能快速、自由地推进工作。实际上，你可以选择你的自动化程度，也可以选择你的参与程度，控制权完全在你们手中。

Guitar 还会持续迭代，直到你的所有变更都通过 CI，以确保你能完全放心地发布智能体生成的代码。最后，它通过若干个专属的分析看板，为审查过程和 CI 提供极高的透明度，让你可以持续提升代码交付的速度、质量和成效。

总而言之，简单总结一下：Git Tarr（Guitar）是专为平台和工程团队设计的，他们需要在智能体级别的吞吐量和速度下充满信心地交付代码。它与 SonarQube 相辅相成，具备对每个代码变更上下文和意图的理解能力。

Git Tarr 利用广泛而多样的上下文来源来实现这一点：从 PR 的 diff、详情、评论等内容提出经过深思熟虑的修复建议；从 CI 日志中提取信息——也就是我个人最讨厌去人工排查的那些日志；以及从项目专属的指令中获取信息。

还包括你自己可以在仓库中编写的规则配置等等。今天在环节中我们会深入探讨其中的一部分。

我想对所有担心噪音的人说明一下，正如我刚才提到的，Git Tarr 是专门针对“信号”进行调优的。因为我们明白，每一次误报都是一次 token 的浪费，也是一次可能带来意外变更风险的修复尝试。Git Tarr 并没有在已经很复杂的审查流程中增加更多噪音和沉重的决策负担，而是承担起了推动变更通过的工作，在此过程中验证并修复所有问题，免去了大家亲力亲为的麻烦。

从宏观上看，当 PR 被打开时，Git Tarr 的审查引擎就会被触发，并调用我们刚才提到的广泛上下文来生成发现项以及修复方案。这些内容会作为可交互的指导建议直接发布到你的拉取请求中，你可以通过评论与它互动，或者在开启自动配置的情况下，由它自动修复并合并。

为了演示这一切，接下来我将把时间交给 Kilian，他将带大家体验本次工作坊的实操环节。如果大家有任何问题或卡壳了，随时举手或叫我。我会在现场走动，如果大家需要任何帮助，我很乐意协助。谢谢大家。
<details><summary>Original English</summary>
>> I
 want
 to
 start
 instead
 with
 a
 scenario


that
 I'm
 sure
 many,


if
 not
 most
 of
 us
 are
 intimately
 and


also
 frustratingly


familiar
 with,
 which
 is


we
 all
 know
 that
 AI
 coding
 agents
 are


wildly
 effective
 at
 writing
 code,
 both


at
 speed
 and
 also
 at
 volume,


but
 while
 these
 agents
 are
 supercharging


our
 teams
 to
 write
 more
 code
 and
 much


more
 quickly,
 we
 ought
 to
 pause
 and
 ask


ourselves
 who
 or
 what
 is
 actually


verifying
 the
 code
 that
 our
 agents
 ship.


And
 whether
 consequently


the
 code
 that
 our
 agents
 ship
 is
 not


only
 secure,
 of
 course,
 and
 maintainable


and
 reliable,
 but
 also
 whether
 it
 is


practically
 and
 not
 just
 functionally
 or


technically
 correct.


As
 we
 know,
 agents,


as
 they're
 generating
 more
 code
 and


they're
 doing
 so
 faster
 than
 anyone
 can


realistically
 inspect,
 a
 couple
 serious


issues
 have
 begun
 to
 arise.


The
 first
 is
 an
 obvious
 review


bottleneck.


We
 have
 teams
 with
 a
 fixed
 number
 of


members,
 but
 which
 are
 now
 facing


an
 increasing
 number
 of
 changes
 uh
 via


their
 AI
 agents.
 They're
 being
 inundated


with
 code
 to
 review,
 and
 as
 a
 result,


queues
 are
 growing,
 merges
 are
 sitting


waiting
 and
 unattended
 to,
 and
 reviewing


is
 essentially
 becoming


uh
 a
 job,
 a
 chore,
 if
 you
 will,
 that


nobody
 wants
 to
 handle
 and
 simply


doesn't
 have
 the
 time
 or
 the
 resources


to
 tackle.


Number
 two
 is
 we're
 noticing
 an
 increase


in
 the
 number
 of
 production
 incidents.


As
 incidents
 scale
 with
 the
 rate
 of


change
 given
 that
 coding
 agents


do
 not
 always
 respect
 the
 project


architectures
 that
 you
 spend
 so
 much


time
 devising
 your
 team
 or
 your
 company


or
 organizations
 coding
 standards
 or
 any


of
 the
 guidelines
 that
 you've


established.
 They're
 unaware
 of
 those


things.
 They
 lack
 the
 proper
 context.


And
 with
 these
 issues
 threatening
 to


undo
 the
 very
 progress
 that
 coding


agents
 promise,
 the
 answer
 has
 to
 be


faster


than


um


anything
 that
 humans
 can
 perform
 and


also
 better
 than
 human
 review


in
 order
 to
 keep
 up
 with
 the
 rate
 of


changes
 that
 are
 being
 introduced
 by


these
 agents.
 And
 so,
 what
 we
 have
 for


you
 is


Guitar,
 which
 is
 the


code
 change
 verification
 agent.
 And
 it


stands
 out
 apart
 from
 and
 above
 the
 rest


in
 a
 number
 of
 ways,
 namely


it
 functions
 with
 a
 high
 signal
 to
 noise


ratio


and
 effectively
 minimizing
 the
 false


positives,
 the
 number
 of
 false
 positives


in
 order
 to
 improve
 the
 fix
 rate
 and


reduce
 token
 expenses
 as
 well.


It
 diagnoses
 CI
 failures.
 This
 is
 really


unique.


And
 it
 separates
 real
 breakages
 from


flaky
 noise
 or
 infrastructure
 noise.
 And


it
 also,
 crucially,
 fixes
 these
 issues


accordingly.


And
 it
 fixes
 autonomously


also.


So,
 that
 you
 can
 move
 forward
 as
 quickly


and
 as
 freely
 as
 possible.
 Effectively,


you
 choose
 your
 level
 of
 automation
 and


you
 also
 choose
 your
 level
 of


involvement.
 We're
 giving
 you
 the
 reins.


Guitar
 also
 iterates
 until
 all
 of
 your


changes
 pass
 CI
 to
 be
 absolutely
 certain


that
 you
 can
 ship
 the
 code
 that
 your


agents
 are
 generating.
 And
 lastly,
 it


provides
 a
 high
 degree
 of
 transparency


into
 the
 review
 process
 and
 your
 CI


through
 a
 number
 of
 dedicated
 analytics


dashboards
 so
 that
 you
 can
 continuously


improve
 the
 speed,
 quality,
 and


effectiveness
 of
 your
 code
 delivery.
 So,


in
 essence,
 and
 and
 just
 to
 recap,
 Git


Tarr
 is
 designed
 for
 platform
 and


engineering
 teams


uh
 who
 need
 to
 ship
 code
 with
 confidence


at
 agentic
 volume
 and
 also
 agentic


velocity.


And
 it
 complements
 SonarQube
 with
 an


understanding
 of
 each
 code
 changes


context
 and
 intent.


And
 Git
 Tarr
 leverages
 a
 variety
 and
 a
 a


wide
 body
 of
 context
 sources
 to


accomplish
 this.


Suggesting
 educated
 and
 informed
 fixes


from
 such
 things
 as
 PR
 diffs


and
 details
 and
 comments
 and
 whatnot
 um


from
 the
 CI
 uh
 CI
 logs
 as
 well,
 the
 the


very
 logs
 that
 I
 personally
 hate
 to
 to


have
 to
 sift
 through.


Um
 from
 project-specific
 instructions
 as


well.
 Um


configurations
 that
 you
 can
 write


yourself
 in
 the
 repository
 rules
 and
 and


much
 much
 more.
 And
 we're
 going
 to
 dive


into
 some
 of
 those
 during
 the
 session
 uh


today.


And
 I
 should
 note
 that
 for
 anybody
 who


is
 worried
 about
 noise,
 as
 I
 mentioned


uh
 Git
 Tarr
 is
 tuned
 for
 signal


uh
 because
 we
 understand
 that
 every


false
 positive
 is
 a
 token
 spent
 and
 a


fix
 attempt
 that
 risks
 an


unintended
 change.
 Um
 and
 rather
 than


adding
 more
 noise
 and
 burdensome


decisions
 to
 an
 already
 complicated


review
 process,
 Git
 Tarr
 does
 do
 the


work
 of
 getting
 the
 change
 through
 and


in
 the
 process
 verifying
 and
 fixing


everything
 so
 that
 you
 don't
 have
 to


yourself.


At
 a
 high
 level


Git
 Tarr's
 review
 engine
 is
 triggered


when
 a
 PR
 is
 opened
 and
 it
 calls
 upon


that
 wide
 body
 of
 context
 that
 we
 just


spoke
 about
 to
 produce
 findings
 and
 also


fixes
 posted
 directly
 to
 your
 pull


requests
 as
 actionable
 guidance
 that
 you


can
 interact
 with


with
 comments


or
 if
 enabled,
 automatically
 fixed
 and


merged.
 And
 to
 demonstrate
 just
 that,


I'm
 going
 to
 pass
 things
 off
 to
 Kilian,


who's
 going
 to
 walk
 you
 through
 the


hands-on
 component
 of
 this
 workshop.


Should
 you
 have
 any
 questions,
 if
 you


get
 blocked,


feel
 free
 to
 raise
 your
 hand
 or
 call
 on


me.
 I'm
 going
 to
 be
 walking
 around
 the


room
 and
 I'm
 happy
 to
 assist
 should
 you


all
 need
 any
 help.
 Thank
 you.
</details>

### 实操演示准备：Fork 仓库与开启工作流

**>>**: 好的，非常感谢 Taylor。大家好，我是 Kilian，Sonar 的开发者内容工程师。我们现在进入本次工作坊的动手操作部分。在开始之前，正如 Taylor 刚才提到的，第一件事是我们得确保已经安装好了 Guitar 应用。所以如果你还没装，请访问 app.guitar.ai，在那里登录并开始 GitHub 安装流程。第二件事就是我手头这个工作坊仓库，地址是 github.com/sonarsamples/aie-new-york-workshop-guitar，你也可以在 repos 标签页下找到它。

我们要做的第一步就是直接 fork 这个仓库。确保 owner（所有者）选择的是你安装了 Guitar 应用的组织。仓库名字可以随便起，你可以保留原名，也可以叫 test run 之类的，只要适合你就行。但最重要的一点是：这里的“Copy the main branch only”（仅复制 main 分支）必须取消勾选。我们准备了多个分支来对应我将演示的不同练习，如果你只复制了 main 分支，就拿不到这些不同的练习分支了。

所以我们直接点击“Create fork”。

完成之后，下一步我们要做的是进入 Actions。默认情况下，GitHub 会在 fork 的仓库中禁用 workflows。为了设置我们接下来要做的一些操作，比如自动合并和批准，你需要启用它。

最后一点，如果你想确认 Guitar 是否能够读取这个 fork，可以进入 Guitar 的仪表板，进入 Settings（设置），进入 Configurations and Repositories（配置与仓库），你应该就能看到你的仓库出现在那里了。

好了，我们直接进入练习。我这里有一个叫 Box Office 的项目，它是一个假想的小型音乐会场馆票务 API 示例项目。
<details><summary>Original English</summary>
>> Cool.
 Thank
 you
 very
 much,
 Taylor.
 Um


hey
 everybody,
 I
 am
 Kilian.
 I
 am
 a


developer
 content
 engineer
 at
 Sonar.
 And


um
 we're
 going
 to
 hop
 into
 the
 hands-on


section
 of
 this
 workshop.
 And
 before
 we


do
 that,
 uh
 the
 first
 thing,
 like
 Taylor


mentioned
 earlier,
 is
 we're
 going
 to


want
 to
 have
 the
 Guitar
 app
 already


installed.
 So,
 if
 you
 haven't
 done
 that


yet,
 please
 go
 to
 app.guitar.ai


and
 sign
 in
 from
 there
 and
 then
 start


the
 GitHub
 install.
 And
 the
 second
 thing


is
 right
 here,
 I
 have
 the
 workshop
 repo.


It's
 at


github.com/sonarsamples/aie-new-york-workshop-guitar,


but
 you
 can
 find
 it
 under
 the
 repos
 tab.


And


the
 first
 thing
 that
 we're
 what
 going
 to


want
 to
 do


is
 just
 go
 ahead
 and
 fork
 the
 repo.


And
 make
 sure
 that
 the
 owner
 is
 the


organization
 that
 you've
 installed
 the


Guitar
 app
 to.


And
 you
 can
 name
 it
 anything.
 You
 can


keep
 the
 name.
 You
 can
 name,
 you
 know,


test
 run,
 whatever
 works
 for
 you.
 But


the
 most
 important
 thing
 is
 that
 this


right
 here,
 copy
 the
 main
 branch
 only
 is


unchecked.
 There
 are
 multiple
 branches


for
 different
 exercises
 I'm
 going
 to


walk
 through,
 and
 if
 you
 only
 copy
 over


the
 main
 branch,
 you're
 not
 going
 to
 get


those
 different
 exercises.


So,


we're
 going
 to
 go
 ahead
 and
 click
 create


fork.


And
 once
 that's
 done,
 the
 next
 thing


that
 we're
 going
 to
 want
 to
 do
 is
 hop


into
 actions.


Right,
 by
 default,


GitHub
 disables
 workflows
 from
 forks.


And
 in
 order
 to
 set
 up
 some
 of
 the


things
 that
 we're
 going
 to
 do,
 like


automated
 merging
 and
 approvals,
 you're


going
 to
 want
 to
 enable
 that.


And
 then
 the
 last
 thing
 is
 that
 if
 you


want
 to
 make
 sure
 that
 Guitar
 is
 able
 to


read
 this
 fork,
 you
 can
 go
 into
 the


Guitar
 dashboard.


Um


go
 to
 settings.


Go
 to
 configurations
 and
 repositories,


and
 you
 should
 see
 your
 repo
 pop
 up


there.


But
 okay,
 just
 to
 hop
 into
 this


exercise.
 I
 have
 here
 Box
 Office,
 which


is
 a
 fake
 sample
 ticketing
 API
 for
 a


small
 concert
 venue.
</details>

**>>**: [哧笑]
<details><summary>Original English</summary>
>> [snorts]
</details>

### 练习一：开箱即用的业务逻辑漏洞检测与自动修复

**>>**: 这是一个非常简单的 Python 项目。我们这里有 `orders.py`，用户可以在里面购票，或者退票退款。我们还有这个 `checkin.py`，它的作用就是处理假想场景下的逻辑：扫二维码让某人进场看演唱会。这是一个很基础的示例应用，但这里有一套测试套件，覆盖了所有现有的功能。每次 PR 被打开时，测试都会运行。

所以我们现在要做的，实际上是为里面的三个分支分别打开拉取请求（PR）。之所以这么做，是因为 Guitar 运行可能需要几分钟时间，为了避免按顺序依次等待每次审查，我们先一口气把它们都打开，然后再一步步看。

有一点需要注意：确保将 base repository 设置为你的 fork。设置好 base repository 为你创建的 fork。我刚才不小心跳回了上游的基础仓库，不过没错，就在这里。我现在打开新的 pull request。哎呀，我刚才一直勾着。
<details><summary>Original English</summary>
>> And
 it's
 it's
 a
 pretty
 simple
 Python


project.
 We
 have
 orders.py
 here,
 where


somebody
 is
 able
 to
 purchase
 a
 ticket


or
 cancel
 it
 and
 get
 refunded.


We
 also
 um
 have
 this
 uh
 checkin.py,
 and


what
 this
 does
 it
 just
 handles
 the
 logic


for
 somebody
 to
 hypothetically
 be
 able


to
 scan
 a
 QR
 code
 and
 get
 someone
 into
 a


concert.
 And
 this
 is
 a
 pretty
 basic
 uh


example
 application,
 but
 there
 is
 a
 test


suite
 here
 um
 that
 cover
 all
 of
 the


existing
 uh
 functionality.
 And
 every


time
 a
 PR
 is
 opened,


uh
 the
 test
 will
 run.


And
 so,
 what
 we're
 going
 to
 do
 right
 now


is
 actually
 open
 pull
 requests
 for
 each


of
 the
 three
 branches
 that
 are
 in
 there.


And
 the
 reason
 for
 that
 is
 because


Guitar
 can
 take
 a
 few
 minutes
 to
 run,


and
 instead
 of
 having
 to
 wait
 for
 each


review
 to
 happen
 sequentially,
 we're


going
 to
 open
 them
 all
 up
 and
 then
 go


through
 them
 step-by-step.


One
 thing
 to
 note
 is
 make
 sure
 that
 you


set
 your
 base
 repository
 to
 um


what
 you
 are
 trying
 to
 do.


Uh
 set
 your
 set
 your
 base
 repository
 to


the
 fork
 that
 you
 have
 made.


So,
 I
 accidentally
 hopped
 back
 to
 the


base
 repository,
 but
 yep,
 right
 here.


So,
 I'm
 going
 to
 open
 new
 pull
 request.


Oops,
 I
 kept
 on
 checking
 it.
</details>

**>>**: [哧笑]
<details><summary>Original English</summary>
>> [snorts]
</details>

**>>**: 好的，所以把它指向你这边的分支，然后依次点击 stage 1、stage 2、stage 3。

好，点击 Create pull request 创建第一个。接着设置第二个，选 stage 2，创建 pull request。然后再打开第三个。再次确认这是针对你的 fork 打开的，而不是针对上游仓库。

好的，现在这三个应该都在运行了。在我们等待的同时，Guitar 应该正在运行它的审查。那我们先来看第一个 PR。

这只是 Guitar 开箱即用的审查能力。我们什么都还没做，也还没做任何配置。这只是它在纯查看 PR 时给出的建议。这次变更所做的是：我们增加了一个功能，允许用户购票后转赠给朋友。假设我买了两张票，我发了一张给我朋友，按理说我们两个人应该都能去看演唱会。

在这里我加入了一些很基础的校验逻辑，比如确保“票未找到”；如果你没有有效的邮箱地址，或者这是一张作废的票，系统就不会允许你转赠这些票。还有针对这些逻辑的一些测试。

这个 PR 的测试是通过的，workflow 显示绿色，CI 也是绿色的。在我们等待审查结果出来的同时，我想指出的一点是：Guitar 在读取这段代码时，它的分析方式与更传统的静态分析工具或其他工具有所不同。静态分析（比如 SonarQube）极其重要，它能捕获像 SQL 注入这样的安全问题，它能追踪跨越 20 个不同文件和函数，在 SQL 注入进入数据库之前识别出来。

但它做不到的是推断意图。通过查看你的描述、标题，将你现有的代码库与你正在添加的新特性进行对比，它无法推断出：“嘿，这里试图创建的业务逻辑根本说不通。”这就是为什么我们需要在彼此之上叠加这两层。它们覆盖不同的能力范围，两者是相辅相成的，共同促成一个经过完整验证的应用。随着代码量和交付速度的不断扩大，我们必须确保代码得到全面的验证。否则，故障和中断几乎是必然会发生的。

现在回到主讨论区，我们看到 Guitar 已经添加了一个发现项。每当 Guitar 发现问题时，它都会在发现问题的代码行添加一条评论，同时还会提交一份包含所有发现项、问题描述和建议修复方案的代码审查，并在顶层提供一份清晰的概要。

如果我们看这里的描述，它写着：“买家在转赠票之后仍可退款并使票作废”。也就是说，在这个 PR 中，当你买了一张票并把它送给其他人后，如果你去取消原订单，你朋友手里的票也会被取消。这是一个没被考虑到的边缘情况，甚至连现有的测试都没能捕获这一点。现有测试只测了“如果你持有一张作废的票，系统不允许你转赠”，但没有反过来测试这种情况。

而且它还在此处明确指出，问题出在最初的订单文件 `orders.py` 中。因此，如果你只是一个查看 diff 的审查人员，在新增的代码里你未必能看出有什么问题。你必须深入了解应用现有的退订逻辑是如何运作的，才能明白哪里被破坏了。

随着我们进行越来越多的智能体编程，这类问题只会成倍增加。应用的受影响面变得越来越复杂，按照我们现在的编码速度，要想掌握每一个函数的底层逻辑几乎是不可能的。正因如此，像 Guitar 这样的审查工具是绝对必需的，因为它会将你所有的功能与现有功能进行比对，即便问题在 PR diff 中并不直观。

太棒了，Guitar 已经提交了审查意见。现在我们该做什么呢？非常简单：你可以直接点击这里的“Apply fix”（应用修复），或者直接评论输入 `guitar fix`。发送这条评论。

Guitar 接下来要做的是向该 PR 推送一个新的提交（commit）。它会盲目地（自动化地）对新提交继续迭代并重新验证。因此，如果工作流中出现任何副作用，Guitar 会继续处理、继续迭代，每个 PR 不会产生额外费用，直到最后完全变绿通过。

现在 Guitar 正在处理那个额外的修复。它最终要做的事情就是在 `orders.py` 文件中进行修复，并为此添加额外的校验。只需要花几分钟时间，它就把诊断故障、重新推送、修复并在每次提交时进行验证的整套流程完全自动化了。

对于“绝不能发布未经验证的代码”这一点，我真的非常坚信。这是绝对关键的，我们必须结合上下文、结合验证，兼顾确定性分析与对当前实现内容的逻辑理解，来对每一个 PR 进行全面验证。

在等待修复生效期间，它会更新这里的提交。我们将在“Files changed”（文件改动）的 diff 中看到它出现。它会分析并确保 workflow 变绿，然后应该就可以合并了。
<details><summary>Original English</summary>
>> Yep,
 so
 you're
 going
 to
 set
 that
 to
 your


um


run
 right
 here,
 and
 then
 click


sequentially
 stage
 one,
 stage
 two,
 stage


three.


So,
 yep,
 create
 pull
 request
 here.


Going
 to
 set
 up
 another
 one.


Pick
 stage
 two.


Create
 pull
 request.


And
 then
 open
 up
 the
 third
 one.


Again,
 make
 sure
 that
 this
 is
 opening


against
 your
 fork
 and
 not
 the
 upstream


repository.


All
 right,
 so
 all
 three
 should
 be


running.
 Guitar
 should
 be
 running
 its


review


um
 while
 we
 wait.
 And
 so,
 let's
 hop
 into


the
 first
 PR
 right
 here.


Um


this
 is
 just
 going
 to
 be
 Guitar's
 out
 of


the
 box
 review.
 We
 haven't
 done


anything,
 we
 haven't
 configured


anything.
 This
 is
 just
 when
 it
 looks
 at


a
 PR,
 what
 it
 suggests.
 And
 what
 this


change
 does
 is


we
 are
 adding
 the
 functionality
 for


someone
 to
 order
 a
 ticket,
 and
 then


transfer
 it
 to
 a
 friend.
 So,
 if
 I
 buy


two
 tickets,
 and
 I
 send
 one
 to
 my


friend,
 we
 should
 both
 be
 able
 to
 go
 to


a
 concert
 hypothetically.


Now,
 I
 have
 included
 in
 some
 pretty


basic
 validation
 here
 that
 just
 makes


sure
 like,
 "Hey,
 the
 ticket's
 not


found."
 If
 you
 don't
 have
 a
 valid
 email


address
 or
 it's
 a
 voided
 ticket,
 it's


not
 going
 to
 let
 you
 transfer
 those


tickets.
 And
 uh
 some
 tests
 for
 that
 as


well.


And
 the
 tests
 for
 this
 uh
 PR
 pass.
 The


workflow
 is
 green.
 The
 CI
 is
 green.


Um


and
 one
 thing
 that
 I
 want
 to
 point
 out


here
 as
 well
 while
 we
 wait
 for
 the


review
 to
 land
 is
 that
 while
 Guitar
 is


is
 reading
 this,
 it's
 analyzing
 in
 a


different
 way
 than
 more
 traditional


static
 analysis
 tools
 or
 other
 tools


might
 be
 doing.
 Where
 static
 analysis


like
 SonarQube
 is
 incredibly
 important


and
 it
 catches
 security
 issues
 like
 SQL


injections
 to
 where,
 you
 know,
 traveling


through
 20
 different
 files
 and


functions,
 it's
 able
 to
 identify
 um
 you


know,
 SQL
 injections
 before
 they
 land
 in


your
 database.


What
 it
 can't
 do
 is
 infer
 intent,
 right?


By
 looking
 at
 your
 descriptions,
 your


titles,
 at
 your
 existing
 code
 base


compared
 to
 the
 features
 that
 you're


adding,
 it
 cannot
 infer
 that,
 "Hey,
 the


business
 logic
 that
 is
 being
 attempted


uh
 to
 create
 here


um
 doesn't
 add
 up
 in
 the
 way
 that
 it


should."
 That
 why
 we
 need
 both
 layers


on
 top
 of
 each
 other.
 They
 cover


different
 capabilities
 and
 both
 of
 them


are
 complementary


towards
 having
 a
 fully
 verified


application.
 We
 need
 to
 be
 making
 sure


that
 our
 code
 is
 completely
 verified
 as


it
 scales
 in
 volume
 and
 speed.


Otherwise,
 um
 outages
 and
 and
 breaks
 are


almost
 guaranteed.


So,
 um
 I'm
 going
 to
 hop
 back
 into


the
 main
 conversations
 here
 and
 we
 see


that
 Guitar
 has
 added
 a
 finding.
 So,


anytime
 Guitar
 finds
 an
 issue,
 it'll
 add


a
 comment


um
 at
 the
 line
 that
 it
 finds
 an
 issue


and
 it
 also
 posts
 a
 code
 review
 that
 has


all
 of
 its
 findings,
 as
 well
 as


descriptions
 and
 suggested
 fixes,
 and


provides
 a
 nice
 summary
 at
 a
 high
 level.


If
 we
 read
 this
 here,
 it
 says
 buyer
 can


refund
 and
 void
 a
 ticket
 after
 giving
 it


away.
 So,
 when
 adding
 this
 PR,


right?
 When
 you
 buy
 a
 ticket
 and
 then


send
 it
 to
 someone
 else,
 if
 you
 go
 ahead


and
 cancel
 your
 original
 order,


it
 gets
 canceled
 for
 your
 friend.
 Right?


This
 is
 an
 edge
 case
 that
 wasn't


accounted
 for,
 and
 there
 wasn't
 even
 a


test
 that
 almost
 caught
 this.
 There
 was


a
 test
 that
 said,
 if
 you
 have
 a
 voided


ticket,
 it
 won't
 let
 you
 send
 it,
 but


not
 the
 reverse.


Um
 and
 it
 also
 identifies,
 right
 here,


that
 the
 issue
 is
 in
 the
 original


ordering
 file,
 orders.py.
 So,


the
 the
 if
 you
 were
 just
 a
 reviewer


looking
 at
 the
 diff,


you
 wouldn't
 necessarily
 see
 in
 the
 code


that
 you're
 adding
 that
 there's
 anything


wrong.
 You
 would
 have
 to
 have
 working


knowledge
 of
 how
 cancellations
 already


work
 in
 your
 application
 in
 order
 to


understand
 what's
 being
 broken.


Now,
 this
 issue
 only
 multiplies


as
 as
 we
 do
 more
 and
 more
 agentic


coding.
 The
 surface
 area
 of
 applications


gets
 more
 and
 more
 complex,


um
 and
 in
 order
 to
 maintain
 an


understanding
 of
 how
 every
 last
 function


works
 is
 almost
 impossible
 at
 the
 rate


at
 which
 we're
 coding.
 That's
 why


reviewers
 like
 Guitar
 are
 absolutely


necessary
 because
 it
 compares
 all
 of


your
 features
 against
 existing


functionality
 even
 when
 it's
 not
 readily


apparent
 in
 the
 PR
 diff.


And
 so,
 awesome.
 Guitar
 has
 posted
 its


review.
 Now,
 what
 do
 we
 do?
 It's
 very


simple.
 You
 can
 either
 click
 this
 apply


fix
 right
 here,
 or
 you
 can
 just
 comment


Guitar
 fix,
 right?


Comment
 that.


What
 Guitar
 is
 then
 going
 to
 do
 is
 add
 a


new
 commit
 to
 the
 PR.
 It
 will
 continue


to
 iterate
 and
 re-verify
 the
 new
 commit


blindly.
 So,
 if
 any
 side
 effects
 in
 the


workflows
 happen
 to
 occur,
 Guitar
 will


keep
 working,
 will
 keep
 iterating
 at
 no


extra
 cost
 per
 PR
 to
 make
 sure
 that
 it


gets
 fully
 green
 by
 the
 end.


So,
 Guitar
 is
 working
 on
 that
 extra
 fix.


And
 what
 it
 will
 end
 up
 doing
 is
 just


fixing
 in
 that
 orders.py


um
 file
 and
 adding
 extra
 validation
 for


this.
 Just
 takes
 a
 couple
 minutes
 and
 it


automates
 this
 entire
 process
 of


diagnosing
 a
 break,


re-pushing,
 and
 then
 fixing
 and


verifying
 your
 commits
 every
 time.


I
 am
 I
 am
 really
 passionate
 about
 the


fact
 that
 we
 not
 cannot
 be
 shipping


unverified
 code.
 This
 is
 absolutely


essential
 and
 we
 need
 to
 be
 verifying


every
 PR
 with
 context,
 with


verification,
 with
 both
 deterministic


and
 um


a
 logical
 understanding
 of
 what's
 being


done
 here.


So,


while
 this
 fix
 lands,


it'll
 just
 update
 uh
 the
 commit
 here.


We'll
 see
 it
 pop
 up
 in
 the
 files
 change


diff.
 Um
 it
 will
 analyze
 and
 make
 sure


that
 the
 workflow
 goes
 green,


and


um


it
 should
 be
 ready
 to
 merge.
</details>

### 练习二：注入上下文与业务规则验证

**>>**: 不过我先快速切到第二个拉取请求，在这里我们要讲上下文（context）。

每个代码仓库或每个团队都有额外的规则和业务逻辑，这些并不一定会体现在代码中。它们可能存在于高级工程师的脑子里、wiki 里、Confluence 页面或者类似的地方。这些业务规则并不一定与代码的技术正确性有关。

比如在这个 PR 里，我们为每张售出的门票增加了 3.50 美元的服务费。如果你买了一张 50 美元的演唱会门票，最后你需要支付 53.50 美元。

但是对于这家假想的公司来说，他们有一条规则：向客户展示的每一个价格必须是全包价（all-in price）。我不知道你们怎么看，但我个人全世界最讨厌的事情就是：去买票的时候明明写着 30 美元，结果加上各种手续费杂七杂八的，最后要付差不多 70 美元。这家假想公司非常重视用户体验，他们为用户着想。所以他们定了一条业务规则：展示的所有价格都必须是全包价。

但我们该如何执行这一规则呢？我们如何确保代码审查智能体能够审查这一点？有几种不同的方法。一种是 `.gitar/review` 目录，另一种是 `.gitar/rules` 目录。

review 目录的作用是：你可以添加所有你想要的上下文，随意添加 Markdown 文件、写入任意多的业务逻辑，Guitar 会根据这些内容来引导自身的审查。顺便说一句，这个功能非常强大。我鼓励大家私下随意往里面灌注上下文，Guitar 在吸收并应用这些上下文方面极其高效和强大。

至于 rules 规则部分，规则功能非常棒，我自己经常配置规则。规则指的是：如果 PR 满足了某些条件，就会触发规则并执行相应操作。例如在这个例子中，每当有定价相关的文件被编辑或更新时，它就会进行检查，并向审查人员展示一份列表：“嘿，这些是被编辑的所有面向客户的字段”，并告诉你这些字段是否属于全包价。

但在规则上你能做的事情远不止这些。举个例子，假设你和另一位工程师在 Slack 对话中讨论某项新功能，你可以设置一条规则：“每当我在 PR 描述中粘贴一个 Slack 链接时，就去访问 Slack，查看那段对话，并根据我们之前的讨论来检查我的代码。”每次你这么做，它都会自动触发。这非常酷，我很喜欢这个功能。

往下翻——抱歉，提前剧透了一下 Guitar 在那里发现了什么。但我们可以看到，这里添加了服务费以及一些测试。

如果我切回主讨论区，可以看到 Guitar 已经发布了它的代码审查。

它发布了这条规则，对吧？它识别出了所有这些定价字段，并提醒你：“哦，这到底是不是全包价。”它找到了这个 bug。各位，再次说明，这本身并不算技术工程层面的 bug。如果你只是一个真空环境下的世界顶级程序员，单纯看这段代码并不能说它是错误的；但根据你的业务和具体场景，这可能并不是你想要实现的效果。因此 Guitar 能够对照这些业务规则进行检查，这非常强大。

这个 PR 我们先不急着合并。在进入第三个练习之前，我们先把它留在这里。

另外提一下，之前那个练习里的 `guitar fix` 已经跑完了，已经完全通过了验证。Guitar 批准了它，完成了修复，我们可以看到……让我看一下 diff。接着它修复了 `orders.py` 并加入了那项额外的校验检查。
<details><summary>Original English</summary>
>> But,
 I'm
 going
 to
 move
 on
 real
 quick


into
 the
 second
 pull
 request,


where
 we're
 going
 to
 cover
 context.


So,


every
 repo
 or
 every
 team
 has
 extra
 rules


and
 uh
 business
 logic
 that
 doesn't


necessarily
 get
 represented
 in
 the
 code.


So,
 that
 could
 be
 something
 that
 lives


in
 your
 senior
 engineer's
 head
 or
 in
 a


wiki
 or
 in
 a
 confluence
 page
 or


something
 like
 that.
 And
 these
 business


rules


don't
 necessarily
 have
 anything
 to
 do


with
 code
 correctness.
 So,


for
 this
 PR
 right
 here,
 we
 are
 adding
 in


a
 $3.50


service
 fee
 for
 every
 ticket
 that's


that's
 purchased.
 So,
 if
 you
 buy
 a
 $50


ticket
 to
 a
 concert,
 at
 the
 end
 you're


going
 to
 be
 paying
 $53.50.


But,


for
 this
 hypothetical
 company
 right


here,
 they
 have
 a
 rule
 that
 says


every
 price
 we
 show
 a
 customer
 is
 the


all-in
 price.
 I
 don't
 know
 about
 you,


but
 it
 is
 the
 biggest
 pet
 peeve
 in
 the


world
 for
 me
 when
 I
 go
 and
 buy
 a
 ticket


for
 something
 and
 it's
 like
 $30
 and
 then


with
 fees
 and
 everything
 like
 that,
 it's


like
 $70
 by
 the
 end
 of
 it.
 Um
 this


hypothetical
 company
 cares
 about
 user


experience.
 They
 care
 about
 you.
 So,


they
 have
 a
 business
 rule
 that
 says


every
 price
 we
 show
 is
 the
 all-in
 price.


But,
 how
 do
 we
 enforce
 it?
 How
 do
 we


enforce
 that
 this
 is
 going
 to
 get


reviewed
 by
 a
 code
 review
 agent.
 Well,


there's
 a
 couple
 different
 ways.
 One
 is


this
 uh
 review


directory.gitar/reviewdirectory


and
 another
 one
 is
 this


.gitar/rulesdirectory.


So,
 what
 a
 review
 directory
 does
 is
 you


can
 add
 all
 the
 context
 you
 want,
 as


many
 MD
 files,
 as
 much
 of
 your
 business


logic
 as
 you
 want
 to
 add
 and
 Gitar
 will


steer
 its
 own
 reviews
 according
 to
 this.


And
 this
 is
 super
 powerful,
 by
 the
 way.


Like,
 I
 encourage
 you
 on
 your
 own,
 just


throw
 as
 much
 context
 as
 you
 want
 at
 it.


Uh
 Gitar
 is
 incredibly
 efficient
 and


powerful
 at
 ingesting
 this
 and
 applying


it.


Uh
 for
 the
 rule
 section
 right
 here,


rules
 are
 awesome.
 I
 set
 these
 up
 all


the
 time.
 Rules
 are
 if
 a
 certain
 uh


criteria
 are
 met
 by
 a
 PR,
 then
 a
 rule


will
 fire
 and
 take
 an
 action.
 So,
 for


this
 one,
 is
 every
 time
 an
 some
 of
 the


pricing
 files
 are
 edited
 or
 updated,
 it


will
 check
 and
 present
 to
 a
 reviewer
 a


list
 of
 hey,
 these
 are
 all
 the
 customer


facing
 fields
 that
 are
 edited
 and
 it'll


let
 you
 know
 these
 are
 all
 in
 or


otherwise.


But
 you
 can
 do
 a
 ton
 with
 rules.
 Um
 one


that
 you
 can
 do
 is
 if
 let's
 say
 you
 and


another
 engineer
 are
 talking
 about
 uh
 a


new
 capability
 or
 feature
 in
 a
 Slack


thread.
 You
 can
 set
 a
 rule
 that
 says,


"Hey,


every
 time
 I
 paste
 a
 Slack
 link
 in
 my
 PR


description,


go
 into
 Slack,
 look
 at
 the
 conversation,


and
 check
 my
 code
 against
 the
 discussion


that
 we
 were
 having."
 And
 it'll
 just


fire
 every
 time
 that
 you
 do
 that.
 It's


super
 cool.
 I
 love
 this
 capability.


Um
 and
 if
 we
 scroll
 down,
 oops,
 a
 little


sneak
 peek
 of
 what
 Gittar
 found
 there.


But
 we
 can
 see
 that
 um
 there's
 this,
 you


know,
 service
 fee
 that
 gets
 added
 and


some
 tests.


If
 I
 hop
 back
 into
 the
 main


conversation,


we
 can
 see
 that
 Gittar
 posted
 his
 code


review.


It
 posted
 the
 rule,
 right?
 It
 sees
 all


of
 these
 pricing
 fields
 and
 it
 lets
 you


know,
 "Oh,
 this
 is
 is
 or
 is
 not
 an


all-in
 price."
 It
 finds
 the
 bug.
 Now


again,
 guys,
 this
 is
 not
 an
 engineering


bug
 per
 se,
 right?
 If
 you're
 just
 the


world's
 best
 programmer
 in
 a
 vacuum,


it's
 it's
 not
 like
 this
 is
 incorrect,


but
 according
 to
 your
 business
 and
 your


use
 case,
 this
 may
 or
 may
 not
 be
 what


you
 want
 to
 do.
 So
 Gittar
 is
 able
 to


check
 against
 this.
 It
 is
 so
 powerful.


We're
 not
 going
 to
 go
 ahead
 and
 merge


this
 one
 in.


Um
 we're
 just
 going
 to
 leave
 it
 before


hopping
 into
 the
 third
 exercise.


Oh,
 and
 just
 um


the
 Gittar
 fix


uh
 and
 then
 I'm
 going
 through
 and
 it's


been
 fully
 verified
 from
 the
 previous


exercise
 that
 we
 did.
 Um
 Gittar


uh
 approved
 it,
 fixed
 it,
 and
 we
 can
 see


that
 um


Let
 me
 look
 at
 the
 diff.


Then
 I
 went
 ahead
 and
 fixed
 this


orders.py


and
 added
 in
 this
 extra
 check.
</details>

### 练习三：CI 失败自动诊断与全自动合并流水线

**>>**: 现在进入第三个练习。我们在这里要做的是启用全自动化和自动合并——实现从打开 PR 的一刻起，直到合并完成的全流水线验证。

这里需要调整一些设置。如果你想跟着做，我强烈建议跟着操作；如果你只想先看看，稍后再配置，这个仓库的 README 中有完整的操作指南。

首先我们要进入 Rules（规则），向下滚动并勾选“Allow auto-merge”（允许自动合并）。这会开启允许 GitHub 进行自动合并的设置。

接下来进入 Rulesets（规则集），点击“New ruleset -> New branch ruleset”。规则集名称可以随便填，比如填 `workshop rule` 之类的都可以。确保它是 Active（处于激活状态），并确保目标设为默认分支（default branch）。

我们在这里要添加的检查规则是“Require status checks to pass”（要求状态检查通过）。这样做达到的效果是：如果你在搜索框里输入 `test`，意思就是我们要求 CI 必须变绿、测试必须通过，之后我们才会认为“可以自动合并”。

再次说明，如果你遗漏了其中的任何步骤，README 里都把所有这些要求列得一清二楚。

点击创建。如果你所在的公司像我们公司一样配置了安全认证，可能会要求输入验证码，我这里正好有一个。

太棒了，我们成功创建了新的规则集。

现在你可能已经看到，对于这个 PR，它刚刚被阻塞了，有一项测试失败了。这次变更做的事情实质上是重构门票扫描的方式。它的改动是：“我们现在要把门票更新为指向门票页面的 URL，并重构应用内部已经存在的一部分逻辑。”

但是测试挂了。如果你点进去看失败原因，它显示：“测试票不能被重复扫描两次”。也就是说，它捕捉到了在重构过程中遗漏的一项校验。如果我检票扫了我的票，应该是一次性生效的。我不应该能够一遍又一遍地扫码，让我后面的朋友都用我同一张票进场。逻辑非常简单，但在重构中很容易遗漏。

在 Guitar 的审查中，它能够检查 CI。它指出了“CI failed”（CI 失败），并说明：“在检票环节有一项测试失败。第二次扫描已使用的票返回了 200 状态码。”所以，如果你的流水线中出现任何失败，Guitar 能够检查日志并进行修复。

在我个人的工程生涯中，最大的烦恼之一大概就是那种排查测试日志的死循环：你必须点进去看哪里挂了，尝试诊断原因，然后在本地修复、推送代码，接着等待流水线重新跑完。有些流水线耗时特别长，你只能干等着，结果又挂了，这简直是一个既耗时又费钱的过程。你甚至可能还得不断在通讯软件上催促另一个工程师来审查。我光是想想都觉得头疼。

Guitar 替你把这一切全解决了。它能够将这个流程自动化，并持续推进。

操作非常简单。你只需要输入——抱歉，我单手打字：输入 `guitar auto apply on`，然后输入 `guitar auto merge on`。`auto apply` 的作用是允许 Guitar 持续推送修复代码，不需要你每次都手动点击确认；而 `auto merge` 的作用则是：每当它检测不到任何剩余问题，并且流水线最终完全通过时，它就会直接帮你完成合并。

好的，我提交这条评论。
<details><summary>Original English</summary>
>> But
 moving
 on
 to
 the
 third
 exercise.
 And


what
 we're
 going
 to
 do
 here
 is
 we
 are


going
 to
 enable
 full
 automation
 and


merging
 complete
 pipeline
 verification


from
 the
 moment
 you
 open
 your
 PR


to
 the
 moment
 that
 it
 gets
 merged
 in.


And
 there's
 going
 to
 be
 a
 little
 bit
 of


settings
 that
 we
 have
 to
 adjust
 here.
 So


if
 you
 want
 to
 follow
 along,
 I
 highly


encourage
 you
 to.
 If
 you
 just
 want
 to


watch
 and
 set
 this
 up
 later,
 the
 read
 me


for
 this
 repo
 has
 all
 of
 the


instructions
 available
 for
 you.


Um
 so
 the
 first
 thing
 that
 we're
 going


to
 want
 to
 do


is
 hop
 into
 rules,
 scroll
 down,
 and


click
 allow
 auto
 merge.
 That
 sets
 up
 the


GitHub
 setting
 that
 allows
 for
 GitHub's


auto
 merging.


Next
 thing
 is
 to
 go
 to
 rule
 sets.


Hit
 new
 rule
 set,
 new
 branch
 rule
 set.


And
 for
 rule
 set
 name,
 you
 can
 just
 say,


you
 know,


workshop


rule
 or
 whatever
 you
 want
 it
 to
 be.


Make
 sure
 it's
 active.


And
 make
 sure
 that
 you
 target
 default


branch.


And
 the
 rule
 that
 we
 want
 to
 set
 here,


the
 check
 we
 want
 to
 set
 is
 require


status
 checks
 to
 pass.


And
 what
 that
 will
 do


is
 if
 you
 type
 in
 test
 here,
 is
 that
 we


are
 going
 to
 require
 our
 CI
 to
 go
 green,


our
 test
 to
 pass
 before
 we
 say,
 "Hey,


this
 is
 good
 to
 go
 ahead
 and
 auto


merge."


Again,
 if,
 you
 know,
 you
 missed
 any
 of


those
 steps,
 this
 is
 in
 the
 read
 me


with
 all
 of
 those
 different
 requirements


listed
 there
 for
 you.


So
 go
 ahead
 and
 create
 that.
 And
 if
 your


company
 has
 secure


off
 set
 up
 like
 mine
 does,
 it
 may


enforce


a
 code,
 which
 I
 have
 right
 here.


Awesome.
 Cool.
 So
 we've
 created
 a
 new


rule
 set.


So,
 you
 may
 see
 already
 for
 this
 PR,


it's
 just
 been
 blocked.
 A
 test
 has


failed.
 But,
 what
 this
 is
 doing
 is
 it
 is


essentially
 refactoring
 the
 way
 that


tickets
 are
 scanned.
 Um


what
 it's
 saying
 is
 that,
 "Hey,
 we're


going
 to
 update
 tickets
 now
 at
 the
 point


to
 the
 ticket
 page
 URL
 and
 refactoring
 a


little
 bit
 of
 the
 logic
 that
 already


existed
 within
 the
 application."


Um


but
 the
 the
 the
 test
 failed.
 And
 if
 you


go
 into
 that
 and
 you
 look
 at
 what


failed,
 it
 says,
 "Test
 ticket
 cannot
 be


scanned
 twice."
 So,
 it
 caught
 a
 check


that
 was
 missed
 in
 the
 refactor.
 Um


if
 I
 scan
 my
 ticket,


I
 should
 be
 one
 and
 done.
 I
 don't
 want


to
 continue
 scanning
 over
 and
 over
 and


let
 all
 my
 friends
 use
 my
 same
 ticket


behind
 me.
 It's
 pretty
 basic,
 but
 it's


easy
 to
 miss
 logically.


In
 Guitar's
 uh
 review,


it
 is
 able
 to
 inspect
 CI.
 It
 says
 CI


failed.
 It
 says,
 "One
 test
 fails
 at
 the


gate
 check-in.
 Scanning
 an
 already
 used


ticket
 a
 second
 time
 returns
 200."
 So,


if
 you
 have
 any
 failures
 in
 your


pipeline,


Guitar
 is
 able
 to
 inspect
 the
 logs
 and


fix.


One
 of
 the


I
 guess
 biggest
 annoyances
 in
 my


engineering
 career
 is
 like
 the
 test
 log


inspection
 loop,
 where
 you
 have
 to
 go
 in


and
 see
 what
 failed
 and
 then
 try
 and


diagnose
 and
 then,
 you
 know,
 fix
 it


locally
 and
 then
 push
 it
 and
 then
 wait


for
 the
 pipeline
 to
 rerun.
 And
 some
 of


these
 pipelines
 can
 get
 really
 long.
 And


then
 you're
 just
 waiting
 and
 then
 it


fails
 again
 and
 it's
 just
 this


time-consuming,
 money-burning
 process.


And
 you
 may
 even
 need
 to
 like
 keep


pinging
 another


engineer
 about
 reviewing.


And
 I'm
 getting
 a
 headache
 just
 thinking


about
 it.


Guitar
 just
 solves


all
 of
 that
 for
 you.
 It
 is
 able
 to


automate
 that
 process
 and
 keep
 going.


So,
 it's
 very
 simple.


All
 you
 have
 to
 do
 is
 type


guitar,
 sorry
 I
 doing
 this
 with
 one


hand,
 is
 guitar
 auto


apply


on


and
 then
 guitar
 auto
 merge
 on.
 And
 what


auto
 apply
 is
 going
 to
 do
 is
 just
 allow


guitar
 to
 keep
 pushing
 fixes
 without


needing
 you
 to
 to
 click
 yes
 on
 it
 every


time.
 And
 then
 what
 auto
 merge
 is
 going


to
 do
 is
 whenever
 it
 doesn't
 detect
 any


more
 issues
 and
 whenever
 your
 pipeline


finally
 passes
 fully,
 it's
 just
 going
 to


go
 ahead
 and
 merge
 that
 in
 for
 you.


Um


cool.


I'll
 add
 that.
</details>

**>>**: [哧笑]
<details><summary>Original English</summary>
>> [snorts]
</details>

**>>**: `guitar auto apply on`，`guitar auto merge on`。如果我刷新一下页面——Guitar 已经响应了，给这条评论点了个赞。谢了，Guitar。

接下来 Guitar 会进行迭代，推送修复方案，进行验证与检查，最终将其合并。这个过程会在几分钟内完成。

这真的无比强大。能够这样配置你的应用。顺便说一句，像我们刚才那样发评论只是为了这次工作坊的演示效果，因为我不想把其他几个 PR 也自动合并进去。你完全可以进入 Guitar 仪表板，为你想要的任何仓库全局开启自动批准和自动合并。你可以进行选择，针对每个仓库自行挑选配置的自动化程度和审批级别。如果你有一个极其前沿的智能体工作流，配有大量的防护机制（guardrails）、完备的测试和精密的流水线，在此基础上再加上 Guitar，你就可以直接让这些流程从一开始就全自动跑起来。

我刷新一下页面。Guitar 还在处理中，但它会持续推进并推送修复，直到一切全部合并完毕。

这个代码仓库也是，我鼓励大家带回家继续自行练习。在文末还有一些额外的进阶功能供大家探索[哧笑]。Taylor 稍后会介绍其中的一部分。大家有 14 天的专业版试用期，我非常建议大家在这个仓库上用起来，也鼓励大家把它用在自己的代码仓库中。我觉得大家会从中受益匪浅。

为了不让大家干坐着看 Guitar 迭代应用修复和自动合并，我现在把时间交还给 Taylor，让他来介绍更多高级特性。
<details><summary>Original English</summary>
>> Guitar
 auto
 apply
 on,
 guitar
 auto
 merge


on.
 If
 I
 refresh
 it,
 guitar
 Oh,
 it


already
 did
 it.
 Hit
 it
 with
 a
 nice


thumbs
 up.
 Thanks,
 guitar.
 Um


And
 so,
 guitar
 will
 iterate,
 push
 a
 fix,


validate
 it,
 verify
 it,
 and
 then


eventually
 merge
 it
 in.
 And
 this
 will


happen
 within
 a
 couple
 minutes.


This
 is


beyond
 powerful,
 right?
 To


be
 to
 be
 able
 to
 set
 up
 your


application.
 And
 by
 the
 way,
 adding
 the


comment
 like
 we
 did
 is
 just
 for
 the
 sake


of
 this
 workshop
 because
 I
 didn't
 want


to
 auto
 merge
 in
 the
 other
 PRs.
 You
 are


able
 to
 go
 into
 the
 guitar
 dashboard
 and


turn
 on
 auto
 approve
 and
 auto
 merge
 for


any
 of
 your
 repos
 that
 you
 want.
 You
 can


be
 selective.
 You
 can
 choose
 the
 level


of
 automation
 and
 approval
 that
 you
 set


up
 for
 each
 repository.
 If
 you
 have
 an


incredibly
 agentic
 workflow
 with
 tons
 of


guard
 rails
 and
 tests
 and
 a


sophisticated
 pipeline,
 um
 and
 then
 you


add
 guitar
 on
 top
 of
 that,


you're
 just
 able
 to
 let
 these
 rock
 and


roll
 right
 off
 the
 bat.


So,
 I'll
 refresh
 this.


Guitar
 still
 working,


um
 but
 it
 will
 continue
 to
 go
 and
 push


until
 everything
 is
 fully
 merged.


The
 repo
 as
 well.


Uh
 I
 encourage
 you
 to
 continue
 working


on
 it
 on
 your
 own
 at
 home.
 There
 are


some
 extra
 things
 at
 the
 end
 um


that
 that
 [snorts]
 are
 more
 advanced


capabilities
 for
 you
 to
 check
 out.
 Uh


Taylor's
 going
 to
 talk
 about
 a
 few
 of


them,
 but
 you
 have
 a
 14-day
 pro
 trial


that
 I
 encourage
 you
 to
 use
 on
 this


repo,
 that
 I
 encourage
 you
 to
 use
 on


your
 own
 repositories.
 Um
 I
 think
 you're


going
 to
 get
 a
 lot
 out
 of
 it.
 Um
 so


instead
 of
 uh
 holding
 y'all
 hostage
 to


watch
 Guitar
 add
 its
 uh
 auto
 merge
 in
 as


it's
 iterating
 and
 applying
 those
 fixes,


I'm
 going
 to
 pass
 it
 over
 to
 Taylor
 to


talk
 about
 a
 few
 more
 features.
</details>

### 高级特性：功能验证、知识库与跨仓库/跨 PR 分析

**>>**: 好的，感谢 Kilian 带来的精彩演示。我希望我们帮大家顺利上手了 Guitar。我只是想回来再聊聊 Kilian 刚才提到的几项更高级的功能。他刚才略有提及，但在我们这个简短的工作坊中完整演示这些功能有些超出了范围。

首先请注意，正如他刚才提到的，在仓库 README 的底部有一个“Take it further”（进阶探索）部分。我鼓励大家在工作坊结束后按照自己的节奏去尝试，带回家体验。

简要强调一下，Guitar 还支持一些额外的特性，包括但不限于：

第一，功能性验证（functional validation）。正如 Kilian 提到的，它会对照 PR 所实现的 ticket（例如 Jira ticket）来进行检查。这非常强大，因为它确保了变更不仅干净规范，而且正确、完整。对吧？它目前支持 Jira 和 Linear，也支持 Slack，你可以通过 Guitar 仪表板的 Settings -> Integrations（设置与集成）进行连接。例如，你可以引用一条 Slack 消息或一个 Jira ticket，为 Guitar 提供更充分的信息来构建审查。

Guitar 还利用了一项我们称之为“知识”（Knowledge）的特性，它能学习规范约定，并根据收到的反馈以及你提供给它的反馈来参考误报情况。而且事实上，这些反馈会根据审查者的资历深浅进行加权，这非常精妙。

这从本质上展示了每次审查背后的规则是什么、它们源自何处以及为何生效。

今天我还想向大家展示两项功能：一项是跨仓库分析（cross-repo analysis），另一项是跨 PR 分析（cross-PR analysis）。

跨仓库分析能够发现那些在单个仓库中可能完全可以顺利合并、但却会破坏另一个仓库代码的 PR。而且在分析的仓库数量上实际上没有任何限制，这很值得思考。

另外还有跨 PR 分析，它能在多个处于进行中的 PR 之间进行相互检查。正如大家可能知道、或者很可能亲身经历过的那样——我自己就深有体会——两个 PR 各自单独看都能通过测试，但合在一起却可能把生产环境搞垮。随着技术栈中引入的智能体越来越多，这种风险只会不断上升。

现在 Kilian 正在带大家浏览仪表板。我们快速点进其中一个发现项看看。请注意，它会直接指引你找到修复方案，向你展示问题发生在何处，更重要的是解释了为什么这个问题确实至关重要——为什么你会想交给 Guitar 来处理并修复它。

这就是 Guitar 的概要介绍。我们希望大家能从中有所收获。再次建议大家有需要的话可以在课后继续深入体验这款工具，尽情向它投入各种上下文，以获得更优质、更知情的代码审查。

有两项特性是属于企业版的功能，其余这些都包含在 Pro 专业版中。

我们现在把时间留给大家提问。如果大家有任何问题，我们很乐意解答。非常感谢大家。
<details><summary>Original English</summary>
>> Well,
 thank
 you
 Killian
 for
 the


insightful
 demo.
 I
 hope
 that
 we
 were


able
 to
 help
 y'all
 get
 a
 rocking
 and


rolling
 with
 Guitar.
 Just
 want
 to
 pop


back
 up
 to
 discuss
 a
 couple
 more


advanced
 features
 that
 Killian
 has
 just


mentioned,
 uh
 which
 he
 touched
 on,
 but


whose


walk-through
 would
 go
 beyond
 the
 scope


of
 this
 short
 and
 simple
 workshop.
 So,


first
 note
 that
 at
 the
 bottom
 of
 the


read
 me
 in
 the
 repo
 is
 a
 take
 it
 further


section,
 as
 he
 just
 mentioned.


I
 would
 encourage
 y'all
 to
 follow
 that


after
 this
 workshop.
 Follow
 it
 at
 your


own
 pace,
 take
 it
 home.
 Um
 but
 to


quickly
 highlight,
 Guitar
 does
 enable


some
 additional
 features
 including


but
 not
 limited
 to


number
 one,
 functional
 validation.
 As


Killian
 mentioned,
 it
 checks
 each
 PR


against
 the
 ticket
 in
 the
 case
 of
 Jira


that
 it
 implements.
 And
 this
 is
 really


powerful
 because
 it
 ensures
 that
 the


change
 is
 correct
 and
 complete
 and
 not


just
 clean.
 All
 right?


So,
 it
 works
 with
 Jira
 currently,


linear.
 It
 works
 with
 Slack
 as
 well,


which
 you
 can
 can
 connect
 through
 the


Guitar
 dashboard
 at
 settings
 and


integrations.


For
 example,
 you
 can
 reference
 a
 Slack


message
 or
 a
 Jira
 ticket
 to
 better


inform
 and
 structure
 your
 reviews
 with


Guitar.


Guitar
 also
 takes
 advantage
 of
 a
 feature


that
 we're
 calling
 knowledge,
 which


learns
 conventions
 and
 also
 references


false
 positives
 from
 the
 feedback
 that


it
 receives
 and
 the
 feedback
 that
 you


provide
 to
 it.
 And
 it's
 weighted
 by


reviewer
 seniority,
 actually,
 which
 is


pretty
 neat.


Um


and
 this
 shows
 essentially
 the
 rules


behind
 every
 review,
 where
 they
 come


from,
 and
 why
 they're
 coming
 into
 play.


There's
 two
 that
 I
 would
 like
 to
 show


you
 all
 today.
 The
 first
 is
 cross
 repo,


and
 the
 other
 is
 cross
 PR
 analysis.


Cross
 repo
 analysis
 finds
 PRs
 that
 may


very
 well
 merge
 cleanly
 independently,


but
 um


but
 break
 code
 in
 another
 repo.
 Right?


And
 there's
 actually
 no
 limit
 on
 how


many
 repos
 it
 analyzes.
 Just
 food
 for


thought.


Um
 and
 then
 there's
 cross
 PR
 analysis
 as


well,
 which
 checks
 in-flight
 PRs
 against


each
 other.


As
 you
 probably
 know,
 or
 may
 very
 well


have
 experienced,
 I
 certainly
 have,
 two


PRs
 can
 each
 pass
 alone
 and
 yet
 still


break


production
 together,
 and
 that's
 just
 a


risk
 that
 grows
 with
 every
 agent
 you
 add


into
 the
 stack.


So,
 Killian's
 walking
 you
 through
 the


dashboard.
 Um
 just
 to
 quickly
 touch
 on


each
 of
 those
 features.
 Um
 if
 you
 would,


perhaps
 we
 could
 click
 into
 a
 single
 one


of
 these
 findings.


Note
 that
 it
 points
 you
 to
 the
 fix,


shows
 you
 where
 this
 is
 occurring,
 and


importantly,
 why
 it
 actually
 matters,


right?
 Why
 you
 want
 to
 defer
 to
 a
 uh
 to


Guitar
 to
 go
 about
 uh
 fixing
 it.


And
 that
 is
 Guitar
 in
 a
 nutshell.
 We


hope
 that
 y'all
 have
 found
 some
 utility


from
 this.
 Um
 again,
 feel
 free
 to
 take


this
 home
 should
 you
 like
 to
 better


familiarize
 yourself
 with
 the
 tool.
 Play


around
 with
 all
 of
 the
 context
 that
 you


can
 throw
 at
 it
 to
 get
 better
 and
 more


informed
 reviews.


Um
 there
 are
 a
 couple
 that
 come
 with
 the


um
 enterprise
 feature.
 All
 of
 this
 is


going
 to
 to
 ship
 with
 with
 Pro.


And
 so
 we'll
 open
 the
 floor
 now
 to
 any


questions.
 Should
 y'all


have
 any
 questions
 for
 us,
 we'd
 be
 happy


to
 answer
 those.
 Thank
 you
 very
 much.
</details>

### 问答环节：MCP 协议与知识摄取

**>>**: 是的，Git Tower（Guitar）具备 MCP 连接能力。它能够通过多种方式摄取这类上下文。
<details><summary>Original English</summary>
>> Yes,
 so
 Git
 Tower
 has
 MCP
 connectivity.


It's
 able
 to
 ingest
 um
 context
 like
 that


in
 a
 variety
 of
 ways.
 Um
</details>

**>>**: 配置你们自己的集成，对。
<details><summary>Original English</summary>
>> Configure
 your
 own
 integrations.
 Yeah.
</details>

**>>**: 这听起来和我们的 Knowledge（知识）功能稍微有些不同。这听起来更像是上下文功能——它会对照架构指南之类的东西来审查代码。而我们的 Knowledge 标签页主要用于引导 Git Tower（Guitar）特定的审查行为。

比如，如果 Git Tower 发布了一条审查意见并建议以某种特定方式修复，你可以反馈说：“其实我们平时倾向于用这种方式或者 XYZ 方式来修复这类问题。”Git Tower 就可以把这个偏好保存下来，用于它未来的自主修复中。

这是一个很好的问题。关于 Knowledge 具体是如何进行摄取的，我还得向大家后续确认。但我确信——事实上我确切地知道——是有办法把它连接起来的，无论那是不是在 Knowledge 功能本身内部。这方面细节我后续再跟您跟进。
<details><summary>Original English</summary>
>> That
 that
 sounds
 a
 little
 bit
 different


from
 the
 knowledge
 capability
 that
 we


have.
 That
 sounds
 more
 like
 the
 context


capabilities
 where
 it'll
 review,
 you


know,
 code
 against,
 you
 know,
 like


architecture
 guidelines
 and
 things
 like


that.
 The
 knowledge
 tab
 that
 we
 have
 is


um


steering
 Git
 Tower
 specific
 reviews.
 So


if
 Git
 Tower
 posts
 a
 review
 and
 suggests


a
 fix
 in
 a
 certain
 way,


you
 can
 say,
 "Hey,
 we
 actually
 tend
 to


fix
 stuff
 in,
 you
 know,
 this
 type
 of
 way


or
 or
 XYZ
 manner."
 And
 Git
 Tower
 can


save
 that
 for
 its
 own
 fixes
 in
 the


future.


That's
 a
 great
 question.
 I'd
 have
 to


follow
 up
 on
 you
 about
 how
 exactly


knowledge
 ingestion
 works.
 Um


but
 I
 I
 I
 believe
 I
 actually
 I
 actually


know
 for
 a
 fact
 that
 there
 are
 ways
 to


get
 that
 connected,
 whether
 that's
 in


the
 knowledge
 feature
 itself.
 I
 would


have
 to
 follow
 up
 with
 you
 about
 that.
</details>