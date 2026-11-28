---
author: AI Engineer
date: '2026-11-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=q4ITwvlFplQ
speaker: AI Engineer
tags:
  - video-generation
  - world-model
  - scaling-law
  - simulation
  - visual-thinking
title: Runway 创始人 Cristóbal Valenzuela：从视频生成到世界模型与 Continuum 操作系统
summary: Runway 创始人 Cristóbal Valenzuela 回顾了公司从 2019 年低分辨率模型到如今前沿视频生成的演进，阐述下一帧预测如何学习真实世界物理规律并扩展为世界模型与交互式模拟系统。他重点展示了早期研究成果 Continuum——一种基于实时视频模型构建的操作界面，能将任意内容转化为可交互的“传送门”，并支持代码 Agent 的视觉思考与动态场景生成。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Cristóbal Valenzuela
companies_orgs:
  - Runway
products_models:
  - Continuum
media_books: []
status: evergreen
---
[music]

>> 大家好。非常非常高兴来到这里。感谢大家留下来听最后一场演讲。欢迎来到我关于“黑客帝国”（The Matrix）以及我们正如何置身其中的演讲。

<details>
<summary>Original English</summary>
[music]

>> Hey
 guys.

Very
 very
 excited
 to
 be
 here.
 Thank
 you

for
 staying
 for
 the
 last
 talk.

Welcome
 to
 my
 talk
 about
 the
 Matrix
 and

how
 we're
 living
 through
 it.
</details>

>> [笑声]

<details>
<summary>Original English</summary>
>> [laughter]
</details>

>> 嗯……那么，你们知道吗？我已经为 Runway 工作了将近十年。实际上大概 10 年前始于这里的纽约。

我想带大家回顾一下我们在建立公司、在纽约建立这个研究实验室的过程中所获得的一些经验。以及我们认为我们在视频、像素生成领域所做的许多工作究竟在向何处推进？因此，我并不是夸大其词，我开玩笑说这可能是一场模拟，也可能不是。

<details>
<summary>Original English</summary>
>> Um

So,
 you
 know
 what?
 I've
 been
 working
 on

Runway
 for
 almost
 a
 decade
 now.
 Started

here
 in
 New
 York,
 actually,
 maybe
 around

10
 years
 ago.

And

I
 want
 to
 walk
 you
 through
 some
 of
 the

learnings
 we've
 seen
 through,
 you
 know,

building
 the
 company,
 building
 this

research
 lab
 here
 in
 New
 York.
 And
 where

do
 we
 see
 a
 lot
 of
 the
 work
 that
 we
 do

in
 video,
 in
 pixel
 generation,
 really

moving
 forward?
 And
 so,
 I
 don't
 kind
 of

exaggerate
 and
 I
 joke
 that
 this
 is
 might

be
 a
 simulation
 or
 not.
</details>

### 从 2019 年的《橙子》到当今最前沿的视频生成

>> 嗯，为了提供一个视角，我先带大家看一段历史。这就像在看史前的古老遗迹。

呃，这是我们在 2019 年制作的第一部 AI 电影。它叫做《橙子》（The Orange），因为正如大家非常清楚地看到的，它是一个从树上掉下来、在世界不同地方走动的橙子。

<details>
<summary>Original English</summary>
Um
 and
 and
 so,
 for
 maybe
 for

perspective,
 I'll
 walk
 you
 through
 a

piece
 of
 history.
 This
 is
 like
 watching

prehistoric
 ancient
 ruins.

Uh
 this
 is
 our
 first
 AI
 film
 that
 was

done
 in
 2019.

It's
 called

the
 orange
 because
 as
 you
 can
 tell
 very

clearly,
 it's
 an
 orange
 that
 falls
 from

the
 tree
 and
 walks
 through
 different

parts
 of
 the
 world.
</details>

>> 嗯，这是……这是我们当时拥有的一个视频模型和图像模型生成的，它在以 128 像素乘以 128 像素的规格生成像素，然后我们强行上采样到这种分辨率。

我现在把它看作一种艺术。这就像在看一部 1900 年代的电影，你知道吗？它很美，背后承载着很多历史。但这是 2019 年。呃，我们在 2018 年、2017 年创立了这家公司。所以，我们当时试图弄清楚这是否有任何发展潜力。

呃，我们试图说服自己，如果对其进行扩展（scale），它自然会改善到我们能够达到接近这种水平的程度。

<details>
<summary>Original English</summary>
Um
 this
 is
 done
 this
 is
 a

video
 model
 and
 image
 model
 that
 we
 had

back
 then
 that
 was
 creating
 pixels
 in

128
 pixels
 by
 128
 pixels
 that
 we
 then

forcedly
 up
 sample
 to

to
 this
 kind
 of
 resolution.

I
 think
 of
 this
 as
 art
 now.
 This
 is
 this

is
 like
 looking
 at
 a
 film
 from
 the

1900s,
 you
 know?
 It's
 it's
 beautiful.

There
's
 a
 lot
 of
 history
 behind
 it.

But
 this
 is
 2019.
 Uh
 we
 started
 the

company
 in
 2018,
 2017.
 And
 so,
 we
 were

trying
 to
 figure
 out
 if
 this
 had
 any

lags.

Uh
 we're
 trying
 to
 convince
 ourselves

that
 if
 you
 scale
 this,
 it
 will

naturally
 improve
 to
 the
 point
 where
 we

can
 get
 somewhere
 close
 to

this.
</details>

>> 这就是当今最前沿的视频。这全是生成的。这些角色都不是真实的。那些地点也全都不是真实的。

