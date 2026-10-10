---
author: AI Engineer
date: '2026-07-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pMggiOb18tc
speaker: AI Engineer
tags:
  - ai-engineering
  - agentic-workflow
  - llm-speed
  - developer-tools
title: AI 工程师的黄金时代：OpenAI 视角下的 Agent、模型加速与闭环演进
summary: 本文为 OpenAI 团队 Romain Huet、Alexander Embiricos 与 Peter Steinberger 在 AI Engineer Summit 上的分享记录。探讨了 AI 工程师如何重塑软件开发范式，展示了从代码补全到长任务自主 Agent 的演进，并详细介绍了 OpenAI 开放的生态层、模型成本与速度突破（如在 Cerebras 上运行的 GPT-5.6），以及面向未来的 AGI 协作工作流变革。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Peter Steinberger
companies_orgs:
  - OpenAI
products_models:
  - GPT-5.6
  - GPT-5.5
  - Codex
media_books: []
status: evergreen
---
### AI 工程师正在吞噬世界

**Romain**: 大家早上好。我是 Romain。

<details>
<summary>Original English</summary>

**Romain**: Good morning, everyone. I'm Romain.
</details>

**Alexander**: 大家好，我是 Alexander。

<details>
<summary>Original English</summary>

**Alexander**: Hey everyone, I'm Alexander.
</details>

**Romain**: 哇，这个房间真是太不可思议了。今天现场有超过 7,000 名 **AI 工程师**和我们在一起。而且你们知道，这不仅仅关乎谁在讨论这项技术，更关乎谁在真正使用它，并每天都在推动前沿的发展。所以，今天能和大家共聚一堂，我们感到无比自豪。

当我和 Alex 筹备这次活动时，我们脑海中不断浮现出**世界博览会**（World's Fair）的场景。世界博览会之所以能让每个人都亲眼看到未来，是因为它是在公开场合进行建设的，明白吗？那些以前听起来觉得不可能的创意，突然之间就真真切切地呈现在那里。人们能够看到它们，走近它们，甚至开始相信它们。老实说，这次活动散发着完全相同的能量。工程的未来并不是从别处降临的，它确实是由这个房间里的每一个人亲手构建的，而且速度比大多数人的预期要快得多。

这也是为什么有些让人感到意外的是，人们一直在说工程师将要消失了。他们的论点是，编程编码正在被抽象化，因此我们最终将不再需要工程师。好吧，事实上，我们的看法恰恰相反。大家都知道，软件吞噬了世界，接着 AI 吞噬了软件。但现在，我们在这里想说的是，**AI 工程师正在吞噬世界**。AI 工程师正是站在这里推动前沿的开拓者。是的，你们大家正在探索如何让这种全新的能力触及每一个人。

事实上，现在是成为一名工程师的最好时代。因为工程的本质从来都不是编写代码，工程一直以来都是在为你自己以及为他人解决实际问题。它是将最新的科学技术与设计、品味、判断力，以及最关键的想象力结合起来，去创造出人们能够真正使用的东西。从这个意义上说，这绝不是工程的终结，我们认为这是向工程本源的回归。

<details>
<summary>Original English</summary>

**Romain**: Wow, this room is incredible. There's over 7,000 AI engineers here today with us. And you know, it's not just about who's talking about this technology. It's also about who's actually using it and pushing the frontier every day. So, we couldn't be more proud to be here with all of you today. And when we were thinking about this event with Alex, we kept coming back to the World's Fair. And the World's Fair made actually the future visible to everyone by building it in public, you know? Ideas that previously sounded impossible were actually suddenly there. People could see them. They could walk into them. And they could even start to believe in them. And honestly, this event has the exact same energy. The future of engineering is not arriving from somewhere else. It's really being built here by the people in this room and much faster than most expected. And that's why it's a little surprising that people keep saying that engineers are going away. The argument is that coding is, you know, abstracted away and therefore eventually we won't need engineers. Well, in fact, we think it's quite the opposite. You know, software ate the world. And then AI ate software. But now, what we're here to say is that the AI engineers are eating the world. AI engineers are the people here pushing the frontier. Yes. And you all are figuring out how this new capability can reach everyone. And there has never been a better time to be an engineer, in fact, because engineering was never about writing code. Engineering has always been about solving problems for yourself and for other people as well. It's about taking the latest science and combining it with design, with taste, with judgment, and most of all, imagination to make something that people can actually use. And in that sense, it's not the end of engineering. We think it's a return to the roots of engineering.
</details>

### 开发范式的无情演进

**Alexander**: 而且我们赖以构建的技术正在加速发展，变得越来越快。例如，我们以前大约每 15 个月发布一个新模型，而现在大约每 6 周就会发布一次。如果你错过了上周的新闻，我们上周刚刚发布了 **5.6 系列**的预览版，我们非常兴奋能将其交到你们所有人的手中。

现在，在所有这些模型之上，产品的进步速度也是势不可挡的。因此，我不需要向你们多说，工程的体验已经变得完全不同了。回顾过去几年，对我而言，那些都是连续性的、令人惊叹的体验。

显而易见，在很长一段时间里，我们拥有的只是代码自动补全（completion），然后我们转向了行内预测（inline prediction），最后我们迎来了 Command K 阶段，你可以要求模型直接做出修改，但它们当时还不会测试自己的工作。接着，模型开始学会测试它们的工作，而现在，我们拥有了能够承接长期且艰巨目标并一直执行到完成的模型。对我来说，其中的每一个阶段，在第一次体验时都绝对是令人瞬间震撼的。当然，在这之后你就会习以为常，并继续专注于把工作做好。

<details>
<summary>Original English</summary>

