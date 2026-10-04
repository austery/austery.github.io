---
author: Latent Space
date: '2026-04-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oBWRHnggscM
speaker: Latent Space
tags:
  - world-models
  - multimodal-ai
  - symbolic-reasoning
  - generative-ai
  - game-development
title: Moonlake：多模态、交互式与高效世界模型——与孙繁耘和Chris Manning的对话
summary: 本访谈深入探讨了Moonlake公司在世界模型领域的创新方法，重点关注其多模态推理模型，该模型通过结合符号表示和物理引擎，旨在构建具有因果理解、长期一致性和交互能力的虚拟世界。对话比较了Moonlake与Sora等视频生成模型的根本区别，强调了交互性而非纯粹视觉保真度的重要性。嘉宾还讨论了当前世界模型评估面临的挑战、语言在AI发展中的作用，以及公司在游戏和具身AI领域的商业化愿景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Yan LeCun
companies_orgs:
  - Moonlake
  - Nvidia
  - OpenAI
  - Meta
  - Google
  - World Labs
  - Physical Intelligence
products_models:
  - Sora
  - JEPA
  - Genie
  - Marble
  - GPT-5
  - Gemini
  - Claude
media_books: []
status: evergreen
---
### 世界模型的评估挑战

**主持人**: 我认为这个领域现在正变得极其困难，因为各种事物都在涌现。我的意思是，这不仅适用于世界模型。我认为它适用于所有事物，包括基于文本的模型，对吧？因为你知道，在早期，拥有良好的基准似乎非常容易，因为我们可以做问答基准之类的事情。但是现在，人们想做的事情很多都不是那种类型，对吧？如果你想获得关于下个月去欧洲旅行哪款背包最适合你的建议，就不是那么容易提出一个基准。这些世界模型也面临着同样的问题。

<details>
<summary>Original English</summary>

**主持人**: I think this whole space is extremely difficult as things are emerging now. And I mean it's not only for world models. I think it's for everything including textbased models, right? Cuz you know in the early days it seemed very easy to have good benchmarks cuz we could do things like question answering benchmarks. But you know these days so much of what people are wanting to do is nothing like that, right? If you're wanting to get some recommendations about which backpack would be best for you for your trip in Europe next month, it's not so easy to come up with a benchmark. And it's the same problem with these world models.

</details>

**主持人**: 在我们开始今天的节目之前，我只想给听众一个小小的留言。谢谢你们。如果没有你们选择点击并收听我们的内容，我们将无法为大家带来如此清晰的AI工程、科学和娱乐内容。几乎每天都有赞助商联系我们。但幸运的是，有足够多的人订阅我们，使这一切无需广告也能持续，我们希望保持这种状态。但我只有一个请求要向大家提出。你能做的最强大、完全免费的事情就是点击订阅按钮。这是我唯一会向你提出的要求。这对我以及我的团队来说意义重大，他们每周都努力为你带来Inspace节目。如果你这样做，我保证我们永远不会停止努力，让节目变得更好。现在，让我们开始吧。好的，我们回到了工作室，与Moonlake的两名主创在一起。我想还有其他创始人，但是Sun和Chris Manning，欢迎来到工作室。

<details>
<summary>Original English</summary>

**主持人**: Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis. But fortunately, enough of you actually subscribe to us to keep all this sustainable without ads, and we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you. And it means absolutely everything to me and my team that works so hard to bring the Inspace to you each and every week. If you do it, I promise you we'll never stop working to make the show even better. Now, let's get into it. Okay, we're back in the studio with Moonlake uh two leads. I guess there's there's other founders as well, but uh Sun and Chris Manning, welcome to the studio.

</details>

**Chris**: 谢谢。谢谢邀请我们。

<details>
<summary>Original English</summary>

**Chris**: Thanks. Thanks for having us.

</details>

**主持人**: 你们，你们就像一颗新星，带着对旧模型真正耳目一新的看法，突然出现在了人们的视野中。我想问一下你们俩是如何走到一起的。Chris，你是NLP领域乃至整个AI领域的传奇人物。我想你是他的研究生。

<details>
<summary>Original English</summary>

**主持人**: You've you guys have uh you know come burst onto the scene with a really refreshing new take of old models. Um I would just want to uh sort of I guess ask how you the two of you came together. Chris, you're a legend in NLP and just AI in in general. Uh you're you're his grad student I guess.

</details>

**Sun**: 实际上是我的联合创始人。

<details>
<summary>Original English</summary>

**Sun**: Actually my co-founder.

</details>

**主持人**: 哦，是的。

<details>
<summary>Original English</summary>

**主持人**: Oh yeah.

</details>

**Sun**: 我应该把大部分功劳归于我的联合创始人**Sharon**。她当时和**Fein教授**一起工作，后来她又和这里的**Ron**和**Chris Manning**一起工作，所以我最初实际上是通过我的联合创始人联系到Chris的。

<details>
<summary>Original English</summary>

**Sun**: I should give a lot of credit to my co-founder Sharon. um she was she was actually working with professor fein and then she ended up working with um Ron and Chris Manning here and then so I got connected through to Chris initially actually through my co-founder

</details>

**主持人**: Moonlake是什么？Moonlake是什么？实际上，我也很好奇这个名字，但是为什么要进入世界模型领域？

<details>
<summary>Original English</summary>

**主持人**: what is moonlake what what is um actually I'm also very curious about the name but like why going into world models

</details>

### Moonlake的起源与世界模型理念

**Sun**: 我在攻读博士学位期间，在**Nvidia**研究院做了很多关于生成交互式世界的工作，旨在训练强化学习智能体或具身AI智能体。我们有两个观察结果。一个是在学术界，一个是在工业界。在工业界，像**Nvidia**这样的公司实际上花费大量资金购买这些交互式世界，无论是为了评估还是训练机器人、策略或模型。在学术界也发生了同样的事情，更具体地说，当我与**Nvidia**合作进行合成数据基础模型训练项目时，我们实际上生成了大量合成数据，并表明这些合成数据在多模态预训练方面与真实世界数据一样有用。但就像我说的，有大量的资金支付给外部供应商或其他公司，以手动策划这些类型的数据。我们非常清楚，在实现具身通用智能模型的过程中，模型需要了解其行为背后的后果，这意味着它们需要交互式数据，而对这些数据的需求正在呈指数级增长。但每个人似乎都从纯粹的视频生成角度或其他角度来考虑这个问题。但我们认为，真正的机会实际上是构建像人类今天所做的那样能够进行推理的模型。所以，这就是**Moonlake**的起源。我认为我之所以进入世界模型领域，部分原因是对世界的哲学思考，我有点相信模拟理论之类的东西。但另一方面，这真的只是因为，哦，那里有一个机会，我觉得没有人以我希望的方式来做。

<details>
<summary>Original English</summary>

**Sun**: so I was working a lot with actually Nvidia research during my PhD years on essentially generating interactive worlds to train reinforcement learning agents or embodied EI agents And then there's two observations. One in academia and one in industry. In industry like folks like Nvidia are actually paying a lot of dollars to purchase these types of interactive worlds whether it's for the sake of evaluation or training the robots um or policies or models. And then um in academia same thing is happening and more specifically when I was actually working with Nvidia on the synthetic data foundation model training project we were actually generating a lot of these synthetic data and showing that hey you can actually these synthetic are actually as useful as real world data when it comes to multimmodal pre-training but then like I said there's a lot of dollars being paid out to like external vendors or or like other folks to manually curate these types of data. It was very clear to us that okay on our way to let's call it embody general intelligence models need to learn the consequences behind their actions which means that they need interactive data and the demand for those types of data are growing exponentially but everybody is sort of thinking about it from a pure say video generation perspective or something else but we feel like the the true actually opportunity is actually building reasoning models that can do these things like how humans do these things today so that's a little bit on the genesis of moon And I think the reason I got into world models was partly a philosophical take of the on the world where I like you know believe the simulation theory and stuff like that but on the other on the other hand it's really just like oh like there's an opportunity there that I feel like nobody's doing it the way I think should be done.

</details>

**Chris**: 我可以说一点。是的。所以，总的目标是追求**人工智能**，你知道，我职业生涯的大部分时间都在语言领域做这件事，正如我们都知道的，在过去的几年里，这非常富有成效。我不需要告诉你我们用**大型语言模型**取得了多少成就，但尽管它们在提升语言和通用智能方面极其有效，但显然这并非世界的全部。这个多模态的世界，包括视觉、声音、味觉，你希望处理的不仅仅是语言。那么问题是如何做到这一点。尽管在计算机视觉领域投入了巨额资金，作为一个研究领域，计算机视觉几十年来实际上一直比语言领域大得多。我的意思是，我认为可以公平地说，视觉理解有点停滞了，对吧？你达到了对象识别，然后进展就停止了，对吧？如果你看看任何这些视觉语言模型，是语言完成了90%的工作，而视觉几乎不起作用。所以，这里真的有一个有趣的研究问题，那就是为什么会这样。**Moonlake**背后的核心思想是试图回答这个问题，相信在对视觉领域进行抽象理解的更符号化层面之间，可以建立一个非常丰富的联系，而这在主流视觉模型中是不存在的，这些模型仍然试图在像素的表面层面操作。

<details>
<summary>Original English</summary>

**Chris**: I can say a little bit about that. Yeah. So of the o overall goal is the pursuit of artificial intelligence and you know most of my career has been doing that in the language space and that's been just extremely productive as we all know the story of the last few years. I don't have to tell about how much we've achieved with large language models but although they have been extremely effective for ramping language and general intelligence it's clearly not the whole world. there's this multimodal world of vision, sound, taste that you'd like to be dealing with more than just um language. And then the question is how to do it. Um and despite you know a huge investment in the computer vision space right as a research field computer vision has been for decades far far larger than the language space actually. I mean, I think it's fair to say that, you know, vision understanding sort of stalled out, right? You got to object recognition and then progress just wasn't being made, right? If you look at any of these um vision language models, it's the language that's doing 90% of the work and the vision barely works. And so there's really an interesting research question as to why that is. And at heart um the ideas behind Moon Lake are an attempt to answer that believing that there can be a really rich connection between a more symbolic layer of abstracted understanding of visual domains which aren't in the mainstream vision models which are still trying to operate on the surface level of pixels.

</details>

**主持人**: 我想在你们的一篇博文中，你们把它表述为**结构而非规模**。这是你们的普遍论点吗？是的。嗯，规模也很好。大量数据也很好。但无论如何，你想要这种结构。是的。以便能够更有效地学习。

<details>
<summary>Original English</summary>

**主持人**: I think one of your blog posts you put it as structure not scale. Is that uh a general thesis? Yeah. Well, scale is good too. Lots of data is good as well. But nevertheless, you want the structure. Yeah. To be able to much more efficiently learn.

</details>

**主持人**: 是的。我真的很喜欢你们还提出了一个例子，说明你们的推理轨迹是什么样子的，对吧？你认为“提炼”这个词最能表达。我甚至不认为这是一个好的描述，但它会涉及例如**几何**、**物理**、**可供性**、**符号逻辑**、**感知映射**等等。但这是一种涉及**空间推理**、**世界模型推理**的例子，与普通的**大型语言模型**推理不同。

<details>
<summary>Original English</summary>

**主持人**: Yeah. The other thing I really liked also was you put out an example of what your kind of reasoning traces look like, right? Which you would distill is is the word that comes to mind. I don't even think that's a good good description but it would involve for example geometry physics affordances symbolic logic perceptual mappings um and what what have you but like that that is the kind of example that involves let's call it spatial reasoning world model reasoning as as compared to normal LM reasoning

</details>

### 世界模型与视频生成模型的区别

**主持人**: 但也退一步说，你们是如何定义世界模型的？你知道，很多人看到像，好吧，你可以做**扩散模型**，你可以做视频生成，但是你们发布了很多博文。你们最近还发表了一篇文章，我们甚至可以把它拉出来，关于高效的世界模型。嗯，你这里有一个相当结构化的定义，但是对于那些不太关注这个领域的普通受众来说，对吧？我们从像视频生成模型到世界生成器，一个模拟器，你们是如何描绘这种区别的？

<details>
<summary>Original English</summary>

**主持人**: but also like taking it a step back so how do you guys define world models you know a lot of people see like okay you can do diffusion you can do video generation but You guys put out quite a few blog posts. You put out a essay recently, we can even pull it up about efficient world models. Um, you have a pretty like structural definition here, but for the general audience that don't super follow the space, right? What's what's the difference in what we see from like a video generation model to a world gen, a simulator, how do you kind of paint that last?

</details>

**Chris**: 是的。所以，我认为这实际上有点微妙，因为你知道，人们看到这些惊人的**生成式AI视频模型**，**Sora**之类的东西，他们认为这是奇迹，他们认为，哦，这太棒了，这有点，你知道，我们已经解决了理解世界的问题，因为你可以生成这些**生成式AI视频**。但现实是，尽管视觉效果看起来很棒，但这些视觉效果实际上并没有伴随着对**3D世界**的理解，理解物体如何移动，不同行为的后果是什么，而这正是**空间智能**真正需要的。所以我的意思是，我们有时使用的一个术语是，你需要**动作条件世界模型**，只有当你能够预测给定某个动作发生后世界会发生什么变化时，你才真正拥有一个世界模型，特别是随着时间的推移，这会变得困难。所以，如果你只是，你知道，试图预测下一个视频帧，那并不是那么困难。但你真正想做的是理解几分钟后动作的后果，可能的后果。为了做到这一点，你实际上需要一个更加抽象的**语义世界模型**。

<details>
<summary>Original English</summary>

**Chris**: Yeah. So I think this is actually a little bit subtle because you know people look at these amazing generative AI video models Sora V3 one of these things and they think genies they think oh this is amazing this is sort of you know we've solved understanding the world because you can produce these generative AI videos but the reality is that although the visuals do look fantastic those visual s actually aren't accompanied by an understanding of the 3D world, understanding how objects can move, what the consequences of different actions are, and that's what's really needed for spatial intelligence. So I mean a term we sometimes use is that you need action condition world models that you only actually have a world model if you can predict given some action is taken what is going to change in the world because of it and in particular that becomes hard over longer time scales. So if you're simply, you know, trying to predict the next video frame, that's not so difficult. But what you actually want to do is understand the consequences, likely consequences of actions minutes into the future. And to do that, you actually need much more of an abstracted semantic model of the world.

