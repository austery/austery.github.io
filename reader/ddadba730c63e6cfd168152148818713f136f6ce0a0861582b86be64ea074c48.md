---
author: Latent Space
date: '2026-07-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9_0hs2sxHHo
speaker: Latent Space
tags:
  - model-interaction
  - code-generation
  - open-source-ai
  - scaling-laws
  - internal-evaluation
title: 关于模型、工具调用与人工智能民主化的技术探讨
summary: 文章讨论了在复杂任务中，将大型语言模型（LLM）与外部工具和虚拟环境结合的趋势。作者认为过度依赖复杂的工具链可能是一种低效的做法，并回顾了早期研究如何通过对基础模型的深入探索（如循环神经网络到Transformer）来推动代码生成能力的演进。此外，文章还探讨了开源社区在AI发展中的关键作用，强调约束条件如何驱动创新，以及构建内部评估流程和模型打磨的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/15 -->

### 关于MCP和工具的看法与AI发展背景

**Speaker A**: 我认为MCP和工具是愚蠢的。如果你正在寻找复杂的任务，越来越长的视野，越来越复杂的任务，无论是在编码还是其他方面，你都会与数据源进行交互，对吧？你将与安装在某种形式虚拟机上的东西进行交互。然后我们在中间放置像MCP这样的东西。我们在它之间放置工具调用，让模型可以编写代码并与系统进行交互。我们开始看到像Laguna S这样的事情正在发生。你也会在像Frontier模型中看到这一点。它们越来越不再是这里了。我们将把50个工具塞进系统的提示词里，在这个安装了这些二进制文件的虚拟机里。这段代码你可以在这里操作，在一个文件夹里，在那里你可以写，你知道你的内存如果你愿意的话。而模型正在使用代码来完成复杂的任务。

<details>
<summary>Original English</summary>

I think MCP and tools are stupid. If you are looking for complex tasks, increasingly longer horizon, increasingly complex tasks, doesn't matter if it's coding or something else, you are going to be interacting with data sources, right? And you're going to be interacting with things that are installed on some form of a virtual machine. Uh, and we're putting like MCP in between. We're putting tool calls in between it where the model can just write code and interact with the system. And we're starting to see that like Laguna S does this a lot. You'll see this as well in like Frontier models. They're increasingly no longer here. We're going to stuff 50 tools in the like system prompts to no here's a virtual machine with these binaries installed. This code base you can operate in here a folder where you can write you know your memory if you want to. And the model is using code to do complex tasks.

</details>

**Speaker A**: 在进入今天的节目之前，我有一个小消息给听众。谢谢你。如果你没有选择点击并收听我们的内容，你就无法获得你如此明确想要的人工智能工程、科学和娱乐内容的。我们几乎每天都收到赞助商的接触。但幸运的是，足够多的人订阅了我们，以在没有广告的情况下保持这一切的可持续性，而我们想保持这种状态。但我只是想请大家一个请求。你能做到的最强大、完全免费的事情是点击那个订阅按钮。这是我唯一会向你提出的要求，它对我来说和我的团队——他们非常努力地每周把Inspace带给你——意味着绝对的一切。如果你做了，我保证，我们永远不会停止努力让这个节目变得更好。现在，让我们开始吧。

<details>
<summary>Original English</summary>

Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis. But fortunately, enough of you actually subscribe to us to keep all this sustainable without ads, and we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you, and it means absolutely everything to me and my team that works so hard to bring the Inspace to you each and every week. If you do it, I promise you, we'll never stop working to make the show even better. Now, let's get into it.

</details>

### 嘉宾互动与AI民主化的起源

**Speaker A**: 好的，我们在这里和Khan来自PSA一起坐着，还有Ibu。欢迎。

<details>
<summary>Original English</summary>

All right, we're here in the studio with Khan from PSA um together with Ibu. Uh, welcome.

</details>

**Speaker B**: 谢谢你。谢谢你的邀请，各位。很高兴能在这里。

<details>
<summary>Original English</summary>

>> Thanks. Thanks for having me, guys. It's good to be >> Yeah. Fresh on the plane. You texted me. You're like, "Hey, I'm on my way to SF." I was like, "You're on a plane right now, right?" Like, "Hey."

</details>

**Speaker A**: 在我给你发短信之后，我意识到你可能带着严重的时差来了。今天想提供一些有趣的体验，但我们来做吧。

<details>
<summary>Original English</summary>

>> Yeah. Fresh on the plane. You texted me. You're like, "Hey, I'm on my way to SF." I was like, "You're on a plane right now, right?" Like, "Hey." after I texted you, I realized that probably coming in with major jet lag. Going to offer some fun experiences today, but let's do it.

</details>

**Speaker B**: 嗯，我的意思是，我想告诉嘉宾的是他们实际上不必准备那么多，因为如果你每天都在认真工作，那么即使是你模糊记得的那些东西，对那些不生活在你世界里的很多观众来说也会是全新的，对吧？嗯，所以10年前你曾在Google Slush上做过演讲，谈论AI的民主化。现在你在这里开源了一个我们即将讨论的不可思议的新模型，但我猜是什么让你进入了AI民主化的领域？比如，这从你的领英或什么那里并不是显而易见的。

<details>
<summary>Original English</summary>

>> Uh, I mean, I think the thing I would tell guests is that they don't actually have to prepare that much because if you're truly working on this every single day, then even like what you hazily remember is going to be new for a lot of the audience that don't live in your world every day, right? Um, so 10 years ago you did a talk at Google Slush, uh, talking about the democratization of AI. Um, and now here you are like open sourcing an incredible new model that we're going to talk about, but I guess what got you into democratization of AI? Like it's not obvious from your LinkedIn or something.

</details>

**Speaker B**: 不，一点也不明显。实际上，我不认为我进入这个领域的方式是显而易见的。我进入这个领域的功劳要归于Andre Kitchin。2015年，他写了一篇文章，叫做“Recurrent的非理性有效性”。

<details>
<summary>Original English</summary>

>> No, it's not at all. Actually, I don't think it's obvious how I got in this space. Um, I owe getting into this space to Andre Kopathy. In 2015, he wrote an article called the unreasonable effectiveness of recurrent.

</details>

**Speaker A**: 是的。是的。那篇文章，我读了它，并在当时一夜之间将我的初创公司转向研究RNN、然后是LSTM和Transformer模型，以便能够编写代码。如果你去这篇文章里往下滚动，你就能开始看到这正是后来成为语言模型的先驱。所以，嗯，至少他当时是字符级别的语言模型，它们开始真正预测字母。他在这里有一个例子。有一个小Paul Graham生成器，你可以大致读懂它，有点道理，但它……还有下面有一个代码的例子。它说莎士比亚。

<details>
<summary>Original English</summary>

>> Yep. >> And that article, I read it and I pivoted my startup at the time overnight to working on RNN's and later LSTMs and transformer models to be able to write code. If you go to this article and you scroll down, you can kind of start seeing like this was the precursor to what ended up becoming language models. So, uh at least what he was character level language models that were starting to actually predict letters. Uh he has an example out here. There's a little Paul Graham generator and you can kind of read it in the text kind of makes sense but it doesn't uh and there's a little there's an example of code a little bit further down. It says Shakespeare

</details>

**Speaker B**: 和……因为某种原因，我读了这篇文章，我深入研究了关于RNN和LSTM的一切。对吧？在Transformer出现之前的那篇论文，我有一个完全不合理的信念，认为神经网络应该能够泛化到任何事情和任何东西，而且语言应该能够泛化到很多智能以及编写代码的能力。所以我开始构建Source，那是一家完全开源的公司，试图构建我们以前称之为“代码语言模型”的机器学习模型，我们在代码上花费了大约四年或五年时间，直到2019年底。这在今天听起来很酷，但那时没人关心，对吧？没人关心。我们处于黑暗中。我们一直在做事情。我们尝试将卷积神经网络应用于代码的结构。当我们注意力机制出现时，我们将其应用于LSTM，然后Transformer论文出来，它不是显而易见的，我们在整个旅程中错过了什么，我们走在正确的轨道上，但我们本应该继续扩展规模。

<details>
<summary>Original English</summary>

>> and and for some reason I read this and I went down the rabbit hole of learning everything I could about RNN's and LSTMs. Right? is pre-transformer paper and I had built a completely unreasonable belief uh that neural nets should be able to generalize to anything and everything and that language should be able to generalize you know to a lot of things that are intelligence and the ability to write code and so I started building Source which was a fully open source company trying to build uh what we used to call machine learning on code language models on code and we spent about four or five years on this uh till the end of 2019 And that sounds really cool today, but back then no one cared, right? Like no one cared. We were in the dark. Like we did things along the way. We tried applying convolutional neural nets to like the structure of code. We were you know when attention came out we were applying it to LSTMs and then the transformer paper came out and it was it wasn't obvious and what we missed throughout that entire journey that we were on the right track but we should have just kept scaling up. And today to all of us the scaling laws and scaling up seems like the most obvious thing.

</details>

**Speaker B**: 但花费我四五年生命在研究代码语言模型上，这并不明显。我对Google和OpenAI以及其他人有一些人非常尊敬，他们接受了那种信心并继续前进。我们最终失败了，而且那是我职业生涯最大的失败。对吧？你当时烧掉了1200万美元的投资者资金，那时是很多钱。是的，你仍然花了很多，但是……你与大约40个人一起花了几年时间只是痴迷于这个问题，生活转向了一个不同的方向，家庭变得更加关注，我保持低调，而且坦率地说，在接下来的两年里，我真的没有真正看语言模型，这有点大错，考虑到接下来的几年。然后ChatGPT出来，那有点像是一种证明。人们开始给我发短信说我找到了我以前的你工作演示文稿和这些旧演讲，在整个旅程中，你知道我们当时有一个非常明确的观点，即随着你构建更智能的AI，它应该开放和开源，当我们开始时， poolside 实际上情况完全不是这样。我想对我们在泳池边开始时非常坦诚：存在两个前提。一个是这项技术不会停止能力的积累，我认为对大多数人来说这很明显了今天。但3年前，当我们开始时，大多数人仍然在争论这些是随机鹦鹉还是不是。第二个是强化学习将是LLM能力的最大驱动力。今天非常明显，三年前并不是OpenAI或Google或Anthropic或其他任何机构持有的观点或方向。所以人们有点看不起我们，或者你知道这真的会成功。所以我们只是开始解决这个问题。我们从来没有再想过开源。我们只是保持低调，我们从头构建了我们的知识理解，对吧？我们并没有从一个现有的实验室中推出。所以我们拿起了论文并开始编写代码，弄清楚事情。直到今年年初，我和我的联合创始人Jason重新拾起了开源的对话。如果你回到我们网站上的一些早期内容，那非常直接。我们的目标是实现AGI。我们想支持一个丰裕的世界，我们想成为第一个到达那里、的公司。但我们是在今年年初开始谈论它的，因为它变得有点明显了世界正朝着一种开始有点像……有点挑衅我们的方向发展。这并不是一夜之间发生的。我们看到这种情况，我们觉得“好吧，世界的道路是这样的”。在整个旅程中，我用了一些作为类比或事情来使用。我说，如果我回到那些日子，大概2015年或2016年，我们正在做这个工作。我从书架上拿起了一本科幻小说。我在读关于2035年的书，AGI已经实现，故事将在接下来的几十年内结束，对吧？而我会有一个第一章，里面每个人都在试图弄清楚事情……

<details>
<summary>Original English</summary>

But having spent four or five years of my life on working on language models on code it wasn't obvious. I have a lot of respect to folks at Google and OpenAI and others who kind of took that confidence and and kept going. Uh, we failed ultimately at the time and it kind of was like biggest failure of my career. Right. You blew $12 million of investors money which was a lot back then. Yep. you spent still a lot but uh and you spent years with like a group of 40 people just obsessing over this problem and life took a different turn and and and family kind of became a focus and I kind of kept my heads down and really frankly didn't really look at language models for the following two years kind of big mistake considering following years and be really interesting and then chatbt came out and it was kind of like a vindication it's like people started texting me I found like my old you work decks and this old talks and and throughout that whole journey you know we we kind of really had a strong point of view at the time that like as you're building more capable intelligence it should be open and open open source when we started poolside that actually wasn't the case at all and I want to be very open about when we started poolside we were like there was a premise of two things. one is this technology is not going to stop compounding in capabilities I think to most people obvious today. But 3 plus years ago when we started most people were still arguing if these were stochastic parrots or not. Uh and the second was that reinforcement learning was going to be the biggest driver for LLM capabilities. Today very obvious 3 years ago was not an opinion held or direction held at either OpenAI or or Google or Anthropic or others. And so people kind of looked down on us a little bit or like you know this this really going to work. And so we just started working the problem. uh and we never really thought about open source again. We just kept our heads down and we and we built our like knowledge understanding from scratch, right? We didn't roll out of an existing lab. So, we picked up the papers and started writing code and figuring things out. And it wasn't until the beginning of this year that me and my co-founder Jason picked up the open source conversation again. And if you go back to some of the early things on our website, it was very straightforward. It was we want to get to AGI. We want to support a world of abundance and we want to be the first company that gets there. Uh but we started talking at the beginning of this year because it became kind of obvious that the world was going in a direction that was starting to kind of like kind of like pick at us a little bit. Like it didn't this didn't happen overnight. It was like a little bit we were seeing this and we're like okay the world's going down a path. And throughout this journey, there was something that I kind of used as a as an analogy or things. I said kind of well, if I go back to back in those days, kind of 2015 or 2016, we're working on this. And I picked up a sci-fi book off the shelf. Uh, and I was reading the book about 2035, AGI is achieved, and the story would be over the following, you know, decades, right? And I would have that first chapter where everyone's trying to figure things

</details>

### 对开源的重新关注与AGI的愿景

**Speaker B**: 我们只是保持低调，我们一直在构建我们的知识理解。对吧？我们并没有从一个现有的实验室中推出。所以我们拿起了论文并开始编写代码，弄清楚事情。直到今年年初，我和我的联合创始人Jason重新拾起了开源的对话。如果你回到我们网站上的一些早期内容，那非常直接。我们的目标是实现AGI。我们想支持一个丰裕的世界，我们想成为第一个到达那里、的公司。但我们是在今年年初开始谈论它的，因为它变得有点明显了世界正朝着一种开始有点像……有点挑衅我们的方向发展。这并不是一夜之间发生的。我们看到这种情况，我们觉得“好吧，世界的道路是这样的”。在整个旅程中，我用了一些作为类比或事情来使用。我说，如果我回到那些日子，大概2015年或2016年，我们正在做这个工作。我从书架上拿起了一本科幻小说。我在读关于2035年的书，AGI已经实现，故事将在接下来的几十年内结束，对吧？而我会有一个第一章，里面每个人都在试图弄清楚事情……

<details>
<summary>Original English</summary>

We just kept our heads down and we and we built our like knowledge understanding from scratch, right? We didn't roll out of an existing lab. So, we picked up the papers and started writing code and figuring things out. And it wasn't until the beginning of this year that me and my co-founder Jason picked up the open source conversation again. And if you go back to some of the early things on our website, it was very straightforward. It was we want to get to AGI. We want to support a world of abundance and we want to be the first company that gets there. Uh but we started talking at the beginning of this year because it became kind of obvious that the world was going in a direction that was starting to kind of like kind of like pick at us a little bit. Like it didn't this didn't happen overnight. It was like a little bit we were seeing this and we're like okay the world's going down a path. And throughout this journey, there was something that I kind of used as a as an analogy or things. I said kind of well, if I go back to back in those days, kind of 2015 or 2016, we're working on this. And I picked up a sci-fi book off the shelf. Uh, and I was reading the book about 2035, AGI is achieved, and the story would be over the following, you know, decades, right? And I would have that first chapter where everyone's trying to figure things

</details>

<!-- chunk 2/15 -->

### 对未来智能体生态的思考与公司发展路径

**Speaker A**: 你会看到下一章，然后你会看到那个世界处于十字路口，而它选择的那条路是三四个或一小撮公司将要创造所有未来的智能。当我想到这个故事时，它感觉像是一本反乌托邦科幻小说，而不是一本乌托邦科幻小说。但现实是，我是一个乌托邦科幻的家伙。所以我们稍微退后了一步，说：“嘿，我们能在这里扮演一个角色吗？”现在对我们来说很容易做到这一点，因为我们不在前沿，但我们就在前沿。我不认为我们能改变主意，而且我不是指当涉及太多资本、太多的期望时，你已经建立了一些东西了，对吧？我们是一个小团队，你知道的，只是在不断改进和完善。所以我们知道我们可以做出那个决定。但当我们越来越接近前沿，追赶上其他人，进行大量的自我反思和大量的对话之后，做这个决定会困难得多。即使存在重大的未解之谜，比如如何用开源基础模型来构建一个商业模式，这是一个大而开放的问题，我们还没有完全的答案，对吧？在什么点你就不再想发布开源模型了，因为模型的滥用带来了实际的风险？政府将如何回应开源？但我认为这一切都归结于一件事，我将停止这个独白：事实是我生活在一个拥有100个基础模型公司的世界里，而不是一个拥有五个。即使我是那五个中的一个。而且我们能为Hunter存在所做的最小且最有意义的贡献是开放我们的研究和开放我们的权重，对吧？现在并想弄清楚如何沿着这条路做得更多。

<details>
<summary>Original English</summary>

**Speaker A**: out. You'd get the chapter of Chhat coming out and then you would get to the chapter where the world was at a fork in the road and one that it picked was one where three or four or handful of companies were going to create all of intelligence moving forward. And when I thought about that story, it felt like a dystopian sci-fi book, not a utopian sci-fi book. And the reality is I'm a utopian sci-fi guy. like uh and so we kind of took a step back and said hey can we play a role here uh now it was easy for us to do so because we were not at the frontier but we were at the frontier I don't think we could have changed our mind uh and I don't mean this like it's when the moment there's too much capital involved too much expectations you've built up things right we're small team you know just improving and improving and so we we knew that we could make that decision now but it would be a lot harder to make as we got closer and closer to the frontier and caught up to others and did a lot of soulsearching and a lot of conversations uh and said, "No, this makes sense." Even if there's big unanswered questions like how the hell do you build a business model with foundation models about open source, big open-ended question that we do not fully have the answer to yet, right? At what point do you no longer want to release open source models because misuse of models has, you know, real potential risks associated with it? Uh how is the government going to respond to open source? Uh but I think it all just came down to one thing and I'll stop the monologue is the fact that I rather live in a world that has a 100 foundation model companies than a world that has five. even if I was one of the five. And the smallest and most meaningful contribution we can make for Hunter to exist is to open up our research and open up like our weights right now and kind of figure out along the way how we can like do more.

</details>

**Speaker B**: 是的。我我认为过去三年中，有更多事情变得更加真实了。你属于一个新实验室（Neolabs）的群体之一，现在人们称之为那个名字，你知道我们正在做这个，就在Thinky发布他们新的模型的那一天，你就是我们在他们的某些基准测试上进行性能开发的人，就像他们还没有它一样。所以这应该表明我认为，实际上这是那些有多个参与者留出空间的领域之一，而你看到了更多的特征，也许是20个而不是100个，但你就是那20个中的一个。我真的希望如此。对。我认为我们对他们的发布感到兴奋。我对每个人发布都感到兴奋，因为最终选择竞争既会推动朝着正确的方向的发展。但是事实是我们创建模型，而虽然我们都在从同一桶数据中有效地汲取，但我们在我们的模型中引入了非常不同的行为和偏见。有些是故意的偏见，有些是完全的偏见。如果我们在一个开源模型将成为代币经济的一部分的世界中塑造一个生态系统，我并不认为这还有任何疑问。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I think if anything over the past 3 years that has become a bit more true. Um you are one of a cohort of Neolabs that people are now calling that and you know we're we're doing this on the day that Thinky launched their uh new model and you are our performing dev on their on some benchmarks that they released right like they just don't have it yet. Um so it should goes to show that I think like actually this is one of those things where like there actually is room for multiple players and you are seeing a little bit more of the feature maybe more like 20 not 100 but like you are one of the 20. I I really hope so. Right. I think we are I'm I'm excited about their release. I'm excited about everyone kind of releasing because like ultimately like choice competition is is both going to drive progress in the right direction. But the fact that like you know we we create models and while we all you know drink out of the same well of data effectively, we do introduce very different behaviors and biases in our models. Some are intended biases, some are completely biases. And if we shape up in an ecosystem in the world where open models are going to be a part of the token economy like I don't think there's any question about it anymore

</details>

**Speaker A**: 嗯，那么我们希望生活在一个公司、国家和人民可以选择并说“嘿，我最认同这个提供商，并且最信任他们处理这类事情”的世界。是的。我认为不仅仅是20个新实验室中的一个，直到最近，你知道，大多数开源创新都来自于中国的实验室，对吧？所以西方深度探索的是今天，好吧，也许它在思考机器的反射，但并没有很多人，对吧？所以，嗯，你们在法国、欧洲开始做了一些事情，但现在你基本上是在采取那种美国立场，而且不仅仅是那个，重点是，我们看到的中国模型不是超级开放的研究。你所做的工作我认为是最好的之一。所以每隔几个月你不仅会得到前沿模型，还会得到一种分解博客文章、技术报告，这里有构建前沿智能所需的一切，你知道你在填补那个差距，对吧？所以不只是开源权重，不只是西方，还有相当开放的研究。

<details>
<summary>Original English</summary>

**Speaker A**: uh then we want to be able to live in a world where companies countries people can choose and say hey I am most aligned and I trust most this provider for these kind of things. Yeah, >> I think more than just one of the 20 Neolabs um up until recently, you know, most of open-source innovation was coming from the Chinese labs, right? So there's the Deep Seek of the West is that today, okay, maybe it's thinking machines reflection, but there aren't many, right? So, um, one of the things you guys started sort of in France, Europe, but very much now you're kind of taking that American standpoint and more than just that, the point is the Chinese models that we see, they're not super open research. Uh, the work you put out is, I think, some of the best. So every few months you get not only frontier models but also here's a sort of breakdown blog paper technical report of here's everything for state of whenever to build you know frontier intelligence and you're filling that gap too right so not just only open weight not just western but also pretty open research

</details>

**Speaker B**: 不，我欣赏它。我认为这实际上是最有意义的贡献是二元对立。让我们称它们为它们是什么：是的，我们可以修改它们，我们可以改变它们，但把权重给某人并不能让他们最终重现你正在做的事情，对吧？现在存在围绕发布数据集的挑战，围绕发布某些东西的挑战，但是能够分享你的研究，比如我们是怎么做的？我们学到了什么教训？我们在计算上花费了数万次实验，我认为非常多。不过有一个更正，Vivv 和我这么说，因为这几年对我们来说有点令人困扰。我们实际上从零开始就是一家美国公司。

<details>
<summary>Original English</summary>

**Speaker B**: no I appreciate it look I think it's I think it's actually the most meaningful contribution rights are a binary let's call them what they are yes we can modify them we can change them but like giving someone the weights does not allow ow them ultimately to recreate what you're doing, right? And and so now there's challenges around releasing data sets, challenges around like release certain things, but being able to share your research like right, how did we do it? What are the lessons we learned that we spent, you know, tens of thousands of experiments of compute on I think very much so. One correction though, Vivu and I I say this because it's kind of been haunting us for quite a few years. We actually from day zero were an American company.

</details>

