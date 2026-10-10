---
author: Latent Space
date: '2026-04-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CeOXx-XTYek
speaker: Latent Space
tags:
  - harness-engineering
  - coding-agents
  - ai-products
  - software-development
  - agent-orchestration
  - prompt-engineering
  - system-thinking
  - ai-enterprise
  - continuous-integration
title: OpenAI的极致Harness工程实践：AI智能体驱动的软件开发与企业级部署
summary: 本次访谈深入探讨了OpenAI Frontier团队如何通过极致的Harness工程实现由AI智能体驱动的软件开发，达到前所未有的生产力。Ryan Lopopolo分享了其团队在零人工代码、百万行代码库的内部工具开发中，如何通过Prompt工程、系统思维和持续的智能体行为调整，克服模型局限性并实现高度自动化。对话还涵盖了AI在代码审查、协作、依赖管理及企业级平台（Frontier）中的应用，展示了AI智能体如何改变软件工程的未来。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Ryan Lopopolo
companies_orgs:
  - OpenAI
  - Snowflake
  - Stripe
  - Citadel
  - GitHub
products_models:
  - Codex
  - GPT-5.4
  - Symphony
  - Frontier
  - Elixir
  - Electron
  - Graphana
  - Playwright
  - Slack
media_books: []
status: evergreen
---
### Harness工程与AI产品构建

**主持人**: 我确实认为，在利用 **Codex**（Harness）作为构建AI产品的一部分，这里有一个值得探索的有趣空间。目前，让模型擅长编程的势头非常强劲，我们看到每个增量模型发布，任务复杂性都取得了巨大飞跃。如果你能设法将你正在尝试构建的产品，或者你正在尝试解决的用户旅程转化为代码，那么使用 **Codex**（Harness）来为你解决这个问题就显得非常自然了。它完成了所有的布线，让你只需通过提示（Prompt）进行沟通，让模型自行运作。你必须退一步，对吧？你需要以**系统思维**的心态来看待事物，并不断问：智能体（Agent）在哪里犯错误？我把时间花在哪里了？我怎样才能避免将来把时间花在那里？然后建立对我正在实施的自动化流程的信心，这样我就解决了**SDLC**的这一部分。

<details>
<summary>Original English</summary>

**主持人**: I do think that there is an interesting space to explore here with **Codex** the harness as part of building AI products, right? There's a ton of momentum around getting the models to be good at coding. We've seen big leaps in like the task complexity with each incremental model release, where if you can figure out how to collapse a product that you're trying to build, a user journey that you're trying to solve into code, it's pretty natural to use the **Codex** harness to solve solve that problem for you. It's done all the wiring and lets you just communicate in prompts to let the model cook. You kind of have to step back, right? Like you need to take a **systems thinking** mindset to things and constantly be asking where is the agent making mistakes? Where am I spending my time? How can I not spend that time going forward? And then build confidence in the automation that I'm putting in place so I have solved this part of the **SDLC**.

</details>

**主持人**: 在我们开始今天的节目之前，我只想给听众一个小小的留言。谢谢你们。如果没有你们选择点击并收听我们的内容，我们将无法为您带来你们如此明确想要的AI工程、科学和娱乐内容。赞助商几乎每天都与我们联系。但幸运的是，有足够多的听众订阅了我们，使这一切无需广告也能持续下去，我们希望保持这种状态。但我只请求大家帮一个忙。你们能做的最强大、完全免费的事情就是点击订阅按钮。这是我唯一会要求你们做的事情，这对我和我的团队来说意味着一切，他们每周都努力为你们带来Inspace节目。如果你这样做，我保证我们永远不会停止努力，让节目变得更好。现在，让我们开始吧。好的，我们现在在录音室，与来自 **OpenAI** 的 **Ryan Lopopolo** 交谈。欢迎。

<details>
<summary>Original English</summary>

**主持人**: Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis. But fortunately, enough of you actually subscribe to us to keep all this sustainable without ads, and we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you, and it means absolutely everything to me and my team that works so hard to bring the Inspace to you each and every week. If you do it, I promise you we'll never stop working to make the show even better. Now, let's get into it. All right, we're in the studio with **Ryan Lopopolo** from **OpenAI**. Welcome. Hi.

</details>

**Ryan Lopopolo**: 感谢您访问旧金山，感谢您与我们共度时光。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Uh, thanks for visiting San Francisco and thanks for spending some time with us.

</details>

**主持人**: 是的，谢谢你。我非常高兴能来到这里。你写了一篇关于**Harness工程**的爆款文章。它很可能成为这个新兴学科的定义性著作。

<details>
<summary>Original English</summary>

**主持人**: Yeah, thank you. I'm super excited to be here. You wrote a blogbuster article on **harness engineering**. It's probably going to be the defining piece of this emerging discipline.

</details>

**Ryan Lopopolo**: 谢谢。这有点有趣，感觉我们从某种意义上定义了话语权。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Thank you. It is uh it's been kind of fun to feel like we've defined the discourse in some sense.

</details>

**主持人**: 让我们稍微介绍一下，这是你第一次播客。是的。感谢你和我们一起度过。嗯，这是从何而来的？你在哪个团队？等等。

<details>
<summary>Original English</summary>

**主持人**: Uh let's let's contextualize a little bit this first podcast you've ever done. Yes. And thank you for spending with us. Uh what is where is this coming from? What team are you in? All that jazz.

</details>

**Ryan Lopopolo**: 当然，当然，当然。我在 **OpenAI** 的 **Frontier** 部门负责前沿产品探索和新产品开发。**Frontier** 是我们的企业平台，用于在任何企业中安全、大规模地部署智能体（Agent），并进行良好治理。我和我的团队的角色是找出新颖的方法，将我们的模型部署到我们能作为解决方案销售给企业的产品包中。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Sure. Sure. Sure. So uh I work on frontier product exploration new product development in uh the space of **OpenAI** **Frontier** which is our enterprise platform for deploying agents safely at scale with good governance in uh any business. And the role of me and my team has been to figure out novel ways to deploy our models into package and products that we can sell as solutions to enterprises.

</details>

**主持人**: 你有背景，我就提一下。**Snowflake**、**Stripe**、**Citadel**。是的。对。是的。

<details>
<summary>Original English</summary>

**主持人**: And you have a background I'll just squeeze it in there. **Snowflake** **Stripe** **Citadel**. Yes. Right. Yes.

</details>

**Ryan Lopopolo**: 完全相同类型的客户。是的。你想要的完全相同类型的客户。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: The exact same kind of customer entire life. Yes. The exact kind of customer that you want to

</details>

**主持人**: 所以，我想说的是，我其实并没有想到会有这样的背景。当我看了你的Twitter时，我看到了相反的东西，对吧？像这样的东西。所以，你有了“全面AI编码”的心态，像关于Slob的东西，比如把你的笔记本电脑绑在你的Whimos上，然后我看了你的个人资料，我想：“哦，你就像隔壁房间里的人一样。”所以，完美的结合。完美。我，嗯，成为AI至上主义者是很有趣的。如果你要扮演那种角色，**OpenAI** 就是实现它的地方。

<details>
<summary>Original English</summary>

**主持人**: So, I'll say I was actually I didn't expect the background. When I looked at your Twitter, I'm seeing the opposite, right? Uh stuff like this. So, you've got the mindset of like full send AI coding, uh stuff about slob, like buckling in your your laptop on your Whimos, and then I look at your profile, I'm like, "Oh, you're just like you're correct in the other room, too." So, perfect mix. Perfect. I uh it's quite fun to be AI maximalist. If you're going to live that persona, **OpenAI** is the place to do it and it's

</details>

**Ryan Lopopolo**: 他们说这是一个标记。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: a token is what they say.

</details>

**主持人**: 是的。内部没有速率限制，我可以像你说的全力以赴地做这件事，这确实很有帮助。

<details>
<summary>Original English</summary>

**主持人**: Yeah. It certainly helps that we have no rate limits internally and I can go like you said full send at this thing.

</details>

### AI Agent驱动的开发实践

**主持人**: 是的。是的。嗯，所以 **OpenAI Frontier**，你是 **OpenAI Frontier** 中的一个特殊团队。我们获得了一些可以发挥的空间，这非常令人兴奋。这就是我为什么一开始就设定了一个“不亲自编写任何代码”的限制。我想，如果我们要让智能体（Agent）部署到最终企业中，它们应该能够完成我所做的所有事情。在使用了这些编码模型，这些编码Harnesses六七八个月之后，我确实觉得这些模型已经足够成熟，这些Harnesses也足够成熟，它们在能力上，在完成工作的能力上，对我来说是同构的。所以，从“我不能写代码”这个限制开始，意味着我完成工作的唯一方法就是让智能体来完成我的工作。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. Uh so so **OpenAI Frontier** and you're a special team within **OB Frontier**. We had been given some space to cook which has been super super exciting and this is kind of why I started with kind of a out there constraint to not write any of the code myself. I was figuring if we're trying to make agents that can be deployed into end enterprises, they should be able to do all the things that I do. And having worked with these coding models, these coding harnesses over 6 7 8 months, I do feel like the models are there enough, the harnesses are there enough where they're isomeorphic to me in capability, in the ability to do the job. So starting with this constraint of I can't write the code meant that the only way I could do my job was to get the agent to do my job

</details>

**Ryan Lopopolo**: 就像，在你之前，这基本上就是文章。所以你们做了5个月的内部工具，零行代码，总代码库超过一百万行。你说它快了10倍，就像如果你自己做的话，你会快10倍。所以，是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: and like just a bit of background before that this is basically the article. So what you guys did is 5 months of working on an internal tool zero lines of code over a million lines of code in the total codebase. You say it was 10x more like it was 10x faster than you would have if you had done it by end. So yeah,

</details>

**主持人**: 这就是我们当时的心态，对吧？

<details>
<summary>Original English</summary>

**主持人**: that was kind of the mindset going into this, right?

</details>

**Ryan Lopopolo**: 没错。我想，一开始使用了 **Codex CLI** 的一些非常早期的版本和 **Codex mini** 模型，它显然比我们今天拥有的模型能力弱很多。这也是一个很好的限制，对吧？当你要求模型构建产品功能时，它却无法将各个部分组合起来，这是一种非常真实的感觉。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's right. I think right started with some of the very first versions of **Codex CLI** with the **Codex mini** model which was obviously much less capable than the ones we have today. Uh which was also a very good constraint, right? It it's quite a visceral feeling to ask the model to build you a product feature and it it just not being able to assemble the pieces together

</details>

**主持人**: 这也定义了我们进入这个项目的思维方式之一，那就是当模型无法完成任务时，你总是可以打开任务，双击进入，构建更小的构建块，然后重新组装成更广泛的目标。说实话，这样做很痛苦。第一个半月比我慢了10倍。但正因为我们付出了这样的代价，我们最终取得的成果比任何一个工程师都要高效得多，因为我们为智能体构建了工具和装配站，让它完成所有事情。但是，是的，所以我们继续前进到 **GPT-5**、**5.1**、**5.2**、**5.3**、**5.4**。经历所有这些模型代际，并看到它们的各种怪癖和不同的工作风格，也意味着当模型更新时，我们必须调整代码库以进行更改。嗯，这里有一件有趣的事情是，**5.2** 时代的 **Codex Harness** 没有后台Shell，这意味着我们可以依靠阻塞脚本来执行长时间的任务。但到了 **5.3** 和后台Shell，它变得不那么有耐心，不那么愿意阻塞。所以，我们必须重新调整整个构建系统，使其在一分钟内完成。你知道，在人们有自己想法的代码库中，我不期望能够做到这一点。但是，由于唯一的目标是让智能体在一周内提高生产力，我们从定制的Makefile构建，到Bazel，再到Turbo，再到NX，然后就把它留在那里了，因为那时构建已经很快了。

<details>
<summary>Original English</summary>

**主持人**: which kind of defined one of the mindsets we had for going into this which is whenever the model just cannot you always pop open that the task double click into it and build smaller building blocks that then you can reassemble into the broader objective. And it was quite painful to do this. Honestly, the first month and a half was 10 times slower than I would be. But because we paid that cost, we ended up getting to something much more productive than any one engineer could be because we built the tools, the assembly station for the agent to do the whole thing. But yeah, so onward to **GBD5** **51**, **52**, **53**, **54**. To go through all these model generations and see their kind of quirks and different working styles also meant we had to adapt the code base to change things up when the model was revved. Um, one interesting thing here is **5.2**, the **Codex** harness at the time, did not have background shells in it, which means we were able to rely on blocking scripts to perform long horizon work. But with **5.3** and background shells, it became less patient, less willing to block. So, we had to retool the entire build system to complete in under a minute. And you know this is not a thing I would expect to be able to do uh in a codebase where people have opinions. But because the only goal was to make the Asian productive over the course of a week we went from a bespoke make file build to basil to turbo to NX and just kind of left it there because builds were fast at that point.

</details>

**Ryan Lopopolo**: 有趣。嗯，多谈谈Turbo到NX。这很有趣，因为这是其他人一直在做的另一个方向。最终，我对实际的前端仓库架构没有太多经验。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Interesting. Uh talk more about turbo to NX. That's interesting because that's the other direction that other people have been doing. Ultimately, I have not a lot of experience with actual front-end repo architecture.

</details>

**主持人**: 你在和Josh说话，是他为我们建造了这个家伙。所以，就像我认识NXT团队，我认识来自Jared Bomber的Turbo，我想，是的，这是一个有趣的比较。

<details>
<summary>Original English</summary>

**主持人**: You're talking to Josh who built us this guy. So, like I know the NXT team and I know Turbo for from Jared Bomber and I'm like yeah that's an interesting comparison.

</details>

**Ryan Lopopolo**: 我们正在爬的山是让它快起来。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: The hill we were climbing right was make it fast.

</details>

**主持人**: 是否涉及微前端？就像。

<details>
<summary>Original English</summary>

**主持人**: Is there micro front ends involved? It's like how

</details>

**Ryan Lopopolo**: 如何复杂化React **Electron**，一个独立的应用程序。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: how complex react **Electron** uh single app sort of thing

</details>

**主持人**: 而且必须在一分钟内完成。这是一个有趣的限制。我其实对后台Shell的东西不是很熟悉。可能在FI3版本中提到过。

<details>
<summary>Original English</summary>

**主持人**: and must be under a minute. That's an interesting limitation. I'm actually not super familiar with the background shell stuff. Probably was talked about in the FI3 release.

</details>

**Ryan Lopopolo**: 基本上意味着 **Codex** 能够在后台生成命令，然后继续工作，同时等待它们完成。因此，它可以生成一个耗时的构建，然后继续，例如，审查代码。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Basically means that uh **Codex** is able to spawn commands in the background and then go continue to work while it waits for them to finish. So it can spawn an expensive build and then continue uh reviewing the code for example.

</details>

**主持人**: 是的。嗯，这有助于它为调用Harness的用户提高时间效率。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Uh and this helps it be uh more time efficient for the user invoking the harness.

</details>

**Ryan Lopopolo**: 我猜，为了真正弄清楚这一点，为什么1分钟很重要？为什么不是5分钟呢？我们希望内部循环尽可能快。1分钟只是一个不错的整数，我们能够实现它。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I guess like and just to really nail this like what does 1 minute matter? Like why not five, you know? Okay, we want the inner loop to be as fast as possible. 1 minute was just a nice round number and we were able to hit it. So,

</details>

**主持人**: 如果它没有完成，它就会终止或者什么的。

<details>
<summary>Original English</summary>

**主持人**: and if it doesn't complete, it kills it or some something.

</details>

**Ryan Lopopolo**: 不。我们只是把它看作一个信号，表明我们需要停止正在做的事情。双击，分解构建图，以缩短时间，这样我们就可以让智能体继续操作。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Uh, no. We just take that as a signal that we need to stop what we're doing. Double click, decompose the build graph a bit to get the time back under so that we can able the agent to continue to operate.

</details>

**主持人**: 这几乎就像一个棘轮。就像你在强制执行构建时间纪律，因为如果你不这样做，它就会不断增长。没错。你提到了。

<details>
<summary>Original English</summary>

**主持人**: It's almost like you're you're it's like a ratchet. It's like you're forcing buildtime discipline because if you don't, it'll just grow and grow and grow. That's right. And you mentioned that

</details>

**Ryan Lopopolo**: 就像我目前正在从事的软件，目前需要12分钟。这太糟糕了。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: like current like the software I work on currently is at 12 minutes. It sucks.

</details>

**主持人**: 这就是我过去与平台团队的经验，对吧？你有一个可接受的构建时间范围，你让它超出了范围，然后你花两三周的时间把它降回到低端。但是因为令牌（Tokens）如此便宜。是的。而且我们与模型如此疯狂地并行，我们可以不断地修剪它，以确保我们保持这些不变量，这意味着代码和SDLC中的分散性更少，这意味着我们可以以一种方式简化，并更多地依赖不变量来编写软件。

<details>
<summary>Original English</summary>

**主持人**: This has been my experience with platform teams in the past, right? Where you have sort of an envelope of acceptable build times and you let it go up to breach and then you spend 2 3 weeks to bring it back down to the lower end of the low end stop. But because tokens are so cheap. Yeah. And we're so insanely parallel with the model, we can just constantly be gardening this thing to make sure that we maintain these invariants, which means there's way less dispersion in the code and the SDLC, which means we can kind of simplify in a way and rely on a lot more invariance as we write the software.

</details>

### 人类与智能体协作的瓶颈

**Ryan Lopopolo**: 你在文章中提到，人类成为了瓶颈，对吧？你们团队有三个人。你们发布了100万行代码，提交了1500个PR。基本上，心态是什么？对吧？所以，代码是可丢弃的，你们做了大量的审查，文章中大部分都在谈论如何将一切重新表述为提示（Prompting），智能体看不到的一切都算是垃圾，对吧？不应该在那里。那么，你们是如何构建它的高层思路是什么？然后你们如何解决“人类就是PR审查”这样的问题，也就是说，人类在这个循环中扮演什么角色？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: You kind of mentioned in your article like humans became the bottleneck, right? You you kicked off as a team of like three people. You're putting out a million line of code like 1500 PRs basically what's the mindset there right so as much as code is disposable you're doing a lot of review a lot of the article talks about how you want to rephrase everything is prompting everything is what the agent can't see it's kind of garbage right you shouldn't have it in there so what's kind of like the high level of how you went about building it and then how you address like okay humans are just kind of PR review like how is human in the loop for this you know

</details>

**主持人**: 我们甚至已经超越了人类审查代码的阶段。目前，大部分的人工审查是在合并后进行的。

