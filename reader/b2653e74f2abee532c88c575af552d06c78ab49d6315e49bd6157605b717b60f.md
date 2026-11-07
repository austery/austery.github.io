---
author: AI Engineer
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UW8Qkk7MG8A
speaker: AI Engineer
tags:
  - ai-agent
  - vulnerability-detection
  - business-logic-flaw
  - application-security
  - static-analysis
title: Sonar 推出 SonarQube Hunter Agent：利用前沿 AI 推理检测业务逻辑安全漏洞
summary: Sonar 推出 AI 安全智能体 SonarQube Hunter Agent，并加入 OpenAI Daybreak Cyber 合作伙伴计划。该智能体针对传统 SAST 难以覆盖的意图与业务逻辑漏洞，通过全局仓库映射与多子智能体协作发现越权、业务逻辑和身份验证缺陷，并支持按需或定时扫描与自动修复。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Taylor Luttrell
companies_orgs:
  - Sonar
  - OpenAI
products_models:
  - SonarQube
  - SonarQube Hunter Agent
  - SonarQube Cloud
  - SonarQube Server
media_books: []
status: evergreen
---
### 智能体时代的安全挑战与传统 SAST 的局限

>> 大家好，下午好，欢迎大家来到我关于 SonarQube Hunter Agent 的演讲。它是一款 AI 安全智能体，专为在攻击者之前检测出 SAST 无法发现的那类漏洞而构建。我叫 Taylor Luttrell，在 Sonar 负责开发者内容制作，我们是 SonarQube 的缔造者。今天我非常兴奋能带大家了解并上手 SonarQube Hunter Agent。

<details>
<summary>Original English</summary>
[music]


>> Well,
 hello,
 good
 afternoon,
 and
 welcome


all
 to
 my
 session
 on
 the
 SonarQube


Hunter
 Agent.


It's
 an
 AI
 security
 agent
 and
 built
 to


detect
 the
 classes
 of
 vulnerabilities


that
 SAST
 cannot
 and
 before
 attackers


can.


My
 name
 is
 Taylor
 Luttrell.
 I
 create


developer
 content
 at
 Sonar.
 We're
 the


makers
 of
 SonarQube.
 Today,
 I
 am
 very


hyped
 to
 get
 y'all
 up
 and
 running
 with


SonarQube
 Hunter
 Agent.
</details>

>> 首先，正如我们所知，在智能体时代，代码正以智能体的速度和智能体的体量在交付，结果导致进入生产环境的漏洞数量达到了前所未有的程度，使各家公司处于暴露且脆弱的境地。

<details>
<summary>Original English</summary>
So,
 to
 start,
 as
 we
 all
 know,
 in
 the


agentic
 era,
 code
 is
 shipping
 at
 both


agentic
 velocity
 and
 agentic
 volume,
 and


as
 a
 result,


an
 unprecedented
 number
 of


vulnerabilities
 are
 reaching
 production


environments,


leaving
 companies
 exposed
 and


vulnerable.
</details>

>> 如果你熟悉或者正在积极使用像 SAST 这种传统的基于模式的扫描工具，你可能非常清楚，存在某些类别的问题是它根本无法处理的。这些是关于意图的问题，而不是它所擅长发现的模式。

<details>
<summary>Original English</summary>
And
 if
 you're
 familiar
 or
 you
 actively


use
 traditional
 pattern-based
 scanners


like
 SAST,
 you
 may
 very
 well
 understand


that
 there
 are
 classes
 of
 issues
 which


it
 is
 simply
 not
 designed
 to
 account


for.


These
 are
 issues
 of
 intent
 rather
 than


the
 patterns
 that
 it
 is
 adept
 at


finding.
 And
 so,
</details>

>> 解释起来就是，至少对 SAST 而言，并非所有的漏洞都是你代码中的 bug。也就是说，它能发现的问题并不总能覆盖所有情况。这些是关于意图的问题，与逻辑层面的漏洞相关：代码本身完全可能是合法的，但意图本身却不对。也就是说，它在技术上或功能上是正确的，但背后的意图存在缺陷，对吧？比如，它与你的底层业务逻辑相冲突。

