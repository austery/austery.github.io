---
author: AI Engineer
date: '2026-07-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=grdoOC1BT1s
speaker: AI Engineer
tags:
  - game-development
  - runtime-llm
  - ai-gaming
  - game-personalization
title: AI时代的游戏创作变革：从提示词到运行时大语言模型
summary: 来自 Meta 的专家 Danielle An 与 David Hoe 分享了 AI 驱动游戏创新的最新实践。他们讨论了如何降低游戏开发门槛、利用主美（Key Art）作为 AI 锚点确保美术连贯性，以及通过运行时大语言模型（Runtime LLM）赋予 NPC 实时自主决策能力，并剖析了并行开发工作流与 Token 经济学、内容安全等工程挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Meta
products_models:
  - Gemini
  - Llama
media_books:
  - Ready Player One
status: evergreen
---
### 1. 互动式幻灯片开场与系统介绍 (Interactive Slides & System Setup)

**David**: 大家好，非常感谢大家来听我们的演讲，特别是在午餐时间之前。真的很感激。我是 David，来自 Meta 的 AI 部门。

<details>
<summary>Original English</summary>

**David**: Hello, thank you for joining us before lunch especially. So, I appreciate it. Uh, I'm David from our AI for Meta.

</details>

**Danielle**: 我是 Danielle，Meta 的首席工程师。

<details>
<summary>Original English</summary>

**Danielle**: I'm Danielle. I'm a principal engineer at Meta.

</details>

**David**: 我们今天准备了一组幻灯片。但我们想尝试做点不一样的体验。所以，今天大家看到的不是普通的、非互动的幻灯片，而是可以互动的幻灯片。如果有兴趣的话，大家可以直接扫描这个二维码。我会尽量把它放大一点。如果在听讲的过程中你觉得有点无聊或手痒，可以去扫一扫，看看这个在演示过程中会发生什么。顺便说一下，这个是实时联动的。所以，不同于普通的幻灯片演示，我们这里的每一个 NPC（非玩家角色）都会逐步揭示幻灯片的内容。因此，根据你们想要让现场变得多么混乱，掌控权完全在你们手中。大家都扫好了吗？我要关掉二维码了。现在交棒给 Danielle。

<details>
<summary>Original English</summary>

**David**: And we have a little set of slides here. We thought we'd make a different experience today. So, instead of non-interactive slides, you get some interactive slides. So, if anyone's interested, you can just scan this QR code. I'll try and make it bigger for you. And if you get fidgety, have a go and see what this does along the way. This is linked up by the way. So, instead of slides, each NPC will reveal the slide content. So, depending on how chaotic you want things to be, you have control. Everyone got that? I'm going to close that down. And over to Danielle.

</details>

**Danielle**: 好的，当你们还在摸索这个互动系统的时候，它看起来已经开始起作用了。很好，有很多人在同时控制它。后台其实有一个投票系统来决定谁是赢家。但如果你尝试去……是的。这就像是一个给你派发任务的互动小游戏。不过，在我们继续深入之前，我们之所以要做这个，是因为我们俩在 Meta 共同主导了一部分由人工智能驱动的游戏创作工作。我们从事这项工作已经有一年多了。我们日常工作很大一部分就是使用 AI 来帮助生成游戏，服务对象包括普通创作者、专业创作者以及所有人。既然这是我们的全职工作，我们觉得今天可以带大家体验一下 David 在过去短短 12 小时内做出来的一系列游戏。那么，我们现在正式开始。

<details>
<summary>Original English</summary>

**Danielle**: Yeah, so while you guys are getting the hang of this, it seems to be working. Well, multiple people are controlling it. There's a voting system behind the scenes that will determine who wins. But if you try to yes. It's like a little quest-giving game, but before we go any further, the reason we're doing this is that the two of us are leading some of the AI-driven gaming creation work at Meta. We've been doing that for over a year now. And a lot of what we do on a daily basis is using AI to help generate games for the casual creator, pro creator, and everybody alike. So, given that that's our full-time job, we figured that we will take you on a little bit of a journey on the games that David made in just the last 12 hours. So, now we're going to get started.

</details>

---

### 2. 传统游戏开发的技能壁垒与 AI 带来的门槛扫除 (Lowering the Barriers of Game Creation)

