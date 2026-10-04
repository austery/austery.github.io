---
author: AI Engineer
date: '2026-04-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wjk0ulMAkbc
speaker: AI Engineer
tags:
  - ai
  - software-quality
  - product-engineering
  - user-experience
title: AI 时代下的软件工程：质量、品味与未来工程师的转型
summary: 本期访谈深入探讨了 AI 技术对软件开发带来的颠覆性影响。与会者讨论了过度追求速度可能导致的产品质量下降，并强调了 **Linear** 公司通过“**质量星期三**”和“**零缺陷策略**”来维持高品质软件的实践。访谈还触及了 AI 在理解用户体验和“品味”上的局限性，并展望了未来软件工程师将更加侧重产品思维和客户导向的转型。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Tuomas Artman
  - Gergely Orosz
companies_orgs:
  - Linear
  - Uber
  - OpenAI
products_models:
  - Cloud Code
  - Opus 4.5
media_books:
  - Apple's Human Interface Guidelines
status: evergreen
---
### AI 趋势与软件质量的权衡

**Gergely Orosz**: 好的。所以，我们没有看到，但请举手示意如果你使用 **Linear**，如果你听说过 Linear，以及如果你想使用 Linear。

<details>
<summary>Original English</summary>

**Gergely Orosz**: Awesome.


So,
 we
 didn't
 see
 it,
 but
 hands
 up
 if


you
 do
 use
 linear
 and
 hands
 up
 if
 you


heard
 of
 linear
 and
 hands
 up
 if
 you
 want


to
 use
 linear.

</details>

**Tuomas Artman**: 太棒了，很高兴看到。我们可能会谈论 Linear，但我们要谈论一些更大的事情，这是一个有点新的趋势，**Thomas**，我们正在谈论事情正朝着错误的方向发展，对吧？什么正朝着错误的方向发展？

<details>
<summary>Original English</summary>

**Tuomas Artman**: Awesome. Great
 to
 see.
 So
 we're
 we
 could


be
 talking
 about
 linear
 but
 we're
 gonna


talk
 about
 something
 a
 bit
 bigger
 which


is
 a
 bit
 of
 a
 new
 trend
 that
 with
 Thomas


we're
 talking
 about
 things
 are
 trending


the
 wrong
 way
 right
 now.
 What
 is


trending
 the
 wrong
 way?

</details>

**Tuomas Artman**: 当代理人 um 能够立即为你做一切事情时，会发生什么？事实可能是，就像钟摆已经摆得太远，朝着错误的方向，即如果你收到一个功能请求，你可能现在就处于立即交付它的位置，而这可能就是错的。我估计，希望从现在起半年或一年后，我们会明白，在没有真正思考的情况下就交付东西是 um，是一件坏事。 um，将会发生的是，um，你因为拥有这种巨大的力量，可以有效地只是，就像，交付每一个进来的请求，或者你脑海中闪过的每一个想法，你将有效地交付 um，一个不那么出色的软件。 um，**史蒂夫·乔布斯**（**Steve Jobs**）曾经说过，你知道，伟大的产品来自于对 999 件事说“不”，而对一件事说“是”。而有了 AI um，我们可能处于一个很容易就说“是”并尝试各种事情然后交付它的地方，并最终到达一个非常复杂的地方，在那里软件实际上对最终客户来说 um，不再那么好用了，或者用户体验变得令人困惑。

<details>
<summary>Original English</summary>

**Tuomas Artman**: The


so


what
 happens
 when
 when
 agents
 um
 are


capable
 of
 doing
 everything
 um


immediately
 for
 you?
 uh
 the
 the
 fact


that
 might
 be
 that
 like
 the
 pendulum
 has


swung
 too
 far
 into
 the
 into
 the
 wrong


direction
 where
 if
 you
 get
 a
 feature


request
 you
 might
 now
 be
 in
 the
 position


to
 just
 immediately
 ship
 it
 and
 that


might
 be
 the
 wrong
 thing
 to
 do.
 Um
 and
 I


I
 reckon
 that
 you
 know
 hopefully
 half
 a


year
 from
 now
 or
 a
 year
 from
 now
 we'll


understand
 that
 like
 shipping
 things
 uh


without
 really
 too
 much
 thinking
 is
 um


is
 a
 bad
 thing.
 Um
 what
 will
 happen
 is


is
 that
 um
 you
 because
 you
 have
 this


this
 enormous
 power
 of
 effectively
 just


like
 shipping
 every
 single
 request
 that


comes
 in
 or
 every
 single
 thing
 thing


that
 pops
 into
 your
 head
 uh
 you
 will


effectively
 ship
 you
 know
 a
 software


that
 that
 is
 not
 great.
 Um
 Steve


Jobs
 back
 in
 the
 day
 said
 that
 you
 know
 great


products
 come
 out
 of
 saying
 no
 um
 to
 you


know
 999
 things
 and
 yes
 to
 one
 thing
 and


with
 AI
 um
 we
 might
 be
 in
 a
 place
 where


um
 it's
 just
 too
 easy
 to
 say
 yes
 and
 and


try
 things
 out
 and
 ship
 it
 and
 get
 to
 a


very
 convoluted
 place
 where
 you
 know


software
 actually
 doesn't
 work
 for
 the


end
 customer
 um
 nicely
 anymore
 or
 that


the
 user
 experience
 get
 gets
 confusing.

</details>

**Tuomas Artman**: 我们过去曾有一个 um，一个阻碍我们这样做的东西，那就是实际的工程曾经是困难的。所以我们曾经会去思考这些功能以及我们想要构建的应用程序，然后才开始工程，因为工程曾是如此耗时。

<details>
<summary>Original English</summary>

**Tuomas Artman**: We
 used
 to
 previously
 have
 um
 this
 you


know
 uh
 this
 thing
 that
 gated
 us
 from


from
 doing
 this
 which
 was
 like
 the


actual
 engineering
 used
 to
 be
 hard.
 So


we
 used
 to
 think
 about
 these
 these


features
 and
 these
 these
 you
 know
 um
 the


the
 applications
 that
 we
 wanted
 to
 build


before
 we
 actually
 started
 engineering


because
 engineering
 was
 such
 a
 time
 you


know
 waste
 of
 time
 and
 it
 it
 took
 a
 long


time
 to
 ship
 something.
 So
 um
 yeah
 that

</details>

**Gergely Orosz**: 但我想挑战你一下。在 AI 出现之前，我们难道没见过这种情况发生吗？一些公司就已经在发布大量功能并堆砌，你现在看到什么不同了吗？我们实际上看到越来越多的公司，你知道，做更多这种，我不知道，像功能拆分的事情吗？

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> but
 I
 want
 to
 challenge
 you
 a
 little
 bit


on
 that.
 Did
 we
 not
 see
 this
 happen


before
 before
 AI
 that
 some
 companies


were
 already
 just
 like
 shipping
 putting


on
 a
 bunch
 of
 features
 and
 stacking
 and


what
 are
 you
 seeing
 different
 right
 now?


Are
 you
 actually
 are
 we
 actually
 seeing


more
 companies
 you
 know
 do
 more
 of
 this


like
 I
 don't
 know
 like
 feature
 factoring


thing

</details>

**Tuomas Artman**: 我们曾在 **Uber** 有过一段共同的经历，我们一起工作过，你知道，我们经历过超高速增长 um，而 **Uber** 的事情是，这是一个“赢家通吃”的市场，你知道，当年 **Uber** 在美国和其他地方都在竞争，你必须不惜一切代价去大量交付 um，去超越竞争对手 um。而我在 **Uber** 看到的，就像是那样的超高速增长，我再也不想经历一次了，就像，不惜一切代价，你知道，只是在救火，维持基础设施运行，尽可能快地扩展，尝试一切，你知道，试图成为赢家 um。而我现在看到 AI 的类比，因为当每个人都拥有交付，你知道，大量功能的能力时，你总是在与别人竞争，你的竞争对手可能是一个小团队，甚至是一个非常能干的个人，他们能够利用 AI 来交付和 um，你知道，构建一个拥有与你相同功能集的产品。 um，而在那种世界里，我认为变得重要的是，你知道，以一种方式脱颖而出，即你构建有品味的软件，构建高质量的软件，从而，你知道，保持某种竞争优势。所以，在 **Linear**，即使在 AI 出现之前，你就在构建有品味的软件，专注于这些事情，但然后这些工具出现了，它们变得更强大，特别是自从 **Cloud Code** 出现以来，现在我们有了 **Opus 4.5**，你应该能够更快地交付，你的工程团队、你的 CTO、你的工程团队应该能够更快地交付。你告诉他们什么？你告诉他们应该在 Linear 里面做什么？他们应该放慢速度吗？不。对吧？Linear 里面到底发生了什么？告诉我们。

<details>
<summary>Original English</summary>

**Tuomas Artman**: we
 had
 a
 you
 know
 common
 experience
 at


Uber
 where
 we
 worked
 together
 where
 we


you
 know
 we
 we
 went
 through
 hyperrowth


um
 and
 the
 thing
 about
 Uber
 was
 that
 it


was
 a
 winner
 takes
 it
 all
 market
 and


Uber
 was
 going
 against
 back
 in
 the
 day


in
 the
 in
 the
 US
 and
 um
 you
 just
 had
 to


ship
 immensely
 um
 and
 and
 and
 you
 know


just
 outpace
 you
 know
 the
 competition
 um


at
 all
 costs.
 Um
 and
 what
 I
 saw
 at
 Uber


like
 was
 was
 that
 hyperrowth
 that
 I


never
 want
 to
 go
 through
 again
 which
 was


like
 um
 at
 all
 costs
 you
 know
 just


fighting
 fires
 keeping
 the


