---
author: AI Engineer
date: '2026-11-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=yzx4IuEh_tU
speaker: AI Engineer
tags:
  - agent-skills
  - model-evaluation
  - context-optimization
  - prompt-engineering
title: 评估与优化 Agent Skills：如何量化模型先验与新知识增量
summary: Nikolai Petrov 探讨了 Agent skills 的评估与优化方法。通过构建评估任务（evals）并结合类似 FActScore 的拆解方法，对技能按条目生成问答，借助模型裁判在有无技能下进行对比测试，建立包含知识冗余、技能退化、新知识习得与概念未掌握的四象限分析，帮助精简已知内容并减少 token 消耗。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Nikolai Petrov
companies_orgs:
  - Intel
products_models:
  - Sonnet
  - Haiku
  - Opus
media_books: []
status: evergreen
---
### Skills 的产生与类型

大家好。我叫 Nikolai Petrov，今天我们将讨论技能（skills）以及智能体（agents）对这些技能的认知。

<details>
<summary>Original English</summary>
Hello.
 My
 name
 is
 Nikolai
 Petrov
 and
 we


will
 be
 talking
 about
 skills
 and
 agents


knowledge
 of
 those
 skills.
</details>

我们最初是从简单的提示词开始的，当时我们在尝试各种新事物，让智能体执行新的工作，反复使用那些提示词，随后我们开始将这些内容打包进技能中，创建出可重复、可复现且轻便的功能或能力，用以指导智能体开展工作。

<details>
<summary>Original English</summary>
We'll
 start
 it
 with
 the
 simple
 prompts


where
 we've
 been


playing
 with
 the
 new
 stuff,
 new
 work


being
 done
 by
 the
 agents,
 repeating


those
 prompts
 over
 and
 over
 again,
 and


then
 we
 start
 packing
 those
 into
 the


skills,


creating
 repeatable,
 reproducible,


portable
 type
 of
 their


functionality


or
 capabilities
 that
 we
 can


teach
 agents
 to
 work
 with.
</details>

其中一些技能非常重要，在 GitHub 上获得了数百个标星。技能有不同的类型：有些是教给模型新知识，为模型带来新的认知或能力；但也有一些纯粹属于引导或流程类的技能，这类技能并不引入任何额外信息，只是用来实现我们希望智能体执行的可重复操作流程。

<details>
<summary>Original English</summary>
And
 some
 of
 those
 skills
 are
 very


important,
 hundreds
 of
 stars
 on
 GitHub.


There
 are
 different
 types
 of
 their


skills.
 Some


teach
 models
 something
 new,
 bringing
 new


knowledge
 or
 capabilities
 to
 the
 model,


but


they're
 also
 type
 of
 their
 just
 steering


or
 process
 skills
 where
 we


do
 not
 bring
 any
 additional
 information


but
 just
 getting
 repeat


table


flow
 of
 the
 actions
 that
 we
 want
 agents


to
 perform.
</details>

这两种类型都很有用。在本场分享中，我们将讨论带来新知识类型的技能，看看我们能从模型对这些技能的理解中获得什么。

<details>
<summary>Original English</summary>
Both
 are
 useful.
 In
 this
 session
 we
 will


be
 talking
 about
 new
 knowledge
 type
 of


the
 skills


and


we'll
 see
 what
 we
 can


get
 from
 the
 model's
 understanding
 of


those
 skills.
</details>

### 基于 Evals 的确定性效果验证

当打包好第一批技能并开始使用时，起初主要凭感觉判断它到底有没有起作用。但除此以外，还有更偏技术、更确定性的方法来检查技能是否有效，以及这些技能的影响是什么，那就是 evals（评估）。

<details>
<summary>Original English</summary>
So
 we
 get
 our
 first
 skills
 packed,
 start


using
 them


basically


starting
 with
 their
 the
 feel
 of


does
 it
 work
 or not.


But
 there
 is
 also
 their
 more
 technical


way
 and
 more
 deterministic
 way
 for
 the


checking
 if
 skills
 are
 working
 or not


and
 what's
 the


impacts
 of
 those
 skills


are
 evolves.
</details>

