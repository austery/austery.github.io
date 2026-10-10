---
author: Latent Space
date: '2026-04-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rv23_KcHt4s
speaker: Latent Space
tags:
  - physical-ai
  - autonomous-vehicles
  - simulation-testing
  - operating-systems
  - hardware-software-integration
title: 150亿美元的物理AI公司：Applied Intuition的模拟、OS与神经网络模型
summary: 本访谈深入探讨了Applied Intuition如何构建物理AI以赋能自动驾驶、工程机械和国防等领域。公司专注于模拟、操作系统和AI模型开发，强调在安全关键环境中部署智能的重要性。讨论涵盖了AI工具在工程中的应用、人才招聘新趋势、以及如何通过创新实现技术的高效落地与验证。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Peter Lewig
  - Kaser Younes
companies_orgs:
  - Applied Intuition
  - Google
  - NVIDIA
  - Tesla
  - Waymo
  - Apple
  - General Motors
products_models:
  - Android
  - iOS
  - CUDA
  - Gemma
  - Euro NCAP
media_books: []
status: evergreen
---
### 物理AI的系统挑战

**主持人**: 今天的物理机器更像是Android和iOS诞生前的手机市场。Google的拉里之所以决定进入Android领域，部分原因在于他们希望在多款手机上运行Google产品。他们从行业内购买了所有这些手机，结果发现这些手机上运行着大约50种不同的操作系统，Google几乎不可能在所有50种设备上都能让他们的应用运行得同样好。因此，解决方案是，如果他们能创造一个真正优秀的操作系统，并让所有手机制造商都对其感兴趣呢？这就是Android的起源，也是Android存在的原因。它是Google将其产品推向各种设备的一种方式。目前的物理产业状况也有些类似，操作系统种类繁多，高度碎片化。要让现代AI应用在这些车辆上运行，首先需要整合操作系统。这就是我们这样做的原因。

<details>
<summary>Original English</summary>

**Host**: Physical machines today are more akin to the state of the phone market before Android and iOS existed. Part of the reason that that Larry at Google decided to get into Android was they they wanted to run Google products on a bunch of phones and they they bought all of these phones from the industry and it turned out they had like 50 different operating systems on these phones and it was virtually impossible for for Google to to make their app run on all 50 devices equally well. And so the solution was well actually what if what if they created a really great operating system and and made it attractive to all of these phone makers. And that was sort of the genesis for what Android was and and why Android existed. It was a way for Google to get their products onto really wide diversity of devices. The state of of the physical uh industry right now. It's a little bit like that. So many different operating systems. It's so fragmented. And to actually get a modern AI application to run on these vehicles, you actually you first have to consolidate the operating system. And so that's that's why we've done that.

</details>

**主持人**: 在我们开始今天的节目之前，我只想给听众们说一句小小的寄语。谢谢大家。如果没有大家选择点击并收听我们的内容，我们将无法为您带来您如此明确想要的AI工程、科学和娱乐内容。我们几乎每天都会收到赞助商的联系。但幸运的是，有足够多的人订阅我们，使我们能够在没有广告的情况下维持所有这些。我们希望保持这种方式。但我只想请大家帮一个忙。您能做的最强大、完全免费的事情就是点击订阅按钮。这是我唯一会要求您的事情。它对我以及我的团队来说意味着一切，他们每周都努力为您带来**Inspace**。如果您这么做了，我保证我们将永不停止努力，让节目变得更好。现在，让我们开始吧。

<details>
<summary>Original English</summary>

**Host**: Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis. But fortunately, enough of you actually subscribe to us to keep all this sustainable without ads. And we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you. And it means absolutely everything to me and my team that works so hard to bring the Inspace to you each and every week. If you do it, I promise you we'll never stop working to make the show even better. Now, let's get into it.

</details>

**主持人**: 大家好，欢迎收听**L in Space**播客。我是**Colonel Apps**的创始人**Alessio**，和我在一起的是**L in Space**的编辑**Swixs**。我们非常荣幸能邀请到**Applied Intuition**的创始人**Kasar**和**Peter**。欢迎。

<details>
<summary>Original English</summary>

**Host**: Hey everyone, welcome to the L in Space podcast. This is Allesio, founder of Colonel Apps, and I'm joined by Swixs, editor of L in Space. We're very honored to have uh the founders of Applied Intuition, uh Kasar and Peter. Welcome.

</details>

**Swixs**: 你们真知道怎么切换到播客模式。这…这…呃，你们真是这方面的行家。他们之前还在开玩笑，然后很快就切换过来了。

<details>
<summary>Original English</summary>

**Swixs**: You guys really know how to turn it on to podcast mode. That was that was uh I you guys are real real pros at this. They were just joking around right before this and then they flipped it pretty quick.

</details>

**主持人**: 是的，很高兴能邀请到你们。也许你们可以先介绍一下自己，这样大家就能知道麦克风后面是谁的声音了。

<details>
<summary>Original English</summary>

**Host**: Yeah, it's great to have you guys. Maybe you just want to introduce yourself so people know the voice on the mic and

</details>

**Peter Lewig**: 大家好，我是**Peter Lewig**。我是**Applied Intuition**的联合创始人兼**CTO**。

<details>
<summary>Original English</summary>

**Peter Lewig**: table. Yeah, I'm Peter Lewig. I'm the co-founder and CTO of Applied Intuition.

</details>

**Kasar Younes**: 我的名字是**Kasar Younes**。我是**Peter**的首席执行官兼联合创始人。

<details>
<summary>Original English</summary>

**Kasar Younes**: And uh my name is Casser Ununas. I am the CEO and co-founder with Peter.

</details>

### Applied Intuition：物理AI的全球领导者

**主持人**: 很好。你们能简要介绍一下**Applied Intuition**是做什么的吗？我读过**Peter**你参加国会会议的一些文件，全球20家非中国顶级汽车制造商中有18家在使用你们的产品。你们在农业、国防、建筑领域都有客户。我想大多数人可能听说过**Applied Intuition**与**YC**初创时期相关，然后你们隐身了很长一段时间。所以，也许你们可以先给大家一个关于公司现状的总体概述，然后我们再深入探讨各个方面。

<details>
<summary>Original English</summary>

**Host**: Nice. Can you guys give the high level overview of what applied intuition is and I I was reading through some of the Congress files uh when you went out there Peter and 18 of the top 20 global non-Chinese automakers use you guys. You have customers in agriculture, defense, construction. I think most people have heard of apply intuition tied to YC when it was first started and then you were kind of in stealth for a long time. So maybe just give people the high level overview of what it is today and then we'll dive into the different pieces.

</details>

**Peter Lewig**: 是的，**Applied Intuition**的使命是构建物理AI，以创造一个更安全、更繁荣的世界。我们致力于为各种移动系统提供物理AI，涵盖从汽车到卡车、建筑和采矿设备，再到国防技术的一切。我们是一家真正的技术公司。我们构建并销售技术，将其出售给制造机器的公司，以及政府。任何希望购买技术来使机器变得智能的人，我们都可以提供。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. So applied intuition our mission is to build physical AI for a safer more prosperous world. And so we work on physical AI for all different types of moving systems everything from cars to trucks to construction and mining equipment uh to defense technologies. And uh and we're a true technology company. So we we build and sell the technology and we sell it to the companies that make the machines. We we sell it to to the government. Uh really anyone that wants to to buy a technology to make machines smart.

</details>

**Kasar Younes**: 是的，我认为在更广阔的AI领域，过去三年里，很多关注点理所当然地都集中在大型语言模型上，因此所有适配屏幕的东西，比如代码补全产品等等。而我们不同之处在于，我们正在将智能部署到许多没有屏幕的设备上。它们是物理机器。车厢内有时会有屏幕，例如汽车或卡车的车厢。但我们提供的大部分价值在于将智能置于**安全关键环境**中。这两个词非常重要，因为学习系统可能会出错。如果你只是问一些你知道的，比如“告诉我关于这些我即将要见的播客主持人”，那当然可以。但是当你运行无人驾驶卡车时，你不能出错。例如，我们现在在日本运行L4级别的无人驾驶卡车，不能有错误。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. And I think uh in the broader AI landscape, a lot of the focus uh rightfully so in the last uh 3 years has been on large language models and so everything that fits in a screen, you know, like uh whether it's code complete products or or or things like that. Um, and what's different about us is we're deploying intelligence onto a lot of things that don't have screens. You know, they're physical machines. There are sometimes screens within the cabin or for for example of a car or a truck or something like that. But, uh, most of the value we provide is putting intelligence that is in safety critical environments. So that those two words are really important because learned systems can make mistakes if you're asking for like you know some you know something like tell me about these podcast hosts that I'm about to go meet but uh you can't do that obviously when you're you know we run like as an example we run driverless trucks in Japan right now like as we speak you can't have errors that those are L4 trucks. Yeah.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yep.

</details>

### 公司发展历程与定位

**主持人**: 这一直是公司的使命吗？我记得最初，人们将你和**Scale AI**非常相似地看待，因为它们都在数据基础设施方面。公司的发展是怎样的？

<details>
<summary>Original English</summary>

**Host**: Was that always the mission? I remember initially I think people put you and Scale AI very similarly for some things about being kind of like on the data infrastructure side of things. What was the evolution of the company?

</details>

**Peter Lewig**: 嗯，从一开始，我们就一直希望成为一家真正帮助推动工业领域发展的技术公司。所以我们最初从自动驾驶领域开始。我们最早的客户是**机器人出租车**公司，我们最初在模拟和数据基础设施方面做了很多工作。然后多年来我们扩展了我们的产品组合。现在我们有超过30种产品，在物理AI领域拥有相当广泛的技术布局。

<details>
<summary>Original English</summary>

**Peter Lewig**: Well, from the very beginning we we always wanted to uh really be a technology company that uh that helped generally push forward the industrial sector. And so we started off working in autonomy. Our very first customers were robo taxi companies and and we started off doing a lot of work in simulation and and data infrastructure. And then over the years we've expanded our portfolios. Now we have over 30 products and it's a pretty broad technology play within the the landscape of physical AI.

</details>

**Kasar Younes**: 是的，我认为与**Scale AI**相似的原因是因为我们都是**YC**生态系统中的公司。但实际上，**Scale AI**是一家非常不同的公司，它更像是一家服务公司，本质上是数据标注公司。而我们从一开始到现在，都做了大量的**工具开发**。所以，如果你认为开发者工具现在又流行起来，这要感谢AI的繁荣。但老实说，十年前，它就不流行了。在2016年、2017年做一家工具公司并不是一件时髦的事情，因为VC们普遍认为工具只是工作流，而工作流最终并不是那么有趣。我们现在又回到了这个循环。但当我们创办公司时，我们的初衷是：我们希望将软件部署到物理机器上，比如汽车和卡车上。当然，我们那时不知道**Transformer**的繁荣会发生，也不知道自动驾驶系统会变得**端到端**。这些我们都不知道。自动驾驶系统实现端到端的重要性在于，现在这些模型可以推广到多种**形态因素**。所以，9、10年前，工具是一种很好的方式，现在仍然是一种很好的方式，可以构建技术并将其出售给我们的客户，他们中的很多人都希望自己构建这些东西。因此，我们提供了一系列解决方案，从只使用开发工具套件的一部分，到购买完整的解决方案。思考公司的方式，或者至少我们思考公司的方式，正如**Peter**所说，我们是一家技术提供商。这有点像**NVIDIA**或**AMD**所做的事情，但我们不做芯片，不做硅片，但我们本质上是技术提供商。我认为，我们甚至开玩笑说，当我们创办公司时，我们知道我们不是那种会构建**Instagram**的人，那根本不是我们最根本的特质。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, I think the the scale reason is because we're all YC universe companies, you know, and so uh but it was a very very different company, you know, Scale was is more of a services company, data labeling company fundamentally. We started and still are uh you know do a lot of tooling. So like you think you know developer tooling is now in vogue again thanks to thank thanks to you know thanks to the AI boom but honestly 10 years ago it was out of vogue like doing a tooling company in 2016 2017 was not like the thing to do because I don't know if you remember that the VCs generally their views was that tooling are just workflows and workflows ultimately are not really interesting uh and we've kind of come you know full full circle of that but when we started the company our our kind You know, it's kind of like in the periphery of what the company wants to be in was like from our earliest days like we want to deploy software on physical machines like on cars and on trucks and things like that. Now obviously we didn't know that the transformer boom was going to happen and we didn't know that autonomy systems would become end to end. Those things we didn't know and why that's important with autonomy system end it is just now you can those models can be generalized to you know multiple form factors. And so back 9 10 years ago tooling was a great way and still is a great way to you know build the technology and sell technology to our and customers a lot of them who want to build the stuff themselves. And so we just offer like a spectrum of solutions from you can just use like one part of of a development suite of tools all the way to buying the full thing. The way to think about the company or at least the way we think about the company is as Peter said a technology provider. It's kind of like uh you know what Nvidia does or what an AMD but we just don't do chips. We don't do silicon but we're a technology provider fundamentally and I think even you know we used to joke when we started the company like you know we're not the guys to build like Instagram like that was just not our that's just not us in a most fundamental way. I mean

</details>

**主持人**: 你有什么想法吗？

<details>
<summary>Original English</summary>

**Host**: you have thoughts.

</details>

**Peter Lewig**: 是的。嗯，我的意思是，这就像，我们曾从事地图和**Google地图**等消费者产品的工作，这些产品出于各种原因极其困难。它只是，我认为它无法解决那个痛点。我认为我们更像是密歇根人，更倾向于传统的工程领域或血统。我刚说的话，**Joe**，我得说，十年前很清楚的是，

<details>
<summary>Original English</summary>

**Peter Lewig**: Yes. Well, it's it's I mean I think it's just like what and and and I mean we worked on maps and stuff Google maps consumer products are extremely difficult for a lot of different reasons. It just I think doesn't scratch the itch. I think we're like Michigan guys who are kind of more in that traditional engineering kind of a realm uh or lineage. I you said Joe I got to say that what was clear 10 years ago was that

</details>

**Kasar Younes**: 软件和AI在车辆上还有很大的潜力。我们十年前就是从这个领域开始的。多年来我们所走的精确道路，我认为我们一直很有战略眼光，并不断调整，以确保我们实际构建的东西对市场有价值。技术变化如此之快，我们自己的**技术栈**大约每两年就会完全改变一次。所以现在我们可能已经完成了大约四次技术栈的完整演进。我看到这种节奏大致会保持下去，所以我们思考工程的方式几乎是以两年为周期来准备自己：嘿，我们希望投入适当的资源，但同时也要非常灵活，随着研究成果的发布和我们研究团队发现新的进展而进行调整。

<details>
<summary>Original English</summary>

**Kasar Younes**: there was so much more that was possible with software and AI and vehicles and that was generally the space that we started in 10 years ago and the precise path that we've taken over the years I think we've been strategic and we we've adjusted to make sure that we're actually building stuff that's valuable to the market and like the technology has changed so much like our own technology stack has has completely changed I would say roughly every two years and so now we've probably done let's say four complete evolutions of our own techn technology stack and I sort of see that cadence roughly keeping up and and so the way even we think about engineering is almost on this 2-year horizon we're preparing ourselves that hey like we want to invest the appropriate amount but then also be very dynamic as the research gets published and as our research team figures out new advancements and adapting to that.

</details>

**Peter Lewig**: 是的，有一点始终保持不变，那就是我们招聘的人才类型。坦率地说，我们招聘的工程师有时会从事非常传统的**Google**套件工作。但与您知道的其他公司不同的是，我们招聘的人员真正了解硬件和软件的交叉点，了解系统，当然还有传统的**ML**研究人员，以及那些真正将**ML**系统投入生产的人。这方面一直相当一致。我认为，看看我们工程团队的构成，公司83%的人都是工程人员。所以，这是一个庞大的工程师团队。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, one thing that has been consistent is the type of people we've recruited. Frankly speaking it's engineers who are fall into the you know sometimes very traditional like you know Google gen suite um but way different from you know other companies we are hiring folks who really know the intersection of hardware and software who know systems obviously traditional ML researchers and folks who uh actually you know put ML systems into production that's been pretty consistent I I think that like you look at the mix of our engineering 83% of the company is engineering. So it's like a giantly a small lot of engineers

</details>

**主持人**: 顺便说一句，一千名工程师，我想这在你们的网站上，所以我想它是最新的。

<details>
<summary>Original English</summary>

**Host**: which by the way a thousand engineers I mean that's on your website so I imagine it's up to date.

</details>

**Peter Lewig**: 是的，是最新的。

<details>
<summary>Original English</summary>

**Peter Lewig**: It is it is up to date. Yes.

</details>