infrastructure
 running
 scaling
 as


quickly
 as
 possible
 trying
 out


everything
 and
 and
 you
 know
 trying
 to


come
 out
 you
 know
 as
 a
 winner
 um
 in
 in


in
 that
 front
 and
 I
 I
 I
 see
 the
 analogy


to
 to
 AI
 nowadays
 because
 when
 everybody


has
 the
 capability
 of
 shipping
 you
 know


tons
 of
 functionalities
 like
 you
 you


always
 are
 in
 a
 competition
 with
 with


somebody
 else
 like
 your
 competition


might
 be
 you
 know
 a
 small
 team
 or
 even


one
 person
 that
 you
 know
 is
 very
 capable


of
 using
 AI
 to
 to to
 ship
 and
 um
 you


know
 build
 a
 product
 that
 is
 you
 know


has
 the
 same
 feature
 set
 as
 as
 as
 you


do.
 Um
 and
 in
 that
 world
 like
 I
 I
 think


it
 becomes
 important
 to
 sort
 of
 you
 know


stand
 out
 um
 in
 a
 way
 where
 like
 you


build
 tasteful
 software
 and
 where
 you


build
 high
 quality
 software
 um
 and
 thus


sort
 of
 you
 know
 maintain
 some
 sort
 of


you
 know
 competitive
 advantage
 um


towards
 your
 your
 uh
 competition.
 So
 at


linear
 even
 before
 AI
 came
 out
 you
 were


building
 tasteful
 software
 and
 and
 and


focusing
 on
 those
 things
 but
 then
 these


tools
 came
 out
 and
 they
 became
 more


powerful
 specifically
 since
 cloud
 code


came
 out
 now
 we
 have
 Opus
 4.5


you
 should
 be
 able
 to
 ship
 faster
 your


engineering
 team
 your
 CTO
 your


engineering
 team
 should
 be
 able
 to
 ship


a
 lot
 faster
 what
 are
 you
 telling
 them


like
 what
 should
 they
 be
 doing
 inside
 of


linear
 with
 this
 capability
 should
 they


be
 slowing
 down.
 No.
 Right.
 What's
 going


on
 inside
 a
 line of
 linear?
 Tell
 us.

</details>

**Tuomas Artman**: 嗯，有，也有没有。我们仍然，你知道，我们仍然会考虑 um，我们推出的每一个功能，就像我们不会走仅仅尝试原型的路线。我们希望保持我们的设计角度，并且，你知道，考虑用户体验。仍然对大量的 um 客户请求说“不”。你知道，很多时间并没有花在实际的工程上。 um，它更多的是弄清楚客户想要什么。我们确实收到了大量的，你知道，功能请求。我们通常不会直接交付它们。我们真正想做的是，嗯，从我们的客户那里获得大量反馈，与我们的客户交谈，弄清楚他们实际的问题是什么，然后将它们归类，弄清楚，你知道，这些功能请求的根本原因到底是什么，然后想出一个解决方案，这个解决方案，嗯，对那一组特定的功能请求来说是完美的。 um，这需要时间。AI 可以帮助你，你知道，很多。当然，它可以，你知道，浏览所有这些请求并给你一个总结，也许可以，你知道，指向不同的分组。 um，但这仍然需要时间来弄清楚什么是正确的事情。 um，然后你进入设计，并且，并且，并且弄清楚，你知道，如何围绕你想要构建的功能来实现出色的用户体验？是的，我们想加快速度，我们也在加快速度。 um，产品建设的某些方面，你有，你知道，加速了很多。 um，例如修复 bug。 um，每个功能，嗯，每个产品都有 bug，而且，你知道，bug 的流入基本上是恒定的。 um，现在修复它们要容易得多。我，你知道，我们 10% 的 bug 是通过，你知道，一个单一的 AI 实例自动修复的，就像当一个 bug 进入 Linear 时，嗯，无论是来自，你知道，我们的工程师报告的，还是客户报告的问题，10% 都会自动，你知道，生成一个 PR 并自动合并，而无需工程师做任何事情。 um，随着时间的推移，这将会变得更多。我确实预见到一个未来，就像它会接近 100%。 um，在接下来的几年里。 um，所以这是你可以加速你构建的地方。将这些不需要太多思考或，你知道，设计专业知识或思考功能的任务，将它们交给代理人。你关心质量，你，你一直，让我们来谈谈 Cloud Code。你怎么看 Cloud Code？你觉得它安全吗？

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> Well,
 yes
 and
 no.
 Like
 we
 still,
 you


know,
 we
 we
 still
 think
 about
 um
 every


single
 feature
 that
 we
 put
 out
 like
 we


we
 don't
 we
 don't
 go
 down
 the
 route
 of


of
 just
 trying
 out
 prototypes.
 We
 want


to
 sort
 of
 maintain
 that
 design
 angle


that
 we
 have
 and
 and
 you
 know
 think


about
 the
 user
 experience.
 Still
 say
 no


to
 a
 lot
 of
 um
 customer
 requests.
 Like
 a


lot
 of
 time
 you
 know
 hasn't
 gone
 into


really
 just
 engineering.
 Um
 it's
 it's


about
 figuring
 out
 like
 what
 the


customer
 wants.
 uh
 we
 do
 get
 a
 ton
 of


you
 know
 feature
 requests.
 We
 usually


never
 ship
 them
 as
 such.
 Like
 what
 we


really
 want
 to
 do
 um
 is
 uh
 get
 a
 lot
 of


feedback
 from
 our
 customers,
 talk
 to
 our


customers,
 figure
 out
 what
 their
 actual


problem
 is
 and
 then
 sort
 of
 group
 that


together
 and
 figure
 out
 like
 you
 know


what
 is
 actually
 the
 root
 cause
 of
 of


you
 know
 these
 feature
 requests
 and
 then


come
 up
 with
 a
 solution
 that
 is
 um
 that


that
 is
 perfect
 for
 that
 you
 know


particular
 group
 of
 feature
 requests.


Um,
 and
 that
 takes
 time.
 Like
 AI
 can


help
 you,
 you
 know,
 so
 much.
 Obviously,


it
 can
 sort
 of,
 you
 know,
 go
 through
 all


of
 those
 requests
 and
 give
 you
 a
 summary


and
 maybe
 sort
 of
 point
 you
 to
 sort
 of,


you
 know,
 different
 groupings.
 Um,
 but


it
 still
 takes
 time
 to
 figure
 out
 what


the
 right
 thing
 is.
 Um,
 and
 then
 you
 go


into
 design
 and
 and
 and
 figure
 out
 like,


you
 know,
 h
 how
 do
 you
 implement
 a
 great


UX
 around
 uh
 the
 functioning
 that
 you


want
 to
 want
 to
 build?
 Yes,
 we
 want
 to


move
 faster
 and
 we
 are
 moving
 faster.
 Um


there's
 certain
 aspects
 of
 uh
 of
 you


know
 building
 a
 product
 that
 has
 you


know
 accelerated
 a
 lot.
 Um
 one
 is
 for


example
 fixing
 bugs.
 um
 every
 feature
 uh


every
 every
 product
 has
 bugs
 and
 you


know
 the
 inflows
 of
 bugs
 is
 effectively


constant
 and
 um
 those
 are
 much
 easier
 to


fix
 now
 like
 I
 you
 know
 10%
 of
 our
 bugs


are
 automatically
 fixed
 by
 you
 know
 a


singleshot
 AI
 instance
 like
 when
 a
 bug


comes
 in
 into
 linear
 um
 be
 it
 from
 sort


of
 you
 know
 our
 engineers
 uh
 reporting


those
 or
 a
 customer
 reporting
 a
 problem


10%
 are
 automatically
 you
 know
 up
 with
 a


PR
 and
 automatically
 landed
 without
 an


engineer
 doing
 anything
 um
 over
 time


that
 will
 go
 upline.
 I
 do
 foresee
 a


future
 where
 like
 it
 gets
 closer
 to


100%.
 Um
 in
 the
 next
 few
 years
 um
 so


that's
 something
 where
 you
 can


accelerate
 your
 your
 building
 like
 hand


off
 you
 know
 these
 tasks
 that
 don't


really
 require
 much
 thinking
 or
 you
 know


design
 expertise
 or
 thinking
 about


functionality
 hand
 that
 off
 to
 agents


you
 care
 about
 quality
 and
 you
 you
 can


tell
 the
 linear
 and
 and
 you
 have
 always


always
 had
 let's
 talk
 about
 cloth


code.
 What
 do
 you
 think
 about
 cloud


code?
 And


you
 can
 you
 can
 it's
 it's it's
 a
 safe


space.

</details>

**Tuomas Artman**: 是的，希望它是一个安全空间。 um，**Anthropic** 说，你知道，**Cloud Code** 的所有功能都是由 **Claude** 编码的。 um，我认为这表明，如果你真正使用，你知道，**Cloud Code**，无论是 CLI 还是桌面应用程序，你都可以发现问题和，你知道，小的，你知道，小的 bug。我，我会说，实际上并没有多少，你知道，只是质量修复，但它们实际上是 bug，嗯，在几秒钟内。 um，它有点，你知道，慢。它可能，你知道，运行的方式让你，你没有真正看到。对我来说，那是一种 um，由于移动速度太快而产生的副作用。就像他们再次，他们在与 **OpenAI** 竞争，而且 um，他们需要交付功能，他们需要非常快速地移动，因为这可能是一个更好的赢家通吃市场。 um，而副作用是，质量就是，你知道，不存在。

<details>
<summary>Original English</summary>

**Tuomas Artman**: Yeah,
 hopefully
 it's
 a
 safe
 space.
 Um,


Anthropic
 said,
 you
 know,
 that
 all
 of


