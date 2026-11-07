---
author: a16z
date: '2026-03-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YAyYCdCkwo4
speaker: a16z
tags:
  - flat-organizations
  - decision-velocity
  - critical-path
  - vertical-integration
  - factory-mindset
title: 特斯拉与SpaceX如何赋能硬件创业公司：前员工的经验分享
summary: 本访谈邀请了SpaceX前星舰推进工程师Chandler Lugjitsa和特斯拉前电池供应链负责人Turner Caldwell，分享他们在特斯拉和SpaceX学到的关键经验，以及如何将这些经验应用于各自的硬件创业公司Galedai和Mariana Minerals。讨论涵盖了扁平化组织、快速决策、关键路径管理、工厂思维、战略性垂直整合和人才招聘等核心原则。两位创始人强调了使命一致性、消除内部摩擦和建立强大技术基础的重要性，为年轻工程师和硬件创业者提供了宝贵建议。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Tesla
  - SpaceX
  - Galedai
  - Mariana Minerals
products_models:
  - Starship
  - Dragon
  - LLMs
media_books: []
status: evergreen
---
### 开场与公司介绍

**Chandler Lugjitsa**: 我曾四次进入**SpaceX**。我无法离开。那就像是我的梦想。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I entered into SpaceX four times. I couldn't leave. Like it was the dream.

</details>

**Turner Caldwell**: 我在**Tesla**工作了大约十年，负责电池供应链。

<details>
<summary>Original English</summary>

**Turner Caldwell**: I spent about a decade at Tesla and got to run around the battery supply chain.

</details>

**主持人**: **Chandler Lugjitsa**是**Galedai**的CEO，该公司致力于下一代导弹推进系统。**Turner Caldwell**是**Mariana Minerals**的CEO，该公司专注于关键矿物供应链。当**Elon Musk**设定超激进的目标时，目标实际上是让团队进行非常审慎的思考。有上千件事需要完成，但其中一百件不可能在六个月内完成。所以，我们必须去攻克那一百件事。对于导弹行业来说，我有点陌生，我意识到我们没有足够的导弹，它们成本太高，而且我们制造得不够快。凭借我在**SpaceX**甚至**UCLA**纯粹从事液体推进系统和发射液体火箭的背景，这是一种非常实际的方式，可以将这项技术应用于导弹系统，我们正在着手去做。

<details>
<summary>Original English</summary>

**Host**: Chandler Lugjitsa is the CEO of Galedai, next generation missile propulsion. Turner Caldwell is the CEO of Marian Minerals, critical mineral supply chains. When Elon sets super aggressive targets, the goal is actually to get the team to think really deliberately. There's a thousand things that have to happen, but a hundred of them cannot be done in 6 months. So, we have to go attack those 100 things. Being somewhat foreign to the missile industry, I realized we don't have enough. They cost too much and we can't make them fast enough. With my background being purely liquid propulsion across SpaceX and even at UCLA launching liquid rockets, is a very real way to apply this technology to miss systems and you go do it.

</details>

**主持人**: 你在**SpaceX**或**Tesla**学到的最重要的一件事是什么，现在每天都应用到你的公司中？

<details>
<summary>Original English</summary>

**Host**: What is the single most important thing that you learned at SpaceX or Tesla that you now apply every single day at your companies?

</details>

**主持人**: 如你所知，我花了很多时间与在实体世界中创业的创始人交流，有一个问题不断出现，那就是他们中有多少人曾在**Tesla**和**SpaceX**接受过培训。人们谈论神话、通宵工作、**扁平化组织**或不可能的截止日期。最好的部分是没有部分。但是，除了这些神话之外，还有一些可重复的实践，它们改变了团队构建和交付复杂硬件的方式。**Chandler Lugjitsa**是**Galedai**的CEO，致力于下一代导弹推进系统；**Turner Caldwell**是**Mariana Minerals**的CEO，专注于关键矿物供应链。**Chandler**曾是**Starship**的首席推进工程师，**Turner**曾领导**Tesla**的电池、矿物和金属业务。所以，很高兴你们能来这里谈谈在**Elon Musk**学校的经历。也许我们从头开始，简单介绍一下你们公司的起源故事，你们发现的问题，你们构建的第一个原型或试点，以及你们意识到这可以成为一项真正业务的时刻。**Chandler**，我们从你开始。

<details>
<summary>Original English</summary>

**Host**: As you know, I spent a lot of my time with founders building in the physical world and one thing that keeps coming up is how many of them trained at Tesla and SpaceX. People talk about the mythology, the all-nighters, the flat or the impossible deadlines. The best part is no part. But beyond the myths are repeatable practices that change how teams build and ship complex hardware. Chandler Lujitza is the CEO of Galedine, next generation missile propulsion, and Turner Caldwell is the CEO of Mariana Minerals, critical mineral supply chains. Chandler was the lead propulsion engineer on Starship. Turner led battery and min battery minerals and metals at Tesla. So it's really great to have you guys here to talk about your experiences in the school of Elon Musk. Maybe to just kick off, maybe start at the beginning, briefly tell us the origin story of your companies, the problems you saw, the first prototype or pilot you built, the moment you realized that this could be a real business. Chandler, let's start with you.

</details>

**Chandler Lugjitsa**: 是的，我想，直到去年夏天我才进入导弹行业，当时我刚跳进去，就意识到我们没有足够的导弹。它们成本太高，而且我们制造得不够快。而且似乎行业里的每个人都还在用老一套的方式做事。我认为，为了获得截然不同的结果，你必须采取截然不同的做法。所以，凭借我在**SpaceX**以及甚至在**UCLA**纯粹从事液体推进系统和发射液体火箭的背景，这是一种非常实际的方式，可以将这项技术应用于导弹系统，我们正要着手去做。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I think being somewhat foreign to the missile industry until the summer of last year, right as I jumped into it, I realized we don't have enough. They cost too much and we can't make them pass enough. And it seemed like everyone in the industry is kind of doing it the same old way. And I think, you know, in order to get drastically different results, you have to do things drastically differently. So, with my background being purely in liquid propulsion across SpaceX and then even at UCLA launching liquid rockets, there's a very real way to apply this technology to missile systems and we're going to go do it. So,

</details>

**主持人**: 太棒了。**Turner**，你呢？

<details>
<summary>Original English</summary>

**Host**: Awesome. What about you, Turner?

</details>

**Turner Caldwell**: 是的，我在**Tesla**工作了大约十年，负责电池供应链。最近，我花了很多时间在矿物和金属方面。我们关注的重点是如何消除供应链中这部分的瓶颈，并确保电池所需的矿物能够跟上电池生产的速度。与**Chandler**所说的类似，这是一个主要参与者都有五十年到一百年历史的行业。这种做事方式，像那些大型且保守的公司，确实根深蒂固。所以，当我们与这些公司合作，以及我们在**Tesla**构建该领域的基础设施时，一个非常明显的问题是，这个行业严重缺乏软件。当你尝试构建这种基础设施时，出现的许多挑战是协调层和编排层的问题。如何管理一个大型复杂的精炼厂，而人才库却在萎缩？如何管理大型复杂的采矿作业，同样是在人才库萎缩的情况下？我们最终得出的结论是，你必须全力以赴，利用汽车和人形机器人领域自主技术的进步，将其应用于精炼厂和采矿作业。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, so, I spent about a decade at Tesla and got to run around the battery supply chain. Most recently, I was spending a lot of time on the minerals and metals side of things. And a lot of our focus was trying to identify how do we debottleneck that part of the supply chain and make sure that the minerals that batteries need could keep up with battery production. And similar to what Chandler was saying, this is an industry that the major players are 50 to 100 years old. And that way of doing things, companies like that that are large and conservative really gets set in that way of doing things. And so as we were engaging, or as I was engaging with those companies and as we were building infrastructure in that space at Tesla, what became very apparent is that the industry is massively software deficient and a lot of the challenges that come out of or come up when you're trying to build this infrastructure is the coordination layer, the orchestration layer. How do you manage a large complex refinery with a talent pool that is shrinking? How do you manage large complex mining operations again with a talent pool that's shrinking? And what we've landed on is that you have to go full bore kind of like leveraging the advances in autonomy in automotive and humanoid robots to go and apply that to refineries and to mining operations.

</details>

### 扁平化组织与决策速度

**主持人**: **Tesla**和**SpaceX**的文化有很多神话。抛开那些流行词，你在**SpaceX**或**Tesla**学到的最重要的一件事是什么，现在每天都应用到你的公司中？

<details>
<summary>Original English</summary>

**Host**: So there's so much mythology around Tesla and SpaceX culture. Maybe forgetting the buzzwords, what is the single most important thing that you learned at SpaceX or Tesla that you now apply every single day at your companies?

</details>

**Turner Caldwell**: 我认为**扁平化组织**至关重要。你需要信息尽可能快地流动。你需要**民主化信息获取**，这才是**扁平化组织**的真正目的。这并不是说如果你错误地实施**扁平化组织**，它不会变得混乱。**扁平化组织**的目的是关于信息流动和协作。所以，任何初级工程师都应该能够在任何时候直接与任何高级成员或任何执行团队的成员交谈，并与公司内部的团队协作，而无需通过经理层层传递信息。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, I think the flat orgs is hyper critical, right? You need information to flow as quickly as possible. You need to democratize access to information and that's really the purpose of flat organizations. It's not because if you do flat organizations wrong, it can get chaotic, right? The purpose of flat organizations is really about information flow and collaboration. And so any junior engineer should be able to go to any senior member of any executive team at any point in time and talk directly to folks that are making decisions as well as collaborate with teams that are within the company kind of without having to funnel information through managers and then back down into their teams.

</details>

**Turner Caldwell**: 所以这非常关键，也是我们构建公司的一个重要部分。

<details>
<summary>Original English</summary>

**Turner Caldwell**: So that's hypercritical and is a big piece of how we've been building the company.

</details>

**主持人**: 我不知道你是否想插话。

<details>
<summary>Original English</summary>

**Host**: I don't know if you want to jump in.

</details>

**Chandler Lugjitsa**: 是的，我来插话。我认为这的另一个部分，也许是使其成功的一个部分，至少从我的经验来看，是你在**扁平化组织**中需要能够非常迅速地做出决策的领导者。我认为**决策速度**，不使用流行词来说，非常非常重要。拥有高度信念的领导力，能够做出强有力的决策，你会加快开发速度，加快生产周期，一切都会变得更快。即使从载人航天的角度来看，有很多风险。通过拥有高信念的领导者，他们也能在那个领域做出非常快速的决策，这有助于减轻低级别、更初级工程师的许多风险，真正让他们能够快速行动。如果你有一个刚开始在**SpaceX**或**Tesla**工作的初级工程师，他们担心自己正在做出一个疯狂的重大决策，这将花费数十万、数百万美元，如果我搞砸了怎么办？如果一个领导者能够通过直接做出决策并说“去做吧”来消除初级工程师的担忧，那么你就会快得多。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I'll jump in. I think another part of that, maybe a part of making that successful, or at least in my from my experience, is you need leaders across that flat org that are able to make decisions really quickly. I think decision velocity, without using a buzzword, is very, very important with high conviction leadership who can make strong decisions, you increase the pace of development, increase of production cycles, everything goes faster. Even from a like flying people to space perspective, you know, there's a lot of risk, right? And by having, you know, high conviction leaders who can go make really fast decisions in that space too, it helps absolve a lot of risk from the lower level, more junior engineers, it really just lets them go fast. Like I think if you have a junior engineer who's just now starting out a SpaceX or a Tesla, and they're like worrying themselves, oh, I'm making this crazy big decision, it's going to cost hundreds of thousands of dollars, millions of dollars, like what if I mess up? If a leader can come in and remove that concern from the junior engineer's mind by just making a decision and saying go, then you go way, way faster.

</details>

