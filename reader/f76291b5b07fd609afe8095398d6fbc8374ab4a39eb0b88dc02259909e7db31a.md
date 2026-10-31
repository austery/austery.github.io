---
author: AI Engineer
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=P_0_Th_ZzIg
speaker: AI Engineer
tags:
  - llm-serving
  - benchmarking
  - cloud-computing
  - inference-optimization
title: 停止盲猜 vLLM 配置：在 RunPod 上基准测试与自托管大模型
summary: RunPod 前向部署工程师 Chris Vela 分享了如何在云端进行 vLLM 配置基准测试，介绍了内部研发的模板工具 BenchPod，通过实测并发与批处理 token 优化吞吐与延迟，帮助团队基于真实数据从研发平稳过渡到生产环境。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Chris Vela
companies_orgs:
  - RunPod
products_models:
  - vLLM
  - BenchPod
media_books: []
status: evergreen
---
### 告别盲猜：大模型生产化落地的配置痛点

我叫 Chris Bella（Chris Vela）。我在 RunPod 工作，是一名现场部署工程师（forward deploy engineer）。今天我将探讨关于对 VLM（vLLM）进行基准测试的话题。主要是聊聊大家在面对新模型推出时所经历的那些挣扎，以及我们在 RunPod 内部与客户合作过程中积累的一些经验。

今天我基本上会向大家展示一个构建在 VLM 之上的仪表板。它实际上使用的是我们自己的 Pods。为了给大家补充一些关于 RunPod 业务的背景：我们处于新型云平台领域，致力于让租用 GPU 变得非常非常容易，覆盖从研发阶段一直到面向生产的服务工作流。很多时候，我看到客户在使用 VLM 时，往往想要最新的模型，却不知道如何启动它；或者他们想开始推向生产环境，却不知道该调整哪些参数旋钮。他们只是直接使用默认的基础配置。我猜在座很多人以前可能见过类似 VLM recipes（配置配方）的东西。这是一个很好的起点，但尤其是在如今这个快速变化的领域，我们始终在高速前进。

那么，你该如何达到更具生产级水准的代码，同时又不仅仅是凭感觉去猜（vibing it）？更重要的是，你如何真正拿到数据？你如何向你的主管或主任工程师证明“这个配置确实更好、这确实在正确工作”？
<details>
<summary>Original English</summary>
[music]

>> My
 name
 is
 Chris
 Bella.
 I
 work
 at

RunPod.
 I'm
 a
 forward
 deploy
 engineer.

Today
 I'm
 going
 to
 be
 talking
 about

benchmarking
 VLMs.
 Kind
 of
 like
 the

struggle
 that
 people
 have
 when
 like

especially
 like
 a
 new
 model
 comes
 out.

Just
 some
 like
 learnings
 that
 we've
 had

like
 internally
 at
 RunPod
 and
 with
 like

customers.

So
 today
 I'm
 going
 to
 be
 showing
 you

essentially
 like
 a
 dashboard
 that
 is

built
 on
 top
 of
 like
 VLM.

It's
 using
 our
 like
 pods
 actually.
 So
 to

give
 you
 like
 a
 little
 more
 context
 of

like
 what
 RunPod
 does
 is
 we're
 in
 the

new
 cloud.

We
 make
 it
 really
 really
 easy
 for
 you
 to

rent
 GPUs

and

starting
 from
 like
 R&D
 to
 like
 more

service
 production
 workflows.
 A
 lot
 of

times
 what
 I
 see
 with
 customers

especially
 with
 VLM
 is
 like
 someone

wants
 you
 know
 the
 latest
 model.
 They

don't
 know
 how
 to
 like
 spin
 it
 up
 or

they
 they
 want
 to
 start
 going
 to

production
 and
 they
 don't
 know
 the
 the

knobs
 to
 like
 touch.
 They're
 they're

just
 using
 whatever
 like
 the
 base
 config

and
 I'm
 guessing
 a
 lot
 of
 you
 probably

seen
 like
 VLM
 recipes
 before.

You
 know
 it's
 a
 good
 start
 especially

but
 like
 especially
 in
 this
 world
 we're

always
 moving
 fast.

So
 how
 do
 you
 get
 to
 more
 production

level

style
 of
 code
 and
 at
 the
 same
 time
 not

just
 like
 vibing
 it.
 It's
 more
 like
 how

do
 you
 actually
 have
 data?
 How
 do
 you

show
 you
 know
 your
 manager
 like
 your

staff
 engineer
 that
 hey
 this
 is
 actually

better.
 This
 is
 actually
 working

correctly.
 So
</details>

所以我真正想说的是，我见过太多人全都在靠猜。很多时候我看到大家用错了 VLM 的版本，他们可能没有使用 nightly 版本；他们的上下文窗口大小设置错误。

这真的取决于实际需求。我认为始终需要往回退一步来看：你希望用你的语言模型达成什么目标？它将作为一个编程智能体（coding agent）吗？还是说更偏向于仅做一些摘要之类非常基础的任务？在盲目引入拥有百万长上下文的模型之前，这通常是我会先问的第一个问题——因为那并不总是必要的。

