---
author: How I AI
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1gYQc4CL_oo
speaker: How I AI
tags:
  - ai-model
  - coding-assistant
  - creative-coding
  - benchmark
title: 从厌恶到真香：Fable 5.2 如何改变了我对 Claude 的看法
summary: 讲述者分享了自己曾因早先 Fable 与 Opus 5 的交互体验而转用 Codex，但最新发布的 Fable 5.2 凭借极快的响应速度、强大的几何与空间理解、长程工程重构能力以及出色的创意与动画生成能力，彻底改变了其态度。文中评测了其在视频制作、3D打字机搭建和工程任务中的表现，同时也指出了其在前端与网页设计审美上的不足。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Claire
companies_orgs:
  - Anthropic
  - OpenAI
  - Vercel
products_models:
  - Fable 5.2
  - Opus 5.5
  - Claude Code
  - Claude Mythos 5.2
  - Codex
media_books: []
status: evergreen
---
### 从“Claude 黑粉”到重回怀抱

如果你一直关注我最近的节目、模型评测，以及我对日常工作流的分享，你就会知道一件事：我算是个“Claude 黑粉”。

令人惊讶的是，这种情绪始于他们发布 Fable 的时候。我记得 Fable 刚面世时，它在智力上确实带来了巨大的飞跃，但同时也残酷地提醒了我们一点：高智商并不意味着容易沟通。这就导致我非常讨厌与 Fable 一起工作。Fable 实在太难协作了，交流起来让人非常恼火，而且很难理解。Opus 5 也是如此。尽管它可能确实能把活干完，但它绝不是一个能带来愉悦体验的模型。

与此同时，在几个月前那些模型发布的时候，我感觉 Codex 在桌面应用的某些锦上添花的体验环节上，确实大幅超越了 Claude Code。因此，Codex 成为了我最喜欢的办公与编程工具。这不仅是因为它作为一个面向软件工程师的环境体验很好，更是因为它的浏览器控制（browser use）和计算机控制（computer use）功能简直比 Claude Code 领先了数光年。

<details>
<summary>Original English</summary>
If you've been paying attention to my recent episodes, my model reviews, and how I talk about how I work, you know this. I am kind of a Claude hater.

Surprisingly, this started when they released Fable. I remember Fable showing up and it was such a huge leap in intelligence and such a stark reminder that intelligence does not make you intelligible, which meant I hated working with Fable. Fable was so hard to work with, so annoying to talk to, so not easy to understand. Same with Opus 5. Just not an enjoyable model to work with, even though it maybe got the job done.

At the same time, those models had come out a couple months ago, I felt like Codeex really outpaced Claude Code in some nice to have experience pieces in terms of their desktop app. So, Codeex became my favorite place to work and code. Not only because it was a nice place as a software engineer, but things like browser use and computer use were just light years ahead of Claude Code.
</details>

但我现在要坦白一件事：我现在重新回到了主要用 Claude Code 和 Opus 5.5 编程的状态。今天我必须告诉大家，这种热爱是真真切切的。今天我彻底成了一个兴奋到喘不过气的“AI 老哥”。对此我深表歉意，我通常会尽量克制自己不这样，但 Fable 5.2 已经来了，我真的爱死它了。我太喜欢它了。它固然有自己的缺陷，但它是一个速度极快、能力超强、一点也不招人烦、富有创意且功能强大的强悍模型。它绝对有它的缺点，但你猜怎么着？它不擅长的那些方面，我们的好兄弟 Opus 5.5 恰好很擅长。

一旦我们所有人都能用上这个模型，我简直要在社会上“横行霸道”了，我打算用它做超多的东西。我认为这可能是一个真正打开消费级 AI 大门的基础模型，因为你能用它做出的酷炫事物实在太多了。我非常喜欢 Fable 5.2，今天我们要带来一期即时加映的迷你短剧集，向大家介绍我是如何测试这款模型的、我认为它的长处在哪里、哪些方面还需要一些改进，以及为什么我觉得自己又变成了一个“Claude 铁粉”。让我们切入正题吧。

<details>
<summary>Original English</summary>
But I have a confession. I am back to coding with mostly Claude code and mostly Opus 55. And today I have to tell you the love affair is real. I am going to be breathless AI bro. today. I am I apologize. I usually try to avoid this, but Fable 52 is here and I love her. I love her. I love her. She has her flaws, but this is a fast, capable, not annoying, creative, powerhouse of a model. It absolutely has its drawbacks, but guess what? the things that it is not good at, our buddy Opus 55 is good at.

Once we all have access to this model, I'm going to be a true menace to society. I'm going to build so much stuff. I think this might be the model that unlocks consumer AI because there is just so much cool that you can do with it. I love Fable 52 and today we're going to do a just in time mini episode telling you how I tested this model, what I think it's great at, where it needs a little bit of work, and why I think I'm a claw boy. Let's get to it.
</details>

### Fable 5.2 的定位与基础特性

那么，让我们先过一遍基础信息，然后我再向大家展示我用 Fable 5.2 构建的所有令人惊叹的项目。