**Turner Caldwell**: 你不能等到所有信息都可用才做决定，对吧？很多时候，你只有在做出决定、尝试过之后，然后迅速迭代，才能知道这个决定是否正确。你不会总是做出正确的决定，但你总是试图最大限度地提高你做出正确决定的百分比。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Like you can't wait to have all of the information available to make decisions, right? And often times you won't find out if a decision is correct or not until you've made it, tried it, and then iterated really quickly on, you know, you're not always going to make the right decision, but you're always just trying to maximize your percentage that you did make the right decision.

</details>

**Chandler Lugjitsa**: 这都是赌注。这都是在下赌注。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: It's all bets. It's all making bets.

</details>

**Turner Caldwell**: 是的，没错。但是速度就是速度，以及执行的卓越性。这些是两件事。

<details>
<summary>Original English</summary>

**Turner Caldwell**: It is. That's right. But speed is speed and like excellence and execution. Like those are the two things.

</details>

**主持人**: 我的意思是，我想你需要这些信息才能做出决策。

<details>
<summary>Original English</summary>

**Host**: I mean, I guess and you need that information in order to be able to make decisions.

</details>

**Turner Caldwell**: 你需要在你给自己设定的时间内尽可能多地积累信息，然后做出决定，再从那个决定中学习。

<details>
<summary>Original English</summary>

**Turner Caldwell**: You need you need to accumulate as much information as you can within the time that you kind of like constrain yourself to and then make the decision and then learn from that decision.

</details>

**主持人**: 是的。然后融入新的信息，我想。

<details>
<summary>Original English</summary>

**Host**: Yeah. And incorporate that new information, I guess.

</details>

### 克服协作与信息孤岛挑战

**主持人**: 你们都对技术细节非常了解。你们都是工程师，现在是公司的CEO。你们在**Tesla**和**SpaceX**的先前职位中，有哪些经验或教训直接改变了**Galedai**和**Mariana Minerals**的结果或你们的思考方式？

<details>
<summary>Original English</summary>

**Host**: You're both pretty deep in the technical weeds. You're both engineers now CEOs of companies. What lesson or experiences did you have in your previous roles at Tesla and SpaceX that maybe directly changed an outcome or how you thought about things at Galadine and Mariana?

</details>

**Turner Caldwell**: 解决离散的技术问题很难。在很多情况下，你解决的是首创的问题。但要让一大群人一起努力解决这些首创的问题，这才是问题开始出现的地方。是的，在团队之间，即使你尝试快速、加速决策，即使每个人都在互相交流，你也需要确保方向一致。

<details>
<summary>Original English</summary>

**Turner Caldwell**: The solving like the discreet technical problems that is hard. You're you're solving kind of first of a kind problems in many cases. But then getting large groups of people to work together towards solving those first of a kind problems actually starts to like that's where the churn starts to appear. Yeah. Between teams and and even if you try to have fast you know accelerated decision-making, even if you have everyone talking to each other, you need to make sure that the vectors are aligned.

</details>

**Turner Caldwell**: 每个人都朝着同一个方向，朝着同一个目标努力。这也是为什么我们在构建**Mariana Minerals**时，一直专注于如何**民主化信息获取**，以避免实体之间形成**数据孤岛**。这在10、20、30人的团队中不会发生，但一旦团队达到100人或更多，就会开始出现。当看到那些试图构建大规模基础设施的团队的增长时，那些信息孤岛和**数据孤岛**确实会自然形成，即使执行团队说不应该有信息孤岛。所以我们试图将其嵌入到核心操作系统中。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And everyone is kind of working in the same direction towards the same thing. And that's a big part of why, as we've been building Mariana, we've been focusing on like how do you democratize access to information between teams so that you avoid kind of data silos that form between entities. And that doesn't really happen in teams of like 10, 20, 30 people. But it does start to happen once you get into teams that are 100 people or more. And seeing that like growth of teams that are trying to build large scale infrastructure, those those pockets of information and those data silos really do form naturally even if like the executive teams are saying like there should be no pockets of information, there should be no data silos. And so we've tried to like embed that into like the core operating systems.

</details>

**主持人**: 是的。那么，你们是如何围绕这个挑战构建产品和系统的呢？

<details>
<summary>Original English</summary>

**Host**: Yeah. So, how do you like how have you built kind of your product and systems around that challenge?

</details>

**Turner Caldwell**: 所以，所有东西都托管在网络应用程序上。访问控制基本上已经消失了，至少在公司内部是这样。当涉及到查看核心工程信息时，它不会存储在某个硬盘上，也不会存储在发送给特定人群的电子邮件中，需要转发才能让所有人看到。我们真正专注于构建集成的数据框架，使任何人都能访问并查看决策的原因或做出了什么决策的背景。因为随着团队规模的扩大，人与人之间的连接数量实际上是使项目执行变得困难的原因。

<details>
<summary>Original English</summary>

**Turner Caldwell**: So, everything is like web app hosted. Their access controls are basically gone, at least internal to the company. When it comes to being able to see like the core engineering information, it does not live on a hard drive somewhere. It does not live in an email that gets sent to a specific group of people and that needs to be forwarded for it to get to everyone. We've really focused on like building that integrated data frame that enables anyone to access and see the context of like why a decision was made or what decision was made. Because as the teams get larger, the number of connections between people is what actually makes building executing projects hard.

</details>

**Turner Caldwell**: 所以你必须**民主化信息获取**。你知道，像EPC（工程、采购、施工）这样的大规模资本项目执行，工程团队、采购团队和施工团队之间存在着巨大的**数据孤岛**。所以你必须构建一个全新的操作系统。它确保每个单独决策的历史都被跟踪，并且每个人都能看到这个历史。现在有了**LLMs**，你可以让它们在你的数据仓库上自由运行，并确保如果有人不理解文件夹结构，他们可以查询**LLM**并快速导航到他们需要去的地方。采矿基本上是一个理想情况下永不结束的漫长建设项目。所以它在地质、矿山规划、维护、矿山运营和加工设施之间存在许多相同的挑战。再次强调，如果你不给人们提供整个运营的背景，整个项目或运营中所有决策的背景，他们就会根据他们可用的数据做出信息决策。所以你试图让每个人都能做出全局最优的决策，同时加速决策。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And so you have to democratize access to that information. And so you know EPC like engineering, procurement, construction, like large scale capital project execution, there are insane data silos between the engineering groups and the procurement teams and the construction teams. And so you have to build like a net new operating system. That ensures that like the history of every individual decision is tracked and everyone can see that history. And now with LLMs, you can kind of like let them run wild on top of your data repository. And ensure that if someone doesn't understand the folder structure, they can just query the LLM and like quickly navigate to where they need to go. And then this, you know, mining is basically one long construction project that ideally never ends. And so it has a lot of the same challenges between like geology and mine planning and maintenance and mine operations and the processing facility. And again like if if you don't give people the context of an entire operation, the entire like all the decisions that are being made across an operation or a project, they're going to make information like within the data that they have available to them. So you're trying to enable like everyone to make like globally optimal decisions without again while accelerating decision-making.

</details>

**主持人**: **Chandler**，你呢？

<details>
<summary>Original English</summary>

**Host**: What about you Chandler?

</details>

**Chandler Lugjitsa**: 是的，我想我的答案是真正专注于**关键路径**。我认为追逐**关键路径**并扮演消防员的角色是**SpaceX**工程师，我想**Tesla**工程师也会做的事情。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I think I think my my answer here is is really focus on critical path. I think I think chasing critical path and being a firefighter is something that SpaceX and I would assume Tesla engineers do.

</details>

**主持人**: 你能解释一下那是什么吗？

<details>
<summary>Original English</summary>

**Host**: Can you can you explain what that is?

</details>

**Chandler Lugjitsa**: 当然可以。**关键路径**就是推动进度的因素。所以它实际上是推动进度的任务或采购活动，需要发生才能解锁下一个阶段或让你达到最终目标。虽然我们在**Galedai**还很年轻，但我们有很多追逐**关键路径**并不断玩“打地鼠”游戏的情况，以真正让自己进入下一个阶段或达到下一个里程碑。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Of course. Yeah, totally can. So critical path just being the thing that's driving schedule. So really the schedule driving task or or procurement activity that needs to happen in order to unlock the either the next phase or get you to the to the end goal. And although we are very young at Galadine, there's a lot of chasing critical path and playing this constant game of whack-a-mole to to really get yourself to that next phase or get yourself to that next milestone.

</details>

### 团队协作与关键路径管理

**主持人**: 那么，如何在不让当前**关键路径**之后的下一个决策花费更长时间的情况下，让团队与**关键路径**保持一致呢？这说得通吗？

<details>
<summary>Original English</summary>

**Host**: Then how do you align a team against critical path without making the next decision that comes after the current critical path take longer? Does that make sense?

</details>

**Turner Caldwell**: 我有一个想法，如果你去追求，你不能像二年级踢足球那样。有时如果你只狭隘地专注于**关键路径**方面的事情，就会有那种感觉。你知道，二年级踢足球基本上意味着每个人都围着球跑。

<details>
<summary>Original English</summary>

**Turner Caldwell**: I've got one if you go for the the you can't play like second grade soccer. Like that that is the that's like sometimes how it feels if you like are narrowly narrowly focused on the critical path side of things, right? And you know secondary grade soccer basically means that everyone like swarms the ball on the field.

</details>

**Turner Caldwell**: 所以你必须建立系统，让你能够调动核心团队去攻克**关键路径**，同时又不让下一个决策落后。这很大程度上在于拥有能够独立并行处理事务的小型**特警队**。或者并行处理事务，让你能够在不转移所有资源的情况下，让当前不在**关键路径**上的事情继续推进。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And so you have to you have to like set up you know systems that enable you to mobilize like core groups of teams to go after critical paths while also not letting the next decision kind of fall behind. And a lot of that is around having, you know, little SWAT teams that are able to like independently attack things that are in parallel. Or attack things in parallel that enable you to kind of keep the thing that is not on critical path right now still moving without like diverting all resources over.

</details>

**Turner Caldwell**: 我们就是这样思考的。

<details>
<summary>Original English</summary>

**Turner Caldwell**: That's how we think about it.

</details>

**Chandler Lugjitsa**: 这很容易，对吧？对于那些没有持续保持一致的人来说，很容易被炒作所吸引，因为它看起来会是城里最热门的事情，因为它就像“哦，哇，这真的阻碍了火箭发射，真的阻碍了生产线”，人们就会说：“哦，我想帮忙，我想帮忙。”这就像我们必须集中资源，这样你就对了，下一件事就不会真的成为**关键路径**，而不是永远不会。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: It's easy, right? It's easy for folks who who aren't getting constantly aligned to to kind of fall into the hype because it it is it will seem like the hottest thing in town whenever that's happening because it's like, oh wow, you know, this is literally blocking a rocket launch. Is literally blocking the production line and people are like, "Oh, I want to help. I want to help." It's like we got to focus resources so that you're right, the next thing doesn't actually become that critical path sooner rather rather than, you know, never. I suppose

</details>

**主持人**: 我想，特别是你，**Chandler**，**Galedai**还处于非常早期阶段。那么，你如何在内部管理这个问题？或者说，你们是否还处于只有一个**关键路径**的阶段？

<details>
<summary>Original English</summary>

**Host**: I guess though like as a especially you Chandler, I mean, Galadine is still very early. So, how do you you know, how do you manage that internally or are you still at the point where there really is just one critical path?

</details>

**Chandler Lugjitsa**: 我想肯定是后者。我们现在团队只有六个人，所以控制这个游戏相对容易。但是，这仍然非常重要，就像我们最初团队的结构是基于学科或领域。所以，让一个航空电子工程师去解决一个正在阻碍生产的发动机设计问题，可能意义不大。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I think the latter for sure like we we have right now our team is six people so it's it's relatively easy to to control that game. But but it's still very important like you know how how we've structured a lot of the initial team is is disciplinary based or or sort of domain based. So it may not make the most sense for a avionics engineer to go troubleshoot a engine design problem that's literally blocking the production of of said problem.

</details>

**主持人**: 那可能对**关键路径**没有帮助。

<details>
<summary>Original English</summary>

**Host**: That probably doesn't help with the critical path.