**主持人**: 好的。那还有40多位创始人呢？

<details>
<summary>Original English</summary>

**Host**: Okay. And then 40 plus founders.

</details>

**Kasar Younes**: 是的。这更多是运气而非策略。但我们招聘了很多前创始人。对于YC和其他创始人来说，这里一直是一个很好的地方，因为我认识很多YC的人。这就像我们招聘很多Google员工，让他们同时运用技术和非技术技能，因为我们专注于应用端。我们有一个研究团队，进行基础研究，并发布成果，我们在这方面取得了很好的进展。但从根本上说，业务希望将这种智能投入生产，并且有一种特定类型的人对此更感兴趣。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. You would also uh this was more luck than than strategy. Um but we've recruited a lot of exfounders. It's been a great place for founders YC and non because obviously I know a lot of the YC folks. It's kind of like we recruit a lot of Google people for for them to exercise both their technical and non-technical skills because you know we're we're we're on the applied side. We have a research team that we do fundamental research. We publish and we we've had great traction there. But fundamentally the business wants to take this intelligence and deploy it into production and and there's like a certain type of person that's more interested in that.

</details>

### 技术栈与核心能力

**主持人**: 是的，**Peter**你提到了**技术栈**。我想让你深入谈谈。我感兴趣的是**Applied Intuition**的边界在哪里，也就是说，你们不做什么？你们在所有垂直领域都有哪些共同点？

<details>
<summary>Original English</summary>

**Host**: Yeah. You mentioned the tech stack, Peter. Uh so I just wanted to give you some rain to just go into it. I'm interested in where applied nutrition uh starts and ends in in in some sense. What won't you do? What uh do you do that's common among all the verticals that you cover?

</details>

**Peter Lewig**: 我们所做的工作分为几个方面，我们已经在这方面努力了近十年。所以这项技术非常广泛。但我们最初是从

<details>
<summary>Original English</summary>

**Peter Lewig**: There's a few buckets of of work that we do and we've been at this for almost 10 years now. So the technology is pretty broad. But uh we got started

</details>

**主持人**: 有一千名工程师，你可以做很多事情。是的。尤其现在有了AI工具。是的。

<details>
<summary>Original English</summary>

**Host**: with a thousand engineers like you can work on lots of stuff. Yeah. Especially with AI tools now. Yeah.

</details>

**Peter Lewig**: 我们从**模拟**和**模拟工具**及**基础设施**开始。通常，如果你想构建一个涉及移动机器的非常复杂的软件系统，你需要对其进行测试。最好的测试方法是结合**虚拟开发**，即模拟，当然还有**真实世界测试**。然后，模拟结果与真实世界结果之间需要一个非常仔细的关联过程，以确保模拟器确实准确。模拟是一个非常深入的话题。我们在这方面有一整套产品，我们可以就此深入探讨很多很多小时。但这是我们公司工作的一部分。

<details>
<summary>Original English</summary>

**Peter Lewig**: So we got our start in in simulation and simulation tooling and infrastructure. And so generally if you're trying to build a very complex software system that involves moving machines, you need to test that. And the best way to test it is it's a combination of virtual developments. So simulation and then also obviously real world testing and then there's a very careful process of that correlation between the simulation results and the real world results and ensuring that the simulator is in fact accurate to that. Simulation is a a very deep topic. We have a whole whole suite of products in that and and we could talk for many many hours about that specifically. Um but that that is one part of what we do as a company.

</details>

**Peter Lewig**: **强化学习**作为其中的一个子部分也至关重要。我认为现在许多AI系统中最好的进展在某种程度上都与强化学习有关，而现在我们拥有大量的计算能力，你可以用强化学习做很多有趣的事情。我们工作的第二个方面是**操作系统技术**。一个真正的操作系统，想想调度器、内存管理、中间件、消息传递，以及高度可靠的网络和数据链路，现实是如果你想在车辆上部署AI，你需要一个真正好的操作系统。当我们深入这个领域时，我们并没有找到我们满意的东西。当然，市面上确实存在一些东西，我们当时也正在使用这些可用的东西。但作为一家工程组织，我们大致意识到这些东西并不好。我们认为我们可以做得更好。所以，我们决定构建一些东西。这就是启动我们操作系统业务的灵感时刻，现在它对我们来说是一个非常真实的业务。为了编写和运行优秀的AI，你需要一个优秀的操作系统。这就是我们进入这个领域的原因。然后我们工作的第三个方面是真正的**基础AI技术模型**。我们做了很多基础研究工作，但也做了**世界模型**，即实际运行在这些物理机器上的**自动驾驶模型**，涵盖汽车、卡车、采矿、建筑、农业和国防领域。所以，这包括陆海空。

<details>
<summary>Original English</summary>

**Peter Lewig**: Reinforcement learning as a sub part of that is also super critical. I think a lot of the a lot of the best advancements happening in in a lot of these AI systems right now in some way relate to reinforcement learning and with now we have lots of compute and you can do tons of interesting things reinforcement learning. The second bucket of work that we do is on operating systems technology. a true operating systems like think about uh schedulers and and memory management and uh and middleware and message passing and uh highly reliable networking and data links like the reality is if you want to deploy AI onto vehicles you need a really good operating system and when when we were getting deeper into that space there wasn't really anything that we were happy with like things existed absolutely and we were using what was available in the market and as an engineering organization, we roughly realized these things aren't great. We think we can do this better. And so let's let's build something. And that was then the that was the the moment of inspiration that started our operating systems business, which is now a very real business for us. And in order to write and run great AI, you need a great operating system. And so that that's what got us into that. And then the third bucket that we work on, it's it's true fundamental AI technology models. We do a lot of work in as mentioned the foundational research but then the also the uh the world models the actual autonomy models that are running on uh on these physical machines as that's across cars, trucks, mining, construction, agriculture and and defense and uh and so that's both land uh air and and sea

</details>

**Kasar Younes**: 此外，第三个领域中一个较小的子部分是人类与这些机器的交互。所以，这是一种**多模态**体验。历史上，如果你移动一台泥土运输机或任何这类机器，都有按钮可按，无论是实际的物理触觉按钮还是触摸屏。但这种交互方式正在发生根本性改变，你只需与机器对话，机器就会与你协同工作。

<details>
<summary>Original English</summary>

**Kasar Younes**: and also uh a smaller subsect of that third bucket is the interaction of humans with those machines. So, uh, that's a multimodal, uh, experience. Historically, if you're moving a dirt mover or any of these machines, there are like, you know, buttons you press, whether they're actual physical tactile buttons or or something like a touchcreen. That's just that fundamentally is changing to where you're just talking to the machine and the machine and you're teaming with the machine.

</details>

**主持人**: 语音。

<details>
<summary>Original English</summary>

**Host**: Voice.

</details>

**Kasar Younes**: 是的。语音。绝对是。是的。而且机器还会感知驾驶舱里的人是谁，他们的状态如何。嗯，你可以从安全系统的角度思考。最简单的例子是驾驶员疲劳，对吗？当你开车时收到那些提醒，也许是让你去喝杯咖啡休息一下，这需要将这种概念的量级放大。但这种**人机协同**的概念很重要。当你想到运行代理或运行为你处理后台工作的Claude等不同实例时，你可以将这种类比几乎复制粘贴到一个农场中，农场主在操作许多机器，他们与机器互动的地方可能是需要做出关键决策或脱离操作的地方。但总的来说，物理机器上的代理正在运行并代表农场主做出决策，直到出现一些可能很关键的事情。这也是我们正在努力的。所以这不是纯粹的**自动驾驶**。它有点混合，但属于汽车领域的自动驾驶范畴。根据**SAPE**级别，这通常被定义为**L2++系统**。我们有人类参与其中，但你可以将这个概念推广到其他垂直领域。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. Voice. Absolutely. Yeah. And also the machine just being aware of who's in the cabin, what their state is. Um, you can think from a safety systems perspective. The most simple version of this is like the driver is tired, right? They're there. You know, if you get those alerts when you're driving your cars and maybe take a coffee break, that take that times, you know, a couple of order of magnitudes up. But this concept of teaming man and machine is important. when you think about running agents or just running you know different instances of uh you know claude and doing work for you in the background you you can take that analogy I almost copy and paste and put it into like a farm where you have a farmer who's running a number of machines so where they interact with the machine is where there's maybe a critical decision or a disengagement or something but generally speaking the agent on the physical machine is running and making decisions on the behalf of the farmer until there's something maybe you critical and that that that's also what we work on. So that's not pure autonomy. It's a little bit of a mix, but it falls under uh autonomy in the automotive sense. That's typically defined in SAPE levels as an L2++ system. We have a human in the loop, but just take that idea, you know, to to other verticals.

</details>

### 硬件与操作系统：协同设计与演进

**主持人**: 是的。你完全没有提到硬件，比如传感器，或者，你知道，你提到了你们不做芯片。我认为即使在自动驾驶汽车领域，也有像摄像头与**激光雷达**这样的大争论。在你们的领域，你们做出了哪些设计决策？这些决策是否受**原始设备制造商（OEM）**在机器上安装设备的能力驱动？你们在共同设计这些方面有多少影响力？

<details>
<summary>Original English</summary>

**Host**: Yeah. You've not mentioned hardware at all like sensors or, you know, obviously we you mentioned you don't do chips. I think even in AV there's like a big uh you know cameras versus lightars like what what are like in your space maybe some of those design decisions that you made and are they driven by the OEM's ability to put things on the machinery like how much influence do you guys have on co-designing those?

</details>

**Peter Lewig**: 是的。我们不做传感器，我们不是制造商。当然，我们的自动驾驶产品中使用了大量的传感器。至于实际安装在车辆上的东西，我们有一套首选的传感器，可以说我们完全支持这些传感器，然后我们的客户可以从中选择。如果他们对支持其他传感器有非常强烈的意见，我们也会将其添加到平台中。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. So so we don't make sensors like we're not a manufacturer obviously we use a lot of sensors in our autonomy products. Um, in terms of what actually goes on the vehicles, we have a preferred set of sensors that that we uh, let's say fully support and then our customers, they can sort of choose from those and obviously if there's a a very strong opinion on supporting something else, we we'll add that to the platform as well.

</details>

**Kasar Younes**: 至于**激光雷达**问题，在自动驾驶领域，这在目前来说是个老生常谈的话题。目前行业的现状是，激光雷达无疑是一个有用的传感器。尤其是在自动驾驶研发阶段进行**数据收集**时。例如，如果你看到一辆**特斯拉**研发车辆，直到今天它仍然安装有激光雷达。在湾区，我们看到像**Model Y**或**Cyber Cav**这样的车辆，它们都装有激光雷达在路上行驶。所以它很有用，因为它提供了**每像素深度信息**。如果你能将激光雷达与摄像头配对，并且你能说这个摄像头正在观察这个方向，这个激光雷达正在观察这个方向，那么现在对于摄像头的每个像素，我都可以看到这个像素有多远。然后你可以将其作为模型训练的一部分，然后深度信息就会成为摄像头数据的学习状态。然后当你进行生产系统时，你就可以移除激光雷达，现在你就可以只用摄像头获得深度信息了。所以，像高传感器配置的研发车辆与成本降低的量产车辆之间的差异，我们将其应用于我们所有的产品组合中。当然，最终目标是希望成本超低、超可靠。然后，在某些使用案例中，你会有一些更定制化的东西，例如在国防领域，你经常在夜间行动，所以你更关心像**红外线**这样的传感器，而不是，你不需要发出能量，所以你不想使用激光雷达或雷达，但你仍然需要在夜间看到东西。所以是的，我们涵盖了整个范围。

<details>
<summary>Original English</summary>

**Kasar Younes**: And the the LAR question is at this point sort of the age-old uh, topic in in autonomy. And the the state of the industry right now is LAR is hands down a useful sensor. Uh specifically for data collection and the R&D phase of autonomy development. Um if you see for example a a Tesla R&D vehicle, it actually has LAR on it to this day. Right in the Bay Area, we see these uh you'll see like Model Y's or Cyber Cav that have have lighters on them just driving around. So it's it's useful because it gives you per pixel depth information. So if you can pair a LAR with a camera and you can say that well this camera is looking this direction, this lighter is looking this direction and now for each each pixel of the camera I can see how far away is that pixel. Um you can actually then use that as a part of your model training and then the that depth information then becomes a learned uh a learned state of the camera data and then when when you're doing the production system you can now remove the LAR and and now you can actually get depth with just the camera. And so that that difference between like a highly sensored R&D vehicle and then the downcosted production vehicle, we use that across our whole portfolio of products. Um and of course the end goal is you want super low cost and super reliable and uh and then in certain use cases you have some more bespoke things like in in defense as an example you do things at night often times and so you care about sensors like infrared uh more so than and you don't you don't want to be putting energy out so you don't want to use LAR or radar but you still need to be able to see at night time. So yeah, we we work the whole gamut.

</details>

**主持人**: 酷。所以那是硬件层面。那么**OS**层面呢？它看起来是怎样的？有什么独特之处？我的意思是，我开**特斯拉**。每当我开其他有屏幕的汽车时，总是很糟糕。那就像是个廉价的**Android平板**，卡顿得很。那么**自动驾驶**未来的**OS**会是什么样子？

<details>
<summary>Original English</summary>

**Host**: Cool. So that's kind of like on the hardware level. Then on the OS level, how does that look like? What is like unique? I mean, my drive I drive a Tesla. Whenever I drive some other car that has a screen, it always sucks. It's some like cheap Android tablet is like it's laggy and all of that. What does the OS of like the autonomy future look like?

</details>

**Peter Lewig**: 当大多数人，嗯，就像你刚才描述的那样。当你想到车辆中的**操作系统**时，你想到的是**人机界面（HMI）**，对吗？人机界面。当然，它是其中一个重要部分，但它实际上只是最上面的一薄层。所以当我们谈论车辆中AI的操作系统时，有很多层深入到**安全关键领域**和**嵌入式系统**中。你谈论的是对电动马达或发动机和执行器的实时控制，你会有不同的冗余来应对不同的情况，例如车辆的转向执行，所有这些都需要操作系统中的核心支持。然后当然，对于自动驾驶，你有实时传感器数据流，延迟在那里非常重要。如果你想象你试图运行**Microsoft Windows**来传输传感器数据或控制车辆，延迟会非常荒谬，你永远做不到。所以我们所做的事情的特殊之处在于我们真正拥有这种**系统级思维**。我们关注整个系统的每一个性能特征。然后，因为我们做了大部分软件或所有软件，我们可以微调和控制所有这些东西。所以我们可以非常非常仔细地调整系统各个方面的延迟。我们可以仔细调整内存管理。我们可以为不同的事情设置正确的**故障保护**和**回退机制**，因为你必须考虑如果发生关键故障怎么办。如果宇宙射线导致处理器中的某个比特翻转从而导致某些故障怎么办？你必须有针对所有这些的故障保护。所以核心操作系统是其中的一部分。然后，嗯，最后一个，虽然不那么令人兴奋但实际上是一个非常重要的话题，那就是**更新的可靠性**。

<details>
<summary>Original English</summary>

**Peter Lewig**: When most people uh it's sort of like what you just described. When you think about operating system in a vehicle, you're thinking about the HMI, right? The human machine interface. And absolutely that's a an important part of it but that's actually only one thin layer on top. Um, so when we talk about operating systems for AI in vehicles, there's many many layers that go deep into the safety critical realm and embedded systems and you're talking about the the real-time control of let's say the electric motors or the the engine and the actuators and you have different redundancies for uh for different let's say the steering actuation in the vehicle and all of these things uh need very core support in the in the operating system. And then of course for autonomy you have real-time sensor data that's streaming in and the latencies there are really important right if you try to imagine you try to run Microsoft Windows uh like streaming your sensor data in or controlling the vehicle like the latencies are going to be absurd like you can never do that and so what's special about what we do is we really have this system level thinking right so we're looking at we care about every performance characteristics of the entire system and then we also because we're doing a lot of the software or all of that software we can fine-tune and control all those things. So we can very very carefully tune in the latencies for every aspect of the system. We can carefully tune in the memory management. We can have the right uh fail safes and fallbacks uh for for different things because you have to account for what what if there is a critical failure. What if there's a cosmic ray that flips out a bit in the middle of the processor that causes some uh malfunction? Uh and you have to have a fail safe to all of that. And so the the core operating system is a part of that. And then the um the one last thing which is a lot less exciting but is actually a very big topic is reliability of updates,

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: right?

</details>

**主持人**: 呃，我有一辆**特斯拉**，你更新得很频繁，对吧，一个月一次。

<details>
<summary>Original English</summary>

**Host**: Uh so the I have a a Tesla and uh you get updates fairly frequently, right, once a month.

