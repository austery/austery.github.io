---
author: a16z
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=s4lXP9IuHjk
speaker: a16z
tags:
  - ai-application
  - software-architecture
  - crm
  - startup-strategy
  - agentic-system
title: 超越大模型实验室的创业突围：HubSpot 联合创始人谈 AI 时代的软件与生态
summary: HubSpot 联合创始人兼 CTO Dharmesh Shah 与 a16z 的 Joe Schmidt 探讨了在 OpenAI 和 Anthropic 等前沿 AI 实验室竞速之外的软件创业空间。Shah 回顾了 HubSpot 从单一营销工具到免费 CRM 平台的演进经验，指出界面只是手段，实际价值在于底层工作与网络。面对基础模型走向基础设施化与可替换化，创业者应避开实验室必经的主干道，专注垂直领域与系统上下文图谱，利用快速迭代与新型单人企业爆发契机构建复利优势。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Dharmesh Shah
  - Joe Schmidt
companies_orgs:
  - HubSpot
  - Andreessen Horowitz
  - OpenAI
  - Anthropic
products_models:
  - ChatGPT
  - Claude
  - Uspot
media_books: []
status: evergreen
---
### 开篇对话：前沿实验室路径之外的软件机会

>> ChatGPT 和 Claude Co-work，它们实际上就是新的操作系统。
<details><summary>Original English</summary>
Chad GPT and cloud co-work. They're effectively the new OS.
</details>

>> 在前沿 AI 实验室正在全速奔跑的赛道之外，仍有大量构建软件的空间。自那时起，HubSpot 一直很忙碌。
<details><summary>Original English</summary>
>> There's plenty of room to build software outside the path the frontier AI labs are racing down. Since then, HubSpot's been busy.
</details>

>> 真正有价值的是正在发生的实际工作。界面只是实现目标的手段。构建生态系统和构建产品非常相似，你必须用这种视角去看待它。我们曾经拥有非常广泛的营销应用基础。我们选择全盘皆做的唯一原因，是为了解决客户面临的实际问题——他们对工具的碎片化感到不知所措。一切还好。我们必须通过一体化的方案来提供服务。你最初构建 HubSpot 时所做的架构决策，是为了让人类在所有这些信息中穿梭导航。现在我们拥有了这些极其强大的模型，它们能以截然不同的方式审视事物。
<details><summary>Original English</summary>
>> The actual thing that's valuable is the work that's happening. The interface is a means to an end. Building an ecosystem is a lot like building a product. You have to think of it that way. We had a very broad base of marketing applications. The reason we chose to do it all is the only way for us to solve the actual problem customers had, which is they're intimidated by this fragmentation. Everything's all right. We had to do it all in one offering. The architectural decisions that you made when you originally built HubSpot was for a human to be navigating all of this information. Now we have these unbelievably powerful models that can go look at things in very different ways.
</details>

>> 既然知道我们身处这样一个 AI 世界，HubSpot 下一个 20 年需要什么样的架构体系？有几点需要考虑。其一是……
<details><summary>Original English</summary>
>> What is the framework we need for the next 20 years of HubSpot now knowing that we have this AI world? Couple [music] things. One is
</details>

### 从“虚无感”到建设者的黄金时代

>> 欢迎回到 a16z 播客。我是 Joe Schmidt，今天我们邀请到了 HubSpot 联合创始人兼 CTO Dharmesh Shah。我们在 X 上围绕我的《黄砖路》（Yellow Brick Road）一文展开交流，今天继续顺着这个话题深入探讨——核心观点是，在前沿 AI 实验室竞速的主干道之外，有广阔的软件构建空间。自那以后，HubSpot 动作频频：他们推出了针对单人企业的 CRM 产品 Uspot，并一直在围绕 Agent 重构自己的平台。今天我们将讨论哪些东西值得构建、成熟软件公司必须做出哪些改变，以及当 AI 成为客户使用产品的主要方式时会发生什么。Dharmesh，感谢加入我们。
<details><summary>Original English</summary>
>> welcome back to the A16Z podcast. I'm Joe Schmidt and today we're joined by Dharmmes Sha, the co-founder and CTO of HubSpot. We're picking up on a conversation that started with an exchange on X about my Yellow Brick Road essay. The idea that there's plenty of room to build software outside the path the Frontier AI labs are racing down. Since then, HubSpot's been busy. They've launched Uspot, a CRM for oneperson businesses, and they've been rebuilding their own platform around agents. Today, we're going to talk about what what's worth building, what an established software company has to change, and what happens when AI becomes the way customers use your product. Darm, thanks for joining us.
</details>

>> 感谢邀请我。
<details><summary>Original English</summary>
>> Thanks for having me.
</details>

>> 嗨，太兴奋了。Dharmesh，就像 LeBron、Madonna 一样，你拥有那种单名即可被大家辨识的名气。这非常酷。这对我来说是一场很有意思的对话，因为我几个月前写那篇文章，主要是为了回应当时硅谷弥漫的那种“一切都无关紧要”的虚无主义情绪。我觉得这种情绪现在实际上依然存在。因此，在这样一个时期掌舵一家成功的大型上市公司，感觉一定很不寻常。现在的感受是怎样的？我很想先从对当前市场状态的观察聊起。
<details><summary>Original English</summary>
Hi. Yeah, so excited. Star mesh, you know, LeBron, you know, uh, Madonna, [laughter] you know, the you you've got the one word, you know, the one name one word name. So, pretty pretty exciting. Um, this is a fun conversation for me because I wrote that essay, uh, you know, a few months ago really in response to this like nihilistic nothing matters feeling that was going on in Silicon Valley. And I feel like it's actually still going on. So, it's got to be strange running a big public company, successful public company through this time period. What does it feel like? I would love to maybe just start just with a market check.
</details>

>> 好的。一方面，这就像老话说的“最好的时代，最坏的时代”。说是最好的时代，是因为伴随这种巨大变革，你会感受到所有的能量与兴奋。回顾一下，HubSpot 现在已经有 20 年历史了。当年公司刚成立时，最初的出发点是：出现了一个叫“互联网”的新事物，中小企业理应借此推动业务增长等等；但他们当时并没有受益，因为这一切太令人不知所措，工具也非常分散，HubSpot 就是这样诞生的。如今快进 20 年，出现了一个叫 AI 的新事物，我们认为中小企业应当从中受益，但这依然让他们感到望而生畏。因此，这感觉像是一项重获新生的使命——面对同样的客户群体，只是迎来了全新的技术。另一方面，它确实制造了大量的“战争迷雾”和不确定性。作为团队，我们在很大程度上努力聚焦于客户，市场该怎样就怎样。对于事物如何演进以及该下注何处，我们有自己的论断。但我专注于积极的一面。我构建商业软件已经超过 30 年了，可以说是日复一日。就创造事物而言，这是我经历过的最有趣的时期。对于建设者来说，这是个多么棒的时代。
<details><summary>Original English</summary>
>> Yeah, it's uh on the one you it's the old best of times, worst of times. Um it's the best of times because you know we have um all this kind of energy and excitement um that you have when you have this kind of massive transformation. And I think backup spot's 20 years old now. And when the company started and the kind of genesis of the company was, oh, there's this new thing called the internet that SMB should be benefiting from to drive growth and things like that. And they're not yet because it's overwhelming and the tools were fragmented all and that's where HubSpot started. Now, fast forward 20 years, there's this new thing called AI that we think small mediumsiz businesses should be benefiting from, but it still feels intimidating and whatever. So it feels like this new um kind of uh revitalized mission u in same customer base uh just new technology. On the other hand um you know it does create a lot of uh the fog of war and uncertainty um that you know we try to for the most part as a team um custody focus on the customers whatever the markets will do what the markets will do. Uh we have our own thesis in terms of how things are evolving and and what bets we're putting down but uh I I focus on the positive side. I've, you know, I've been building commercial software for 30 plus years now. Like literally like every day. Um, and this is the most fun I've ever had um in terms of building things. It's uh this what a time to be a builder.
</details>

### 软件演进史：抽象层跃迁与低成本快速试错

>> 是的，我完全同意。非常奇怪的是，明明眼前一切都在起效，大家的感性认知却如此消极。就像你掉出船外直接扎进水里一样真切。如果回头看，我很想聊聊你早期的那些创立经历，比如 Pyramid，当然还有 HubSpot，以及你们是如何走到今天的。我很确定当年人们也说过类似的话，比如“写软件变得太容易了”、“现在还能做什么软件”。我很想听听你的看法，在实际创立公司的过程以及你今天在全新创业团队身上看到的现象之间，有哪些相似点和不同点。
<details><summary>Original English</summary>
>> Yeah. No, I totally agree. And it's it's it's so strange that the perception is negative when literally everything is working. It's like you fall out of the boat out of the boat and you hit water right now. Um maybe if we go back to I'd love to talk a little bit about some of those form you know formation experiences obviously with Pyramid and and um and then of course HubSpot and and how you guys got there. I I'm sure back then people were saying some of the similar you know things about hey it's gotten so much easier to build software and you know it's not it's not what are you even building now? I'd love to hear your commentary on maybe um you know the the similarities and the differences in terms of like how you're actually building companies and and what you're seeing today with uh you know with new startups.
</details>

>> 好的，我给你一个稍微偏极客视角的回答，因为我本身就是个技术宅。我在软件行业已经干了很久，从“史前时代”算起都快 150 年了。但软件及软件开发的历史，一直都是不断提高抽象层次的过程。我入行时，大家还在用机器语言，系统运行在大型机之类的主机上。接着我们有了第三代语言，有了 C 和 C++，再后来有了第四代语言。我们所做的一切，就是尝试将你脑海中想要解决的任何问题的构想，变得更容易落地实现。当年这极其困难，后来逐渐变得容易。
<details><summary>Original English</summary>
Yeah, I'll give you a slightly geeky response because I'm a geeky guy is that um you having been in the software industry since prehistoric ages um 150 years ago. But yeah, the story of software um in software development has always been this kind of increasing levels of abstraction right so when I started we still had you know machine language we were running on mainframes and things like that then we had 3G's we had C and C++ and we had you know 4G's and so it's what we've done is to said okay can we get to whatever manifestation you have in your head of whatever problem you're trying to solve can we make that easier for you to do right so back then it was really really hard and then it got progressively easier
</details>

>> 在这个过程中，我们在抽象层次上经历过一些非线性的飞跃。但从本质上讲，AI 让我兴奋的地方在于，它为我们提供了一套全新的工具，让我们能在更高的抽象层上工作。这就是改变了的地方。在我看来，人类和企业面临的核心问题并没有变，只是我们现在拥有了一套更好的工具。由于我本身背景偏软件，这带有我的个人倾向。所以从某些方面来说，一切如常。稍微偏离一下主题，最近发生的一件事是……
<details><summary>Original English</summary>
>> uh and we've had some jumps along the way in terms of you know nonlinear uh kind of increases in the in the level of abstraction but like at its base this is the thing that kind of excites me about AI is it gives us a new tool set to work at yet higher levels of abstraction that's the thing that's sort of changed right um and so in my mind like the the problems are still the same you know that humanity is dealing with and and businesses are dealing with uh but now we have a better set of tools and I have a you know kind of software oriented bias that that's my thing but um so so in in some ways it's sort of the the same and and um we'll go off a little bit of a tangent here because one of the things that's happened recently is um
</details>

>> 我们看到了由 TypeSafe 团队发布的 dev 模型……
<details><summary>Original English</summary>
>> you know we had the dev model uh
</details>