我相信你们——你们可能在座的人现在都知道这个，嗯，你们可能已经在 Twitter 上看到过了。

嗯，这些模型简直好得不可思议。而且最有趣的是，当我看到这样的成果时，嗯，我依然相信，只要再过短短几年，它看起来就会像当年的《橙子》一样。

嗯，所以我想带大家了解一下，不仅是我们今天在 Runway 正在思考什么，还有在接下来的几年里，以及正在塑造这一切的研究。

<details>
<summary>Original English</summary>
This
 is
 state-of-the-art
 video
 today.

This
 is
 all

generated.
 None
 of
 these
 characters
 are

real.
 None
 of
 those
 locations
 are
 real.

I'm
 sure
 you

You've
 probably
 here
 you
 know
 this
 um,

by
 now.
 you've
 probably
 have
 seen
 this

online
 on
 Twitter.

Um,
 the
 models
 are
 just
 incredibly
 good.

And
 the
 most
 interesting
 thing
 is
 that

when
 I
 look
 at
 stuff
 like
 this,

um,
 I
 still
 believe
 this
 will
 look
 like

the
 orange
 in
 just
 a
 couple
 more
 years.

Um,
 and
 so
 I
 want
 to
 walk
 you
 through,

you
 know,
 how
 we're
 thinking
 not
 only

through
 what
 we're
 doing
 at
 Runway

today,
 but
 also
 in
 the
 next
 couple
 of

years
 and
 the
 research
 that's
 shaping

that.
</details>

### 下一帧预测与世界模型的涌现属性

>> 嗯，我们是一家处于艺术与科学交汇点的公司。呃，我们深深植根于艺术和创意社区，同时我们拥有世界上一些顶尖的研究人员在致力于扩散模型和大型视频模型的研究。嗯，我喜欢这种结合，因为它让我们能够汇聚两者的精华。

呃，我们是一个由科学家和艺术家组成的团队，在思考视频扩展和世界模型的问题。

嗯，但在某种程度上，公司的核心理念早在 120、130 年前就已经被电影和动态影像所发现了——

那就是，如果你思考视频，也许你们在高中时还记得这个，呃，视频是一种视错觉。视频是运动的错觉。如果你以足够快的速度拼接帧，你就会创造出运动。你创造出了运动的错觉，创造出了动态画面。

所以在 Runway，我们也在做非常类似的事情。我们真正将这个理念推向了下一个高度：我们如何以足够快、足够规模化的方式进行**下一帧预测**（next frame prediction），从而希望能够做出超越单纯漂亮且优美的创意视频的事情。

<details>
<summary>Original English</summary>
Um,
 we
 are
 a
 company
 that's
 at
 the

intersection
 of
 both
 both
 art
 and

science.
 Uh,
 we
 have
 uh,
 deep
 roots
 in

artistic
 and
 creative
 communities
 and
 we

have
 some
 of
 the
 best
 researchers
 in
 the

world
 working
 on
 diffusion
 models
 and

large
 video
 models.
 Um,
 and
 I
 like
 that

combination
 because
 it
 allows
 us
 to,
 you

know,
 bring
 the
 best
 of
 both
 worlds.

Uh,
 we're
 we're
 a
 team
 of
 scientists
 and

artists
 thinking
 about
 the
 problem
 of

scaling
 video
 and
 world
 models.

Um,
 but
 in
 a
 way
 that
 the
 core
 idea
 of

the
 company
 was
 already
 discovered
 by

cinema
 and
 by
 moving
 pictures
 120,
 130

years
 ago,

which
 is,
 if
 you
 think
 about
 video,
 and

maybe
 you
 remember
 this
 from,
 uh,

from
 high
 school,
 video
 is
 an
 optical

illusion.
 Video
 is
 the
 illusion
 of

movement.
 That
 if
 you
 do

if
 you
 stitch
 frames
 fast
 enough,
 you

will
 create
 movement.
 You
 will
 create

the
 illusion
 of
 movement.
 You
 create

motion
 pictures.
 And
 so
 at
 Runway
 we're

doing
 kind
 of
 something
 very
 similar.

We're
 taking
 that
 idea
 really
 to
 the

next
 level.
 How
 do
 we
 do
 next
 frame

prediction
 fast
 enough,
 scale
 enough,
 at

in
 in
 in
 in
 such
 a
 way
 that
 we
 can

hopefully
 do
 more
 than
 just
 pretty

pretty
 and
 nice
 creative
 videos.
 And
 so
</details>

>> 所有这一切，所有这些，呃，当然都是由**扩展定律**（scaling laws）驱动的。我想我们坚信扩展定律不仅适用于语言模型，同样也适用于视频。事实正是如此。我们现在正在大幅提升投入到你们已经见过的那些模型背后的算力规模。

而且我认为，看到模型随着时间推移不断扩展，最有趣的一点就是出现的涌现属性，即当你开始采用电影在 120 年前发现的这个非常简单的想法——也就是下一帧预测，并真正将下一帧预测推向下一个层次时，所显现出的智能。

对吧？所以，如果我拿出一张像这样的图像，这不是真实的，这两个人不是真实的，而我只是根据前面的帧不断预测下一帧的样子；如果我做得足够快，如果我用一个足够大的网络去做，我就能得到运动。我就会得到运动的错觉。我就会得到对我们来说看起来如此逼真、以至于我们人类无法分辨的东西。

我看着那个视频，我已经做这行 10 年了，我也无法告诉你那究竟是真是假。

<details>
<summary>Original English</summary>
all
 of
 this
 all
 of
 this
 uh,
 is
 powered

by,
 of
 course,
 scaling
 laws.
 I
 think
 we

believe
 in
 scaling
 laws