<details>
<summary>Original English</summary>
in
 explaining
 this,


um


basically,
 not
 all
 vulnerabilities
 are


bugs
 in
 your
 code,
 at
 least
 according
 to


SAST.
 And
 that's
 to
 say


that
 the
 issues
 that
 it
 can
 find


are
 not
 always


accounted
 for.
 These
 are
 issues
 of


intent,
 issues
 related
 to
 logic-level


vulnerabilities,
 wherein
 the
 code
 may


very
 well
 be
 valid,


but
 the
 intent
 itself
 is
 not.
 And
 that's


to
 say
 that
 it's
 technically
 or
 it's


functionally
 correct,


but
 the
 intent
 behind
 it
 is
 flawed,


right?
 It
 contradicts
 your
 underlying


business
 logic,
 for
 example.
</details>

>> 如今在许多公司，渗透测试最多一年两次，或者每季度一次。但由于攻击者现在配备了比以往更好的模型，而且智能体生成的代码变更交付之间的间隔越来越短，我们需要一类全新的智能体来查明、检测并修复这些漏洞。因此，我带来 SonarQube Hunter Agent 正是为了精准填补这一空白。

<details>
<summary>Original English</summary>
Now,
 in
 many
 companies,
 pentests
 happen


at
 most
 twice
 per
 year,
 perhaps
 once
 per


quarter.


But,
 as


attackers
 are
 now
 enabled
 with
 better


models
 than
 ever,
 um
 and
 as
 the
 time


between
 which


these
 uh


agent-generated
 changes
 are
 shipping,
 we


need
 a
 new
 class
 of
 agents
 to
 suss
 out,


to
 detect,
 and
 to
 fix
 these


vulnerabilities.
 So,
 I
 introduce


SonarQube
 Hunter
 Agent
 to
 fill
 that
 gap


exactly.
</details>

### Hunter Agent 的工作机制与多智能体架构

>> 为了实现这一点，首先会有一个智能体对代码仓库进行全局映射。然后，基于该全局映射，它会启动三个专门的智能体，分别对应它能够发现的一个问题类别。这些问题着眼于所有组件之间的关系，并尝试定义出所谓的安全预期。随后，我们会运行对抗性验证，确保这些问题确实准确，而不是误报。我们还设有噪声门禁，以减少那些有效性极低的问题，或者是属于系统既定设计的情况。

<details>
<summary>Original English</summary>
So,
 in
 order
 to
 accomplish
 this,
 there's


first
 an
 agent
 that
 maps
 the
 repository


globally.
 And
 then,
 based
 on
 that
 global


map,
 it
 starts
 three
 specialized
 agents,


one
 per
 class
 of
 issue
 that
 it
 can
 find.


And
 these
 issues
 look
 at
 relationships


between
 all
 the
 components
 and
 try
 to


define
 the
 security
 expectations,
 if
 you


will.


We
 then
 run
 adversarial
 validation
 to


make
 sure
 that
 the
 issues
 are
 actually


correct
 and
 not
 false
 positives.
 And
 we


have
 noise
 gates
 as
 well
 to
 reduce
 the


really
 low


um


validity
 uh
 issues
 or
 issues
 that
 would


be
 by
 design.
 And
 so,
 these
 playbooks
</details>

>> 这些剧本本质上是将代码仓库作为输入。它们处理所有复杂的智能体编排，并输出高质量的问题，你可以随后将它们指派给你的开发者。在此过程中，我们会为这些问题指定严重程度，确定它对你的整体代码库可能产生的影响，并直接为你指出可以直接处理它们的准确位置。

<details>
<summary>Original English</summary>
essentially
 take
 a
 repository
 as
 input.


They
 handle
 all
 the
 complex
 agent


orchestration,
 and
 they
 output


high-quality
 issues
 that
 you
 can
 then


assign
 to
 your
 developers.
 In
 doing
 so,


we
 assign
 a
 severity
 to
 these
 issues.
 We


determine
 the
 impact
 that
 it
 can
 have
 on


your
 overall
 codebase,
 and
 we
 point
 you


to
 the
 exact
 location
 where
 they
 can
 be


addressed
 directly.
</details>

