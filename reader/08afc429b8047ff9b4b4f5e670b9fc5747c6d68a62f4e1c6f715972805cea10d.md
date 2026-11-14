---
author: The MAD Podcast with Matt Turck
date: '2026-07-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Oojrfdl42LI
speaker: The MAD Podcast with Matt Turck
tags:
  - external-brain
  - open-source-ai
  - technology-trends
  - model-architecture
title: 外部大脑的构建与开源人工智能的变革力量
summary: 文章探讨了通过制造外部工具和外部大脑来提高智能效率的理念，并深入分析了当前开源人工智能领域（如新模型发布、中美竞争）的发展现状。核心观点强调了开放技术在促进创新中的基础性作用，以及AI作为解决人类结构性问题的唯一关键工具，同时讨论了公众接受度与安全问题中开源技术的优势。
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
<!-- chunk 1/10 -->

### 外部大脑的深远影响

**Speaker A**：如果你接受我们将达到极限这个事实，那么这意味着获得更多智能的方法就是提高效率。如果我们已经处于极限，就无法通过施加更多力量来获得更多智能。我们必须更周全地考虑如何利用我们所拥有的。我们制造工具。我们制造帮助我们解决问题的外部器官。你知道，我们有一个外部的胃，我们称之为厨房。现在，我们正在创造一个外部大脑。一个外部大脑的意义是什么？非常深远。其实没有人真正知道。

<details>
<summary>Original English</summary>

**Speaker A**: If you accept as the truth that we're going to be running at the limit, then what that means is that the way to get more intelligence is to be more efficient. We can't get more intelligence by applying more force if we're already at the limit. We have to be more thoughtful about how we use what we have. We build tools. We build external organs that help us solve problems. You know, we we have an external stomach. We call it a kitchen. Now, we're creating an external brain. What is the implications of an external brain? Pretty profound. Nobody actually really knows.

</details>

### 播客开场与开源AI的现状

**Matt Turk**：大家好，我是 Matt Turk。欢迎回到 Mad 播客。开源 AI 正迎来又一个高光时刻，几乎每周都有强大的新模型发布。我今天的嘉宾是解读这一切的最佳人选之一。Brian Kentaro 领导着 Neimotron，这是 Nvidia 的开源基础模型系列。现在，并不是每个人都意识到 Nvidia 在构建前沿 AI 模型方面投入了巨大的努力，但它雇佣了数百名 AI 研究人员，而且 Neotron 3 Ultra 在几周前一经发布，立即成为美国排名第一的开源权重模型。我们的对话将从开源 AI 的现状以及中美之间的竞赛开始，然后我们将深入探讨 Neotron，用通俗易懂的语言解释位训练（bit training）、混合成员变换架构（hybrid member transform architecture）、混合专家模型（mixture of experts）、多 token 预测（multi-token prediction）以及多层蒸馏（multi-teer distillation）。最后，我们将难得一见地了解一个现代 AI 研究组织实际是如何运作的——如何让许多聪明的大脑共同构建一个模型，而不是仅仅发表 100 篇论文。请尽情享受这场与 Brian Katansarao 的精彩对话。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome back to the Mad Podcast. Open source AI is having yet another moment with powerful new models arriving almost weekly. And my guest today is one of the very best people to unpack it all. Brian Kentaro leads Neimotron, Nvidia's family of open foundation models. Now, not everyone realizes Nvidia has a massive effort to build frontier AI models, but it employs hundreds of AI researchers and Neotron 3 Ultra immediately became the number one US openweights model when it was released just a couple weeks ago. We begin this conversation with the state of open source AI and the race between the US and China and then we go deep inside Neotron for bit training hybrid member transform architecture mixture of experts multi-token prediction and multi-teer distillation all in plain language and finally we get a rare look at how a modern AI research organization actually runs how you get many brilliant minds to build one model instead of a 100 papers please enjoy this awesome conversation with Brian Katansarao

</details>

**Matt Turk**：好了，Brian，很高兴能进行这次对话。似乎开源正迎来辉煌的一年。所以，你们在 NVIDIA 刚刚发布了 Neotron 3 Ultra，这是一个重要的时刻，它也是美国最好的开源权重模型。这就在几天前。然后，就在更近的时候，GLM 5.2 发布了，这又是一个重要时刻。所以看来开源 AI 的发展正在加速。我觉得这是一个很好的切入点。你对我们目前的处境有何评估，闭源和开源之间目前的差距有多大？

<details>
<summary>Original English</summary>

**Matt Turk**: All right, Brian, excited to do this. It seems that open source is having a banner year. So, you guys at NVIDIA just released Neotron 3 Ultra, which is an important moment and the best open-source openweight model in the US. That was just a few days ago. And then uh even more recently, GLM 5.2 came out and that was another moment. So it seems that things are accelerating in open source AI. It feels like a great place to start. What's your assessment about where we are and how wide the gap between closed source and open source currently is?

</details>

### 开源技术的变革力量

**Brian Katansarao**：嗯，看到所有的精力都投入到 AI 的开源技术中真的很令人兴奋，因为我们知道，开源技术使人们能够进行创新。你知道，互联网就是一个很好的例子。事实上，我们确实有过封闭的互联网。我不知道你是否还记得当年的 America Online 和 Prodigy。它们很棒。而开放的互联网同样也令人惊叹，对吧？比如有那么多不同的公司能够弄清楚如何彻底改变他们的工作，这都要归功于一种开放的技术。互联网在零售业的应用与在医疗保健或制造业的应用截然不同。但它们都已经被互联网彻底改变了。我相信，AI 也是一种非常具有变革性的技术，同时也是一种需要在各种不同场景下进行应用的技术，正因如此，我认为 AI 的开源技术是非常基础且至关重要的。看到世界各地这么多不同的组织持续投资和开发 AI 的开源技术，非常令人兴奋。而且，你知道，我希望这种趋势能够继续下去。

<details>
<summary>Original English</summary>

**Brian Katansarao**: Well, it's really exciting to see all of the energy going into open technologies for AI because we know that um open technologies make it possible for people to innovate. You know, the internet is such a great example of that. Um, we actually did have closed internets. I don't know if you remember things like America Online and Prodigy back in the day. Um, and they were great. Um, and open internet has also u been amazing, right? Like so many different companies have been able to figure out how to transform their work um, thanks to uh, an open technology. The application of the internet to retail is very different from the application of the internet to healthcare or manufacturing. But all of them have been totally transformed um by the internet. Um AI uh I believe is uh also a very transformational technology and also a technology that needs to be applied in very diverse ways and because of that I believe that open technologies for AI are really fundamental. Um and it's very exciting to see continued um investment and development of open technologies from uh for AI from so many different organizations around the world. Um uh and uh you know I I hope that that continues.

</details>

**Matt Turk**：那么你认为开源相比于闭源目前落后多少？过去几年的一个大趋势就是这种差距正在缩小。你认为开源是否已经快要赶上，还是说闭源模型不断地在抬高门槛？

<details>
<summary>Original English</summary>

**Matt Turk**: And what's your sense for how far behind opensource is compared to closed sources? It's been the the big trend of the last few years has been this sort of narrowing gap. Do do you think that open source is almost there or the bar keeps getting raised by the closed source models?

</details>

### 发展速度重于差距

**Brian Katansarao**：嗯，我觉得这个问题也许是一个很诱人的问题，因为，你知道，设立某种竞赛很有趣，但我实际上觉得整个 AI 社区的发展速度非常快。举个例子，如果你看看过去 3 个月里 AI 的进展，无论是闭源还是开源，都令人难以置信。因此，如果你处于一个发展非常非常快的领域，我认为这比不同模型之间可能存在的任何特定差距都更重要，因为最重要的事情是，AI 作为一个领域是如何发展的？

<details>
<summary>Original English</summary>

**Brian Katansarao**: Well, I I feel like this question um uh it's maybe a tempting question because, you know, it's fun to set up kind of competition, but but I actually feel like the whole AI community is moving very fast. Um and if you look, for example, at the progress in AI, whether it's closed or open just over the past 3 months, it's been incredible. Um, and so if you're in a field that's moving really, really fast, I think that's more important than any particular gaps that might exist between different models because the most important thing is, you know, how is AI developing as a field?

</details>

**Matt Turk**：你认为推动开源 AI 继续取得进展的驱动力是什么？是社区吗？是像 Nvidia 这样的大公司在背后支持吗？是与中国的全球竞争吗？是什么推动着开源 AI 向前发展？

<details>
<summary>Original English</summary>

**Matt Turk**: What do you think the drivers are to continue progress in open-source uh AI? Is that the community? Is that big companies like Nvidia being behind it? Is that the global competition with China? what propels open source AI forward?

</details>

### 开源技术的驱动力

**Brian Katansarao**：你知道，我认为有很多因素在推动 AI 的开源技术向前发展。其中之一就是需求。有那么多的组织希望定制 AI，并希望将其深入整合到他们的工作中，这种方式确实需要 AI 的开源技术。所以我认为需求无疑是存在的。我也认为这正是开发技术的最佳方式。我们已经看到了，几十年来，在开放环境下开发的技术发展得更快，因为我们都可以互相学习。而且，在一个我们正在经历有生之年技术领域最激动人心的事情——AI 的开发和部署——的时代，除了让 AI 变得更棒之外，计算机科学家还想致力于什么呢？如果作为一个社区一起合作是实现这一目标的最佳方式，那么这也是推动社区走向开放开发技术的一个驱动力。

<details>
<summary>Original English</summary>

**Brian Katansarao**: You know, I think there's a number of things that that are pushing open technologies for AI forward. One is just the demand. You know, there's so many organizations that want to customize AI and want to integrate it deeply into their work in a way that really requires open technologies for AI. And so, so I think um the demand is certainly there. I think also it's just um uh the best way to develop technology. Um, and we've seen this, you know, for for many decades that technologies developed in the open move quicker because we can all learn from each other. And um, in an era where we're undergoing the most exciting thing to happen in technology in our lifetimes with the development and the deployment of AI, um, what else do do computer scientists want to work on other than making AI awesome? And if working together as a community is the best way to do that, then that's also a driver that pushes the community towards openly developing technology.

</details>

**Matt Turk**：问一个也许有点愤世嫉俗的问题。社区中至少有一部分人想知道，作为一个生态系统的开源（不是指 Nvidia，而是总体而言）之所以能够取得进展，部分原因是否是基于蒸馏闭源模型的能力。在这样一个我们看到像 Anthropic 这样的公司开始不鼓励蒸馏的世界里，你认为在这种背景下，或者作为其结果，开源 AI 的进展有可能会放缓吗？

<details>
<summary>Original English</summary>

**Matt Turk**: to ask maybe a slightly cynical question. there is at least a a a part of the community that's wondering whether open-source as an ecosystem not not Nvidia but in general has been progressing in part based on the ability to distill closed source models and in a world where we seeing the anthropics and fable fives of of the world starting to discourage distillation do you think there is a chance that opensource AI progress may slow down in that context or as a result.

</details>

**Brian Katansarao**：你知道，在我看来，毫无疑问，当技术界决定对我们这个时代最具变革性的技术进行巨额投资时，将会取得迅速的进展。而且，这项技术不会被一小群人所控制。因为那根本不是这个行业的运作方式。你知道，我们做出了最好的工作。当能够以自己的方式思考并应用它时，我们的工作能产生最大的影响。所以，你知道，我喜欢闭源 AI 的 API，无论是来自 Anthropic 还是其他人的。我觉得它们很惊人，你知道，我对那些实验室正在做的工作留下了非常非常深刻的印象。但他们并不是世界上仅有的实验室。世界各地有很多实验室，很多人都有好主意。并不是说只有少数几个实验室垄断了所有好主意。那不是真的。人类社会不是这样运作的。这个星球上有很多聪明人。而且，你知道，社区当然非常关心这项技术。它显然具有如此大的变革性，对这么多事物产生如此深远的影响，以至于当然有许多人想参与其中。因此，我认为随着时间的推移，我们将看到开发和部署 AI 的面向社区的方法将继续得到加强并被广泛采用，因为这确实是我们人类这个物种构建事物的历史轨迹。

<details>
<summary>Original English</summary>

**Brian Katansarao**: You know, in my mind, there's no question that when the um technology community decides to make huge investments in the most transformational technology of our time, that there's going to be rapid progress. Um and also that that technology is not going to be controlled by a small group of people. Um because that's just not the way that um the industry works. you know, we we um do our best work. Um uh we have the most impact with our work when we're able to uh each think about it in our own way and apply it in our own way. So um you know uh I love uh the uh closed AI APIs uh whether from anthropic or other people. I think they're amazing you know um really really impressed with the work that those labs are doing. But they're not the only labs in the world. There's lots of labs around the world and lots of people have a good idea. Um, it's not the case that there's only a few labs that have the monopoly on all good ideas. That's just not true. That's not how humanity operates. There's a there's a lot of bright people on this planet. And um, you know, the community uh, of course cares deeply about this technology. It's obviously so transformational, has such profound impacts on so many things um that that of course uh, many people uh, want to be involved in that. And um so I think over time we're going to see that um community oriented approaches to developing and deploying AI are going to continue to strengthen and be widely adopted because that's really the history of how we built things as a as a human uh species.

</details>

**Matt Turk**：你认为这在全球范围内也是如此吗？尤其是考虑到中国，有这样一种看法：是的，世界各地有很多人都有好主意。然而，中国模型取得的许多进展，是直接受到了闭源模型的启发，或者可能就是通过从闭源模型中蒸馏而产生的。这只是一种新闻界吸引眼球的诱饵吗？或者从一位领先的 AI 研究人员的角度来看，你是否也对中国涌现出的新颖想法印象深刻？

<details>
<summary>Original English</summary>

**Matt Turk**: Do you think that is globally true as well? So um you know in particular with respect to China this perception that yes a lot of people have great ideas around the world. Uh however a lot of progress from Chinese models were directly inspired or perhaps uh generated through distillation from from the closed source models. Is that just a kind of like press rage bait or from the perspective of a leading AI researcher? You're very impressed by the the the novel ideas that come out of China as well.

</details>

**Brian Katansarao**：你知道，也许有些不同寻常，我实际上曾经在一家中国公司工作了大约两年半。我在 BYU 工作过。我在硅谷的 AI 实验室工作，和 Andrew Ing 还有 Daario Amadei 一起，我们都在一家中国公司工作，并见识到了我们在 BYU 其他部门的同事们是多么聪明、勤奋、富有创造力和发明精神，而你……

<details>
<summary>Original English</summary>

**Brian Katansarao**: You know, um uh perhaps unusually, I uh actually did work at a Chinese company for about two and a half years. I worked at BYU. Um I worked in the Silicon Valley AI lab uh along with Andrew Ing and as well as Daario Amadei and um uh we all worked uh for a Chinese company and saw how smart, hardworking, creative, inventive our colleagues were uh at the rest of BYU and you

</details>

<!-- chunk 2/10 -->

### 合作与开源 AI 技术的价值

**Speaker A**: ……这种经历一直让我难以忘怀。我认为，那种认为其他国家的成就完全是靠“山寨”心态创造出来的说法，是绝对错误的。完全不是这么回事。那么我们在科技界会互相学习吗？当然，我们当然会互相学习。但是我想说，中国 AI 社区对他们正在构建的东西如此开放，对全世界来说真的是一件好事。我认为这让许多公司能够构建出没有这个社区就无法完成的东西，而且我认为这也促进了整个 AI 生态系统的技术进步。所以，你知道，我非常感谢我们在中国的同行多年来所做的贡献，我也很希望能鼓励中国以外的世界各地的 AI 实验室也保持这种开放的精神。你知道，前段时间 OpenAI 发布 GPT 的开源模型时我非常激动，当然 Google 也在 Gemma 上做出了出色的工作。看到这些绝对令人兴奋。并且，我们在 Nvidia 也在推进 Neotron。所以我认为，世界其他地区有机会在某种意义上追赶上中国，也就是说我们可以理解作为一个社区共同合作构建 AI 技术的益处，而在这种合作方式上，我认为坦率地说中国一直处于领先地位。

<details>
<summary>Original English</summary>

**Speaker A**: ...know that experience has stuck with me. Um I think it's absolutely false to say that um you know uh the achievements of some other country are all being um created by sort of you know copycat mentality. It's just not true. Um now do we all learn from each other uh in the technology community? Of course you know of course of course we learn from each other. But um you know uh I would say uh you know it's been a really good thing for the world that the Chinese uh AI community has been so um open with what they've been building. I think it's enabled a tremendous number of companies to build things that uh they couldn't have done without um that community and I think it's also spurred um technological progress throughout the AI uh ecosystem. So, you know, I'm really grateful for um the contributions that um our um colleagues in China have made over the years and um you know, I would love to encourage a spirit of openness amongst AI labs around the world outside of China as well. You know, I was really excited when uh OpenAI released the GPT OSS models um a while back and then of course Google's been doing great work with Gemma. Absolutely thrilling to see that. Um, and you know, we're pushing Neotron along here at Nvidia as well. Um, so I think there's a chance for um uh the rest of the world to catch up to China uh in the sense that um you know we can understand the benefits of working together uh as a community to build technologies for AI uh in a way that I think China has frankly been leading.

</details>

**Speaker B**: 太好了。现在客户使用开源模型的理由是什么？你们的根本优势是什么？

