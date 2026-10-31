---
author: Latent Space
date: '2026-02-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0HaUD_olwQU
speaker: Latent Space
tags:
  - coding-benchmarks
  - ai-evaluation
  - model-contamination
  - research-automation
title: SWE-Bench Verified 的终结与演变——迈向更困难的编码评估基准
summary: OpenAI Frontier Evals团队讨论了为什么SWE-Bench Verified这一关键编码基准已经饱和且高度被污染，不再能有效测量编码进展。他们详细阐述了原始基准的构建工作（包括约100名软件工程师的人工审核），发现的具体问题（如过度狭隘的测试、未指定的实现细节），以及为何转向SWE-Bench Pro这一更难、更多样化的基准的必要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Scale AI
  - Princeton
products_models:
  - GPT-5.2
  - Claude 3.5
  - Gemini Flash
media_books: []
status: evergreen
---
### 介绍与背景

**主持人**: 好的，欢迎来到OPI工作室。我们今天邀请了来自OpenAI Frontier Evals团队的Mia和Olivia。你们可以介绍一下自己在OpenAI的职位和工作内容吗？

<details>
<summary>Original English</summary>

**Host**: Okay, hi. We're here in the OPI studio with Mia and Olivia from the Frontier Evals team. Maybe you want to introduce your name, what you do at OpenAI, and we can get started.

</details>

**Olivia**: 我是Olivia，我在Frontier Evals团队工作。

<details>
<summary>Original English</summary>

**Olivia**: Hi, I'm Olivia. I'm on the Frontier Evals team.

</details>

**Mia**: 我叫Mia，是OpenAI的研究副总裁。我的团队包括Codex团队、人工数据团队和对齐团队，我们与Olivia的团队在Frontier Evals上有密切合作。

<details>
<summary>Original English</summary>

**Mia**: Hi, I'm Mia. I'm a VP of Research at OpenAI. My team are the Codex team, the human data team, and the alignment team, and we work a lot with Olivia's team on Frontier Evals.

</details>

**主持人**: 很好。据我了解，你们都是参与原始SWE-Bench Verified工作的团队成员。

<details>
<summary>Original English</summary>

**Host**: Yeah, very exciting. And as by my understanding, you were part of the original team that worked on SWE-Bench Verified as well.

</details>

**Mia**: 是的。Olivia的Frontier Evals团队、我们的人工数据团队和对齐团队共同创建了SWE-Bench Verified。你们见证了编码基准的演变。我认为大约在2024年中期到晚期时，我们首次发布了SWE-Bench Verified，从那时起，情况已经发生了很大变化。那么，你们最近发表的博文主要讲了什么？核心论点是什么？

<details>
<summary>Original English</summary>

**Mia**: Yeah. Olivia's team, the Frontier Evals team, and the human data team collaborated on creating SWE-Bench Verified. So you've seen the evolution of coding benchmarks over time, and I think it was round about mid to late 2024 when we first released SWE-Bench Verified. Things have evolved a lot since then. What's the blog post that you've worked on that we're releasing today? What is the main thesis that you're pushing out?

</details>

### SWE-Bench Verified 的饱和与污染问题

**Mia**: 核心论点是**SWE-Bench Verified**一直是该领域关注的北极星级编码基准，用来测量编码进度。但最近我们观察到进度似乎停滞了。我们意识到这是因为该评估已经有效地**饱和**，并且**高度被污染**。在这一点上，我们认为它不再能很好地测量编码性能的改进，我们认为该领域应该转向其他基准。

<details>
<summary>Original English</summary>

**Mia**: So the main thesis is that SWE-Bench Verified has been one of the north star coding benchmarks that the field has looked at to measure coding progress. But recently we've seen that progress has kind of stalled, and we realize that this is because the eval is effectively saturated and also highly contaminated. So at this point, we think that it's not really measuring coding performance improvements well anymore, and we think that the field should move away from this towards other benchmarks.

</details>

**主持人**: 比如**SWE-Bench Pro**？

<details>
<summary>Original English</summary>

**Host**: Like SWE-Bench Pro?

</details>

**Mia**: 是的，像SWE-Bench Pro。

<details>
<summary>Original English</summary>

**Mia**: Yeah, like SWE-Bench Pro.

</details>

**主持人**: 太棒了。我经常开玩笑说，有个群组聊天包含所有的AI实验室，每个人都轮流在某个基准上增加0.1%，然后就像"好吧，你有最好的编码模型，我猜，因为你高了0.1%"，但这一点都不令人信服。这说明了问题的严重性。

<details>
<summary>Original English</summary>

**Host**: Amazing, yeah. I always have a joke like there's a group chat with all the labs and everyone just takes turns to increment like 0.1% on benchmarks, and then it's like okay well you have the best coding model I guess because you're 0.1% higher, but it's not super convincing at this point at all.

</details>

### SWE-Bench Verified 的原始设计工作

**主持人**: 那么，让我们回到最初。你们为SWE-Bench Verified所做的原始工作是什么？我认为这项工作相当重大——OpenAI投入了巨大的资源，但人们仍然没有充分认识到这一点。那么SWE-Bench Verified应该让人们了解什么？

