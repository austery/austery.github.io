---
author: AI Engineer
date: '2026-06-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iNkFlCiij0U
speaker: AI Engineer
tags:
  - benchmark
  - agent-evaluation
  - task-quality
  - evaluation-methodology
title: 构建有效基准测试的科学与艺术：Snorkel AI 的元评估经验
summary: Vincent 分享 Snorkel AI 在构建基准测试方面的经验：任务质量、分布多样性、难度与模型余量、稳健评估方法是“科学”；论点、路线图与研究者体验是“艺术”，并提出环境复杂度、自主时长、输出复杂度三个方向。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Snorkel AI
products_models: []
media_books: []
status: evergreen
---
### 开场与背景
大家好，最近怎么样？很好。我很高兴来到这里，我来自旧金山，过来要走一小段路，但我非常期待今天演讲之后以及之后与大家交流。我叫 Vincent，是 Snorkel AI 的研究员（research fellow）和联合创始人。

今天我要讲的是构建基准测试的一些元评估（meta evaluations）。也就是我们发现在构建有效基准测试时真正有用的艺术与科学。我在 Snorkel 有幸与我们的研究人员、学术界和产业界的优秀合作者，以及开源社区一起构建优秀的基准测试。我想分享过去几年里我们的一些心得：什么样的基准测试能够塑造这个领域并推动它前进。

<details>
<summary>Original English</summary>
Hey everybody.

How's it going?

Lovely. Well, I'm very excited to be

here hailing from San Francisco. It's a

little bit of a trek over, but I'm super

excited to to uh chat with you all um

today after the talk uh and beyond. Uh

my name is Vincent. I'm a research

fellow and a co-founder at Snorkel AI.

And uh you know, today I'm going to be

talking about um some meta evaluations

for building benchmarks. The art and

science of what we found to be really

useful when building effective

benchmarks. I have the great privilege

at Snorkel of working with both our

researchers, uh great collaborators in

academia, industry, uh and the open

source community to build great

benchmarks. And I wanted to share some

of the learnings that we've had over

the, you know, last few years on on what

really makes for benchmarks that uh

shape the field and and move it forward.
</details>

我们是一个前沿 AI 数据实验室（frontier AI data lab）。我们的联合创始人在斯坦福、华盛顿大学（U Dub）、威斯康星等学术环境中有实验室，我们还有一支内部的部署工程师和应用工程师团队。我提这一点，是因为我们既能接触学术前沿、与前沿实验室合作，也能接触在实践中部署的真实企业和公司。作为一家公司，我们的重点是构建最好的数据集和环境，来定义并推动未来的 AI 能力。我们很幸运地处在这样一个独特的交汇点：既处于学术前沿，又通过在企业中的部署接触现实。

<details>
<summary>Original English</summary>
So, a little bit about us. Uh we're a frontier AI data lab. Uh we have, you know, labs both at uh at academic settings. You know, our our co-founders uh have have labs at Stanford, U Dub, Wisconsin. We have an internal team uh for deployed engineers, applied engineers. And uh I mention this because we get a lot of exposure to both, you know, the academic frontier, work with frontier labs, and also real enterprises and and companies who are deploying in practice. So, our focus as a company is on building the best data sets and environments to define and advance future AI capabilities. And we are in a fortunate spot where we get to play at this unique intersection of both, you know, the frontier academically, but also um uh uh to contact reality with our deployments um in enterprises.
</details>

### 评估差距与基准测试的作用
今天我想谈谈我们在真实部署中看到的一种不对称。如今人们对智能体（agents）确实很兴奋，我相信这个房间里的每个人都玩过这些智能体，我们也看到了真实的进展，表现为在模型卡（model cards）上不断爬坡（hill climbing）。感觉（vibes）在改善，尤其是在编程方面，确实在发生转变。但是当你问个人、企业或这些大型组织，是否完全准备好放手让这些智能体在高风险环境中部署，你会得到一些犹豫。这并不是说能力不在那里，而是我们在实践中衡量这些智能体的能力，落后于能力本身所处的位置。这是我认为该领域最重要的挑战和研究问题之一，也是我们在 Snorkel 非常感兴趣的问题之一。

<details>
<summary>Original English</summary>
So, today I wanted to talk about an asymmetry that we see in our real-world deployments.

There's real excitement around agents today. You know, we see it at every person in this room, I'm sure has has played with these

these these agents and we see a real

progress marked by, you know, hill

climbing on model cards. We see the

vibes are improving, right? And truly

shifting, especially in coding. But when

you ask individuals and enterprises or

these, you know, large-scale

organizations if they're fully ready to

let these agents loose and,

you know, deploy them in high-stakes

environments, you you get a little bit

of hesitation. And that's not to say the

capabilities aren't there, but our

ability to actually measure these agents

in practice that is falling behind of

where the capabilities actually are.

This is one of the challenges and

research questions that I think are

actually one of the most important in

the field and one of the ones that we're

very interested in here at Snorkel.
</details>

