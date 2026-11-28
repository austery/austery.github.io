---
author: AI Engineer
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1NWnSwCB4NM
speaker: AI Engineer
tags:
  - kv-cache
  - ai-agent
  - anomaly-detection
  - ai-security
  - inference-engine
title: 利用推理引擎的 KV Cache 检测 AI Agent 安全攻击与异常
summary: Intrinsic AI 创始人 Ari Azarfar 提出将推理引擎中的 KV Cache 作为安全信号，用于补充传统边界防护。通过建立正常推理流量的基线来检测异常页面，不仅能覆盖边界护栏盲区、保护数据隐私，还可定位具体异常位置并用于威胁发现，但在生产落地中仍面临多模型表征不一致与大规模对象传输等挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ari Azarfar
companies_orgs:
  - Intrinsic AI
products_models: []
media_books: []
status: evergreen
---
### KV Cache 的安全视角

大家好，我是 Intrinsic AI 的创始人 Ari Azarfar。本场演讲面向那些正在构建智能体（Agent）并运行自己推理技术栈，或有此计划的人群。如果你属于这类开发者，通常会将现代推理引擎的基础核心——KV Cache，视为一种吞吐量优化手段：每个 token 计算出的 Key 和 Value 被保留下来，这样模型就不必重复计算。今天，我想带大家从一个不同的角度来看待 KV Cache。

<details>
<summary>Original English</summary>
Hi,
 I'm
 Ari
 Azarfar,
 founder
 of


Intrinsic
 AI.


Um
 this
 talk
 is
 for
 people
 who
 build


agents
 and
 run
 their
 own
 inference


stack,
 or
 plan
 to.
 And
 if
 that's
 you,


you
 associate
 typically
 the
 KB
 cache,


the
 bread
 and
 butter
 of


uh
 modern
 inference
 engines,
 usually
 as


a
 throughput
 optimization.
 The
 keys
 and


values
 computed
 per
 token,
 kept
 so
 the


model
 doesn't
 compute
 them
 again.
 Today,


I'll
 like
 to
 show
 KB
 cache
 in
 a


different
 light.
</details>

AI Agent 应用可能出现故障或受到攻击的方式层出不穷：提示注入（Prompt Injection）、越狱（Jailbreak）、工具调用损坏、敏感工具调用、敏感数据泄露、隐藏后门、漂移等等。目前，我们防范这些层出不穷的 AI Agent 应用故障时，通常采用边界防护方式，比如通过评估模型（Judge Model）根据策略检查提示词、输入以及响应输出；或者针对每种情况分别构建一个分类器。

<details>
<summary>Original English</summary>
The
 way
 agents
 agent
 AI
 agent


application
 could
 go
 wrong
 or
 keep


growing,
 right?
 Prompt
 injection,


jailbreaks,
 broken
 tool
 calls,
 sensitive


tool
 calls,
 sensitive
 data
 exposures,


hidden
 backdoors,
 and
 drifts,
 and
 so


forth,
 right?
 So,
 the
 way
 right
 now
 we


typically
 guard
 against
 against
 this


numerous
 ways
 that
 an
 AI
 agent


application
 could
 go
 wrong
 is
 by


guarding
 the
 edge,
 by
 perhaps
 passing
 a


judge
 model
 that
 checks
 the
 prompts,
 the


inputs,
 and
 the
 response
 outputs
 against


your
 policy.


All
 right?
 Or
 you
 build
 a
 classifier
 for


each
 case.
</details>

但这里有一个不同的视角：模型在行动之前、在解码之前、在生成响应之前，以及在响应转化为另一个工具调用之前，都会把每个输入变成计算。KV Cache 就是你的推理引擎对该计算过程的记录。现代推理引擎原本就在免费使用和读取它。因此，在本次演讲中，我想建议将这种数据作为现有安全护栏的补充，并将其与你的 KV Cache 基础设施集成起来。

<details>
<summary>Original English</summary>
But
 here's
 a
 different
 light.
 The
 model


turns
 every


input
 into
 a
 computation
 before
 it
 acts,


before
 it
 decodes,
 before
 it
 generates


the
 response,
 before
 that
 response


becomes
 another
 tool
 call.
 The
 KB
 cache


is
 your
 engine's
 record
 of
 that


computation.
 The
 modern
 inference