<details>
<summary>Original English</summary>

**Speaker B**: Great. What is the case for a customer to be using open-source models uh these days? What is your fundamental advantage?

</details>

**Speaker A**: 每家公司都是围绕着一个秘密建立的。这个秘密不仅关系到他们的知识产权，也关系到他们的平台。这涉及到他们如何应对问题和客户？他们如何思考满足客户需求的解决方案？情况总是如此，当 AI 能够与这些秘密更紧密地结合时，它的价值就更大，因为 AI 严重依赖数据，所以输入的数据越有价值，解决方案就变得越有价值。现在，每家公司在考虑如何部署 AI 时，都必须仔细思考这会对我们公司的核心机密产生什么影响。在许多情况下，由于商业机密，或者试图理清商业模式，甚至是监管要求，你会发现有些数据在法律上你必须非常谨慎地处理。而当你能够自己把这些想清楚并亲自实施时，情况会好得多。考虑到 AI 的整合、AI 与客户互动的方式、以及设置的护栏，每家公司对其客户以及客户的需求都有具体的了解。而且用于 AI 的开放技术最令人惊叹的一点是，它们允许定制化，对吧？所以公司可以仔细思考这一点。他们可以构建对他们真正重要的东西。你知道，我在这场对话刚开始时谈到了互联网，以及互联网在不同行业中是如何以非常不同的方式部署的。当我们看到 AI 正在改变整个经济中我们工作和娱乐的方式时，人们对此有很大的渴望。这确实在很大程度上刺激了对 AI 开放技术的需求。

<details>
<summary>Original English</summary>

**Speaker A**: Every company is built around a secret. Uh this is a secret that has to do with not just their intellectual property but also their platform. Uh which has to do with how do they interact with problems and customers? um how do they think about solutions uh to what their customers need and it is always the case that the value of AI is greater when it can be more tightly connected with those secrets because you know AI depends on data critically so the more valuable the data that goes in the more valuable the solution becomes now um every company when it's thinking about how to deploy AI has to think through what are the implications for the core secrets of our company and um there's a lot of circumstances where um due to trade secrets or or you know trying to think of think through the business model or or even regulatory requirements that you know there's data that you really have to treat very carefully by law. Um and it is much better to do that when you are able to think that through and implement it yourself. um thinking about the integration of AI, the way that AI interacts with um customers, um the guard rails that are put in place, you know, every company um has a specific understanding of its customers and and therefore what the customer needs. And um the amazing thing about open technologies for AI is that they allow custom uh customization, right? So companies can think this through. They can build things that really matter for them. And you know, I started out this conversation talking about the internet and about how the internet, the deployment of the internet has been done in very different ways for very different industries. Um, and there's a lot of desire to do that. Um, uh, as we see AI change the way that we work and play throughout the entire economy. Um, this is really spurring a lot of demand for open technologies for AI.

</details>

### 早期的职业道路与在英伟达的研究

**Speaker B**: 太好了。我很想深入了解一下 Neotron，但在那之前，也许能花几分钟谈谈你的故事，你的背景。你是如何走到今天的？包括去 BYU 的那段经历。

<details>
<summary>Original English</summary>

**Speaker B**: Great. I'd love to go into a bit of a deep dive into Neotron, but before we do that, maybe a few minutes on your story, your background. What was your path to where you are today? Um, including the the BYU detour.

</details>

**Speaker A**: 所以，我是 2008 年开始在 Nvidia 工作的。那时我还是个研究生，试图弄明白用于人工智能的并行计算。我认为 Nvidia 有机会改变计算机处理 AI 的方式。

<details>
<summary>Original English</summary>

**Speaker A**: So, um, I started work at, uh, Nvidia in 2008. Uh, at the time I was a graduate student trying to figure out, um, parallel computing for artificial intelligence. And I thought um Nvidia had a chance of changing the way computers work AI.

</details>

**Speaker B**: 在 2008 年，这想必是一段孤独的探索旅程吧。

<details>
<summary>Original English</summary>

**Speaker B**: which was a lonely presumably a lonely quest right in 2008.

</details>

**Speaker A**: 哦，那时候非常混乱。人们觉得我疯了，我记得 2008 年去参加 ICML。我发表了第一篇关于在 GPU 上训练模型的论文，人们问我为什么来这里。人们说这不适合作为 ICML 的论文。我们这里只搞高级的数学。而我当时的反应是，好吧，但我认为计算对 AI 来说其实非常重要。如果我们可以训练具有更强学习能力的更大模型，我们或许就能解决更多的问题。然后他们有点点着头说，好吧，我还是不太明白你为什么来这里。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, it was it was very chaotic back then. People thought I was crazy and you know I remember going to ICML in 2008. I published my first paper training models on the GPU and people asked me why I was there. People said this is not a good paper for ICML. We're we're we just do fancy math here. And I was like, well, but I think computing actually matters a lot for AI. If we could train bigger models that had more capacity to learn, we could probably solve more problems. And um they kind of nodded their heads and like, well, I'm not really sure why you're here.

</details>

**Speaker B**: 大概来说，GPU 不也是用来打游戏的东西吗，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Isn't a GPU a thing for gaming as well, presumably, right?

</details>

**Speaker A**: 是的。也有这个原因，对吧，我们现在还经常遇到这种看法。实际上，GPU 是什么由 Nvidia 说了算。你知道，是我们制造了它们。所以 GPU 就是我们为了加速世界上最重要的计算而制造的东西。这在 1995 年是图形处理，而如你所知，现在很长一段时间以来它已经是 AI 了。总之我开始在 NVIDIA 工作，我当时在研究组里做一些奇怪的事情，比如试图在 GPU 上为 AI 制作编译器和库。这促成了 Copperhead 的诞生，它是一种可以编译到 GPU 的 Python 嵌入式语言，我认为它预示了后来 TensorFlow 和 PyTorch 中的许多东西，然后那又促成了 cuDNN 的诞生，这是 Nvidia 首个用于 GPU 深度学习的产品。我非常喜欢那项工作。但我一直希望能够亲眼看到更多关于 AI 的实际应用，而在 NVIDIA，我主要致力于 AI 的库和编译器。所以我想，好吧，当 Andrew Ng 邀请我跟他一起在 BYU 建立硅谷 AI 实验室时，我觉得这是一个绝佳的机会，因为即使在那个时候，BYU 在将 AI 应用于其核心业务方面也非常先进。所以这对我来说是个极好的机会。BYU 硅谷 AI 实验室是一个很棒的地方，到处都是极其聪明且工作非常努力的人。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. There's there's also that, right, which we we continue to um run into that uh that idea. Actually, a GPU is whatever Nvidia says it is. You know, we make them. So a GPU is is a is a thing that we make in order to accelerate the world's most important computations. Um which in 1995 was graphics and you know for a long time now it's been AI. So um anyway I started at NVIDIA um I was in the research group um doing uh strange things about trying to make um uh compilers libraries uh for AI on the GPU. Um that led to um the creation of uh first copperhead which was a it was a a Python uh embedded language that um compiled to the GPU um which I think foreshadowed a lot of things in TensorFlow and and PyTorch um and then um uh then that led to the creation of QDNN which was Nvidia's first product for um uh for deep learning on the GPU. Um and uh I I really enjoyed working on that. Um but I was always wanting to see more uh firsthand about the applications of AI and at NVIDIA I was mostly working on you know uh libraries and compilers for AI. So I thought um well you know when Andrew Ing asked me to go uh build the Silicon Valley AI lab with him uh at BYU I thought oh this is a great opportunity because even back then BU um was very advanced in its application of AI to its core business. And so um uh so that was a a fantastic opportunity for me. The BU Silicon Valley AI lab was an amazing place um full of brilliant people that were working really hard.

</details>

### 早期与 Daario 的共事经历

**Speaker B**: 和年轻的 Daario 一起工作是什么感觉？当时有没有什么迹象表明他能成为他今天这样的人？

<details>
<summary>Original English</summary>

**Speaker B**: What was it like working with a young Daario? Uh was there like any signs that he could become uh you know who who he has become?

</details>

**Speaker A**: Daario 从一开始就才华横溢。我记得我面试过他，我当时在面试小组里，那时他一直在从事生物信息学工作，所以他并没有涉足深度学习或者我们现在称之为 AI 的这些领域，但很明显他学得极快，而且他思考问题极其深入。我想我最钦佩 Daario 的一点就是他信念的坚定。你知道我在这个领域工作了很长时间，我也一直相信 AI 将会改变世界，但我认为我并不像 Daario 相信得那么彻底，这也许是因为我在读博期间的学术训练充满了太多的谨慎。我不知道你是否记得，但在 2005 年，AI 被认为是陈旧且糟糕的东西。

<details>
<summary>Original English</summary>

**Speaker A**: Daario um was brilliant from the beginning. I remember um I interviewed him uh I was on the panel um and um at the time he uh had been working in bioinformatics so he he hadn't been working on deep learning or or the things that we call AI these days um but it was very clear that he learned extremely quickly and also that he thought extremely deeply um I think you know uh the thing I admire most about Daario uh is the strength of his conviction um you know I've been working in this field uh for a long time and I've believed also that AI is going to transform the world but I don't think that I believed uh in it as completely as Daario did and perhaps that was because you know my academic training during my PhD was full of a lot of caution uh I don't know if you remember but AI was old and bad in 2005

</details>

**Speaker B**: 永远也行不通。

<details>
<summary>Original English</summary>

**Speaker B**: it will never work

</details>

**Speaker A**: 人们用计算机做这种事情，从 1945 年就开始了。对吧。而且这么多年来，有过太多最终未能兑现的宏伟承诺。所以我对待 AI 时带着很多谨慎。事实上，那时候我们通常叫它机器学习，这基本上是一种避讳。就好像我们只是不想让人们知道我们在搞 AI，因为那样他们就会说：“哦，我们听说过那个。它从来都行不通。”对吧？所以我进入 AI 领域时带着一点这种类似学术上的谨慎，就像是：“哦，我们应该留点退路。我不知道现在是不是时候”。而 Daario，他坚定的信念，他对当时技术发展到那个时刻的理解——明白这一次它真的能行得通，以及这对于技术应该如何发展、应该建立什么样的机构所带来的影响。我认为他做出了惊人的成就，所以，是的，和他一起工作……

<details>
<summary>Original English</summary>

**Speaker A**: that people did with computers they started doing it in 1945 Right. Um and and so there had been so many grandiose promises that failed to deliver over the years. And so I came to AI with a lot of caution. In fact, back then we used to call it machine learning, which was basically a dodge. Like we just didn't want people to know that we were we were working on AI because then they would be like, "Oh, we've heard about that. It never works." Right? So, um I came to AI with a little bit of this like uh you know, academic caution like, "Oh, we should you know, we should hedge a little bit. like I don't know if now's the time like um and and Daario, you know, he his uh strength of conviction and his understanding of the moment of how um the technology was developing this time it was actually going to work and then the implications of that on um you know how the technology should be developed um uh what kind of institutions uh to build I think he's done a spectacular job and so um yeah working with

</details>

<!-- chunk 3/10 -->

### 回归 Nvidia 与 DLSS 的诞生

**Speaker B**: ……这总是、总是一段有趣的经历。

<details>
<summary>Original English</summary>

**Speaker B**: ... it was always always a a fun experience.

</details>

**Speaker A**: 后来你回到了 Nvidia，带我们回顾一下这段旅程吧。

<details>
<summary>Original English</summary>

**Speaker A**: So then you went back to Nvidia and walk us through the journey.

</details>

**Speaker B**: 好的。其实在10年前，也就是2016年，黄仁勋（Jensen）打电话给我说，嘿，你想不想回来建立一个应用研究实验室？我觉得那会是一个绝佳的机会。你知道，我一直很喜欢 Nvidia。我喜欢这家公司的运作方式，以及它所坚持的信念。Nvidia 是一家非常独特的公司。它能够跨越很长的时间周期坚持做一件事，我在 CUDA 上看到了这一点，在我们的深度学习技术上看到了这一点。在我们的光线追踪图形技术、AI 图形技术上，我也看到了这一点。一次又一次，Nvidia 敢于投入5到10年的研究来改变世界。能在一家拥有这种坚定信念并能贯彻到底的公司工作，对我来说是非常理想的。我真的非常喜欢公司给予研究人员的支持，去发明未来。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So uh 10 years ago actually in 2016 uh Jensen called me up and said hey uh would you like to come back and build an applied research lab and I thought that would be a fantastic uh opportunity. I you know I've always loved Nvidia. I've loved um the way the company works, the convictions the company holds. You know um Nvidia is a very unique company. it follows through over long time periods, you know, uh, and I've seen that with CUDA. I've seen it with our deep learning technologies. I've seen it with our ray tracing graphics technologies, our AI for graphics, you know, over and over again, Nvidia is not afraid to put in five or 10 years worth of research in order to change the world, you know, and um, working at a company that has that strength of conviction and the ability to follow through is kind of an ideal thing for me. Um I just really I just really love the support that the company gives uh gives its researchers um to invent the future.

</details>

**Speaker B**: 所以我想我应该回来。我参与的第一个项目实际上后来变成了 DLSS，你们的一些观众可能知道，DLSS 是我们的实时 AI 图形技术，它能让小 GPU 跑出大 GPU 的效果。它的效率大约提高了10倍，因为我们不再为每一帧的每一个像素计算颜色，而是使用 AI 来推断颜色。如今，当你在玩游戏时使用 DLSS，每24个像素中就有23个是由我们的 AI 模型生成的。玩家们非常喜欢它。它已经成为玩游戏的标准方式，因为它的响应速度快得多，画面也更漂亮。我们的 AI 是在庞大的数据集上离线训练的，它能够比传统方法更漂亮地实时渲染图形。我们最近实际上发布了 DLSS 5，这是一个完全生成式的 DLSS 版本，我对此感到非常兴奋。它代表了我们十年来关于如何让实时图形变得更加美丽的研究的结晶。所以这也是我这段旅程的一部分——实时 AI 图形技术。

<details>
<summary>Original English</summary>

**Speaker B**: And so um I thought I'd come back um uh the first project that uh that I worked on um actually became DLSS uh which uh some of your um audience may know about but DLSS is our real-time uh AI for graphics and it makes a small GPU run like a big GPU. It's about 10 times more efficient because rather than computing uh the color of every pixel for every frame, we use AI to infer the color. Uh and uh you know these days 23 out of every 24 pixels uh is being generated by our AI model when you're using DLSS um to play games. And gamers love it. It's become the standard way of playing games because it's just so much more responsive and it's more beautiful. Our AI, we train it offline on huge data sets. Um and it's able to render uh graphics in real time uh more beautifully than uh traditional methods do. Um uh we recently actually announced DLSS 5 which is a fully generative version of DLSS and um I am so excited about it. It represents culmination of 10 years worth of research on how to make um real-time graphics much more beautiful. Um and so uh so that's part of uh part of the journey uh here for me was real-time uh uh AI for graphics.

</details>

### Megatron 项目与大语言模型的崛起

**Speaker B**: 但与此同时，我们也启动了一个语言建模项目。那是在2017年，在 Transformer 还没火起来、语言建模还没开始席卷世界之前。但我就是有这样一种直觉，也许是基于我在 BYU 工作时看到的一些现象，我直觉地认为，处理文本和理解文本将带来更好的推理能力，进而推动 AI 在各个领域的更好应用。

<details>
<summary>Original English</summary>

**Speaker B**: Um but then at the same time we also started a language modeling project. Um and this was back in 2017 um you know before transformers uh were big and before um language modeling uh uh started taking over the world. But um you know I just had this intuition maybe built on you know some of the things that that I had seen uh while working uh at BYU. I I just had this intuition that you know working with text and understanding text was going to lead to better reasoning which was going to lead to better application of AI in all sorts of domains.

</details>

**Speaker B**: 所以我们启动了这个名为 Megatron 的项目。Megatron 的意思是“最强大、最硬核的 Transformer”，这就是我们如此命名的原因。这其实是一个系统层面的项目，旨在向世界展示如何在 Nvidia 的硬件上训练最大的 Transformer 模型。当时，你们的听众中有些人可能还记得，也可能不记得，但那时有一种说法是：唯一能训练大型 Transformer 模型的方法就是使用 TPU。毕竟，Transformer 是在 Google 发明的。所以，我们看了这篇 Transformer 的论文并非常喜欢它，我们想，哇，这有着惊人的潜力。我们在自己的语言建模任务上尝试了一下，它的效果比我们以前使用的 RNN 好得多。同时我们也立刻意识到，这里存在着一个巨大的系统级机会——去共同优化 GPU、网络以及所有的编译器和软件，从而让人们能够极其显著地扩展基于 Transformer 的语言模型。我们觉得，这是一件能真正产生影响的事情。因此，我们启动了 Megatron 项目，这基本上帮助了整个行业弄清楚如何训练极大规模的 LLM（大语言模型），同时也为如今的 Nemotron 项目奠定了基础，在这个项目中，Nvidia 会为了自身的目的训练自己的 LLM。这就是大概的历史。

<details>
<summary>Original English</summary>

