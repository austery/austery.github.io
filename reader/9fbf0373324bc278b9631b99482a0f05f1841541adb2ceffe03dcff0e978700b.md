---
author: AI Engineer
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ATMcd9tkhhc
speaker: AI Engineer
tags:
  - financial-analysis
  - ai-harness
  - deterministic-ai
  - trust-building
  - workflow-design
title: 构建可信赖的财务分析 Harness：从电子表格到确定性 AI 工作流
summary: 演讲者 Francesco 和 Filipe 在 AIE 工作坊中提出，财务分析的核心瓶颈已从速度转向信任。他们主张摒弃仅依赖电子表格或纯提示词驱动的非确定性 AI 方法，转而构建具有确定性后端代码的“Harness”。通过引入测试、证据链和明确的工作流，确保 AI 在金融领域的应用具备可追溯性与可靠性，从而在模糊性与精确性之间建立用户信任。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Francesco
  - Filipe
companies_orgs:
  - Monzo
  - Nubank
products_models:
  - Claude
  - ChatGPT
  - Looker Studio
media_books: []
status: evergreen
---
<!-- chunk 1/11 -->

### 开场与自我介绍

早上好。

[音乐]

感谢大家的到来，欢迎来到 AIE。我想这不仅是对大家，对我们也是第一场演讲。

<details><summary>Original English</summary>

Morning.

 [music]

Thanks everyone for being for being here

and welcome to AIE. I guess first first

session for everyone and for us as well.
</details>

>> 我们想先做个自我介绍，并告诉大家我们今天将要讨论的内容。我们认为我们不能再只靠电子表格进行沟通了。因此，今天的主题完全是关于构建一个真正值得你信任的财务分析 Harness。

<details><summary>Original English</summary>

>> So h we wanted to introduce ourselves

and tell you about what we're going to

discuss. We think we need to stop

talking with spreadsheets. So, this is

all going to be about building a

financial analyst harness that you can

actually trust.
</details>

我们是 Francesco 和 Filipe。先简单介绍一下我自己。我来自委内瑞拉，在英国生活了大约七年，最近刚搬到马德里。我从事数据相关的工作，同时也和 Felipe 一起在一家银行工作。我喜欢在我到访的每座城市寻找最棒的餐馆。所以如果你对纽约有什么推荐，我非常乐意接受，也很喜欢到处旅游。我的爱好听起来之所以这么普通，是因为我把大部分时间都花在捣鼓构建东西和钻研技术上了，代价就是牺牲了个人时间。所以这就是为什么你看到的爱好清单会是这样。接下来交给……

<details><summary>Original English</summary>

We are Franchesco Filipe. A little bit of a quick introduction about me. I'm originally from Venezuela. I lived in the UK for about seven years and recently moved to Madrid. H I work at data and I work at a bank as well with Felipe. Erh. I like just finding the best eeries in any city that I visit. So if you have any recommendations for New York, I'm more than happy to take them and just travel around. And the reason my hobbies sound so vanilla is because I just spend most of my time building stuff and nerding out at the expense of my personal time. So that's how you end up with a list like that. Uh and then
</details>

>> 太棒了。好的。很高兴见到大家。我也做个快速介绍。我是 Filipe，巴西人。我也搬到了英国，至今已经一年半了。这是一段有趣的历程，生活可以说是发生了翻天覆地的变化。不过，能够在那里生活感觉很好。我常讲一个故事：在决定大学是否要从事这行之前，我曾经每天雷打不动地练大约七个小时的钢琴。之后顺理成章的决定就是去学电气工程，因为谁不想呢，对吧？后来某个时候我进入了数据领域，因为当时有人向我展示了一个叫 Google Data Studio 的东西。现在它叫 Looker Studio，不过现在他们又改回去了，我都搞不清楚到底是怎么回事了。我当时做的第一个仪表盘看起来就像一卷古埃及纸草书一样竖长，你必须不断往下滚屏滚屏滚屏滚屏才能看到内容。不过，剩下的就都成了历史。我在很多初创公司、小团队和 Scaleup 工作过。后来去了一家大公司 Nubank，可能你们有些人听说过。之后回到了 Monzo，我认为它是介于 Scaleup 和大型成熟企业之间的规模，但目前增长非常迅速。

<details><summary>Original English</summary>

>> nice. All right. Um happy to meet everyone. Um also quick intro. I'm Philipe. I'm originally Brazilian. Um, I also moved to the UK. It's been a year and a half now. So, it's been a fun journey. Um, life turned pretty much upside down. But, yeah, it's good to be it's good to be there. Um, I like to tell a story that before going to to decide whether I wanted to do it in university, I used to play piano for like literally seven hours a day. Um, and the natural decision there was to then study electrical engineering because who wouldn't, right? Um, I ended up at some point landing in in data because someone showed me something that at the time called uh Google Data Studio. Now it's Looker Studio, but now they went back. I don't I don't even know what's going on. Um, and then my first dashboard looked like a papyrus of how vertical it was. You had to scroll scroll scroll scroll scroll down to see something. Um, but yeah, the the rest is history. So I worked at a lot of um startups and small teams and scaleups. Um and then eventually went to a big company at New Bank. Maybe some of you do know um and then before going back to to Monzo which is I would say a middle turn between a scale up and a big enterprise company but it's growing uh so fast for now.
</details>

目前我的大部分时间都在 Monzo 工作，负责构建用于内部生产力的内部 AI 驱动解决方案，主要服务于数据团队。所以我们基本上是想通过借助 AI 构建工具，让我们的数据团队变得更优秀。当我不跟机器人和智能体打交道时，你大概可以在某些地方找到我攀岩，要么是在大自然中，要么是在室内岩馆。

<details><summary>Original English</summary>

Um and yeah most of my time currently has been working at Monzo with building internal AIdriven solutions for internal productivity primarily for the data team. So, we basically want to get our data team better by um building with AI. Um and yeah, when I'm not talking to robots and agents, uh you can probably find me climbing somewhere um either in nature or in a gym.
</details>

对于我们今天为什么给大家带来这个主题，有一些出发点。我认为 Francesco 和我都曾在金融服务业的数据团队工作过，也就是刚才提到的 Monzo、Nubank 以及该领域的其他几家公司。我们现在正在拓展 AI 在那里的能力边界。我们在 Monzo 的团队一直在从影响力的角度大力推动 AI 的落地应用。我们不想做无意义的“Token 消耗最大化”，如果不能带来具体的业务价值，我们不想投入大量资金。所以采用过程是非常非常审慎的，我们也在这方面看到了非常好的成果。

<details><summary>Original English</summary>

Um and some starting like points of why are we bringing this for you today? I think um both Franchesco and I worked in data teams in financial services. So again, Monzo, New Bank and a few other companies in the in the sector. Um, we're now pushing what AI can do there. Our team at Monzo has been um, working a lot with with adopting AI from an impact perspective. We don't want to be like token maxing. We don't want to be spending a lot of money if that doesn't bring us like concrete business value. Um, so the adoption is very very deliberate and we've been seeing very good results on that.
</details>

另一方面，这也是我们一直在做的事情，特别是 Francesco，一直在运用 AI 让我们的生活更轻松。同样，不是通过“我搭建一个开源客户端实例——我对此没有任何意见——然后直接让它连接所有东西”这种方式，而是切实去思考：在我的生活中，我关心的到底是什么？我可以通过 AI 的帮助把哪些事情变得更轻松？这就是为什么我们说在这个示例中我们并不代表 Monzo，因为我们会运用从 Monzo 带来的知识，但会与大家一起构建一个可以在实践中切实验证的示例，而无需过多讨论领域专业知识。如果你对我们在 Monzo 构建的东西感到好奇，我们明天有一场分组讨论会，届时我们将讨论 AgentShip，这是我们内部构建的远程智能体能力。接下来交回给 Francesco。

<details><summary>Original English</summary>

And on the flip side, this is something also something we've been we've been doing, Franchesco particularly is applying AI to make our lives easier. Um and again not through the approach of I'm going to set up an open client instance nothing against it um and just give it connections to everything but actually what are the things that I care about in my life that I can um get the help of AI to to u make easier. So this is why we say we're not representing Monzo um in this example because we're going to use the knowledge we bring from Monzo but uh build with you an example where we can um actually see that in practice without having to discuss a lot of domain knowledge. Um but if you are curious about the things we are building at Monzo we have a breakout session tomorrow um where we're going to talk about agent chip which is our inhouse remote agent capability. Um so with that Franchesco back to you.
</details>

### 核心目标：构建信任

>> 很好。提醒大家一下，今天的目标是信任。这可能看起来有点反直觉，因为这感觉非常务虚，而这又是一个工作坊，大家本应该埋头狂写两个小时的代码。但你会发现，我们会换一种思路。因为我认为我们已经过了那种必须花几个小时在键盘上苦敲才能得到值得信任的东西的阶段了。那么，让我们从领域开始。金融是高度定制化的。

<details><summary>Original English</summary>

>> Cool. So, as a reminder, today the goal is trust and it may seem a little bit counterintuitive because it feels very wishy-washy and this is a workshop and you're supposed to be coding really hard for two hours. H but you're going to see we're going to give it a little bit of a spin. Uh because I think we're past the point of having to spend hours like grinding through your keyboard uh to get something that you can trust. So, let's start with the domain. Finance is tailored.
</details>

你有你的数据，你有你的策略。有时候你其实并没有真正的策略。此外还有你对金融、对个人财务状况等所具备的知识，或者通常存在的误解。当我们谈论财务分析师时，有一个非常具体的工作职责描述。我们对这个工作描述放得稍微宽泛了一些。从为投资机构、投资公司、银行等进行研究，一直涵盖到个人使用场景。但金融就是金融，对吧？所以眼下，在产出成果、掌控财务、进行分析方面的瓶颈其实并不在于速度。我敢肯定你们当中有些人后台可能正运行着 Claude 或 ChatGPT 等任务在处理一些事情。所以那并不是瓶颈。

<details><summary>Original English</summary>

You have your numbers. You have your strategy. Sometimes you don't really have a strategy. And there is the knowledge that you have on finance, on your personal situation and so on or generally misconceptions. H when we talk about a financial analyst, there is a very specific job description. We are being a little bit generous with that job description. So it's going all the way from doing research for investments, investment firms, banks and so on all the way to like personal use cases as well. But finance is finance, right? So right now the gap on producing something, getting hold of your finances, doing an analysis is not really speed. H I'm pretty sure some of you may have some background tasks running with like claude or chpt getting some stuff done. So that's not the bottleneck.
</details>

根据我们过去几个月的经验，我们认为现在的瓶颈在于它如何与我们建立连接。所以信任是我们不能想当然的东西，坦白说，正是因为我们具体在谈论钱。这是利害关系最高的话题之一。我们需要投入精力确保系统中建立了信任。坦率地说，如果钱对你来说利害关系还不够高，而你可以一次性搞定你的资金问题、预算、融资以及所有其他事情，那么工作坊结束后请来找我，我会向你推销一些投资点子，所以是的，请我们稍后再聊。

<details><summary>Original English</summary>

H we believe that based on the experience we had over the last few months, the bottleneck now is how it connects with us. Um so trust is the thing we cannot take for granted and transparently because we're talking about money specifically. Erh this is one of the highest stakes topics. uh we need to invest in making sure that there is trust built into the system and transparently if money is not high stakes enough for you and you can like oneshot your money problems your budgeting your financing everything else h find me after the workshop I will buy you in into some investment ideas so yeah let's chat later please
</details>

所以，一切的起点就是那个目标——赢得信任。这样你才能真正把枯燥繁重的工作委托给多个智能体、你的智能体集群（Swarms）、你的工厂（Factories）或者随便什么。但是你怎么信任所获得的结果呢？我准备随口提几个名词，因为老实说，它们都不是什么新鲜事物。大家可能已经在苦苦思索：好吧，建立信任靠的是配置 Traces，或者做 Loops，或者我们常说的任何其他关键词。单元测试已经老生常谈了，让智能体做规划，我们知道那很好；做评估（Evals）肯定也算，还有 Traces、可观测性、Loops 以及 Graphs。我可以一直列举大家认为可以用来开始构建信任的各种组件，但它们本质上只是组件。我们今天想要讨论的，实际上是关于如何达成那种信任的设计原则。

<details><summary>Original English</summary>

um so where everything starts is from the goal which is earning the trust So then you can truly delegate the boring work to multiple agents, your swarms, your factories, whatever. But how you do trust the results that you're getting. Erh, I'm going to namerop a few things because honestly none of them are new. You're probably already grinding thinking, well, you buy trust by h setting up traces or doing loops or any of the other keywords we have. So unit testing that gets old planning with your agent we know that that's good. Uh doing evals for sure traces and observability loops and graphs like I can keep naming components of how you think you can start building trust but they are basically components. H what we want to discuss today is actually the design principles on how to achieve that trust.
</details>

因此，构建一个真正适用于金钱事务的 Harness 需要极高的信任度。所以我们不会去讨论具体的技术，我们不会去给大家读某个特定产品的 Readme 文档，并且我们会默认大家了解目前为止列出的一些概念。主要是，这将是一场略有不同的工作坊，因为我们希望大家能切身感受到这些原则在现实中是如何运作的。

<details><summary>Original English</summary>

So building a hardness that actually works for money matters requires an in immense amount of trust. So we're not going to be discussing specific technologies. We're not going to read you the readme of a particular product. H and we will assume you know some of the concepts that have been listed so far. Um and mainly this is going to be a slightly different workshop because we want you to feel how the principles work in reality.
</details>

所以今天我们围绕一个非常简单的例子构建了一个 Harness，并且希望大家去试用它。但不要聚焦在“噢，如果我输入这个，得到的响应就会快得多，而且 UI 看起来很流畅”——剧透一下：并不会那样。但更重要的是，我们希望大家能感受一下：对一个基于非常特定的 Harness 所构建出来的智能体拥有信任感，究竟会是什么样的体验。所以再次说明，这只是一个非常简单的实现和一个示例。如果大家待会儿觉得这太偏顶层设计了，可以尽管吐槽我，我们晚点可以再讨论。关于信任——我之后可能会把能说“信任”这个词的次数都用光，直到自己抓狂——但我们认为你必须从基层一步步把它构建起来，对吧？所以你拥有一个共享领域，关于规划的整套机制，确保你和模型在用同一套术语对话。这听起来比实际操作要简单得多。接下来是一致性，我很确信在场的每个人都会有同感，但它是要做到

<details><summary>Original English</summary>

So we have built a hardness today around a very simple example and we want you to try it out but don't focus on oh if I type this then I get the response so much quicker and the UI is so slick. it spoiler it won't be h but more importantly we want you to feel how it may feel like having trust in an agent that has been built with a very specific hardness uh so again this is just one very simple implementation an example h you can roast me later if you think this is too top level but we can discuss that later so trust and I'm probably going to run out of times I can say trust without going insane but we think you need to build it from the ground up, right? So you have a shared domain, the whole thing about a plan, making sure that you and the model are talking in the same terms. And it sounds more trivial than it actually is. Then consistency, and pretty sure everyone in the room will be on the same page, but it's making
</details>

<!-- chunk 2/11 -->

确保数字来自正确的地方。因此，语言模型不会直接去处理大量的算术运算，而是会进行一些工具调用，会为我们编写一些脚本，尽力想出一种能让结果保持一致的方法。我们也需要证据，基本上就是把凭证拿出来看，对吧？你可以回溯并追踪这些决策以及导致这些决策的原因。问责制可能是一个很有争议的话题，也许是其中最抽象的一个，但归根结底，即使你运行着100个智能体，它们所做事情的结果，你仍然需要对其负责。所以这是我们在工作中非常认真对待的事情。我们认为这是一种思维方式的转变，当人们做出这种转变时，他们就开始构建能够与他们一同演进的系统，而不是随意扔问题进去并指望碰巧能成事的黑盒子。

<details><summary>Original English</summary>
sure that the numbers come from a correct place. So rather than a language model trying to process a lot of arithmetic, it will do some tool calling. It will write us some scripts. It will try to come up with a way that the results are consistent. We also want evidence where basically show the receipts, right? You can follow back and trace back the decisions and what led to them. Accountability is probably a very spicy one and maybe the mo most abstract of them, but ultimately even if you're running a 100 agents, the results of what they do, you're still accountable for them. So that's something we take very seriously at work. And we think it's a mindset shift that when people make it, they start building systems that evolve with them and not black boxes that they just throw problems at hoping that something sticks.
</details>

最后是验证。所以我们要确保存在一个独立的视角，另一个角度。呃，我想说，我大概一年会有三次觉得自己有了世界上最好的想法，结果菲利佩却跟我说：请别去实现那个，求你了求你了求你了。我……哎呀，稍等一下。我正好想就这一点补充一下，我认为有两点：第一点是，我们在这里有非常充裕的时间一起合作，所以，嗯，随着我们逐步建立这些原则，如果能从各位的经验中学习也会非常好。因此，如果这与你们做过的任何工作产生共鸣，或者特别是你们在与智能体协同工作时遇到的任何挑战，嗯，完全可以随时提出来，然后我们可以一起把它构建出来。嗯，只是再强调一下弗朗切斯科刚才说的话，我们并不是说这就是唯一的模式，你们不会看到我们走上大讲台说“忘掉你们知道的一切，这就是做这件事的方法”。这是一种模式，一种处理它的方式，呃，在很多用例中一直对我们很有效。我稍后会在Monzo分享几个例子，弗朗切斯科也有其他几个例子。嗯，不过确实，再次说明，并不存在能解决我们面临的每一个问题的万灵丹。另外，如果你觉得“信任其实被高估了，直接往一个问题上扔100个智能体，最终它就会解决”，也欢迎随时向我们提出质疑。我们很乐意听听成功的故事，但从重复、从经验以及在工作内外的大量不同用例来看，我们确实认为你需要构建一个系统，它能让你有信心确认事情正朝着正确的方向发展，而不仅仅是事情表面上看起来正确。

<details><summary>Original English</summary>
And finally, verification. So we want to make sure that there is a separate point of view, another perspective. Erh, I would say I'm guilty of thinking I have the best idea in the world probably like three times a year and then only to have Filipe tell me please don't implement that please please please and I I Oops one second and I would just compliment on on this bit that I think two things the first one is we have a very generous window here to to work together so um it will be very nice to learn from your folks's experience as well as we build through this principles so if this resonates with any work you've done or any particularly any challenges you've faced um when working with agents feel absolutely free to to raise that and then we can we can build it uh together um and just ding uh doubling down on something that Franchesco said this we're not saying this is the model you won't say us going to to the big stage and saying forget everything you know this is how to do it this is a model a way to approach it uh that has been working for us in a number of use cases. I'll share a few examples at Monzo later and Francisco has a few other examples as well. Um but yeah, again there's not a single silver bullet to to solve every single problem we face. And also fe feel free to challenge us if you think actually trust overrated. Just throw a 100 agents at a problem eventually will get solved. happy to hear the success stories but from repetition from experience and a lot of different use cases at work and outside we do think you need to build a system that gives you the confidence that things are going in the right direction and not just that things look correct
</details>

### 婚礼预算工作坊

所以，信任，皆大欢喜。嗯，说到信任，我是来坦白的：我对今天的工作坊怀有不可告人的动机。呃，所以这就立刻打破了你们的信任。是什么呢？还不到五分钟。你们来这里是为了帮我弗朗切斯科筹划我的婚礼。

<details><summary>Original English</summary>
so yeah trust happy days um speaking of trust I'm here to confess that I have an ulterior motive with today's workshop Uh so breaking your trust immediately. What is it? Less than five minutes.

You are here to help me Francesco to plan my wedding.
</details>

虽然没人特别兴奋，但你们会兴奋起来的。呃，具体来说只是为了算清关于支付婚礼费用的一些财务情况。嗯，而且因为这是一场大会，我想让它尽可能尴尬一点。所以举手示意一下，呃，谁办过婚礼？谁结过婚？

<details><summary>Original English</summary>
So nobody's super excited but you will get excited. Erh specifically just to figure out some some stuff around the finances of paying for a wedding. Um and because it's a conference I want to make it as screeny as possible. So show of hands. Uh, who has had a wedding? Who's gotten married?
</details>

好的，太棒了。宾客人数在50人以下的。

<details><summary>Original English</summary>
Okay, awesome. Number of guests under 50.
</details>

>> 对。好的。不，还是要举手。还是那种尴尬模式。好的，挺好。

<details><summary>Original English</summary>
>> Yeah. Okay. No, still show of hands. It's still like cringey mode. Okay, cool.
</details>

>> 大概100人。

<details><summary>Original English</summary>
>> About 100.
</details>

对。不错。

<details><summary>Original English</summary>
Yeah. Nice.
</details>

大概150人。

<details><summary>Original English</summary>
About 150.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 不错。

<details><summary>Original English</summary>
>> Nice.
</details>

200人。