uh,
 not
 only
 apply
 for
 for
 language

models,
 but
 also
 for
 for
 video.
 And
 this

has
 been
 true.
 We're
 now
 really
 ramping

up
 the
 amount
 of
 compute
 that
 we
 put

behind
 the
 the
 models
 that
 you
 already

have
 seen.
 And
 and
 I
 think
 the
 the

interesting
 thing
 about,
 you
 know,

seeing
 the
 model
 scale
 over
 time
 is
 the

emerging
 properties
 that
 appear,
 the

intelligence
 that
 appears
 when
 you
 start

taking
 this
 very
 simple
 idea
 that
 cinema

found
 itself
 uh,
 figuring
 out
 120
 years

ago,

um,
 which
 is
 next
 frame
 prediction,
 and

taking
 next
 frame
 prediction
 really
 to

the
 next
 level,
 right?
 So,
 if
 I
 take
 an

image
 like
 this,
 which
 is
 not
 real,

those
 two
 people
 are
 not
 real,
 and
 I

just
 keep
 on
 predicting
 what
 the
 next

frame
 will
 look
 like
 based
 on
 the

previous
 frames,
 and
 if
 I
 do
 it
 fast

enough,
 and
 if
 I
 do
 it
 with
 a
 network

that's
 big
 enough,
 I'll
 get
 movement.

I'll
 get
 the
 illusion
 of
 movement.
 I'll

get
 something
 that
 looks
 so
 real
 to
 us

that
 we
 we
 humans
 can
 distinguish.
 I
 I

look
 at
 that
 video
 and
 it's
 I've
 been

doing
 this
 for
 10
 years.
 I
 can't
 tell

you
 if
 that's
 real
 or
 not.
</details>

>> 嗯，我们测量过这一点。我们实际上衡量过、试图量化人们是否能区分真实视频和生成视频，我认为那个图灵测试我们已经通过了。呃，人们已经无法分辨了。

但是，这里更有趣的事情是，当你预测下一帧时，实际上发生的是你学到的远不止漂亮的画面。

你正在学习物理学，你正在学习物体恒存性，你正在学习重力，你正在学习遮挡，你正在学习运动，你正在学习物体在现实世界中如何运作，而你仅仅通过视频、通过图像、通过下一帧预测就完成了所有这些。

所以，如果你看一个像这样复杂的事物，嗯，一个好的视频模型为了理解如何把它做成一段连贯一致的视频，它自然需要理解：
- 所有这些物体究竟是什么；
- 它们各自如何相互关联；
- 一只骆驼可能会如何站在那样的球上；
- 容器里的水看起来是什么样。

如果我把所有这些结合在一起，并且做得足够快，我有望得到一段在我们看来逼真连贯的视频。

<details>
<summary>Original English</summary>
Um
 and
 we
 measure
 that.
 We've
 actually

measured
 tried
 to
 quantify

um
 if
 people
 can
 distinguish
 between

real
 and
 generated
 videos,
 and
 I
 think

that
 that
 Turing
 test
 we
 already
 passed.

Uh

people
 are
 not
 able
 to
 distinguish.
 But,

the
 more
 interesting
 thing
 is
 here
 is

that
 really
 what's
 happening
 as
 you

predict
 next
 frames
 is
 you're
 learning
 a

lot
 more
 than
 just
 pretty
 frames.
 You're

learning
 about
 physics,
 you're
 learning

about
 object
 permanence,
 you're
 learning

about
 gravity,
 you're
 learning
 about

occlusion,
 you're
 learning
 about

movements,
 you're
 learning
 about
 how
 the

objects
 work
 in
 the
 real
 world,
 and

you're
 doing
 that
 all
 through
 just

video,
 through
 images,
 through
 through

next
 frame
 prediction.
 So,
 if
 you
 look

at
 a
 complex
 thing
 like
 this,

um
 a
 good
 video
 model
 for
 it
 to

understand
 how
 to
 make
 this
 a
 consistent

video
 will
 need
 to
 naturally
 understand

uh
 what
 all
 these
 objects
 are,
 how
 each

of
 them
 relate
 to
 one
 another,
 how
 a

camel
 might
 probably

uh
 stand
 on
 a
 ball
 like
 that,
 what
 water

in
 a
 container
 looks
 like,
 and
 if
 I
 do

all
 of
 that
 together,
 and
 I
 do
 it
 fast

enough,
 I'll
 get,
 hopefully,
 a

consistent
 video
 that
 looks
 real
 to
 us.
</details>

### 从物理模拟到交互式世界界面模型

>> 所以，我们用来评估视频模型的很多基准测试不仅是创意层面的——创意层面的意思基本上就是你喜不喜欢它——而且实际上是基于物理、基于几何、基于物体在真实世界中如何表现以及这些物体应该如何表现，呃，还有模拟器或视频世界。

因此，你采用这种下一帧预测的理念，并以足够快的速度执行它，当然现在你就能得到某种看起来更像我们对视频应用或游戏应用所期望的东西。再次强调，这仅仅是视频，对吧？

而你把这个想法带到下一个层次。如果我们开始运用下一帧预测的理念，但把它放在环境背景中，或者某种看起来类似于游戏的东西中，会发生什么？你实际上可以开始越来越接近一个物理引擎、一个模拟系统。

但是这个模拟系统并没有物理定律——我们没有去描述物体的行为应该是什么样，该模型纯粹凭借规模的力量就知道该怎么做。这开始变得非常有趣，因为你可以考虑去玩这些世界。

这不是 GTA，这是某人在一个根本不存在的环境和软件中扮演另一个人。这完全是对模拟的模拟，这变得非常“元”（meta），对吧？

