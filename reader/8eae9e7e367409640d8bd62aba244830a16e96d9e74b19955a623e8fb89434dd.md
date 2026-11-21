---
author: AI Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hFNbPmzzcEs
speaker: AI Engineer
tags:
  - decision-models
  - system-one
  - recursive-models
  - human-computer-interaction
title: 递归决策模型与系统一：无需大语言模型处理每个决策的智能体架构
summary: Raymond Weitekamp 提出递归决策模型（RDM）架构，主张通过组合快速、低成本的系统一决策模型解决传统上被认为需要复杂推理的任务，探讨了决策与生成的阴阳互补、仲裁者机制以及基于纯决策的人机交互系统 Oso。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Raymond Weicamp
  - Daniel Kahneman
  - Alex Tseng
  - Omar Khattab
  - Rebecca Fiebrink
companies_orgs:
  - TypeSafe
  - MIT
  - Compound AI
products_models:
  - Jev
  - RLM
  - RDM
  - Oso
  - Wekinator
media_books:
  - Thinking, Fast and Slow
status: evergreen
---
### 系统一模型与决策模型定义

大家好，我叫 Raymond Wecamp。我今天的演讲最初定的标题是“递归决策模型”，而在提交该标题后我所意识到的，也是我们今天真正要讨论的，是操作系统一（Operating System One）。

好，那么先做一些简短的定义，这是什么意思？系统一模型这个名称，源自 TypeSafe 在不到两个月前发布 Jev 时引用的概念，来自 Daniel Kahneman 在《思考，快与慢》中普及的理论。我们大脑的系统一部分负责做出非常迅速、凭直觉的判断、直觉反应和条件反射——或许反射更偏向纯粹的神经学机制，但其核心思想是，我们做出的很多决定实际上并非纯粹理性的。系统一是快速的，系统二是缓慢的、更深思熟虑的逻辑推理和问题解决等。

我想，当他们发布 Jev 时，不太明确的一点是，他们是打算让“系统一”成为他们专有的模型家族名称，还是期望其他所有人也都称它们为系统一模型。我认为大多数人都在称它们为决策模型（decision models）。我当时不太想等大家争论出一个最终结果，所以在构思“递归决策模型”时，就直接沿用了这个说法。不管叫什么名字，实质都一样，我们其实不必过分纠结于“它们究竟是什么？它们到底算不算决策模型？”

这里的 Ali 提出，Jev 做出的是判断（judgments），而非决定（decisions）；做出决定的是你的代码。我认为这完全正确。然而，业界思潮以及 TypeSafe 之外从事该领域的大多数人，似乎都在向“决策模型”这个称呼靠拢。不过也有一小部分人坚持只把它们叫做零样本分类器（zero-shot classifiers）。

无论如何，我并不执着于这场命名之争，只是想解释清楚我在讨论什么。我认为现在与系统一、系统二以及 Daniel Kahneman 等概念关联起来的一点，虽然可能与人类行为方式有关，但从构建 AI 系统的角度来看，更有趣的问题是：如果推理实际上是由许多微小的决策构成的呢？

或者换一种视角来看：如果我们认为需要大量推理或深思熟虑认知处理的行为或任务，实际上可以通过大量非常微小、极其快速的决策以不同的方式来解决呢？我们在整个演讲中会反复回到这个问题，我认为这是理解其中趣味的关键所在。

<details>
<summary>Original English</summary>
Hey, my name is Raymond Wecamp and my talk today is originally titled recursive decision models and what I think I've realized since submitting that title is what it's really about what we're really going to be talking about today is operating system one.

Okay, so maybe some quick definitions what what does that mean?

So system one models the naming of system one models from Type Safe when they released Jev not even two months ago now I think came from this concept that Daniel Kahneman popularized in Thinking, Fast and Slow. This idea of like the system one part of our brains is making very fast and intuitive like judgment calls, gut reactions, reflexes. Maybe maybe reflexes more purely neurological, but that idea of like a lot of the decisions that we make are not actually like purely rational. And so system one is fast, system two is slow, more deliberate like logical reasoning, problem solving, etc.

And I think what was a little unclear when they when they announced Jev was whether they intended system one to be like their proprietary name family of models or like that's they were expecting all the other people to call them system one models.

I would say most most people are calling them decision models. And and so I wasn't really willing to to wait for the people to decide. And so so when I came up with recursive decision models you know it was just it was just kind of using that. So arose by any other name tomato tomato we don't really need too hung up on this idea of what are they? Are they decision models or not?

Ali here argues that Jeff makes the judgments, not the decisions. Your code makes the decision. I think that's that's absolutely correct.

And yet I think that that much of the zeitgeist and much of the folks working in the space outside of type safe are are kind of rallying around this idea of decision model being the term. There is the holdout camp of refusing to call them anything other than zero shot classifiers.

Anyways, I don't have a dog in the race. The naming just trying to explain what I am talking about. And I think that one of the things that is now connected here to this idea of system one, system two, Danny Kahneman, all this stuff maybe related to how we behave, but I think much more interesting from this perspective of building AI systems is what if reasoning was actually many small decisions?

And yeah, maybe a different way of seeing this like what what if behaviors or tasks that we might think of as requiring a lot of reasoning or a lot of like deliberate cognitive processing could actually be solved in a different way with a lot of very tiny, very, very fast decisions. We're going to keep coming back to this question throughout the talk and I think it's it's really key in what's interesting here. So
</details>

### 递归决策模型与“阴阳”收敛

递归决策模型（Recursive Decision Models, RDM）。这是我一直在构建的概念。简单来说，它可能是我非常兴奋的两件事物的结合。一件刚刚出现一年多，叫做递归语言模型（Recursive Language Models, RLM），来自 MIT 的 Alex Tseng 和 Omar。他们的原始博文发布就在一年多以前，在此祝 RLM 迟到的生日快乐。

然后，和许多人一样，我也迫不及待地想要从 Jev 的候补名单中出来，幸运的是很快就排到了。他们在这方面做得很好。

我一直与人们分享的一点是，我认为 TypeSafe 展现的过人之处，以及吸引如此多 AI 工程师关注的原因，在于将 Jev 视作“收敛”（convergence）的理念——决策是收敛的。

