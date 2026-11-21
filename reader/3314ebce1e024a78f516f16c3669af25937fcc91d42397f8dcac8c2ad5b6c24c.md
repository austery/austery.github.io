---
author: Dwarkesh Patel
date: '2024-06-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wZ0ToxtXz5g
speaker: Dwarkesh Patel
tags:
  - agi
  - intelligence
  - arc-benchmark
  - memorization
  - brute-force
title: AI智能的本质：从Arc基准到‘暴力破解’的思考
summary: 本次讨论探讨了AI模型若能解决Arc基准测试（达到人类80%水平）是否标志着AGI的到来。发言者质疑了基准测试的有效性，认为其可能被规模化数据“作弊”或“暴力破解”。文章深入剖析了智能的本质，将其比作路径寻找算法，并挑战了AI“记忆”与人类“推理”的二元划分，认为两者可能处于同一连续光谱上，且人类学习过程本身也包含大量算法记忆。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - arc
media_books: []
status: evergreen
---
### AI智能的本质：从Arc基准到“暴力破解”的思考

讨论的核心在于，如果一个多模态模型能在一年内解决“Arc”基准测试，并达到人类平均水平的80%，这是否意味着通用人工智能（AGI）的出现？对此，演讲者提出了一种设想：期望看到一个LLM类型的模型能够以80%的准确率解决Arc，但其训练数据不应是明确为预测该测试集而准备的。然而，Arc基准测试的意义在于，它每次都呈现新的图谱和智能挑战，使得作弊变得不可能。如果Arc是一个完美无瑕的基准，那么在测试集内是无法被预测的。Arc测试已发布四年多，至今仍能抵抗“死记硬略”式的解决方案，在一定程度上经受住了时间的考验。但演讲者也指出，如果通过手工创建数十万个Arc任务，再通过程序化生成变体，最终可能产生数亿个任务，那么训练数据与测试集之间很可能会产生足够的重叠，从而能够获得极高的分数。这引出了一个观点：拥有足够的规模，总能“作弊”。

<details>
<summary>Original English</summary>

so
 suppose
 that
 it's
 the
 case
 that
 in
 a


year
 a
 multimodal
 model
 can
 solve
 Arc


let's
 say
 get
 80%
 whatever
 the
 average


human
 would
 get
 then
 AGI
 quite
 possibly


yes
 I
 think
 if
 you
 if
 you
 start
 so


honestly
 what
 I
 would
 like
 to
 see
 is
 uh


an
 llm
 type
 model
 solving
 Arc
 at
 like


80%
 but
 only
 trained
 on
 information
 that


is
 not
 um
 explicitly
 trying
 to


anticipate
 what
 it's
 going
 to
 be
 in
 the


AR
 test
 set
 but
 isn't
 the
 isn't
 the


whole
 point
 of
 Arc
 that
 you
 can't
 sort


of
 it's
 a
 new
 chart
 of
 type
 of


intelligence
 every
 single
 time
 is
 the


point
 so
 if
 Arc
 were
 perfect
 Flawless


Benchmark
 it
 would
 be
 impossible
 to


anticipate
 within
 the
 test
 set
 and
 you


know
 Arc
 was
 released
 uh
 more
 than
 four


years
 ago
 and
 so
 far
 it's
 been
 resistant


to
 memorization
 so
 I
 think
 it
 has
 uh
 to


some
 extent
 passed
 a
 test
 of
 time
 but
 I


don't
 think
 it's
 perfect
 I
 think
 if
 you


try
 to
 make
 by
 hand
 uh
 hundreds
 of


thousands
 of
 AR
 tasks
 and
 then
 you
 try


to
 multiply
 them
 uh
 uh
 by


programmatically
 generating
 variations


and
 then
 you
 end
 up
 with
 maybe
 hundreds


of
 millions
 of
 tasks
 uh
 just
 by
 brute


forcing
 the
 task
 space
 there
 will
 be


enough
 overlap
 between
 what
 you're
 train


on
 and
 what's
 in
 the
 test
 set
 that
 you


can
 actually
 score
 very
 highly
 so
 you


know
 with
 enough
 scale
 you
 can
 always


cheat
</summary>
</details>

### 智能的路径寻找与“暴力破解”的界限