>> 噢，对。
<details><summary>Original English</summary>
>> oh yeah
</details>

>> 它真正将本质拉回到了“这终究只是软件”。这展现了开发的另一个维度，它并不是 Transformer 架构，但实际上正在拓宽视野。它所做的就是为构建者的工具箱增添更多工具，并扩大了谁能成为构建者的范围，这非常棒。很多事情依然没变，我们面对的仍然是类似的问题，能够在更高的抽象层上工作是一件好事。我认为当下是做初创企业绝佳时机的理由之一——虽然任何时候都是做创业的好时机，但现在格外好——正是因为在如此高的抽象层次下，AI 让你可以更快地迭代。你可以迅速吸取过去可能需要 6 个月、1 年甚至 2 年才能得出的教训：直接尝试，构建原型并发布，用真实用户和客户进行测试，看看会发生什么。这在以前是完全无法想象的。
<details><summary>Original English</summary>
>> uh you know released uh by the by the type safe folks and what that really takes it back to is like oh well it is really just software and here's another kind of dimension of development that we're having that's not a transformer but is actually kind of opening up and and that's what it does is we're just putting more tools in the tool chest of builders and we're expanding the scope of who can be a builder which is awesome too. Um, but like a lot of it is still the same. We're still dealing with uh, you know, kind of similar issues and it's just nice to be able to work at a higher level of abstraction. Um, and one of the reasons I think this is a great time, it's always a good time to do a startup. Uh, but it's a great time to do a startup is that um, because we're working at such high levels of abstraction, AI lets you iterate so much faster. Oh yeah. So you can learn the lessons that might have taken you 6 months, a year or two years to do. It's like, okay, well, just try it, you know, build something, get something out there, test it, you know, with actual users and customers and see what happens. Uh, and that just wasn't possible before. So, it's uh but yeah.
</details>

### 创业点子选择：缩窄切口与分发壁垒

>> 天哪，我完全赞同。我真希望你能看到我们甚至在自己这家风险投资机构内部构建的所有东西。哪怕只是身处一线，乐趣也大得多。这正好引出了我想探讨的一个问题：回顾历史，尤其是看你创立过的业务，通常都会从一个非常狭窄的产品切入面起步，服务某类非常具体的客户。伴随着这种快速迭代流程，以及以极高速度创造多得多的软件的能力，你观察到这种情况发生了怎样的变化？我很想听你谈谈这个。
<details><summary>Original English</summary>
>> Oh my gosh. I I totally agree with you and this is I wish you could see, you know, all the things that we're even building here at at our at our venture capital firm, right? I mean, and so it's even being on the front lines is so much more fun. This was actually leads into a question I wanted to talk to you about which is I think historically and if you look especially at the businesses you've built um you know you would start in some very narrow product you know surface and for for a very narrow type of customer um how have you observed this changing with that fast iterative process and the ability to build so much more create so much more software so much faster I'd love to hear you talk a little bit about that
</details>

>> 我在创业圈无论是直接还是间接参与都有一段很长时间了，至今我仍将自己视作一个创业者。挑选想法从来都是最困难的事情之一，尤其是对于那些缺乏相关经验的初次创业者。即便是在 30 年后的今天，我觉得自己在这方面的判断力也仅仅是比过去略好一点。创业者在选题时常犯的一个典型错误是，他们认为这纯粹是一门严密的定量分析——搞一个 18 列的电子表格，填入所有系数，然后它就能自动吐出最佳点子。
<details><summary>Original English</summary>
>> yeah I think this this um you know I've been in kind of the startup world directly and indirectly for a long time. I still think of myself um as a startup guy is that uh like picking the ideas has always been like one of the hardest things um especially for like you know first time first- time founders that haven't been through it. Um and even now after 30 years I think I'm marginally better at it than I used to be. Um but one of the things I think the the common mistakes uh entrepreneurs make in terms of kind of idea selection is that they they think it's a matter of like rigorous analysis that we're going to have this kind of 18 column spreadsheet that's going to give me all the coefficients out it's going to spit you know the best possible idea.
</details>

>> 是的，我无数次看到别人拿美国人口普查局的数据大做文章。
<details><summary>Original English</summary>
>> Yeah. The number of times I've seen the like US census file. Uh
</details>

>> 没错，比如列出全美有 18,000 家律师事务所。
<details><summary>Original English</summary>
>> yeah exactly like 18,000 lawyer law firms.
</details>

>> 这根本不相干。
<details><summary>Original English</summary>
>> This is not relevant.
</details>

>> 是的。我和其他创始人交流以及我个人的经历表明，你几乎不可能先验地知道一个点子的所谓“质量”、成功概率或最终走向。检验一个点子是否优秀的唯一真实办法就是去测试它。最终即便你取得了成功，那个成功的产品往往也同你最初的构想大相径庭。人们如今视作成功企业的样子，很多时候与最初的设想几乎没有相似之处；也许原始概念的某些基因还在，但面貌完全变了。这种认知的副产物就是：既然你不太可能事先预知某个想法是否靠谱，那么最明智的做法就是尽快把想法推向市场，以最快速度验证它到底行不行、自己是否应该转向探索别的事情。
<details><summary>Original English</summary>
>> Yeah. Um and and just and what I've experienced and then uh not just me it's not just a data point of one but even you know talking to other founders um is that uh it's almost impossible to know a priority what the quality quote unquote of an idea is or it kind of probability of success um or what the outcome is going to look like and the only real way to test an idea is to actually or know if an idea is good is to actually test it. And what ends up even if you're successful, the thing that you end up with that succeeds will often times or more often than not not resemble the original idea you started with. Right? So what you get to that people now think of as oh that was a successful business. Sometimes it doesn't resemble um you know have some similar similarities maybe you know the gene pool of the original uh you know concepts are still there but um but it's different. So the so the kind of byproduct of that thinking is that um since you're unlikely to know um whether a given idea of a set of ideas maybe you're exploring is going to be good or not um then then the like the smart move is to say let's get the idea out there as quickly as possible and learn as quickly as possible as to whether this or um is or is not a good idea and should I be pursuing something something else. Um yeah
</details>

>> 这一逻辑在今天依然成立。回到 AI 这个点，我们现在能更快地迭代了。然而，依旧困难甚至可能比以往更困难的一点在于分发渠道。正因为现在开发软件变得极其容易，做软件的人会多得多，市场上的选择也会爆发，从而更难穿透噪音触达客户。我深信的一点是在早期尽量“收窄视口”聚焦切入，不仅是我，很多人都表达过类似观点，因为聚焦能提高你杀出重围并学到真知的几率。创业者常犯的第二个错误，是觉得自己一开始就必须画一个庞大的目标市场（TAM），宣称“这能做成一家百亿美元的公司”。拥有把业务做到百亿规模的抱负固然很好，但先告诉我你在前 30 天要干什么。你实际要做的第一件事是什么？先赚到第 1 块钱收入，然后再去考虑 100 块。
<details><summary>Original English</summary>
>> so I think that that still holds today. Okay, unless again back to the kind of AI point, we can iterate faster now. The one thing that's still hard and I would argue maybe even harder now than it was is distribution, right? But that's you because it's so much easier to build software now. Many more people will be doing it. So there's going to be many more options and it's going to be hard to sort of cut through the noise and kind of get into contact uh with a customer. And you know, one of the things I'm a big believer in is kind of starting out with um and I'm not the only person that has uh said this by far, but it's sort of to narrow the aperture in the kind of early days to kind of focus in uh because that sort of increases your odds of of uh you know kind of getting kind of getting through and learning and you know mistake number two that uh entrepreneurs make is that they feel like they need to start with this massive you know TAM where it's like oh this can be a hundred billion dollar business like that's great that you have the kind of ambition and vision that this could 100, but like tell me what you're going to do in the first 30 days. Like what's the thing that you're actually $1 revenue first then let's get to $100.
</details>

>> 即便对我现在而言，无论是在负责创新业务的 HubSpot Next，还是在核心平台内部探索新点子，也都是尽量缩窄视野。我认为最终胜出的是那些迭代周期最短、试错成本最低的人。如果你能缩短这个反馈回路，以更低代价汲取教训，从长远来看，你平均而言总能赢。
<details><summary>Original English</summary>
>> And and I and like even now for me it's like as I explore new ideas uh you know within within HubSpot both for HubSpot next which is our innovation arm or even um new ideas within the core platform. It's like kind of narrowing that field of views like you know can we somehow like I think the the people that win are the ones that have the shortest uh iteration time and the cheapest learning time. So if you can sort of shorten that loop uh and learn less expensively uh whatever the lessons are going to be uh over over the fullness of time you end up and end up winning on average. Yeah.
</details>

### 从 LegalSpot 到一体化平台：HubSpot 的战略演进

>> 是的。不过我仍然认为，当前时刻对于高自主能动性的人来说是最好的时代。诚然，开发软件变得容易多了，但在周六晚上 10 点 45 分我们互发邮件时，能独自坐在电脑前专心写代码、做酷炫东西的人依然凤毛麟角。我想把话题拉回到 HubSpot 最早期的阶段。如果我没记错的话，你们最初做的是一个法律软件产品？可能中间曾有过某种法律产品形态，但它如今演变成了面向中小企业的综合 CRM。你们把那个初始切口扩展成现在的平台，简直不可思议。我想了解你们当初是如何思考从中小企业营销切口逐步向平台拓展的。
<details><summary>Original English</summary>
>> Yeah. No, I I still think though I that this moment is the best possible moment for high agency people. And the reality is yes, there's it's way easier to build software, but there's only so many people who are sitting alone on, you know, 10:45 p.m. when we exchange an email on on Saturday night. you don't hack it on their computer and just go be that person and go build something cool. I I want to go to back to like what I I believe in the beginning of HubSpot you started with >> and correct me if I'm wrong a legal product. Um maybe there was a legal a legal product in there somewhere and somehow that has now become this CRM for small and mid-size businesses. I mean it's unbelievable what you guys have like expanded that wedge into. I'd love to hear how you guys thought about you know of course that evolved into the SMB marketing wedge and so on and so forth but would love to hear how you expanded from there to platform.
</details>

>> 当时我们还在东海岸读商学院，我和合伙人就是在那儿认识的。我们首先被中小企业（SMB）市场的魅力所吸引，那是一个未被充分服务的市场。我简单讲讲背后的故事：我们俩都在软件行业干了很久，他懂市场与销售，我负责产品开发与工程。我们以前都做过企业级软件，深知其中的痛点。对于初创公司来说，企业软件极度枯燥无趣：销售周期漫长、收入过度集中、少数大客户深度绑架你的产品路线图和愿景。
<details><summary>Original English</summary>
>> Yeah. Um so when we first started you know we were in business school that's where my co-founder and I met um here on the east coast and the the thing we sort of ellighted upon was first the the kind of beauty of the SMB as a market. Um it's like it was underserved like and I'll give you the quick story here because it's it's interesting. So we had both been in software for a long time. you on the kind of uh marketing and sales side, my on the kind of product development engineering side. Uh and and we had both done enterprise software before. Uh so we sort of knew that. Um and the challenge with enterprise software was it's uh completely nonfun. Um as a startup entrepreneur, sales cycles are long. You get revenue concentration. You got a small set of customers kind of impacting your product roadmap and your vision and things like that. Um and and so that
</details>