</details>

**Chandler Lugjitsa**: 确实没有。所以对我们来说，这稍微容易一些，但随着我们团队的快速壮大，我们肯定会非常关注不让它失控，因为那样会浪费大量资源。也许就实际或战术建议而言，你从**Tesla**和**SpaceX**带到你公司的一个具体流程或节奏是什么？

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: It doesn't. So for us it's a little bit easier but definitely top of mind as we as we grow the team really quickly to to not let it get out of control because you just waste a bunch of resources. Maybe in terms of like practical or tactical advice like what are what is a specific process or rhythm that you've brought from Tesla and SpaceX into your companies?

</details>

### 实用流程与节奏：邮件更新与公司节拍

**Chandler Lugjitsa**: 我可以先说这个。我认为我真正喜欢的一点，可能听起来有些反直觉，是电子邮件更新。我认为关于**关键路径**相关事宜的高信号、低噪音的电子邮件更新，对于向更广泛的人群提供信息来说，是极其重要的。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I can I can hop on this one first. I think the the thing that I really like and may sound counterintuitive potentially is is email updates. I think high signal low noise email updates on particularly with things related to critical path are are extremely important to do one you know give the information to a broader set of folks even.

</details>

**主持人**: 这些是您发给团队的电子邮件更新，还是团队发出的？

<details>
<summary>Original English</summary>

**Host**: And these are email updates from you to the team or from the team out.

</details>

**Chandler Lugjitsa**: 团队发给任何人。所以任何人，就消防团队而言，通常会有一个主要的负责人来推动那个问题或推动那个特定的任务完成。这个人要承担责任，并发送高频率的电子邮件更新，以度过问题中不那么好的部分，这不仅对团队看到和听到极其重要，而且我认为对于处理该项目的个人来说，回忆当天发生了什么并确保记录下来，也是极其重要的。没错。记录事情非常重要。我口袋里总是带着一个笔记本，我认为为了把这些写下来，让他们看到并思考：“我想我今天没有朝着目标取得最直接的进展。明天我们来解决这个问题。”

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Team out anyone. So anyone really to the point of the the the fire teams there's usually going to be one extreme owner who is driving that problem or driving that you know specific task to get it completed and for that person to take ownership and send you know high high cadence email updates to get through the not so good parts of said problem is is extremely important not only for the team to see and hear but I think it's actually wildly important for the individual who's working that project to recall what they what happened that day and make sure write it down. Exactly. Writing down things is freaking massive. I have a notebook in my pocket at all times and I think in order to get that out and for them to write it down, see it and be like, I don't think I made the most direct progress towards the goal in in this particular day. Let's fix it for the next day.

</details>

**Turner Caldwell**: 是的。其次，我认为，当你非常忙碌时，自然会发生一件事，那就是你没有时间写下东西和写报告。我们尝试做的是，当你在运行一个制造过程时，你每天都有一个班次交接，每天都会通过电子邮件发送出去。如果你想推动流程开发和研发，并将其视为一种制造型流程，那么最好的强制功能就是在一天结束时，你有一个相当于班次交接的东西，你会说：“这是我们今天做的，这是我们本应做的，这是我们为什么没有做本应做的事情。”

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah. Second, I think that, you know, there's a there there's like this natural thing that happens when you're very busy is that, you know, you don't have time to write things down and write reports. What what we've tried to do is, you know, the when you're running a manufacturing process right and you have like just a day-to-day operation, you have a pass down that happens between shifts that gets emailed out every day. And if you want to drive like process development and R&D towards thinking about it as a manufacturing type process, the the best forcing function is at the end of the day you have like the equivalent of a shift pass down which is you say here's what we did, here's what we were supposed to do, here's why we didn't do the things we were supposed to do and you know because.

</details>

**主持人**: 随着团队的壮大和事情的增多，这确实会变得很繁重。

<details>
<summary>Original English</summary>

**Host**: That does become burdensome from as like the team starts to grow and as there's a lot of stuff happening.

</details>

**Turner Caldwell**: 我们尽力做到，如果所有东西都进入同一个聚合的数据骨干，你实际上可以自动填充大部分的交接内容。这让人类处于一个位置，他们真正像是在审查交接。

<details>
<summary>Original English</summary>

**Turner Caldwell**: We've done our best to try to like if everything is going into the same like aggregated kind of like data backbone, you can actually autopop populate the bulk of those pass downs. And it puts humans in a position where they're really like reviewing a pass down.

</details>

**主持人**: 编辑，也许是添加评论，而不是从头开始写东西。

<details>
<summary>Original English</summary>

**Host**: Editing maybe adding commentary versus having to write something from scratch.

</details>

**Turner Caldwell**: 我们发现，即使在大型运营中，交接也是非常手动的。但是所有这些数据都在收集。所以，与其让某人坐下来，花一个小时的时间精确记录发生了什么，我们投入了大量精力来思考如何自动生成所有这些。但你仍然希望人们查看它。你仍然希望他们点击发送，因为他们应该对其中的内容拥有所有权和责任。我们尝试做的另一件大事是，这里有一个平衡点，你需要为公司设定一个“**公司节拍**”。如果你不为公司设定**公司节拍**，人们就不一定会知道他们正在朝着什么方向前进。这就是你如何利用**扁平化组织**并赋予它们一些结构的方式，每个人都知道决策将以某种节奏汇总，你显然必须灵活，因为会有一些极其关键的决策必须在当天做出。但你也希望为公司提供一些结构和节奏，使每个人都能有效地以相同的节奏前进。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And what we've found even in like large scale operations like the pass downs are very manual. But all that data is being collected and so instead of someone having to sit down and carve out an hour of their data to write down exactly what happened, we've we've put a ton of focus into like how do we autogenerate all those. But you still want people to look at it. You still want them to click send because like they should have ownership and accountability of like what is in it. The other big thing that we've we've tried to do it's like a balance here of like you need to set like a drum beat for the company. And if you don't set a drum beat for the company, people don't really know what they are moving towards necessarily. It's how you kind of take flat organizations and enable like give them some structure and everyone knows that decisions are going to roll up on some cadence and you obviously have to be flexible because there's going to be super critical decisions that have to happen the day of. But you also want to like give some structure and like a cadence to the company that enables everyone to kind of be moving in the same rhythm effectively.

</details>

**主持人**: 就像冲刺。我们尝试将冲刺保留给真正对公司至关重要的事情，软件工程组织显然以两周的冲刺周期运行。但如果我们有一个重要的里程碑要实现，我们就会将其称为冲刺，并说整个公司都在朝着这个目标冲刺。但**公司节拍**有点不同。这就像你正在构建大规模基础设施，这是一个12个月或18个月的项目。

<details>
<summary>Original English</summary>

**Host**: Like a sprint. Sprints we try to reserve for like truly critical to the company type things and the software engineering organization obviously runs in two week sprints. But if we're going to if we have like a major milestone that we're trying to hit like drive towards then we'll we'll coin that a sprint and say like look the company like as a whole is sprinting towards this thing. But the the drum beat is a little bit different. It's like you're because you're building if you're if you're if you're building large scale infrastructure the like it is a 12-month project or an 18-month project. And if you're.

</details>

**Turner Caldwell**: 是的。这与向云端发布软件不同，你可以每天发布一次。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah. This isn't the same thing as, you know, shipping software to the cloud where, you know, you can do a release cadence every day if you want.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Turner Caldwell**: 我认为很多人，那些整个职业生涯都在软件领域工作的人，很难在心理上想象在12到18个月的时间里从事某项工作意味着什么。

<details>
<summary>Original English</summary>

**Turner Caldwell**: I think that's what a lot of folks and it's it who who have spent their whole careers working in just software sort of it's hard to mentally imagine what it means to work on something over a 12 to 18 month period.

</details>

**Chandler Lugjitsa**: 这是一个漫长的周期。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: It it is a long cycle.

</details>

**Turner Caldwell**: 但**公司节拍**的目标也是给自己时间庆祝那些中间的胜利。因为在18个月的时间里，你很容易忘记自己取得了巨大的进步。当你回顾时，你会说：“哦，我们建造了这东西。太棒了。”但你必须，那个**公司节拍**也是团队的奖励功能，他们会说：“看，好吧，我做对了。我正在朝着正确的方向前进。”你会在某个固定的基础上获得这种校准。

<details>
<summary>Original English</summary>

**Turner Caldwell**: But like the also the goal of kind of the cadence is like give yourself time to celebrate those like intermediate wins. Because it's easy to like lose track of the fact that you're making a ton of progress over an 18 month period. Like you look back and you're like, "Oh, well, we built this thing. It's awesome." But you have to like that cadence is also like a it's the reward function for the team that they are saying like, "Look, okay, I'm doing the right thing. I'm driving towards the right thing." And you and you get that calibration on some regular basis.

</details>

**主持人**: 是的。**Chandler**，你如何考虑设定里程碑？

<details>
<summary>Original English</summary>

**Host**: Yeah. How do you think about setting milestones, Chandler?

</details>

**Chandler Lugjitsa**: 尽可能快。我不知道，我相信**Turner**对此也有一些看法，但总是有“**Elon时间**”，这通常是一个很难应对的问题。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: As fast as humanly possible. I don't know. There's I'm sure Turner has some impact of this, but there's there's Elon time always, and that's a that's a hard one to battle with usually. I think.

</details>

**Turner Caldwell**: 我肯定会倾向于在设定这些里程碑时采取这种做法。

<details>
<summary>Original English</summary>

**Turner Caldwell**: I definitely say I lean towards that in setting these very milestones.

</details>

**Chandler Lugjitsa**: 我现在已经很了解你了。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I know knowing you pretty well by now.

</details>

**Chandler Lugjitsa**: 是的。我真的会从这个角度去思考。幸运的是，在我的短暂而充实的职业生涯中，我接触过火箭的许多不同部分。我对事情应该花费多长时间有一个不错的判断。我认为，就这个**公司节拍**而言，但要提前做一些事情来让团队保持一致，比如：“嘿，我认为这些事情需要这么长时间。你作为将直接执行它的人，这听起来合理吗？”然后尽早解决这个问题，从一开始就设定好时间表。这就是我们所做的。我们都坐下来。我们设定了一个非常雄心勃勃的时间表，要在六月前让火箭升空。我们分解了需要做的事情才能实现这个目标。它们非常合理。如果我们开始偏离这条道路，那么你就会开始想：“出了什么问题？”

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah. I really try to think about it from Fortunately, I've been able to to touch a lot of different parts of of rockets over my short but jam-packed career so far. And and I have a decent gauge on on how long things should take. And I think sort of to the to the to the effect of this drum beat thing, but doing something sort of upfront to align the team to like, hey, this is what this is how long I think these things are going to take. You as the person who's going to go execute on it directly, like does this sound reasonable? And then battle it there early and then set that schedule from the get-go. Which is what we did. We all sat down. We set this very ambitious schedule to go get a rock in the air by June. And like we broke down the things we need to do to get there. And they're very reasonable. And if we start straying from that path, then you start to be like, what what's what's wrong?

</details>

**主持人**: 我的意思是，我想这就是为什么领导层中有技术人员真的很重要。

<details>
<summary>Original English</summary>

**Host**: I mean, I guess this is where having quite technical folks in leadership really matters.

</details>

**Turner Caldwell**: 是的，你必须有信誉。你必须有一个核心，你必须对什么是真正具有挑战性但又可实现的有感觉。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, you have to have like you're credible. You have to have like a core, you have to have a sense of like what is actually challenging but achievable.

</details>

**Turner Caldwell**: 设定超激进里程碑的目的，我认为每个人都应该这样做，是为了筛选出真正的**关键路径**。回到**关键路径**的评论，而不是说：“好吧，我以前做过这个。它应该需要36个月。”当**Elon**设定超激进的目标时，目标实际上是让团队进行非常审慎的思考，思考在那个激进的时间框架内什么行不通，什么实际上无法解决问题。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And like the purpose of setting super aggressive milestones, which I think everyone should do. Is it's meant to weed out like what the actual critical paths are. Going back to the critical path comment, of like instead of saying, "Okay, I I've done this before. It should take 36 months." When when Elon sets like super aggressive targets, the goal is actually to get the team to think really deliberately and very what doesn't work in that like what actually doesn't solve for the aggressive time frame.

