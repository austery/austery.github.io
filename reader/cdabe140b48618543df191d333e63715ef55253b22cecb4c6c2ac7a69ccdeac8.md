---
author: AI Engineer
date: '2026-10-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rWtbOgl5FTU
speaker: AI Engineer
tags:
  - model-evaluation
  - benchmark
  - jagged-frontier
  - cost-optimization
  - ai-agent
title: 超越模型卡片：用评估度量参差前沿与大模型投资回报率
summary: 演讲者探讨了基础模型在不同领域及任务中表现出的“参差前沿”，指出公开基准的单一分数无法反映实际业务表现，盲目选用单价较低的模型反而可能因消耗更多 Token 而导致成本更高。通过构建贴合实际工作流程的定制化评估（Eval），企业能够量化投入产出比、优化模型路由与采购决策，从而有效推动 AI 的规模化落地。
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
  - Vals Index
  - Finagent
  - ValSmith
media_books: []
status: evergreen
---
[music]

<details>
<summary>Original English</summary>
[music]
</details>

### 超越模型卡片与参差前沿

>> 我想聊一聊超越模型卡片（model card）的话题，探讨如何利用评估（evaluations）来度量这种参差前沿（jagged frontier）。针对今天在座的听众，我也会重点关注金融领域。

<details>
<summary>Original English</summary>
>> I'm
 going
 to
 talk
 a
 little
 bit
 about
 uh


going
 from
 beyond
 the
 model
 card,
 how


evaluations
 can
 be
 used
 to
 measure
 this


jagged
 frontier.
 Uh
 special
 focus
 on


finance
 for
 this
 audience
 as
 well.
</details>

首先来谈谈模型卡片本身。过去几年里，我们构建了一些非常重要的基准测试，各大主流基础模型实验室在发布模型时都纳入了这些测试。大家应该对这类成果比较熟悉了。上周 Sundar 在台上提到了我们的 Vals 指标（Vals Index），甚至就在昨天，Muse 模型也在引述我们的 Finagent 基准。随着新模型不断推出，我们需要不断更新这些幻灯片，这也让我们的生活充满了乐趣。今天早上我还特意核对了一下，确认没有新模型发布。这类模型卡片反映了人们对模型新增能力的大致理解。它们能够通过单一数值展现出一个模型的智能程度。特别是我们的 Vals 指标，它通过整合各项结果，试图衡量模型在金融、法律、编程、医疗等领域的经济影响力。根据这些高层次的数据，你可以对模型完成高价值工作的能力有一个大致了解。

<details>
<summary>Original English</summary>
Um
 yeah,
 so
 first
 off
 talking
 about


model
 cards
 themselves,
 we've
 built
 uh


some
 of
 the
 most
 important
 benchmarks


over
 the
 last
 couple
 of
 years
 that
 the


major
 foundation
 model
 labs
 have


included
 in
 their
 model
 releases.
 So


people
 I
 think
 are
 familiar
 with


artifacts
 like
 this.
 Uh
 last
 week
 we


have
 Sunder
 talking
 about
 our
 Val's


index
 on
 stage
 and
 then
 uh
 even
 just


yesterday
 Muse
 models
 uh
 reciting
 our


our
 Finagint
 benchmark.
 You
 know,
 it


keeps
 our
 lives
 interesting
 to
 have
 to


keep
 re-updating
 these
 slides
 as
 new


models
 come
 out.
 I
 had
 to
 double-check


new
 models
 didn't
 come
 out
 this
 morning,


but
 um
 these
 are
 say
 these
 these
 kind
 of


model
 cards
 reflect
 a
 general


understanding
 of
 what's
 newly
 capable


with
 the
 models.
 Um
 and
 so
 uh
 they
 they


can
 reveal
 from
 a
 single
 number
 how


intelligent
 is
 a
 model.
 In
 particular,


our
 Val's
 index
 is
 compiling
 results
 to


try
 and
 measure
 the
 economic
 impact
 of


models
 uh
 in
 domains
 like
 finance,


legal,
 but
 also
 coding,
 health
 care,
 and


things
 like
 that.
 So
 from
 these


high-level
 numbers,
 you
 can
 get
 a
 sense


of
 how
 capable
 a
 model
 is
 for
 uh


valuable
 work.
</details>

但这并不能展现全貌。当我们进一步深入、审视构成 Vals 指标的各项具体基准时，就会看到一幅更加细致的画面。大家可能对这个概念有所了解，即“参差前沿”（jagged frontier）。它的含义是：在特定的领域或任务集中，当你汇总结果得出那个单一数值时，实际表现可能会与该数值呈现出差异。正如大家在这里看到的，在不同模型之间，谁能占据第一名的表现其实并不一致。

<details>
<summary>Original English</summary>
Um
 but
 that
 doesn't
 give


the
 whole
 picture.
 And
 so
 when
 we
 dial


in
 a
 little
 bit
 more
 closely
 and
 look
 at


the
 constituent
 benchmarks
 that
 comprise


the
 Val's
 index,
 we
 can
 see
 a
 more


nuanced
 picture.
 And
 this
 may
 be


something
 you
 all
 are
 familiar
 with,
 the


jagged
 frontier.
 And
 the
 idea
 that


within
 a
 particular
 domain
 or
 set
 of


tasks,
 you
 may
 see
 different
 performance


uh
 from
 when
 you
 aggregate
 results
 to


produce
 that
 single
 number.
 And
 so
 you


can
 see
 here
 across
 the
 different


models,
 uh
 we
 actually
 see
 an


inconsistent
 performance
 for
 who's


number
 one.