**Speaker B**: And so um uh so we started this project uh called Megatron. Megatron stands for the biggest baddest transformer. That's why we named it that. Um, and it was really a systems project to show the world how to train the largest transformer models on Nvidia's hardware. Uh, back at the time, uh, some of your, uh, audience may or may not remember this, but, uh, there was there were being claims made that the only way to train big transformer models was on the TPU. Um, because after all, the transformer had been invented at Google. And, uh, so, you know, we looked we looked at uh, you know, we loved the the the transformer paper. We thought, wow, this has amazing potential. We tried it out on our own language modeling tasks and it worked so much better than the RNN's that we had been using before. And also we saw immediately that there was an enormous systems opportunity to co-optimize the GPU, the networking, all of the compilers and software that would enable people to scale uh transformer-based language models uh really dramatically. And we we thought, you know, this is this is something that that um could really have an impact. So we started the Megatron project um which then led to I think uh basically helping the whole industry figure out how to train um extremely large uh LLMs um and also led to the foundations of today's Neotron project um where you know Nvidia trains uh its own LLMs um uh for its own purposes. So that's kind of the the history

</details>

### Nemotron 模型的双重使命

**Speaker A**: 非常棒的旅程。好的，那我们来谈谈关于 Nemotron 的一切。在进入具体细节之前，我确信你被问过很多次那个显而易见的问题——为什么 Nvidia 首先要在乎构建模型，并投入大量精力去创造自己的前沿模型系列？

<details>
<summary>Original English</summary>

**Speaker A**: great journey. Okay, so let's go into all things uh Neatron. And before we get into the specifics, that's the obvious question that I'm sure you've been asked uh many times uh which is why does Nvidia care in the first place to be building model and investing very significant efforts into creating its own family of of frontier models.

</details>

**Speaker B**: 你知道，Nemotron 有两项任务。第一项任务是帮助我们理解如何构建未来的系统。NVIDIA 是一家加速计算公司，这意味着我们要从第一性原理出发，思考世界上最重要的计算挑战，并设计系统（其中包含大量软件），使人们能够发明和部署那些在标准计算中永远无法实现的事物。但为了做到这一点，Nvidia 必须深刻理解关于 AI 是如何运作的一切。这就是我们为主要产品线共同设计所有系统和软件的方式。所以 Nemotron 的第一个任务是确保 Nvidia 继续生存下去，这样我们才能在摩尔定律已死的时代继续提供有意义的加速计算。而我们如今获得的加速来自于专业化，但专业化又是建立在理解的基础上的。

<details>
<summary>Original English</summary>

**Speaker B**: You know, Neimotron has two jobs. The first job is to help us understand how to build the systems of the future. NVIDIA is an accelerated computing company and that means thinking through the world's most important computational challenges from first principles and designing systems which includes a lot of software uh in order to make it possible for people to invent and deploy things that never could have been done with standard computing. But in order to do that, Nvidia has to deeply understand everything about how AI works. That's how we co-design all of the systems and software um uh for our main product line. So the first job of Neotron is to make sure that Nvidia continues to exist so that we can continue delivering meaningful acceleration in an era where Moore's law has died. uh and the the acceleration that we get these days comes through specialization but again specialization comes through understanding.

</details>

**Speaker B**: 所以，Nemotron 的第一个任务就是帮助 Nvidia 理解如何构建其核心产品。Nvidia 的第二项任务，或者说 Nemotron 的第二项任务，是支持生态系统。多年来，Nvidia 建立的最有价值的东西之一，就是世界各地那些使用 Nvidia 技术构建和部署令人惊叹的 AI 的人们。我们认为，必须要有来自 Nvidia 的开放 AI 技术继续存在，以帮助支持这一点。Nemotron 并不想成为唯一一个开放的 AI 技术。我们喜欢所有的 AI 技术，原因很简单：只要 AI 得到进一步的发展和部署，对我们的业务就是一个机会。因此，我们非常明确地试图发展我们的生态系统，因为这对我们是好生意。但我们并不想成为这个生态系统中唯一的系统技术提供商。我们很高兴看到其他公司也做出贡献。对于 Nemotron 第二项任务来说，最重要的事情就是要确保各种形态和规模的公司依然能够去构建和部署他们自己的 AI。

<details>
<summary>Original English</summary>

**Speaker B**: So that's Neatron's first job is to help Nvidia understand how to build its core products. Nvidia's second or Neatron's second job is to support the ecosystem. Uh, one of the most valuable things that Nvidia has built over the years is um, all of the people around the world who build and deploy amazing AI um, using Nvidia's uh, technologies and uh, we think that it's necessary for uh, open technology for AI to continue to exist uh, from Nvidia to help uh, support that. Neotron's not trying to be the only open technology for AI. We love all technology for AI for the very straightforward reason that whenever AI uh is further developed and further deployed, it's an opportunity for our business. So, so this is this is um you know, we're we're very explicitly trying to develop our ecosystem because that's good business for us. Um but we're not trying to be the only provider of technologies for this ecosystem. We love seeing um other companies contribute as well. Um the the most important thing for Neimatron's second job is just making sure that it continues to be possible for companies of all shapes and sizes to build and deploy their own AI.

</details>

### 摩尔定律的终结与加速计算

**Speaker A**: 顺便问一下，摩尔定律已经死了吗。这已经是官方定论了吗？

<details>
<summary>Original English</summary>

**Speaker A**: By the way, Moors law is dead. Is that is that is that official?

</details>

**Speaker B**: 它已经死了好几年了。

<details>
<summary>Original English</summary>

**Speaker B**: It's been dead for years.

</details>

**Speaker A**: 它已经死了好几年了。那是为什么呢？

<details>
<summary>Original English</summary>

**Speaker A**: It's been dead for years. Like why why is that?

</details>

**Speaker B**: 嗯，你只需看看半导体制造业的进展就知道了。你知道，摩尔定律最初的表述是经济学层面的，对吧？它讲的是，我们在每个24个月或者别的什么周期内，有能力在同一块芯片上放置两倍数量的晶体管。而如今，情况绝对不再是这样了，并且大概在过去5到10年里都已经不是这样了。我们仍在扩大我们的系统规模，对吧？这通过很多种方式实现。其中之一就是堆叠更多的硅片。我们还在让晶体管继续变得更小、更高效，尽管步伐放缓了，但与此同时它们也变得昂贵了许多。所以，在摩尔定律还生效的时代，打造未来系统的最佳方式是采用当前的系统，然后直接缩小它的尺寸，同时可能让其性能翻倍，对吧？但在我们已经身处其中一段时间的这个新时代里，你无法再从缩小现有设计中获得经济效益了，你真的必须更加巧妙地思考如何利用系统的每一个部分。这就是为什么在这个时代，加速计算比以往任何时候都更有价值，因为我们需要从第一性原理出发思考问题，并协同设计绝对一切的东西——从晶体管到算法再到应用程序——以减少……

<details>
<summary>Original English</summary>

**Speaker B**: Well, you just look at the the progress uh in semiconductor manufacturing. You know, the the original statement of Moore's law was economic, right? It was about we can afford to put twice as many transistors on the same chip in every whatever 24 months, whatever the the time period is. And um these days that is absolutely not the case and it hasn't been for probably 5 or 10 years right now. We are still scaling our systems right um through a number of ways. One is just applying a lot more silicon to it, right? uh we are also getting transistors are continuing to get smaller and and more efficient although at a slower pace but they're also getting quite a bit more expensive at the same time. Um uh so the uh you know in an era where where Moore's law was alive, the best way to make the system of the future was to take the system of the present and then just shrink it and and maybe double it at the same time, right? But in an era where where we've been living for a while now where you don't get economic benefits from taking your existing design and shrinking it, uh you really have to be more clever about how you use every part of the system. uh that that's uh you know an era where accelerated computing is is much more valuable than ever because the the work of thinking through the pro problem from first principles and co-designing absolutely everything uh from transistors to algorithms and applications uh in order to reduce

</details>

<!-- chunk 4/10 -->

### 提供有意义的加速与Nvidia的模型业务

**Speaker B**: ……浪费并且能够提供有意义的加速，这比以往任何时候都更有价值。

<details>
<summary>Original English</summary>

**Speaker B**: waste and and deliver meaningful acceleration that's more valuable than ever.

</details>

**Speaker A**: 太棒了。回顾一下你一分钟前所说的话。Nvidia涉足模型业务在商业上是非常合理的，因为第一，这有助于设计更好的芯片；第二，任何对AI有利的事情最终都会对Nvidia有利，这非常说得通。Neotron（尼奥创）这个项目是最近才开始的，对吧？我相信它是在2023年启动的。或许你可以快速给我们梳理一下几个关键的发布节点。我相信在2023年发布了Neotron 38B作为一个关键版本，还是说我漏掉了哪一步？

<details>
<summary>Original English</summary>

**Speaker A**: Fantastic. to play back what you were saying uh a minute earlier. It makes good business sense for Nvidia to be in the model business because one it helps design better chips and two uh whatever is good for AI is ultimately good for Nvidia which makes a lot of sense. That Neotron effort is reasonably recent, right? It started in 2023, I believe. Maybe walk us quickly through the key releases. I believe in 2023 there was Neatron 38B as a key release or am I missing a step?

</details>

**Speaker B**: 是的。是的。是的。所以，你知道，有些版本号已经随时间流逝而模糊不清了。我甚至觉得我们好像身处《指环王》的世界里，就像是我们从一个古老的矿井中挖掘出了一些古老的遗物。嗯，你知道，那是很久以前的事了。你知道，我们最初称之为Neotron 1的其实是我们与微软合作的一个项目。嗯，我们联合训练了一个5300亿参数的模型。嗯，我相信那是在2021年发布的。所以那是GPT-3的时代。嗯，当时我们把它叫做Megatron Turing NLG。Turing（图灵）是微软当时对他们语言模型工作的命名。但回过头来看，我们把它叫做Neotron 1。然后在这个过程中我们又构建了几个版本，一直到了Neotron 3。接着Llama出现了，我们对此感到非常兴奋。我们非常高兴Meta能够支持开放的AI技术领域。所以我们开始把我们的语言模型技术应用到Llama模型中，于是便诞生了Llama Neotron 1。而且你也知道，这是第一个基于Llama构建的推理模型。我们对此感到非常自豪，而且——

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Yes. Yes. So, you know, the the you know, the the numbering is somewhat lost to time. It I almost feel like we're in the Lord of the Rings and it's like, you know, there's like some ancient like relics that we're digging up out of an old mine. Um, you know, this is a long time ago. You know, the original what what uh we originally called Neotron 1 was actually a project that we did with Microsoft. Um, we jointly trained a 530 billion parameter model. Um, I believe that was released in 2021. And so this is GPT3 era. Um, and that's what um, at at the time we called it Megatron Touring NLG. uh touring was uh what Microsoft was calling their their language model efforts um at the time. But uh uh that uh in retrospect we called Neotron 1. Uh then along the way we built a few more uh we got up to Neotron 3. Um and then uh Llama came along uh and we were really excited about that. We were very happy that Meta was supporting the open uh AI technology space. Um and so we we started um you know taking our language model technology and adding it to llama models which then resulted in llama neatron 1. Um and you know that was the first uh reasoning model uh built on llama. Uh we were really proud of that and

</details>

**Speaker A**: 那是在2025年。

<details>
<summary>Original English</summary>

**Speaker A**: that was 2025.

</details>

**Speaker B**: 可能是24年，我想我有点记不清了，大概是那个时候。嗯，然后……是的，然后我们继续进行开发。最后我们……版本号好像又重新开始了。我们发布了Neotron 2，我相信那是在去年。接着我们很快又推出了Neotron 3，因为我们需要加入相关的支持。Neotron 2当时没有加入支持，这使得它在与其他模型竞争时显得有些劣势，比如GPT OSS 20B当时速度非常快，就是因为这个，所以我们觉得，好吧，我们必须得把它加进去。于是那就成了Neotron 3。现在我们处于一个略微尴尬的境地，因为你知道我们正在研发Neotron 4，对吧？但我们在2024年已经发布过一个被称为Neotron 4的340B模型。所以，我不完全确定我们要如何解决这个营销上的问题。这个营销问题可不是我制造出来的。所以，我会尽我所能地去解释清楚，无论我们什么时候发布那个全新的Neotron 4，它都将与2024年版的Neotron 4是不同的。但无论如何，我们在这一块已经耕耘很长时间了。我认为对我们来说，比起任何特定一代的模型，更重要的是Nvidia在开发这些模型上所展现出的持续承诺。我们已经做了一阵子了。我认为在过去的一年中，我们的模型变得极为有用。这主要反映了两件事。第一，整个公司已经齐心协力。现在Nvidia内部有许多不同的团队，他们懂得了这件事对Nvidia的未来有多么重要。因此，投入到Neotron中的人力和优秀创意有了大幅度的增加。然后，第二点，伴随而来的是我们能够扩展投入其中的计算资源。显然，拥有良好的计算基础设施对于构建AI是非常重要的。我们最近大幅增加了投资，因为我们相信这真的是我们公司未来的关键。

<details>
<summary>Original English</summary>

**Speaker B**: Uh might have been 24 uh I I believe I can't remember uh somewhere around there. Um and then uh uh yes and then we we continued uh to to develop that um uh and uh you know last we we so we the numbers kind of started over again. We released a a Neotron 2 um I believe it was last year. Um and then we quickly followed that up with Neatron 3 because um uh we we needed to put support in. Neatron 2 didn't have support and that made it kind of uncompetitive against uh other models like GPT OSS 20B was just like so fast because of so we were like okay we've got to we've got to put put thee in. So that became Neatron 3. Um now we're in a a slightly difficult state because you know we're working on Neotron 4 right but we already released a Neotron 4 which was um in 2024 we released a 340B uh model called Neotron 4. Um, and so I'm not exactly sure how we're going to um solve this marketing problem. I didn't create this marketing problem. Uh, so uh I'll I'll I'll do my best to to make it clear that Neotron 4 of of of whatever the NE whenever we release that is different from the the 2024 Neotron 4. Um, but uh in any case, we've been working on this for a long time. I I think um more important to us than any particular generation is just the sustained commitment that Nvidia has to developing these models. We've been doing it for a while. I think our models have gotten dramatically more useful in the past year. Um which is a reflection of two things primarily. One is that uh the whole company has come together. So there are many different teams around Nvidia that now understand how important this is to Nvidia's future. And so there's dramatically more people and better ideas that are going into Neotron. Um and then uh number two along with that we've been able to scale the um compute resources that go into it. Um obviously it's um very important to have good computing infrastructure to build AI. We've um recently increased our investment substantially because uh we believe that that this is really really key to our company's future.

</details>

**Speaker A**: 令人着迷。

<details>
<summary>Original English</summary>

**Speaker A**: Fascinating.

</details>

**Speaker B**: 但为了接续刚才的思路，我认为让所有人都知道我们在这方面已经投入了很长时间，这真的非常重要。我们正在大幅度增加我们的投资，而且Nvidia是一家能够坚持到底的公司。你知道，我们在CUDA上坚持了10年以上，现在我们在Neotron上也在做同样的事情。

<details>
<summary>Original English</summary>

**Speaker B**: But I just to continue the thought I think it's really important that everybody knows that we've been doing this for a long time. We are increasing our investments substantially and Nvidia is a company that follows through. You know we followed through over 10 plus years with CUDA and we're doing that with Neotron. Now

</details>

### Neotron 联盟与开源生态

**Speaker A**: 了解这些非常有帮助，因为我认为更广泛的外部世界才刚刚开始意识到，这里一直有一股非常实质性的开源前沿AI研究力量在运作。所以听到这个过程真的很令人感兴趣，现在有了这么一个模型家族，我们稍后就会谈到它。另一个重要的时刻似乎是仅仅在3个月前，也就是今年3月份创立了Neotron联盟。你想简单解释一下那是什么吗？

<details>
<summary>Original English</summary>

**Speaker A**: that's very helpful because uh I think the the broader world is is just starting to catch up to the fact that there is a very substantial open-source frontier AI research effort that that's been happening. So it's really interesting to to hear that uh you know there's been this progression and now there's this family of models that we're going to talk about uh in a second. Another important moment seems to be uh the creation just in March 3 months ago of the Neotron coalition. Do you want to explain briefly what that is?

</details>

**Speaker B**: 所以，Neotron的存在是为了帮助支持这个生态系统，我们当时在想，这和业内其他的AI项目不同，对吧？因为我们其实并不是想要以任何方式去主导。我们只是想要去支持，我们不是要去控制AI是如何被整合到这些公司里的。我们只是想确保能够有优质的AI。但我们想，如果在我们开发它的时候能够和大家合作，那么它对大家来说就会变得更有用。由于从一开始我们就考虑了他们的需求，这会让它更容易被整合进去。而且你知道，Neotron一直都是合作性的。我刚才还跟你说，很久很久以前，我们训练的第一个大模型就是跟微软一起做的，对吧？那是一项联合的努力，Nvidia和微软的研究人员并肩工作，共同打造了它，我认为那最终让Nvidia和微软都受益匪浅。我认为我们双方都从那次经历中学到了很多。所以，因为Neotron并不是试图去跟其他公司竞争，而是为了提供支持，因为无论如何我们都会将其开源发布，那为什么不在模型构建完成之前就展开合作呢？与其让Neotron成为一个Nvidia完全自己闭门造车，然后往网上一扔说：“嘿，你们为什么不试试这个呢？我们觉得它可能很不错。”倒不如我们和那些感兴趣的合作伙伴一起合作，在Neotron诞生之前就确保它对他们是有用的，并且结合各种反馈、评估、环境、基准测试，或者是其他人想要带来的任何其他类型的技术。事实证明，整个生态系统里有很多公司都真心希望开源模型能够成功，因此他们有自己的利益诉求。他们有着确保开源技术保持卓越的既得利益，那为什么不与他们合作，让他们按照自己喜欢的方式来为让Neotron变得更好而做出贡献呢？这就是Neotron联盟的理念。它并不是一个排他性的联盟。我们并不是想成为市面上唯一的模型。所有与我们合作的公司都可以自由地继续以对他们有意义的方式开展工作。然而，你知道，这些公司愿意跟我们合作，是因为他们想确保用于AI的开源技术能够继续快速发展，并且他们有机会去影响这个发展的过程。