</details>

**Chris**: 是的。问题在于，你想要比仅仅预测下一个标记所能提供的**结构**更多。嗯，通常情况下，过去五年的经验是，这被规模冲刷掉了。嗯，那么这里正确的中间地带是什么呢？就是你不要忽视惨痛的教训，但也要比我们今天所做的更高效。你知道，一种可能性是，看，如果我们只是收集大量的视频数据，这个问题就会解决。嗯，在某些假设下，这可能是真的，但在某些方面，这可能不是真的。首先，真正重要的是理解行动的后果，生成一个**行动条件世界模型**。如果你只是收集观察性视频数据，这是在挖掘在线视频时容易收集到的东西，你实际上不知道正在采取的行动是如何导致视频变化的。所以，如果你从不直接收集行动，而是试图从观察到的视频中推断它们，这并非不可能，但非常困难，而且尚未真正确定你能够以任何规模做到这一点。因此，收集**行动条件视频数据**非常重要，这也是为什么人们对使用模拟感兴趣的原因，这样你就可以收集你知道行动的数据，而这些数据供应非常有限。但即使数据再多，可能问题最终也能解决，但即使我们收集了大量的文本数据，文本数据也总是在一个高度抽象的层面。对吧？语言是一种人类设计的抽象表示，每个标记都有意义，它代表着世界的抽象。对吧？一旦你将某人描述为**教授**，一旦你说他们是**居高临下**的，对吧？你知道，这些都是对世界的非常抽象的描述，而不是你观察到的像素级别。因此，从像素级别达到这种抽象程度需要数量级的数据和处理。所以，尽管我们绝对希望尽可能多地利用数据，利用惨痛的教训，但如果有一种方法可以让你使用比纯粹从像素工作的人少五个数量级的数据，你就能更快地取得更大的进展。这就是这里的赌注。所以你可以说这只是为了能够，你知道，更高效、更快速、更廉价地完成它。但我认为它实际上不止于此。我认为我们应该将它与人类的工作方式进行类比。在某种程度上，你知道，是的，我们有这些**高分辨率的眼睛**，我们可以像看视频一样观看一个场景，但神经科学和心理学的所有证据都表明，进入人们眼睛的大部分东西从未被处理。对吧？你对你正在关注的东西进行相当精细的处理。但你知道，一旦它远离了这一点，是的，那里还有另一个人，你只是以自上而下的方式处理对你周围世界的这种非常抽象的**语义描述**。所以，你知道，这就是人类正在做的事情。他们正在使用**语义抽象**。所以我认为这只是正确的表示方式，因为我们还有其他目标。我们希望能够实现**实时世界**，这意味着你可以处理的处理量是有限的，我们希望进行**长期规划**和**一致性**，这又有利于抽象。我的意思是，我想**Physical Intelligence**的朋友们最近发表了一篇博文，你知道，他们也朝着同样的方向发展。他们说：“哦，模型。”

<details>
<summary>Original English</summary>

**Chris**: Yeah. The question comes where you want to have more structure than is available in just predicting the next token. Um and typically well let's let's call it the experience of the last 5 years has been that that is just washed away by scale right. Um so what is the right middle ground here that uh you don't ignore the bitter lesson but also you can be more efficient than what we're doing today. You know, one possibility is look, if we just collect masses and masses and masses and masses of video data, this problem will be solved. Um, under certain assumptions that could be true, but there are sort of multiple avenues in which it could not be true. The first is what's really essential is understanding the the consequences of actions, producing an action conditioned world model. And if you're simply um collecting observational video data, which is the easy stuff to collect when you're sort of mining online videos, you don't actually know the actions that are being taken to see how the video is changing. And so if you're never collecting directly actions and you're having to try and infer them from what happened in the observe video, that's not impossible, but it's very hard and it's not really established that you can get that to work at any scale yet. And so there's a lot of premium on collecting action condition video data which is part of why there's been a lot of interest in using simulation so that you can be collecting data where you do know the actions which is in quite limited supply. But there's also in the limit of as much data as you could possibly have. You know, maybe the problem is eventually solvable, but even though we collect huge amounts of text data, text data is always at a great level of abstraction. Right? Language is a human-designed abstracted representation where there's meaning in each token and it's representing an abstraction of the world. Right? As soon as you're describing someone as a professor and as soon as you're saying that they're condescending, right? You know, these are very abstracted descriptions of the world is not at sort of what you're observing as pixel level. And so to get to that kind of degree of abstraction starting from pixels is orders and magnitude of extra data and processing. And so although you know we absolutely want to exploit get as much data as possible use the bitter lesson nevertheless if there are ways in which you can work with five orders of magnitude less data than people working purely from pixels you're going to be able to make a lot more progress a lot more quickly. And that's the bet here. And so you could just say that's only wanting to be able to, you know, do it more efficiently, do it more quickly, do it more cheaply. But I think it's actually more than that. I think one should be making the analogy to how human beings work. At one level, you know, yes, we have these high resolution eyes and we can look and see a scene like a video, but all of the evidence from neuroscience and psychology is that most of what comes into people's eyes is never processed, right? that you're doing fairly fine processing of exactly what you're focusing on. But you know, as soon as it's away from that of Yeah, there's another guy over there that you've sort of only processing top down this very abstracted semantic description of the world around you. And so, you know, that's what human beings are doing. They're working with semantic abstractions. And so I think it is just the right representation because we also have other goals. We want to be able to do you know real time worlds that means there's a limit to how much processing you can do and we want to do long-term planning and consistency and again that favors abstraction. I mean I guess there was actually a recent blog post that came out from our friends at physical intelligence and you know they were sort of heading in the same direction. And they were saying, "Oh, model."

</details>

**主持人**: 是的。为了保持对世界上正在发生的事情的**长期记忆**，这样我们就可以做更长期的工作。我们实际上存储的是关于世界上正在发生的事情的文本，对吧？试图将其全部保持在像素级别并不是一个成功的策略。是的，我的意思是，你可以在视频模型中看到这种**时间一致性**。我们的训练规模是，你知道，我们拥有的所有视频数据。我们可能有30秒，几分钟。这与玩了半小时的游戏状态不同，对吧？嗯，我认为你们拆解得很好。你们有一篇关于用智能体构建**多模态世界**的博文。我不知道你们是否想谈谈这个。这是我读过的一件事。我以为——

<details>
<summary>Original English</summary>

**主持人**: Yeah. To maintain a long-term memory of what's happening in the world so we can do longer term. We're actually storing text of what is um, you know, been happening in the world, right? It's not such a successful strategy of trying to keep it all at a pixel level. And yeah, I mean, you can see it in video models like that temporal consistency. We're at a scale of train on, you know, all the video data we have. We have it for maybe 30 seconds, a few minutes. That's not the same as a game state played for half an hour, right? Um, I thought you guys break it down pretty well. You have a you have a blog post about uh building multimodal worlds with an agent. I don't know if you guys want to talk about this. This is one of the things I read. I thought

</details>

**Sun**: 是的，我提到的推理链。是的。

<details>
<summary>Original English</summary>

**Sun**: Yeah, the thing I talked about with the reasoning chain. Yeah.

</details>

**主持人**: 所以，这有不同的阶段。它看起来更像一个**智能体**，一个**脚手架**。与仅仅输入一个提示语，而你没有相同的一致性，这是非常不同的方法。对于正在收听的人来说，你知道，我强烈建议阅读它。它以不同的角度剖析了这个问题，对吧？那么，当你谈论视频世界游戏模型时，你需要考虑什么？你需要考虑什么？因素是什么？元素是什么？状态是什么？所以我不知道你们有没有关于这个的话题。

<details>
<summary>Original English</summary_

**主持人**: So, there's like different phases to this. It seems like it's more of an agent, a scaffold. Uh, very different approach than just, you know, type in a prompt and you you don't have the same consistency. It also like for people that are listening, you know, I would highly recommend reading it. It breaks down the problem in a different light, right? So like what do you need to consider when you're talking about video like world game models, right? How would what do you need to consider? What are the factors? What are the elements? What's the state? So I don't know if you guys have stuff to talk about for this one.

</details>

**Sun**: 是的。嗯，实际上我想补充一下我们之前的一个观点，那就是快速变化。我确实觉得有时人们会混淆，哦，我们正在采用一种抽象的方法，这意味着他们不相信**惨痛的教训**，但这只是错误的，对吧？我们相信惨痛的教训，但我觉得我们总是讨论的问题是，什么是正确的抽象级别？今天我喜欢打的比方是，假设我们可以编码和解码，用字节表示所有图像、视频、音频，那么最惨痛的教训方法是训练一个**下一个字节预测模型**，而不是**下一个标记预测模型**，在这种模型中，它天生就是多模态的，你可以只是嗯，但就像，好吧，就像Chris指出的那样，你需要达到那种规模和计算量。所以这就是为什么我们总是回到，好吧，什么是最高效的方法？而推理模型，就这篇博文而言，它展示了，嘿，我们实际上只是在推理世界，推理世界中对我有意义的那些方面，以便我从这个世界模型中学习我想要学习的东西。

<details>
<summary>Original English</summary>

**Sun**: Yeah. Um actually I wanted to add on a little bit on our previous point which is just like change quickly. I I do feel like sometimes people confuse like oh like we're taking an an method with with abstraction that means they don't believe in bitter lesson like like that's just false right like we are believe is a bitter lesson but then I feel like the question that we always discuss is like what is the right abstraction level today the analogy I like to make is like let's just say we can encode and decode represent all of images videos audio in bytes then the most bitter lesson approached is to train a next bite prediction model as opposed to the next token prediction model where it's just like okay it's natively multimodal and you can just um but it's like well yeah like to to Chris's point it's like the scale and compute you need to achieve that. Um um so that's why we always come back to like okay what is the most efficient way to do it and and reasoning models to to the point of this blog post is a showcase of like hey we're actually just like reasoning about the world and reasoning about the aspects of the world that that matter for me to learn what I want to learn from this world model. Um

</details>

**主持人**: 是的，就像你在改进你正在建模的**编码器**一样，一个更好的表示方式只会用更少的空间表示重要的事物。

<details>
<summary>Original English</summary>

**主持人**: yeah, it's like you're improving the encoder of whatever you're uh trying to model and like a better representation would just represent the important things in less space.

</details>

**Sun**: 是的。

<details>
<summary>Original English</summary>

**Sun**: Yeah.

</details>

**主持人**: 这会更高效。

<details>
<summary>Original English</summary>

**主持人**: And which would just be more efficient.

</details>

**Sun**: 是的。

<details>
<summary>Original English</summary>

**Sun**: Yeah.

</details>

**主持人**: 嗯，所以是的，我完全同意这与**惨痛的教训**并不矛盾。我还想提一件事。嗯，与**Yan LeCun**正在研究的**JEPA**有什么哲学上的区别吗？

<details>
<summary>Original English</summary>

**主持人**: Um so yeah, I I fully agree that it is not um antagonistic to uh bitter lesson. I do want to mention one more thing. Um is there any philosophical differences with the Japa stuff that uh Yanukun is working on?

</details>

**主持人**: 我得去那里。你，你，你提到了一些**潜在抽象**。我就想，好吧，那我们来谈谈吧，对吧？就像房间里的大象。

<details>
<summary>Original English</summary>

**主持人**: I got to go there. you you you're you're mentioning like some latent abstraction. I'm like, okay, fine. Let's let's talk about it, right? Like it's an elephant in the room.

</details>

### 与Yan LeCun哲学观点的差异

**Chris**: 是的，存在哲学上的差异。**Yan LeCun**是我的挚友。但他从未真正欣赏过语言的力量，特别是**符号表示**的普遍性。**Yan**是一个非常视觉化的思考者。他总是声称他用视觉思考，他的脑海中没有文字、符号或数学。嗯，也许**Yan**是这样，但我肯定不是这样。但是，无论如何，你知道，根据**Yan**的说法，世界和智能的基本构成是视觉，而语言只是人类之间一种**低比特率的通信机制**，它没有多少其他用处，远远不如进入你眼睛的**高比特率视频**。我认为他从根本上错过了许多重要的事情，对吧？想想这个进化论的论点，看看动物，对吧？最接近的类比是**黑猩猩**，对吧？所以黑猩猩的大脑与人类的大脑相当相似。它们有很棒的视觉系统。它们有很棒的记忆系统。它们有，你知道，比我们更好的短期记忆。它们可以计划。它们可以制造原始工具。但是，你知道，人类在对世界的理解、我们能计划什么、我们能建造什么方面遥遥领先。我们之所以能取得如此大的进步，基本上是因为人类设法发展了**语言**，这提供了一种**符号知识表示**和**推理层面**，从而极大地提升了大脑智能所能做的事情。哲学家**Dan Dennett**将语言称为一种**认知工具**，并认为，你知道，人类在世界上的生物中是独一无二的，他们设法构建了自己的认知工具，而语言就是第一个著名的例子，但其他事物，如数学和编程语言，也是认知工具。它们赋予你**抽象思维**、**扩展因果推理链**的能力，这让你能够做更多的事情，我们也将其用于**空间表示**、**智能**、**规划**和**游戏玩法**。所以我们相信，这正是**Moonlake**正在开发特定技术的基础，即**符号表示**是强大的，你希望在理解视觉世界时使用它，当你需要因果理解时，当你需要保持长期一致性和预测时，你知道，据我所知，这在**Yan LeCun**的世界观中是不存在的，所以我认为这就是根本的哲学差异。嗯，然后是他一直在推广的特定模型**JEPA**，我的意思是，这是一种合理的科研方向，可以用于构建视觉世界模型，在我看来，这是一种合理的科研方向，但它并没有真正确立为每个人都应该遵循的最佳方向，至少在**Meta**尚未大规模开发。但它不仅仅是视觉，对吧？我的意思是，**JEPA**是一种，你知道，只是**联合嵌入预测**，它实际上可以应用于任何事物，人们也确实做到了。如果论点是存在一种潜在表示，或者说这种潜在表示更适合这项任务，那么为什么不让机器为我们做这件事，而不是完全预先定义它，**JEPA**形状的东西不是正确的答案吗？如果不是，为什么不呢？所以我认为**JEPA**有一部分是正确的，那就是你确实想要一个**联合嵌入**，它能给你一个一致的世界模型，而**Yan**的论点是你永远无法从**自回归语言模型**中获得这种一致性，因为它们是自左向右地一次生成一个标记。我想这就是我们，你知道，这个领域研究人员争论的地方。你知道，我实际上并不相信那是对的，因为尽管标记生成是这种自回归过程，你知道，从左到右进行，我猜不一定是自左向右，但无论如何，在标记序列中，我们可以有自右向左的**阿拉伯语**。你知道，尽管如此，模型内部的所有权重，它们是模型对世界理解的**联合模型**，所以我认为你可以将模型的权重视为一种**联合表示形式**，因此，认为它可以成为世界模型的基础，从而避免**Yan**的反对意见，这是合理的。