engine,
 for
 free,
 are
 using
 it
 and


reading
 it.


And
 therefore,
 on
 this
 talk,
 I
 would


like
 to
 suggest
 as
 as
 a
 complement
 to


the
 way
 you're
 already
 using
 your
 own


guardrails,
 to
 use
 this
 data
 and


integrated
 with
 your
 KB
 cache


infrastructure.
</details>

### 基于 KV Cache 的安全信号优势与实现步骤

我将其称为“基于 KV Cache 的优先安全信号”（KV-first Security Signals），它之所以重要，主要有三个原因：
- **数据本就存在**：你可以从推理技术栈原本准备丢弃的这堆数据中淘出金子；
- **覆盖安全护栏盲区**：因为无论什么东西绕过了那些护栏，它依然会转化为计算；
- **原地留存**：非常适合数据隐私场景，适用于你无法读取输入和输出内容的用例。

实现的方法相当直接，包含三个步骤：
1. 针对你的 AI 工作负载和推理流量学习一个基准线，了解你的 KV Page 通常是什么样的；
2. 找出对照基准线而言较为罕见的 KV Page，这些通常就是你的异常；
3. 对这些异常进行分类和解释。

首先，我们来看看这种集成可以发生在技术栈的哪个位置。

<details>
<summary>Original English</summary>
I
 refer
 to
 this
 as
 a
 KB
 first
 security


signals,
 and
 basically
 three
 reasons


that
 matters,
 right?
 So,
 the
 data
 is


already
 there.
 You
 pick
 the
 gems
 from


the
 pile
 your
 inference
 stack
 would


already
 were
 throwing
 away.


It
 covers
 the
 guardrails
 blind
 spots,


because
 whatever
 it
 slips
 past
 those


guardrails,
 it
 still
 becomes


computation.
 And
 it
 stays
 in
 place,
 so


it's
 perfect
 for
 data
 privacy


application,
 for
 cases
 where
 you
 do
 not


have
 the
 luxury
 to
 read
 the
 inputs
 and


outputs.
 And
 the
 recipe
 is
 pretty


straightforward,
 right?
 Has
 three
 steps.


You
 learn
 a
 baseline
 for
 your
 AI


workload,
 for
 your
 AI
 inference
 traffic,


how
 your
 KB
 page
 typically
 look
 like,


and
 then
 find
 the
 KB
 pages
 that
 are


rarer
 against
 your
 baseline,
 typically


your
 anomalies.
 And
 then
 you
 can
 even


classify
 and
 explain
 those.
 So,
 first


let
 start
 with
 where
 in
 the
 stack
 this


integration
 could
 happen.
</details>

### 系统集成点：实时检测与威胁发现

KV Cache 的一个有趣之处在于，某种程度上它的存在让推理在一定意义上变成了有状态的。例如，像 LMCache 这样的 KV Cache 管理层会将它们从 GPU 卸载存储到远程存储中；或者 LLMD 和 NVIDIA Dynamo 会将每个新请求路由到可能已经持有该缓存 KV Page 的 Worker 上。因此，你有两个集成点可以将这些异常检测或分类器整合进去：

其一，你可以直接在推理引擎内部（例如通过 vLLM 等）实现它。这种方式的优势在于它是**实时的**，它生成的告警可以伴随未来的工具调用或未来的策略生效。因此，仅通过在推理引擎内观察到的计算异常，你就可以强化自己的策略或护栏。

其二，你也可以将其作为一种威胁发现的方式，与你的 LMCache 集成，从而读取存储的 KV Page 并找出与其余部分不相符的内容。

<details>
<summary>Original English</summary>
The
 interesting
 thing
 about
 the
 KB
 cache


is
 that
 in
 a
 way
 existence
 of
 those
 had


made
 the
 inference
 in
 a
 way
 stateful,


right?
 So,
 for
 example,
 things
 like
 KB


cache
 management
 layers
 such
 as
 LM
 cache


stores
 them


from
 GPU
 down
 to
 a
 remote
 storage.
 Or


LLMD
 and
 NVIDIA
 Dynamo
 route
 each
 new


request
 towards
 the
 worker
 that
 already


holds
 perhaps
 that


cached
 KB
 page.
 So,
 there
 are
 two


integration
 points
 you
 you
 you
 you
 can