</details>

**Peter Lewig**: 大多数制造车辆的公司，基本上从不进行更新。即使他们进行更新，通常也只更新一个模块。也许他们正在更新**HMI模块**，但他们无法更新，比如说，系统的**安全关键部分**。你需要去经销商那里才能完成。因此，有了我们的操作系统，我们现在实际上可以对车辆中的任何系统进行高度可靠的更新。这说起来容易做起来难。有很多技术上深入的东西在**技术栈**中，可以以一种不会意外“砖化”车辆的方式做到这一点。

<details>
<summary>Original English</summary>

**Peter Lewig**: Most companies that are making vehicles, right, are basically never doing updates and they're and even if they are doing updates, they're usually only updating maybe one module. Maybe they're updating the the HMI module, but they're not able to update, let's say, the the safety critical parts of the system. you have to go into the dealer for that. And so with our operating system now, we can actually enable highly reliable updates of any system in the vehicle. And that's way easier said than done. Like there there's lots of technical technically deep stuff in the tech stack to to do that in a way that you're not going to accidentally brick a vehicle. And right if imagine you're read

</details>

**Kasar Younes**: 是的。把车“砖化”是非常昂贵的。老实说，在整个行业中，我们所做的最具影响力的事情之一，就是我们现在正在赋能整个行业实际进行**软件更新**。顺便问一下，这方面的客户是谁？我猜很多硬件制造商都有自己的固件，我敢肯定其中一些人会请你们为他们编写，因为你们是专家。而其他人则有自己的固件。这笔钱是谁出的？是谁邀请你们进入这个领域的？是最终用户还是制造商？

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. Bricking a car is a very expensive uh and honestly across the industry maybe one of the most just pure impactful things that we've done is we've just we're now enabling the industry to actually do software updates. Just to clarify as well who is the customer for this like uh I assume a lot of hardware manufacturers have their own firmware and I'm sure some of them would just have you write it for them because you're experts. Uh and others would have their own. It's like who pays for this? Who who invites you into the the house? Is it is it the end user or is it is it the manufacturer?

</details>

**Peter Lewig**: 是的。是的。首先，让我对软件的**碎片化**做一个类比。今天的物理机器更像是**Android**和**iOS**出现之前的手机市场状况。对吧？我多年前曾在**Google**从事**Android**工作。**Google**的拉里之所以决定进入**Android**领域，部分原因在于他们希望在多款手机上运行**Google**产品。他们从行业内购买了所有这些手机，结果发现这些手机上运行着大约50种不同的操作系统。**Google**几乎不可能在所有50种设备上都能让他们的应用运行得同样好。因此，解决方案是，如果他们能创造一个真正优秀的操作系统，并让所有手机制造商都对其感兴趣呢？这就是**Android**的起源，也是**Android**存在的原因。它是**Google**将其产品推向各种设备的一种方式。目前的物理产业状况也有些类似。是的，这些公司有固件，但他们有太多不同的操作系统。它非常碎片化。要让现代AI应用在这些车辆上运行，首先需要整合操作系统。这就是我们这样做的原因。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Yeah. So let me make an analogy firstly on the on the fragmentation of software. So physical machines today are more akin to the state of the phone market before Android and iOS existed. Right? So uh I worked on Android at Google by the way many many years ago. And uh and part of the the reason that that Larry at Google decided to get into Android was they they wanted to run Google products on a bunch of phones and they they bought all of these phones from the industry. And it turned out they had like 50 different operating systems on these phones. And it was virtually impossible for for Google to to make their app run on all 50 devices equally well. And so the solution was well actually what if what if they created a really great operating system and and made it attractive to all of these phone makers. And that was sort of the genesis for what Android was and and why Android existed. It was a way for Google to get their products onto really wide diversity of devices. The state of of the physical uh industry right now, it's a little bit like that. Like there's yes, these companies have firmware, but they they have so many different operating systems. It's so fragmented. And to actually get a modern AI application to run on these vehicles, you actually you first have to consolidate the operating system. And so that's that's why we've done that.

</details>

**Peter Lewig**: 然后，呃，你具体的问题是我们的客户是谁？通常是制造这些机器的公司。我们向他们销售我们的技术，以真正简化架构，然后使这些应用能够在它们上面运行。在多少程度上可以重复使用？你们有一个适用于所有设备的操作系统，还是需要一些定制？

<details>
<summary>Original English</summary>

**Peter Lewig**: And then uh your specific question was who are our customers? It's it's generally it's the companies that are making these machines. And you know, we're we're we're selling our technology to them to really simplify the architecture and then enable these applications to run on them. How much is reusable across like do you have like one OS that is just configured for everything or is there some more customization that it's needed?

</details>

**Peter Lewig**: 是的，**高度可重用**。所以，嗯，基本技术是相当通用的。然而，我们必须考虑芯片组支持等问题。因此，如果你在编写，比如说，一个**LLM**，你假设“嘿，我要使用**CUDA**，我要在**NVIDIA**芯片上运行”，那么你就不必考虑这方面的硬件。你只是说，“好的，我只在**CUDA NVIDIA**生态系统中，我将使用它。”但硬件，尤其是在**安全关键系统**中，它要多样化得多。不是只有一两个参与者。我们必须支持大量的不同芯片组。所以我们的操作系统不仅仅运行在**x86**的同等物上。它必须运行在来自许多不同公司的各种架构芯片上。但同样，我们已经为此努力了很长时间。所以我们支持所有这些芯片组。然后，当你想要运行AI应用程序时，我们现在可以跨各种提供商可靠地做到这一点。我认为这在很大程度上受到了**Android**的启发。**Android**拥有庞大的测试套件，它是一个可靠的操作系统，可以在数千种设备上运行。我们认为我们可以在所有这些物理移动机器上做到同样的事情，不同之处在于我们真正处于**安全关键领域**。**Android**不是。所以，在**Android**上我不需要使用**Gmail**。我可以使用**Superhuman**，那么你们的机器呢？人们可以将其他人的自动化系统引入其中，还是它是一体化的？

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, highly reusable. So the um the the fundamental technology is is quite universal, right? So things that we do have to think about though are like chipset support. And so, um, if you're if you're coding, let's say, uh, an LLM and you have start with an assumption that, hey, oh, I'm going to I'm going to use CUDA and I'm going to run this, uh, on an NVIDIA chip, then you don't really have to think about the hardware in that sense. Like you you're just, okay, I'm just I'm in the CUDA NVIDIA ecosystem and I'm I'm going to to use that. But the the hardware, especially in safety critical systems, it it's a lot more diverse. There's not one one or two players. There's a a bunch of different chipsets that we have to support. And so our operating system doesn't just run on like the equivalent of x86. It has it has to run on a number of different architectures from chips from a bunch of different companies. U but again we've been working on this for a long time now. So we have we have support for all of those those chipsets. And then when you want to then run the a applications we can then do that reliably across now a variety of providers. And I think that is like heavily inspired by Android right? Android has a huge suite of testing and uh and it's a reliable operating system that runs on thousands of devices and you know we think we can we can do the same in in all these physical moving machines with the difference that we're really in a safety critical realm. Android isn't. So on Android I don't need to use Gmail. I can use a superhuman like what about your machinery? Like can people bring somebody else's automation to it or is it kind of like allin-one?

</details>

**Kasar Younes**: 你必须使用。我的意思是，如果，是的。是的。完全开放。是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: You have to use I mean if uh Yeah. Yeah. It's totally open. Yeah.

</details>

**Peter Lewig**: 是的，是的。我们的理念是，我们是一家技术公司，因此我们将技术授权给客户，让他们按照自己的意愿使用。所以如果客户想要，如果他们想授权我们的自动驾驶技术和我们的操作系统，那很好，我们会授权。如果他们只是想授权操作系统，然后使用不同的自动驾驶技术，那也可以。我们有很好的文档来使用开发者工具。是的，没错。是的，如果它们能一起工作，当然会更好。都是C++吗？我猜是带有不同的编译目标。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Yeah. Our our our philosophy is that we are a technology company and so we we license our technology to customers to use how they want and so if a customer wants to if they want to license our autonomy tech and our operating system then great we'll license those. If they just want to license the operating system and then use different autonomy tech that's fine also and we have great documentation to use developer tooling. Yeah exactly. Yeah, it's like a better together if obviously uh if you if they work together. Is it all C++? I I assume is with different compile targets.

</details>

**Kasar Younes**: 我们使用大量的**C++**。呃，我的意思是，**Rust**在很多方面也算是一种新的热门技术。但是的，当你深入到底层，尤其当你遇到**实时约束**时，你迟早会遇到**C++**，有时甚至可能需要用到**汇编语言**。

<details>
<summary>Original English</summary>

**Kasar Younes**: We use a lot of C++. Uh I mean Rust is is sort of a hot the new hotkit on the block for for a bunch of things as well. Uh but yeah, when when you the lower level you get especially when you when you get to realtime constraints, you hit C++ at some point and at some point maybe you work your work work your way into assembly when needed.

</details>

**主持人**: 哦，天哪。

<details>
<summary>Original English</summary>

**Host**: Oh damn.

</details>

### AI与工程实践

**主持人**: 我对**编码代理**的采纳情况很好奇，既然你提到了更多深奥的语言，那么内部的采纳情况如何？你学到了什么？

<details>
<summary>Original English</summary>

**Host**: I'm curious about the um coding agent adoption just like since you're mentioning more esoteric languages like what's the adoption internally? What have you learned?

</details>

**Kasar Younes**: 是的，我们什么都用。嗯，我的意思是，**Cursor**曾是公司一段时间内最热门的工具。我认为现在**Claude Code**已经占据了主导地位。我们有一个内部排行榜，我们用它来鼓励公司内部的采纳。是的，它们非常有用。我的意思是，老实说，我们也从这些工具中汲取灵感，思考如何将这种思维方式运用到物理领域。就像，如果为屏幕上的这个或那个东西构建应用程序如此容易，我们就可以将许多相同的想法应用到：如果想让物理机器做某事，我们如何使用我们自己的工具和平台使其变得更容易。你们是否在改变**OS架构**，比如暴露服务的方式，以使其更友好于AI？

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, we we use everything. Um I mean so Cursor was I think the the hottest tool in the company for a good while now. Claude code I think has has taken the the reign on that. We have a internal leader leaderboard that we use just to sort of encourage adoption uh with within the company and uh yeah they're phenomenally useful. I I mean it's uh honestly we we take inspiration from from some of those tools also and how we're adapting some of that mindset of thinking to the physical realm like oh if it's so easy to to build an app for this or that thing that lives just on a screen we can we we're taking out a lot of those same ideas and and applying that to okay well if you wanted a physical machine to do something how easy can we make that uh using our own tooling and platform as well. Are you changing any of like the OS architecture kind of like the way you expose services to like be more AI friendly or

</details>

**Peter Lewig**: 是的，当然。呃，在我们的工具和基础设施工作的早期阶段，很多时候，工程师都是某些主题的专家，但他们处理的事情往往更具数学性或更抽象，而**图形用户界面（GUI）工具**在某些方面确实非常有用。举个例子，我们有一个名为**Sensor Studio**的产品，它帮助你为自动驾驶车辆设计**传感器套件**，无论是汽车、无人机、采矿设备还是机器人。你将传感器放置在不同的位置，有一个库可以让你了解你在系统设计中做出的权衡。这曾经是一个非常**GUI密集型**的工作，因为它更像一个**CAD工具**。然而现在，我们暴露了所有底层API，现在使用AI代理，你只需通过文本就可以配置传感器套件，并且很可能比过去通过GUI获得更好的结果。我们现在正在将这种思维方式应用到整个产品组合中。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, absolutely. The uh in the early days of our tools and infrastructure work, it was a lot about um you had engineers that were experts in certain topics, but the things that you're dealing with, they're often times more mathematical or more abstract where actually guey tools are very very useful for certain things. As an example, we have a a product we call Sensor Studio which is uh it helps you design the sensor suite for uh for your autonomous vehicle whether again it could be a car, it could be a a drone, could be a mining mining equipment, could be a robot and and you you place sensors in different places you there's different uh there's a library you can understand what are the trade-offs that you're making in in the design of that system and that was like a very a very gooey intensive uh thing because it's a little bit more like a CAD tool in that sense. if you've seen CAD tools. Nowadays though, uh we we expose all of the underlying APIs for that and and now using uh AI agents, you can actually configure a sensor suite with just text and and likely reach a better result than you could have through the guey in the past. And we're taking that thinking now through the whole product portfolio.

</details>

**主持人**: 我还在想，就AI的采纳而言，这是否会改变你们的招聘方式，或者你们如何以不同的方式管理工程师？

<details>
<summary>Original English</summary>

**Host**: The another thing I was thinking about is just in terms of like AI uh adoption, does that change your hiring at least a little bit or how do you how do you sort of manage engineers um differently?

</details>

**Kasar Younes**: 是的，绝对会。嗯，我想，像现在谷里所有的公司一样，我们也在不断发展我们的招聘实践，因为成为高效人才所需的技能变化太快了，对吧？我的意思是，你过去常常只选择那些能够编写代码的人，而现在，更多的是**AI工程师**的技能组合，对吧？它更像是，你知道如何实现，但实际上，编写代码不再是核心工作了，对吧？它实际上是知道要问什么问题，知道如何将这些不同的AI工具组合在一起。所以我们现在进行的面试，我认为比以往任何时候都更难，但我们也允许，你知道，选择性地使用AI工具来解决问题。我认为这样一来，你会开始看到工程师的**双峰分布**，对吧？你会开始看到，哇，有一部分人，他们真正理解，他们全身心投入，他们显然投入了必要的时间来学习这些工具以及如何高效工作。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, absolutely it does. Um we I think like every company in in the valley right now are evolving our our hiring practices um because the the skills required to be effective are changing so fast, right? I mean you used to really select for just wrote implementation ability and and now it it is more the AI engineer skill set right where it's like yeah you know how to implement but actually just banging out code is is no longer the core job right it's it's actually knowing what questions to ask knowing how tie how to tie together these different AI tools and so the the interviews that we give now I think are way harder than they've ever been but but we also allow right selective use of AI tools to solve problems. And I think in that you you start to see more of a biodal distribution of engineers, right? You you start to see like, wow, there's there's this subset of of people that they they really get it like they're they're all in and they they've clearly invested the the hours needed to learn these tools and and how to be effective.

</details>

**主持人**: 然后还有一群没有做到这一点的人。生产力差距是巨大的。所以我们显然正在努力挑选那些真正投入其中的人。

<details>
<summary>Original English</summary>

**Host**: And then there's sort of the the group of people that haven't done that. And that the productivity gap is just enormous. And so we're trying to obviously select for the people that are are really really into this.

</details>

**主持人**: 我三年前第一次写我的**AI工程师**文章时，我就说过，实际上并非每个人都应该成为AI工程师，因为我认为有一种极端的观点认为，每个软件工程师都是AI工程师，而我举的例子是那些不应该采用AI的人，包括**嵌入式系统**、**操作系统**和**数据库**人员。他们现在是否正在采用AI？我认为这是一个经典的惨痛教训，嗯，六个月前我还会说同样的话，但它现在正变得对每个领域都非常有用，我敢肯定。

<details>
<summary>Original English</summary>

**Host**: I first wrote the my AI engineer piece 3 years ago and when I first wrote about it I was like actually not everyone should be an AI engineer because I think there's there's an extremist stance where well every software is an AI engineer is an AI engineer and my actual example of people who should not be adopting AI was embedded systems and operating systems and database people are they adopting AI? I think it's the classic bitter lesson uh topic which is the um six months ago I would have said the same thing but it's it's becoming super useful for every domain I'm sure right like

</details>

**Peter Lewig**: 大约六个月前，或者可能是一年前，如果你尝试使用最新的**Cloud模型**来编写**GPU着色器**，结果可能不尽如人意。但如果你现在使用最新的模型来完成这类任务，你会有点惊讶，就像“哇，这竟然真的奏效了。太棒了！”我们在嵌入式领域也看到了同样的情况。呃，毫无疑问，尤其是在进入**安全关键系统**时，**人工验证**是百分之百的关键。嗯，就像，我，你不会把自己的生命托付给未经人类非常仔细检查的AI编写的软件。所以我认为现在，呃，真正的挑战在于针对这些**安全关键系统**的适当**人工验证**水平。

<details>
<summary>Original English</summary>

**Peter Lewig**: there was uh I think 6 months ago or maybe maybe a year ago if you tried to use let's say the latest cloud model for writing shaders uh GPU shaders the results were probably underwhelming and if you use the latest model now to do that kind of task you're a little bit blown away like, "Wow, that actually worked. That's amazing." And we see the same thing in in the embedded realm. The um no question though, especially when you get into safety critical systems, the the human validation is is 100% key. Um like I I you're not going to trust your life to uh AI written software that's that's not been very carefully uh checked by humans. And so I think now the um really the challenge is about that appropriate level of of human validation for for these safety critical systems.