演讲者进一步探讨了智能的本质，提出了一种比喻：可以将智能视为一种在未来情境空间中寻找路径的算法。这类似于实时战略（RTS）游戏开发中的概念，玩家在一个地图上拥有部分信息（存在战争迷雾），无法完全了解未知区域或过去区域的现状。智能的目标是，一旦设定了目标，就能找到通往该目标的最佳路径。然而，这种路径寻找受限于已知信息，无法预见未知或变化。如果能完全掌握地图的所有信息，路径寻找问题可以通过死记硬略所有可能的路径来解决，即通过纯粹的记忆来完成。但在现实生活中，由于未来充满不确定性，生命是不断变化的，因此纯粹的记忆或死记硬略是不现实的。演讲者暗示，如果世界的“分布”是静态的（例如，在一种“病态的分布”下），那么通过“暴力破解”所有可能的行为空间来“强制获得”智能是可能的。

<details>
<summary>Original English</summary>

if
 you
 can
 do
 this
 for
 every


single
 thing
 that
 supposedly
 requires


intelligence
 then
 what
 good
 is


intelligence
 apparently
 you
 can
 just


Brute
 Force
 intelligence
 if
 if
 the
 world


if
 your
 life
 were
 athetic
 distribution


uh
 then
 sure
 you
 could
 just
 bruteforce


the
 space
 of
 possible
 behaviors
 could


like
 you
 know
 the
 way
 we
 think
 about


intelligence
 there
 are
 several
 metaphors


SEL
 actives
 but
 one
 of
 them
 is
 you
 can


think
 of
 intelligence
 as
 a
 past
 finding


algorithm
 in
 future
 situation
 space
 like


I
 don't
 know
 if
 you're
 familiar
 with


game
 development
 like
 RTS
 game


development
 but
 you
 have
 a
 map
 right
 and


and
 you
 have
 it's
 like
 a
 2d
 2D
 2D
 map


and
 um
 you
 have
 partial
 information


about
 it
 like
 there
 is
 some
 fog
 of
 War


on
 your
 map
 there
 are
 areas
 that
 you


haven't
 explored
 yet
 you
 know
 nothing


about
 them
 and
 then
 there
 are
 areas
 that


you've
 explored
 but
 um
 you
 only
 know
 how


they
 were
 like
 in
 the
 past
 you
 don't


know
 how
 they
 like
 today
 and


um
 and
 and
 now
 instead
 of
 thinking
 about


Tod
 I
 think
 about
 the
 space
 of
 possible


future
 situations
 that
 you
 might


encounter
 and
 how
 they're
 connected
 to


each
 other
 intelligence
 is
 a
 past


finding
 algorithm
 so
 once
 you
 set
 a
 goal


it
 will
 tell
 you
 uh
 how
 to
 get
 there


Optimum


um
 but
 of
 course
 it's
 it's
 constrained


by
 the
 information
 you
 have
 uh
 it
 it


cannot
 pass
 fine
 in
 an
 area
 that
 you


know
 nothing
 about
 it
 cannot
 also


anticipate
 uh
 uh
 changes
 and
 um
 the
 the


the
 thing
 is
 if
 you
 had
 complete


information
 about
 the
 map
 uh
 then
 you


could
 solve
 the
 pathf
 finding
 Problem
 by


simply
 memorizing
 every
 possible
 path


every
 mapping
 from
 uh
 point
 A
 to
 point
 B


uh
 you
 could
 you
 could
 solve
 the
 problem


with
 pure
 memory
 but
 where
 the
 reason


you
 cannot
 do
 that
 in
 real
 life
 is


because
 you
 don't
 actually
 know
 what's


going
 to
 happen
 in
 the
 future
 life
 is


Ever
 Changing
</summary>
</details>

### 人类与AI的学习光谱：记忆还是推理？