**Alexander**: And the technology we're building on is accelerating, getting faster and faster. For example, we used to ship a new model every 15 months or so, and now it's about roughly every 6 weeks. And in case you missed it, last week we launched a preview of the 5.6 series, and we're super excited to get into all of your hands. Now, building on top of all these models, the rate of product progress is relentless. And as a result, I don't have to tell you and the engineering feels completely different. So, just to go over a couple years of what for me were successive like mind-blowing experiences. You know, obviously for a long time we've had, you know, completion, and then we went to inline prediction, and then finally we had then we had command K where you could ask model to make a change, but they wouldn't test the work. Then models started testing the work, and now we have models taking on long, hard goals until they're done. And for me, each of these phases, I remember the first time was just mind-blowing, and then obviously afterwards you just get used to it and you're trying to get your work done.
</details>

### 从代码补全到自动测试的跨越

**Romain**: 是的，事实上，我都无法相信仅仅在两年前，**构建和测试循环**（build and test loop）甚至还不是模型的一部分。这是我在 2024 年开发者大会（Dev Day 2024）上的一张照片，当时我使用了 o1 预览版从零开始构建了一个微型无人机的控制界面。

当时稍微有些疯狂的是，模型实际上无法运行代码或验证其自身的工作，而我虽然知道这个演示在大多数时候都能成功，但绝对不可能保证百分之百成功。所以我只能暗自祈祷并保佑一切顺利。你们大概能从这里看出来我当时非常紧张。不过，嘿，这就是我。我只做现场直播演示，所以我每次都无法预料实际会发生什么。

幸运的是，那次演示确实成功了。到了去年也就是 2025 年的开发者大会，我已经足够自信了，因为模型当时已经可以测试它们自己的工作，甚至能够现场控制一整套相机系统和照明系统。但确实，我们已经走了很长的一段路。

<details>
<summary>Original English</summary>

**Romain**: Yeah, in fact like I can't believe that build and test loop was not even part of the models just 2 years ago. This was a picture of me at Dev Day 2024, and I used o1 in preview at the time to build a mini drone in drone interface from scratch. And the slightly insane part is the model could not actually run the code or verify its own work, and I knew the demo would work most of the time, but surely not all of the time. So, I had to cross my fingers. You can kind of see here that I was pretty nervous, but hey, that's me. I only do live demos, so I never know what's actually going to happen each time. Luckily, it did work, and by Dev Day of last year in 2025, I was confident enough now the models could test their own work to kind of control an entire camera system and lighting system live. But yeah, we've come a long way.
</details>

**Alexander**: 是的，所以我们都称他为“演示之神”（demo god）。在演示开始前，我会问他：“嘿，你的现场演示成功率通常是多少？”他会回答说：“大概四分之三吧。”然后我们只能说：“好吧，祝你好运。”

显然，自那以后我们已经取得了长足的进步，光是今年一年的发展就堪称疯狂。我们在这里展示的，是我们在今年目前为止所发布的所有产品。事实上，这甚至不是全部，只是我们今年发布的众多产品中的一部分精选。

我个人最喜欢的发布包括 **Codex 应用程序**（Codex app）、**目标模式**（goal mode）以及远程协作功能。这些功能真正改变了我们开展工作时的体验和感受。

<details>
<summary>Original English</summary>

**Alexander**: Yeah, so we refer to him as the demo god and you know, before the demo like I'll ask him so hey, how often does demo work? He'll be like, you know, three times out of four and we're all right, good luck. Um, obviously we've come miles since then and this year alone has been crazy. So, what we're putting up here are all the things that we've shipped so far. Not actually not even all, a selection of the things that we've shipped so far this year. Uh, my favorite things that we've shipped are like Codex app, goal mode, remote. These are things that really changes how it feels to do work.
</details>

### 构建全流程自主 Agent 与开放生态栈

**Romain**: 你们知道，显然如果我们自己不使用 Codex 来构建 Codex，我们就无法做到这些事情。但对我来说，最有趣的是，现在 Codex 和 Agent 可以执行任何你在自己电脑上可以完成的自主任务。

这意味着它们不仅是在协助你编写代码，还在协助你处理编码之前的工作，以及协助你处理编码之后的工作。这一点至关重要，对吧？我想今天会有很多关于“循环”（loops）的讨论。如果你能将 Agent 不仅与你必须要做的工作连接起来，还与“为什么要这么做”的背景原因连接起来，你就能让 Agent 开始承担多得多的工作量。

然后，如果你能将其与你之后要做的事情联系起来——比如代码评审（review）和部署（deploy）——这就是你如何帮助它落地并完成更多实质性工作的方法。

所以，有了这一切，我们当然可以跑得快得多。但作为一个产品负责人，最令人兴奋的实际上是我们在构建什么方面做出了更好的决策。例如，我们可以尝试并快速迭代原型化更多的想法，并且我们可以花更多的时间与用户在一起。是的，指的就是在座的每一位。

因此，我想在这里停顿一下，对大家的提议以及建设性的反馈表达由衷的感谢。可以说，如果没有你们，我们、Codex 乃至整个行业都不会有今天的成就。谢谢大家。

<details>
<summary>Original English</summary>

**Romain**: You know, obviously we couldn't do these things if we didn't use Codex to build Codex, but I think to me what is most interesting is that now Codex can do and agents can do any task that you can do on your own computer. And so, that means they're not just helping you with the coding, but they're helping you with what happens before the coding and they're helping you with what happens after the coding. And this is really key, right? I think there's been a lot of talk, there will be a lot of talk today about loops and if you can connect the agent to not only the work that you have to do, but why it has to be done, that's how you can get the agent to start to begin much more work. And then if you can connect it to what you do afterwards, review and deploy, that's how you help it land much more work. So, with all of this, of course we can move much faster, but to me as a product person, the most exciting thing is actually that we make better decisions around what to build. For instance, we try, we prototype many more ideas and we spend much more time with users. So, yes, that's all of you. So, wanted to pause and just give you all a big thank you both for the love and the constructive feedback. I would say it's safe to say that we, Codex and actually the entire industry wouldn't be here without you.
</details>

**Alexander**: 是的，非常感谢大家提供的一切反馈。我们一直在倾听你们所有人的声音。谢谢你们。