**Speaker A**: 是的。他们搬到了法国。所以故事一次就足够了，非常适合美国公司。我们一直都是一家美国公司，而且早期我们就做了一个非常明确的决定。我们说我们不会在湾区雇佣任何研究人员。我们将去世界其他地方寻找人才。那就是从美国中西部、西雅图到你知道塞拉维亚，还有台湾和新加坡和其他地方的一切。这是因为我们采取了一种观点，认为这将会成为这场人才战争，而且我认为多年来如此。现在三年前还没有完全明显。但我认为今天非常明显了，而且我们也意识到世界上最能提供最有趣创新的那些最优秀的人才不会只待在这里。所以这促使我们创建了一家完全远程的公司。我们最终在巴黎和伦敦以及不同的地方开设了办公室，我们在美国有很多团队，在国外也有很多团队，但我们一直采取这种观点，就是我们是一家美国公司，但是如果我们想让最好的工作与我们合作，我们就需要采取全球视角。现在我们在硅谷也有人，比如公司的发展，还有其他人，但我认为一个减慢我们最初发展的因素是它，但它现在让我们加速了，这就是为什么你看到我们模型和发布节奏的进步，因为我们没有从现有的实验室中推出，我们没有自由流动的信息。在当时我们只是采取了这个观点，就是好吧，那我们来解决问题吧，我们去读一下外面的一些论文，然后我们来弄清楚这些事情。多年来我们在模型训练中犯了一些很滑稽的错误，尤其是在前12个月里。有一些我至今仍然困扰着并让我感到害怕。我们可以稍后谈论它们。但它在团队中创造了一种韧性和持久性，对吧？多年来极少数人离开了我们，告诉我们“好吧，我们可以做到这一点”。当我们第一次从零开始写我们的第一个训练代码库时，它不是任何开源的fork。它是“好的，让我们从头构建它。”我记得我们有一个时刻花了三周时间解决一个优化器错误。比如训练就是无法稳定。我们对它非常痴迷，我们想也许我们错了。也许我们应该把这个仓库进行分支或直接做完。但后来当我们解决了它时，我仍然记得当时我们公司有五个人。当我们解决它时，我们是，“哦，如果我们愿意努力工作，我们可以做到这些事情。”我认为这种带有非常强的工程偏见的文化帮助我们到达了现在的地步。所以这里有一种关于开源和人才以及这些事情的观念。我认为我们只是从不同的起点做出了不同的决定。而且我认为我们很幸运。我确实想

<details>
<summary>Original English</summary>

**Speaker A**: and I do want to

</details>

<!-- chunk 3/15 -->

### 关于模型构建的工程化视角与经验总结

**Speaker A**: 绝对可以称之为幸运，但它也是团队非常努力工作的结果，现在开始在结果中有所体现了。

<details>
<summary>Original English</summary>

**Speaker A**: definitely call it lucky, but also a lot of hard work of the team that now like that's starting to kind of show up in results.

</details>

**Speaker B**: 只是因为我们可能不会再重新讨论这个了，但嗯，如果有人知道答案，这会是一个有趣的招聘挑战。是哪个 Bug？然后我们不会告诉解决方案，但是……

<details>
<summary>Original English</summary>

**Speaker B**: Uh just because we probably won't revisit this again, but um and this is a fun recruiting challenge if someone knows the answer. What was the bug? And then we we won't tell the solution, but

</details>

**Speaker A**: 所以这个 Bug 是你来测试我的记忆。所以，如果你……如果你把原子（atom）当作优化器，你有 epsilon，对吧？就在分母里，在分母里。而且在时间上，如果我回忆起来，你看了早期的 Llama 论文和一些类似的东西……

<details>
<summary>Original English</summary>

**Speaker A**: so the bug this is you're going to test my memory here. So but I think I think I can recall. So if you so if you look at um so if you take like atom as an optimizer you have epsilon yeah which is right like in the denominator exactly in in the denominator and at the time if I recall you looked at like the early lama papers and things like that

</details>

**Speaker B**: 人们会榨取（juicing）epsilon，大概是这样。他们会像……我不知道是不是 eus 4 的高值 epsilon，如果你在训练期间思考这个问题，这有点奇怪和反直觉，因为我们只是通过在分母中添加一个随机数，也就是小数点后添加一个随机数来给我们的优化器增加噪声，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: people were juicing epsilon like quite a bit like they were like adding I don't know if it was eus 4 whatever like a high value for epsilon and if you think about this during training it's kind of like bit weird and counter intuitive that we're adding noise to our optimizer by just adding effectively like a random number in the denominator uh right like behind the decimal point and uh

</details>

**Speaker A**: 我不记得确切的 Bug 了，但我记得的是，一旦我们解决了它，我们就再也不需要像在 Llama 论文和其他地方那样榨取这么多的 epsilon 了。那是一个……一个基础性的时刻，我们信任了那篇论文，然后我们是这样想：哦，不，它必须是这样的，它必须有这么高的 epsilon 值，但对我们来说直觉上说不通，为什么你必须有这么高？比如，如果你只是想避免除以零，为什么值不能非常小呢？

<details>
<summary>Original English</summary>

**Speaker A**: and and it was like one of those fundamental moments where we had trusted this paper that was out there and we're like oh no it has to be this way it has to have this high value of epsilon but it made no sense to us intuitively like why do you have to have this so high? Like if you're just trying to avoid division by zero, why can't the value be extremely small?

</details>

**Speaker B**: 那是那种你意识到，比如，从零开始寻找东西会建立更好的直觉。因为你在模型构建中很快学到的一件事是，你最初的直觉会受到很强的冲击，对吧？它是一种非常实验性的科学，那些看起来很明显的东西你会很快学会你是错的，希望你能弄清楚为什么。有时候你甚至不会……

<details>
<summary>Original English</summary>

**Speaker B**: and and that was kind of like one of those moments where you realize like okay, finding things out from scratch yourself builds a better intuition because the one thing you learn very quickly with model building is that your intuitions that you start with are going to get beaten up so hard right? like the it's such an experimental science uh that the things that seem obvious you very quickly get to learn like you were wrong and hopefully you figure out why and sometimes you don't even Yeah. Um yeah

</details>

**Speaker A**: 所以你知道，你发布你的新模型时，Vivoo 非常兴奋。我的意思是，每个人都非常兴奋，但 Vivu 带领我们的论文俱乐部在上面做出了展示，你们当然看到了。也许可以讨论一下从中吸取的教训。无论你能透露多少……我们可以专注于模型工厂之类的东西， whatever you can sort of disclose.

<details>
<summary>Original English</summary>

**Speaker A**: so you know, one of the reasons that you uh you know when you released your new models, um Vivoo got really excited. I mean, everyone got really excited, but Vivu led our paper club on it and you guys saw it obviously. Um maybe talk through some lessons learned in that. Uh whatever you can sort of disclose.

</details>

**Speaker B**: 我们可以在模型工厂的东西上集中讨论，无论你认为什么是一个好的起点。所以我想说，我们公司从非常早期的观点就是模型构建最终是 90% 工程。而且我知道我们在行业里都知道这一点，因为如果你看看每个研究人员把时间花在哪里，他们都在写代码、看数据和写代码。所以我们当时就说，好吧，在三年前，那只是 Bash 脚本、Slurm 和训练以及数据管道的意大利面条式代码库。然后我们看了这个，然后我们说，嗯，最终模型构建是一个过程。你从原始数据开始，对吧？比如预训练原材料，网络等等。你正在做一整套过滤、清理、转换、分析。这些日子比三年前复杂得多。然后你正在训练一个模型，这本质上是一个跨硬件的大规模分布式系统问题，而且以前它仍然非常不稳定，而现在随着每一代新模型的出现，我们得到我们新的挑战集，然后你进入下一个阶段，那时没有中间的训练，但比如你进行后训练，然后是强化学习。所以我们看了这个，我们说，这看起来像一个工业化的过程，这看起来像一个端到端的流程，而它的每一个部分都有它的机械结构，对吧？如果它是你的大数据管道，如果是你抓取网络的爬虫，如果是你大规模分布式训练，那么你就有了可靠性。然后我们说，为什么不把世界上最聪明的分布式系统工程师中的一些人带进来，让他们从零开始参与研究过程，而不是事后补救，而是真的从一开始就做。这就是我们的模型工厂。所以我们的模型工厂始于少数几个组件。今天它有数千个组件，我试图把它等同于如果你想起来像福克斯康（Foxcon）的早期。如果他们当时在那里，在接下来的十年里，他们将能够重建 Foxcon，因为他们看到了导致构建那个系统的每一个决策和所有的复杂性。如果你和我今天走在 Foxcon 上，没有机会……

<details>
<summary>Original English</summary>

**Speaker B**: and so we kind of said, okay, the state at the moment, like 3 years ago, was bash scripts and slurm and spaghetti code bases for training and like data pipelines that were kind of patched together. And we kind of looked at this and said, well, ultimately model building is a process. You're going from raw data, right? Like pre-training raw material the web, etc. Uh you're doing a whole bunch of filtering, cleaning up, transformations, analyzing. these days that's you know far more complex than it was 3 years ago. uh then you're training a model which is effectively a large distributed systems problem right across hardware that has still it's become a lot more reliable was extremely flaky back then uh and now with every new generation we get our new sets of challenges and and then you go into the next stages right there was no mid-training back then but like you go you know you're post-training and then and then your reinforcement learning and so we kind of looked at this and we says well this looks like an industrialized process this looks like an endto-end process uh that every single part of it kind of has its machinery, right? If it's your big data pipelines, if it's your crawling ingestion of the web, if it's your you know large scale distributed training and then you've got your your reliability. And we said, well, why don't we take some of the world's smartest distributed systems engineers that we knew and make them part of the process of research from day zero, not retrofitting it later on, but like really from the beginning. And that became our model factory. And so our model factory started with a handful of components. Today it's thousands of components and I kind of try to equate it to if you think about like someone who was at the very early days of Foxcon. If they had been there for the following decade, they would be able to rebuild Foxcon because they saw every decision that led to building that system and all the complexity. If you and I walk on a Foxcon today, no chance

</details>

**Speaker A**: 对吧？因为我们没有导致那的决策和历史记录。所以我们从一开始就构建，带着一个真正理解这个指标——我们正在优化的目标是从研究人员的想法到我们可以信任并作为下一个模型训练的一部分的结果的速度。而且因为这是一种实验科学，最终在开始时，当它不那么复杂的时候，你可以……可以修补你的方法来绕过它，但现在，在任何基础模型公司你运营的，我的意思是，我们是一个小团队，我们少于 70 名研究人员，还有 35 名工程师，而且我们每月运行超过 10,000 次甚至可能是 10 到 20,000 次实验。所以如果你看看每一个模型运行的规模，最终你需要能够将其视为一个基础设施问题。而我们多年来所做的事情在这一点上变得非常好，只是通过工作、改进以及专注于那些端到端的决策，所以现在这意味着你研究了我们发布的 Laguna XS2，从预训练开始到发布模型花了 5 周时间；而我们今天讨论的模型从开始到预训练发布花了 8 周。我们昨天就开始训练下一个模型，因为我们现在已经完成了我们正在发布的模型的后训练，你知道吗？下周或者等这个出来的时候……然后我们将计算转移到我们现在正在训练的更大规模的 Laguna M 模型上。所以模型应该是一个过程的产物，它本身不应该是某件事，比如……就像你看着 SpaceX 的工厂一样，是的，第一个火箭建起来非常困难，但更困难的挑战是建造工厂，而现在他们正在推出，没有人再考虑下一次发射了。所以这只是又一次发射，又一次发射，又一艘火箭脱离轨道。这就是我们对模型构建所做的努力。

<details>
<summary>Original English</summary>

**Speaker A**: right? Because we don't have the lineage and history of decisions that led to that. And so we kind of built early on from the beginning uh with a team that really understood that well the metric that we are optimizing for is the speed of an idea from a researcher to an experimental result that we can trust to then being part of the next model training. and in the and because it's such an experimental science ultimately in the beginning when it wasn't that complex you could kind of patch your way around it right but now at any foundation model company you are running I mean we're small team right we're less than 70 researchers another 35 engineers uh and we're running well I haven't checked the latest count but far more than 10,000 maybe 10 to 20,000 experiments a month and so if you look at that scale of every model run that is like it's ultimately it's it's you need to be able to trust it as an infra problem and so what we have now done over the years has gotten really good at that and just by working it and improving it and obsessing over those kind of end-to-end decisions so now what that means is that you looked at Laguna XS2 that we launched it was 5 weeks from the beginning of pre-training to launch the model that we're going to talk about today was 8 weeks from start to pre-training uh to launch we started the next model literally yesterday because we now finished the post-training required for the model we're launching you know next week or by the time this comes out today uh and we move that compute to the much larger Laguna M model that we're now training and so the model should be an artifact of someone's process it shouldn't be really a thing in itself like and we kind of treat this like the way you would look at like a SpaceX factory where yes the first rocket really hard to build, but the much harder challenge was building the factory and now they're rolling off and no one is really thinking about the next launch anymore. So, it's just another launch, it's another launch, another rocket comes off. And that's what we're trying to do with model building.

</details>

**Speaker B**: 而从零开始，我们带着一个真正理解这个指标——我们正在优化的目标是从研究人员的想法到我们可以信任并作为下一个模型训练的一部分的结果的速度。而且因为这是一种实验科学，最终在开始时，当它不那么复杂的时候，你可以……可以修补你的方法来绕过它，但现在，在任何基础模型公司你运营的，我的意思是，我们是一个小团队，我们少于 70 名研究人员，还有 35 名工程师，而且我们每月运行超过 10,000 次甚至可能是 10 到 20,000 次实验。所以如果你看看每一个模型运行的规模，最终你需要能够将其视为一个基础设施问题。而我们多年来所做的事情在这一点上变得非常好，只是通过工作、改进以及专注于那些端到端的决策，所以现在这意味着你研究了我们发布的 Laguna XS2，从预训练开始到发布模型花了 5 周时间；而我们今天讨论的模型从开始到预训练发布花了 8 周。我们昨天就开始训练下一个模型，因为我们现在已经完成了我们正在发布的模型的后训练，你知道吗？下周或者等这个出来的时候……然后我们将计算转移到我们现在正在训练的更大规模的 Laguna M 模型上。所以模型应该是一个过程的产物，它本身不应该是某件事，比如……就像你看着 SpaceX 的工厂一样，是的，第一个火箭建起来非常困难，但更困难的挑战是建造工厂，而现在他们正在推出，没有人再考虑下一次发射了。所以这只是又一次发射，又一次发射，又一艘火箭脱离轨道。这就是我们对模型构建所做的努力。

<!-- chunk 4/15 -->

### 关于模型工厂和数据流的讨论

**Speaker A**: 谈到我们的模型，我真正想谈论的是模型工厂，而我最酷的例子就是每次我们启动一个新的运行，无论它是一个预训练的大规模运行，还是一个后训练版本中的一个（比如为发布或许多实验做的那种），在任何给定时刻，有人在那天之前做出的、他们有实验结果的更改都会将其变成那个运行。所以，不是像 90 天前就截止了，或者根本没有，而是从那一刻起就可以信任机器了，然后你还需要投资于可靠性。

<details>
<summary>Original English</summary>

**Speaker A**: look like. Uh and that's frankly so when we talk about like to your question about our models I really talk about the model factory and my coolest example of these things is always that when we kick off a new run doesn't matter if it's a pre-training like big run or if it's now a post like one of 10 post-training versions we do for like pre-release or many experiments is that at any given moment the changes that somebody made that they had experimental results on from the day before make it into that run. So there's not like a cut off 90 days before or like no it's like literally from that moment because we can now trust the machine enough and then you also have to invest in a reliability.
</details>

**Speaker A**: 我最喜欢的关于 Laguna S 的一个指标是，完全没有在线事件，就像零。而且到我记得的整个年度，我们还没有发生有意义的在线事件。现在有一个星号是，通常在启动新模型运行的前 6 小时，有些东西会崩溃，因为你设置了错误的配置，你犯了一个小错误等等。所以通常会有一些干预，但那总是在在线期间，而不是非在线期间，而且我认为这正在开始累积。所以我们现在发布的模型我喜欢它，它很棒，但我们已经进入下一个了。我认为这就是应该有的方式。

<details>
<summary>Original English</summary>

**Speaker A**: So one of my favorite metrics about like Laguna S is that there was no on call events right like completely zero and actually we haven't had a meaningful on call event like to wake up for as far as I recall this entire year. Uh now there is one asterisk to that in usually the first 6 hours of launching a new model run something breaks because you set a config wrong you made a small mistake etc. So that's usually there's a little bit of intervention but that's always within like in call periods right not not on call and and I think that's starting to now compound. So the model we're releasing now I love it it's amazing but we're already on to the next one. Uh and I think that's the way it should be.
</details>

**Speaker B**: 我们现在发布的模型我喜欢它，它很棒，但我们已经进入下一个了。我认为这就是应该有的方式。我想指出这一点，为了背景，这大约是一个月前。嗯，我们在技术报告中找到了它。所以我们只是带着“新的模型发布了”就来了。我们没有听说过做这个的。

<details>
<summary>Original English</summary>

**Speaker B**: Uh and I think that's the way it should be. I think I also just want to point out, so for context, this was like a month ago. Um, we found it actually in the tech report. So, we just came in with, okay, new models dropped. Haven't heard about it for doing this.
</details>

**Speaker A**: 我们非常像，啊，好的，你看，你知道的，和 Kimmy、Deepseek 等小模型一样。Gemma 级别。哦，那是一篇关于构建内容的非常酷的论文。然后我们遇到了这个页面，对吧？技术报告的字面上的第二页是呃这个过程允许我们从头构建小型模型到在 5 周内交付，应用了这些经验教训。然后我就是说，哦，这篇论文不是关于这里的技术报告、基准测试和训练了多少个 token 的，对于那些想深入了解我们将在播客上讨论的那些人来说。它都安排在这里了，对吧？从可以与训练代码、预训练数据接口的小型模型到自定义软件。

<details>
<summary>Original English</summary>

**Speaker A**: >> We're very much like, ah, okay, look, it's like, you know, on par with Kimmy, Deepseek, whatnot, the small ones, Gemma level. Oh, it's a very cool paper on what goes into building. And then we hit this page, right? Like literally page two of tech report is uh this process allowed us to build the small model from scratch to delivery within 5 weeks applying the lessons and then I'm like oh this paper is not about here's a tech report of benchmarks and here's how many tokens it was trained on like for people that want to dive more from what we're not going to discuss on the podcast. It's all laid out here, right? From custom software that agents can use to interface with training code, pre-training data.
</details>

**Speaker B**: 是的。论文是这样。是的。是的。所有那些东西。你知道，在这里读论文。但是……但我我喜欢原则。我认为那是讲述一些故事的一个很好的起点。也许我们可以一个一个地通过原则来走。我会指出 Dexter，它被 Prefect 买走了。是的，这有点有趣。但是的，我实际上非常熟悉 Dexter。呃，任何触发某种故事的东西。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. The paper clock. >> Yeah. Yeah. All that stuff. You know, read the paper here. But um but I I I would like I I love principles. I think that is a good starting off point for maybe telling some stories. Maybe we can go one by one past the principles. I'll just call out the Dexter just called bought by Prefect. Yeah, it's a kind of fun. But yes, I'm actually very familiar with Dexter. uh just anything where like they trigger some kind of story.
</details>

**Speaker A**: 所以，嗯，我会说……实验代码是显而易见的，但我认为我最喜欢的事情是……不知道它在这里在哪里，但早期，而且我仍然认为这实际上是很多基础模型公司的人准备他们的训练数据集，他们把它们打包，然后将它们复制到分布在所有节点上的训练集群中，然后训练就开始了。我们三年前看了这个，我们觉得这没意义。因为你必须重新制作一个数据集的时刻，你必须做更改，你必须修复一些东西等等。你有了这么长时间来重新打包它，对吧？分词、重新打包、移动到集群上，然后分布到节点上。你的集群越大，你就开始使用花哨的像 torrent 这样的算法来分配你的数据。所以为什么我们不将数据流式传输到训练中呢？这在基本……

<details>
<summary>Original English</summary>

**Speaker A**: >> So well I would say um well experiments code is obvious but I think one of my favorite things is uh I don't know where it is in here but early on uh and I still think this is the case actually a lot of foundation model companies people prepare their training data sets they get packaged up then they get copied over to a training cluster distributed across all of the nodes and then training starts. Uh and we looked at this like 3 years ago and we were like that makes no sense. You lose so much time because the moment you have to rematerialize a data set, you have to make a change, you have to fix something, etc. You've got all this time of like repackaging it, right? Tok tokenizing it, repacking it, moving it over to a cluster, then distributing it across the nodes. The bigger your clusters are, you start using fancy like torrent like algorithms to like distribute your data. So why aren't we streaming data into training, right? something that's very common in like just basic
</details>

**Speaker B**: 只是在时间上。只是在时间上，就像良好的计算机科学原则一样。那是我认为解锁模型工厂的第一件事之一，因为一旦你开始思考训练作业，无论它是一个大运行还是一个小的后训练实验消耗每秒的某些 token，而且从数据移动的角度来看，这实际上不是很多，所以我们说，嗯，我们有我们的训练集群。现在我们有了像 AWS 那样的设置，我们可以构建这些惊人的大数据管道。我们可以设置一些东西。我们在底层使用 Spark 来运行所有这些东西。

<details>
<summary>Original English</summary>

**Speaker B**: >> just in time >> just in time like good computer science like principle and that was one of the first things that I think unlocked are the model factory because the moment you start thinking about well a training job doesn't matter if it's a big hero run or small like you know post-training experiment consumes a certain number of tokens per per second right and it's actually not a lot right from a like a data moving data perspective so we said well we have our training cluster And now we've got like our AWS kind of setup where we can build these amazing big data pipelines. We can set things up. We use Spark underneath the hood like all these things.
</details>

**Speaker A**: 但当你提到 AWS 时，它不是真正的 AWS。它是内部的。是我们的内部。就像运行我们内部服务在 AWS 账户或任何硬件上一样。所以一旦我们做出了那个转变，我可以将数据流式传输到训练中，你就会意识到很多事情被解锁了，因为现在你不需要等待整个数据集物化。M 你现在所有的数据实验，关于混合数据的，它是一个配置问题，因为你有了这些进来的数据源，而我们只是有一个叫做 blender 的服务，它在报告里，然后我们说，“好的，对于这次运行，我想要这个来源的 20%，这个来源的 10%，我想要这么多周期，我想要这以某种方式打乱，而你的训练作业可以开始，而其余的数据仍在物化中”。此外，它的作用是……因为所有这些都在下面。所以对我们来说，我们将底层的​​数据层视为像一个不可变的​​数据层。而且这对实验来说非常重要，代码不可变的数据意味着你总可以回去理解它，一直深入到光标在哪个版本代码上停留的单个 token。

<details>
<summary>Original English</summary>

**Speaker A**: Uh and so once we made that shift into I can stream data into training all of a sudden you realize a lot of things unlock because now you don't have to wait for the whole data set to materialize. M you now all of a sudden when you're running data experiments about mixing data it's a config because you've got these data sources that are coming in and you just we have the service called blender that's in the report where we then say okay for this run I want 20% of this source 10% of this source I want this much so many epochs of repetition I want this to be you know uh shuffled in a certain way and your training job can start while the rest of the data is even still materializing uh also what it does is because all of this underneath. So for us, we treated the data layer underneath as like an immutable data layer. And that was really important like experiments as code immutable data later means that you can always go back and understand literally down to the single token at which cursor it went in on which version of the code.
</details>