the
 functionality
 has
 been
 has
 been
 in


cloud
 code
 has
 been
 coded
 by
 claude.
 Um,


and
 I
 think
 it
 it
 shows
 like
 if
 you
 if


if
 you
 truly
 use
 you
 know
 cloud
 code


either
 the
 CLI
 or
 or
 then
 the
 desktop


application
 um
 you
 can
 spot
 problems
 and


you
 know
 small
 sort
 of
 you
 know


small
 bugs.
 I
 I
 would
 say
 there's


there's
 not
 really,
 you
 know,
 just


quality
 fixes,
 but
 they're
 actually
 bugs


um
 in
 in
 effectively
 a
 few
 seconds.
 Um


it
 is
 a
 bit,
 you
 know,
 slow.
 It
 might


be,
 you
 know,
 functioning
 in
 a
 way
 that


you
 you
 don't
 you
 don't
 really
 really


see.
 And
 to
 me,
 that's
 sort
 of
 a
 um
 a


side
 effect
 of
 moving
 so
 fast.
 Like


obviously
 they
 they
 again
 they're
 in
 a


competition
 with,
 you
 know,
 Open
 AI
 and


um
 they
 need
 to
 ship
 features
 and
 they


need
 to
 sort
 of
 move
 move
 really
 quickly


uh
 because
 it
 might
 be
 a
 better
 takes


all
 market
 again.
 Um,
 and
 uh,
 the
 side


effect
 of
 that
 is
 that
 the
 quality
 just,


you
 know,
 isn't
 there.

</details>

**Gergely Orosz**: 是的。嗯，这并不是一个很棒的收购宣传，所以我认为你不会成功的。但是，嗯，我绝对喜欢，你可以看到这些东西中的一些，但质量如何衡量？我们之前也谈过，嗯，就在我们开始谈论 **Uber** 之前，我们如何尝试衡量质量，以及那如何影响你学习关于它的可衡量之处以及不可衡量之处。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> Yeah.
 Well,
 this
 was
 not
 a
 great


acquisition
 pitch,
 so
 I
 I
 don't
 think


you're
 you're
 going
 to
 get
 there.
 But,


uh,
 I
 absolutely
 like
 you
 you
 can
 see


some
 of
 these
 things,
 but
 how
 do
 you


measure
 quality?


And
 we've
 talked
 about
 this
 before
 uh


just
 be
 just
 before
 we
 started
 on
 Uber


how
 we
 tried
 to
 measure
 quality
 and
 and


how
 that's
 influence
 you
 to
 learn
 what


you
 can
 measure
 about
 it
 and
 what
 you


cannot.

</details>

**Tuomas Artman**: **Uber** 是一个很好的例子，说明了衡量质量是多么地困难，因此你就不去衡量。 um **Uber** 作为一个例子，就像我们有，你知道，这五个主要指标，每个人都在关注和改进。 um，最重要的是收入，就像，它本质上是一个交易性的，你知道，应用程序。 um，你产生的收入越多，就越好。

<details>
<summary>Original English</summary>

**Tuomas Artman**: Uber
 is
 a
 good
 example
 of
 like
 where
 it


is
 immensely
 hard
 to
 measure
 quality
 and


therefore
 you
 sort
 of
 don't.
 Um
 Uber
 as


an
 example
 like
 we
 had
 you
 know
 these


five
 big
 metrics
 um
 that
 everybody
 was


looking
 looking
 after
 and
 looking


looking
 to
 improve.
 Um
 the
 big
 one
 was


revenue
 like
 um
 it
 is
 effectively
 a


transactional
 you
 know
 application.
 Um


the
 more
 revenue
 you
 generate
 the
 the


better.
 So

</details>

**Gergely Orosz**: >> 其他的指标是，比如，完成的行程。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> the
 other
 ones
 were
 like
 trips
 taken

</details>

**Tuomas Artman**: >> 行程。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> trips
 taken

</details>

**Gergely Orosz**: >> 行程，行程。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> trip
 trip
 taken.

</details>

**Tuomas Artman**: >> 嗯。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> Uh

</details>

**Tuomas Artman**: >> 我认为行程的质量也是一个指标。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> I
 think
 the
 quality
 of
 the
 ride
 was
 was


one
 as
 well.

</details>

**Tuomas Artman**: >> 从注册到第一次行程的时间。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> It
 also
 time
 to
 first
 trip
 from
 from


sign
 up
 to
 the
 first
 time
 that

</details>

**Tuomas Artman**: >> 就是这样，我们有几个黄金指标。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> well
 that's
 so
 we
 had
 a
 few
 golden
 metrics

</details>

**Gergely Orosz**: >> 对，但收入那个是大家关注的。所以当你发布一个新功能 um，或者发布了完全新的东西，比如 Uber Pool，举个例子，我不知道哪个先来， Lyft Pool 还是 Uber Pool，我想 Uber 是先开始的，然后 Lyft 才跟上，但是 um，显然如果你发布一个新功能，可以，你知道，降低一次行程的价格，它会增加你的收入，所以你怎么衡量质量呢？你根本就衡量不了。 um，如果，如果没有任何其他平台提供便宜的拼车服务，那么你就不需要质量。 um，而且这就是，你知道，我一直以来的感受。在 **ED**，就像，我们有工程师，至少在初期，他们关心质量。 um，这是我们的责任，去弄清楚我们发布的某样东西是否出色。我仍然记得我 2012 年加入的时候，我想。 um，我提交了一个 PR，在那时，**Uber** 应用程序在屏幕中间有一个圆圈，显示行程即将到达的预计到达时间。我改变了地图的边距。 um，然后一个 OG 工程师回复了我的 PR，他是，你知道，从一开始就在团队里。我想他是第一个 iOS 工程师。 um，他说：“哦，这个圆圈差了两个像素。”我当时说：“你测量过吗？”“哦，当然，我测量过了。”然后我说：“我再量一次。”你知道，是的，差了两个像素。所以我不得不把它向上移动一个像素。没有人会真的在意。没有人会注意到，但人们热衷于维护质量。这也是为什么至少在早期，**Uber** 应用程序性能很好，质量很高。 um，但然后，一旦你有一个足够大的团队，并且你有这些 um 增加收入的激励措施 um，你就会尽快发布新功能，而质量是不会影响你收入的东西，直到它开始影响。所以会发生什么？ **Uber** 发布了 **Uber Pool**，**Lyft** 也跟着发布了 **Lyft Pool**。所以你有两个竞争产品，价格相同，功能相同。 um，你可以选择其中一个应用程序，随着时间的推移，就像，我的理论，这就是为什么我们想把 Linear 打造成一个高质量的工具，是因为随着时间的推移，人们会选择质量更高的那个。 um，这可能需要一段时间，就像，人们可能仍然使用 **Uber**，然后每年尝试一下 **Lyft**，比如一年一次，或者什么的，打开它，然后想，哦，这个用户体验感觉好多了，我感觉我能更快地叫到车，即使价格和他们销售的产品是一样的。所以随着时间的推移，你就会开始失去用户。 um，这将是一个渐进的滑坡。不会有 AB 测试可以让你弄清楚是否应该投资质量。 um，这只会随着时间的推移而发生。这就是它的危险所在。 um，如果你构建了一个质量差的产品，你就给自己打开了被竞争对手超越的门户。 um，嗯，不是被超越，而是被竞争对手慢慢超越。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> right
 but
 the
 the
 revenue
 one
 was
 what


everybody
 everybody
 looked
 after.
 So


when
 you
 shipped
 a
 new
 feature
 um
 or


shipped
 you
 know
 something
 totally
 new


like
 you
 know
 Uber
 pool
 for
 example
 um
 I


don't
 know
 which
 one
 came
 first
 lift


pool
 or
 Uber
 poolool
 I
 think
 Uber


started
 it
 and
 then
 lift
 came
 around
 but


um
 obviously
 if
 you
 ship
 a
 new
 feature


that
 sort
 of
 you
 know
 makes
 the
 price


you
 know
 of
 a
 of
 taking
 a
 trip
 lower
 it


will
 increase
 your
 revenue
 so
 how
 do
 you


measure
 quality
 in
 that
 like
 you
 you


simply
 don't
 um
 if
 if
 there's
 no
 other


way
 of
 you
 know
 if
 if
 there's
 no
 other


platform
 that
 provides
 you
 with
 uh
 with


with
 a
 pool
 drive
 that
 is
 inexpensive


then
 uh
 you
 you
 don't
 really
 need
 to


have
 quality.
 Um
 and
 that
 was
 you
 know


my
 my
 feeling
 throughout
 like
 at
 ED
 like


we
 had
 engineers
 that
 that
 cared
 at


least
 in
 the
 beginning
 we
 had
 engineers


that
 cared
 about
 quality
 like
 it
 was
 up


to
 us
 to
 figure
 out
 like
 whether


something
 we
 shipped
 was
 was
 great
 or


not.
 I
 I
 still
 remember
 when
 I
 joined
 in


2012,
 I
 think.
 Um
 I
 put
 up
 a
 first
 PR


and
 back
 back
 then
 the
 Ubra
 application


used
 to
 have
 this
 this
 poll
 in
 the


middle
 of
 of
 the
 screen
 that
 used
 to


have
 an
 ETA
 of
 like
 when
 when
 your
 trip


is,
 you
 know,
 is
 is
 is
 going
 to
 arrive.


And
 I
 made
 some
 changes
 to
 the
 margins


of
 the
 of
 the
 map.
 Um
 and
 the
 PR
 came


back
 from
 a
 from
 an
 OG
 engineer
 who
 was,


you
 know,
 was
 on
 the
 team
 for
 from
 from


