---
author: AI Engineer
date: '2026-07-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xyL2Ltkh-SA
speaker: AI Engineer
tags:
  - agent-evaluation
  - llm-judge
  - prompt-engineering
  - quality-control
title: YouTube Ads 团队分享：如何通过评估系统（Evals）与提示词塑造 Agent 的行为
summary: 本文是 YouTube Ads 团队专家关于构建生产级 Agent 评估系统（Evals）的深度分享。文章详细阐述了如何从优化基础工具集、初期的直觉评估（Vibing）阶段，逐步过渡到人类评估与 LLM 裁判的规模化评估，并重点探讨了通过 Trace 分析排查非确定性问题以及 launch 指标爬坡的实践路径。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - YouTube
products_models: []
media_books: []
status: evergreen
---
### 评估对构建 Agent 的重要性

**Preetika**: 大家好。听起来大家刚吃完午饭回来。希望大家都已经充满了电，一点都不困。在午饭后立刻做演讲总是很有趣，因为你永远不知道听众的状态。这是一群背景各异的听众，但我们非常高兴能来到这里，也很高兴见到大家。

我们的演讲主题是关于**评估系统（Evals）**的。当然，我们现在身处评估专题会场。我们将向大家介绍我们在构建评估系统时，尤其是在为 **YouTube 广告（YouTube Ads）**团队构建时，有哪些行之有效的方法。我们在 YouTube 广告团队工作，主要负责为 YouTube 广告构建图像和视频模型。

构建一个 **Agent（智能体）**是很困难的。我想在座的各位中，无论是作为个人副业项目还是作为生产系统的一部分，大概都构建过 Agent。这是一件非常艰巨的任务。它非常繁琐，需要耗费大量的时间。而让它变得可靠则更加困难。让它在生产环境中切实执行你期望它做的事情，理解它可以操作的各种不同元素，以及在你向最终用户推出时它会如何反应——这始终是一件非常棘手的事情。这就是为什么评估系统是管理这一过程的非常便利的工具。

<details>
<summary>Original English</summary>

**Preetika**: Hi everyone. Uh sounds like everybody came back from lunch. So hope everybody is recharged and not sleepy at all. It's always interesting to do a talk right after lunch because you never know. It's a mixed crowd. Uh but we're very happy to be here. Happy to see you all. Our talk is going to be about eval. Of course, we're in the eval track. We're going to talk you through what are some things that worked for us while we were building eval uh especially for YouTube ads. We work on the YouTube ads team as part of the we do image and video models for YouTube ads. So, building an agent is hard. I think anybody who's here in the audience probably has built an agent as a side project or as part of production systems. It's a very hard thing to do. It's laborious. It takes a lot of time. Uh making it reliable is harder. So having it do things that you actually want it to do in production, understanding the different kind of things that it can play with, how it's going to react when you launch it to your end users, that's always a very hard thing to do, which is why eval are pretty handy way to manage that.

</details>

### 优化基础工具与自我修正机制

**Daniel**: 是的，接下来，基本上第一步就是你必须打好 Agent 的基础。所以在构建你的 Agent 时，你会希望拥有一套聚焦且对 **LLM（大语言模型）**友好的工具集，来为你的 Agent 提供一个非常好的根基。所以，我会说，在直接跳到更大规模的 Agent 评估之前，首先优化这些工具并确保它们处于最佳状态是非常重要的。

一旦你的工具得到了优化，你还可以采取其他步骤，比如构建一个独立的**克里特/批判 Agent（Critique Agent）**并引入**修复循环（Remediation Loop）**。这可以弥补更多的差距，提供一种自我纠正机制，并填补基础工具集可能存在的局限性。

一旦你的基础结构定义好了，你就可以开始构建评估系统。拥有一个强大的评估系统非常重要，因为这为你提供了一种证明你所做更改价值的方法，并且能让你对所做的任何更改进行**消融实验（Ablation Experiments）**。因此，我会说，这是攀登质量阶梯的必不可少的工具。但同样，最开始拥有一个好的基础是非常重要的。