所以，当我说“欢迎来到我的黑客帝国模拟”时，我可不是在开玩笑。

<details>
<summary>Original English</summary>
So,
 a
 lot
 of
 the

uh
 benchmarks
 that
 we
 use
 to
 evaluate

our
 video
 models
 are
 not
 only
 creative,

it's
 creative
 basically
 means
 do
 you

like
 it
 or
 do
 you
 don't,
 are
 actually

based
 on
 uh

on
 physics,
 on
 geometries,
 on
 how

objects
 behave
 in
 the
 real
 world,
 and

how
 those
 objects
 should
 behave,
 uh
 and

also
 simulator
 or
 video
 worlds.
 So,
 you

take
 that
 idea
 of
 next
 frame
 prediction,

and
 you
 do
 it
 fast
 enough,
 and
 you
 get,

of
 course,
 now
 something
 that
 looks
 more

like
 what
 we
 should
 expect
 from
 a
 video

application
 or
 a
 game
 application.

Again,
 this
 is
 just
 just
 video,
 right?

And
 you
 take
 you
 take
 that
 idea
 to
 the

next
 level.
 What
 happens
 if
 we
 start

this
 idea
 of
 next
 frame
 prediction,
 but

do
 it
 in
 the
 context
 of
 through
 the

environment
 or
 something
 that
 looks

similar
 to
 a
 game,
 you
 can
 start

actually
 getting
 closer
 to
 a
 physics

engine,
 a
 simulation
 system.
 But
 the

simulation
 system
 has

no
 physics
 laws
 that
 we
 didn't
 describe

what
 the
 behavior
 of
 the
 object
 should

be,
 the
 model
 just
 knows
 how
 to
 do
 that

by
 pure
 force
 of
 of
 of
 scale.
 And
 this

kind
 of
 gets
 gets
 kind
 of
 interesting

because
 you
 can
 only
 think
 about
 playing

worlds.
 This
 is
 not
 GTA,
 this
 is

someone
 playing
 someone
 else

in
 a
 environment
 and
 a
 software
 that

doesn't
 exist.
 It's
 all
 simulation
 of
 a

simulation,
 which
 which
 gets
 really

meta,
 right?

So,
 I'm
 not
 kidding
 when
 I
 said
 welcome

to
 my
 matrix
 simulation.
</details>

>> 嗯……但对我来说最有趣的事情是，你们之前看到的一切都不是实时的。意味着制作那些视频花了几分钟或几秒钟。

嗯，当我们思考未来三四年的视频模型和世界模型时，我们现在看到的很多东西，是在深入思考：当你不仅扩展模型、让它们变得庞大得多、具有多得多的涌现属性，而且开始让它们**具备交互性**时，会发生什么？对吧？

同样运用下一帧预测的想法：你拿出一帧，预测下一帧、再下一帧、再下一帧、再下一帧，但我可以在那个帧预测过程中的任何时间点采取行动，这意味着我可以在那个世界中模拟任何可能的分歧或行动。

所以在这样的世界里，我可以播放视频，但我也可以去触碰那张图像的任何部分、任何方面，并使其具备交互性，从而影响那个世界带来的后果。而且它确实奏效了。

<details>
<summary>Original English</summary>
Um

But
 the
 most
 interesting
 thing
 for
 me
 is

that
 everything
 you
 saw
 before
 was
 not

real-time.
 Meaning
 that
 it
 took
 a
 couple

minutes
 or
 seconds
 for
 those
 videos
 to

be
 made.

Um
 a
 lot
 of
 what
 we're
 seeing
 right
 now,

when
 we
 think
 about,
 you
 know,
 the
 next

three,
 four
 years
 of
 video
 models
 and

world
 models,
 is
 to
 deeply
 think
 about

what
 happens
 when
 you
 start
 not
 only

scaling
 the
 models
 and
 making
 them
 much

much
 much

bigger
 with
 much
 more
 emerging

properties,
 but
 also
 what
 happens
 when

you
 start
 making
 them
 interactive,

right?
 So,
 take
 the
 same
 idea
 of
 next

frame
 prediction,
 you
 take
 a
 frame,
 you

predict
 the
 next
 frame,
 the
 next,
 the

next,
 the
 next,
 but
 then
 I
 can
 act
 at

any
 point
 in
 time
 in
 that
 frame

prediction,
 which
 means
 I
 can
 simulate

any
 possible
 divergence
 or
 action
 in

that
 world.
 So,
 in
 this
 world,
 I
 could

play
 the
 video,
 but
 I
 can
 also
 come
 and

touch
 every
 part
 any
 aspect
 of
 that

image
 and
 make
 it
 interactive
 to
 affect

the
 consequences
 of
 of
 that
 world.

And
 it
 works.
</details>

>> 当然，正如你们可以想象的，这对各种不同的用例都极其有用。我们现在在 Runway 设立了一个完整的机器人实验室。因此，如果你来到我们纽约的办公室，一半看起来像好莱坞制片厂，另一半则是一群机器人在办公室里穿行走动。

这样我们就能够让这些模型、或者开始让这些模型成为自主系统和具身系统在世界上行走和推理的大脑。

嗯，但还有几个更有趣的用例，我认为超越了视频和机器人这两个显而易见的方向，那就是：当你把屏幕上的任何东西、任何像素都看作一个视频模型时，会发生什么？

嗯，这里有一个很好的例子。这是一个视频模型。你现在看到了什么？首先，这是一张图像。那张图像可能是真实的，也可能不是，但我可以实时运行我们的一个视频模型，并使其成为一个交互式应用程序。

