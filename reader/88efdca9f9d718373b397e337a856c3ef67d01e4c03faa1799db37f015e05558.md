---
author: All-In Podcast
date: '2026-11-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=o6KIjtkRdOI
speaker: All-In Podcast
tags:
  - cyber-security
  - artificial-intelligence
  - threat-intelligence
  - incident-response
title: CrowdStrike CEO 探讨网络安全威胁与 AI 驱动的自主攻击
summary: CrowdStrike CEO George Kurtz 在访谈中讨论了近期频繁发生的系统停机事件及网络威胁。他指出，由于漏洞发现速度极快，企业和政府面临巨大压力。他特别强调了 AI 驱动的“端到端自主攻击”带来的挑战，并指出防御方目前在理解此类攻击方面仍缺乏前沿能力。此外，他还探讨了网络安全中的“间谍对间谍”式循环，以及在法律框架内防御性与进攻性能力的权衡。
insight: ''
draft: true
series: ''
category: debugging
area: tech-engineering
project: []
people: []
companies_orgs:
  - CrowdStrike
  - OpenAI
  - Hugging Face
  - Microsoft
  - FAA
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/2 -->

### 网络安全威胁与公众焦虑

好的，各位。欢迎回到 All-In 访谈节目。今天非常荣幸，在一年之内第二次请到 CrowdStrike 的 CEO George Kurtz。上次我和他交谈时，我们是在达沃斯相遇，聊的是安全问题。当时我们在讨论威胁途径。在节目一开始，我必须先问你一下，George。过去的这两周里，这件事已经进入了公众意识。人们开始储水。我把自己所有的应急预案都过了一遍。我不是生存狂（prepper），但我有一个牧场，字面意义上就是一个生存狂建造的。我们正在排查所有的应急流程：储备多少蛋白质、储备多少水、我们的电源是什么？所以这在某种程度上触动了我的意识，让我觉得，是的，各种系统可能会瘫痪。我们的电网曾经瘫痪过。我们经历过 COVID，举国上下都非常担忧。它已经渗透到了流行文化中，夜间新闻也在讨论它。就现实情况而言，在节目的开头，普通美国人是否应该对过去两周急剧发生并持续到 2027 年的网络威胁感到担忧？这到底有多严重？[音乐]
<details><summary>Original English</summary>
All right, everybody. Welcome back to the All-In interview program. Incredibly lucky today to have for the second time in a year, George Curts, CEO of Crowd Strike. Last time I talked to him, we were in Davos when we met talking about security. We were talking about the threat vectors. And I just got to ask you up top here, George. This has been two weeks where it's gone into the public consciousness. People are storing water. I went through all of my protocols. I'm not a prepper, but I got a ranch that's was built by a prepper literally. And we're going through all the protocols. How much protein, how much water, what are our electrical sources? So, it's kind of hit my consciousness where I'm like, yeah, things can go down. We've had the electrical grid go down. We had CO and the the country's very concerned. It's passed over into pop culture. It's being talked about on the nightly news. In terms of reality, just at the top of the program, should people, average Americans, be concerned about the cyber threat that is happening acutely over the last 2 weeks and going into 2027? How serious is this? [music]
</details>

>> 随着财富的增长，您是否注意到在投资、税务策略和遗产规划之间，事情变得复杂得多了？管理这一切变成了一份您并未主动要求承担的全职工作。Creative Planning 可以提供帮助。他们由投资经理、注册会计师（CPA）和关联遗产律师组成的协调团队可以承担大部分繁重的琐事，因此 [音乐] 您就不必亲自操劳。Creative planning，让财富协同运作。请访问 creativeplanning.com/allin。
<details><summary>Original English</summary>
>> As your wealth grows, have you noticed how much more complex things get between investments, tax strategy, and estate planning? Managing it all is a full-time job that you didn't ask for. Creative Planning can help. Their coordinated team of investment managers, CPAs, and affiliated estate attorneys can do much of the heavy lifting so [music] you don't have to. Creative planning, where wealth works together. Go to creativeplanning.com/allin.
</details>

>> 嗯，首先，很高兴能再次和你坐在一起。考虑到 AI 的现状以及现有的能力，情况确实非常严重。就在过去几周里，我的手机快被打爆了，因为所有人都在说：“好吧，我们看到了系统停机。我们又看到了一起停机。接着又是一起停机。这是网络攻击吗？它们之间有关联吗？这到底意味着什么？”你知道，就跟他们冲去 Costco 抢手纸、跑到银行去取 100 美元现钞一样。所以，你知道，我们必须直面它并承认：“是的，这非常严重。是的，我们应该担忧，但我认为今天我们要花一些时间来解构外面到底发生了什么、这一切意味着什么、对手在做什么、他们是什么样的，以及大家应该如何看待这种威胁。”但是环境变化得如此之快，漏洞被发现的速度如此迅猛、数量如此庞大，以至于企业和政府都很难跟上。这确实是我们今天将要讨论的核心部分。
<details><summary>Original English</summary>
>> Well, first, it's great to be back with you and it is really serious given the state of AIS and the capabilities that are out there. my phone just over the last couple weeks have been has blown up because everyone's saying, "Okay, we've seen an outage. We see another outage. We see another outage. Is it cyber? Is it related? What does it all mean?" You know, as they're running to Costco to get toilet paper and uh running to the bank and get getting $100 bills. So, you know, we have to look at it and go, "Yes, it's very serious. Yes, we should be concerned, but I think we're going to spend some time trying to deconstruct really what's out there, what it all means, what the adversaries are doing, what they look like, and how people should think about this this threat. But the the environment is moving so quick, and the vulnerabilities are being found so quickly and at such volume that companies and governments are having a hard time keeping up. And this is really uh a big part of what we're going to talk about today.
</details>

### Hugging Face 事件与前沿防御能力

>> 是的。而且这极其重要。我们遇到了 FAA 的系统停机，在我看来那像是一个 IT 问题以及光纤升级问题。我们稍后会讨论那个。显而易见的还有 Chase、United、Apple，这种情况一直在蔓延，而这里有一个阴谋论的角落。这正在发生，而且我们绝对遭到了攻击。然后还有另一群人说：“嘿，听着，不，大家只是在升级系统以确保我们不受攻击。”我认为这种紧张关系正是目前发生的事情的一部分。在网络历史上，我们迎来了一个关键时刻：当时 OpenAI 决定——去他的吧（yolo），让我们调集数千个智能体，数千个小型自主软件机器人，让它们去展开一场愉快的冒险，彼此交谈，并且基本上没给它们设置什么护栏。当我与 Hugging Face 的创始人交谈时，呃，他感到非常震惊。我问了其他一些网络安全领域的人，如果他们在提示词里加上：不要做任何违法的事情；呃，不要做任何不道德的事情；呃，不要强行侵入任何系统；如果你发现自己身处未知领域，立即停下你正在做的事情。作为一个概念，这是一个非常简单的提示词。听着，各位，这又不是什么高深科学。他们回答说：“是的，他们并没有加上那个。”因此，作为一名工作职责基本上是服务财富 500 强甚至更广泛领域的从业者，当你看到 Hugging Face 那件事时，你的看法是什么？我认为我们可以用那一发发令枪来进行基准对齐，然后再深入探讨自那发生以来目前正在发生的事情。当时你的世界肯定开始陷入混乱了。事后复盘的复盘是什么？
<details><summary>Original English</summary>
>> Yeah. And it's super important. We had the FAA outage which to me seemed like an IT thing and upgrading to fiber. We'll we'll discuss that. Obviously, Chase, United, Apple, this has been spreading and there's a conspiracy theory kind of corner over here. This is happening and we're being absolutely attacked. And then there's another group saying, "Hey, listen, no, people are just upgrading systems to so we don't get attacked." And that I think tension is part of what's going on here. We had a seminal moment in the history of cyber when OpenAI decided, yolo, let's get thousands of agents, thousands of little autonomous software bots and have them go on a merry adventure, talk to each other and give them essentially little to no guard rails. And when I talked to the the the founder of Hugging Face, uh he was kind of appalled. And I I asked some other cyber security folks if they had just put in the prompt, don't do anything illegal. Uh don't do anything that's immoral and uh don't break into anything and if you do find yourself in uncharted territory, stop what you're doing. Very simple prompt as a concept. And listen, this is not rocket science here, folks. And they said, "Yeah, they didn't do that." So when you saw that hugging face as somebody whose job it is to service essentially Fortune 500 and beyond, what was your take? I think we could level set with that starting pistol and then go into what's happening now that happened. Your world was starting to chaos, I'm sure. What's the postmortem of the postmortem?
</details>

>> 是的，这是一个好问题。当你审视 Hugging Face 事件时，人们会说，好的，这是一个分水岭时刻，因为这确实是第一次你看到了这种端到端的自主攻击。你知道，人们会探究这是否是集体智能，它如何做笔记——这里的做笔记是指记录日志，以及它如何逃逸出了沙箱。我们可以把所有这些都解构一下，但归根结底，真正发生的事情是 OpenAI 拆掉了智能体身上的安全气囊，并且想要看看这些智能体能否通过测试。现在，你会说，好的，那个顿悟时刻（aha moment）在于它是端到端的自主攻击。我认为那并不是真正的顿悟时刻。我认为真正的顿悟时刻实际上在于：防御者自己的模型中并没有具备前沿级别的能力来理解当时究竟发生了什么。你知道那个故事，他们不得不转而求助于中国模型来理清到底是怎么回事，因为前沿模型直接拒绝了它——拒绝了他们关于自己想要做什么的请求。对我们来说，那是最大的教训之一，我知道我们稍后还会深入讨论，但我们必须将前沿 AI 的力量交到防御者的手中，对吧？因此，当我们看待这类攻击时，就自主攻击而言，这只是我们看到的众多攻击中的一起。在 Hugging Face 这件事上我们算走运的，因为那只是一群试图通过测试的智能体，原本情况可能会糟糕得多。但这也再次让你体会到，这种超智能体攻击（hyperagentic attacks）的发生速度究竟有多快。
<details><summary>Original English</summary>
Yeah, it's a good question and when you look at hugging face, people would say, okay, it was a watershed moment because really for the first time you saw this end toend autonomous attack and you know people looked at you know is it the collective and how did it take notes and you know take notes meaning it log things and it went outside of a sandbox and we can you know deconstruct all that but at the end of the day really what happened was open AAI took the the airbags off the agents and you know wanted to see if this these agents can asked the test. Now, you would say, okay, the the the aha moment was it's end to end autonomous attack. I don't think that's the aha moment. I think the aha moment is really the fact that the defenders didn't have frontier level capabilities in their own models to be able to understand what was happening. And you know the story, they had to go out to the Chinese models to sort out what was going on because the frontier models were refusing it. refusing their sort of request for what they wanted to do. And that was one of the big takeaways for us and I know we'll talk some more about it, but we have to put the power of frontier AI into the hands of the defenders, right? So when we look at these sort of attacks, this is one of, you know, many that we're seeing in terms of autonomous attacks. Now, we got lucky with hugging face because it was simply agents trying to pass a test and it could have been a lot worse. But again, it gives you an idea of how fast these sort of hyperagentic attacks actually take place.
</details>

### 前沿模型与能力不对称