</details>

### 代码基准与企业评估的细粒度挑战

当你着眼于具体的组织或公司时，这种情况会更加突出。在很多方面，代码生成领域展现出的现象，正代表了各大垂直领域正在发生的状况。在编程场景下，当我们为特定的代码仓库创建定制基准测试时，会发现这种参差性变得更加剧烈。在 x 轴上是不同的编程语言和代码库，在 y 轴上则是模型的相对性能，可以看到结果更加碎片化。更不用说，这还没有考虑模型可能在不同的测试框架（harnesses）中运行，或者你在追求性能的同时还可能需要优化成本和延迟。因此，所有这些都说明了一个观点：在通用的模型卡片基准中所看到的性能粒度，并不一定最贴合在实际生产中使用这些模型或产品的人群的需求。

<details>
<summary>Original English</summary>
Uh
 but
 that's
 made
 even
 more
 so
 when
 you


look
 at
 particular
 organizations
 or


companies.
 So
 in
 a
 lot
 of
 ways,
 coding


is
 indicative
 of
 what's
 happening
 across


every
 major
 vertical.
 Um
 when
 we
 look
 at


coding
 and
 actually
 create
 custom


benchmarks
 for
 particular
 repositories,


we
 see
 that
 that
 jaggedness
 just


increases
 even
 more.
 And
 so
 on
 on
 the


x-axis
 you've
 got
 different
 programming


languages
 and
 libraries.
 And
 on
 the


y-axis
 you
 see
 the
 relative
 performance


of
 models
 and
 see
 that
 it's
 even
 more


fragmented.
 But
 this
 isn't
 even
 to
 take


into
 account
 that
 there
 are
 different


harnesses
 in
 which
 these
 models
 can
 can


be
 used
 or
 the
 idea
 that
 you
 might
 be


optimizing
 for
 cost
 and
 latency
 as
 well


as
 performance.
 And
 so
 this
 all
 feeds


into
 the
 idea
 that
 the
 the
 granularity


of
 of
 the
 performance
 you
 see
 in
 a


general
 model
 card
 benchmark
 is
 not


necessarily
 what's
 most
 applicable
 for


people
 who
 are
 using
 these
 models
 or
 or


products
 in
 practice.
</details>

### AI 支出激增与 ROI 困境

与此并行的是，AI 的普及率大幅上升。企业在 AI 上的支出同比增长了大约 2 倍。但在如此庞大的开销下，要理解投入产出比（ROI）来自何处依然非常困难。你可以看到，经常使用 AI 的人群比例现在达到了 90%，但如果看最小的那根柱状图，明确建立了 ROI 的比例只有 7%。因此，面对所有这些 Token 支出和不断增长的应用率，对很多公司而言，AI 究竟在哪些方面实际创造了价值，依然很不明确。

<details>
<summary>Original English</summary>
In
 parallel,
 AI
 adoption
 has
 gone
 up


considerably.
 So
 year
 over
 year
 there's


roughly
 a
 2x
 increase
 in
 enterprise
 AI


spend.
 But
 with
 all
 that
 spend
 it's


still
 really
 obtuse
 to
 understand
 where


the
 ROI
 is
 coming
 from.
 You
 can
 see
 that


people
 regularly
 using
 AI
 is
 now
 90%
 but


if
 you
 look
 at
 the
 smallest
 bar
 now
 we


have
 established
 ROI
 just
 at
 7%.
 So
 for


all
 this
 token
 spend
 and
 increased


adoption
 it's
 still
 very
 unclear
 where


AI
 is
 actually
 driving
 value
 for
 a
 lot


of
 companies.
</details>

我认为有两个引人注目的统计数据：能够真正追踪 AI 成本和支出的团队，更有可能弄清楚 ROI 会从何而来；而这本身也是阻碍应用落地的一个关键瓶颈。那些无法切实量化投资成本与回报的团队，往往将此视为大规模推行 AI 的巨大阻碍。因此我认为，评估（evals）是这里的核心切入点。如果人们能够构建出关键评估，衡量模型具备哪些能力，以及如何最有效地利用这些资金，他们就能够在自己的企业中更广泛地落地 AI。

<details>
<summary>Original English</summary>
And
 I
 think
 two
 interesting
 stats
 that


jump
 out
 at
 me,
 the
 groups
 that
 are
 able


to
 actually
 track
 AI
 cost
 and
 spend
 are


much
 much
 more
 likely
 to
 actually


understand
 where
 ROI
 is
 going
 to
 come


from.
 And
 this
 is
 also
 a
 key
 blocker
 for


adoption
 itself.
 The
 groups
 that
 are


unable
 to
 actually
 quantify
 the
 cost
 to


the
 return
 on
 their
 investment
 often
 see


this
 as
 a
 big
 bottleneck
 to
 actually


widely
 roll
 out
 AI.
 And
 so
 I
 think
 evals
 is


the
 key
 story
 here.
 If
 people
 are


able
 to
 construct
 key
 evaluations
 that


measure
 what
 our
 model's
 capable
 of
 and


what
 will
 be
 the
 most
 efficient


utilization
 of
 those
 dollars,
 they'll
 be


able
 to
 adopt
 AI
 in
 their
 firm
 more


broadly.
</details>

### 更便宜的模型反而更贵