<details>
<summary>Original English</summary>

**Alexander**: Yeah, thank you so much for all the feedback. We're constantly listening to all of you. Thank you.
</details>

[观众掌声]

### 重新定义人机协作界面

**Romain**: 好的。目前的模型正在变得非常优秀。我想说，如果你挑选一个中等难度的电脑任务，并给我和模型相同的时间去完成，可能至少在我的情况下，模型在处理平均任务时的表现会比我更好。

既然如此，既然模型在某些方面已经比我们更聪明，几乎可以做任何事情，那么我们该如何去塑造它？我们日常使用的产品应该带给人们怎样的体验？

为了回答这个问题，我们回归到了我们的使命，也就是我展示在屏幕上的这部分内容：“让通用人工智能（AGI）惠及全人类”。为了实现这一点，我认为目前有两大核心问题需要思考。

第一个问题是，我们该如何设定 Agent，让它们在现实世界中真正替我们做事？也就是说，它们能做些什么？逐渐地，Agent 正在与越来越多的系统进行连接。然后，它们应该在哪里运行？稍后我们会详细讨论这一点。

另一个问题是，我们该如何使用这些 Agent？对于我们而言，我们周围的产品形态应该感觉像什么？对我们来说，我们的目标绝对不是为了实现工程师的自动化，从而取代人类。相反，我们想要塑造的产品形态，是那种能最大程度赋能工程师的工具。

如果我们思考那种产品形态到底是什么，其实我们认为它非常简单。我读过很多科幻小说，也看过很多超级英雄电影，我真的觉得里面那些朴素的设想大致是正确的。

这里大致有两种协作模式。一个是对话（Chat）。我知道有些人认为对话交互已经过时了，但我认为对话界面在很大程度上被低估了。

另一个则是某种手把手的沉浸式协作体验（hands-on experience）。

所以，你真正想要的是一个单一的实体（single entity），你可以在任何地方、针对任何事情向它寻求帮助。同时，你还需要一个强大的协同界面（collaborative UI），当你想亲自去检查、引导或塑造某些事物时，你可以使用它。

我让 Codex 的图像生成功能为我画了一张插图来展示这一点，以帮助大家理解什么时候你会想要使用这些不同的工具。我的类比是，这就像是和团队一起工作。大部分时间里，你们只是在交流想法，你的团队成员就会去执行具体工作。你并不想总是站在他们身后盯着看，或者针对每一小项工作都要走到你同事的办公桌前去检查。大多数时候，你只想和他们沟通，然后“让他们去施展（let them cook）”。

然而每隔一段时间，你又需要亲自深入进去，一路探究到最细微的细节中，和团队成员共同挖掘并解决那个问题。对于我们构建产品而言，我们抱持的理念是，希望让你在做这些工作时能保留一种对工作的绝对掌控感（feeling of mastery），因为这才是最强大的。我们不希望让人们觉得想要深入细节或拆解硬件是一件极其困难的事。

<details>
<summary>Original English</summary>

**Romain**: Okay. So, the models are getting really good. I would say, if you pick like a medium length computer task and you give me and the model the same amount of time to get that task done, probably at least in my case, the model will do a better job than me for the average task. And so, okay, we're we're getting these models, you know, in some ways they're smarter than us. They can do almost anything. How should we shape that? What should the products that we use feel like? And so, to answer that, we look to our mission. The part of it here that I've got up is, you know, AGI that benefits all of humanity. And I think in order to do this, there are two main questions that I think about now. One is, how do we set up the agents to actually do things in the world? So, what can they do? You know, gradually agents are getting connected to more and more things. Then where do they run? More on that later. And then the other question is, how do we use these agents? For us, you know, what what should the product feel like around them? And for us, the goal is squarely not to automate engineers. Instead, the the product shape that we want is one that maximally empowers engineers. So, you know, if we think about what that product shape is, we actually think it's pretty simple. I I read a lot of sci-fi, and you know, watch superhero movies. And I actually think that the the simple ideas in there are approximately right. So, there are two modalities, roughly. Chat. I actually think I know some people think chat is dead. I think chat is underrated. Uh and some kind of hands-on experience. So, what you want is a single entity that you can ask for help with anything, anywhere. And then you want a a powerful collaborative UI that you can use when you want to inspect, steer, or shape things yourself. And so, I had Codex image gen me an illustration of this to help understand when you might want to use these things. And so, my analogy for you, yeah, I hope you like the image gen. Uh my analogy for you would be it's just like working with a team. Most of the time, you're just talking about stuff, and your team is just doing stuff. You don't actually want to watch over the shoulder, or like have to walk over to the workbench of your teammate for every single unit of work. Mostly, you just want to talk and let them cook. And then every now and then, you want to dig in and really dig in all the way to the weeds of things, and dig digging that problem together. And for us, as we build product, we have this idea that we want to make it so that you can retain this feeling of mastery of the work that we're doing, because that's really powerful. We don't want to make it feel like actually it's really hard to like get to the details and like, you know, disassemble the hardware in this case.
</details>

### 打开黑盒：可定制与可Fork的技术栈

**Alexander**: 没错。将这个愿景付诸实践才刚刚开始，这也是为什么我们构建了 Codex 应用程序。

你将获得一个非常简单的对话界面，可用于编程以及其他任何事情。你可以进行交谈，并在需要时深入决策。例如在屏幕上的这个案例中，我们展示了 Homan 对即将到来的世界杯比赛预测得分。

<details>
<summary>Original English</summary>

**Alexander**: So, the way that we're bringing to this to life is just the beginning, but this is why we built the Codex app. You get a very simple chat interface that you can use for coding and for anything else. And you know, you can have a conversation and then go deep as you want. So, in the case here, we have Homan's predicted score of this upcoming World Cup match.
</details>

**Romain**: 我希望我是对的，希望我能猜对。我们拭目以待。

<details>
<summary>Original English</summary>