**Speaker B**: 是的。这花了我们一年的时间才明白，工程必须变得更棒，但我们还没有理解这是最终为了良好的严格科学进步。我们人数很少，我们是一个非常小的群体，所以很多是 YOLO 想法和 YOLO 运行。但是一旦我们意识到我们将数据视为不可变，代码视为始终版本，并且你可以完美地跟踪和追踪每一个实验从头到尾，你就可以完美地重复一切，对吧？你有完美的复现性。如果我想的话，我仍然可以重现两年前的运行，对吧？这实际上促进了科学进步，就像科学过程一样。我们可能花了公司大约一年半的时间才弄清楚这一点。

<details>
<summary>Original English</summary>

**Speaker B**: >> yeah. and it took us a I have to admit like the first year of poolside we understood that engineering had to get great but we didn't understand yet uh that this is ultimately in support of like a good rigorous scientific progress. We were quite a few we were a very small number of people so a lot of it was yolo ideas and yolo runs. But once we realized that we treated data as immutable and code as always version and you could always track and trace every experiment end to end perfectly, you could repeat everything perfectly, right? You had perfect reproducibility. I can still reproduce runs from 2 years ago if I wanted to, right? It actually enables the scientific progress like the scientific process. And I think that took us probably about a year, year and a half into the company to figure out.
</details>

**Speaker A**: 我们还雇佣了一些很棒的人才，比如我们的应用研究联合负责人 Nikolai，他从 Yandex 加入我们，他在 2020 年代初就开始从事语言模型工作。我认为他把那种……嘿，我们想有更多的严谨性带到公司。然后一旦我们有了越来越强大的平台，允许人们做更多事情，但又具有这种不可变性，我们就能够开始真正地认为每一个实验都是一次消融。我们需要理解它，而且我认为在过去的几年里，我们变得更加科学严谨了，而底层的基础设施促成了这一点。

<details>
<summary>Original English</summary>

**Speaker A**: We also had some great hires like our co-head of applied research, Nikolai who joined us from Yandex who've been working on language models since like the early 2020s I think brought that into the company of like hey we want to have even more rigor and then once we kind of had the combination of like increasingly more capable platform that allowed people to do more but had this immutability, we were able to start actually okay every experiment is truly an ablation. we truly need to understand it and and I think we became much more scientifically rigorous in the last couple of years and the infra underneath enabled it.
</details>

**Speaker B**: 嗯，还有一些有趣的东西。比如你分享所有消融的实验，选择数据集时，这里有一个随机的小小段落，只是说，哦，是的，预训练数据我们有一些……我们有一个自动混合器，你知道它训练八个小型模型，将它们放大，选择预训练数据集，我们甚至不需要查看它。我就是说，哇，有很多工程的活力在那里。而且你知道，有很多……

<details>
<summary>Original English</summary>

**Speaker B**: >> yeah a lot of it's fun like even just the one you share all the ablations two picking the data sets right there's like a random small small paragraph in here where it's just like oh yeah pre-training data we have some um we have an automixer you know it trains eight small models scales them up picks the pre-training data set we don't even need to look at it I'm like wow a lot of engineering vigor there and there's just you know there's just a lot
</details>

**Speaker A**: 是的。而且我们想发布更多东西，实际上我们一直认为写论文还没有赚到应得的权利。长期以来。所以一旦你处于前沿，你就赚到了花费时间进行研究并发表成果的权利，因为在那之前你还在追赶，而这个行业中的每一分钟和每一小时都很重要。我痴迷于不仅仅是想法到结果的钟表时间，而是每天我们浪费的时间，是你不知道它不允许……

<details>
<summary>Original English</summary>

**Speaker A**: >> yeah and look and we want to put out more like actually we we treat writing papers as something that we haven't earned the right for yet for a long time. So you earn the right to spend time, you know, publishing research once you're at the frontier because until then you're catching up and every minute and hour in this industry matters. Like I I obsess over not just a wall clock time from idea to result, but just general like time every day that we you know waste is is one that doesn't allow
</details>

<!-- chunk 5/15 -->

### 追赶进度与生态建设

**Speaker A**: 我们需要追赶进度。但在这个案例中，我们说：“好的，我们会给团队三四天时间来完成他们的工作，把所有东西都交出来。”对于你之前提出的观点，如果你了解你的东西，很容易把它弄出来。所以我们有很多更多的事情需要随着时间的推移去讨论，而且我们肯定会开始做这些事情。

<details>
<summary>Original English</summary>

us to catch up. But in this case, we said, "Okay, we're going to give ourselves I think we gave the team like three or four days while still doing their work. Like give everything in there." And to your point earlier, if you know your stuff, it's easy to like put it out. And so there's so many more things that we want to talk about over time and we will definitely start doing.
</details>

**Speaker A**: 随着我们赢得更多权利，同时我们的使命也增加了希望更多的基础模型公司能够存在，你会看到我们变得更加积极主动，只是在不断地尝试分享我们沿途学到的那些可以帮助他人加速的东西。

<details>
<summary>Original English</summary>

And as we earn more of the right, but also now have like added to our mission that we want more foundation model companies to exist, you'll see us like be way more proactive uh and just trying to keep dropping some of those like things that we've learned along the way that can help others like speed up,
</details>

**Speaker A**: 这就是这个的另一个很酷的一面，对吧？这并不是回到你之前说的观点，它不仅仅是我们的训练基准。如果你想复制优化器、数据集、后训练等实验，你会把很多东西列在这里，和如何做你的系统放在一起，你知道吗？所以它实际上是在促进其他人的能力。

<details>
<summary>Original English</summary>

>> which is the other cool side of this, right? It's not like back to your point, it's not just here's the benchmarks of our training. If you want to replicate here's experiments of optimizers, data sets, post training, uh, you lay out a lot of it here alongside here's your system for how to do it, you know. So it's it's really like promoting >> other people can do the same.
</details>

**Speaker A**: 顺便说一下，我还要明确一点，我们一直以来都非常受益于别人已经发表的所有开源研究的事实，对吧？你提到过，你知道，中国实验室和我们，我认为重要的是，来自每个国家、每个文化和背景，包括像我们这样的西方公司，都有不同的模型可以供人们选择信任。但我认为我们必须在应得的时候给予认可，对吧？那那个出色的中国实验室在分享他们的研究方面做得非常出色，而我们绝对一直在利用这一点。所以当你处于接收方时，我认为你也有一种回报的义务。你有没有一个你最喜欢或被低估的中国学者想点名表扬的人？

<details>
<summary>Original English</summary>

>> And by the way, I also want to make clear right we have been incredible like we've taken a lot of advantage of the fact of all the open research that others have published, right? and and and you mentioned, you know, that the Chinese labs and we I think it's important that there's, you know, from every country and every culture and background, including like Western companies like us, there's different models that come out that people can choose to trust. But I think we do have to give credit where credit's due, right? The incredible Chinese lab has done an amazing job at sharing their research and we have definitely take like been on the receiving end of taking advantage of that. So when you're on the receiving end of something coming to you, I think it's you also have kind of an obligation to give back. Do you have a favorite or underrated Chinese lad that you want to shout out?
</details>

**Speaker B**: 每个人都点名表扬 DeepC。

<details>
<summary>Original English</summary>

Everyone shout out DeepC.
</details>

**Speaker A**: 那是个好问题。Mulan 当然是，对吧？

<details>
<summary>Original English</summary>

>> That's a good question. Mulan obviously for
</details>

**Speaker B**: 是的。是的。听着，我认为我记得大家最近都在谈论 Zeu 和 GLM 5.2。我想大多数人没有意识到的是他们开始的时候。

<details>
<summary>Original English</summary>

>> Yeah. >> Right. They started years before Chachi BT. It was just rebranded >> and uh and and so I have like >> I remember how hard it was to work on these things >> before the rest of the world got excited about it. And so I have an immense amount of respect for people uh uh who were working on improving models when it wasn't the sexy thing to do when believing in LLMs, you know, was was going to get you ridiculed.
</details>

**Speaker B**: 我记得 2016 年的时候，当我们用这些模型做我们所谓的代码机器学习时，人们会坦率地嘲笑我们，比如“这没道理。为什么你们要花这么多钱去试图弄清楚这个问题？”我可以说他们可能就是那个值得点名的，不只是因为他们最新的模型非常好，而是因为他们为了走到这里而奋斗了。

<details>
<summary>Original English</summary>

I remember like back in 2016 when we were doing what we'd call, you know, machine learning on code with with some of these models, you know, we would people would just frankly laugh at us like to be like, you this makes no sense. Like why are you wasting all these like millions of dollars on trying to figure this out? And uh and so I would say they're probably the one that uh I think deserves the shout out, not just because their latest model is very good, uh but because they they fought to get here.
</details>

**Speaker B**: 我认为每一个基础模型公司都要花时间才能走到这一步，对吧？我们花了三年才达到我们现在要发布的那个模型的。而现在模型之间的间隔是按周计算的。它不再按月或年计算了。但这些东西很艰难。如果我们能让下一个人的事情变得稍微容易一点，我们就应该都这么做，因为如果我们不这样做，在模型真正开始影响递归自我改进到需要追赶否则可能变得不可行的水平之前，我们有一个小窗口期，我们应该在这个窗口期鼓励尽可能多的新实验室或我们想称之为什么的机构开始。所以这是我目前的一种使命之一，但质量是，我希望鼓励任何现在认为自己可以解决这个问题的人去走出去，成为我的竞争对手，比如开始另一个基础模型，因为我认为我们需要它。否则我们不会在这样一个世界中存在，在那里我不希望只是第五或第六家公司获胜。我希望看到一个有很多选择的世界。

<details>
<summary>Original English</summary>

And I think I think every foundation model company you takes time to get here, right? It took us three years to get to the model that we're that we're now going to be releasing. And now the the time in between the models is coming is counted in weeks. It's no longer counted in months or years. But this stuff's hard. Uh, and if we can make it a little bit easier for the next person, like we should all do so because if we don't do so, we're we've got a small window before models are really impacting recursive self-improvement to a level where catching up otherwise might become unfeasible and we should try to in that window encourage as many neolabs or whatever we want to call them like to start. And so one of my kind of current mi uh mission but quality is I want to encourage whoever is a researcher right now who thinks they can actually tackle this to go and leave and become my competitor like start another foundation welcome because I think we need it u I think otherwise we're not going to be in the world where uh I don't want to just be the fifth or the sixth company that wins. I want to look at a world where there's lots of choice.
</details>

**Speaker A**: 别人在开始一个基础模型时看不到什么？你知道，计算量很大，需要大量的资本，需要大量的计算资源来搭建工厂并进行训练。但有很多东西在那里，对吧？那是一个……

<details>
<summary>Original English</summary>

>> What else do people not see in starting a foundation model? you know it's there's a lot of comput there's a lot of capital required a lot of compute you lay out moto factory and how to do the training but there's a lot there right that's a
</details>

**Speaker B**: 嗯，看吧，这是一种过度简化。我总是用星号来标记它，因为它可能会在人们的脑海中产生一点偏差，但我实际上认为你可以把模型构建的 95% 都简化为做两件事：你改进数据，或者你提高计算效率。我知道这对那些非常出色和有技能的人来说可能感觉像是一种过度简化。但如果你真的看看我们正在做什么？我们正在看数据。我们正在生成新数据。我们正在改进数据。而要做到这一点，唯一的办法就是查看数据，对吧？这是基础模型构建的很大一部分。另一方面，我们又在推理、架构、新的注意力机制方面取得了这些不可思议的突破。但它们到底在做什么呢？它们带来了计算效率。多年来我们确实有一些突破，允许更多的模型能力，但在极限上，如果你能训练一个足够大的模型，比如你有无限的计算能力，我们可能如果拥有无限的计算能力，明天可能就是 AGI 了，对吧？它不是这样。所以……

<details>
<summary>Original English</summary>

>> well look it's uh I I in turn this is an oversimplification and I and I I always asterisk it with that because it can land a little bit the wrong way in in people's minds but I actually think you can sum down and I sum up 95% of model building to just doing you're just doing two things you're improving data or you're improving compute efficiency and I know kind of feels like an oversimplification for the incredible like gifted and skilled work people do. But if you really look at it like what are we doing? We are looking at data. We're generating new data. We're improving data. Uh and the only way to do that is to look at the data, right? That's a big part of foundation model building. And on the other hand, we come up with these incredible breakthroughs in inference, in architecture, new attention mechanisms. But what are they really doing? They're bringing compute efficiency. Now we have definitely had some breakthroughs over the years that that allow for more model capabilities but at the limit if you could train a large enough model right like you had infinite compute we probably if you had infinite comput you'd be at AGI probably already tomorrow right like it's not and so uh and let me say that infinite compute with infinite ability of much faster networking because networking and so being more of the bottleneck than than compute but uh so I do think that that's those are the main things and to just realize that this is engineering. I think it's become more obvious. But I think for quite a few years, people have held foundation model companies and researchers and others on this pedestal of like you're doing credible magic or rocket science or only like you know Nobel laureate physicists can do this. And don't get me wrong, there are some really hard problems that need to be solved. But a lot of the work that all of us are doing on a day-to-day is not sitting down trying to solve a math theorem. A lot of the work that we're doing is just really doing the basics, right? Writing good code, looking at data, improving it, running experiments, looking at plots, trying to see like, hey, trying to shape our intuitions. And a lot more people could be highly capable researchers. Uh, and I think that's it. It it feels it feels far for people to do so. I've seen in our own company, we've seen engineers become researchers because the model factory allowed them to be have a much lower hurdle of running experiments and trying things. And one of the guys on our team who started as an engineer building our our agents is a legit reinforcement learning researcher now making real progress. Uh and that happened in the span of like 6 months. Um that would have not been what I think most people assumed was possible, you know, a couple of years ago.
</details>

**Speaker B**: 是的。我想一个有趣的时候是当你可以……你知道，比如对于编程语言，如果你能编译该语言，那么等效的是你能使用你自己的工具，对吧？你有你的命令行界面（CLI），你有你自己的模型……我们推测你不仅仅在使用你自己的模型，但没有办法……你知道那百分比会随着时间的推移如何变化。

<details>
<summary>Original English</summary>

Um that would have not been what I think most people assumed was possible, you know, a couple of years ago. Yeah. Um I think one of the interesting moments is when you can sort of um self-host like you know for a programming language like if you can compile the language in the in the language the equivalent is can you use your own tools right you have the pool CLI you have your own models um presumably you're not only using your own models there's no way but like um you know what's that percentage over time
</details>

**Speaker B**: 这是我们发布的第一款模型，它开始对我们自己的工作做出有意义的贡献。它不是一个最先进的模型。Fable 确实有一些非常强大的模型，但 Laguna S 非常有趣。我将把那段引语拉出来。我们的应用研究联合负责人之一 Penging 上周说了一些东西，在那个模型发布大约十天前，比我们预期的要好得多。他说他有种感觉，很多……

<details>
<summary>Original English</summary>

>> this is the first model that we're releasing that is starting to meaningfully contribute to our own work. It's not a it's not state-of-the-art model yet. Fable and there are very capable models, but Laguna S is really interesting. I'm going to actually pull up the quote. Penging, one of our co-heads of applied research uh said something uh last week as the as the model came out about 10 days ago, much better than frankly we had hoped for expected. and he said, uh, I have the feeling that a lot of the
</details>

<!-- chunk 6/15 -->

### 模型的持续性与规模的权衡

**Speaker A**: gains in intelligence, but more from different behavior, more verification, less taking things for granted, not declaring victory early, and being way more persistent. And to be honest, those are more predictive than raw intelligence for success and human also to some degree. And this was he wrote me this on 5th of July on a Sunday and it's kind of been burned in my brain ever since because the Luna S model as you'll see it and why it does so well in benchmarks and why it does so well in using it on a day-to-day basis is that it's just incredibly persistent. It reasons a lot. I do call that out. We have work to do on making it more efficient. We have to do work to do on offering different reasoning modes. But this is the model that has been able to do things that I never thought it could do. 118 billion 8B active model, which is not that large. It fits on a DGX Spark and still runs at, you know, 30 40 tokens a second on a Spark. Is able to solve Erdos 397 independently. It's able to do complex programming tasks. It's able to I asked it this morning to make me a Wi-Fi scanner without using any external libraries on my Mac. And it's like figuring out like the core WLAN API by really persistently trying to understand it without access to the internet. And more and more I love checking. I've probably spent 8 to 10 hours a day with this model for the last 10 days. I'm not exaggerating. I was on my 11-hour flight yesterday. I spent 10 hours reading trajectories and traces and like of the model.

<details>
<summary>Original English</summary>

Speaker A: gains in intelligence, but more from different behavior, more verification, less taking things for granted, not declaring victory early, and being way more persistent. And to be honest, those are more predictive than raw intelligence for success and human also to some degree. And this was he wrote me this on 5th of July on a Sunday and it's kind of been burned in my brain ever since because the Luna S model as you'll see it it and why it does so well in benchmarks and why it does so well in using it on a day-to-day basis is that it's just incredibly persistent. It reasons a lot. I do call that out. We have work to do on making it more efficient. We have to do work to do on offering different reasoning modes. But this is the model that has been able to do things that I never thought it could do. 118 billion 8B active model, which is not that large. It fits on a DGX Spark and still runs at, you know, 30 40 tokens a second on a Spark. Is able to solve Erdos 397 independently. It's able to do complex programming tasks. It's able to I asked it this morning to make me a Wi-Fi scanner without using any external libraries on my Mac. And it's like figuring out like the core WLAN API by really persistently trying to understand it without access to the internet. And more and more I love checking. I've probably spent 8 to 10 hours a day with this model for the last 10 days. I'm not exaggerating. I was on my 11-hour flight yesterday. I spent 10 hours reading trajectories and traces and like of the model.

</details>

**Speaker A**: And what I take away from it is exactly what Ping said. we are going to be able to squeeze so much more out of smaller models than I think we had imagined in the industry because yes there's intelligence and larger models are more intelligent like no doubt about it we should continue to scale up uh but the behaviors of being really persistent of being able to backtrack when you're wrong of like understanding how to interact with your environment show us that we can get a lot more out of it and this for me has created a bit of uh question in my mind the last couple of days. If you think about where we're using models today, right? We are using models say for knowledge work represents 25% of the global economy, you know, $25 trillion of work. As we scale up models and they become more intelligent, we are excited about using them more and more for pushing the frontier of science. And if you look at the frontier of science like true breakthroughs in science, they have been linked, they are linked to more intelligence in many places. Einstein figuring out general relativity is able to bring ideas together that other people would have not brought together. And I think one of the many dimensions of intelligence is the ability to do that. And it's something we clearly see that as models get larger and more capable, they're able to pull more ideas and threads together that a smaller model wouldn't be able to.

<details>
<summary>Original English</summary>

Speaker A: And what I take away from it is exactly what Ping said. we are going to be able to squeeze so much more out of smaller models than I think we had imagined in the industry because yes there's intelligence and larger models are more intelligent like no doubt about it we should continue to scale up uh but the behaviors of being really persistent of being able to backtrack when you're wrong of like understanding how to interact with your environment show us that we can get a lot more out of it and this for me has created a bit of uh question in my mind the last couple of days. If you think about where we're using models today, right? We are using models say for knowledge work represents 25% of the global economy, you know, $25 trillion of work. As we scale up models and they become more intelligent, we are excited about using them more and more for pushing the frontier of science. And if you look at the frontier of science like true breakthroughs in science, they have been linked, they are linked to more intelligence in many places. Einstein figuring out general relativity is able to bring ideas together that other people would have not brought together. And I think one of the many dimensions of intelligence is the ability to do that. And it's something we clearly see that as models get larger and more capable, they're able to pull more ideas and threads together that a smaller model wouldn't be able to.

</details>

**Speaker A**: And we're starting to see examples of that in medicine and like in bio and other things. But if you think about the majority of knowledge work that we do and it includes building software, I'm a software developer at heart first and foremost probably. Uh although I probably can't say it that much anymore. I don't write production coding years. Uh is that what makes us good is actually our persistence. It's our ability to encounter a problem and backtrack and say I need to go figure out this bug. I need to go research this. I need to go look at the documentation. I need to like try different five different ways to see like if I can solve it. But it is not necessarily bringing three ideas together from radically different fields. And so if we are now seeing and I think Laguna S is an example that we are able to make a relatively small model much more capable than I had definitely predicted or any previous like benchmarks had shown for any model remotely this size or even larger uh at least on coding tasks that it's because of the behaviors and so now the question I have and I don't have it answered is I know at the limit so infinite model size right extremely large model and the cost of that model is going to be very expensive to run. We know this, right? So larger model ROI. Uh so I know that at the very limit I'm not going to use the world's largest model one day quadrillion parameter whatever crazy like skill we scale up to do a basic coding task. Already today I'm starting to size down for certain tasks. So it means that there is an optimal. It means there's some curve that goes as we go up the model size for knowledge work at some point we're at the peak and after that the return on investment of using a bigger model uh just doesn't make sense.

<details>
<summary>Original English</summary>

Speaker A: And we're starting to see examples of that in medicine and like in bio and other things. But if you think about the majority of knowledge work that we do and it includes building software, I'm a software developer at heart first and foremost probably. Uh although I probably can't say it that much anymore. I don't write production coding years. Uh is that what makes us good is actually our persistence. It's our ability to encounter a problem and backtrack and say I need to go figure out this bug. I need to go research this. I need to go look at the documentation. I need to like try different five different ways to see like if I can solve it. But it is not necessarily bringing three ideas together from radically different fields. And so if we are now seeing and I think Laguna S is an example that we are able to make a relatively small model much more capable than I had definitely predicted or any previous like benchmarks had shown for any model remotely this size or even larger uh at least on coding tasks that it's because of the behaviors and so now the question I have and I don't have it answered is I know at the limit so infinite model size right extremely large model and the cost of that model is going to be very expensive to run. We know this, right? So larger model ROI. Uh so I know that at the very limit I'm not going to use the world's largest model one day quadrillion parameter whatever crazy like skill we scale up to do a basic coding task. Already today I'm starting to size down for certain tasks. So it means that there is an optimal. It means there's some curve that goes as we go up the model size for knowledge work at some point we're at the peak and after that the return on investment of using a bigger model uh just doesn't make sense.

</details>

**Speaker A**: Now I think the question is before I would have thought that peak was really very far away. This model for me is the first sign that maybe that peak is at trillion, five trillion, 10 trillion. Maybe we can squeeze way more out of these models. I'm no longer thinking that we need two or three orders of magnitude on the largest models to be able to, you know, solve knowledge work uh the accounting, the legal, the code that we write. And so if if that holds true, it is an argument for the commoditization of models. It's an argument that open-source can win and like succeed in this world. And now it's of course a self-serving argument and it's a hopeful argument. But theoretically at the limit it works. We just have to go discover in the next couple of years of how much more we can squeeze out. Now I do want to put a big asterisk. This does not mean I'm against scaling models. I think we ultimately only succeed if we scale our models as large as our competition. I do not like I think we should not put our head in the sand and say we're going to be king of open-source small models. I think that's frankly it's a copout. It's trying to be king of your own kingdom but not realizing what the rest of the world's doing. All of us rather use a smarter, faster, you know, more model. But it's kind of a sign of hope. And so I don't want to overly state this is a good model. We have a long way to go to get to the state-of-the-art. But what hopefully people take away when they use this model is that the behaviors inside of it are what push it to be far more capable less than necessarily the number of parameters.

<details>
<summary>Original English</summary>