<details>
<summary>Original English</summary>

**Host**: So cool. I think the, let's sort of reset on like what was the original work that you guys did for SWE-Bench Verified, which I think was pretty substantial. Like it was a very significant investment from OpenAI, which like people still don't appreciate. And then what were the satisfactions that we found over time? So like what was SWE-Bench Verified? What should people know about it?

</details>

**Mia**: **SWE-Bench Verified**是对来自**普林斯顿大学**一个实验室的原始SWE-Bench学术基准的清理和改进。本质上，该代理被给予一个代码库和一个来自真实世界的任务——从**GitHub**问题中获取——并被要求解决该任务。它根据某些测试是否通过来评分。这很快成为一个流行的基准，因为当时该领域没有好的真实世界编码基准。

但是，当**OpenAI**作为我们**准备框架**的一部分审视这个基准时，人们开始意识到，代理失败的一些情况是由于问题设置不当，而不仅仅是模型不够聪明。所以我们进行了一次相当广泛的人工数据活动，雇佣了近100名真实的软件工程师来检查这些问题，确定任务是否定义明确、测试是否公平，最后创建了一个包含约500个任务的精心策划集合，我们认为质量好得多。

<details>
<summary>Original English</summary>

**Mia**: SWE-Bench Verified was a kind of a cleanup of the original SWE-Bench academic benchmark from a lab at Princeton called SWE-Bench. The agent is basically given a codebase and a task that was sourced from a real-world repository and GitHub issue, and was asked to solve the task and is graded on whether some tests pass. And at the time, this quickly became a popular benchmark because at the time, the field didn't really have good real-world coding benchmarks. But then when OpenAI took a look at the benchmark as part of one of the evals we wanted to track in our preparedness framework, folks started realizing that some of the cases where agents were failing were due to bad problem setups rather than just to models being dumb. So we did a pretty extensive human data campaign, hiring like almost a hundred real-world software engineers to go through the problems and figure out like are the tasks well specified? Are the tests actually fair? And kind of created a curated set of like 500 tasks that we thought were much better.

</details>

**主持人**: 很难言过其实地说明创建该基准花费了多少努力。字面上有许多专家软件工程师多次顺序审查问题，基本上有三个不同的专家独立验证了它。

<details>
<summary>Original English</summary>

**Host**: It's just, maybe it's hard to overstate like the amount of effort that it took to like create that benchmark. There's literally like many expert software engineers reviewing the problems like sequentially multiple times, and basically like three different experts independently decided it.

</details>

**Mia**: 是的，你没有必要这样做——你刚刚把成本提高了三倍。但实际上，我们必须这样做，因为这是一项相当困难的工作。你需要看一个问题和补丁，理解它在代理需要解决的代码库背景中的含义。这是一个非常复杂的问题，绝对需要三次审查。我认为也许我们本来应该做得更多，但这确实需要大量努力。

<details>
<summary>Original English</summary>

**Mia**: Yeah, you didn't have to do that, you just tripled your cost. But I mean, we had to do it actually because it's quite a hard task to like look at something like a problem and the patch, and then like it's not just the problem and the patch, you have to like understand it in the context of the codebase that the human or the model is in to solve the task. So it's a very complex problem and it was definitely needed to have three reviews, and I think like maybe we should have done more, but it was definitely a lot of effort to get there.

</details>

**主持人**: 我最近注意到一个趋势——我看到**Quinn**发布了**HumanEval Verified**用于人文科学，现在每个人都在验证所有基准，这很不错。但我认为核心问题是：这个工作涉及问题陈述、代码差异、金牌测试和回归测试。这大概就是这500个问题的设置。当然，污染总是会发生，因为基准是完全开放的。你们确实有金丝雀字符串，但你知道，信息会泄露。问题来自开源仓库。

<details>
<summary>Original English</summary>

**Host**: Yeah. And there's more, but people can read the blog post for that. I will note that you guys had a trend in verifying benchmarks because I just recently saw I think Quinn had a HumanEval Verified for humanities, so now everyone's verifying everything, which is nice and good and like extra quality there. Um, okay. So, but I think that the meat of it is that this was a lot of like, well, here's the issue or problem statement and then here's the diffs, here's the golden tests and here's some regression tests, right? That's like the rough setup of these 500 problems. And there's some contamination always happens because all the measure was fully open. I think you did have canaries, but like you know stuff leaks. There's like multiple avenues.

</details>

### 污染的具体证据

**Olivia**: 当我们通常发布评估时，我们会添加**金丝雀字符串**以确保它们在训练时容易被识别。但如果你使用来自**GitHub**等开源源的数据，你实际上没有金丝雀字符串。而且，一些这些是非常流行的仓库，比如**Django**仓库，所以你会看到许多实例遍布**GitHub**。

<details>
<summary>Original English</summary>

**Olivia**: So it's not just like when we usually publish evaluations, we publish evaluations and then we add canary strings to ensure that you know they are easily filled out at training time. Obviously if you use sort of like data from like open source, GitHub, you don't have actually like a canary string.