</details>

**Turner Caldwell**: 然后它会给你一个优先级列表。就像，好吧，如果我们想在六个月内完成，有上千件事必须发生。其中900件事可以在六个月内完成，但有100件不能在六个月内完成，所以我们必须去攻克那一百件事。攻克也可以意味着删除它们。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And then it gives you your priority list. It's like okay there's a thousand things that have to happen if we want to do it in 6 months. 900 of those things can be done in six months but 100 of them cannot be done in six months and so we have to go attack those hundred things. Attack can mean delete them too.

</details>

**主持人**: 没错。把那些事情浮到最上面，然后砍掉。

<details>
<summary>Original English</summary>

**Host**: Exactly. Float those things to the top and they cut.

</details>

**Turner Caldwell**: 没错。

<details>
<summary>Original English</summary>

**Turner Caldwell**: That's right. Yeah.

</details>

### 避免团队倦怠与使命一致性

**主持人**: **Tesla**和**SpaceX**都以通宵工作、非常紧张的工作文化、长时间工作以及非常严格的截止日期而闻名，比如你试图在六个月内完成通常需要36个月的事情。在这种情况下，你们如何避免团队倦怠？

<details>
<summary>Original English</summary>

**Host**: Both Tesla and SpaceX are famous for, you know, all-nighters, like a very intense work culture, long working hours, like really these really hard deadlines where, you know, you're trying to do something in 6 months, which normally might take 36 months. How do you avoid kind of team burnout in those situations?

</details>

**Chandler Lugjitsa**: 这很大程度上取决于公司的**使命一致性**有多强。如果工作很有趣，就不会感觉像在工作。特别是对于那些与公司使命高度一致的人来说。显然，在**SpaceX**的案例中，让生命多行星化是一个了不起的使命，值得你全力以赴去实现。所以它让长时间工作、通宵工作变得不那么影响你。我认为我现在很大一部分精力都放在思考如何真正说服很多以前从未考虑过国防领域的人，让他们对国防充满热情。因为现实是，在我的案例中，**SpaceX**有那么多人才，**Rock Lab**、**Firefly**和**Relativity**也有那么多人才，他们也需要来解决这套问题。你知道，你如何建立**SpaceX**以及其他公司能够在其员工队伍中实现的同样炽热的**使命一致性**，现在在这些专注于“美国活力”的新问题领域，人们已经有一段时间没有涉足了。然后让这一切感觉像乐趣，而不是痛苦。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: A lot of this comes back to the to how mission aligned the company is or or how strong the mission of the company is. It's it doesn't feel like working if it's fun. And particularly for folks who are are so aligned with the mission of the company. Obviously in SpaceX's case, making life multilanetary, that's a fantastic mission to go stand behind and work your butt off to to achieve. So it makes it makes the long hours, the the overnight the all-nighters, it makes it so that they don't really impact you that much. And I think a large like a very high amount of thought on my end right now is going into, you know, how how do I really convince a lot of folks who haven't thought about defense before to be passionate about defense. Because the reality is is in in my case, there's so much talent that's living at SpaceX. There's so much talent living at Rock Lab, Firefly, and Relativity that need to come work this problem set too. You know, it's it's how do you how do you build that same fiery mission alignment that that SpaceX has been able to achieve and other companies have been able to achieve with their workforce now in these in these, you know, new American Dynamism focused problem sets that people just haven't been working on in a while. And then makes makes it all feel like fun and not like pain.

</details>

**Turner Caldwell**: 是的，**使命一致性**绝对是核心。我认为真正导致倦怠的是内部摩擦（churn），以及缺乏对目标取得进展的感觉。所以，如果人们正在为某个目标努力，并且他们觉得他们正在朝着目标前进，那么如果你的**使命一致性**很强，解决难题就会很有趣，只要你正在朝着那个目标取得进展。所以，有一些事情会让工作变得不那么有趣，比如内部摩擦可能来自不稳定的决策，这会让团队朝着不同的方向发展，尤其是在快速行动、非常灵活的初创公司中，总会有一点点这样的情况。但第二点是，公司内部的政治会产生巨大的内部摩擦。**数据孤岛**和我们所说的“囤积乐高积木”也会产生巨大的内部摩擦。当人们不得不处理这些问题，而无法专注于“好吧，我有一个问题需要解决，路径清晰，决策清晰，优先级清晰”时，他们就会全力以赴去做。是的。但这确实会破坏那种兴奋感，如果团队周围有事情正在偏离核心使命。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, the the mission alignment is definitely kind of like the core piece. I think the thing that actually causes burnout is churn. And like a lack of feeling like you're making progress towards a goal. And so if people are working towards something and they feel like they're actually like progressing towards it. And you know, if you're mission aligned, solving hard problems can be fun because you're as long as you are like making progress towards that goal. So there's a handful of things that can make like work not fun which is churn can come from like you know erratic decision that kind of like moves teams in different and there's always going to be a little bit of that especially in startup companies that are moving quick and being very nimble. But the second is like politics in companies creates an insane amount of churn. Data silos and kind of hoarding your legos is what we call it can create an insane amount of churn. And when people have to deal with that and aren't able to focus on like, okay, I have a problem that I have to solve, the pathway is clear, the decision is clear, the priorities are clear, they, you know, they'll work their butts off to go do it. Yeah. But it but it definitely it it destroys kind of like the excitement. If you have things that are around the team that are taking away from like the core mission.

</details>

**Turner Caldwell**: 所以人们可以对不可能的目标感到兴奋，因为我们要去证明它。是的，这就像人们真正感到兴奋的唯一事情，如果它感觉不可能。

<details>
<summary>Original English</summary>

**Turner Caldwell**: So the people can get excited about like impossible goals because we're going to go prove it. Yeah, it's like the only thing that people do really get excited about if it feels impossible.

</details>

**Turner Caldwell**: 但是，**Chandler**提到的另一件事是，只要你设定的目标是激进但可能的，它就必须在可能性范围内。那么，如果你设定的目标过于激进，而没有实际的技术路径去实现它，那也会令人沮丧。所以，这是一种混合，既要确保尽可能消除内部摩擦，又要确保你设定的目标是激励人心的，而不是令人沮丧的。

<details>
<summary>Original English</summary>

**Turner Caldwell**: But that's the other thing that Chandler mentioned which is like if as long as you're setting goals that are aggressive but are possible like that has to be like it has to be in the realm of possibility. Then you know it doesn't like if you go super super aggressive on targets that have no actual technical path towards towards achieving it the like that can be demoralizing also. So it's a mix of like making sure the churn is gone to the extent that you can and and making sure that you're setting goals that are motivating, not demoralizing.

</details>

### 需要“忘却”的原则：垂直整合的战略性

**主持人**: 是的。那么，反过来说，**Tesla**或**SpaceX**的哪些原则在你的新公司中不起作用，或者你可能需要“忘却”的模式，因为领域、公司规模或其他原因而不适用？

<details>
<summary>Original English</summary>

**Host**: Yeah. So maybe flipping it, what principle from Tesla or SpaceX has not worked for you in your new companies or patterns that you maybe needed to unlearn that didn't apply either because of the domain or because of the size of the company or something else.

</details>

**Chandler Lugjitsa**: 我认为一个有趣的点是，这并非选择不做，而是推迟实施。我在**Starship**工作时，以及在**Dragon**上也有一些，我确实运用了一件事，那就是**SpaceX**拥有强大的资源支持，你可以做很多很棒的事情。为了应对**关键路径**，有一些方法可能效率较低，但能实现目标。并行处理很多事情可能会消耗大量资源，包括时间和成本。我认为这是我们目前由于规模原因无法做到的事情，但我认为随着我们成长，为了达到速度，你需要做一切可能的事情。现在对我们来说，可能意味着快速成长，但这与**SpaceX**目前可能拥有的可能性集合不同。所以，我认为密切关注那个时间点，以便我们能够提高速度，一直在我脑海中。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I think a fun one that's it's it's not choosing not to do it, it's kind of delaying the implementation of but the one thing that that I definitely employed working Starship a little bit on Dragon as well is with with the fantastic resource that SpaceX has behind it, you can do a lot of fantastic things and you know in order to fight critical path there are ways to do that that maybe are less efficient I suppose but ways that will go achieve the goal. Parallel pathing a lot of things can be pretty resource intensive both on a time space but also on on cost and I think that's that's one thing that we are not able to do right now given our size but I think it's something that as we grow like in order to hit speed you need to do everything possible and and you know what what possible looks like right now for us is is growing very quickly but but is a different set of possibilities than maybe what SpaceX has right now so I think kind of uh really keeping an eye on on when that point is so that we can crank up the velocity even um has been in my mind.

</details>

**Turner Caldwell**: 是的。我不会说有什么特别的一点，至少在**Tesla**，它是一个我们不会模仿的核心原则。我宁愿说，这更像是对这些原则的实施进行调整，以解决内部摩擦、人员流动和倦怠等问题。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah. I wouldn't actually say that there's any like one pinpointed thing that like that at least at at Tesla at Tesla was you know a core principle that we wouldn't mimic. I would say that it's more like kind of massaging the implementation of those. That is to address some of the things like churn and turnover and burnout.

</details>

**主持人**: 嗯，我的意思是，你在**Tesla**的时候，公司规模增长了几个数量级。所以你看到了公司的两个非常不同的版本。所以我想，**Tesla**在达到10万人规模时的一些经验对你来说就不那么相关了。

<details>
<summary>Original English</summary>

**Host**: Well, I mean at at Tesla you you were there as the company grew in order of magnitude. So you saw two very different versions of the company. So I imagine you know some some lessons from when Tesla, you know, crossed 100,000 people are less relevant to you.

</details>

**Turner Caldwell**: 在早期，它显然更扁平，正如你所预期的，因为一旦你达到13万、14万人，你就必须开始分层一些结构。

<details>
<summary>Original English</summary>

**Turner Caldwell**: In in the early days the like it it was it was flatter obviously as you would expect cuz once you get to like 130 140,000 people you know you have to start to layer in some structure.

</details>

**主持人**: 我的意思是，你有大量的员工在工厂车间工作，他们较少参与设计决策。

<details>
<summary>Original English</summary>

**Host**: I mean you have massive you know groups of people who are working on factory floors who are less involved in design decisions.

</details>

**Turner Caldwell**: 是的。所以那些组织保持扁平化和灵活，直到今天仍然如此。但我认为没有任何原则，因为我实际上相信**Tesla**大部分的运作方式。我认为只是在过程中可以做一些小的调整，使团队的工作更具可持续性。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah. And so those organizations like stayed flat and nimble and still are to this day. But I I you know I I don't think there's any because like I I actually believe in a lot of in in most of kind of how Tesla was running. I think that the it's just there's like little tweaks that you can make along the way that that enable you to make it like more sustainable for the for the teams.

</details>

### 工厂思维与迭代：Starship和锂精炼厂

**主持人**: 那么，也许我们稍微换个话题，**Tesla**和**SpaceX**都以用**工厂思维**处理每个问题而闻名。你知道，一切都是一个工厂。**Turner**，你之前提到过，一切都归结为一个制造问题。所以我想谈谈这在实践中意味着什么。**Chandler**，也许从你开始。我们能谈谈**Starship**的迭代吗？从V1到V2到V3，你是如何平衡系统复杂性和生产率的？

<details>
<summary>Original English</summary>

**Host**: So um maybe switching gears a little bit, both test Tesla and SpaceX are famous for approaching every problem with this kind of factory mindset. Um, you know, everything is a factory. Everything, you you touched on it earlier, Turner, everything kind of boils down to a manufacturing problem. Um, so I want to talk a little bit about what that means in practice. Um, Chandler, maybe starting with you. Can we talk about iteration on Starship? So from V1 to V2 to V3, how did you balance system complexity and production rate?