我们认为，弥合这个评估差距需要一套工具箱。正如我之前提到的，我们坚信现场部署（field deployments），也就是把工程师和研究人员实际派到团队中，去接触现实，与大家一起把这些模型部署到风险很高的真实生产环境中，比如金融、保险、医疗，这些场景中重要的不只是一个数字，而是真实的结果。我们也很喜欢其他评估工具，比如红队测试（red teaming）、私有的人工评估（private human evals）、众包标注（crowdsource labeling），也就是今天大家讨论的许多主题，很高兴看到这些。但我们最强烈地认为的一点是：基准测试，尤其是开放基准测试（open benchmarks），仍然是衡量工具箱中至关重要的一环。

<details>
<summary>Original English</summary>
So, closing that gap, that evaluation

gap, we believe requires a toolkit,

right? As I mentioned earlier,

we're strong believers in field

deployments, right? So, this is

you know, actually deploying engineers,

researchers on our teams to

again contact reality and and and work

with folks to deploy these models in

real production settings where the

stakes are high, right? These are

finance settings, insurance,

you know, healthcare settings where it's

not just about a number, it's about real

outcomes. And we're also big fans of

other eval tools, right? This is red

teaming, private human evals,

crowdsource labeling, a lot of the the

themes that we saw talked about today,

which which has been awesome to see. But

one of the things that we

feel most strongly about is that

benchmarks, open benchmarks in

particular, remain a really critical

piece of the measurement toolkit.
</details>

最好的开放基准测试不只是对过去的进展拍一张快照、回头看。它们实际上是在定义进展、塑造这个领域，并为能力需要走向何处设定目标。即使看最近几个月，像 Terminal Bench、METR 的长时程（Long Horizon）基准测试、ARC-AGI 这样的基准测试，都是令人兴奋且关键的路标，指明这个领域的走向。因此，通往安全、可信的智能体之路，在实践中将真正依赖更多这样的基准测试。

<details>
<summary>Original English</summary>
The best open benchmarks aren't just

about, you know, taking a snapshot of

progress looking backwards. They're

actually about defining progress and

shaping the field and setting a goalpost

about where capabilities need to go.

And, you know, even looking at the last

few months, right? Benchmarks like

Terminal Bench, uh Meters Long Horizon

benchmark, uh RKG I, these are really

exciting and critical guideposts for

where the field is going and and and as

a result, the path to safe, trustworthy

agents

um will will really depend on more of

these benchmarks in practice.
</details>

### Open Benchmarks 资助项目
那么我们在 Snorkel 做什么呢？我非常幸运能参与其中的一件事是“开放基准测试资助”（Open Benchmarks grants）。几周前、大约一个月前，我们投入了 300 万美元来支持开放基准测试。这是一份很有趣的工作，我能与最好的学术团队和构建者合作，加速并资助下一波基准测试，它们将真正引导这个领域的方向。目前反响非常热烈，我承认评审上还有点落后。但我们很高兴看到社区目前提出的各种想法。在这次演讲中，我们已经评审了我认为超过 120 份申请，涵盖学术界和产业界实验室。我们想分享过去几个月的一些看法和心得：第一，对于有用的基准测试，什么是最基本的门槛（table stakes）？也就是说，如何构建真正有用的、能衡量进展的优秀实证“量尺”（empirical measuring sticks）？第二，是什么真正把那些塑造前沿的基准测试区分出来？归根结底，构建真正高效、有效的基准测试的艺术与科学是什么？

<details>
<summary>Original English</summary>
So, what are we doing at Snorkel? One of

the things that again I'm I'm very

fortunate to to be able to be a part of

is uh the Open Benchmarks grants. We

recently, a few weeks ago, a month ago,

uh

deployed $3 million to commit to Open

Benchmarks. And this is a really fun

job. I get to work with the best

academic teams, you know, builders, uh

to really accelerate and fund um the

next wave of benchmarks that's going to

really steer and and and guide where uh

the field is going. We've had a wild

reception so far. I'm a little

admittedly behind on some some reviews.

Uh but we've been really excited to see

what the community has come up with so

far. And in this talk in particular, you

know, we've reviewed I think over 120

applications so far spanning academia

and industry labs. We wanted to share a

few perspectives, a few learnings um

over the fast past few months about what

we view as one table stakes for for

useful benchmarks, right? How do you

actually build good empirical measuring

sticks that are actually useful, you

know, to to measuring progress? And two,

what really separates, you know, those

benchmarks that are shaping the

frontier, right? What what is the art

and and the the the science, if you

will, of building really efficient

effective benchmarks at the end of the

day.
</details>

在讲的过程中，我会有一个有趣的机会，也许有点太美式了，学一下 Timothy Chalamet，向过去几年里塑造了这个领域的一些伟大基准测试致敬，并结合这些维度来谈。我希望这些主题能引起你们的共鸣，也能激发一些新的思考：我们如何把大家日常工作中正在追求的这些心得应用起来，去塑造这个领域并推动它前进。这里有两大主题。在“科学”一侧，我们如何构建有效的量尺？我们会谈任务质量、分布控制，以及总体上稳健的评估。在“艺术”一侧，也就是优秀基准测试的差异化因素：如何构建对领域走向有论点（thesis）、能启发新路线图的基准测试，并且关键是面向这样的受众来构建，即研究者受众、构建者受众，使得采用变得更加顺畅，并成为这些基准测试的一等公民（first-class citizen）。