定义 evals 可以采用不同的格式，但从本质上讲，这就是你希望智能体能够解决的任务定义。你将它部署到位，理想情况下使其更具确定性，以便我们进行验证。我们可以设置两组对照：一组不加载技能，另一组加载技能并向上下文中提供这些额外信息。

<details>
<summary>Original English</summary>
There
 are
 different
 formats
 where


evolves
 can
 be
 defined,


but
 at
 the
 sense
 this
 is
 task
 definition


that
 you
 want
 your
 agent
 to
 be
 able
 to


solve.


You
 put
 it
 in
 the
 place,
 ideally
 more


deterministic,
 so
 we can
 validate
 it.


And
 we
 can
 two
 arms.
 One
 where
 no
 skill


loaded
 and
 their
 second
 one
 where
 we're


loading
 the
 skill
 and
 providing
 this


additional
 information
 to
 the
 context.
</details>

接着我们比较它们运行的情况。这里涉及多项指标：其一是解决了多少个评估任务。在这个案例中，在没有技能的情况下解决了五个任务中的三个；加载技能后，五个任务全部解决，这意味着我们多搞定了两个任务。此外，还会对 Token 使用量、完成这些任务所花费的时间以及其他因素产生影响。

<details>
<summary>Original English</summary>
And
 we
 compare
 how
 they
 runs.
 There
 are


multiple
 things.
 One
 is
 how
 many


evolves
 been
 solved.


In
 this
 case
 with
 no
 skill
 we're
 solving


three
 out
 of
 five.


With
 skill
 we're
 solving
 all
 five,


meaning
 that
 we
 get


two
 more
 tasks.


There
 also
 would
 be
 implications
 on
 the


tokens
 usage
 or
 time
 that
 it
 took


those
 tasks
 to
 be
 completed
 and
 other


factors.
</details>

但最终，我们是在对比这些指标，看看哪些是合理的，哪些不是。这是评估技能的主要工具之一，证明它们不仅是美好的想法，而且对智能体而言是切实有效的指令和上下文。

<details>
<summary>Original English</summary>
But
 at
 end
 we
 are
 comparing
 those
 and


seeing
 what
 makes
 sense
 what
 not.


And
 this
 is
 one
 of
 the
 main
 tools
 for


evaluating
 the
 skills
 and


saying
 that
 they
 not
 just


nice
 ideas
 but
 actually
 working
 pieces


of
 instructions
 and
 context
 for
 the


agents.
</details>

### 技能优化的瓶颈与 FactScore 思路

但接下来该做什么？我们到了拥有有效技能的阶段，它解决了一些评估任务。但我们知道，应该有更好的方法。模型在不断演进，我们可能还希望让技能更高效，也就是说消耗更少的 Token。那么这里有哪些选择呢？

<details>
<summary>Original English</summary>
But
 what
 next?
 We
 get
 to
 the
 stage
 there


we
 have
 their
 working
 skill.
 It
 solved


some
 evolves.


But
 we
 know
 that


there
 should
 be
 a
 better
 way.
 We
 have


models
 evolving.
 We
 have


some


maybe
 cases
 there
 we
 want


to
 get
 skill
 more
 efficient,
 meaning


consuming
 less
 tokens.
 So
 what's
 their


their
 options
 there?
</details>

一种选择是逐行修改，尝试暴力穷举所有不同的组合。另一种选择是通盘考虑哪些修改合理，比如参考用户对技能的反馈，看看技能在哪些地方表现良好、哪些地方不行。而且面对新模型，仅仅运行技能并观察其效果，有哪些途径？这些修改的颗粒度应该有多大？是代码行、句子还是概念？

<details>
<summary>Original English</summary>
One
 is
 just
 change
 line
 by
 line
 and
 try


brute
 force


all
 the
 different
 combinations.


Another
 would
 be
 to
 think
 through
 what


makes
 sense
 so
 maybe
 use
 something


as
 the
 user
 feedback
 on
 the
 skills
 to


see
 where
 skills
 perform
 well
 there
 it's


not.


And
 with
 new
 models
 just
 running
 skill


and
 seeing
 how
 it
 works,
 what's
 the