<details>
<summary>Original English</summary>

**Daniel**: Uh yeah, and then um basically uh the first step when you're doing this is of course you need to have your agent foundation. So um when you're building uh your agent, you know, you will want to have a focused and strong set of LLM friendly tools to give your agent a very good foundation. Um so yeah, I would say it's important to first optimize these tools and make sure they're the best they can be before just jumping onto um larger agent evals. Um so once your tools are optimized uh you can also take some other steps like making an independent critique agent right with a remediation loop and this can fill more gaps as far as um having a self-correction mechanism and filling those gaps where uh maybe your base tool set has limitations. Uh and then once your base structure is defined uh you can have you can then go to um having an eval and having a strong eval is very important as this gives you um like a way of proving the value of changes you make as well as running ablation experiments on any changes you make. So I would say this is a very essential tool for climbing the quality ladder. Uh but again it's very important to have that uh good foundation to begin with.

</details>

### 从“非标体验”到规模化评估

**Daniel**: 那么，Agent 的可靠性基本上是 Agent 自身能力、**护栏（Guardrails）**和评估系统三者的函数。

要理解你的 Agent 在真实世界中的表现——基本上，如大家所知，生成式 AI 的输出并不完全是确定性的。它经常在某些领域失败，或者一次成功一次失败，所以我们无法真正保证它在野外环境下的表现。对于某些使用场景，这极其重要，我们需要一种方法来进行规模化测量，确保即使在模型具有非确定性的情况下，我们仍能获得我们想要的输出。

因此，我们需要定义什么才是好的表现，并通过定义好的表现来规范它在真实世界中的行为。这基本上就是设定我们的目标输出。所以，要构建能够真正规模化的评估系统，它们必须是严格且可测量的。

这里有一个有趣且可能有些反直觉的点：在早期阶段，**非标的手感体验（Vibing）**其实是对你有好处的。我这里所说的 Vibing，基本上是指在刚开始时做一些不那么具有扩展性的事情。当你最开始起步时，你可能会想要直接着手构建一个超级全面的评估系统，但我们发现，其实先采用基于直觉的方法效果更好。你可以先观察其能力并查看输出。在这个阶段，很容易看出问题到底出在哪里。

因此，尽管这种方法不可扩展，但它仍然能给你一个非常好的概念：当你做出改变时会发生什么，同时它也允许你更快速地进行迭代。在这一阶段，微调提示词（Prompt Tweaks）也可以带来巨大的性能提升，你可以对架构进行彻底的改变，而你的评估系统在这时不会对你形成阻碍。所以，这就像一家处于初创阶段的公司一样，首先快速做出更彻底的改变。

通过这种方式，我认为你可以非常熟悉你所构建的内容、它的失败模式是什么，并且它能给你带来更深层次的理解，使你能够有针对性地进行指标攀爬（Hill Climb）。当你在构建更全面的评估系统时，这些基本上都会成为非常有用的经验。

另外这里有一张图表，展示了如果你过早地跳转到规模化评估（如引入规模化评估员/Scaled Raiders），可能会导致你在迭代和校准评估系统时经历巨大的起伏，因为你还在努力应对模型的剧烈变化。

所以另一件事是，你应该尽早开始，且从小处着手。

<details>
<summary>Original English</summary>