与此同时，还要考虑会有多少用户来使用它？很多时候大家的做法是，每个人都在试图用最便宜的价格获取最小规格的 GPU。但如果你要面对更高并发的用户，你就必须开始思考：我该如何有效利用 KV cache（键值缓存）？

因此，在走向生产之前，所有这些细微的优化参数都需要你去摸索清楚。而在很多时候，我们都在争取快速推进。

正如我所说，RunPod 把它做得非常简单，就像虚拟机一样，它是 Docker 化的，你可以自带镜像。但归根结底……在座的各位谁以前用过 VLM？
<details>
<summary>Original English</summary>
really
 what
 I'm
 trying
 to
 say
 is
 like

I've
 seen
 a
 lot
 everyone's
 just

guessing.
 Like
 you
 know
 you're
 a
 lot
 of

times
 I
 see
 people
 are
 using
 the
 wrong

VLM
 version.
 They
 might
 they're
 probably

not
 using
 like
 the
 nightly
 version.

They
 have
 the
 wrong
 size
 for
 their

context
 window.

It
 really
 depends
 like

I
 I
 think
 it
 always
 is
 a
 step
 back.
 It's

like
 what
 are
 you
 trying
 to
 achieve
 with

your
 your
 LM
 model?
 Are
 you
 is
 it
 going

to
 be
 a
 coding
 agent?
 Is
 it
 more
 kind
 of

like
 you're
 just

um
 you
 know,
 doing
 summaries,
 like
 very

very
 basic
 tasks.
 That's
 usually
 the

first
 question
 I'd
 be
 asking
 before
 you

you
 know,
 getting
 Kim
 K
 3,
 having
 you

know,
 a
 million
 long
 context.
 Like

that's
 not
 always
 necessary.

Uh
 and
 at
 the
 same
 time
 it's
 like
 how

many
 users
 are
 going
 to
 be
 using
 this?

Um

a
 lot
 of
 times
 people
 are
 like
 going

everyone's
 trying
 to
 always

get
 like
 the
 the
 smallest
 amount
 of
 GPU

for
 the
 cheapest
 price.
 But
 if
 you're

going
 to
 be
 going
 to
 a
 more
 concurrent

users,
 you
 need
 to
 start
 thinking
 about

like
 how
 am
 I
 going
 to
 be
 utilizing
 the

KB
 cache?

Uh
 so
 all
 this
 is
 there's
 all
 these

little
 like
 optimization
 knobs
 that
 you

need
 to
 like
 figure
 out
 before
 you
 go
 to

production.
 And
 a
 lot
 of
 times
 we're

trying
 to
 move
 fast.
 So
 um

Yeah,
 like
 like
 I
 said,
 like
 RunPod
 like

we
 like
 have
 very
 much
 like,
 you
 know,

we
 make
 it
 very
 very
 easy.
 It's
 like
 a

VM.
 Uh
 it's
 dockerized.
 Uh
 you
 can
 bring

your
 own
 image.
 But
 at
 the
 end
 of
 the

day
 like
 um

like
 who
 here
 has
 used
 like
 v
 l
 m

>> before?
</details>

### 版本兼容性与 BenchPod 的推出

>> 好的。你看，当你在寻找支持特定模型（比如 Kim K 3）的环境时，如果你使用的版本类似 0.27，它是无法正常运行的。技术迭代如此之快，代码往往跟不上最新的变化。你必须具备正确的版本。很多时候这就会演变成一种持续集成/持续交付（CI/CD）的流程，对于不了解底层细节的人来说，就会开始陷入困境。他们会看到各种报错并困惑：“为什么跑不通？”因为其中的某些网络层还没有编写完，或者代码还处于高度开发中的状态。

与此同时这也是个现实问题：比如新模型刚出来，第二天我绝不会直接把它部署到生产环境。你可能会遇到大量的幻觉问题，可以说它在那种状态下还没准备好。

所以我提出的方案是——我创建了一个名为 **BenchPod** 的东西。它将作为一个模板推出，目前尚未正式上线。

它本质上是构建在 VLM 之上的整套指标系统，让你能非常轻松地进行基准测试。熟悉 VLM 的人都知道原生就可以做测试，但 BenchPod 将一切集中化了，让你能总览所有信息，并且能非常迅速地调整配置。
<details>
<summary>Original English</summary>
>> Okay,
 so

you
 know,
 like
 when
 you're
 looking
 for

like
 like
 especially
 like
 Kim
 K
 3,
 like

if
 you
 you
 use
 like
 a
 version
 of
 like,

you
 know,
 0.27,
 it's
 not
 going
 to
 be

working.
 Like

like
 we're
 moving
 so
 fast
 the
 code
 is

not
 getting
 as
 fast.
 Like
 you
 need
 to

have
 the
 right
 version.
 And
 a
 lot
 of

times
 that
 turns
 into
 kind
 of
 like
 a
 CD

CI
 CD
 process
 that

um
 especially
 if
 people
 who
 don't