>> 在光谱的另一端则是消费级软件市场。消费级市场的问题在于结果高度两极分化：你要么极其巨大，要么一无所获；而且很多时候只能靠广告变现，无法真正为产品本身收费，用户留存极难维持。从纯市场分析的角度看，中小企业市场兼具两者的优势：它具有企业级市场的属性，你可以为解决的问题直接收费；同时它具备消费级市场的规模，不会面临收入集中风险，你可以服务成千上万甚至数以百万计的客户。我们当初觉得做创业就要挑这种两全其美的领域。于是我们带去参加 MIT 50K 商业计划大赛的最初构想，其实是一款面向小企业的 ERP 软件，相当于“小企业版 Oracle”。
<details><summary>Original English</summary>
>> so there's that. On the other end of the the spectrum, you have consumer markets, right? Consumer companies in the software space. And the issue with consumer markets is that a lot of them have very biodal outcomes that says okay if you're successful it's going to be this massive outcome um and a lot of times you're doing kind of advertising subsidies or figuring out some other way you can't really charge for the product uh because you don't be a chunk kind of thing and the the beauty of SMB was um just from a pure market analysis perspective this is you know two guys in business school at the time it's like oh well SMB has like the beauty of enterprise in terms of you can actually charge money for problem that you're solving. It's like there's nothing wrong with charging money, but it has a scale of consumer that you're not going to have this revenue concentration. You can have tens of thousands, hundreds of thousands of millions of customers. And so you sort of have the kind of best of both, right? And um so that was our kind of original thinking like, oh, if we were to do a startup like uh and so then our original idea that we took to the MIT 50K uh competition was um like ERP software like an oracle for small business. Y
</details>

>> 再次回到“收窄视口”的逻辑：当时正值软件从 C/S 架构向 Web 架构迁移，我们觉得应该有人做一个专为中小企业设计的集成化系统。但在参赛时我们意识到题目太宽泛了，于是进一步收窄视口，将其命名为 LegalSpot。当时 HubSpot 这个公司名字已经注册了，但为了在早期验证市场，我们围绕“律所专用 ERP”写了商业计划书。就像你前面吐槽的，普查局数据显示全美律所数量众多，乘以客单价就能在商学院的 PPT 和表格里算出完美的数字。
<details><summary>Original English</summary>
>> um and the way this going back to the kind of narrow the aperture it's like okay well that seems like an interesting thing because you know we're going to this kind of transition from client server to to the web it's like like someone should create like an oracle for for small business that's everything's integrated kind of works together it's kind of built for SMB um and when we went to the business plan competition uh we said that's like too big let's narrow the aperture and let's call it legal spot uh the HubSpot company name had already existed but the thing we wrote the business plan around um purely as a way to kind of test the market early on is to say let's focus on ERP for law firms just as a narrow and you know back to the your original act like ah there's you know all the US census bureau things oh there's lots of them out there we can multiply x by y and it makes for great uh business school kind of spreadsheets um and poweroint decks
</details>

>> 我们有动手测试水温的习惯。在我们还在商学院推演想法时，早期调研得出的教训是：律所是一个极难做销售的市场。当我们和律所探讨 ERP 和解决方案时，他们唯一感兴趣的部分反而是市场营销和网站搭建。
<details><summary>Original English</summary>
>> and so and so we did that and and uh you know we have a kind of propensity for kind of testing the waters and one thing we learned early on uh in that uh while we're still in business kind of noodling on the HubSpot idea is like that's not a fun market to sell into. Uh and as we talked to the law firms and we talked about, you know, ERP and what the solution, you know, would or could be, uh the the marketing and the website, all that was the part that was the most interesting to them.
</details>

>> 他们会说：“等等，你能帮我拉来更多客户吗？”
<details><summary>Original English</summary>
>> Yeah. They're like, "Wait, hold on. Can you help me find more customers?"
</details>

>> 没错。他们说：“工时记录这些功能无所谓，你能帮我找到更多匹配的目标客户吗？”于是我们面临两个选择：坚持做面向中小企业的 ERP，还是做面向中小企业的营销工具？我们几乎是扔硬币决定的。虽然我们做了一些基于小样本数据的推演，但人生苦短，事实证明律师是第二难做销售的客群，仅次于软件工程师。
<details><summary>Original English</summary>
>> Exactly. Yeah. I was like, "We got the time tracking and all that that doesn't really matter. Can you help me find more clients that are the ideal fit and things like that?" And so we were sort of like down to those two ideas like oh do we kind of stick with the kind of ERP for um for SMB or do we do this kind of marketing for for SMB and we chose we almost could have flipped the coin. We almost could have uh we we didn't we were you know a little bit more deliberate about it and we did extrapolate from a a minor set of data points but it was like life is short. Uh as it turns out lawyers uh are the second hardest market to sell into. Software developers being the hardest. Uh it's like
</details>

>> 于是你们开始切入中小企业营销工具。后来它演进成平台以及功能完备的 CRM。这个演进是从第一天就深思熟虑好的吗？我问这个是因为现在很多团队可能在使用新的 AI 媒介，比如早期的语音交互产品（我认为这依然蕴藏巨大机会，你们可能也在探索），或是客服聊天界面，大家都想成为各自领域的“HubSpot”。你能讲讲你们如何走过这段产品历程，并通过构建反馈回路从最初的切口发展为平台的吗？
<details><summary>Original English</summary>
>> so now we're in uh you know navigating the SMB kind of marketing uh product. Of course that then morphs into you know more of a much more of a platform and a full CRM. Was that thoughtful from day zero? And I the reason I'm asking is I think there's a lot of folks out here that maybe are using some new AI medium whether that's you know commonly early on it was voice voice products and I actually still think that's a huge opportunity for so many folks. Um I'm sure you're exploring that at HubSpot. uh or maybe there's there's some sort of support kind of chat, you know, interface >> and everyone of everyone always wants to end up being the hubspot for whatever use case, right? So maybe talk a little bit about how you you navigated that product journey and created the right the right loops to get to more of a platform from this initial wedge.
</details>

>> 我们最初做的是一套营销应用套件。回答你的第一个问题：在业务起步的第一天（t=0），我们完全没有“未来某天要成为 CRM 平台”的想法，任何商业计划书里都没有写过。但随着公司演进，我们面临了需要打造“第二款产品”（或所谓的“第二曲线”）的节点。这可能带有 HubSpot 自身的特点，但我认为该规律具有普遍性。当时有两件事同时发生：第一，我们做营销软件时意识到，营销和销售/CRM 业务距离极近，是天然的相邻品类；第二，在公司成立五六年、上市前两三年左右，我们对已有客户群做了一次 CRM 使用情况调研。结果发现，20% 的客户在使用 Salesforce，另外 20% 使用其他各类 CRM……
<details><summary>Original English</summary>
>> Yeah. So we started off as a um a suite of marketing applications and uh to answer your kind of um the first question, this was not at time t equals zero, we think we're going to be a CRM platform someday. that was not um it was not in any of our PowerPoint decks. It was um and and so yeah, we we didn't have that. But as the company evolved, we sort of and this may be a little bit kind of idiosyncratic to HubSpot, but I don't think so. I think the pattern still exists even outside of a CRM. You sort of have the need for um kind of product number two, right? Like the second actor or however one tends to phrase it. And we sort of hit that. So a couple things happened simultaneously. uh we were in the marketing software business and one of the things we sort of recognized is that being in the marketing software business um you know was very very close to you know sales and CRM that was the kind of the adjacent category so that kind of made logical sense. Uh the other thing that we sort of learned um you know once you know we had a bunch of customers is that we did a survey of our customers um this is you know maybe a couple years before the IPO um so maybe five six years into the company uh and just to see which CRM they were using and we discovered um that 20% um were using Salesforce.com uh another 20% were using some other CRM other than Salesforce.com.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但有 60% 的客户完全没有使用任何 CRM。
<details><summary>Original English</summary>
>> Uh but 60% were not using a CRM at all.
</details>

>> 明白。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这让我们觉得不可思议。这些人在付费使用 HubSpot 软件来获取销售线索，他们不是随机的路人公司，而是真金白银付钱给我们的人。那些线索最终都去哪儿了？如果没有系统承接，他们把数据放哪了？
<details><summary>Original English</summary>
>> And that was insane to us. It's like, wait a second. So you're using HubSpot software, you're paying us money. So these are not like random, you know, companies. These are people paying us money um to generate leads. What's happening to those leads? Like if they're not where you put like what?
</details>

>> 于是我们意识到，这些企业理应使用 CRM。我和合伙人的思考逻辑非常直白朴素：既然品类存在，市面上也有优秀的产品，他们为什么不用？归结到底有两点：第一，望而生畏，CRM 复杂的概念把他们吓住了；第二，太昂贵，他们觉得启动成本过高。我们判断 CRM 是一个优质的相邻品类，而且我们本来就需要第二款产品；从战略上看，现有 CRM 厂商随着时间推移迟早会向下游侵入营销软件领域，我们不可能永远只守在营销工具这一单一品类里。
<details><summary>Original English</summary>
>> And so that was so the the thing that we sort of ellighted upon was like, okay, well >> like these companies should be using a CRM. So, you know, we're u my co-founder and I are very um weirdly s simple-minded. It's like, okay, well, why are they not using a CRM? It's like it's the categories exist. It's not and there are great companies with, you know, great products out there. And we came down to it's like, oh well, it's uh overwhelming. They're just intimidated by the idea of a CRM. Uh it's too expensive. They think it's going to cost too much to kind of get going with a CRM. Uh and so we made the decision that it was a nice adjacent thing. We need a second product anyway. there was a strategic value to saying okay well over the fullness of time um the existing CRM players are likely going to get into the marketing space uh and we're going to have so even if we wanted to stay in in the marketing software category it's unlikely that we're going to be able to do that forever right so that all those things sort of converged around the same time period and so when we launched the CRM um you know we sort of addressed both of those issues like okay so we're going to build a CRM and we're going to address the 60% it's like okay for those people that have not picked a CRM yet.
</details>

>> 于是我们决定做一款 CRM 来拿下这 60% 的空白市场：既然别人觉得难用，我们就做当时市面上最易用的 CRM；既然别人觉得贵，我们就直接免费开放。不是免费试用（Freemium），而是完全免费。HubSpot 的理念一直是“在索取价值之前，先创造客户价值”。如果能提供有用的东西，并且能靠已有营销软件业务的现金流来提供补贴，我们就移除了所有门槛。随着持续迭代，我们认识到要在 CRM 领域获胜，它必须成为一个平台，因为 CRM 天生就具备平台属性。从第一款产品扩展到第二款战略相邻产品是一段漫长的旅程。
<details><summary>Original English</summary>
Why have they not done it? Too hard. Okay, let's make the easiest CRM that's ever been conceived at that point in time. We were focused on SMB, so that was a core strength anyway. And we're going to take the it's too expensive off the table because we're going to make it free. >> Not premium, free. It's like, okay, well, and this this has been sort of the um kind of philosophy at HubSpot is like create customer value before you try to extract it. It's like if you can just get out there with something that's useful and we could obviously subsidize it with the kind of the marketing software business that we already had. Um but that that was the idea. It's like okay well then we've sort of removed the obstacles uh and then it's like let's get out there and then uh and then as we iterated we sort of learned um you know that in in order to win in the kind of CRM space it needed to be a platform right it's like it can't just be like because CRM is almost by definition now um and even then um are platforms. So that that was a journey just going from product one to product two expanding out into a strategic adjacent thing.
</details>