<details>
<summary>Original English</summary>
So, as I'm doing this, I'll have a fun

opportunity, maybe this is a little too

American, but to pull a Timothy Chalamet

and honor some of the greats, you know,

some of the great benchmarks of the last

few years

that have really shaped the field in

talking about some of these axes. And I

hope that these, you know, themes

resonate with you and also inspire a bit

of,

you know, kind of new thinking about,

hey, how how can we actually deploy some

of the learnings we're we're all kind of

driving towards in our day-to-day work

to, you know, shape the field and and

move it forward. So, two themes here

again on the science side, you know, how

do we actually build effective measuring

sticks? We'll talk about task quality,

distributional control, robust evals in

general. Um and on the on the art side,

right, really the the differentiators

for great benchmarks, um how do you

build benchmarks with a thesis on where

the field is going that inspire new road

maps, um and that critically are are

built for this audience, right, a

researcher audience, a builder audience

so that adoption is is something that is

a way smoother um and and a first-class

citizen uh for a bunch of these

benchmarks.
</details>

### 科学一：单个任务的质量
先从科学开始。这是我们在实践中，以及在产业界、学术界和前沿实验室的部署中看到的，什么造就了真正有效的量尺。

第一件事是单个任务的质量。也就是说，单个任务需要经过极其严格的验证。它们需要代表真实世界的复杂性，需要有定义良好、结构良好的指令，需要有可验证的解答，并且最好已经由真实世界的领域专家实际验证过。这里的 GPQA 是我最喜欢的基准测试之一，不仅因为它是一个持久经久的基准测试，直到今天仍然捕捉研究生水平和专业水平的知识，你仍然能在模型卡上看到它，而且我最喜欢的贡献之一其实藏在附录里。

<details>
<summary>Original English</summary>
So, let's start with the science. Uh

this is again what makes for really

effective measuring sticks as we've seen

them in in practice and in the

the deployments that we see uh in

industry and academia and with Frontier

Labs.

So, the first thing I want to talk about

is individual task quality. Right, this

is the idea that individual tasks need

to be exceptionally, rigorously

validated, right? They need to represent

real-world complexity. They need uh

well-posed, well-structured

instructions. Um they need verifiable

solutions uh that ideally have been um

actually validated by real-world domain

experts. Um one of the the benchmarks

here, GPQA, is one of my favorites, um

not just because it's been a very

lasting and enduring benchmark that

captures, you know, uh graduate-level

and professional knowledge uh even to

this day, right, you kind of still still

see this on model cards. But, one of my

favorite contributions is actually

tucked away in the appendix.
</details>

GPQA 引入了一种新的对抗式质量控制机制。其想法是：这些任务不仅需要定义良好，还需要其他专家能够解决。所以他们有一个非常严格的多评审者协议：有原作者，还有评审者和裁决者参与其中，并有修订的机会。这些任务真正在推动知识的前沿，对任何单个专家来说，要判断“对，这确实是个好任务”或不是，并非易事。因此，开发这种严格的对抗式质量控制机制，是我在这里最兴奋的贡献之一。如果你读附录，还会看到他们引入了新的激励机制：报酬实际上取决于是否达成一定的一致。我来自学术界，这里有一些来自同行评审流程的灵感，尽管同行评审有缺陷。但这种关于如何获得真正严格的多专家质量控制的创新，带来了我们在单个任务质量方面看到的那类结果，我们认为这是任何重要基准测试的关键基础。

<details>
<summary>Original English</summary>
GPQA uh introduced one new adversarial

uh quality control mechanism. So, the

idea was that not only do these tasks

need to be well-posed, um they need to

be tractable for other experts to solve.

So, they had a very very rigorous

multi-reviewer protocol where there was

an original author, you know, there were

there were reviewers and adjudicators in

the loop. There was opportunity for

revision. Right, these were tasks that

were really pushing the frontier of

knowledge and it was non-trivial for any

single expert to say, "Yeah, this is

actually good task or not." And so,

developing this sort of rigorous

adversarial

quality control mechanism was one of the

contributions I was most excited about

here. And if you read the appendix, you

also see that they introduce new

incentive mechanisms, right? Payouts are

actually based on whether there was

certain agreement and, you know, uh uh

coming from academia, you know, there's

there's uh some inspiration here from

the peer review process as as flawed as

that is, but, you know, this type of

innovation around how you actually get

really rigorous, you know, multi-expert

quality control um leads to the type of

outcomes that we see around individual

task quality that um we we see as a a

key foundation for any benchmark that

matters at the end of the day.
</details>