Speaker A: Now I think the question is before I would have thought that peak was really very far away. This model for me is the first sign that maybe that peak is at trillion, five trillion, 10 trillion. Maybe we can squeeze way more out of these models. I'm no longer thinking that we need two or three orders of magnitude on the largest models to be able to, you know, solve knowledge work uh the accounting, the legal, the code that we write. And so if if that holds true, it is an argument for the commoditization of models. It's an argument that open-source can win and like succeed in this world. And now it's of course a self-serving argument and it's a hopeful argument. But theoretically at the limit it works. We just have to go discover in the next couple of years of how much more we can squeeze out. Now I do want to put a big asterisk. This does not mean I'm against scaling models. I think we ultimately only succeed if we scale our models as large as our competition. I do not like I think we should not put our head in the sand and say we're going to be king of open-source small models. I think that's frankly it's a copout. It's trying to be king of your own kingdom but not realizing what the rest of the world's doing. All of us rather use a smarter, faster, you know, more model. But it's kind of a sign of hope. And so I don't want to overly state this is a good model. We have a long way to go to get to the state-of-the-art. But what hopefully people take away when they use this model is that the behaviors inside of it are what push it to be far more capable less than necessarily the number of parameters.

</details>

**Speaker A**: Is that mostly post-training? Like right. So it's entirely post-training. Are we done improving anything on pre-training? Is like pre-training done? No. Okay. Uh so I just wanted to cover pre-training and then we go post training. Pre-training is not done. Uh I mean look there's a part of pre-training of just dealing with skill right every new order of magnitude of model skill you are going to get new things you got to solve for that's those are ultimately you know engineering challenges uh I have a I would say a not commonly held opinion that reinforcement learning will move earlier and earlier into pre-training yeah is mid-training not even mid-training like like mid training today right is uh like if you look at um so we've been working on this for years already uh and I think the best I think the first time we saw it out in public was the deepseek zero paper uh this is a year and a half ago I think if I recall correctly um where you know you can very early on in a model as it starts capable of being able to use language etc induce reasoning uh and so the question that I kind of have is like we have this we have the data set that's the web uh and the web I think we can arguably say probably has the totality of humanity's knowledge somewhere encoded in different places. It's a huge variance degree of quality from garbage data and like once you look at pre-training data you really get humbled of like what the web is to like you know the most greatest scientific papers and best blog posts and like you know best transcripts and whatnot and so now what we are trying to figure out and have been doing a lot of work on and it's a place where maybe not as open as we're on other things but we will become more over time. uh we've been spending a couple of years really doing research

<details>
<summary>Original English</summary>

Speaker A: Is that mostly post-training? Like right. So it's entirely post-training. Are we done improving anything on pre-training? Is like pre-training done? No. Okay. Uh so I just wanted to cover pre-training and then we go post training. Pre-training is not done. Uh I mean look there's a part of pre-training of just dealing with skill right every new order of magnitude of model skill you are going to get new things you got to solve for that's those are ultimately you know engineering challenges uh I have a I would say a not commonly held opinion that reinforcement learning will move earlier and earlier into pre-training yeah is mid-training not even mid-training like like mid training today right is uh like if you look at um so we've been working on this for years already uh and I think the best I think the first time we saw it out in public was the deepseek zero paper uh this is a year and a half ago I think if I recall correctly um where you know you can very early on in a model as it starts capable of being able to use language etc induce reasoning uh and so the question that I kind of have is like we have this we have the data set that's the web uh and the web I think we can arguably say probably has the totality of humanity's knowledge somewhere encoded in different places. It's a huge variance degree of quality from garbage data and like once you look at pre-training data you really get humbled of like what the web is to like you know the most greatest scientific papers and best blog posts and like you know best transcripts and whatnot and so now what we are trying to figure out and have been doing a lot of work on and it's a place where maybe not as open as we're on other things but we will become more over time. uh we've been spending a couple of years really doing research

</details>

<!-- chunk 7/15 -->

### 如何将网络转化为模型训练中的思考方式

**Speaker A**: 我们如何才能把网络变成不仅仅是下一个词的预测，而是教会模型在训练早期就进行思考的一种方式呢？我认为那里有大量的金矿可以挖掘。我们现在正处于一个……你知道，我们在行业中有一些药物。其中一种药物是蒸馏。另一种药物是，你知道，更多的环境，它们很棒，它们让我们感觉良好，让模型变得更好，就像我们都对它们上瘾了，我们会用它们，对吧？在各种不同的方式中。但最终，我认为我们仍然只是勉强从网络中榨取着我们应该从中获取的东西。

<details>
<summary>Original English</summary>

**Speaker A**: how can we turn the web into not just next token prediction but into a way to teach the model to think earlier in its training. uh and and i think there's a huge amount of gold to be found there. uh i think we are right now in you know we've got some drugs in the industry. one of the drugs is distillation. another drug is, you know, more environments like and they're great and they make us feel good and they make the models better and like we're all addicted to them and we'll use them, right? uh in in various different ways. uh and but ultimately i think we are still barely squeezing out of the web what we should be getting out of the web.

</details>

**Speaker B**: 我认为仅仅是下一个词的预测预训练是不够的。所以我认为我们还会看到一些非常有趣的事情发生。还有，在后训练中进行强化学习来诱导行为以改进某些方面，比如……我认为全世界都知道如何做这件事了。现在我们正在将其规模化。每个人都在做，但我怀疑我们是否需要像今天这样去使用环境。我还不确定你是不是走得太远。

<details>
<summary>Original English</summary>

**Speaker B**: i think just next token prediction pre-training is not enough. uh and so i think we'll see some very interesting things still happen. uh and that rl in post training to induce behaviors to improve things like i think we the whole world knows how to do this now. i think we're we're scaling it up. everyone is but i wonder if we need to go as far as we're going today with environments. i'm not sure yet if you mean you're going too far.

</details>

**Speaker A**: 我不确定通往通用人工智能（AGI）的道路是否只是更多的环境。更多环境。这似乎是一个没有尽头的……我想要这个表格的操作手册，对吧？我是要构建家具的环境，还是我们只是要尾随，我们需要一些通用解决方案？我认为可以从网络中泛化出更多东西。但我也有很大的鼓舞感，比如当我看看拉古纳斯（Laguna S）时，后训练就是那件大事。而且我看到，哦等等，仅仅通过让这些行为变得更好，我们就能从中获得更多。这只是稍微改变了你对智能的看法。人们经常引用的类比是强化学习阶段是你学到的新知识不多。你重新调整了分布，你可以朝着你想要的方向推理。关于你在中期训练的观点，很多中期训练仍然只是在一个领域继续预训练，比如医学，然后你进行强化学习。所以，仍然只是预……

<details>
<summary>Original English</summary>

**Speaker A**: i think there is a ability to generalize more from the web. uh but i also i'm very encouraged like when i look at laguna s and just post training is is what is the big impact there. uh and i see like oh wait a second just by making some of these behaviors much better we're able to get so much more out of it. it just changes a little bit the way you think about intelligence. the analogy people draw often is the rl phase is where you don't learn as much new knowledge. you reshift. yeah. yeah. so, you know, you reshift distribution and you can have it reason towards what you want. um, on your point about mid-training, a lot of mid-training is still just continue pre-training in a domain, say medicine, then you do rl. so, still just pre...

</details>

**Speaker B**: 它是更好的数据，对吧？我的意思是中期训练，我喜欢我们发明这个词的方式，它实际上就像你知道第二阶段。它是预训练的第二阶段，但用一种非常愚蠢的方式来做课程设计，对吧？最终你想要的是从 token zero 到 token 30 或 40 个训练 token 的课程设计，那才是模型学习的最佳课程设计。但中期训练本质上是网络上的一个两阶段课程设计，因为我们没有计算资源……呃，有效地尝试消除完美的课程设计，对吧？所以，我确信你很快会看到人们谈论其他终极的两个或三个阶段，现在我们做这个，我们谈第二阶段和第三阶段。中期训练，但最终我们所做的只是试图将一个课程分配给我们的网络数据，以便让模型学得更好。我认为在某些时候，随着计算资源和模型的运行成本越来越低，下一代计算将成为一个更连续的谱。我也认为通过你进行中期训练以及第二阶段和第三阶段的方式，是组织性的。这是我想我们真正试图避免的模型工厂的问题。中期训练之所以存在，是因为有一个中期训练团队，现在有的人或者人们决定专注于某种中期训练的努力。但你真正想要的是工程和实验技能，它允许一个更连续的谱，而你没有无限的阶段了。现在我们不在那里。计算资源不在那里。组织设计还没有在那里。但我认为我们会到达那里的。我们几年后会回顾一下，然后想，“哦我的天哪，我们以前以如此天真的方式做了我们的预训练数据。”就像我们几乎没有订购它。我们并没有真正做好构建那种课程的设计工作。

<details>
<summary>Original English</summary>

**Speaker B**: it's just better data, right? like i mean mid-training, i like how we invented this word like it's effectively just like you know second phase. it's a second phase of pre-training with like a really dumb way to do a curriculum, right? like ultimately what you'd want is a curriculum from token zero to token 30 whatever or 40 train tokens that really truly is the optimal curriculum for the model to learn. but mid training is essentially a two-stage curriculum on the web because we do not have the compute uh and uh effectively to to try to ablate the perfect curriculum, right? and so i'm pretty sure that you'll start see people talking soon about some other terminal two or because now now we do this right we talk stage two and stage three and stage four mid training and like but ultimately all we're doing is we're trying to assign a curriculum to the web data that we have to uh to allow the model to learn better. i think at some point as things get compute as as models get cheaper to run as next generations of compute this will become more of a continuous spectrum. i also think the reason by the way you have mid-training and like stage two and stage three is organizational right it's this is i think a thing where that we really try to avoid with the model factory is like mid-training exists because there's a mid-training team now right there's people or like people decide to focus on like a mid-training effort uh but what you really want is engineering and and skill of experiments that allows for a much more continuous spectrum that you don't you have infinite stages now we're not there. compute's not there. organization design is not there for it yet. uh but i think we'll get there. uh we'll look back on a couple of years and be think, "oh my god, it was so cute that we did our pre-training data like this in such a naive way." like we barely ordered it. we didn't really do a good job at like the kind of building that curriculum.

</details>

**Speaker A**: 我会确认，当我与一些研究人员交谈时，他们说现在重点是预训练如何改变以及除了下一个词预测之外的下一个目标是什么。我假设你没有答案，但你有一些想法。我们有一些想法。我们还没有准备好讨论它。我们已经为此工作了几年。我认为这也是你之前问过关于构建基础模型公司中什么不明显的问题之一，那就是你不断地在平衡……

<details>
<summary>Original English</summary>

**Speaker A**: and i'll confirm that you know when i talk to some researchers that this is a lot of the focus now is like how does pre-training change and what is the next objective other than uh next token prediction. i assume you don't have the answers but you have some ideas. we have some ideas. we're not ready to talk about it yet. uh we've been working on them for years. and i think that's the one thing that's also like you asked earlier about like what's not obvious about building a foundation model company is that you are constantly balancing

</details>

**Speaker B**: 边。你知道，这个食谱有效。是的。与你的突破性的纯研究和找到那种平衡以及根据你在竞赛中的位置调整百分比是至关重要的。我的意思是，所以这是一种很好的方式，我本来想在某个时候提出自动研究。那是另一种发明。呃，这就像……诚实地说，可以有多少目标函数呢？比如试一千个，运行它，随便吧。这也……你知道你在寻找什么。你正在寻找失败者。像……人们还在赌一些事情，对吧？当你谈论更多的新实验室时，你正在做一种“我们将构建基础模型、扩大规模、下一个词预测器”的版本。我们看到的许多其他新实验室想要采取完全不同的方法，对吧？在某种程度上，你是对的，这都是关于计算效率，那是净目标，但你知道，有些是不同的架构，比如花费的计算量差异巨大。所以，有些是不同的。它们不是……你知道，99% 不平衡这里是纯粹的基础模型和扩大规模。它们是 99% 在这里是会改变一切的新研究。我认为看，这取决于你什么时候开始，对吧？是的。当我们开始做那个新东西时，我们做的强化学习在代码上。不长了，那已经不再具有新颖性了，但我们当时是……那是我们在没人相信强化学习的时候痴迷的地方。所以当你开始公司时，你必须有自己的想法。你必须有让你加速的东西。对吧？对我们来说，它是强化学习到LLM，后来变得普遍起来，你知道知识，但在开始的时候不是这样。

<details>
<summary>Original English</summary>

**Speaker B**: versus like your my breakthrough pure research and and finding that balance and and adjusting the percentage to it based on where you are in the race is really important. i mean so like this is a nice way i was going to bring up auto research at some point. that's another andre invention. uh, which is like i honestly like how many objective functions can there be, right? like just try a thousand of them, set it running, whatever. it's also like you know what you're looking for. you're looking for losers like that. like it's also a thing people take bets on, right? when you say more neolabs, you're doing a version of we'll do foundation models, scale them up, next token predictors. a lot of other neolabs that we see want to take a completely different approach, right? at some level, you're right, it's all uh compute efficiency and that's the net objective, but you know, some are okay, different architecture, like vastly different amounts of compute spend. so, some are different. they're not just they're like, you know, 99% not balancing here's the vanilla and scale up. they're 99% on here's novel research that'll change everything. and i think look i think it depends when you started as well, right? yeah. when we started like the novel thing we did was reinforcement learning on code. no long that's no longer novel by far but we were like we that's where we obsessed over when no one believed in rl. so you have to kind of when you start the company you have to have to have your own idea. you have to have something that's different that allows you to speed up. right. for us it was rl to llm that later became common like you know knowledge but in the beginning it wasn't.

</details>

**Speaker A**: 这很酷。你知道，这是你2023年的原始博客的宗旨。而且你把所有东西都摆在这里了。博客相当低估了，对吧？整个强化学习在代码上非常非常早。我们甚至不得不与一些人争论，比如我们说这里的一些事情，是为了推动超越当前能力来训练你自己的基础模型。我们不得不与那些人争论，你的自己有一个……你知道，基础模型很重要。你不能通过微调来找到成功的关键，对吧？主要的这种能力是从训练一个准确且有用的基础模型中产生的。

<details>
<summary>Original English</summary>

**Speaker A**: it's cool. you know, this was like your original 2023 blog of purpose and like you do lay it all out here. the blog is pretty underrated, right? the whole rl on code was very very early on. we even had to argue with people like we we say here things like to push beyond current capability to train your own foundation model. we had to argue with people that it mattered that you had your own like you know base model. uh you can't fine-tune your way to success, right? major capabilities emerged from training a base model made accurate and useful during fine tuning

</details>

**Speaker B**: 而从那个角度来看，在当时你知道我们知道闭源模型、开放的 Anthropic 很大，我们拥有的开源模型是 Mistral 7B、30B、70B。但当我们实际上……这个日期是错的，当我们发布它的时候，那是四月……

<details>
<summary>Original English</summary>

**Speaker B**: which like for perspective at the time you know we knew closed models open anthropic were huge the open models we had were like mistral 7B a 30B a 70b no but when we actually this the date on this thing is wrong when we published this it was april uh

</details>

**Speaker A**: 四月2023年。我认为这只是在 AR 上迁移文件上发生的事情。Mistral 一开始我们就从同一个月开始了，所以当时并没有……我记得当时只有 Llama 出来，就这样，对吧？所以……但我想我们确实想要……我们想要尽可能多的想法的多样性，而且我认为如果你今天开始，你想要的是能给你带来优势的东西，对吧？而我认为我们有时会过度思考。我认为每个架构在极限下都有效，RNN 也是如此。这只是计算效率不是吗？比如如果你有无限的计算资源，你可以可能就从前拿一个基本的 RNN，然后可以走得很远。现在已经有了有意义的突破了，注意力机制、其他东西在那里。但我想我们仍然……我们仍然处于弄清楚这些事情的非常早期阶段。我最兴奋的事情是……

<details>
<summary>Original English</summary>

**Speaker A**: april 2023 i think this is just happened on a migration file on ar on archive mistral had started we started on the same month right so this wasn't there was only i think llama out at the time and that's it right and so uh but i I agree i think we want we want as many diversity of ideas and i do think if you're starting today you you want something that gives you an edge right uh and what i do think we sometimes over i think every arch like at the limit every architecture works and rnn works it's just not compute efficient right like if you had infinite compute, you could probably just, you know, take a basic rnn from back in the day and you could get pretty far. uh now there have been, you know, meaningful breakthroughs, attention, other things that are there. uh but you i think we are we're still we're still very early in figuring these out. the things i'm most excited about i'm

</details>

<!-- chunk 8/15 -->

### 关于低精度训练和模型规模的讨论

**Speaker A**: 很多人对进行极低精度训练感到兴奋，对吧？比如我们现在看到的那些三元（ternary）的东西，那非常酷。昨天那个 bonsai 的东西也超级好看到。我记得你可以找到我2023年的一些推文，那是关于一个概念，就像是“这是一个明显的权衡”。更大的模型、更低的精度就意味着……你知道的，定义上就是更小的模型具有更高的精度，对吧？这只是实际情况是如何运作的，对吗？实际的大小限制在哪里？所以现在有公司正在试图弄清楚这个问题。比如那些东西如果做得对，可能会改变我们的行业，因为最终我们计算能力的瓶颈是枫树（maple）瓶颈和网络瓶颈，而当你开始做这些事情时。所以我对那感到兴奋。我们并没有在做任何……我的意思是，我们通常会像 Laguna S 那样用 FP8 进行训练。不过在这场运行中，我必须承认不是 FP8 的是新运行中全量（all-to-all）的。昨天我们刚开始的新运行，FP8 全量就是那种……就像断电一样，我们不太习惯想要这样做。

<details>
<summary>Original English</summary>

**Speaker A**: most excited about people doing extremely low precision training, right? So like the ternary stuff that we're seeing and it was very cool. The bonsai stuff yesterday was super cool to see. Uh, I think there's you can find tweets from me going back to 2023 which is like kind of the notion of like well it's an obvious trade-off. Bigger model, lower precision equals, you know, smaller model with higher precision by definition, right? It's just what is like how does that actually play out, right? What's the actual size limit? So you now have companies that are trying to figure that out. Like those are the kind of things that can change our industry if they're done right because ultimately like our bottleneck on compute is is is a maple bottleneck uh and and a networking bottleneck and the moment you start doing those things. So I'm excited about that. We're not doing any I mean we're doing the usual like uh Laguna S was trained in FP8. Uh only thing that in this run I have to admit that wasn't FP8 was the all to all in the new run we just started yesterday. 80 fpa it was all to all that was just like cut off day like we're not perfectly comfortable wanting to do it.

</details>

**Speaker A**: 你在 NVFP4 训练方面有很棒的工作，我 ​​认为他们在那方面被低估了。我对进行 NVF4 训练感到兴奋。这还没有意义，因为我们仍在对 hoppers 进行训练，对吧？我们相对较小。我们现在是 10k H200 集群公司，很快就会扩展到更多，但如果有人正在考虑申请工作的话……但是是的，我认为这里有更多的潜力可以榨取，希望 Laguna S 能向人们展示这个规模的模型可以获得更多东西，而且我们在 8 周内完成了这件事。我们认为任何模型大小都有更多的潜力可以榨取。现在我们正在扩大规模，因为这对我们公司来说是最优选择，但如果我有无限的时间，我非常想在其他模型尺寸上推动更多的能力。

<details>
<summary>Original English</summary>

**Speaker A**: Uh you've got amazing work by Neimatron in NVFP4 training like I think it's underrated what they've done there. Uh I'm excited to get to NVF4 training. Uh doesn't make sense yet cuz we're still training on hoppers, right? We're like relatively small. We're 10k H200 cluster company right now. will be scaling to a lot more soon, but uh and really a lot more if someone is thinking about applying for a job. Uh but like the yes, I think it's there's so much more juice to squeeze out of this and hopefully Laguna S shows people that a model at this size can get a lot more and and we did this thing in 8 weeks. We think there's a lot more juice to squeeze out at any model size. uh we're now scaling up because it's the most optimal thing to do for us as a company, but if I had infinite time, I would love to push more the capabilities at other model sizes.

</details>

### 模型尺寸的演变与 Laguna S 的情况

**Speaker A**: 我不认为我们已经正确宣布了你们的新尺寸。所以，我们有 XS，大约是 30B。旧的中等模型是 200B，这似乎将过时了。新……Laguna S，1181180 亿总参数，8B 活跃参数。所以非常稀疏。这是对冗余架构的扩展。这就像现在的经典或者说叫经典，比如滑动窗口注意力与全局注意力的 3:1 比率。它只是对于我们来说是一个不错的尺寸，有两个原因。一个是成本效益极高。这对我们快速取得进展是一种很好的方式。我们看到的一件事是，在一家基础模型公司内部，我们在发布和交付之间取得了平衡，以及你们的新研究。但是有了模型工厂，我们可以将模型的发布视为团队投入时间减少的一部分，因为在此时此刻，你知道，你完成了预训练运行，应用最新的后训练，所以这是一种很好的权重类别。它也能装进 DJX Spark 中，我有一个小小的软性偏好。我喜欢拥有那个小东西，你知道的，运行一个好的模型。

<details>
<summary>Original English</summary>

**Speaker A**: I don't think we've properly announced what your new sizes. So, we have XS which was 30Bish. Uh old medium was 200B which is going to be deprecated it seems. So, new Laguna S Laguna small 118118 billion total parameters 8B active. So very sparse. It's a scale up of the excess architecture. Uh it's the kind of classic or call it classic these days like 3:1 ratio of sliding window attention to global attention. It's just it's a nice size uh for a couple of reasons. One is just very costefficient for us. It was a good way to do we wanted to get our progress out quickly. One of the things that we've seen is that it's a balance inside a foundation model company between focus on releasing and shipping and like your new novel research. But with the model factory, we are able to like treat the release of a model as less of a time investment from the team because it's just oh at this moment in time you know do the pre-training run done apply the latest post-training and uh and so this is I think a nice weight class. It's one that also will fit on the DJX Spark, which uh I have a small like soft spot for. I love having that little thing like, you know, run a good model.

</details>

### 模型性能的对比与行业地位

**Speaker A**: 是的，我们在去年在 GTC 上就涵盖了这一点。很好。我认为 GPT OSS 12B 是第一个，因为它是一个大型单 GPU，也就是 H100，对吧？租一个 H100。现在你有了 128GB Max、Mac mini、Sparks。这是最理想的地方。但我认为我最兴奋的是这个模型有望向人们展示这个规模是可能的，因为当你查看基准测试并开始使用它时，你会意识到我们正在超越其尺寸的模型两到三倍。是的，他们会这么想。比如今天的 Thinky 模型大约有万亿参数。所以是的，没错。而且看，我兴奋的是，它刚刚发布了。所以对于听着这个的人来说，我是在我的手机上看到它的，两秒钟就来了，所以我甚至还没有机会读完帖子。但是以某种方式，你不仅比 Thinky 好，而且在某些基准测试上，比如那个 tow bench（双边测试），你实际上是前沿水平。我们正在看，我们正在做……我不太确定我们在 3 银行方面是否处于最先进水平，我还没有检查我们在排行榜上的位置，但我认为我们在我们权重类别内是安全的，我在说这个感觉非常舒服，甚至在比我们大两倍的某些权重类别中，我们可能就是前沿水平。我也想对这一点做保留，你知道，目前世界上最好的模型仍然是……给我一个一个 5.6 的点，我之前也使用了其他模型。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, we covered it on this pod GTC last year. Nice. I think a GPT OSS 12B was the first because it's a large single GPU, which was the H100, right? Rent one H100. Now you've got 128 gig max, Mac minis, Sparks. It's it's the home sweet spot. But I think what I'm most excited about is that this model hopefully shows people what is possible in this size because uh when you'll look at the benchmarks and and start using it, you'll realize that we are outperforming models two or three times their size. yeah, and they think so for example today's Thinky model is like a trillion pars. so yeah, exactly. And look, and by the way, I'm excited about I have it just came out. So for those of you listening to this it like I saw it on my phone coming in two seconds, so I haven't even had a chance to read the post. but somehow you are not only you're you're better than thinky which is like one of those benchmarks but also like on certain benchmarks like the tow bench one like you're actually state of the art. We're look we're doing uh I'm not sure if we're state-of-the-art on I mean 3 banking I haven't checked where we sit on the leaderboard uh but I think we are within our weight class I feel very comfortable to say and even in some weight classes twice larger that we are probably state-of-the-art. I also want to caveat this like you know best model still in the world right now is definitely you know give me a fable give me a 5.6 to your point earlier we also use other models.