这与生成式 AI 形成了鲜明对比。生成式 AI 正在疯狂爆发，可以说是人类历史上增长最快的市场，该领域的大部分关注点和资金都集中在“生成”上。这很棒，生成也带来了许多令人惊叹的可能性。但如果仔细想想，即便拥有无限的 token，你拥有的其实也是无限的发散。生成式的东西很难自行收敛，我们依然会面对无用信息（slop），依然需要有人去决定什么东西才能进入生产环境。也许你搭建了代码工厂，由各种智能体替你做决策。但在一天结束时，真正让我兴奋、也让许多人对 Jev 这类系统一决策模型感到兴奋的核心，是这种“阴与阳”的平衡力量。

决策模型无法生成文本，它只能在选项中挑选。这与 LLM 形成鲜明对比，后者能够自由倾泻出开放式的文本。在早期，甚至很难让它们输出结构化格式。因此，我将这视作阴与阳的互补。

我不打算深入探讨递归语言模型，强烈建议大家去看看我今年夏天在 AI Engineer World's Fair 上的演讲——“递归编程智能体”（Recursive Coding Agents），在他们的 YouTube 频道上可以看到。我的幻灯片也是一个网站，录制完后会公开。那里会更深入地探讨为什么我认为 LLM 是新型推理模型，以及为什么这是一个非常重要的范式。

<details>
<summary>Original English</summary>
recursive decision models. So this is my concept that I've been developing. It's at its simplest perhaps the marriage of two things that I got really excited about. One just over a year old. It's called recursive language models, RLM. This is from MIT, Alex Sang and Omar. Their original blog post is just over a a ago. Happy birthday to RLM, belated birthday.

Um, and then like many others, I was also chomping at the bit to um, I think it's actually champing at the bit. Anyways, I was champing and chomping uh, to get off the freaking Jev weight list, which thankfully got off real quick.

Um, they did a good job with that. But I think that one of the things that I've been sharing with people is I think that part of what TypeSafe did so well and what captured the attention of so many engineers, AI engineers, is um, this idea of Jev as convergence, right? Like decisions converge.

And that is in direct contrast to generative AI, which has been you know, blowing up like crazy. It's arguably like the fastest growing um, you know, market in the history of the world. And um, so much of the attention and money in in the space has been about generation, right? And that's awesome and there's amazing things that are possible with generation.

But if you really think about it, like even if you if you have infinite tokens, right? You kind of have infinite divergence, right? Like the generative stuff, it's actually hard to um, converge. It's like we still have slop. Is someone still needs to decide like what's going to make it into production. And maybe you've got your like code factory set up there. All those like agents are doing those decisions for you.

Um, but at the end of the day like the the important thing that I got me excited and I think I think this is why many other people are so excited about about Jev, these system one models, these decision models is [snorts] this this idea of yin and yang, right? It's a counterbalancing force.

Um, and so the decision model cannot generate text. It can only uh, uh and pick and choose amongst options. Um and that is like in direct contrast to LLMs which have this ability to just like spit out uh free-wheeling open-ended um text. And in the early days actually hard to get them to structure their output. So I I see this as as yin and yang.

Um I am not going to go super deep into um recursive language models. I would highly encourage you to check out my talk from the summer from AI uh Engineer World's Fair this summer, recursive coding agents. It's on their YouTube channel. It's also at Um my slides here are also a um a website and I'm going to make them available publicly after I record this. Um that is going to go a lot deeper into why I think LLMs are the new reasoning models, uh why this is a really important paradigm.
</details>

### RDM 的三项基本法则

基于此，我们需要做一个直接的类比。在 RLM 的理念中，根递归语言模型能够调用子递归语言模型，子模型又可以调用下一级，然后你必须限制递归深度，以便能够从深层调用中返回。在这里，假设深度为 2 时它调用的是 LLM，那么这棵树中的叶子节点最终就是一个 LLM 调用。我们完全可以把这个类比映射到系统一决策模型上：一个根模型可以决定调用子 RDM，在设定的最大深度处，执行单次系统一决策调用。

但我们还必须考虑如何将它们组合在一起。稍后我会展示完全由纯决策构成的示例，这非常重要。左下方是我所说的“决策作为工具”（decision as a tool）。这与我关于递归编程智能体的演讲类似，只需将 RLM 替换为智能体即可：根编程智能体、子智能体等等。

将决策作为工具（或将 Jev 作为工具）是很自然的做法。在大家获得 Jev 权限的 24 小时内，就涌现了大量案例：用 Jev 进行上下文压缩，用 Jev 决定某个工具调用是否执行，或者用 Jev 作为路由器来决定将请求分发给哪个模型。这些都很酷，也有很多有趣的用例，大家上手探索的速度非常快。

但在我看来，更有趣、也更不显而易见的设计是：根节点本身就是一个决策模型，而调用语言模型或智能体仅仅是它可选择的决策路径之一。关于 RDM，我接下来要讲的内容几乎都属于这种范式，即让系统一决策模型充当整个系统的根或父节点。

在构思 RDM 的过程中，我给自己制定了**三项法则**：

1. **上下文保留在模型外部**：代码可以对其进行切片。在 Doom 的例子中，完整的游戏状态存在于外部，第一人称射击控制套件只获取其中的特定子集，地图探索鸟瞰视角决策模型则获取另一重视角。
2. **决策可以选择调用另一个决策**：同样受限于最大递归深度，形成递归树。这两点直接继承自 RLM 的核心思想（上下文外置、智能体可派生子智能体），并将其直接应用于系统一决策模型。
3. **必须在完全没有生成模型的情况下也能工作**：这对我来说至关重要。将 Jev 仅作为普通编程智能体的工具固然很棒，但很直接。若想解锁真正新颖的能力与行为，就要看在没有生成模型参与时能否运行，这也证明了 RDM 架构本身的自洽性；与此同时，它又**必须能够与 LLM 及智能体组合协同**。

<details>
<summary>Original English</summary>
So with that we do need to sort of to to draw the direct the direct analogy here. And so in the LLM idea, right, the root recursive language model has the ability to call sub recursive language models. And those could call sub recursive language models and then you can you have to sort of like cap the depth of recursion to just not um if you ever want to like come come back from the depths. Um and so here we say like okay at depth two then it's an LLM. So the the leaf node in this graph in this tree would would ultimately be an LLM call. We can make that exact analogy, that exact map onto system one models onto decision models and say okay we've got a root um that can decide to call a sub uh RDM uh and then there's some max depth at which point we just have to make like a single call, a single system one call, a single decision call.

Um but we also have to think about composing these together, right? And the um I am going to show some examples as pure decisions all the way down. That's very important.