<details>
<summary>Original English</summary>

**Chris**: Yeah, there are philosophical differences. Um Yan LeCun is a dear friend of mine. Um but he has never appreciated the power of language in particular or symbolic representations in general. Yan is a very visual thinker. He always wants to claim that he thinks visually and there are no words, symbols or math in his head. Um maybe that's true of Yan. It's certainly not the way I think. Um but at any rate you know um the world according to Yan is the basic stuff of the the world and of intelligence is visual and language is just this low bit rate communication mechanism between humans and it doesn't have much other utility and it's far inferior to the high bit rate video um that comes in your eyes. And I think he's fundamentally missing a number of important things there, right? Think of this evolutionary argument looking at animals, right? That the closest analogies, the things with chimps, right? So chimpanzees, you know, have fairly similar brains to human beings. They have great vision systems. They have great memory systems. They've got, you know, better memory than we do of short-term memories. They can plan. They can build primitive tools. But, you know, humans massively ahead in what we understand about the world, what we can plan, what we can build. And essentially what took off for us was that humans managed to develop language and that gave a symbolic knowledge representation and reasoning level which just gave this sort of vaultting of what could be done with the intelligence in brains. So the philosopher Dan Dennett refers to language as a cognitive tool and argues that you know humans unique among the creatures in the world have managed to build their own cognitive tools and language is the famous first example but other things like um mathematics and programming languages are also cognitive tools. They give you an ability to think in abstractions in extended causal reasoning chains and that allows you to do much more and we use that for spatial representation and intelligence and planning and gameplay as well. So we believe and this is you know underlying the specific technologies that Moonlake is making that symbolic representations are powerful and you want to use it in your understanding of the visual world when you want a causal understanding when you want to maintain long-term consistency and prediction and you know as I understand it that's just not in Yan LeCun's worldview so I think that's the fundamental philosophy ical difference. Um then there's the specific model he's been advancing Jeffa I mean that's a reasonable research bed as a direction as to to head for building out a model of the visual world to my mind it's sort of one reasonable research bed it's not really established it's the best one that everyone should be following at least developed at scale at Meta but it's not just vision right like I mean Japa is a you know just join embedding prediction can be applied to anything really and and people have done it. If the argument is that there is a latent representation or that is that is probably more uh suited to the task then why not let machines do it for us instead of predefining it at all and isn't something like a Jeppa shaped thing the right answer and if not why not so I think there's a part of Jeppa that's right which is you do want to have a joint embedding that gives you a consistent model of the world and yan 's argument is you can never get that from auto regressive language models because they're sort of left to right turning out one token at a time. I guess this is where we're um you know the researcher arguments of the field. you know, I'm not actually convinced that's right cuz although the token production is this auto regressive um process that's heading, you know, left to right, I guess don't have to be left to right, but anyway, in sequence of tokens, we could have right to left Arabic. that um you know although that's true all of the weights of the model that are internal to the transformer they are a joint model of the model's understanding of the world and so I think you can think of the weights of the model as a form of joint representation and therefore it is plausible to think that that could be the basis of a world model which avoids um Han's objections.

</details>

**主持人**: 我想我明白了，显然这也会触及**Moonlake**最终要做的事情，对吧？就像很难说清楚，因为你公布了最终结果，但我们不知道输入是什么。所以，你知道，那是我们必须随着时间推移弄清楚的事情。

<details>
<summary>Original English</summary>

**主持人**: I think I follow and obviously that will touch on what Moon Lake eventually ends up doing as well, right? Like which it's hard to tell because you put out the end results but we don't know the inputs that go into it. So it's it's you know that's that's something that we have to figure out over time.

</details>

**Chris**: 是的。

<details>
<summary>Original English</summary>

**Chris**: Yeah.

</details>

**主持人**: 我的意思是，我想这有点分解了一些输出。你愿意带我们看一遍吗？

<details>
<summary>Original English</summary>

**主持人**: I mean I guess this kind of breaks down some of the outputs. Do you want to walk us through it?

</details>

### 推理轨迹与交互式世界

**Sun**: 是的。呃，所以这只是带我们了解**推理轨迹**，就像，好吧，假设我们想在这个上下文中构建一个世界，它实际上只是一个游戏演示，展示了这个世界模型可以构建的各种交互。是的，它实际上只是一个推理轨迹，就像，好吧，你被提示创建一个**保龄球游戏**，它是如何实现你所看到的**因果关系**、**交互**和**一致性**水平的，对吧？嗯，所以是的，这几乎就像一个推理轨迹的例子。

<details>
<summary>Original English</summary>

**Sun**: Yeah. Uh so this this really just walks us through the reasoning traces of like okay that just say if we want to build a world in this context it's really just a game demo that that shows the variety of interactions that this world model can build and yeah it's really just a reasoning traces of like okay you're prompted to create a bowling game like how did it achieve what you saw that level of causality interaction and consistency right um so yeah this is almost just like an example of like a reasoning traces

</details>

**主持人**: 非常详细。

<details>
<summary>Original English</summary>

**主持人**: very detailed

</details>

**Sun**: 非常非常详细，但你必须，你甚至没有意识到，对吧？就像当一个视频生成时，当一个球击中一个球瓶时会发生什么，对吧？所以首先，你会听到音频，音频触发器会触发，分数会增加，世界会改变，球瓶会开始掉落，计时器会启动。嗯，你知道，这就像我们现在习惯于对语言模型进行推理一样，有一个完整的状态，包括**几何**、**物理**等等。

<details>
<summary>Original English</summary>

**Sun**: very very detailed but you got to like you don't even realize it right like when a video is generated what happens when a ball strikes a pin right so first like you there's audio in that like audio triggers happen score increments uh the world changes like pins have to start dropping there's a timer that goes on um you know it's just like very similar to how now we're used to reasoning for language models there's a whole state of what happens so geometry physics uh all this stuff and then

</details>

**主持人**: 有那种单一的提示。所以资产**物理化**，所有这些东西。这是一个很好的视图，可以看到正在发生什么。

<details>
<summary>Original English</summary>

**主持人**: there's kind of that single prompt so asset um physication, all this stuff. It's it's like a it's a nice view to see what's going on.

</details>

**Chris**: 我认为**Sun**也太客气了，没有指出**Google**的**Genie**演示以及**World Labs**的**Marble**都没有交互式世界。

<details>
<summary>Original English</summary>

**Chris**: I think Sun is also too polite to point out that uh both like Google's Genie uh demos as well as uh World Labs's Marble do not have interactive worlds. Uh

</details>

**Sun**: 这就是拥有**推理模型**的好处，对吧？因为你可以说：“哦，也许在这种特定情况下，我想学习如何打保龄球。”然后你可以说，好吧，那么在学习如何打保龄球时，什么才是重要的呢？好吧，也许我需要了解**物理**的基本原理，我想把它扔过去。我想知道当它重置时，这是一个新的游戏。所以我知道，是的，基本上，你知道，你知道，你知道，拿起球，你知道那个球会导致球瓶倒下。你知道对于这个特定的保龄球游戏来说，重要的是得分。你知道得分对应着倒下的球瓶数量。嗯，所以这就像，如果一个模型知道它看起来像什么，知道保龄球游戏看起来像什么，但实际上不让你反复练习，不让你了解如何才能获得高分，那么它就无法让你学习你在世界模型中想要学习的东西，对吧？我认为这真的只是一个例子，说明我们所采用的方法相对于当今人们谈论所谓的“世界模型”时的主流方法所具有的优势。

<details>
<summary>Original English</summary>

**Sun**: that's the benefit of having a reasoning model, right? Like because you can you can say, "Oh, like maybe in this particular context I want to learn how to bowl." And then you can say, okay, then what is it important when it comes to learning how to bowl? Okay, maybe it's like I need to understand the the basic of like physics and I want to throw it over them. I want to know that when I when it resets, it's it's a new game. So I know that yeah, basically, you know, you know, you know, to pick up the ball, you know that ball's going to cause the pins to fall down. You know that what's important to this particular bowling game is to score. and you know that the score corresponds to the number of pins that fell down. Um so it's just like if it's a model that sort of knows what it looks like, knows what a bowling game looks like, but doesn't actually allows you to practice over and over again and to understand that oh like what it takes to actually get a high score, then it sort of doesn't actually allow you to learn what you set out to learn within the world model, right? And and I think this is really just one example of showing like the advantages of the approach that we're taking over most the let's call it the zeitgeist is today when people talk about quoteunquote world models,

</details>

**主持人**: 对吧？所以它似乎是当有一个世界模型时要问的问题是，我不仅可以在世界中漫游并欣赏美丽的画面吗？我还可以与世界中的物体互动并看到动作的正确后果吗？

<details>
<summary>Original English</summary>

**主持人**: right? So it sort of seems like the question to ask when there's a world model is can I not only just wander around the world and look at the beautiful graphics? Can I interact with the objects in the world and see the right consequences of actions

</details>

**Sun**: 而且你也理解如果你做某事会产生什么后果，对吧？所以它不仅仅是，好吧，有一件事，如果我拿起它，就会发生一些事情，但你知道，有50个选项，我知道我可以期望，我可以推断出如果我做其中任何一个会发生什么，对吧？所以当你真正能看到它并与之互动时，就非常不同了。

<details>
<summary>Original English</summary>

**Sun**: and you also understand what the consequences would be if you do something right so it's not just like okay there's one thing if I pick it up something will happen but you know there's there's 50 options and I know I can expect I can infer what would happen if I do any of them right so very different when you can actually see it play around with it

</details>

**主持人**: 这里有两个大胆的元素，我的意思是，我想不那么雄心勃勃的一个是，嗯，让我们真的为听众阐明，这与编写**Unity**代码有什么根本区别，对吧？就像只是创建一个模型将提示语翻译成**Unity**代码。

<details>
<summary>Original English</summary>

**主持人**: there there's two cheeky elements of that I mean the the sort of I guess less ambitious one is um let's really establish for listeners uh why is this fundamentally different than writing unity code right like just creating a model to translate a prompt into unity code

</details>

**Sun**: 所以有一个底层的**物理引擎**。在这个意义上，它与**Unity**有一些重叠的地方，但我们认为它就像**物理引擎**或**工具**或**代码**是**认知工具**，就像借用**Chris**的术语一样，对吧？就像模型可以部署的工具一样，作为实现目的的手段。所以今天你可能会说，好吧，在这种特定情况下，我们关心**物理**，我们关心长期的**因果关系**，那么是的，我们部署并使用物理引擎。然后也许明天我们会说，好吧，我们正在训练无人机，我们只关心**流体力学**和世界的视觉方面，那么，是的，也许模型实际上不必使用物理引擎，或者它可能使用其他类型的表示或物理引擎来完成任务。所以是的，为**Unity**编写代码有点类似于模型可以使用的工具。但我们的目标是让模型采用**表示条件推理**方法或过程。是的。

<details>
<summary>Original English</summary>

**Sun**: so there is an underlying physics engine um in that sense there's some overlapping things to unity but the way we think about it is like physics engine or tools or code are cognitive tools like borrowing Chris's term right like tools that the model can deploy as means to an end. So today maybe you say okay in this particular context we care about physics we care about the long-term causality consequences then yes we deploy it employ physics engine and then maybe tomorrow we say okay we're we're training that just say drones where we only care about really fluid dynamics and the visual aspect of the world then then yeah maybe we don't actually the model actually doesn't have to use a physics engine or maybe it employs other types of representation or physics engine to achieve the task. So yes, writing code for Unity is sort of similar to a tool that a model can employ. But our goal is for model to take a representation conditioned reasoning approach or process. Yeah.

</details>

**主持人**: 内部。

<details>
<summary>Original English</summary>

**主持人**: Internally.

</details>

**Sun**: 是的。使用这些东西就像**通用工具调用**一样，对吧？我认为这非常有趣。另一个更雄心勃勃的是某种递归元素，它会变成**多人游戏**，对吧？就像这里有一个**单人游戏**元素。你没有模拟任何其他参与者，那又是另一回事了。

<details>
<summary>Original English</summary>

**Sun**: Yeah. Using these things is just like general tool calls, right? Which I think is very interesting. The other more ambitious one is uh some kind of recursive element where it becomes multiplayer, right? Like here there's a single player element. you're not modeling any other people involved and that is a whole other thing.

</details>

**Sun**: 但实际上，我们已经可以做**多人游戏**了。

<details>
<summary>Original English</summary>

**Sun**: But in fact, we can already do multiplayers.

</details>

**主持人**: 哦，是的。好吧。我没见过——

<details>
<summary>Original English</summary>

**主持人**: Oh yeah. Okay. I haven't seen

</details>

**Sun**: 你只需提示我们的模型，说嘿，将其配置为**多人游戏**，然后它就会这样做，你就能配置多人游戏了。

<details>
<summary>Original English</summary>

**Sun**: any you just actually just like prompt our our model to say hey like configure it to multiplayer then it'll do like this you'll be able to configure multiplayer.

</details>

**主持人**: 太棒了。

<details>
<summary>Original English</summary>

**主持人**: Great

</details>

**Sun**: 为你提供**持久性数据库**。

<details>
<summary>Original English</summary>

**Sun**: persistency database for you.

</details>

**主持人**: 容易。

<details>
<summary>Original English</summary>

**主持人**: Easy.

</details>

### 当前局限与未来发展