<details>
<summary>Original English</summary>

**主持人**: we we've moved beyond even the the humans reviewing the code uh as well. Most of the human review is uh postmerge at this point.

</details>

**Ryan Lopopolo**: 但合并合并。那甚至不是审查，那只是像“哦，让我们通过使用来让自己开心”。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: But merge merge that's not even review that's just like oh let's just make ourselves happy by using

</details>

**主持人**: 从根本上说，模型可以轻易地并行化，对吧？只要我愿意花费多少GPU和令牌，我就能拥有处理我代码库的能力。唯一稀缺的东西是我团队的同步人工注意力。一天只有这么多小时。我们必须吃午饭。我希望睡觉。虽然，你知道，停止戳机器很困难，因为它让我想要喂它。你必须退一步，对吧？你需要以**系统思维**的心态看待事物，并不断问：智能体（Agent）在哪里犯错误？我把时间花在哪里了？我怎样才能避免将来把时间花在那里？然后建立对我正在实施的自动化的信心。所以，我已经解决了**SDLC**的这一部分。通常，这看起来就像我们开始需要非常密切地关注代码，因为智能体没有正确的构建块来生成模块化软件，这些软件能够适当地分解，可靠且可观察，并且实际上能够生成一个可用的前端。对吧？因此，为了不把所有时间都花在终端前，最多同时做一两件事，我们投入精力为模型提供了可观察性，这就是文章中的那个图。

<details>
<summary>Original English</summary>

**主持人**: fundamentally the model is trivially paralyzable right as many GPUs and tokens as I am willing to spend I can have capacity to work on my hood base. The only fundamentally scarce thing is the synchronous human attention of my team. There's only so many hours in the day. We have to eat lunch. Uh I would like to sleep. Although it's quite difficult to, you know, stop poking the machine because it makes me want to feed it. Uh you kind of have to step back, right? Like you need to take a **systems thinking** mindset to things and constantly be asking where is the agent making mistakes? Where am I spending my time? How can I not spend that time going forward? And then build confidence in the automation that I'm putting in place. So I have solved this part of the **SDLC**. And usually what that has looked like is like we started needing to pay very close attention to the code because the agent did not have the right building blocks to produce modular software that decomposed appropriately that was reliable and observable and actually acred a working front end in these things. Right? So in order to not spend all of our time sitting in front of a terminal at most doing one or two things at a time invested in giving the model that observability which is that uh that graph in the the post here.

</details>

**Ryan Lopopolo**: 是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah.

</details>

**主持人**: 让我们来看看。是哪些跟踪先存在的？

<details>
<summary>Original English</summary>

**主持人**: Let's walk through this traces which which existed first.

</details>

**Ryan Lopopolo**: 我们一开始只有应用程序，其余的所有东西，从向量到所有这些登录指标API，我只用了半个下午的时间。我们特意选择了非常高级、快速的开发工具。现在有很多很棒的东西。嗯，我们大量使用了MI，这使得在我们本地开发中拉下所有用Go编写的Victoria Stack二进制文件变得微不足道。一小段Python胶水就可以把所有这些东西启动起来，然后你就可以开始了。这里有一件很酷的事情是，我们试图尽可能地颠倒过来，也就是说，我们不是设置一个环境来生成编码智能体，而是生成编码智能体，就像那是入口点一样，只有 **Codex**，然后我们通过技能（Skills）和脚本（Scripts）赋予 **Codex** 启动这个Stack的能力，如果它选择这样做的话。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: We started with just the app and the whole rest of it from vector through to all these login metrics APIs was I don't know half an afternoon of my time. We have intentionally chosen very high level fast developer tools. There's a ton of great stuff out there now. Uh we use MI a bunch which makes it trivial to pull down all these go written Victoria stack binaries in our local development. Tiny little bit of Python glue to spin all these up and off you go. One neat thing here is we have tried to invert things as much as possible which is instead of setting up an environment to spawn the coding agent into instead we spawn the coding agent like that's the entry point just codecs and then we give **Codex** via skills and scripts the ability to boot this stack if it chooses to

</details>

**主持人**: 然后告诉它如何设置一些末端变量，以便本地开发中的应用程序指向它选择启动的这个Stack。我认为这才是推理模型与过去 **GPT-4** 和 **GPT-4o** 的根本区别，过去的模型无法思考。所以你必须将它们放入具有预定义状态转换的盒子中，而在这里，我们将模型，将Harness视为整个盒子，并提供一系列选项，以及足够的上下文，让它做出明智的选择。所以销售。

<details>
<summary>Original English</summary>

**主持人**: and then tell it how to set some end variables so the app in local dev points at this stack that it has chosen to spin up and this I think is like the fundamental difference between reasoning models and the four 1s and four O's of the past where these models could not think. So you kind of had to put them in boxes with a predefined set of state transitions whereas here we have the model the harness be the whole box and give it a bunch of options for how to proceed with enough context for it to make intelligent choices. So sales

</details>

**Ryan Lopopolo**: 感觉其中很大一部分是关于脚手架（Scaffolding），对吧？以前的智能体，你会定义一个脚手架。它会在那个循环中运行，你知道，再试一次。自从我们有了推理模型之后，这种情况就改变了。当你不使用脚手架时，它们似乎表现得更好，对吧？你也会深入到一些利基领域，比如你的spec.md，以及非常短的agent.mmd。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: feel like a lot of that is around scaffolding, right? Previous agents, you would define a scaffold. It would it would operate in that, you know, loop, try again. That's kind of pivoted off from when we've had reasoning models. They're seeming to perform better when you don't have a scaffold, right? You and you go into like niches here too, like your spec.md and like having a very short agent.mmd.

</details>

**主持人**: 是的。是的。

<details>
<summary>Original English</summary>

**主持人**: Yes.

</details>

**Ryan Lopopolo**: 是的。所以你甚至在这里列出了它是什么，但是。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. So you you even lay out what it is here, but

</details>

**主持人**: 我喜欢目录。是的。像这样的东西，它真的有助于指导人们，因为每个人都在尝试做这件事。

<details>
<summary>Original English</summary>

**主持人**: I like the table of contents. Yeah. that like stuff like this, it really helps guide people because everyone's trying to do this.

</details>

### 重新发明技能与文本驱动的智能体

**Ryan Lopopolo**: 这个结构也使得将新内容放入仓库中变得非常便宜，以指导人类和智能体。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: This structure also makes it super cheap to put new content into the repository to steer both the humans and and the agents.

</details>

**主持人**: 我的意思是，你，你，你有点重新发明了技能，对吧？

<details>
<summary>Original English</summary>

**主持人**: I mean, you you kind of reinvented skills, right?

</details>

**Ryan Lopopolo**: 从第一性原理出发，打造了巨大的智能体技能。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: One big agent skills from first principles.

</details>

**主持人**: 当我们开始做这件事的时候，技能（Skills）并不存在，对吧？嗯，你有一个短小的一百行总体目录，然后你有一些小技能，对吧？核心信念，MD，技术追踪器。是的。是的。嗯，是的。所以这些技能超越了技术追踪器，并且质量分数非常有趣，因为这基本上是一个微小的脚手架，就像一个Markdown表格，它是 **Codex** 的一个钩子，用于审查我们在应用程序中定义的所有业务逻辑，评估它如何与所有这些文档化的护栏（Guardrails）匹配，并为自己提出后续工作。所以，你知道，在 beads 和所有这些票务系统之前，我们只是将后续工作作为笔记记录在一个Markdown文件中，你知道，我们可以通过Cron生成一个智能体来处理。这里有一个非常巧妙的事情，那就是模型从根本上渴望文本。所以，我们在这里做的很多事情就是找出将文本注入系统的方法。对吧？当我们因为缺少超时而收到一个页面时，例如，我可以在那个页面上直接在 **Slack** 中添加 **Codex** 并说：“我将通过添加超时来解决这个问题。请更新我们的可靠性文档，要求所有网络调用都必须有超时。”所以，我不仅做了一个及时的修复，而且还持久地编码了关于“什么是好的”这种过程知识。

<details>
<summary>Original English</summary>

**主持人**: Skills did not exist when we started doing this, right? Um you have a short one 100 line overall table of contents and then you have little skills, right? Core beliefs, MD, tech tracker. Yeah. Yeah. Um yeah. So the skills over The techjet tracker and the quality score are pretty interesting because this is basically a tiny little scaffold like a markdown table which is a hook for **Codex** to review all the business logic that we have defined in the app assess how it matches all these documented guardrails and propose follow-up work for itself. So you know before beads and all these ticketing systems we were just tracking follow-up work as notes in a markdown file which you know we could spawn an agent on acron to kind of burn down. There's this really neat thing that like the models fundamentally crave text. So a lot of what we have done here is figure out ways to inject text into the system. Right? when we get a page because we're missing a timeout, for example, I can just add **Codex** in **Slack** on that page and say, I'm going to fix this by adding a timeout. Please update our reliability documentation to require that all network calls have timeouts. So, I have not only made a point in time fix, but also like durably encoded this process knowledge around what good looks like.

</details>

**Ryan Lopopolo**: 是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah.

</details>

**主持人**: 我们把它提供给根编码智能体，当它进行工作时。但你也可以用它来提取测试，或者一个代码审查智能体，它指向相同的东西，以缩小所生成代码的可接受范围。我认为我对这类事情的一个担忧是，你认为你做出了正确的决定，让它永久地存在于所有事物中。是的。

<details>
<summary>Original English</summary>

**主持人**: And we give that to the root coding agent as it goes and does the thing. But you can also use that to distill tests out of or a code review agent which is pointed at the same things to narrow the acceptable universe of the code that's produced. I think one of the concerns I have with that kind of stuff is like you think you're making the right call by making it persisted for all time across everything. Yes.

</details>

**Ryan Lopopolo**: 但你没有考虑到你需要做出的例外情况，对吧？然后你必须回滚它。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: But then you didn't think about the exceptions that you need to make, right? And then you have to roll it back.

</details>

**主持人**: 部分原因是。有时它会过度遵守指令。

<details>
<summary>Original English</summary>

**主持人**: Part of it is also sometimes it can follow instructions too well.

</details>

**Ryan Lopopolo**: 这有点像一个技能，对吧？所以它决定何时使用工具，对吧？就像它不会在每次调用时都运行。它会决定何时检查质量分数，对吧？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: It's somewhat a skill, right? So it determines when it uses the tools, right? Like it's not it's not like it'll run at every call. It'll determine when it wants to check quality score, right?

</details>

**主持人**: 是的。我们在提供给这些智能体的提示中确实允许它们回绝。嗯，当我们第一次开始将代码审查智能体添加到PR时，它会是本地的 **Codex** 编写更改，推送PR。在这些PR同步时，一个审查智能体触发，它发布评论。我们指示 **Codex** 必须至少承认并回应这些反馈。最初，驱动代码作者的 **Codex** 愿意被PR审查员“霸凌”，这意味着你可能会陷入一种情况，即事情没有收敛。所以我们不得不。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And we do kind of in the prompts we give these agents allow them to push back. Um when we first started adding code review agents to the PR, it would be **Codex** locally writes the change, pushes up a PR. On those PR synchronizations, a review agent fires, it posts a comment. We instruct **Codex** that it has to at least acknowledge and respond to that feedback. And initially the **Codex** driving the code author was willing to be bullied by the PR reviewer which meant you could kind of end up in a situation where things were not converging. So we kind of had

</details>

**Ryan Lopopolo**: 我们不得不对这两个东西的提示添加更多的可选性。对吧？就像审查智能体被指示倾向于合并东西，而不是浮出任何优先级高于P2的问题。我们没有真正定义P2，但我们给了它。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: we kind of had to add more optionality to the prompts on both of these things right like the reviewer agents were instructed to bias toward merging the thing to not surface anything greater than a P2 in priority. We didn't really define P2 but we we gave it

</details>

**主持人**: 定义P2。我们给了它一个框架，在这个框架内，它可以评分它的输出，然后。

<details>
<summary>Original English</summary>

**主持人**: to define P2. We gave it a framework within which to uh score its output and then

</details>

**Ryan Lopopolo**: 大于P0会更糟，对吧？P2是P0，如果你合并这个东西，你就会摧毁代码库，对吧？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: greater than P 0 is worse, right? Georgia P2 is P 0 is you will like nuke the code base if you merge this thing, right?

</details>

**主持人**: 是的。是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah.

</details>

**Ryan Lopopolo**: 但在代码编写智能体方面，我们也赋予它灵活性，可以推迟或反驳审查反馈，对吧？这经常发生，对吧？比如，我碰巧注意到一些东西，并在代码审查中留下了一个评论，这可能会使范围扩大两倍，对吧？我通常并不意味着这需要在当下立即解决。它更多的是一个参考信息，对吧？把它归档到待办事项中，在下一个修复周中处理。如果没有这个允许的上下文，编码智能体将倾向于它们所做的事情，那就是遵循指令。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: But also on the on the code authoring agent side, we also gave it the flexibility to either defer or push back against review feedback, right? It happens all the time, right? like I happen to notice something and leave a code review which could blow up the scope by a factor of two, right? I usually don't mean for that to be addressed exactly in the moment. It's more of an FYI, right? File it to the backlog, pick it up in the next fix it week sort of thing. And without the context that this is permissible, the coding agents are going to bias toward what they do, which is following instructions.

</details>

**主持人**: 是的，我确实想检查几件事，对吧？就像，嗯，所有这些编码审查智能体都可以自主合并。

<details>
<summary>Original English</summary>

**主持人**: Yeah, I do wanted to check in on a couple things, right? like uh all the the the coding review agent it can merge autonomously

</details>

**Ryan Lopopolo**: 我认为很多人对此感到不舒服，对吧？你这里有一个列表，列出了智能体做了多少事情，它们做产品代码和测试CI配置、发布工具、内部开发工具、文档、**EVA Harness**、审查评论、管理仓库本身的脚本、生产仪表板定义文件，几乎所有东西。是的。嗯，所以它们都在同时运行，团队中是否有人可以拉动一根绳子来停止一切？因为我们正在这里构建一个原生应用程序，我们没有进行持续部署，对吧？所以，仍然有一个人类在循环中，负责剪切发布分支。我明白了。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I think that's something that a lot of people aren't comfortable with right and you have a list here of how much agents do they do product code and test CI configuration release tooling internal dev tools documentation eva harness review comments scripts that manage the repository itself production dashboard definition files like everything yes and uh so they're just all turning at the at the same time is there like a cord that that any human on the team pulls to stop everything So because we are building a native application here, we're not doing continuous deployment, right? So there is still a human in the loop for cutting the release branch. I see

</details>

**主持人**: 我们要求在将其推广到分发之前，对应用程序进行一次经过祝福的人工批准的冒烟测试。

<details>
<summary>Original English</summary>

**主持人**: we require a bless human approved smoke test of the app before we promote it to distribution these sorts of things.

</details>

**Ryan Lopopolo**: 所以你在应用程序上工作，你没有构建像基础设施那样的东西，你没有像九个九个可靠性那样的东西。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: So you're working on the app you're not building like infrastructure where where you have like nines of reliability that kind of stuff.

</details>

**主持人**: 没错。没错。好的。而且，我完全承认，所有这些活动都发生在一个完全全新的仓库中。所以，不应该认为这普遍适用于，比如，这是一个你要交付给客户的生产产品。当然。是的。你知道，所以这是真实的。

<details>
<summary>Original English</summary>

**主持人**: That's correct. That's correct. Okay. And also like full recognition here that all of this activity took in a completely green field repository like there's should be no that this applies generally to like this is a production thing you're going to ship to customers of course. Yeah. You know so this is real

</details>

### 模型能力的演进与瓶颈

**Ryan Lopopolo**: 就像，其中一件事是你提到你把这个作为一个全新的仓库开始。第一个月左右的入职工作相当，就像倒退一样，对吧？你必须与系统一起工作，现在你已经达到了那个点，你知道，你非常自主。我很好奇，比如，好吧，那么人类在这个循环中扮演了什么角色？你希望仍然可以自动化的瓶颈是什么？其中一部分也是，你认为模型的轨迹如何改进，并分担更多的人类参与循环？我们刚刚获得了 **GPT-5.4**。嗯，它确实很好。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: and like one of the things there is you mentioned you started this as a repo from scratch. The onboarding first month or so was pretty it was like working backwards right and you had to work with the system and now you're at that point where you know you're very autonomous. I'm curious like okay so what how human in the loop is it right so like what are the bottlenecks that you wish you could still automate and part of that is also like where do you see the model trajectory improving and offloading more human in the loop right we just got **5.4** for um it's a really good

</details>

**主持人**: 顺便说一句，非常棒的模型。

<details>
<summary>Original English</summary>

**主持人**: fantastic model by the way.

</details>

**Ryan Lopopolo**: 是的。是的。这是第一个融合了顶级编码能力的模型。所以它是 **Codex** 级别的编码和推理。所以通用的推理都在一个模型中，对吧？所以。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah. It's the first one that's merged uh top tier coding. So it's **Codex** level coding and reasoning. So general reasoning both in one model, right? So

</details>

**主持人**: 和计算机使用。

<details>
<summary>Original English</summary>

**主持人**: and computer use

</details>

**Ryan Lopopolo**: 计算机使用。现在我可以直接让 **Codex** 写博客文章。而对于这个，我必须在聊天和。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: computer use. Now with I can just have **Codex** write the blog post. Whereas for this one I had to balance between chat and

</details>

**主持人**: 哦，我需要，我可能要失业了。哦，天哪。

<details>
<summary>Original English</summary>

**主持人**: oh I need to I might be out of a job. Oh my god.

</details>

**Ryan Lopopolo**: 我知道。你刚刚给了我一个关于完全由AI驱动的通讯的想法，就像 **GPT-5.4** 可以做到一样。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I know. You just gave me an idea for a completely AI newsletter that like **5.4** could do.

</details>

**主持人**: 是的，我明白了。现在。

<details>
<summary>Original English</summary>

**主持人**: Yeah, I get it. Now,

</details>

**Ryan Lopopolo**: 这种事情只是“闭环”的一个例子，对吧？就像你提到的仪表板。我们让 **Codex** 编写 **Graphana** 仪表板的JSON，并发布它们，同时响应页面，这意味着当它收到页面时，它知道哪些仪表板是定义的，以及哪个警报是由代码库中哪个确切日志触发的，因为所有这些东西都汇总在一起了。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: this sort of thing is just one example of closing the loop, right? like the dashboard thing you mentioned. We have **Codex** authoring the JSON for the **Graphana** dashboards and publishing them and also responding to the pages which means when it gets the page it knows exactly which dashboards are defined and what alerts what alert was triggered by which exact log in the codebase cuz all of this stuff is collated together.

