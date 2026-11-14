---
author: Latent Space
date: '2026-05-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rlM_fAKxB3Q
speaker: Latent Space
tags:
  - engineering-fundamentals
  - ai-development
  - developer-productivity
  - typescript
  - domain-driven-design
title: 工程基础在 AI 时代的重要性：Matt Pocock 访谈
summary: 本期播客采访了 AI Hero 的 Matt Pocock，他强调了即使在 AI 飞速发展的时代，坚实的软件工程基础依然至关重要。讨论深入探讨了代码可维护性对 AI 开发的影响、领域驱动设计 (DDD) 的应用、TypeScript 在 AI 工程中的崛起，以及他对未来 AI 工具和学习方法的见解。Matt 分享了其教学经验，并指出 AI 辅助编程应回归工程本质，而非一味追求捷径。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Matt Pocock
companies_orgs:
  - AI Hero
  - OpenAI
  - Goldman Sachs
products_models:
  - Claude code
  - AI SDK
  - GPT-4o
media_books:
  - Philosophy of Software Design
  - Extreme Programming
  - Pragmatic Programmer
  - DDD
  - Zettelkasten
status: evergreen
---
### 引言与开场白

**主持人**: 好的，我们现在来到 AI Engineer Europe 的播客展位，与 AI Hero 的 Matt Pocock 见面。你好吗？
<details>
<summary>Original English</summary>

**Host**: Okay, we're here in the AI engineer Europe podcast booth with Matt Pocock of AI Hero.

</details>

**Matt Pocock**: 你好，你好吗？挺好的， man。很高兴来到你这里。
<details>
<summary>Original English</summary>

**Matt Pocock**: Hey man, how you doing? Good, man. It's nice to be in your neck of the woods for once.

</details>

**主持人**: 是的。你经常做 SF（科学幻想）方面的内容，但很高兴你能来伦敦。
<details>
<summary>Original English</summary>

**Host**: Yeah. You do a lot of SF stuff, but nice so nice that you come to London.

</details>

**Matt Pocock**: 是的。
<details>
<summary>Original English</summary>

**Matt Pocock**: Yeah.

</details>

**主持人**: 我们这次的体验和你其他的伦敦活动相比如何？
<details>
<summary>Original English</summary>

**Host**: How do we stack up versus your other London event experiences?

</details>

**Matt Pocock**: 这是我参加过的最差的一次。
<details>
<summary>Original English</summary>

**Matt Pocock**: It's the worst I've ever been to.

</details>

**主持人**: 迄今为止最差的。简直令人难以置信。地点令人惊叹，内容也很棒。
<details>
<summary>Original English</summary>

**Host**: By far the worst. Absolutely astonishing. Astonishing location, great stuff.

</details>

### Matt 的历程与核心论点

**主持人**: 你我第一次联系，是当你即将开始你的创作和开发者旅程时。你最初做的是 TypeScript，反响非常好。现在你经营着 AI Hero，并且即将完成一个 Claude Code 的课程。
<details>
<summary>Original English</summary>

**Host**: You and I first connected when you were about to start your sort of creator journey and your developer journey. You started total TypeScript, which did very well. And then now you're running AI Hero. You're just about to finish a Claude code course.

</details>

**Matt Pocock**: 是的。我现在的课程以两周为一个周期进行，因为 AI 发展得太快了。很难发布一个自定进度的课程并保证永久更新。所以，是的，我们正处于一个为期两周课程的最后几天。这很棒。
<details>
<summary>Original English</summary>

**Matt Pocock**: Yep. I run courses in two-week cohorts these days because AI moves so quickly. Hard to release a self-paced course and guarantee updates forever. And so yeah, on the last couple days of a two-week course. It's wonderful.

</details>

**主持人**: 这是否意味着 Claude Code 的源代码在你刚开始时就泄露了？
<details>
<summary>Original English</summary>

**Host**: Does that mean that the Claude code source leaked just as you started?

</details>

**Matt Pocock**: 是的。
<details>
<summary>Original English</summary>

**Matt Pocock**: Yeah.

</details>

**主持人**: 那怎么样？你……你……你经历了什么？
<details>
<summary>Original English</summary>

**Host**: How was that? What what what did what what did you

</details>

**Matt Pocock**: 我觉得我真是倒霉，你看。我曾开过一个关于 AI SDK 的课程，它基于 AI SDK V4。课程的第二天，他们就宣布了 AI SDK V5，对吧？一个巨大的破坏性变更。嗯，而这次，我想是课程的第二天，他们发布了 100 万的上下文窗口，或者也许是在课程开始前不久。然后，是的，Claude Code 的源代码泄露了。但幸运的是，我的课程其实不是关于 Claude Code 的。我注意到我在构建它的时候。它主要关注工程软件基础，而这，我的意思是，这也是我在这里演讲的内容。现在我关注的是回归这些旧的文本，找出什么是有价值的，然后将其转化为 AI 时代的东西。
<details>
<summary>Original English</summary>

**Matt Pocock**: Well, I'm cursed, you see, because I did a course on AI SDK and it was based on AI SDK V4. On day two of the course, they announced AI SDK V5, right? A huge breaking change. Um and this time, I think day two of the course, they released the 1 million context window or maybe just before the course started. And yeah, now the Claude code source has leaked. But fortunately, the course is not really about Claude code. I noticed that when I was building it. It's mostly about engineering software fundamentals and that's I mean, that's the talk I'm giving here, too. It's kind of what I'm focused on now is going back to these old texts, figuring out what's good and translating that into the AI era.

</details>

**主持人**: 所以人们可以看到你的演讲。你也做了一个工作坊。你是……我请了三个人做一个双场演讲，因为你是一位重要的伦敦人物，我想确保我们有足够的时间接触你的内容。我认为，很多时候，会议害怕重复邀请演讲者。但我有一个特别的论点，那就是 YouTuber 非常适合做会议演讲者，因为你们为了生计，整天都在说话。
<details>
<summary>Original English</summary>