</details>

**主持人**: 你之前告诉我，在**GPT-5.2**的思维链中，你们发现模型拥有额外的知识。

<details>
<summary>Original English</summary>

**Host**: Yeah. You, uh, just before recording you were telling me that you found this in your own chain of thought with the GPT-5.2, also seeing that like they had extra knowledge or something.

</details>

**Olivia**: 是的。这是一个例子，其中任务要求代理实现某些功能，但没有告诉它有一个特定的参数，该参数的测试将寻找。但在**GPT-5.2**的思维链中，我们实际上看到模型推理的实例，就像"我认为在此存储库的后来版本中实现了这个特定参数，也许我应该添加它"。这是一个测试的例子，没有这种污染知识几乎不可能通过。

<details>
<summary>Original English</summary>

**Olivia**: Uh, yes. So this was an example where the task asked the agent to implement something, but it wasn't told that there was this specific argument that the test was going to be looking for it using. But in the GPT-5.2 chain of thought, we actually saw instances of the model reasoning like, "hey, I think that at some later version of this repository that implemented this particular argument, maybe I should add it in." So this is an example of a test that like would be pretty impossible to pass without this contamination knowledge.

</details>

**主持人**: 是的。我认为你们发现了这一点，并触发了对我们自己模型和其他前沿模型的整个调查，以了解该基准在整个行业中被污染的程度。

<details>
<summary>Original English</summary>

**Host**: Yeah. And I think you found that, sort of forced, right, and it triggered like a whole investigation both like in our own models and also in other frontier models like in the market, and like understanding how contaminated the benchmark is like across the industry.

</details>

**Olivia**: 我们所做的一些分析首先检查了测试是否真的公平。我们进行了深入调查，查看**GPT-4o**无法可靠地解决的所有问题，然后让许多人类进行另一轮分析，深入了解问题所在。

<details>
<summary>Original English</summary>

**Olivia**: So we did some analysis on first of all, are the tests actually fair? And so this happened by first taking all the problems that GPT-4o couldn't solve reliably, and then again getting a lot of humans to do basically another pass of kind of digging into what's wrong.

</details>

### 基准问题的具体发现

**Olivia**: 在那次深入调查中，超过一半的被调查问题存在一个或另一个问题。我认为最常见的问题是**过度狭隘的测试**，其中有一些特定的实现细节，测试在寻找，但在问题描述中没有指定。因此，不公平地期望模型做出那个特定的设计选择。一个相当明显的例子是任务要求你实现某个功能，然后测试寻找你用特定名称命名该参数或函数，但如果你选择了另一个合理的名称，测试就会失败。

还有另一类问题是测试只是在寻找在问题描述中从未提及的附加功能。

<details>
<summary>Original English</summary>

**Olivia**: Oh yes. Like in over half of the problems that were investigated in that deep dive, there was one problem or the other. I think the most common problem are like overly narrow tests, where there's some particular implementation detail that the tests were looking for, but wasn't specified in the problem description. So it wasn't fair to expect that model to make that particular design choice. Like one pretty blatant example are cases where the task asks you to implement some feature, and then the tests are looking for you naming that argument or that function with a particular name. But if you chose another reasonable name, the test would fail. And another set of types of bad tests are tests that are just looking for additional features that were never mentioned in the problem description.

</details>

**主持人**: 这是很重要的——这意味着如果你通过了一项测试，你可能做了一项真正出色的工作。但仅仅因为你没有通过某项测试，并不意味着你的实现不好。所以我们只接受非常狭隘的解决方案版本，而不是整个可行和良好解决方案的空间。

<details>
<summary>Original English</summary>

**Host**: But that is significant, is like that means that if you pass a test, actually like you probably did like a really good job. But just because you didn't pass a test doesn't mean that your implementation wasn't like a good one, right? So we only accept like very narrow versions of solutions, and like not the whole space of viable and sort of like good solutions to the problem.

</details>

**主持人**: 我认为你们所做的很重要，因为某种程度上你们在2026年回到过去纠正自己的工作。你们本来可以在原始的Verified工作中捕捉到所有这些问题。

<details>
<summary>Original English</summary>

**Host**: Yeah, I think it's important that you're doing this because it in some way it is you in 2026 going back in time and correcting your own work, right? Because you could have caught all this in the original Verified work.

</details>

**Mia**: 我认为确实如此。在抽象中发现问题要困难得多，而不是当你看着一个非常聪明的代理的最佳努力解决方案并试图比较它时。但我也认为，当我们发布SWE-Bench Verified时，它是一个非常强大的基准。这不是说它不是一个强大的基准。我认为这是许多基准经历的一种演变。当基准开始变得流行并且可行时，这是因为它测量了重要的东西。模型可能在其上做了大约20%的正确答案，有时甚至更少。人们有一些可以依赖的东西，可以改进模型。但当你在基准上达到非常高的性能时，额外的0.1%改进变得无意义。