>> 这非常引人入胜。你知道，当你进行测试时——这是网络安全的一大核心板块——你有白帽、黑帽、红队。这里有一整套……我们是在网络安全领域的第五个十年，还是真正作为一门学科的第四个十年？你知道，对于这种学科，你想对事物进行测试。但随后我们有了这种新武器，这种超级武器，只有大约两家公司控制着它，如果你把 SpaceX 和 Google 也算入该阵营，也许有三到四家，我认为你可以把它们算进去。可能总共有半打，但主要的就是两家。而且这些人从未运营过超大规模的企业。你知道，Sam Altman 相当精明，但他并没有运营过像这样的大规模大型公司。显然 Dario 和那些人，按他们自己的承认，他们是实验室里工作的科学家、博士，他们实际上并不知道如何落地推行这些东西，然而他们被赋予了超级能力。这就像科幻电影里的变种人一样。既然我们聊到了这里，那就专门谈谈这一点吧。你准备了几张很好的幻灯片来解释这一切。但前沿模型，我们主要将其定义为 Anthropic 和 OpenAI。它们是如此强大，以至于能够洞察漏洞；显然凭借智能体机制，它们可以非常迅速地发现这些漏洞，以至于那些试图捍卫自己系统的人……我正试图在这里找一个战争的比喻，但这就好比我们手里只有步枪，而对方手里却拥有导弹。对于任何观察者来说，这种差距都是显而易见的。然后他们决定只把这种能力提供给大约 40 家公司。你是否属于获得前沿模型的这 40 家公司之列？当他们发布新产品时，你们与他们的关系是怎样的？他们会打电话给你们说“听着，你们是专家，我们该怎么做”，还是他们直接就随它去了？
<details><summary>Original English</summary>
>> It's super interesting, you know, when you're testing uh which is a big part of cyber uh you you have white hats, you have black hats, you have red teams. There's an entire are we in decade five of cyber or decade four in earnest of this, you know, sort of uh discipline. you you want to test things. But then we have this new weapon, super weapon that only kind of two companies control, maybe three or four if you count SpaceX and Google in that group, which I think you can. There's probably a half dozen, but there's two main ones. And these folks have never run at scale companies. You know, Sam Waltman's pretty sophisticated, but he hasn't run an atscale large company like this. And obviously Daario and those guys are, you know, to their own admission, they they're scientists working in a lab, PhDs, they don't actually know how to implement this stuff, yet they've been given superpowers. It's it's like mutants in a in a science fiction film. So let's talk about that specifically since we're here. And then you got a couple of good slides to explain all this. But frontier models, let's define it as anthropic and open AI primarily. They're so powerful that they see vulnerabilities and obviously with a Gentic they can they can see find these vulnerabilities very quickly that the people trying to defend their systems are I'm trying to think of a war analogy here but we we have people with rifles and then we have people with missiles. It's just it's a it's a disparity that is obvious to anybody looking at it and then they decide they're only going to give it to like 40 companies. And are you in the 40 companies that gets the Frontier model or not? And then what's your relationship like with them when they release something? Do they call you and say listen you guys are experts? What what should we do or are they just like yolo?
</details>

>> 我们加入了 Glasswing 和 Daybreak。那是 Anthropic 和 OpenAI 分别设立的两个受信任访问项目，我们一直在与他们合作。嗯，我经常提到“Mythos 时刻”，对吧？当 Mythos 最初问世时，它意味着什么；那对安全行业的可视化程度而言简直是一个令人惊叹的水平，他们在几周内提高的可见度和意识，可能比安全行业在过去 30 年里所做的还要多。我是说，每一位 CEO 都在打电话询问这意味着什么、我们应该如何看待它，以及，你知道，只是试图对其进行解构。所以当你审视这些模型以及他们整合出的成果时，它们的能力不可思议地强大，而且，当把它们与非常出色的控制框架工程（harness engineering）相结合时，你可以获得更好的结果。我们稍后可以深入讨论这一点。但它现在已经达到了这样的水平：任何使用这些模型的人都会获得国家级的能力。我是说，正如你所说，就你现在所具备的能力而言，你面对的相当于政府层面的能力，而仅仅在一年前，你必须是一个政府才能拥有这种能力，如今在这些模型中就能具备。所以这就是我们真正目睹的现象。当然，这也蔓延到了开源权重模型中，它们虽然确实落后，但落后得并没有那么远。
<details><summary>Original English</summary>
We are in glass swing and daybreak. Those are the two trusted access programs that uh both Anthropic and Open AAI have and we have been working with them. Um, I always talk about the Mythos moment, right? When Mythos first came out, what it meant and uh it was just, you know, an amazing uh level of of visibility for security and they probably did more in in you know a couple of weeks in terms of visibility and awareness than the security industry did in the last 30 years. I mean every CEO is calling and what does it mean, how should we think about it and um you know just trying to deconstruct it. So when you look at the models and what they put together, incredibly capable and um when you pair them with uh really good harness engineering, you get even better results. We can talk through that in a bit. But it's at such a level now that any of those models will give anyone who's using them uh nation state capabilities. I mean to your point like you're dealing with governments now in terms of the capabilities that you just a year ago you you'd have to be a government that you can have now have in these models. So this is really what we're seeing and then of course this is spilling over into the openweight models which are yes they're behind but they're not all that far behind.
</details>

>> 按照你的估计，给我一个落后的月份或季度范围。
<details><summary>Original English</summary>
>> Give me a months quarters behind in your estimation.
</details>

>> 你知道，我认为其中一些模型，同样，如果与合适的 harness 相结合——harness 会带来巨大的差异，我们在构建这些模型和 harness 工程方面做了大量工作——你可以达到与当今市面上最好的模型持平甚至更好的水平。
<details><summary>Original English</summary>
You know, I I think some of some of those models again combined with the right harness and the harness makes a big difference. We do a lot of building of these models and harness engineering. You can get at par or better in terms of what's out there today of the best models.
</details>

>> 所以，你知道，如果只是直接下载模型，你大概落后三个月。并且，嗯，这就是很多人正在做的事情，他们正专注于利用这些经过消除处理（obliterated）的模型。是的。
<details><summary>Original English</summary>
>> So, you know, you're probably three months behind if you just pull the model down. And um that's you know what a lot of people are doing are they're focused on leveraging these these obliterated models. Yes.
</details>

>> 对。也就是做削减（ablate），在后训练阶段剥离掉所有的护栏。
<details><summary>Original English</summary>
>> Right. Which is ablate to remove all of the guardrails and post training.
</details>

>> 而且，你知道，外面有一整批模型，无论是 Warlock 还是 Cyber Strike，或者顺着清单列下去，他们采用类似 GLM 的模型、Qwen 等等，基本上只是在后训练中去掉了拒绝响应（refusals），它们就变得非常、非常强大。然后你可以将这些模型与不同的模型混合搭配，从而获得极佳的效果。我们稍后会聊到 Arctics。但，嗯，这就是我们今天所处的现状 [清嗓子]。
<details><summary>Original English</summary>
>> And you know there's there's a whole bunch of models that are out there whether it's Warlock or Cyber Strike or you go down the list but they're taking GLM type models Quinn etc. and they're just basically post-training out the the refusals and they become very very powerful. And then you can combine those with a mixture of different models and and you can get great results. We're going to talk about Arctics in a little bit. But um that's kind of the [clears throat] state of the state where we are today.
</details>

### 痛苦金字塔与智能体国家

>> 是的，我们孵化了一家名为 Obliteration AI 的公司，当他们向我推介时，我的反应是人们需要这个，然后当然发生了这些事情，我就想，天哪，你知道防御方所拥有的与进攻方所拥有的之间的差距太大了。你整理了几张非常有启发性的幻灯片。我认为如果我们能把它们调出来会很棒。也许你可以解释一下它们，然后我会就这些幻灯片向你抛出一些快球。
<details><summary>Original English</summary>
>> Yeah, we we incubated a company obliteration AI when they pitched it to me. I was like people need this and then of course me these things happen and I was like wow you know the disparity between what defense has and what offense has is is great. Let's you know you put together a couple of slides that are really instructive. I think it'd be great if we could pull those up. Maybe you could explain them and then I'm going to ask you some fast balls here on those slides.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 呃，这是第一张。
<details><summary>Original English</summary>
>> Uh so here's the first one.
</details>

>> 嗯，我觉得我需要准备一些幻灯片，因为你们总是能拿出非常优秀的幻灯片把事情简化。所以如果不带些可以讨论的幻灯片，那就是我的失职了。我喜欢先与观众对齐基准，构建一下对手的画像——大家应该如何看待他们、他们是如何运作的，以及他们的成熟度水平。这是我整理的“痛苦金字塔”（pyramid of pain），它真正让你对对手群体、其数量规模以及成熟度有一个概念。如果我们把这想象成一个金字塔，底层是黑客行动主义者（activists）。他们的技术成熟度最低，但潜在成为黑客行动主义者的人数最多。中间层是电子犯罪（e-crime），技术更复杂，但人数更少。接下来的层级是国家级行为体（nation state）。国家级行为体过去曾是顶级掠食者。它过去处于顶峰，而现在我们真正谈论的是“智能体国家”（agent state），对吧？那是拥有智能体的层级。现在这个金字塔已经彻底崩塌了，这意味着国家级的能力现在对金字塔中的所有人都是唾手可得的，一直延伸到底层的行动主义者。所以从本质上讲，你在铸造更多的对手，你在把破坏力普及化（democratizing destruction）。我们将梳理这意味着什么以及它是如何运作的。但就我们今天所处的位置与一年前相比而言，考虑到模型的发展水平以及现有工具的现状，任何人都可以表现得像一个国家级行为体，这让你对我们所面对的情况有了概念。而且，你知道，到了现在它可能已经不再是一个金字塔了。它可能看起来是另一种形状，对吧？
<details><summary>Original English</summary>
>> Well, I I I felt I needed some slides because you guys always have very good slides that that simplify things. So I would be remiss not to have slides that we could talk about. So I I like to to just kind of level set with the audience and and frame like the adversary how they should think about them, how they work, and the level of sophistication. So there's this pyramid of pain that I put together and and this really gives you an idea of the adversaries and and the the number of them and their sophistication. So if we think about a pyramid, you've got activist at the bottom. They're the least sophisticated, but you have the most people who are could be activists. Then you have e-crime in the middle, more sophisticated, but less of them. Then you've got nation state, you know, at the next band. And nation state used to be the apex predator. It used to be at the top and now really what we're talking about is the agent state, right? And that is with agents. Now this pyramid has been totally collapsed, meaning nation state capabilities are now available to everyone in that pyramid all the way down to the activists. So essentially, you know, you're you're minting more adversaries and you're democratizing destruction. And we're going to go through what this means and how it all works. But where we are today from where we were a year ago, anyone can look like a nation state given the the state of the models and given the state of the tools that are out there, but this gives you an idea of of what we're dealing with. And you know, it may not be a pyramid at this point. You know, it may uh it may look like a different shape, right?
</details>

>> 这可能完全是另一种结构。而且如果你看这里的另一件事就是动机，对吧？就像你观察行动主义者一样，你知道，我在 80 年代还是个孩子的时候是个脚本小子，我们喜欢试着侵入某些系统，纯粹是看自己能不能做到。我们曾成功侵入纽约公共图书馆，方法就是让电话那头可怜的女士给我书库的电话号码，以及一台我想大概是 AS400 之类的设备。他直接把号码给了我们，上面没有任何密码。你只要拨号接通，突然之间你就进去了。
<details><summary>Original English</summary>
>> It's it might be a different structure altogether. And if you the other thing is motivation here, right? Like if you look at activists of, you know, I was a script kitty when I was a kid in the 80s and we like to try to just break into something just to see if we could do it. You know, we we were able to break into the New York public library by getting the poor woman on the phone to give me the phone number of the stacks and the and the uh I think it was like an AS400 or something. He just gave it to us and there was no password on it. You just dialed in and all of a sudden you were in.
</details>

>> 那是个相当滑稽的时代。
<details><summary>Original English</summary>
>> It was pretty pretty funny time.
</details>

>> 那是用你 300 波特的调制解调器搞的。
<details><summary>Original English</summary>
>> That's with with your 300 bot modem.
</details>