**Romain**: I hope I'm right. I hope I'm right. We'll see.
</details>

[观众笑声]

**Alexander**: 好的。你在界面中可以做的是，直接指向一个非常具体的东西并说：“嘿，我希望你做这个修改。”或者你也可以自己动手进行修改。

这里有一个有趣的故事。我记得在开始这个项目之前，曾向在座的几位推销过这个想法，当时我被很直接地告知：“我们绝对不会使用这种工具，我永远不会离开我的终端，也不会离开 Vim 或 Emacs。”但实际上，那些人现在都在使用它。

即使在我们的团队内部，当时也有很多疑问，比如：“我们为什么要构建这个？人们热爱终端命令行，他们热爱 IDE。”我们的观点是，在命令行中，你很难为任何形式的工作构建那种协同协作界面，命令行里基本上就只有对话。而在 IDE 中，顺序往往又反了，它是以代码为起点的。

但现在，是时候过渡到像和团队伙伴一起工作那样的体验了——也就是先进行沟通，并在需要时随时深入代码细节。

<details>
<summary>Original English</summary>

**Alexander**: Okay. Um and what you can do here is you could go in and you can point at a very specific thing and say, "Hey, I want you to make this change." Or you can make this change yourself. And a fun story here is that actually I remember pitching some of you who I know are in the audience uh this idea before we started and I was told squarely like, "We I will never use such a tool. I will never leave my terminal." Uh or Vim or Emacs. Um but actually those people are now using it. And even internally like within our team, there were a lot of questions like, "Why should we build this? People love the CLI, they love the IDE." And it's a little subtle, but our take is that you can't really build that collaborative interface for any kind of work in a CLI. It's mostly chat. And then in an IDE, the order is wrong and so you're starting with the code, but now it's time to transition to like working with teammates where you chat first and you dig in when you need it.
</details>

**Romain**: 确实如此。无论是产品层面还是模型层，我们的进展都非常迅速。但我们也试图与大家保持同步，对吧？

说实话，每次我打开 X，都会看到这个房间里的某个人正在用 Codex 做一些我之前完全没有意识到它能做的事情。坦率地说，这就是先驱者所做的。你们去尝试、去探索，为你们自己和你们的团队配置各种工具，而作为回报，我们从中获得了启发。我们向你们学习，最终所有人都会从中受益。

所以，你们正在帮助我们弄清楚接下来该构建什么，以及工程的未来应该是什么样子。

但要让这一切行之有效，我们非常关心的一点是，Codex 不能是一个只有 OpenAI 才能改进的封闭产品。因此，我们在设计 Codex 时，特意将其构建为一套任何人都可以基于此进行开发的“分层技术栈”（set of layers）。

我们今天想向大家展示一下这套技术栈的组成，以及它是如何体现的。

首先，一切都始于模型。Alexander 刚才展示了我们在模型上的进展有多么迅速。而大家主要是通过 **Responses API** 来使用这些模型的。猜猜看，这正是我们构建 Codex 应用程序的方式！我们使用的是相同的模型，通过相同的 API。我们构建自己产品的基础，与我们提供给开发者的完全一样。

当 Codex 需要某些新功能时，我们总是尝试先将其融入到 API 中，这样你们也同样能从中受益。最近的一个例子是上下文压缩（compaction）。Codex 需要一种方法来为长期运行的任务压缩冗长的上下文，因此我们把这个功能构建到了 API 中。这意味着你们自己的 Agent 也可以使用我们为自己构建的相同底层机制。

接下来是下一层，**Codex 测试床**（Codex harness）也是开源的，因此你可以审查它、Fork 它、适配它。我们在 **Agent MD** 上也采取了相同的方法。我们没有为 Codex 遵循指令重新发明一种全新的文件格式，而是认为我们应该选择一个其他 Agent 也可以共同使用的命名和格式。

在测试床中，虽然默认的模型是 OpenAI 的模型，但它们并没有被硬编码在里面。所以，如果你想使用开源模型并保持相同的 Agent 循环，完全是可以的。

我们还将这个 Codex 测试床引入了我们模型的后期训练（post-training）流程中。这意味着模型可以在开源的环境中学习如何调用工具并导航操作。

以我们的开源代码团队为例，他们能够检查我们如何实现这一参考方案，并复用对他们有意义的部分，或者完全更改其余部分并做出不同的选择。我知道他们当时正在尝试看我们如何实现与 ChatGPT 的登录连接，所以他们可以直接查看代码并从中学习。

我们认为，这比让开发者去反向工程我们是如何构建以及如何发布的要好得多。

但是，如果我们想再上一层楼呢？如何将这个测试床引入到应用中？如何让人们能够用他们已有的 Codex 订阅进行登录？事实证明，我们自己也遇到了同样的问题，因为我们想要构建一个 VS Code 插件和 Codex 应用程序，并且我们需要一个统一的方式来控制这个测试床。

因此我们构建了**应用服务器**（app server），并且我们也将其开源了。这个应用服务器并不是某种社区适配器，它确实是我们在自己的产品中实际使用的路径，你们同样可以使用它。

比如这里的 Toma，也就是 X 上的 Demilyan，在我们发布官方的 Codex 应用程序之前，他就使用我们的应用服务器为 Codex 构建了他自己的原生应用，名为 **Codex Monitor**。正因为他做到了这一点，他现在成为了我们团队的一员，并且他还亲自操刀构建了 iOS 版的 Codex。

在应用层之上，我们同样希望确保创新不会受限于我们自己的想法。因此，我们在这里构建了可扩展的底层机制，比如我们在屏幕上展示的内置浏览器以及插件系统。所以，如果以浏览器使用（browser use）和计算机使用（computer use）为例，这些都是作为插件构建的，使用了与提供给你们完全一样的扩展接口。