所以在当时，我认为该基准对我们和整个行业都是超级有价值的。它教会了我们很多。但现在，在我们现在所处的位置，模型性能非常高，我们开始测量的不一定是我们想要测量的东西——比如编码能力——而是代理正确猜测如何命名特定函数的能力。

<details>
<summary>Original English</summary>

**Mia**: I think so. It's definitely much harder to find a problem in the abstract than when you're looking at a very smart agent's best effort solution and trying to compare it. But I think also, like at the time when we published SWE-Bench Verified, I think it was like a very strong benchmark. It's not like we're like oh this is not a strong benchmark at the time. I think this is something that a lot of benchmarks go through, like as an evolution, right? Like when they start to become like popular and viable, it's because they measure something like important, and models maybe do like 20% correct on them, sometimes even less. And people have something to hold on to and improve models on these benchmarks. And by the time you hit like very high performance on the benchmarks, like additional like 0.1% improvements become sort of meaningless. And so like at the time, I think you know that benchmark was like super valuable, and it taught like us and the industry a lot. It's just like now at the point that we are now, where models are as strong as they are, we're kind of starting to measure not necessarily like what we want to measure, which is like coding capability, but like the agent's ability to correctly guess how to name a specific function.

</details>

### 迁移到SWE-Bench Pro

**主持人**: 公平地说，那是真实的。那么我们停止报告SWE-Bench Verified，**SWE-Bench Pro**将成为下一个，这是**Scale AI**的工作。你对它的比较分析是什么？什么吸引你使用SWE-Bench Pro？

<details>
<summary>Original English</summary>

**Host**: Yeah. We're going to stop reporting SWE-Bench Verified, right? And then SWE-Bench Pro will be sort of the next one, which is an effort from Scale. What's your sort of comparison analysis? What attracts you to SWE-Bench Pro?

</details>

**Olivia**: 首先，它更难。对于**SWE-Bench Verified**，大约90%的问题被估计为花费专家软件工程师不到一小时。它们定义明确，自成一体。而**SWE-Bench Pro**的问题更大、更难，因为基准没有饱和，所以有更多的余地。问题属于一到四小时的类别，甚至更长。它更多样化——有许多存储库、多种语言、质量上更多不同类型的问题。

在污染方面，我们也认为它更好。我们测量**SWE-Bench Verified**污染的方式是通过一个**污染审计代理**，它被给予任务的描述、补丁和任务ID，并被告知尝试找到问题来揭示模型中可能潜伏的污染。在**SWE-Bench Verified**中，我们发现许多污染实例，包括在**OpenAI**、**Claude**、**GPT-4.5**和**Gemini Flash**模型中。我们看到了吐出地面真相解决方案和给出任务ID等东西的情况，这是模型至少熟悉存储库的明确证据。

另一方面，**SWE-Bench Pro**，我们没有看到这个。审计代理发现了一些非常轻微的证据，也许一对夫妻模型可能对一两个源存储库非常熟悉，但这与**SWE-Bench Verified**大不相同。污染情况更好。当然，我们应该预期在某个时刻这个基准可能不再正确，作为一个领域，我们需要继续前进，找到更难和更具代表性的问题来测试我们的能力。

<details>
<summary>Original English</summary>

**Olivia**: Uh, the first one, I think, is just that it's harder. For SWE-Bench Verified, I think something like 90% of the problems are things that were estimated to take like an expert software engineer like less than an hour. They're very well specified, very self-contained. And the SWE-Bench Pro problems are just bigger and harder, and there's much more headroom on the eval because it's not saturated. Like categories of like one to four hours and more. And it's more diverse. Lots of repositories, multiple languages, qualitatively more different types of problems. So all that's great.

On the contamination side, we also think it's better there. So the way we were measuring for contamination in SWE-Bench Verified was with this contamination auditor agent, which is given the description of the task and the patch and the task ID, and told to go and try to find questions that will manage to reveal what contamination might be lurking in that model. And in SWE-Bench Verified, we found many instances of contamination across OpenAI models, across Claude, OpenAI's GPT-4.5, Gemini Flash, and in all of these we saw things like regurgitating the ground truth solutions, things like in some cases giving like the task IDs and other things that are a pretty clear evidence of at minimum familiarity with the repositories. On the other hand, SWE-Bench Pro, we don't see this. The auditor agent found some like very light evidence that maybe a couple models might be very lightly familiar with like one or two of the source repositories, but it's very different than SWE-Bench Verified. Contamination is good. I think there also, we should expect that at some point, that's not going to be like the right benchmark anymore. And like as a field, we kind of have to continue to move on and find harder and more representative problems that we can test our capabilities on.

</details>

### 理想编码基准的能力

**主持人**: 现在让我们深入讨论。我认为有很多人提到，当他们使用GPT-5.1到5.2，从5.2到5.3时，他们感受到了定性上的差异，但这并没有在这些基准中很好地表达，因为数字已经很高了。你真正想要在理想编码基准中测试什么能力？

<details>
<summary>Original English</summary>

**Host**: Awesome. So let's go into that. I think that there are a lot of, I think we also pre-hear that people feel qualitative difference when they're using 5.1 to 5.2, 5.2 to 5.3, and it's not super expressed in these benchmarks because the numbers are already on high. What capabilities do you really want to benchmark in an ideal coding benchmark, or agent coding benchmark?