Um this bottom left of what I'm I'm calling decision as a tool. Um so you could you can also this is what my recursive coding agent talk was about. It's like replace RLM with like agent, right? Coding agent. Okay, you got the root coding agent, you got the sub agent, da da da da da.

So I would say like this decisions as a tool or Jev as a tool was is like the obvious one. And within you know 24 hours of people getting access to Jev, there's tons and tons of examples here, right? People using Jev for compaction, people using Jev as the thing that decides whether a tool call can execute or not. People using Jev as a router to decide which um which model is going to get this particular request, right? So that stuff's um it's all very cool. There's some really interesting cases there and people just went buck wild going super fast um figuring that

I think to me what's I'm more interested in is um is not as obvious how you would set it up. Uh and that's where the root is a decision model and you only can you could choose as a decision to call to a language model or an agent um as one as one possibility. So almost everything that I'm going to be talking about with RDM is going to um be in this paradigm where we're actually letting the root or the parent of this system be the system one model, the decision model.
</details>

### Doom 案例：纯决策原语的组合

我想展示这个案例。大家可能有些印象，这是“Jev 玩 Doom”，是发布时推特宣传的一部分，引起了广泛关注。即便如此，我认为它依然是目前最被低估或至少最缺乏进一步探索的范式之一。来看一段简短的视频片段：

>> 将答案组合成玩家的下一步行动，并在游戏状态变化时持续循环。这就是我们所说的 AI 原语组合。这套组合以秒级处理瞬时游戏操作……

他们展示的第一个模块是构建好的决策框架，用于处理第一人称射击层面的操作：是驻留、前行、行走、闪避等。它非常简单，完全契合将不同系统组合成递归决策模型的理念——一个由不同类型决策构成的图。接着来看第二个组合：

>> 负责决定下一步探索何处，两者协同工作以打通关卡。

现在有了两个组合：一个是第一人称视角，另一个是鸟瞰或全局地图视角的决策。通过将两者组合，便得到了一个可以玩 Doom 的决策智能体。

据我观察，几乎极少有人在真正推进这种架构。将两个系统组合在一起是一个极其强大的思路。仅依靠两个独立但耦合的决策智能体，完全基于纯 Jev 调用，就能构建出一个通关 Doom 的智能体，这非常惊人，但在几百上千万人看过该视频后，其潜力仍被严重低估。这又回到了那个问题：如果推理本质上是由许多微小决策构成的呢？有哪些我们原以为需要复杂推理的任务，实际上只需要巧妙设计快速决策架构就能完成？

<details>
<summary>Original English</summary>
Okay, so now I want to show this for a couple reasons. This you might recognize this. This is the Jev Plays Doom. It was part of like the launch tweet storm and got a lot of attention. And yet despite that, I would say it's also one of the most um underappreciated or at least I would say underdeveloped um examples here. And so I'm just going to show a very short clip from this where

>> can pose their answers into the player's next action and keep repeating that loop as the game changes. This is what we call a composition of AI primitives.

>> of AI primitives.

>> Now this composition handles the moment-to-moment play at a second

>> basically the first thing that they're showing is this harness that they built of decisions to handle the like the first person shooting aspect. Is it going to hold, carry on, walk, dodge, blah blah blah. That has these actions, right? This is where I it's so simple and it's very much in line with this idea of composing systems together, recursive decision models, right? A graph of different types of decisions.

Um here we go. So this is the second composition.

>> that decides where to explore next and they can work together to make it through a level.

>> Okay. So now you have two compositions. One is the first person perspective. One is this like bird's eye or like map aware perspective and by composing those two things together you have a doom playing decision agent.

And now to me, I don't know, maybe I missed something, but I would say like um I have seen almost nothing. Very very very few um examples that are actually like taking this forward, that are that are moving this. This is a super powerful idea of composing these two systems together. It's really insane that with like essentially two separate um but coupled um so two distinct but coupled decision agents, right? You now have with pure Jev calls um a doom playing agent, right? Like that is really wild and I think really underappreciated despite the fact that probably like I don't know, millions or tens of millions of people saw this video. And it comes back to this question, what if reasoning uh was actually many small decisions, right?

And um or what are the types of activities or categories of things that we might naively assume would need reasoning when in fact what we need is a smart way of architecting small fast decisions. Okay.
</details>

### 纯决策层级：从高尔顿板到分层搜索

首先来看“纯决策到底”（decisions all the way down）的例子。大家可能熟悉高尔顿板（Galton board），通常在学习高斯分布或正态分布时会接触到：每个弹珠在每个钉子处各有 50% 的几率向左或向右下落，最终形成钟形正态分布曲线。

将递归决策层级可视化的最简方式是：如果钉子本身能够做决策呢？你可以将其类比为二分查找，每个带编号的球下落时，钉子判断“该往高去还是往低去”，逐层将数据分割。当钉子具备判断力时，就能实现精准分类。

像 Jev 这样的系统一模型，支持一次提出多个问题，跨多个维度进行评估。我们可以在三维空间中将其可视化：小球在下落过程中，一个轴按颜色分类，另一个轴按数字分类。横截面视图显示，作为分类器，它能将小球准确分流到对应的编号和颜色桶中。这是一个玩具示例，现实中单次分类调用或许就能完成，但这种层级可视化的模式正是 RDM 的运行基础。

TypeSafe 发布时的一个示例展示了分层搜索：他们使用包含 12,000 个商品类别的 Shopify 数据库，通过对 Jev 的分层调用实现束搜索（beam search）算法，根据用户查询确定所属的商品类别。

而在 RDM 中，你可以实现“无束之束搜索”：在每一层，系统仅询问下一层子类别中哪一个值得探索。面对 12,000 个类别，我们无需一次性塞满上下文窗口，而是从父类别开始，判定用户提到的“笔记本双肩包”应进入哪个分支，并由此迭代深入。代码层面可以采用贪心策略选择最优项，也可以保留概率排名前三的路径进行探索。其核心机制类似于二分查找，但组合的基本单元是一个分类器、一个判断、一个决策模型。

在视觉领域也是如此。Jev 在初版发布约一个月后支持了多模态。社区成员 Lily 展示了首个变体：在检测到目标后逐级局部放大，形成反馈循环，缩小包围框重新判定（例如检测甲虫）。TypeSafe 的 Nathan 进一步拓展了该思路，采用更接近二分查找的机制对图像进行递归对半切分（类似黄金螺旋式切分），并在每个切片桶中判断目标是否存在。