比方说，我想打开车灯；也许我想把车转过来；嗯，我只需点击它就行。我可以再转过来，也许打开引擎盖看看车内部有什么。

现在，你刚才在这里看到的一切，都没有物理的 3D 表色。没有 Unity，没有 Unreal，没有 Blender。

这仅仅是一个视频模型。一个经过训练、能够理解界面中的动作和点击的视频模型。我们称之为“世界动作模型”——

<details>
<summary>Original English</summary>
And
 of
 course,
 this
 is
 incredibly
 useful

for
 a
 variety
 of
 different
 use
 cases,
 as

you
 can
 imagine.
 We're
 now
 seeing
 an

entire
 robotics
 lab
 in
 Runway.
 So,
 if

you
 come
 to
 our
 office
 in
 New
 York,
 half

of
 it
 is
 what
 looks
 like
 a
 Hollywood

studio.
 Half
 of
 it
 is
 a
 bunch
 of
 robots

walking
 through
 and
 moving
 through
 the

office.

And
 so
 we're
 able
 to
 make
 these
 models

or
 start
 making
 these
 models
 the
 brains

of
 how
 autonomous
 and
 embodiment
 systems

walk
 and
 reason
 about
 the
 world.

Um
 but
 there's
 a
 couple
 of
 more

interesting
 use
 cases
 that
 I
 think
 go

beyond
 the
 two
 obvious
 one,
 which
 is

video
 and
 robotics,
 which
 is
 what

happens
 when
 you
 think
 about
 anything

anything
 any
 pixel
 on
 a
 screen

as
 a
 video
 model.

Um
 here's
 a
 good
 example.
 This
 is
 a

video
 model.

What
 do
 you
 see
 right
 now?
 Well,
 this
 is

an
 image
 first
 of
 all.
 That
 image
 could

be
 real
 or
 not,
 but
 I
 could
 run
 one
 of

our
 video
 models
 in
 real
 time
 and
 make

this
 an
 interactive
 application.
 So,

let's
 say
 I
 want
 to,
 you
 know,

turn
 the
 lights
 of
 the
 car.
 Maybe
 I
 want

to
 like
 turn
 the
 car
 around.
 Um
 I
 can

just
 click
 through
 it.
 I
 can
 turn
 it

around
 again.
 Maybe
 open
 the
 hood
 and

see
 what's
 inside
 the
 car.
 Now,

everything
 you
 just
 saw
 here
 has
 no

physical
 3D
 representation.
 There's
 no

Unity.
 There's
 no
 Unreal.
 There's
 no

Blender.

It's
 just
 a
 video
 model.
 A
 video
 model

has
 been
 trained
 to
 understand
 actions

and
 clicks
 in
 an
 interface.
 We
 call
 this

a
 world
 action
 model.
</details>

>> [嗤笑]

>> 嗯，抱歉，呃，是**世界界面模型**（world interface model）。

而世界界面模型，嗯，我觉得大家现在都理解了。它是一个界面，同时也是一个世界模型。世界界面模型。

嗯，它能让你做非常酷的事情，就像这样。

这里有另一个应用，另一个关于你如何考虑实时使用这种模型的例子。

嗯，我可以获取一张图像、一个表征，移动物体，并期望它们像我真正身处那个房间里一样移动。再次提醒大家，这里没有任何 3D 表征，这个环境之前可能根本没有被建模过。它只是一张图像，以及一个理解物体在空间中移动是什么样子的模型——这是因为一个非常简单的理念：充分扩展后的下一帧预测可以变成一个世界模型或模拟引擎。

<details>
<summary>Original English</summary>
>> [snorts]

>> Um
 sorry,
 um
 a
 world
 interface
 model.

And
 the
 world
 interface
 model,
 well,
 I
 I

feel
 like
 you
 guys
 understand
 now.
 It's

It's
 It's
 an
 interface
 and
 it's
 a
 world

model.
 World
 interface
 model.

Um
 allows
 you
 to
 very
 cool
 stuff
 like

this.
 And
 so
 here's
 another
 application

another
 um
 example
 of
 of
 how
 you
 could

think
 about
 using
 a
 model
 like
 this
 in

real
 time.

Um
 I
 can
 take
 an
 image
 a
 representation,

move
 objects
 around,
 and
 expect
 them
 to

move
 as
 I
 was
 if
 you
 if
 as
 I
 was

actually
 in
 that
 room.
 Again,

remember
 there's
 no
 3D
 representation
 of

this.
 There
 This
 environment
 might
 not

actually
 be
 have
 having
 modeled
 before.

It's
 just
 an
 image
 and
 the
 model
 that

understands
 how
 objects
 look
 moving
 in
 a

space
 because
 of
 this
 very
 simple
 idea

that
 next
 frame
 prediction
 scale
 well

enough
 can
 become
 a
 world
 model
 or
 a

simulation
 engine.
</details>

### Continuum：基于视频模型的操作系统与“传送门”

>> 嗯……那么利用我剩下的 8 分钟时间，我想向大家展示这个被推向另一个极致的理念。

我们不仅在思考如果你能控制这些很酷的应用程序和很酷的界面会发生什么，而且在思考如果你不断进行外推（extrapolating）会怎样。顺便说一句，我认为“外推”可能是如今在 AI 领域、在创办公司过程中最重要的技能之一。在接下来的 6 个月、12 个月、18 个月里会发生什么，可能是最需要尝试去预测和理解的事情之一。

因此我们在 Runway 经常问自己这个问题：会发生什么？如果我们不断扩展模型会发生什么？如果我们继续加入更多数据、如果我们不断让它们成为更好的模拟系统，会发生什么？

