---
author: AI Engineer
date: '2026-10-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Ok6QdZHCcI8
speaker: AI Engineer
tags:
  - self-hosting
  - open-source-model
  - llm-inference
  - cost-optimization
  - developer-productivity
title: Revolut 如何通过自建开源模型降低 90% AI 编码成本
summary: Revolut 的 David 介绍了其团队为 2,000 名工程师自建开源模型（如 GLM）的实践经验。通过在 56 张 B200 上部署并在参数与上下文等方面进行精细调优，交付周期缩短 70%、编码时间缩短 60%，Token 综合成本降至每百万 30 美分，达到商业 API 费用的十分之一；同时通过沙箱机制与合规控制满足欧盟银行业监管要求。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - David
companies_orgs:
  - Revolut
  - Anthropic
  - OpenAI
products_models:
  - GLM
  - Gemini
  - B200
media_books: []
status: evergreen
---
### Revolut 背景与工程效能

[music]

>> 我叫 David。我在一家叫 Revolut 的公司负责 AI 运营。今天我们有 50 分钟时间。我们将讨论高性能工程，以及在专用 GPU 上自建开源模型。听起来怎么样？太棒了。所以这会是一场偏技术的分享，请多担待。
<details>
<summary>Original English</summary>
[music]

>> My
 name
 is
 David.

I
 lead
 AI
 operations
 at
 a
 company
 called

Revolut.

We
 have
 50
 minutes
 today
 together.

We'll
 talk
 about
 high-performance

engineering
 and

self-hosting
 open-source
 model
 on

dedicated
 GPU.
 How's
 that
 sound?

Cool.
 So,
 it's
 going
 to
 be
 a
 technical

one,
 so
 bear
 with
 me.
</details>

首先简单介绍一下我们公司，因为我知道这是在美国，大家可能不了解 Revolut。简单说几句：我们是欧洲的一家数字银行，拥有 8,000 万客户，业务遍布 45 个市场。去年我们是欧洲下载量最大的金融类 App。截至 7 月，我们是欧洲最大的私营企业。所以，我们发展得还可以。Revolut 的重心在于持续推出大量产品，因此公司高度重视工程文化以及该领域的卓越表现。我们接下来就聊聊这个。
<details>
<summary>Original English</summary>
Um
 so,
 maybe
 to
 start
 off
 because
 I
 know

this
 is
 the
 US
 and
 you
 may
 not
 know

Revolut.

Uh
 quick
 words
 about
 our
 company.

We're
 a
 digital
 bank
 in
 Europe.
 We
 have

80
 million
 customers.

We're
 live
 in
 45
 markets.

With
 the
 most
 downloaded
 financial
 app

in
 Europe
 for
 the
 last
 year.

And
 as
 of
 July,
 we're
 Europe's
 largest

private
 company.

Um

So,
 we're
 doing
 okay.

The

the
 emphasis
 of
 Revolut
 is,
 you
 know,

shipping
 a
 lot
 of
 product
 and
 so
 there's

a
 high
 focus
 on
 engineering
 culture
 and

uh

excellence
 on
 that
 domain.

And
 so,
 we'll
 talk
 about
 that.
</details>

### AI 引入历史与开源自建决策

那么，我们来谈谈 AI。这里有一张图表，大家会看到两条线。这是过去一年中 2,000 名工程师绩效的样本数据。绿线代表交付周期（lead time），即从工程师接手一个功能，到该功能合并并准备部署的时间。蓝线代表编码时间（coding time）。绿线的单位是天，蓝线的单位是小时。
<details>
<summary>Original English</summary>
So,
 let's
 talk
 about
 some
 AI.

We
 have
 a
 chart
 here.
 I
 going
 to
 see
 two

lines.
 This
 is
 a
 sample
 of

2,000
 engineers
 performance
 over
 the

last
 year.

So,
 the
 green
 line
 is
 going
 to
 be
 lead

time.
 So,
 it's
 going
 to
 be

when
 engineer
 picks
 up
 a
 feature
 until
 a

feature
 is
 merged
 and
 ready
 to
 be

deployed.

The
 blue
 line
 is
 going
 to
 be
 coding

time.
 So,
 the
 green
 line
 is
 in
 days.
 The

blue
 line
 is
 in
 hours.
</details>