**Daniel**: Um so yeah the the reliability of your agent is basically a function of the capabilities of the agent uh the guard rails and the evals. Um so understanding uh what your agents do in the real world. uh basically uh generative AI outputs as I'm sure you're all familiar are not exactly deterministic right so it can often fail in certain areas or uh one time it can succeed one time it can fail so we can't really guarantee how it will behave in the wild and for some use cases this is extremely important right and we need a way to uh measure at scale and make sure that it is uh getting the output we want uh despite the non-determinism of these models. So we need to define um what's good here and eval behave in the real world by defining what good looks like. Uh it's basically just setting this is uh you know our target output. Uh to build evals that actually scale they really need to be strict and measurable. And uh so an interesting uh thing here that I think might be somewhat counterintuitive is that early on vibing can actually be kind of good for you. Uh and what I mean here by vibing is basically um doing things that are not exactly scalable to begin with. Um so when you're first uh starting out it may be that uh you you know you could uh take a track of basically just going ahead and making the super comprehensive eval right um but we found it actually works better to first do intuition based approach where you kind of um first see the capabilities and look at the outputs and at this stage it's pretty easy to tell what the issues actually are right uh so even though this is non-scalable it will still give you like a way good idea of when you change this what happens um and like uh it allows you to more quickly iterate as well. So at this stage prompt tweaks can also have like large performance gains you can make a radical change to the architecture um and your eval is not kind of like hindering you in this way. So it's like a very good way kind of you know like an early stage company of just like first you know doing something making more radical changes quickly. Um so yeah this way I think you can also get very familiar with what you're building what the failure patterns are and uh it gives you more of a a sense of depth and understanding it uh which allows you to hill climb in a targeted way and these will basically be very useful learnings when you're actually like building the more comprehensive EVO. Uh yeah, and then there's a chart here showing kind of uh you know if if you uh jump to scale to um these scaled raiders like too early uh it can cause you to kind of have like very big ups and downs as you might be iterating and calibrating the eval as you are struggling with uh changing the model radically. Um so another thing here is um you can you should start early and start small.

</details>

### 协同人类评估员的最佳实践

**Preetika**: 正如我之前所说，你在第一天并不需要一个庞大的**黄金标准数据集（Golden Set）**。你只需要从几个核心任务开始。你可以梳理你的 Agent，定义你想要针对的首要任务是什么，对吧？然后就从这些高层面的任务开始，随着工作的深入，再慢慢过渡到更详细的表示。

在这里，测试负面情况也同样重要。检查模型是否没有做某些糟糕的事情，与检查它是否完成了任务一样关键。

这里有一个有趣的视觉图表：编写评估系统可能只是一个很小的点，而人类就评估标准（Rubric）应该是什么而展开的争论，则是一个非常庞大的任务。

好的。我们已经确立了我们想要从小处着手，并且在开始时编写评估，试图了解我们的模型在哪些方面表现良好，Agent 在哪些方面出现了下滑，找出所有的模式。最终，你会进入一个需要引入更多团队的阶段。如果最开始只是由产品经理（PM）和交互设计（UX）组成的核心团队在工作，那么接下来你会引入更多的团队。你会拥有一个更大的黄金标准数据集，一个你想要测试的更大的数据集。所以你会开始考虑**规模化评估员（Scale Raiders）**、**LLM 评估员（LLM Raiders）**等等。接下来我们将详细介绍这看起来是怎样的。

关于与规模化评估员合作以及对我们有效的一些经验：

第一，是为他们提供一个关于他们实际在评估什么的清晰标准，并附带非常明确的示例。我们遇到过很多情况，尤其是在你构建东西的早期阶段，当然，会有很多我们没有测试过的边缘情况和困难情况，评估员可能会遇到。所以他们会跑来问你：“哦，在这种情况下我该怎么办？”然后有时我们团队内部甚至会就“这应该算通过还是算失败”产生分歧。所以，我认为尽早在这方面达成一致非常重要，你能够给评估员提供的清晰度和示例越多，帮助就越大。因此，在你的团队内部，对于什么算作好的使用场景、什么算作评估通过，应该有很强的共识。

第二，我们注意到对我们帮助很大的一点是，从评估员那里获取**解释说明（Explanations）**。当你的团队或其他规模化评估成员对评估进行“通过”或“失败”的评级时，这并不能真正告诉你 Agent 应该在什么地方进行改进，或者做出这一结论背后的思考是什么。所以，获取他们为什么要做出某种评级的解释是非常有帮助的。无论是进行单侧评估，还是进行双侧对比评估（Side-by-side Eval，即同时测试两个模型），获取关于为什么一个失败或一个成功的解释都是极有帮助的。