>> 对创业者来说，另一条可借鉴的经验是：尽力去解决客户的“完整问题”。无论你怎么界定边界，核心在于“我们试图解决的实际问题到底是什么”。在 HubSpot 成立之初，我们提供了一个非常广泛的营销应用合集，这违背了外界所有的常规建议（常规建议通常是“把一件事做到极致”）。但我们把所有东西都做了：内容管理、SEO、落地页、表单等等，尽管在每一个细分领域都有极其优秀的公司和独立产品。我们之所以全做，是因为这是解决客户真实痛点的唯一途径——客户被各个工具的割裂与碎片化彻底搞懵了，我们必须通过一体化的方案来交付。过去 20 年我们一直坚守这个逻辑，今天依旧如此。
<details><summary>Original English</summary>
But then and this is the other thing I think that carries over to um the entrepreneurs listening is that do what you can to solve like the whole customer problem uh like how however you define it whatever circle you draw it around it's like what's the actual problem we're trying to solve. So even when HubSpot started um we had a very broad base of marketing applications and which goes against every piece of advice you get and that I've given it's like do one thing really really well. We did all the things. So we had content management and SEO and landing pages and forms or whatever and they were great companies with great products in each of those categories. The reason we chose to do it all is the only way for us to solve the actual problem customers had which is they're intimidated by this fragmentation. Everything's all right. We had to do it all in one offering. And so we sort of carried that idea with us for 20 years and we still do the same thing now. It's like what's the actual problem we're trying to solve?
</details>

### 构建生态的本质：像做产品一样对待开发者

>> 这非常有意思。事后复盘时，大家谈及市场进入策略，往往会提到“棕地策略”（去替换那些已经在核心系统上的客户，寄希望于周期更迭时客户愿意更换底层软件），或者“绿地策略”（去赢取那些此前从未采用过软件的新客户）。外界往往认为 HubSpot 从一开始就有着深思熟虑的绿地策略，但现实是你们发现很多客户原本就没有系统，于是顺势构建了产品。按这种顺序推进完全没问题，只要做扎实了，依然能做成庞大的企业。在这套初始方案周围建立生态是另一关键环节，HubSpot 在这方面做得很棒。在早期构建生态的过程中有哪些核心心得？如今随着 AI 的引入，生态建设受到了怎样的影响？
<details><summary>Original English</summary>
Well, it's so interesting because I think you know with hindsight everyone always talks about okay well you know from a go to market strategy there's you know the brownfield approach of if you go after all these people who are on every core system already and you rip and replace it and hopefully you're in the middle of a cycle like this where everyone's willing to revisit that or you go after green field and you you try to win all these new businesses who have never adopted software before and I think uh the standard thinking on HubSpot is like oh well it was just like a very thoughtful from the beginning let you know let's go after the green field and the reality is it's like actually no like all of our customers just didn't have it and we built it and um it's totally fine if you do it in that order and you can still be a massive company if you if you nail it. Um, so interesting. How how did you think about, you know, another part of this is, you know, building the right ecosystem around that initial offering though, right? And I think that's something that HubSpot has done such an amazing job of maybe what are the key learnings from the early days of building the ecosystem and then now that you you know it's such a different role today where that eos you're you're able to do a lot of that in different ways. I'd love to hear you talk about that with you know the advent of AI and how that's impacting the ecosystem as well.
</details>

>> 在我的职业生涯中，我长期作为平台与生态的使用者，深知这其中的双向感受。这并不是贬低以往或现在的任何平台，但生态和平台的发展往往存在一个倾向：平台提供商起初极力吸引开发者，希望大家基于核心平台构建应用和创办企业；但随着时间推移，他们往往会——无论有意还是无意——踩踏这些开发者，收紧权限、关闭接口。比如 15 年前的 Twitter，早期是一个非常开放的生态，可谓百花齐放，催生了大量第三方客户端、产品和公司；但后来他们关停了接口，对开发者变得极不友好甚至带有敌意。
<details><summary>Original English</summary>
>> Yeah. Uh and I've been a consumer of platforms and ecosystems for you know most of my professional career. So I sort of know what it's like on both sides. Um and this is no disparagement to any of the existing platforms then or now. But uh what tends to happen with um ecosystems and platforms is that um the platform providers will start um you looking to attract the developer ecosystem and and get people to build apps or build uh you know companies that are kind of adding value to the core platform. Uh but over time what ends up happening is that um either intentionally or or unintentionally they sort of kind of stomp over uh those developers. They'll close things up. They'll shut down and we saw this I can we can talk about this as story is 15 plus years old now like Twitter had this in the early days right they had the original Twitter was this kind of very open ecosystem. were a platform and we and and literally a thousand flowers bloomed back then. Lots of Twitter clients built lots of people um you know built uh products and and uh and companies uh on that original set of APIs. And it's not exclusive to Twitter. That's just what jumps to mind right now. But um but then they sort of closed it down and became you know everything from like developer unfriendly to almost developer hostile, right?
</details>

>> 我们吸取了这些教训，努力成为当年我们做开发时梦寐以求的那种平台，延续 HubSpot 友善、受人喜爱的品牌形象。我们是资本主义者，自视为主流且温和的资本主义者——大家都是来做业务赚钱的，我们尽可能坦诚透明。我们会告诉合作伙伴：我们无法承诺永远不做某些功能，但如果我们在寻找市场空白，我们会明确指出哪些领域存在机会且我们极不可能进入。这帮我们在广泛的群体中建立了信任。此外，做生态系统和做产品极其相似，底层逻辑是一致的。作为一名技术骨干，就像我们思考核心客户的“价值实现周期”（Time to Value）一样，我们也必须考量开发者的“愉悦达成时间”（Time to Joy）——从调用 HubSpot API 跑通第一个程序，到通过生态赚取第 1 美元，我们能否缩短这个链条、降低门槛。
<details><summary>Original English</summary>
Um and so one of the things that I think this has kind of helped us build the ecosystem is that we've sort of take the taken those lessons to heart that says okay well let's be the platform that we wished would have existed for us back when we were doing you know very incendurary things like let's you know be the sort of carry that HubSpot brand of being kind of friendly likable um and that's like we're we're a we're red blooded capitalists uh we like to think of ourselves as like warm-hearted red-blooded capitalists like okay everyone's here to make money here's what we're doing and we try to be uh even with our uh with our partners uh try to be as open a book as we can be in terms of like okay here are things that we're we can't promise you we're not going to do this but here's what we're doing if we were looking for white space if we were you here's the things the kinds of things we would do that we think there's an opportunity that you know we're highly highly unlikely to kind of traverse into that territory uh and that's worked so we've built trust um you know across a a wide pool of people now then some of it's just the uh you know building an ecosystem is a lot like building a product you have think of it that way is to say okay well in um as a developer at heart it's like okay well in the same way we think about time to value for the core customers we have to think about time to joy for a developer how fast can someone get to oh I got something working on with the HubSpot APIs to the oh I made my first dollar you know working with the HubSpot within the HubSpot ecosystem whatever that is can we compress that can we reduce the time to joy um you know for for that that class of customer yeah so
</details>

### 黄砖路隐喻：避开前沿实验室的坦克

>> 祝贺你们建立了这样一个繁荣的生态。顺着这个话题，转到你刚才提到的《黄砖路》那篇文章。我很想听听你对当前前沿实验室试图涉足的那些工作流有什么看法。HubSpot 包含许多体验，而那些横向产品正试图把这些环节囊括进去。你如何思考需要防守的领域，以及在哪里能够构建最持久的价值？
<details><summary>Original English</summary>
>> no to totally and uh no congrats on building such a thriving ecosystem. Maybe just transitioning a little bit now into, you know, the the essay and the conversation we were having around it. I'd love to hear how you think about the things that you're maybe concerned about uh with regard to the workflows that the the labs are kind of going after. And of course, there's many things inside of the HubSpot experience. I think that that those horizontal products are trying to pull in. Um and how you think about like the the area that by which you want to defend and and where you can kind of build the most durable value. would love your commentary on that.
</details>

>> 我先说明，作为 HubSpot 的联合创始人兼 CTO，我的观点自带立场，但这并不意味着我是错的。对于置身局外的人来说，就像你文章中绝妙的“黄砖路”比喻：眼前有一条通往翡翠城的平整明亮的康庄大道，看似空空荡荡，但你不知道有一整队重型坦克正全速开过来，而且随着技术进步，这些坦克的推进速度越来越快。
<details><summary>Original English</summary>
>> Yeah, a few thoughts. Uh, one is I'm going to open this with a have a very very biased point of view. Uh, given that I'm co-founder CTO of HubSpot, >> that doesn't necessarily make me wrong. Um, >> so the a few thoughts. one is around um and we'll just talk more broadly and then we can kind of zero in on uh some of the specific things is that you know for those on the outside looking in um it's like it feels like and this is your kind of yellow brick uh road which I you know I love the essay the the idea and the analogy was you know very apt which is like there's this you know well praved shiny bright road that's kind of pointed to the emerald city or whatever how could you not like walk down it's like and it feels empty at the time right but you don't know that there's like a like a fleet of tanks coming down that road. Um and and they're getting faster. It's not that that they're even slow because they've invented this new thing that makes them even go fast. >> Um
</details>

>> 这正是你那篇文章的前提，我完全赞同：他们确实会沿着那条大道一路横扫。这是一条通往万亿美元估值与市值的宽阔道路，但在这条主路之外，还有大量的机会。我习惯用框架来思考，创业者往往在两个极端上犯错：其一，轻视实验室，宣称“ChatGPT 无法做这个，或者 Claude Co-work 无法做那个，我们要去填补这个空白”。这种想法让我担忧。这里有两个误区：第一，如果你在这个缺口后面加上“目前”两个字（比如“ChatGPT 目前还做不到”），如果这句话听起来成立，那它就是个伪机会；第二，混淆了“产品”与“公司”的边界——ChatGPT 这款产品现在不能做，并不代表 OpenAI 这家公司不会做，他们随时可能推出一条新产品线。所以你必须想清楚那条大道的宽度。大道自身在变宽，你不仅要避开主路，最好还要保持一定距离。
<details><summary>Original English</summary>
>> and so and and this was kind of the premise of your essay, which I wholeheartedly agree with, is that uh yes, they're going to um they're going to barrel down that road. Um and it's it is a shiny nice road and and hence the trillion dollar um you know, valuations um and soon to be market caps. But uh but there's so much opportunity outside of that. And so here's like a I'm a framework kind of guy like here's a mistake I think entrepreneurs make on both sides of it. Uh one when they dismiss it they say oh well chat GPT doesn't do this or cloud co-work doesn't do that well we're going to do this we're going to fill this gap. Um and those are the ideas that uh make me nervous right because there's and there's two things sort of I think misguided about that thinking. One is if you can just append uh the word yet to it uh and it still holds water that's a problem. It's like, oh, Chad GPD can't do that yet. Does that ring true? If it sort of does, it's like, okay, well, that that's a problem. That's thing number one. >> Thing number two is what I think of as u measuring the product versus the company. It's like, oh, >> chat GPT can't do that. It's like, okay, but can OpenAI the company do that? Like maybe, you know, it's a new product, a new product line or whatever. It's like, so you have to sort of think through how wide is that road? Um, you know, like, okay, maybe the road itself is getting wider. Fine. So maybe stay off the road, but maybe also stay out, you know, a little bit outside, it's like, okay, if there's all things being equal, if you can just be a little bit further away. So even if as they expand when you can and it's somewhat predictable. Um, so that's kind of thing number one is to make sure um that and and either, you know, pick things that the frontier model companies um either have a structural constraint uh that they just can't do regulatory wise, whatever it is, um or have a what I think of as like an incentive constraint.
</details>