我想和大家分享一个特别有趣的发现，它说明了为什么厂商呈现的模型性能直觉往往与实际体验不符。以 Opus 5.5 为例，它是 Anthropic 的第二梯队模型。在纸面上它确实更便宜：输入 4 美元、输出 20 美元，相比之下 Fable 5.1 是输入 10 美元、输出 50 美元。但在实际操作中，特别是在这个税务基准测试中，你会发现它实际上更贵，贵了 14%。这是因为智能程度较低的模型试图消耗更多的 Token 来完成任务。然而在实际结果中，它的得分反而低了 3%。因此，如果选择前沿智能模型，你的情况原本会更好：花费更少，同时获得更好的性能。但对于在实践中使用模型的人来说，这种直觉并不直观。他们可能会想：“我其实应该用 Sonnet 或 Opus”，结果却为更差的性能付出了更高的代价。

<details>
<summary>Original English</summary>
I
 think
 one
 particular
 interesting


finding
 that
 that
 I
 want
 to
 share
 with


you
 all
 is
 an
 indication
 of
 why
 the


intuition
 that
 are


intuition
 of
 model
 performance
 as


presented
 by
 labs
 doesn't
 often
 align


with
 experience.
 So
 if
 you
 look
 at
 Opus


5.5
 that's
 the
 kind
 of
 second
 tier
 model


from
 Anthropic.
 And
 on
 paper
 it's


actually
 cheaper.
 $4
 and
 $20
 out


compared
 to
 Fable
 5.1's
 $10
 and
 $50
 out.


But
 in
 practice,
 and
 particularly
 for


this
 tax
 benchmark,
 you
 see
 that
 it's


actually
 more
 expensive,
 14
 more


expensive.
 And
 that's
 because
 the
 less


intelligent
 model
 is
 trying
 to
 expend


more
 tokens
 to
 try
 and
 get
 its
 work


done.
 But
 this
 actually
 bears
 out
 as
 a


3%
 lower
 score.
 Um
 and
 so
 you
 are


actually
 would
 have
 been
 better
 off


using
 the
 frontier
 intelligence.
 You


would
 have
 spent
 less
 and
 got
 a
 better


performance.
 Um
 but
 that
 kind
 of


intuition
 isn't
 isn't
 directly
 available


for
 people
 who
 are
 using
 the
 models
 in


practice.
 And
 so
 they
 may
 try
 and
 say,


"Actually,
 I
 should
 use
 a
 Sonnet
 or
 an


Opus."
 But
 end
 up
 overpaying
 for
 uh


inferior
 performance.
</details>

我认为这表明，我们应该更加严谨地去探究回报究竟来自何处。这将描绘出一幅更真实的图景，而不是单纯依赖厂商直接灌输的直觉。

<details>
<summary>Original English</summary>
Uh
 and
 so
 I
 think
 this,
 you
 know,


reveals
 that
 we
 should
 actually
 take
 a


more
 diligent
 effort
 to
 figuring
 out


where
 return
 is
 coming
 from.
 And
 and


that
 will
 inform
 a
 more
 realistic


picture
 as
 opposed
 to
 the
 intuition
 that


labs
 are
 feeding
 directly.
</details>

### 金融领域的帕累托前沿分析

具体到金融领域，关于这种参差前沿的概念，我重点提到了 Vals 指标，但我们还有一个针对金融研究任务的金融 Agent 基准（finance agent benchmark），以及 Excel 建模和税务 Agent。即使横跨这些基准，哪款模型位居第一、或者谁能稳定排在第二或第三，依然不是一目了然的。

<details>
<summary>Original English</summary>
If
 we
 look
 at
 look
 at
 finance
 in


particular,
 so
 that
 this
 kind
 of
 jagged


frontier
 concept,
 uh
 I
've
 highlighted


the
 Vals
 Index,
 but
 we
 also
 have
 a


finance
 agent
 benchmark
 looking
 at


research
 tasks
 for
 finance,
 and
 then


Excel
 modeling,
 uh
 and
 then
 tax
 agent.


Uh
 and
 even
 across
 these
 benchmarks


again,
 it's
 not
 immediately
 obvious


which
 is
 number
 one
 or
 will
 be


consistently
 two
 or
 three.
</details>

当你观察帕累托曲线（Pareto curve）时，这幅图景会变得更加微妙。在 x 轴上是成本，具体来说是每项任务的成本，而不仅仅是 Token 进出的成本；在 y 轴上是性能。我们这里看的是 Excel 建模基准，即观察这些 AI 模型能否创建并处理作为金融核心工作的 Excel 模型。绿线代表所有问题上的综合表现。而在红线中，我们单独切分出了杠杆收购（LBO）任务，这是使用这些模型时可能会接触到的特定 Excel 模型子任务集。我想指出两点：首先，你可以看到 LBO 任务的整个前沿都低于整体任务得分。因此，你仅从高层级的 EMB 结果中得出的直觉，并不能与你在 LBO 类别任务中看到的情况相匹配。如果你的公司侧重某一种类型的 Excel 模型，清晰了解对你真正相关的内容就非常重要。其次，从总体得分转到单纯的 LBO 子类别时，前沿也在发生变化。你原本可能以为使用 Fable 5.1 能获得最佳性能，但在 LBO 任务中，它实际上跌出了帕累托前沿。你将为该类别中不再处于最先进水平的模型支付极其高昂的溢价。这再次印证了这种观点：顶层的总体表现并不那么重要，最重要的是与你最相关的任务子集，以及你希望在公司内部实现的成本与性能优化。

<details>
<summary>Original English</summary>
This
 picture
 is
 made
 even
 more
 nuanced


when
 you
 look
 at
 the
 Pareto
 curve.
 So
 on


the
 x-axis,
 you've
 got
 cost.
 In


particular,
 it's
 cost
 per
 task,
 not
 just


token
 in
 token
 out
 cost.
 And
 on
 the