the
 get-go.
 I
 think
 he
 was
 the
 first
 iOS


engineer.
 Um
 and
 he
 he
 was
 like,
 "Oh,


this
 this
 pole
 is
 off
 by
 two
 pixels."
 I


was
 like,
 "You
 you
 measured
 it?"
 "Oh,


yeah,
 sure.
 I
 I
 measured
 it."
 And
 I
 was


like, "I
 measured
 again."
 And
 you
 know,


yes,
 two
 pixels
 off.
 So,
 I
 had
 to
 move


it
 up
 by
 one
 pixel.
 And
 that
 was
 the


like
 nobody
 would
 would
 really
 care.


Nobody
 would
 see
 it,
 but
 like
 people


were
 keen
 on
 upholding
 the
 quality.
 And


that's
 why
 at least
 in
 the
 beginning,


the
 Uber
 application
 was
 was
 pretty


performant,
 was
 was
 of
 highest
 quality.


Um
 but
 then
 like
 once
 you
 have
 a
 big


enough
 team
 and
 you've
 got
 these
 um


incentives
 of
 just
 increasing
 revenue
 um


you
 ship
 new
 features
 as
 as
 quickly
 as


possible
 and
 and
 quality
 is
 a
 thing
 that


like
 it
 it
 doesn't
 affect
 your
 revenue


until
 it
 does.
 So
 what
 happens
 Uber


ships
 Uber
 pool
 lift
 comes
 ahead
 and


ships
 Uber
 uh
 you
 know
 Lyft
 pool
 as


well.
 So
 you've
 got
 two
 competing


products
 that
 effectively
 have
 the
 same


price
 point
 do
 the
 same
 thing.
 um
 you


can
 choose
 either
 one
 of
 the


applications
 and
 over
 time
 like
 my


theory
 and
 and
 that's
 why
 we
 we
 you
 know


want
 to
 build
 linear
 into
 this
 high


quality
 tool
 uh
 is
 that
 over
 time
 people


will
 will
 pick
 the
 one
 that
 is
 of
 higher


quality
 um
 it
 might
 take
 a
 while
 like


people
 might
 be
 you
 know
 sticking
 to


Uber
 and
 then
 trying
 out
 lift
 you
 know


once
 a
 year
 or
 something
 like
 opening
 it


up
 mean
 like
 oh
 this
 user
 experience


actually
 feels
 better
 I
 I I
 feel
 like


I'm
 getting
 the
 car
 faster
 um
 even


though
 the
 price
 and
 the
 product
 that


they
 sell
 is
 is
 the
 same.
 So
 over
 time


you
 will
 start
 losing
 your
 users.
 Um
 and


it
 will
 be
 a
 gradual
 you
 know
 slip.


There
 there
 will
 be
 no
 AB
 test
 that
 you


can
 do
 in
 order
 to
 figure
 out
 like


whether
 you
 should
 invest
 in
 quality.
 Um


it'll
 just
 happen
 over
 time.
 And
 that's


that's
 the
 danger
 of
 it.
 Um
 if
 you
 if


you
 build
 a
 bad
 quality
 product,
 you


open
 up
 yourselves
 uh
 to
 uh
 sort
 of
 be


leaprocked
 by
 by
 a
 competition.
 Um
 well


not
 leaprocked
 like
 slowly
 overtaken
 by


the
 competition.

</details>

**Gergely Orosz**: 你在 **Linear** 做了一些非常独特的事情，我以前从未见过。它叫做“**质量星期三**”（Quality Wednesdays），我参加过一次你们的“质量星期三”。整个工程团队聚集在一起，这是一个全远程团队。所以每个人都接入，持续了 30 分钟，我记得大约有 25 位工程师在那次通话中，每个人展示一个他们完成的质量修复。从一个像素的改变开始，真的是一个像素的改变，到“哦，我让我们的后端效率大大提高，并且使用了更少的东西”，就这样，砰砰砰砰砰。 um，我想 25 个人花了大约 37 分钟，但不到两分钟。这怎么开始的？是你吗？

<details>
<summary>Original English</summary>

**Gergely Orosz**: you
 do
 something
 really
 unique
 at
 linear


related
 to
 this
 that
 I've
 never
 seen


before.
 It's
 called
 quality
 Wednesdays


and
 I
 sat
 into
 one
 of
 your
 quality


Wednesdays.
 The
 whole
 engineering
 team


gets
 together.
 It's
 a
 full
 remote
 team.


So
 everyone
 just
 dials
 in
 and
 it
 was
 30


minutes
 and
 every
 engineer
 I
 think
 we


had
 about
 25
 engineers
 on
 that
 call


would
 show
 one
 fix
 that
 they
 did
 was


quality
 and
 it
 went
 from
 like
 a
 one


pixel
 change.
 It
 was
 literally
 a
 one


pixel
 to
 uh
 oh
 I
 just
 made
 our
 our
 our


back
 end
 like
 way
 more
 efficient
 and
 and


using
 less
 things
 and
 it
 was
 just
 boom


boom
 boom
 boom
 boom.
 Uh
 and
 I
 think
 it


took
 like
 37
 minutes
 for
 the
 25
 people


but
 it
 was
 less
 than
 two
 minutes.
 How


did
 this
 start?


And
 was
 this
 you?

</details>

**Tuomas Artman**: 是我。是的，绝对。 um，主要原因，就像，我想回到，我想大概是三四年前。 um，我们在应用程序中有一个东西，就像，如果你使用它，你可以，你可以，你可以注意到它，就像每一个高亮都需要在你悬停在上面时立即高亮，因为你知道，这让应用程序感觉很快，但是当你移开时，按钮需要有一个非常快速的淡出，因为这会让应用程序感觉很流畅，就像它必须是，你知道，瞬间高亮，然后 150 毫秒后，你知道，淡出，因为这为用户交互增加了一点质量。 um，而且这 desde，你知道，一开始就存在了。 um，然后我有点沮丧，因为我不得不，你知道，向工程师指出这一点，因为如果你不寻找那种非常微小、细致的细节，你就是找不到。就像你实现了一个新功能，然后 um，你只是忘记了 um，你知道，实现它，或者如果你不知道你在寻找什么，你甚至都看不到它。所以，在我的一次户外活动中，因为我厌倦了报告这些，我说，让我给大家展示一下，你知道，他们应该做什么， um，以及他们应该如何实现这些，你知道，小的质量修复。 um，我选择了应用程序的一小部分，我说，你知道，在那里我注意到高亮缺失了，你知道，我把团队召集起来，嗯，我告诉他们，让我们，你知道，花一个小时来弄清楚这个特定视图有什么问题，在我看来，就是信任高亮，大家也都加入进来了。 um，我们发现的是，在视图选项菜单中，我们发现了那个小 UI 的 35 个问题。 um，我当时想，天哪，天哪，天哪。 um，我没看到那些。 um，我完全不知道我们有这么多小问题，就像，当你不是真正关注的时候，你就不会注意到。 um，所以，从那时起，你知道，我所想的，我们想要做的，就是让每个人都始终参与进来，并且，并且，并且尝试在产品中找到问题，因为显然我们充满了，你知道，小的质量问题。如果，你知道，一个小菜单有 35 个东西要修复，那么应用程序的其余部分就有，你知道，数千个。迄今为止，我们可能已经修复了 um 2500 或 3000 个，嗯，这些小的、细致的细节， um，在应用程序中。 um，而且，你知道，这就是它变得更好，并且 um，并且拥有最高的质量标准的原因。 um，你知道，那就是它的开端。但然后我们意识到 um，这有一个很好的副作用。我们告诉大家的是，你必须，每个星期三，你必须自己找到一个问题，就像，我们不会把它们交给你，就像，你必须自己进入产品去找到它。所以人们开始这样做，每周都找到一个问题，一开始很容易，然后变得更难，因为你知道，质量修复减少了，但 um，你知道，人们一直在产品中找到问题。 um，其副作用是，大家，无论何时，当他们构建一个完全不相关的功能时，他们总是在寻找这些小的质量修复，因为他们知道他们必须带着一个修复来参加下一个星期三的会议。

<details>
<summary>Original English</summary>

**Tuomas Artman**: It
 was
 me.
 Yeah,
 for


sure.
 Um
 the
 the
 big
 one
 was
 like
 I
 mean


to
 go
 back
 like
 I
 think
 it
 was
 three


four
 years
 ago.
 Um
 we
 have
 this
 thing
 in


the
 application
 like
 if
 if
 you
 use
 it
 um


you
 can
 you
 can
 you
 can
 spot
 it
 like


every
 single
 highlight
 needs
 to


highlight
 instantaneously
 when
 you
 hover


over
 it
 because
 that
 you
 know
 makes
 the


application
 feel
 fast
 but
 when
 you
 hover


out
 there
 needs
 to
 be
 this
 very
 quick


fade
 out
 of
 of
 a
 button
 because
 that


makes
 the
 application
 feel
 smooth
 like


it
 has
 to
 be
 this
 like
 you
 know


instantaneous
 highlight
 and
 then
 over


150
 milliseconds
 you
 know
 fade
 out


because
 that
 adds
 a
 bit
 of
 quality
 um
 to


to
 the
 user
 interaction
 and
 um
 that
 was


in
 place
 since
 you
 know
 the
 beginning


like
 the
 the
 the
 early
 Um,
 and
 then
 I


got
 sort
 of
 frustrated
 because
 I
 had
 to


sort
 of
 point
 this
 out
 to
 to
 engineers


because
 if
 you're
 not
 looking
 for
 that


very
 small
 minute
 detail,
 you're
 just


not
 going
 to
 find
 it.
 Like
 you
 implement


new
 functionality
 and
 um
 you
 just
 forget