options
 there?


And


how
 large
 those
 modification
 should
 be?


Just


lines,
 sentences,
 ideas.
</details>

我们发现有用的做法是：与其碰运气，不如在这里建立一个更具确定性的流程，借鉴 FActScore 中条目（items）的概念。我们可以将技能和指令拆分成这些条目，并针对每个条目配备一对我们预期的问答。

<details>
<summary>Original English</summary>
So
 what


we
 found
 to
 be
 useful
 is
 instead
 of


relying
 on
 their
 luck,
 we
 can
 put
 more


deterministic
 process
 here


using
 idea
 of
 their
 items
 from
 their


fact
 score.


We
 can
 split
 their
 skill
 and


instructions
 into
 those
 items


and


for
 each
 of
 those
 have


pair
 of
 question
 and
 answer
 that
 we


expect.
</details>

这既可以是通用的概念（比如这里的命题），也可以是契约（contracts），在其中对行动提出更明确的预期。一般来说，每个技能我们会获得预设数量的条目，比如说每个技能有 25 或 30 个条目。

<details>
<summary>Original English</summary>
This
 could
 be
 either
 general
 ideas
 like


proposition
 in
 this
 case
 or
 contracts


there
 we
 put
 more


definitive
 expectation
 on
 their


action.


And
 in
 general,
 we
 will
 be
 getting
 their


some
 predefined
 amount
 of
 the
 items
 per


skill
 and
 we
 will
 have
 let
 say


25
 or
 30


items
 per
 skill.
</details>

### 评测矩阵与四种影响类型

然后针对每个条目，我们同样运行两个分支：一个没有技能，一个包含技能。同时设立裁判或裁判组来评估模型的回答。我们将这些问题提给我们关注的模型，再由裁判（理想情况下是不同系列的模型或裁判组）对这些问题的回答进行评估。我们会确保问题不会泄露答案。

<details>
<summary>Original English</summary>
Then
 for
 each
 of
 the
 items,
 we
 will


again
 run
 two
 arms,
 one
 without
 skill


and
 one
 with
 skill.


And
 we
 will
 have
 judge


or
 panel
 of
 judges
 that
 will
 be


evaluating
 model
 answers.
 So
 we
 asking


those
 questions
 to
 the
 model
 that
 we


interested
 in.


We
 evaluating
 those
 questions
 with
 their


judge,
 ideally
 different
 family
 of
 the


models
 or


panel
 of
 judges.


We will
 ensure
 that
 the
 question
 do
 not


leak
 answers.
</details>

视具体情况而定，我们可以在不提供工具或额外信息的情况下进行对比，以检查模型的内部理解；也可以为它配备一些工具（例如联网访问），这样更具实际意义。由此我们可以得到一个简单的四象限计数矩阵，主要用于检验模型是否知晓某项内容，以及技能对此产生的影响是如何映射的。

<details>
<summary>Original English</summary>
We


depending
 on
 the
 case
 can
 compare
 with


no
 tools
 or
 additional


information
 to
 check
 their
 internal


model
 understanding
 or
 provided
 with


their
 some
 tools
 like
 web
 access.
 So


it
 would
 be
 more
 practical.


And
 we


can
 get
 their
 simple
 forward
 counts


matrix.


Basically
 where
 we
 are
 checking
 that
 the


model


uh


knows
 or
 do
 not
 know
 something


and
 how
 this
 maps
 to
 their


skill
 impact
 on
 this.
</details>

最简单的情况是：无论有没有技能，模型都能回答出特定的问题。这意味着技能对此没有任何影响，并且这本身已经是模型先验知识的一部分了。

<details>
<summary>Original English</summary>
So
 the
 simplest


option
 is
 where
 model
 was
 able
 to
 answer


this
 particular


questions
 even
 without
 skill
 or
 with


skill.
 This
 means
 that
 skill
 have
 no


impact
 on
 this
 and
 this
 was
 already
 part


of
 the
 model's
 knowledge.
</details>

第二种情况是：在没有技能时模型其实能够正确回答，但加入技能后，我们反而看到了性能下降，模型在陈述或解释特定方面的能力退步了。