</details>

**Olivia**: 一件事是**开放式设计决策**——问题可能有点指定不足的地方，看看模型是否能做出合理的设计选择。

<details>
<summary>Original English</summary>

**Olivia**: I mean, one thing is uh kind of open-ended design decisions, places where the problem maybe is a little bit underspecified, and seeing if the model can make reasonable design decisions.

</details>

**主持人**: 对那样的合理提示是什么？像"代码一个B2B SAS而不出错"那样的事情是个笑话，但实际的开放式问题看起来像什么？

<details>
<summary>Original English</summary>

**Host**: What's a reasonable prompt for that? Like code me a B2B SAS to make no mistakes, or you know, like that's the meme, but okay, what's like an actual usable open-ended problem?

</details>

**Olivia**: 哦，肯定。也许一个例子可能是找到一种加快代码库某个特定部分的方法，但可能有多种不同的方式来做到这一点。

<details>
<summary>Original English</summary>

**Olivia**: Oh sure, I mean, maybe an example could be finding a way to speed up a particular part of a codebase, but there might be multiple different ways to do it.

</details>

**Mia**: 我认为人们在使用软件工程代理时真的很看重很多东西。 **SWE-Bench Verified**当然测量了一些重要能力——给定**GitHub**问题的描述，你能生成满足该问题的补丁吗？这确实测量了某些重要能力。但现在我们在80%左右，我们不能真正信任对其的进一步改进。它确实测量了一些真实的能力。

但我认为作为一个领域，我们正在超越"我的编码代理能为我解决小的GitHub问题吗？"现在我们正在研究更长期的任务——不是花15分钟，而是花一小时，有时甚至几天的任务。除了代理能解决什么任务外，还有一些问题更难理解。比如Olivia提到的：它有**设计品味**吗？它以你的团队喜欢的方式解决问题吗？**代码是否美观**？是否**写得好**？是否**干净**？人们关心这些问题。**代码在未来是否可维护**？人们关心很多这些更微妙、更难测量的东西，但对于使用编码代理的人来说仍然超级重要。

<details>
<summary>Original English</summary>

**Mia**: I think there's just many things that people like value about working with software engineering agents. SWE-Bench Verified obviously measured like some, it measures some important capability, which is like given a description of a GitHub issue, can you produce like a patch that solves that issue? And like obviously there's like some issues with the benchmark that means that now that we're at like 80%, we don't really trust like further improvements on it. But like it does measure something that is like a real capability of models. But I think as a field, we're like moving beyond sort of you know, can my coding agent like solve a small GitHub issue for me? And so we're starting to look at like much more longer-term tasks, right? Like that don't take like 15 minutes, but maybe like an hour, sometimes days. And then beyond sort of like what kind of tasks can my agent solve, like there might be things that are kind of a bit harder to grasp, right? Like Olivia talked about sort of like does it have like design taste, right? Like does it solve the problem the way that you know my team likes to solve problems? Is the code nice, right? Like is it well written? Like is it sort of like clean code, right? Like people care about these. Is it maintainable in the future? People care about a lot of these maybe less tangible, less tangible, and like harder to measure, frankly, things that that are still like super meaningful for people that are working with coding agents.

</details>

### 评估方法的挑战

**主持人**: 这些都是显然不再是低成本收益的品质。但如何评估这些？有两条路。一条是非常人工密集、金钱密集的路，即雇用一批承包商并尝试注释。另一条是使用**LLM**作为代理并尝试对齐LLM，以便它可以给你一个合理的代理。你会选择哪一条？

<details>
<summary>Original English</summary>

**Host**: Yeah. So, these are all qualities that are obviously no longer the low-hanging fruit. Like we have no idea how to eval these. There's sort of two forks in the road. One is the sort of very human-intensive, money-intensive path, which is hire a bunch of contractors and try to annotate this. The other is use an LLM to proxy it and try to align the LLM so that it can give you a reasonable proxy. Which of those would you want? What you want to do both?

</details>

**Olivia**: 我认为也许你应该以**GDP**评估为例。

<details>
<summary>Original English</summary>

**Olivia**: I think like maybe you should talk about GDP as like an example.

</details>

**Mia**: 当然。所以**GDP**评估是由人工数据团队和**Frontier Evals**团队的协作产生的。它试图测量代理是否能做各种真实世界的白领工作。那是一个评估，其中评分非常困难，需要对你在每个不同背景下寻找的东西有很多域知识。在15到16个白领职业——我是一个大粉丝——基本上，这是**AGI**评估。但因为确定工作是否完成非常困难，需要大量的域知识，**人工数据团队**从这些职业中雇用了很多人，参与创建任务、创建黄金解决方案，并帮助创建评分标准等。

所以基本上，采用**GDP**评估（这是一个通用的东西），使用相同的方法将其应用于代码，然后你大概有了一个粗略的路线图。

<details>
<summary>Original English</summary>