to
 uh
 you
 know
 implement
 it
 or
 you
 don't


even
 see
 it
 if
 you're
 not
 if
 you
 don't


know
 what
 you're
 looking
 out
 for.
 So


what
 I
 did
 as
 at
 one
 of
 our
 off
 sites


because
 I
 got
 frustrated
 of
 reporting


these
 I
 was
 like
 let
 me
 show
 everybody


like
 you
 know
 what
 what
 what
 they
 should


be
 doing
 um
 and
 and
 how
 they
 should
 be


implementing
 these
 these
 you
 know
 small


quality
 quality
 fixes.
 Um
 and
 what
 I


took
 is
 a
 very
 small
 portion
 of
 the


application
 and
 I
 was
 like
 you
 know


where
 where
 I
 noticed
 that
 you
 know
 the


highlights
 were
 missing
 and
 and
 you
 know


I
 brought
 the
 team
 together
 and
 uh
 I


told
 them
 let's
 you
 know
 spend
 an
 hour


trying
 to
 figure
 out
 what's
 wrong
 with


this
 particular
 view
 and
 in
 my
 mind
 it's


trust
 the
 highlights
 and
 everybody
 duck


in
 um
 and
 what
 we
 found
 in
 it
 was
 one
 of


the
 view
 option
 menus
 uh
 we
 found
 like


35
 problems
 with
 with
 that
 tiny
 UI
 um


and
 I
 was
 holy
 Holy,
 holy
 crap.
 Um,
 like


I
 I
 didn't
 see
 those.
 Um,
 I
 I
 had
 no


idea
 that
 we
 had
 all
 these
 small


problems
 that
 like
 you
 wouldn't
 notice


when
 you're
 when
 you're
 not
 really


looking.
 Um,
 so
 from
 that,
 you
 know,


what
 what
 I
 what
 I
 thought
 we
 we
 would,


you
 know,
 want
 to
 do
 is
 like
 have


everybody
 always
 chime
 in
 and
 and
 and


try
 to
 find
 problems
 in
 the
 product


because
 apparently
 we
 were
 full
 of,
 you


know,
 small
 quality
 quality
 problems.
 If


a,
 you
 know,
 small
 menu
 has
 35
 things
 to


fix,
 then
 the
 rest
 of
 the
 application


has,
 you
 know,
 thousands.
 And
 to
 date,


we've
 probably
 fixed
 um
 2,500
 or
 3,000


um
 of
 these
 small
 minute
 details
 uh
 in


the
 application.
 Um
 and
 and
 that's
 how,


you
 know,
 has
 become
 better
 and
 um
 and


and
 has
 the
 highest
 highest
 quality
 bar.


Um
 that
 was,
 you
 know,
 that
 was
 the


start
 of
 it.
 But
 then
 we
 realized
 um


there's
 there's
 a
 nice
 side
 effect
 to


this.
 And
 what
 we
 what
 we
 told
 people
 is


that
 you
 have
 to
 every
 Wednesday
 you


have
 to
 find
 a
 problem
 yourself
 like
 we


won't
 hand
 them
 to
 you
 like
 you
 have
 to


go
 in
 into
 the
 product
 and
 find
 it.
 So


people
 started
 doing
 that
 every
 single


week
 finding
 a
 problem
 and
 it
 used
 to
 be


um
 in
 the
 beginning
 it
 was
 it
 was
 easy


then
 it
 became
 harder
 because
 you
 know


the
 quality
 fixes
 went
 down
 but
 um
 you


know
 people
 kept
 on
 finding
 finding


problems
 in
 in
 the
 product.
 Um
 and
 the


the
 side
 effect
 of
 that
 was
 that


everybody
 was
 all
 but
 when
 whenever
 they


were
 building
 something
 a
 totally


unrelated
 feature
 there
 was
 they
 were


always
 on
 the
 lookout
 for
 these
 small


quality
 fixes
 because
 they
 knew
 they
 had


to
 come
 to
 the
 next
 Wednesday
 meeting


with
 a
 fix


</details>

**Tuomas Artman**: >> 去修复它们。是的。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> to
 get
 the
 fix
 them.
 Yeah.

</details>

**Tuomas Artman**: >> 是的。所以他们总是在寻找这些，这意味着他们引入的回归越来越少，或者这些，你知道，小的质量回归到产品中。所以，如果你一直在思考质量，并且你意识到了质量相关的事情，那么你一定会犯更少的错误。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> Yeah.
 So
 they
 were
 always
 looking


looking
 for
 those
 and
 that
 meant
 that


they
 were
 introducing
 less
 and
 less


regressions
 or
 these
 you
 know
 small


quality
 quality
 regressions
 into
 the


product
 anyway.
 So
 if
 you
 if
 you
 think


about
 quality
 all
 the
 time
 and
 if
 you


are
 aware
 um
 of
 quality
 you
 know
 things


then
 uh
 you're
 you're
 bound
 to
 make
 less


mistakes.

</details>

**Gergely Orosz**: 我觉得这个实践我到处都没见过，它既令人惊叹，又相当有雄心。所以，我的意思是，如果你是一个小型初创公司，你应该尝试一下，因为尤其是在现在，有了像这样的代理，这不应该太难做到，而且你可能会得到。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> I
 mean
 this
 practice
 is
 I
 haven't
 seen


it
 elsewhere
 and
 it
 seems
 both
 awesome


also
 pretty
 aspirational.
 So
 I
 mean
 if


you're
 a
 small
 startup
 like
 you
 should


probably
 try
 it
 out
 if
 you
 can
 because


especially
 now
 nowadays
 with
 with
 agents


like
 like
 it
 shouldn't
 be
 that
 difficult


to
 do
 and
 and
 you
 might
 get

</details>

**Tuomas Artman**: >> 如果你是一家大公司，你应该更应该尝试一下。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> if
 you're
 a
 big
 startup
 you
 should
 even


even
 more
 try
 it
 out.

</details>

**Tuomas Artman**: >> 好了。但有一件事不像那么有雄心，而且容易得多，特别是现在你已经做了，甚至在代理出现之前，就是“**零缺陷策略**”（zero bug policy）。告诉我这个。这对你来说，“零缺陷策略”意味着什么？在实践中意味着什么？比如，你们肯定有 bug，对吧？我只是扮演魔鬼代言人。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> There
 there
 we
 go.


But
 one
 thing
 that
 is
 is
 not
 as


aspirational
 and
 a
 lot
 easier
 to
 do


especially
 now
 that
 you
 have
 been
 doing


even
 before
 agents
 zero
 bug
 policy.
 Tell


me
 about
 this.
 What
 does
 zero
 bug
 policy


mean
 for
 you
 and
 what
 does
 it
 mean
 in


practice?
 Like
 you
 have
 bugs
 surely,


right?
 I'm
 just
 playing
 devil's
 advocate


here.

</details>

**Tuomas Artman**: 当然。 um，我们的“零缺陷策略”字面意思就是，如果一个 bug 被报告了，um，它会自动分配给某人，立即，显然使用代理。 um，他们会找到谁创建了这个 bug，或者你知道，谁一直在处理这个区域， um，这就会成为你的最高优先级。你放下其他所有事情。 um，早上醒来，你去你的“我的问题”列表，你看到一个分配给你的 bug。那是你要处理的第一件事，你修复它。或者你也可以选择不修复它。你知道，这很重要。不是每个 bug 都会被修复。如果它，你知道，超级困难或棘手，并且它，你知道，适用于十万分之一的用户， um，你知道，你可能不应该浪费时间。 um，但是每一个 bug 都会立即被修复。 um，这个策略的开始，嗯，来自于这样的想法：bug 是在每个公司以恒定的速率被创建的。当你创建功能，当你创建功能，当你进行工程时， um，你将会创建 bug。而大多数公司，在我们的“零缺陷策略”之前，我们 um，把它们放在一个待办事项列表中。我们说，嗯，你知道，当我们有时间的时候，我们会修复它们。 um，然后随着时间的推移，你的产品会变得越来越糟，在某个时刻你会看到，哦，我的天，我们有 500 个 bug 在待办事项列表里，我们需要做些什么。然后你才开始从顶部修复。而发生的是，嗯，修复 bug 的速率基本上是恒定的。无论你是现在修复，还是两个月后修复，都没有关系。一旦你达到了那个阈值，我们有这么多 bug，你实际上就是在修复所有进来的 bug，只是迟了两个月。所以，牢记这一点，你只需要做一个很小的权衡就能达到零 bug。如果修复 bug 的速率是恒定的，你所需要做的就是停止，你知道，新功能的开发，直到你把 bug 降到零，然后强制执行你将继续，你知道，修复你的 bug，因为立即修复 bug 比三个月后修复它需要更多的精力，如果你关心你问题的总体数量。所以，对我们来说，这意味着，我们花了相当于三周的时间，没有开发任何新功能，只是修复 bug，把它们降到零。 um，从那时起，每个 bug 都会在七天内被修复，通常你知道，在两个小时或三个小时内。 um，这对用户来说意味着，用户在报告 bug 时会非常兴奋，两个小时后他们会收到一封电子邮件，说哦，我们修好了。如果你刷新浏览器， um，我们已经为你解决了。 um，这会让你的用户非常高兴，因为你知道，你很少有这样的体验。

<details>
<summary>Original English</summary>

**Tuomas Artman**: Sure.
 Um
 we
 zero
 bug
 policy
 literally


means
 that
 if
 a
 bug
 gets
 reported
 um
 it


gets
 assigned
 to
 somebody
 automatically


immediately
 using
 agents
 obviously
 like


they
 will
 find
 who
 has
 created
 this
 bug


or
 who
 has
 you
 know
 been
 working
 in
 this