>> 所以你要选择前沿模型公司面临限制的领域：要么是“结构性限制”（受制于合规等因素无法触碰），要么是“激励机制限制”——他们理论上能做，但实际去做的概率极低。以 HubSpot 为例，我是 OpenAI 的投资人也认识 Sam Altman，假设任何一家前沿模型公司某天醒来，眼馋 CRM 行业以及 HubSpot 超过 30 亿美元的年收入，决定成立团队抢占这个市场。他们有足够的智力和野心吗？当然有。但正是由于这种野心，OpenAI、Anthropic 或其他前沿实验室极不可能真正去做这件事，因为这不符合他们的核心诉求。
<details><summary>Original English</summary>
Yes, they could do that, >> but the odds of them doing that are really really low because I'll just I'll use HubSpot as an example. So, let's say um any of the frontier model companies um I'll pick on Sam Alman since uh I'm an investor in OpenAI and and know Sam. It's like he could wake up tomorrow and say, you know, that CRM industry that looks awfully tempting and that uh you know three plus billion dollars of revenue that that HubSpot has, we're going to make it our mission or somebody within the company's mission to go go take that revenue. Are they smart enough? Yes. Do they have ambition? Yes. But it's that very ambition that makes it highly unlikely that the team at OpenAI or SAM or anyone or same thing with Enthropic or any of the frontier model companies, they're unlikely to do that. Uh and but that's what it would take to be able it's like okay so my thesis and this kind of winds back to where do you find the pockets of opportunity that are off the yellow brick road which is one thing we know for sure is the frontier model companies have invested hundreds of billions of dollars kind of building doing the pre-training as as as you well know and so their whole business effectively now is um taking the capex that they've spent and the money they're continuing to spend and say how do we sell Infer how do we sell tokens how do we kind of monetize the thing that we've built? Yep.
</details>

>> 前沿模型公司已经在预训练上投入了数千亿美元，他们现在的核心商业闭环是如何消化已发生的资本支出以及持续投入的资金——即如何售卖推理、如何售卖 Token、如何实现变现。他们通常有两条路径可选：一条是直接面向全球所有人卖 Token，通过消费级产品触达大众，或者直接向财富 500 强企业（如摩根大通）直销，派驻大批全职员工提供服务，无需中间商；另一条路径则是通过 SaaS 公司、初创团队等作为推理服务的转售分发渠道，由熟悉垂直行业、掌握特定客群分发优势的伙伴来消耗 Token。这并非二选一，他们会同时推进这两条路：在通用消费端自己主导，同时将 AI 作为基础设施对外开放。这与 15 年前我们将 AWS 和云计算视为基础设施如出一辙。
<details><summary>Original English</summary>
>> Awesome. uh it's a tale as old as time and they have two choices. Uh like one is they can say oh we're just going to go directly to everybody on the planet and sell them tokens and they'll do that by virtue of the consumer product and they'll do that uh and even on the high end they'll say okay well we're going to go directly to Fortune 500 JP Morgans and we're going to sell them tokens because we're going to sell them there doesn't need to be an intermediary and we'll have an army of FTEEs that can help us do that. Uh and that's certainly a path and they're kind of walking down that path. Another possible path is it's like okay well there are uh you know SAS companies and products and companies and startups or whatever that know their particular domain know their market have some distribution or have something that allows them to sell tokens and be a reseller of inference for lack of a better lack of a better term. It's like okay well and they don't actually this is not a binary choice they can do both they can say oh for these kinds of things for consumer we want to own that we don't want other things you know people doing like a chat GPT equivalent uh we're going to own that >> but there's going to be lots of opportunity to say okay well think of um AI as infrastructure in the same way we thought of AWS and and cloud comput as infrastructure 15 years ago
</details>

### 模型基础设施化：消除供应链依赖风险

>> 这完全是一回事。作为创业者，我认为现在围绕 AI 领域构建产品远没有 2023 年那么令人胆寒。在 2023 年，我个人的经商准则本来极少：第一，绝不开餐厅；第二，绝不当收租的房东；第三，绝不与 Sam Altman 竞争（尽管我意外碰上过几次）。但在 2023 年回看，如果让我下注，我会觉得他们已经遥遥领先，掌握了某种点石成金的秘方，没人知道未来是否有人能追赶上来并承担得起庞大的资本开支。
<details><summary>Original English</summary>
>> it's the exact same thing it's like and um and as entrepreneurs once again I'm biased but not wrong. I think it's less scary now to build um in and around uh kind of the AI arena than it was in 2023. And the reason I say that is back in 2023 um and I have, you know, very few uh uh rules for business. One is uh never own a restaurant. Number two is don't ever be a landlord and charge rent. And number three is never compete with Sam Alman. Um which I've accidentally done a couple times. Um but the the reality though is that at the time in 2023 if we take ourselves back um if I were a betting person I would have said they are just so far it was like they had figured out this kind of magic elixir or something like that. It's like I have no idea if anyone ever is going to be able to really solve it in the and and be able to pull all the things including the capex spend that was going to be necessary. Uh I was thankfully wrong about that.
</details>

>> 值得庆幸的是，从创业者和生态的角度来看，我当时判断错了。现在的局面是，模型即使不能完全被称为大宗商品化（Commodity），但作为普遍存在的基础设施，无论在价格还是可替代性上都在走向大宗化。像 OpenRouter 这样的工具之所以存在，是因为模型切换变得非常简单。在 HubSpot 内部以及大部分 SaaS 公司中，大家都在对用例进行解耦和模型路由，根据不同任务分配最合适的模型。这样一来，创业者无需担心出现单家公司垄断关键生产要素的供应链卡脖子风险。我们拥有开源生态，也有丰富的商业产品。只要避开那条主干道，你有充足的底层选项，完全不用担心被压缩利润空间。
<details><summary>Original English</summary>
Like you know thankfully in terms of from entrepreneurs and from an ecosystem perspective because where things stand now is that um models I'm not going to say they're a commodity but part of the virtue of them being as common as they are is they are infrastructure and they're going to trend toward both from a pricing perspective and even a fungibility perspective. Right now, you know, things like open router exist because it's easy to sort of swap out models back and even within HubSpot and most SAS companies are doing some form of uh use case decomposition and model routing to figure out what's the right model for the for this task. The byproduct of that is that like you can sort of swap out what you need or whatever. So there's less reason to be scared because you don't have this kind of uh supply chain power where like this one company controls the one crucial ingredient for you to build the product and solve the problems that you're solving. We don't have that right now. We have open source. We have lots of great commercial products. Um, so as long as you stay off the yellow brick road, it is completely possible now that you're not going to get margined out or whatever because you have options. There's not just one company providing the one key ingredient to building an AI an AI native company.
</details>

### 界面与工作流：Uber Eats 类比与第二大脑

>> 完全赞成。如果不做基础大模型，初创公司或 HubSpot 真正的壁垒依然在于构建高质量的软件本身，这才是向客户交付价值的核心层。其他现成的基础设施都可以打包集成并服务客户。正如我文章中提到的，通过各种闭环测试识别这些细分领域，并在这一层建立规模报酬递增或滚雪球式的复利优势。很想听听你对这一层复利闭环与长期优势的思考。
<details><summary>Original English</summary>
>> No, totally. And I think that the other piece of this which you kind of touch on it's like okay of course with enough focus but it's it's also just that uh the advances or the advantages you're going to build is uh as a as a startup or as a HubSpot or whoever it is if you're not building a foundation model. It's you're actually you're building still high quality software. I think that is the layer that you're going after to provide value to your customer. And so of course there's all these other great pieces of infrastructure that you can now package up and then give to those those uh you know those customers. And and the way that at least I think about it and of course I argue in this essay is like you know there's like there's loops, there's tests, there's things that you can kind of do to try to identify these pockets, but then hopefully you're building some sort of, you know, increasing return to scale or compounding advantage at this layer. And so I'd love to hear how you think about this, you know, HubSpot or any of the things you're working on as it relates to the loops you try to build in these products or the the advantages you're trying to to build in.
</details>

>> 归根结底全是复利闭环，Joe。无论是在 AI 出现前还是出现后，这都是商业的核心本质。我回溯一下之前按在栈里的一个思考点：今天恰好是 OpenAI 的开发者日（DevDay，9 月 30 日），就在我们录制之前……
<details><summary>Original English</summary>
>> Yeah, it it's compounding loops all the way down, Joe. Um, of course that's that's the the entire name of the game. Before AI, after AI, but um, a couple of things I'll say. So I'm going to rewind. Uh, I pushed one idea on on the stack. I'm going to pop it off and and talk through it. Is that so the you know, one of the questions we get, you know, back on the um, if you were an entrepreneur kind of evaluating the ideas. Um, it's like, okay, well, so today was uh, OpenAI's uh, dev day by the way. So, September 30th. So, you right before this call is uh our recording.
</details>

>> 怎么了？
<details><summary>Original English</summary>
>> What's that?
</details>

>> 我是说我们给听众明确标注了录制时间戳。
<details><summary>Original English</summary>
>> I said we're dating the recording for for the the audience.
</details>

>> 没错，带时间戳的。
<details><summary>Original English</summary>
>> So, you now know timestamped.
</details>

>> 一年多前 HubSpot 是第一家推出 ChatGPT 连接器的 CRM 公司，后来我们也为 Anthropic 做了类似支持。常有人问我们：“大家都通过 ChatGPT 或 Claude Co-work 进来，这难道不会削弱 HubSpot 的长期价值吗？”我能理解这种顾虑，我的反驳是：界面确实重要，但其重要性存在一个光谱。光谱的一端就像 Uber Eats 或 DoorDash——它们的应用体验很好，但 App 本身其实很容易被替代；真正有价值的是背后的网络、与餐厅的合作关系、能随时到店取餐派送的骑手履约网络与物流系统，这才是难以撼动的壁垒。光谱的另一端则是“界面即全部产品”，没有界面就没有任何价值。
<details><summary>Original English</summary>
>> Exactly. You know exactly when this is being recorded. Um so, and HubSpot launched our um we were the first, you know, CRM company to do so our connector to chat GPT over a year ago and we have some more one for Anthropic. And one of the questions, you know, we get sometimes is like, oh, well, doesn't that sort of diminish the long-term value of HubSpot? It's like okay if everyone's coming in through chatbt or through cloud co-work or something like that isn't that like just saying eroding the kind of long-term value and um I and I understand the reasoning my sort of counter that is that um like the interface matters uh but it matters to varying degrees there's a spectrum so let's say one of the spectrum I'm making this up as I go um let's say you look at something like an Uber Eats or a Door Dash right it's like okay they have very compelling apps but it's like okay well the app is trivial. What's actually valuable is the network that they have, the partnerships of the restaurants and things like that. So, a driver can show up, pick up food and deliver it to the logistics and all of that. That's where the actual value is and that's the part that's sort of hard to displace. Um, there are other things where the the interface is the entirety of the product, right? That's all there is. If it weren't for the interface, there would be no value.
</details>