</details>

### 使用内部评估和模型发布流程的价值

**Speaker A**: 我认为你之前提到的有趣的是，你开始将大量的实际使用转向它，对吧？基准测试是用来比较的，但它们并不完全现实。是的，它们必须是这样。这是他们将如何进行 dog food 基准测试的方式。不，你必须……你需要使用你自己的模型，并拥有你自己的内部评估和基准测试，而有趣的是，在新的检查点发布后的前 30 分钟内，那就像预训练之后的第一轮后训练，你自己可以感受到这个模型将如何发展。你并不完全知道，但当这个模型出来时，我们是……哦，这不一样了。而且我认为那是……我想那是例子，但它有点像你的孩子，我不知道孩子们，你知道的，父母会看到他们的孩子，它很完美，他们喜欢它，然后你知道他们看不到你构建自己的过程中所有的粗糙边缘。最有趣的部分是你对你做出的每一个模型都有一点喜爱。我们试图不断地表达这一点：这是我们训练过的最差的模型，所以我知道团队现在已经准备好进行下一个了，因为它应该如此，因为这是一场竞赛，而这个模型是时间的一个时刻，希望向人们展示我们对这场竞赛的认真态度，我们想为此非常努力，我们想要反馈，对吧？哪里做得好？哪里不好？拥有自己的模型在世界公开是一种好处，你会得到很多反馈。你如何看待用一个 harness（框架）构建它，比如……开源代码、codeex，你有你自己的 CLI 工具池。基本上让人们使用它，模型的代码设计、训练它进去。所以你需要做一些多 harness 训练，特别是对于这些较小的尺寸，你想对这些模型做一点多 harness 训练，只是为了确保正确，而且这非常小，你知道，你不需要很多，但只是为了让你在你的 harness 中看到的那些正确的行为转移到其他人可能会使用的 harness 上。我们内部一直把这称为“打磨”，也就是你有你的模型，你对它做一点打磨，让它能够在你自己的 harness 上很好地工作。毫无疑问，在你自己 harness 上会更好。而且仅仅是因为你把强化学习计算放在哪里？你把你的 RL 和合成数据放在你自己的 harness 里，因为它是你理解得最好的，并且你可以推动最多的东西。因为这种端到端的控制允许你让它变得更好。然后将这些能力转移更多的是确保模型诱导了正确的推理量，你知道，理解一些可能存在于其他地方的更复杂、更奇怪的工具调用格式。所以我们进行多 harness 打磨，这就是我们称之为“打磨”。这并不是驱动能力的因素，但它创造了更好的体验。我个人认为，坦率地说，我认为每个人这些天可能都在做这些事，但看到为什么你自己的 harness 仍然会……

<details>
<summary>Original English</summary>

**Speaker A**: I think that so the interesting thing you mentioned earlier is you're starting to shift a lot of your actual usage to it, right? Benchmarks are like they're good to compare, but they're not super realistic. They they have to, right? This is how they're going to dog food benchmark. No, you have to like you have to use your own models and and you have to have your own internal evals and benchmarks and and what the funny thing is is like within first 30 minutes of a new checkpoint coming out that's you know the kind of first post train after a pre-train you yourself can feel in the first 30 minutes of where this model is going to be like you don't know exactly but like when this one came out we were like oh like this is different like uh and and I think that's I think that's the example uh but it's a little bit like you know like your kids I don't know if kids by you know parents like they see their kid and it's perfect and they love it and then like you know they don't see all the rough edges you always get that when you build your own it's the most fun part is that you like you love a little bit every model that you do we try to kind of say this thing constantly it's like it's the worst model we'll ever train and so I know the team now is like already on to the next one uh as it should be because this is a race uh and this model is a moment in time that hopefully shows people that we are serious about this race, that we want to work really hard at it, that we want feedback, right? Where is it good? Where is it not? Like one of the nice things about having your models out in open way out in the world is that you get a lot of feedback. How do you think about building it with like um working with a harness, right? So open code, codeex, you have your own pool CLI tool. Um basically getting people to use it, the code design of model harness, training it in. So you need to do some multi-harness training like if you uh especially at these smaller sizes like you want to do a little bit of multi-harness training for these models to just get the right and it's very little like you don't need a lot but it's just like to get the right behaviors that you see in your harness transferring to the harness that like you other people might use it in. Uh we internally have been kind of this calling this polishing which is like you've got your model you do a little bit of polishing so that like it's able to work well on other harnesses as it is in your own. No doubt it's going to be better in your own harness. And and it's just because of like where are you putting your reinforcement learning compute, right? You're putting your RL and and your synthetic data, you're putting it to your own harness because it's the one that you understand the best and you're able to kind of push the most. Uh because that end-to-end control is what allows you make it better. Uh then transferring those capabilities is more about just making sure the model, you know, induces the right amount of reasoning and like, you know, uh understands some of the maybe more complex weird tool call formats that might exist somewhere else. Uh, and so we do do some multi-harness polishing as we call it. Uh, it's not really what drives capabilities, but it does create a better experience. I think frankly I think everyone probably does these days, but it is totally fair to see why your own harness is going to still

</details>

<!-- chunk 9/15 -->

### 关于模型能力与工具的权衡

**Speaker A**: 我们认为，在推动能力时，我们并不想通过在强化学习（RL）运行中加入十个“套件”（harnesses）来交换性能提升，因为这只是复杂性。这是工程上的复杂性，因为当你试图做好的科学研究，当你试图真正理解什么能让我的模型改进时，你希望改变一个变量为你能理解的东西，而将来自你不了解或不能以你理解的方式理解的别人的套件引入。对吧？他们可能有不同的子集或不同的提示词。如果它是开源的，你可以查看源代码。

<details>
<summary>Original English</summary>

**Speaker A**: be better than others. And I think we see this with all the foundation model companies. Uh, and it's just that when you are pushing capabilities, you don't really want to trade it off by putting 10 harnesses in your RL runs because it's just complexity. It's complexity of engineering because these when you're trying to do good science, when you're trying to really understand what make my model improve, you want to make one variable change to something you understand and a harness from someone else you don't know or understand in the same way as you understand your own. Right? They might have different subaents or different prompts. Well, if it's open source, you can look at the source.

</details>

**Speaker B**: 是的，但现在是时候了，对吧？比如我真的不能强调，我知道我在这方面有点奇怪，因为我有朋友，我们可以见面吗？或者我们可以做这个吗？或者我们可以去？我没有，因为最终这是一场竞赛，时间才是唯一重要的东西。如果我看看我们的团队，然后说“好吧，在构建能快速泛化到其他套件的模型方面，我们为什么要引入这种复杂性？”而且从某种意义上说，我们的模型在自动套件中表现得很好。我真的鼓励人们去做这件事。它很有效。比如我们在开源代码和Kilo Code以及其他人那里进行了测试，还有……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, but it's time, right? Like like I really cannot stress like I know I'm like a weird person on this because like I have friends like can we meet up or can we do this or can we go? I'm like no because ultimately this is a race and time is the only thing that matters. And if I look at our team and say okay what is complexity worth introducing on our general trajectory to building more capable models which generalize to other harnesses quickly and by the way our model works well in auto harnesses. I really encourage people to do it. It works well. Like I've we've been testing in open code and kilo code and others and like and in clock

</details>

**Speaker A**: 我知道本田。

<details>
<summary>Original English</summary>

**Speaker A**: I know Honda.

</details>

**Speaker B**: 没错。

<details>
<summary>Original English</summary>

**Speaker B**: Exactly.

</details>

**Speaker C**: 一切都在被购买。

<details>
<summary>Original English</summary>

**Speaker C**: Everything's getting bought.

</details>

**Speaker A**: 我认为其中一部分是，你知道，而且有一些很棒的……我兴奋的是，我觉得她的套件实际上非常酷，比如……

<details>
<summary>Original English</summary>

**Speaker A**: Uh and I and I think part of that is like you know and there's some amazing I'm excited like I think her mess is actually ridiculously cool harness like uh and so

</details>

**Speaker B**: 而你你知道，问题的一部分实际上只是模型与模型加套件的努力程度有多大，对吧？新的基准测试，比如智能体（agents）……它不只是想衡量模型。同样地，随着模型变得越来越像智能体，它们需要一个套件来运行，对吧？所以，我认为当你向模型公司提出这个问题时，你可以将其分成两部分：一个是套件，就像我们有一个非常精简的套件。当你查看它时，它就像六个工具。它就像 shell 和 shell kill、shell weight、write、fetch web，还有……我不知道，bash。我想我漏了一个，但基本上就是所有的工具，而且非常简单。它是非常轻量级的。所以它不是一个旨在在一个基准测试上表现良好或在一个特定子集上表现良好的套件，对吧？它不是一个深度研究的套件。所以我认为我们看到了构建了大量提示词和额外数据源和其他工具来真正推动模型能力的复杂套件所展现出的惊人能力。但我们的模型在编码任务中仍然比那些在代码方面做同样事情的其他套件要好，因为它是在 RLED（强化学习）中训练的。现在我鼓励人们，我认为我们的模型以目前的形式是完全可以接受的，并且很好，差异可能对任何人来说都太小了，但我们最终在基准测试上仍然略有优势。所以我想两者都是真的。拥有套件的基础模型公司会真正推动它们，因为从操作上讲，这是具有科学严谨性和改进模型的最好方式，但也有一个愿意拿我们的模型并投入大量精力来改进套件的人将与我们竞争，正如他们应该做的那样。而且那仅仅是因为套件是模型的能力和它需要的额外指令以及它需要的访问数据和工具之间的“补丁”。这最终我认为就是一个套件是什么。随着你构建更强大的模型，你知道你在改进模型的指令遵循能力。而额外的套件只是说：“嘿，如果你遇到 X、Y 或 Z，就以这种方式表现。”所以即使你会说两个具有不同套件的模型可以达到你所关心的同等能力，一个专门针对某种能力的套件会更有效地做到这一点。这有点像一个人正在学习如何以最高效的方式完成任务，使用正确的工具和正确的数据源，与一个真正聪明的人去想办法。他们都会解决任务，但其中一个会做得更有效率。所以我非常支持当前世界中发生的各种套件开发。我们希望与更多的套件创建者合作，确保如果它需要一些额外的训练，比如打磨，我们会做这件事。

<details>
<summary>Original English</summary>

**Speaker A**: But our model is still better than some other harnesses who do that in coding like tasks because it was RLED with it. Now I do encourage people I think our model by the way is perfectly fine and good that the differences are probably maybe too small for anyone to notice but we see it ultimately still on benchmarks uh by a little bit. So I think it's both are true. Foundation model companies with their harnesses will really push them because it's just operationally frankly the best way to have scientific rigor and improving your models but also someone who takes our model and really does a lot of work on improving a harness is going to out compete us as they should. Uh, and that's just because the harness is the stop gap between what the model is capable of and what it needs as additional instructions and what it needs as access to data and tools, right? And that's ultimately I think what a harness is. It's like is it able as you build more capable models, you know, you're improving the instruction following the models. And so additional harness is just saying hey if you encounter X Y or Z behave this way. And so even if you would say that two models with two different harnesses can equally reach the same capability that you care about a harness that is really tailored towards a capability will do it more efficiently. It's kind of like a person who's getting a manual of how to do the task in the most efficient way with the right tools and the right data sources versus a really smart person like go figure it out. They'll both solve the task, but one will do it a lot more efficient. So, I'm a big fan of all the harness development that's happening in the world. And we want to work with more harness like creators to also make sure that like if it needs some additional training like polishing that we will do it.

</details>

**Speaker B**: 我是说，嗯，我想当你把这描述成一场竞赛时，有一个问题是你们在竞速什么？你们是在竞速成为最好的编码模型公司还是最好的编码模型加套件公司？我认为这两者是不同的东西。或者填空或两者都不是。所以我们从零开始就为我们的网站提出了 AGI 编码的想法，并且我们一再强调这一点。我们认为专注于编码和长期的软件任务是一个通往 AGI 的道路，因为它迫使我们解决困难的问题。它迫使我们解决执行需要大量推理、外部工具、数据等的极其复杂的长期复杂工作的能力。我能向你展示的一件事是，所以我们将有一个与这个模型进行网络聊天，而且我喜欢这个模型进行深度研究，只是用它来做我的编码艺术。它从未为此训练过。它从未被看作是这样的，但就我个人而言，它在这一点上很棒。因为最终技能会迁移，它们会泛化。现在我们目前关注的不是让世界上最伟大的医学知识被编码到这个模型中，或者世界上最伟大的法律知识，但实际上我们不会发布这个基准测试，因为我们没有时间真正做，但它在法律实务上表现得非常好，而且至少在我们第一次运行上，我们非常严谨，当我们发布评估时，我们会检查每一个小细节。我们运行了它很多次，我们通过了，就像我们……我们试图对它保持极度的诚实，所以如果我们没有花足够的时间在基准测试上，而我们在内部使用它，那才是公开的。我们只是说我们不会发布它。嗯，所以我的意思是另一种方式就是把它交给人工智能分析，让它们像第三方一样运行它。

<details>
<summary>Original English</summary>

**Speaker B**: I mean, um I think when you say it's a race, there's a question of what are you racing to? Um are you racing to be the best coding model company or the best coding model plus harness company? I think that's a do those are different things. Or fill in the blank or neither. Uh so we I I raised AGI coding for us since day zero of our website has been and we've said this over and over again. We think focusing on coding and long horizon like software tasks is a path towards AGI because it forces us to solve the hard problems. It's it forces us to solve the ability to do extremely long horizon complex work that requires lots of reasoning, external tools, data, etc. And one of the things I can show you, so we'll we'll have a web chat on with this model and I've loved this model for deep research, just using it in my coding arts. It was never trained for it. It was never like looked at it, but it's great at it in my opinion. Uh because ultimately the skills transfer, they generalize. Now where we are not focused on today is to make sure that the world's greatest medical knowledge is encoded in this model or the world's greatest legal knowledge but it actually did we won't be publishing this benchmark because we didn't have time to really do proper but it did really well on legal bench uh and at least on our first runs uh and we are very rigorous when we publish eval we have checked them for every little thing we have run them many times we've passed like we've gone and we like we try to be extremely honest with it so if we haven't spent enough time on benchmark that we use internally that is public. We just said we won't publish it. Um and so I mean the other way is just to give it to artificial analysis and let them run it like third party.

</details>

**Speaker C**: 哦，100%。我们将会把这做得很出色，而且仍然需要时间和精力，对吧？因为你正在与人们合作来理解……你知道，基础设施以及他们使用的工具，它们设置得好吗？但我同意你绝对想要。我是一个 Vals 和 AA 以及其他在做这些事情的公司的大粉丝。

<details>
<summary>Original English</summary>

**Speaker C**: Oh, 100%. And we are going to be doing this as well and and still it takes time and effort, right? Because you're working with people to understand like you know the infraures and and like the tools they're using and like are they set up well. But I agree you absolutely want to. I'm a big fan of companies like Vals and AA and like others that are doing this stuff.

</details>

**Speaker A**: 你是第一个提出这个问题的。

<details>
<summary>Original English</summary>

**Speaker A**: You're the first to bring it up.

</details>

**Speaker B**: 是的，我认为它们很棒。它们做了很多工作并发布了东西。而且我认为还有更多，请创建更多的评估公司，比如创建更多的评估。我认为这对行业非常有价值。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think they're great. they've got like I I love like a lot of the work they've done and put out. Uh and so and there's I think many more and please create more eval companies like create more evals. I think it's so valuable for the industry.

</details>

**Speaker C**: 实际的垄断。我感觉……哦，寡头市场也许吧，你知道吗？

<details>
<summary>Original English</summary>

**Speaker C**: Actual monopoly kind of I feel like oh duopoly maybe you know

</details>

**Speaker B**: 我认为它可以被打破。

<details>
<summary>Original English</summary>

**Speaker B**: I think it can be broken.

</details>

**Speaker A**: 是的，因为我认为它实际上可以非常容易地被打破，因为创建评估不是性感的工作，但无论谁做，每个人都愿意得到一个好的评估。你从来没有……如果一个 EVA 构建得很好，每个人都在庆祝它，每个人都愿意为此付费，而且每个人都愿意像基础市场一样。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah because I think it can actually be broken really easily because creating an eval isn't sexy work but whoever does it everyone is happy to get a good eval. You've never like if an EVA is well constructed, everyone's celebrating it and everyone's willing to pay for it and everyone's willing like the foundation market.

</details>

**Speaker B**: 哦，是的。是的。我认为创建评估……是。但就成为行业标准而言，我们将会运行 TB 并确保你没有作弊，我会以你运行的方式来运行它，而不是你的竞争对手运行它。

<details>
<summary>Original English</summary>

**Speaker B**: Oh yeah. Yeah. I think creating eval Yes. But like in terms of being like we are the industry standard ones that will run TB and make sure that you didn't you didn't cheat and I'll run it the same way that you run it versus your competitor run it.

</details>

**Speaker A**: 是的，那非常正确。我们需要那个，而且很不错的是，我们有几个标准的地方可以遵守。这让我们都保持诚实。我认为这超级重要。所以……嗯，但是的，不，我认为我们的目标是构建世界上最强大的模型，现在我们专注于编码智能体能力和长期的任务，但你看到的那样，你会得到很多免费的东西。我一直说，对于我们来说更容易，因为我们能接触到编码的前沿，然后说“好吧”。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, that is very true. And we need that and and it's actually nice that that's like a few standard places that we all have to like, you know, adhere to. It keeps us all honest. I think that's super important to do so. uh and uh but yeah no I think our goal is to build the world's most capable models uh and right now we are focused on the coding agent capabilities uh long arising work but what you see with that is that you get a lot for free I've always said it's a lot easier for us as we get to you know sot and frontier on coding to then say okay

</details>

<!-- chunk 10/15 -->

### 模型工厂与代理框架的讨论

**Speaker A**: 现在，我们将专注于使用模型工厂来为那些你已经了解的地方添加更多数据。我们不像在医疗或法律等领域那样强大。嗯，同样地，我认为我们看到和我们通过推理模型看到的情况很多。如果你给模型访问正确的知识来源，并且它们有能力进行推理，它们就能很好地深入到对它们来说不太熟悉，甚至在它们的训练数据中是无缝的领域。所以，但是是的，我们现在是像代理一样的模型加 harness 吗？不是，我们是一家模型公司。嗯，但我认为今天的模型不能在没有 harness 的情况下进行训练。这是不可能的。所以，它有点就像以前一样，只是容器中的权重。现在有一个附加到它的代理 harness。嗯，但我认为作为一家模型公司而成为一个代理 harness 与真正构建一个代理公司的不同是巨大的。我认为他们可以做比我们多得多的事情。

<details>
<summary>Original English</summary>

**Speaker A**: now we're going to obsess in using the model factory to add more data for places that you know we're not as strong on like could be medical or legal or any other areas um and similarly I think what we see and we see this with reasoning models a lot if you give models access to the right knowledge sources and they have capable ways of reasoning they're able to go very well into domains that are less known to them or even seamless in their training data so uh but yeah are we agent like model plus harness no we're model company uh but i think models today cannot be trained without harnesses it's not possible so it kind of is just like where before it was just the weights in the container well now there's an agent harness that's attached to it uh and but i think there's a big difference in being an agent harness as a model company than someone who's truly building an agent company i think they can do far more than we can

</details>

**Speaker B**: 是的。嗯，我明白了。是的。我认为那是我一个小小的反驳。如果你真正定位为一家模型公司，那么就为开源代码做最好的模型，对吧？而不是为了池或任何其他东西。嗯，我认为这不像你知道那样，这与目标相比微不足道，如果目标是 AGI，实际上就是为 Hermes 做最好的模型。

<details>
<summary>Original English</summary>

**Speaker B**: yeah um understood yeah i think that that is my minor push back if you are truly identify as a model company then make the best model for open code right instead of for pool or whatever um i think that that's not as you know that's that's minor compared to actually if the goal is AGI actually make the best model for hermes

</details>

**Speaker A**: 对，比如因为那是编码之后的下一个阶段。我一直在和他们非常密切地合作，因为我认为你必须投入精力去维护它，这就是我们进行打磨并花时间做这件事的原因。而且我认为加班是必要的，是的，你对平衡这一点是正确的，但最终你只是想要通用能力，让所有东西在每个 harness 中都能平等运作。

<details>
<summary>Original English</summary>

**Speaker A**: right like because that is the next stage after coding i'm look and we are uh we're working actually like very closely with them because i do think like it's and uh you have to care you have to invest in it's why we do the polishing and we spend time on it uh and i think over time yeah you're you're right that you want to kind of balance that out but ultimately you just want general capabilities that everything works equally in every in every harness

</details>

**Speaker B**: 嗯，就这个话题来说，你们在做 Hermes、open claw、nano claw 等方面做了很多事情吗？

<details>
<summary>Original English</summary>

**Speaker B**: uh just on the topic do do you guys do much with like hermes open claw nano claw whatever

</details>

**Speaker A**: Pi pi。不，pi 是一个不同的派对。

<details>
<summary>Original English</summary>

**Speaker A**: pi pi no pi is a different pie

</details>

**Speaker B**: 更多是编码。

<details>
<summary>Original English</summary>

**Speaker B**: it's more coding

</details>

**Speaker A**: 我是 Pi 的大粉丝，但我必须说，我认为它真的很像 Pi。在池方面和在最小表面方面，你听起来最接近 Pi。

<details>
<summary>Original English</summary>

**Speaker A**: i'm a big fan of pi though i have to say i think it's a really pi pi you sound closest to pi in terms of pool and pi in terms of like the minimal surface

</details>

**Speaker B**: 最小的。因为我没有……给我一个更强烈的意见。

<details>
<summary>Original English</summary>

**Speaker B**: the minimal it's because i don't i have a allow me for one more strong opinion

</details>

**Speaker A**: 我已经这么说两年了。我认为 MCP 和工具是愚蠢的。

<details>
<summary>Original English</summary>

**Speaker A**: i've been saying this now for two years i think mcp and tools are stupid

</details>

**Speaker B**: 哦，那很酷。现在你支持 MCP。

<details>
<summary>Original English</summary>

**Speaker B**: oo that's cool now you support mcp

</details>