y-axis,
 you
 have
 performance.
 And
 and


here
 what
 we're
 looking
 at
 is
 that
 Excel


modeling
 benchmark.
 So
 seeing
 whether


these
 AI
 models
 can
 create
 and
 work
 with


Excel
 models
 that
 are
 core
 to
 work


that's
 happening
 in
 finance.
 Uh
 in
 the


green,
 you
 have
 the
 overall
 performance


across
 all
 of
 the
 questions.
 And
 then
 in


red,
 what
 we've
 done
 is
 is
 segmented
 out


the
 LBO
 tasks.
 So
 this
 is
 a
 particular


subset
 of
 Excel
 model
 tasks
 that
 you


might
 you
 might
 be
 working
 with
 in
 the


in
 uh


um
 using
 any
 of
 these
 models.
 Um
 and
 I


want
 to
 call
 out
 a
 couple
 things.
 In


particular,
 first
 what
 you
 see
 is
 that


the
 entire
 frontier
 for
 LBO
 is
 lower


than
 the
 overall
 task
 score.
 So
 the


intuition
 you
 would
 have
 from
 just
 the


the
 high-level
 EMB
 results
 would
 not


match
 what
 you
 see
 for
 the
 LBO


categories
 of
 tasks.
 And
 so
 if
 your
 firm


is
 especially
 doing,
 you
 know,
 one
 type


of
 Excel
 models
 over
 another,
 it's


important
 to
 have
 a
 clearer
 picture
 of


what's
 going
 to
 be
 actually
 relevant
 to


you.
 But
 the
 other
 is
 that
 the
 frontier


is
 also
 changing
 when
 you
 go
 between
 the


overall
 scores
 to
 just
 the
 LBO


subcategory.
 So,
 whereas
 you
 might
 have


thought
 you
 would
 have
 get
 the
 best


possible
 performance
 from
 using
 Feable


5.1,
 when
 you
 go
 to
 the
 LBO
 it
 actually


drops
 off
 the
 Pareto
 frontier.
 You're


going
 to
 be
 massively
 overpaying
 for


what
 is
 no
 longer
 the
 state
 of
 the
 art


model
 for
 that
 category.
 Uh
 and
 so


again,
 this
 kind
 of
 reiterates
 this
 idea


that
 it's
 it's
 less
 important
 what
 you


see
 at
 the
 top,
 but
 actually
 the
 subset


of
 tasks
 that
 are
 most
 relevant
 for
 you


and
 the
 cost
 performance
 optimization


that
 you
 want
 to
 see
 within
 your


company.
</details>

### 构建基准测试的核心要素与指标选择

我想分享一些实际构建基准测试的经验。我们刚才讨论了结果，以及为什么结果可能反直觉。当我们实际构建基准测试时，最重要的事情之一就是审视用于汇报准确率的指标。选择不同的指标，得出的结论会完全不同。许多基准测试采用部分得分（partial credit）。这回答的问题是：在期望值上，如果我给模型一个问题或任务，我期望看到该模型的输出满足多少百分比的要点，尤其是与人类相比。而“完全正确答案”（fully corrected answers）指标关注的则是：在输入给模型的所有问题中，有多少比例能够被完美解决？这是一个截然不同的指标。它可能意味着模型非常擅长生成递进式的回复，你可以据此继续完善以获得更好的结果；但如果你把它直接发给客户，它能否满足你的所有标准就如同掷硬币一样不可预测。因此，选择正确的指标对于准确呈现模型性能、真正建立对其能力的正确直觉至关重要。

<details>
<summary>Original English</summary>
So,
 I
 want
 to
 share
 uh
 some
 some
 lessons


from
 actually
 building
 the
 benchmarks.


We
 talked
 a
 little
 bit
 about
 the
 results


and
 and
 why
 the
 results
 may
 be
 intuitive


unintuitive.
 Um
 when
 we
 actually
 build


benchmarks,
 one
 of
 the
 most
 important


things
 that
 we
 need
 to
 look
 at
 is
 the


metric
 we
 use
 to
 report
 accuracy.
 Uh
 and


so
 you
 you
 you
 have
 a
 different
 takeaway


if
 you
 pick
 a
 different
 metric.
 A
 lot
 of


benchmarks
 deal
 with
 partial
 credit.
 And


so
 what
 this
 is
 answering
 is
 in


expectation,
 if
 I
 were
 to
 give
 a


question
 or
 task
 to
 a
 model,
 what


percentage
 of
 the
 points
 would
 I
 expect


to
 uh
 see
 satisfied
 by
 the
 the
 the
 work


the
 work
 output
 of
 that
 model,


especially
 compared
 to
 humans?
 And
 then


the
 fully
 corrected
 answers
 metric
 is


more
 looking
 at
 of
 the
 percentage
 of


questions
 that
 I
 give
 to
 models,
 what


percentage
 of
 them
 will
 come
 back


perfect?
 And
 that's
 that's
 a
 very


different
 metric.
 It
 may
 mean
 uh
 that
 a


model
 is
 very
 good
 at
 producing
 uh
 an


incremental
 response
 that
 you
 can
 work


with
 to
 build
 a
 better
 response.
 Um
 but


if
 you
 were
 to
 pass
 this
 directly
 to
 a


client,
 it
 would
 be
 a
 coin
 toss
 of


whether
 it
 was
 meeting
 all
 the
 criteria


that
 you
 have.
 Uh
 and
 so
 picking
 the


right
 metric
 is
 very
 important
 to


accurately
 representing
 the
 performance


of
 a
 model
 and
 actually
 forming
 a
 good