<details>
<summary>Original English</summary>
So now on to recursive decision models. I think the the glib tagline for this would be like a decision that can decide to make another decision. And um that's certainly an important element of it.

Uh while I was developing these um this idea, this concept, I've I've given myself three rules. Okay? The three rules of RDMs are

one that the context stays outside the model. And so the code um can cut it into slices. So the the in the Doom example the the full state of um the game uh is outside then those two little sub harnesses, the first person shooting harness has some specific subset of that. The um the map exploring birds-eye view decision model has another uh view of that.

Uh the second thing is this uh and now this is where it's a little different from that demo is the decision can choose to call another decision. And again up to this maximum depth we talked about this recursive tree. Now these two things are the most important fundamental aspects of RLM as well, right? The context is externalized. The agent can make sub agents. The RLM can call sub RLMs and sub LLMs, right? Um the so those two things are like copied straight from the RLM idea and then it's applying that directly to to system one models, decision models.

Uh the third piece is first it must work with no generative model at all. And this is very important to me um because I again I'm like all this like Jev as a tool for a normal coding agent is is is cool and there's some really great examples, but it's it's obvious to me. What was really interesting in terms of novel, what might unlock some novel behaviors, some novel capabilities um is what if there's no generative model at all. Also proves that the that the RDM architecture is actually uh correct. Like it should be able to work with no generation. And at the same time it must compose with LLMs and with agents, right? Um so those are my three rules in developing this concept of recursive decision models.

So first I want to show the the decisions all the way down example. Okay? So decisions all the way down.

Um you might be familiar with this idea of a Galton board. Um maybe you learned about this in the context of learning about um the the Gaussian distribution or or um uh what do they call it? Normal distribution. So like each ball has like a 50/50 chance at each pin of um falling and then you build this like bell curve um Gaussian distribution. So the simplest way that I could think of to to visualize this idea of um like recursive layers of decisions is now what if the pins could decide? So you could think of this kind of like a binary search like so each um numbered ball just like oh is this one going to go higher or lower, higher or lower? Um and so this pin is like splitting them in half, this pin spitting them in like to its half, etc. Um and again this is kind of like a silly, simple example, uh but now when those are smart, then we separate them perfectly.

Now, system one model like Jev, decision model, whatever we want to call them, uh well, we can ask about we can ask many questions at once. We don't have to just ask one on one axis. We could ask in multiple dimensions. So, we can now visualize that in 3D as like the ball's falling, they're being sorted uh by color in one axis, by number in another. We could put the cross-sectional views here and see that in the case that this is a perfect um classifier, right? Um it's perfectly classifying the numbered bucket that it should go in in the end, the uh colored bucket. So, again, this is very much a toy example in the sense that like actually what you you could do all of this in one classifier call, you could do all of this in one decision call. You don't need um this like recursive tree or like iterative tree to do it. But I'm um I want you to keep the visualization of this because it's exactly what's going to happen in some of these more specific examples of recursive decision models. Okay. So,

hierarchical search was one of the launch day uh cookbooks of Type Safe. And they what they did is they took um this Shopify uh database of 12,000 product categories and they implemented like a beam search algorithm with hierarchical calls to um Jev to figure out from from a user query which product category um the user's query was describing.

And what is unique as a simple demonstration of what's possible with recursive decision models is you can do the beam search without the beam. So, essentially at each layer here, we're simply asking well, um, of the next sublayer of products, what is the next one that we're interested [snorts] um, in exploring? And so, uh, in this in this example, we're exploring we're not exploring all 12,000 categories at once. That would like overload the context window. We're taking the parent category. We're deciding, okay, the user said laptop backpack. Okay, which category am I going to explore next? And and iterating along uh, from there.

Um, and we could decide in the code how we implement it. Do we do greedy? Do we pick like only the top one, right? Do we explore [sighs] top three um, that are rated uh, with the different probabilities, etcetera? But you could kind of again, it's like similar to a binary search algorithm in theme, except that like the compositional unit of it is a classifier, is a judgment, is a decision model, is a system one model. Again, too many names. I don't want to fight about the names.

Okay, visually, um, we can show this um, as well. And so the uh, Jev quickly became uh, multimodal uh, just a few weeks ago, about a month after the initial uh, launch. And um, Lily over here uh, posted like the first variation of this, which is like wherever you are getting a hit, you are um, now then kind of like zooming in to have like a feedback loop and like figure out you know, ask again on a on a smaller box. Okay, is this really uh, in her her case looking for um, beetles, right? Um, and then Nathan from the Type Safe team kind of followed up on this. And um, what's interesting about his implementation is it's much more like um, this um, binary search in the sense it's like a recursive halving of the of the image, right? Like a like a golden golden spiral style like halving, right? And then within those blocks, within those buckets, like what what is it that we're seeing?

So again, this is this is the these are simple simple examples that you you might not need recursion here like a you know a good vision model could probably answer the question in one shot and I think some people have have pointed that out clearly, but I'm I'm trying to give a number of different visual examples of of how a recursive decision model could work and where different ways of you seeing what that might look like in terms of the recursion.
</details>

### Factorio 演示与纯决策局限性

回到游戏案例，这是我利用递归决策模型运行《异星工厂》（Factorio）的演示。画面中有很多制造钢材的生产线。我的目标实际上是让递归决策模型教我玩 Factorio，因为这是评估度量系统的绝佳开放式环境。系统逐层判断：哪一组生产线存在异常，哪一条产线有问题，确定是某个机械臂需要维修更换，随后移动过去执行操作。

这里没有大型语言模型，没有任何生成式模型参与。虽然它在某种程度上属于规整矩阵的玩具示例，并且在寻路方面因缺乏路径递归而绕了远路，但如果不知情，人们很容易下意识认为这必须依赖高阶推理模型。完全不依赖生成式语言模型完成此类操作，展现了小决策网络的巨大潜力。

然而，“纯决策到底”存在明显的局限性：**必须有外部机制预先定义允许做出的决策集合**。拥有 TypeSafe 账户的人可能记得获取 API Key 时的问卷测试：“Jev 能否生成文本？”答案是否定的，填“是”就无法获取密钥。若仅依赖决策模型，所有选项必须由脚本、智能体或应用程序在程序层面预先枚举。

不过，对于游戏、浏览器以及诸多计算机使用（computer use）场景而言，预先枚举动作空间或许已经足够。在当前的电脑屏幕上，可选的操作和快捷键数量看似庞大，通常被视为必须由前沿推理模型处理的基准测试。但如果能程序化枚举所有可用选项，通过微小决策树同样可以实现极速导航。