**主持人**: 是的。那么，我们当前有哪些局限性呢？有一种方法是，好吧，**扩大视频预测器**。显然存在数据问题，嗯，你知道，使用这种方法，呃，是数据限制吗？接下来的步骤是什么？是实时性吗？所以，你知道，有一方面是编写一个**智能体**来编写**Unity**代码，但是，好吧，我想实时播放游戏，我想让角色也像智能体一样，但是我们如何才能看到这种扩展呢？

<details>
<summary>Original English</summary>

**主持人**: Yeah. So what what are like some of the current limitations in where we're at. So there's one approach of like okay scale up video predictors. Obviously there's data issues uh you know with approaches like this uh is it data constraints what are like the next steps is it real time like so there's one side of you know write an agent to write unity code but okay I want to be streaming a game real time I want to have characters being also like agentic but where where do we kind of see this scaling up right

</details>

**Sun**: 是的，绝对存在数据限制，数据越多，这种推理模型就越能像人类一样操作各种工具和软件来构建任何必要的东西。然后还有一种**保真度**限制，我们实际上正在用另一个模型**Rey**来解决，我们稍后可以讨论。但是，好吧，用我们正在采用的方法，要达到**照片级真实感**并不容易。但是我们认为有更好的解决方案，我们稍后可以深入探讨。

<details>
<summary>Original English</summary>

**Sun**: yeah there's definitely a data constraint like the more data the the better this reasoning model can almost basically act as humans to like operate a variety of tools and softwares to build whatever is necessary and then there's a sort of fidelity constraint which we're actually solving with another model Rey which we can talk about later. Um but it's like well it's not as easy to get to photo realism with the approach that we're taking. Um but we think there are better solutions to that which is we can dive into later later.

</details>

**主持人**: 你们在这里提到的一点是，它是一个**扩散模型**，对吧？所以有一些方法，呃，**扩散模型**，**高斯泼溅**，嗯，是的，所以**Rey扩散模型**，你们想介绍一下吗？

<details>
<summary>Original English</summary>

**主持人**: The one one thing you note here is it's a diffusion model right? So there's there's a few approaches uh diffusion caution splatting um yeah so Rey diffusion model you guys want to

</details>

**Sun**: 是的，完全没问题。所以，在我们的**世界建模框架**中，我们认为我们训练了两个模型，对吧？一个是我们刚刚谈到的**多模态推理模型**，它主要处理世界的**因果关系**、**持久性**和**逻辑确定性**。然后，**Rey**是我们的赌注，它说，好吧，虽然所有这些模型都可以处理我们刚刚谈到的所有这些事情，但与现有视频模型相比，它的局限性在于它没有那么高的像素保真度，对吧？而**Rey**是说，嘿，我们实际上可以利用我们用多模态推理模型生成的任何**持久表示**，并学习将其重新风格化为**照片级真实感**的风格或你想要的任意风格。所以这个模型几乎是说，嘿，我将尊重你创建的世界的**持久性**和**交互性**，但我唯一的工作是确保其像素分布接近我们想要的。

<details>
<summary>Original English</summary>

**Sun**: yeah totally so within our world modeling framework we think there are two models that we train right like there's the multimodal reasoning model that we just talked about that essentially handles mainly the the causality the persistency and logic determinism determinism of the world and then Rey is our bet on saying okay Like while all those model um can take care of all these things that we just talked about its limitations compared to existing say video models is that it doesn't have as high of a pixel fidelity right off the gate right and Rey is to say hey we can actually take whatever persistent representation that we generate with our multimodal reasoning model and learn to restyle it into photorealistic styles or arbitrary styles you want. So this model is almost to say, hey, I'm going to respect the persistency and interactivity of the world that you created, but my only job is to make sure that its pixel distribution is close to what we want.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**主持人**: 还有，是的，例子，对吧？你保持了**KO散度**，在那里——

<details>
<summary>Original English</summary>

**主持人**: And yeah, example, right? You kept the KO divergence where

</details>

**Sun**: 不，不。我的意思是，这，这，这是一个经典的，嗯，你怎么不偏离原始材料太远，就像你保持了**KO**一样，这有点酷。

<details>
<summary>Original English</summary>

**Sun**: No, no. I mean, this this is a a classic like um how you don't stray too far from the source material as you you kept the KO, which is kind of cool.

</details>

**Chris**: 是的。是的。我的意思是，区别在于，我的意思是**Sun**正在指出这一点，某种程度上说，这是一条更困难但更好的道路，你知道，通常情况下，**扩散模型**会生成整个场景，它看起来很可爱，但它背后没有**空间理解**，而这正是实现**实时图形**、**游戏玩法**、**空间智能**、**理解世界后果**所需要的。而这是一种**假设抽象语义世界模型**、**世界状态**的路径，然后**扩散模型**再在此基础上用于生成高质量图形。

<details>
<summary>Original English</summary>

**Chris**: Yeah. Yeah. I mean and the difference is and I mean Sun was pointing at this where sort of saying it's in one way a more difficult path but a better path that you know typically the diffusion models uh producing the whole scene and it looks lovely but there isn't spatial understanding behind it which is allowing for the real time graphics game play the spatial intelligence understanding the consequences of worlds where this is um taking a path where it is assuming an abstracted semantic model of the world the world state and then the diffusion model is then being used on top of that to produce the high quality graphics.

</details>

**主持人**: 这有预期的实际或商业用途吗？还是说这只是能力展示？

<details>
<summary>Original English</summary>

**主持人**: Is there an intended practical or business use for this or is it like a like a demonstration of capabilities?

</details>

**Sun**: 我们实际上相信这将是**渲染**的下一个范式。所以它将取代**Riser**。它将取代今天的**DLSS**，因为它不仅拥有从世界中学到的这些**像素先验**，这样你就可以以**照片级真实感**的风格玩任何游戏，这是很多玩**GTA**的人的愿望，对吧？就像嗯……

<details>
<summary>Original English</summary>

**Sun**: We actually believe that this is going to be the next paradigm of rendering. So it's going to replace how rest Riser is. It's going to replace DLSS today because it not only has these pixel prior that's learned from the world such that you can literally play any game in photorealistic styles which is a lot of people's desire when they do GTA right like um

</details>

**主持人**: 所有的**mod**，所有添加完美光照等等的人。

<details>
<summary>Original English</summary>

**主持人**: all the mods all the people adding perfect lighting and all this.

</details>

**Sun**: 所以我们称之为世界的**皮肤**。

<details>
<summary>Original English</summary>

**Sun**: So skins for worlds let's call it

</details>

**主持人**: **皮肤**，你可以称之为**皮肤**，你可以称之为**定制**，你可以按照自己喜欢的方式玩，对吧？是的，没错。我认为我们在这篇博文中特别指出的另一件事是它的**可编程性**，对吧？这意味着这个渲染器，历史上渲染器总是游戏状态的衍生品。对吧？你说好吧，这是游戏状态，我正在渲染一帧。但在这里我实际上是说，这个渲染器可以成为**游戏循环**的一部分。我可以说，如果我得到10个苹果，我的首选武器，我的子弹就会变成苹果。这是可能的，因为我们可以说，我们基本上可以动态地让某些游戏状态触发渲染器的**先决条件**，这样渲染器现在也成为了游戏循环的一部分。一件事是说它只是外观，但第二件事是说存在这些新颖的交互，这些交互之所以可能，是因为这个渲染器现在实际上拥有世界的**先验知识**。

<details>
<summary>Original English</summary>

**主持人**: skins that's called you can call it skins you can call it customization you can play it how you want right? Yeah, exactly. And I think another thing that we really pointed out spec specifically in this blog is the programmability of it. Right? So what this means is that this renderer well historically renderer is always a derivative of the game state. Right? You're saying okay here's the game state I'm rendering out of frame. But here I'm saying actually this renderer can be part of the gameplay loop. I can say something along the lines of if upon getting 10 apples, I'm gonna my weapon of choice, my bullet's going to turn into apples. And that's that's possible because we can say we can basically dynamically have certain game state trigger the the preconditions to the renderer such that the rendering is now part of the game loop too. One thing is to just say okay it's it's it's the appearance but the second thing is also to say there's these novel interactions that are of possible because this renderer now has actually prior of the world.

</details>

**主持人**: 这取决于艺术家如何利用它。

<details>
<summary>Original English</summary>

**主持人**: It is up to the artists to figure out what to do with it.

</details>

**Sun**: 这取决于**创作者**。是的。而且我也认为这实际上是我们提出的另一个重要论点，我们之所以做出这个选择，是因为很多时候，无论是具身AI还是游戏，你都希望有一个人类可以注入意图的层面，对吧？所以例如，假设在游戏环境中，显然是我的**创作意图**，但也许在具身AI环境中，就像，哦，我采用这个基础策略，我想实际对其进行微调，以便部署在我的家里，所以你想要几乎说注入一个层面，人类可以说：“哦，这是我想要创建的事物分布，以实现我的目标。”

<details>
<summary>Original English</summary>

**Sun**: It is up to the creators. Yes. And I also think that's actually another big argument that we're making and the reason that we're picking back taking the bet we're making is that a lot of the times whether it's for embody AI or gaming like you want a layer where human can inject their intentions right so for example let's just say in the context of gaming it's obviously like my creative intent but maybe in the context of embody AI it's like oh like I take this foundational policy and I want to actually fine-tune it to deploy in my house so you want to almost say inject have a layer where human can say, "Oh, here's the distribution of things I want to create to achieve my goal."

</details>

**主持人**: 我认为今天的**3D图形**基本上是人们表达，“嘿，我关心这个世界什么？”的层面。它允许人类意图更明确、更分布式地在这些世界中表达，而不是仅仅说，“嘿，我要生成像任意的，它就像只是提示。”你知道，

<details>
<summary>Original English</summary>

**主持人**: And I think 3D graphics as it as it is today is basically the layer for people to say, "Hey, what do I care about in this world?" And it allows um basically human intent to be expressed in these worlds much more explicitly and distributionally as opposed to just saying, "Hey, I'm going to generate like arbitrary and it's like just prompts." You know,

</details>

**主持人**: 这就是其中之一，就像，我想你会建立一系列模型，对吧？这只是其中之一，这可能就像效用最高或频率最高的一个。我不知道该怎么称呼它，就像是的，你可以立即将其放入任何游戏中，你不需要你们做的任何其他东西，但是嗯，我可以看到，我可以看到。我认为人类意图是人们甚至不习惯的东西，因为我们太习惯于**静态世界**或嗯，你知道，不反应的世界，或者我不知道。你现在有点让我大开眼界，就像，好吧，我想知道你是否和**GDC**的人谈过，他们会怎么做？

<details>
<summary>Original English</summary>

**主持人**: it's one of those things where like I I think you're going to build up a series of models, right? This is just one of this is probably like the highest utility or heaviest frequency one. I don't know what to call this where like yeah, you can immediately drop this in on any game and you don't need anything else that that you guys do, but um I could see I could see that. I think the the human intent is something that people are not even used to because we're so used to static worlds or um you know, worlds that just don't react or I don't know. It's it's you're kind of blowing my mind right now with like well I wonder if you've talked to people at GDC and what are what are they going to do with it?

</details>

**Sun**: 是的。现在我们在这方面采取的立场是，我们不会比我们的用户更有创造力。

<details>
<summary>Original English</summary>

**Sun**: Yeah. Now the stance that we take on this front is like we're not going to be more creative than our users.

</details>

**Chris**: 嗯，但我们希望确保我们以一种真正能让他们表达意图的方式来构建事物。

<details>
<summary>Original English</summary>

**Chris**: Um but we want to make sure that we're building things in a way that really allows them to express their intent.

</details>

**主持人**: 你说的“这是我想要的分布”这件事。我认为文本可能带宽太低，无法真正展示，因为你知道，我可能只是想投入一堆**参考资产**，然后你就可以从中找出答案。

<details>
<summary>Original English</summary>

**主持人**: The thing that you said about here's the distribution that I want. I think text may be the too low of a bandwidth to to really demonstrate because you know there I'm I'm probably just going to want to drop in a bunch of reference assets and then you can figure it out from there.

</details>

**Chris**: 你可能想要两者的结合，对吧？就像你扔几张图片进去。我想要这种风格。我想要它看起来像这样。这是一种混合，对吧？

<details>
<summary>Original English</summary>

**Chris**: You probably want to do a mixture of both, right? Like you throw in a few images. I want it this style. I want it to look like this. It's it's a mixture, right?

</details>

**Chris**: 我认为是混合。我的意思是，是的，我的意思是，这显然有一个**视觉组件**，并不是说，你知道，所有东西都可以是文本，因为当然你想要一个视觉外观，但也有大量提供世界外观和事物行为的整体画面，你可以用几句话来表达，而通过视觉方式做起来会非常耗时和困难。所以我认为，是的，你想要两者的结合。

<details>
<summary>Original English</summary>

**Chris**: I think it's a mixture. I mean, yeah, I mean, there's clearly a visual component of this and it's not that, you know, everything can be text because of of course you want to give a visual look, but there's also a massive amount of giving the overall picture of the look of the world and the behavior of things that you can express in a few words of text and it be very time consuming and difficult. ult to do via visual means. So I think yeah you want a combination of both.

</details>

### 世界模型的评估与哲学边界

**主持人**: 所以我有一个问题是，我们如何评估**世界模型**？所以就像有很多轴，对吧？一个是，好吧，我有偏好，我们对提示语的依从性如何？一个是模拟，一个是，就像事情是否有核心逻辑被打破。所以从我们知道如何评估**扩散模型**，有**保真度**，有这样的东西，但是大多数人可能没有考虑到的挑战是什么？是的，我认为这是一个很好的问题，可能是世界模型中最难的问题之一，因为它总是回到你正在构建这个世界模型的目的，根据你的最终目标和目的，评估应该有所不同。所以，在游戏环境中，最直接的衡量方式是人们实际在这个你创建的世界中花费了多少时间。如果你的目标是，例如在我们刚刚谈到的环境中，嘿，部署一个**具身智能体**，那么你的最终指标就是，好吧，在这些你生成的世界中训练之后，当你在目标环境中实际部署时，它的**鲁棒性**如何？但是，你知道，衡量这些最终指标是困难的。所以今天人们有像我称之为**代理指标**的东西，它基本上试图衡量我们真正关心的是最终指标，但坦率地说，每个用例都不同。嗯，是的，