<details><summary>Original English</summary>
200.
</details>

>> 更多。好的。

<details><summary>Original English</summary>
>> More. All right.
</details>

>> 对。是的。盛大的婚礼。不错。这大概会引起共鸣，但听起来它会是一个非常简单的计算，非常简单的过程，婚礼也会顺顺利利地进行。而对于结过婚的人来说，大概都知道实际情况并非如此。嗯，甚至连算清楚账目以及搞懂事情怎么会这么快变得这么昂贵，都绝非易事。这里稍微讲个故事，希望我的女朋友——未婚妻——看不到这个。但我们之前做了一些计算，她说：“不，对啊，但每顿晚餐的费用就这么多。”我说：“对，而且在此之上你还有另外两项可变成本。所以那根本不是最终的数字。”不管怎样，为这个做预算一直是个挑战，这还算说得轻了。我不建议大家去办，但你们懂的，我已经在车上了。呃，所以今天你们要么帮我筹备婚礼打无薪白工，要么你们也可以做自己的方案。呃，所以我们在一个代码仓库里放了一些东西，你们会获得访问权限。所以，如果你们想自选探索路线，那就那么做。不建议这么选，因为我确实需要帮助，但随便你怎么选。

<details><summary>Original English</summary>
>> Yeah. Yeah. Big wedding. Nice. This is probably going to resonate, but it sounds like it's going to be a very simple calculation, very simple process, and the wedding is going to go by nicely and smoothly. And for the people who got married, probably you know that is not the case. Um, and even running the calculations and figuring out how things got so expensive so quickly. It's not trivial. This is a little bit of storytelling and hopefully my girlfriend doesn't fiance doesn't see this. But we were doing some calculations and she was like, "No, yeah, but the cost per like dinner is this much." And I'm like, "Yeah, and you have another two variable costs on top of that. So that's not the number." And anyway, budgeting for this has been a challenge to underelling it a little bit. I wouldn't recommend doing it, but you know, I'm already on the train. Erh, so today you're going to give me a hand with the wedding unpaid labor or you can do your own plan. Uh, so we put a few things in a repo that you're going to get access to. So you if you want to pick your own adventure, do that. Wouldn't recommend because I do need help, but whatever you choose.
</details>

>> 所以我们会给大家几分钟时间，呃，让你们把它配置好。只需扫描二维码，或者访问我的仓库，里面会有一些关于如何配置的说明。

<details><summary>Original English</summary>
>> So we'll give you a few minutes uh for you to set this up. just either scan the QR code or go to my repo and there will be some instructions on how to set it up.
</details>

>> 我们当时没准备这个时刻的背景音乐，比如电梯音乐那种。

<details><summary>Original English</summary>
>> We did not plan a background music like an elevator music for this moment.
</details>

>> 对，如果大家在配置时遇到任何问题，请告诉我们。

<details><summary>Original English</summary>
>> Yeah, let us know if you have any any trouble setting up.
</details>

>> 另外，如果有人会唱歌，现在倒是个好时机来……

<details><summary>Original English</summary>
>> Also, if anyone sings, it would be a good time to
</details>

>> 现场卡拉OK。

<details><summary>Original English</summary>
>> karaoke live.
</details>

顺便说一句，你们现在还不需要执行任何东西。只要确保把仓库放到了你们偏好的，嗯，环境设置中，然后我们会引导大家完成整个执行过程。

<details><summary>Original English</summary>
By the way, you don't need to execute anything just yet. Just make sure you have the repo in your preferred um setup and then we'll guide you through the the execution.
</details>

太好了。呃，所以你们刚刚克隆了一个病毒。没有啦，开玩笑的。但里面有很多写好的代码。结构确实很合理。我们有一份关于今天工作坊如何开始的指南。呃，我们有这个示例，也是今天演讲中最重要的事情——也就是帮我筹划我的婚礼。呃，还有测试套件本身，也就是我们构建出来向你们展示如何应用这些原则的东西。最后，还有一个文件夹，凡是你构建的脱离我们当前内容的东西，都会存放在那里。所以，再次说明，这有点像是一次自选探索路线，呃，附加的风险是如果你卡住了，我们可能无法帮到你，但你可以……嗯，今天所做的一切，你都可以带回家，你可以查看你做了什么，哪些你喜欢，哪些你不喜欢。

<details><summary>Original English</summary>
Cool. Uh so you just cloned a virus. No, just kidding. But a lot of coded stuff in there. The structure does make sense. So we have a guide on how we start for today's workshop. H we have the example most important thing of the talk today. So helping me figure out my wedding. H also the harness itself the thing we build to show you how the principles are applied. And then finally there is a folder where everything you build that drifts away from what we're doing is going to get stored in. So again, it's a little bit of a pick your own adventure uh with the added risk that we may not be able to help you if you get stuck, but you can um and everything you do today, you can take it home and you can check what you did and what you like, what you didn't
</details>

>> 而且特别是，我本来想说，特别是测试套件本身，呼应我们刚才开的玩笑，比如这就是目前构建的程度。嗯，同样，我们在这里分享的原则，就是这里所构建的原则。我们昨天还在讨论，这感觉就像是，呃，我们向你们展示一张桌子来教你们如何做一张桌子，如果这讲得通的话。呃，但我们真的、真的相信，做这件事本身并不是难事。难的是知道我们希望如何着手处理这个问题。所以这就是为什么我们以这种方式把它呈现出来。但有时我们会打开它，看一下底层细节，嗯，只是为了向你们展示在我们应用的原则背后，嗯，究竟在发生着什么。

<details><summary>Original English</summary>
>> and particularly I was going to say particularly the harness itself talking to to the jokes we were just making about like this is as far as this was built. Um again the the principles we're sharing here the principles that are built here. We were discussing just yesterday is like uh this can feel like we are showing you a table to teach you how to build a table if that makes sense. Uh but we really do we really do believe that the again building is not the hard thing. The hard thing is knowing how we want to approach the problem. So that's why we're bringing it like this. But we're going to open the open the look under the hood a bit. um at times just to show you what's going on um behind the the principles we're applying
</details>

>> 而且就像菲利佩刚才说的那样，这感觉很像是说“嘿Claude，请帮我建一家价值100万美元的公司”。如果你不确切知道为了实现目标你所依循的原则以及你正在做出的决策是什么，无论你尝试多少次，你都很可能只是任凭自己受制于碰巧发生好事的那种随机性。所以我们想再次锚定这些原则，因为它们是层层累加的，而且我们认为这其中有一套相当符合逻辑的合理顺序。因此，首先是构建那个共享领域、计划模式，不管你想怎么称呼它；然后是建立一致性，确保任何能够运行或应当运行的东西都能可靠地运行；然后是拥有证据来支撑决策从何而来、输入的是什么信息、事物是否经过测试等等，并将这些置于核心地位；接着是问责制，你如何对机器正在做的事情保持足够好的把握？你不想完全进入黑盒模式，因为那样你的问责制就荡然无存了。而我相信，这间屋子里的很多人都经历过这种情况。

<details><summary>Original English</summary>
>> and pretty much like Filipe was saying it can feel akin to saying like hey Claude please build me a $1 million company if you don't know exactly what are the principles and the decisions you're making in order to make something happen doesn't matter how many times do you try you're likely going to be just leaving yourself up for the randomness of something good happening by accident. So we want to anchor the principles again because they build on top of each other and we think there is a nice sequence that kind of makes logical sense. So building that shared domain plan mode however you want to call it then setting up consistency making sure that whatever can run or should run reliably does. Then having the evidence to back up where the decisions are coming from, what information is coming through, if things are being tested and so on and putting that front and center. Then the accountability, how do you keep a good enough grasp of what the machine is doing? You don't want to go full blackbox mode because then your accountability is gone. And that has happened to many of us in this room, I'm sure.
</details>

但另一面也很不切实际，即“哦，对于你做的每一次修改，把diff发给我，我肯定会逐行审查它”。从没有人这么做过。呃，然后最后是验证。所以在数据和金融领域，呃，你往往需要有一个独立的参考点，一个可供比对的反事实基准。呃，而忽略等式中的这一部分，只会导致你凭着自己的偏见来行事。所以你的结果总是会出现偏差。这其中夹杂着一些短视。因此，这些原则只是试图把我们的精力引导到最有用的地方，以获得

<details><summary>Original English</summary>
But the other side is also not very realistic where oh for every change you make send me the diff. I'm going to review it line by line for sure. Nobody has done that ever. Uh and then finally verification. So in data and in finance erh you often need to have a separate point of reference a counterfactual that you can check against. H and ignoring that part of the equation just leads to you running things on your own biases. So your results are always going to be skewed. There's some short-sightedness that plays into that. So these principles are just to try to funnel our efforts into where is most useful to get
</details>

<!-- chunk 3/11 -->

### 现场演示与 Harness 原则

我们真正可以信赖的东西。

提前提醒一下，今天肯定会有东西出问题。直接叫我们过去就行，我们会尽量协助你们解决。另外，其中有些部分确实过度工程化了。今天这不是一节关于优秀 UI/UX 设计的课程。好的，所以这只是为了向你们展示它体验起来会是什么感觉，展示其中的潜力。我们绝不是在做一款正式产品。要是遇到问题，或者有点疑惑，尽管举手，我们会在房间里走动提供协助。

<details><summary>Original English</summary>something that we can actually trust. Um heads up again something will break today surely. Just call us to you. we will try to fix it with you. Uh some of it is also overengineered. This is not a session on good UI UX design. Okay. So this is just to show you how it could feel, show you the potential. Uh by no means we're building a product and yeah just raise your hand. Something's not working out. You're a little bit confused. Raise your hand and we're going to float around the room.</details>

你们可能想检查一下这是否能运行，试着运行那个命令。

<details><summary>Original English</summary>Um, so you may want to check if this works, try and run that command.</details>

对。我想到了这一步，如果有谁那里运行不顺畅，我们可以到处看看，给大家五分钟时间把这部分跑通。如果配置一切顺利，终端里显示成功，你应该就能看到 UI 界面打开了。

<details><summary>Original English</summary>Yeah. And I think at this point we can just go around if things are not working for anyone and give everyone five minutes to get going with this bit. You should see the UI opening if everything goes successful with the setup works success in the terminal as well.</details>

很好。那里的第二个命令会打开一个设计得非常好的 UI，供大家做一些操作。这里是我们准备展示给大家的示例，因为这有点层层包裹，就像洋葱或者食人魔一样。我们要给大家展示一个在示例用例上运行的 harness 样例。如果你们想运行底部的那个命令，会看到一个更加充实的示例。但如果你们只停留在运行第二个命令并使用 UI，我让你们用 UI 来看 harness 的表现可能会让人觉得有点怪。但这正是重点所在。重点是向你们展示它在现实世界中的真实感受和应有的感觉。需要我在这里停留片刻吗？

<details><summary>Original English</summary>Cool. And that second command there will open a very well-designed UI for you to do some stuff. Here is the example we're going to show you because this is kind of like layered, you know, like an onion or an ogre. H we're going to show you an example hardness being run on an example use case. Um, if you want to run that command at the bottom, you will see kind of like a more fleshed out example. But if you stay on the just running the second thing and just use the UI, h it may feel weird that I'm asking you to use an UI to see how a hardness behaves. But that's the point. The point is to show you how it feels in should feel in the real world. Um, should I leave it here for a moment?</details>

>> 我觉得可以。

<details><summary>Original English</summary>>> Yeah, I think so.</details>

>> 好的。键盘敲击声小了，我默认大家都已经输入完想输入的命令了。

<details><summary>Original English</summary>>> Yeah. Okay. Okay. I hear less typing. I'm going to assume you've typed whichever command you wanted to type.</details>

>> 那么我们来看 harness 的实际步骤和原则，共享领域是第一个。能举手示意一下，有谁打开了 UI 但还没有进行其他操作吗？

<details><summary>Original English</summary>>> So let's go through the actual steps and the principles of the hardness and the share domain is the first one. Can I see little show of hands of who opened the UI and hasn't done anything else with it.</details>

>> 好的，好的。简而言之，你们右手边有一个聊天窗口，基本上什么内容都没有。如果你们想跟着看一个财务担忧、某项想要做的分析的示例，那就是开始的地方，基本上我们要从想要实现的目标出发，尽力去给出一个解释。你们平时可能每天都在和各自的 agent 做同样的事，但请把重点放在认识到这一点上：你很可能无法与 agent 拥有相同的上下文。等等，我能前后翻一下以防万一吗？好的，演示。

<details><summary>Original English</summary>>> Cool, cool, cool, cool, cool. All right. So um long story short, you have a chat window on your uh right right hand side and it has nothing essentially. Uh if you want to follow through an example of a financial worry, some analysis you want to do and that's the place to start and basically we want to walk from the goal we want to achieve and just try our best to give an explanation. You're probably doing this daily with your agents anyway, but focus on understanding that you're likely not going to have the same context as the agent. Um, wait, can I go back and forward just in case? Okay. Yeah. Demo.</details>

我想解释一件事，我觉得大多数人没有意识到这个事实：模型所知道的，并不一定就是你心里所想的。所以，除非你非常有钱，有很多为你专门训练的模型，否则你对某些事物的定义很可能和大众群体的定义并不完全一样。如果你在查找某个术语，agent 或模型可能足够聪明，知道这属于哪个领域，但这并不一定就是你的本意。所以，与你的模型来回沟通确实会带来很大的不同。而如果你自己在尝试，harness 旨在鼓励你深入挖掘，挑战你的一些假设，问你一些你可能都不知道自己需要问的问题。如果你们想做的话，是的。

<details><summary>Original English</summary>Um, so I wanted to explain something and I think most people don't realize the fact that what the model knows is not necessarily what you think. So unless you're very rich and you have a lot of models trained for you, h you're like likely your definition of certain things are not going to be the exact as what the majority of the population defines. So if you're looking up for a certain term, the agent may the model may be smart enough to know well this sits in this space but it's not necessarily the thing that you meant. So going back and forth with your uh model really makes a difference. And the hardness is supposed to encourage you if you're trying it out yourself to dig deeper to challenge some of your assumptions to ask you questions you may not knew you needed to to ask yourself. So if you want to do Yeah.</details>

那我来做和大家一样的事情，但我会运行 harness 示例。让我先回到这里一下，确保所有东西都准备好了。有人完全跟不上，还是大家都还好？好的，也许你能帮他一下，

<details><summary>Original English</summary>So let me do the same thing that you folks are doing, but I'm going to do harness example. Let me go back here for a second. Just make sure I have everything Is anyone completely lost or are good? Okay, maybe could you give him a hand</details>

>> 趁着我运行所有内容。对于后来的人，我也会给你们二维码，所以如果有人掉队了，可以重新跟上。

<details><summary>Original English</summary>>> while I I I run everything. And for the folks that arrived later, I will give you the QR code as well for the so if anyone lost that you can you can pick it up again.</details>

好的，趁大家跟着操作的时候，我来展示两件事。当你运行婚礼示例时，应该看到的就是这个，对吧？稍后我们会解释这里到底是怎么回事。只是为了给大家展示一下，如果你选择走自己的方向，会看到类似这样空白的界面。然后你可以做的是，在 Francesa 演示婚礼示例的同时，你也可以提出一些想要使用 harness 来做的事情。比如，我不知道，规划自己的婚礼、规划一次旅行、规划公司或个人生活中的一项新投资，都没关系。任何与财务生活相关、我们可以应用相同原则的事情都可以。再次稍作提示，如果你们需要在这两者之间切换，比如婚礼示例或你自己的用例，在 my 和 var 文件夹里会有一个数据库，基本上就是存储这些内容的地方。你们直接把它删掉就行了。哎呀。然后用之前的命令再次打开 UI，就能看到那个示例了。

<details><summary>Original English</summary>Okay. Um let me show you two things while I while we we let you go with it. So this is what you should be seeing when you run with a wedding example, right? Um we're we're going to explain in a bit um what's going on here. If you are choosing just to show you as well, if you are choosing to uh pick your own pick your own direction, um you're going to see something like this where it's empty. And then what you can do is as Francesa is going to run through the wedding example, you can say something you want to to use a harness for as well. So things like I don't know plan your own wedding, plan a trip, um plan a new investment in your company or in your personal life, doesn't matter. Um anything that relates to financial the financial life that we can um implement the same principles. If you ever need uh again just opening the hood a bit. If you ever need to switch between one and another like the the wedding example or your own um you can just delete the in the my and var folder you're going to have a database that's basically what's storing this. So you can just delete it. Oops. And then once you open the the UI again with the previous command, you're going to get the example.</details>

>> 你想打开那个空白的吗？

<details><summary>Original English</summary>>> Do you want to open the clean one?</details>

>> 可以，没问题。

<details><summary>Original English</summary>>> Yes, I can. Sure.</details>

>> 好的。考虑到大家拿到的确实是一块空白画布，我们想稍微消除一些歧义。如果你打开婚礼示例，那是一个包含所有要素的完整演练示例。但假设这就是我们的起点，对吧？而我遇到了一个问题。你那里有听写功能吗？

<details><summary>Original English</summary>>> Yeah. So, appreciating that you're literally you're literally being given uh a blank canvas. We want to disambiguate a little bit. So, if you open the wedding example, that's a work through example that has all the elements. But let's say this is where we're starting, right? And I have a problem. Do you have a dictation thing there?</details>

>> 有的。

<details><summary>Original English</summary>>> Um, I do. Um,</details>

>> 好的。

<details><summary>Original English</summary>>> okay.</details>

>> 看看这个行不行。稍等一下。

<details><summary>Original English</summary>>> Let's see if this is working. Wait a second.</details>

### 输入需求与 Harness 的审问约束

基本上，在右手边的那个聊天窗口里，那是一个大家熟悉的界面，对吧？那么，针对任何具体的问题，你会如何向 AI agent 寻求帮助？就是从聊天开始。你带着一个问题开始，开始描述你想实现什么。所以如果让我来做，我会说：我有一场婚礼，需要付三笔款项。一笔是 6000 美元，另一笔金额未知，还有一笔是剩余的钱款。而且，我的一部分成本是固定的。我知道自己在 DJ 上要花多少钱，还有花在装饰上的钱，但我不知道会有多少人参加婚礼。这是我每顿晚餐、每个座位要付的金额。所以我甚至不知道该怎么去确保我能按时付款。按时付款，准时、按时。我先把第一段删掉。

<details><summary>Original English</summary>So, basically on that like chat window on the uh right hand side, you are it's a familiar interface, right? So, how would you go about getting some help from an AI agent for whatever specific problem? Just start with a chat. You start with a a problem and you start to describe what you want to achieve. So, if I were to do it, I'll say I have a wedding and I need to make three payments. One for $6,000, another one for an unknown amount, uh, and another one for the rest of the money. And also, uh, some of my costs are fixed. I know what I'm going to spend on a DJ and I don't know decorations, but I don't know how many people are going to attend the wedding. And that's the amount of money I'm going to pay per h per dinner per seat. So, I don't even know how to go about making sure that I can pay in time in time. On time, on time on time. Um, I'll say let me just cut the first bit.</details>

太好了。

如果你想针对自己真正关心的具体问题来运行，你可以从那里开始，而我目前做的只是和 agent 一起做规划。

如今大多数 harness 都带有一种能识别出你正在尝试为某个问题做规划的概念，它会尝试提出一个合理的设想，提出一组问题来提供更多的明确性。harness 本身决定了你会面临怎样的问题，以及在实现任何东西之前规划需要具备怎样的严谨度。它的理念在于不会立即进入顺从附和的模式，直接去实现你提出的任何极其不明确的疯狂想法，而是帮助你向下深钻，深挖它需要做些什么。这就是建立共享上下文的原则。

<details><summary>Original English</summary>Cool. So if you want to run it for a problem that you actually care a little bit more about uh you will start there and all I'm doing is planning with the agent. Most of the harnesses today come with some notion that triages that you're trying to plan for a problem and it will try to come up with a reasonable idea some set of questions to give some more clarity. The harness itself is what guides the sort of questions that you will get asked and the sort of rigor that the plan needs to have before implementing anything. The idea is that it doesn't go immediately into a yes man mode and just implements whatever crazy idea you came up with that is very unclear but that helps you drill down and dig into what it needs to do. So that's the principle of getting a shared context.</details>

>> 在你继续之前插一句。后排看这个字体大小可以吗？文本的大小。可以。好的，太好了。谢谢。

<details><summary>Original English</summary>>> Quick one before you you continue. Is the size okay for the back of the room? The size of the text. Yes. Okay. Cool. Thank you.</details>

好的。抱歉，因为这是现场的，我正在看屏幕。

好的，从我这里已有的信息来看。

好的，那我或许可以继续在这里补充澄清信息。我先跳过一些内容，但可以说像这样：我没有任何积蓄。

钱得自掏腰包。我妈妈可能会给我大约 5000。我知道参加婚礼的每人价格大概在 150 左右。