</details>

**Chandler Lugjitsa**: 是的，我刚开始参与**Starship**项目时，大约是第三次飞行的时候。所以V1的全堆栈有一些参与，然后一直推动V2的开发周期，然后开始接触V3，并在我离开公司之前将其大致规划出来。我认为，对我们来说，这种权衡的真正核心，以及实现速度和**工厂思维**的关键，以及普遍的生产重点，就是需求。从设计方面来看，如果你能尽快地把所有听起来很愚蠢的需求都提炼出来，然后给自己一个机会把它们从等式中剔除，你现在就给自己留下了。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I when just to give some context, I whenever I started in the Starship program is around flight 3 time frame. So little bit of V1 play in terms of full stack. And then pushed all the way through the V2 development cycle and then started to touch V3 and and kind of lay that out before before I left the company. I think really what it what what this trade for us came down to is is and what enabled kind of the speed and thinking with um this this factory mindset is and really just production focus in general is requirements. Like from from the design side, if you can boil up all of the requirements that sound stupid as fast as possible and then give yourself a chance to whack them out of the equation, you you now leave yourself.

</details>

**主持人**: 比如什么？如果你能举个例子。

<details>
<summary>Original English</summary>

**Host**: Like what? Give me an example if you can.

</details>

**Chandler Lugjitsa**: 是的，有一个很有趣的例子。这有点深入细节，但我们有机会从**Booster**那里获取一些硬件。**Booster**在V3设计方面比**Ship**团队稍领先一些。他们为了**Booster**跳过了V2，直接从V1到V3。他们为V3飞行器设计了一些硬件，实际上可以很容易地插入**Ship**。我们工程师非常有限，无法设计大量的推进系统硬件。我们发现，哦，我们也许可以使用这个。我们很早就把它拿过来了，这本来会是**Booster**更早的实施。出现的一个听起来有点傻的问题是，它本质上是一个位于燃料箱内的通气管。你可以在那个通气管内冷凝液体。而那些有效地排出储罐的阀门不喜欢液体。所以当我们试图超快地进行时，我们想：“哦，太棒了，我们得到了免费的硬件。我们可以跳过整个设计周期。让我们快速行动，我们可以更快地投入生产。”我们当时想：“哦，我们也会把液体弄到这个东西里。我不知道阀门会不会喜欢那样。”我们所做的就是调动必要的资源来证明这会没问题。这不仅让我们能够更快地将整个硬件设计投入生产，而且还让**Booster**在他们到达那里时也能使用相同的硬件。所以从公司目标角度来看，这非常棒，而且是完美的方向。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, there's there's one that's kind of interesting. It's kind of getting into the weeds, but we we had the opportunity to pull some hardware from from Booster. So Booster was a little bit ahead of ship the ship team in terms of their V3 design. They kind of skipped V2 for for Booster. They went from V1 to V3. And they had some hardware designed for for the V3 vehicle that actually could have been plugged in the ship very easily. And we had somebody we had very limited engineers to go design a ton of prop systems hardware. And we identified that, oh, we could maybe use this. And we kind of brought it over early, which would have been an earlier earlier implementation booster. And one of the things that popped up that's that sounds kind of silly is it was essentially a snorkel that lives inside the fuel tank. And you could condense liquid inside that snorkel. And the valves that that were, you know, effectively venting the tank there, don't like liquid. So when we were like trying to go super fast, like, oh, sweet, we got free hardware. We can skip a whole design cycle. Let's go fast and we can, you know, just jump into production sooner rather than later, we were like, "Oh, we're going to get liquid in this thing, too. I don't know if the bows are going to like that." And what we did is we just spooled up the the necessary resources to go prove that that's going to be okay. And what that what that did was not only allow us to go roll in this whole hardware design into production sooner, but it also enabled Booster once they got there to go use the same hardware. So from a company goal perspective, it was fantastic and it was like the the perfect direction. I think.

</details>

**Chandler Lugjitsa**: 我甚至不会把所有这些想法都归功于自己。实际上，团队里的另一个人，他现在还在那里，把这个想法提给了我，我当时想：“哦，天哪，这太棒了。我们做吧。我们快点。”但这就是一件事，它真的只是让你对质疑每一个要求保持非常清晰的意图，因为这样做的好处是，当工程师开始实际设计硬件时，你的要求集能够让他们设计一个非常简单的解决方案，而简单就是快，简单就是便宜。所以，我认为**SpaceX**的整个理念是非常真实的，它正在**Starship**上发生，甚至在**Dragon**的修复上也发生。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I won't even take I won't take credit for all of that ideation. Actually another guy on the team is still there kind of brought it to my plate and I'm like, "Oh man, that's freaking great. Let's do it. Let's go fast." But that that's one thing and it's really just you know staying super clear on on this intention to question every requirement because what that does is it enables your requirements set whenever you know an engineer steps in to go actually design the hardware to be you know enable to design a very simple solution and simple is fast simple is cheap. So really I think that whole part of the space mantra is very real and and it is happening across Starship it's even happening on on fixes on Dragon.

</details>

**主持人**: 就像如果你没有专注于生产，如果你没有提前两步思考生产，你就会设计出一些完全为这套要求量身定制的东西。

<details>
<summary>Original English</summary>

**Host**: Like if you hadn't been focused if you if you hadn't been thinking two steps ahead about production you would have just designed something from scratch that was perfectly bespoke to the set of requirements.

</details>

**Chandler Lugjitsa**: 没错。就像我们，是的，没错。定制要求。我认为，我们实际上在意识到“哦，糟了，我们应该直接用那个”之前，已经为所有这些硬件做了一整套设计，因为那样我们就可以更快地开始弄清楚如何建造这些有点复杂的焊接件，然后非常迅速地建立这些焊接件的生产线。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Exactly. It's like we Yeah, exactly. bespoke requirements. And I think, you know, we we literally had a whole design for all this hardware before realizing, oh crap, we should just go use that because then we can go start figuring how to build these, you know, somewhat complex weldments sooner rather than later and then build a production of those very quickly.

</details>

**主持人**: 那就是信息获取真正重要的地方。绝对是。是的。**Turner**，你呢？你帮助建造了**Tesla**在**Corpus Christi**价值数十亿美元的锂精炼厂，它现在已经投入运营。你克服了一些最艰难的挑战是什么？你是如何用这种**工厂思维**和生产思维来应对它们的？

<details>
<summary>Original English</summary>

**Host**: That's where information access really matters. Absolutely. Yeah. What about you, Turner? You know, you helped build Tesla's billion-dollar lithium refinery in Corpus Christi, which is, you know, up and running. What were some of the hardest challenges you overcame? How did you how did you approach them with this kind of factory and production mindset?

</details>

**Turner Caldwell**: 是的，我认为，为制造而设计有点像你如何进行产品设计，并确保你可以将其规模化，使其能够以非常短的生产周期大规模生产。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, I think that so design for manufacturing is kind of like how you do product design and ensure that you can kind of scale that into something that can be produced at scale with, you know, very short tech times and all that.

</details>

**主持人**: 是的。但我的意思是，人们并不真正把精炼厂看作是一种产品。

<details>
<summary>Original English</summary>

**Host**: Yeah. But I mean people don't really think about a refinery as a product.

</details>

**Turner Caldwell**: 没错。所以我们花了大量时间思考的问题，显然也是我在**Tesla**时思考的问题，是当你进行建设时。环境是你正在建造一个定制的东西，所以你必须将其分解成可以在场外制造并运到现场的模块化子集。然后你必须思考，所有东西都应该有一个**节拍时间分析**。**节拍时间分析**基本上就是分解构建某物所需的所有离散步骤。这需要发生。

<details>
<summary>Original English</summary>

**Turner Caldwell**: So Exactly. And so the the what we spent a good amount of time thinking about and that obviously we thought about when I was at Tesla was when you're in when you're in like construction basically. The the environment is you're building a custom thing right and so you have to break that down into like modular subsets that can be manufactured off site and brought to site. The and then you have to think like everything should have a tact time analysis associated with it, right? Like what analysis attack time analysis which is basically breaking down all the discrete steps required to go to to build something effectively. And that needs to happen in.

</details>

**主持人**: 这是一个**Tesla**或**SpaceX**的术语，还是一个行业术语？

<details>
<summary>Original English</summary>

**Host**: Is that a Tesla a SpaceX term or is that an industry?

</details>

**Turner Caldwell**: 那是一个行业术语。

<details>
<summary>Original English</summary>

**Turner Caldwell**: That's an industry term. Okay.

</details>

**Turner Caldwell**: 是的，我不能把发明**节拍时间分析**的功劳归于自己。关键在于，在整个价值链中，从研发到分析实验室的运行方式，你都应该思考：从样品进入实验室到结果出来，有哪些单独的步骤？所以你需要像运行小型制造流程一样运行分析实验室。在施工中，你需要将其分解为特定的任务子集，这些任务实际上是拧紧螺栓和焊接接缝，以构建出实际需要的时间表，而不是自上而下地评估建造某物需要多长时间。然后，在采矿作业中，你还需要对采矿作业中发生的所有离散任务进行超离散的**节拍时间分析**。我认为建筑行业并非所有人都这样做，但由于每个项目都是定制的性质。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, can't take credit for inventing tax analysis. The the key there is that like through the whole value chain from like R&D and like how your analytical labs run you should be thinking about okay what are the individual steps that go from a sample comes into a lab to a result comes out and so you need to run analytical labs like little manufacturing processes on construction you need to boil it down into specific subsets of tasks that are you know actually torquing bolts and actually like welding out seams to build that up into like what does the schedule actually need to be instead of doing like top down assessments of kind of how long something is going to take to build. And then when you're in mining operations, you also need to do like super discreet tactile analyses of all of the discrete like discrete tasks that happen around a mining operation. And I think that the construction industry does not some folks do this, but because of the like custom nature of each individual project.

</details>

**Turner Caldwell**: 这需要时间和精力，你必须分配资源才能从头开始构建，了解做某事实际需要多长时间。当我们开始思考如何像制造运营一样运行施工时，你知道，一个施工现场通常是这样运行的：一个主管已经得到了他们本月的任务目标，他们每天会到现场，和工人们围成一圈，他们会说：“你今天在做什么？你今天在做什么？你今天在做什么？”一天结束时，他们回来，说：“你今天做了什么？你今天做了什么？”并没有很多定量的东西是定期发生的，也没有很多对施工运营的短周期控制是实际量化的。所以，我们在**Mariana Minerals**开始做的是将其分解，这最终成为一个数据管理问题，以及一个资源分配优化问题。你有一部分材料和设备在现场，有一部分人员在现场，你有一系列需要完成的任务。今天，这就像是人类试图在三个数据库之间进行协调，决定现场将要发生什么任务。我们看到那里有大量的机会可以算法化地完成。

<details>
<summary>Original English</summary>

**Turner Caldwell**: It's it you it takes time and effort and you have to allocate resources to be able to like build build from the ground up of like how long it actually takes to do something. And as we start to think about like how do you run construction like manufacturing operations you know the way a construction site runs typically is a superintendent you know has been given their target for the month on a daily basis they'll go out to the field they'll stand in a circle with the trades they'll say what are you doing today what are you doing today what are you doing today at the end of the day they come back they say what did you do today what did you do today and there isn't a lot of like quantification that happens on a regular basis like there isn't a lot of short interval control of construction ruction operations that is actually quantified. And so what we you know what we have started doing at Mariana is breaking that down and this ends up being like a data management thing right and a resource allocation optimization you have to do where you have a subset of materials and equipment that are on site you have a subset of people that are on site and you have a set of tasks and need to be done and today that is like humans trying to like sit between those three databases and decide like what is the task that's going to happen at the site. Um and we see a ton of opportunity there to do that algorithmically.

</details>