是的，今天 Anthropic 正式发布了 Fable 5.2，同时推出的还有 Claude Mythos 5.2——它们底层是完全相同的模型，只是 Mythos 专供网络安全和生命科学领域使用。它们代表了 Anthropic 的前沿级模型，而且这个新家伙确实非常惊艳。它并不是要取代 Opus 5.5。事实上他们官方也表示，大部分日常的编程与知识型任务依然属于 Opus 5.5 的职责范畴。但是当你面临庞大的规模、复杂的架构，以及更具创意性的工作时，Fable 5.2 的表现极为出色。

关于 Fable 5.2 将会有铺天盖地的新闻报道。其中我最喜欢的一条是，在科学研究领域，它解决了黑洞物理学中的两个未解难题。今天早上在餐桌旁，我就是把这条趣闻讲给我的孩子们听的。我对它在生命科学与硬核科学前沿的潜力感到无比兴奋。

不过，让我们还是把注意力聚焦在编程上。官方宣称它非常擅长处理棘手的 Bug、性能优化、系统架构设计以及长程运行的复杂任务。它能够完成大规模的代码迁移，甚至能够构建类似操作系统的系统。而在我实际的使用体验中，它的运行速度极快。你将会看到很多惊人的基准测试成绩，在各大模型最高投入算力级别（highest effort level）的测试下，它基本上全面超越了现有的各类前沿模型——无论是 Frontier Code、Frontier Suite 还是 Automation Bench，在各项测试中它的表现都极其优秀。我准备把它放进完整的 How I AI 基准测试中去跑一遍。今天大家会看到其中的部分预览，但我之后会针对所有最新模型进行一次完整的端到端评测。今天这期只是一期迷你节目，分享我对 Fable 5.2 的初步印象。

<details>
<summary>Original English</summary>
So, let's get through the basics and then I'll show you all the amazing things that I built with Fable 5. So yes, today is releasing Fable 52 alongside Claude Mythos 52 which is the same underlying model but just available for cyber security and life sciences purposes. They are anthropic frontier model and this baby is a banger. It is not a replacement for Opus 55. In fact they say most daily coding and knowledge tasks are Opus 55 tasks. But when you need scope, complexity, and I would say creativity, Fable 52 is amazing.

There are going to be so many headlines about Fable 52. My favorite is that in science, it solved two open problems in the physics of black holes. This is the little tidbit I told my kids this morning at the kitchen table. I am really excited about the frontier in terms of life and hard sciences.

But let's focus a little bit about coding. What they say is it's really good at stubborn bugs, performance optimization, architecture, and long running tasks. Um, it can do huge migrations. It can build things like operating systems. And I will tell you my experience is it's very fast. You're going to see a lot of amazing benchmarks. It's basically outpacing all the Frontier models at each model's highest effort level. Frontier code, Frontier Suite, Automation Bench, all of them. It is doing really well. I am going to run it against the full how I AI bench. We're going to see a preview of that today, but I want to do the full end to end against all the newest models. And today is just a mini app on my impressions of Fable 52.
</details>

现在，就像他们所有带深度思考的模型一样，它也设有你需要了解的防护栏（guardrails）。但我必须说明，在我自己的测试过程中，我没有触发其中的任何一条。这可能与我当时测试的具体内容有关，但我还是要重申，这个模型在协作时完全不会让人觉得恼人。真的很棒，非常感谢 Anthropic 团队。

当然，该模型依然保留了网络安全和生物领域的防护栏，除非你加入了 Mythos 项目。此外，该模型内部还包含大量的防蒸馏保护机制。关于具体的技术细节与调用成本，我们稍后再作讨论。

<details>
<summary>Original English</summary>
Now, like all their thinky models, there's going to be some guard rails that you need to know about, but I will say in my testing, I didn't come up against any of them. It might have to do with what I was testing, but I will say again, this model was just not annoying to work with. Love it. Thank you, Anthropic team.

So, there are still cyber and bio guard rails on this model, of course, unless you're in the Mythos program. And there's also a lot of anti-distillation safeguards in this model. We'll talk about what it is, what it costs a little bit later.
</details>

### 高层体验盘点：优势与短板

那么，在亲自上手使用了几天之后，我对这个模型的宏观感受是什么？

**优点方面**，首先是它速度极快。事实上我曾特意询问过 Anthropic 团队：“这真的是它在正式发布时的速度吗？”因为它的响应实在太迅捷了。我几乎从未觉得自己在做不必要的等待。这不仅体现在单轮交互的吐字与生成速度上，还体现在它的自主执行能力上——它在确实需要用户决策时才会发出提醒，绝不做多余的打扰。所以它的速度是真的很快。

其次，它非常擅长创意类工作，并且在创意发挥上表现突出——不过有一个例外，我稍后会讲到。它非常擅长生成视频，尤其是细节极其丰富的视频生成。在这一期节目中大家会看到许多有趣的视频，因为我对能用它做出来的东西感到极度兴奋。在 3D 和游戏开发方面，我认为它迈出了很大的一步。我不会去搞那种 AI 油管博主常做的赛车游戏，但我确实做了一款小游戏，而且我觉得它非常好玩。