### 科学二：分布多样性
第二是分布多样性（distributional diversity）。其想法是，对于任何真正重要的基准测试，你要为该领域、为真实世界任务定义清晰的分类体系（taxonomy），并有意地分布这些任务。这可能意味着：我捕获了一段轨迹（trace）或一股真实世界的流量，记录我的智能体在真实世界中如何运行，我想真正代表这种分布。它也可能意味着：我特别去刻画并分类那些失败模式，它们看似矛盾地罕见，但在生产中却不成比例地重要。以经典的自动驾驶场景为例：黄灯、行人或摩托车骑手，出现的频率可能远低于其他类型的场景，但在这些场景中把它们做对却不成比例地重要。因此，定义这样的分类体系，并非常有意地在其中分布任务，我们认为是优秀基准测试的标志之一。MMLU 现在已有几年历史，构建了一个相当宏大的分类体系，涵盖 STEM、人文等 57 个学术和专业领域。它一直是理解研究生和专业水平知识的持久基准测试之一，我们同样认为，这在很大程度上是深思熟虑、有意为之的分类体系设计及朝此构建的结果。

<details>
<summary>Original English</summary>
Two is uh distributional diversity,

right? This is the idea that for any

benchmark that really matters, you want

to define a clear taxonomy for the

domain, for real-world tasks, and

distribute those tasks uh intentionally.

So, this might be, "Hey, I I captured a

a trace or or a kind of real-world

stream of um traffic along um, you know,

how my agent is operating in the real

world, and I want to really represent

that distribution." It could also mean,

"Hey, I'm specifically characterizing

and taxonomizing the failure modes that

are, you know, paradoxically rare, but

you know, disproportionately important

in in production, right? If you take

classic self-driving settings, right?

Yellow lights or, you know, pedestrians

or uh motorcyclists, right? Might

actually show up way less than other

other types of scenarios but are

disproportionately important, you know,

to get right in these settings. And so,

defining that taxonomy, being really

intentional about distributing tasks

across it is one of the home hallmarks

of uh great benchmarks in our view. Um

MMLU, um few years old now, uh

constructed a a quite ambitious taxonomy

of, you know, 57 academic and and

professional domains across STEM,

humanities, et cetera. It's remained one

of the lasting benchmarks for

understanding graduate and professional

level knowledge and again a lot of this

was as as we we believe a result of

really thoughtful and intentional

taxonomy designed and and

building towards that.
</details>

### 科学三：难度与模型余量
第三个维度是单个任务的难度和模型余量（model headroom）。基准测试没有饱和非常重要，它要暴露能力中真实的薄弱点，并可靠地区分处于前沿的各个模型所处的位置。我最喜欢的图之一是右上角的这张，功劳完全归于 ARC Prize Foundation 团队。ARC AGI-2 在很长一段时间里，几个月甚至几年，都没有饱和。大约 18 到 24 个月前，当推理（reasoning）大力推进时，我们看到能力出现了巨大跃升，而这对应着模型能力的真实跃升。这个基准测试是有意设计来代表人类具备、而模型当时不具备的某种效率或能力，它很好地捕捉了：这里有大量的模型余量，人类能做到这一点，差距在哪里？而且果然，它与最近的 o1 式推理推进相关性很好，这种推进在过去 18 到 24 个月里主导了这个领域。就在几周前，ARC 团队刚刚发布了 ARC AGI-3，发布时前沿模型都低于 1%。每一项任务在某种程度上都是人类可解的。因此它仍然是该领域最有意义、最令人兴奋的基准测试之一，任何新模型出来，人们都在等着看它在 ARC 上表现如何。我认为他们做得很好，这里的模型余量真的非常令人兴奋。

<details>
<summary>Original English</summary>
The third axis here is around difficulty

of individual tasks and model headroom.

Right, it's really important that the

benchmark is unsaturated that it exposes

real soft spots in capabilities and

reliably separates where models sit at

at the frontier. One of my favorite

plots is is the one on the top right.

This was you know all all credit to the

ARC Prize Foundation team.

ARC AGI-2 you know for a very long time

was unsaturated right for for several

months and years. And when there was the

big reasoning push you know maybe 18-24

months ago

we saw a massive leap in capabilities

that actually corresponded to a real

leap in model capabilities. Right, this

was a benchmark that was intentionally

designed to represent a type of

efficiency or capability that

humans have but models didn't have and

and they really kind of captured well

hey there's a lot of model headroom

here. Humans can do this.

Where's that gap? And again low and

behold it correlated quite well with the

recent you know 01 style reasoning push

that has really dominated the field in

the in the past 18-24 months. Just a few

weeks ago the ARC team just launched AGI

ARC AGI-3 and again at launch they had

frontier models under 1%. Every single

task was a human solvable to some degree

and so it remains one of the I think the

the most

meaningfully exciting benchmarks in the

space where you know any new model you

know people are kind of awaiting hey how

does it do do on ARC? And and I think

they did this quite well. Right, the the

kind of model headroom here is is really

really exciting.
</details>

### 科学四：稳健的评估方法
在实证测量方面，我想谈的最后一个维度是稳健的评估方法论。这一点可以讲得很深，我只捕捉一些高层想法：基准测试最好超越准确率，去捕捉真正重要的现实维度。这包括成本、延迟、推理轨迹的质量、一些中间步骤和工具使用。无论哪些维度对手头的能力真正重要，把它们作为奖励或监督信号捕捉下来都至关重要，而让基准测试衡量它声称要衡量的东西，在构建稳健、可复现的基准测试时，其实是一项不容易的工作。