</details>

**主持人**: 它必须拥有所有权。

<details>
<summary>Original English</summary>

**主持人**: It has to own everything.

</details>

**Ryan Lopopolo**: 是的。是的。这意味着如果我们的停机没有导致页面错误，它就可以使用现有的仪表板集。它拥有现有的指标和日志集，可以找出仪表板或底层指标中的差距，并一次性修复它们。就像你让一个全栈工程师能够从后端一直驱动一个功能到前端一样。所以，看起来你们团队所做的大部分工作都是以模型希望软件编写的方式全面工作，对吧？对于更好的代码可读性，智能体可读性，它对人类来说可读性更差。你认为这会如何影响更广泛的团队？所以，在 **OpenAI**，你是否像这样联络，说这就是软件应该编写的方式？就像我能想象你加入一个新团队，带着这种方法论，这种心态，呃，团队有自己的代码审查方式，团队编写代码的方式，团队的结构。其中很大一部分是为了人类的可读性。那么，我们是否都应该改变？这在 **OpenAI** 内部以及更广泛的软件工程领域会如何发展？对吧？就像，是不是那些采用这种方法的团队会，你知道，这非常彻底，对吧？你必须做出一个非常大的转变。他们应该全力以赴吗？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yes. Yes. And it means that if we have an outage that did not result in a page, it has the existing set of dashboards available to it. It has the existing set of metrics and logs and can figure out where the gaps in the dashboard are or in the underlying metrics and fix them in one go. In the same way you would kind of have a full stack engineer be able to drive a feature from the back end all the way to the front end. So it seems like a lot of the work you guys had to do was you as a small team are fully working for a way that the model wants the software to be written right it's less human legible for better code legibility agent legibility how do you think that affects broader teams so one at **OpenAI** like do you leaison like this is how software should be written like I can imagine say you join a new team with this methodology this mindset uh there's ways that you know teams do code review teams write code like teams are structured And a lot of it is for human legibility. So like should we all swap? Like how does this play back one broader into **OpenAI** and then like broader into software engineering, right? Like is it like teams that pick this up will like you know it's pretty drastic, right? You have to make a pretty big switch. Should they just full send like

</details>

**主持人**: 心态非常明确，我脱离了流程，对吧？我真的不能对代码层面的东西有深入的看法。这就像我是一个领导500人组织的团队技术主管一样，是的，我不适合在每个PR上深究。这就是为什么合并后代码审查在这里是一个很好的类比，对吧？我有一些代表性的代码样本，我必须用它来推断团队在哪里挣扎，在哪里可以得到帮助，在哪里他们已经快速行动，我可以将注意力转移到其他地方。

<details>
<summary>Original English</summary>

**主持人**: the mindset is very much that I'm removed from the process, right? I can't really have deep code level opinions about things. It's as if I'm group tech leading a 500 person organization like yeah like it's not appropriate for me to be in the weeds on every PR. This is why that postmerge code review thing is like a good analog here right like I have some representative sample of the code as it is written and I have to use that to infer what the teams are struggling with where they could use help where they're already moving quickly and I can pivot my focus elsewhere.

</details>

**Ryan Lopopolo**: 是的。所以，我对所编写的代码并没有太多看法。但是，我有一个基于命令的类，它用于拥有可重复的业务逻辑块，这些业务逻辑块自带跟踪、指标和可观察性。对吧？所以，重点不是业务逻辑的结构，而是它使用了这个原语，因为我知道这默认会带来杠杆作用。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. So I don't really have too many opinions around the code as it is written. I do however have like a commandbased class which is like used to have repeatable chunks of business logic that comes with tracing and metrics and observability for free right and the thing to focus on is not how that business logic is structured but that it uses this primitive because I know that's going to give leverage by default.

</details>

**主持人**: 是的。是的。回到那种**系统思维**。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. back to that sort of **systems thinking**

</details>

**Ryan Lopopolo**: 你在博客文章中也提到了这一点，即强制执行架构和品味，你如何设定使用范围。嗯，还有一部分是关于重新定义工程等，但，是的，听起来很有趣，你知道。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: and you have part of that in your blog post enforcing architecture and ta taste how you set boundaries for what's used uh there's also a section on like redefining engineering and stuff but yeah it's just it's interesting to hear you know

</details>

**主持人**: 你知道，随着模型变得越来越好，它们在提出这些抽象以解除自身阻塞方面也变得越来越好，这再次让我能够不断提升到更高的层次，更深入地展望未来，看看最终会阻碍团队发布产品的因素。

<details>
<summary>Original English</summary>

**主持人**: and you know as the models have gotten better they have gotten better at proposing these abstractions to unblock themselves which again lets me move higher and higher up the stack to look deeper into the future on what ultimately block the team from shipping

</details>

**Ryan Lopopolo**: 是的，你提到了。嗯，所以这主要是一个拥有100万行代码库的 **Electron** 应用程序，但它也管理自己的服务。所以它就像一个前端的后端。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: yeah you mentioned And uh so you this is primarily a it's like a 1 million line of code codebase **electron** app uh but it manages its own services as well. So it's like a back end for front end type thing.

</details>

**主持人**: 我们确实有一个后端，但那是托管在云端的。但是这种结构实际上是在 **Electron** 内部的独立主进程和渲染进程中。

<details>
<summary>Original English</summary>

**主持人**: We do have like a a backend in there but that's hosted in the cloud. But this sort of structure is actually within the separate main and renderer processes with within the **electron**.

</details>

**Ryan Lopopolo**: **Electron** 就是这样工作的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's just how **electron** works.

</details>

**主持人**: 是的。是的。所以，就像，也以同样的严谨程度处理了MVC风格的分解，这非常有趣。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. So like like have also treated like MVC style decomposition with the same same level of rigor which has been very fun.

</details>

### AI原生开发范式转变

**Ryan Lopopolo**: 呃，我有一个有趣的双关语，这有点离题，但你知道MVC是模型-视图-控制器，任何全栈Web开发人员都知道这一点，但我的AI原生版本是模型-视图-爪子，爪子就是Harness。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Uh I have a fun pun this is like a tangent but you know MVC is model view controller and any sort of full stack web dev knows that but my AI native version of this is model view claw the claw the the harness.

</details>

**主持人**: 没错。没错。没错。我确实认为，在利用 **Codex**（Harness）作为构建AI产品的一部分，这里有一个值得探索的有趣空间。目前，让模型擅长编程的势头非常强劲，我们看到每个增量模型发布，任务复杂性都取得了巨大飞跃，如果你能设法将你正在尝试构建的产品，或者你正在尝试解决的用户旅程转化为代码，那么使用 **Codex**（Harness）来为你解决这个问题就显得非常自然了。它完成了所有的布线，让你只需通过提示（Prompt）进行沟通，让模型自行运作。

<details>
<summary>Original English</summary>

**主持人**: That's right. That's right. That's right. I do think that there is an interesting space to explore here with **Codex** the harness as part of building AI products right there's a ton of momentum around getting the models to be good at coding we've seen big leaps in like the task complexity with each incremental model release where if you can figure out how to collapse a product that you're trying to build a user journey that you're trying to solve into code it's pretty natural to use the **Codex** harness to solve that problem for you. It's done all the wiring and lets you just communicate in prompts to let the model cook.

</details>

**Ryan Lopopolo**: 这非常有趣。而且它也是一种非常工程化可读的方式来增加。对。是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: It's been very fun. And it's also like a very engineering legible way of increasing. Right. Yeah.

</details>

**主持人**: 只是给你，只是给模型脚本，你为自己构建的相同脚本。

<details>
<summary>Original English</summary>

**主持人**: Just give you just give the model scripts, the same scripts you would already build for yourself.

</details>

**Ryan Lopopolo**: 是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah.

</details>

**主持人**: 嗯。是的。所以对于听众来说，这是 **Ryan** 在说软件工程或编码智能体将吞噬知识工作，就像那些你通常认为必须为此构建一个单独智能体的非编码部分一样。不，你从编码智能体开始，然后从那里向上发展，就像OpenClaw一样，对吧？它内部是Python。

<details>
<summary>Original English</summary>

**主持人**: Um Yeah. So for listeners, this is **Ryan** saying that software engineering or coding agents will eat knowledge work like the non-coding parts that you would normally think, oh, you have to build a separate agent for it. No, you start with coding agent and go up from there, which openclaw has, right? It's pie under the hood.

</details>

**Ryan Lopopolo**: 是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yes.

</details>

**主持人**: 基本上用代码定义你的任务。一切都是编码智能体。

<details>
<summary>Original English</summary>

**主持人**: Basically define your task in code. Everything is a coding agent.

</details>

**Ryan Lopopolo**: 顺便说一句，既然我提到了它，这可能是你唯一会提到它的地方。你有没有使用过OpenClaw？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: By the way, since I brought it up, it's probably the only place you bring it up. Is any open claw usage from you? Any

</details>

**主持人**: 不，不，我没有。我的房子里没有闲置的Mac mini。

<details>
<summary>Original English</summary>

**主持人**: No, no, not for me. I don't have any spare Mac minis rattling around my house.

</details>

**Ryan Lopopolo**: 你买得起。嗯，不，我只是有点好奇，它是否改变了 **OpenAI** 中的任何东西，但现在可能还处于早期阶段。然后，你知道，我想在这里拉上的另一件事是，你提到了票务系统，你提到了PRs，我想知道这两个东西是否必须消失，或者为这种编码而重新发明，对吧？所以Git本身就像对多智能体非常不友好。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: You can afford it. Um, no, I just I'm kind of curious if it's like changed anything in **OpenAI** yet, but it's probably early days. And then the, you know, the other thing I want to pull on here is like you mentioned ticketing systems and you mentioned PRs and I'm wondering if both those things have to go away or be reinvented for this kind of coding, right? So the git itself and is like very hostile to multi- aents.

</details>

**主持人**: 是的，我们大量使用了工作树（Work Trees）。

<details>
<summary>Original English</summary>

**主持人**: Yeah, we make we make very heavy use of work trees,

</details>

**Ryan Lopopolo**: 对吧？但即使如此，就像我昨天刚发布了一个关于Cursor的播客，他们说他们要放弃工作树，因为它们仍然有很多合并冲突。它们仍然太不直观了。但是继续。模型在解决合并冲突方面非常出色。是的。为了达到我不需要同步地在终端循环中的状态，我几乎不在乎是否有合并。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: right? But like even then like I just did a dropped a podcast yesterday with cursor saying then they said they're getting rid of work trees because like it still has too many merge conflicts. It's still too unintuitive. But go ahead. The models are really great at resolving merge conflicts. Yeah. And to get to a state where I'm not synchronously in the loop in my terminal, I almost don't care that there are merge

</details>

**主持人**: 可丢弃的，对吧？我们调用了一个美元的技能（Skill），它指导 **Codex** 推送PR，等待人类和智能体审查员，等待CI通过，修复可能存在的任何问题，如果PR出现冲突则合并上游，等待所有测试通过，将其放入合并队列，处理问题直到它进入主分支。这就是完全授权的含义，对吧？就像这在大型模型中，对人类来说，合并PR可能是一项繁重的任务，但智能体完全有能力做到这一点，我真的不必考虑它，除了保持我的笔记本电脑开着。

<details>
<summary>Original English</summary>

**主持人**: disposable, right? We invoke a dollar land skill and that coaches **Codex** to push the PR, wait for human and agent reviewers, wait for CI to be green, fix the flakes if there are any merge upstream if the PR comes into conflict, wait for everything to pass, put it in the merge queue, deal with flakes until it's in main. And this is kind of what it means to delegate fully, right? like this is this is in a you know very large model probably a significant tax on humans to get PRs merged but the agent is more than capable of doing this and I really don't have to think about it other than keep my laptop open.

</details>

**Ryan Lopopolo**: 是的。我以前更是一个控制狂，但现在我想，是的，实际上你做得比我更好。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. I used to be much more of a control freak but now I'm like yeah actually you could do a better job this me.

</details>

**主持人**: 是的。在正确的语境下。

<details>
<summary>Original English</summary>

**主持人**: Yeah. With the right context.

</details>

**Ryan Lopopolo**: 是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yes.

</details>

### Harness工程的非功能性需求

**主持人**: **Harness工程**还有其他什么吗？只是这部分。我只是想确保我们。

<details>
<summary>Original English</summary>

**主持人**: Anything else in harness engine in general? Just this piece. I just wanted to make sure we

</details>

**Ryan Lopopolo**: 我认为有一点我可能在文章中没有说得非常清楚，但我确实在Twitter上听到有人对此感兴趣。有什么议论，然后你的回应是什么？

<details>
<summary>My note**: The transcript has "What's the chatter and then what's your response?", which seems like the host is asking *Ryan* to explain the chatter and his response. So I should attribute this to Ryan.**Original English</summary>

**Ryan Lopopolo**: I think one thing that I maybe didn't make super clear in the article that I I kind of heard on Twitter as an interest to them. What's the chatter and then what's your response?

</details>

**主持人**: 最终，我们所有编码在文档、测试和审查智能体中的东西，以及所有这些东西，都是将构建高扩展、高质量、可靠软件的所有非功能性需求（non-functional requirements）放入一个空间，通过提示（Prompt）注入智能体。我们或者将其写成文档，或者添加Lint，其中错误消息会告诉如何做正确的事情。因此，整个元（Meta）的目的是基本上从我团队中所有工程师的头脑中提取出他们认为“好”是什么样子，他们会默认做什么，或者他们会如何指导新员工去做才能使东西合并。这就是为什么我们关注智能体所犯的所有错误，对吧？这是编写的代码与尚未写下的非功能性需求不符。

<details>
<summary>Original English</summary>

**主持人**: Ultimately, all the things that we have encoded in docs and tests and review agents and all these things are ways to put all the non-functional requirements of building high-scale highquality reliable software into a space that prompt injects the agent. We either write it down as docs, we add lints where the error messages tell how to do the right thing. So the whole meta of the thing is to basically tease out of the heads of all the engineers on my team what they think good looks like, what they would do by default or what they would coach a new hire on the team to do to get things to merge. And that's why we pay attention to all the mistakes mistakes that the agent makes, right? This is code being written that is misaligned with some as yet not written down non-functional requirement.

</details>

**Ryan Lopopolo**: 抱歉。网上的人误解了什么？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Sorry. What did the online people misunderstand or

</details>

**主持人**: 不，有人真的就是这么说的。我当时想：“哦，是的。好吧。这就是，这就是，这就是我正在做的事情，我同意。”是的。我明白了。我明白了。我明白了。我明白了。

<details>
<summary>Original English</summary>

**主持人**: No, what somebody just literally said that. I was like, "Oh, yeah. Okay. This this is this is the thing. This is what I was doing agree with." Yeah. I see. I see. I see. I see.

</details>

**Ryan Lopopolo**: 我明白了。我明白了。有趣。还有一件我完全没有想到的巧妙事情是，人们只是把文章链接发给Pi或 **Codex**，然后说：“让我的仓库变成这样。”

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I see. I see. Interesting. One other neat thing which I did totally did not expect is folks were just taking the link to the article and giving it to like pi or **Codex** and and say make my repo this

</details>

**主持人**: 你实现了完全递归。

<details>
<summary>Original English</summary>

**主持人**: you achieve a full recursion

</details>

**Ryan Lopopolo**: 而且效果惊人。真的，效果惊人。就像我昨天用 **GPT-5.4** 尝试了一下，我当时没有那么多时间，我当时在外面演讲，这是我其中一件要做的事情，我想：“好吧，我有这篇文章，我们能，我们能就这样把它搭起来，看看会怎么样吗？”我第一次就是这么做的，然后我想：“好吧，让我再拿一个小侧边仓库，然后说，如果我要完全自动化它，就像这样，因为我还没有写一行代码，它就像一套完整的。”

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: and it was wildly effective really it was wildly effective like this actually is something I tried with **5.4** yesterday I I didn't have that much time I was like out speaking at something and this is one of my things I was like okay I have this article can we can we just like scaffold out what it would be like to run this and I I did it first as that and then I was like okay let me take another little side repo and say like okay if I was to fully automate this like this cuz I haven't written a line of code it's like a full set

</details>

**主持人**: 这是一个我用语音TTS做的副业，我只是像随便做一些东西，这不是生产级的，我想：“我怎么才能让它变成这样呢？”它实际上是一种很好的方式，它是一种很好的方式来学习可以改变什么，可以像这样，这只是一种很好的分析方式，你给它所有的代码，你给它所有的上下文，你给它文章，它会很好地引导你。

<details>
<summary>Original English</summary>

**主持人**: it's a side thing I'm doing with like voice TTS I'm just like slobbing out whatever it's not production I'm like how would I make this like this and it's it's actually like a really good way it's like a good way to learn what could be changed what could be like it's just a good analyzing right you give it all the code you give it all the context you give it the article and it it walks you through it very well

</details>

**Ryan Lopopolo**: 没错。没错。我想在我们去 **Symphony** 之前还有一件事，我想谈谈 **Brett Taylor** 的回应。我们邀请他参加了节目。他是你的董事长，这太疯狂了。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: that's right that's right I guess one more thing before we go to **Symphony** is I wanted to cover **Brett Taylor**'s response. We had him on the on the show. He is your chairman which is wild.

</details>

**主持人**: 是的。嗯，他也在阅读你的文章，并参与其中。他说软件依赖项基本上正在消失。它们可以被供应商化。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Uh that he's reading your articles as well and like getting engaged in it. He says software dependencies are going away basically. They can just be like vendored.

</details>

**Ryan Lopopolo**: 是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yes.

</details>

**主持人**: 嗯，回复。

<details>
<summary>Original English</summary>

**主持人**: Uh response

</details>

**Ryan Lopopolo**: 100%。你仍然会向 **DataDog** 付费。你仍然会向 **Temporal** 付费。谢谢。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: 100%. You still prom you still pay **DataDog**. You still pay **Temporal**. Thank you.

</details>

**主持人**: 是的。我们现在能够内部化的依赖项的复杂程度，我想说是中低水平。对吧？仅仅基于模型的能力。

<details>
<summary>Original English</summary>

**主持人**: Yep. The level of complexity of the dependencies that we can internalize is I would say low medium right now. Right. just based on model capability.

</details>

**Ryan Lopopolo**: 什么是中等水平？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: What is what is medium?

</details>

**主持人**: 我，我，我可以说，几千行的依赖项，我们可以在一个下午的时间内轻松地内部化。其中一个巧妙之处在于，你可能根本不需要大部分代码，对吧？通过内部化一个抽象，你可以剥离所有通用部分，只关注你需要启用特定构建内容的部分。