<details>
<summary>Original English</summary>
The
 second
 one
 is
 where
 without
 skill


actually
 model
 was
 able
 to
 answer
 this


correctly.


And
 by
 adding
 skill


we
 saw
 degradation
 in
 performance
 and


model
 capability
 to


talk
 or
 explain
 particular
 aspects.
</details>

理想的情况是：没有技能时模型无法回答某项内容，而有了技能后，我们开始看到它能够回答这些新类型的问题和场景，这也正是我们的目标——教会模型新的东西。

<details>
<summary>Original English</summary>
The
 ideal
 case
 is
 where
 without
 skill


model
 wasn't
 able
 to
 answer
 something


and
 with
 skill
 we
 start
 seeing
 that
 it


can
 answer
 those
 new


type
 of
 the
 questions
 and
 scenarios
 and


this
 is
 what
 we
 were
 aiming
 for
 teach


model
 something
 new.
</details>

但也可能存在第四种情况：技能写得不够理想，或者某些表述不够清晰，导致无论有没有技能，模型都无法做出回答；尽管这个主题对模型可能相关且重要，但它在一定程度上仍然错失了其中的一些概念。

<details>
<summary>Original English</summary>
But
 there
 also
 can
 be
 there
 fourth


option
 where


skills
 were
 written
 not


ideally
 or
 in
 some


might
 be
 not
 clean
 way


where
 model
 wasn't
 able
 to
 answer
 it


either
 without
 skill
 or
 with
 skill
 and


while
 this
 topic
 might
 be
 relevant
 and


important
 for
 the
 model
 it
 still
 sort
 of


misses
 some
 of
 those
 concepts.
</details>

最容易修复的是那些实际上损害了性能的指令或条目，而在流行的技能中，这类情况相当罕见。在下方的方框中可以看到，在 Anthropic 的技能中，近 400 个条目中只有 1 例，其他技能则完全没有。但对于那些受众较少、较不流行的小型技能，可能会遇到更多这种情况，我们在自己的一些实验中就观察到了这点。

<details>
<summary>Original English</summary>
The
 simplest
 thing


to
 fix
 are


instructions
 or
 items
 that
 actually


hurts
 performance
 and


for
 popular
 skills
 those
 are
 pretty


rare.


So
 in
 their


uh


box
 below
 you
 see
 that
 it's
 just
 one


case
 out
 of
 the
 mostly
 400


items
 in
 entropic
 skills
 and
 others


don't
 have
 those.


But
 for
 their
 smaller
 skills
 that
 are


less
 popular
 you
 probably
 having
 more
 of


those.
 This
 is
 what
 we
 are
 seeing
 with


some
 of
 our
 um
 experiments.
</details>

这是最直接、最容易修复的问题：确保你的技能不会降低模型的能力和表现，只引入关键相关的上下文。我们还可以对此进行着色标注，在这个场景中是按行展示的，但如果深入到条目维度，单行或单个句子中可能会有不同的颜色。这提供了一个可视化示例，展示哪些细节和指令能为模型带来有益的新内容，而哪些则是模型早已知晓的。

<details>
<summary>Original English</summary>
And


this
 is
 just
 straightforward
 the


simplest
 thing
 to
 fix


to ensure
 that
 your
 skill
 do
 not
 reduce


model
 capabilities
 and
 performance
 and


bring
 only
 prevalent


context
 there.


And
 we
 also
 can
 actually
 color
 this
 in


this
 scenario
 this
 is
 done
 by
 lines
 but


actually
 going
 with
 items
 you
 might
 have


there


different
 coloring
 for
 a single
 line
 or


a
 single
 sentence.


And
 this
 just
 gives
 your
 example
 there


visualization
 where


this
 would
 be
 helpful


details
 and
 instructions
 in
 terms


what
 new
 stuff
 you
 bring
 to
 the
 model


and
 what


is


something
 that
 model
 already
 knows.
</details>

### 评测成本与认知精细度差异

在成本方面，我们运行了所有这些问题去提问模型，但成本依然相对低廉：对于 29 个技能，使用 Sonnet 作为裁判，调用 Sonnet 和 Haiku 仅花费了 14 美元。