understand
 what's
 happening
 uh
 just

start
 struggling.
 They
 they
 start
 seeing

errors
 and
 they're
 like,
 "Why
 is
 this

not
 working?"
 You
 know,
 it

the
 the
 layers
 within
 it
 are
 not
 they

haven't
 been
 written
 or
 they're
 it's

very
 in
 development
 code.

Uh
 and
 at
 the
 same
 time
 that's
 actually

kind
 of
 a
 problem
 is
 like
 Kim
 K
 3
 comes

out,
 you
 know,
 the
 next
 day
 I
 would
 not

put
 that
 on
 production
 just
 yet.
 Uh

you're
 going
 to
 be
 seeing
 a
 lot
 of

probably
 hallucinations.
 Uh
 it's
 just

not
 ready
 in
 that
 state,
 I
 would
 say.

Um
 so
 what
 I
 propose
 um
 so
 uh
 I
 created

this
 thing
 called
 it's
 called
 BenchPod.

It's
 going
 to
 be
 a
 template.
 It
 hasn't

come
 out
 yet.

Um
 so
 it's
 essentially
 built
 on
 top
 of

like
 uh
 v
 l
 m.
 Um
 it's
 a
 whole
 metric

system.
 Uh
 you
 can
 benchmark
 very
 easy.

And
 a
 lot
 of
 you
 who
 are
 familiar
 with

like
 v
 l
 m
 you
 can
 benchmark
 already,

but
 this
 kind
 of

um
 centralizes
 everything,
 so
 you
 can
 be

able
 to
 see
 everything,
 be
 able
 to

change
 the
 config
 very
 quickly.
 Uh
</details>

这是我特别注意到的一个关键痛点：使用我们 Pod 的用户在设定好一个配置后，往往必须重启镜像并等待冷启动发生。在这个过程中伴随着各种加载等待，导致你无法快速迭代。你可能要等上 30 分钟让模型下载权重并加载到 GPU 中，这纯粹是在浪费时间。当然，如果你运行的是自动化智能体，你可能不在意等待，但在大家都在力求敏捷的当下，这确实是个痛点。

与此同时，RunPod 的优势在于你能找到所需的各种硬件设备。如果你有疑问，比如“我想在 B300 上跑这个模型”，我们拥有 B300 算力，你可以不再仅仅停留在纸面上阅读评测，而是能实际动手测试，去验证所有这些指标是否真实。

所以正如我所说，BenchPod 就像是一个基于 VLM OpenAI 接口打包的 Docker 镜像。我们将内置所有版本。我们附带了一个轻量级载荷，基本构建了这整套 FastAPI 应用程序，你可以将其直接对接给你的智能体使用。很酷的一点在于，你可以指定想要托管的服务模型，并且我们内建了完整的看门狗（watchdog）机制来实现自愈。因此，如果你真正开始迈向生产级别，完全不必为此担忧。稍后我会向大家展示：就在刚刚过去的周日，我们实例上的模型出现过故障，随后系统自动完成了自愈。我们当前有 4 个节点在运行它，因此我们的内部用户没有受到任何影响。它已经达到了生产就绪的状态，不需要过多操心。归根结底，它让构建生产工作流变得简单得多。
<details>
<summary>Original English</summary>
that's
 like
 a
 very
 important
 thing
 that

I
 I
 notice
 is
 that
 uh
 especially
 with

people
 who
 use
 like
 our
 uh
 our
 pods
 is

you
 set
 up
 a
 config,
 but
 then
 you
 have

to
 restart
 the
 image.
 You
 have
 to
 wait

for
 cold
 starts
 to
 happen.
 It's
 all
 this

loading,
 and
 you're
 not
 moving
 as
 fast.

You're
 waiting
 like
 30
 minutes
 like
 for

Kim
 A
 I
 3
 to
 like
 download
 the
 weights,

load
 into
 GPU.
 Uh
 it's
 kind
 of
 wasted

time.
 I
 mean,
 if
 you
 have
 an
 agent,
 you

know,
 you
 really
 don't
 care,
 but
 um

that
 is
 a
 pain
 point
 especially
 when

we're
 trying
 to
 move
 fast.
 And
 at
 the

same
 time
 it's
 like
 the
 cool
 thing
 about

Runpod
 is
 you
 can
 find
 these
 machines.

So,
 if
 you
 have
 that
 question,
 it's
 like

I
 want
 to
 run
 Kim
 A
 I
 3
 on
 a
 B300,
 we

have
 B300s,
 and
 you
 can
 start
 going
 from

like
 not
 just
 like
 reading
 about
 it.
 You

can
 actually
 start
 testing
 it
 and
 seeing

if,
 you
 know,
 there's
 truth
 to
 all
 these

metrics.

So,
 yeah,
 so
 like
 bench
 like
 like
 I

said,
 like
 bench
 pod
 is
 more
 like

um
 it's
 it's
 built
 like
 a
 of
 a
 a
 docker

image
 of
 um

um
 v
 l
 m
 open
 a
 b
 i.
 We're
 going
 to
 be