<details>
<summary>Original English</summary>

**Speaker B**: So, Neotron exists to help support the ecosystem and we were thinking, well, this is a different kind of AI project than other projects around the industry, right? Because um we're not actually trying to dominate in any way. We're just trying to support we don't we're not trying to control uh uh the way that AI is um uh being integrated into all these companies. We're just trying to make sure there's good AI. But we thought well maybe if we worked with people while we develop it then it's going to be more useful for them. It'll be easier to integrate because we will consider what they need from the beginning. And um you know Neotron has always been collaborative. I was telling you that you know long long time ago our first big model that we trained we we did with Microsoft right? It was a joint effort where Nvidia and Microsoft researchers worked side by side to build that and that um that ended up I think helping both Nvidia and Microsoft. I think we both learned a lot from that um experience. And so because Neotron is not trying to compete with uh other companies, but rather support, uh because we're going to be putting it out there openly anyway, why not collaborate before the thing is built? Rather than Neotron being a project that Nvidia does all on its own and then posts on the internet and says, "Hey, why don't you try this? We think it might be good. Why don't we make sure that it's good for the partners that um uh that are interested by working with them before Neotatron is even created um and incorporating you know any sort of feedback evaluations environments um uh benchmarks um or any other um kinds of technology that other people want to bring. It turns out that the entire ecosystem there's a lot of companies that really want open models to succeed and so they have a self-interest. they have their own vested self-interest in making sure that open technologies are excellent and so why not um work with them and and let them contribute uh however they'd like to to making Neotron better. So that's the the idea of the Neotron coalition. It is not an exclusive coalition. We're not trying to be the only model out there. All the companies that we work with are free to to continue doing the work however makes sense to them. And yet um you know these companies want to work with us because they want to make sure that um open technologies for AI keep um developing quickly and that they have a chance to influence how that happens.

</details>

### Neotron 模型家族介绍

**Speaker A**: 太好了。目前Neotron模型家族的现状如何？你们有Nano（纳米版），有Super（超级版），还有Ultra（极限版）。这些模型都是做什么的？它们各自的应用场景又是什么呢？

<details>
<summary>Original English</summary>

**Speaker A**: Great. What's the current state of the Neimontron family? You got nano, you got super, you got ultra. What do those models do and what are the use cases for them?

</details>

**Speaker B**: 所以Nano是一个300亿总参数、30亿激活参数的模型。Super是1200亿总参数和120亿激活参数，而Ultra则是5500亿总参数和550亿激活参数。它们被设计出来，其实是为了适配小、中、大型的部署场景。你知道，对于那些不需要那么多知识或推理能力的任务，Nano可以表现得非常出色，但显然如果是为了获得能力最强的模型，你就会去选择Ultra。在很多方面，Super是我们最受欢迎的模型，因为它在成本和智能之间达到了一种极好的平衡。所以我们挺喜欢这种构建模型家族的大、中、小策略，因为我们的客户似乎对此反响相当不错。但是，你知道，从Nvidia的角度来看，人们在使用大语言模型时所做的最重要的事情，其实是构建智能体，也就是构建具有智能体特性的……

<details>
<summary>Original English</summary>

**Speaker B**: So nano is a 30 billion um uh total 3 billion active parameter model. supers 120 and 12 and ultra is 550 and 55. Um they're designed um really to fit, you know, it's kind of small, medium, and large um uh deployment scenarios. Um uh you know, Nano can be really capable for things that um you know don't require nearly as much knowledge or reasoning, but obviously for the for the most um capable model, you go for ultra. Um, super in a lot of ways is our most popular model because it represents kind of a great balance between um cost and and intelligence. So we we kind of like um having this small, medium, and large um approach to building a family just because our customers um seem to respond to that um pretty well. But um you know uh the most important thing from Nvidia's point of view that people are doing with uh uh with LLMs is agents right is um building agentic

</details>

<!-- chunk 5/10 -->

### Agentic Workflows & Neotron's Efficiency

**Speaker A**: 拥有一个全天候为你排忧解难、代为执行各种任务的智能代理工作流（agentic workflows），这绝对是一种令人无比兴奋且极具前瞻性的问题解决方式。这为我们处理日常需要应对的繁杂挑战提供了一条全新的奇妙途径。而且，你知道，让 Neotron 在这一特定的代理目标和复杂用途上表现得无比出色，正是我们梦寐以求的事情。这也就是我们始终孜孜以求的核心目标和愿景。

<details>
<summary>Original English</summary>

workflows having an agent working on your behalf solving problems for you night and day. Um such an exciting way of approaching the problems that we have to solve. Um and um it's our dream to make Neotron amazing for that purpose. That's our goal

</details>

**Speaker B**: 为了在宏观层面上对这个问题进行更为深入的探讨，我们了解到 Neotron 产品系列主要聚焦于代理推理（agentic reasoning）领域，并且特别注重于如何让这种复杂的推理过程变得更加高效。我们可以把这个总结作为描述你们目前发展重心的合适头条吗？

<details>
<summary>Original English</summary>

>> to double click on this at a high level. Neotron family is focused on agentic reasoning with a particular focus on making it efficient. Is that is that the right headline?

</details>

**Speaker A**: 完全正确。是的。因为英伟达（NVIDIA）本质上是一家加速计算公司，所以 Neotron 在构建模型时，始终坚决贯彻“速度优先”的底层理念和方法。正如我刚才所阐述的，我们正试图从第一性原理出发，从纯粹的计算角度去彻底思考和剖析这其中的核心问题到底是什么。而且，你知道的，Neotron 3 系列架构中包含了很多让我们感到无比自豪的尖端创新元素。举个具体的例子，Neotron Ultra 和 Super 这两个大规模模型都是使用极其前沿的 4 位（4-bit）算术精度进行预训练的。我们在预训练它们时，全面采用了 MVFP4 数据格式。你要知道，设计并创造出一种全新的算法，让你的大模型能够在使用如此粗糙的算术精度下依然能够平稳收敛，并最终取得极佳的训练成果，这绝非是一件轻松容易的事，它需要投入巨量的创新思维和工程努力。我们对这项技术成就真的感到非常骄傲。也许你可以借此机会，为大家详细解释一下，比如 4 位精度和传统的 16 位精度之间到底有着怎样的本质区别？

<details>
<summary>Original English</summary>

>> That's right. Yeah. Um Neotron has always been um uh speed first approach to building models because NVIDIA is an accelerated computing company. As I was saying, we're trying to think through what is the problem here computationally from first principles and um you know Neotron uh 3 family has a lot of things in it that are uh we're really proud of. For example, um Neotron Ultra and Super uh were pre-trained using 4bit arithmetic. We pre-trained those in MVFP4 um which you know uh is a not trivial thing to do to invent the algorithm so that your model can converge to an excellent result using such coarse arithmetic uh required a lot of invention. Really proud of that. Do you want to explain maybe for for people what 4bit is versus 16 bit for example?

</details>

### The Magic of 4-bit Arithmetic in AI Models

**Speaker C**: 你知道吗，其实就在昨天，我在 Hacker News 上看到了一篇非常令人惊叹的帖子。那里面有人开发了一个实用的小工具，让你可以上传任何一张照片，然后该工具基本上会对照片进行所谓的“色调分离（posterize）”处理，它的本质操作就是减少画面中的颜色数量，以此来强行适应各种不同的底层数字格式，其中就包括了 NVFP4、MXFP8，以及市面上流通的其他一些数值格式。因此，你可以用手指在屏幕上随意滑动对比，直观地观察这种降精度操作对一张照片的色彩还原究竟产生了什么实际影响。而且，你会亲眼目睹这种变化真的是相当具有戏剧性和冲击力的。毕竟，四位（4 bits）的位数容量实在是非常之少，对吧？它满打满算仅仅能够表示 16 种不同的数值。当然了，如今我们所谈论的这些，实际上都属于被称为块缩放格式（block scaled formats）的范畴。所以，通常一组较低精度的数字还会共同伴随一个 8 位（8-bit）的独立缩放因子。涉及到这部分的技术细节可能会变得相当晦涩和复杂，所以也许对于普通听众来说，它们并不是当前讨论中最关键的部分。但是，我们之所以如此执着于采用这种超低精度方案，其核心原因在于：首先，在我们的 GPU 硬件上，特别是在最新一代的 Blackwell Ultra 架构上，处理这些特殊格式的数据吞吐量有着极其惊人的提升；其次，我们清楚地知道，这种转变将会节省极其庞大、近乎天文数字般的能量消耗。思考当前人工智能所面临的计算瓶颈，其中一个至关重要的角度就是，我们注定将始终在资源的极限状态下维持运转。无论这个无形的极限到底是什么，它有可能是一个严苛的经济极限，比如我们总共只有这几十亿美元的有限预算，只能用来购买数量特定的计算服务器。它也极有可能是一个更为物理的电力极限，比如我们当前能够负担得起、或者电网能够提供的用于训练大模型的电力容量，总共就只有那么几十吉瓦而已。但不管这个最终的瓶颈极限落在哪里，我们都注定要在那个极限的边缘高负荷运转。任何一家涉足这个领域的组织，每一家有抱负的科技公司，都会不可避免地面临同样的处境，为什么呢？因为智能（intelligence）所蕴含的潜在价值实在是太不可思议、太高昂了，你知道的，所以人们、投资者、科技巨头们一定会不遗余力地去投入资金，因为他们心中无比确信自己最终能够从中获得极其丰厚的技术红利与商业回报。智能所带来的潜在价值真的是无穷无尽、不可估量的。因此，如果你在内心深处接受了“我们将不可避免地始终在极限状态下运行”这一客观事实，那么由此推导出的必然结论就是：获取更多智能的唯一现实途径，就是让自己在计算上变得更加极致地高效。如果我们当前已经彻底触及了资源的物理或经济极限，我们显然无法再通过简单粗暴地投入更多算力蛮力来获取更多的智能。我们必须静下心来，更加深思熟虑地考量该如何压榨出我们现有每一份资源的全部价值。你要知道，在庞大的计算系统中来回移动 4 位数字格式的数据，其成本要低廉得多得多。它们不仅在宝贵的显存中占据的空间小得多，而且当你将它们从内存中提取出来，或者仅仅是在芯片内部的各个处理单元之间进行来回传输时，它们所消耗的皮焦耳（picojoules）能量也显著更少。当然，当算术单元真正对它们执行数学计算时，消耗的能量也是大幅度降低的。所以，正是上述的这些综合因素，真正在幕后强力驱动着整个行业对 4 位格式技术的狂热投资。而且我认为，时至今日，用于模型推理部署阶段的 4 位格式技术标准已经变得非常成熟和广为确立了。在当下，将一个庞大模型压缩，制作出一个可以直接用于部署的、性能优秀的 4 位量化检查点（quantized checkpoint），已经是一件相当直接和顺理成章的常规操作了。这一步骤能够立刻为你带来许多在推理阶段的运行成本和响应速度上的巨大优势。然而，如果要将 4 位格式直接应用于模型从零开始的预训练（pre-training）阶段，那所面临的困难和挑战就完全是另一码事了，其难度要大得多。因为在训练过程中，你有一个极其敏感的数值求解器（numeric solver）在不断地反向传播并优化海量的神经网络权重。如果你在计算过程中没有极度谨慎地、绝对正确地处理这些极其粗糙的数字，你的模型就有极大的风险会直接发散（diverge）。一旦发生这种情况，其惨烈结果就是，你不仅没有成功熬过漫长的预训练阶段并获得一个训练完毕的模型，你最终得到的，基本上只是一个因为数值爆炸而彻底发散的废弃运行记录。你知道，这对于任何消耗了巨量算力资源的团队来说，始终是一件令人毛骨悚然、无比恐惧的事情。所以，为了能够让我们真正在 4 位精度的极端环境下成功对 Neotron 进行预训练，这背后耗费了我们无数的心血和大量的发明创造。我们对最终能够攻克这一难题，真的感到无比的自豪。

<details>
<summary>Original English</summary>

>> You know, actually there was a fantastic post I saw in Hacker News yesterday where somebody let you um upload a picture and then it would basically posterize it, basically reduce the colors to fit different um uh number formats including NVFP4 and MXFP8 and some of the other formats that are out there. And so you could kind of swipe around and look what it does to the colors of a picture. Um and you know it's it's really quite dramatic. Four bits is not a lot of bits, right? That's only 16 values. Um now, of course, these are all um what are called block scaled formats. So, um groups of numbers also come with uh an 8bit um scaling factor. And the the specifics of this can get rather complicated. So, maybe they're not quite as important. Uh but the the reason why we want to do this is because first of all we have dramatically higher um throughput for these formats in our GPUs um specifically on Blackwell Ultra. Um and uh uh secondly, we know that it's going to save an enormous amount of energy. Um one one way to think about uh the computational problem of AI is that we are going to be running at the limit. Whatever the limit is, it could be uh an economic limit like we only have so many billion dollars to to buy servers with. It could be a power limit. We only have so many gigawatts that we can afford to to train a model with. Whatever the limit is, um uh we're going to be running at that limit. The or every organization is is because why? Because the value of intelligence is so high, you know, that that people are going to they're going to invest because they they know that they're going to get return. um uh the value of intelligence is is enormous. Um so if you if you accept as the truth that we're going to be running at the limit, then what that means is that the way to get more intelligence is to be more efficient. We can't get more intelligence by applying more force if we're already at the limit. We have to be more thoughtful about how we use what we have. And you know, 4-bit number formats are dramatically cheaper to move around. They take up less space in memory. um they take up less uh pico jewels when you move them from the memory um in or even on the chip uh around the chip much less uh energy when you compute on them and so uh so that's really um driving you know the investment in 4-bit formats and I think these days 4-bit formats for uh deployment are very well established um it's it's pretty pretty um straightforward these days to make a a good quantized uh four-bit uh checkpoint that you can deploy and that gets you a lot of inference cost and speed advantages. Um but using 4-bit formats for pre-training uh that's quite a bit uh more challenging because uh you have this um numeric uh solver that's you know optimizing the weights and um you know it it can be quite sensitive. So if you if you don't uh treat the numbers right uh your model can diverge uh and instead of actually getting a model done through pre-training you end up with you know basically just uh that run diverged which is you know always always scary. So it it took a lot of invention for us uh to be able to pre-train Neotron uh in 4bit. We're really proud of that.

</details>

### Hybrid Architecture: Transformers & State Space Models

**Speaker B**: 好的，这真是太棒了。那么，随着我们探讨的内容稍微深入到一些更为底层的技术细节，有报道称 Neotron 采用的架构似乎是混合型（hybrid）的。这个说法准确吗？所以，它本质上是一个融合了经典 Transformer 和状态空间（state space）模型的综合体，这在目前看来是一种稍微更为奇特、相对少见的新型架构形式。请带我们详细地了解和梳理一下这个架构吧。

<details>
<summary>Original English</summary>

>> Okay great. All right. So, as we uh get into slightly more technical things, the uh architecture of Neotron uh is hybrid. Is that is that right? So, it's a combination of transformer and member state space which is a slightly more exotic uh form of of of architecture. Walk us through that.

</details>