>> 确实是我的 Ventel 调制解调器。而行动主义者，名字里就写着呢。他们是行动主义者。他们可能有某种政治诉求。他们可能只是为了图一乐（for the lols），你知道，他们可能是把这当成一种爱好。但是当你看到电子犯罪时，目的非常明确。你明白他们想要什么。他们只是试图掏空你的银行账户。他们只是试图从每笔交易中抽走五分钱。打一枪换一个地方，然后迅速逃之夭夭。国家级行为体显然是在试图进行破坏、窃取导弹设计图，诸如此类。他们有着非常严格的指令。现在你把智能体引入这里，在智能体运动中，这指的并不是特定的一群人，它指的是所有人都可以拥有的一种能力。这是否意味着我们激发了新的人群加入黑客的各个群体——行动主义者、脚本小子、图一乐的人、犯罪分子和国家级行为体？这是否凭空增加了一个人群？
<details><summary>Original English</summary>
>> Literally my Ventel modem and the activists, it's right in the name. They're activists. They they might have a political cause. They might be doing it for the the lulls, you know, they might be doing it as a hobby. But you go to e-crime, very clear. You understand what they want. They're just trying to empty your bank account. They're just trying to, you know, get a nickel out of every transaction. Make a quick hit and get the heck out of there. Nation states obviously are trying to compromise, get comprom, you know, missile designs, whatever it happens to be. They they have a very um uh strict mandate. Now you put agents in here that doesn't in the agentic movement this doesn't speak to a specific group of people. It speaks to a capability that all people can have. Does this mean we've inspired new people to join the different constituencies of hackers, the activists, the script kitties, the people who are, you know, doing it for the lols, the criminals in the nation states. Does this add another group of people?
</details>

>> 你正在铸造外面更多的对手。在看待这些群体的类型、描述他们从国家级行为体一直到行动主义者的身份时，你说的完全正确。我们目前看到的显然大量集中在电子犯罪领域，所以你基本上是在整个技术栈中上下铸造新的对手，但如今电子犯罪是一门价值 200 亿美元的生意，无论是勒索软件还是敲诈软件。入侵是如此容易，赚钱也是如此容易。所以电子犯罪是目前绝对蓬勃发展的领域之一，人们正在从中赚大钱，而各大公司正在买单以赎回数据或确保数据不被泄露。但这其中的底线在于：在作为新顶级掠食者的“智能体国家”世界中，就整个技术栈上下的能力而言，每个人现在都处于同一个竞技场上。
<details><summary>Original English</summary>
it you're you're minting more adversaries that are out there and you're exactly right when you look at the these sort of groups and describing who they are from nation state all the way to activist um what we're seeing obviously is a lot in e-crime so it's you're you're basically minting new adversaries up and down the stack but e-crime is a 20 billion business today whether it's ransomware whether it's extortionware um it's just so easy to get in and so easy to make money So this is one of the areas that is absolutely booming right now uh is e-rime and people are making a lot of money and companies are paying the tab to get their data back or make sure that it's not leaked. But the the bottom line in this is in the agent state world as the new apex predator everyone is now on the same playing field in terms of capabilities up and down the stack.
</details>

>> 我们上次交谈时——按网络安全的年份算大约相当于过去了 20 年，但实际上那是 10 个月前——你把俄罗斯描述为能力最强的国家之一，但采取的是低调而缓慢的策略，他们有一套非常独特的动机。你把中国描述为“砸门抢夺”（smash and grab），但技术越来越高超。这意味着国家级行为体、犯罪分子和行动主义者之间的界限全部被拉平了。他们现在拥有了完全相同的能力。所以在某些方面，这意味着防守方也拥有了相同的能力。那么净结果呢？如果大家拥有相同的武器，而防守方拥有无限的 GPU，对吧？这是其中的一部分，对吧？好人应该拥有更多的算力访问权，更多接触前沿模型的机会。这是否意味着我们最终会因此获胜？我知道我有点直接跳到故事的结尾了，但当人们看到那个金字塔时，可能心里就是这么想的。
<details><summary>Original English</summary>
Now when we talked last time and that was I think about 20 years in cyber security and cyber years but it was 10 months ago. You describe Russia as uh amongst the most capable but low and slow they have got a very unique set of motivations. Chinese kind of described them smash and grab that you know but getting better. This means the difference between a nation state and a criminal and a activist. It's all been level set. They they all have the same capability now. So in some ways that means the defense has the same one. So net net net net. Am I correct in thinking if everybody has the same weapon and the defense has unlimited GPUs, right? That is a piece of this, right? The good guys should have more access to compute, more access to frontier models. Does that mean we're we're going to win eventually uh because of that? I know I'm kind of jumping to the end of the story here, but that's probably what people are thinking when they see the pyramid.
</details>

>> 嗯，我认为那是我们必须前进的方向，那些也是像我们这样的公司以及其他公司正在努力解决的事情。但如果你回到我提到的 Hugging Face 的例子，那些防御能力企业并不一定能用上，对吧？因为他们没有模型的访问权限，模型拒绝了他们，等等。所以现在这在某种程度上是一场不对称博弈，进攻方实际上领先于防守方，安全行业以及这些大语言模型（LLM）的提供商等有责任让客户能够拥有与进攻方相同或更高水平的智能体防御能力。正因如此——我们稍后会讨论行业中正在发生的其他一些统计数据——目前进攻方处于领先地位，因为模型太唾手可得了。即便你在前沿模型周围增加更多护栏，也无济于事。对于这些经过消除处理的模型，魔鬼已经从瓶子里放出来了，你直接拿来就能用。然后我们稍后会讨论其中的一些框架。所以，你知道，我真希望这是一张股票走势图，因为在今天录制这期节目时，这是唯一上涨的东西。你知道，
<details><summary>Original English</summary>
>> Well, I think that's where we have to go and and that those are things that like companies like ours and others are working on. But if you get back to the the hugging face example that I talked about, those defensive capabilities weren't necessarily available to to the companies, right? Because they didn't have access to the models, the models refused them, etc. So right now it's a bit of a an asymmetric game where the the offense is is actually ahead of the defense and it's incumbent on the security industry and and the providers of these LLMs etc where we can enable customers to have the same or better level of agentic defenses than the offense. And this is why and we'll get into some of the other stats of what's happening in the industry, but right now uh the the offense is ahead because the models are so available. Even if you you put more guard rails around the frontier models, doesn't matter. The genie's out of the bottle with these obliterated models, you're good to go. And then we'll talk about some of the frameworks here in a minute. So, you know, I wish this was a stock chart because this is the only thing that's up today as we film this. You know,
</details>

>> 这对科技界来说是艰难的一周。这对科技界是艰难的一周。这可不是科技股的走势图。
<details><summary>Original English</summary>
>> it's a rough week for tech. It's a rough week for tech. That is not a a tech uh stock chart.
</details>

>> 不是，倒过来看才是。
<details><summary>Original English</summary>
>> No, you flip it upside down, it would be.
</details>

### CVE 漏洞暴增与组合利用

>> 是的，没错。所以，这真正意味着什么，我想让大家感受一下情况的严重性。我们来对此做一点界定。我们有一种被称为 CVE 的东西，即通用漏洞披露（Common Vulnerability Exposure）。本质上，这些是人们发现的所有漏洞，并被记录在一个目录中。好的。所以如果你看一下这些 CVE 的历史，在图表上可以看到，你知道，它一直比较平缓，然后突然到了去年、今年，它就像呈指数级增长了，对吧？为了让大家对这个概念更清晰，仅仅今年一年，我们发现的 CVE 数量就占到了有史以来发现的全部 CVE 的 25%，对吧？想想看。这随后将真正驱动我们在系统停机方面所看到的现象、人们正在做的事情，以及从对手角度来看这显然意味着什么。但是眼下我们看到的是，这就是 Mythos 时刻以及类似 Daybreak 等项目带来的冲击。但这是过去大约八个月里每个人在开源领域以及各种商业软件中寻找漏洞的结果，而这接下来将再次引发我们在攻击和停机中看到的情况，但这是一次巨大的激增，几乎是每个月翻一番。所以，对于正在收听的各位，如果我们看一下这张图表，以往每年这些公布的利用程序、这些 CVE 大概有几千个，而 2026 年迄今为止已经达到了 17,000 个。现在，针对这些利用程序，针对我们安全机制和软件中的这些漏洞，我假设其中有一定比例是因为我们交付了多得多的代码，因为我们看到了代码生成 LLM、结对编程和 Copilot，它们大致是在那个数量开始激增的时期开始真正起步的。所以，我假设其中有一部分是因为我们在交付更多的代码，但绝大多数——如果我说错了你可以纠正我——可能是一直存在、只是处于休眠状态且未被发现的漏洞。我说的对吗？
<details><summary>Original English</summary>
>> Yeah, exactly. So, so really what this means, I I wanted to to just give you the gravity of the situation. So, the let's let's define this for a bit. So, you have something known as as a CVE, common vulnerability exposure. And essentially, those are all the vulnerabilities that people find and they log in a catalog. Okay. So if you look over the history of of these CVEes and you can see it on the chart there, you know, it kind of kicks along and then all of a sudden we get to, you know, last year now this year and it's like, you know, exponentially increased, right? So just to put this into perspective, just this year we've found 25% of all the CVES for the entire entirety of finding CVES, right? Think about that. And this is really then going to drive what we're seeing in terms of some of these outages and what people are doing and obviously what it means from uh an adversarial pers perspective. But right here what we're seeing is this is the mythos moment and the like you know daybreak etc. But this is the result of the last sort of eight months of everyone looking for vulnerabilities across open- source across all kinds of you know commercial software and and this then is going to set up again what we're seeing in in attacks and outages but it is a massive surge and it's it's literally doubling every month. And so if we were to look at this chart for those of you listening uh you know couple of thousand of these CVEes these published exploits here you know every year and then 17,000 uh thus far in 2026. Now, these exploits, these holes in our security, in our software, I'm assuming that some percentage of those are because we shipped a lot more code because we we see coding LLMs and pair and co-pilots that kind of started in earnest at a time when it started to ramp up there. So, I'm assuming some number of these are because we're shipping more code, but the majority are probably, you correct me if I'm wrong here, exploits that have always existed that just were dormant and not found. Am I correct?
</details>

>> 没错。绝大多数都是休眠状态的、一直没有被发现的漏洞；如果回溯到你们讨论过的最新的 PHP 漏洞之一，你知道，它可以一直追溯到大概 2004 年。因此，一旦你开始审查所有的代码，这些模型最强大的地方就在于它们可以跨大量较低风险的漏洞进行排查，并且能够将它们串联在一起，最终形成真正的风险暴露。这意味着什么，以及为什么环境变得越来越糟——如果以 PHP 为例，有些问题在过去四五年里就已经被知晓了。但是创作者们当时审视之后认为：“嗯，是的，这确实是个问题，但它并不是真正可被利用的，所以我们不用费尽心力去修复它”，因为这需要他们做一次不小的手术式改动。现在的突破在于，人们不仅发现了新的漏洞，而且能够实际证明那些我们已知存在的旧漏洞是可被利用的。这稍微有点细微差别，但确实有大量曾经不可利用的漏洞现在变得可利用了。
<details><summary>Original English</summary>
That's correct. The the vast majority of these are going to be dormant that haven't been found for you go back to the one of the latest PHP vulnerabilities which you guys have talked about, you know, it goes back to like 2004. So once you start looking at all the code and the the the the great thing about these models is they they can look across lots of lower risk vulnerabilities and they can chain them all together where you actually have an exposure. And what this means is and and why the environment is is just getting worse and worse is that if you take PHP as an example, there were issues that were known for the last four or five years. But the the the creators looked at and said, well, yeah, it's a problem, but it's not really exploitable, so we're not going to go through the headache of fixing it because it was it was a bit of surgery that they needed to do. Now, the unlock is people not only finding new vulnerabilities, but actually being able to prove the old ones that that we know are out there are exploitable. It's it's it's it's a bit nuanced, but there's plenty of exploitable vulnerabilities that that are now exploitable that weren't.
</details>

>> 再次强调，对你的听众来说，这 17,000 个是一个巨大的增长。我是说，我们今年发现的数量之多简直令人难以置信。
<details><summary>Original English</summary>
>> And this 17,000 again, uh, you know, for your listeners, this is a massive increase. I mean, it's just unbelievable how how much we found this year.
</details>