Tau Bench（转写为 “Towel Bench”）是我们非常喜欢的一个基准测试，这些年它有过多次演进。它被构建来评估这些多轮智能体的任务完成情况。他们构建了一个巧妙的用户模拟器，而且不只是看准确率和完成度，还看对策略约束的遵守情况。比如右手边论文中的一个例子：一个模型订对了航班，但违反了票价舱位规则，仍然算失败，最终仍然是不可行。所以这种有意识地选择我们真正关心哪些维度、真正想衡量什么，并严格地衡量，是构建这些前沿评估时重要的标志之一。

<details>
<summary>Original English</summary>
This last axis here I want to talk about

on on the empirical measurement side is

all about a robust eval methodologies.

Now this goes really deep. So just kind

of capturing some of the high-level

ideas, benchmarks need to ideally go

beyond accuracy to capture real-world

dimensions that matter, right? This is

everything from cost, latency, you know,

the quality of the reasoning traces,

uh uh some of the intermediate steps and

and tool use. Whatever dimensions

actually matter for the capability at

hand, uh capturing those as reward or

supervision signals is really critical

and measuring what it what it claims to

um is is actually a non-trivial uh feat

uh in in uh you know, building robust

and and reproducible benchmarks. So

Towel Bench is a benchmark that we're

we're a big fan of, you know, it's had

multiple evolutions over the year, but

over the years, but it would it was a

benchmark that was built to evaluate

both task completion of these multi-turn

agents. They built a a clever, you know,

kind of user simulator, um but also, you

know, not just accuracy and completion,

but adherence to policy constraints. So

a model, for example, on the right-hand

side, this was the one of the examples

from the paper, a model that books the

right flight, but violates fair class

rules still fails, is still a kind of um

no-go at the end of the day. So um this

notion of hey, being intentional about

what axes we actually care about, uh

what do we actually want to measure and

measuring that rigorously, uh is one of

the hallmarks that uh matters when

you're when you're building um these

these frontier evals.
</details>

### 艺术一：基准测试要有论点
现在我想转向差异化因素：是什么造就了推动前沿的基准测试。这并不是说我在前几页提到的那些没有推动前沿。这些只是我认为对那些真正的研究贡献至关重要的特殊特征，它们真正塑造着这个领域的走向：所有实验室接下来会往哪里爬坡？这就是艺术，是帮助我们前进的秘方。

其中一个关键标志是，这些基准测试应该有一个论点（thesis）。它们应该有一个关于能力子空间、关于领域走向的研究问题。它应该重新审视先前的能力。而最有雄心的基准测试其实是对世界走向的一种声明。Terminal Bench 就是这样的赌注之一。它押注的是 CLI（命令行界面），不只是针对编程智能体，而是针对通用的计算机使用。在很多方面，我认为这已被证明是一个基本正确且影响深远的赌注。我们看到 Claude 和 Codex 的团队在这些基于编程和 CLI 的工具之上构建他们的通用企业能力，我们看到这个赌注得到了验证。Terminal Bench 仍然是最稳健、最重要的基准测试之一，在所有最近的模型卡上都有测量。所以，这是早期的一个赌注：我们认为 CLI 将作为核心界面、核心抽象和能力承载（affordance），对智能体以通用方式与真实世界交互非常重要。通过衡量这些能力，我认为它确实帮助加速了这个领域在这方面的运作。

<details>
<summary>Original English</summary>
So I want to shift a little bit now to

the differentiators, right? What

actually leads to the benchmarks that

push the frontier. That's not to say,

you know, anything I mentioned on the

last few slides have not pushed the

frontier. These are just special

characteristics that I view as you know,

critical to to the benchmarks that are

real research contributions that are

really shaping where is the field going,

where are the where are all the labs

going to hill climb next? Um and uh this

is this is the art, the special sauce

that um helps push us forward.

So one of the key hallmarks here is um

these benchmarks should have a thesis,

right? They should have a research

question about a subspace of

capabilities, about where the field is

going. It should revisit previous

capabilities. Um and the most ambitious

benchmarks are really a statement about

where the world is going. Terminal bench

um is one of these bets, right? It was a

bet on the CLI, not just for coding

agents, but for general purpose computer

use. And in many ways, I think this has

turned out to be a largely correct and

and consequential bet, right? As as

we're seeing uh teams at at kind of

Claude and and and Codex build their

general purpose, you know, enterprise

capabilities on top of these um coding

and CLI-based tools, we're seeing this

bet pan out. And again, Terminal bench

remains one of the most robust and kind

of uh most important benchmarks that are

measured on on all the recent uh model

cards. So, again, this was a bet early

on to say, "Hey, we think the CLI is

going to be really important um as a

core interface, a core abstraction and

affordance for agents to interact with

the real world in general purpose way.

And uh by measuring those capabilities,

you know, I I'd argue that it actually

um helped accelerate uh you know, how

how the field is operating in this way.
</details>