**Speaker C**: 是的，你知道的，我们团队在 2024 年曾经发表过一篇极具影响力的学术论文。那篇论文通过严谨的实验证明，通过将新兴的状态空间模型（SSM）与成熟的 Transformer 模型巧妙地结合在一起，你实际上可以训练出一个在各个维度上都更加智能的复合模型。为了验证这一点，我们实际上进行了一次非常全面且详尽的参数扫描和架构探索，试图弄清楚在一个宏大的模型架构中，到底应该分配多少比例来执行传统的全注意力（full attention）机制，同时又应该保留多少比例来部署状态空间模型，才能最终获得具有最低困惑度（perplexity）的优异结果。简单来说，这一切探索都是为了打造出你在理论和工程上所能获得的最强大的语言模型。在经过一系列复杂的实验后，我们惊讶地发现，实际上你最理想的配置是让它主要作为一个基于状态（state-based）的模型来运行，同时在关键节点辅以少量的传统注意力机制。这背后蕴含的直觉其实非常有趣，那就是状态空间模型似乎天生就更擅长对一个冗长的时间序列产生一种类似于人类直觉式的、宏观且印象派的深刻理解。这是为什么呢？因为它们在运行时的本质，基本上是在不断地将整个历史序列的所有关键信息压缩、提炼，并总结到一个尺寸恒定的潜在状态空间（constant space）之中。这正是它们之所以能够高效工作的底层数学原理，对吧？因此，它们并没有被赋予那种能够随时随机回头审视和检索整个庞大序列历史中任意节点的全局能力。取而代之的是，它们被迫在处理每一个时间步长时，将之前吸收的所有重要信息精炼总结到一个恒定大小的内存缓存（cache）里，或者你可以把它想象成是它们正在高速运转时所使用的一本容量有限但内容高度凝练的小型“草稿本（scratch pad）”。而令人意想不到的是，正是这种看似限制了模型自由度的严苛数学约束条件，似乎在某种程度上反而倒逼它们在处理某些需要建立宏大全局理解的复杂任务时表现得更加智能。另一方面，传统全注意力机制的不可替代的优势则在于，它拥有上帝视角，可以极其精准地在浩如烟海的历史数据中提取出非常具体、极其细微的信息片段，并对这些片段进行像素级精确的审查和利用。在使用全注意力机制时，它绝对不会遗漏任何哪怕是最微小的细节。在这个过程中，没有发生任何会丢失重要信息的有损压缩（lossy compression）操作，你实际上能够一览无余、毫无保留地看到整个数据序列的完整全貌。所以，经过深思熟虑的设计，我们发现，将这两种在原理上截然不同的机制互补性地结合起来使用，其最终展现出的性能和智能程度实际上要远远优于单独依赖其中任何一种单一架构。而且，必须要强调的是，这种智能层面的根本提升，是完全独立于它所带来的运行速度优势而独立存在的。这纯粹意味着模型在理解能力上变得更加聪明了。你知道，自从我们在业内首次发表了那篇突破性的论文之后，我认为有很多其他顶尖的研究实验室在进行复现后，也纷纷发现并确认了这一结论是确凿无疑的。我们现在可以看到，市面上有很多最新的模型在构建其底层架构时，都开始积极采用混合型 SSM（状态空间模型）的前沿方法。举个明显的例子，QN 团队在他们的新一代模型中就已经采用了这种做法。此外，Kimmy 团队目前也在他们的新模型中积极部署并使用了他们自己命名的所谓“Kimmy 线性注意力机制（Kimmy linear attention）”。所以，我认为在构建先进的基础架构（base architecture）时，将某种形式的、高效的状态模型与传统的全注意力机制混合并在协作中使用，如今这在行业内已经变得相当普遍，并被广泛认可和采纳了。不仅如此，除了智能上的提升，这种混合架构目前在运行速度上也展现出了极其惊人的显著优势。原因在于，在训练和推理过程中，你需要用来保存并维持那个状态空间缓存（cache）的内存显存量，相对于你不断增长的输入序列长度来说，实际上是一个令人欣慰的恒定常数。这就顺理成章地意味着，在进行大规模模型训练和高并发推理时，你通常可以在有限显存的 GPU 上轻松容纳下规模大得多的批次（batches），因为单次处理的内存需求被大幅度地压低了。这直接导致 GPU 能够始终保持在一种更加饱满、更加繁忙的高强度工作状态，最大化了硬件的利用率。因此，你也知道，这理所当然地为系统提供了大量相当关键、极其可观的效率收益和性能红利。

<details>
<summary>Original English</summary>

Yeah, you know, we published a paper in 2024 that showed that you actually get a smarter model by combining um state space models with transformers. And we we actually did a sweep of uh you know, how much of the model should be full attention and how much of it should be um a state space model in order to get the the lowest perplexity, basically the best the best language model um that you could get. And we found that you actually want it to be mostly a state-based model with a little bit of attention. And so kind of the intuition behind that is that um the state space models seem to be better at um kind of this intuit um intuitive kind of impressionistic understanding of a sequence um uh because they're um you know they're kind of summarizing the entire sequence into a constant space. That's how they work, right? So instead of having the ability to look at the entire sequence randomly, uh they summarize everything at every step into a constant um cache or little scratch pad that they're they're working on. And um that constraint seems to actually make them smarter at some tasks that involve like global understanding. Um on the other hand, the advantage of full attention is that it can pick out very specific uh bits of information and look at those exactly. It doesn't lose anything. There's no lossy compression going on. and you can actually see the whole thing. Um, and so we found that um, uh, you know, using both of these together was actually better than using either one on their own. Um, and that is independent of the speed benefit. That is just the model is smarter. And you know, since we published that, I think a lot of other um, uh, labs have also found this to be true. Um, you know, a lot of uh, uh, models these days are being built with hybrid SSM approaches. For example, QN has done that. Um, Kimmy is using what they call Kimmy linear attention these days. So, um, it's become, I think, quite widely adopted to use some sort of state-based model in conjunction with um, full attention for um, uh, for the the base architecture. Um now it also has some speed benefits because um the uh uh amount of memory that you need to hold uh that state space uh cache is actually constant with respect to your sequence length. um which then means that um generally you can fit much higher batches on the GPU when you're training and doing inference uh because the memory um requirement is lower and it keeps the GPU uh fuller and busier um and therefore um you know provides some some pretty important signific uh some some pretty important efficiency benefits as well.

</details>

### Mixture of Experts (MoE) & Sparsity

**Speaker B**: 所以，据我所知，这些最新模型在底层设计上，也同样是基于广为人知的专家混合（Mixture of Experts，简称 MoE）架构的。请您稍微花点时间，为我们通俗易懂地讲解一下这个复杂架构的运作原理，也许在开始之前，可以先帮部分不熟悉的观众回忆一下，专家混合架构从最基础的概念层面来说，到底是什么意思？

<details>
<summary>Original English</summary>

>> So the models are also based on ane mixture of expert architecture. walk us through that and maybe remind people what is in the first place.

</details>

**Speaker C**: 所谓专家混合（Mixture of Experts）架构，在深度学习领域中，它本质上就是一种实现网络参数稀疏性（sparsity）的极为高级的表现形式。这里所蕴含的核心且极具启发性的理念是，哇，当你试图用整个互联网上浩如烟海、包罗万象的数据来训练一个终极语言模型时。你的初衷无疑是希望它能够如同全知全能的神明一般，绝对记住并掌握关于世间万物所有历史演变的全部浩瀚细节。但是，当你向这个模型抛出一个极其具体、非常局部的问题时，为了仅仅给出一个清晰准确的答案，强求模型在进行推理的瞬间，真的去在脑海中翻腾并重新思考整个宇宙的全部浩瀚知识体系，这在计算逻辑上听起来难道是一件合理且高效的事情吗？其实，这在现实中是完全不合理的。在处理绝大多数的具体任务时，模型所需的知识调用机制似乎应该是高度稀疏的，对吧？它实际的运作过程看起来更像是，我们是在驱使一个无所不知的语言模型，在一个为了解决当前特定问题而临时划定的、极其微小且高度聚焦的思想空间里进行深度的探索和挖掘。在日常使用中，我们当然无比渴望模型具备一种随时随地能够从其浩瀚无垠的知识宇宙中精准调取所需信息的能力。我们夜以继日地训练它，终极目的就是为了让它尽可能广泛、尽可能深刻地理解它所能接触到的宇宙万物。但是，当它真正被部署在服务器上、并开始实时处理用户请求和运行推理运算时，它在每一微秒的时间切片里，其实根本不需要盲目地去查看、激活并遍历其庞大参数库中的所有那些冗杂且毫无关联的背景信息。过去在如何实现这种高效的选择性激活方面，学术界和工业界已经涌现出了极其多种多样的技术方法来尝试解决这一难题。

<details>
<summary>Original English</summary>

>> So mixture of experts is a form of sparsity. Um the idea is wow, you want to train a model on the entire internet. You want it to remember absolutely everything about the history of everything. But when you're answering a particular question, does it seem reasonable that it needs to actually think about the entire universe in order to answer that question? Actually, no. It seems like it's quite sparse, right? It seems like um we're we're we're using a language model to explore a very tiny space of ideas in order to answer a question or solve a problem. We want the model to be able to draw from the entire universe. We want to train it so that it understands everything that it possibly can. But when it's actually running, it doesn't really need to see all of that information. There's been a variety of approaches to

</details>

<!-- chunk 6/10 -->

### 混合专家模型 (Mixture of Experts) 的工作原理

**Speaker A**: 尝试利用这种特性，但混合专家模型（Mixture of Experts, MoE）一直是最成功的。它的工作原理是，神经网络中有一个被称为“路由器”（router）的组件，它是经过训练学习而来的，用来决定对于流经模型每一层的每一个 token，将激活信号发送给专家的一个子集。在试图理解输入、建立对问题的表征并生成我们要输出的下一个 token 时，它会做出选择，决定模型的哪一部分实际上会参与到与这个 token 的交互中。所以这有点像，如果我有一家550名员工的公司，但其中55人是在工程部门，那么对于有关工程的会议，我希望这55名专家员工来参加，而不是公司的其他所有人。

<details>
<summary>Original English</summary>

**Speaker A**: that try to take advantage of this property, but mixture of experts has been the most successful. And the way that it works is that the neural network has what's called a router that is learned that um is going to decide to send activations to a subset of the experts uh for every token that's flowing through every layer of the model. It's going to be making choices about um which fraction of the model is going to actually get to interact with this token as we try to understand it, build up representations of the problem, and then generate the next token that we're going to output. So it's a little bit like if I have a company with 550 employees but uh 55 of them are in engineering I want the 55 employees who are specialists to come to my meeting about engineering and not the rest of the company.

</details>

**Speaker B**: 没错。是的。或者你也可以把它想象成一个图书馆。比如，如果你去图书馆做研究，你不会去读图书馆里的所有书。你的首要任务是弄清楚，为了找到你问题的答案，你需要去查阅哪些书。所以这就是这背后的核心理念。现在，这对我们构建的系统有着深远的影响。例如，对于 Blackwell 架构，Nvidia 全力以赴。这就是为什么我们打造了 NVL72，它允许多达72个我们的 GPU 彼此以极高的速度、极低的延迟读写对方的内存。那么为什么这很重要呢？这是因为，当你把一个 token 穿过层层堆叠的网络时，在每一层，你都有一个路由器，将这个 token 路由到其他地方。为什么不把你的专家进行划分，使得你不必把每一个专家都放在每一个 GPU 上，而是给每个 GPU 分配一个专家子集，然后在你将 token 推送穿过网络时，在不同的 GPU 之间非常动态地路由这些 token 呢。这在事前是无法预测 token 需要去哪里的，因为这对于那个特定模型、那个特定 token 来说是非常具体的。所以，这就是为什么我们要打造 NVL72，也是为什么 Blackwell 在应对当今 AI 模型的推理时如此惊人。这是因为我们在构建它时，对混合专家模型进行了深刻的思考，而这也印证了 Nemotron 的首要任务。你知道，如果我们没有在理解 AI 方面进行投入，我们就不可能把 Blackwell 架构构建好。而这也直接转化为 Blackwell 部署量的增加，对此我们感到非常激动。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. Yeah. Or you could think about it as a library. Like if you go into a library to do research, you don't read all of the books in the library. Like your first job is to figure out which books do you need to look at in order to find the answer to your question. And so um so that's kind of the the idea behind. Now have fascinating implications for the systems that we build. So with Blackwell for example, Nvidia went all in ones. That's why we built NVL72 which allows up to 72 of our GPUs to read and write each other's memory uh at very high speeds, very low latency. Now why is that important? It's because as you put a token through the stack of layers, at every layer, you have a router that's routing that token somewhere else. Why don't you partition your experts so that you know the experts are not sitting every expert on every GPU, but you have a subset of the experts assigned to each GPU and then you're routing the tokens between the GPUs very dynamically as you push uh the token through the network. Now um this is impossible to predict in advance where the tokens need to go because it's very specific to that particular token for that particular model. And so that's why we built NVL72 and that's why um Blackwell is so amazing for inference for you know today's AI models uh is because we thought deeply about mixture of experts when we were building it and this is speaking to Neatron's first job. you know, if if we hadn't been working on understanding AI, we wouldn't have been able to build Blackwell properly. And that, you know, has has translated directly into um you know, increased deployment um of Blackwell, which you know, we're we're we're very excited about.

</details>

### 潜在混合专家模型 (Latent MoE) 创新

**Speaker A**: 你刚才描述的这种叫做“潜在的”（latent）吗？还是那是一个不同的概念？

<details>
<summary>Original English</summary>

**Speaker A**: Is what you just described called latente or is that a different concept?

</details>

**Speaker B**: 潜在混合专家模型（Latent MoE）是我们在 Nemotron 3 系列中的一项具体创新。它的作用实际上是通过在计算期间对数据进行向下投影（down projecting），从而减少必须通过 NVLink 发送的通信量。所以你知道，每一个 token 都会产生一个向量，其核心思想是，我们将采用那个向量并学习一种方法来压缩它，然后将压缩后的数据发送穿过网络，随后在另一端对其进行解压缩。这样做的结果是，我们节省了网络带宽，并且在相同的推理成本下，我们获得了四倍数量的专家。所以你可以把它想成是，我们的图书馆的藏书量扩大了四倍，而在相同的推理成本下，由于这项特定的创新，我们能够读到四倍数量的书籍。

<details>
<summary>Original English</summary>

**Speaker B**: Latent MOE is a specific uh innovation that we have in Neotron 3 family and uh what it does is actually um reduces the amount of communication that has to be sent through envy link during computations by basically down projecting it. So you know every token is it produces a vector and the idea is like we're going to take that vector and learn a way to compress it and then send that compressed thing through the network and then we're going to uncompress it at the other end and as a result we save on network bandwidth and we also get four times the number of experts for the same inference cost. So you could think about it as like you know our library of books got four times bigger um and we get to you know read four times more books uh at the same inference cost because of because of this particular innovation

</details>

**Speaker A**: 总的来说，它正逐渐成为前沿 AI 的默认架构。

<details>
<summary>Original English</summary>

**Speaker A**: is in general becoming the default architecture for Frontier AI.

</details>

**Speaker B**: 是的，我相信很长一段时间以来它已经是前沿 AI 的默认选择了。它们在推理成本和智能表现之间提供了一个非常出色的结合。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah I believe have been the default um in Frontier AI for a long time. Um they're just a really good combination of inference cost and intelligence.

</details>

### 百万 Token 长上下文窗口

**Speaker A**: 太棒了。但它们也有缺点。它们占用的内存要大得多。如果你只有非常少量的内存，那么一个密集（dense）模型会显得更聪明。而且它们通常在两种情况下表现最佳：要么你以批大小（batch size）为一运行，也就是你基本上在运行单一任务；要么你是在运行一个巨大的数据中心，中间有无数的查询涌入。所以它们可能会有点棘手。Nemotron 3 Ultra 的另一个重要特征是其拥有 100 万 token 的上下文，也就是长上下文窗口。在整体应用中这有多重要？它使得模型能够做些什么？

<details>
<summary>Original English</summary>

**Speaker A**: Great. Great. But they have drawbacks as well. You know, they they take a lot more memory. Um uh if you have a very small amount of memory, a dense model is going to be smarter. Um and they also um they tend to work best either if you're running at batch size one. So you're running basically a single job or you're running a huge data center with like infinite queries coming in in the middle. They can be a little bit tricky.

Another important characteristic of Neimatron 3 Ultra is the 1 million token context. the the long context window. How important is that in the overall mix and what does it enable the model to do?

</details>

**Speaker B**: 上下文长度越长，我们就能用语言模型解决越具挑战性的问题。这使我们能够执行各种操作，比如在查询中附加各种信息，可以是一个代码库，也可以是各种指令。从长远来看，我希望我能拥有我个人的 LLM（大型语言模型），它能够阅读我的所有电子邮件，并帮我解答相关问题。我们能在特定查询中附加的信息越多，模型就能越有用。不过，对大量输入数据进行推理的成本会越来越高昂。因此，这也是为什么通常对上下文长度有多大存在限制的原因之一。但是对于 Nemotron 3，我们试图尽可能地将这个界限推得更远。我们认为一百万个 tokens 已经是巨大的数据量了，你可以用它完成许多事情。

<details>
<summary>Original English</summary>

**Speaker B**: The longer the context length, the more challenging problems we can solve with a language model. Um, that allows us to do things like append all sorts of information to a query, which could be a codebase, it could be instructions. Um, you know, uh, in in the long term, I'm hoping that I have my own personal LLM that's able to read all of my emails, you know, and help me answer questions about that. You know, the more information that we can attach to a particular query, um, the the more useful the model can be. Um, now, uh, it can get more and more expensive, right, to reason over large amounts of of input data. And um and so that's one of the the reasons why there's usually a limit on how big the context length can be. But with Neotron 3, we we tried to push it as far as we could go. Uh we think a million tokens is a lot of tokens. Um and you can do a lot of things with that.

</details>

### 上下文压缩与智能体工作流

**Speaker A**: Prisma 在多步骤的智能体（agentic）工作流中特别有帮助。关于上下文压缩（context compaction），有一个完全独立的讨论，那就是要确保模型不会在过多的 token 中迷失方向。所以你们对此是怎么看待的？

<details>
<summary>Original English</summary>

**Speaker A**: Prisma is particularly helpful in sort of multi-step agentic workflows and there's this whole separate discussion around context compaction to make sure that the model doesn't get lost in too many tokens. So like how do you how do you all think about this?

</details>