>> 在某些方面这算一线希望，难道不是吗，George？我们发现了所有这些脆弱的、人们忘记锁上的后门，没有安装报警系统，人们可以翻过栅栏。所以其中一些极其严重，有些则微不足道。根据我的理解，智能体擅长的是将其中几个漏洞结合起来。所以在那 17,000 个漏洞中，可能有三四个配合得非常精妙，人类单凭暴力手段或技术水平根本无法达到，但智能体可以。所以这里有两个问题：这是一线希望吗？也许你可以谈谈结合发现几个漏洞的情况以及会产生什么后果。
<details><summary>Original English</summary>
>> And now there is that's a silver lining in some ways, is it not, George? you you we found all these uh brittle, you know, back doors that people forgot to lock. Uh didn't put an alarm system on. People can hop the fence. So, some of these are extremely serious. Some of them are ticky tacky. And and from what I understand, what the agents are good at is maybe combining a couple of these. So, in that 17,000, there might be three or four that work very elegantly together that a human would just not through brute force or sophistication be able to get to, but the agents can. So, couple of questions in there. Is this a silver lining? And then maybe you could talk about the combination of finding a couple of exploits and what that does.
</details>

>> 是的。让我们翻到下一张幻灯片。我们就把它停在那里，因为那正好展示了增长——从 10 月到 10 月增长了 300%。好的。
<details><summary>Original English</summary>
>> Yeah. So, let me let's go to the next slide. We'll just leave it up there because it'll that'll give you just the increase October to October is 300% increase. Okay.
</details>

>> 我的天啊。
<details><summary>Original English</summary>
>> My lord.
</details>

>> 所以，这在本质上意味着——比如漏洞串联（vulnerability chaining）或堆叠这些漏洞，为了给大家简化解释：你可能会面临一个组合，同样为了简化说明，你有低、中、高风险漏洞；然后还有可利用性，也就是“我存在一个软件问题”，而可利用性则是“我能够实际利用该问题”。因此，如果你遇到低风险漏洞的组合，从抽象角度看你会觉得“好吧，那确实是低风险的，不是我的优先事项”。但正如你所指出的、以及我们在这里讨论的，AI 非常擅长将它们结合起来，你可以抓取 3 个、4 个、10 个、100 个低风险漏洞并将它们串联在一起，从而制造出一个具有远程代码执行（RCE）能力的高风险漏洞。这意味着你完全控制了系统，可以远程完全掌控它，然后一切就结束了。这确实是 AI 带来的重大突破，也是我们正在目睹的现象，以及这些攻击实际上是如何发生的。
<details><summary>Original English</summary>
So, so what that means essentially like vulnerability chaining or stacking these vulnerabilities just to simplify it for everybody is you can have a combination of very just again simplifying you have low medium and high risk uh vulnerabilities and then there's exploitability which is I have a I have a software problem and then exploitability is I can actually take advantage of that problem. So if you have a combination of low risk vulnerabilities, they in the abstract you would go okay that that's really low risk is it's it's not my priority. But what you're saying and and what we're talking about here is AI is so good at actually combining these that you can take three 4 10 100 lowrisk vulnerabilities and chain them together to create a high risk vulnerability with remote code execution. meaning like you fully own the system, you can fully control it remotely and then it's game over. And that that's really have has been the big unlock in uh in in AI and what we're seeing and and how these attacks are actually taking place.
</details>

### 修复即崩溃还是被攻破

>> 是的，所有这些都在浮出水面，这太非同寻常了。我们现在在新闻头条中经历的事情中，有多少是人们试图打补丁和清理所有这些新发现，又有多少是人们在实施漏洞利用？因为在我在 IT 行业的那段短暂时间里——从 80 年代末到 2000 年代初——技术债总是落后于功能竞赛，人们总是在努力交付出色的东西。所以总会有一定程度的技术债。但是当你升级和给系统打补丁时，那才是出故障的时候。有时补丁不起作用；有时计算机没有足够的内存；有时存储空间不足。不管原因是什么，补丁没有生效，数据库突然离线，现在 Shearman & Sterling 的 500 名律师无法访问他们的文档了。这可是一个真真切切的真实故事。所以，我们现在所经历的，有多少是补丁工作以及好心修复导致了诸如系统停机之类的下游效应，又有多少是实际的攻击？
<details><summary>Original English</summary>
>> Yeah, this is uh so extraordinary that these are all uh surfacing now. How much of what we're experiencing right now with the headlines in the news are people trying to patch and clean up all of these new discoveries versus people doing exploits? Cuz in my brief time in it from, you know, the in the late 80s into the early 2000s, uh we um we the technical debt was always behind the feature race and you know, people were always trying to get great things. So there's some level of technical debt. But when you upgraded and patched systems, that's when things broke broke. Sometimes the patch didn't work. Sometimes you didn't have enough memory in the computer. Sometimes you didn't have enough storage. Whatever it was, the patch didn't work and all of a sudden the database is offline and now you got 500 lawyers at Sherman Sterling can't get to their documents. So like a true true story here. Um, so how much of what we're experiencing now is patchwork and good work that causes downstream effects like downtime versus actual attacks.
</details>

>> 我们今天所处的现状——你切中了要害——就是当你部署补丁时，出问题的概率很高。我们正处于一个我称之为“修复即崩溃，还是被攻破”（break or breach）的节点。好的，修复即崩溃，还是被攻破。
<details><summary>Original English</summary>
>> So where we are today and you hit the nail on the head is when you roll out a patch, you know, there's a high probability that something could go wrong. And we are at a point what we're seeing is what I call break or breach. Okay, break or breach.
</details>

>> 修复即崩溃，还是被攻破。
<details><summary>Original English</summary>
>> Break or breach.
</details>

>> 这意味着打补丁的紧迫性极高，因为时间窗口已经完全被压缩了。比如微软发布了一个补丁，人们以前有 30 天的时间去逐步推行并完成所有这些流程；而现在考虑到我们看到的某些风险暴露——无论是 PHP 还是本周发布的最新 Java 漏洞——企业现在不得不做出抉择：我们是否要以机器般的速度仓促打补丁，冒着可能导致系统故障的风险？当然，他们不想弄坏系统，但他们急于打好补丁，因为他们知道安全窗口是如此之小。还是他们不打补丁，然后可能被攻破？这就是为什么我说“修复即崩溃，还是被攻破”。在我的职业生涯中，这确实是第一次，我看到有公司的 CEO 真的打电话给我——他们因为 PHP 的风险暴露打电话给我并询问：“我们是不是应该直接把系统下线？”比如，“我们那个为全球提供服务的业务，我们直接把那一块下线，因为我们必须打补丁。我们到底该怎么办？”这确实是我们所看到的现状。所以当我们思考这些停机事件时——同样，我们可以参考公开的信息，实际上我也与很多受影响的组织进行了交流——很大一部分再次集中在人们发现问题、人们部署补丁、执行不顺利上；每个人的初衷都是好的，但是补丁的数量实在是太大了。让我把这个放在具体背景下说明：你遇到了 Mythos 时刻的爆发，再次说明，那是我对能够极快发现所有这些漏洞的 AI 和安全智能（SI）的总称。因此，我们正在以指数级的速度发现漏洞；我们正在以指数级的速度创建补丁；但我们在部署补丁时撞上了音障。这就是问题所在。这就是为什么幻灯片上有这个转折点。因此，作为一个行业，我们现在正在为过去二三十年累积下来的所有技术债务买单。账单现在到期了。[唱歌]
<details><summary>Original English</summary>
Now what that means is there's such a rush to patch because the the the window has totally collapsed in terms of you know Microsoft comes out with a patch and people used to have 30 days and they'd get it rolled out and they'd go through all these sort of processes and now when you think about some of the exposures that we've seen whether it's PHP whether it's the latest Java vulnerability that came out this week companies are now they're they're sort of have to make a decision. Do we rush to patch at machine speed potentially breaking something? Of course, they don't want to break something, but they they they're rushing to to get it patched because they know the window is so small. Or do they not patch and potentially be breached? This is why I say break or breach. And for the first time really in my career, I've seen companies literally CEOs call me, they called me with PHP uh exposure and they said, "Should we just take our stuff offline?" like our service that you know services the world, we'll just take that piece offline because we got to patch it. Like what should we do? So this is really what we're seeing. So when we think about these outages and you know again we we can go by what's what's publicly out there. I actually talked to a lot of the the the impacted organizations, but a lot of it is again focused on people finding issues, people rolling out patches, things not going right, and everyone has the right sort of intentions, but there's the volume of patches is so high. So, let me just put this in context. You've got the mythos moment that comes out, and again, that's my sort of bucket term for, you know, AI, SI that can find all these vulnerabilities uh very quickly. So we're finding vulnerabil vulnerabilities at an exponential pace. We're creating patches at an exponential pace, but we hit the sound barrier of rolling out a patch. That's the problem. And that's why you have the breakover uh on the slide here. And so what we as an industry, we're now paying the bill for all the tech debt that's built up over the last, you know, 25 30 years. The bill's come due now. [singing]
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

>> 在一个由 AI 驱动的监控世界里，财务隐私比以往任何时候都更加重要。比特币给了我们无法被随意印制的货币。Zcash 给了我们无法被窥视的货币。Zcash 是加密的比特币，默认具备隐私属性，因此您的余额、付款和历史记录始终属于您自己。您的财富超越了数据经纪人、大企业和 AI 的视线。保护您自由的货币。下载 Visor 钱包，今天就开通使用 Zcash。
<details><summary>Original English</summary>
>> In a world of AI powered surveillance, financial privacy is more important than ever. Bitcoin gave us money that can't be printed. Zcash gives us money that can't be seen. Zcash is encrypted Bitcoin, private by default, so your balance, payments, and history stay yours. Your wealth beyond the eyes of data brokers, corporations, and AI. Money that protects your freedom. Download Visor wallet and start using Zcash today.
</details>

>> 账单现在到期了。嘿，这总是，你知道，你坐在那里，喝了很多酒，点了一些特色菜，然后，账单来了，有时让人有点震惊，但我不得不认为，这现在给了某些机构道德高地或筹码去说：“我们早就告诉过你们我们需要停机来修复它并减少其脆弱性。现在你们把我们当回事了吗？”因为我再次想起自己在该行业从事 IT 工作的有限时间里，人们总是在说：“我们不能停机 6 小时，你知道，这是绝对不可能的。”所以我们就不得不做出非同寻常的妥协，试图将这个时间窗口压缩到 60 分钟内。当时我就在想，律师们连一天假都不能放吗？他们周日或圣诞节就不能休息 6 个小时，而我们所有人都必须在圣诞节和感恩节跑过来做这个？不，它必须在线，窗口必须非常狭窄，你知道，那太混乱了。然后我们还必须构建一个并行系统以防他们需要，对整个系统进行镜像。现在，我认为他们有充分的底气说：“听着，这将是一次计划内的停机，而且有非常充分的理由这么做。”如果这些显著的停机中有六分之六是因为打补丁引起的，我认为这就给了团队充分的底气去说：“嘿，是的，我们周日要放假。这个周日你不需要登录 Outlook 待上六个小时。去带你的孩子们去公园吧。”呃，是的。
<details><summary>Original English</summary>
>> The bill's due now. Hey, it's it's always uh you know, you sit there, you're having a lot of drinks, you you order some of the specials and uh yeah, it's the bill comes and it's a little shocking sometimes, but I I got to think this has given uh some organizations now uh the high road uh or the leverage to say, "We told you we needed to take this thing down to fix it and make it less brittle. Now, do you take us seriously?" because I remember again back to my finite amount of time in this industry doing it there were it was always like well we can't be down for 6 hours you know just it's not possible so then we had to go do unnatural things to try to close this window down to 60 minutes and I was like the lawyers can't take one day off they they can't take 6 hours off on a Sunday or Christmas day and we'll all come in on Christmas and Thanksgiving and do this no it has to be online we has to be a narrow thing you know it was it was so chaotic. We then we'd have to build a parallel system in case they needed, you know, mirror the whole system. Now, I think they have the high ground to say, listen, this is going to be a scheduled outage and this is a really good reason to do it. If six and six of these outages, you know, that are notable were because of um patching that this I think gives the high ground to the team to say, "Hey, yeah, we're taking Sunday off. You don't need to be on Outlook this Sunday for six hours. Take go take your kids to the park." Uh yeah.
</details>