为了防止大家遗忘，我们重新梳理一下时间线，因为 AI 的发展非常快。Cloud code 大约是在 2025 年 2 月推出的，对吧？那是 Cloud Code Sonnet 3.7，就是会删掉你生产数据库的那个版本，对吧？可不是我们今天拥有的安全的 Cloud 和 Codex。所以，在我们谈论普及度时请记住这一点。
<details>
<summary>Original English</summary>
Just
 to
 reset
 the
 timeline
 in
 case

people
 forget
 because
 AI
 moves
 really

fast.

Cloud
 code
 came
 out

around
 February
 2025,
 right?
 And
 that's

the
 Cloud
 Code
 Sonnet
 3.7,
 the
 one
 would

delete
 your
 prod
 database,
 right?
 Not

the
 safe
 Cloud
 and
 Codex
 that
 we
 have

today.

So,
 bear
 in
 mind
 when
 we
 talk
 about

adoption.
</details>

从图表上可以看到，25 年 1 月，公司首次引入了 AI，也就是 Gemini。那是大家第一次能在 AI 中使用私有数据。大约在 2 月，我们开始尝试 Cloud Code。然后在 1 月是我们首次规模化上线 Cloud Code。可以看到，Gemini 带来了 10% 的交付周期缩减和 20% 的编码时间缩减，这意味着人们不再需要去查 Stack Overflow 或阅读文档了。但是当时的 Cloud Code 并没有产生那么大的影响。
<details>
<summary>Original English</summary>
So,
 what
 you
 see
 here
 on
 this
 chart
 is

January
 25th,
 first
 introduced
 AI
 in
 the

company,
 right?
 Gemini.

First
 time
 people
 were
 able
 to
 use

private
 data
 within
 AI.

Around
 February,
 we
 start
 playing
 around

with
 Cloud
 Code.

And
 then
 January
 is
 when
 we
 first

launched
 Cloud
 Code
 at
 scale.

What
 you
 see
 is

Gemini
 had
 10%
 improvement
 in
 lead
 time,

20%
 improvement
 in
 coding
 time,
 so

that's
 people

no
 longer
 needed
 to
 look
 Stack
 Overflow

and
 read
 documentation.

But
 then
 Cloud
 Code

not
 so
 much
 impact
 at
 the
 time.
</details>

所以刚推出时，我们对 AI 的成本持高度怀疑态度。我们看到工程师每个月花费 1,000 美元甚至 10,000 美元，但投资回报率却不高。因此在推出时，我们设置了严格的预算上限。接着我们开始寻找下一个方案：如何能以极低的部分成本，向工程师提供无限量的 Token，让他们可以毫无负罪感地使用 AI？于是，我们把目光投向了开源。
<details>
<summary>Original English</summary>
So,
 when
 we
 launched
 it,
 we
 were
 highly

skeptical
 about

the
 cost
 of
 AI.
 We
 were
 seeing
 engineers

spend
 a
 thousand
 a
 month,
 ten
 thousand
 a

month
 with
 not
 so
 much
 ROI.

And
 so,
 when
 we
 launched
 it,
 we
 launched

it
 with

strict
 budget
 limits.

And
 so,
 we're
 looking
 at
 the
 next
 thing,

right?
 So,
 how
 can
 we
 provide

unlimited
 tokens
 to
 engineers
 so
 they

can
 use
 AI
 guilt-free

for
 a
 fraction
 of
 the
 cost.
 And
 so,
 we

looked
 into
 open
 source.
</details>

### 自建 GLM 带来的效能突破与成本优势

大约在 26 年 4 月，我们开始自建开源模型。我们非常喜欢用 GLM 来写代码。大家可以看到，大约在那个时候，也就是 4 月 26 日上线 GLM 51 后，我们观察到编码时间改善了 60%，交付周期改善了 70%。影响极其显著。我们从中获得了什么启示呢？交付周期的改善幅度要大于编码时间，这说明工程的瓶颈并不一定在于编码本身。不再需要去翻收件箱，或者不再需要在 Jira 和 Confluence 上折腾，就能节省大量时间。因此，拥有了无限量的 Token，大家就可以自由地去做这些事，不再需要把 Token 攒到季度末或留给最困难的任务去用了。
<details>
<summary>Original English</summary>
So,
 around
 April
 26th
 is
 when
 we
 started

self-hosting
 open
 source
 model.
 We're
 a

big
 fan
 of
 GLM
 for
 coding.

So,
 around
 that
 time
 what
 you
 see,
 April

26th,
 GLM
 51

we
 see
 60%
 improvement
 in
 coding
 time,

70%
 improvement
 in
 lead
 time.
 So,

dramatic
 impact.

What
 do
 we
 learn
 from
 this?
 Well,