在编程方面，它的表现极其出色。它帮我完成了一些系统架构与重构方面的工作，处理了多项长程工程任务，这些都是之前的模型（例如 Opus 5.5、Astra 等）未能真正顺利搞定的，而且它的配合度很高，绝不烦人。

**缺点方面**呢？它很不擅长前端开发和网页设计。在后续展示的一些评测和成果中大家也能看得出来。如果你为它提供了一套优秀的品牌指南或风格设计规范，它能够很好地理解并遵循规范，做出来的东西非常得体、极具品味；但如果让它自由发挥，它的审美倾向就会非常令人担忧。可以说，它在自主设计上真的缺乏好的品味。

此外，我认为它缺乏配套的图像生成模型这一点也被放大了。因为当一个模型本身极具创意时，你会希望它在各个层面上都能展现创意。而在很多时候，我发现自己不得不频繁调用 OpenAI 的 Image Gen 2.5 来生成图像，因为 Fable 在这方面表现确实不好。

因此从宏观角度来看，我未来绝对会高频使用这个模型，我是真的非常喜欢它。不过在展开后续完整的 How I AI 基准测试之前，我想先展示几件它极其擅长的具体成果。

<details>
<summary>Original English</summary>
Okay, so what are my highle takeaways of this model having hands-on experience with it for a couple days? The pros are it's really fast. I in fact asked the anthropic team, is this as fast as it's going to be at launch? Because it was super fast. I never really felt like I was unnecessarily waiting for the model. And that's both the speed of individual turns as well as its autonomy and its willingness to alert me when it needed something, but no more than that. So, it's really fast.

It's also really good at creative work and at being creative with one exception, which I will talk about. Um, it's great at video generation and detailed video generation. You're going to see a lot of fun videos in this episode because I am super excited about what I was able to build. Um, 3D and gaming. I think it's a step up. I'm not going to do one of those like AI YouTube bro race car games, but I did make a game and I thought it was pretty fun. It is really great at coding. It has helped me with some architecture rearchitecture work, longunning engineering tasks, things that previous models, Opus 55, Astra, etc. have not been able to really get through and it's not annoying.

What are the cons? Well, it's not good at front-end and web design. You will kind of see that in um some of the evals and things that I show you. Like it's really good. It's really tasteful when you give it a good brand or style guide and it's good at following it, but left to its own devices, it has incredibly concerning taste. Like she just does not have good taste. And then I think this comes from a lack of image gen model really shows because when a model is really creative, you want it to be creative along a lot of aspects. And I found myself a lot of times invoking OpenAI's image gen 25 to create images. And then you know Fable wasn't very good at that in particular. So I, you know, high level I am going to use this model all the time. I really love it. But I want to show a couple things that it was really good at and then again later we'll do the full how I AI bench.
</details>

### 视频生成实战：从静态幻灯片到生动动画

首先我们来聊聊视频生成。我之前一直在把客户会议记录、推文等各种素材转化为视频，频繁采用 Hyperframes 配合 Opus 5.5 来制作。我必须承认这种组合非常棒，彻底改变了我的生活，也改变了我做产品营销的方式。

但我总觉得那些视频看起来还是有点像幻灯片。大家明白我的意思吧？那些视频给人的感觉就像是带有动效的 Google Slides 或是动态 PowerPoint。而 Fable 真正令人惊艳的地方在于，它将我那些由 AI 生成的动态视频提升到了一个完全不同的境界。

我想给大家看一个例子：我之前发过一条关于“软件工厂”（Software Factory）的推文。当下所有人都在谈论软件工厂，我也就此发过相关推文。我把那条推文连同我们 CXO.dev 的品牌规范一起丢给 Fable，并对它说：“把这条推文做成一段视频。”

坦白讲，在制作过程中我经历了几轮交互迭代，稍后我会展示其中一个令我极其印象深刻的子循环环节。但先来看看它为我生成出来的东西：

> “在工程团队内部，我反复看到这样一个故事：它始于一句话——‘我们需要一个软件工厂’，于是每个人都爱上了这个想法。接着，一个团队获得了一个季度的时间来搭建它：规划、编码、探索、验证、审查、发布。在幻灯片上，这套流程看起来无比美好。然后，他们把系统正式上线了。代码仓库还没就绪，检查流程极其缓慢，全员都未接受过培训。他们最终实际搭建出来的，不过是一个更糟糕的 Claude Code 仿制品。”

我不会让大家看完整个视频，但大家通过这里的画面就能看到：这是一个完全动态化呈现的小型“太空侵略者”（Space Invader）机器人动画视频，而且内容还在持续展开。中间还出现了一个“Bug 工厂”，它制作了所有这些惊艳的视觉效果，结尾处还立起了一块类似广告牌的画面。虽然它不能说百分之百完美，但比起过去已经好了太多，绝对不再是那种呆板的动态幻灯片了。

我对此感到无比佩服。除了我们的品牌手册之外，我没有为它提供任何创意指导，我也没有预先画过任何分镜脚本。这完全是 Fable 凭借自主性独立构建出来的。