最后，我们最近还为 Codex 构建了针对特定角色的插件，例如，为了让那些从事数据科学或设计的人更轻松地定制功能。这些插件也是开源的。你可以查看它们的底层原理，并在需要时从中汲取灵感。我们的目标确实是尽可能让这个生态系统保持开放和灵活。最棒的是，人们可以在越来越多的地方使用他们现有的订阅，从 Open Code、Pi、Droids、Open Claw 到 Xcode，甚至 JetBrains 等 IDE。

你们可以看到，这些工具正成为人们使用方式中非常有意义的一部分，这就是为什么我们如此看重与大家一起建立这个开放的生态系统。

所以，如果说我希望大家从这一节和这次演讲中带走一件事，那就是：我们并没有为 OpenAI 构建一套系统，然后再为开发者构建第二套简化的系统。在每一个层面上，我们自己所使用的，和我们提供给你们的完全是同一样东西。我们要感谢大家，因为每次你们 Fork 我们的测试床，每次你们找到模型能力的边界，都意味着我们可以借此学习并不断改进。

老实说，今天在这个房间里有 7,000 名最优秀的 AI 工程师，我相信你们将定义未来我们如何体验 AI，以及世界在未来如何体验 AI。非常感谢大家。

<details>
<summary>Original English</summary>

**Romain**: Totally. And we're moving really fast on this, on the product surface and the model layer, of course, but we're also trying to keep pace with all of you, right? Honestly, half the time I open X, I see someone in this room doing something that I had not realized Codex could actually do. And honestly, this is what pioneers do. You guys experiment, you set up tools for yourself, for your team, and in turn, we get inspired. We learn from you and eventually everyone benefits. And so we are helping uh you are helping us figure out like what to uh what to build next and also what the future of engineering should look like. But for that to work, one thing that we we really care about is that Codex cannot be a closed product that only OpenAI can improve. So we've intentionally designed Codex as a set of layers that anyone can build on. And we want to show you a little bit of that stack today and how it it manifests. First, it starts with the model and Alexander showed how quickly we're progressing on models. And you guys use these models through the responses API and guess what? This is how we built the Codex app, right? We use the same models and through the same API. We actually are building on the same thing that we give to developers. And when Codex needs something new, we always try to bake it into the API first so you can benefit as well. One example recently was compaction. Codex needed a way to compact long contexts for long-running tasks and so we'll build that into the API. So that means your agents can use the same primitives that we built for ourselves. Moving on to the next layer, the Codex harness is also open source so you can inspect it, you can fork it, you can adapt it. And we also took the same approach with Agent MD. Instead of reinventing a new file format for Codex for to follow instructions, we thought let's pick a name that other agents can actually use as well. The models are hard to default in the in the harness the models from OpenAI but they're not hard coded in there. So if you want to use an open model and keep the same agent loop, you can. And we also bring this Codex harness into the post-training process of our models. So that means the models can learn to call tools and navigate an environment that's actually something that's open source. Now take the open code team for instance. They actually were able to inspect how we have this like reference implementation and they could reuse the parts that make sense to them or change entirely all the rest and make different choices. I know for instance they were trying to see how we did like signing with ChatGPT and so they could look at the code and and and learn from it. And we think it's better than having developers reverse engineering how it builds what and and how we launch. But now let's say, speaking of subscriptions, that we want to go a level higher. And how you bring this harness into an app? And how do you let people sign in with their existing Codex subscription, for instance? Well, it turns out we had the same problem ourselves, cuz we wanted to build a VS Code extension and the Codex app. And we wanted to have a unified way to like actually control this harness. So we built app server, and we also made that open source. And the app server is not kind of a community adapter, it's really the path that we use for our own products. And you can use it, too. Toma, for instance, here, aka Demilyan on X, he built his own native app for Codex, called Codex Monitor, before we even launched the Codex app. Cuz he could build that using the app server. And now he works on our team, and he actually built Codex for iOS. And moving up the stack, at the app layer, we also want to make sure that innovation is not blocked on our own ideas. And so we built extensible primitives here, like the in-app browser that we showed on the screen, and plugins. So if you take, for instance, browser use and computer use, these were built as plugins using the exact same extension points that we have available for for all of you. And lastly, we also recently built role-specific plugins for Codex, say, to make it easier to to customize for people who work in data science or design, for instance. And these plugins are also open source. You can see under the hood and get inspired from them if that's useful. Our goal is really to keep making this as open and flexible as we can. And the best part is people can use their existing subscription in more and more places, from Open Code, Pi, Droids, Open Claw, to even Xcode and JetBrains as IDEs. And you can see how they're becoming quite a meaningful part of how people use these tools and that's really why we want to care about building this open ecosystem with all of you. So really if there's one thing I want you to take away from this section and this talk, it's this. We're not building one system for OpenAI and a second system that's simplified for developers. At every layer, we actually use the thing that we give to you. And we want to thank all of you cuz every time you fork the harness, every time you find the edge of capabilities of the models, it means we get to learn and improve. And honestly, with 7,000 of the finest AI engineers in this room today, I'm confident that all of you will define a lot of how we uh will experience AI and how the world will experience AI in the future. So thank you.
</details>

[观众掌声]

### 价值最大化与速度革命

**Alexander**: 我想为那边那位不断为场上注入活力的人鼓掌。就是你，太感谢你了。

在你们所有人的帮助下，我们正在让 Agent 的实用性呈爆发式增长。那么现在的关键问题就是：我们如何从中最大化释放出它们的价值？而我们所说的价值，可不是通过拼命消耗 Token（token maxing）来实现的。针对这一点，我们有一个专门的术语，也许你们也在使用。我不确定它是否显示在屏幕上，那就是：**价值最大化**（value maxing）。

因此，当我们与工程团队负责人沟通时，大部分的谈话主题都围绕着“价值最大化”这个概念。我们会带大家了解几个经常被讨论的常见话题，其中一些方面我们已经取得了很大进展，而另一些方面则仍有巨大的提升空间。

首先是**成本效率**（cost efficiency）。