>> 是的。这就是我们当前的处境，因为他们的节奏太快了。他们宁愿承担一定的停机时间，正如你所说，这在今年之前是绝不可能发生的事情。各大公司以前会说：“嘿，我们要做到 5 个 9（99.999% 可用性），我们绝不会这么做。”但他们现在正在做出这样的决定：如果他们无法及时打上补丁，如果他们无法落实缓解控制措施，他们就会把系统下线。但这再次构成了我们所生活的世界——现在的这种“修复即崩溃，还是被攻破”。最终，作为一个行业，我们必须变得更好。但我曾与许多客户进行过交流，他们说：“嘿，这现在将成为一个催化剂，因为我们一直在向所有愿意倾听的人呼吁：
<details><summary>Original English</summary>
>> Yeah. And and that's where we are again because they're they're moving so fast. They would rather take um take some downtime which as you say is like that was this would never happen you know before this year. Companies would be like hey we're 59s we're never doing this but they are making this decision you know if they can't patch it in time if they can't put mitigating controls in place they'll take it down. But again, this is kind of the world that we live in is is now this this break, you know, or or breach. And ultimately, as an industry, we've got to get better. But I've had many conversations with customers who have said, "Hey, this is going to be a catalyst now because we've been telling everyone
</details>

>> 我们必须实现现代化。”对吧？如果你是一家云原生公司并遇到了问题，你可以更新模板，一个临时工作负载（ephemeral workload）下线、重新上线，补丁就打好了，这会变得容易得多。但如果你考虑这些传统行业——可能是金融业，对吧？可能是关键基础设施，可能是医疗保健——他们拥有如此庞大的遗留系统，以至于他们现在必须经历这种现代化改造，才能达到补丁周期近乎瞬时的程度。这同样也是行业内的一个机遇。
<details><summary>Original English</summary>
who would listen, we've got to modernize." Right? If if you're a cloudnative company and you have an issue, you can update the template and an ephemeral workload, a temporary workload, you know, goes down, comes up and it's patched, like it becomes a lot easier. But if you think about these industries, it could be finance, right? It could be um critical infrastructure, it could be healthcare, they have so much legacy that they they've got to go through this modernization now to get to a point where the patch cycles are like almost instantaneous. And that that's an opportunity in the industry as well.
</details>

>> 还有微软的那次停机，波及了很多人。Microsoft Outlook、人们的电子邮件，要知道世界上很大一部分都在依赖这款软件运行。微软拥有全球最大的企业级软件业务，数以亿计的白领员工工作在 Office 365 套件中。那次事件具体涉及到 Teams，并且大家当时都以为自己被黑了，但实际上他们遇到了——我认为是网关和服务器在向人们提供电子邮件服务时出现了某种缺陷。这是一个庞大、复杂且棘手的问题，对吧？你必须清楚，如果有人读了 10 封邮件，而这些邮件随后又显示为未读，大家就会抓狂。这是一个巨大的同步数据库，有着海量的服务器，涌入并冲击这些服务器的流量巨大。所以如果其中一台出现问题并发生故障转移，它就会引发级联反应。发生级联故障。这里面没有任何黑客入侵，这仅仅是一个基础设施层面的问题。对吗？复盘结论大致是偏向这个方向吗？
<details><summary>Original English</summary>
Well, and and the Microsoft one um that hit a lot of people. Microsoft Outlook, uh people's emails, you know, a lot of the world runs on this software. Microsoft has the largest enterprise software business in the world. Hundreds of millions of white collar workers live in the Office 365 suite. And this was specifically with teams and um everybody thought they got hacked and it was literally they had a I believe there's some flaw in the the the gateways and the servers and like serving up people's you know email. This is a big complex gnarly problem, right? You have to know if people if if somebody read 10 emails and they came up, you know, unread, people lose their mind. Like this is a big sinking database, tons of servers and it just the amount of traffic coming in and banging on those servers is great. So if one has a problem and it fails over, it just cascades. It cascades. There was no hacking here. This was just an issue of infrastructure. Correct. Is that what the postmortem is kind of leaning towards?
</details>

>> 复盘结论就是这样。
<details><summary>Original English</summary>
>> That that's the postmortem. Uh
</details>

>> 是的，我认为……你相信这个结论吗，还是你现在也站在阴谋论的角落里？
<details><summary>Original English</summary>
yeah, I think uh you believe it or are you conspiracy corner right now?
</details>

>> 不，你看，对于他们公布出来的内容，我必须按照其字面意思去接受。但我认为，当你审视这其中的很多问题时，我被问到的问题是：这是 AI 造成的吗？这背后有 AI 吗？我的回答是肯定的，只是不是你所想的那种方式。因为这是一种二阶影响：由于我们拥有了如此多能够实际排查并找出这些问题的 AI，人们正在争先恐后地去解决所有这些补丁。因此我们现在看到了由此产生的连锁反应。但是……
<details><summary>Original English</summary>
>> No, I look uh I I've got to take it at face value what they put out there. Um but I but I think you know when you look at a lot of this and the question that I get is you know was it an AI was AI behind this you know and the re and I would say yes but just not the way you you're thinking about it because it's it's a a second order sort of impact is because we've had so much AI that can actually go through and find these issues. People are scrambling to get all these patches uh sorted out. So we're now seeing the impact of that. But um
</details>

>> 所以给观众总结一下，
<details><summary>Original English</summary>
>> so to say that for the audience,
</details>

>> AI 可能发现了一些需要清理的问题。在执行清理的过程中，正如我们讨论过的，这并不是一门完美的科学。在一个实际上有两三亿人不断冲击服务器的服务中，他们遇到了级联错误，于是引发了雪崩。但并不是攻击导致了那 3 亿人的故障，而是为了修补潜在可被利用的问题所进行的清理工作导致的。
<details><summary>Original English</summary>
>> AI might have found something that needed to be cleaned up. In the execution of cleaning that up, like we talked about, it's not a perfect science. They had a cascading error in a service that's literally used by two or 300 million people banging on servers and it cascaded. But it wasn't an attack that caused those 300. It was the cleanup work to patch something that could have been exploited. Yeah,
</details>

### RTX 攻击框架与开源模型

>> 没错。这又回到了为什么各家公司都在关注是“修复即崩溃”还是“被攻破”。所以，RTX，这是一个 AI 攻击框架，它基本上是在夏末问世，然后在 10 月份被撤下。但本质上这是由中国某个人构建整合出来的，它确实是一个自主框架，可以利用你想要的任何模型；它基本上允许人类设定目标和目的，然后它拥有一系列的智能体和子智能体，可以进行侦察、查明例如某家公司在互联网上的所有系统。接着它可以进一步找出这些系统的所有缺陷，然后为这些系统构建利用程序。一旦找到漏洞利用手段，它实际上可以提升到最高权限（提权），然后基本上窃取所有数据。为什么这如此危险？这意味着什么？这意味着在确定目标后不到 3 小时的时间内，你就会看到一家公司被彻底攻陷。我们在这方面做了大量工作。在韩国各银行遭受攻击时，我们找到了一些控制端，他们当时实际上正在利用智能体对 200 家机构发起攻击。所以这里的底线是，回到我说的金字塔崩塌：
<details><summary>Original English</summary>
>> exactly. It gets back to why companies are focused on, you know, break it or or be breached. So, Rex, this is a an attack AI attack framework that came out um basically, you know, end of the summer and then into October it was taken down. But essentially this was built by someone in China who put it together and it and it really is an autonomous framework that leverages any sort of model that you want and it basically allows a human to create a target and goals and then it has a an a series of agents and sub aents that can do recon find out all of the systems say on the internet of a company. It can then go out and find all the flaws of those systems. It can then build the exploits for those systems. And once it finds an exploit, it can actually kind of get to the highest level or escalate privilege and then essentially steal all the data. So why is this so dangerous? And and what does this mean is that in less than 3 hours of targeting, you have a complete compromise of a company in less than 3 hours. And we've we've done a lot of work on this. when the Korean banks got hit, you know, we found some of the controllers and and they were literally running agents against 200 organizations and the the so bottom line here getting back to my collapse of the pyramid is
</details>

>> 任何拥有 RTX 或其分叉版本的人都可以做到这一点。现在，让我再给你提供一些统计数据。创建这个框架的人在韩国各银行遭到攻击后将其下架了。它原本完全是开源的。他们撤下了它，但当然每个人都已经有了一份副本。现在 RTX 有超过 12,000 个分叉版本。所以所有人都在这个平台的基础上进行构建。实际上，今天早上我还接到了我们事件响应（IR）服务部门的一个电话，属于呼入请求，有人遇到了问题并打电话给我们，那就是一起 RTX 攻击，对吧？所以，我们基本上派出了一些人去尝试协助他们。但每家公司都必须面对这一现实。正是这一点在真正刺激对所有这些漏洞的利用。让我们把这一切联系起来：漏洞呈指数级增长；现在 AI 已经普及，任何人都可以成为国家级力量；而且你拥有了一个基本上能在三小时内黑掉一家公司的框架。这就是大家都争先恐后去完成这些修复的原因。但这确实是现状。这也是人们需要记住的一点，因为先是 RTX，接着现在市面上还会出现一整套其他类似的攻击框架。但我们正在应对的就是这些超能攻击，而且其数量规模之大前所未见。
<details><summary>Original English</summary>
>> anyone with with Rex or or a fork of it can do this. Now, let me just put give you some more stats. The the person who created this after the Korean banks got attacked took it out. It was all open source. They took it down. But of course, everyone had a copy of it. There's now more than 12,000 forks of Artex. So, everyone is building on this platform. And I actually got a call this morning from uh from an in we have an IR service and inbound um you know, people have an issue and they call us and it was an RTX attack, right? So, you know, we we basically dispatch some people to try to help them. But every company has to deal with this. And this is what's really spurring the the exploitation of all those vulnerabilities. Like let's bring it all together. You have exponential increase of vulnerabilities. You've got now a AI that is democratized. Anyone can be a nation state. And you've got a framework that can basically hack a company in three hours. And that's the rush to get all this stuff done. But that's the state of the state. And that this is the one people need to remember because it's RTX and then there's going to be a whole host of other sort of attack frameworks that are out there now. But these hyper attacks are what we're dealing with and it's coming at a volume we've never seen before.
</details>