<details>
<summary>Original English</summary>
So first let's talk about videogen. I have been making so many videos out of customer meeting notes, tweets, all these sorts of things. And so I've been really using this combination of hyperframes and Opus 55 to do videos. And I will say it's incredible. Like it's changed my life. It's changed how I do product marketing. All these things. But I feel like they all still kind of felt like slides. You know what I'm talking about? These videos that really just look like animated Google Slides or PowerPoints. And what was really incredible about Fable was that it took my AI generated animated videos to the next level.

And so the example I want to show you is I had this tweet about software factory. So, everybody's been talking about software factories. I had this tweet about software factories. And I gave Fable that tweet plus our CXO.dev brand guidelines and said, "Make this tweet a video." Now, I will say I have to go back and forth and I want to show one sub loop that I did that was really impressive with Fable that made this amazing. But look at what it generated for me.

There's a story I keep seeing inside engineering orgs. It starts with one sentence. We need a software factory and everyone falls in love with the idea. So one team gets a quarter to build it. Plan, code, discovery, validation, review, release. On a slide, it's beautiful. Then they turn it on. The repo isn't ready. The checks are slow. Nobody's been trained. And what they've really built is a worse version of Claude Code.

So I won't make you watch the whole thing, but you can just see there. This is a full animated little Space Invader bot full video and it keeps going. There's like a bug factory. It's done all these amazing visualizations. It ends with this like billboard. It's not 100% perfect, but it's way better than it was before. It is certainly not like an animated slide. And I was just so impressed. I did not give it any creative guidance other than our brand book. I did not storyboard this. This is really Fable being independent and building this by itself.
</details>

### 精准的空间与几何理解：从精灵动画到组装家具

在制作过程中，它做的一件让我尤其钦佩的事情是关于那些小侵略者机器人的。我们官网上只有这些小家伙的静态图片，是由此前参加过我们节目的 Jamie Ganon 为我们设计的。我希望让它们动起来，而不是像以前那样呆滞。过去当我使用 Opus 或其他模型时，这些角色往往只是在屏幕上生硬地来回平移扭动；但我想要的是真正的肢体动画。

令人惊艳的是，Fable 针对这些“太空侵略者”自行生成了一系列精灵图（sprites），设计了它们具体的动作姿态、欢呼的时机以及跳跃的动作。同样，这完全没有经过人为的详细提示，但表现却让我叹为观止。因为这些本是非常抽象的对象，而我认为它在为其注入生命力与动画设计上完成得极其出彩、极具创意。

事实上，我已经把这种侵略者动画的生成任务融入到了新的 How I AI 评测基准当中。大家可以看到，“为侵略者机器人制作动画”现在将作为一项测试用例加入到基准集中，我后续会用不同的模型对它进行横向评测。大家瞧，这个小家伙走进来，看起来像一个迷你的 Claude 形象；当被问到能否发布（ship it）时，它们兴奋地上蹿下跳。这项任务在视觉上看起来极其简单，但过去我用其他任何模型都完全做不出来。而且它的生成速度飞快。这让我深切感受到它拥有极其出色的几何感知与运动感知能力，在动画生成层面，Fable 5.2 确实给我留下了极深的印象。

<details>
<summary>Original English</summary>
And one thing that it did that I was really impressed by is we had these little invader bots, um, these little guys. And we just have static images of them. We put them on our CXO website. Jamie Ganon, which did an episode with us previously, made them for us. And I wanted them to be animated. I didn't want them. They were like kind of before when I was using Opus or these other models, they would kind of like wiggle their way across the screen, but I wanted them to be animated. And so, um, what was really impressive is, uh, Fable made these little sprites of the Space Invaders and how they would move, when they would cheer, jump. Again, this was not prompted, but so impressive to me because these are really abstract objects, and I think it did a really quite nice and creative job of animating these.

In fact, I have built this kind of invader um animation into the new Howi AI eval bench. And so, if you see here, animate the invader bots will now be in Eval as part of the Howi AI bench. I'll test different models against it. But look, you can see he walks in, he looks like a little Claude code claude. Um, he asked if you can ship it. They get excited and jump up and down. Again, this is something that 100% it looks super simple. I could not get any other model to pull off. And it was fast. It was fast. And so I just think about how it has a good sense of geometry, how it has a good sense of movement. And I've been really impressed with Fable 52 in terms of animation.
</details>

顺便提另一个佐证它卓越几何能力的旁证案例。这是一项两三天前没有任何模型能够解决的真实测试：我从中国直邮代发（drop shipped）购买了一批非常不起眼的组装家具送到家里，送达时包装里只有一袋敞开的螺丝、25 块木板，且没有任何说明书。上周我费尽心思试图让各种 AI 为我生成一套组装说明书，每一个模型都彻底失败了。