**Danielle**: 既然接下来就要到午餐时间了，而且前面的演讲时间也有点延迟，所以就像 David 刚才说的，我们非常感激大家能在这里。但我们也应该坦诚面对大家来听这个演讲的原因，以及我们能带来什么价值，或者不能带来什么价值。我们想象，如果你来听这个演讲，说明你是一群对游戏非常感兴趣的人，也许你平时玩很多游戏，或者至少你对游戏是如何制作的有些兴趣。更棒的是，如果你希望在未来自己动手制作游戏，或者你以前就做过游戏，并且好奇 AI 将会如何改变这一切。所以，这就是适合你们的演讲。但如果这些对你来说都不太感兴趣，至少你可以在午餐前开心地玩一玩这个小游戏，增加一下你的食欲。

在 2026 年，你们中的很多人可能已经在 **Gemini** 上构建过一些小游戏，比如平台跳跃类游戏，或者俄罗斯方块之类的。如果你自己没做过，也许你的孩子、你的妈妈、你的朋友们已经做过了。这概率非常高，非常有可能。

起初，这确实让人印象非常深刻。因为只需要输入两三个 Prompt（提示词），你就会惊叹：“哦，这是一个游戏，我能认出这是一个游戏了。”如果你足够幸运，它甚至能开箱即用，直接运行，但并不是百分之百能保证。

但问题在于，随着时间的推移，大家都会发现这种新鲜感开始消退。因为你输入的很多 Prompt 其实都是大同小异的。如果每个人都说：“我想要一个看起来像超级马里奥的平台跳跃小游戏。”如果这些游戏能够运行的话，它们整体上看起来其实都很相似。所以，过了一段时间，大家就会觉得：“接下来呢？虽然这很酷，但下一步是什么？”这就是我们现在面临的状况。

<details>
<summary>Original English</summary>

**Danielle**: So, because there's lunch and the previous talks are a little bit delayed, so we appreciate you being here like David was saying. But we should also be honest about why you're here and we want to tell you what kind of value we might bring or not bring. So, we're imagining if you come to this talk, you're people that are very interested in games, maybe you play a lot, or at least you're somewhat interested in how games are made. And even better, if you wanted to make them in the future or if you made them in the past and you you're wondering how AI is going to change that. So, this is the kind of talk for you. But if none of that is interesting to you, at least you can just have fun play the game before lunch and work up your appetite.

But um now we're going to get going on to the real part. In 2026, a lot of you probably have either built something like a little game, like a platformer game, or a Tetris or something on Gemini. If you have not, maybe your kids, your moms, your friends have built them. Very chances are it's a very likely. And initially, it's very impressive cuz within a couple prompt, you're like, \"Oh, here is a game. I can I can recognize this.\" And if you're lucky, it works out of the box, but not guaranteed. But the problem is that as time goes on, you would all see that the novelty kind of wears off and a lot of what you prompt is the same. If everybody says, \"I want a little platformer game that looks like Mario.\" Overall, they all kind of look similar if they work at all. So, after a while, it's like, \"What's next? This is cool.\" So, that's um Yeah, we're all moving a lot here.

</details>

---

### 3. 主美锚点工作流与游戏内的一致性美学 (Key Art Workflows & Cohesive Aesthetics)

**Danielle**: 是的，我们大家在这个场景里移动得都很频繁。看来大家都想看清楚屏幕上显示的文字到底是什么。（笑声）所以大家最好能先稍微保持静止一会儿，虽然我不知道现场具体有多少人。实际上，我不确定这里有多少人，但有很多很多的人正在控制屏幕上的角色，所以画面很难稳定下来，这也是这个游戏的一部分。

但我们要表达的核心观点是：现在每个人都可以在周末轻松做出一款游戏，但接下来会发生什么？这意味着什么，尤其是对整个游戏行业而言？在我们看来，这意味着以前很多想要做游戏的人，因为自身技能的限制而被阻挡在外。比如我是一个程序员，但我不是艺术家。我不会做 3D 建模，不会画画，也拿不到合适的美术资源。但现在，你可以直接使用 **Meta Banana** 或者 **Mesh** 这样的 AI 工具，或者其他类似的工具，来打破这些瓶颈。

同样地，对于那些以前非常想做游戏，但可能缺乏编程技能的艺术家来说也是如此。以前他们不得不等待工程师配合，或者干脆觉得这完全不可能实现。对于想要抓住这个时代机遇来制作更多游戏的人来说，虽然门槛已经被扫除了，但这并不意味着每个人都能做出一款真正优秀的游戏。