<details>
<summary>Original English</summary>

**主持人**: I I I would say like a a couple thousand line dependency is a thing that we could inhouse no problem in an afternoon of time. One neat thing about it is like probably most of that code you don't even need, right? Like by in-housing an abstraction, you can kind of strip away all the generic parts of it and only focus on what you need to enable the specific things you're building.

</details>

**Ryan Lopopolo**: 我一直称之为插件的终结。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I've been calling this the end of plugins.

</details>

**主持人**: 是的。因为有太多，你知道，当我发布一个开源项目时，我希望接受所有东西，并且自由。我希望接受，对吧，这是Postel定律，但这意味着有太多的臃肿，太多的开销。

<details>
<summary>Original English</summary>

**主持人**: Yeah. because there's so much like you know when I publish an open source thing I want to accept everything and be liberal I want to accept right this is postal's law but that means there's so much bl so much overhead

</details>

**Ryan Lopopolo**: 这里还有一个巧妙之处是，当我们在仓库中部署 **Codex** 安全时，它能够深入审查和更改内部化的依赖项。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: one other neat thing about this too is when we deploy **Codex** security on the repo it is able to deeply review and change the internalized dependencies

</details>

**主持人**: 以比打补丁到上游、等待发布、拉下来、确保与我仓库中的所有传递依赖项兼容等方式低得多的摩擦。所以，如果代码是免费的，因为令牌便宜，内部化这些东西的摩擦也低得多。

<details>
<summary>Original English</summary>

**主持人**: in a much lower friction way than it would be to like push patches upstream wait for them to be released pull them down make sure that's compatible with all the transitives I have in my repo and things like that. So, it's also much lower friction uh to kind of internalize some of these things if code is free because the tokens are cheap sort of thing.

</details>

**Ryan Lopopolo**: 是的。是的。我认为，我唯一反对这一点论点基本上是规模测试，显然像 **Linux**、**MySQL** 这样的大型软件，它甚至调用数据和时间依赖，然后可能是安全测试，嗯，传统上，我认为是Linus Torvalds说的，开源安全是最好的消毒剂。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah. I I think like the the the only argument I have against this is basically scale testing which obviously the larger pieces of software like **Linux** **my SQL** he calls up even the data and temporals and then maybe security testing where uh classically I think is it Linus Tovals who said like security open source is the best disinfectant

</details>

**主持人**: 对，众目睽睽。

<details>
<summary>Original English</summary>

**主持人**: right many eyes

</details>

**Ryan Lopopolo**: 众目睽睽。而且，如果你，你知道，内联你的依赖项并编写它们，你将不得不重新学习你所知道的其他人犯的错误。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: many eyes and uh if you you know inline your dependencies and and code them up you're going to have to relearn mistakes from other people that you know

</details>

**主持人**: 是的。是的。你知道，要内部化这种依赖关系，你又回到了起点，你必须重新组装所有这些零碎的东西，才能对所编写的代码有高度的信心。

<details>
<summary>Original English</summary>

**主持人**: Yep. Yep. And you know to internalize that dependency you're back to zero and you have to kind of start reassembling all those bits and pieces to have high confidence in the code as it is written right.

</details>

**Ryan Lopopolo**: 是的。嗯。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Um

</details>

**主持人**: 甚至像这个介绍的一部分，你基本上提到所有东西都是由 **Codex** 编写的，包括内部工具，对吧？所以内部工具，就像你在可视化正在发生的事情时，它正在向前写入。是的，我现在为AI构建了内部工具，我只是展示给他们看，他们问我花了多长时间，我没有花任何时间，我只是提示它，你知道。

<details>
<summary>Original English</summary>

**主持人**: even part of like the first intro of this you basically mentioned like everything was written by uh **Codex** including internal tooling right so internal tooling like when you're visualizing what's going on it's it's writing it forward to Yeah, I built internal tools for AI now and like I just showed them off and they're like how long did you spend and I I they I didn't spend any time I just prompted it, you know,

</details>

**Ryan Lopopolo**: 这里有一个非常有趣的故事。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: very funny story here.

</details>

**主持人**: 是的，说吧。

<details>
<summary>Original English</summary>

**主持人**: Yeah, go ahead.

</details>

**Ryan Lopopolo**: 我们将应用程序部署到内部的头几十个用户，呃，出现了一些性能问题。所以我们让他们为我们导出跟踪。呃，获取一个tarball，交给我们的随叫随到工程师，他与 **Codex** 合作，出色地构建了这个漂亮的本地开发工具 **Nex.js** 应用程序，你可以拖放parall，它会可视化整个跟踪。呃，它非常棒。花了一个下午，但所有这些都不是必需的，因为你只需启动 **Codex**，给它tarball，然后问同样的事情，就能立即得到响应。所以，从某种意义上说，优化人类可读的调试过程是错误的。它不必要地让人类介入循环，而他本可以只是让 **Codex** 花5分钟进行处理，就能得到相同的结果。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: We had deployed our app to the first dozen users internally uh had some performance issues. So we asked them to export a trace for us. Uh get a tarball, gave it to our on call engineer and he did a fantastic job of working with **Codex** to build this beautiful local dev tool nex.js app that you drag and drop the parall in and it visualizes the entire trace. Uh it's fantastic. Took an afternoon, but none of this was necessary because you could just spin up **Codex** and give it the tarball and ask the same thing and get the response immediately. So in a way optimizing for human legibility of that debugging process was wrong. It kept him in the loop unnecessarily when instead he could have just like **Codex** cooked for 5 minutes and gotten the same.

</details>

**主持人**: 是的。你必须对抗你的本能，比如“我们以前就是这么做的”或者“我以前会这样解决它”。

<details>
<summary>Original English</summary>

**主持人**: Yeah. You have to fight your instincts here of like this is how we used to do it or this is how I I would have used to solve it.

</details>

**Ryan Lopopolo**: 是的。在这个本地的可观察性堆栈中，当然你可以部署 **Jaeger** 来可视化跟踪，但我不会期望一开始就查看跟踪，因为我不会编写代码来修复它们。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. in this in this local uh observability stack like sure you can def deploy Jerger to visualize the traces but I wouldn't expect to be looking at the traces in the first place because I'm not going to write the code to fix them.

</details>

### Symphony：去中心化软件共享

**主持人**: 是的。我的意思是，所以基本上需要有这种内部堆栈，并拥有整个循环。我认为这已经非常明确了，嗯，听起来你未来可能会分享更多这方面的信息，对吧？

<details>
<summary>Original English</summary>

**主持人**: Yeah. I mean so basically there needs to be like this kind of house stack and owning the whole loop. I think that that is very well established and uh it sounds like you might be like sharing more about that in the future, right?

</details>

**Ryan Lopopolo**: 是的。呃，我想我们很高兴这样做。我们稍后会谈论 **Symphony**，但就像我们分发它的方式一样，它是一个规范（Spec），我想人们在Twitter上称之为“幽灵库”（ghost libraries）。这真是一个很酷的名字。嗯，这确实意味着与世界共享软件变得便宜得多，对吧？你定义一个规范，你如何构建你自己的规范，尽可能详细，以便编码智能体能够本地重新组装它。这里的工作流程非常非常酷。就像我们已经把我们专有仓库中存在的所有脚手架都拿出来了，启动了一个新的仓库，让 **Codex** 以我们仓库作为参考，编写规范。我们告诉它，启动一个T-mox，生成一个断开连接的 **Codex** 来实现规范，等待它完成，生成另一个 **Codex** 和另一个T-mox来审查规范或审查与上游相比的实现，并更新规范，使其分歧更小。然后你就一遍又一遍地循环，Ralph风格，直到你得到一个能够高保真地再现现有系统的规范。这太棒了。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Uh I think we're excited to do so. We're gonna talk about **Symphony** in a little bit, but like the way we distribute it it as a spec, which I think folks are calling ghost libraries on Twitter. Like this is like a such a cool name. Um it does mean it becomes much cheaper to share software with the world, right? You define a spec how you could build your own specifying as much as is required for a coding agent to reassemble it locally. The flow here is very very cool. Like we have taken all the scaffolding that has existed in our proprietary repo, spun up a new one, ask **Codex** with our repo as a reference, write the spec. We tell it, spin up a T-mox, spawn a disconnected **Codex** to implement the spec, wait for it to be done, spawn another **Codex** and another T-Mox to review the spec or review the implementation compared to upstream and update the spec so it diverges less. And then you just loop over and over and over. Ralph style until you get a spec that is with high fidelity able to reproduce the system as it is. It's fantastic and

</details>

**主持人**: 你基本上没有在其中添加任何你的人为偏见，对吧？就像很多时候人们会写一个规范，然后说：“好吧，我认为应该这样做。”你会即兴发挥一些东西，但智能体本可以处理它。你仍然在某种意义上进行脚手架（Scaffolding），对吧？我希望它这样做。它能更好地确定那个规范。

<details>
<summary>Original English</summary>

**主持人**: and you're basically you're not really adding any of your human bias in there, right? Like a lot of times people will write a spec and be like okay I think it should be done this way and you'll you'll riff on something and it's like no that agent could have just handled it. Like you're still scaffolding in a sense, right? I want it done this way. It can determine that spec better better.

</details>

**Ryan Lopopolo**: 没错。没错。我的一部分，你知道，我最近一直在做很多评估（Eval）工作，我的一部分在想，一个智能体能否产生一个它无法解决的规范？也就是说，它是否总是能够想象它能做到的事情？或者你能想象它不可能做到的事情吗？我认为对于 **Symphony**，我们有一个轴线，对吧？你有容易或困难，或已建立或新的事物，对吧？我认为困难和新的事物仍然需要人类的驱动。但我想其他象限在有正确的脚手架和正确的驱动智能体完成任务的东西的情况下，基本上已经解决了。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's right. That's right. Part of me uh you know I've been working a lot on eval recently and part of me is wondering if an agent can produce a spec that it cannot solve like is it always capable of things that it can imagine or can you imagine things that it is impossible to do. I think with **Symphony** we there's like this uh there's this axis right where you have things that are easy or hard or established or new right and I think things that are hard and new is still something that uh the models need humans yeah drive but I think those other quadrants are largely solved given the right scaffold and the right thing that's going to drive the agent to completion

</details>

**主持人**: 真是太疯狂了，它居然解决了。

<details>
<summary>Original English</summary>

**主持人**: it's crazy that it's solved

</details>

**Ryan Lopopolo**: 但这意味着人类，那些时间有限、注意力有限的人，可以专注于最困难的工作，对吧？比如那些完全是空白领域的问题，或者那些最深层次的重构，你不知道接口的正确形状是什么。这就是我想投入时间的地方，因为它让我为下一个规模级别做好了准备。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: but it it means that the humans the ones with limited time and attention get to work on the hardest stuff, right? Like the problems where it's pure white space out in front or like the deepest refactorings where you don't know what the proper shape of the interfaces are. And this is where I want to spend my time because it lets me set up for the next level of scale.

</details>

**主持人**: 是的。是的。太棒了。嗯，让我们介绍一下 **Symphony**。我想我们一直时不时地提到它。嗯，**Elixir**，一个有趣的选择。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. Amazing. Uh let's let's introduce **Symphony**. I think we've been mentioning it uh every now and then. Uh **Elixir**, interesting option.

</details>

**Ryan Lopopolo**: 是的。是的。再一次，就像 **Elixir** 在这里的表现仅仅是一种派生。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah. And again like the the the the **elixir** manifestation here is is just a derivative.

</details>

**主持人**: 是模型选择的吗？

<details>
<summary>Original English</summary>

**主持人**: Is it a model chosen?

</details>

**Ryan Lopopolo**: 嗯，是的。是的。它之所以选择它，是因为进程监督和Gen Server非常适合我们在这里进行的进程编排类型。对。你基本上是在为每个正在执行的任务启动小型守护进程，并驱动它完成。这意味着模型通过使用 **Elixir** 和Beam获得了大量免费的好处。我的意思是，我必须去上一门关于Beam和 **Elixir** 的速成课，我认为大多数人并没有在这种并发规模下运行，你不需要它，但它是一个很好的可恢复性心智模型以及所有这些东西，这些都是我关心的事情。嗯，但告诉我 **Symphony** 的故事，它的起源故事，你用它做什么？它是如何形成的？以及你没有走过的任何废弃路径？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Uh yeah. Yeah. And it chose that because the process supervision and the gen servers are super amendable to the type of process orchestration that we're doing here. Right. You are essentially spinning up little dammons for every task that is in execution and driving it to completion. Which means the model gets a ton of stuff for free by using **Elixir** and the beam. I mean I I had to go do a crash course in Beam and **Elixir** and I think most people are not operating at that scale of concurrency where you need that but it is a good mental model of resumability and all those things and these are things I care about. Uh but tell me the story the origin story of **Symphony** uh what do you use it for? Is this how did it form and maybe any abandoned paths that you didn't take?

</details>

**主持人**: 在12月底，我们大约每个工程师每天提交3.5个PR。

<details>
<summary>Original English</summary>

**主持人**: At the end of December uh we were at about three and a half PRs per engineer per day.

</details>

**Ryan Lopopolo**: 这在 **GPT-5.2** 在一月初发布之前。每个人从假期回来，只有 **GPT-5.2**，仓库中没有其他工作。我们每个工程师每天提交5到10个PR。就像我不知道你们怎么样，但那样不断切换非常累人。就像我一天结束时完全筋疲力尽。所以再一次，人类把时间花在哪里了？他们把时间花在。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: This was before **5.2** came out in the beginning of January. Everyone gets back from holiday with **5.2** and no other work on the repository. We were up in the five to 10 PRs per day per engineer. And like I don't know about y'all, but like it's very taxing to constantly be switching like that. Like I was pretty tapped out at the end of the day. So again, where are the humans spending their time? They're spending their time

</details>

**主持人**: 在所有这些活跃的T-Mo面板之间进行上下文切换，以推动智能体前进。所以让我们再次构建一些东西来将我们自己从循环中移除。嗯，这就是我们这里的狂热冲刺适配器所做的，它找到了一个方法来消除人类坐在终端前的需要。所以，大量的开发盒子实验，你知道，自动启动智能体，就像这看起来是一个很棒的最终状态，我的生活就是海滩。我每天打开L两次，嗯，你知道，对这些事情说“是”或“否”。

<details>
<summary>Original English</summary>

**主持人**: context switching between all these active T-Mo panes to drive the agent forward. So let's again build something to remove ourselves from the loop. And uh this is what uh frantic uh sprint adapter here to find a way to remove the need for the human to sit in front of their terminal. So lot of experimentation with dev boxes and you know automatically spinning up agents like it seems like a fantastic end state here where my life is beach. I open l twice a day and uh you know say yes no to these things and

</details>

**Ryan Lopopolo**: 这又是一个非常非常有趣的构建工作的方式，因为我对延迟变得不那么敏感了。我对代码的依恋程度也大大降低了。就像我对实际的创作体验几乎没有投入。所以如果它是垃圾，我可以把它扔掉，不用太在意。在 **Symphony** 中，有一个“返工”（rework）状态，一旦PR被提出并升级到人类进行审查，它应该是一个廉价的审查，对吧？它要么可以合并，要么不可以。如果不行，你就把它移到返工。 **Elixir** 服务将完全清空整个工作树和PR，然后从头开始。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: this is again a super super interesting framing for how the work is done because I become more latency insensitive. I have way less attachment to the code as this is written. Like I've had close to zero investment in the actual authorship experience. So if it's garbage, I can just throw it away and not care too much about it. In **Symphony**, there's this like rework state where once the PR is proposed and it's escalated to the human for review, it should be a cheap review, right? It is either mergeable or it is not. And if it's not, you move it to rework. the **elixir** service will completely trash the entire work tree and PR and start it again from scratch.

</details>

**主持人**: 这就是再次提供机会，问“为什么它是垃圾？”对吧？智能体做了什么？

<details>
<summary>主持人**: And this is that opportunity again to say why was it trash, right? What did the agent do that was

</details>

**Ryan Lopopolo**: 在将票据再次推进之前修复它？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: fix that before moving the ticket to progress again?

</details>

**主持人**: 是的。为什么这不在 **Codex** 应用中？我想是你们领先于 **Codex** 应用，我猜。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Why is this not in **Codex** app? I guess it's you guys are you guys are ahead of **Codex** app, I guess.

</details>

**Ryan Lopopolo**: 是的。所以团队的工作方式基本上是尽可能地“AI优先”，并超前发展，我们所做的很多事情都融入了我们现有的许多产品中，比如我们与 **Codex** 团队进行了深入协商，才有了 **Codex** 应用的存在，才有了 **Codex** 能够使用的技能（Skills），这样我们就不必自己动手制作自动化功能，所有的自动化重构智能体就不必是手工编写的控制循环。以某种方式脱离 **Frontier** 和 **Codex** 的产品开发，并快速找出什么有效，然后找到可扩展的东西并广泛部署，这真的非常棒。这是一种非常有趣的操作方式。它当然是混乱的。我经常会忘记代码的实际状态，因为我没有参与循环，对吧？呃，有一次我们通过MCP将Playwright直接连接到 **Electron** 应用。我对MCP持悲观态度，因为Harness会强制将所有令牌注入上下文，而我对此没有发言权。呃，它们会干扰自动压缩。呃，智能体可能会忘记如何使用工具。在Playwright中，我可能只需要调用三个方法。所以我为很多东西付出了代价。有人启动了一个本地守护进程，它启动Playwright并暴露了一个微小的shim CLI来驱动它。我完全不知道这发生了，因为对我来说，我运行 **Codex**，它就能变得更好。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. So the way the team has been working is basically to be as AI pill as possible and spread ahead and a lot of the things we have worked on have fallen out into a lot of the products that we have like we were in deep consultation with the **Codex** team to have the **Codex** app be a thing that exists right to have skills be a thing that **Codex** is able to use so we didn't have to roll our own to put automations into the product so all of or automatic refactoring agents didn't have to be these handrolled control loops. It has been really fantastic to be in a way unanchored to the product development of **Frontier** and **Codex** and just very quickly try to figure out what works and then later find the scalable thing that can be deployed widely. It's been a very fun way to operate. It's certainly chaotic. I have lost track very often of what the actual state of the code looks like because I'm not in the loop, right? Uh there was one point where we had wired **Playwright** directly up to the **Electron** app uh with MCP. MCPs I'm pretty bearish on because the harness forcibly injects all those tokens in the context and I don't really get a say over it. Uh they mess with autocompaction. Uh the agent can forget how to use the tool. There's probably only like what three calls in **Playwright** that I actually ever want to use. So I pay the cost for a ton of things. Somebody vibed a local Damon that boots **Playwright** and exposes a tiny little shim CLI to drive it. And I had zero idea that this had occurred because to me I run **Codex** and it's able to you know get better.