**Host**: Yeah. So people can see the talk. You did a workshop as well. You're one of the I had three people do a double session where, you know, because you're a big London figure, I wanted to make sure that we have enough exposure to to to things. And I think often times conferences are afraid to double down on speakers. But I think I have a particular thesis that YouTubers make particularly good conference speakers because you speak all the time for a living. And

</details>

**主持人**: 我不知道，我称你为 YouTuber，你会不会觉得不舒服？这是一种虚荣吗？
<details>
<summary>Original English</summary>

**Host**: I don't know. Do you do you cringe when I call you a YouTuber? Is that a vanity?

</details>

**Matt Pocock**: 是的。我是说，我的身份是教师，我一直努力……有一类 YouTuber 我并不太想与之互动，那就是“评论员”。我不是一个试图预测未来的人。我只是在教东西。你不会每两周就改变你最喜欢的想法。就像其他一些 YouTuber 一样。我是说，那些东西确实很受欢迎，而且很有吸引力，但很难不落入那些陷阱，因为那些数字确实很好。但我的目的是教一些经久不衰、有意义、让我感觉良好的东西。是的，工程基础以及所有这些。
<details>
<summary>Original English</summary>

**Matt Pocock**: Right. I mean, like I mean, my agency is I'm a teacher, I really try there's a whole category of YouTubers that I don't really try to interact with or try to be, which is the pundit, right? I'm not I'm not a guy who's trying to predict the future. I'm just trying to teach You don't you don't change your favorite idea every two week two weeks. Exactly. Like some some other YouTubers. Exactly. I mean, that stuff does do really well,

</details>

**主持人**: 哪些是你珍视的工程基础？
<details>
<summary>Original English</summary>

**Host**: What are the fundamentals that you hold dearly to?

</details>

**Matt Pocock**: 我的意思是，我稍微重述一下我的演讲，就像……
<details>
<summary>Original English</summary>

**Matt Pocock**: I mean, I'll kind of re- run my talk a little bit now, which is like

</details>

**主持人**: 预告。人们可以在网上找到。
<details>
<summary>Original English</summary>

**Host**: >> little preview. People can find it on online.

</details>

**Matt Pocock**: 理论是这样的，有一种观点认为，代码已经不再重要了，对吧？我们正处于一个时代，你不需要真正去思考代码，或者在构建应用程序时将代码记在脑海里，因为你只需要用英文描述，然后用 AI 把它编译成代码。你不需要关心代码，它只是一个编译目标。我认为，每次我尝试这样做，每次我试图忽略代码时，我最终都会陷入一团糟。所以，在试图改进编译器和优化编译器的过程中，我回顾了那些经典的旧文本，你知道，比如《极限编程》和《程序员的修炼之道》，以及《软件设计的哲学》和 DDD，所有那些东西。我发现的是，哦，我可以直接把这些东西放进我的提示里，你知道吗？我开始深入，深入，再深入，然后意识到，哦，好了，这里实际上比我最初想象的要多得多。而且，我们过去为人类所做的一切，对 AI 也同样适用。实际上，在脑海中保留代码，并对你正在构建的东西有真正的意图，不一定是指审查一切，而是仍然对架构和模块保持一定的理解，尤其是，这真的能带来回报，因为如果你有一个对人类来说易于更改的代码库，那么对 AI 来说也同样容易更改。而且这意味着你可以工作得更快，因为对人类来说难以更改的代码库，对 AI 来说会更糟糕。
<details>
<summary>Original English</summary>

**Matt Pocock**: The theory is that there's this idea that code doesn't matter anymore, right? We're in an era where you don't really need to think about the code or hold the code in mind when you're building applications because you can just use a description in English and use the AI as a kind of compiler to turn that into code. You don't need to care about the code, it's just a compile target. And I think that every time I tried that, every time I tried to ignore the code, I would just end up with a this terrible mess. And so in kind of trying to better the compiler and improve the compiler, I went back to the old classic text, you know, like extreme programming and pragmatic programmer and philosophy of software design and DDD, all that stuff. And what I found there was just, oh, I can just take these and just put them into my prompts, you know? And I started going deeper and going deeper and going deeper and realizing oh, okay, there's actually there's so much more here than I realized and that everything that we were doing for humans really works with AI, too. And actually keeping the code in mind and being really intentional about what you're building, not necessarily reviewing everything, but still keeping a sort of understanding of the architecture and the modules, especially, it really yields dividends because if you have a code base that's easy to change for humans, it's going to be easy for AI to change, too. And it's going to mean that you can work a lot faster because a code base that's difficult to change for humans is is going to be even worse for AI.

</details>

**主持人**: 是的。我一直在思考“窄腰”这个概念。不知道你有没有听过这个东西。
<details>
<summary>Original English</summary>

**Host**: Yeah. I've been thinking a lot about the concept of a narrow waist. I don't know if you've heard about this thing.

</details>

**Matt Pocock**: 它来自早期的互联网架构哲学。你听说过可能的分层 1、2、3、4、5、6、7 吗？窄腰是指第三层和第四层，基本上 TCP/IP 和 HTTP 已经占据了主导地位，除了 WebSocket 之外，实际上没有其他选择。Mhm。我认为在代码库中引入窄腰可以容忍“污垢”，对吧？你可以说，“我不在乎这里面发生了什么，但进来的东西由我定义，出去的东西也由我定义。”你里面可以随便怎么做。
<details>
<summary>Original English</summary>