there's
 more
 impact
 on
 the
 lead
 time

than
 on
 the
 coding
 time,
 so

what
 we
 find
 is
 the
 bottleneck
 for

engineering
 is
 not
 necessarily
 coding.

You
 can
 save
 a
 lot
 of
 time
 not
 having
 to

dig
 through
 your
 inbox
 or

messing
 with
 Jira
 and
 Confluence.
 And

so,
 when
 you
 have
 unlimited
 token,

you're
 free
 to
 do
 that.

You
 no
 longer
 have
 to
 save
 your
 tokens

for

end
 of
 the
 quarter
 or
 the
 most
 difficult

task.
</details>

那么我们目前的现状是怎样的？开源现在是 Revolut 的优先策略，而且经济效益非常良好。账单是固定的，月底不会再有账单惊吓。前沿闭源模型只是特例。当然，我们依然在继续使用 CodeX 和 code code。最新的模型非常棒，Gemini 也运转得非常好。但我们只把它们保留作为特例使用。
<details>
<summary>Original English</summary>
So,
 where
 do
 we
 stand?

Well,
 open
 source
 is
 now
 a
 priority
 at

Revolut
 and
 yet
 the
 economics
 are

favorable.

The
 billing
 is
 flat,
 we
 don't
 have
 any

bill
 shock
 at
 the
 end
 of
 the
 month.

And
 the
 French
 here
 is
 the
 exception.

So,
 obviously,
 we
 keep
 using
 CodeX
 code

code.

The
 latest
 models
 are
 fantastic.
 Uh

Jimmy
 and
 I
 are
 going
 very
 well
 as
 very

good
 as
 well.

But,
 um
 we
 keep
 them
 as
 exception.
</details>

我们是如何做到这一步的？来看一些自建模型时至关重要的指标。为了支撑 2,000 名工程师，我们大致需要 56 张 B200。这是为了承载 GLM-53。GLM 是一个大模型，拥有 8,000 亿参数。你的目标应当设定为首字延迟（time to first token）低于 3 秒。这是经验得出的结论：只要超过 5 秒，我的 Slack 收件箱就会被各种反馈挤爆，所以我们知道这就是极限。在吞吐量方面，它其实没有那么关键，就交互性而言，我们提供每秒 200 个 Token 的服务。大家都觉得挺好，不需要更高了。人们的工作方式已经改变，大家不再盯着看流式输出的思考过程 Token，而是并行运行任务，等任务完成后再去查看。但如果你想要高吞吐量，作为 Revolut 的工程师，你只要在下午 5 点之后连上去，那时候没有人在占 GPU，你就能获得 800 TPS 的速度，体验就像做梦一样好。在成本和成效方面，自建 GLM 之后，我们的 Token 综合成本是每百万 30 美分。因此，我们现在的开销账单只有过去付给 Anthropic 和 OpenAI 的十分之一。
<details>
<summary>Original English</summary>
So,
 how
 do
 we
 get
 there?

Some
 metrics
 that
 matter
 when
 you're

self-hosting
 model.

So,
 to
 serve
 2,000
 engineers,
 we
 roughly

need
 56
 B200.

And
 that's
 to
 uh
 host
 GLM-53.
 GLM
 is
 a

big
 model,
 right?
 800
 billion

parameters.

What
 you
 want
 to
 aim
 for
 is
 sub-3
 second

time
 to
 first
 token.

This
 is
 empirical
 evidence.
 As
 soon
 as

you
 exceed
 5
 seconds,

my
 Slack
 inbox
 starts
 to
 blow
 up
 and
 so

we
 know
 that's
 the
 limit.

In
 terms
 of
 throughput,
 it
 doesn't

really
 matter
 as
 much,
 right?
 So,
 we

serve
 in
 terms
 of
 interactivity,

200
 tokens
 per
 second.

People
 are
 fine,
 you
 don't
 need
 to
 go

higher.

Um
 the
 way
 people
 work
 has
 changed,
 we

no
 longer
 look
 at
 the
 stream
 of
 thinking

tokens,
 people
 run
 tasks
 in
 parallel
 and

check
 in
 when
 the
 task
 is
 done.

But,
 if
 you
 want
 to
 have
 high

throughputs,
 when
 you're
 an
 engineer
 at

Revolut,
 you
 just
 connect
 after
 5:00

p.m.
 when
 no
 one
 is
 on
 GPU
 and
 you
 can

get
 800
 TPS
 and
 then,

you
 know,
 it's
 a
 dream.