而我买花要付 500。我需要买我的西装。

我只是故意加了一堆复杂性并弄得很凌乱，因为 agent 的意义就在于，它不会放过你一开始没有提供信息、含糊其辞的事实。这整件事的核心在于，它确实是一个护栏，迫使你真正去过一遍它制定规划所必需的每一个数据点。我想接下来不管出来什么，我们直接构建，试着推进下去。

<details><summary>Original English</summary>Yeah. Sorry, I'm reading because this is like live. Okay. From the one I have. Okay. So maybe I can keep adding clarifying information here. And I'm going to skip ahead, but something like I have no savings. It will come from my pocket. My mom may give me like 5k. H I know the price per a person going to the wedding is around 150 and I'm paying 500 for the for the flowers. I need to buy my suit. I'm just adding a bunch of like complexity and being disorganized on purpose because the point of the agent is that it doesn't let go the fact that you're being vague um in not providing the information ahead of time. The whole point of this is that it's really guardrail for you to for to forcing yourself to actually go through um every single data point that it needs to come up with a plan. Erh, I think for the next one we just build whatever h comes up to try and move on.</details>

>> 提出方案。现在，

<details><summary>Original English</summary>>> Propose the plan. Now,</details>

>> 有人在跟着尝试吗

<details><summary>Original English</summary>>> is anyone trying it out</details>

<!-- chunk 4/11 -->

与你个人遇到的某个问题相关？
<details><summary>Original English</summary>
with a problem you have personally?
</details>

>> 是的。好的，太棒了。你想跟我们稍微讲讲它吗？
<details><summary>Original English</summary>
>> Yes. Okay, cool. Do you want to tell us a little bit about it?
</details>

>> 噢，合理，合理，合理。很好。好的。它在问很多问题，而我……
<details><summary>Original English</summary>
>> Oh, fair, fair, fair. Nice. Okay. It's asking a lot of questions and I'm
</details>

>> 不，我，我接受了那个方案。是的。
<details><summary>Original English</summary>
>> No, I I accepted the plan. Yeah.
</details>

>> 那么，你能回到预填好数据的示例吗？
<details><summary>Original English</summary>
>> So, can you go back to the seated example?
</details>

>> 是的，我可以。嗯，
<details><summary>Original English</summary>
>> Yes, I can. Um,
</details>

### 治理框架与领域上下文对齐

>> 为了省去你们很多来来回回的沟通，因为对你们所有人来说这并不是很高信号的内容。这里有几个要点。一个是具备那种自我意识，并迫使治理框架记住：你的领域知识和智能体所知道的内容不会是一样的。你要尽可能找到那种像文氏图重叠的部分。但这需要大量的来回沟通，而这往往是花费最多时间的地方。如果你设计了一个真正出色的治理框架，它会手把手地引导你制定出真正好的方案，把事情实现好，呃，并且知道哪些组件重要，哪些不重要。呃，如果你的治理框架基本上就是“好啊，对我说的每一句话都说行，然后尽你所能去实现它”，那你得到的结果就会很不稳定。所以，这就是预填好数据的示例。顶部那个方案已接受的提示，本质上意味着我已经经历了大体上 10 分钟左右的来回沟通。呃，智能体觉得自己对我的问题了解得足够多了，可以将其拆解为各个步骤。所以你们在那个图表中看到的，就是它视为决策树中各个决策点以实际作出决策的全部步骤。
<details><summary>Original English</summary>
>> so to save you a lot of the back and forth back and forth here because it's not very high signal for any of you. There's a couple of takeaways. One is having that self-awareness and forcing the hardness to remember that your domain knowledge and whatever the agent knows is not going to be the same. You want to find that kind of like vin diagram superposition as much as you can. H but it takes a lot of back and forth and that's often where most of the time is spent. If you design a really good harness, it will guide you by the hand on coming up with a really good plan, implementing things well, uh, and knowing what components are important and which ones aren't. Uh, if your harness is basically like, yeah, say yes to everything I say and do your best to implement it, then you're going to get variable results. So, this is the seated example. The plan accepted thing at the top means essentially that I already went through the back and forth for around 10 minutes or whatever. Uh and the agent feel it knows enough about my problem to break it down in steps. So what you have in the diagram over there is the all the steps that it considers as decision points in a decision tree if you may erh to actually make a decision.
</details>

如果我可以插一句的话，嗯，我觉得就像我们开头所说的那样，稍微看一下底层原理挺好的，只是为了给你们一个概念，你们当然也可以自己或者在你们首选的智能体的协助下探索这个。嗯，但当我们谈论 Franchesco 所描述的一切时，嗯，这也来自于我们在治理框架内部设定的指令，对吧？所以这里就是我们设定智能体执行访谈以及它最终必须达成什么结果的指令所在。所以这就是在治理框架之上构建的原则的具体物化体现，对吧？就像构建在治理框架内部一样。我是说如果你想回到界面上的话。
<details><summary>Original English</summary>
And if I if I may, um I think it's it's as we said in the beginning, it's nice to look under the hood a bit just to give you an idea and you can of course explore this by yourself or with your preferred agents help. Um but when we are when we're talking about everything that Franchesco is describing um this also comes from the instructions that we have inside the harness, right? So this is where we have the instructions of the agent performing the interview and what it must end up with. So this is the materialization of the principle built beyond the harness, right? Like built inside the harness. I mean if you want to go back to the to the UI.
</details>

希望随着我们在示例中的推进，这能开始变得更容易理解。不过我们增加了一些提升使用体验的细节：如果你想知道这个设计得如此精美的整个界面中的哪些元素对应于我们正在讨论的某条原则，你只需要悬停在底部，它就会被拆解开来。所以你们可以看到，当我们进行规划、规划共享领域上下文时，它制定出了一个方案，方案在右上方高亮显示；然后它给出了所有节点以及其他决策之间的连接，以及我们从这里开始需要界定哪些范围。那么我们继续往下讲吗？好的。还有人在用对话做规划吗？
<details><summary>Original English</summary>
So this is hopefully going to start making more sense as we as we progress in the example. But we added a couple of quality of life things where if you want to know what elements of this whole UI that is so beautifully designed uh make sense for whatever uh principle we're discussing. You just need to hover down at the bottom and it will be broken down. So you see when we did the planning the planning the sharing the domain context it came up with a plan is highlighted at the top on the right and then it came up with all the nodes and the connections in between the other decisions and what we need to start scoping from here. So should we move on? Yes. Is anyone still doing any planning with the chat?
</details>

>> 挺好。
<details><summary>Original English</summary>
>> Cool.
</details>

>> 好的。是的。所以，我们这里有几样东西。如果你想自己动手玩玩并细读这个治理框架，比如你可以进入界面上的第三步，比如左侧的小图表中。
<details><summary>Original English</summary>
>> Okay. Yeah. So, we had a few things here. If you wanted to uh play around and peruse the uh harness yourself, you could for instance go on the step three in the UI like in the little diagram on the left hand side.
</details>

>> 哎呀，抱歉。我正准备展示……
<details><summary>Original English</summary>
>> Oops, sorry. I was going to show
</details>

>> 标签页太多了。
<details><summary>Original English</summary>
>> too many tabs.
</details>

>> 你可以点击像第……不，
<details><summary>Original English</summary>
>> You could click on like step no
</details>

>> 里面的第三步。对。它会给你一点细分说明，告诉你信息来自哪里，为什么模型认为这是你需要做决定的节点，包括它是否根据你在与它规划期间所使用的语言做出了任何假设。举例来说，智能体，你说过这个吗？我可以用这个指一下……
<details><summary>Original English</summary>
>> step three in the Yeah. And it will give you a little bit of a breakdown of where the information came from where why the model thinks this is the node you need to make a decision of uh including if it's making any assumptions based on the language you were using during your planning with it. So for instance the agent did you say this I could point with this
</details>

>> 呃，如果你长按那个，是的。
<details><summary>Original English</summary>
>> uh if you press and hold that yeah
</details>

>> 太棒了。
<details><summary>Original English</summary>
>> awesome
</details>

>> 不是人工智能。
<details><summary>Original English</summary>
>> not AI
</details>

>> 所以在智能体汇总的方案中，有相当多由它提议的内容，因此你可以开始稍微剖析并理解，比如实际上这是来自于我，这是我认为我知道的事实，或者这是智能体根据我的语言推断出来的东西。如果你在同一个地方稍微向上滚动一点。是的。再上，再上，再上，再上，再上，在那里。是的，没错。呃，这里曾有一些来回沟通，因为我当时使用的语言比较含糊，而它做出了一种假设，即因为我在这里用了这个关键词，所以我指的是这个。再次说明，这是一个非常明显的例子，但你们可以通过点击来体验，四处看看。如果我们回到幻灯片展示，上面有一些注释，因为再次强调，这一切都是为了将原则扎根于某种让人觉得是为了建立信任而设计的东西中。所以上面有一些标记。再次说明，这虽然不是世界上最好的界面设计，但能让你知道事情是来自于你、来自于智能体，还是仍然是一个未决问题并且需要你做出决定，而且你可以看出方案是如何构建出来的。
<details><summary>Original English</summary>
>> so there's there's quite a few things in the plan uh that the agent put together that were proposed by it so you can start dissecting a little bit and understanding like actually this came from me this is a fact that I think I know or this is something the agent inferred based on my language. If you scroll up a little bit just on the same Yeah. more more more more more there. Yeah, sure. Uh here there was some back and forth because I was being vague with the language I was using and it made an assumption that because I was using this keyword here, I meant this. Again, this is a pretty obvious example, but you can play around with clicking through, seeing things around. If we go back to the presentation, there's some annotation because again, this is all about grounding the principles into something that feels like it was designed for building trust. So you have some notation. Again, not the best UI design in the world, but knowing if things came from you, from the agent, or is it still an open point and you need to make a decision on and you can tell how the plan has been built.
</details>

你还有另一件事可以尝试。你可以回到第二步，呃，如果我们在那里点击那个节点，其实可以告诉智能体。是的。而且你其实可以在拥有……抱歉，呃，你可以直接告诉智能体，比如“其实你对这一步做出的某些假设是不正确的”，然后再稍微进行一些来回沟通。呃，我还是要做一下举手表决，不过出于强化和参与感的考虑，呃，谁曾经历过超过十轮以上的对话环节——也就是来回拉锯至少十次——在某个时刻你说，“让我从头开始吧，这根本讲不通了，有些我们之前讨论过的内容完全找不到了”。谁经常有这种感觉？
<details><summary>Original English</summary>
You have another thing you can try. You can go back into step two uh and actually tell the agent if we click on the node there. Yeah. And you can actually tell the agent after you have sorry uh you can just tell the agent like well actually you're making some assumptions about this step that are not correct and then go a little bit back and forth. Erh, I will still do the show of hands thing, but because of reinforcement and engagement, uh, who has been in a chat session with over like well over 10 turns, so back and forth and back and forth at least 10 times where at some point you said, let let me start from the beginning like this is not making any sense. Some stuff we already discussed like it's well gone. Who has had that feeling on a regular basis?
</details>

是的。所以，这是我们当下所拥有的治理框架设计所导致的结果：它们被设计用于线性讨论，并将所有内容作为一个大型会话保存在上下文中。而我们这里的这种设计，其目的在于将其拆解开来，这样你就可以讨论单个元素，而不必把整体大局上的事情弄得更为复杂。
<details><summary>Original English</summary>
Yeah. So, that is a consequence of the design of the harnesses we have today where they're designed for a linear discussion and to keep everything in the context as one big conversation. Whereas here the way we designed it is supposed to break it down so you can discuss individual elements without necessarily making things you know more complicated in the grander scheme of things.
</details>

>> 对。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 一致性原则与确定性执行

>> 呃，太好了。所以我先让你们自己稍微操作体验一下，但我确实想再深入一点。因此我要介绍一致性原则。这是建立在共享领域的基础上的，因为你已经有了一个方案，而且智能体非常有能力去理解：你方案中的这些部分只是一段代码，或者只是一个电子表格的计算，比如它总是会给你一个一致的结果，这是你整个方案中的确定性元素。呃，基于此，你需要去实现代码。你需要去实现某些每次都能给你相同结果的东西。呃，做个类似的举手表决。有人尝试过在聊天对话中做预算编制或任何财务计算吗？结果怎么样？比如，你们对结果有把握吗？你……是的，有一点。
<details><summary>Original English</summary>
>> Erh cool. So I will let you play around with it a little bit but I do want to maybe go a little bit further. So I will introduce the consistency principle. And this build on the shared domain because you already have a plan and the agent is very capable to understand well these pieces of your plan are just a piece of code or just a calculation spreadsheet like it will always give you a consistent result is a deterministic element of your whole plan. Erh and based on that you need to implement code. You need to implement something that will give you the same result every time. Erh similar show of hands thing. Has anyone tried to do like budgeting or any financial calculation in the chat and how did that go? Like are you confident on the results? You Yeah, a little bit.
</details>

>> 采样温度可能……比如非常好，嗯，不太好。相当糟糕。
<details><summary>Original English</summary>
>> Temperature maybe like very well um not too well. pretty bad.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 那么，好吧。我很想知道是否有人愿意主动分享自己的经历，包括他们看到了什么，以及他们认为为什么会发生这种情况。不过对我来说，有好几次我认为自己提供了所有必要的信息。智能体返回给我一个公式。它甚至被排版成了公式的样式。你知道的，就是那种斜体公式的样子，看起来非常漂亮。我当时觉得它懂得自己在说什么。接着给出的结果却是……我又不是计算器，但我知道那个结果是错的。所以从一开始我就觉得算了，重头开始吧。嗯，有人还有其他类似的例子吗？
<details><summary>Original English</summary>
>> So, so all right. So, I would love to know if anyone wants to volunteer their story, but what they saw and why they think it happened. But to me, a couple of times I thought I was giving all the necessary information. The the agent gave me back a formula. It was even formatted as a formula. You know, the kind of like italics formula thing that looks really nice. I was like knows what he's talking about. And then the result was like I'm not a calculator and I know that result is wrong. So from the get-go I was like nah start from scratch. H anyone has any other like examples
</details>

>> 一致性，对吧？所以很多时候结果看起来不错、挺合理，但你把同样的内容再运行一次，就会出现某种变动。
<details><summary>Original English</summary>
>> consistency right? So a lot of times the results look good reasonable but you run the same thing again that's something.
</details>

>> 是的。所以这基本上就是该原则的灵感来源。抱歉，你想分享什么？
<details><summary>Original English</summary>
>> Yeah. So that's basically the inspiration on the principle. Sorry, what do you want to share?
</details>

>> 是的。所以这就说明了每次它都可能……
<details><summary>Original English</summary>
>> Yeah. So it goes to the point that every time it might
</details>

>> 是的。呃，而且那是一个非常棒的例子，用来说明为什么我们谈论的是构建一个治理框架，而不仅仅是将这些原则作为一套技能或指令插入到现有的治理框架中，例如 Codex、Claude Code 或其他任何东西。比如当我们用非确定性的方式来做这件事时——也就是给智能体一堆指令，上面说了正确的内容，但仍然依赖智能体“别犯错，请做正确的事”。嗯，这就是问题的关键所在。我们依赖于后台发生的很多事情，而且基本上……
<details><summary>Original English</summary>
>> Yeah. Uh and and that's a great a great um example to say part of the benefit why we are talking about building a harness and not just plugging these principles in a set of skills or instructions to an existing harness such as like codec, cloud code or anything else. Like when we when we do it the not the non-deterministic way, which is to give the agent a bunch of instructions that um say the right things, but still rely on the agent uh make no mistakes, please do the right thing. Um that's that's the point. We're relying on a bunch of things happening in the background and basically
</details>

<!-- chunk 5/11 -->

每次都会得到非确定性的结果。所以我觉得构建 harness 的价值——同样，这也稍微涉及底层机制，并且来自我们在 Monzo 所应用的原则——在于将非确定性与一些我们在相关时希望控制的确定性行为结合起来。

<details><summary>Original English</summary>
getting a nondeterministic result every time. So I think the value here from building the harness again this is looking a bit into the under the hood and like from principles we we applied at at Monzo as well is mixing the non-determinism with some deterministic behavior that we want to control um when when relevant
</details>

>> 我记得你提到过，对于这个演示，很多 harness 都是写好的，对吧？我理解这部分，对吧。对于生产环境，你在对话中进行计算，与你让模型在代码中为你编写计算代码，两者之间有什么区别？

<details><summary>Original English</summary>
>> I think you mentioned that for this demo a lot of this harness was quoted right I get this part right for production like what's the difference between you making calculations in in chat versus you asking the model to code up calculations for you in code.
</details>

>> 我有几个做预测的个人例子。你可以尝试自己亲手做预测，或者制作一个包含大量花哨计算的电子表格，你很可能会把一些事情做对并得到一个体面的预测。你也可以直接从一个可信的仓库获取一个库，里面已经把所有东西都内置好了。你还可以用更模块化的方式编写一些代码，经过良好的单元测试、端到端测试，应用我们知道该如何做的所有良好软件工程实践，以确保那段代码能够给你一个良好的结果。所以我觉得区别——噢，抱歉。区别有点在于：如果你完全任由智能体去决定如何实现事物、何时需要在代码中完成，而不是在旁边构建好某些东西，你就会面临相当大的失误率，就像碰运气一样。

<details><summary>Original English</summary>
>> So I have a couple of personal examples on doing forecast where you can try and do forecast yourself by hand or come up with a spreadsheet with a lot of fancy um calculations and you will likely get a few things right and get a decent forecast. You can also just get a library from a trusted uh repo and that has everything baked in. You can also write some code in a more modular fashion that is well unit tested, you're doing end to end testing, you're doing all the like good software um engineering practices that we know how to do to ensure that that piece of code is going to give you a good result. Um, so I think the different Oh, sorry. The difference lies a little bit on the fact that if you're just leaving it to the agent to decide how to implement things and when they need to do it in code versus when it like you should just build something on the side, you're going to have a little bit of a big miss ratio like hit or miss.
</details>

>> 对。对。我猜我想问的是，如果这是写好的，是不是意味着没有应用良好的工程实践？这部分我理解。你们有类似经过测试的产品吗？

<details><summary>Original English</summary>
>> Yeah. Yeah. I I guess what I'm asking is if this is why quoted no good engineering practices were applied. I get this part. Do you have like a product that that was tested?
</details>

>> 我们——我要再打个广告了。明天上午我们有一场分组讨论，会讲我们在 Monzo 构建的、应用了其中一些原则的内容。不过，是的，我认为当我们说 harness 是写好的时，背后的含义更多是指具体的实现细节，比如抽象、方法、实际代码；但无论如何，结合确定性与非确定性的原则是相同的，不知这样解释是否说得通。

<details><summary>Original English</summary>
>> We we I'm going to do the the uh ad again. Uh tomorrow we're going to have a breakout session in the morning where we're going to talk about uh what we build at Monzo that applies some of these principles. uh but yeah I think the what is behind when we say like the harness being voded I think it's more about the implementation detail of like abstractions methods the actual code uh but the principles of mixing the determinism and the non-determinism are the same regardless if that makes sense
</details>

>> 谢谢。

<details><summary>Original English</summary>
>> thank you
</details>

### 确定性计算与代码固化

>> 还有一件事，另一点表明这是一个值得考虑的好原则的迹象是：在过去大概一年左右的时间里，大多数智能体开始更积极地进行工具调用，并构建自己的工具，以更具确定性的方式来解决计算问题。

<details><summary>Original English</summary>
>> uh and another thing another thing that signals that this is a a good principle to consider on over the last what year or so most of the agents have started to do more aggressive tool calling and building their own tools to solve calculations in a more deterministic way
</details>

坦白讲，智能体确实越来越厉害了，对吧？所以我们大可以干等着，然后所有问题就都解决了。我对这种思维方式抱有的一个疑虑是，它会在运行中临时随手创建东西。是的，在某一时刻针对特定问题，你可能会得到正确的代码；但是也许到了第 100 次运行它的时候，它却凭空发明了一段原本不需要重新发明的全新代码。我可以分享的其他非工作相关例子也正是关于这个的：比如我每个月都有一个不说严格、但也算半严格的预算结算，我会把我对账单里的所有项目分类。

<details><summary>Original English</summary>
and honestly agents are just getting better right so we could just wait and then all the problems are solved the one challenge I have with that mindset is that h it will create stuff on the on the go like in flight so Yes, you may get the right code for the right problem at an at a point in time, but maybe the time number 100, you run it, turns out is inventing a new piece of code that didn't need to be reinvented. uh and other examples non-workrelated that I can share err are around like doing exactly that like I have a I don't want to say strict but semi-strict close of budget every month and I categorize everything in my statements
</details>