### 艺术二：为领域提供路线图
这里值得一提的第二点，是为这个领域绘制路线图的能力。一个真正塑造我们所有人走向的优秀基准测试，会产出新的路线图。它启发针对研究问题的新攻关方向，帮助大家构思，并想出关于基准测试和方法的新思考方式。我认为 SWE-bench 是这方面一个非常出色的例子。它是一个简单的想法，而最好的想法往往相当简单：你如何通过 PR（拉取请求）来利用现有的编程类能力？它催生了一整个新的基准测试家族，从 SWE-bench Lite、Verified、Pro、Multilingual、Multimodal 等等。它的演进在今天仍然非常有意义。它改变了我们思考编程智能体的方式，而看到 SWE-Bench 团队的工作之后涌现出多少新的研究方向和受其启发的基准测试，在编程领域里是很棒的事情。可以说，在此之上还有很多创新空间。新的编程方式是什么样的？这些类型的工作流如何适用于“vibe coding”，以及开发者正在应用的这种新的抽象层？看到 SWE-Bench 团队奠定的基础，以及它将如何塑造我们未来对编程智能体的思考，非常令人兴奋。

<details>
<summary>Original English</summary>
The second piece here, I think, worth uh

mentioning is uh the ability to kind of

roadmap for the field. Um a a great

benchmark, you know, one that really

shapes where where all of us are going

is producing new roadmaps, right? It's

inspiring new attacks against research

problems. It's helping folks ideate and

come up with new ways for thinking about

uh benchmarks and methods in general.

And I think Sweet bench is uh really

phenomenal example of this, right? It

was a simple ideas, often the best ones

are quite simple, right? How do you um

kind of leverage um you know, existing

uh uh coding coding type capabilities

via via PRs. Uh and it's spawned a new

family of benchmarks, right? All the way

from Sweet bench light, verified, pro,

multilingual, multimodal, etc. And its

evolution, I think, is is still very

relevant today. It's evolved how we

think about coding agents, and one of

the things that's been awesome to see

with uh the SWE-Bench team is how many

um new research directions and kind of

inspired benchmarks have come after it

um in this coding space. And arguably,

I'd say, you know, there's a lot more

room um to kind of innovate on top of

this as well. What are the new ways of

um coding look like? How do these types

of workflows apply to 5 coding and kind

of this new layer of abstraction that

that's offered developers are are

applying? Um I think it's been really

exciting to see the the foundation that

the SWE-Bench team sets and how that's

going to um shape, you know, how we

think about coding agents moving

forward.
</details>

### 艺术三：研究者体验
接下来这一点，我认为被严重低估，那就是研究者用户体验（researcher UX）。我认为最有远见的基准测试构建者，都致力于研究者和构建者的体验。也就是说，用你的基准测试来运行模型和智能体要非常简单，贡献新任务、进行扩展要非常简单，而且，把从基准测试得到的一些信号用于 RL 或训练后调优（post-training tuning）也要非常简单。我认为这被严重低估了。让你构建并推出的东西易于社区或核心用户使用，是一条经典的产品原则。在这里，基准测试有核心用户，也就是其他的构建者或研究者。因此，投入时间和精力去构建这些界面，对一些最重要的基准测试的采用至关重要。

<details>
<summary>Original English</summary>
So, this team here, I think, is severely

underrated, and this is the notion of

researcher UX. Right? I think the most

prescient benchmark builders are

committed to the researcher and builder

experience. This is to say, it's really

simple to run models and agents against

uh your benchmark. It's really simple to

contribute new tasks, to extend. And

also, it's it's really simple to

leverage some of the the signals that

you're getting for the benchmark for RL

or or kind of tuning um post talk. I

think this is really underrated. Uh

it's, you know, a classic product

principle to make what you're building

and putting out there easy to use by the

community or by your core users. And in

this case, benchmarks have core users,

which are other builders or researchers.

And so, really putting in time and

attention to building those interfaces

has been important for the adoption of

some of the most important benchmarks.
</details>

值得一提的是，斯坦福 CRFM 的团队几年前构建了 HELM，我认为它开创了一个标准化、模块化的测试框架（harness），用于评估可复现的不同场景，以及针对一套标准模型测试台来评估模型。几个月前的 Terminal Bench 2.0 又随 Harbor 一起发布，在很多方面，Harbor 已成为构建智能体的团队事实上的测试框架和评估基础设施。所幸今天已有不少基于这一原则的开源软件。但在构建你的基准测试时，要考虑：它有多容易扩展？社区采用它并最终针对它爬坡有多容易？我认为这是决定这些前沿基准测试能否获得高采用率的一个被严重低估的因素。

<details>
<summary>Original English</summary>
Right? To call out, I think the the

Stanford team um at CRFM uh built HELM,

you know, several years ago, which I I

would argue kind of pioneered a

standardized modular harness for

evaluating reproducible, you know,

different scenarios, as well as kind of

models against a standard test bed of

models. Um

Terminal Bench 2.0, just a few months

ago, again, shipped with Harbor, which

has been, in many ways, the de facto uh

harness and and kind of evaluation