In
 terms
 of
 cost,
 in
 terms
 of
 impact,
 uh

self-hosting
 GLM,
 our
 blended
 cost
 of

token
 is
 30
 cents
 per
 million.

And
 so,
 our
 invoice
 is
 1/10
 of
 what
 we

were
 spending
 on

Anthropic
 and
 um

OpenAI.
</details>

### 推理调优与核心参数实践

运行开源模型需要做大量的调优工作。如果只是拿到 GPU、把权重加载到 GPU 上就开始做推理，你得到的性能会非常糟糕。因为你的工作负载将极度依赖于你所设置的各项参数。如果看这张图表的最左侧，蓝线代表需求，也就是每秒请求数（RPS）。这将是影响 GPU 延迟的瓶颈所在。红线是我们正在优化的目标，即首字延迟。当我们 4 月刚起步时，可以看到每秒请求数在 3 左右，虽然高但也没那么高。而首字延迟超过了 10 秒，非常慢。大家看到的所有数据都是基于相同数量的 GPU，我们并没有增加 GPU 数量，依然是 56 张。到了 8 月底，每秒请求数超过了 7，首字延迟降到了 1.6 秒左右。也就是说，在需求增长 76% 的情况下，我们实现了 88% 的性能提升。
<details>
<summary>Original English</summary>
So,
 there's
 a
 lot
 of
 tuning
 that
 goes

into
 running
 open
 source
 models.

If
 you

just
 get
 GPUs
 and
 upload

weights
 on
 a
 GPU
 and

you
 start
 doing
 some
 inference,
 you're

going
 to
 get
 terrible
 performance.
 It's

because
 your
 workload
 is
 going
 to
 be

very
 dependent

um
 on
 the
 parameters
 that
 you
 set.

So,
 if
 you
 look
 all
 the
 way
 to
 the
 left

of
 that
 chart,
 the
 blue
 line
 is
 going
 to

be
 demand,
 so
 that's
 request
 per
 second.

That's
 going
 to
 be
 what's
 going
 to
 be

the
 bottleneck
 for
 your
 latency
 for
 your

GPUs.

And
 the
 red
 line
 is
 what
 we're

optimizing
 for,
 that's
 the
 time
 to
 first

token.

So,
 when
 we
 started

back
 in
 April,
 you
 could
 see

request
 per
 second
 around
 three,
 which

is
 high
 but
 not
 so
 high.

And
 time
 to
 first
 token
 over
 10
 second,

which
 is
 very
 slow.

All
 of
 the
 data
 that
 you
 see
 is
 the
 same

number
 of
 GPU.
 We
 didn't
 increase
 GPU

count,
 we're
 still
 at
 56.

And
 by
 the
 end,
 you
 see
 in
 August

request
 per
 second,
 we're
 about
 over

seven,
 and
 time
 to
 first
 token
 we're

around
 1.6.
 So,
 we've
 had

88%
 improvement
 in
 performance
 for
 76%

increased
 demand.
</details>

>> [嗤笑声]

>> 所以从中得到的经验是，有很多参数可以进行优化，如果你打算部署并为某些模型提供服务，你确实需要在扩容时认真做好这些。那么我们来聊聊参数。虽然没有秘密配方，但需要考量的有以下几点：
<details>
<summary>Original English</summary>
>> [snorts]

>> So,
 the
 learning
 from
 this
 is
 there's
 a

lot
 of
 parameters
 that
 you
 can

improve
 on,
 and
 you
 really
 need
 to

really
 scaling
 if
 you're
 looking
 to

serve
 for
 some
 model.

So,
 let's
 talk
 parameters.

There's
 no
 secret
 recipe,
 but
 the
 things

to
 consider

are
 the
 following.
</details>

第一点，长上下文是个骗局。你必须清楚意识到，即便你能提供 100 万 Token 的上下文，256（即 256k）才真正是你所需要的。关于量化，如果运行在 Blackwell 代际的 GPU 上，你绝不会想运行高于 FP4 的规格。NVFP4 是最好的。大体上从 FP8 降到 FP4，可以在完全不损失精度的情况下，节省 40% 的 GPU 占用空间。其他需要考量的参数包括张量并行（tensor parallelism）：尽管 GLM 可以在 TP4 上放得下，但你没有足够的 KV cache，所以根据你的工作负载规模，TP8 可能会表现更好。还有一些更深度的技术：检查你的缓存命中率，代码任务的缓存命中率需要达到 90% 以上。此外，你还可以探索优化推测解码（speculative decoding）、顺序预填充（sequential pre-fill）、以及 PGD 等技术。
<details>
<summary>Original English</summary>
First
 one,