</details>

**主持人**: 是的。就像，呃，完全不知道这一点。所以我们在人类空间中花了大量时间进行同步的知识共享。我们每天站立会议长达45分钟，因为我们几乎必须将当前状态的理解传播出去。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Like uh like no knowledge of this at all. So we have had like in human space uh to spend a lot of time doing synchronous knowledge sharing. We have a daily standup that's 45 minutes long because we almost have to fan out the understanding of the current state.

</details>

**Ryan Lopopolo**: 是的，我本来想说这对于单个人的多智能体来说是好事，但多人多智能体则完全是政治上的爆发式增长。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah, I was going to say like this is good for a single human multi- aent but multihuman multi- aent is a whole like pol like explosion of stuff.

</details>

**主持人**: 是的。这正是我们应用程序中拥有如此严格的10000名工程师级别架构的根本原因，因为我们必须找到方法来划分空间，这样人们才不会相互践踏。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And that this is fundamentally why we have such a rigid like 10,000 engineer level architecture in the app because we have to find ways to carve up the space so people are not trampling on each other.

</details>

**Ryan Lopopolo**: 抱歉，我不明白10000这个数字。呃，我错过了什么吗？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Sorry, I don't I don't get the 10,000 thing. Uh did I miss that?

</details>

**主持人**: 仓库的结构就像500个NPM包。呃，它就像你认为一个七人团队正常的架构一样。但是如果每个人实际上是10到50人，那么像深度分解、分片和正确的接口边界这样的数字就更有意义了。

<details>
<summary>Original English</summary>

**主持人**: The structure of the repository is like 500 mpm packages. Uh it's like architecture to the access for what you would consider I think normal for a seven person team. But if every person is actually like 10 to 50 then the like numbers on like being super super deep into decomposition and sharding and like proper interface boundaries make a lot more sense

</details>

**Ryan Lopopolo**: 对我来说，这就是为什么我谈论微前端，你知道NX来自那个世界，但很酷，只是回到这一点，我不知道你是否有其他，你知道，关于编排这么多工作的想法，这足够了吗？这有没有什么顿悟时刻？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: right to me that's why I talked about micro front ends and you know NX is from that world but cool just coming back to to this like I don't know if you have other you know thoughts on orchestrating so much work going through this is this enough is this like any aha moments

</details>

**主持人**: 会很有趣，看看。好吧，所以现在你选择 **Linear** 作为你的问题追踪器，对吧？就像。

<details>
<summary>Original English</summary>

**主持人**: it'll be interesting to see like where Okay, so right now you pick **Linear** as your issue tracker, right? Like

</details>

**Ryan Lopopolo**: 还是它实际上是 **Linear**？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: or it's like a is it is it actually linear?

</details>

**主持人**: 这实际上是 **Linear**。

<details>
<summary>Original English</summary>

**主持人**: This is actually **Linear**.

</details>

**Ryan Lopopolo**: 哦，那是 **Linear**。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Oh, that's **Linear**.

</details>

**主持人**: 是 **Linear**。

<details>
<summary>Original English</summary>

**主持人**: It's **Linear**.

</details>

**Ryan Lopopolo**: 哦，我从来没看过视频。我不得不下载演示视频来运行，但是。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Oh, I I never look at the video. The demo video I had to download to run, but

</details>

**主持人**: 是的。所以我，因为我是 **Slack** 的狂热用户，但就像，是的，**Linear** 也非常好。是的。

<details>
<summary>Original English</summary>

**主持人**: yeah. So I I cuz I'm a **Slack** maxi, but like Yeah, **Linear** is also really good. Yes,

</details>

**Ryan Lopopolo**: 我们确实大量使用 **Slack**。我们，嗯，我们触发 **Codex** 来做所有这些低复杂度的修复，这些修复会将知识同步到仓库中。这非常便宜。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: we do make a good use of **Slack**. We um we fire off uh **Codex** to do all these lowlexity fixups, the things that like sync that knowledge into the repository. It's super cheap.

</details>

**主持人**: 是的。在 **Codex** 中做。

<details>
<summary>Original English</summary>

**主持人**: Yeah. do it in **Codex**.

</details>

**Ryan Lopopolo**: 我最大的建议是 **OpenAI** 需要构建 **Slack**，对吧？你需要拥有 **Slack** 构建，才能将其转化为。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: My biggest plug is **OpenAI** needs to build **slack**, right? You need to own **slack** builds to turn this into

</details>

**主持人**: 我，我确实读过。是的。嗯。

<details>
<summary>Original English</summary>

**主持人**: I I did I did read it. Yeah. Um

</details>

**Ryan Lopopolo**: 我会说，如果我们认为这些智能体要做有经济价值的工作，这就像是使命，对吧？我们希望AI广泛部署，做有经济价值的工作。那么我们需要找到方法，让它们自然地与人类协作，这意味着协作工具我认为是一个值得探索的有趣空间。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I would say that if we think that we want these agents to do economically valuable work, which is like this is the mission, right? We want AI to be deployed widely to do economically valuable work. Then we need to find ways for them to naturally collaborate with humans which means collaboration tooling I think is an interesting space to explore.

</details>

**主持人**: 是的，完全正确。是的。**GitHub**、**Slack**、**Linear**。是的，这有点是我的想法，比如 **Codex** 现在已经启动了 **Codex** 模型，然后是CLI，现在有了一个应用程序，应用程序可以让我并行启动多个 **Codex** 实例，但是 **Codex** 还没有很好的团队协作功能，对吧？而且看起来你的团队在发布产品方面有一些发言权，对吧？所以，就像你和他们谈过，**Codex** 就出现了。如果你正在处理那些你可能不会关注的东西，比如，你希望其他人构建什么？那些将生产力提高5倍、50倍的人，应该构建非常适合他们工作流程、团队的利基产品吗？它应该更通用，以便其他人可以采用吗？是否存在一个利基市场？就像，因为一部分原因就是，好吧，一切都只是内部工具吗？我们是否拥有一切都按照自己的方式进行？就像我们团队的运作方式有我们自己的沟通方式，或者，你知道，有没有更广泛的方式来做？它是不是像一个问题追踪器？如果你想就此发表一些看法。

<details>
<summary>Original English</summary>

**主持人**: Yeah totally. Yeah. **GitHub** **Slack** **Linear**. Yeah, that was kind of my thing like okay where do we see right now **Codex** has started **Codex** model then CLI now there's an app app can let me shoot off multiple CEXes in parallel but there's no great team collaboration for **Codex** right and it seems like your team had some say into what comes out right so like you talked to them **Codex** kind of was a thing from there if you guys are on the bound stuff that like you know you might not focus on but like what do you expect other people to be building right so people that are like 5x 50xing should you build stuff that's like very niche for your workflow, for your team. Should it be more general so other people can adopt it? Is there a niche there? Like because because part of it is just like, okay, is everything just internal tooling? Do we have everything our own way? Like the way our team operates has our own ways that we like to communicate or you know, is there a broader way to do it? Is it is it something like a issue tracker? Just thoughts if you want to riff on that.

</details>

### 智能体行为的优化与可观察性

**Ryan Lopopolo**: 我认为有待确定，我们还没有以一种通用的方式解决这个问题。我确实认为，在使代码和流程尽可能一致方面存在杠杆作用。如果你认为代码是上下文，代码是提示，那么从智能体行为的角度来看，最好能够查看XYZ目录中的一个包，而无需深入到ABC目录，因为它们具有相同的结构，使用相同的语言，内部具有相同的模式。这种相同的杠杆作用来自于对一套单一技能的统一，你将每个工程师的品味都倾注其中，以确保智能体的效率。所以，比如在我们的代码库中，我们只有六个技能。就是这样。如果软件开发循环的某些部分没有被覆盖，我们首先尝试将其编码到现有设置技能之一中。这意味着我们可以更便宜地改变智能体行为，而不是改变人类驱动程序的行为。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I think TBD like we have not figured this out in a general way. I do think that there is leverage to be had in making the code and the processes as much the same as possible. If you think that code is context, code is prompts, it's better from the agent behavior perspective to be able to look in a package in directory XYZ and it not to have to page so deeply into directory ABC because they have the same structure, use the same language, they have the same patterns internally. And that same like leverage comes from aligning on a single set of skills that you're pouring every engineer's taste into to make sure that the agent is effective. So like in our codebase, we have I think six skills. That's it. And if some part of the software development loop is not being covered, our first attempt is to encode it in one of the existing setup skills. Which means that we can change the agent behavior more cheaply than changing the human driver behavior.

</details>

**主持人**: 是的。你有没有尝试过让智能体改变自己的行为？

<details>
<summary>Original English</summary>

**主持人**: Yeah. Have you ever you experimented with agents changing their own behavior?

</details>

**Ryan Lopopolo**: 我们有。呃，是的。或者父智能体改变子智能体，你知道，行为或者类似的东西。我们有一些技能蒸馏（Skill Distillation）的功能。嗯，例如，你可以用 **Codex** 做一件很巧妙的事情，就是让它指向自己的会话日志，然后问它。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: We do. Uh yes. Or parent agent changing a sub agent's you know behavior or something like that. We have some bits for skill distillation. Um, so for example, there's one neat thing you can do with **Codex** which is just point it at its own session logs to ask it to

</details>

**主持人**: 告诉你如何更好地使用工具。这就像。自省，让它做事情。

<details>
<summary>Original English</summary>

**主持人**: tell you how you can use the tool better. It's like introspection ask it to do things.

</details>

**Ryan Lopopolo**: 我如何更好地使用这个会话？我应该拥有哪些技能？是的，我喜欢修改“你可以做事情”的方式，就像“你可以让智能体做事情”。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: How can I use this session better? What skills should I have? Yeah, I like the modification of you can do just do things to like you can just ask agent to do things.

</details>

**主持人**: 是的，你可以直接用 **Codex** 做事情。这，这就像一个，这就像我们有一个傻傻的表情符号。你可以直接用 **Codex** 做事情。你可以直接提示。呃，我们生活在一个真正辉煌的未来。但就像，好吧，你可以一对一地做，但我们实际上正在将这些数据吸收到整个团队的Blob存储中，每天运行智能体循环，以找出作为一个团队，我们可以在哪里做得更好，以及如何将其反映回仓库中。是的。尽管每个人都免费受益于其他人的行为。PR评论也是如此，对吧？这些都是反馈，意味着所编写的代码偏离了好的标准。一个PR评论，一个失败的构建，这些都是信号，意味着在某个时刻，智能体缺少上下文。我们必须找出如何吸取它，并将其放回仓库中。

<details>
<summary>Original English</summary>

**主持人**: Yeah, you can just **Codex** things. This is this is like a this is like a silly emoji that we have. You can just **Codex** things. You can just prompt things. Uh it's really glorious future we live in. But like okay, you can do that oneonone, but like we're actually slurping these up for the entire team into blob storage and running agent loops over them every day to figure out where as a team can we do better and how do we reflect that back into the repository. Yeah. Though everybody benefits from everybody else's behavior for free. Same for like PR comments, right? These are all feedback that means the code as written deviated from what was good. A PR comment, a failed build, these are all signals that mean at some point the agent was missing context. We got to figure out how to slurp it up and put it back in the repo.

</details>

**Ryan Lopopolo**: 顺便说一句，我正是这样做的。我使用云代码进行知识工作时。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: By the way, I do this exactly right. I used when I use uh cloud code for knowledge work.

</details>

**主持人**: 云代码工作就像一个不错的产品，对吧？我想你会同意的。我总是让它告诉我下次如何做得更好。

<details>
<summary>Original English</summary>

**主持人**: Cloud code work is like a nice product, right? I think you would agree. I always have it tell me what do I do better next time,

</details>

**Ryan Lopopolo**: 对吧？这就是元编程反射。所以几乎可以认为，在 **Symphony** 中你有六个反射提取层。几乎就像零层一样。所以六个层是策略、配置、协调、执行、集成、可观察性。我们已经谈到了其中几个，但零层是关于“我们工作得好吗？我们能改进我们的工作方式吗？我能修改我的工作流程MD吗？”或者其他什么。我不知道。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: right? And that's the meta programming reflection thing. So almost think like you have six reflection extraction levels in **Symphony**. Almost like the the zero layer. So the six levels are policy, configuration, coordination, execution, integration, observability. We've talked about a couple of these, but the zero layer is like the okay well are we working well? Can we can we improve how we work? Like can I modify my own workflow MD or something? I don't know.

</details>

**主持人**: 是的，当然。是的，你当然可以。嗯，就像这个东西也可以自己开票，因为我们给了它完全的访问权限。

<details>
<summary>Original English</summary>

**主持人**: Yeah, of course. Yeah, of course you can. Um, like this thing is also able to cut its own tickets because we give it full access.

</details>

**Ryan Lopopolo**: 是的。让它开一个票，让它开票。你可以在票据中写上你希望它在后续工作中提交。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Make it a ticket to have it cut tickets. You can put in the ticket that you expected to file it on followup work.

</details>

**主持人**: 自我修改。是的。

<details>
<summary>Original English</summary>

**主持人**: Self modifying. Yeah.

</details>

**Ryan Lopopolo**: 是的。不要把智能体关在盒子里。给智能体完全访问它的领域。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Put don't put the agent in a box. Give give the agent full accessibility over his domain.

</details>

**主持人**: 当你说“不要把智能体关在盒子里”时，我产生了心理反应。所以我想你应该把它关在盒子里。只是你给了盒子它需要的一切。

<details>
<summary>Original English</summary>

**主持人**: I had a mental reaction when you said don't put the agent in a box. So I think you should put it in a box. Like it's just that you're giving the box everything it needs.

</details>

**Ryan Lopopolo**: 是的。上下文和工具。对。但是作为开发人员，我们习惯于调用不同的系统。但在这里，你使用开源的东西，比如 **Prometheus**，无论什么，你都在本地运行它，这样你就可以拥有完整的循环。对。我假设。是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Context and tools. Right. But we're like as developers we're used to calling out to different systems. But here you use the open source things like the **Prometheus** whatever and you run it locally so that you can have the full loop. Right. I I assume. Yep.

</details>

**主持人**: 没错。嗯。

<details>
<summary>Original English</summary>

**主持人**: Right. Um

</details>

**Ryan Lopopolo**: 我认为，我认为，就像你想要最小化云依赖一样。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I think I think like you want to minimize cloud cloud dependencies.

</details>

**主持人**: 你还想确保你考虑智能体可以访问什么，对吧？它能看到什么？它是否回到循环中，就像从最基本的意义上说，你让它看到自己的调用跟踪。呃，它可以确定它在哪里出了问题，对吧？但你是否将其反馈回去？所以，你知道，只是最基本的层面，比如你想要准确地看到输入输出。比如，智能体能否访问正在输出的东西，对吧？它可以在很多方面自我改进。

<details>
<summary>Original English</summary>

**主持人**: You also want to make sure that you think about what the agent has access to, right? Like what does it see? Does it go back into the loop like from the most basic sense of uh you let it see its own like calls traces. Uh it can determine where it went wrong, right? But are you feeding that back in? So, you know, just the most basic level of like you want to see exactly what's input output. Like, does the agent have access to what is being outputed, right? It can self-improve a lot of these things.

</details>

**Ryan Lopopolo**: 都是文本，对吧？我的工作是找出将文本从一个智能体传递到另一个智能体的方法。嗯。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: It's all text, right? My job is to figure out ways to funnel text from one agent to the other. Um,

</details>

**主持人**: 这太奇怪了。就像，你知道，很久以前，在这波AI浪潮刚开始的时候，就像，呃，Andre说，你知道，英语是最热门的新编程语言，它就在这里。它就在这里。是的。这些功能。是的，很多，好吧，很多软件，很多东西都有图形用户界面，它是为人设计的，呃，你知道，我们正在看到CLI的演变，适用于所有东西，对吧？所有工具都有CLI，你可以很好地使用它们，但你知道，我们是否能获得良好的视觉，良好的小沙盒，就像现在这是一种非常有效的方式，模型喜欢使用工具，它们喜欢基于它们，它们喜欢阅读文本，所以给它一个CLI，让它自由发挥，这适用于所有东西。

<details>
<summary>Original English</summary>

**主持人**: it's so strange. Like, you know, like way back at the start of this whole AI wave, like uh Andre was like, you know, English is the hottest new programming language is it's here. It's here. Yeah. The features. Yeah, a lot of okay like a lot of software a lot of stuff there's a guey it's made for the human uh you know we're seeing the the evolution of CLI for everything right all tools have CLI your can use them well but you know do we get good vision do we get good little sandboxes like right now it's a really effective way right models love to use tools they love to bass they love to read through text so slap a CLI let it let it go loose that works for everything

</details>

**Ryan Lopopolo**: 是的，是的，是的，我们还一直在将非文本的东西适配成那种形状，以便，呃，在某些方面改进模型行为，对吧？就像我们希望智能体能够看到UI。智能体不像我们那样感知视觉，对吧？就像它们看不到一个红色的盒子，它们看到的是红色盒子按钮，对吧？它们在潜在空间中看到这些东西。呃，所以如果我们想要。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: that does yeah yeah yeah we've also been adapting non textual things to that shape in order to uh improve uh model behavior in some ways, right? Like we want the agent to be able to see the UI. Agents do not perceive visually in the same way that we do, right? Like they don't see a red box, they see red box button, right? They see these things in latent space. Uh so if we want

</details>

**主持人**: 是的。是的。我们有一个东西，每次他去太空都会响。叮。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. We have a thing that goes off every time he goes to space. Ding.

</details>

**Ryan Lopopolo**: 无论如何，嗯，如果我们真的想让它看到布局，那么将图像栅格化以询问并将其输入给智能体几乎更容易。呃，而且没有理由你不能同时做这两件事，对吧？就像进一步完善模型感知它正在操作的物体的方式一样。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Anyway, um if we want to actually like make it see the layout, it's almost easier to rasterize that image to ask and feed it in to the agent. Uh and there's no reason you can't do both, right? To like further refine how the model perceives the object it's manipulating.

</details>

### Symphony的协调层与领域适配

**主持人**: 酷。呃，我们能，你想再谈谈这些层中的哪几个可能需要更多的自省，或者你个人对此有热情？我得说，这里的协调层是一个很难搞定的部分。

<details>
<summary>Original English</summary>