我让智能体去决定如何分类、如何做汇总以及退款和支出等所有事情，到了某个时间点我就觉得：不行不行不行，这必须得写成脚本。因为我每次得到的结果都略有不同，而且我花了越来越多的钱和时间去跟智能体掰扯，就为了让它给我想要的结果——那个它明明已经连续三次做对、但在第四次却搞错了的结果。所以我不想再多费口舌，但一定要确保我们运行这些计算：计算只写一次，然后在每次需要的时候直接运行。模型能够去选用这些工具，你只需要确保你的 harness 设定得非常严格，绝不会去直接做算术运算，或者试图仅通过解析 token 来解决这些问题。

<details><summary>Original English</summary>
I left it to the agent to decide how to implement things and how to do the categorization and how to do the aggregates and everything else and the refunds and expenses and at some point I was like no no no this needs to be a script because I'm gettinglight slightly different results every time and I'm spending more money more money and time uh wrangling with the agent to get it to give me the results that I wanted that it got right three times already but didn't get it right in the fourth erh so I don't want to repeat it again but make sure that we run the calculations you write the calculation once and then you run it every time you need it um and the model is able to pick the tools is you just need to make sure that your hardness makes it very strict that it's not going to do any arithmetic or try to solve these problems by just parsing tokens.
</details>

如果不确保你的计算以及所有确定性的东西都在代码中运行，会发生什么呢？它们就只存在于模型脑海的深处。一旦你开启新会话，它就消失了；每个新问题或新会话都会产生新代码，变得一团糟；同样的问题得到不同的答案，再次出现非确定性。你是在要求一台随机机器产生一致的输出，所以你大概率是得不到的。

<details><summary>Original English</summary>
Um so what can happen if you don't make sure that your calculations and everything that is deterministic runs in code they're in the thickest in the model's head. So it's gone once you start new session the new code for every new question and or new session and it becomes a mess and same question different answer non-determination again you're asking the stoastic machine to produce a consistent output so you're likely not going to get it. Um,
</details>

这里有一些具备固定计算方法的事物例子，对吧？我敢肯定，如果你去问 10 家不同的金融服务公司，他们做这些事情的方式可能会略有不同，但大体公式和总体思路是一样的。所以你完全可以导出一个库，只编写一次并进行更新，这些做法并不新鲜，它们都源自良好的软件实践。回到演示，如果我们直接看预填的示例——你能高亮一下这里吗？好的。

<details><summary>Original English</summary>
so here's some examples of things that have a way to be calculated, right? Like I'm sure if you ask 10 different financial services companies, they will have a slightly different way of doing these things, but the general formula, the general idea is the same. So you could realistically export a library, write it once, update it, and these things are not new. they saw from like software good practices. So demo again if we just want to go to the seated example h in the can you highlight this? Okay.
</details>

### Harness 的指引与验证流程

>> 同样，通过使用这个，你可以看到在你的决策过程中，有些节点需要被实现为代码。我认为最简单的检查方法之一就是：如果它是一项计算，大概率就必须以代码形式来实现，对吧？同时还要有测试、单元测试、基准样例等。在构建像这样的 harness 时，你应该通过确保你所关心的实现信息呈现在你面前，来与你的智能体建立信任。另一个在实际情况中的例子是为你提供代码版本。你的代码通常会有版本控制。如果代码版本发生任何变化，而你正试图运行同一个流程，智能体应该能够捕捉到该情况并将信息反馈给你，提示说：实际上这处代码变动了，即使函数名称相同，你可能也不应该完全信任这里的输出，因为无论什么计算现在都变了。

<details><summary>Original English</summary>
>> So again just using this h you can see how the nodes in your decision making process um some of them needed to be implemented as code and I think the one of the easiest way to check is if it's a calculation likely it has to be implemented as code right uh as well as some testing unit testing golden examples etc. the you should build trust with your agent when you're building a harness like this by making sure that the information you care about about its implementation it's in front of you. Another example of how this has looked in the wild is giving you versions of the code. Your your code is more likely versioned. If anything change with the version of the code and you're trying to run the same process, the agent should be able to pick it up and surface that information to you and say actually this code change you probably even though the function is the same you probably shouldn't trust uh what's coming out of this because the whatever calculation h is different now.
</details>

所以当你在使用 harness 并接受了方案后，就会生成一个像这样的完整图表，顶部会提示你：“需要我来构建代码吗？”它会为你完成这一切。再次说明，这全都是受指引的。这就是 harness 的意义所在：它提供引导。有人在按照自己的方案构建具体步骤吗？

<details><summary>Original English</summary>
So as you're working with the with the harness and you accepted the plan, you have a nice graph like this being built, you will get something at the top saying, do you want me to build the code? H and it will do it for you. And again, it's all guided. That's the point of a hardness that it guides things. Erh, is anyone building any of the steps on their plan?
</details>

>> 这样可以吗？

<details><summary>Original English</summary>
>> Is that okay?
</details>

>> 可以。可以。挺好。

<details><summary>Original English</summary>
>> Yeah. Yeah. Cool.
</details>

>> 我切换去关注那个了。

<details><summary>Original English</summary>
>> I switch to focus.
</details>

>> 好的。行。[笑声]

<details><summary>Original English</summary>
>> Okay. Yeah. [laughter]
</details>

>> 合情合理。

<details><summary>Original English</summary>
>> Fair enough.
</details>

>> 合理。合理。

<details><summary>Original English</summary>
>> Fair. Fair.
</details>

>> 好的。如果你正跟着看婚礼示例，你可以尝试几项操作。点击第一步，然后点击代码，接着点击测试并立即运行测试。测试在这里。

<details><summary>Original English</summary>
>> Cool. So if you're following on the wedding example, you can try a few things. Click on step one, then code, and then the test and run the tests now. Tests here.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 95。

<details><summary>Original English</summary>
>> 95.
</details>

>> 抱歉，现在几点了？

<details><summary>Original English</summary>
>> Sorry, what time is it?
</details>

>> 9点54分。[笑声] 好，很好。不过是的，这里的原则——再回到把所有东西串联起来的思路——你不应该指望自己每次都记得去运行测试，也不应该指望自己每次都记得“嘿，这听起来像是我可以写点代码来一劳永逸解决的问题”。智能体应当在这整个过程中引导你。这就是我们在构建这个东西时融入的原则之一。另外顺便提一句，我想我们之前提过，代码仓库里还有一个名为 build yours 之类的小补充文件。

<details><summary>Original English</summary>
>> 9:54. [laughter] Okay, good. Um, but yeah, the the the principle here and just going back to try and tie everything up together, you shouldn't rely on you remembering to run the test. You shouldn't rely on you remembering that, hey, this this sounds like I can h create some code to solve it every time. The agent should guide you through it. And that's one of the principles we baked into building this. Uh, as an aside, I think we were telling you, uh, there's a little extra file in the repo that says build yours or something.
</details>

>> 它基本上按顺序融入了所有原则，并且会指导你构建一个[哧哼声]类似的 harness。

<details><summary>Original English</summary>
>> Um, it essentially has all the principles baked in in order and it will guide you on building a [snorts] similar hardness.
</details>

>> 叫 built your own。

<details><summary>Original English</summary>
>> It's built your own.
</details>

>> 没错。

<details><summary>Original English</summary>
>> There you go.
</details>

>> 是的。所以它会指导你构建一个体验与我们向你展示的 harness 相似的东西，该 harness 优先考虑建立信任的机制，而不是仅仅提供看起来正确的东西。所以你可以试一下。测试应该通过了。[哧哼声] 你会注意到这里没有任何类似思考、细阅等智能体在加载内容时常用的动词。是的，因为这些只是需要在你的环境中运行的测试。不要过度设计它。虽然由我来说这话有点滑稽，但只要让你的 harness 的所有组件按其应有的方式协同工作，而不是建立在智能体把事物串联在一起的臆想、憧憬和魔术胶水之上，事情就会容易得多。

<details><summary>Original English</summary>
>> Yeah. So yeah, it will guide you on building something that feels similar to the harness we're showing you that prioritizes trust building mechanisms over just giving you something that looks correct. So you can try this. The [snorts] test should be passing. You will notice that there was no thinking, perusing, all the verbs that agents put when they're loading something. Yeah. because these are just tests that need to run in your environment. Don't overengineer it. Funny that I'm saying that, but it's easier if all the components of your harness just work together as they should and not based on like hopes and dreams and magic glue from an agent orchestrating things together.
</details>

>> 我看我们刚才有个提问。所以如果我们——是的，我的意思是我们可以那样做，但我更倾向于不做纯朗读环节。基本上，这一切都关乎弄清楚你真正在意的是什么，以及一个功能完备的系统的功能需求是什么……

<details><summary>Original English</summary>
>> I think we had a question. Erh, so if we Yeah, I mean we can do that, but I'd rather not do a reading session. Basically, it it all goes about h figuring out what you actually care about and what are the functional requirements for a functioning
</details>

<!-- chunk 6/11 -->

harness。我在对话中有意穿插了一些这方面的内容。同样，因为知识产权的原因，我得稍微注意避免透露过多细节。不过，在构建组成 harness 行为的各个部件时，你需要确保每个步骤的目标都有明确的意图。最初几个组件之一的意图，就是尽可能多地收集信息，从而制定出一个计划。这一点也写在里面了。所以这基本上就是针对说明的说明，就像宜家的组装指南一样。它的作用是以非常清晰的方式指导你，告诉你“这些是你应该关注的事情”，但随后你可以根据自己的偏好来选择具体如何实现它们。

<details><summary>Original English</summary>
harness.
H
 I'm
 sprinkling
 some
 of
 that
 through
the
 conversation.
 Again,
 need
 to
 avoid
oversharing
 a
 little
 bit
 because
 of
 IP.
Uh
 but
 you
 want
 to
 make
 sure
 that
 the
objectives
 of
 each
 of
 the
 steps
 when
you're
 building
 the
 parts
 that
 will
 make
up
 the
 behavior
 of
 your
 hardness
 have
 an
intent.
 The
 intent
 of
 one
 of
 the
 first
components
 is
 gathering
 as
 much
information
 as
 possible
 to
 come
 up
 with
a
 plan.
 And
 that
 is
 written
 in
 here
 as
well.
 So
 this
 is
 basically
 instructions
for
 instructions.
 It's
 the
 IKEA
 guide.
Um
 it
 is
 supposed
 to
 guide
 you
 very
nicely
 on
 these
 are
 the
 things
 you
should
 care
 about
 but
 but
 then
 you
 can
pick
 uh
 your
 preference
 on
 how
 they
 get
implemented.
</details>

>> 提问：那么这和比如规范驱动开发（spec-driven development）有什么区别呢？规范驱动开发可能也是类似这样线性的，从你的所有问题开始，从想法一直贯穿到最后。这个和那个有什么不同？

<details><summary>Original English</summary>
>> Question.
 So
 how
 is
 this
 different
 from
let's
 say
 the
 specdriven
 development
expected
 something
 like
 that
 which
 is
also
 linear
 from
 starting
 from
 all
 the
questions
 from
 you
 starting
 from
 idea
all
 the
 way
 to
 the
 end
 and
 how
 is
 it
different
 to
 this
 one
 is
 different
 to
that
</details>

>> 你介意我来回答这个问题吗？我想提我认为相关的两点。第一点是，当我们为某种特定用例构建 harness 时，它与编程助手领域的智能体有些许不同。因为对于编程助手来说，代码通常只是达到目的的手段，对吧？我们构建的是执行某种动作的东西，它是一个产品，是一个应用，无论具体是什么。而在这种情况下，智能体是在协助我们进行分析、解决问题，并引导我们完成整个过程。因此，对于这件事来说，一份庞大的规范——比如就拿 Francesco 的婚礼来说，事情是会改变的，它会不断演化、改变。如果我们退回到那份不断变动的规范，我们其实又在依赖智能体在解释上的非确定性，寄希望于它能极其稳健并做出正确的行动。因此，harness 实质上是将原本完整的规范拆解成带有明确立场的各个章节，如果这能讲得通的话。

<details><summary>Original English</summary>
>> do
 you
 mind
 if
 I
 come
 to
 that
 um
 I
 I
want
 to
 mention
 two
 things
 that
 I
 think
are
 are
 relevant
 here
 um
 I
 think
 the
first
 one
 is
 when
 we're
 building
 a
harness
 for
 a
 specific
 type
 of
 use
 case
it's
 a
 bit
 different
 from
 the
 coding
assistant
 world
 of
 agents
 because
 with
the
 coding
 assistance
 we
 usually
 the
code
 is
 a
 means
 to
 an
 end
 right
 like
 we
we're
 building
 something
 that
 performs
an
 action.
 It's
 a
 product,
 is
 a
 an
 app,
whatever
 that
 is.
 Um,
 in
 this
 case,
 the
agent
 is
 helping
 us
 like
 analyze,
 solve
a
 problem,
 and
 work
 us
 through
 that.
 So,
the
 the
 gigantic
 spec
 for
 this
 like
let's
 say
 for
 Franchesco's
 wedding,
things
 will
 change
 like
 it
 will
 evolve,
it
 will
 change.
 And
 then
 if
 we
 go
 back
to
 the
 everchanging
 spec,
 we
 are
 relying
again
 on
 the
 determin
 on
 the
non-determinism
 of
 the
 agent
 to
interpret
 that
 that
 can
 be
 very
 very
very
 um
 robust
 and
 perform
 this
 the
 the
correct
 thing.
 So
 the
 harness
essentially
 breaks
 down
 what
 would
 be
the
 spec
 in
 opinionated
 sections
 if
 that
makes
 sense.
</details>

第二点作为补充，其实是我想结合我们在数据方面的经验来谈谈。我不知道你们当中有多少人从事数据工程、分析或类似的工作。是的。我认为我们从这个领域以及这些原则中带过来的另一件事，就是指标定义和维度定义总是在改变的概念。根据我们的经验——我们经历过很多很多次，我相信你们很多人也一样——经历过这样的对话：“这个数字准确吗？”“我不知道。听起来是对的，但我们永远无法确定。”如果永远无法确定，那这个数字到底对不对？我认为这也是从这个视角出发的：达到我们信任智能体就像信任仪表盘、指标或可视化图表一样的程度。我们与它达成了认知一致，而 harness 可以持续引导我们，让这种一致性随着时间的推移保持真实。但是前提假设会改变，源数据会改变，上下文也会改变。让 harness 具备适应这种变化的能力，就等于承认了这种变化是必然发生的，而不是每次都要重新给出 prompt 并回到流程起点。这样讲明白了吗？

<details><summary>Original English</summary>
Um
 and
 I
 think
 the
 second
thing
 to
 complement
 with
 that
 and
 is
actually
 something
 I
 wanted
 to
 to
 like
ground
 on
 our
 experience
 from
 data.
 I
don't
 know
 how
 many
 of
 you
 work
 in
 data
engineering
 analytics
 or
 anything
 like
that.
 Yeah.
 I
 think
 something
 else
 that
we
 bring
 from
 this
 word
 in
 these
principles
 is
 the
 idea
 that
 um
 metric
definitions
 and
 dimension
 definitions
always
 change.
 like
 in
 our
 experience
we've
 like
 [snorts]
 had
 many
 many many
times
 and
 I'm
 sure
 many
 of
 you
 as
 well
um
 that
 conversation
 were
 is
 this
 number
correct?
 I
 don't
 know.
 It
 sounds
 like
 it
is,
 but
 we're
 never
 sure
 and
 then
 if
we're
 never
 sure,
 is
 the
 number
 correct?
Um,
 I
 think
 this
 is
 also
 coming
 from
that
 perspective
 is
 that
 to
 the
 point
where
 we
 trust
 the
 agent
 as
 well
 as
 we
trust
 a
 dashboard
 or
 a
 metric
 or
 a
visualization.
 Um,
 we've
 reached
alignment
 with
 it
 and
 the
 harness
 can
continue
 guiding
 us
 into
 that
 alignment
continuing
 to
 be
 true
 over
 time.
 But
premises
 will
 change,
 source
 data
 will
change,
 context
 will
 change.
 And
 then
having
 the
 harness
 able
 to
 adapt
 to
 that
is
 like
 recognizing
 that
 this
 change
will
 be
 a
 thing
 um
 rather
 than
 having
 to
every
 time
 pro
 prompt
 again
 and
 go
 back
to
 the
 process.
 Does
 that
 make
 sense?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 基于此我想追问一个问题。从这个角度来看，有什么补充吗？因为在大多数实际工作中，你都在开发某样东西，即使它会在不同的迭代中发生变化，你也是在开发某样东西。AI 智能体也可以成为这个流程的一部分……

<details><summary>Original English</summary>
>> Follow
 question
 on
 that.
 any
 complnt
this
 perspective
because
 most
 most
 workable
 thing
 you
 are
developing
 something
 even
 though
 it's
subject
 to
 change
 through
 different
iterations
 you
 are
 developing
 something
with
an
 AI
 agent
 can
 be
 part
 of
 this
 flow
 as
well
</details>

>> 完全可以利用这一点，用这个 harness 来做到……

<details><summary>Original English</summary>
>> absolutely
 use
 that
 this
 part
 this
harness
 to
 do
 that
 it
</details>

>> 当然可以，在底层实际上发生的也是这种情况。因此，当我们创建……如果你去底层查看我的文件夹，里面会保存着所有的东西。所以你可以把这看作是 harness 背后的规范。因此同样的原则完全适用，在面向编程智能体的规范驱动开发中通常就是这样使用的：你拥有一个作为所构建事物定义来源的实体。在这种情况下也是一样的。不同之处在于，我们是通过带有明确立方的具体工作流将其呈现出来，而不是表现为单一外观的文档，如果这样讲得通的话。

<details><summary>Original English</summary>
>> absolutely
 and
 this
 like
 under
 the
 hood
this
 is
 essentially
 what's
 happening
 as
well.
 So
 when
 we
 have
 when
 we're
creating
um
 the
if
 you
 if
 you
 look
 under
 the
 hood
 in
 the
my
 folder,
 you're
 going
 to
 have
everything
 that
 is
 saved.
 So
 you
 can
think
 of
 this
 as
 the
 spec
 that's
 behind
the
 harness.
 So
 absolutely
 like
 the
 same
principle
 applies
 here
 in
 the
 in
 the
specdriven
 development
 for
 again
 coding
agents
 is
 usually
 used.
 you
 have
something
 that
 is
 the
 source
 of
 um
definition
 for
 the
 thing
 being
 built.
 In
this
 case,
 it's
 the
 same
 thing.
 The
difference
 is
 that
 we
 surface
 that
through
 opinionated
 like
 uh
 workflows
rather
 than
 a
 single
 um
 looking
 document
if
 that
 makes
 sense.
</details>

好的，太棒了。这是你可以尝试的另一件事。你可以尝试去修改某项计算的运作方式，然后你很可能会遭到 harness 的抵制。再次重申，harness 的目的就是引导你并强制你做正确的事。而这些原则的存在，是为了帮助你每次都做出正确的决定。因此，如果你尝试去把乘法改成聚合计算，你或许能快速完成编辑并保存文件，成功破坏了分析逻辑；但是当你运行测试时，你实际上根本无法得出你原本想做的分析结论，因为 harness 会根据自身的定义和构建方式阻止你继续下去。

<details><summary>Original English</summary>
All
 right,
 cool.
 So,
that's
 another
 thing
 you
 can
 try
 out.
 um
you
 can
 try
 and
 change
 how
 a
 calculation
works.
 Uh
 and
 you're
 likely
 going
 to
 get
some
 push
 back
 from
 the
 harness.
 Just
 to
reiterate,
 the
 point
 of
 the
 harness
 is
to
 guide
 you
 and
 force
 you
 to
 do
 the
right
 thing.
 And
 the
 principles
 are
 here
to
 help
 you
 make
 the
 right
 decision
every
 time.
 So
 again
 if
 you
 go
 try
 and
change
 uh
 multiplication
 for
 a
 an
aggregation
 you
 may
 just
 go
 make
 the
quick
 edit
 save
 the
 file
 success
 you
sabot
 attach
 the
 analysis
 but
 when
 you
run
 the
 test
 you
 won't
 be
 able
 to
actually
 reach
 any
 conclusion
 of
 the
analysis
 you
 wanted
 to
 do
 h
 because
 the
hardness
 is
 going
 to
 stop
 you
 by
 its
 own
like
 definitions
 and
 the
 way
 it
 was
built.
 Um,
</details>

### 证据

我们应该继续讲证据吗？证据就是我之前说的凭据，拥有凭据并能够展示出：“对，这就是它的来源。这是正确的，原因在于形成了那种因果关系。”所以它建立在第二项原则之上，因为你不仅拥有经过测试的代码，还拥有其他一切，你便有了一条可以向后追溯的线索。因此，你有一种方法来证实你所做的决定，你拥有证据。在这一原则中这一点非常重要，因为原则是需要你去解读的东西，对吧？我不想留给你们一个非常模糊、带有雄心壮志的空话，比如“对啊，去找证据，这太棒了”，而是：关于证据，什么是你需要切实关注的？