后来我把这个难题交给了 Fable 5.2，它的表现令人惊叹。它不仅为我生成了眼前这样的示意图，而且一步一步详尽地列出了完整的组装流程。如果你曾经拼装过复杂的宜家或者平板包装家具，你就会明白构件的组装顺序至关重要。它给出的顺序极其合理。之所以能够验证，是因为我正是拿着这份说明书，和来家里帮我组装的师傅一起完成拼装的。它的步骤顺序完全正确。这也是此前没有任何其他模型能够完成的任务；我曾反复尝试过，因此我知道这是一个含金量极高的真实基准测试。而它仅仅是依据我拍摄的几张放在地板上的低分辨率平板家具构件照片、上面印有的中文标签，在零原始说明书的情况下推导出来的。向大家报个喜讯：那件家具现在已经稳稳地立在我家里，感觉棒极了。

<details>
<summary>Original English</summary>
I'll give sort of a side another side example of its excellence in geometry which it was a eval that no model two days ago 3 days ago could fix which was I got a very shady pile of furniture straight drop shipped from China delivered to my house and it showed up with an open bag of screws, 25 pieces of wood and no instructions. And I tried so hard last week to get this to put together a set of instructions for me. Every single model failed and I dropped it to Fable 52 and it did such a good job. It not only gave me this like kind of diagram right here, but it gave me bitto bit how to put it together.

If you've ever done complex IKEA or flatpack furniture, you know that the order in which you put stuff together is really important. And it put really good. And I know cuz I followed these instructions with the um the guy that came to my house to assemble it. It did it in the right order. And this was something again that no other model was able to do. I tried. I tried. So I know this is a true benchmark. And it did it truly from pretty low res images of the flat pack items on my floor with Chinese language labels on them. And again, zero instructions. Um good news to you all. This piece of furniture is now in my house and feeling really nice.
</details>

### 游戏开发与趣味性

以上就是它在几何理解和视频生成方面的表现，我对此非常满意。

第二个例子是，我将那个 CXO 工厂的游戏概念扩展成了一个“太空侵略者”射击游戏。同样，从视觉角度来看，这算不上那种令人惊叹的 3D 大作；但这款游戏最让我喜欢的地方在于：它非常幽默。在搞笑这件事上，Fable 做得非常出色。

我制作的这款游戏的主题是“如何避免把系统做成 Bug 工厂”。你扮演一名工程师，必须在 Bug 进入生产环境之前将它们拦截。你可以选择自己的挑战模式：如果配置了更多 Agent，你就会有更多帮手来拦截 Bug，但一旦漏掉一个，流入生产环境的负面影响就会更大；你也可以获取受保护的时间（protected time），从而有更多余裕来排查 Bug，或者选择增加测试用例。大家可以看到，各种 token 正在穿越防线。哦，我还获得了一些免费额度，看起来感觉不错。糟糕，“氛围编程”（vibe coding）来了，海量 Bug 涌入！

这就是我做的 CXO 小游戏。这个游戏真正打动我的地方依然在于：我当时只是简单地说了一句“利用我们品牌的太空侵略者形象，做一款对抗 Bug 的游戏”，它就自主构思出了所有的游戏机制，并且巧妙地将它们与我们觉得很棒的商业逻辑串联在一起。

它甚至为我们做了一个预告片，我觉得非常滑稽。为了不影响收听播客的听众，我就不播放声音了，但它的旁白大意是：团队这个季度原本只有一项核心任务，随后他们加入了更多的 Agent；交付速度确实加快了，他们兴奋地向财务部门报喜，但财务部门一看到 Token 账单直接傻眼；于是他们被降级成了便宜的廉价模型，只能用来解决低级 Bug；而游戏里的最终大 Boss，正是以巨型太空侵略者形象登场的“单体巨石代码库”（monorepo）。

我觉得这太好笑了。我自己玩了几局，真的忍不住笑出声来。我今天会尝试把它部署上线。大家回想一下，当初 Opus 5 和第一代 Fable 刚发布时是多么招人烦，交流起来是多么不近人情、令人不悦；而现在，我们却拥有了一个如此风趣、让人乐于与之合作的模型。

<details>
<summary>Original English</summary>
Okay, so that is like geometry and video which I have been very happy with. One second is I extended that CXO factory game into a Space Invader shooter game. Um, again, this isn't like one of those 3D games that are going to be really impressive from a visual perspective, but what did I love about this game? It is funny. So, good job, Fable, on being funny.

So, I made this game about not running a bug factory. Um, you are an engineer that has to stop bugs before they get to um production. You get to pick your challenges. And so, if you have more agents, you have more agents stopping bugs, but then if they miss a bug, more bad stuff gets through production. You get protected time, therefore you have more time to catch bugs or you have tests. Again, you can see the tokens are getting through. Oh, I got some free I get some free credits. I get these look good to me. Oh no, vibe coding. So many bugs.

Okay, so this is my CXO um game. And what I really loved about this game was again I just said make a game about fighting bugs using our space invaders from our brand. And it came up with all these concepts. It tied it to business things that we thought were awesome. It made a trailer for us that I thought was really funny. I'm not going to play the sound because it's going to be really annoying for people watch listening on the podcast, but it says basically this quarter the team had one job then they added more agents. They shipped faster. they call Finance, but Finance saw the token bill. So, they get downgraded to the cheap model and can only solve easy bugs and it um stars the monor repo, which is this giant space invader, as the final boss. I think it's really funny. I played it a couple times and actually giggled. I'm going to try to get this live today.