那么，决定一款游戏究竟是好是坏的分水岭在哪里？其实依然取决于那些经典的要素。在这里，我们将向大家分享我们在过去一年中，在 AI 游戏构建方面所学到的一些经验和窍门——那就是：你该如何脱颖而出？

我希望到目前为止大家还没有觉得太无聊。究竟如何脱颖而出呢？这里有几点建议。首先，通常最重要的是**美学（Aesthetics）**，对吧？当你在体验过几次提示词生成游戏后，你肯定不会再满足于一个紫色方块在绿色方块上跳来跳去的简易平台界面。这其中有大量的美术门槛和讲究。此外，你所制作的游戏，其 UI、故事和美术之间也必须具备极高的**连贯性（Cohesion）**。这些元素是否感觉像是一个整体？它们看起来是否像是存在于同一个宇宙之中？然后，这里还有大量的游戏测试（Play Test），以及来自真实玩家的真实反馈，他们会明确告诉你什么是好的，什么是不好的。不过，我们直接来看一段视频，也许 David 可以对这段视频所要表达的核心观点进行一下点评。

<details>
<summary>Original English</summary>

**Danielle**: So, people want to see what the text actually is. [laughter] It's good to just kind of not move for a while, but I don't know how many people are here. Actually, I'm not sure how many people are here, but a lot of people are controlling, so it's hard to stabilize, which is a part of the game. But the point here is that everybody can build a game over the weekend, but what is the next thing? And why What does this mean really to the industry? And like in our opinion, what this means is just a lot of people previously who wanted to build games, but were gated by skill sets. For example, I'm a coder, but I'm not an artist. I cannot do 3D modeling. I cannot draw. I cannot get art. But now you can just use Meta Banana or Mesh you or whatever else to get yourself unblocked. Um same thing with artists who previously really wanted to build games, but maybe they don't have the coding skills and so they have to wait for engineers or they just feel like that's not possible. For a set of people that really want to utilize this moment to build more games, if the barriers are removed, but then that doesn't mean everybody can make a good game. What will make What it will separate a good game versus a bad game is still a lot of the typical stuff. And here we're going to share with you some of the tips that we've learned in the last year working on AI game building, which is how do you stand out? Um I hope so far you're not too bored. How do you stand out? Um here's a few things. Like one is usually aesthetics, right? Like after you prompt a few games, you just you're not satisfied with like a little box that's purple next to a box that's green that shows like a platform. There's a lot of art to that. There's also a lot of cohesion to the game you make between the UI and the stories and then art. Is Does it feel like one entity? Does it feel like it's one lives in one universe? And then there's also lots of like play tests and like the real people with real feedback who tell you what is good. But um just going to directly go to the video that maybe David can comment on what what's the point of this video.

</details>

**David**: 好的，这段视频来自于和我们一起工作的一位美术总监 Dale。他在这里想要展示一个大家可以尝试的示例工作流。这主要是关于如何使用**主美艺术（Key Art）**作为锚点，来引导和统一其他的生成模型。就像传统游戏开发一样，在迭代过程中，你可能会突然发现一个你非常喜欢的概念。对于 AI 模型也是一样的道理，你可以仅使用一张主美图作为整个游戏的视觉灵感来源。在这个例子中，你可以看到主美图是一个非常可爱的熊的形象。

这其中的区别在于，这幅图基本上成为了你美术风格的锚点。你可以据此过滤和筛选出你之后看到的这些美术资产。同时，它也能帮助你锚定游戏的核心玩法。所以，它实际上承载了非常多的信息，而且是一个非常简单、高效的入门方式，能够让 LLM（大语言模型）在整个创作会话过程中保持极高的连贯性。是的，这段视频就是展示这个过程的。

<details>
<summary>Original English</summary>

**David**: Yeah, so this is the a video from one of our art directors that we work with, Dale. And he wanted to demonstrate here example workflow that you can try out, which is really about using key art as a an anchor for the fellow models. So, just like game development, you might have a stage where you're iterating and you come across like a a concept that you really like. So, same thing with the models, you can use just a single key art image for game for inspiration. In this case, you can see the key art was a lovely bear example. And the difference here is that you go from being able to, you know, um it basically anchors you on um having a an image that you can use for the art style that you can then filter down to the assets that you can see here before, but also it can also help anchor on, you know, what the gameplay could be. So, it actually holds a lot of information and it's a very simple way to get started and allow for the LLM to have some cohesion throughout the sessions as well. So, yeah, that's just demonstrating that.