infrastructure for teams who are

building agents um more broadly. And so,

you know, thankfully we have a bunch of

open source

software out there today, you know,

based on this principle. But as you're

building your benchmarks, right, kind of

considering, "Hey, how easy is this to

extend? How easy is it for the community

to adopt and eventually kind of hill

climb against this?" I think is a

severely underrated factor for for what

makes for really high adoption of of

these frontier benchmarks.
</details>

### 框架回顾
这就是完整的框架。我可以讲得更详细，欢迎会后来找我。真正在实证上有意义的量尺，靠的是任务质量，以及对分布控制和多样性的关注，靠的是难度和模型余量，当然还有稳健的评估方法论，衡量在实践中真正重要的具体维度，并对此有明确的意图。而在“艺术”一侧，这些优秀的基准测试对前沿走向有论点，为领域设定路线图，并且真正优先考虑研究者用户体验。

<details>
<summary>Original English</summary>
So, this is the full framework. Again,

can go into more detail and and please

find me afterwards. But again,

what makes for really empirically

meaningful uh measuring sticks, right,

it's task quality and attention to

distributional control and diversity, uh

it's it's difficulty and model headroom,

and of course a robust eval methodology

that measures the concrete axes that

actually matter and it matter in

practice and is is intentional about it.

And of course, on the off side, right,

these these great benchmarks really have

a thesis on where the frontier's going.

Uh they set road maps for the field and

they really prioritize researcher UX.
</details>

### 下一波基准测试的三个方向
在结束之前，我想提出几个我们在 Snorkel 非常兴奋的维度，我们认为它们将涵盖下一波基准测试。我尽量在这里为创造力留出更多自由度，但我们认为这些是有很大空间去推进复杂度和现实感的领域。所以我想分享一点我们内部的路线图，以及关于这个领域走向、我们哪里需要更多基准测试和更多贡献的想法。

这是我们的观点：我们认为下一批优秀基准测试的维度有三个。我稍后会更详细地说明。第一，环境复杂度（environment complexity）：这些基准测试所处的运行环境有多复杂、多真实、多动态？它们是否代表了专业人士、科学家，或使用这些工具的人真正可能用到的真实世界场景？第二，自主时长（autonomy horizon）：这些基准测试是否代表了这些智能体所面对的现实且处于前沿的时间跨度长度？它们是否捕捉了自主性滑块（autonomy slider）上的不同点，从而代表用户把它们用作副驾驶（co-pilots）与完全自主智能体之间的不同用法？这在基准测试中是不是有意的设计？第三，捕捉广泛的输出复杂度。我认为这在今天探索得很不够。很多是基于聊天或文档的输出，而在细致入微、差异化的奖励信号方面则少得多，也就是日常工作中真正出现的真实产物（artifacts）。关键是还有新的产物，也就是我们甚至还没想象过的新形态：智能体如何与人类交互，智能体之间如何相互交互。

<details>
<summary>Original English</summary>
Now, before I wrap up, um I want to

propose, you know, a few dimensions that

uh we're really excited about at Snorkel

uh that we think are really going to

encapsulate, you know, the the next wave

of of benchmarks. Um tried to leave some

more degrees of freedom here for

creativity, but these are areas where we

think there's a lot of room to push

complexity, to push, you know, realism

in benchmarks. And so, I wanted to share

a little bit of our internal road map

and thinking around where the field is

going and where we need more benchmarks

and more contributions.

So, this is our point of view. Um we

think that uh the the axes for the next

great benchmarks are threefold. Um and

I'll go into a little bit more detail

about what I mean here um in just a

second. But one, it's environment

complexity, right? how complex, how

realistic, how dynamic is the operating

environment that these benchmarks are

working. Are they representative of

real-world settings that a professional,

that, you know, scientist, that someone

using these tools could actually use?

Two is autonomy horizon. Do these

benchmarks represent realistic and

frontier

horizon lengths that these agents are

operating against? Are they capturing

different points on the autonomy slider

that are again representative of how

users are using them as co-pilots versus

fully autonomous agents? Is this an

intentional design in the benchmark? And

three, capturing the wide range of

output complexity. I think this is very

under explored today. Right? Lots of

chat-based or document-based outputs. Um

not as much around nuanced uh kind of

differentiated reward signals, right?

Real artifacts that show up, um you

know, in day-to-day work that we that we

represent. And critically, um new

artifacts, right? New types of form

factors that we haven't even imagined

about, you know, how agents interact

with humans, how agents interact with

each other.
</details>

### 环境复杂度
下面分别说一说。第一个我不会讲得特别详细。环境复杂度，就是捕捉我们日常工作环境中的真实世界复杂性，而这个差距往往正是智能体今天失败的地方。以编程智能体为例：真实的代码库有组织特定的策略、大量的 Slack 上下文、截图、不稳定（flaky）的工具链、分布式的 CI、脑子里装着自己喜好与偏好知识的人类评审者，以及许多并行的贡献者。今天的基准测试只捕捉了这种复杂性的一部分，而且不只是在编程领域，在其他领域也是如此，提高复杂度水平并继续推动这些模型能做什么、以代表真实世界的使用，既令人兴奋，也是一个机会。