having
 every
 version
 already.
 Um

we
 just
 have
 a
 little
 like
 like
 payload

that
 like
 pretty
 much
 creates
 this
 whole

fast
 a
 p
 i
 application.
 Uh
 you
 can
 use

it
 for
 your
 agents.
 Uh
 the
 cool
 thing
 is

you
 can
 serve
 uh
 you
 can

pretty
 much
 specify
 which
 uh
 models
 you

want
 to
 have.
 We
 have
 a
 whole
 watchdog,

too,
 so
 it
 like
 self-heals,
 too.
 So,
 uh

if
 you
 were
 actually
 starting
 to
 go
 to

more
 production
 levels,
 uh
 you
 can

actually
 uh
 you
 don't
 have
 to
 worry

about
 it.
 And
 then
 like
 I
 will
 show
 you

uh
 like

this
 past
 Sunday
 uh
 Kim
 A
 I
 went
 down
 on

our
 instance,
 and
 it
 uh
 self-healed.

And,
 you
 know,
 we
 have
 we
 have
 right
 now

like
 four
 nodes
 running
 it,
 so
 none
 of

like
 our
 internal
 users
 saw
 any
 problem.

It
 was
 a
 production
 ready
 um
 didn't
 have

to
 like
 think
 about
 it
 too
 much.
 And
 at

the
 end
 of
 day,
 yeah,
 like
 it's

it
 it
 makes
 it
 much
 more
 sim-
 uh
 simple

process
 to

uh
 have
 production
 work
 workflows.
</details>

### 指标系统与控制台演示

我猜很多人对这个模型都很熟悉，所以我将拿 Kim and K3（Kimi k1.5 / K3）来演示，因为我们一直在高频使用它。大家都知道它支持 100 万上下文。但有趣的是，在单张 B300 上其实跑不到 100 万，只能用到大约一半。不过我们团队特别注意到的一点是，我们大量将其用于编程智能体，在完成长任务方面这个容量已经非常充裕了。而且它对 KV cache 的利用也极其出色，所以在首字时间（time to first token）的响应速度上非常非常快。在接下来的演示中，我也会展示让我的编程智能体调用在 RunPod 上运行的该模型。

这就是我们的仪表板。它包含非常多的指标，看起来可能有点繁杂，但本质上我们始终围绕着 GPU 指标来考量，并监控你当前使用的 CUDA 版本，这一点非常重要——如果你运行它在 CUDA 12.8 下跑不通，但可以在 13.0 下正常工作。

我们提供的最佳功能在于可以查看基准测试、审视所有数据，还能在 Playground 里进行交互测试。因此在将模型接入编程智能体或直接请求 OpenAI 响应接口之前，你可以立即测试验证它是否运转正常。这里还涵盖了许多 CI/CD 相关的流程观测，比如“冷启动到底需要多久？”以及“在实际真实流量下我的指标表现如何？”
<details>
<summary>Original English</summary>
So,
 I'm
 guessing
 a
 lot
 of
 people
 I'm
 I'm

going
 to
 show
 you
 Kim
 and
 K3
 because

we've
 been
 using
 that
 a
 lot.

Um

I'm
 guessing
 a
 lot
 of
 people
 here
 are

very
 familiar
 with
 Kim
 and
 K3.
 Um

so,
 you
 know,
 1
 1
 million
 contacts.
 Uh

one
 thing
 that's
 interesting
 on
 1B
 300,

uh
 can't
 get
 to
 the
 1
 million.
 You
 got

to
 use
 half
 of
 it.
 But
 one
 one
 thing

I've

noticed
 especially
 with
 our
 team,
 like

we're
 using
 it
 a
 lot
 for
 coding

uh
 agents.

Um
 that
 is
 very
 much

um

enough
 to
 do
 long
 task.
 Um
 It's

utilizing
 KB
 cache
 uh
 very
 well,
 too.

So,
 um
 in
 terms
 of
 speed
 of
 like
 time
 to

first
 second,
 um

it
 is
 very
 very
 very
 quick.
 And
 like
 in

the
 demo,
 I'll
 show
 you
 too
 with
 like
 my

coding
 agent
 running
 this
 Kim
 and
 uh

model
 on
 RunPod.

So,
 this
 is
 like
 our
 dashboard.

Um

It
 has
 a
 lot
 of
 metrics.
 You
 know,
 it

can
 it
 look
 looks
 like
 a
 lot,
 but
 uh

essentially,
 you
 know,
 we're
 always

thinking
 about
 like
 the
 GPU,
 like,
 you

know,
 have
 a
 lot
 of
 like
 GPU
 uh
 metrics,

you
 know,
 and
 what
 CUDA
 version
 you're

on,
 which
 is
 very
 very
 important.
 You

know,
 if
 you're
 running
 Kim
 and
 it

doesn't
 work
 on
 a
 12
 8
 CUDA,
 it
 works
 on

13.0.

Uh
 and
 really
 it's
 what
 we
 have
 is
 like

the
 best
 we
 can
 we
 we
 can
 look
 at