area
 and
 um
 that
 becomes
 your
 highest


priority.
 You
 drop
 everything
 else.
 Um


the
 morning
 you
 wake
 up
 you
 go
 to
 your


my
 issues
 list
 and
 you
 see
 a
 bug


assigned
 to
 you.
 That's
 the
 first
 thing


you
 pick
 up
 and
 you
 fix
 it.
 Or
 you
 can


also
 decide
 not
 to
 fix
 it.
 Like
 that's


important.
 like
 not
 every
 bug
 gets


fixed.
 If
 it's,
 you
 know,
 super
 hard
 or


gnarly
 and
 it,
 you
 know,
 applies
 to
 one


out
 of,
 you
 know,
 100,000
 users,
 um,
 you


know,
 you
 probably
 shouldn't
 waste
 your


time
 on
 it.
 Um,
 but
 every
 single
 bug


gets
 fixed
 immediately.
 And
 the
 the
 the


the
 start
 of
 this
 um
 came
 from
 from
 the


idea
 that
 like
 bugs
 are
 are
 are
 created


at
 a
 constant
 rate
 at
 every
 company.


When
 you
 create
 features,
 when
 you
 when


you
 create
 function,
 when
 you
 engineer,


um,
 you
 will
 be
 creating
 bugs.
 And
 most


of
 the
 companies
 and
 we
 prior
 to
 our


zero
 back
 policy
 like
 we
 um
 put
 them
 in


a
 backlog.
 We're
 like
 uh
 you
 know
 when


it
 gets
 when
 we
 get
 some
 time
 like
 we'll


we'll
 fix
 them.
 And
 uh
 what
 happens
 over


time
 is
 like
 your
 product
 gets
 worse
 and


worse
 and
 at
 some
 point
 you
 look
 like
 oh


man
 we've
 got
 you
 know
 500
 bugs
 in
 the


backlog
 like
 we
 need
 to
 do
 something


about
 it
 and
 that's
 when
 you
 start


fixing
 from
 the
 top


and
 what
 happens
 is
 that
 um
 the
 rate
 at


which
 you
 have
 to
 fix
 bugs
 is
 again


constant.
 It
 doesn't
 matter
 whether
 you


fix
 them,
 you
 know,
 two
 months
 from
 now


or
 immediately.
 Like
 once
 you
 hit
 that


threshold
 of
 we've
 got
 so
 many
 bugs,


you're
 now
 effectively
 fixing
 all
 the


bugs
 that
 come
 in
 um
 except
 two
 months


later.
 So
 with
 that
 small
 notion
 in


mind,
 like
 there's
 there's
 a
 very
 small


trade-off
 that
 you
 have
 to
 do
 in
 order


to
 get
 to
 zero
 bucks.
 If
 the
 rate
 that


you
 have
 to
 fix
 bugs
 is
 constant,
 all


you
 need
 to
 do
 is
 stop,
 you
 know,


development
 of
 new
 features
 for
 as
 long


as
 it
 takes
 you
 to,
 you
 know,
 bring
 your


bugs
 to
 zero
 and
 then
 enforce
 that


you're
 going
 to
 keep
 on,
 you
 know,


fixing
 your
 bugs
 because
 it's
 not
 more


effort
 to
 fix
 bugs
 immediately
 than
 to


fix
 them
 three
 months
 from
 now
 if
 you


care
 about
 the,
 you
 know,
 overall
 sum
 of


of
 of
 your
 of
 your
 problems.
 So
 to
 us


that
 meant
 um
 we
 spent
 effectively
 three


weeks
 of
 of
 not
 working
 on
 any
 any
 new


functionality
 of
 just
 fixing
 bugs


getting
 that
 down
 to
 zero.
 Um
 and
 from


there
 on
 out
 every
 bug
 gets
 fixed
 um


within
 seven
 days
 usually
 you
 know
 in


two
 hours
 or
 3
 hours.
 Um
 and
 what
 that


means
 to
 users
 like
 users
 get
 super


excited
 when
 they
 report
 a
 bug
 and
 two


hours
 later
 they
 get
 an
 email
 saying
 oh


we
 fixed
 it
 if
 you
 refresh
 your
 browser


um
 we've
 got
 it
 covered
 for
 you.
 um
 that


makes
 you
 like
 that
 makes
 your
 users


super
 happy
 because
 you
 know
 you
 don't


really
 have
 that
 experience
 too
 often


with
 with
 companies.

</details>

**Gergely Orosz**: 好的，一个刁钻的问题。如果我在 **Linear** 工作，有一个“**质量星期三**”要来了，然后我被分配了一个 bug，那算吗？

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> Okay,
 curve
 ball
 question.
 If
 I'm


working
 at
 linear
 and
 there's
 a
 quality


Wednesday
 coming
 up
 and
 I
 get
 assigned
 a


bug,
 does
 that
 count?

</details>

**Tuomas Artman**: 不，那不算。那是缺陷。 um，你必须找到一个质量修复。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> No,
 that
 does
 not
 count.
 That's
 that's
 a


defect.
 Um
 you
 have
 to
 find
 a
 quality


fix.

</details>

**Tuomas Artman**: >> 哦，天哪。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> Oh
 man,

</details>

**Tuomas Artman**: >> bugs
 are
 separate.
 They
 they
 are


immediately
 immediately
 created.
 And
 now


with
 you
 know
 AIS
 being
 capable
 of
 at


least
 pointing
 you
 where
 that
 problem
 is


and
 helping
 you
 immensely
 uh
 fix
 bugs
 I


think
 like
 literally
 every
 company
 um


should
 have
 a
 zero
 bug
 policy.
 It
 it


doesn't
 make
 sense
 to
 not
 have
 one.
 One


thing
 that
 you
 know
 when
 we
 talk
 about
 a


and
 think
 about
 AI
 agents
 we
 think
 about


speed
 code
 generation.
 We
 rarely
 use


quality
 and
 AI
 agents
 in
 the
 same


sentence.
 Why
 is
 that
 with
 the
 tools


getting
 better?
 Should
 AI
 engines
 not
 be


better
 to
 have
 feedback
 loops?
 you
 know


they
 can
 write
 unit
 tests
 like
 should


they
 not
 be
 able
 to
 produce
 better
 code


better
 features
 better
 UIs
 even
 uh
 no


they
 they
 don't
 feel
 they
 they
 have
 no


taste
 um
 they
 they
 simply
 don't
 um
 they


are
 not
 human
 beings
 I
 think
 the
 last


bastion
 that
 you
 know
 we
 have
 to
 tackle


at
 some
 point
 and
 maybe
 we'll
 get
 there


maybe
 we
 won't
 is
 um
 you
 know
 have
 you


know
 tasteful
 AI
 being
 able
 to
 create
 UI


that
 is
 you
 know
 purpose-built
 for
 you


know
 that
 specific
 feature
 you're


building
 for
 the
 product
 that
 you're


building
 is,
 you
 know,
 has
 great
 design


um
 and
 has
 the
 ability
 to
 figure
 out


like
 what
 what
 a
 user
 feels
 when
 they


use
 your
 application.
 To
 give
 you
 an


example,
 um
 AI
 doesn't
 have
 a
 concept
 of


time
 and
 currently
 how
 it
 sort
 of


interacts
 with
 your
 browser
 is
 um


effectively
 timeless.
 um
 they
 take


screenshots
 or
 they
 look
 at
 the
 DOM
 and


if
 you
 ask
 it
 to
 create
 a
 very
 you
 know


high
 performant
 application
 like
 yeah
 it


can
 go
 back
 you
 know
 and
 look
 at
 all
 the


all
 the
 things
 that
 have
 been
 written


about
 like
 you
 know
 go
 to
 versol
 to
 host


your
 next
 app
 or
 you
 know
 use
 caching
 or


or
 whatever
 but
 it
 won't
 be
 able
 to
 use


your
 application
 and
 get
 frustrated


because
 you
 know
 a
 click
 took
 two


seconds
 um
 it
 knows
 that
 one
 second
 is


better
 than
 two
 seconds
 but
 it
 it


doesn't
 know
 whether
 two
 seconds
 is
 is


is
 slow
 enough.
 Um
 the
 other
 aspect
 that


goes
 into
 it
 is
 um
 it
 it
 doesn't
 really


see
 um
 and
 it
 doesn't
 know
 what
 for


example
 a
 good
 use
 animation
 is.
 Um


Emil,
 one
 of
 our
 um
 uh
 design
 engineers


um
 just
 yesterday
 posted
 um
 on
 on
 on
 X


um
 where
 he
 you
 know
 did
 this
 trial
 of


you
 know
 having
 agents
 build
 certain


animations
 for
 you
 know
 um
 certain


functionality
 like
 you
 know
 bringing
 up


a
 pop-up
 or
 highlighting
 a
 button
 or


moving
 things
 around
 and
 um
 he
 agents


were
 totally
 capable
 of
 doing
 all
 of


this
 and
 then
 he
 took
 a
 manual
 step
 and


was
 like
 well
 if
 I
 now
 take
 it
 and
 just


improve
 it
 and
 make
 it
 feel
 good
 um


here's
 the
 outcome
 and
 he
 has
 it
 up
 on


his
 side
 can
 sort
 of
 you
 try
 out
 what


the
 agent
 did
 and
 what
 he
 then
 he
 then


fixed
 and
 at least
 to
 me
 and
 I
 hope


everybody
 else
 um
 like
 his
 animations


just
 feel
 natural
 they
 they
 feel
 they


feel
 like
 like
 the
 welldesigned
 whereby


the
 the
 agent
 did
 all
 the
 right
 things


but
 you
 know
 had
 an
 ease
 in
 as
 an