如果我们让它们成为能够预测屏幕上任何内容的通用模拟系统呢？字面意义上屏幕上的任何内容。

所以我们一直在研究一个我们称之为 **Continuum** 的想法。

Continuum 就是将实时视频模型或世界模型的理念真正推向下一个层级。这是一个操作系统。这里的理念是，在不久的将来的某个时刻，你可能会打开电脑，而你在屏幕上看到的流式传输内容可能全部来自一个视频模型。

<details>
<summary>Original English</summary>
Um

so

with
 the
 8
 minutes
 I
 have
 left,
 I
 want

to
 show
 you
 this
 idea
 taken
 to
 another

extreme.

We're
 we're
 thinking
 not
 only
 about
 what

happens
 if
 you
 can
 control
 the
 school

applications
 and
 the
 school
 interfaces,

but
 what
 happens
 if
 you
 keep

extrapolating
 and
 I
 think
 by
 the
 way

extrapolating
 may
 be
 one
 of
 the
 most

important
 skills
 these
 days
 in
 in
 AI
 in

in
 company
 building.
 What
 happens
 over

the
 next
 6
 months,
 12
 months,
 18
 months

may
 be
 one
 of
 the
 most
 important
 things

to
 to
 try
 to
 predict
 and
 understand.
 And

so
 we
 ask
 ourselves
 that
 question
 a
 lot

at
 Runway.
 What
 happens?
 What
 will

happen
 if
 we
 keep
 scaling
 the
 models?
 If

we
 keep
 adding
 more
 data,
 if
 we
 keep

making
 them
 better
 simulation
 systems.

If
 we
 make
 them
 universal
 simulation

systems
 that
 can
 predict
 anything
 on
 a

screen.
 Literally
 anything
 on
 a
 screen.

So
 we've
 been
 working
 on
 this
 idea
 that

we
 call
 continuum.

And
 continuum
 is

the
 the
 idea
 of
 real-time
 video
 models

or
 world
 models
 taken
 really
 to
 the
 next

the
 next
 degree.
 This
 is
 an
 operating

system.
 The
 idea
 here
 is
 that
 you
 might

open
 your
 computer
 at
 some
 point
 in
 the

near
 future
 and
 what
 you
 see
 streaming

to
 your
 screen
 may
 be
 coming
 from
 a

video
 model.
</details>

>> 所以，接下来我将向大家具体展示这个想法会如何成型。这仍然是非常早期的研究，但我想向大家展示这种将视频模型结合为你操作系统的一部分、你日常工作一部分的想法。

举个例子：我当时正在研究旧金山以及旧金山的雾。我想了解更多关于它在何时以及如何发生的信息。这是结构化数据。这其实是一个网站，这是你从互联网上获取的内容。

而现在 Continuum 拥有这样一个构想：我可以选择该网站中的任何一部分内容，并将其变成一个**传送门**（portal）。我们称之为传送门。

传送门是一个实时视频。它是完全可交互的，并且完全基于你正在体验和阅读的内容。我可能不会通读所有那些文字，文字对我来说太多了。所以我只想获取一段视频，我就可以生成一段由大家在那儿看到的文本所表征的视频。

这些传送门可以是 3D 插图，也可以是你正在观看或与之交互的任何内容。在右侧，你可以保留之前体验过的所有可视化内容和传送门，保留你一直试图学习的任何东西。

基本上它是一个记忆库。它是你之前看过的想象或视觉感知的“硬盘”。

在这里我当时正在研究电池，所以我可以回到我之前关于电池的传送门。因为它们是实时交互式应用，我可以在任何地方点击它们，可以拖动它们，可以开始提问，而视频和内容本身将会根据我的交互以及我操作它的方式发生改变。

<details>
<summary>Original English</summary>
So

I'll
 show
 you
 next
 specific
 how
 this

idea
 could
 could
 shape.
 This
 is
 still

very
 early
 research,
 but
 I
 want
 to
 show

you
 this
 idea
 of
 combining
 video
 models

as
 part
 of
 your
 operating
 system,
 as

part
 of
 your
 daily
 work.
 So
 here's
 an

example.

I
 was
 researching,
 you
 know,
 San

Francisco
 and
 the
 fog
 in
 San
 Francisco.

I
 wanted
 to
 learn
 more
 about
 when
 and

how
 it
 happens.
 This
 is
 structural
 data.

This
 is
 actually
 a
 website.
 This
 is

something

you
 can
 take
 from
 from
 the
 internet
 and

now
 continuum
 has
 this
 idea
 that
 I
 can

select
 any
 part
 of
 content
 in
 that

website
 and
 make
 it
 a
 portal.
 We
 call

this
 a
 portal.
 And
 the
 portal
 is
 a

real-time
 video.
 It
's
 fully
 interactive

and
 fully
 based
 on
 the
 content
 you're

experiencing
 reading
 through.
 I
 probably

won't
 read
 through
 all
 of
 that
 text.

It's
 too
 much
 text
 for
 me.

So
 I
 just
 want
 to
 get
 a
 video
 and
 I
 can

make
 a
 video
 that's
 represented
 by
 by

the
 text
 you
 see
 there.

These
 portals
 can
 be
 3D
 illustrations.

It
 can
 be
 any
 content
 that
 you're

watching
 or
 interacting
 with.
 On
 the

right
 you
 can
 have
 all
 the

visualizations
 and
 portals
 you've
 you've

experienced
 before,
 anything
 you've
 been

trying
 to
 learn.

Basically
 it's
 a
 it's
 a
 memory.
 So,
 it's

the
 disk
 of
 the
 imaginations
 or
 the