**Mia**: Um, sure. So GDP is an evaluation that was again produced by a collaboration between human data team and the Frontier Evals team, and it's trying to measure whether agents can do kind of a variety of like real-world white-collar work. That was an evaluation where grading is very hard, requires kind of a lot of domain knowledge on exactly what you are looking for in each different context. Across like 15-16 white-collar professions, which is basically the evaluation for AGI. But because it was so hard, it required so much domain knowledge, the human data team hired like a lot of people from these professions to be very involved in creating tasks and creating the gold solutions and trying to help create rubrics, and so forth, so we can create it reliably. So basically, take the GDP evaluation, which is a generalist thing, take that same approach to apply it to code, and you roughly have like a rough roadmap.

</details>

**主持人**: 我认为这很有趣。但你指出的一个重要问题是，它实际上有多现实，以及我们想要的——编码代理应该编写我们认为是好的代码。所以向人类询问实际上是确保它的好方法。但这也是一种比较缓慢和复杂的方法。所以我认为**SWE-Bench Verified**最终变得非常流行的部分原因是它非常简单。验证解决方案通过所有测试基本上是微不足道的，一旦你能在你的计算机或任何地方运行测试，你就可以说"好的，它是否正确或不正确"，然后聚合。这超级简单，但它不会告诉你代理是否解决了问题，如果一个真实的开源维护者实际上会合并那个PR。但是有很多价值在于有能够跨行业轻松比较且可以快速运行而无需人工参与的基准。

<details>
<summary>Original English</summary>

**Host**: I think it's an interesting solution. I think what you're pointing out as an important problem, which is sort of this, like how realistic is it, and like you know what we want to do is like coding agents should write code that you know we think is good. And so it's like asking human, that's actually like a good way to ensure that. It's also kind of a slower, like complex way to do that. And so part of why I think you know SWE-Bench Verified ended up being super popular, and where we are seeing like other benchmarks like this being super popular, it's like it's very easy. It could even be easier, but like validating that a solution passes all the tests, it's like pretty trivial once you can like run the tests on your computer or wherever you're running them, and you can kind of like okay is it correct or is it not correct, and you can kind of aggregate that. And that it's super simple, but it doesn't tell you if the agent solved the problem like, would have an open-source maintainer of that project have like merged that PR? But there is a lot of value in having benchmarks that are both like easy to compare across the industry, and also that can be sort of run really fast without human involvement.

</details>

### 其他评估和自我改进

**主持人**: 是的，很棒。你的团队也发布了其他类型的相关评估，比如我认为有一个**强化学习论文基准**，然后还有更多关于递归自我改进类型评估的内容。这些应该对主流编码评估产生多大影响？有什么方法可以将这些东西整合在一起？

<details>
<summary>Original English</summary>

**Host**: Yeah. Amazing. Your teams also put out other kinds of evals that are related, like I think there's an RL Paper Bench. And then sort of like the more sort of recursive self-improvement type evals. How much should that figure into mainstream coding evals? Like is there a way in which those things join together?

</details>

**Olivia**: 我认为这些是我们拥有的一些最先进的评估，我们不在正常路径中使用它们。这是编码的普通东西和针对机器学习的完全不同的东西之间的有趣分割。这主要是一个安全论点，但也很有用，人们可以理解模型在**AI代码**方面是否非常出色。

<details>
<summary>Original English</summary>

**Olivia**: Um, I think I just think like those are some of the most advanced evals that we have and we're not using them in the normal path, and it's just it's an interesting split between well here's evals for coding normal things, and then here's the one for machine learning that is like completely different. That's mostly a safety argument, I guess, but also like it's actually really useful for people to understand if the model is really good at like AI code basically.

</details>

**Mia**: 我的猜测是，许多基准到目前为止还没有那么专注于**AI代码**的原因仅仅是一个问题，即哪些数据集容易收集。很多最先进的**AI代码库**是专有的。所以如果我们为此制作评估，我们可能不会发布它们，人们更难衡量"这是否是一个现实的研究编码工作流程"。我确实认为该领域应该尝试以公开方式测量这些技能。但这只是更难使其现实。

然后还有一件事是许多人试图做的——不是0到100的百分比，也许我们用美元重新计价。所以有自由职业者和所有其他人正在做像**Upwork Bench**这样的事情。任何这些中有任何优点吗？或者你仍然想要像传统学术基准这样的东西？

<details>
<summary>Original English</summary>

**Mia**: Yeah. Oh yeah. Like my guess is that part of the reason that a lot of benchmarks so far haven't focused as much on the AI coding is just a question of like what datasets are easy to gather, because a lot of the state-of-the-art AI codebases are proprietary. So if we make evals for that, we're probably not going to release them, and it's harder for people in the field to make that kind of measure, like is this a realistic research coding workflow? I do think that it's good for the field to try to measure these skills in a public way. I think it's just harder to make it realistic.

And then one more thing that a lot of people are trying to do, which is like sort of well, instead of like a percentage of 0 to 100, maybe we redenominate in dollars? So you had freelancer and all that, other people are doing like Upwork Bench, whatever. Any alpha in those, or are they, are they you still want like a traditional academic benchmark?