But again, like remember how annoying Opus 5 and Fable were when they came out. So annoying. Not a good hang. not enjoyable to be around. And now we have this like funny model that I like working with.
</details>

### 真实工程重构：ChatPRD 的数据管道改造

以上都是些趣味性的尝鲜项目，我们做了一款游戏。接下来，让我们快速巡礼一下它在真实的 AI 工程、复杂编码和架构设计层面的硬核表现。

重申一遍，我对这款模型的表现感到极其欣慰。如果你最近没留意我的工作流变化，我近来一直重度依赖 Claude Projects 和 Opus 5.5 来跑大部分的编程任务。它确实帮我攻克了不少代码难关，而且在前端开发上的表现也很不错。

这一次，我把 Fable 5.2 投入到了我在 ChatPRD 负责的产品智能（Product Intelligence）功能中。那是一个包含复杂的抓取摄入（ingest）、分类整理（organize）、提炼总结（summarize）以及自动化 Wiki（auto wiki）的数据流水线产品，我已经陆陆续续开发了大约 6 个月。由于经历了长时间的迭代，那里的代码库结构非常杂乱。

于是我让 Fable 5.2 尝试优化整套管道，使其更加高效、更易于维护，要求它施展出最顶尖的产品化架构思维。坦率地讲，我对它的重构成果非常满意：结构组织得非常清晰合理，而且在很大程度上与我脑海中规划的后续技术演进路线不谋而合。

在这次重构任务中，与 Fable 5.2 协作体验极佳的另一个关键在于：它能够在恰当的节点主动停下来确认，而在需要提交 PR 之前，又展现出了极其强大的端到端自主执行能力。我发现它非常适合处理长程任务，具备良好的架构抽象思维，代码编写质量很高，而且在这个历经 6 个月反复迭代、代码结构异常混乱的复杂数据管道项目中，与它的沟通协作丝毫不令人烦躁。

目前这项技术迁移我已经完成了大约一半。我会继续推进并在完成后告诉大家它是否稳定运行，但截至目前，一切进展顺利，我对它感到非常满意。

<details>
<summary>Original English</summary>
So that's all the kind of fun stuff. We did a game. Let's just take a quick world tour through real AI engineering, coding, and architectural thinking. Again, I've been really, really pleased with this model. If you haven't been following my changes, I've been using a lot of Claude projects and Opus 55 to run a lot of my coding tasks right now. It's really helped me break through some coding challenges. I also think the front-end work is quite nice. Um, and so I turned Fable 52 on my product intelligence product at ChatPRD, which is a complex ingest, organized, summarize, auto wiki product that I've been working on for like 6 months. Um, and it's like a pretty messy codebase.

And so I asked Fable 52 just to make the pipeline more efficient, easier to maintain, just do its greatest product thinking. And I will say I'm like very happy with the work here. It's quite sensibly organized and in fact matches my upcoming kind of like in my mind road map of things that I needed to do. The other thing that was really nice on working with Fable 52 on this is it stopped at the right moments but was pretty autonomous until it needed a PR. And so I found that it's longunning, that it's got good architectural thinking, that it does code nicely, and that it's not annoying to work with um on this fairly complex kind of like data pipeline product that has I will say like very messy code in it from 6 months of iteration. So I'm about halfway through this migration. I will get through it all and let you all know if it works, but so far so good and I have been really happy with it.
</details>

### 前端审美翻车与“压轴大作”

接下来，我要快速列举一些我认为它做得很糟糕的方面，然后再向大家展示 Fable 5.2 构建出的最震撼的巅峰之作。请务必看到最后，因为最让人眼前一亮的项目就在片尾。

在揭晓那个项目之前，我必须先谈谈它的短板：它在网页设计方面非常差劲，可以说是非常糟糕。我之前一直尝试让 AI 构建一些能够帮我放慢生活节奏的网站。于是我让它帮我设计一款新型的浏览器主页——结果做出来的东西极其难看，充斥着毫无美感的劣质拼凑物（slop），可以说是糟糕透顶。

当放手让 Fable 5.2 自由发挥时，它做出来的设计通常都不尽如人意。另一个例子是我一直在做的一本带有幽灵风格的故事书：最终的效果只能说勉强能看，但整体依旧相当丑陋。因此在后续的工作流中，我可能会考虑将 Opus 5.5 与 Fable 进行组合，让 Opus 处理前端设计，Fable 负责后端逻辑，因为我实在不敢恭维 Fable 的独立前端设计品味。从这个维度来说，我对它是持保留态度的。

<details>
<summary>Original English</summary>
I'm going to do a quick run on things that I think are terrible and then I'm going to show you the best thing that Fable 52 built. So, please stick around till the end. Um, because the eyepopper item is at the end. But before we get there, I do want to talk about some things that it's bad at.

It's bad at web design. It's like real bad at web design. And so, I've been trying to make AI that um helps me slow down, websites that help me slow down. So, I asked you to design a new kind of like browser homepage for me. This is so so ugly. Such much slop. So, so terrible. And so, when I've left Fable 52 to its own devices, it's made pretty bad designs. Same with this story book. I've been working on a kind of like ghostly story book. Um, same with this story book. Like, it's okay, but it's pretty ugly. So, I might pair Opus 55 with Fable on the back end for some of the design stuff, but I really don't love the front end design of Fable. So, that's a kind of like thumbs down on the model.
</details>