**Speaker B**: 绝对是这样。如果你在使用智能体工作流，压缩是你一直都要处理的事情。而且压缩的效果往往相当不错，因为语言模型非常擅长识别最相关的信息并进行总结，当你对上下文进行压缩时，你基本上就是在试图对其进行总结。所以，压缩并不是一个糟糕的方法。但我认为拥有那些本身就能够直接针对更大量数据进行推理的模型，在本质上是更有用的。因此，我们当然也希望能在这方面突破边界。

<details>
<summary>Original English</summary>

**Speaker B**: 100%. I mean um uh you know compaction is that's a thing if you're using an agentic workflow you deal with all the time. Um and compaction tends to work pretty well you know because language models um are pretty good at at identifying the most relevant things and summarizing and you're basically trying to summarize your context when you compact it. Um so uh compaction uh is is not a bad approach. I think having models that can just natively uh reason about larger amounts of data is just inherently more useful. So of course we want to push the the boundary on that as well.

</details>

### 多 Token 预测 (Multi-token Prediction)

**Speaker A**: 太棒了。你能不能谈谈多 token 预测？那也非常有趣。

<details>
<summary>Original English</summary>

**Speaker A**: Great. Can you talk about the multi-token prediction uh which is also very interesting

</details>

**Speaker B**: 如果你以低批大小运行，这通常是当你在数据中心中试图获得最高交互性时发生的情况。你希望模型能够尽可能快地响应，此时模型成本更高一些也没关系。你每个 token 的成本可能会更高，但你希望尽可能快地获得结果。或者如果你在本地运行，你可能也会以批大小为一进行运行，仅仅因为你是唯一在使用它的人。事实证明，GPU 还有闲置的额外执行能力没有被使用。在这些场景下运行时，大部分工作实际上是从内存中提取权重，然后你将 token 推过那些权重，接着你再去内存里提取更多的权重。但事实证明，如果你将两个 tokens 甚至五个 tokens 推送通过那些相同的权重，其花费的时间基本是相同的，因为昂贵的部分并不在于执行那些将 token 推过权重的数学运算。昂贵的部分仅仅在于从内存中读取所有的这些权重数据，所有那些参数都必须被读取进来。

那么多 token 预测的核心思想就是利用这一点，让模型一次性预测多个 tokens。假设模型预测了五个 tokens。我们知道第一个 token 是正确的。接下来的四个 tokens 可能是正确的，也可能不正确。所以接下来我们要做的就是，在下一次传递时，我们将这四个 tokens 输入到模型中进行运算，在末尾我们会进行检查。你知道模型然后会预测另一组 tokens，我们接着会去核对上一次额外预测出的 tokens 是否正确。如果正确，那么我们直接接受它们，这样我们就获得了比如 4 倍的速度提升；如果它们是不正确的，我们只接受那些正确的部分，然后从那里继续。所以这样做的好处是，它完全不会降低准确率，因为你是在利用模型进行双重检查。所有的这些推测都会在你跑下一次模型时得到检验。所以开启这项功能丝毫不会降低你的准确性。

<details>
<summary>Original English</summary>

**Speaker B**: if you're running at a low batch size um which is when you are trying to get the most interactivity if you're in a data center. So you want you want the model to respond as quickly as possible and it's okay for it to be more expensive. your token your cost per token might might be higher but you want the result as quickly as possible or if you're running um locally um so you might be running at batch size one just because you're the only person using it. It turns out that uh the GPU has extra execution capabilities that are just lying there unused. The bulk of the work when you're running in these scenarios is actually fetching the weights from memory. And then you push the token past those weights and then you fetch more more uh weights from memory. But it turns out if you if you push two tokens or even five tokens through those same um weights, it would cost basically the same amount of time because the the expensive thing is not doing the math to push the token through the weights. The expensive thing is just reading all of those weights from memory. all those parameters they have to come in. And so the idea with multi-token prediction is to take advantage of this by having the model predict multiple tokens at once. Let's say that the model predicts five tokens. We know the first token is correct. The next four tokens may or may not be correct. So then what we do is on the next pass we take those four tokens and we stick them into the model uh and then uh run it through and at the end we check you know the model then predicts another set of tokens right then we check were the extra tokens we predict last time correct. If so then we just accept them uh and then we get like a 4x speed up. um and if they were incorrect then we only accept the ones that were correct and then um you know uh uh proceed from there. So the benefit of this is it it doesn't degrade accuracy at all because you're using the model to doublech check right. So all this speculation is going to get checked uh during the next token that you you uh run through the model. So it doesn't degrade your accuracy at all to turn on

</details>

<!-- chunk 7/10 -->

### 多词元预测与加速计算 (Multi-token Prediction and Accelerated Computing)

**Nvidia Representative**: 多词元预测能够为你带来速度上的提升，而且这是一种概率性的提升，具体取决于你的预测器的接受率。所以，如果你的预测器更加准确，接受率就会变高，你就能获得更高的速度提升。对于我们最近的 Neotron 模型，我们对它的接受率感到非常自豪，但我们一直在努力让它们变得更好，一直在努力提高那个接受率。这是加速计算的一个非常好的例子。通过多词元预测，你获得的速度是模型准确率的函数。你的模型越准确，推理速度就越快，推理成本就越低。这通常不是事物运作的方式，但在这种情况下，它就是这样运作的。这意味着，如果我们作为 Nvidia 这样一家公司，试图为世界上最重要的计算工作负载提供有意义的加速，这必须是我们思考这个问题的一个重要部分。如果在推理方面（这是 2026 年最重要的计算工作负载）有可能实现 3 倍的成本降低或速度提升，并且这取决于多词元预测网络的准确率，那么这就是 Nvidia 需要非常深入理解的事情，因为它将直接影响我们的业务。

<details>
<summary>Original English</summary>

**Nvidia Representative**: Multi-token prediction, but it can give you a speed up and it's probabilistic depending on the acceptance rate of your predictor, you know. So if your predictor is more accurate, the acceptance rate goes higher, you get a higher speed up. So with our recent Neotron models, we're pretty proud of our acceptance rates, but we're always trying to make them better. Always trying to improve that acceptance rate. This is a really good example of accelerated computing. With multi-token prediction, the speed that you get is a function of the accuracy of your model. The more accurate your model is, the faster the inference is, the cheaper the inference is, the more accurate it is. That's not usually how it works, but in this case, that's how it works. And what that implies is that if we're trying as Nvidia as a company to provide meaningful acceleration to the world's most important computational workloads this has to be an important part of how we think about it. If there's a 3x cost reduction or speed improvement for inference, which is the most important computational workload of 2026, if that's on the table and it depends on the accuracy of the multi-token prediction network, then that's something that Nvidia needs to understand very deeply because it's going to affect our business directly.

</details>

### Neotron 3 的多领域在线策略蒸馏 (Multi-domain On-policy Distillation in Neotron 3)

**Interviewer**: 很有趣。继续我们刚才的话题，多层蒸馏，我们之前稍微谈到了蒸馏。这在 Neotron 3 的背景下意味着什么？

<details>
<summary>Original English</summary>

**Interviewer**: Fascinating. To continue on the tour, multi-teer distillation, we talked about distillation a little bit up front. What does that mean in the context of Neotron 3?

</details>

**Nvidia Representative**: 对于 Neotron 3 Ultra，我们在后训练阶段使用了一种叫做多领域在线策略蒸馏（multi-domain on-policy distillation，简称 MOPD）的技术。这包含的意思是，我们有很多模型想要改进的不同方面。例如，科学理解不同于数学定理证明，数学定理证明不同于编程，而编程又不同于智能体工具的交互。对于 Neotron 3，我想我们大概有 10 到 15 个这样的教师模型。其理念是，你采用这些教师模型，并将它们在某个特定领域的能力推向极致。所以，你不需要担心让它在所有方面都表现出色，只需让它在某一个领域变得极其聪明即可。然后，你拥有了这些模型的集合，你想要创建一个学会擅长所有事情的单一模型。我们使用了一种特定的强化学习技术来实现这一点，这也是当今很多实验室都在使用的，叫做 MOPD。这种方法的好处在于，因为是教师模型在进行监督，它们可以向学生模型提供非常密集的奖励。基本上每个词元都在接受监督，因此学生模型可以学得非常快，然后变得几乎和所有的教师模型在所有方面一样好。这种方法的一个好处是，它真的能帮助团队更好地协同工作。如果没有这样的技术，假设你有 500 个人在努力让一个模型变得更好，一个团队说：“我想让它在这个方面变得更好”，另一个团队说：“我想让它在那个方面变得更好”，这可能会演变成一场拉锯战，就像是：“到底谁赢？”。如果你必须做出选择，比如：“我要优先考虑这个而不是那个”，那么你就会让另一个团队觉得他们的工作无关紧要。这真的很难。在 2026 年构建人工智能的挑战之一，就是你必须弄清楚如何让人们协同工作，即使归根结底你们只是在构建同一个东西。因此，这项特定的技术在帮助更多人协同工作以使 Neotron 变得更强大方面发挥了极其重要的作用。

<details>
<summary>Original English</summary>

**Nvidia Representative**: So with Neotron 3 ultra we did postraining using something called multi-domain on policy distillation and what that entails is that we have many different aspects of the model we want to improve. For example science understanding is different from math theorem proving which is different from coding which is different from agent harness interactions right. With Neotron 3 I think we had about 10 or 15 of these teachers and so the idea is that you take these teacher models and you push them as far as you can go on some specific domain. So you just don't worry about making it good at everything just make it really really smart at this one domain. Then you have a collection of these models and you want to create one model that learns to be good at everything. And we do that using a specific reinforcement learning technique that a lot of labs these days use called MOPD. And the good thing about this is that because the teachers are supervising they can give really dense rewards to the student model. Basically every token is getting supervised and so the student can learn really quickly and then become almost as good as all of the teachers at all of the things. So one benefit of this is that it really helps the team work together better. If you don't have a technique like this and you have let's say 500 people working to try to make a model better and one team's like well I'm trying to make it better at this thing and then another team's like I'm trying to make it better at that thing there can be a tug-of-war where it's like well who wins. And if you have to make a choice like oh I'm going to choose to prioritize this one over that one then you make the other team feel like their work doesn't matter. It's just really hard. One of the challenges of building AI in 2026 is that you have to figure out how to get the people to work together even though you're only building one thing at the end of the day. And so this particular technology has been really instrumental in helping more people work together to make Neotron stronger.

</details>

**Interviewer**: 很有趣。所以，这不仅仅是一个技术问题，同样也是一个人力组织问题。

<details>
<summary>Original English</summary>

**Interviewer**: Fascinating. So it's just as much a technology question as a human organization question.

</details>

**Nvidia Representative**: 完全正确。

<details>
<summary>Original English</summary>

**Nvidia Representative**: Exactly.

</details>

### 数据来源与合成数据 (Data Sources and Synthetic Data)

**Interviewer**: 好的。太棒了。让我们先在这个话题上做个标记，稍后我们会回过头来，因为你刚刚提到的后训练，这在各个层面上都是一个令人着迷的话题。你们在 Neotron 的背景下做的一件令人兴奋的事情，就是发布了数据，也就是训练数据。那是否包括用于特定强化学习任务的特定行业数据呢？

<details>
<summary>Original English</summary>

**Interviewer**: Okay. Fantastic. Let's put a pin in this and get back to this in a second because it's a fascinating topic in terms of the post training that you just alluded to. One of the exciting things that you all did in the context of Neotron is also to publish the data, the training data. Does that include per industry data for specific reinforcement learning tasks?

</details>

**Nvidia Representative**: 是的。

<details>
<summary>Original English</summary>

**Nvidia Representative**: Yes,

</details>

**Interviewer**: 这就是今天这样对话的美妙之处，你们确实可以谈论这些事情。那么，人们是从哪里获取用于后训练强化学习工作的数据的呢？显然，当今世界的一个关键问题是，大型语言模型（LLM）或人工智能系统已经在编程和数学方面变得非常出色了，下一个大问题是，它们能否在法律、咨询以及各种不同的领域变得同样出色？而闭源模型黑盒的一部分就在于，人们是如何进行所有这些工作的？他们从哪里获取数据？在您可以讨论这一切的范围内，我非常好奇你们是如何着手处理这个问题的。

<details>
<summary>Original English</summary>

**Interviewer**: That's the beauty of a conversation like this today where you guys can actually talk about those things. So where does one get the data from for post-training reinforcement learning focused efforts? Right obviously one of the key questions in the world today is that LLMs or AI systems have become great at coding and great at math. Like the next big question is can they become great at law and consulting and then all sort of different domains. And part of the black box of closed models is like how people go about doing all of this? Where did they get the data from? To the extent that you can talk about all of this, I'd be very curious about how you guys have gone about it.

</details>

**Nvidia Representative**: 这不是一个容易回答的问题，因为它相当复杂。但我可以说，我们依赖于许多方面。一是我们确实会从一些正在构建可购买数据集的公司那里购买数据。并且在只要我们有权重新分发或公开该数据的范围内，我们也会将其作为 Neotron 数据工作的一部分进行公开。你知道，对于 Neotron，我们正在努力尽可能地开放我们发布的数据，因为我们的目标是支持整个生态系统。我们的目标不是成为市面上唯一的模型。当我们听说行业内的其他模型在使用我们的数据集来使他们的人工智能变得更强时，我们感到非常高兴，因为这意味着我们成功地完成了保持生态系统繁荣和发展的工作。此外，我们也是合成数据生成的坚定支持者。我们使用了大量的计算资源，在我们自己的系统上运行语言模型来创建合成数据，这些数据随后有助于我们的模型在解决特定领域的问题时变得更好，并且我们也发布了大量这类数据。当然，做到这一点并不那么简单明了，因为就像人们常说的，人工智能总是“垃圾进，垃圾出”。所以，你必须非常努力地确保你创建的任何合成数据都能真正增加价值，能够真正帮助模型更智能地泛化和解决问题。这些是我们构建数据集的主要途径。

<details>
<summary>Original English</summary>

**Nvidia Representative**: It's not an easy question to answer because it is quite complex. But I would say we rely on a number of things. One is that we do purchase data from companies that are building data sets that you can purchase. And to the extent that we have the rights to redistribute or to open up that data we do as part of our Neotron data effort. With Neotron, we are trying to be maximally open with the data that we release because our goal is to support the ecosystem, right? Our goal is not to be the only model out there. And we love it when we hear of other models around the industry that are using our data sets to make their AI stronger because that means we're succeeding at our job to keep the ecosystem thriving and growing. Now we also are big believers in synthetic data generation. We use an enormous amount of compute running language models on our own systems to create synthetic data that then helps our models be better at solving problems in specific domains and we release a lot of that data as well. Now it's of course not very straightforward to do this. AI is always garbage in garbage out. So you have to work really hard to make sure that any synthetic data that you create is actually adding value, that's actually helping the model generalize and solve problems more intelligently. But those are the primary ways that we go about building our data sets.

</details>

### AI 的泛化与强化学习环境 (AI Generalization and RL Environments)

**Interviewer**: 既然我们在讨论各个领域的后训练和强化学习，我很想听听您对我们未来在泛化方面发展方向的看法。顺着我刚才所说的话往下讲，整个行业似乎正在从编程和数学（这些是具有可验证奖励的领域）向各个不同的行业进军。您是否认为这就是事物发展的方向？并且，您认为整个行业是否有能力像覆盖编程或数学那样，高效地覆盖接下来的几个领域？

<details>
<summary>Original English</summary>

**Interviewer**: Since we're talking about post training and RL in different domains, just curious to get your thoughts on where we go from here in terms of generalization. So just to build on what I was saying a second ago, like the industry seems to be marching from coding and math which are domains with verifiable rewards to different industries. Do you think that this is where things are going and that the industry as a whole is going to be able to cover those next few domains as efficiently as coding or math?

</details>

**Nvidia Representative**: 编程真的非常特别，因为这是一项极具智力色彩的活动，创造了大量的经济价值，这也意味着我们拥有海量的词元可以从中学习，同时也有相关的工具能够让我们验证模型是否真正在解决问题。所以，编程在我们的心目中将永远占据着特殊的地位，并且我认为人工智能将继续在这个领域变得更好，因为我们与它之间有着这种特殊的关系。至于其他领域，我想让我感到兴奋的，是为人工智能在强化学习期间提供更加多样化的学习环境。我相信，强化学习是教导人工智能如何解决问题的一种如此通用的形式。而我们在弄清楚如何应用它方面才刚刚起步。我认为，随着我们的环境变得越来越复杂，人工智能随后会对它试图解决的问题，以及它可以采取的行动的影响学到更多的理解。然后，它就能在解决这些问题时变得更好。

<details>
<summary>Original English</summary>

**Nvidia Representative**: Coding is really special because it's a very intellectual exercise that created a lot of economic value which then meant that we had an enormous amount of tokens that we could learn from as well as tooling that allows us to verify whether our models are actually solving problems. So coding is always going to have a special place in our heart and something that I think AI is going to continue to get much better at because we have this special relationship with it. With regards to other domains I think what I'm excited about has to do with significantly more diverse environments for AI to learn in during reinforcement learning. I believe that reinforcement learning is such a general form of teaching an AI how to solve problems. We're just getting started at figuring out how to apply that. And I think as our environments get more sophisticated, the AI then learns more understanding of the problems that it's trying to solve as well as the implications of the actions that it can take. Then it becomes much better at at

</details>

<!-- chunk 8/10 -->