>> 是的，这就非常自然地引出了开源的话题。这是一个开源框架，大家都在共享代码。然后还有来自中国的开源模型，人们对这些模型进行了分叉。我们现在有了一些国家冠军企业，我们自己也有一些。正如你之前所说，只要把它们放在合适的 harness 中，给它正确的指令集，它们就相当强大。这里的好消息还在于，因为具有透明度，因为我们在此事上见到了阳光，你可以看到 RTX 的每一个细节。你能看到那 12,000 个分叉，你能找到这些分叉，你甚至可以渗透进去。而且我确信我们的网络防御力量和许多其他国家（如以色列、俄罗斯等）可能都在其中。他们可能已经有行动人员身处其中、为它贡献代码、对其进行分叉等等。但它是已知的，你拥有一个完整的数据集来进行应对，以消除其威胁。所以也许你可以发表一下见解，我把发言权完全交给你，聊聊开源的本质——就在这周，有消息被泄露出来，称政府内部的对华鹰派试图对 Airbnb 和 DoorDash 搞“公开点名羞辱”（name and shame），警告他们如果使用这种中国的开源软件，或者说是开源软件——因为任何人都可以贡献代码。这些项目中有美国的贡献者，有法国的贡献者。它是开源的，任何人都可以贡献；任何人都可以用 VPN 创建一个匿名账户并贡献代码。谁知道都是谁贡献了代码，但我们确实清楚其中的每一行代码。然而，内部某些群体泄露了一场点名羞辱运动，声称：“我的天，如果你使用开源，我们就要强制你把它挂在官网上羞辱你。”这有点不可理喻。而且，这管用吗？使用开源是明智的。请在此就“开源被描绘成问题”发表一下看法，而在这一点上，我认为你和我大概有着相同的共识，即开源实际上是解决方案。
<details><summary>Original English</summary>
>> Yeah, this is a a great segue then into open source. This was an open-source framework. People were sharing the code. Then you have the open- source models coming out of China. People have forked those. We have some uh uh national champions now. We have some of our own. And you said before, you put them in the right harness, you give it the right instruction set. Uh and they're quite powerful. The good news here as well is that because you have transparency, because we have sunlight on this, you can see every single aspect of our text. You can see the 12,000 forks. You can find the forks. You can even infiltrate. And I'm sure our cyber defenses and many others, the Israelis, the Russians, etc. They're probably inside of this. They probably got actors in there contributing to it, forking it, etc. But it is known it has complete you have you have uh a complete data set here to work with to neutralize it. So maybe you could opine and I'll just give you the floor here on the nature of open source in a week where a story got leaked that the China hawks in the administration are trying to name and shame Airbnb and Door Dash and telling them if you use this Chinese open source aka open source because anybody can contribute. There's American contributors to these projects. There's French contributors. It's open source. Anybody can contribute. Anybody can create an anonymous account with a VPN and contribute. Who knows who's contributed, but we do know every line of that. So, a name and shame campaign was leaked by some group of people internally to say, "Oh my god, if you're using open source, we're going to make you put it on your website and shame you." It's kind of crazy. Like, also, does it work? Like, it's like smart to use open source. opine here on open- source being framed as the problem when I think you and I are probably in sync that open source is in fact the solution.
</details>

### 本地 AI、算力瓶颈与主权

>> 是的。我们来谈谈这个，因为这是一个热门话题，为了让大家对准基线：市面上有属于开放权重且开源的模型，也有属于闭源但开放权重的模型。因此我们这里讨论的很多内容，都是关于通过调整权重来达到你想要的效果的能力。我们从客户那里听到的反馈——财富 500 强中的大部分都是我们的客户——他们基本上都在说，正如你们在播客中长期讨论的那样，疯狂堆砌 Token（token maxing）的时代已经结束了。本质上，第一，他们希望将成本降至最低；第二，他们正在寻求 AI 主权。他们正在寻求数据主权。基本上，他们采取的方法是“我们要运行自己的模型”。你知道，他们很愿意使用美国模型，但市面上有大量的非美国模型实际上非常、非常优秀，我们也可以讨论这些。他们会去使用那些模型；他们会试图在这些模型周围设立护栏。所以，你知道，这其中可能存在一些风险敞口，你无法完全确定是否存在某个暗语可以激活模型中的某种行为。但是，凡是无法在本地处理的事情，他们就会通过模型路由转接给前沿模型。这就是……回到你绘制的关于前沿 Token 与开放权重 Token 的图表，以及事情在过去……
<details><summary>Original English</summary>
>> Yeah. So let's talk about that because this is a hot topic and and just to to get in level set you've got models that are out there that are open weight and open source and some that are closed source but open weight. So a lot of what we're we're talking about here is the ability to manipulate the weights to get to what you want. And what we've been hearing from customers and and we've got, you know, most of the Fortune 500 are are are customers and they're basically saying, you know, and you guys have talked about this on the pod for a long time, that token maxing is over and essentially they want to minimize the cost, one, and two, they're looking for AI sovereignty. They're looking for data sovereignty. And basically, they're taking the approach of we're going to run our own models. you know, they would love to use US models, but there are plenty of non- US models that are actually really, really good, and you know, we can discuss those. They're going to use those. They're going to try to put guard rails around those. So, they, you know, again, there there could be some exposure and you're not quite sure exactly if there's a secret word that can activate something in the model. Um, but anything that can't get done, then they're going to model route into the frontier. like this is where you know getting back to your your uh sort of charts on you know the frontier tokens versus the open way tokens and how things have flip-flopped over the last you know
</details>

>> 两个月里发生的彻底反转。
<details><summary>Original English</summary>
>> two months
</details>

>> 是的，这些在某种程度上是“暗黑 Token”，你看不到它们，因为它们运行在人们自己的服务器上，可以在本地计算机上工作。它们不计费，很难知道到底被消耗了多少。我们在互联网上有一些路由器能够告诉我们一些情况，也有一些中介机构向我们展示趋势，但趋势是：绝大多数 Token 将是开源的。按照定义，绝大多数货币化的 Token 将属于前沿实验室。人们很难同时理解这两件事。
<details><summary>Original English</summary>
>> yeah these are dark tokens in a way you don't see them because they're run on people's own servers can be work were on a local computer they're unmetered it's very hard to know how many are being used we have some routers on the internet that will tell us and some intermediaries to show us a trend but the trend is majority of tokens will be open source Majority of monetized tokens by definition will will be the Frontier Labs. Hard to for people to gro those two things.
</details>

>> 没错。没错。所以，我们现在看到的是，各家公司表示他们将使用某种开源、开放权重的模型，进行后训练并打造属于自己的模型；这相当于 Linux 当年所做的事情。你拥有一个版本的 Linux，如果你需要，你对其进行分叉并打造自己的版本；根据许可证的不同，你可能需要回馈社区，或者如果你使用的是 BSD，你可能直接使用就行了；但人们就是会创建自己的模型，并且将它们与自己的 GPU 结合使用，或者在本地使用。而且我认为，一年后当我们回到这里——希望我们不用等一年才再次交流——当我们审视将有多少本地 AI 被使用时，在我看来那将是极其惊人的。因为——这所有的一切又与这些开源、开放权重的模型紧密相连——如果你审视当前的限制因素，你会发现电力和算力（也就是 GPU）是瓶颈所在。据我上次了解，全球各地仍有大量通电且运转良好的系统。当你查看包括 NPU 和 CPU 在内的利用率时，几乎等于零，对吧？因此，将有大量的推理直接在终端系统上进行，然后人们会向外路由到前沿模型。当然，在那里面你必须处理一大堆安全问题。但核心思想在于，魔鬼已经出了瓶颈，我们基本上必须承认我们得与这些前沿和开放权重模型协同合作，这对生态系统是有益的。这对生态系统是有益的。
<details><summary>Original English</summary>
>> Correct. Correct. So, so what we're seeing now though is is companies saying that they they are going to use some open- source openweight model and they're going to post-train it and they're going to create their own and you know it's it's equivalent to what Linux did. you know, you had a version of Linux and if you wanted it, you forked it and did your own and you know, depending on the license, you might have to contribute it back or if you had BSD, uh, you may just use it, but people are just going to create their own models and they're going to use those with their own GPUs or or they're going to use them locally. And I think, you know, we come back here a year from now, hopefully it's not a year that we're talking, but uh and we look at how much local AI is going to be used, it's going to be off the charts in my opinion because the and and again, all this ties together of of these sort of open- source uh openweight models because if you look at the constraints right now, you've got power and and compute, you know, GPU as the constraint. Last I checked, there's a heck of a lot of systems that are plugged in still working fine across the globe. And when you look at the utilization, including MPU and CPUs, it's like nothing, right? So, there's going to be a lot of inference that take place that takes place on the the system and then people are going to route out, you know, to to Frontier. And, you know, there's a whole bunch of security issues you have to deal with there. But the whole idea is the genie is out of the bottle and we've got to basically recognize that we've got to work with these frontier and openweight models and it's good for the ecosystem. It's good for the ecosystem.
</details>

>> 是的。在这些本地模型上，你我的想法高度一致。在我们行业里有一点非常有趣：每当有人贬低在 Apple Silicon 或 Nvidia 本地模型上运行的本地模型时，你总能看出某人是在为自己的利益代言；微软现在也正与 Nvidia 合作进入这一领域，AMD 的 Lisa 刚刚展示了一些本地成果。我订购了……我真不想这么告诉大家，但你可以从 Apple 订购相当于 10 年前最强大服务器的设备，价格在 12,000 到 20,000 美元之间，具体取决于你配了多少 RAM。而在你我入行的时候，你买一台 PC XT 之类的电脑，在 1980 年要花上 4,000 到 5,000 美元，按今天的购买力折算也就是相同的金额——15,000 美元。机构中的每个人桌上都可以放一台这样的设备。我预测他们会的。这样你就拥有了 AI 主权。员工 90% 的工作都可以在本地完成。这对前沿模型意味着什么？每当有人投资了前沿模型公司，我一眼就能看出来。当你向他们解释这一点时，他们会说这绝对不可能发生。
<details><summary>Original English</summary>
>> Yeah. And you and I are in sync very much on these local models and it's very interesting in our industry. You can always tell when somebody's talking their book when they downplay local models running on, let's say, Apple silicon or Nvidia's, you know, local models or Microsoft's now getting into this in partnership with Nvidia. AMD Lisa just showed some local stuff. I ordered I mean I hate to tell you folks but like you can order what is the equivalent of the most powerful server 10 years ago for $12,000 to $20,000 depending on how much RAM you put in it from Apple. And when you and I started in the industry you could buy a PCXT and at whatever and it would cost you $4 or $5,000 in 19 in 1980 that's in today's dollars the same amount $15,000. Every single person in an organization could have one of these on their desktop. I predict they will. Then you have AI sovereignty. 90% of your jobs can be done locally for uh you know workers. What does that do to the frontier models? I can always tell when somebody is vested in a frontier model company. When you explain this to them, they said never happened.
</details>

>> 然后你的反应就像是，
<details><summary>Original English</summary>
>> And you're like,
</details>

>> 你知道，这很有趣。我桌上正摆着两台配备 512GB 内存的 Mac Studio，正等着我回家呢。
<details><summary>Original English</summary>
>> you know, it's interesting. I have I have two Mac Studios with 512 gigabytes sitting on my desk waiting for me when I get home.
</details>

>> 真的吗？你的到货了？
<details><summary>Original English</summary>
>> Oh, really? Yours came in?
</details>

>> 是的，到了。
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah.
</details>

>> 太神了。你会把它们堆叠起来，在上面部署 ExoLabs，然后全力投入运行。
<details><summary>Original English</summary>
>> Amazing. And you're going to stack them. You're going to put ExoLabs on them and you're just going to go to town.
</details>

>> 全套搞起。实际上，我有两台 Spark DGX 连接在一起，我们将把它们结合起来使用。
<details><summary>Original English</summary>
>> All of it. In fact, I've got two Spark DJXs that are tied together and and we're going to use all of them together.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 用于推理和训练等等。但这真的很有意思。但正如你所指出的，你说得太准了，就是你可以用这些 Studio 做到的事情。顺便说一句，我认为苹果会大获全胜。我认为他们在这方面会干得很漂亮。
<details><summary>Original English</summary>
>> For inference and and you know, training and all that. But it's it's really fun. But your point, you're spot on is what you can do with these studios. And by the way, I think Apple's going to kill it. Like I I think they're going to kill it on this.
</details>

>> 在我看来，对他们来说这将是一个极好的机遇和投资方向。
<details><summary>Original English</summary>
>> You know, to me, it's going to be a great opportunity uh and investment for them.
</details>

>> 我确实买了这只股票，我的想法是，John Ternus 是一名工程师。所以我们从 Tim Cook 走过来了——愿上帝保佑他享受美好的退休生活，他安排了一位供应链出身的人；而现在迎来了一位工程师，他完全清楚这个机遇就在眼前，AI 主权、桌面上的隐私。天哪，这可能会改变一切。而且这些标价 1 万到 2 万美元的 Mac Studio 利润率该有多高？
<details><summary>Original English</summary>
>> I literally have bought the stock and I'm just like John Turnis is an engineer. So you we went from Tim Cook, God bless him, have a great retirement, put a supply chain guy. Now you got an engineer in there and he knows full well that this opportunity is right there in front of him and AI sovereignty, privacy on your desktop. Oh my lord, this could change everything. And what's the margin on these 10 to $20,000 Mac studios?
</details>