integrate
 those
 anomaly
 detection
 or


those
 classifiers
 into.


Either
 you
 can
 implement
 it
 directly


inside
 of
 your
 inference
 engine
 via
 LMs,


you
 name
 so
 forth.
 The
 beauty
 of
 this


approach
 is
 that
 it's
 real
 time.


And
 and
 the
 the
 the
 alert
 that
 it
 would


perhaps
 generate
 could
 ride
 along
 your


future
 tool
 calls
 or
 your
 future


policies.
 So,
 you
 can
 harden
 basically


your
 policies
 or
 guardrails
 but
 just


generating
 the
 computational
 anomalies


that
 you
 observe
 within
 your
 inference


engines.


And
 you
 or
 perhaps
 you
 can
 integrate
 it


with
 as
 a
 as
 a
 way
 of
 threat
 discovery


in
 a
 sense.
 So,
 you
 can
 integrate
 with


your
 LM
 cache.
 So,
 it
 reads
 the
 stored


KB
 pages
 and
 find
 things
 that
 don't


belong
 with
 the
 rest,
 right?
 So,
 now
 I


want
 to
 show
 you
 some
 numbers
 and


just
 a
 very
 simple
 hello
 world
 use
 case


if
 if
 this
 is
 actually
 working
 and
 this


is
 a
 valid
 approach.
 And
 for
 that,
 let


me
 use
 the
 use
 case
 that
 has
 no
 text
 to


filter
 at
 all,
 a
 voice
 agent.
</details>

### 实验案例：语音 Agent 与文本 Agent

现在我想给大家看一些数据，以及一个非常简单的入门示例，来看看这是否真的有效、是否是一种可行的方法。为此，让我使用一个完全没有文本可过滤的用例——语音 Agent。

这里是一个语音 Agent 的案例研究。在这个案例中，模型使用的是 Gemini 404B。我们的基准线由 4 种声音说出的 72 个普通语音片段组成。我们观察的是 16-token 的页面。显而易见，这个粒度是可以调整的，但这里使用较短的页面只是为了在基线中获得更多数据。然后在测试集上，我们有不同的声音——一个干净的声音，另一个则包含隐藏指令。正如这里所示，你不仅可以通过简单的异常检测来检测这些情况，而且还能知道是哪个页面、请求的哪一部分发生了这种异常事件。我们甚至更进一步，训练了一个以 KV Page 作为特征的模型。我们尝试对其进行解释或打上有用的标签；在这个案例中，尽管该模型甚至没有在音频上进行过训练，它却能够生成关于个人信息、家庭住址、位置数据、出行信息、目的地的正确信息。

<details>
<summary>Original English</summary>
So,
 here's
 a
 case
 of
 study
 of
 a
 voice


agent.
 In
 this
 case,
 it
 was
 a
 Gemini


404B.
 Our
 baseline
 was
 72
 ordinary
 clips


and
 spoken
 four
 voices.
 We're
 looking
 at


16
 token
 pages.
 Obviously,
 this


granularity


could
 change.
 But
 here
 was
 just
 use
 this


shorter
 pages
 so
 we
 could
 have
 more
 data


in
 the
 baseline.
 And
 then
 on
 the
 test,


we
 have
 different
 voices


one
 clean
 voice
 and
 the
 other
 one
 has
 a


hidden
 instruction
 within
 it.
 As
 you
 can


as
 shown
 here,
 not
 only
 you
 can
 detect


these
 cases
 just
 using
 simple
 anomaly


detection,
 but
 also
 you
 would
 know
 which


part
 of


um


which
 page
 which
 part
 of
 your
 request


had
 this
 anomalous
 event.
 We
 even
 went


further
 and
 we
 trained
 a
 model
 that
 uses


the
 KD
 pages
 as
 features.


And
 we
 didn't
 we're
 trying
 to
 explain
 it


or
 tag
 it
 with
 things
 that
 are
 useful.


In
 this
 case,
 although
 it
 wasn't
 even


trained
 on
 audio,
 it's
 able
 to
 generate


correct
 information
 about
 personal


information,
 home
 address,
 location


data,
 travel
 information,
 destination.
</details>