其他需要记住的是，在我们的案例中，输出是多样化的（Multi-output）。因此，我们在构建广告时会询问规模化评估员：“这些广告准确吗？我们做对了吗？它符合品牌安全（Brand Safe）吗？这是我们期望它呈现的样子吗？”诸如此类的问题。所以我们拥有一个类似于多轮的评估系统。如果你在构建这类案例，它可能会变得有些棘手，因为这不完全是简单的通过或失败。你的评估员可能会说：“哦，好吧，它在品牌安全方面做得非常好，但在准确性之类的地方做得不够好。”所以，解释说明能切实帮助你找到问题的根源，弄清楚 Agent 到底在哪些地方遗漏了信息。然后你也可以利用这些输入来更好地训练你的 Agent。

<details>
<summary>Original English</summary>

**Preetika**: So um you don't as I said before you don't need to have like a massive golden set on day one. Um you can just kind of start with a few core tasks. So you can look through your agent and define what are the primary things that you want to target, right? Um and just uh basically start with those like highle things and can slowly come to a more detailed representation as you move on. Um, and so here it's important to also test the negatives. Checking if the model like didn't do something as bad, uh, something bad is just as critical as checking if it did the task. Um, so yeah, and uh, yeah, there's a funny visual here about writing the evals can be a very small point and humans arguing over what the rubric should be is, uh, is kind of like a very large task here. Uh cool. So we've established that we want to start small and we want to wipe code at the start. Not wipe code but like why eval at the start and try to get a sense of like what our models doing good where the agents are falling. Find out all the patterns. Eventually you'll get at a stage where you will try to involve more teams. So if it's just a core team of like PM and GX working at the start then you'll bring in more team. You'll have a bigger golden set a bigger data set that you want to test out. So you'll think about scale raiders, LLM raiders, all of that. So we'll get a little bit more into what that looks like. So just a couple of things on like working with scale raiders and things that worked for us. Uh one was that providing them with a clear rubric of what they were actually rating with very clear examples. So we had a lot of situations, especially early on when you're building things. of course like there are so many edge cases and difficult cases that we've not tested out that a raider might encounter. So they're coming back to you saying oh what what what should I do in this case and then sometimes we as a team are like disagreeing on like should this be a pass should be should this be a fail things like that. So I think that's very important to do early on as much as clarity and examples you can give the raers that would be super helpful. So yeah to that point like human human agreement should be strong within your team of what you consider a good use case and a good past case for an eval. Uh the second things that we noticed that helped us a lot was getting explanations from raider. So when you do have your teams or other scale members rate eval if it's a pass or a fail, that doesn't really tell you much about where should the agent improve, what was the thinking that went behind coming to that conclusion. So it's helpful to get explanations of why they're rating something a certain way. And this is true for like if you do single side evals or sideby-side eval like when you're testing two models at the same time having explanations of why one thing failed or one thing worked can be super helpful. Uh other things to keep in mind is that you could also do like in our case it was multi output. So we were asking scale raiders um when we were building ads like are these ads accurate like did we do the right things for it? Is it brand safe? Is it like something that we expected it to be? Things of that nature. So we had like almost like a multi-turn eval system. If you're building those kind of cases, it can get a little tricky because it's not exactly a pass failure. Your raiders could be like, "Oh, well, it does very well in well in brand safety, but it does not do really good in like accuracy or things of that nature." So explanations really help you like get to the bottom of like where is it that the agent's actually like missing things. And then you can also use that input to train your agent better.

</details>

### 引入 LLM 裁判与 Trace 分析

**Preetika**: 好的，现在我们多谈了一些关于引入跨功能团队和人类评估员的话题，但如果你使用的是 **LLM 裁判（LLM Judges）**、自动评估器（Auto Raiders）呢？我们也走过了这条路。为了给自己建立一个更全面的结构，我们尝试做了一些事情：