animation
 or
 or
 you
 know
 did
 it
 a
 bit


too
 slowly
 or
 too
 quickly
 um
 and
 it
 just


felt
 you
 know
 unnatural.

</details>

### Linear 的企业文化与招聘

**Tuomas Artman**: 我想稍微谈谈 **Linear** 的文化。第一，在那里工作是什么样的？你如何创造一个真正关心质量、良好的客户体验的团队？你们在那里具体做什么？ um，工程师在入职第一天就会接触到什么？是的，我们专门为此招聘，并且我们有一个特定的招聘流程，确保我们能找到那些像我们一样思考，或者愿意构建高质量软件的人。 um，我们的大部分工程师都是产品工程师。我们当然有技术挑战。我们有 um，你知道，一个同步引擎。我们有，你知道，规模。我们需要扩展我们的基础设施。但我们想做的是让大部分工程师专注于产品，构建功能，你知道，以及为客户构建功能，并与客户进行非常高层次的互动。 um，所以首先，我们为此招聘。 um，我们有一个“**伯克试炼**”（Burke trial），我们对每一位员工都这样做，你知道，好几天，对吧？

<details>
<summary>Original English</summary>

**Tuomas Artman**: I
 wanted
 to
 talk
 a
 little
 bit
 about
 the


culture
 at
 Alineir.
 One,
 it's
 like


working
 there
 like
 how
 you
 created
 this


team
 that
 really
 cares
 about
 quality


good
 customer
 experience.
 What
 are
 what


what
 are
 things
 that
 you
 do
 specifically


there?
 C
 can
 we
 talk
 about
 it
 on
 on
 what


engineers
 are
 exposed
 to
 who
 who
 join


the
 company
 from
 day
 one?
 Yeah,
 we
 we


hire
 for
 for
 that
 specifically
 and
 we


have
 a
 you
 know
 specific
 hiring
 process


where
 we
 make
 sure
 that
 we
 get
 people


that
 think
 like
 mind
 or
 think
 think
 like


us
 and
 want
 to
 build
 high
 quality


software
 that
 is
 beautiful.
 Um
 most
 of


our
 engineers
 are
 product
 engineers.


They're
 they're
 like
 we
 obviously
 do


have
 technical
 challenges.
 We
 have
 um


you
 know
 a
 synchronization
 engine.
 We


have
 you
 know
 scale.
 We
 need
 to
 scale


our
 infrastructure.
 But
 what
 we
 wanted


to
 do
 is
 have
 most
 of
 our
 engineers
 just


be
 you
 know
 focusing
 on
 the
 product
 and


build
 features
 you
 know
 and
 and


functionality
 for
 customers
 and
 engage


with
 the
 customers
 at
 a
 very
 high
 level.


Um
 so
 first
 of
 all
 we
 we
 we
 hire
 for


that.
 Um
 we
 have
 a
 Burke
 trial
 that
 we


do
 with
 every
 single
 employee
 that
 that


you
 know
 several
 days
 right

</details>

**Gergely Orosz**: >> 这是一个完整的一周。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> it's
 a
 full
 week.

</details>

**Tuomas Artman**: >> 这是一个完整的一周。所以我们，我们显然为此付费，但我们与一个人合作整整一周。他们通常会实现一个全新的项目或产品或功能。 um，有时他们甚至在那周之后就交付了，这真的很神奇。 um，但我们想从中获得的是，只是看看他们如何从头到尾地推动一个产品，弄清楚需要什么。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> It's
 a
 full
 week.


>> So
 we
 we
 obviously
 pay
 for
 that
 effort


but
 we
 work
 with
 a
 with
 a
 person
 for
 a


full
 week.
 they
 usually
 implement
 a


green
 field,
 you
 know,
 pro
 project
 or


product
 or
 feature.
 Um,
 sometimes
 they


even
 ship
 it
 after
 that
 week,
 which
 is


which
 is
 pretty
 amazing.
 Um,
 but
 what
 we


want
 to
 get
 out
 of
 that
 experience
 is


just
 to
 see
 them
 drive,
 you
 know,
 a


product
 from
 from
 start
 to
 finish,


figure
 out
 what
 is
 needed.

</details>

**Gergely Orosz**: >> 所以，这里的反驳是，“等等，一周，你付费，当然，但有人必须花时间离开工作。”一大群优秀的人会说，“不，我要么不能，要么不愿这样做。”

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> So,
 a
 push
 back
 here
 would
 be
 like,
 hang


on,
 a
 whole
 week,
 you
 pay
 for
 it,
 sure,


but
 someone
 had
 to
 take
 time
 off
 of
 it.


A
 bunch
 of
 great
 people
 will
 say,
 no,
 I


I
 either
 cannot
 or
 will
 not
 do
 that.

</details>

**Tuomas Artman**: >> 好吧，那完全没关系。那些人从一开始就不想在这里。所以，这是自我筛选，但在你经历了如此严格的招聘流程之后，这比我认为的任何其他流程都要长。你的意思是，在大多数地方，你有一个一天的流程，或者它们是堆叠起来的。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> Well,
 that's
 totally
 fine.
 like
 those


people
 didn't
 want
 to
 be
 here
 in
 the


first
 place.
 So,


it's
 it's
 it's
 self,
 but
 after
 you
 go


through
 this
 pretty
 rigorous
 hiring


process,
 it's
 a
 lot
 longer
 than
 I
 think


any
 other
 process.
 I
 mean,
 you
 know,
 you


have
 a
 dayong
 process
 at
 most
 places
 or


or
 they're
 stacked
 across.

</details>

**Gergely Orosz**: 你有没有看到与你在 **Uber** 招聘时不同的结果？当你招聘 **Uber** 的时候，你做了常规的事情，比如五次面试，六次面试等等。你看到了什么不同的结果？

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> Did
 you
 see
 any
 different
 result
 than


for
 example
 when
 you
 hired
 at
 Uber?
 When


you
 were
 hiring
 at
 Uber,
 you
 you
 did
 the


usual,
 you
 know,
 like
 five
 interviews,


six
 interviews
 and
 so
 on.
 What
 was
 the


outcome
 difference
 that
 you're
 seeing?

</details>

**Tuomas Artman**: 当然，嗯，我们，我们很少出错。 um，我们雇用的大部分人，当然总有几个人，我们 um，我们就是错过了什么，然后 um，我们继续，回到循环中，就像，我们有一些迹象表明我们有点不确定，然后我们还是雇用了那个人。但这些人只是，就像，少数几个。我认为我们的大部分工程师都非常优秀。 um，而且我们的工程标准非常高，并且在不断提高。

<details>
<summary>Original English</summary>

**Tuomas Artman**: Certainly
 um
 like
 we
 we've
 had
 very
 few


misses.
 Um
 most
 of
 the
 people
 that
 we've


hired
 and
 sure
 there
 always
 are
 a
 few


where
 we
 um
 we
 just
 missed
 something
 and


um
 we
 and
 going
 back
 into
 sort
 of
 the


loops
 like
 we
 there's
 inklings
 of
 like


us
 being
 a
 bit
 uncertain
 and
 then
 we


went
 ahead
 and
 hired
 the
 person
 anyways.


But
 those
 are
 just
 like
 a
 a
 few
 handful


of
 handful
 of
 people
 like
 I
 think
 most


of
 our
 engineers
 are
 you
 know
 really


excellent.
 Um
 and
 our
 engineering,
 you


know,
 bar
 is
 is
 super
 high
 and


constantly
 increasing.

</details>

**Gergely Orosz**: 然后一旦这些工程师进来，你告诉我一些关于 Slack 频道和客户的有趣的事情，对吧？

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> And
 then
 once
 those
 engineers
 enter,
 you


told
 me
 something
 interesting
 about
 the


Slack
 channels
 and
 customers,
 right?

</details>

**Tuomas Artman**: 我们确实有 um，与我们所有大客户的 Slack 频道。任何人都可以加入。 um，大多数人都会这样做，就像你浏览客户请求，你浏览人们遇到的问题。 um，我们还记录了我们与客户举行的每一次会议。我们有很多会议，不仅仅是在 CX 方面或 um 支持方面，但我们的 PM 不断地与重要客户交谈，以弄清楚我们下一步应该构建什么，所有这些都被记录下来， um，并且任何有趣的观点都会被标记，所以任何人都可以进入，然后你知道，查看，甚至搜索，嗯，关于特定功能，然后弄清楚，你知道，客户在说什么，他们想要什么。所以每个人都能接触到客户需求，嗯，而这对于伟大的产品来说是超级重要的。这几乎就像，如果你进入 Linear，你就会得到，就像，客户反馈的“高压水枪”，你真的无法逃避看到和感受，你知道，客户的痛苦或喜悦或任何东西。

<details>
<summary>Original English</summary>

**Tuomas Artman**: We
 do
 have
 um
 Slack
 channels
 with
 all
 of


our
 big
 customers.
 It's
 open
 to
 anybody.


Anybody
 can
 jump
 in.
 Um
 and
 most
 people


do
 like
 you
 browse
 through
 customer


requests,
 you
 browse
 through
 what
 you


know,
 what
 problems
 people
 have.
 And
 um


we
 we
 also
 record
 every
 single
 meeting


that
 we
 have
 with
 customers.
 And
 we
 have


a
 lot
 of
 meetings
 like
 not
 only
 on
 the


on
 the
 CX
 side
 or
 um
 support
 but
 our
 PMs


have
 constantly
 you
 know
 talked
 with


Bler
 customers
 to
 figure
 out
 what
 we


should
 be
 building
 next
 and
 all
 of
 those


are
 recorded
 um
 and
 any
 interesting


points
 are
 tagged
 so
 anybody
 can
 can
 go