<details>
<summary>Original English</summary>
So now let's get back to playing video games and so this is this is me playing Factorio with a recursive decision model.

So we've got all of these these lines that are making our steel or whatever. I'm I'm not very good at Factorio so apologize. I actually would like to my goal actually with this is to have my recursive decision model teach me how to play Factorio cuz I never really played before, but it's a it's a pretty cool like very open-ended way of evaluating the systems, the metric in systems. So you can see here it's got all these lines. It's figuring okay this group is the the one that's got a problem. This line is the one that's got a problem. It's this element, the inserter that I think I need to go fix and I need to replace it. So now it's going to run over and go do that.

And now the thing that I I want to point out here is there's there's no reason here. There's no large language model here. There's no thing generative here, right? So it's kind it I don't know. Maybe it's a little bit of a toy example and that it's literally like a matrix of these things and they're all the same. Um, but then it moves on to the next one. You'll see actually I should have maybe added some pathfinding composition of uh recursion because it ran like the long way around to go the next one. That was not totally perfect, right? But this is just an example of what what if you just looked at this without knowing it, I think you would I don't know. At least I would assume that you need some kind of reasoning model here. You need um and um yeah, you like this is like I don't know, like Cloud plays Pokémon level uh thing and it to me it's just absolutely fascinating that this can be done uh without any uh generative language model in there at all.

So again, we come back to this idea. What if reasoning or tasks that we might have assumed naively required reasoning can actually be done with these many many many small decisions?

All right. So the the weakness or the downside, um the limitation of decisions all the way down, right? Is that something has to have made those decisions. Like what what um are the allowed decisions? And um for any of you who have a type-safe account, you might remember the the quiz. You have to pass a quiz to get an API key. And the question is, can Jeff generate text or not? And the answer is no. And if you put yes, they won't give you an API key. So so the um you something like programmatically um whatever like a script has to do it, another agent has to do it, the application itself has to have pre-enumerated all of it, right? Um, if you can only have decisions, then there's no generative aspect.

Um, and what's crazy to me is that for games, for browsers, and I think even for a lot of elements of computer use, that actually might be enough, right? And I think if you kind of visualize now back all these examples that we just showed, uh, you hopefully can understand why with a tree of many, many, many small decisions, we can actually um, find things. So you imagine a game, the number the total possible um, actions available to a user, the total um, possible state of the game um, can be like enumerated programmatically and recursively addressed to make judgments, make decisions about what what the next move is um, in a browser. So these slides are is actually a website. Um, in this particular website, you can go up, you can go down, you can start a video. So there's like three interactive elements in the DOM. Um, the the you think about just think about it on your computer. Like really if you're on your computer right now, like how many um, how many actions are available to you on the current screen uh, or with like the hotkeys? Like it's it's a lot. And if and typically computer use has been this benchmark where you think of, oh, only the smartest frontier reasoning models can actually figure this out. Um, well, maybe not. Like maybe actually if you could just enumerate like all of the possible options to you um, you can navigate it with uh, very quickly um, and and we're going to get towards real-time machine learning examples in a little bit. Okay.
</details>

### 与生成模型组合：Map 共享接口与智能家居

单纯依赖决策模型存在局限，因此它必须能与生成模型组合。

在二分切分或大纲遍历（标题 -> H1 -> 子标题 -> 段落 -> 句子 -> 词）中，路径是程序化预定义的。而当引入生成模型后，调用树呈现出有机、涌现的图结构：生成模型负责发散，决策模型负责收敛。决策与生成的结合就像一套强大的自动机，能够促成复杂系统的涌现行为。

TypeSafe 曾发布过一个智能家居示例：当问题无法单纯通过决策解决时，交由 LLM 处理生成部分。我在此基础上进行了扩展，增加了更多房间和设备。面对高层指令（如“我们要去睡觉了”），系统通过决策模型极快地分解执行一系列子步骤：锁门、开灯、关闭其余设备；面对模糊指令（如“看场电影”），系统也逐步完成相应配置。

为了让决策模型与语言模型互相通信，需要一个统一的共享接口，我称之为 **Map（映射表）**。

决策模型只能基于给定内容进行指向和判断，而原始 LLM 输出的是无结构的 token 流。Map 可以理解为一组指针集合，包含名称（如“开电视”）、描述以及底层的具体实现函数（如翻转布尔值或复杂循环）。决策模型从 Map 中挑选合适项，底层代码执行对应函数；而 LLM 则获得了结构化接口，能够根据用户的新习惯来添加、编辑和修改 Map（例如将“电影时间”学习定义为开电视与关灯的组合）。

此外，Map 本身也可以是多维的，用于承载嵌入向量。例如 Every 的 Kieran Clausen 曾提出利用 Jev 构建低维且高语义密度的嵌入表示，RDM 代码库中的 Map 同样支持该机制。

<details>
<summary>Original English</summary>
So it also must compose generatively, okay? So there is a weakness um, with decisions only. And one way that you might think about this is um, like the the symmetry. So so um, not just the symmetry, but like the the pre-definition too of the tree. So like in these examples of like the halving search or this like hierarchical search, so like here I'm calling it outline walk. It's a similar example that you find the title, you find the um the H1 heading, you find the subsection heading, you find the paragraph, you find the sentence, you find the word, right? Um so at each one of those those layers of abstraction you can call another one. So that's not like super symmetric like this like pure binary search um halving one, but the paths are are essentially like predefined um or need to be programmatically defined.

Um and what's very interesting about then when you can um now have a generative element which I'm showing as like the square here. So like in this previous one it's like the generative ones diverge, the um the decision models converge, generative ones diverge, decision models converge. That's kind of an animation. Similar idea here. Now you can start to have So these are actual real call trees from the demo I'm about to show you, the smart house. You have these much more organic shapes and these much more like emergent graphs. And I think there's this um I have this idea that like that pairing, the yin and yang of the decision model and the generative model itself is kind of this very powerful automaton, right? That can kind of ratchet through the system and and generate emergent behavior complex systems uh from the pairing of these things. And you can get a some sense of that from from the the different geometries of these graphs that you're looking at without seeing the actual behavior.

