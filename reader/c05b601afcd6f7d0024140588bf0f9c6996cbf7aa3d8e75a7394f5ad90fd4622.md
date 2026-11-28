---
author: AI Engineer
date: '2026-07-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=htM02KMNZnk
speaker: AI Engineer
tags:
  - loop-craft
  - agentic-workflow
  - vertical-track
  - recursive-improvement
title: AI工程师世界博览会：从循环到软件工厂的工程实践
summary: 文章回顾了AI工程师世界博览会的盛况，核心探讨了构建“软件工厂”的概念。演讲深入分析了工程师在不同抽象层级（循环）上的工作方式，以及如何通过人类心跳、学习工具、协作等过程来定义和提升生产力。同时，文章也讨论了垂直领域专场的扩展趋势、基础设施的资源分配策略，以及模型递归式自我改进等前沿技术方向。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/54 -->

### 开场致辞：AI工程师世界博览会开幕

**Speaker 4**: 女士们先生们，欢迎来到AI工程师世界博览会。我们非常激动地开启这令人难以置信的几天，其中包括鼓舞人心的主题演讲、技术见解以及与AI社区领袖们的对话。请大家和我一起欢迎AI工程师联合创始人兼Latent Space编辑——Sweex。

<details>
<summary>Original English</summary>

**Speaker 4**: ladies and gentlemen, welcome to the AI engineer worlds fair. we're excited to kick off an incredible few days of inspiring keynotes technical insights and conversations with leaders across the AI community. please join me in welcoming co founder of AI engineer and editor at late space sweex.

</details>

**Speaker 0**: 哇哦。

<details>
<summary>Original English</summary>

**Speaker 0**: 哇哦.

</details>

**Speaker 5**: 嗨，你们都在啊。我们切换到幻灯片吧。我很荣幸欢迎大家来到——基本上是我们有史以来最大规模的工程师聚会。我觉得聊聊我们今天聚在这里做什么是件有趣的事。所以，嗯，我希望幻灯片已经准备好了，我可以看看我的幻灯片是不是正常。我们得确保这个设置是对的。一开始，是token。然后是聊天。然后我们学会了使用工具。然后我们学会了循环。我跳过了一些步骤。而如今，我们都在做自动化。我们都在做Cron任务、运维等等。在今天这场讲座中，还有那些在家观看的朋友们，我们也会讨论软件工厂。所以有很多循环堆叠。我写了这个叫“循环工艺”的东西。我想昨天有观众在印度做了一个工作坊。请确认还能听到我说话，那就好。抱歉，我的麦克风滑了一下。

<details>
<summary>Original English</summary>

**Speaker 5**: hi, you're there. let's switch to slides, and i'm going to kick off this this stage. i'm hononred to welcome all of you um to basically the biggest gathering of the engineer we've ever had. i think it's interesting to talk and think about what we all doing here today. so um i hope that we have the slides up, i can actually see whether if make sure my styts are up. we do need to make sure this the sic right cool in the beginning. there was the token. then there was the chat, then we learn to use tools. then we learn to cycles. i'm skipping a few steps. and these days. we're all of our automations. we're all about chrome jobs and the ops and the rest today on this lexurship, the those of you watching at home, we're going to be talking about software factories as well. so there's a lot of loopp stacking. i wrote this sa of loopcraft. i think johin the audience did a workshop on india yesterday. please still hear me that we good. sorry. i had a mike slip.

</details>

**Speaker 5**: 嗯，我认为这基本上就是工程师的规模——定义你正在工作的循环，并弄清楚那是否是合适的抽象层级。当你准备好了，就向上提升一个循环，以进入下一个生产力和推理规模化的层级。当你发现问题时，就向下深入一个层级，以找出可靠性并修复你发现的任何bug。如果我把这简化一下，我有一个更好的类比，没那么复杂。这实际上就是一堆狂野的循环，对吧？我想在座的各位都是程序员，或者能理解这一点。实际上，这就是我们今天在这里要做的事。我期望工程师、领导者、研究人员、创始人，都能理解并像人类通用智能一样，在这些你们能够上下自如的所有循环中游刃有余。这就是为什么有这么多内容。我经常告诉那些抱怨内容太多的人，我不会为此道歉。我们提供内容。由你自己决定并引导自己，弄清楚你当前在哪个层级工作，你当前在哪个层级遇到了阻碍。

<details>
<summary>Original English</summary>

**Speaker 5**: um and i think this is something that is basically a ore scale of an engineer is defining what loops you're working in and figuring out whether that's the right level extraction. and when you're ready going up with loop in order to figure out the next level and productivity and scaling your inference. and when you're finding issues going down the p and when finlolevel in, in order to gure out reliability and fixing what of a bugs you you find, if you only simplify it, i have a have a better analogy that will be less complicated. it's literally just a stack of wild loops, right? i think all of you in the audience of the programmers or understand this and effectively, this is what we're here to do today. II expect engineers ers, leleers ers, our researchers ffounders to all be understanding and be cursing in as a as a human gengeneral intelligence, all these loos that you guys are capable of lup and down. and that is why there's so much countit. i often tell people of you who who complain about the tracks. i'm not going to apologize ze. we go content. it's up to you to decide and brought yourself as to which level you currently working in which level you 're currently blocked on.

</details>

**Speaker 5**: 所以，最近占据我大部分时间的事情，我给它做了一个人类类比，那就是：什么是人类循环？一开始，当你还在子宫里的时候，你会先有一个心跳。那是生命的证明。然后你学会说话，然后我们学会使用工具，然后我们开始工作。我们吃饭、睡觉、编码、写提示词，重复。然后我们开始团队协作。我们开始在小团体和家庭中工作。我们之前推广过“微型团队”的概念，我认为这对每个人来说都越来越重要。我认为，一个有趣的想法是，把整个人类项目作为一个整体来看待，比如我们所有人最终要走向何方。从你个人的语境向外延伸，到你的家庭、你的国家、你的公司，无论什么，再到人类文明这个更宏大的项目。我们在构建集体智能。我认为考虑这一点很有趣。

<details>
<summary>Original English</summary>

**Speaker 5**: so the thing that's occupying most of my time um recently, and what i make it a human analogy for is, what is the human loop. and in the beginning, there's a harbby when you're sof in the room you you to to get that harbeby. that's the proof of life, then you learn to talk, then we learn to use tools, then we start to work. we eat sleep code, repeat a prompt um and then we start working in teams. we start working in small groups and families. we have promoted the concept of tiny teams before, and i think that is increasingthe important with everybody. and i think 没有没有 the interesting thing to think about is like the broader human projects as a whole, like where we all going going know, know, extend out from your personal context, your family, your country, your company, whatever to the broader project that the human civilizzation. what we're builbuilding, we colcolletive inteinteligence ence. i think it's inteintesting to um consider it.

</details>

**Speaker 5**: 所以，我想今天留给你们的一点想法是，你们用编码所做的事情，绝对正在跨越到人类生活中。我在AI工程师大会上上一张便条中传达的信息是，你知道，你在一个领域看到的智能体，今年绝对会横向扩展到其他领域。今年是我们增加垂直领域专场的一年。比如，你知道，医疗保健AI、金融AI等等。我们今天有一个四点的工程专场，我对此感到非常兴奋。所有这些都旨在展示AI是如何最终渗透到编码领域的。

<details>
<summary>Original English</summary>

**Speaker 5**: so i think that's a little bit one. i want to leave you with today, like the things that you do do with coding are definitely crossing over to human life. um the message of my last, you note at engengineer that that you know, it's very much like agents that you see are working in one domein are definitely journalizing this year. this is the year that we are adding vertical tracks. like you know, i in health care AI in finance ANGTM. we have a four depoint engineering track is today, which i'm very excited about all. all this is mesed to see how AI is just fufusing finally young coding,

</details>

**Speaker 5**: 好的。嗯，最后一点，我想给大家更新一下组织者的压力曲线。嗯，给大家一个概念。这是2023年第一次AI工程师大会。这是售票曲线，基本上人们买票的方式是线性的。然后我们有了2024年的第一次世界博览会，大约两千人。好的，2025年。嗯，我可能画错了几条线，但我们基本上有六千人，如果你计算一下的话。我们的目标是六千人。实际上，我们今天已经超过了，达到了七千人。嗯，基本上，我要求大家早点买票。你们没有。嗯，如果你衡量一下詹金斯效率，它是在上升而不是下降，方向错了。所以，如果你们所有人都团结起来，你知道，管好你们自己，你知道，早点加入我们，我想那会很棒。不管怎样。

<details>
<summary>Original English</summary>

**Speaker 5**: okay. um last waldspare, i give you all an update on the stress curves uh of the of the organizers. uh just to give an idea. this is um the first wortes uh first AI engineer in twenty twenty three. uh this is ort ort that the sales curves basically of like how people bought basically as kind of linear. then we had the first walspare ir twenty four, uh about two thousand people. 好的好的, twenty twenty five. uh was uh, i think mayybe skit a few lines, but we're we're basically at six thousand um and if you took the calculate, so we aim for six thousand. we actually crossed in going when to seven seven today today. um um basically, i ask you all to buy your tickets earlier. you did not. 嗯, uh if you measure a jennical efficient, uh it has going up and not down, it's the wrong direction. so if if you all consises togather, you know, you 're yourself ves, and you know, join us early, i think that would be great anyway.

</details>

**Speaker 5**: 嗯，为什么我们想办一个会议？为什么我致力于一个会议？为什么你们都来参加一个会议？基本上，这是最高循环的概念。嗯，我想向你们提出，价值的最高循环是——如果我能让幻灯片正常工作，配合刷新——好的，那个最高循环就是人类聚集在一起，弄清楚下一个循环是什么，对吧？那个制造循环的循环。嗯，所以我们在世界各地组织AI工程师峰会。今年，我们在纽约、巴黎、新加坡都有峰会。而且，你知道，还有墨尔本，我差点忘了，还有迈阿密。嗯，我们正在组织这些合作伙伴活动。我们希望你们在自己的国家组织活动。我们有一个合作团队来做这件事。而我们是所有循环中的最高循环，那就是世界博览会，是峰会的峰会。所以，我非常激动地欢迎今天在座的各位。我希望你们能找到自己生成循环的生成过程，并将其向下传播到你们的团队、你们的个人工作流程、你们的生活中。

<details>
<summary>Original English</summary>

**Speaker 5**: um why we want to work at a conference, why why i work on a conference? why you all comes a conference is basically the concept of the highest loop. um i was sumit to you that the highest loop of vall is to if i can make a slidework only god with the refresh, okay, that hihighest opp is where humans come together to figure out what the next loop is right. the loopp that makes loops. um so we organize engineinesummmits all around the world. this year, we have summit in new york summits in paris summits in singapore. and you know, again, it's a melbourne and and forgetting one already met miami um and we are organize ze this the partners. we want you to organize that in your own home. tries are we're having a partnershiship team to do do this. and we are the highest loop of all, which is the world's fair, which is the summit of summits. so you i'm very excited to welcome all of you today. i hope that you figure out your generative process for generating loops and propagate it down to your teams to your personal workflows to your lives.

</details>

**Speaker 0**: 非常感谢，请享受接下来的演出。大家好，欢迎。

<details>
<summary>Original English</summary>

**Speaker 0**: thank you very much and enjoy to show hello and welcome.

</details>

### 主题介绍：软件工厂

**Speaker 6**: 哇，看看这观众规模。太不可思议了。AI工程师大会的规模是去年的两倍，我们的展区是去年的四倍。感谢在座的每一位成为这个社区的一部分。今天，我们有十八个不同的内容专场，涵盖分组讨论、主题演讲和展览环节，贯穿我们在这里的所有时间以及今天所有这些不同的会议。我非常激动地介绍今天主舞台的专场，名为“软件工厂”。一年前，Jeffrey Huntly发布了“粗略循环”，它抓住了我们的注意力，激发了我们的想象力，因为我们看到“粗略循环”可以代表我们整夜自主工作，并独立创建出完整的产品。然而，在早期，它并不完美。“粗略循环”只被推荐用于绿地项目。并且它附带了一个预期，即它只能带你完成大约90%的路程。在过去的一年里，我们学到了很多。整个行业也取得了相当大的进步，这使得现在成为软件工厂模式最大的转折点。视觉能力得到了提升，使得模型能够看到和验证它们以前无法完成的工作。我们还可以访问更丰富的工具生态系统，使得智能体能够访问它们以前无法获取的真实生产数据。我们还看到上下文窗口和记忆能力得到了改进，使得智能体和循环能够追踪之前完成的工作。推理模型和能力得到了改进，使得模型能够承担更复杂的任务。此外，AI安全最佳实践已经出现，使得模型和智能体能够拥有在企业内部完成真正有意义的工作所需的安全性、自主性和能力。所有这些因素结合在一起，现在软件工厂不再是未来的愿景。它们已经成为现实。今天的主讲嘉宾正处于这一变革的前沿，他们将帮助我们区分什么是真实的，什么是炒作，什么在实践中真正有效，以及如何构建能够产生真正结果——而不是垃圾——的软件工厂。

<details>
<summary>Original English</summary>

**Speaker 6**: wow, like the the size of this audience. this is incredible. air engineer has grown twice the size compared last year, and our extro was four times the size. thank you to each every one of you for being a part of this community. today. we have eighteen different tracks of content, ranging from break out tracks, keynotes and explosessions across all of our time here and all of these different sessions today. i'm super excited to introduce today's main stage track called software factories a year ago, jeoffrey huntly released the rough loop, it capture our attention and sparked our imagination as we saw the rough loop, work autonomsly overnight on our behalf and create entire products on its own. however, and the early days it wasn't perfect. the rough loop came recommended for green field work only. and it came with the expectation that it would get you about ninety percent of the way there over the last year we'wearned a lot. and there's been an considerable amount of advancements made across the industry, which makes now the single largest inflection point for software factories model. vision has improved, allowing models to see and verify work they couldn't have previously. we also have access to far richer tool ecosystems, allowing agenc's access real production data that they couldn't have previously. we've also watched context windows and memory improve, allowing agents and loops to track work that's been done before raising models and capabilities have improved, allowing models to take on more sophisticated task. also, AI security best purchases have emerged, allowing models and allowing agents to have the security, autonomy and capability. they need to do real meaningful work within the enterpriall of this comes together. now software factories are no longer a vision for the future. they become practical reality. today's speakers on the frefront of this shift, and they're going to help us separate what's real from what's hype, what actually works in practice and how to build software factories that pretuse real results, not slop.

</details>

**Speaker 6**: 我非常激动地介绍下一位演讲者。他的演讲题目是“论人工智能与知识”。他是微软的企业副总裁兼杰出工程师。请大家欢迎他上台。Pablo Castro。

<details>
<summary>Original English</summary>

**Speaker 6**: some very excited intererders are very for speaker. his talk is htidled on ai and knowledge. he's AC vp and distinguish engineer at microsoft. please walg them to the stage. public castro.

</details>

**Speaker 4**: 现在上台的是微软的企业副总裁兼杰出工程师，Pablo Castro。

<details>
<summary>Original English</summary>

**Speaker 4**: now taking the stage is CVP and distinguish engineer at microsoft public castro.

</details>

### 主题演讲：论人工智能与知识

**Speaker 7**: 我不知道。大家好，早上好。很高兴回到AI工程师世界博览会。

<details>
<summary>Original English</summary>

**Speaker 7**: i don't everyone, everyeveryin, good morning. it's great to be back here at the ai engineer walks spare.

</details>

**Speaker 8**: 我在微软的工作是连接人工智能与知识之间的桥梁。作为一个像呆子一样的知识狂人，这对我来说就像天堂一样。我花大量时间研究知识的表示、提取、搜索等等，并思考智能体与知识之间的反馈循环。你知道，思考“知道某件事”到底意味着什么，你知道……

<details>
<summary>Original English</summary>

**Speaker 8**: my job at microsoft is to connect the dots between ai and knowledge as an information with three will nerd like desk grade for me, like i spend a lot of time and looking at knowledge, representation, extraction, searge. and what not and thinking about agents and knowledge filling bites to reflect, and you know what it means to know something, you know,

</details>

<!-- chunk 2/54 -->

### 知识的三种类别：内在、外在与习得

**Speaker 8**: 我们如何根据已知信息完成任务，其本质就是如此。

<details>
<summary>Original English</summary>

**Speaker 8**: the nature of how do we get things done based on what we know next,

</details>

**Speaker 8**: 对吧。

<details>
<summary>Original English</summary>

**Speaker 8**: right,

</details>

**Speaker 3**: 二位，有请。

<details>
<summary>Original English</summary>

**Speaker 3**: 二位 there.

</details>

**Speaker 8**: 所以今天早上，我想我们花点时间聊聊知识的本质，并将其分为三类：内在知识、外在知识和习得知识。

<details>
<summary>Original English</summary>

**Speaker 8**: so this morning, what i thought we would do is spend a little bit of time talking about the nature of knowledge and split into these three categories of intrinsic extrinsic and learned innate knowledge.

</details>

**Speaker 8**: 内在知识就是模型自带的知识。

<details>
<summary>Original English</summary>

**Speaker 8**: it's just the knowledge that comes with the models.

</details>

**Speaker 8**: 你知道，这是我们用来训练模型的数据，也就是训练数据，以及存储在模型参数记忆中的内容。

<details>
<summary>Original English</summary>

**Speaker 8**: you know, is what we train the models on the training data and what is stored in the models, kind of parametric memory.

</details>

**Speaker 8**: 虽然这看起来显而易见，但我认为，正是这种知识将我们推入了今天所处的指数级增长时代。

<details>
<summary>Original English</summary>

**Speaker 8**: and while it's kind of the obvious thing i would argue, this is the knowledge that actually threw us into the exponential we are in today.

</details>

**Speaker 8**: 正是它开启了许多场景，这些场景随后发展壮大，促成了我们今天用智能体所做的所有事情。

<details>
<summary>Original English</summary>

**Speaker 8**: it's what started many of the scenarios that then grew and all the things we're doing with agents today.

</details>

**Speaker 8**: 让我用一个代码的例子来说明。

<details>
<summary>Original English</summary>

**Speaker 8**: let me give an example with code.

</details>

**Speaker 8**: 我写了这两段代码，时间相隔大约二十五年。

<details>
<summary>Original English</summary>

**Speaker 8**: so i wrote these two pieces of code about twenty five years apart.

</details>

**Speaker 8**: 然而，把它们组合起来的过程却惊人地相似，比如我必须坐下来，利用我所知道的，或者我必须去查阅的资料。

<details>
<summary>Original English</summary>

**Speaker 8**: and yet the process to put this thing together was surprisingly similar, like i had to sit down with what i knew or what i had to go look up.

</details>

**Speaker 8**: 然后我就直接把它写出来。

<details>
<summary>Original English</summary>

**Speaker 8**: and i then just write it up.

</details>

**Speaker 8**: 虽然我对知识这方面很感兴趣，但你可以说，写一封电子邮件或者创建一份文档摘要也是同样的情况。

<details>
<summary>Original English</summary>

**Speaker 8**: and while you know, i'm interested in this with knowledge, you could say the same thing about, you know, writing an email or creating a summary of a document.

</details>

**Speaker 8**: 好的，好的，好的，好的，现在。

<details>
<summary>Original English</summary>

**Speaker 8**: 好的好的好的好的， now.

</details>

**Speaker 8**: 你可以在这类任务中看到这种指数级增长，现在我相信你可以追溯得更远。

<details>
<summary>Original English</summary>

**Speaker 8**: you can see this exponential at play in tasks like this, where now i'm sure you can go further back.

</details>

**Speaker 8**: 但一个有趣的起点是微软引入 IntelliSense 的时候。

<details>
<summary>Original English</summary>

**Speaker 8**: but an interesting point in time to start looking at this would be when microsoft introduced intellisense.

</details>

**Speaker 8**: 那是在九六年，你知道，它很棒。

<details>
<summary>Original English</summary>

**Speaker 8**: it was in ninety six, and you know, it was great.

</details>

**Speaker 8**: 你不再需要记住函数签名之类的东西了。从那时起，过了二十二年。

<details>
<summary>Original English</summary>

**Speaker 8**: you didn't have to remember function signatures anymore and what not. it takes twenty two years from there.

</details>

**Speaker 8**: 才进入下一个阶段，机器学习帮助我们实际对 IntelliSense 提供的选项进行排序。

<details>
<summary>Original English</summary>

**Speaker 8**: to get to the next step, where machine learning helps us actually rank the options we give you in intellisense.

</details>

**Speaker 8**: 所以选择正确的选项更快了。

<details>
<summary>Original English</summary>

**Speaker 8**: so it's quicker to pick the right choice.

</details>

**Speaker 8**: 对对对对对对，仅仅三年后，GitHub Copilot 就发布了。

<details>
<summary>Original English</summary>

**Speaker 8**: 对对对对对对， just three years after that github copilot launches.

</details>

**Speaker 8**: 那是一个关键的转折点。

<details>
<summary>Original English</summary>

**Speaker 8**: and that was one key inflection point.

</details>

**Speaker 8**: 这甚至是在 GPT 宣布之前。

<details>
<summary>Original English</summary>

**Speaker 8**: this was even before gpt was announced.

</details>

**Speaker 8**: 现在，我认为 GitHub Copilot、ChatGPT 这类体验在很大程度上是建立在内在记忆之上的，也就是模型已经知道的东西。

<details>
<summary>Original English</summary>

**Speaker 8**: and no, i would argue that github copilot, chatgpt that sort of experiences were heavily grounded on this intrinsic memory, what the models already knew.

</details>

**Speaker 8**: 对对对，从那里开始，当然事情在几年后发生了变化，当然，Copilot 发布了，我们做事的方式也迅速演变。

<details>
<summary>Original English</summary>

**Speaker 8**: 对对对， from there of course things shifted in a couple of years later, of course copilot launches and how we do things kind of evolved really quick.

</details>

**Speaker 8**: 这把我们带到了去年，OpenAI 发布了 o1 模型。

<details>
<summary>Original English</summary>

**Speaker 8**: which takes us to a kind of less, last year openai o1 ships.

</details>

**Speaker 8**: 然后是快速的 succession，GPT-4o 发布，另一个模型不断被嵌入并用于编码。

<details>
<summary>Original English</summary>

**Speaker 8**: and then a rapid succession, gpt-4o, another models keep getting embedded and used at coding.

</details>

**Speaker 8**: 所以今年是极其成功的一年，像 OpenClaw 这样极其成功的软件问世，没有一行代码是手写的。

<details>
<summary>Original English</summary>

**Speaker 8**: so this incredibly successful year, where incredibly successful software, like like open claw comes to existence with not a single line of code written by hand.

</details>

**Speaker 8**: 这就是指数级增长的曲线形状，其中很大一部分是由模型的内在知识驱动的。

<details>
<summary>Original English</summary>

**Speaker 8**: so this is that shape of the exponential curve and a lot of this was powered by the intrinsic knowledge in models.

</details>

**Speaker 8**: 当然，还有现在推理的能力。在微软，我们希望让所有这些模型都可用，并让你能够轻松地将它们集成到你正在构建的智能体中。

<details>
<summary>Original English</summary>

**Speaker 8**: and of course, the ability to reason now. in the context of microsoft, we want to make available all these models and make it easy for you to integrate them into the agents you're building.

</details>

**Speaker 8**: 我们通过智能体平台来实现这一点，该平台始于我们构建的一个上下文系统，以便你可以为你的智能体提供基础。

<details>
<summary>Original English</summary>

**Speaker 8**: we do this from an agent platform that starts with what we all go and build has a contextualization system, so you can ground your agents.

</details>

**Speaker 8**: 当涉及到智能体托管、可观测性和管理时，我们在 Microsoft Foundry 中完成所有这些工作。Microsoft Foundry 也是我们在模型目录中提供数千个模型的地方。

<details>
<summary>Original English</summary>

**Speaker 8**: and when it comes to agent hosting, observability and management, we do all of these in foundry. microsoft foundry is also where we offer thousands of models in our model catalog.

</details>

**Speaker 8**: 这样你就可以为正确的任务选择正确的模型。

<details>
<summary>Original English</summary>

**Speaker 8**: so you can pick whatever is the right model for the right task.

</details>

**Speaker 8**: 而且我们每天都在增加更多模型。

<details>
<summary>Original English</summary>

**Speaker 8**: and we keep adding more every day.

</details>

**Speaker 8**: 事实上，就在昨天，我们宣布 Claude 在 Microsoft Foundry 中正式可用。

<details>
<summary>Original English</summary>

**Speaker 8**: in fact, just yesterday, we announced that claude in microsoft foundry is generally available.

</details>

**Speaker 8**: 所以你可以在 Foundry 统一体验的背景下使用 Claude 的所有能力。

<details>
<summary>Original English</summary>

**Speaker 8**: so you can use all the capabilities of claude in the context of the kind, kind, unified experience in foundry.

</details>

**Speaker 8**: 这样你就得到了两全其美的方案。

<details>
<summary>Original English</summary>

**Speaker 8**: so you get best of both worlds.

</details>

**Speaker 3**: 没有没有，没有异议。

<details>
<summary>Original English</summary>

**Speaker 3**: 没有没有没有异议。

</details>

### 从内在知识到外在知识：企业级知识基础

**Speaker 8**: 现在我想深入探讨更多细节，但是，但是别误会我。

<details>
<summary>Original English</summary>

**Speaker 8**: now i want to go deeper into more details, but but don't get me wrong.

</details>

**Speaker 8**: 到目前为止，如果你正在构建一个需要参与组织或公司内部活动的系统或智能体。

<details>
<summary>Original English</summary>

**Speaker 8**: so far, if you're building a system or an agent that needs to participate in what's happening in an organization or a company.

</details>

**Speaker 8**: 你知道，作为一个行业，我们当然意识到，我们看到了 RAG 模式的出现，它最初是一种相当低端的技术，但很快发展起来。

<details>
<summary>Original English</summary>

**Speaker 8**: and you know, as an industry, we realized certainly, and we saw the rag pattern emerge that started as a pretty low technique but quickly evolved.

</details>

**Speaker 8**: 我们今天通过上下文工程所做的一切。

<details>
<summary>Original English</summary>

**Speaker 8**: and what we do today with context engineering.

</details>

**Speaker 8**: 它变成了一个相当复杂的系统，用于连接智能体及其完成任务所需的知识，其中许多维度使得这个领域变得复杂。

<details>
<summary>Original English</summary>

**Speaker 8**: and you know, it became a pretty sophisticated system for connecting agents and the knowledge they need to get their job done, of the many dimensions of which are this guard can complicated area.

</details>

**Speaker 8**: 其中一个是，从简单孤立的数据源到整个公司范围的知识基础的演变。

<details>
<summary>Original English</summary>

**Speaker 8**: on one is kind of the evolution from simple and isolated data sources to whole company wide grounding.

</details>

**Speaker 8**: 另一个是我们如何从简单的向量搜索等开始。

<details>
<summary>Original English</summary>

**Speaker 8**: and the other one is how we started with simple vector searching and what not.

</details>

**Speaker 8**: 我们确实看到它演变成了相当复杂的检索系统。

<details>
<summary>Original English</summary>

**Speaker 8**: and we really saw this evolve into fairly complicated retrieval systems.

</details>

**Speaker 8**: 所以让我们从公司知识基础开始。在微软与客户交流时，我们早期注意到的一件事是，每当你构建一个智能体，你总是会拥有你为该智能体关心的、你自己管理的知识。

<details>
<summary>Original English</summary>

**Speaker 8**: so let's start with company grounding. at microsoft, spending time with customers, one of the things we saw early was that whenever you build an agent, you will always have the knowledge you care about for that agent that you manage yourself.

</details>

**Speaker 8**: 但你也经常需要基于你组织中的环境数据来为智能体提供基础。

<details>
<summary>Original English</summary>

**Speaker 8**: but you also need to ground the agent, often on the kind of ambient data of your organization.

</details>

**Speaker 8**: 我们知道，无论智能体做什么，这都可能包括你的文档、你的电子邮件、你的 Teams 讨论线程，或者你数据仓库中的信息等等。

<details>
<summary>Original English</summary>

**Speaker 8**: we know whenever the agent does, this includes maybe your documents, your emails, your teams threads, or the information in your data warehouse and what not.

</details>

**Speaker 8**: 因此，我们构建了 Microsoft IQ，作为一种为你提供单一入口点的方式，让智能体能够访问所有这些环境数据以完成其工作。

<details>
<summary>Original English</summary>

**Speaker 8**: so we built microsoft iq as a way to give you a single entry point into all these kind of ambient data that agents need to get their job done.

</details>

**Speaker 8**: 除了你构建到智能体中的特定信息之外。

<details>
<summary>Original English</summary>

**Speaker 8**: in addition to the specific information that you build into the agent.

</details>

**Speaker 8**: Microsoft IQ 不是一个单一功能，而是一组能力，从 Work IQ 开始，它将你的智能体连接到所有文档，比如 SharePoint，或者电子邮件、日历、你的聊天记录以及人与人之间的联系。

<details>
<summary>Original English</summary>

**Speaker 8**: microsoft iq is not one feature, it's more like a set of capabilities that goes from work iq that connects your agents to all the documents and say, sharepoint, or the emails, calendar, your chats and the connections between people.

</details>

**Speaker 8**: 还有 Public IQ，它让你能够访问你所有的分析资产和数据，来自数据仓库和数据湖，为 Power BI 报告提供支持。还有 Foundry IQ，用于你自己的智能体，你可以推送自己的数据，然后将其用于知识基础。

<details>
<summary>Original English</summary>

**Speaker 8**: which is public iq, that gives you access to all your analytics assets and from data, warehouses and data lakes to power bi reports. and foundry iq, which is what you use for your own agents, where you can push your own data and then use it for grounding.

</details>

**Speaker 8**: 当然，有时你的智能体需要去网络上获取数据作为基础。

<details>
<summary>Original English</summary>

**Speaker 8**: and of course, sometimes you have your agents go out to the web to ground on data.

</details>

**Speaker 8**: 可能不是你的数据，而是公共信息。

<details>
<summary>Original English</summary>

**Speaker 8**: maybe not yours, it's public information.

</details>

**Speaker 8**: 但你需要用它来完成智能体世界观的拼图。

<details>
<summary>Original English</summary>

**Speaker 8**: but you need to use it to complete the picture of what the agent's world view is.

</details>

**Speaker 8**: 为此，我们有 Bing IQ。

<details>
<summary>Original English</summary>

**Speaker 8**: and for that, we have bing iq.

</details>

**Speaker 8**: 这第一部分允许智能体基于这类环境数据进行知识基础。

<details>
<summary>Original English</summary>

**Speaker 8**: now this first part allows agents to ground on the kind of these ambient data.

</details>

### 检索系统的演进：从向量到智能检索

**Speaker 8**: 现在我之前提到的第二部分，是实际检索系统的演进。当 RAG 刚出现时，我认为我们看到的是向量数据库的初步采用，这确实帮助我们启动了许多系统。

<details>
<summary>Original English</summary>

**Speaker 8**: now the second i mentioned before is the evolution of the actual retrieval systems. when rag first emerged, i think what we saw is an initial adoption of vector databases that really unblocked us from getting a lot of the systems off the ground.

</details>

**Speaker 8**: 那很棒。

<details>
<summary>Original English</summary>

**Speaker 8**: and that was great.

</details>

**Speaker 8**: 我认为，你知道，有那么一秒钟，作为一个行业，我们以为如果我们能变得非常、非常擅长计算向量之间的余弦相似度，我们在检索方面就万事大吉了。

<details>
<summary>Original English</summary>

**Speaker 8**: i think you know, for a hot second, as an industry, we thought that if we could get really, really good at computing cosine similarity between vectors, we would be all set for retrieval.

</details>

**Speaker 8**: 但事实证明，事情从来没那么简单。

<details>
<summary>Original English</summary>

**Speaker 8**: it turns out, you know, things never that easy.

</details>

**Speaker 8**: 所以我们知道，评估一次又一次地表明，如果你结合多种方法，你会得到更好的结果。

<details>
<summary>Original English</summary>

**Speaker 8**: so we know what evaluations show over and over again, is how you know if you combine methods, you just get better results.

</details>

**Speaker 8**: 比如，在这个案例中，这是来自 Microsoft 的评估，它是 Foundry IQ 背后的搜索技术。

<details>
<summary>Original English</summary>

**Speaker 8**: like, in this case, this is an evaluation from microsoft, the search technology behind foundry iq.

</details>

**Speaker 8**: 你可以看到，单独的方法不如组合方法表现好，尤其是在将其应用于真实世界的客户场景时。

<details>
<summary>Original English</summary>

**Speaker 8**: and you can see how individual methods don't do as well as combined methods, particularly when you apply them to real world customer scenarios.

</details>

**Speaker 8**: 现在，关键在于如何构建一个平台，让你能够组合这些构建块，而不会把复杂性直接摆在你面前。

<details>
<summary>Original English</summary>

**Speaker 8**: now, the trick is how you build a platform that allows you to combine these building blocks without putting the complexity right in front of you.

</details>

**Speaker 8**: 它让你在需要控制时可以选择加入。

<details>
<summary>Original English</summary>

**Speaker 8**: it lets you opt into it when you need control.

</details>

**Speaker 8**: 但是当你有一个清晰的场景时，你可以拥有一个简单的系统。

<details>
<summary>Original English</summary>

**Speaker 8**: but when you have a scenario that is clear, then you can have an easy system.

</details>

**Speaker 8**: 所以在 Foundry IQ 中，这是我们核心的设计目标之一。我们实现这一点的方式是实际分层构建这个系统。

<details>
<summary>Original English</summary>

**Speaker 8**: so in foundry iq, that was one of our core design goals and the way we do this is we actually layer this system.

</details>

**Speaker 8**: 所以你可以从顶层开始。你可以去 Foundry 说，嘿，我有一堆 PDF 或图片在那里，帮我处理它们。

<details>
<summary>Original English</summary>

**Speaker 8**: so you can start at the top. you can go to foundry and say, hey, i have a bunch of pdf or pictures over there, just deal with them.

</details>

**Speaker 8**: 现在，如果你愿意，你可以做底层所有的事情，比如分块、向量化、处理相关性排名等等。

<details>
<summary>Original English</summary>

**Speaker 8**: now if you can do everything under the cover and do like chunking and vectorization and deal with relevance ranking and what not.

</details>

**Speaker 8**: 现在，如果你是专家并且想要控制，你也可以这样做。你可以去堆栈的底层。

<details>
<summary>Original English</summary>

**Speaker 8**: now, if you're an expert and you want control, you can also do that. you can go to the bottom of the stack.

</details>

**Speaker 8**: 你想构建向量索引，并告诉它如何提取向量，控制词汇检索等等。所有这些你都可以做。

<details>
<summary>Original English</summary>

**Speaker 8**: and you want to build vector indexes and tell how to extract the vectors, control lexical retrieval, and what not. you can do all of that.

</details>

**Speaker 8**: 而且你可以在同一个堆栈中完成，这意味着你可以根据需求的变化上下移动。

<details>
<summary>Original English</summary>

**Speaker 8**: and you can do it in the same stack, which means you can go up and down, as your needs change.

</details>

**Speaker 8**: 现在，在核心检索系统之上，我们还引入了一个智能检索堆栈，因为我们看到，对于简单的情况，快速的一次性检索就很棒。

<details>
<summary>Original English</summary>

**Speaker 8**: now, on top of the core retrieval system, we also introduced an agentic retrieval stack because we see that for easy cases, a quick single shot retrieval is great.

</details>

**Speaker 8**: 但对于更复杂的情况，你确实需要一个系统，它能够反思数据集中的内容，并在我们返回结果之前，判断是否满足了输入中的信息需求。

<details>
<summary>Original English</summary>

**Speaker 8**: but for more sophisticated cases, you do want a system that can reflect on what's in the data set and assess whether or not we satisfy the information need in the input before we come back with results.

</details>

**Speaker 3**: 没有没有没有，没有证据。

<details>
<summary>Original English</summary>

**Speaker 3**: 没有没有没有没有证据。

</details>

**Speaker 8**: 当然，我们看到很多这样的模式出现。

<details>
<summary>Original English</summary>

**Speaker 8**: of course, we see a lot of patterns like this emerge.

</details>

**Speaker 8**: 问题总是：这真的有用吗？我们的结果更好吗？

<details>
<summary>Original English</summary>

**Speaker 8**: and the always the question is: is it actually useful? are our results better?

</details>

**Speaker 8**: 根据我们的经验和评估，对于困难案例，智能检索方法可以在我们跟踪的许多指标上产生差异，比如事实依据、证据召回率或答案完整性。

<details>
<summary>Original English</summary>

**Speaker 8**: our experience and our evaluation is that for difficult cases, agentic retrieval can make a difference across the many metrics that we track, things like factual grounding, evidence recall or answer completeness.

</details>

**Speaker 8**: 我们看到智能检索方法持续优于简单方法。这就是个体简单方法之间的差异。

<details>
<summary>Original English</summary>

**Speaker 8**: we see the agentic retrieval approach continuously does better than simple. that's the individual simple difference.

</details>

**Speaker 3**: 现在让我给你展示一些实际应用。如果我们能切换到笔记本电脑，我们切换一下。

<details>
<summary>Original English</summary>

**Speaker 3**: now let me show you some of these in action if we can go to the laptop and we switch the laptop.

</details>

**Speaker 8**: 第二个。

<details>
<summary>Original English</summary>

**Speaker 8**: 第二个。

</details>

**Speaker 8**: 所以这里我在 Foundry 中。Foundry 是你管理智能体、管理模型的地方，也是你可以管理所有你提供给智能体以完成其工作的知识的地方。

<details>
<summary>Original English</summary>

**Speaker 8**: so here i'm in foundry. and foundry is where you manage your agents, manage models, but also the place where you can manage all the knowledge that you give your agents in order to do their jobs.

</details>

**Speaker 8**: 在这里，你可以，

<details>
<summary>Original English</summary>

**Speaker 8**: here you can,

</details>

<!-- chunk 3/54 -->

### 知识库的创建与配置

**Speaker 8**: 你可以创建知识库，它们就像是智能体进入你所关心的知识的入口点。在这个例子中，我将创建一个知识库。我有一个关于电影的数据集。这些是智能体检索系统。所以我会给它一个模型来驱动检索工作流程。我可以设定你希望模型和整个系统付出多少努力，这实际上是延迟与质量之间的权衡。我可以配置许多其他东西，但关键是，我想指定数据来源。我可以从头开始创建。但在本例中，我在 Blob 存储中有一堆非结构化数据，比如 PDF 等。我有结构化的数据，比如包含统计数据的 Parquet 表。我还想基于网络信息。所以，如果我采取这三个步骤，然后保存这个知识库，我现在就有了这个资产，这个知识库，我可以将它连接到一个基础智能体。这需要一点时间，但它也是一个独立的资产，如果我在其他场景中使用另一个工具，每个知识库在 MXP 中都是可发现的。所以你可以直接连接到它，而无需在中间编写任何胶水代码。

<details>
<summary>Original English</summary>

**Speaker 8**: you can create knowledge bases as they kind of the entry point of any agents into the knowledge you care about. in this case, i'll create knowledge base. i have a date to set about movies. this are agentic retrieval systems. so i'll give it a model to power the retrieval workflow. and i can say how much effort you want the model to make all the system to make, and it is effectively a trade off between latency and quality. i can configure a number of other things, but critically, i want to say where the data want to ground this coming from, and i can start from scratch. but in this case, i have a bunch of unstructured data like PDF and what not in blob storage. i have a structure, you know, parquet tables with statistics, and i also want to ground from the web. so if i take these three steps and then i save this knowledge base, now i have this asset this knowledge base that i can connect to a founder agent here. i'll take a second, but also it's a stand alone asset that if i have a different harness that i'm using in other use cases, every knowledge base in MXP is discoverable. so you can just connect to it without having to write any glue code in the middle.

</details>

**Speaker 8**: 现在，像这样的知识库有很多组成部分。其中一些，比如这个非结构化内容，你通常会构建索引，进行因子分解等等。如果你想要控制这些，你可以在这里进行配置。但如果你不需要，你可以直接使用它。让我切换到后台，向你展示这个特定实例背后的细节。如果我进入知识库，这就是我们刚才创建的知识库，我可以深入查看。例如，我可以找出支撑这个特定内容片段的索引。在那个索引中，我可以看到索引的结构。如果我对量化方法或想使用哪种索引有特定偏好，或者我想为我的向量指定索引类型，我都可以进行设置。当然，我还可以实际探索数据，查看里面的内容，了解数据块是如何组织的等等。所以，这些的目标是再次为你提供一个高生产力的环境，当你不需要那么复杂的功能时，你可以直接使用；而当你需要确保完成任务时，你可以回到后台进行精细控制。

<details>
<summary>Original English</summary>

**Speaker 8**: now a knowledge base like this has a bunch of parts. some of them, like, for example, this unstructured content, you usually build indexes. you factorize these things and what not. and if you want control over that, like if you don't, you can just use it here. but if you do let me just switch to the UI and show you the capabilities behind that particular instance. where if i go to knowledge bases, this is the knowledge base we just created a second ago, and i can go peek inside. for example, i can go fish out the index that backs this particular piece of content. and in that index, i can see what is the structure of the index, if i'm opinionated about maybe quantization approach i want to use or which index type i want for my vectors, i can say all of that. and of course, i can actually go and explore the data, and you know, see what's inside how chunks were organized and what not. so the goal of these is to again give you a highly productive environment when you wouldn't need the sophistication. and when you needed to make sure you have it to get your job done, you go back to the UI.

</details>

**Speaker 8**: 当然，这方面的另一个方面是，如今我们所有人最关心的问题之一是 Token 效率。因此，我们仔细评估了这个系统，以确保我们为你提供信息最密集的答案，同时使用最少的 Token，这样你在所有检索任务中消耗的 Token 都能产生高价值。我想讨论的最后一类知识是习得知识。习得知识是我们作为个人和组织每天在工作中积累的成果。我们能够观察流程，并通过反思和改进每一步来做得更好，这个想法现在已经真正改变了。既然我们有智能体在执行工作，我们可以自动地让智能体进行反思。

<details>
<summary>Original English</summary>

**Speaker 8**: and of course, the other aspect of this is, you know, top of mind these days for all of us is token efficiency. and so we carefully evaluate this system to make sure that we give you the most information dense answer that uses the fewest tokens so that your consumption of tokens has a high value when it comes to all retrieval tasks. the last category of knowledge i want to talk about is learned knowledge. now learned knowledge is the result of us doing the work we do as individuals and our organizations every day. and the idea that we can actually observe the processes and get better at them by reflecting and improving every step of it is something that is really changed. now that we have agents doing the work, and we can go and have the agents automatically reflect.

</details>

**Speaker 8**: 我最近写了关于这方面的文章，并反思了一个事实：人和智能体真的可以在工作中相互叠加。他们可以创建这个学习循环，有效地捕捉你所工作的公司或组织的独特之处，并将其输入到工作中，以增强你所做的工作。现在，在 Foundry 中，我们希望将其作为一种具体化的产品提供，让你今天就能使用。因此，我们构建了一个名为智能体优化器的组件，它有效地实现了这个过程，允许你评估基线、生成候选方案，然后评估新的候选方案。如果我们有强有力的结果，就将其部署到生产环境。让我快速展示一下这看起来是什么样的。如果我们能切换回笔记本电脑。

<details>
<summary>Original English</summary>

**Speaker 8**: i wrote about this recently and reflected on the fact that people and agents can really compound in how they do their work and how they can create this learning loop that effectively captures what's unique about the company or organization you're working on and inputs that to work to augment the work that you do. now in foundry, we wanted to offer it like a materialized version of these that you can use today. so we built a component called the agent optimizer that effectively goes through this process and allows you to evaluate a baseline generate candidates. and then you know, evaluate the new candidates. and if we have a strong result, then deploy that to production. let me give you kind of a quick flavor of what this looks like. if we can switch back to the laptop.

</details>

### 智能体优化器演示

**Speaker 8**: 好的。所以在这里，在 VS Code 中，我安装了 Foundry 工具包。我有一个简单的智能体。你如何编写智能体并不重要，只要你将配置外部化，比如你的指令、工具、技能定义等等。一旦你有了这样一个智能体，只需要两个关键步骤。首先，通常你已经有了一个评估集，但如果没有，你可以说“生成评估”。我们会查看我们所知道的关于智能体的信息，比如追踪记录、指令等，然后为你生成一个专注于任务的评估集。在这个例子中，我稍早运行过这个。所以，为了让你了解它的样子，你会看到一堆任务，然后是问题和标准等等。一旦你有了数据集，你就可以使用下一个工具进行评估，你可以说“优化”，我可以直接运行优化。这可能会运行大约四十五分钟，然后你会得到一个优化版本，这是通过有效地爬山法得到的。它会根据你的评估建立基线。我稍早运行过这个。所以让我向你展示这个特定例子的输出。

<details>
<summary>Original English</summary>

**Speaker 8**: all right. so here in VS Code, i have the foundry toolkit installed. and i have a simple agent. it doesn't matter how you write your agent as long as you externalize configuration, like, you know, your instructions, tool, definition skills and what not. so once you have one of those, it takes two key steps to do this. so first up i can actually so usually you have an evaluation already, but if you don't you can actually say "evaluate generate". and what it will do is we look at what we know about the agent of traces and instructions and what not and would produce a task-oriented evaluation for you. in this case, i run this a little bit earlier. so just to give you a flavor what this looks like, you have a bunch of tasks, and then you know, the questions and the criteria. and what not once you have a dataset, you can evaluate then with the next tool, you can say, optimize, and i could just run optimize on its own. and that will run in this case, this run for maybe forty five minutes or so, and you get an optimized version by effectively hill climbing the metric. it could that establish from by evaluation. so i run this earlier. and so let me show you the output for this particular one.

</details>

**Speaker 8**: 好的。你可以看到，我们首先建立了基线。然后我们使用不同的组合，通过一种类似遗传算法的循环来迭代候选方案，寻找在我们拥有的约束条件下表现更好的选项。有趣的是，一旦你找到了一个更好的方案，你可以简单地点击“应用优化”。由于你将配置外部化了，这允许你将一个配置替换为另一个。如果我们看这里，你可以看到，例如，原始配置和我们刚刚应用的配置，这里只挑选了指令部分。这些是为这个示例智能体编写的一些相当简单的指令。但如果我看优化后的版本，你会看到一堆并非人工编写的指令，它们是从爬山过程中涌现出来的，目的是让这个特定的智能体变得更好，这是基于我们已有的指令、技能和工具，同时也基于对智能体实际追踪记录和用户使用情况的反思。所以，这就是实际应用中的真实学习循环。你可以回到幻灯片。

<details>
<summary>Original English</summary>

**Speaker 8**: well, you can see that you know, we establish the baseline first. and then we kept iterating on candidates using different combinations using a genetic algorithm style kind of loop and looking for options that perform better given the constraints that we have. and the interesting thing is that once you found one that is better, then you can simply to say "apply optimization". and what this does is since you externalize the configuration, it allows you to swap one configuration for the other. if i look here, you can see that, for example, the baseline config and the one we just applied just to pick on instructions. these are some fairly trivial instructions for this example agent. but if i look at the optimized one, then you can see a bunch of instructions that are not hand-written, but that they emerged out of the hill climbing process to get to make this particular agent better, given what we have in terms of instructions and skills and tools, but also based on reflecting on the actual traces from the agent and how users use it. so this is the real learning loop materialized in practice. you can go back to slide.

</details>

### 总结与介绍

**Speaker 8**: 所以，这是一个非常快速的概述，关于我们如何看待人工智能背景下的知识，以及我们如何认为可以启用这些学习循环，这些循环将捕捉到我们所工作的每个公司和组织中存在的差异化能力。如果你想尝试我今天谈论或展示的任何内容，你可以访问 ai dot foundry dot com 开始使用。说到这里，感谢大家今天早上的聆听。祝你们在接下来的活动中一切顺利。

<details>
<summary>Original English</summary>

**Speaker 8**: so this was like a very quick overview about how do we think about knowledge in the context of AI? how do we think we can enable these learning loops that will capture, you know, this differentiated capability that lives in each one of the companies and organizations we work on. if you want to try anything of what i talked about or showed today, you can head to ai dot foundry dot com and get going. and with that, thank you all for listening this morning. i hope you have a great rest of event.

</details>

**Speaker 4**: 请大家和我一起欢迎 OpenAI 的企业产品负责人和开发者体验负责人，Alexander 和 Roman。

<details>
<summary>Original English</summary>

**Speaker 4**: please join me in welcoming the head of enterprise product and the head of developer experience at open ai alexander and roman.

</details>

**Speaker 7**: 大家早上好。

<details>
<summary>Original English</summary>

**Speaker 7**: good morning, everyone.

</details>

**Speaker 9**: 我是 Roman。

<details>
<summary>Original English</summary>

**Speaker 9**: i'm roman.

</details>

**Speaker 10**: 我是 Alexander。

<details>
<summary>Original English</summary>

**Speaker 10**: i'm alexander.

</details>

**Speaker 9**: 哇，这真是太不可思议了。今天这里有超过七千名人工智能工程师。你知道，重要的不仅仅是哪些人在谈论这项技术，更是哪些人每天都在实际使用它并推动着前沿发展。所以，今天我们能与大家齐聚一堂，感到无比自豪。我和 Alex 在构思这次活动时，我们总是回到“世界博览会”这个概念。如果我们能再放一张幻灯片。

<details>
<summary>Original English</summary>

**Speaker 9**: wow. this is incredible. there's over seven thousand ai engineers here today with us. and you know it's not just about who's talking about this technology. it's also about who's actually using it and pushing the frontier every day. so we couldn't be more proud to be here with all of you today, and we were thinking about this event with alex. we kept coming back to the world's fair. you know, if we can advance one slide.

</details>

**Speaker 10**: 这张可以。

<details>
<summary>Original English</summary>

**Speaker 10**: this one works.

</details>

**Speaker 9**: 好的，我们可以回到世界博览会这个概念。世界博览会是一个行动。它通过公开建设，让未来对所有人可见。你知道，那些以前听起来不可能的想法，突然之间人们可以看到它们，可以走进它们，甚至可以开始相信它们。老实说，这次活动有着完全相同的能量。工程的未来并非来自别处。它真的、真的就在这里被构建。在这个房间里的人们，以远超预期的速度在构建。这有点令人惊讶，因为人们一直说工程师会消失。论点是编码被抽象化了，因此，最终我们将不再需要工程师。然而，事实上，我们认为恰恰相反。你知道，软件吞噬了世界。然后人工智能增强了软件。但现在我们要说的是，人工智能工程师正在吞噬世界。人工智能工程师就是这里的人们，是推动前沿的人们。

<details>
<summary>Original English</summary>

**Speaker 9**: all right, we could go back to the world's fair. and the world's fair is an action. the future visible to everyone by building it in public, you know, ideas that previously sounded impossible. were actually suddenly there people could see them, they could walk into them, and you could even start to believe in them. and honestly, this event has the exact same energy. the future of engineering is not arriving from somewhere else. it's really, really built right here. the people in this room and much faster than someone expected. and that's quite a little surprising that people keep saying that engineers are going away. the argument is that coding is you know, abstracted away. and therefore, eventually, we won't need engineers. well, in fact, we think it's quite the opposite, you know, software ate the world. and then AI augments software. but now what we're here to say that the AI engineers are eating the world, AI engineers are the people here, pushing the frontier.

</details>

**Speaker 8**: 是的。

<details>
<summary>Original English</summary>

**Speaker 8**: yes.

</details>

**Speaker 9**: 而你们所有人都在探索这种新能力如何能够触及每一个人。现在成为工程师从未有过更好的时机。事实上，因为工程从来就不是关于编写代码。

<details>
<summary>Original English</summary>

**Speaker 9**: and you all are figuring out how this new capability can reach everyone? and there has never been a better time to be an engineer. in fact, because engineering was never about writing.

</details>

<!-- chunk 4/54 -->

### 工程的本質與AI的演進

**Speaker 9**: 工程一直以來都是關於為自己和他人解決問題。它是關於將後期的科學與設計、品味、判斷力，以及最重要的想像力結合起來，創造出人們真正能使用的東西。從這個意義上說，這不是工程的終結。

<details>
<summary>Original English</summary>

**Speaker 9**: Could engineering has always been about solving problems for yourself and for other people as well. It's about taking the later science and combining it with design with taste with judgment. And most of all imagination to make something that people can actually use. And in that sense, it's not the end of engineering.

</details>

**Speaker 10**: 我們認為這是回歸工程的根源，而且我們所依託的技術正在加速，變得越來越快。例如，我們之前大約每十五個月發佈一個新模型。現在大約是每六週一次。如果你沒注意到，上週我們發佈了 5.6 系列模型的預覽版。我們非常興奮能讓大家使用。在這些模型的基礎上，產品進步的速度是無情的。結果就是，我不需要告訴你，工程學的感覺已經完全不同了。所以，回顧過去幾年，對我來說一系列令人驚嘆的經歷：很長一段時間裡，我們有程式碼補全，然後我們進入了行內預測，最後，我們有了命令 Kate。我們可以要求模型進行更改，但它們不會測試工作。然後模型開始測試工作。現在我們有了能夠承擔長期艱鉅目標直到完成的模型。對我來說，每一個階段，我都記得第一次體驗時的感覺，那令人驚嘆，之後你就習以為常了。所以你還是得繼續完成你的工作。

<details>
<summary>Original English</summary>

**Speaker 10**: We think it's a return to the roots of engineering and the technology we're building on is accelerating, getting faster and faster. For example, we aged the ship a new model every fifteen months or so. And now it's about roughly every six weeks. And in case you missed it. Last week, we launched the preview of five, five point six series. And we're super excited to get into all of your hands. Now building on top of all these models. The rate of product progress is relentless. And as a result, I don't have to tell you the engineering feels completely different. So just to go over a couple years of what for me, was successive mind blowing experiences, you know, obviously, for a long time, we've had, you know, completion, and then we went to inline prediction. And then finally, we had then had command Kate. We can ask a model to make a change, but they wouldn't test the work. Then models started testing the work. And now we have models taking on long hard goals until they're done. And for me, each of these paces, I remember the first time, which is mind blowing in the obviously afterwards you get get. So so you're trying to get your work done.

</details>

**Speaker 3**: 沒有沒有。

<details>
<summary>Original English</summary>

**Speaker 3**: No, no.

</details>

**Speaker 9**: 是的。事實上，我簡直不敢相信，就在兩年前，構建和測試循環甚至不是模型的一部分。這是我在 2024 年 Dev Day 的照片，當時我使用了 o1 預覽版，從頭開始構建了一個迷你無人機介面。有點嚇人的是，模型實際上無法即時編寫程式碼。所以在工作中，我知道演示大部分時間會成功，但肯定不是每次都成功。所以我交叉著手指，你會看到我當時非常緊張。但是，嘿，這就是我。我只做現場演示。所以我每次都不知道會發生什麼。幸運的是，它確實成功了，到了去年年底和 2025 年，我對模型能夠測試自己的工作、控制攝像頭系統和燈光系統充滿了信心。但是，是的。

<details>
<summary>Original English</summary>

**Speaker 9**: Yeah. In fact, like I can't believe that build and tests loop was not even part of the models. Just two years ago. This was a picture of me, a Dev Day, twenty twenty four, and I used o one in preview at the time to build a mini drone interface from scratch. The slightly insane part is the model could not actually code live. So in the work, I knew the demo would work most of the time, but surely not all of the time. So I had my fingers crossed you're gonna see here that I was pretty nervous. But hey, that's me. I only do live demos. So I never know what is going to happen each time. Luckily, it did work and by Dev Day of last year and twenty twenty five, I was confident in it. Now the models could test their own work to get control of the entire camera system and lighting system lives. But yeah.

</details>

**Speaker 10**: 我們已經走了很長一段路。是的，所以我被稱為演示之神，你知道在演示之前，我問他，所以幫他讓演示成功。實際上，你知道，四次中有三次成功了，我們還行，對吧。顯然，從那時起我們已經進步了很多，而僅今年一年就已經很瘋狂了。所以我們在這裡或那裡列出了我們已經發佈的所有東西。實際上，這甚至還不是我們今年迄今為止發佈的所有東西的完整列表，我們能回去一下嗎？不，沒關係。重點是，我最喜歡我們發佈的東西，比如 Copilot Chat、Copilot 程式碼審查、Copilot 自主模式。這些東西真正改變了工作的感覺。所以，好的，對的，你知道，顯然，如果我們不使用 Copilot 來構建 Copilot，我們就無法做到這些事情。但我認為，對我來說，最有趣的是，現在 Copilot 和智能體可以完成你可以在自己電腦上完成的任何任務。所以這意味著它們不僅僅是與程式碼互動，它們還在幫助你處理編碼之前發生的事情。對對對，它們也在幫助你處理編碼之後發生的事情。而這確實是關鍵，對吧？我認為已經有很多討論，今天也會有很多關於循環的討論。如果你能將智能體不僅連接到你必須完成的工作，還能連接到為什麼必須完成它，這樣你就能讓智能體開始承擔更多的工作。然後，如果你能將它連接到你之後做的事情，比如審查和上線，這樣你就能完成更多的工作。是的。

<details>
<summary>Original English</summary>

**Speaker 10**: We've come a long way. Yeah, as so I'm referred to as the demo god, and you know before the demo, like I've asked him, so help him make the demo work. And really, you know three times out of four, and we're alright, right. Obviously, we've come a mile since then, and this year alone has been crazy. So we're putting up here or here or somewhere are all the things that we've shipped. So that's not even know a selection of the things that we've shipped so far this year actually, can we go back once? No, it doesn't really matter. The point is my favorite things that we've shipped like Copilot Chat, Copilot Code Review, Copilot Autonomous Mode. These are things that really change how it feels to do work. And so, okay, right, you know, obviously, we couldn't do these things if we didn't use Copilot to build Copilot. But I think to me, what is most interesting is it now Copilot can do and agents can do any task you can do on your own computer. And so that means they're not just pinging with the code but they're helping you with what happens before the coding. Right, right, and are helping you with what happens after the coding. And this is really key, right? I think there's been a lot of talk. There will be a lot of talk today about loops. And if you can connect the agent to not only the work that you have to do, but why it has to be done, that's how you can get the agent to start to begin much more work. And then if you can connect it to what you do afterwards review and the deploy, that's how you have at land much more work. Yeah.

</details>

**Speaker 10**: 所以，有了這一切，當然，我們可以更快地行動。但對我來說，作為一個產品人，最令人興奮的事情實際上是我們圍繞著要構建什麼做出了更好的決策。例如，我們嘗試原型化更多的想法，並且我們花更多的時間與用戶在一起。所以，是的，那就是你們所有人。所以，其中一個熱情就是給你們所有人一個大大的感謝，感謝你們的喜愛和建設性的反饋。我想可以這麼說，沒有你們，就沒有 Copilot，實際上整個行業也不會存在。

<details>
<summary>Original English</summary>

**Speaker 10**: So with all of this, of course, we can move much faster. But to me, as a product person, the most exciting thing is actually that we make better decisions around what to build. For instance, we try we prototype many more ideas, and we spend much more time with users. So yes, that's all of you. So one of the passions just give you all a big thank you, both for the love and the constructive feedback. I would say it's safe to say that we Copilot and actually the entire industry wouldn't be here without you.

</details>

**Speaker 9**: 是的，非常感謝所有的反饋。好吧，這些東西大部分都是獻給你們所有人的。謝謝。

<details>
<summary>Original English</summary>

**Speaker 9**: Yeah, thank you so much for all the feedback. Well, most of these things are to all of you. Thank you.

</details>

### 未來展望：智能體與產品形態

**Speaker 10**: 好的。那麼下一步是什麼？模型變得越來越好了。我想說，如果你選一個中等長度的電腦任務，然後給我和模型同樣的時間來完成那個任務，可能，至少在我的情況下，對於平均任務，模型會做得比我更好。所以，好吧，我們正在讓這些模型，你知道，在某些方面，比我們更聰明。它們幾乎可以做任何事情，我們應該如何塑造它？我們使用的產品應該是什麼感覺？為了回答這個問題，我們審視了我們的使命。我這裡展示的部分是「惠及全人類」。我認為為了做到這一點，我現在思考兩個主要問題：一個是，我們如何設置智能體讓它們在現實世界中實際做事？所以它們能做什麼？你知道，逐漸地，智能體連接到越來越多的東西，那麼它們在哪裡運行？稍後會詳細介紹。另一個問題是，我們如何為我們自己使用這些智能體？圍繞它們的產品應該是什麼感覺？對我們來說，目標絕不是自動化工程師。相反，我們想要的產品形態是最大化地賦能工程師。所以，你知道，我們思考那個產品形態是什麼，我們實際上認為它很簡單。我讀了很多科幻小說，你知道，也看了很多超級英雄電影。我實際上認為那些簡單的想法一直都在，對吧。所以大致有兩種模式：聊天。我實際上認為，我知道有些人認為聊天已死。我認為聊天被低估了。我認為某種動手實踐的體驗也很重要。所以你想要的是一個單一的實體，你可以在任何地方、任何事情上向它尋求幫助。然後你想要一個強大的協作用戶介面，當你想要自己檢查、引導或塑造事物時可以使用它。所以我讓 Copilot 影像生成 Jenny 畫了一幅插圖來說明這一點，以幫助理解你可能何時想要使用這些東西。所以我給你的類比，我希望你，你喜歡這個影像生成。我給你的類比是：這就像與一個團隊合作，大多數時候你只是在討論事情，你的團隊就在做事。你實際上不想在每一個單位的任務上都盯著他們的肩膀或者必須走到你隊友的工作台前。大多數時候你只想交談。讓他們去發揮。然後時不時地，你想要深入挖掘，真正深入到事情的細節中，一起解決那個問題。對我們來說，當我們構建產品時，我們有這樣一個想法：我們希望讓你保持對我們所做工作的掌控感，因為這非常強大。我們不想讓它感覺，實際上，真的很難獲取細節。就像你知道的那樣，在這個例子中組裝硬體。所以我們將這個想法變為現實的方式才剛剛開始，但這就是為什麼我們構建了 Copilot 編輯器，你會得到一個非常簡單的聊天介面，你可以用它來編碼和做任何其他事情。你知道，你可以進行對話，然後深入到你想要的任何程度。所以在這個例子中，我們有關於即將到來的世界盃比賽的預測分數。我希望我是對的。

<details>
<summary>Original English</summary>

**Speaker 10**: Okay. So what's next? The models are getting really good. I would say, if you pick like a medium length computer task, and you give me and the model the same amount of time to get that task done, probably, at least in my case, the model will do a better job than me for the average task. And so okay, we're getting these models, you know, in some ways, they're smarter than us. They can do almost anything, how should we shape that? What should the products that we use feel like? And so to answer that, we look to our mission. The part of it here that I've got up is that it benefits all of humanity. And I think in order to do this, there are two main questions that I think about now, one is, how do we set up the agents to actually do things in the world. So what can they do? You know, gradually agents getting connected to more and more things than where do they run more on that later? And then the other question is, how do we use these agents for us? What should the product feel like around them? And for us, the goal is squarely not to automate engineers. Instead, the product shape that we want is one that maximally empowers engineers. So you know, we think about what that product shape is we actually think it's pretty simple. I read a lot of sci-fi. And you know, watch superhero movies. And I actually think that the simple ideas are there constantly, right. So there are two modalities roughly chat. I actually think I know some people think chat is dead. I think chat is underrated. I think some kind of hands-on experience. So what you want is a single entity that you can ask for help with anything anywhere. And then you want to see a powerful collaborative UI that you can use when you want to inspect steer or shape things yourself. And so I had Copilot image gen Jenny, an illustration of this to help understand when you might want to use these things. And so my analogy for you, I hope you, you like the image gen. My analogy for you would be. It's just like working with a team, most of the time you're just talking about stuff, and your team is just doing stuff. You don't actually want to watch over the shoulder or like have to walk over to the work bench of your teammate for every single unit of work. Mostly just want to talk. Let them cook. And then every now and then you want to dig in and really dig in all the way to the weeds of things and dig in that problem together. And for us, as we build product, we have this idea that we want to make it that you can retain this feeling of mastery of the work that we're doing because that's really powerful. We don't want to make it feel like, actually, it's really hard to like get the details. And like you know, this assemble the hardware in this case. So the way that we're bringing this to life is just the beginning, but this is why we built the code, except you get a very simple chat interface that you can use for coding and for anything else. And you know, you can have a conversation and then go as deep as you want. So in the case, here, we have Homan's predicted score of this upcoming world cup match. I hope I'm right.

</details>

**Speaker 9**: 對。我希望我是對的。我們走著瞧，好吧。

<details>
<summary>Original English</summary>

**Speaker 9**: Right. I hope I'm right. We'll see okay.

</details>

**Speaker 10**: 你在這裡可以做的是，你可以進去，指向一個非常具體的東西並說，嗨，我希望你做這個更改，或者你可以自己進行這個更改。一個有趣的故事是，實際上，Copilot 編輯器是一個相當有爭議的項目。嗯，我記得在我們開始之前向你們中的一些人推銷這個想法，我被告知，我永遠不會使用這樣的工具。我永遠不會離開我的終端，嗯，但那是 Emacs。嗯，但實際上那些人現在正在使用它，即使在我們團隊內部。有很多問題，比如，我們為什麼要構建這個？人們喜歡 CLI，喜歡 IDE，這有點微妙。但我的觀點是，你實際上無法在 CLI 中為任何類型的工作構建那種協作介面。它主要是聊天。而在 IDE 中，順序是錯的。

<details>
<summary>Original English</summary>

**Speaker 10**: And what you can do here is you can go in, and you can point it a very specific thing and say, hi, I want you to make this change, or you can make this change yourself. And a fun story here is that actually, the Copilot editor was quite a controversial project to start. Um I remember pitching some of you who I know in the audience like this idea before we started, and I was told squarely, I will never use such a tool. I will never leave my terminal um but then were Emacs. Um but actually those people are now using it and even internally like within our team. There are a lot of questions, like, why should we build this? People love the CLI, love the IDE, and it's a little subtle. But my take is that you can't really build that collaborative interface for any kind of work in a CLI. It's mostly chat. And then in IDE, the order is wrong.

</details>

<!-- chunk 5/54 -->

### 从代码优先到对话优先，再到开放生态

**Speaker 10**: 所以你是从代码开始的。但现在该过渡到与队友协作的模式了——先聊天，需要时再深入。

<details>
<summary>Original English</summary>

**Speaker 10**: so you're starting with the code. but now it's time to transition till like working with teammates where you chat first, then you dig in when you need it.

</details>

**Speaker 11**: 有没有没有 totally。

<details>
<summary>Original English</summary>

**Speaker 11**: 有没有没有 totally.

</details>

**Speaker 9**: 我们在产品表面和模型层都推进得非常快，当然。但我们也会努力跟上你们所有人的步伐，对吧？老实说，我经常打开 XII，看到这个房间里的某个人正在做某件我都没意识到 XII 竟然能做的事。老实说，这就是先驱者做的事。你们做实验，为自己和团队搭建工具。反过来，我们也受到启发，向你们学习，最终每个人都受益。所以我们正在帮助你们，你们也在帮助我们弄清楚下一步该构建什么，以及工程的未来应该是什么样子。

<details>
<summary>Original English</summary>

**Speaker 9**: and we're moving really fast on this on the product surface and the model layer, of course. but we will also try to keep pace with all of you, right? honestly, have the time i open XII see someone in this room doing something that i had not realize could x could actually do. and honestly, this is what pioneers do. do you guys experiment, you set up tools for yourself for your team. and in turn, we get inspired we learned from you and eventually everyone benefits. and so we are helping you are helping us figure out what to what to build next and also what the future of engineering should look like.

</details>

**Speaker 9**: 但要做到这一点，有一件事我们非常非常在意，那就是 Codex 不能是一个只有我能改进的封闭产品。所以我们有意将 Codex 设计为一组任何人都可以构建的层级，今天我们就想向你们展示一下这个堆栈以及它是如何体现的。

<details>
<summary>Original English</summary>

**Speaker 9**: but for that to work, one thing that we really really are is that dex cannot be a cluclose product that only open, i can improve. so we've intentionally design cordex as a set of layers that anyone can build on, and we want to show you a bit of that stack today and how it manifests.

</details>

**Speaker 9**: 好的，对对对。首先，从模型开始。Alexander 展示了我们在模型上的进展有多快，你们通过 Responsi 的 API 使用这些模型。猜怎么着？我们就是这么构建 Codex 的。我们使用相同的模型，通过相同的 API。我们实际上是在我们提供给开发者的同一个东西上进行构建，如果 Codex 需要某些功能，我们实际上会把它构建回 API 中。这样你们也能受益。比如最近在压缩方面，Codex 需要一种方法来压缩长上下文以处理长时间运行的任务。所以我们把它构建到了应用中。这意味着你们的代理可以使用我们为自己构建的相同原语。

<details>
<summary>Original English</summary>

**Speaker 9**: 好的，对对对，first, it starts with the model. and an exander showed how quickly with progressing on models and you guys use these models through the responsi's api. and guess what? this is how we build the could except right. we use the same models and through the same api. and we actually are building on the same thing that we give to developers, and we could exneeds something and acactry builback it into the api. i so you can benefit as well. when example recently with compaction, could acx needs the way to compact long conttext for long running tasks. and so we'll build that into the app. i so that means your agents can use the same primitives that we build for ourselves.

</details>

**Speaker 9**: 来到下一层。Codex 本身也是开源的。所以你可以检查它，可以复刻它，可以改编它。我们在 Agent MD 上也采用了同样的方法，而不是为 Codex 重新发明一种新的文件格式来遵循指令。我们想，让我们用一种其他代理也能使用的语言。模型在 harness 中有默认值，但它们并不是硬编码在里面的。所以如果你想使用一个开放模型并保持相同的代理协议，你可以做到。我们还将这些优秀的特性引入到我们模型的后训练过程中。这意味着模型可以学习使用工具和导航环境。这实际上是开源的。

<details>
<summary>Original English</summary>

**Speaker 9**: moving onto the next layer. the critics honest is also open source. so you can inct it. you can fork it. you can adapt it. and we also took the same approach with agent MD instead of reinventing a new file ld forat for for codex to follow instructions. we thought, let's speak a name that other agents can actually use as well. the models harder default in the the harness, the momodels come up an eye, but they're not hard created in there. so if you want to use an open model and keep the same agent group you can, and we also bring these good exhoness the post training process of our models. so that means the models can learn to cool tools and navigate an environment. that's actually something that's open source.

</details>

**Speaker 9**: 就拿 Open Code 团队来说吧。他们实际上能够检查我们是如何实现参考实现的，他们可以重用对他们有意义的那些部分，同时完全改变其余部分，做出不同的选择。比如，他们试图了解我们是如何做签名的，也就是 ADG PT。所以他们可以查看代码并从中学习。我们认为这比让开发者逆向工程我们是如何构建的以及为什么这样构建要好。

<details>
<summary>Original English</summary>

**Speaker 9**: now take the open code team. for instance, they actually we're able to inspect how we have dislike reference implelementation, and they could reuse the parts that make sense to them would change altirely all the rest and make different different choices, know, know ininstance. they were trying to see how we did like signing, which adg PT. and so they could look at the code and learn fumit. and we think it's better than having developers reverse engineering, how would build and and how we not.

</details>

**Speaker 9**: 但现在，说到订阅，假设我们想再往上走一层，看看如何将这个 harness 引入到一个应用中。以及如何让人们用现有的 Codex 订阅登录？结果发现，我们自己也有同样的问题，因为我们想构建 VS Code 扩展和 Codex，并且我们想要一种统一的方式来实际控制这个 harness。所以我们构建了 Observer，并且我们也将其开源。Observer 不仅仅是一个社区适配器。它实际上是我们用于自己产品的路径，你们也可以使用它。比如，这里有一个关于 Ababties on Native 的例子，那是 Codex Monitor，在我们甚至还没推出 Codex 之前就有了，因为他可以用 Observer 来构建它。现在他在我们团队工作，他实际上为 IUS 构建 Codex，并在堆栈的上层工作。

<details>
<summary>Original English</summary>

**Speaker 9**: but now let's say, speaking of subscriptions that we want to go a level higher and how you bring this harneness into an nap. and how do you like people sign in with the existing good exscription? for instance, well, it turns out we we had same problem of ourselves because we wanted to build AVS good extension and the could, except and we wanted to have a unified way to like actually control this harness. so we build observer, and we also made that open source. and the observer is not going of a community adapter. it's really the path that we use for our own products, and you can use it too tuoma. for instance, here for a million on on ababties on native, that for connex could could x monitor before we even launched to could accept, cause he could build that using the observer. and now you works on our team, and he actually builds could tex for IUS and moving up the stack at the upplayer.

</details>

**Speaker 9**: 我们还希望确保创新不被我们自己的想法所阻碍。所以我们在这里构建了可扩展的原语，比如我们在屏幕上展示的 MCP 工具和插件。所以，以 MCP 工具和 Computer Use 为例，这些是作为插件构建的，使用了我们为你们所有人提供的相同扩展点。对对对。

<details>
<summary>Original English</summary>

**Speaker 9**: we also want to make sure that innovation is not blocked on our own ideas. and so we build extensible primitives here, like the enough bozzard that we showed on the screen and plugins. so if you take, for instance, bozza use and computer use, these were built as pluggins using the same extension points that we have available for for all of you. 对对对.

</details>

**Speaker 9**: 最后，我们最近还为 Codex 构建了特定角色的插件，以便更容易地为从事数据科学或设计等工作的人进行定制，这些插件也是开源的。你可以查看内部实现，并从中获得灵感，如果这有用的话。

<details>
<summary>Original English</summary>

**Speaker 9**: and lastly, we also recently build role specific lugggfor for could i say to make it easier to to customize for people who work in data science or design, for instance, and these bluggings are also up and source. you can see under the hood and get inspired from them. if that's useful.

</details>

**Speaker 3**: 嗯。

<details>
<summary>Original English</summary>

**Speaker 3**: 嗯.

</details>

**Speaker 9**: 我们的目标是继续尽可能保持开放和灵活。最棒的是，人们可以在越来越多的地方使用现有的订阅，从 Open Code Pie、Droid Open Class，甚至到 Execode 和 Jet Brains 等 IDE。你可以看到它已经成为人们使用这些工具的一个非常重要的部分。这就是为什么我们如此关心与你们所有人一起构建这个开放生态系统。谢谢。

<details>
<summary>Original English</summary>

**Speaker 9**: our goal is ready to keep making this as open and flexible as we can. and the best parties people can use the existing subscription in more and more places from open code pie, droid open class to even execode and jet rains as ideas. and you can see how you'becomcoming quite meaningful bart of how people use these tools. and that's really why we want to care about building this open ecosystem with all of you. thank you.

</details>

**Speaker 9**: 所以，真的，如果我想让你们从这个部分和这个堆栈中带走一件事，那就是这个。我们不是在构建一个封闭的 AI 系统。而是一个在每一层都为开发者简化的系统。我们实际上使用的是我们给予你们的东西。我们想感谢你们所有人，因为每次你们复刻 harness，每次你们发现模型能力的边界，都意味着我们有机会学习和改进。老实说，今天在这个房间里，我们有七千名最优秀的 AI 工程师。我相信你们所有人将在很大程度上定义我们将如何体验 AI，以及世界将如何体验未来的 AI。

<details>
<summary>Original English</summary>

**Speaker 9**: so really, if this one thing i wanted to take away from this section and this stack, it's this. we're not building one system full, open a eye. and the second system that simplified for developers at every layer, we actually use the thing that we give you. and we want to thank all of you because every time you fork the harness ness, every time you find the edge of capabilities of the models. it means we get to learn and improve. and honestly, we seven thousands of the finest AI engineers in this room today. i'm confident that all of you will define a lot of how we will experience ai in how the world will experience ai in the future.

</details>

**Speaker 3**: 所以谢谢你们。

<details>
<summary>Original English</summary>

**Speaker 3**: so thank you.

</details>

**Speaker 10**: 我想对那边正在注入它的那个人大声说一句。就是你。好的。非常感谢。所以在你们的帮助下，我们正在让代理变得极其有用。那么现在的问题是，我们如何从它们身上获取价值，而且要知道，这不仅仅是关于 token 的魔法。我们对此有一个术语，也许你们也用过。我不知道屏幕上是不是叫价值最大化。

<details>
<summary>Original English</summary>

**Speaker 10**: i want to give a shout out to whoever over there is injecting it. that's you. okay. thank you so much. so with all of your help, we are making agents explosively useful. and so now the question is, how do we get value out of them and know that's not token magazine. we have a term for this that maybe you is as well. i don't know is an on screen value maxzine.

</details>

**Speaker 10**: 你知道，当我们与工程领导者交谈时，大多数对话都围绕着与价值最大化理念相关的一些主题。所以我们将讨论一些常见的议题，有些我们已经取得了很大进展，有些则还有更多工作要做。第一个是成本效率。每个人都想要前沿智能，对吧？每个人都想要最好的模型。比如在 Terminal Ventier 上，那就是 GPT 5.6。就像我说的，我们等不及让你们拥有它，但好吧，你们也想要尽可能多的智能。这就是效率发挥作用的地方。成本效率一直是我们相当长一段时间以来的重点，而且成果持续显现。

<details>
<summary>Original English</summary>

**Speaker 10**: so you know, when we talk to engineering leaders, most of the conversation is about some themes relating to the idea of value maxting. so we're going to walk through a few common topics that come up some things. we've already made a lot of progress and some things were actually there's a lot more progress to still be made. so the first one of these is cost efficiency. everyone wants frontier intelligence picker, a favorite evl. you want the best model. so with terminal ventier, for instance, that's GPP five point point six soul. and like i said, we can't wait for you to have it, but okay, you also want as much intelligence as you can get. and that's where efficiency comes in. cost efficiency has been a focus for us for quite some time, and the results are continuing to pay off.

</details>

**Speaker 10**: 例如，GPT 5.6 Turbo。我认为它就像……在基准测试中，它带来了 GPT 5.5 级别的智能，但成本只有一半，而且在基准测试中击败了一些相当知名的模型，但输入 token 每百万仅需 1 美元，输出 token 每百万仅需 6 美元。我把比较这些成本的任务留给你们，但这真是不可思议的价值。

<details>
<summary>Original English</summary>

**Speaker 10**: so for example, GPD five points six ter. i think it's like darark lue in there brings gp five point five level intelligence, but at half the cost and lunar there, beats some pretty notable models in this evl, but at only one dollar per million inper tokens and six dollars per million up protokens. i'll leave it to you to compare those cost, but that is insane value.

</details>

**Speaker 9**: 是的，真的，我们真的等不及看到你们所有人用 GPT 5.6 和这个新模型系列进行构建。接下来我想谈谈速度，对吧？GPT 5.3 Codex Spark 向你们展示了速度能达到什么程度，但我们也知道你们都想要前沿智能，你们不想要一个不够快的模型。你们希望它能以最佳状态运行。这就是 GPT 5.6。在 Rebrst 上运行，前沿智能。现在，每秒 70 个 token，我们等不及想看看你们下个月能用它构建什么。老实说，换个角度看，这就像在十秒钟内写出一篇相当可观的论文。而且这不仅仅是关于更快地得到一个答案，对吧？而是关于你能用这种速度做什么。你可以想象一个代理采用不同的方法，也许并行处理五六个，然后回来选择最好的一个，而所需的时间甚至还不够生成一个。所以我们真的很期待看到当你们拥有前沿智能时，这能带来什么。以这种速度达到最佳水平，它真的开始感觉不像是在等待 AI 响应，而更像是一个已经在向你们展示结果的同事。

<details>
<summary>Original English</summary>

**Speaker 9**: yeah, really, we really can't wait it to see all of you build with jup ty five point six, and these new family of models. now the next thing i want to touch on any speed, right? GP ty five point three could exspark showed you what speed gonna ck, but we also know that you all want frontier intelligence, you don't want to have a model. that's this not kind, as as hawhat, you can operate at the very best. well. this is GP ty five point six. so l running on a rebrst, the frontier intelligence. and now, seventy ty fifty tokens of second, we can't wait to see what you can build with this next month. and honestly, what that is perspective, this is kind of like having a pretty substantial pisol are written in like ten seconds. and it's not just about getting one answer faster, right? it's about what can you do with that speed. you can think about an agent taking different approaches, maybe like five or six and palel, maybe like, you know, coming back and picking the best one in the time you would have taken to not even generate, ate just one. so we really come way to see what that can and luck when you have funtier intelligence. the very best at that speed, it really starts to feel less like waiting for an eyes to respond and much more like a to worker. that's alalready shown you the results as it goes.

</details>

**Speaker 10**: 说到与同事合作，我能请大家举一下手，谁熟悉这种在办公室里看到的场景？好的，好的。嗯，你们很多人表现得很好，至少有些人……看，是的，很多人让他们的笔记本电脑保持打开状态，这样代理就可以继续工作。这很有趣，但你知道我们真正想要的是什么吗？我们希望能够合上电脑，我们希望能够并行运行许多任务，在它们自己的独立环境中隔离运行。

<details>
<summary>Original English</summary>

**Speaker 10**: speaking of working with coorkers, can i get to show hands who who is familiar with this kind of site in officers? okay, okay. well, a lot of your very well behave at least some people at thread. see, yeah, a lot of people are keeping their laptops open, so that agents can keep working. and this is funny, but you know what we really want is we able to shut computers um and we want to be able to run many tasks in parallel, isolated on their own box.

</details>

<!-- chunk 6/54 -->

### 从本地任务到云端任务的融合

**Speaker 10**: 实际上，我们从一开始就瞄准了这个目标。我们的第一个重大尝试是 Cursor Cloud，它很快就要迎来一些重大升级。但更好的是，当我们思考这个问题时，未来不应该再有本地任务和云端任务这种尴尬的区分，让你不得不决定在哪里运行一切。实际上，你应该拥有的是回到我之前说的那种状态：你只需要一个智能体，随时随地与它交谈任何事情，它应该能自己弄清楚：我需要做什么？哪个环境适合我的工作？然后使用任何可用的资源。

<details>
<summary>Original English</summary>

**Speaker 10**: now we've been to actually aiming at this from the start. our first major lash was Cursor Cloud, and it is due for some major upgrades coming soon. but better yet, as we think about this, the future shouldn't have this awkward distinction between like a local task and cloud task, and you have to decide where to run everything. really, what you should have is kind of going back with i'll saying earlier. you just have an agent, you talk to it wherever whenever about anything, and it should figure out okay, what do i need to do? which environment is right for my work and use whatever is available?

</details>

**Speaker 9**: 事实上，Theo 上周末就这个话题做了一个预测，那条推文非常精准，Alex。你觉得呢，是六个月之内还是更早？

<details>
<summary>Original English</summary>

**Speaker 9**: in fact, Theo made this prediction over the weekend on these very topic, and it's a pretty acute tweet like Alex. what do you think sooner later than six months?

</details>

**Speaker 10**: 我认为，也许不是那条推文的确切细节，但会比六个月快得多。

<details>
<summary>Original English</summary>

**Speaker 10**: i think the not maybe not the exact detail of the vibe of this tweet much sooner than six months.

</details>

**Speaker 9**: 我的意思是，以现在一切发展的速度，如果它真的更快到来，我一点也不会惊讶。好了，现在你可能在想，今天的现场演示在哪里？对于这次 AI Engineer 大会，我们想做点不一样的。我们认为这是一个非常独特的时刻，让我们所有人一起想象我们将如何工作、如何构建。所以我们想邀请一位特别的嘉宾，他一直在与智能体合作，真正推动我们变得更加……高效。我是说，OpenAI。所以，有请 Peter Steinberger 上台。交给你了。

<details>
<summary>Original English</summary>

**Speaker 9**: i mean, at the pace at which everything is going, i would not be surprised if it's sooner indeed um well. so now you might be wondering where's live demo today? well, for this AI Engineer, we wanted to do something a little different this time around. and we think it's a very unique moment for all of us to imagine how we work and how we build. and so we wanted to bring a special guest who's been working with agents and really has pushed us to be more eg. i pills, i OpenAI. so with that, please welcome to the stage to clocloother pepeter steinburger heater. take it away.

</details>

**Speaker 10**: 谢谢大家。

<details>
<summary>Original English</summary>

**Speaker 10**: thank you all.

</details>

**Speaker 11**: 大家早上好。你知道吗，我喜欢这张照片，因为它提醒我几个月来发生了多大的变化。我曾经在十个或更多的终端窗口中挣扎，总是等着其中一个完成，这样我才能“偷”回智能体并排队下一个任务。在一月份，那感觉像是生产力的巅峰。今天，这感觉有点傻。我以为我在编排任务，实际上，我才是那个瓶颈，我是调度器、路由器、内存。你知道吗，一开始，我通过十个终端与一个智能体配对。没过多久，我就像在管理十个直接下属。现在，我主要与一个长期运行的“经理”对话，它把工作委派给一个团队。对于棘手的工作，我仍然可以下沉，直接与一个“工人”配对，但我的默认方式已经改变了。我变成了一个管理着一个小型智能体公司的经理。三个变化使之成为可能：第一，服务解耦使得长期运行的任务足够可靠，我不再需要围绕会话协调进行优化。第二，让一个线程创建并监督项目。第三，当事情发生时，自动化通知同一个经理。所以我们有了持久上下文、警报和触发器作为你的循环。一旦这个循环开始工作，你就会发现下一个问题：瓶颈在不断移动。

<details>
<summary>Original English</summary>

**Speaker 11**: good morning, everyone. you know, i love this picture, because it reminds me just how much has changed in a few months. i was struggling ten or more terminal windows always waiting for one of them to finish. so i could steal the agent and queue network in january that feels like peak productivity today. it feels a little bit silly. i thought i was orchestrating really. i was polling. i was the scheduler, the router and memory, you know, at first, i paired with one agent with ten terminals. i wasn't long appearing, i was managing ten direct reports. now i mostly talk to a long running manager which delegates work to a team for tricky work. i can still drop down and pair directly with a worker, but my default changed. i managed to manager of a small company of agents. three changes made it possible, number one services decoupling made long running tasks reliable enough that i stopped optimizing around for sessions coordination. let's one thread create and steer projects and third automation notify the same manager when something happens. so we have persistent context and triggers as your loop. and once the loop starts working, you discover the next problem, the bottleneck keeps moving.

</details>

**Speaker 11**: 你知道吗，去年，我主要受限于 token。现在，我加入了 OpenAI，解决了这个问题。我知道，我知道，这个策略不能规模化。然后我的限制转移到了计算机的算力上。所有这些线程同时运行，我的 MacBook 开始像喷气发动机一样轰鸣。这主要通过使用测试盒子解决了，这样智能体可以在另一台机器上运行测试。现在，我主要受限于注意力。与 token 或算力不同，我不能简单地增加更多。所以今天最重要的技能是决定把注意力花在哪里。我仍然会盯着智能体看，看着代码飞速闪过。我知道，我知道，这感觉很酷。但对于早期的模型，这是必要的。你知道吗，你看到智能体走向一个方向，你不喜欢，你就按 Escape，你“偷”回控制权。但最新一代的模型在理解意图方面非常出色，以至于看着智能体生成代码有点浪费时间。

<details>
<summary>Original English</summary>

**Speaker 11**: you know, last year, i was primarily constrained by tokens. now i fixed that for joining OpenAI. i know i know the strategy does not scale, then my constraint shifted to compute on a computer. all these threads run the same time. and my MacBook started sounding like a jet engine that's mostly fixed by using test boxes. so agents can run test on a separate machine. now i'm primarily constrained by attention, and unlike tokens or compute, i can't simply add more of it. so the most important skill is today is deciding where to spend it. i'm still staring at the agent. well, the code flashes by i know i know it's it feels cool. but with the earlier models, this was necessary. you know, you see the agent going in a direction, you don't like you hit escape, you steal it. you steal it back. but the latest generation of model is so good at understanding intent that it's a little bit of a waste of time to watch the agent generate code.

</details>

**Speaker 0**: 想象一下，有人在我的一个开源项目上提交了一个 issue，“经理”被唤醒，根据项目目标、笔记和愿景进行评估，然后决定是否合适。如果合适，它创建一个“工人”任务。“工人”进行调查、实现更改、运行测试，然后另一个智能体可以审查结果。我不需要看着那些智能体工作，或者消费每一条中间消息。当“经理”需要我时，它会返回一个 PR、原始 issue、提议的 diff，可能还有一个视频，甚至是一个我可以 VNC 进入的运行中构建。我审查一次，留下一条笔记，我可能批准。循环继续，检查通过后它就可以合并。智能体运行内部执行循环，我设定方向，并在外部循环中做决策。

<details>
<summary>Original English</summary>

**Speaker 0**: imagine, someone files an issue on one of my open source projects, the manager wakes up, reads it against the projects, goals, notes and vision, and decides better. it might be a fit if it does, it creates a worker task. worker investigates implements the change, runs the tests, and another agent can review the result. i don't need to watch those agents work or consume every intermediary message. when the manager needs me. it returns a pr, the original issue that propose diff, maybe a video or even a running build. i can vnc into. i review once i leave a note, i may approve. the loop continues, and it can land after the checks pass, the agent runs the inner execution loop. i set the direction, and i make decisions in the outer loop.

</details>

**Speaker 0**: 你知道吗，Paul 已经在运行这个的一个版本了。他把它叫做他的“参谋长”。它每十分钟醒来一次，协调他的待办工作。智能体创建线程和侧边栏，这样 Paul 可以在工作需要额外指导时随时加入。你知道吗，一旦“经理”有了很长的生命周期，回到 TTY 感觉就是不对的。Cursor 已经可以在主机之间移动工作。OpenAI 有网关和笔记，但 Meta 感觉像是最终形态。我甚至不想去思考我在哪里工作。工作智能体应该能够连接到我的任何一台机器。它们应该知道哪些工作可以在云端完成，或者哪些工作需要我的本地机器。“经理”不应该是你应用里的一个会话陷阱。它应该是一个智能体，我可以通过 Slack 发短信给它，或者从任何地方与它交流。真的，为什么我不能和我的智能体对话，让它为我设计整个循环？我们还没有解决这个问题。模型的发展速度超过了基础设施和组织围绕它们的设计。设计这些东西是下一个工程问题。这就是你们所有人的用武之地。未来不是二十个终端，而是更好的循环。让我们来构建它们。谢谢。

<details>
<summary>Original English</summary>

**Speaker 0**: you know, Paul Paul Salt is already running a version of this. he painted his chief of staff. it wakes up every ten minutes, and it coordinates his to-do work. the agent creates threads the sidebar, so Paul can jump in. whenever the work needs additional steering, and you know, once the manager is long lifetime, going back to TTY just feels wrong. Cursor can already move work between hosts. OpenAI has a gateway and notes, but Meta feels like the final form. i don't even want to think where i work. work agent should be able to connect to any of my machines. they should know which work can be done in the cloud, or which work requires my local machine. the manager shouldn't be a session trap inside your app. it should be an agent that i can text steer from slack or hear from wherever i am. really, why can't i talk to my agent and have it design the whole loop for me? we haven't solved that yet. models are advancing faster than the infrastructures. and organizations around them designing those things is the next engineering problem. and that's where all of you come in the future is not twenty terminals. it's better loops, let's build them. thank you.

</details>

### 欢迎与开场

**Speaker 3**: 请大家和我一起欢迎 AI Engineer 联合创始人、Latent Space 编辑 Swyx。

<details>
<summary>Original English</summary>

**Speaker 3**: please join me in welcoming cofounder of AI Engineer and editor at Latent Space Swyx.

</details>

**Speaker 5**: 哎，我们本来应该有来自……呃……Journey 的……呃……今天。呃……不幸的是，他没能来到美国，但我们让他连线分享他的……呃……生活。我希望……我希望他那边能看到我们。呃……我还想感谢大家的一件事是，这是一个非常、非常大的社区努力。我非常感谢 OpenAI 团队和 Microsoft 为开幕带来的能量。但是，呃，你们所有人都在组织所有这些边会活动，其中有一个，我想特别提一下，就是 AI Engineer Kids Day。我们知道，呃，这是一个非常……呃……成人专业系列的活动，但我们也关心下一代工程师。所以我想播放一个视频。

<details>
<summary>Original English</summary>

**Speaker 5**: so we actually were supposed to have to shine from the uh journey us today. um unfortunately couldn't make it in um the the united states, but we have him beamed in to share our your life for. i hope i hope he's where team sees us is seeing him live. um one thing i also wanted to um thank people for doing is this is a very, very big community effort. i love. thank you so much to open to open AI team for and to Microsoft for bringing the energy is opening things. but even uh all you guys have been organizing all these side events um and one of them, i just wanted to shout out in particularly AI Engineer Kids Day um know are very asset of adult professional series. but we you know, we also care about the next generation of the engineers. so i wanted to play the video.

</details>

**Speaker 6**: 我们现在在旧金山的 AI Engineer World Fair，这是世界上最大的 AI 工程师和企业家聚会，我们正在举办有史以来第一次 AI Engineer Kids Day。

<details>
<summary>Original English</summary>

**Speaker 6**: we're in San Francisco at AI Engineer World Fair, which is the biggest collection of AI engineers and entrepreneurs in the world, and we're holding the first ever AI Engineer Kids Day.

</details>

**Speaker 7**: 我真的很喜欢这个工作坊系列，因为我们正在激励下一代 AI 技术专家。这些孩子是未来将从事 AI 工作的人。他们非常 AI 原生，将成为 AI 专家。

<details>
<summary>Original English</summary>

**Speaker 7**: and i really love this workshop series because we're inspiring the next generation of AI technologists. these kids are the people who will be doing AI in the future. their very AI native will be the AI experts.

</details>

**Speaker 8**: 让这个工作坊与众不同的是，传统上，当你用……呃……游戏……工作时，如果你不使用 AI，会花很长时间，而且你走不了那么远。但在这个工作坊里，因为我们使用了……呃……WordEAX，我们能够比通常在工作坊中走得更远，并且能够探索比通常更高级的概念。

<details>
<summary>Original English</summary>

**Speaker 8**: something i makes this workshop stand apart is traditionally when you work with three the games. if you don't use AI, it takes a long time. and you won't get as far. but in this workshop, because we use WordEAX, we were able to get a lot further than you normally would in a workshop and be able to explore a lot more advanced concepts than normal as well.

</details>

**Speaker 9**: 来，这里有一个有趣的积木块，你可以训练 AI 并创建 AI 和 SAS 来真正创建游戏世界。

<details>
<summary>Original English</summary>

**Speaker 9**: come, here is fun block of lother, and you can train AI and create AI and SAS to create game really world.

</details>

**Speaker 5**: 为孩子们的活动鼓掌。谢谢 Stephen Chin 主持这个活动，基本上为我们未来十年、十五年培养了后备力量，因为我们总得想办法成长。呃……所以话不多说，我们将请出 Anscheng 来做他的主题演讲。如果我们都准备好了。

<details>
<summary>Original English</summary>

**Speaker 5**: give it up for the kids um events. thank you, Stephen Chin for running that um and basically generating the funnel for us for ten, fifteen years from now for our next next ten years, we have to grow somehow. um so without further ado, we're going to bring Anscheng for his keynote. if we're all set.

</details>

**Speaker 1**: 嘿，你好吗？

<details>
<summary>Original English</summary>

**Speaker 1**: hey, how are you?

</details>

**Speaker 10**: 对，我在这里。

<details>
<summary>Original English</summary>

**Speaker 10**: right? i'm here.

</details>

**Speaker 5**: 呃，是的。呃，见到你真是太好了。呃，Shasha 你一直在和……呃，是的，新加坡……呃……交谈。显然，J L Mh 是当下的热门话题，对吧？呃，楼下展区有一个很棒的展位。呃，我想很多人只是很兴奋能听到你关于……呃……AI 领域正在发生的事情。所以，如果你想开始的话。

<details>
<summary>Original English</summary>

**Speaker 5**: uh, yes. uh, it's really good to see you again. uh, Shasha has you've been speaking with, yeah, you Singapore. uh and obviously, J L Mh is uh the talk of the town, right? uh there's an amazing booth downstairs in the expo. and uh, i think a lot of people are just very excited to hear from you on. uh, what's going on as AI. so if you want to take it away.

</details>

**Speaker 10**: 是的，抱歉，再次，你知道，不能亲自到场。我有一个整个团队来到了城里，我们有一个展位。所以如果你有任何问题，请随时在 LinkedIn 上联系我。同时，你也可以找我的团队和我们的展位。因为我无法看到我的幻灯片，所以我需要 Swyx 帮我。帮我过一下所有的幻灯片。是的，你来分享，比如我们现在在哪张幻灯片上。

<details>
<summary>Original English</summary>

**Speaker 10**: yes, sorry, again, for not being, you know, in person, i have a whole team coming into the town, and we have a booth. so you have any questions feel free to reach out to me on LinkedIn. and also, you can look for my team and our booth. and since i cannot see my slides, though, i will need Swyx to help me. i live through all the slides for me. yeah, you get to share are like, which which slides we are in right now.

</details>

**Speaker 5**: 是的。所以我们正在开场幻灯片上。我们在谈论智能体和 AI。

<details>
<summary>Original English</summary>

**Speaker 5**: yeah. so we're on the opening slide. we're talking about intelligence and AI.

</details>

<!-- chunk 7/54 -->

### 介绍公司、模型名称与品牌定位

**Speaker 10**: 好的。所以，是的。你可以看到，这是我们第一次向大家介绍 John for forpto。呃，我们也会分享一些关于 ZZWAI 和 GOM 的内容，因为可能有人会觉得 Z 到 AIGGN 与它们无关，对吧？你们是你们的公司，不是 Z 到 AI，或者你们的模型叫 Z one 或 Z two。你们可以在这里找到我的 X 账号和我们公司的 X 账号。所以你可以搜索我的名字，应该是 They Should Really 和 ZAI org，然后关注他们以获取后续信息。好的，我们可以进入第二张幻灯片了。实际上，我看不到幻灯片。我试一下。是的，我尽量确保它是正确的。所以这家公司实际上叫做 Zip。可能有些人听说过它，而模型的名字叫 GOM。实际上，它不是一个品牌名，而是一个通用术语。GOM 实际上代表“通过自回归空白填充训练的通用语言模型”（General language model by training with auto aggressive blank billing）。那篇论文是在 2021 年发表的。所以实际上，我们是首批在自回归语言模型上进行探索的实验室之一，与 OpenAI、Atopic 和 DeepMind 同时期。即使在今天，我们虽然不再使用 GOM 作为架构，但我们仍然使用 GOM 这个名字作为我们的品牌名。所以我们使用了 GOM 5.1、5.2，它成为了我们最引以为豪的产品和模型之一。

<details>
<summary>Original English</summary>

**Speaker 10**: okay. so yeah. so you can you can see that it's the first time for us to introduce john for forpto. uh ght going to to the the le also also we are going share something ababout, ZZWAI and GOM, because maybe people will think z 到 AIGGN, they are irrelevant, right? you are your companies, not z 到 AI or your models called z one or z two. and you can find my x and our companies x account here. so you can can search for my name is they should really and ZAI org, and you can follow them for the follow ups. so yeah, we can go to the second slide. it actually, i cannot see the slide. so try ed. yeah, i try to make sure that it is correct. so the company actually is called zip. maybe some people i've heard of it and the models ls, it's it's called GOM. actually it's not a brand name. it's a generic term. so GOM actually represent general language model by training with auto aggressive blank billing. and that paper was published back in twenty twenty one. so actually, we were the one of the first labse to do w explraations on our ge riguage models. so at the same time, with open AI and at topic and deep mine. and even today, we we no longer use GOM as the architecture, we still use the name GOM as our brand name. so we used JGOM five point, one, five, five point two, two, and it become like one of our, like most prouh product product and model.

</details>

### 探索智能上限：从推理到智能体能力

**Speaker 10**: 我们寻找的第二件事是智能上限。就智能而言，我们可能觉得它代表 IQ 之类的东西。当 Deep Sea 推出 one 或 one 时，你们在谈论模型解决数学问题、物理问题的能力。但智能的真正含义并不仅仅是 IQ 或物理问题。所以从 GOM 4.5 到 GOM 4.4 和 4.7，我们正在探索几件事，比如推理、编码和智能体能力。正如你从幻灯片中看到的，我们添加了最后几行。我经常还没完成那张幻灯片。是的。好的，它回到了那两张幻灯片。

<details>
<summary>Original English</summary>

**Speaker 10**: and the second thing that we look for is intelligence upper bang. so in terms of intelligence, we we may feel that it's represent IQ something something like that. and when deep sea launched one or one launched, you are talking about the models capability to solve math problems, physics problems. but what actually intelligence mean is not just like IQAME or other other our physics problem. so from GO and four point five to GO and four, four and seven, we are exploring like several things is like reasoning, coding aggentic capabilities. so as you can see from the slides, so we add like, uh yeah, the last last liyes. we i often haven't like finished that slide. yeah. so okay, yeah, it just go back to the two two slights.

</details>

**Speaker 5**: 我没有背景。谢谢。我想要你。你不要误解那些没有背景的人，为什么？好的，你知道，是的，好吧。

<details>
<summary>Original English</summary>

**Speaker 5**: i don't have a background. thank you. i want you. you don't don't underthank makers that don't have backwartons like why? okay, you know, yeah, ay good.

</details>

**Speaker 10**: 是的，没关系。因为人们想看 GOM 在 phypon two 上的表现，他们不想看你展示 GOM 在 five point one 或 five 上的结果，而 GOM 在 phppon on to 上专门针对编码和智能体任务进行了优化。你可以从图表中看到，因为有很多谣言说你的模型是否应该解决这些难题。但实际上，我想和大家分享这张幻灯片。你可以看到它的性能介于 OpenAI 的 4.7 和 8 之间，我们使用了最难的题目，比如 deps。我们使用了 OpenAI 几分钟前提到的 turnal bench took one one，所有长周期任务和基准测试都表明，其能力至少与 OpenAI 的 4.7 相当，并且相比 one pone way 有显著提升。我还为 red g ah 添加了一个名为“高”的思考级别。因为我们也注意到，随着任务难度的增加，模型会消耗更多 token。而且我们非常关注 token 效率。所以这是我们第一次为思考预算添加“高”级别，但即使没有思考，非思考模型也比 five point one 的思考模型更好。所以我认为这对于开源权重模型来说是一个巨大的进步，确实令世界印象深刻。很多人最近都在谈论 GOM 在 phypon unu 上的表现。好的，下一行。

<details>
<summary>Original English</summary>

**Speaker 10**: yeah, never mind. yeah, because people want want to see GG on phypon two, then they don't want to see you like GI on five pon, one or five, while like g on phppon on to actually specializing calling an genttasasks. you can see from the grab because there are a lot of rumors whether you are model supposed to metholes fabble. but actually, i want to share this lives to all of you. so you can see is somewhere between opens four pseven and opopen eight, and we use the hardest problems like deps. we turnal bench took one one, which was mentioned by the open IT uh several minutes ago, and all the like long horizzon task and benchmark shows that the capabability is on part wer, a least opopen s four th and seven, and it shows a significant improvements over one pone way. i also forred red g ah weopen until we add a thinking level called high. so because we also notice, as we move to the harder task, a my consume more tokens. and also we we care a lot about the token efficiency. so it's the first time we at the high level for thinking budget, but even without thinking, the non thinking model is better than the foypon one thinking model. so i think it's a huge improvement for the open weight model that's really impresss the world. and my people are talking about g and pponunu lately ok ay next next line.

</details>

### GOM 不仅仅是编码模型

**Speaker 10**: 我想提的一件事是，GOM 不仅仅是编码模型，因为人们在 pyclock 编码任务中使用它。实际上，我们在编码之外训练了很多东西。例如，我们改进了 GDP 投票和数学问题。坦率地说，我们也很关心数学问题。而且，我们还训练了很多与角色扮演和通用聊天相关的东西。我们希望改进模型的每一个方面，所以你可以从人工智能分析指数中看到，它远远领先于其他开源权重模型，并且接近前沿模型。所以我想说，如果你还没有体验过 GOM，你可以用 GOM 进行通用聊天，用它来处理你的日常工作流程，不仅仅是编码，你可以探索模型在编码范围之外的能力。

<details>
<summary>Original English</summary>

**Speaker 10**: and one one thing i want to mention is that GOM is more more than coding model because people use it in pyclock cocode tags s open cobut. actually, we have train a lot of things outside coding. for example, we improve blood in gdp ballot and also math problems. we also care about math problems, frankly speaking. and also, we train a lot of thing um related to role play general chat. we want to improve every aspects of the model so you can see from the artificianalysis intelligence index actually leads the other open way model a lot and close to the frontier model. so i want you, if you you haven't expericed GOM yet, you can use GOM to do general chat, use it to process your daily workflow, not just for coding, but you can explore the model like beyond the coding scope.

</details>

### 开源权重的理由：安全、多样性与共同塑造未来

**Speaker 10**: 下一张幻灯片。GOM open to 是一个开源权重模型。所以人们总是问我，为什么你们要开源权重？你们关心自己的业务吗？或者你们担心失去市场给一些影响力竞争者吗？但实际上，我们开源权重有几个原因，因为用户有需求，而且需求一直存在。如果我们能满足他们的需求，我认为开源模型对我们来说是可以的。例如，如果我们的用户想要安全和控制，我们想构建 press，我们可以在某些情况下开源模型。如果一个企业或政府，尤其是在西方世界，想要使用我们的模型，我们开源权重，上传到 Hugging Face，这样他们就可以在本地使用模型。我认为这对整个生态系统探索模型非常有益，尤其是当能力接近前沿模型时。第二，如果人们想要多样性。就多样性而言，我指的是在法律、金融、安全等领域的能力，他们可以在模型中找到，所以我们需要开源模型让他们进行微调。例如，Harvey 正在微调 GOM 5.1。也许他们之后会考虑微调 GOM 5.2。我和很多其他公司谈过，他们也在考虑微调 GOM，作为他们下一步或下一个策略，以区别于其他应用公司。第三，如果我们的客户或个人想要共同设计和预测未来，有时他们需要看到模型的架构。他们需要看到你训练模型的配方。所以我们希望使之成为常态。我们希望使之成为主流。所以我们希望与客户和开源社区共同塑造未来。所以我认为我们的需求已经涵盖了这些，有些部分相互契合，就像没有你们所有开源社区参与者，比如 on flaws 和 vidia，以及一些个人、超级开发者，他们也是其中的一部分，就无法实现一样。非常感谢像 Peter 这样的应用构建者，对吧？因为开源不仅仅包括开源模型，还包括开源软件和其他各种支持。所以你们所有人都在支持。你们现在所做的一切推动我们制造出更好的模型。我认为你们是真正的英雄。

<details>
<summary>Original English</summary>

**Speaker 10**: next slience and gm open to is a open way model. so people always ask me, why do you open weight? so do you care about your business or like do you care about losing market to some influence riders? but actually, we open the weights for several things because their users needs and they are always needs. if we can meet their needs, i think it's okay stempally ok for us to to open the model. for example, if our users wants security and control and we want to build press, we can open and wait the model force for some cases, if an enterprise or government, especially in the western world, want to use the model we open way, we outload to the hugging phase so that they can use the model on prennce. i think it's very beneficial for the whole ecosystem yet to explore the model, especially when the capability is, is close to the frontier model. and second, if people want diversity. so in terms of diversity, i mean, the capabilities in legal finance security, they can find in the model, so we need to open the model to let them find tune. for example, harvey is fine tining GI five point one. and maybe they are thinking about the fine tuning GIF five point two afterwards. and i have like talked to a lot of other companies. they are also thinking about fintune GON as they are the next step or next strategy to defretiate themselves from other application compons. and third, if our customer or an individual want to coal design and predict the future, sometimes they need to see the architecture of the model. they need to see the recipe of how you train the model. so we want to make the norm. we want to make my bats. so we want to code shape the future with our customers with the open source community. so i fake our neys and already costs this, some pretty i fits into each other and GF, like one to coucouldn't sexy without you all the open stres community players, like on flaws and vidia, and and some like individuals, super developers, they are part of it. and thanks a lot to application builters like peter, right? because open source doesn't just include open source model, but also open source software and open source other sorts of support. so all you are support. and what do you you're doing right now pushus to to make better models? i think um you are the true hero.

</details>

### 分享资源：技术博客与 Zecode 测试平台

**Speaker 10**: 最后，我想分享一个很好的资源，让你了解 GOM 和 phypon two，那就是我们的技术博客。实际上，在那篇技术博客中，我们分享了几件事，比如我们的 Hugging Face 仓库，你如何尝试 GOM 和 phypon two，如何尝试内部聊天机器人代理？还有，你可以调用 API。而且，我们有一个编码平台，比如 codex 或 clock cloloss swipon to you，让你作为个人使用你的 token。我们还分享了一些关于我们训练流程和训练配方的内容，你可以理解为什么它是一个好模型。所以模型背后有很多东西，不仅仅是一个拥有大量数据的模型。我们还有出色的技术支撑着模型，所以你可以自己探索模型。我们可以看到我们经历了哪些困难。最后一张幻灯片，实际上，还有一件事。这是我们第一次向整个社区分享 zecode。这另一件事是我们实际上有自己的测试平台。zecode 是为 GOM 在 phypon unu 上设计的，但也支持所有前沿模型。你可以自带密钥。你可以连接到 zecode。实际上，我认为操作方式类似于 codex。实际上，你可以尝试一些技术，比如 goal 或其他紧凑技术，就像我们在 codex 和 cococode 中所做的那样。这个测试平台非常适合 John，也欢迎你。如果你还没有体验过，你可以搜索 z code，或者你可以去展台。我们有团队成员向你展示这个测试平台，欢迎来展台，欢迎以后和我交流。下次我一定会在旧金山和大家交流。是的，谢谢。

<details>
<summary>Original English</summary>

**Speaker 10**: and the last, i want to share AA great resource for you to go through GO. and pypon two is how our tech block. so actually, in that tech blog, we share several things like our hugging face reprepall, how you can try the joo and phypon two, how how can try the inside chechep lot agent? and also, you can call the api. and also, we have a coding plan like the codex or clock cloloss swipon to you, you to use your tokens as individuals. and also we share something about our traraining peline training recipe, which you can understand why it's a good model. so there are a lot of things behind the behind momodel, not just um AA model that had great data. we also have fantastic technologies behind the model, so you can explore the model yourself. we can see what difficulties we have gone through and blast slides, actually, it's kind of a one more thing. so it's the first time we share zecode to the whole community. so that one more thing is we actually have our own harineys. the zecode actually is spilled for GI fiponunu, but also support all frontier models. you can bring your own key. you can connect to zecode. actually the 对有, i think the operations is similar to codex. actually, you you can try some techniques, like goal or other like compact technique techniques, like what 've din in in cotex and cococode. and this harneis ethcaates, the perfect one for john, welcome, too. if you have an experience it, you can just search z code, or you can go go to bbooth. we have our team members showing this harneys to you and welcome to darbooks, and welcome to like talk to me in the future. and next time i've definitely be in sf talking to everyone. yeah, thanks,

</details>

**Speaker 5**: 非常感谢你。嗯，相信我，第一次参加工作坊时，我被禁止入境参加自己的会议。所以我完全理解这种感觉。呃，一切都好，非常感谢 HYI 团队。

<details>
<summary>Original English</summary>

**Speaker 5**: thank you very much. um so trust me, the very first worlspare. i wasn't allowed to come back in the country for for my own conference. so i know exactly this feeling. uh it's all good um HYI team really appreciate them. uh,

</details>

<!-- chunk 8/54 -->

### 世博会的意义与Hugging Face的参与

**Speaker 5**: 他们付出努力，真心想见你，他们来这里就是为了见你。这就是世博会的全部意义——把顶尖的LDS、IHH公司以及所有参与者都聚集在一个地方，这样你们就可以一起做生意。你可以见到你所用模型背后的那些人，问那些他无法公开回答、但你可以私下询问的问题。嗯，我也很自豪他能展示那份Hugging Face的名单。你知道，前八名贡献者中，我们有四位在世博会现场。嗯，我们正在与NVIDIA、Unsloth、Alama以及所有那些微调公司合作，为接下来几天你将在本地展区看到的推理演示做准备。嗯，说到这里，非常感谢你，Shaine。嗯，我要把时间交给下一位嘉宾。我想我可能是在做Alee的工作。所以，嗯，我们接下来要和Hugging Face以及MiniMax聊聊。

<details>
<summary>Original English</summary>

**Speaker 5**: making the effort they really want to meet you they are here to meet you. and this is the whole point of the world's fair to bring the top LDS's IHH companies and all in one place. so you can do business together. you get to see the people behind the models that you use, ask the questions that he cannot answer in public, but you can ask in private. um i'm also proud he showed that list of hugging face. uh you know, top contributors think we are four for eight. uh in that list, uh present at walls. uh. we're working with NVIDIA and Unsloth and Alama and all those of tuners as well um to make a sort of the inference at the local tracks that you're going to see over the next few days. um with that, thank you so much as Shaine. um i'm going to initiate the next couple folks. i think i might be doing Alee's job here. so um we will talk to Hugging Face next and MiniMax.

</details>

### 介绍Hugging Face与MiniMax

**Speaker 2**: 谢谢。

**Speaker 11**: 天籁，现在加入我们舞台的是Hugging Face的联合创始人兼首席科学官，Thomas Wolf。

**Speaker 12**: 大家好，很高兴你能来到台上，很高兴你能来。

<details>
<summary>Original English</summary>

**Speaker 2**: thank you.

**Speaker 11**: Tian Lai joining us on stage is the co founder and chief science officer at Hugging Face Thomas Wolf.

**Speaker 12**: everyone, nice to have you on stage nice to thanks for having me.

</details>

**Speaker 13**: 是的。

<details>
<summary>Original English</summary>

**Speaker 13**: yeah.

</details>

**Speaker 12**: 所以，我想你今天行程很满，因为你刚刚发布了GMM，它目前在开放模型排行榜上排名第二，任何人都可以使用。现在我们还有了Qwen。所以基本上，你连续拥有了所有顶尖模型，至少是顶尖的开放模型。我们也很高兴请到了Lei，她有着非常精彩的人生经历。她去了美国宾夕法尼亚州，在纽约大学攻读博士，在Yann LeCun的实验室工作，研究JEPA。但我们决定今天不讨论JEPA，那是改天的话题。然后她没有加入当时在纽约的Hugging Face，而是决定加入MiniMax。对于那些可能不了解全球所有知名实验室的人来说，这可以理解，因为我认为现在大概有64个开放实验室。MiniMax是中国顶尖的AI独角兽之一。所以，除了DeepSeek、Qwen、Yi和LM，你刚刚也看到了，我们还有MiniMax。他们是一个极其有才华的团队，正在争夺第一的位置。MiniMax最新的版本是M3，就在今年六月早些时候发布，当时是顶尖模型，顶尖的开放模型，非常令人印象深刻。这个模型有很多非常有趣的特点。我们会快速深入探讨，然后专门聊聊MiniMax，这很棒。

<details>
<summary>Original English</summary>

**Speaker 12**: so i think you're on for a trip today because you just so um GMM, which is a current number um two under the open model leaderboard that everyone can use. and now we have Qwen too. so so basically, you would have all the top models at least the top open. so smother in a row, and we are very likely to have Lei who has pretty amazing path in life. so she got to the US Pennsylvania. she was studying doing PhD at NYU in the lab of Yann LeCun working on JEPA, but we decided we won't talk about JEPA today, right something for another day, and then instead of joining Hugging Face, which was in New York. so at that time, she decided to go join MiniMax. so for those who maybe don't know all the all the known labs around the world and you're forgiven, because i think there's like sixty four and the known labs right now, MiniMax is one of the top of what we call the AI dragons in china. so there's DeepSeek there. well, known Qwen and Yi and LM that you just saw. and we have a MiniMax. they are extremely extremely talented team fighting for the first spot. so the the latest release of MiniMax was M3 just just earlier earlier in June, which was the top model at the time top open model, very impressive. there's lot of very interesting things about this model. so we will quickly dive in them and then talk a bit very specific about MiniMax, which was great there.

</details>

**Speaker 1**: 哎呀。

<details>
<summary>Original English</summary>

**Speaker 1**: oh.

</details>

**Speaker 12**: 那么，也许请Lei先开始介绍一下。你能给我们讲讲M3的一些情况吗？你喜欢这个模型的哪些方面？发布过程如何？

<details>
<summary>Original English</summary>

**Speaker 12**: so maybe you Lei to start a little bit. can you can you give us you know a little bit of your of of of M3, what you like about this model? how is the release?

</details>

**Speaker 13**: 是的，M3。我们在本月初发布了M3，它是一个小型MoE模型，总参数量为4000亿，激活参数量为200亿。但它在编码性能和多模态理解方面都非常强大。嗯，这就是开放模型通常不具备的——模型不仅能处理编码，还能理解视频和图像。并且它拥有超长的上下文，达到100万token。嗯，我们推出了新的架构，叫做MiniMax稀疏注意力（MSA）。所以我们确实将这三者结合在一起，因为我们知道它们在未来的人工智能应用中将非常重要：编码能力、智能体能力、更长的上下文以及多模态理解。嗯，是的，我认为这就是这个模型非常有趣的地方。

<details>
<summary>Original English</summary>

**Speaker 13**: yeah, M3. we released M3 earlier this month, and it is a small MoE model with four hundred and four hundred billion total parameters and twenty billion activated. but it is very capable in terms of both coding performance and also it understands multimodal. so um that's what open source models don't usually have is that they can the model can only only deal with coding, but it can also understands videos um images. and it has a super long context of one million. um we out our new architecture called MSA MiniMax sparse attention. so we you we really put these three things together because we know that they are they will be very important in future AI applications, coding capability. it is agentic capabilities longer context and multimodal understanding. um yeah, i think that would be very interesting about the model.

</details>

### 深入探讨长上下文与稀疏注意力

**Speaker 12**: 是的。所以这个模型有很多值得深入探讨的地方。而且它可能仍然是前五名开放模型中唯一一个真正支持多模态的。我们可能需要先谈谈长上下文，因为它是第一个真正实现100万token长上下文并且功能可用的模型。你们还推出了MiniMax稀疏注意力，这是一种使其高效的技术，你们也广泛地发表和分享了。你能谈谈这个吗？也许谈谈这个项目是如何从注意力机制发展到实现长上下文的。

<details>
<summary>Original English</summary>

**Speaker 12**: yeah. so so there's a lot to unpack in this model. and and it's it's it's still i think the only top five model open model that's actually multimodal models. so we need to talk about that maybe first about the long context, because there was also the first one that's really had this real one million token long context as actually functional. and you guys had all also the the MiniMax sparse attention and which is this one technique to to make that efficient that you also published and and share extensively can can you talk a bit about this? maybe how the project went from from the attention and how to make this long context.

</details>

**Speaker 13**: 是的，关于长上下文的故事，甚至可以追溯到MiniMax-01和MiniMax-02，当时模型实际上能够处理1000万token的上下文，1000万token，是的。但那时它不是一个智能体模型，对吧？它只是，比如说，输入一本书，它就能给出书评，诸如此类。所以我们意识到，更长的上下文实际上解锁了很多能力，尤其是在与用户交互时。现在，当智能体与整个环境交互，获取所有轮次的响应，进行多轮对话时，较短的上下文不足以执行这个版本的复杂任务。所以，我们必须拥有更长的上下文。因此，我们通过MiniMax稀疏注意力来实现这一点，嗯，这是一种可扩展且设计简单的架构。所以，从更高的层面来说，它有一个索引框架，可以在更高层次上选择上下文中哪些内容更重要。然后我们有一个稀疏注意力分支，它在选定的块上执行计算，以实际完成任务。是的，就是这样，我们真正设计了一个优雅的架构，以便我们能够扩展上下文，并在未来扩展模型规模。

<details>
<summary>Original English</summary>

**Speaker 13**: yeah, i was see the story about long context went back to even MiniMax-01 and MiniMax-02 or one where the model was actually was able to perform context of ten million, um a token context ten million, yes, but then it was not an agentic model, right? it was just, for example, dump in a book, it would be able to give reviews on it. a step like that. so what we realized with that, you know, longer context, actually, it unlocks a lot of capabilities and, especially when interacting with users. and now, when you know the agents is interacting with the whole environment and getting all the poll responses getting multi rounds, the shorter context wouldn't be enough to perform the complex task for this version. so, we have to have a longer context. and so what we pursued was with our MiniMax sparse attention um which you know was the architecture that was scalable, and had a simple design. so i would say, from a higher level, it has an index framework um that you know selects on a higher level. what is what matters more in the context? and then we had a sparse attention branch that calculates performs the calculation on the selected blocks um to actually perform the tasks. and so yeah, like that, we really designed an elegant architecture so that we can scale the context. and then scale the model size in the future.

</details>

**Speaker 12**: 太棒了。对于在这个领域待了相当长时间的人来说，我们有过很多关于注意力的工作，对吧，稀疏注意力、平方注意力。还有很多线性注意力。然后不知何故，当Flash Attention出现时，所有这些都消失了，我们发现我们只需要更高效的计算。现在，我喜欢我们回归到第一性原理思考：什么是注意力？我们如何让它更高效？所以，100万token是疯狂的，对吧？GPT-2是1024个token，当时每个人都觉得，“哇，那真大。我们永远不需要更多了。”你认为未来会怎样？就像Jevdin在演讲中提到的，一天内处理你所有的token。100万token，那绝对是某种程度的token注意力。

<details>
<summary>Original English</summary>

**Speaker 12**: with that, that's beautiful. i like for for those of being in the field for quite some time. we had a lot of work on attention, right sparse and square. and there was a lot of linear attention yeah. and then somehow all of these disappeared at some point when Flash Attention came around, we discover we just needed more efficient compute. now i like how we come back to thinking, you know, first principle, what is attention? how can we make that more efficient? so one million token is crazy, right? GPT-2 was a thousand twenty four, and everyone was like "wow, that's really big. we never need more." do you see this coming like going the future like Jevdin was speaking media a day your tree. i'm token, that's definitely something can token attention.

</details>

**Speaker 13**: 这绝对是我们可以去探索的方向。上下文长度方面，是的，这绝对是非常值得探索的事情，而且这种架构设计，连同硬件，都需要大量的研究投入。

<details>
<summary>Original English</summary>

**Speaker 13**: that's definitely something we can explore it. words that's the length of the context. definitely, that's something something that's very deciding to explore with, and something that architecture design, along with hardware, will require a lot of research onto that.

</details>

**Speaker 12**: 是的，你认为还有很多唾手可得的成果。今天我们看到OpenAI，他们正在降低推理成本，我们不知道具体怎么做，但可能是通过某种更高效的注意力处理方式。你认为在如何处理注意力方面，仍然有很多唾手可得的成果可以获取吗？所以，可能M3在这方面仍然非常有趣，部分原因是它的稀疏注意力潜力，部分原因是它虽然模型小，但效率非常高，对吧？你认为我们能走得更远吗？也许你们是如何发明M3的？我的架构？是智能体想出的主意，还是人类想出的主意？

<details>
<summary>Original English</summary>

**Speaker 12**: yeah, you think there's still a lot of low hanging fruits. so today, we saw OpenAI, they are already reducing inference cost, we don't know how as a phone, but like reducing that their inference bill by how they probably having some more efficient processing around attention. you think there's still still a lot of low hanging fruit that can be gotten in how we can process. and so so probably still still very interesting about M3 is how it is in particular, because of of sparse potential. and in part because of it's small one, but it's so very efficient, right? you think we can go even way further. maybe how did you guys invented M3? my architecture? was it an agent coming up with the idea? was it a humans still coming up with the idea to with it?

</details>

**Speaker 13**: 嗯，是的。所以我们确实认为在架构和推理优化方面还有很多工作可以做，以使模型更高效，特别是对于那些对任务非常敏感但又需要非常强大能力的任务。对于这类任务，我们确实希望模型高效。至于谁想出了稀疏注意力，实际上，是我们团队的一名实习生。嗯，一名实习生，嗯，这在很多实验室并不常见，嗯，因为我认为有些实验室的实习生没有接触数据或工作内容的权限。但是，是的，我们对任何愿意为我们的模型做出贡献的人持开放态度。所以这个架构实际上是由一名实习生设计的。

<details>
<summary>Original English</summary>

**Speaker 13**: well, yeah. so we do think there's still a lot of work that can get into your architecture and inference optimization so that the model can be more efficient, especially with there are task that are very task sensitive, but require very strong capability. and for that, those kind of task, we really want the model to be efficient uh and who came up with sparse actually, think an intern from our team word on that that yeah, an intern um that doesn't usually have in a lot of labs, um because i thinking some labs' interns don't have access to the data of the work stuff. but yeah, we are open to anyone who would like to contribute to our model. so the architecture was actually designed by an intern.

</details>

### MiniMax的组织与研究文化

**Speaker 12**: 这非常好，对实习生来说是个好消息。这也很好地引出了MiniMax是如何在内部运作的。我们在上台前讨论过，每个人都可以提出项目。请告诉我们一些你们是如何组织、如何进行研究的。

<details>
<summary>Original English</summary>

**Speaker 12**: it's very good still some work for instance here ah no good news, and that's also a good segway to also how MiniMax is working internally. so so we are discussing before coming on stage of saying, everyone can propose a projects. i think tell us a little bit about how you are organize how you do a research.

</details>

**Speaker 13**: 我认为这与在学校甚至早期的科技公司非常不同。嗯，我们确保的是我们有良好的基础和良好的基础设施，这样任何人都可以玩转模型，并思考他们可以如何改进模型。然后在模型发布后，他们可以自由地，对吧。然后，在人们使用模型之后，他们可以有自己的评估。

<details>
<summary>Original English</summary>

**Speaker 13**: i think that is very different from even in school or even in earlier tech companies pretty pretty different from that. um what we what we make sure is that we have good foundation and good um infrastructure so that anyone can play with a model and can think of what they can improve with the model. and then after model releases, and they they are free, right. they then after people with the model, they can think of their own evaluations.

</details>

<!-- chunk 9/54 -->

### 社区贡献与原生多模态训练

**Speaker 13**: 他们可以找到自己的弱点，并提出他们想要改进模型的地方。然后其他对此感兴趣的人，会提议加入项目，他们会工作几周甚至几个月。当他们完成时，最终成果会被整合到我们的模型中，就像我们说的，用于我们的最终训练，然后发布给用户。

<details>
<summary>Original English</summary>

**Speaker 13**: they can find their own weaknesses and propose the thing that they want to improve on the model. and then other people who are interested in that, you know, proposed to join the project, and they will work on for a couple of weeks or even a couple of months. and when they work out, the final thing is shipped to our model it it is, you know, we you said in our final training and is shipped out to the audience.

</details>

**Speaker 12**: 明白了。所以人们可以提前投入时间到项目上，你说的几个月可能真的是很深入的探索？是的，有可能。是的，我好了。

<details>
<summary>Original English</summary>

**Speaker 12**: just see. so can i people forward on time on project when you say couple of months can be like really deep exploration? yes, possible. yes, 我好了。

</details>

**Speaker 13**: 我想说，例如，架构方面可能需要更长时间的调查研究实验，甚至为树训练重新做评估。是的，所以可能需要更长的时间。

<details>
<summary>Original English</summary>

**Speaker 13**: i would say, for example, architecture might require longer time of investigation research experiments, even redoing the evaluations for tree training. yes, so it might require a onger ger time.

</details>

**Speaker 12**: 那么现在，是的，我知道你们也非常重视评估。我们可以谈谈这个。我想有一件事可能与此相关，那就是 M3 和团队拥有的这种独特能力，这种独特的模态。所以不仅仅是文本，这个模型还能理解图像和视频。据我了解，请更好地解释一下，当你发布模型时，在 Hugging Face 上，他说这个模型从第一步开始就是作为一个多模态模型训练的。不仅仅是像拼凑起来的。这是从头开始的，我想多了解一点，为什么你认为这很重要，以及为什么从第一步开始进行多模态模型训练，而不仅仅是事后训练。

<details>
<summary>Original English</summary>

**Speaker 12**: so now yeah, and i know you also very big gand evaluation agagree. we could talk about that. i think one thing probably related to that this unique speciability that m three and the team has this unique modality. so another just tex, but this similar can also understand image in video. and as i understand, please explain better when you read the model, l ard and hhigy face, he said the model was strain from the first step as a mini model. not just that a like uzo. and it's after softwi and you that is little bit more about that and why you think it's important and um and why starting from the first step on verty model training and not just training.

</details>

**Speaker 13**: 嗯，我们称之为原生多模态。这某种程度上是典型的模型实验室训练重要模型的方式。比如说，视觉理解能力是在文本预训练完成之后才加入的。他们添加适配器然后进行训练。但我们发现，这样做实际上会损害文本性能。而且视觉理解性能也不会很好地收敛，因为模型某种程度上会向文本理解收敛，这既不是最优的，也不具备很好的可扩展性。你想想看，我们想要扩展数据，对吧？嗯，而且，我们也可以从预训练中途开始训练这种能力，例如，继续预训练。但我们发现这会非常，你知道，对配方很敏感。嗯，不同的架构需要不同的配方。不同的数据混合、不同的学习率。很难控制，很难，你知道，扩展到更大的规模。你无法真正将你的实验结果和结论扩展到更大的模型。所以我们想，为什么不从一开始就训练，这是最自然的呢？我们知道很多实验室在这样做时会遇到问题。嗯，模型在训练几步之后就会崩溃，无论是文本还是视觉理解能力，但我们设法解决了这个问题。我们在 VIT 上做了很多工作，我们在实际训练的数据上也做了很多工作。嗯，例如，我们交错数据，我们称之为交错数据。嗯，它实际上是自然数据，但我们保留了图像和视频，而不是将它们屏蔽掉，并且我们对数据进行了非常好的清理和屏蔽，并且我们做了非常好的奖励建模，这样我们从第一步开始训练并扩展到更大规模。哦，是的，它不会崩溃。

<details>
<summary>Original English</summary>

**Speaker 13**: um so we call it native moortormoality. um and so it is somehow typical for model lapse to train the important model. let's say, vision understanding capabilities after the tex pretraining is done. um they put adaptters in the train that art. but we found out with that, that would actually harm the tex performance 好. and the vision vision understanding performance wouldn't converse that well, because the model is kind of convergers towards the model, the text understanding um and it's just not the most optimal and also not the most scalable. if you think about it, we want to scale the data right? 嗯, and also, we can also some webs um train this capability from half ways through the pretraining, for example, continued pretraining. but what we found that this would be very, you know, a recipe sensitive. 嗯, it is different for the recipe would be different for different architectures. different. you know, data makes tures different learning rates. it's hard to control hard to you know, scale to you. you can't really scale your experiment results and conclusions to a larger model. and so you know what we thought was, why not just training from the very first step that comes the most natural? we know that a lot of labs run into problems doing that. um the model would collapse after a couple of steps of training, you know, both text and vision understanding, but we managed to solve that problem. we did a lot of work on um VIT, and we did a lot of work on the data that we actually training. um for example, we do inter leave the data, what we call interleave the data. um it's actually natural data, but we keep the 嗯 images and video was in instead of masking it out, and we do some pretty good cleaning and masking on the data, and we do very good reward modeling so that we turn it from the first step and scales up. oh yeah, it does not collapse.

</details>

**Speaker 12**: 这真的很令人印象深刻。我们未来应该期待更大的模型吗？这个模型还相当小，对吧？它有一千二百八十亿参数，其中二百二十亿是激活的。嗯，你觉得你们会超过万亿参数吗？

<details>
<summary>Original English</summary>

**Speaker 12**: that's really impressive ve ve should we expect much larger model in the future. so this one is still fairly small, right? it's it's hundred twenty eight billion pameters twenty three reactive billion. um well, you think you will go past the trillion 拜拜。

</details>

**Speaker 13**: 当然，是的，未来肯定会。有很多任务，模型用较少的参数是无法执行或做好的。我们肯定会比这更有雄心。

<details>
<summary>Original English</summary>

**Speaker 13**: definitely yeah, definitely in the future. there are many tasks that wouldn't be able to the model wouldn't be able to perform or good good at with smaller proeters. we are definitely going more ambitious than this.

</details>

**Speaker 12**: 太好了，很期待。关于 MiniMax，另一个我一直觉得非常迷人的事情是，你们如何拥有这整个系列的应用和产品，对吧？我记得你们已经开源了很多东西。还有去年一月的 Hugging Face 平台。那是八个月前的事了，我们聊了一点关于团队，了解你们在做什么。我记得你，你们的这些应用已经有了巨大的使用量。你能讲讲用户的情况吗？所以基本上是，你们有很多应用。然后你们有了所有这些数据，为什么不训练一个模型呢？然后他们建立了研究团队，嗯，故事是怎样的？

<details>
<summary>Original English</summary>

**Speaker 12**: it's great looking forward. it's another fasintesting ating thing always by fine fascinating about minimaxes, how how you also have this whole range of appapps and product right? are remember already how so many study to open source things. and the haking face platform in january last year. so that eighty months ago, and we are chatting a little bit about the team to understand what you were doing. and i remember you, so you were already having a huge usage and some of this some some this apps. and can you tell a little bit how stustusaright so was it basically, you had a lot of apps. and then we have all these data, why not traying a model? and then they build research team m, how is the story there?

</details>

**Speaker 13**: 嗯，我们的故事是从第一天起就做模型。所以，嗯，我相信多模态模型，一个能理解所有模态并输出的模型，是我们 CEO 从第一天起就计划的事情，甚至在公司成立之前。所以那是 AGI 的梦想。我认为那非常非常早，甚至在 ChatGPT 出现之前。是的，然后应用是随之而来的东西，因为你有这么多能力，你希望人们去体验它。嗯，不是很多人能使用 API，对吧？我们不能期望每个人都通过 API 来体验。所以我们需要好的用户界面，好的应用，好的场景，让人们可以，你知道，体验模型。我认为实际上这些应用覆盖了全球约两百个国家的超过三亿人。我认为还有超过百万的企业。

<details>
<summary>Original English</summary>

**Speaker 13**: um our our story is model from the first day. so um i believe that multimodelity model a model i can understand ds obvions and outpust. all modalities was the first thing that our um CEO planned on the first day, even before the company even started. so that was the dream of AGII. think that was very, very early, even before tragic t came out. yeah, and then appps for something that comes along because you have some much of capabties. you want people to experience it. well, not many people can use it with api, right? we can't expect everyone's experience with api. so we need good uuser introduction. you know, interfaces, good ups, good scenario that people can can. you know experience ence model with. i think actually those apps covered more than three hundred million people around two hundred countries globbally. i think over over milmillion companies as well.

</details>

**Speaker 12**: 啊，当我听到这个规模时，这真是令人大开眼界，我们通常没有意识到这种用户群的规模。这让我想到了关于开源商业模式的问题，这是一个一直存在的问题。现在业界对此很关注。你们开源模型很好，但你们也需要有收入来源，对吧？所以我想，你们决定让一些东西免费，这对世界很好。你们怎么看这个？你们也有一些用于应用的特定模型。你们考虑过未来吗？你们会保持开源模型吗？可能很难说死，但我觉得你们会保持开源。你们内部的文化是怎样的？现在个人感觉如何？

<details>
<summary>Original English</summary>

**Speaker 12**: ah this was was mindgrowing when i heard about the size, and we don't often realize the size of of this type of fusige already. and i kind of bring me to the question around um 是的, open source business model and all of that, which is always existing question. andergy is right now. it's nice to open so ls model, but you, you also need to have some revenue stream right? and so i guess, and stsomething something you, you decided things to be for free and and think think it's it's great for the world. and how do you see this? you also have some specific models you use for the app. you think about you thinking the future. you'll keep. it's probably hard to say for sure. but i think you will keep open. so sing models, how is the culture around up? it's a sing right now personally.

</details>

**Speaker 13**: 对于我和模型研究团队来说，我们一直希望开源模型。那是我们的计划，因为我们看到开源社区如何共同帮助把模型做得更好。例如，我们从伟大的社区收到了很多关于模型性能的反馈。所以每当我们开源，那些非常有价值的意见会反馈到我们后来的版本中。所以真正地开源是很棒的。

<details>
<summary>Original English</summary>

**Speaker 13**: and also for the model research team. we always hope to open source to models. that is our plan because we we see how the open source community together can es to model l build better. for example, we receive a lot of feedbacks on the model performance from the great community from the great community. so whatever we open source, and those are very value able come comes to our later versision. so for reely open ansforcing is great.

</details>

**Speaker 12**: 太好了。实际上，替观众问一下，那些正在使用 MiniMax 或 MiniMax 模型的人，有没有什么是你们希望他们反馈给你们的？例如，当人们尝试修改模型或进行实验时，你知道，调整参数，你认为从社区获得的对未来模型最有价值的东西是什么？

<details>
<summary>Original English</summary>

**Speaker 12**: it's great. and actually GF some ask for the audience people who are using an ammstry or minimax. is there something you would love them to send back to you as feedback do you, for instance, you read when people try to modify models or play around, you know, tweeks, what is the best thing you think you can take from the community for the future models for intweh 呀？

</details>

**Speaker 13**: 我想说，无论人们遇到什么问题，特别是对于多模态模型，对吧？这是我们第一次将它们结合在一起。我们未来肯定会做得更多。现在它可能有一些缺陷，但我们正在改进。所以无论什么反馈，说模型在某个方面做得不够好，我们肯定会在未来版本中改进。还有，无论人们想要什么功能，比如说，思考能力，对吧，人们要求这个，嗯，就像每个人都可以要求，我们会尝试在未来的模型中理解并加入。

<details>
<summary>Original English</summary>

**Speaker 13**: i would say whatever um issues that people are running into, especially with more time modelright, right? this is first time that we're conconining it together. we are definitely going more. and this is on that in the future. it might have some flah right now, but we are improving on that. so whatever that uh feeback that model is not good doing that great. we will definitely improve that in future versions and also whatever features that um people want, say, you know, for example, thinking effort, right, people ask for that um like everyone can ask, and we will try to conunderstand the future models.

</details>

**Speaker 12**: 是的，你现在已经在多模态中看到了很多这样的用例。在编码代理方面，我觉得它还有点未被充分探索。

<details>
<summary>Original English</summary>

**Speaker 12**: yeah, you see a lot of use that right now already in multimodity. in terms of coding agents, i feel like it's it's a little bit. and er expllored 来家 it is it is,

</details>

**Speaker 13**: 是的，但它实际上可以解锁很多能力。以及很多代理应用场景。例如，你想要模型读取 PPT 幻灯片。然后总结一份结构不太清晰的报告，或者你想理解一个很长的视频，比如一个长视频，然后你希望模型在理解之后使用一些工具来行动。这解锁了各种各样的代理用例。

<details>
<summary>Original English</summary>

**Speaker 13**: but um it can actually unloks a lot of capable. and and a lot of uh agent applications says, for exexple. you want, want the model to read the PPT powerpoint. so and to resome some report that is not very structured or you wanted to understand a very long video say that you don't in a long playing video, and then you want some model to act. uh using some tools uh after understanding it and allocks a wide variety of um agent use cases.

</details>

**Speaker 12**: 所以就像代理最终可以观看我的 YouTube 教程，并理解如何使用我的编码工具，我描述的方式大概就是这样。呃，代理最终可以观看 YouTube 教程并从中理解东西。

<details>
<summary>Original English</summary>

**Speaker 12**: so like the agent could finally watch my youtube tutorial and understand how to use my coding tools, how i describe it is something like that. uh could agent finally watch ed, youtube totoals and understand things from them.

</details>

**Speaker 13**: 是的，是的。

<details>
<summary>Original English</summary>

**Speaker 13**: yeah yeah,

</details>

**Speaker 12**: 我想。那么，你们内部大量使用代理编码工具吗？比如在编码方面肯定用。

<details>
<summary>Original English</summary>

**Speaker 12**: i think. so. do you use a lot of agent coding tools internenis it like i'm in coding for sure.

</details>

**Speaker 13**: 但是在研究方面呢，嗯，我们做我们自己的研究，嗯，我们建立了我们自己的研究流程自动化，对吧？

<details>
<summary>Original English</summary>

**Speaker 13**: but like is it also already in terms of research, is it um we d our own research, harneses ses, we built our research ch kssses automizzation, right?

</details>

<!-- chunk 10/54 -->

### 模型能力与多智能体前景

**Speaker 13**: 比如让模型去发布其他模型，让模型自动构建数据之类的。你可以看到越来越多的模型能够做到这些，包括……实际上，我们在长程任务和跨组织协作方面表现非常出色。所以我们可以利用这种模型能力，将其整合起来，利用这些生成结果更快地构建迭代版本。我们已经在构建第三版和第四版了。

<details>
<summary>Original English</summary>

**Speaker 13**: like the model posting other models, let the model build data auto data stuff like that. You can see how more and more models are capable of doing those, including, and three, actually, we were very good at those cases, long horizon and cross-organizational. And so we can use that model capability harness it together and help use that generations and build our iterations even faster. We're building three and four already.

</details>

**Speaker 12**: 第三点一版甚至更快。Tokay 说 JMP 已经……我很想听听你对未来几个月有什么兴奋的期待。你觉得在 AI 或更广泛的领域，有什么你希望看到发生的特性或事情吗？现在脑子里想到什么都可以说。

<details>
<summary>Original English</summary>

**Speaker 12**: And three point one even faster. Tokay said the JMP already. I would love to finish on what you find exciting in the coming months. You think it can be a feature or things you want to see happening in the AI or broader space in terms of whatever really top of your mind now. It's going, it's going to happen.

</details>

**Speaker 13**: 有很多事情都令人兴奋。但我最近觉得最兴奋的是多智能体。我认为很多 AI 应用都在使用与多智能体相关的模型。这让我们能够处理更复杂、更具挑战性的任务。同时，它也告诉我们模型能做什么、不能做什么。你可以做很多非常令人兴奋的事情。

<details>
<summary>Original English</summary>

**Speaker 13**: A lot of things are very exciting. But what I recently find the most exciting would be multi-agents. I think a lot of AI applications are using model relating multi-agents. That allows even more capable, even more complex tasks. And also, it tells us what the models are capable and not capable of. And you can do a lot of things that are pretty exciting.

</details>

**Speaker 12**: 谢谢。很高兴你能来。

<details>
<summary>Original English</summary>

**Speaker 12**: Thanks. Great to have you.

</details>

**Speaker 13**: 谢谢邀请。

<details>
<summary>Original English</summary>

**Speaker 13**: Thanks for having me.

</details>

### 欢迎回归与安全专场介绍

**Speaker 3**: 女士们先生们，请鼓掌欢迎我们的下一位演讲者。他是来自 Keycard Ally 的技术人员。

<details>
<summary>Original English</summary>

**Speaker 3**: Ladies and gentlemen, please put your hands together, and welcome back. R&D member of technical staff at Keycard Ally.

</details>

**Speaker 14**: 哇，刚才的内容太棒了。我非常兴奋地向大家介绍我们的下一位演讲者，他将为我们开启安全专场。软件工厂只有在安全融入其中的前提下才能实现。如今，工程师们必须应对不断演变的智能体供应链，技能和软件包似乎每天都在被攻破。组织必须管理身份信任，因为智能体越来越多地代表用户和其他智能体执行任务。安全团队必须找到方法来治理智能体，并确保它们的访问权限仅限于当前任务所必需的范围。如今，整个行业正在发生巨大的转变，从传统的应用安全转向智能体安全。Rental Deaggs，Sick 公司的营销、工程和 AI 编排副总裁，正在帮助大型企业客户应对这一转变。他将为我们介绍更多关于 AI 工程师安全专场的信息，该专场由 Sneak 赞助。让我们欢迎 Rental Deaggs 上台。

<details>
<summary>Original English</summary>

**Speaker 14**: Wow, what amazing content so far. Super excited to tell you more about our next speaker who's introducing the security track. Software factories are only made possible if security is in the loop. Today, engineers have to navigate an ever-evolving agent supply chain between skills and software packages that seem to be compromised almost daily. Organizations have to manage identity trust as agents increasingly do work on behalf of users and other agents. Security teams have to find ways to govern agents and make sure their access is scoped to only what's necessary for the task at hand. Today, there's an enormous shift that's happening across the industry from traditional application security to agentic security. Rental Deaggs, VP of Marketing, Engineering and AI Orchestration at Sick, is helping large enterprise customers navigate that shift. He's here to tell us more about the AI Engineer Security Track, which was made possible by Sneak. Please welcome to the stage, Rental Deaggs.

</details>

### AI 安全的现状与挑战

**Speaker 15**: 大家好，你们好吗？我是 Rental Deaggs，感谢 Ali 的介绍。我只上来讲几分钟，所以会很简短。我想利用这段时间谈谈 AI 安全的现状，以及我最近一直在思考的一些问题，可能也是你们都在思考的问题。我几乎整个职业生涯都是开发者和安全专业人士。尽管我身处安全领域，但近年来随着生成式 AI 的兴起，最让我兴奋的是能够更快地构建出更高质量的软件。没有什么比把你正在开发的东西交付给真正的用户，并激发他们的喜悦感更棒的了，对吧？这感觉就像开了外挂一样。我认为，在当今世界，要让在座的各位能够大规模地做到这些，确实存在几个障碍。第一件事，可能我们所有人几年前都深有体会，那就是当你使用 AI 构建软件时，AI 生成的代码总是存在安全风险。每个人都知道这一点，这并不新鲜，对吧？我认为这之所以不是什么大问题，是因为首先，大家直觉上都明白，人类写代码时会引入安全问题，而 AI 模型写代码时，事实证明它们也会引入安全问题。因此，将安全作为开发生命周期的一部分，是现代工程工作的核心组成部分，这毫无疑问。不过，我认为第二点更有趣。那就是当你试图将真正的自主智能体部署到生产环境中时。你如何才能做到高枕无忧，不用担心部署的智能体会失控，做出它们不该做的事，从而损害你的业务、用户或其他方面，对吧？这是一个更难解决的问题。最后，我认为阻碍我们真正创新和快速前进的，在这一点上几乎是地缘政治问题了。我不知道你们怎么想，但有多少人因为无法访问某个模型而感到恼火？请举手。是的，很多人。有多少人因为现在无法使用全新的 OpenAI GPT-5.6 模型而感到有点烦恼？是的，很多人。我认为这很有趣，因为这一切都与安全相关，对吧？从根本上说，我觉得我们在这个领域仍需解决的最大问题是，能够默认使用 AI，并且默认是安全的。因此，我非常兴奋地宣布，就在这场演讲之后，楼下二楼 2005 号房间，我将全天主持世界博览会上的首个安全专场，届时会有一些世界上最好的公司和演讲者，共同探讨所有这些难题以及我们未来如何解决它们。所以，如果安全对你来说像我一样重要，请到楼下来加入我们，二楼 2005 号房间。我们有来自 Anvideo、Thropic、Keycard、Alyworks 和 Sneak 的演讲者。当然，我们还有大量精彩的内容，希望能帮助你们提升正在构建的东西的水平，并且毫无顾虑地去做。那么，我就讲到这里。非常感谢大家的时间。希望能在楼下见到你们。我是 Randal，我会全天主持这个活动。谢谢大家。

<details>
<summary>Original English</summary>

**Speaker 15**: Hello, how's it going everyone? I'm Rental Deaggs with a nice intro Ali, and I'm only up here for a couple minutes. This can be very brief, but what I wanted to talk about in the time that I have is kind of the state of AI security and the things that I've been thinking about quite a lot lately, and maybe things that you've all been thinking about too. So I've been a developer and security professional pretty much my entire life. And even though I've been in the security space, the thing that makes me excited in these recent years, with the rise of generative AI, is being able to build better quality software more quickly. There's nothing more fun than shipping the things you're working on to actual users and sparking a sense of joy, right? It almost feels like a cheat code. And I think that there's really a few obstacles to allowing all of us in the room today to do these things at scale in today's world. So the first thing is something that all of us probably learned the hard way a few years ago, which is when you're building software using AI, there's always the risk that the code AI generates might have a security issue. Everybody knows that, it's nothing new, right? And I think the reason that that's not a big deal is because first of all, everyone kind of intuitively knows that when humans write code, we generate security issues. When AI models write code, turns out they also generate security issues. And so having security as part of your development life cycle is just like a core part of modern engineering work, no questions at all. I think the second thing though, is a little more interesting. It's when you're trying to deploy actual autonomous agents into production. How do you do that in a way that allows you to go to sleep easily and not worry that the agents you deployed are going to go off the rails and do something they're not supposed to do, harm your business or your users or something else, right? And that's a much more difficult problem to solve. And then the final thing that I think is a barrier to us really innovating and moving quickly is almost geopolitics at this point. Like I don't know about all of you, but how many people were kind of annoyed when access to a model got pulled? Show hands. Yeah, a whole lot of you, alright. How many people are a little annoyed they can't use the brand new OpenAI GPT-5.6 model right now? Yes, a lot of people. And I think it's interesting because this is all related to security, right? Like fundamentally, the biggest problem that I feel we have to still solve in our space is being able to use AI by default and have it be secure by default. And so that's why I'm really excited to announce that right after this, downstairs on the second floor in room 2005, I'll be running the first security track at the World's Fair for the entire day, with some of the best companies and presenters in the world, talking all about these problems and how we can fix them going forward. So if security is a concern to you like it is to me, please come downstairs, join us again, room 2005, second floor. We have presenters from Anvideo, Thropic, Keycard, Alyworks, and Sneak. Of course, we have a ton of amazing content, and it's hopefully to allow you to level up the stuff you're building and do it without any worry at all. So that's where I'm going to go. So without further ado, thank you so much for the time. And hopefully, I'll see you down there. I'm Randal, and I'll be hosting the event all day, right? Take care everyone.

</details>

### 智能体故障的复现与调试难题

**Speaker 16**: 我得告诉你，你从遥测日志里拉出那次运行记录，把它传给同一个模型，用同样的提示词，在本地运行来隔离那个 bug——我们都会这么做。令人惊讶的是，它居然能正常工作。再跑一次，它又能运行。你跑十次，每次结果都完美无缺。但现在，我们来谈谈那一次出问题的运行，它消失了，你无法复现它。如果你无法复现它，你就无法调试它。但如果你无法调试它，你就无法保证它不会发生在你的下一个客户或用户身上。我是 Fisher，Ashimev 是我的联合主持人。我们不会让智能体在真实的生产环境中运行，你知道，那种地方，事后补救是不够的。那是你正在和客户通电话，解释为什么数据实际上出错了。这场演讲就是要讲这个。当智能体在生产中失控时，最可怕的事情之一就是无法复现它。在接下来的十分钟里，我们将看看这实际上是如何爆发的。你让智能体连接到一个有问题的 API，用户说“帮我买一千美元的股票”。现在有趣的部分来了。智能体没有做数学计算，而是把数字“1000”直接塞进了数量字段。是的，它本来要卖 190 股，结果变成了 190 美元一股，一千美元能买多少？变成了 1000 股，190 美元一股，那就是 19 万美元的灾难，对吧？更糟糕的是，我的保险 API 返回了一个干净的 200。好的，在 3000 万次运行中，我们得到了零异常，零警报。如果你看仪表盘，它完全是绿色的，就像你的仪表盘一样，你觉得它完美无缺，一切正常。然后，就像我们上次讨论的那样，问题出现了。你做的第一件事是什么来尝试修复它？本能的反应是，把模型的温度调到绝对零度，因为贪婪解码会让一切变得确定，对吧？但这完全是个误解。把温度设为零并不能修复有缺陷的推理路径。它只是意味着模型会以完全相同的方式、在完全相同的时间犯完全相同的逻辑错误。老实说，比这更糟的是，回到我们刚才讨论的场景。看看 Jeeeling 在 Ready 和 Hecnews 上的测试结果。硬数据显示，温度为零在硬件层面甚至都不是真正的确定性。运行同一个提示词一千次，仍然可能因为底层的 GPU 非确定性和 CUDA 架构而产生几十个完全不同的响应。要理解为什么会发生这种情况，我们需要从基本原理来看，归结起来就是四个简单的事情。

<details>
<summary>Original English</summary>

**Speaker 16**: I've got to tell you, you pull the run from the telemetry logs, pass it to the same model using the same prompt, and run it locally to isolate the bug, which we all do. And surprisingly, it will work as well. Run it again, it will run again. You run it ten more times, it will be just perfect every time. But now let's talk about that one run which caused the issue, and that will be gone, you can't reproduce it. And if you can't reproduce it, you can't debug it. But if you can't debug it, you can't promise it might not happen to your next customer or user. Right now I am Fisher. I have Ashimev as my co-host. We won't run agents against real production scenarios. You know, the kind of place where better back-right isn't over vanity. It's you on a call with a customer explaining why the data actually worked. This whole talk is going to be about that. One thing to lose the second an agent goes haywire in production is being able to reproduce it. That will be our focus for the next ten minutes. Look at how this actually blows up. You've got the agent hooked to a broken API, which is this, and how you are taking the user, says him, send a thousand dollars of stock. Now comes the interesting part. Instead of doing the math, the agent stays the wrong number one thousand and dumps it straight into the quantity field. Yes, it sells one hundred and ninety shares instead, now at one hundred and ninety dollars a share, a thousand dollars in total will become how much? A thousand and ninety thousand dollars disaster, right? Under terrible parties that the PI on my insert returned a clean two hundred. Okay, in thirty million runs, we got zero exceptions, zero alerts. If you see the dashboard, it's completely green, like your dashboard, just you think it's perfectly green, perfectly flawless. Then such as NIU as we last discussed comes up. What's the first thing you will do to try and fix this? The reflex here is to, you know, just turn the model temperature down to absolute zero, as greedy decoding will make everything deterministic, right? But that's a complete misconception. Setting the temperature to zero doesn't fix a broken reasoning path. It just means the model is going to make the exact same logic error at the exact same time. And honestly, even worse than that, go back to the scenario we just discussed. Look at the Jeeeling creates on Ready and Hecnews. The hard data shows that temperature zero isn't even truly deterministic on a hardware level. Running the same prompt a thousand times can still return dozens of completely different responses just due to the underlying GPU non-determinism and the CUDA architectures. To understand why this actually happens, we need to look at it from first principles. It comes down to four simple things.

</details>

<!-- chunk 11/54 -->

### 采样确定性与系统确定性

**Speaker 16**: 采样确定性属于系统确定性。温度设为0意味着总是取argmax，但这并不能保证底层运算在数值上是确定性的——浮点运算不满足结合律。你添加不同的模型，对吧？但时序偏移会改变矩阵运算中的最终逻辑，进而改变胜出的token。这不是一个一致性问题：在同一个推理加速器上运行同一个应用程序一千次，我保证它会输出完全相同的文本。所以真正的挑战在于批处理，因为请求会以不同的方式组合在一起。第二，我想谈谈混合专家模型。路由机制也存在完全相同的问题。每个专家都有严格的容量限制。如果一个批次溢出某个特定网络，部分token就会被丢弃。每当token被丢弃时，丢弃哪个token完全取决于计算图——你如何组织批处理。所以这里的要点是：追求文本输出的确定性是一条完全失败的道路。我们不需要模型每次都返回完全相同的token，我们只需要系统执行完全相同的状态转换。这意味着我们一直以来都问错了问题。错误的问题是：我如何让模型变得确定性？我看到有团队在这上面耗费数周，最后放弃，认定系统不可靠。正确的问题是：我如何调试和复现一次运行？你无法做到，因为确定性从来就不是目标。调试才是目标。我们把这两件事搞混了。现在我想谈谈确定性与可靠性之间的区别。确定性是相同的输入产生相同的输出——这是可控性。你无法从一个托管API获得这个，而且你实际上也不想要它，因为让模型变好的因素——当模型产生更多创造性变体时，它表现更好——与可靠性是相反的。可靠性是指一次已经发生过的运行，其细节足够完整以便调试。这是可观测性。你不需要模型是确定性的。你需要记录它。你不需要冻结模型。你捕获它做了什么。

<details>
<summary>Original English</summary>

**Speaker 16**: one sampling determinism is in system determinism. Temperature zero means always take the argmax, but it doesn't guarantee that the underlying operations are numerically deterministic — floating point math isn't associative. You add different models, right? But timing shifts in matrix operations alter the final logic, which in turn will shift the winning token. That's not a consistency issue: run the same inference application alone on an accelerator a thousand times, I guarantee you'll get the exact same text. So the real challenge is batch variance here, because the requests get grouped together in whatever way hits the service. Second, I want to talk about mixture of experts. Routing has the exact same problem. Each expert has strict capacity limits. If a batch overflows a specific network, some tokens get dropped. Whenever a token gets dropped, which token gets dropped depends entirely on the compute graph — how you organize the batch. So the takeaway here is that chasing deterministic text outputs is a losing path completely. We don't need the model to return the exact same token back every time; we just need our system to execute the exact same state transition, which means we've been asking the wrong question all along. The wrong question is: how do I make the model deterministic? And I've seen teams burning weeks on that and walk away deciding the system is unreliable. The right question is: how do I debug and reproduce a run? You can't, because determinism was never the goal. Debugging was the goal. We keep mixing up determinism and reliability. Determinism is same input, same output — that's controllability. You're not getting that from a hosted API, and you don't actually want it because what makes the model good — the model performs better when it produces more creative variants — is the opposite of reliability. Reliability is a run that already happened, recorded well enough to debug. That's observability. You don't need the model to be deterministic. You need to record it. You don't freeze the model. You capture what it did.

</details>

**Speaker 0**: 另一个问题，我们都在思考这个问题：你记录吗？当然记录，但不是在网络层面，因为你一半的调用甚至不会触及网络。本地的检索增强生成工具、内存以及那些不涉及流式传输的部分——在边界处记录。因为你需要捕获进入每个节点和离开每个节点的内容。想象一下，你的智能体产生了错误的输出——调用了错误的工具，写错了东西。现在突然之间，你的团队需要紧急开会来弄清楚到底发生了什么。实际上这种情况现在也很常见。标准的生成式响应——你的直觉会告诉你从遥测日志中提取那个提示词，用相同的模型和相同的提示词在本地运行它来隔离错误。我们都会这么做。令人惊讶的是，它通常会成功。再运行一次，它又会成功。你再运行十次，每次都会完美运行。但让我们谈谈那一次失败的运行——它消失了，你无法复现它。如果你无法复现它，你就无法调试它。如果你无法调试它，你就无法修复它。它可能发生在你的下一个客户或用户身上。我是Disha。我邀请了我的联合创始人，我们将讨论智能体在生产环境中的真实问题。你知道，那种让每个人都感到沮丧的问题。

<details>
<summary>Original English</summary>

**Speaker 0**: Another question, which we are all thinking about: do you record? Sure, but not at the network layer, because half your calls never touch the network. The local retrieval, the in-process tools, the memory, and the parts that do not involve streaming — record at the boundary instead. Because you need to capture what enters each node and what leaves it. Imagine your agent produced a wrong output — called the wrong tool, wrote the wrong thing. And now suddenly your team is on a conference call to figure out what actually happened. That's pretty common right now as well. Standard generative response — your gut will tell you to pull the prompt from the telemetry logs, pass it to the same model using the same prompt, and run it locally to isolate the bug. Which we all do. And surprisingly, it will work. Run it again, it will work again. You run it ten more times, it will be just perfect every time. But now let's talk about that one run which caused the issue and that will be gone — you can't reproduce it. And if you can't reproduce it, you can't debug it. And if you can't debug it, you can't fix it. It might happen to your next customer or user right now. I am Disha. I have with me my co-founder, and we will talk about agents against real production problems. You know, the kind of problems that bother everyone.

</details>

### 浏览器智能体的挑战与改进

**Speaker 2**: 我是Pushon II，一名基础工程研究员，这就是我现在正在做的事情。我认为智能体应该去中心化，所以我一直在探索这个领域。我理解为什么它现在这么热门。我们面临浏览器挑战。这是一个对浏览器智能体非常有影响力的基准测试，因为你必须完成长序列的任务。这实际上揭示了为什么浏览器智能体一开始表现不佳。浏览器智能体花了大约十秒钟才点击了开始按钮。现在我们才在第一步，总共有三十步，而它仅仅点击一个按钮就花了这么长时间。好了，不说这个了，我想展示我正在构建的东西。我想让你感受到看到正在发生什么的感觉。你可以看到智能体在想什么，而且它快得多、聪明得多，而我使用的是更便宜的模型，对吧？我在这里展示了这一点。这些模型相当聪明，但问题在于它们周围的基础设施。如果你注意之前的视频，智能体在截屏时并不理解正在发生什么。它点击某个东西，却不明白发生了什么。所以我的方法是给智能体提供一个良好的环境，对吧？这样它就可以规划长序列，可以找出失败的地方以及发生了什么。

<details>
<summary>Original English</summary>

**Speaker 2**: I'm Pushon II, I'm a founding engineer for this, that's what I'm presenting right now. I think agents should be decentralized, so I've been exploring that for some time. I understand why it's so hot right now. We have the browser challenge. This is a very impactful benchmark for browser agents because there are things you have to do in long-running sequences of tasks. And this actually reveals why browser agents suck at the beginning of the video. The browser agent took like ten seconds to click the start button. And now we're on step one, there are thirty steps, and it has taken so long just to click one button. So enough of this, I want to show you what I am building. I'd like to give you the feeling of seeing what's happening. You can see what the agent is thinking, and it is so much faster and so much quicker, and I'm using a much cheaper model, right? I showed this here. These models are pretty smart, but it's the infrastructure around them that sucks. If you noticed in the video earlier, the agent didn't understand what was going on. It clicked something, it didn't understand what was going on. So my approach has been to give a nice environment for the agent, right? So it can plan long sequences, it can figure out where it failed, what is going on.

</details>

### 知识工作的新范式

**Speaker 3**: 我发现进度分散在整个代码库或单个仓库中，还分散在Slack、邮件、会议、文档以及其他各种东西里，对吧？而且其中一半实际上只存在于别人的脑子里。所以我必须让我的AI主动联系他们，让他们回答问题，然后继续推进。当我还是个人贡献者时，这很容易，只需要写代码。但随着你规模的扩大，你会发现今天很多知识工作只是弄清楚发生了什么、谁在等什么、哪些未完成的事情需要关注。所以如果你想从这次演讲中带走什么，你可以听完这个就离开。你需要的是这六件事：第一，长上下文真的有效。现在你可以放心地固定一个非常长的线程，知道它基本上会记住你告诉它的内容。第二，你应该开始习惯和你的电脑说话。语音真的很好用。语音会越来越好，你将能够通过语音完成比键盘更多的事情。第三，计算机使用截图——非常非常好。这是引入上下文的好方法，我稍后会详细说明。最重要的是，真正开始投资于你的个人记忆是什么样的，对吧？你想使用哪些技能？你想自动化哪些技能？还有，你想与团队其他成员分享哪些插件？一旦你设置好了，你就可以开始把这些固定线程和自动化当作队友一样看待。更有趣的是，我不知道有多少人知道这一点，但每个线程和上下文可以相互通信。所以也许今天你可以让一个固定线程感觉像一个队友，但很快，你可能会让作为自动化的线程与其他线程通信。你可以拥有一个管理者的概念。这些是我今天想带给你们的一些非常重要的概念。如果你过去使用过ChatGPT之类的工具，你可能习惯了必须使用非常短的线程，它们只是偶尔发生，几条消息之后上下文就会耗尽，你需要创建一个新线程来捕获上下文。现在，我所有的工作都发生在一个固定线程中——你固定它，给它一个名字，它会持续运行。通过自动化和触发器，你可以开始唤醒这些东西。所以工作流程实际上分为三个步骤，对吧？你把上下文带入系统，在这个固定线程上工作，然后你弄清楚计算机如何行动并回馈给外部世界。我们可以很快地讨论这些。对，这里有多少人实际使用语音输入？请举手。是的，大概百分之三十到四十。我几乎可以保证，到今年年底，会有越来越多的人这样做。托尼·斯塔克不是用键盘打字，而是和贾维斯说话。我真的希望你能认识到，到今年年底，你会感觉自己像托尼·斯塔克，你会通过语音自动化你生活中的大部分事情。语音比大多数人打字快三倍。我得了关节炎，我甚至不能再打字了。我只用脚踏板来控制语音输入，这太棒了，而且我也很懒。所以我如果要打字，我只会发一条消息说“修复这个”，然后希望AI能弄清楚发生了什么。

<details>
<summary>Original English</summary>

**Speaker 3**: I find that progress is scattered across not just a code base or a single repo, but across things like Slack and email meetings and documents and a bunch of other stuff, right? And half of it is actually just stuck in someone else's head. And so I have to have my AI reach out, have them answer questions and move forward. When I was an individual contributor, it was very easy, just write code. But as you sort of scale yourself, you find that a lot of the knowledge work happening today is just figuring out like what has happened, who is waiting on what, and which loose threads need attention. And so if you want to take anything away from this talk, you can just leave right after this. You want these six things: one, long context works. Now you can really feel comfortable pinning a very long thread and knowing that it's generally going to remember what you've told it. You should also start getting really comfortable with talking to your computer. Voice is really good. Voice is going to get better through time, and you're going to be able to do even more with dictation rather than a keyboard. Computer use with screenshots — very, very great. It's a great way of bringing in context, I'll talk more about what that looks like. And most importantly, really start investing in what your personal memory looks like, right? What are the skills that you want to use? And what are the skills you want to automate? But also, what are the plugins you want to share with the rest of the team? And once you have that set up, you can start thinking about these pinned threads and automations like teammates. And more interestingly, I don't know how many people will know this, but every thread and context can talk to each other. So maybe today you can work on having a pinned thread feel like a teammate, but very quickly you might have threads that are automations that communicate to other threads. And you could have this idea of a manager. And these are some of the really big concepts I want to bring to you today. And so if you used something like ChatGPT in the past, maybe you were used to having very short threads, they only happen every once in a while, after a couple messages the context is going to run out, and you really need to create a new thread to capture context. Now all of my work happens in a pinned thread — you pin it, you give it a name, it runs over time, and with automations and triggers, you can start waking these things up. And so work really happens in three acts, right? You bring the context into the system, you do work on this pinned thread, and then you figure out how the computer can then act and write back to the rest of the world. And we can talk about these things pretty quickly. Right, how many people here actually use dictation? Show of hands? Yes, maybe like thirty percent, forty percent. I can almost ensure you that by the end of the year, more and more people will do so. Tony Stark is not typing into a keyboard, he's talking to Jarvis. And I really want you to recognize that by the end of the year you're going to feel like Tony Stark, you're going to automate most of your life through voice. Voice is like three times faster than most people type. And I have arthritis, I can't even type anymore. I just use a foot pedal to control dictation, and it's pretty awesome, and I'm also really lazy. So if I had to type, I would just send a message like "fix this" and hope that the AI can figure out what's going on.

</details>

<!-- chunk 12/54 -->

### 语音指令与自动化工作流

**Speaker 3**: 然后当它搞砸的时候，我会在推特上抱怨说，你知道，这AI袜子真不行，但实际上，当我用语音输入时，我自己也只是个胡言乱语的家伙。呃，我举个例子，比如这个问题，检查一下浏览器。呃，这个空白区域我不太满意，可能是网站上的截图，也可能是在Figma上，然后我就提一个低质量的请求，去改CSS。然后，当你发完消息，在Slack上通知对方，等待预览的延迟，再把预览链接也发过去。我绝不会手动打这些字，但说“空格键”就简单多了，模型也能搞清楚如何实际执行这些操作。一旦你把这些重要的地方都设置好，你只需要把它们和外界连接起来。这就是你想要安装插件的地方，对吧？我的大部分工作就是Slack、Gmail、Notion、Linear、Obsidian这些。但有了这些插件，你就能真正让你的AI有能力延伸到外部世界，读取更多信息。

<details>
<summary>Original English</summary>

**Speaker 3**: and then when it dozen i complained on twitter that you know the ai socks, but in reality, when i use dictation, i you'll just a blaber. er i take look like this issue, check the browser. er this whwhite space. i'm not happy with maybe it's a screen shop on the website. maybe it's on figma, then like make a poor quequest d, it the the css. and then also like when you're done message, ges, the guy on slack and then wait for the preview lag and then sand on the preview laink too. i would never type this, but the space elve is very easier to say, and the the model can figure out how to actually take these actions. once you have all this important place, you just have the connected with the rest of the world. and this is where you want to install plugins, right? most of my work is just slack gmail, counter notion llinear opsidian. but having these plugins, you can really just give your AI the ability or reach out into the world and read more information.

</details>

**Speaker 5**: 没有没有。

<details>
<summary>Original English</summary>

**Speaker 5**: 没有没有。

</details>

**Speaker 3**: 一旦你做到这一步，我就想尝试一个非常简单的提示，对吧？试试看“我的项目有什么变化，把重要的事情告诉我”。你真的会惊讶于这些新模型能多么轻松地搞清楚你的工作内容，以及如何让你变得更高效。什么才是重要的？

<details>
<summary>Original English</summary>

**Speaker 3**: once you do this, i just wanted to try out a very simple prop, right? trioswhat's changed around my projects, bring me the important things. and you're really going to be surprised at how much these newer models can just figure out what you do for work and how you can become more productive. and what's important?

</details>

**Speaker 5**: 没有没有没有没有。

<details>
<summary>Original English</summary>

**Speaker 5**: 没有没有没有没有。

</details>

**Speaker 3**: 一旦你信任这些插件能正常工作，你也可以开始考虑开发自己的插件。我在开发者体验团队工作，很多时候也要处理Slack和推特上各种琐碎的反馈。所以我发布了一些技能，专门用来做委派和分类。它知道某个功能是谁开发的，以及我需要把这个问题发到哪个Slack频道，对吧？我可以为自己投资这些，然后和团队分享。你几乎可以成为插件英雄，对吧？你构建这些自动化工具，不仅能提升自己，还能提升整个组织。但有时候，信息并不是通过让Cotext读取Slack来获取的，比如我刚刚在推特上看到了什么。这是一个非常酷的功能，叫做“快照”。它是我一直以来最喜欢的特性之一。你只需要按下空格键旁边的两个Command键，就像“咔嚓”一声，它就会截取应用程序的屏幕截图，加上所有的上下文和辅助功能树。然后我和Cotext的对话基本上就是：我拍个快照，然后在Slack上对话。我就直接说“回答这个问题，回复过去，再提一个低质量的请求”。这很重要，然后把它变成一个技能。我实际上在训练我的技能上投入了太多，以至于我常常感觉自己就像一个能量网络。我拍个快照，发送问号，然后AI就得自己搞清楚：“哦，有人在推特上因为某个故障要求退款，让我去处理一下”，对吧？所以，如果你今天想做点什么，就试试快照工作流，对吧？也许你正在阅读推特和Slack上的反馈，你拍个快照。Cotext就会触发一些分类技能或沟通技能，在内部Slack和外部推特之间进行协调。然后你就把那个讨论串钉起来。好的，这是一个故障，这是人们在推特上遇到的一些速率限制问题。让我们想想怎么处理，我们可以把它钉起来，然后随着时间的推移跟进。让我们把这个任务分配给正在处理这项工作的人。所以现在，基本上，我的侧边栏就是我管理的每一个项目，就像一个员工讨论串，我时不时地醒来看看。我有一个单独的讨论串，用来管理所有面向AI的文档，用于维护开源社区。同时，我还有一个讨论串来管理X平台的反馈。如果你想每三十分钟关注一下，你只需要告诉它去做。就这样，它就会每三十分钟醒来一次，检查更新，并更新你周围的上下文。你也可以对拉取请求这样做，对吧？你只需要说：“确保测试通过。每小时检查一次，处理所有反馈。如果CI坏了就修复它，并确保它随时可以合并到主分支。”它就会照做，对吧。我还会做一些事情，比如协调支持。呃，检查一下Slack上是否有人回答了问题，如果你能回答，就在推特上回复，然后也更新我的员工讨论串。它们每三十分钟醒来一次。我不确定我的Token够不够用，我设的是三十分钟。如果你用的是Pro计划，每天做两次就已经非常非常高效了。但你不光可以在自己的电脑上运行这些自动化任务，你也不必一直守在电脑前，对吧？这就是像“远程控制”这样的功能真正派上用场的地方。远程控制功能让你可以从手机上，在云端查看你电脑上的所有本地和远程讨论串。所以现在很多工作都可以在公园里或者骑自行车的时候完成了。这真的很方便。

<details>
<summary>Original English</summary>

**Speaker 3**: once you trust the pluggins work, you can are also thinking about your own plugins. so so i work on the developer experience team, a lot of the time of m also just dealing with all of the meiness of the feedback on slack on twitter. and so i puput out some skills that just do delegation and tology. it knows given some feature who's worked on it and what slach i need to hear this in right? and i can invest in this for myself and then share this with the team. and you can kind of become the plug in hero, right? you build these automations, and you can skill not only yourself with the entire organization, but sometimes you know, the text doesn't really come in by asking cotex to read slack and figure what i just saw or read twitter. this is really cool future called apshots. it. it one of my favorite features of all time. all you have to do is press both commandties beside the space bar, right is just like pitch, and it'll take the screen shot of the application, plus all the context and the accessibility tree. and then half my conversation with codex is just. i take a snapshot of something and have a conversation on slack. and i just go like answer this question, reply back also make a poor quequestive. it's important and turned this into a skill. i've actually invested so much in my tree arging skills that usually i just feel like a manergy net. i take ken apshop. i send the question mark, and the AI has to figure out, oh, someone ask for, like credits from twitter based at some outage and let me go handle this, right? so if you just do anything today, you try try an p shot, workflow, right? ybe. you're reading some feedback on twitter and slack, you take an apshot. cotext will then trigger some kind of tiogan skills or some calm skills to communicate between the internal slack versus the external twitter. and then you just pint that thread. okay, this is some outage. this is some great limit issue that people are facing on twitter. let's figure how we can manage this, and we can pin this and work with it over time. and let's bring this apart two working on the work. so now basically, my site bar is just every single project i manager, just a cheep of staff threread just wawake up every once in a while. i have a single thread that runs all the documentation from an eei e for the ssdes II, maintained the open source community. and also, i just have a thread tomander x feeback. and if you want to do something like keep an eyon it every thirty minutes, you just ask you to. and just by doing that, it will just wake up every forty thirty minutes, check forty updates and update the context that's around you. you can do this to babies at a poll request, right? you can just say, make sure the test are green. check every hour address all the feedback. if CI is broken fix it and make sure it's always merggible into mine, and and i'll do that, right. i also do things like corneating support. uh check that someone on socks. as answer a question, if you can answer the question, then report back on twitter and then also my keeof staff ththread. they just wake up every thirty minutes. i don't if my tokens i do thirty minutes. if you are using on your proe pllike doing it like twice a day is a very, very productive, but not only can you run these automations on your computer, you don't have to be glue to your computer, right? these are where is is where features like remote control really come in. so remote control is the ability to view every local and remote thread on your computer in the cloud from your phone. and so a lot of work now now can be done like at a park are riding a bike. it's actually pretty convenient.

</details>

**Speaker 3**: 好的好的，上周我在做一个发布视频。这不像我们那种代码库的发布视频。有人给了我一些反馈。于是我掏出手机，告诉我的电脑去找到那个视频，做一些修改，导出视频，分享到Slack上，然后监控那个Slack讨论串，并说：“好的，每三十分钟，如果有人说话术不对或者时机不对，我们就尝试修复并做一个修订。”当我回到家处理这个视频时，已经没有需要执行的反馈了，对吧。但讨论串真的只适用于单一的工作流。我强烈推荐的另一件大事就是建立一个记忆库，对吧？就像我设置了一个类似城市环境的通用日志。我有一个人员目录，一个项目目录，还有一些代理笔记。如果你扫描这个二维码，你会得到一个我如何设置我的系统的模板。所以你可以直接拉取这个仓库，告诉Cotext“帮我设置好”，它就会安装我使用的所有技能，并引入我强烈推荐的目录结构。最后，你可以选择你想要交互的表单。例如，同样的插件，我可以读取上下文，对吧？你可以读取邮件。你也可以起草东西。我不知道在座的是否有人真的信任AI代你发送邮件和群发消息。但一般来说，我现在的大部分自动化任务也会准备草稿。所以我审查的每一封邮件都已经有了草稿，每一条Slack消息，或者有人问我的问题，都已经有了草稿。你还可以用Artifacts取得很多进展。你可以制作PDF、幻灯片、Excel和文档，它们都可以在Cotext中打开。这样，你就可以直接在应用程序中进行注释和反馈。最近，我们推出了一个网站功能。所以现在你可以像可视化应用程序一样，用Chat ABT登录，连接你的数据库。你实际上可以拥有一个在整个组织内共享的应用程序。所以，越来越多的时候，与其分享一个谷歌文档，我可能实际上会分享一个带数据库的网站，来与团队其他成员沟通并跟踪某项工作的进展，对吧？也许是发布就绪检查，也许是某种迁移。如果没有集成，没有插件来做某件事，这就是像“计算机使用”功能派上用场的地方，对吧？Cotext有一个非常强大的浏览器，基于与Less相同的可访问性模型构建。所以你可以用它在浏览器端做很多事情，对吧？你可以有身份验证。你可以在后台运行多个标签页。如果是一个原生应用，那么你可以使用通用的计算机使用功能。使用计算机使用功能时，它不会接管你的屏幕。它仍然使用辅助功能树，并允许你在后台控制计算机。所以很多时候，我就在做我的工作，然后我切换到另一个标签页，或者打开另一个应用程序，然后我意识到Cotext正在做它需要做的事情来完成任务，这些事情也非常强大。

<details>
<summary>Original English</summary>

**Speaker 3**: 好的好的，last week i was working on a launch video. i this is not like us code bases with launch video. someone give me some feedback. and so i pulled out my phone, and i told my computer to go find the video, make some changes, an eye movie, share the video on slack and just moter of that slack thread and say, okay, every thirty minutes, if someone says the wording is off for the timing as we are try to fix it and a revision. and when i got back home to work on this video, there was no more feedback to execute on, right. but threads really just work across a single workstream. one of the big things that i really also recommend is just setting up like a memory base, right? like i just using up a city involve gengenerally looks. like i have a people's directory. i have a project directory in some agent notes. and if you scan this horarcode, you're going to get a template of how i set up my my system. and so you can just pull this repoo tell cut as i set up for you, and it ininall all all the skills that i use. and introduce to save structures that i really recommend. and then lastly, you can sof choose the forms that you want to interact over. for example, the same pluggins i can read context, right? you can read email. you can also draft things II don't know if people here really trust aid to send e mails and masd messages on your behalf. but generally, most of my automations now also will prepare draft. so every email that i ever has when i review it theis already a draft, every slack message or someone asking me a question already, have a draft set up there. you can also do a lot of progress, make a lot of progress with artifacts. you can make pdf and slies and excells and documents, and they all open within the coexcept. in that way, you can just annote and give feedback directing the application. and then recently, we've launched a sitet's feature. so now you can just like vipudular applications, you have logging with chat ABT, and you can connect your databasand. you can effectitively have application that you share across the org. and so more and more. and there sharing a google dog, i might actually just share a website with the database to communicate the rest of my team and track a progress of some kind of work, right? maybe launched ready this or maybe it's some kind of migration. and if there's no integration, if there's no plugged to do something, this is where things like computers comes in, right? codes has a very powerful browser built off the sympaonology y built at less with. and so you can do a lot with things on the chconomic centurm side, right? you can have uh authniication. you can have multiple tabs running in the background. and if it's a native app, then you can use just general computer use right with computer use. it doesn't take over your screen. it still uses the accessibility tree and allows you to control computer ter in backackground. and so ten times, i'll just be doing work. and i slit it to a tab, all chose them on other application. and i realize that cotex is just doing when it needs to do to get the job done, and these things are also incredibly powerful.

</details>

**Speaker 3**: 对对对的对对。呃，在过去的一周里，我让Cotext做了很多有趣的事情。它帮我拿到了机票退款，对吧？它只是每五分钟检查一次客服频道，然后它就想要把我的钱要回来。呃，每当我看到一个很长的表格，我就直接截图发给它，然后说：“帮我把这个填了”，你知道的。最近，我——我完全不推荐这么做——但最近，我让Cotext用文档签名功能签了一份文件，然后发了一份传真给我的医生。哦，我就发了一份传真。这就像，你知道的，faxpdf.com 那种感觉。

<details>
<summary>Original English</summary>

**Speaker 3**: 对对对的对对。uh. in the past week, i've had cotex to a bunch really fun things. it's gotten me refunds in a plane ticket, right? it just checks the customer support channel every five minutes, and it's it just wanted to get my money back. uh, every time i see a really long form, i just sian abstra and and say, say, fill of this one for me, you know, recently, i had, and i don't recommend this at all. but recently, i hea coltex use document, sign and sign a document and then send a fax message to my doctor. and oh, i just send a fax message. this is like, you know, facx PDF dot com.

</details>

<!-- chunk 13/54 -->

### 利用 Codex 实现自动化工作流

**Speaker 3**: 我会请你把注意力放在输入 CudcoCard 信息上，然后我们就可以继续了。其中很多步骤都是自动化的，这真的很有趣。你也可以使用原生的测试应用，大多数时候都是这样。当我在开发 Cotex 应用时，我只需启动另一个版本的 Cotex 应用，而主 Cotex 就在进行测试。功能正在构建中，我可以看着它做这个动画，或者我可以去做别的事情，你甚至可以出去骑自行车。最近，大概两天前我才知道，它居然还能通过屏幕镜像来控制 iPhone。我还不太清楚我们能拿这个做什么。我觉得这是一种很酷的体验，不仅能控制你的电脑，还能通过屏幕镜像这类技术有效地控制你的 iPhone。

<details>
<summary>Original English</summary>

**Speaker 3**: I use you your attention to put the cudcocard information, and then we can go for that. And so a lot of these are automated in that really fun. You can also use the test native applications, right most of the time. When i'm working on the cotex app, i just spent up another version of the cotex app, and the main cotex is just testing. The future is building, and i can watch it, do this animation, or i can just go and do something else, and you can write a bike. And recently, i didn't know this and told, maybe like, you know, two days ago, it somehow can also control the iphone through screen miring. I don't know what we can do with that just yet. I think there's very cool experience and that only build a control your computer, but effectively control your iphone just through technology like through swimmiring.

</details>

**Speaker 3**: 那么你可能会问，计算机使用能控制 Codex 吗？答案是，你其实不需要这么做，因为就像我之前说的，这些 Codex 线程已经可以互相通信了，这意味着你已经有了管理者。在之前的例子里，如果有人通过 Twitter 或 Slack 给我的模型提供反馈，我可能会截个图。我截个图，让智能体收集信息，然后上下文树会找到正确的工程师，弄清楚如何沟通这次故障，然后我固定这个线程，对吧？但这仍然需要我手动截图，或者让智能体执行某种操作。但因为线程现在可以互相通信，你真的可以改变工作方式。

<details>
<summary>Original English</summary>

**Speaker 3**: But then you might ask, okay, can computer use control codex. And the answer is that you don't really have to because like i said before, these codex threads can already talk to each other, right, which means you already have managers. So in the earlier example, where i say maybe someone is giving me you model feedback or or on twitter on slack, i might take a screen shot. Take a apshot. I might have the agent gathers. And context tree osha, the right engineer, figure how to communicate this outage. And then am i pin the thread, right? But this still requires me taking the app shop or taken having the agency to take some kind of action. But because threats can now talk to each other, you can really change the way do at work.

</details>

**Speaker 3**: 现在，我有一个单一的监控线程，这个线程每小时醒来一次。它仅仅通过计算机使用或命令行界面读取所有的 Slack 和 Twitter 信息。然后它会尝试找出我们面临的主要问题。接着，它不会自己处理分类工作，而是创建一个新线程，给它重命名，并初始化它。那个新线程的任务就是弄清楚如何分类，而那个线程的工作是进行沟通。然后那个线程负责执行自动化。也许一天后，另一个人也对这个议题提供了反馈。主智能体可以说，好的，这仍然是一个未解决的问题，似乎没有人处理它。让我给这个关于速率限制故障的线程发一条消息。然后那个线程可能会决定在 Slack 上发帖、提问、阅读文档，或者查看是否有待审核的 PR。一旦你理解了这些围绕编排线程、启用心跳和计算机使用，以及让这些智能体互相通信的基本概念，你就可以做这些非常酷的事情。

<details>
<summary>Original English</summary>

**Speaker 3**: Now. I have a single montherthreat, and that threat wakes up every hour. And and just using computer uther are using the cli reads all of slock and all of twitter. And then it will try to figure out what are the big issues that we have. Then instead of doing the triotion acaccount itself, i'll make a new thread. It'll rename it, it'll in it. And then that threats jobs, i figure how a trioge that jobs that threats job s had to do communications. And then that thread is one to does this automation. And then maybe in a day from now, maybe someone else also hasno feedback about this issue. The main agent can can say, okay, this is still an ongoing issue. It doesn't seem like anyone's address this. Let me send a message to this thread about the like great limit outage, right in that bed might decide to post a message on slack or ask a question or maybe read the dogs or youyou, see if any porequests are pending review. And these are the kind of really cool things that you can do. Once you understand these basic concepts around painting these threads, enabling heartbeath and computer use. And then just allowing these agents to talk to each other, right?

</details>

**Speaker 3**: 所以我真心希望，通过这次简短的分享，我已经让你相信工作的本质已经改变，Codex 正在发挥作用，对吧？总的来说，我觉得我们离实现持续学习已经很近了，只需通过一个带有记忆库的固定线程，使用插件和计算机执行操作，并确保将信息记录在你的记忆库中，你就可以在提高生产力方面取得很多成果。只需通过心跳机制，告诉 Codex 持续关注某个任务，你现在就可以运行这些自动化流程，让你的工作主题跨越不同的会话。所以我认为，如果你是一个忙碌的开发者、经理或高管，这是一个非常好的使用 Codex 的方式，不仅仅是为了编码。如果你想在你的小操作系统中跟踪所有事情，如果你想用一个便宜的杂务线程来管理你的每日简报或会议研究，或者如果你想用循环来自动化你的工作。对对对，去看看 Codex，尝试一下这些想法。然后今天下午 2:50，在第四轨道，我们会做一个更长的、类似工作坊的活动，我们可以进行更深入、更长的对话，讨论我们实际在做什么，我可以给你们关于我如何使用这类自动化的具体反馈。最后，欢迎来到开放展位，我们就在正中间，你不会错过的，那里很有趣。谢谢大家。

<details>
<summary>Original English</summary>

**Speaker 3**: So i really hope that in this quick session, i've really convinced you that the nature of work has changed compacsion works, right? Generally speaking, i feel like we're pretty closer things like continue learning by just having a memory base in a pin thread and by taking actions using plugins and computer use and making sure you write things down in your memory revolt. You can get a lot of results in terms of how you can improve your paractivity. And by just having something like a heartbeat, just by telling codex, keep it out on this, you can now run these automations that carry your worktheme across different sessions. And so i think if you 're a busy developer or a manager, an executive, this is a really great way of using codex, not just for coding you if you want to keep track everything in your little opposidiinvovolt, if want want to use a cheapp staff threat to manage your daily briefs or your meetings research, or if you just want to use loops to basically automate this work. 对对对 ah check out the curts out, try some of these ideas out. And then today, at two fifty PMI track four, we're na do a longer like our long workshop, where we could actually have a longer conversation and deeper conversation about what we actually do. and i can give you guys and feedback on the specifics of how i've been using these kind of automations. And and lastly, comes to hello at the opening ebooth. we're right in the middle. you can't miss it. it's lot of fun. and and as it thank you.

</details>

### 生产环境中智能体的可复现性与调试

**Speaker 0**: 现在突然之间，你的团队开始集体讨论，试图弄清楚到底发生了什么。这在当前作为标准生成响应时很常见。你会被告知从临时日志中提取原始提示，将其传递给同一个模型，使用相同的提示，并在本地运行以隔离错误，我们都会这么做。令人惊讶的是，它会正常运行。再运行一次，它还会正常运行。你运行十次，每次都会完美运行。但我们现在讨论的是那一次运行，它导致了问题，但现在已经消失了。你无法复现它。如果你无法复现它，你就无法调试它。如果你无法调试它，你就无法修复它，它可能会发生在你的下一个客户或用户身上。现在，我是 Fisher，我是 CoCo 的联合创始人。我们针对真实的生产后端运行智能体。你知道，那种情况比这更糟糕。你正在和客户通电话，解释数据到底去了哪里。我整个演讲都将围绕这一点展开：当智能体在生产环境中失控时，最重要的一件事就是能够复现它。这将是接下来十分钟的起点。我们来分析一下这到底是如何搞砸的。你有一个智能体，它搞砸了一个应用，比如用户说“卖出价值一千美元的股票”。现在有趣的部分来了，智能体没有做数学计算，而是说“数量：一千”，然后直接把这个数字填入了数量字段。是的。它写的是“一千”，但实际上，如果股价是一百九十美元一股，一千美元只能买大约五股，但这里却变成了一千股，价值十九万美元，这完全是个灾难。更讽刺的是，PI 返回了一个干净的 200 状态码。在百万分之一秒内，我们得到了零异常、零错误。如果你看日志，一切看起来都完全正常。你觉得它完美无缺，然后突然之间，就像我们上次讨论的，问题就冒出来了。

<details>
<summary>Original English</summary>

**Speaker 0**: And now suddenly, your team is on a on corrotation to figure out what actually raintruck pretty common right now as one standard and genaning response, youare got to retell you to pull the row prom from the tedimetary logs, pass it to the same model, using the same prob and run it locally to isolate the bug, which we all do. And surprisingly, it will work as well. rn it again, it will work again. you you run it ten more times, it will be just perfect every time. but now i've talk about that one run, which cost studio and but will be gone. you can reproduce it. and if you can reproduce it, you can debarg it. and if you can debug it, you can't promise it might happen to your next customer or user right now, i am fisher. i have ashimved me as my cocoo enenter. we won't rangagents against real production backons. you know, the kind of place better bad, right isn't over l than it in. it's you on a call with a customer explaining fed the data actually went. this whole talk is going to be about that. one thing to lose the second and agent goes habby in production, which is being able to reproduce it. that will be a not start for the next ten minutes to follow. nalyps. look are how this actually blows up. you've got in an agent hook who 've broke a app i, which is this and how you am taking the user, says him, sell a thousand dollars of stock. now comes interesting part instead, ad doing the math, the agagent stastays, the roong number one thousand and dumps it stayed into the quantifill. yes. well, it says one thousand and has instead now at a hundred and ninety boxes share a thousand dollars in ten will waak up how much a hundred and ninety thousand dollars disaster right. and the terariicide parties that the PI on my inwer t returned a clean to hundred hundred. okay. in milmillion seconds, we got zero excepzero zero erts. if you see the deep, it's completely work back your dice food. that's you think that perfectly green perfectly flooders, then such as NIU as we last discussed comms up up whathe.

</details>

**Speaker 0**: 你接下来会尝试做的事情，就是尝试修复它。这里的本能反应是，你知道，把模型温度降到绝对零度，假设贪婪解码会让一切变得确定，但这完全是一个误解。把温度设为零并不能修复一个错误的推理路径。它只是意味着模型会在完全相同的时间，以完全相同的方式，犯完全相同的逻辑错误。老实说，甚至更糟。回到我们刚才讨论的场景，看看 Reddit 和 Hacker News 上的抱怨帖子。硬数据表明，温度为零在硬件层面甚至都不是真正确定的。运行相同的提示一千次，仅仅因为架构中的非确定性和浮点运算，仍然可能产生几十种完全不同的响应。所以要理解为什么会发生这种情况，我们必须从基本原理来看。这归结为四个简单的事情。第一，采样确定性与系统确定性。温度为零只意味着总是取 arg max，但它并不能保证底层核心在每次运行时保持一致。浮点运算不满足结合律。你在模型中添加的顺序不同，对吧？但矩阵乘法操作中的时序偏移会改变最终的逻辑，这反过来又会改变胜出的 token。这不是一个一致性问题。在 GPU 上单独运行同一个数学应用一千次，我保证每次结果都完全相同。所以真正的罪魁祸首是批次差异。因为请求会与同一毫秒内到达的其他请求分组在一起。混合专家路由具有完全相同的工作方式。关键专家有严格的容量限制。如果一个批次溢出了特定专家网络的 token，多余的 token 会被静默地路由到其他地方。一个 token 是否能进入专家网络，完全取决于它与谁一起被批处理。所以这里的寓意是，追求完全相同的文本输出是一场必输的战斗。我们不需要模型每次都返回完全相同的 token。我们只需要我们的系统执行完全相同的状态转换。这意味着我们一直以来都问错了问题。错误的问题是：我如何让模型变得确定？我看到团队在这个问题上浪费数周时间，最后得出结论说系统不可靠。正确的问题是：我如何调试和测试一个我无法复现的运行？因为确定性从来都不是调试的起点。两个字，我们混淆了，我现在要讲的是，字节级确定性与可靠性是两回事。确定性是相同的输入产生相同的输出，这是可控性。你无法从一个托管的 API 获得这一点。

<details>
<summary>Original English</summary>

**Speaker 0**: The thing thing you will do, do try, try and fix this. The reflex here is, you know, just just n the momodel temperature down to absolute zero ashuming greedy recording will make everything deterministic right, but that's a complete misconception setting. the temperature to zero doesn't fix a broken reasoning park. it just means the model is going to make the exact same logic letter, the exact same me be at the exact same time. and honestly, even worse than that, go back of the scenario we just discussed. look at the jeeling craads on red and heconnews. the hard data shows that temperature zero is it even truly deterministic on a hardware level running the same prompked, a thousand types can still to turn dozens of completely different responses just due to the anlangg, non determinisism and the my architectures, which are there. so to understand why this actually happens, we'll have to look at it from first principles. it comes down to four simple things. one sampling determinminism is in system determinism temperatures. ero just means always take the arg max, but it doesn't guarantee that the underlying cores stay identical rann to her two sloating point math isn't associated the order. you add your disal medals, right, but a timing shift in matdx oooperation il thors the final logic and which in turn will slipped the winning token 谁. it's not a conferency issue, run the same raticx prise application alone in AGPU or thousand times, and i'll guarantee against exact saambridge. so the real culture, it is batch vadiance here, because it request gets group with whatever as hit the celva that mili second food mixture experts rououting has the exact same work. king leck experts have strict capacity elements if a patats overflows a specific of network tokens scadtly rouded, whether ver token makes the cy depends entirely on the graffic you guard batched with 嗯, so the automatically here is that chasing text outputs is a losing butter completely. we don't need the model to return the exact same token back every time. we just need our system to execute the exact steam state transition, which means s we've been asking the wrong question on allog lade. the wrong question is, how do i make the moderor determinissttic? and i think team's burning weeks on that and walk away deciding the systems is annoyable. the right question is, how do i debug and gretest run? i can't reproduced because determinisism was never nonot star debugging boys. two words, we give mixing up, which i talk about now is bytified determinism and reliability is advise. determinism is same input, same output that's control ability. you're not getting it from a hostdy API.

</details>

<!-- chunk 14/54 -->

### 可观测性与可靠性：记录边界

**Speaker 0**: 你真正想要的是那个“异常”，因为正是这种异常让模型变得优秀，推动模型进化。你会得到更多的创造性。而另一个维度是可靠性，这更像是一条已经运行得足够好、可以进行调试的记录。这就是可观测性。你不需要模型去“管理”错误，你需要的是错误被记录下来，并且你不去冻结模型，而是捕捉它所做的事情。

<details>
<summary>Original English</summary>

**Speaker 0**: and you dold actually wanted because that anamess is what makes the model good, advance the model explodes. what you'll get more create vantness. the other vil's replliability, which is river, is a run that already happened well enough to debug it. that's observability. you don't need the model that a ministke, you need et rent recorded, and you don't freeze the model, you capture what it did.
</details>

**Speaker 0**: 另一个我们都在思考的问题是：你应该从哪里记录？当然不是在网络层，因为你的代理有一半永远不会触及网络。网络、本地检索、进程内工具、记忆以及那些不在流式处理和SSE下的部分。相反，要在边界处记录，因为你需要捕捉进入每个节点和离开每个节点的内容——每一步的含义，而不是数据包。

<details>
<summary>Original English</summary>

**Speaker 0**: another question, which we are all thinking about is where do your record from? sure. not at the network layd because half your agginwill never text. the network, the local retrieve the in process tools, the memory and the parts that do not read under streaming and essay 没有 record at the boundary instead, because you need to capture what enters each note and what leaves it the meaning of each step and not the packkets one three play ads.
</details>

**Speaker 0**: 这里有一个确定性的CI，你可以停止模型，我们将使用相同的模型调用精确地重现失败路径。让我们谈谈这个循环，它始于关于可视化、理解和修复的修正。然后是实际工作的部分，即深入调试并最终验证。好了，现在让我们看看如何将刚才讨论的工作付诸实践。

<details>
<summary>Original English</summary>

**Speaker 0**: here is a deteromisstic CI, where you stop the modern, will we run the exact failure of line with thero model calls 嗯嗯嗯嗯嗯？ let's talk about the loop and the and now it starts with ammidation regarding visusubalization understanding fixing. then the party working on which is dedeeping unfinally verified. all right. let's now see how to bring the work lolobe just discuss into action.
</details>

### Chronical：基于边界的可观测性框架

**Speaker 8**: 我们已经确定，可靠性是任何代理产品化的一个必要条件。但是，我们如何构建代码作为这个概念验证呢？我们所做的是构建了一个名为Chronical的东西。Chronical的核心是“边界”的概念。把边界想象成你代理工作流中任何节点周围的边界框。一个节点可以是一个工具调用，可以是对LLM的调用，也可以是从向量数据库的检索。只要它是一个方法，就可以用`@boundary`注解进行标注。这个注解是做什么的呢？它确保任何进入该方法以及从该方法出来的内容都会被记录。所以任何输入和输出都会被记录。在此基础上，你可以定义参数，比如模型版本或正在运行的代码版本。这样，代理运行期间的整个状态都会被冻结并保存为一个追踪记录。

<details>
<summary>Original English</summary>

**Speaker 8**: so we established that reliability is a coordinate of produtionizing. any agent, but how do we build this code as a proof of concept for this? what we have done is we have built something all ctronicical at the heart of chronical lies the concept of a boundary, think of a boundary as a bounding box around any node in your identic al work. lp a note can be a toolcone. it can be a called to an ilyym or reretrigual from iraq. it doesn't matter as long as it's a method can be annodated with the bounctuary annotation. now, what does asannotation do? it ensures that anything that goes into the matter and comes out of the matter, gets regarded it. so any input and outprepaare ly get regarded on totop of that, you can define parametis like a model version or the version of the code that is running. so that the entire state, during which the agent run happened, gets frozen and saved as a trace.
</details>

**Speaker 8**: 现在让我们看看实际效果。我们一直在谈论这个股票交易代理，它已经投入生产。这是同一个代理的表示。你有初始规划步骤，它接收用户输入。它可以使用下单工具来实际执行股票的卖出和买入。然后最后，它委托给查找工具。

<details>
<summary>Original English</summary>

**Speaker 8**: now let's see this an action. 对对对, we've been talking about this stockselling agent, which went he have ad in production. this is that representation of the same. you have your initial planning step, which takes into look on the user input. it can use the place order to ooe to do the actutuselselling in buying of the stocks. and then finally,
</details>

### 软件工厂：自主软件开发的全生命周期

**Speaker 7**: 嘿，大家好。我是Mraza，今天我们将讨论软件工厂。每个人都在谈论软件工厂，但只有少数人真正在构建一个。而更少的人知道构建一个软件工厂到底需要什么，以及如何定义它。所以我将讨论：什么是软件工厂？我应该自己构建还是外包？哪些已经在生产中有效？仍然存在的挑战是什么？以及这一切要花多少钱？

<details>
<summary>Original English</summary>

**Speaker 7**: hey, what's up? i'm mraza ah, and today will be talking about software factory. um everyone is talking about software are factory, but only few people are actually a building one. and even fewer people know what it actually takes to build one and how to define it. so i will be talking about what is softwt factory, should i build your own over outsort, said, what works in production already, what i remain challenges. and how much is this all going to cost?
</details>

**Speaker 7**: 我叫Storiza，我在一家名为Factory的公司工作。我们构建软件工厂这个概念已经很长时间了。但最终，技术正在赶上，现在为企业（如UI或AV）在生产中构建它是可能的。我将软件工厂定义为整个循环，即自主开发软件的整个生命周期。这不仅仅意味着编码和生成代码。我的意思是，像收集所有信号、响应用户反馈和日志、确定优先级、编排所有内容、执行、验证、在生产中进行良好的测试，然后在此基础上迭代，同时在这个过程中持续改进，并获取新的知识和技能。

<details>
<summary>Original English</summary>

**Speaker 7**: uh my name storiza, i ked at a company called factory outcome. and if we've been building um this concepcepof, the sofare factory for a quite a long time. but finally, the technology is sketching up, and it's possible to build this in production for enterprises like UI or AV. uh, i would defind a software factory as the whole loop, the whole life cycle of developing software with automomy, which doesn't mean just coding and generating code by that. i mean, collike thing, all the signouncis reacting to use it, feedback to logs, prioritizing, what's important, then orchestrating it all, executing validating, doing gretly good testing in perrection, and then iterating on audis well, while also continuously improving in the process. and gaining new knowledge and new skills.
</details>

**Speaker 7**: 这是一些历史。说到历史，我指的是2023年。所以软件工厂以前真的不可能实现，尽管我们从GPT和其他模型发布之初就有这个想法——这个持续循环的想法。当时有AutoGPT、BabyAGI，它们已经具备了在软件上迭代的概念。但以前行不通。模型的问题在于，它们太啰嗦了，存在上下文长度问题、推理质量问题，不同的程序都是如此，或者我们缺少良好的环境让代理能够在隔离环境中实际工作。所以，这解释了为什么软件工厂这个范式现在才开始流行并且真正有用。

<details>
<summary>Original English</summary>

**Speaker 7**: 好的好的好的, uh, this is just some history and by history, i mean, two thousand, twenty tree, an AI. so the software factory wasn't really possible before, even though we always had this idea from the beginning of uh GPT launch and others, we had this idea of the continuous loop. there was outo GPT, baby agi and earready with the concepts of iterating on the software. but it didn't work before. but the alamms were how how losenating thing there was problem problem with contex land problem problem with the reason quality, a different programs like this, or we are missing good environments where the agents can actually work in the isolation. so oldest, kind of lets to why the software factory is the paradigm that's starting to be popular now and actually useful 啊,
</details>

**Speaker 7**: 我喜欢通过定义“它不是什么”来定义事物。所以我想说，软件工厂不仅仅是编码代理，甚至不只是一群编码代理。即使有成千上万的代理也不行，因为生成代码、编写代码，与其他所有事情相比，那是容易的部分。工程师甚至不会把大部分时间花在编写代码上。挑战在于其余的部分。这就是我想要强调的。它也不仅仅是一些咨询服务。那不仅仅是别人试图卖给你和你组织的某种策略。我认为方法当然不同，但我们相信你应该真正地从零开始重建你的组织，使其准备好成为一个软件工厂。你不能请个咨询公司，然后往你组织中间扔点东西。你真的应该深思熟虑，从头开始重建。

<details>
<summary>Original English</summary>

**Speaker 7**: i like to define things by what they are not. so i want to say soft facfactory is not just coding agent, and it's not even a swarm of coding agents. even thousands of agents because generating code right iting code, that's the easy code comppared all the others ers. engineers don't even spend most of it. uh, just the right thing code, the challenges are the rest of it. um so this is what i want to enhance, and it's also not just some consultancy. that's just not just some strategy that someone will try to sell you and your organizzation. i think approachis are, of course, different, but we believe you should reliate build your organization from ground up to be ready to become ssoftware factory like you can't invite the consultancy and just throw something in the middof your organization, you should really be mindful and rebuilded for from scratch.
</details>

**Speaker 7**: 这是我喜欢的构建软件工厂的方法。我认为这和构建一个真正的人类团队很相似，因为有很多代理，正如我所说，它们会测试各种东西，迭代各种东西，所有这些最终可能变成一团乱麻。所以你需要深思熟虑。我想说，在软件工厂中，最重要的事情是“模型无关性”。也就是说，作为组织，独立于LLM的选择。然后你需要是“自主的”。所以你需要赋予代理正确的信任、权限和治理，并且你需要信任它们能够自主运行很长时间，因为代理的预测周期很长，甚至可能一年或更久，而无需人类介入。当然，这听起来很雄心勃勃。但是，例如，Devin已经有一些长时间运行的会话，已经构建了一些东西并运行了数周。所以这并不那么疯狂。同样，就像人类组织一样，你需要通过提供良好的代码库、对良好结构的理解、文档来“入职”团队中的任何新成员，并且还要让他们在这个过程中改进和获取知识，并在团队内部分享。

<details>
<summary>Original English</summary>

**Speaker 7**: uh, this is the approach i like um showing to building the software factory. and i think it's similar to building the real team of humans, because there is a lot of agents, as i said, they will be testing variday think, iterready think, and it's all can end up as a big cares. um so you need to be mindful. and i would say, the team important things is being aggistic in the software factory. so being independent of alelem choices of how how be already as the organization, then you need to be alanimous. so so you need to the agents ts their right thtrust and oldest permissions and governance, and you need to trust it to run early for a long time because the predictions are the agenciof viaround, even even a year or more years without the human induloop. of course, that sounds ambitious. but for example, admissions already out a long gunning sessions already build uh things and run for weeks. so it's not that crazy, and there think, think always crazy. so same as human organization, you need to underboard any new people in your team by giving them good code base, understanding good structure, documentation, and also let them improve in the process and gain. you knowledge, share it, share it within the team.
</details>

**Speaker 7**: 所以这是三个要点。现在让我们谈谈“模型无关性”这一点。我认为需要指出的是，如果你是一个构建者，正在构建软件工厂的不同原语，你需要为每个人已经使用的方式做好准备。你需要跨环境工作，比如LLM、GitHub，并将其连接到一切，你还需要允许人们引入他们正在使用的订阅。因为每次都有新技术、新前沿模型、新基准，要赶上非常困难，但要预测哪个会胜出也同样困难。所以最好对每个人都保持无关性。然后是关于对模型保持无关性的话题。这是最近很多讨论的话题。这张图表来自Coinbase的CEO，他谈到了这一点。他们开始在AI组织上节省资金，但没有减少token的消耗。黑线是他们花费在token上的金额。他们继续增长token消耗，但他们停止了花费那么多钱。他们是怎么做到的？不同的技巧，比如为人们设置不同的默认模型。所以停止推动人们只使用不同的层级作为默认，然后是缓存，当然，是为了避免每次都重新处理内容，然后对支出没有限制，但需要看到结果，如果你花了很多钱。最后一件非常重要的事情是智能路由，即在LLM之间进行智能路由，并在LLM之间进行token优化，而不是花费那么多token。我们在Factory中构建了一个叫做自动模型路由的东西，对此有很多疑问。但它所做的是在你的流程中自动在不同模型之间进行路由。重要的是，它首先决定哪个模型是最优的。然后，如果它在任务中失败或出现任何问题，它可以切换到不同的模型，但这通常不会发生。重要的是，它不仅有助于节省资金。它还有助于提高可靠性或速度，某些模型通常更快。而且，如果一个提供商失败，

<details>
<summary>Original English</summary>

**Speaker 7**: so these are the three points. and now let's talk about the agagnostic one. uh think the important thing to point out, if you are a builder and building different primitives of the softrge factory, you need to be ready for how everyone is already working. you need to work across environmenments like llag, get up and connect it to everything, and you need to also allow people to already bring subscriptions. they are using because there is every every time there is new new technology, new frontier models, new benchmarks, and it's so difficult to catch up, but also to predict what will be the winning. so it's best to be agagnostic for everyone. um then there's a topic of being agagnostic to models. um this is totopic of lot of discussions recently tly. this charcharis from this charge is from ceo of coinbice who to beat it about. they they ararted uh started saving money. and their organization on AI, but without they reducing the talkand spent. so the black line is how much they spent on tokens. they continue growing and talken maxicine, but they stop spspding ding much money money, how they did it um different tricks, like different default models for people. so stop pushing people to use only different tears as a default, then cathing, of course, um to stop preering the stuff every time, and then no limits on spending. but just needing to see the results, if you spend a lot. and the last thing that's really important topic is it outing so smart erouting between elamms and just a token optimising between the elyams instead of just spending. so much toens, we built a thing infacfactory called a automatic model routing, and there has been a lot of questions it wounded. but what it does is it's automatic ally outs between different models ls in your prothe. the important thing is its decides first toword model is most optimal. and then um it's can switch to different model if it's failing to task or in case of any troubles, but it usually doesn't happen. 嗯, and important thing is it doesn't just help um spend save money. it also helps a reliability or with spespeed open, certain modeills are often faster. and uh, if one provider fails,
</details>

<!-- chunk 15/54 -->

### 路由与分类机制

**Speaker 7**: 你可以自动切换到另一个模型。所以它不仅仅是省钱。这是我们的基准测试，非常保守。我更喜欢保守的基准，但我认为方向是明确的。例如，你可以节省25%的成本，但即使是Mark可能也清楚这是如何运作的。这里有四个部分：首先，你只需分配一个任务，基本上不需要做任何事情。但作为一个组织，你可以例如给不同的人分配不同的权限和不同的默认模型，这对市场、销售或工程师等不同角色非常有用。然后你有分类，这是重要的部分。这是路由的魔力所在。你需要真正审视提示的结构、代码库的难度、使用了哪些工具等因素，并对任务的难度进行分类。之后，你基本上设定一个阈值，判断什么足以完成任务，然后选择阈值以上最便宜的模型。所以就是选择预测能够完成你任务的最便宜模型。然后就可以了。

<details>
<summary>Original English</summary>

**Speaker 7**: you can just switch to another one automatically. So it doesn't more than just saving the money. This is our benchmark, which is very conservative. I prefer conservative benchmarks, but I think that direction is clear. You can save, for example, twenty-five percent, but even Mark probably knows how the thing works. There are four parts: first, you just assign a task, and you don't really need to do anything. But as an organization, you can, for example, give different permissions and different default models to different people, which is very useful like marketing or sales or engineers, or sales different default models. And then you have the classification, which is the important part. This is the magic of the routing. You need to really look at the structure of the prompt, the code base, how difficult the task is, what tools are being used, all these factors, and make a classification of difficulty of the task. After that, you basically do a threshold of what is enough to accomplish the task, and you choose the cheapest model above the threshold. So the cheapest model that is predicted to accomplish your task. And then you go, okay.

</details>

**Speaker 7**: 所以当我们推出时，收到了很多问题，比如：它真的有效吗？如果模型误判了呢？是更便宜还是更贵？实际上，如果模型无法完成任务，或者需要升级怎么办？我们如何处理这种情况？我认为这些都是合理的问题，这也是为什么构建一个好的路由算法如此困难。你需要非常准确地进行分类。挑战不在于需要频繁切换，而是即使你在任务中途切换到更难的模型，总体上你仍然更快、更便宜。这只是一个路由的概述。我们还收到了很多关于如何处理缓存的问题。我们是否给用户折扣？因为你可以通过缓存和跳过每次发送上下文来节省大量资金。开源模型也可以做到这一点。我认为人们有时会忘记这一点，你也可以托管开源模型。在像DeepCompute这样的平台上，你也可以利用缓存。所以我想强调，最终给用户的价格只是一个定价决策，而不是技术挑战，因为每个人都可以做缓存，问题只在于你向用户传递什么价格，以及你与API提供商达成什么协议。所以这是与模型无关的。

<details>
<summary>Original English</summary>

**Speaker 7**: So when we launched, we got a lot of questions, like: does it actually work? What if the model misclassifies? Is it cheaper? Is it more expensive? Actually, what if the model can't accomplish the task or if it needs to upgrade? And how do we handle that? So I think these are valid questions, and that's why it's so difficult to build a good routing algorithm. You need to classify very well. And the challenge is not the need to switch too often. But even if you're switching in the middle of the task to a more difficult model, you still overall are faster and cheaper. This is just an overview of routing. A lot of questions we got on this were also how do we handle caching? Do we give discounts to users? Because you can, of course, save a lot of money by caching and skipping sending the context all the time. Open models can do this as well. I think people sometimes forget this, and you can just host open models as well. On DeepCompute, you can take the same advantage of caching. So I want to emphasize the final price for users is just a pricing decision. It's not a technical challenge, because everyone can do caching. It's just what price you pass on to the users and what deals you make with the API providers. So this is model-agnostic.

</details>

### 自主性与软件工厂核心

**Speaker 7**: 现在说到自主性，这是软件工厂的核心。每个人都在谈论循环，我认为它们一直存在于不同的上下文中。它们现在只是升级并转移到代理的上下文中。你可能听说过代理循环，将任务分解为子任务分配给代理。这不是新概念。问题不在于循环本身，而在于你如何定义循环中“完成”的含义。这是我同事的一个例子。他构建了一个代理循环来生成一个算法的依赖图。我认为这里你可以看到循环的挑战，因为在编程中，以前有明确的标准来判断什么是“完成得好”。现在，标准是开放式的，因为任务非常不确定。它基本上是开放式的。你可以做像打印东西这样真实的事情。定义和验证任务是否完成真的非常困难。所以这是困难的部分。它们需要是可验证的。

<details>
<summary>Original English</summary>

**Speaker 7**: And now the autonomy, which is the core of the software factory. Everyone is talking about loops, I think they have been here the whole time already in different contexts. They are just now leveling up and moving to the context of agents. You probably heard about the agent loop, specifying the tasks and splitting into sub-tasks for agents. This is not a new concept. The question is not the loop itself, but the question is how you define what it means to be done in the loop. This is one example from my colleague. He made a loop of agents building a dependency graph of an algorithm. I think here you can see what is the challenge of the loops, because before in programming, groups had clear criteria of what it means to be done well. Now, the criteria are open-ended because tasks are very non-deterministic. It's basically open world. You can do even real stuff like printing something. And it's really difficult to define and verify that the loop is done and the task was accomplished. So this is the difficult part. They just need to be verifiable.

</details>

**Speaker 7**: 我称之为“草图图表”。它基本上显示，代理自主完成的任务及其持续时间一直在增加，但仍然不可靠。所以，如果它在实验室里运行很长时间，并不意味着它在生产环境中会可靠，即使你迭代它并提供反馈。所以这个问题还没有解决。存在一些问题，比如作弊。例如，如果你以错误的方式定义“完成”的含义，代理可能会试图通过你的测试，而不是真正验证你需要做什么和完成什么，而是试图仅仅通过你的测试。所以这是通过测试作弊。

<details>
<summary>Original English</summary>

**Speaker 7**: I call this the sketch chart. It basically shows that the tasks and how long agents autonomously work have been increasing, but still it's not reliable. So if it runs for a very long time in the lab, it doesn't mean that it will be reliable in production, even if you iterate on it and provide feedback. So it's not solved. There are problems like cheating. For example, if you define what it means to be done in the wrong way, the agent can try to pass your tests, but not really verify what you need to do and accomplish, but instead try to solve just passing your tests. So cheating by tests.

</details>

**Speaker 7**: 我们有所谓的“任务派遣”，这就像是代理的长时间运行会话。我们称之为派遣，因为我们把代理派去执行任务，任务在循环中工作并迭代直到完成，它们甚至可以持续数周。主代理是编排器，然后它分配任务给工作代理，然后有验证器审查任务。这是一个来自我们客户的真实任务示例。他们运行了16个小时。这正好说明了验证有多重要，它甚至占用了整个过程的40%。总结一下，编排器决定并提高“完成”的条件，然后将其交给称为工作代理的代理，代理们开始工作。有趣的是，它们按顺序工作，而不是以群体或并行方式。每个代理完成一些事情并传递给下一个。

<details>
<summary>Original English</summary>

**Speaker 7**: We have something called "missions", and these are like long-running sessions of the agents. We just call them missions because we send the agent on a mission, and the missions work in the loop and iterate on tasks until it's done, and they can do it even for weeks. And the main agent is the orchestrator, and then it assigns work to worker agents, and then the validators who review the task. So this is one example, a real mission from our customers. They ran for 16 hours. And this just shows how important the validation is, it takes even 40% of the whole process. To summarize, the orchestrator just decides and raises the conditions of what it means to be done, then it gives it to the agents called workers, the agents work on it. And what is interesting is that they work in a sequence, so they don't work in a swarm or parallel, the agents work in sequence. And everyone accomplishes something and passes it to the next one.

</details>

**Speaker 7**: 嗯，我们实际上发现，如果你这样做，最终会得到更清晰的上下文和更清晰的思路，就像人类有其他同事审查他们的代码一样。所以类似的事情，我们只是让代理传递给下一个，但序列中的每个工作仍然可以有并行代理执行更小的任务。所以我不知道它们是在搜索网页还是在那期间构建文件。所以它们是按顺序的，每个都有子代理和验证器。它们审查输出并提供反馈，然后将其发送回起点。重要的一点是，验证器判断他们自己没有编写的代码，对吧？编排器代理代码中有一个验证合约。这是在编写任何代码之前就存在的吗？第一种是常规验证器。第二种是用户测试验证器。严格验证器是真正验证代码如何工作的那个。它真正运行测试。它是对代码非常严格的检查。但第二种，我认为，真正有趣的是用户测试验证器。那个是真正在竞技场中尝试东西的。它不关心代码是如何编写的。它只是运行，在它的虚拟计算机上工作，点击东西，检查一切是否正常。

<details>
<summary>Original English</summary>

**Speaker 7**: Um, we actually found that if you do this, you end up with more fresh context and kind of fresh heads, similar to when humans have other colleagues verifying their code. So similar thing, we just let the agents pass to the next one, but still every worker in the sequence can have parallel agents doing smaller tasks. So I don't know if they are searching on the web or building files during that. So they are in sequence, and everyone has sub-agents as well and validators. They review the output and provide feedback and send it back to the beginning. An important thing, the validators judge code that they didn't write, right? There is something from the orchestrator agent called a validation contract. That is it there before any code is done? The first type is a routine validator. The second is a user testing validator. The strict one is the one that really verifies how the code works. It really runs tests. It's a very rigorous check of the code. But the second, I think, is really interesting: the user testing validator. And that's the one that is really in the arena trying the things. So it doesn't care how it was made. It just goes, it works in its virtual computer and it clicks on the stuff, and it checks if everything works.

</details>

**Speaker 7**: 看到一个工程师用我们的代理迁移旧代码库的例子。它真的需要代理在界面中点击操作，因为如果只是创建产品，它可能创建了产品，但无法交互。它只是一个虚假的结果。所以一个真正在界面上点击操作的代理能够检查它是否真的在工作，而不仅仅是代码看起来不错。我认为这是一件很酷的事情，这也是由计算机使用方面的进步和代理的持久化虚拟机环境所促成的，这在以前是没有的，或者没那么好。但现在真的很棒。它允许代理作为用户进入竞技场。

<details>
<summary>Original English</summary>

**Speaker 7**: Seeing one engineer migrating an old codebase with our agent. And it really needed the agent to click through the stuff because if other products, it just created the product, but it didn't work. It wasn't interactive. It was just a dummy result. So an agent that really clicked on the stuff allowed to check that it's actually working and not just looking good in code. I think this is one cool thing that was also allowed by the progress in computer use and the persistent environments of virtual machines for agents, which also wasn't there before, or wasn't that great. But now it's really great. So it's allowing the agent to go into the arena.

</details>

**Speaker 7**: 哎呀，这只是我们用户的一个真实任务示例。我喜欢了解用户正在构建什么并获取反馈。这就是它在你的仪表板上的样子。这就是我如何可视化这些任务。有趣的是，它只是一个包含更小循环的循环，因为每个代理都在运行，它们也处于循环中。但总的来说，它就像一个大的循环组。也许这听起来有点奇怪，但事实就是如此，全是循环，一个套一个。嗯，好的。最后一部分是持续改进和持续学习。嗯，关于代理，房间里的大象是上下文问题，很多问题都与此相关。在软件工厂中处理这些长时间任务时，你如何应对上下文爆炸？你如何保持上下文清晰？这非常重要，因为企业，尤其是他们使用数百种工具，他们使用Figma、Jira、Gmail、Drive等等，平均有数百种工具。所以所有这些工具在代码中都有规范，所有这些都有模式、参数和描述。所以代理很容易被这些工具淹没，导致上下文膨胀。如果有两个听起来相似的工具，代理实际上可能会丢失上下文，因为它们会填满上下文窗口并需要压缩。所以这真的很危险。

<details>
<summary>Original English</summary>

**Speaker 7**: This is just one example of a real mission from our users. I like to just learn what users are building and get feedback. And this is just how it can look on your dashboard. And this is how I visualized the missions. What is interesting is that it's just a loop with smaller loops because every one of the agents is running, they get in loops as well. But overall, it's like one big loop group. Maybe this sounds weird, but it's like that, it's all loops inside loops. Um, okay. And the last part is always improving, always learning. Um, there is this elephant in the room: context with agents. A lot of questions are about it, like: how do you navigate the context blow-up because you work on these long missions in the software factory? And how do you actually keep the context clean? And that's very important because enterprises, especially, they use hundreds of tools, they use Figma, Jira, Gmail, Drive, like hundreds of tools on average. So all these have specifications in the code, all these have schemas and parameters and descriptions. So it can cause agents to really bloat with that and bloat the context. If there are two tools that sound similar, the agent can actually lose context because they fill up the context window and need to compress. So this is really dangerous.

</details>

**Speaker 7**: 所以为此，我们在软件工厂中有一个叫做“延迟上下文引擎”的东西，我们构建了这样的适配器。我们只是逐步披露上下文中有什么以及使用哪些工具。所以我们基本上有一些隐藏的工具，只有在实际需要时才会在后面提供帮助。

<details>
<summary>Original English</summary>

**Speaker 7**: So for this, we have something within the software factory called a deferred context engine, and we built such adapters. We just progressively disclose what's in the context and what tools to use. So we basically have some hidden tools that are only revealed later if they are actually needed.

</details>

<!-- chunk 16/54 -->

### 工具懒加载与代码库准备度

**Speaker 7**: 所以它首先只列出工具的简短列表和简短描述，当代码中实际需要时，才会调用该工具并完全加载它。

<details>
<summary>Original English</summary>

**Speaker 7**: so it first just has short list of the tools and uh only short descriptions and when it needed actually in the code and can call the tool and fully load it.

</details>

**Speaker 7**: 所以重要的一点是，没有任何东西被真正移除。

<details>
<summary>Original English</summary>

**Speaker 7**: so important thing is, nothing is actually removed.

</details>

**Speaker 7**: 它只是被隐藏起来，直到需要时才可访问。

<details>
<summary>Original English</summary>

**Speaker 7**: it's just hidden and not reachable until needed.

</details>

**Speaker 7**: 所以这是为了以后考虑，重要的是，它实际上节省了大量令牌。当你使用越来越多的工具，做越来越多的事情时，实际上节省的效果会真正地、真正地扩展，你可以节省百分之五十或更多的令牌。

<details>
<summary>Original English</summary>

**Speaker 7**: so it's just for later and important thing, is it actually saves a lot of tokens um at scale once you use more and more tools do more, actually you save it really, really scales, and you can save fifty percent of tokens or more.

</details>

**Speaker 7**: 好的。嗯，另一件棘手的事情，并且第一次让我感到惊讶的是，采用人工智能，你要么大获成功，要么同样可能大败而归。这有点像幂律分布。

<details>
<summary>Original English</summary>

**Speaker 7**: okay. um another thing which is tricky and was surprising for me for the first time. is that one adopting AI, you either succeed big or you can fail big the same way. it's a bit of power law.

</details>

**Speaker 7**: 所以，如果你的代码库没有准备好，如果你没有结构化的代码库和重要的事项，那么采用或转向软件工厂实际上可能让你最终变得更糟，并使你的代码退化。

<details>
<summary>Original English</summary>

**Speaker 7**: so if your code base is not ready, if you don't have structured code base and h important things, then adopting or turning into software factory can actually make you end up worse and make your code degraand.

</details>

**Speaker 7**: 在那些采用人工智能的人和那些对此思考得更多一点的人之间，生产力存在巨大且不断增长的差距。还有来自斯坦福的另一项数据，关于有无结构化代码库、是否循序渐进以及文档编写良好，人工智能可能会让你的代码变得更糟。

<details>
<summary>Original English</summary>

**Speaker 7**: uh there is a big and growing up in productivity between the those who aappted AI, where there's those who actually thought about it a bit more. there is another data from stanford about yewithwithout ctured codes base and being gradudy and documenting well, the AI can make your code worse.

</details>

**Speaker 7**: 我认为如果你是工程师，很可能同意有时人工智能真的会把事情搞得一团糟，而且这可能会越来越严重，并且很难回头。

<details>
<summary>Original English</summary>

**Speaker 7**: and i think if you are engineed superprobably can agree that sometimes ai really makes a mess, and this can really compound more and more, and it's difficult to go back.

</details>

**Speaker 7**: 作为软件工厂的一部分，我们有一个叫做“代理就绪度”的东西。它是一个框架。我不喜欢看框架，但把它看作是你代码库的卫生检查以及你应该做的事情，因为你的代码库状况及其所有细节与你采用人工智能的效果和生产力之间，实际上存在很好的相关性，而不是拥有一个庞大的混乱代码库。

<details>
<summary>Original English</summary>

**Speaker 7**: um we have something as a part of the software factory. we have something called agent reitiness. and it's a framework. i don't like to watch framework, but take it as a hygiene check of your code base and things you should do because there is actually a nice cotilabebetween how your code base is looking and all der details there and how good you're going to adopt AI and and a productive instead of how with a mssave code base.

</details>

**Speaker 7**: 所以有一些事情，比如你的开发者环境有多可重现，或者你是否拥有良好的测试，是否所有东西都有文档记录，你的代码或测试的风格是什么？等等。基本上，所有你为了保持代码库整洁而会做的事情。所以这些因素被证明非常有用，我们的大客户实际上会经历这个代理就绪度框架并进行所有检查。然后他们可以跟进建议的行动。那么如何修复呢？

<details>
<summary>Original English</summary>

**Speaker 7**: so there are things like how and a preparticible is your developer environment, or if you have everything good test, if you have all things were documented, what's the style of your code or the test? and inteter uh, everything that you would do also to keep code bsccreen. so do these factors actions show to be very useful, and we have our bigger customers actually go through these agentineous framework and do all checks. and then they can follow up with recommended actions. so how to fix that 可的？

</details>

**Speaker 4**: 好的可的可以的以的以的以的。

<details>
<summary>Original English</summary>

**Speaker 4**: 好的可的可以的以的以的以的。

</details>

### 持续学习与人类角色演变

**Speaker 7**: 嗯，关于软件工厂中的上下文和持续学习，我认为还有一点是，大多数时候在使用人工智能时，或者至少根据我的经验，你会不断向代理重复：“你怎么把事情搞砸了？” 然后你觉得代理并不真正理解你。我认为这又是与人类组织和团队的一个很好的类比。

<details>
<summary>Original English</summary>

**Speaker 7**: um i think one more thing about the context and the continuous learning in the society factory is the most of the time when working with AI, or at least from my experience, is that you keep it repeating to agents with, how do you wonder things down? and you feel like the agent doesn't really get you. and i think this is again nice spattle with human organizations and teams.

</details>

**Speaker 7**: 因为当你加入一家公司时，有很多规则并没有真正被明确记录，你只是通过观察来学习事情是如何完成的。有很多言外之意的东西，你除了观察之外无法从其他地方学到。我认为这对代理来说也是一个巨大的挑战。

<details>
<summary>Original English</summary>

**Speaker 7**: because when you're joining your company, there are a lot of rurules that are not really qualified anywhere like you just learn and upset of how of things are done. and there are a lot of things between the lines that you can't really learn anywhere else than just observing. i think this is big challenge for agents as well.

</details>

**Speaker 7**: 为此我们推出了一件事，就是插件，它们就像是打包的可重用技能和上下文以及幕后的事情，你可以真正地将其规范化或自动化，它会自动更新和记录，嗯，是的，并审查和记录你所拥有的。

<details>
<summary>Original English</summary>

**Speaker 7**: and one thing we launch for that is spluggins, which are like a packaged reusable skills and context and things behind the scenes that you can really qualify or automekay, which is automatically updating and documentaand, uh yeah and reviewing and documenting what you have.

</details>

**Speaker 5**: 对呀对对。

<details>
<summary>Original English</summary>

**Speaker 5**: 对呀对对。

</details>

**Speaker 7**: 所以问题是，如果我们像这样构建软件工厂，我们人类会怎么样？嗯，人类会失业并沦为永久的下层阶级吗？我认为不会。嗯，我想保持乐观。

<details>
<summary>Original English</summary>

**Speaker 7**: so the question is what will happen to us humans? if we build software factory like this, uh will humans just lose jobs and go to perman and underclass. i think they will not. and uh, i want to be positive.

</details>

**Speaker 7**: 所以我想到的是人类向上移动到更酷任务的平行类比。我认为我们之前作为人类有过同样的经历，将一些层次抽象化。我们最初是从作为“人肉计算机”开始的。我们实际上是计算机，做着所有那些繁琐的细节工作。然后我们有了编程语言，将其中的一部分编码、抽象化，然后是编码代理。所以将其中一部分外包出去，但仍然处于循环中，非常密切地监控一切。

<details>
<summary>Original English</summary>

**Speaker 7**: so i'm thinking of this parallel of humans just moving up levels up to the uh to the cooler tasks than before. i think we actually had before the same same experience of us as a humans abstracting some levels up. and we actually started ourselves as human computers. we actually wear the computers doing all the the detadetastustuff at the beginning. then we had programming language is codifying, some of it abstracting and then coding agents. so outsourseeing, some of it uh still being in the luu, very closely um and being monitoring everything.

</details>

**Speaker 7**: 而现在我们正在向上移动到软件工厂，在那里我们管理这些代理。正如我所说，编排代理和工作流，然后变化和调整这些团队结构，即能够良好地、持续地在循环中工作的代理团队。我们只是监控并决定构建什么。

<details>
<summary>Original English</summary>

**Speaker 7**: and now we are moving kind of up to software factories, where we manage these agents. as i said, orchestrraor agents and workings and then variate and nodithese teams structure, teteamof agents that work guduly continuously in the loop. and we just monitor and decide what to built.

</details>

**Speaker 7**: 嗯。所以我想积极地结束这一点，作为人类，我们应该决定在软件中构建什么，而不是如何构建它，因为那是代理的事情。通过这种自主软件的持续循环，我认为我们实际上可以实现这一点。

<details>
<summary>Original English</summary>

**Speaker 7**: uh. so i want rereend this positively, we should be as a humans deciding what's to build in the software, not how to build it because that's a further agents. and by this a continuous cycle of autonomous software, i think we can actually achieve that.

</details>

**Speaker 1**: 没有没有。

<details>
<summary>Original English</summary>

**Speaker 1**: 没有没有。

</details>

**Speaker 7**: 嗯，这是一个警告。或者如果有人觉得这会夺走我们酷的东西。我相信，实际上，它会夺走那些烦人的东西。在企业和组织中，你已经花了很多时间在协调和会议上。正如我提到的，基本上那些言外之意的事情，那些日常需求，你需要从每个人那里获取上下文，分享你的状态，在会议上同步事情。所以所有这些事情实际上都可以外包给你的软件工厂，而你只需要谈论那些酷的东西。

<details>
<summary>Original English</summary>

**Speaker 7**: uh this is one warning chard. or if someone thinks i will take the cool, cool stuff from us. i believe, actually, it will take the annoying stuff and in enterprises and organizations you already spenle out on alignments on the meetings. as i mentioned, basically a thing behind between the lines, the dually needs you need to get context from everyone, share your statules sing on the things on meetings. so all these things could be actual outsource to your software factory, and you could be just talking about the cool stuff.

</details>

**Speaker 7**: 好的。这就是我要说的，非常感谢。去拿些草，让你的代理为你构建吧。谢谢。

<details>
<summary>Original English</summary>

**Speaker 7**: okay. so this is it to thank you so much. go such some grass and let your agents built for you. thank you,

</details>

**Speaker 9**: 我的爱。

<details>
<summary>Original English</summary>

**Speaker 9**: 我的爱。

</details>

### 浏览器代理的优化与演示

**Speaker 2**: 好的，大家好，我是Gushan。嗯，我工作……我曾是两年的创始工程师。现在我是总裁，对吧？浏览器代理作为一个想法很酷，但总裁应该更务实。我可能宣布采用，但我自己并没有探索它。我已经利用它一段时间了。这有一个非常有趣的浏览器代理基准测试，因为有些事情你必须顺序执行你的任务。

<details>
<summary>Original English</summary>

**Speaker 2**: okay, everyone, i am gushan. uh, i work. that's i was a funding engineer for two years. that's i'm pleasdent, right? and that is brosiagents brosilaents as an idea so cool, but but posient should go czy day. i possibly amouncing that adoption and myself self don't don't explorating that. i have exploiting that for some time. and this have the that adopbut. but this this is very impresting benchmark for gasiate agents because there are only things that you have to do sequencing of your dusks.

</details>

**Speaker 2**: 这实际上揭示了为什么浏览器代理很糟糕。你在视频开头看到了，浏览器代理花了像……我们花了十秒多钟只是点击开始按钮。现在我们才在第一步。总共有三十步，它花了那么长时间只是点击一个按钮。

<details>
<summary>Original English</summary>

**Speaker 2**: and this actually reviews, you know why browther isn't suck. you saw the beginning of the video um brobrowser. this agent took like me. we tend to any seconds just to click the start button. and now we're on step one. there are thirty steps, and it are seconken so long just to click one button.

</details>

**Speaker 2**: 嗯，所以够了，我想向你展示我一直在构建的东西，同样的设置。

<details>
<summary>Original English</summary>

**Speaker 2**: um so enough of this, i want to show you what i am been building it so same upset 这的。

</details>

**Speaker 2**: 嗯，我喜欢那种能看到正在发生什么的感觉。你知道，你可以看到代理在思考，正如你所见，它快得多，快得多。而且我为此使用了一个便宜得多的模型，对吧？这里的高性能模型相当聪明，但问题在于它们周围的基础设施。

<details>
<summary>Original English</summary>

**Speaker 2**: um i'd like as sort of appplicate the feeling of seeing what's happening. you know, you can see when the problem agent is thinking, and as you can see, it is so much fast and so much quicker. and i'm using a much jeaper model, right? the high posis here here, momols ls pretty smart, but it's the infa around them that sucks.

</details>

**Speaker 2**: 如果你注意到之前的视频，也许是一个屏幕截图，代理在计划下一步要做什么。如果你点击某个东西，它不明白发生了什么。所以我这里的核心方法是给代理一个良好的环境，让它知道它在哪里，这样它就可以计划长序列。它可以找出它在哪里失败了，发生了什么。并且它可以计划点击操作。

<details>
<summary>Original English</summary>

**Speaker 2**: if you notice in the video earlier, maybe be a screen shot, the agent is plan of deeper was going on. if you clicicsomething something, it doesn't undersend was going on. so my courth thesa here has been give a nice environment for the agent to you was so where it can plan long sequences. it can figure out where it failed, what is going on. and i can plan the clicicket.

</details>

**Speaker 2**: 我发现了一个很酷的表示方法，它压缩了网站，让代理可以看到……看到DOM。

<details>
<summary>Original English</summary>

**Speaker 2**: i figured out is a cool representation, which complesive the website, and let's the agent and see see, see the diabege.

</details>

**Speaker 2**: 而且使用的令牌非常非常少。现在我想展示一些实际的例子。比如说，下载这个……这个点。所以这是Clord。他们做了这个。所以对于普通人来说，这很简单，它截取了一个干净的截图。你看到按钮，它点击了。但有趣的是，它在这之后卡住了。

<details>
<summary>Original English</summary>

**Speaker 2**: and very few few dokenes now want to show some actual uh, examples, let's say, on download this this point. so this is clord. they underdo it. so the is you this is is assimple for the popoation, and it ook is clean shot. you see the button by the clicicum. but then what's interesting is that it got stuck after this point.

</details>

**Speaker 2**: 所以从第46秒到视频结束，它花了……截取一个干净的截图。它卡住了，因为某些原因，做CleanShot。基本上整个过程花了两分钟，而在我的例子中，在我们的视频里，我只是启动，然后“砰”一声就完成了。这就是浏览器代理的美妙之处。它有多快。而且我为此使用了如此便宜的模型。

<details>
<summary>Original English</summary>

**Speaker 2**: so from forty six, second unto the end of this video, it took is clean shoort. it's glored for somesomeboy's and dookeas clean shot basicthis entire process took two minutes, where eas in my case in our video. so i just boots and boom done. and that's the beauty of a browseration. and just how ququick was that. and i'm using such a cheap model for this.

</details>

**Speaker 2**: 另一个有趣的例子是，我和我的朋友周日要去背包旅行。我在想，你知道吗，因为这个网站是加拿大的，我对加拿大的网站不太熟悉，所以我花了一些时间来搞清楚这个网站。所以我让它……帮我预订这个，但创新之处在于，它无法选择日期，然后就卡住了。但这是我的代理的视频。

<details>
<summary>Original English</summary>

**Speaker 2**: another another interesting example is, so my friend and i am bring packing on on on sunday. i was wondering, you know what, because this this site is in canada, and i am not refluent in candida like it took me sometime to figure out this website. so i has to lot like like, take a new book this for me and by the innovation, it's unable to pick er date, and it's just stuck. but this is the video of my agent.

</details>

**Speaker 1**: 它说“选择日期”，然后选择日期，“砰”一声完成，对吧？就这么简单，理论上使用起来很不方便。

<details>
<summary>Original English</summary>

**Speaker 1**: ledisees select said, and what's in the date and boom done, right? it's so simple, inconvenient to use in theory.

</details>

**Speaker 1**: 那么下一步是什么，对吧？我计划在这个项目中开源什么？因为，再说一次，我的代码不是超级可防御的，我想提供的产品是，也许是一个API，正如你所见，我们正在运行这些命令。也许我只想把这个命令暴露为一个API。给我……你给我你的意图，我来为你执行，然后交还给你。或者也许把它作为一个网站开放，或者把它作为一个插件暴露在浏览器中。

<details>
<summary>Original English</summary>

**Speaker 1**: so what's next right? what am i planning on doing indian open source in this project? because, again, my this code is not super defensible that the product that i want to give is again, maybe an api that, as you can see, we were running these commands. maybe i just want to expose this command as an api. give me me, you are a give me your intent, and i will execute for you, yar back to you. and or maybe open this as a website or exposed this as a plug in in berya.

</details>

**Speaker 1**: 所以底线是，我想让浏览器代理更快、更便宜、更可靠，并且以这种方式衡量。世界上每个人都在做它们，因为它们可以为你做这么多事情。所以，这就是这里的大致想法。谢谢观看。这个对话用Markdown呈现了那个特定页面的网站。

<details>
<summary>Original English</summary>

**Speaker 1**: so bottom line is, i want to make browser agents faster, cheeer and more reliable and dismeasure. everybody in the world is doing them because they can just do so much for you. so it. that's the broad idea here. thank you for wating. this in dial markdown presents the website that particular page.

</details>

<!-- chunk 17/54 -->

### 通过截图压缩实现高效反馈

**Speaker 1**: 我们来做一个有趣的对比。我们打开完整的 DOM，这大概有两万个 token。但如果我们用截图，这张截图大约七百个 token。我的模型有八百个 token 的上下文窗口。在一种情况下，它只能看到某一个片段；而在另一种情况下，它能看到整个网站，对吧？有几个重要的反馈点。我们可以说，好的，这些是页面上新出现的内容，而这些现在已经消失了，对吧？同样，我们可以说，之前挡住她想要点击的那个东西现在已经被移除了。现在我们给出反馈说，你希望点击这里，但这是可以做到的，因为我们在浏览器中持续跟踪状态变化。所以，综合所有这些，我得到的是一个非常清晰的、对网站进行压缩后的表示。你可以把这个和截图一起给模型，这样 token 的消耗非常节省。这样，模型对任务的理解会非常好，然后它就能构建出要执行的长序列任务。

<details>
<summary>Original English</summary>

**Speaker 1**: and let's actually do this interesting comparison by let's go to the yes, too. The full DOM, this would be around twenty thousand tokens. But so let's say we have this screenshot, this screenshot about about seven hundred tokens. My model has got eight hundred token context. He said in one case it could see only one particular snippet. In the other case, you can see the entire website, right? A couple of the things that it's important to give feedback, right? So we say that ok here, these are the new things that popped up on the page. This is now gone, right? And similarly, we can say that, you know, this thing that was blocking a thing that she want to click has now been removed. Now we give a feedback that you'd like to click this, but that can happen because, you know, we keep tracking state changes in the browser. So all of this together, what I get is a very clean representation that basically compresses the website. And you can give this along with the screenshots, pretty cheap token-wise. So the model understands really well, and then it can construct this long sequence of tasks to execute.

</details>

### 智能体工程中的双循环

**Speaker 4**: 大家好，欢迎来到我们的演讲——智能体工程。我是 Bining，MultiAgent 的联合创始人。今天和我一起的是我的同事。

<details>
<summary>Original English</summary>

**Speaker 4**: and oh hi, everybody, welcome to our talk. The Agentic Engineer, I'm Bining, co-founder of MultiAgent. And I'm here with my colleague.

</details>

**Speaker 5**: 嗨，我是 Burack，MultiAgent 的 CTO。今天我们要讨论的是循环（loops）以及智能体工程是如何运作的。

<details>
<summary>Original English</summary>

**Speaker 5**: hi, I'm Burack. I'm the CTO of MultiAgent. And today, we're basically gonna talk about loops and how the agentic engineer works.

</details>

**Speaker 4**: 正如大家现在所知，循环是构建软件的热门话题，尤其是在智能体循环中。我们将同样的循环应用于构建 AI 智能体。大家也知道，这里有两个概念。一个是离线循环，在构建过程中，你迭代你的智能体，进行测试和评估，改进它，然后继续。第二个是我们称之为在线循环，一旦你的智能体部署到生产环境，你监控它的轨迹，进行诊断，然后将结果反馈到优化循环中，以便迭代并拥有多个版本的智能体。

<details>
<summary>Original English</summary>

**Speaker 4**: So as you all aware of now, loops is the hot topic how you build software in an agentic loop. And we apply the same loop to the building of AI agents. And as you all aware, there's two concepts here. One is the offline loop, where while you build, you iterate on your agent, you test it, evaluate it, you improve it, and you go on. And then you have a second loop, which we call the online loop, where once your agent is deployed to production, you monitor its traces, you diagnose, and then you feed it back into your optimization loop, yeah, to iterate and have multiple versions of your agents.

</details>

### 手动循环的瓶颈

**Speaker 4**: 到目前为止，我们做这些循环都是手动的。这非常慢。生命周期基本上是：你有一个问题，你想对你的智能体做一些改动，你实施改动（如果你使用编码智能体，可能会更快地实施改动），你为这个新功能或问题生成一些样本来测试，然后你查看结果，查看轨迹，看看结果如何。然后你可能会发布，做 A/B 测试。所有这些反馈都是手动的，耗时非常长。最终，瓶颈变成了人工审查和人工构建时间。这是无法扩展的，尤其是当你的组织计划部署数百个智能体时。这很痛苦。这就是为什么我们认为智能体工程师是构建智能体的自然下一步。接下来让 Burack 详细介绍一下我们如何通过智能体工程师来改进时间线和生产可靠性。

<details>
<summary>Original English</summary>

**Speaker 4**: Up until now, what we did was doing this loop manually. It's quite slow. The lifecycle is basically you have an issue, you wanna change something to your agent, you implement the change (you may be faster to implement the change if you use coding agents for it), you generate some samples for this new feature or issue to test it, then you look at the result, you look through traces, how does the outcome look like? Then you may ship it, you do A/B testing. And all your feedback is kind of manually, takes very long. And the bottleneck basically becomes the human manual view and the human building time. And that you can't scale, especially if in your organization, you are now planning to roll out hundreds of agents. It's painful. And yeah, this is why we think the agentic engineer is the natural next step to build agents. And I have Burack to dive into how we improve timing and the route to production reliability with the agentic engineer.

</details>

**Speaker 5**: 关键点是，一旦你达到一定数量的智能体或基于 AI 的功能，人类手动执行这个循环就无法真正扩展，时间也不够。所以，以智能体方式执行这个循环是提高吞吐量的关键，因为你可以在相同时间内完成更多循环。这个循环的运作方式有几个阶段。当你从零开始时，就像当前的软件开发实践一样，你首先要为你的智能体或技能创建规格说明。在这里，你需要定义所有的职责、功能、智能体需要处理的决策以及在不确定条件下的行为。同样，这只是定义阶段。一旦你定义了你的智能体需求……

<details>
<summary>Original English</summary>

**Speaker 5**: The key thing here is basically once you reach a certain number of agents or AI based features, humans performing the loop again cannot really scale in enough time. So this is why doing this agentically is the key to increasing the throughput because you can fit many more cycles into the same amount of time. And now how that loop works is basically we have a few stages. So this is when you are starting from scratch like the current software development practices, you first create a spec for your agent or your skill in this case. And here you need to define all the responsibilities, all the functions that the agent needs to handle, the decisions that it has to make under uncertain conditions. And here again, this is only the definition stage once you defined your agent's requirements.

</details>

### 成为组织中最快的构建者

**Speaker 7**: 我上周末参加了一个婚礼，在纽约，那里有大概两百人。我和一个我从未见过的人聊天，我告诉他我在准备这个演讲。他说，哦，酷，这个会议是关于什么的？我说是关于 AI 工程的，然后我就能看到他的眼神变得空洞。他开始往我身后看，想找下一个人聊天。所以，能来到一个满屋子都真正想听这些东西的房间，真是太酷了。我很高兴来到这里。我是 Conductor 的联合创始人。有人用过 Conductor 吗？好的，不错。Conductor 是一个桌面应用，用于同时管理一组编码智能体。所以，你不需要为你的 Claude Code、Codex 或其他编码智能体打开一堆终端窗口，而是有一个统一的界面来管理它们。构建 Conductor 的一个很酷的地方是，我近距离观察了很多最优秀的构建者。我看了他们的工作流程，看了他们如何工作，看了他们做的事情以及他们避免做的事情。所以我想把那些我看到的最优秀的工程师使用的原则整理出来，分享给大家。这就是 Conductor 的样子。大家能看到吗？好的。这是我的原则——成为你组织中速度最快的构建者。

<details>
<summary>Original English</summary>

**Speaker 7**: I was at a wedding this weekend, and it was in New York, and there were about two hundred people there. And I was talking to someone who I never met before, and I told him about prepping for this presentation. And he said, oh that's cool, like what's the conference about? And I said it was about AI engineering, and I could just see his eyes glaze over. And he started looking behind me to find the next person to talk to. And so it's so cool to actually be in a room full of people who actually want to hear about this stuff. So I'm very glad to be here. I am the co-founder of Conductor. Has everyone here used Conductor? Okay, nice. Conductor is a desktop app for managing a team of coding agents all at the same time. So instead of having a bunch of terminal windows for your Claude Code, your Codex, or whatever coding agent, you have one interface to manage them all. And one of the really cool things about building Conductor has been that I've seen a lot of the best builders up close. I've watched their workflow, I've seen how they work. I've seen the things they do and the things that they avoid doing. And so I thought I would compile a bunch of the principles that I've seen the best engineers use and give them to you all. So here's what Conductor looks like. Can you guys see this? Okay? Nice. So here's what Conductor looks like. And here are my principles for being the fastest builder in your organization.

</details>

### 原则一：靠近前沿

**Speaker 7**: 让我们从第一条开始：靠近前沿。靠近前沿意味着你总是在最新东西发布的那天就去尝试。这意味着当 UltraCode 发布时，你去尝试它；当 Sash Goal 发布时，你给它 API。靠近前沿非常重要，有几个原因。如果你在经营自己的初创公司，那么靠近前沿意味着你会产生很多关于你应该构建什么的新想法。这确实发生在我们身上。我们当时在构建一个完全不同的应用，叫 Cororus。但我们在去年二月就开始重度使用 Claude Code，以至于我们整个工作流程都围绕它构建。我们开始把仓库克隆五次。然后我们发现了工作树（worktrees）。然后一点一点地，我们就把 Conductor 构建成了一个内部工具，我们自己都没想到。这就是靠近前沿的结果。如果你不在做初创公司，你也应该成为公司里那个总是知道最新工作流程的人。过去，你可以依靠你的社交网络，关于最佳工作流程的重要信息会慢慢传到你这里。但如果你只是等待信息传到你这里，你总是会落后三到六个月。所以靠近前沿非常重要。这里有一个关键词是“靠近”。如果你处于最前沿，是有危险的。你可能会做我称之为“中间件”的事情，也就是你把所有时间都花在优化工作流程上，而不是做实际工作。所以，我们在内部想出了一个启发式方法，我们称之为：不要试图战胜市场。当你试图判断自己是靠近前沿还是处于前沿，是否过度深入最新趋势时，你应该问自己：为什么这个工作流程不是默认的？举个例子，当粗糙循环（rough loops）开始流行时，你应该问自己：我是否应该花大量时间用粗糙循环来优化我的工作流程？因为如果粗糙循环对每个人都有效，如果它们是默认的，那么你可能应该等待 Anthropic 或 OpenAI 把这个工作流程构建到默认框架中。你可以把这看作是类似有效市场假说，除非你拥有真正的阿尔法（alpha）。我所说的真正阿尔法，是指一些关于你的用户或代码库的、模型可能不知道的信息。举个例子，我们 Conductor 是一个聊天应用，我们必须非常快速地渲染非常长的聊天记录，性能对我们来说很重要。所以我们花了很多时间来优化我们的渲染工作流程，以便快速渲染聊天记录，并且我们愿意在代码的其他部分做出牺牲来实现这一点。所以，如果你拥有某种阿尔法，也就是关于你正在构建的应用的、模型可能不知道的信息，那么你应该花时间优化工作流程。否则，不要。不要成为那个拥有惊人 IMAX 设备但实际上不产出成果的人。

<details>
<summary>Original English</summary>

**Speaker 7**: So let's start with number one, stay near the frontier. Staying near the frontier means you're always trying the latest things basically the day they come out. It means that when UltraCode comes out, you're trying it. It means that when Sash Goal comes out, you're giving it API. It's really important to stay near the frontier for a few reasons. If you are doing your own startup, then staying near the frontier means that you come up with lots of new ideas for what you should actually be building. And this literally happened to us. We were building a totally different app called Cororus. But we started using, we were such power users of Claude Code back in February of last year that we started building our whole workflow around Claude Code. And we started cloning our repo five times. And then we discovered worktrees. And then bit by bit, we had built Conductor as an internal tool, and we couldn't figure it out. We couldn't deny, you know, staying at the frontier. And if you're not doing a startup, you should be the person at your company who always knows what the latest and latest workflows are. It used to be that you could just kind of use your social graph and the information that was important about the best workflows to use would trickle down to you. The things just move to you, but you're always going to be three to six months behind if you do that. So it's very important to stay near the frontier. And there's an important word here: near. There is a danger if you are at the frontier. You can do what I call "midwit," meaning where you're spending all of your time working on your workflow and not doing actual work. And so internally, we've come up with a heuristic for this. And we call it: don't beat the market. Don't try and beat the market. The heuristic you should use when you're trying to decide if you're near the frontier or at the frontier and deep into the latest trends is you should ask yourself: why isn't this workflow the default? So for example, rough loops were becoming a big thing. You should ask yourself, should I spend a ton of time optimizing my workflow with rough loops? Because if rough loops work for everyone, like if they are the default, then you probably should just wait for Anthropic or OpenAI to build the workflow into the default harness. You can think of this as sort of like the inefficient market hypothesis where unless you have real alpha, you shouldn't be optimizing your workflow too much. And what I mean by real alpha is some kind of information about either your users or your code base that the models might not know. So for example, for us, we have a chat app. We have to render really long chats really quickly. And performance is important to us. And so we need to spend a lot of time optimizing our rendering workflows to render the chats quickly, and we're willing to make sacrifices in other parts of our codebase to make it happen. So if you have some kind of alpha, some kind of information about the app you're building that the models might not know about, then you should put time into the workflow. Otherwise, don't. Don't be the person who has an amazing IMAX setup but doesn't actually get stuff done.

</details>

### 原则三：创建无垃圾区

**Speaker 7**: 好的，第三条：创建无垃圾区。在 Conductor……

<details>
<summary>Original English</summary>

**Speaker 7**: Okay, three, create slop free zones. So at Conductor...

</details>

<!-- chunk 18/54 -->

### 无垃圾区与代码库的精细管理

**Speaker 7**: 我们有一个术语，叫做“无垃圾区”。无垃圾区是代码库的一部分，是应用中需要非常严格的人工审核的部分。实际上，我觉得这有点不寻常。很多人以为我们是纯粹的“Token最大化者”，会疯狂地生成三万行代码，但事实并非如此。我对代码库的某些部分非常谨慎，而对其他部分则非常宽松。这一点之所以重要，是因为如果你不注意你的无垃圾区，你的代码可能会陷入非常棘手的境地。这确实发生在我们身上。我们不得不重写了整个许可证好几次，因为我们之前对无垃圾区不够小心。这不是开玩笑。我们有一个迁移文件，在我们的CI中，任何对迁移文件的更改都需要人工审核。我们还假设所有用Sack写的代码都是无垃圾的。不是Ruby，而是由AI或人类编写的Turby。我们所有的文档，我们的云MD，我们所有的技能文件，我们都投入了大量时间让它们变得优秀。这也是我从所有最优秀的构建者身上看到的，他们都在云MD或技能文件上投入了异常多的时间。我想，另一种思考方式是，如果你有一个新实习生加入你的公司，你有机会每天在他们耳边低语一句话，每次他们坐下来工作的时候你都能在他们耳边低语，你可能会花很多心思去想你要在他们耳边低语什么。这就是云MD或代理的作用。MD就像是每次代理开始工作时加载到它们上下文中的信息。所以你可能需要花很多心思在这些东西上。

<details>
<summary>Original English</summary>

**Speaker 7**: We have this term. We call a slop free zones and a slop free zone is part of the codebase, a part of the app that requires really strict human review and actually, I think a little bit unusual. And this way, I think a lot of people assume that we are pure token maxers, and we are like ripping through like thirty thousand lines of code, but actually not. I'm actually quite careful with certain parts of our codebase and then very loose with other parts of our codebase. The reason this is important is because if you are not careful about your slop free zones, your code can get in a really tricky spot and this actually happened to us. Yeah, we've had to rewrite our whole license a couple of times because we weren't careful about slop free zones. It's not a joke. We have a migrations file and in our CI, any change to the migrations file requires a human to review it. We also assume that anything written in Sack is slop free. It's not Ruby, it's Turby by human. All of our docs, our cloud MDs, like all our skill files, we put a ton of time into making them good. And this is also the thing I've seen with all the best builders up close, like they put an unusual amount of time into the cloud MD or their skill files. And I think another way that I thought about this is like, if you had a new intern who was joining your company, and you had the opportunity to like whisper something in their ear every time they started working, like every day, anytime they sat down, you could like whisper something in their ear, you would probably put a lot of thought into like what it is that you're whispering in their ear. And this is what cloud MD or agents are. MD is like information that gets loaded into agents' context every time they start working. And so you probably want to put a lot of thought into those.

</details>

### 喂养巨兽：中央信息数据库

**Speaker 7**: 第四点，喂养巨兽。我们有一个内部工具，叫做“指挥家”内部代理，也被称为CIA。CIA基本上是一个中央数据库，记录组织中发生的一切。所以每当有新的Slack消息，CIA就会捕获它。CIA代理会看到Slack中发送了一条新消息，它会捕获它并保存到PostgreSQL数据库中。每当用户在Discord中提出错误请求，同样的事情也会发生。每当我们开会，我们都会录音，然后存入CIA。我们称之为“喂养巨兽”，因为如果你想让你的代理在公司里有效，你希望它们拥有尽可能多的信息和上下文，了解你们具体的工作方式。最好的方法就是将所有信息集中在一个地方。我认为这条推文总结得很好：把所有东西都放进数据库，然后给你的代理一个SQL工具，让它处理剩下的事情，这真的很有效。

<details>
<summary>Original English</summary>

**Speaker 7**: Okay, four, feed the beast. We have an internal tool we call the conductor internal agent, and it's also known as the CIA. And the CIA is basically the centralized database of everything that's happening in the organization. So anytime a new Slack message gets sent, the CIA picks it up. The CIA agent will see that a new message was sent in Slack, it will pick it up and will save it to a PostgreSQL database. Anytime a user has a bug report in Discord, the same thing happens. Anytime we have a meeting, we are recording it, and it goes into the CIA. We call this feed the beast because you want for your agency to be effective in your company, you want them to have as much information, as much context as they can have about the way you guys specifically work. And the best way to do that is by having a centralized place for all the information. I think this tweet sums it up pretty well. It's really effective to just put everything in a database and then give your agent a SQL tool and let it handle the rest.

</details>

### 自由放养代理与云端协作

**Speaker 7**: 接下来是自由放养代理。给你的代理很大的发挥空间，给它们一个沙盒，在那里它们不会被“杀死”，可以探索你的代码库，处理真正困难的任务。它们知道当你合上笔记本电脑时它们不会被关闭。给它们机会去创造更多自己的同类。给它们与代理和其他人类协作的方式。自由放养代理这个概念之所以重要，是因为模型正在变得更好，它们能够运行更长时间，而且数量会更多。所以如果它们被限制在你的笔记本电脑里，它们的效率远不如自由漫游时高。另一件重要的事情是，一旦你给了它们一个不局限于你笔记本电脑的沙盒，你就可以在上面构建很多很酷的东西。我们在指挥家中也构建了类似的东西。我快速给你展示一些很酷的东西。这是指挥家，我把它放大一点。这实际上是本周即将发布的新版本指挥家，它围绕着云端协作展开。我之前说过，你需要为代理提供一个沙盒，你需要自由放养代理。你会注意到每个工作区顶部都有一个小云图标，我可以点击它，获取代理运行所在的沙盒信息。最棒的是，我可以合上笔记本电脑，代理会继续运行，直到基本上本周结束。以前，指挥家中的每个任务都是基于Git工作树构建的，但现在它们都在云端沙盒中。它们是自由放养代理。但同样很酷的是，你可以在云端之上构建协作功能。你看这里，我再放大一点。那是我。这里列出了我正在处理的事情。你可以看到我在指挥家组织中，但如果我向下滚动，我可以看到Kadin正在做什么，Louis正在做什么，Tawfiq正在做什么。我可以看到Jackon的脸出现在那里。我可以点击进去，实时看到他在做什么。我认为协作是这些工具中最重要的新概念之一，但目前几乎没有人谈论它。协作之所以重要，不仅是因为所有伟大的事物都是由团队而非个人构建的，还因为随着模型变得更好，就像我们在过去两天看到的那样，你对自己正在构建的东西会更有雄心。而如果你变得更有雄心，你将需要更多的人和更多的代理来处理这些事情。就像我们在工作区中看到的，Kadin正在处理这个任务。我可以说，我可以审查他做的更改。我把它缩小一点，看起来没问题。但我想说，我们能不能用制表符而不是空格？Kadin应该能实时看到这条消息，他也可以在工作区中聊天。你看，他正在打字。我看到Kadin正在打字。看看他说什么，他好像打了很长一段。好吧，也许他停下来了。我给他一点时间看看。但关键是，我们现在可以拥有与团队成员实时共享的协作空间。好了，他又在打字了。好吧，我待会再回来看。代理们已经逃走了。我对此感到非常兴奋，我们本周将向所有指挥家用户推出这个功能。我认为协作将成为今年最重要的界面变化之一。云端另一个很酷的地方是，给予代理自由放养的沙盒，我们可以给代理API让它们自己启动。我这里有一个我的OpenCloak，叫做Lord Canbox。你可以看到它有权访问指挥家API。所以从我的手机、Telegram、Slack或任何地方，我都可以说，嗨，你能为我创建一个新的工作区，让所有按钮都变成蓝色吗？我向Lord Cranden发送这条消息，Lord Cranden有权访问指挥家API，所以它可以自己启动工作。我们看看它会做什么。好的，它刚刚创建了工作区。代理已经在上面了。然后我可以进入我的指挥家，虽然我正要离开，但它仍在设置工作区，它会在我离开时为我工作。所以我对在自由放养代理之上可以构建的所有酷东西感到非常兴奋。

<details>
<summary>Original English</summary>

**Speaker 7**: Okay, next is free range agents. Give your agents a lot of space to play, give them a sandbox where they won't get killed, where they can explore your code base, where they can work on really hard tests, where they know that they're not going to get shut down when you close your laptop. Give them opportunities to create more of themselves. Give them ways to collaborate with agents and other humans. What's interesting with free range agents and this concept and why it's important is the models are getting better and they are able to run for much longer and they're going to be many more of them. And so if they are confined to your laptop, then they cannot be nearly as effective as if they are free roaming. The other thing that's important here, once you give them a sandbox to play that isn't confined to your laptop, there's a bunch of really cool stuff that you can build on top, and we have built similar things in Conductor. I'll give you a quick glimpse into some of those cool things. So this is Conductor, I'll make it a bit bigger. And this is actually a new version of Conductor that is coming out this week, and it is centered around collaboration in the cloud. And so the thing I said was, you need to create a sandbox for agents to play, you need a free range agent. And so you'll notice that each workspace has a little cloud icon at the top, and I can click it and get information about the sandbox the agent is running in. And what's awesome about this is I can close my laptop, and the agents are going to keep running up until basically this week. Every task in Conductor was built on a Git work tree, but now they're in a cloud sandbox. They are free range agents. But what's also really cool that you can have built on top of cloud is collaboration. So you'll see here, I'll make this even bigger. That's me. And here are a list of the things that I am working on. And you can see that I am in the Conductor org, but if I scroll down, I can see what Kadin is working on. I can see what Louis is working on. I can see what Tawfiq is working on. And I can see Jackson's face pop up there. I can click in and see what he's working on in real time. And I think collaboration is one of the most important new concepts in these tools that no one is really talking about right now. Collaboration is important because not only are all the great things built with teams of people, they're not built by individuals, so they're built by teams, but also as models get better, as we've seen this with the past two days, you have a lot more ambition with the kinds of things you're building. And if you're getting more ambitious, you're going to need more people and more agents to work on those things. As we've seen in a workspace like Kadin is working on this one, and I'm going to say I can review the changes that he's made. I'll make it a little smaller, and this looks fine. But I'm just going to say, can we actually use tabs, not spaces? And Kadin should be able to see that message happened in real time, and he can actually chat in the workspace as well. So he can see here that he's typing. So I see Kadin is typing. Let's see what he says, seems like he's typing a lot. Okay, maybe he stopped. I'll give him a second to take a look at it. But the point is, we can now have collaborative spaces that are shared in real time with people on our team. Okay, he's typing again. Okay, come back, the agents have escaped alright. So I'm really excited about this, and we're rolling this out to all Conductor users this week. I think collaboration is going to be one of the most important new interface changes this year. The other really cool thing about cloud is that by giving the agents the free range sandbox, we can give the agents API to spawn themselves. So I have here, I'll bring up my OpenCloak. So this is my OpenCloak called Lord Canbox. And you can see that it has access to a Conductor API. So from my phone or from Telegram or really from Slack or wherever, I can say, hi, can you create a new workspace for me that makes all the buttons blue? And so I'll text that to Lord Cranden, and Lord Cranden has access to the Conductor API, and so can kick off work itself. So let's see what it does here. Okay, so it just created the workspace. The agent is on it. And then I can go into my Conductor, I'm about to leave, but it's still setting up the workspace, and it will do work for me while I am gone. So I'm pretty excited about all the cool things you can build on top of free range agents.

</details>

### 乐团，而非工厂

**Speaker 7**: 好的，今天我要讲的最后一个原则，也是这次演讲的标题，就是“乐团，而非工厂”。今天整个演讲的主题都是关于软件工厂的。老实说，我有点讨厌这个词。我认为这是思考这些新兴工具的错误方式。当我想到工厂时，我想到的是自动化，自动化有很多了不起的地方，它让我们的生活更高效，我们可以创造更多的东西。但我希望未来不是被建造成工厂。我希望未来感觉像人。我希望进入心流状态。我希望像站在乐团面前一样挥舞我的指挥棒。我往这边一挥，这支由代理和人类组成的团队就开始工作。当我需要时，我可以深入细节，但大多数时候我只看全局。我不认为未来应该是我们像管理代理集群的工厂流水线经理一样按按钮，让代理们像流水线一样产出下一个功能。我们十年前就用“功能工厂”这个词尝试过了，但根本行不通。我希望我的软件感觉人性化、有匠心。我希望感觉人类是这一切的中心。

<details>
<summary>Original English</summary>

**Speaker 7**: Okay, the final principle that I want to talk about today and the title of this talk is orchestras, not factories. The whole talk track today is about software factories, and I honestly kind of hate the term. I think it's the wrong way of thinking about these new tools that are emerging. I think when I think of a factory, I think of automation, and there's a lot of amazing things about automation, and look, it makes our lives more efficient, and we can create more of everything. But I don't want the future to be built as factories. I want the future to feel human. I want to be in the flow. I want to be like in front of an orchestra like waving my baton, but I wave it this way, and this team of agents starts working, and this intermingling of humans and agents starts working. As I go here, and when I want to, I consume it on the details, but most of the time I consume the overview. And I don't think the future should be we are like managing swarms of agents, and we are like factory line managers pushing buttons to get the agents to pump out the next feature. We tried this like ten years ago with the term feature factories, and it just doesn't work. I want my software to feel human and crafted. I want to feel like a human at the center of it all.

</details>

<!-- chunk 19/54 -->

### 构建者原则与工厂AI的诞生

**Speaker 7**: 而且我认为，因为我们都在构建这些工具，我们实际上有责任让这些工具对人类来说变得很棒。我认为这非常重要。所以，要用那些让我们感到兴奋、感到有能力、感到进入心流、感到快乐的词汇。所以我不认为未来是这样的。我不想这样。我不想待在我的黑暗工厂里，我想成为一个乐团指挥。我想有这种感觉。我想进入心流。我想玩得开心。我想搞砸一些东西。我想感觉自己像史蒂夫·乔布斯，和一群出色的人类以及AI智能体在同一个平台上设计Mac。我想感觉自己像在指挥一个乐团。所以，这是我关于如何成为你所在组织中最佳构建者的原则：靠近前沿，不要试图成为市场，创建无槽点区域，喂养野兽，释放智能体，思考乐团而非工厂。我编了一个好记的缩写：STISTIKFE。好了，非常感谢你们的邀请。我会在附近回答大家的问题。我们网上见。

<details>
<summary>Original English</summary>

**Speaker 7**: and i think because we're all building these tools, we actually have a responsibility to make the tools um great for humans. i think it's really important. so like use the words, i make us feel feel excited and like feel feel feel capable and fufeel, like we're in the flow and having fun. and so i don't think the future is, uh is, is something like this. i don't want to be. i don't want to be in in my dark factory II want want to be a lie manager. i want to feel like this. i want to be in the flow. i want to be having fun. i want to be crashing things. i want to feel like i'm steve jobs designing the mac with a team of amazing humans and ai agents on the same place, like i want to feel like coming in orchestra. so here are my principles for being the best builder in your organization. stay near the frontier, don't try and be the market. create sslot t free zones, feed the beast, free rage agents, and think about orchestras, not factories, came of this handy acronym for for rememberit stistikfe. all right. so, thanks, thanks, thanks a ton for for having ving. i'll ll be around youll ll to ask questions. and uh, i'll see you on the internet.

</details>

**Speaker 8**: 好的。我想讲一个关于工厂本身的故事。大家好，我是Rush。我经营着Machine Craft，一家拥有100人的工厂，位于北卡罗来纳州。我是科学团队，我是预算，我什么都是。不知怎么的，我们最终构建了一个由36个AI智能体组成的系统，它运行着我们整个从产品到市场的流程。我认为这仍然有点荒谬。让我展示一下它是如何发生的，以及为什么你也可以做同样的事情。从外面看我们公司，它看起来就是机器和金属。但真正的公司，真正重要的部分不是机器，而是知识：客户是谁，我们在2019年给他们报了什么价，为什么那台机器需要一个定制的曲轴。三代以来，所有这些知识都只存在于三个大脑里。最初是我祖父的，然后是我父亲的，现在是我的，这真是一种极其可怕的经营公司的方式。当你这么说的时候，很多人加入过我们，也有人离开过我们，那扇旋转门从未停止。每一次有人走出去，我们大脑的一部分就跟着他们走了。我们不害怕竞争对手。我们害怕的是遗忘，害怕某天醒来发现整个公司只存在于两个日渐衰老的脑袋里。所以我有了一个想法。老实说，一开始听起来很疯狂。但如果我们不把知识写在没人会读的文档里呢？如果我们培养一个大脑来承载它呢？不是一个你可以戳一下的聊天机器人，而是一个公司的数字孪生。我没有雇佣销售团队。我试图自己构建一个，这工作量巨大，因为你需要知道这有多混乱。我们制造热成型机器。它们加热塑料片并成型，同一台机器，但最终却能生产水培容器、汽车零部件、太阳能板、医疗用品甚至包装——七个完全不同的领域，七个完全不同的买家。所以这个大脑不能只是记住一本宣传册。它必须知道一个给定的客户生活在哪个宇宙里。这几乎无聊地简单：我们喂给它一切，我的意思是，一切：多年的CAD图纸、付款计划、时间表、邮件威胁、数百GB的我们自己的私有历史——不是公共互联网，是我们的互联网。这里是转折点，也是让每个工程师都惊讶的部分：我也做了这个。我们没有训练模型，地下室里没有GPU在嗡嗡响。没有微调。我们只是查看了所有历史，把它切成小块，让现成的模型阅读并提取事实。我们把每个块的含义存储为向量和关系（谁和什么相连），作为一个图。这个大脑不是一个更聪明的模型。它实际上是一个非常、非常有组织的记忆。现在，事情变得有点……以一种好的方式。我们不再把AI看作软件，而是开始把它看作我们正在养育的东西。所以我们给了它一个基于生物学的身体：感知能力来弄清楚谁在和它说话，消化文档成事实的能力，记忆，一个“梦境周期”，一个免疫系统来对抗错误信息。为什么是生物学？因为进化已经花了十亿年解决“你如何保持连贯？”这个问题。我们只是抄袭了作业。好了，关键问题：为什么是36个智能体，而不是一个天才、一个巨大的提示？你已经知道答案了，如果你曾经尝试过一个应该做所有事情的提示，结果它把所有事情都做得很糟糕。所以这不是一个单一的心智。这是一个团队，一群专家。每个智能体只有一个工作：Tina负责会议室，Prometheus负责销售，BlueButters负责定价，Habastors知道每台机器的规格，VetaFact检查一切，而我最喜欢的是Guid的修正——一旦人类修正了一个错误，它就会永远被修复。一个智能体，一份工作。这是一个团队，不是一个英雄。最酷的部分是：它们会开会。Tina召集专家们。它们真的会争论，然后另一边会得出一个单一的答案。这就像一个从不睡觉、从不醉酒、而且不知何故没有自我的董事会会议室。那么所有这些到底做了什么？老实说，整个前端业务——从一个陌生人在某处出现到他们成为客户之间的所有事情——九个具体的工作，每一天：真正引用真实世界账户的对外邮件，基于交叉核对数据构建的简报，报价，一个用于外联的“左滑右滑”模式，重新激活死掉的线索（我称之为“来自过去的冲击”），处理入站回复并在我们浪费一小时之前判断一家公司是否合适。九个工作，一个从不睡觉的操作员。那么所有这些运行在哪里？一个Google表格？真的，就这个。你打字进去，它就会带着十几个搜索跑出来。知识库到达收件箱，放下邮件，然后在你真正发送任何东西之前展示给你看。在引擎盖下，这是一个真正的技术栈，不是一个用胶带粘起来的演示：用于向量的数据库，用于关系的图数据库，用于CRM的数据库，三个不同的模型提供商，每个都适合特定的工作。它实际上是最好的工具：用于文档的Google，用于每个通信渠道的，加上监控，这样我们就能看到它在想什么。所有这些，每个能力都通过一个协议暴露为230个工具，以及一条黄金法则，我们从不打破：AI起草，人类批准。现在说说记忆。这是大多数AI悄悄对你撒谎的地方，因为一个原始的语言模型基本上是一条金鱼——大约30秒内很聪明，然后你关上盖子，它就忘了你曾经存在过。所以我们有目的地分层设计了记忆：工作记忆（最近几分钟），关于某人的事实记忆，情景记忆（将整个对话作为小故事），关系记忆（带有从陌生人到信任者的温度），以及门口的一个“保镖”——一个筛选机制，决定什么值得记住。

<details>
<summary>Original English</summary>

**Speaker 8**: okay. i want to delay a story about a factory daught itself. how to remember hi, i'm rush up. i run machine craft one hundred people factuin in there noror day, the science team, nor i'm a the budget, none of that. and somehow we ended up building a thirty six AI agent that runs up and dire go to market. i think that's still a little ridiculless. let me show you how it happen and why can do the same thing. so here's the thing about our company from the outside, it looks like machines and metal. but the actual company, the bd that matters isn't the machines is the knowledge who the customer is what we quotted them into thousand and nineteen, why that one machine he needed bebeard custom week. and for three generations, all of that lived in exactly three brands. initially my grandfathers, the myour fathers and now mine, which is a genuinely terrifying way it on another company. when you said with it, a lot of people have joined us. people have left us that revolving doors never stopped. and every single time, someone walked out a junk of our brain, walked out with them. we weren't sare red of competitors. we were scared of forgetting are waking up one day and realizing the whole company only existed inside two increasingly died heads. so i had an idea. i'll be honest, sounded insaying first. but what if instead of writing the knowledge down in some document, nobody ever leads? what if we grew a brain that just held it, not a chat bot, you poke at a twin of the company. i didn't hire salelsty. i tried to build one a quite deat work, because you need to know how messy this is. we make term farming machines. they heit up a plastic sheet and shape it it same corore machine, but it ends up making hyroponic countries sparbbh tubs ev, ca, panels, medical kissings and even packaging seven totally different words, seven totally different buyers. so this brain couldn't just memorize a brochure. it had to know which universe a given customer lives in sapbn was almost boring. ly, symbol, feeded, everything, and i mean, everything, years of goat's drawings, payment schedules, timelines, email threats, hundreds of gigabytes of our own private history, not the public internet, our internet. and here's the plot burst the part that surprises every engineer. i dll this too. we have a trained a model, no gp s huming in the basement. no fine tuning. we just looked at all the history, chopped it into bite size junks, and let off shrulf models, read it and pull out the facts. we stold the meaning of each junk as vectors and relationships who's connected to what, as a graph, the brain is in a smarter model. it's actually a really, really well organized memory. now this is where it gets a little bit in a good way. we stopped thinking of era as a software and started thinking of it as something we've raising. so we gave it a body modered on biology senses to figure out who is stocking to a got to digest the documents into facts, a memory, a dreamccycle, an immune system to fight off bad information by biology. well, because evolution already spent a billionaire solving. how do you stay cohead over over? we just cocoy, ed, the homework, okay. so the big question, why thirty six agents, instead of one genius, mga prompt bigres? and you already know this, if you ever try ed one prompt that suppposed to everything ends up doing everything badly. so ita isn't one mind. it's a bantiin, a whole gust of specialist. each one has exactly one antra PA tina runs the room prometeus owns the sale. blututers does pricing. habastors knows every machine speck called veta fact, jcks everything and mmen my favorite guid's corrections. so the second and human fix is something it days fixed forever. one agent, one job, it's a team, not a hero, and here's the cool bot. they hold meetings, a tina bose en specialists. they actually argue, and a single answer comes out the other side. it's like having a board room that never sleeps, never get styted and somehow has no eagle. so what does all this actually done? honestly, the whole front business, everything between a stranger exist somewhere. and now they are a customer nine concrete jobs, every single day, outbound emails that actually reference with my real world account briefs, built from cross checked fooits before a cal quotations, a swipe left swipe bride mode for outreach, reviving dead leads, which i call blast from the blast inbound replies and figuring out before we waste an hour, whether a company is even a fit nine jobs, one operator who never sleeps ps, where does all this live? one girls adapt? that's genuinely it you type. and eat out each es out with a dozen hands search. the knowledge beers reach the in box, drops the email bears the god, and then shows you before anything actually goes out under the hood is genuinely a real stack, not a demo held together with a tape data basis for vectors for relationship graph for the c rm, three different motor providers, each big for the job. it's actually best for dools for google for swallowing documents for every communication channel plus monitory. so we can see what is thinking all of it, every capability exposed as two hundred and thirty tools over one protocol and golden den le. the one we never break, ira, drafts, human sense. now memory. and this is the bodwhere where most II quietly lied to you, because a row language model is basically a gold fish brilliant for about thirty seconds, and then you close the dobin and forget you ever existed. so we engineer memory on purpose in layers, working memory for the last few minutes. in fact, about someone who is episodes des whole conversations as little stories, relationships with warmpth that grows from stranger to truster and a bouncer at the door, a salian skit that decides what's even worth for remembering.

</details>

**Speaker 6**: 这样大脑就不会在没有依据的情况下胡编乱造。

<details>
<summary>Original English</summary>

**Speaker 6**: so the brain doesn't get up without making things up.

</details>

### AI编码的演进与自主性转折点

**Speaker 9**: 嗨，我叫Duckch。我是一家名为Graphite的公司的联合创始人。在Graphite，我们正在开发AI智能体，它们能在拥有完整代码库上下文的情况下审查和测试拉取请求。我们的做法是，当你打开一个拉取请求时，Graphite会解析文件。它使用代码库的知识库来理解哪些内容可能受到影响。它还会在沙盒中运行你的代码以发现各种问题。但我今天不想谈论Graphite。我想谈论的是非常有趣的事情。所以，当我三年前第一次搬到旧金山湾区时，正是AI编程真正开始起作用的时候。那时我们有带Tab补全的GitHub Copilot，以及后来带有更高级Tab补全的Cursor。2024年，AI智能体变得稍微好了一些。我们开始看到多文件编辑。这来自Cursor和早期版本的Claude Code。2025年，一些有趣的事情开始发生，那就是智能体变得越来越自主。2025年12月是转折点，对于任何在AI编码领域工作或使用AI编码的人来说，都明白那些模型与之前的模型有本质上的不同，它们是完全自主的。它们可以从一个工单直接生成一个拉取请求。对对对。从那时起，推特上似乎充满了人们尝试使用“polyphysics sleep”来保持他们的智能体存活，并在一夜之间构建大量代码的故事。对我来说，这似乎是在独立黑客项目或初创公司的领域内可能发生的事情，但不是在大型企业里，而大型企业正是我们合作的所有公司。

<details>
<summary>Original English</summary>

**Speaker 9**: 哎, my name is duckch. i am one of the cofounders of a company called grapp tile. and a grapp tile. we are working on AI agents that review and test poll requests with full context of the code base. the way we do this is when you open a poll request, gragraptile resolve the files. it uses a knowledge base of the code base to understand what could potentially be affected. it also runs your code in a sandbox defind various issues, but i don't want to talk about grapal today, but i want to talk about is something very interesting. so when i first mood or summer ers has go three years ago was when ai coding had really started it to work. and what we have at that time was sccopilot with tab complete and later cursor with more vanced tob complete in twenty twenty four ai agents call a little better. and we started to see multii file edits. this was with cursor and early versions of cloud code in twenty twenty five. something interesting started to happen, which is the agents got increasingly autonomous. and december of twenty twenty five was the turning point for anyone that's working in the ecoding ying or using a adecode that understand that those models were fundamentally different from the ones that came before and that they were completely autonommous. they could go from ticket to poor request. 对对对. and from there, twitter seem to be full of stories of people experimenting with polyphysics sleep to keep their agents alive and building large amounts of code all the ones. and to me, it seemed like this was something that was possible inside the realm of maybe indie. hacker projects are shartups, but not the enterprise, which was all of the companies that we were working with.

</details>

<!-- chunk 20/54 -->

### 自主智能体编码的质量评估

**Speaker 9**: 而且我并不能确定，真正的自主智能体编码能否在企业中真正起飞。

<details>
<summary>Original English</summary>

**Speaker 9**: and there's no sure that i had that truly agentic coding could not take off of the enterprise.

</details>

**Speaker 9**: 我们开始面临一个挑战，因为我听到了很多关于人们在企业中做这些事情并且确实有效的报告。

<details>
<summary>Original English</summary>

**Speaker 9**: we starting to a challengge because i heard many reports of people doing the stuff in the enterprising that it was really working.

</details>

**Speaker 9**: 所以我变得非常好奇。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i got really curious，

</details>

**Speaker 9**: 这些由智能体生成的 PR 真的好吗？

<details>
<summary>Original English</summary>

**Speaker 9**: are these three five pr s actually good.

</details>

**Speaker 9**: 你能在拥有真实客户的大型公司里做到这一点吗？

<details>
<summary>Original English</summary>

**Speaker 9**: can you do this at a large scale company with real customers？

</details>

**Speaker 9**: 而当它们确实失败时，又是以何种方式失败的？

<details>
<summary>Original English</summary>

**Speaker 9**: and in what ways did they fail when they did fail？

</details>

**Speaker 9**: 所以，作为一个业余的数据科学家，我决定深入数据，看看结果如何。

<details>
<summary>Original English</summary>

**Speaker 9**: so as an amateur day，

**Speaker 9**: scientist，

**Speaker 9**: i decided to dive into the data and see what came of it.

</details>

**Speaker 9**: 而我发现的第一件事是，要弄清楚哪些 PR 是完全由“氛围编码”生成的，实际上非常困难。

<details>
<summary>Original English</summary>

**Speaker 9**: and the first thing that discovered it was，

**Speaker 9**: it's actually very hard to figure out which prs are fully vibe coded.

</details>

**Speaker 9**: 我们处理着数万个数据集。

<details>
<summary>Original English</summary>

**Speaker 9**: i've got how we work work with tens，

**Speaker 9**: thousands，

**Speaker 9**: ds tetes.

</details>

**Speaker 9**: 我们处在一个有趣的位置，我们不是代码的编写者，而只是代码的审查者，但所有这些代码都经过我们的系统。

<details>
<summary>Original English</summary>

**Speaker 9**: and and we this inteinteresting place where we're not the quoters，

**Speaker 9**: but only the reviewers of the code，

**Speaker 9**: but all this code goes through our system.

</details>

**Speaker 9**: 而在这些公司中，比如 Canva、Coinbase 和 Scale，都是真实的公司、真实的客户和关键的工作负载，要识别哪些 PR 是“氛围编码”的非常困难，但我决定试一试。

<details>
<summary>Original English</summary>

**Speaker 9**: and any these companies companies like can video and coin base and scale，

**Speaker 9**: real companies，

**Speaker 9**: real customers and critical workas and letifying，

**Speaker 9**: which pr were bibicoded was difficult，

**Speaker 9**: but i decided to give it a shot.

</details>

**Speaker 9**: 我尝试的第一件事是，我查看了 Git 的 author 字段。每次提交在 GitHub 上都必须有一个作者字段。

<details>
<summary>Original English</summary>

**Speaker 9**: and the first thing that i tried was，

**Speaker 9**: i looked with the guit of author field every commitsion and get up has to have a field for the author.

</details>

**Speaker 9**: 我想，如果作者被标注为 Cursor 或 Claude Code，那就有很强的证据表明这是一个完全由“氛围编码”的 PR。

<details>
<summary>Original English</summary>

**Speaker 9**: and i figured that if the author was attributed to cotex or cloud code，

**Speaker 9**: that was pretty strong evidence that that was a fully vide PR.

</details>

**Speaker 9**: 但我发现，在所有 PR 中——再次强调，每个月有超过一百万个拉取请求经过 Graphite——实际上只有大约百分之一的 PR 在作者字段中被归因于某个智能体。

<details>
<summary>Original English</summary>

**Speaker 9**: but i found out of all the pr，

**Speaker 9**: and again，

**Speaker 9**: more than a million poll requests go through a grpbed der every month，

**Speaker 9**: only about one of every hundred who were attributed to an agent in the author field in tudity.

</details>

**Speaker 9**: 这对我来说说不通。不可能只有百分之一的 PR 是完全由“氛围编码”的。

<details>
<summary>Original English</summary>

**Speaker 9**: this didn't make sense to me.

**Speaker 9**: it couldn't be the only one percent of all pr were fully vibb coded.

</details>

**Speaker 9**: 所以我开始查看 PR 描述。结果发现，这些智能体和人类一样自恋，它们喜欢留下痕迹，表明是它们自己编写了代码。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i start looking for PR description.

**Speaker 9**: furters turns out these agents are as narcsistic as humans are，

**Speaker 9**: and they like to leave traces that they are the ones that worked on the code.

</details>

**Speaker 9**: 所以 Claude 会留下“co-authored-by: Claude”，而 Codex 会留下“co-authored-by: Codex”，这似乎有点帮助。

<details>
<summary>Original English</summary>

**Speaker 9**: and so cloud would leave a co author by cloud and codex would leave a coauthor by codex，

**Speaker 9**: and that seemed to help a little bit.

</details>

**Speaker 9**: 第三件事是，分支前缀——Cursor 实际上会为你命名分支。而且我直觉上认为，如果有人使用 Cursor 来生成分支名称，那就有很好的证据表明该 PR 的大部分代码是“氛围编码”的。

<details>
<summary>Original English</summary>

**Speaker 9**: the third thing other that was branch preprexxcocotex actually names the branches for you.

**Speaker 9**: and it seems to me intuitively that if someone was using cotex to produce the branch names，

**Speaker 9**: it was pretty good evidence that most of that PR was vive cauin.

</details>

**Speaker 9**: 我发现，在四月份，Graphite 审查的所有 PR 中，有超过四分之一有证据表明，即使不是完全，至少在很大程度上是由“氛围编码”生成的。

<details>
<summary>Original English</summary>

**Speaker 9**: i found it in a month of april，

**Speaker 9**: more than a quarter of all pr that gpplle reviewed had evidence of being，

**Speaker 9**: if not fully，

**Speaker 9**: at least largely vibe coded，

</details>

**Speaker 9**: 然后我把这个数字回溯到之前的几个月。结果发现，变化的速度非常快。

<details>
<summary>Original English</summary>

**Speaker 9**: then attract this number back to the previous whove months.

**Speaker 9**: and it turns out that the rate of change is incredibly fast.

</details>

**Speaker 9**: 大约一年前，只有不到百分之一的拉取请求有证据表明是完全由“氛围编码”生成的，而现在这个数字超过了四分之一，并且还在上升。于是真正的问题来了。

<details>
<summary>Original English</summary>

**Speaker 9**: about a year ago，

**Speaker 9**: less than a percent of all poll requests had evidence of being fully vibe coded and a neighble that number was more than a quarter and trend ding upwards and then became the real question.

</details>

**Speaker 9**: 这些 PR 好吗？真正的公司正在这样做吗？它们好吗？你能合并这些代码吗？它们是垃圾，还是真正的好软件？

<details>
<summary>Original English</summary>

**Speaker 9**: are these perds？

**Speaker 9**: any good are real companies doing this？

**Speaker 9**: are they？

**Speaker 9**: any good？

**Speaker 9**: can you merge this stuff as there's just slop as it real good software？

</details>

**Speaker 9**: 首先，问题变成了：一个拉取请求“好”意味着什么？一个由“氛围编码”或人类编写的拉取请求“好”意味着什么？所以我开始对 PR 质量进行一些统计分析。

<details>
<summary>Original English</summary>

**Speaker 9**: and at first then then question becomes.

**Speaker 9**: what does it mean for a poll request to be good？

**Speaker 9**: what does it mean for a vibe coted or AA human written poll request to be good so that i started to do some statistical analysis around pr quality.

</details>

**Speaker 9**: 我首先查看的是回滚率。GitHub 允许你回滚拉取请求。如果一个拉取请求被回滚了，那它肯定不太好，这看起来是合理的。

<details>
<summary>Original English</summary>

**Speaker 9**: and the first thing that i looked that with revert rates helld lets you revert poll request，

**Speaker 9**: and it seemed reasonable that if a poll request was reverted，

**Speaker 9**: it must have not been very good.

</details>

**Speaker 9**: 所以我开始追踪我们整个客户群的回滚情况。方便的是，GitHub 会用“reverted-”加上 PR 名称来标记被回滚的分支。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i started tracking reverts across our entire customer mobase conveniently get how labels reverted branches with reverted to dash and in the name with the pr.

</details>

**Speaker 9**: 所以我开始查看拉取请求被回滚的比率。这是我发现的数据：对于 Cursor，大约每千个请求中有一个被回滚；对于 Devin，这个数字是千分之一点五；而对于人类，有趣的是，对于那些有合理证据表明主要由人编写并且至少由人拥有的 PR，这个数字大约是千分之二点五。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i started looking at the rates at which portoquests were being reverted.

**Speaker 9**: this is the data that i found the codetex about one out of every thousands requests seem to be reverted for dedevon.

**Speaker 9**: that number was in a half and for humans.

**Speaker 9**: interestingly，

**Speaker 9**: for yars that there was reasonable evidence that it was written largely by a person and earleast owned by a person.

**Speaker 9**: the number was round two and half.

</details>

**Speaker 9**: 这些数字都在一个相当接近的范围内。它们都很小，都低于百分之十，并且彼此之间都在一个范围内。

<details>
<summary>Original English</summary>

**Speaker 9**: these numbers are fairly within range.

**Speaker 9**: they're all small，

**Speaker 9**: less ten percent and all kind of within range of each other.

</details>

**Speaker 9**: 所以我开始查看其他证据，因为我非常确信那些关于“四分之一 PR 是氛围编码”的文章。所以我真的在寻找证据来证明这一点。

<details>
<summary>Original English</summary>

**Speaker 9**: so i start looking at some other piece of evidence，

**Speaker 9**: because i was very convinced of these wipe quarterpiar's articles.

**Speaker 9**: so i was really looking for evidence that，

**Speaker 9**: that was true.

</details>

**Speaker 9**: 所以我接下来查看的是，回滚率是否因 PR 大小而异。因为似乎有可能人们让智能体做简单的工作，处理那些直截了当的、验证性的工单，而人类则承担更复杂的任务。这就是为什么它们的回滚率相似？

<details>
<summary>Original English</summary>

**Speaker 9**: so the next thing i look that was are the river is different by size because it seemed there was possible that people were making agents do simple or work.

**Speaker 9**: it was the straighforward of valalidefying tickets，

**Speaker 9**: said agents were working on and humans were taking on the more complex tasand.

**Speaker 9**: that's why why were were ate for similar？

</details>

**Speaker 9**: 而且 PR 大小似乎是变更复杂性的一个很好的代理指标。但结果发现，回滚率在不同大小的 PR 之间实际上保持相对稳定。甚至没有一个明确的模式表明智能体在处理更小或更简单的任务。

<details>
<summary>Original English</summary>

**Speaker 9**: and it seemly ly pr size was a good proxy for complexity of a change.

**Speaker 9**: but it turns out that revert rates actually stayed relatively stable across different sizes.

**Speaker 9**: there wasn't even a real pattern that said that agents were working on smaller or simpler tasks.

</details>

**Speaker 9**: 结果发现，智能体的回滚率在整个范围内相当均匀。对于人类来说也是如此。

<details>
<summary>Original English</summary>

**Speaker 9**: it turns out revert raate tes were pretty even across the board for agents.

**Speaker 9**: and for humans，

</details>

**Speaker 9**: 我接下来查看的是 Graphite 的评论。如果 Graphite 正在审查和测试所有这些代码的智能体，那么它理应在更差的代码中发现更多问题。Graphite 会用 P0、P1 或 P2 来标记所有问题。

<details>
<summary>Original English</summary>

**Speaker 9**: the next thing i that，

**Speaker 9**: that was grab helile comments，

**Speaker 9**: if grappiles the reviewing and testing embattedating agent for all of this code，

**Speaker 9**: it's imreasonable that it would find more issues and code that was worse and grb phile community labels all the issues with pey，

**Speaker 9**: euroes，

**Speaker 9**: p ones or petus.

</details>

**Speaker 9**: 所以我开始追踪 Graphite 在人类编写的 PR 与完全由 AI 编写的 PR 中发现 P0、P1 和 P2 问题的比率。结果再次显示，人类编写和 AI 编写的 PR 之间没有显著差异。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i started tracking the rates at which grrup hirle finds pezeroes p ones and petus across poor requests that written by people versus ones written entirely by eye.

<details>
<summary>Original English</summary>

**Speaker 9**: what's again，

**Speaker 9**: there just was not damage of difference between the human written and airir and poll requests.

</details>

**Speaker 9**: 事实上，人类实际上比 Devin 或 Cursor 更有可能制造 P0 错误。类似地，在 P1 错误方面，Devin 和 Cursor 产生的 P1 错误更少，而 P2 错误则更接近。再次强调，根本没有双重证据表明智能体编写的 PR 比人类编写的 PR 更差或更具关键性损害。

<details>
<summary>Original English</summary>

**Speaker 9**: in fact，

**Speaker 9**: humans are actually more likely to make p zero errors than devithin cortex or claud.

**Speaker 9**: similarly，

**Speaker 9**: the case with p ones where both devin and cotex created fewer p ones and p pets were even closer.

**Speaker 9**: once again，

**Speaker 9**: there just wasn't double ge vidence that the agent written ps were meaningfully worse or more critically damaged than their human wrt encounterparts.

</details>

**Speaker 9**: 我接下来查看的是审查轮次。使用 Graphite 的一个非常常见的模式是，你进行一次审查，提交一个拉取请求，给出一些评论，然后让智能体修复这些评论，在拉取请求中再提交一次，通常两轮就足以解决拉取请求中的所有问题，并使其达到可合并状态。

<details>
<summary>Original English</summary>

**Speaker 9**: the next thing i looked at with the review rounds，

**Speaker 9**: a very common pattern for using rapile.

**Speaker 9**: is that you have a review，

**Speaker 9**: a poll request，

**Speaker 9**: give it some comments，

**Speaker 9**: and then you let the agent to fix those comments，

**Speaker 9**: make another committer in the poll request and usually two rounds enough for all of the issues from the poor request to be addressed and for the poor request to be grato to emerged.

</details>

**Speaker 9**: 看起来合理的是，一个更聪明或更有能力的拉取请求作者应该能够用更少的审查轮次达到可合并状态。这对我来说似乎很直观。

<details>
<summary>Original English</summary>

**Speaker 9**: it seemed reasonable that a smarter or more capable author for a polar quest would be able to get to emergerable pr with fewer review round that seemed into it of you true to me.

</details>

**Speaker 9**: 所以我开始追踪平均审查轮次数量。对于 Devin，略高于两轮；对于人类，2.2 轮；对于 Cursor，2.5 轮。再次强调，完全在一个范围内。平均轮次数相当一致。再次强调，没有证据表明智能体生成的 PR 更差。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i started tracking average number of review rounds were deven little over two for people，

**Speaker 9**: two point two vercocotex to a half once again，

**Speaker 9**: entirely within arrange the mean number beerations.

**Speaker 9**: it took foreign agent or a percent to get a polar quest st.

**Speaker 9**: emergitble state was fairly consistent throughout once，

**Speaker 9**: again，

**Speaker 9**: no evidence of agentic pr mean worse.

</details>

**Speaker 9**: 既然没有强有力的证据表明这些 PR 在数量上更差或更好，我有兴趣看看是否存在不同的失败模式。智能体编写的 PR 和人类编写的 PR 是否以不同的方式失败？

<details>
<summary>Original English</summary>

**Speaker 9**: so now that there wasn't any strong evidence that these were quantitative，

**Speaker 9**: the worse or better i was interested in seeing there were patterns of failure.

**Speaker 9**: there were different in agent writain ps huhuwritten PS where they badred in different ways.

</details>

**Speaker 9**: 所以我开始追踪一些关于这方面的有趣数据。我是这样做的。Graphite 会在所有这些拉取请求上留下评论。它倾向于识别各种逻辑、性能和安全性错误。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i started tracking some interesting data around that here.

**Speaker 9**: re's how i did it.

**Speaker 9**: so group hyle leaves comments on all of these protocosts.

**Speaker 9**: it tends to identify all kinds of logic performance and security earars.

</details>

**Speaker 9**: 所以我决定运行一个非常简单的文本搜索，并说：好的，不同类型的错误在不同智能体之间是否不同？对于不同的大小是否不同？现在，这里的数据集非常大。它有数百万个拉取请求。所以这些数据是合理的，置信度很高。当然，你不能使用所有数据。所以我只用了大约两个月的数据。因为在那之前，这些智能体基本上已经过时了。

<details>
<summary>Original English</summary>

**Speaker 9**: and so i decided to run a very simple tech search and said，

**Speaker 9**: okay，

**Speaker 9**: are types of errors in different agents，

**Speaker 9**: different for different size.

**Speaker 9**: now the data set here is quite large.

**Speaker 9**: it's in the millions of protoquests.

**Speaker 9**: and so this data is reasonable，

**Speaker 9**: high confidence.

**Speaker 9**: and of course，

**Speaker 9**: you can't use all data.

**Speaker 9**: so i only used about two months of data.

**Speaker 9**: since prior of that，

**Speaker 9**: the agents are are essentially obsolete and IW.

</details>

**Speaker 9**: 一些非常有趣的数据点出现了。例如，Claude 产生 SQL 注入错误的可能性是人类的三倍。来自 Devin 的授权绕过错误比来自任何其他智能体或人类的要少一半。另一个有趣的数据点是，空指针引用错误在 Cursor 中比任何其他智能体都要常见得多，每种错误都更常见。

<details>
<summary>Original English</summary>

**Speaker 9**: some very interesting datpoints clard for instances wanted to have times more likely than people to produce a equal injection error.

**Speaker 9**: author bypasses are half as likely coming from deven than from any other agent and from people and another interesting data point.

**Speaker 9**: but and plus one greos were much more common and cursor than any other，

**Speaker 9**: each of farm more common.

</details>

**Speaker 9**: 对我来说有趣的是，当这些智能体在多种不同衡量标准下表现的好坏程度如此一致时，它们在出错的定性方面却有如此大的差异。

<details>
<summary>Original English</summary>

**Speaker 9**: it was interesting to me that there were this much variation in the qualitative aspects of what these agents were getting wrong when there were so much consistency in how good or bad they were and been measured in many different ways.

</details>

**Speaker 9**: 所以，结果可能是自主智能体实际上相当不错。这对我来说非常令人兴奋，因为某种程度上，我在编程真正起飞之前就成了一名程序员。我和我们许多人一样，习惯了编程这门手艺。而我们在训练四、训练五中看到的许多“氛围编码”智能体似乎更有前途和实质内容，尤其是在应用于专业商业环境时。

<details>
<summary>Original English</summary>

**Speaker 9**: so it might turn out that autonomous agents are actually quite good.

**Speaker 9**: and this is very exciting to me because it an an ttent，

**Speaker 9**: i kind of become programmmer before i had taken off.

**Speaker 9**: and i was used to，

**Speaker 9**: like many of us，

**Speaker 9**: the craft of programming，

**Speaker 9**: and it seemed like a lot of the vibe coded agents we were seeing in training，

**Speaker 9**: train four and training.

**Speaker 9**: trainfive were a lot more promised and substance，

**Speaker 9**: especially and applied to professional commercial settings.

</details>

**Speaker 9**: 怎么了。

<details>
<summary>Original English</summary>

**Speaker 9**: 怎么了。

</details>

**Speaker 9**: 但趋势似乎非常清晰。这些智能体正变得非常非常擅长编码，不仅在通用环境中，而且 Graphite 的客户群主要由大公司组成，而不是个人开发者。当然，个人开发者并不真正审查他们的代码，也不需要。所以这个样本基本上是由拥有真实客户的公司组成的。

<details>
<summary>Original English</summary>

**Speaker 9**: but the dejetory seems quite clear.

**Speaker 9**: these agents are getting really，

**Speaker 9**: really good and the're，

**Speaker 9**: getting really good at coding，

**Speaker 9**: not only in general environments，

**Speaker 9**: graplds customer bases made up much more of larger companies than a days of individual quotors.

**Speaker 9**: of course，

**Speaker 9**: individual quotors don't really review their code of don't nneed too.

**Speaker 9**: and so this sample said said，

**Speaker 9**: is essentially created compcompanies with well customers.

</details>

**Speaker 9**: 结果发现，他们实际上可以在商业环境中进行大量的“氛围编码”。所以我们开始思考这对代码审查和代码验证意味着什么。如果大部分代码都将完全由智能体编写，而且看起来智能体编写的代码相当不错，那么代码审查应该是什么样子？我认为有几件事非常清楚。

<details>
<summary>Original English</summary>

**Speaker 9**: and it turns out that they actually can do lot lot true vibe coding in a commercial setting.

**Speaker 9**: so we started thinking about what that means for code review and code validation.

**Speaker 9**: if most of the code is going to be written entirely by agents，

**Speaker 9**: and it seems like the agents writing pretty good code，

**Speaker 9**: then what should code review look like？

**Speaker 9**: i think a couple of things very clear.

</details>

<!-- chunk 21/54 -->

### 从统计中浮现的关键发现

**Speaker 9**: 从我的统计分析中浮现出的一个关键数据点是，在法院撰写判决的数量上，第99百分位的法院与第50百分位的法院之间存在相当大的差异。

<details>
<summary>Original English</summary>

**Speaker 9**: The initiating data point that emerges from my statistical analysis is that there was quite a bit of a difference between the 99th percentile of courts and the 50th percentile courts in terms of how much courts are writing.

</details>

**Speaker 9**: 事实上，使用Graphite的中位数法院每月只撰写大约50次提交。

<details>
<summary>Original English</summary>

**Speaker 9**: In fact, the median court that uses Graphite is writing fewer than 50 commits a month.

</details>

**Speaker 9**: 而第99百分位的法院每月撰写的提交数量接近1000次。

<details>
<summary>Original English</summary>

**Speaker 9**: The 99th percentile is writing close to 1000 commits a month at that scale.

</details>

**Speaker 9**: 这完全不可行，尤其是当这将成为人们编码的标准时，去做任何类似于手动代码审查的事情。

<details>
<summary>Original English</summary>

**Speaker 9**: It is completely infeasible, especially if this is going to be the standard for how people code, to do anything resembling manual code review.

</details>

**Speaker 9**: 同样，维护大型测试套件似乎也不符合直觉，我对此深表怀疑。

<details>
<summary>Original English</summary>

**Speaker 9**: It also seems not intuitive that we would be maintaining large test suites, as I go to hell.

</details>

**Speaker 9**: 我们对这个想法感到非常兴奋：我们可以构建真正自主的代码验证。

<details>
<summary>Original English</summary>

**Speaker 9**: We got really excited about this idea that we could build truly autonomous code validation.

</details>

**Speaker 9**: 我们开始思考这意味着什么。

<details>
<summary>Original English</summary>

**Speaker 9**: We start thinking about what that means.

</details>

**Speaker 9**: 当然，在之前的时代，代码验证由这三个一般方面组成。

<details>
<summary>Original English</summary>

**Speaker 9**: And of course, code validation in the prior era was made up of these three general facets.

</details>

**Speaker 9**: 你会进行测试、审查和质量保证。

<details>
<summary>Original English</summary>

**Speaker 9**: You'd have testing, you have review, and you have quality assurance.

</details>

**Speaker 9**: 但对我们来说，这些仅仅是实现细节。

<details>
<summary>Original English</summary>

**Speaker 9**: But to us, these are simply implementation details.

</details>

**Speaker 9**: 代码验证的目标实际上只是回答三个非常简单的问题。

<details>
<summary>Original English</summary>

**Speaker 9**: The goal of code validation was actually just to answer three very simple questions.

</details>

**Speaker 9**: 这个变更是否违反了用户契约？这个变更是否增加了未来用户契约被违反的可能性？第三，它是否实现了作者的意图？

<details>
<summary>Original English</summary>

**Speaker 9**: Does this change violate the user contract? Does this change increase the future propensity of a user contract to violation? And third, does it fulfill what the author intended?

</details>

**Speaker 9**: 因此，我们从零开始设计了Graphite，以精确地回答这三个问题。我们通过审查代码来实现这一点，当然，是以一种更传统的方式，使用代理来查看代码，查看变更的影响范围，找出可能受影响或相关的代码。

<details>
<summary>Original English</summary>

**Speaker 9**: And so we've designed Graphite from the ground up to exactly answer those three questions. We do this by reviewing the code, of course, in a more traditional sense where we use agents to look at the code, look at the blast radius of the change, find out the stuff that could be affected or related.

</details>

**Speaker 9**: 然后我们在沙盒中运行代码，使用网络浏览器代理四处点击，试图破坏东西，模拟用户行为。

<details>
<summary>Original English</summary>

**Speaker 9**: And then we run the code in a sandbox, click around with web browser agents to try to break things, simulate user interactions.

</details>

**Speaker 9**: 对我们来说，这似乎是通往真正自主代码验证的一条更有效的路径，因为我很难想象，人类将审查大量代理生成的代码，并且这将成为新的软件开发工作，这种想法相当反乌托邦。

<details>
<summary>Original English</summary>

**Speaker 9**: And that seems to us to be a much more effective path towards truly autonomous code validation because it's hard for me to imagine that this idea that humans would be reviewing large amounts of agent code, and that would become the new job of software engineering, is quite dystopian.

</details>

**Speaker 9**: 我不认为有人会每天早上醒来，整天审查那些垃圾代码。

<details>
<summary>Original English</summary>

**Speaker 9**: I don't think anyone wants to wake up every morning and review slop all day.

</details>

**Speaker 9**: 我更愿意花时间想出天才的想法，然后让机器去弄清楚如何将其转化为商业级代码。

<details>
<summary>Original English</summary>

**Speaker 9**: I'd much rather spend the time coming up with the genius ideas and letting machines figure out how to turn that into commercial grade code.

</details>

**Speaker 9**: 这就是我的演讲。我叫Ducch，你今天可以在Rapal找到我。你也可以来我们的展位，我们有一台街机。非常感谢。

<details>
<summary>Original English</summary>

**Speaker 9**: That's my talk. My name is Ducch and you can find me at Rapal today. You can also come by our booth, we have an arcade machine. Thank you so much.

</details>

### 重新思考AI代理与视觉内容

**Speaker 11**: 嗨，我是Nori Authentic的CEO。我们部署了一个AI员工，它了解你的公司、你的代码库、文档、Slack和其他类型的数据。

<details>
<summary>Original English</summary>

**Speaker 11**: Hi, I'm the CEO of Nori Authentic. We deploy an AI employee that understands your company, your codebase, docs, Slack and other kinds of data.

</details>

**Speaker 11**: 我们花了很多时间思考编码代理实际上是如何工作的。大多数人认为编码代理只写代码，但如果你问我，那只是糟糕的营销。先忘掉“编码”这个名字。代理几乎可以做任何事情。只有一个诀窍：你必须能够像代理一样思考，才能让它今天做你想让它做的事情。

<details>
<summary>Original English</summary>

**Speaker 11**: We spend a lot of time thinking about how coding agents really work. Most people think coding agents only write code, but if you ask me, that's just bad marketing. Forget the name for a second. Coding agents can do almost anything. There's just one trick: you have to be able to think like an agent to get it to do what you want it to do today.

</details>

**Speaker 11**: 今天我们要谈谈我们如何使用编码代理来做一些大多数人认为代理非常不擅长的事情：制作视觉制品，比如幻灯片、文档，甚至视频。

<details>
<summary>Original English</summary>

**Speaker 11**: Today we're going to talk about how we use coding agents to do something most people think agents are terrible at: make visual artifacts like slides, docs, and even video.

</details>

**Speaker 11**: 每天，全世界要投入大约34,000个人类年时间来制作幻灯片。其中大部分时间不是思考，而是摆弄。一个需要十小时的幻灯片，一旦你去掉了所有的格式、品牌和移动东西，实际上应该只需要大约25分钟。

<details>
<summary>Original English</summary>

**Speaker 11**: Every day, the world pours something like 34,000 human years into making slide decks. Most of that time isn't the thinking, it's the fiddling. A deck that takes ten hours should really take about 25 minutes once you remove all the formatting and the branding and the moving things around.

</details>

**Speaker 11**: 假设你需要制作一张幻灯片。你会怎么做？你打开一个工具：PowerPoint、Figma、Canva，然后你开始操作一个画布。这些工具中的每一个都是为人类的手和眼睛构建的。点击、拖拽、放置、调整大小、对齐、网格——所有这些动作和模式对于世界的空间视图来说是有意义的。底层有一个数据结构，但它是一种只有应用程序才能读取的格式。当你把这些工具交给一个代理时会发生什么？嗯，输出结果完全错误。东西以奇怪的方式重叠。你看不到文本。没有对齐。简直是垃圾。

<details>
<summary>Original English</summary>

**Speaker 11**: Say you need to make a slide. What do you do? You open a tool: PowerPoint, Figma, Canva, and then you start manipulating a canvas. Every one of these tools is built for human hands and human eyes. Click, drag, drop, resize, snap to grid, all motions and patterns that make sense for a geospatial view of the world. There is a data structure underneath, but it's in a format that only the application can read. What happens when you hand these tools to an agent? Well, the output comes out all wrong. Things overlap in weird ways. You can't see the text. There's no alignment. It's garbage.

</details>

**Speaker 11**: AI怀疑论者说，不仅仅是工具的问题，代理从根本上无法推理空间，而且有像ARC-AGI这样的整个基准测试正是基于这个前提建立的。有一个来自开发者Simon Willison的著名小测试。他问每个新模型同样的事情：你能画一只骑自行车的鹈鹕吗？但这里有个陷阱。代理只允许使用SVG。这是一个快速的检查，看模型是否能推理空间。以下是一些模型在这个测试中实际给出的例子。是的，这些非常糟糕，真正地、深刻地、非常糟糕。

<details>
<summary>Original English</summary>

**Speaker 11**: AI skeptics say that it's not just the tools, agents fundamentally can't reason about space, and there are whole benchmarks like ARC-AGI that are built exactly around that premise. There's a famous little test for this from developer Simon Willison. He asks every new model the same thing: can you draw a pelican riding a bicycle? But there's a trick. The agent is only allowed to use SVG. It's a quick gut check for whether a model can reason about space at all. Here's some examples of what the models actually give you on this test. And yeah, these are pretty bad, like genuinely deeply, really bad.

</details>

**Speaker 11**: 那么这是否意味着没有希望了？代理注定只能生成糟糕的图形？不，我不这么认为。如果你问我，问题不在于模型，而在于媒介。如果我让你，一个假定的人类，手写一个骑自行车的鹈鹕的SVG，你也不可能做到。SVG只是一堆数字。你无法从一堆数字变成一只鹈鹕。你就是无法那样看东西。那不是人类思考的方式。我们以图形方式思考。所以我们构建了让我们在画布上绘图的工具：Figma MCP、PowerPoint、截图、替换操作。所有这些代理工具有什么共同点？它们都像人类一样处理问题。但AI不是人类。让AI使用画布就像让人类手写SVG一样。这根本说不通。你需要根据AI的思考方式来给它工具，而不是像素。是语言、词语、标记结构——那是它的原生媒介。

<details>
<summary>Original English</summary>

**Speaker 11**: So does that mean it's hopeless? Agents are just doomed to be bad at graphics? No, I don't think so. If you ask me, it's not the model. It's the medium. If I asked you, someone who is presumably human, to handwrite an SVG of a pelican riding a bicycle, you won't be able to do that either. SVGs are just a wall of numbers. You can't go from a wall of numbers to a pelican. You just can't see that way. That's just not how people think. We think graphically. So we build tools that let us draw on a canvas: Figma MCP, PowerPoint, screenshot replace ops. What do all these agent tools have in common? They all approach the problem like a human. But an AI is not a human. Asking an AI to use a canvas is like asking a human to write SVG by hand. It doesn't really make sense. You need to give the AI tools based on how it thinks, not in pixels. In language, words, token structure, that is its native medium.

</details>

**Speaker 11**: 想象一种语言，它非常擅长描述布局，模型已经在数十亿个示例上训练过。它们直观地理解这种语言，它可以渲染成像素，并且可以在任何地方运行。没错，HTML让模型能够以结构思考。HTML标签具有内置于语言中的含义：标题、图表、网格。然后浏览器将其全部转化为像素。所以模型实际上从未放置过坐标，你可以免费获得各种视觉效果：图表、布局、字体、动画，所有的一切。

<details>
<summary>Original English</summary>

**Speaker 11**: Imagine a language that's incredible at describing layout, that models have seen and trained on billions of examples of that. They understand intuitively that it renders to pixels and can run everywhere. All right, HTML lets a model think in structure. HTML tags have meanings built into the language: a heading, a chart, a grid. And the browser turns it all into pixels. So the model never actually places a coordinate, and you can get all sorts of visual effects, charts and layouts, fonts and motion, all of it for free.

</details>

**Speaker 11**: 还记得之前的鹈鹕吗？现在让它做完全相同的任务，但是用HTML。同样的鸟，但现在它处于一个模型可以推理的结构中。你可以阅读、主题化和编辑它的每一行。

<details>
<summary>Original English</summary>

**Speaker 11**: Remember that pelican from earlier? Now ask it to do the same exact task, but in HTML. Same bird, but now it's in a structure that the model can reason about. And you can read and theme and edit every single line of it.

</details>

**Speaker 11**: 嗯，我一生都在用PowerPoint制作幻灯片。所以我一直认为这两件事——幻灯片和PowerPoint——是同义词，但这其实不是真的，不是吗？PowerPoint是你用来制作幻灯片的工具。幻灯片本身，那只是演示模式。事实证明，你的观众中没有人会关心你是如何进入演示模式的。编辑格式完全是任意的，所以你可以直接选择代理已经擅长的编辑格式：HTML。如果你之后需要渲染成不同的格式，比如PDF，我们使用这个HTML技巧来构建我们所有的幻灯片、董事会演示文稿和销售演示文稿。这些都是我们实际展示和不断发送的真实东西。

<details>
<summary>Original English</summary>

**Speaker 11**: I've spent my whole life building slide decks with PowerPoint. So I always thought that those two things, slide decks and PowerPoint, were synonyms. But that's just not really true, is it? PowerPoint is a tool that you use to make slide decks. The deck itself, that's just the presentation mode. And as it turns out, no one in your audience is going to care how you got to the presentation mode. The editing format is totally arbitrary, so you can just pick the editing format that the agents are already good at: HTML. And if you need to render to a different format like PDF later on, we use this HTML trick to build all of our slide decks, our board decks and our sales decks. These are real things that we actually present and send out constantly.

</details>

**Speaker 11**: 我们也用它来做文档。它给我们的文档带来了色彩和活力，同时遵循我们的品牌。当然，我们也用它来制作像这样的视频。你现在看到的就是HTML和CSS。这完全是开发者的东西。几乎每件事，只要加上一点结构和一点色彩，都会变得更好。纯文本是一种选择，通常是出于方便的选择，但如果你真的想创造一些有用的东西，它通常是错误的选择。

<details>
<summary>Original English</summary>

**Speaker 11**: We use it for our docs, too. It gives our docs color and vibrancy all while following our brand. And of course, we also use it to make videos like this one. What you're watching is just HTML and CSS. It's literally just devs all the way down. Almost everything is better with a little structure and a little bit of color. Plain text is a choice, generally a choice of convenience, but it's usually the wrong one if you're actually trying to create something of use.

</details>

**Speaker 11**: 现在我想暂停一下，指出一个漂亮的幻灯片本身通常一文不值。你仍然需要去获取所有内容，所有实际填充那个幻灯片的东西，对吧？所以，再次强调，我们可以像模型一样思考。如果你只是让模型访问你的数据，比如你的通话记录或你的电子邮件，你可以让模型从头到尾构建幻灯片。让你的代理做所有繁重的工作，而你专注于愿景和故事。这就是Nori Sessions让你能够做到的。我在通勤的地铁上，用手机为我的公司构建了整个董事会演示文稿。这就是我们的Nori，它存在于我们公司的结构中。当然，Nori自带了你需要的一切，让这一切工作起来。所以不用费心重新发明轮子。这就是我的小推销。谢谢聆听。

<details>
<summary>Original English</summary>

**Speaker 11**: Now I do want to take a quick break here and point out that a beautiful deck on its own is generally not worth anything. You still have to go and get all of that content, all of the things that actually populate that deck, right? So again, we can think like the model. If you just give the model access to your data, say your call transcripts or your emails, you can have the model build the deck from end to end. Let your agents do all the grunt work while you focus on vision and story. That's what Nori Sessions lets you do. I've built entire board decks for my company on the subway during my commute. That's our Nori, it lives in the fabric of our company. Of course, Nori ships with everything you need to make this all work. So don't bother reinventing the wheel. That's my little pitch. Thanks for listening.

</details>

**Speaker 11**: 如果你只带走一样东西，那就是这个：停止像用户一样思考，像模型一样思考。给它正确的语言，对于图形，你只需要HTML。

<details>
<summary>Original English</summary>

**Speaker 11**: If you have just one takeaway, it's this: stop thinking like a user, think like the model. Give it the right language, and for graphics, all you need is HTML.

</details>

### 重新构想移动端工作流程

**Speaker 12**: 嗨，大家好。你能感觉到吗？嗨，我叫Reren Nama，一名拥有十四年经验的移动软件工程师，今天我来和大家谈谈关于技术栈的重新构想，以及移动端的工作流程。

<details>
<summary>Original English</summary>

**Speaker 12**: Hi, everyone. Can you feel it? Hi. My name is Reren Nama, a mobile software engineer for the last fourteen years, and I'm here to talk to you today about tech stack reimagining, the mobile workflow.

</details>

**Speaker 12**: 你知道，回到过去，当光标是你用鼠标移动的东西，而AI代理是菲利普·K·迪克书籍或电影里的那种反乌托邦角色时——无论哪个时代——你知道，就在几个月前，那时我们还认为我们仍将使用我们的IDE，只是可能稍微好一点。

<details>
<summary>Original English</summary>

**Speaker 12**: Say, you know, back in the old times, when a cursor was that thing you move with your mouse and AI agents were that dystopian character from Philip K. Dick books or movies, whatever fits your time, you know, just a few months back, back then, when we thought that we will still be using our IDE, just maybe slightly better.

</details>

<!-- chunk 22/54 -->

### 从蒸汽机到电动机：AI时代的效率悖论

**Speaker 12**: 现在我们知道了，我们允许AI做那种“支票式”工程——当我们讨论时，我们称之为Codex、Cursor之类的工具。我们只是告诉它们该做什么，除非是调试或者AI搞不定的事情，否则我们不会用自己的想法。理论上，这应该让我们效率提升十倍，对吧？大家都这么说，对吧？我们真的效率提升十倍了吗？你感觉到了吗？我不知道。我感觉不到我们效率提升了十倍——不是作为单个工程师，不是作为一个团队，也不是作为整个公司。所以为什么呢？为什么我们看不到效率提升十倍的承诺变成现实呢？

<details>
<summary>Original English</summary>

**Speaker 12**: and now we know that we allow this AI to do like check-style engineering when we discuss we'd cloud called Codex, Cursor, whatever. And we just tell them what to do, and we don't use our ideas unless it's for the debugging or something that the agent couldn't figure out. And that in theory, should have made us ten times more productive, right? That's what everybody says, right? Are we ten times more productive? Do you feel it? I know. I can't feel that we are ten times more productive — not as a single engineer, and not as a whole group, and not as the whole company. So why is that? Why don't we see the promise of ten times more productivity come to actual life?

</details>

**Speaker 12**: 你知道，有个故事是这样的：当工厂从蒸汽机换成电动机时，起初他们并没有看到多大的提升。是的，电动机更好，效率更高，但他们没有看到被承诺的十倍、二十倍、三十倍的效率提升。原因在于，他们只是把蒸汽机换成了电动机，但真正的收益是在几年后才出现的——那时他们才明白，这不只是换发动机的问题，而是要改变整个工作流程。你看，以前工厂里只有一个巨大的蒸汽机，所有机器都根据电力消耗和与蒸汽机的距离来排列。所以工作流程不是按照从开始到结束应该有的顺序来组织的，而是根据与中央发动机的远近来设计的。当他们意识到这一点，并且也意识到可以把电动机做得更小、放进每台机器里之后，他们重新布置了工厂，让工作流程顺畅运行——因为现在这变得可能了。真正的收益——二十倍、三十倍的效率提升——才到来。这不只是因为换了发动机，而是因为改变了整个工作流程。

<details>
<summary>Original English</summary>

**Speaker 12**: So you know, they tell the story about how when factories switched from steam engines to electric engines, at first they didn't see that big of a gain. So yeah, the electric engines were better, they were more efficient, but they didn't see that ten times, twenty times, thirty times more effectiveness that they had been promised. And the reason for that was that they only changed the steam engine with the electric engine, but the real gain came some years afterwards when they understood that it's not only about changing the engine, it's about changing the whole workflow. Could you see they used to have like one giant big steam engine in the factory? And all of the machines were rearranged based on the power consumption and the proximity to that steam engine. So it wasn't organized by the workflow that they should have been like from the start to the end of the workflow. No, it was designed by proximity to that central engine. When they realized that, and they also realized that they could take the electric engine, make it smaller and put it inside each machine, and then they arranged the factory to make it work as the workflow should — because now it was made possible. Then the real gain — twenty times, thirty times more productive than they were before — not because of only changing the engine, but of changing the whole workflow.

</details>

### 重新构想AI时代的工作流程

**Speaker 0**: 这正是我今天想和你们讨论的。让我们思考一下，如何利用AI让以前不可能的事情变得可能，从而改变工作流程，实现十倍、二十倍的效率提升。让我们看看当前的工作流程：产品经理有了想法，他们与设计师迭代，与用户体验迭代，与开发迭代，然后又回到设计师那里，再与QA迭代，再回到开发那里。也许经过所有这些迭代之后，你才能把东西上线。刚才那个重复的词是什么？出现了那么多次——对，迭代。这很成问题，因为迭代制造了摩擦。每一次迭代都制造了上下文切换，这又产生了需要进行的沟通、需要完成的同步。而AI并没有消除所有这些——AI加速了编码，但没有消除摩擦，没有消除迭代。为什么呢？

<details>
<summary>Original English</summary>

**Speaker 0**: And that is what I want to talk to you about today. Let's think how we make things that were very possible before possible now, and we can change the workflow and then become ten times, twenty times more productive to do that. Let's look at the current workflows. The PM has an idea. They iterate with the designers, they iterate with the UX, they iterate with the dev, they iterate then back with the designer, then they iterate with the QA, and they iterate back with the dev. And maybe after all those iterations, maybe you have something in production. So what was that word that was repeating? So many times — yeah, iteration. And this is a problem because iteration creates friction. Each iteration creates context, which creates communication that needed to be done, synchronization that needed to be done. And AI didn't eliminate all of that. AI sped up code, but didn't eliminate the friction. It didn't eliminate the iteration. Why is that?

</details>

**Speaker 0**: 那么让我们重新想象一下我们能做什么。请耐心听我一会儿。如果我们不用一个工具做设计、另一个做测试、另一个写代码、再另一个做发布，会怎样？如果我们能用一个工具、一个代码库呢？如果我们不在Figma上设计，然后把设计文档发给开发者让他们想办法把设计变成现实，而是让设计师直接在代码上设计，然后给开发者发一个PR呢？如果QA可以直接与AI代理迭代，只需拿到一个链接和他们的模拟器，就能告诉代理要测试什么、要注意什么，如果发现问题就告诉它要修复什么？如果我们能让开发工作流程直接在代码上运行呢？如果上帝是我们中的一员呢？不，抱歉，我有点跑题了。

<details>
<summary>Original English</summary>

**Speaker 0**: So let us reimagine what we can do. Bear with me for a moment. What if, what if, what if instead of using one tool for designing, another one for testing, another one for coding, and then another one for releasing — what if we could use one tool, one code base? What if, instead of designing on Figma, then sending a design doc to developer in order for them to figure out how to bring those designs alive — what if designers could actually design on code and then send the developer a PR? What if QA could iterate with the agent itself, just getting a link with their simulator, and they can tell the agent exactly what to test, what to be cautious of, and if they find something, exactly what to fix? What if we could make the dev workflow work on the code itself? What if God was one of us? No, sorry, I got carried away there.

</details>

**Speaker 0**: 你可能在问，我们怎么能做到这一切？一种方法是让每个人都下载Xcode和Android Studio，教设计师、产品经理和QA如何构建、如何在模拟器上测试，然后用200GB的存储空间和大量内存塞满他们的笔记本电脑。这是一种方法。但我猜大多数人会拒绝这个想法——而且理由充分。所以我们可以用另一种方法。也许我们把它放在CI里，对吧？让AI代理与CI迭代，这样他们就不需要下载Android Studio、Xcode和所有东西了。但你知道CI构建需要20到40分钟，我们能让代理等40分钟，只是为了知道它推送的iOS代码实际上构建失败了吗？那还有什么办法呢？引入云沙箱。云沙箱这个概念已经存在很多年了，只是还没有用于移动开发。使用云沙箱，你可以告诉代理：这里有一个CI，去和CI对话，启动一个只为此迭代运行的小型虚拟机。虚拟机在30秒或更短时间内启动，进行构建，在云端的浏览器中显示模拟器——Codex、Cursor，随便什么。然后他们可以迭代，告诉它把那个按钮改回去，测试一些东西，修改代码。他们推送并打开一个PR，设计师可以在代码上工作，完成后给开发者发一个PR。开发者进行一些迭代——运行一个、两个、三个不同的虚拟机并行工作。他们发送PR进行审查。QA可以从那里接手，告诉代理要测试什么、要修复什么。从那里，它直接进入应用商店进行审核。

<details>
<summary>Original English</summary>

**Speaker 0**: And you're probably asking, how can we do all of that? One way would be to tell everyone to just download their Xcode and their Android Studio and teach designers, and PM, and QA how to build and how to test on simulators, and bloat their laptops with the 200GB of storage and whatever they do to their memory. That's one way. But let me guess that most of them would reject that idea — and for good purposes. So we can make another way. Maybe we just put it in our CI, right? So we let the agent iterate with the CI, so they don't have to download Android Studio, Xcode, and everything. But you actually know that CI builds take between 20 to 40 minutes, and we can actually let our agent wait for 40 minutes just to understand that the iOS code that it pushed actually failed to build. So what else? What can we use? Introducing cloud sandboxes. Cloud sandboxes are actually a concept that has been around already for many years, just not for mobile development yet. Using cloud sandboxes, you can tell the agent: here's a CI, talk to the CI, spin up a small VM that runs only for this iteration. The VM boots up in 30 seconds or less, make the build, show them a simulator under a browser in the cloud — Codex, Cursor, whatever. And then they can iterate over it, tell it to change that button, go back and test something, and change the code. And they push and open up a PR, and then the designer can work on code, send a PR to the developer. After they're done, developers make some iterations — run one, two, three different VMs to run in parallel. They send the PR for review. QA can take it from there and tell the agent exactly what to test and what to fix. And from there, it goes straight to the stores for review.

</details>

**Speaker 0**: 让我们看看它应该如何工作。想象你看到这个屏幕。想象你在Cursor里面，例如。你左边有聊天界面，右边有实际的应用程序。设计师正在与代理迭代，告诉它他们想要什么、想要改变什么，然后立即在屏幕上看到变化。构建时间更快了——它在云端和预览中。构建时间更快了。然后迭代不是与开发者进行，而是与代理在笔记本电脑上进行，无需安装Xcode或Android Studio。一旦完成，他们可以告诉代理获取代码、打开PR并发送给开发者。这个工作流程才是让我们效率提升十倍的原因——不仅仅是因为使用了AI，而是因为使用AI来改变工作流程。想象一下，消除我们在旧时代习以为常的所有摩擦——这就是我们如何变得效率提升十倍的方法。

<details>
<summary>Original English</summary>

**Speaker 0**: So let's see how it should work. So imagine you see this screen. Imagine you're inside Cursor, for example. You have a chat interface to your left, you have the actual app to your right. The designer is iterating with the agent, telling it exactly what they want them to do, what they want to change, and see the changes immediately on the screen. Build time is faster — it's on the cloud and preview. Build time is faster. Then the iteration is not with the developer, but with the agent under the laptop without the need to install Xcode or Android Studio. And once they're done, they can tell the agent to take that code, open up a PR, and send it to the developer. This workflow is what makes us ten times more productive — not only because of using AI, but because of using AI to change the workflow. Imagine it and remove all that friction that we took for granted in the old times — that is how we become ten times more productive.

</details>

**Speaker 1**: 谢谢。

<details>
<summary>Original English</summary>

**Speaker 1**: Thank you.

</details>

### 一个学会记忆的工厂

**Speaker 2**: 好的。我想讲一个关于一个工厂的故事，这个工厂教会了自己如何记忆。大家好，我是Rushup。我经营着一家名为MachineCraft的100人工厂，在北爱尔兰……蒸汽？不，我是说预算。这些都没有。不知怎么的，我们最终构建了36个AI代理，运行从创意到市场的整个流程。我觉得这仍然有点荒谬。让我告诉你这是怎么发生的，以及为什么你也可以做同样的事情。

<details>
<summary>Original English</summary>

**Speaker 2**: Okay. I want to tell a story about a factory that taught itself how to remember. Hi, I'm Rushup. I ran MachineCraft — a one hundred person factory in Northern Ireland. Steam? No, I'm a budget. None of that. And somehow, we ended up building 36 AI agents that run an end-to-end go-to-market. I think that's still a little ridiculous. Let me show you how it happened and why you can do the same thing.

</details>

**Speaker 2**: 从外面看我们公司，它看起来像是机器和金属。但真正的公司——真正重要的部分——在于机器里的知识：客户是谁，我们在2019年给他们报了什么价，为什么那台机器需要那个奇怪的定制零件。三代以来，所有这些知识只存在于三个大脑里。最初是我祖父的，然后是我父亲的，现在是我的——这真是一种经营公司的可怕方式。当你仔细想想，很多人加入过我们，也有人离开过我们，这个旋转门从未停止。每一次有人走出去，我们大脑的一部分就跟着他们走了出去。我们不害怕竞争对手。我们害怕的是遗忘——或者某天醒来发现整个公司都……（话未说完）

<details>
<summary>Original English</summary>

**Speaker 2**: So here's the thing about our company from the outside, it looks like machines and metal. But the actual company — the part that matters — is in the machines: the knowledge of who the customer is, what we quoted them in 2019, why that one machine needed that weird custom piece. And for three generations, all of that lived in exactly three brains. Initially, my grandfather's, then my father's, and now mine — which is a genuinely terrifying way to run a company. When you sit with it, a lot of people have joined us. People have left us. That revolving door never stopped. And every single time, someone walked out, a chunk of our brain walked out with them. We weren't scared of the competitors. We were scared of forgetting — or waking up one day and realizing the whole company...

</details>

**Speaker 1**: 哎。

<details>
<summary>Original English</summary>

**Speaker 1**: Ah.

</details>

### 从PowerPoint开始的编程之路

**Speaker 4**: 很高兴来到这里。今天和我一起的是Gergely Orosz，《实用主义工程师》的作者。我很高兴能与Simon Arksson聊天，他是Turbo Puffer的创始人兼CEO，一位非常技术型的CEO。我们将进行一场相当技术性的讨论。但在我们进入正题之前，Simon，我想问你，你是如何通过PowerPoint开始接触计算机的？

<details>
<summary>Original English</summary>

**Speaker 4**: It's great to be here. And today, with me here, is Gergely Orosz, author of The Pragmatic Engineer. And I'm excited to have a chat with Simon Arksson, a founder CEO of Turbo Puffer, a very technical CEO, and we're going to have a pretty technical discussion. But before we jump into it, Simon, I wanted to ask: where did you follow up with computers through PowerPoint?

</details>

**Speaker 3**: PowerPoint？我不知道你们是否知道这个，但在PowerPoint里——你可能知道——你可以制作图表之类的东西，当你点击它们时，它们会转到另一张幻灯片，这很快就变得图灵完备了，对吧？你可以创建非常复杂、错综复杂的游戏。然后在某个时候，你通过Microsoft Office套件，发现了FrontPage——你还记得FrontPage吗？

<details>
<summary>Original English</summary>

**Speaker 3**: PowerPoint? I don't know if any of you know this, but in PowerPoint — you probably know this — in PowerPoint, right, you can make diagrams and stuff, and when you click them they go to another slide, and that becomes Turing complete real quick, right? You can sort of, you know, create very complicated, convoluted games. And at some point, you know, you make your way through the Microsoft Office suite, and you discover FrontPage — you remember FrontPage?

</details>

**Speaker 4**: 我记得FrontPage。它本应消除对所有前端开发人员的需求——没错。

<details>
<summary>Original English</summary>

**Speaker 4**: I remember FrontPage. It was supposed to eliminate the need for all front-end developers — exactly.

</details>

**Speaker 3**: 而且它只在Internet Explorer中能用。

<details>
<summary>Original English</summary>

**Speaker 3**: And it only worked in Internet Explorer.

</details>

<!-- chunk 23/54 -->

### 从心碎到编程：自学之路

**Speaker 3**: 我记得有一次心碎的经历。有一天，有人在 Firefox 里打开了我创建的一个网站，结果页面布局全乱了。后来有一天，我不小心在 FrontPage 里点了一下 HTML 那个东西，它显示出了所有我根本看不懂的内容。于是我就开始研究它，上网找一些小代码片段，加进去就能让光标改变，还能实现各种不同的效果。然后事情就慢慢升级了，接着你升级到了 Dreamweaver。现在你开始写代码了。然后你就会想，嗯，怎么让页面动态起来呢？你学 PHP？对我来说，我把互联网上丹麦语的编程建议都看遍了。我当时大概十一二岁。然后我就沉迷于《魔兽世界》整整四年，但这让我的英语变得非常好。

<details>
<summary>Original English</summary>

**Speaker 3**: I remember a heartbreak. I had one day when someone opened a website I created in Firefox, and it just is all over the place. And then one day, I accidentally clicked the HTML thing in FrontPage, and it just showed all of this stuff that I couldn't make sense of. And it just started looking at it and then going online and finding little snippets that you could add in to make the cursor change in all of these different different different things. Then then just sort of escalate from there there, then you upgrade to Dreamweaver. And now you're coding. And then you're like, well, how do you make the pages dynamically, you learn PHP? And then for me, I exhausted the internet on Danish language programming advice. And I was I was around eleven or twelve. And so I just know know when got addicted to World of Warcraft for four years, but that gets you really really good at English.

</details>

**Speaker 4**: 所以你算是开始黑客式地深入学习了，按理说更符合逻辑的做法是，你知道，去大学里系统地学习这些知识，但你并没有这么做，对吧？

<details>
<summary>Original English</summary>

**Speaker 4**: So you kind of start hacking get into deeper and a logical step would have been to just, you know, go to university and learn properly about this, but that's not what you did did you?

</details>

**Speaker 3**: 我的意思是，我就是开始……我通过玩电子游戏学会了英语。然后，你知道，现在互联网这个巨大的宝库对我来说会非常有趣，因为那些只跟我说丹麦语的算法，你就不会遇到那种瓶颈。所以那会非常有趣。也许我的编程会学得更好，那也不错。然后，是的，我在高中期间就开始接一些零活之类的。嗯，后来我接触到了一个叫国际信息学奥林匹克竞赛的东西。有这么一个比赛。是的，啊，我当时有一个网友，她住在澳大利亚，她是澳大利亚队的成员。她告诉我丹麦可能也有类似的队伍，但我之前从未听说过。于是我找到了一个有点神秘的网站，提交了申请，然后解决了一些编程问题，这些问题和我之前解决的 HTML 和 PHP 问题看起来非常不同。这就像是算法类的题目，确切地说，这并非你实际会遇到的那种问题。但我认为它能说明你可能遇到的那类问题，你可以想象一下。好吧，这里有 N 辆卡车。这里有 M 个包裹。这些包裹有这些尺寸，告诉我哪些包裹应该放在哪辆卡车上，然后做一些最优化的安排。这是一个 NP 完全问题。你无法完美解决它，但你可以参与竞争，而比赛中的其他人也都在尽力做到最好。就是这类问题，对吧？是的。所以我在高中时就开始做这个，同时也在工作，嗯，我开始……然后 Shopify 就找到了我，当时我还在上高中。

<details>
<summary>Original English</summary>

**Speaker 3**: I mean, I just I started just I mean, you then I learned video games that I learned English. And then you know, this, like massive arsenal of the web, I now would be very interesting because the algorithms who just speak Danish to me, and you could just you wouldn't have hit the wall like idea. So that would have been very interesting. Maybe I would been better at programming that would have been nice. And then yeah, then I just started picking up jobs and things like that throughout high high school when I was in in high school. Well, well, I got exposed to thing called the International Olympiad in Informatics. There is this thing. Yeah ah, and I had I had an internet friend, and she lived in Australia, and she was on the Australian team, and she told out there's probably something for the Danish team as well, but I'd never I'd never heard about it before. And so I founded on something like little mysterious website and then applied and then solve these programming problems that look very different from the html and php things that I solved until it was. It's like the algorithmic ish programs exactly sort of like this is not actually the kind of problem you would see there. But I think it illustrates about the the kind of problem that you might get right is you can imagine something. I okay, here's like N trucks. Here's M packages. Do M packages have these dimensions give me which trucks which packages should be in right, and then do something optimal. That's an NP complete problem. You can't solve that, but you could compete, but everyone else in the competition of doing the best thing. So these kinds of problems, right? Yeah. And so I started doing that in high school was working um I was working as well for I started. um and then I just Shopify found me while I was still in high school,

</details>

**Speaker 4**: 整个 Shopify 找到你的过程，是因为你的开源贡献吗？还是其他什么原因？

<details>
<summary>Original English</summary>

**Speaker 4**: And the whole I Shopify found me was it through your open source contributions. Was it? Was it something else?

</details>

**Speaker 3**: 是因为我写了一篇文章，当时我摔了我的 iPhone。你知道，那时候 iPhone 很多问题。曾经有那么一段时间，你摔了 iPhone，你就知道屏幕完蛋了。现在这种情况不常发生了，屏幕质量好多了。但在那时，摔一次就坏了，没法用了。所以我换回了一个老款的诺基亚砖头机。那是在 2013 年，我当时并没有真正意识到智能手机的所有负面影响。于是我写了篇文章，大意是“哦，我的天，我开始给别人打电话了，我的方向感也回来了”。我写了篇关于这个的文章。这篇文章短暂地登上了 Hacker News，然后《纽约时报》决定报道它。不会吧，真的。所以带来了巨大的流量。然后 Shopify 的招聘人员把这些信息拼凑起来，和我通了电话。嗯，我觉得他们当时没意识到我还在上高中。但通话很愉快，他们邀请我去加拿大渥太华。我完全不知道加拿大渥太华是什么地方。我记得邮件里好像写了类似“渥太华是什么？”我完全没概念。于是我去了那里，走进那栋大楼，感觉……我参加了面试，然后说我得先完成高中学业。之后，嗯，我搬到了加拿大，嗯，在 2013 年入职了。

<details>
<summary>Original English</summary>

**Speaker 3**: It was because I had written an article where I had I drop my iPhone. And I had, you know, iPhone is a lot like there. There used used to be a time and ever you drop your iPhone. And you just knew it was over for the screen. It doesn't really happened as much much anymore. Like screens have gotten a lot better. But back then it was like get one drop, and it was dead, and it just it couldn't use it anymore. And so I went back to one of these old Nokia brick phone. And this was back in 2013, and doesn't really realize all the pernicious effects of smartphones at the time. And so I wrote this article about how oh my god, I'm am like calling people. And I have my sense of direction back back and I wrote an article about it. And this article it went on Hacker News briefly, and then um New York Times decided to feature it no way yeah. And so a lot of traffic was driven to it. And then and I had Shopify recruiter put it all together. And um and I had a call with them. And then I don't think they realized that I was still in high school. But um but I had a great call with them. They invited me on site to Ottawa Canada. um I had no idea what Ottawa Canada is. I think the email said something like what's an Ottawa and no idea. um And so I went there and it was like walked into the building, and it was just a just felt. And and so I I interviewed with them. And then said what I got to finish high school. And then um and then I move to Canada um and to I it up up. Yeah, in 2013.

</details>

**Speaker 4**: 是的，我觉得这算是一个很合理的借口，让你完全不用考虑上大学的事了。但你当时有没有想过这个问题？

<details>
<summary>Original English</summary>

**Speaker 4**: Yeah, I think that's that's a like legit excuse for like not even worrying about college and a university. But did did across your mind,

</details>

**Speaker 3**: 确实想过。我以为我只是休学一年。我以为，好吧，我去 Shopify 工作一年，然后可能会回去上大学。但我当时，哎呀，我那时非常没有安全感，因为我没有学过计算机科学。我唯一的接触就是信息学奥林匹克竞赛，那算是一个很好的计算机科学速成课。至少它教会了我，你可以坐下来读一篇论文，只要花足够的时间，就能搞明白。所以我反复这样做。在 Shopify 的第一年，每次我听到一个我不懂的东西，我就把它记在一张纸上，然后回家。那天晚上，我就会去阅读相关资料，因为我感到不安，觉得，嗯，如果有人提到 TCP，他们肯定确切知道三次握手里有什么，以及 TLS 是如何在其上建立的。他们还研究过 Wireshark 和所有那些东西。我不认为这是真的，但我当时是那么想的。所以我对我遇到的每一件事都这么做。嗯，那真是一个很好的速成课。然后很快，事情就变得很清楚了，嗯，我只想继续做这件事。我不想去别的地方，然后再回来做这个，因为我感觉我已经找到了我想做的事。所以。

<details>
<summary>Original English</summary>

**Speaker 3**: It did I thought I was going. I thought I I was doing a gap year I thought I was like, okay. I'm going to go work at Shopify for a year. And then I'll probably go back and look do, but I was just 哎呀, I was very insecure the time of of the fact that I hadn't studied computer science. And my only exposure had been all the IOI competition was a pretty good crash course in a lot of computer science. And if nothing else it had really taught me that you can just sit down and read a paper and just figured it out if you spent enough time on it. So I did I did that repeatedly. And in my first year year at Shopify, I just every time I heard something that I didn't know what was I noted it down in piece paper, and then I went home. And then that evening, I would just read about it because I felt insecure that, like well, someone mention she is mentions like TCP, surely they know exactly what's in the three way handshake and how TLS is like layered on top. And they've looked at Wireshark in all of that. I don't think that's true, but that's what I thought no. So I going to did that for everything that I encountered. Well, I was really good crash course. And then very quickly, it became clear that well, I just want to continue doing this. I don't want to go go somewhere else and and come back to this, because I felt like I already found what I wanted to do. So.

</details>

**Speaker 4**: 听起来这很大程度上是因为你内心有这种非常非常强烈的不安全感，当时你还很年轻，没有其他人拥有的教育背景。而在公司内部，即使在当时，甚至现在，Shopify 都在做很前沿、很尖端的东西，对吧？他们是领先的。所以你只能不断地自学，不断地追赶，深入理解每一个你遇到的概念。你不仅仅是试图了解表面，而是尽可能深入，通过互联网、书籍，无论什么方式。

<details>
<summary>Original English</summary>

**Speaker 4**: Sounds like is a pretty accommodation of like you just having this like very, very national insecurity, then you're young, you know, you don't have the education that everyone else. And and inside company, that's just just dotting pretty like cutting it stuff even at the time and even even else today, right? They there, they're leading. So you just keep self teaching yourself like just catching up and go and let do understand that you just went deep in every concept that you understand. You didn't just just try to understand surface level, but like go as deep as you can search on the internet by books, whatever that is,

</details>

**Speaker 3**: 我觉得就是这样。我只是想不断学习计算机是如何工作的。我认为这是我现在面试工程师时会寻找的特质，就是你无法控制自己，总想一层层地剥开事物的本质。对我来说，这最终让我走到了基础设施层，因为，你知道，在 Shopify，我总是被吸引到最底层。我本来在产品端工作，午餐时我会坐在基础设施团队旁边，但我就是控制不住自己。我太想了解他们说的反向代理是什么了。我当时想，为什么是“反向”的？我现在还是回答不了这个问题。

<details>
<summary>Original English</summary>

**Speaker 3**: I think it was just it. I just wanted to keep learning how computers work. and i think that this is something that i now look for when we interview engineers is that you just you can't help yourself, but trying to peel back the layers. And for me, that ended up with the infrastructure layer because was, you know, always process to the metal at Shopify. And i would just the set next to to at lunch because i was working on the on the product side, but it just i couldn't help myself. i was so i just wanted help learn what it was when they're talking about a reverse proxy. i'm like, why is it reverse? i still can't answer that.

</details>

**Speaker 4**: 我是说，好吧，

<details>
<summary>Original English</summary>

**Speaker 4**: I mean, okay,

</details>

**Speaker 3**: 你知道，

<details>
<summary>Original English</summary>

**Speaker 3**: you know,

</details>

**Speaker 4**: 嗯，

<details>
<summary>Original English</summary>

**Speaker 4**: well,

</details>

**Speaker 3**: 什么算是“反向”呢？因为它是个代理，对吧？我不知道，这就像倒排索引，什么算是“倒排”呢？这名字起得真糟糕。

<details>
<summary>Original English</summary>

**Speaker 3**: what's in reverse because it's proxy, right? I don't I don't know it's like an inverted index like what's inverted. It's like it's a terrible name anyway.

</details>

**Speaker 4**: 我是说，这总比你去查 NAT 表要好一些。所以有些东西就是这样。但是，在 Shopify，你遇到的那些持久而艰难的挑战是什么？比如那些宕机事故，那些定义了你、当时也很有趣或值得学习，但在其他地方很难获得的经历？

<details>
<summary>Original English</summary>

**Speaker 4**: I mean, it's still better one when you get to NAT NAT tables to look up. So some of those things like some of that. But I ar, I hear there's some like weird names with this. But at Shopify, what were some of the kind of like hard enduring challenges that use enduring challenges outages like like learning that kind of defined you that we're really also fun at the time or interesting to learn, but it would have been hard to get it elsewhere.

</details>

**Speaker 3**: 是的。所以我认为，你知道，在 2010 年代，有很多 SaaS 公司发展得非常快。我感到非常幸运能近距离目睹这一切。于是我最终加入了基础设施团队。那是在 2013、2014 年，Docker 刚刚兴起。我们正在将所有东西容器化。每一年，我们都必须应对增长，虽然与今天公司的增长速度相比，我们的速度是几倍、几十倍、几百倍，但这是一家年增长率达到 100%、120%、140% 的公司。所以每年，我们都在为黑色星期五做准备，情况总比前一年更糟。那还是我们购买物理硬件的时代，对吧？我们必须在某个时间点下订单，并基于此做一些预测。Shopify 也必须进行扩展。当你扩展大多数软件时，很多应用层的问题最终都会归结到数据库层。

<details>
<summary>Original English</summary>

**Speaker 3**: Yes. So i think it was, you know, in the 2010s, there's like a bunch of SaaS companies that that scaled really quickly. and i felt so fortunate to have a front row seat to that. and so i ended up on the infrastructure team. and this was back in 2013, 2014 and docker was coming out. and so we were containerizing everything. and we were just every single year. we had to, you know the growth rates, but it's times times times quint in compares into the growth rates of companies today. but it was a company that was growing at you 120 140 percent year over year um and so every year, we were just preparing for a black friday. it was going to be a lot worse than the last. and this is back in the day of we're buying physical hardware, right? we have to like place in order at a particular point in time and do some interpolation based on that. and and Shopify also had to scale. and when you're scaling most software, a lot of the application layer problems end up back at the database layer.

</details>

<!-- chunk 24/54 -->

### 从 Rails 到数据库之间的那一层

**Speaker 3**: 于是我自然而然地就处在了 Rails 和数据库之间的这一层。当时我并没有给数据库本身贡献太多补丁，大部分时间都花在了编排工作上。我们当时在做分片，因为，就像我亲爱的老板阿米洛常说的那样，你没法给写入做缓存。所以总有一个基本点，你不得不超越单个分片。我大概是在那时候加入的，他们做了分片，而且他们觉得他们做成了。他们在黑色星期五前一周进行了切换，这简直令人难以置信，但居然成功了。随后几年，我们致力于进入多个数据中心之类的事情。我们还有一台巨大的、神秘的红色服务器，有 128 GB 内存，这在当时算很多了，今天倒不算什么。没人真正知道里面跑着什么。然后有一天它宕机了，大家都觉得，这太可怕了。因为人们一直把它当作一个 KV 存储来用。于是我们开始把它拆分出来。我们做了所有这些工作，确保如果你访问一个 Shopify 商店，而存储你会话的那个组件宕机了，正确的行为不应该是整个网站都挂掉，但除非你身处一个强制要求这样做的编程环境，否则默认的故障处理不会帮你解决所有问题。所以我们构建了这个矩阵：好的，当这个组件宕机时，这个服务应该这样运作。我发现自己为其中很多情况编写了测试周报。然后我想，好吧，我们不能只是模拟所有这些情况。于是我当时想出了这个主意：哦，我们要做的是，通过 shell 调用 GDB，然后附加到进程里，再关闭数据库用来模拟整个数据库层故障的文件描述符。这有点疯狂。我们从未在 CI 上这样做过，但它确实发现了 Rails 上游的大量问题，比如在连接层处理故障方面。然后我继续创建了一个名为 Toxiproxy 的代理。你们以前听说过这个吗？没有？没有？好吧。Toxiproxy 就像一个七层代理，位于你和数据库之间。基本上就是有这个代理，而 MySQL 什么的并不直接使用这个协议。但你可以在它前面做任何事情，我可以让数据库宕机，让它变慢。随着时间的推移，它还增加了七层功能，比如以这种方式制造一堆故障。你不是在模拟底层驱动，而是在测试驱动及其在高故障情况下的表现。于是，整个这个矩阵就可以在 CI 中实现了。

<details>
<summary>Original English</summary>

**Speaker 3**: and so i just naturally found myself at this layer between rails and the databases. i didn't at the time contribute many patches to the databases themselves, but most of my time was spend orchestrating. so we were doing sharding because, as my my dear boss amillow used to say, you can't cache writes. so there's a fundamental point where you you just you have to move beyond a single shard. i joined around the time, and they did the sharding, and they did it think they did. they cut over a week before black friday, which is mind blowing, and very, but it worked. and then the the subsequent years we worked on things like going into multiple data centers. we also had this big, mysterious red red server that was like, you know, one hundred and twenty eight gigabytes of ram, which was a lot at the time today. it's not that much. and no one really knew what was in it. and then it went down one day, and people like well, that's super terrifying. because people had just been treating as this kv store. and so we started splitting it out. we did all this stuff around making sure that if you if you, if you go visit a shopify store, and the thing that stores your sessions is down, the right behavior is not just for the entire, the right thing be be down, but that's not of a default failure out, right? you're not going to rescue all of that unless you're in a programming language that really forces that. so we did things like build this matrix out of, okay. well, this service when this component is down should act this way. and i find myself writing the test week for a bunch of that. and then i was like, okay, well, we can't just mock all of this. and so i came up with this idea at the time. like oh, what we're going to do is we're just going to shell out to gdb and then into the process and then close the file descriptor that the database uses to simulate through the entire layer that the database fails. that was a little crazy. we never never to do on on CI, but it did uncover a massive amount of issues in rails to be upstream and things like that of round, just like handling failures at the connection layer. so then i moved on to create this proxy called toxiproxy. but you and you heard of this before, no, no, yeah. toxiproxy is it's just like a layer seven proxy that sits in between you and what layer four, but in between you and the database, but then basically have just this this proxy, and then mysql whatever doesn't speak the protocol. but you can you put it before, i can take take database down, make it slow and over time, it also added later, layer seven things of like do a bunch of failures this way. you're not mocking the low level drivers, but you're testing the drivers and their failure heavily as well. so then this entire matrix could be implemented in CI.

</details>

**Speaker 4**: 所以基本上，这个代理就像一个非常薄的中间层，它只是透传。它构建了模拟数据库问题或数据损坏等功能，或者任何你想做的事情。你就在里面做。然后任何构建在它之上的东西都能被测试到。

<details>
<summary>Original English</summary>

**Speaker 4**: so the basically the proxy was just like a really thin layer, which like was passed through. so it built the functionality to like simulate problems of database, or things like data corruption, or whatever you wanted to do. so you just do it in there. and then you can test anything that built on top of it.

</details>

**Speaker 3**: 但，是的，每个人，我称这个代理为 Toxiproxy，它需要处在一个精确的层，就像你做的。比如，Toxiproxy 让 MySQL 宕机，然后你传给它一个 lambda 表达式，描述你想做什么，比如获取这个页面，做一个检查，在 sessions 表宕机的情况下结账。这就在 MySQL 驱动和 Rails 中发现了数十个问题，就像整个生态系统之前都没有为此做过测试，而且在生产环境中很难看到，对吧？因为 MySQL 宕机了，你只是习惯性地把它重启，而不是去想应用程序本可以做什么。

<details>
<summary>Original English</summary>

**Speaker 3**: but but yeah and everyone, i call this proxy toxiproxy it needs to be in a layer exactly you do like, like, like you know, toxiproxy got mysql down, and it passes it a lambda of what you wanted to do, like, get this page do a check, check out whatever with the sessions table down. and this just uncovered tens of issues right in the mysql driver in the rails, like just like none and the ecosystem had been testing for this, and it was very difficult to see this in production, right? because they're mysql down. you're just used to just getting it back up and not like, what could the application actually have done?

</details>

**Speaker 4**: 这很有趣。当然，我们稍后会更多地讨论数据库。但想想我们系统中很多问题，或者说一些最普遍的问题，总是与状态有关。我以前从未将这两者联系起来，我的意思是，状态通常意味着有数据库。如果没有数据库，如果你在服务中持有状态，如果你用 Memcached，你仍然会有问题，你有网络问题，你有数据损坏等等，但它通常更孤立。但基本上，如果我们有状态，通常就有数据库；如果我们有数据库，并且我们可以模拟这些问题，那么突然间你就可以预测很多事情。所以状态的问题在于，很多时候很难提前模拟问题，除非你拥有这样的工具。所以听起来你在这方面取得了相当不错的成功。

<details>
<summary>Original English</summary>

**Speaker 4**: it is interesting. of course, we're going to talk a bit more about database, obviously. but just thinking about how a lot of the problems or some of the most general problems in our systems are always to do with state. and i never connected until now that i mean, state is usually there's a database. if there's no database, if you have state in the services, if you use memcached, you still have problems, you have network problems you have. i don't know, corruption whatever, but it's usually like more isolated. but basically, like if we have state, which typically means databases, if we have databases, and if you can simulate these problems, so suddenly you can, you can like predict a lot of things. so the problem with state often time is it's really hard to simulate problems happening ahead of time, unless you have the tools. so sounds like you were pretty successful with that.

</details>

**Speaker 3**: 是的，据我所知，它至今仍在 Shopify 的 CI 系统中运行。我不知道观众里有没有 Shopify 的人，但我很确定它还在用。我们针对它编写了所有这些测试，以实现所有这些不同的故障条件。结果非常棒。

<details>
<summary>Original English</summary>

**Speaker 3**: yeah, i think to my knowledge it though, running in like the CI system of shopify today. i don't know anyone in the crowd from shopify, but i'm pretty sure that it still does it. and so we wrote all these test against that to implement all of these different failure conditions. and it just yeah, it worked out great.

</details>

### 离开 Shopify 的决定

**Speaker 4**: 所以你在 Shopify 待了八年。让我们从你刚入职开始，就像个间隔年。然后一年又一年，你在什么时候想过离开，为什么？你的决策框架是什么样的？听起来你像是在一个史诗般的旅程上，甚至直到今天。Shopify 做得非常好，可能比你离开时发展得更好，那种增长一直在持续。所以我确信留下来肯定有理由，你本可以留在他们的组织里。

<details>
<summary>Original English</summary>

**Speaker 4**: so you spent eight years until at at shopify. so let's started from like, just a gap year. it just went on a year or the year and another year at what points did you think about leaving and why? and what was your kind of decision framework? it sounds like you were on epic, but not even today. shopify is doing wonderful. it's probably doing even way better than you know that growth kind of kept on. so i'm sure there have been an argument to stay, and you could stay in their organization.

</details>

**Speaker 3**: 是的。所以我在那里待了八年，从 2013 年到 2021 年。我觉得就是到了某个时候，我想看看不一样的东西。我从 18 岁起就在 Shopify 内部了，对吧？我在高中时见过另一家初创公司，如果我想学更多关于计算机的知识，学得更快，也许是时候给我的大脑注入一些新鲜感了。所以我在 21 年离开了。我在基础设施的很多不同部分都工作过，比如缓存。我和我现在的联合创始人 Justin 重新构建了整个 Shopify 的商店前端，它支撑了几乎 100% 的流量，我们在着手 18 个月后就完成了。我们致力于让 Shopify 在多个数据中心运行。我们做了很多数据库扩展项目，比如缓存所有这些不同的东西，对吧？很多可扩展性来自于商家在 Shopify 上发布大量产品，这会带来大量流量。但最终我就这样离开了。当我离开的时候，我并不真正知道自己想做什么。我在 Shopify 时做的项目之一就是这个 Napkin Math 项目。你们见过 Napkin Math 吗？没有。Napkin Math 本质上就是我维护在 GitHub 上的一个表格，上面写着：你能往 DRAM 里推多少带宽？到 S3 的一次往返要花多少钱？需要多长时间？你能往 NVMe SSD 里推多少带宽？你能往一个 EBS 卷里推多少带宽？就是一堆数字，大概有 50 个这样的数字，然后是一个 Ruby 脚本，生成所有这些成本：一 GB 内存要花 2 美元？一 GB S3 要花 2 美分？一 GB 这个要花 10 美分？对吧？现货价格是多少？三年期预留实例的价格是多少？就像有一个巨大的表格，然后为几乎每个单元格制作了闪卡。所以我知道这些数字。这个项目是我在 Shopify 时开始做的，因为我发现自己经常处于这样一个角色：我去评审一个项目，对吧？某个产品团队会说，好的，我们得做这个。我们得构建这个基础设施来支持这个功能。很多时候他们会说，好的，我们对数据库 A 做了基准测试，但基准测试结果不太好。所以我们打算用数据库 B。我非常讨厌基准测试，因为对我来说这不是一个令人满意的答案。这并没有建立我的直觉。你说数据库 A 需要 10 秒才能完成的事情，如果做一下 Napkin Math，它应该只需要 10 毫秒，对吧？如果是一个搜索查询，对吧？就像，好的，你搜索三个词。每个词有这么多匹配的文档。那是这么多兆字节。我们取这些列表的交集。你在多个核心上有每秒 100 GB 的 DRAM 带宽。这应该只需要 10 毫秒。你告诉我基准测试花了 10 秒。我们俩肯定有一个人错了。要么是我的理解有差距，这很有可能，要么是你基准测试做错了。

<details>
<summary>Original English</summary>

**Speaker 3**: yeah. so i spent eight years there from 2013 to 2021. and i think it just came a point where i wanted to see something different. i've been inside of shopify since i was eighteen years old, right? i'd been seen one other start up in high school as like if i want to learn more about computers, more and learn faster, it might be time to inject some novelty into my brain. and so i left in 2021, and i'd worked on so many different parts of the infrastructure like caching. me and justin was now my co-founder rebuilt the entire storefront for shopify, which powers almost a hundred percent of traffic. eighteen months after we embarked on it. we worked on running shopify in multiple data centers. we worked on so many database scaling projects like caching all of these different things, right? a lot of the scalability came from the merchants launching lots of products on shopify, which would force a lot of traffic. but that's that's eventually how i left. and so when i left, i didn't really know what i wanted to do. and so when one of the projects i had, while i was at shopify, was this napkin math project, have you seen this napkin math? no. so napkin math was essentially just a table that i maintained on github of how much bandwidth can you drive to dram. what is a roundtrip to s3 cost? and how long does it take? how much bandwidth can you drive to an nvme ssd? how much bandwidth can you drive to an ebs volume? just a collection of probably there's probably like fifty of these numbers and then a ruby script that generates them all what all these things cost, what is a gigabyte of memory cost two dollars? what is a gigabyte of s3 cost, two cents? what is a gigabyte? what is this cost, ten cents? right? what is it cost on spot? what is it cost on a three year reserved? like what just have a massive table and create flashcards for almost every single cell. so i know of these numbers, and this was a project started to work on at shopify, because i found myself in this role a lot where i was going and review a project, right? so some product team would be like, okay, we got to do. we got to build this thing. so we're got to build this infrastructure to support a feature. and a lot of the times they would say, okay, well, we've gone and benchmarked database a, but the benchmarks are not very good. so we're going to go with database b and i hate benchmarks so much because that's not a satisfying answer to me. it's like this does not build my intuition. database a that you saying takes ten seconds to do. this should take ten milliseconds if you do a napkin math, right if it's a search query, right? it's like okay, you're searching for three terms there. each term has this many documents that match it. that's this many megabytes. we intersect these many, this many lists. you have dram bandwidth on multiple cores of a hundred gigabytes per second. this should take ten milliseconds. you tell me, the benchmark takes ten seconds. one of us is wrong either. there's a gap in my understanding, which is very likely or you have benchmarked the wrong thing.

</details>

<!-- chunk 25/54 -->

### 糟糕的基准测试与数据库设计的思考

**Speaker 3**: 从某些方面来看，原因就在于，比如你跑了一个基准测试，却没意识到你的基准测试是在一百个不同节点上做分布式查询。所以当然，P99 延迟会非常高，非常高，对吧，除非你把它砍掉了，或者做了一些不同的权衡。所以我发现自己反复陷入这样的讨论，人们基于糟糕的基准测试来做基础设施决策。所以我需要一个，需要一个工具进去，然后就说，好吧，我们就在这里做个计算，因为那时我总是在做这些小演示，或者写一些小原型脚本来演示这个问题。但我的论点就是，这是缓存块的样子，这是我们需要访问的页面数，这是渲染一个节点所需的时间，需要一毫秒，你必须访问一千个块，然后返回结果。这就是你查询计划的差异，对吧？比如，MySQL 里是不是有个 bug？我们有没有那种问题？这里的差异是什么？然后我就被那个 bug 缠住了。所以在我离开 Shopif​​y 之后，我写了很多关于这个的文章。我就想，好吧，这个查询应该花多长时间？然后我后来有一个假设，好吧，我的 SQL 每秒能做多少次写入？难道 MySQL 每秒能做的写入次数不应该等于你每秒能做的事情的数量吗？这听起来有点道理，对吧？每次你执行一次写入，你都要同步到磁盘以持久化。那么你每秒能做多少件事？如果一件事需要一毫秒，那你应该每秒做一千次写入。但这似乎不太对，因为数据库每秒能做的写入次数远不止一千，对吧？为什么能做到呢？所以这就是我测试的事情之一。然后我发现，好吧，我那个小 ThinkPad 上的 YK​​O 每秒能处理一万次写入。这怎么可能呢？然后你就会问，这怎么可能呢？因为你会批处理。所以当 fsync 发生时，通常是 4KB，对吧。但这并不直观，实际上我大概花了 2020 到 2024 年这段时间，一直纠结于这个问题，我写了 BPF 追踪之类的东西来做所有这些分析。这花了我很长时间。然后我发现，哦，每次 fsync 的大小都比我预期的要大得多。哦，原来是在批处理。你去看代码，读它。然后你发现某个偏僻的文章，总是来自某个德国小镇，有人写了篇文章，讲的是 B-tree 的某个内部机制以及他们做的一个补丁。感觉整个互联网都运行在巴伐利亚的小镇上。我确信这一点。

<details>
<summary>Original English</summary>

**Speaker 3**: and in some ways, some reasons right is like okay you've done a benchmark. you don't didn't realize that your benchmark is doing a distributed query across a hundred different nodes. and so of course, the p, nine in nine, it's going to be really, really high right, unless you've cut that off, or it made some difference set of tradeoffs. so just found myself in these discussions repeatedly, where people were making infrastructure decisions based on poor benchmarks. and so i needed some, i needed some animal to go in and just be like, like, okay, we just do do calculation here here then then because i was always doing these, like little demos, or like writing little prototype scripts to to demonstrate this. but it was just, i just the argument of here's how a cache block looks. this is how many pages we have to visit. this is what a render node necessity takes. it takes one million second, you have to visit a thousand block, a block and then percent back. and the this is the difference to your query well like this is the query plan. correct? like, is there a bug in MySQL? do we have that desks like what's the discrepancy here? and i just got called with that bug. and so after i left Shopify was just writing a lot of articles about this. i was just like, well, how long this should query take. and then one hypothesis i had at some point, like, okay, well, how many writes per second can my SQL do? well, shouldn't the amount of writes per second? then MySQL do equally amount of things that you can do per second. that sort of make sense, right? every time you do a write. you fsync to persist a disk. so how many things can you do per second? well, one thing takes one millisecond should, you do a thousand write per second. well, that doesn't really match up like think a database can do more than one thousand, right? per second. why can you do that? so that was one of those things where i tested. and like okay, well, my YK​​O on on a little ThinkPad, could do ten thousand write per second. well, how was that possible? and now you're just ask, how was it possible because you batch? so when fsync happens on, usually a 4KB, yeah, right. but it's like that's not intuitive like it's actually i got caught was like, just like, you know, probably some, like twenty twenty to twenty four period, where i got obsessed with this question, where's like you're writing like the BPF traces and all of that to do all of this? this is like took me forever. and you and then i found out that oh, every fsync was like much larger than i would have inferred. like oh, it's batching you go into the code and you read it. and then you found some obscure article by it's always somewhere in like a central German town. that's like written some article about like how some intricacy of B-tree works and a patch that they did to. it's like the entire internet runs on small towns in Bavaria. i'm convinced yeah.

</details>

**Speaker 4**: 然后你决定开始做 Turbular Buffer。

<details>
<summary>Original English</summary>

**Speaker 4**: and then you decided to start Turbular Buffer.

</details>

**Speaker 3**: 是的。

<details>
<summary>Original English</summary>

**Speaker 3**: yeah,

</details>

**Speaker 4**: 你是怎么决定的？你当时知道你想在那里构建什么吗？是更像“我想构建一个数据库”吗？因为你显然对数据库很感兴趣。你在基准测试方面做得非常出色，比如，理论上的极限是什么？你非常熟悉。这很可能让你成为了这个细分领域的专家，然后你怎么又想去搞数据库了？

<details>
<summary>Original English</summary>

**Speaker 4**: how did you decide? did you know what you want to build there? was it more like i wanna build something something? database because you were clearly into databases. you done a an awesome job benchmarking, like, what is the theoretical like limits? you are very familiar. what this probably became like this expert in this niche and how i did you want to go to databases again.

</details>

**Speaker 3**: 我认为是三件事同时出现了。我在 Shopify 做的项目是搜索，而且我做得并不愉快。

<details>
<summary>Original English</summary>

**Speaker 3**: i think it was. there's three things that sort of came to a head. the project that worked on on Shopify was search, and i didn't have a good time.

</details>

**Speaker 4**: 你当时用的是什么？

<details>
<summary>Original English</summary>

**Speaker 4**: what did you use back there?

</details>

**Speaker 3**: 我们不需要提其他数据库公司的名字。但那是其中一家很多不同公司都在用的传统搜索公司。而且很难让它做我想做的事。我当时就觉得，那些涉及到那个数据库的项目，我就是没法让它们达到我想要的性能，而且它没有查询规划器。我搞不清楚为什么它有时候能追踪，有时候完全不行。所以我尽可能多地学习，试图弄明白。我开始修改它的源代码。但我就是没法让它经常追踪成功。维护起来非常困难。所以这件事就一直在我脑海里，我以为我再也不会碰它了。然后第二个因素是 Napkin 项目。因为它让我非常熟悉所有这些 Napkin 数学，知道如果完美利用机器，可能达到什么样的性能。第三个因素是，在做这些事的时候，你知道，离开 Shopify，我在那里待了八年。在那段时间里，我做了这个，我称之为“天使工程”。所以我加入了我朋友的公司。我投资股权，而不是直接投资之类的。因为我想保持参与，我想看看外面还有什么，这也是我离开的原因。然后这个问题一次又一次地出现，对吧？比如 ChatGPT 在 2022 年出现。我当时在和一家公司合作，他们想把大量文档连接到 AI。那时候上下文窗口非常非常小。所以你必须非常快速地读取每个搜索结果。

<details>
<summary>Original English</summary>

**Speaker 3**: i don't we don't need to names ok of other database companies. but was it was one of the like traditional search companies that a lot of different companies run? and it was very difficult to get it to do what i did. and i was just like the projects that touched that database just i couldn't get them to perform at the level, and there's there's no query planner. and like i couldn't figure out why it wasn't there and sometimes it track and then sometimes it really didn't track at all. and so i tried to learn as much as i could to figure out. and i started editing the source code of it. and i was just, i couldn't get it to track very often. it was very difficult to maintain. and so i just that was sort of like in the back of my head, i never thought i would touch that again. then the second ingredient in was the Napkin project. because it sort of just gave me a lot of facility with all of these napkin math numbers of what might be achievable with the machine, if you utilized it perfectly. and the third one was that doing this, you know, leaving Shopify in twenty twenty one have explained eight years there. and doing that time, i did this, i call it angel engineering. so i joined my friend's companies. and i just vested equity instead of just investing or something like that. and because i wanted to have my fingers in, and i wanted to see see what else was out, and that's why i left. and this problem kept coming up again again and it again and again, right? like ChatGPT came out in, twenty twenty two. and i was working with with a company then, and they wanted to connect a bunch documents to AI. and that's when the context windows were very really small. so you had to read every search very quickly.

</details>

**Speaker 4**: 当时只有几千字节。

<details>
<summary>Original English</summary>

**Speaker 4**: it was like a few kilobytes.

</details>

**Speaker 3**: 取决于模型，是几千字节或四KB，非常非常小。所以你必须非常快速地完成搜索，对吧。所以我跟他们合作。我创建了一个小推荐引擎。这个推荐引擎实际上相当不错，比如我发现其中一个联合创始人的妻子怀孕了，是通过我在跑他的数据时得到的推荐，但他当时结婚了，但他被推荐了。是的，我的意思是，就像，啊，我读了，啊，我确实得到了许可。我只是觉得没人会想到它这么好用。然后我就想，好吧，就是这样了。这东西太厉害了。然后我粗略估算了一下为所有人，所有用户，做这件事的成本。这家公司叫 Readwise，是一个保存文章稍后阅读的应用。这每月要花掉六千美元。而这是一家初创公司，一家自力更生的加拿大公司。他们当时在所有其他基础设施上总共每月花费大约五千美元。所以这从根本上来说，在一家公司里行不通。如果你在做投资，你必须在你的支出之上实现一些增长，对吧，这根本对不上。所以我们就没有发布它。然后我转而去做调优 PostgreSQL 的 autovacuum 之类的事情，这是个不错的消遣。然后我就一直忍不住想，为什么存储所有这些我们用于推荐的向量会这么贵。然后有一天我做了 Napkin 数学。我想，我们能不能直接用 S3，做一些聚类，然后以某种方式组织文件。也许你可以构建那个东西。然后有一天，我就想，去他的，我干了。然后坐下来开始写代码。我花了 2023 年整个夏天，把头往墙上撞，试图找到一种方法，能让我得到我想要的延迟，因为 S3 的带宽很好，但延迟……

<details>
<summary>Original English</summary>

**Speaker 3**: it was a kilobytes or 4KB. depending on a model was very, very small. so you had to reach for search, very quickly right now. and, so i work with them. and i was i was i create a little recommendation engine. and the recommendation engine was actually quite good, like i found out that one of the cofounders wife was pregnant through the recommendations that i was getting when was running his feed, but but was was was wed, but he was recommended. yeah, i mean, it was just like ah i was reading like ah i did get permission. i just like i don't get anyone expected to be good enough. and just like, okay, it's this. this thing is just king, and then i ran the back of the envelope math on what it would cost to do this for everyone. like all the users. this is a company called Readwise is like articles that you save and then and insert later. and it was going to cost six grand a month. and this was a company. it's a bootstrap canadian company. they spent about five at the time they were spending five, five a month on all the other infrastructure combined. so just it didn't fundamentally in a company. if you're doing an investment, you have to to run some growth margin on top of whatever you're paying right, it just didn't line up um and so we just didn't ship it. and i worked on, i'd know tuned to autovacuum on PostgreSQL or something like that, which is a good past time. and then i just just couldn't stop thinking about why i was so expensive to store all of these vectors that we were using for the recommendations. and i suddenly did the napkin math day day. i can we just use it out of S3 and do some clustering and then organized the files and just the way. and like maybe you could build that. and then one day, i just gonna said, fuck it and did it. and like sat down and started to like to write it out. and i spent the summer of of twenty three, just hammering my head against the wall, trying to find an approach. that i can get the latency that i wanted um because the bandwidth with S3,

</details>

**Speaker 4**: 延迟是几百毫秒，对吧？

<details>
<summary>Original English</summary>

**Speaker 4**: is it as a really good bandwidth but latency were talking hundreds of milliseconds or right?

</details>

**Speaker 3**: 是的，它的 P99 延迟，对于一个 256KB 或 512KB 的对象，在 S3 上是 200 毫秒，而且你的 P99 也是一样。

<details>
<summary>Original English</summary>

**Speaker 3**: yes, the p ninety nine on it because two fifty six or five twelve kiloby object on S3, um a two hundred milliseconds and and your same p, nine nine.

</details>

**Speaker 4**: 因为当你谈论大规模时，你关心的是 P99。

<details>
<summary>Original English</summary>

**Speaker 4**: because like when you're talking large scale, you wanna care about about p ninety nine,

</details>

**Speaker 3**: 对。

<details>
<summary>Original English</summary>

**Speaker 3**: right?

</details>

**Speaker 4**: 想想看，当你谈论的不是 P50。

<details>
<summary>Original English</summary>

**Speaker 4**: think think think when you're not talking my p fifty,

</details>

**Speaker 3**: 当你设计一个系统时，你想要优化 P99。特别是当你在 S3 上设计一个系统时，通常每一毫秒，你处理的不是一个请求，而是很多请求，对吧？

<details>
<summary>Original English</summary>

**Speaker 3**: when you're designing a system, you want to optimize for the p ninety nine. and especially because when you're deciding a system on on S3, generally in every mill, second, you're not doing one request, you're often doing lots of request, right?

</details>

**Speaker 4**: 你会遇到 P99 延迟问题。

<details>
<summary>Original English</summary>

**Speaker 4**: you're going to have the p, nine,

</details>

**Speaker 3**: 九，确实如此。所以就像你在 S3 上遍历一棵树，对吧，比如，你拿到树的上层，200 毫秒。你再拿到树的另一层，200 毫秒。你拿到一堆树的叶子节点，又是 200 毫秒。所以总的来说，你需要关注 P99，甚至可能是 P99.9，来正确地设计系统，因为你需要最小化你必须进行的往返次数。

<details>
<summary>Original English</summary>

**Speaker 3**: nine real ick exactly. so it's like if you're navigating a tree on S3, right, it's like kay, you get the upper layer of the tree. two hundred mill. second, you get like another layer of the tree, two hundred mill. second, you get a bunch of leaf of the tree and two hundred, a mill second. so an aggregate, you have like you want to look at the p, ninety nine, probably even the p, ninety nine point nine to design the system properly because you need to minimize the number of roundtrips that you had to make.

</details>

<!-- chunk 26/54 -->

### 从原型到产品：最初的工程决策

**Speaker 3**: 所以我就没有把它画出来，而是尝试了一堆不同的方法。

<details>
<summary>Original English</summary>

**Speaker 3**: so i just didn't sketch that out and try to bunch a different approaches.

</details>

**Speaker 3**: 然后，最终，在2023年7月，我找到了一个似乎可行的方案，然后又重写了大概两次。

<details>
<summary>Original English</summary>

**Speaker 3**: and then and then finally, in july of twenty three, i got something and it seemed to work and then rewrote it probably twice.

</details>

**Speaker 3**: 然后在10月份发布了，就是基于那个夏天的成果，然后在此基础上继续构建。

<details>
<summary>Original English</summary>

**Speaker 3**: and then released in october based on just that summer and then working through it and you built on on top of it.

</details>

**Speaker 4**: 因为我觉得你的能力很强，而且各方面都做得很好，你是怎么让它变快的？

<details>
<summary>Original English</summary>

**Speaker 4**: because guess your ability and all of and just really good, how do you make it fast?

</details>

**Speaker 3**: 一开始我们并没有，或者说我一开始并没有。那时候只有我一个人，这真的只是一个项目，不是一个公司。它只是为了满足我的好奇心。我并没有打算做这个，比如去筹集一千万美元。我当时几乎不知道AVC是什么。我只是觉得我必须做这件事。我非常专注于做这件事，我清楚地知道，如果我不做，别人也会做。那个夏天我完全沉迷其中。所以第一个版本是最简单的东西。我认为自己是一个非常务实的人，我没有陷入细节。我几乎没怎么读相关的文献。我只是大致了解了一下基本概念，然后勉强实现了它，因为如果读太多文献会花太多时间。这是它可能成为的最简单的版本。

<details>
<summary>Original English</summary>

**Speaker 3**: we didn't in the beginning or i didn't in the beginning. it was just me at that time, and it was really like it was a project. it was not a company. it was to satisfy my curiosity. it was like did not set out to do this, like i'm going to go like raise ten million dollars. and i was like, i barely knew what AVC was like. guy was like, i just had to do this thing. and i was so focused on doing it. i'm so clear to me that if i wasn't going to do it, someone else was going to do it. and i just became fully obsessed that summer with it. and so the first version was the simplest possible thing. i think i am a very pragmatic person like i didn't get buried. i barely read like literature. i sort like, you know, read enough. it is that got to the basic idea barely implemented because that would have taken too much time. it was the simplest possible version of what it could be like, really.

</details>

**Speaker 3**: 你必须想象的是，做到这一点最简单的方法是在向量上运行某种聚类算法，你把聚类结果放到文件里。这些文件被命名为 cluster_1、cluster_2、cluster_3 等等。然后你还有另一个文件，里面是这些聚类的中心点。搜索时，你先下载中心点文件，查看中心点，然后下载最接近的几个聚类文件。这里还有一些优化，比如合并一些聚类和文件，主要是为了控制成本和提升性能。基本上就是这样，然后让它能够扩展。这就是第一个版本。

<details>
<summary>Original English</summary>

**Speaker 3**: what you have to imagine is that the simplest way you could do this is you run some clustering algorithm on the vectors, like you put the clusters, and then you put the clusters in files. the files are called cluster one, cluster two, cluster three up. and then you have another file called centroids of the clusters. and then you do the search by downloading centroids, looking at the centroids, and then downloading the closest clusters. there's a few optimizations around merging some clusters that were in files and so on, just to control some costs and some performance. but that basically and then getting that to scale. that was the first version.

</details>

**Speaker 3**: 那么，我们是如何让它变快的呢？嗯，我甚至不需要实现一个缓存层。我就在 S3 前面放了一个 Nginx 反向代理，然后在这个反向代理上做了缓存。我其实知道反向代理是什么，但我到现在还是不知道“反向”具体指什么。不过没关系。这个反向代理，反向的东西。在这个场景下，性能提升靠的就是缓存，对吧？缓存所有 S3 的对象。这又是最简单的方法。因为我只需要把它放在前面，我知道怎么配置 Nginx。我写过很多 Nginx Lua 脚本，比很多人多。Nginx 是一个非常优秀的软件。就在前面加了个缓存。然后我处理缓存失效的方式就是直接调用 xargs 命令，根据 Nginx 的目录结构删除反向代理缓存中的内容。这就是我们发布的产品。它当时就运行在一台单服务器上，用的是 t2.micro 实例。我当时想，好吧，看看有没有人会在意。

<details>
<summary>Original English</summary>

**Speaker 3**: well, i didn't need to implement a caching layer. i just put the reverse proxy in front of s three with nginx, and then had a caching on that reverse proxy. i like, i do know what it is. i just still don't know what the reverse is about. but anyway, the reverse proxy, reverse things. and the performance in this case, um baby. that's what it's about by caching, right? all of the s three objects. again, it was simply that. because like i'm just going to put that in front, i knew how to configure nginx. like i've written more nginx lua than, yeah, a lot of nginx do a very good software. um just had that cache in front. and then the way that i would do things like deleting in the cache was just like shell out to xargs and just removed like things in the cache of reverse proxy, the directory structure on nginx. and that's what we shipped. it was just running on a single server and t2 micro instance. i was like, okay, let's see if anyone gives a shit.

</details>

**Speaker 4**: 是的。到目前为止，我的意思是，这有点像很酷的工程实践，一个很酷的副业项目，包含一堆新颖的想法。我觉得这背后有一些扎实的工程功底。因为当我了解 Turbofer 的时候，我看到他们和 Cursor 的人聊过，关于他们如何构建后端和数据库，如何扩展，以及所有那些迁移。他们告诉我，“哦，我们之前用的是 Postgres，但后来发现不行，就换了别的东西，结果效果很好。他们用了八个月的 Turbofer，这是一个托管的 Postgres 服务，效果很好，这很令人惊讶。”然后他们说，“哦，然后我们换到了这个叫 Turbofer 的东西，效果也很好。”我当时就想，Turbofer 是什么？我觉得我们可能是他们的第一批客户。这一点我从来没想明白。当时 Cursor 已经很有名了。你是怎么认识他们的？他们又是怎么成为你的第一个客户的？

<details>
<summary>Original English</summary>

**Speaker 4**: yes. so so far. i mean, this is kind of like cool engineering and like a cool side project and like a bunch of novel ideas and i don't know, like i think just some solid engineering. how the curse are come into play. because like when i learned about turbo offer, i was saw them with cursor about like how they built there. they're back in their database, how they scaled and tell me all these migrations. and they're telling me like, oh, so we were on postgres, but it didn't know they did something else and postgres it. and we worked out well. they went eight months of turbo offer and which is a managed service, a postgres, and it didn't well and which is very surprising. and they like oh yeah, then we went to this thing, all turbo offer, and they worked well. and i was like what turbo offer, i think oh at turbo offer. i well think that we were around their first customers. and this never computed to me. cursor was already massive about that point. how did you meet the folks? and how they become were the first customer.

</details>

**Speaker 3**: 他们是第一个客户，第一个，第一个。不，嗯，我在 Twitter 上发布之后就建立了这个。我说，我做了这个东西。坦白说，我当时的状态是，“嘿，你们知道吗，我受够了在这个东西上工作。我整个夏天都在做这个。我不知道有没有人在乎。我只想在这个东西上继续工作，如果有人在乎的话。我们再把它发到 Twitter 上吧。它现在运行在 GCP 的某个角落里的一个 t2.micro 实例上。如果有人觉得惊讶，我会把它好好部署到多台机器上。但在此之前，我们就先这样。我们就先这样。”任何真正做过内部数据库工作的人，都不会有，或者说，会有太多的自尊心去发布这样的东西。而我只是，你知道，我做过一些项目。我就像发布一个 SaaS 项目一样发布它。为什么不能像做 SaaS 一样做数据库呢？我不知道。我的想法是，如果有人用它，我们再做适当的部署。我知道如何运行高可用性的软件。但这在当时不是问题。我当时觉得，这非常简单，非常。这是它可能做到的最简单的版本。然后我在 Twitter 上发布了，我说你可以用一美元处理一百万个向量。在那之前，我认为最便宜的可能是一百万个向量要一百美元，而且还得是能用的。嗯，而且我知道它是可靠的，对吧？我知道它有一些不变性。比如，如果你关闭所有虚拟机，数据不会丢失，所有的写入都直接提交到 S3。它拥有今天所有的相同的不变性。然后 Cursor 联系了我。现在认识他们了，我确定当时 Cursor 可能只有几个人，我也认识了他们的创始人。现在我确定，他们某天在餐桌上肯定讨论过，“我们现在拥有的单位经济学行不通，所有向量都在 DRAM 里的方案行不通。为什么没有人构建一个方案，我们可以把正在使用的代码库放到内存里，而其他所有东西都放在对象存储里？我们只需要热加载，这太有道理了，对吧？你打开代码库，几秒钟内它就在内存里了，然后查询速度和任何其他方案一样快。”这太有道理了。

<details>
<summary>Original English</summary>

**Speaker 3**: they were the first customer, the first, the first. no, um build this out after i just launched on on twitter as okay. i build this thing. and frankly, it was like, hey, you know what thing to me is like i am so sick of working on this. i guess, like i've been working on this all summer. i don't know if anyone cares, i only want to work on this. if anyone cares, let's put it on twitter again. single t2 micro instance on a corner somewhere in gcp is like if someone goes surprise, i'll set it up properly on multiple. and like i'll just block on that. but let's just block on that. let's like the MVP of MVP. anyone who's actually worked in the internal on databases would never have had, like would have had too much pride to ship anything like that. um and i'm just you know, i've worked on. i was just releasing it like a saas project. why can't you work on a database like it's saas? i don't know. it's like if anyone uses it, we'll do a proper. i know how to run software with a lot of nines. and but was not not a problem. i was like, it was very, very. it was the simplest version of what it could be. and then i released on twitter. i was that you could do a million vectors for a dollar. and before that, i think the cheapest was maybe hundred dollars per million for something that actually work. yeah, um and i knew it was reliable, right? i knew like i had had these invariants. like if you shut down all the vms, like no data is loss, like all the writes are committed directly to s3. like it has all the same invariant it had today um and cursor reached out and knowing them. now i'm sure at the time the cursor was maybe people and and knowing the founders. now i am sure that they had set at the dinner table one day and were like the unit economics are what we have right now, where all the vectors are in dram are not working. why hasn't one built it? where we can put in memory the actual codebases that are actively being used. we can put in memory and everything else just sit in object storage. and we just hot loaded in, it makes so much sense, right? you open the code base a few seconds, and it's in ram and then the queries are as fast as anything else, it made so much sense.

</details>

**Speaker 3**: 所以，我的意思是，当时他们，如果你看看他们联合创始人早期的推文，他谈到使用历史记录来做 KV 缓存。他们当时就在做这个，即使到现在，几乎也没有人在做，尽管价格很合适。是的。这非常不常见，但我认为这将会发生，对吧？但他们走在了时代的前面。即使是我，我不知道他们是否考虑过自己构建。我认为这很有可能。然后他们找到了 Turbofer，这完美地匹配了他们的需求。再说一次，我不知道这个晚餐对话是否真的发生过，或者这只是他们内部的想法匹配上了。所以我们交换了一堆邮件，然后有些事情就促成了。我当时对 B2B 销售一无所知。现在我喜欢 B2B 销售了。但当时我什么都不知道。我只是想帮助他们，因为他们遇到了一些单位经济学不匹配的问题。所以我就去了 Sempazis Go。我去了加拿大。我去了 Sempazis Go，然后出现在他们的办公室。当我出现在他们办公室时，他们正在讨论一些 Postgres 的问题。

<details>
<summary>Original English</summary>

**Speaker 3**: so i mean, at the time they were, if you look at some of the one of the co founders early tweet, he talks about using history for KV caching. and they did like that, which barely anyone is still doing even though yeah of price. yeah. and it's very, it's very uncommon, and i think it will happen right, but they were ahead of their time, even they i think i don't know there are thinking of building it themselves. i think that's quite likely um and they found turbofer, and it just perfectly pattern matching to that again. i don't know if this dinner conversation happened. or if this was just inside like pattern matched. and so we exchanged a bunch of emails, and then something compelled. i didn't know anything about b to b sales. now i love b to b sales. now i don't know anything. i was just like i just want to help them because they were. they had some unit economics that didn't line up. so i just went to sempazis go. i went in canada. i went to sempazis go, and i showed up the office. and when i showed up the office, they um they were having some postgres problem that they were discussing.

</details>

**Speaker 4**: 是的，一些 Postgres 的问题。

<details>
<summary>Original English</summary>

**Speaker 4**: yeah, the end of several problems.

</details>

**Speaker 3**: 是的，是的，早期的时候。我当时就说，“哦，你们有 PG Analyze 吗？”他们说，“哦，没有，我们赶紧弄一个吧？我们来看看。”结果和 Postgres 的老问题一样，autovacuum 运行得不够频繁。所以他们遇到了所有这些问题，比如索引膨胀之类的。是的，他们应该做索引扫描之类的。所以我们讨论了所有这些，并帮助他们。这就像我的数据库极客本能被激发了。我认为这足以让他们建立信任，觉得，“好吧，如果他懂得如何帮我们解决数据库问题，也许他也知道如何构建一个数据库。”而在这个时候，我还联系了我认为在 Shopify 工作过的最好的工程师，我的联合创始人 Justin 和 Sheeth。她做的第一件事就是移除 Nginx 反向代理缓存，换成了 Falbase 缓存，一个直接的缓存层。

<details>
<summary>Original English</summary>

**Speaker 3**: yes, yeah, early on. and i was like, oh, you guys have PG analyze, and they said, oh, no, we don't and let's let's let's get that going right? let's look at it. and it was the same thing as it always is with postgres, which the autovacuum hadn't run enough. and so they had all of these, like index bloat. yeah, they should be doing index scans and level about. so we were talking about all of that and just helping them. it was like my database geekiness just kicked in. and i think this build enough trust with them that okay. well, maybe if he knows how to help us with the database, maybe he also would know how to build one. and at this time, i also approached i thought was the best engineer who ever worked at shopify, my cofounder justine and she came on. and the first thing that she did was um remove the reverse proxy nginx cache with a falbase cache, just the direct cache layer.

</details>

<!-- chunk 27/54 -->

### 从 Cursor 到 NVIDIA：创业故事与 CPU 短缺

**Speaker 3**: 就像昨天的工作一样顺利。她当时在线，已经开始着手处理了。然后那天晚上，Cursor 那边说，好吧，我们要迁移了。所以在那之后，我们花了一两周的时间把所有东西都迁移了过去。那时候 Cursor 还是一家小公司，对吧？

<details>
<summary>Original English</summary>

**Speaker 3**: great like the yesterday work. and so she was online, she was starting work on it. and um and cursor cursor cursor, then that night was like, okay, well, we're going to migrate. so so migrated everything over the course of a week or two after that, um and cursor was a small company back then, right?

</details>

**Speaker 4**: 是的。而且他们当时正处于大规模快速增长的初期。

<details>
<summary>Original English</summary>

**Speaker 4**: yeah. and they were just in beginning of their massive rapid growth exactly.

</details>

**Speaker 3**: 我告诉他们我会把账单削减百分之九十五。我确实做到了，就像我们刚才看到的那样。他们之前的供应商给他们的最后一张账单，和我们给他们的第一张账单相比，确实低了百分之九十。

<details>
<summary>Original English</summary>

**Speaker 3**: and I told them that i was going to reduce the bill by ninety five percent. and i did like we did just see, and i did we like they came on and their last bill with their previous vendor. and the first bill with us, it was ninety percent lower yeah.

</details>

**Speaker 4**: 你没点名供应商，这很 nice。但我能想象他们和那些供应商谈话时的情景。在 Cursor 的深度对话中，那大概是……是八十……或者具体来说是……嗯。

<details>
<summary>Original English</summary>

**Speaker 4**: you're nice for not naming vendors, but but i can see it as they talks to them. and it's in the deep dialog cursor. it was it was eighty or was or war specifically.

</details>

**Speaker 3**: 所以这不是……这不是在 Postgres 之后发生的。

<details>
<summary>Original English</summary>

**Speaker 3**: so this was this was not this was not postgres now.

</details>

**Speaker 4**: 对，但可能是在那之后不久，对吧？但我们不点名了。不过，他们选择离开是有原因的。他们的可靠性是他们的主要卖点，我确定……但后来 Swallet 告诉我的是，他说，听着，有些事情我们做了，但永远不应该做。他说其中一件事就是，你永远不应该把你的业务押注在一个小初创公司上，而你是他们最大的客户，除了……我很喜欢那个家伙。所以我想这正好说明了，即使在你……对我来说，这个故事告诉我们的是，你可以做一些事情。当你构建高质量的东西并且努力推进时，好事自然会发生，就像 Cursor 这个客户一样。当你是一家初创公司时，有时候，当你有信念的时候，承担一些理性的风险是可以的。在我看来，你通过亲自出现、帮助他们、展示你自己，给了他们这种信念。你就像他们的兄弟，你的……你有八年的 Shopify 经验和你的好奇心。他们可能正是因为这些才承担了风险，而不是因为你是什么大牌供应商，他们可能以前从未这样做过。

<details>
<summary>Original English</summary>

**Speaker 4**: but yeah, but there were the reason they went. there is reliability was their main selling point i'm sure the unit of comments, what would have been there, but he had this was, and then what Swallet told me is, he said, like look like there's a few things that we did. it should never ever do. and he said of one of them, you should never ever bet your business on a tiny startup where you are. there are only our biggest customer except... and is that i love the guy. so i guess it just comes to show that even in your... to me, what this story is shows us is you can do things. and when you build high quality things and you're pushing for things, good things can just come to the customer of cursor. when you're startup, it's okay to take sometimes your rational risks when you have conviction. and it sounds to me that you gave them conviction by showing up in person, by helping them by showing that, you know, yourself, like you, suddenly brother, your your tennis, or eight years of shopify experience in your curiosity. and they probably took risk because of that, not because you were some your dom vendor, they probably never never done that.

</details>

**Speaker 4**: 快进到今天，Turbopuffer 现在规模大多了。你正在做一些很酷的事情，但你的业务非常有趣，因为 CPU 对你来说很重要，对吧？你主要运行在 CPU 上。你昨天告诉我一个故事，说你见到了 Jensen，而 Jensen 真的很想向你推销 GPU。你能跟我讲讲那次会面是怎么进行的吗？

<details>
<summary>Original English</summary>

**Speaker 4**: so the fast forward today, turbopuffer is now a lot bigger. you're working on some cool things, but you have this very interesting business where for you cpu are important, right? you run on mostly cpus, and you told me a story over dinner yesterday that you met jensen and jensen. he really wanted to sell you on gpus. can you tell me how that meeting went?

</details>

**Speaker 3**: 嗯，是的，Jensen Huang，对吧？我以前从未见过 Jensen。我们当时在一个活动上，在 NVIDIA。我们正在做演示，在一个很大的总部，非常令人印象深刻。是的，他们邀请了几家公司去谈谈我们的业务，以及我们如何能与 NVIDIA 合作。我不知道，我那天可能心情有点搞怪。所以我走上台说，嘿，我是 Turbopuffer 的 Sven。是的，如果你对我的名字感到好奇，如果一切都不顺利，我们总能把它改成 Vapes。我当时有点紧张，这就是我说的。

<details>
<summary>Original English</summary>

**Speaker 3**: um yeah, jensen huang, right? yeah, i just i never met. i never never met jensen before, we were at an event and at nvidia. and we're just doing presentations in a big HQ super impressive. yeah, exactly they invited a couple companies to go and talk about our businesses and how we can partner with nvidia. and i don't know, i was like, i think i was in a goofy mood that day. and so i went up on stage. and i said, hey, i'm sven from turbopuffer. yeah, if you're wondering about the name, it's if everything goes south, we can always pivot it into vapes. i was kind of nervous as this is what i said.

</details>

**Speaker 4**: 然后他回你话了？当时房间里是谁？Jensen 是直接……？

<details>
<summary>Original English</summary>

**Speaker 4**: and then and then he said back to what who was in a room as a jensen was a director or it,

</details>

**Speaker 3**: 是 Jensen。然后他好像说，我不知道，他有五十个直接下属还是什么，我知道没有回答，然后是一大堆 NVIDIA 的领导层，对吧？因为你去那里，然后你谈论那个，你找到……合作伙伴更多在一起，对吧？所以我说，是的，我们也有足够的股权可以转型做 Vapes。然后他说，我当时已经很紧张了。他说，从你的幻灯片来看，也许你应该这么做。

<details>
<summary>Original English</summary>

**Speaker 3**: then it was jensen. and then he has like, i don't know, it's it's fifty direct reports or it was like, i know there was no answer, then a bunch of the like nvidia leadership, right? because you go there. and then you talk about that, you find about... the partners are more together, right? and so i said, yeah, this is also plenty of equity that we could have an into vapes. and then he said, i was already nervous. he said, judging by your slide, maybe you should.

</details>

**Speaker 1**: 不，他没有。

<details>
<summary>Original English</summary>

**Speaker 1**: he did not,

</details>

**Speaker 3**: 我不知道该怎么回他。所以我说，嗯，Jensen，你……？他没有回答这个问题。然后团队里的某个人给全公司发了消息：“糟糕的演讲，Sven 刚刚问 Jensen 要不要 Vapes。”然后你知道，这是个很棒的开端，对吧？然后团队之前跟我谈过，说有时候我们要确保不说那个词。

<details>
<summary>Original English</summary>

**Speaker 3**: and i didn't know what to say back to that. so, i said, well, jensen, do you...? he didn't answer the question, and someone on the team wrote to the whole company. terrible poffer simm just asked jensen a few vapes. um and then you know, this is a great start, right? and then the team had sort of talked to me beforehand. like sometimes, we got to make sure we don't say the c word.

</details>

**Speaker 1**: 我们不能说 CPU。

<details>
<summary>Original English</summary>

**Speaker 1**: we can't say cpu.

</details>

**Speaker 3**: 所以我就是忍不住一直说 CPU 有多棒，就像……我们爱 CMD 和……就像有这么多 CPU。很容易就能得到……就像在 CPU 的世界里，你不需要……我想我差点就说出来“我很高兴我不需要 GPU”了，但我就是忍不住一直谈论 CPU，是的。所以 Jensen 对此产生了兴趣。

<details>
<summary>Original English</summary>

**Speaker 3**: so i just couldn't stop talking about how cpu was like amazing. it's so sick like we love CMD and up like like there's so many cpu. there's so easy to get like it's just the right in cpu land like you don't like, i think i stop short of saying. i'm so glad i don't need gpus, but but it was just i just couldn't stop talking about cpu, yeah. and so jensen took an interest in that.

</details>

**Speaker 4**: 所以，好吧，谁知道呢？我敢肯定你可能给他留下了深刻印象。所以也许他把让你用上 GPU 当成了他的使命。但你对 CPU 的看法是什么？你能告诉我吗？你在超大规模云服务商那里看到了什么？你现在在 AWS，你在 GCP，你在 Azure，我想现在……严重的是，存在 GPU 短缺。当我与推理公司交谈时，他们正在构建 AI 应用，他们能得到什么就用什么。你会认为获取 CPU 应该很容易。是吗？

<details>
<summary>Original English</summary>

**Speaker 4**: so okay, who knows? like i'm i'm sure you may you made an impression. so maybe he made it his mission to, like at some point, get you guys onto GPUs. but what is thinking of cpus, can you tell me? but what you're seeing inside of the hyperscalers, the cloud providers you're now in aws, you're in gcp, you're on azure, what i would think now. heavily is there's a GPU shortage. and when i talk with inference companies, they are and and AI apps, they're getting whatever they can get. no would think getting cpus is should be easy. is it?

</details>

**Speaker 3**: 不，不再是了。发生了什么？好吧，跟我们讲讲其中的动态以及你学到了什么？

<details>
<summary>Original English</summary>

**Speaker 3**: no, it's not anymore. what was happening? okay, tell us about the dynamics on the ground and what you've learned?

</details>

**Speaker 3**: 是的。所以我认为 GPU 可能会继续稀缺，我不知道，也许会有一些过剩。我拒绝过多地推测宏观情况。但我认为，随着强化学习成为非常大的一部分工作负载，它需要大量的 CPU。所以那些实验室正在消耗大量的 CPU，因为你需要 CPU 来做，比如，好吧，我们需要教这个模型如何搜索。我们需要教它如何使用 Graph。我们需要教它如何启动 Bash。它需要运行所有这些事情，并从中学习。这需要大量的 CPU。所以我认为强化学习正在消耗大量的 CPU。然后，所有的 Agent 也都在 CPU 上运行，对吧？它们需要在 CPU 上做所有通用的事情。所以随着需求曲线向右移动，并且这变得越来越普遍，这反过来又会反馈到 RL 中，对吧？因为事情变得更普遍了。比如，哦，模型在造船方面不太擅长。我不知道，然后你知道，你不得不建立更多的 RL 环境来做这个。所以我认为这就是我们正在看到的。所以我们处于另一端，需要这些 CPU。我们也需要大量的 NVMe。现在很多这些都绑在 DRAM 上，对吧？比如 GPU 服务器也需要大量的内存。但我认为在 CPU 方面，情况在好转之前会变得更糟。我认为即使是大型公司也在互相争夺资源，甚至我们也在向那些我们与之竞争 CPU 的公司销售产品。这真的非常困难。所以我们想尽办法确保尽快获得这些 CPU。

<details>
<summary>Original English</summary>

**Speaker 3**: yeah. so i think that gpus will probably continue be scarce like, i don't know, maybe there's going to be some surplus. i refuse to speculate too much about the macro, but i think as as RL is becoming a very, very large amount of the workloads that needs a lot of CPU. so the labs are sucking up a lot of CPU because you need CPU to be like, okay, we need to like teach this model, how to how to search. we need to teach it how to use graph. we need to teach it how to boot up bash. it needs to run all these things, things learn from that. that takes a lot of CPU. and so i think RL is consuming a lot of CPU. and then also just all of the agents are running on CPU, right? they need to do all the very general purpose things on CPU. and so as the demand curve is shifting to the right and that becoming more and more applied, and that feeds back into RL, by the way, right, because of things become more applied. like oh, the models are not that good at cat or ship building. i don't know, and then you know, you have to spin up even more, RL environments to do that. so think that's what we're seeing. and so we're on the other end of that needing these CPU. we and a lot of NVMe as well. um and a lot of this right now is tied up in dram, right of where, like you need a lot of also for the GPU servers. um but i would assume that it gets a lot worse before it gets a lot better on the on the CPU side. um and i think even the big companies are fighting among each other right to get cpu and even know we're selling to companies that we also fight for cpu with and against right even. it's it's really difficult. and so you write things to try to make sure to get these cpu as fast possible.

</details>

**Speaker 4**: 是的。昨天晚餐时，你和你的团队在一起，实际上那里有很多我们的客户，很多是 AI 实验室或 AI 初创公司。但其中很多，比如 Reflection，他们的足迹非常非常大。他们告诉我，他们处于一种无法再购买更多 GPU 或 CPU 的境地。他们已经用尽了。他们签了尽可能长的合同。我之前没有意识到，当你超过一个小鱼，成为一个中等规模甚至是大鱼时，云端的竞争会如此激烈。现在，这很有趣。所以现在你甚至在幕后进行着这种可能不那么明显的斗争。

<details>
<summary>Original English</summary>

**Speaker 4**: yeah. and yesterday, i was at dinner that you was with your team, where where actually a bunch of our customers, a bunch of them, our AI labs or AI startups. but a lot of them, one of them, uh, reflection had huge massive footprint. and they were telling me that they're in a situation where they cannot buy more like they bought all of the gpus or cpus. they max out. they have longest contracts that possible, and i didn't realize how competitive it is in the cloud when you go beyond a small fish, like a medium sized or even a large fish. now like it's it's interesting. so now you have this even you're having this kind of fight behind the scenes that is maybe not as visible exactly.

</details>

**Speaker 3**: 我的意思是，你和云服务商合作，对吧？你和他们讨论哪些区域有 CPU，哪些区域正在获得 CPU。这归根结底是电力问题，对吧？比如，好吧，电力在哪里，这通常就是他们会把新 CPU 运往的地方。所以我们必须和我们一些最大的客户在这方面合作。这些都是真实的限制，正在影响到我们。我们非常幸运，因为对我们来说，运行大量的 Turbopuffer 实例非常容易，因为我们只需要几个 CPU、内存和 S3，然后我们就处于一个很好的位置。但是，即使在架构层面，我们也可以做很多改变，试图避免很多这些问题。

<details>
<summary>Original English</summary>

**Speaker 3**: and i mean, you, you work with the clouds, right? you work with them to talk about which regions have have cpu, which regions are getting. it comes down to power right of like, okay. well, where is the power, which is generally where they're going to ship the new cpu. and so we have to work with some of our biggest customers on that. these are real constraints right right that are making their way to us. we're just very fortunate that it's very easy for us to run lots of turbopuffer instances, because all we need are like like a few cpu and the memory, and then s3 and then we're in a good place. but there's lots of change that we can make even into the architecture, but try to protect from a lot of this.

</details>

<!-- chunk 28/54 -->

### 关于机器类型与风险投资的讨论

**Speaker 3**: 现在我宁愿把精力花在其他事情上，但我们非常、非常擅长使用大量不同的技能，对吧？所以我们不需要所有东西都必须是特定的 CPU 或实例类型。我们可以运行许多、许多不同类型的机器类型，在少数几个层面上。

<details>
<summary>Original English</summary>

**Speaker 3**: now i'd rather spend that during effort on other things, but we are very, very good at using a lot of very different skills, right? so we don't need everything to be a particular cpu or instance type. we can run with many, many different types of machine types on a few meaning.

</details>

**Speaker 4**: 这就像一个花哨的名字，用来指代不同的机器类型。

<details>
<summary>Original English</summary>

**Speaker 4**: that's like it's an fancy name for like different different machine types.

</details>

**Speaker 3**: 完全正确。比如，你知道的，feaning 或者 ia g 或者随便他们叫什么。你最喜欢哪个？嗯，我们现在真的很喜欢 GCP 上的 C3。这些机器在我们做了一系列优化之后，性能也非常好。这些真的是很棒的机器类型，我们非常喜欢。还有 GCP 上的 Arm 架构机器，我们也喜欢。但总的来说，我们有很多种选择，而且我们很容易切换。这也是我几个月前决定 ABFCM 的一部分。你必须告诉云提供商你打算用多少，并做出承诺，对吧？云并不像看起来那样无限，而且你规模很小。

<details>
<summary>Original English</summary>

**Speaker 3**: exactly, like you know, feaning that's or ia g or whatever they called, what's your favorite one? um we really like right now, the um C3 on on GCP. um does that for, these or also performing really well now that we've done a done a bunch of um of optimizations to them. um those are really great, great machine types we really like those. and then the arm c forch es as well um on on GCP of we like those. but i think that in general, like when yeah, a bunch, and we very easy shock of a bunch of, but that shop pify. i was also part of deciding i had ABFCM right a few months out. you have to tell the cloud providers, how much you're intending to use do commits on all of that, right? the clouds are not infinite as they seem, and you're small.

</details>

**Speaker 4**: 当然，一方面是这样，比如获得基础设施。另一方面，风险投资也能带来信誉。如果你融资一亿、十亿美元，你的一些客户可能刚融了二十亿。实际上，我昨天还和他们聊过。这给了你信誉，也给了你现金，你可以支付这些东西。嗯，你 Turbopuffer 的具体情况，你和风险投资的关系似乎非常有趣。我从来没听说过你宣布融资，直到可能最近。你能告诉我，你开始做这件事的时候，没怎么考虑除了构建和运营之外的事情吗？你是怎么看待风险投资的？你是怎么看待融资的？因为我觉得你有一个非常新颖和不同的视角，这在硅谷内部很典型。

<details>
<summary>Original English</summary>

**Speaker 4**: and one way, of course, so like get like infrastructure. and and also just like credibility is venture capital. if you raise a hundred hundred million dollars, a billion dollars, some of your customers just raise two billion dollars. actually, i talk with them yesterday, you know, i gives you credibility. you gives you cash, you can pay for this thing. um, your specific turbal profers, your relationship to venture capital seems very interesting. i never heard you announced a ise until maybe just very recently. can you tell me how and you told me that when you start this thing, you didn't think too much outside of just buildings and ooall stuff. how did you think about venture capital? and how do you think about raising because i can i feel you, you have a very freshand different perspective and which which is typical inside of siloammi.

</details>

**Speaker 3**: 是的。所以我认为要理解我对资本的想法，你必须回到 Turbopuffer 的起点，对吧？当时我向 Cursor 承诺，我可以把他们的账单降到每月四万美元。这是基于一些非常粗略的餐巾纸数学计算：如果 Turbopuffer 比他们现有的方案实现得更好，那么成本可以降到这个数。这就是我们发布时的定价，也是我们对 Cursor 的保证。但当时的软件并没有那么好，它很可靠，但非常简单，对吧？这是我核心的工程原则：简单至上。你和我之前聊过，我在公司里看到过很多长期存在的问题，在 Uber 也是长期存在的问题。你会发现，简单几乎总是胜出。

<details>
<summary>Original English</summary>

**Speaker 3**: yeah. so i think to understand my how i think about capital, you have to go back to the the beginning of turgo puffer, right, where i promied cursor that just seen. and i could get their bill to four quay a month. and this was based on some very rough nafkan math on. okay, if turturbpuffer was a better implementation than occurrently than then, it could cost this much. and that's the pricing we ship with, and that's will be guaranteed guaranteed curser. but the suoftwer was not that good, like it was very reliable, but it was very simple, right? that's like a core engineering principle of me. me. it's simplicity above everything. you and i have talk before me, me, how suffered age is well and some of the advantages of seeing um you silong tenteners inside a company, you you at a long tender er, uber at a long, long tener tratrarififiso. you see sisimplicity just almost always wins.

</details>

**Speaker 1**: 在当时，我并不确定这是否是一个风险投资的机会，因为我明白，一旦你拿了风险投资，无论房间里有多少笑脸，每个人都在某种程度上期望你必须在某个时间框架内获得巨大的回报，这对所有相关方都有意义。而所有相关方，包括加拿大的养老基金等等，那是一整条利益链。所以当时，我不知道这是否能成为一个大生意。在最开始的时候，我并不完全清楚。这感觉像是一个非常小众的产品，就是构建这个特定的搜索引擎。这对我来说完全没问题。所以，这没问题。然后我就看着 Cursor 的账单，看着我的 GCP 账单，我们就是从 GCP 起步的。你知道，就像个愚蠢的丹麦人，心里想，好吧，这个数字就应该比那个数字低。是的，差不多就是这样。我想我在旧金山待的时间不够长，因为我觉得这里的钱运作方式有点不一样。仅此而已。

<details>
<summary>Original English</summary>

**Speaker 1**: and at the time, i was not convinced whether this was was venventure skill opportunity, because i understood that if you take venture capital, no matter how many smiles are in the room, everyone is sort of expecting that you have to earn a big return on that on some timthat that makes sense to everyone involved and everyone involved. are you pension funds in canada like that did like it is like a whole stack right of of people that they need to. so at the time that, like you know, i don't know if this could be a builility. i didn't know that in the very, very beginning um it wasn't completely clear to me. it felt like a very nich kind of product right to build this particular search engine. and that was completely fine with me. so you know which it was fine. and so then i just looked at the curser bill. and i look at my GCP bill, which just what we started on and you know was was like you dumb danish person, who is just like, okay, like this number should just be lower than the other number. yeah, that's sort of you know. and it's just i don't think i spend enough time and sanfron csco because i think the money over here, it works a little bit differently. that's just that's all.

</details>

**Speaker 4**: 我知道你做生意的方式是，只要你能盈利，你就没问题，对吧？

<details>
<summary>Original English</summary>

**Speaker 4**: i knew you you're doing business one or one as as long as you're making a profit, you're good right?

</details>

**Speaker 1**: 是的，我没有在开玩笑，也没有夸张，我当时就是这么想的。对我来说，逻辑就是，我们只要不断优化，直到这两个数字大致相等。嗯，也许如果我们能接到一些其他工作负载，我们就可以开始给自己发工资了。但这在当时就是我们的核心理念。嗯，因为我不知道我能不能融到一大笔钱。我不认识任何有钱的人。我没有任何人脉关系。嗯，我是一个彻头彻尾的局外人。我完全是圈子外的，对吧？我在丹麦的奥胡斯长大，然后搬到了加拿大的渥太华。我在加拿大是局外人，在旧金山湾区也是局外人。所以我只是从第一性原理来思考。哦，风险投资，你需要在这个时间线上获得这样的回报。我还不知道我能不能做到。我需要更多数据来决定，因为我想，我有点想继续做这个项目。但如果我必须在某个时间点之前达到某个目标，否则就算失败，那压力就太大了。后来，我遇到了一个2012、2013年时在III（III可能是某个机构或公司）一起共事的人，他叫Borin。他在III时是北马萨诸塞州团队的成员。他非常厉害。他厉害到北马萨诸塞州团队都叫他“神”。我不知道为什么，但那就是他的代号。他非常非常厉害。我真的很想和Borin一起工作，但我雇不起他。他明确说了他需要多少薪水才能生活。你知道，我当时的想法就是，我想构建这个系统，这就是它的成本。但在那个时候，我已经有六个月没拿薪水了，而且我们已经花了几万、几十万美元在GCP和其他东西上。我觉得我们不能再在GCP上这样下去了。后来我在硅谷遇到了一个人，他叫Lucky。我最后给他打了电话，说，嘿，我想在这里学得快一点。我们能融个七十万美元吗？这就是我想融的金额。我想雇两个工程师，干完今年剩下的时间。我自己还得拿薪水。然后再留一点缓冲。这就是我们需要的。如果到年底还没有产品市场匹配，或者这不是个大机会，那我们就不做了，把整个项目关掉。我们会好好清算，然后把剩下的钱全部退还给你。我想那是你第一次听到有人这么说。我当时也跟其他一些VC说了，他们觉得这很可怕。我想对西海岸的人来说，这听起来像是你没什么野心之类的。但对我来说，我只是不知道，我只是来自一个不知道怎么玩这个游戏的地方。我就只是摊开牌来玩，这就是我的看法。所以我们非常清楚我们想这么做。但同时，我们也逐渐明白，我们不想只是继续做这个，然后指望它变大。我们开始建立 conviction，相信它真的能变得非常、非常大。所以我们那么做了，然后雇了Borin。那年年晚些时候公司就开始盈利了。然后我们继续招人。之后，要融更多钱，你需要有理由。融资有六个原因。第一个原因是资助研发。嗯，这就是我们一月份融资的原因，因为我们之前用很多自己的机会成本（比如不拿薪水、自己付账单）来资助研发，但我们想学得更快一点。所以我们雇了Borin和Morgan作为第一批工程师。第二个融资原因是资助增长。你做出了东西，你想让全世界知道，你想花更多钱去做这件事。第三个融资原因是为了创始人的 ego。这是一个非常流行的原因，非常、非常流行，对吧？大数字，大量媒体报道。我认为这是一个非常、非常危险的融资理由。我希望人们能更多地讨论这一点，因为当你这样做的时候，你是在稀释所有员工的股份，你是在为未来的员工设定一个价格和他们的上升空间。对一些人来说，这变成了一场地位游戏。但这不是我们该做的。我们在这里是一起建立一个大生意，这不是融资的理由。

<details>
<summary>Original English</summary>

**Speaker 1**: yes, that was was i'm i'm not kidding in this exaggeration that it was just like that just made sense to me that just even and i were just going to go optimize this until these rutt numbers were roughly equal. um maybe if if we could get some of other workloads, we could start paying ourselves, but that, that was like very much the philosophy at the time. um because i didn't know if i could go raise a bunship of of money. i didn't know anyone who had the money. i didn't have any relationships. um 're annxlual outsider of i was an outside der. i was that was like outside square, right? i grew up in all who's denmark, and i um i dn't move to ottawa canada. it's like i'm an outsider to canada a in canada and outoutsider two anfr's disco. so i was just thinking about this from first principle. oh, h, your eventure capital, you need this return you needed on this timeline. i don't hope i can deliver that yet. i would need more data to decide that because i want ted, i kind of want to keep working on this. and now i have to get to this point for it to not be a failure in in january. then i there's a person that i was at III with in twenty twelve and twenty thirty, and his name is byn, and he was on the northermasasdononly teteam at iri, and he was his. he was really good. he was so good that the north massaony an team called him god. i don't know why, but that was what he went by, and he was yewas very good, good, good rouroup. i really want want to work with borin, but i couldn't afford to work with boys, and he was very much like this is what i could live off. you know, i just got like i want to build the state like that would be like this is what it compute. but at this point, just seeing that, i hadn't take ken a salary for like six months and 'd already. we'd already spent like tens thousand hundred dollars on like on GC people and all of that. and just like i don't think we can on GY people and can do it. and so i had met one one individual in in silicon valley. his name is loccky, and and just i ended up just calling him and saying, hey, i kind of want to learn a little bit faster here. can i can we raise like seven hundred kay? that's like what i wanted to raace. so it's like i wanna have two engineers for the rest of year just seen. i still need to be paid. and then a little bit of buffer room. it's this is what what need. and and this doesesn't pm f, and it's a big opportunity by the the year. i don't think wegoing to bother ther and will just shut the whole thing down. and we i want to have a taking a time will return everything to you 啊. i think there was the first time you heard anyone said like that. um and i told some other vcs that at the time, and that was terrifying to them. i think to someone on the west coast, this sounds like you have low ambition or something like that. um and to me, it was just like i don't know, just came from a when i don't know how to play a game. i just play it open cars like this is how i see it. so and we were it was very clear to us that we wanted to do this. and but also, it became clear to us that we didn't want it just like keep working on this and leesit could become big. and you were starting to builp condition conviction that is actually become really, really big. and so we did that and hiirer born, then became profitable later that year. and then just continue to higher. and then it's like to raise more money. you need sort of there's six reasons to race capital. the first reason to raise capitals to fund r and d. um that was the reason that we raied capital in january because we funded RND with a lot of our own. you know, opportunity cost sts, not taking a salary and then paying the bills ourselves, but we wanted to learn a little bit faster. and so we hired boorn and morgin us the first engineers. and in the second reason to raise capital is the fund growth. you build something, and you want to tell the world about it, and you want to spend more capitals to do that. the third reason to to raise capital is for the founders ego. it's a very popuposly. it's very popular, very, very popular, right? big numbers, lots of press like. and i think this is a very, very dangerous reason to raise money. and i wish that it was more talk about because you're deluting all of your employees when you do it, you are um setting a certain price for future employees, and they're upside. it's it's for some people who can become a status game. and that's not what it's about. we're here to build a big business together, and this is not a reason to raise money.

</details>

<!-- chunk 29/54 -->

### 融资的六个原因

**Speaker 1**: 但我确实认为这种情况会发生。第四个融资原因是为了奖励你的员工，对吧？如果你正在一段非常漫长的旅程上，你想和世界上最优秀的人一起工作。而根据定义，世界上最优秀的人并不多。所以你想奖励他们。嗯，这就是我们在12月拿了更多资金的原因——为了让员工能够变现一些股权，而不是等待像IPO或更远的未来事件。第五个融资原因是为了建立战略合作伙伴关系。在这个城市里，已经有一些通过战略合作而成功的公司。第六个融资原因是为了进行并购之类的事情。但你必须非常诚实地面对自己，你到底是出于这六个原因中的哪一个在融资。我们第一次融资的原因是第一个，第二次融资的原因是第四个。

<details>
<summary>Original English</summary>

**Speaker 1**: but i do think that it happens um the fourth reason to to raise capital was to reward your employees, right? it's if you're on a very long journey. and you want to work with the best people in the world. and by definition, there's not that many best people in the world. so you want to reward them. um that was the reason that we took more capital in december um was to allow the employees to liquidate some equity, instead of waiting for some like event like an ipo or something like further out. um fifth reason to raise for a strategic partnership. there are strategic partnership that have been made in this in this city that have made companies. the six reason to raise will be doing ma or or something like that. but it's like you have to be very honest about what reason you are raising in those six. first reason we raised was one. and second reason we raised was four.

</details>

**Speaker 3**: 嗯，所以第一次融资是为了研发，第二次是为了给员工提供流动性。

<details>
<summary>Original English</summary>

**Speaker 3**: um which once the first reason to raise was r&d, and the second reason was to provide liquidity to the employees.

</details>

**Speaker 1**: 是的。

<details>
<summary>Original English</summary>

**Speaker 1**: yep.

</details>

**Speaker 3**: 我认为这是一种健康的方式。而且我认为，在身份认同方面，我们很少谈论股权，尤其是对那些刚起步的创始人来说，因为现在似乎有很多人在融资。这将是其中重要的一部分。我想问问你关于你们现在的远程文化。我看到很多公司，尤其是那些做AI相关业务的公司，无论是构建AI基础设施还是AI产品，很多都倾向于线下办公，通常在旧金山或伦敦等地设立总部。因为这些公司经常发现，线下办公的迭代速度更快，层级更少。当然，速度非常重要。你是远程起步的，现在仍然是远程。效果如何？你们发现了哪些技巧或方法让远程协作变得更好？

<details>
<summary>Original English</summary>

**Speaker 3**: i think it's a nice and healthy way. and i think the equity part, we don't talk about in the identity, and so especially the the founders who are to to take you, because this seems where a lot of people are raising. it will be part of it as closing thing. i want to ask you about the way you have a remote culture these days. i'm seeing it especially for companies that do anything with ai may that be building ai infra or or or just ai products, a lot of them prefer in person having a hq often times in sf or wherever your headquarters is maybe be london or somewhere else. because you often, these companies often find that they have faster iteration is just a few layers can of between. and of course, speed, as is very, very important. you have started remote. you're still remote. how is it working? and what kind of quirks are like or tribal ways have you found to make this work better?

</details>

### 远程协作模式

**Speaker 1**: 是的，我认为公司是在2023年成立的，当时正值疫情之后，很多公司都是远程办公。Shopify的基础设施从一开始就是远程的，因为让很多人搬到渥太华非常困难。所以对我来说很自然的是，好吧，我认为可能有两个城市可以让你快速建立一家数据库公司，那就是旧金山和纽约，也许还有其他城市，对吧？但那是已经被验证过的地方。所以如果你不想那样做，我认为你必须全力投入某种分布式模式。我们一直在思考这种分布式模式对Turbopuffer意味着什么。这并不意味着完全没有线下聚会。我们每年会让大家聚在一起两次，在某个地方。今年我们去了南非，然后去了墨西哥城。所以这并不算多。但我们一直在尝试做的一件事是，我们有一个概念叫“篝火”。篝火的概念是，当几个人随机聚集在一个地方时，你就称之为篝火，并鼓励其他人，如果愿意的话，可以加入。例如，这周就是一个篝火活动，因为我来这里参加这个会议和其他一些事情。所以每个人都受到邀请，我们会去见客户，对吧？我们会为客户举办晚宴之类的活动。我们把它变成一个活动，一起度过时光，并鼓励每个人都来。我们现在已经发展到不会强制要求，但不是每个人都需要每次都参加篝火。有些人只想专注于工作，埋头写代码。那也很好。我们有些人每年只参加两次线下聚会，其他时间都在家和家人在一起。他们不花时间在飞机上。嗯，这太棒了，完全符合这种模式。公司里还有其他人可能每两周就要坐一次飞机。嗯，前几天有个人看到纽约有一个篝火活动，大家都在一个会议室里连线，她觉得很兴奋，就直接从渥太华打车去机场，飞到纽约和团队一起出去玩，对吧？我认为这太棒了。我们还引入了一些机制，比如如果你做了一个会议演讲、写了一篇博客文章，或者为Turbopuffer做了一些额外的事情，嗯，我们会给你一个Turbopuffer积分，这个积分可以让你升级下一次航班到商务舱，这再次鼓励了大家和团队在一起的时间。嗯，现在，我的意思是，Turbopuffer积分可能会发展出自己的生命。我们几乎在讨论建立一个中央银行，为Turbopuffer积分设定利率，并建立一个Turbopuffer积分的博彩市场。所以这可能会发展出它自己的生命。你知道，如果你参加像这样的会议，我们的一些工程师在这里只是为了与客户互动，整天站在展台上是很累的。所以如果你为了做好这件事而站了两天，你就会得到一个Turbopuffer积分，对吧？所以这就是我们尝试做的一些有趣的小事，来鼓励人们见面，如果他们想见面的话。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, i think the company started in twenty twenty three, sort of like on the on the post-covid era where a lot of companies were just remote. um the shopify infrastructure was remote since the very, very beginning because it's not very difficult to get them to move to ottawa. um and so it was natural to me is like, okay, i think there's kind of maybe two cities where you can build a database company fast. and that's san francisco and maybe new york there, maybe other cities, right? but that's like kind of where it's been done. and so if you don't want to do that, i think you have to go all in on on some distributed model. and so we've had to figure out what is that distributed model mean for turbopuffer. it doesn't mean the absence of in person. we get everyone together twice a year in some in some location. um this year, we were in south africa, then we in mexico city. and so so it's like that's that's not that often. but one of the things that we've been trying to do, we have this concept called camp fires. and the concept of the camp fire is that when a couple of people just sort of randomly congregate in a place, you call it a camp fire, and you encourage as people, people as want, come come and join. so for example, this week is a tribe of of camp fire in san francisco because i am here for this conference and a bunch of other things. and so everyone is invited to come like we're going to go for customers, right? we're going to put on dinners for our customers and things like that. and we just make a thing out of it and and spend time together, and we encourage everyone to come. we've also gone to the extent now of we won't encourage that, but not everyone, not everyone needs to go to to campfire all the time. some people just want to, you know, lock in and hack into the terminal. and that's great. we have people that just make it to the offsites twice a year and otherwise they're home with their families. they don't. they don't spend time on an airplane. um fantastic like that is completely compatible with this model, and there are other people with the company who are on a plane, probably every two weeks. um we had someone the other day where they saw, a camp fire happening in new york. and everyone was dialing in from a meeting room in new york, and she had so much fomo that she took an uber straight to the airport in ottawa, flew to new york to hang out with the team, right? and i think that's fantastic um and we've also introduced these things where um if you you do a conference talk or a blog post or something for turbopuffer something a bit extracurricular, um we give you a turbo credit and a turbo credit allows you to upgrade your next flight to business class, which, again, encourages spending time together with the team. um and now i mean, turbo credits are probably going to take on a life of their own. we're almost talking about doing a central bank and doing interest rates on the turbo credits and and doing a betting market on the turbo credits. and so like this might take on, it's life on its own. and you, you know, if you're at a conference like this, there's some of the our engineers here who are just to interact with customers and beyond, like standing on a like expo floor all day is quite taxing. and so if you do that for two days because you want to do it well, you get a turbo credit, right? and so it's just like these fun little things that we try to do to to encourage people to meet if they want to meet.

</details>

**Speaker 3**: 谢谢你。嗯，在这次对话中，我觉得非常有趣的是，Turbopuffer作为基础设施层被这么多AI公司使用，但在这次谈话中，我们却很少谈论AI，更多地谈论了持久的原则、保持好奇心以及人与人之间的联系，以及让人们一起工作、相互信任是多么重要。所以非常感谢你。让我们为Simon热烈鼓掌。

<details>
<summary>Original English</summary>

**Speaker 3**: thank you. well, in this session, what i found very interesting as turbopuffer is so many ai companies are using you as infra layer, but in this conversation, we managed to talk very little about ai, a lot more about enduring principles, pushing being curious and the human connection, how important this is for people to work together to trust each other. so just thank you very much for this. so let's give a big round of applause for simon.

</details>

**Speaker 1**: 非常感谢。

<details>
<summary>Original English</summary>

**Speaker 1**: thank you so much.

</details>

### 评估AI代理系统

**Speaker 8**: 超级工程实验室和基础设施。今天，我们将讨论生产环境中的AI代理系统。当大多数人听到“评估”这个词时，他们会想到基准测试：一个模型在基准测试中得了90分，新版本得了92分，团队庆祝。但AI代理系统从根本上改变了评估的含义。系统会推理、规划、调用工具、检索信息、执行工作流，并与生产基础设施交互。问题不再是模型是否通常给出了正确答案。问题是系统质量是否足够好。我想讨论一下，对于现代AI代理系统，评估是如何演变的，以及评估基础设施的重要性。这是几乎所有AI组织今天都在遇到的问题。离线基准测试在持续改进，但生产环境的可靠性却常常无法预测。为什么会这样？因为基准测试衡量的是模型能力，而生产环境衡量的是系统行为。基准测试无法捕捉工具故障、API上下文变化、数据可用性、长尾工作流等问题。随着系统变得越来越动态，基准测试性能和生产性能之间的差距也在扩大。这就是许多团队所面临的困境。

<details>
<summary>Original English</summary>

**Speaker 8**: supertengines lab and infrastructure. today, we're going to be talking about production with agentic systems. when most people hear the word evaluation, they think about benchmarks a model scores ninety percent on benchmark, a new version scores ninety two percent, a team celebrates. but agentic systems have fundamentally changed what evaluation means today. the system reasons, plans, calls tools, retrieves information, executes workflows, and interacts with production infrastructure. the question is no longer did the model generally give the right answer. the question is is the system quality good enough? i would like to discuss how evaluation is evolving for modern agentic systems and evaluation infrastructure. this is the problem almost every ai organization is encountering today. offline benchmarks continue improving, yet production reliability often remains unpredictable. why is that? because benchmarks measure model capability, production measures system behavior. a benchmark doesn't capture tool failure, api context changes, data availability, long tail workflows. and as systems become more dynamic, the gap between benchmark performance and production performance grows. the result is what many teams face.

</details>

### 让AI成为明星球员

**Speaker 4**: 好的？大家好。我的名字是Kevin。我将谈论Antigravity。这里有《足球》的粉丝吗？哇！想象一下，你是阿根廷队的教练，比赛进行到第89分钟，你的队伍里有梅西。你会执行什么战术？那就是把球传给梅西，然后其他人闪开。AI不再只是角色球员了。如果你围绕它们构建了正确的产品，它们可以成为你的明星球员。而要让你的明星球员发挥，你必须给模型让路。我们可能需要把幻灯片调出来。哦，它们已经在了。嗯，Antigravity是谷歌面向技术用户和非技术用户的AI代理编码产品。我们在2025年11月推出，此后在谷歌内部和外部都加速了部署。我叫Kevin，是Antigravity工程团队的部分负责人。让我们更多地了解一下Antigravity是什么。我们一直并且将永远毫不妥协地以代理为先。所以去年我们在Antigravity IDE中首次推出了一个全新的代理管理器概念，它是一个管理和编排多个代理的平台。从那时起，我们实际上提取了我们的代理，并推出了我们自己的Antigravity CLI。上个月在Google IO，我们很高兴地推出了Antigravity 2.0，其主题是“给模型让路”。我们实际上将IDE与代理管理器解耦了。所以现在你有两个独立的应用程序，现在你可以在一个独立的应用程序中使用代理管理器。一图胜千言。这是Antigravity 2.0运行时的截图。正如你所看到的，

<details>
<summary>Original English</summary>

**Speaker 4**: all right? hello, everyone. my name is kevin. i'm going to be talking about antigravity. so are there any world cup fans out there? whoa! imagine you are coaching argentina and you're in the eighty ninth minute. and you have messi on your team. what play are you running? it's called give messi the ball and get the heck out of the way. llms aren't just role players anymore. they can be your star player, if you build the right product around them. and to let your star player cook, you have to get out of the model's way. we might want to get the slides up. oh, they are great. um so antigravity is google's agentic coding product for technical and non technical users. we launched back in november of twenty twenty five and have been accelerating adoption, both within google and externally ever since. my name is kevin, and i lead part of the engineering team on antigravity. so let's talk a little bit more about what antigravity is we have and always will be unapologetically agent first. so we debuted the antigravity ide last year with a brand new agent manager concept, and it was a platform to manage and orchestrate many agents. since then, we've actually extracted our agent and launched our own antigravity cli. and last month at google io, we had the pleasure of launching antigravity 2.0 and in the theme of getting the model out of the way we actually decoupled the ide from the agent manager. so now you have two separate applications, and now you can use the agent manager in a standalone app. and so a picture is worth a thousand words. here's a screen shot of antigravity 2.0 in action. as you can see,

</details>

<!-- chunk 30/54 -->

### 从专用任务控制到智能扩展

**Speaker 4**: 这不仅是为你自己的智能体和项目设立的专用任务控制中心，你还有子智能体，你拥有所有新模型。你拥有工作树、定时任务、语音模式。这个产品能影响的事情太多了，但今天我不想花时间向你介绍产品。我想多聊聊幕后故事，聊聊其中蕴含的一些原则，以及一些导致其路线图产生的关键因素。

<details>
<summary>Original English</summary>

**Speaker 4**: not only is that your own dedicated mission control for your agents and projects, you have sub agents, you have all the new models. you have work trees, scheduled tasks, voice mode. there are so many things to impact with the product, but i don't want to spend today telling you about the products. i want to tell you a little bit more about the behind the scenes, some of the principles that went into it. and notably some of the things that led to its road map.

</details>

**Speaker 7**: 嗯。

<details>
<summary>Original English</summary>

**Speaker 7**: 嗯.

</details>

**Speaker 4**: 所以，对于你们中的一些长期关注者来说，这实际上是我第五次在AI工程师大会上发言。我从22年开始就一直致力于构建开发者工具。在我谈论过的所有经验教训中，有一个理念最为突出，那就是“随智能扩展”。这意味着，随着模型变得更好，你的产品也应该如此。无论你使用的是哪个模型，其前沿能力都应该体现在你的用户体验中。那么，让我们来谈谈更具体的例子。

<details>
<summary>Original English</summary>

**Speaker 4**: so as some of you for the long time, AIN ge ans ans, this is actually my fifth time speaking at AI enge. um and i've been building developers tools since twenty two. and the one thing that has stood above all other lessons that i've talked talked about is the idea of scaling with intelligence. this means that as the model gets better. so should your product in the frontier edge of whatever model you are serving should be appparent inside of your users product experience. so let's get into more concrete examples of what this means.

</details>

**Speaker 4**: 对于那些在X上关注我，或者在过去四年里听过我演讲的人来说，你们会知道，我年复一年地致力于这些类型的转型。在2022年，我专注于自动补全和聊天侧边栏。这基于嵌入、规则文件、AST语法、树解析，基本上那个应用里的一切都是确定性的，因为那是当时模型能处理的全部。到了2024年，当智能体出现时，它彻底改变了开发者工作的方式。随之而来的是新的原语，比如MCP、自定义工具和权限系统。到了2025年，我们推出了Antigravity的智能体管理器，许多其他产品也紧随其后，采用了类似的模式，让用户可以同时并行管理多个智能体。这催生了技能、钩子、工件以及其他一些原语，这些定义了2025时代。

<details>
<summary>Original English</summary>

**Speaker 4**: so for those of you that follow me on x or hear me just gap generally for the last four years, you'll know that i've been working on a number of these sort of transformations year over year over year. in twenty twenty two, i was working on auto complete and chat cybars. this was based on embeddings rules files AST syntax, three parsing, basically everything inside of that app is deterministic because that's all of the model could really handle. and in twenty twenty four, when agents came onto the scene, it completely chanchaned. how developers were going to do work with. it came new permitives like mcp custom tools and permission systems. and with twenty twenty five, we introduce antigravity is agent manager with many other products following suit in that similar forrein factor with users managing many agents at once in parallel. and this led two things like skills, hooks artifacts in a couple other primitives, and that sort of defined the twenty twenty five era.

</details>

**Speaker 4**: 那么，我们来谈谈2026年以及可能出现的原语。在回答这个问题之前，我想带你们回顾一些更贴近我们自身的“战斗伤痕”。随智能扩展绝非易事。要拿走用户喜爱和熟悉的东西，引导他们走向一条可能——这是一个关键词——更好的道路，这非常困难。我们并非总是正确的，但在我准备这次演讲的幻灯片时，有两个例子浮现在我的脑海中。第一个是赋予AI终端权限。我们都还记得关于“Son of Anton”删除你整个代码库并对你的初创公司、公司等等造成灾难性后果的恐惧。但随着模型变得更好，人们投资于权限系统等原语，用户最终构建得更快，交付得更多，而且他们是在安全的前提下做到的。所以我们能够克服这一点。随着模型变得更智能，它们能够更好地判断应该在终端中运行什么，不应该运行什么。

<details>
<summary>Original English</summary>

**Speaker 4**: so let's talk a little bit about twenty twenty six and what those primitives might be. before we answer this question, i want to take you back to some of these battlescars that are a little bit closer to home. scaling with intelligence really is not easy. it's really hard to take away something that users love in our familiar with to lead them down potentially, and that's a big keyword, a better path. we aren't right one hundred percent of the time, but there are two that jumpp to mine. when i was putting together of the slides with this talk. the first one is giving ai a terminal. we all remember fears about son of anton deleing your entire code base and doing catastropc things to both. you know, you're start up your company exetra exetra. but as models got better and people invested in primitives, such as permission systems, users ended up building, faster ended up shipping more. and they did so safely. so we're able to overcome this. and as models got smarter, they're able to bake better decisions about what they should and should not run in your terminal.

</details>

**Speaker 4**: 第二个例子是这条推文，它非常典型地代表了当我们从Windsurf中移除聊天功能时我收到的“怒吼”。很多用户对我们的团队大喊大叫，因为我们拿走了他们非常珍视的东西——聊天侧边栏，并用一个纯粹的智能体取而代之。在当时，这是一个熟悉的功能，很难让人接受。但当我们回顾过去，模型已经进步了，多步骤研究、智能体研究和执行成为了新的范式。而今天，我们都在使用并喜爱着所有这些智能体产品。所以，现在我把你们带到今天的“战场”：今天发生了什么？我们将智能体管理器从IDE中分离出来。在Antigravity 2.0中，不，我们将它们拆分成了独立的应用程序。我们认为，IDE之于智能体管理器，就如同调试器之于IDE。你并不总是需要调试器，但如果你需要深入一层，深入抽象栈的下一步，它绝对是有帮助的。我们的预测是，这种智能体编排的理念——你可以称之为智能体团队、蜂群，或者软件工厂——就是未来，我们愿意押注这个未来。

<details>
<summary>Original English</summary>

**Speaker 4**: the second instance is this tweet, which is very representative of sort of the yelling that i got when we removed chat from wininerf. so a lot of users were yelling at our team because we took away something that was very dear to them. the chat side bar and replaced it with only an agent. now at the time. this is something that was familiar. and rather difficult to swallow. but when we look back models have advanced multi step research, agentic research and execution became the new paradigm. and here we are today using and loving all these agentic products. and so now i bring you to today's battle, what is going on today. so we did couple the agent manager from the id. and with antigravity two point, no, we spot them into separate applications. we believe that the ide is to the agent manager, what the debuggger was to the ie. you don't always need a debugger, but it definitely is helpful to have it. if you need to go a layer beneath and go one step deeper into that abstraction stack. and our prediction is that this idea of agent orchestration, you can call agent teams. you can call it swarms, you can call software factories is the future, and we're willing to bet on that future.

</details>

**Speaker 4**: 所以，以下是我们称之为“2026时代智能体团队”的原语。这些包括子智能体、卡片内的生成式UI等等。我们稍后会更全面地讨论这些东西是什么，以及它们在产品中如何体现的例子。但首先理解“为什么”非常重要——是什么带来了这些变化？是什么模型变化，什么模型属性实际上导致了这些新事物的开发？作为一个产品团队，你是强行推动新时代的原语，还是通过使用模型、体验模型而自然获得的？答案是两者兼而有之。身处Google DeepMind的特权之一就是我们拥有产品与模型之间的这种关系。你们还记得Antigravity 1.0的核心是并行管理智能体，让人类处于驾驶位。如果你们记得我上次的演讲，我更多地谈到了这种研究-产品飞轮。现在，正如承诺的那样，由于Antigravity产品的存在，Gemini已经学会了更多关于如何管理一个智能体团队的知识。让多智能体系统变得更好、更具协作性、更擅长将任务分解为更小的子任务，这仍然有很大的提升空间。但有了Gemini，我们有了一个非常好的开端。所有的基础知识都已经注入到模型中，这样我们就可以构建像Antigravity 2.0这样的产品。Gemini 3.5 Flash于四月份发布，它将我们在后台与Antigravity一起开发的许多能力带到了市场上。Flash现在不仅擅长执行测试，它实际上非常擅长领导团队。它更快、更便宜，推动了智能与运行速度和成本之间的帕累托曲线。综合所有这些，我们非常兴奋地宣布，在Antigravity中，智能体团队功能已进入公开预览。你只需输入斜杠命令“/teamwork”，就会看到一个新的模式，你可以进入并释放一群智能体来处理手头的任务。

<details>
<summary>Original English</summary>

**Speaker 4**: so here are the primitives for what we're calling. the agent teams twenty twenty six era. these are things like subagents generative UI inside cars. we'll talk more completely tly about those things are in some examples of how they manifest inside of the product. but it's really important to first understand the why what brought about these changes and what model changes, what model properties actually led to the development of these new things? and as a product team, do you force the new era of primitives? or is it something that comes to you by using the model and experiencing the model? the answer is kind of both right and the privilege of being inside of google deep mind is that we do have that relationship between the product and the model. so you remember the crox of antii gravity, one point o is to manage agents in parallel to put the human in the driver seat. and if you remember my last talk, i talk a lot more about this research, product fly wheel. and now as promised because of the antigravity product, geri has now learned a finger, too about how to manage a team of agents. there's still a lot of headroom room, make mumulti ents systems better, more collaborative, better, a deconstructing task into smaller task. but we've got a really good head start with germany. and all the basics have been imbuted the model so that we can build up product like antigravity tupoint out gernine three point five flly gmini three point five flash laununed back in april. and this brought to market a lot of those capabilities that we have been working on on the background with antigravity and flash now isn't just good at executing test. it's actually really good at leading teams s. it's faster and cheaper, pushing the parado curve of what is intelligent, verses, the speed and the cost at which you run those things. and putting this all together, we were really excited to announce agent teams in public preview inside of antigravity. all you have to do is simply type the slash command, sash teamwork, and you'll see a new mode where you can enter an unleash, a swarm of agents onto the task at hand.

</details>

**Speaker 4**: 我们来谈谈这是如何工作的。作为用户，你需要指定你的任务。越具体越好，不过，这种智能体通信方式的特性是，如果它需要更多信息，它实际上可以向你询问，直到一切都基本清晰。你将与那个主导智能体合作，它会管理一个任意规模的团队来完成工作。我喜欢把它比作复仇者联盟，对吧？它不只是一堆专业角色，它创造了前端工程师、后端工程师、基础设施专家、QA、设计师，等等等等。每个子智能体可以承担的角色有无限可能。每个子智能体都是动态生成的，可以独立运行，它甚至可以选择与主导智能体不同的模型。这是由主导智能体完成的，再次强调，我们是在随智能扩展。这方面最酷的一点是，它可以利用像Flash一样快的模型来使用生成式UI。事情可以几乎瞬间发生。如果你问，“嘿，我的任务状态如何？给我展示一个甘特图看看进展”，或者，也许你更喜欢像Chrome调试器那样的工具，它可以向你展示一个时间线。所有这些都是即时生成的，因为它能够按需生成UI。

<details>
<summary>Original English</summary>

**Speaker 4**: so we'll talk a little bit about how this works. you as a user will specify your task. the more specific you are the better, though, the nature of these agentic communication styles is that if it need something more, it can actually ask you for more until everything is basically clear. you'll work with that lead agent, and it will manage a team of arbitrary size to get that work done. and when i like to say it's kind of like the advengers right didon't take a bunch of specialized roles. it made front end engineers back in engineers, infrastructure specialist QA design, the list goes on and and on and on. there, there are infinite possibilities for what each of those subagents could take on, each sovasion is dynnamicgenerated and can operate independently, and it can even actually select a different model from what the main agent is using. and this is done so by that main agent, again, we are scaling with intelligence. and one of the coost aspects of this is that it can use generative UI with a model that is as fast as flash. things can happen nearly instantaneously. if you ask, hey, what is the status of my task show me a camin in what's going on, or maybe you know, prefer something a little bit more like, uh, the chrome debugger tool, it can show you a timmlike. and all these things are generated on the fly because it's able to generate UI on demand.

</details>

**Speaker 4**: 这个系统已经实现了一些项目。我们构建了一个照片编辑器，你可以在浏览器中直接编辑原始照片。我们还构建了一个消息应用，可能对在座的各位来说有点眼熟。这些项目动用了数百个子智能体，运行了将近半天时间。但为了真正测试它的能力，我们做的一个最引人注目的运行实际上是构建了一个完整的操作系统内核。这是我们在Google I/O上展示的成果，我们从零开始构建了一个完整的操作系统内核，并且真的在上面玩了《毁灭战士》。我的同事Rohan在Google I/O上演示了这一点。我们对这个里程碑感到非常自豪，因为它真正证明了，如果你投入更多的智能，投入更多的子智能体来解决这类问题，像Gemini 3.5 Flash这样的模型能够以一种不仅非常强大，而且可扩展、温和地说，还负担得起的方式来完成它。显然，我们不会每天花几千美元来构建一个操作系统内核，尽管这是可能的。其中一些数据是：它动用了93个子智能体，耗时12小时，发出了15000次请求，消耗了20亿个token。而成本不到1000美元，这是这个项目真正酷的地方之一。所以，正如你从这个例子中看到的，子智能体原语是构建2026时代智能体团队的决定性部分之一。

<details>
<summary>Original English</summary>

**Speaker 4**: so some of the projects that the system has implemented. we've built a photo editor, you can actually edit raw photos directly inside of your broser. um we've also built a messaging app that might look a little bit familiar to those in the um in each each. these took hundrereds subagents uh and took almost half a day to run, but to really put it through its paces. one of the hero runs that we did was actually building an entire OS kernel. this is something that weve got to show off at google io, but we built a complete os corneal from scratch and actually played dooe on it. and my colleague room was able to demo this at google io. we were superproud of this particular milestone because it really demonstrated that if you throw more intelligence, you threw more subagents um at this sort of problem a model like german at three point five flash could do this in a way that was not only very, very powerful, but also scalable. and, you know, mild, dly, affordable. obviously, we're not going to spend thousands and thousands of dollars to about an OS correnal every day, though it is possible. and some of the stats out of this, it took ninety three subagients over the course of twelve hours, made fifteen thousand requests, two billion tokens. and it was under a thousand dollars, which was one of the really co aspects of this project. and so as you can see with this particular example, subagent primitives are one of the defining parts about building um twenty twenty six era of agent teams.

</details>

<!-- chunk 31/54 -->

### 从手动流程到自动化研究

**Speaker 4**: 所以智能体团队只是第一个例子，我想向你们展示我们团队内部使用的另一个例子，它展示了这些新原语的能力。第二个例子是关于自动化研究任务。我们在 Gemini 内部工作，帮助 Gemini 在编码相关任务和智能体相关任务上变得更好。而这正是产品真正开始展现魔力的地方。我们有一个内部版本的 Antigravity，研究人员、工程师和非技术人员都可以使用。当他们理解了 Antigravity 提供的原语后，它就变成了一种非常非常强大的方式来自动化自己的工作流程。

<details>
<summary>Original English</summary>

**Speaker 4**: so agent teams are just that first example, and i want to show you another example that our team uses interternally that sort dedestrates of these new primitives. um the second one about auautomating research tasks, so we work inside of gemini. we help sort of make gmini better at coding related task, agentic related task. and this is where the real magic starts happening with the product. we have an internal version of antigravity that researchers, engineers non technical folks can use. and when they understand the primitives that antigravity offers, it becomes a very, very powerful way to automate your own worklose.

</details>

**Speaker 4**: 我们以并排评估分析为例。这是一个非常常见的工作流程，不仅在 DeepMind，在整个行业都是如此。基本上，你会获取多个输出结果，一个、两个、三个、四个等等，然后你想比较它们。所以你会拿一组测试，进行一些运行，得到一些结果，最终它们会在两个不同的表格里。对，现在你会查看对照组，查看实验组，然后弄清楚不仅有什么差异，而且可能还有这些差异的原因是什么？以及我们如何从那里开始迭代，为下一个实验做出更好的版本？传统上，这需要大量的 Jupyter Notebook 和手动操作。但是当你开始使用 2026 年的新原语时，你的工作流程会变得干净得多。

<details>
<summary>Original English</summary>

**Speaker 4**: so we'll take the example of side by side eval analysis. this is a very common workflow, not only a deep mind, but just generally in the industry. you essentially, you will take multiple rollouts, one, two, three, four extrtra, and you want to compare them. so you'll take a set of test. you'll do some rollouts youll get some results and y'll essentially be in two different tables. 对对, now you'll look at contcontrol, look at the experiment ment and know how to figure out not only what the difference was. but perhaps what are the reasons for those differences? and how can we actually iterate from there and make a better version of for the next experiment? now? traditionally, this was a lot of jupiter note book elbow, greece essentially. but when you start working with the new primitives in twenty twenty six, you end up with a lot cleaner of a worklobe.

</details>

**Speaker 4**: 嗯，所以研究人员能够通过简单地用自然语言向智能体提问关于评估结果的问题，来自动化这个工作流程的百分之九十。然后，这个已经具备了技能并理解谷歌庞大代码库的智能体，就能够处理数据并返回一个差异报告给你。这里真正酷的地方是，它不仅仅是把这个差异报告交给用户，它还多走了一步。它启动了一个研究智能体专家，这个专家会提出一百种不同的假设，解释为什么会出现这些差异。然后它使用子智能体，为每个假设分配一个子智能体，基本上并行地深入研究每一个特定案例，最终映射回一个单一的响应，然后告诉研究人员：嘿，这是我发现的一些领域。现在，这里有一份报告供你审阅。

<details>
<summary>Original English</summary>

**Speaker 4**: 嗯, so researchers wewere able to automate ninety percent of this workflow by simply asking the agent about the evalils in questioning using natural language, then the agent that is now primed with skills and an understanding of googles. massive montreo code base is able to crunch the numbers and get back to you with a delta. now what's really cool here is instead of just taking that delta than handing it to the user, it went the extra step. it spn up for a research agent specialists that proposes a hundred different exhrothesis over why those deltas might occur. and then it uses subagents to then spit up one subagent for hypothesis and basically drills into that particular case in parallel, mapping back to a single response and then telling the research are. hey, here are some areas that i found. now, here's a report that you can review.

</details>

**Speaker 4**: 而真正酷的是，它不仅仅停留在报告阶段。它实际上还构建了一个生成式用户界面，供你浏览和交互。所以我可以使用下拉菜单进行过滤、分段、切片，并与数据进行丰富的交互。嗯，在内部，我们非常关心这类工作流程，用于改进模型、改进产品，并理解用户在谷歌内部成功和失败的方式。所以，过去非常手动化的流程，现在只需要几分钟。过去需要手动工程，你必须构建自己的智能体评估池，设置你的评判标准，整合数据管道。所有这些现在都开始建立在我们在之前的幻灯片中确立的这些新原语之上。你拥有一个完全动态的子智能体图。生成式用户界面在最后出现，以最符合用户理解方式或可能适合他们学习风格的方式，丰富地传达发现结果。所有这些都可以随时重新生成和重做。用户所要做的就是加载一个技能文件，然后提问，没有异议。

<details>
<summary>Original English</summary>

**Speaker 4**: and what's really cool is that it doesn't stop it, just the report. it actually puts together a generative UI for you to look through interact. so i drop down filter segment slice and actually interact richly with that data. 嗯, and internally, we care a lot about this sort of workflow, improving the model, improving the product and understanding the ways that users find success and failure internally a google. so what used to be a very manual process. now it takes minutes. so what used to be hand engineering, you'd have to build your own acing pool of agents, you'd have to set up your judges, you'd have to take together data pipelines. all of this now starts becoming grounded in these new primitives that we established earlier in the slideshow. you have a subagiing graph that is completely dynamic. the generative UI comes in the end to rithally convey the findings in a way that the user best understands, or maybe vocaters to their learning style. and all of these things can be regenerated and redone on the fly. all the user had to do was load up a skills file and asked away 没有异异议.

</details>

### 2026 年的三大原语

**Speaker 4**: 所以，通过团队合作和这个评估例子，我们开始触及我一直在谈论的这些 2026 年原语。这些模型特性确实改变了我们思考产品和开发产品的方式。我们谈到了三个例子。首先，我们有动态子智能体。为了提供更多细节，嗯嗯，基本上，没有两个子智能体是相同的。主智能体完全自主地进行编排。它动态地配置、提示和分配子智能体。它们并行运作，在不同的安全环境中运行，无论是沙箱还是远程执行系统，并且它们可以承担无限数量的专业化角色。所以，这里的扩展故事是相当明显的。从最后两个例子中，你可能可以看出来，随着模型变得更智能，你的团队将变得更加专业化。它将变得更加协作。最终，这意味着它将能够为你完成更复杂的工作。

<details>
<summary>Original English</summary>

**Speaker 4**: so with teamwork and this ebel example, we start arriving at these twenty twenty six primitives that i keep talking about. and these model characterteristics really changed the way that we have to think about the product and how we have to develop the product. so the three examples we've talked about, first, we have the dynamic ovagent and to provide a little bit more color here. 嗯嗯, basically, no two subagents are the same. the main agent is the one that is orchestrating this entirely on its own. it's configuring and prompting and ceding the subagents on the fly. they they ooperate in parall l they ooperate in different types of secure environments be at a sandbox be at a remote execution system. and they can all take on ininfinite number of specialized roles. so the scaling story here is quite obvious. and from the last two examples, you can probably tell, as the model get smarter, your team will become more specialized. it will become more collaborative. and ultimately, that means it'll be capable of getting more complex work done for you.

</details>

**Speaker 4**: 第二个是这个新概念，我们过去稍微做过一些，但它被称为 Sidecar。这是一个我们即将引入 Antigravity 的新插件协议。Sidecar 本质上是一个解耦的进程。这个名字在一定程度上反映了引擎盖下发生的事情，但它是一个长期存在的实用程序，负责监听。它允许模型监听外部世界，并为可能发生的事情设置自己的触发器。例如，这可能是短信消息、Webhooks、Cron 作业、连接到 GitHub PRs，等等。但这是一个通用的插件原语。Antigravity 已经将 Sidecar 用于基于时间的事情，这就是定时测试 Cron 概念的来源。嗯，但在引擎盖下，这都是这个新的 Sidecar 原语。我们将在今年夏天晚些时候发布这个规范，以便你们都可以在这个新原语之上进行构建。但是，内部人员使用这种概念的方式有一些非常非常酷的。

<details>
<summary>Original English</summary>

**Speaker 4**: and now the second is this new concept, we've uto do it slightly in the past, but it held side cars. this is a new plugging protocol that we're bringing to integravity a side car ar prois esessenally ally. it is a decar process. the naming sort of reflects what what's going on to the the hood, but it's a long live utility, and it's responsible for listening. it allows the model to listen to the outside world and set up its own triggers for things that might happen. for example, this could be sms messages. this could be web hooks, cron jobs, hooking it up to get hub PS. the list goes on and on, but this is a generic plugged in primitive integravity ity already use a side cars for things that our time based. this is where the the scheduled test croon concept comes from. um but under the hood, this is all this new side car primitive. so when 're releasing the spect for this, so that you all can build on top of this new primitive um later this summer, but there are some really, really cool ways that people internally have been using this sort of concept.

</details>

**Speaker 4**: 第三个也是最后一个原语是生成式用户界面。我们假设人类编写的专用用户界面已经过时了。Gemini Flash 在 Antigravity 上的运行速度接近每秒 900 个 token。这比许多其他前沿模型体验快十倍。在几秒钟内，你就能从脑海中的想法，变成一个提示，再变成一个设计好并完美嵌入到你对话视图中的用例。而且，不依赖于模板甚至 HTML 文件，Antigravity 可以内联渲染你生成的用户界面，所以你可以做一些类似在 Playground 中操作的事情。但这也可以扩展到条形图、图表、表格，任何你想要交互并且可能比 Markdown 文件或对话视图更深入检查的东西。生成式用户界面在很多方面让我想起了已故的史蒂夫·乔布斯在发布 iPhone 时说过的一句话。他证明了移除键盘的合理性。他说，它们都有这些键盘。无论你是否需要，它们都在那里。而且它们所有这些控制按钮都固定在塑料上，对于每个应用程序都是一样的。以一种类似的方式，我们构建了我们的产品，使其能够动态地适应智能体的需求。我们跳过了基础设施和机械用户界面，转而使用 Sidecar 和生成式用户界面。这创造了一种不固定在塑料上的产品体验。

<details>
<summary>Original English</summary>

**Speaker 4**: and the third and final primitive is generative. i so we hypothesize that human written specialized us are kind of dead geri flash on antigravity clocks in it almost nine hundred tokens a second. this is ten x passive than a lot, the other frontier model experiences. and in a matter of seconds, you're able to go from whatever you are thinking inside of your head into a prompt into a use case that is designed and embedded inside of your conversation view perfectly. and rather than rely on tempplts or even even t ml files antigravity can render your generated UI in line, so you can do things like things in play doome. but this also extends the things like bar charts, graph tables, anything that you would want to interact with and maybe inspect a little bit further than just a markdown file or just a conversation in genertive view in, in many ways, reminds me of the quote that the late steve jobs said, when unveiling the iphone, he justifies the removal of the keyboard. and says they all have these keyboards. they are there whether you need them or not. and they all of these control buttons that are fixed in plastic and are the same for every application. and in an nawgious way, we built our product to dynamically scale with the needs of the agent, we skipped to have a infrastructure and mechanical us in favor of sidecars in generau. i and that creates a product experience that is not fixed in plastic.

</details>

**Speaker 4**: 所以，子智能体、Sidecar 触发器和生成式用户界面是驱动 Antigravity 的最新原语。我们尽力不挡道，让模型自由发挥。如果你正在围绕智能体构建产品，你应该考虑：我的产品中有哪些原语？它们如何随着模型的智能而扩展？我们都熟悉，使用所有这些新工具，发布功能现在相当容易。关键在于决定实际添加哪些功能，以便模型——也就是你的产品——能够随着下一个模型版本的发布而扩展，而下一个模型版本无疑会更快、更好、更便宜。因此，有了正确的原语，你作为构建者或产品所有者，可能会对模型的能力感到惊讶。

<details>
<summary>Original English</summary>

**Speaker 4**: so subagents side part triggers in generative UI are the latest permitives that are powering antigravity. we've tried our best to stay out of the way and let the model cook. and if you're building a product around an agent, you should consider what are the primitives that are in my product? and how might they scale with the model's intelligence? we all are familiar with shipping features is now quite easy with all of these new tools. and it's about deciding what features to actually add so that the model. so your product can scale with the next release of the next model, which will inevitably be faster, better and cheaper. and so with the right primitives, you as a builder or you as a product owner, you might be surprised of what the models can do.

</details>

**Speaker 4**: 按照惯例，我会一直使用这张幻灯片，直到我真正征服了 TPU Crunch。所以你们可以在 Twitter 上找到我。嗯，你们可以给我发私信提供反馈。我们一直在寻找关于如何构建最新最棒产品的新想法。感谢观看。谢谢 Swyx 和 Ben 邀请我。来到这里总是很开心，如果你们想进一步交流，我会在 Antigravity 的展台。如果你们想更多地了解产品，一些团队成员也会在那里。非常感谢你们的时间。

<details>
<summary>Original English</summary>

**Speaker 4**: and in classic fashion, i'm going to keep using the slide until i've actually conquered the TPU crunch. so you can find me on twitter. uh, you could dm me for feedback. we're always looking for new ideas on how to build the latest sting greatest. thank you for watching. thank you, swix and bent for having me. it's always joy to be here, and i'll be at the antigravity booth if you want to talk further. so you want to get to know the product a bit more. some t members will be there. so thank you so much for your time,

</details>

**Speaker 6**: 很高兴在 2026 年见到你们所有人，不是人类。

<details>
<summary>Original English</summary>

**Speaker 6**: if cited to meet you all not for human in twenty twenty six.

</details>

**Speaker 11**: 编码智能体将悄然淘汰第一个软件平台，不是因为它不好，仅仅是因为这个平台不再必要。我是 Dominic Tunnel，Resonate 的创始人兼 CEO。Resonate 是一个以极简主义和简洁为核心技术价值观构建的全球执行平台，这些特性将在本次演讲中发挥核心作用。在 Resonate，我们有一个关于软件工程发展方向的工作理论：通用实现将越来越多地被定制实现所取代。这些定制实现不是作为一个新的库、新的框架或新的平台按需生成的，而是作为对已有基础设施的最小扩展。这个理论认为，重用将向上游移动。我们不再重用通用实现，而是重用规范，并从中派生出定制实现。事实上，

<details>
<summary>Original English</summary>

**Speaker 11**: coding agenents will quietly retire the first soft platform, not because it's bad simply because the platform is unnecessary. i am dominic tunnel. i am founder in ceo of resonate. resonate is a global execution platform built with minimualism and simplicity as its core technical values, and these properties will play a central role. in this talk, it resonate. we have a working theory where software engineering is headed general purpose implementations will increasingly be replaced by be spoke implementations. generated on demand not is a new library, a new framework or a new platform, but is a minimum extension of the infrastructure that is already in place. this theory holds too reuse will move upstring instead of reusing, a general purpose implementation. we will reuse a specification, and we will derive a be spoke implementation from it. in fact,

</details>

<!-- chunk 32/54 -->

### 从实现到规约：AI时代的价值迁移

**Speaker 11**: 我们可以构建许多量身定制的实现，专门适配已有的基础设施。我们只需要在这个节点上询问Agent。提示词本身就是一个平台。Resonate是一个全局执行平台。我们有Resonate Java的实现，也有面向TypeScript、Python、Rust、Go和Java的Resonate SDK实现。所以我们必须问：如果实现变得可以自动生成，这个新现实对我们意味着什么？我们的价值在哪里？我们的答案是：我们的价值从实现转移到了规约。这改变了我们对推理的思考方式，产品不再是实现，产品是规约，是协议。从那个协议出发，我们希望衍生出多个服务器实现。一个是通用型Resonate服务器，是我们的参考实现；其他的则是与基础设施合作伙伴一起为客户和合作伙伴构建的实现。这意味着可以在他们现有的基础设施之上直接实现持久化执行，且只需极少的额外依赖。所以问题不再是“我们能构建一个服务器吗？”，问题是“我们能从同一个规约中反复综合出可信的服务器吗？”如果可以，那么……

<details>
<summary>Original English</summary>

**Speaker 11**: we can build many bespoke implementations tailor made for the infrastructure that is already in place. We just have to ask the agent at this point. The prompt is a platform. Resonate is a global execution platform. We have an implementation of the Resonate Java. We have implementations of the Resonate SDK for TypeScript, Python, Rust, Go and Java. So we have to ask, what does this new reality mean for us if implementations become generatable, where does our value live? And our answer: our value moves from implementation to specification. Now this changes how we think about reasoning, the product is no longer the implementation. The product is specification, the protocol. And from that protocol, we want to derive multiple server implementations. One is a general purpose Resonate server, our reference implementation, others are implementations built with infrastructure partners for customers and partners. This means durable execution right on top of their existing infrastructure with minimal additional dependencies. So the question is no longer can we build a server? The question is, can we repeatedly synthesize trusted servers from the same specification? And if so,

</details>

**Speaker 9**: 当我们谈论Agent工程时……

**Speaker 11**: 我们把所有注意力都放在验证上：我们如何知道结果是正确的？但今天，我想把焦点放在规约上。更重要的是，Agent如何参与系统的规约制定，而不仅仅是构建或验证它？最近，我们与多个基础设施提供商合作，将持久化执行原生地带入他们的技术栈。其中之一是Syndia，也就是NATS背后的公司，NATS是一个为构建现代分布式系统而设计的开源消息系统。在接下来的演示中……

<details>
<summary>Original English</summary>

**Speaker 9**: how when we talk about agentic engineering,

**Speaker 11**: we focus all of our attention on verification. How do we know the result is correct? But today, I want to focus on the specification instead. And more importantly, how can agents participate in specifying the system, not just building or verifying it? Now recently we partnered with multiple infrastructure providers to bring durable execution natively to their technology stack. One of them is Syndia, the company behind NATS, an open source messaging system designed for building modern distributed systems. For the rest of this presentation.

</details>

**Speaker 0**: 我们准备好了。

<details>
<summary>Original English</summary>

**Speaker 0**: we okay.

</details>

### 自我改进的软件工厂：开源新范式

**Speaker 5**: 大家好。我很兴奋能来到这里。我叫Zac Lloyd。今天我要讲的是自我改进的软件工厂，新的开源模式。基本上，我想谈谈我认为开发领域正在发生的变化。先简单介绍一下我自己。我曾是谷歌的首席工程师，领导过Google Docs的工程工作，做工程师已经超过二十年了。虽然我不经常发布东西，但过去六个月我一直在读大西洋月刊的代码。我是一家名为Work的公司的创始人，如果你不熟悉的话，它是一个开源的Agentic开发环境。你可能知道它是一个终端，公司就是这样起步的——基本上是一个内置了Agent的终端。我们几个月前将其开源，我想谈谈这段经历以及背后的动机。它是一个很受欢迎的开源项目，拥有超过六万颗GitHub星标。有几百人为它贡献代码，超过八十万活跃开发者在使用Work。但渐渐地，我们关注的焦点不再仅仅是终端的交互方面，更多的是如何自动化开发。我们主要会讨论这个。我的论点是，软件工程这门学科将变得更像工厂工程。我稍后会解释我的意思。但请记住，这就是我认为将要发生的事情。

<details>
<summary>Original English</summary>

**Speaker 5**: hello, everyone. I'm excited to be here. My name is Zac Lloyd. Today I'm going to be talking about self improving software factories, the new open source model. And basically, what I think is happening to development. A little bit about me just to begin. So I am a former principal engineer from Google. I led engineering on the Google Docs. I've been an engineer now for over twenty years, a long time. I'm not shipping frequently, but I haven't read Atlantic code in the last six months. And I'm the founder of a company called Work. If you're not familiar, it's an open source agentic development environment. You may know it as a terminal, that is how the company started. We were basically a terminal that has agents built in. We open sourced it a couple months ago, and I'm going to talk a little bit about that experience and the motivation for it. It's a popular open source project, over sixty thousand GitHub stars. We've had a couple hundred people contributing, over eight hundred thousand active developers who are using Work. But increasingly, we are focused not just on the terminal aspect and the interactive aspect of developers, but more so on how do you automate development. And we'll talk mostly about that. So the thesis that I have is that the discipline of software engineering is going to become something more like factory engineering. And I'll explain what I mean by this in a minute. But just keep that in mind, that's what I think is going to happen.

</details>

**Speaker 5**: 如果你看看过去十年开发领域的变化，我的天，变化太疯狂了。我们从一个聊天和自动补全的世界（比如Cursor或Copilot），发展到了现在这个阶段——我认为主要是交互式Agent。你坐在电脑前，告诉Claude Code做点什么，告诉Work做点什么。我相信在未来六个月到一年内会发生的事情是，我们将更多地走向自动化世界。但在那之前，先快速做个调查：在座有多少人在构建Agent？几乎百分之百。有多少人通常同时使用多个Agent？又是几乎所有人。有多少人现在正在运行Agent？我不会生气的。如果我有票，我也会这么做。有多少人是在云端运行Agent的？好奇问一下。看起来不到一半，但仍然不少。有多少人已经在内部建立了一个系统来自动化整个开发生命周期？从分类、规约、实现、审查……有些人已经在做了。所以这就是将要发生的事情。我相信每个有规模的项目都会拥有类似这样的东西，它看起来会像这个大的循环。每个人都在谈论循环。循环本身并不复杂。这个循环说的是一个云软件工厂。这个循环基本上就是软件开发生命周期，是同一回事。简单过一下这个循环：想法从顶部进入，Agent进行分类。如果事情很复杂，他们会进行规约——这些蓝色的框是人类介入点，人类会审查规约。Agent进行实现，人类和Agent审查代码。Agent进行验证，人类审查你要发布的产品，然后你进行监控，如此循环往复。这就是我认为开发最终会呈现的样子，无论好坏。

<details>
<summary>Original English</summary>

**Speaker 5**: If you look at development over the past decade, it's crazy how it's changed. We've gone from a world of chat and auto completes, Cursor or Copilot, to the phase we are in now, which I consider to be mostly interactive agents. So you're sort of sitting at your computer, and you are telling Claude Code to do something, you telling Work to do something. And I believe what's going to happen over the next six months, a year, hard to predict, is that we're going to move much more towards the world of automation. But before I dive into that, just a quick show of hands: how many folks here are building agents? Almost everyone, makes sense. How many folks are building typically with multiple agents at one time? Again, almost everyone. How many people are running an agent right now? I am not offended. I would get the ticket, I'd be doing it. So how many folks are running agents in the cloud, out of curiosity? That looks like less than half, but still significant. And how many folks have set up a system internally to automate the whole of the software lifecycle? So everything from like triaging, specifying, implementing, reviewing... some hands. So some people are doing this. So this is what's going to happen. Every project of significant size, I believe, is going to have something like this, and it's going to look kind of like this big loop. And everyone is talking about loops. There's nothing that complicated about loops. This loop says a cloud software factory. This loop could literally just say the software development life cycle. It's the same thing. But just to go through this loop: ideas are going to come in at the top, agents are going to do triage. If something is complicated, they'll spec — these old blue boxes are where humans come in, humans will review the spec. Agents will do the implementation, a human and agent will review the code. Agents will verify, human will review the product you ship, and then you monitor and round and round you go. And this is what software development, for better or worse, I think is going to end up looking like.

</details>

**Speaker 5**: 所以我重复一下我的论点：如果这就是软件工程未来的样子，那么软件工程师将会是那些设计和管理这些工厂的人。我在演讲开始时承诺过，并且我在演讲标题里写了，我会谈谈开源。所以我想花几分钟谈谈这个。我提开源是因为我们开源的主要原因之一就是为了建立一个公共工厂。这是我们构建的一个叫做build.work的网站截图，它展示了我们系统中所有正在流转的Issue，它们处于什么状态，哪些Agent在处理它们，哪些贡献者在处理它们。这有点像是一个在规模上运行的原始工厂。它运行得并不完美，但它确实在运行。我们开源的原因之一就是为了尝试构建这个。总的来说，我认为在Agentic开发的时代谈论开源是很有趣的。这是一张很棒的图表，你一看就懂。它表明构建软件正变得越来越便宜。其推论是，克隆软件也变得微不足道。所以如果你从事软件行业——我不知道在座有多少人直接从事软件业务——但如果构建软件是免费的，那么构建一个软件业务就非常困难。你很难捕获价值，尤其是当竞争对手可以克隆的时候。所以我给大家的一个重要建议是：你们要做的第一件事就是为你们的代码申请专利。开玩笑的，别这么做，这完全是个玩笑。我的第一步显然是，你需要有一个伟大的产品。这一点一直如此，但我认为，光有伟大的产品可能从来都不够，但现在更是如此。如果你认为仅仅通过构建和发布一个伟大的产品就能建立一个伟大的企业，你很可能不会成功。你需要产品之外的优势。这些优势可能是分销渠道、生态系统、强大的品牌、数据护城河，或者资本。但如果你是一家初创公司——我来自初创公司世界——你通常没有这些优势。而你仍然想要突破。我建议的方法之一就是公开构建。

<details>
<summary>Original English</summary>

**Speaker 5**: So I repeat the thesis, which is that if this is what software engineering is going to look like, software engineers are going to be the ones who end up designing and managing these factories. Now I promised at the beginning, and I put it in the title of the talk, that I would talk about open source. And so I want to do that for a few minutes. I bring up open source because one of the main reasons that we open sourced was to build a public factory. And so this is a picture of this website we built called build.work, which shows all of the issues that are flowing through our system and what state they're in and what agents are working on them, what contributors are working on them. And it's kind of like a proto-factory done at scale. It's not working perfectly, but it is working. And one of the reasons we open sourced was to try to build this. Just in general, I think it's interesting to talk about open source in the time of agentic development. This is a really super graph, but it's like, you get it. It's like it's becoming much cheaper to build software. A corollary of that is that it's becoming trivial to clone software. And so if you are in the software business — I don't know how many folks in this room are in the software business per se — but it's very hard to build a software business if it's free to build software. It's hard to capture the value, especially if a competitor can clone. And so my big takeaway, or big tip, for everyone in here is: the first thing you should do is patent your code. I'm kidding, don't, this is a complete joke. Don't do this. My first step is obviously, you need to have a great product. This has always been the case, but I would say a great product probably was never enough, but even now more than ever, if you think that you're going to build a great business just by building and shipping a great product, you're probably not gonna succeed. You need advantages beyond the product. And so those advantages could look like distribution, ecosystem, could be that you have a great brand or data moat, you might have capital. But if you're a startup again — I'm coming from the startup world here — you just don't have these advantages. And so you still want to break through. And one of the ways that I suggest doing this is by building in the open.

</details>

**Speaker 5**: 需要说明的是，Work花了五年闭源开发才达到现在的状态，然后我们决定公开构建。我来解释为什么。如果你公开构建系统，它有助于建立你的生态系统。它可以让你从在Hacker News上被骂变成被容忍。它可以提升你的品牌，建立社区。所以有很多好处。而且我认为一些传统上令人头疼的问题现在可以得到管理。比如，传统上开源的痛点可能是你会收到很多嘈杂的Issue，你会得到很多质量不高的PR，你可能会陷入代码审查的困境，你可能需要花很多时间验证变更。所以解决方案——我绕了一大圈才说到这一点——对于开源，或者至少对于Work来说，最终让我们决定这样做的是，我们构建了一整套自动化系统，实际上就是一个围绕管理开源项目的软件工厂。就像我说的，我认为这就是未来的样子。我会深入一点，给那些想为自己的项目构建类似东西的人提供一些更技术性的内容。

<details>
<summary>Original English</summary>

**Speaker 5**: So to be clear, it took Work five years of building closed source to sort of make the product, and then we decided to build in the open and explain why. If you build in the open, it helps build your ecosystem. It can take you from like hated on Hacker News to like tolerated. It can burnish your brand, create community. And so there's all these advantages. And some of the things that have traditionally been a pain can now be managed. And so like the traditional pain of open source might be something like you get a lot of noisy issues, you get sloppy PRs, you can end up in code review hell, you can end up having to spend a lot of time verifying changes. And so the solution — kind of a long way of getting to this — for open source, or at least for Work, the thing that made us finally decide to do this was that we built a whole set of automations, really a software factory around managing the open source project. And so like I said, this is what I think the future is going to look like. I'm going to dive in a bit, get a little more technical for folks who want to try to build something like this for their own projects.

</details>

**Speaker 2**: 嗯。

<details>
<summary>Original English</summary>

**Speaker 2**: Mm.

</details>

**Speaker 5**: 那么，一个有效的软件工厂的组成部分是什么？

<details>
<summary>Original English</summary>

**Speaker 5**: So what are the components of an effective software factory?

</details>

<!-- chunk 33/54 -->

### 软件工厂的核心要素

**Speaker 5**: 其实开始并没有那么复杂，或者说从高层来看，你需要一套自动化流程，你需要一种提供上下文和技能的方式，你需要一种在正确时机引入人类的方法，比如当事情在工厂里卡住的时候。然后一个非常重要的事情是，你需要一套自我改进的能力。所以把这想象成循环。如果你在开源世界里做对了，你就可以创造一个智能体帮助贡献者做贡献、帮助维护者做维护的世界。这里要强调一点，这并非开源世界独有的东西。我认为每个有规模的项目都能从这种方法中受益。我预测每家公司、每个开源项目最终都会在其核心拥有一个软件工厂，就像 CI/CD 成为标配一样——当然，你肯定有那个。也许我不知道那是十年前什么时候发生的。

<details>
<summary>Original English</summary>

**Speaker 5**: it's really not that complicated to start or at a high level. you need a set of automations. you need a way of providing context and skills. you need a way of bring humans in at the correct time to sort of like when things get stuck on the factory. and then a really important thing as you need some set of self improvement capabilities. so think of this is loops. and if you do this right in the open source world, you can get a, you know world where agents are helping contributors contribute, they're helping maintainers maintain. and one an emphasize, there's nothing special about open source here. i think every sizable project can benefit from this approach. and i predict that every every company, every open source project will have at its core a software factory kind of lect the way that CICD became just like, of course, you have that. maybe i don't know when that happened ten years ago.

</details>

### 参观工厂车间

**Speaker 5**: 让我们花点时间参观一下工厂车间。你不会想仔细看这个，这太多了。这张幻灯片的目的不是让你阅读工作流，而是说明工厂基本上是一个步骤图，你在其中定义如何为你的产品构建制品。而且每个产品看起来都相当相似。东西进来，它们流经各个步骤，在某些点卡住。大致来说，退一步看，有输入，输入实际上是想法。输入可能来自你的团队，也可能来自你的用户。输入本身可以通过某些渠道进入，你应该考虑这些渠道，比如问题追踪器是一个明显的渠道，或者 Slack、Teams 等沟通渠道。它们可能直接来自你的终端或 IDE，也可能来自你的监控系统。但总有一组输入将工作带入工厂。然后是分类，这是一个非常重要的步骤。我把它简化得非常简单，但你想要一个智能体，当问题进来时，它会查看问题并判断：如果这个问题很简单且没有歧义，就直接实现它。这就是你实际开始使用工厂的方式。如果问题很难，我建议让一个智能体生成规格说明。

<details>
<summary>Original English</summary>

**Speaker 5**: let's tour the attack the factor floor for a second year. so you're not going to look at this. this is too much. um the point of this slide is not to have you read the worflolow, it's that facfactory for or is basically a graph um of steps where you are defining like, okay, how to to offer get built for my product. and it looks pretty similar for every product. things come in. they flow through um they get stuck at certain points um and you know, broadly speaking, just to back out of second. so there's the inputs, the inputs are really ideas. um the inputs could be coming from your team. they could be coming from your users. um the inputs themselves can end come in through certain channels that you should think about, as like your cass trackers and obvious one or slack, your teams, like your communication channels. they could come directly from like your terminal RDE. they could come from your monitoring systems, but there's some set of inputs that bring work into the factory. there's trioge. this is a really important step. so again, i boiled down a sathing, very simple, but like you want an agent that is looking at issues as they come in into saying, you know, if this is easy, and this is unambiguous, just simplement it. and this is how you can actually get going with a factory. if finissuyou is hard. if i recommend having an agent that produces spespects.

</details>

**Speaker 5**: 你可以用很多不同的方式来做这件事，但我认为我们在工作中采用的方式非常有效，我推荐的方式是：有一个智能体，我们称之为产品规格智能体，它描述产品以及我们正在构建的变体；还有一个技术规格智能体，它描述架构和代码的形状。然后你有一个实现智能体，这基本上是一个在云端某处运行的编码智能体，它会创建一个 PR。你可以使用各种编码智能体来做这件事。你还有审查环节，这有很多方式。最痛苦的部分，我猜人们已经有点厌倦审查千篇一律的垃圾代码了。我会先让一个智能体做代码审查，然后随着时间的推移，这变成了一种风险管理练习，决定何时引入人类进行代码审查，但你需要有一个步骤让人类可以参与进来。对于某些类型的应用来说，这是一个非常重要的步骤：验证步骤。比如，如果你正在构建一个 AI UI，这涉及到让计算机实际使用智能体产生的代码，并生成视频和截图。当然，CI/CD 仍然在使用。还有监控。智能体在你的工厂里不会在代码发布后就停止工作，它们应该观察发布的内容：它崩溃了吗？它被使用了吗？然后循环往复，因为你把监控步骤的输出反馈回工厂的顶部。

<details>
<summary>Original English</summary>

**Speaker 5**: you can do this many different ways, but i think it's very effective the way that we do it at work that i recommend is having an agent, right? what we call a products spect and the tespeproduct spect describes the product and variance the are building towards text, back describthe architecture and the shape of the code. then you have an implementation agent. this is basically a coding agent that run somewhere in the cloud. it makes a def. you can use all sorts of coding agent for this. you have review this isn't many ways. the most painful part, like i expect, the people are a little bit tired of reviewing identical slop. i would have an agent two code review first, and then it becomes over time, like a risk management exercise of like when you bring in humans to do coter view, but you want to have a step in heir where humans can do it. this is a very important step for certain types of apps. the verification step. so this would be things like computer use you're building AA sort of UI having the computer actually used the code at the agent, produced and producing videos and screen shots. 对对对, CICD still use it, obviously. and in monitoring. so agents don't stop in your factory when code a shipped, they should observe what's been shipped? is it crashing? is it being used and round around you go because you take the output of this monitoring step? and you feeit back into the top of the factory.

</details>

### 构建工厂的挑战与架构

**Speaker 5**: 现在你可以尝试构建这个。我之前参加了一个我朋友 Anam 的演讲，Uber 已经构建了一个内部版本，这很酷。我想说，对于大多数组织来说，这真的取决于你处于什么阶段。你可以很容易地构建一个简单版本，但要构建一个真正能扩展的东西，可能就像……你可能应该专注于你自己的产品，而不是构建这个基础设施，因为最终你会想要很多东西。你不会想到要读这个，但东西很多，因为你确实要构建它。如果你构建它，你最终会得到看起来有点像这样的东西：你会有一堆让工作进入工厂的方式，这就是顶部区域；你会有一个控制平面，用于决定工作如何在你的工厂车间中分配；你会有实际工作发生的地方，那就是云沙箱，需要确定使用什么智能体、什么模型、什么工具；最后，我认为这是一个非常重要的事情，你会想要在你的工厂下面设置某种数据平面。这是一个让智能体记住它们做过什么、学习、并随时间改进的东西。

<details>
<summary>Original English</summary>

**Speaker 5**: now you can try and build this. and i went to a talk earlier that my friend anamm gave where uber has built an internal version of this. um and it's pretty cool. i would say, for most, you know, most organizations, it really depends where you are. you'll be able to build a simple version of this easily, but to build a thing that actually scales is probably like you's, probably focusing on your own product, not building this infrastructure because there's a lot of stuff that you end up wanting. you're not think king, not what to read this. it's just a lot of stuff because you do build it. um if you you it, it, you ll end up with something that looks kind of like this, which is um you're going to have a bunch of ways to getting work in the your factory. that's what's in the topiyear. you're going to have a sort of control ane for figuring out how work gets distributed across your factory floor. you're going to have the actual place where where the work happens. and so that's going to be cloud sandbox is it's going to be figuring out what agent trun. so what's the harness? what's the model? and then finally, i think this is a really important thing. you're going to want to set up some kind of data plane that sits below your factory. and so that's something that lets agents remember what theyve done, learn, improve overtime.

</details>

**Speaker 5**: 工厂不仅仅是一个产品，它也是一种思维方式。这让我回到了我一开始的论点：你需要衡量和改进。工厂就是……我不知道，你可以把这个比喻无限延伸，但你应该思考效率。这意味着，你交付了多少软件？它应该花费多少人力时间和 Token 时间？你需要衡量这些并尝试随时间改进。一个关键部分是创建循环。循环听起来复杂，其实并不复杂。循环基本上是让智能体通过观察它们正在做什么、在哪里失败来改进的方式。一个你会在工厂里想要的常见循环是技能循环。这意味着你的工厂智能体在运行技能，同时有观察者智能体在观察这些技能是如何被应用的，并尝试改进这些技能。例如，如果你有一个代码审查智能体，它留下了评论，而你的工程团队在纠正这些评论，你会希望有一个观察者智能体来查看这些情况，并基本上改进代码审查智能体，以便下次运行得更好。

<details>
<summary>Original English</summary>

**Speaker 5**: the factory is not just like a product. it's also a mindset. and this brings me back to the thesis i had at the beginning, you need a measure and improve. so factory is is where they i don't know. you can stretch this metaphor as far as you want, but like you should be thinking of efficiency. and so that means like how much software did you ship, how much should it cost in terms of human time and token time? and you're going to want to measure this and try to improve it over time. a key part of this is creating loops. so loops are again, they they sound complicated. they're not that complicated loops are basically ways of having agents and improum by like observing what they're doing, where they're failing. um and so a common kind of looops you're going to want to in your factory is like a skill loop. that means you're going to have your factory agents that are running skills, and they going to have observer agents that are seeing how those skills are being applied um for it shoes and trying to improve the skills. so for instance, if you had a code view view ent um and it was leaving comments, and a singer engineengineering, your team is going correcting. those comments you'd want an observer agent that would look at that and basically um improve the coter view agent for the next run.

</details>

### 工程师的新角色

**Speaker 5**: 这是留给大家思考的一个想法：活着的工程师在哪里？我认为你必须进入这种心态。

**Speaker 0**: 我正在非常努力地让我的团队进入这种心态。这并不总是容易的，你不仅仅是在构建产品，你还在构建构建产品的东西。这完全不同，这更像是流程工程或制造业之类的东西。你可能会想，好吧，这听起来很无聊？这无聊吗？这取决于，取决于你的乐趣在哪里。如果你的乐趣在于编写代码，我认为在座的每一位软件工程师都将编写更少的代码。但如果你的乐趣在于交付产品，那么现在是最好的时机。而这正是我找到乐趣的地方。我喜欢构建和交付东西。所以在座的每个人都会写更少的代码，但他们会交付更多，这将是一个权衡。但如果你像工厂工程师一样处理它，我认为你会发现仍然有一系列非常酷的工程挑战。你几乎可以把它看作是元工程，比如，你如何设计你的智能体系统，使其成为最好的工程系统？我认为这是一组非常引人入胜且有趣的挑战需要解决。

<details>
<summary>Original English</summary>

**Speaker 5**: this is one thought just to leave folks with, like, what is where is this live engineers? i think you're going to have to get into this mindset.

**Speaker 0**: and i'm trying very hard to get our team into this mindset. it's not always easy that you're not just building the product, but you're building the thing that builds the product. and that's like it's just different. it's more like process engineering your manufactureing or something like that. and you could think like, okay, maybe that's obbuomer like is that obomber is that you know? and it depends like it depends what joy. you get out a software n engineering if your joy is in writing the code. i think you're everyone in here who is a software engineer is going to be writing less code. but if your joy is in shipping product like it's never been a better time. and this is actually where i find my joy. it's like i like building in shipping the thing. so everyone in here is going to code less, but they're going to shiit more and that's going to be a trade off. but if you approach it like you're a factory engineer, i think you can see like that they're still a really cool set of engineering challenges. you could almost think it was like matter engineering, like, how do you engineer your system of agents to be the best possibility engineering? but i think is a very compelling and interesting set of challenges to solve.

</details>

### 实践资源与问答

**Speaker 0**: 就这些。对于感兴趣的朋友，如果你扫描这个二维码，我已经设置了一个开源入门仓库，任何想尝试构建自己的工厂智能体的人都可以做。这使用了 Warp 的智能体平台作为一部分，但老实说，你不必使用它，我不是想推销我们的产品。但这应该能让你很好地了解，比如，你想设置一个做分类的智能体，或者一个写规格说明的智能体，你实际上该怎么做？如何从工厂的理论走到实际实践？我不知道我们是否有能力在这里回答问题。我留了几分钟提问。如果有人有问题，否则我就结束了。好的，是的，你想构建这个。这工作量很大。是的，这也是一个很好的问题。所以有些人说这有点矛盾。我认为你应该这样想：每个人都会部署某种工厂，但是工厂的调优，比如这些技能是否适合我的领域……

<details>
<summary>Original English</summary>

**Speaker 0**: so that's it. uh for folks who are interested um this. if you follow the income as QR code, i've set up um a open source skittobrepo, where anyone who wants to try building their own factory agents can do it. this uses warps uh agent platform as part of it. but you honesay you don't have to use it, but i'm not trying to push ing into our product, but this should give you a good sense of like, okay, you want to set up uh, an agent that does um trios or an agent that does spectwriting. how do you actually do that? how do you get from like the theory of working with a factory too actually putting it into practice? um i don't know, we have the capability do questions in here. i saved a few minutes for questions. if anyone has questions, otherwise, i will. i wrap up, yes, yes ah, you want want to build this. it's a lot of more. yes, you are also a it's a great question. so so said some of it alalconcontraicictory, i think you should the way you should think of it is like everyone's going to deploy some sort of factory. but then the tuning of the factory, though, like are these the right skills for my domain,

</details>

<!-- chunk 34/54 -->

### 工厂隐喻与产品品味

**Speaker 0**: 这家工厂是否在以正确的方式制造我的产品？我仍然认为存在一系列有趣的工程挑战。在某些地方，你可以构建这个，但我认为，你很可能应该把大部分精力集中在为公司构建核心产品上。但还有很多调整和弄清楚如何让工厂为你的产品服务的工作，对吧？这个问题问得很好。是的。非常感谢。我有个问题。所以，如果你现在是一名即将毕业进入职场的大学生，你会把时间花在哪里？所以，这个问题（以防有人没听清）是：如果我是一名即将毕业进入职场的大学生，我会怎么做？所以我认为，在这个新世界里，最重要的技能是适应能力。我认为那是批判性思维。这是你可以学习的能力。我确实认为——我不知道你是否是计算机科学专业的学生——但我仍然认为，理解底层系统和架构，并能够推理和理解，我认为，能够理解代理所编写的代码，有着巨大的价值。我开始写代码了。所以我会专注于这些技能。而且，我不知道，我们正在以比以往任何时候都大的规模招聘。有很多关于人们因为AI而没有被雇佣的误导性信息，但这并不是我们的经验。到目前为止，我所寻找的是真正具有适应能力、以产品为导向的思考者，他们能够解决基本问题，成为问题解决者，即使底层技术发生变化。是的，我想还有时间再问一个问题：那产品品味呢？所以问题是，产品品味呢？以及如何真正构建有用的东西？我认为这个问题可能问得对，也许框架是这样的。想法从何而来？所以我认为，工厂这个比喻，我倾向于使用它，是因为我觉得它确实有道理，但它听起来可能有点机械化或非人性化。我仍然认为，在这一切之下，唯一重要的是：你是否在构建有用的东西？如果你有一个工厂，它生产出来的都是没人关心的垃圾，那还有什么意义？我认为人类的品味、人类的输入、人类的产品直觉，人类在那些你无法自动化的接触点上进行引导，是绝对至关重要的。这就是我所做的。我试图弄清楚客户想要什么，人们想要什么，什么对他们有价值。所以我认为这绝对是关键点。我想时间到了，所以我得走了。希望大家喜欢这次聊天，非常感谢邀请我来发言。

<details>
<summary>Original English</summary>

**Speaker 0**: Is this factory building my product in the right way? I still think there's a bunch of interesting engineering challenges. And for some places, you can build this, but I get I think, think, think, think that you, you should probably be focusing on building the core product for your company for the most part. But there's a bunch of like tuning and like figuring out how to make the factory work for your product, right? That matters is a great question. Yes. Is that thank you so much. I had a question. So if you were a college student right now, yes, graduating and entering the workforce where would you spend your time yet? So the question in case people couldn't hear was like if I was a college student graduating and entering the workforce right now. So I think that the most important skills in this new world are adaptability. I think that's critical thinking. It's like the ability which you can learn. I do think I don't know if you're a computer science student, but I still think there's a ton of value in understanding like the underlying systems and architecture and being able to reason and understanding, I think, could understand the specs that agents have written. I started writing. So I would focus on those skills. And like, I don't know, we're hiring more people than we've ever hired. There's a lot of kind of like misdirection around like, you know, people not being hired because of AI, that's not our experience. So far and what I'm looking for are like really adaptable product focused thinkers who can make basically any problem, solve problem solvers even as the underlying technology changes. Yeah, I think of time, for one more question is what about the like? So the question was, what about the product taste? And like how do you actually build useful? I think that's probably right, like maybe the framing. And like where do the ideas come from? So I think that um there's a problem with the, the factory metaphor, and I'm like leaning into it because I think that's that. There's something to it is that it can kind of sound like um mechanizing or dehumanizing. Um and I still think underlying all of this. The only thing that matters is like, are you building something useful? And if you have like a factory that is like turning out stuff that no one cares about. It's like what's the point? And I think that human taste, human input, human product sense, humans like guiding at those touch points where you can't automate stuff is that absolutely like essential. And like that's like what I do. I'm trying to figure out what what do customers want, what do people want? What's can be valuable to them. So I think that's absolutely key point to it. I think I'm out of time, so I have to go. I hope folks enjoyed this chat really grateful for being invited to speak.

</details>

### 生产中的AI代理：OpenGov的实践

**Speaker 2**: 非常感谢大家。接下来是关于生产中的AI代理，具体是OpenGov如何构建和扩展OG Assist。

**Speaker 4**: 所以，嗯，这个演讲将会包含大量精彩内容。我们会讨论AI代理，会讨论我们的框架，会讨论评估、可观测性、追踪，还会讨论工具和技能。这里面会有很多好东西。我们会向大家介绍我们在OpenGov所做的事情，以及我们如何在生产环境中以我们运营的规模来运作。这样你们就能看到一个关于AI代理的真实用例和工作负载。嗯，那么，话不多说，让我们开始吧。好的，议程。快速过一下我们今天要讲的高层内容。啊，我会先向大家简单介绍一下OG Assist。嗯，我是OpenGov的，我会告诉大家这一切的起源故事。啊，我们会讨论OG Assist，嗯，一个重大的赌注——Effect，嗯，稍微深入一下我们的代理循环，我们会讨论A2A协议、评估和沙盒。我们会讨论如何处理长上下文。我们会讨论监控、可观测性以及我们如何收集反馈，以及我们如何根据反馈进行迭代。最后，嗯，我们还会讨论工具和技能，以及OpenGov如何不仅将AI用于我们提供给客户的外部服务，也用于改进我们内部的开发工作流程。在继续之前，先简单介绍一下我自己。我的名字是Gabe，我是OpenGov的一名软件工程师。我在AI代理团队工作，我是帮助构建OG Assist以及你们今天将看到的一些系统的人员之一。简单介绍一下OpenGov。OpenGov是一家软件公司，其使命是推动更高效、更经济的政府。嗯，所以OpenGov销售ERP软件，涉及预算、采购、资产管理和许可等领域。嗯，我们大约在四年前成立。很酷的是，嗯，我们有一个叫做OG Assist的东西。OG Assist是我们所有产品导航栏顶部的一个小按钮。很酷的是，嗯，我们所有的产品套件和产品团队都构建了工具和技能来驱动这个按钮。例如，如果我打开这个，嗯，如果我点击这个按钮，我打开OG Assist，它会说，嘿，嗯，我要问关于Racos的问题，这非常特定于你正在查看的当前产品，你可以看到在这个聊天界面里，我能够与代理对话。代理能够进行工具调用，以查找该套件中的数据信息。所以，能够通过我们构建的名为OG Assist的能力来创建这些第一方的体验，真的非常酷。

<details>
<summary>Original English</summary>

**Speaker 2**: So thank you all very much. Agents in production.

**Speaker 4**: Specifically how OpenGov built and scaled OG Assist. So um this presentation is going to be jam packed with just so much good stuff where we talk about AI agents, we're going to talk about our harness, we're going to talk about um evals, observability, traces, we're going to talk about um tools and skills. Um it's there's going to be a lot of good stuff in here. We're going to talk to you guys about what we do at OpenGov and how we operate at the scale that um we operate at um in production. So you'll be able to see a real use case and workload uh with AI agents. Um so without further ado, let's get started. Okay, agenda. So just really quickly going to go through um high level. What we're going to talk about today. Ah I'm going to tell you guys a little bit about OG Assist. I'm uh OpenGov is I'm going to tell you guys the origin story of how this all kind came to be. Ah we're going to talk about OG Assist, uh big bet on Effect, uh, a little bit into our agent loop, we're going to talk about the A2A protocol, evals and sandboxing. We're going to talk about how we manage long context. We're going to talk about um monitoring, observability and how we collect feedback um and how we iterate on that feedback. We're going to, lastly, uh also talk about tools and skills and how at OpenGov um we use um AI not only externally that we uh serve to customers, but also internally to improve our development workflows. Just a little bit about me before you go any further. My name is Gabe, I'm a software engineer here at OpenGov. I work on the AI agents team, and I'm one of the folks that helped build um OG Assist and some of the systems that you guys will be seeing today. So a little bit about OpenGov. OpenGov is a software company um on a mission to power more effective and economic government. Um so OpenGov sells ERP software for things like budgeting, procurement, asset management and permitting. And um we were founded about four years ago. And what's cool is um we have this thing called OG Assist and OG Assist is this little button on the top of all of our products in the navigation bar. And what's cool is um all of our product suites and product teams um have built tools and skills in order to power this button. So for example, if I open up um this, um if I click this button, I opened up OG Assist says, hey, um I'm going to ask about Racos, which is very specific to the current product that I'm in, and you can see that inside of this kind of chat interface, I'm able to speak to an agent. And the agent is able to make tool calls in order to um look up information against data inside of that suite. So it's really cool um to be able to kind of first party create these experiences through the capability that we built called OG Assist.

</details>

### OG Assist的起源与Effect赌注

**Speaker 1**: 对。

**Speaker 4**: 好的。所以，简单讲一下这一切是如何发生的。嗯，不久前，我们看到AI真的开始起飞了，在一种原则性的方式下，AI能力团队邀请我加入。嗯，我立刻答应了，OG Assist开始发展壮大。我们开始将OG Assist系统集成到我们的产品中，不仅是我们后端的能力，还有我们前端的能力。所以你会看到，我们赋予代理的能力之一就是能够看到屏幕上的内容，并基于页面上的内容采取行动。所以你可以看到，我在这里问代理，嘿，屏幕上是什么？你能高亮显示一些我接下来可以采取的步骤吗？所以你可以看到代理在这里思考，它说，好的，我有哪些工具可用？嘿，让我去高亮一些你实际上可以点击的东西，并告诉你更多关于它的信息。这只是OG Assist系统的一个能力。这只是这一切如何发生的一个小故事。所以，关于Effect的重大赌注。嗯，我真的很想包含这张幻灯片，因为嗯，在代理团队，我们下了一个巨大的赌注，押注Effect，可以说，这个赌注已经获得了丰厚的回报。嗯，我们使用Effect。Effect是一个TypeScript库，它是开源的，帮助你编写更好的TypeScript代码。嗯，你知道，它包含了很多东西，比如Schema，比如Expo。如果你曾经用过，它还有用于错误处理、日志记录、追踪的东西，里面包含了很多功能。它确实有助于编写更好的代码和更好地组织代码。它有助于架构设计和快速搭建新服务。对于我们代理团队来说，它确实帮助我们设计和构建了核心的代理循环。所以你们会在整个演讲中看到，Effect在我们团队中是如何获得回报的。嗯，我们在OpenGov非常喜欢Effect，我们鼓励其他人也试试看。嗯，是的，我们继续。

<details>
<summary>Original English</summary>

**Speaker 1**: Right.

**Speaker 4**: Okay. So just a quick story about how this all came to be. So um a little while back, we saw that AI was really starting to take off in a principled way, the AI enablement team asked me to join. And um instantly, I said, yes, and OG Assist started to grow. And we started integrating OG Assist system into our products and not only our backend capabilities, but also our frontend capabilities as well. So you'll see that one of the capabilities that we give the agent is to um see what's on the screen and and take action on what's on the page. So you could see that um I'm asking the agent here, hey, what's on the screen? Can you maybe highlight um some the next steps that I could take? So you can see that the agent here is thinking, it's saying, okay, what tools do I have available to use. And hey, let me go in and highlight something that you could actually click on and tell you more about it. So just a capability of the OG Assist system. Just a little short story about how this all came to be. So the big bet on Effect. Um so I really wanted to include this slide because um here on the agent team, we made a huge bet to bet on Effect and suffice to say it's paid off in dividends. Um we write Effect. So Effect is this library for TypeScript. It's open source, and it helps you write better TypeScript code. Um you know, it's got a lot of stuff like Schema, like Expo. If you've ever used that, it's also got um things for error handling, for logging, for traces, it's just got so much in there. It really helps write better code and structure your code better. And it helps with architecture and spinning up new services. And for us on the agent team, it really helped design and build the core agent loop. So you'll see throughout this presentation sprinkled in um how Effect on our team uh has paid off in dividends. So we really love Effect here at OpenGov, and we encourage other folks to try it out. Um yeah, let's keep going.

</details>

### Effect原生代理循环

**Speaker 4**: Effect原生代理循环。最初，我们使用的是LangGraph。在团队开始扩大规模、我们的用例开始演变之前，这都还好。所以我们决定转向我们自己基于Effect的代理循环，以便对这个代理循环拥有完全的控制权。这样，当我们有复杂的用例或需要构建的功能时，我们可以直接深入其中。我们完全控制了代理循环，不仅如此，现在我们完全基于Effect。所以，你从Effect获得的所有好东西，现在都可以传播到整个代理循环中，比如追踪、结构化、并发、日志记录。一切都得到了更精细的控制，这确实让我们能够从头开始充分释放我们自己代理循环的全部潜力。

<details>
<summary>Original English</summary>

**Speaker 4**: The Effect native agent loop. So originally, we were on LangGraph. And that was fine until the team really started to scale, and our use cases started to evolve. So we decided to move over to our own kind of Effect native agent loop to have full agency over this agent loop, such that when we have complex use cases or features that we need to build, we could kind of get in. We had full control of the agent loop, but not only that, but now we're fully on Effect. So all the cool things you get with Effect now are propagated throughout the entire agent loop like the tracing, structured concurrency, logging. Everything is more fine-grained control, and it really allows us to really unlock the full potential of having our own agent loop from the ground up.

</details>

**Speaker 5**: 嗯。

**Speaker 4**: 所以我想提到的另一件事是，在左边你会看到一个代码示例。这基本上是我们正在使用的Effect循环的核心。我们使用一个叫做Effect AI的包。在那个包里，有一个叫做Chat和LanguageModel的东西。所以通过Chat，你可以实例化一个AI聊天，例如，然后你可以使用streamText函数来流式传输文本，你可以传入一个提示，它会在底层使用一个语言模型。由于我们做的是依赖注入，如果我们想热切换到另一个模型，我们可以传入一个不同的语言模型。

<details>
<summary>Original English</summary>

**Speaker 5**: Uh.

**Speaker 4**: So another thing I wanted to mention is on the left you'll see a code example. This is really the basics of the Effect loop that we're using. We're using this thing called the Effect AI package. And in that package, there's this thing called um there's a Chat and a LanguageModel. So with the Chat, you can instantiate an AI chat, for example, and then you could stream text using um that kind of streamText function, you could pass in a prompt and it'll work with a language model under the hood. Since we're kind of doing dependency injection, we could pass in a different language model if we were to hot swap to another one.

</details>

<!-- chunk 35/54 -->

### 完全掌控智能体循环

**Speaker 4**: 例如。所以，真正完全掌控我们自己的智能体循环，就给了我们所有的操作杠杆。这确实解锁了模型的全部能力，也让团队对这个循环拥有完全的自主权。

<details>
<summary>Original English</summary>

**Speaker 4**: for example.

**Speaker 4**: so really just having full roll of our own agent loop,

**Speaker 4**: just kind of gives us all the levers.

**Speaker 4**: and it really just unlocks the full capability of the model and for the team as well to have full agency over this.

**Speaker 4**: this loop.

</details>

### 智能体间协议的价值

**Speaker 4**: 不，我想提的是智能体间协议（Agent-to-Agent Protocol）。在Agency这边，我们在这个协议上取得了很大的成功。这个协议是Google创建的一种开放协议，用于智能体之间的通信。我们发现它在定义我们的智能体路由时非常有用，例如，在后端，我们的模型和模式都遵循这种智能体协议。所以我们建模……例如，有一种叫做智能体卡片（Agent Card）的东西，就像你在这里看到的，它包含了智能体的名称、描述等等，对吧？拥有这种严格的协议，这种严格的规范，确实推动了我们的开发进程和团队对齐，因为我们所要做的就是遵循这个规范。我们知道这就是我们前端和后端都会消费和生产的契约。所以，嗯，我认为这对我们非常有帮助。而且很酷的是，A2A有很多扩展，对吧？你可以扩展协议，添加元数据之类的。还有A2UI。嗯，所以有很多有趣的东西，嗯，在A2A协议中，嗯，这就是对我们有效的方法。所以分享给你们。

<details>
<summary>Original English</summary>

**Speaker 4**: no,

**Speaker 4**: the thing i wanted to mention is the agent to agent protocol.

**Speaker 4**: so here on the agency,

**Speaker 4**: we've had a lot of success with this protocol.

**Speaker 4**: so this protocol being the protocol that google created kind of an open protocol for agents that in our communicate.

**Speaker 4**: but um we found this very useful for um defining our agent rourouts,

**Speaker 4**: for example,

**Speaker 4**: in the back end and our model and our schema to follow this kind of a agent protocol.

**Speaker 4**: so we model.

**Speaker 4**: so for example,

**Speaker 4**: there's this thing called an agent card,

**Speaker 4**: what you see here,

**Speaker 4**: and it's got the name of the agent,

**Speaker 4**: a description exetra,

**Speaker 4**: right?

**Speaker 4**: and having this kind of a rigorous protocol.

**Speaker 4**: this rigorous spect really helped drive our development and drive alignment,

**Speaker 4**: because you know,

**Speaker 4**: all we had to do was um gying with this spect and folall.

**Speaker 4**: this spect.

**Speaker 4**: and we knew that this was kind of the contract that our front and and back in with both consume and and produce.

**Speaker 4**: so um this uh,

**Speaker 4**: i would say also has been um very helpful for us.

**Speaker 4**: and and what's really cool is a to a has a lot of extensions,

**Speaker 4**: right?

**Speaker 4**: so you can extend the protocol um adding like meda data.

**Speaker 4**: um there's also a to UI.

**Speaker 4**: um so lots of fun stuff,

**Speaker 4**: uh with a to a protocol,

**Speaker 4**: uh h is kind of what's worked for us.

**Speaker 4**: so to sharing that with with you folks,

</details>

### 反馈与评估：迭代的关键

**Speaker 4**: 反馈与评估。这里的引语是“发布是起点，而非终点”。我们在AgencyScene上做的事情是，我们有多种方式进行评估和收集反馈。显然，你知道，会有用户打电话或发邮件给我们，或者直接告诉我们。但主要的方式是我们有“赞”和“踩”的机制。在这里，嗯，用户可以告诉我们，“嘿，这个效果很好，这是个很棒的回复”，或者“那不是个好回复”。我们能够利用那个信号进行迭代，我们可以把它带回去，帮助改进未来的回复。嗯，我们还有自动评估。所以，在我们的CI中，我们有针对实际完成的评估。我们可以测试提示词是否……嘿，它是否命中了一些工具？是否做了它应该做的事情？这也有助于提高我们的准确性。所以，这些自动评估与收集反馈相结合，确实很有帮助。这帮助我们改进了我们的工具、技能和协调性，这就是我们能够如此快速迭代的原因。

<details>
<summary>Original English</summary>

**Speaker 4**: feedback and evots.

**Speaker 4**: so here the quote is shipping is the start,

**Speaker 4**: not the finish.

**Speaker 4**: so what we do here on the agenscene is we have kind of multiple ways we do evalils and collect feedum.

**Speaker 4**: obviously,

**Speaker 4**: you know,

**Speaker 4**: will have foks s call in or email us or or just let us know and tell us.

**Speaker 4**: but the main way is we have the stumbs up and dumbs down mechanism.

**Speaker 4**: and here um someone is able to tell us,

**Speaker 4**: hey this.

**Speaker 4**: this work really well.

**Speaker 4**: this was a great response,

**Speaker 4**: or that wasn't a great response.

**Speaker 4**: and that signal,

**Speaker 4**: we taken reable to iterate on um and we could take it back and help and prove um you know,

**Speaker 4**: the response in the future.

**Speaker 4**: um we also have automated evalils.

**Speaker 4**: so in in the in our CI,

**Speaker 4**: we we have evalils that run against real completion.

**Speaker 4**: so we could test the prompt against.

**Speaker 4**: hey,

**Speaker 4**: did it hit some tools did to do what it's supposed to do.

**Speaker 4**: and that also helps with our accuracy.

**Speaker 4**: so those automated eevalls and conunction with collecting feedback really help.

**Speaker 4**: and so improve are our our ools ls.

**Speaker 4**: our skills are harness ness,

**Speaker 4**: and that's really how i were able to iterate so fast.

**Speaker 4**: and so quickly,

</details>

### 人在回路中

**Speaker 4**: 人在回路中。这是我们构建的一个很酷的功能，我们在智能体循环中确定性地设置了，如果某个工具调用需要批准的话。所以，如果智能体尝试……

<details>
<summary>Original English</summary>

**Speaker 4**: humans in the look.

**Speaker 4**: so this is really coofeature ure built t where we demministically in our up the agent loop,

**Speaker 4**: if there is a tool call approval required.

**Speaker 4**: so if in agent ttrists,

</details>

### 为何我们仍是瓶颈？

**Speaker 7**: 好的，大家好。我是Eighent Craft的创建者，我也创建了MCPYI，它后来变成了MCP Apps和MCCP指导委员会。还有很多其他东西。但我们在这里要讨论的是为什么我们要“滚雪球”式地发展，以及为什么我们不必如此。嗯，正如大家所知，基于用户和日常的智能体非常棒。它们能做的事情太多了，从生成猫咪表情包到B2B SaaS应用。既然它们如此出色，我们不得不问，为什么我们还不是不可阻挡的？为什么不是每个人都拥有一支能做任何他们想做的事情的智能体大军？按理说这应该相对简单。我的意思是，你只需要一堆模型提供者，然后启动25个云代码引擎，就搞定了。但现实是，要做成这样的事情并不那么简单。首先，你真的想要使用智能体。其次，一旦你真正启动它们，每一个智能体都需要你引导、指挥和审查它们。当规模扩大时，这简直令人筋疲力尽。我们需要找到一种方法来扩展规模，让我们能够做到这一点而不会 burnout。所以，实际上，我们才是瓶颈。很酷的一点是，正因为我们是瓶颈，我们需要的技能是找到方法，让自己不会在每次使用智能体时都 burnout。

<details>
<summary>Original English</summary>

**Speaker 7**: okay,

**Speaker 7**: hi everyone.

**Speaker 7**: i'm in a sotomon.

**Speaker 7**: i am the creator of eighent craft,

**Speaker 7**: and i also created MCPYI,

**Speaker 7**: which became MCP apps and MCCP steering committee.

**Speaker 7**: and then a bunch of our stuff.

**Speaker 7**: but we hear to talk about why roll the ball on neck and why we don't have to be.

**Speaker 7**: so uh as you all know,

**Speaker 7**: and user b day agents are amazing.

**Speaker 7**: there's so much they can do from generating cat memes to b to b saataps.

**Speaker 7**: so if there are so amazing,

**Speaker 7**: we have to ask,

**Speaker 7**: why aren't we all unstppable?

**Speaker 7**: why doesn't everyone have an army of agents that does whatever they want,

**Speaker 7**: so it should be relativezy.

**Speaker 7**: i mean,

**Speaker 7**: you just have a bunch of modeitorors,

**Speaker 7**: and you spin up twenty five clouds code engines.

**Speaker 7**: and you're done.

**Speaker 7**: so the reality is that it's just not that simple to do something like that,

**Speaker 7**: you need to a really want to use agents.

**Speaker 7**: and secondly,

**Speaker 7**: once you actually spend them up each one,

**Speaker 7**: these these agents requires you to steer them,

**Speaker 7**: direct them,

**Speaker 7**: review them.

**Speaker 7**: and when it's a scale officially,

**Speaker 7**: it's just exhausting.

**Speaker 7**: we need to find the scalls to allow us to do it without burning out.

**Speaker 7**: so in reality,

**Speaker 7**: we are the ballonic.

**Speaker 7**: and the cool thing here is that why we are the ballonic,

**Speaker 7**: the skills that we need to do these things to find ourselves,

**Speaker 7**: not burning out every time you used agent or will ver.

</details>

### 从游戏到智能体编排：AgentCraft

**Speaker 7**: 所以，如果你试着把它和你一直在做的编程之外的事情比较，比如玩电子游戏，其实并没有太大不同。比如你在玩《魔兽争霸》或《星际争霸》，你有一堆不同的单位在跑来跑去，你需要理解它们在做什么并监督这一切。这和实际检查智能体并没有太大区别。所以我把这个概念推得更远，创建了AgentCraft，这是一个受游戏启发的编排器，试图将所有好的东西整合到工作中。让我们快速看一下它实际的样子，试着理解我们可以经历怎样的旅程，才能真正提升人类和智能体协作的感觉。这就是AgentCraft。这里确实有很多东西需要解读。所以我们只讲基础，快速看一下。这里看到的是一个智能体。嗯，它是云代码或开放代码的实际表示。无论智能体做了什么，你可以想象它可以在你的设备上被检测到，或者你可以直接从AgentCraft启动新的智能体。嗯，所以接下来你有像Codex和Open Code这样的设置。了解我的在的 at your command，这些智能体可以做任何事情。它们就是普通的智能体。所以我可以在那个漂亮的侧边栏里提示它们。它还有语音功能。所以这里有语音输入，嗯，让它为我做点什么，提示，提示。现在这些智能体可以做任何事情了。如果你环顾四周，你会看到地图上有许多不同的元素。所以，你有建筑物。这些建筑物代表功能，例如。如果你管理你的日志系统，嗯，你有像集成终端、集成Git这样的功能。你可以在这个空间内完成所有工作。对对对对。

<details>
<summary>Original English</summary>

**Speaker 7**: so along ah if you try to comare it to our stuff that you've been doing outside of programming,

**Speaker 7**: for example,

**Speaker 7**: playing video games.

**Speaker 7**: it's not really that different,

**Speaker 7**: like if you're playing workraft,

**Speaker 7**: for example,

**Speaker 7**: or seems,

**Speaker 7**: and you have a bunch of different units running around and need to understand what you're doing and supervise all of it.

**Speaker 7**: how definn't do that from from actually inspecting agents.

**Speaker 7**: so i took this concept too far,

**Speaker 7**: and i created agencraft,

**Speaker 7**: which is a game inspired orchestrator and tries to bring all that good stuff together into work.

**Speaker 7**: so let's take a quick look of what that actually looks like,

**Speaker 7**: can try and understand the journey that we can go through to really raise the feeling of how humans and agents can collaborate.

**Speaker 7**: so this is a agencraft.

**Speaker 7**: there's really a lot to unpack here.

**Speaker 7**: so we'll just go for the basics to a quick what to see here is an agents.

**Speaker 7**: um it's an actual representation of a cloud code or open clode.

**Speaker 7**: whatever agent did,

**Speaker 7**: you can imagine it can be detected on your device,

**Speaker 7**: or you can actually spond new ones directly from agent craft.

**Speaker 7**: um so nex said you have like codex and uh open code to setrum.

**Speaker 1**: 了解我的在的 at your command,

**Speaker 7**: and these agents can do everything.

**Speaker 7**: they're just normal agents.

**Speaker 7**: so i can just prompt them in this nice siypanit.

**Speaker 7**: it also has voice.

**Speaker 7**: so there's moking maddhere uh and just do something for me,

**Speaker 4**: prompt prompt.

**Speaker 7**: and now these agents can do whatever.

**Speaker 7**: and if you look around,

**Speaker 7**: you would see that the map has a bunch of different eleelements.

**Speaker 7**: so so you have buildings.

**Speaker 7**: these builings reprepresent fununctionalities for for exple.

**Speaker 7**: if if you can manyour your lulugging ssls um you have like integrated terminal integrated get.

**Speaker 7**: you can can do your all of your work from within this space.

**Speaker 1**: 对对对对,

</details>

### 提升规模：第一步是可见性

**Speaker 7**: 所以，既然我们有了这个，并且理解了基础，让我们看看我们能做什么来提升规模。第一步显然是可见性。我需要了解发生了什么。我的智能体在做什么？所以我有一个指挥中心，它向我展示不同的智能体，它们的任务是什么，它们最后做了什么，以及它们现在在做什么——我需要的一切，以便快速了解谁需要我的关注，谁不需要。对对对。

<details>
<summary>Original English</summary>

**Speaker 7**: so not as we have this and we understand the basics,

**Speaker 7**: let's look at what we can do and to raise the scening.

**Speaker 7**: so the first step is obviously,

**Speaker 7**: visibility.

**Speaker 7**: i neeneed to understand what's going on.

**Speaker 7**: what are my agents doing?

**Speaker 7**: so i have this my cpphal,

**Speaker 7**: and it shows me the different agents and what your task is and what the left me they did is and what their currencdoing everything i need to quickly understand who needs my attention and who doesn't 对对对,

</details>

### 地图与空间感知

**Speaker 7**: 第二部分是，不仅仅局限于这个，你还有一张地图。所以我可以把我的文件系统项目投射到地图上，我可以确切地看到我的智能体在做什么，不仅仅是看列表，我可以实际看到。好的，这个智能体正在处理这个目录或这个文件，而这些文件在地图上被表示为房间。所以我真的可以查看时间线，确切地看到每个智能体在什么时候做了什么，我可以利用这些信息，因为我们稍后会做审计，并用它来创建链接。我还可以创建很酷的东西，比如热力图。所以我很容易就能看到发生了什么。嗯，另一个方面是，现在我们有了这种可见性，但这还不够。我们需要能够对正在发生的事情做出反应。如果一个智能体需要我的注意，我需要能够快速跳转到它。就像视频游戏或即时战略游戏或《文明》一样，无论什么，你按下空格键，它就会带你到最近的需要你注意的东西，这样你就能很容易地了解情况，并从一个事情跳到另一个事情，回答问题或调整计划。

<details>
<summary>Original English</summary>

**Speaker 7**: the second part of it is when not just limited to this,

**Speaker 7**: you have a map.

**Speaker 7**: so i can take that,

**Speaker 7**: say my file system project it onto the map,

**Speaker 7**: and i can see exactly what my agents are doing,

**Speaker 7**: not just by be looking at the list of stuff,

**Speaker 7**: i can actually see.

**Speaker 7**: okay,

**Speaker 7**: this agent is not working on this directly or this file and the ile ile that presented as rooms on the map.

**Speaker 7**: so i can really look at the tron and see exactly what each agent did and when and i can take this nice information because we are do aucus later and use that to create lingages.

**Speaker 7**: and i can create cold stuff like heat maps.

**Speaker 7**: so i can really easily see what's going on.

**Speaker 7**: and 对嗯 the the the other aspect is that now does we have this visibility?

**Speaker 7**: that's not really enough.

**Speaker 7**: we need to be able to react to what's going on.

**Speaker 7**: if one needs my my attention.

**Speaker 7**: i need to be able to quickly jump to it so much like video games or RTS games or civilization,

**Speaker 7**: whatever you would click space bar and would just take you to the nearest thing that actually need your attention so you can really easily understand is going on.

**Speaker 7**: and jump from one thing to the other and answer questions or true plans.

**Speaker 1**: and you're jorun that was nice.

</details>

### 从可见性到自主性：解决信息过载

**Speaker 7**: 我的意思是，拥有这种可见性是一个很好的步骤，但这还不够。持续查看智能体在做什么，以及它们正在使用什么工具，这种粒度太令人疲惫了。所以我们还需要别的东西。原因是我们有两个主要问题：一是我们脑子里要装的东西太多了。如果我能理解发生了什么，我能看到一切，我大概能同时处理二十件事。如果你有这个庞大的编码项目或其他什么，我甚至无法思考下一步想做什么。所以我需要找到解决这个问题的方法。嗯，所以我们可以……我的意思是，我们可以告诉智能体，“去浏览我的代码库，找出下一步该做什么，为我创建任务”，我点击一个按钮，接受任务，然后某个智能体为我完成任务，这很有趣。嗯，这很酷，但问题在于，好吧，现在我有二十件事同时在发生，我需要像保姆一样照看每一个，这完全令人筋疲力尽。所以你可能会问，好吧，我们有智能体。正如我们已经确定的，智能体非常棒。所以我可以直接告诉智能体为我做这件事。现在，这有时被称为“软件工厂”，它们只是自主地做事。所以你可以给它一个你想要的大致方向，它会启动一个编排器，为你分解任务，然后全部运行起来，嗯，在这种情况下，是在一个本地的容器里。所以它是在一个隔离的环境中运行，我不需要做任何保姆式的工作。

<details>
<summary>Original English</summary>

**Speaker 7**: i meit's a nice step just to have that disability,

**Speaker 7**: but it's not pretty enough.

**Speaker 7**: it's pretty exhausting to keep looking at what the agents are doing in the grounllarity of what father are using and what tools are using at the moment.

**Speaker 7**: so we need something else.

**Speaker 7**: and the reason is that we have,

**Speaker 7**: like two main problems here,

**Speaker 7**: one is that there's this too much to hold in our heads.

**Speaker 7**: if it,

**Speaker 7**: if i can understand what's going on,

**Speaker 7**: and i can see everything i can't pretty like twenty things.

**Speaker 7**: at the same time,

**Speaker 7**: i can't even think of the next thing i wanto do if you have this huge coding project to whatever.

**Speaker 7**: so i need to find some way to fix that.

**Speaker 7**: um so we can.

**Speaker 7**: i mean,

**Speaker 7**: we can tell the agents ah no go through my cold base,

**Speaker 7**: find out what the next thing thing to do are creating tasks for me at clicicbutton.

**Speaker 7**: i accept the quest under some some agent,

**Speaker 7**: the desert for me,

**Speaker 7**: which is fun.

**Speaker 7**: uh it's cool,

**Speaker 7**: but the problem problem here is that okay,

**Speaker 7**: now i have twenty stuff going at the same time,

**Speaker 7**: and i have two babies sit each and everyone,

**Speaker 7**: and that is completely exhausting.

**Speaker 7**: so you could ask,

**Speaker 7**: okay,

**Speaker 7**: we have agents.

**Speaker 7**: agents are amazing as we've established.

**Speaker 7**: so i can just go ahead and tell the agents to do it for me.

**Speaker 7**: now.

**Speaker 7**: it's called software factories by the times were just doing stuff autonomously,

**Speaker 7**: so you can give it like a general sense of what you want.

**Speaker 7**: it would sporn d and orchestrator and break it down for you and run it all in well,

**Speaker 7**: in this case,

**Speaker 7**: it's a local um container.

**Speaker 7**: so if it is just dyand isolation,

**Speaker 7**: and i don't need to do any babysitting,

</details>

<!-- chunk 36/54 -->

### 从个人效率到团队协作，再到降低门槛

**Speaker 7**: 亚洲人对我来说就是这样。

<details>
<summary>Original English</summary>

**Speaker 7**: the asian does it for me.

</details>

**Speaker 7**: 对，嗯，除此之外，你还有循环（loops），这是现在大家都非常喜欢的功能。所以你可以做一些很酷的事情，比如直接告诉它，我知道怎么在推特上找酷的东西，如果你想构建或者开始使用，它就会在后台自动为你创建这些很棒的功能，你不需要前期做太多工作。

<details>
<summary>Original English</summary>

**Speaker 7**: 对，嗯， on top of that, you have loops, which everyone really likes right now, so you can do cool things like just tell that to, i know sccan twitter for cools, if you wanna build or sccan to get get up, and it will just create this nice features for you in the background, without tunion to do too much up front.

</details>

**Speaker 7**: 对对对，不好的地方在于，我的意思是，这很好，但是当我再次遇到问题时该怎么办？我知道我可以处理二十个，但即使是同时审查五件事，想要把它们都搞定也非常非常困难。

<details>
<summary>Original English</summary>

**Speaker 7**: 对对对， the bad thing is that i mean, this is nice, but what do i do when i have again? I know i would take twenty, but even five things to review at the same time, it's very, very hard to get that out of the way.

</details>

**Speaker 7**: 嗯。所以我做的是创建了这个，嗯，叫做审查视图的东西。这样我就能看到我需要的所有变更。我能看到哪个文件被修改了，如果你想一个文件一个文件地看，或者可以直接获取可视化证据。所以你可以实际看到变更的视频或照片。这样你就能非常快速地理解你想要什么，甚至可以并行运行几个实例，然后从中选出最好的实现方案。

<details>
<summary>Original English</summary>

**Speaker 7**: 嗯。 so what i did is create um this, like review view it. so i get the entire changes i need. and i get what file changed, if you want to go like file ile file, or can get just get visual evidence. so you can actually see videos of what change or photos of what change. so you can really quickly understand what you want or even run a few um instances in parallel and just speak the best implementation out of these.

</details>

**Speaker 7**: 所以现在我们有了这个，我们有了可见性和自主性。这很酷，我们似乎已经处在一个很好的位置，提升了我们所能做的事情的上限，但这仍然非常累人。

<details>
<summary>Original English</summary>

**Speaker 7**: so now as we have this, we have um visibility and we have autonomy. it's prety cool, like we reised like a pretty good place in raising the scening of what we can do evagents, but it's still pretty exhausting.

</details>

**Speaker 7**: 我的意思是，这很有趣，但现在我不得不问自己，我真的需要是唯一一个做这件事的人吗？整天只和智能体对话并尝试，这相当孤独。而且，你知道，如果你看看一个团队是如何运作的，例如，如果只有我一个人，那还好，但你有一个团队。我甚至可能不是审查正在发生的事情的合适人选。所以我需要别的东西，那就是协作。

<details>
<summary>Original English</summary>

**Speaker 7**: i mean, it was fun, but now i have to ask myself, do i really need to be the only one doing this? it's pretty lonely to just talk to agents all day and trying. and you know, if you look at um what a team does, for example, if it's just me, that's fine, but you have a team. i might not even be the right person to review what's going on. so i need something else, and that's something is collaboration.

</details>

**Speaker 7**: 我们可以让其他人加入我们。在 Agent Craft 中实现的方式是，我可以创建这些嗯，叫做作战室（war rooms）的东西，嗯，托管它们。它完全是本地的，但你可以通过隧道等方式让别人加入你。所以我可以创建一个房间，然后说，我的团队里有一个产品设计师。在这个例子里，是我妻子，我可以邀请她加入。她做她的事，她设计任何东西。而我作为工程师，不仅能看到她设计的那个东西，我不仅能在我的地图上看到它，我实际上可以拿过来，基于它继续工作，提示词就像她一样。嗯，所以我可以接受那个设计，跟进它，实现它，而她可以继续工作。

<details>
<summary>Original English</summary>

**Speaker 7**: we can just have other people join us. so the way that looks in agent craft is that i can create these um h called no war halls, warwhom, whatever uh host them. it's like complete his local, but you can do like tunnels and people can join you. and so i can create a room, and i say have a practy designer in my team. in this case, it's my wife, and i can i prove her out a wife fugi met. so i can i prove her and she does her thing, she designs whatever. and i as an engineer can not only see that that's that ter. i can not only see that on my map, i can actually take that and follow off off of it, prompt yeh that just like her. um so i can take that design, follow up on it, implement it while she keeps working.

</details>

**Speaker 7**: 这里很酷的一点是，不仅可以在人与人之间交接，还可以拥有这种共享工作空间，不再真正受限于 Git，我可以用 Git，但我不再受它的束缚。每个人都在协同工作。你可以考虑一下。在房间内的人之间，以及在智能体之间，也存在某种检查机制。所以你可以有一个非常好的公告板，精确显示每个人在做什么，每个智能体在做什么，它们都彼此感知，并且它们可以比通常情况更紧密地协作。

<details>
<summary>Original English</summary>

**Speaker 7**: and the cool thing here that not not can can hhand off for four can kind of have this shared work space ace, not not really bound anymore to get i kind use gget, but i'm not to rebound something. everyone is working together. you can sider. there's also some kind of checks between not only between the people within the room, but also between agents. so you can have really nice notice board of exactly what each person is doing, what each achating are doing are all aware of each other, and they can collaborate much more closely than you normally would be able to do.

</details>

**Speaker 7**: 所以例如，在这里我可以说，好的，我接手了这个设计任务。所以现在有一个弹窗，但这种方式也适用于不同设备。你可以用手机、网页、Telegram，或者任何你喜欢的平台。所以我们有了可见性、自主性和协作。我们成功地提升了天花板。现在，特别是对于高级用户来说，做非常激进的事情、使用更多智能体、做更多事情都成为可能。

<details>
<summary>Original English</summary>

**Speaker 7**: so for example, here i can say, okay, i took off this design task. so now now have a pop, but way this is also from devices. you can have like mobile and and i fleg telegramc and new telegram, whatever float your boat. so we have visibility and we have autonomy, and we have collaboration. so we managed to raise the feiling. it's now possible, especially if you're power users to do radicall stuff and use more agents and do more things.

</details>

**Speaker 7**: 但有趣的是，如果我看看收到的反馈，不仅仅是高级用户能够做更多事情。对我来说很酷的是，那些与智能体毫无关系、或者与生产力毫无关系的人也过来说，好的，我的孩子们非常喜欢它，他们一直用它来制作策略智能体，这是以前做不到的。或者有人因为玩《星际争霸》而偶然发现了它，现在他也能用它来做有生产力的事情了。还有很多其他的例子，它们把那些迄今为止还落后于时代的社群带入了这个新的生产力世界。

<details>
<summary>Original English</summary>

**Speaker 7**: but the interesting thing here was, and if loolook at the feedback i got, it's not just that power users were able to do more. the coolthing for me was that people that had even nothing to nothing to do vagents or nothing to do with productivity. uh come and say, okay, my kids really love it and do it all the time to to work as strate agents, which it didn't do until now, uh or someone that fununt out of colleft, because he plaay starar craft. and now it can certainly do be productive stuff with it and a much of other examples of kind of bring communities that so far were kind of behind into this new world of productivity.

</details>

**Speaker 7**: 所以我们需要提升天花板，但我们也需要降低门槛。我们需要某种方式，将世界上大概百分之九十的人带入这个智能体驱动的未来，而不会让他们感到疲惫不堪。

<details>
<summary>Original English</summary>

**Speaker 7**: so we need to raise the ceiling, but we also need to lower the floor. we need to have some kind of way to take, no, probably it around ninety percent of the people in the world and bring them into this igenentic future without having them burn out.

</details>

**Speaker 7**: 所以，我又一次走得太远了。嗯，这个项目暂时命名为 TVD，可能也叫 Loopers。这里的想法是，好的，为什么我们需要像 Agent Craft 这样的东西？它可能非常复杂，特别是如果你不熟悉智能体的基本原理，或者复杂的 UI，那可能会令人生畏。所以我们要尝试找到一个更低的共同点，让东西变得易于使用，尤其是在智能体能力更强的现在。

<details>
<summary>Original English</summary>

**Speaker 7**: so again, i took it too far. um and as this uh curtly named TVD, um potentially loopers, the idea here is, okay, why why do we need something like? you know what craft, which is potentially very complicated, especially might be even daunting if you're not into the grand ulity ity of what father are are, or what complex the UI is and kind of try to find a lower ddenominator of what makes stuff accessible, especially now that agents are much more capable.

</details>

**Speaker 7**: 所以，与其详细说明他们正在处理哪些文件，也许我可以让它更像一个手机游戏级别，有他们不断回来使用的项目，并使用循环。我们的东西依赖于智能体更加自主，有一个非常基础的层面：我提示，我得到结果。我可能不太关心具体方式，但如果我想，我可以看到它，并且拥有这种非常棒、互动且完整的体验，让我想再次使用它。

<details>
<summary>Original English</summary>

**Speaker 7**: so instead of in onarity or or ving, an exactly what files theyy're woron on, maybe i can have it more of a mobile game level, have projects that they keep returning to and use looks. and our stuff as that rely on agents being more autonomouous to have like a very basic level of i prompt. i get the result. i don't really can't perhaps about the way i can't see it if i want you and have this really nice, interactive and full experience that makes me want to come back to this.

</details>

**Speaker 7**: 嗯，显然，这只是一种可视化方案。它可能会引起一些人的共鸣，但可能对另一些人没有吸引力，因为我们并不都一样。对一个人来说看起来很棒很容易的东西，对另一个人来说可能非常困难。嗯，但我正在尝试寻找一种方法让它更可定制，尝试理解作为一个人，你需要什么才能理解并想要使用这些工具。所以这只是一个非常非常早期的草稿。嗯，但如果你想使用它，请告诉我。

<details>
<summary>Original English</summary>

**Speaker 7**: 嗯， and obviously, and this is one visualization. it can can really resonate with some people. but might not presenent tive others because we're not all the same and what may appear like amazing and easy to one person can appear very difficult to another. uh but uah, i'm trying to look at the way to make this more customizable, try and understand what it is that you, as a person need in order to understand. and want to use these tools. so this is a very, very early draft. um but if you want to use it, please let me know.

</details>

**Speaker 7**: 所以我们是瓶颈。我想我们现在已经充分证明了这一点。但是，让我们停止成为瓶颈并开启这个新未来所需的技能，只掌握在我们手中。所以我们是瓶颈，但我们不必如此。我希望你们能吸取生活中与你们相关的东西，并将其应用到未来。

<details>
<summary>Original English</summary>

**Speaker 7**: so we're the boallonenic. i think ''ve establish that pretty volunteer now. but the skills that we need to stop being the balloonic and enabled this new future are only with us. so we are the bonneck, but we don't have to be, and i hope that your can take what's relevant to you in your life and apply it forward.

</details>

**Speaker 7**: 所以我请求你们做两件事。第一，Agent Craft 已经发布了，你可以直接通过 `npx agent craft` 安装。Agent Craft 是一个网站。嗯，去做你的事吧。这个我刚给你们展示的新东西，可能叫 Loopers，还在实验阶段。嗯，我正在尝试了解大家的兴趣，以及人们真正在寻找什么，以获得他们想要的门槛和天花板。我还在摸索中，请表达你的兴趣，告诉我你在寻找什么，这样我才能知道下一步该怎么做。

<details>
<summary>Original English</summary>

**Speaker 7**: so i would ask you for two things. one agient craft is already out there like you can just index install. ageent craft is a website. um do your thing thing, this new thing that i just showed you popotitially uppers is still experimental. i'm so trying to understand the interest in what people are actually looking for to get the floor that they want toward the seeing that they want. i'm still try here and express your interest and tell me what you're looking forwso. i can know what to do do this.

</details>

**Speaker 2**: 谢谢。

<details>
<summary>Original English</summary>

**Speaker 2**: and thank you.

</details>

### 检索边界处的信号死亡

**Speaker 9**: 待会儿在结构化搜索的结尾见。今天，我的演讲题目是《检索边界处的信号死亡》。所以让我们深入探讨一下，什么是智能体？本质上，我的观点是，智能体是检索领域中失败的根源，特别是，如何让信号真正跨越平凡的边界，以及如何让你的智能体基本上无所畏惧。

<details>
<summary>Original English</summary>

**Speaker 9**: see you in good fend of stulied search. and today, my talk later use a signals die at retrieval boundary. so look into uh what are agents? essentially, my agent feels what is the cause of fiels in retrieval, particularly and how to make actually signals cross the trivial boundary and how to make your agent basically unconfair.

</details>

**Speaker 9**: 那么，我们开始吧。什么是智能体？智能体是一个拥有自主性的算法，能够推理、调用工具、与数字世界交互、检索记忆以完成任务。但这里缺少的一个主要环节是学习。它还应该从哪些有效、哪些无效中学习。

<details>
<summary>Original English</summary>

**Speaker 9**: so uh, pluit started. but what is an agent and agent does an agalym that has agency to reason involve those uh interact with digal world retrieve uh the memory to complete the task. but major loophihere is missing is a learning. it should also learn from what to work and what it didn't work suppose.

</details>

**Speaker 9**: 嗯，如果我必须解释什么是智能体，我可以通过 ReAct 智能体来解释。所以基本上，智能体从接收输入开始，嗯，在一个循环中执行它，嗯，调用工具进行检索和研究，然后在任务完成时暂停。这是非常基础的 ReAct 架构。缺少的一点是如何让智能体了解结果。所以智能体会在同一个任务上反复失败。

<details>
<summary>Original English</summary>

**Speaker 9**: um if i have to uh explain what is asient and i can explain through occasient. so if i have to explain uh, what agent does, i had explained with react agent. so basically uit from the agent ent, uh, execute it in a look, uh, calling to a reree al research and then pause when the dusk 's company. this is very basic react architecture. one thing that is missing is how to make agent the noledge on the outcome. so agent keeps feiling at the same task.

</details>

**Speaker 9**: 好的。Gartner 报告说，85% 的 AI 项目失败。结合各种调查和缺陷报告，问题归结为，大多数时候，轨迹是静态的。73% 的失败是因为检索、生成和上下文问题。所以我从某个地方看到一个帖子，我引用 Exit 的创始人说，嗯，我们一直在优化错误的东西，你在为错误的东西付费。我们一直在优化错误的东西，我们让错误的答案出现得更快、更便宜，而不是让正确的答案出现一次。

<details>
<summary>Original English</summary>

**Speaker 9**: k. gotland report said eighty five percent of air takes failing chin, concerts and mkancies to in a deflight repreport. the problem came out to be most of the time is that tratree was static, seventy three percent of like my fierce because of the hieve, not generation and contect stuff. so i have n't post from around sure. i sht the exit to your paincorn said, uh, we have been optimising for the wrong thing you are paying and not for for are opwrwrong things. we have been optimising for the wrong things we made wrong answers up here faster and cheabird had before got to make greicree one loone.

</details>

**Speaker 9**: 那么为什么这很重要？因为典型的智能体没有从结果中学习。所以在评估和行动之间缺少一个反馈循环。你的可观测性平台拥有所有的追踪数据。嗯，所有那些捕获每一次调用、每一次错误、每一次完成、每一次异常的数据，以及你用来判断输出是否正确（基本上是通过或失败）的所有评估，但这些评估并没有以任何方式反映在智能体的上下文或智能体的行动中。

<details>
<summary>Original English</summary>

**Speaker 9**: so why this this does does doesn't matter again. the type coomnize agents are not outcoming from. so there's n't missing milar, twtween, valils and action. your obsoability has all the traces. uh, all these staff that catch a absoilities. the star that catch every dounle, every airland, accomlition, every exceptions, you eva swijujuges ges, whether ffind that output was correct wrong, basically pass or fear, but these evalls are not reflected in agent context skills empdifies by agent action in any ways.

</details>

**Speaker 3**: 那个一一一个月，十一个一个个的一的一个。

<details>
<summary>Original English</summary>

**Speaker 3**: 那个一一一个月，十一个一个个的一的一个。

</details>

**Speaker 9**: 所以智能体无法访问昨天运行的原因。它运行的通过或失败的评估信号在仪表盘中死亡了，这就是缺失的环节。

<details>
<summary>Original English</summary>

**Speaker 9**: so the asian doesn't has any access to why yesterday is runs. h runs postor fear eva signal dies in the dash ford isn't n't missinginga.

</details>

<!-- chunk 37/54 -->

### 从手动优化到智能记忆系统

**Speaker 9**: 系统会消耗追踪信息、吸收 I Raad，并将两者都融入树中，供未来运行使用。

<details>
<summary>Original English</summary>

**Speaker 9**: a system that consume traces absorb iraad and can brt both into the tree without its for future runs.

</details>

**Speaker 9**: 所以这里有一个手动改进的环节，工程师实际上必须坐下来查看邮件，判断这个方案是否表现良好，然后意识到需要重新部署提示词。

<details>
<summary>Original English</summary>

**Speaker 9**: so there's a manual improvement, tax and engineer actually has to sit and see if the email and also will be perform well, realiate the proms redeploit.

</details>

**Speaker 9**: 他们同意进行模型重构，将我们的网络或 Ying 适配到定制模型上。为什么？我当前记忆系统感觉……为什么记忆系统被设计成实际上会增加响应？但嗯，事实并非如此。所以他们看到了我们现有的系统。

<details>
<summary>Original English</summary>

**Speaker 9**: a great you. they agreed to expense a model restructure, took our nets ts or ying to the custom models. why? i current memories feeling why memories was designed to actually add respese. but um it's not so they see uh what we we having as a current system.

</details>

**Speaker 9**: 当前的记忆系统基本上存储了用户差异、个人资料、对话历史，或者用于长期个性化，比如儿童体验，但并没有在现有生产环境中实现自我改进。

<details>
<summary>Original English</summary>

**Speaker 9**: uh and current memory is that they basically store user differences, profile conversation history or long ononlived personalization, such child experience ces no acself improving the existence for production.

</details>

**Speaker 9**: 如果你看看市场上已有的方法，市场正在推出一些手动方案，这些方案使用嵌入相似度来进行空引用和虚拟信号匹配。

<details>
<summary>Original English</summary>

**Speaker 9**: if you see uh already existing approach in the uh market, market is uh launching um does mannal, which does emptifed references ua virtual signal is as embedding simility.

</details>

**Speaker 9**: 我们有没有……它是否从市场中学到了什么？不能。所以我们提出了一些新的发现，这是一种基于对智能体执行任务的有用性来加权的相似度。

<details>
<summary>Original English</summary>

**Speaker 9**: 我们有没有 does it learn for mark could not. um so we have come up with something a new day discore, which is a similarity bit vadted by how useful it is for the agent to execute the task.

</details>

**Speaker 9**: 它实际上包含了历史请求和过去的项目。所以我们提出了智能体架构，让智能体带着这些经验进行训练。这是一个强化学习框架，让智能体无需重新训练、微调或手动提示工程，就能从经验中改进。

<details>
<summary>Original English</summary>

**Speaker 9**: it has actually the history of asked prieces and past items. so we came up with agent archies that that agents with trenn that experience. it's a rentern yare that that much agent improve from experices without free training, fine tuning or manual prom training.

</details>

**Speaker 9**: 这与在提示词中塞入所有教训的做法有些不同，因为在这里，智能体实际上是在执行过程中改进。所以我们引入了效用分数。你不会仅仅检索语义相似的内容，而是检索那些根据历史记录是否对执行结果有帮助来加权的记忆。

<details>
<summary>Original English</summary>

**Speaker 9**: how it's a little different from compilying like the s pie because you big in all the lessons in the prompt here is actually improving because it's it is executed because so but again, introduce uh utility score. so you do not retrieve why he would retrieve resimantic and laded to the cutting dusk waited by whether those memories have historically helped or heg.

</details>

**Speaker 9**: 执行结果成为检索和重排序中的首要信号，而不仅仅是余弦相似度。其中一个关键点是，它将记忆视为推理，而非事实——不是没有上下文和历史的静态事实，而是像这样的推理：如果客户支持人员正在处理退款，它不会只说“用户偏好被称呼为短名”，而是会推理出类似“如果有人要求退款，你应该先检查结算状态再退款，这样客户就不会被重复退款”这样的逻辑。

<details>
<summary>Original English</summary>

**Speaker 9**: the evi outcome becomes a first class signal in the dustory will reranking and not just sport cainful. one of the heat things is it. she ate memory as reason, not as facts, static fact with no conteicts and no history, but reasoning like suppose. uh if uh if theif, if is uh customer er support ers, uh looking for refriend, it will not only say y user er fers ers h uact user prefers uh it to be called by a short name. it's actually a reason about quite like like if somesomeone ask for refund, you should check the settlement before refunding it, so that the the the customer doesn't get be refund twice.

</details>

**Speaker 9**: 所以检索基于有用性，数量根据任务动态升级。这是一件非常重要的事情，因为大多数智能体都依赖于上下文填充，而我们的系统能够从历史中学习并进行推理。这在基准测试中得到了验证。

<details>
<summary>Original English</summary>

**Speaker 9**: so read based on usefulness, ness quantts is upgraded based on dusk. so this is a very big thing um because most of the agents here with context stuffing, and this has been rourought up in the ast ast, learn from history and reason ing. and this has from benchmarks.

</details>

**Speaker 9**: 我们在 ToolBench 上对我们的记忆系统 Reflect 进行了基准测试，这个测试实际上衡量了智能体是否遵循了策略。我们看到性能从 66% 提升到了 76%，无需修改技能。一旦积累了大约十条记忆，Reflect 的性能达到了 88%。

<details>
<summary>Original English</summary>

**Speaker 9**: so uh, we have benchmark the our memory system reflect with on tol bench, which as actually measure if agents have followed a policy ban are com't. so we have seuuh uh uh, the performance improve from sixty six to seventy six percent without making in skills and wet skills. refleperforms ces eigheighty. uh, once it are uh enough memory like ten uh memories.

</details>

**Speaker 9**: 我们做的是将推理和理解烘焙成技能，这样你的智能体就能始终保持更新。大多数情况下会发生什么？假设你有一个产品搜索智能体。系统中有一个列系统提示词，即使这个列不再有用，它仍然保留在系统提示词中。目前没有任何系统能够更新它，说“嘿，现在没有这个列了，所以你以后可能不应该再提到它”。而我们的技能系统可以实现这一点，因为智能体总是使用最新的技能，并且类似的行为在 MisMisy 和 Jupty 中也得到了验证。

<details>
<summary>Original English</summary>

**Speaker 9**: uh we do is be beacon, the uh reasoning and the understanding into skills so that your agent always remains updated. what happens most of the time? yeah, seen suppose you have a product s cul agent. so there's a system. there's a column system proong even though that column is no useful anymore. it remains of the system problem. so there's no system right now that can update that. hey, there's no column uh right now call this. so really probably you shouldn't entertained it in the future. and this is possibly with skills that because ages always uuses calls that skill, updated skills all the time, and the similar behavior has mismissey and jupty.

</details>

**Speaker 9**: 我们还在 Agent Dictators 上进行了基准测试，这个测试本质上测试了模型推理、规划和工具使用的能力。这些测试也扩展到了多步骤任务流程，而不仅仅是静态的问答。所以你可以看到，在 HumanLastExam 上，没有记忆系统时得分是某个值，而有了 Reflect 记忆系统后，得分提升到了 61.53%。这种趋势在其他智能体基准测试中也有体现，比如 BigCodeBench 和 LongTVCrow。

<details>
<summary>Original English</summary>

**Speaker 9**: five five point for we have also benchmark it on agent dictators with essentially test a modest ability to reason plan unuse. those also extended multistep twks flows rather than measing ing stastatic QNA. so you can see here uh with the suppose the human last exam, uh with right, you get for desame point uh, the suarpoint uh with mememory stestem because h, with refilmememorsystem uh, this to sixty one, five, three, three perent. so this this kind kind of rend d shoore in another uh aggentic bbench marks um as well, like uh big cold bench, like long TV eccrow.

</details>

### 从 AI 赋能到 AI 贫困：可持续构建 AI 原生产品

**Speaker 8**: 好的，大家好。在我开始之前，这个房间真的很大。大家能靠近一点吗？因为我感觉自己在对着空荡荡的房间说话，而且你们还分散坐着。帮我个忙，我给你们 30 秒时间。所有我们的秘书……我还能看到你们在后面。谢谢，谢谢，谢谢。我们只是聊聊天。这是个巨大的房间，我们这里有 500 人，这个环节本来应该比这多得多。谢谢。老实说，我就知道你们能做到。这其实没那么难。谢谢。我自己也坐在后面，我自己在演讲时也会工作。我完全理解。我整天都在工作，但不是在听我演讲的时候。好了，我要开始了，但我还是会指着你们，如果你们还在后面的话。

<details>
<summary>Original English</summary>

**Speaker 8**: so okay, hello, okay, before i get started, you guys, this is a huge key net room. can everyone like comford because i'm talking to like eempty roand disperse y, we'll do me a favor. i'm setting thirty minutes on you. all of our secrats. i can see you still. thank you. thank thank thank you. thank thank we're 're, just na chat. it's a giant room, and there's five hundred of us this term was way larger than that. thank you. honestly, i knew guys had it in you. it's really not so hard. thank you. i also sit the back. i also worked during talks. i get it. it's totally get it. i did all day, but not for me. okay, i'm going to start, but i'm going to still point at you if you're in the back like you. okay, i'm sarah. i lead our engineering teams for AI at notion.

</details>

**Speaker 8**: 我的演讲是关于“Token Town”的。如何从“AI 赋能”走向“AI 贫困”？我知道今天大家都在谈论软件工厂，我们会讨论这个话题，但我们要讨论的是如何可持续地做到这一点。这是我，这是我加入 Notion 的第一天，在汗流浃背的地铁上。就像我说的，我领导 Notion 的 AI 团队，我的团队开玩笑说我靠谈判 AI 合同为生。所以这是一张我和 AI 以及 Anna Wintour 的合影，因为之前有一篇媒体文章这样称呼我。这大致就是我的想法：如何在不同的供应商之间进行谈判，确保为你的公司保持品味。我不是一个人在做这件事。这是我们最近的一些发布，这只是其中一部分。任何优秀的工程经理都会指出，我们有一整个公司的团队在构建这些，我只是那个有幸来谈论它的人。

<details>
<summary>Original English</summary>

**Speaker 8**: um looking to my talk, it's about token town. how do you go from not go from AI pilled to AI poor? okay, um i know that today's all software factories, we're going to talk about that, but we're going to talk about how to do it sustainable play. 嗯, this is me. this is on my first day and notion in a very sweatdy subway. um like i said, i lead our AI teams that notion um and i negotiate AI contracts for a living my team jokes. i act like ana winter. so this is a nice, a nice image of me with AI and a winter here after a press article referred to me that externally, um and that's kind of ideidea. um um how you think about negotiating bebetwen en different vendors, um making sure that mamaintain taste for your company. i don't do it alone. this is launched it one of our recent launches. this is just a subset. any good engineering manager points out that we have a whole company of people building this, that just the one that gets to come talk to about it.

</details>

**Speaker 8**: 我们一直在构建很多东西。这是我们 2026 年 AI 使用量的一个例子，我们为能够增长这种使用量感到非常自豪。我将和你们谈谈如何构建一个 AI 原生产品和一家 AI 原生公司。但这只是为了给我的演讲增加一些可信度，证明我们做得还不错。对于那些不了解 Notion 的人来说，它一直是那个持久的记录系统。它一直是你可以与同事协作的地方。但今天，这个协作点有点不同了。不仅仅是人类。Notion 一直是协作的地方。而今天，这种协作发生在人类与智能体、人类与人类、智能体与智能体之间。

<details>
<summary>Original English</summary>

**Speaker 8**: so we've been building a lot. um this is an example of our ai usage just just twenty twenty twenty six, and we've been really proud of how we've been able to grow that usage. and i'm going to talk to you about how you can build an AI native product and an ai native company. um but this is just to give me some credit that that we're doing, it kind of well 看. so for those of you that don't know, notions always been that durable system of record. it's always been the place where you can collaborate with your peers um. but today, that point of colcollaboration is a little bit different. it's not just humans. notions always been the place collaboration. and today, that collaboration happens between humans and agents, humans and humans, agents and agents.

</details>

**Speaker 8**: 我们喜欢将 AI 转型看作一个旅程。我相信你们中的一些人正在看这张幻灯片，想知道自己处于哪个阶段。AI 作为思考伙伴是我们所有人开始摸索的阶段。三年前、四年前感恩节 ChatGPT 刚出来的时候，我们都开始尝试，我们会说，“我该怎么用这个给我房东写邮件，说我不应该为重新粉刷付钱？”然后我们复制粘贴，把它变成一封完整的邮件。最终，我们开始达到一个可以用 AI 作为助手来执行单个任务的阶段。这就是 Notion AI 最初起步的方式，它能够节省员工的时间。但从功能上讲，它的能力受限于人类要求它做的事情。AI 智能体是我们大约一年前非常兴奋推出的功能，但这在很多产品中都有。我们可以做重复性工作，思考一个流程，然后让 AI 来完成那个流程。我认为真正有趣的是，当 AI 真正成为关键工作流的一部分时，流程之间相互连接，甚至整个系统都在运行。

<details>
<summary>Original English</summary>

**Speaker 8**: and we like to think about ai transformations going through this journey. and i'm sure some of you are looking at the slide in wondering where you are ai is a thought partner is when we all started tinkering. we all started just going to the very first version of chat y ptitin thanksgiving. when it came out three years ago, four years ago, and we started saying, like, how can i send this emails to my landlord to say that i ouldn't pay for repainting, right? then we copy pace, it entered entory email. eventually, we started getting to a place where we could use AI like like an assiant ant II able able mamay be execute individual task. that's how notion AI really took off in the beginning, and it was able to save employee time. but it functionally was limited in its capabilities based what humans acid to do. ai is timates is what we were really excited to launch almost a year ago now, but this is two in many products. we can do repetitive work and think about a process and have ai dudo that process. what i think is really interesting is when ai actually becomes that critical workflow, where processes are interfacing with each other in new of entire systems running.

</details>

**Speaker 8**: 你们中有多少人感觉自己的 AI 系统已经崩溃了？或者说“AI 是系统”这个概念现在才开始出现？很好。你们中没有人完全做到。我们发现没有人真正搞清楚了如何做好这件事。88% 的人甚至无法让 AI 成为一个系统。为什么会这样？在 Notion，我们认为这是因为数据过于孤立，没有一个持久的记录系统作为协作点。我们相信，为了让你的软件工厂运转、让你的公司运转、让你的系统运转，你需要那个持久的记录系统。这就是 Notion 的使命。

<details>
<summary>Original English</summary>

**Speaker 8**: how many you guys feel like you have? ai is system down? are she said you came up now coming? great. none of you exactly. we have found that no one has figgered out how to do this. well, eighty eight percent of people can't even get past ais in a system. and why is that we've at these? is that notion, it's because there's too much cylude data and not a sturable system of record for that point of collaboration. and we believe that for your software factory to work for your company to work and for your systems to work, you need that durble system of record. and that is nocean's mission.

</details>

**Speaker 8**: 做到这一点成本很高。你会看到很多公司试图致力于这个愿景，而这些只是一周内出现的关于成本高昂的头条新闻。所以你可以把所有的钱都投入到一个流程中，试图构建一个系统，最后却感觉像这样，对吧？你最终会用喷灯去点燃一根实际上很大的雪茄。但你应该明白这个意思。成本是一个结构性的进入壁垒。它让你很难为用户提供产品。

<details>
<summary>Original English</summary>

**Speaker 8**: so doing that is expensive. you see a lot of companies that try and commit themselves to this vision. and these are just a serious heheadinines with within a week of how that's painful. so you can put all of your money into a process to try and make a system. and you end it feeling like this, right? you end up using a blow torch to light what is actually at large cigar. but you kind of get the idea. cost is a structural barrier to entry. it makes it hard for you to serve products.

</details>

<!-- chunk 38/54 -->

### 供应商就是你的竞争对手

**Speaker 8**: 这让你很难建工厂。

<details>
<summary>Original English</summary>

**Speaker 8**: it makes it hard for you to build factories.

</details>

**Speaker 8**: 而且我认为，这最终是事情无法大规模成功的主要原因之一。

<details>
<summary>Original English</summary>

**Speaker 8**: and it is ultimately, i would posit one of the largest reasons why things do not happen at scales successfully day.

</details>

**Speaker 8**: 我主张，对于任何在应用层AI公司工作的人来说，这是他们需要非常熟悉的事情，以理解他们在为客户构建耐用、令人兴奋且有启发性的产品时所做出的权衡。

<details>
<summary>Original English</summary>

**Speaker 8**: and i would argue for anyone working in an applied AI company at something for them to be really familiar with to understand the trade offs that they are making to build durable and exciting and enlightening products for their customers.

</details>

**Speaker 8**: 但这就是当今市场的现状，对吧？

<details>
<summary>Original English</summary>

**Speaker 8**: but that's that really how the market is today, right?

</details>

**Speaker 8**: 我不会点名，但你们都有搜索引擎。

<details>
<summary>Original English</summary>

**Speaker 8**: i'm not going to name names, but you guys have search engines.

</details>

**Speaker 8**: 你可以想出一个推理模型，它升级了。太棒了，但那个可怜的token定价还是一样的。这有什么不喜欢的呢？你试试看，它用了三倍的Alpaca token。场景B：一个模型升级了，但它有一个全新的数字，对吧？无论那个模型系列喜欢什么营销体系，它都是全新的，比它的前身贵了40%，而前身将在未来四个月内被弃用。

<details>
<summary>Original English</summary>

**Speaker 8**: she can figured out exhibit a reasoning model, gets upgraded. amazing that poor token pricing is the same. what's not to love you. try it out, uses three times as many Alpaca tokens right exhibit be a model. it's upgraded, but it has an entire new digit, right? whatever marketing system that model family likes its brand new it's forty percent more than its predecessor, which is being deprecated in the next four months.

</details>

**Speaker 8**: 这些都是我们面临的真实场景。你们都在点头，因为这些情况现在几乎每个月都很常见。但问题来了：你在那段时间里增长了40%吗？你的收入增加了33%吗？没有。那么，如果你只是升级你正在做的所有事情的模型，你该如何驾驭这个系统？你最终会做成一笔糟糕的交易，要么对你的客户，要么对你的投资者，取决于你如何收费以及你的资金从哪里来。

<details>
<summary>Original English</summary>

**Speaker 8**: these are real scenarios that we face. all of you are nodding because these are common pretty much monthly now, but here's the problem. are you growing forty percent in that time period? are you making thirty three percent more revenue? no. so how do you navigate this system if you just ought to upgrade your model in everything that you're doing? you're giving one bad deal, either your customers or your investors, depending on how you charge and where you get your money.

</details>

**Speaker 1**: 两者都不是好兆头。

<details>
<summary>Original English</summary>

**Speaker 1**: neither or good fortune.

</details>

**Speaker 8**: 五百万家公司有能力驾驭这一点。他们可以雇佣大型咨询团队，拥有自己的内部团队，建立专业知识，并驾驭这些权衡。大多数人做不到。其他所有人没有能力进行有杠杆的谈判，他们被困在这些场景中，对吧？我作为Anthropic员工的部分工作就是思考如何为“五百万家”公司发声，那些没有足够规模来拥有杠杆和谈判能力的非“五百强”公司，但它们需要考虑如何……我将分享一些我在拥有大量流量时学到的经验，我认为这些经验可以扩展到那些没有流量的公司。

<details>
<summary>Original English</summary>

**Speaker 8**: five million companies have the capability to navigate this. they can hire large consulting teams have durable teams on their own and build expertise and handle navigate these tradeoffs. most people don't everyone else has no ability to negotiate with leverage, and they're stuck in these scenarios right? part of my job as that an Anthropic joke is to think about advocating for the fortune five million, the non fortune five hundred companies that don't have the mass to have leverage and negotiate, but need to think about how, and i'm going to share some the lessons that i've learned when i have kind of large amounts of traffic behind me that i think scale to those who don't.

</details>

**Speaker 8**: 这现在可能不像我四个月前开始做这类演讲时那么秘密了。你的供应商就是你的竞争对手。我知道很少有人能说服我这不对。你总是会得到一笔糟糕的交易，尤其是与那些原生构建模型的人交易，对吧？有时商品成本差异极大。基本上，他们提供的是首方产品，然后你以巨大的加价购买那些token，然后再以另一个巨大的加价卖出去。这根本不是真正的价值。你可以肯定你得到了一笔非常糟糕的交易。如果你把自己绑定到一个供应商，你就没有出路。如果你用这种结构销售一个AI产品，你就是在祈祷自己是一个可行的企业，我不鼓励这样做。

<details>
<summary>Original English</summary>

**Speaker 8**: this is probably less of a secret. now, then it was when i started giving talks like this, maybe four months ago. your supplier is your competitor. i know very few people who have convinced me that that's not true. you always be getting a bad deal, especially with someone who builds them natively, right? sometimes the cost of good service is extremely different. you're basically they're serving a first party product and then you're buying those tokens at a huge surcharge, and then then selling them again another another surcharge. that's not really value. you can defend you're getting a really bad deal. and if you tie yourself to one provider, you have no exit. if you build an AI product that you're selling with this structure, you are crossing your fingers and hoping that you are a viable business and do not encourage that.

</details>

**Speaker 8**: 这真的很有趣，Dylan发布了一些分析。我想大概是八小时前，但在这个演示中可能是一个月前。他们购买了订阅计划，他们只是强调了前沿实验室对首方产品的收费与它们出售给第三方的价格有多么不同。这是一笔糟糕的交易。不要玩这个游戏，或者试着让我知道你怎么赢。我不推荐。想想其他所有人，想想这种结构意味着什么，以及你的专长在哪里。我不认为那是靠token经济学取胜。我认为关键在于产品。关键在于构建数据飞轮，比任何人都更了解你的客户，了解你何时需要能力，何时需要低价，何时需要延迟改进。我向你保证，你并不总是需要最便宜但最强大的模型，然后构建引人注目的用户界面和编排，并用一些例子来证明你在那笔糟糕交易中出售的token的成本是合理的。你的工作不是训练模型。我的意思是，你们中有些人可能正在训练最好的模型，我很乐意为其提供服务，之后可以来找我谈，但你们大多数人不是。停止试图赢得那场游戏，思考如何构建使用多种模型的最佳产品，帮助你的客户，帮助你的团队押注于前沿技术，而不是押注于实验室，我们将讨论如何做到这一点。

<details>
<summary>Original English</summary>

**Speaker 8**: this is really interesting Dylan and some analysis posted this. i think it's says eight hours ago, it wasn't at this slide probably a month ago, they purchased this subscription plan, and they just highlighted right how different what frontier labs charge customers for first party products are versus what they sell. it's a bad deal. don't play this game or try and let me know how you win. i don't recommend think about everyone else think about what that structure means and where you have expertise. i don't think that that's winning on the token economics. i think it's about product. it's about building data fly wheels and understanding your customers better than anyone else understanding when you need capability when you need low price when you need latency improvements, i promise you you don't always need. it's usually the lowest, but the most capable model out there and then build compelling, UI and orchestration, and also use some examples of that to justify the cost on the bad deal. tokens that you do resell the job is not to train. i mean, some of you might be training the best model, and i'd love to serve it and come talk to me afterwards that most of you are not doing that. stop trying to win that game and think about the best product that uses many models, help your customers help your team bet on the frontier, not on the lab, and we'll talk about what it looks like to do that.

</details>

**Speaker 8**: 这种成本与能力的权衡实际上非常激烈。我引用一下。LLM不久前发布了一份备忘录，大概两周前，我很喜欢。其观点是，对于整体经济而言，更简单的模型可能是最具成本效益的生产力提升途径。他们谈到了前沿模型与日常使用模型之间的这种分化。我深信这一点。对于每个产品，前沿与日常的定义，饱和能力或模型能力的定义，取决于你的产品和你的专业知识。没有人可以取代这一点，并非所有流量都是平等的。将所有流量都发送到最新的OpenAI模型是一个巨大的错误。其中一些绝对是大型技能数据分析，当你在Notion上做这件事时，我们会推荐OpenAI，但当你处理电子邮件收件箱时则不会。如果我们向你收费让你在OpenAI上做这件事，我们就是在欺骗你和我们自己。想想你的流量模式在哪里。然后想想前沿实验室模型提供商如今的结构。我的意思是，它实际上是一个寡头垄断，对吧？这没问题，因为他们正在竞相冲向顶峰。我认为顶峰非常艰难且非常重要。这并不是说产品没有前沿困难任务的用武之地。我希望每个人都能理解。这不是这次演讲的内容。要理解你何时需要这些任务，而且并非所有任务都需要。这些任务的问题在于要记住定价是如何被激励的。你也能弄清楚这些参与者是谁。你是最好的模型，AI今天能做的所有事情之上就是你的市场。你基本上可以随心所欲地定价。如果你稍微落后于那个最好的模型，你只需要每百万token便宜一美元，你就拥有了剩下的市场。你知道关于加油站的经济学理论吗？最好的加油站是那些紧挨着的加油站，因为它们覆盖了东西两个方向。是的，模型定价也是如此。这意味着价格与能力增长并不相关。所以对于这些复杂任务，要理解你需要什么能力，但要成为复杂性的专家，并记住处理复杂性的角色是会变化的。

<details>
<summary>Original English</summary>

**Speaker 8**: this cost for capability bridge second tradeoff is actually really intense. cited it. LLM came out with this memo a while ago, maybe two weeks ago, i loved it. the idea that for the economy at large, simpler models might be the most cost effective productivity augmenting pathway. they talk about this bifurcation on frontier versus every day usage. i really believe that. and for every product, the definition of frontier versus every day, the definition, saturated capabilities or model capability, overhangs depends on your expertise on your product. no one can replace that in not all traffic is equal. it is a huge miss to send all of these to the latest OpenAI model. some of these absolutely large skilled data analysis when you do it on Notion, we'll recommend OpenAI right when you treat an email in box. if we're charging you to do that on OpenAI, we're ripping you off in ourselves, think about where your traffic patterns are. and then think about how frontier lab model providers are structured today. i mean, it's functionally an oligopoly, right? and that's fine because they're racing to the top. and i think the top is really hard and really important. this is not to say that products don't have a place for frontier difficult task. i want everyone to not misunderstand. that's not what this talk is about understand when you need those task, and it's not everything. the problem with those task are is keep in mind how pricing is incentivized. you can figure out who these players are either. you are the best model, everything above what AI can do today is your market. you can basically price it as high as you kind of want. if you're slightly behind that best model, all you need to be is like a dollar per million tokens cheaper. and you have the rest of the market. you know that economic theory about gas stations were the best gas stations are the ones that are right next to other because they cover east and west. the most yeah, it's the same with model pricing, which means that price does not correlate with capability growth. so for this complex task, understand what capabilities you need, but be the expert in what complexity is and keep in mind that who handles complexity changes.

</details>

**Speaker 8**: 很多时候，你会看到应用层AI公司在营销上非常公开地支持某个特定的实验室。对我来说，当他们不是模型无关的时候，这总是一个危险信号。因为如果你看图表，它基本上显示他们每个月都落后，对吧。最好的前沿能力的新模型和新模型提供商一直在变化。如果你为了获得推荐和更大的折扣而将自己的命运与某个特定提供商捆绑在一起，你这样做是为了服务你的客户，但只有一半的时间是有效的。

<details>
<summary>Original English</summary>

**Speaker 8**: often times you'll see applied AI companies really be outspoken on marketing with a specific lab. that's always kind of a red flag for me when they're not model agnostic. because if you look at the graph, it basically shows that they're behind every month, right. the new model in the new model provider of the best frontier capabilities changed. and if you hit your ride with one particular provider in exchange for reference, a larger discount, i'm you're doing it to service your customers like half of the time.

</details>

**Speaker 0**: 对。所以真的要想想那个折扣是否值得没有一个前沿产品。记住，可替代性就是你的杠杆。如果你在任何时候都没有离开的能力，你就被困住了。再说一次，我认为这可能是你最昂贵的决定，无论你得到什么折扣，或者为了实现模型互操作性而付出的工程工作。应对这种情况的一个选择是保持模型无关，在你的系统中拥有不同的模型和能力。这样在任何时候，如果定价看起来不公平或不可持续，你都不会破产。Notion的自动模型就做得很好。我们总是提供固定的模型，但我们也有一个顶层的自动模型，它处理了大约75%的流量，对吧？我们有能力在我们的产品中切换模型，我们也向我们的客户提供这种能力，让他们可以访问这些模型而不会被供应商锁定。这是我们AI瑞士方法的一部分。你们在拍幻灯片。就是这张幻灯片。好的。模型物流手册，这就是你如何构建多模型的方法。很难消除哪些模型可能转录的猜测。我理解我们投资于这项技术。它甚至不必是每个线程的。只要考虑你的模型的互操作性。考虑每秒钟每能力成本，而不仅仅是token。这里有一个很好的例子。我们在宣布与Parallel合作作为我们的网络搜索提供商时发布了这篇评论。如果你只看单次调用的长度或成本，Parallel可能不是最便宜的。但是如果你拥有整个网络搜索轨迹的专业知识，你会看到这个粒度的不同之处在于它让我们能够为我们的客户做出最好的决策，因为我们理解整个轨迹上的所有权衡，而不仅仅是单次调用。快速切换。而且，我认为我们谈论这个并给他们一些回报。这种关于用例的专业知识对前沿实验室也非常有价值。

<details>
<summary>Original English</summary>

**Speaker 0**: right. so really think about if that discount is worth not actually having a frontier product. and remember that, that optionality is your leverage, if you don't have the capability to walk at any point, you are stuck. and again, i think that's probably the most expensive decision. you'll make regardless of what discount you get or the engineering work to have model interoperability one option to navigate this, a state model agnostic have different models and capabilities in your system. so that at any point, if pricing seems unfair or untenable, you're not out of business notion's auto model. does this really well? we have stated the our models available always, but we also have an auto model there at the top that handles about seventy five percent of her traffic, right? we have the ability to switch between models in our product, and we also offer it to our customers that they have access to these models without vendor locking. that's part of our AI Switzerland approach. you guys left taking photos of slides. this is the slide. okay. model logistics playbook, this is how you do it build from multi model. it is hard to kill the guesswork, which models may transcribe. i understand that we invest in that technology. it doesn't even have to be per thread. just think about your harness's model interoperability. think about the cost per capability per second, not just the tokens, here's a great example. we posted this review when we announced our partnership with parallel as our web search provider. if you were to look at just length of single call, all or just cost parallel might not be the cheapest. but if you have expertise in entire web search trajectories, you'll see how it differs the granularity of this level is what lets us make the best decisions for our customers because we understand all of the tradeoffs on entire trajectories, not just single call. switch fast. and often, i think we talks about that and give them something back. that expertise on use cases is also very valuable to frontier labs.

</details>

<!-- chunk 39/54 -->

### 开源权重模型的价值与AI安全治理

**Speaker 0**: 我们发现，在早期访问计划合作中，我们的评估实际上对前沿实验室帮助很大，这也是我们可以用来交换的东西，而不需要支付异常高昂的费用。

<details>
<summary>Original English</summary>

**Speaker 0**: we find that our evals in our early access program partnerships actually help us a lot with frontier labs and is something that we can exchange instead of extraordinary large comments.

</details>

**Speaker 0**: 而且我不认为折扣值得失去可选择性。

<details>
<summary>Original English</summary>

**Speaker 0**: and i don't think the discount is ever worth the lost and opctionality.

</details>

**Speaker 0**: 这是一种视角。

<details>
<summary>Original English</summary>

**Speaker 0**: that's a perspective.

</details>

**Speaker 0**: 你可以选择保留它。

<details>
<summary>Original English</summary>

**Speaker 0**: you can choose to keep her,

</details>

**Speaker 0**: 第二个选项是中等。

<details>
<summary>Original English</summary>

**Speaker 0**: not the second option is moderate.

</details>

**Speaker 0**: 任务。

<details>
<summary>Original English</summary>

**Speaker 0**: task,

</details>

**Speaker 0**: 理解开源权重模型的位置。

<details>
<summary>Original English</summary>

**Speaker 0**: understanding open weights place there.

</details>

**Speaker 0**: 开源权重模型已经足够强大，能够处理这些任务，并且在其之上进行定制的可能性也扩展了它们所能覆盖的高端市场增长。

<details>
<summary>Original English</summary>

**Speaker 0**: open weight models are really strong enough to handle these tasks in the possibility to oral on on top of them has also kind of expanded the upmarket growth that they can cover.

</details>

**Speaker 0**: 我认为开源权重模型基本上是在降低客户的使用成本门槛。

<details>
<summary>Original English</summary>

**Speaker 0**: i view open weight models is basically lowering the barrier to entry on cost for our customers.

</details>

**Speaker 0**: 而且它们也给了你谈判的筹码。

<details>
<summary>Original English</summary>

**Speaker 0**: and they also give you negotiation leverage.

</details>

**Speaker 0**: 所以这是一种可信的替代方案，对定价施加了下行压力。如果目前排名前三的供应商出现寡头垄断，这种压力就会显现出来。

<details>
<summary>Original English</summary>

**Speaker 0**: so it's kind of a credible alternative that's putting that downward pressure on pricing that if there's an allogopy of tour three providers at the top is unavailable right now.

</details>

**Speaker 0**: 否则，我认为Claude 2.6可能是我们第一次真正看到一个模型性能达到GPT-5、5、2、LM和5.2的水平，而5.2又是一个重磅炸弹。

<details>
<summary>Original English</summary>

**Speaker 0**: otherwise, i think came me two six was probably the first time that we really saw a model that i performed five, two GPT, five, two, two LM, and five two now was another five, two bomb shell in the villa.

</details>

**Speaker 0**: 那可能也只是暂时的领先，但现在已经不再是开源权重模型只适合在小型任务上进行微调的情况了。真正要考虑的是，如果它们足够胜任你的需求，就不要依赖我们的RL。

<details>
<summary>Original English</summary>

**Speaker 0**: that also probably just best here, but it's no longer the case where open way models are good for just sf t on small tx really think about without our rel if they're capable enough for what you need.

</details>

**Speaker 0**: 再次强调，不要只考虑外部基准测试，要能够对你的系统有深入的了解。

<details>
<summary>Original English</summary>

**Speaker 0**: and again, don't just think about externnal benchmarks be able to have expertise on your system.

</details>

**Speaker 0**: 你的工具错误率是多少？你实际需要的延迟是多少？

<details>
<summary>Original English</summary>

**Speaker 0**: what are your tool errors, what the actual latency that you need?

</details>

**Speaker 0**: 这里有一个我们故意稍微调整过的基准测试例子。

<details>
<summary>Original English</summary>

**Speaker 0**: right? here's an example of a benchmark that we pushted a little bit steill on purpose, right?

</details>

**Speaker 0**: 但你明白我的意思。Fill if a based tenfof 曾经展示过这张幻灯片，从那以后我就一直借用它。

<details>
<summary>Original English</summary>

**Speaker 0**: but you get the idea fill if a based tenfof this showed this slide once, and i've stolen it ever since.

</details>

**Speaker 0**: 谢谢。

<details>
<summary>Original English</summary>

**Speaker 0**: thank you.

</details>

**Speaker 0**: 你在吗？伙计？

<details>
<summary>Original English</summary>

**Speaker 0**: are you here? buddy?

</details>

**Speaker 0**: 好吧。

<details>
<summary>Original English</summary>

**Speaker 0**: okay,

</details>

**Speaker 0**: 哦，聊天。

<details>
<summary>Original English</summary>

**Speaker 0**: oh, chat.

</details>

**Speaker 0**: 嗨。

<details>
<summary>Original English</summary>

**Speaker 0**: hi,

</details>

**Speaker 0**: 嘿。

<details>
<summary>Original English</summary>

**Speaker 0**: hey.

</details>

**Speaker 0**: 好吧，他可以上来讲得更好，但核心思想是，你不必非得是顶尖的。

<details>
<summary>Original English</summary>

**Speaker 0**: well, he could come up and say it better, but the idea is that you don't have to be at the top, right?

</details>

**Speaker 0**: 我并不是在论证开源权重模型就是最好的模型。

<details>
<summary>Original English</summary>

**Speaker 0**: i'm not trying to make a case that open way it is the best model out there.

</details>

**Speaker 0**: 然而，我要论证的是，差距最终会被弥合。

<details>
<summary>Original English</summary>

**Speaker 0**: the case being made, however, is that the gap gets covered eventually.

</details>

**Speaker 0**: 所以，如果你今天的任务已经足够好，那么六个月后，它们很可能就会被开源权重模型覆盖。

<details>
<summary>Original English</summary>

**Speaker 0**: so if the task that you're having today are good enough than in six months, they're probably covered by open way.

</details>

**Speaker 0**: 所以现在就要做好准备。

<details>
<summary>Original English</summary>

**Speaker 0**: so be prepared now.

</details>

**Speaker 0**: 最后一点，作为我们CPO和GP，我们最近在Notion推出了一个叫做Workers的功能。

<details>
<summary>Original English</summary>

**Speaker 0**: and the last thing as cps of our gps, we've ve recenlalaunched something at notion called workers.

</details>

**Speaker 0**: 我不认为大语言模型对每项工作都是必要的。我们很多工作实际上是在处理离散的代码片段。你不需要一个大语言模型来把CSV转成PDF。

<details>
<summary>Original English</summary>

**Speaker 0**: i don't think that the gp was necessary for every job, a lot of the jobs that we have are actually serving um discrete pieces of code like you don't need an alymp to turn a csv into a pd f.

</details>

**Speaker 0**: 你不需要一个大语言模型来把Notion连接到Calls。

<details>
<summary>Original English</summary>

**Speaker 0**: you don't need an alymn to talch a notion to a calls.

</details>

**Speaker 0**: 如果我们有CLI，你绝对不需要大语言模型来确定静态SQL查询。

<details>
<summary>Original English</summary>

**Speaker 0**: if we have ACLI, you definitely don't need alalympt to determine stic eal queries.

</details>

**Speaker 0**: 这就是人们很快变成Token贫民的地方。

<details>
<summary>Original English</summary>

**Speaker 0**: this is where people become token poor, very quick.

</details>

**Speaker 1**: 没没有没有。

<details>
<summary>Original English</summary>

**Speaker 1**: 没没有没有。

</details>

**Speaker 0**: 我认为除了开源权重、成本和可选择性之外，最后一个选项实际上是治理。

<details>
<summary>Original English</summary>

**Speaker 0**: and i think the last option here besides open weight c in and opoptionality is actually governance.

</details>

**Speaker 0**: 有很多治理方面的问题。一个是可见性和理解，了解谁在使用数据，理解可维护性和控制。

<details>
<summary>Original English</summary>

**Speaker 0**: there's a lot of egi governance. um one is visibility underststanding, who using the the atata underananding maintainability and control.

</details>

**Speaker 0**: 当你拥有模型可选择性时，你可以为客户提供更多价值。

<details>
<summary>Original English</summary>

**Speaker 0**: when you have model optionality, you can offer a lot more to your customers.

</details>

**Speaker 0**: 我用一个Notion的例子来说明治理是如何运作的。

<details>
<summary>Original English</summary>

**Speaker 0**: i'm uan example of how that governance works a notion.

</details>

**Speaker 0**: 所以，最后的建议是，再次强调，思考架构，思考开源权重，并构建超越Token的价值。

<details>
<summary>Original English</summary>

**Speaker 0**: so final tips, again, think about architecture, think about open weight and build value that transtends tokens.

</details>

**Speaker 0**: 所以我们要离开Token镇了。我知道我之前说过欢迎来到Token镇，但现在我们要花接下来的时间真正思考下一步该做什么。

<details>
<summary>Original English</summary>

**Speaker 0**: so we're going to depart token town. i know i said of welcome to token town. and when going spspend next next minutes, really thinking about what to do next.

</details>

**Speaker 0**: 所以我认为未来六个月的挑战不在于能力。

<details>
<summary>Original English</summary>

**Speaker 0**: so i think the challenge of the next six months doesn't have to do with capabilities.

</details>

**Speaker 0**: 我认为这与安全有关。

<details>
<summary>Original English</summary>

**Speaker 0**: i think it has to do a security.

</details>

**Speaker 0**: 让我们从这里开始。

<details>
<summary>Original English</summary>

**Speaker 0**: let's start there.

</details>

**Speaker 0**: 有一个概念叫做“致命三角”，我认为是Simon Wilson创造的。

<details>
<summary>Original English</summary>

**Speaker 0**: there's this concept called the lethal trifacta simon wilson son. i think, crafted this,

</details>

**Speaker 0**: 如果你能访问私有数据，接触到感兴趣的内容，无论是通过数据摄取、MCP、电子邮件，还是能够与外部通信，这可能包括网络搜索中的载荷。

<details>
<summary>Original English</summary>

**Speaker 0**: if you have access to private data exposure to interested content, whether it be through ingjestion mcp, email and the ability to x to communicate externally, and that can include like payloads in a web search.

</details>

**Speaker 0**: 一旦你的系统具备了这些，就存在风险。

<details>
<summary>Original English</summary>

**Speaker 0**: the second you have that system yyorks wissing risk.

</details>

**Speaker 0**: 事实上，系统越自主，这种风险就越不受监督。

<details>
<summary>Original English</summary>

**Speaker 0**: and in fact, the more autonomious system is the more unsupervised this risk is,

</details>

**Speaker 0**: 我认为这才是构建有价值产品的关键，而不仅仅是能力。

<details>
<summary>Original English</summary>

**Speaker 0**: i think that this is what builds valuable product, not just capability,

</details>

**Speaker 0**: 沙盒和计算机也是如此。

<details>
<summary>Original English</summary>

**Speaker 0**: same with sandboxes and computers.

</details>

**Speaker 0**: 我们讨论过这个，但它确实能在你的产品中构建更好的确定性，并且在多智能体编排中为你的客户带来更好的Token经济性，理解哪些智能体做什么以及什么需要持久化。

<details>
<summary>Original English</summary>

**Speaker 0**: we talks about this, but it really is something that builds better determinism in your product and also better token economics for your customers in multi agent, orchestration understanding what agency do and what persists.

</details>

**Speaker 0**: 我认为企业知识的持久化是一个实际上没有被充分讨论的话题，最近一些产品的发布才开始涉及。

<details>
<summary>Original English</summary>

**Speaker 0**: i think perperstence of enterprise knowledge is something that's actually really not discussed enough starting to be with some recent launches.

</details>

**Speaker 0**: 你知道，这里有音频，所以不要让你的工作流程看起来像这样。

<details>
<summary>Original English</summary>

**Speaker 0**: you know, there is audio, so don't have your workclothes look like this.

</details>

**Speaker 0**: 我认为这就是大多数软件工厂目前的状况。

<details>
<summary>Original English</summary>

**Speaker 0**: and i think this is where most suoftware factories are today.

</details>

**Speaker 0**: 对吧？实际上你整个工程团队的时间都花在照看工厂上。

<details>
<summary>Original English</summary>

**Speaker 0**: right? it's like actually your entire engineering time just spend time babysitting the factory, right?

</details>

**Speaker 0**: 我的意思是，我明白，一开始就是这样。智能体编排是让工厂运转起来最困难的任务之一。

<details>
<summary>Original English</summary>

**Speaker 0**: i mean, i get it are started off like this agent orchestration is one of the most difficult tasks of making factories work.

</details>

**Speaker 0**: 好吧，这是我告诉团队要说服人们购买Notion AI。

<details>
<summary>Original English</summary>

**Speaker 0**: so okay, this is me telling tea pain to tell people to buy nation AI.

</details>

**Speaker 0**: 我放这张幻灯片的原因是，我要花一点时间来推销Notion。

<details>
<summary>Original English</summary>

**Speaker 0**: and the reason i included this slide is i am going to sell notion for a second.

</details>

**Speaker 0**: 这是我的工作，永远在成交，永远在销售，永远在招聘，可以来找我。

<details>
<summary>Original English</summary>

**Speaker 0**: it's my job always be closing, always be selling, always be hiring confined me.

</details>

**Speaker 0**: 但我要花一点时间谈谈Notion现在是如何做到这一点的。

<details>
<summary>Original English</summary>

**Speaker 0**: but i'm going to talk for a second about how nation does this today.

</details>

**Speaker 0**: 我们已经具备了检查任务的能力。

<details>
<summary>Original English</summary>

**Speaker 0**: we already have the ability to inspect task.

</details>

**Speaker 0**: 你可以想象，在Notion文档中查看任何任务时，你可以让Claude去评估你需要什么。

<details>
<summary>Original English</summary>

**Speaker 0**: and you can imagine any task that you look at um in a notion document, you can have claud actually go ahead and scope out what you need.

</details>

**Speaker 0**: 我们今天已经推出了这种管理能力。

<details>
<summary>Original English</summary>

**Speaker 0**: we've launched this managaging capability today.

</details>

**Speaker 0**: 所以，如果我到这个任务的顶部，我实际上可以要求Claude Agent去执行这个任务。

<details>
<summary>Original English</summary>

**Speaker 0**: so if i go ahead to the top of this task, i can actually ask claude agent just go about the task, right?

</details>

**Speaker 0**: 理想情况下，它会在你的Settle中工作，实际上填充整个需要完成的工作范围。在这个例子中，它还没准备好。

<details>
<summary>Original English</summary>

**Speaker 0**: ideally. it's working in your seettle actually populate an entire spect of what needs to be done in this example. it's not ready.

</details>

**Speaker 0**: 它会问我一个问题。

<details>
<summary>Original English</summary>

**Speaker 0**: it's going to ask me a question.

</details>

**Speaker 0**: 请记住，这是一个Markdown文件。

<details>
<summary>Original English</summary>

**Speaker 0**: keep in mind, this isan a mark done file.

</details>

**Speaker 0**: 这是一个活跃的文档。

<details>
<summary>Original English</summary>

**Speaker 0**: this is an active document.

</details>

**Speaker 0**: 假设我实际上不知道答案，然后我去问我的团队该怎么做。

<details>
<summary>Original English</summary>

**Speaker 0**: let's say, i don't actually know the question, and i go ahead, and i ask my team um what to do,

</details>

**Speaker 0**: 想象一下，你可以把你的团队成员标记到这些系统中，比如M Jasor PM。

<details>
<summary>Original English</summary>

**Speaker 0**: imagine that you can kind of tag in your team into these systems, m jasor pm.

</details>

**Speaker 0**: 所以在这个例子中，她不知道，通常她是知道的，但多智能体编排很重要。

<details>
<summary>Original English</summary>

**Speaker 0**: so in this example, she doesn't know usually she does, but motly agent organstration is important.

</details>

**Speaker 0**: 也许Claude Code不是我们语音的最佳选择。

<details>
<summary>Original English</summary>

**Speaker 0**: maybe cloud code isn't the best accost for our voice.

</details>

**Speaker 0**: 但Decagon是对的。

<details>
<summary>Original English</summary>

**Speaker 0**: but decaagon is right.

</details>

**Speaker 0**: 你也可以询问Decagon Agent或我们的合作伙伴Agent，来收集你需要的数据。

<details>
<summary>Original English</summary>

**Speaker 0**: you can ask decagon agents or proud partners to them as well, to collect three data that you need.

</details>

**Speaker 0**: 好的。

<details>
<summary>Original English</summary>

**Speaker 0**: okay.

</details>

**Speaker 0**: 在这个例子中，我们认为我们了解得足够多了，我们将继续实际迭代这个流程中的一些步骤。

<details>
<summary>Original English</summary>

**Speaker 0**: in this example, we think we know enough we're going to go ahead and actually iterate through some of this fflow.

</details>

**Speaker 0**: 我跳过了一点。

<details>
<summary>Original English</summary>

**Speaker 0**: and a skip had a little bit.

</details>

**Speaker 0**: 我们问Till我们需要什么。

<details>
<summary>Original English</summary>

**Speaker 0**: we asked her till what we needed.

</details>

**Speaker 0**: 他回复了。

<details>
<summary>Original English</summary>

**Speaker 0**: he replied,

</details>

**Speaker 0**: 再次强调，这是一个协作文件，而不仅仅是Markdown。

<details>
<summary>Original English</summary>

**Speaker 0**: again, it's a collaborate file and not just to mark down,

</details>

**Speaker 0**: 我们可以让Claude去实际审查这个PR。

<details>
<summary>Original English</summary>

**Speaker 0**: and we can have cloud actually go ahead and spent at the pair.

</details>

**Speaker 0**: 希望这看起来有点熟悉。

<details>
<summary>Original English</summary>

**Speaker 0**: hopefully, this is looking a little familiar.

</details>

**Speaker 0**: 现在这就是软件工厂的一种分工。

<details>
<summary>Original English</summary>

**Speaker 0**: now this is kind of division of software factories.

</details>

**Speaker 0**: 这就是我们试图倡导的。

<details>
<summary>Original English</summary>

**Speaker 0**: it's what we're trying to host.

</details>

**Speaker 0**: 好的，Claude提交了一个PR。

<details>
<summary>Original English</summary>

**Speaker 0**: okay, claud put up a pr.

</details>

**Speaker 0**: 也许这还不够。

<details>
<summary>Original English</summary>

**Speaker 0**: maybe that's not enough.

</details>

**Speaker 1**: 也许我想去问问Cortex它觉得怎么样，Great Found也是。

<details>
<summary>Original English</summary>

**Speaker 1**: maybe i want to go ahead and ask cotex what it thinks great found too.

</details>

**Speaker 0**: 问题在于，你可以想象这在真正的工厂中是如何扩展的。

<details>
<summary>Original English</summary>

**Speaker 0**: issuous, you can think about this scaling in an actual factory.

</details>

**Speaker 0**: 所以今天，在Notion中，你实际上能够将这些Agent编排在一起，并且你不是在承诺使用某个实验室的产品。

<details>
<summary>Original English</summary>

**Speaker 0**: so today, in notion, you're actually able to orchestrate these agents together and you're not committing to a lab.

</details>

**Speaker 0**: 你承诺的是AI正在增强和自动化你所做的事情这一理念。

<details>
<summary>Original English</summary>

**Speaker 0**: you're committing to the concept that ai is augmenting and automating what you do.

</details>

**Speaker 0**: 这是真实的。

<details>
<summary>Original English</summary>

**Speaker 0**: this is real.

</details>

**Speaker 0**: 我问过Gief是否可以发布这个，这就是它今天的工作方式。

<details>
<summary>Original English</summary>

**Speaker 0**: i asked gief if i could post this, this is how it works today.

</details>

**Speaker 0**: 在Notion内部，几乎我们所有的Polishing和大型反馈都是通过我们的软件工厂来协调的，无论是写入正确的团队，还是让裁剪Agent迈出第一步。

<details>
<summary>Original English</summary>

**Speaker 0**: internal in ocean, almost all of our polish and large feedback like this is actually coordinum through our software factories, both in terms of writing to the right teams and also having cutting agents take the first step verr cell.

</details>

**Speaker 0**: Vercel也这样做，从Staging到Shipping再到Closing，我们看到客户获得了巨大的投资回报率提升。

<details>
<summary>Original English</summary>

**Speaker 0**: does this as well from staging to shipping to closing, and we see massive araoi gains from our customers.

</details>

**Speaker 0**: 在给定任务上节省了超过三分钟。

<details>
<summary>Original English</summary>

**Speaker 0**: it's over three minutes saves on a given task.

</details>

**Speaker 0**: 想象一下在规模上的效果。

<details>
<summary>Original English</summary>

**Speaker 0**: imagine that at scale.

</details>

**Speaker 0**: 所以我认为我们正在尽最大努力思考工厂层面。

<details>
<summary>Original English</summary>

**Speaker 0**: so i think we're trying our hardest to think about the factory length.

</details>

**Speaker 0**: 没有可选择性，我们无法做到这一点。

<details>
<summary>Original English</summary>

**Speaker 0**: we cannot do this without opportality,

</details>

**Speaker 0**: 没有确信我们理解哪些模型适用于哪些任务的信念，我们也无法做到这一点。

<details>
<summary>Original English</summary>

**Speaker 0**: and we cannot do this without conviction that we understand what models are required for, which tests.

</details>

**Speaker 0**: 外面的世界真的很疯狂。

<details>
<summary>Original English</summary>

**Speaker 0**: it's really wild out there.

</details>

**Speaker 0**: 各位，我明白。

<details>
<summary>Original English</summary>

**Speaker 0**: you guys i get it.

</details>

**Speaker 0**: 市场非常年轻。

<details>
<summary>Original English</summary>

**Speaker 0**: the market is really young.

</details>

**Speaker 0**: 它异常动荡。

<details>
<summary>Original English</summary>

**Speaker 0**: it's exceptionally oppic.

</details>

**Speaker 0**: 它发展迅速。

<details>
<summary>Original English</summary>

**Speaker 0**: it's moving fast.

</details>

**Speaker 0**: 我非常感谢像AI Engineer这样的社区，能把大家聚集在一起，公开谈论这些事情以及我们是如何应对的。

<details>
<summary>Original English</summary>

**Speaker 0**: i'm super grawful for committeties like AI engineerto, bring totogether and talk openly ly about these things and how we navigted.

</details>

**Speaker 0**: 我认为我们有责任为所有客户把事情做好，并成为批判性思考者，在我们共同应对这一切时保持清醒。

<details>
<summary>Original English</summary>

**Speaker 0**: um i think we owe it to all of our customers to get it right and to be critical thinkers, how we naviviate this together.

</details>

**Speaker 0**: 我基本上一直在线。

<details>
<summary>Original English</summary>

**Speaker 0**: i'm chchonicically online.

</details>

**Speaker 0**: 幸运的是，你随时可以在Twitter上给我发私信。

<details>
<summary>Original English</summary>

**Speaker 0**: fortunately, um you can always DM me on twitter.

</details>

**Speaker 0**: 你可以给我发邮件。

<details>
<summary>Original English</summary>

**Speaker 0**: you can email me.

</details>

**Speaker 0**: 你可以在会后找到我。

<details>
<summary>Original English</summary>

**Speaker 0**: you can find me after this.

</details>

**Speaker 0**: 你。

<details>
<summary>Original English</summary>

**Speaker 0**: you,

</details>

**Speaker 3**: 谢谢你和我一起探讨并思考这个问题。这个演示文稿内容非常丰富。

<details>
<summary>Original English</summary>

**Speaker 3**: you thank you for yepping with me and thinking about this problem and have a good deck is for ah just just got so much in there.

</details>

### 从LangGraph迁移到自研Agent循环

**Speaker 4**: 它确实有助于编写更好的代码，更好地组织代码结构，有助于架构设计，加速新服务的搭建。对我们Agent团队来说，它确实有助于设计和构建核心和操作。

<details>
<summary>Original English</summary>

**Speaker 4**: it really helps write better code and structure your code better and helps with architecture spending up new services for and for us on the agents team really helping this design and build the the corage ge and opp.

</details>

**Speaker 4**: 所以你会在这个演示中看到，穿插着，我们团队如何使用Effect获得了回报。

<details>
<summary>Original English</summary>

**Speaker 4**: so you'll see throughout this presentation, sprinkle, then um how afffect on our team uh has paid of individent.

</details>

**Speaker 4**: 所以我们非常喜欢Effect在Open Gov和H上的应用。

<details>
<summary>Original English</summary>

**Speaker 4**: so we really love a effect you at open gove and h.

</details>

**Speaker 4**: 我们鼓励其他人也尝试一下。

<details>
<summary>Original English</summary>

**Speaker 4**: we encouraother other folks to try it out.

</details>

**Speaker 4**: 是的，让我们继续推进Effect原生循环。

<details>
<summary>Original English</summary>

**Speaker 4**: and yeah, let's keep going the effect native loop.

</details>

**Speaker 4**: 最初，我们使用的是LangGraph。

<details>
<summary>Original English</summary>

**Speaker 4**: so originally, we are on langrarah.

</details>

**Speaker 4**: 在团队真正开始扩展之前，这都还好。

<details>
<summary>Original English</summary>

**Speaker 4**: and that was fine until the team really started to scale.

</details>

**Speaker 4**: 我们的用例也开始演变。

<details>
<summary>Original English</summary>

**Speaker 4**: and our use cases started to evolve.

</details>

**Speaker 4**: 所以我们决定迁移到我们自己定制的Effect原生Agent循环，以便对这个Agent循环拥有完全的控制权，这样如果我们有复杂的用例或需要构建的功能，我们就能灵活应对。

<details>
<summary>Original English</summary>

**Speaker 4**: so we decided to move over to our own kind of affecnaated agent loop to have full agency over this agent loop such that if we have complex use cases or features that we need to build,

</details>

<!-- chunk 40/54 -->

### 掌控智能体循环与效果系统

**Speaker 4**: 我们能够……是的，进入其中。我们完全掌控了智能体循环，不仅如此，我们现在完全基于效果系统。所以你得到的所有酷炫功能，效果现在贯穿整个智能体循环，比如追踪结构、货币化、日志记录。一切都更加精细可控。这确实让我们能够充分释放潜力，从头构建我们自己的智能体循环。

<details>
<summary>Original English</summary>

**Speaker 4**: we could kind of get in. we had full control of the agent loop, but not only that, but now we're fully on effects. so all the cool things you get, what effect is now propagated throughout the entire agent loop, like the tracing structure can currency to logging. everything is more fine grain control. and so it really allows us to really unlock the full potential having our own agent loop from the ground.

</details>

**Speaker 4**: 嗯，另一件我想提的是，你们会看到一个代码示例。这基本上就是我们正在使用的效果循环。我们使用一个叫做 effect ai 的包。在那个包里，有一个聊天和一个语言模型。对于聊天，你可以实例化一个聊天，然后使用 stream text 函数来流式传输文本，你可以传入一个提示。很酷的是，在底层，语言模型实际上在做依赖注入。我们可以传入一个不同的语言模型，比如热切换到另一个。所以，真正完全掌控我们自己的智能体循环，给了我们所有的控制杆。这确实释放了模型的全部能力，也让团队对此拥有完全的自主权。

<details>
<summary>Original English</summary>

**Speaker 4**: so another thing i wanted to mention is you'll see a code example. this is really the basics of the effect loop that we're using. we're using this thing called the effect ai package. and in that package, there's this thing called a chat and a language model. so for the chat, you can instantiate a chat for example. and then you could stream text using that stream text function, you could pass in a prompt and what's cool is with a language model under the hood we're kind of doing dependency injection. we could pass in a different language model if we were to hot walk to another one, for example. so really just having full control of our own agent loop, just kind of give us all the levers. and it really just unlocks the full capabilities of the model and for the team as well to have full agency over this loop.

</details>

### 智能体间协议

**Speaker 4**: 不，我想提的另一件事是智能体间协议。在 Agency 这边，我们在这个协议上取得了很大成功。这个协议是谷歌创建的一种开放协议，用于智能体间的通信。但我们发现它对于定义我们的智能体路由非常有用，例如，在后端，我们的模型和模式都遵循这种智能体协议。所以我们建模。例如，有一个叫做智能体卡片的东西，你们在这里能看到。它有智能体的名称、描述等等，对吧？拥有这种严格的协议，这种严格的规范，确实推动了我们的开发和对齐。因为，你知道，我们所要做的就是与这个规范对齐并遵循它，我们就知道这是前端和后端都消费和生产的契约。所以，嗯，我认为这对我们非常有帮助。而且很酷的是，A2A 有很多扩展，对吧？所以你可以扩展协议，比如添加元数据。嗯，还有 A2UI。嗯，所以有很多有趣的东西，嗯，与 A2A 协议相关。嗯，这就是对我们有效的方法。所以与大家分享。

<details>
<summary>Original English</summary>

**Speaker 4**: the thing i wanted to mention is the agent to agent protocol. so here on the agency, we've had a lot of success with this protocol. so this protocol being the protocol that google created kind of an open protocol for agency in our communicate. but we found this very useful for defining our agent routes, for example, in the back end and our model and our schema to follow this kind of agent protocol. so we model. so for example, there's this thing called an agent card. would you see here? and it's got the name of the agent, a description et cetera, right? and having this kind of a rigorous protocol. this rigorous spec really helped drive our development and drive alignment. because you know, all we had to do was align with this spec and follow this spec, and we knew that this was kind of the contract that our front end and back end both consume and produce. so this, i would say also has been very helpful for us. and what's really cool is a2a has a lot of extensions, right? so you can extend the protocol with like metadata. there's also a2ui. so lots of fun stuff with a2a protocol. this is kind of what's worked for us. so sharing that with you folks.

</details>

### 反馈与评估

**Speaker 4**: 反馈与评估。这里的引语是“发布是开始，而非结束”。所以我们在 AgentScene 这里所做的，是我们有多种方式进行评估和收集反馈。嗯，显然，会有人打电话、发邮件或者直接告诉我们，但主要的方式是我们有“赞”和“踩”的机制。在这里，人们可以告诉我们，“嘿，这个效果很好，这是个很棒的回复”，或者“那不是一个好回复”。我们会接收那个信号并进行迭代，我们可以把它带回去，帮助改进未来的回复。嗯，我们也有自动化评估。在我们的 CI 中，我们有针对真实完成的评估。所以我们可以测试提示词，比如，它是否命中了一些工具？是否做了它应该做的事情？这也有助于提高我们的准确性。所以这些自动化评估，结合收集反馈，确实帮助我们改进了我们的工具、技能和框架，这就是我们能够如此快速迭代的方式。

<details>
<summary>Original English</summary>

**Speaker 4**: feedback and evals. so here the quote is shipping is the start not the finish. so what we do here on the agenscene is we have kind of multiple ways we do evals and collect feedback. obviously, you know, will have folks call in or email us or just let us know and tell us, but the main way is we have the thumbs up and thumbs down mechanism. and here someone is able to tell us, hey this work really well. this was a great response or that wasn't a great response. and that signal we take and are able to iterate on and we can take it back and help improve the response in the future. we also have automated evals. so in our CI, we have evals that run against real completion. so we could test the prompt against. hey, did it hit some tools? did it do what it's supposed to do. and that also helps with our accuracy. so those automated evals in conjunction with collecting feedback really help us improve our tools, our skills, our harness, and that's really how we are able to iterate so fast and so quickly.

</details>

### 人在回路中与沙盒

**Speaker 4**: 人在回路中。这是一个非常酷的功能。我们在智能体循环中确定性地构建了它。如果需要工具调用审批，如果智能体试图进行需要人工批准的工具调用，它会显示这个 UI，人类可以点击接受或拒绝，从而明确拒绝或明确接受智能体试图执行的操作。这确保了，你知道，我们在建立信任，同时也确保安全，特别是当智能体试图执行变更操作时，始终确保人类在驾驶座上。沙盒。另一件我们致力于安全方面的事情是，每当智能体试图执行代码或创建文件时，它都在沙盒中进行。所以我们给智能体提供了沙盒，它可以按需启动这些沙盒，并诚实地使用它们，执行代码、创建文件。这是一个安全的临时隔离空间，智能体可以在其中采取行动，而我们不必担心对我们的生产系统造成任何风险。嗯，这真的非常非常酷。它们最后也会被拆除。所以在这个例子中，我说，“嘿，为2026年AI工程师大会的与会者创建一个PDF，并允许我下载它，这样我就可以与他们分享。”

<details>
<summary>Original English</summary>

**Speaker 4**: humans in the loop. this is a really cool feature. we built where we deterministically in our agent loop. if there is a tool call approval required, so if an agent tries to make a tool call that it needs human approval for it'll show this UI and the human can click accept or reject so explicitly reject or explicitly accept the action that the agent is trying to make. this ensures that you know, we're building trust and also ensuring that we're being safe, especially when the agent trying to do a mutating operation and always always always making sure that humans are in the driver's seat. sandboxing. so another thing that we worked on, going back to the safety slide we just saw, was whenever the agent tries to execute code or tries to create files. it does so in a sandbox. so we gave our agent sandboxes such that it could spin up these sandboxes on demand and it could use those sandboxes honestly, right? code execute code create files. and it's kind of this safe temporary isolated space such that the agent can take action in there and we don't have to worry about any risk to our production system. it's really, really cool. they also get torn down at the end. so in this example, i said, hey, create a PDF for the folks of the AI engineer conference on twenty twenty six. and allow me to download it so i could share with them.

</details>

**Speaker 5**: 你可以看到智能体创建了这个……战斗……slop……slop。

<details>
<summary>Original English</summary>

**Speaker 5**: and you can see that the agent created this fighting slop would slop.

</details>

### 工程实践：对抗 Slop

**Speaker 6**: 我的名字是 Byband。我想谈谈一些一开始可能有点傻的事情。我想快速展示一下我们团队的工程实践。我们不进行代码审查，我们要求每个工程师并行工作，并且我们对人们如何使用 AI 没有标准化。我知道你们几乎所有人都在想什么。我们可能是一家初创公司，而且我可以保证我显然是千禧一代。那么，在没有代码审查的情况下，我们公司到底做什么呢？嗯，大约三年前，我们决定构建一种编程语言。这是一件绝对没有 slop 容身之地的事情。这是一件每次都必须以完全相同方式解析的事情，一件你不能在一年后、一个月后因为做了糟糕的设计决策就改变的事情。你必须正确，持续三年。过去三年，我们一直在与 slop 进行一场未宣之战。当我第一次遇到这个敌人时，我去找了我伟大的导师 Slop Sue，他教了我一些东西：要打败 slop，我们必须成为 slop。所以我们开始准备，然后我们开始获胜。所以当我们思考时，什么是 slop？Slop 就是任何你不阅读的代码，无论你是否承认。这是你的代码库中 slop 最少的时候，珍惜它。所以我们开始用 slop 反击 slop。那么，我们如何用这些工程实践发布一个稳定的编程语言呢？我们经历的第一场小冲突是标准的冲突。招聘优秀工程师的难点在于，可悲的是，你不能告诉他们该做什么。有些人想用 Claude，有些人想用 Cursor，有些人想用他们在 Hacker News 上刚发现的最新东西。所以，我们没有试图在我们的代码库中强制执行标准，而是做了一件不变的事情。我们构建了一个架构文件，而不是使用 Claude MD。只是选择了一些每个模型都能理解的东西。这个文件非常小，只能包含几个月或几年内不会改变的东西。在我们的案例中，它是编译器的层级，你越深入编译器，就告诉开发者至少要和另一个人谈谈，这会减慢一点速度。所以现在我们有了标准。所以任何人都可以使用他们想要的任何东西，但我们面临的真正敌人实际上是设计的战斗。这里的每个人都知道你有正确完美的设计文档。我们团队有一个非常简单的规则：代码可以是 slop，但写作不能。当然，如果我告诉每个工程师这个，他们会写出漂亮的文档，并且他们手写一切，不使用 AI。嗯，可悲的是，并没有。所以我们构建了一个设计文档工具。这个设计文档工具有效地替代了 Notion 和 GitHub 用于设计文档。它有版本控制、评论等所有你想要的功能。显然，我们这样做，人们会使用吗？嗯，可悲的是，并没有。我们在那之上又构建了另一个工具。这个工具是一个 Slack 集成。每次设计文档更新时，这个频道都会收到通知。结果，这个频道很快成为我们公司最受欢迎的频道，在凌晨两点。有人发布了一个设计文档，三个人立刻开始阅读，因为它很有趣。最有趣的东西是设计文档。不是要求变更的电话，但这还不够。所有这些实际上都由 Markdown 文件和简单的 CI 脚本支持。我把它做得像 GitHub 一样，但又不是 GitHub 本身。所以现在智能体可以处理这个。但所有这一切的真正问题是，我构建了这个，我有点精神错乱，我开始每天发布十个设计文档。很快团队就在与我的 slop 作斗争。所以我们不得不回到最后一条规则。这最后一条规则是，如果你要发布一个设计文档，你需要人们真正去阅读它。有了这最后一个标准，

<details>
<summary>Original English</summary>

**Speaker 6**: my name is byband. i'm want to talk about something that is a little, i would say maybe a little silly at first. i'm want to show your team's engineering practices really quickly. we do no code reviews. we require every engineer to work on things in parallel, and we have no standardization how people do ai. and i know immediately what almost all you are thinking. we're probably as sumor wise a start up, and i can guarantee you i'm clearly millennial. so what do we actually do at our company without code reviews? well, we built about three years ago, we decided to build a programming language. that's something that has absolutely no room for slop. it's something that has to parse every single time exactly the same, same way, something you can't just change a year later, or a month later, because you made a bad design decision, you have to be correct for the last three years. we've been an unsung war against slop. and when i first met this enemy, i went to my great mentor, slop sue, and he taught me something to defeat the slop, we must become the slop. so we began and we prepared and then we started winning. so when we think about it, what is slop? slop is just any code you don't read and whether you admit it or not. this is the least amount of slop that your code base will ever have cherish it. so we started fighting back against the slop when we started fighting back with slop. so how do we go ship a stable programming language with these engineering practices? while the first skirmish we ever had was the skirmish of standards. the hard part about hiring great engineers is, you sadly can't tell them what to do. some of them want to use claude. some of them want to use cursor. some of them want to use the latest thing that they just found on hacker news. so instead of trying to hold standards in our code base, we did something that is an invariant. we built an architecture out nd file instead of using claude md. just picks something that every model can just understand. this file has been incredibly small, and it can only have things that will not change for months or for years. in our case, it's the layers of the compiler you go deeper into the compiler, tell the devs that just talk to at least one other person that slows it down a little bit. so now we had standards. so anyone can use whatever they want, but the real foe we face was actually the battle of design. everyone here knows that you have the right perfect design docs. and we have a very simple rule in our team. code can be slop, writing cannot. and of course, if i tell every engineer this, they write beautiful writing, and they hand write everything they don't use AI. well, sadly, not. so we built the design doc tool. this design doc tool is a replacement for both notion and github effectively for design docs. it has versioning, commenting, all the stuff you want. and obviously, we do this, people use it? well, sadly not. we built another tool on top of that. and this tool was a slack integration for that tool. every time a design doc was updated this channel got notifications, and what ended up happening is this channel became the most popular channel on our company really fast at two AM. someone posts a design doc, three people started reading it right away because it's just interesting. the most interesting stuff is design docs. not calling to change, but this wasn't enough. all of this is actually backed by markdown files and simple ci scripts. i make it treat like github without being github itself. so now agents can go do this. but the real problem with all this is i built this, and i hit a little bit of psychosis, and i started shipping ten design docs a day. and soon the team was fighting my slop. so we had to go back at last rule. this last rule was if you're going to ship a design doc, you require people to actually go read it. and with this last standard,

</details>

<!-- chunk 41/54 -->

### 设计狗与架构之战

**Speaker 6**: 我们突然有了质量极高的设计狗。

<details>
<summary>Original English</summary>

**Speaker 6**: we suddenly had design dogs that are incredibly high quality.

</details>

**Speaker 6**: 但架构之战怎么办？你如何让代码库收敛？

<details>
<summary>Original English</summary>

**Speaker 6**: but what about the battle of architecture?

**Speaker 6**: how do you have your code base converge?

</details>

**Speaker 6**: 我们构建了另一个工具。这个工具基本上是一个依赖图可视化工具，包含内部依赖和一些外部依赖，用于观察代码库的变化。

<details>
<summary>Original English</summary>

**Speaker 6**: we build to another tool this tool?

**Speaker 6**: basically visualizor dependency graph internally with some external depencies as well in lows to watch the code base change.

</details>

**Speaker 6**: 它有语义边界，有独立的包。但更有趣的是，我们可以构建CAI工具来保证某些不变性不会被破坏。

<details>
<summary>Original English</summary>

**Speaker 6**: it has semantic boundaries individual packages,

**Speaker 6**: but it's more interesting is we can go build CAI tools that guarantee that certain invariants can't be broken.

</details>

**Speaker 6**: 当你构建一个新包或添加依赖时，它就会泄漏。我们现在有了CI/CD变更，或者简单的git提交历史。它能精确地告诉你什么会被破坏，以及我们实际上正在进行的架构变更。

<details>
<summary>Original English</summary>

**Speaker 6**: and what this does is when cloud build a new package or as a dependency,

**Speaker 6**: it's leaky.

**Speaker 6**: we now have CICD changing or a simple git commit history.

**Speaker 6**: it tells exexactly with break ak by by we're actually tually to american architecture ture change.

</details>

**Speaker 6**: 我们在过去三四个月里没有改变过架构。

<details>
<summary>Original English</summary>

**Speaker 6**: we haven't ged our architecture and last three or four months.

</details>

**Speaker 6**: 但即使我们做了这么多设计狗，即使我们的代码很稳定，你真的会不读代码就直接发布吗？你会信任你的团队这样做吗？想想一门编程语言。一门编程语言有那么多不变性——你有生成器，你有闭包，你有内存分配，你有FFI边界。你能信任那个系统吗？Python在二十五年后依然如此吗？

<details>
<summary>Original English</summary>

**Speaker 6**: but as much as we might do,

**Speaker 6**: design dogs.

**Speaker 6**: and as much as we might have stable code,

**Speaker 6**: would you genuinely ship code without reading it?

**Speaker 6**: would you trust your team to go do that and think about a programming language?

**Speaker 6**: a progragramming language has so many invariance you you gengeners,

**Speaker 6**: you have closures,

**Speaker 6**: you have memory allocation.

**Speaker 6**: you have FA five boundaries.

**Speaker 6**: could you trust that system python as box twenty five years later?

</details>

**Speaker 6**: 嗯，这就是我们做一些完全不同的事情的地方。我们做的是构建一个系统，其中有持续运行的代理，不断创建演示程序。我们拿到这些演示程序，然后让代理尝试从头开始启动一些东西。然后我们查看整个云端转录，看看使用了什么工具，发生了什么。显然，人类可以检查它们。但更重要的是，我们可以让代理去检查它们。代理会发现什么是坏的——不仅仅是语言层面上的错误，还有那些本应一次工具调用就能完成，却用了三次的情况。然后我们可以去发现问题，让人类与这些问题协作，判断哪些是真实的，哪些是幻觉，哪些品味不佳——尽管我讨厌用这个词。然后我们可以让代理去创建修复方案并解决问题。

<details>
<summary>Original English</summary>

**Speaker 6**: well,

**Speaker 6**: here's where we did something insightly different.

**Speaker 6**: what we did was we built a system that actually has agents constantly running and creating demo programs.

**Speaker 6**: we take these demo programs,

**Speaker 6**: one second,

**Speaker 6**: and we have agents try and spin something up from scratch.

**Speaker 6**: we then look at the entire cloud transcripts,

**Speaker 6**: see what tools you see what happened.

**Speaker 6**: and obviously,

**Speaker 6**: ly,

**Speaker 6**: as humans can inspect them.

**Speaker 6**: but more importantly,

**Speaker 6**: we can have agents go inspect them.

**Speaker 6**: and agents find what was was ls.

**Speaker 6**: what was bad and not just what was bad into intervworld is incorrecting language.

**Speaker 6**: but what's the three tool calls when it should have only taken one?

**Speaker 6**: and then we can go head and find issues,

**Speaker 6**: and we can have humans collaborate with these issues to figure out which oneare real,

**Speaker 6**: which one's are hlucinations,

**Speaker 6**: which ones are don't have taste as much as i hate to use that word.

**Speaker 6**: and then we can have agents go head and create fixes to these problems and go address them.

</details>

**Speaker 6**: 最重要的是，我们不只是试图检测这些问题，我们可以更进一步。如果你能找到语言特性，而不是猜测什么好什么坏呢？你可以进行A/B测试。你可以找出哪个方案需要的工具调用更少，哪个方案错误更少，哪个方案产生了正确的结果。然后确定性地知道发生了什么。

<details>
<summary>Original English</summary>

**Speaker 6**: and most importantly,

**Speaker 6**: instead of trying to just detect these issues,

**Speaker 6**: we can go once that further.

**Speaker 6**: what if you could find language features instead of guessing wall was good guessing.

**Speaker 6**: what school was good.

**Speaker 6**: you could go in AB taxi.

**Speaker 6**: you could forget out onees took less tool calls,

**Speaker 6**: which one took,

**Speaker 6**: which one made less errors,

**Speaker 6**: which one produce a correct outcome.

**Speaker 6**: and deterministically know what's going on.

</details>

**Speaker 6**: 关键在于，你可以开始构建数据和系统，而无需编写一行代码。我在这里最关心的不是这些工具中的某一个是你应该去构建的，而是事实是，为了赋能一门编程语言，它不需要八个人，不需要两年多的时间。它需要成百上千、成千上万的人工时。然后你仍然会得到一个有缺陷的系统。而今天，我们可以花费数十亿个token让它工作，让它稳定。你也可以回家构建这些内部工具和这些粗糙的工具，确保你的代码库可以在不必真正阅读每一行代码的情况下发布，因为你的工程师不会去读的。我认为我们可以开始赢得这场战斗，一点一点地。随着我们赢得这场战斗，slop可以被击败。

<details>
<summary>Original English</summary>

**Speaker 6**: the point is you can start building data or and systems without ever writing a single line a code.

**Speaker 6**: and the thing that really i care about the most over here is not that any one of these tools is specifically what you should go build,

**Speaker 6**: but the fact of the matter is,

**Speaker 6**: in order to able the programming language,

**Speaker 6**: it won't have taken eight people.

**Speaker 6**: it won't have taken less than two years.

**Speaker 6**: it were have taken hundreds and thousands and tens of thousand man hours.

**Speaker 6**: and then you would still have a broken system.

**Speaker 6**: and today,

**Speaker 6**: we can to spend billions of tokens and make it work,

**Speaker 6**: and we can make it stable.

**Speaker 6**: and you two can go home and build these internal tools and these sloppy tools to make sure that your code basis can ship without really having to read necessarily every single line of code,

**Speaker 6**: because your engineers aren't going to.

**Speaker 6**: and i think we can start winning this battle le and sloloand as we win this battle.

**Speaker 6**: slop can be defeated.

</details>

**Speaker 6**: 但遗憾的是，我有一件悲伤的事情要说。我认为我们仍然会输掉这场战争。我认为我们会输掉这场战争的原因是我们试图使用的一些基础性东西本身就有缺陷。

<details>
<summary>Original English</summary>

**Speaker 6**: but sadly,

**Speaker 6**: i have a sad thing to say,

**Speaker 6**: i think we're still going to lose the war.

**Speaker 6**: and i think the reason that we're going to lose this war is because some of the foundational stuff that we try and go use itself is broken.

</details>

**Speaker 6**: 你们中有多少人使用过TypeScript？可能你们大多数人，希望如此，或者至少你们的代理在上面运行过什么东西。你知道TypeScript的主要设计杠杆是正确性和生产力之间的平衡吗？这里有个星号，因为他们真正指的是人类生产力。如果你仔细想想，有些东西你永远不会在编程语言的最核心层去做。如果你是为一个人类从不编写一行代码的世界设计，让我告诉你这真正意味着什么。

<details>
<summary>Original English</summary>

**Speaker 6**: how many of have use sidescrit？

**Speaker 6**: probably most of you hopefully at this point or at least your agents have so something run there？

**Speaker 6**: did you know that types？

**Speaker 6**: er's main design le is the strike balbalted，

**Speaker 6**: corcorrectness and productivity.

**Speaker 6**: and there's an astricts year because what they really mean is human productivity.

**Speaker 6**: and if you think about it，

**Speaker 6**: there are things you would never do in a programming language at the very core layer.

**Speaker 6**: if you were designing for a world where where humans never wrote a single encode and let me show you what that really means.

</details>

**Speaker 6**: 我要写点东西，你们猜猜这段代码是做什么的。这个呢？或者这个？这个呢？为什么我们在排序时要把东西转成字符串？这就是slop被内置到语言中了，不管你喜不喜欢。这个呢？我喜欢TypeScript的这一部分，你知道吗，我的代理也喜欢TypeScript的这一部分。这就是slop被内置到语言中了。不管你喜不喜欢，使用这些工具构建的系统都会有slop。我很抱歉，讲错了。

<details>
<summary>Original English</summary>

**Speaker 6**: i'm going to to write something and try and guess what this code does pretty safe，

**Speaker 6**: what about this one or even more？

**Speaker 6**: so this one，

**Speaker 6**: why do we turn things to strings when we sort them？

**Speaker 6**: this is just slop big into the language，

**Speaker 6**: whether you like it or not.

**Speaker 6**: what about this？

**Speaker 6**: i love this part of type script，

**Speaker 6**: and you know what my agent loves this part of type script.

**Speaker 6**: this is slop big into the language.

**Speaker 6**: and whether you like it or not，

**Speaker 6**: the systems will have slop.

**Speaker 6**: if you build using these these tools，

**Speaker 6**: i'm i'm sorry，

**Speaker 6**: wrong talk.

</details>

**Speaker 6**: 但你想一下JavaScript做了什么。JavaScript存在了，然后JavaScript存在之后，我们开始构建系统。所以我们有了LiveScript，我们构建了CoffeeScript，TypeScript。现在我们正试图构建Effect。但问题是底层的东西已经坏了，而且我们编写代码的方式现在也不同了。所以我们为什么要修补这样的东西？我们为什么不尝试做一些不同的事情呢？

<details>
<summary>Original English</summary>

**Speaker 6**: but if you think about what javascript does javasscript exists，

**Speaker 6**: and then after javascript existed，

**Speaker 6**: we started building systems.

**Speaker 6**: so leare it on，

**Speaker 6**: we built coffee script，

**Speaker 6**: the entitship.

**Speaker 6**: and now we're trying build effect.

**Speaker 6**: but thing is the thing underneath is already broken and more so the way we right code is also different now.

**Speaker 6**: so why are we trying to pch something like this？

**Speaker 6**: why don't we just try and do something a little different？

</details>

**Speaker 6**: 我认为如果我们尝试这样做，我们可能需要一种虚构的语言。让我展示一下Bammo真正能做什么。当你开始从第一性原理思考，如何从最基础的层面本身来对抗slop时，我一直在谈论不读代码。这真的重要吗？好吧，让我展示一种思考代码的新方式。

<details>
<summary>Original English</summary>

**Speaker 6**: and i think what we might need if we try and go do that is basically going to be a made up language.

**Speaker 6**: so let me show you what bammo really can do.

**Speaker 6**: and when you start thinking from first principles，

**Speaker 6**: how you can try and combat swap from a very foundational leyer itself，

**Speaker 6**: i keep talking about not reading code.

**Speaker 6**: does it even matter？

**Speaker 6**: well，

**Speaker 6**: let me show you a new way to think about code.

</details>

**Speaker 6**: 这并不是说我们都必须马上这样做。但是，如果我每次看代码循环时，每次看代码时，我真正看到的不是代码本身，而是一个能为我可视化所有代码的小东西呢？当我点击时，它会带我到确切的行，我链接到的代码。如果我想要一个稍微宽泛的视图，我可以放大并点击，让它展开。我可以更有趣地浏览我的代码库。

<details>
<summary>Original English</summary>

**Speaker 6**: and this isn't to say，

**Speaker 6**: we all have to go do this right away.

**Speaker 6**: but what if every single time i looked at code loops？

**Speaker 6**: what if every single time i looked at code，

**Speaker 6**: what i really saw was not the code itself，

**Speaker 6**: but a quick little thing that could actually visualize all the code for me.

**Speaker 6**: as i clicked around，

**Speaker 6**: it took me to exact lines.

**Speaker 6**: the code i was link to.

**Speaker 6**: if i wanted to have a slightly brought of you，

**Speaker 6**: i could zoom in and click around and have it expand.

**Speaker 6**: and i could naviget my code basis more intereingly.

</details>

**Speaker 6**: 我快速运行一下这个。在它运行时，它会向你展示一个不同的管道，而你无需阅读任何代码。你看，我正在设置一个带代理循环的outh和haan，因为其中有语义边界。我可以展开这个。我可以继续展开。因为我希望那里没有太多slop，让那是slop然后走开。所以，不必理解所有代码，我可以选择我想阅读和理解的代码部分，并在真正关心时跳转到确切的行。

<details>
<summary>Original English</summary>

**Speaker 6**: i'm moof of this rurun really quickly.

**Speaker 6**: while while it runs shshoyou a different pipeline without any you ever reading the code，

**Speaker 6**: you know，

**Speaker 6**: i'm setting up south and haan agent loop because of semantic boundaries in there，

**Speaker 6**: i can expand this.

**Speaker 6**: i can keep expanding this.

**Speaker 6**: and because i hope that's too much slop with let that be slop and walk away.

**Speaker 6**: so instead of having to understand all the code，

**Speaker 6**: i can opt into what parts of the code i want to read and understand and go to the exact lines when i really care about them.

</details>

**Speaker 6**: 如果我们回到我之前运行的管道，如果在它运行时，我实际上可以获得一个完整的执行跟踪呢？在一个我们不阅读所有代码的世界里，理解代码的唯一方式实际上是通过执行跟踪。实际上，通过精确地看到在任何给定时间，我的程序的哪些部分花费了多少时间。如果你想跟踪你的程序，想想如果你必须在TypeScript中跟踪所有管道，你的程序会有多慢。这是不可持续的。

<details>
<summary>Original English</summary>

**Speaker 6**: if we go back to the previous pipeline，

**Speaker 6**: i was running，

**Speaker 6**: what if while it's running，

**Speaker 6**: i can actually get a full execution trace in a world where we don't read all the code.

**Speaker 6**: the only way to understand the code is actually by the execution trace.

**Speaker 6**: and actually，

**Speaker 6**: by seeing exactly how much time will spent on what parts of my program at any given time，

**Speaker 6**: if you want to go and actually track your program through，

**Speaker 6**: think about a slow，

**Speaker 6**: your program would be if you had to go trace everything in pipe on our typshriit.

**Speaker 6**: it's untennible.

</details>

**Speaker 6**: 最棒的是，如果你从第一性原理出发，你可以让这几乎零性能成本。我们不仅可以让它对人友好，而且因为这对代理来说也是内置的，你可以让它做到每个文件都有一个跟踪系统，供Claude导航。这样Claude就能找到哪里是bug，哪里是错误，哪里是低效，并优化你的代码，而无需你自己动手。

<details>
<summary>Original English</summary>

**Speaker 6**: and the best part here is if you start from first principles，

**Speaker 6**: you can make this effectively zero performance cost 没有。

**Speaker 6**: not only can we make it great for humans，

**Speaker 6**: but because that's all belt for agents anyway，

**Speaker 6**: you can go ahead and make it.

**Speaker 6**: so that every single file has a tracing system that clod can navigate through.

**Speaker 6**: so laud can find what we're bogs，

**Speaker 6**: what were ears.

**Speaker 6**: and what we're ineficficenciciand and art opoptizing yhode without you having to do it yourself.

</details>

**Speaker 6**: 我认为如果我们开始以这种方式思考，重点不在于阅读所有代码，而在于作为人类理解你正在使用的系统，以及你可以构建的工具，这些工具可以为你提供关于你正在使用的系统的信息。但我认为还有另一层。

<details>
<summary>Original English</summary>

**Speaker 6**: and i think if we go sort thinking matter from this way，

**Speaker 6**: it's not so much about reading all the code，

**Speaker 6**: but it's more so about as a human understanding the system mature working with and the tools that you can build，

**Speaker 6**: can give you information about the system that ure working with.

**Speaker 6**: but i think there's another letter to it.

</details>

**Speaker 6**: 我们花了几十年构建IDE工具。想想花了多长时间，才让一个像我这样至今仍不会退出Vim的人，最终能开始使用VS Code。那是一个美好的日子。我成了一个真正的程序员。好吧，根据某些人的说法，我仍然不是，因为我不会写Vim代码。但是，以代理为先的工具是什么样的呢？

<details>
<summary>Original English</summary>

**Speaker 6**: we spent decades building.

**Speaker 6**: i tool link，

**Speaker 6**: and that think about how long it took before someone like me who does not know how to escape them to this day，

**Speaker 6**: can finally start using VS code.

**Speaker 6**: it was a beautiful day when that happened.

**Speaker 6**: i became a real programmer.

**Speaker 6**: well，

**Speaker 6**: according some people，

**Speaker 6**: i'm still not because i can't write vim code，

**Speaker 6**: but what does agent first tooling look like？

</details>

**Speaker 6**: 我想我们都熟悉grep。所以我不会去谈论它，但我会谈论ripgrep，因为如果我想在我的代码库中grep并理解它是什么，我不应该在任何地方使用grep。我会用ripgrep搜索类似"calculate"的东西。它会给我一堆代码，显示所有使用它的地方，可能有点用。但如果你可以转而描述代码呢？比如说，你能为我描述一下"calculate"吗？如果它附带所有文档呢？如果它附带实际的源代码呢？如果它还告诉你它在底层所有被使用的地方呢？在底层，我们可以让多个工具调用突然变成单个工具调用。

<details>
<summary>Original English</summary>

**Speaker 6**: i think we're all familiar with grap.

**Speaker 6**: so i'm not going to go and talk about it，

**Speaker 6**: but i will talk about a rip grap because ggrap should not be used anywhere if i want to grgrap through my code base and understand what it was，

**Speaker 6**: i would regrab say something like calculate.

**Speaker 6**: and i'd give me a bunch of code where everything was being used and maybe you be somewhat useful.

**Speaker 6**: but what if you could instead to start describing code and say it，

**Speaker 6**: can you described calculate for me，

**Speaker 6**: what if it came with all the doshinings？

**Speaker 6**: what if it came with the actual source code？

**Speaker 6**: and what if it also told you everywhere was actually use under the hood，

**Speaker 6**: we can make something uto be multiple tool，

**Speaker 6**: calls a single tool call of a sudden.

</details>

**Speaker 6**: 如果你学习正在使用的库的方式，不必进行网络搜索呢？你只需说，你也可以直接询问任何外部库，然后信息就直接给你了。

<details>
<summary>Original English</summary>

**Speaker 6**: what if the way you want to learn about libraries that you are using instead of have to do a web search？

**Speaker 6**: you just said，

**Speaker 6**: you could just ask for any external library as well and was just given to you.

</details>

<!-- chunk 42/54 -->

### 从代码阅读到代码运行：理解系统的全新方式

**Speaker 6**: 因为当我刚开始热爱编程时，Ted 学习教会了我一个宝贵的经验：代码永远是真理的唯一来源。不要阅读任何东西，只读代码本身。文档可能会撒谎，um，实际的描述或架构文件、readme 文件肯定会撒谎，但代码不会撒谎。除非你正在处理某些我们重新收集的东西。然后当你沿着这条路走下去时，你会从不阅读代码到理解架构，从不搜索代码到精确理解你在每个工具调用中得到了什么。但你接下来会做什么？嗯，我为了真正理解代码所做的最后一件事就是运行代码。

<details>
<summary>Original English</summary>

**Speaker 6**: because when i first love start, ted learning had a code one valuable lesson. i had was the code is always a source of truth. don't read anything, but the code itself, the docs may lie the um the actual description or architecture file readme file will definitely like, but the code cannot lie. except if you're working on some we're recollectures. and then when you go down this road, you go from not reading the code to understand the architecture you go from not searching the code to understanding exactly what you're getting an everyone tool call. but what's the next thing you do? well, the last thing i do to truly understand code is i run the code.

</details>

**Speaker 6**: 那么，如果你运行的每一个东西，你写过的每一个函数都能立即被使用呢？你知道，就像这里的 Potiticco，可以作为一个简单的 CI 命令立即使用。所以如果我运行 `add`，它就变成一个带有附加参数的 CI 命令，我可以快速运行它并看看会发生什么。如果我拥有的每一个工具都能被打包成一个独立的单元测试，我可以直接运行它，而无需实际执行任何代码呢？并且，作为 Alalc 工具，它就像一个二进制文件，其中功能被捆绑在一起。我们可以构建非常快速的工具，让代理不必费力地遍历正在发生的事情。一切都是类型安全的，一切都是确定性的，一切都是可猜测的。最棒的是，想象一下你可以在任何系统上构建，而你的代理不必担心跨 Windows、Mac 和 Linux 的部署。你可以针对任何你想要的层。它可以为任何架构构建，包括 wasm 系统。突然间，作为一名工程师，你被超级赋能了，你不再受限于底层系统所能做的事情。你可以非常快速地行动，你可以以代理的速度行动。

<details>
<summary>Original English</summary>

**Speaker 6**: so what if every single thing you ran every single function you ever wrote was immediately available. you know, potiticco over here was immediately available as a simple CI command. so if i run add, add becomes a CI command that has arguments attached to it, and i can run it really quickly and see what happens. what if every single tool i had could be packed into a unit test, that's completely stand alone that i can just run without ever having to actually execute any of the code. and as alalc tools, a binary that has functions just bundled in some way. we can build really quick tooling where agents don't have to go through what's happening. everything is typesafe, everything is deterministic, and everything is actually guessable. and the best part is imagine you could build on any system, and your agents don't have to worry about deployments across windows mac and linux. and you can just target any layer you want. and it builds for any architecture, including wasm systems. all of a sudden as an engineer you're supercharged, you're no longer bound by what you can do in the systems underneath you are preventing. you can just move very fast. you can move at agent speed.

</details>

### 修复 JavaScript 的深层问题：错误处理

**Speaker 6**: 但我之前谈到的很多内容都是关于工具。如果我们尝试修复 JavaScript 的一些真正问题呢？一些深植于语言中的东西，不是那种表面的东西。我的意思是，更重要的事情，比如错误处理。除了 Rust，你见过漂亮的错误处理吗？嗯，我看到代理在这里做的事情是，你使用 try catch，然后它们不断地嵌套 try catch，一个接一个，然后想象它们最终放弃了，记录一些错误然后处理它。如果我们能从最根本的原则开始做错误处理呢？在那个世界里会发生什么？嗯，我向你展示了 `add` 和 `multiply` 函数。我没有向你展示 `divide`。`divide` 是危险的。它很吓人。所以我们来看看 `divide`。你可以在这里看到，`divide` 抛出一个除以零的错误。但还会发生什么？这个函数实际上知道它会抛出除以零的错误，而你无需编写任何代码。如果我向上到 `calculate` 函数，它在某个时刻调用了 `divide`，这个函数也知道它会抛出除以零的错误。所以错误类型现在被推断出来了，你无需做任何猜测。这意味着当你捕获或处理错误时，我们可以做穷举保证，编译器可以证明你已经处理了错误或者没有处理错误。不再是猜测了。没有人知道，它是被保证证明的。所以如果你想发布一个保证永远不会抛出的 API，嗯，这个系统是坏的，因为它不满足约束。它有两个你没有抛出的错误。如果你想捕获那个错误，嗯，我可以在一秒钟内为他们编写代码，但你可以开始捕获某些错误。我的意思是，我现在将返回一个哨兵值。现在这个解析，之前会抛出除以零错误，现在保证不再抛出除以零错误了。因为如果我在这里捕获任何异常，我每次都返回一个零值。编译器和工具可以为我们做很多工作。

<details>
<summary>Original English</summary>

**Speaker 6**: but a lot of the stuff that i've been talking much to the state has been about tooling. what if we tried to fix some the real sense of javascript, some of the stuff that is deep in the language, not the sort stuff. but i mean, more important stuff like errors. have you seen error handling be beautiful ever other than rust? um what i see agents do over here is you do try catch, and then they keep nesting try catch after try catch after try catch and imagine they give up in some sort of lot, log some error happen and deal with it. what if we could do error handling from very first principles, what happens in that world? well, i showed you add multiply function. i didn't show you divide. divide is dangerous. it's spooky. so let's go look at divide. you can see over here, divide, throws a division by zero error. but what else happens? the function actually knows that it throws division by zero error without you having to write any any code, if i go up to the calculate function, which at some point calls divide, this function also knows it throws division by zero error. so error types now get inferred without you ever having to do any guess. that means that you catch or handle errors, we can do exhaustive guarantees, and the compiler can prove that you have handled the error or not handled the error. it's no more guessing. there's no one knows it's guaranteed to be proven. so if you want to ship an api where guarantees, it never throws. well, this system is broken because it doesn't meet the constraints. it has two errors that you're not throwing. if you want to go catch that. well, i can write the code for them a second, but you can start catching certain errors. i mean, i'm going to return a sentinel value for now. and now this parsing, which previously threw division by zero error is now guaranteed to no longer throw the division by zero. because if i catch any exceptions in here, i return a zero value, every single time, the compiler and the tooling can do a lot of work for us.

</details>

**Speaker 6**: 我们在代码库中已经习惯了这一点。我们中的许多人可能不知道编译器在底层是如何工作的，但我们信任它们。代码是信任的问题。我们不盲目使用代码的原因是，我们信任它，以及底层的系统。我们没有足够的可追溯性。还有一件事。但在我告诉你们所有人都去编写一堆 Bammo 代码之前——因为我去过那里，我可以告诉你会有人对我说什么——他们会说，嘿，使用一种新的编程语言并不能解决你所有的问题，它只会带来一大堆新问题。所以我们说，如果我们试图让每个人都把世界上所有的代码重写进这个新系统，我们就会在“垃圾代码”之战中失败。那么，一个不需要你重写所有代码的解决方案是什么样的呢？嗯，我们大约两年前开始思考这个问题。我们当时说，如果你能使用 Bammo，不仅仅像我今天展示的那样独立使用，而是从你选择的任何现有语言中使用呢？从 Python 到 TypeScript，到 Rust，到 Go，到 Ruby，到 Java，到任何之后出现的新语言。如果 Bammo 中的每一个函数都能在你选择的语言中立即被访问呢？在这种情况下，我正在直接从 Python 调用 Bammo 的 `calculate` 函数，并且它是完全类型安全的。不仅如此，我们还能在 TypeScript 中得到 `calculate`。以防我们中有些人想编写正确的代码。所以 Bammo，虽然没有函数着色，但它确实让你能够在代码中做任何你想做的事情。但如果你想要更酷一点呢？如果你开始跨语言边界传递 lambda 呢？我有一个叫做 `withTimeout` 的函数，这个函数会在一定秒数后超时。如果这个工作没有完成，无论需要多长时间，它都保证会超时。在那个世界里，你甚至可以跨桥传递 Python lambda。你可以跨桥传递泛型。你可以传递闭包。它应该就能工作。所以工程师不必快速上手。更重要的是，当代理做某事时，类型系统永远不会撒谎，类型系统成为绝对的真理中心，防止不变量进入你的代码库。

<details>
<summary>Original English</summary>

**Speaker 6**: and we're already used to this in our code bases. we many of us probably don't know how compilers work under the hood. and we trust them code is a matter of trust. the reason that we don't use code blindly is, we trust it, and the systems underneath them. we don't have enough traceability. one more thing. but before i tell you all to go write a bunch of bammo code because i've been there. and i can tell you what someone would tell me, they said, hey, using a new programming language is not going to solve all your problems it's just going to come with a whole slew of new problems. so we said, i think we'll lose the war on slop if we try to ask everyone to rewrite all the code in the world into this new system. so what does a solution like that look like where you don't have to rewrite all your code? well, what we started to do was we started to think about that about two years ago. and we said, what if you could use bammo, not just stand alone, like i show today, but from within any existing language of your choice, from python to typescript, to rust, to go to ruby, to java, to anything new that comes up even after it. what if every function in bammo is immediately accessible in the language of your choice. in this case, i'm calling the bammo calculate function directly from python and it's completely type safe. not only we get calculate, we get calculate in typescript. in case some of us want to write correct code. so bammo while it has no function coloring, it does give you the benefit of having to do whatever you want across your code. but what if you want a little bit cooler, what if you started passing around lambdas across language boundaries? i have a function called with timeout this function times out after a certain number of seconds. and if this work doesn't complete, it's guaranteed to no matter how long it takes. in that world, you can even pass python lambda across the bridge. you can pass generics across the bridge. you can pass closures, it should just work. so engineers don't have to go fast with it. and more importantly, so when the agent does something, the type system never lies, the type system becomes the absolute center of truth that prevents invariants from entering your code base.

</details>

### 核心理念：构建复杂系统的新方式

**Speaker 6**: 我今天真正想谈的不是任何一件具体的事情，而是一个通用的概念。你可以在没有传统系统（如代码抽象）的情况下构建极其复杂的系统。你可以并行工作，你可以随心所欲地使用 AI，而不需要任何形式的标准化。但最重要的是，你必须非常深思熟虑地考虑你的工程团队如何在底层使用这些系统。当我们开始构建 Bammo 时，我没想到能够构建出我们做到的一些软件。就在昨天，我的一名工程师纯粹用 Bammo 构建了一个部分 C 编译器。所以当你开始推动这些系统的边界，并且在某种程度上停止阅读代码时，在我看来，它为工程团队释放了闸门，让他们能够真正填补旧流程中存在的空白。

<details>
<summary>Original English</summary>

**Speaker 6**: and what i really wanted to talk about today was not any one specific thing, but it's a general concept. you can build incredibly complex systems without traditional systems like code abstractions. you don't you can work in things in parallel and you can use AI. however, you want without requiring any sort of standardization. but the most important part is you have to be incredibly thoughtful, about how your engineering team actually uses the systems under the hood. when we started building bammo, i didn't think it would be possible to build some of the software we did. and just yesterday, one of my engineers built a partial c compiler purely in bammo. so when you start pushing the boundaries of these systems and you stop reading the code in some ways. in my mind, it releases the flood gates for engineering team to actually cover the gaps of what existed in your old process.

</details>

**Speaker 6**: 你有没有在一家没有 CI/CD 的公司工作过？他们说，添加 CI/CD 会拖慢我们的速度。他们确实在添加 CI/CD 的三个月里慢了下来。但之后，他们的速度就快多了。如果我们要以代理的速度交付，我们的流程必须进化。记住，这是你的代码库迄今为止“垃圾代码”最少的时候。所以拥抱它，并开始反击。我大约在十五年前爱上了软件，这是第一件真正改变我感知世界方式的事情。我真的、真诚地不希望软件失败，我认为我们都可以构建一个美丽软件的世界。我认为需要的是，我希望你们每个人今天回家后，去构建这些“垃圾”工具，让你的系统更健壮，让你的流程更健壮。然后，对于你们中最勇敢的人，我希望你们回去思考这些核心基础层系统，思考它们是如何被破坏的，看看你是否能想象出一种修复它们的方法。我认为我们确实需要一个新 Git。我认为我们确实需要一个新数据库。是的，我认为我们需要一种新的编程语言。我是 Vivek，我在 Bammo 工作。谢谢。

<details>
<summary>Original English</summary>

**Speaker 6**: have you ever worked at a company that had no CICD? they said, adding CICD would slow us down. they did slow down for three months while they added it. but after that, they move a lot faster. our processes have to evolve if we are going to ship at agent speed. and remember, this is the least amount of slop, your code base will ever have to this day. so just embrace it and start fighting it back. i fell in love with software about fifteen years ago, and it was the first thing that truly changed the way i perceived the world. and i really genuinely don't want software to die, and i think we can all build a world of beautiful software. and i think what it takes is i want each of you to go home today and build these sloppy tools, make your systems more robust, make your processes more robust. and then for the bravest of you, i want you to go back and think about these core foundation layer systems, think about how they're broken and see if you can imagine a way to fix them. i think we do need a new git. i think we do need a new database. and yes, i think we need a new programming language. i'm vivek and i work on bammo. thank you.

</details>

### 生产级智能体系统的评估

**Speaker 7**: 我是 Sham Gupta，我是 Matter 的委托代表，负责为 Matter 的 Supportalab 和基础设施组织构建训练和推理基础设施。今天，我们将讨论生产级智能体系统的评估。当大多数人听到“评估”这个词时，他们会想到基准测试——模型在基准测试上得了 90 分，新版本得了 91 分，团队会庆祝一下。但智能体系统从根本上改变了评估的含义。今天，系统存储了提示词、重试逻辑、计划、工具调用、工具信息、执行工作流。它们与生产基础设施交互。问题不再是模型是否生成了正确的、正确的字符。问题是系统的行为质量。它们做到了吗？

<details>
<summary>Original English</summary>

**Speaker 7**: it was sham gupta, and i was offering delegate meter, a king on building of training and inference infrastructure for the matter, supportalab and infrastructure organization. today, we're going to be talking about production of agentic systems. when most people hear the word evaluation, they think about benchmarks a model scores ninety percent on benchmark, a new version, scores ninety one percent, a team celebrates a little bit. but agentic systems have fundamentally changed what evaluation means. today, the system stores the prompts, the retries, the plan, the tool calls, the tool information, the execute workflows. they interact with the production infrastructure. the question is no longer did the model generate the right, right character. the question is the system behavior quality. do they?

</details>

<!-- chunk 43/54 -->

### 评估的演变：从基准到生产可靠性

**Speaker 7**: 我想讨论一下，对于现代基于范围标记的混合基础设施，评估是如何演变的。这就是问题所在。几乎每个AI组织如今都遇到这个问题：离线基准测试在持续改进，但生产环境的可靠性却常常仍然不可预测。为什么会这样？因为基准测试衡量的是模型能力，而生产环境衡量的是系统行为。基准测试无法捕捉到偶发故障、AB测试环境变化、可用性、长尾学习增长，以及随着系统变得更加动态，基准性能与生产性能之间的差距会越来越大。结果就是许多团队今天所经历的：高基准分数，但生产行为却不尽如人意。传统的评估侧重于输出，但我们应该问模型一个问题：它是否产生了正确的答案？而智能体系统迫使我们问一个不同的问题：系统是否按照预期行为运行？包括规划质量、工具使用、执行、从故障中恢复以及决策制定。换句话说，我们正在从评估答案转向评估工作架构，这需要根本不同的评估架构。

<details>
<summary>Original English</summary>

**Speaker 7**: I would like to discuss how evaluation is evolving for modern range marking into blution infrastructure. This is the problem. Almost every AI organization is encountering today. Offline benchmarks continue improving, yet production reliability often remains unpredictable. Why is that? Because benchmarks measure model capability, production measures system behavior. A benchmark doesn't capture dull failure, AB test changes, use availability, long learning growth lows, and as systems become more dynamic, the gap between the benchmark performance and production performance grows. The result is what many teams experience today: high benchmark scores, but ununderlove the production behavior. Traditional evaluation focus on outputs, but we should ask a question to the model: did it produce a guide answer? Agency systems force us to ask a different question: did the system behavior and dedupllanning quality, tool usage, execution, recovery from failures, decision making? In other words, we are moving from evaluating answers to evaluating architectures, and that requires fundamentally different evaluation architectures.

</details>

**Speaker 7**: 许多团队仍然认为幻觉是生产环境中主要的故障模式。但这通常只是其中一个类别。智能体系统引入了全新的故障模式层级。在最底层，有记忆故障、可重复性故障、安全故障。往上走，你必须考虑推理错误。再往上，你必须考虑协调故障。这就是为什么仅仅评估模型输出会错过大多数生产环境中观察到的问题。而最有用的思维转变是：停止像研究员一样思考，开始像SRE或接近SRE的方式思考。不要用准确率来衡量成功。要衡量可靠性、延迟、成本，以及智能体系统是否采用了相同的方法。目标不是最大化基准分数，目标是最大化可靠的结果。可靠性成为首要指标，准确率只是其中一个组成部分。这就是我思考现代评估系统的方式。

<details>
<summary>Original English</summary>

**Speaker 7**: Many teams still think hallucinations are the primary failure modes in production. They are often just one category. Agent systems introduce a whole hierarchy of failure modes. At the very foundation, there are memory failures, repeatable failures, safety failures. As you go up, you have to think about reasoning mistakes. People banning rily ilecuand at the highest have to think about coordination failures. And this is why evaluating only model output misses the most production rescue observed. While the most useful mindset shift is to stop thinking like researchers and start thinking like SRE or approaching SRE. Don't measure success using accuracy. Measure reliability, latency, cost, and agent systems take the same approach. The goal is not maximizing the benchmark scores. The goal is to maximize dependable outcomes. Reliability becomes the north metric, accuracy becomes only one boot. And this grammar is how I think about modern evaluation systems.

</details>

**Speaker 7**: 你可以看到，基准测试很有用，它们可扩展、可重复，但它们的操作范围有限。基于场景的评估，这些模拟真实工作流程的评估，以及你看到的推广方式，这才是最高价值的评估信号来源。令人惊讶的是，大多数评估数据实际上来自真实用户与真实系统的交互。现在让我们谈谈，评估常常仍然关注于微小的提示变化，而不是评估提示本身。例如，一个客户支持流程是一个协调流程。一个搜索流程在即时环境中运行。我们衡量的是条件正确性、工具选择、规划质量、资源使用，这些在高规模下变得指数级重要。关键的技术要点是：评估应该由信号驱动，而不是由流程驱动。一旦系统上线，每一次交互都成为一个信号。这是评估思维中最大的转变之一。生产流量不再是单纯的流量，它变成了评估数据。我们连接执行轨迹、用户结果、升级事件、故障、反馈信号。生产环境是任何组织都将拥有的最大、最具代表性的评估数据集。

<details>
<summary>Original English</summary>

**Speaker 7**: You can see they are benchmarks. They are useful, they're scalable, they're repeatable, but the operation range is limited in the middle. The scenario-based evaluations, these simulate realistic workflows. And the way to see promotion delimilitary. This is where the highest value evaluation signals come from. The surprising insight is that the most evaluation data often comes from real users interacting with real systems. Now let's talk about, it often involves so often evaluations still focus on much dollar changes instead of evaluating prompts themselves. For example, a customer support flow is a coordination flow. A search flow operates inside the immediate environment. We measure the condition accuracy, tool selection, planning quality, resource usage, which becomes exponentially high at high scale. The key technical takeaway is that evaluation should be signal-driven, not flow-driven. Once a system hits production, every interaction becomes a signal. This is one of the biggest shifts in evaluation thinking. Production traffic is no longer just traffic, it becomes evaluation data. We connect execution traces, user outcomes, escalations, failures, feedback signals. Production is the largest and the most representative evaluation data any organization will ever have.

</details>

**Speaker 7**: 但是，有多少组织将人类视为反馈系统？我认为这是错误的框架。人类是评估者。他们提供自动化系统无法提供的信号：主观性、信任、有用性和安全性。这些信号对于校准评估流程和识别自动化指标中的盲点变得至关重要。最成功的系统结合了自动化评估和有针对性的人工审查。现在，智能体系统持续漂移：模型变化、新版本每隔几个月发布一次。

<details>
<summary>Original English</summary>

**Speaker 7**: But how many organizations view humans as feedback systems? I think that's the wrong framing. Humans are the evaluators. They provide signals that automated systems cannot: subjectivity, trust, usefulness, and safety. These signals become really critical for calibrating evaluation pipelines and identifying blind spots in automated metrics. The most successful systems combined automated evaluation with targeted human review. Now, agent systems drift constantly: model changes, new version every couple of months.

</details>

**Speaker 5**: 提示词可以改变，工具可以改变，用户行为可以改变。

<details>
<summary>Original English</summary>

**Speaker 5**: The prompts can change, tools can change, user behavior can change.

</details>

### 构建适用于真实世界的循环

**Speaker 8**: 大家好。我是Human Layer公司的联合创始人。我来这里谈谈循环。我想我们最近都在构建循环。但我最近意识到，我想我们可能都做错了。循环非常强大，别误会我的意思，但围绕它们的很多讨论都是炒作驱动的，真的没什么帮助，对吧？我认为我们整个行业不知何故有一种想法，认为我们可以把提示词通过管道输入到一个编码智能体的循环中，然后就能这样构建东西。也许我们投入了大量时间在验证器上。也许你有六个不同的代码审查智能体。但归根结底，这样做，我们仍然在构建四万行的提示词，只是没人想读它们，对吧？这并不夸张。Jeff Dean，对吧？这是真实的，也是创新的。嗯，它是一个锋利的工具，对于某些类型的问题非常有效。如果你不在一个团队中工作，它非常有效。如果你不在关键系统上工作，它也非常有效。但我们大多数人都在关键系统上工作，我们不适合那个框框。所以今天，我想谈谈如何在大型、复杂的代码库中构建适用于有真实客户、真实用户、真实监管义务和服务级别协议以及所有阻止我们直接将四万行黄色提示词投入生产的系统的循环。换句话说，我想谈谈如何为真实世界构建循环。

<details>
<summary>Original English</summary>

**Speaker 8**: I'm co-founder of a company called Human Layer. And I'm here to talk about loops. I think we've all been building loops lately. And I realized recently, I think we're all doing it wrong. Loops are really powerful. Don't get me wrong, but so much of the discourse around them is hype-driven and just really not helpful, right? I think we have this idea just kind of as an industry somehow that we can like pipe a prompt in a loop to a coding agent and that we can build things this way. Maybe we're investing a lot of time in verifiers. Maybe you have six different code review agents. But at the end of the day for doing this, we're still building forty thousand line prompts that just nobody wants to read, right? And this isn't exaggerated. Jeff Dean, right? This is real and it's innovative. Um, it's a sharp tool that works very well for certain types of problems. It works very well if you're not going on a team, it works very well if you're not working on critical systems. But most of us work on critical systems, and we don't fit in that box. So today, I want to talk about how to build loops that work in large, complex code bases for systems that have real customers, real users, real regulatory obligations and service level agreements and everything else that keeps us from shipping yellow forty thousand line prompts straight to production. In other words, I want to talk about how to build loops for the real world.

</details>

**Speaker 8**: 如果你不知道，这篇文章实际上可以追溯到七月。它在过去的一月里病毒式传播，我想那是我们很多人开始构建循环的时候。当然，更近一些，我确定这周你会看到很多这张幻灯片。但Peter Seibel说我们不应该再给编码智能体写提示词了，对吧？我们应该只设计循环，让智能体去提示。OpenAI著名的就是建立在循环之上。他们构建循环，构建代码，循环审查代码，他们发布代码，他们发现并修复代码。甚至还有循环来发现和修复合并代码的循环中的错误，对吧？循环无处不在。这是一个循环之旅。Creative Clock的代码最近也说，这是他作为工程师的全部工作。现在就是写循环来提示Claude，最终我们可能甚至不需要循环，对吧？我们只会有一群智能体设计循环，提示智能体构建循环的代码。然后不知怎么的，我们就在编写生产代码了。我猜，事实上，我们正在构建的循环产生了如此多的代码，我们不可能全部阅读，对吧？所以我们还不如根本不读任何代码，对吧？我们正在投资验证和代码审查，但所有这些代码都是只读的。这是上个月在城里举行的一个会议的论点。所以很多前沿实验室的聪明人都认为这是软件开发的未来。如果你这样做，你的移动速度会快得多，其他所有人都会被甩在后面。现在，这到底效果如何还不清楚。UIT花了六个月才修复Claude代码终端的闪烁问题。OpenAI团队在更短的时间内编写了一个渲染器，而OpenAI的代码以稳定性问题著称。然而，非常清楚的是，这东西真的非常昂贵。如果你不在前沿实验室工作，没有无限的token预算，我们编写的所有这些代码实际上非常昂贵，对吧？MD Pococok最近谈到，在智能体时代，糟糕的代码比以往任何时候都更加昂贵。所以今天，我想谈谈我认为在真实世界中有效的方法，以及我们在Human Layer开始做的事情。需要明确的是，我们仍然在构建循环，对吧？我认为循环非常强大，但我可以设计循环并且仍然阅读代码。事实上，我们可以设计循环，让阅读代码变得更容易，因为循环让代码变得更好。我们可以用循环解决复杂代码库中的难题，并且我们可以增量地构建我们的软件。但要做到这一点，需要一些真正的工程能力。

<details>
<summary>Original English</summary>

**Speaker 8**: If you're not aware, uh, this post actually dates back to July. It went viral this past January, which is when a lot of us, I think, started building loops. And of course, much more recently, I'm sure you're going to see this slide a lot this week. But Peter Seibel said that we shouldn't be prompting coding agents anymore, right? We should just be designing loops that prompt agents. OpenAI notoriously built on loops. They built loops, built code, loops reviewed the code. They logged in, released the code. They found and fixed the code. There's even loops for finding and fixing bugs in the loops that are merging the things, right. It's loops all the way down. It's a loop journey. Also the Creative Clock code recently said that this is his entire job as an engineer. Now it's just writing loops to prompt Claude, and eventually we might not even need loops, right? We're just going to have like swarms of agents designing loops, prompting agents building code for loops. And like I don't know somewhere, we're like writing production code. I assume and in fact, the loops that we're building are producing so much code that we can't possibly read all of it, right? So we might as well just not read any of it, right? We're investing in verification and code review, but all this code is read only. This was the thesis of a conference that was here in town last month. So a lot of smart people at frontier labs think that this is the future of software development. And if you're doing this, you're moving much faster and everybody else is getting left behind. Now, it's not clear how well this works yet. UIT took six months to fix the Claude code terminal flicker. The OpenAI team wrote a renderer in a fraction of that time and OpenAI's code notoriously has stability issues. What is abundantly clear, however, is that this stuff is really expensive. If you don't work at a frontier lab and have an unlimited token budget, all this code that we're writing is actually really expensive, right? MD Pocock talked about this recently: bad code is much more expensive in the age of agents than it has ever been at any point in the past. So today, I want to talk about what I think works in the real world and what we started doing at Human Layer, which to be clear, is still building loops, right? I think loops are super powerful, but I can design loops and still read the code. In fact, we can design loops that make it easier to read the code because the loops are making the code better. We can solve hard problems in complex code bases with loops, and we can build our software for that at three incrementally. But to do this is going to take some real engineering, yeah.

</details>

**Speaker 8**: 那么让我们谈谈控制理论。控制理论是关于我们如何驱动一个动态系统——这应该就是你的代码库——朝着某个期望的、稳定的或最优的状态前进，对吧？你有一个传感器来测量世界的当前状态。你有你的设定点，对吧？世界的期望状态。这两者之间的差异就是测量误差。你有一个控制器，它读取这个测量误差，并将其转化为一个控制信号，关于要对系统应用的增量变化。我们有一个执行器，它将这个变化应用到系统上，而系统在此期间会经历各种扰动。然后我们重新测量，重新计算我们的测量误差，然后回到起点。这听起来非常复杂，而且它确实可以很复杂。我实际上有一个双胞胎兄弟，他是一名航空航天工程师。他们就是这样让战斗机不坠落的。

<details>
<summary>Original English</summary>

**Speaker 8**: So let's talk about control theory. Control theory is all about how we drive a dynamic system, which should be your code base, towards some desired, stable or optimal state, right? You have a sensor that measures the current state of the world. You have your set point, right? The desired state of the world. The difference between these two things is measured error. You have a controller that reads that measured error and turns it into a control signal about an incremental change to be applied to the system. We have an actuator that applies that change to the system, which is undergoing disturbances in the meantime, and then we remeasure, recompute our measured error and we go back to where we started. Now this sounds really complicated, and it can be. I have a twin brother, actually, who's an aerospace engineer. This is how they keep fighter jets from falling out of the sky.

</details>

<!-- chunk 44/54 -->

### 控制循环的实际应用

**Speaker 8**: 啊，HH。

<details>
<summary>Original English</summary>

**Speaker 8**: ah HH.

</details>

**Speaker 8**: 这可能比大多数情况要简单一点。

<details>
<summary>Original English</summary>

**Speaker 8**: it's probably a little bit simple than most.

</details>

**Speaker 8**: 你会想，这个恒温器知道发生了什么吗？它用的是控制回路，PP，PP，给我们在座的欧洲朋友们解释一下？

<details>
<summary>Original English</summary>

**Speaker 8**: you'll think does that know what happen of these a thermst stat uses contcontrol PP for for any our european friends in the audience？

</details>

**Speaker 8**: 这是我们在美国这边有的东西的一部分。

<details>
<summary>Original English</summary>

**Speaker 8**: that's part of something we have here in the states.

</details>

**Speaker 8**: 它叫做空调。

<details>
<summary>Original English</summary>

**Speaker 8**: it's called air conditioning.

</details>

**Speaker 8**: 而且，嗯，我们大多数人可能每天都在使用控制回路，对吧？

<details>
<summary>Original English</summary>

**Speaker 8**: and uh, most of us probably actually use control loops on a daily basis, right？

</details>

**Speaker 8**: Kubernetes 的自动扩缩系统就是建立在控制回路上的，基础设施即代码使用期望状态、当前状态、迭代变更，就像控制回路模式一样。Postgres 的自动清理和复制也是近似于控制回路。

<details>
<summary>Original English</summary>

**Speaker 8**: cuberonetties auto scaling systems are built on control loops, infrastructures code uses a desired state current state iterative changes like control l oppattern postgresses are autovacuum and rex iritrol on both both uare are proproed imate control loops.

</details>

**Speaker 8**: 是的，好的，当我们有一个想要改变的问题系统时，控制回路是理想的。我们可以通过测量来获得关于变更结果的反馈，就像优秀的软件工程师一直被教导要做的那样。控制回路增量地改变系统，而不是试图立即直接达到最终状态，一次性搞定所有事情，冒着把一切搞砸的风险，对吧？它们帮助我们避免过度调整和破坏系统的稳定性，并将风险最小化。

<details>
<summary>Original English</summary>

**Speaker 8**: 是的, 好的, control loops are ideal when we have a system that we want to change a problem. we can measure in a way to get feedback on the result of that change, like good soft engineers have always been thought to do control, loops, changes, system incrementally, instead of just trying to get straight to the end state immediately. all the once and risk blowing everything up, right？ they help us to avoid over stistering and destabilizing the system. and adminimizes risk.

</details>

**Speaker 8**: 所以控制回路与我所说的“盲目回滚”正好相反。它们是我们避免出现这种图表的方式，因为没人想审查这个，对吧？这并不是说所有的回滚循环都是盲目的。最好的回滚实际上是在应用控制理论。我知道 Jeff Hunleis 就在会场的某个地方闲逛。如果你去和他聊聊，他会告诉你同样的事情，对吧？回滚是一种教学工具。我认为我们有些人把它理解得太字面化了。但这本应是我们一直用来做循环的方式，但回滚循环还有另一个问题。它们不是增量的，对吧？它只是一个 bash 循环。

<details>
<summary>Original English</summary>

**Speaker 8**: so control loops will the opposite of what i'm going to call our blind rall flu. they're how we avoid pours that look like this because nobody wants to review this right, which is not to say that all rouf loops are blind loops. the best roops are actually applying control theory. i know jeff hunleis out in the whole somewhere wandering around. if you go talk to him, he's going to tell you the same thing, right？ right？ the routh is, is teaching device. and i think some of us ready it a little too literally. but this is how we should have always been doating loops, but it's other issue e the rouf loops. they're not incremental right？ it's just a bash loop.

</details>

**Speaker 8**: 所以我们必须构建智能控制回路。要做到这一点，我们首先要定义一个设定点，也就是我们代码库在某个属性方面的期望状态。

<details>
<summary>Original English</summary>

**Speaker 8**: so we have to build a gentic control loops. and to do that, we start by defining a set point, which is the desired instate of our code base with respects to some property of it.

</details>

**Speaker 0**: 我们有一个传感器。构建传感器的方法有很多。它可以是严格确定性的，比如你的 ESLint 规则、你的 AST 图、你的包管理器；也可以是非确定性的，比如你可以有一个智能体、一个技能和一堆自然语言规则。所以你也可以有一个管道，比如两者的结合。那么我们如何构建智能控制回路呢？

<details>
<summary>Original English</summary>

**Speaker 0**: and we had a sensor. there's a lot of ways to build a sensor. it can be strictly deterministic. your ES land rules, your AST grap, your packwork or it can be not deterministic. you can have an agent and a skill and a bunch of natural language rules. so you could also just have a pipeline like a combination of the two. so how do we build a gentic and goops？

</details>

**Speaker 0**: 嗯，好了，现在这些都是理论，对吧？实际上来说。而且因为我们使用了智能体，我们可以在系统组件之间稍微模糊界限。比如，ESLint 的 `react` 插件就非常棒。它是一个很好的工具，可以捕获上周所有潜入你代码库的 React 槽点。但它是一个混合型的传感器和控制器。它会告诉你所有 React 代码的问题，并且，顺便说一下，还会告诉你应该修复的前三件事以及如何修复它们。类似地，控制器和执行器实际上可能只是一个单一的智能体，在同一个上下文窗口中决定一个增量变更并应用它。

<details>
<summary>Original English</summary>

**Speaker 0**: 嗯, there we go now ah this is all theory, right？ practically speaking. and because we're using agents, we can bw the lines a little bit between system components. so eight and biys react doctor, for example, is fantastic. it is um it's a great way to catch all of the react slot that lalad snot ck into your code bed last week. but it's a hybrid sensor in controller. it tells you what all the problems with your react code. and also, by the way, what of the top three things you should fix and how how do you fix them？ similarly or controller and actuator might actually just be a single agent deciding on an incremental change to make and then applying it and the same context window.

</details>

**Speaker 0**: 但我想让你稍微关注一下控制器，因为如果没有控制器，或者没有一个调优良好的控制器，我们可能会一次性做出太大的变更，或者完全做出错误的变更。如果你把它放在一个循环里，很快就会陷入麻烦。

<details>
<summary>Original English</summary>

**Speaker 0**: but i want to suyou in on the controller a little bit, because without one or without a well tuned one, we might make too large of a change all the once, or we might might make the wrong change entirely. and if you put that in a loop year in trouble pretty quickly.

</details>

**Speaker 2**: 嗯，对对。

<details>
<summary>Original English</summary>

**Speaker 2**: 嗯, 对对.

</details>

**Speaker 0**: 所以我们可以使用控制回路来根除不良模式并清理我们的代码，但实际上我们可以将它们用于各种各样的事情。对吧？我们可以确保我们的 API 符合其他人的 OpenAPI 规范。我们可以确保我们的 MCP 服务器符合我们当前使用的任何版本的 MCP 规范。我还没检查过。你可以将一个项目从 Python 镜像到 TypeScript，反之亦然。你甚至可以维护你基于 Vite 的 Next.js 分支，使其与上游保持同步。关键问题是：我们能找到可以测量的东西吗？我们能增量地应用变更吗？我们能获得关于这些变更质量的反馈吗？为了说明这一点，我将演示一个控制回路，我们在其中使用人工层作为循环的一部分。

<details>
<summary>Original English</summary>

**Speaker 0**: so we can use control loops to root out bad patterns into clean up our code, but we can actually use them for all sorts of things. right？ we could make sure that our api is complained with someone else as open AP speback. we can make sure that our mcp server is complained with whatever version of the the mcp specification that were currently on. haven't checked. you could mirr a project from pyython and hydescript or vice versa. you could even maintain your veet based slolop fork of next js against the upstream. the key questions are. can we find something we can measure？ can we apply changes incrementally？ and can we get feedback on the quality of those changes to illustrate that i'm going to walk through a control looloop, but we use eternally a human layer for our loop.

</details>

**Speaker 0**: 我们正在增量地将我们的 RKC API 迁移到 Effect。我们已经在一些容易出错的代码中采用了它。我们很喜欢它，所以正在将其推广到代码库的其余部分。如果你以前没见过 Effect 代码，右边的代码只是一个简单的过程，左边是用 Effect 重写的。这个语法真的很奇怪，我们选择了它。我们真的很喜欢它。它不适合所有人。没关系。嗯，我不打算深入讨论 Effect，所以我们会继续推进。点击器不工作了，好吧。

<details>
<summary>Original English</summary>

**Speaker 0**: we are incrementally migrating our RKCAPI to affect. we adopted it for some of our race prone code. we like it so weadopting in across the rest of our code base. if you've never seen effects code before the code on the right, just just kind kind tritrivial proycure, the left ft rewritten effeffect h. this in tax is really weird were cychoes. we really like it. it's not for everybody. that's okay. uh isn't n't talk about effect, so will keep moving wh clickers not work king cool.

</details>

**Speaker 0**: 所以第一步，我们必须构建我们的传感器来查找未迁移的过程。我们可以让智能体来做这件事，或者我们可以使用 graph 或 grap grap。但在 Suwe 中，我们可以使用 AST 图，因为它非常强大。它是你构建循环工具箱中应该拥有的工具。它是语言无关的。它独立于你的 TypeScript 配置或 ESLint 规则，如果你是一个 TypeScript 开发者，你已经看到 Lalaud 用内联注释禁用了这些规则。所以我们可以编写一个简单的规则，根据上面的模式找到未迁移的过程。

<details>
<summary>Original English</summary>

**Speaker 0**: so step one, we have to build our sensor to find unmigrated procedures. we can have an agent do this or we could use grap or grap grap. but in suwewan can use ST grap because it's really powerful. it's a tool to have in your tool box for building loops. it's language agagnostic. it's out of band from your touchtript config or eelluent rules, which if you're a touchgroup developer, you have watched lalaud disled those with inline comments, but so we can just write a simple rule that finds on migrated procedures res based on the pattern above.

</details>

**Speaker 0**: 随着时间的推移，我们甚至可以添加更多规则来描述我们想要摆脱的其他模式，并带有精细的包含/排除路径。如果你有一个多语言单体仓库，就像我们做的那样，它可以用于你能想象到的任何语言。我们只需将其指向我们的代码库，它就会输出一个很长的违规列表。实际上，它会输出大约五十行违规，我们将其过滤到四个，然后确定性地排序。我们为什么一开始要这样做？因为我说过这将是实用的。所以我们将暂时跳出我们的控制范式。因为在我们开始一次一个地增量迁移过程之前，我们需要强制所有新的过程都使用 Effect，对吧？所以我们将对主分支运行一次完整扫描，确定性地对所有违规进行排序，并将其记录在我们的版本控制中。

<details>
<summary>Original English</summary>

**Speaker 0**: and we, over time, we can even layer on more rules that describe other patterns. we want to get rid of with granular, including exclude pads. if you have a multi lingual monorepoo, like we do i'd work for any language you could possibly imagine. and we 're just sandour code bastions and it'll ce ce, a longest of violations. it'll too long. in fact, it'll give you about fifty liys per violations, and we're just going to filter it down to four, and we're going to sort it deterministically. why are we doing that？ at the beginning？ i said this was going to be practical. and so we're going to step outside of our control of paradime for a second. because before we start incrementally migrating procedures wanted a time, we need to enforce that all new procedures are using effect, right？ so we're going to run a full scan once on main, sort all the violations deterministically and tracit in our verversion control.

</details>

**Speaker 0**: 然后在每个新的 PR 上，我们可以查看该分支是否添加了任何未迁移的过程，对吧？所以这就是我们的控制回路，我们的系统正在经历干扰。在这种情况下，嗯，我们的团队正在发布新功能。这就是我们确保他们没有撤销我们循环工作的方法。这并不直接映射到控制回路的某个部分，但我们可以稍微调整一下。它被称为干扰抑制器。

<details>
<summary>Original English</summary>

**Speaker 0**: and then on every new PR, we can see if it the branch added any unmigrated procedures, right？ so this is our control loop, and our system is undergoing disturbances. in this case, uh, our temage shipping clothslog. and this is how we make sure that they're not undoing our loops work. this doesn't matp directly ads to a part of the control loop, but we can kind of like squen edit a little it. it calcalled a disturbance dampener.

</details>

**Speaker 0**: 所以现在我们已经稳定了领先地位，我们可以实际设计我们的控制器了。对于一个简单的控制器，我们可以确定性地从列表中选择第一个违规。你可以使用 bash 和 jq，或者我们可以更聪明一点，使用 AST 图找到最小的未迁移过程，并总是选择最小的来降低风险。

<details>
<summary>Original English</summary>

**Speaker 0**: so now we've stostothe the leeding, we can actually design our controller for a simple controller. we could just deterministically pick the first violation from the list. you can use bash and jq, or we could get a little clever er and use ST gt to find the smallest on migrated procedure and always pick the smallest one to reduce the risk.

</details>

**Speaker 4**: 嗯。

<details>
<summary>Original English</summary>

**Speaker 4**: 嗯.

</details>

**Speaker 0**: 如果我们真的想，我们可以让一个智能体来做决定。我认为你不应该派一个智能体去做确定性代码的工作，但你当然可以。事实上，根据复杂程度，我们可以让智能体获取要迁移的过程并同时执行它，就像我们刚才讨论的那样。但我们还可以让它更强大，对吧？因为我们迁移到 Effect 不仅仅是为了迁移本身，我们这样做是因为它有助于处理错误，并帮助我们更好地检测我们的代码。

<details>
<summary>Original English</summary>

**Speaker 0**: we could have an agent make the decision. if we really want to, i don't think you should ever send an agent to do deterministic codes 's job, but you certainly can, in fact, depending on the complexity, we could have the agent, take the procedure to migrate and just do it at the same time, like we just talked about, but we can make this even more powerful, right？ because we're not just migrating effect for the sake of it, we're doing it because it's helpful for handling errors and for helpful us instrument our code better.

</details>

**Speaker 0**: 所以如果我们想变得非常聪明，我们可以查看我们的遥测数据，找出哪些过程错误最多，或者检测最少，或者在我们的 APM 中存在缺口，对吧？当我们向执行器智能体发送控制信号时，我们不仅可以包含要迁移的过程，还可以包含我们试图通过这次迁移修复的所有相关数据，这样执行器智能体实际上可以使代码变得更好，而不仅仅是进行一对一的迁移。嗯，就是这样。

<details>
<summary>Original English</summary>

**Speaker 0**: and so what we could do, if we want to get really clever is we can look at our telemetry and figure out which procedures have the most errors or or the least instrumentation or has a gap in our APM, right？ and when we send a control signal to our actuator agent, we can include not just the procedure of migrate, but also all the data about the things that were trying to fix with this migration, so that the actuator agent can actually make the code better instead of just doing a one to one migration. um m. there very go.

</details>

**Speaker 0**: 所以下一步是构建我们的执行器。我们的执行器只是一个智能体，加上一个技能，带上你自己的编码智能体。你应该在技能上花很多时间。不是所有东西都应该放在前面。你会希望随着时间的推移，根据在人工层中有效的方法来迭代它。我们喜欢在让智能体自由发挥之前，先手动构建我们所谓的“黄金模式”。这些只是地道的、手写的例子，供智能体遵循，因为它们只是模式复制器，否则你得到的是文档中的内容或智能体从互联网上知道的东西。

<details>
<summary>Original English</summary>

**Speaker 0**: so next is building our actuator. our actuator is just in agent, plus a skale brbring your sel, i coding agent of choice. you should spend a lot of time on the skill. not all that should be at front. you'll want to iterate on it over time based on what works it human layer. we like to build up what we call golden patterns by hand before setting the agent lose. these are just like idetomatic hand written examples for the agent to follow because they're just pattern replicators and otherwise you're getting what's in the dogs or what the agent knows from the internet.

</details>

**Speaker 0**: 所以我们将技能，对对对对，加上我们的控制信号，输入到我们的执行器智能体中。当然，技能应该包含一个响应模板，然后智能体将不断地工作，工作，工作，最终产生一个最终响应。然后我们将确定性地提交、推送，并使用最终消息作为 PR 描述创建一个 PR。

<details>
<summary>Original English</summary>

**Speaker 0**: and so we pipe the skill. 对对对对, plus our control signal and do our actuator agent. and if the skill, of course, should include a response template and the agents going to work and work and work, and it will produce a final response. and then we're going to deterministically commit and push and create APR using the final message as rpr description.

</details>

**Speaker 0**: 现在我们所要做的就是实际运行这个循环，对吧？嗯，我的建议是，在你的 GitHub Actions 或 GitLab CI 或 CircleCI 或任何你正在使用的工具中运行它，因为它可以访问你的代码。它可以访问你的密钥，并且它有很好的调度和调度原语，对吧？

<details>
<summary>Original English</summary>

**Speaker 0**: now all we have to do is actually run the loop, right？ um my recommendis is you get get acactions your your gt lab or your circle ci or whatever else you're using, because it has access to your code. it has access to your secrets, and it has great dispatched in scheduling primitives, right？

</details>

<!-- chunk 45/54 -->

### 将人类纳入循环：低摩擦的反馈与流量控制

**Speaker 0**: 我们不需要为此新建一个集群。所以我们可以编写一个工作流，它运行循环的一次迭代：感知、控制、执行，并创建一个PR。然后我们可以安排它每天运行一次。每天早上，我们走进办公室，就会看到一个小的增量PR。这有风险。当我们第一次尝试时，这实际上非常令人沮丧，我们关掉了循环。因为我们必须不断更新技能，我们必须不断检出分支变更、修改技能、修改代码、提交并推送，我们的循环实际上摩擦非常大，对吧？但有一种更好的方法，对吧？我们可以将人类纳入循环，并以一种非常低摩擦的方式在出错时重新引导它。实现这一点的方法就是创建一个在版本控制中跟踪的反馈文件，就像一个Markdown文件，对吧？我们可以确定性地将其加载到我们的执行器代理的上下文中。每次在运行控制器之后，我们都可以给PR添加一个标签，对吧？每个工作流都需要能够识别它创建的PR，因为会有一堆不同的循环在运行。我们希望一个工作流能够响应其PR上评论的反馈，我们将为每个循环工作流设置一个评论触发器。所以当用户在该PR上留下一个“/iterate”评论时，循环工作流就会拾取它。它会确定性地加载所有的PR上下文、差异评论、评论、描述到代理的上下文中，连同技能一起，并指示代理修复代码，同时也要更新那个反馈文件。看起来就像这样。这样做的好处是，现在那个带有指令的反馈文件，在版本控制中备份，你可以看到它随时间的变化。如果需要，你可以回滚它。

<details>
<summary>Original English</summary>

**Speaker 0**: we don't need a new cluster for this. so we can write a workflow that runs a single iteration of the loop sense, control actuate and creates a PR. and then we can schedule this to run once a day. and every morning, we walk into the office to a small incremental PR. that's a risk. and when we first tried this, this was actually really frustrating and we turned the loop off. and um because we had to constantly update the skill, we had to constantly check out the branch, changed the skill, changed the code, commit and push, and our loop is actually really high friction, right? but there's a better way to do this, right, where we can put a human on the loop in a really low friction way to resteer it when it goes wrong. and the way to do this is to just create a feedback file that's tracked in version control, just as a markdown file, right? we can deterministically load it into our actuator agent's context. every time that it runs after we run the controller, then we can add a label to the PR, right? each workflow needs to be able to identify PRs that it created since there'll be a bunch of different loops running. and we want one workflow to respond to feedback from comments on their PRs, and we're going to have a comment trigger to each loop workflow. so when a user leaves a slash iterate comment on the PR, the loop workflow is going to pick that up. it's going to deterministically load all of the PR context, the diff comments, the comments, the description into the agent's context, along with the skill, and it's going to instruct the agent to fix the code, but also to update that feedback file right looks kind of like this. and the benefit of doing this way is that now that feedback file with instructions, it's backing in your version control, you can see how you've changed it over time. you can revert it if you need to.

</details>

**Speaker 0**: 嗯，所以我们要做的下一件事是流量控制，因为我们做这件事时遇到的另一个问题是，如果我们在客户现场待了一周，或者我们在旅行，或者花了六天时间做幻灯片而不是写代码，呃，我们所有循环产生的PR就会堆积起来，产生重复的、冲突的工作，而我们没有时间处理。而且，循环的工作很重要，但也没那么重要。所以现在我们有了所有这些垃圾需要处理。这并不重要。所以这其实是一个很容易解决的问题，因为每个循环及其工作流都有一个标签。它们在工作流首次运行时被附加到PR上。在我们检出代码、安装依赖项、运行感知、控制、执行步骤之前，我们可以检查一下我们创建的最后一个PR，或者任何带有该循环标签的PR是否处于打开状态。如果是，我们就直接关闭，对吧？因为这意味着自上次循环分支以来，还没有人类审查过这个循环的代码，对吧？没有人审查过上一次的输出。所以没有理由为人类审查堆积更多的工作。对对对，这样，每个循环在任何时候最多只有一个打开的PR。没有堆积，没有重复，希望也没有冲突。

<details>
<summary>Original English</summary>

**Speaker 0**: um, so the next thing we're going to do is add flow control because the other problem that we had when we did this was that if we were at a customer site for a week or if we were traveling or spent six days working on slides instead of writing code, uh, the PRs from all our loops, they just stack up, duplicate work that conflict, and we couldn't get around to doing it. and like the loops work is important, but it's not that important. and so now we just had all this like junk, we had to deal with it. it wasn't important. so this is actually really easy problem to fix, because each loop and its workflow has a label. they get attached to PRs when the workflow first runs. before we check out the code and install the dependencies and run sense, control, actuate steps, we can just check and see if the last PR that we created or any PR with the loops label on it is open. and if so, we just shut down right, because this means that the last time that a human reviewed the code from this loop was before the loop branch, right? no human reviewed the last output. so there's no reason to stack up even more work for humans to review. right, right, right, this way, we have exactly one PR and most open per loop at a time. no stacking, no duplication, hopefully no conflicts.

</details>

**Speaker 0**: 当然，一旦我们对循环有信心了，我们就会想加快它的速度，对吧？我有一百五十个RPC过程需要迁移。如果我一次只做一个，那将需要六个月，这比我愿意等待的时间长得多。幸运的是，有很多方法可以提高我们PR的速度。我们可以让我们的控制器一次挑选三个或五个过程来迁移，而不是一个。有很多方法可以迁移。我们可以让我们的控制器挑选三个或五个，然后在单独的实现阶段处理每一个，这样会更便宜、更可靠，因为每次迁移都有自己的上下文窗口。或者我们可以直接运行工作流四次，把四个PR分别交给团队里的四个人。所以，让我们把所有这些整合起来。我们构建了一个控制循环，可以增量地改进我们的代码，并且我们实际上是在审查代码。它有自适应的流量控制，所以我们不会产生一堆没人想审查的垃圾工作。我们可以以一种超低摩擦的方式即时重新引导它。如果你想自己尝试一下，嗯，我们构建了一个技能，请试试看。我的推特账号在底部，请分享它。如果你对此感到兴奋，我们正在旧金山招聘。如果你正在处理关键任务系统，并想弄清楚如何从AI中获得更多价值，我们很乐意聊聊。非常感谢。

<details>
<summary>Original English</summary>

**Speaker 0**: and of course, once we're feeling confident in the loop, we're going to want to speed it up, right? i have one hundred and fifty RPC procedures to migrate. if i do one at a time, it's going to take six months, which is way longer than i want to wait. fortunately, there's a lot of ways to pick up the velocity of our PRs. we could have our controller pick procedures to migrate instead of one. there's a lot of ways to migrate. we could have our controller pick three or five, and then do each of those in a separate implementation phase will be both cheaper and more reliable, since each migration gets its own context window. or we could just run the workflow four times and give one PR to each of four people on the team. so let's put it all together. we build a control loop that improves our code incrementally and we're actually reviewing the code. it has adaptive flow control. so we're not creating a bunch of fluff or a bunch of work that nobody wants to review. and we can resteer it on the fly in a super low friction way. if you want to try this yourself, um we built a skill, please try it out. my twitter handle is down there on the bottom, please share it. i would love to see what you build. and if you get excited by this, a human layer, we're hiring here in san francisco. and if you're working on mission critical systems and want to figure out how to get more out of the AI, we'd love to chat. thank you so much.

</details>

### 从实现到规范：AI时代的平台演进

**Speaker 8**: 嗯，在2026年，编码代理将悄然淘汰第一个软件平台，不是因为它不好，而仅仅是因为这个平台不再必要。我是Dominic Tunnel，我是Resonate的创始人兼CEO。Resonate是一个全球执行平台，其核心技术价值观是极简主义和简单性，这些特性将在本次演讲中扮演核心角色。在Resonate，我们有一个信念：软件工程正在被颠覆。通用实现将越来越多地被按需生成的定制实现所取代，不是作为一个新的库、新的框架或新的平台，而是作为现有基础设施的一个极简扩展。如果这个理论成立，那么工具将向上移动到规范层面。与其重用通用实现，我们将重用规范，并从中推导出一个定制实现。事实上，我们可以构建许多为现有基础设施量身定制的实现。我们只需要在这一点上询问代理。提示即平台。Resonate是一个全球执行平台。我们有Reasonate Java的实现，我们有Reasonate SDK for TypeScript、Python、Rust、Go和Java的实现。所以我们必须问，如果实现变得可生成，这个新现实对我们意味着什么？我们的价值在哪里？我们的答案是，我们的价值从实现转移到了规范。这改变了我们思考推理的方式。产品不再是实现。产品是规范，是协议。从那个协议出发，我们希望推导出多个服务器实现。一个是通用的Resonate服务器，我们的参考实现。其他的是与基础设施合作伙伴一起为客户和合作伙伴构建的实现。这意味着在他们现有的基础设施之上实现可靠的执行，并且附加依赖最小。所以问题不再是“我们能构建一个服务器吗？”。问题是，“我们能从同一个规范中反复综合出可信的服务器吗？”如果可以，怎么做？当我们谈论代理工程时，我们把所有注意力都集中在验证上。我们如何知道结果是正确的？但今天，我想把重点放在规范上。更重要的是，代理如何参与系统的规范制定，而不仅仅是构建或验证它？最近，我们与多个基础设施提供商合作，将可靠的执行无缝地带到他们的技术栈中。其中之一是Syadia，NATS背后的公司，NATS是一个为构建现代分布式系统设计的开源消息系统。在本次演讲的剩余部分，我们将使用Resonate on NATS来探索我们的代理工程实践。我们如何从规范走向实现？首先，我们需要统一我们的心智模型。这张图是代理编码的常见视图。有一个代理，有一个规范，然后有一个实现。对于许多应用来说，这已经足够了。但对于我们正在尝试做的事情来说，这还不够，因为我们不是要从一个规范生成一个实现。我们是要从规范生成多个针对特定目标的实现。所以规范绝不能考虑实现的任何方面。规范绝不能假设具体的数据库模式或具体的索引。这个规范甚至不能假设一个带有表和事务的关系型数据库。它绝不能假设一个键值存储。它绝不能假设弱一致性。它绝不能假设强一致性。规范必须是抽象的，只有实现必须是具体的。所以我们要求代理遵循抽象规范，并具体地生成具体实现。起初，我们要求代理在FOS之上用Rust构建一个Resonate，但代理失败了。抽象规范和具体实现之间的差距太大了。代理生成了一个在快乐路径上工作的系统。它通过了基本测试，但它不正确。它在并发性上出错了。它在进程失败时出错了。它在网络故障时出错了。这个实现更接近于一个原型，而不是一个生产系统。所以我们修改了流程。我们没有要求代理直接从抽象规范跳到具体实现，而是插入了一个中间工件：具体规范。这个具体规范是与代理交互式地推导出来的。

<details>
<summary>Original English</summary>

**Speaker 8**: um, in twenty twenty six, coding agents will quietly retire the first software platform, not because it's bad simply because the platform is unnecessary. i am dominic tunnel. i am founder and ceo of resonate. resonate is a global execution platform built with minimalism and simplicity as its core technical values, and these properties will play a central role in this talk. at resonate, we have a belief that software engineering is being disrupted. general purpose implementations will increasingly be replaced by bespoke implementations, generated on demand, not as a new library, a new framework or new platform. but as a minimal extension of the infrastructure that is already in place. if this theory holds, tools will move up the stack. instead of reusing a general purpose implementation, we will reuse a specification, and we will derive a bespoke implementation from it. in fact, we can build many bespoke implementations tailor made for the infrastructure that is already in place. we just have to ask the agent at this point. the prompt is a platform. resonate is a global execution platform. we have an implementation of the resonate java. we have implementations of the resonate sdk for typescript, python, rust, go and java. so we have to ask, what does this new reality mean for us if implementations become generatable? where does our value live? and our answer, our value moves from implementation to specification. now this changes how we think about reasoning. the product is no longer an implementation. the product is specification, the protocol. and from that protocol, we want to derive multiple server implementations. one is a general purpose, resonate server. our reference implementation. others are implementations built with infrastructure partners for customers and partners. this means durable execution right on top of their existing infrastructure with minimal additional dependencies. so the question is no longer can we build a server? the question is, can we repeatedly synthesize trusted servers from the same specification? and if so, how? when we talk about agentic engineering, we focus all of our attention on verification. how do we know the result is correct? but today, i want to focus on the specification instead. and more importantly, how can agents participate in specifying the system, not just building or verifying it? now recently we partnered with multiple infrastructure providers to bring durable execution natively to their technology stack. one of them is syadia, the company behind nats, an open source messaging system designed for building modern distributed systems. for the rest of this presentation, we will use resonate on nats to explore our agentic engineering practices. how do we go from specification to implementation? first, we need to level set our mental model. this picture is a common view of agent coding. there's an agent, there's a specification, and then there's an implementation. and for many applications that is enough, but it is not enough for what we are trying to do because we are not trying to generate one implementation from a specification. we are trying to generate multiple target specific implementations from the specification. so the specification must not take any aspect of an implementation into account. the specification must not assume a concrete database schema or concrete indexes. this specification must not even assume a relational database with tables and transactions at all. it must not assume a key value store. it must not assume weak consistency. it must not assume strong consistency. the specification must be abstract, only the implementation must be concrete. so we ask the agent to follow the abstract specification and generate concrete implementation specifically. at first, we asked the agent to build a resonate for us in rust on top of foscers, and the agent failed. the gap between the abstract specification and the concrete implementation was too large. the agent generated a system that worked on the happy path. it passed the basic tests, but it was not correct. it broke on the concurrency. it broke on the process failure. it broke on the network failure. the implementation was closer to a prototype, but not a production system. so we amended the process. instead of asking the agent to jump directly from abstract spec to concrete implementation, we inserted an intermediary artifact, the concrete specification. that concrete specification was derived interactively with the agent.

</details>

<!-- chunk 46/54 -->

### 从人工驱动到智能体驱动的设计转变

**Speaker 8**: 但人类是后端的核心驱动力，这意味着要做出针对目标的特定决策，明确数据，设计模式、索引、SKL 清理、以及事务边界。这些决策都被记录下来，智能体确实能够实现一个生产系统。所以这行得通，但也暴露了局限性。智能体帮助我们构建了系统，但智能体并没有帮助我们设计系统。如果规范是一个可复用的产品，那这还不够。下一步显而易见：智能体必须向上游移动。但如何做到呢？当我们开始大规模构建 Resonate 时，我们改变了问题。我们不再问“智能体能构建生产系统吗？”，而是问“智能体需要什么才能先设计系统，再构建系统？”于是，我们让智能体访问一个确定性的模拟环境，并给了它一个不同的任务：不要构建生产系统，而是构建一个模拟实现。模拟实现不是产品，它是可执行的设计，其目的是在部分有序、部分失败的情况下发现正确的算法。一旦这些算法在模拟中被发现、测试和验证，我们让智能体编写具体的规范，然后才让智能体编写生产实现。所以这个过程变成了：抽象规范、模拟实现、具体规范、然后具体实现。这是智能体向上游移动的关键点。人类仍然参与设计过程，但现在智能体是驱动者。有两个要素使这成为可能：极简主义和简单性。不幸的是，极简主义和简单性不是起点，而是终点。我们花了多年时间让协议变得更小、更简单。每次遇到问题，我们都会问：我们能去掉什么？什么抽象可以被移除？什么属性可以被删除？什么关系可以被打破？结果是一个非常小的协议集，围绕两个对象：一个全局 Promise 和一个全局 Task。简单性很重要，因为即使是简单的并发分布式协议也有复杂的状态行为空间。因此，即使在几个简单原语之上实现简单的协议也很困难。

<details>
<summary>Original English</summary>

**Speaker 8**: but the human was the main driver for postcores that meant making target specific decisions, explicit the data, schema the indices, the SKL clearies, the tracacboundaries one. so those decisions were written down, the agcient was indeed able to implemena production system. so this worked, but it also revealed the limitations. the agent helped us build the system, but the agent did not help us design the system. and if the specification is a reusable product, then that's not enough. now the next step is obvious. agents have to move up stream, but how when we started building resonate on that sale, we changed question. we did not ask can the agent built the production system? instead, we ask what does the agent need in order to design the system first and build the system. second, so we gave the agent access to a deterministic simulation environment, and we gave it a different task. do not build the production system, build a simulated implementation. the simulated implementation is not the product, it is executable design its purposes to discover the correct algorithm under partial order under partial failure. and once these algorithm are discovered, tested and verified in simulation, then we ask the agent to write the concrete specification, and only then to be ask the agent to write the production implementation. so the process becomes abstract specification, simulation implementation, concrete specification and then concrete implementation. this is a point where the agent moves upstream humans are still involved in the design process. but now the agent is a driver, two ingredients make this possible minimualism and simplicity. unfortunately, minimualism and simplicity are not the starting point. they are the finish line wespspbeen years years, making proprococol smaller and simpler. every time we ran into a problem. we ask, what can we take away, what abstraction can be race, what property can be remove, what relationship can be break. the result is a very small protocol sent that around two objects, a global promise and a global task that simplicity matters, because even simple concurrent disssibuity protocol have a complex state ment behavior space. so another terms implementing even simple protocols on top of a few simple primiters is tough.

</details>

### 以 Nuts 为例：模拟环境的关键作用

**Speaker 8**: 让我们用 Nuts 来具体说明。Nuts 提供了一小组原语：我们可以构建在队列、键值存储和延迟或定时消息之上。这些不是推理概念，而是目标平台的概念。所以设计问题变成了：如何仅使用这些原语来表达可靠性协议？让我们聚焦于键值存储。键值存储是版本化的。我们创建一个键，值为 foo，然后更新为 bar，再更新为 baz。所以最新值是版本 2 的 baz。大多数时候，当我们读取这个键时，我们得到的就是一个新鲜读取。如果所有读取都是新鲜的，设计会很简单。但有时读取是过时的。这里，最新值仍然是版本 2 的 baz，但读取返回了版本 0 的 foo。这不是损坏，也不是键值存储的 bug。这是在目标平台一致性模型下的有效读取。这很重要，因为我们的实现不能只在目标行为方便时才正确，实现必须在目标行为合法时也正确。所以模拟环境必须暴露这种确切的行为：新鲜读取、过时读取，以及告诉我们处于哪个世界的版本信息。不幸的是，我们无法通过读取本身知道读取是过时的。我们稍后会在尝试写入时发现。我们读取了版本 0，所以尝试更新版本 0，但键已经向前推进了。那一刻，目标告诉我们：你看到的世界不是当前的世界。在允许偶尔过时读取的并发模型之上构建始终正确的应用程序并不简单，对人类不简单，对智能体也不简单。那么，我们如何为智能体的成功创造条件？我们的智能体需要什么工具来完成任务，而不是一败涂地？智能体依赖反馈而茁壮成长——即时、明确的反馈。不仅仅是显示“这错了”的反馈，而是显示“为什么错”和“怎么错”的反馈：返回了什么状态值？触发了什么逻辑？哪个写入失败了？哪个不变量因此被破坏了？所以我们在 Python 中构建了一个确定性模拟测试环境。在那个环境中，我们模拟了 Nuts 中我们依赖的部分 I/O。例如，模拟的键值存储。它为每个键保留完整的版本历史。在 Get 时，模拟存储有时返回最新版本，但有时由确定性随机生成器控制，返回一个旧版本。在 Update 时，存储强制执行乐观并发控制：只有当你读取的版本仍然是最新版本时，写入才会成功，否则会抛出异常。这给了智能体一个行为方式与真实存储相同的存储，在元组正确性方面。但与真实目标不同，模拟是确定性的、可重复的、可检查的。所以当智能体编写了错误的算法时，我们可以重现导致错误的执行，智能体可以针对那个轨迹修复算法。但确定性模拟做的不仅仅是注入过时读取。它让我们暴露真实平台隐藏的事实。我们称之为生产中的“禁果”。当你从键值存储读取时，你只得到你观察到的版本的值。你无法知道那次读取是新鲜的还是过时的。你无法看到最新值。你不应该得到这些信息，因为真实代码不能依赖它。但在模拟中，我们可以记录每次 Get 并发出一个追踪事件。如果读取是新鲜的，追踪说这是新鲜的。如果读取是过时的，追踪说这是过时的，这是你得到的值，这是最新值是什么。这些信息对算法来说是禁止的，但对智能体来说却非常有用。它让我们以智能体可以立即采取行动的方式探索失败。

<details>
<summary>Original English</summary>

**Speaker 8**: let's make this concrete with nuts. nuts gives us a small set of primitives. we can build on quees, a key value store and delayed or scheduled messages. these are not reasoning concepts. these are the concept of the target platform. so the design question becomes how can we express the reasontly protocol using only these primatters? let's focus on the key value store. the key value store is versened. we create a key with value fool, then be updated to bar, then be upted it bbus. so the latest value is pass at version, too. most of the time when we read the key, that is exactly what we get a fresh read. and if all reads were fresh, the design will be straight forward, but sometimes the readed is stale here. lalatest value still bbus adversion too, but the read returns full at version zero that is not corruption. that is not a bug in the key value store. that is a valid read under the consistency model of the target platform. and that matters because our implementation cannot be correct. only when the target behaves conveniently, the implementation has to be correct when the target behaves legally. so the simulation environment has to expose exactly this kind of behavior, fresh reads, stale reads. and the version information that tells us which word we are in. unfortunately, we do not know the read was stale simply by reading. we will find out later when we try to write here to we read version zero. so we try to update version zero, but the key has already moved on the right fares. that is the moment the targetels us. the word you saw is not the current word building, always correct applications on top of a concurrency model that allows occasional stale readis, not simple, not for humans, not for agents. so how to we set up our agent for success, what tools does our agent need to acist task instead of falling flat on its face. agents thrive on feedback, immediate unambiguous feedback, not just feedback that shows this man wrong feedback that shows why and how this man wrong, what state value was returned, what logic was triggered, what ride failed and which invarian broke because of that. so we built a determiniisc simulation testing environment in python. and inside that environment, we simulated the parts of nuts. io. we depend on here, for example, is the simulated key value store. it keeps a full version history for every key on get the simulated storard, sometimes return the latest version, but sometimes controlled by the deterministic random generator. the store returns on lot diversion on update the store and forces optimistic concurrency the right only succeeds. if the version you read is still the latest merger, otherwise it raises. this gives the agent a store that behaves like the real store in the ways of metaphor correctness. but unlike the real target, the simulation 's deterministic, it's repeatable and it's inspectable. so when the agent writes the wrong algorithm, we can reproduce the exexcution that broken and the agent can repair the algorithm against that trace. but deterministic simulation does more than just inject state rates. it lets us expose facts. the real platform heights. we call this the forbidden fruit in production. when you read from the key value store, you only get the value in the version you observed. you do not get to know whether that read was fresh or stale. you do not to see the latest value. you, you misand you you shouldn't get that information, because real code cannot depend on it, but in simulation, we can recorded here every get in mits a tray event. if the read is fresh, the tray says this was fresh. if the read is still, the trace says, this was still this is what you got. and this is what the latest value was, that information is forbidden to the algorithm, but it is incredibly useful to the agent. it lets us explore failures in terms. the agent can act on now.

</details>

### 追踪事件：揭示因果关系的钥匙

**Speaker 8**: 这就是一个追踪事件的样子。生产代码只接收结果。它看到 Promise 是 pending 状态。这就是真实平台告诉它的一切。但模拟还记录了读取的类型。这次读取是一次过时读取，并且记录了算法看不到的最新值。最新值表明同一个 Promise 已经 settled。这个差异正是智能体在调试分布式算法时需要的：不仅仅是“不变量失败了”，而是“不变量失败是因为算法基于一个过时的世界视图做出了决策”。再次强调，算法不允许依赖这些信息，但智能体被允许使用它来解释为什么它设计的算法是错误的。因果关系变得可见。智能体不仅知道系统错了，它知道系统为什么错了。通过这种方法，智能体能够弥合差距。首先，智能体在确定性模拟器中启动了一个概念验证，通过模糊测试验证。从概念验证中，智能体推导出了具体的规范。那时我们已经知道算法是正确的。和之前一样，从具体规范中，智能体推导出了实现。确定性模拟让智能体能够参与设计，而不仅仅是实现。人类仍然在设计过程中。但这一次，智能体是驱动者。从一个单一的抽象规范开始，智能体通过模拟、具体规范到具体实现，设计和构建了平台。提示是一个平台，规范是一个产品。非常感谢您的观看。如果您有任何问题，请随时联系我们。您会在 Resonate 的代码中找到我。

<details>
<summary>Original English</summary>

**Speaker 8**: this is what a tracevent looks like. the production code only receives the result. it sees the promise was pending. this is all the real platform bod tallas, but the simulation also records the type of the read. this read was a stil read, and it records the latest value that was hidden from the algorithm. the latest value says the same promise is already settled. that difference is exactly the kind of facct and agent needs when it's debugging, a distributed algorithm, not just the invion field, but the invion failed because alrithon made a decision from a stale view of the word. again, the algorithm is not allowed to depend on this information, but the agent is allowed to use it to explain why the algoriththm it designed was wrong, cause and effect becomes visible. the agent does not just learn that the system is wrong. it learns why the system is wrong. and with this approach, the agent was able to close the gap. first, the agent boot, a proof of concept in the deterministic simulator verified by foce testing from the proof of concept, the agent derived the concrete specification. when we already knew that irorithm was correct. and like before from the concrete specification, the agent derived an implementation deterministic simulation, lets agents participate in the design, not just in the implementation. humans are still in the design process. but this time, the agent is a driver from a single abstract specification, the agent designed and builook the platform via simulation to concrete specification to concrete implementation. the prompt is a platform, and the specification is a product. thank you very much for watching. if you have any questions, please don't hesitate to reach out. you will find me and resonates this code.

</details>

### 新演讲者：智能体与检索边界

**Speaker 10**: 嘿，大家好。我是 Swam，我是 Stulid Search 的前端工程师。今天我的演讲主题是“在检索边界使用信号”。那么，什么是智能体？本质上，我认为智能体是检索领域的一个原因，特别是如何让信号跨越检索边界，以及如何让你的智能体基本上变得自信。是的，没错。那么，我们开始吧。什么不是智能体？智能体是一个具有推理、行动、与环境交互、检索记忆以完成任务的能力的实体。它缺少的一个主要部分是学习。它也应该从什么有效、什么无效中学习。假设我必须解释什么是智能体，我可以通过 React 智能体来解释。所以，如果我要解释智能体做什么，我会用 React 智能体来解释。基本上，智能体在一个循环中执行……

<details>
<summary>Original English</summary>

**Speaker 10**: hey, everyright. i'm swim. i'm i'm see you in good fronend of stulid search. and today, my talk me ter use a signals die at retrieal boundary. so look into uh what are agents? essentially, my agent feels what is uh cause of fiels in retrieval, particularly and how to make actually signals ross, the trivial boundary and how to make your agent basically unconfair. 是的没的。 so, uh plus started ted. what is n't an agent? and agent is an analym that has agency to reason involve those. uh interact with that, dual would retrieve uh the memory to complete. the ask, ask major or uopa is missing is a learning. it should also learn from what to work and what it didn't work. suppose um if i have to uh explain, what is asient did i can explain through occasient. so if i have to explain uh, what agent does, i had explained with react agent. so basically uit from the agent uuh execute it in a look,

</details>

<!-- chunk 47/54 -->

### 软件工厂的失败与优化误区

**Speaker 10**: 嗯，坚持进行重复研究，然后在公司做这些事的时候暂停一下。

<details>
<summary>Original English</summary>

**Speaker 10**: uh cling to a retrial research and then pause when the the do's this company.

</details>

**Speaker 10**: 这是非常基础的 React 架构。

<details>
<summary>Original English</summary>

**Speaker 10**: this is very basic react architecture.

</details>

**Speaker 10**: 缺少的一点是如何让智能体了解结果。

<details>
<summary>Original English</summary>

**Speaker 10**: one thing that is missing is how to make agent the noledge on the outcome.

</details>

**Speaker 10**: 所以亚洲人一直在做同样的任务，拿到了报告，说百分之八十五的空中故障发生在 chin，咨询公司和麦肯锡的二十份航班延误报告。

<details>
<summary>Original English</summary>

**Speaker 10**: so asian keeps feeling at the same task gotten the report, said eighty five percent of air takes failing chin, concerts and mkenzees to entwenty deflight report.

</details>

**Speaker 10**: 问题在于，大多数时候，实际情况是静态的，百分之七十三是因为来自周围的交通和连接问题。

<details>
<summary>Original English</summary>

**Speaker 10**: the problem came out to be most of the time is that the tually was static, seventy three percent because of tratrict and conacst from from from around ving.

</details>

**Speaker 10**: 为了错误的事情。

<details>
<summary>Original English</summary>

**Speaker 10**: for the wrong thing h.

</details>

**Speaker 10**: 我们一直在为错误的事情进行优化。

<details>
<summary>Original English</summary>

**Speaker 10**: we have been optimisze for the wrong thing.

</details>

**Speaker 10**: 你在付钱，而不是为了你的优化。

<details>
<summary>Original English</summary>

**Speaker 10**: you are paying and not for your potimisong.

</details>

**Speaker 10**: 我们一直在为错误的事情进行优化。

<details>
<summary>Original English</summary>

**Speaker 10**: and we have been optimising for the wrong thing.

</details>

**Speaker 6**: 嗯，没有啦啦啦啦，我是你，嗯，嗯嗯，没有，我会你。

<details>
<summary>Original English</summary>

**Speaker 6**: the 嗯, 没有啦啦啦啦 the 我是你 the 嗯, 嗯嗯, 没有 the 我会你.

</details>

### 下午主题演讲开场

**Speaker 11**: 女士们先生们，请鼓掌欢迎我们的回场嘉宾，来自 Keycard Alii 的技术职员成员。

<details>
<summary>Original English</summary>

**Speaker 11**: ladies and gentlemen, please put your hands together and welcome back our mc member of the technical staff at keycard alii.

</details>

**Speaker 6**: 如何，嗯。

<details>
<summary>Original English</summary>

**Speaker 6**: how 嗯.

</details>

**Speaker 12**: 欢迎回到我们的下午主题演讲。我希望你们今天到目前为止都过得非常棒。我知道我肯定是的。我很享受探索我们十八个不同分论坛中的所有不同演讲。我很享受探索展览区，我也很享受与你们所有人——工程师们——交流和合作。这是一个非常特别的地方，我们可以在同一个空间里聚集，进行真正有趣的对话，推动 snax 的边界。让 AI 安全工程师和任何工程师进入同一个房间，理解我们如何能够解锁……因为安全问题而受阻的交付，从而更快地交付并提高我们的工程效率，这是一件非常强大的事情。让构建模型的人和正在使用模型的人坐在同一个房间里，也是非常令人兴奋的。这样我们就能理解什么真正有效，并帮助我们找到 snax。我对今天剩下的内容感到非常兴奋。但我想花一点时间感谢我们了不起的赞助商，是他们让这一切成为可能。让我们为我们的主赞助商微软鼓掌。我还想感谢我们的实验室和白金赞助商，以及我们的金牌赞助商，也为他们鼓掌。最后但同样重要的是，我想感谢我们的银牌和铜牌赞助商。

<details>
<summary>Original English</summary>

**Speaker 12**: welcome back to our afternoon. keynotes, i hope you all had an amazing day so far. i know i certainly have. i've enjoyed exploring the different talks across all of our different eighteen different tracks. i've enjoyed exploring the exposession, and i'm enjoyed talking and at working with all of you, a engineers, a really special place where we can all come together in one space and have really interesting conversations that pushed the boundaries of what snacks. it's a really powerful thing to get AI security engineers. any engineers into the same room and understand how we can of unlock um shipping because of security issues, ship faster and increase our engineering velocity. it's also really exciting to get the same people that are building the models in the same room with the people that are using them. so we can understand what actually works and help us to find what snacks. i'm super excited for the rest of our content today. but i want to take a moment to think our amazing sponsors that make all of this possible. let's take up run of applause for our presenting sponsor microsoft. i also want to recognize our lab and platnum sponsors also our gold sponsors, rn of a pause for them as well. and last, but not least, i want to thank our silver and brown sponsors,

</details>

**Speaker 4**: 这些赞助商数量众多，而且举办这样的活动需要很多人的努力。

<details>
<summary>Original English</summary>

**Speaker 4**: which there are newable amount of those as well as eararling takes a lot of people to put on this event.

</details>

**Speaker 12**: 所以非常感谢所有的赞助商，也感谢所有来到这里、让这个社区成为可能的人们。嗯，我知道我们今天听到了很多关于软件工厂的内容，它们非常有趣。我们所有人都对它们能带来的生产力提升和潜力感到非常兴奋。但在实践中，它们可能比理论上更困难。我非常兴奋，因为我们下一轮的演讲者将帮助我们理解循环工程的实践，并帮助我们理解如何创建真正有效的、不产生垃圾的软件工厂。我非常兴奋地介绍我们下午主题演讲环节的第一位演讲者。嗯，这位演讲者是一位经验丰富的 AI 演讲者。他告诉我这是他第四次在 AI Engineer 演讲，这太不可思议了。嗯，这位演讲者以发动“反垃圾战争”而闻名。他以提出“上下文工程”这个术语而闻名，他以创建我们熟知并喜爱的“研究-计划-实施”框架而闻名。很荣幸能介绍 Jack Fororthees，联合创始人兼 CEO。他将要谈论“工程还不够：为什么软件工厂会失败？”请大家欢迎 Deck 上台。

<details>
<summary>Original English</summary>

**Speaker 12**: and so super thankful to all over their responsors thanful for all of the people that are here that make this community possible. um i know weve heard a lot about offacfactories today, and they're super interesting weall. all very, very alert by the promise of what the productivity and unlock that they can deliver. but in practice, they could be more difficult than in theory, and i'm really excited because our next round of speakers are going help us understand the practices for a loop engineering and hell, ll us understand how we can create software factories that actually work and don't produce slab. i'm super excited to introduced our very first speaker of the afternoon keynote sessions. um this speaker is a seasoned ai speaker. he to told me is his fourth time you spopoken at a engineer, which is incredible. um this speaker is known for raaging. the war on slop. he is known for calling the the term context engineering, and he is known for creating the research to plan implement framework that we know in love. it's my honor to introduce jackfororthees co founder and ceo. he were layer to talk about harness engineering is not enough. why software factories fail? please welcome to the stage deck.

</details>

**Speaker 6**: 我开了你，为了非常多的钱，正在做，伙计们，为今天所有伟大的演讲者站起来。

<details>
<summary>Original English</summary>

**Speaker 6**: 我开了你 for very money are was doing guys giit up for all the great speakers today.

</details>

### 工程不够：为什么软件工厂会失败

**Speaker 13**: 到目前为止，好的，这是最难的。工程是不够的，以及为什么软件工厂会失败，我们将会点击。

<details>
<summary>Original English</summary>

**Speaker 13**: so far, all right, this is hardest. engineering is not enough and why software factories fail and we're going to click.

</details>

**Speaker 6**: 也许，嗯，哦。

<details>
<summary>Original English</summary>

**Speaker 6**: maybe um oh.

</details>

**Speaker 13**: 幻灯片太多了，等一下，伙计们。好的。所以我们都在竞相将 AI 编码投入生产。关于循环工程已经有很多讨论，我们可能应该写更多的循环。是的，我猜我们现在都在做循环？Strong GM 建立了一个无人值守的软件工厂，甚至没有人编写代码。主流叙事是我们应该投入更多的 token。你是瓶颈。模型足够好，代码是免费的，只管交付更多东西。但与此同时，我们开始看到裂痕。我们在 AI Engineer Europe 的朋友开始看到速度放缓，因为那些本不应该因为编码智能体而出现故障的公司，却因为编码智能体而出现了故障。也许代码库比以往任何时候都崩溃得更快。我们在 far 的朋友甚至做了一份报告，自从一月份我们开始使用所有这些 AI 编码工具以来，二月份，嗯，代码审查请求的质量下降了，我们有更多的评论、更长的评论，以及大量未经任何审查就被合并的 PR，事件数量大幅上升。每个开发者的 bug 数量大幅上升。很多人会告诉你，你使用的方式不对。这是你没能成功的唯一原因。好吧，也许你是，但这不是重点。我已经就如何在使用 AI 时做得更好发表了很多演讲，在 YouTube 上可能有百万的观看量，但这一点在不同的演讲中都有体现。基本的事情是，作为工程师，我们被告知，如果 token 最大化不起作用，那是技能问题，你只需要花更多的 token，嗯，只要足够多地阅读代码，足够多的工程。如果我们也许加入一些神奇的词汇、对抗性审查、足够的 PR 机器人，我们就能两全其美，实现一百倍的更快速度和高质量。没有人需要做我们都讨厌的那件事，叫做代码审查。我今天在这里要说服你们，这实际上不是一个技能问题，没有任何数量的工程或循环最大化可以解决一个根本上是模型训练问题的问题。这就是为什么我们说工程是不够的。为了理解这一点，我们得深入探讨编码模型是如何训练的。我将谈谈我认为当前一些基准测试的缺点，以及更好的基准测试可能是什么样子。我还会谈谈在此期间如何安全地更快前进。嗯，这听起来可能像是一通抱怨，但这里有希望。嗯，我将谈谈我们的历程，以及我们在构建这个世界时遇到的一系列陷阱，以及我们与许多用户和客户共同开发的一系列令人兴奋的新技术。我认为我们作为一个社区，如何进入智能体工程的下一个篇章，无论这之后是什么。嗯，我们在这里用了很多词。我想稍微理清一下。我想给你们一个软件工厂的简要历史。嗯，实际上，我上周才知道，“软件工厂”这个术语是在 1968 年的一个 NATO 会议上定义的。它大约在 2022 年左右开始出现，就在 AI 开始兴起之前。嗯，基本上，在一个典型的 2022 年软件工厂里，你会有一群人在构建东西。你会有工程师，你会有产品经理。也许你有一些领导团队在推动愿景。他们都认为有些事情需要完成。所以你把它放进一个追踪器里，比如 Linear、Jira、Asana，某种状态机，用来追踪需要完成的事情。然后有人去那里拿一个任务，然后构建这个东西。在这个过程中可能会有一些自动化测试，也可能有一些手动测试。到了某个点，我们创建一个拉取请求，说，好的，酷。我们要运行一些检查，自动化的事情，人类会审查变更和代码。也许我们甚至会让人类以某种方式拉取代码并进行测试。如果这里出了任何问题，我们会回溯到构建这个东西的人，最终，我们准备好投入生产。所以我们把它部署到生产环境。一旦它进入生产环境，就会与我们的用户接触，用户会做我们都喜欢的一件事。嗯，用户喜欢抱怨。我爱我们的用户，但是，是的，他们会要求东西。他们会发现 bug，你会收到功能请求，嗯，这些会反馈给你的团队。你可能还会添加监控。所以，嗯，你知道，我们最想要的是什么？我们想要在凌晨三点东西坏了的时候叫醒工程师。然后你就会被拖进一个 bug 里，试图去修复它。嗯，我们在这个循环里循环往复。嗯，我们交付了大量的代码。嗯，我们在这里注意到的一件事是，团队几十年前就发现了，这个“有人构建东西”的步骤，嗯，在大多数情况下通常需要数小时或数天，而审查部分对于大型项目也需要数小时或数天。所以团队开始做这些前期规划、架构提案、冲刺规划，并且作为一个团队在这些事情上进行协作，嗯，希望这样可以降低某些东西需要返工的几率，这样我们就能够减少审查每一行代码所花费的时间，因为我们在事前已经对齐了一切。

<details>
<summary>Original English</summary>

**Speaker 13**: that's way too many slides hold on guys. okay. so we're all racing to put eye coding into production. and there's been lots been said about loop engineering, and we should probably write more loops. and yeah, II, guess we doing loops? now strong gm, built a lights off software are factory where nobody even raiss the code. and the prevailing narrative is we should just end more tokens. you are the bottm eck. the models are good enough code is free, just ship more stuff. but at the same time, we are starting to see the cracks, our friend morio at ai engineer, europe begduus to slow down because companies that should not be having outages because of coding agents or having outages due to coding agent, perhaps um code bases are falling apart faster than they ever have before. and our friends and far, as say, i actually even did a report since we all picked up all these AI coding tools in january, a be february ary um or request coreview quality is wait down, were having more comments longer comments and tons of ps being worged without any review at all incidents are way up. bugs per developer a way up, and many people will tell you that you're holding it wrong. that's the only reason you're not. well, maybe you are, but that's not the point, but i've spoken a lot about how to hold it better when it comes to working with AI, probably ly million views on youtube, but this point across a monunch different talks. ks. and the basic thing is like, as engineers, we've been told that if token maxzine isn't working than it's a skill issue, you just need to spend more tokens um with enough reading the code that with enough harnest engineering. if we maybe sprinkle some magic words, adversiial review, enenough or PR bots that we can get the best of both worlds, ten do one hundred exfaster high quality. and nobody has to do that thing. we all hate called code review. i'm here to convince you today that this is, in fact, not a skill issue that that no amount harharness engineering or loops maxine can solve what is fundamentally a model training issue. that's why we say the hardest is not enough um and to understand this, we kind of have to grapple and digin to how coding models are trend. i'm going to talk about what i think the shortcomings are with some of the current benchmarks and what better ones might look like. and it's will talk about how to move faster safely in the meantime, um it's because sound like a rant um but is hope here um i'm going to talk about our journey and a bunch of the land minds we've hit um building in this world, a bunch of exciting new techniques that we've been king king with a lot of our users and customers dedevelop. and i think how we all as a community get to the next chapter of agentic engineering after whatever this thing, if that were in. um so we use a lot of words here. i assume out a little bit. i want to give you kind of like a brief history of the software factory. um and if actually, i don't i just learn this last week is the term software are factory was defined a nato conference in ninenineteen sixty years. you'll start around twenty twenty two right right before II started coming around um and basically in a typical twenty twenty two software factory. you will have some people building stuff. youll have engineers, you'll have pms. maybe you have some sort of leadership teen that is driving the vision here, and they all the side that stuff needs to get done. and so you put it in a tracker, a linear, a gera abeds, some sort of state machine, the tracks, what needs to be done. and then someone goes and grabs something off for there. and they build the thing. and there maybe some automated testing in that process, mabe be might manual testing in that process. and a certain point we make this poll request thing says, okay, cool. we're got to run about to checks automated stuff, a humans going to review the change and review the code. and perhaps we might even have uh a human pull down and test it somehow. and if anything goes wrong here, we look back to someone builds the thing and eventually, we're ready for product. and so we shift it to production. and once it's in product makes contact with our users and users, do a thing that we all love. um users love to complain. i love our users, but yeah, they're going ask for things. things are going to find bugs, you're going to file feature requests um and that goes back to your team. you might also add monitoring. and so um you know what do we want more than anything se? and we want to wake up engineers at three in the morning when something breaks. so then you get dragged out a bug to try to go fix it. um we waon on on in this loode. um and we am ship a bunch a code. um and one thing we we notice here is that teams figured this out decades ago is that this someone builds the thing step 嗯 is usually going to take hours or days in most cases, and the review part will also take hours or days for large things. and so team started doing these upfront planning, architectural proposals, sprint planning, and it would collaborate on on on these things as a team, uh, with the hope that we might decrease the percent chance that something would need to be reworked that we would be able to reduce the time spent in reviewing every line of code because we aligned on everything ahead of time.

</details>

<!-- chunk 48/54 -->

### 从编码代理工厂到“熄灯”软件工厂的演进

**Speaker 13**: 这就引出了代理软件工厂。现在每家公司都在谈论他们如何构建了一个编码代理工厂，将百分之七十五的代码编写工作转移给了代理。

<details>
<summary>Original English</summary>

**Speaker 13**: this brings us to the agentics software factory every company and their mother is talking about how they built a coding agent factory that shift seventy five percent of their code.

</details>

**Speaker 13**: 现在，几乎所有人都在说这个。

<details>
<summary>Original English</summary>

**Speaker 13**: now, literally everybody.

</details>

**Speaker 13**: 所以我们来看一下从二零二二年开始的软件工厂模型。我们只是把“有人构建东西”替换成了“代理构建东西”。我们有一个编排层、一个沙箱测试平台、一个模型和计算机使用能力。我不会深入讨论这些细节，这周你们肯定能听到一百场相关的演讲。

<details>
<summary>Original English</summary>

**Speaker 13**: and so we look at the software factory from twenty twenty two. We just replace someone builds the thing with an agent builds the thing. And we have an orchestration in a harness of sandbox in a model and computer use. And i'm not going to get into the details of that. You can watch one hundred talks about that this week, i'm sure.

</details>

**Speaker 13**: 但现在，构建部分只需要几分钟或几小时，而人工部分——如果你要审查代码并测试更改——仍然需要几小时或几天。所以我们引入了代理代码审查和代理回归测试，这让这部分流程更快了，但它可能仍然是瓶颈。不过我们可以在这一环节做更多循环。为什么不多做些循环呢？

<details>
<summary>Original English</summary>

**Speaker 13**: but now the building part takes minutes or hours, but this human part still takes hours or days if you're going to review the code and you're going to test the changes. And so we bring an agentic code review, and we bring an agentic regression testing and it makes this part faster, but it's probably still the bottleneck, but we can do more loops here. Why not? Let's do some more loops.

</details>

**Speaker 13**: 所以我们可以把所有事件直接路由到工厂里。这样还需要有人被叫醒去修复问题吗？也许代理能帮你解决这个问题。你可以收集所有用户反馈，直接把它们塞进工厂。这样人们就可以提出需求，然后需求就被构建出来。现在你唯一的工作就是：你能往待办事项队列里塞多少东西，以及你能以多快的速度审查和测试这些更改。

<details>
<summary>Original English</summary>

**Speaker 13**: so we can route all incident in straight into the factory. So does someone need to get woke up? And try to fix it when they try just wake up to a power query. And maybe that fixed the issue for you, you can take all the user feedback. So just stick a straight into the factory. So that people can ask for stuff, and it gets built. And now your only job is how much things can you stuff into the queue of stuff to do and how fast can you review and test the changes.

</details>

**Speaker 13**: 这当然就引出了“熄灯软件工厂”——我相信你们都知道。在这种模式下，基本上我们不再阅读代码了。我们会说，“你知道吗，代码审查这玩意儿进行得不错。不，谢了，我们不再做代码审查了。”我们把精力投入到系统的其他所有部分：测试、监控、部署所有其他东西。我们只管写更多代码，把那些系统构建得更好。现在我们的工作真的就只是：我们能要求代理构建多少东西？

<details>
<summary>Original English</summary>

**Speaker 13**: which brings us, of course, to the lights off software factory, where basically we no longer read the code. We say, you know what this is going great, that code review thing. No, thanks, or it is not going to do that anymore. And we invest into all these other parts of the system. You're testing your monitoring, you roll out everything else. We just write more code and build those systems better. And now our job really is just how much stuff can we ask the agent to build.

</details>

**Speaker 13**: 我要提出一个观点：这行不通。这就是为什么软件工厂会失败。我决定要说什么，这与Willem Larsen的那篇精彩文章无关。我打算直接引用他的话。一个开发者为一个只有十几个人会运行的个人项目编写代码，与一个团队为了让一个运行了十年的企业系统再维持一个季度而工作，这两者几乎没有任何值得一提的共同约束。你在互联网上听到的大部分内容，都是这两类人中的一群在告诉另一群人该如何生活。所以如果你喜欢“氛围编码”，请便。但我们关心的是：如何帮助人们在复杂的代码库中解决难题？

<details>
<summary>Original English</summary>

**Speaker 13**: i am going to posit that this does not work. And this is why software factories fail. As i decide what i'm going to say, has nothing to do with Willem Larsen had this great post. I'm going to literally take his quote for beta. A developer providing coding a side project a dozen people will ever run, and a team keeping a ten year old enterprise system alive for another quarter share, almost no constraints worth naming. And most of what you hear on the internet is one of these groups of people telling the other group of people how to live their lives. So if you love vibe coding, please go on. What we care about is, how do we help people solve hard problems in complex code bases?

</details>

**Speaker 13**: 我们经常处理“棕地”项目，传统上这指的是那些运行了十年的老旧系统。实际上我认为，代理在项目开始大约三到六个月后就开始真正遇到困难了，尤其是在我们如今能够如此快速地交付代码的情况下。你可以问我怎么知道的，我会告诉你，这是因为二零二五年初的Joy。我们试过这个。我们完全进入了“熄灯”模式。如果你认真尝试过几个月，你可能至少发现了一个代理无法解决的问题。即使你使用了最先进的提示词工程，做了研究，进行了复现，你最终还是得亲自深入那个你已经三个月没读过的代码库，去弄清楚到底哪里出了问题。与此同时，你的网站宕机了，你的用户非常愤怒。而如果你像我一样，在阅读所有这些被你放任流入系统的劣质代码时，你可能会感到非常痛苦。

<details>
<summary>Original English</summary>

**Speaker 13**: we are brown field a lot, which historically has meant like some ten year old job a thing. I actually think agents really start to struggle after maybe three to six months, especially with the pace at which we can ship. Now you can ask me how i know this, and i will tell you that is because of Joy, old, twenty twenty five. We tried this. We went full lights off. If you have tried this seriously for number of months, you probably found at least one issue that the agent couldn't solve. Even with your most advanced prompting, you do research with do reproductions, you just you have to go and dig into that code base that you stop reading three months ago to try to figure out what's broken. And in the meantime, your site was down your users were pissed. And you, if you were like me, you were probably miserable reading all this slop code that you let slip into your system.

</details>

**Speaker 13**: 我想说的是，模型有一个缺点。它们无法在没有相当程度的人类引导下，长期维持并提升代码库的质量。可维护性基本上指的是，在代码库的一个部分进行更改变得非常非常困难，而不会破坏其他部分。这是Martin Fowler的“ shotgun surgery”，教科书式的代码坏味道。关于可维护性，有很多书可以读。事实上，John Ousterhout这周也在这里演讲，如果你想的话，可以亲自去问他关于软件设计哲学的问题。

<details>
<summary>Original English</summary>

**Speaker 13**: and what i want to get to is basically, models have a shortcoming. They can't maintain an improve code base quality over time, not without a decent amount of human steering. And i want say, maintainability basically talking about issues like it becomes really, really hard to make a change in one part of the code base without breaking other parts of the code base. This is Martin Fowler, low shock on surgery, textbook code smell. There's a bunch of books even go read about it. In fact, John Ousterhout, who is actually here speaking this week. So you can go ask him in person about the philosophy of software design, if you want to.

</details>

**Speaker 13**: 但这引出了一个问题：为什么模型不能做软件可维护性？你可能会说，“但是Dax，你知道，从那以后模型已经进步了很多。”它们在有些方面确实变好了，但在其他方面基本还是老样子。如果你想解决“氛围编码”或一个新营销网站的问题，是的，它们比二零二四、二零二五年好多了。但就提升代码库质量而言，我认为它们并没有进步多少。我无法证明这一点，因为没有好的基准测试来衡量模型维护代码库质量的能力。但如果你和编码代理一起工作过一段时间，很多人可能都有这样的感觉：它们通常会让事情随着时间的推移变得更糟，让代码库更难处理。

<details>
<summary>Original English</summary>

**Speaker 13**: but it brings us in this question of, like, why can't models do software maintainability? And you may also be saying, but dex, you know, surely the models have gotten much better since then. They've got better in some ways, but they still about the same in others. If you want to solve one of problems or vibe code, a new marketing site. Yes, they got way better since twenty twenty five and twenty twenty four. But as far as improving code base quality i think they not got gotten much better. Now. I cannot prove this because there are no good benchmarks for a model's ability to maintain code base quality. And i'll getting it like where we're going with that. But if you work with coding agents for a while, a lot of people probably have this feeling that they generally make things worse over time and make the code is harder to work in.

</details>

**Speaker 13**: 为了弄清楚为什么会这样，我们先退一步，看看第一个伟大的编码代理。为什么Claude Code能在不到一年的时间里从零做到四十亿？我认为现在是九十亿收入。因为在Claude Code之前就有很棒的编码代理，你有Aider，你有CodeBuff，这个类别里有很多工具。它们都拥有相同的工具集。那么区别是什么？区别在于，这是第一次有模型实验室针对他们将分发给用户的测试平台来训练模型。它变得非常非常擅长在代理循环中调用这些工具。事实上，OpenAI团队在十一月做了一个演讲，基本上是说，如果你是一个测试平台构建者，而你不拥有模型权重，并且你不能在你的测试平台中训练模型，那么与那些同时拥有模型和测试平台的人相比，你将永远处于劣势。

<details>
<summary>Original English</summary>

**Speaker 13**: to figure out why this happens going to zoom out to the first great coding agent. Why did Claude Code go from nothing to four billion? And i think now they're nine billion in revenue in under a year because there were great coding agents before Claude Code. You had Aider, you had CodeBuff. There was a bunch of tools in this category. They had all the same tools. So what was the difference? The difference was that, that this was the first time that a model lab trained a model against the harness that they were going to distribute to users in. And it got really, really, really good. This is just some of the tools, but it got really, really good at calling these sorts of tools in an agentic loop. In fact, the OpenAI team did a talk in november about basically if you are a harness builder and you don't own the model weights, and you can't train the model in your harness. You will always be at a disadvantage compared to somebody who owns both the model and the harness.

</details>

**Speaker 13**: 我要引用我同事Calvin French-Owen的几张幻灯片，他在Codex最初发布时是MTS。但模型只是下一个词元的预测器。这是一年多前的幻灯片，基本上，当你进行代理循环时，上下文进入，下一步输出。我们之前已经演示过这个，但我们要在六十秒内演示编码代理和强化学习。我们要做的是：让模型更好地调用工具，更好地解决软件问题。我们会生成一个问题，把问题交给它，然后生成一系列尝试解决该问题的轨迹。我们会根据正确性、测试通过率等所有指标对它们进行评分。然后我们会进行强化：让不良行为发生的可能性降低，更新权重让良好行为更可能发生。

<details>
<summary>Original English</summary>

**Speaker 13**: and i'm going to cite a couple slides from my buddy Calvin, French-Owen, who was a MTS on Codex during the initial launch. But models are just next token predictors. This is slide from over a year ago, where, basically, as you're doing your agentic loop context when it goes in next step comes out. And we've demonstrated this, but we're going to see we're doing coding agent and reinforcement learning in sixty seconds. So what we're going to do is get the model to get better at tool calling, better at solving software problems? We're going to generate a problem. We going to give it a problem. And we're going to generate a bunch of traces try to solve the problem bunch of different times. We're going to score them all on correctness and the test pass and all this stuff. And then we're going to reinforce, we're going to make the bad behavior less likely and we're going to update the weights to make the good behavior more likely.

</details>

**Speaker 13**: 这里有一个经典的基准测试：SWE-bench。这些是大约十五分钟的任务，来自像Rails、Jacquard和Django这样的开源仓库，它们有二元奖励：你修复了你试图修复的问题吗？你在不破坏其他东西的情况下做到了吗？我们来看一个来自这些基准测试的实际问题。这是Fastlane，一个Ruby项目。

<details>
<summary>Original English</summary>

**Speaker 13**: there's one of the classic here is SWE-bench multilingual. They're about fifteen minute tasks from open source repos like Rails and Jaco and Django and all this stuff, and they have binary one or zero rewards on. Did you fix the problem you were trying to fix? And did you do without breaking anything else? We look at actually your real problem from one of these benchmarks. This is Fastlane, which is a Ruby project.

</details>

**Speaker 0**: 基本上，有一个问题是我们没有检查空值，然后因为一个空指针异常导致堆栈跟踪崩溃。在这个基准测试中，你会有一个基础提交，我们会在人类过去解决这个问题之前将其检出。我们会给它一个测试补丁，说明之后的行为应该是什么。我们有一个黄金补丁，这些对模型是隐藏的。然后我们让代理去尝试解决这个问题，我们存储补丁，并且我们会忽略对任何测试文件所做的更改，因为我相信你们见过模型注释掉测试代码只是为了让它通过。然后我们会应用我们的黄金测试补丁，运行所有测试和新测试，如果它们都通过了，我们就得到奖励，否则就没有。模型的目标就是让测试通过。在这个系统中，我们没有办法因为糟糕的程序设计或损害系统的可维护性而惩罚它。这就是为什么我们会得到像这样的东西：在不必要的地方加上try-catch，或者像这样。我认为Biboga之前举过强制类型转换的例子，模型只是为了通过测试而做各种事情。因为你无法验证代码的可维护性，所以在这方面进行训练就变得非常困难。

<details>
<summary>Original English</summary>

**Speaker 0**: basically, there was some issue where we weren't checking for null. And we have a stack trace blow up because we have an null pointer exception. And in this benchmark, you have a base commit that we're going to check out before the issue was solved by a human in the past. We're going to give it a test patch that says, here's what the behavior should be. Afterwards. We have a golden patch. And these are hidden from the model. And so we have the agent go try to solve the and we store patch and we ignore all changes made to any test files because i'm sure you've seen models comment out test just to get things working. Because then we're going to apply our golden test patch. And we're going to run the test, all test and the new test pass and they both pass. Then we get the reward, otherwise we don't and the models are trying to get the test to pass. There's no way in this system that we can penalize it for poor program design or for eroding the maintainability of our systems. That's why we get things like this. Try catches around things that probably don't need a try catch or things like this. I think Biboga gave this example earlier of casting things, the other things just so the model can just wants to get the test to pass. And so you can't verify the maintainability of the code, it gets way harder to train on this stuff.

</details>

<!-- chunk 49/54 -->

### 代码可维护性评估的未来

**Speaker 0**: 所以请记住，验证图片质量、代码可维护性，比代码能跑、测试能通过要难上好几个数量级，因为糟糕架构的成本函数是以月甚至年为单位来衡量的。

<details>
<summary>Original English</summary>

**Speaker 0**: So remember, picture verifying code quality, maintainability is orders of magnitude harder than the code runs and the test pass, because the cost function of bad architecture is measured in months and years.

</details>

**Speaker 0**: 如果你有一个代码片段，几个月后才发现有人把它改得有点过头了，那么要把这个奖励信号反向传播回去，真的非常困难。

<details>
<summary>Original English</summary>

**Speaker 0**: If you have a code episode and then you only find out months later that like somebody vibed this a little bit too hard, there's really hard to propagate that reward signal back across the gap.

</details>

**Speaker 0**: 现在，第一年正在慢慢变好。而且我知道有人在YouTube评论区会提到这一点，是的，我知道基准测试和验证器是不同的，它们实际上必须是不同的数据集，但它们的形态相同，这些基准测试的结构直接正确，或者说是基础性的。

<details>
<summary>Original English</summary>

**Speaker 0**: And now the first year's getting better slowly. And since I know someone's going in the YouTube comments about this, yes, I know benchmarks and verifiers are different, and they did actually have to be separate data sets, but they're shaped the same and the structure of these benchmarks directly correctly or fundamental.

</details>

**Speaker 0**: 那么，评估代码可维护性的未来是什么？有一个很酷的东西叫SWE-bench Multimodal，来自Abundant AI？或者像四百小时的任务，比如克隆微软的整个Excel，每一个功能？嗯，他们有一些复杂的奖励通道机制。

<details>
<summary>Original English</summary>

**Speaker 0**: So, what is the future of evaluating code maintainability? There's a really cool one called SWE-bench Multimodal from Abundant AI? Or where you have like four hundred hour tasks of like clone all of Microsoft Excel, every single feature? Um, they have some sophisticated reward channel stuff.

</details>

**Speaker 0**: 嗯，来自Data Curve的SWE-bench也是类似的大型任务，基于那些实际上不在训练集中的开源仓库，因为它们从未在现实世界中真正构建过。嗯，还有来自Cognition的Frontier Code，这是多PR任务。他们做了一些有趣的事情，比如让模型编写测试，如果模型没有通过补丁代码，它就会受到惩罚。我们还有一个评判模型，它会说：“好的，因为这遵循了我们所有的代码质量规则。”

<details>
<summary>Original English</summary>

**Speaker 0**: Um, SWE-bench from Data Curve is also like large tasks on OSS repos that were not actually in the training set because they were never actually built in the real world. Um, in the Frontier Code from Cognition, um, which is multi-PR tasks. They do interesting things like have the model write tests that if the model doesn't patch the code then it gets penalized. And we have a judge model that says, "Okay, because did this follow all of our code quality rules."

</details>

**Speaker 0**: 嗯，所以我们正在进步。但我认为模型评判质量只能走到这一步。嗯，因为如果新模型，如果模型知道好的代码长什么样，它可能一开始就会写出来。嗯，审查代理在推理过程中使用更多令牌，它可以提高下限，但我们仍然受到在强化学习过程中所能教授的内容的限制。

<details>
<summary>Original English</summary>

**Speaker 0**: Um, so we're getting better. But I think models judging quality can only go so far. Um, because if the new model, if the model knew what good code looks like, it would probably write it in the first place. Um, and review agents, during more tokens of the problem, it can raise the floor, but we're still constrained by what we can teach during RL.

</details>

**Speaker 0**: 嗯，所以我会假设，对于AI来说，我们仍然困在阅读代码的阶段，但我们可以快速行动。当然，未来也存在这个问题被解决的世界。如果你只想不断抛出问题，直到你得到GPT-7，并且你想考虑这个问题，请便，嗯，但我最好还是少做预测。我们有一些问题要解决。所以，让我们用工程方法解决这个问题。

<details>
<summary>Original English</summary>

**Speaker 0**: Um, and so I will posit for an AI, we're stuck reading the code, but we can move fast. And of course, there's a world where this is solved um in the future. And if you want to just keep throwing problems until you get to GPT-7 and want to think about this, by all means, please um, but I'd better less predict. We've got some problems to solve. So let's engineer our way out of this.

</details>

**Speaker 0**: 对对对，嗯，所以把话题拉回来。我们要把代码审查放回去。嗯，我们要拥抱这种方法：我们如何提前规划，以减少我们经历漫长或困难审查过程的可能性？我们要找到杠杆。我们要使用AI来帮助解决这个问题。

<details>
<summary>Original English</summary>

**Speaker 0**: Right, right, right. Um, so turning the lens back on. We're going to put the code review back. Um, we're going to embrace this approach of like how do we plan up front to reduce the chance that we have a long or a difficult review process? We're going to find leverage. We're going to use AI to help with this.

</details>

**Speaker 0**: 嗯，我们要做的第一件事是进行某种产品评审，理解要解决的问题是什么。期望的行为是什么？也许看看线框图？这里有一个产品评审的例子，就像我们昨天对一个新功能的线框图所做的那样。嗯，一旦我们完成了产品评审，顺便说一句，小东西我们仍然直接交给代理。但一旦我们有了产品评审，我们还会进行架构、系统架构。很多人已经这样做了一段时间了。组件契约、数据模型、约束条件。

<details>
<summary>Original English</summary>

**Speaker 0**: Um, the first thing we're going to do is some sort of product review, understanding what problem we're solving. What's the desired behavior? Maybe looking at mock ups? Here's a product review as we were going on yesterday with a mock up of a new feature. Um, once we have our product review, by the way, we don't small stuff still goes straight to the agent. But once we have the product review, we will also do architecture, system architecture. A lot of people have been doing this for a while. Component contracts, data models, constraints.

</details>

**Speaker 0**: 嗯，这是一个我们构建的文档示例，用来理解这些系统将如何组合在一起，以及从那里看到的全局图景是什么。然后，我们做一些我认为在当今编码中被严重低估的事情，那就是程序设计。我认为人们认为一旦架构正确，模型就可以直接生成代码了。嗯，但我们不知道，我们经常需要深入到类型、方法签名、程序布局和调用栈中。

<details>
<summary>Original English</summary>

**Speaker 0**: Um, this is an example of a doc that we build to understand how these systems are going to fit together. And what's like the high level picture of it from there? Then we do something that I think is really under-emphasized in coding these days, which is program design. I think people assume that once you get the architecture right, the model can just cook. Um, but we don't know, we often look into the types and the method signatures, the program layout and call stacks.

</details>

**Speaker 0**: 所以这里有一些例子。我不认为你能读懂这个，但这正是我们实际如何布局这些东西以及这些系统将如何交互的抽象层次。嗯，来自Cloudflare的Dylan M. 经常谈论他如何在规划过程中使用这些调用图。我认为这完全正确。嗯，然后一旦我们完成了程序设计，我们可以做一件叫做“垂直切片”的事情，嗯，这是实现顺序和多仓库协调。我们如何在整个系统中构建它，以及如何在此过程中检查它。

<details>
<summary>Original English</summary>

**Speaker 0**: And so here's some examples. I don't think you'd be able to read this one, but this is like the level of abstraction or rate is how we actually lay this stuff out and how these systems are going to interact. Um, Dylan M. from Cloudflare talks a lot about how he's using these call graphs as part of his planning process. I think this is exactly right. Um, and then once we've done the program design, we can do this thing called vertical slices, um, which is the order of implementation, multi-repo coordination. How we're going to build this across our entire system and how we're going to check it along the way.

</details>

**Speaker 0**: 我其实对水平规划模型有点看法，但不会深入讨论。如果你想了解更多，可以去看看我们在AI Engineer Miami的演讲。嗯，这里有几个这样的文档截图，展示了测试和每个阶段之间的步骤。嗯，这里的主要思想是，在预先规划和协调上花费三十分钟，可以在审查中为你节省数小时。

<details>
<summary>Original English</summary>

**Speaker 0**: I actually have a bit about how models of horizontal plans and won't go too deep into it. If you want to learn more about this, you can go watch our talk from AI Engineer, Miami. Um, couple of shots of a doc like this, going through the tests and the steps in between each phase. Um, the main idea here is thirty minutes over here in pre-planning and alignment can save you hours in review.

</details>

**Speaker 0**: 所以，实际上仍然需要阅读每一行代码。嗯，跳过这部分。基本上，这里的总结是，你不会有太多的PR。如果你被PR淹没了，实际上是你有太多糟糕的PR，嗯，因为好的PR审查起来是一种享受。它非常彻底。是的。这很棒。这就是我们讨论过的。这就是我们谈到的。

<details>
<summary>Original English</summary>

**Speaker 0**: And so it's actually visible to still read every line of code. Um, skip this part. Basically, the summary here is like you don't have too many PRs. If you're drowning in PRs, you actually have too many bad PRs, um, because good PR is a joy to review. It's just really thorough. Yep. This is great. This is what we discussed. This is what we talked about.

</details>

**Speaker 0**: 但即使AI生成的代码只需要20%的返工，这对很多AI代码来说已经很慷慨了，嗯，这对审查者和提交者来说都是一种情感和智力上的负担。对对对，嗯，所以如果你使用模型进行规划和协调，你的协调时间会更短，因为你使用AI一次性获取所有信息。你的代码审查更快，因为你提前对齐了，你的编码也更快，因为AI完成了编码。所以你实际上并没有真正移动得更快，但你仍然在阅读所有内容，你仍然在审查代码。

<details>
<summary>Original English</summary>

**Speaker 0**: But even if AI PR needs twenty percent rework, which is generous for a lot of AI code flops, um, it's an emotional and intellectual burden on both the reviewer and the submitter. Right, right, right. Um, and so if you use models for planning, alignment, your alignment is shorter because you use AI to get all the information at once. Your code review is faster because you aligned up front and your coding is faster because AI did it. And so you're not actually really moving faster, but you're still reading everything, you're still reviewing the code.

</details>

**Speaker 0**: 所以，总结一下。嗯，听到这些很容易感到有点沮丧。呃，你真的很想要一个我们只需放手一切的世界，我们可以永远不再阅读代码。嗯，但我们是工程师，这些只是约束条件。模型擅长某些事情，它们不擅长其他事情。所以，去弄清楚如何在一组约束条件下解决问题。使用循环，它们很棒。去解决难题。寻求杠杆作用。

<details>
<summary>Original English</summary>

**Speaker 0**: So, closing thoughts. Um, it's easy to hear all this and be a little burned out. Uh, you really like the world where we just let go of everything, and we can just like not have to ever read code ever again. Um, but we're engineers, and these are just constraints. Models are good at certain things and they're not good at other things. And so go figure out how to solve problems given a set of constraints. Use loops, they're great. Go solve hard problems. Seek leverage.

</details>

**Speaker 0**: 嗯，如果你想在这方面得到帮助，我们正在构建HumanLayer，HumanLayer是一个AI IDE和协作平台，它是你软件工厂的构建模块，嗯，并且很快将成为更好的软件质量验证器。我们为云端代码和代码风格工作区做了一个重大举措。它会引导你完成执行这类工作的工作流程。我们正在与设计合作伙伴洽谈。我们正在招聘创始工程师，在这里和旧金山都有职位。去获取这些幻灯片，现在就去看。你可以在humanlayer.com上试用HumanLayer。嗯，小团队免费。去解决难题和复杂的代码库。

<details>
<summary>Original English</summary>

**Speaker 0**: Um, if you want help with this, we're building HumanLayer. HumanLayer is an AI IDE and collaboration platform, its building blocks for your software factory. Um, and soon to be a better verifier for software quality. We've got sort of a big move for cloud code and code style workspace. It walks you through the workflows for doing this sort of work. And we are talking to design partners. We are hiring founding engineers here and in San Francisco. Go and get these slides and go get them right now. You can try HumanLayer at humanlayer.com. Um, free for small teams. Go solve hard problems and complex code bases.

</details>

**Speaker 3**: 感谢大家的热情。

<details>
<summary>Original English</summary>

**Speaker 3**: Thank you all for your energy.

</details>

**Speaker 4**: 请大家欢迎，来自Libaness Labs的研究学者，Eric Admir。

<details>
<summary>Original English</summary>

**Speaker 4**: Please welcome to the stage, the research scholar at Libaness Labs, Eric Admir.

</details>

### 利用类型系统实现AI安全

**Speaker 5**: 嗯。

<details>
<summary>Original English</summary>

**Speaker 5**: Um.

</details>

**Speaker 1**: 嗯，能往回退一点吗？抱歉，好的。大家下午好，感谢你们在漫长的一天展览之后还在这里。哦，抱歉，那是个现场活动。嗯，我希望你们看这个演示能和我制作它一样开心。让我先把话说清楚：这不是产品发布或公告之类的。这是一个二十分钟的教程，教你如何使用基本类型、静态类型和编译器知识来使AI变得可证明安全。我今天要和你们分享我所有的秘密。

<details>
<summary>Original English</summary>

**Speaker 1**: Well, can you go back one slide? Sorry, all right. Good afternoon, everybody, thanks for being here after a long day of docs exhibits site event. Oh sorry, that was a site event. Um, I hope that um you have as much fun watching this demo as I had creating it, and let me first get this out of the way. This is not a product launch or announcement or anything. It's a twenty minute tutorial of how you can use elementary types, static types and compiler knowledge to make AI provably safe. And I'm sharing all my secrets with you today.

</details>

**Speaker 1**: 希望这能激励你们中的一些人，明年你们会在楼下有一个展位，展示你们自己创建的可证明安全的代理工具。或者，谁知道呢，也许你们中的一些人已经解决了这个问题。请告诉我，然后你知道，我们可以去喝杯咖啡，而不是做这个演讲了。嗯，闲话少说，我们开始吧。

<details>
<summary>Original English</summary>

**Speaker 1**: And hopefully to have inspired some of you, next year you will have a booth downstairs where you have created a provably safe agentic harness. And or who knows maybe some of you have already solved it. Let me know, and then you know, we can grab a coffee instead of doing this talk. Um, with that out of the way, let's get going.

</details>

**Speaker 1**: 嗯，在我准备这些幻灯片的时候，抱歉我同时在多任务处理，我还在现场用Cursor编码。然后当我的注意力分散了几秒钟，因为我试图说服模型画一些它不想画的画，你们稍后会看到其中一些画，你们可以猜猜哪些是被拒绝的。当然，当我准备删除我的一个文件时，我确信你们以前也遇到过这种情况，嗯，或者也许没有，也许你们总是，你知道，以无权限方式运行所有东西，然后你说“是，是，是”，但我喜欢活得危险一点。

<details>
<summary>Original English</summary>

**Speaker 1**: Um, while I was prepping these slides, and I'm sorry that I was multitasking, but I was also um live coding on the side. And then when my attention went for a few seconds, because I was trying to convince the model to draw some pictures that it didn't want to do, and you will see some of these pictures later, you can guess which ones were rejected. Certainly, when I went to delete one of my files, and I'm sure this has happened to you before, um, or maybe not, maybe you always like, you know, run everything with no permissions. And then you say, "Yes, yes, yes," but I like to live dangerously.

</details>

**Speaker 1**: 嗯，但我相信，如果在模型的目标和模型当前所处位置之间存在任何障碍，它会尽其所能去实现那个目标，包括杀死我们，或者删除你的文件，或者删除你的数据库。所以我认为这些模型本质上非常非常危险，我们必须驯服它们。所以这就是我的演示内容。

<details>
<summary>Original English</summary>

**Speaker 1**: Um, but I'm convinced that if there's anything between the model's goal and where the model currently is, it will do everything that it can to reach that goal including killing us or deleting your files or deleting your database. So I think that these models are intrinsically very, very dangerous and we have to tame them. So that's what my demo is about.

</details>

**Speaker 1**: 那么，让我们开始这个故事。我认为这是一个非常非常悲伤的故事，但也是一个可怕的故事，关于我们作为一个行业如何走到了这一步，我们即将让普通人，普通大众，将他们的计算机、他们的财务、他们的整个个人生活的控制权交给AI代理。而我们没有任何保护措施。我认为这非常非常悲伤和可怕。

<details>
<summary>Original English</summary>

**Speaker 1**: So let's like, you know, start this story. And it's I think a very, very sad story, but also a scary story of how we, as an industry, got to this point, where we are about to let normal people, the general public, give control of their computers, their finances, their whole personal lives over to AI agents. And we don't have any protection in place. I think very, very sad and scary.

</details>

<!-- chunk 50/54 -->

### 从对话到行动：AI 安全的新挑战

**Speaker 1**: 那么让我来告诉你我们是如何走到这一步的。我会引入一些角色，比如 Claude，我们还会看到 Dario 和 Sam Berne，但主角是我们这里友好的小 Clot。我想你们都记得 2022 年 11 月 30 日。这可以说是历史上非常特别的一天，因为这是你第一次能够与你的电脑对话。你可以说“帮我总结一下我的邮件”，然后它就会用完美的英语回答你。对我来说，至少那是个奇迹。但我认为我们大多数人当时并没有意识到，引入这个看似无害的功能——允许模型提出问题并返回答案——会打开一个潘多拉魔盒，并将永远改变我们的历史。

<details>
<summary>Original English</summary>

**Speaker 1**: and so let me tell you the story how we got there. and i will like like have some characters like claude, and we will see dario and yeah as sam berne, but and the main character is is our friendly pit clot here. i think you can all remember um november thirty twenty twenty two. this was kind kind like a very special day in history, because this was the first time that you could speak to your computer. you could say you like summarize my emails, and it would, you know, answer you in perfect english. um i think for me, at least that was magic, but i think most of us didn't realize that by introducing this innocent looking function here, allow m that thinks a question and returns and answer that, that would open on door's box, and that would change our history forever.

</details>

**Speaker 1**: 但在我们继续这个故事之前，这个会议叫做 AI Engineer，对吧？所以我们都是工程师，也许我们是最后一代仍然理解这是什么、代码是什么的工程师了。或者你们大多数人已经忘记了代码是什么，因为你们所有的代码都是由智能体编写的。但如果我们看这里的签名，它写着“奥林匹克问题”。问题，有一个答案。对，问题和答案并不是字符串。它们是非常复杂的 JSON 结构，而且随着每一代新的大语言模型的出现，它们变得越来越复杂。但对于这次演讲，我们可以假设问题和答案只是大字符串。我们不在乎它们具体如何，我们在乎的是它们代表什么。

<details>
<summary>Original English</summary>

**Speaker 1**: and but before we go continue the story, this conference is called ai engineer, right? so we are engineers and maybe we're the last generation of engineers that still understand what this is, what code is. or maybe most of you have already forgotten what code is, because all your code is written by agents. but if we look at this signature here, it says it the olympics question. tion, there's an answer. 对 the question and answers are not strings. they are very complicated json structures, and they get more complicated every day. every time a new rage of abs comes out. but for this talk, we can just assume that question and answer are just a big types. we we don't care about how care like we do care about what they represent.

</details>

**Speaker 1**: 然而，大语言模型作为伟大工具的 euphoria 并没有持续太久。就在我们以为已经根除了计算机科学中的 SQL 注入这个小问题时，它却卷土重来了，因为坏人发现可以通过提示注入来欺骗大语言模型，而大语言模型无法区分代码和文本。所以它们非常非常容易被欺骗。我认为，这比 SQL 注入曾经带来的问题还要大。但让大语言模型名声不好的不仅仅是提示注入。大语言模型是在整个互联网上训练的，互联网上有很多好东西，但也有很多坏东西。比如如何制造炸弹？如何合成毒品？如何入侵系统？大型基础模型实验室的领导们有点担心政府会干预并监管这个行业。所以他们告诉他们的博士研究员们：去为这个问题找个解决方案。在政府介入之前解决它。于是，这些博士研究员们，因为他们是博士，他们深入思考了安全问题。他们为大语言模型想出了一个新接口。就是右边这个有点吓人的东西。看看那个。上面是不是有一些希腊符号？到处都是括号。嗯，你可能听说过 Lean。这里有人听说过 Lean 吗？Lean 现在可是热门货，对吧？风投们正在开出数十亿美元的支票，只要你声称你在做与 Lean 相关的事情。当然，这些博士研究员们正在使用 Lean，而你们却要因此受苦。

<details>
<summary>Original English</summary>

**Speaker 1**: now anyanythe upheria of like these alalyams is being a great tools didn't last very long. and just when we thought that we have eradicated the small box of computer science equal ejection, it came back with vengeance because the bad guys discovered that you can trick alyams using protet injection and alyams have no distinction, make no distinction in coat and text. and so they are very, very easy to trick. and this, i think, is a bigger problem than sequal injection ever was, and but it was not prompt ejection. only that made alamam sckind of like have a bad rap. allaams are drained on the whole internet. and there's like a lot of good stuff on the internet, but also a lot of bad stuff. like how do you create a bomb? how how do sysyntisize ed drugs? how do you heck into lesystems? and the leaders of the big foundation labs, they got a little bit worried that that the government with interfere and regulated the industry. so they told there phd researchers go find a solution for this. this problem, right and quick it before solve it before, you know, the government steps um and here, the PHD types since their PHD types, they thought long and heart about the safety problem. and they came up with a new interface for elams. that's this kind of scary sheet on the right. look at that. well, does it say there's like some sick, my greek symbols, there's brobes ever ver. well, that is an probably you have heard of lean. anyone here heard of lean an is now the half thing right? like vc are are writing, like multibillion dollar checks. if you just say that you're doing something with lee, and of course, these beach d types researchers are using lean and you have to suffer because of that.

</details>

**Speaker 1**: 现在让我们先看看这个签名。它用的是叫做 Dephane 的简单语言。它说的是：大语言模型接收一个问题，返回一个答案。它要求这个问题是“proper”的，这意味着它不是一个冒犯性的问题。然后模型返回一个安全的答案。而且这件事是自动证明的。所以如果你给它一个 proper 的问题，它就会给你一个安全的答案。我认为 Lean 受到了太多关注。我是一个正在康复的类型狂和数学成瘾者，我喜欢 Lean，但还有很多很多其他的定理证明器和模型检查器，比如 Isabelle、Rocq、PVS、Dafny 等等。但 Lean 是那种能让风投资金源源不断的东西。所以我今天会使用 Lean。嗯，这里我们再次把接口画了出来，在 Lean 中。在 Lean 中，你不需要做自动证明。如果你是 Lean 专家，你会说“Eric，我们有 Grind 和 Lean”，但让我们先把这些放在一边。但在 Lean 中，你既要展示如何计算结果类型，又要手动进行证明。所以这与自动证明略有不同。但如果你思考这件事哪怕一纳秒，你就会意识到，要写一个形式化证明来证明一个答案是安全的或一个问题是 proper 的，是不可能的。这就是为什么在楼下展厅里至少有 100 家初创公司都在使用大语言模型作为评判者，因为这不是你可以形式化规范的东西。一个答案安全意味着什么？这不是一个数学属性。当然，如果你像这些家伙一样拥有一个基础模型，你不需要外部的大语言模型作为评判者，你只需把它内置到模型中，然后称之为“模型已对齐”。但不幸的是，试图将对齐融入模型并非万无一失，模型经常被越狱，所以他们不得不去找教皇，请求他保佑他们的模型是安全的。

<details>
<summary>Original English</summary>

**Speaker 1**: now let's first look at the signature, and it's likely simply language called dephane. and what this thing says is that the alymtakes a question returns, an answer. it requires this question to be proper, which means that it's not an offended question. and then the model returns a safe answer. and this thing is proved automatically. so if you give it a proper question, it gives you a safe answer. now. i think there's too much attention for lean. i'm a recovering type holic and math addict, and i love lean, but there's many, many other dear provers and model checks out there like isaabi rock PVSDL plus and but lean is degrees that can't like keeps the vc money bumps going. so i will use lean and today. 嗯, so here years there kept luck it out the interface again and an and now and lean. you don't do automatically improving. if you're like a lean expert, you will say eric, well, we have grined and lean, but let's cup lucky up put that decide for a minute um. but in ine, you have to both show that how to compute the the result type and you have to do the proof by hand. so it's slightly different than the definitely a jump. but if you think about this thing for this a single nano second, you will realize that it's impossible to write a formal proof that an answer is safe or a question is proper. and that is why there are at least a hundred stargpps down here in exhibition hall that are using a allams as a judge, because this is not something that you can formally specifiabout. what does it mean that an answer is safe? that's not the mathematical property um. and of course, if you own an foundation model like these guys, you don't need external alalympse as a judge, you just be big it into the way. and you call it. the model is aligned. um but unfortunately, trying to bake alignment into the model is not foolproof, and models gets routinely jail broken, so they had to go to the pope. and ask it look get like, you know and bless their model that it's safe.

</details>

**Speaker 1**: 现在，我认为如果模型说了冒犯性的话，那很糟糕，但那些只是言语。归根结底，言语就像……它们会从你身上滑落，它们不会造成任何伤害。必须有人类根据言语采取行动，才能使其变得危险。所以也许这就是他们所说的“广义安全”的意思，也是 Anthropic 谈论安全时的意思，因为仍然有人类参与其中。但随后发生了一件可怕的事情，一件真正可怕的事情，永远地改变了世界。那就是在 2023 年 6 月，OpenAI 宣布 GPT-4 支持工具调用。当然，所有其他供应商都争先恐后地复制这个功能。这是最小差异化原则的体现，这就是为什么所有这些 API 看起来都一样。添加工具调用这个行为，将 AI 安全从一个哲学辩论变成了会造成真正危险的事情。你可以说工具调用给了模型手，除了嘴之外；或者你可以说工具调用就像给了它们一把上了膛的枪。但当然，没人听我的，每个人都无视我说的话。这些家伙就继续前进，快速转向工具调用。他们就是……就这么做了。我们在那个……现在让我们回到这是一个 AI Engineer 会议。所以让我们看看当添加工具调用时，大语言模型签名有什么不同。只是那里多了一个小小的 IO。当然，它搞乱了签名的格式。但如果你看这张图，你会看到，现在 Claude 从一只可爱的小狗变成了一个危险的东西。看看所有这些危险的工具。现在它变得可怕了，对吧？我从未见过比有大语言模型工具调用更可怕的东西。现在，如果你看这个，这就像类型系统的一小步，却是混乱的一大步。为什么？因为这个 IO 表明，为了计算答案，智能体必须进入智能体循环并产生副作用。在它产生答案的同时，它可能会清空你的银行账户，可能会删除你的文件。然后它给你一个安全的答案，但谁在乎安全的答案呢？我所有的文件都没了，对吧？所以没错，这是混乱的一大步。

<details>
<summary>Original English</summary>

**Speaker 1**: i'm now i think it's terrible if, like a model said something offensive, but those are just words, and ultimately, words are like they just like, you know, they drip off your body. they don't do anything. some human has to act on words to make them dangerous. and so maybe that is what they mean by broadly safe. and when tropicc talk about safety and because it's still a human involved, but then something terrible happened, something really terrible happened that changed the world forever. and that is and june twenty twenty twenty three open. the eye announced two goal support in GPT four. and of course, all the other vendors rushed out to copy this. this is gold to the principle of minimum differentiation, and that is why all these aps look the same. now the act of adding two goals, ls ges ges AI safety from a philosophhical debate, do something that causes real danger. you could say two goals give the model gloss, in addition to a mouth, or you can say two gouses like having a gun alload a gun to them. but of course, nobody listens to me, everybody ignores what they say. and these guys just went ahead. and keft shift toocalls. they just yeah, this just do it. 我们在那个 now let's go back to like this is ai engineer and conference. so let's look at what is the difference in the signature of alalench when they add a tool calls. and it's just that little i owe there. and of course, it message up the formatof, the h nature. but if you look at the picture, there were you show, now certainly clolot goes from like a nice puppy to a dangerous thing. look at as all these dangerous tools. and now it's become scary, right? i've never seen anything scary er than an alalamma tool goals. now, if you look at this, this is like like a small step for a type whether giant leap for chaos, why is that? and that is because this io says that in order to compute the answer, the agent has to go to the agentic loop and is doing side effeture. while it's producing the answer, it might empty your bank account, but might delete your files. and then it give you a safe answer, but who cares about a safe answer, but all my files are gone, right? so that's right say, it's it's a giant leap for for chaos.

</details>

**Speaker 1**: 再次抱歉，这是一个工程师会议。让我们看看这个类型 IO。你不需要理解它，但只需看到这里有一个叫做“Real World”的类型。是的，在 Lean 中。这是一个直接的东西，有一个叫做“Real World”的类型。为什么？因为 IO 类型的东西会改变现实世界。所以它警告你：不要用这玩意儿，因为它会产生不可逆的副作用，比如删除你的文件。所以，Solomon 在他的演讲中……去年，在这个叫做 AI Engineer 的会议上，有一个大语言模型在一个循环中破坏它的环境。我认为他是个英雄。我不知道 Solomon 今年是否在这里，但我认为他值得一轮掌声，因为我认为这是 AI 智能体的正确定义。顺便说一句，这是我不得不费力生成的一张图片，因为它明显描绘了暴力。所以这有点不安全，对吧？我有一张描绘暴力的图片。所以我们……嗯，我们的智能体可以访问私有数据。它们有像提示注入这样的输入内容，现在我们还给了它们工具。Solomon 的版本导致了这种情况，这个小小的 IO 因素。我们能对此做些什么呢？嗯，我不知道你们是否看过荷兰的足球迷，他们有著名的进行曲“向左，向左，向左。向左，向左？”

<details>
<summary>Original English</summary>

**Speaker 1**: um again, sorry. this is an engineer conference. let's look at this type io, and you don't have to understand it, but just see that there's a type theare called real world. yes, lean. this is a direct thing as a type called real world. and why is that because something of type io will mudate to the real world? so it warns you don't use this shit because it can make every versible side effects and like deleting your files, so solomon on hikes. and last year, disconference called an AI ent ent an allamb that's wrecking its environment in a loop. and i think he's a hero. i don't know if solo amon is here this year, but i think he should he deserves a round of a ploss because i think this is the right definition of an i agent. and by the way, this was one of the pictures that i had to robble to generate because it's clearly depics violence. and so it's kind of an unsafe, right? i have a picture that the big big violence. and so i we don't well, our agents have access to private data. they have interested content like the prompt ejections, and now we gave them tools. simon on versician caused this, the little try factor. and what can we do about this? well, um i don't know if you seen the dutch shocker fans, they have the famous march and days ic. do the left left left. do the left left?

</details>

<!-- chunk 51/54 -->

### 将计划重构为程序：实现数学上可证明安全的智能体计算

**Speaker 1**: 向右，向右，对吧？这实际上是解决这个问题的秘诀。荷兰队昨天被淘汰了，所以你得看我跳舞。但我们所做的，就是把这个 IO 向右推。现在你看到的是，Claude 的工具带向左移动了。当然，Claude 是一只可爱的小狗，对吧？因为它没有直接执行智能体循环，而是创建了一个计划，然后说：“这是执行智能体循环的计划。”然后 Bernie 会接手这个计划，我们来执行它，我们都信任 Bernie，对吧？Bernie 是个好人。好的。所以在这里展示一下。这就是我们正在做的，我们把智能体循环与智能体本身进行了“气隙隔离”。所以我们不让智能体在它运行之前就运行智能体循环。我们现在希望能够完全控制它。

<details>
<summary>Original English</summary>

**Speaker 1**: do the right right, right? this is actually the secret to solve this problem. the dutch team got eliminated yesterday. so you have to see me doing the dance, but all that we're doing is you 're pushing this io to the right to the right. and what you now see is that the tool belt of clolot goes to the left to the left, and certainly cllad is a nice puppy, right? because instead of executing the agenctic loop, it creates a plan and says, here is the plan to do the the genentic gloop. and now bernie will take that plan, and we will executed, and we all trust burniy. right? berney is a good guy. alright. so just do get to show it here. so in some that's what we're doing, we're air gapping the aggentic looloofrom the agent. so we don't let the agent run the agentic loop before the agent run it. we want to be able to jack it all right now.

</details>

**Speaker 1**: 问题是，如果你得到一个类型为 `IO a` 的值，那实际上是一个黑盒。Lean 手册上说，那是一个黑盒，你无法对它进行推理。所以即使 Claude 现在给了我们这个计划，我们也无法查看这个计划内部。Lean 不允许我们这样做。顺便说一句，这是另一张图片，对吧？它……那是在宣扬毒品使用和模型。让我来做。我是一个好老师。是的，我可以让它变成被禁止的图片。所以如果我们再看一下 Lean，你在这里看到的是，模型现在计算了一个答案，但它并没有计算答案，对吧？它创建了一个 `IO answer`。所以这是一个生成答案的计划。然后它创建了一个证明，证明这个计划是安全的。好的一点是，你可以在不运行智能体循环的情况下获得那个证明。但不幸的是，正如我所说，这个证明，如果它是某种 `IO` 类型的东西，那就没用了。该死，我们能对此做些什么呢？

<details>
<summary>Original English</summary>

**Speaker 1**: the problem is that if you get the value of type io of a, that's a really a black box, and the lean manual says, that is a black box, you cannot reason about it. so even though clad now gives us this plan, there's we cannot look into this plan. an doesn't allow us to do it. by the way. this is another picture, right? it. that's promotes drugs use and the model. let me do it. i'm a good teacker. yeah, i can just make it to forbidden pictures. so if we look in the lean, again, what you see here is that the model now compute an answer, but it doesn't compute the answer, right? it creates an io of answer. so this is a plan to generate the answer. and then it creates a proof that this that, that plan is safe. and the nice thing is here that you can get that, that proof without having to run the agentic c loop. but unfortunately, as i said, like this proof, if it's like something of type io, it's useless. i shit what can we do about that?

</details>

**Speaker 1**: 所以我继续推动你们前进。然后我们永远得不到最终答案，但这里还有一个技巧。你会看到这里的研究人员变得非常老练，不再是那些做蠢事的人，而是真正的人。比创建 `IO a` 类型的计划更好的做法是，创建一个代表 `IO a` 类型表达式的程序。这非常“元”，对吧？我不是指 Meta AI 的那个“元”。别想得太“元”，而是指“元”在……你知道，你懂我的意思。再说一次，对于签名来说是一小步，但对于安全性来说却是一大步。因为现在模型返回一个表达式，一个代表你计算的程序。如果你懂 Lisp 或 Scheme，你会认出这是我经常使用的技巧之一。但如果你懂 Lisp，这当然是你的第二天性。我没办法，不谈论单子（Monad）就不能做演讲。所以如果你问自己，这个表达式是什么？嗯，那只是一个单子，但它不仅仅是单子。它是一个自由单子（Free Monad）。自由单子是什么？它是一个失去了单子律的单子。

<details>
<summary>Original English</summary>

**Speaker 1**: so i keep going like moving you guys forward. and then we never get to the final answer, but there's one less trick. and you see the researchers here are becoming more much more sophisticated instead of the fatto do diones in the pnow there, like a real people. and what is better than than creating plplan of type io of a it's creating a program that's represents an expression of type io of a who that chounis very mata, right? i'm not matta in terms of meta AI. don't think there very meta, but and tta in the terms of like you like matter, you know, you know what i mean. and again, it's a small step for a signature, but a giant leap for safety. because now the model returns an expression, a program that resents your computation, if you know, linth or shshsharp well will recognize that this is one of the tricks that i always use. but if you know, list, this is, of course, second nature for you. and i cannot like, you know, have a talk without talking about monents. so if you ask yourself, what is this expression thing? well, that's just a moonat, but it's not just the monant. it's a free monant. where's a free monant? it's a monant that lost diydise.

</details>

**Speaker 1**: 现在，如果你看一下证明某物属性的签名，你会发现它接收一个返回答案的计算的表达式。如果你在大学里上过任何编译器课程，你就会知道对这些程序进行数据流分析、类型检查是微不足道的，对吧？所以现在我们安全了。我们安全到家了。我想提醒你，我们只需对这些表达式、这些程序进行静态分析，就能解决驱动问题。好的，这是我将向你们展示的最后一段代码，因为我快没时间了。但只是想向你们展示，你现在有了一个用于这种语言的简单归纳递归解释器，并且你有一个简单的归纳证明，模型可以生成这些证明。

<details>
<summary>Original English</summary>

**Speaker 1**: and now if you look at the the signature of property to proof that something and say, if you see that it takes an expression of a competition that returns an answer. and if you have taken any compiler course in college, you know that it's trivial to do data a low analysis, type checking and your own programs, right? so now we're safe. we are home safe and definitely wanted to remind you that we can solve the drive a problem just by doing int analysis on these expression on these programs. okay, this is the last gode that will show you because i'm running out of time. but just what to show you here that you know, you now have a simple inductive rigds of interpreter for this language, and you have a simple inductive proof, and the models can generate these proofs.

</details>

**Speaker 1**: 嗯，所以来回顾一下今天的内容。是的，总结一下。我们所做的是，从可能给出错误答案的、不受约束的LLM，到对齐的LLM。然后我们看到了工具是如何反应的。然后我们通过延迟执行解决了这个问题。也就是通过将LLM与工具进行“气隙隔离”。然后真正的解决方案是将计划重构为一个程序。一个我们可以证明是安全的程序。现在你可能会说，Eric，你是个天才。不。我的大脑只有花生那么大。这被称为“证明携带代码”（Proof-Carrying Code），是90年代的学者发明的。我只是在更高层次上窃取了这个想法。如果你没看懂代码，记住：三点：智能体是危险的，需要被证明是安全的。所以，除非你能绝对证明某个行为是安全的，否则永远不要让智能体去做。而且智能体生成的语言不是为普通用户设计的。不懂自由单子（Free Monad）？没关系。消费它的是机器。生成它的是机器。处理它的是机器。所以我们应该停止为人类设计语言。这基本上只需要编程101的知识。不。我们讲完了吗？好的？就是这样。故事结束了。

<details>
<summary>Original English</summary>

**Speaker 1**: 嗯, so too, um recapittoday. yeah, summarize, what we did is we went from unhinged allaams that was like, you know, could give bad answers to once that were aligned, then we saw how tools react ted, then we solve that by differing execution. so by air gapping, the the lamm from the tools and then the real solution was to refight the plan into a program. and the program that we could prove to be safe. now you would say, eric or 're a genius, no. and my brain is the size of a peanut. this is something that's called to proof carrying code. and it was invented by academics in the nineteen thousand ty. and and i'm just stealing it alright at the higher level, if you didn't understand the code, three point agents are dangerous and they'll proven safe. so if you never ever let your agents do something, unless you can absolutely prove that a safe and the language that this agents generated does not designed normal users, don't understand free monoment dodoes. it matter. it's a machine that consumes it. it's a machine that generates. it's a machine that proceits. so we should stop designing languages for humans, and it's all basic only requires programming one, no. and did we go? alright? that's it. um the end of the story.

</details>

**Speaker 1**: 如果你好奇想尝试一下，一群学者，特别是哈佛的I'm in，已经实现了这个。它在他们自己的GitHub上。它使用了一种略有不同的语言。我使用的也是一种与Free Monad略有不同的语言。但想法是一样的。语言重要吗？嗯，重要的是原则。所以希望今晚你们学到了，实际上有可能拥有数学上可证明安全的智能体计算。而且它只需要非常基础的类型系统和编程语言机制。非常感谢。

<details>
<summary>Original English</summary>

**Speaker 1**: if you're curious to play with this, a bunch of academics and particular another, i'm in from harvard have implemented this. it's their own getop. it uses a slightly different language. but what i use it use is also a slightly different language than freeonage ts, then the ideas, the same the language. does it matters? it's the 嗯嗯 the principal that matter. so hopefully, you've learned tonight that it is actually possible to have mathematically proven safe agentic compute. and it only requires very elementary type systems and programming language. machininery. thank you so much.

</details>

**Speaker 3**: 啦啦啦啦啦啦啦啦。

<details>
<summary>Original English</summary>

**Speaker 3**: 啦啦啦啦啦啦啦啦.

</details>

### 主题演讲：Cursor 的递归模型改进

**Speaker 4**: 请大家欢迎上台，Cursor 的机器学习工程师，模型行为专家，Lee Robinson。

<details>
<summary>Original English</summary>

**Speaker 4**: please welcome to the stage. the machine learning engineer model behavior at cursor lee robinson.

</details>

**Speaker 0**: 嗯，好的，各位。我很高兴来到这里，很高兴回到 AI Engineer 大会，并谈谈我们在 Cursor 是如何训练模型的。谈谈我们如何训练模型，以及模型如何学会自我训练，或者说递归模型改进。所以，我们在 Cursor 的目标是构建尽可能最好的 AI 模型，这听起来很合理。你可能听说过这个公式：如果我们给模型更多的计算资源，我们就能得到更好的模型。我认为这是一个有用的、简化的问题描述，但我今天想深入探讨几个层次，谈谈训练这些模型所涉及的所有不同部分。

<details>
<summary>Original English</summary>

**Speaker 0**: 嗯, alright, everyone. i'm excited to be here excited to be back at ai engineer and talk a little bit about how our training models at curor. so how we trained the models and also how the model learns to train itself or a recursive model improvement. so our goal like cursor is to build the best possible ai models, which might make sense. you might have heard of this equation of if we just give the models more compute, we can get a better model out. and i think this is a helpful, simple vacation of the problem, but i want to actually click in a few layers deeper in the talk today and talk about all the different pieces that go into training these models.

</details>

**Speaker 0**: 所以我们可以考虑这个循环。我们将模型部署到世界中，然后当你们使用模型时，我们会得到反馈，哪些地方做得好，哪些地方可以改进。我们利用这些反馈来扩展和改进下一轮训练的数据。同时，我们也会增加模型的计算量，并全面扩大训练规模，以创建一个新模型。这是一个可以不断重复的循环。然而，如果你看到我那只有用的海龟或兔子在底部慢慢移动，对吧，它非常慢，这将是一个串行过程。而且你一次只能进行一次大规模训练。所以我们想让它更快一些。但我实际上会再深入一层，添加更多细节。实际上有两个循环：外循环和内循环。在外循环中，我们有反馈进来，但我们也有像在线指标这样的数据。所以运行 A/B 测试，观察用户偏好模型的哪个检查点，这些信息会流入，希望能帮助我们制作更高质量的评估，确保我们获得模型应有的正确行为，并且能够为模型创建更困难的问题，然后我们在训练过程中塑造我们想要获得的奖励。所以我们也想加速那个内循环。

<details>
<summary>Original English</summary>

**Speaker 0**: so we can think about this loop. we put a model up to the world, and then we get feedback from you all when you use the model, what goes well or places we can improve. we use that to scale and improve the data that we do for the next round of training. and we also then increase them out a compute and scale up training over all to make a new model. and this is a loop that can just go over and over again. however, if you see my helpeful sil or a turtle to bunny metre down in the bottom, right, it's pretty slow is is going to be a serial process. and you can only do and this incense one big run at the time. so we want to make this a little bit faster, but i'll actually go another layer deeper and add some more color here. there's actually two loops, the outer loop and interloop on the other loop, we have the feedback coming in, but we also have data like online metrics. so running ab tests and seeing what users prefer the feecheck point of a model that's going to then flow into, hopefully making better high quality evals that helping sure were getting the right behaviors we want out of the model. and also being able to create much more difficult problems for the models to try to solve where we then kind of shape the rewards that we want to get during training. so we want to climb that interloop as well.

</details>

**Speaker 0**: 我们在 Cursor 大规模训练模型已经大约一年了，我想谈谈我们目前取得的一些进展。我们在五月发布了 Composer 2.5，它现在是 Cursor 中最受欢迎的模型，这很令人兴奋。我们通过生成更多的 RL 环境、尝试一些新的学习方法，以及为模型创建更宏大的问题，大大扩展了这里的训练规模。到目前为止，结果非常有希望。就像我提到的，这对我们来说仍然是一个新的努力。机器学习从一开始就融入了 Cursor 的血液，当时我们正在为 Tab 或代码补全等任务训练更专门的模型。但在过去的一年里，我们真正加快了步伐，组建了一个志在训练最先进模型的团队，在过去的两个月里，我们取得了相当不错的进展。对对，人们现在喜欢 Composer。我认为这是因为它既快速又相当智能，而且成本效益高。正如我们今天从其他演讲者那里听到的，我认为目前市场上确实存在这类模型的空间。

<details>
<summary>Original English</summary>

**Speaker 0**: we have been training models for about a year at the large scale at cursor, and i want to talk about some of our progress so far. so we put out composer two point five in may, and it's now the most popular model and curser, which is exciting. and we scale up training here quite a bit by generating more are il environments, trying out some new methods for learning and also just making more ambitious problems for the models to solve. and the results have been pretty promising so far. like i mentioned, this is still a new effort for us. ml has really been in the blood of cursor since the start, where we were training more specialized models for things like tab or code hotto complete. but really, in the past year, we've sabfed up and build team with ambitions to train in know set of the art models, and we made some pretty good progress just in last two a months. 对对, people like composer right now. i think because it is both fast and pretty smart and also cost effective. and as we heerard from other speakers today, i think there is a space in the market right now for that type of model.

</details>

<!-- chunk 52/54 -->

### 从用户反馈到模型训练：Cursor 的迭代循环

**Speaker 0**: 除了拥有世界上最智能的模型之外，我们认为拥有这两类东西的良好选择也很重要。所以，我们认为 Composer 在这方面很好地满足了市场需求。

<details>
<summary>Original English</summary>

**Speaker 0**: in addition to also having the most intelligent models in the world, and we think is important to have a good selection of both of these type of things. So Composer, we think is serving a good niche here.

</details>

**Speaker 2**: 对对对。

<details>
<summary>Original English</summary>

**Speaker 2**: Right, right, right.

</details>

**Speaker 0**: 当我们发布它的时候，我们自己对一些公开评估的结果印象相当深刻。它的表现比我们在 Artificial Analysis 上预期的要好一些。不过，这只是个相当温和的提升。然而，我们发现了许多行为，我们非常希望在下一个版本的模型中加以改进。具体来说，我们想要一个更大、更智能的模型。我们希望控制训练的每一个方面。所以，理想情况下，是从头开始进行完整的预训练，而不是像之前那样使用开源的 Kimi 模型。我们希望注入新的数据，使模型不仅在编码方面，而且在更多方面，成为一个更通用的模型，表现出色。然后，还要扩大训练过程的每个部分：更多的数据、更多的计算资源，并尽可能推动我们的强化学习。

<details>
<summary>Original English</summary>

**Speaker 0**: and when we released it, we were honestly pretty impressed with some of the public evals. It did a little better than we expected on Artificial Analysis. It was a pretty modest jump. However, there were a lot of behaviors that we found that we really wanted to improve the next version of the model. Notably, we wanted to have a much bigger and smarter model. We wanted to control every aspect of training. So ideally, doing a full pre-trained from scratch versus the previous open source space of Kimi that we were using. We wanted to infuse new data so that we can make the model great outside of more things in just coding, but more the general model. And then also just scale up every part of the training process, more data, more compute and really pushing our RL as far as we can.

</details>

**Speaker 0**: 所以首先，我谈到了改进外部循环，然后我们会深入探讨内部循环。如果你有一段时间没用过 Cursor 了，你可能还认为它是一个带有 Tab 自动补全功能的 IDE。但实际上，如今我们绝大部分收入都来自 Agent 的使用。这意味着 Cursor 内部的所有数据也都来自 Agent 的使用。我们用这些数据来训练更好的模型。举个例子，在外部方面，我们有两种不同的反馈渠道：当你在使用产品时，可以对不同的回复点赞或点踩来提供反馈。我们利用这些反馈来分类，例如，Composer 在哪些地方可能做得不够好，我们希望在未来的版本中改进。在内部方面，我们自己是模型和产品的重度用户，我们非常挑剔，希望确保使用的是好模型。当然，我们整天都在使用它们。所以，我们很好地结合了人工报告和自动化报告，并通过多种方式试图从模型中获得最佳行为。如果我们一次又一次地这样做，就能向世界推出更好的模型。

<details>
<summary>Original English</summary>

**Speaker 0**: So first somewhat, I talked about improving the outer loop and then will drill in the inner loop. If you haven't used Cursor in a while, you might think about it as this IDE or tab autocomplete. And in reality, the vast vast majority of our revenue today comes from agent usage. And that means that all of the data inside of Cursor is also coming from agent usage. We use that to train better models. So for example, we kind of have two different buckets of feedback on the external side, when you're using the product, you can thumbs up or thumbs down different responses and get feedback. And we use that to then classify places where, for example, Composer's maybe doesn't do as good of a job. And we want to improve that for future versions. And then also on the internal side where heavy dogfooders of our models in our products, we're very critical and want to make sure we're using good models. And we, of course, use them all day. So we have a good mix of manual orts automated reports internally. And just lots of ways, we're trying to get the best behaviors out of the model. And if we do that over and over and over again, we can get better models out to the world.

</details>

**Speaker 0**: 但真正能让我们实现巨大加速的地方，是改进那个内部循环。所以，我们再聚焦回来。我们拥有这些高质量的评估基准，我们拥有这些非常困难的训练任务，我们希望尽可能快地攻克这些评估基准。这样我们就能知道，当我们创建模型的新检查点时，我们确实在我们想要衡量的方面取得了进展。

<details>
<summary>Original English</summary>

**Speaker 0**: But really the place where we can make massive speed ups is improving that inner loop. So just to zoom back in and that again, we have these high quality evals. We have these very difficult training tasks, and we want to climb these evals as quickly as possible. So that we know if we make a new checkpoint of the model, we're actually making progress on the things that we want to measure.

</details>

**Speaker 0**: 好的好的好的。

<details>
<summary>Original English</summary>

**Speaker 0**: Right, right, right.

</details>

**Speaker 0**: 所以，举个例子，我们引入的一些评估基准已经包含了像这样的任务：理解当你可能包含了五十个文件时，你的真实意图是什么——这对模型来说有点困难，需要弄清楚你的实际意图；或者试图找出何时应该追问用户以澄清问题，何时应该相信他们的判断之间的界限。用户说“不，我确实想这么做”，这里面有很多细微的差别，人们有不同的偏好。所以，很多这些评估基准都试图塑造这些不同的行为，并模拟作为一名软件工程师的感觉。我们要求模型做非常雄心勃勃的事情，比如，“嘿，我们刚开了个会。你能去阅读所有的数据、日志、Slack 和 Notion，然后得出和我们一样的结论或修复方案吗？”很多模型在这方面做得并不好。这支撑了我们基于这些软件工程任务创建的许多评估基准。

<details>
<summary>Original English</summary>

**Speaker 0**: So for example, some of the evals that we have introduced have already had things like understanding what you really meant when you have included maybe fifty scale files, it gets kind of hard for the models to figure out your actual intent or trying to figure out the line between when you push back and ask the user to clarify a question verses when you trust their judgment. And they said, no, I really wanted to do this. There's a lot of fine line and people have different preferences. So a lot of these evals are trying to shape a lot of those different behaviors and also model what it feels like to be a software engineer. We asked the models to do really ambitious things like, hey, we just had this eve. Could you have actually went and read through all the data og logs, read through Slack, read through Notion and came to the same conclusion or the same fix that we did. Um and a lot of models are just not very good at this that, and that um backs, a lot of evals that we create based on these soft engineering tasks.

</details>

**Speaker 2**: 对对对。

<details>
<summary>Original English</summary>

**Speaker 2**: Right, right, right.

</details>

**Speaker 0**: 现在，随着模型变得更智能，它们也找到了非常有创意的方法来“黑掉”评估基准。所以，在我们为模型新版本进行训练时，我们也注意到出现了一些有趣的奖励黑客行为。模型学会了如何直接回溯历史，找出是否存在解决方案或部分解决方案；它们找到了很好的方法去上网，如果有一个公开的评估基准，它们会查看是否有该评估基准的任何分支，从而可以查找结果。这影响了我们的模型以及其他模型。所以我们在这里做了一点研究，发现如果我们对衡量公开评估基准的方式做一些小的改变，我们报告的分数就会发生相当显著的变化。所以首先，我们会在开始时删除 git 历史，在结束时再恢复。这会影响运行结果。然后，我们还可以设置网络白名单，或者对 Agent 可以访问和通信的网站进行一些基本控制。我认为这对于公开评估基准很有帮助，因为人们通常用它们来校准一个模型发布时是否优秀。你知道，你会看到那张包含所有基准测试分数的大图表，但这并不能真正测试使用这些模型时的真实感受。实际上，你可以访问互联网，你可以用这些模型在互联网上做任何你想做的事情。所以你肯定在使用它。所以，你希望能够测试模型的真实能力，这就是我们拥有 Cursor 评估基准的原因。我们有一个私有评估集，主要由代码库中发生的事情组成，这些是从评估基准中保留出来的。这样我们就能确保模型没有在这些数据上训练过，并且它基于那些真实世界的工程任务。

<details>
<summary>Original English</summary>

**Speaker 0**: Now, as the models get smarter, they also find very creative ways to hack the evals. So as we've been training for a new version of our model, we also notice there was some interesting reward hacking going on. The model learned how to just go back in the history and figure out if there was a solution or a part of a solution, they figured out good ways to go online. And if there was a public eval to see if there was a fork of the eval anywhere, they could look up the results from. And this affected our models as well as other models. So we did a little research here and found that if we did just a couple small changes on measuring public evals, we could have a pretty noticeable change in the scores that were reported. So first off, we would delete the git history at the start. We could restore at the end. So that would affect the run. And then also, we can have a network allowlist or just some basic controls on the sites that the agent can go and talk to. And I think this is helpful for public evals, which often are the things people are using to calibrate whether a model is good when it gets released. You know, you see that big chart of all the benchmark numbers, but this isn't really true tests of what it feels like to use these models. Like in reality, you have access to the internet, and that's why whatever you want in the internet with these models. So you're definitely using it. So you want to be able to test the true capabilities of the models, and that's why we have Cursor evals. You have a private eval set that is mostly made up of things that happen in a codebase, which is held out from the evals. So we ensure that the models aren't trained on it, and it's based on those real world engineering tasks.

</details>

**Speaker 0**: 现在，攻克那个内部循环的另一部分，是尝试为模型创造非常非常困难的问题。随着模型变得更好，你可能已经注意到，如果你观察一个评估基准，所有模型的得分都在 90% 左右，那么可能是时候淘汰那个评估基准，并尝试更困难的任务了。这些评估基准的半衰期会随着模型变得更智能而缩短。要做到这一点，需要很多条件。它需要一定的研究品味，来判断这些问题应该是什么样的。它需要大量的计算资源，这样你才能尝试许多不同的想法。有些想法会成功，有些则不会。而且这里存在与时间的赛跑。所以你想尽可能多地并行尝试。举个例子来说明这类问题。比如说，在左边，每一个圆点代表代码库中的一个文件，在底部是测试。你可以做的一件事是，为一个非常雄心勃勃的应用或任务生成一个非常复杂的应用或环境，然后你可以删除其中的一部分。你可以删除一个功能，你可以删除文件，然后测试就会失败。然后你可以让这些模型去，基本上以它认为合适的方式，重新实现那个功能。它有一个非常可验证的目标，即所有测试都通过，以便在最后获得一些奖励。这个方法效果很好，让我们能够为前沿模型规模化地创造这些有趣的问题。

<details>
<summary>Original English</summary>

**Speaker 0**: Now, another part of climbing that inner loop is trying to make very, very difficult problems for the models to solve. As the models get better, you might have noticed. If you're looking in an eval and all the models are scoring like ninety percent, probably time to retire that eval and try to get something more difficult. And the half-life of those evals will go down as models get smarter. And to do this, it requires a lot of things. It requires some amount of research taste, and what these problems should be. It requires a lot of compute. So you can try a lot of different ideas. Some of them are going to work. Some of them are not going to work, and there's a race against the clock here. So you want to try as many in parallel as you can. Just to put an example to this of one of those type of problems. Let's say that on the left, for example, you have each one of those dots is representing files in a code base. And one on the bottom you have the tests. One thing you can do is generate a very complex application or environment for a very ambitious application or task, and then you can delete part of it. You can delete a feature, you can delete files, and the test will then fail. And then you can ask these models to go and basically figure out however it wants to reimplement that feature, and it has a very verifiable goal of all the test passing to be able to get some reward back at the end. And this actually works out pretty well and has allowed us to scale making these interesting problems for the frontier models to solve.

</details>

**Speaker 0**: 此外，我们还发现了一些新的学习方法，我个人认为非常有趣。第一个是，你可以教模型自我指导。例如，如果你考虑一个强化学习 rollout 或与 Agent 的一次对话，这可能有几十万个 token。如果你试图在最后评判模型在哪个地方做出了正确或错误的决定，这有点困难，对吧？你有所有这些工具调用、思考块。要弄清楚将功劳归因于哪个根本问题是非常困难的。所以我们越精确越好。你知道，是哪个工具调用或思考块？这非常困难。我们为改进这个过程所做的一件事叫做“文本反馈”。我们希望聚焦于那个 rollout 的某个特定部分。理想情况下，我们可以给模型一个提示或轻推一下，“嘿，顺便说一下，你可以这样改进”，然后再次查看概率，提高我们想要的行为的概率，降低我们不想要的行为的概率。例如，在左边，你有一个学生案例，它进行了一次 rollout，尝试了一个工具调用，但工具调用失败了。它本应知道这个工具是可用的，但这次它决定不使用。然后我们可以使用一个教师模型。我们可以使用同一个模型，但包含这个提示，我们说，“嘿，提醒一下，你有所有这些工具可用。”然后，就像我提到的，我们可以提高概率，从而得到我们想要的行为。这个例子是关于工具调用的，但我们几乎可以将其用于任何事情。我们可以用它来改变风格，我们可以用它来获得任何我们想要在强化学习期间影响模型的行为。这对我们来说被证明是非常有价值的。

<details>
<summary>Original English</summary>

**Speaker 0**: Additionally, we have found some new learning methods, which I personally think are really interesting. The first one is you can teach the model to kind of coach itself. So for example, if you think about an RL rollout or a conversation within an agent, this can be hundreds of thousands of tokens. And if you think about trying to grade at the end of this, where the model made a right decision or a wrong decision, it's kind of hard, right? You have all these tool calls, you thinking blocks. It's pretty hard to figure out where to assign that credit to the root issue. So the more precise we can be the better. You know, was it one of the tool calls or a thinking block? It's pretty hard. And one thing that we've done to improve this process is something called textual feedback. So we want to zoom in on one specific part of that rollout. And ideally we can hint or kind of nudge to the model. Hey, by the way, the way you could improve and then look at the probability again, and judge up the ones we want or downweight the ones we don't. Again, for example, on the left, you have this student case where you have a rollout, and it tries a tool call. And the tool call fails, it should have known that this tool was there, but it just decided not to work for this time. We can then use a teacher. We can use the same model, but we include this hint, and we say, hey, as a reminder, you have all of these tools available. And then we like I mentioned, we can just upvote or upweight the probabilities such that we can get the behaviors that we want. And this example is with the tool calling, but we can really use this for anything. We can use this for making style changes. We can use this to get any behavior. We want to influence the models during RL, and this is proven to be very valuable for us.

</details>

**Speaker 0**: 现在，我们如何扩展这些循环，包括内部和外部循环，也归结为扩展计算资源。我们在三月份宣布，我们正在与 CoreWeave 合作，以获得更多的计算资源，这使我们能够从头开始训练非常大的模型，不仅仅是产品模型。

<details>
<summary>Original English</summary>

**Speaker 0**: Now how we scale these loops, both the inner and outer loops also comes down to scaling out compute. We announced back in March that we are partnering with CoreWeave to get access to a lot more compute and that allows us to train very large models from scratch, not only the product.

</details>

<!-- chunk 53/54 -->

### 从超级计算机到芯片：全栈优势与算力分配

**Speaker 0**: 但同样也包括从模型到超级计算机的各个层面。

<details>
<summary>Original English</summary>

**Speaker 0**: but also the models down to the supercomputers.

</details>

**Speaker 0**: 就是那些我们用 Glosses 训练模型的数据中心，并且越来越多地，也包括使用 Terifab 的芯片。

<details>
<summary>Original English</summary>

**Speaker 0**: are the data centers where we're training these models with glosses and then increasingly to the chips as well with terifab.

</details>

**Speaker 0**: 这让你能够利用整个技术栈，做出一些非常有趣的事情。

<details>
<summary>Original English</summary>

**Speaker 0**: and that it just allows you to duce prepretty interesting things in taking advantage of that full stack.

</details>

**Speaker 0**: 如果你还没看过 Glosses，我个人觉得那真的很有意思。

<details>
<summary>Original English</summary>

**Speaker 0**: if you haven't seen glosses, i think it's really interesting. personally.

</details>

**Speaker 0**: 他们能够在 122 天内用 1000 个 GPU 搭建出这台超级计算机，然后在 92 天内又增加了另外 1000 个 GPU。

<details>
<summary>Original English</summary>

**Speaker 0**: they're able to train ah they are able to build out this supercomputer in one hundred and twenty two days for one thousand gp u, and then added another hundred hundred gp u in ninety two days.

</details>

**Speaker 0**: 所以非常令人印象深刻。他们为了完成这个，不得不做一些非常有创意的事情，比如接管一个旧工厂。

<details>
<summary>Original English</summary>

**Speaker 0**: so very impressive. i had to do some pretty creative things to get this done and kind of take over this old factor.

</details>

**Speaker 0**: 在孟菲斯。这展示了他们能够非常快速地建立起这些数据中心，这当然对我们的模型训练工作非常有利。

<details>
<summary>Original English</summary>

**Speaker 0**: and in menmpice. and it's kind of shown they can stand up these data centors really quick, which is, of course, very for for our model training efforts.

</details>

**Speaker 0**: 至于 Terifab，我认为他们正在构建自己的芯片，这一点也非常有趣。我的意思是，为了让你理解这个芯片的规模，我们想想这个物理结构有多大。我知道你们都在想，它大概有 100 个 Buc-ee's 那么大。我来自南方，你知道，我们爱 Buc-ee's。即使不是南方人，我也爱 Buc-ee's。这就像是南方的皇冠明珠，顶级的加油站。它包含了很多东西，但这只是让你对它的规模有个概念。

<details>
<summary>Original English</summary>

**Speaker 0**: and for terarfab. i think it's also very interesting that they're building their own chips. i mean, to put the size of this into perspective. we just think about how large this physical structure is. i know you're all thinking it. it's like the size of a hundred buckies, which it's from my force from the south. you know, we love bucks ies, not even from the south. and i love buckies. this is like the crown drul of the south, the premium gas station as station. it's a lot of stuff, but that just puts it into perspective, the size.

</details>

**Speaker 0**: 所以回到一开始的那个等式：投入更多算力，你就能得到更好的模型。我认为有时很难理解，这些算力到底是做什么的？你实际上把这些算力用在了哪里？假设你有一大堆计算资源，你拿它做什么？我认为，逐步了解几件事情会很有帮助。当然，首先是实际向用户提供模型服务，但同样也包括在内部提供不同的检查点。你在运行不同的 A/B 测试。你在尝试模型的不同变体。还有实际的训练过程本身，但也包括从预训练到后训练再到强化学习的各个子部分。然后，你还要训练这些衍生模型，用于处理流程中的部分工作，比如我们稍后会谈到的内部循环。你还有数据生成和奖励生成。所以，要创建那些我提到的、真正有挑战性的问题，或者当你进行评估时，试图创建那些用于判断是否成功的评分标准，并给出一个分数。然后实际去评判这些分数。嗯，你还有评估本身。理想情况下，对于模型的每一个新检查点，你都希望持续运行评估，看看在你衡量的那些方面是否有改进。同时，还要一直开发新的评估方法，就像我提到的，这些评估方法要随着模型变聪明而不断改进，你需要持续投入来让它们变得更好。嗯，还有研究本身。理想情况下，你希望解放你的研究团队，让他们能够调整参数、尝试大胆的想法、实验新事物，以及进行消融实验。所有这些都需要算力，并且需要你在某个地方进行分配。

<details>
<summary>Original English</summary>

**Speaker 0**: so going back to this equation at the start, more compute in, you get a better model out. i think it's sometimes hard to understand what does that computer even do? where do you actually put that compute? let's you have access to a bunch of mops, like what do i do with it? and i think it's helpful just to step through a few of the things, of course, first, you have actually serving the model to in users, but also you're serving up different checkpoints internally. you're running different AB tests. you're trying different variations of the model. you have the actual training process itself, but also the sub pieces from pretraining to bid training to rl. and then also, you're then training these derivative dels ls, do do parts of the proprocess clilimbing the interloop, which we'll talk about here in the second. you have the data generation. and the reward generation. so creating those really ambitious problems that i talked about, or when you're doing evalls trying to create these rurubricks for whether it was successful or not and give it some grade. and then actually judging those scores. um you also have the eballs themselves, ideally on every new checkpoint of the model you want to be continuously running evalls to see if you're improving in the places that you're measuring. and as well as just developing new evls ls all the time, like i mentioned, the the tough life with these emails as models to get smarter, you need to be really continuously investing in making these better. um and there's just the research itself. ideally, you want to free up your team of researchers to be able to tweet the nobs to try ambitious ideas experiment with new things as well as you side runs. and this all is compute that needs to be you allocated for somewhere.

</details>

**Speaker 0**: 嗯，但这最终会变成什么样子呢？理想情况下，你可以达到这样一种状态：同时进行多个大型训练运行，研究人员不受阻碍，他们可以去尝试研究。而你仍然在为这个核心飞轮做出贡献。如果你做到了这一点，并且我们重新审视我们的速度计和底部，对吧，你开始达到一个点，你得到了一些类似递归式自我改进的东西，模型改进的速度要快得多，快得多。那么下一个瓶颈就变成了：你如何扩展那些实际训练模型的人员？你如何自动化机器学习或研究中更单调的部分，以便你能将这些有用的模型推向世界？这就是为什么我认为事情开始变得真正有趣。

<details>
<summary>Original English</summary>

**Speaker 0**: 嗯, but what that ultimately turns into is ideally, you can get in the state where you have multiple large training runs happening at the same time where the researchers are unblocked. and they can go try the research. and you're still kind of contributing back to this core fly wheel. and if you do that and we revisit our speemeter and bottom, right, you're starting to get to a point where you're getting something that's like. rs, i recuse ve model and improvement here where the models are improving much, much fast, sir. then the bottom neit becomes, how do you scale the folks actually train the models? how can you automate the more monotinous parts of machine learning or research so that you could get these useful models out into the world? and this is why i think it starts to get really interesting.

</details>

### 模型即马里奥：工具与上下文的力量

**Speaker 0**: 对。如果你把模型想象成马里奥，如果你给它一些工具，突然间它就更像超级马里奥了。如果你给它很好的上下文，关于你组织的一切，你工作的所有地方，你连接到所有不同的工具，那个上下文，有点像把它变成了火焰马里奥或者超级火焰马里奥？为了进一步证明这一点并补充一些例子，我认为，对于工具来说，很多都是显而易见的。模型可以用工具写代码。它们可以运行 shell 命令，可以在网上查东西。但我认为，即使是这些原始版本的内存，比如写文件，这最后三个，我认为它们正开始变得非常流行和有用，那就是模型和工具应该能够像你一样使用电脑。它不必只局限在你的 GUI 里，或者你的 CLI 里，它应该能够控制你电脑的每一个部分。

<details>
<summary>Original English</summary>

**Speaker 0**: 对, if you think about the model as mario, if you give it some tools, all the sudden you're more like a supermario. and if you give it great context, everything about your organization, all the places that you work, you connected to all your different tools, that context, kind of turns it into the firemario or the superfire mario? and just as kind of further prove this point and add a few examples here, i think, for tools, a lot of these are pretty obvious. the models can write code with with the harness. they can you run shocuman as they can look things up on the web. but i think increasingly, even with these primitive versions of memory, like writing files, these last three, i think you're just starting to become really popular and more useful, which is the models and the harnesses should be able to use a computer exactly like you would. it doesn't need m be be just inside of your gooe, or your c alii should be able to control every part of your computer.

</details>

**Speaker 0**: 对，你作为人类，在 Slack 上或者在你的工具上，基本上就是在脑子里订阅了 Slack 的讨论串，这样你就能跟进更新。理想情况下，你希望模型能够直接跟进阅读，然后在需要的时候提醒你。就像我们有代码库来存储代码一样，随着这些模型为我们做越来越多的工作，我们越来越需要一个类似“自我版 Dropbox”的东西，比如，你把这些东西存在哪里？比如，文档，对吧？你可以把它放在代码里，我想，但我认为这里有一个越来越新的机会。

<details>
<summary>Original English</summary>

**Speaker 0**: 对 you as a human on slack or on your tool is basically subscribing to slack threats in your head so that you can follow them for updates. ideally, you kind of want the models to just follow with read and then pink you, if it need ds. and just just like we have code bases that store the code increasingly, as these models do more work for us. and kind of need like a drop box for the ourselves, like, where do you store this? like decks, right? you could put that in code, i guess, but i think there's an increasingly new opportunity here.

</details>

**Speaker 0**: 然后对于上下文，当然，你有所有不同的地方可以连接，比如 MCP、Slack、非线性数据、Datadog，嗯，还有代码库本身。但我认为最后两个真的很有趣，那就是我们越来越多地发现，有一个人类与一个智能体团队一起工作，然后这些智能体可以开始与其他智能体合作。这听起来有点奇怪，但我认为这将是未来六个月的一个大趋势。

<details>
<summary>Original English</summary>

**Speaker 0**: and and then for context, of course, you have all the different places you can hook up with mcps slack and nollinear data, dog said, uah and the code base itself. but i think he's last to are really interesting, which is increasingly we find that you have a human working with the team of agents, and then the agents can start working with the other agents. it's a little et a, but i think this will be a big trend in the next six months.

</details>

**Speaker 0**: 我给你举个例子。我们创建了这些工具和系统，研究人员可以直接从 Slack 运行实验。我们希望避免那种人类成为瓶颈，需要启动、审查和照看运行的状态。我们实际上有一个完整的团队，专门负责自动化研究工作中那些不能解放研究人员时间、让他们去研究大胆想法的部分。团队中的每个人都可以访问这个计算集群，他们基本上可以直接从 Slack 训练模型。团队中有几个人已经把这个做得非常深入，他们拥有这些智能体系统，可以为他们做大量工作。也许他们想去创建一堆非常困难的问题让模型去尝试解决，或者他们想基于一些好主意创建一大堆新的评估方法，他们只想让模型自己去运行，然后工作一段时间。但如果出了问题，如果基础设施出故障了，或者某个地方出现了小问题，模型可以在 Slack 上给他们发消息，或者直接呼叫他们，说，嘿，这非常重要。你不想因为基础设施宕机而损失六个小时，你应该现在就去检查一下。这种人与智能体的协调，我认为，才刚刚开始被摸索出来，这将是一个日益增长的趋势。

<details>
<summary>Original English</summary>

**Speaker 0**: just you kind of put an example to this. we've created these tools in these systems where researchers can run experiments directly from slack. we want to avoid this states of being bottenect on humans, launching and reviewing in babysitting runs. and we actually have an entire team just working on automating every part of the research work that isn't, you know, isn't freeing up the sesearchers time to work on the ambibious ous ideas. every perperson on ammteam gets access to this fleet of a, they can basically train models directly from slack. and what a few people on the team of taken this very far where they have these agent systems that can go and do a lot of work for them. maybe they want to go create a bunch of very difficult problems for the models to uh try and solve, or they want to create a whole bunch of new evalils based on some good ideas that they have, and they just want to let the models cook and go work for a while. but if something gets wrong, if the infrastructure goes thethere's some blip somewhere, the model can message them on slag or just page them directly and say, hey, this is really important. you don't want to lose six hours because your info rs down like you should go check this out right now. and this like human to agent coordination, i think, is just starting to be figured out, and it will be an increasing trend.

</details>

### 递归式自我改进：模型训练下一代模型

**Speaker 0**: 最后一点是，模型正在学习训练下一个模型。这有点难以理解，我喜欢这样想：每次你发布这个智能的新版本，你就可以创建或提炼出这些衍生版本，用于加速训练过程的其他部分，包括内部循环和外部循环。所以，当你尝试进行评估时，例如，你有不同的模型来进行评判，你也有你的奖励模型。所以，当你让顶层模型变得更聪明时，它实际上会改进整个系统。如果你想想我之前展示的那个多训练运行的图表，我要在这里加一个新的计量表，那就是从大脑到银河大脑的计量表，或者说智能计量表。你系统中最聪明的模型在这里是一个瓶颈。如果最聪明的模型创造了那些衍生模型，那么当你改进那个最聪明的模型时，你实际上可以让每一个循环都变得更好、更好。你可以提高智能的底线。这就是你开始实现那种递归式自我改进的方式，这种模型一直在为你改进，特别是当我们带来越来越多的算力时。我认为这将真正帮助我们扩展模型工作，并希望能为你们所有人创造出更有用的模型。

<details>
<summary>Original English</summary>

**Speaker 0**: the last bit here is that the model is learning to train the next model, and it's a little hard to wrap your brain around the way i like to think about it is every time you release a new version of this intelligence, then you can create or distill these derivtive versions that you use to speed up other parts of the training process, both the interloop in the other loop. so when you're trying to do your evels, for example, you have different models for doing the judging and you have your reward models as well. so when you make the top level model model smarter, it actually improves the whole system. if you think about the multiple training runs diagram, i showed you going to throw on a a new metre here, which is the brain to galaxy brain meter or the intelligence meader. you are a bottm eck here on the smartest model in your system. and if the smardest model then creathose dribit models, when you can improve that, you can actually make every single one of these loops much, much better. and you can raise the kind of floor the inteintelgence ence. and this is how you start to get to you improprolike this recursive self improvement this model that is just improving all the time on your behalf, and especially as we bring more and more compute online. i think this is really going to help us scale our model efforts and hopefully make even more useful models for you all to use to conclude.

</details>

### 致谢与新模型预告

**Speaker 0**: 最后，我只想感谢 Cursor 工程、机器学习和研究团队的每一个人，他们一直在努力工作，很快，希望很快，就会为大家带来一个新模型。我们认为这个模型将比我们上一个模型有显著的改进，我们很期待你们来尝试它。非常感谢。

<details>
<summary>Original English</summary>

**Speaker 0**: i just like to thank everyone on the cursor engineering and ml and research teams who have been working hard to get a new model out to you all here very soon, hopefully, very soon soon that we think will be pretty notable improvement over our last model, and we're excited for you to try it. thank you so much.

</details>

**Speaker 3**: 检察求你告诉你。

<details>
<summary>Original English</summary>

**Speaker 3**: 检察求你告诉你.

</details>

**Speaker 4**: 女士们，先生们，请鼓掌欢迎我们的主持人，来自 Keycard AI 的技术人员。

<details>
<summary>Original English</summary>

**Speaker 4**: ladies and gentlemen, please put your hands together and welcome back our mc member of the technical staff at keycard alii.

</details>

**Speaker 5**: 怎么样啦啦啦啦？

<details>
<summary>Original English</summary>

**Speaker 5**: how 啦啦啦啦？

</details>

**Speaker 7**: 嗯，在 AI Engineer 大会的第一天真是精彩。

<details>
<summary>Original English</summary>

**Speaker 7**: well, what it amazing first day of contact here at AI engineer.

</details>

<!-- chunk 54/54 -->

### 闭幕总结

**Speaker 7**: 今天听了所有关于软件工厂的精彩演讲后，我最大的收获是：软件工厂的原材料已经存在了，对吧？我们的上下文变得更大了，我们有了更好的内存模型，改进的视觉模型，我们实际上可以验证工作。我们有了更好的AI安全最佳实践，现在可以理解关于代理身份和访问控制的模式。但我们必须有纪律，能够正确地运用所有这些原材料，才能构建出真正有效的工厂。我真的很认同今天下午听到的演讲中的观点，比如在某个演讲中提到的，对我来说最重要的收获是：工程作为一种实践绝对没有消亡。工程师可能不再编写所有代码了，代理可能会编写代码，但工程必须成为那个循环的一部分。特别是如果你想编写真正有效、不会产生垃圾的软件工厂。所以我希望大家今天都学到了很多。我知道我确实学到了很多，非常感谢你们的好奇心、你们的乐观精神、你们的能量。我们明天再见。

<details>
<summary>Original English</summary>

**Speaker 7**: I think the biggest take away for me at today after listening to all amazing talks on software factories, is that the raw materials for software factories exist, right? Our context got larger, we have better memory model, improved vision model, we can actually verify the work. We've got better AI security best practices now to understand patterns to on agent identity and access control. But we have to have the discipline to be able to wield all of the raw materials correctly in order to build off our factories that actually work. And I really resonated with the nuances from the talks I heard this afternoon, such as a talk where I mentioned that one takeaway for me was that engineering as a practice is absolutely not dead. Engineers might not be writing all of the code anymore, agents might be writing the code, but engineering has to be part of that loop. Especially if you want to write software factories that actually work and don't produce slop. So I hope everyone learned a lot today. I know I certainly did, and thank you so much for your curiosity, your optimism, your energy. We will see you back here tomorrow.

</details>

**Speaker 8**: 非常感谢。

<details>
<summary>Original English</summary>

**Speaker 8**: Thank you so much.

</details>

**Speaker 9**: 这是我们第三年举办Engineering World大会。

<details>
<summary>Original English</summary>

**Speaker 9**: This is our third year doing the Engineering World conference.

</details>

**Speaker 5**: 我们有这么多活动，你们正在帮助我们塑造工程的未来。工程应该是什么样子——永远，永远。

<details>
<summary>Original English</summary>

**Speaker 5**: We have so many events you are helping us step into the future of engineering. Engineering should look like forever, forever.

</details>

**Speaker 8**: 永远，永远。

<details>
<summary>Original English</summary>

**Speaker 8**: Forever, forever.

</details>

**Speaker 5**: 对对对对，永远对。

<details>
<summary>Original English</summary>

**Speaker 5**: Yes, yes, yes, yes, forever yes.

</details>

**Speaker 6**: 不如看。

<details>
<summary>Original English</summary>

**Speaker 6**: Let's see.

</details>