**Matt Pocock**: It comes from old internet architecture philosophy. You've heard about maybe layer 1 2 3 4 5 6 7. The narrow waist is layers three and four, where basically TCP IP and HTTP have mostly dominated and there no other alternatives effectively apart from web sockets. Mhm. And I think introducing narrow waist in the code base allows you to contain slop, right? You can say, I don't care what goes on in here, but what goes in is defined by me, what goes out is defined by me. Do whatever you want inside.

</details>

**主持人**: 是的。所以……
<details>
<summary>Original English</summary>

**Host**: Yes. And so

</details>

**Matt Pocock**: 在我脑海中，这与 MVC 的早期分解有些相似。人们称之为 Model View Controller。今天我称之为 Model View Claw。我经常看到这种情况，就像我运行 AIE 的方式一样。AIE 现在是一个九人公司。每个人都负责大象的不同部分，我必须确保每个人都能……嗯，协同合作，并且……嗯，像……做出一个会议，让没有人注意到幕后那些粗糙的边缘。所以一部分是，是的，我负责网站。我负责演讲者，我负责内容。但一切都必须从我这里流向，好吧，你需要什么 AV 设备？你需要什么酒店？你需要什么……你知道，其他……嗯，住宿。而且存在巨大的协调问题。这到处都是。我甚至不再觉得这真的是编程了。这只是关于你如何设置系统的。
<details>
<summary>Original English</summary>

**Matt Pocock**: some there's some equivalents of this in my mind of this and the former decompositions of MVC. People call it model view controller. Today I call it model view claw. I view this a lot in in terms of how I run AIE as well. AIE is now a nine-person business. Everyone has different parts of the elephant and I have to make sure that everyone sort of uh comes together and like produces a conference where nobody notices the the the the rough edges down under under the hood. And so part of it is yes, I I run the website. I run the speakers, I run the content. But everything has to flow from me down to, okay, well, what AV do you need? What hotels do you need? What you know, other other sort of accommodations do you need? And there's a huge coordination issue.

</details>

**主持人**: 是的。这到处都是。我甚至不再觉得这真的是编程了。这只是关于你如何设置系统的。
<details>
<summary>Original English</summary>

**Host**: It's just everywhere. And I don't even feel like it's really programming anymore. It's just systems in how you set up systems. Yeah.

</details>

**Matt Pocock**: 是的。这……我的意思是，你刚才说的关于在任何系统中拥有自包含的盒子这个想法，实际上，让我们以代码库为例。这是一个迷人的想法，John Osterhout 在他的《软件设计的哲学》一书中谈到了这一点。这就是所谓的“深度模块”，基本上，大量的功能，一个简单的接口。有点像端口和适配器，对吧？就像你有一个端口与其他端口通信一样。等等。而且你绝对是对的，当你的代码库或系统设计是这样的时候，你可以设计接口，对它非常在意，并且做一个坐在那里理解它的人，然后委托实现，委托内部发生的事情。而这正是我如何最好地利用 AI 进行编码的方式。我猜你正在组织你的公司，这也会很奏效。
<details>
<summary>Original English</summary>

**Matt Pocock**: This I mean, what you said there about the idea of having self-contained boxes within within any system actually, but let's use a code base as an example. It's a fascinating idea and John Osterhout in his book Philosophy of Software Design talks about this. It's this idea of deep modules basically, a large amount of functionality with a simple interface. Kind of ports and adapters, right? Like you have a port that talks to other ports, etc. And you're totally right in that when you have a code base or a system design like this, you can design the interface, be very intentional about that, and be a human sitting there and understanding it, but then delegate the implementation, delegate the stuff that's going on inside. And that's how I've used AI best for coding. I imagine for what you're doing, putting it into an org, that would work great, too.

</details>

**主持人**: 是的。我在两方面都看到了。我……我也……你知道，我为 condition 和 Devin 在高盛公司提供咨询，这与你有成千上万的工程师时的情况大不相同。
<details>
<summary>Original English</summary>

**Host**: Yeah. I see it both ends, right? I I also, you know, consult for condition and Devin at a Goldman Sachs is very, very different when you have tens of thousands of engineers.

</details>

**Matt Pocock**: 而且，那是一个……那是一个美丽的事情。你提到了领域驱动设计，DDD。我就是那种……我猜是够老了，经历过那段时期。我们实际上昨天有一个 DDD 的讲座，或者说来自宜家的一个工作坊。你觉得它在普及吗？你觉得它重要到我应该更多地介绍它吗？
<details>
<summary>Original English</summary>

**Matt Pocock**: And it's a beautiful thing that to see. You mentioned domain-driven design, DDD. I am one of those people that I guess old enough to to have had that. We have actually a DDD talk yesterday or one of the workshops from IKEA. Do you think it's catching on? Do you think it's important enough that I should be featuring it more?

</details>

**主持人**: 我认为它对架构师和处理大型系统的人非常有吸引力。大多数人如果刚开始接触软件开发，可能从未遇到过它。我不知道。
<details>
<summary>Original English</summary>

**Host**: I think it's a very appealing concept for architects and people who work with large systems. Most people will never have encountered it in their software journey if they started more recently. I don't know.

</details>

**Matt Pocock**: 是的。这是一个迷人的想法，因为 DDD 是一系列……我不是 DDD 专家。这是我相对较新接触到的东西。但 DDD 提供了一套构建块和一套实践，它们相互配合。所以你那里有的，因为它的存在时间很长，所以它已经在这些……嗯……嗯，模型中潜在的空间里了。如果你说，你不需要发明这一整套新术语，你只需要添加这个框架，这个非常、非常灵活、非常可组合的系统，它允许你以这种方式构建系统。正因为如此，它非常有吸引力。所以，使用一个预先构建好的……嗯……框架来与模型交谈，并让模型准确理解你在说什么，因为它理解，这感觉很对。而且因为它已经非常专注于……嗯……输出，并且将代码与语言对齐，这就是 DDD 的本质。基本上，你想……嗯……创建一个统一的领域模型，这样 AI 和你就能说同一种语言。
<details>
<summary>Original English</summary>