<details>
<summary>Original English</summary>

**主持人**: So one question I kind of have is how do we go about evaluating world models? So like there's many axes right one is like okay I have preferences how well do we adhere to prompts one is the simulation one is like do things is there core logic that's broken. So coming from we know how to evaluate diffusion there's fidelity there's stuff like that but what are some of the challenges that most people probably aren't thinking about? Yeah, I think this is like a great question and probably one of the hardest questions in world models because like I think it always comes back to what are you building this world model for and depending on your end goal and purpose the evaluation should differ. So in the context of games then the most direct way of measuring is how much time are people actually spending in this world that you create. And if your goal is to say for example in the context that we just talked about like hey deploying deploying action in body a agent then your your end metric is then okay after training in these worlds that you generate how robust it is to when you actually deploy to the target environment but then you know it's it's hard to measure these end metrics. So today people have like these proxy metrics that I call that basically try to measure what we really care about which is the end metrics but then frankly it's different for every use case. Um yeah,

</details>

**主持人**: 这似乎是一个很大的挑战，对吧？就像在**语言模型**或**视频模型**、**图像模型**中，你的基准是代理，对吧？人们实际上并没有问指令遵循、工具使用问题，它们是衡量其下游表现的代理。但对于这个，所以就像，你知道，团队、公司是否应该在游戏之外拥有自己的独立基准？如果你想到像，好吧，视频制作、电影之类也想使用世界模型的东西，他们是否应该内部化自己的代理？这是你们会做的事情吗？这属于哪种类型？

<details>
<summary>Original English</summary>

**主持人**: which seems like quite a challenge, right? Like in in language models or video models, image models, your benchmarks are proxies, right? People aren't actually asking instruction following tool use questions, they're proxies of how well it will do downstream. But for this, so like you know, should should team should companies have their own individual benchmarks outside of games? If you think of stuff like okay video production, movies stuff like that that also want to use world models should should they sort of internalize like their own proxy is this something you guys do where does that kind of

</details>

**Chris**: 我认为这个领域现在正变得极其困难，因为各种事物都在涌现。我的意思是，这不仅适用于世界模型。我认为它适用于所有事物，包括**基于文本的模型**，对吧？因为你知道，在早期，拥有良好的基准似乎非常容易，因为我们可以做问答基准之类的东西，你可以根据这些文档回答问题，以及各种其他类型的，你知道，进行逻辑推理或数学。但同样，这些都是，并且存在视觉上的等价物，例如**对象识别**，对吧？但这些都是小组件任务。但你知道，现在人们想做的很多事情，包括语言模型，都不是那样的，对吧？你想要与语言模型进行交互，并获得关于下个月去欧洲旅行哪款背包最适合你的建议，这不是同一种事情，对吧？而且，对于这种大型语言模型能否为你提供有效的指导互动来购物，就不是那么容易提出一个基准了，对吧？所以，这些世界模型也面临着同样的问题。因此，如果我们以**游戏设计**为例，那么成功就是游戏设计师能够在合理的时间内制作出他们想象中的东西，这才是真正的宏观任务。但是，你知道，这很难转化为基准。我认为很多东西实际上会变成人们用脚投票，对吧？我的意思是，我想这就像在**大型语言模型**层面发生的事情，对吧？当人们选择使用**GPT-5**或**Gemini**或**Claude**时，你知道，个人正在尝试这些不同的模型，并决定，哦，我喜欢**GPT-5**给我的答案，或者不，我觉得从**Claude**那里可以获得更准确的细节，对吧？

<details>
<summary>Original English</summary>

**Chris**: I think this whole space is extremely difficult as things are emerging now and I mean it's not only for world models I think it's for everything including textbased models right cuz you know in the early days it seemed very easy to have good benchmark marks because we could do things like question answering benchmarks and could you answer the question based on these documents and the various other kinds of you know do pieces of logical reasoning or math. But again these are sort of and there are sort of visual equivalents of things like object recognition right but these small component tasks but you know these days so much of what people are wanting to do also with language models is nothing like that right you're wanting to um have an interaction with the language model and get some recommendations about which backpack would be best for you for your trip in Europe next month and it's not the same kind of thing, right? And it's not so easy to come up with a benchmark as to does this large language model give you an effective interaction for guiding you in a good way for shopping, right? So, and it's the same problem with these world models. So if we take the game design case, well success is that a game designer can produce what they are imagining in a reasonable amount of time and that's really the kind of macro task but you know that's a very hard thing to turn into a benchmark and I think a lot of this is actually going to turn into people working walking with their feet, right? I mean, I guess that's what's happening, you know, at the large language model level, right? when people are choosing to use, you know, GPG5 or Gemini or Claude, you know, individuals are trying out these different models and deciding, oh, I like the kind of answers that GPT5 gives me or no, I feel like I get more accurate detail from Claude, right?

</details>

**主持人**: 这是一种直觉检查。我意识到这一点，但实际上是人们是否觉得它能为他们提供他们想要的效用，对吧？

<details>
<summary>Original English</summary>

**主持人**: It's a lot of vibe checking. I realize that but it's actually whether people feel it's giving them utility in what they want. Right?

</details>

**主持人**: 而那里有趣的是，很多人喜欢视觉，对吧？这看起来很漂亮，但这并不是它存在的目的，对吧？如果一个游戏设计师正在开发某个东西，他们关心的是**游戏引擎**，是状态。它可以看起来像任何东西。你可以稍后修复它，或者你可以有一个非常好的游戏状态，你可以快速编辑它到20个不同的版本，这些版本都保持状态。

<details>
<summary>Original English</summary>

**主持人**: And the the interesting thing there is like a lot of people prefer the visual, right? This looks pretty, which is not the objective of what this is for, right? It's if a game designer is working on something, they care about the game engine, the state. It's it can look whatever. You can fix that up later or you can have a really good game state and you can quickly edit it to 20 20 different versions that keep state,

</details>

**Chris**: 对吧？所以这是一个非常重要的区别，嗯，对于**Moonlake**的优势而言，对吧？所以，是的，我的意思是，你知道，精美的视觉效果在几秒钟内看起来很可爱，但游戏真正的核心是**概念**、**游戏玩法**，你知道，很多时候，这甚至不需要精美的视觉效果。我的意思是，有很多非常成功的游戏，它们的视觉效果相对原始，而有些游戏人们花费数百万制作**照片级真实感**的视觉效果，但游戏却很烂，对吧？嗯，所以，嗯，在思考世界模型中什么重要时，将这两个轴分开是非常重要的。这次对话让我想起了我在非AI生活中曾有过的**游戏评论**和**小说讨论**。呃，有些人可能知道**Brandon Sanderson**，他是一位非常著名的**小说作家**，他是一位狂热的游戏评论家，他非常喜欢那些你改变了关于世界的一个正常假设的视频游戏。例如，**Baba is You**。我不知道你有没有遇到过，就像游戏规则会随着你的游戏而改变，还有就是，你知道，你可以选择性地**逆转时间**，或者选择性地**改变重力**。我认为这也会让我想起其他类型的由作家创造的世界模型，**Ted Chiang**就是我的典型例子，他会带你进入你今天所知的世界，但只改变其中一件事，然后在此基础上创造一个一致的世界。呃，我长篇大论地说，是否很容易创造出不存在的替代规则，但你只改变一件事，然后让一大群人去尝试，看看它是否有效。我的第一个回答是，使用像**Moonlake**这样的技术，这似乎比使用其他世界模型更容易，也更具可操作性。嗯，**Sun**可以做到这一点。我让他给出第二个答案。

<details>
<summary>Original English</summary>

**Chris**: right? So that's a really important distinction um for and for speaking to Moonlike strength, right? So yeah, I mean, you know, great visuals are lovely to look at for a few seconds, but games are really all about the concept, the game play, and you know, a lot of the time that doesn't actually even require great visuals. I mean there are just lots of very successful games which have relatively primitive visuals and there are other games where people have spent millions producing photorealistic um visuals and the game sucks, right? Um so um keeping those two axes apart is really important in thinking about what's important in a world model for different uses. This conversation is reminding me of some game review and fiction discussions I've um had in my sort of non-AI related life. Uh some people might know Brandon Sanderson who's a very famous uh fiction author uh had is is a big big game reviewer and he he's a big fan of video games where you change one thing about a normal what what you might assume about the world. For example, Baba is you. I don't know if you might have come across that where like the rules change as you play the game and also like where you know you can do things like reverse time selectively or like change gravity selectively and I think this is also remind reminds me of other kinds of world models that are created by authors where Ted Chang is is my typical example where he'll take the world that you know today but change one thing about it and but then create a consistent world based on that. uh which is longwinded as of me of for me to say is is it easy to create alternative rules that don't exist but you change one thing and then let's let's run a whole bunch of people through it to see if it works. My first answer will be that seems a lot easier and more conceivable to do using techn technology like moon lakes than with some of the other world models out there um where the sun can actually make it happen. I'll let him give the second answer.

</details>

**Sun**: 如果我猜，你被**游戏引擎工具**所束缚，对吧？就像归根结底，那就是你拥有的**思想伙伴**。如果我要求一些东西，比如它永远不允许**逆转时间**，或者**重力**永远只以一种方式工作，那么，好吧，就是这样。但有时**重力**可能会改变。但用代码改变比用主要基于真实世界数据和虚拟世界数据学习的模型要容易得多，例如**Genie**，它实际上是基于大量真实世界数据和大量虚拟游戏数据训练的，很难说，好吧，也许改变视觉效果，比如世界的时间段很容易，比如你无法改变**重力**。

<details>
<summary>Original English</summary>

**Sun**: If I guess for you, you're constrained by the game engine tool, right? Like at the end of the day, that's the that's the thought um partner that you have. If I ask for something where like if it never is allowed to reverse time or if gravity only ever works one way, then well, that's it. But sometimes gravity might change. But it's a lot easier to change with code as opposed to a model that is learned primarily on data of real world and virtual worlds that are I guess like for example Genie right like there's actually train on a lot of real world data and a lot of virtual gaming data and it's hard to say well maybe it's easy to say okay I want to change the visuals in like the time period of of the world like you can't change gravity for example

</details>

**主持人**: 我觉得你可以做到轻微的程度，对吧？所有事情都归结为**代码**是执行它的更好方式。但模型并没有那么多样化和创造性，对吧？你可以说，“好吧，让**重力**变慢。”它可以做到，但它受限于你用文本表达它的方式，对吧？就像它们只会进行几次迭代，而通过编程，你知道，如果有一个游戏引擎在底层，你可以随心所欲，对吧？所以，我认为大多数模型的一个局限性是它们**过度训练**于一种风格，对吧？而且提取**多样性**非常困难，至少这是我们所看到的。我的意思是，你有没有想到现有模型中，无需使用代码就可以更容易做到某些事情的例子，比如某些类型的**创作意图**或**状态转换**？

<details>
<summary>Original English</summary>

**主持人**: I feel like you can to light bounds right everything comes comes down to like code is a better way to execute it. But the models aren't that diverse and creative, right? You can say, "Okay, make gravity slower." It can do that, but it's limited to your representation of how you text it out, right? Like they're they're only going to do a few iterations, whereas programmatically, you know, if there's a game engine under the hood, you can you can kind of go wild, right? So, one of the I don't know, one of the limitations of most models is that they're very overtrained to one style, right? and extracting diversity is pretty difficult at least that's something we've seen. I mean are there examples you have in mind where existing models it like it would be easier to do that's not using code like certain types of creative intent or like

</details>

**Sun**: **剪裁**，呃，其他模型，其他世界模型非常擅长**剪裁**。

<details>
<summary>Original English</summary>

**Sun**: clipping uh other models other world models are very good at clipping through things

</details>

**主持人**: 我的腿穿过一块石头。

<details>
<summary>Original English</summary>

**主持人**: clipping my my legs clipping through a rock

</details>

**Sun**: 因为，因为你知道，这只是，这只是不好。

<details>
<summary>Original English</summary>

**Sun**: because because it's you know it's just it's just bad

</details>

**主持人**: 就像你必须非常努力地使用你的东西才能真正做到这一点，呃，我认为这可能是一个你实际上准备好的话题，呃，**高斯泼溅**与呃，其他的东西。

<details>
<summary>Original English</summary>

**主持人**: like you would have to struggle very hard with your your stuff to actually make that uh which I think is maybe a topic that you actually prepared on uh gshian splatting versus uh the other stuff.

</details>

**主持人**: 是的。是的。对于那些不太熟悉的人来说，对吧？有**高斯泼溅**，有**扩散模型**，什么可行，什么可以扩展。我觉得在二月份**Sora**出来的时候，那篇博文的标题就是——

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. It's just for those not super familiar right there's a there's gshin splatting there is diffusion like what works what scales up. I feel like in February when sor one came out the the blog post was literally titled like

</details>

**Sun**: 我们每天都提它。

<details>
<summary>Original English</summary>

**Sun**: we bring it up and every day

</details>

**主持人**: 你知道，世界视频生成模型就是世界模拟器。呃，它非常**惨痛的教训**化。是的。很多都是**涌现**，对吧？所以，呃，不去看他们的博文。基本上，他们整件事就是当你扩大规模时，所有这些一致性，所有这些东西都解决了。这是一个非常简单的前提，对吧？他们只是扩大了**扩散模型**。从那时起，你知道，这是2024年2月。我们能做多少？这已经两年了，基本上是五年。你知道，我们还需要多少AI时间才能扩大规模，或者我们是否会达到数据上限？但我想我们已经谈论了很多，对吧？就像这又回到了我们最初讨论的，什么适合当时，这似乎是你们的方法，对吧？

<details>
<summary>Original English</summary>

**主持人**: you know world world video generation models are world simulators. Uh it's super bitter lesson pilled. Yeah. A lot of it is emergence, right? So, uh not to go through their blog post. Basically, their whole thing was as you scale up all this consistency, all this stuff just kind of solves. It's a very simple premise, right? They just scaled up diffusion. And from there, you know, this is this is Feb 2024. How much can we It's already been 2 years, which is basically 5 years. You know, how much more AI time do we need to just scale up or or do we hit a data cap? But I think we already talked about this a lot, right? like this is back to the beginning discussion of what's appropriate for the time and that seems like your approach, right?

</details>