benchmarking,
 look
 at
 all
 our
 data,
 we

can
 like
 playground
 with
 it.
 So,
 like

before
 you
 even
 put
 it
 into
 your
 like

coding
 agent
 or
 uh
 just
 hitting
 the

OpenAI
 uh
 response,
 you
 can
 start

testing
 real
 quick
 if
 this
 is
 working.

And
 just
 a
 lot
 of
 like
 more
 CICD
 process

of
 like,
 you
 know,
 how
 long
 are
 my
 cold

starts
 happening?

Um
 how
 are
 how
 are
 my
 metrics
 looking
 um

through
 actual
 traffic?
</details>

现在我给大家展示现场演示。

我先带大家快速看一下 RunPod 平台本身。目前这个模板还没完全就绪，如我所说大概会在月底上线。本质上我们只需填入一个 Docker 镜像就可以部署在这里。虽然当前界面显示没有可用的 B300，但我手上正运行着一台。在这一行工作有趣的一点就在于：硬件供应往往会有波动。

>> [笑声]

>> 但从部署体验来说，我们把它做得极其简单：你可以挂载存储卷，然后进行部署；我们还有定时排队部署功能，只要算力空出来就会自动启动。整个过程基本就是点击按钮，BenchPod 随之启动。

我展示一下当前正在实际运行的实例。这里具备完善的错误扫描，让你拥有真实数据了解运行状况。同时我们还支持随任务运行的实时指标，所有数据都会备份到持久化存储中。这一切都是基于 FastAPI 的调用，所以你的智能体可以很轻松地抓取所有这些数据并完成模型分发，你甚至根本不需要使用 UI 界面。

作为智能体落地的坚定支持者，我依然希望能掌握系统的实际运行状况，而这个工具为我提供了一个俯瞰全局的视角，清晰监控 K3 实例的运行情况。在这个界面上可以看到，上个周末我们遭遇了一次 GPU 故障，随后成功修复；冷启动耗时大约 9 分钟，对于这类大模型来说算是相当不错的成绩。
<details>
<summary>Original English</summary>
So,
 I'm
 going
 to
 show
 you
 guys
 the
 demo.

So,

So,
 really
 like
 I'm
 going
 to
 show
 you

real
 quick
 like
 RunPod
 itself.
 So,

um

this
 will
 So,
 we
 don't
 have
 this
 set
 up

yet.
 Like
 I
 said,
 um
 it'll
 be
 up

probably
 at
 the
 end
 of
 the
 month.
 Uh
 but

really
 all
 we
 have
 is
 just
 like
 a
 Docker

image.
 We
 can
 be
 able
 to

uh
 put
 that
 in
 right
 there.

If
 it
 loads
 correctly.
 But
 uh
 Uh,
 yeah,

so
 right
 now
 there's
 no
 B300s,
 but
 uh,
 I

have
 one
 running
 right
 now.

That's
 the
 fun
 thing
 about
 working
 in

this
 industry.

Uh,

you
 know,
 uh,
 supply
 can
 be
 uh,

dependent.
 Uh,
 but

>> [laughter]

>> But
 yeah,
 it's

in
 in
 the
 sense
 of
 that
 like,
 you
 know,

we
 make
 it
 really
 easy.
 You
 can
 put

storage
 volume.
 Uh,
 you
 deploy
 it,
 you

know,
 we
 have
 a
 part
 two
 so
 you
 can

deploy
 when
 you're
 available.
 So,
 you

know,
 if
 you
 were
 seeing
 the
 screen
 like

this,
 it
 will
 deploy
 whenever

it
 get
 it
 get
 started.

Uh,
 so
 that's
 like
 literally
 the

process.
 You
 click
 that
 button,
 benchpod

like
 starts
 up.

Um,

and
 I
 can
 show
 you
 like
 right
 here.

I
 have
 it
 on
 the
 wrong
 one,
 but
 I'll

show
 you
 guys
 here.
 So,
 like
 this
 is

like
 this
 is
 our
 actual
 like
 Kimi

running
 currently.

Um,
 so
 a
 cool
 thing
 is
 like

you
 know,
 you
 you
 start
 like
 it
 has
 a

whole
 air
 scan
 so
 you
 have
 actual
 data

to
 know
 like
 what
 is
 happening.
 Um,

cool
 thing
 is
 we
 have
 live
 metrics,
 too.

As
 like
 things
 are
 running.
 Uh,

all
 of
 this
 is
 also
 like
 backed
 up
 in

like
 storage
 data.
 So,
 like
 it's
 all

um,

um,
 backed
 up
 no
 matter
 what.
 Um,
 it's

all
 face
 fast
 API
 calls
 so
 your
 agent

could
 easily
 just
 call
 all
 this
 data.

You
 can
 actually
 just
 serve
 everything.

Like
 you
 don't
 even
 have
 to
 use
 the
 UI.

I
 I
 think
 I'm
 a
 big
 proponent
 of
 like
 as

we
 go
 to
 agents
 it's
 like
 I
 still
 want

to
 have
 like
 some
 awareness
 of
 what's