第一，我们监控了分歧率（Disagreement Rates），在某些情况下，团队也监控了一致率。基本上，你可以建立一个采样流水线，用来监控人类评估员或专家如何对评估进行评级，对比 LLM 如何对其进行评级。你可以了解其趋势，看看一致率是否在期望的范围内。

第二，我们超越了简单的“通过”和“失败”。我们还会查看 **Agent 运行轨迹（Agent Traces）**，稍后我们会详细讨论这一点。但在进行“通过/失败”评估并试图理解事情是如何被评级时，我们做了一些抽样检查，以理解这些逻辑背后的推理，从而能切实看清到底发生了什么。它是如何得出最终通过或不通过的结论的？

另外就是再次强化 Daniel 之前提到的高质量**真值（Ground Truth）**的观点。我们希望提供一个非常庞大的黄金标准数据集。它能覆盖广泛的使用场景，并且在你的团队内部具有很高的人类一致性。

下面是我们在 Agent 中看到的一个快速示例。我来带大家看一下。它基本上是说，如果你想知道它在做什么，就去看它的思考过程（Thinking）。

我们曾给 Agent 提供了其中一个提示词，内容是：出于法律原因，免责声明（Disclaimers）绝对不能被移除。我们在提示词中向 Agent 提及了多次。我们在这方面对它进行了训练，一切进展顺利。但后来我们开始看到一些边缘情况，Agent 在看到提示词以及广告中存在免责声明时，仍然会将其移除。如果仅仅做分类统计（例如通过率是百分之多少），我们是无法发现这个问题的。所以我们必须切实去查看 Trace（运行轨迹）以了解发生了什么。

在这个例子中，你可以在初始 Trace 中看到，它实际上检测到了它所搜索的内容中存在免责声明，并且它说：“好的，我找到了一个免责声明，现在我要继续去移除它。”这完全不是我们要求它做的事情。

这是我创建的一个样本图像，我把它输入给 Agent。上面写着：“美利坚，我们可以做得更好。这是一则公共公园广告。”如果你看右下角，它写着：“由‘保持公园清洁’的公园社区资助。”我们把它发送给 Agent，结果它直接把它移除了，尽管我们明确告诉它不要这样做。这类事情时有发生。所以，检查推理逻辑以及它是如何得出你所关注的结论的，真的非常重要。

另外，就像所有的机器学习（ML）系统一样，有些规律仍然适用，这是我最喜欢的部分。Agent 不会泛化得特别好，这取决于你训练的数据集类型。准备某种数据集来测试边缘情况和更广泛的能力通常是一个好主意。拥有一个测试集是很好的实践。如果你们中有人在传统的 ML 系统中工作过，就会知道拥有测试验证集是非常有益的。相同的概念在这里同样适用。如果你有一个测试集，请谨慎使用它，并用生产数据进行更新。接下来有请 Daniel。

<details>
<summary>Original English</summary>