每个人都渴望拥有最前沿的智能。你可以任意挑选你最喜欢的评估基准（eval），但你总是想要最好的模型。因此，以这里的终端基准（terminal bench）为例，目前表现最顶尖的是 **GPT-5.6 Sol**。正如我刚才所说，我们已经迫不及待地想让大家用上它了。

但是，除了想获取尽可能多的智能外，效率也同样关键。成本效率在过去很长一段时间里一直是我们的研发重点，而这些成果也正在持续带来丰厚的回报。

举个例子，图表里深蓝色标记的 **GPT-5.6 Terra**。它能够提供媲美 GPT-5.5 级别的智能，但成本直接砍半。而旁边的 Luna 模型在这次基准测试中也击败了一些非常著名的模型。但它的价格低得惊人：每百万输入 Token 仅需 1 美元，每百万输出 Token 仅需 6 美元。我把这些价格对比留给你们自己去衡量，但这无疑是极其惊人的性价比。

<details>
<summary>Original English</summary>

**Alexander**: I want to give a shout-out to whoever over there is injecting energy. That's you, okay, thank you so much. Uh so, with all of your help, we are making agents explosively useful. Uh and so now the question is how do we get value out of them? And you know, that's not token maxing. We have a term for this that maybe you use as well. I don't know, is it on screen? Value maxing. So, you know, when we talk to engineering leaders, most of the conversation is about some themes relating to the idea of value maxing. So, we're going to walk you through a few common topics that come up, some things where we've already made a lot of progress, and some things where actually there's a lot more progress to still be made. So, the first one of these is cost efficiency. Everyone wants frontier intelligence. Pick your favorite eval, you want the best model. So, with terminal bench here for instance, that's GPT 5.6 Sol, and like I said, we can't wait for you to have it. But okay, you also want as much intelligence as you can get, and that's where efficiency comes in. Cost efficiency has been a focus for us for quite some time, and the results are continuing to pay off. So, for example, GPT 5.6 Terra, I think it's in like dark blue in there. Brings GPT 5.5 level intelligence, but at half the cost. And Luna there beats some pretty notable models in this eval. But at only $1 per million input tokens and $6 per million output tokens. I'll leave it up to you to compare those costs, but that is insane value.
</details>

**Romain**: 确实如此。我们非常期待看到大家用 GPT-5.6 和这一全新模型家族去构建应用。

接下来我想谈谈**速度**（speed），对吧？之前的 GPT-5.3 Spark 已经向大家展示了高速度能释放怎样的潜力，但我们也知道，大家都希望在享有高速度的同时保留前沿的智能。你一定不希望模型因为追求速度而降低智力水平。

那么，来看看在 Cerebras 芯片上运行的 **GPT-5.6 Soul**，它能以每秒 750 个 Token 的惊人速度输出前沿的智能。我们非常期待下个月看到你们会用这个工具开发出什么。

老实说，从宏观角度来看，这种速度体验就相当于在短短 10 秒钟内直接写好一个内容相当充实的代码拉取请求（PR）。而且，这不仅仅是更迅速地获得某一个答案的问题，对吧？它关乎你能用这个速度去实现什么。

你可以让 Agent 同时尝试五到六种不同的解决路径，进行并行探索，然后在你甚至还没用老模型生成完一个单一路经的相同时间里，直接对比并挑选出最好的一个结果。所以，当你可以用如此极致的速度去操作最前沿的智能时，我们非常期待它能开启怎样的全新可能。这真的让人感觉不再是在等待 AI 做出响应，而更像是在和一位在你思考的同时就已经不断把结果呈现在你眼前的同事并肩工作。

<details>
<summary>Original English</summary>

**Romain**: Yeah, we we we really can't wait to to uh, to see all of you build uh, with GPT 5.6 and this new family of models. Now, the next thing I want to touch on is speed, right? GPT 5.3 could spark showed you what speed can unlock, but we also know that you all want frontier intelligence. You don't want to have a model that's like not as great as what you can operate at the very best. Well, this is GPT 5.6 Soul running on Cerebras, the frontier intelligence at now 750 tokens a second. We can't wait to see what you can build with this next month. And honestly, to put that in perspective, this is kind of like having a pretty substantial PR written in like 10 seconds. And it's not just about getting one answer faster, right? It's about what can you do with that speed? You can think about an agent taking different approaches, maybe like five or six in parallel, maybe like, you know, coming back and picking the best one in the time you would have taken to not even generate just one. So, we really can't wait to see what that can unlock when you have frontier intelligence, the very best at that speed. It really starts to feel less like waiting for an AI to respond and much more like a coworker that's like already showing you the results as it goes.
</details>

### 从本地到云端的环境解耦

**Alexander**: 说到和同事一起工作，我能调查一下吗？大家在办公室里见过这样的场景吗？（请举手）

好的，好的，哇，看来很多同学都很规矩。我确实看到了前排有些同学举手了。

是的，许多人在离开办公室时会保持笔记本电脑处于打开状态，以便 Agent 可以在后台继续工作。这很有趣，但事实上，我们真正想要的是能够直接合上电脑。我们希望能够在独立的隔离沙箱中并行运行多个任务。

其实，我们从一开始就将目标瞄准了这一点。我们推出的第一个重要产品就是 **Codex Cloud**，而它很快就会迎来一些非常重要的升级。

但更好的是，当我们思考这个问题时，未来不应该在“本地任务”和“云端任务”之间存在如此别扭的界限，以至于你必须自己去纠结在哪里运行什么。

就像我之前所说的，未来的理想体验是：你应该只有一个 Agent，你随时随地可以和它探讨任何问题，而它自己会弄清楚：“好的，我需要做什么，哪个环境最适合我当前的工作”，然后自主选择并调度所有可用的环境资源。

<details>
<summary>Original English</summary>