happening
 and
 having
 this
 gives
 me
 a

good
 like
 like
 eagle's
 eye
 view
 of
 like

what
 is
 happening
 with
 my
 uh,
 Kimi
 K3
 K3

instance.
 Uh,
 but
 yeah,
 like
 you
 can
 see

here
 like
 I
 was
 going
 to
 show
 you
 like

uh,
 this
 past
 weekend
 we
 had
 a
 failure

with
 a
 GPU.
 Uh,
 we
 were
 able
 to
 fix
 it,

but
 uh,
 being
 able
 to
 just
 do
 a
 cold

start
 time
 like
 9
 minutes
 on
 it
 like
 K3s

pretty
 pretty
 good.
</details>

### 参数调优：批处理 Token 与吞吐延迟权衡

这里很酷的一点是我们具备模型分发功能，你可以启动各种对比实验，点击应用后系统会极速重启生效。这里的配置纯粹就是 VLM 的 YAML 配置文件。在这个小演示中我测试的是调整每次发送的批处理 token 最大数量（max number of batched tokens）。

我想向大家展示这样调优能带来怎样的加速效果。我之前已经跑过了这些测试，省得大家在这干等 20 分钟看基准测试跑完。这些测试是以不同的并发量运行的，分别从单个并发用户开始，逐步递增到 8、64 和 192 个并发。而且我们能够很直观地把多次运行的结果并排进行对比。

你可以看到，仅仅增加批处理 token 数量，对首字延迟并没有太大改变。但我注意到的一个有趣现象是：**增加批处理 token 数量后，Token 间延迟（inter-token latency）实际上显著降低了**。这意味着对于整个请求来说，特别是运行长任务时，其完成速度相比 VLM recipe 中的默认基础配置要快得多。

你可以把这套流程接入智能体并开始大规模探索，从而更快拿到评测结论，基于真实数据把服务从单 Pod 平滑迁移到多节点集群。
<details>
<summary>Original English</summary>
Um,

and
 the
 cool
 thing
 here
 is
 that
 we
 have

the
 serve
 so
 you
 can

start
 out
 experiments
 and
 essentially

like

apply
 them.
 It'll
 restart
 real
 quick.

Um,
 you
 can
 it's
 literally
 just
 like
 the

config
 YAML
 file
 from
 like
 VLM.
 And
 um,

so
 like
 for
 this
 like
 little
 demo
 what
 I

tested
 was
 we
 were
 just
 changing
 the
 max

number
 of
 batch
 tokens
 uh,
 that
 were

sent
 through.

And
 I
 kind
 of
 wanted
 to
 show
 you
 guys
 of

like,
 you
 know,
 what
 what
 kind
 of
 like

speed
 ups
 would
 happen
 with
 this.
 Um

I'll
 go
 right
 here.

So,
 I
 run
 these
 before
 because
 we're
 not

going
 to
 spend
 like
 20
 minutes
 just

looking
 at

benchmarks.
 So,
 these
 benchmarks
 are

running
 like
 concurrency.
 So,
 they're

they're
 running
 um

you
 know,
 starting
 with
 like
 just
 one

concurrent
 user
 and
 then
 eight,
 64,
 192.

And
 the
 cool
 thing
 is
 like
 we
 can
 be
 at

we
 can
 actually
 compare
 multiple
 runs

against
 each
 other.

You
 can
 kind
 of
 see
 like
 even
 just

increasing
 the
 match
 the
 the
 number
 of

batch
 tokens
 doesn't
 really
 change
 that

much
 the
 like
 time
 to
 first
 second.

But,
 interesting
 thing
 that
 I
 did
 notice

of
 increasing
 that
 is
 like
 the
 inner

token
 latency
 actually
 decreases
 quite
 a

bit
 when
 you
 increase
 that

batch
 tokens.

Which
 means
 it's
 like
 the
 request

itself,
 if
 it's
 especially
 running
 like

a
 long

like
 job
 essentially,

it's
 actually
 much
 faster
 finishing
 the

job
 than
 the
 base
 like
 config
 that
 like

you
 find
 on
 VLM
 recipe.
 The
 cool
 thing

is
 is
 like
 you
 can
 add
 this
 to
 an
 agent

and
 just
 start
 going
 crazy
 with
 it.
 And

you
 can
 start
 getting
 those
 answers
 much

much
 quicker,

have
 the
 data,
 and
 move
 from
 this
 if
 you

have
 it
 like
 on
 a
 pod,
 you
 can
 start

moving
 to,
 you
 know,
 a
 multi-node

cluster.
</details>

你也可以迁移到 Serverless 架构。如果你需要随负载进行弹性伸缩，这是获取真实数据的绝佳方式。谈到我们的 Serverless，很多人会犯同样的毛病：直接套用默认的基础配置，然后苦苦等待 Worker 节点启动。而通过基准测试拿到一手真实数据后，你就能胸有成竹地面向生产部署，一切变得极其简单。正如我常说的，凡事都要以事实为依据。