**Turner Caldwell**: 如果你拥有所有这些数据，你就可以设定每日、每小时的目标。然后，如果你能自动化现场的数据捕获，比如**Boston Dynamics**的**Spot Dog**机器人，它工作得很好。它可以在现场漫游，进行3D扫描。你需要在软件方面做大量工作，才能将输入的3D扫描与模型进行协调。然后你就可以对施工进行短周期控制，这实际上就是制造，也就是超短周期控制。每个人都有一个仪表板，告诉你：“好吧，我们今天在这个工位要生产多少零件？”他们知道自己是朝着目标前进、落后于目标还是超越目标。衡量施工、采矿、精炼中重要的事情，这实际上是需要转变的文化。

<details>
<summary>Original English</summary>

**Turner Caldwell**: That enables you if you have all that data available you can actually set daily hourly goals and then if you can automate the data capture that is happening at the site like Boston Dynamics has the Spot Dog that works great. It can kind of roam around the site take 3D scans you have to do a lot of work on the software side to be able to reconcile the 3D scans that have come in to the model. And then you can actually do short interval control on construction which is effectively what manufacturing is which is like short super short interval control. Everyone has a dashboard that tells you, okay, how many parts are we trying to make today at this station? And they know whether they're trending towards their goal or they're trending behind their goal or or exceeding their goal. And like measuring the things that matter in construction, in mining, in refining like that is actually the the like cultural thing that needs to shift.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Turner Caldwell**: 我们在**Tesla**做了很多这样的尝试。但最终，你必须投资于支持这些的软件骨干。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And that we did a good amount of um tried tried to do a good amount of at Tesla. But there's the ultimately you have to invest in like the software backbone that enables that.

</details>

**主持人**: 很少有创始人能像你**Turner**一样，经常说我们提前完成计划且预算内。

<details>
<summary>Original English</summary>

**Host**: From you know few founders I've heard as often we are ahead of schedule and under budget than uh than you Turner.

</details>

**Turner Caldwell**: 我们正在努力。是的，我们正在努力。这关乎衡量和量化。我认为很多制造业，你会深入了解，因为你每小时生产数千个零件，这取决于制造过程的规模，而这种衡量和对照目标进行衡量并设定目标的水平，在这种大规模基础设施生态系统中是不会发生的。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Well we're trying. Yeah we're trying. It's about measuring and quantifying like I think a lot of manufacturing like you go really deep on understanding like because you're making thousands of parts you know an hour depending on the scale of manufacturing process and that level of like measuring and measuring against goals and setting targets just doesn't happen in this like large scale infrastructure ecosystem.

</details>

### 垂直整合：战略性而非盲目

**主持人**: 也许谈谈**垂直整合**，它是**Tesla**和**SpaceX**最明显和最常被讨论的原则之一。它也非常昂贵，非常困难。最近TVPN就此进行了一次很好的讨论。你知道，所有硬科技初创公司都应该**垂直整合**吗？你何时何地进行**垂直整合**？你们是如何思考这个问题的？你们如何平衡速度与资本密集度和运营风险？我很想听听你们对**垂直整合**的看法。也许**Chandler**，你先说。

<details>
<summary>Original English</summary>

**Host**: Maybe talking a little bit about vertical integration it's one of the most obvious and talked about Tesla and SpaceX principles. It's also really expensive, really hard. There's been, you know, various debates. TVPN had a good session on this recently. You know, should all tech hard tech startups vertically integrate? Where and when do you vertically integrate? How do you guys think about it? You know, how do you balance speed with capital intensity and operational risk? I'd love to hear your your thoughts on on vertical integration. Maybe Chandler, why don't you.

</details>

**Chandler Lugjitsa**: 是的，我可以插话。你为什么不插话呢？

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I can jump in. Why don't you jump in?

</details>

**Turner Caldwell**: 我当时正在和**Mike Vinciata**直接讨论这个问题。

<details>
<summary>Original English</summary>

**Turner Caldwell**: I was talking with Mike Vinciata about this directly.

</details>

**主持人**: 之后。

<details>
<summary>Original English</summary>

**Host**: After that.

</details>

**主持人**: 它引起了不小的轰动。

<details>
<summary>Original English</summary>

**Host**: It caused quite a stir.

</details>

**Chandler Lugjitsa**: 确实如此。是的，我们进行了很好的来回讨论。很有趣。我基本上支持那里的观点。我认为。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: It sure did. I was Yeah, we had a good back and forth. It was funny. I I'm largely in support of the take that was on there. I think.

</details>

**主持人**: 也许对于没看到的人，那是什么观点？

<details>
<summary>Original English</summary>

**Host**: Maybe for the people who didn't see it, what what was the take?

</details>

**Chandler Lugjitsa**: 至少我的理解是，它必须是战略性的。这种一无所有、理想主义的“我们要**垂直整合**”的方式，我认为在某种程度上是天真的。**垂直整合**并不容易。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: The the the take at least my readback on it was it needs to be strategic. Like this this blank slate idealistic we're going to vertically integrate is like I think almost naive in a way. Like vert vertical integration is not easy.

</details>

**主持人**: 当然不容易。

<details>
<summary>Original English</summary>

**Host**: Certainly not easy.

</details>

**Chandler Lugjitsa**: 确实非常不容易。我认为我们来自的地方可能让它看起来很容易。但它真的不容易。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: It's very much not easy. And I think there's we we've we're coming from places that have made it look easy for sure. But it's it's not it's really not.

</details>

**主持人**: 从外面看，从外面看。

<details>
<summary>Original English</summary>

**Host**: From the outside from the outside,

</details>

**Chandler Lugjitsa**: 从外面看，看起来超级容易。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: From the outside looks super easy.

</details>

**主持人**: 是的。这是一个非常浪漫的梦想。

<details>
<summary>Original English</summary>

**Host**: Yeah. It's very romantic dream.

</details>

**Chandler Lugjitsa**: 绝对是。我认为很多人可能没有经历过那种痛苦，无法理解战略性地追求它所带来的权衡。所以，我认为我的想法是，我们必须尽快将那些会成为我们供应链瓶颈或生产线瓶颈的组件内部化。所以，我认为对我们来说，这意味着一些较大的焊接件，从这类事情开始，尽早将其内部化是相对容易做到的事情，但它是一个非常复杂的事情，涉及多个步骤。如果我们能将其内部化，我们就能解决一个问题，从而实现每年生产10,000枚导弹的目标。我认为当然还有更多挑战，或者你只要审视你的内部产品，就需要去看看哪些事情真正影响了你的进度。对我们来说，现在可能就有五个这样的问题，它们都在尖叫着“请帮助，请帮助”。所以这些事情显然会是首要考虑的，比如我们该怎么做？我们该用什么方法来做？然后你就可以开始分析实现它所需的资本密集度有多高，所需的时间有多长。但它必须是战略性的，我认为很多观点，比如“我们完全**垂直整合**了这个，我们完全整合了那个”，这肯定会花费大量金钱。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Absolutely. And and I think you have a lot of people who maybe haven't lived that pain to understand that like the trade associated with with going for that strategically. So I think how how I think about it is we have to bring in the assemblies inhouse that that are going to bottleneck our supply chain as fast or bottleneck our production line as fast as possible. So I think what that looks like for us is is some of the bigger weldments like starting starting with that sort of thing bringing it in house sooner rather than later is something that's relatively easy to do but is a very complex thing that has multiple steps that that if we can bring that in house we we we whack one mole on the table of of getting to this you know 10,000 missiles per year number. I think there's of course many more challenges or you kind of just whenever you're looking at your in-state product, you need to go and see what are the things that are are really hitting me on schedule. And for us, there's probably five of those right now that are are like screaming at us like please help, please help. So those things are obviously going to be top of mind to like how could we do this? Like what is what is the way we would do this? And and then you can actually start to analyze the the how intense the capital is to to make it happen. How how extensive the time is required to actually go and achieve on that. But it's it has to be strategic and I think a lot the a lot of the takes that are uh we're fully vertically integrated this we're fully integrated that is just it's it's going to spend a lot of money that's for sure.

</details>

**Turner Caldwell**: 是的，我认为为了**垂直整合**而**垂直整合**，就像**Chandler**所说的，没有任何意义。我认为每一个**垂直整合**的决策，有成千上万个这样的决策，都必须归结为一个问题，尤其是在公司早期：如果你不做**垂直整合**的决策，公司是否存在？所以，如果你把它归结为一组二元问题，比如**Mariana Minerals**是否存在，或者**Mariana Minerals**不存在，那么决策就变得容易了。这可能是由多种因素驱动的，要么是零件不存在，要么是技术不存在，要么是成本高得离谱，以至于公司如果不进行**垂直整合**就无法生存。我称之为“那个东西”，因为有很多很多东西，以及软件堆栈的子组件或部分，你知道，如果你不自己去做，公司就不会存在。所以当你把它归结为这一点时，它就与最终的战略决策驱动因素联系在一起。所以你不应该仅仅因为可以在子组件上节省5%、10%甚至50%而进行**垂直整合**，这并不能满足“如果我们不这样做，公司是否存在”这个条件。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, I don't think vertical integrating for the point of vertical integrating to kind of echo what Chandler was saying is makes any sense. I think every vertical integration decision which there there are thousands of them need to boil down to like one question especially in like the early days of companies is does the company exist or not if you make the decision to ver if you don't make the decision to vertically integrate and so like if you boil it down to like a subset of problems that are binary and like does Mariana exist or does Mariana not exist the that makes the decision easy where and and that could be a number of drivers it's either the part doesn't exist the technology doesn't exist or the cost is like so insane high that the company can't exist by not vertically integrating into the thing and so if the and I call it the thing because there's many many things and and like subcomponents or parts of the software stack that you know if you don't go and do it yourself like the company just won't exist and so when you boil it down to that like it ties into like that is the ultimate strategic decision driver so you should not be vertically integrating just because you can save 5% or 10% or 20 even 50% on a subcomponent that does not kind to check the box of like does the company exist or not if we don't.

</details>

**主持人**: 所以这主要不是成本问题。

<details>
<summary>Original English</summary>

**Host**: So it's not primarily a cost thing.

</details>

**Turner Caldwell**: 在早期不应该是。在早期，当你资源有限，你必须决定如何分配这个需要继续增长的团队，就像所有初创公司或许多初创公司一样。所以当你处于这种资源受限模式时，你只应该**垂直整合**那些具有二元结果的事情，比如公司存在或公司不存在。然后，一旦你开始拥有一个庞大的团队，并且你正在降低单位成本，那才是成本驱动的**垂直整合**开始变得有趣且更长期的决策。因为现在，在纸面上它可能看起来很棒，但从供应商到你自己的风险转移是你必须考虑的主要事情。你的供应链中的任何人都承担着这些活动的风险，对吧？所以，你并没有消除一个供应链点。你实际上是在扩大你的供应链互动，因为如果你**垂直整合**到上游，他们有自己的供应链，你现在必须吸收。我们决定成为一家构建和运营矿物基础设施的软件公司。主要是因为向采矿公司销售软件的软件公司很难渗透这个行业，因为问题在于软件和技术的采用率实际上受到如果你是纯粹的SaaS公司，那将是客户的限制。

<details>
<summary>Original English</summary>

**Turner Caldwell**: It it shouldn't be in the early days like in the early days when you have resources that are that are slim and you have to decide like where where do I allocate this this team that you know needs to continue to grow like all startups or like many startups the so when you're in that like resource constrained mode you should only be vertically integrating into the things that are that have like a binary outcome of like the company exists or the company doesn't exist. Then eventually once you like start to like have a large team that can like go and you're and you're driving down unit cost that's where the like costdriven vertical integration starts to become like an interesting and and much longer decision I would say because now you're now it's like on paper it can look great but the risk transfer from a supplier to yourself is like the main thing that you have to be thinking about right the like folks that do do anything in your supply chain they are carrying risk in those activities right and so whether it is You're not eliminating a supply chain point. You're actually expanding your supply chain interactions because the if you vertically integrate into something that's upstream, they have their own supply chain that you now have to absorb. We made the decision to go and be, you know, a software company that builds and operates minerals infrastructure. Mainly because software companies that sell to mining companies have a very very hard time penetrating the sector because the issue is the like the rate of uptake of software and of technology is actually gated by what would be the customers if you were a pure place ass company.