>> 大多数企业级应用实际上更偏向 Uber Eats 这一端——虽然不像外卖平台具备强双边网络效应，但真正值钱的是正在发生的实际工作，界面只是达到目的的手段。对 HubSpot 而言，界面之所以重要，是因为营销和销售人员需要达成特定业务成果，在 AI 出现之前，界面是人与计算机交互的通道。HubSpot 过去立足的核心是理解客户要解决的痛点并构建极简的交互界面，但这绝非价值的全部。在整个价值链条中，界面占比绝不可能达到 99%。从桌面 C/S 软件迁移到 Web 浏览器时代也发生过类似的事情：当年大家用 IE 或 Mozilla 浏览器访问应用，但微软和 Google 并未因此垄断整个应用生态，反而有大批 SaaS 公司应运而生。浏览器只是分发入口，避免了在千百万台电脑上逐一安装软件。
<details><summary>Original English</summary>
So, and and and I think most business applications actually sit more towards the Uber Eats kind of thing, right? Not in the sense that they have uh network effects like Uber Eats and Door Dash do, but in the sense that the actual thing that's valuable is the work that's happening. The interface is a means to an end. Mhm. >> The only reason the interface is important to HubSpot is because uh marketers and sales people are trying to get something done or deliver on certain outcomes and the interface is the way but in order for them to communicate with a computer and before AI happened. It's like HubSpot's claim to fame was like oh we understand the problem you're trying to do whatever and we've actually built the interface that's super simple to help you kind of get there but that was not the entirety of the value. Now one can argue where on the spectrum you know you know HubSpot falls but I can guarantee you it does not fall in the the interface has you know 99% of the value and so my argument is that in the same way you know you know everything kind of comes back around again is that uh when when we saw the original kind of SAS development just moving to the kind of web- based application world we had the same kind of thing it's like okay well we have client server apps you know running on our desktops you know back in the day uh and then we had you know this browser thing come along the internet explorer and you know later Mozilla uh you folks uh know well um and it's like okay well now my software is running inside of a browser but as it turns out like Google did not own the entire application stack right there was an entire lots and lots of lots of software companies that got built and it's like oh the interface became the browser because that was a convenient way to get to the actual kind of product that you needed to get to browser was a better way than installing something on you know 19 uh million uh computers
</details>

>> 如今的情况类似，不同之处在于 AI 具备真正的智能和行动力。但像 ChatGPT 和 Claude 这类产品扮演的其实就是新时代的浏览器，人们通过它们来消费服务。HubSpot 这样的企业会作为插件或生态的一部分接入其中。在开发者日上我们看到他们不断丰富 ChatGPT 内部的能力并推出生态插件架构，这完全合乎逻辑。因此对于 B2B 领域的创业者，我的基本建议是：不要在界面上过度纠结，关键是找到帮客户达成目标的最优路径，提供成本最低、延迟最低、摩擦最小的交付方式。
<details><summary>Original English</summary>
we have a similar thing now like and it's different right because uh the AI doing work. It's doing actual smart things. They can do more things. >> But if you just look at the kind of chat GPT and cloud cos >> they are the new browsers like this is the way people are consuming value and there will be companies like HubSpot that sort of plug in and this is the thing we saw from dev day and we saw it you know last year and we continue to see it's like oh they're going to increase the richness of what's available within chat GPT. they launched a you know this kind of go at it a marketplace for people to plug in a um you know in plug-in architecture and all those things which makes complete sense to me um so so my fundamental philosophy which I think holds true for most people looking to at least in the B2B world is that >> like don't overthink the interface figure out what's the best possible way to achieve the outcomes your customers are looking for um and then the other you know value that you can bring uh is around like what's the economic um you know best way, what's the lowest latency way, what's the lowest friction way to kind of accomplish those outcomes.
</details>

>> 大语言模型是人类历史上最杰出的技术之一，但我的公开观点是：任何能通过结构化查询确定性解决的问题，务必用结构化查询确定性地解决。绝不要用模型推理去解决一条数据库查询就能搞定的事情，那毫无意义。如果数据本身就在那里，比如问“我们从爱尔兰获得了多少客户或收入”，你不应该去翻阅 800 万条 Slack 消息和邮件来进行推理；哪怕数据散落各处，底层也应该是一次数据库查询，而不是调动一个智商 300 的大模型去硬猜。
<details><summary>Original English</summary>
Um and often like an LLM is very very good at lots and lots of things. It's the most you brilliant technology we've had in the history of humankind. But uh one of the things I've kind of gone record of saying is like anything that can be solved with a structured query deterministically, solve with a structured query deterministically. Don't use inference to solve something that a query can solve. It doesn't make any sense. So even if the data were there, it's like, oh, >> if your question is how many customers or how much revenue are we getting from uh from Ireland, >> you shouldn't have to troll through 8 million Slack messages and emails or whatever infer the answer. Yes, the data is probably there somewhere. >> Yeah. >> But that should be a database query that should not be uh you know, solved through inference and and throw a 300 IQ model at it.
</details>

### 系统原语与上下文图谱：软件重写的平行宇宙

>> 许多公司在梳理定价模式与用量逻辑时也在面对类似困惑，这本身就够单独录一期播客了。最后想请教一个很有意思的问题：站在今天回头看，最初构建 HubSpot 时所做的一系列架构决策，是基于人类理解与导航信息的逻辑来存储数据的。现在面对能够以全新维度洞察信息的高能力模型，如果你从零开始，会有哪些不同的设计？或者你目前在管理层面上正在采取哪些动作来应对？
<details><summary>Original English</summary>
>> No, totally. And I I I think I think there's many companies that are navigating through this as they try to understand their own pricing and and consumption uh ideas here which could be its own dang podcast I think um for that matter. May maybe last question on this because I think it's really interesting you talk through this >> the architectural decisions that you made when you originally built HubSpot are probably uh you know when we would benefit hindsight I don't know how you would revisit those. I'm I'm so curious to hear how you think about that because of course now the way that you know that you designed it originally was for a human to to be navigating all of this this information and you're storing that in a way that's intuitive to a human and so now we have these you know unbelievable unbelievably powerful models that can go look at things in very different ways and so I don't know how you think about the way you may have wanted to start differently or maybe what you're doing to address that now as as as a as an executive at HubSpot.
</details>

>> 作为一名受过正统计算机科学训练的技术极客，在构建大型软件系统时，我极其推崇“框架与核心原语（Primitives）”的理念，并在此基础上持续演进。这是产生复利和杠杆的源泉。软件开发的核心在于：一旦把最底层的核心原语定义准确，随着市场和产品的变化，你后续只需将这些原语重新组合编排。HubSpot 自创立以来一直践行这一原则：我们构建了一套核心底层框架，营销自动化等功能都跑在上面。当我们后来进军销售与 CRM 领域时，营销自动化底层的工作流原语（比如发邮件、等待三天、判断点击）完全可以直接复用，使我们的销售自动化产品在发布第一天就具备了超越竞争对手多年积累的能力。
<details><summary>Original English</summary>
>> Yeah. Um couple things. one is you know so I'm a classically trained computer science software development nerd um forever and one of the things I'm a big believer in in terms of uh you know large scale software applications is around this notion of like frameworks and and starting with a set of primitives that you sort of evolve over time because that's the thing that gives you that's coming back to kind of uh compounding and leverage one of the things I've learned you know across um every company I've I've I've done and worked in is that you know software if you can kind of get those core primitives right um and then what you end up doing is sort um remixing and recomposing those uh primitives in kind of novel ways based on how the market evolves and how the product evolves. And so that part has been true at HubSpot since the beginning, right? So the thing we built out was we had this kind of core uh kind of operating system or operating framework that we had on which we built the marketing automation things like that. So when we went to product you know 2 3 4 or whatever like most of the value that we needed to bring to market already existed in the form of primitives like for instance we started with marketing automation which is oh here's this deterministic workflow to do marketing like send an email out wait three days wait for them to click it's like oh well then when we got into sales and CRM it's like well our marketing automation primitive is actually a primitive we can just reuse all of that technology and we will have more on day one of our sales automation app or product than anyone likely has that's been added for a few years right? Like and and so that part of it I think still holds true.
</details>

>> 我们现在正重新审视这一框架，思考面向未来 20 年的 AI 世界需要什么样的新原语。正如你所提到的，数据不再仅仅是关系数据库中的结构化数据，而是包含了大量非结构化信息。这些数据一直存在于企业组织内部，但在 10 年前以当时的成本根本无法有效利用。如今，我们依然需要一个存储已知事实的确定性结构化数据库作为“记录系统”（System of Record），同时需要在此基础上建立一个由非结构化数据组成的“上下文系统”（System of Context）。我们正在推进这一架构，其形态类似于“第二大脑”或由图结构承载的“上下文图谱”（Context Graph）。结合这两者，我们便能驱动模型推理与智能体（Agents）来执行工作。
<details><summary>Original English</summary>
Um and so what we're doing now is to say, okay, what is the framework we need for the next 20 years of HubSpot now knowing that we have this AI world and so you touched on one of the things is oh well the data is no longer just this kind of structured data in a relational data store or whatever which made sense for the kinds of queries uh determinist queries you're doing. Now it's both structured and unstructured data and it's not like this data didn't exist within the organization even within our customers organizations. It's like you just couldn't do anything with it. uh that was meaningful uh at any sort of uh well at any price actually back 10 years ago but now you can right so so now we revisit the primitives and say okay well we still need a structured data store um and I will uh you know happily debate this with whoever wants to debate it like there is still room whether it's relational some other there needs to be some persistent mechanism for storing kind of known facts uh and data some sort of system or record if you will uh alongside uh this kind of system we think of as a system of context which is this unstructured data and that's the thing that um we're sort of building out and the way I think this is going to evolve is um this notion of um and I use this term others use it too like a second brain or like an open like a >> can we put all the things that are happening um and and the the kind of the structure that likely makes sense um is some sort of graph structure can we store this in some sort of uh context graph another term that's um has been used and and that's the idea. It's like okay well can we take this and then use that in combination with the structured data store and then draw inference and drive agents and drive outcomes and and and get work done.
</details>

>> 此外，Agent 编程对现有成熟企业（Incumbents）带来了巨大红利。它不仅让我们能更快地交付软件和测试点子，更让我们有能力承担过去根本不敢涉足的大型重构工程。我们管理代码的记录系统是 GitHub。假设你现在拥有了像 Fable 5.1 或 Astra 6.1 这样的先进编程模型，你常常会感慨：“要是当年的自己能做出不一样的架构选择该多好。”理论上，你现在完全可以把历史代码库调出来，花费 20 万美元的 Token 费用，让智能体按照新的语言、框架或原语架构彻底重写一遍，直接跳到做出不同选择的“平行宇宙分支”去验证结果。成熟企业的一大独特优势在于拥有庞大的单元测试资产，在今天体现为评测集（Evals）。每当新模型发布，我们都可以跑一遍评测，精确评估质量、延迟与成本之间的权衡。我们同样可以用这种机制去小规模测试代码重写假说（比如“如果用 Rust 重写会怎样”）。
<details><summary>Original English</summary>
So uh one thing that's interesting uh in terms of AI you didn't asked this question but uh it occurred to me as as we were chatting is that one of the things that's really beautiful about uh agentic coding now um is and this is particularly true for actually even more true for incumbents is like yes it allows us to produce software faster. We can test ideas faster, which we've talked about before, build products faster, which is all awesome. We benefit from that. But the other thing you can do is you can actually go um deeper and do larger projects that you might not have otherwise considered. So what's possible now um is that you know so we have a system of record for code which most people which is GitHub. So imagine you said okay well I have something like a you know a fable 5.1 or like um six Astra um that's out now or 6.1 that's out now. Um but so imagine you say okay well I wish like younger me had made these choices when it came to if I just could go back in time here's how I would have done those primitives or I would have introduced this as a primitive that's a reusable service versus because we didn't know that then but we sort of know that now in theory it's actually possible um to now say I want to I want to play that back I want to take this body of code that we used this data structure for this language for this framework for this architecture for and what would happen if we said we're going to spend $200,000 on tokens to go just redo that and basically just play that it's like the you know infinite possible universes thing or let's let's jump to that branch of the universe where we had made a different choice and then see what happens where we wind up and one of the advantages um you know companies like HubSpot have is that we have uh what people used to call unit tests uh and now show up as eval can we actually measure the viability of the thing that we just did it still pass the test does it still produce the outcomes. Does it still do all the things that it needs to do? Like we have that now. So we do we run this test now when new models come out. It's like okay well we can run our battery of evals across uh new models and say okay well here's a trade-off. Here's the economic value like we lose about 3% of quality points uh but we gain this much in terms of latency or or economic. We could do the same thing with testing these kind of theories like okay if we did rewrite this the whole thing in Rust I'm making that >> what what would it look like? what what what's the actual and you can you know test it uh now with small bodies of work. So >> anyway that's it's it's exciting. Uh
</details>