long
 context
 is
 a
 scam.

You
 really
 need
 to
 be
 mindful
 that
 even

though
 you
 can
 serve
 1
 million
 token,

256
 256
 is
 really
 what
 you
 need.

Quantization,
 if
 you're
 running

Blackwell
 generation
 GPU,

you
 don't
 want
 to
 run
 anything
 higher

than
 FP4.

And
 VFP4
 is
 best.
 Roughly
 going
 from
 FP4

to
 FP8

is
 a
 40%
 saving
 in
 GPU
 footprint
 for

zero
 loss
 in

uh,
 precision.

Other
 parameters
 to
 consider,
 tensor

parallelism,
 even
 though
 GLM
 fits
 on
 uh,

TP4,

you
 don't
 have
 enough
 KV
 cache,
 and
 so

maybe
 a
 TP8
 works
 better
 depending
 on

how
 large
 your
 workload
 is.

And
 then
 the
 more
 esoteric,

check
 your
 cache
 hit.
 Coding
 test
 needs

to
 be
 above
 90%
 uh,
 cache
 hit.

And
 you
 can
 look
 into
 optimize

spec
 decoding,
 uh,
 sequential
 pre-fill,

PGD
 zag,
 all
 of
 these.
</details>

### 生产架构与多模态路由

很好。现在我们来讨论生产架构部署。GLM 显然是一个纯文本模型，这对某些人来说是个限制。我想说，我们每次都会做出的权衡取舍是：选用更聪明的模型，然后通过其他方式来解决图像识别问题。你可以很容易地搭建一个本地路由器，Open Codex 就是其中一种，你可以把所有图像识别请求路由到 Gemini 或其他视觉模型，而把主要任务保留给核心模型。如果你确实需要视觉模型，GLM-4V Flash 表现就非常不错。我们的 UI 设计师对其利用得很好，UI 产品的交付效率有了极其显著的提升。最后一点是关于测试运行框架（harness）。所有这些端点都将是兼具响应功能的 OpenAI 兼容 API，因此你可以在 Open Code、Codex 以及 Codex 应用程序内部直接使用它们。运转得非常良好，这也是我们所推荐的方案。
<details>
<summary>Original English</summary>
Cool.
 So,
 now
 let's
 talk
 about

production
 setup.

Gnome
 obviously
 is
 a
 text-only
 model,

which
 is
 a
 limitation
 for
 some
 people.

The
 trade-off
 I
 would
 say
 we
 would
 make

every
 time
 is
 get
 the
 smarter
 model
 and

figure
 out
 how
 to
 do
 image
 recognition

another
 way.

You
 can
 easily
 have
 a
 local
 router.
 Open

Codex
 is
 one

where
 you
 would
 route
 any
 image

recognition
 to

Gemini
 or
 Luna

and
 keep
 Gemini
 for
 the
 main
 task.

If
 you
 really
 need
 some
 vision
 model,

Gnome
 5G
 flash

works
 really
 well.
 We
 have
 our
 UI

designer

making
 great
 use
 of
 it.

Turnaround
 for

UI
 product
 has
 gone
 a
 really,
 really

long
 way.

And
 then
 the
 last
 one
 is
 going
 to
 be

about
 the
 harness.

So,
 all
 of
 these
 endpoints
 are
 going
 to

be
 OpenAI
 compatible
 API
 with
 response

API
 and
 so
 you
 can
 use
 them

inside
 Open
 Code

Codex

Codex
 app
 as
 well.
 Works
 really
 well.

And
 so,
 that's
 what
 we
 we
 recommend.
</details>

### 合规、安全与数据隐私

最后一条信息，这是留给在场的首席信息官（CIO）们的。关于使用源自中国的开源模型，过去存在许多顾虑与负面看法。需要考虑的是，你并不是在调用直连中国的专用推理端点。你只是获取模型权重，并将它们部署在美国本土的服务器上。因此在数据共享层面，这完全没有问题。Revolut 的情况尤为特殊，因为我们是一家受欧盟监管的银行，遵从合规方面最严格的监管机制。我们发现切实可行的做法是：所有这些编码任务都不被视作自主 Agent。它们始终处于人机协同（human in the loop）的状态。那么，你该如何向监管机构证明有人在回路中监督呢？首先要建立一个能确保这一点的沙箱。这个沙箱意味着——如果大家用过 Codex code 的话，它提供了各类“需我审批”的功能。你只需要针对那些不允许的操作制定规则即可。例如，你可以允许 grep 命令，但不允许执行 Gradle。这能给监管机构带来信心，证明这不是需要接受不同监管规则的自主 Agent。
<details>
<summary>Original English</summary>
And
 then