</details>

**Turner Caldwell**: 是的。所以对我们来说，这方面的疑问总是：**Mariana Minerals**是否存在？如果我们既不是软件公司也不是采矿公司，答案是否定的，公司将不复存在。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah. And so the question for us in that regard was always like, does Mariana exist or not? If we're not both a software company and a mining company, the answer to that was no, the company would not exist.

</details>

**Turner Caldwell**: 嗯，所以我们必须这样做。但是一旦你决定这样做，就会有一个问题：你的合作关系有多少？以及是否存在一个足够丰富的生态系统，有足够的竞争，让你有信心某个子组件的成本会下降，或者软件堆栈的某个部分的成本会下降。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And so we had to do that. But then once you like sign up for that, there's a question of like how much of your like part like where do you do partnerships and and where is there a rich enough ecosystem where there's enough competition to be able to have confidence that like the cost will come down on some subcomponent or the cost will come down on some some part of the software stack.

</details>

### 招聘优秀人才与职业发展建议

**主持人**: **Tesla**和**SpaceX**都以能够招聘到高素质人才而闻名。其中一部分归结于你们之前谈到的使命问题，即**使命一致性**。另一部分归结于人们希望与聪明人一起工作并向他们学习。但是，从这些公司走出了这么多优秀的工程师和创始人，这确实非常了不起。那么，这些公司是如何招聘的？他们是如何招到如此优秀的人才和工程师的？你又是如何将这些经验带到你今天正在建立的公司中去的？

<details>
<summary>Original English</summary>

**Host**: So something that both Tesla and SpaceX are, you pretty famous for is the caliber of talent that they're able to hire. And you know, part of it comes back to this mission, this mission problem, this mission alignment that you guys talked about before. Part of it comes down to, you know, people who people want to work with other smart people and learn from other smart people. But it's, you know, it's pretty remarkable how many excellent engineers and founders have come out of these companies. So, how does hiring work at these companies? Like, how do they get such excellent talent and excellent engineers in the door? And how do you bring that some of those lessons into the companies that you're building today?

</details>

**Turner Caldwell**: 是的，我认为在**Tesla**，至少在**Tesla**，我相信**SpaceX**也是如此，招聘过程的关键部分是技术评估。它进行得相当深入。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, I think the like the the key part of the hiring process at at at you know, Tesla at least, and I'm sure at SpaceX, um is the the like technical um evaluation. It goes quite deep.

</details>

**Turner Caldwell**: 所以，如果你申请一个工程职位，在获得录用通知之前，你可能需要与六位工程师交谈。你几乎肯定会进行一次技术测试，展示你如何思考问题，以及你是否能够解决简历上声称能够解决的问题。所以，这种对进入公司的人员进行评估的技术严谨性是相当广泛的。在获得录用通知之前，你将进行八到十次对话。

<details>
<summary>Original English</summary>

**Turner Caldwell**: And so they're, you know, you're going to talk to six engine, if you're applying for an engineering role, you're probably talking to six engineers before you're getting an offer. You're almost certainly doing a technical test that kind of shows how you think through problems and are you able to solve the problems that your resume says you're able to solve. And so that level of like technical rigor that goes into assessing folks that are coming into the company is pretty extensive. You're going to have eight to 10 conversations before you get an offer. And we've.

</details>

**主持人**: 这是一种特点。

<details>
<summary>Original English</summary>

**Host**: And that's a feature like.

</details>

**Turner Caldwell**: 百分之百。它确实会让招聘过程稍微慢一些吗？是的。但确保进入公司的人能够自主工作，并能够平衡权力和责任，这非常重要。这意味着他们必须对他们将要进入的领域有非常深入的技术理解。我们有效地模仿了这一点，并确保了这一点。当你没有**Tesla**或**SpaceX**那样的品牌时，这会更难。你知道，那些试图在这些公司找到工作的人会说：“是的，我愿意做技术测试，是的，我愿意和你想让我交谈的尽可能多的人交谈。”所以你确实需要与候选人进行一些管理。但对于那些真正对使命和公司感到兴奋的人，也就是你无论如何都想招进来的人，他们会经历这个过程。我们通常会双向推销它，即：“看，如果你要加入，你加入的是一家本质上具有高风险的初创公司。所以你也应该了解我们拥有的团队。”所以这是双向的。

<details>
<summary>Original English</summary>

**Turner Caldwell**: 100%. And like it does does it make the like hiring process a little bit slower? Yes. But it is really important to do your darnest to make sure that the folks that are coming to the company are going to come in and be autonomous and able to like balance authority and accountability. Which means that they have to really really have a deep technical understanding of the field that they're going into. We've mirrored that effectively. And ensured that and it's it's harder when you don't have the brand that Tesla or SpaceX have right of you know the folks who are trying to get a job at those companies they're like yes I'll do a tech test yes I will talk to as many people as you want me to talk to and so you you know you do have to manage that a little bit with candidates but for the folks who are really excited about the mission and the folks who are really excited about the company who are the folks that you want to bring in anyways they will go through that process and we typically pitch it in both directions it's look, if you're going to join, you're joining a startup that has, you know, inherently has high risk. And so you should also get to know the team that we have. And so it goes in both directions.

</details>

**主持人**: 我一直发现，极其严格且实际上很难的面试过程，会积极筛选出那些被这种非常困难的面试过程所激励的人。

<details>
<summary>Original English</summary>

**Host**: I've always found that extremely rigorous and actually hard interviewing processes positively filter for people who are motivated by the really hard interview process.

</details>

**Turner Caldwell**: 是的。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yep.

</details>

**主持人**: 就像如果你是一个顶尖工程师，你希望与其他的顶尖工程师一起工作，你希望知道其他的工程师也经历了和你一样的过程。而且，非常困难的面试过程很有趣，但它们很难设计。对于面试官来说，这可不是胆小鬼能做的。

<details>
<summary>Original English</summary>

**Host**: Like if you're a cracked engineer, you want to work with other cracked engineers and you want to know that other engineers have gone through the same process that you have. And like really hard interview process is pretty fun but they're very hard to design. It's not for the faint of heart on the interviewer side.

</details>

**Chandler Lugjitsa**: 我想，为了回答这个问题，我不会重复他所说的。不不，这很好。它非常相似，但我要做的区分，以及我认为我能在这里增加的价值是，对于全职的、比如说有多年的经验的人来到**SpaceX**，他们会经历四、五、六轮筛选，然后是小组面试来结束。我认为我能在这里增加的价值尤其与实习生渠道有关。我认为鉴于**Tesla**和**SpaceX**的品牌，这实际上已经被量化了。这些是历史上申请人数最多的项目，它们引起了公众的极大兴趣，这显然是一把双刃剑，对吧？就像你得到了非常好的，但你也得到了非常糟糕的。这是一个广泛的分布。然而，我认为，看看这些兴趣项目对最终的全职候选人或全职员工的影响，它给了这些人三个月的试用期。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I think to not just repeat what he said to answer the question. No no it's good. Uh it is very similar but the distinction I'll make and I think the value I can add here is um I very true on the full-time like say multi-year experienced person who's coming to a SpaceX like they're going through four or five six screens right a panel interview to finish it off. Um, I think the the the value that I can add here is particularly related to the internship funnel. I think given the brand with Tesla and SpaceX, like literally it's been quantified. These are like the most applied to programs ever and they've got this insane interest from the public, which obviously is a double-edged sword, right? It's like you you get very good, but you also get very bad. It's a it's a broad spread. Um, however, I think looking at the the impact of of these these interest programs on the eventual full-time candidates or the full-time um employees, it gives it gives a three-month trial period to these people.

</details>

**Chandler Lugjitsa**: 那些表现出色的人会一直留下来。我自己也是如此，我曾四次进入**SpaceX**。我无法离开。那就像是我的梦想。我开始做软件。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: And people that crush stay all the time and and I find that myself included, I was a I entered into SpaceX four times. I couldn't leave. Like it was it was the dream. I I started software.

</details>

**主持人**: 你当时想：“哦，也许我这个夏天会尝试一些不同的实习。”

<details>
<summary>Original English</summary>

**Host**: You were like, "Oh, maybe I'll try something try a different internship one summer."

</details>

**Chandler Lugjitsa**: 我差点辍学留下来，但他们说我们不能再那样做了。那不是旧时代了。所以，我认为，在**Starship**、**Dragon**甚至**Falcon**上做大量关键工作的绝大多数人都是实习生。我认为那个项目对最终的工程师群体来说是如此关键，因为它给了人们一个真正的机会去证明：“是的，我是一个杀手。我是一个狠角色。我能做到这一点。”

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: I almost jumped out of school to stay, but they but they said we couldn't do that anymore. It's not the old days. So, uh, but there I think the the overwhelming population of folks that are doing so much of the critical work on Starship Dragon Falcon even are interns and and I think that program is so freaking crucial to like the eventual engineering population because it it gives people a real chance to go and demonstrate that yes, I am I am a killer, right? I am I am badass. I can do this thing.

</details>

**主持人**: 那么在**Galedai**，你仍然是一个小团队，你正在壮大你的团队。

<details>
<summary>Original English</summary>

**Host**: So at Galedine, like you're a small team still, you're growing your team.

</details>

**Chandler Lugjitsa**: 我们刚刚启动了实习生项目。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: We just launched internship program.

</details>

**主持人**: 我正要说。

<details>
<summary>Original English</summary>

**Host**: I was just going to say.

</details>

**Chandler Lugjitsa**: 我们刚刚做了这个。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: We just did this.

</details>

**主持人**: 你是如何考虑这个的？以及如何设计你的实习生项目以及更广泛的面试流程，以招募到最优秀的人才？

<details>
<summary>Original English</summary>

**Host**: How are you thinking about that? And and and designing your both internship program, but like broader interview process to get the best quality people in the door.

</details>

**Chandler Lugjitsa**: 是的。所以我们仍然非常小，所以这没什么大不了的，但我当然会和每个人交谈。我不知道你是否还在这样做。我相信你还在。多次。是的，没错。多次。通过电话说服他们，让他们相信。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yep. So we're still very small, so it's it's not really saying much, but I'm of course talking to every person. I I don't know if you still are. I'm sure you are. Multiple times. Exactly. Yeah. Multiple times. Uh coercing them over the phone, convincing them that.

</details>

**主持人**: 你是在做行为面试和深入的技术面试吗？

<details>
<summary>Original English</summary>

**Host**: Are you doing both kind of the the the the uh behavioral interviews and the like deep dive technical interviews?

</details>

**Chandler Lugjitsa**: 是的，我发现我从一开始就问一个宽泛的问题，然后深入探讨很多事情。但我真的会放开手脚，给自己一个发挥的空间，去围绕他们的问题集进行“拳打脚踢”，但我实际上会问：“请带我回顾一个你解决过的问题。”当他们用20或15分钟回顾那个问题时，我很快就能知道他们是否优秀。通常，无论是什么学科，我都能足够好地围绕那个问题集进行一些“拳打脚踢”，以感受一下。但我发现，对于那些不真实的人来说，要通过我的筛选是相当困难的。但对于全职流程，我们正在进行两到三轮筛选，然后是小组面试。我的很大一部分框架也是，我非常希望把你介绍给团队。我们有一个非常小的团队，你实际上需要和他们一起生活，我们希望确保我们对你满意，你也对我们满意，这给了你一个完美的平台来做到这一点。所以这通常是我们完成全职流程的方式，但对于实习生，我们现在正在摸索。这确实是一个较短的流程，但我真正寻找的是第一批导弹工程师的热情。我需要那些会全力以赴的人。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I find that I get a lot out of like I I I I always start with one sort of broad question, then dig into a lot of things, but I I I really open it up to to allow myself a playground to like punch and jab and and go around their problem set, but I effectively ask, "Walk me through a problem that you solved." And whenever they walk through that problem over 20 minutes or 15 minutes, I I know very quickly whether or not they're good or not good. And usually I'm I'm okay enough, no matter what the discipline is, to kind of jab and punch around that problem set a little bit to to feel it out. But I find it's pretty hard to to get past my my screen there with people who are who are not not true. But for the full-time process, we're doing, you know, two, three screens and then a panel interview. And and a large part of my framing too is is very much I want to introduce you to the team. Like we have a very small team that you're going to need to live with effectively and we want to make sure that we're happy with you and and you're happy with us and this gives you the perfect forum to do it. So that's usually how we finish our our our full-time process, but but for interns, we're figuring out right now. It's a shorter process admittedly, but what I what I'm really looking for for this first wave of of uh of missile engineers is is is passion. Like I need people going to come in and crush and for.