**Alexander**: Speaking of working with coworkers, um, can I get a show of hands? Who who is familiar with this kind of sight in offices? Okay. Okay, wow, a lot of you are very well behaved. I really see some people up front. Um, so yeah, a lot of people are keeping their laptops open so that agents can keep working. And this is funny, but you know, what we really want is to be able to shut our computers um, and we want to be able to run many tasks in parallel isolated on their own box. Now, we've been actually aiming at this from the start. Our first major launch was Codex Cloud, and it is due for some major upgrades coming soon. But, better yet, as we think about this, the future shouldn't have this awkward distinction between like a local task and a cloud task, and you have to decide where to run everything. Really, what you should have is kind of going back to what I was saying earlier. You should just have an agent, you talk to it wherever, whenever, about anything, and it should figure out, okay, what do I need to do, which environment is right for my work, and use whatever is available.
</details>

**Romain**: 事实上，Theo 在周末刚刚针对这个话题做出了一个预测。这是一条非常敏锐的推文。Alex，你觉得呢？会比 6 个月更快还是更慢？

<details>
<summary>Original English</summary>

**Romain**: In fact, Theo made this prediction over the weekend on this very topic. And it's a pretty acute tweet. Like, Alex, what do you think? Sooner or later than 6 months?
</details>

**Alexander**: 我认为具体的细节可能不尽相同，但这条推文所描绘的变革方向，绝对会比 6 个月快得多。

<details>
<summary>Original English</summary>

**Alexander**: I think the not in maybe not exact details, but the vibe of this tweet much sooner than 6 months.
</details>

**Romain**: 是的，我的意思是，以目前一切演进的速度来看，如果它真的来得更快，我一点也不会感到惊讶。

好了，那么现在你可能会问，今天的现场演示在哪呢？对于这次 AI 工程师大会，我们想做一些稍微不同的尝试。我们认为当前正处于一个非常独特的历史性时刻，值得我们所有人去重新想象我们的工作方式以及构建方式。

因此，我们想邀请一位特别的嘉宾上台，他用 Agent 拓宽了我们对可能性的认知边界，并真正推动了我们在 OpenAI 内部更加深刻地去拥抱 AGI 时代的到来。

那么，请大家热烈欢迎“Claw之父”——**Peter Steinberger** 登台！

<details>
<summary>Original English</summary>

**Romain**: Yeah, I mean, at at the pace at which everything is going is going, I would not be surprised if it's sooner indeed. Um, Well, so now, you might be wondering, where's the live demo today? Uh, well, for this AI engineer, we wanted to do something a little different this time around. And we think it's a very unique moment for all of us to kind of reimagine how we work and how we build. And so, we wanted to bring a special guest who has bent what's possible with agents and really has pushed us to be more AGI pilled uh at OpenAI. So, with that, please welcome to the stage the claw father, Peter Steinberger.
</details>

[观众掌声]

**Romain**: Peter，交给你了。谢谢大家。

<details>
<summary>Original English</summary>

**Romain**: Peter, take it away. Thank you all.
</details>

**Alexander**: 谢谢，Al。

<details>
<summary>Original English</summary>

**Alexander**: Thanks, Al.
</details>

### 外环决策与内环执行的闭环设计

**Peter**: 谢谢，Al。大家早上好。

我非常喜欢这张照片，因为它提醒我，在短短几个月内发生了多么翻天覆地的变化。

我曾经需要同时在屏幕上排列 10 个甚至更多的终端窗口，并且总是在等待其中一个完成，这样我才能把那个 Agent 抽调出来去队列新的任务。在今年一月份，那还被我认为是极高生产力的体现。而今天来看，这多少显得有些滑稽。

我当时以为自己在扮演一个协调指挥的总架构师，但实际上，我只是在做轮询（polling）工作。我自己充当了调度器、路由引擎以及存储上下文的记忆体。

最初，我是与单个 Agent 进行结对编程。但当我在屏幕上排开 10 个终端时，那已经不再是结对，而是我同时在管理 10 个直属下级汇报。

而现在，我主要是与一个长周期运行的“协调经理” Agent 进行交谈，它会将具体的工作委派给底下的 Agent 团队。对于棘手的工作，我仍然可以亲自下场与具体的执行 Worker 共同探讨，但我的默认工作模式已经彻底改变了：我管理的是一个由 Agent 组成的小型公司的“经理”。

有三大关键改变使得这一切成为可能。

第一，**服务器端的上下文压缩**（server-side compaction）使得长周期运行的任务变得足够可靠，以至于我不再需要围绕“单次会话”的局限去刻意优化。

第二，**多 Agent 协同机制**允许单个主程序去创建并引导合适项目的子任务。

第三，**触发器自动化**（automation triggers）可以在某些特定事件发生时主动唤醒协调经理 Agent。

所以，我们有了持久化上下文、委派机制以及触发器。这就是闭环的要素。

而一旦这个闭环顺畅运转起来，你就会立刻发现下一个核心瓶颈，因为瓶颈总是在不断转移。

去年，我主要受制于 Token 的获取限制。我通过加入 OpenAI 解决了这个问题，但我知道这个策略无法被广大开发者推广。

接着，我的限制转移到了本地的计算资源上。当所有这些 Agent 线程在同一时间并行运行时，我的 MacBook 听起来就像是喷气式飞机的引擎。我们主要通过使用独立的测试沙箱（test boxes）解决了这个问题，这样 Agent 就可以在独立的机器上运行它们的测试套件。

现在，我面临的最主要限制是**注意力**（attention）。不像 Token 或计算资源，我无法简单地通过充值或加资源来扩充我的个人注意力。因此，今天最重要的一项技能是决定把注意力花在哪里。

当代码快速闪过屏幕时，你是不是还在目不转睛地盯着 Agent 的执行过程？我知道，这看起来确实很酷，但在使用早期模型时，这确实是必要的。因为你会看到 Agent 偏离了你预期的方向，你必须按下 ESC 键中断它，然后手动输入把它引导回正确的轨道。

但最新一代的模型在理解意图上已经变得如此出色，以至于花时间盯着 Agent 一行行生成代码已经成了有点浪费时间的事情。