>> 在呈现这些发现时，如果你已经在使用 SonarQube，这些问题会与我们通过 SAST 工具寻找的所有其他问题一起呈现。正如我所说，你可以为所有这些问题指定严重程度。

<details>
<summary>Original English</summary>
So,
 in
 representing
 these
 findings,
 if


you
 already
 use
 SonarQube,
 these
 issues


will
 surface
 alongside
 all
 of
 the
 other


issues


that
 we
 already
 look
 for
 using
 our
 SAST


tool.
 As
 I
 said,
 you
 can
 assign
 a


um


You
 can
 assign
 a
 severity
 to
 all
 of


these.
</details>

### OpenAI Daybreak 合作与分层安全体系

>> 在智能体时代，攻击者的行动速度比以往任何时候都要快，你需要一个能跟上这一节奏的解决方案。因为漏洞从被发现到被武器化的时间正在缩短，而且现在缩短得越来越快。

<details>
<summary>Original English</summary>
Um
 in
 the
 agentic
 era,


where
 attackers
 are
 moving
 faster
 than


ever,


you
 need
 a
 solution
 that
 can
 keep
 pace


with
 just
 that.
 As
 the
 time
 between
 a


vulnerability
 being
 discovered
 and


weaponized
 is
 shrinking,
 and
 it's


shrinking
 now
 ever
 faster.
</details>

>> 因此，我们非常激动地在今天宣布——大家是首批听到这一消息的——Sonar 正在加入 OpenAI Daybreak Cyber 合作伙伴计划。这将直接在像 SonarQube Hunter Agent 这样的产品中，为你带来受治理的高级网络安全前沿模型访问能力。因为我们认识到，安全团队同样需要前沿智能。我们必须跟上我们所对抗的攻击者的步伐，因此我们认为有必要将其作为这套智能体的一部分，用于查明那些可能被遗漏的漏洞类别。

<details>
<summary>Original English</summary>
And
 so,
 we
 are
 very
 excited
 to
 announce


today,
 y'all
 are
 among
 the
 first
 to
 hear


this,
 that
 Sonar
 is
 joining
 the
 Open
 AI


Daybreak
 Cyber
 Partner
 Program.
 This
 is


going
 to
 bring
 you
 governed
 access
 to


advanced
 cybersecurity
 frontier
 models


directly
 in
 products
 like
 SonarQube


Hunter
 Agent.


Because
 we
 recognize
 that
 security
 teams


need
 frontier
 intelligence,
 too.


We
 have
 to
 keep
 pace
 with
 the
 very


attackers
 that
 we
 are
 fighting
 against,


and
 so
 we
 saw
 fit
 to
 include
 this
 as


part
 of
 the
 very
 agent
 that
 susses
 out


the
 classes
 of
 vulnerabilities
 that
 may


be
 slipping
 through
 the
 cracks.
</details>

>> 我们在 SonarQube Hunter Agent 内部提供前沿推理。剧本会贯穿整个代码库运行。每一个线索在呈现之前都会经过调查和验证，而这些 Daybreak 级别的推理深化了每个剧本背后的推理过程，以确保所有的发现都是精确的、可复现的，同时也是可审计的。

<details>
<summary>Original English</summary>
We
 provide
 frontier
 reasoning
 inside


SonarQube
 Hunter
 Agent.
 Playbooks
 run


across
 the
 whole
 codebase.
 Every
 lead
 is


investigated
 and
 validated
 before
 it


surfaces,
 and
 these
 Daybreak
 class


reasonings
 deepen
 the
 reasoning
 behind


each
 playbook
 to
 ensure
 that
 all
 the


findings
 are
 precise,
 they
 are


repeatable,
 and
 are
 auditable,
 as
 well.
</details>

>> 这样一来，我们建议将 SAST 与 Hunter Agent 相结合，我们也在单一平台上实现了这一点，以提供两层验证，确保没有任何漏洞被遗漏。一边是 SAST 和 SCA，另一边是 Hunter Agent 弥补空缺。这在设计上就是分层安全体系：零信任、多层级且彼此独立，确保我们能以精准且可复现的方式发现零日漏洞。