**Sun**: 是的。我想表达的观点是，存在非常非常多种类的**世界模拟器**，而且拥有一个能够产生**像素连贯性**的世界模拟器对于游戏、营销和所有这些事情都非常有用，但它在**因果推理**和**具身AI**方面并没有人们想象的那么有用。是的，这个标题是真的，我们并不是说它，你知道，不是一个很棒的世界模拟器。但实际上，在我们写的博文中，我们的赌注更多是，在真实世界任务和虚拟任务中，将会有不成比例的巨大价值份额，其中不需要**高分辨率像素保真度**，是的，视频模型有其价值。是的，这已经达到了我对物理学的绝对理解极限，但我想到的一个例子基本上是在一个**确定性世界**中解决类似**三体问题**的问题，而视频模型只会近似地解决，足够好。

<details>
<summary>Original English</summary>

**Sun**: Yeah. The point I'm trying to make is that there are very many many different types of world simulators and like having a world simulator that can produce pixel coherency is very very useful for games and you know marketing and all these things but it's not as useful as people think when it comes to causal reasoning when it comes to embodied AI and yeah like it this this title is true like we're not saying that it's it's like you know not a great world simulator. But actually in the blog that we we we we wrote the bet is more so that there are going to be disproportionately large share of value of real world task and virtual tasks where high resolution pixel fidelity is not needed and yes video models have their values. Yeah, this is at the absolute limit of my physics understanding, but one example that comes to mind is basically having to solve like bas the equivalent of a threebody problem in a deterministic world whereas the video models would just approximate it. Good enough.

</details>

**主持人**: 是的。对。就像在某个点上，你的方法会遇到这样的问题：好吧，你现在必须模拟世界。非常感谢。就像你正在努力做到这一点，但仅仅在游戏引擎允许的范围内，而且游戏引擎无法做一些事情。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Right. Like there's there's some point at which your approach kind of runs into like the well you now have to simulate the world please. Thank you very much. And like you're you're trying to do that but only to the extent that the game engine lets you and like game engines cannot do some things.

</details>

**Sun**: 是的。不，我的意思是，我认为这里有趣或更具技术性的问题实际上是，你如何在**扩散先验**和**符号先验**之间划定界限。是的。而且这条界限实际上可以是流动的。就像我想，也许你想表达的是，好吧，人们说**像素先验**一切。但我们说的是，好吧，我们划定了一条界限，这是我们认为为我们今天关心的领域和事物提供最具经济价值的地方。我实际上确实认为，而且这也是我们内部一直做的事情，那就是，好吧，考虑到我们学到的新方程，或者我们学到的世界新元素，或者也许我们在开发模型过程中获得的其他知识。我们是否应该继续保持这条线，就像今天这样，还是应该稍微向左或向右移动一点？对吧。就像有时我们意识到，哦，也许客户或其他人想要某些用**像素先验**而不是**符号先验**更好地处理的事情。

<details>
<summary>Original English</summary>

**Sun**: Yeah. No, I mean I I think the the interesting or more technical question here actually is where do you draw the boundary between what's handled with let's say diffusion prior and when and what's handled with symbolic prior. Yes. And right this boundary can actually be fluid. Like I think like maybe what you're trying to get at is like okay people are saying pixel prior everything but what we're saying is okay there's a boundary that we draw where this is where we think provides the most economical value for the domains and things that we care about today. And I actually do think and it's something that we do internally all the time which is like okay given new equations that we learn or new elements of the world and that we we learn or maybe some other knowledge that we acquire in the process developing the models. Should we still be maintaining this line exactly as it is today or should we move it a little bit left or a little bit right? Right. Like sometimes that we realize that oh like maybe customers or or folks like want certain things that are better handled with pixel prior as opposed to um symbolic prior.

</details>

**主持人**: 是的。你的**皮肤**理论是一个向右移动的例子。是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Your your skin thing is a is a example moving it right. Yeah.

</details>

**主持人**: 嗯

<details>
<summary>Original English</summary>

**主持人**: Um

</details>

**主持人**: 还是向左，我不知道左右是什么。

<details>
<summary>Original English</summary>

**主持人**: or left I don't know what the left right is.

</details>

**Sun**: 是的。是的。是的。不，**Rey模型**。是的。实际上我们有几个版本的它们。它们实际上略有不同。

<details>
<summary>Original English</summary>

**Sun**: Yeah. Yeah. Yeah. No the the the the revery model. Yes. Actually we have a few iterations of them. They're actually at slightly different

</details>

**主持人**: 我知道。你应该，你应该那样做。这是一个很酷的维度可以展示。

<details>
<summary>Original English</summary>

**主持人**: I know. You should you should do that. That's a cool dimension to show.

</details>

**主持人**: 是**量子力学**是我们世界的**扩散先验**吗？对吧？就像那是**经典力学**与**量子力学**的边界，对吧？就像就是那样，对吧？在一个点上，上帝掷骰子，而在另一个点上则没有。

<details>
<summary>Original English</summary>

**主持人**: Yeah. is quantum mechanics the diffusion prior of our world right it's like that's the boundary of classical mechanics versus quantum right like that's it right at one point God plays dice and the other point doesn't

</details>

**Sun**: 我不知道**Chris**你是否想说，但我认为我总觉得**物理学**用**符号先验**会更好。

<details>
<summary>Original English</summary>

**Sun**: I don't know I don't know if Chris you want to say but I think I think generally I feel like physics is better with symbolic prior um

</details>

**主持人**: 甚至是**量子物理学**。

<details>
<summary>Original English</summary>

**主持人**: even quantum physics

</details>

**Sun**: 甚至是**量子物理学**，是的。

<details>
<summary>Original English</summary>

**Sun**: even quantum physics yeah

</details>

**Chris**: 这开始进入我所说的**MLST领域**，他喜欢变得哲学化。我们相当友好。

<details>
<summary>Original English</summary>

**Chris**: this is start to um MLST territory is is what I call it where he he likes to get philosoph ical. We're we're quite friendly.

</details>

**主持人**: 我的意思是，我们需要获得，我们需要获得**奇点**。我听到了一些。

<details>
<summary>Original English</summary>

**主持人**: I mean, we need to get we need to get singularity. I heard some of that.

</details>

### 商业化、应用场景与招聘

**主持人**: 不，不，我认为这实际上非常有帮助。而且，伙计，我只想让你**产品化**这个。作为一名产品经理，我只是想，好吧，作为一名玩家，你知道，我想成为一名研究员，你知道，就像这很酷，这是一种理论上的，就像你有一个非常好的，我不知道，就像思考这些事情的方式，但我只是想看到你，你知道，表达它。我确实认为，当你开放新的工具时，你从根本上改变了事物，就像，好吧，使用人类意图将其融入到你的渲染方式中。好吧，艺术家将不得不花两到三年时间来弄清楚如何处理这个问题，而你只是不知道。

<details>
<summary>Original English</summary>

**主持人**: No, no, I think that is actually really helpful. And uh man, I just want you to productize this. Like as a product guy, I'm just like, well, as a gamer, you know, I want to researcher, you know, like it's cool like this this is a theor theoretical like you have a very good I don't know like the way of thinking about these things, but I just want to see you like, you know, express it. I do think like you're fundamentally things when you leave open new tools like okay use use human intent to incorporate it into how you render. Well, artists are going to have to take like two to three years to figure out what to do with this and you just don't know like

</details>

**Chris**: 但我认为，你知道，这提供了一个更易于接近和可控的世界，**NLP**的美妙之处在于，这将使其能够被采用和使用，我们对此非常乐观。

<details>
<summary>Original English</summary>

**Chris**: but I think you know this is um gives a much more approachable and controllable world for the beauty of NLP that that will enable it to be adopted and used and we're very hopeful about that.

</details>

**主持人**: 是的。是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah.

</details>

**Sun**: 是的。我的意思是，我们实际上非常专注于**商业化**，从这个意义上说，我们确实非常相信**数据飞轮**方法，在这种方法中，我们将它交到创作者和用户手中，然后他们会教我们何时以及何种能力或模型应该改进，这就是为什么我们实际上是，你知道，像测试版产品一样。

<details>
<summary>Original English</summary>

**Sun**: Yeah. I mean we are we are very focused actually on commercialization in the sense that like we do we do really believe in the data flywheel approach where um we put this in the hands of the creators and the users and then they will teach us when what capability or model should improve and that's why we are we are actually you know like products in beta

</details>

**主持人**: 是的，专注于游戏，游戏领域有什么相邻的东西？

<details>
<summary>Original English</summary>

**主持人**: yeah focusing on gaming what what's like the adjacent thing to gaming

</details>

**Sun**: 基本上是具身AI。所以也许我们可以，我可以，我可能会从我们看到这个平台三年后的样子开始，那就是，好吧，用户会告诉我们他们想实现什么。最终目标可能是，嘿，我只是想制作一些东西来教我的孩子谦逊的价值。嗯，或者它可能是我想要微调我的无人机，使其在救援情况下表现出色。我可能是扫地机器人。我想训练我的操作或像扫地机器人一样，使其在我的办公室里非常健壮，对吧？但就像无论它是什么。

<details>
<summary>Original English</summary>

**Sun**: embody basically so maybe we can we can I I'll maybe start with where we see the platform in three years which is like, okay, the users would tell us what they want to achieve. The end goal could be, hey, I just I want to make something to teach my kids the value of humility. Um, or it could be, hey, I want to fine-tune my um drones to be really good at rescue situations. I could be vacuum robots. I want to like train my manipulation or like vacuum robot to be very robust to my office, right? But it's like whatever it is

</details>

**主持人**: 在我的办公室里。

<details>
<summary>Original English</summary>

**主持人**: in my office

</details>

**Sun**: 像在我的办公室里非常健壮地导航。但后来它就像无论你想要什么最终目标，我们的世界模型都会说，好吧，给定你想要实现的目标，让我生成一个环境分布，以便我可以训练和评估你想要的任何东西。是的。对。也许出于游戏的目的，它只是最终的模拟，那就是最终产品。对于某些策略。就像我可以在这些环境中训练它，然后帮助你看到你的策略在哪里失败或没有失败，然后你知道，所以我想——

<details>
<summary>Original English</summary>

**Sun**: like navigate very robustly with in my office. But then it's like whatever end goal that you want our world model will say okay given what you want to achieve let me generate a distribution of environments such that I can train and evaluate whatever it is you want. Yeah. Right. Maybe for the purpose of games it's just the end simulation and that's the end product. for certain policies. It's like I can train it within these environments and then help you see where your policy is failing or not and then you know so I think

</details>

**主持人**: 所以在这种情况下，它更多的是一种训练工具，而不是其他。

<details>
<summary>Original English</summary>

**主持人**: so in that case much more of a training tool than in other

</details>

**Sun**: 训练和评估，两者兼顾，对吧？

<details>
<summary>Original English</summary>

**Sun**: training evaluation both right

</details>

**主持人**: 当然，一样。

<details>
<summary>Original English</summary>

**主持人**: sure same same thing

</details>

**Sun**: 我认为它只是这个**世界模型**，它允许人们训练任何策略，这些策略可以在任何**多模态环境**中行动。

<details>
<summary>Original English</summary>

**Sun**: I think it's just this world model that allows people to train any policy that can act in any multimodal environments

</details>

**主持人**: 奖励欺骗会更难吗？有没有一个角度让奖励欺骗更难？就像我只是笼统地说，因为我认为这是很多人在这些环境中训练智能体时面临的一个关键问题，我不知道你能解决它吗？

<details>
<summary>Original English</summary>

**主持人**: would it be harder to reward hack is there an angle here where it is harder to reward hack like just I'll just put it generally because I think that's a that's obviously a key problem that a lot of people face when in when training agents in these environments and I don't know can you solve it

</details>

**Chris**: 我认为不一定。我的意思是，在某种程度上，存在一个错误的奖励，它似乎可以在一个更符号化的世界或一个更基于像素的世界中被欺骗。嗯，我不知道**Sun**有什么想法，但我认为这并没有真正得到解决。

<details>
<summary>Original English</summary>

**Chris**: I think not necessarily I mean to the extent that there's a misspecified reward that it seems like it could be hacked in a more symbolic world or in a more pixelbased world um I don't know if son's got any thoughts but I don't think that's really being solved

</details>

**主持人**: 另一件事是，你也可以构建一个更好的**Sora**作为**视频生成模型**，对吧？因为那样你就会把**扩散**方面推向右边一点。我想如果我把方向弄对了，嗯，就是这样。

<details>
<summary>Original English</summary>

**主持人**: the other thing that comes to mind is just you could just build a better Sora as a videogenerated model, right? Because then you you would move the diffusion uh side a bit more further to the right. I think if I got the directionality correct um and that's it.

</details>

**Sun**: 它在领域上更好，对吧？就像**一致性**现在是否存在，或者某些东西是否存在，对吧？

<details>
<summary>Original English</summary>

**Sun**: It's better on domains, right? Like on consistency over now or for sure it exists versus something doesn't, right?

</details>

**主持人**: 所以——

<details>
<summary>Original English</summary>

**主持人**: So

</details>

**Sun**: 是的，

<details>
<summary>Original English</summary>

**Sun**: yeah,

</details>

**主持人**: 你的问题更像是——

<details>
<summary>Original English</summary>

**主持人**: is your question more like like

</details>

**主持人**: 我只是在胡思乱想，就像你能用你拥有的东西构建什么？我确实认为思想或学术会立即转向**训练**和**评估**，但艺术往往会采取不寻常的方向，就像你最终可能会——

<details>
<summary>Original English</summary>

**主持人**: I'm just riffing on like how do you what can you build, you know, with the stuff that you have? I do think that the mind or the academic does go immediately to training and in evaluation but like art tends to take unusual directions like you might end up

</details>

**Chris**: 好的，是的，但问题是，你能用这个软件开发引人入胜的**游戏玩法**吗？

<details>
<summary>Original English</summary>

**Chris**: okay yeah but the question is can you use this piece of software to develop compelling gameplay and

</details>

**Chris**: 我认为你不能用**Sora**制作引人入胜的**游戏玩法**，对吧？如果你想拥有一个可以漫游的世界，那很好，但你实现**游戏机制**的能力如何？你希望它们以何种方式实现？以及事物如何保持，你知道，与你的**游戏玩法**的**长期历史**一致，影响未来的行动。我认为那里根本没有这样的东西。