<details><summary>Original English</summary>
should
 we
 move
 on
evidence?
Er,
 evidence
 is
 the
 whole
 thing
 I
 was
saying
 before
 about
 the
 receipts,
 having
the
 receipts
 and
 being
 able
 to
 show
 that
well,
 yeah,
 this
 is
 where
 this
 came
from.
 This
 is
 correct
 because
 of
 in
doing
 that
 causality
 relationship.
 So
 it
builds
 on
 the
 second
 principle
 as
 since
you
 have
 code
 that
 is
 tested
 as
 well
 as
everything
 else
 h
 you
 have
 a
 trail
 that
you
 can
 follow
 backwards.
 So
 you
 have
 a
way
 to
 substantiate
 the
 decisions
 you're
making
 and
 you
 have
 the
 evidence
and
 it's
 important
 in
 this
 principle
because
 a
 principle
 is
 something
 you
need
 to
 interpret
 right
 and
 I
 don't
 want
to
 leave
 you
 with
 a
 very
 vague
ambitional
 thing
 like
 oh
 yeah
 do
evidence
 it's
 awesome
 but
 what
 is
 what
about
 evidence
 is
 something
 that
 you
need
 to
 take
 care
 of
</details>

回到作为数据专业人员的身份，这是每周都会让我们吃苦头的事情。并非所有的信息都是一样的。如果你真的想呈现一份分析，或者你想为你所在的公司对潜在投资做一些财务分析，你必须展示你的数据是从何而来的，并且能够将你的决策归因于你所拥有的这套证据链。既然我们能够展示一切从何而来，那么就存在一些我们想要避免的错误，即把所有事情都当作既定事实。比如，“哦对，你提供给我的这个受邀人数是既定事实”——我不知道，回到我的婚礼的例子。结果是我未婚妻又多邀请了三个人，但没告诉我。现在我的整个模型全错了。我这是在试图把它简化为一个非常简单的例子，但我想你们能够想象，在某个地方出现了一个错误的前提假设，并且不知道它从何而来，这对任何财务分析来说都会是致命的。

<details><summary>Original English</summary>
going
 back
 to
 being
data
 professionals
 this
 is
 something
that
 bites
 us
 on
 a
 weekly
 basis.
 Erh,
not
 all
 information
 is
 the
 same.
 If
 you
really
 want
 to
 present
 a
 piece
 of
analysis
 or
 you
 went
 to
 do
 some
financial
 analysis
 on
 a
 potential
investment
 for
 your
 firm,
 you
 need
 to
show
 where
 your
 numbers
 came
 from
and
 be
 able
 to
 attribute
 your
 decision
to
 the
 body
 of
 evidence
 you
 had.
 Erh
 so
since
 we
 can
 show
 where
 everything
 came
from
 uh
 there's
 some
 mistakes
 we
 want
 to
avoid
 where
 everything
 is
 treated
 as
 a
fact.
 So
 oh
 yeah
 this
 number
 you
 gave
 me
for
 the
 number
 of
 um
 I
 don't
 know
 going
back
 to
 my
 wedding
 the
 number
 of
 people
invited
 is
 a
 fact.
 Turns
 out
 my
 fiance
invited
 three
 more
 people
 didn't
 tell
me.
 Now
 my
 whole
 model
 is
 wrong.
 uh
 and
I'm
 trying
 to
 reduce
 it
 to
 a
 very
 simple
example
 but
 I
 think
 you
 can
 imagine
 how
having
 a
 wrong
 assumption
 somewhere
 and
not
 knowing
 where
 it
 came
 from
 can
 be
fatal
 for
 any
 financial
 analysis.
</details>

比方说，在构建智能体的世界里，很容易去设想某件事，或者把某件事当作毛估的猜测。模型无法分辨什么是确凿的事实，什么是估算。因此，你需要通过 harness 的设计来强制规范这一点。另一个很容易让事情迅速分崩离析的例子是：想象一下，有一个数据人员、分析师之类的人来找你，说：“不，不，不。这是结果。相信我，我算过这些数字了。”你会信任这个作为……是的，我看到有人摇头表示不信。

<details><summary>Original English</summary>
Um
so
 let's
 say
 in
 the
 world
 of
 a
 gentic
building
 it's
 very
 easy
 to
 assume
something
 or
 treat
 something
 as
 a
gueststimate.
 erh
 the
 model
 can't
 tell
what
 is
 a
 hard
 truth
 and
 what
 is
 an
estimation.
 So
 you
 need
 to
 enforce
 that
through
 the
 design
 of
 your
 hardness.
Erh,
 and
 another
 example
 where
 this
 kind
of
 like
 falls
 fall
 into
 pieces
 really
quickly
 is
 imagine
 you
 have
 a
 data
person,
 an
 analyst,
 something
 coming
 to
you
 and
 being
 like,
 "No,
 no,
 no.
 Here's
the
 result.
 Trust
 me,
 I
 run
 the
numbers."
 Do
 you
 trust
 that
 as
 a
 Yeah,
 I
see
 some
 like
 no.
</details>

我认为这里的任何人都不想去看单个数字背后的所有日志和数学计算。但是，只要有追踪路径去弄清楚“好的，我可以反向追溯这个决定”，就能相当大地增加我们人类的信心。所以我们这里有一些不同的例子：聊天中非结构化的想法需要被标记为解读；智能体的推理或从记忆中提取信息需要被视为假设；而如果我提交了一份银行对账单，那还有什么可讨论的呢？那是既定事实，那就是我花掉的金额，等等。

<details><summary>Original English</summary>
I
 don't
 think
 anyone
 here
 will
 want
 to
see
 all
 the
 logs
 and
 the
 math
 behind
 a
single
 number.
 But
 just
 having
 the
 trace
to
 figure
 out,
 okay,
 I
 can
 follow
 back
this
 decision
 increased
 increases
confidence
 for
 us
 humans
 quite
 a
 bit.
Erh,
 so
 we
 have
 some
 like
 different
examples
 here.
 Erh,
 unstructured
thoughts
 in
 a
 chat
 needs
 to
 be
 labeled
as
 an
 interpretation.
 the
 agent
reasoning
 or
 pulling
 information
 from
memory
 needs
 to
 be
 treated
 as
 an
assumption
 and
 then
 if
 I
 submit
 a
 bank
statement
 what
 is
 there
 to
 discuss
 like
that
 is
 a
 fact
 that's
 how
 much
 I
 spent
etc
</details>

如果我再回到数据从业人员的角度，数据标注以及确保拥有用于训练某种模型或运行任何流程的精选数据集是至关重要的。这基本上是同一件事：你只需要为你收集的证据赋予恰当的重要性级别，并确保尽可能多地去收集它。这是一件非常有趣的事，但证据同样会体现在代码中。因此，这不仅关乎“你从哪里得到这个数字”，还关乎“你是怎么得到这个……”

<details><summary>Original English</summary>
if
 I
 take
 like
 go
 back
 again
 to
 being
 a
data
 person
 data
 labeling
 and
 making
sure
 that
 you
 have
 a
 curated
data
 set
 for
 either
 training
 something
or
 running
 any
 process
 is
 paramount
 and
this
 is
 basically
 the
 same
 thing
 you
just
 need
 to
 assign
 the
 right
 level
 of
importance
 to
 the
 evidence
 you're
gathering
 and
 make
 sure
 that
 you
 gather
as
 much
 as
 as
 much
 of
 it
 as
 you
 can.
Um,
 this
 is
 a
 really
 funny
 one,
 but
evidence
 also
 goes
 into
 the
 code.
 So,
it's
 not
 just
 where
 do
 you
 get
 this
number
 from,
 but
 how
 did
 you
 get
 this
</details>

<!-- chunk 7/11 -->

数字？我曾遇到过这样一件事，有人当时正在使用母文件。每家公司都有一个母文件，在共享云端硬盘里被收藏之类的。那个人往里面输入了一些数字，一切看起来都很正常。母文件原本对哪些数值范围是合理的设定了一些预设假设。那个人并不知道，因为文件变过了。他们没做错任何事，只是不知道文件变了。呃，然后结果完全错了。用你的 harness 构建确定性代码时，同样的事情也会发生。如果你没有一种方式，甚至对自己代码中所做的更改也具备可追溯性，你就会在流程发生变动时让自己面临盲点。而输入是完全一样的。

<details><summary>Original English</summary>
number?

 And

 I

 had

 I

 have

 an

 anecdote





where

 someone

 was

 using

 the

 master

 file.





In

 every

 company

 there's

 a

 master

 file





and

 is

 favorited

 in

 the

 share

 drive

 and





whatever.

 And

 that

 person

 puts

 some





numbers

 in

 there

 and

 everything

 looked





fine.

 The

 master

 file

 had

 some





assumptions





of

 what

 range

 of

 values

 were

 reasonable.





That

 person

 didn't

 know

 because

 the

 file





changed.

 They

 didn't

 do

 anything

 wrong.





They

 just

 didn't

 know

 the

 file

 changed.





Uh

 and

 then

 the

 results

 were

 entirely





wrong.

 And

 the

 same

 will

 happen

 with





deterministic

 code

 you

 build

 with

 your





harness.

 If

 you

 don't

 have

 a

 way

 to





having

 a

 traceability

 even

 for

 changes





you

 make

 in

 your

 code,

 you're

 leaving





yourself

 uh

 vulnerable

 for

 blind

 spots





on

 the

 process

 change.

 The

 inputs

 were





the

 same.
</details>

呃，往后跳一点。如果我们顺着这个示例看，你能打开其中任何一个吗？

<details><summary>Original English</summary>
Erh

 skipping

 ahead

 a

 bit.





So

 if

 we're

 following

 from

 the

 example,





can

 you

 open

 any

 of

 them?
</details>

>> 能，

<details><summary>Original English</summary>
>> Yes,
</details>

>> 证据高亮显示了。呃，再说一次，通过这个示例，你可以直接点击底部，然后查看被高亮显示的部分，看到你关心的区域。但这正是信息流转的方式，以及哪些部分是由助手提议的，比如你可以拿出凭据，说明这到底出自哪里。看看行业中金融分析师的其他实现，你能获得细化到数据集的可追溯性，比如你知道是哪个连接器或哪个数据供应商为你提供了诸如苹果在当天这个时间点是这个价格的信息——如果你在做股票交易或投资相关的事情。所以这极其重要。我觉得我们不需要在这里花更多时间了，除非有人有疑问。

<details><summary>Original English</summary>
>> the

 evidence

 is

 highlighted.

 Erh,





and

 again,





you

 can

 see

 like

 the

 areas

 that

 you

 care





about

 through

 the

 example

 by

 just

 like





clicking

 on

 the

 bottom

 and

 then

 seeing





the

 bits

 that

 get

 highlighted.





But

 this

 is

 how

 the

 flow

 of

 information





goes

 through

 and

 what

 parts

 are

 proposed





by

 an

 assistant

 like

 you

 can

 show

 the





receipts

 of

 where

 where

 this

 came

 from.





Looking

 at

 other

 implementations

 of





financial

 analysts

 in

 the

 industry





you

 get

 traceability

 down

 to

 the

 data





set

 like

 you

 know

 which

 uh

 connector

 or





which

 supplier

 of

 data

 gave

 you

 the





information

 that

 whatever

 Apple

 had

 this





price

 at

 this

 point

 of

 the

 day.

 if





you're

 doing

 something

 about

 trading

 or





investing

 in

 stocks

 and

 shares.

 So,

 this





is

 extremely

 important.

 I

 don't

 think

 we





need

 to

 spend

 any

 more

 time

 here

 unless





anyone

 has

 any

 questions.
</details>

噢，很好。太棒了。

<details><summary>Original English</summary>
Oh,

 good.





Cool.
</details>

那么，这里有几件事你可以尝试。嗯，你可以给 agent 出一点小难题。直接在聊天框里打字，你就会看到那些证据行或者进入后续流程的某些输入是如何发生变化的，而且它能够追踪到这是源于你在聊天中纠正了某个事实。

<details><summary>Original English</summary>
So,

 here's

 a

 few

 things

 you

 can

 try.

 Um,





so

 you

 can

 add

 a

 little

 bit

 of

 a

 a





curveball

 to

 the

 agent.

 Just

 typing

 in





the

 chat

 and

 you

 will

 see

 how

 some

 of





those

 evidence

 lines

 or

 some

 of

 the





inputs

 that

 go

 into

 the

 rest

 of

 your





process

 change

 and

 it

 it's

 able

 to

 trace





that

 it

 came

 from

 you

 correcting

 some





fact

 in

 the

 chat.
</details>

另一个例子是，呃，如果你想进去做一项修改，并点击那个变动了的带下划线的数字。它应该能一路反向显示这到底来自哪里，以及为什么它对你后续的计算有影响。

<details><summary>Original English</summary>
And

 another

 example

 is

 erh

 if

 you

 want





to

 go

 and

 make

 a

 change

 and

 click

 on

 the





underlined

 figure

 that

 changed.

 It





should

 show

 you

 all

 the

 way

 back

 where





this

 came

 from

 and

 why

 it

 matters

 for





the

 rest

 of

 your

 calculation.
</details>

>> 我要说的话可能听起来有些重复。嗯，但再说一次，我们……这个 harness 是如何应用这些原则的一个示例。但我确信每个人都在思考自己的用例、自己的公司、正在构建的 agency、正在使用的 agency，以及如何把点连成线、如何把线路接通。我认为，当我们正在构建的 agent 的用户、客户在使用它时，我们可以思考这样一个例子。再说一次，他们对你的产品、对你的 agent 以及对输出结果所持有的信任，正是推动使用、采纳、改进等等的动力，而这又是通过我们提到的追踪演进等循环来实现的。所以同样，我认为底层的关键在于，当你构建 harness 时，务必确保你能让使用它的客户、用户体会到这一点，从而信任你的 agent 给出的结果。再次强调，可能有点啰嗦，但要确保我们一边推进一边把所有东西串联起来。

<details><summary>Original English</summary>
>> I'm

 going

 to

 say

 something

 that

 might





feel

 repetitive.

 Um

 but

 again

 we

 are

 we





are

 this

 this

 harness

 is

 an

 example

 of





how

 to

 apply

 the

 principles.

 But

 I

 I'm





sure

 everyone

 is

 thinking

 about

 your

 use





cases,

 your

 companies,

 the

 agency

 you're





building,

 the

 agency

 you're

 using,

 and





how

 like

 to

 to

 to

 connect

 the

 dots

 and





to

 to

 I

 don't know

 put

 the

 wires





together.

 I

 think

 this

 is

 an

 an

 example





we

 can

 think

 about

 when

 our

 users,

 our





customers

 of

 the

 agents

 that

 we're





building

 are

 using

 it.

 And

 again

 the





trust

 that

 they

 have

 in

 your

 product

 in





your

 agent

 and

 in

 the

 output

 is

 what





will

 drive

 usage

 adoption

 improvement





and

 so

 on

 through

 the

 loops

 that

 we





mentioned

 through

 tracing

 evolves

 and

 so





on.

 So

 again,

 I

 think

 um

 what's





underlying

 here

 is

 when

 you're

 building





a

 a

 harness,

 make

 sure

 that

 you

 can

 um





make

 this

 happen

 to

 uh

 your

 customers





that

 are

 using

 your

 users

 that

 are

 using





so

 that

 they

 trust

 the

 results

 that

 your





agent

 is

 giving

 them.

 Again,

 maybe





repetitive,

 but

 like

 making

 sure

 we

 uh





draw

 get

 everything

 together

 as

 we

 go.
</details>

在我们继续之前，有人能举个例子，说明哪次拥有证据链原本能帮你省去很多麻烦吗？我看到有人点头，像是痛苦的认同，但如果你有什么想分享的，非常乐意听听。否则我们就可以继续了。

<details><summary>Original English</summary>
Before





we

 move

 on,

 anyone

 has

 any

 example

 of

 a





time

 where

 having

 the

 evidence

 trail





would

 have

 saved

 you

 a

 lot

 of

 pain?





I

 see

 nodding

 like

 painful





acknowledgement,

 but

 if

 anything

 you





want

 to

 share,

 more

 than

 happy

 to

 to





hear

 you

 out.

 Otherwise,

 we

 can

 carry





on.
</details>

基本上每一次你想做什么事的时候都是这样。所以我在玩这个。我真的很喜欢能够拿出凭据等等的这个想法。那基本上就是我每次跟 agent 对话的场景，无论我是在写代码，还是在做幻灯片之类的。我会问：“这个数字打哪儿来的？”对方就说：“嗯，我们聊过这个等等等等。”我就觉得：“要是能直接向我具体展示比如那份文件就好了……”

<details><summary>Original English</summary>
basically

 every

 single

 time

 you

 try

 to





do

 something.

 And





so

 I'm

 playing

 with

 this.

 I

 really

 like





the

 idea

 of

 being

 able

 to

 show

 the





receipts

 and

 everything.

 That

's





basically

 every

 single

 conversation

 I





have

 with

 an

 agent,

 whether

 I'm

 coding





or

 like

 working

 on

 a

 deck

 or

 something.





I'm

 like,

 "Where

 did

 this

 number

 come





from?"

 Like,

 "Well,

 we

 talked

 about

 this





blah

 blah

 blah

 blah

 blah."

 I'm

 like,

 "It





would

 be

 nice

 if

 I

 could

 just

 be

 able

 to





show

 me

 specifically

 like

 the

 paper
</details>

我喜欢你用演示文稿当例子，因为我自己就有过这么一件事：我有足足一个月半左右的时间，想尽一切办法让自己不用去调整 Google Slides 里的文本框大小。所以我硬是折腾出了一套能帮我做幻灯片的东西。呃，我做了一个非常不错的 harness，它能深挖问题、调取所有相关文档，并帮我突出想要向团队展示的要点。结果在我的对话里，我始终没发现这样一个事实：当我要求做修改并给出一个例子时，模型会死死盯住那个例子不放，以至于把它塞到了我整份演示文稿的各处。我当时并没注意到。所以你可以想象，我当时正在向高管层展示某些生动的例子，他们问我：“你从哪儿弄来的那个数字和那个假设？”我当时说：“太离谱了，我不知道那是从哪儿来的，太离谱了。”但事实就是如此，这种事往往会发生。真的很让人恼火。那种后果层面的痕迹真的会严重损害你对自己的 harness 及其生成结果的信任。

<details><summary>Original English</summary>
I

 like

 the

 that

 you

 use

 a

 presentation





as

 an

 example





because

 I

 had

 an

 example

 myself

 where

 I





was

 trying

 as

 hard

 as

 I

 could

 to

 not





have

 to

 resize

 text

 boxes

 in

 Google





Slides

 for

 a

 good

 like

 month

 and

 a

 half.





So

 I

 was

 forcing

 my

 way

 into

 having





something

 that

 could

 help

 me

 build





slides.

 Erh,

 and

 I

 had

 a

 really

 nice





harness

 that

 would

 like

 dig

 into

 the





problem,

 get

 all

 the

 relevant

 documents





and

 help

 me

 highlight

 what

 are

 the

 key





points

 that

 I

 wanted

 to

 present

 to

 the





team.

 And

 turns

 out

 in

 my

 conversations,





I

 never

 caught

 the

 fact

 that

 when

 I

 ask





for

 a

 modification

 and

 give

 an

 example,





the

 model

 will

 fixate

 on

 the

 example

 so





hard

 that

 it

 will

 put

 it

 everywhere

 in





my

 presentation.

 I

 didn't

 pick

 it

 up.





So,

 you

 can

 imagine

 I

 was

 showing

 some





colorful

 example

 to

 senior

 leadership





and

 they

 were

 like,

 "Where

 did

 you

 get





that

 number

 and

 that

 assumption?"

 And

 I





was

 like,

 "That's

 crazy.

 I

 don't

 know





where

 that

 came

 from.

 That's

 crazy."

 But





yeah,

 it

 tends

 to

 happen.

 It's

 really





annoying.

 And

 that

 trace

 of

 consequence





can

 really

 hurt

 the

 trust

 that

 you

 have





in

 your

 harness

 and

 the

 results

 it





produces.
</details>

### 问责与把关机制

让我继续讲。另一个原则是关于问责（accountability）。呃，这是建立在证据基础之上的，因为你只有掌握了某些事实、有了某些参考点时才会做决策。呃，话虽如此，但我们身边都有那种对自己根本不懂的事情却说得极其自信的朋友。所以算是一个小小的反例。但总体而言，我认为如果说有一点我希望这里的每个人都能达成共识，那就是无论 AI agent 做了什么，最终承担责任、负有问责义务的人是我们自己，对吧？嗯，而且有件好玩的事，人们讨论说 AI 会……你知道，因为 AI 我们将没有任何工作了。我总是会回归到这样一个事实：我被雇佣、我拿到薪水，部分原因是我要对我为公司产出的结果承担责任，而不是因为我坐在电脑前敲一些东西。因此，人类体验中存在这样一种元素：信任、问责以及团队协作至关重要。那你该如何保持高度的问责性呢？你确实需要能够看清引擎盖下方、黑盒子内部等等。