**Matt Pocock**: Yeah. It's a fascinating idea because what DDD is is a set of like I'm not like a DDD expert. This is something I'm encountering relatively new. But what you have with DDD is a set of building blocks and a set of practices that all fit together. And so you what you have there, because it's been going around so long, it's kind of in the latent space of these um uh these models already is if you say, you don't need to invent this whole new set of terms, you can just bolt on this framework, this system that's very, very flexible, very composable, and allows you to build systems in this way. And because of that, it's very attractive. And so using a pre-built kind of framework for talking to the model and having the model understand exactly what you're saying because it understands, that just feels right. And because it's so focused on um outputs already and aligning the code with language, that's what DDD is. Essentially, you're trying to kind of create a unified domain model so that the way I think about it now is that so that the AI and you are speaking the same language.

</details>

**主持人**: 这是真的。这非常有帮助。
<details>
<summary>Original English</summary>

**Host**: That's so true. That is so, so useful.

</details>

**Matt Pocock**: 所以，为了具体说明这一点，我在 mattpocock/skills 中有一个技能……嗯，我有一套技能，它变得非常流行。它有大约 13,000 颗星，或者之类的。其中一个技能是“通用语言”技能。通用语言本质上是一个概念，你创建一个文档，它基本上定义了你正在谈论的术语。当你……比如说，你是一个客户，我是一个为你构建系统的人，当我提到……嗯……一个“痣”，比如说，我们可能在讨论一个健康应用程序，我们在调查痣；或者我们可能在谈论间谍，或者需要理解“痣”在这个语境下的含义，你知道吗？或者动物。或者动物，对吧？我们可能在建造一个动物园应用，对吧？所以你需要所有这些术语，任何在一个成熟的项目上工作过的人都知道，你会有所有那些奇特的行话。所以，我有一个技能，它基本上可以扫描你的代码库，寻找所有这些术语，并与你一起优化它们。而且我注意到，我一直在打开那个文档，每当我提示的时候，因为它意味着我可以更清晰地提示，并与 AI 进行更有意义的对话，因为它正在使用我的领域模型，使用我的……
<details>
<summary>Original English</summary>

**Matt Pocock**: So to make that concrete, I have a skill um I have a set of skills in mattpocock/skills, which got insanely popular. It has like 13,000 stars or something. And one of those skills is ubiquitous language skill. Ubiquitous language is essentially a concept where you create a document which essentially defines the terms of what you're talking about. And when you let's say you're a client and I'm a guy building a system for you, when I say um a mole, for instance, we might be talking about a health application where we're investigating moles or we might be talking about spies or something where we need to understand what a mole is in that context, you know? Or the animal.

</details>

**主持人**: 你保留那个文档，你保留那个技能……
<details>
<summary>Original English</summary>

**Host**: You keep the document you keep the skill

</details>

**Matt Pocock**: ……一直开着？我保留……我的意思是，它生成一个 Markdown 文件，放在我的仓库里，我一直开着它，一直看着它。所以我们想到了一起。
<details>
<summary>Original English</summary>

**Matt Pocock**: open? I keep I mean, it generates a markdown file that sits in my repo and I just keep that open, look at it all the time. So we're thinking along the same lines.

</details>

**主持人**: 它会进入你的 agents.md、Claude.md 还是仅仅是供你人工参考？
<details>
<summary>Original English</summary>

**Host**: And does it go in your agents.md Claude.md or is that literally just for your human reference?

</details>

**Matt Pocock**: 我在 agents.md 中保留了一个引用。我非常担心在里面放太多东西。但它知道它在那里，以备不时之需，但主要是当它在仓库中进行搜索，在探索时，它会使用那些术语并搜索那些术语，而那个文档就会出现。
<details>
<summary>Original English</summary>

**Matt Pocock**: I keep a reference to it in agents.md. I'm very nervous about putting too much in yeah. But it knows it's there if it needs to see anything, but mostly when it's doing searches within the repo, when it's exploring, it'll use those terms and search for those terms and the the document comes up.

</details>

**主持人**: 是的。更广泛地说，关于 AI 的趋势，我认为你一直在解释和教授事物方面做得非常出色。你是怎么做到你所做的事情的？你的视频……为什么效果这么好？
<details>
<summary>Original English</summary>

**Host**: Yeah. Just just more broadly on AI trends, I I I think you have been really good at explaining and teaching things. How do you do what you do? Your your videos uh do so well.

</details>

**Matt Pocock**: 我认为英国口音并没有什么坏处。
<details>
<summary>Original English</summary>

**Matt Pocock**: I think the British accent doesn't hurt.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Matt Pocock**: 但我认为你也很……你在推特上表现得棒极了。就像……你知道，人们常说我做得很好，但我和你比起来，我差远了。
<details>
<summary>Original English</summary>

**Matt Pocock**: >> [laughter] >> But I think you're also like you're normally amazing on Twitter. And like you know, as much as people say I'm good at it, I'm not compared to what you do.

</details>

**主持人**: 嗯，我……
<details>
<summary>Original English</summary>

**Host**: Well, I mean

</details>

**Matt Pocock**: 我不真的理解它，首先。我所知道的是，我在成为一名开发者之前，曾做过 6 年的语音教练。当我成为一名开发者时，我注意到……我从底层开始，真的。我从初级到中级，到高级，等等。而沟通能力总是我觉得我拥有的一项非常强大的技能，而其他人都没有。我认为，在过去的几年里，我选择做的是真正缩小我的焦点。再次，我不是试图成为一个评论员，对吧？我只是在试图教东西。所以，这意味着我需要将我的时间分配在学习东西和找出正确的措辞上。这就是为什么，再次回到这些文本，它们如此有用，因为我现在有了所有这些模型，我可以用来向人们解释事物。是的，我不知道。我不知道我为什么做得这么好。我大部分时间都不觉得我做得好。大部分时间我都觉得我只是看到了需要改进的地方。
<details>
<summary>Original English</summary>