Um Type Safe had a really cool uh cookbook uh that they also launched uh with or maybe it was called a um I don't know, demo or whatever um of a of a smart home. And so the the key thing from the smart home demo was that that they showed was when the problem cannot be solved purely with a decision, then it can go to an LLM to do generative element. So what I've done is adapt the smart home demo, make it much many more rooms in the home, many more appliances and things like that to show how the recursive decision model can can interact with the home. You can express a very high level thing like we're off to bed and then you can ask that and it will do all of the substeps very very quickly to get you to door locked and lamped on lamp on, everything off.

And then you can have these more like oblique type things that it's learning how to do over time. Let's watch a film. And then we will ask now it's going to like work through all those things.

In order for the decision model and the language model to talk to each other, we need some kind of shared interface. And so this is what I'm calling the map. And so again, the decision model can only point, it can judge various things that were given to it. And LLMs in their sort of most raw form have no structure to their output. It's perfectly open-ended stream of tokens, right? And so what we need is to kind of have a shared interface. And so I I call this the map.

And the the map is you could think of it as a a a set of like pointers in the sense that it could literally have like a name like TV on that has a very simple description and then some function in this case is like flipping this boolean to be on, right? It might have a much complicated function underneath it, like this sort of like loop here. But the key idea is that the the decision model can decide from the map which things are the right thing. It doesn't it so it can decide lights on. The code underneath it can implement the light can implement the lambda function lights on. Okay?

The LLM now has a structured interface to add and edit and modify the map. So the LLM can basically be learning from new user behavior that okay, this movie time is now the combination of turning on the TV and turning off the lights. And so now there is a shared interface, the shared substrate that both can talk to. I'm not going to go into it here because it gets a little bit more complicated, but I also want to point out that the map itself can be multi-dimensional. So it can essentially be representing embeddings. And and for example, like Kieran Clausen from Every had a a really interesting idea of using using Jev to create low dimensional but highly semantically meaningful embeddings. So so this map that I built into the RDM codebase can can handle that as well.
</details>

### 并发与仲裁者模式

我在递归决策模型中加入的最后一个原语是**仲裁者（Arbiter）**。

Jev 具备快速和成本极低的特点，不仅能在手机、老旧笔记本上运行，也能在最新的高端设备上高效运作。因此，我们可以大规模并行运行多个模型，在面对不确定性时进行投机性推测执行。

但如果让所有并发模型同时操作状态，就会引发状态冲突。类似 CPU 的并发控制：多通道并发读取，但在写入时必须引入锁机制防止冲突。这受到了 Alex Tseng 关于智能体投机性程序化工具调用研究的启发。

将该模式应用于音频流处理时：在说话人尚未说完整个句子时，多个通道已在基于局部信息投机性生成决策并进行投票。仲裁者的职责是评估何时积累了足够的置信度，从而允许某项动作穿透并改变系统状态；若缺乏该门控，较快的模型可能抢先修改状态，引发冲突。因此，仲裁者充当了控制状态变更的门控机制，对于高并发决策执行至关重要。

在实现方面，我最初将 RDM 实现为 DSPy 模块。一方面因为 Compound AI 团队迅速在 DSPy 中添加了对系统一 API 调用的支持；另一方面，DSPy 规范的结构化方式为验证 RDM 模块行为提供了良好的试验场。此外，我还开发了独立的 Rust 包 `rdm`，以便在各类系统中实现极速且可移植的部署。

<details>
<summary>Original English</summary>
The last property or the last primitive or behavior that I have included in my recursive decision models is what I'm calling the arbiter.

And here's why this is important, which is Jev is fast and cheap. There's decision models that can run on your phone, on a crappy 10-year-old laptop, on obviously you can get a better one on your new your new MacBook Pro, whatever. These things are very fast, They're very inexpensive, either from a compute perspective or a dollar's perspective. And that means that we can run many at once. We can we can actually speculatively run a bunch of them when uncertain, all in parallel.

And now the thing is that we need to if we just let all of those act on the state, um, we're going to have a lot of collisions. We're going to have a lot of challenge. So um, an example from how your CPU is working would be like that there can be many things reading in parallel, concurrently, um, but now we need some kind of lock when we write because we don't want to uh, collide, have colliding uh, writers. There's also an interesting idea also from Alex Tseng um, at MIT in Omar's group, the inventor of RLMs, about um, speculative tool calling, speculative programmatic tool calling for agents. Uh, and this is um, you know, informed my thinking here. But here's here's this idea applied to audio, which is like we have uh, I'm speaking uh, these sentences. We're having we're making decisions where I haven't even actually like finished the sentence. And so we essentially have um, at various times the arbiter is like deciding, okay, with the given information that I have across all of these different channels, what is the decision that I'm going to allow through? So you could you could imagine that like each one of these uh, lanes might like want to um, might be voting for like a certain action. And the arbiter's job is to figure out like where it has the confidence to actually like allow that action to change the state because again, if we let them all uh, act, we could have a lot of collisions. Let's say just a simple example, right? There's two there's two that are making uh, the their different models, they're making the same kind decision um and one of them uh goes a little bit faster, changes the state um before the second one makes a different decision that would have changed the state the other way. You can imagine all kinds of problems or collisions that could happen when you do that. So this this pattern of the arbiter is what I've developed um as a way of like um um it's like a gate for what can actually now um act on the system, change the state of the system. And it's very useful when you want to run many of these things in parallel.

Okay. So I'd love you to try it. Um my very first implementation of RDM was as a DSP Pi module. Um this is in part because the DSP uh team, in particular the the folks at Compound AI uh were very very quick to add support for System One API calls within um DSP. Um and secondly DSP is a very um opinionated way of working. It's very structured way of working and I found this to be very useful playground for um essentially ensuring that the ideas of recursive decision models um were structured in the right way that um the modules were behaving uh in the right way. Uh I have also uh made a standalone Rust package um RDM which is great when uh you want to bring uh very very fast and portable um RDMS to all kinds of systems. So yeah, check it out um in either my DSP fork uh if you're a DSP nerd or um the RDM package if you want to play around with Rust.
</details>

### 从身体束缚到激进人机交互

由此我们进入了“操作系统一”（Operating System One）。这里包含双重含义：既指代首个操作系统原型，也代表学习如何操作和调度系统一模型。

驱动我的核心动力，是人类与计算设备之间沉重的身体绑定。长期低头操作鼠标导致严重的肩颈劳损与重复性压力损伤；尽管各类人体工学设备层出不穷，数字工具也带来了巨大的生产力与经济价值，但现有的 QWERTY 键盘、鼠标和触控屏等主流物理接口，让身体承受了不必要的肉体消耗。