现在回到文本 Agent。在这个案例中，使用的是在 vLLM 缓存上实时服务的 314B 模型。左边的图向大家展示了攻击流量与正常流量通常是如何相互区分开的；右边的图可能更有意义，它使用的是 Hugging Face 上的 AT-Bench。它有自己的良性 Agent 轨迹基线，以及 8 类 Agent 故障（从注入工具描述到错误信息等）。我们观察了异常检测生成的 Top 10 告警，在 10 次告警中大约有 7 到 8 次确实是有意义且有用的异常活动。我们甚至进一步观察了是否存在某种比其他异常更加突出的异常事件。

<details>
<summary>Original English</summary>
So,
 now
 back
 to
 text
 agents.
 In
 this


case,
 it
 was
 a
 client
 314
 billion
 served


live
 on
 bill
 110
 cash.


The
 one
 on
 the
 left
 shows
 you
 an
 idea
 of


how
 attacks
 and
 normal
 traffic
 would


typically
 separate
 from
 each
 other
 and


then
 the
 one
 on
 the
 right,
 which
 is


perhaps
 more
 meaningful,
 it
 was
 using


the
 AT
 bench
 and
 hugging
 face.
 It
 has


its
 own
 baseline
 of
 benign
 agent
 traces


and
 eight
 kind
 of
 agent
 failure
 from


injected
 tools
 description
 to


misinformation
 and
 so
 forth.


We
 look
 at
 the
 top
 10
 alerts
 that


anomalous
 anomaly
 detection
 would


generate
 and
 about
 seven
 to
 eight
 times


of
 out
 of
 10
 of
 these
 alerts
 are


actually
 anomalous
 meaningful
 and
 useful


anomalous
 activities.
 We
 even
 went


further
 and
 we
 looked
 at
 whether
 there's


any
 kind
 of
 anomalous
 event
 that
 is


stand
 out
 more
 than
 the
 rest.
</details>

### 生产落地的挑战与结语

在生产环境中落地会让事情变得困难，主要有以下两点：

第一，**模型会发生变化**。微调和新版本发布会发生变化，同时不同 Agent 各自运行在不同模型上，还有路由器会为每个请求选择专有模型。这意味着每个模型都会在它自己的坐标系中写入页面。因此，你要么去学习每一个基准线、分类器和解释器（这在计算上是无法承受的），要么必须找到一种方法将它们全部映射到一个共享的表征空间中。

第二，**实时意味着需要搬运大对象**。例如，1.34B 模型的 256 个 token 块对应大约 40 MB 的 KV 数据。像 CacheGen 这样的压缩和流式传输技术可能会有所帮助，但为了进行安全分析并实时采取行动而搬运这些数据，目前仍然较为缓慢。

这就是我们在 Intrinsic AI 所解决的问题。我们正在寻找那些构建自己的推理技术栈、并将安全视为基础架构设计决策的团队。希望本次分享对大家有所帮助。非常感谢大家的聆听，再见！

<details>
<summary>Original English</summary>
Um
 to
 make
 things
 hard
 in
 production.


First,
 models
 change.


Fine-tunes
 and
 new
 releases,
 but
 also


agents
 that
 each
 one
 on
 a
 different


model.


And
 routers
 that
 pick
 a
 specialist
 model


per
 request.
 That
 means
 each
 model


writes
 its
 pages
 its
 own
 coordinates.


So,
 either
 you
 learn
 every
 baseline,


classifier,
 and
 explainer,
 which
 is
 uh


computationally
 prohibitive,
 or
 you
 have


to
 find
 a
 way
 to
 map
 them
 all
 into
 one


shared
 representation
 space.


Second,
 real
 time
 means
 moving
 big


objects.
 For
 example,
 a
 1
 256
 token


chunk
 of
 1.34
 billion
 is
 about
 40


megabytes
 of
 KB.


Compression
 and
 streaming
 like
 cache
 gen


could
 help,
 but
 moving
 that
 for
 security


analysis
 and
 acting
 in
 real
 times
 is


still
 a
 slow.
 And
 that
's
 what
 we
 solve


at
 Interesting
 AI.
 We
 are
 looking
 for


teams
 building
 their
 own
 inference


stacks
 who
 treat
 security
 as
 a


foundational
 design
 decision.


I
 hope
 this
 was
 helpful
 for
 you.
 Thank


you
 so
 much
 for
 listening.


Bye.
</details>