intuition
 of
 what
 it
 can
 do.
</details>

我们还会深入考量另外三个维度：
- **有效性（Validity）**：你是否真的在评估现实世界中发生的事情？也就是说，这些问题或任务是否反映了真实的工作，还是人为捏造的？评分标准（rubrics）是否切实描述了我们所追求的目标或期望看到的卓越水准？
- **可靠性（Reliability）**：这通常取决于任务数量或样本量。很多公司可能只有五六个样本，在获得新模型或产品的权限时就进行一种“感觉检查”（vibe checking）。但采用严谨的方法、拥有足够的任务和样本量，以确保重复运行能够显示出一致的结果，其实是极其重要的。
- **区分度（Discriminability）**：我们认为，所有模型都得 100% 或所有模型都得 0% 的基准测试并没有太大价值。理想情况下，我们应该能够区分不同的模型，看清楚技术前沿的全貌。特别是，我们还希望确保构建的基准测试具有前瞻性：探索哪些全新的任务比模型目前的能力更具挑战性，从而确保前沿留有空间，让我们能够随着模型的改进持续观察其技术进展。

<details>
<summary>Original English</summary>
There's
 another
 three
 components
 that
 we


think
 a
 lot
 about.
 So,
 validity,
 are
 you


actually
 evaluating
 what's
 going
 on
 in


the
 real
 world?
 That
 means
 are
 the


questions
 or
 tasks
 reflective
 of
 actual


work
 going
 on
 or
 are
 they
 contrived?
 Um


and
 then
 are
 the
 rubrics
 actually


describing
 what
 we're
 looking
 for
 or
 the


standard
 of
 excellence
 we
 want
 to
 see?


Reliability,
 this
 is
 usually
 a
 function


of
 the
 number
 of
 tasks
 or
 the
 sample


count.
 Um
 a
 lot
 of
 companies,
 they
 have


maybe
 five
 or
 six
 samples
 and
 they're


kind
 of
 vibe
 checking
 new
 models
 or


products
 as
 they
 get
 access.
 Um
 but
 it's


actually
 really
 important
 to
 have
 a


rigorous
 approach
 and
 have
 enough
 tasks


and
 samples
 to
 make
 sure
 your
 repeated


runs
 actually
 show
 consistent
 results.


And
 then
 lastly,
 discriminability.
 So,


we
 we
 don't
 think
 it's
 that
 valuable
 to


have
 benchmarks
 where
 all
 models
 score


100%
 or
 all
 models
 score
 0%.
 Ideally,
 we


can
 we
 can
 actually
 discriminate
 between


models
 and
 see
 what
 the
 frontier
 looks


like.
 In
 particular,
 we
 also
 want
 to


make
 sure
 we're
 building
 benchmarks


forward-looking.
 So,
 what
 are
 the
 new


set
 of
 tasks
 that
 are
 even
 more


ambitious
 than
 what
 models
 can
 do
 today


uh
 to
 make
 sure
 that
 there's
 room
 at
 the


frontier
 for
 us
 to
 uh
 you
 could
 uh
 to


continue
 to
 see
 model
 progress
 as
 they


get
 better.
</details>

### 评估面临的三大高层难题

接下来谈谈我们观察到、而且其他人也可能会遇到的一些高层难题：

第一，**Agent 解决的是测试任务，而不是实际问题**。大家常将其称为“奖励黑客”（reward hacking）。我们见过很多情况：设置了一个沙箱，让模型通过我们的模型代理（proxy）运行，有时模型会试图在代理内调用其他模型来逃逸沙箱或访问互联网。因此，构建容器的方式非常关键，必须确保测出真正重要的东西：它们究竟能否完成手头的任务，还是在借助其他工具甚至其他模型来达成目标？在金融领域我们也特别观察到了这个问题，很多时候评估关注的是回复中是否包含一系列评分细项或要素。于是模型就会采取两头下注（hedge）的做法，给出三种可能的答案，这样满足所有评分标准的概率更高。但从实际应用来看，这完全过头了。人并不想去甄别三种不同的答案，他们只希望得到第一个答案并且它就是对的。因此，这里的目标是构建能够反映人们实际工作内容和期望工作产出的评估，而不是构建那些能被模型钻空子的人工测试。

<details>
<summary>Original English</summary>
Okay.
 So,
 and
 then
 some
 of
 the


high-level
 problems
 that
 we've
 seen
 and


I
 think
 others


uh
 you
 know,
 can
 and
 and
 do
 run
 into.


The
 first
 is
 that
 agents
 solve
 the
 task,


not
 the
 problem.
 So,
 this
 is
 talked
 a


lot
 about
 as
 reward
 hacking.
 Um,
 and


we've
 seen
 a
 lot
 of
 instances
 where


we'll
 have
 a
 sandbox
 and
 models
 will
 be


run
 with
 our
 model
 proxy.
 And
 sometimes


they
 may
 try
 and
 actually
 call
 other


models
 uh
 within
 that
 proxy
 to
 escape


the
 sandbox
 or
 make
 use
 of
 the
 internet.


Uh,
 so
 it's
 really
 important
 to
 to
 build


the
 the
 containers
 in
 a
 way
 that
 you're


actually
 testing
 for
 what
 matters.
 Can


they
 can
 they
 do
 the
 task
 at
 hand
 um
 or


are
 they
 actually
 leveraging
 other
 tools


or
 maybe
 even
 other
 models
 to
 get
 there?


Um,
 we've
 also
 seen
 this
 issue
 in


finance
 in
 particular
 where
 a
 lot
 of
 the


times
 uh
 evals
 are
 looking
 at
 a
 set
 of