### 解决问题的环境将变得更为复杂

**Speaker A**: 实际上，在解决这些问题时，当我审视我们今天正在使用的环境，综合考虑各方面因素，它们仍然相当简单。而且我认为，在接下来的几年里，这些环境将变得极其复杂和多样化。

<details>
<summary>Original English</summary>

**Speaker A**: actually um solving those problems. When I look at the the uh environments that we're using today, they're still uh fairly simple um all things considered. And I think um uh that's going to become significantly more complex and diverse over the next few years.

</details>

### 英伟达的研究组织结构

**Speaker B**: 好的。你刚才提到了让500人协同工作，我之前说过我们会回到这个话题，因为这非常有趣。所以，让我们退一步讲，能跟我们说说英伟达的研究组织是怎样的吗？它是如何构建的？它究竟是如何运转的？

<details>
<summary>Original English</summary>

**Speaker B**: All right. So you mentioned uh you know making 500 people work together and I I said we would get back to it because it's so interesting. So just uh taking a step back like tell us about the research organization at uh Nvidia like how is it structured? How how does it all work?

</details>

**Speaker A**: 嗯，英伟达并不是根据组织架构图来构建的。我们确实有一张架构图，但这实际上并不是了解我们工作方式的最佳途径。比如，我的团队其实并不属于官方的英伟达研究团队。我的团队实际上是构建GPU的那个组织的一部分。而且，我的团队也并非唯一在构建Nemotron的团队。公司里大约有10个团队深度参与了Nemotron的构建。他们在公司的不同部门，在企业级软件部门，在我们的AI软件部门。英伟达实际负责设计GPU的部门也深度参与了Nemotron的构建。所以，有非常多不同的团队必须协同工作。我们总是喜欢说，使命才是老板，而不是组织。但这意味着人们必须弄清楚如何协同工作。这其实很有挑战性，因为人类天生是部落化的生物，我们很难自然而然地对不太了解或不信任的人友好，或者与那些过去没有成功合作经验的同事共事。而Nemotron这个名字实际上就反映了这一点。我们有负责构建AI软件的Nemo团队，以及主要专注于大型语言模型系统研究的Megatron团队。我们决定合作，然后开始将我们的项目称为Nemotron，这也反映了这些团队之间的这种合作。从那以后，Nemotron急剧扩张。有更多的团队加入了这项工作。

在英伟达内部以这种开放的方式来构建它非常重要。我们在邀请全公司的志愿者来帮忙构建英伟达的AI。我们认为这对公司的未来非常重要，随着这一愿景的不断发展，越来越多的人想要加入。这棒极了。我们对此感到非常兴奋，而这也意味着我们必须弄清楚如何组织工作，以便每个人都有机会做出贡献、感受到被倾听，并觉得他们的想法在通向产生影响力的道路上得到了公平的评估。我们有一套正式的流程来做这件事。我们有一个内部网站，人们可以在上面分享想法，然后这些想法会被分配给负责构建Nemotron各个部分的25位不同的负责人之一。他们会与这些想法互动。其中一些想法会得到进一步的开发。而另一些想法则会被推迟，直到我们下一次去构建新模型时再考虑。但我们正试图以一种开放和包容的方式来构建Nemotron，以便我们真的能够作为一个公司齐心协力地构建它。我认为，能够弄清楚如何协作构建AI的组织将会取得成功。而那些在“谁拥有AI”的控制权上纠结的组织，往往会浪费大量的精力。所以，英伟达的成功和Nemotron的成功，我认为与我们的协作能力成正比，这是我非常看重的一点。

<details>
<summary>Original English</summary>

**Speaker A**: Well uh Nvidia is not structured according to an org chart. um we have one but it's not actually the best way of understanding how we work. Um uh my team for example is not part of the official NVIDIA research team. My team is actually part of the organization that builds the GPU and my team is not the only team building Neotron. There's probably 10 teams around the company that have significant involvement in building emotron um in different parts of the company in in enterprise software um in uh uh our AI software um uh division the part of uh Nvidia that actually designs the GPU also significantly is involved in in building Neotron. Um so there's there's so many different teams that that have to work together. Um we um always like to say that the mission is the boss um rather than uh the organization. But um what that implies is uh that people have to figure out how to work together um which is challenging um in the sense that humans are naturally tribal creatures and it's uh not natural for us to um be friendly with people we don't know very well or trust uh co-workers that we don't have you know success working with in the past. And um you know uh actually the name Neimotron uh reflects that. We had um the Nemo team which was building software for AI and the Megatron team which was building uh primarily focused on systems research for um uh for building large language models and um you know we decided to work together and then start calling our projects Neimotron reflecting you know sort of the um uh the collaboration between these teams. Since then, Neimocron has has dramatically expanded. There's so many more teams that are part of the effort. 

Um, and it's really important um that we have structured it uh in this open way inside of Nvidia. Um, you know, we are inviting uh volunteers from around the company to come help build NVIDIA's AI. Uh, we think it's very important to the future of the company and, you know, as that vision continues to develop, more and more people want to join. That's fantastic. We're really excited about that and it means that we then have to figure out uh how to organize the work so that everybody has a chance to contribute and feel heard and feel like their ideas um are are uh you know fairly evaluated um on the on the path towards impact. Um uh we we have a a formal process for doing that. We have an internal website where people um share ideas and then those ideas um are assigned to um one of 25 different um leads that are uh you know over various parts of building Neotron. Um they interact with those ideas. Some of those ideas get further developed. Um some of those ideas get deferred until you know the next uh the next time we we go around building a new model. Um but we're trying to build Neotron in an open and inclusive way um uh so that u you know we can really come together as a company to build it. I think um you know organizations that figure out how to collaborate to build AI succeed. Organizations that struggle with control over who owns the AI tend to uh waste a lot of effort. Um and so Nvidia's success and Nematron success I think is directly proportional to our ability to collaborate something that I care deeply about.

</details>

### 算力资源的分配机制

**Speaker B**: 太棒了。但你之前提到过，尽管你在 GPU 领域无可争议的第一领导者工作，作为研究组织，你们也没有世界上你们想要的那么多 GPU。所以，GPU 和算力的分配是如何进行的？它是基于一个想法有多大的前景，还是基于早期的成功？你们是基于成功来分配或收回 GPU 吗？

<details>
<summary>Original English</summary>

**Speaker B**: Fantastic. But you you mentioned uh earlier that um despite the fact that you work at the you know number one undisputed leader in in GPUs you all as a research organization don't have all the GPUs that that you would want in the world. So like how does the allocation of GPUs and compute uh happen? And is that based on how promising an idea is or early success? Do you give GPUs, withdraw GPUs based on success?

</details>

**Speaker A**: 这是一个非常复杂的问题，弄清楚如何分配算力对行业内的所有人来说，显然都是一个难题。在 Nemotron 内部，我们有一个预算。在 Nemotron 内部，我们会根据我们认为的项目需求来分配算力。我们有一个层级结构。我们有一系列的计划，在每一个计划下，我们又有一系列的项目，他们各自会提出自己的需求。然后，我们有一个为期两周的周期，在这期间我们会审查各种需求，同时也会审查预算，随后我们以一种层级化的方式做出决策，算力也就是这样被决定下来的。

话虽如此，我认为我们在这一点上还可以做得更好。当我们做出关于算力分配的决策时很难，因为每一个研究人员都确信，只要给他们的想法分配一千倍的 GPU，他们的想法就能改变世界，对吧？而且他们可能也是对的，那可能是真的。然而，我们也是在极限下运行。我们没有多余一千倍的 GPU 可以分给我们的每一个想法。我们必须在现有的限制内运作。所以，这是一个充满挑战的过程。我们试图将尽可能多的人的视角纳入其中，以便它能尽可能地成为一种共同的理解——或许不一定是完全赞同。所以，可能有时候某个项目觉得它确实应该获得更多的 GPU，因为那会带来非常大的影响，但它并没有得到。在那种情况下，我们希望他们能够理解，为什么另一个项目获得了更多的 GPU，以及为什么在公司的这一特定分配周期里，那个项目被视为更优先的事项。这样人们至少能理解我们现有的分配是有原因的。话虽如此，这个过程一直在改进。要让这个过程变得更透明、更公平，总是有更多的工作要做。而且，当然，我的首要目标就是去获得更多的 GPU，这样我们也能资助更多的事情，因为我也想那么做。

<details>
<summary>Original English</summary>

**Speaker A**: It's a really complicated question and it's it's obviously a a difficult problem for everyone in the industry to figure out how to allocate their their compute. Um uh inside Neotron uh you know so we we have a budget uh for Neotron. Um and inside Neotron we allocate compute based on what we think the needs of the project are. We have a um a hierarchy. So we had a we have a set of programs and and in inside of each program we had have a set of projects and each of them put forward their requests. Um and then you know we have a two-week cycle where we review requests and we review the budget and then we make decisions um in kind of a hierarchical way and then um you know uh compute gets decided that way. 

Um now having said that um this is something that I think we can still do better at. Um uh it's hard when we're making decisions about compute allocation because um every researcher is convinced that their idea uh could change the world if it just got a thousand times more GPUs attached to it, right? And they they might be right. It might actually be true. And yet we're running at the limit. We don't have a thousandx more GPUs for every idea that that we have. We we have to operate within uh the limits that that we have. And so it is um a challenging process. We try to incorporate as many people's um perspectives into that as possible so that it's as much as possible a shared sense of uh understanding maybe not agreement. So there may be times when one project feels like it really deserved more GPUs because the impact of that would have been so high but it didn't get it. We hope in that circumstance that they have an understanding of why some other project did get more GPUs and why that was considered more of a priority during this particular allocation round um for the company. Um so that people can at least uh understand you know that there's a reason uh for the allocations that we have. Um uh having said that um you know this process is always improving. There's always more work to be done to make this more transparent and more fair. Um and and then of course u my my number one is just to get more GPUs so that um you know we can also fund more things because I would like to do that too.

</details>

### 平衡实用研究与探索性研究：自举法

**Speaker B**: 你是如何在有用的研究和伟大的探索性研究之间取得平衡的？

<details>
<summary>Original English</summary>

**Speaker B**: How do you balance useful research with great exploratory research?

</details>

**Speaker A**: 我的信念是，研究需要通过“自举（bootstrapping）”来实现。研究是一个“先有鸡还是先有蛋”的问题。情况总是这样，每个研究员都相信：“如果我能拥有更多的资源，我的想法就能改变世界。” 实际上，研究员有这种感觉很重要，因为如果你没有那种感觉，你也就不会有去做一些疯狂和新颖事情所需的信念，对吧？所以，你必须有信念。当然，你以这种信念作为起点。但随后，你如何将这种信念转化为其他人能够理解的东西，对吧？那些其他人愿意投资的东西。这就是我所说的“先有鸡还是先有蛋”的问题。因为一旦你的研究想法明显很好且具有影响力，要获得资源就容易了。但你如何在没有那些资源的情况下，让它变得明显很好且具有影响力呢，对吧？

所以，解决这种先有鸡还是先有蛋问题的方法，就是通过自举。这是一种迭代式的解决问题的方法。你先做一件小事，你得到了某种信号，表明这是一个好主意，然后你把这件事告诉别人，接着你再申请稍微多一点的资源。如果人们看到了，比如，“哦，对，那个实验结果还不错，挺吸引人的，我们可能应该在那方面多做一点。” 那你就步入正轨了。而且随着时间的推移，大量迭代，快速迭代，多次迭代，你就能通过自举，为你的想法找到重要的资源。在这个过程中，通常还能吸引更多的人加入进来，因为他们有机会看到这个想法将会改变世界，然后他们想要成为其中的一份子。

<details>
<summary>Original English</summary>

**Speaker A**: My belief is that research needs to be bootstrapped. Um it research is a chicken and egg problem. So um it is always the case that every researcher believes if I just had a lot more resources my idea would change the world. Actually, it's important that researchers feel that way because if you didn't feel that way, you wouldn't have the conviction that's required to go do something crazy and new, right? So, you have to believe um and and so of course um uh you start with that belief. Uh but then how do you translate that belief into something that other people can understand, right? That other people are willing to invest in. Um this is what I call the the chicken and egg problem, right? Because like once your research idea is obviously good and impactful, it's easy to get resources. But how do you get it to be obviously good and impactful without those resources, right? 

So so the way you solve chicken and egg problems is by bootstrapping. This is an iterative uh problem solving approach where you do something small. you get some sort of signal about this is a good idea and you tell people about that and then you ask for just a little bit more and um if people saw like oh yeah that you know that experiment turned out pretty well that's pretty intriguing we should probably do a little bit more there um then you're on track right and uh that that um over time you know iterate a lot iterate quickly iterate many times uh you can bootstrap to you know finding significant resources for your idea and also usually attracting more people um to come along with it uh on the way because they have a chance to see that this idea is going to change the world and then they want to be part of it.

</details>

**Speaker B**: 登月计划也是这样……

<details>
<summary>Original English</summary>

**Speaker B**: Is that how the moonshots at

</details>

<!-- chunk 9/10 -->

### Nvidia 的创业文化与决策机制

**Speaker A**: 多年来，无论是在人工智能还是其他领域，Nvidia 是如何发展起来的？是自下而上的——有人想出了一个好主意，还是黄仁勋（Jensen）自上而下地说“这就是我们需要做的”？

<details>
<summary>Original English</summary>

**Speaker A**: Nvidia got started as well over the years whether that's in AI or otherwise? So it was bottoms up somebody coming up with a good idea versus Jensen saying this is what we need to do.

</details>

**Speaker B**: 嗯，你知道，黄仁勋也有很多好主意。所以，公司对他的想法非常积极响应，这也同样重要。但是黄仁勋总是非常明确地说，这是一家由志愿者组成的公司。你知道，我们每个人之所以在这里，是因为我们自己的选择，我们原本可以在生活中做些别的事情，但我们选择在这里。因此，我们在做决定时，尤其是对于早期阶段的研究，往往是非常自下而上的，因为这有点像是一种邀请：“带着你最好的想法来吧。让我们弄清楚我们所有最好的想法是什么，然后我们再从那里迈出下一步。”

那么，我们有时会有对公司战略至关重要的自上而下的想法吗？当然，当然有。比如 NVFP4 预训练就是其中之一。所以，作为公司的领导层，我们决定我们要真正在 FP4 硬件上进行大量投资。现在是时候去发明一些能够成功使用它的优化算法了。所以，我们告诉团队，我们并没有对团队说：“你们必须去研究 NVFP4 预训练。”我们说的是：“这里有一个机会，我们正在进行一项重大投资，如果我们要能解决这个问题，那对我们公司将意义重大。”然后我们让对此感兴趣的人去进行研究，结果我们成功了，你知道。

所以这就是一种自下而上和自上而下的平衡。但它总是带有一种自举（bootstrapping）的感觉。即使像 NVFP4 这样具有重大战略性自上而下成分的项目，其非常错综复杂、包含许多活动部件的实际技术解决方案，也是出自研究人员自己之手。而且你知道，我的信念是，研究总是来源于研究人员自己。你不能准确地告诉研究人员该如何去解决一个问题，因为如果那样的话，这就不是研究，而是工程了。但在人工智能的世界里，我们需要解决的最重要的问题都带有这种研究成分，如果我们想要取得进展，就必须给研究人员创新的自由。

<details>
<summary>Original English</summary>

**Speaker B**: Well, you know, Jensen has lots of good ideas, too. And so, the company is very responsive to his ideas, and that's important as well. But Jensen very explicitly says all the time, this is a company of volunteers. You know, each of us is here because we choose to, we could be doing something else with our lives, but we choose to be here. And so, you know, we tend to make decisions, especially for early stage research, it tends to be very bottoms up, because, you know, it's sort of an invitation like bring your best ideas. Let's figure out, you know, what are all of our best ideas and then we'll take a step from there.

Now do we sometimes have top-down ideas that are important for the company strategy? Of course, you know, of course. NVFP4 pre-training is one of those, you know. So, we decided as leadership of the company, we're going to really invest in FP4 hardware. Now it's time to go invent some optimization algorithms that succeed in using it. And, so, we told the team, we didn't say to the team, you have to work on NVFP4 pre-training. What we said is, there's an opportunity, we're making a big investment, and if we can figure this out, it will be significant for our company. And then we let the people who are interested in that work on that and as a result we succeeded you know.

So it is a balance of like bottoms up and tops down, but it always has this bootstrapping feeling even with something like NVFP4 where there's a significant like strategic top down component, the actual technical solution which is very intricate and complex and has a lot of moving parts that came from the researchers themselves and you know that's my belief is that research always comes from the researchers themselves. You can't tell research exactly how to go solve a problem because then it wouldn't be research, it would be engineering. But in a world of AI where the most important problems we have to solve all have this research component, there needs to be freedom for researchers to innovate if we're going to make progress.

</details>

**Speaker A**: 听了你说的这一切，Nvidia 的文化似乎依然非常有创业精神，这让我感到很惊讶。它是一家非常大的公司，所以我相信肯定也存在办公室政治，你刚才也提到了部落本能，我相信这一切也都在发生。但是，特别是考虑到这家公司已经存在了这么长时间，取得了惊人的成功，而且内部员工也赚了很多钱，但它似乎仍然非常有创业精神，是自下而上驱动的，也许是唯才是举的（meritocratic），这样的理解对吗？