**Speaker A**: 我支持 MCP，我们支持工具和一切。这对我来说完全没有意义。然后我会解释一下原因，然后我认为我可能可以让人们在这个问题上达成共识。如果你正在寻找复杂的任务，越来越长的时间跨度，越来越复杂的任务，无论它是编码还是其他东西，你都会与数据源进行交互，对吧？你将与安装在某种形式的虚拟机上的东西进行交互。而我们所做的就是我们在那些东西之间放置一层。我们把 MCP 放在中间。我们把工具调用放在中间。这甚至更多地关乎工具调用，模型可以只是编写代码并与系统进行交互。我们开始看到像 Laguna S 在做很多这样的事情。你会在 Frontier 模型中看到这一点。它们越来越不再是这里，我们将把 50 个工具塞进系统提示里，在这里有一个安装了这些二进制文件的虚拟机。你可以在这个文件夹中操作，如果你想的话可以写你的内存。模型正在使用代码来完成复杂的任务。当它使用代码时，它不是一个或两个被链接起来的工具调用或三件事。它实际上是从使用 if 语句和 for 循环开始的，并使事情具有条件性。所以，我认为我们正在从工具调用转向模型有效地编写代码、小脚本。当你得到 Python 代码解释器时，你会看到这一点。

<details>
<summary>Original English</summary>

**Speaker A**: i support mcp and we support tools and everything they make absolutely no sense to me uh and like and then i'll explain a little bit why and then i think i can probably get people to come along on this one if you are looking for complex tasks increasingly longer horizon increasingly complex task doesn't matter if it's coding or something else uh you are going to be interacting with data sources right and you're going to be interacting with things that are installed on some form of a virtual machine uh and what we are doing is that we're putting a layer in between those things we're putting like mcp in between we're putting tool calls in between and this is even more about tool calls than mcp where the model can just write the code and interact with the system and we're starting to see that like laguna s does this a lot you'll see this as well in like frontier models they're increasingly no longer here we're going to stuff 50 tools in the like system prompt to no here's a virtual machine with these binaries installed this code base you can operate in here a folder where you can write you know your memory if you want and the model is using code to do complex tasks and when it uses code it is not one or two tool calls or three things that are chained together it actually starts you know using if statements and for loops and and making things conditional and so i actually think we're moving from we already are moving from tool calls you know to effectively models writing code little scripts and you see this a lot when you get the python you know

</details>

**Speaker B**: 完全正确。就像在箭头里，你知道，编写的代码和文件。我不知道你叫什么 EOF。是的。完全正确。嗯，你已经在模型中看到这种情况发生得更多了，因为当你开始以 RL 训练它们时，模型想要自由，它们想要以最有效的方式完成它们想做的事情，而不是在系统提示中调用那 50 个工具中的一个。所以，我非常喜欢给模型一个最小的 harness，尽可能小的，给它一个包含其自身代码库、可以访问 API 密钥和数据源以及它需要的少量库和文档的容器，然后让它自由运行任务。嗯，我认为这就是我们前进的方向。我想在 12 个月内不会再看到一个塞满了 20 个或 30 个或 40 个工具的单个系统提示了。

<details>
<summary>Original English</summary>

**Speaker B**: exactly like in just the arrow arrow you know written code and the file i don't know what you call the eof yeah exactly uh you already see this happening more in models because when you start training them in rl the models want to be free they want to be able to do the thing they want to do in the most efficient possible way and it is not calling one of the 50 tools in there like system prompt and so i'm a very big fan of give the model a minimal harness as minimal as possible give it a container in which it has its own codebase right they got a model's codebase that has access to the api keys and data sources and and little libraries and and documentation that it needs and just let it run free at the task um and i think that is the way we're going i think we will in 12 months not see a single system prompt that is stuffed with 20 or 30 or 40 tools anymore

</details>

**Speaker A**: 不评论，不反驳。我认为……我认为它会得到支持很长一段时间，只是因为现在很多人都在用它进行训练。但也许你们在未来的模型中不需要支持它了。所以，嗯，但是是的，我的意思是如果你能，我想写代码是更通用的，它是一个终点手段。

<details>
<summary>Original English</summary>

**Speaker A**: no comment no no push back there i think uh i think there will be it'll be supported for a long time just because that's a lot of people are trained on that now but maybe you guys don't have to support it in your models going forward so uh but yeah i mean if you can i do think that's writing code is more generalist and it's a it's a means to an end

</details>

**Speaker B**: 和我们支持工具，而且这实际上是我们正在做的第一个并行工具调用模型，我们需要赶上。所以，那就在那里，就像这样，但……这是我个人的小意见，我想让模型拥有尽可能多的自由度，只是让你知道自由并能做有能力的。

<details>
<summary>Original English</summary>

**Speaker B**: and we do support tools and we support and this is actually the first model we're doing parallel tool calling in which we needed to catch up on so like that's there and like so it's it's there but i it's a personal nitpick like i want the models to have as many degrees of freedom and just like you know be free and and do capable things

</details>

**Speaker A**: 是的。所以，那就是通往……如何为我的 Hermes 或我的 open cloud 做使用 poolides 模型和 laguna 模型之类的一切的路径。通常我寻找的是计算机使用或视觉能力，那是一个非常大的问题，你们有一篇关于它的博客文章，但同时持久性我认为与长上下文一样具有很强的价值，而你们有百万个 token 的上下文。

<details>
<summary>Original English</summary>

**Speaker A**: yeah so and then so that was on the path towards like okay how do you use poolides models and laguna models for my hermes or my open cloud all those things and so typically what i look for is um computer use or vision that's a that's a very big one you guys have a blog post on that but then also the persistence i think is very strong value as well as long context which you guys have a million token context anything else

</details>

**Speaker B**: 所以对我们来说，看，对我们来说，视觉理解是下一步，对吧？我们还没有视觉理解。

<details>
<summary>Original English</summary>

**Speaker B**: so for us look so for us vision understanding is is the next thing right we don't have vision understanding in these models yet

</details>

**Speaker A**: 我本来打算……嗯，我们还没有这些模型的视觉理解。而且这是我们已经开始努力做的事情之一，我们认为拥有视觉理解超级重要。那是公司愿景。嗯，所以不，我们还有工作要做。而这实际上是我喜欢思考模型的原因之一，从我浏览博客文章的两分钟来看，我对多模态（包括音频）非常投入。

<details>
<summary>Original English</summary>

**Speaker A**: i was going to is the we don't have vision understanding in these models yet uh and so this is something that we've we've started efforts on like we think it's it's super important to have visual understanding that's company vision uh and so no we've got work to do there and and this actually one of the things i loved about the thinking model like from the two minutes i scrolled the blog post very committed to multimodal including audio

</details>

**Speaker B**: 是的。它们是最先进的音频，无论参数有多大，都是最先进的音频，但也是从头训练的，对吧？不是那种编码器意义上的。对我来说，这是你需要从头开始的一个最强理由，因为你会拥有不同的分词器。你会完全一致，就像零……我在这里没有异议，只是添加模态，然后保持简单。我们不太会长期处理音频。它在名字里也算一个。

<details>
<summary>Original English</summary>

**Speaker B**: yeah they're state-of-the-art audio as much as it's a trillion parameter state-of-the-art audio but also all trained from scratch right no encoder in the sense to me that's that's that's one of the strongest reasons why you need to trade from scratch is you would just have a different tokenizer you'd have different i'm fully aligned like zero dis zero disagreement from me here like uh just add the modality and and and don't put you know keep it keep it simple uh we're i don't think we'll touch audio for a very long time it's kind of in the name too you know ink link ink

</details>

**Speaker A**: 是的。是的。嗯，为什么音频这么难？不是关于什么，再次说，这都归结于焦点。我看到……对吧，说不意味着有一个研究人员和计算资源可以取得通用进展。我们的观点是，通用进展将来自于将这些模型推向更强大的推理能力、更长的时间跨度任务的能力。我不认为音频会增加这一点。我不认为它会让我们离 AGI 更近。我认为它是接近 AGI 的一种必要的模态。我认为视觉理解处于这些事情的中间。我认为视觉理解绝对可以做到，但它也解锁了今天非常有价值的能力。所以，这就是重点，对吧？你想要更多多样性。你想要更多的基础模型公司专注于不同的事情。我认为我们只是像一个戴着盲眼的人一样……

<details>
<summary>Original English</summary>

**Speaker A**: it's kind of in the name too you know ink link ink true yeah yeah why so what's so hard about audio it's not about what's again it all comes down to focus i see right like saying no to things means that there's a researcher and compute that can go to making general progress and our view is like general progress is going to come from the ability to push these models to far more capable reasoning far more longer horizon tasks uh i don't think audio adds to that i don't think it it pushes us close to AGI i think it is a necessary modality as you get close to AGI i think visual understanding sits in the middle of those things i think visual understanding can absolutely do so but it also unlocks capabilities that are just valuable today so but this is the point right you want more diversity you want more different foundation model companies to focus on different things i think we are just kind of like a horse with blinders on just like yeah you have your path we have our path we want to catch up to the frontier and uh we don't want to distract ourselves with anything else

</details>

<!-- chunk 11/15 -->

### 关于研究方向和模型规模的讨论

**Speaker A**: 是的。我将指出研究的一个分支是深度OCR，你可以直接扔掉文本分词器，只用视觉。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Uh I will call out that one of the branches of research is deeply OCR which is can you just throw away the text tokenizer and just only vision.

</details>

**Speaker B**: 我觉得我看着这个，我觉得我有点像个技术宅，看这些东西。就像看看代码中的比特数一样。

<details>
<summary>Original English</summary>

**Speaker B**: I find this I look geek the geek in me is like looks at this stuff and it's like okay look like look at the number of bits in code.

</details>

**Speaker A**: 对。我认为这超级酷，对吧？但我认为我们最终会回到……可能工作上。它只是计算效率足够吗？我感觉所以很多这些东西最终都会奏效。你知道，文本的优点是什么？我之前提到的Peng和Nikolai，我的两位应用研究负责人，他们简直不可思议。如果没有他们，我们不可能走到今天，而Nikolai和我多年来一直在和你辩论……嗯，推理应该在潜在空间中还是在tokens中？但有一件事是我认为他和我们三个人都非常同意的是，语言是不可思议的，因为它是一种编码知识和信息以及智能的极其密集的途径。对吧？如果你想想一篇物理论文里包含了多少知识或思考量，然后生成那篇20页文档中的那些小小的比特数，那里编码了这么多东西，还有视频和图像等其他模态是惊人的，但它们没有文本那样密度……或者推理之类的我们试图推入的那些东西。在很多情况下，它们都在那里。你可以看一个50分钟的精彩讲座，你知道，在YouTube上，但如果你把那当作视频数据而不是文本数据，信号到噪声的比率、模态的计算效率会低得多。所以我们对语言的看法是你可以走得很远，但当你的计算能力有限时，你知道人们非常地联系在一起。我认为我们可以推动语言，它越好越值得投资，但我希望所有模态都存在。我发现DeepSeek和其他人正在尝试的东西超级酷，我可以一直转发他们，但内部我们只是要保持专注。

</details>

**Speaker B**: 我会说，你知道，看看Anthropic、OpenAI有很多视觉和多模态能力。嗯，Anthropic好像没有，对吧？Fable在图像处理方面是一个大进步，但他们不是那个拥有多模态能力的语言模型编码公司，那个从来都不是非常灵活的，你知道它走得很远。

<details>
<summary>Original English</summary>

**Speaker B**: which I'll say, you know, you can see somewhat works looking at anthropic. OpenAI has a lot of vision, multimodality. Um, Anthropic kind of just didn't, right? Fable's a big step up in image processing, but like they're not known as the multimodal company, right? the language model coding company that has multimodal capabilities that's never super flex and you know goes pretty far.

</details>

**Speaker A**: 我觉得Anthropic做了很多事情，对吧？但我认为这种对仅仅推动能力、扩展模型的狂热关注，我不同意。我认为这是第一个障碍，一旦我们解决了那个问题，我们就可以改进一整套其他事情。但同时在光谱的另一端，看到人们正在构建这些空间模型，它们是为非常不同的用例而构建的模型，这真的让人兴奋。但我认为最终所有东西都会在某个点汇合起来。

<details>
<summary>Original English</summary>

**Speaker A**: I look I in this I think I I think anthropic I mean they've done many things right but I think this maniacal focus on just pushing capabilities scaling up models is I couldn't agree more. Uh I think it's it's that's the first hurdle and once we get that then we can improve a whole bunch of other things. uh and but at the same time on the other end of the spectrum it's really exciting to see people you know building these spatial models right that are uh in the world models that are being built like for very different you know use cases uh but I think ultimately it all comes together at some point.

</details>

### 模型规模的命名和训练成本讨论

**Speaker B**: 好的，所以扩展模型，这是Laguna S。对于小、超小、小、中、大都有很好的命名。

<details>
<summary>Original English</summary>

**Speaker B**: okay so scaling models this is Laguna S for small you have good naming extra small small medium large

</details>

**Speaker A**: 嗯，仍然是扩展……所以新的中型模型开始训练了，它比上一个中型M昨天开始训练的要大得多。所以这是一个39天的预训练运行。你知道你如何提前知道天数？只是计算机……模型工厂。对吧？在这一点上，比如有了模型工厂，像Laguna M和超小，甚至引用GPU小时数来表示不同尺寸的天数等等，我就可以反向推算出成本是多少，对吧？多少GPU，多少小时？

<details>
<summary>Original English</summary>

**Speaker A**: um still scaling so the new medium started training and it's much bigger than the last medium M started training yesterday. Uh so it's a uh 39 day pre-training run. Uh and uh how do you know the days in advance? Just the computer >> model factory but >> right and and like at this point like with the model factory like it's >> I thought it was interesting. So in in the Laguna medium and extra small you even quoted number of GPU hours for how many days and whatever for different size and I'm like oh you can also work backwards to how much that costs right? What GPUs how many hours

</details>

**Speaker B**: 你会意识到那不是很多。不，不是。

<details>
<summary>Original English</summary>

**Speaker B**: >> and you realize it's not a lot. No, it's not.

</details>

**Speaker A**: 它不是很多钱。你知道，你从DeepSeek的West开始，我认为那个是DeepSeek时刻，对吧？人们意识到你可以用不多的钱训练出能力非常强大的模型。但我认为那是谬论，对吧？训练运行不是昂贵的部分。训练运行是一个非常令人失望的事件，对吧？比如我们昨天收到一条Slack消息说新模型正在训练，这里有链接，你知道，所以你可以跟进评估等等。就是这个时刻所付出的所有工作，就像人们常说的，我不知道体育，但运动员谈论的是……你知道，那都是准备、去健身房，然后是比赛。游戏只是一个游戏。我认为这有点像模型。

<details>
<summary>Original English</summary>

**Speaker A**: Uh, and you know, you started with Deepseek of the West and and uh I think that's uh the Deepseek moment, right, was a moment when people realize you can train incredibly capable models for not a lot of money on the training run. But I think that's the falsehood, right? Like the training run is not the expensive part. The training run is a very anticlimactic event, right? Like we just had a Slack message come up yesterday to say the new model is training and here are the links you know so you can can follow along the evals and like that's it uh all the work that goes into that moment it's kind of like how people talk I know nothing about sports but how like athletes talk about like you know it's all the preparation it's all the going to the gym and then the game is just a game I think that's a little bit like with model

</details>

**Speaker B**: 是的，人们对DeepSeek过度关注了。它训练花了500万美元或者 whatever，对吧？在那个之前，基础设施建设、数据……但不是Laguna M正在训练，是的，会有L和Excel，你会看到M比上一个M大得多。所以这些代号是我们版本的……

<details>
<summary>Original English</summary>

**Speaker B**: yeah people had overindexed on deepsek was trained for $5 million or whatever it was right it's like there's the amount of R&D before that the infrastructure is built >> up older things the data but no so Laguna M is training and yes there will be an L and there will be Excel and and what you'll see that what you'll see with M right M is much larger than the last M right so these monikers are a little bit our version of the

</details>

**Speaker A**: 他在嘲笑那些说小是24B或者什么的。不，Mistral现在已经超过100B了。

<details>
<summary>Original English</summary>

**Speaker A**: >> he was making fun of people for saying small is 24B or something >> no small small for Mistral now is over 100B

</details>

**Speaker B**: 什么？我能做到。我的小模型是118，所以我不想再说什么了。

<details>
<summary>Original English</summary>

**Speaker B**: >> what >> yeah I can pull it off >> I mean our small right is 118 so I don't want to say anything else like

</details>

**Speaker A**: 我认为你小模型也是可以的。我们都知道，任何基础模型公司最难做的一件事是命名。我不想说我们在这方面很厉害。我的意思是，这是Laguna S 2.1。但至少人们能理解，中型比小。除非你搞砸了，比如你有密码。

<details>
<summary>Original English</summary>

**Speaker A**: >> I mean I think it's also okay you're small as >> we all know that the single hardest thing for any foundation model company is naming I don't want to say that we're good at it either. I mean, it's this is Laguna, you know, Laguna S 2.1. It's it's >> But at least people understand, you know, medium is bigger than small. Until you mess that up, like you have a password.

</details>

**Speaker B**: 我们在命名这个话题上会到最后，但也许是这样。为什么叫Poolside？为什么叫Auna？当我们创立公司时，它将被称为Snowball Apps。那是雪球效应之后，因为我们预计这家公司会成为一个雪球效应，对我们来说绝对是一个雪球效应。

<details>
<summary>Original English</summary>

**Speaker B**: we try we try hard. Uh while we're on the topic of naming, this is going to be at the end, but might as well. Uh why poolside? Why Auna? So when we started the company, it was going to be called Snowball Apps. Uh it was after the snowball effect because we expected this company to become a snowball effect and it definitely has been a snowball effect for us.

</details>

**Speaker A**: 结果它是一个亚马逊商标。我跟你说，我的联合创始人下一个名字的建议是叫Bedrock。

<details>
<summary>Original English</summary>

**Speaker A**: >> turns out it's an Amazon trademark. I kid you not that my co-founder's next suggestion of a name was let's call it Bedrock.

</details>

**Speaker B**: 在这一点上，我当时是这样的，好吧，你很擅长给东西命名，如果你在亚马逊。在我们公司早期，在我们注册之前，我们在一家非常大的科技公司的年会，我们和他们讨论过，你知道，你必须意识到公司到这个点是我、我的联合创始人CEO玛格丽塔，我们知道第一个加入我们的人还没有正式注册，我们当时正在与这家大科技公司进行一个开放的AI微软风格的交易，他们将为我们提供大量的计算资源。我们会给他们，你知道，永久访问，一整套各种东西。我们在那个会议上发现名字Snow Labs在商标了，而我们当时正在讨论这个，我们没有权利拥有它，对吧？我们是那几个人，还没有什么，但这家大公司愿意考虑我们可能与他们合作的事实。我们当时正在讨论这件事，而且是在他们的年度会议上公开场合，而那家公司的首席科学家说人们可以在这里听到我们，比如我们应该去别的地方。让我们去泳池边的餐厅。因为在那个时刻我和Jason看着对方，然后说哦……后来那天晚上，名字“stuck with us”，我们就叫公司Poolside。从那时起，我们从未完成那笔交易，我们把它用作提醒我们永远不要拒绝我们的雄心，因为那样会是轻松的道路。而艰难的道路是我们所做的事情，就是当你只是几个人时，试图筹集巨额资金。

<details>
<summary>Original English</summary>

**Speaker B**: and so at this point I was like okay no you are amazing at naming things if you were at Amazon. Uh and so uh early on in the company uh before we were incorporated uh we were at an annual conference of a very big major tech company and we had been discussing with them and you have to realize the company at this point is me my co-founder CEO Margarita we know the first person is going to join us we haven't like incorporated yet uh and we were discussing an open AI Microsoft style deal with this big tech company like they were going to provide us with a lot of compute. We would give him, you know, perpetual access, a whole bunch of kind of things. And uh we found out the name was trademarked Snow Labs while we were at that conference and having this discussion that we had no right to have, right? We were a couple of guys who had nothing yet, but this big company was willing to entertain the fact that we might partner with them. And uh we were discussing this and it was in their annual conference in a public setting and the chief scientist of that company said people can hear us here like we should move somewhere else. Let's go to the restaurant poolside. And for some reason me and Jason looked at each other in that moment and said oh uh and then later that night we the name stuck with us and we said let's call the company Poolside. And ever since we never ended up doing that deal and we used it as a reminder to never turn down our round down our ambitions because that would have been the easy path. Uh and the hard path was what we did which is start and try to raise exorbitant amounts of money when you're just a couple of guys who are

</details>

<!-- chunk 12/15 -->

### 关于AGI的雄心与行业格局

**Speaker A**: 即使是那些不来自硅谷，不出身于那些著名的实验室和机构的人，他们也在构建人工智能。所以每个人都假设AGI（通用人工智能）都是在泳池边，因为“AGI”这个名字曾经是一个俏皮的名字，我们喜欢它，而且它有点不同。但实际上，这个名字提醒着我们永远不要降低我们的雄心。每当我们面对选择只走更艰难道路的时候。

<details>
<summary>Original English</summary>

not even building it in Silicon Valley who don't come from any you know the known labs and things like this. And so everyone assumes poolside because AGI everyone sits poolside and it was a playful name and we liked it and it was a little bit different but actually the name is like a reminder for us to never round down our ambitions. Uh and whenever you're faced with those decisions to just pick the harder path.

</details>

**Speaker B**: 是的。我意思是，那是一个很棒的故事。我知道你以前说过，但我只是想在记录上留下。但那是第一次见到你的时候我做的。你告诉我你让我坐下来。我们在某个酒店里，你当时说我们正在筹集5亿美元。然后你给了我整个愿景，然后你真的做到了，而我当时就觉得嗯，你知道，我没有那么多机会去问，比如，你如何能把这种规模的融资做到那些风险投资人那里？他们想要什么？是的，模糊地说是AGI，但他们想要什么呢？当这些（投资者）看的时候，世界肯定已经改变了，对吧？当我们筹集那5亿美元的那一轮时，大多数投资者的对话仍然是在试图解释这些模型不仅仅是僵硬的鹦鹉学舌，而是它们将继续前进。我看到世界从OpenAI要赢一切，而且没有人能建立公司，对吧？我的意思是，Anthropic在筹集他们5亿美元那一轮时挣扎了，你知道，这有点像……嗯，报道过。他们顺利完成了。所以我想当我们当时融资的时候，大约一年前，这个世界与今天非常不同。我认为今天这里存在一种功能，即相信AGI是真实的那些人的数量可能是一个超线性或者绝对是一种指数函数本身。而且我认为这一点很重要，因为如果你持有这种信念——三年前、一年前和半年前我们寻找那些分享这种信念的人，也就是“这项技术将从根本上支撑所有具有经济利益或在科学上有趣对未来的一切”——那么随后的价值函数就很容易理解了，这没问题，如果你达到了那个点，你就是这个商品的其中一个，是能够构建这个商品的参与者。多年来，构建这个商品不仅仅是构建模型，也是构建基础设施和其他东西。所以我想今天，因为人数更多，而且结果已经得到了证明，我认为Anthropic现在所取得的不可思议的财务成功，以及OpenAI、谷歌等其他公司的增长，不再是他们产品市场契合的问题了。几年前，那仍然是问题的一部分，比如这些东西能告诉人们多少收入数字在我们的行业里？现在人们仍然会嘲笑你。

<details>
<summary>Original English</summary>