</details>

---

### 4. 运行时大语言模型驱动的动态 NPC 决策 (Runtime LLM-driven Dynamic NPCs)

**Danielle**: 好的，这应该能向大家展示出，你自己或者你孩子随手 Prompt 出来的游戏，与专业制作的游戏之间的差距。而这个差距已经被大大缩短了，因为正如 David 所说，现在有非常多的 AI 工具可以帮助你实现这一点。

然而，一旦你达到了基本的水准，觉得“好吧，这看起来已经像一个像样的游戏了”，那么最重要的事情就是：在所有的游戏看起来都非常有质感和抛光度（Polished）的时代，是什么让你的游戏脱颖获胜？是什么让你的游戏成为“最好的（Best）”，而不仅仅是“更好的（Better）”？正如身处 AI 时代的每个人都会说的那样，答案是**品味（Taste）**。这对于游戏的真正意义在于，你不仅仅是交付了一个游戏，而是你拥有一种能够洞察人类会喜欢它的直觉——知道哪一部分人群会喜欢它，以及他们为什么会从中获得乐趣。

一旦你达到了这个水准，你可能会觉得：“啊，太棒了，我现在能做游戏了。”但问题在于，事情并没那么简单，因为现在我们又引入了新的技术——**运行时大语言模型（Runtime LLMs）**。这意味着，在你玩游戏的同时，有一个活生生的实体，也就是运行时 LLM，它在实时修改、改变游戏，并以某种方式引导着游戏。这里是另一个相关的例子。David，你想对此发表一下评论吗？

<details>
<summary>Original English</summary>

**Danielle**: So, this hopefully shows you that what the difference between something you can prompt or your kids can prompt versus a professionally made game. And the distance is shortened by a lot because what David is saying, all the AI tools that can help you with that. Um but another once you get to the basic level of like, \"Okay, this looks like a decent game.\" One of the most important things is what will make your game stand out if every game looks polished? What makes your game the best, not just better? And what makes it the best is the same as everybody know in the AI age would say is the taste. What it really means to the games is that it's not that you delivered a game, but it's that you have the feel that this is a game humans would like. And which subset of the humans would like and why they would have fun with that. Like what are Um And then once you reach that level, you're like, \"Ah, great. Now I can make a game.\" Now, the problem is that not quite because now there's introduction of new technology, runtime LLMs. Um what that means is that while you are playing the game, there is a living entity, the runtime LLM, that is modifying, changing the game, directing the game in some way. Here is another example of that. Would you like to comment on that?

</details>

**David**: 好的，我们团队也是花了几天时间做出了这个游戏。这是一款多人游戏，在这里的每一个 NPC 都是完全由运行时大语言模型驱动的。在这个部分，人类玩家正在设置一个竞争性的游戏。这是四个玩家彼此对抗的游戏。

在设置阶段，通过指定 NPC 应该做什么，给它赋予一个独特的性格——比如它可能是一个小偷，可能非常具有荣誉感，可能速度非常快。无论它拥有什么样的性格，游戏现在就要开始了。

然后你会看到，这些运行时 LLM 会独立做出决策，去实现这个游戏的目标，在这个游戏中也就是收集尽可能多的方块。

但当你观看游戏过程时，你会发现有些 NPC 会自主做出决策去偷取其他 NPC 的方块，或者去阻挡其他 NPC，甚至是去踢其他 NPC。这些完全不是预先写好的脚本。这些完全是由运行时大语言模型驱动的实时自主决策。所以，这为游戏增添了非常多的乐趣和动态性。每一局游戏都是独一无二的，且完全不可重复。在过去 18 个月 AI 被引入之前，这在整个游戏行业是完全不可能实现的。但现在，因为推理时间足够快，且模型足够便宜，我们终于能够真正构建出这类游戏了。同样，这也仅仅是花了几天时间构建出来的。

<details>
<summary>Original English</summary>