**Matt Pocock**: I don't really understand it, first of all. What I do know is that I spent 6 years as a voice coach before I became a developer. And what I noticed when I became a developer is I would I would you know, I started from the bottom really. I was working as a junior going up to mid, senior, blah. And the ability to communicate always just felt like a ridiculous overpowered skill that I had in my locker that no one else had. And I think what I've chosen to do over the last couple of years is really narrow my focus. Again, I'm not trying to be a pundit, right? I'm just trying to teach stuff. And so that means I need to divide my time between learning the stuff and figuring out the right phrases to use about it. This is why again going back to these texts is so useful cuz I have all of these models now that I can use to explain things to people. Yeah, I don't know. I don't know why I'm so good at it. Mostly I don't feel good at it. Mostly I feel like I just see the things to improve.

</details>

**主持人**: 也许你可以带我们走一遍，比如说，Claude Code 的工作坊，或者你做的其他什么？准备这样的东西需要什么？比如，研究过程是怎样的，你又会舍弃什么？
<details>
<summary>Original English</summary>

**Host**: >> maybe you can walk us through maybe the Cloud Code workshop or something else that you did. What goes into preparing something like that, right? Like what what is the research process and what do you throw out?

</details>

**Matt Pocock**: 是的。比如说，我们有一个探索和利用的阶段，对吧？在那里我正在弄清楚这个工作坊可能是什么样子。我最近的课程花了大约 2 个月的时间来准备。它大约是……我不知道，4.5 小时的精心剪辑的视频，但有很多练习，很多东西在里面，大概有 100 个不同的单元，我们这么说吧。所以，比如说，我弄清楚了……就像我从零开始。什么会很有趣？什么在这个环境中很有趣？我在这里的角度是什么？我把很多东西都放在 Obsidian 库里。所以，大量的想法，基本上是一个 Zettelkasten，如果你听说过这种方法的话。然后这些松散的笔记开始……嗯，开始凝聚成一个计划。而且我actually 已经构建了一个自定义应用程序来规划这些东西。所以这意味着我可以开始看到各个部分，看到我想要看到的各种信息分组。从那里，我优先考虑每个单独的课程，弄清楚它对课程运行有多重要。P1、P2、P3。然后我记录下所有的 P1，基本上，然后这就是课程，基本上。因为很多东西都会被剪掉，因为它放不进去了，或者有各种各样的顾虑和事情。所以，这种方法以及发展……这个想法，即每节课只教一件事，每节课都应该……所有知识之间的依赖关系都应该超级清晰，而且你应该……总是挑战人们，但不要让他们不知所措。我想这可能就是我做了这么长时间的经验积累下来的直觉。但如果你把这个想法放在心里，你就很难出错。
<details>
<summary>Original English</summary>

**Matt Pocock**: Yeah. Let's say we have an explore and exploit phase, right? Where where I'm figuring out what this workshop might look like. My most recent course took about 2 months to put together. It's about I don't know, 4 and 1/2 hours of very tightly edited video, but lots and lots of exercises, lots and lots of stuff in there, about 100 different units, let's say. So let's say you I figure out exact like I start from scratch. What would be interesting to show, what's interesting in this environment, what's what's my angle here? And I just make a ton of stuff inside an Obsidian vault. So tons of ideas, essentially a zettelkasten, if you've ever heard of that approach. And these loose notes then kind of sort of start coagulating into a plan. And I have actually a custom application that I've built for planning this stuff, too. So this means that I can then start seeing sections, start seeing groupings of information that I want to see. From there, I prioritize each individual lesson, work out how important it is to the running of the course. P1, P2, P3. I then record all the P1s mostly, and then that's the course, essentially. Cuz most loads of stuff gets left on the cutting room floor cuz I just can't fit it in or it has various concerns and things. So that approach and developing this idea that each lesson should only teach one thing, each lesson should depend and the dependencies between all the knowledge should be super clear, and you should always challenge people without overwhelming them. And this is I suppose just instincts I build up over a long time of doing this.

</details>

**主持人**: 是的。你是否感受到人们学习方式的任何变化？因为……你可以随时问一个……你可以问 ChatGPT。我不知道。这是一个……我想这是一个更广泛的教育概念，对吧？比如说……你是否给人们更多的练习？你知道，它是否更多地是动手操作的？
<details>
<summary>Original English</summary>

**Host**: Yeah. Do you feel any changes in how people learn? Because there's a lot of you can just ask a brock. You can ask ChatGPT. I don't know. This this is a I guess a more broader education concept, right? Of like do you give people more exercises?

</details>

**Matt Pocock**: 你可以教人们三件事。你可以教他们知识，通过讲座来做到这一点，对吧？这就是事物如何运作，这些是术语。你可以教他们技能。你……这是如何做到的。试着用互动练习来做。或者你可以教他们智慧。而智慧是最难的。智慧如何教？对我来说，那就是进行讨论，小组讨论，在工作坊中进行，这是推荐的方法。但智慧是很难获得的。而实际上与 AI 合作，你可以……你可以通过与 AI 交谈来获得一点智慧。你以前从未能……能够拥有这样的学习机制，你知道吗？书籍主要是基于知识的。你知道，你可以从中获得一点智慧，但你必须自己做一些工作才能得到它。但我注意到的是，我越是倾向于……嗯，AI 实验性的东西，人们就越会对我的材料敬而远之。我发现，实际上，传统的方法才是……
<details>
<summary>Original English</summary>