Yeah. Uh I mean that's a great story. I I know you told it before, but I just wanted to on the record. Uh but that's that's what I did the first time I met you. You told me you sat me down. You were we were in the hotel somewhere and you were like we're raising 500 million. I'm like and then you gave me the whole vision and then you actually did it and I was like uh well you know I don't have that much opportunities to to to ask like just how do you do that kind of raise to that kind of to those kinds of VCs what are they looking for you know like yes vaguely AGI but like what do they want when these look it's the world's definitely changed right when we were raising that $500 million round the majority of investor conversations were still trying to explain that these models were not just stoastic parrots and that they were going to keep going. Uh I've seen the world go from OpenAI is going to win it all and there's no one else who can build a company, right? I mean, Anthropic struggled, you know, to raise their $500 million round. It's kind of like well reported. They pulled it off gladly. Uh and so I think when we raised that, it was about a year and a half ago at this point. The world was very different than it is today. I think the world today there's been there's been this function where the number of people who believe AGI is real uh is probably a super linear or definitely some form of an exponential function itself. M and I think this is important because if you hold the belief that we had three years ago and a year and a half ago and we looked for people who shared that belief which is like this technology is going to fundamentally underpin everything that's economically interest or economically valuable and scientifically interesting for like the future. Then the value function afterwards is easy to understand which is okay if you get there you are one of the commodity one of the players who can build this commodity. uh and over the years building that commodity has become not just about building models but also about building infrastructure and other things and so I think today because the number of people is bigger and the outcomes have been proven right I think the incredible like financial success that Anthropic is having right now and like the growth that OpenAI's had and others and Google no longer make this a question of is their product market fit uh which really a couple of years ago was like part of the question like how big can these things tell people that like you know you be up these amount of revenue numbers in our industry right now people were still like would laugh you out the room.

</details>

**Speaker B**: 嗯，我认为这取决于世界上谁相信它将成为智能的寡头垄断，以及谁相信这个寡头垄断可以被其他公司打破。我认为这才是区分那些相信人工智能的人和不相信的人之间最主要的区别。然后你又有一个层，你知道，是自我筛选出来的基础模型公司，因为他们会想说：“看，我不能在那里赚到钱，你知道，与我能投入应用公司的资金相比，非常不同。”我认为有不可思议的应用公司，应该有很多被构建，但我认为我们仍然在一个世界里，现在这只是这个可以继续成为谁将是赢得这场智能的早期阶段。在我看来，智能将是世界上需求最大的商品。它将在利润和价格上变得更加商品化。而且世界想要选择和选项。所以我认为把世界当作只有两个参与者来对待，这对投资者来说是非常短视的。我认为那个认为年初比现在大得多的群体。

<details>
<summary>Original English</summary>

uh now I think it's a function of who in the world believes that it's going to be an igopoly of intelligence and who believes that igopoly can be broken by other companies and I think that's what divides investors more than anything else for the ones who believe in AI uh and then you've got a whole layer that you know is kind of self-selecting out foundation model companies because they're like look I I can't make a the money I put there you know compared to what I can put in application companies very different I think there's incredible application companies and there should be many should be built but I do think we are still in a world right now where this is the early innings of this can still be the early innings of who is going to you know be part of the set of people who win this is intelligence is the most in my view going to be the world's most demanded commodity. It will more commoditize in margin and price. Uh and the world wants choice and wants options. And so I think treating the world as like oh there's only going to be two players I think is very shortsighted from investors. I think that group who thought that was a lot bigger at the beginning of the year than now.

</details>

**Speaker A**: 嗯，我认为在过去的几个月里，很多人被唤醒了，变得非常疯狂。你知道，世界可以利用更多的智能，但世界也复杂得多。我们应该有多种选择，更多选项，可以关闭的、不能是那种限制人们对模型的限制。现在我认为这是这个领域的一个方面，对吧？比如我们正在进入一个模型公司说你不能允许我用于基础模型开发的世界。他们应该被允许做这件事。这是资本主义。这是他们的业务。这是他们的产品。但这是疯狂的。我们竟然可以接受这样。

<details>
<summary>Original English</summary>

Mhm. I think the last couple of months have woken up a lot of people and going holy like the the world both can use a lot more intelligence but also like the world is far more complex. we should have multiple choices, more options, things that can be turned off that can't be that the restrictions that people put on models now I think is is another area of this, right? Like the fact that we are entering into a world where model companies are saying you're not allowed to use me for foundation model company development. They should be allowed to do this. It's capitalism. It's their business. It's their work product. Uh but it is insane. It is it is wild that we are like okay with that.

</details>

**Speaker B**: 你对Anthropic说的话还是对白宫说的话更感兴趣？你知道你在选择……两个不同的限制和约束。

<details>
<summary>Original English</summary>

Do do you have more problem with Anthropic saying it or the White House saying it? You know that you're picking two two different uh you know limitations and restrictions there.

</details>

**Speaker A**: 听着，我想我这样说。我认为随着这项技术变得越来越有能力，好坏都一样，我们确实想要向民主让步，去弄清楚更多。我认为任何一家公司单方面做决定都是危险的。这是权力集中在少数人手中，他们拥有非常有限的制衡手段。而且这在历史上从来没有成功过，无论以何种方式或形式。这不是对现有基础模型公司的批评。这只是关于我希望世界是怎样的更多的评论。我认为在一个技术变得越来越有能力的世界上，政府需要积极地在确定……哪里存在真正的滥用风险方面发挥作用。而且我认为我们需要将滥用与你不知道是否会发生、我们不知道的末日场景分离开来。而且我认为从非常实际的角度来看，我很高兴看到现在又开始出现更多的对话，在政府层面试图弄清楚这些问题。而现在最终的决定可能……我对此感到高兴，也许不。也许我同意，也许不。但最终，这就像民主总是这样，对吧？在任何给定时刻，我可能并不完全满意其中一个或另一个，但人们选择投票给某人来做出那些决定。所以我认为从长远来看，从二十年的时间跨度来看，世界是朝着某种方向发展的，而且民主是有效的。至少它做到了著名的那句话——它是最糟糕的组织形式，除了我们尝试过的所有其他形式。

<details>
<summary>Original English</summary>

Look I think I I I'll put it this way. I think we we want to as this technology gets more capable for the better and worse we do want to yield to democracy to figure this out more and more. I think any single company making unilateral decisions uh is is dangerous. It's a concentration of power in a small number of people with very limited checks and balances. Uh and that has never worked out well in history uh in any way, shape or form. Uh and this is not a criticism on the existing foundation model companies. This is just more commentary on like how I'd like the world to be. Uh I think in a world where the technology gets more capable, government needs to play an active role in determining you know where where is there real risks of misuse right and I do think we need to separate safety between misuse uh and you know doomsday scenarios that you know I think are no one knows if are going to happen or not. And I think just like very practically I think uh I'm glad to see there's a lot of conversation now starting to happen again at the government level of trying to figure this out. Uh and and now what the final decisions are maybe I'm happy about them, maybe I don't. Maybe I agree, maybe not. But ultimately like that's kind of democracy always, right? Like at any given moment I might not be perfectly happy with one or the other, but people chose to vote in someone to make those decisions. And so I think over the long run over you know over a 20 year time span the world kind of directionally goes correct and and democracy does work at least what's the famous quote of like it's the you know the worst of all it's the best of all the worst systems or or something like

</details>

**Speaker B**: 它是最糟糕的组织形式，除了我们尝试过的所有其他形式。

<details>
<summary>Original English</summary>

it's the worst form of uh organization except for all the others that we've tried.

</details>

**Speaker A**: 完全正确。你总可以指望我引用丘吉尔的名言，因为我研究过丘吉尔很多。我喜欢那个。所以现在我希望如此。我认为我们正处于一个关键时刻，因此对任何人发声都很重要。我认为那些正在考虑开始他们自己的基础模型公司的研究人员，会开始让人们分享他们的意见并公开表达，无论是通过他们的代表还是在X上，就像做一样。但具体到你的观点，我认为我们现在还没有达到需要限制开放模型的水平。如果我们要这样做，我认为会对创新造成伤害。

<details>
<summary>Original English</summary>

I love that. Uh and so that's what I hope for now. I do think we are in a critical moment of time and so speaking up for anyone is important. I think you know researchers who are thinking about starting their own foundation model companies start you know people who want to share their opinion and be vocal if that's with their representatives or just out on X like do so. Uh and but concretely to your point uh I think we are not at a level of capability right now that we should start restricting you know open models in any way shape or form. I think it will hurt innovation if we do so.

</details>

**Speaker B**: 有没有一个你会在某个点改变你的意见的时候？

<details>
<summary>Original English</summary>

Is there a point at which you will change your opinion there?

</details>

**Speaker A**: 是的。我的意思是，看，那里必须有一个地方。是的。对。比如，如果你面无表情地坐着说这可以永远开放，以任何方式、形状或形式。我认为正如我所同意的，说相反的话需要现在被关闭。就像我认为在光谱的两端，我们就会犯错。

<details>
<summary>Original English</summary>

Yes. I mean look and there has to be. Yeah. Right. Like you cannot if you sit with a straight face and say this can be open forever in every way, shape or form. Uh it is just as I think agreeous as saying you know the opposite of it all needs to be closed down right now. Like I think at any ends of extremes of spectrums is where we go wrong.

</details>

**Speaker B**: 对，在社会上任何方式、形状或形式。所以答案总是更细致的，而且答案永远不是非黑即白。

<details>
<summary>Original English</summary>

right and in in in society in any way, shape or form. And so the answer is always more nuanced and the answer is never black and white.

</details>

<!-- chunk 13/15 -->

### 对现实世界场景的思考与模型安全讨论

**Speaker A**: 我认为当我们遇到像现实世界这样的场景时，我们需要说“嘿，我们必须更小心”，我们需要重新评估这是否意味着以不同的方式训练一个模型，以及开放它并提供不同版本的某些东西。你可能知道有些事情是完全限制性的，没关系，因为我不认为任何人应该是不负责任的。我真正想指出的是，人们一直在呼吁对这些模型的滥用感到恐惧，从GPT-2开始，对吧？而且我仍然记得我们不能发布GPT-2，因为整个世界都会陷入混乱。

<details>
<summary>Original English</summary>

I think as we encounter like real world scenarios where we have to say hey we have to be more careful we need to reevaluate if that means training a model differently and opening it up having different versions some things that you know that are restrict totally okay because I don't think anyone should be irresponsible. What I do want to call out is that people have been calling for the fear of misuse of these models since GPT2, right? And I still remember like we cannot release GBT2 because the whole world will get misario.

</details>

**Speaker B**: 那么，这并不是对Dario的评论，而是在这个领域的一般性评论。所以到目前为止我们做得还不够好，我们需要变得更好。我认为与安全机构和更好的评估所做的工作是正确的方向。

<details>
<summary>Original English</summary>

And so like this is not a commentary on Dario, it's a commentary just in general in the space. And so we have we have not been very good at this so far and we need to get better at it. And I do think that the work that's happening with like safety institutes and better eval is probably the right direction.

</details>

**Speaker A**: 是的。我的意思是，我想为这辩护一下。从安全角度出发再逐步回滚，比另一条路好，因为另一条路是一次性的决定。

<details>
<summary>Original English</summary>

Yeah. I mean I I want to say something in defense of this. It's better to air on the side of safety and then roll it back rather than the other way because the other way it's a one one way decision.

</details>

**Speaker B**: 我认为是的，我认为那是真的。

<details>
<summary>Original English</summary>

I think I think that's I think that's true.

</details>

**Speaker A**: 但是有一个注意事项，还有竞争，对吧？你不能在安全的一边独断，对吗？你正在谈论……

<details>
<summary>Original English</summary>

the caveat there is also the competition, right? You you don't have global error on the side of safety, right? You're talking

</details>

**Speaker B**: 是的，没错。所以你不能单方面进行安全，因为别人可能会比你更不安全。

<details>
<summary>Original English</summary>

Yeah, exactly. So, you don't get to do uni unilateral safety because someone else will just be more unsafe than you.

</details>

**Speaker A**: 是的，没错。你可以暂停创新。这不意味着停滞。

<details>
<summary>Original English</summary>

Yeah, exactly. You can pause innovation here. It doesn't mean it's it's pausing.

</details>

**Speaker B**: 夺取。所以它们很复杂，对吧？

<details>
<summary>Original English</summary>

Take over. So, they're complex, right?

</details>

**Speaker A**: 我认为我们谈论某些我们可以达成共识的、在国际上达成共识的特定能力时会好得多，比如我们想限制或不限制可用的模型。然后我们应该就可用模型的黑白问题进行讨论，是还是否？就像你开始提出这些大而笼统的声明的时候，风险就开始出现了。我总是回想当我们禁止吸烟广告时。这很好。我不是说反对回去，但它实际上为烟草公司建立了一个寡头垄断，因为没人能竞争。而且那可能是烟草业发生过的最好时刻。我们现在不想做那样的事。

<details>
<summary>Original English</summary>

And and I think we are much better off talking about certain capabilities that we can you know commonly agree on and internationally agree on that we want to you know limit or not have available then we should talk about it in black and white of models available yes or no like the moment you start getting these big blanket statements it's that's when you start getting at the risk of like I always think back about when we banned advertising on cigarettes. good thing. I'm not saying I'm against back, but it effectively established an igopoly of cigarette companies because no one else could ever compete. Uh, and it was the probably the best moment to to the tobacco industry that that ever happened. And we don't want to do that right now.

</details>

**Speaker B**: 如果我们现在拉起创新之墙，这是一个自私的评论，因为我还没有到达前沿，但这不仅仅与我有关。我认为这与这个领域的每个人都有关系。你现在在2026年根据模型目前的性能做决定，而这是只有两三个公司才能构建的东西，对我来说读起来就像是我能读到的最反乌托邦科幻小说的第14章，因为从那里我以为你可以演绎世界上发生的所有场景，而且其中没有那些让我对未来感到兴奋的。我认为我们应该思考的是，我们想要什么样的未来？我们想要拥有什么？我认为那是一个智能成为一种商品、每个人都可以获取的未来。它会变得越来越便宜，对吧？这很重要。它可以影响世界上的更多方面，而它不是一个单一公司可以把自己的大拇指放在其输出规模上然后关掉或打开的地方。我认为比美国政府更有权力的实体是英伟达，因为基本上谁获得分配就获得了计算能力。你可以把它下放到台积电或者……

<details>
<summary>Original English</summary>

If we if we pull up, you know, walls behind innovation, and this is a self-serving comment because I'm not at the frontier yet, but it's not just related to me. I think it's related to everyone in the space. uh you are deciding right now in 2026 based on the current capabilities of models that this is something that only two or three companies can build and that to me reads like chapter 14 of the most dystopian sci-fi novel that I could read because from there I think you can play out all the scenarios that happen in the world and none of those are the ones that make me you know excited about the future uh and I think that's the thing we should all think about like what's the future we want to be excited about what do we want to have and I think that's a future where intelligence is a commodity, everyone can access it. It becomes cheaper and cheaper, right? And I think that's important. It can like impact more of the world and it's not one where, you know, a single company puts their thumb on their scale of what it outputs uh to or turns it on or off. I think the one entity that has more power than the US government here is Nvidia because like basically whoever gets the allocations gets the compute. You can take it down to TSMC or

</details>

**Speaker B**: 台积电以下。但我只是想测试一些挑衅性的言论，看看你有没有回应。

<details>
<summary>Original English</summary>

>> TSMC below that. But I I just want to test provocative statements to see if you you have any response.

</details>

**Speaker A**: 我需要思考一下那个……实际上我认为它们是受监管的，对吧？你可以看到政府……

<details>
<summary>Original English</summary>

>> I need to think on that one >> which actually I think they are regulated, right? Like you can see the government

</details>

**Speaker B**: 他们能运到中国吗？

<details>
<summary>Original English</summary>

>> Can they ship to China?

</details>

**Speaker A**: 好的。但你知道，他们不是中国。

<details>
<summary>Original English</summary>

>> Okay. But you know they're not China.

</details>

**Speaker B**: 看，我认为这个行业之所以存在是因为英伟达所做的事情。

<details>
<summary>Original English</summary>

>> Look, I think this industry has existed because of what Nvidia has done.

</details>

**Speaker A**: 是的。对。我知道我们这些人喜欢给它指责，但我还想说，我记得当我们开始在2015年之后，Kapathy的文章发布后，由于我们能够将消费级GPU放入服务器中，这使得这种进步成为可能，他们允许我们这样做，然后你继续前进，所以基础模型与它们的硬件和系统是如此紧密地联系在一起。为什么我们会看到这种逐步的进步？我们看到它们发生是因为下一代网络和系统会推出，对吧？你可以用Hoppers训练的模型和GB300的区别在于一个万亿参数模型和一个五或六万亿参数模型的区别。所以这些东西确实是密切共存的。我认为对于未来来说，更有趣的问题将是如何随着我们开始更加共同设计这些东西，我们可以解锁哪些模型能力，就像我们看到下一代系统一样。而且我认为世界……你懂的，世界厌恶资本主义，它在试图推动那些允许更多竞争的东西方面做得很好，对吧？而英伟达允许竞争。不是，你知道，但如果政府说其他人无法通过监管有效地构建基础模型，那是非常不同的。要建立一个英伟达吗？绝对很难。建立一个基础模型难吗？我认为建立一个基础模型非常困难。但我们应该让游戏场地成为一个，如果你明天醒来想做某事，他们是允许你做的，并且被允许使用工具去做。我认为在模型公司和芯片公司方面，我们看到的仍然存在很大区别。

<details>
<summary>Original English</summary>

>> Yeah. >> Right. I know that we people like it's easy to give him flack, but I also want to say like I remember when we started sourced right in in and in in 2015 post that Kapathy article it was able for this progress to happen because we're able to put consumer GPUs in servers and they allowed us to do so and then like and you kept going further and so this is something like foundation models are so closely linked to their hardware and their systems. Why do we see these step-wise progress happening? And we see them happening because of the next generation of networking and and systems that come out, right? The difference of a model you could train on hoppers versus GB300's is the difference between a trillion parameter model and a five or six trillion parameter model. And so these things really coexist I think very closely to each other. And I think the more interesting question I think for for the future is going to become of like how do we what can we unlock in terms of model capabilities like as we start co-designing these things even more and we're seeing that with like the next generation of systems and I think the world the world you know abhores like capitalism does a really good job at trying to like you know push towards things that are that allow for more competition, right? And and Nvidia allows for competition. It's not, you know, but if a government says no one else can build foundation models effectively through the regulation, that is very different. Is it hard to go build an Nvidia? Absolutely. Is it hard to build a foundation model? I think it's very hard to build a foundation model. But we should like make the playing field one that where you know if someone wakes up tomorrow and wants to do so they're like allowed to do so they're allowed to use the tools to do so. And I think there's still a big difference between what we're seeing in the discussions about model companies versus what we're seeing with chip companies.

</details>

**Speaker B**: 差距似乎在于谁来监管它，对吧？政府在决定什么太安全、太聪明、太危险。嗯，但当我们抛出这些尖锐的问题时，你有什么想改变的吗？所以你知道，是否应该开放AI、开源模型是开放权重？这与我们在强化学习中确定的你的安全屏障有关吗？有没有什么应该做的事情？

<details>
<summary>Original English</summary>

>> The gap also seems to be the expertise in who regulates it, right? Who at the government decides what's too safe, too smart, too dangerous. Um but while we're throwing spicy questions out there um do you have anything that comes to top of mind that could be changed? So you know should open AI anthropic open source models is it open weights? Is it what we do in RL that determines you know your safety barriers? Is there anything that should be done there?

</details>

**Speaker A**: 嗯，是的。我兴奋的一件事是我想我们正在越来越多地谈论它。我不认为现在有人在做硬件的混合训练，对吧？就像你考虑那个概念，我们正在推理中看到这个，对吧？预填充和解码。是的。嗯，只是更好地与通用GPU以及更专业化的芯片一起工作，对吧？比如英伟达的Grock芯片、LPU和GPU的结合，行业中有不同版本的这些东西，而且强化学习是批次大小的约束，对吧？所以你最终是由于批次大小的限制，因为你没有无限的任务，对吧？当你拥有整个网络时，你可以更灵活地扩展你的批次大小，因为你拥有整个网络。但对于强化学习来说，你有……你知道，会有数百万个任务你要训练。所以你不能大规模增加你的批次大小，这意味着你实际上无法以某种方式通过强化学习来扩展计算能力，就像你可以在预训练时那样扩展计算能力一样。所以我对任何能改进这方面的事情都感到非常兴奋。我认为开始改进它的一个最佳方法是我们在推理中已经开始看到的那些事情，即预填充和解码与不同芯片的分离，以实现强化学习，对吧？我想我们很快就会在那里。嗯，我认为更多的人应该致力于这个工作。因为那样我们就能在单位时间内更有效地训练我们的LLM。再次回到事实，这是一场竞赛，对吧？这场竞赛不是以GPU的数量来衡量的，而是以日历时间来衡量的，这可能是我们现在能为加速我们行业带来的最大影响之一。所以这是我喜欢钻研技术并与人们交谈的一点。

<details>
<summary>Original English</summary>

>> um yes. Um one of the things that I'm excited about that I think we're more and more talking about I don't think anyone is doing yet is uh mix and match of hardware during RL training, right? Like the you think about like the notion and we're seeing this in inference, right? The prefill and decode. Yeah. uh just work better with, you know, a general purpose uh a GPU and and a more specialized like chip, right? Like the Grock chip at Nvidia, the LPU and the GPU combined and there's different versions of that in the industry and and RL is batch size constraint, right? So like you are ultimately and you're batch size constraint because you don't have infinite tasks, right? When you've got the entire web, you can be much more flexible in scaling up your batch size because you've got the entire web. But for RL, you have, you know, x millions of tasks that you are going to be training on. And so you cannot blow up your batch size massively, which means that you actually can't scale compute to a certain extent with RL the same way you could scale compute with like pre-training. Uh, and so I'm very excited about anything that improves that. And I think one of the best ways to start improving that is the things that we're already starting to see in inference, which is the separation of the the prefill and decode to different chips to come to reinforcement learning, right? Uh and I think we'll be there soon. Um and I think more people should be working on this. Uh because then all of a sudden we're able to just be way more efficient in how we train our LLM from a wall clock time. Again, coming back down to the fact that it's a race, right? the race is measured not in how many GPUs, but the race is measured on on calendar time and that's probably one of the biggest impacts we can have right now to speed up our industry. Uh and so that's one like technically I love geeking out about and talking to people.

</details>

<!-- chunk 14/15 -->

### 数据中心与模型训练的对比及研究方向

**Speaker A**: 我参观了他们的数据中心，亲眼可以看到 PD 分离是如何在数据中心中映射出来的，而且你必须拥有自己的硬件才能完成那件事。

<details>
<summary>Original English</summary>

**Speaker A**: I had a tour of their data center and um physically you can see how PD disaggregation is mapped out in the in the data center and you have to own your own hardware to do that.

</details>

**Speaker B**: 是的。不，听着，我认为空间上的创新才是最酷的事情。而且我很高兴，因为坦率地说，我们所有人都想知道为什么我们在发布模型之前两周、或者没有发布之后、预训练、然后是 SFT（监督微调），再到发布之间需要这么长时间。我的最大瓶颈现在是 RL 时间，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. No, look, I think it's I think more innovation in space is just like is the coolest thing. Uh and uh and so I'm I'm excited because that's frankly like all of us are like why why did we finish you know post-training this model whatever two weeks before release or no sorry between release between pre-training then you know mid-training SFT and then the time it takes for release. My biggest wall clock bottleneck right now is RL time, right?

</details>