visual
 sensations
 you've
 seen
 before.

So,
 here
 I
 was
 researching
 about

batteries,
 and
 so
 I
 can
 go
 back
 to

the
 portal
 I
 had
 around
 batteries

before.
 And
 since
 they're
 real-time

interactive
 applications,
 I
 can
 click
 them
 anywhere.
 I
 can
 move
 them
 around.
 I

can
 start
 asking
 questions
 and
 the

videos
 and
 and
 the
 content
 itself
 will

change
 based
 on
 based
 on
 my
 interactions

and
 the
 way
 I'm
 I'm
 managing
 through
 it.
</details>

>> 这里是另一个非常酷的例子，当团队第一次展示给我看的时候，简直让我大为震撼。

因为它是实时视频，所以你可以让它与任何东西完全交互。不仅能通过点击，比如调整应用程序窗口大小也会改变其行为。对吧？所以我可以调整大小。

我在这里正在学习光合作用。如果我调整应用程序的大小，我就会得到不同的体验。而且由于它同样是完全交互式的应用，我可以点击它，在细胞的不同部分或光合作用的运作过程中进行导航，从而对我试图学习和做的事情有更好的理解。

再次说明，对于这一点，我仍然感到有些不确定的事情是：我不知道该怎么称呼它。我不知道这算不算是……它感觉不像普通的可视化，感觉不像视频，感觉也不像游戏。它介于这些事物之间，我认为我们需要共同努力去弄清楚我们究竟该如何称呼这类交互。

我相信大家会听到类似的声音，［嗤笑］另一件事是你可以改变 prompt 的结构，或者从一开始创建该交互的内容。

<details>
<summary>Original English</summary>
Here's
 another
 very
 cool
 example
 that

when
 I
 the
 first
 time
 I
 saw
 it
 when
 the

team
 showed
 it
 to
 me,
 it
 was
 like
 blew

my
 mind.

Since
 it's
 a
 real-time
 video,
 you
 can

make
 it
 fully
 interactive
 with
 anything.

Not
 only
 with
 clicks,
 but
 like
 resizing

the
 applications
 would
 also
 change
 the

behavior.
 Right?
 So,
 I
 can
 resize.
 I'm

I'm
 learning
 about
 photosynthesis
 here.

If
 I
 resize
 the
 application,
 I
 get
 a

different
 experience.
 And
 since
 it's

again
 fully
 interactive

applications,
 I
 can
 click
 through
 it,

navigate
 through
 parts
 of
 the
 cell
 or

how
 photosynthesis
 work
 to
 get
 a
 better

understanding
 of
 what
 I'm
 trying
 to

learn
 and
 do.

Again,

the
 one
 thing
 that
 still
 feels
 to
 me

kind
 of
 uncertain
 about
 this
 is

I
 don't
 know
 how
 to
 call
 this.
 I
 don't

know
 if
 this
 is
 doesn't
 feel
 like
 a

visualization.
 It
 doesn't
 feel
 like
 a

video.
 It
 doesn't
 feel
 like
 a
 game.
 It's

something
 in
 between,
 and
 I
 think
 we

need
 to
 do
 the
 collective
 work
 of

figuring
 out
 how
 we
 call
 these
 kind
 of

interactions
 in
 the
 first
 place.
 And
 I'm

sure
 [snorts]
 you
 hear
 kind
 of
 the
 other

thing
 is
 that
 you
 can
 change
 the

structure
 of
 the
 prompt
 or
 what's

actually
 creating
 that
 interaction
 in

the
 first
 place.
</details>

### AI 智能体的“视觉思考”与实时动态世界

>> 这里是另一个例子。我要输入一些内容。

我觉得这是目前为止最缺乏探索的领域之一。我们称之为**视觉思考**（visual thinking）。

我们把 Continuum 连接到了一个代码智能体（coding agent）上。代码智能体能做的事情是，它可以利用 Continuum 来对一个问题进行可视化思考。

想象一下，你让你的代码智能体为你的自行车创建一个 3D 模型。该模型不仅能尝试单纯通过代码来思考，还可以启动一个版本的 Continuum 来在视觉上思考这个问题。

如果大家想过某人……我相信你们有朋友，或者在场的很多人也许就是视觉型思考者。什么是视觉型思考者？那就是首先通过视觉来思考问题和想法的人。这有助于你锚定并构想出你想做的一些最好的事情。这在某种程度上非常相似。

智能体具备进行视觉思考的能力。智能体可以构建出一种你可以接入并与之交互的想象。因此，不仅智能体可以与之交互，我自己也能看到它，而且我能以比单纯仅通过文本要好得多的方式来引导该智能体。对我们而言，这是一个非常强大的想法。这是一种全新的范式，我们称这个概念为“视觉思考”。

<details>
<summary>Original English</summary>
Here
 is
 another
 example.

I'm
 going
 to
 type
 something.

And
 this
 is
 one
 of
 the
 ones
 that
 I
 feel

has
 been
 the
 most
 underexplored
 yet.

This
 is
 we
 call
 this
 visual
 thinking.

So,
 we've
 connected
 Continuum
 to
 a

coding
 agent.
 And
 what
 the
 coding
 agent

can
 do
 is
 it
 can
 use
 Continuum
 to

visualize
 through
 a
 problem.

So,
 imagine
 you
 ask
 your
 coding
 agent
 to

create
 a
 3D
 model
 for
 your
 bike.
 And

instead
 of
 the
 model
 trying
 to
 just

think
 through
 that
 via
 code,
 the
 the
 can

spin
 a
 version
 of
 Continuum
 to
 think

through
 the
 problem
 visually.