**Preetika**: Okay, so now we talked a little bit more about involving cross functional teams and human agents, but what about if you're using LLM raiders, auto raiders, LMS judges. So we ended up going down that path. Also few things that we tried to do to kind of set this set a more uh comprehensive structure for ourselves is one we we monitored disagreements or in some cases teams monitored agreements. So basically if you can have a sample pipeline of sorts that is monitoring how a human raider or some expert would rate an eval versus how an LLM would rate it. You can get a sense of like how it's trending and if the agreement rates are in the ballpark that you would expect it to be. Uh the second thing was we went a little bit beyond pass and fail. So we also looked at agent traces which we'll get to later. But when we were doing pass fail eval and trying to understand how things were getting rated, we did a couple of spot checks to understand the reasoning behind those logic so we could really see what was going on. How did it come to the conclusion that something was a final pass or no? Uh and again like just reinforcing the high quality ground truth point that Daniel made earlier. So we want to give a golden set that's like super expansive. It covers a broad range of use cases and it also has very high human human agreement within your team. Okay. So this is a quick example of what we had seen in the agent. I'll walk you folks through it. So uh it basically says if you if you want to know what it's doing look at it at its thinking. Uh we had given the agent one of the prompts and it was that for legal reasons disclaimers can never be removed. And we had mentioned that to the agent a couple of times in the prompt. We had like trained it on that and it was all going fine. But then we started seeing that there were edge cases in which the agent was seeing the prompt and it was seeing that there's a disclaimer present in the ad and then still removing it. And we could not find that if we were just doing a categorical like the this x% pass rate or not. So we really had to look at the traces to see what was going on. And in this example, you can see in the initial trace, it actually detects that there is a disclaimer in what it's searching for and it says, okay, I found a disclaimer and now I'm going ahead and remove it, which was not what we asked it to do. Uh this is a sample image that I created that I ran through the agent. It says, "America, we can do better. It's a public parks ad." And if you'll see at the bottom right, it says paid by the community of parks of keep parks clean. and we sent it to the agent and it just removed it when we told the explicitly not to. So those kind of things will happen. So it's really important to like check the reasoning and how it's like getting to the things that you care about. Uh cool one other thing. So like all ML systems some things still are applicable which is my favorite part. So agents will not generalize very well depending on the kind of like data sets that you've trained on. It's usually a good idea to have some sort of data set to test for like edge cases like broader capabilities. Uh also a very good practice to have a test set of sorts. If some of you have worked in like traditional ML systems, it was always good to have test validation sets of that sort. Same concept applies here. Uh if you have a test set, use it sparingly and also refresh it with prod data. Daniel.

</details>

### 指标爬坡与 launch 评估

**Daniel**: 好的。这张幻灯片基本上是关于**指标爬坡（Hill Climbing）**的，这可能会非常有收获。

这张图表基本上展示了你可以做什么。在进行人类评估之后，如果它达到了标准，显然你可以在这里结束；但它很可能达不到标准。当它没有达到标准时，你首先可以审查你的评估集，并找出诸如**精确率（Precision）**和**召回率（Recall）**之类的指标。然后你可以进行迭代，基本上可以对评估系统做出更改，或者调整你的评级指南等；或者直接调整模型本身，或者调整 Agent，调整其工具集。

通过所有这些工作，你既可以迭代你的评估系统，也可以同时迭代 Agent。一旦你定义了一个非常好的评估系统，这个循环在迭代 Agent 以及进行我之前提到的质量指标爬坡、进行消融实验等方面会非常有效。

接着，就发布就绪度（Launch Readiness）而言，你基本上需要理解**回归（Regressions）**。确定模型性能在何处以及为何下降，以便你能够区分可接受的折衷（Trade-offs）与关键性的失败。

这基本上就是说，通过这些评估系统来理解你所遇到的确切问题，并找出折衷方案，这是非常重要的。

然后，这也是一个非常关键的要点：你应该关注**模式（Patterns）**，而不是孤立的单次运行（Isolated Runs）。一个很诱人的陷阱是过度关注模型的极小示例。你可能会对 Agent 进行一次运行，然后发现它在这个案例上失败了，你可能会想：“好吧，我应该根据这个评估和 Agent 的 Trace 来更新提示词，对吧？”但如果你这样做，就会陷入陷阱，因为正如我之前所说，这些是非确定性系统。

更重要的是你实际上要依赖模式。在你的黄金标准数据集中，重要的是拥有多个可以覆盖这些你希望看到的模式的示例。你基本上需要看全局：它在这一模式上的失败频率是多少，而不是看那个具体的、孤立的个别示例。

此外，投资于在线评估系统（Online Evals）并确保你的数据与真实世界的情况相匹配，也是非常重要的。

<details>
<summary>Original English</summary>