<details>
<summary>Original English</summary>
In
 doing
 so,
 we
 recommend
 combining
 SAST


and
 Hunter
 Agent
 and
 we
 do
 so
 in
 a


single
 platform
 to
 provide
 two
 layers
 of


verification
 so
 that
 nothing
 slips


through
 the
 cracks.
 SAST
 and
 SCA
 on
 one


hand
 and
 Hunter
 Agent
 picking
 up
 the


slack.


This
 is
 layered
 security
 by
 design.
 It's


zero
 trust,
 it's
 multi-layered,
 and
 it's


independent


to
 ensure
 that
 we
 can
 find
 zero-day


vulnerabilities
 with
 precision
 and
 a


repeatable
 manner.
</details>

### 产品演示：按需扫描与执行流程

>> 这就是 SonarQube Hunter Agent 的概况。现在我要切换环节，直接演示这款产品，让大家切身感受它在真实生产环境中的工作方式。

<details>
<summary>Original English</summary>
And
 that
 is
 SonarQube
 Hunter
 Agent
 in
 a


nutshell.
 I'm
 now
 going
 to
 switch
 gears


and
 I'm
 going
 to
 demo
 the
 product


directly
 to
 give
 you
 all
 a
 sense
 of
 how


it
 works
 in
 a
 real
 production
 setting.
</details>

>> 屏幕上是我自己的一个简单的 Python 应用程序，我已经用 SonarQube Hunter Agent 对其进行了扫描。我在这里登录了我的 SonarQube Cloud 控制台，如果我导航到 Hunter Agent，你可以看到在完全相同的界面内，只需点击“立即扫描”按钮，就可以触发按需扫描。这会为你预估在 SonarQube 上对项目执行全代码库深度推理传递所需的单元数量。你还应该注意到，这既适用于 SonarQube Cloud，也适用于我们的自托管版本 SonarQube Server。

<details>
<summary>Original English</summary>
So,
 I
 have
 on
 screen
 a
 simple
 Python


application
 of
 mine
 which
 I
 have
 scanned


with
 SonarQube
 Hunter
 Agent.
 I've
 logged


in
 to
 my
 SonarQube
 Cloud
 dashboard
 here


and
 if
 I
 navigate
 to
 Hunter
 Agent


you
 can
 see
 that
 within
 the
 very
 same
 UI


you
 can
 trigger
 an
 on-demand
 scan


by
 clicking
 the
 scan
 now
 button.


This
 is
 going
 to
 give
 you
 an
 estimation


of
 the
 number
 of
 units
 required
 to


perform
 the
 deep
 whole
 code
 base


reasoning
 pass
 over
 your
 project
 on


SonarQube.
 You
 should
 also
 note
 that


this
 works
 either
 with
 SonarQube
 Cloud


or
 with
 our
 self-hosted
 variant


SonarQube
 server.
</details>

>> 如果我点击“立即扫描”，它就会启动对该项目的扫描。根据项目的大小和复杂度，它可能需要一个小时以上的时间，所以我提前对这个项目运行了一次扫描，现在就带大家来看一看。

<details>
<summary>Original English</summary>
So,
 were
 I
 to
 click
 scan
 now,
 it
 would


kick
 off
 a
 scan
 of
 the
 project.


Depending
 on
 the
 size
 and
 the
 complexity


of
 the
 project


it
 can
 take
 upwards
 of
 an
 hour
 so
 I
 I


went
 ahead
 and
 ran
 a
 scan
 on
 this


project
 already
 which
 I'm
 going
 to
 walk


you
 through
 now.
</details>

>> 扫描耗时大约一个小时完成。在扫描项目时，它首先会安全地克隆目标仓库，赋予 AI 引擎对源代码的直接访问权限；然后它会分析应用架构，以映射潜在的攻击面并构建全面的威胁模型；接下来，它执行深度的上下文扫描，以检测 IDOR、失效的访问控制以及业务逻辑漏洞等严重缺陷；随后它将来自所有专业 AI 子智能体的发现聚合并去重为单一统一的问题列表；最后自动将经过验证的漏洞直接导出并记录到你的 SonarQube 问题列表中。

<details>
<summary>Original English</summary>
The
 scan
 took
 about
 an
 hour
 to
 complete