想象一下，当有人在我的开源项目上提交了一个 issue 时，

协调经理 Agent 就会被唤醒。它会根据项目的总体目标、维护记录和开发愿景去通读这个 issue，并决定这是否符合项目的调性。如果符合，它就会创建一个专门的 Worker。

那个 Worker 会去深入调查、实现修改、运行测试套件，接着会有另一个 Agent 去评审这个工作结果。

我不需要亲自监视这些 Agent 工作的具体细节，也不需要逐条阅读中间的每一条冗长日志。

当协调经理需要我的时候，它会直接返回一个包含了原始 issue 描述、建议的代码 diff 差异、甚至是演示视频的 PR。或者，它还会提供一个我可以随时通过 VNC 登录进去的实时运行环境。

我只需要审查一次，留下一条反馈，或者直接点击批准，接着这个循环就会继续，并在所有 CI 自动检查通过后完成合入。

Agent 负责运行**内环的执行循环**（inner execution loop）。而我则负责在**外环循环**（outer loop）中设定方向并做出决策。

你知道，Paul 已经在运行类似的版本了。他开发了他的“幕僚长” Agent，它每隔 10 分钟就会被唤醒一次，去协调他在 GitHub 上的所有工作。Agent 会在侧边栏中主动创建不同的讨论线程，以便 Paul 可以在工作需要他引导时随时切入进去。

一旦经理 Agent 变成了长周期运行的实体，将其局限在一台笔记本电脑上显然就显得格格不入了。目前 Codex 已经能够实现在不同主机之间迁移工作。Open Claw 也设计了网关（gateway）和节点（nodes）。

但这两者目前感觉都还不是最终形态。我甚至不希望去思考我究竟在哪里工作。我的 Agent 应该能够智能连接我的任何设备。它们应该清楚哪些任务可以在云端高效解决，哪些任务必须依赖我的本地开发机器。

协调经理不应该是一个被困在某个特定应用界面内的临时会话。它应该是一个我可以随时给它发短信、在 Slack 里引导、或者在任何地方都能收到它反馈的主动助理。说真的，为什么我不能直接和我的 Agent 对话，并让它为我设计并运行这整个工作流循环呢？

我们目前还没有完全解决这个问题。模型的演进速度实际上超越了目前围绕它们构建的软件测试框架（harnesses）以及组织协作流程。而设计这些配套的基础设施，正是下一个待解决的工程问题。这也是在座的各位 AI 工程师大展身手的地方。

未来不是在屏幕上平铺 20 个终端，而是构建更加完美的闭环（loops）。

让我们一起去把它们构建出来。谢谢大家。

<details>
<summary>Original English</summary>

**Peter**: Thanks, Al. Good morning, everyone. You know, I love this picture because it reminds me just how much has changed in a few months. I was juggling 10 or more terminal windows, always waiting for one of them to finish, so I could steal the agent and queue new work. In January, that felt like peak productivity. Today, it feels a little bit silly. I thought I was orchestrating. Really, I was polling. I was the scheduler, the router, and the memory. You know, at first, I paired with one agent. With 10 terminals, I was no longer pairing. I was managing 10 direct reports. Now, I mostly talk to a long-running manager, which delegates work to a team. For tricky work, I can still drop down and pair directly with a worker, but my default changed. I manage the manager of a small company of agents. Three changes made it possible. Number one, server-side compaction made long-running tasks reliable enough that I stopped optimizing around first sessions. Coordination lets one thread create and steer the right projects. And third, automation can wake the same manager when something happens. So, we have persistent context, delegation, and triggers. There's your loop. And once the loop starts working, you discover the next problem, the bottleneck keeps moving. You know, last year, I was primarily constrained by tokens. Now, I fixed that by joining OpenAI. I know I know the strategy does not scale. Then, my constraint shifted to token uh compute. All these threads run at the same time, and my MacBook starts sounding like a jet engine. That's mostly fixed by using test boxes. So, agents can run tests on a separate machine. Now, I'm primarily constrained by attention. And unlike tokens or compute, I can't simply add more of it. So, the most important skill is today is deciding where to spend it. Are you still staring at the agent while the code flies by? I know I know it's it's it feels cool, but with the earlier models, this was necessary. You know, you you you you see the agent go in a direction you don't like, you hit escape, you steer it, you steer it back. But, the latest generation of models is so good at understanding intent that it's a little bit of a waste of time to watch the agent generate code. Imagine someone files an issue on one of my open source projects. The manager wakes up, reads it against the project's goals, notes, and vision, and decides whether it might be a fit. If it does, it creates a worker. That worker investigates, implements the change, runs the tests, and another agent can review the result. I don't need to watch those agents work or consume every intermediary message. When the manager needs me, it returns a PR, the original issue, the proposed diff, maybe a video, or even a running build I can VNC into. I review once, I leave a note, I maybe approve, the loop continues, and it can land after the checks pass. The agent runs the inner execution loop. I set the direction and I make decisions in the outer loop. You know, Paul Paul thought he's already running a version of this. He pinned his chief of staff. It wakes up every 10 minutes and it coordinates his GitHub work. The agent creates threads in the sidebar so Paul can jump in whenever the work needs additional steering. You know, once the manager is long-lived tying it to a laptop just feels wrong. Codex can already move work between hosts. Open claw has a gateway and nodes. But neither feels like the final form. I don't even want to think where I work. My agent should be able to connect to any of my machines. They should know which work can be done in the cloud or which work requires my local machine. The manager shouldn't be a session trapped inside your app. It should be an agent that I can text, steer from Slack, or hear from wherever I am. Really, why can't I talk to my agent and have it design the whole loop for me? We haven't solved that yet. Models are advancing faster than the harnesses and organizations around them. Designing those things is the next engineering problem. That's where all of you come in. The future is not 20 terminals. It's better loops. Let's build them. Thank you.
</details>

**Romain**: 谢谢大家。

<details>
<summary>Original English</summary>

**Romain**: Thank you.
</details>