<details><summary>Original English</summary>
Let

 me

 carry

 on.

 So

 another

 principle

 is





on

 accountability.

 Uh





and

 this

 builds

 on

 the

 evidence

 because





you

 only

 make

 a

 decision

 when

 you

 have





some

 facts

 when

 you

 have

 some

 point

 of





reference.

 Erh

 well

 I

 do

 want

 to

 say





that

 but

 we

 all

 have

 that

 friend

 who





speaks

 very

 confidently

 about

 something





they

 don't

 know.

 So

 little

 bit

 of

 a





counter

 example,





but

 generally

 I

 think

 if

 there's

 one





takeaway

 I

 would

 love

 for

 everyone

 here





to

 feel

 aligned

 with

 is

 we

 are





ultimately

 the

 responsible

 people,

 the





accountable

 people

 for

 whatever

 AI





agents

 do,

 right?

 Um

 and

 there's

 a

 funny





thing

 where

 people

 discussing

 that

 AI

 is





going

 to

 um

 you

 know

 we're

 not

 going

 to





have

 any

 jobs

 because

 of

 AI.

 I

 always

 go





to

 back

 to

 the

 fact

 that

 I

 get

 higher,

 I





get

 paid

 partially

 because

 I

 am





accountable

 for

 the

 results

 that

 I





produce

 for

 the

 company,

 not

 for

 me





sitting

 in

 a

 computer

 and

 typing

 some





stuff.

 So

 there

 is

 an

 element

 of

 the





human

 experience

 where

 the

 whole

 trust





and

 accountability

 and

 working

 together





as

 a

 team

 matters

 a

 lot.

 And

 how

 do

 you





keep

 accountability

 high?

 You

 do

 need

 to





be

 able

 to

 see

 under

 the

 hood,

 inside





the

 black

 box,

 etc.
</details>

呃，我不知道是谁说的这句话。我很喜欢。我一直没能引述它，但是：agent 不需要承担任何现实后果，你要承担。所以我很喜欢举手示意这种形式，但这大概是我唯一的手段了。也许正因如此。有谁见过写下或者被人当面说过这样的话吗：“嗯，我不知道，Claude 给我的就是这个。” [笑声]

<details><summary>Original English</summary>
Erh,





I

 don't

 know

 who

 said

 this.

 I

 loved

 it.





I

 never

 able

 to

 quote

 it,

 but

 agents





face

 no

 real

 world

 consequences.

 You

 do.





So





I

 I

 love

 the

 show

 of

 hands

 thing,

 but

 it





probably

 is

 the

 only

 resource

 I

 have.





Maybe

 that's

 why.





Has

 anyone

 seen

 either

 written

 or

 been





told?

 Well,

 I

 don't

 know.

 That's

 what





Claude

 gave

 me.

 [laughter]
</details>

是啊，

<details><summary>Original English</summary>
Yeah,
</details>

>> 感觉很棒，对吧？就像，“噢，合情合理。是啊，是啊，一切都被原谅了，别担心。”我们要承担 agent 所作所为带来的后果。因此，在我们的 harness 中具备问责机制，能极大减轻你不得不承受的心理压力。免得你脑子里一直在想：“但你觉得它在这里是不是做了错误的假设？”之类的。呃，所以你是想要减少歧义，而不是消除歧义。呃，我敢肯定这里的很多人都会怀念自动模式（auto mode）出现之前的日子。呃，谁想回到自动模式存在之前、你必须按回车键批准每一次单独修改的时候？

<details><summary>Original English</summary>
>> that

 feels

 great,

 right?

 Like,

 oh,

 that





makes

 sense.

 Yeah.

 Yeah.

 Everything

 is





forgiven.

 Don't

 worry.

 We

 face

 the





consequences

 of

 what

 agents

 do.

 So,





having

 accountability

 mechanisms

 in

 our





harnesses





reduces

 a

 lot

 the

 amount

 of

 stress

 you





need

 to

 go

 through.

 Just

 going

 in

 your





head

 like,

 "But

 do

 you

 think

 it

 made

 the





wrong

 assumption

 here?"

 Whatever.

 Erh,





so

 you

 want

 to

 reduce

 ambiguity

 and

 not





remove

 it.

 Uh,

 I'm

 pretty

 sure

 a

 lot

 of





people

 here

 will

 remember

 fondly

 the





days

 prior

 to

 auto

 mode.

 Uh,

 who

 wants





to

 go

 back

 to

 before

 when

 auto

 mode





existed

 and

 you

 had

 to

 approve

 every





single

 change

 by

 tapping

 enter?
</details>

>> 是啊，是啊。美好的时光。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Lovely

 times.
</details>

>> 我现在还在这么做。

<details><summary>Original English</summary>
>> I

 still

 do

 it.
</details>

好吧。

<details><summary>Original English</summary>
Fair

 enough.
</details>

[笑声]

<details><summary>Original English</summary>
[laughter]
</details>

>> 挺合理的。

<details><summary>Original English</summary>
>> Fair

 enough.
</details>

>> 在所有比如说 100 次敲击里，你有多少次是觉得不行的？我的意思是，得了吧。这是一行代码的修改，对比这是很重要的修改，谢天谢地我当时看了一眼。是的，我刚才……

<details><summary>Original English</summary>
>> And

 from

 all

 the

 let's

 say

 100

 taps

 you





did,

 how

 many

 of

 them

 you

 failed

 where?





I

 mean,

 come

 on.

 This

 is

 a

 oneline





change

 versus

 this

 is

 important.

 Thank





god

 I

 was

 looking

 at

 this.

 Yeah,

 I

 just





pre
</details>

我以前经常那样做，但现在呃你有任务集，你审核任务，然后让它去执行，然后我在最后进行审核

<details><summary>Original English</summary>
I

 used

 to

 do

 that

 a

 lot

 but

 now

 uh

 you





have

 the

 set

 of

 tasks

 you

 review

 the





task

 and

 then

 let

 it

 do

 it

 then

 I

 review





at

 the

 end
</details>

>> 这……这基本上就是 harness 的一部分，比如这种设计是有意的，所以你审核的是任务而不是单独的逐项修改，我们只是在此提醒大家：当你设计 harness 时，要确保有意纳入这些把关点（gates），确保你仍然能够对产出的内容负责。嗯，所以确保任何需要做出的判断、任何重要的消歧义——不是那些微不足道的细节，对吧？呃，你依然能够对其有所掌控。呃，要是没有它会发生什么？我不知道，这台随机机器说没问题。真是个绝妙的回答。

<details><summary>Original English</summary>
>> and

 and

 that's

 basic

 that's

 basically





part

 of

 the

 hardness

 like

 the

 design

 is





intentional

 so

 you

 review

 tasks

 instead





of

 individual

 changes

 is

 and

 we're

 just





providing

 you

 with

 a

 a

 reminder

 that





when

 you're

 designing

 a

 harness,

 you





want

 to

 make

 sure

 that

 you

 include

 on





purpose

 those

 gates

 to

 make

 sure

 that





you

 can

 still

 be

 accountable

 for

 what

 is





being

 produced.

 Um

 so

 make

 sure

 that

 any





judgment

 call,

 any

 disambiguation

 that





is

 important,

 not

 the

 trivial

 ones,





right?

 H

 you

 can

 get

 some

 hold

 of

 it





still.

 H

 what

 happens

 without

 it?

 I





don't

 know.

 The

 stoastic

 machine

 said

 it





was

 fine.

 Amazing

 answer.
</details>

<!-- chunk 8/11 -->

审批每一笔计算。光谱的另一端感觉也不好。或者逐行审查你的智能体交付的每个 PR。对，那真的写得不算好，对吧？

<details><summary>Original English</summary>
Approving every calculation. The other side of the spectrum doesn't feel great. Or reviewing every PR line by line that your agents ship. Yeah, that it's not really well written, right?
</details>

>> 但确实，如果没有以一种你懂的、对用例合情合理的方式来设计，它会导致要么很多苦差事，要么很多不必要的工作。额。

<details><summary>Original English</summary>
>> But yeah, it leads to a lot of either a lot of toil and unnecessary work if it's not designed um in a way that you know makes sense for the use cases. Erh.
</details>

那么，关于如何设计良好的问责机制，主要收获是什么？极少数关卡，带有极高信号。你举的任务例子，以及把它们拆解成能让你推导它们连接方式的做法。这是个非常好的例子，额，比如大家只在功能测试通过时才做审查。在此之前的任何事情。我觉得你可以稍微含糊一点，比如对，看起来差不多对，但你绝不会把任何没有通过你所有测试的东西推向生产环境，对吧？所以你设置了一些关卡，但那些关卡必须具有极高的信号，额。

<details><summary>Original English</summary>
So what is the main takeaway on how to design a good mechanisms for accountability? Few gates with very high signal. Your example of the tasks and breaking it down in a way that you can reason about the the way they connect. It's a really good example h on where people do h reviews only on functional tests being passed. anything prior to that. I think you can be a little bit handwavy with yeah sure this looks about right but you wouldn't push anything into production that hasn't passed uh all your tests right so you put some gates in place but those gates need to be very high signal um
</details>

>> 并且，额，补充一下，我认为我们在使用编程助手领域的一些例子，再次强调，这并不是我们在 Monzo 比如处理事情的方式，因为像是有不同的上下文，但当我们在……这引入到了我们的测试支架中。我认为我们使用 AI 编程的例子是因为它们离我们很近，而且它们是许多人每天都在使用的工具。额，但我们在这里应用的，就像 Claude Code 在他们具备一项允许你衡量自己想在多大程度上参与该流程的功能时所做的一样。当我们在构建我们的财务测试支架时，我们也可以用同样的方式来引导我们的用户。

<details><summary>Original English</summary>
>> and uh to to complement I think we're using some examples in the coding assistant world and and again this is not how we for instance approach things at at Monzo because of like a different context text, but when we this is bringing to to our hardness. I think we use the AI coding examples because they're close to us and they're the tools many of us are using on a on a daily basis. Uh but when we apply here is the the same thing that claude code does when they have a feature that allows you to gauge how much you want to be involved in the process. When we are building our financial harnesses, we can also guide our users in the in the same way.
</details>

### 问责关卡与可追溯设计

那相当切中要害。额，再次回到金钱这个领域，有些事情你可以留给智能体去弄清楚。比如，如果你有某样东西的几个可能取值，你就会想，好吧，做三个情景。大概率会没事的。但你在做出任何决定之前，想要把它们并排对比审查。你绝不会把王国的钥匙全盘托付给一个你并不一定信任它会为你着想的东西。并不是说它会有自己的意图，但是，额……

<details><summary>Original English</summary>
That is pretty spot on. Um, and again, just going back to the domain with money, there's some stuff you can leave the agent to figure out. For instance, if you have a few possible values for something, you're like, well, do three scenarios. It's probably going to be fine. But you want to review them side to side before making any decision. You wouldn't hand over entirely the keys to the kingdom to something that you don't necessarily trust is going to have your best interest in mind. Not that it will have an interest at mine, but um
</details>

所以这是一个……非常重要的一点是，你知道错误的决定会延续到你的其他决定中。因此你设计的关卡必须符合目的。你需要非常了解用例，才能够把关卡设置在重要的地方。否则，你只是在任何决定之前添加“询问我”，然后它就又变得信号非常低了。额，而且在代码方面，你并不一定需要去问，因为测试本身就会说明问题。这就是收据派上用场的地方，因为你只需要检查一切都在通过，并且你会因此而拥有很大的信心。

<details><summary>Original English</summary>
so this is a it's very important that you know that bad decisions carry forward into your other decisions. So the gates you design need to be fit for purpose. You need to know the use case really well in order to be able to put the gates where it matters. Otherwise, you're just adding before any decision, ask me and then it becomes very low signal again. Um and well for code you don't necessarily need to ask because the tests will speak for themselves. That's where the receipts come in handy because you only need to check that everything is passing and you will have a lot of confidence because of it.
</details>

所以如果你回到演示，说来好笑，这个计划在问责性上其实并不高。

<details><summary>Original English</summary>
So if you go back to the demo, funnily enough, this plan is not very high on accountability.
</details>

唯一的步骤是我将检查我们计算出的所有东西、所有的情景等等，并且我将做出一个关于我每个月需要存多少钱的决定。我是说这依然挺好，因为没有任何钱从我的银行账户流向任何地方，但是，是的，作为一种问责机制，我有信心这会把控住其他任何事情。

<details><summary>Original English</summary>
The only step is I will check everything that we calculated all the scenarios whatever and I will make a decision on how much I need to save every month. I mean still nice because no money is moving out of my bank account anywhere but yeah there's a accountability mechanism I feel confident that that will gate any anything else
</details>

>> 我想作为，作为一个额外的例子，比如在这个质疑和决定中，很有可能随着我们，假设我们接受了这个，并且这现在被标记为我们做出的一个决定，如果我们使用了这一信息，比如 2 万在第三笔付款的同一天到账，作为影响最终决定的因素。这肯定伴随着问责性。

<details><summary>Original English</summary>
>> I think as a as a as an extra example like in this this challenge and decision here likely as we let's say we accept this and this is now marked as a decision we made if we ever use this information like the 20k landing on the same day as payment three as something that influences the final decision. This definitely comes with the with the accountability.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

往上翻。

<details><summary>Original English</summary>
Go up.
</details>

>> 不，其实我有点在即兴发挥，但是如果你往上滚动一点点。

<details><summary>Original English</summary>
>> No, I actually like I'm improvising a little bit, but if you scroll up a little bit.
</details>

>> 嗯。额，这再次说明，我完全不以此处的任何良好设计自傲，恰恰相反，但额，你看我们在那里有一个稍微有点奇怪的结构，看起来有点像一棵树，有东西分支出来又汇聚回去，那是另一种问责机制，正如 Philip 所说的，在其中有一些决定模型要么是假设的，只是试图找你验证，比如“嘿，这个对吗？这是你想在这里使用的数字吗？”，要么只是试图弄清楚事情如何融入整个系统。

<details><summary>Original English</summary>
>> Mhm. Erh this is like again not not priding myself of any good design at all anything the contrary but h you see we have a little bit of a weird structure there looks like a tree a little bit with something branching out joining back in that's another accountability mechanism as Philip is saying where there's some decisions the model will either assume and just try to verify with you like hey is this right is this the number you want to use here or just try to figure out things how they fit into the overall um system.
</details>

我们认为展示你需要设计一个能给你带来问责性的测试支架的好方法，是确保你能够追踪所有已经做出的决定、是谁做出的，额，并拥有那种感觉：嗯，这是智能体假设的东西，而我让它延续到了我其余的流程中，或者这是我为其提供了修正输入的东西。原因再次是因为我是一个非常看重视觉的人，那可能是什么东西的症状。我不知道。但我认为它有点像不是一条直线对话，而是分支出来然后再分支回去的原因是，当你在与智能体聊天时，再次强调，出于财务目的，你可能会在做出决定之后对某件事进行推敲，而且你完全有权利纠正信息并添加更多上下文。所以，我认为重要的是，当你在创建测试支架时，你不仅要构建用于验证事物、确保你依然负有责任的关卡，而且还要用于纠正方向并确保你可以安全地这样做，而不是像“哦，因为我在聊天中输入了这句话，现在我所有的分析全没了”。额，那在我身上发生过很多很多次，试图解决一个问题，也许我有些心不在焉地对着手机发语音，在中间说了句什么，然后整个分析就全没了，因为我无法真正去掉那句话并且请让其他一切保持原样。额，所以这给了我们另一种手段来对进入财务分析系统的内容负责，以及对什么……

<details><summary>Original English</summary>
We thought a good way to showcase that you need to design a harness that gives you the accountability is making sure that you can trace all the decisions that have been made who made them uh and have that sense of well this was something that the agent assumed and I let carry on in the rest of my flow or it's something that I provided a revised input to and the reason again I'm a very visual person that could be symptom of something. I don't know. But the reason I think it's kind of like a not a straight line conversation, but rather branching out and then branching back in is that when you're chatting with an agent, again, for financial purposes, you may reason about something after a decision has been made and you are well in your right to correct information and add more context. So, I think it's important that when you're creating an a harness that you not only build those gates for validating things, making sure that you're still accountable, but also for correcting the course and making sure that you can do so safely and it's not like, oh, because I typed this sentence in the chat, now all my analysis is gone. H that has happened to me many many times trying to solve a problem and maybe I was like dispersed dictating to my phone I said something in the middle of it and then the whole analysis is gone because I can't really take away that one sentence and please keep everything else as it was h so this gives us another means to be accountable for what goes into the system for financial analysis and what
</details>

你想切到幻灯片吗？是的。

<details><summary>Original English</summary>
Do you want to move to the slides? Yes.
</details>

好的，太酷了。那么，额，我们可以尝试几件事。额，你可以把鼠标悬停在婚礼例子中显示我们有多少位客人的芯片上。而且你可以添加，那会把它添加到聊天中，然后你可以说：“哦，其实不是这个数字。额，比如我们将迎来不少于 150 位客人。”额，那会让你的测试支架重新思考计划，看到该输入对其他事情造成的影响，并提出修改你的计划，或者仅仅是更改输入什么的。

<details><summary>Original English</summary>
Okay, cool. So, uh, a few things we can try. Erh, you can go and and hover into the chip that guest that says how many guests we have in the wedding example. And you can add that that will add it to the chat and you can say, "Oh, actually, it's not this number. H we will get no fewer than 150 guests for instance. Erh that will get your harness to rethink the plan see the consequences of that input into other stuff and suggest a either a modification of your plan or just change the input whatever.
</details>

这里的重点在于你是有意构建反馈机制，并且你拥有一定的判断力，来确保基于该输入可能会改变你整个分析的事实而存在某些随之而来的决策。额，你需要把握大局以确保那些改动是合理的。

<details><summary>Original English</summary>
The important part here is you build the feedback mechanism on purpose and you have some judgment over making sure that there is some consequential decision making on the fact that this input may change your whole analysis. H you need to be on top of making sure that those changes make sense.
</details>

你可以尝试的另一件事是，如果你点击第五步，额，你可以开启一个新的分支对话，像一个分支出来的对话，我想按钮在底部的聊天界面上。

<details><summary>Original English</summary>
The other thing you can try is on if you click on step five erh you can open up a new branch conversation like a branched conversation I think is the button on the chat at the bottom
</details>

>> 这里。

<details><summary>Original English</summary>
>> here.
</details>

>> 对。对。所以你可以开启一个新分支。

<details><summary>Original English</summary>
>> Yeah. Yeah. So you can open a new branch.
</details>

有人用过那个斜杠……

<details><summary>Original English</summary>
Has anyone used the slash
</details>

>> Claude 上的“顺便说一句”功能吗？

<details><summary>Original English</summary>
>> btw by the way thing on cloud?
</details>

你们用起来体验怎么样？

<details><summary>Original English</summary>
How has been your experience using it?
</details>

>> 有时管用，有时不管用。

<details><summary>Original English</summary>
>> Sometimes it works, sometimes it doesn't.
</details>

>> 有时管用，有时不管用。而且感觉就像你在做旁白，但又不是真正的旁白。旁白……

<details><summary>Original English</summary>
>> Sometimes it works, sometimes it doesn't. And it feels like you're doing an aside, but not really an aside. Aside
</details>

>> 它变成了上下文的一部分，对吧？

<details><summary>Original English</summary>
>> it becomes a part of the context, right?
</details>

>> 但是你有的选吗？比如我也许在对话中途有一个愚蠢的问题。

<details><summary>Original English</summary>
>> But do you get a choice? Like maybe I have a stupid question in the middle of the conversation.
</details>

>> 不，我没得选。我没有，[笑声] 如果我问了一个问题，那么它就变成了该会话的一部分。

<details><summary>Original English</summary>
>> No, I don't have a choice. I don't [laughter] if I ask a question then it becomes the part of the session.
</details>

>> 对。对。

<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

### 旁白分支与校验原则

所以在我们这里，我们试图做的，回到我们为什么要这样做，我们想向你展示如果我们在设计时抱有“好吧，这真的需要是一段旁白”的意图，它感觉会是什么样。我在跟 AI 聊天时有太多愚蠢的问题了。太多了。这很丢人，但我最终不得不打开一个单独的聊天，因为我不相信它不会污染我正在做的事情。然后我就会花更多时间去说：“嘿，这是一个愚蠢的问题。请不要用在其他任何事情上”，这就像 Philippe 说过的“请不要犯任何错误”那回事一样。