### 压轴登场：Claire 的全功能 3D 打字机

但如果你想见识一下最让我热血沸腾的成果，现在就展示给大家看。

昨天，我看到 Vercel 的 Guillermo Rauch（GMO）制作了一个极其惊艳的 3D 黑胶唱机，它能够伴随唱片纹理播放公有领域的素材图像。那个设计极其优美，我彻底被它吸引了。而且他公开了源代码。我从中获得了巨大的灵感，随后我把 Fable 5.2 引导向了一个类似但截然不同的创意方向。

现在，我想向大家隆重介绍：**Claire 的打字机**。

这是一台功能完整、全 3D 渲染的打字机。你可以通过直接用鼠标点击按键来进行输入，也可以直接在实体键盘上敲击打字。你可以拉近视角，近距离观察机械结构的运转细节；如果你按了退格键并覆盖打字，系统也完全支持。大家看，“Welcome to how I AI. This is my beautiful typewriter.”

在画面中大家能看到我刚才打出了一个真正的错别字。你可以对它进行修正，它会在纸面上涂抹涂改液——虽然涂抹的位置还稍微有一点偏差，但它确实执行了涂白覆盖并重新键入的逻辑。

但这还不是全部，你还可以为它营造出浓厚的环境氛围（vibes）。我们可以打开音乐，打开下雨的声音，听听这惬意的雨声。你可以通过旋转这里的沙漏来启动一个写作计时器：这个能开启一个 15 分钟的倒计时，而那个大沙漏则是 30 分钟。此外，这里还有非常精美的写作灵感提示符（prompts），比如如果你想写关于“等待”的话题，它会给出相应的写作提示；桌上还摆放着这杯热咖啡。

我其实把 GMO 的黑胶唱机也整合到了旁边，你可以随意切换不同的广播电台，比如调到一个爵士乐电台。这难道不是很惬意吗？我未来绝对打算用这种方式来写作。

<details>
<summary>Original English</summary>
But if you want to see the thing that I was most excited to build, let me show it to you right now. Okay, so GMO at Verscell um I saw yesterday made this amazing um 3D record player that plays public domain images with the grooves. It's so beautiful. I'm obsessed with it. And um he actually gave the source code and I was mega mega mega inspired by this and pointed Fable 52 at a similar but different problem.

And I would like to introduce you to Claire's typewriter. So this is a fully functioning 3D rendered typewriter. You can type on it by clicking the keys or you can type on it by using your keyboard. You can zoom in and get a closeup of how it works if you backspace and type over things. You can do that. Welcome to how I AI. This is my beautiful typewriter.

Okay, so this is you can see I have a a literal typo in this. You can clean it up. It will go and put uh wide out. It doesn't quite get it right, but it will do. Wide out and type over. But that's not the only thing. You can make it real viby. So, let's turn on some music. Let's turn on some rain. We need some nice rain. Um, you can start a writing timer here by turning one of these sandlasses that starts a 15-minute timer. The big one's 30 minutes. Um, and then you also have these beautiful prompts. So, if you want to write about waiting, don't say what it's for. You can get a writing prompt. You have this nice cup of coffee. I have actually integrated GMO's record player over here. You can change different radio stations. So, we can have a jazzy radio station. Isn't this nice? Um, and this is like I am totally going to write this way.
</details>

更棒的是，我还构建了许多不同的场景模式。眼前这个是我的“温柔黄昏”（soft evening）场景。我可以打开台灯，光影会随时间产生动态变化——现在恰好是傍晚，色调非常柔和。我还可以切换到带着便携旅行打字机的“火车旅行”场景；也可以坐在油灯旁，看着精致的玻璃沙漏发呆；或者切换到“手写信纸”模式，拿起这支铅笔写下：“Hello my beautiful how I AI guests, so nice to have you here.” 虽然还不算完美，但基本功能都已齐备。

最后是我个人最钟爱的一套：我可以切换到一个千禧年风格（Y2K）的复古电脑终端，在绿色荧光屏与琥珀色屏幕之间自由切换。如果回到之前的打字界面，我写下一句“I love this thing”，然后点击打印页面，旁边的针式打印机就会真实地将它打印出来，整齐地堆叠在一旁。我可以随时展开这叠文稿进行翻阅、保存或者复制其中的文本。

我准备把这个应用正式部署上线供大家亲自体验。我对这个东西完全着迷了。打字机的核心键盘部分，几乎是由 Fable 单次提示词（single-shot）一次性直接生成的！后续我只进行了一些微调，并不断为它追加新的周边功能。我马上会把它部署出去，看看大家是否愿意在我的这台复古打字机上敲下文字。

这就是我的“AGI 时刻”。当我亲眼看到它跑通的那一刻，我整个人都激动坏了。这实在太酷了，它极大地释放了我的创造力，在过去我根本无法想象自己能做出这样的产品，但借助 Fable 5.2，我做到了。