rubrics
 or
 or
 items
 that
 we
 want
 to
 see


included
 in
 the
 response.
 And
 so,
 models


can
 hedge
 and
 give
 three
 possible


answers
 uh
 which
 has
 a
 higher
 chance
 of


satisfying
 all
 the
 criteria
 um
 but
 in


practice,
 that's
 way
 way
 too
 much.
 A


person
 does
 not
 want
 to
 consider
 three


different
 answers.
 They
 just
 want
 to
 get


the
 the
 first
 answer
 and
 and
 have
 it
 be


right.
 Um,
 and
 so,


the
 goal
 here
 is
 to
 try
 and
 build
 evals


that
 are
 reflective
 of
 the
 actual
 work


people
 are
 doing
 and
 the
 work
 output


they
 want
 to
 see
 um
 not
 to
 build
 these


contrived
 evals
 that
 that
 the
 models
 can


actually
 gain.
</details>

第二，很多人开始看到软件成本正在下降，编写代码变得极其容易。但在实践中遗憾的是，运行评估依然具有难以置信的挑战性，尤其是从**基础设施**的角度来看。随着我们转向长程运行（longer-running）的 Agent，基础设施能够在长时间内保持稳定一致，并且在中断后能够恢复并重新拉起，就显得格外关键。我们在评估中刚刚突破了 6 万亿个 Token。我们运行着规模庞大的评估集，并且尽可能以最高程度的并行方式来执行。这确实经历过严格的负载测试，但其他人哪怕在较小的规模上，也会遇到类似的基础设施难题。

<details>
<summary>Original English</summary>
The
 second
 is
 I
 think
 a
 lot
 of
 people


are
 starting
 to
 see
 that
 the
 cost
 of


software
 is
 coming
 down
 and
 it's
 it's


actually
 very
 very
 easy
 to
 produce
 code.


But


unfortunately,
 we
 still
 see
 in
 practice


that
 running
 evals
 is
 incredibly


challenging,
 especially
 from
 an


infrastructure
 side
 of
 things.
 Um,
 and


in
 particular,
 as
 we
 get
 to


longer-running
 agents,
 it
 means
 that


it's
 really
 important
 to
 have


infrastructure
 that
 can
 stay
 consistent


over
 a
 long
 period
 of
 time
 and
 then
 if


interrupted,
 can
 be
 resumed
 and


respawned
 back
 up.
 Um,
 we
 have
 I
 think


just
 recently
 crossed
 6
 trillion
 tokens


just
 in
 evaluation.
 Um,
 so
 we
 run
 a


considerable
 asset
 of
 evals
 and
 we
 run


everything
 in
 as
 highest
 degree
 parallel


as
 possible.
 Um,
 so
 I
 think
 this
 has


really
 been
 load
 tested,
 but
 I
 think


other
 people
 are
 going
 to
 run
 into
 this


even
 on
 a
 much
 smaller
 scale.
</details>

第三，很多现有的基准测试针对的是单轮提示与单轮回复，但在实际业务中，**一切都是多轮交互（multi-turn）**。你最初有一个自认为面面俱到的需求规格（spec），但随后会收到反馈的问题，或者在做出成品后会有额外的意见，需要通过更多轮次的迭代才能推动产生最终结果。因此，基准测试与评估必须切实覆盖这种多轮交互的环节，这一需求不会消失。

<details>
<summary>Original English</summary>
Uh,
 and
 the
 last
 is
 that
 I
 think
 a
 lot


of
 the
 existing
 benchmarks,
 they
 deal


with
 a
 single
 prompt,
 single
 response,


but
 in
 practice
 everything
 is


multi-turn.
 Uh,
 you
 have
 an
 initial
 spec


which
 you
 think
 covers
 everything,
 but


then
 you
 get
 questions
 back
 or
 you
 have


additional
 feedback
 once
 something's


built
 and
 then
 it
 takes
 more
 of
 this


iteration
 to
 actually
 drive
 to
 the
 end


output.
 And
 so
 I
 think
 benchmarks
 and


evals
 need
 to
 actually
 cover
 this


multi-turn
 component.
 That's
 not
 going


to
 go
 away.
</details>

### 案例研究：用评估大幅缩减研发 Token 成本

来看一个具体的案例研究。在我们自己的团队中，我们做了一个小型的“Token 拉满”（token maxing）实验：我们获得了一些工具的免费访问权限，并开放给了所有工程师。他们非常充分地使用了这些无限制的 Token。回过头来看那个月，我们消耗了价值 150 万美元的 Token。而团队大概只有 10 到 12 个人，那个月在 Token 上的花费大约是薪资支出的 10 倍。这虽然很疯狂，但我们看到了极佳的产出。因此，我们的目标是设法让所有工程师保持相同的产出水平，同时大幅降低成本。而我们实现这一目标的解决方案，自然就是构建评估。我们在内部构建了一系列工具，现在已将其作为一款名为 ValSmith 的产品对外推出。这是我们在编程领域所做的事情，我认为这也预示着其他知识工作领域未来的走向。我们所做的是将 GitHub 仓库作为核心载体，观察已经完成的工作以及正在进行的工作。特别是，GitHub 仓库由 Pull Request（PR）构成，每个 PR 都包含一个 GitHub Issue 和对应的解决方案。因此，我们能够拨回时钟，把这些相同的任务交给 Agent，看看它们能否达到人类工程师的同等工作水平。

<details>
<summary>Original English</summary>
So
 to
 look
 at
 a
 case
 study
 in


particular,
 when
 we
 looked
 at
 our
 team,