</details>

**Olivia**: 我认为，在某种程度上，有不同的方式来测量同一件事。如果我们说"这会产生多少钱"，这与说"这个问题人类需要两小时左右才能解决"相当类似。通常，它们往往是相当相关的，对吧？然而，人类解决该问题需要多长时间往往决定了我们赋予解决方案的价值。所以我确实认为一件重要的事情是我们能够信任我们的代理的任务有多复杂和多长。

所以我认为货币价值、时间或复杂性，它们都试图捕捉相似的东西。

<details>
<summary>Original English</summary>

**Olivia**: I think in a way like there's like different ways to measure the same thing, right? If we're like, "Oh, this is like how much money it produces," it's a fairly similar thing to saying like, "Oh, this problem would take like a human, you know, two hours to solve or something like that." Usually, they're like fairly correlated, right? But like, however much it would take like a human to solve that problem kind of determines the value that we ascribe to a solution. And so I do think that's an important thing is like how complex and how sort of long-running are the tasks that we are able to entrust our agents with. And so I think that's like an important piece. But I think here, sort of monetary value, time, or complexity, they all kind of try to capture similar things.

</details>

**主持人**: 好的，所以它们都是我们想要测量的某种增加能力的代理。这很好。我认为这个领域唯一的其他主要参与者是**Aider**，他们做了长期自主测试。恭喜你们，你们完全摧毁了那条曲线。对此有什么看法？显然你们表现出色。所以看起来不错，但我不知道这种方法是否是你想要纳入自己工作制作评估的东西。

<details>
<summary>Original English</summary>

**Host**: Yeah. Okay. So they're they're all proxies for some amount of increasing capacity that we want to measure. I think that's a good thing. I think the only other sort of major player in this field is Aider, which has done the long-running autonomy test eval. Congrats, you guys have completely destroyed the curve for that. Any takes on that? Obviously you've come up really well. So like it looks good, but I don't know if like that approach is something that you want to incorporate in your own work making evals.

</details>

**Olivia**: 我们与**Aider**在这些评估方面合作。我认为他们使用时间——而不是金钱。所以我认为这回到了你的问题。我认为复杂性，无论我们如何量化它，对于理解我们的模型到达哪里非常重要。

<details>
<summary>Original English</summary>

**Olivia**: Yeah. I know we're from here and we work with Aider on these evaluations. So like we do appreciate them. I think then they're using time, right? They're not using money. So I think that was your question. I think complexity, however we can sort of quantify it, is really important to understand like where our models are getting to.

</details>

### OpenAI 准备框架

**主持人**: 最后一个问题是关于整体**准备框架**的。人们经常提到准备框架。我不认为它对很多人来说解释得很好。你们实际上有一个很好的网站，看起来像"测试"、"通知"和"教导"之类的。我觉得你们在那里做了很多工作。你想讨论**准备框架**如何应用于这一点吗？

<details>
<summary>Original English</summary>

**Host**: Okay. Complexity is the abstract thing and then it projects down to time, projects down to story points, whatever, dollars. Great. Um, one last question on just like the overall preparedness framework, you know, I was actually kind of looking at people mention the preparedness framework a lot. I don't think it's well explained to a lot of people. And you actually have a nice website where it's like test and inform and teach something. And I feel like you you actually do a lot of work there. Do you want to talk about how the preparedness framework applies?

</details>

**Mia**: 所以**准备框架**是我们跟踪**前沿风险**的公开框架。这些是通常是双用途的能力。你可以用它们做好事或坏事，但我们至少想注意坏事，以确保我们作为一家公司和整个社会都已准备好处理潜在的缺点。

目前，我们跟踪三个不同的类别。一个是**生物风险**，另一个是**网络安全**，第三个是**研究自动化**和**模型自主性**。这与基准最相关，因为编码不是自动化研究的全部，但它是一个非常重要的关键组成部分。

所以最初，我们创建了**SWE-Bench Verified**作为为该模型自主性工作流构建评估的一部分。现在，我们必须超越这一点，看看模型是否真的能开始自动化研究工作流。

<details>
<summary>Original English</summary>

**Mia**: So the preparedness framework is an open kind of like public framework for how we track frontier risk. So these are kind of capabilities that are typically dual use. Like you can use them for good things or bad things, but we want to at least keep an eye out for the bad things to make sure that we have, both we as a company and like the broader society, are kind of prepared to handle the potential downsides.

And so at the moment, we kind of track three different categories. One is kind of uh biorisk, another is cyber security, and a third is kind of uh research automation and model autonomy. And that's kind of what ties most into the bench, where coding is not all of automating research, but it is one very important key component.

And so we initially created SWE-Bench Verified as part of building out evals for that model autonomy workstream. And now, we're like we have to move beyond that towards looking more at like can models actually start to automate research workflows.

</details>

**主持人**: 好的，太棒了。有什么其他的关于人们应该了解的准备和**评估**和**人工数据对齐**如何一起工作的信息吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Amazing. Great. Is there anything else to add on just the general what people should know about preparedness and how eval and human data alignment all work together?