**主持人**: Cool. Uh could we you want to talk about a couple more of these layers that might bear more introspection or that you have personal passion for? I will say that the coordination layer here was a really tricky piece to get right.

</details>

**Ryan Lopopolo**: 让我们来做。是的，我完全支持。这正是 **Temporal** 的核心。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Let's do it. Yeah, I'm all about that. And this is **Temporal**'s uh core core thing.

</details>

**主持人**: 这就是当我们把规范（Spec）变成 **Elixir** 的时候，模型会走捷径，对吧？就像它会想：“哦，我有很多原语可以使用，在这个可爱的运行时中，它有原生的进程监督。”呃，我认为这是一种巧妙的方式，可以将规范转化为更可实现的东西，通过做出自然地映射到领域的选择，对吧？就像你一样。

<details>
<summary>Original English</summary>

**主持人**: This is where when we turn the spec into **elixir** where like the model takes a shortcut, right? Like it's like, oh, I have all these primitives that I can make use of in this lovely runtime that has native process supervision. uh which is I think kind of a neat way to have taken the spec and like made it more achievable by making choices that naturally map the domain, right? In the same way that like you would

</details>

**Ryan Lopopolo**: 如果你在做全栈Web开发，更喜欢有一个TypeScript模型仓库，对吧？因为。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: prefer to have a TypeScript model repo if you are doing full stack web development, right? Because

</details>

**主持人**: 跨前端和后端共享类型的能力大大降低了复杂性。呃，因为。

<details>
<summary>Original English</summary>

**主持人**: the ability to share types across the front end and back end reduces a lot of complexity. Uh and because

</details>

**Ryan Lopopolo**: 这就是GraphQL曾经的用途。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's what GraphQL used to be.

</details>

**主持人**: 没错。而且。

<details>
<summary>Original English</summary>

**主持人**: That's right. and and

</details>

**Ryan Lopopolo**: 我不知道它是否还活着，但是。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I don't know if it's still alive, but

</details>

**主持人**: 这里没有人为的介入。所以，我的个人编写 **Elixir** 的能力或者不编写 **Elixir** 的能力，并不需要偏离使用正确的工具，这真是太疯狂了。

<details>
<summary>Original English</summary>

**主持人**: no humans in the loop here. So like my own personal ability to write or not write **Elixir** doesn't really have to bias us away from using the right tool for the job, which is just wild.

</details>

**Ryan Lopopolo**: 喜欢它。我喜欢它。是的。我不知道是否有任何语言会因此而比其他语言更挣扎。我觉得每个人都有自己的抽象，这会很有意义，但它可能会更慢。它可能会有更多故障，就像你不得不时不时地重启服务器一样。嗯，我，我不知道。我认为可观察性层（Observability Layer）得到了很好的理解。集成层MCP已经死了。我认为所有这些，就像一个非常有趣的层次结构，可以上下遍历。这是系统上工作的人们理解的通用语言。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Love it. I love it. Yeah. I wonder if any languages struggle more than others because of this. I feel like everyone has their own abstractions that would make sense, but maybe it might be slower. It might be more faulty where like you would have to just kick the server every now and then. Um I I don't know. I think observability layer is really well understood. Integration layer MCP is dead. I think all these like just like a really interesting hierarchy to travel up and down. It's common language for people working on the system to understand.

</details>

**主持人**: 策略（Policy）方面的东西非常酷，对吧？就像，是的，你不需要编写大量代码来确保系统等待CI通过。这是你的机构知识。

<details>
<summary>Original English</summary>

**主持人**: The the policy stuff is really cool, right? Like yeah, you don't really have to build a bunch of code to make sure the system wait for CI to pass. It's your institutional knowledge.

</details>

**Ryan Lopopolo**: 是的，你只需给它 **GH CLI**，并附上一些文本，说明CI必须通过。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah, you just give it the **GH CLI** with some text to say CI has to pass.

</details>

**主持人**: 它使这些系统的维护变得容易得多。

<details>
<summary>Original English</summary>

**主持人**: It makes the maintenance of these systems a lot easier.

</details>

**Ryan Lopopolo**: 你认为CLI维护者需要为智能体做任何特殊的事情，还是保持原样就可以了？因为我不知道当人们创建 **GitHub CLI** 时，他们是否预料到会发生这种情况。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Do you think that like CLI maintainers need to be do anything special for agents or just as is? It's good cuz like I don't think when people made the **GitHub CLI** they anticipated this happening.

</details>

**主持人**: 没错。**GH CLI** 非常棒。它很棒。超级行业。如果你想尝试 `gh repo create` 就像 `gh pull` 然后是拉取请求号，对吧，`gh` 像 `153` 什么的，对吧，然后它，它就像拉取。

<details>
<summary>Original English</summary>

**主持人**: That's correct. The **GH CLI** is fantastic. It's great. Super industry. If you want to go try ghre repo create like gh pull and then pull request number right gh like 153 whatever right and then it it like pulls

</details>

**Ryan Lopopolo**: 基本上我目前与 **GitHub** Web UI的唯一交互就是 `gh pr view-web`，扫一眼差异，然后说：“没问题，发出去。”是的。是的。是的。但是，嗯，CLI之所以好用，是因为它们非常节省令牌（Tokens），而且可以很容易地变得更节省令牌，对吧？就像我相信你们都见过，我去做构建或者Jenkins，然后就得到一堵巨大的构建输出墙，为了解除人类的阻塞，你的开发人员生产力团队几乎肯定会编写一些代码来解析构建日志中的实际异常，并将其贴在页面顶部的一个便签上。你基本上希望CLI也以类似的方式构建，对吧？你希望修补`-silent`到prettier，因为智能体不在乎每个文件是否已经格式化了。它只想知道它是否格式化了，对吧？这样它就可以运行写入命令了。类似地，就像在我们的PNPM分布式脚本运行器中，当我们有一个运行器时，当你做递归时，它会生成一座巨大的文本山，但所有这些都是为了通过测试套件。所以我们最终将所有这些都封装在另一个脚本中。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: basically my only interaction with the **GitHub** web UI at this point is ghpr view-web glance at the diff and be like sure thing send it. Yeah. Yeah. Yeah. But um the CLI are nice cuz they're super token efficient and they can be made more token efficient really easily, right? Like I'm sure you all have seen like I go to build kite or **Jenkins** and I just get this massive wall of build output and in order to unblock the humans your developer productivity team is almost certainly going to write some code that parses the actual exception out of the build logs and sticks it in a sticky note at the top of the page. And you basically want CLIs to be structured in a similar way, right? you're going to want to patch d- silent to prettier because the agent doesn't care that every file was already formatted. It just wants to know it's either formatted or not, right? So they can then go run the write command. Similarly like in our PNPM sort of distributed script runner when we had one when you do d-recursive like it produces a absolute mountain of text but all of that is for passing test suites. So we ended up wrapping all of this in another script

</details>

**主持人**: 抑制。你可以用它来普遍输出测试中失败的部分。是的，你可以将错误管道输送到标准输出。我不知道。好吧，随便。CLI要思考的事情太多了。我以前为我的公司维护一个CLI，就像，是的，这，这就像对我来说非常核心的东西，但你正在取代我的工作。

<details>
<summary>Original English</summary>

**主持人**: to suppress the which you can vibe to generally output the failing parts of the test. Yeah, you could pipe uh errors versus the standard standard out. I don't know. Okay, whatever. Too much too much thinking to have to do the CL. I used to maintain a CLI for my company and like Yeah, this is this is like core very core to my heart, but you're vibing my job.

</details>

**Ryan Lopopolo**: 没错。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's right.

</details>

**主持人**: 酷。还有其他什么吗？我的意思是，这是一个很长的规范。我，我，我很欣赏。就像，它里面有很多强烈的观点。还有其他我们应该强调的事情吗？你知道，我想显然你可以花一整天的时间来研究其中一些，但就像，你知道，我确实认为其中一些有很多细致的地方，或者其中一些你可能想告诉人们，嘿，接受这个，但你知道，要把它变成自己的。

<details>
<summary>Original English</summary>

**主持人**: Cool. Any other things? I mean, this is a long spec. I I I appreciate that. Like, it's it's like got a lot of strong opinions in here. Any other things that we should highlight? You know, I think obviously you can spend the whole day going through some of these, but like you know, I I do think that some of these have a lot of care or some of this you might you might want to tell people, hey, take this, but you know, make it your own.

</details>

**Ryan Lopopolo**: 从根本上说，软件在能够适应其部署环境时会变得更加灵活，对吧？这意味着像 **Linear** 或 **GitHub** 这样的东西，即使在规范中指定，也不是它的必需部分，对吧？就像存在一个更柏拉图式的理想，你可以替换成 **Jira** 或 **Bitbucket**，例如，对吧？但是能够紧密指定。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Fundamentally, software is made more flexible when it's able to adapt to the environment in which it is deployed, right? Which means that things like **Linear** or **GitHub** even are specified within the spec, but not required pieces of it, right? there's like a more platonic ideal of the thing uh that you could swap in like **Jira** or **Bitbucket** for example, right? But being able to tightly specify

</details>

**主持人**: 像ID格式或单个智能体的Ralph循环如何工作这样的东西，基本上意味着你可以快速启动并运行一个完全指定的系统，然后你在后期进行演变。我认为我们从来没有打算让它成为一个你永远无法更改的静态规范，对吧？它更像是一个蓝图，用于启动和运行一些东西。

<details>
<summary>Original English</summary>

**主持人**: things like the ID formats or how the Ralph loop works for the individual agents basically means you can get up and running with a fully specified system quickly that you then evolve later on. I think we never intended for this to be a static spec that you can never change, right? It's more like a blueprint to get something working up and running

</details>

**Ryan Lopopolo**: 然后你可以随心所欲地随意改动。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: for you then to vibe later till your heart's content.

</details>

**主持人**: 你在这里有一些代码和脚本，就像，哦，我的意思是，我认为这是一个非常好的提示（Prompt）。它只是一个非常非常长的提示。

<details>
<summary>Original English</summary>

**主持人**: You have like code and scripts in here where it's like, oh, I mean I I think this is a really good prompt. It's just a very very long prompt.

</details>

**Ryan Lopopolo**: 从根本上说，智能体擅长遵循指令。所以，给它们指令，对吧？它会，你知道，提高结果的可靠性，对吧？就像我们使用 **Symphony** 的方式一样，我们不希望人们在智能体将系统变为现实时监控它。所以，对这些成功标准非常固执己见，非常严格，意味着。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Fundamentally, the agents are good at following instructions. So, give them instructions, right? And it will, you know, improve the reliability of the result, right? Like we much like the way we use **Symphony**, we don't want folks to have to monitor the agent as it is vibing the system into existence. So being very opinionated, very strict around what these success criteria are means that like

</details>

**主持人**: 我们的部署成功率提高了。

<details>
<summary>Original English</summary>

**主持人**: our deployment success rate goes up.

</details>

**Ryan Lopopolo**: 是的。这意味着我们不必为此而开票。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Means we don't have to get tickets on this thing.

</details>

### AI时代的软件可丢弃性与信任

**主持人**: 我认为这一切都回溯到“代码是可丢弃的”，对吧？就像早期当你使用CLI或启动 **Codex** 运行时，它需要两个小时。你可能想监控它，就像，好吧，我正在使用一个工作流。我不想让它走错路。我会把它切断，但，你知道，直接启动所有四个。就像那是 **Codex** 应用中我最喜欢做的事情，对吧？直接4倍运行。没关系。其中一个可能正确，其中一个可能更好。别想太多了。就像我第一个例子可能就是深度研究。当你进行深度研究时，我问它一个关于LLM的问题，它认为这是一个法律问题，花了一个小时，然后回来一份完全跑偏的报告。我当时想，好吧，我得稍微监控一下这个东西。不，不要监控它，你，你希望构建它，让它走正确的路，你不想，你不想坐在那里像保姆一样照看，对吧？你不想像保姆一样照看你的智能体。

<details>
<summary>Original English</summary>

**主持人**: I think it all goes back to that like go to disposable, right? Like early on when you had CLI or you'd kick off a **Codex** run, it would take two hours. you would kind of want to monitor like, okay, I'm in the workflow of just using one. I don't want it to go down the wrong path. I'll cut it off and but you know, just shoot all four. Like that was my favorite thing of the **Codex** app, right? Just 4x it. Like it's okay. One of them will probably be right, one of them might be better. Stop stop overthinking it. Like my my first example was probably like deep research. when you put out deep research and I'd ask it something like I asked it something about LLM it thought it was legal something and spent an hour came back with a report completely off the rails and I was like okay I got to monitor this thing a bit no don't don't monitor it just you you want to build it so that it goes the right way and you don't want to you don't want to sit there and babysit right you don't want to babysit your agents

</details>

**Ryan Lopopolo**: 对于你提出的那个深度研究查询，通过查看糟糕的结果，你可能已经发现你需要稍微调整你的提示，对吧？就像你反馈回代码库中的那个护栏（Guardrail），用于进一步调整智能体执行的提示。类似的概也适用于那里。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: with that deep research query that you made looking at the bad result you probably figured out you needed to tweak your prompt a bit right like that's that guardrail that you fed back into the code base for the ask your prompt to further align the agent's execution. Same sort of concepts apply there too

</details>

**主持人**: 当你谈论的时候，我的意思是客户感觉如何？

<details>
<summary>Original English</summary>

**主持人**: when you talk I mean how are the customers feeling

</details>

**Ryan Lopopolo**: 对于 **Symphony**，呃，我认为我们没有客户，对吧？这是我们向世界发布的东西。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: for **Symphony** uh I I think we have none right this is a thing we have put out into the world

</details>

**主持人**: 我的意思是 **Symphony** 是内部的，对吧？只要你高兴，你就是客户。

<details>
<summary>Original English</summary>

**主持人**: I mean **Symphony** is internal right as long as you're happy you're the customer

</details>

**Ryan Lopopolo**: 没错。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: that's right

</details>

**主持人**: 呃，你知道，外部看法是怎样的？

<details>
<summary>Original English</summary>

**主持人**: uh just you know what's what's the external view

</details>

**Ryan Lopopolo**: 我会说，人们对这种分发软件和思想的方式感到非常兴奋，以便宜的方式。对我们这些用户来说，它再次将生产力提高了5倍。这意味着我认为这里有一些东西，它是一种持久的模式，围绕着将人类从循环中移除，并找出信任输出的方法。对吧？这里共享的视频。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I say folks are very excited about this way of distributing software and ideas in cheap ways. For us as users, it has again pushed the productivity 5x Which means I think there's something here that's like a durable pattern around removing the human from the loop and figuring out ways to like trust the output. Right? The video that is shared here

</details>

**主持人**: 是我们希望编码智能体附加到PR上的那种视频。

<details>
<summary>Original English</summary>

**主持人**: is the same sort of video we would expect the coding agent to attach to the PR

</details>

**Ryan Lopopolo**: 就是这样创建的。你知道，这是在这个系统中建立信任的一部分。对我来说，构建这个东西最酷的地方在于，它更紧密地推动了智能体与你合作成为队友的形象，对吧？我不会像你工作周里处理的那些票据那样在你背后盯着你。我从来不会想这样做。我不会想要你的整个会话在Cursor或Claude Code中的屏幕录像。我希望你做你认为需要做的事情，来说服我代码是好的，并且可以合并。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: that is created. You know that's part of building trust in this system. And that's to me like fundamentally what has been cool about building this is like it more closely pushes that persona of the agent working with you to be like a teammate, right? I I don't shoulder surf you like for the tickets that you work on during the week. I would never think that I would want to do that. I wouldn't want a screen recording of your entire session in cursor or claude code. I would expect you to do what you think you need to do to convince me that the code is good and mergeable

</details>

**主持人**: 并以一种对评论者可读的方式压缩整个轨迹。

<details>
<summary>Original English</summary>

**主持人**: and compress that full trajectory in a way that is legible to me the reviewer.

</details>

**Ryan Lopopolo**: 是的。它只是，呃，你就是可以那样做，因为 **CEX** 绝对会胡搞。这很棒。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Y it's just uh and and you can just do that because **CEX** will absolutely sling some F around. It's great.

</details>

**主持人**: 哦，我的意思是 **FFmpeg** 是老牌的，就像神一样的CLI。

<details>
<summary>Original English</summary>

**主持人**: Oh, I mean EV F ev is the OG like god CLI.

</details>

**Ryan Lopopolo**: 是的。瑞士军刀电锯。我以前常说，呃，**FFmpeg** 的每个标志里都藏着一个SAS微型SAS，我们可以称之为。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Swiss army chainsaw. I used to say uh there's a SAS micro SAS let's call it in every flag in **FFmpeg**.

</details>

**主持人**: 哦，当然。你知道我的意思吗？当然。

<details>
<summary>Original English</summary>

**主持人**: Oh, for sure. You know what I mean? For sure.

</details>

**Ryan Lopopolo**: 就像把它托管成一个服务，给它一个UI。那些不知道 **FFmpeg** 的人会为此付费。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Like just host it as a service, put a UI on it. People who don't know **FFmpeg** will pay for it.

</details>

**主持人**: 当我们第一次实验这个的时候，那种感觉很疯狂，就像坐在电脑前，窗户到处乱跳，被捕获，文件出现在我的桌面上。就像感觉非常未来，有一个东西控制我的电脑，用于实际的生产性使用，对吧？就像我只是在那里，保持它清醒，偶尔晃动一下鼠标。

<details>
<summary>Original English</summary>

**主持人**: When we were first experimenting with this, it was a wild feeling to be at the computer with just like Windows just popping up all over the place and getting captured and files appearing on my desktop. like very much felt like the future to have a a a thing controlling my computer for like actual productive use, right? Like I'm just there keeping it like awake jiggling the mouse every once in a while.

</details>

**Ryan Lopopolo**: 这就是一些办公室职员所做的。他们买一个鼠标抖动器。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's what some office workers do. They buy a mouse jiggler.

</details>

**主持人**: 没错。没错。

<details>
<summary>Original English</summary>

**主持人**: That's right. That's right.

</details>

### Spark模型与未来瓶颈