大家可以在这里看到实际的调用情况，比如我输入“what is a bench pod？”（抱歉我拼错了），可以看到命令行实例在快速响应。目前我们内部大概有 50 位用户在使用该实例，我们大多数人都摆脱了外部商业云接口，直接使用它。我们也有其他实例运行 GLM、DeepSeek、Qwen（Quant 3.8）等模型。未来我们希望探索更智能的路由方案（smart routers），实现在不依赖第三方的同时自托管全部模型。
<details>
<summary>Original English</summary>
You
 can
 move
 to
 serverless,
 too.
 So,
 if

you're
 going
 to
 be
 like
 scaling
 up
 and

down

that
 that
 this
 is
 a
 perfect
 way
 of
 like

actually
 getting
 data.
 And
 just
 to
 give

you
 like
 a
 context
 on
 our
 serverless,

like
 serverless
 a
 lot
 of
 people
 will
 do

the
 same
 thing.
 They
 they
 just
 put

whatever
 the
 base
 config
 is
 and
 then
 are

struggling
 as
 like
 they're
 waiting
 for

workers
 to
 start
 up.

This
 actually
 gets
 you
 the
 real
 data.

You're
 now
 ready
 to
 go
 to
 production.

Makes
 it
 really
 really
 simple.

And
 just
 gives

It's
 like
 I
 always
 say,
 it's
 basing

everything
 in
 facts.
 And

I
 can
 like
 show
 you
 guys
 right
 here.

Like
 this
 is
 actually
 like
 Kenny

writing.
 So
 I
 was
 just
 like,
 what
 is
 a

bench
 pod?

I
 misspelled
 it.
 Sorry.

But
 that
 this
 is
 little
 command
 instance

running
 through
 it.
 Um

yeah,
 and
 Um
 you
 know,
 it
 is
 pretty

pretty
 quick.
 Like
 like
 I
 would
 say
 like

there's
 like
 a
 probably
 like
 50
 users

right
 now
 on
 our
 internal
 one
 and
 we

most
 of
 us
 are
 getting
 off
 cloud
 and

just
 using
 the
 and
 we
 have
 other

instances
 with
 like
 GLM,
 uh
 deep
 seek,

uh
 quant
 3.8.
 Um
 but
 yeah,
 like
 I
 think

in
 the
 future
 we're
 looking
 to
 more
 at

like
 smart
 routers.
 Like
 how
 how
 do
 we

host
 all
 this
 without
 being
 reliant
 on

someone
 else?

Um

Yeah,
 so
 let
 me
 go
 back
 to
 our
 uh

thing
 real
 quick.
 So
</details>

### 从研发到生产的选型与成本考量

回到我们的幻灯片，上面列出了一些核心数据，大家有需要的话可以拍照留存。正如我所提到的，你完全可以自定义实验负载——如果你预计将有 500 人持续并发访问，你可以精确模拟并观察它的表现。

但归根结底，核心问题依然是**我们如何完成从研发到生产的跨越？**我认为这正是 BenchPod 能为大家带来便利的地方。

总结起来，我希望大家记住的流程是：
1. 挑选一个 Pod，获取相应的 GPU 算力机器；
2. 选定你的模型，对比多套配置——千万不要直接依赖 VLM recipe 上线，它经过了验证但并非生产就绪；
3. 执行测试——让你的智能体去跑自动化测试；
4. 根据具体需求，无论是 ITL（Token 间延迟）、TTFT（首字时间）还是 TPOT（每输出 Token 时间），针对关键指标进行优化；
5. 最终交付胜出的配置——部署上线并实现服务扩缩容。现在你就拥有了一个真正可用的大语言模型，无论供内部团队还是外部业务使用。
<details>
<summary>Original English</summary>
some
 like
 important
 data
 like
 we
 were

just
 talking
 about
 it.
 If
 anyone
 wants

to
 screenshot
 that.
 But
 uh

Like
 I
 said,
 like
 you
 can
 you
 can

specify
 the
 experiment
 yourself
 too.
 So

if
 you
 were
 like,
 I'm
 going
 to
 have
 like

500
 people
 using
 this
 all
 the
 time.
 Like

I
 want
 to
 like
 see
 how
 well
 this
 is

going
 to
 be.
 Um

But
 at
 the
 end
 of
 the
 day,
 like
 I
 said,

it
 is

how
 do
 we
 go
 from
 R&D
 to
 production?
 And

I
 think
 this
 is
 where
 like
 bench
 pod

will
 make
 it
 a
 lot
 more
 easier
 for

people
 to
 use.

Um

So
 like
 at
 the
 end
 of
 the
 day,
 like
 what

I
 want
 you
 guys
 to
 like
 know
 is
 like

um
 you
 know,
 pick
 a
 pod,
 get
 like
 a
 GPU

machine.
 You
 have
 your
 model,
 compare

configs.
 Don't
 just
 start
 with
 like
 the

VLN
 recipe.
 The
 VLN
 recipe
 is

proven,
 but
 it's
 not
 production
 ready.

Um

and
 then

test.
 Have
 your
 agent
 tested.
 And
 then