**David**: Our team built this again just over a couple days and this is a multiplayer game where each of the NPCs here is entirely driven by LLM. So, this is the part where the humans are setting up a competitive game. It's a four four players playing against each other. And by specifying what the NPC should do, giving it a personality, maybe it's a thief, maybe it's very honorable, maybe it's very fast. Whatever personality it has, now the game is about to begin. And you will see these runtime LLMs independently making decisions, achieving the goal of this game, which is to get as many cubes as possible. But as you watch, you will see some of the NPCs will make decisions to steal other NPCs' cubes or block other NPCs, kick other NPCs. These are entirely not scripted. These are runtime LLM-driven decision-making. So, it just adds a lot of spice, a lot of dynamicness to the games. Every game is unique. Every game is not repeatable. And so, that is a new form before the introduction of AI in the last let's say 18 months which is now possible. So now we're sort of experimenting a lot with this genre of games where you can see these NPCs starting to fight with their personalities. You can obviously design the game to be more spicy um or more friendly, co-op or competitive. And again, the point of these games is that they were previously not in the industry made it was just not possible to make them, but now the inference time is fast enough the models are cheap enough for us to actually build these kind of games. Again, build over a couple days.

</details>

---

### 5. 并行化工作流与大模型时代下的工程挑战 (Parallel Workflows & Scalability Challenges)

**Danielle**: 接下来，我们要分享一些我们在过去 12 个月中带领这些多学科团队所学到的经验。感觉像是过了 12 年一样漫长。管理跨学科的团队，我们使用 AI 工具学到了什么？它又如何改变了构建游戏的体验？

简而言之，它改变的第一件事是成本。在过去，制作游戏是非常昂贵的，因为这是一个线性的过程，从一个部门流转到另一个部门。你必须先做设计，然后做美术，接着做 3D 建模，可能还要做动画，最后才是写代码。这完全是一个线性的瀑布模型。这意味着，一旦你决定做一款游戏，你就很难再回过头去修改上游的决定。那样的代价极其昂贵。但是现在，因为 AI 的存在，我们实现了团队的并行化工作。对游戏的更新和迭代可以在几个小时、几天内完成，而不是以前的几个月。这带来的改变是革命性的，游戏变得更加有趣，因为你有更多的时间去进行游戏测试。在游戏点子上的迭代时间变得更充裕，而不仅仅是线性地执行计划。这绝对是一个游戏规则的改变者。

我们学到的第二点，除了在品味方面，就是通过大语言模型和运行时决策，游戏里可以有一个“游戏大师（Game Master）”来帮助你让游戏变得更加个性化，对你来说更有趣。例如，以我为例，我是一个协调能力比较差的人。所以当我和朋友们玩游戏时，如果是合作模式，我总是那个拖累团队的人。在过去，这常常让我放弃玩游戏，因为我觉得自己一直在拉团队的后腿。但如果大语言模型能为我实时调整这一点，让我依然能和我的团队一起玩并乐在其中，这就是一个巨大的进步，这在以前是完全不可能的。

另一个收获就是，正如我们之前所说，运行时大语言模型将成为改变游戏规则的力量。但就像任何其他技术一样，技术本身并不能直接让产品变得更好。和许多团队一样，我们目前仍处于探索如何使用运行时 LLM 的早期阶段。我们总是会联想到类似《星际迷航》里的场景，对吧？你只要说：“想象我面前有一片森林，现在我在猎熊。”然后这一切就突然呈现在你面前了。我们确实预见这终有一天会成为现实，但目前这还不是现实。所以，如今如何利用运行时大语言模型来让你的游戏在与其他游戏的竞争中脱颖而出，这仍然是我们在不断探索的领域，很多人对这个方向都非常感兴趣。

但总的来说，面临的挑战依然非常多。我想无论是身处游戏行业还是其他行业，每个人都能真切感受到的一点是，AI 每天都在改变我们所做的事情，从使用的工具、到我们的代码库、再到对“什么是优秀”的定义。仅仅跟上这种变化本身就已经非常困难、非常具有挑战性，但同时也非常有趣，如果你喜欢这种探索，它会带你走得很远。

现在你可能注意到了，系统好像有点出问题，角色现在拒绝和 NPC 说话了。

接下来我想谈谈这套技术栈在平台和工程层面的巨大挑战。我们是在 Meta 工作，Meta 非常看重能够服务成千上万创作者的平台建设，尤其是现在每个人都能轻松创作，海量的游戏内容正准备上线。在这个过程中，我们的核心挑战之一就是整个技术链条上的“非确定性”（Non-determinism）。