**Ryan Lopopolo**: 我想问一件事，就像，好吧，当东西这么好，可丢弃，异步启动一堆智能体时。一个问题是，好吧，你总是像一个思维超前的家伙吗？你在哪里看到了Spark？所以 **GPT-5.3** Spark，就像我有很多想要快速更改的想法，我不会打开IDE，我不会做任何事情，但我会说，好吧，修复这个小东西，更改一行，更改一个颜色，Spark非常适合这一点，但就像我仍然是瓶颈吗？你知道，我为什么不让它回去呢？就像随便谈谈，你知道，有没有。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: One thing I wanted to ask so like okay as stuff is so good is disposable async shoot off a bunch of agents. One question is like okay are you always like a extra high thinking guy and where do you see spark so **5.3** spark like there's a lot of me wanting to make quick changes I'm not going to open up ID I'm not going to do anything but I will say okay fix this little thing change a line change a color spark is great for that but like am I still the bottleneck you know like why don't I just let that go back in like just riff on that you know is there

</details>

**主持人**: Spark是一个与你从这些模型中获得的高度推理模型完全不同的模型。你知道。

<details>
<summary>Original English</summary>

**主持人**: spark is such a different model compared to the the extra high level reasoning that you get in these you know

</details>

**Ryan Lopopolo**: 公平地说，对人们来说，它是一个不同的模型，不同的架构，不同的，就像它不支持，它只是。它速度极快。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: to be fair for people it is a different model different architecture different like it doesn't support it it just it's incredibly fast

</details>

**主持人**: 我还没有完全弄清楚如何使用它，呃，说实话，我更快。我正在将它用于我用于高度推理的相同类型的任务，它会在编写一行代码之前完成三次压缩。

<details>
<summary>Original English</summary>

**主持人**: I have not quite figured out how to use it yet uh to be honest I faster I was I was adapting it to the same sorts of tasks I would use x high reasoning for and it would blow through three compactions before writing a line of code

</details>

**Ryan Lopopolo**: 我的意思是，这是 **GPT-5.4** 的另一个大特点，对吧？一百万令牌的上下文，这在智能体领域是巨大的，对吧？就像你可以在压缩之前运行更长时间，你在一个任务上花费的令牌越多，效果就越好。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: and I mean that's another big thing with uh **5.4** for right million coken content which is huge in aentic right like you can just run for longer before you have to compact the more tokens you can spend on a task before compacting like the better you'll do

</details>

**主持人**: 没错。没错。我不知道，呃，如何部署Spark。我认为你的直觉是正确的，就像它非常适合快速构建原型，快速探索想法，做那些文档更新。它对我们来说非常棒，可以将反馈转化为Lint，我们在代码库中已经有很好的 ESLint 基础设施。呃，这些东西它很擅长，它让我们能够快速解除阻塞，做那些像代码库中的抗脆弱修复任务。

<details>
<summary>Original English</summary>

**主持人**: that's right that's right I'm not sure uh how to deploy spark I think your intuition is right that like it's very great for spiking out prototypes exploring ideas quickly doing those documentation updates it is fantastic for us in taking that feedback and transforming it into a lint where we already have good infrastructure for eslints in the codebase. Uh these sorts of things it's great at and it allows us to unblock quickly doing those like antifragile healing tasks in the codebase.

</details>

**Ryan Lopopolo**: 是的，这很有道理。所以你们正在将模型推向极限。卡片模型目前还不能很好地做什么？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah, that makes sense. So you're push you guys are pushing models to the freaking limit. What can card models not do well yet?

</details>

**主持人**: 它们绝对还没有达到能够从新产品创意到原型的地步。

<details>
<summary>Original English</summary>

**主持人**: They're definitely not there on being able to go from new product idea to prototype

</details>

**Ryan Lopopolo**: 一次性。这就是我发现我花大量时间指导的地方，就是将一个全新事物的模拟（Mock）的最终状态转化为一个可玩的（Playable）产品，对吧？想想没有现有屏幕的产品。同样，虽然随着每个模型版本的发布，情况有所改善，但最棘手的重构是我花费最多时间的地方，对吧？那些我干扰最多，那些我现在双击以构建工具来帮助分解单体（Monoliths）之类的事情。这是一种我只期望会变得更好的东西，对吧？在一个月的时间里，我们从低复杂度的任务转向了低复杂度和大任务，在这两个方向上。所以，这意味着不要与模型对赌，对吧？你应该期望它会自己推向更高、更复杂的空间。是的。所以，我们所做的事情对此是健壮的。它基本上意味着我将能够把时间花在其他地方，并找出下一个瓶颈是什么。我。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: single one shot. This is where I find I spend a lot of time steering is translating end state of a mock for a net new thing, right? Think no existing screens into product that is playable with. Similarly, while this has gotten better with each model release, like the gnarliest refactorings are the ones that I spend my most time with, right? The ones where I am interrupting the most, the ones where I am now double clicking to build tooling to help decompose monoliths and things like that. This is a thing I only expect to get better, right? Over the course of a month, we went from the low complexity tasks to like low complexity and big tasks in both these directions. So, this is what it means to not bet against the model, right? You should you should expect that it is going to push itself out into these higher and higher complexity spaces. Yeah. So, the things we do are robust to that. It just basically means I'll be able to spend my time elsewhere and figure out what the next bottleneck is. I

</details>

**主持人**: 我确实认为这也是一种不同类型的任务，对吧？就像 **Codex** 在代码库理解和代码库工作方面非常出色，但是像Lovable、Bolt、Replit这样的公司，它们解决的是一个非常不同的问题，从零到一的脚手架，对吧？一个产品创意，就像有人正在从事这方面的工作，而且模型也在推动像阶跃函数这样的变化，这与你今天看到的软件工程智能体有点不同，对吧？

<details>
<summary>Original English</summary>

**主持人**: I do think it's also a bit of a different type of task, right? Like **Codex** is really good at codebase understanding working with code bases but companies like lovable uh bolt replet they solve a very different problem scaffold of zero to one right idea at a product and it's like there are people working on that and models models are also pushing like step function changes there it's just kind of different than the software engineering agents you see today right

</details>

**Ryan Lopopolo**: 就像我说的，模型对我来说是同构的，呃，唯一不同的是如何将这里的东西放入模型的上下文。对于这些空白项目，我自己并不擅长。呃，这意味着通常在智能体轨迹中，我意识到缺少的部分，这就是为什么我发现我需要进行同步交互，我期望通过正确的Harness和正确的脚手架，能够从我这里提取出这些东西，或者优化可能的空间，对框架的使用非常固执己见，或者设置一个模板，对吧？这些都是为模型提供所有非功能性需求，这些额外的上下文，让它有锚点，避免可能结果的广泛分散。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: like I said the model is isomeorphic to myself uh the only thing that's different is figuring out how to get what's in here into context for the model. And for these whites space sort of projects, I myself I'm just not good at it. uh which means that often over the agent trajectory I realize the bits that were missing which is why I find I need to have the synchronous interaction and I expect with the right harness with the right scaffold that's able to tease that out of me or refine the possible space right to be super opinionated around the frameworks that are deployed or to put a template in place right these are ways to give the model all those non-functional requirements that extra context to anchor on and avoid that wide dispersion of possible outcomes.

</details>

### OpenAI Frontier：企业级AI转型平台

**主持人**: 谢谢你。呃，我想谈谈 **Frontier**。

<details>
<summary>Original English</summary>

**主持人**: Thank you for that. Uh I wanted to talk a little bit about **Frontier**.

</details>

**Ryan Lopopolo**: 是的，当然。呃，总的来说，呃，你们大概一个月前宣布了它。嗯，这里有一些图表，如果它有点像你们的企业产品，这就是我的看法。它是一个产品还是很多产品？我不能谈论这里完整的产品路线图，但我想说的是，**Frontier** 是我们希望通过它实现所有企业的AI转型，从小到大。我们希望通过让部署高度可观察、安全可控、可识别的智能体（Agent）到工作场所来做到这一点，对吧？我们希望它能与你们公司原生的IM堆栈配合使用，我们希望它能插入你们现有的安全工具。我们希望它能够插入你们使用的工作区工具。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah, sure. Uh overall, uh you guys announced it maybe like a month ago. Um and there's there's a few charts in here and there if it's kind of like your enterprise offering is kind of what I view it. Is there one product or is there many? I can't speak to the full product roadmap here but what I can say is that **Frontier** is the platform by which we want to do AI transformation of every enterprise and from big to small and the way we want to do that is by making it easy to deploy highly observable safe control identifiable agents into the workplace right we want it to work with your company native IM stack we want it to plug into the SK uh security tooling that you have. We want it to be able to plug into the workspace tools that you used.

</details>

**主持人**: 所以，你只是要剥离规范（Specs），对吧？

<details>
<summary>Original English</summary>

**主持人**: So, you're just going to be stripping specs, right?

</details>

**Ryan Lopopolo**: 我们期望那里会有一些Harnesss的东西。**Agents SDK** 是其中的核心部分，它使初创公司和企业构建者都能够拥有一个默认可用的Harness，能够利用我们模型的所有最佳功能，从Shell工具到带有文件附件和容器的 **Codex** Harness，以及所有我们知道用于构建高度可靠、复杂智能体的其他东西。我们希望使其变得出色，并使其易于以安全的方式将这些东西组合在一起。例如，对吧？就像 **GPT OSS Safeguard** 模型一样，它有一个非常酷的功能，就是能够与安全规范（Safety Spec）接口。安全规范是企业特有的。我们有责任为这些人找出方法，让他们在其企业中检测智能体，以避免他们特别关心的信息泄露，以了解他们公司内部的代码名称等。因此，提供正确的钩子（Hooks）使平台可定制，但同时也，你知道，对于大多数人来说默认可用，这就是我们正在探索的空间。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: We expect that there will be some harness things there. **Agents SDK** is a core part of this to enable both startup builders as well as enterprise builders to have a works by default harness that is able to use all the best features of our models from the shell tool down to the **Codex** harness with file attachments and containers and all these other things that we know go into building highly reliable complex agents. We want to make that great and we want to make it easy to compose these things together in ways that are safe. For example, right like the **GPT OSS Safeguard** model for example, one thing that's really cool about it is it ships the ability to interface with a safety spec. Safety specs are things that are bespoke to enterprises. We owe it to these folks to figure out ways for them to instrument the agents in their enterprise to avoid excfiltration in the ways they specifically care about to know about their internal company code names these sorts of things. So providing the right hooks to make the platform customizable but also you know mostly working by default for folks is kind of the the space we are trying to explore here.

</details>

**主持人**: 是的。这就像，你知道，像 **Snowflake** 这样的公司就需要这个，对吧？是的。像Brex这样的公司，像 **Stripe** 这样的公司。是的，很有道理。我本来想回到你那里，你知道，我，我，我认为你们的演示视频非常具有启发性。它对我来说，也是一个非常大规模智能体管理的例子。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And this is like you know the **Snowflake**s of the world just need this right. Yeah. Brexites of the world **Stripe**s. Yeah, makes sense. I was going to go back to your, you know, I I I think the demo videos that you guys had was was pretty illustrative. It's kind of like also to me um an example of very large scale agent management.

</details>

**Ryan Lopopolo**: 是的。就像你给人们一个控制仪表板，如果你播放，如果你像播放这些多智能体中的任何一个，你可以深入到单个实例并查看正在发生的事情。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yes. Like you give people a control dashboard that if you play if you like play any one of these like multiple agent things. You can dig down to the individual instance and see what's going on.

</details>

**主持人**: 是的，当然。

<details>
<summary>Original English</summary>

**主持人**: Yes, of course.

</details>

**Ryan Lopopolo**: 但谁是用户呢？是首席执行官、首席技术官、首席信息官，还是类似的人？所以，你知道，至少我在这里的个人观点是，我们正在努力为之构建产品的买家是员工，他们正在有效利用这些智能体，对吧？那将是它们出现的任何界面，它们可以访问的连接器，诸如此类。像这个仪表板这样的东西是为IT、你们的GRC和治理人员、你们的AI创新办公室、你们的安全团队准备的，对吧？你们公司中负责成功部署到员工工作空间，并以安全的方式，符合你们所有法规要求和客户证明等事项的利益相关者。所以它就像冰山一角，在实际的终端之下。是的，你跳跃，就像你在UI中的每一层，就像在智能体方面，深入到提取层，对吧？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: But who's the user? Is it is it like the CEO, the CTO, CIO, something like that? So, you know, at least my personal opinion here, the buyer that we're trying to build product for here is one and employees who are making productive use of these agents, right? That's going to be whatever surfaces they appear in, the connectors they have access to, things like that. Something like this dashboard is for IT, your GRC and government's folks, your AI innovation office, your security team, right? the stakeholders in your company that are responsible for successfully deploying into the spaces where your employees work as well as doing so in a safe way that is consistent with all the regulatory requirements that you have and customer attestations and things like that. So it is kind of a iceberg beneath the actual end. Yeah, you you jump like every I guess layer in the UI is like going down the layer of extraction in terms of the agent, right?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yep.

</details>

**Ryan Lopopolo**: 是的。是的。我认为这很好。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah. I think it's good.

</details>

**主持人**: 是的。深入研究单个智能体轨迹级别的能力将非常强大。

<details>
<summary>Original English</summary>

**主持人**: Yeah. The the ability to dive deep into the individual agent trajectory level is going to be super powerful

</details>

**Ryan Lopopolo**: 不仅是从安全角度，而且对于负责开发技能的人来说也是如此。我们博客中提到的另一件有趣的事情是内部数据智能体（Internal Data Agent），它利用了大量的 **Frontier** 技术，使我们的数据本体对智能体可访问，并理解数据仓库中实际有什么。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: not only for like from like a security perspective but also from like someone who is accountable for developing skills. One thing that was interesting that we also blogged about shipping was uh an internal data agent which uses a lot of the **Frontier** technology in order to make our data ontology accessible to the agent and things like that to understand what's actually in the data warehouse.

</details>

**主持人**: 是的。语义层之类的东西。呃，我曾短暂地参与过那个世界。呃，它解决了吗？我不知道。对于人类来说，就收入是什么达成一致意见实际上非常困难。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Semantic layer type things. Uh I was briefly part of that that world. Uh is it solved? I don't know. It's actually really hard for humans to agree on what revenue is.

</details>

**Ryan Lopopolo**: 是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yes.

</details>

**主持人**: 你知道。

<details>
<summary>Original English</summary>

**主持人**: You know.

</details>

**Ryan Lopopolo**: 是的。什么是活跃用户？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yes. What is what is what is an active user?

</details>

**主持人**: 公司里有大约五名数据科学家定义了这个“黄金”。

<details>
<summary>Original English</summary>

**主持人**: There's like what five data scientists in the company that have defined this golden

</details>

**Ryan Lopopolo**: 他们都不同，是的，而且没有，而且还有内部政治，涉及到归属问题，比如我是营销部门的，我负责这么多，销售部门负责这么多，它们加起来超过100%，我就想，好吧，你们有不同的定义。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: they all different yeah and like no and there's also internal politics as to attribution of like I I'm marketing I'm responsible for this much and sales is responsible for this much and they all add up to more than 100 and I'm like well you guys have different definitions.

</details>

**主持人**: 是的。如果你是一家初创公司，一切都是，你知道。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And if you're a startup everything is a r you know.

</details>

**Ryan Lopopolo**: 所以，所以我想这很酷。哦，你们博客上发过这个。好吧。我没有，我没有看到这个。呃，是的。这是同一件事吗？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: So so I think that's that's cool. Oh you guys blogged about this. Okay. I didn't I didn't see this. Uh yeah. Is this the same thing?

</details>

**主持人**: 我不知道。呃，你指的是这个吗？

<details>
<summary>Original English</summary>

**主持人**: I don't Uh, is this what you're referring to?

</details>

**Ryan Lopopolo**: 嗯，是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Uh, yes.

</details>

**主持人**: 好的。那么，我们会让人们去阅读这篇作为我们数据机构的文章。

<details>
<summary>Original English</summary>

**主持人**: Okay. Well, we'll send people to read this as our data agency.

</details>

**Ryan Lopopolo**: 这个。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: This one.

</details>

**主持人**: 呃，是的。我不知道你有没有什么亮点。我。

<details>
<summary>Original English</summary>

**主持人**: Uh, yeah. I don't know if you you have any highlights. I

</details>

**Ryan Lopopolo**: 不，不，不。我的意思是，总的来说，有很多值得阅读的好东西。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: No, no, no. I mean, in general from the point, a lot of good things to read.

</details>

**主持人**: 是的。是的。有很多作业给人们。呃，不，但就像数据作为反馈层一样。你需要首先解决这个问题，才能关闭产品的反馈循环。没错。所以智能体才能理解，就像人类并不知道这一点。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. Lot lots of homework for people. Uh, no, but like data as the feedback layer. You need to solve this first in order to have the products feedback loop closed. That's right. Like so for the agents to to understand and like this is not something that humans have not know of this like in

</details>

**Ryan Lopopolo**: 这就是你如何构建艺术家，让他们不仅仅是编码，对吧？

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: this is how this is how you build artists that do more than coding right

</details>

**主持人**: 要真正理解你如何经营业务，你必须理解什么是收入，你的客户群是什么，对吧？

<details>
<summary>Original English</summary>

**主持人**: to actually understand how you operate the business you have to understand what revenue is what your customer segments are right

</details>

**Ryan Lopopolo**: 你的产品线是什么，对吧？就像我们在这里描述的，在Harnessing的代码库中，有一件事在核心信念（Core Beliefs）MD中，那就是团队中有谁，我们正在构建什么产品，我们的最终客户是谁，我们的试点客户是谁，以及我们希望在未来12个月内实现什么愿景，所有这些都是构成我们如何构建软件的上下文信息。哦，天哪。所以，我们也要把它提供给智能体。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: what your product lines are right like one thing that's in like looping back to the codebase that we described here for harnessing one thing that's in core beliefs MD is like who's on the team, what product we're building, who our end customers are, who our pilot customers are, what the full vision of what we want to achieve over the next 12 months is like these are all bits of context that inform how we would go about building the software. Oh my god. So, we have to give it to the agent, too.

</details>

**主持人**: 我猜这些东西是相当动态的，而且会随着时间而变化，对吧？就像其中一部分是，它不仅仅是一个大规范。你把它作为一个东西，它会迭代。

<details>
<summary>Original English</summary>

**主持人**: I'm guessing that stuff is like pretty dynamic and it changes over time, too, right? Like part of it was it's not just a big spec. you you have it as one of the things and it will iterate.

</details>

**Ryan Lopopolo**: 有一件事，我认为会让你更加震惊的是，我们有关于如何正确生成深度油炸模因（Deep Fried Memes）并在 **Slack** 中拥有互动文化的技能（Skills），因为有了 **Slack** **ChatGPT** 应用，你可以使用 **Codex**，我可以让智能体代表我发帖。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: One one thing that I think is going to break your mind even more is we have skills for how to properly generate deep fried memes and have reacti culture in **Slack** because with the **Slack** **chatgpt** app that you're able to use and **Codex** like I can get the agent to post on my behalf.