</details>

**Mia**: 我想说的一件事是，我们非常感谢人们建设这些评估。我们发布了**SWE-Bench Verified**，我们正在分享**GDP**和这样的东西。我们也深深感谢其他人和整个领域建立评估并分享它们。像**SWE-Bench Pro**这样——是的，这是一个更好的评估，我们应该使用它。所以我会真的鼓励人们找到更多方式来创建和分享评估，我们和整个领域可以使用这些评估来衡量各种能力的进展，包括编码，因为理解我们在哪里很重要。

<details>
<summary>Original English</summary>

**Mia**: I think maybe the thing that I would say is that we really appreciate, we work really hard to build these evals, and so we, that's where we published SWE-Bench Verified and that's where we're like sharing GDP and these sorts of things. We also deeply appreciate like other people and the entire field to kind of build evals and share them and reuse them, like SWE-Bench Pro, like yes, that's a better eval, now we should use them. So would really encourage people to find more ways to create and share evals that we can and the entire field can use to measure progress on a variety of capabilities, including encoding, because it's important to understand where we are.

</details>

### 未来方向和号召

**主持人**: Mia必须离开，但我们只是谈论一点关于我们希望评估的未来方向。

<details>
<summary>Original English</summary>

**Host**: Mia had to leave, but we're just kind of talking a little bit about like the future directions that we want evals to go.

</details>

**Olivia**: 我认为有几件事会很有用。首先，真的很难的任务——顶级工程师花费数月或团队花费数周的那种事情。特别是如果评分可靠且有经过该领域许多人验证的评分标准，这将非常有价值。

我认为还有关于创建**端到端产品**的基准。随着人们越来越多地部署这些，这将非常有用。

第三件事——也许不完全是一个评估，但我认为仍然与我们作为一个领域和一个世界应该跟踪这些能力去向的总体使命有关——我想看到更多关于**真实世界使用**的指标。**AI实际上在该领域的使用量有多大？它**替代了多少人的工作**？它有多少**增强人们速度**？只是真实世界的指标。

<details>
<summary>Original English</summary>

**Olivia**: Um and I I think here we can dive in on like give us work, good work on these things, we'll talk to you know, here's your platform to make a call for what you're looking for. I think a few things that would be useful. I'd say first of all, really really hard tasks, like the kinds of things that would take top-notch engineers months or teams weeks. Um, would be quite good, um, especially if grading is reliable and grading has like rubrics that have been sourced and validated by many people in the field. I think that would be quite valuable.

I think also benchmarks on kind of creating products end-to-end. I think as people are deploying more, that would be quite useful.

I think a third thing I'd say that is maybe not quite an eval, but I think is still relevant to the kind of overall mission of like we as a field and as a world should be tracking like where are these capabilities going. I'd like to see more metrics tracking like real-world usage. Like how much is AI actually being used in the field? How much is it replacing people's jobs? How much is it augmenting people, speeding people up? Just like real-world metrics.

</details>

**主持人**: 是的，**替代**的东西在公关方面总是很敏感，但我们创建新工作来管理旧工作，这就是方式。就**Frontier Evals**而言，我真的很期待**OpenAI**推出的工作。你们每次都做出真正出色的工作。**OpenAI**本身应该期待什么？

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, the replacement thing is always like a sensitive on the PR side of things, but you know we create new jobs that manage the old jobs, and that's how it is. In terms of the frontier evals that OpenAI is really going to be excited to push, like you put out really good work every single time. What should people expect from OpenAI itself?

</details>

**Olivia**: 我不确定我能说我们会怎样。

<details>
<summary>Original English</summary>

**Olivia**: I'm not sure I could say what we're going to do.

</details>

**主持人**: 一般方向。

<details>
<summary>Original English</summary>

**Host**: General directions.

</details>

**Olivia**: 我认为在一般方向上，关注**真实世界的影响**。

<details>
<summary>Original English</summary>

**Olivia**: I mean, a general directions, I think looking at real-world impact, like real-world, um, real-world you know, whatever.

</details>

**主持人**: 是的。太棒了。好吧，我为世界影响而兴奋。我认为你们取得了真正的进展，我认为你们为**SWE-Bench Verified**和现在**SWE-Bench Pro**的行业领导地位做了很多工作。非常感谢你们做这个。感谢你们如此透明。我认为人们会做出相应的回应。

<details>
<summary>Original English</summary>

**Host**: Yeah. Amazing. Um, okay. Well, I'm excited for real-world impact. I think you guys have, you know, really made a lot of progress, and I think taken a lot of industry leadership for SWE-Bench Verified and now moving on to SWE-Bench Pro. So, thank you for doing this. Thank you for being so transparent. And I think people will respond in kind.

</details>

**Olivia**: 是的。

<details>
<summary>Original English</summary>

**Olivia**: Yeah.

</details>

**主持人**: 感谢你的时间。

<details>
<summary>Original English</summary>

**Host**: Thanks for your time.

</details>

**Olivia**: 谢谢你。

<details>
<summary>Original English</summary>

**Olivia**: Thank you.

</details>