### 孵化机制与 Uspot：单人企业爆发与早期变现

>> 这种设想非常吸引人。我此前写过一篇文章，以 Workday 为例探讨传统软件必须推倒重来、成为“AI 原生”企业时所面临的优劣势。HubSpot 的一大优势在于创始人依然深度参与日常运营并亲自驱动变革。除了构建平行宇宙，你们在消除官僚主义、内部团队组织上有哪些实践？
<details><summary>Original English</summary>
>> I think this is such a fascinating topic. I I wrote a different essay um I think right around the same time I wrote the yellowbook road maybe a little bit before and I actually used workday as an example uh on this front but of just like hey you have to kind of start over to think about being AI native and here's all the here's all the advantages you have but here's all the disadvantages and so you know it's it's almost you know the the benefit I think that HubSpot has is it has an amazing you know founder who's still very very involved in the company of course running the business and and driving these changes and so that I I love that example of like trying to think about these like alternative universes that you can Are there other processes that you're trying to create inside of HubSpot or teams you're trying to create in HubSpot or or or destroying bureaucracy? I'm just curious to hear what you're doing as a as a founder right now.
</details>

>> 我们内部有一个名为 HubSpot Next 的创新实验室，相当于“初创公司里的初创团队”。我们当年做 CRM 时也采取了类似的做法：将团队完全隔离，不设规矩，不必使用既有技术栈，甚至不必挂靠原有品牌，纯粹以解决问题为导向。目前我每晚都在亲自带头推进一个名为 Uspot 的项目——这是一款面向独立创业者（Solopreneur）的单人 CRM。HubSpot Next 的每个项目要么探索新产品品类，要么探索新市场，要么测试新技术。相比于在核心系统上大动干戈，把“第二大脑”和上下文图谱放到 Uspot 里进行快速验证，成本低得多、节奏快得多。这个产品刚上线刚好 30 天。
<details><summary>Original English</summary>
>> Yeah. Um so we have a group within HubSpot um called HubSpot Next and the idea is it's it's a um effectively an innovation lab. So it's a it's a startup within a startup. Um and so we'll have any number of these kind of going on at any particular point in time. And the motivation and we really truly do treat it like a startup and we and we did a variation of this when we built the CRM. It's like okay we're going to build this CRM thing. It's like wait what's that? We're in the marketing software business and it's like and we sort of had cordoned off the team. Uh they had none of the rules. You didn't have to build it on our stack. You didn't have to use the brand. You didn't have to do anything. Just go solve the problem. Um and we've sort of carried that idea through now. And so um and the and uh and I've championed uh and led several of these projects over um over the years. And the one I'm working on right now literally every every single night um is a project called Uspot. Um and it's a oneperson CRM. It's a CRM for solopreneurs. That's the market. And this going back to the uh kind of narrow your um aperture of focus. But the HubSpot next projects have um they're pursuing either a new product category, a new product idea, pursuing a new market, or testing a new technology. And going back to the can you learn your lesson cheaply, it's much easier for me. It's like I have this idea for a second brain, right? Like, oh, maybe a graph, you know, graph model works better. Maybe you plug in all the social media, everything that's coming in or whatever, and it's like, okay, well, let's test this in in Uspot because that's a much easier kind of faster paced way to test it. Um and so the product uh now is exactly 30 days old. Uh so
</details>

>> 恭喜。
<details><summary>Original English</summary>
congratulations on
</details>

>> 实际测试表明，这套逻辑确实行得通，第二大脑的原语是成立的。回到避开黄砖路的话题：你不应该抱怨 ChatGPT 或 Claude 的通用记忆能力太差并试图去解决这个横向问题——因为他们迟早会解决。你应该做的是针对特定垂直客群，识别出通过第二大脑能够解决的具体痛点，把数据接入点、工作流与智能体串联起来。
<details><summary>Original English</summary>
yeah and and it's and it's been fascinating um kind of learning and so the answer to the the original question is you know can something like that work? The answer is yes. um it it does work and I think um other entrepreneurs should kind of take away from um you know this is that so that that notion of having a second brain um that holds um and it the thing to going back to the kind of yellow brick road conversation kind of avoiding being run over the thing you shouldn't do is to say oh well chat GPT and cloud corework are really bad at memory or whatever and this like
</details>

>> 没错，通用能力总会提升的。
<details><summary>Original English</summary>
>> yeah it's like it's going to get better
</details>

>> 别去碰那种横向通用场景，而是去深挖特定客户群体。那么，如何将这些孵化成果反哺回母体？需要建立怎样的机制？
<details><summary>Original English</summary>
>> don't solve that problem don't solve the horizontal use case or whatever but say hey within this class of customer here's is a class of problems that they have that would be benefited by thinking about this notion of having a second brain. What would the injection points be? How do you pull it together? What's the actual agents that you would produce or the work that you would kind sort of accomplish? But I think that underlying primitive um is actually a powerful one. I think it it it applies. Um so >> yeah. And then now that you I mean I think you spot so fascinating and I think it's very valuable for that particularly for this type of user. I mean it's it's what they they want of course. Yeah. um how do you then take those learnings and like productize them at the mothership if if at all and and what processes do you need to put in place to to make that happen?
</details>

>> 我们的做法是把它们当成“内部人才与资产收购”（Acquihire）。比如我几年前做过一个叫 agent.ai 的项目，早期定位是 AI Agent 交易市场与构建工具。后来我们发现构建工具这半边业务很有价值，但需要整个 HubSpot 团队的资源支持，于是母体直接吸收了该技术，将其转化为了 HubSpot 内部的产品功能。对于 Uspot，未来既有可能作为独立产品保留，也有可能将验证成功的“第二大脑”和数据接入架构抽离出来，供母体核心团队吸纳到多人协作模式中。
<details><summary>Original English</summary>
>> Yeah. Um the way we've done it which we you know we've kind of stumbled over the years and tried various mechanisms um is to kind of pull on that original thread of um this is a startup within a startup. So we do a couple of things. Um one is if the thing gets to scale uh and we've had this happen you know multiple times before. So, there was a product I launched a couple years ago called agent.ai. >> Uh, and agent.AI was a marketplace for AI agents, you know, back back in the day. This was one of my accidentally competed with Sam Alman uh stories. Although it was focused on go to market, it was uh two horizontal uh but there were two parts to it. There was this kind of agent AI marketplace and there was an agent builder that says, "Oh, can we let mere mortals actually build these uh kind of mix of deterministic nondeterministic um agents?" And what we discovered is that uh half of the idea was right uh but actually belonged and needed uh the full HubSpot team behind it. So we did a effectively an acquisition, right? So he's like we're going to take that and now we're going to make agent builder a product within HubSpot or whatever and that's what it lives lives at right now. So in the US case, right? Like uh one possible outcome is oh like we're building the CRM for one person companies, we got these things right, those things wrong, whatever. Maybe we just absorb it into uh HubSpot becomes a product of HubSpot. Um maybe we say, "Oh, well, the product itself still probably needs to be standalone or maybe the market doesn't work. Uh but the idea of a second brain maybe works and like here are the things in the ejection points that we think work for SMB uh and and multiplayer kind of team based mode or whatever. We just sort of let the core team decide what they want to pick and choose." It's it's a little bit like they're looking like at an aqua hire and it's literally like that. It's like, "Oh, here's what we can buy." Um, at the low low price of it's included.
</details>

>> 相当于免费包含在内了。
<details><summary>Original English</summary>
>> It's included. Yeah. [laughter]
</details>

>> 没错。这种模式赋予了我们极高的实验自由度。大企业所欠缺的并不是某种特定能力，而是组织本身的包袱与重负。一旦能甩掉这些包袱，大公司在分发渠道、客户信任、代码资产和评测体系上的优势就会转化为巨大的加速杠杆。
<details><summary>Original English</summary>
>> It's not It's not free. It's free. >> Exactly. It's free. Um, so yeah, that's and >> and we sort of try to have an open mind about it. But the nice thing about doing it the way we do it is that >> so you think it's like why can't you just do it within the you know the core core of business is that those degrees of freedom are super important to be able to run the experiments at the rate that you want to run them. So you have to like one of the things I've you know long said you know being a startup guy is that um the the issue that incumbents sort of hard to use uh incumbent when I refer to HubSpot now I still think of it in some way >> it's still a startup don't worry >> y um is that not the absence of something it's not like startups you know have something that um that the larger companies don't the issue is that >> is the kind of I'll call it baggage um and the weight that the organization has and if they can find a way to kind of shed that then you get all the advantages of being larger. You have distribution, you have customer relationships, you have eval, you have, you know, 20 years of a code base that you can use as data to kind of inform the next product that you build. All this stuff is is actually an asset. So, if you can sort of shed the liabilities um and you know, HubSpot next is a way to say, okay, well, we're just going to pretend that we have none of those liabilities, which we don't as a startup with a startup, we can just go off and do our thing, which we've been doing. Um, but then when it comes time to lean into the asset, it's like, oh, it would be helpful to have the HubSpot brand here or can we get some advice on distribution over there, it's like we can do that. So,
</details>

>> 现在的宏观讨论中充斥着对 AI 负面冲击的担忧，但从数据上看，增长令人惊叹。Uspot 证明了针对单人企业的专属 CRM 在过去几乎不可行，如今却迎来了爆发契机。
<details><summary>Original English</summary>
>> it's so easy right now, especially with some of the the the national discourse to to think negatively about AI and like the impacts, but the reality is all the data I've seen are so it's so exciting. Like growth is unbelievable. Um, and I actually think you spot is a really good example of of this potential growth, right? It's like when in the in the history of mankind would it have been like a good idea to go build like this like >> super individualized CRM for one person like it would have been almost impossible to do that historically right but now we're able to do that and what is that then going to let those one people companies do like that is >> we're going to see growth unlike I think anything we've ever seen before and it's just so cool to dream. So maybe I'd love to just hear you talk a little bit about what you're seeing like these initial use cases maybe from Uspot or or what you're seeing from from growth. It's just it's it's it is really amazing time to be alive.
</details>