we
 did
 a
 little
 token
 maxing
 experiment


uh,
 where
 we
 we
 got
 free
 access
 to
 some


tools
 and
 just
 gave
 it
 to
 all
 the


engineers.
 Um,
 and
 they
 they
 really
 made


use
 of
 these
 unlimited
 tokens.
 Um,
 and


and
 if
 if
 we
 actually
 look
 back
 for
 that


month,
 we
 spent
 1.5
 million
 dollars


worth
 of
 tokens.
 This
 is
 like
 a
 team
 of


I
 think
 10
 or
 12.
 So
 it's
 roughly
 10


times
 the
 amount
 we
 were
 spending
 on


salary
 for
 tokens
 in
 that
 month.
 Uh,
 and


so
 that
 was
 pretty
 insane,
 but
 we
 saw


great
 output.
 And
 so
 our
 goal
 was
 to
 try


and
 maintain
 the
 same
 level
 of
 output


across
 all
 these
 engineers,
 but


massively
 cut
 cut
 down
 on
 cost.
 And
 and


really
 our
 solution
 to
 do
 that
 was
 of


course
 to
 build
 an
 eval.
 Um,
 we
 built
 a


bunch
 of
 tools
 internally
 and
 then
 have


now
 exposed
 this
 as
 a
 product
 called
 Val


Smith.
 Uh,
 and
 so
 this
 is
 you
 know,
 what


we're
 doing
 in
 coding
 and
 I
 think
 it's


again
 a
 sign
 of
 what's
 going
 to
 what's


going
 to
 come
 in
 other
 parts
 of


knowledge
 work.
 Um,
 so
 what
 we
 were
 able


to
 do
 is
 look
 at
 the
 GitHub
 repo
 um,
 as


a
 essentialized
 way
 of
 seeing
 what
 work


has
 already
 been
 done
 and
 what
 work
 is


continuing
 to
 happen.
 Um,
 and
 in


particular
 GitHub
 repos
 are
 comprised
 of


PRs
 or
 pull
 requests
 which
 have
 a
 GitHub


issue
 and
 a
 resolution.
 And
 so
 what
 we


can
 do
 is
 unwind
 the
 clock
 and
 give


those
 same
 tasks
 to
 agents
 to
 see
 if


they
 could
 have
 equivalently
 done
 the


work
 of
 humans.
</details>

通过这种方式，我们更加清晰地了解到哪些模型是大材小用、价格过高且没有必要使用，而哪些模型能够切实完成任务。这也是许多人的直觉与实际情况不符的另一个例证。大家可能会想：“我们用了大量的闭源模型，应该尝试自建托管开源模型来削减成本。”大家可以看到我们这里对 GPT-5.6 Soul 和 Kimiko 3 的对比：5.6 Soul 表现更好，在这个内部评估中得分高出 2%；同时，比起在高度优化的推理技术栈上托管开源模型，它还要便宜得多——单次任务只需 2.50 美元，而不是 11 美元，而且速度更快，耗时只有一半。因此，并没有充分的理由认为“使用开源模型就一定能降低成本”这种直觉是成立的。这带来了两个主要转变：第一，我们能够明确要采购哪些工具，以及这些工具在整个组织内的使用限额；第二，我们可以向工程师提供建议，明确指出“针对这个特定的 GitHub Issue，你实际上应该搭配这款模型来使用这一款编程工具”。这大幅降低了成本。我们的支出减少了 90%，但依然能够保持同样的产出水平。

<details>
<summary>Original English</summary>
Um,
 and
 in
 doing
 that
 we
 found
 a
 a
 a


much
 clearer
 understanding
 of
 which


models
 were
 overkill,
 were
 way
 too


expensive,
 and
 did
 not
 need
 to
 be
 used,


and
 then
 which
 ones
 were
 actually


capable
 of
 getting
 the
 task
 done.
 Uh
 and


I
 think
 again,
 this
 is
 another
 place


where
 the
 intuitions
 that
 a
 lot
 of


people
 have
 may
 not
 be
 what's
 actually


born
 out
 in
 practice.
 So,
 I
 think
 you


may
 see,
 "Oh,
 we're
 using
 a
 lot
 of


close-source
 models.
 We
 should
 try
 and


cut
 costs
 and
 use
 our
 own
 self-hosted


open-source
 model."
 Uh
 you
 can
 see
 the


comparison
 here
 we
 have
 between
 GPT-5.6


Soul
 and
 Kimiko
 3,
 and
 we
 see
 that
 5.6


Soul
 is
 better.
 It's
 It's
 going
 2%


better
 on
 this
 internal
 eval.
 It's
 also


considerably
 cheaper
 than
 than
 hosting


it
 through
 a
 very,
 you
 know,


inference-optimized
 uh
 stack.
 So,
 it's


$2.50
 instead
 of
 $11,
 and
 it's
 faster,


half
 the
 time.
 And
 so,
 there's
 no
 real


reason
 why
 um
 this
 kind
 of
 intuitive


sense
 of
 using
 open
 source
 would
 be
 a


legitimate
 way
 to
 drive
 down
 cost.
 Um


and
 so,
 this
 has
 resulted
 in
 two
 main


differences.
 One,
 we
 can
 actually
 figure


out
 which
 tools
 we're
 going
 to
 procure,


what
 the
 usage
 limits
 of
 those
 things


should
 be
 across
 the
 organization,


but
 then
 also,
 we
 can
 give


recommendations
 for
 engineers
 and
 say,


"We
 think
 that
 for
 this
 GitHub
 issue,


you
 should
 actually
 use
 this
 particular