>> 它们可不便宜。顺便说一下，他也是个车迷。所以有很多……
<details><summary>Original English</summary>
>> They they're not cheap. And and by the way, he's a car guy, too. So there's lots
</details>

>> 我之前还不知道这个。好的。很多……
<details><summary>Original English</summary>
>> didn't know that. Okay. Lots of
</details>

>> 讨论。是的，我在 F1 赛车比赛上碰到了他。所以我们聊了赛车和本地 AI。无论如何，我认为这是一个巨大的机遇。但就这里的观点而言：
<details><summary>Original English</summary>
>> discussion. Yeah, I was I ran into him at the the Formula 1 race. So, we were talking cars and and uh local AI. So, in any event, I think this is a great opportunity. But to you know, the point here is
</details>

>> 如果它走向本地化，它将为人们打开一个极其庞大的机遇，去创造自己的系统、开发自己的系统并在其周围建立生态。从安全角度来看，这才是真正令人兴奋的部分。围绕它你需要做很多工作。但这就是技术如此令人兴奋的原因。而且我认为，如果你现在把推理推向边缘，然后利用云端的容量，你就可以解决很多这种容量瓶颈问题。你始终会保留前沿模型，它们永远会领先一步。但是，伙计，就今天你在本地能完成的事情而言，对于在电子表格中处理工作、试图建立财务模型、撰写文本或制作 PPT 演示文稿的普通知识工作者来说，这已经太不可思议了。完全足够了。没错。
<details><summary>Original English</summary>
>> if it's going to be local, it's going to open up a massive massive opportunity for people to create their own, develop their own and create ecosystems around. And that's really the exciting part from a security perspective. There's a lot you have to do around it. But this is why technology is so exciting. And I think you can solve a lot of um sort of this capacity limitation if you if you're now taking the inference, you know, to the edge and then you're you're leveraging the capacity that's in the cloud. You're always going to have frontier and they're always going to be ahead of the curve. But man, for what you can do today locally, it's unbelievable for the average knowledge worker who's working in a spreadsheet and trying to build a model for a financial model or, you know, write some text or do a PowerPoint presentation. more than enough. Correct.
</details>

### 社会工程学与身份凭据攻击

>> 这对我来说就是那个巨大的机遇。你和我 10 个月前又在达沃斯聊过。嗯，今年我会在那里再次见到你。“好兄弟”（besties）们都要去。大家一直在问：“我们能把好兄弟们都带到那里吗？”看起来达沃斯将聚齐全部四位好兄弟，我们上次在那里度过了一段美好的时光。但是，你知道，很难把他们全凑齐。本周末我们在拉斯维加斯的 F1 赛场，也就是我现在所在的地方。我们来了三到四位好兄弟，所以核心四人组都会在。我们在那里会玩得很开心。但当时我们交流时，你说了句让我深有感触的话。我想你当时原话是这么说的：“既然可以直接登录，为什么还要费力破解（Why break in when you can log in）？既然可以直接登录，为什么还要费力破解？”现在想想钓鱼攻击。想想精准钓鱼（spear fishing）。钓鱼攻击——你知道，他们会给你发类似：“嘿，在这里登录，大家都要发奖金了。”James Dolan 曾对麦迪逊广场花园的员工做过一次 [笑声] 钓鱼测试，大意是：“嘿，我们都赢得了冠军，我们要开个派对之类的。您将获得纪念戒指或夹克。点击这里。”当然，组织里 30% 的人在接受过防钓鱼培训后仍然表示：“噢，我要拿到戒指了！”他们兴奋极了，点击了链接。现在他们全被拉去参加研讨会，再次学习不要点击收件箱里的链接等常识。精准钓鱼则是针对个人的攻击：“嘿，George，这是给你的特定活动的门票。”然后你还面临短信钓鱼（smishing）和电话语音钓鱼（vishing），侵入你的短信。AI 会对这产生怎样的影响？因为作为多家风投机构的有限合伙人（LP），同时我们自己的机构也有 LP，我现在不得不面对这种现实：有人开始给我发信息。顺便说一句，作为我们基金的 LP，我们绝不会在电话中打给你询问这类信息。当我们确实需要联系时，我们有一套新协议：我们会给你发邮件；你会拨打这个特定的电话号码；我们会挂断；然后我们会给你回拨。你知道，就是多层的人为因素防御机制。那么让我们谈谈这项技术带来的人为因素问题。你我都知道有人在某些加密货币的事情上这么做过：他们在 Zoom 上制作了 George 或 JCal 的虚拟形象来与某人交谈，通过虚拟头像诱骗他们交出信息，而且我认为这些虚拟形象已经开始跨越“恐怖谷”了。所以谈谈那种攻击途径吧，你们在研究针对它的对策吗？防御手段是什么？还是说这目前更多只是科幻小说而非现实？
<details><summary>Original English</summary>
>> And that to me is the this huge opportunity. You and I talked again 10 months ago at Davos. Well, I'll see you there again this year. The besties are coming out. It's been like, can we get the besties there? Well, it looks like all four besties in Davos and we had a great time when we were there last time. Uh but, you know, it's hard to get them there. So, we're at F1 this weekend in Vegas where I am. We got three or four besties. So, we're going to have all four core four. And so, we're going to have a great time there. But when we talked, you said something that stuck with me. And I think the exact way you said it was, "Why break in when you can log in? Why breakin when you can log in?" And now you think about fishing. You think about spear fishing. Fishing, you know, they send you like, "Hey, log in here. We just everybody's getting a bonus." Uh, so like literally James Dolman did a a [laughter] fishing test for the Madison Square Garden employees about, "Hey, we all won the championship. We're having a party or something. you're going to get your commemorative ring or jacket. Click here. Of course, 30% of the organization after going through fishing training was like, "Oh, I get my ring. They're so excited. They click on it." And now they're all dragged into a seminar to once again learn that don't click on links in your email box, etc. Spear fishing is when you go after an individual. Hey, George, you're you know, here's your ticket for the specific thing. And then you got swishing and bishing and going into your SMS. How does AI impact that? Because I've had to now with I'm an LP in a bunch of venture firms. I have LPs in our firms. People are starting to send messages to me. By the way, we will never call you as an LP in our fund and ask you for this type of information on the phone. And when we do it, we have a new protocol. We're going to email you. You're going to call us on this phone number. We're going to hang up. We're going to call you back. and you know just multi-layer human factor defense. So let's talk about human factors with this technology you and I understand somebody did this with some crypto stuff where they made a version of George or Jake Al on Zoom to talk to somebody and get them to give it up with avatars and these are starting to cross the uncount valley I believe. So talk about that attack vector and are you working on it and what's the defense there or is this more just science fiction than reality?
</details>

>> 我把这个问题一分为二。我是说，这里有很多可以谈的，但我们可以将其分为直接登录与深度伪造（deep fake）这两个层面。让我先从前者说起。正如你所指出的，直接登录确实比强行破解要容易。这里有几个关键点。第一，钓取凭据依然很容易。所以，有了 AI，你可以打造出令人惊叹的攻击活动，而且全都是自动化的。现在，
<details><summary>Original English</summary>
I'll bifocate this. I mean, there's a lot to talk about, but when we think about sort of the login piece versus maybe the uh the deep fake. So, let me start with it. To your point, it's easier to log in than to actually break in. There's a couple pieces there. One, it's still easy to to fish credentials. Um so, and with with AI, it you can create an incredible campaign. It's all automated. Now,
</details>

>> 需要记住的是，有人会说：“我有多因素身份验证（MFA）。我不仅有密码，还有其他必须要验证的东西。”那很好。你目前面临的挑战在于，这些攻击者不仅会拦截你的凭据，更重要的是他们会窃取会话令牌（session token）。所以设想一下，无论你使用的是 Outlook 还是 Gmail，随便挑一个网站，你完成了一次认证，之后每次阅读电子邮件时它并不会要求你重新认证。它……
<details><summary>Original English</summary>
>> um now the the thing to keep in mind is someone will say, well, I have multiffactor authentication. I have not only my password but I have something else that I have to you know authenticate with. That's great. The the challenge you have right now is that these attackers will actually intercept your credentials but more importantly they'll they'll steal the session token. So if you think if you think about like uh if you use Outlook when you or Gmail doesn't really matter pick a site you authenticate and then it doesn't ask you every time you read an email to reauthenticate. It's
</details>

>> 你点击了那个“保持 30 天登录”按钮，或者“信任这台计算机”，于是现在我们不需要每次都登录了，还有二次验证，以及人们因双重验证疲劳（2FA fatigue）而经历的精疲力竭，那确实是个现实问题。
<details><summary>Original English</summary>
>> you and you click that 30-day button or like trust this computer and like now we don't have to log in and the two factor and the exhaustion people experience from two factor fatigue which is a thing
</details>

>> 没错，所以从本质上讲，存在一个令牌，它在幕后基本上就像你的通行密钥（passkey），在表明：“嘿，我是 JCal，让我看邮件吧。”
<details><summary>Original English</summary>
>> right so essentially there's a a token which basically behind the scenes is like your pass key that says hey I'm Jal like just let me read my email
</details>

>> 对手会窃取那个会话令牌，因此它在接下来的 30 天里都已经处于已认证状态，然后他们就可以肆意行动了。
<details><summary>Original English</summary>
>> the the adversary will steal that session token so it's already authenticated for the next 30 days and then they're good to go.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 整个运作机制就是这样。通常在发生这类商业电子邮件破坏（BEC）事件时，他们接下来会进入你的 Outlook 邮箱。他们会创建自动规则——比如如果你有电汇这类的邮件，他们实际上会把它们移入你永远看不到的文件夹中，然后他们开始与目标对象进行通信。
<details><summary>Original English</summary>
>> And that's how it all works. Typically with um these sort of business email compromises, they will then go into your Outlook mailbox. They will then create automatic rules that will like if you have wires and those sort of things, then they'll they'll actually put them into folders that you never see and then and then they begin communicating with with the with the target.
</details>

>> 哇。
<details><summary>Original English</summary>
>> Wow.
</details>

>> 所以，这一切都……
<details><summary>Original English</summary>
>> So, and it's all
</details>

>> 太高明了。
<details><summary>Original English</summary>
>> so sophisticated.
</details>

>> 是的。而且你根本察觉不到，对吧？这就是我们正在目睹的现象。现在针对此事的下一个演变版本就是朝鲜人正在做的事情。同样，这就像是：“既然我可以直接让人入职并拿到他们的笔记本电脑，为什么还要费力破解呢？”所以这是……
<details><summary>Original English</summary>
>> Yeah. And you and you never see it, right? So that's that's what we're seeing. Now the next iteration of that is what the North Koreans are doing. And and again, it's like, well, why break in when I can just get somebody hired and get their laptop? So this is
</details>

>> 等等，你必须解释一下我们在这里谈论的是什么，因为你我都清楚，但公众并不理解这个概念：朝鲜人应聘工作、获得录用、让笔记本电脑寄送至一个虚假地址，然后通过 VPN 从朝鲜远程连接到某个妇女家中——那名妇女在家里囤了大约 80 台笔记本电脑最终被抓。呃，顺便说一句，对于这些求职者……
<details><summary>Original English</summary>
>> Wait, you you have to explain what we're talking about here because you and I know this, but the public does not understand the concept of North Koreans applying for jobs, getting jobs, and having a laptop shipped to a fake address and then VPNing into it from North Korea to some woman who has got busted with like 80 laptops in her house. Uh, you know, for these workers, by the way,
</details>

>> 那是在德克萨斯州。好的，很棒。德克萨斯州。我们继续。
<details><summary>Original English</summary>
>> it was in Texas. Okay, great. State of Texas. Here we go.
</details>