<details>
<summary>Original English</summary>

**Chris**: I don't think you can take sore and produce compelling gameplay right if you want to have a world that you can wander around in a bit you're good but what are your ability abilities to have gameplay mechanics implemented the way you'd like them to be and to have things stay, you know, with the long-term history of your gameplay that influences future actions. I think there's just nothing there for that.

</details>

**主持人**: 是的，我确实倾向于同意。我只是想测试一下边界。我还想指出，随着**AAA游戏产业**的发展，**电影**和**游戏**之间的界限已经模糊了。嗯，你最终基本上是在制作一部两小时的电影，作为你团队的一部分。

<details>
<summary>Original English</summary>

**主持人**: Yeah, I do tend to agree. I I'm just trying to sort of test the boundaries. I would also make the observation that as AAA games industry has developed, the line between what is a movie and what is a game has blurred. Um, and you you you do end up basically producing a two-hour movie as part of your team.

</details>

**Sun**: 嗯，不，老实说，我们的**世界模型**实际上在**相邻市场**中有许多应用。

<details>
<summary>Original English</summary>

**Sun**: Um, no, honestly, there there's so many actually applications in adjacent markets that our world model can go into.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**Sun**: 但是的，这样胡思乱想很有趣。尽管在执行方面，我们必须专注于，好吧，我们想随着时间解锁哪些能力，并为此制定了**路线图**。但是的，如果我们只是胡思乱想可能性，我觉得它是不是无穷无尽的。是的，这很经典。在我看来，可能性和列表的嵌入非常接近。

<details>
<summary>Original English</summary>

**Sun**: But yeah, it's sort of fun to riff riff on. Although on the execution side, we sort of we we need to stay focused with like, okay, what are the capabilities we want to unlock over time and there's a road map for that. But yeah, if we're just ripping on sort of like the possibilities, I feel like whether it's endless. Yeah, it's like classic. the embedding for possibility and list in my mind is very close.

</details>

**主持人**: 是的，我确实想专注于一个奇怪的选择。我不知道它是否奇怪。也许我在这里有什么发现。呃，**音频**，对吧？你本可以说没有音频，而音频在我看来有很多递归性，而在视频中你只需要做**光线投射**，这在计算上要简单得多。音频似乎要困难得多。我不知道你是否想评论一下**空间3D音频问题**。你真的必须这样做吗？我想你必须这样做才能身临其境，但很多人确实认为它就像，好吧，你只是在上面放了一个**TTS模型**。

<details>
<summary>Original English</summary>

**主持人**: Yeah, I do want to uh focus on one like weird choice. I I don't know if it's weird. Maybe I'm I got something here. Uh audio, right? You could have just said no audio and audio in my mind has a lot of recursion whereas in in video you can just do ray casting and that's much computationally much simpler. Audio just seems way harder. I don't know if you want to just comment on just the spatial 3D audio problem. Did you really have to do it? I I guess you do to be immersive, but like a lot of people do treat it as like, well, you just stick a a TTS model on top of

</details>

**Chris**: 游戏音频不仅仅是语音，对吧？不仅仅是**TTS**。

<details>
<summary>Original English</summary>

**Chris**: Well, there's a lot more to game audio than just speech, right? It's not just TTS.

</details>

**主持人**: **TTS**、**SFX**、**DGM**

<details>
<summary>Original English</summary>

**主持人**: TTS, SFX, DGM

</details>

**主持人**: 空间上，在我看来，**回声**。

<details>
<summary>Original English</summary>

**主持人**: spatial in my mind, echoes.

</details>

**Chris**: 是的。

<details>
<summary>Original English</summary>

**Chris**: Yeah.

</details>

**主持人**: 和**反射**。我什至不知道还有什么。我不知道这个领域还有哪些问题。

<details>
<summary>Original English</summary>

**主持人**: And reflections. And I I don't even know what's what else. I don't I don't know what what other problems in this space.

</details>

**Sun**: 是的，我认为这一点，这有点更指向使用**游戏引擎**作为模型可用的工具的好处，对吧？因为**空间音频**的一部分来自模拟底层的代码。虽然我们确实让我们的模型可以访问其他类型的**音频模型**作为工具，

<details>
<summary>Original English</summary>

**Sun**: Yeah, I think this point like the is sort of a more more pointing to the benefits of using an game engine as a tool that's available to the model, right? Because like part of the spatial audio is from the code that is underlying the simulation. And while we do give our model access to other types of audio models as tools,

</details>

**主持人**: 我认为它们都不会是空间的。

<details>
<summary>Original English</summary>

**主持人**: none of them would be spatial, I think.

</details>

**Sun**: 对。但这正是我们提供模型抽象或工具套件的更多要点，以便它能够实现这一点。你可以争辩说，**空间性**有点像我们提供给智能体的工具和抽象的**涌现**。我认为这就是这种方法的美妙之处，就像有很多东西，就像人类如何构建技术，它们就像彼此构建的**乐高积木**一样，这里也是一样，就像会有一些东西，所以它只是从能够以**组合上有趣**的方式将这些东西组合在一起中涌现出来。

<details>
<summary>Original English</summary>

**Sun**: Right. But that's exactly sort of more point to we're giving our model an abstraction or a suite of tools such that it's able to achieve that. And you can argue that sort of spatial is like a like emergence out of the the tools that we and abstraction that we provide to the agents. And I think that's the beauty of this this this approach is like there's a lot of things kind of like how humanity's built technology and they're like Lego blocks that build on top of each other and it's the same thing here like there's going to be things that so just sort of emerges from being able to put these things together in like combinatorily interesting ways

</details>

**Chris**: 对，所以这个集成的**音频模型**利用了**Moonlake**世界的理解和语义，对吧？而对于一般的**生成式AI视频模型**来说，根本没有实际的音频集成，对吧？有人可能会在视频上加上一些音乐或**音景**或其他东西，所以它不是一个无声视频，但它们根本没有连接到一个**一致的世界模型**中，也没有任何东西可以说，好吧。视频中正在发生一个动作。因此，应该从视觉场中的这个部分发出声音。

<details>
<summary>Original English</summary>

**Chris**: right so this integrated audio model exploits the understanding and semantics of the moon lake world right and whereas in general role for the Gen AI video models, there's no actual integration across to audio at all, right? That someone might stick some music or stick a soundsscape or whatever else on top of their video so it's not a silent video, but they're in no way connected into a consistent world model and there's nothing that's okay. An action is happening in the video. Therefore, there should be a sound that's coming from this part of the visual field.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**主持人**: 这和**Sora 2**不一样吗？它没有音频吗？不是说它不像——

<details>
<summary>Original English</summary>

**主持人**: Is that different than Sora 2? Does it not have audio? Not to say it's not like

</details>

**Sun**: 它没有**空间音频**。

<details>
<summary>Original English</summary>

**Sun**: doesn't have spatial audio.

</details>

**主持人**: 它没有。

<details>
<summary>Original English</summary>

**主持人**: It doesn't.

</details>

**主持人**: 不，我已经玩过很多次了。它听起来就像有人在上面放了一个**11 Labs**的声音，然后只是试图做**唇形同步**。

<details>
<summary>Original English</summary>

**主持人**: No, I've I've played around with it enough. It just sounds like someone put an 11 Labs voice on top of it and just tried to do the lip syn.

</details>

**Chris**: 我的意思是，我见过，好吧。生成一只狗在海滩上，对巨浪的反应，然后四处移动。它绝对是，就像让狗远离镜头，看看声音是否会下降。

<details>
<summary>Original English</summary>

**Chris**: I mean, I've seen Okay. Generate a dog at the beach and reactions to big wave and move around. It's definitely like have the dog have the dog move away from camera and see if the the sound goes down

</details>

**主持人**: 或者没有，对吧？因为它们没有**空间音频**。

<details>
<summary>Original English</summary>

**主持人**: or it doesn't, right? Cuz they don't have spatial audio.

</details>

**Sun**: 我们确实想基本上，就像我们，我们的模型，我们正在训练的模型，基本上是朝着拥有所有这些不同模态的组合**潜在表示**的目标前进的，对吧？这样你就可以跨这些不同模态进行推理。嗯，所以例如，如果我闭上眼睛，你播放一个视频，你播放汽车从我身边滑过的声音，我几乎可以在脑海中视觉化地推断出那个轨迹。我认为那种能力，我们希望我们的模型能够进行推理，对吧？这就是我们采取这种**多模态推理方法**的原因。就像我们想要这种组合**潜在空间**，它可以，是的。哦，你说**潜在空间**。我们喜欢这里。我们必须每次有人说“in space”时都敲响铃。呃，不。你必须训练**Daredevil**一个，你只有音频，但你必须弄清楚所有东西在哪里。

<details>
<summary>Original English</summary>

**Sun**: We do want to basically like we our model like the one we're training is basically towards the goal of having a combined lat representation across all these different modalities, right? Such that you can like reason across these different modalities. Um, so for example, if I close my eyes and like you play a video, you play a sound of like a car skidding away from me, I almost can like visually extrapolate that trajectory in my mind. And I think that that type of capability, we want our model to be able to reason, right? And that's the reason that we're sort of taking this multimodal reasoning approach. It's like we want this combined lat space that can Yeah. Oh, you said lat space. We like that here. We have to play the the bell every time that someone says in space. Uh, no. You got to train Daredevil one where you you it's only audio but you have to work out where everything is.

</details>

**主持人**: 酷。我想这就是我们对**Moonlake**的全部报道了。呃，我想我们还有几个关于**Chris Manning**的**信息检索**问题，以及任何其他关于**注意力机制**或**自然语言处理**的话题。

<details>
<summary>Original English</summary>

**主持人**: Cool. I think that that was that was about it for our Moon Lake coverage. Uh, I do think we have like a couple of uh Chris Madding questions on on IR and and uh just any any other sort of attention topics or N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N N L topics.

</details>

**Chris**: 好的。

<details>
<summary>Original English</summary>

**Chris**: Okay,

</details>

**主持人**: 说吧。

<details>
<summary>Original English</summary>

**主持人**: go ahead.

</details>

**Chris**: 哦，不。我的意思是，是的，这很有趣。呃，你知道我们谈论了你们是如何相遇的，但你基本上是**NLP**的教父，对吧？你从早期的**嵌入**、早期的**注意力机制**，你做了2015年的**机器翻译注意力机制**，所有这些，呃，你拥有**信息检索**，所以在**RAG**之前就有**RAG**，你知道我们只是想大声说出来并钦佩很多东西，对吧？那么是什么促使你转向**世界模型**呢？这一切是如何发生的？

<details>
<summary>Original English</summary>

**Chris**: Oh, no. I mean, yeah, it's just fun. uh you know we talked a bit about how you guys met but you basically you you were like the godfather of NLP per se right you spent the whole career from early embeddings early early attention you did 2015 attention for machine translation everything uh you you had information retrieval so rag before rag you know we just want to shout that out and admire a lot of that right so what prompted the switch over to world models how how'd all that come about

</details>

**Chris**: 部分答案是学生的**热情**和**创造力**，但这里有一点历史，对吧？所以是的，我的职业生涯大部分时间显然都在做与语言相关的事情，你知道我是如何进入研究领域的，我当时想，啊，人类如何能实时产生语音并相互理解，这真是太神奇了，他们是如何在小时候学会语言的，这怎么可能发生呢？所以是的，一开始我非常专注于**语言**。但你知道，当它进入2010年代时，我开始，你知道，我一直在研究**问答**，然后我开始对**视觉问答**产生兴趣，这是一个非常明显视觉理解很差的领域。对吧？你知道，那些日子，就像几乎没有视觉理解一样。你只会得到来自先验的答案。所以，你知道，如果你问桌子上有多少人，它总是回答2，无论你在图片中能看到多少人。你知道，所以这似乎，啊，这些模型实际上无法从图像中获取**语义信息**。所以我对这个问题很感兴趣，并试图在这方面做更多工作。然后事情开始，你知道，**生成式AI图像**的革命开始了，然后我在**Moonlake**时代之前有学生开始研究这个。我还和创立**PA**的**Demis Hassabis**一起工作。嗯，所以——

<details>
<summary>Original English</summary>

**Chris**: to some answer it is um the enthusiasms and creativity of students but there's a bit of a history there right so yeah so clearly most of my career has been doing stuff with language and you know how I got into research was thinking ah this is just so amazing how humans can produce speech and understand each other in real time and somehow they managed to learn languages when they're kids how could this possibly happen and so yeah starting off I was very focused on language But you know as it sort of got into the 20110s I started you know going I'd been working on question answering and then I started to get um interest in visual question answering and that was an area where it was very noticeable that the visual understanding was bad. Right? You know, these were the days when like it sort of seemed like there was almost no visual understanding. You were just getting answers that came from prior. So, you know, if you asked how many people are sitting at the table, it always answer to regardless of how many how many people you could see in the picture. And you know, so it seemed like ah these models actually aren't able to get semantic information out of images. And so I was interested in that problem and tried to work more on that. And so then that required knowing more about what's happening in vision and how you can represent visual information. And then things start, you know, there started to be this revolution of um doing generative AI images and then I had students that started looking at that before the era of Moon Lake. I was also working with Demi Gore who founded PA. Um and so

</details>

**主持人**: 还有**Ian Goodfellow**显然与**GANs**有关。

<details>
<summary>Original English</summary>

**主持人**: and Ian obviously with Gans.

</details>

**Chris**: 是的。虽然**Ian**从未是我的学生，但是的，**Ian**，我对他和**GANs**的整个十年都非常了解。是的。我的意思是，**Ian**是**斯坦福**的本科生，但是的——

<details>
<summary>Original English</summary>

**Chris**: Yeah. Though Ian was never my student but yeah Ian I I was very aware for the the whole decade there of Ian with GANs. Yeah. And I mean Ian was a Stanford undergrad but yeah

</details>

**主持人**: **Richard Dyouu.com**我想他是你的学生。嗯——

<details>
<summary>Original English</summary>

**主持人**: Richard Dyouu.com I believe he was your student. Um

</details>