**Matt Pocock**: You can teach people three things. You can teach them knowledge, and you do that through lectures, right? This is how things work, these are the terms. You can teach them skills. You this is how to do it. Try doing it with an interactive exercise. Or you can teach them wisdom. And wisdom is the hardest. How do you teach wisdom? For me, that's been doing discussions, small group discussions in workshops is kind of the recommended approach. But wisdom is something that is really hard to get. And actually working with AI is something you can can sort of get to wisdom a little bit by talking to AI. You've never really been able to able to have that with any kind of learning mechanism before, you know? Books are mostly knowledge-based. You know, there's a little bit of wisdom you can glean from them, but you've got to do a bit of work on your own to get there. But what I've noticed is the more I lean into the kind of AI experimental stuff, the more it actually turns people off my materials. I'm finding that actually a

</details>

**主持人**: 给我讲座，是的。是的，什么……
<details>
<summary>Original English</summary>

**Host**: >> Give me the lectures, yes. Yeah, what

</details>

**Matt Pocock**: 仍然对大多数人来说是有效的。大多数人仍然只想以传统的方式学习，而我对此完全没问题。你知道，在创作者经济浪潮时，Maven 一直专注于互动讨论，然后结果是人们只是想要讲座。他们……他们可能需要一点家庭作业，但很多人甚至不做家庭作业。
<details>
<summary>Original English</summary>

**Matt Pocock**: still works for most people today. Most people just still want to learn a traditional way, and I'm totally fine with this sort of The you know, back when there was the creator economy wave, Maven was all about the interactive discussions, and then it turns out that people just want lectures. And they they maybe a bit of homework, but a lot of them don't even do the homework.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: That's right.

</details>

**Matt Pocock**: 是的。所以我说你已经找到了最终的形态，那就是讲座。
<details>
<summary>Original English</summary>

**Matt Pocock**: >> [laughter] >> Yeah. And I So what you're saying is that I've arrived at the ultimate form factor, which is just just lectures.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: >> [laughter]

</details>

**Matt Pocock**: 我是说，我对我的内容非常谨慎，以至于……要让人真正地完成工作。即使在我的 TypeScript 内容中，我也会这样组织，以至于人们会……你基本上会被 thrust 到一个问题中，然后必须自己解决。之后我才会给你知识。而这种方法感觉很不错，真的。
<details>
<summary>Original English</summary>

**Matt Pocock**: I mean, I I'm very careful with my stuff to really force people to do the work, essentially. Even in my TypeScript stuff, I would structure it so that people would have almost you'd essentially just be thrust into a problem and have to solve it on your own. I would give you the knowledge afterwards. And that approach has felt pretty good, really.

</details>

**主持人**: 是的。所以，是的。
<details>
<summary>Original English</summary>

**Host**: Yeah. So yeah.

</details>

### TypeScript 在 AI 工程中的崛起

**Matt Pocock**: 我注意到的一件事是，当我开始做 AI Engineer 时，我一直很清楚它应该是 50% Python，50% TypeScript。我想，这种情况已经改变了。我想今年是 TypeScript 在 GitHub 调查中超越 Python 的一年。嗯，我没有预料到这一点。我认为 Python 在后端方面更具表现力，尤其是在后端方面。而 TypeScript 则存在我们一直以来在 TypeScript 中遇到的 TypeScript 依赖性问题。我不知道。你认为 TypeScript 正在获胜吗？我的意思是，你可能会偏向于说“是”。
<details>
<summary>Original English</summary>

**Matt Pocock**: Something I've noticed when I started AI engineer, I was pretty conscious about it being 50% Python, 50% TypeScript. I would say that's changed. I think this year is the year that TypeScript overtook Python in the GitHub survey. And um I didn't really foresee that coming. I think that Python is somewhat more expressive, especially in useful in the back end. And TypeScript has the TypeScript dependency issues that we've always had in TypeScript. I don't know. I I think like do do you think TypeScript is winning? I mean, you you

</details>

**主持人**: 当然。而且我的回声室是 100% TypeScript。100% TypeScript。而且，再次，没有评论员。我……我不是评论员。我的意思是，TypeScript 拥有……
<details>
<summary>Original English</summary>

**Host**: >> would be biased to say yes. >> Of course. And my echo chamber is 100% TypeScript. 100% TypeScript. And again, no punditry. I like I'm not a pundit. I

</details>

**Matt Pocock**: 这个令人难以置信的丰富生态系统，拥有各种框架和工具，以及非凡的……而且你拥有……Vercel Next.js 和 Cloudflare Next.js。
<details>
<summary>Original English</summary>

**Matt Pocock**: mean, what you have with TypeScript is this incredibly rich ecosystem of frameworks and tools and extraordinary And you have the

</details>

**主持人**: 确实如此，对吧？我不是……我在开玩笑。但你知道，你在……你……所以你在应用程序的构建方面，你不能忽视 TypeScript。你知道，当它涉及到构建应用程序时。而且这似乎……正在构建这些东西的每个人，正在构建聊天应用程序的每个人，大多都在这样做。如果你关心 UX，你关心交付优秀的东西，你大多是在用 TypeScript 来做。至少，这是我所看到的。
<details>
<summary>Original English</summary>

**Host**: Versel Next.js and the Cloudflare Next.js. Exactly, right? I'm not I'm I'm taking the piss. But you know, you you so you can't overlook TypeScript in any conversation, you know, when it comes to building applications. And that just seems like everyone who's building this stuff, everyone who's building chat applications, is mostly doing it. If you're concerned about UX, you're concerned about shipping great stuff, you're mostly doing it in TypeScript. At least, that's what I see.

</details>

**Matt Pocock**: 是的，是的。我认为 TypeScript 可能会赢得 AI 工程的胜利，而这是我没有预料到或看到的，我甚至不知道如何……如何围绕这一点进行定位。因为……我认为这确实意味着很多不同的事情，关于我选择在我的工作中推广或押注哪些框架。
<details>
<summary>Original English</summary>