<details>
<summary>Original English</summary>

**Speaker A**: Listening to everything you're saying, I'm struck by how entrepreneurial the culture at Nvidia still seems to be. So like it's a very large company so I'm sure there's also politics and you mentioned the tribal instincts like I'm sure all of this is happening but especially given you know how long the company's been around a phenomenal success the fact that people have been making a lot of money internally it still seems to be very entrepreneurial bottoms up driven maybe meritocratic is that the right takeaway?

</details>

**Speaker B**: 是的，我的意思是，Nvidia 有一件非常不同寻常的事情，那就是其领导层的任期。黄仁勋执掌公司已经 33 年了，但他并不是孤身一人。公司里还有很多其他非常资深的高管，他们在那里工作了三十年甚至更长时间。包括我的老板在内，这些人记得在一家非常小的 NVIDIA 工作是什么感觉，他们也知道在一家非常大的 NVIDIA 工作是什么感觉。他们对公司有一种共同的主人翁意识。

你知道，Nvidia 是一个我们经常说“没有一个人会孤独地失败”的地方，而这句话的意义在于，这只是在陈述一个事实，对吧。你在一家公司工作，这是一个整体的公司，你们要么一起成功，要么一起失败。你在加速计算领域工作，而加速计算是成千上万种技术的组合。如果其中任何一项未能提供加速，那么整个价值就被破坏了。如果编译器很糟糕，那么芯片再好也无济于事。归根结底，你卖给那些试图构建 AI 未来的研究人员的是时间和能力。如果他们没有得到这些，那么到底是晶体管、数学单元、编译器、库、网络还是沿途其他任何东西未能达到预期，这都不重要了。整个组合就失败了，整个价值就被破坏了。因此，我们在 NVIDIA 在文化层面对此有着深刻的理解，这也是激励我们一起工作方式的动力。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah I mean one thing that's very unusual about Nvidia is the tenure of its leadership. Jensen Huang has been running the company for 33 years, but he's not alone. There are a lot of other very senior leaders in the company who have been there for three decades or longer. Including my boss and these people remember what it feels like to work at a very small NVIDIA and they know what it feels like to work at a very large NVIDIA. They have a shared sense of ownership for the company. 

You know Nvidia is a place we often say no one fails alone and the point of that, that's just a statement of fact right. You work at a company it's a one company you all succeed together you all fail together. You work in accelerated computing, accelerated computing is the composition of thousands of technologies. If any of them fail to deliver acceleration the value is destroyed. It doesn't matter whether the chip is great if the compiler sucks. At the end of the day the thing that you're selling is time and capability to researchers that are trying to build the future of AI. And if they don't get that, it doesn't matter whether it was the transistor or the math unit or the compiler or the library or the networking or anything else along the way that failed to live up to its expectations. The whole thing in composition fails, the whole value is destroyed. And so we have a deep understanding of that culturally at NVIDIA and it is something that motivates the way that we work together.

</details>

### 关于智能的多面性与人类的未来

**Speaker A**: 也许在结束谈话时，我想把视角拉远一点，从你这样极度深入了解所有这一切的人的角度，听听你对未来发展方向的看法。可能谁也不知道几年后会怎样，但我不知道在未来一两年内，也许会有一些可见性。我在某个地方读到过，你并不一定是一个非常相信“奇点”（singularity）那种理论的人。这样说准确吗？

<details>
<summary>Original English</summary>

**Speaker A**: Maybe to close the conversation, I'd love to zoom out, get your take from, you know, the perspective of somebody who's like as deep into all of this as it gets about where things may be going. So like who knows in a few years, but I don't know in the next year or two maybe there's some visibility. I read somewhere that you're not necessarily a big singularity kind of a person. Is that fair?

</details>

**Speaker B**: 准确。

<details>
<summary>Original English</summary>

**Speaker B**: True.

</details>

**Speaker A**: 为什么会这样呢？

<details>
<summary>Original English</summary>

**Speaker A**: And what why is that?

</details>

**Speaker B**: 嗯，我认为智能实在是太多面化了。你知道，我经常思考这样一个问题：如果一家公司要寻找它的下一任 CEO，它会通过寻找获得国际数学奥林匹克竞赛冠军的人来找到下一任 CEO 吗？可能不会，对吧？尽管对人们来说这令人难以置信，像我即使在任何方面也永远无法在国际数学奥林匹克竞赛中竞争，那些人非常了不起，对吧？他们拥有令人难以置信的才华。但这并不是经营一家公司所需要的那种才华。

如果我们看看我们文化中其他非常重要的方面。例如，音乐家。成为一名成功的热门音乐家需要什么样的智能？不要以为这全凭运气。不是的。这些人在努力工作，而且他们在某些方面非常聪明，这种聪明可能是我这个拥有博士学位的人所无法理解的，对吧？我可能没有那种智能。

所以当我思考智能时，我认为它实在是太多面化、太依赖语境了。你知道，它真的取决于具体情况。这不仅仅是关于原始的智力。原始的智力有点像引擎的马力，但是一个没有轮子的引擎运转起来是哪儿也去不了的，对吧？所以智能的影响在很大程度上与智能所处的环境、驾驭它的马具、平台有关。

所以当我考虑到这一点时，我认为，你知道，“奇点”虽然是一个诱人的想法，但我认为这确实是一个错误的想法，因为它并没有真正将这些其他因素考虑在内。所以我相信人工智能将继续以极快的速度发展。它将为我们世界经济各个方面的人们，为从事各种工作的人们解锁重大的能力。我对它将带来的机遇感到非常兴奋。

我也对我们将如何管理这一过渡感到一点担忧。所以我确实认为过渡对人类总体来说是困难的。比如我们通常是保守的。而且，你知道，将会发生很多改变。这是我们在思考方式、工作方式以及学习方式上发生的一场深刻的变革。

最终，我对我们人类弄清楚这一切的能力有信心。你知道，我们过去也做到过。这就是我们的本质。我们制造工具。我们制造外部器官来帮助我们解决问题。你知道，我们有一个外部的胃。我们称之为厨房。它为我们创造了巨大的价值。我们可以吃一些没有厨房就无法食用的东西。现在，我们正在创造一个外部的大脑。你知道，外部的胃对我们这个物种的影响是相当深远的。它们导致了农业的出现，进而导致了有组织的社会以及我们城市建立的方式。所以我们思考一下一个外部大脑的影响是什么，相当深远。实际上没有人真正知道。但我真正相信的是，人类拥有解决问题、学习以及以造福我们的方式整合新技术的强大力量。

我也相信，我们作为一颗行星所面临的问题，都需要更多的智能。每一个问题都是如此。无论是存在的不平等，还是气候变化，或者是，你……

<details>
<summary>Original English</summary>

**Speaker B**: Well, I think that intelligence is just so incredibly multifaceted. You know, I always think about this question like if a company were to be looking for its next CEO, would it find the next CEO by looking for somebody who won the International Math Olympiad? Probably not, right? Even though like it's incredible for people like I could never even compete in any way at the International Math Olympiad and those people are amazing, right? They have just incredible brilliance. That's not the right kind of brilliance to run a company. 

If we look for example at other aspects of our culture that are really important. For example, musicians. What kind of intelligence does it take to become a hit musician? Don't assume that it's all luck. It's not. These people are working hard and they're very smart in ways that I might not understand with my PhD, right? I might not have that kind of intelligence. 

And so when I think about intelligence, I think it's just so multifaceted and so contextual. You know, it really depends on the situation. It's not just about raw intelligence. Raw intelligence is kind of like the horsepower of an engine, but an engine running without wheels doesn't go anywhere, right? So the impact of intelligence has a lot to do with the context that the intelligence is put in the harness, the platform. 

And so when I think about that, I think you know the singularity is although it's an attractive idea, I think that it's really a wrongheaded idea because it doesn't really take into account these other factors. So I believe that artificial intelligence is going to continue to develop at a rapid pace. It's going to unlock significant capabilities for people in every aspect of our world economy, people doing every kind of work. I'm very excited about the opportunities that it's going to bring. 

I am also a little bit concerned with how we're going to manage the transition. So I do think that transitions are hard for humans in general. Like we're conservative generally. And you know there is going to be a lot of change. This is a profound change in the way that we think and the way that we work, the way that we learn. 

Ultimately I have faith in our ability as humans to figure it out. You know we've done it in the past. This is who we are. We build tools. We build external organs that help us solve problems. You know we have an external stomach. We call it kitchen. It creates enormous value for us. We can eat things that we couldn't eat without a kitchen. Right now we're creating an external brain. You know the implications of the external stomach were pretty profound for us as a species. They led to agriculture which led to organized societies the way our cities are built. So we think about what is the implications of an external brain pretty profound. Nobody actually really knows. But what I do believe in is the power of humanity to solve problems and to learn and to incorporate new technologies in ways that benefit us. 

I also believe that the problems we face as a planet all require more intelligence. Every single one of them. Whether that's inequality or climate change or you...

</details>

<!-- chunk 10/10 -->

### AI作为解决人类结构性问题的工具

**Brian**: 至于我们面临的其他那些我认为非常令人担忧的结构性问题，解决这些问题将需要创造力和智力。对我而言，这意味着我们未来真正能创造出的唯一工具就是人工智能（AI）。因为我们面临的问题都与智力有关。无论采用何种技术途径来解决这些问题，其解决方案最终都将被称作AI。这让我对未来充满希望，但同时也对它将给我们带来的挑战保持敬畏——毕竟我们要试图弄清楚如何与这个全新的“外部大脑”以一种全新的方式共存。但我相信我们学习和改变的能力。我也相信，最终这将使我们的生活变得更美好。

<details>
<summary>Original English</summary>

**Brian**: know any of the other structural problems that I think are very worrisome that we face. The solutions to those are going to require invention and intelligence. And what that means for me is that the only kinds of tools that we can really create moving forward are going to be AI. Because the problems that we face are all about intelligence. And regardless of the technological approach to solving those problems, the solutions will always be called AI. And so that makes me hopeful for the future but also you know somewhat respectful of the challenge that it is going to bring to us as we try to figure out how to live in a new way with this new external brain. But I believe in our ability to learn and to change. And I think ultimately this is going to make our lives better.

</details>

### 公众对AI的接受度与经验

**Matt Turk**: 你们是否感觉到行业内部似乎正在形成一种对AI的抵触情绪？这是你们能感知到或思考过的问题吗？如果是的话，你认为这可能是我们这个行业在沟通上存在的问题吗？特别是考虑到你刚才提到的AI那些显而易见的巨大潜力。

<details>
<summary>Original English</summary>

**Matt Turk**: Do you guys feel the AI backlash that seems to be forming internally? Is that something that you all perceive think about? And if so, do you think it's a communication problem that our industry may have? You know, in particular, given what you just said about all the obvious potential of AI,

</details>

**Brian**: 我一直很担心公众看待和接触技术的方式，这非常重要。不可否认的是，渴望技术进步的社会总是比抗拒改变的社会拥有更多的技术进步。所以我认为思考这个问题确实很重要。关于AI，有一点很有趣：我相信当它融入日常生活时，往往会更容易被接受。到了那个时候，人们就不再把它当成“AI”来看待了，而只是觉得“哦，这是我使用的一个工具”。比如，当你使用地图应用导航开车去某个地方时，你会介意那是AI在帮你规划路线吗？我的意思是，那背后确实有非常复杂的AI在起作用，但你其实并没有在意这一点，对吧？你只是在使用一个工具。所以我认为，人们对AI的接受度是随着经验的积累而来的。我们使用它的经验越多，我们越懂得如何高效地利用它工作，我认为我们就会对它越感到自在。

<details>
<summary>Original English</summary>

**Brian**: you know, I'm always worried about the way that the public thinks about technology and interacts with it. It matters a lot. And it is definitely the case that societies that want technological advancement have more technological advancement than societies that don't want change. So I think it is actually important to think about it. One thing that's interesting about AI is that I believe it tends to be much more accepted when it is part of everyday life and then at that point people stop thinking about it as AI. It's just, oh, this is the tool that I use. Like, do you care whether it's AI that's helping you route your car when you ask the map application to help you drive somewhere? Like, I mean, there is actually sophisticated AI that's going into that. But you're not really thinking about that, right? You're just using a tool. And so I feel like people's acceptance of AI comes with experience, right? The more experience we have working with it, the more we learn how to work with it productively, I think the more comfortable we become with it.

</details>

### AI安全问题：开源与闭源的争论

**Matt Turk**: 太棒了，Brian。这真是一次引人入胜的对话。作为确保我们涵盖这一主题的最后一个问题，我想谈谈安全问题。目前的安全性处于什么状态？在今天的安全话题探讨中，开源和闭源各自处于什么位置？

<details>
<summary>Original English</summary>

**Matt Turk**: Great, Brian. So, it's been a fascinating conversation. Maybe as a very last question to make sure we cover it, I want to make sure that we talk about safety. What is the state of safety currently? And where does open source and closed source sort of fit in the safety conversation today?

</details>

**Brian**: 安全问题现在是每个人都在关注的焦点。你看 Fable 的发布，以及政府对其采取的应对方式，我认为这就是对这些模型安全性担忧的结果。它们变得越来越强大，也可能被滥用。目前对于如何思考和定义安全性有不同的方法。我对此可能有一个略显非主流的观点，那就是：我认为开放的技术通常更安全，因为它们暴露在更多的阳光下。当有更多的人在思考一项技术的安全性、评估它并为使其更安全做出贡献时，我认为这本质上比让一小群人负责所有人的安全要安全得多。

我也认为，因为人工智能本质上是关于思想的——关于以不同方式探索思想——所以在这种情况下，多样性比单一文化更安全。这意味着会出现不同的信念。多样性不仅仅是关于那些容易达成共识的事情，它更是关于那些艰难的事情。比如当人们有着深刻的意见分歧、彼此完全不认同时。我认为，让人们能够以多元的方式探索他们的想法，比试图创建一个“围墙花园”（在这个花园里，某些想法被认为是安全的，而另一些则是不安全的）要安全得多。

这种观点在当今的AI环境中存在争议，我觉得这很有意思，因为我们有数百年的传统直接回应了这一点。比如在美国，我们有关于良心自由和言论自由的法律。我们之所以有这些法律，并不是因为我们几千年来没有考虑过“如果没有它们，社会会不会更安全”，对吧？我们尝试过。我们确实尝试过建立一种单一文化，规定“这些想法是可以安全谈论的，这些想法是可以安全信仰的”。但我们发现，那远不如一种多元主义安全。在多元主义下，我们官方不对哪些思想是安全的预设立场。我们实际上发现，作为一个社会，支持多样性比试图自上而下地保持每个人的安全要安全得多。因此，我相信开放的AI技术本质上是构建AI最安全的方式。

<details>
<summary>Original English</summary>

**Brian**: Safety is on everybody's minds right now. You know watching the Fable release and the way that the government interacted with that I think is a consequence of concerns about safety about these models. You know, they get stronger and stronger and then they could be misused. And you know, there's different approaches to thinking about safety and trying to define safety. I have maybe a slightly unorthodox opinion about this, which is that I think open technologies are generally safer because there's more sunlight. You know, when more people are thinking about the safety of a technology and evaluating it and then contributing to making it safer, I think that's inherently safer than having a small group of people being in charge of safety for everyone else.

I also think with artificial intelligence because it is really about ideas. It's really about exploring ideas in different ways. That diversity is more safe than monoculture. And what that means is that there's going to be different beliefs. Like diversity isn't just about the easy stuff. Diversity is about the hard stuff. Like when people have deeply felt disagreements, they really really totally disagree with each other. Making it possible for people to explore their ideas in a diverse way I think is more safe than trying to create a walled garden where you know certain ideas are considered safe and certain ideas are considered unsafe.

And you know this is controversial in today's AI environment which I think is interesting because we've had hundreds of years of tradition that speak directly to this. You know, in the United States, for example, we have laws about freedom of conscience and freedom of speech. And you know, it's not because we didn't consider for thousands of years would it have been safer if we didn't have those, right? We tried that. We actually tried having a monoculture about like these ideas are safe to talk about, these ideas are safe to believe. And we found that to be much less safe than a pluralism where we officially don't take a position about what ideas are safe. We actually found that is much safer as a society to support diversity than it is to try to keep everybody safe top down. And so I believe that open technologies for AI are inherently the safest way of building AI.

</details>

### 结尾致辞

**Matt Turk**: 好的。我很喜欢这个观点。用一个充满争议的观点来结束这次对话。Brian，这真的太棒了。非常感谢你。很感激你今天能花时间接受我们的采访。

<details>
<summary>Original English</summary>

**Matt Turk**: All right. Love it. Controversial take to close the conversation. Brian, it's been fabulous. Thank you so much. Really appreciate your spending time with us today.

</details>

**Brian**: 感谢你的邀请。

<details>
<summary>Original English</summary>

**Brian**: Thanks for inviting me.

</details>

**Matt Turk**: 大家好，我是 Matt Turk。感谢收听这一期的 MAD Podcast。如果你喜欢这期节目，如果你还没有订阅的话，我们非常希望你能订阅，或者在你观看或收听本节目的平台上留下好评或评论。这能切实帮助我们建设播客，并邀请到更多优秀的嘉宾。感谢，我们下期节目再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks and see you on the next episode.

</details>