</details>

**主持人**: 那么你招聘的实习生有哪些背景？

<details>
<summary>Original English</summary>

**Host**: And like what what backgrounds of interns are you are you hiring for?

</details>

**Chandler Lugjitsa**: 项目团队，不限哪个。所以方程式赛车、无人机、无人机系统等等，还有火箭团队。我实际上在全国找到了一支特定的火箭团队，他们使用的推进剂与我们相同，我之前并不知道它的存在，因为它比较罕见，但我正在瞄准那所学校。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Uh project teams, doesn't matter which. Uh so formula, the the um the whatever drone UAS stuff, but rocket teams, too. Um, I actually found a specific rocket team in the country that that works on rockets with the same propellants that we're using, which I did not know existed because it's a little bit more rare, but I'm targeting that school.

</details>

**主持人**: 把他们都挖过来。把他们都挖过来。

<details>
<summary>Original English</summary>

**Host**: Get them all out. Get them all out.

</details>

**Chandler Lugjitsa**: 把整个团队都弄过来，让他们坐上巴士，带到这里来。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Get the whole team, get them on a bus and bring them over here. But yeah,

</details>

**主持人**: 嗯，也许总结一下，鉴于我们正在谈论招聘实习生和年轻人才，你们俩都在相对年轻的时候就开始了在**Tesla**和**SpaceX**的职业生涯。对于一个年轻的**SpaceX**或**Tesla**工程师，或者实际上是任何一个年轻工程师，如果他们有一天考虑离职创业，你会给他们什么建议？他们应该如何思考这段旅程？

<details>
<summary>Original English</summary>

**Host**: Uh, maybe wrapping up, um, given we're talking about hiring interns and young talent, both of you started your careers at Tesla and SpaceX, you know, relatively young. Um, what advice would you give to a young SpaceX or Tesla engineer or in fact just a young engineer overall who's thinking about maybe one day leaving to start a company? How should they be thinking about that journey?

</details>

**Turner Caldwell**: 是的，我想说，如果你在一家拥有非常高**人才密度**的公司工作，并且你觉得自己一直在学习，每天都是一个成长的机会。而且你能够看到项目从混乱的早期阶段，到中间的混乱阶段，再到部署的混乱阶段。这种经验是极其宝贵的。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, I would I would say um, you know, if you if you're at a company that has, you know, really really high talent density um, and you're in a position where you feel like you're constantly learning and every day is kind of like a growth opportunity. Um, and you get to see projects from like the messy phase, the the early messy phases through the middle messy phases through the kind of deployment messy phases. Um, like that experience is is incredibly valuable and.

</details>

**主持人**: 从头到尾地看到一件事。

<details>
<summary>Original English</summary>

**Host**: Seeing something through end to end.

</details>

**Turner Caldwell**: 从头到尾。所以我想说，在你能够参与一个从头到尾的项目，并且多次这样做之前，不要去创业。这能让你看到在每次迭代中，从概念到部署，你能做得多好。与世界上最优秀的人一起做这件事是一种非常独特的经验，它能让你最终能够去创业。但我不会急于离开去创业，因为一方面是你的信誉，但更重要的是你吸引人才的信誉，因为公司最终是这些优秀人才的集合，他们被一个让所有人兴奋的使命所驱动。所以，说服人们加入一个充满痛苦和风险的使命，如果你多次经历过执行周期，你就会有更多的信誉。你知道，对整个过程的某个部分需要多长时间，或者整个过程需要多长时间，有一个内在的理解，这样你就可以可靠地设定目标，让团队能够团结起来并为之努力。所以，我想说，做到这一点，充分利用那些你能够做到这一点的生态系统和公司，在那里他们会稍微保护你免受你必须承担的风险。只要你在公司内部的职责范围内获得权力和责任，并且你获得的越来越多，那将是无价的经验，能够让你成功。

<details>
<summary>Original English</summary>

**Turner Caldwell**: End to end. So I would say that I wouldn't go and start something until you have like been able to sit around a project that you have seen go end to end and then done that multiple times that enables you to see how like how much better can you get with each iteration of um of of like from concept through to deployment and getting that getting to do that with like the most awesome people in the world um is is like a very unique experience that positions you to be able to go and start something eventually. But I wouldn't like rush to leave and go start something because one your credibility um to but really your credibility to attract talent because like the like the companies are are ultimately like this assembly of like awesome people who are driven towards a mission that everyone's excited about. Um and so convincing people to join you on that mission that's going to be painful. It's going to be risky. Um you have a lot more credibility if you have like been through the execution cycle multiple times. Know, have like the kind of embedded understanding of like how long does some part of that process take or how long does that whole process have to take so that you can credibly set targets that the team can then rally behind and go build uh build to. And so um I would say that getting like having done that you take take full advantage of like ecosystems and companies where you have the ability to do that um and and where you know they're insulating you a little bit from the risk that you have to be able like be comfortable taking. Um, and as long as you're getting authority and accountability in like the scopes that you're getting within the company and then you're getting like more and more of that, that is going to be invaluable experience that uh that will enable to set you up to be successful.

</details>

**主持人**: 我看到你点头了，**Chandler**。

<details>
<summary>Original English</summary>

**Host**: I see you nodding, Chandler.

</details>

**Chandler Lugjitsa**: 是的，我正在再次思考。我认为**Turner**和我过着同样的生活，只是他比我早几年。我18岁时进入**SpaceX**。那是我第一次踏入**SpaceX**这个有趣的糖果乐园，那是我的梦想，对吧？我从第一天起就告诉自己，我要像一块海绵。我想尽可能地成为最大的海绵，吸收所有这些了不起的人尽可能多的信息。这不仅仅是实习期的事情。这是一辈子的事情。我今天仍然在这样做。但我认为，是的，我处理这个问题的方式，以及我认为人们应该普遍处理这个问题的方式，不仅仅是去**SpaceX**或**Tesla**，而是他们应该真正从“我如何让自己被世界上最优秀的人包围，并从头到尾地完成一个项目，并像**Turner**所说的那样进行这些重复训练”的角度来处理。但我会补充一点，这很难，对吧？如果你刚毕业，你可能不知道那是什么样子。所以也许一些可操作的建议是，依靠你的网络。依靠你在学校认识的人，那些可能去了其他地方并见过其他环境的同伴，或者如果你有教授，你生活中其他可以进行有意义对话的人，关于某些公司、使命、产品等方面的观点，那就去做吧，因为这可能很难。这可能有点吓人。你不知道，因为你还没有做过。你不知道。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I'm I'm trying to think about again. I think Turner and I live the same life. Just use a little a couple years ahead. Um, I started SpaceX when I was 18 years old. Like that was when I first entered the doors into the fun candy land that was SpaceX and it was the dream, right? And I told myself from day one that I'm going to be a sponge. Like I I want to be the biggest sponge I possibly can to absorb as much freaking information from all these amazing people as I can. Um that's not not an internship limited thing. That's a forever thing. I'm still doing it today. But I think yeah, a lot of a lot of how I approached it and how I think people should approach it generally. Not not just if they're going to a SpaceX or a Tesla, but they should they should really approach, you know, this from a how can I surround myself with the best people in the world um and work on a project from start to finish and and do those reps like what Turner was saying. I will I will caveat that though with it. It's it's hard, right? If if you're if you're fresh coming out of school, you may not know what that looks like. So maybe maybe some actionable recommendation is, you know, lean on lean on your network. Lean on people you know both in school, peers who may have entered elsewhere and seen other environments or um if there's professors, other people in your life that you can have meaningful conversations with about perspective on on certain companies, just missions, products, that sort of thing, like go do that thing because it it can be hard. Like it can be kind of scary. You don't know because you haven't already done it. You don't know if.

</details>

**主持人**: 什么是好的。

<details>
<summary>Original English</summary>

**Host**: What good looks like.

</details>

**Chandler Lugjitsa**: 什么是好的。没错。所以，是的，我会补充一点，这很难，但一旦你找到那个最佳地点，那就去做一块海绵吧。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: What what good looks like. Exactly. So it I will yeah caveat it with it with it's hard but once you find that that sweet spot of of place to be then just go be a sponge.

</details>

**Turner Caldwell**: 是的。我认为知道什么是好的，并能够培养对优秀团队如何构建的理解和直觉，这是非常宝贵的。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah. I think knowing what good looks like and being able to develop an understanding and intuition for how exceptional teams build is like pretty invaluable.

</details>

**Chandler Lugjitsa**: 是的。是的。我认为如果没有在**SpaceX**做那些事情几年，我不可能创办**Galedai**。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah. Yeah. I I don't think I could start Galadine with without having spent, you know, a handful of years doing the things I did at SpaceX. So.

</details>

**Turner Caldwell**: 是的，我想我最后要说的是，你永远不会真正完全准备好去创办一家公司，对吧？就像你不会在那里待上十年，然后去工作，然后去创办一家公司。没有秘诀。所以总会有一个“你何时觉得自己有信心去冒险”的问题，不同的人对何时觉得自己准备好去做会有不同的看法，但我普遍认为，在你必须学习所有公司建设方面的事情之前，你希望拥有尽可能强大的技术基础。所以，确保你在技术方面过度投入，然后再去考虑如何招聘、如何融资、如何围绕公司构建整个生态系统和基础设施。因为一旦你开始创业，你就会不断学习，但专注于建立强大的技术基础是关键。

<details>
<summary>Original English</summary>

**Turner Caldwell**: Yeah, I think that maybe the last thing I'll say is that you're you'll never actually be like fully trained to go and start a company, right? Like the like it's not like you stay there for it's there's no recipe. It's not like you stay somewhere for 10 years and then you go and you work you go and start a company. The and so there's always going to be like a a when when do you feel yourself confident to go and take a risk and different people are going to have different perspectives on like when do they feel ready to go and do it but I generally think that you want to have as strong of a technical basis before you go and have to learn all of the company building uh side of of things and so making sure that you're kind of like overindexing on the technical side before you go and uh kind of sign up for figuring out how to hire and figuring out how to fundra and figuring out how to build all the the ecosystem around a company that and the infrastructure around a company that has to be built. Um because you are going to keep learning as once you go and start something but you know being hyperfocused on building that strong technical basis is the is the key.

</details>

**Chandler Lugjitsa**: 是的，我可以想象，如果我已经有了技术基础，然后去发展融资和所有这些我不知道如何做的其他事情。这已经很难了。我无法想象反过来，去学习我到目前为止拥有的所有技术能力，或者至少足够成功地完成我们正在做的事情，那将非常非常困难。

<details>
<summary>Original English</summary>

**Chandler Lugjitsa**: Yeah, I can imagine like this already having the technical basis and going and growing into the fundraising all of this other stuff that I didn't know how to do. Like this is already hard. I could not imagine the inverse like going and and and being going and needing to figure out all of the technical chops that I have up until this point or at least enough to to be successful in what we're trying to do. Uh would be very very difficult.

</details>

**主持人**: 所以不要试图在创业的同时学习如何建造火箭。这是个好建议。

<details>
<summary>Original English</summary>

**Host**: So don't don't don't try to learn how to build rockets on the job as a founder. That's good advice.

</details>

**主持人**: 酷。好的。这太棒了。谢谢大家。太好了。谢谢。

<details>
<summary>Original English</summary>

**Host**: Cool. All right. This was awesome. Thanks, guys. Great. Thanks.

</details>