<details><summary>Original English</summary>
So in here, what we're trying to do, and going back to why we're doing it like this, we want to show you how it could feel if we design something with the intent of, well, this really needs to be an aside. I have too many stupid questions when I'm chatting with AI. So many. And it's shameful, but I end up having to open a separate chat because I don't trust it's not going to contaminate what I'm doing. And then I will take more time just being like, "Hey, this is a stupid question. please don't use for anything else is the please don't make any mistakes thing Philippe was saying
</details>

>> 额，效果不是很好。所以无论你怎么设计，如果你有一个反馈机制，确保你根据自己究竟想怎么使用它来量身定制。额，哎呀，很好。然后至于额最后一点，最后一个原则将是验证。所以你需要第二双眼睛，而这建立在……原则之上。

<details><summary>Original English</summary>
>> h doesn't work quite well. So whatever you design if you have a feedback mechanism make sure that you tailor it to how you actually want to use it. Erh oops cool and then as for h the last point the last principle will be verification. So you want a second pair of eyes and this builds on the principle of
</details>

<!-- chunk 9/11 -->

责任归属，因为你同样要对那次审查负责。额，也许这听起来太抽象了，但有没有人遇到过这种情况：有人就凭着一句“没有啊，弗朗切斯科（Francesco）审查过了”，就把错误决策的责任推到你或者其他人头上？

<details><summary>Original English</summary>
accountability

because you are accountable for that

review as well. Erh,

and maybe that's too abstract, but has

anyone been in a situation where someone

h passed the blame on a bad decision to

you or anyone else just on the basis of

No, but Franchesco, review it.
</details>

这种情况确实会发生。

<details><summary>Original English</summary>
That happens.
</details>

>> 确实会发生。所以，嗯，大约一个月前我们进行过一次很有意思的交谈，当时有几个人开始产生一种想法：在 VIP 编码中，某样东西是好是坏、是否正确的负担，最终落到了团队审查者的手里。这让人感觉非常挫败，因为塞给你的只是一堆看起来大概没错的东西，但最终确保它正确的责任却落在了你的头上。整个验证原则只是为了建立更多的反馈回路，让你不至于留下盲区，但绝不是要把责任推卸出去。归根结底，这只是来自不同渠道的补充信息，用来避免偏见、避免你陷入自己的思维定势和固有流程中。但它丝毫不会免除任何责任。

<details><summary>Original English</summary>
>> That happens. So, um, we were having a

funny conversation like a month ago

where a few a few people are starting to

have thoughts that the burden of

something being good or correct with VIP

coding ends up being in the hands of the

reviewer in a team that feels really

demoralizing because you're just being

given a bunch of stuff that sure looks

about right, but then it's your

responsibility responsibility ultimately

to make sure that it is right.

This whole principle of verification is

just building more feedback loops so you

don't have blind spots but without

relegating any of the accountability.

Ultimately, this is just extra

information from a different source to

avoid biases and avoid

you getting stuck on your own thinking

and your own processes. But it doesn't

remove any of the responsibility or

accountability.
</details>

### 直觉检验与基准参照

嗯，很有意思的是，专家往往不会逐个单元格去检查。这更多来自我与财务团队在数据方面共事的经验。他们打开电子表格，可能只看几个他们知道能反映大概总数的单元格；如果感觉不对劲，他们就会指出来。比如：“我们怎么在营销上花了这么多钱？我觉得这不对。”这在一定程度上是一种直觉反应。你不需要耗费很大精力，不需要完全重做你的方案，也不需要去质疑自己做出的每一个决定，但你确实需要有一个独立的参照点。额，我想我之前有个例子，不过记不太清了，好像是关于一条传播非常广泛的推文，说埃隆·马斯克（Elon Musk）拥有不知道多少万亿美元，然后有人评论说，他其实可以给世界上每个人分一百万美元，而且自己手里还能剩下钱。当时大家就觉得：“等等，什么？这感觉不对啊。”就像你读到它时会想：“等等，什么？看着挺像那么回事。”然后你转念一想：“不对，不对，这不可能对。”要让你去深究那个人所做的计算，靠的就是那么一点点直觉。嗯，所以只要能有什么东西帮忙把关，给出个粗略答案，或者在某处看着不对劲时提出质疑，就非常有帮助。

<details><summary>Original English</summary>
Um

yeah, funny enough, expert experts often

do not check every cell. And this is

more on like my experience working with

financial finance teams in data.

They could open a spreadsheet and just

look at the you know a few cells they

know will give you a ballpark total and

if it doesn't feel right they will let

you know. It's like, how did we spend

this much money on marketing? I don't

think that's right. Uh, and it's a

little bit of a gut reaction.

You don't need a lot of effort. You

don't need to like redo your plan

entirely or challenge every decision

you're made, but you do want to have a

separate point of reference. Erh,

I think I I had an example, but I don't

remember what was it was something about

a tweet that got really famous about

Elon Musk having I don't know how many

trillion dollars and someone saying

like, well, he could give a million

dollars to every person in the world and

still have money. And he was like,

wait, what? That doesn't feel right.

Like you read it and you're like, wait,

what? Looks plausible. And then you're

like, "No, no, that's not right." And

that needed need that needed for you to

look into the calculations the person

made is like a little bit gut feeling.

Um, so just having something review and

give you a rough answer or some

challenge if something doesn't look

right is extremely helpful.
</details>

>> 不好意思。

<details><summary>Original English</summary>
>> Sorry.
</details>

提供。

<details><summary>Original English</summary>
supply.
</details>

>> 问得太好了。额，我刚才在努力想一些更接地气的例子，但我认为这是非常值得探讨的对话。一个很有力的论点是：如果你已经有了关于数据应该呈现什么样子的黄金样本，那为什么你的流程产出的结果会与之不同呢？你为什么不直接用黄金样本去核对呢？这也是我想从金融领域抽象出来的一点。你拥有很多信息源，非常多。在你的数据之外，你总能找到另一个参照点。所以，如果你正在使用的某些信息源声称了不知道什么事实或数字，你有互联网，你应当始终尝试通过查看所有不在我当前使用范围内的资源，来增强你获得的信号；这样就能避免那种反馈回路——即你手头只有现成的信息，只有自己的黄金样本，结果看什么都觉得是对的。在构建测试夹具（harness）时，总要尽量发挥一点创造力，引导它可以利用哪些其他的参照点来帮助你做出更好的决策，或者发现某些不太对劲的地方。这样说能理解吗？

<details><summary>Original English</summary>
>> That is such a good question. Uh I was

trying to come up with a examples that

feel more down to earth, but I think

that's a very conversation to have. A

good argument is if you're getting

golden examples of how the data should

look like, why would your process give

you something different to that? Like

why don't you just check with your

golden examples? And this is something I

I wanted to abstract away from the world

of finance. You have a lot of sources of

information, a lot of them. You always

have another point of reference outside

of your data. So if some sources you're

using are claiming I don't know whatever

fact a number you have the internet you

should always try and

enhance the signal you're getting by

looking out look at all the resources

that are not the ones that I'm using and

you avoid that feedback loop where you

only have the information you have

available you only have your golden

examples and everything looks right to

me

Always try to get a little bit creative

when building a harness to try and guide

which other uh points of reference it

could use to help you make a better

decision or to know if something is not

quite right. Does that
</details>

>> 能。我想我们通常会尽量与相关人员合作，去理解 Agent 应该使用的最佳工具或信息组合是什么。所以试图理解怎样才是最优的……

<details><summary>Original English</summary>
>> Yeah.

And I guess we generally try to work

with

whoever it is to like understand what

would be the best set of things that

agent should use.

So trying to understand how that would

have been the optimal
</details>

### 薄片抽取与跨领域校验

再举一个可能有用的例子。我认为黄金样本为你提供了事实真值（ground truth），确保你处于正确的空间之内，但没有任何一个领域是孤立的。所以，我以前在某家公司当商业智能（BI）分析师时，经常遇到这种情况：我觉得自己写得非常好，查询语句很棒，得出的数字看起来也很合理，而且我核对了一切，没发现任何差错。然后，当我把仪表盘展示给某个利益相关者时，对方立刻就说“这不对”。我当时就很诧异：“你什么意思？你比我更懂 SQL 吗？这分析是你跟我一起做的吗？”结果发现，这个人来自另一个团队，他们对那一年的销售额等数据心里大概有个数。所以他们凭直觉就知道那个数字不可能对，因为如果它对了，就意味着他们在另一个地方掌握的信息是错的。如果把这一点转译到 Agent 的世界，我在测试夹具中给 Agent 的黄金样本，会带有基于该领域的偏见和选择性偏差等，因为我是针对该领域挑选的它们，而且我认为它们很契合该领域；但当你着眼于一个稍有相关的跨界领域时，你可能会发现这实际上根本讲不通——仅仅通过对比手头的另一件事物，就能看出这个数字是错的，我甚至不需要回过头去重新检查自己的计算。

<details><summary>Original English</summary>
to give you another example that could

be useful. I think the golden examples

give you your ground truth for making

sure that you are within the right space

but no domain is isolated. So what

happened to me a lot of times when I was

a BI analyst in some like company is

that I thought what I wrote was really

good. So my query was good. The number I

got seemed reasonable and I was checking

everything and nothing looked off. And

then when I presented the dashboard to

some stakeholder immediately went like

that's not correct and I was like what

do you mean? Do you know SQL more than I

do? Did you do do the analysis with me?

And turns out this person was from a

separate team and they just had an idea

of how many whatever sales were made in

that year. So they knew instinctively

that number can't be right because it

means my information in this other place

is incorrect. So it's not if we

translate that to the agentic world the

golden examples I will give my agent in

my hardness will be based on like biases

and selection bias and so on based on

the domain and I picked them for the

domain and I think they're good for the

domain but when you look at a slightly

tangential domain you may find out that

actually this is nonsensical like this

number is wrong just by looking at this

other thing next to me I I don't even

need to look again into my calculations.
</details>

很好。

<details><summary>Original English</summary>
Cool.
</details>

额，所以存在一个叫做“薄片抽取”（thin slicing）的概念，即凭借你经验轶事的极薄切片，根据你在自己领域、在所从事的任何分析中的经验，去感知哪些东西感觉是对的，哪些感觉是不对的。而模型所拥有的，是其他所有人经验的平均值。因此，在构建测试夹具时，你需要确保能够建立一种反馈机制，以便从模型自认为掌握的知识，一路核验到你认为自己掌握的知识。如果把你刚才听到的这句复杂的话倒过来看，这正是我们开启整个框架和所有原则的方式——你正试图达成那种共享领域、共享上下文。本质上，你是在将自己的语言转译为模型的训练数据集。你只是在与模型合作，表达出类似“好的，这就是我对这个问题的理解，或者我公司是如何处理这件事的”；然后模型协助你说“好的，那我该如何将它融入我的训练数据集中”。而在这里，我们做的是相反的事，我们只是在说：“好的，我认为我们已经达到了让你能对这个领域做出合理解释与判断的程度，但我们还是建立一个反馈回路吧，这样我就能根据我的经验告诉你，这看起来是完全离谱，还是合情合理。”所以……

<details><summary>Original English</summary>
Erh. So there is a concept called thing

slicing

where you have thin slices of your

anecdotal experience and you know what

things feel right or feel wrong based on

your experience in your domain. Whatever

analysis you're doing. the model will

have an average of everyone else's

experiences. So when you're building

your hardness, you need to make sure

that you can uh have a feedback

mechanism so that you can verify from

what the model thinks it knows all the

way to what you think you know. And if

you flip that convoluted sentence I just

said it's the it's how we started the

whole framework and all the principles

where you're trying to get to that

shared domain shared context. You're

essentially translating your language

into the training data set for the

model. You're just working with the

model to be like okay this is how I

understand the problem or how my company

does this. and then the model is helping

like okay this is how would I fit it in

my training data set here we're doing

the opposite we're just saying okay I

think we got to a point where you can

make a reasonable judgment over this

domain but let's have a feedback loop so

I can tell you from my experience if

this looks entirely off or if it looks

reasonable so
</details>

嗯，确实，“这大概没问题”呈现出来的样子可能跟你的预期大相径庭。我认为这是个很好的描述方式：比如“对，看着差不多对”，结果发现你们公司确实很在乎那 5% 的差异。当你为团队构建测试夹具时，意识到这 5% 对整个团队来说可能是一票否决的关键因素，就会带来天壤之别。

<details><summary>Original English</summary>
um

yes it's probably fine may look nothing

like yours

I think is a way good way to describe it

like yeah it looks about right and then

turns out your company does care about

that 5% difference it makes a world of a

difference when you're building hardness

for your team that you're aware that

that 5% it will be a deal breaker for

the whole team.
</details>

嗯，如果你没有办法做到这一点，就会出现一些状况。比如逐行检查一切，或者什么都不检查，或者对“大概合适”该是什么样子毫无概念；而如果你没有那个参照点，你的测试夹具同样也不会有。所以你需要构建诸如此类的外部验证点。

<details><summary>Original English</summary>
Um there's some stuff that happens if

you don't have um a way to do this. So

checking everything line by line or

checking nothing or you know no sense of

what about right looks like and if you

don't have that point of reference your

harness won't have it either. So you

need to build those kind of like

external validation points.
</details>

这部分内容我先跳过一些。至于验证，同样体现在决策中的那些分支节点上，我们在那里为模型自以为掌握的部分内容添加了外部参照点。

<details><summary>Original English</summary>
I'm going to skip through some of this.

And for the verification, it's those

notes in the H decision as well where

we're adding uh an external point of

reference to some of the stuff the model

thought it knew.
</details>

当那个分支就这样……

<details><summary>Original English</summary>
It's kind of satisfac satisfactory when

the thing just like
</details>

>> 分支合并回来时，感觉挺让人满意的。对，没错。

<details><summary>Original English</summary>
>> the branch go comes back. Yeah, exactly.
</details>

而且我觉得这再次创造了一条轨迹，从而能够……比如，那种薄片抽取和快速的直觉式审视也正是来源于此，因为你理解了 Agent 经历的思考过程，而不仅仅只看输出结果。

<details><summary>Original English</summary>
And again, I think it creates a a trace

to to um be able to like the the thin

slice and the quick instinctive look

also comes from from this because you

understand the thought process that the

agent went through and not only the the

output only.
</details>

我返回一下。好的。

<details><summary>Original English</summary>
I go back. Yes.
</details>

因此，和其他示例一样，如果你还在跟着操作，有几件事你可以尝试。你可以针对带标签的质疑（tagged challenge）打开一个分支。那基本上是一个独立的 Agent，我们指派它的任务是审查方案、审查假设，然后提出一些有益的质疑：“这读起来合理吗？”嗯，直接点击它、打开它，然后你就会看到就像菲利普（Philippe）刚才做的那样，它会合并回主干，并切实改变方案。所以这是会产生影响的，而且我们认为这是另一个重要的……

<details><summary>Original English</summary>
So, as with the other examples, if

you're still following along, there's a

few things you can try. So, you can open

a branch uh on a tagged challenge.

That's basically a separate agent that

we tasked with reviewing the plan,

reviewing the assumptions, and then

doing some healthy challenge. Does this

read reasonable? Um so just click it

open it up and then you will see how

just Philippe did it will join back into

the trunk and actually change the plan.

So there is a consequence

and we think this is another important
</details>

<!-- chunk 10/11 -->

这也是对 harness 的设计保持审慎态度的一部分。我们本可以直接采用大模型作为裁判（LLM as a judge）的方式。也就是说，针对每一个决策、每一套方案等等，直接再启动一个智能体去做审查，然后就完事了。但问题在于，如果没有反馈回路，我们的财务决策或者任何决策都根本不会得到任何改进。所以这也是设计的一部分，是你为了针对自己的各种用例打造合身专属的 harness 所需要培养的品味。然后另一件你可以尝试的事情，就是再点开一个，然后直接点击忽略（dismiss）。我们特意设计了这一点，因为正如我之前所说的，有时候某些对话实际上并没有带来任何改变，或者对你的流程来说并不实质关键，而你作为当事人最清楚不过。所以你需要拥有那种用于核实事务的参照点。

<details><summary>Original English</summary>
part of being intentional with the design of your harnesses. We could have left it as LLM as a judge. So for every decision, for every plan, whatever, spin another uh agent and then do a review and call it a day. The problem is if there's no feedback loop, our financial decision or decision whatsoever doesn't improve at all. So that's part of the design, the taste you need to build h to create fitforpurpose harnesses for whatever use cases you have. Then the other thing you can try is opening another and just clicking on dismiss. And we did that on purpose because sometimes as I was saying before some conversations don't actually change anything or not material to your process and you will know better. So you need to have that kind of like point of reference for validating things.
</details>

那么简单总结一下，并把这个在屏幕上留存片刻。如果你还在实际把玩体验这个 harness，想要构建一个在处理财务数据和资金时真正值得信赖的优秀 harness，其框架是建立在这五条原则之上的：拥有共享领域、保持一致性、出示凭据、明确责任归属，以及确保在你自己所认为的认知之外建立起有意识的核实闭环。

<details><summary>Original English</summary>
Um so just to summarize and leave this on the screen for a moment. Um, if you're still playing around with the harness, uh, the framework for building really good harnesses that you can trust with financial data with money, it's built on these five principles. So having a shared domain, having consistency, showing the receipts, keeping your accountability, and making sure that you create intentional loops for verification outside of what you think, you know.
</details>

额，什么？没有彩带庆祝啊。有点失望。好的。有几个案例我们认为界定清楚很重要。噢，不好意思，你刚刚举手了。

<details><summary>Original English</summary>
Erh, what? No confetti. Disappointing. Okay. So, there's a few cases where we think it's important to define. Oh, sorry. You had your hand up.
</details>

### 构建专用 Harness 的考量与权衡

>> 是的。我就是想确认一下自己的理解。你们为我们带来了一套框架原则，大家可以在此基础上构建自己的 harness。同时你们也展示了一个 harness 作为范例。所以我现在在想，我应该在什么时候去构建其他的 harness？harness 应该做到多通用或者多专用？因为你们是用具体的 harness 来解决问题的，比如在你的工作中总共拥有多少个 harness？是只有一个，并在这个 harness 中解决你遇到的所有事情，还是说拥有多个更加专用的 harness？它的通用程度如何，你们多长时间会构建一个？比如你在构建一个 harness 上会投入多少精力？是一个月做一个，还是每六个月做一个？

<details><summary>Original English</summary>
>> Yes. So, I just confirm my understanding. You brought us a framework principle. You can build your harness upon it. And you also brought one harness as an example. So, I'm I'm thinking about when should I build other harness, how generic or how specific the harness should be because you solve problems with the specific harness and like for example how many harnesses do you have in your work? It's just one and you solve everything that you have for this in this harness or you have multiple more specific harness. How generic and how often do you build one? Like how much effort do you put in building one? you make one every month or you make one every six months.
</details>

>> 这是一个非常好的问题，当然并没有明确唯一的答案。我认为就像你所说的那样，我们可以梳理出光谱的两端：一端是我凡事都只用 Claude Code 或者 Codex，把所有的东西都嵌入到 skills、instructions 等等之中；而在光谱的另一端，则是我每想做一件哪怕微小的新事情，都从零开始构建一套。当然，到了一定阶段这种做法会让人精疲力竭，因为有时候你花在制造工具上的时间，比实际使用工具的时间还要多。

<details><summary>Original English</summary>
>> That's a that's a great question and there's no clear answer of course. Um I think it's we could we could trace as you said like the two ends of the spectrum as I just use cloth code or or codeex for everything and I just embed everything into skills instructions so on so forth and on the other end of the spectrum is for every small new thing I want to do I'll build it from the ground up and like of course that will get tiring at some point because like you're spending more time creating your tools than actually using the tools sometimes
</details>

还是那句话，并没有明确统一的答案。我认为关键在于你何时觉得这个用例足够有价值。也就是说，你追求可复现性；或者你觉得使用预置的通用 harness 所得出的结果非常频繁地出现错误，因为构建 harness 能带给你的价值，就是让你通过确定性部分与非确定性部分的结合，重新获得更多控制权，对吧？

<details><summary>Original English</summary>
Um again there's no clear answer. I think it comes to um when you feel the use case is worth enough. So you want reproducibility, you want it to feel few the results you are getting using the pre-built harnesses are very frequently getting it wrong because the value you get from building the harness is you get more control again with the deterministic bit together with the nondeterminism. Right?
</details>

我们在财务分析的情境和用例下讨论这些原则，原因就在于，如果我们把这种类型的用例放在一个不具备这些原则的 harness 中运行，我们很可能会遇到 Francesco 在刚才各个步骤中梳理出的那些陷阱。所以在这种情况下，为了避免我们一而再、再而三看到的这些陷阱，去专门构建工具是合理的。但话又说回来，我认为这取决于你认为会有多少用户经历那个用例，以及你所观察到的问题关键程度究竟有多高。比如，如果你正在解决的是一项非业务关键性的任务，那么留有人类在回路中审查你拿到的输出并引导智能体，哪怕需要多经历几轮对话，大概也是完全可以接受的。但如果你要把这个东西交到内部用户的手中，比如说你正在为自己的信用分析师团队构建工具，将有 50 个人使用它来支撑公司的关键决策，那么毫无疑问，你绝对不希望在这个过程中出现巨大的变异波动。所以还是那句话，我认为这里没有非黑即白的界限，但这些是我在做决策时会去权衡考虑的因素。