从最前端的用户通过 Prompt 进行创作，到游戏运行时的 LLM 实时进行决策（就像我们刚才展示的游戏），再到后端的平台内容分发、推荐和分级算法，整个全栈系统里都在引入各种智能体和 Agent 系统。

对于我们工程师来说，特别是在面对大规模高并发的系统时，我们现在正为此苦苦挣扎。因为在过去，我们习惯的工程逻辑是：写代码、写测试、保证系统稳定性，我们在一个已知且确定的代码库上进行调试、扩展。这才是我们过去所理解的“稳定”和“可扩展”。但现在的时代，如果你的大模型在不断更新、你的 Prompt 在频繁变化，任何一个微小的改动都有可能彻底掀翻你原有的系统稳定性。面对这样一套完全由 AI 模型构成的非确定性系统，我们该如何进行 Debug？我们该如何与这样的系统共处？这依然是一个巨大的工程挑战。

<details>
<summary>Original English</summary>

**Danielle**: So next um we're going to share some learnings from us driving these teams in the last 12 years uh 12 months. Feels like 12 years now. Um directing teams um across disciplines and what have we learned using AI tools and how does it change the game building experience? Um briefly the first thing it changes is in the past building games are very expensive because it's a linear kind of process. From one department to another, first you design and then you go to like art, then you go through modeling, potentially you go through animations, you go through coding, but all of this is kind of like a linear waterfall model. And what that means is that once you commit to making a game, it's very hard to revisit the decisions upstream. That's very very costly. But nowadays because of AI we have achieved teams that are working in parallel and updates and iterations on the games are achieved in hours, days as opposed to months. What this achieves is just that games are more fun because you have more play test. You have more um time to iterate on the game idea as opposed to just linearly executing and this is a game changer.

And the second thing that we've learned uh on on top of the taste it's just with LLMs, with runtime decision making, it the there's a game master that can help you make the game more personal, more interesting for you. For example, for myself, I'm not very um I'm coordination challenged. So when I play games with my my friends, I'm always if it's co-op, I'm always the one that is like tanking the team. And in the past, it just sometimes stops me because I feel like I'm just dragging the team behind. But if LLMs can adjust that for me, allow me to still play with my my team and have fun, that is big win that that previously was not possible.

Another learning is as we previously said, runtime LLM is going to be a game changer. But just like any piece of technology the technology itself does not make the product better. We are just like a lot of the teams still at early phases of exploring how do you use runtime LLM? We imagine a lot of these kind of things like Star Trek, right? You say, \"Imagine in front of me there's a forest and now I'm hunting bears.\" And then it just suddenly happens. We do see that eventually becoming reality, but it's not currently the reality today. So today how do you use runtime LLMs to drive your game to be differentiating against other games is still something we're exploring and a lot of people are very interested in this area.

But in general, there's lots of challenges. I think everybody, whether you're in the game industry or other industry, what do you do feel is that every day AI is changing what you're doing from the tools from to your code base to what good looks like and just keeping up with that has been very hard, very challenging um but also very interesting um if that's the kind of thing that you like, that's going to take you a really long way. Um It's refusing to talk to the NPC now. Um

And the last bit I'll talk about this kind of technology driven is now you imagine we work at Meta like Meta cares about being a platform of millions and millions of piece of gaming content that will come online especially now that everybody can create. One of the main challenges is just that through all of a agentic systems from the front end where the user is prompting potentially to runtime the LLM is making decision like the game we showed we showed before to the platform serving content, ranking content delivering content. Through the whole platform there's a an agents and agentic systems at play. So that just means and determinism throughout the whole stack which is something that as engineers, especially at scale, we are struggling a lot with in general, right? Because we're used to thinking that you write code, you write test, stability, debugging against a set known a known set of code base is what we call stability and scalability. But now in these days, if your model is changing, model upgrades, if your prompts is changing, a lot of things can in in entirely throw off your system. So how do you even debug that? How do you um engage with systems like that is still challenge.

</details>

---

### 6. 个性化体验与未来展望 (Personalization & The Ready Player One Future)

**Danielle**: 不过，既然我们现在只剩下 2 分钟了，而且快到午餐时间了，让我们说一些能让我们和大家每天都倍受鼓舞的话。那就是，AI 正在彻底改变整个游戏行业，而我们现在正处于“第零天（Day Zero）”。对于那些读过或看过《**头号玩家**》（Ready Player One）的人来说，我们认为我们正处于那个让“绿洲（Oasis）”能够真正成为现实的起点。