在关于 AI 工程师演进的漫画中，从最初在笔记本前佝偻打字，到引入 AI 辅助进行 vibe coding，再到摆脱传统屏幕直接与悬浮球对话，乃至最终仅凭意念即可调动系统的终极形态。通过 OSO 与递归决策模型，我目前正聚焦于语音交互阶段。

这可以追溯到我在普林斯顿笔记本乐团（Princeton Laptop Orchestra）的经历。近 20 年前，乐团探讨的核心命题就是“让笔记本本身成为乐器”：触控板、键盘、网络低延迟时钟同步等都被用作交互界面。当时我借助 Rebecca Fiebrink 开发的实时机器学习框架 Wekinator，利用极小的 KNN 和单层神经网络开展实时分类、映射与非线性插值实验。这段音乐计算背景让我重燃热情，希望将 RLM、Jev 和 RDM 结合起来，实现无需整天触碰键盘鼠标即可操作计算机的目标。

<details>
<summary>Original English</summary>
Okay. So this is where we move into operating System One. And I mean this uh with both of these phrasings, right? Um this is an operating system one. It's operating system one. And we're also learning how to operate system one models, right? So that's sort of the plan words here with operating system one.

And what's really important to me um personally is this physical enmeshment that we have with with our devices, right? Um I got like tech neck, right? Like my head's always down. I've got this like crazy like shoulder problem and tension from mousing all the time. When I was in grad school with really stressful deadlines, I was having all kinds of um repetitive stress issues and I've got every crazy vertical mouse and trackball and ergonomic keyboard that you could possibly imagine. But the like there is great um power and economic benefit in working with computers, in working with devices, in working with um our phones and our tablets in terms of being interconnected and be able in terms of being able to just do our normal jobs. And obviously anyone who is an AI engineer is going to need a computer to do their job. And at the same time like there is just all of this um I would say unnecessary suffering that is caused by the coupling of our physicality, like the coupling of our physical bodies to the physical computer, like through the traditional interfaces that have made their way in as the popular ones of society, the QWERTY keyboard, the mouse, the touchscreen, etc.

Okay, so some of you might recommend recognize this um this sequence. Uh I used it in my Recursive Coding Agents talk and it's also at the back of a t-shirt uh from the AI engineer code event in New York a couple years ago. And so so here we go. We've got the evolution of of the AI engineer. Uh you know typing on the laptop not great posture. You know now here it's got like the AI sparkle features. So we're we're vibe coding here maybe. Um you know in the third one you can see there's no more computer anymore. So now we're just like talking to this like orb. Um that's pretty cool. And uh then in the this ultimate like state of enlightenment, right? We just like think and and um things are manifested uh in in our world or I I don't even know what kind of uh wavelengths are coming out of this guy's head.

So I'm going here. I'd like to get to the the right um making some progress but think right now with uh with operating system one and my recursive decision models I'm I'm much closer to to the audio piece. Um and so I want to um I want to sort of take a um to go back in time a little bit. Um this these videos are um I'm getting old. They're they're coming up on uh not quite 20 years old. It's like 17 18 year old uh videos and I want to show you some experiments um in what I call radical human computer interfacing um from some of my work and music. I'm just going to show these really quick and I'll explain a little bit what's going on. So

so over here [music] so so just watch here really set this up. All right. So we've got like uh hitting these four different locations on the laptop and that is uh being classified uh to make a drum kit, right? Drum on by hitting our laptop. So, the laptops used to have um accelerometers built into them back when we're still uh have disk spinning disk hard drives. Um this one I'm not going to play um so much of, but you can um uh on the left one I'm like triggering the drum kit here. You can use the tilt of the um laptop to control different effects. I'm using the hit of this thing as the side chain compression. Um so it's like a ducking compressor every time I hit it. Uh and that's as much as I'm going to do on that, so I'm not going to go on that.

But this is um I want to bring this up um because it's personally meaningful to me. It's also the way that I actually learned um how to program and um the way that I learned machine learning. And this is through the Princeton Laptop Orchestra. Um it just celebrated its 20th anniversary uh this spring. And really the idea of the Princeton Laptop Orchestra was what would what does it mean um to have the laptop itself be the instrument? So, there were pieces where you're performing where the trackpad was the instrument. There were pieces where the keyboard was the instrument. There were pieces where all the computers were networked together on um Wi-Fi and like syncing super super um quick like low latency clock times to send messages back and forth to each other.

And um I was able to work with this uh brand new cutting-edge real-time machine learning framework called the Wekinator developed by Rebecca Fiebrink um to actually develop um and again this is like this is like 19 years ago, 18 years ago. Um these um very very small um you know K-Nearest Neighbors um like single layer neural nets um you know things that look much more like principal component analysis than like what we think as like transformers, large language models. And and um and you can actually um do uh what you might call like on the fly um machine learning to to um classify and map and do non-linear interpolations. Um it was just so so much fun. So I've been having a lot of fun with coming back to um that a little bit and kind of merging um my excitement about RLMs, um my excitement about Jev, these decision models, this this invention of recursive decision models and now towards um this kind of personal goal of just like like I want to be able to get things done through my computer and uh work in this field without hurting, without like touching a keyboard all day, without touching a mouse all day.
</details>

### Earshot 实验与 Oso 项目展望

作为 OSO 的前身实验，我构建了一个名为 Earshot 的系统。

系统包含两层机制：一层对音频进行转写并根据转写词触发动作（例如在 1 至 8 号工作区之间切换）；另一层基于 ChucK 平台的新框架 ChAI（ChucK AI，类似 Wekinator 的后继者），利用极小的模型直接处理 40、80 或 100 毫秒的超短音频切片，依据粗粒度的音频频段特征直接分类。

初始阶段该小型监督模型不可信，因此上层的大模型充当“教师模型”对其进行教学；同时，系统独立评估何时对小模型建立足够的信任并直接采纳其输出。

测试中使用了 Philip Glass 歌剧《沙滩上的爱因斯坦》中的插曲《Knee Play 1》。起初在听到数字时存在较长延迟；随着监督学习的进行，前几个数字的响应速度明显提升；最终对纯音频切片的响应延迟降低至约 45 毫秒。递归决策模型在此负责判定何时信任在数十毫秒级别原始音频上在线学习的小模型。

除音频外，Matt Mastracci 的 Hunch 项目展示了类似的端侧能力：利用嵌入的 Gemma 2 模型，通过 WebGPU 在本地运行 Pictionary 涂鸦游戏，对涂鸦的分类响应时间控制在 150 毫秒左右。这表明极小的嵌入、编码器和分类器模型正在复兴，通过合理的架构编排能发挥出巨大作用。