and
 then
 scanning
 the
 project
 at
 first


securely
 clones
 the
 target
 repository
 to


grant
 the
 AI
 engine
 direct
 access
 to
 the


source
 code.


It
 then
 analyzes
 the
 application


architecture
 to
 map
 potential
 attack


surfaces
 and
 build
 a
 comprehensive


threat
 model.


It
 next
 executes
 deep
 contextual
 scans


to
 detect
 critical
 flaws
 like
 IDOR,


broken
 access
 control,
 and
 business


logic
 vulnerabilities
 and
 it
 aggregates


and
 deduplicates
 findings
 from
 all


specialized
 AI
 sub-agents
 into
 a
 single


unified
 issue
 list
 before
 lastly


automatically
 exporting
 and
 logging


validated
 vulnerabilities
 directly
 into


your
 SonarQube's
 issue
 list.
</details>

### 漏洞分类与案例详情

>> 扫描完成后，我可以点击进入扫描结果，查看 Hunter Agent 发现的所有问题。你可以看到，这个项目上有 46 个未解决的问题，分布在我之前提到的三个问题类别中：分别是**失效的访问控制漏洞**、**业务逻辑漏洞**，以及**身份验证和会话漏洞**。

<details>
<summary>Original English</summary>
So
 after
 having
 completed,
 I
 can
 click


into
 scan
 results
 to
 surface


all
 of
 those
 issues
 that
 the
 Hunter


agent
 found.
 You
 can
 see
 here
 that
 there


are
 46
 open
 issues
 on
 this
 project


broken
 across
 the
 three
 issue
 categories


that
 I
 touched
 on
 earlier.


Those
 being
 broken
 access
 control


vulnerabilities,
 business
 logic


vulnerabilities,
 and
 authentication
 and


session
 vulnerabilities.
</details>

>> 快速回顾一下：
- **失效的访问控制漏洞**：涉及不安全的直接对象引用（IDOR）、缺失或不正确的授权检查、权限提升、敏感数据暴露以及跨站请求伪造（CSRF）。
- **业务逻辑漏洞**：涉及跳过必要的业务流程步骤、滥用可重复操作以及缺失速率限制等。
- **身份验证和会话问题**：正如我提到的，涉及访问破坏，或者更准确地说是身份验证失效、会话固定、永不过期的会话、脆弱的密码恢复机制、缺失多因素认证以及缺乏防暴力破解保护等。

<details>
<summary>Original English</summary>
So
 to
 quickly
 recap,
 these
 broken
 access


control
 vulnerabilities
 relate
 to
 such


things
 as
 insecure
 direct
 object


references
 or
 IDOR,
 missing
 or
 incorrect


authorization
 checks,
 privilege


escalations,
 sensitive
 data
 exposure,


and
 cross-site
 request
 forgery.


Moving
 on
 to
 business
 logic,


this
 relates
 to
 such
 things
 as
 skipping


required
 workflow
 steps,
 abusing


repeatable
 actions,
 and
 missing
 rate


limits.
 And
 then
 lastly,
 those


authentication
 and
 session
 issues
 as
 I


had
 mentioned
 pertaining
 to
 broken


access
 or
 broken
 authentication,
 I


should
 say,
 session
 fixation,


non-expiring
 sessions,
 weak
 password


recovery,
 missing
 multi-factor


authentication,
 and
 brute-force
 gaps.
</details>

>> 接下来我会点击进入这些失效的访问控制问题，并随机挑一个。注意，这些问题与 SonarQube 扫描出的所有其他问题都显示在同一个问题列表中，因此你无需跳转到新控制台去查看和检查它们。现在我点击进入失效的访问控制。

<details>
<summary>Original English</summary>
So,
 I'll
 go
 ahead
 and
 click
 into
 these


broken
 access
 control
 and
 I'll
 pick
 an


issue
 at
 random.
 Note
 that
 these
 surface


in
 the
 same
 issues
 list
 as
 every
 other


issue
 that's
 scanned
 by
 SonarQube,
 so


you
 don't
 have
 to
 navigate
 to
 a
 new


dashboard
 to
 surface