So,
 if
 you
 ever
 think
 about
 someone
 or

I'm
 sure
 you
 have
 friends
 or
 maybe
 some

a
 lot
 of
 people
 here
 maybe
 visual

thinkers.
 What
 a
 visual
 thinker
 is
 is
 it

thinks
 through
 problems
 and
 through

ideas
 visually
 first.
 And
 that
 helps
 you

ground
 and
 project
 some
 of
 the
 best

things
 you
 want
 to
 do.
 And
 this
 is

somehow
 very
 similar.

Agents
 have
 the
 ability
 to
 do
 visual

thinking.
 Agents
 can
 spin
 up

a
 sort
 of
 imagination
 that
 you
 can
 tap

and
 and
 interact
 with.
 So,
 not
 only
 the

agent
 can
 interact
 with
 it,
 I
 can
 also

see
 it
 myself.
 And
 I
 can
 guide
 the
 agent

in
 much
 better
 ways
 that
 I
 might
 have

able
 to

guide
 it
 just
 via
 text
 alone.
 Which
 is

for
 us
 a
 very
 powerful
 idea.
 It's
 a

completely
 new
 paradigm.
 And
 we
 call

this
 this
 this
 idea

uh
 visual
 visual
 thinking.
</details>

>> 嗯，我的最后一个例子是关于如何思考让 Continuum 不仅仅是按照我之前向大家展示的方式使用或浏览交互式结构化内容，而是真正让它们成为完全实时的、具有响应性的活体体验（live experiences）。

在这个例子中，我当时正在搜索火星。嗯，当 Continuum 理解了我试图搜索的意图时，它还会推荐专门为此实时设计的界面。

所以在这里，它为我创建了这个火星前哨基地，它实际上应该准确包含了关于现在实际在火星上的机器人、或者预计可能在 2030 年到达的机器人的数据。

嗯，由于这完全是交互式的，我可以与它互动。我可以去往各个地方，我可以四处走动，方式就像我可能在一个 3D 系统或 3D Continuum 中四处走动一样。

嗯，而且它确实奏效了。简直令人着迷。

<details>
<summary>Original English</summary>
Um

The
 last
 example
 I
 have

is

how
 you
 think
 about
 taking,
 you
 know,

Continuum
 to

become
 much
 more
 than
 just
 uh
 using
 or

navigating
 interactive
 structural

content
 in
 in
 the
 way
 I've
 showed
 you

before,
 but
 actually
 making
 them
 fully

live
 experiences
 that
 are
 reactive.
 So,

in
 this
 case
 I
 was
 searching
 for
 Mars.

Um
 and
 as
 as
 Continuum
 understands
 the

intention
 of
 what
 I'm
 trying
 to
 search

from,
 it
 also
 suggests
 interfaces
 that

are
 specifically
 designed
 in
 real
 time

just
 for
 that.
 So,
 here
 it
 created
 for

me
 this
 Mars
 outpost
 that's
 actually

should
 be
 uh
 accurate
 with
 the
 data

about
 the
 actual
 like
 robots
 that
 are
 in

Mars
 right
 now

uh
 or
 the
 ones
 that
 are
 projected
 maybe

in
 2030.
 Um
 and
 since
 this
 is
 fully

interactive,
 I
 can
 interact
 with
 it.
 I

can
 go
 to
 places.
 I
 can
 move
 around
 in

the
 same
 way
 that
 I
 might
 move
 around,

you
 know,
 in
 a
 3D
 system
 or
 in
 a
 3D

Continuum.
 Um

And
 it
 works.

Just
 fascinating.
</details>

### 未来展望：一切皆可模拟

>> 嗯，所以，当我说“一切都将被模拟”时，嗯，我真的在努力理解、或者帮助不仅是我们的团队、更是全世界达到这样一个阶段：今天我们所看到的很多东西，希望在短短几年或几个月后听起来都会变得显而易见。

我们将回头审视 Continuum，它可能会感觉非常接近我们刚刚展示给大家看的那个《橙子》视频。

Continuum 以及我们在视频和 Runway 中所做的很多关于模拟的事情，目前仍处于非常早期的阶段，但我们正在走向一个它真正能够工作、并且真正能够扩展的节点。

因此，我们真正感到兴奋的是，在接下来的 8 到 12 个月里，我们将把今天在这里展示的大部分内容发布给所有人使用。谢谢大家。

>> [掌声]

<details>
<summary>Original English</summary>
Um

So,
 when
 I
 say

everything
 will
 be
 simulated,
 um

I'm
 really
 trying
 to
 understand
 or
 help

not
 really
 our
 team,
 but
 the
 world

get
 to
 the
 point
 where
 a
 lot
 of
 what

we'll
 see
 today
 will
 sound
 obvious,

hopefully
 in
 a
 few
 more
 years
 or
 months.

We'll
 look
 back
 at
 Continuum
 and
 it
 will

might
 feel
 very
 close
 to
 the
 video
 of

the
 orange
 that
 we
 just
 showed
 you.

Continuum
 and
 a
 lot
 of
 the
 things
 we're

doing
 in
 in
 video
 and
 in
 Runway
 when
 it

comes
 to
 simulation
 are
 still
 in
 very

early
 days,
 but
 we're
 getting
 to
 a
 point

where
 it
 actually
 it
 actually
 works
 and

it
 really
 scales.
 So,
 what
 we're
 really

excited
 about
 is
 that
 for
 the
 next
 8
 to

12
 months
 we're
 releasing
 most
 of
 what
 I

showed
 here
 for
 everyone
 to
 use.
 Thank

you,
 guys.

>> [applause]
</details>