<details>
<summary>Original English</summary>
Um, but even better than all this, I've made a bunch of different scenes. So, this is my soft evening scene. I can turn on the light. It follows the time of day. So, right now it is um evening and soft evening. I can go on a train with my travel typewriter. I can sit by an oil lamp with my beautiful glass sand timer or I can write in handwritten pages. So I have this pencil. I can say hello my beautiful how I AI guests. So nice to have you here. It's not perfect but we get there.

And then my favorite one, I can do a Y2K computer and I can change it between a green and amber screen. And if you go back and I say, I love this thing. I can print the page and it will print it on my doc matrix printer. Keep it in a stack. I can open up these stacks, read them. I can save them. I can copy the text. Um, and I am gonna deploy this and you all can use it. I am obsessed with this thing. It is a singleshot.

I'm going to turn off the music for a minute. Actually, it's pretty relaxing. I'm going to keep it on. I like it. Um, it is so relaxing. And I just think I'm going to come in here and do full screen writing on my beautiful typewriter. And listen, you can even hear the static when it plays on the record player. And this truly one shot by Fable the keyboard. I've done some tweaks. I've kept giving it new features. Um, but I'm going to deploy this and see if you all want to type on my beautiful, beautiful typewriter.

This has been my AGI moment. I lost it when I saw this. I think it is so cool. It's helped me be so creative and it's just something I could never imagine being able to do before and I was able to do with Fable 52.
</details>

### 获取渠道与结语

所以我正式回归了，宝贝们，我彻底回来了！我爱死它了，它非常出色。我现在无时无刻都想用它，它让我倍感快乐。

同样，我已经在这里跑完了完整的 How I AI 基准测试，大家可以看到它的运行效率非常高：即使是像“为侵略者机器人制作完整动画”这样复杂的任务，也仅仅耗时 16 分钟；绝大部分常规任务都能在 1 分钟之内迅速搞定，其中不乏很多高难度的综合工程。在一两周后，我会把完整的 How I AI 评测成绩拿来与其他几个主流模型做全方位的横向对比，让大家清晰地看到彼此之间的实力差距。但我现在真的非常偏爱这款模型。

最后，让我们以“如何获取它”来收尾：该模型将在 API 以及各大云平台上提供，包括 AWS、Google Cloud 和 Microsoft Azure；它也会同步内置到各项云端应用和 Cloud Code 之中，我目前主要就是在 Cloud Code 里面调用它。

此外，官方还将推出一个极速模式（Fast Mode）——尽管它现在的速度已经极快，但他们仍将推出一个更加飞速的版本。对于各类订阅用户而言，你们还将享受到专属的 Fable 配额重置机制。

大家一定要亲自尝试一下这个模型。它真的能给人带来纯粹的快乐。回想起最初那个让我由衷厌恶的初代 Fable，再看看现在的版本，我内心对它充满了温情与好感。Anthropic 这次干得太漂亮了，你们彻底把我拉回了阵营。我原本以为这绝无可能，但你们确实交出了一份极其出色的答卷。

以上就是本期 How I AI 针对我最新心头好——极具创意的 Fable 5.2 的即时快评。我要回到我的 3D 打字机旁继续我的创意创作了，大家接下来肯定会看到你们的朋友 Claire 产出海量的视频和全新的消费级应用。

感谢收听 How I AI。非常感谢大家的观看。如果你喜欢本期节目，请在 YouTube 上点赞并订阅，更欢迎在评论区留下你们的想法。你也可以在 Apple Podcasts、Spotify 或任何你常用的播客客户端找到我们。请务必考虑给我们留下评分与好评，这能帮助更多人发现这个节目。你可以在 howiipod.com 查看往期所有剧集并了解关于本节目的更多信息。我们下期再见！

<details>
<summary>Original English</summary>
So that's I'm back. I'm back, baby. I love her. She is great. I want to use it all the time. It makes me happy.

Now again, I have done the H full howi AI bench here. You can see here it is very fast. So um even something as complex as animating the invader bots only took 16 minutes. A lot of things are in sub 1 minute. Um there's some complex tasks. So I will do the full how I AI benchmark against a couple other models um maybe in a week or two just so we can see all of this against each other. But I really love the model.

Um, again, let's just close with how do you get it? So, it's going to be available in the API and on the cloud platform as well as AWS, Google Cloud, and Microsoft Azure. It's going to be in the cloud apps and in cloud code. I've been using it in cloud code. There's going to be a fast mode. So, even though it's already fast, they're going to make a new fast version. And subscribers, you're going to get fable resets. So, use this thing. I just it like sparks joy and I just think back to how much I truly hated truly hated the original fable and now I just I I feel warm fuzzy feelings about this model. So good job Anthropic. You hooked me back. I never thought it was possible but you did a really good job.

That has been how I AI hot takes on Fable 52, my new favorite little creative model. I'm going to get back to my typewriter. I'm going to get back to my creative projects and you all are about to see a lot of video and a lot of consumer apps out of your friend Claire. Thanks for joining how I AI.

Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.
</details>