>> 我在 Uspot 上做的一个不同尝试是极早就开启了商业化变现。目的并不是为了覆盖服务器成本，而是为了尽早验证定价模型与用户的付费意愿。令人惊讶的是，用户非常愿意为用量计费（Consumption-based）模式刷信用卡。参考美国人口普查局的数据：2025 年全美新成立公司数量达到约 560 万家，创历史新高；今年截至 8 月已突破 400 万家，预计又是一个破纪录的年份。更关键的数据是，在新增企业中，预计在未来两年内不打算雇佣员工的单人企业占比已经超过了 70%。这是一个前所未有的庞大市场，就像当年外界怀疑中小企业无法做大软件业务一样，如今面向单人企业的软件市场空间同样极其广阔。
<details><summary>Original English</summary>
>> Yeah. Um so it's what's interesting like the I knew this to be the case but I wasn't sure to what degree. So as I mentioned the one thing I did differently with Uspot um versus prior kind of HubSpot next projects that I've done is I uh I monetized really early. Um, and part of it is not to kind of cover COGS or something like that. It's like that's one of the lessons I wanted to learn is I want to learn like the pricing lessons and some of the things that we want to learn more about kind of monetization pricing and what you know value people ascribe to this. That was part of it. So the thing I've been really surprised by is uh willingness of for people to put a credit card down on a consumptionbased model. Um like it's like nothing. I've I've launched lots of projects um you know over the years at HubSpot. This has been in that regard the most successful. So there's like this signal um out there um and part of it I think is just driven by you know the sheer numbers you know we'll bring the the US census data into this right now is that so in 2025 we had the most number of new company formation the United States has ever seen I think it was like 5.6 million closely on 6 million uh which is great uh this year we were already at four like by August um we were already over four million so it's going to be another record year so it's not like oh we had this onetime spike and now it's selling back in. So that's kind of fact number one that's super interesting. Uh fact number two that's even more interesting is the percentage of those new company formations that are expected to remain oneperson companies is the highest it's ever been and it's increasing and so the US censure actually tracks this data they say they put every new company into two buckets and they one is that this company is predicted to hire an employee within at least an employee within the next two years and they bucket them in those two ways and the bucket of they are unlikely to actually hire an employee in the next two years. Uh that percentage is now it's yeah over 70%. Um so so it's exciting. So there's this new market. Um and so for the entrepreneurs that are out there's a entirely and just like SMB was back when you know and everybody sort of uh pushed back on HubSpot back in the day. It's like oh you can't make money in SMB. It's so hard or no software company has ever other than into it has ever made a multi-billion dollar business in SMB. Um but you can it's like it's big enough. Yeah, there's going to be painful parts to uh you know those kinds of markets. But anyway, I'm I'm excited for that. I'm excited for excited for the economy. I'm excited for all the entrepreneurs that are going to be starting these millions of businesses or whatever. Um yeah, and and then excited for the entrepreneurs that build things for the for that market just like it's exciting all the way around. I'm uh yeah
</details>

### 软件市场的扩容：反驳“SaaS 末日论”

>> 以前垂直软件往往靠低客单价结合支付分润来实现盈利，现在随着为小微客户创造价值维度的极大增加，整体市场空间正在成倍放大。
<details><summary>Original English</summary>
>> no I totally agree with this and and we we talk a bunch about uh you know aspects of this all the time and I think one of the one of the areas we've talked about has been like oh well vertical software in the past well how did you make that work well you made vertical software work with a low you know ACV or annual or monthly cost but then you made it up because you had payments uh you know interchange revenue and and I just don't know if people are fully appreciating the increase in in opportunity size as there's just so much more you can and and so many other ways you can you can offer value and and create value for your your small customer.
</details>

>> 这正是我用来反驳“SaaS 末日论”的核心论据。AI 本质上仍然是软件，而不是某种新型能源。软件能够解决的问题领域被极大地拓宽了。在 HubSpot 创立第一年去融风险投资时，几乎所有的 VC 都拒绝了我们，理由是“市面上从未出现过估值数十亿美元的营销软件公司”。我们当时反驳道：如果审视任何规模企业的利润表（P&L），几乎每一个科目下面都对应着一家市值千亿美元的软件巨头，唯独营销科目没有。因为以往的营销更偏向艺术创作与广告采买，但随着互联网的出现，营销开始变成一个非常适合用软件解决的问题。
<details><summary>Original English</summary>
>> This is yeah and this is my uh kind of counter to the >> sort of the the the SAS apocalypse um kind of idea is that the reality is that you know and AI by the way for the record I know you know this it is software just so you know it's not like it's not software right it's not some new energy source it's it's software really smart software but software uh and what what has really happened now is like if you look at the class of problems um that software uh was designed okay I'm gonna I'm gonna take one minute because this is actually a good story only a handful of good stories so when we were first starting uh in the first year of HubSpot and we were out raising venture capital we said hey we're building this marketing software company um here's what we're going to do u and and the almost universally across all the VCs that we talked to came back and said well there's not been a marketing software company in the billions or whatever um like that that's so we got two strikes like the SMB strike and the fact that we're doing marketing software and our argument at the time was the reason okay so if you look down the P&L of any uh any size business every line item on the on the P&L has a 100 plus billion dollar software company name attached to that line item except for marketing it's not like people don't spend and the reason is is that marketing historically has been an arts craftsy kind of thing or whatever it's like you have this amount of spend you spend a little bit on on creating the creative but then you just spend it on ads and billboards and all those kinds of things. Fine. >> And our thesis was that as a result of the internet marketing the industry is going to look a lot like a problem that software was designed to solve and that's why a software company needs to didn't need to exist 5 years prior to HubSpot starting but now someone will build a massive uh you know marketing uh marketing software business.
</details>

>> 我今天持同样的观点：过去有一整类问题是软件无力解决的，现在通过 AI，出现了一大批软件能够攻克的新场景。虽然在这个过程中确实会有一些软件公司被淘汰，就像当年无法向云端和 SaaS 转型的传统软件一样；但总体而言，软件市场的整体机遇比以往任何时候都要庞大。如果你拥有自主能动性和创业精神，当下就是构建软件公司的最佳时刻。
<details><summary>Original English</summary>
I'm going to make the same argument now that before there was a class of problems that software wasn't really equipped to solve. >> Yes. Now there is a massive set of these new problems uh problems existed new things that we can do with AI that didn't exist before. So the opportunity set is way larger than yes some software companies will die no doubt just like some software companies did not make the transition into SAS in cloud-based things or whatever like that's the circle of life kind of thing but >> in aggregate the opportunity is bigger than we've ever like if you're anywhere near like software have the agency and and are entrepreneurial there's never been a better time to build a software company >> go right now do it
</details>

### 快问快答与结语

>> 完全赞同，太有意思了，非常感谢你的时间。最后来一轮简短的快问快答。
<details><summary>Original English</summary>
yeah I totally agree with you this has been uh unbelievably fun I'm I'm I'm so grateful for your time. I'm going to end with a quick lightning round for you >> and we can go on on our merry ways.
</details>

>> 我反应可不算快，希望题目简单点。
<details><summary>Original English</summary>
>> I'm not very fast on my feet, so there's only a few of these are softballs.
</details>

>> 先来个最简单的：Dunkin' 还是 Starbucks？
<details><summary>Original English</summary>
Um, I'll start with a very easy one. I I I would assume Duncan or Starbucks.
</details>

>> Dunkin'。
<details><summary>Original English</summary>
>> Uh, Duncan. Okay.
</details>

>> 不过顺便说一句，我不喝咖啡。
<details><summary>Original English</summary>
>> But I don't drink coffee, by the way.
</details>

>> 那你平时喝什么？只喝水吗？你是机器人吗？
<details><summary>Original English</summary>
>> Oh, wow. Okay. Well, then what what do you drink instead? Just only water. Are you a cyborg?
</details>

>> 只喝水。多年前我就戒掉咖啡因了。
<details><summary>Original English</summary>
>> Uh, just just what? Yeah. Wow. I gave up caffeine like years ago.
</details>

>> 更令人佩服了。下一个：Instinct 还是 Muse？关于新型 Agent 购物体验的。
<details><summary>Original English</summary>
So, anyway, even more impressive, Darm. Okay. Um, uh, Instinct or Muse? >> I'm sorry, what? >> Instinct or muse? You know, on the new, uh, the new agentic shopping experiences,
</details>

>> 我选 Instinct。
<details><summary>Original English</summary>
>> I'm g have to say instinct.
</details>

>> 如果选一种动物，你想成为什么？
<details><summary>Original English</summary>
>> Okay, interesting. It, um, if you had to be an animal, which type would you be?
</details>

>> 我还是想做哺乳动物，可能选大象吧。
<details><summary>Original English</summary>
>> I would still be a mammal. >> Maybe an elephant.
</details>

>> 大象，很棒。HubSpot 身上最具波士顿印记的特质是什么？
<details><summary>Original English</summary>
>> An elephant. I like that. Okay, good. What's the most Boston thing about HubSpot?
</details>

>> 几乎体现在方方面面。
<details><summary>Original English</summary>
>> Um, almost everything. It's
</details>

>> 很好的回答。
<details><summary>Original English</summary>
>> good good answer.
</details>

>> 我们非常务实，以解决客户问题为先。我常说我们融合了西海岸硅谷的野心与进取，以及东海岸脚踏实地、埋头苦干的务实作风。
<details><summary>Original English</summary>
>> Yeah. Um we're very pragmatic solve for the customer. Uh I I say that um we're sort of like a hybrid between like a some of the best of the kind of west coast uh kind of valley thinking in terms of uh ambition aggression but some of the pragmatism of the the east coast heads down just work at it grind.
</details>

>> 最后一个问题：你在 HubSpot 度过的最棒的一天是哪天？
<details><summary>Original English</summary>
>> I love it. And then uh finally what's the best day you've ever had at HubSpot?
</details>

>> 大约一周前。脑海中的很多构想终于各就其位，我开始清晰地看到事物将如何展开演进。很难用言语详尽表达，但这确实是最棒的一天。
<details><summary>Original English</summary>
about a week ago. Um it's like the things are starting to fall into place like both in my head and like it's just like okay I I can sort of see how this is unraveling. It's um yeah it's hard hard to explain. This is not something I'm going to be able to say but uh yeah it's
</details>

>> 太酷了，经历了这么多年，最棒的一天居然发生在一周前。
<details><summary>Original English</summary>
>> oh that's so cool. I mean after however many years the be you know the best day was a week. I mean
</details>

>> 在 HubSpot 20 年的历程中，我现在所度过的时光是我个人经历中最开心的阶段。我在 HubSpot 没有任何直属下属（我一直是一名独立贡献者 IC），这意味着我既能享受大公司的规模红利、参与长线决策布局，又不用承担管理负担，还能随时亲手推进像 Uspot 这样的创新项目，真正兼顾了两者的长处。
<details><summary>Original English</summary>
>> yeah but and I also say this more broadly um and I mean this like all things but um >> so the best time I've had even being a startup guy in the history um of HubSpot which is 20 years old now is the time I'm having right now. U and and the reason is and people like oh that can't possibly be true if you're it's like um it's like I have all the so by the way I have no direct reports at HubSpot. I've never had direct reports. So, like I'm a um an IC, but um and the reason is that I have all the benefits of scale. You get a seat at the grown-ups table. You can make long-term bets. You can put, you know, you can like you can do things, but I have like another downside. I can do HubSpot, you know, next projects like Uspot or whatever. So, I have sort of the best of both worlds. Uh and it's so much fun right now. Yeah. So,
</details>

>> 极棒。Dharmesh，你是一位卓越的时代级创业者与思想家，也是一位极度友善的人。非常感谢你今天的分享。
<details><summary>Original English</summary>
>> it's awesome. Well, uh Darm, you are a generational entrepreneur, a wonderfully kind human, and a generational thinker as well. And I'm so grateful for your time today and for your engagement on all these topics. So enjoy.
</details>

>> 期待下次交流。
<details><summary>Original English</summary>
>> I look forward to the next time.
</details>

>> 谢谢。
<details><summary>Original English</summary>
>> Thank you.
</details>

>> 再见，朋友。
<details><summary>Original English</summary>
>> See you, buddy.
</details>