<details><summary>Original English</summary>
Um the reason why we're talking about the the principles in the case in the um scenario of a financial analysis is because if we do this type of use case in a harness that doesn't have it we'll probably have some of the f pitfalls that Franchesco talks through each of the steps. So then in this case it makes sense for um to avoid these pitfalls we are seeing over and over and over again to build the thing. But again, I think it comes down to how many users you believe will go through that use case, how critical is the problem that you were seeing. So like if if there's a non-b businessiness critical um task that you were solving, you were probably fine to have a human in the loop reviewing the outputs that you get and steering the agent even if that takes a few extra turns. But if you're putting this in the hands of a uh internal user, for instance, let's say you were building something for your team of credit analysts, um you're going to have 50 people using something to support key company decisions. Yeah, you absolutely don't want a lot of variability on that. So again, there's no clearcut I would say, but these are the things I would consider in in making the decision.
</details>

或许我可以通过反面情况来补充说明一下。我们之所以认为这套方案特别适合财务类的 harness，是因为它的利害关系重大。你需要大量的反馈回路。这些用例中存在着非常具体的特性，我们在个人层面或公司层面都以某种形式在此呈现出来了。但设想一下，如果你想用 AI 仅仅是去制作社交媒体内容，而你的用例之一可能就只是像大家都在做的那样，用 AI 生成的视频去淹没 Instagram 和 TikTok。那么这里的某些步骤你大概就不会那么在乎了。搜集证据？图什么呢？核实或责任归属就更无关紧要了。所以这套方案是专门针对财务类用例设计的，也可以延伸到它的不同层级，但一切都立足于它是一套信任系统这一事实上。如果你的用例并非必须如此，那么这个方案可能就没有那么大用处。至于你究竟想要构建多少个 harness，我认为 Filipe 说得更贴切，但你很容易沦落为不断磨刀却从未真正砍柴的受害者。所以到了一定阶段，如果你尝试去使用某种现成工具却得不到正确的结果，你可以尝试添加几个 skill、几个命令、几样额外的东西；如果依然得不到你想要的结果或体验，你发现自己不停地从一个对话复制粘贴文本到另一个对话，不断开启新会话，感觉变得杂乱繁复，那就做个 harness 吧。把你不得不重复做过三到五次的所有事情变成只需一次，并围绕它来进行设计。

<details><summary>Original English</summary>
Maybe I can help with uh the counterfactual. So, we think this is a good recipe specifically for financial harnesses because there's a lot at stake. You want a lot of feedback loops. There's very specific things about those use cases that somehow we're representing here even at the personal level or the company level. But imagine you want to do you want to use AI just to produce like social media content and maybe one of your use cases is just flooding Instagram and Tik Tok with AI generated videos like everyone is doing. There's some steps here that you probably don't care that much. Evidence gathering. What for? H verification or accountability even less so. So this is specifically geared towards like financial use cases and it can be extended to different levels of it but everything hinges on the fact that is a trust system. H this recipe may not be as useful if your use cases are not necessarily like that and in terms of how many harnesses you want to build. I think Filipe said it better, but you can easily fall victim for doing a lot of axe sharpening and not actually using the axe. H So, at some point, if you're trying to use something and you're not getting the right results, you can try adding a couple of skills, a couple of commands, a couple of extra things, still not getting the results or the experience you want. You're finding yourself copy pasting text from one chat to another, opening a new session. It feels convoluted harness. So you all the repeated things that you had to do three five times. Okay. Just once and you design it around it.
</details>

>> 是的，没错。

<details><summary>Original English</summary>
>> Yes. Yes.
</details>

>> 还有几个相关的问题。比如对于你的婚礼筹划任务，对吧？我认为其中一种比较天真的看待方式大概是：比如启动一个智能体，启动各个智能体，场地智能体。你有试过这种做法吗？结果如何，或者说你对此怎么看？

<details><summary>Original English</summary>
>> Some more related question. So for your wedding planning task, right? I think one of like one of the naive way of looking at this is like maybe spin of agent, right? agents, venue agents. Uh, have you have you have you tried that and what's the outcome or like your opinion on that?
</details>

>> 首先我要坦白的是，我订阅了最昂贵的 Claude 套餐，而且确实用到了上限，但这并不是在褒义上说的，就好像 Anthropic 绝对因为我而亏损陷入了赤字。我曾尝试调研所有事情，涉及所有场地、鲜花、婚礼，做各种筹划，推演我们必须支付多少费用的各种不同方案等等。而我发现的是，在很多情况下，通过新的网络搜索以及优化过的工具等等，直接帮我列出马德里排名前五的摄影师，效果就足够好了。运行得非常顺畅。不需要再做别的任何事，只需启动、拿到对比，甚至去联络他们。但对于某些更加微妙的用例，我确实希望拥有更多的控制权和可预测性——这与它们的财务属性相关联——我确实发现自己会觉得：我需要构建一套稳健的东西，我可不想把这个重新再计算一遍了。而且为了说明那种切肤之痛：我记得有一天自己在车里，当时觉得“行啊，我可以用语音模式口述一些东西”，然后我就开着车，往返大概各需要一个小时的车程，你知道的，去程一小时，回程一小时，在那段路程里同样的对话我翻来覆去进行了三次，就是因为每次我想做一些与财务相关或临近的规划时，某些环节就会出岔子，然后我就会觉得……所以是的，这很有帮助。

<details><summary>Original English</summary>
>> I will start by confessing that I have the most expensive cloth subscription and I do max it out and not in a good way as in Anthropic is definitely on the on the red because of me. I tried research everything for all the venue, the flowers, the wedding, do the planning, do the different like scenarios for how much we will have to pay etc. And what I found is that in many cases it was good enough to give me the list of the top five photographers in Madrid with the new web search with like a refined h tooling etc. Worked like a charm. didn't have to do anything else just spinning and having comparisons and even reaching out to them. But for some more nuance use cases where I do want to have more control and predictability and this is linking to the financial nature of them I did find myself being like I need to build something robust. I'm not recalculating this again. Uh and to to make the pain very real. I remember myself one day because I was in the car and I was like, "Yeah, I can dictate some stuff, voice mode, and then I was driving and it was about an hour drive back and forth, you know, an hour and an hour and I re had I had the same conversation three times in that t in that trench just because every time I was trying to do some financially related or adjacent planning, something will go wrong and I'll be like so yes, that helps.
</details>

### 向领导层沟通期望与管理认知

>> 那么回到你做商业智能（BI）的例子，对吧？比如……我认为早年间并没有人会去验证你的 SQL 查询，对吧？所以这看起来就像是我们处于……这就像是更高阶的 SQL 查询，对吧？现在你之所以去构建工具，是因为 harness 构建起来更容易了等等。在与领导层的对话中，你们是否找到了某种方法去把这一点向他们阐明清楚？因为在我看来，每当有 AI 介入时，人们总会有一种期望，认为它会是 100% 正确的。你能理解我的意思吗……

<details><summary>Original English</summary>
>> So getting back to your example of being a BI, right? Like um I don't think back in the day there were people who were validating your SQL queries, right? Um so this seems like we are it's like next level of SQL queries, right? Now you're building tools because harnesses are easier to build and stuff. Have you found ways to kind of make this point clear to leadership in in conversations that like because because to me it feels every time there is an AI there is an expectation that it will be 100% correct like do you see what I'm getting at
</details>

>> 所以你的问题是关于管理预期，以便当人们进行基于智能体的自主探索时……

<details><summary>Original English</summary>
>> so is your question about managing the expectations so that when people do agentic self surf
</details>

>> 不是自主探索，更多的是比如你构建了这个，并且你在与高管领导层沟通，以便在你的公司里做出某项财务决策，对吧？而他们

<details><summary>Original English</summary>
>> it's not enic sales more so like let's say you build this and and you talking to your senior leadership to make a financial decision in your company, right? And they
</details>

<!-- chunk 11/11 -->

### 验证 AI 产出与 harness 的边界

开始追问你，不断盘问你，而且一旦你说：“哦，我用了 AI 和 harness”，他们就会说：“那这个必须达到 200% 的正确率才行”，或者类似的话，你懂我的意思吧？你有找到什么方法来确保他们理解这本质上仍然是 SQL 查询吗？

<details><summary>Original English</summary>
start drilling you and drilling you and and the moment that you say, "Oh, I use AI and harnesses," they're like, "Well, this has to be 200% correct or something like you know what I'm saying? Have you found the way to to kind of make sure that they understand this is still SQL queries?"
</details>

>> 稍微剧透一下，明天有一场演讲。[笑声] 我不知道。你有什么想法吗？[清嗓子]

<details><summary>Original English</summary>
>> Bit of a spoiler, but there's a talk tomorrow. [laughter] I don't know. Do you have any? [clears throat]
</details>

>> 对，对。不，我认为在以 AI 为先的世界里，正如你所说，我们有时会忘记那仅仅是一个工具，一种达到目的的手段，在……比如到底发生了什么之前。所以我认为我们注意到的，再次从 Monzo 的经验来看，我们一直是从高度以影响为导向的视角来切入的。所以这不是说“我们应该为此使用 AI，因为 AI 可以巴拉巴拉”，而是“我们在这里期望的结果是什么？我们在这里如何衡量成功？我们是在追求减少与 BI 团队之间的来回沟通吗？”——我们甚至都没有 BI 团队，但你懂我的意思——“来验证一个新看板吗？”好的，那我们可以追踪这一点，实际看看 AI 是否能支持我们实现这个结果。

<details><summary>Original English</summary>
>> Yeah. Yeah. No, I think um it's with the AI first world, we sometimes as you were saying forget that what's that that's only a two and a means to an end be before like what's what's going on right so I think what we would have noticed and again from Monzo's experience we've been approaching it from an highly impactbased um point of view so it's not about we should use AI for this because AI can something something something. It's like what's the outcome we're looking for here? What how do we measure success here? Are we looking for less uh back and forth with a BI team? Uh we don't even have a BI team, but you get you get what I mean. Um to validate a new dashboard. Okay. So, we can track that and actually see if AI can support us in in generating that outcome.
</details>

我们是在追求减少……我不知道……因数字看起来不对而提交的内部咨询工单吗？好，那我们就去追踪那个指标。那么在某种程度上，只要合乎逻辑，我们采用的方法、我们实施的方式其实并不那么重要，因为归根结底，它是一个能够帮助我们达成该结果的工具，可能速度更快、有着更好的护栏等等。所以我认为，重点较少在于去让人们对实现本身、对 AI 本身产生信任，而更多在于围绕我们试图通过 AI 推动实现的结果达成一致。

<details><summary>Original English</summary>
um are we looking for um less I don't know internal ask tickets because the number looks wrong. Okay, so let's track that and then the approach that we do the way we do that doesn't really matter to a point if that makes sense because it will be again a tool that can get us to that um to that result probably faster with better guard rails and so on and so forth. So I think it's less it's less about gaining trust on the implementation on the AI itself but more about aligning on what's the outcome we're trying to drive with the AI.
</details>

我想那边还有一位。

<details><summary>Original English</summary>
I think we had another one there.
</details>

我的问题更多是：你展示了一个具有一定复杂度的 harness，对吧，你有 UI，有数据库等等。但我也构建过调用其中一些步骤的过程，不过它们都是以 skill 的形式存在的，对吧，它会向你提问，基于 Python 脚本来跑数据等等。所以我的问题更多是：在你看来，使用一个包揽所有这些的 skill 与构建一个单独的工具之间，界限在哪里？或者说你尝试过这样做吗？

<details><summary>Original English</summary>
My question is more you have show a harness that has some complexity right you have a UI you have databases say but I have also build processes that invoke some of these steps but they are all at skill right that it ask you questions it runs the number based on a Python script and so on so my question is more like where you see the boundaries between like having a skill that does all these creating like a separate tool or have have you tried that?
</details>

>> 当然。是的，完全没错。我认为这同样非常类似于我们刚才所说的关于你的用户群体以及你所追求的可复现性：也就是当这件事变得足够关键，以至于非确定性方法所带来的权衡取舍已经……我们不再愿意承担这些取舍时。我通常把基于 prompt 的方式（比如 skill 命令）描述为：“嘿，请遵循所有这些指示，千万不要犯错，拜托拜托拜托。”因为情况确实就是这样，对吧？我们正在给机器提供大量组织非常严密的指令，并寄希望于它去执行这些指令。如今的 agent 已经足够出色，它们可能在 99% 的时间里都能执行你的指令。但是，剩下的 1% 呢？如果出现一个导致运行失败的极端边界情况呢？如果你把它分发给内部用户，而你的内部用户在其用户级别的 cloud.mmd 文件中写了一条与你要求 agent 做的事情相冲突的指令呢？

<details><summary>Original English</summary>
>> Absolutely. Yeah, absolutely. Um I think it it again very similarly to to what we were saying about your user base and the reproducibility you want is when this becomes critical enough that the tradeoffs we are getting with the nondeterministic approach are are not uh we're not willing to have them. I usually describe the the skill command like the the promptbased approach as hey please follow all of this and make no mistakes please please please like again because this is what's going on right we are we are giving a a lot of organized very well organized instructions to a machine and hoping that it it will perform these instructions agents are good enough nowadays they will probably perform your instructions 99% of the time. Uh, but what about that 1%? What about an edge case that makes things don't work? What about if you distribute this to your internal users and your internal user has a instruction in their user level cloud.mmd file that goes against what you are telling your agent to do.
</details>

你明白我的意思吧？也就是说，当你开始将其分发给许多用户和使用场景时，事情可能会在你无法预测的地方变得一团糟。然后你会发现自己……在 Moz 我们有一个内部的 agent 扩展贡献机制，多个团队可以在里面——“嗯，我碰到了一个对我管用的东西，让我把它分享到内部”——比如各种插件、skill 等等。非常频繁地，我们在审查指令时，会看到各种试图打补丁的内容：“如果用户试图做这件事，回复用户说该 skill 不支持那个”。你看，这又是在试图去弥补很多东西，而利用确定性——我所说的确定性是指后端代码，比如 Python 或无论我们使用的是什么——harness 开箱即用就能解决并覆盖这些问题，或者……

<details><summary>Original English</summary>
You see my point is like um there are many when you when you start distributing it to a number of users and use cases things can get messy in places you are not able to predict and then you can find yourself I we have a at Moz we have an internal like contribution for agent extensions where multiple teams can well I've come across something that works with me let me share it internally um so like plugins skills and so on and very frequent ly we when reviewing the instructions we see things trying to cover for if the user tries to do this tell the user back that this skill does not support that and you see like it's again trying to cover for many things that with the determinism and when I say determinism is the backend code like the python the whatever we are using uh that the harness provides that out of the like out of the box is something we can cover or
</details>

>> 还有人有其他意见或问题吗？

<details><summary>Original English</summary>
>> anyone has any other comments, questions.
</details>

>> 好的。

<details><summary>Original English</summary>
>> All right,
</details>

>> 太好了。

<details><summary>Original English</summary>
>> cool.
</details>

### 财务领域的模糊性与构建信任的 Harness

>> 那个小玩意儿在哪儿？[笑声] 算了。算了。算了。好，好，好，好。往前跳。往前跳。啊，真有意思。呃，我本来想开个玩笑的，但我翻页按得太快，完全错过了。但财务很有趣。我说有趣，是因为我觉得它是一个极其吸引人的领域，而且还有一个额外的优势：过去财务感觉就像是纯粹摆弄电子表格，非常乏味的工作，这里加加数字，那里弄弄公式之类的。如果你问任何会计师，它完全关乎创造力和解释，因为他们会想出最千奇百怪的东西。我认为面对这种程度的模糊性，AI 真的非常擅长，非常非常擅长。你有电子表格的某些部分，然后你意识到某些现金流不太对劲，因为一部分收入被归纳到了一个月后，你就会觉得：“啊，这就是创造力。”

<details><summary>Original English</summary>
>> Where is the thingy? [laughter] Never mind. Never mind. Never mind. Cool, cool, cool, cool. Skipping ahead. Skipping ahead. Ah, fun. Erh, I wanted to make a joke and I completely missed it for clicking this thing too quickly. But finance is funny. And I say funny because I find it to be a super interesting domain with a the added advantage that back in the day finance felt like just working with spreadsheets, very like boring work, adding numbers here and there, formulas, whatever. If you ask any accountant is all about creativity and interpretation because they will come up with the weirdest things and I think in that level of ambiguity AI is really good really really good you have some bits that are the spreadsheet and then you realize some of the cash flow didn't quite make sense because some of the revenue was attributed a month later and you're like ah creativity.
</details>

所以，正因为我们身处财务领域，取决于你的心态如何，你可以把一个问题看作是非常简单的事情，直接让一个 agent 在 10 分钟内搞定；你也可以看待它的本来面貌：它实际上是必须在 100% 的时间里可靠运行的事物，与字里行间大量的解读和创造性自由的混合体。

<details><summary>Original English</summary>
So because we are in this space of finance and depending on where is your mind mindset at you could look at a problem as something very simple that you can just get an agent to fix within 10 minutes or you could look at it as it actually is which is a mixture of things that need to run reliably 100% of the time and a lot of interpretation and freedom of creativity in between the lines.
</details>

所以是的，抱歉，这个笑话讲得很糟糕，但这就是我想表达的核心意思。归根结底，你对 harness 的设计必须是有意为之的，以此来提升信任度。

<details><summary>Original English</summary>
So yeah, sorry, very poorly delivered joke, but that's what I wanted to go through. Uh, and the bottom line being the design of your harnesses needs to be intentional to increase trust.
</details>

不要假定说：“哦，因为这是在 AI 上运行的，所以它就会像那句话说的有 200% 的准确率。”它很可能做不到，除非你设计好所有的机制，使得无论运行什么流程，你都知道自己在某种程度上可以信任其结果。是的，模型会变得越来越好。我们在过去 6 到 9 个月里所看到的简直不可思议，事情发展之快甚至让我感到有点头晕目眩，但它们仍然必须去赢得信任。它并不是 100% 正确的；当我们谈论金钱时，即使是 1% 的错误，有时也是一大笔钱。所以是的，我们直接跳到了提问环节，但如果其他人还有什么问题的话……

<details><summary>Original English</summary>
Don't assume that oh because this is running on AI is going to be what was the the quote 200% accurate. It will likely not unless you design all the mechanisms so that whatever process runs you know you can trust the results to a degree. Um and yeah models are going to get better. We have seen the last six months nine months in saying I'm getting a little bit of whiplash even with you know how fast things are going but they still have to earn the trust. it's not a 100% right and in when we're talking about money 1% wrong sometimes it's a lot of money so yeah we kind of skipped into the questions but if anyone has anything else
</details>

>> 对，就非常简短地问一下，比如在 UI 中，你是如何体现信任的？比如你直接要求它“展示你是如何计算这个的”，还是它会向你展示代码？

<details><summary>Original English</summary>
>> yeah just really quick like in the UI how do you demonstrate trust like you just ask it show me how you calculated this or does it show you the code
</details>

>> 能展示一个例子吗？比如你是怎么证明它的？

<details><summary>Original English</summary>
>> can you show an example like how do you prove it
</details>

>> 我们的初衷是让它成为所有东西的聚合体现。框架中的所有步骤都应该让人感觉到：“哦，我知道这来自哪里，我知道这是作为代码运行的，我知道这是经过测试的。”所以它本应是一种让人沉浸其中的体验，感觉“这是值得信赖的”。但这同样只是我们提出的一种实现方式。

<details><summary>Original English</summary>
>> the intent was that it was a aggregation of everything so All the steps in the framework should have felt like oh but I know where this is coming from but I know this is running as code but I know this is tested. So it should have been an experience to kind of like immerse into this feels trustworthy. But again it's one implementation we came up with.
</details>

>> 所以并不是特别直接。

<details><summary>Original English</summary>
>> So not not super direct.
</details>

>> 是的。但我认为核心收获在于：在任何时候，都不会有单一的一件事能够奏效并彻底赢得用户的信任。所以我认为，对某些人来说验证会更重要；而另一些人则更为怀疑，他们想看到具体的计算过程和数字等等。因此，我再次认为，这个流程能够引导并覆盖各种可能的可能性。

<details><summary>Original English</summary>
>> Yeah. But I think the the takeaway is there won't be a single thing that will work to earn the user's trust at any point. So I think that's for some people the verification will be more important. Some others are a bit more skeptic and they want to see the actual calculations and numbers and so on. So I think again that the process guides and covers for a multitude of u of possible possibilities.
</details>