**Chris**: 嗯，是的，你知道，那个阶段也有一些联系。所以我的意思是，你知道，那个时代有一些论文是关于我指的是**Andre Karpathy**是一位博士生，与**Richard**同时期，所以那个时代也有一些**语言视觉联合工作**，你知道，以现代标准来看，这似乎有点古老，但是的，我们正在尝试从**文本依赖图**到**视觉场景**。

<details>
<summary>Original English</summary>

**Chris**: um yeah and you know there were there were links across at that stage as well. So I mean you know there were several papers in that era of doing I mean so Andre Kapathy was a um PhD student at the same time as Richard and so there was some joint language vision work in that era as well you know it seems kind of ancient by modern standards but yeah we're trying to go from sort of textual dependency graphs to visual scenes

</details>

**主持人**: 当时**GloVe嵌入**确实取代了大量的**TF**，比如**one-hot编码**，我们看到的早期**视觉语言模型**就像**LAVA风格的适配器**，对吧？它从技术上讲仍然只是嵌入**潜在空间**，让我们添加图像，让我们混合模态。所以，那是你们超级提出的其中一件事，对吧？

<details>
<summary>Original English</summary>

**主持人**: at a time the glove embeddings really took over a lot of TF like one hot encoding all that the early vision language models we saw were like lava style adapters, right? It's it's technically still just embedding latent space, let's add image, let's mix modality. So, and that that's one of the things you super put out there too, right?

</details>

**Chris**: 是的。

<details>
<summary>Original English</summary>

**Chris**: Yeah.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**主持人**: Yeah.

</details>

**主持人**: 是的。嗯，非常感谢这一切。感谢你们在**世界建模**方面推动了世界的发展。呃，我真的认为如果人们深入理解我们刚刚涵盖的一切，他们就会看到未来。而且我认为你们，你知道，在这里做出了非常重要的贡献。你们正在招聘什么？你知道，哪里可以找到你们？你知道，我们同意**CTA**是一个招聘电话。是的。我的意思是，我们不是已经拥有**AGI**了吗？你不再需要工程师了，对吧？

<details>
<summary>Original English</summary>

**主持人**: Yeah. Well, thank you for all of that. Thank you for advancing the world on uh world modeling. Uh I honestly do think that if people deeply understand everything we just covered, they will see what's coming. And I think you guys have, you know, made some really significant contribution here. What are you hiring for? You know what what is the where do people find you? You know, we we agreed that the CTA was a hiring call. Yeah. I mean, don't we have AGI? You don't need you don't need engineers anymore, right?

</details>

**Sun**: 是的。在模型方面，我们实际上正在努力构建一个**自我改进系统**。但这意味着我们需要人来设置这个自我改进系统。嗯，所以更具体地说，是那些在**代码生成**、**计算机视觉**和**图形学**方面拥有交叉知识的人，对吧？这就是我们在团队中寻找的核心研究背景，而且我们团队的大多数人今天都拥有这两种背景。

<details>
<summary>Original English</summary>

**Sun**: Yeah. On the model side, we we are actually striving towards basically a self-improving system. But what that means is that we need people to set up the self-improving system. Um so more specifically people who have the intersection of knowledge within code generation and computer vision and graphics, right? That's that's sort of the core research background that we look for within our team and and the majority of the team today do have like both backgrounds. Um

</details>

**主持人**: 当你说**计算机视觉**和**图形学**时，它们是同一回事吗？还是**计算机视觉**是一回事，**图形学**是另一回事？它们之间有多么紧密地交织在一起？

<details>
<summary>Original English</summary>

**主持人**: when you say computer vision and graphics, are they the same thing or is it computer vision one thing, graphics another thing? How intertwined are they?

</details>

**Chris**: 它们交织在一起但又不同。是的。我认为，你知道，这与我们一直在讨论的一些主题有关，**Moonlake**内部正在构建的更明确的底层**世界模型**确实借鉴了**计算机图形学**的传统。所以它将**计算机图形学**与**视觉理解**相结合。

<details>
<summary>Original English</summary>

**Chris**: They're intertwined but different. Yeah. And I think, you know, this relates to some of the themes that we've been talking about that the more explicit underlying world models that are being constructed inside Moon Lake really draw on the computer graphics tradition. And so it's then combining that with the visual understanding of vision.

</details>

**主持人**: 明白了。好的。所以如果你写过**游戏引擎**，就来找我们，对吧？

<details>
<summary>Original English</summary>

**主持人**: Got it. All right. So if you've written a game engine, you're come talk to us, right?

</details>

**Sun**: 哦，是的，当然。但我确实认为界限正在模糊，现在越来越模糊，就像如果你对**视觉**和**图形学**有普遍的理解。

<details>
<summary>Original English</summary>

**Sun**: Oh yeah, definitely. But I do think that the line is blurred like increasingly blurred these days where it's like if you have a general understanding of vision and graphics.

</details>

**主持人**: 我认为按照你的标准，这，呃，对我来说，感觉视觉是，你知道，我会把它留给大实验室。图形学，我，我，我能理解你希望从**第一性原理**做起，但视觉有这么多现成的视觉模型我可以拿来用，但可能对你来说不够好。

<details>
<summary>Original English</summary>

**主持人**: I think for your standards it is uh for me it feels like vision is is you know I'll leave that to the big labs. Graphics I I I can get that you know you would want to do that from more first principles but vision there's so many vision models off the shelf that I can take but probably not good enough for your

</details>

**Sun**: 我明白了。我明白了。如果你正在做这种区分，那么也许我们更关心拥有**图形学知识**。

<details>
<summary>Original English</summary>

**Sun**: I see. I see. If if you're sort of like making that distinction, then then maybe we we care a little bit more about having graphics knowledge.

</details>

**主持人**: 是的。没错。没错。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Exactly. Exactly.

</details>

**主持人**: 嗯

<details>
<summary>Original English</summary>

**主持人**: Um

</details>

**主持人**: 就像，你知道，有时招聘电话可以很简单，就像如果你知道某个问题的答案，你就应该和我谈谈，你知道，就像你的世界中那种核心的已知难题。

<details>
<summary>Original English</summary>

**主持人**: it could be like you know sometimes a hiring call can be as simple as like if you know the answer to blah you should talk to me you know like the the the sort of core known hard problem in uh in your world.

</details>

**Sun**: 啊，我明白了。是的。在这种情况下，如果你，是的，如果你以前写过**游戏引擎**，如果你在不同目标上**强化学习**过各种编码模型，就像——

<details>
<summary>Original English</summary>

**Sun**: Ah I see. Yeah. In that case, if you Yeah, definitely if you've written a game engine before, if you've RLED a variety of coding models on different objectives like

</details>

**主持人**: 容易。

<details>
<summary>Original English</summary>

**主持人**: easy

</details>

**主持人**: 嗯

<details>
<summary>Original English</summary>

**主持人**: um

</details>

**Sun**: 很多。是的，

<details>
<summary>Original English</summary>

**Sun**: many of those. Yeah,

</details>

**主持人**: 如果你做过**多模态潜在空间对齐**。我特意再次提到了**空间**。

<details>
<summary>Original English</summary>

**主持人**: if you've done multimodal lan space alignment. I I intentionally included space again.

</details>

**主持人**: 一个可怜的编辑每次都要编辑东西。呃，是的，**潜在空间对齐**。老实说，有那么难吗？

<details>
<summary>Original English</summary>

**主持人**: A poor editor has a edit thing every time. Uh yeah, lean space alignment. Honestly, is it that hard?

</details>

**Sun**: 嗯，我那里有一些脚本，我为有一天我不得不做它而保存着，但我现在不必做它。它已经完成了，对吧？

<details>
<summary>Original English</summary>

**Sun**: Well, I there's some scripts out there that I've saved for the day I someday someday have to do it, but I don't have to do it. It's done, right?

</details>

**Sun**: 我认为是的，有一些版本已经完成了。但我认为我们正在对齐**音频**、**文本**、**语言**和**视频**，对吧？就像，基本上，我们有这些角色模型，它们能够充当**智能体**，以便在这些世界中行动并提取长**时间范围视频**，然后将其编码回模型，以便进行**自我改进**。所以，这是一个极其令人兴奋但也极具技术挑战性的问题。所以那些想做一生中最好工作的人，你知道，这里有一个地方。

<details>
<summary>Original English</summary>

**Sun**: I think yeah, there's there's versions of that that are done. But I I think we are aligning audio, text, language, and video, right? Like, and basically, we have these role models that are able to act as agents to like act in these worlds and extract long horizon videos and encoding that back to the models to sort of self-improve. So, it's an insanely exciting but also technically challenged problem. So people who want to do their lives best work, you know, makes a place.

</details>

**主持人**: 你们公司有多大？你们在哪里？

<details>
<summary>Original English</summary>

**主持人**: How big are you guys? Where are you guys based?

</details>

**Sun**: 我们目前在**萨托**，但我们正在搬到**旧金山**。嗯，我们现在大约有18个人。

<details>
<summary>Original English</summary>

**Sun**: We're currently based in Sato, although we're moving up to SF. Um, we're about 18 folks right now.

</details>

**主持人**: 我的最后一个问题是，为什么叫这个名字？名字背后有什么故事？

<details>
<summary>Original English</summary>

**主持人**: My ending question was going to be why what is the name? What's behind the name?

</details>

**Sun**: 哦。嗯，

<details>
<summary>Original English</summary>

**Sun**: Oh. Um,

</details>

**主持人**: 顺便说一下，非常酷的图形和设计。实际上，在公司成立之初，我们一直在思考如何取一个公司名称，让人们感受到像**OpenAI**一样的氛围，但又带有**工业光魔**的感觉，因为我们关心**创造力**，并将其作为解决**AGI**的漏斗。所以我们围绕像**梦工厂**，像**工业光魔**这样的名字进行了大量的头脑风暴，嗯，所以有一些基本的，呃，一些我们觉得在语义上与公司身份非常接近的东西。

<details>
<summary>Original English</summary>

**主持人**: very cool graphics and design by the way. Actually, at the at the time when the when the when we started the company, we were thinking a lot about how do we make a company name that gives people the vibe of like open AI but for like almost like industrial light and magic vibes because it's like we care about creativity and using that as a funnel to solve AGI. So then we were we brainstorm a lot around like dreamworks right like industrial light of magic and um so there's a few few basically uh space of things that we feel like are very very semantically close to the company's identity.

</details>

**Sun**: 是的。

<details>
<summary>Original English</summary>

**Sun**: Yeah.

</details>

**Sun**: 然后最终选择了**Moonlake**，部分原因是**梦工厂**的氛围，你知道，**梦工厂**的，呃，

<details>
<summary>Original English</summary>

**Sun**: And then it ended up being Moon Lake partly because of the DreamWorks vibe, you know, the DreamWorks uh

</details>

**主持人**: **Moonlake**。

<details>
<summary>Original English</summary>

**主持人**: Moon Lake.

</details>

**Sun**: 没错。是的。嗯，所以那是一点灵感，然后**月亮**有点像，它基本上是关于**反射**。**反射**部分也暗示了我们非常相信的**自我改进循环**，那是通往**多模态通用智能**的道路。所以就是这样，我将留下这个。

<details>
<summary>Original English</summary>

**Sun**: Exactly. Yeah. Um, so that was a little bit of that inspiration and then the moon was sort of like a it basically was like about the reflection. The reflection part also implies the self-improvement loop that we sort of like really believed in and that's the path towards multimotal general intelligence. So that's that's that's that I'll leave.

</details>

**主持人**: 我喜欢一个好名字。我喜欢一个好名字。这很棒。

<details>
<summary>Original English</summary>

**主持人**: I love a good name. I love a good name. This is great.

</details>

**Chris**: 这是一个很好的名字。

<details>
<summary>Original English</summary>

**Chris**: It's a very good name.

</details>

**主持人**: 这是一个很好的背景故事。我很高兴我问了这个问题。我还会说，你知道，我最喜欢的故事书或传记之一是**Ed Catmull**的**《创意公司》**，讲述了**皮克斯**的故事，以及他如何，你知道，被**迪士尼动画艺术家**拒绝。然后他进入**计算机领域**，并强行回到了**迪士尼**。

<details>
<summary>Original English</summary>

**主持人**: It's very good lore. I'm glad I asked the question. I will also say, you know, one of my favorite story uh books or biographies ever is Creativity Inc. with Ed Catmill's story about Pixar and how he, you know, was rejected as a Disney animation artist. So then he went into computing and brute forced his way into back into Disney.

</details>

**Sun**: 是的。**Walt Disney**也是我最喜欢的创始人之一。他就像他的故事，当时你就像，“好吧，我要创建这个身临其境的公园。”就像人们无法拥有那种技术来虚拟创建它，但就像，你知道吗，让我们把它实体地建造起来，这样人们就可以。

<details>
<summary>Original English</summary>

**Sun**: Yeah. And Walt Disney is also like one of my favorite founders. He's like his his story like at the time you're like, "Okay, I'm going to create this like immersive park." like people can't can't even have that technology to create it virtually, but like you know what, let's just build it physically such that people can.

</details>

**主持人**: 所以他是第一位**世界建模者**。

<details>
<summary>Original English</summary>

**主持人**: So he's the first world modeler.

</details>

**Sun**: 不，我，我，我会告诉人们，像**主题公园**也是**世界模型**。

<details>
<summary>Original English</summary>

**Sun**: No, I I I'll tell people that like theme parks are world models, too.

</details>

**主持人**: 是的。是的。是的。我的意思是，你知道，这是一个小世界，或者就像**Epcot中心**，里面有所有的小**国家复制品**。是的，那些非常有趣。嗯，好的。非常感谢。我们涵盖了，你知道，大量的内容。感谢你们的时间，感谢你们激励了我们。

<details>
<summary>Original English</summary>

**主持人**: Yeah. Yeah. Yeah. I mean, you know, it's a small world or it's like the Epcot Center with all the little um replicas of the countries. Yeah, those are very interesting. Um Okay. Well, thank you. We've covered uh you know, a huge amount. Thank you for your time and thank you for inspiring us.

</details>

**Chris**: 谢谢你邀请我们。

<details>
<summary>Original English</summary>

**Chris**: Thank you for having us.

</details>

**主持人**: 聊天愉快。是的，玩得很开心。
<details>
<summary>Original English</summary>

**主持人**: Fun chatting. Yeah, it's been a good time.

</details>