</details>

**主持人**: 只是它也是幽默的一部分。幽默是 **AGI** 的一部分。呃，它有趣吗？它相当不错。是的。

<details>
<summary>Original English</summary>

**主持人**: Just it's part of humor. Humor is part of **AGI**. Uh is it is it funny? It's pretty good. Yeah.

</details>

**Ryan Lopopolo**: 好的。是的，它在制作方面相当不错，你知道，这就像我认为幽默是一个非常困难的智力测试，对吧？就像你需要用非常少的词语来表达很多上下文。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Okay. Yeah, it's pretty good at making, you know, it's it's a lot of like I think humor is like a really hard intelligence test, right? Like it's like you have to get a lot of context into like very few words.

</details>

**主持人**: 这就是，这就是为什么 **GPT-5.4** 对我们的产品来说是一个巨大的提升。这是模因化的。是的，当然。

<details>
<summary>Original English</summary>

**主持人**: This is this is why this is why **5.4** is such a big uplift for our varieties. It's it's the memeing. Yeah, for sure.

</details>

**Ryan Lopopolo**: 是的。是的，这很酷。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah, it's really cool.

</details>

**主持人**: 所以 **GPT-5.4** 可以帮助我们。这是重点。

<details>
<summary>Original English</summary>

**主持人**: So **5.4** can chip us. That's the take away.

</details>

**Ryan Lopopolo**: 是的。也许，嗯，也许当你们今天在这里完成后，让 **Codex** 去查看你们的编码智能体会议并嘲笑你们。嗯，喜欢它。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Maybe um maybe when y'all are uh done here today, ask **Codex** to go over your coding agent sessions and to roast you. Um love it.

</details>

**主持人**: 我会试一试。试一试。呃，只是回到我想说的最后一点是，是的，我，我，我认为还有很多其他的，就像你们正在做这个，但这是一个其他所有公司都应该采纳的模式，无论他们是否与你合作。对我来说，这就像我看到这个，我就想，每家公司都需要这个。我的意思是。

<details>
<summary>Original English</summary>

**主持人**: I'll give it a shot. Give it a shot. Uh just coming back to the the the final point I wanted to make is yeah, I I I think that there there are multiple other like you guys are working on this, but this is a pattern that every other company out there should adopt regardless of whether or not they work with you. To me this like I saw this I was like every company needs this. I mean

</details>

**Ryan Lopopolo**: 这就是多个业务所需要的，让人们实现好处并分发层。嗯，它，它，它，我想它听起来很无聊，对人们来说，就像，哦，你知道，它是为了保障和等等，但就像，嗯，我想你，为了大规模处理智能体，就像你在这里设想的那样。嗯，我不知道它是否像一个真实的截图，像一个演示，但就像这就是你需要的。这是我最初对 **Temporal** 的看法，就像你构建了这个仪表板，你基本上把公司中每个长时间运行的进程都放在一个仪表板上，仅此而已。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: this is multiple business what it takes to get people to Yes. Yeah. Actually realize the benefits and distribute layer. Um and it's it's it it I think it sounds boring to people like oh you know it's for safeguards and and whatever but like um I think you to to handle agents at scale like you're envisioning here. Um I don't know if it's like a real screenshot like a demo but like this is what you need. This is my original sort of view of what **Temporal** was supposed to be like you you built this dashboard and you basically have every longunning process in the company and one dashboard and that's it.

</details>

**主持人**: 没错。没错。是的。我认为这很，这很像为每个企业定制的，对吧？就像你关心不同的事情。

<details>
<summary>Original English</summary>

**主持人**: That's right. That's right. Yeah. I think it's pretty it's pretty like customized towards every enterprise, right? Like you care about different things.

</details>

**Ryan Lopopolo**: 有很多定制，对吧？但就像我的意思是，会有很多独角兽公司专门做这个服务。就像我不知道。我非常非常支持 **Frontier**，如果你看不出来的话。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: There's a lot of customization, right? But like I mean there'll be multiple unicorns just doing this as a service. Like I don't know. I'm like very very **Frontier** pled if you can't tell.

</details>

**主持人**: 太棒了。但，但就像它只在后来才明白，因为显然这个先出来了，然后是Harness，然后是 **Symphony**，它只在我这里才明白，就像这实际上是你为了做到这一点而发布的东西。

<details>
<summary>Original English</summary>

**主持人**: Amazing. But but like it only clicked cuz obviously this came out first, then harness and then **Symphony** and it only clicked for me that like this is actually kind of the thing you ship to do that.

</details>

**Ryan Lopopolo**: 是的。是的。这里有一套构建块，我们将其组装成这些智能体，而构建块本身就是产品的一部分，对吧？这种能力。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah. There's a set of building blocks here that we assembled into these agents and the building blocks themselves are part of the product, right? the ability to

</details>

**主持人**: 指导、撤销授权，如果模型变得失调。所有这些都可以通过 **Frontier** 访问。

<details>
<summary>Original English</summary>

**主持人**: steer, revoke authorization if a model becomes misaligned. Like all of this is accessible through **Frontier**

</details>

**Ryan Lopopolo**: 公司里会有很多利益相关者。他们需要看到平台中他们需要看到的东西才能同意。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: and there's going to be a bunch of stakeholders in the company that have the things they need to see in the platform to get to Yes.

</details>

**主持人**: 所以我们将在 **Frontier** 中构建所有这些，以便我们能够实际进行广泛部署。这很有趣。

<details>
<summary>Original English</summary>

**主持人**: So we'll build all those in the **Frontier** so that we can actually do the widespread deployment. That's the fun part.

</details>

**Ryan Lopopolo**: 是的。是的。我还想回顾一下，呃，有这种AGI的层次，就像我不知道 **OpenAI** 是否还在谈论这个，但他们以前谈论过AGI的五个层次，其中一个就像是，哦，它就像一个实习生，在某个时刻是AI组织，这就是它，对吧？这是第四或第五层，我不记得是哪一层了，但它是在这条路上的某个地方。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah. I'm also calling back to like uh there's this like levels of **AGI** like I don't know if **OpenAI** is still talking about this but they used to talk about five levels of **AGI** and one of it was like oh it's like an intern and the coding software engineeration at some point it was AI organization and this is it right this is level four or five I can't remember which which level but it's somewhere along that path was this

</details>

**主持人**: 你知道我怎么提到我的团队在这里玩得很开心，全力冲刺吗？对吧？我们这样做，我们收集 **Codex** 的所有智能体轨迹，然后吸取并提炼它们，就像这就是构建我们团队级知识库的含义，你知道，将其反映回代码库，但它不一定非得那样，对吧？你知道，它也不必仅仅局限于 **Codex**，对吧？我希望 **ChatGPT** 也能学习我们的模因文化，以及我们正在构建的产品和方式，对吧？这样当我问它问题时，它也能完全了解我的工作方式，我非常期待 **Frontier** 能实现这一点。

<details>
<summary>Original English</summary>

**主持人**: you know how I mentioned that my team is having fun sprinting ahead here right and we do this thing where we're collecting all the agent trajectories from **Codex** to slurp them up and distill them like this is what it means to build our team level knowledge base you know happen to reflect it back into the codebase but it doesn't have to be that way right you know and it doesn't have to be bound to just **Codex** right I want **chatbt** to also learn our meaning culture and also the product we are building and how right so that when I go ask it it also has the full context of the way I do my work and I'm super excited for **Frontier** to enable this

</details>

**Ryan Lopopolo**: 是的，太棒了，模型人员看到你这样做时会说什么？就像你有很多反馈，显然你有很多用途，你有很多轨迹，我没有，我没有想象其中很多对他们有用，但其中一些有用。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: yeah amazing what are the the model people say when they see you do this like you have a lot of feedback obviously you have a lot of usage you have a lot of trajectories I don't I don't imagine a lot of it's useful to them but some of it is

</details>

**主持人**: 你也有这个，你每天部署10亿令牌的智能，而这在206年初期，你，你知道，正在运作。

<details>
<summary>Original English</summary>

**主持人**: you have this too you deploy a billion tokens of intelligence a day and this was you know this was at the beginning of 206 you're yeah you know cooking

</details>

**Ryan Lopopolo**: 是的，存在一个根本的张力，我想你已经讨论过，是投资Harness更深，还是投资训练过程更深，以使模型默认做更多的事情。是的。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: yeah there's this fundamental tension which I think you have talked about between whether or not we invest deeper into the harness or we invest deeper into the training process to get the model to do more of this by default. Yeah.

</details>

**主持人**: 我认为我们在这里的操作方式的成功意味着模型会获得更好的品味，因为我们可以指出方向，而我们所构建的任何东西都不会主动降低智能体的性能，因为它们所做的只是运行测试，而运行测试是编写可靠软件的重要组成部分。如果我们围绕 **Codex** 构建一个全新的ROS脚手架来限制其输出，那我认为这将是额外的Harness，很容易被废弃。但是，是的，如果我们能够以一种对 **Codex** 已经生成的输出（即代码）来说是原生的方式来构建所有护栏（Guardrails），我认为这既不会与模型的持续发展产生摩擦，同时也是良好的工程实践。这才是重点。

<details>
<summary>Original English</summary>

**主持人**: And I think success for the way we are operating here means the model gets better taste because we can point the way there and none of the things we have built actively degrade Asian performance cuz really all they're doing is running tests and like running tests is a good part of what it means to write reliable software. If we were building an entire separate ROS scaffold around **Codex** to restrict its output, that I think would be like additional harness that would be prone to being scrapped. But yeah, if instead we can build all the guardrails in a way that's just native to the output that **Codex** is already producing, which is code, I think one, no friction with how the model continues to advance, but also like just good engineering. And that's that's the whole point.

</details>

**Ryan Lopopolo**: 是的。所以我和研究科学家有过类似的讨论，关于策略（Policy）和离策略（Off-Policy）的强化学习等价物。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. So I've had similar discussions with research scientists where the RL equivalent on policy versus off policy.

</details>

**主持人**: 是的。你基本上是在说，你应该构建一个“在策略上”（On-Policy）的Harness，它已经很好地在分布范围内，然后你从那里修改它。但是如果你构建“离策略”（Off-Policy），那么它就不是那么有用。

<details>
<summary>Original English</summary>

**主持人**: Yeah. And you're basically saying that you should build an on policy harness which is already like well within distribution and you modify it from there. But if you build off policy well it's not that useful.

</details>

**Ryan Lopopolo**: 没错。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's right.

</details>

### OpenAI Frontier：构建AI驱动的未来

**主持人**: 太酷了。那么还有什么我们没有涉及到的，我们应该提出来的吗？

<details>
<summary>Original English</summary>

**主持人**: Super cool. Well any thoughts any things that we haven't covered that we should get get out there?

</details>

**Ryan Lopopolo**: 只是，呃，我非常高兴能从 **Codex** 团队所做的一切工作中受益。他们绝对是无情地交付产品。这是我们核心工程价值之一。无情地交付产品，而那里的团队以极致的程度体现了这一点。哦，是的， **GPT-5.3** 和Spark以及 **GPT-5.4** 在短短一个月内发布，这真是惊人的速度。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Just uh I've been super excited to kind of benefit from all the cooking that the **Codex** team has been doing. They absolutely ship relentlessly. This is one of our core engineering values. Ship relentlessly and they the team there embodies it to an extreme degree. Oh yeah to have **5.3** and then spark and **5.4** come out within like what feels like a month is just a phenomenally fast.

</details>

**主持人**: 刚好是一个月前，是 **GPT-5.3**，昨天是 **GPT-5.4**。是的。我的意思是，我们现在每个月都有 **GPT-5.5** 吗？

<details>
<summary>Original English</summary>

**主持人**: This exactly a month ago it's **5.3** and yesterday was **5.4**. Yeah. I mean is do we have every month now is 5'5 nice? Like

</details>

**Ryan Lopopolo**: 呃，你知道，我不能说Poly Markets会非常不高兴，对吧？呃，我想这很有趣，它也与增长相关。你知道，他们宣布它有200万用户，但就像我几乎不再关心 **Codex** 了，就像这就是游戏，伙计。就像编码很酷，软件就像知识工作。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: uh you know I can't say that the poly markets would be very upset, right? Uh well I I think it's interesting that like it's also correlated with the growth you know they they announced that it's like 2 million uh users but like almost don't care about **Codex** anymore like this is it this is the game man like it's like coding cool soft like knowledge work

</details>

**主持人**: 没错，你知道，这就是要追逐的东西，呃，你知道，这是我的团队很高兴支持的东西。

<details>
<summary>Original English</summary>

**主持人**: that's right you know this is the thing to chase after and uh you know this is one of the things that my team is excited to support

</details>

**Ryan Lopopolo**: 让整个像自托管Harness的东西工作起来，你已经做到了，就像我们其他人都在努力追赶，但就像那样做，你知道，和你一起。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: get the whole like self-hosted harness thing working which you have done and like the rest of us are trying to figure out how to catch up but like then do things, you know, right with you.

</details>

**主持人**: 做事。

<details>
<summary>Original English</summary>

**主持人**: Do things.

</details>

**Ryan Lopopolo**: 没错。你就是可以做事情。这就是本集节目的主线。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: That's right. You can just do things. That's the line for the episode.

</details>

**主持人**: 就这样。还有其他的行动号召吗？你，你 basé 在西雅图。你的团队，我猜。

<details>
<summary>Original English</summary>

**主持人**: That's it. Any other call to actions? You're you're based in Seattle. Your team, I'm guessing.

</details>

**Ryan Lopopolo**: 新的Bellevue办公室。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: New Belleview office.

</details>

**主持人**: 新的Bellevue办公室。我们刚刚在录制日昨天盛大开业。呃，这太棒了。漂亮的建筑。非常高兴能成为Bellevue社区的一部分，在华盛顿州建设未来。我想说，为了成功服务于这里的企业客户，**Frontier** 还有很多工作要做。我们当然正在招聘。如果你还没有尝试过 **Codex** 应用，请下载它。我们刚刚突破了200万周活跃用户，以惊人的速度增长，每周增长25%。请加入我们。呃，是的，我认为这是一个有趣的。我不知道，我的最后观察，嗯，**OpenAI** 是一家非常以旧金山为中心的公司。就像我认识那些因为不想搬到旧金山而拒绝工作或没有得到工作的人，而现在他们别无选择，对吧？你必须在伦敦开设，你必须在西雅图开设。我想知道这是否会改变文化，对吧？显然你不能说，但是。

<details>
<summary>Original English</summary>

**主持人**: New Belleview office. We just had the grand opening yesterday as of the recording date. Uh which was fantastic. Beautiful building. Super excited to be part of the Belleview community building the future in Washington. And I would say that there is lots of work to be done in order to successfully serve enterprise customers here uh in **Frontier**. We are certainly hiring. And if you haven't tried the **Codex** app yet, please give it a download. We just passed 2 million weekly active users, growing at a phenomenally fast rate, 25% week over week. Please come join us. Uh yes and I think that's an interesting I don't know my my final observation um **OpenAI** is a very San Franciscocentric company like I I know people who have been who turned down the job or didn't get the job because they didn't want to move to SF and now they just don't have a choice right you have to open the London you have to open the the Seattle and I wonder if that's going to be a shift in the the culture right obviously you can't say but

</details>

**Ryan Lopopolo**: 我是我们在西雅图办公室的第一批工程师之一。所以，你看，这非常自然。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: I was uh one of the first engineering hires out of our Seattle office so See it was very natural.

</details>

**主持人**: 成功是我一直在努力建设的一部分，而且它发展得很好。对。我们在那里建立了耐用的产品和业务线。呃，也有大量的从零到一的工作正在进行，这有点是我们公司进行应用AI工作的核心本质，以追逐它，呃，新的，以找出我们实际上可以成功部署模型的地方。所以，呃，是的，100%。我们纽约也有一个办公室，呃，那里也有大量的工程人员。

<details>
<summary>Original English</summary>

**主持人**: Success has been part of what I have been building toward and it is has grown quite well. Right. We have durable products and lines of business that are built out of there. Uh ton of 0ero to one work happening as well which is kind of the core essence of the way we do applied AI work at the company to sprint after it uh new to figure out where we can actually successfully deploy the model. So uh yes 100%. We also have a New York office too uh that has a ton of engineering presence.

</details>

**Ryan Lopopolo**: 是的。呃，完全正确，这些，这些都是我AI工程的路线图。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Uh exa exactly that's these these are my road maps for AIE.

</details>

**主持人**: 只要哪里有工程师招聘，我就会去。没错。

<details>
<summary>Original English</summary>

**主持人**: Wherever people hire engineers I will go. That's right.

</details>

**Ryan Lopopolo**: 纽约的办公室也很酷。我相信是老REI大楼。REI办公室。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: It's a cool office too. New York is the old REI building I believe. The REI office.

</details>

**主持人**: 是的，它就是不，你永远不会有那么大。对。纽约就像你无法获得他们所需的那种规模的办公室。纽约西雅图有一种非常像办公室狂人（Office Madmen）的感觉。它很漂亮。呃，Bellevue的那个非常绿色，金色装置，非常太平洋西北风格，是一个非常酷的地方，很多人都喜欢那里。人们喜欢纽约，他们想留在纽约，对吧？

<details>
<summary>Original English</summary>

**主持人**: Yeah it's just No, you'll never be as big. Right. New York is like you can't get the size of office that they need. The the New York Seattle has a very like office madmen sort of vibe. It's it's beautiful. Uh the the Belleview one is very green, gold fixtures, very Pacific Northwest is very cool place which a lot of people are like there for. People like New York, they want to be in New York, right?

</details>

**Ryan Lopopolo**: 是的。是的。我们有一个很棒的工作场所团队，一直在建造这些办公室。能在这里工作真的是一种荣幸。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: Yeah. Yeah. We have a fantastic workplace team that has been building out these offices. It really is a privilege to work here.

</details>

**主持人**: 是的。太好了。呃，好吧，谢谢你的时间。呃，你非常慷慨，嗯，你一直在忙碌。所以，我让你回去继续工作。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Excellent. Uh okay. Well, thank you for your time. Uh you've been very generous and uh you you've been cooking. So, I'm going to let you get back to cooking.

</details>

**Ryan Lopopolo**: 很高兴与你们聊天。呃，周五快乐。

<details>
<summary>Original English</summary>

**Ryan Lopopolo**: It's been amazing chatting with you folks. Uh happy Friday.

</details>

**主持人**: 周五快乐。

<details>
<summary>Original English</summary>

**主持人**: Happy Friday.

</details>