**Daniel**: Yes. Um so then um yeah this slide is basically uh talking about hill climbing and how it can be quite rewarding. So um yeah you might find that uh after human eval right uh you can uh this this diagram basically shows like the uh kind of stack of what you can do. So after um human eval if it meets the bar obviously you can finish there but um it probably won't and then uh when it doesn't meet the bar uh you can first review your eval set uh and find numbers like precision and recall um and then you can um iterate and basically uh you know make changes to the eval or adjust your uh rating guide things like this uh or just adjusting the model itself or the agent uh adjusting its tooling. Um, and then through all of these things, you can both iterate on your eval as along with um, iterating on the agent. And this loop, uh, once you have a very good eval defined, it works quite well for iterating on your agent um, and doing quality hill climbing as I mentioned before, doing ablations and whatnot. And then um so as far as uh launch readiness you uh basically need to understand um regressions. So identify where and why the model performance is uh degrading so that you can distinguish between acceptable trade-offs and critical failures. Um so yeah this is basically just saying like it's very important to understand from these evals right what is the exact issue that you're having and figure out um the trade-offs here and then um you should also this is a very important point so you should focus on patterns rather than isolated runs so a tempting thing is to hyperfixate on very small examples from the model right so you might have uh one run that you do with your agent and then you find uh it fails on this case and you might think to yourself, okay, well, I should update the prompt based on my eval and uh the the trace of the agent, right? But um if you do this, this is kind of a trap because as I said before, these are non-deterministic systems. So what's more important is that you actually rely on patterns. So in your golden set, it's important to have multiple examples that can cover these kind of uh patterns that you might want to see. And you basically want to look at the entire picture of how often is it failing on that pattern, not that specific individual example. Um, and yeah, it's important here also to invest in online evals uh and and making sure that your data is matching the real world representation.

</details>

### 评估系统的持续演进

**Preetika**: 好的，太棒了。我们谈了许多在构建评估系统时对我们有效的方法。当然，根据你的具体应用，实际效果可能会有所不同，情况会有所差异。

我们想在这里重温的一些要点是，我们认为一个好的评估系统通常应该能够代表你希望你的产品所擅长的领域。而这取决于你在构建 MVP（最小可行产品）案例还是在进行生产环境推广时 Agent 所处的状态，这会有所不同。

因此，评估系统会有所不同，但它仍然非常需要围绕“你希望你的产品擅长什么”并针对这一点进行优化。

当然，保持它的演进是非常重要的。这就是为什么我们谈到要拥有在线评估系统、用生产数据更新测试集、拥有采样流水线等各种手段。

高度策化的黄金标准数据集也会随着你的使用场景的演进而演进。因此，培训团队（无论是规模化评估员还是跨功能团队）了解如何评级、你的期望是什么，也是非常重要的。我认为现在这已经变得更加主流了，所以希望它的争议性比六个月前要小一些，当时我们的团队还在摸索：好的，我们该如何做这个，预期是什么？所以，我认为在这些培训上进行投入是很有帮助的。

然后是提供带有清晰示例的评估模板和评级标准，这样你就不会遇到规模化评估员跑来跟你说“我不确定该如何评级这个”的情况，或者有许多内容被标记为“未知”或“我不知道”之类的情况。

此外，还要选择正确的发布指标。我们向大家展示了一些发布就绪度的幻灯片。这是进行发布就绪度评估的一个非常高层面的概括。你会对模型进行多次迭代，进行 A/B 对比或消融实验，并试图看清：回归发生在什么地方？什么是可接受的回归，什么不是？诸如此类。当你构建这些系统时，及早明确你的准入规则（Gatekeeping Rule）或发布标准（Launch Criteria）是非常重要的。是否有你正在关注的特定精确率或召回率数值？是否还有你关注的其他指标？如果你在进行模型评估，那么该指标看起来可能与通常的精确率和召回率有所不同。所以记住这些也是很重要的。

以上就是我们关于构建生产级评估系统的所有建议。谢谢大家。

（掌声）

我们很准时。

<details>
<summary>Original English</summary>