<details>
<summary>Original English</summary>
Cost
 wise


we
 are
 running
 all
 those
 questions
 and


asking
 model


but
 still
 relatively
 this
 is
 cheap
 for


29
 skills
 14
 bucks
 of
 there


sonnet
 and
 haiku


calls
 with
 their
 sonnet
 used
 as
 a
 judge.
</details>

我们还可以通过几种方式来检验特定知识的严格程度。我们有宽泛（lenient）和严格（strict）两种检验方式：前者考察通用概念，而后者则检验确切细节。你可以将这理解为对主题的总体认知与理解，对比对确切键值、参数、数值或具体步骤的掌握之间的差异。

<details>
<summary>Original English</summary>
And


there


couple
 ways
 how
 we
 also
 can
 check
 their


strictness
 of
 their
 some
 knowledge.


We have


lenient
 and
 strict
 ways
 of
 the
 checking


this
 where
 first
 checks
 the
 general
 idea


while
 the
 second
 one
 is
 checking
 for


exact
 details
 and
 you
 can
 think
 about


the
 difference
 between
 general
 knowledge


and
 understanding
 of
 the
 topic
 to
 the


understanding
 of
 the
 exact


keys
 parameters
 and
 exact
 values
 or


steps.
</details>

我们在跨模型测试中看到，两者的差距非常大，尤其是在规模更大的前沿模型中。例如我们观察到 Opus 对技能的总体理解能达到 70%，但在具体细节上的掌握却下降到了仅 22%。

<details>
<summary>Original English</summary>
And
 what
 we
 see
 across
 the
 models
 is


the
 difference
 is
 large


especially
 with
 their


larger
 frontier
 models
 where
 we
 see
 opus


dropping
 from
 70%
 understanding
 of
 their


skill
 in
 case
 of
 the
 general


understanding


to


just
 22%
 of
 the
 specific


details.
</details>

这非常符合我们的预期。我们看到新模型具备相当出色的泛化能力，能够理解概念；但为它们提供有助于解决这些问题的确切细节和数据，依然很有帮助。

<details>
<summary>Original English</summary>
And


this
 is
 much
 our
 expectations.
 We
 see


that
 new
 models
 are


pretty
 well
 generalized
 and
 understand


concepts.


But
 it's
 still
 helpful
 to
 provide
 their


with
 exact
 details
 and
 data
 that
 will
 be


useful
 for
 their
 solving
 those
 problems.
</details>

### 模型横向对比与优化落地

这里展示了在不同模型间对比这三个包含技能的热门代码库的概况。其中一个有趣的观察是：体量较小的模型总体上对技能的理解度较低，而体量更大的 Sonnet 理解得更好，这正是我们需要更大模型的原因。

<details>
<summary>Original English</summary>
Here
 is
 outlook
 of
 their


comparing
 those
 three
 popular
 rappers


with
 the
 skills


across
 different
 models.
 So
 one
 of
 their


interesting
 observations
 here
 is
 that


smaller
 model
 have


in
 general
 lower
 understanding
 of
 their


skill


with
 their
 larger
 sonnet
 having
 better


understanding,
 which
 is


why
 we have
 bigger
 models.
</details>

但同时我们也发现，总体而言模型已经理解了这些技能中的大量细节和上下文。你可以预见到，随着模型不断更新以及训练能力的进一步提升，模型具备的理解能力还会越来越多。此外我们发现，不同技能之间的这种表现差异相当显著。

<details>
<summary>Original English</summary>
But
 also
 we
 see
 that
 overall
 their


models
 already
 understand
 a
 lot
 of
 their


details
 and
 context
 of
 those
 skills.
 And


you
 would
 expect
 that
 with
 the
 newer


models
 and
 more
 advances
 in
 their


better
 training
 capabilities,
 we
 will


have


more
 and
 more


in
 terms
 of
 the
 model's
 understanding.


But
 also
 we
 see
 that
 this
 pretty


significantly
 differs
 skill
 to skill.
</details>

这并不是坏事，因为有些技能的定位本身就是指导性的。但了解这些技能如何为不同的模型和系列引入新知识，同样是一项有用的信息，理想情况下应该在更广泛的模型集合上运行这一测试。