所以如果你想成为其中的一部分，我真的很希望你们能去探索她，因为如果你去探索她，这里有非常酷的东西。求求你了，让我们转向她。（笑声）

呃，求你了，能转到她吗？

啊，好的，转过来了。我个人非常喜欢 **Labubu（拉布布）**。所以，这就是个性化的瞬间之一。通过 AI，你可以把任何游戏导向你想要的任何方向。对我来说，构建这样一个瞬间，就意味着你可以创造一个由 Labubu 构成的宇宙，你可以成为任何你想要的 Labubu，收集任何你想要的 Labubu。

最后，在大家去吃午餐之前，给大家一个小小的带走思考。不管你现在处于什么阶段，也许你从来没有做过游戏。那么你本周末的任务就是——周末马上就要到了——你可以尝试使用任何你最喜欢的模型，也许是 **Gemini**、**Llama** 或者是其他任何模型，去尝试 Prompt 出一个非常基础的游戏，比如俄罗斯方块或者跑酷游戏，随心所欲，看看它会做出什么。它可能会失败，但当它给你带来惊喜且运行得很好时，它也会给你带来无尽的快乐。

又或者，你可能已经经历过了那个阶段，这也正是你来听这个演讲的原因——你正在思考：“下一个阶段是什么？”对于你们来说，下一步可能是我们之前提到的，用更精致的美术、更好的 UI 和出人意料的惊喜来升级你的游戏，让它感觉不再是一个直接 Prompt 出来的简陋半成品，这样你就可以上传并分享它。

但如果你已经超越了那个阶段，你是一个关心系统可扩展性的工程师，那么就需要考虑 **Token 经济（Token Economy）**了。你如何确保创作者、玩家和平台在 Token 经济中能够实现盈利？

此外，**内容安全（Content Safety）**也是目前更大的挑战之一。你如何确保通过运行时大语言模型实时生成的图像和内容对你的受众来说是绝对安全的？这其中依然有许多悬而未决的挑战。

好的，时间已经到了。非常感谢大家能来听我和 David 的演讲。感谢大家的参与，以及与 NPC 们的互动。希望大家玩得开心，现在可以去吃午餐了。谢谢！

<details>
<summary>Original English</summary>

**Danielle**: But since we have only 2 minutes left and it's about lunch time let's say something like that is that inspires David and I on a daily basis is that this just means that for the whole gaming as an industry is being transformed is being transformed by AI and we're day zero. So for those of you who have read or seen Ready Player One, this is the moment where we think we're at the beginning where that Oasis can actually be a reality. So if you want to be part of that you're going to I do really hope you guys navigate to her cuz there's something very cool here if you navigate to her. Hello, please. [laughter] Uh Come on, please. Can we go to her? Ah, yes. So I personally love Lububu. Um so this is the one of those personalization moments where with AI you can steer any game towards anything that you want. And for me building this moment just means that you can create a universe of Lububus and you can be any Lububu you want, you can collect any Lububu you want.

And last but not least, a little bit takeaway before lunch is wherever it is you are, maybe you've never built a game. So then the task here for the takeaway for you is the weekend is coming. You can just use any of your favorite models, maybe Gemini Manas, whatever it is, just try to prompt a very basic game like Tetris or um a infinite runner, something that you play and just see what what it does. It's going to fail, it's going to bring you delight when he surprises you and it works really well. Or maybe you are the people that already went through that phase and that's why you're in this talk where you're like, \"What is the next phase?\" The next thing for for you is probably something we mentioned prior is to upgrade your game with art, with UI, with surprises so so it doesn't feel like it's something that is prompted out of the gate so you can upload there. But if you're beyond that as well, then if you're engineer that cares about scalability, then think about tokens. How do you make sure creators, players, and platform with token economy are going to be profitable um and content safety is one of the bigger challenges is how do you make sure with runtime LLM, maybe potentially generating images and content, you know that the content is actually safe for your audience. There's a lot of open challenges there. Whoever it is you are and I mean negative time. So thank you very much for being here from me and David. Thank you for the participating and working with the NPCs. Hopefully you had a little fun and go to lunch. Thanks.

</details>