**Matt Pocock**: Yeah, yeah. I I I think it could be that TypeScript is going to win AI engineering, and that's something that I haven't anticipated or seen or I don't even know how to sort of position around this. Because it it I think it really does mean a lot of different things for what frameworks I choose to promote or bet on in in in my line of work.

</details>

**主持人**: 是的，这很有趣。还有其他你特别着迷的 AI 话题吗？你知道，你正在……你正在完成你的 Claude Code 探索，接下来是什么？
<details>
<summary>Original English</summary>

**Host**: Yeah, it is interesting. Any other topics in AI that you're particularly captivated by? You know, you're you're finishing up your Cloud Code exploration, what's next?

</details>

**Matt Pocock**: 嗯，我认为这是我做过的最成功的课程。所以在过去的 18 个月里，我一直在努力弄清楚我的定位，努力弄清楚我在哪里。我甚至……那种 TypeScript 出现并取代 Python 的想法，是我之前赌过一点的方向。我甚至制作了一个 TypeScript eval 的框架，叫做 Everlight。
<details>
<summary>Original English</summary>

**Matt Pocock**: Well, I think this has been the most successful course I've ever done. So like for the last 18 months I've been trying to figure out my positioning, trying to work out where I fit. I even sort of That idea of sort of TypeScript coming and eating Python is something that I was betting on for a little bit. I even made a TypeScript eval's framework called Everlight.

</details>

**主持人**: 我没见过那个，是的。
<details>
<summary>Original English</summary>

**Host**: I I didn't see that, yeah.

</details>

**Matt Pocock**: 是的，它基本上……它在开发方面停滞了。但你知道，人们对 eval 并不真正感兴趣，你知道，eval 不够性感。现在没有人对做 eval 感到兴奋，对吧？
<details>
<summary>Original English</summary>

**Matt Pocock**: Yeah, which is sort of stalled in its development and stuff. But you know, people are not really interested in eval's, you know, you like eval's are not sexy. Like no one's excited to do eval's these days, right?

</details>

**主持人**: 我们这里有很多人会不同意。
<details>
<summary>Original English</summary>

**Host**: >> We have many many people who would disagree here.

</details>

**Matt Pocock**: 我的意思是，从我和大家交流来看，在我制作的关于它的内容中，它并没有什么进展。至少现在人们还没有真正喜欢它，我认为。嗯，至于我接下来要去哪里，嗯，我想……我想编码代理的争论基本上要结束了。它们大多正在朝着类似的方法聚集，那就是……你知道，Firebase 系统，一套简单的工具。而且我认为我对此感兴趣，并扩展到那个领域，并关注如何制作一门课程，可能……就像一次性完成所有代理。可能。并……嗯，尝试……构建框架，构建……嗯，你知道，软件工厂的方法，这些方法基本上独立于你正在使用的代理。所以一种……嗯，在。而且我认为，在接下来的几个月里，让我们这么说吧。我不是……我不是一个水晶球。控制的反转将变得非常重要，即你将更多的控制权放在开发者手中，而不是……嗯，约束中。
<details>
<summary>Original English</summary>

**Matt Pocock**: >> [laughter] >> I mean, from everyone I've talked to in the content I produce on it, it doesn't go anywhere. At least people are not kind of into it yet, I think. Um in terms of where I'm going next, uh I think that I think that the coding agents kind of debate is sort of ending, really. Like they're mostly coagulating toward a similar approach, which is you know, Firebase systems, a simple set of tools. And I think I'm interested in expanding into that kind of area and looking at how to make a course that potentially like does all the agents at once, possibly. And sort of trying to build frameworks and build methods of uh you know, software factories that are kind of independent of the agent that you're using. So a kind of at. And I think that coming up for the next couple of maybe the next few months, let's say. I'm not a not a clairvoyant. That the inversion of control is going to be really important, where you put more control in the hands of the developer

</details>

**主持人**: 嗯……哦。我以为开发者想要更少的控制，而不是更多。是这样吗？
<details>
<summary>Original English</summary>

**Host**: >> and less in the harness. Yeah. Um Oh. I thought the developer wants less control, not more. Is that not true?

</details>

**Matt Pocock**: 我认为这是一个权衡，对吧？因为如果你使用 Claude Code，比如说，直到最近你还看不到 Claude Code 的内部，对吧？你……嗯，有一点……有一个框围绕着 Claude Code，你不需要看里面。那是令人安心的，对吧？因为你只是……“好吧，这套装置想让我做什么？我顺着它的方向走吧。我不太担心里面是什么。”而你得到的是易用性，但你失去了可观测性。你失去了……嗯，控制里面发生了什么并调整它。而这个权衡对我来说真的很有趣，因为比如说，如果我们看 Pi（一个 AI 框架），它是由微小的、原始的组件组成的，你完全是从零开始构建的。现在，如果你能很好地使用 Pi，这意味着什么呢？就是你对系统有完全的控制，你可以观察系统的所有部分。但然后你需要维护更多东西，需要关心更多东西，会出错的东西，这一切都取决于你。所以这个权衡是我接下来想探索的，当然。
<details>
<summary>Original English</summary>

**Matt Pocock**: I think there's a trade-off, right? Because if you're using Cloud Code, let's say, and until recently you couldn't see Cloud Code internals, right? You sort of had a there was a sense of a box around Cloud Code that you didn't need to look inside. And that's comforting, right? Because you just sort of go, "Okay, what what does the harness want me to do? Let's lean in its direction. Let's not worry too much about what's inside." And what you get is you get ease of use, but you lose observability. You lose the ability to kind of control what's going on and tweak what's going on. And there's that trade-off is really interesting to me because let's say we look at Pi instead, which is composed out of tiny little primitives that you totally build up from the ground. Now, what that means if you're able to use Pi really well is you have total control over the system and you can observe all the parts of the system. But then you have more stuff to maintain, stuff to care about, stuff that can go wrong, and it's all up to you. So that trade-off is something I'm interested in exploring next, for sure.