um
 and
 inspect
 all
 of
 these.
 So,
 I'll
 go


ahead
 and
 click
 into
 broken
 access


control.
</details>

>> 你可以在最上方看到一个被评定为高严重程度的问题。所有问题都打上了 Hunter Agent 的标签，因为它是最初用来发现它们的 AI 智能体，同时也标明了它所属的问题类别。

<details>
<summary>Original English</summary>
You
 can
 see
 at
 the
 very
 top
 we
 have
 a
 an


issue
 which
 has
 been
 rated
 high
 in


severity.


All
 of
 the
 issues
 are
 tagged
 with
 Hunter


Agent
 as
 this
 was
 the
 AI
 agent
 used
 to


surface
 them
 in
 the
 first
 place,
 and


then
 also
 the
 class
 of
 issue
 that
 it


pertains
 to
 as
 well.
</details>

>> 为了协助你修复这些问题，我们首先会向你展示该问题具体出现在你代码库中的什么位置，并提供关于为什么这是一个问题的说明。比如在这个例子中，正如你所见，问题在于任何已登录的用户都可以通过管理员访问检查，因为他们可以写入自己的角色字段。因此，我们基本上会向你阐明为什么这是个问题，并指出你该如何着手去修复它。此外还包括与当前问题相关的任何活动记录，并且你可以像处理其他 SonarQube 问题一样，将该问题指派给你选择的开发者。

<details>
<summary>Original English</summary>
In
 trying
 to
 help
 you
 remediate
 these


issues,
 we
 first
 show
 you
 where


specifically
 within
 your
 code
 base
 the


issue
 has
 surfaced,


as
 well
 as
 providing
 an
 explanation
 as


to
 why
 this
 is
 an
 issue.
 So,
 in
 this


instance,
 as
 you
 can
 see,
 the
 issue


pertains
 to
 any
 signed-in
 user
 being


able
 to
 pass
 the
 admin
 access
 check


because
 they
 can
 write
 their
 own
 role


field.
 So,
 you
 we
 walk
 you
 through


basically
 why
 this
 is
 an
 issue
 and
 then


also
 point
 you
 to
 how
 you
 can
 go
 about


fixing
 it
 as
 well.


Any
 activity
 as
 well
 related
 to
 the


issue
 at
 hand,
 and
 you
 can
 assign
 the


issue
 like
 you
 can
 any
 other
 SonarQube


issue
 to
 the
 developers
 of
 your


choosing.
</details>

>> 默认情况下，所有未解决的问题都处于开启状态，你可以选择：
- **接受该问题（Accept）**：意味着它确实有效，不是误报，但它不会影响你的质量门禁，因此不会阻止你尝试交付的代码进入生产环境。
- **确认该问题（Confirm）**：意味着该问题有效，且确实会对质量门禁产生影响。
- **标记为误报（False positive）**：如果你确实认为该修复或判定是不正确的。

<details>
<summary>Original English</summary>
All
 issues
 um
 open
 uh


are
 uh
 started
 in
 an
 open
 state
 by


default,
 and
 you
 can
 either
 accept
 the


issue,
 meaning
 that
 it
 is
 indeed
 valid,


it's
 not
 a
 false
 positive,
 but
 it
 will


not
 affect
 your
 quality
 gates,
 and


therefore
 it
 will
 not
 prevent
 the
 code


you're
 trying
 to
 ship
 from
 entering
 uh


production.
 You
 can
 confirm
 it,
 meaning


that
 the
 issue
 is
 valid
 and
 it
 will
 will


fact
 have
 an
 impact
 on
 the
 quality
 gate


or
 you
 can
 mark
 it
 as
 a
 false
 positive


if
 you
 really
 and
 truly
 believe
 that
 the


fix
 is
 incorrect.
</details>

>> 那么返回到我们之前执行的扫描中。我们还有 5 个业务逻辑方面的发现，以及一些身份验证和会话方面的发现。为了拓展了解，我也点击进入其中一个看看。你可以看到，在最上方我们有另一个高严重程度的安全漏洞。这个漏洞是指：任何仅拥有账户密码的用户，无需完成多因素认证即可访问包括管理员功能在内的每一个受保护路由。同样地，我们会为你指出该问题存在于你代码中的什么位置、为什么它是一个问题、你可以如何修复它，以及与它相关的任何活动记录。