coding
 tool
 with
 this
 model."
 Uh
 and


this
 is
 able
 to
 drive
 the
 cost
 down


considerably.
 I
 think
 we're
 spending
 90%


less,
 but
 still
 able
 to
 get
 the
 same


output.
</details>

### 组织知识与评估驱动的落地优势

我想抛给大家的一个问题是：我们正在继续扩展这种方法，并将这种编程模型推广到其他领域、知识工作、法律、金融等。但核心问题在于：**你在哪里追踪企业过去已经完成的工作历史？** 有些律所已经存在了上百年。那么，体现组织品质沉淀的数据保存在哪里？你在哪里追踪卓越工作的标准？在今天，这些信息可能散落在电子邮件中——记录着员工与客户的过往回复，可能保存在 SharePoint 中，或者存留在 Databricks 的转储数据中。但我认为，这是很多企业拥有却尚未意识到的核心宝藏，它将成为构建评估的关键突破口，进而成为更系统化推进 AI 落地的关键突破口。

<details>
<summary>Original English</summary>
I
 think
 the
 question
 I
 would
 have
 for


you
 all
 We're
 We're
 continuing
 to
 expand


this
 approach
 and
 and
 take
 this
 model
 of


coding
 to
 other
 domains,
 knowledge
 work,


legal,
 finance,
 things
 like
 that.
 But


the
 key
 question
 is,


where
 are
 you
 tracking
 the
 history
 of


work
 that
 has
 already
 been
 done
 by
 that


firm?
 Some
 of
 these
 law
 firms
 have
 been


around
 for
 like
 100
 years.
 And
 so,
 where


Where
 is
 that
 I
 think
 quality
 of
 the


organization
 stored?
 Where
 are
 you


tracking
 the
 standard
 of
 excellence?
 And


so,
 that's
 today
 may
 exist
 in
 places


like
 email
 from
 the
 history
 of
 responses


that
 people
 have
 had
 with
 their
 clients,


may
 exist
 in
 SharePoint,
 may
 exist
 in


Databricks
 dumps,
 but
 I
 think
 this
 is


the
 key
 treasure
 trove
 that
 a
 lot
 of


companies
 have
 and
 don't
 realize
 will
 be


the
 major
 unlock
 for
 evals,
 and
 then
 the


unlock
 for
 AI
 adoption
 more


systematically.
</details>

一旦构建了这些评估，它们不仅能推动技术落地，我们还发现它们能够带来更多维度的优势应用：
- **容量合理化（Right-sizing）**：不再盲目追求最大化消耗 Token，而是弄清楚整个组织合理的使用上限应该是多少。
- **商务谈判（Negotiation）**：一旦明确了自己的真实筹码，你就可以在批量采购定价的谈判中占据主动。
- **智能路由（Routing）**：这正成为许多 AI 产品的核心原语，用户也可以直接实现。企业可以构建智能路由系统，自主匹配最合适的模型。
- **微调或后训练（Fine-tuning or post-training）**：这是铸造任务最可靠的途径，并配有外部评估集以确保该方案切实有效。

最后留给大家的一个思考是：对很多公司来说，过去的竞争优势以机构知识（institutional knowledge）的形式存在于员工的大脑中。而评估能够让你把这种竞争优势代码化（codify），用文字、脚本和语言将其明确沉淀下来。这将是确保企业在 Agent 时代取得成功的最大驱动力。好的，这就是我的全部内容，谢谢大家。

<details>
<summary>Original English</summary>
Once
 these
 evals
 are
 constructed,


they
 can
 enable
 adoption
 to
 happen,
 but


we've
 also
 seen
 that
 there's
 more


advantageous
 ways
 that
 they
 can
 be
 used.


So,
 first
 is
 right-sizing.


So,
 rather
 than
 just
 token
 maximizing,


how
 do
 you
 figure
 out
 what
 the
 right


usage
 limit
 should
 be
 across
 the


organization?
 Negotiation.
 Once
 you


realize
 uh
 you
 have
 actual
 leverage,
 you


can
 take
 that
 to
 the
 conversation
 you


have
 in
 bulk
 pricing.


Then
 routing.
 This
 is
 becoming
 a
 core


primitive
 in
 uh


in
 a
 lot
 of
 AI
 products,
 um
 but
 can
 also


be
 done
 by
 users
 directly.
 And
 so,
 they


can
 build
 intelligent
 routers
 that


actually
 figure
 out
 the
 right
 model
 to


use.


And
 then
 fine-tuning
 or
 post-training.


Uh
 this
 this
 can
 be
 the
 most
 reliable


way
 for
 you
 to
 actually
 mint
 the
 tasks


and
 then
 have
 an
 external
 eval
 set
 to


make
 sure
 that
 this
 approach
 is
 working.


Last
 thought
 I'd
 leave
 you
 with
 is
 I


think
 for
 a
 lot
 of
 companies,
 they
 have


a
 competitive
 advantage
 that
 has
 existed


in
 the
 heads
 of
 employees
 through
 things


like
 institutional
 knowledge.
 And
 what


evals
 allow
 you
 to
 do
 is
 actually


codify
 the
 competitive
 advantage
 and
 put


that
 down
 in
 words
 or
 in
 scripts
 in


language.
 Uh
 and
 that
 will
 actually
 be


the
 the
 biggest
 unlock
 for
 uh
 making


sure
 that
 a
 company
 succeeds
 through
 the


agentic
 era.
 Okay.
 That's
 all.
 Thanks,


everyone.
</details>

>> [掌声]

<details>
<summary>Original English</summary>
>> [applause]
</details>