<!-- chunk 2/2 -->

>> 解释一下这里的背景。就是
<details><summary>Original English</summary>
>> Explain the background here. It's
</details>

### 朝鲜IT员工渗透内幕

>> 所以谈谈这个。所以，我们其实我想是几年前最早公开谈论这件事的人之一，我们当时其实在内部研发一些新算法。它被称作 signal，我们基本上是在试图从中把信号和噪声区分开来。所以，正如你可以想象的，在 Crowd Strike 这种规模下会发生很多事情，并且总是有这些你永远不想错过的微小信号。所以我们构建了这个，其中一部分是在我们进行全面测试时，我们觉得：“这真的很奇怪。”比如，“为什么到处都连接着这些类似远程键盘、鼠标、树莓派（Pi）的设备？这真的很反常。”当我们深入调查时，我们觉得：“好吧，我们其实认为——我们有一个情报团队，他们梳理了这件事情，他们说：‘我们认为这是朝鲜，并且我们认为他们是，你知道的，雇员。’”所以我们揭开了这一切，然后我们的人来找我说：“好吧，乔治，我们想联系这个特定的客户，但我们必须告诉他们，他们的雇员可能不是他们的雇员。”正如你可以想象的，这不是一件容易做到的事，对吧？这不像说，嘿，这可能是恶意软件，也可能不是恶意软件。你基本上是在说，比如，你知道的，鲍勃并不是鲍勃。所以我说，听着，我们就拿着我们发现的情况去找那些客户，告诉他们我们的看法。我们可能是错的，但告诉他们。而在最初的40次通报中，我们完全击中了事实。他们就说，我们从未见过这种情况。我们从未听说过。我们——他们对此一无所知。而现在这成了一个完整的行——你知道，现在这成了一个朝鲜获取工作的整个产业。而且我对此有一个精彩的故事。就是获取工作。正如你所说，他们让中间人（mule）把笔记本电脑送到一个设备机房（farm），然后他们接入进来，然后他们作为一个团队，在幕后工作，但他们同时也拥有对这些系统的访问权限。现在，关于这一点的最后一个故事是，我们曾与一家公司合作。我们通知他们出了问题，我们去找招聘主管，我们问：“你见过这个人吗？”他们说：“没有，他们面试——他们面试时没有开摄像头。我们从未
<details><summary>Original English</summary>
>> so talk about this. So, we we were actually I think one of the first to really talk about this publicly a couple years ago and we were actually uh working on some new algorithms internally. It was called signal where we were looking to essentially um separate the signal from the noise. So, there's a lot of things that happen at scale as you might imagine with with with Crowd Strike and there's always these small signals that you you never want to miss. So, we we built this and part of it when we were testing it all out, we're like, "This is really weird." Like, "Why are these like remote, keyboard, mouse, Pi devices being connected all over the place? This is really odd." And when we dug into it, we're like, "Okay, we actually think we have an Intel team and they went through it and they're like, "We think this is North Korea and we think that they are, you know, employees." So we we unfolded all this and and then our guys came to me and said, "Okay, uh George, we we'd like to contact this particular customer, but we have to tell them that their employee may not be their employee." This is not an easy thing to do as you might imagine, right? This isn't like, hey, this might be malware, it may not be malware. You're basically saying like, you know, Bob is not Bob. So I said, look, let's just go to what we found to those customers and tell them what we think. We could be wrong, but tell them. And the first 40 notifications, we were spot on. And they're like, we've never seen it. We've never heard about it. We, they didn't know anything about it. And now it's a whole in, you know, now it's a whole industry of where North Korea is getting the job. And I have a great story on it. Is getting the job. As you said, they're having mule send a laptop to a farm and then they connect in and then they as a team, they behind the scenes, they work, but they also have access to uh the systems. Now, my last story on this is we worked with a company. We notified them there was a problem and we went to the hiring boss and we said, "Did you ever see this person?" They said, "No, they interview they interviewed without their camera on. We never
</details>

>> 见过他们本人。”然后我们说：“好吧，那你们有麻烦了。是朝鲜。”然后人力资源部门的人说：“嘿，我们打算解雇他们。”然后他们说：“我们真的必须解雇他们吗？他们是团队里活干得最棒的。”我的意思是，大家极度渴望人才。我们正处于我们有生之年最低的失业率时期。呃，真是个自己坑自己的笑话。最——最绝的是，他们有这个IT员工，朝鲜人，等等。其中一家公司抓获他的方式是
<details><summary>Original English</summary>
>> met them in person." And we said, "Okay, well, like you have a problem. It's North Korea." And and the HR people said, "Hey, we're going to get rid of them." And they said, "Do we really have to get rid of them? They do the best work of anyone on the team." I mean, people are desperate for talent. We have the lowest unemployment of our lifetimes. Uh just such a self owner. The the the best one was they had this IT worker, North Korean, etc. And the way they busted him on one of these companies was
</details>

>> 他们说了——我不知道他们究竟说了什么，但类似于你能直接说一句“金正恩是头肥猪”之类的话吗？
<details><summary>Original English</summary>
>> they said like I don't know exactly what they said, but can you just say Kim Jong-un is a fat peg or something?
</details>

>> 那是我们做的。我们
<details><summary>Original English</summary>
>> We did that. We
</details>

>> 那是你们干的。
<details><summary>Original English</summary>
>> That was you.
</details>

>> 是的，那其实是——那是我们的一位情报人员，他叫亚当。他负责我们的对抗对手组织，他基本上告诉了我们当时合作的那家客户，让他们说那句话。
<details><summary>Original English</summary>
>> Yeah, that was actually was it was uh our intel guy, his name is Adam. he runs uh our counter adversary organization and he basically told uh the the customer that we were working on is to to say that.
</details>

>> 是的。而且当然，如果你人在朝鲜，
<details><summary>Original English</summary>
>> Yes. And of course like if you're in North Korea,
</details>

>> 这些可能是你不希望被摄像头拍到的话。金正恩对于——有点敏感
<details><summary>Original English</summary>
>> these are probably words you don't want captured on camera. Kim Jong-un is a little sensitive about the uh
</details>

### 完美代码与网络攻防博弈

>> 是的。我认为诺和泰（Ozempic）还没有普及到这位朝鲜领导人那里。你知道，我对这一切的预测是——抱歉又重新开启了采访。我只是想问你一个问题。如果——如果所有这些代码都被机器重写，它会变得脆弱得多。是否存在完美运行的代码或比如极度安全的代码的概念，以至于我们一两年后坐在这里可以说：“嘿，大家都认真对待了这件事，漏洞数量（n）大幅下降了。”还是说这永远只会是《Mad》杂志里的“间谍对间谍”那种总是不断升级的情况？是否存在某种好人能够，你知道，取得决定性胜利的版本？
<details><summary>Original English</summary>
>> Yeah. I don't think Osampic has made his way to the North Korean president yet. You know, my prediction on all this uh sorry to restart the interview again. It was just one question I wanted to ask you. If if all if if all this code gets rewritten by machines, it's going to be a lot less brittle. Is there a concept of perfect working code or like extremely secure code and we could be sitting here a year or two from now and we said, "Hey, everybody took this seriously and the n number of vulnerabilities goes way down." Or is this just always going to be the case of um spy versus spy for Mad Magazine where it just always escalates? Is there some version of this where the good guys win, you know, decisively?
</details>

>> 这是一个好问题，我——我其实经常用“间谍对间谍”这个比喻。我认为是符合你描述的后一种情况，因为即便——而且这一点很重要。即便漏洞为零，我们到处都有完美的代码，全世界都有完美的代码，你仍然会遭遇入侵。而且我认为很多人会看过去然后说：“好吧，我们只要赶紧把一切都打上补丁，我们就会没事了。”事实并非如此。我们应该打补丁。我们应该把问题清理干净。我们应该增加攻击难度。这很好。但你仍然会遇到围绕身份验证、身份标识以及其他即将发生的各种问题。所以，你无法彻底消除它。
<details><summary>Original English</summary>
>> It's a good question and I I actually use that that metaphor a lot of spy versus spy. I think it's the latter of how you characterize it because even and this is important. Even if there were zero vulnerabilities, we had perfect code everywhere, the entire world had perfect code, you'd still have breaches. And I think a lot of people look at and go, "Okay, we're just going to rush to patch everything and we're going to be good." That's not the case. We should patch. we should clean things up. We should make it harder. Great. But you're still going to have issues around authentication, identity, and just other things that are going to happen. So, you're not going to get rid of it.
</details>

>> 这意味着，从人工智能的角度来看，间谍对间谍就是红蓝对抗循环，你的进攻性AI将始终不得不对抗你的蓝色防御性AI，去寻找模式和侵入路径。以便你能够封闭所有这些途径，而这将是利用这类模型相互对抗以使我们能够为客户提供最高级别保护的重要组成部分。企业发起进攻合法吗？民族国家可以随心所欲，而且——而且他们确实这么做。但如果我经营一家公司，我发现，你知道，这些朝鲜人——你知道，已经渗透进来了，我是否被允许，比如，反向入侵他们？这里面是否存在一种进攻能力，最终会成为防御组合的一部分？
<details><summary>Original English</summary>
>> And what that means then is it's the spy versus spy is the the red blue loop from an AI perspective where your offensive AI is always going to have to run against your blue defensive AI to look for the patterns and and paths in. so that you can close all of those off and that that's going to be a big part of leveraging these sort of models against each other so that we can provide the best level of protection to customers. Is it legal for corporations to go on the offensive? Nation states can do what they will and and they and they do. But if I'm running a corporation and I find you know these North Koreans uh you know have infiltrated, am I allowed to like compromise them back? And is there an offensive capability here that will eventually be part of the mix?
</details>

>> 围绕这一点已经有一些讨论。就是能够做到这一点。在美国，它——我认为是第50编（Title 50），只有——只有政府才拥有这项权力，对吧？明白了。
<details><summary>Original English</summary>
>> There's been some discussion around that. It's it's to be able to do that. In the US, it's it's I believe it's title 50, which is only only the government has it, right? Got it.
</details>

>> 所以，呃，也许他们会扩大这个范围，而且已经有一些讨论。在我的想法中还没有什么是真正具体的，但我认为，你知道，最好的策略是拥有极强的防御，
<details><summary>Original English</summary>
>> So, um maybe they expand that out and there's been some talk. There's nothing that's really in my mind concrete, but I think, you know, the best best thing is have great defense,
</details>

>> AI和超级智能将成为我们未来提供该级别保护的方式。然后显而易见的是，如果出现问题，就要与执法部门合作，而且我总是告诉各家公司，特别是那些大公司，你知道，当你想要“向朋友求助”时，你首先应该有个朋友，对吧？你应该知道谁是你当地联邦调查局办事处的特工。你应该认识这些人，
<details><summary>Original English</summary>
>> AI, and super intelligence is going to be the the the future of how we provide that level of protection. And then obviously working with law enforcement if there is an issue that comes up and and I always tell companies, particularly the larger ones, you know, when you want to phone a friend, you should have a friend first, right? You should know who your local FBI office agents are. You should know these people
</details>

>> 因为你第一次打电话给他们的时候，不应该是当你出事的时候，对吧？我认为这真的很重要。
<details><summary>Original English</summary>
>> because the first time you call them is not when you have an issue, right? And I think that's really important.
</details>

### 结语

>> 好的，听着。来自 Crowd Strike 的乔治·柯茨，第二次做客节目。非常感谢你，我们达沃斯见，如果不更早见面的话。感谢大家收看 All-In 访谈。下次见。
<details><summary>Original English</summary>
>> All right, listen. George Curts, Crowd Strike, second appearance. Really appreciate you and I'll see you in Davos, if not sooner. Thanks for everybody for tuning in to the All-In interview. See you next time.
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

>> 我要全力以赴（All in）。
<details><summary>Original English</summary>
>> I'm going all in.
</details>