<details>
<summary>Original English</summary>
And


it's
 not
 bad.
 Some
 skills
 are
 intended


to
 be
 directional.


But
 it's
 also
 useful
 piece
 of


information
 to
 see
 how
 those


skills
 bring
 new
 knowledge


to
 the
 different
 model
 and
 different


families
 and
 this
 should
 be
 run
 ideally


in
 the
 broader


set
 of
 the
 models.
</details>

不过，掌握这种“新颖性”（novelty）信息只是信号之一，它基本上是优化的初始向量。归根结底，我们仍需运行 evals 来验证对技能所做的所有修改是否真正有效。

<details>
<summary>Original English</summary>
But


just
 having
 their


this
 novelty
 piece
 of
 information
 is


just
 one
 of the
 signals.
 It's
 basically


initial
 vector
 for
 optimization.


At
 the
 end,
 we
 still
 have
 to
 run
 evolves


and
 validate
 that


all
 all
 changes
 that
 we


try
 to make
 with
 their
 skill
 actually


works.
</details>

一种较简单的场景是：我们可以审视技能，尝试从技能中移除部分或全部模型已知的信息，然后运行评估。评分结果可能保持不变，基本上我们能获得相同的结果，模型依然有能力解决这些问题。若是如此，那就太棒了，我们可以缩减技能体积，节省 Token 并节省上下文空间。这样，我们就能获得明确的指导，而不是盲目穷举和猜测可以或应该移除什么、添加什么，或者如何修复性能退化。

<details>
<summary>Original English</summary>
So
 the
 one
 of
 their
 simpler
 scenarios


would
 be
 we
 can
 look
 on
 their
 skill
 and


try
 to
 remove
 some
 or
 all
 of
 their


already


known
 pieces
 of
 information
 from
 the


skill
 and
 run
 evaluation.


It
 might
 come
 up
 with
 their
 same


scoring.
 Basically
 we
 will
 be
 getting


their
 same
 results
 model
 still
 capable


of
 solving
 those
 problems.
 Then
 great
 we


can
 reduce


skill
 size,
 save
 tokens,
 save
 context.


And
 instead
 of
 their


brute
 forcing
 and
 guessing
 what
 we
 can


or
 should
 remove


or
 add
 or
 how
 to
 fix
 their
 uh


degradations
 we
 can
 have
 a
 guidance.
</details>

所有这些度量和实验都是通过 docume 完成的，这是一个用于对比与智能体及上下文相关的一切要素的框架，无论是 skill、AGENTS.md 还是 MCP 工具等等。新颖性是该工具的功能之一，能为你提供技能优化和评估的初始向量；但它同时也提供 evals、上下文影响评估、路由、描述对比、命名比对等一系列与技能相关的功能。在这些方面，获得更具确定性的评估来对技能的去留与调整做出清醒决策，将会非常有帮助。非常感谢大家的时间，请大家继续编写出更好的技能。

<details>
<summary>Original English</summary>
So
 all
 of
 those
 measurements
 experiments


been
 done
 with
 the
 docume
 which
 is
 a


framework
 for
 their
 comparing


everything
 related
 to
 the
 agents
 and


context


where
 it's
 is
 skill,
 agents
 MD,
 MCP


tools,
 whatever.
 And
 novelty
 is
 one
 of


their
 pieces
 of
 the
 functionality
 where


you
 can
 get
 this
 initial
 vector
 for


their
 skill
 optimization
 and
 evaluation


but


there
 are
 also
 uh
 evals.
 There
 is


assessment
 of
 the
 context
 impact,


routing,
 comparing
 their


uh
 descriptions,
 naming,
 bunch
 of the


things
 that
 related
 to
 their


skills
 where
 it
 would
 be
 helpful
 to


actually
 get
 their
 more
 deterministic


evaluations
 to
 make


conscious
 decisions
 in
 terms
 of
 the
 what


should
 be
 done
 with
 the
 skills.


So
 thank
 you
 for
 your
 time
 and
 please


go
 ahead
 and
 write
 better
 skills.
</details>