</details>

### 模拟、验证与统计可靠性

**主持人**: 你如何看待，是的。谈到**模拟**方面？我认为可验证的奖励和**强化学习**是最热门的事情。你们内部做了什么来围绕这个构建？以及什么让你能安心睡觉？比如，如果有人只是在编写一些VIP代码，或者想尝试一些新东西，你们有一个足够好的系统吗？因为我认为反面也成立，如果编写任何东西都超级容易，那么在可验证性方面就会增加很多工作。那对人们来说是什么样的呢？

<details>
<summary>Original English</summary>

**Host**: How do you think about Yeah. touching on the simulation side? I think verifiable reward and reinforcement learning is like the hottest thing. What have you done internally to build around that? And like what what gives you what makes you sleep at night? like if somebody's like you know just vip coding something or like wants to try something new you have like a good enough system because I think the opposite is also true is like if it's super easy to write anything then it puts a lot of work on like the verifiable yeah side of it like what does that look like for people

</details>

**Peter Lewig**: 是的，是的，所以**可验证性**是更广泛的**评估**范畴，对吧？你如何评估你得到的结果？我认为这可能是目前最困难的问题，因为随着模型越来越好，发现系统中的故障会越来越难。所以，要通过适当的评估来发现这些故障，这个问题也随着模型越来越好而变得越来越难，但它仍然和以前一样重要，对吧？仍然会有未满足的**边缘案例**等等。所以这对我们来说是一个巨大的投资领域。嗯，在**强化学习**方面，我的意思是，关键在于最新一代技术带来了所有这些新要求。例如，**端到端**是目前**自动驾驶**和**物理AI**领域的大事，这意味着你现在可以训练模型，有效地接收传感器数据，然后输出控制信号，并从中获得非常好的结果。但是你训练和改进这些模型的方式与前几代截然不同。所以，要在端到端模型上进行强化学习，你现在需要实际模拟所有传感器数据。对吧？所以这变成了我们称之为**神经模拟**的工作，但你可以把它想象成**高斯泼溅法**和**扩散方法**的混合，你真正关心性能。性能就是一切。如果你不能足够快、足够便宜地进行足够的模拟，你实际上就无法获得最终有价值的结果。这与我们许多**嵌入式系统**的工作也有关，那就像是性能关键型工作。而这种**性能优化**、**性能关键性**，它也延续到许多模型训练工作中，因为唯一能使其负担得起的方式就是它必须非常快。

<details>
<summary>Original English</summary>

**Peter Lewig**: yeah yeah so so verifiability broader bucket of like evaluations right how do you evaluate the the results that you're you're getting I think this this is probably the hardest problem right now because the as the models get better, it can be harder and harder to find the faults in the system. And so like the problem of doing proper eval to find those faults, uh like that problem also keeps getting harder as as the models get better, but it's no less important than it's ever been, right? If you still there are still going to be edge cases that are not met and and whatnot. And so it's it's a big area of investment for us. the um on the reinforcement learning topic, I mean the key thing is there's all these new requirements that that come to be in in the latest generation of of these technologies. So for example, end to end is the big thing right now in in autonomy and physical AI, which is you can now train these models that can effectively take sensor data in and then put control signals out and get really good results out of that. But the way that you train and improve those models is really different from uh from the previous generations. And so to do reinforcement learning on an endto-end model, you now need to actually simulate all the sensor data. Right? So then this becomes we we call our our work in this neural simulation, but it's think of it like a a hybrid of Gaussian splatting and and diffusion methods and uh where you really care about performance. Like performance is is everything. If you can't do enough simulation fast enough and cheap enough, you actually can't get results that are are worthwhile in the end. It also gets gets to a lot of our work in embedded systems, which is like performance critical work. And that that performance optimization, performance criticality, it carries over to a lot of the the model training work um because the only way to make it affordable is it has to be really fast.

</details>