<details>
<summary>Original English</summary>
So, a little bit about each one. Um the

first one here, I won't go into all of

these in in significant detail, right?

Environment complexity is all about

capturing the real-world

complexity that that is uh in our in our

day-to-day working environments, right?

And this this gap is often where agents

fail today. Consider coding agents,

right? A real codebase has org-specific

policies, you know, lots of Slack

context, uh screenshots, flaky tool

chains, you know, CI that's that's kind

of distributed, um human reviewers with

knowledge in their heads about what they

like and what they prefer, um many

contributors in parallel. Benchmarks

today capture a fraction of this

complexity and you know, not just in

coding but other domains, there's a lot

of excitement and an opportunity to up

the level of complexity and continue to

drive what these models um can do to to

represent real-world uses.
</details>

### 自主时长
第二，还是自主时长。这完全关乎一个智能体在可靠性崩溃之前能运行多久。以客户体验智能体为例，在很多情况下，这些智能体可能会丢失几周前传达的上下文；不同的集成或产品规格可能会改变某个特定模型的实际规格或需求；重组（reorgs）可能会在中途改变优先级。真实世界的场景实际上代表了更多的复杂性，这些复杂性体现在这类长期的持续学习（continual learning）式场景中，它们代表了状态和环境的变化。所以我们认为，在构建代表极长时程和自主智能体的新基准测试方面，有很大的贡献空间。

<details>
<summary>Original English</summary>
Two, again on autonomy horizon, right?

Uh this is all about how long an agent

can operate before it reliably

before reliability breaks down. Right?

Let's take a customer experience agent,

um

you know, in in many cases, right? Uh

these these agents may lose track, you

know, of of context that was, you know,

delivered a few weeks ago, different

integrations or product specs might, um,

you know, change uh the actual spec or

requirements for for a particular model.

Reorgs can kind of shift, you know,

priorities midstream. Um, real-world

settings actually represent a lot more

complexity that again is represented in

these kind of long-term continual

learning type type settings that

represent kind of changes in state and

environment. Um, so we again think that

there's a lot of room to contribute and

and build out new benchmarks that

represent very very long horizon and an

autonomous agents.
</details>

### 输出复杂度
最后，这个维度完全关乎产出更复杂、更有代表性的工作，以及可用于不仅是评估、也可用于训练期间奖励信号的细致信号。这同样必须是复杂的，而且这个差距也在扩大。再以软件为例，或者一份提出战略建议的复杂报告。要定义“一个好的建议、一个好的战略提案、总体上一个好的路线图有什么是可验证的”，既不简单，也带有主观性。这其中的细微之处需要被很好地捕捉，需要捕捉组织上下文和真正好的人类判断。明天的基准测试，我们对能够捕捉所有这些场景的信号感到兴奋。还有可信的输出：智能体真正捕捉自身不确定性的能力，并能说出“我其实对此不确定，我需要停下来或者请求更多信息”。不只是纯文本答案的不同类型的输出，也是我们非常期待的。

<details>
<summary>Original English</summary>
And lastly, this axis is all about

producing more complex work, more

representative work, and also nuanced

signals that can be used for not just

evaluation, but reward signals during

training. This also has to be complex

and this gap is is growing as well,

right? Let's take again a software

example, right? Or or a complex report

for making strategic recommendations.

It's non-trivial and subjective, you

know, to define, "Hey, what is

verifiable about a good recommendation,

a good strategic proposal, a good

roadmap in general?" Um, the nuances of

this need to be captured well. They need

to capture organizational context,

really good human judgment. Um, and

tomorrow's benchmarks really, you know,

we're we're excited about um signals

that capture all of these settings.

Trustworthy outputs, right? The ability

for agents to actually capture their own

uncertainty and uh define, "Hey, I'm

actually not sure about this. I actually

need to stop or kind of ask for more

information." Again, different types of

outputs that aren't just, you know, a a

kind of plain text answer is something

we're really excited about.
</details>

### 结语
希望这能激发一些思考：我在做什么？我如何把它变成一个有意义的基准测试？我们仍在接受开放基准测试资助（open benchmarks grant）的基准测试申请，所以如果你感兴趣，请通过 benchmarks.snorkel.ai 联系我们，也欢迎直接联系我。我们很期待看到这个领域的走向，并再次用基准测试不只是衡量回顾性的进展，而是真正塑造未来前进的方向。感谢大家的时间，期待很快再聊。

<details>
<summary>Original English</summary>
So again, uh hopefully, you know, this

inspired a little bit of thinking

around, "Hey, what am I working on? How

can I turn this into a meaningful

benchmark?" Um, we are still accepting,

you know, benchmarks uh in in the open

benchmarks grant. So if you're excited,

uh please reach us at

benchmarks.snorkel.ai.

Feel free to reach me directly and uh

we're really excited to see uh where the

field is going and to again to use

benchmarks to not just measure, you

know, progress looking backwards, but

really shape where where things are

going moving forward. Thanks for your

time and excited to catch up soon.
</details>