whatever,
 you
 know,
 based
 on
 what
 you

need,
 if
 it's
 ITL,
 if
 you
 need
 TTF,

TPOT,
 like
 metric,
 like
 optimize
 on

that.
 And
 then
 ship
 that
 winner.
 Go
 to

service,
 scale
 out,
 and
 now
 you
 can
 like

um

Now
 you
 have
 a
 working
 LLM
 model
 that

can
 be
 used
 internally,
 can
 be
 used
 for

our

Um

Yeah,
 it's
 it
 just
 makes
 it
 very
 very

simple.
</details>

不过针对大型模型，我还有一点想提醒大家：它对你的团队来说并不总是必须的。很多人忽略了一个重要事实：**其实完全可以选用较小的模型**。目前在我们的平台上，一个单 B200 节点每个月大概需要花费 4 万美元（价格可能会有浮动）。这是一台极其强大的机器，但当你规划内部托管还是自用时，最重要的是考量什么才是最合理的选择。不要仅仅因为它是最前沿的模型就盲目采用，它可能在性价比上并不划算。

比如我用 4 张 H200 跑 DeepSeek，效果就非常出色；超大模型则更多用来解决非常复杂且细致的长任务。

此外，确保工具链选型的契合也是至关重要的一环。至于上下文知识库（wikis）之类的内容今天我就不多展开了，但具备这些能力以及 AI 治理，将是 RunPod 接下来要走的下一步。在自托管开源 LLM 时，这些都是需要始终纳入考量的方面。

大家有什么问题吗？我们在楼下的展位也设有展台。如果你想进一步交流，欢迎在 LinkedIn 上加我好友。我每周都在探索所有最新推出的模型，在这个过程中踩过很多坑、积累了不少心得。大家也可以扫描名片上的二维码获取测试额度体验 RunPod。正如之前提到的，BenchPod 模板将在本月底发布供大家探索体验。
<details>
<summary>Original English</summary>
But
 yeah,

one
 thing
 I
 would
 say
 especially
 with

like
 Kimmy
 that
 I've
 noticed
 is
 um

it's
 not
 always
 necessary
 for
 a
 team.

Like
 like
 a
 big
 thing
 that
 I
 think
 like

most
 people
 don't
 think
 about
 is
 that

um

you
 can
 use
 a
 smaller
 model.
 You
 know,

it
 it's
 a
 B
 200
 right
 now
 like
 a
 node.

That's
 like
 on
 our
 on
 our
 platform
 like

that's
 going
 to
 cost
 you
 40K
 a
 month

essentially.
 And
 it
 might
 go
 up,
 it

might
 go
 down
 a
 little,
 but
 you
 know,

it's
 a
 very
 powerful
 machine
 and
 I
 think

when
 you're
 thinking
 about
 like
 how

you're
 going
 to
 be
 um

serving
 stuff
 if
 you
 want
 to
 be
 doing

this
 internally
 or
 for
 yourselves
 is

like
 what
 makes
 sense
 the
 best.
 And
 just

because
 it's
 the
 the
 frontier
 model,

maybe
 it
 doesn't
 make
 sense.

Um

like
 I
 said
 like
 like
 I
 run
 a
 deep
 six

on
 a
 4
 H
 200s
 and
 does
 a
 really
 good

job.

Kimmy's
 more
 for
 like
 long
 tasks
 that

I'm
 trying
 to
 solve
 something
 like
 very

very
 detailed.

Um
 but
 like
 I
 said,
 the
 other
 thing
 is

like
 making
 sure
 your
 like
 tooling

choice
 is
 like
 on
 there.
 That
 is
 a
 big

thing.

Context
 like
 I
 I'm
 not
 going
 to
 be
 going

through
 too
 much
 about
 like
 context
 like

wikis
 and
 all
 that,
 but
 the
 ability
 to

have
 all
 that
 and
 like
 AI
 governance
 is

the
 next
 step
 that
 we
 are
 going
 to
 be

going
 with
 RunPod,
 but
 just
 something
 to

be
 always
 be
 thinking
 about
 especially

if
 you're
 going
 to
 be
 self-hosting
 your

um

your
 LLM
 models.

But
 yeah,
 is
 there
 any
 questions?
 Like

And
 we'll
 also
 be
 at
 the
 booths.
 So
 like

downstairs.
 But
 yeah,
 add
 me
 on
 LinkedIn

if
 you
 want
 to
 talk
 more.
 I'm
 always

exploring
 every
 new
 model
 like
 every

week.
 So

always
 have
 some
 like
 gotchas
 that
 I've

been
 learning
 through
 the
 through
 the

time
 I've
 been
 doing
 all
 this
 work.
 And

yeah,
 also
 scan
 the
 card
 QR
 code
 so
 you

can
 get

you
 get
 some
 credits
 and
 you
 can
 test

out
 RunPod.
 And
 and
 said,
 the
 template

will
 be
 out
 like
 at
 the
 end
 of
 the

month.
 So
 you
 can
 go
 play
 around
 with

it.
</details>