**Kasar Younes**: 我认为花几分钟谈谈我们自己对**验证**和**确认**的不断演进的思考是值得的，这包括传统的模拟器，例如车辆动力学之类的，它们从教科书中提取公式并将其转化为软件，以实现这种神经模拟/**世界模型**的宇宙。我认为这是一个有趣的话题。

<details>
<summary>Original English</summary>

**Kasar Younes**: I think it's worth a few minutes talking about our own uh evolving thoughts on verification and validation within kind of uh traditional simulators which are you know uh you can think of like vehicle dynamics or something like that which are taking textbooks and taking those formulas and putting them into software to like now this neural sim/world model universe uh I think that's an interesting topic.

</details>

**Peter Lewig**: 是的，是的。所以，在，嗯，在更传统的开发中，你通常会对问题有更**非黑即白**的答案。例如，在欧洲，有一个监管系统叫做**Euro NCAP**，即**欧洲新车评估计划**。作为该计划的一部分，车辆必须通过一系列测试。这些测试实际上包括**安全系统**。比如，当一个孩子突然跑到汽车前面时的**自动紧急制动**，或者一个被遮挡的孩子突然跑出来并被撞到。所以你最终会得到这些二元答案，比如测试中的汽车是否通过了这项特定的测试，并且有一套非常 well-known 的测试案例，车辆必须通过这些测试。这就是，比如说，直到大约十年前，这个行业的工作方式。但现在发生的变化是，有了这些模型，一切都变成了**统计数据**，对吧？你不再有非黑即白的答案，而是，比如说，我能从系统中获得多少数量级或多少个“九”的可靠性，以及我如何证明这是真的？嗯，而且，物理AI作为一个行业，最大的突破老实说就是这些模型变得更加可靠了，对吧？事情实际上运作得好得多。现在这些系统能达到的“九”的数量已经足够好，以至于实际部署这些东西变得具有**成本效益**。因此，**验证**和**确认**的最大转变是，过去更多的是严格的**需求**以及你是否满足它们，而现在更多的是**统计验证**和**确认**，一切都围绕着可靠性有多少个“九”以及**平均故障间隔时间**。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Yeah. So, so in um in more traditional development, right, you you often times would have uh more black and white answers to questions. And so the uh in in Europe, as an example, there's a regulatory system. It's called Euro Encap. It's the European New Car Assessment Program. And as part of that, the vehicles have to pass a bunch of tests. And those those tests actually uh in include um safety systems. So, automatic emergency braking for a child that runs in front of a car uh or let's say an oluded child that runs out and and you hit it and and so you have you end up with sort of these binary answers of like well did did the car under test pass this specific test and there's a very very well-known set of of test cases that the vehicle has to pass and that was how the industry worked let's say uh until 10ish years ago but what's changed now is with these models everything is stat statist statistics, right? Like you no longer have a black and white answer, but it's like, well, how many orders of magnitude or how many nines of reliability can can I get in the system and how can I how can I prove that to be true? Um, and uh and and the big unlock honestly for physical AI as as an industry is that these models are just becoming much more reliable, right? Things like things actually work a lot better. like the number of nines you can get out of these systems are are now good enough that it actually becomes cost- effective to to really deploy these things. And so the the big shift in in so verification validation has been from a little bit more of a in the past it was strictly requirements and are you meeting or not and and now it's more of a statistical uh verification and validation case where it's all about how many nines are reliability and and meantime between failures that sort of thing.

</details>

**主持人**: 那么目标受众是**监管机构**，还是客户也有？我想客户已经认可了，主要是需要满足监管机构。

<details>
<summary>Original English</summary>

**Host**: And is the target audience regulators or even the customers are few I imagine the customers are bought in and it's mostly regulators that need to be satisfied.

</details>

**Kasar Younes**: 我们确实与**美国政府**合作。我们当然也与**欧洲政府**和**日本政府**合作。而且，政府并非像AI实验室那样。

<details>
<summary>Original English</summary>

**Kasar Younes**: We do work with the US government. We do work of course with the European governments and and the government of Japan and um the government is not like an AI lab by any means. So

</details>

**Peter Lewig**: 他们只关心结果。他们关注结果，所以我们在这方面进行教育，比如说教导他们：嘿，我们认为验证应该这样做，这是一个我们认为合理的方法，以及如何思考无人驾驶系统何时足够安全可以上路。嗯，但，呃，我不会说政府在要求这个。更像是我们正在教导政府。老实说，这更多是为了我们自己的安心，对吧？我们希望构建非常安全的系统，当然我们的客户也深切关心这一点。但在这个背景下，我们通常也在教育我们的客户。

<details>
<summary>Original English</summary>

**Peter Lewig**: they just care about the outcome. they hear about the outcome and and so we we do education uh in in that regard and like s sort of teaching about hey this is how we think validation should be done and this is an approach that that we think is is reasonable and how to think about like when is a a driverless system actually safe enough to to to go on the roads and that that sort of thing. Um but uh I wouldn't say that the government is asking for it. It's like we're more teaching the government in that in that sense. It's honestly it's more so for our own our own comfort, right? Like we want to build very safe systems and then of course our customers care deeply about that as well. But in that context we're also typically educating our customers.

</details>

**Kasar Younes**: 是的。我的意思是，我们的第一个核心价值观是**全面安全**。所以，呃，我认为我们不能过分强调，我们自己验证和确认我们部署的系统是安全的，这可能和监管机构或客户说“你知道的”一样重要。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. Our first I mean uh uh our first core value is on round safety. So uh I think we can't underline enough that uh us also verifying and validating that the systems that we're deploying are safe to to us is probably as important as like some regulator or a customer saying you know.

</details>

**主持人**: 当然。好的。是的，你们必须让自己满意。

<details>
<summary>Original English</summary>

**Host**: Of course. Okay. Yeah, you have to satisfy yourselves.

</details>

**Peter Lewig**: 是的，正如我所说，全球的法规往往只是最低标准，但你真的必须大大超越监管机构的期望才能制造出好产品。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, as I say as as a whole across the world regulation often times it's like a almost lowest common denominator but like you really have to substantially exceed what the regulators are expecting to make good products.

</details>

### 安全、事故与人机统计差异

**主持人**: 我经常谈论的一件事，我认为我试图让听众也能理解，就是**Cruise**公司，他们发生了一起事故，基本上导致公司倒闭。我想知道人们是否对单一事件反应过度，因为无论如何，事故都会发生，对吧？因为这是一个统计学问题，但我不知道监管机构是否理解，你不能从单一事件中推断，但我们却这么做了，因为我们只有这些数据可循，而且你的样本量必然会比消费驾驶更小。

<details>
<summary>Original English</summary>

**Host**: One thing I often talk talk about I think and I try to make this relatable to the audience also is Cruise where they had an accident that basically ended the company. I wonder if people overreact to a single incident because incidents are going to happen regardless, right? Because it's a statistical thing, but as long I don't know if regulators understand that uh you cannot extrapolate from a single incident, but we do because that's all we have to go on and your sample sizes are necessarily going to be lower than I consumer driving.

</details>

**Kasar Younes**: 是的，我认为**Cruise**的案例并非技术故障。嗯，真正复杂的问题在于公司如何与监管机构沟通，以及他们的行为方式。我认为这成为了更大的问题，如果你看，你知道，它肯定是一个技术故障，但它被大大加剧了。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, I think the the the cruise example wasn't a technology failure. Um there was the the real uh compounding issue there was just how did the company talk to the regulators and and what was their kind of behavior and I think that became more of the issue if you look you know isn't it definitely was a technology failure but it was made much

</details>

**主持人**: 是的，是的。换句话说，**Cruise**仍然存在一个版本。

<details>
<summary>Original English</summary>

**Host**: yeah yeah let me put it another way there is a version where crew still exists

</details>

**Kasar Younes**: 对。这就像是漫长链条中的最后一根稻草。**ATG**曾发生过那起可怕的事故，有人真的因此丧生，因为，你知道，那是一个无家可归的人过马路。所以，是的，我认为，呃，我们不能低估，最终，统计验证只是其中的一部分，但它不是唯一的。像消费者和，比如说，这些技术的主流采用也将是这个讨论的一部分。我认为像**Waymo**这样的公司正在为行业做出很多积极贡献，就他们正在设定一个高标准，并且他们正在以一种非常负责任的方式展示如何处理这些问题。也有过更多的事故。只是它们没有你提到的**Cruise**那起那么严重。但是，是的，所以我想你会继续看到这种情况。我认为长期问题实际上仍将围绕着：很明显，从统计学上讲，人类是糟糕得多的驾驶员。是的。没有争议。所以，在哪个时间点，我们是感性动物？

<details>
<summary>Original English</summary>

**Kasar Younes**: right it was like the last straw in like a long chain of like ATG had that horrific accident or someone actually dying uh because you know uh that was a homeless person crossing the street. So yeah, I think I think uh we can't understate enough that ultimately like statistical validation of something that's one part of it but it's not the only part of it like consumer and let's say mainstream adoption of these technologies is also going to be part of that conversation. I think companies like Whimo are doing a lot of, you know, service positively to the industry in the sense of they're they're setting a high benchmark and they're showing, you know, kind of in a very responsible way how to how to deal with these. There have been way more incidences as well. They've just not been as significant as as the cruise one that you mentioned. But yeah, so I think I think you'll just continue to see that. I think probably the long-term question is really going to be again around like it is very clear humans are way worse drivers statistically. Yeah. Like there's no there's no debate. And so at what point we're emotional animals?

</details>

**主持人**: 是的。所以我的想法是，作为一个社会，我们必须达到一个程度，接受那些本不会由人类造成的恐怖事故，因为从统计学上讲，我们明白总体上它更安全。就像飞机一样，它们更安全，我认为它们是我们拥有的最安全的交通方式。

<details>
<summary>Original English</summary>

**Host**: Yeah. So my thing is like we have to get to a point as a society where we accept horrific accidents that would never happen by a human because statistically we understand that it is safer overall. In the same way that planes they're safer uh than I think they're the safest mode of transport that we have.

</details>

**Peter Lewig**: 是的。我的意思是，开车去机场比坐飞机更危险。所以，如果你对坐飞机感到紧张，只要想想我只要到达机场就好了。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. I mean it's more dangerous to drive to the airport than it is to get the flight. So, so if you're ever if you're ever getting nervous about getting on a plane, just think I just got to get to the airport.

</details>

**主持人**: 如果我到达机场，我就会没事。

<details>
<summary>Original English</summary>

**Host**: If I get to the airport, I'll be good.

</details>

**Kasar Younes**: 但那也是飞机，它也集中了恐怖风险，而且如果，如果飞机，是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: But then that's planes also concentrated terror risk and if if planes Yeah.

</details>

**Peter Lewig**: 我是说，我，我，我真的不认为我们需要担心这些系统会造成比人类更糟糕的事故，因为人类确实会做可怕的事情。人们总是会在方向盘前睡着。

<details>
<summary>Original English</summary>

**Peter Lewig**: And I was I I I don't think we honestly have to worry about there ever being accidents from these systems that are much worse than what humans would cause because humans do do terrible things. People fall asleep at the wheel all the time.

</details>

**Kasar Younes**: 我有，我，我曾经疲劳驾驶。有点像酒驾，那是极端的例子。但是，嗯，我的意思是这些AI系统有冗余，有回退机制，有很多很多事情必须出错才能真正发生灾难性的事情，因为这些系统有很多回退机制。

<details>
<summary>Original English</summary>

**Kasar Younes**: I have I I've been a drowsy driver. kind of like drunk drivers and that's that's the extreme end of the example. But um I mean these AI systems you have redundancies, you have fallbacks like there's many many things have to go wrong for there to actually be something catastrophic because there's there's so many uh fallbacks that these systems have.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

### 模拟的挑战与精度

**主持人**: 我的意思是，你们的**模拟**非常庞大，因为有太多的用例。那么，有没有在模拟中奏效，但实际部署后却完全不起作用的情况呢？是的，也许对模拟有一些误解。所以，让我在这方面多说一些技术细节。首先，没有模拟能够完美地代表真实世界。总是存在一个“**模拟与现实匹配**”的过程，你需要真实世界的反馈来为模拟器中使用的参数提供数据。你需要多次重复这个验证流程，直到你确信模拟器现在能够准确地代表真实世界中将要发生的事情。现在，如果你在已经完成完整验证并认为其准确无误的情况下，却出现了不同的情况。那些是更棘手的情况，而且这绝对可能发生。但实际上，验证过程是非常重要的部分。你永远不能跳过模拟验证过程，也就是确保“嘿，我这里的模拟与现实差距足够小，我可以信任这些模拟结果”。当你深入其中时，有很多有趣的事情可以做。我举一个最近遇到的有趣例子：在这些**类人机器人系统**中，**执行器过热**是一个真实存在的问题，对吧？所以，当然，那些演示非常精彩，我，最棒的，最棒的，我喜欢看机器人表演杂技，就像所有人一样。但是这些系统实际上会过热，对吧？如果，如果你使用模拟，你可以将这些执行器的温度作为模拟中表示的参数之一。然后，如果你正在对某个任务进行**强化学习**，那么机器人就可以在模拟中调整其运动，以考虑这样一个事实：它知道在移动时，它实际上正在导致这个电机过热。但是，如果你最初没有在模拟中表示电机热量这个参数，那么你的**强化学习策略**可能会忽略这一点，然后你把它应用到机器人上，机器人就会过热并发生故障。

<details>
<summary>Original English</summary>

**Host**: I mean your simulation is like so vast because there's so many use cases. What are like maybe things that worked in a simulation and then you put it out and it's like this just this just did not work at all. Yes, maybe a bit of a misconception uh about simulation there. So, let me go a little bit more more technical on this. So, um at first go, no simulation is is going to represent the real world. There's always a process of this uh sim to real matching where you actually you need the real world feedback to basically feed into the parameters that are being used in the simulator. And you have to do that. It's like this validation flow uh a number of times until you can get some confidence that oh I I think the simulator is now accurately representing what's going to happen in the real world. Now if if you have a situation where you've done that full validation and and you thought that it was accurate and then there's something different. Those are much trickier cases and that's that absolutely can happen. But really the validation process is a really important part. you can never skip the simulation validation process like where you're actually ensuring that hey actually my sim real gap here is is small enough that I can trust these uh these simulation results and and there's there's so many fun things that you can do when you get into it like I'll give one one fun example that came up recently is like in these uh these humanoid robotics uh systems overheating actuators is a real problem right so uh obviously phenomenal demos I the most amazing the most amazing I can get I I love watching robots do acrobatics like everybody. But these systems actually overheat, right? If if like and one of the ways you can use simulation though is you can actually have that the temperature of those actuators be one of the parameters that's represented in the simulation. And um and then if you're doing reinforcement learning over a certain task, then the robot can actually adjust its motions in the simulation to account for the fact that oh, it knows that as it's moving, it's actually beginning to overheat this this motor. But if you didn't have that parameter of let's say the heat of that motor represented in the simulation initially then your RL policy might it will disregard that and now you run that on the robot and the robot will overheat and and fail.

</details>

**主持人**: 我猜问题是，你们如何处理所有这些参数，同时还要了解部署环境？比如温度就是一个很好的例子，对吧？

<details>
<summary>Original English</summary>

**Host**: I guess the question is like how do you have all of these parameters taken care of while also understanding the deployment environment like temperature is like a great example right well

</details>

**Kasar Younes**: 为什么你把我的机器人弄得更糟了？当它在一个冰柜里运行时，它其实不应该担心这个问题，你知道吗？就像，是的，你们如何设计这些模拟？

<details>
<summary>Original English</summary>

**Kasar Younes**: why did you make my robot worse when it runs in like a freezer so it actually shouldn't worry about that you know it's like yeah how do you design these simulations

</details>

**Peter Lewig**: 这老实说就是让**模拟**如此困难的原因，对吧？因为模拟本质上是关于你试图优化系统的开发，对吧？我如何更快、更好、更便宜地构建系统？我有哪些杠杆可以实际实现这一点？而且因为模拟只是一个软件程序，你可以比硬件系统更容易地改变它。然后，**世界模型**和使用它作为模拟的一部分的特别之处在于，现在模拟不再仅仅随着添加新的数学方程而扩展，我们现在可以通过额外的真实世界数据来扩展模拟环境，这同时也开启了机器人学的一个全新领域。

<details>
<summary>Original English</summary>

**Peter Lewig**: this is honestly the the this is what makes simulation so hard right uh it's because you simulation is is fundamentally about you're trying to optimize the development of a system right how can I build the system faster and better and cheaper and and what are all the levers that I have to actually accomplish that and and because simulation's just a software program you can you can change it a lot more easily than you can hardware systems and then what's particularly awesome about the let's say world models and using that as a part of simulation is now the simulation doesn't just scale with let's say adding new math equations in but we can actually scale the simulation environment now with uh with additional real world data and and that That also unlocks I would say a whole new field of robotics.

</details>

**Kasar Younes**: 有一条界限，当你跨过这条线时，进行**真实世界测试**会更好。在这个“**中心轮间隙**”中，你可以以极其昂贵的成本重现现实，而且没有什么东西是免费的。所以你真正要做的就是找到那条界限，在那里你既能获得良好的性能，又能获得良好的反馈，无论是在训练端还是在评估端，而且它比在真实世界中做要便宜得多。在某些时候，这样做就没有意义了。所以，即使从我们自动驾驶最早的日子起，我们的观点就是你仍然会进行真实世界测试。没有，没有这个神奇的国度，你不会那样做。而且，也许更细致地说，在传统软件开发中，你知道，车辆中软件的大部分测试，95%都可以是像传统**CI/CD**那样的流程，就像你在传统**Web开发**中会有的那样。但一旦你有了，比如说，一辆卡车，你可以在一个**试验台**上做其中的4%，这个试验台拥有卡车的所有电气电子组件，但没有轮胎，也没有物理特性。然后你还有1%，那就是实际的车辆。在使用模拟进行智能系统方面，也有类似的类比。你在模拟器中做了很多工作，但，嗯，并且使用**世界模型**，呃，但最终它是**物理AI**，所以你将把它部署到物理机器上，而冰柜的例子也由此而来。

<details>
<summary>Original English</summary>

**Kasar Younes**: There is a meniscus line where you cross where still doing real world testing is better. There's a in this center wheel gap you can reproduce reality at exceedingly expensive costs and nothing is free. So really you you finding that line where you're getting great performance, you're getting great feedback, whether it's on the training side or on the eval side, but it's way cheaper than doing in in the real world. At some point that doesn't make sense. And so even, you know, from our earliest days in autonomy, our view was you're still going to do real world testing. There's there's not there's not this, you know, magical land where you're not going to do that. And uh maybe even like a more nuanced version of this in like traditional software development is you know most of your testing for software in a vehicle 95% of that can be like traditional CI/CD kind of flows that you'd have in traditional web development but once you have now you let's say you have a truck you can do like 4% of those in like a rig which has all the components the electrical electronics of a truck but doesn't have it doesn't have the the tires and it doesn't have the physics and then you have the 1% which is actually the vehicle. There's something sim there there's a similar analogy in terms of using simulation for intelligent systems. you do a lot in a simulator but um and and using world models uh but ultimately it's it's physical AI so you're going to deploy it on physical machines and the freezer example comes to comes to light

</details>

**主持人**: **世界模型**对我来说一直是最难理解的东西。比如，我们有一个关于

<details>
<summary>Original English</summary>

**Host**: the world model thing has been to me the hardest thing to wrap my head around like we have fill on on the

</details>

**Kasar Younes**: 我们一直在做一些小系列，比如其他**Intuition**公司的**General Intuition**也一样。是的，我的意思是，有很多关于**NeRFs**的报道。

<details>
<summary>Original English</summary>

**Kasar Younes**: we've been doing a small series of like and other intuition companies general intuition as well uh yeah I mean lots of lots of coverage on nerfs and

</details>

**主持人**: 是的，这感觉就像我们谈论**日心说**一样，对吧？就像在一个**世界模型**中，如果你只输入视觉数据，模型可能会学到太阳是绕着地球转的，这听起来有道理，对吧？但实际上并非如此。我想，还有哪些类似的事情？比如**水滑**。我想，一个世界模型能否理解**水滑**，以及多少水量会导致水滑？对我来说，我不知道你们是怎么做到的。我想，当你们同时在日本的高速公路上驾驶汽车和在亚利桑那州或其他你们部署挖掘机的地方进行作业时，你们在多大程度上依赖**世界模型**来生成模拟，然后尝试弥补差距，而不是将世界模型作为工具交给工程师来策划模拟，如果这有道理的话。

<details>
<summary>Original English</summary>

**Host**: yes it it feels like like we talked about um the heliocentric system, right? It's like in a world model, if you just feed visual data, the model might learn that the sun spins around the earth, it makes sense, right? And it's like, well, not really. And I think what are like some of these other things that like like hydroplaning is one thing I think about. It's like, can a world model understand hydroplaning and like what amount of water like causes it to happen? And it's like, yeah, to me it's like I don't understand how you guys do it. I guess is like the the real thing is like when you're doing both cars and the highway in Japan versus the you know excavator and a line in uh wherever you're Arizona wherever you're deploying them how much of it are you relying on the world models to like generate the simulations for you and then try and close the gap after versus like giving the world models as a tool to your engineers to like curate the simulations if if that makes sense.

</details>

**Peter Lewig**: 是的，完全正确。所以，嗯，我可以说，在纯粹的工程层面，我认为如果你希望进行真实世界的部署，并且你完全依赖**世界模型**方法，你可能在破产之前都无法实现其运作。所以，有一个非常实际的心态是：嘿，**世界模型**很棒，在很多用例中都非常有用，但你需要做很多其他事情才能实际启动、部署和运行它。最根本的是，**世界模型**是关于理解世界，但也是关于理解将会发生什么。它就像**因果关系**，对吧？所以，如果你有一个建筑工具，这个建筑工具将以某种方式在地球上进行一些工作，它将移动泥土，世界模型需要理解这种因果关系，比如：好的，当我把这些材料从这里搬到那里时，现在这些东西就在那里了，而不再在这里。这种因果关系。嗯，数据显然是一个大问题。**水滑**就是一个非常好的例子，因为它有时确实很不明显，对吧？就像，嗯，正在下雨，而且这条路，比如说，有适当的弧度，所以水从路上流走，汽车在这里开得更快。然后你接近一条非常平坦的路，水现在积聚在那条路上，突然之间汽车开得更慢了，因为当它们开得更快时，它们开始失去控制。嗯，而且，场景中有很多视觉上的细微差别。所以，我确实认为，在**世界模型**概念中，模型很可能会学会当这些视觉线索出现时，你就应该开慢点。这显然就是这些模型的美妙之处，对吧？它们只是学习这些不明显的东西。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah totally. So um I can say at a pure engineering level I think if if you're hoping to do real world deploys and you're purely relying on a world model approach you probably won't get to something that works uh before you go bankrupt. So there is just a very practical mindset of like hey world models are are amazing and they're extremely useful for a lot of use cases but there are a lot of other things that you need to do to actually get something started and something deployed and working. Uh most fundamentally role models are all about it's understanding the world but also understanding what's going to happen. It's like the cause effect relationship right and so like right if you have a take some sort of construction tool uh and that construction tool is going to be doing some work on the earth in in some way it's going to be move moving earth um the world model needs to understand that cause effect relationship like okay when I when I take this material from here and put it over there now I have things that are over here and and not over there anymore and that that cause effect relationship. Um, data obviously is a is a big problem. The hydroplane one is is actually a really great example because it's actually quite non-obvious sometimes, right? It's like, well, it's it's raining and uh and well, this this road uh has, let's say, the appropriate curvature to it, so the the water is running off the road and cars are driving faster here. And then you approach a road that's very flat and water is now puddling on that road and all of a sudden cars are driving slower because when they were driving faster they were starting to lose control. Um and uh there are a lot of visual nu uh very nuanced visual cues in the scene. And so I do think in in the world model concept there's a good chance the model actually would learn that you should just drive slower when these visual cues exist. And that's obviously the be the beauty of uh these kinds of models, right? just they learn these non-obvious things.

</details>

**主持人**: 它不需要知道**水滑**来知道它需要开慢点。我想是的。

<details>
<summary>Original English</summary>

**Host**: It doesn't need to know about hydroplaning to know that it needs to drive slower. I guess it's Yeah. Yeah.

</details>

### 嵌入式系统与模型部署

**主持人**: 我想问关于部署模型的问题，假设你们用了很多这些模型进行训练数据和模拟，但是如何将它们部署到生产系统上呢？大概你们在设备上有**GPU**，但我一直在说“在设备上”。对机器来说，正确的术语是什么？

<details>
<summary>Original English</summary>

**Host**: want to ask questions about uh also the deploying models that presume like you you use a lot of these models for training data and simulation, but what about deploying it onto the systems in in production? Presumably, you have you have like GPUs on device, but they're I keep saying on device. What's what's the right term for machine?

</details>

**Peter Lewig**: 我们称之为**嵌入式**。是的。

<details>
<summary>Original English</summary>

**Peter Lewig**: We're embedded. Yeah.

</details>

**主持人**: 是的，是的。**嵌入式世界**是什么样的？因为对于不熟悉那个世界的人来说，这非常陌生。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. What what is the embedded world like? Because for for for people who are not used to that world, this is very alien.

</details>

**Peter Lewig**: 是的，是的。所以，我们实际上称之为**板载**和**离板**。所以，嗯，板载软件和离板软件。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Yeah. So, so actually we we call it onboard and offboard. So, um onboard software and offboard software. And

</details>

**Kasar Younes**: 离板软件的优点是你不必关心时间。而且你可以运行非常大的模型，对吧？所以你可以说，这个模型，我不在乎它给我结果需要1秒还是10秒。呃，因为我们有时间，而且模型可以非常大，它们可以在数据中心或大型**GPU**上运行，你当然可以有分布式计算等等。但是板载你没有这些好处。就像，嗯，我需要在这个模型中获得答案的毫秒数，所以更多的精力在于，把它想象成**蒸馏**，它就像真正的效率，字面上每毫秒的每一个分数都很重要，而且你不能出现模型花费太长时间的情况，因为那样车辆就无法正常工作。是的。所以你仍然可以使用很多相同的技术，而且模型本身，你可以把它想象成你可以在离线运行的更大模型的**派生**，然后你只是试图得到一个仍然表现良好但更小、足够小的版本，然后你可以在这个嵌入式系统上运行，在那里你关心延迟和功耗。

<details>
<summary>Original English</summary>

**Kasar Younes**: the the great thing about offboard software is you don't have to care about time. Uh and you can run really large models, right? So, you can you can say, well, this this model, I don't care if it takes 1 second for it to give me a result or 10 seconds for it to give me a result. uh because we have time and the models can be really big and they can run uh in the data center or on a on a huge GPU and and you can obviously have distributed compute etc. But on board you don't have have any of those benefits. like well I need I have this many milliseconds where I need an answer from this model and so a lot more of the energy then is about think of it more like distillation and and it's like truly efficiency and like literally every every fraction of a millisecond counts and and uh and you you you can't have a situation where the model takes too long because then the vehicle can't actually function. Yeah. And so you can you can still use a lot of the same techniques uh and and the the models themselves you can think of as like a derivative of of larger models that you can run offline and then you're you're trying to just get a model that is still performs really well but it's it's a it's smaller small enough version that you can then run on this embedded system where you care about latency and power.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Kasar Younes**: 是的。我认为，呃，我认为一个更广泛的观点，可能不那么明显，但值得一提的是，在**物理AI**世界中，我们目前并不受模型智能的限制。实际上，**Peter**所说的，实际上是将它们部署到

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. And I think like the the broader point I think uh which which uh maybe is not obvious but it's worth saying is in the physical AI world we're not really constrained right now by like the intelligence of the models. It's actually what Peter's talking about is actually deploying them in

</details>

**主持人**: 它们给你的硬件上。

<details>
<summary>Original English</summary>

**Host**: the hardware they give you.

</details>

**Kasar Younes**: 是的。在他们给你的硬件上。所以，在安全关键系统方面，这是一个现实。所以这些最终成为你的限制因素，而不是，比如说，一个**基础模型公司**的限制因素可能是资本，你知道，或者是研究人员。所以我们以这种方式处理这些事情，你知道，对于我们这些来自那个领域的人来说，这些限制因素非常有趣，它们会激发创造力。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. On the hardware you give you and and so and there's a reality is of safety critical systems. So those end up being your your limiting factors rather than let's say a limiting factor for you know a foundation model company is going to be just capital maybe you know or or or researchers. So we're we're in that way dealing with you know for us as people who kind of come in that realm of like a very interesting those constraints force creativity

</details>

**主持人**: 我想，在2018年，没有人会部署或给你**Transformer**的硬件，但现在他们会了。这种演变是怎样的？呃，请稍微揭开帷幕。

<details>
<summary>Original English</summary>

**Host**: and I imagine you know nobody was deploying or giving you the hardware for transformers back in 2018 whatever but now they are. What's the evolution like? Uh just peel back the curtains a little bit.

</details>

**Peter Lewig**: 是的，首先是**Transformer**。我认为这篇论文最初是在2017年发表的。所以没有时间。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, transformers first off. I think the paper was originally published in 2017. So there's no time

</details>

**主持人**: 而且，呃，我

<details>
<summary>Original English</summary>

**Host**: and uh I

</details>

**主持人**: 但我只是说，我猜我的意思是，你知道，**嵌入式ML系统**通常参数少得多，计算量少得多，而现在，数量级增加了。

<details>
<summary>Original English</summary>

**Host**: but I'm just saying I guess I'm saying like you know embedded ML systems usually like a lot less parameters, a lot less compute and now like orders of magnitude more.

</details>

**Peter Lewig**: 是的。是的。绝对是。嗯，我当时想说的是，我认为在，呃，在2017年的原始论文中，也许在论文的最后一句话的某个地方，他们提到了，顺便说一下，这种技术可能对图像和视频也很有用。而且，这种影响花了几年时间才真正显现出来。但现在，我们看到**Transformer**无处不在。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Yeah. Absolutely. Um, what I was going to say though was I think in the uh in the original paper in 2017, maybe it's in the last paragraph somewhere in the paper, they talk about like by the way this this this technique might might be useful for like images and videos as well. And uh it took a few years for that impact to really hit. Uh but like now I we're seeing transformers are everywhere.

</details>

**Kasar Younes**: **Transformer**和，呃，嗯，是的，然后计算能力不断变得越来越好。嗯，但你确实有一个基本的权衡，对吧？它就像是你拥有功耗，你拥有成本，呃，还有性能，以及在**嵌入式封装**中获得这些东西的正确组合，这个封装还可以经受震动和烘烤，以及这些东西必须在其中运行的所有条件。但是，是的，我认为它们只会变得越来越好。所以我们也尝试着在理解这些系统改进速度的基础上规划我们的策略。

<details>
<summary>Original English</summary>

**Kasar Younes**: Transformers and uh the um yeah then the compute just keeps getting better and better. Um but you do have this fundamental trade-off, right? It's like you have power, you have cost uh and and performance and and like getting the right getting the right mix of those things in an embedded package that can also be like shaken and and baked and all the conditions that these things have to have to operate in. But yeah, I think that they're only going to keep getting better. And so we also try to plan our strategy understanding that uh we know the rate of improvements of these systems.

</details>

**主持人**: 是的。所以就像**Google**刚刚发布了**Gemma 2B**模型，一个有效的2B模型。这对你们有用吗？还是太大了？你肯定可以在嵌入式系统上运行那个模型。是的。嗯，嗯，所以是的，它在这方面是有用的。更大的问题是，你将用什么来作为**嵌入式系统**？你实际上需要对其进行大量定制才能使其有用。但是，是的，你肯定可以运行一个20亿参数的模型。

<details>
<summary>Original English</summary>

**Host**: Yeah. So like Google just released the Gemma 2B model like effective 2B model. Is that useful to you guys or is that too big? You can run that model on an embedded system definitely. Yeah. Um the um so so yes it's it's useful in in that regard. The bigger question is like what do you use for an embedded system? Like you actually need to customize it quite a bit to make it useful for for something. But uh but yeah you you could run a two billion parameter model definitely.

</details>

**主持人**: 同样有趣的是，定制的**ML模型**占多少百分比，它只做那件事，而不是一个通用的**LLM**？呃，这可能对你们的情况来说并不那么有用。你可以想象不同的用例，对吧？所以

<details>
<summary>Original English</summary>

**Host**: Also interesting like what percent is a custom ML model that only does that thing versus a generalist LLM? Uh which probably is not that useful actually for your context. Like you can imagine different use cases, right? So the

</details>

**Kasar Younes**: 语音方面，是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: the voice stuff, yes.

</details>

**Peter Lewig**: 完全正确。是的。所以，对于，嗯，实际的**自动驾驶元素**，我的意思是，那是百分之百内部完成的，我们做了所有的一切。数据模拟、模型，所有的一切。嗯，但是当你进入更通用的用例时，比如语音或语音助手之类的，那就是这些更通用的模型，比如**Gemma**，实际上可能非常有用武之地。

<details>
<summary>Original English</summary>

**Peter Lewig**: Totally. Yes. So for the um the actual uh autonomy elements, I mean that's 100% in-house, we do every bit of that. The data simulation, the model, everything. Um but when you get into the more generic use cases like voice or voice assistant kind of thing, that's where these these more generalist models like GMA actually can be quite quite useful.

</details>

**主持人**: 是的。而且显然，在“你必须在机器上完成多少工作”和“只需打电话回家”之间也存在权衡。

<details>
<summary>Original English</summary>

**Host**: Yeah. And then there's also obviously a trade-off between like what percent must you do on machine uh versus just call home.

</details>

**Kasar Younes**: 是的。一切都关乎**延迟**。一切都关乎延迟。是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. It's all about latency. It's all the latency. Yeah.

</details>

**主持人**: 是的。嗯，就像，你知道，我认为实际上在很多情况下，尤其是在美国，你只需要连接到网络。

<details>
<summary>Original English</summary>

**Host**: Yeah. Well, like you know I think actually in a lot of context especially in the US you can just have a connection to to the web.

</details>

**Kasar Younes**: 是的。我想我，我想我们的大部分世界都是，所有东西都必须是相当的，呃，你知道，**嵌入式**和**本地化**的，因为仅仅是这个性质。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. I think I I think though most of our universe is everything has to be fairly uh uh uh you know embedded and local because just the nature of

</details>

**主持人**: 即使在美国，仍然有很多地方没有网络覆盖，对吧？如果你看看采矿业的旧式自动驾驶世界，那是在**Transformer**和，以及神经网络，比如**CNN**和这种宇宙出现很久之前，它们真的只是**手工编码**的系统。它们只是说这台机器将以这种**RG精确的GPS**运行到那个地方。

<details>
<summary>Original English</summary>

**Host**: even in the US there's a lot of like still have coverage right and if you look at like uh the old world of autonomy within mining which is like long before transformers and and and kind of a neural networks uh in the like CNN and kind of a universe they were really just handcoded, you know, systems. They were just like this machine is going to run to that place with this RG accurate GPS.

</details>

**Peter Lewig**: 是的。这奏效了，而且奏效了20年。那么我们为什么要使用**Transformer**或更现代的**端到端系统**呢？主要是因为你只能真正沿着一条路径运行，然后倒退。这提供了很多价值，但不如机器真正智能时所获得的价值大。它在动态世界中感知、理解和行动。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. And so that worked and that works for 20 years. So why would we actually need to use transformers or kind of more more modern end to end systems? Mainly because you can only really run a path and run backwards. That provided a lot of value, but not as much as you get when the machine is actually intelligent. It's it's seeing, it's perceiving, it's acting in a dynamic world.

</details>

**主持人**: 我查了一下**RTK**，**实时动态定位**，精度在一到两厘米。

<details>
<summary>Original English</summary>

**Host**: I looked up RTK, realtime kinematic, uh, one to two centimeter accuracy.

</details>

**Peter Lewig**: 是的。是的。太棒了。但是，你知道，在没有手机信号覆盖的偏远地区也很棒。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Yeah. Fantastic. But, you know, and fantastic in far away lands where there's not going to be cell phone coverage.

</details>

**Kasar Younes**: 是的。同样的事情。它广泛应用于今天传统的采矿和农业**自动驾驶系统**。所以，比如，一台收割机在田里行驶时可以精确到一两厘米。呃，他们使用**RTK**。它很昂贵。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. Same thing. It's widely used on the legacy mining and agriculture autonomy systems today. So, like, uh, for example, a combine that can be precise within one or two centimeters as it's driving down the the field. Uh, they use RTK. It's expensive.

</details>

**Peter Lewig**: 是的。它确实是自动驾驶，但它不像我们2026年所说的智能那样智能。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. And it's it's autonomy, but it's not intelligent in the way that I think all of us if in 2026 would be talking about intelligence.

</details>

### 多元化策略与创新

**主持人**: 在你的一篇博客文章中，你提到了关于**大规模Transformer**的研究，这些研究类似于现代**生成式AI**。除了“你绝对正确，我应该驾驶汽车”之外，还有什么大的区别？所以我想你可能想删除那部分。我们内部有一个多元化的投注策略，我们之所以这样做，是因为我们现在在许多行业和许多地理区域运营，而且每种方法老实说都有不同的风险。所以，呃，我们不会把所有的鸡蛋都放在一个篮子里，采用单一的方法，因为那种方法可能行不通。

<details>
<summary>Original English</summary>

**Host**: In one of your blog posts, you mentioned research on large scale transformers that are similar to those doing modern generative AI. What are like the big differences other than you're absolutely right. I should steer the car. So I don't you probably want to remove that. We have a diversified bet strategy internally and and the reason we we've done that is because we operate in now a bunch of industries, a bunch of geographies and and each of the approaches has honestly a different risk to them. And so uh like we're not going to put all of our eggs in in a single in a single basket for a single approach because that approach may not work out.

</details>

**Kasar Younes**: 嗯。

<details>
<summary>Original English</summary>

**Kasar Younes**: Mhm.

</details>

**Kasar Younes**: 呃，所以，这是我们的一个赌注，它在某些场景下有某些优势，但这些事情在实践中会如何发展，它有某些好处，也有某些缺点。然后研究团队会努力解决在这些其他方法下表现更差的情况，并最终为所有这些事情找到一个真正伟大的解决方案。

<details>
<summary>Original English</summary>

**Kasar Younes**: Uh and so that's that's one of the bets that we have and it has certain advantages in in certain scenarios and then but the way that these things play out in practice is it has certain benefits. It also has certain drawbacks and and then and then the research team tries to then work on uh the situations where that's actually worse than than these other approaches and uh to ultimately arrive at at a really great solution for all these things.

</details>

**主持人**: 物理自动驾驶有**规划模式**吗？比如，你有一个规划步骤，然后是执行步骤吗？

<details>
<summary>Original English</summary>

**Host**: Is there a plan mode for physical autonomy like do you have a planning step and then action step or

</details>

**Peter Lewig**: 所以简短的回答是肯定的。对。对。就像你可以使用**Claude Code**来规划一些复杂的编码任务，并且你会得到一些几乎是规范性的东西。这些类似的方法绝对可以应用于物理系统，因为想象一下你正在尝试完成某个任务。最容易想到的是**机器人出租车**。但我认为在国防或采矿领域，事情会变得更有趣。你实际上必须提前考虑很多步骤。这不仅仅是一件事，而是要完成目标，有上百个步骤。然后这种**计划模式**的概念，是的，非常适用于此。

<details>
<summary>Original English</summary>

**Peter Lewig**: so short answer is yes. Right. Right. So just like you can use uh cloud code to to plan out some complex coding task and and you get some almost specification written out. Those similar similar approaches absolutely can be applied to physical systems because imagine you're trying to accomplish some task. The easiest to think about is is robo taxi. But I think things get more interesting let's say in the defense context or in uh in the in the mining context. You actually do have to think about many steps in advance. It's it's not just this one thing, but to accomplish the goal, there's a hundred steps and then the this concept of the plan mode, it's yeah, very applicable in this.

</details>

**主持人**: 是的。我，我当时想说，对我来说，驾驶感觉就像一个很棒的**下一个令牌预测**的东西，因为你有点像在一条路上，而且你之前做了什么真的不重要，你知道，你总是可以转身。是的。

<details>
<summary>Original English</summary>

**Host**: Yeah. I I was going to say to me, driving feels like a great next token prediction thing because you're kind of like on a path and like it doesn't really matter what you've done before, you know, you can always turn around. Yeah.

</details>

**Peter Lewig**: 是的。而像采矿，它就像，哦，天哪，我从这个东西里挖了一勺，现在我们真的不能再去了，你知道吗？就像，有没有巨大的不同，我想，你如何划分这些不同类型的自主性，或者说，驾驶、挖掘、飞行等类型？

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Versus like mining, it's like, oh man, I took a, you know, I took a scoop out of this thing. It's like now we can't really, you know, I can't really go there anymore, you know? It's like is there like a huge different like how would you I guess like do you have like a tonomy of like these different types or there's kind of like driving excavating like flying

</details>

**Kasar Younes**: 有趣的是，我认为世界上的一切实际上都可以归结为**下一个令牌预测问题**，嗯，任何工作流，任何事物，都可以被视为有一系列步骤或一系列轨迹或其他你想要称之为的东西，它实际上可以归结为那种事情。在采矿案例中，你可以想象像挖了一勺，好的，那是一组令牌，现在模型理解了状态空间是不同的，现在下次我做令牌预测时，它会被修改。但是，是的，这些技术的卓越之处在于它们的**普遍适用性**，对吧？我的意思是，它确实是令人难以置信的。

<details>
<summary>Original English</summary>

**Kasar Younes**: so the interesting thing is I think probably everything in the world can actually be boiled down to like a next token prediction problem um and uh any workflow anything uh can be thought of almost as like there's this the sequence of steps or the sequence of trajectories or whatever you want to call it and it can be boiled down actually to to that sort of thing and in the mining case you can imagine like taking that scoop okay that was that set of of tokens and and now that's the model is now understanding that okay that the state space is different and and now the next time I do token prediction it's going to going to be modified by that but yeah the remarkable thing about these techniques is just how how universally applicable they are right I mean it's it's truly is incredible

</details>

### 物理AI的生产化挑战

**主持人**: 你们在构建物理AI方面还有哪些被低估了？我的意思是，我们在节目开始前就谈论过这个问题。有很多**类人机器人公司**会做这些很棒的演示。呃，然后我买不到，所以显然它不存在。在你们的情况下，你们在真实的街道上进行生产，有很多客户。人们低估了什么？就像七年前的演示很棒，然后花了七年才真正投入使用一样。你能分享一下，也许在技术上最难完成的最后1%是什么？

<details>
<summary>Original English</summary>

**Host**: what else is underrated about what you guys are building on the physical I I think there I mean we were talking about it before the episode. There's a lot of humanoid companies that do these great demos. Um and then I can't buy it so obviously it cannot be there. In your case, you're like in production on real streets with like a lot of customers. What what are like the things people are underestimating the same way the way demos seven years ago were great and then took seven years to actually get them on the street. Can you share about maybe like the last 1% that was really hard to to get done technically?

</details>

**Peter Lewig**: 是的。当然，无论如何，将产品投入生产都非常具有挑战性。嗯，所以我想我可能会把答案分为**研究**和**生产**。首先在生产方面，当你真正将东西投入到现实世界中时，会发现很多问题。我的意思是，现在**类人机器人**领域的经典问题是这些系统实际上相当脆弱。呃，所以，嗯，我不是在谈论任何一家公司，但就整个行业而言，这些系统都相当脆弱。我的意思是，有趣的是，我前几天看到一个东西，呃，我认为中国正在用类人机器人进行**马拉松比赛**。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. So certainly productionizing stuff is really challenging no matter what. Um so I I maybe would I would split the answer maybe into research and then also in into production. First on the production side there's just so many problems that you find when you actually get the stuff to to go in the real world. And so I mean the classic problem in in humanoids right now is these systems are actually pretty brittle. Uh and so um I'm not talking about any one company but just as an industry these systems are are pretty brittle. I mean interestingly I saw this thing uh the other day that uh I think China is doing a a marathon with humanoids.

</details>

**Kasar Younes**: 是的，是的。所以，在政府中，不只是中国政府，任何政府都有一个概念叫做“**奖金政策**”，也就是说，有不同的方式来影响一个行业走向某个方向。比如你可以通过**监管**，对吧？你可以强制执行，或者你也可以进行这些**比赛**。所以美国的版本是**DARPA大挑战赛**。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. Yeah. So so in in government and not China specifically but in any government there is a um there's a concept called uh prize policy which is so that there's there's different ways of of influencing an industry to go a certain direction like you can you can regulate it right you can do mandates or you can actually just do these competitions. So the US version of this was the Darper Grand Challenge.

</details>

**主持人**: 它确实推动了行业发展，但我认为中国真的在举办这场马拉松比赛，因为他们知道**类人机器人**的可靠性是一个问题。那么，有什么比举办一场让类人机器人跑26英里的比赛更能解决这个问题的酷方法呢？

<details>
<summary>Original English</summary>

**Host**: It really worked industry, but I think China is literally doing this marathon because they know that reliability uh of of humanoids is a problem. And so what cooler way to solve that than to have a competition where humanoids need to run 26 miles, right?

</details>

**Peter Lewig**: 我们到了吗？机器人能跑马拉松吗？

<details>
<summary>Original English</summary>

**Peter Lewig**: Are we there? Can can robots run a marathon?

</details>

**Kasar Younes**: 我想快了。

<details>
<summary>Original English</summary>

**Kasar Younes**: I think it's happening any day now. So

</details>

**主持人**: 那么我们就在那儿了。顺便说一句，还有汽车行业，也有一个版本，那就是**24小时赛**。

<details>
<summary>Original English</summary>

**Host**: So we're there. By the way, also you know automotive, there's a version of this which is like 24 hours,

</details>

**Kasar Younes**: 对。就像**保时捷**赢得24小时耐力赛，然后将这些产品投入生产。我实际上会把它分解一下。你谈论**研究**，你谈论**生产**。实际上中间还有一个步骤，那就是**高级工程**，我认为很多行业正在向高级工程迈进，它不像基础研究那样是提出新颖技术。它实际上是为生产而进行的高级工程。那么，哪些子组件会限制其进入生产？一旦进入生产，又会面临另一系列问题，比如这些机器的部署维护。所以，我想说，至少在我们的领域，我们主要从事汽车领域的**高级工程**。

<details>
<summary>Original English</summary>

**Kasar Younes**: right? It's like Porsche wins 24 hours literally puts those, you know, products into production. I would actually break it down. You you talk about research and you talk about production. There's actually a step in the middle which is like advanced engineering and I think a lot of the industry is moving into advanced engineering where it's like it's not fundamental research like we're coming up with novel techniques. It really is advanced engineering for production. So what are the the subcomponents that are going to limit to getting into production once you're in production deal with another set of problems which is like the deployment maintenance uh of those machines that that exist. So I would say at least in our field we're mostly in advanced engineering in the like automotive parllets.

</details>

**Peter Lewig**: 老实说，每一步都很艰难。

<details>
<summary>Original English</summary>

**Peter Lewig**: Honestly every every step is hard though.

</details>

**主持人**: 这就是为什么你价值150亿美元。所以我想你在每一步都倾尽全力。

<details>
<summary>Original English</summary>

**Host**: Well that's why you're worth $15 billion. So I think you you bleed every step.

</details>

**Peter Lewig**: 是的。很有趣。我的意思是，我想，我不知道，我发现它真的很有趣。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. It's fun. I mean I think I mean it's like I don't know I I find it really enjoyable.

</details>

**Kasar Younes**: 是的。但有趣的是，我们已经在这个领域工作了近10年，我们看到了太多的糟糕时期，所以现在我们可以审视这个领域的任何一家公司，看一个演示，然后我就可以写下一份清单，我确切地知道他们将遇到的接下来20个问题，而且我也可以猜测他们将如何尝试解决每个问题，我还可以猜测哪个会真正奏效。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. But what was also fun is like so we've we've been in this now for almost 10 years and like we we've just seen we've seen so much bad time and so right now we we can look at any company in the space and get a demo and like I can I can write down a list of I know exactly the next 20 problems they're going to hit and like and I I can guess also what they're going to try to solve each of those and I can guess which one's going to actually work.

</details>

**主持人**: 是的。这些就像是特别的天才。我们已经见过这些东西了。

<details>
<summary>Original English</summary>

**Host**: Yeah. These were like particularly like geniuses. We've seen this stuff.

</details>

**Peter Lewig**: 是的。我们已经见过足够多的这种东西了。我们经历过足够多的这种东西了。我们，你知道，作为公司的领导者，我们自己的**世界心智模型**。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. We've seen enough of this stuff. We lived a little enough of this stuff. We, you know, our own kind of mental models of the world as as leads in the company.

</details>

**Kasar Younes**: 我们尝试了很多很多事情。我们在这里谈论的是成功，对吧？

<details>
<summary>Original English</summary>

**Kasar Younes**: We've tried so many things in many. We're talking about the wins here, right?

</details>

**Peter Lewig**: 在这么多人在做这么多不同的事情中，有很多失败。嗯，那就会被融入到你的**世界心智模型**中。

<details>
<summary>Original English</summary>

**Peter Lewig**: There's plenty of losses among that many people doing that many different things. And um that kind of like get baked into your like mental model of the world.

</details>

**Kasar Younes**: 是的。但总的来说，我想说，我们对**机器人技术**感到兴奋，当然，还有

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah. But I would say in general like we're excited about robotics for sure and like the

</details>

**Peter Lewig**: 巨大的机会。

<details>
<summary>Original English</summary>

**Peter Lewig**: massive opportunity

</details>

**Kasar Younes**: 巨大的机会。而且行业中发生的事情是，这些概念都不是新的，对吧？新的在于现在这些东西真的奏效了。

<details>
<summary>Original English</summary>

**Kasar Younes**: massive opportunity and what's what's happening in the industry is like none of these concepts are are new right what's new is like the stuff is actually working now

</details>

**Peter Lewig**: 对，就像人们很久以前就想使用**神经网络机器人**一样，呃，但现在我们有了数据集，我们有了**模拟技术**，现在东西真的开始奏效了。是的，我们想要成为其中的一部分，我们也将成为其中的一部分。

<details>
<summary>Original English</summary>

**Peter Lewig**: right like people have wanted to use uh neural net robotics for a long time uh but but now again we now have the data sets we have the simulation technologies where stuff is actually starting to really work and yeah we we want to be part we're going to be part of that for

</details>

### 给创业者的建议

**主持人**: 你对创业公司有什么建议，或者反对创立某些创业公司？有很多像**Scale Approval**这样的新公司。你认为有哪些是需要考虑的？

<details>
<summary>Original English</summary>

**Host**: Do you have requests for startups or like advice against starting certain startups? There's a lot of like scale approval new companies. It's like what do you think are things

</details>

**Kasar Younes**: 很多，很多**Applied Intuition**用于其他事情。我认为你，你在Y的某个地方达到了某个徽章，对吧？你变得像一个，你知道的，或者字面上是相同的类似名称，你知道的，嗯，我的意思是，我认为我最大的建议，你知道，在这种几乎是技术商业化方面，我认为通常这种约束，我们谈到了**硬件约束**，我们也谈到了，呃，在商业方面也有约束，那就是我们只做符合这个框架的事情。我认为这对创始人来说非常好。我认为它之所以不常被关注，是因为你有大量的资本获取途径，而且技术问题非常困难。你会说，我有一个约束，那就是解决这个技术问题。而且我认为**风险投资界**总体而言往往不太懂技术。对他们来说，如果你说如果我们解决了这个问题，就会有很多钱。这对他们来说就足够了。但你作为一个创始人，我不是在给你如何向VC推销的建议。那对VC管用。你仍然需要经营一个可持续发展的企业。我认为我们真正地，在你之前问的那个问题中，关于，你知道，我们公司可能不那么明显的地方。它就像是，这真正是**复利技术**。我们所做的很多工作只是复利。我们不会把它扔掉。它会变得更好。**操作系统**的工作会变得更好。**开发工具**会变得更好。**模型**会变得更好。所以我们真的会获得巨大的，我想你可以在**Waymo**身上看到一个例子，**Waymo**是一家，我想说，在很长一段时间内都非常有趣的公司，但并不值1260亿美元，对吧？所以会发生什么呢？人类大脑就是无法情感上理解**复利效应**，所以这将在我们的世界中发生。所以现在如果你是一个创始人，你正处于那个漫长旅程的开始，如果你能在商业方面施加一点约束，你就有更大的可能性看到那个旅程的另一端，因为如果你到达另一端，你将从**复利技术**中获得巨大的回报，只是很多人没有做到。所以是的，总结一下，想想你如何使用金钱以及你如何使用你有限的资源和有限的工程师。我认为有时创始人会错误地采纳非常成熟的公司的策略，然后应用到他们自己的公司。他们会说，哦，**史蒂夫·乔布斯**说要完全垂直整合。是的，2007年的**Apple**与1978年和1982年非常不同。那些公司是不同的。他们当时只是从其他制造商那里获取电子产品，然后将其放入外壳中。所以我只是想在你的商业方法上更细致一些，因为它会影响你的技术方法。

<details>
<summary>Original English</summary>

**Kasar Younes**: a lot of a lot of applied intuitions for other things? I think you you hit a you hit a certain uh what is it uh you know badge when Y right you become like a you know or or literally the same similar names like you know um I I mean I think my biggest advice you know in this like almost like commercialization of technology is I think often the that constraint so we talked about like hardware constraints and we talked about uh there's also like on the commercial side there's constraints which is we're going only do things that fit in this box. That is, I think, very good for founders. The reason I think it's not often focused on is because you have plenty of access to capital and the technical problems are so hard. You're like, I already have a constraint which is just getting this, you know, this technical problem solved. And I think the venture community generally speaking tends to be not very technical for them. If you just say if we solve this thing, it's going to be a lot of money. That's kind of enough for them. But you as a founder, I'm not giving you advice on how to pitch VCs. That'll work for VCs. You still got to run a sustainable business. And I think we're really in in in that question you asked earlier about kind of, you know, what's maybe not obvious about our company. It's like this is truly compounding technology. A lot of the work that we do just compounds it. We don't throw it away. It it gets better. The operating system work gets better. The de dev tooling gets better. The models get better. And so we're really going to get a hu I I think you see it in Whimo as an example like Whimo is a company that is I would say very interesting for a long time but not worth $126 billion right so what happens like is that the human brain just doesn't emotionally understand the compounding effects so that's going to happen in our universe so now if you're a founder you're at the beginning of that you know that long you know walk if you can put a little constraint on on commercials that has a small ability for you to more likely see the other end of that that walk because you get to the other end you will get the big return from compounding technology just a lot of people just don't make it. So yeah summarize like think a little bit about the equation of how you use money and where you use the limited resources and limited engineers that you have. I think sometimes in founders falsely kind of take very mature companies strategies and then apply to their like nent they're like oh well Steve Jobs says be completely vertical. Yeah, in 2007, Apple is very different than 1978 and 1982. Those companies were different. They they were literally just taking electronics from other manufacturers and putting it in enclosure. And so I just be a bit more like I don't know bit a bit more nuanced in your in your commercial approach as it informs your technical approach.

</details>

**主持人**: 你今天感觉不同吗？我的意思是，你刚刚加入了**X**，对吧？你一直在建立这家公司。你一直在秘密地建立这家公司，现在你就像，嗯，我大概应该谈论我正在做的事情了。我认为很多创始人也有类似的心态，他们想筹集大量资金来表明自己很强大，而你们在没有

<details>
<summary>Original English</summary>

**Host**: Do you feel differently today? Like I mean you just joined X, right? You've been building this company. you've been building this company in stealth and now you're like well I should probably be talking about what I'm doing. I think a lot of founders are in a similar way where they want to raise a lot of money to signal they're strong and you raise a lot of money without

</details>

**Kasar Younes**: 花钱招聘。是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: spending hire and to hire. Yeah.

</details>

**主持人**: 你显然喜欢那样。你认为仍然有可能采取一种非常狭隘的方法，比如“嘿，我们正在构建一个**复利**的东西”，而不需要一开始就有一个宏大的愿景，而不是？

<details>
<summary>Original English</summary>

**Host**: You obviously like that. Do you think that's still possible to like have a very narrow approach of like hey we're kind of like building a compounding thing without a grand vision right away versus

</details>

**Kasar Younes**: 很难回答非常笼统的问题。呃，我，我，所以也许，也许我把它重新定义为：是否有可能构建一个产品，它拥有一个小的，比如说，问题空间，并希望问题空间会增长？也许这是问同一个问题的另一种方式，但更容易回答。我认为总是可以的，那就是旧**YC**的理念：深入挖掘，然后，你知道，而不是广而浅。不幸的是，广而浅有太多的技术，尤其是在**硬科技公司**中，问题太多了，你无法全部做到，而且会做得非常平庸。所以，所以，所以完整的产品实际上相当平庸。所以，是的，我，我仍然认为应该找到一个**小问题空间**。你问的另一个问题是相关的，那就是：你是否应该秘密地构建和匿名地构建？嗯，是的，如果你是**YC的COO**。

<details>
<summary>Original English</summary>

**Kasar Younes**: it's very difficult to answer very general questions that uh I I so maybe like maybe I reframe it as in is it possible to build a product that has a small let's say problem space and hope that the problem space will grow maybe that's like a different way of asking the same question but more answerable I think always yes that is the old YC like go really deep and then you know rather than very broad and shallow very broad and shallow unfortunately there's just too many tech especially in hard tech companies there's just too many problems and you can't you're going to do all of them in a very mediocre way and so the the the the full product is actually fairly mediocre so yeah I I I still in I'm still in the camp of find a small problem space the other question you're asking is a tangental is like should you like build in in stealth and anonymity. Well, yeah, if you're a YCCOO.

</details>

**主持人**: 是的，你可以，因为我们，是的，我们曾在**Google**一起工作。我们有很长的历史，而且我们不，这意味着我们有很大的网络。我的意思是，我们的第一个

<details>
<summary>Original English</summary>

**Host**: Yeah, you can because we Yeah, we worked, you know, together at Google. We have a long history and we don't and which mean which is another way of saying we have big networks. I mean, our first

</details>

**Kasar Younes**: 400人，其中大部分是**Google**员工。公司的大部分人来自，你知道，我们工作过的这家巨头公司，这非常不同。你是一个没有那种经验的创始人，你必须做这些事情。我认为，所以就像，不要采纳我眼中的世界，或者其他创始人**Jensen**眼中的世界，他们处于不同的时间和空间，最重要的是他们的公司处于不同的阶段。

<details>
<summary>Original English</summary>

**Kasar Younes**: of 400 people, majority were Googlers. Like a majority of the company came from, you know, this giant company we worked at and that's just very different. you're a founder who is doesn't have that experience, you have to do these things. And I think it's that's so it's like just don't take my version of the world or whatever other founder Jensen's version of the world, they different time and space and most importantly their companies are in a different phase.

</details>

**主持人**: 不。

<details>
<summary>Original English</summary>

**Host**: No.

</details>

**Kasar Younes**: 所以如果你想从其他非常年轻的公司那里获得灵感，那也很糟糕，因为它们大多数都会失败，对吧？所以你唯一真正的解决方案是使用**第一性原理思维**，并根据我的技能、我的联合创始人的技能、我的早期团队成员的技能以及我从客户那里听到的，来决定我应该在哪个产品空间进行构建。

<details>
<summary>Original English</summary>

**Kasar Younes**: And so then if you want to take inspiration from other really young companies, that's also bad because most of them are going to fail, right? So the only the only solution you really have is use first principal thinking and say based on my skills, my co-founder skills, the skills of my early team members and the what I'm hearing from customers, what's the product space that I should I should build in.

</details>

**主持人**: 是的。这有道理吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Does that make sense?

</details>

**Kasar Younes**: 是的，有道理。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, it does.

</details>

**主持人**: 是的。我，我的意思是，**Sam Altman**他说他后悔在YC给出的大部分建议。所以我总是很好奇地问像你这样的创始人，他们不是，每个离开YC的人都做了相反的事情。你，你知道的，我们，你知道的，当**Sam**是总裁时，我是**COO**，所以我们一起工作，你知道，非常密切，这是一种保守的说法，因为公司当时也很小，但你知道，YC当时不像**OpenAI**那么大。

<details>
<summary>Original English</summary>

**Host**: Yeah. I I mean Sam Sam Alman, he said he regress a lot of the advice that he's given at Y. So I'm always curious to ask, you know, founders like you who've not been everyone who leaves YC like does the opposite. you, you know, we, you know, when Sam was president, I was COO, so and we'd have a CEO, so we worked together, you know, extremely closely would be an understatement because the firm was also small, but you know, YC wasn't wasn't as big as like an open AI is.

</details>

**Peter Lewig**: 我大致同意这一点，但我想说这更多不是YC的功能，而是市场的功能。

<details>
<summary>Original English</summary>

**Peter Lewig**: I I directionally agree with that, but I would say that's not more of a YC function. It's more of the market.

</details>

**Kasar Younes**: 这是一个不同的世界。AI行业是不同的，我应该更具体地说，AI公司以及它们与其他**YC公司**和市场的关系是如此根本性的不同。筹集的资金数额不同，投资者的数量不同，**种子基金**的数量庞大。我们早期的投资者之一是**Floodgate**。他们在大约2000年代末做了一些分析，他们说像**Floodgate**这样只写低于100万美元支票的首轮基金只有个位数。他们不是加速器或孵化器。**Ann**，她是那里的联合创始人之一，和**Mike**一起，他们说今天他们尝试做，或者说，就像3、4年前，他们尝试做这项分析时，他们发现大约有350个基金，或者类似的数量。所以我们正处于一个不同的环境中。所以**2014年的YC建议**在2026年就不适用了。但是**Sam**比我更擅长说这些事情。他以某种方式弥补了

<details>
<summary>Original English</summary>

**Kasar Younes**: It is a different world. the AI industry is different is the the AI companies I should say more specifically and how they relate to the other YC companies and market just so fundamentally different the amount of money raised is different the amount of investors the sheer number of seed funds one of our early investors is floodgate um and they did some analysis in the late uh 2000 like double O's where they were like there's like singledigit number of funds that were like floodgate which were like writing sub$1 million checks first checks and they were not accelerating incubator and Ann who's who's one of the co-founders there uh with with Mike they they said that today they try to do or like today as in like 3 4 years ago they they they tried to do this analysis and they like lost count at like 350 funds or something like that. So we're just in a different environment. So the YC advice from 2014 just would not apply in 2026. But Sam is like way better at saying these things than me. He somehow makes up like

</details>

**主持人**: 他，他，他说得更简短、更有趣。

<details>
<summary>Original English</summary>

**Host**: he he he says it in a shorter most more interesting and than than me. I I can just give you like the like I like if you ask me like you know what are the purpose of a car like open the owner's manual I say number one look there's a steering wheel and you know instead of like it can change your life and

</details>

**Kasar Younes**: 确切地说，是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: mo exactly yeah

</details>

### AI模型效率与工程师特质

**主持人**: 那么对**Peter**来说，我只是有点好奇，是否有任何你认为对你们非常有意义，如果解决了，无论是已解决还是未解决，如果有任何人正在研究，他们应该与你联系的技术或研究问题？

<details>
<summary>Original English</summary>

**Host**: and then for Peter I was just kind of curious if there's any particular tech or research problem that you would call out as very meaningful for you guys if it was solved and unsolved and if anyone is working on it, they should get in touch with you.

</details>

**Peter Lewig**: 是的，我认为，嗯，总的来说，让模型非常高效，对吧？因为我们必须在实际车辆上运行。**物理AI**实际上是，呃，它正在将非常大的AI变得非常小和非常高效，而且，呃，所以我们不断地处于这些限制的边界，比如，你可以有一个很棒的模型，但现在我们需要让它更快更小。所以这在普遍意义上是一个领域，然后我想说，嗯，嗯，那些真正热衷于评估这项技术，比如**模型评估**的人，嗯，这是一个非常困难的话题，尤其是在**安全关键系统**中。嗯，呃，我的意思是，我们现在有一个非常棒的工程团队在研究这个问题，还有研究人员，但这是一个巨大的投资领域，所以，是的，那些热衷于，嗯，是的，性能，我说是模型性能，包括能力和字面上的延迟，以及模型的评估。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, I think um generally the the making models very efficient, right? because we have to run on actual vehicles like physical AI is literally uh it's taking like very large AI and now making it very small and very efficient and uh and so we're constantly just at that boundary of these limitations of like well you can have a great model but now we need to make it faster and smaller and and so that that in general as a as a field and then I would say also um uh folks that are just really passionate about uh evaluating this technology as in like model eval um is is a hugely difficult topic especially in safety critical systems and um uh I mean we we have a a really great engineering team that works on this now and and and researchers but it's it's a big area of investment and so yeah folks that are passionate about um yeah performance I I say model performance both in terms of capability and and literally latency and then evaluation of models.

</details>

**主持人**: 棒极了。我想，有什么具体的工程职位正在招聘吗？特别是，什么样的工程师在你们公司会成功？我认为这始终是最重要的事情。

<details>
<summary>Original English</summary>

**Host**: Awesome. I guess any uh specific engineering roles that you're hiring for and especially like who are people that succeed at your company as engineers? I think that's always the most important thing.

</details>

**Kasar Younes**: 是的，我的意思是**fly.co/careers**。我认为字面上有数百个职位。呃，我们正在关注我们讨论过的所有主题，从**开发工具**和**物理AI**到**操作系统**再到**自动驾驶**以及**物理机器中的AI**。工程师的类型，这是一个很好的问题。实际上比职位更有趣，因为我们，你知道，我们是一家大公司，我们无所不包。是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, I mean fly.co/careers. I think there's literally hundreds of roles. Uh we're looking at all the topics we talked about from, you know, dev tooling and physical AI to operating systems to autonomy and and and and AI uh within physical machines. The types of engineers, that's a great question. actually more interesting than than the roles because we're you know we're a large company where we everything we are everything. Yeah.

</details>

**Peter Lewig**: 我想，你知道，我们是一家**Sunnyvale**公司，嗯，我认为从这次谈话和我们的背景中，你大概可以预测这意味着什么。呃，你知道，我们倾向于招聘相当认真的人，嗯，他们理解**底层系统**，而不仅仅是对技术有肤浅的理解，呃，就像工程师中的工程师一样。我们肯定也招聘具有多元技能的人才，我们招聘大量的专家，非常明确地说，但他们见过生产环境，我认为这确实决定了你如何构建技术。

<details>
<summary>Original English</summary>

**Peter Lewig**: I think you know we're a sunny veil company and um I think just from this conversation and kind of our backgrounds you can kind of predict a little bit of what that means. uh you know we tend to hire fairly serious people um who are who understand low-level systems not just just like a a superficial understanding of technology uh like engineers engineers almost we definitely hire folks who are uh like have some diverse skill sets we hire tons of specialists as well to be very very clear but they've seen production and I think that cuz that really informs how you how you build technology

</details>

**Peter Lewig**: 是的，那些真正欣赏**硬件软件边界**的人。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, people that really appreciate the hardware software boundaries.

</details>

**Kasar Younes**: 是的，没错。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, exactly.

</details>

**Kasar Younes**: 当然，在**Vibe Coding**时代，有一批工程师，他们根本不考虑硬件，而我们没有那种奢侈。所以，那些对深入一点更有热情的人。

<details>
<summary>Original English</summary>

**Kasar Younes**: Definitely in the vibe coding era there there are a crop of engineers that they don't think about hardware at all and we don't have that luxury and so people that are a little more passionate about going a little bit deeper.

</details>

**Peter Lewig**: 是的。如果你把我们和，你知道，AI实验室之类的东西对比，那就是你会得到最大的对比，那就是我们只是在处理现实。我的意思是，还有什么？所有那些经典的东西，你知道，你想要那些努力工作，热爱技术的人，就像这样的播客一样。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. If you're to contrast us versus like a you know AI lab or something that's where you're going to get the biggest contrast which is like we're just dealing with with reality. I mean, what other things all the classic stuff, you know, you want you want folks who work hard and who are uh who love the technology and like like a podcast like this or

</details>

**Kasar Younes**: 如果你听到了播客的这一部分，你可能已经符合条件了，你对此感兴趣。

<details>
<summary>Original English</summary>

**Kasar Younes**: like if you made it to this part of the podcast, you probably qualified for you're interested in this.

</details>

**主持人**: 是的。**Peter**也说他喜欢这个播客，这就像他。具体来说，在**硬件软件边界**部分，这是我一直在思考我们教育系统的问题，嗯，在美国，但可能也普遍如此，我觉得有一种远离传统计算机科学或工程教育的趋势。

<details>
<summary>Original English</summary>

**Host**: Yeah. And and Peter said that he likes the podcast as well, which is like him. specifically on the hardware software boundary part is it's something I think about of our education system um in the states but also maybe just in gerally I feel like there is that retreat away from that classical computer science or e education

</details>

**Kasar Younes**: 工程，或者，是的。

<details>
<summary>Original English</summary>

**Kasar Younes**: engineering or yeah

</details>

**主持人**: 是的。就像，有没有一个时间点，你只是自己动手？就像，你知道，在这一点上，你们是这方面的世界专家，实际上你不应该等待某个大学系统来培养他们。

<details>
<summary>Original English</summary>

**Host**: yeah and like is there a point where you just do it yourself like you know because at this point you guys are the world experts on this and actually you shouldn't wait for some college system to spit them out for you

</details>

**Peter Lewig**: 你是指在教育和**技能提升**方面吗？是的，就像，直接获取。

<details>
<summary>Original English</summary>

**Peter Lewig**: you mean in terms of education and upskilling kind of Yeah, just just grab like

</details>

**Kasar Younes**: **通用汽车**已经做到了。**Smart GMI大学**。

<details>
<summary>Original English</summary>

**Kasar Younes**: General Motors already did it. Smart GMI University.

</details>

**Peter Lewig**: 是的，我本科就是在那上的。我去了**通用汽车学院**。呃，

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah, that's where I went for undergrad. I went to the General Motors Institute. Uh,

</details>

**主持人**: 好的。我没有注意到。我看到了**HBS**。

<details>
<summary>Original English</summary>

**Host**: okay. I that did not come out. I saw HBS.

</details>

**Peter Lewig**: 是的。是的。每个人都看到了**HBS**，**哈佛**的品牌影响力很高。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. Yeah. Everyone sees HBS the the Harvard brand at Lewis is is high.

</details>

**主持人**: **通用汽车学院**是什么样的？

<details>
<summary>Original English</summary>

**Host**: What was General Motors Institute like?

</details>

**Kasar Younes**: 呃，它在100年前就开始了，就是为了回答你刚才说的这个问题。字面上就是你刚才说的问题，那就是密歇根没有足够的工程师。呃，你知道，你正在谈论现代公司**通用汽车**的早期。有一本很棒的书，**Alfred Peace Loans**的《我在通用汽车的岁月》，强烈推荐，它基本上谈论了现代公司是如何形成的，但其中一部分是他们说：我们基本上缺乏工程师，所以他们创办了一所学校。事实上，即使是**Google**，在大约10年前，也考虑过在内部创办一所大学，当时也有过讨论。所以，是的，我们绝对会提升人才。我们**THR**部门的培训量实际上是惊人的。是的。但当你达到我们这个规模时，这是一种奢侈。当你只有25名工程师时，你只能努力生存。

<details>
<summary>Original English</summary>

**Kasar Younes**: Uh, it started 100 years a to answer this exact question. Literally the question you just said, which is like not enough engineers in Michigan. uh you know you're talking about the early days of the modern corporation General Motors being there's a great book Alfred Peace Loans uh my years with General Motors uh that is highly recommended which basically talks about what becomes a modern corporation but a part of that is they're like we are we're basically buffering on engineers so they started a school and actually even Google as as as most as recent as probably 10 years ago was thinking of starting a university internally there was discussions on it so yeah it was absolutely we we definitely up I We definitely upscale folks as well. The amount of training we do in THR is actually surprising. Yeah. But it's a luxury you have when you're at our size. When you're like 25 engineers, you just got to survive.

</details>

**主持人**: 所以，再说一次，采纳与你公司相关的建议，而不是立即开始尝试培养高中生，让他们变得优秀，你知道，我上过你教的一节课，因为听起来你教的东西很多。

<details>
<summary>Original English</summary>

**Host**: So again, take advice that's relevant for your company rather than like immediately start trying to take high schoolers and make good, you know, I I did go to a class that that you taught because like it sounds like you can teach a lot.

</details>

**Peter Lewig**: 是的。所以我认为老实说，现在这些大型模型最棒的用例之一就是**教育**，对吧？就像我，我曾经有一个非常优秀的工程师，航空航天工程背景，在相对较短的时间内，他凭借这些模型的帮助，完成了非常自信的**前端工作**，非常自信的**后端工作**。而且你不仅可以用它们来完成实现，还可以学习，对吧？就像你问问题，你不会觉得尴尬，因为模型不会责怪你。

<details>
<summary>Original English</summary>

**Peter Lewig**: Yeah. So I think honestly the one of the most amazing use cases of these large models now is education right like I I've I've taken an engineer who uh very good engineer aerospace engineering background and in a relatively short time time span like he's doing very confident front end work very confident backend work like with the help of these models and like not only can you do implementation with them but you can also just learn right it's like you ask questions and you don't feel embarrassed because the model's not going to model's not going to call you out on Hey.

</details>

**主持人**: 是的。我认为你可能需要的不仅仅是工程学位，尽管工程学位非常重要，就像我，我，我不知道有没有办法捷径学习**流体力学**或**热传递**这些基础知识。

<details>
<summary>Original English</summary>

**Host**: Yeah. I think I think the thing you probably need more than an engineering degree though engineering degrees are like very important like I I I don't know if there's a way to shortcut like fluid dynamics or heat transfer the fundamental stuff.

</details>

**Peter Lewig**: 这些基础知识，呃，至少在机械方面，你需要**工程思维**，而这有时并非每个人都具备。有些人情感上更倾向于艺术或其他事物，这完全没问题。这里没有评判。但我认为工程思维，也许更实用地说，是渴望理解更底层、更底层、更底层的东西，比如**光子是如何运动的**？

<details>
<summary>Original English</summary>

**Peter Lewig**: The fundamental stuff uh at least on the mechanical side is you need an engineering mindset and that sometimes is actually not everybody actually has that. Some people are emotionally drawn towards the arts or something else and it's completely fine. There's no judgment there. But I think the engineering mindset maybe in a more usable way is like wanting to understand a lower level and a lower level and the lower like like how do photons move?

</details>

**主持人**: 极度好奇心。

<details>
<summary>Original English</summary>

**Host**: Extreme curiosity

</details>

**Peter Lewig**: 极度好奇心。就像，光是什么？**无线电波**是什么？这些真正基础的问题。

<details>
<summary>Original English</summary>

**Peter Lewig**: extreme curiosity like what is light? What is a radio wave? Like these really fundamental questions,

</details>

**主持人**: 对吗？如果你对软件足够好奇，最终你会接触到硬件，对吗？

<details>
<summary>Original English</summary>

**Host**: right? If and if you get curious enough about software, you ultimately end up in hardware, right?

</details>

**Kasar Younes**: 所以那是**Alen K**。是的。是的。没错。所以我正在尝试做类比，然后做所有这些事情，就像，你知道，你有点像是新**通用汽车**和**特斯拉自动驾驶部门**的混合体，对其他人来说。

<details>
<summary>Original English</summary>

**Kasar Younes**: And so that's the Alen K. Yeah. Yeah. Exactly. So I'm trying to make analogies and then do all these things like you know you're kind of a blend between new General Motors and Tesla autonomy division for everyone else.

</details>

**Peter Lewig**: 我的意思是，呃，你知道，我们曾经涉足所有这些其他领域。我想如果你和我们的卡车客户交谈，他们甚至不会觉得，你知道，他们可能觉得，哦，你们做了一些汽车方面的工作，但你们真的在帮助我们。

<details>
<summary>Original English</summary>

**Peter Lewig**: I mean uh you know we were in all these other fields. I think if you talk to our trucking customers they wouldn't even think perceive you know they like some sense like oh you guys did some automotive stuff but you're you're really helping us. So

</details>

**主持人**: 汽车不是卡车。

<details>
<summary>Original English</summary>

**Host**: automotive is not trucking.

</details>

**Peter Lewig**: 不不，是的。是的。它们是分开的。有不同的问题。你有公路和越野两大类。我想你正在考虑的是这个。所以有公路和越野。呃，但在公路范围内，有所有这些机器的子类别。特别是当你谈论，你知道，当你看到一个没有人类的送货机器人时。这实际上非常不同，因为现在你不必关心你在**自动驾驶系统**中驾驶时的实际感受。你不需要考虑这一点。你可以

<details>
<summary>Original English</summary>

**Peter Lewig**: No no that's Yeah. Yeah. It's it's separate. There's different problems. The masses you have you have the general categories of onroad and off-road. I think that's what you're thinking. So there's onroad and off-road. Uh but within on-road there's all these sub subasses of machines. Especially when you talk about, you know, you know, you look at uh a delivery robot that doesn't have a human in it. That's actually very different because now you're not concerned with like the actual feeling that you have when you're in a self-driving system. You don't have to account for that. You can

</details>

**Kasar Younes**: 你可以猛踩刹车，你不关心顿挫和所有这些指标，这些指标变得非常疯狂。呃，老实说，思考它的方式有点像，呃，任何你需要特殊训练才能操作的系统，你可以稍微不同地思考。所以，操作卡车的许可证与操作汽车的许可证不同，操作飞机的许可证也不同，你懂的。

<details>
<summary>Original English</summary>

**Kasar Younes**: you can you can break hard and you don't care about jerk and all of these metrics are become become insane. Uh the way to think about it honestly is a little bit like uh any system that you as an as a human would need special training to operate, you can think of a little bit differently. So like the license to operate a truck is different from the license to operate a car which is different from the license to fly a plane is different from you get it right.

</details>

**主持人**: 各位，非常感谢你们抽出时间。

<details>
<summary>Original English</summary>

**Host**: Awesome guys. Thank you for taking the time.

</details>

**Kasar Younes**: 是的，谢谢邀请。谢谢。

<details>
<summary>Original English</summary>

**Kasar Younes**: Yeah, thanks for having us. Thank you.

</details>