**Speaker A**: 而且我不能进一步扩展它，因为由于那个糟糕的尺寸限制，我无法添加更多的 GPU。有一篇非常酷的博客文章出来，展示了在比我们任何人都低精度的情况下完成 RL 的工作。我当时觉得这真的很酷。所以今天是什么日期？今天是 7 月 15 日。所以这发布了五天前。而且我觉得这非常酷。呃，我想你知道，在保持稳定性的情况下进行低精度 RL，我们仍然在 FP8 中做这件事，所以我很兴奋看到他们分享这项工作并把它推出来。一旦我们转向 Blackwell GPU，这绝对是我很期待做的事情。

<details>
<summary>Original English</summary>

**Speaker A**: And it's just because I can't scale it up further because I can't add more GPUs to it because of that bad size constraint. There's a really cool uh blog post that just came out that was showing uh RL done in even lower precision than any of us are doing. I thought this was really cool. So this what date is it today? We're on July 15. So this came out 5 days ago. Uh and I thought this was very cool. uh I think you know lower precision RL while keeping it stable we're we're still doing this in FP8 and so uh I was excited to see them sharing this work and and bringing it out uh it's definitely something that I'm excited to be doing once we move to uh to Blackwell GPUs

</details>

**Speaker B**: 但是的，开放研究的一部分就是你获取和给予。

<details>
<summary>Original English</summary>

**Speaker B**: but yeah cool part of open research you know you you take and you give

</details>

**Speaker A**: 没错。我只是快速提一下，有一篇论文基于量化级别做了一个研究，他们大致得出结论说 4 位是最佳选择。

<details>
<summary>Original English</summary>

**Speaker A**: exactly yeah I'll just quickly mention there was a paper that did a basion on uh levels of quantization and they roughly concluded that 4bit was the sweet spot.

</details>

**Speaker B**: 但我不记得这是几年前的事了，对吧？我想我记得是今年。

<details>
<summary>Original English</summary>

**Speaker B**: But I don't remember this was a couple of years ago, right? I think I remember this year

</details>

**Speaker A**: 一年才出来。但就像，我感觉 NV FP4 也许就是它了。你不可能达到最低的，那只能是三进制。就这样。不是那么多。

<details>
<summary>Original English</summary>

**Speaker A**: one year came out. But like I'm like, okay, maybe NV FP4 is it. You can't really like the the lowest you can go is turnary. That's it. Like there's not that many.

</details>

**Speaker B**: 嗯，我的意思是，NVFP4 和 4 位在可行的方面仍然存在相当大的差异，对吧？但我想 NVFP4 在其潜力方面是低估的。我很高兴它出来的时候，你只是获得了那种额外的权衡——比如范围上的权衡。

<details>
<summary>Original English</summary>

**Speaker B**: Well, I mean there's there's still quite a difference between NVFP4 and 4bit, right? In terms of what's what's possible, but I think NVFP4 is, you know, underrated in terms of of what it is. I'm I'm quite excited that when it came out uh it's uh you know just getting that extra like that trade-off between uh between range u yeah

</details>

**Speaker A**: 这非常酷。

<details>
<summary>Original English</summary>

**Speaker A**: is very cool.

</details>

**Speaker B**: 呃，几个收尾问题。我有一个快速问题。

<details>
<summary>Original English</summary>

**Speaker B**: Uh couple closing questions. I have a quick question.

</details>

**Speaker A**: 好，一个快速问题回到技术层面。关于 XS 2.1 从中训练新的小型模型，在训练模型方面有什么主要的收获吗？你在早些时候的讨论中提到了很多，关于预训练，你可以榨取很多东西，对吧？你可以在同一时间从网络中学到更多东西，同时你将 30B 扩展到 120B。所以对于模型有多小有门槛吗？我只是会唠叨一会儿，最后我会问一个问题，但卡拉普蒂（Karpathy）的论点的一部分是认知核心，对吧？我们看到了 Vibe Thinker、Nan Beads、3B、4Bs 等，这解释了很多东西。然后你知道，这个想法是你可以将工作卸载到另一个模型上，因为这些是小型推理模型，你是否在设备上的 20、30B 模型或单 GPU 100B 模型中找到了任何有趣的发现？你能榨取更多吗？有很多可以榨取的东西。我可能不会做出太多前瞻性的承诺，但我认为我们可以在超出的尺寸上榨取更多东西。而且我认为我们在训练过程中学到了一些东西，这将使我们能够进一步改进超出的尺寸。而且我想从那时起我们就学到了本可以让 S 变得更好的事情。我认为我们还有很多空间来榨取更小的模型。我不认为这是反对扩展它的论点，这只是一个呃。而且从某种意义上说，我​​认为为较小的模型有一个后训练配方并试图将其应用于更大的模型并不太有帮助。

<details>
<summary>Original English</summary>

**Speaker A**: Okay quick question back to technical side. So any big takeaways from XS 2.1 medium to training the new small just general in terms of training models. You mentioned a lot in the earlier discussion about okay in pre-training there's a lot you can squeeze out right you can learn a lot more from the web um at the same time you took 30b and scaled it up to 120B right um is there any gating on how small is too small so I'm I'm just going to ramble for a bit I'll come to a question at the end but you know part of Karpathy's thesis was cognitive core right we've seen vibe thinker nan beads 3b 4bs that reason a lot and then you know the idea is you offload to a different model for the work this these are small reasoning models so have you found anything interesting in model sizes like 20 30bs on device 100bs on single GPU um can you squeeze out more there's a lot more to squeeze out uh like I think not to make too many forward promises but I think we can squeeze a lot more out of the excess size as well uh and I think we learned learned a lot during s training that will allow us to improve excess like size even further and I think already since then we have learned things that could have made s even better uh I think there is a lot more still for like our our space to squeeze out of models much smaller u I don't think that's an argument against scaling it's just an uh and one by the way I think this is a nice thing that you know it's really it's not very helpful to have a post-training recipe for a smaller model and try to apply it to a bigger model

</details>

**Speaker B**: 是的，在所有情况下，你都将不得不重新思考大部分配方。但对于一个应用于更小模型的后训练配方来说，几乎总是很好的改进和基线。你仍然可以进一步调整它。但我认为这不一定很明显。而且一旦你让你的更大模型变得更好，你通常会有一个快速的杠杆来再次改进你的小型模型。但是我们能从较小的模型中榨取更多东西吗？Laguna 给了我很多信心，我认为我们可以做到。而且我认为这与我们之前讨论的那部分有关，即它关乎行为，而不是你试图改进的模型本身的原始智能。在所有轴上都有这样的事情，比如模型推理多长时间。所以它可以保持多久，还有效率，对吧？理想情况下，你想同时推动两者。而你们现在澄清的事情是，你们正在做的是什么？我们在前沿实验室（Frontier Labs）看到的通常是蒸馏，对吧？你有一个大型模型你并不真正发布给用户，而你为推理提供的内容通常是从那个模型中蒸馏出来的，这会给你带来一些收益，对吧？听着，我认为我们现在不这样做，因为……为什么我们也在构建这些模型呢？这些模型是我们研究路径的一部分。所以，你知道，Laguna Medium 比最近发布的这两个模型和最后一个模型要大得多。而且我们在过去训练过更大的模型。所以，一个更大模型的工程组成部分在任何数量级的尺寸上，你都会在预训练中学习到关于稳定性的新东西。但在较小的模型尺寸上，你可以更快地在内部迭代你的研究。因此，对于我们蒸馏到一个更小的模型来说，这实际上没有起到作用。这些模型有点……不是正确的术语，但对我们来说它们是双用途模型。它们是我们改进模型工厂的进步，也是可以发布到世界上的东西。所以这就是为什么我们不这样做。我们做过蒸馏实验，你可以做一些非常酷的事情，而且我认为如果你有大量的用户数据，那么你可以在其中做得更进一步，但我想在从头开始训练一系列快速的模型方面有一些值得说的话，这样作为一个研究组织，你可以学习经验而不是等待。这实际上是我们多年来学到的一个大经验，当我们以前模型训练之间的周期要长得多时，比如六个月，我们只会训练一个大模型，等六个月再训练另一个更大的模型，你会积累太多变化和改进，到你训练下一个模型时，它就像一锅汤，你真的不知道是什么成分导致了结果。所以当你更频繁地训练模型时，这对于后训练和从头开始预训练都成立，你将更有能力了解是什么导致了改进，我认为这很重要。最终我们仍然没有深度学习的真正科学，你知道大型语言模型的，但我们都在试图从我们的实验中获得见解，因为正是这些见解带来了可扩展性定律，而可扩展性定律带来了使我们更计算高效并获得更多能力的改进。

<details>
<summary>Original English</summary>

**Speaker B**: but um recipe for post training for a bigger model applied to a smaller model is almost always just a really good like improvement and and baseline. You can still tweak it more. Uh but I don't think that's necessarily like obvious. Uh and uh and so you once you make your bigger models better, you often have a a quick lever to quickly improve your smaller models again. Uh but will we be able to squeeze a lot more out of smaller models? Laguna S gave me a lot of confidence that I think we can. Uh and I think it's around that discussion we had earlier about that it's about the behaviors, not necessarily the raw intelligence uh that you're trying to improve the models for. And that's on all axes of uh there's like an axis of how long a model will reason. So how long can it stayic and there's also efficiency, right? You want to ideally push on both. And the the thing to clarify you guys aren't doing right now which we do see at Frontier Labs is the distillation, right? You have a big big model that you don't really ship to users and what you put out for inference is typically distilled from that which gets you quite a bit of gains, right? Look, I think it's it's something we don't do right now because of like why we're also like building these models, right? These models are for us part of our research path. So, we've you know, Laguna Medium was much larger than the last two models that this one and last one that we've released. Uh and we've trained even bigger models in the past. So, there is the engineering component of like a bigger model and at every kind of order of magnitude size, you'll learn new things in pre-training about stability. But at smaller model sizes you are able to just iterate a lot quicker like internally right on your research. And so uh for us distilling down to a smaller model doesn't actually serve the purpose. These models are kind of it's not the right term but to us they're dualpurpose models. They are progress for us to wait to see did we improve in the model factory and something to put out into the world. Uh and so that's why we don't do it. We've done distillation experiments and there's like really cool things you can do and I think if you have lots of user data uh then uh you can go even further right uh in that but I think there's something to be said in having a a quick cadence of models trained end to end from scratch so that you as a research organization can learn the lessons and not wait. That was actually one of the big lessons we learned over the years when we used to have a much longer cadence between model trainings like six months and we would train just like a big big model, wait six months train another bigger model uh you would be compounding so many changes of improvements that at the by the time you're training your next model it's a bit of a soup and you don't really know what ingredients led to the outcomes. So when you are training far more frequently models uh and this holds true for both post-training uh and from pre-training from scratch you are much more able to get an understanding of what led to the improvements uh and I think that's important like ultimately we are all still there is no true science yet of you know deep learning for large language models uh but we are all I think you know trying to gain insights from our experiments because it's those insights that lead to scaling laws that lead to the kind of improvements that allow us to be more compute efficient and get more capabilities.

</details>

**Speaker A**: 是的。嗯，很棒。我本来想用一点历史来结束。你花了一些时间研究工程团队生产力的指标。你对今天的工程团队生产力怎么看？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Um, amazing. I was going to end off with a little bit more history. Uh, you spent some time looking at uh metrics for engineering team productivity. How do you think about engineering team productivity today?

</details>

**Speaker B**: 我的意思是，这太疯狂了，对吧？我的意思是，这是黄金时代。比如，你可以只是拿一个想法，通过等待一个代理完成工作来构建它。我不知道。对我来说……

<details>
<summary>Original English</summary>

**Speaker B**: I mean, it's wild, right? I mean, it's the it's like the golden age. Like, it's the fact that you can just take an idea and build something by waiting overnight for an agent to do the work. I don't know. to me

</details>

**Speaker A**: 你怎么衡量？因为字面上，你看起来……我想这是一个好问题，是我很久没有想过的问题。但你知道，你很有资格去做它。我将不……这公平一点的点，让我花点时间思考一下。从根本上说，代码是什么？

<details>
<summary>Original English</summary>

**Speaker A**: like how do you measure on you know because literally in a you look I think it's a good question it's one I haven't thought about in a long time uh but you know you're you're pretty qualified to do it I'm going to no it's a fair point let me take a second to think about it look ultimately what is code what is

</details>

<!-- chunk 15/15 -->

### 软件工程的本质与迭代周期

**Speaker A**: software engineering is to go from something that is valuable for an end user or sets of end users uh like an idea an extra bug fix a feature to like delivering that value. And I think what we're doing with these models becoming more capable is that we are massively like both cutting out middlemen and compressing the time that it takes to deliver that value. And ultimately that iteration cycle for any startup or any company is what allows you to win, right? if you're able to solve a bug in two hours versus in staying in the backwalk for three weeks. If you're able to like be on a customer call and learn, hey, if this feature existed, it would like, you know, they'll be willing to pay more and it's more valuable to them and you ship it in a week instead of in a month. And so I think ultimately maybe the same things that we looked at years ago preLM still apply. And it's just the notion of cycle time, but in this case, it's the lead time from the moment you have a valuable thing that you're looking to do for someone to the moment that it's actually shipped to them. Every other metric is ultimately a leading indicator for that lagging indicator, right? It doesn't matter if you're looking at amounts of code, PR, reviews, all of these kind of things. And so I think in this case we are starting to move so quickly in some of these things that we can just sit back and look at what was traditionally the lagging indicator which is the lead time from contrition ticket to like you know like an end result. Um what I would look at in this new world uh that maybe we didn't think about before is how much can a single person do with that. Right? One of the most like if you look at AI native companies they're not designed like the engineering orgs of you know pedalm age. They're actually designed with often just the builder, right? Uh and as close to the kind of customer to the ability to ship. Uh there isn't necessarily a huge team in between that sits there. And I think that is I think is exciting like organizations where a single IC can just you know get much closer to that. So I would look at from where the value sits that's identified to the moment it's shipped and how many people are involved in that and you want the amount of people involved in that to be less and you want the time end to end to be shorter.

<details>
<summary>Original English</summary>

software engineering is to go from something that is valuable for an end user or sets of end users uh like an idea an extra bug fix a feature to like delivering that value. And I think what we're doing with these models becoming more capable is that we are massively like both cutting out middlemen and compressing the time that it takes to deliver that value. And ultimately that iteration cycle for any startup or any company is what allows you to win, right? if you're able to solve a bug in two hours versus in staying in the backwalk for three weeks. If you're able to like be on a customer call and learn, hey, if this feature existed, it would like, you know, they'll be willing to pay more and it's more valuable to them and you ship it in a week instead of in a month. And so I think ultimately maybe the same things that we looked at years ago preLM still apply. And it's just the notion of cycle time, but in this case, it's the lead time from the moment you have a valuable thing that you're looking to do for someone to the moment that it's actually shipped to them. Every other metric is ultimately a leading indicator for that lagging indicator, right? It doesn't matter if you're looking at amounts of code, PR, reviews, all of these kind of things. And so I think in this case we are starting to move so quickly in some of these things that we can just sit back and look at what was traditionally the lagging indicator which is the lead time from contrition ticket to like you know like an end result. Um what I would look at in this new world uh that maybe we didn't think about before is how much can a single person do with that. Right? One of the most like if you look at AI native companies they're not designed like the engineering orgs of you know pedalm age. They're actually designed with often just the builder, right? Uh and as close to the kind of customer to the ability to ship. Uh there isn't necessarily a huge team in between that sits there. And I think that is I think is exciting like organizations where a single IC can just you know get much closer to that. So I would look at from where the value sits that's identified to the moment it's shipped and how many people are involved in that and you want the amount of people involved in that to be less and you want the time end to end to be shorter.
</details>

### 评估人才与代理能力

**Speaker A**: Okay. Um, is there a way to eval when you're interviewing somebody?

<details>
<summary>Original English</summary>

Okay. Um, is there a way to eval when you're interviewing somebody?
</details>

**Speaker B**: O uh because that is you know I look the most compressed version I think the the common answer to this is agency.

<details>
<summary>Original English</summary>

O uh because that is you know I look the most compressed version I think the the common answer to this is agency.
</details>

**Speaker A**: Yeah. How much agency does a person have? Uh, I think in the age of AI getting more capable, agency becomes probably one of the most important qualities for anyone. And I think agency is something you can look for in you know what people have done in the past because agency is something that if you have it, you are demonstrating it right. No one has just agency and is sitting back and not like exercising it. The whole definition of it is that it's exercised. And so understanding like what were things that people did in their lives in their professional and their personal project that showed agency and your personal backstory shows a ridiculous amount of agency right like I think that is ultimately it it's the you know the Silicon Valley you know quote of the last you know year and a half or so it's like you can just do things right that's I think what you're looking for.

<details>
<summary>Original English</summary>

Yeah. How much agency does a person have? Uh, I think in the age of AI getting more capable, agency becomes probably one of the most important qualities for anyone. And I think agency is something you can look for in you know what people have done in the past because agency is something that if you have it, you are demonstrating it right. No one has just agency and is sitting back and not like exercising it. The whole definition of it is that it's exercised. And so understanding like what were things that people did in their lives in their professional and their personal project that showed agency and your personal backstory shows a ridiculous amount of agency right like I think that is ultimately it it's the you know the Silicon Valley you know quote of the last you know year and a half or so it's like you can just do things right that's I think what you're looking for.
</details>

**Speaker A**: I think then aligning high agency people is very hard because they all want to go their own way that's the whole point right? Yeah, but I think the notion like I think the notion of a good leader, right, in an organization is to be able to bring people together around like a common outcome. And I think what you want to do with anyone who's high agency, I feel very lucky I've got an organization with incredibly high agency people. Like I mean I'm not the one who built the model, right? I cannot stress this enough. Like it's the team that like achieved this and it's a team that is incredibly high agency. And so if you look at like what does it take to bring that together it's it's ultimately a common goal and a common set of boundaries because if you allow to just go you can do everything you become an exploration algorithm and this is what we see in big tech right in research and big tech everything is an exploration algorithm everyone can do anything as long as and then becomes political about gathering the resources so when you say this is our common goal and these are the boundaries that we've set right we're not multimmodal we focus on RL like we do these things and you're upfront with people before they join the company, you know, like you get a lot of agency. You can run where you want, but these are these are the places where we say this doesn't this are the lanes that make sense.

<details>
<summary>Original English</summary>

I think then aligning high agency people is very hard because they all want to go their own way that's the whole point right? Yeah, but I think the notion like I think the notion of a good leader, right, in an organization is to be able to bring people together around like a common outcome. And I think what you want to do with anyone who's high agency, I feel very lucky I've got an organization with incredibly high agency people. Like I mean I'm not the one who built the model, right? I cannot stress this enough. Like it's the team that like achieved this and it's a team that is incredibly high agency. And so if you look at like what does it take to bring that together it's it's ultimately a common goal and a common set of boundaries because if you allow to just go you can do everything you become an exploration algorithm and this is what we see in big tech right in research and big tech everything is an exploration algorithm everyone can do anything as long as and then becomes political about gathering the resources so when you say this is our common goal and these are the boundaries that we've set right we're not multimmodal we focus on RL like we do these things and you're upfront with people before they join the company, you know, like you get a lot of agency. You can run where you want, but these are these are the places where we say this doesn't this are the lanes that make sense.
</details>

### 创新源于约束与影响力

**Speaker A**: I think it actually gets the best out of people because like innovation comes from constraints. We did this with relatively little computer and relatively little money compared to some of like you know the others that are out there. uh and I've thought back on that quite a bit recently and thought actually it was a good thing because those constraints kind of forced us to become much better in certain other axis that might others might have not right we uh we purchased relatively little external data uh I was going to ask about that

<details>
<summary>Original English</summary>

I think it actually gets the best out of people because like innovation comes from constraints. We did this with relatively little computer and relatively little money compared to some of like you know the others that are out there. uh and I've thought back on that quite a bit recently and thought actually it was a good thing because those constraints kind of forced us to become much better in certain other axis that might others might have not right we uh we purchased relatively little external data uh I was going to ask about that
</details>

**Speaker B**: exactly right that was a constraint but it's a constraint that pushed us to move on other areas to improve and like and there's lots of versions of that so I think high agency people you want to empower you want to get them really excited what they're doing but you also want to say hey if you join this mission this is the outcome I need you to achieve but these are the places that we don't go and maybe if you care about those places go somewhere else.

<details>
<summary>Original English</summary>

exactly right that was a constraint but it's a constraint that pushed us to move on other areas to improve and like and there's lots of versions of that so I think high agency people you want to empower you want to get them really excited what they're doing but you also want to say hey if you join this mission this is the outcome I need you to achieve but these are the places that we don't go and maybe if you care about those places go somewhere else.
</details>

**Speaker A**: yeah, great um call to action who are you hiring?

<details>
<summary>Original English</summary>

yeah, great um call to action who are you hiring?
</details>

**Speaker B**: we are hiring on every possible role in applied research and engineering in the company uh so from pre-training all the way to eval to post-training architecture like we are still in a world where you know individuals can have massive impact and I think our pitch to join us it's we spoke a lot about the mission how we think about things but I think we are one of the places where it's the highest ratio to individual to impact right less than 70 people built this model less than 150 to engineering and researchers like together did this effort and that's a very broad definition because I put myself in the 115 list and so being able to do this kind of work on a mission that you're aligned with uh and you can have that in every individual still has a huge impact.

<details>
<summary>Original English</summary>

we are hiring on every possible role in applied research and engineering in the company uh so from pre-training all the way to eval to post-training architecture like we are still in a world where you know individuals can have massive impact and I think our pitch to join us it's we spoke a lot about the mission how we think about things but I think we are one of the places where it's the highest ratio to individual to impact right less than 70 people built this model less than 150 to engineering and researchers like together did this effort and that's a very broad definition because I put myself in the 115 list and so being able to do this kind of work on a mission that you're aligned with uh and you can have that in every individual still has a huge impact.
</details>

**Speaker A**: and being able to publish being able to open source the model. Yeah, look at all of those things are are part of that, but I think ultimately uh when you you can today pick between joining a very large foundation model company and but you are one of many uh and not by any fault of them but just by definition the denominator has become really big and our denominator is quite small and so the level of impact you get to have is really high and I think ultimately all of us frankly the most incredible high agency people I know what are they optimizing for they're optimizing for impact uh they're optimizing for impact and am I aligned with the mission and and if today you heard about the mission and aligned and you're optimizing for impact I think we're a really good place to try.

<details>
<summary>Original English</summary>

and being able to publish being able to open source the model. Yeah, look at all of those things are are part of that, but I think ultimately uh when you you can today pick between joining a very large foundation model company and but you are one of many uh and not by any fault of them but just by definition the denominator has become really big and our denominator is quite small and so the level of impact you get to have is really high and I think ultimately all of us frankly the most incredible high agency people I know what are they optimizing for they're optimizing for impact uh they're optimizing for impact and am I aligned with the mission and and if today you heard about the mission and aligned and you're optimizing for impact I think we're a really good place to try.
</details>

**Speaker A**: okay, I think we ended there was fantastic uh statement you did amazing on 4 hours of sleep uh you guys so you know podcast eval definitely appreciated I literally like my eyes are like starting to go like this I'm like let you go let you go back to thank you for setting this Uh we wanted to get this in because we think it's a great model and I think it's a great story to tell.

<details>
<summary>Original English</summary>

okay, I think we ended there was fantastic uh statement you did amazing on 4 hours of sleep uh you guys so you know podcast eval definitely appreciated I literally like my eyes are like starting to go like this I'm like let you go let you go back to thank you for setting this Uh we wanted to get this in because we think it's a great model and I think it's a great story to tell.
</details>

**Speaker B**: Thank you.

<details>
<summary>Original English</summary>

Thank you.
</details>