<details>
<summary>Original English</summary>
So,
 navigate
 back
 to
 the
 scan
 that
 we


had
 conducted.


We
 have
 also
 uh
 five
 business
 logic


findings
 and
 a
 number
 of
 authentication


and
 session
 findings
 as
 well.
 I'll
 go


ahead
 and
 click
 into
 one
 of
 these
 just


for
 more
 breadth.


You
 can
 see
 here
 at
 the
 very
 top,
 we


have
 another
 high
 severity
 security


vulnerability.
 This
 one
 pertaining
 to


any
 user
 with
 only
 an
 account
 password


being
 able
 to
 reach
 every
 protected


route
 including
 admin
 functions
 without


completing
 multi-factor
 authentication.


Again,
 we
 point
 you
 to
 where
 in
 your


code
 the
 issue
 resides
 as
 well
 as
 why


it's
 an
 issue,
 how
 you
 can
 fix
 the


issue,
 and
 then
 again,
 any
 activity


related
 to
 it.
</details>

### 定时扫描与自动化修复

>> 需要注意的是，虽然 Hunter Agent 可以按需运行，但它也可以按计划定时运行。如果我在这里导航到 Hunter Agent，我可以配置定时扫描，按我选择的频率来运行，它的可配置性非常高，无论是每日、每周还是每月都可以。如果我不想专门扫描主分支，我还可以选择一个特定分支。在本例中，我扫描的是主分支。

<details>
<summary>Original English</summary>
Note
 that
 while
 the
 Hunter
 Agent
 can
 be


run
 on
 demand,
 it
 can
 also
 be
 run
 on
 a


scheduled
 basis.


So,
 if
 I
 navigate
 here
 to
 Hunter
 Agent,


I
 can
 configure
 a
 scheduled
 scan


whereby
 I
 can
 run
 it
 at
 the
 frequency
 of


my
 choosing.
 It's
 highly
 configurable.


Uh
 be
 that
 daily


or
 weekly
 or
 monthly.
 And
 I
 can
 also


select
 a
 specific
 branch
 should
 I
 not


want
 to
 scan
 the
 main
 branch


specifically.
 [snorts]


This
 case,
 I
 scanned
 the
 main
 branch.
</details>

>> 简而言之，这就是 Hunter Agent。在为你指出这些业务逻辑层面的漏洞类别时，我们会建议修复方案；但我非常高兴地宣布，从本周起，这些问题也能够以自动化的方式得到修复。值得一提的是，你实际上可以将这些问题指派给 SonarQube 修复智能体（remediation agent），它能够为你处理这类安全问题的修复工作，同样也可以按计划定时执行。

<details>
<summary>Original English</summary>
And
 that
 is
 Hunter
 Agent
 in
 a
 nutshell.


In
 pointing
 you
 towards
 these
 classes
 of


business
 logic
 level
 vulnerabilities,
 we


suggest
 fixes,
 but
 I
 am
 excited
 to


announce
 that
 as
 of
 this
 week
 these


issues
 will
 also
 be
 able
 to
 be
 fixed
 in


a
 remediated
 or
 in
 a
 automatic
 fashion.


I
 should
 note.


You
 can
 in
 fact
 assign
 these
 issues
 to


the
 SonarQube
 remediation
 agent
 which


can
 take
 care
 of
 remediating
 these


classes
 of
 security
 issues
 for
 you
 and


also
 on
 a
 scheduled
 basis.
</details>

>> 这就是 SonarQube Hunter Agent，它将使你能够在其他人之前捕获逻辑层面的漏洞，从而使你能够在自己沦为猎物之前主动猎捕问题。非常感谢大家。

<details>
<summary>Original English</summary>
And
 that
 is
 SonarQube
 Hunter
 Agent
 which


will
 enable
 you
 to
 catch
 logic
 level


vulnerabilities


before
 anybody
 else
 does
 so
 that
 you
 can


hunt
 for
 issues
 before
 you
 yourself
 are


hunted.
 Thank
 you
 very
 much.
</details>