</details>

**主持人**: 是的，我认为所有这些发展都非常有趣。我认为世界需要更多像你这样的老师。我也被邀请在我的播客上做更多类似的事情，很多人也在努力……就是……变得更高效地使用 AI。我想知道如何才能做好。我认为你显然更专注于工程和编程以及软件工程。但也有……有一些通用的方法，比如想知道，好吧，我该如何更有效地过我的生活？如何更有效地管理我的团队和我的公司？
<details>
<summary>Original English</summary>

**Host**: Yeah, I think it's very interesting all the these these developments. I think the world needs more like teachers like yourself. I have been also asked to do more stuff like that on on my podcast, and a lot of people are trying to also just like get out get more productive with the AI. And I wonder how to do that well. I think you're obviously more focused on engineering and programming and software engineering. But there's a there's equivalents of like more generalists that want to know, okay, well, how do I live my life more efficiently just in general? How do I run my team and my company more efficiently?

</details>

**Matt Pocock**: 完全同意。奇怪的是，Obsidian 似乎在那方面赢了。他们只有四个人。
<details>
<summary>Original English</summary>

**Matt Pocock**: Totally. It seems like Obsidian is like kind of winning there, weirdly.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: Mhm. They're four people.

</details>

**Matt Pocock**: 是的。
<details>
<summary>Original English</summary>

**Matt Pocock**: >> [laughter] >> Really? They're really that small? Four people? Wow, I didn't know that. They they they recently posted a job for a fifth person and that thing got 9 million views because everyone was like, what do you mean you you you've done this with four people?
<details>
<summary>Original English</summary>

**Matt Pocock**: >> [laughter] >> That's crazy. I never heard that. Wow.

</details>

**主持人**: 真是太疯狂了。我从没听说过。哇。
<details>
<summary>Original English</summary>

**Host**: I mean, that the stuff that we're doing as software engineers now is like we seem to be a step ahead of everyone else because we're able to work in a domain where AI is actually producing quality stuff.

</details>

**Matt Pocock**: 我不知道。这意味着我们现在作为软件工程师所做的事情，我们似乎比其他人都领先一步，因为我们能够在一个 AI 确实能产生高质量内容的领域工作。所以，我正在做的是，我正在与我的……我正在写我的技能集，我正在思考如何将它们抽出来，在我的日常生活中使用它们？例如，我从 Claude Code 中取出什么，然后放进……
<details>
<summary>Original English</summary>

**Matt Pocock**: And so what I'm doing is as I'm working with my with my set of skills that I'm kind of authoring, I'm thinking how can I pull these out and use these in my everyday life? For instance, what do I take out of Claude code and put

</details>

**主持人**: 立即查看你的技能。
<details>
<summary>Original English</summary>

**Host**: >> to look up your skills right now.

</details>

**Matt Pocock**: 是的，mattpocock/skills。其中有一个叫做“grill me”。它基本上只有三个……嗯，句子那么长。好吧。它基本上是让 AI 无情地采访你，对吧？直到你达成一个共同的想法。我相信每个人都……嗯……用过或用过这种技术。我意识到我在各种领域都需要这项技能。任何我想让 AI 与我保持一致的领域，我想达成一个共享的理解，我想让它……嗯，可能甚至……人为地……嗯，质疑它自己的假设，质疑我的假设，直到我们达成一个共享的设计理念。我用它来做各种各样的事情，生成文档，做很多很多这样的事情。所以我认为，我越是将它们分解成独立的、可组合的部分，它们在软件工程之外就越有用。
<details>
<summary>Original English</summary>

**Matt Pocock**: >> Yeah, mattpocock/skills. And there's one one in particular called grill me Okay. which is like three uh sentences long. Okay. And which basically gets the AI to interview you relentlessly, right? Until you reach a shared idea. I'm sure everyone sort of had that technique or used that technique. And I've realized I need that skill in all sorts of domains. Any kind of domain where I want the AI to be aligned with me, I want to reach a shared understanding with the AI and I want it to sort of artificially, maybe even, sort of just question its own assumptions, question my assumptions until we reach a shared design concept. And I've used that for all sorts of stuff, for generating documents, for doing tons and tons of things like this. And so I think the more I break these down into individual composable parts, the more useful they are outside of software engineering, too.

</details>

**主持人**: 是的。这就像 20 个问题游戏等等。
<details>
<summary>Original English</summary>

**Host**: Yeah. It's like the 20 questions and and all that.

</details>

### 结论

**Matt Pocock**: 嗯，好了，这太棒了。很高兴能再次聊聊。我也想把 Lisp 的听众介绍给你。嗯，我认为解释 AI 和保持最新状态的工作永远不会结束。所以，嗯，很高兴有朋友……嗯……也从 JavaScript 转向了 AI。
<details>
<summary>Original English</summary>

**Matt Pocock**: Um okay, this has been beautiful to catching up. Uh I want also want to just introduce the Lisp audience to your work. Um I think the work of explaining AI and keeping up to date is never done. So, uh just glad to have friends in uh

</details>

**主持人**: 绝对。这是一段有趣的旅程。是的。今天还在继续。好的。
<details>
<summary>Original English</summary>

**Host**: who've also made the crossover from JavaScript to AI. Absolutely. It's a been a fun journey. Yeah. Continues today. All right.

</details>

**Matt Pocock**: 谢谢你。很好。
<details>
<summary>Original English</summary>

**Matt Pocock**: >> Thank you. Nice.

</details>

**主持人**: [笑声]
<details>
<summary>Original English</summary>

**Host**: >> [laughter]

</details>