如何让身体摆脱设备的物理约束？不触碰甚至不直视电脑该如何工作？这正是我正在研发的系统——**Oso（oso.computer，即 Operating System 1）** 所探索的方向。

Earshot 证明了我们能在完整转写完成前，以超越文本转写的极快速度对语音做出响应。Oso 是一个基于递归决策模型构建的计算机使用智能体。尽管它支持常规智能体或 RLM 智能体，并可将重型编码任务分派给 Claude Code 或 Codex，但其架构是**决策优先（decision-first）** 的。

它具备递归自我改进能力，能够不断学习用户偏好，并像 Earshot 示例那样，一旦建立信任便将决策交由最快、最小的本地可用模型处理。仲裁者机制在此持续评估系统对轻量模型的信任程度。

向终端迁移（例如 Claude Code）并不代表终端本身是最优界面，而是反映了大家逐渐意识到图形界面、键鼠等传统交互方式的局限。我希望通过 Oso 重新审视人机交互的底层模式，欢迎大家尝试 RDM 代码库并关注项目的后续进展。非常感谢大家！

<details>
<summary>Original English</summary>
Um and so uh I'm going to show this example. I this is sort of a precursor to to OSO that I called Earshot. And I want to set this up and explain it because it's actually a little bit confusing video to watch. Um so you can think of this as this is a a recursive decision model. We have uh one layer of the system that is transcribing the audio and then choosing an action to take based on the transcribed word. And so the um here you're just going to see there's it's going to be cycling through my different workspaces one um through eight.

Um and then uh while that's happening there is a very small um uh based in Chuck there's a new thing called Chai that's like Chuck AI that's sort of the successor to the Wekinator that I mentioned before. Very very small model model operating on a very very small slice of audio, 40 milliseconds, 80 milliseconds, 100 milliseconds, right? And essentially trying to just map from some very crude binning of so the features are just like some bins of audio, frequency bins of audio, um which is the right one. Now this is supervised, right? So it it's it knows nothing in the beginning and we can't trust it in the beginning.

So there is one layer on which there's like a teacher model that's teaching this small real-time model, right? And then there's a second layer on which the system is independently figuring out when it actually trusts the small model enough to follow it. So we're going to watch it now and what you're going to see is in the beginning there's a big delay between the word and this comes from Philip Glass's um uh knee play one part of uh Einstein on the Beach. And um so you're going to see that [music] it's going look up here for the one two three four. So there's a big delay right now. [music]

Okay. Now it's it's supervised learning. So this [music] early numbers where it's hearing them more one two three four are going to learn a little faster. So now see how it's speeding [music] up a little bit for the early ones but there's a lag [music] by the end of this thing you're going to see that we got down to essentially 45 millisecond um [music] time. Here we go. One two three four one two three four five six. [music] So now for those we're really locked in, right?

Oh and there's a little blip but it's learning and it's going. [music] So this is recursive decision model deciding um when to trust this smaller supervised [music] model that is learning on the fly and operating on tens of milliseconds of information [music] on the pure audio, right? So here we go. By the end it's really going [music] to get

Anyways, to me that's super exciting. Um really really fun to like come back to these um these real-time on-the-fly machine learning algorithms, which is actually how I first learned um about machine learning and and I first learned programming through through music. So um

I also want to So that's the audio example. I also want to give a shout out to this project called Hunch. Uh Matt Mastracci, not sure exactly how to pronounce it. He sent something really crazy visually messing with just embedding Gemma 2 um and essentially having this thing play Pictionary. So he has this thing classifying your doodles um on your machine in Web GPU in like what look at these numbers like 150 milliseconds. So again, I want I I just want to give this a shout out as like I'm not the only one working in this space. Audio isn't the only um way in, but these these very very very small um embedding models, encoder models, classifier models, right? Like there's a whole resurgence of this and if you can uh structure them and architect them into a bigger space, you can do really really powerful things. Okay. So

with this this is kind of where I 'm going is like how can we decouple our bodies from our devices? What would it mean to work on a computer without touching it? What would it mean to work on a computer without being able to see it, right? And that's really what um I'm building up towards with this project that I have called Oso, oso.computer. It's short for Operating System 1. It's not quite ready um but that Earshot demo that I showed you where we're very quickly from a single uh word uh even before uh even at a speed that would be faster than we can actually transcribe what we're saying. We're able to react and respond um to to our voice. starting starting with voice as the first input.

Um and yeah, just like a little bit about also as like a teaser and I hope you'll join the waitlist and try it out when it's ready is like it is a computer-used agent, but it's built on recursive decision models. So, yes, there are uh regular agents and RLM agents um and you can actually um uh you can um sort of farm out jobs or um uh give them to like your normal coding agents like Claude Code and Codex. Um but it's it's decision first, right? And so you can also do things that are super fast uh without touching the keyboard, without touching the mouse.

Um it's recursively improving. It's constantly trying to learn um what the preferences are um of the user and it's also trying to essentially always like that um Earshot demo, the the Philip Glass demo, it's also trying to like farm out the decision to the the fastest, smallest um available model once it can build trust in that. So, that's this idea of the arbiter, right? It's like figuring out, okay, where have we seen this thing do well before and then now how much can I trust it over time? So, it's a it's an evolving system.

It is a tool to control your computer without touching it. Again, we're starting with voice. It's an experiment in what I consider radical human-computer interfacing. Let's like rethink everything. I think there's this really interesting thing about everyone going into the terminal um with Claude Code and I don't think it's actually anything um special about the terminal. That's why um that happened. The terminal is clearly not like the best interface for it. I think a big part of what happened over the last couple years of us all going into the terminal was really about uh just realizing the limitations of these default interfaces that we've been given, these application interfaces, these default visual um interfaces, touch screen interfaces, mice, keyboards, all this stuff. Um and then yeah, lastly it's just like um I'm having so much fun uh coming back to uh what I consider my roots in in real-time machine learning and and it's really fun to be building this this computer usage and OSO. So anyways, I hope you'll check it out. I'm really grateful for your attention. This is a long talk. I'm using the opportunity to do the virtual talk to to really go deep um and yeah, I hope you'll check out the recursive decision model repositories and I hope you'll sign up uh for this wait list when OSO is ready at oso.computer.

Thank you so much.
</details>