last
 message,
 this
 one
 is
 for
 the
 CIO
 in

the
 room.

There's
 been
 a
 lot
 of
 stigma
 in
 using

Chinese
 open
 source
 model.

So,
 the
 thing
 to
 consider
 is
 you're
 not

using

the
 inference
 dedicated
 endpoint
 that

goes
 to
 China.
 You
 just
 getting
 the

weights
 and
 putting
 them
 on
 a
 US-based

service.

So,
 for
 data
 sharing
 side,
 this
 is

totally
 fine.

Revolut
 in
 particular,
 because
 we're
 a

EU
 regulated
 bank,
 we
 fall
 under
 the

most

strict
 regime
 in
 terms
 of
 compliance.

And
 so,
 what
 we
 find
 that
 works

is

all
 of
 these
 coding
 tasks
 are
 not

considered
 autonomous
 agents.

They're
 always
 with
 a
 human
 in
 the
 loop.

And
 so,
 how
 do
 you
 give
 uh
 reassurance

that
 you
 have
 a
 human
 in
 the
 loop?

You
 start
 by
 creating
 a
 sandbox
 that

guarantees
 that.
 And
 the
 sandbox
 means

now,
 if
 you've
 used
 Codex
 code,
 it
 has

all
 of
 these
 features
 of
 approve
 for
 me.

You
 just
 have
 to
 set
 the
 rules
 for
 the

operations
 that
 you
 don't
 want
 to
 allow.

So,
 you
 can
 allow
 grab
 but
 not
 Gradle,

for
 instance.

And
 that's
 going
 to
 give
 confidence
 uh

to
 your
 regulator
 that

this
 is
 not
 an
 autonomous
 agent
 that

needs
 different
 uh
 supervision.
</details>

沙箱同样可以保护你免受内部恶意行为的侵害，对吧？公司内部可能会有不良行为者，你需要为此进行防范。大公司里能发现些什么往往会出乎你的意料。最后一点是提示词注入。鉴于现在的模型非常聪明，这虽然不再是一个大问题，但它始终是一个隐患。在数据隐私方面，前面我们已经谈到过。只要数据存放在符合数据等效性框架的国家或地区内——即美国、欧盟、英国、以色列——就完全没有问题，你就可以在那里使用数据。所有你的推理提供商或 GPU 提供商默认都会实施零数据留存政策。最后，你还需要一套非常强大的 OpenTelemetry 可观测性系统，这样一旦发生事故，你必须能够深入查看日志。它同时也能为你提供相关的分析数据。好的，谢谢大家。以上就是我的全部演讲内容。

>> [掌声]
<details>
<summary>Original English</summary>
The
 sandbox
 also
 protects
 you
 from
 uh

rogue
 use,
 right?
 You
 may
 have
 bad
 actor

inside
 your
 company,
 and
 you
 want
 to

shield
 uh
 for
 that.

You
'd
 be
 surprised
 what
 you
 find
 in
 a

large
 company.

And
 then,
 the
 last
 one
 is
 prompt

injection.
 Not
 not
 so
 much
 a
 thing
 uh

now
 given
 how
 smart
 models
 are,
 but

always
 a
 thing.

In
 terms
 of
 data
 privacy,
 we
 spoke
 about

it.
 So,
 as
 long
 as
 the
 data
 sits

in
 one
 of
 the
 countries
 that
 are
 in
 the

data
 equivalency
 framework,
 so
 US,
 EU,

UK,
 Israel,

you're
 fine.
 You
 can
 get
 your
 data
 to
 be

used
 there.

All
 of
 your
 inference
 provider
 or
 GPT

provider
 are
 going
 to
 have

zero
 data
 retention
 by
 default.

And
 then,
 the
 last
 thing
 you
 need
 is
 a
 very
 strong
 uh
 open
 telemetry
 so
 that
 if

you
 ever
 have
 an
 incident,
 um
 you
 need

to
 be
 able
 to
 go
 deep
 uh
 and
 look
 at
 the

logs.

Also
 gives
 you
 some
 uh
 yeah,
 analytics.

All
 right.
 Thanks,
 everyone.
 That
 was

all
 for
 my
 talk.

>> [applause]
</details>