in
 and
 then
 you
 know
 look
 at
 and
 even


search
 uh
 for
 you
 know
 certain


functionality
 and
 figure
 out
 like
 what


are
 customers
 saying
 what
 what
 do
 they


want
 so
 everybody
 gets
 exposed
 um
 to


customer
 needs
 uh
 and
 that
 is
 super


critical
 if
 you
 if
 you
 want
 great


product.
 It's
 almost
 like
 if
 you
 enter


linear,
 you
 get
 this
 like
 fire
 hose
 of


like
 what
 are
 customers
 feedback
 and
 you


you
 cannot
 really
 escape
 seeing
 and


feeling,
 you
 know,
 feeling
 the
 customer


pain
 or
 joy
 or
 whatever
 that
 is.

</details>

**Gergely Orosz**: 当然。是的。因为我们是为客户而建的。就像 **Linear** 最初是一个我们为自己构建的产品。对，我们作为工程师是主要客户。我们已经超越了这一点，就像我们为更大的公司和企业构建。我们已经不是一家大公司了。所以我们必须构建那些，你知道，我们自己不会使用的东西。而做到这一点的方法就是，你知道，与你的客户交谈，弄清楚他们需要什么。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> Certainly.
 Yeah.
 Cuz
 we
 build
 it
 for


customers
 like
 Liner
 started
 off
 as
 a


product
 where
 we
 build
 it
 for
 ourselves,


right?
 We
 as
 engineers
 were
 the
 primary


customer.
 We've
 grown
 out
 of
 that
 like


we
 we
 build
 it
 for
 larger
 corporations


and
 enterprises
 and
 we're
 no
 big


enterprise.
 So
 we
 have
 to
 build
 things


that
 you
 know
 we
 wouldn't
 use
 ourselves


and
 the
 only
 way
 to
 do
 that
 is
 to
 you


know
 talk
 with
 your
 customers
 and
 figure


out
 what
 they
 need.

</details>

### 未来工程师的角色与建议

**Gergely Orosz**: 如果你必须展望未来一年，你，你有时会有强烈的意见。所以，让我们把它们带出来，展望一年。你认为软件工程师或产品工程师的角色将如何改变，因为我们拥有这些强大的工具？它们在某些领域变得更好，而在其他领域可能没有那么好。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> If
 you
 had
 to
 look
 a
 year
 ahead
 you
 you


you
 sometimes
 have
 strong
 opinions.
 So


like
 let's
 bring
 those
 out
 a
 year
 ahead.


How
 do
 you
 think
 the
 role
 of
 the


software
 engineer
 or
 product
 engineer


will
 change
 because
 we
 do
 have
 these


powerful
 tools.
 They're
 getting
 better


in
 certain
 areas
 and
 maybe
 not
 so
 much


better
 in
 others.

</details>

**Tuomas Artman**: 我认为每个人将在某种意义上都成为产品工程师。如果你考虑一下 AI 的进展，回到四年前，它还不能写一行代码，现在它正在掌管代码库。 um，再往前推四年，如果你仍然相信指数增长仍然存在，我们没有遇到障碍 um，我不知道我们是否会，但 um，如果它继续这样增长，你将不再需要那些将数据从一个地方传输到另一个地方的工程师。你仍然需要那些知道客户想要什么，以及什么是好的功能，或者什么是好的用户体验的工程师。 um，所以我想，你知道，工程师将不得不转向成为以产品为导向和专注于产品的。他们将不得不成为“迷你 PM”，与客户交谈，参与那个层面，嗯，然后可以，你知道，实现客户想要的功能。

<details>
<summary>Original English</summary>

**Tuomas Artman**: I
 think
 everybody
 will
 become
 a
 product


engineer
 um
 in
 in
 some
 sense.


If
 you
 if
 you
 think
 about
 how
 AI
 has


progressed
 um
 go
 back
 like
 four
 years
 it


wasn't
 able
 to
 write
 a
 single
 line
 of


code
 and
 now
 it's
 commandeering
 code


bases
 um
 go
 four
 years
 ahead
 and
 if
 you


if
 you
 still
 believe
 that
 it's
 that
 the


exponential
 growth
 is
 still
 there
 and
 we


don't
 hit
 a
 wall
 um
 which
 I
 I
 don't
 know


if
 we
 will
 but
 um
 if
 it
 if
 it
 keeps
 on


going
 growing
 like
 this
 like
 you
 you


won't
 be
 needing
 engineers
 that
 sort
 of


pipe
 data
 from
 one
 place
 to
 another
 you


still
 will
 be
 needing
 engineers
 who
 know


what
 a
 customer
 wants
 and
 what
 a
 good


feature
 looks
 like
 or
 what
 a
 good
 user


experience
 looks
 like.
 Um
 so
 I
 think
 you


know
 engineers
 will
 have
 to
 move
 to


become
 product
 oriented
 and
 product


focused.
 They
 will
 have
 to
 be
 sort
 of


mini
 PMs
 who
 sort
 of
 talk
 with
 customers


are
 engaging
 in
 that
 layer
 um
 and
 then


can
 you
 know
 implement
 functionality
 um


that
 your
 customers
 want.

</details>

**Gergely Orosz**: 哦，天哪。所以，你知道，我记得在 2000 年代，我们作为程序员，你只需要掌握一种语言，然后是多种语言，然后是 QA 工作，你得到了 QA 工作，然后是 DevOps，现在你却说我们要承担产品工作和客户支持工作。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> Oh
 man.
 So
 like
 you
 know
 I
 remember
 in


like
 the
 the
 2000
 the
 two
 2000s
 we
 as
 a


as
 a
 programmer
 you
 could
 just
 use
 one


language
 then
 it
 was
 like
 multiple


languages
 then
 the
 QA
 job
 you
 got
 the
 QA


job
 then
 you
 got
 DevOps
 now
 you're


saying
 we're
 the
 the
 product
 job
 and
 the


customer
 support
 job
 as
 well.

</details>

**Tuomas Artman**: >> 哦，其他的都下降了，现在你只需要做，你知道，PM 的工作。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> Oh
 everything
 else
 has
 dropped
 now
 like


you
 just
 need
 to
 do
 the
 you
 know
 PM
 job.

</details>

**Gergely Orosz**: 好的。 um，作为最后的建议，你在招聘产品工程师。你说你现在确实招聘产品工程师。现在不是每个人都有机会在一个产品工程师的角色中工作。但是，如果你是一名软件工程师，你可以做些什么来培养这种产品意识，让你的工作更接近产品工程师的工作？

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> Okay.
 Um
 and
 as
 closing
 advice
 you
 are


hiring
 for
 for
 product
 engineer.
 You


said
 that
 you
 actually
 hire
 for
 that


now.
 Not
 every
 might
 have
 the


opportunity
 to
 work
 in
 a
 role
 that
 is
 a


product
 engineer
 right
 now.
 But
 if


you're
 a
 software
 engineer,
 what
 are


things
 that
 you
 can
 do
 to
 grow
 this


product
 sense
 to
 be
 to
 to
 change
 your


work
 to
 be
 closer
 to
 what
 a
 product


engineer
 does?

</details>

**Tuomas Artman**: 我的意思是，这完全是关于，嗯，更接近你的客户。如果你在一个公司工作，或者只是构建东西。就像，学习的最好方法是，你亲自动手，尝试一些东西，为自己构建它。这是最容易的部分。 um，你可以考虑，就像，你需要什么。你可以构建它，然后你就能从中学到经验。然后你把它发布到全世界，希望其他人也能使用它，然后你知道，你就有了你的第一个客户，你可以从中获得经验，你知道，无论你构建的是正确的东西还是不正确的东西。 um，当然，也有大量的文献，你可以，你知道，阅读 **Apple** 的人机界面指南，那是一本最好的书， um，如果你想做好用户体验，嗯，只要遵循他们说的去做，你就会做得很好。 um，是的，那就是那两件大事。

<details>
<summary>Original English</summary>

**Tuomas Artman**: I
 mean,
 it's
 all
 about
 uh


getting
 closer
 to
 your
 customers
 if


you're
 working
 at
 a
 company
 or
 just


building
 stuff.
 Like
 the
 best
 way
 to


learn
 is
 to
 actually
 you
 get
 your
 hands


dirty,
 try
 something
 out,
 build
 it
 for


yourself.
 That's
 the
 easiest
 part.
 um


you
 can
 think
 about
 like
 what
 you
 need


you
 can
 you
 can
 build
 it
 and
 you
 learn


from
 that
 experience
 then
 you
 ship
 it
 to


the
 world
 hopefully
 somebody
 else
 uses


it
 as
 well
 and
 then
 you
 know
 you've
 got


you
 know
 your
 first
 customers
 that
 you


can
 get
 experience
 from
 of
 you
 know


whether
 you're
 building
 the
 right
 thing


right
 thing
 or
 not
 um
 obviously
 there's


literal
 lit
 literature
 as
 well
 you
 can


you
 know
 read
 through
 you
 know
 Apple's


human
 interface
 guidelines
 that's
 the


best
 book
 um
 if
 you
 want
 to
 do
 sort
 of


good
 UX
 um
 just
 follow
 what
 they
 say
 and


you'll
 be
 good
 um
 and
 yeah
 those
 are


those
 are
 the
 two
 big
 things

</details>

**Gergely Orosz**: 太棒了。嗯，**Thomas**，非常感谢你。

<details>
<summary>Original English</summary>

**Gergely Orosz**: >> awesome
 Well,
 Thomas,
 thank
 you
 so
 much.

</details>

**Tuomas Artman**: 谢谢你。

<details>
<summary>Original English</summary>

**Tuomas Artman**: >> Thank
 you.

</details>