**Preetika**: Okay, awesome. So, we talked a bunch about like what worked for us while we were building evals. Of course, your mileage may vary depending on your application. Things can uh things can differ. Uh some of the things that we wanted to recap here was uh it's like what what we think makes a good eval system generally is like it should be representative of what you want your product to be great at. And that will differ depending on the state at which your agent is when you're building MVP cases, it would look differently versus when you're doing production rollout. So that would differ. Uh but it still needs to be very much uh centered around what do you want your product to be good at and optimizing for that. Uh important to of course keep it evolving. That's why we talked about having your online eval having test sets that are refreshed with production data, having sampling pipelines, all sorts of things. Uh highly curated golden sets which will also evolve as your use cases evolve. So training teams whether it's scale raers or your cross functional teams on how to rate things how what are you expecting out of them that's also very important that's uh I think now it's getting more mainstream so hopefully it's less less controversial but like six months ago our teams were like still figuring out okay how do we like do this what's expected out of it so I think investing in those trainings can be helpful uh and then raider templates and rubrics with clear set of examples so you don't have scale raers coming back to you saying I'm not sure how to rate this. Um lots of like things getting marked as like unknowns or I don't know things like that. Also choosing the right launch metrics. So some of the launch metrics launch slides that we showed you. This is a very high level of generally how you would do a launch readiness. You would like check it. You'll do bunch of iterations on the model. You'll do an AB diff or ablation and you'll try to see okay where is the regression happening? What's an acceptable regression versus not? Things like that. As you're doing these systems, it's important to like uh get some clarity early on on what is your gatekeeping rule like what's your launch criteria. Is there a certain precision recall number that you're looking at? Is there some other metric that you look at? If you're doing a model eval, then probably that metric looks different than just the usual precision recall. So those things can also be important to keep in mind. Uh yeah, those are all the tips that we have to build production grade eval. Thank you. [applause] We're on time.

</details>

### 现场问答：如何校准 LLM 裁判

**Host**: 太棒了。非常感谢。我们有时间提问吗？工作人员，我们有时间提问吗？就一个问题。我们有时间提问吗？就一个。好的。这位先生先举手的。请讲。

**Audience**: 你们所有的评估评级都是由人类完成的吗？还是你们也使用 LLM 作为裁判？如果是的话，你们校准裁判以提供良好评估的校准流程是怎样的？

**Preetika**: 是的，我认为这是一个很好的问题。我不会说全部都是。我认为这取决于非常具体的使用场景，取决于你试图构建什么样的系统。当然，我们有海量的使用场景。所以，我不能详细说明基准测试和所有这些系统的具体细节，但我们谈到的关于分歧率和监控采样流水线等方法，通常都是适用的。是的。

**Daniel**: 乐意在线下交流更多细节。是的。

**Host**: 太棒了。非常好。非常感谢。Preetika 和 Daniel，请大家给他们热烈的掌声。你们也可以在后台向他们提问。谢谢。

（音乐）

<details>
<summary>Original English</summary>

**Host**: Awesome. Thank you very much. Uh do we have time for questions? Staff one. Do we have time for questions? Just one. All right. You went up first, sir. Go ahead.

**Audience**: Are uh all your eval judgments being performed by humans or are you also using LLM as a judge? Um, and if so, what's your calibration process look like for calibrating that judge to provide good evaluations?

**Preetika**: Yeah, I think that's a good question. I think I wouldn't say all. I think it depends on very use cases like depending on like what kind of systems you're trying to build. We have of course like a plethora of use cases. So, I co can't go into details about what the benchmarking and all of that system looks like, but some of the things that we talked about in terms of disagreement rates and ma monitoring like sampling pipelines, those things hold true generally. Yeah,

**Daniel**: happy to chat more offline. Yeah.

**Host**: Awesome. Great. Thank you very much. Daniel and Pratika, please give them a round of applause. You can always ask them questions in the back. Thank you. [music]

</details>