演讲者对“记忆”与“推理”的界限提出了质疑，认为这种区分在人类和AI之间可能过于简化。当一个孩子学习代数或微积分时，我们不会说他们“记住了”微积分，而是说他们“学会了”微积分。然而，当AI解决类似的数学问题时，这种能力却常被贴上“记忆”的标签。演讲者认为，人类学习过程，包括掌握加法算法、代数或微积分，本质上也是在学习和应用算法或程序，这与AI的学习过程在根本上是相似的。如果AI通过学习大量技能和技术，即使它们能自动化几乎任何任务，只要分布是静态的，就可能被归类为“记忆”。演讲者进一步推测，如果远程工作技能可以通过记录屏幕并训练模型来合成数据，从而导致大量远程工人失业，而AI创造了巨大的经济价值，那么这种情形下的AI能力是否仍应被视为“记忆”？核心观点是，人类和AI在处理信息和解决问题的方式上可能共享一个连续的光谱，而非截然不同的类别。

<details>
<summary>Original English</summary>

I
 feel
 like
 you're
 using


words
 like
 memorization
 which
 we
 never


use
 for
 human
 children
 if
 if
 like
 your


kid
 learns
 to
 do
 algebra
 and
 then
 like


now
 learns
 to
 do
 calculus
 you
 wouldn't


say
 they
 memorized
 Calculus
 if
 they
 can


just
 solve
 any
 arbitrary
 algebraic


problem
 you
 wouldn't
 say
 like
 they've


memorized
 algebra
 they
 say
 they've


learned
 algebra
 humans
 are
 never
 really


doing
 pure
 memorization
 or
 pure


reasoning
 but
 that's
 only
 because
 you're


semantically
 labeling
 when
 the
 human


does
 the
 skill
 it's
 a
 memorization
 when


the
 exact
 same
 skill
 is
 done
 by
 the
 llm


as
 you
 can
 measure
 by
 these
 bench


marks
 and
 you
 can
 just
 like
 plug
 in
 any
 sort


of
 math
 problem
 humans
 are
 doing
 the


exact
 same
 as
 LM
 is
 doing
 which
 is
 just


for
 instance
 I
 know
 if
 you
 learn
 to
 add


numbers
 you're
 memorizing
 an
 algorithm


you're
 memorizing
 a
 program
 and
 then
 you


you
 can
 reapply
 it
 you
 are
 not


synthesizing
 on
 the
 Fly
 uh
 the
 addition


program
 so
 obviously
 at
 some
 point
 some


human
 had
 to
 figure
 out
 how
 to
 do


addition
 but
 like
 the
 way
 a
 kid
 learns


it
 is
 not
 that
 they
 sort
 of
 out
 from
 the


accents
 of
 SE
 Theory
 how
 to
 do
 addition


I
 think
 what
 you
 learn
 in
 school


is
 mostly
 memorization
 right
 so
 my
 claim
 is


that
 listen
 these
 models
 are
 vastly


underparameterized
 relative
 to
 how
 many


flops
 or
 how
 many
 parameters
 you
 have
 in


the
 human
 brain
 and
 so
 yeah
 they're


they're
 not
 going
 to
 be
 like
 coming
 up


with
 new
 theorems
 like
 the
 smartest


humans
 can
 but
 most
 humans
 can't
 do
 that


either
 um
 what
 most
 humans
 do
 it
 sounds


like
 a
 similar
 to
 what
 you're
 calling


memorization
 which
 is
 memorizing
 skills


or


memorizing
 um
 you
 know
 uh
 techniques


that
 you've
 learned
 and
 so
 it
 sounds


like
 it's
 compatible
 in
 your
 tell
 me
 if


this
 is
 wrong
 is
 it
 compatible
 in
 your


world
 if
 like
 all
 the
 remote
 workers
 are


gone
 but
 they're
 doing
 skills
 which
 we


can
 potentially
 make
 synthetic
 data
 of


so
 we
 record
 everybody's
 screen
 and


every
 single
 remote
 worker
 screen
 we


sort
 of
 understand
 the
 skills
 they're


performing
 there
 and
 now
 we've
 trained
 a


model
 that
 can
 do
 all
 this
 all
 the


remote
 workers
 are
 unemployed
 we're


generating
 trillions
 of
 dollars
 of


economic
 activity
 from
 Mii
 uh
 remote


workers
 in
 that
 world
 is
 are
 we
 still
 in


the
 memorization
 regime
 so
 sure
 uh
 with


memorization
 you
 can
 automate
 almost


anything
 as
 long
 as
 it's
 it's
 a
 static


distribution
 as
 long
 as
 you
 don't
 have


to
 deal
 with
 change
</summary>
</details>