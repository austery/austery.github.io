---
author: AI Engineer
date: '2026-04-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CS5Cmz5FssI
speaker: AI Engineer
tags:
  - token-maxing
  - software-engineering
  - ai-productivity
  - developer-experience
  - tech-trends
title: AI 驱动下的软件工程变革：Token Maxing、生产力与未来角色
summary: 本次对话深入探讨了“Token Maxing”现象，即大型科技公司如何因绩效指标而驱动员工大量使用 AI 工具，以及 AI 如何重塑软件工程师的角色和期望。对话还触及了大型科技公司在 AI 基础设施上的巨额投入、工程师管理模式的演变，以及 Gergely Orosz 分享了他创办 "Pragmatic Engineer" 的历程和见解。总体而言，AI 正在以前所未有的速度加速行业变革，推动工程师能力边界的拓展和企业战略的调整。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Gergely Orosz
  - Brian Armstrong
  - Thomas Dunca
  - Mikuel Parkin
companies_orgs:
  - Meta
  - Microsoft
  - Salesforce
  - Uber
  - Shopify
  - GitHub
  - Anthropic
  - Coinbase
products_models:
  - GPT-4.5
  - GitHub Copilot
  - Cursor
media_books: []
status: evergreen
---
### Token Maxing 现象及其动因

**主持人**: 好的。我猜在座的大多数人都，举手示意一下，有多少人订阅了 Pragmatic Engineer？
<details>
<summary>Original English</summary>

**Host**: All right. I'm going to assume most of you, show of hands, who subscribes to Pragmatic Engineer?

</details>

**Gergely Orosz**: 天哪。
<details>
<summary>Original English</summary>

**Gergely Orosz**: Oh my god.

</details>

**主持人**: 他，呃，无需介绍。那我们直接开始吧。嗯，什么是 Token Maxing，在座的各位都应该做吗？
<details>
<summary>Original English</summary>

**Host**: He is, uh, he needs no introduction. Then let's get right into it. Um, what is token maxing and should everyone here be doing it?

</details>

**Gergely Orosz**: 我在一周或一周半前首次听说了 Token Maxing，有些人已经做更久了。我大概三天前发推说“哦，有这个 Token Maxing”，然后你又会在社交媒体上看到它，我的私信（DMs）开始爆炸式增长，都是来自大型公司的员工。我不想点名，但像 Meta、Microsoft 以及其他一些公司，比如 Amazon（这里指亚马逊的荷兰分部，即 Bol.com）以及更多公司。每个公司关于人们为什么这样做，以及他们是否喜欢，是否认为这是好事的故事都有点不同。但有几个共同的主题。

一是，在这些大公司里，Token 的输出在某种程度上是被衡量的。要么有排行榜，要么有方法可以查看你的同行。以 Salesforce 为例，你可以查看公司里每个人在 AI 上的花费。你可以在某个工具里搜索，它会显示这个人花了多少钱在 AI 相关的 Tokens 上。首先，有这个数字，然后是科技行业的不确定性，对吧？我们正在听到裁员的消息，比如 Block 那样的公司大规模裁员。而且，我意思是，无论人们花多少 Tokens，他们都被解雇了，这和 Token 数无关。但人们开始思考，这是否是绩效评估或晋升的一部分，或者其他什么？答案是“某种程度上”。

在 Meta 内部，我和一些经理谈过，在绩效评估中，他们有一个数据点，这是众多数据点之一，就像代码 diffs、工作影响或代码审查一样，衡量一个人有多大帮助。但就像任何数据点一样，他们有时会把它拿来使用。所以，通常来说，就像任何数据点一样，它可能会被武器化。比如，一个表现不佳、影响力低且 Token 数量少的人，显然根本没有尝试。而一个表现优异、影响力高且 Token 数量多的人，显然是在创新，这是有益的。

所以在这些公司里，我跟 Meta 的很多人谈过。再次强调，这不代表 Meta 的全部情况，但他们有一个排行榜，人们在那里展示自己，拥有大量的 Tokens。很多工程师感到害怕、担忧，所以他们开始 Token Maxing，试图产生 Token。我听到的（二手）故事是，例如，他们不再阅读文档，而是让 AI 代理总结文档并提问，即使 AI 回答得不好，但他们的 Token 计数会增加。人们只是不想落在 Token 数量的底部 25% 或 50% 之列。

在 Microsoft 也是一样，也有一个排行榜。我和人们交谈，他们说“太离谱了”，有些人只是运行自主代理来生成垃圾代码，说实话，仅仅是为了让那个数字上去。有时情况会变得很荒谬，因为 Meta 曾经有过这个排行榜，在一篇文章出来后就废除了它，因为它看起来很糟糕，他们就关闭了。但人们仍然在 Token Maxing，因为他们认为“这可能会发生，但你知道，我们是工程师，别忘了这些是高薪工作，对吧？你真的不想因为一些愚蠢的事情而失去工作，比如你的 Token 数量不够”。

但 Salesforce 有每月最低花费目标，我记得大约是 175 美元。所以人们会，你知道，在月初就 Token Max，以达到这个目标。所以，这很奇怪。它最初只是个笑话，几个月前，Token Maxing 真的只是人们疯狂地享受这个东西，并构建酷炫的东西。但在很多公司，它已经变成了一种文化上的怪事。所以，这是一个奇怪的时期。

我记得以前，当早期开发者生产力工具出现时，比如 Velocity 和 Pluralite Flow，它们会衡量代码行数和 QPRs（季度绩效回顾）数量。我们知道那很愚蠢，公司也会照此优化。但现在，像 Meta 和 Microsoft 这样顶尖的公司，竟然在激励人们做一些愚蠢的事情。
<details>
<summary>Original English</summary>

**Gergely Orosz**: So I I heard about token maxing a week ago or like week and a half ago first and you know some people have been doing it for longer and I tweeted about it I think three days ago saying oh there's this token maxing and again you see it on social media and my DMs were blowing up from from people at large companies. I don't want to name names but like you know Meta, Microsoft uh some so some some other ones as well like uh the likes of and and and so so many more and the story is a little bit different every at every company on why people are doing it and whether they like it or whether they think it's good. But there's a few a few common themes.

One is token output at these larger companies is measured in in some way. There's like either a leaderboard or there's a way to look up your your peers. Salesforce, for example, you can check the spend the the money spent that every every person at the company did. You can like search in a tool that someone built and it shows how many dollars they spent on on AI related tokens. And you know, first there's this number, then there's this uncertainty on in the tech industry, right? We're kind of hearing layoffs, like massive cuts at the likes of block. And I mean there like no matter how much tokens people spend they were let go independent of this but people start to think like does is it part of performance evaluations or promotions or all that and the answer is kind of. So inside of meta I talk with managers and in the performance evaluation they have this data point which is one of many data points right the same way as as like diffs or impact or or code reviews of how helpful this person is but they do just like with any data point they sometimes pull it in and use it. So typically in just like any data point it can be weaponized. So like a low performer with low impact and a low token count clearly not even trying. So, and a high performer with high impact and high token count. Clearly, that's innovating and this must be doing good.

So, inside of these companies specifically, I talked with a lot of people at at Meta. And again, this is not representative 100% of Meta, but they had this leaderboard where people showed up and they have like massive amounts of tokens and a lot of engineers got just scared, worried, so they started to token max to try to generate tokens. stories that I've heard first or well secondhand from these people who who who told me firsthand is for example instead of reading the documentation I will ask the agent to summarize it for me and ask questions even though it doesn't do a good job answering it but my token count goes up people just want to not be in the bottom 25% or bottom 50% for token count. where these things are measured inside of Microsoft again there's a leaderboard and I'm talking with people they're like it's ridiculous like how some people are just running autonomous agents to build junk honestly for the sake of having that number go up and and sometimes it gets ridiculous because like inside of Meta they had this leaderboard they got rid of it after an article came out and it looked amaz like just just like closed it down. that people are still token maxing by the way because there's this this thinking that it might have gone but you know we're engineers and don't forget these are highp paying jobs right that like you don't really want to lose a job over something stupid as like you didn't have INF token count and that's how it feels but inside Salesforce there's a target of minimum spend per month like I think it's like $175 between the things so like people are like again you kind of like you know beginning of the month like just token max to get there so it's it's it's weird and it started as a joke earlier like a few months ago token maxing was really just people like going crazy and enjoying this thing and building cool stuff. But it's kind of turned into in a lot of companies I think it's just a culturally weird thing. So it's a weird time to be in cuz I remember lines of code used to be when when early uh developer productivity tools came out like velocity and pluralite flow. They kind of measured lines of code and and number of QPRs and we know that was stupid and people kind of optimized for that at companies that did it. But it's it's almost like what now it's the top running companies like Meta and Microsoft who are incentivizing people just to do just stupid stuff honestly.

</details>

**主持人**: 嗯，这些真是离奇的故事。你鼓掌支持的其中一点，值得我们再深入聊聊。嗯，我喜欢和你聊天，订阅你的通讯，是因为你基本上会匿名化这些来自真实事件和真实例子的故事。嗯，为什么，呃，现在这一切仍然值得这样做呢？考虑到“好心的定律”（Goodhart's Law），就是任何被衡量的东西都会被滥用。考虑到所有这些缺陷，它仍然值得吗？你知道，AI 整体上是否仍然让我们更快？就像，Token Maxing 的成本，即使有所有这些荒谬的例子，它是否仍然是净收益？
<details>
<summary>Original English</summary>

**Host**: Yeah, those are wild stories. And one of the things you're clapping for that deserves another full conversation. Uh, one of the things I like about talking with you and subscribing to your newsletter is that you basically kind of anonymize all these stories from from real incidents and real examples. Um, why is it that, uh, is is it still worth it right with all the flaws, uh, you know, when you have good heart's law like what whatever gets measured gets, uh, sort of abused with all the flaws, is it still worth it, you know, is, is, is AI basically still making us faster overall, like the cost of token maxing is still with all these, like really ridiculous examples, is it still net worth it?

</details>

**Gergely Orosz**: 是的，别忘了，Token Maxing 之所以可能存在，是因为，让我们回到六个月前，当时我在一个 CTO 晚宴/会议上，很多 CTO 级别的技术人员聚在一起。那是在阿姆斯特丹，我们有很多人在那里交谈。当时，荷兰的“亚马逊”（指 Bol.com，荷兰最大的电商公司）的一位 CTO 说，“嘿，我有个问题，我团队里的工程师对 AI 非常怀疑，他们不怎么用它。”别忘了，这是在 Opus 4.5 和那些模型出来之前。它们没有那么高效。我们已经有了 Cursor，他们还在使用。他们说，“他们根本没怎么用它。”

在我们现有的代码库上，对吧？然后，旁边荷兰国家银行的负责人说，“哦，我们没有那个问题。我们的工程师正在使用它，因为我们的使命是监管这件事。所以，我们需要理解它。”他们更有动力。当时，一些经验丰富的工程师还在观望，因为如果你有一个现有的代码库，然后使用 AI Cursor 或类似工具，它可能有点用，即使有。然后这些工程师就想，“我为什么要用一个工具，如果它不能帮我重构，找不到 bug，做不到我需要的事情？”

然后，领导层看到他们并没有真正使用它，并且他们听到像 Anthropic 这样的公司说，他们用 Claude 编写了大量代码，收入正在增长。所以，这些领导层可能在混淆相关性和因果关系，但他们想，“嗯，我们应该更多地使用它，因为好事情可能会发生，如果我们不使用，坏事情也可能发生。”所以，所有的目标设定和衡量，其实是来自领导层想要“我们希望工程师们使用该死的 AI”。我不在乎是什么。这有点像一种推动，我们知道这不好，但“总比他们不用好”。

最好的例子是 Coinbase，CEO Brian Armstrong 发了一封邮件说，“每个人都需要加入进来使用 AI 工具，如果一周内有人不使用，我就会找他谈话。”然后，我记得一周后的周六，他解雇了一名工程师。你知道吗？这又是一个高薪工作，我们说的是年薪 30-40 万美元的基础工资，外加股票期权等等。他们收到了信息，每个人都开始使用了。

你回到你的问题，一方面，这是一种推动。看，我觉得这有点……可能会有争议，但你有没有想过，为什么大公司喜欢进行那种代码风格面试、算法面试，这和实际工作毫无关系？我们知道事实就是这样，并且对此有很多批评，他们已经做了 20 年了。但关键是，它会筛选出特定类型的人。它会筛选出那种聪明、愿意忍受绝对的 [口误，可能指 BS 或其他] 来获得这份工作的人。这个人，你知道，他们会提前两个月学习 AI，花两三个月学习代码，这在工作中毫无意义，但你还是做了。你进去了，这个人会忍受 [口误，可能指 BS 或其他] 来保住工作。

所以 Token Maxing 发生在大型公司，人们也在忍受这种 BS。看，他们中的很多人很聪明，他们会从中最大化利用。有些人会构建酷炫的东西。我认为这是大科技的现实。所以，我们正处于一个奇怪的境地，大科技公司有点比初创公司更奇怪，你知道，初创公司没人关心 Token Maxing。他们关心的是构建东西，你知道，使用任何有意义的东西。人们会关心成本。

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Gergely Orosz**: Yeah, so don't forget like the reason token maxing is probably a thing is like let's just go back to six months ago where I I I was at a I was at a CTO like dinner conference whatever like a bunch of CTO's gather CTO level people this this was in Amsterdam and we had like like a bunch of people and there we were talking and and one of the CTO's like the the the Amazon of the Netherlands there there's a e-commerce company was saying like hey like everyone like I have a problem like engineers on my team are really skeptical of AI and they're not really using it. The AI tools, don't forget this was before Opus 4.5 and those models were were out. They were not as as productive. We had uh we we already had a cursor and and the like and they subscribed. They're like they're just not using it that much on existing code bases, right? And and next to them uh the head of the Dutch National Bank said like, "Oh, we don't have that problem. Our engineers are using it because our our mission is to regulate this thing. So, we need to understand it." And they're kind of motivated. And there was this time where experienced engineers were kind of holding off because if you had an existing codebase and use AI cursor whatever on it was mildly useful if that even and these engineers were like why should I use a tool if it doesn't help me refactor it doesn't find the bug it doesn't do what I need to do and leadership saw they're not really using it and they kept hearing you know the likes of Antrophic for example was already saying how they're writing a lot of their code with with cloth code uh and it just keeps increasing and andropics, you know, like revenue is going up like this. So those leaders are kind of they might be confusing correlation and and and you know, like which one comes first, but they're like, well, we should be using it more because probably good things will happen and thus bad things will happen if we don't use it. So the whole targeting and measuring things, it actually came from leadership wanting, we want our engineers to use faking AI. I don't care what it is. And it it was a bit of a push like we know this is bad but it's it's better than them using it. Best example is Coinbase where uh Brian Armstrong the CEO just like fired an engineer or he sent an email saying everyone like needs to get on board and use AI tools and whoever doesn't use it in a week I'll have a conversation with them and then I think a week later on Saturday he fired an engineer and you know like this again high paying job like we're talking base salary like three 400k,000 per per year uh and then both equity and everything on top of it like they got the message everyone just started to just you know like use it and you back to your question. So on on one there there's a push and look I feel it's a little bit like this is going to be controversial but have you ever wor wondered why big tech loves to do lead code style interviews algorithmical interviews which have nothing to do with the job and and we know it's the case and there's a lot of criticism for this and they've been doing this since since like 20 years but here's the thing it selects for a specific type of person. It selects for the person who's smart and willing to put up with absolute [inaudible] to get the job. And this person, you know, they will study two months pre AI, two months or three months of lead code, which again makes no sense on the job, but you do it. You get in there and this person will be putting to put up with [inaudible] that makes absolute no sense to keep the job. So token maxing happens at large companies and people are putting up with this BS. And look, a lot of them are smart and they will make the most of it. some of them will build cool stuff. Um it's it's the reality I think of big tech. So we're in this weird place where big tech is a bit weirder than startups where you know no one cares about tokenaxing. They care about like just building stuff and you know use whatever makes sense. Don't people will care about the cost.

**Host**: Yeah.

**Gergely Orosz**: But going back to your question like like you know like is is it making us productive as as a whole like individually it's it certainly is and as teams we're kind of like a bit question mark because we should be moving faster and there are a few companies that do. Entrophic is a good example, but a bunch of companies are like not it's it's it seems it's hard to retrofit all this AI into like the way we have been working.

**Host**: Yeah. Uh, one of my favorite studies from last year was the meter study where they uh did a blind test of uh people and their expectations of productivity, right? And basically the the end result was they felt 20% more productive, but their demonstrated results was actually they were 20% less productive on average.

**Gergely Orosz**: Yes. But that that study was very interesting because they

**Host**: it was very small sample size.

**Gergely Orosz**: It was 30 people and there was one outlier uh who actually was way more

**Host**: Anthony we we interviewed him on the

**Gergely Orosz**: pod. Yeah.

**Host**: Yeah. Yeah. So he was the one productive AI engineer

**Gergely Orosz**: but anyway, so uh, actually my theory is that uh, something that I've seen on my team is that I've been enabling coding agents for the rest of my team who are non techchnical right and uh, you as the engineer may not be more much that much more productive because and you can be more productive if you uh attend AIE but uh, if you actually enable your non-coding uh, your your non-coding collaborators to code, actually they are more productive because they don't have to wait for you right? And that's that like unlock of like oh suddenly you have serverless developers basically uh, and I think I think that's that organizational coding thing is different than studying pull request level productivity for the individual developer.

**Gergely Orosz**: yeah, and and the thing that still I still remember to this date I I talked with Simon Willis I think in 2024 so two years after Chad GPT came out and he was Simon Wilson top commenter on hacker news or he's he's

**Host**: that's his that's not his title man top commenter on hacker What the [inaudible]

**Gergely Orosz**: No, he's

**Host**: creative, Django, top blogger. Yeah. Uh, prompt injections. Uh, yeah.

**Gergely Orosz**: Yeah. He's actually not talk. I'm sure he's the most submitted block cuz he blocks so much like like and he's

**Host**: but he told me back then he said like this thing AI is is just so hard to to get good at. He's like there's no manual. And he's like, I've been doing it back then for two years and I'm still I'm still figuring out what works and what doesn't. I keep changing my workflows. And I think that's something that is a bit hard for us. Two things about AI that for any of us engineers is hard to understand. One is it just takes a long time to get good at it and you need to keep doing it. And the second thing is understanding the theory will not make you better at using the tools which is an absolute mind [inaudible] honestly because we're so used to you know you understand how the compiler works, how assembly works. Okay, you will now be more efficient if you want to write low-level code because you know how it works. But what with these things I mean you can of course it's helpful to understand how how the the architecture underlying works attention the different the the different probability sets etc etc but it will not help you get a sense for how you can use it and then once you figure out how you can be more productive if you're if you're inside of a team again it kind of breaks and you have to relearn again but but the more effort you put into it it like it's clear that it's it's working it's helpful and I think it it's the teams I'm seeing and getting more value out of it. Low ego, open to learning, open to leaving your priors behind. The word priors I have not used forever and I feel we're in this stage where like just just leave your priors behind. Just have an open mind like don't leave your experience behind but you know be open to it.

**Host**: Yeah. Zooming out a little bit. How is the role of the software engineer changing?

**Gergely Orosz**: I think it's always this was always coming but AI is just just speeding it up. uh even before AI a few it's interesting I see like startups in many ways venture funded startups are kind of front running what the industry will be catching up because venture funed startups are about fast growth um doing mo moving fast with smaller teams because smaller teams mean smaller comps even preai so a lot a lot of these venture funed startups start to expect a lot wider range of roles from engineers for example devops as a whole inside VC funded companies from the mid210s every engineer was kind of like responsible for the code they deployed but like more traditional companies they had more money more sorry more less pressure they kind of have dedicated devops teams and some of those things so in in the industry like the software engineer is now becoming like the kind of the tester role has collapsed into software engineer we most companies don't have dedicated testers very very few do devops collapse into here uh and now we're starting to have the product role also starting to come so a lot of companies even like in 2022 before AI starts to hire for product engineers that's happening faster and I think the the last push that AI is doing is even for early career engineers there's a lot more seniority expected or or senior like things planning about things knowing about the business so I I I think the role is expectations are are higher teams are also getting smaller everywhere I talked with someone at John Deere 200 person uh 200 year old company sorry uh you know like they do tractors and and all all that stuff and and inside of that company, one of their their VP of engineering was telling me how they're actually seeing that their two pizza teams are now just one pizza teams inside of that company. It's the reality partially because of these tools.

**Host**: So, my joke used to be I am a one pizza team because I eat a lot of pizza, but uh, depends how much pizza you eat.

**Gergely Orosz**: Uh, there's so I'm sorry to interrupt. I don't know if I cut you off in some critical point. Uh, there's a comment saying I've heard it twice even among this audience where a lot of people are saying that oh uh, you're no longer an engineer, everyone's an engineering manager now and you've been an engineering manager and I wonder if you agree with that or if you have a different take, you know, because basically you're the the the the common analogy is that you're no longer a software engineer, you're just managing engineering agents, right?

**Gergely Orosz**: Yeah, if you've been a manager before that is an absolute [inaudible] so so here here's the thing the like Yes, you are a manager without all the things that no one wants to become a manager for the the when you become an engineering manager. Hands up if you are or have been an engineering manager, right? Hands up if you actually if you've not been and you want to be one

**Host**: about 15 20%.

**Gergely Orosz**: All right, you come and talk to me afterwards. I I'll tell there's a hand up there. I'll talk you out of it. So, so what you think you become an engineering manager to like help people's career, maybe have higher salary, higher impact, all you know there can be a lot of dynamics but the reality is is is you you become more removed from the product and you have to deal with people problems and the thing with with agents is you don't have to deal with people drama, people problems, conflict between your team. I mean unless the next generation of agents starts to fight with each other. I think that'll be something but you actually you you do have to orchestrate but it's more like a tech lead role or or or experienced engineer where where you're like mentoring uh, mentoring engineers but you don't have the people management. You don't need to worry about the personal problems. So it's actually a lot more kind of empowering. And I was talking with uh, the podcast was was just out yesterday with with DHH uh, creator of Ruby on Rails who said, you know, people told him like, okay, it's it's like managing things and he's not excited about managing agents, but it feels it's more like a mech suit where you have like you can do seven things at once, you can do a lot faster and you're in control and that's more what it feels like. So there's orchestration, yes, but it's very different to management. And also the the really really bad thing or honestly shitty thing about management if if you make it into management which makes it hard also rewarding later when you you tell yourself at least this thing is you start a project with all these people under you you know congratulations you've got 10 people wonderful and you start a project and in 6 months you will see some results of the decision that you made with agents it's just so much faster so the the feedback loop is faster so I I think it's it's not much of it except for the orchestration and and and for that everyone's going to have their own flavor. Some people will will have the tendency to like run multiple agents and they're good at this or we good at it. Some people just do like two agents. Michelle Hashimoto, I interviewed him. He has two agents. He always has one agent running. No, he has one background agent that he doesn't. That's it. He's like two is enough for me. Great.

**Host**: Yeah. Yeah. Uh, we're figuring out the patterns. Um, uh, I want to hit you on large tech infra. uh, this is something that I think both of us are very excited by by uh, good infra which is a very niche uh, interest. What are you seeing?

**Gergely Orosz**: it's wild to see how much of the so I said that from externally a lot of companies a lot of big tech companies especially the ones are spending a bunch on AI and have platforms and all that you're not seeing too much like more come out like Uber is a good example I'm not seeing too many more features come out of Uber or new products launcher and they're like but what's going on they are really investing in AI but when you look inside there's a whole lot of buzz they are rebuilding their complete IM infra you know they're and I'm not talking about they're buying cursor or or cloud code or all that they're doing that as well but they're completely they're building their own own custom background coding agents that is integrated into their monor repo they are are having uh, their own MCP gateway that is is now integrated into service discovery their on call tooling is being retoled their internal code review system is like like categorizing based on risk. They are like and Uber is one example but all everyone else Airbnb intercom meta Microsoft even midsize companies are just building so much internal improp and I was asking to myself like why on one end this feels like such a waste but when I worked at Uber for four years I realized they spend so much on on internal platform there's two reasons one is honestly it's a it's a lowrisk way to get good with AI uh, to be hands-on and these companies want to be hands-on but maybe you shouldn't start with shipping AI features no one wants into your codebase. Second of all, because these these companies have such so much code that never fit in a context window, by building custom solutions and just basic basic wagons, that kind of stuff, they will have better results than off-the-shelf vendors. So, they already have a win. And number three, honestly, is anything that has AI in it gets funded. So, there's this joke of if you're in the developer platform team and you're asking for more headcount, like good luck with that. Oh, developer platform. Oh, but say that you want to get two extra headc count for agent experience. Done. H. So, so there's that part as well. But, but all

**Host**: agent experience is just a CLI

**Gergely Orosz**: pretty much. But all these come inside there's so much buzz and so much work. Everyone's building their own custom system. So, I'm kind of wondering how long this will take, but I think for next year this is going to happen. So, if you either have friends or if you're work if you're working at a company, you'll see. But talk with with friends at other large companies and you will probably see you are all building the same thing. If you're at a large company and you're not already building an MCP gateway, what are you even doing?

**Host**: Yeah. Um, actually a lot of these topics are exactly the things I cured for tomorrow. Uh, it's just fantastic to have you as the closing keynote for today because uh, it's, it's like an appetizer for tomorrow. We have talks about MCP gateway and all these sort of AI architecture and infra things and I do think like uh, infra like taking AI infra seriously as a company is uh, very mis not that well un understood and right now you just kind of learn by example from people because there's not really like a textbook or anything like about it. So the way I think about this because again from if you just kind of step out and we love to criticize big tech of how they're wasting money here and there and by the way we love to criticize Google and I'm kind of thinking to myself like hang on what if Google ex actually executed well like do we want that and you know they would kill all the startups but but what they're doing makes makes sense and Shopify is an example where I'm like huh I'm starting to get why it makes sense to do all this stuff. So Shopify in 2021 they were the first company to have access to a GitHub copilot. What happened is the the head of engineering fartoir heard about GitHub copilot being developed internally inside of GitHub and he pinged Thomas Dunca the CEO of GitHub at the time and said hey Thomas I heard you guys are doing C-pilot and he's like yeah we are it's internal. He's like I I'd like to get access to it. He's like yeah but it's not for sale. He's like no no no you don't understand. I I didn't ask if it's for sale. we would like to roll it out to all of Shopify and in return we will give you feedback for 3,000 people for you know as honest feedback all the time and so they got it a year before it was out anywhere and they incurred a lot of churn. It wasn't that great initially and and they went through all of this stuff and then Shopify was the first company to on board to like a bunch of other tools and they gave unlimited budget and they're spending so much time ironing out bugs. But the reason they're doing it, this is what like made me click is they are trading off churn and expense and spending a lot more money to be at the forefront of this. They are a few months ahead or six months ahead of their competition and for them it's worth it. It's not worth it for anyone else, right? If you're if you're at a company where your business is like something something physical and you don't care like yeah, just just wait out it it'll come. But for a lot of us in the tech industry this turn is worth it. Plus what Farhan told me is like because he actually told me he's kind of worried about the cost now. But he was like look like it's still worth it because if it would look silly if I said you cannot have these tools, how would I hire the best?

**Host**: So it's it's innovation, recruitment and it kind of makes sense when you think about it. And the weird thing everyone is doing it at the same time. So it looks silly but it, it's rational.

**Gergely Orosz**: Uh, my next podcast is with Mikuel Parkin the CTO of Shopify and uh, the sheer amount of machine learning that they do and infra that they set up for their customers makes me want to be a customer. You know, that's that's like the best uh, endorsement I can give. Um, I'm going to get meta a little bit and talk about pragmatic engineer. Uh, you and I kind of startedish in COVID. Uh, you just left Uber. Uh, how has it been growing? What, what are the main stats that you're proud of that uh, you'd like to share with the world? Yeah. So I I started pragmatic engineer I I I a joke that if it wasn't for co I I would probably never have started the this thing because what happened with co is uh, Uber had layoffs and most of the tech industry was doing great but Uber was not and my team uh, was hit by layoffs and then we we had to disperse the remaining people at other teams because our mission no longer made sense and it was just like a the morale was low my morale was low so I was like let me take a break. I wanted to write some books. Swix was writing his book the the coding career.

**Host**: Yeah, some of you have read it. I've met some of you.

**Gergely Orosz**: Yeah. and and that that's how we met there. And then uh, my plan was to write a book and then start start up some startup something something platform engineer control C, control V from what Uber was doing inside and that's actually almost all Uber su Uber startups it's it's amazing temporal is is is from there.

**Host**: if I by the way, if I did not start AI engineer I would have started platform engineer.

**Gergely Orosz**: that that would have been the industry conference.

**Host**: yeah, love it. And then I start I started the pragmatic engineer uh, a year after I left Uber. It was just an experiment. Um, I figured no one Substack was taking off. No one was writing about software engineering in-depth and I just acted all confident saying pretended that I I knew what I was doing. The first article was about Uber's platform and program split that no one had written about publicly before and it's a it's a free article. You can you can now check it out. Uh, and it was like when you feel product market fit, that's what I felt almost immediately. The first week before I published anything, just a confident Twitter post, I had 100 people pay upfront $100 for the whole year, which I was like, whoa, I have published anything. In six weeks, I was at a,000 people paying for this thing that didn't exist before, which was my old Uber base salary back back in Amsterdam. And it just kept going up. So like I I figured like when you find product market fit, this is like outside of like there's this rule like if you find product market fit, just keep doing what you're doing. So for me, I just kept writing that one article. I got all these interview requests, collaborations, podcast. I just said no to all of them because I knew the most important thing was to do what makes it successful, which is that one article. And later it turned into two articles. And for two years, this is all I did, just two articles. And after two years, I looked up and I was like, huh, like this is actually working. People like doing it. I like doing it. There's a future in that. And that's when I decided I actually want to turn this into a business that I don't burn out because for two years every vacation I went to I was working 50 60 hours. I was always thinking I was writing I I couldn't really let go. So I started to grow the team a little bit. Uh, I I Ellen Bird the first secondary researcher Ellen she's ex x ex uh.

**Host**: she's here right?

**Gergely Orosz**: Ellen's not here. Um, Jessica is who who just joined uh, later.

**Host**: Yeah.

**Gergely Orosz**: And then uh, so now it was two of us. Uh, and I started a podcast year and a half ago because I talked with so many people. I figured it was a bit of a shame to to not have it. So, the primatic engineer became the number one paid technology newsletter about four months after starting. It stayed there for three years. Now, semi analysis has

**Host**: Dylan versus uh, you guys. Um, yeah. No, congrats on your success. Uh, I think you're also a leading tech voice in Europe which I think you're sort of proudly sort of uh, upholding that over here which I would really wanted to feature. Thank you for your support for AIE. And uh, everyone thank you. Good. Awesome. Thanks, man.

</details>

### AI 对软件工程师角色的影响

**Gergely Orosz**: 是的，所以在 Meta，我和一些经理谈过，在绩效评估中，他们有一个数据点，这是众多数据点之一，就像代码 diffs、工作影响或代码审查一样，衡量一个人有多大帮助。但就像任何数据点一样，他们有时会把它拿来使用。所以，通常来说，就像任何数据点一样，它可能会被武器化。比如，一个表现不佳、影响力低且 Token 数量少的人，显然根本没有尝试。而一个表现优异、影响力高且 Token 数量多的人，显然是在创新，这是有益的。

在 Microsoft 也是一样，也有一个排行榜。我和人们交谈，他们说“太离谱了”，有些人只是运行自主代理来生成垃圾代码，说实话，仅仅是为了让那个数字上去。有时情况会变得很荒谬，因为 Meta 曾经有过这个排行榜，在一篇文章出来后就废除了它，因为它看起来很糟糕，他们就关闭了。但人们仍然在 Token Maxing，因为他们认为“这可能会发生，但你知道，我们是工程师，别忘了这些是高薪工作，对吧？你真的不想因为一些愚蠢的事情而失去工作，比如你的 Token 数量不够”。

但 Salesforce 有每月最低花费目标，我记得大约是 175 美元。所以人们会，你知道，在月初就 Token Max，以达到这个目标。所以，这很奇怪。它最初只是个笑话，几个月前，Token Maxing 真的只是人们疯狂地享受这个东西，并构建酷炫的东西。但在很多公司，它已经变成了一种文化上的怪事。所以，这是一个奇怪的时期。

我记得以前，当早期开发者生产力工具出现时，比如 Velocity 和 Pluralite Flow，它们会衡量代码行数和 QPRs（季度绩效回顾）数量。我们知道那很愚蠢，公司也会照此优化。但现在，像 Meta 和 Microsoft 这样顶尖的公司，竟然在激励人们做一些愚蠢的事情。
<details>
<summary>Original English</summary>

**Gergely Orosz**: So, inside of these companies specifically, I talked with a lot of people at at Meta. And again, this is not representative 100% of Meta, but they had this leaderboard where people showed up and they have like massive amounts of tokens and a lot of engineers got just scared, worried, so they started to token max to try to generate tokens. stories that I've heard first or well secondhand from these people who who who told me firsthand is for example instead of reading the documentation I will ask the agent to summarize it for me and ask questions even though it doesn't do a good job answering it but my token count goes up people just want to not be in the bottom 25% or bottom 50% for token count. where these things are measured inside of Microsoft again there's a leaderboard and I'm talking with people they're like it's ridiculous like how some people are just running autonomous agents to build junk honestly for the sake of having that number go up and and sometimes it gets ridiculous because like inside of Meta they had this leaderboard they got rid of it after an article came out and it looked amaz like just just like closed it down. that people are still token maxing by the way because there's this this thinking that it might have gone but you know we're engineers and don't forget these are highp paying jobs right that like you don't really want to lose a job over something stupid as like you didn't have INF token count and that's how it feels but inside Salesforce there's a target of minimum spend per month like I think it's like $175 between the things so like people are like again you kind of like you know beginning of the month like just token max to get there so it's it's it's weird and it started as a joke earlier like a few months ago token maxing was really just people like going crazy and enjoying this thing and building cool stuff. But it's kind of turned into in a lot of companies I think it's just a culturally weird thing. So it's a weird time to be in cuz I remember lines of code used to be when when early uh developer productivity tools came out like velocity and pluralite flow. They kind of measured lines of code and and number of QPRs and we know that was stupid and people kind of optimized for that at companies that did it. But it's it's almost like what now it's the top running companies like Meta and Microsoft who are incentivizing people just to do just stupid stuff honestly.

</details>

**主持人**: 是的，那些故事真是太离奇了。还有，你刚刚提到的其中一点，值得我们再深入聊聊。嗯，我喜欢和你聊天，订阅你的通讯，是因为你基本上会匿名化这些来自真实事件和真实例子的故事。嗯，为什么，呃，现在这一切仍然值得这样做呢？考虑到“好心的定律”（Goodhart's Law），就是任何被衡量的东西都会被滥用。考虑到所有这些缺陷，它仍然值得吗？你知道，AI 整体上是否仍然让我们更快？就像，Token Maxing 的成本，即使有所有这些荒谬的例子，它是否仍然是净收益？
<details>
<summary>Original English</summary>

**Host**: Yeah, those are wild stories. And one of the things you're clapping for that deserves another full conversation. Uh, one of the things I like about talking with you and subscribing to your newsletter is that you basically kind of anonymize all these stories from from real incidents and real examples. Um, why is it that, uh, is is it still worth it right with all the flaws, uh, you know, when you have good heart's law like what whatever gets measured gets, uh, sort of abused with all the flaws, is it still worth it, you know, is, is, is AI basically still making us faster overall, like the cost of token maxing is still with all these, like really ridiculous examples, is it still net worth it?

</details>

**Gergely Orosz**: 是的，别忘了，Token Maxing 之所以可能存在，是因为，让我们回到六个月前，当时我在一个 CTO 晚宴/会议上，很多 CTO 级别的技术人员聚在一起。那是在阿姆斯特丹，我们有很多人在那里交谈。当时，“荷兰的亚马逊”（指 Bol.com，荷兰最大的电商公司）的一位 CTO 说，“嘿，我有个问题，我团队里的工程师对 AI 非常怀疑，他们不怎么用它。”别忘了，这是在 Opus 4.5 和那些模型出来之前。它们没有那么高效。我们已经有了 Cursor，他们还在使用。他们说，“他们根本没怎么用它。”

在我们现有的代码库上，对吧？然后，旁边荷兰国家银行的负责人说，“哦，我们没有那个问题。我们的工程师正在使用它，因为我们的使命是监管这件事。所以，我们需要理解它。”他们更有动力。当时，一些经验丰富的工程师还在观望，因为如果你有一个现有的代码库，然后使用 AI Cursor 或类似工具，它可能有点用，即使有。然后这些工程师就想，“我为什么要用一个工具，如果它不能帮我重构，找不到 bug，做不到我需要的事情？”

然后，领导层看到他们并没有真正使用它，并且他们听到像 Anthropic 这样的公司说，他们用 Claude 编写了大量代码，收入正在增长。所以，这些领导层可能在混淆相关性和因果关系，但他们想，“嗯，我们应该更多地使用它，因为好事情可能会发生，如果我们不使用，坏事情也可能发生。”所以，所有的目标设定和衡量，其实是来自领导层想要“我们希望工程师们使用该死的 AI”。我不在乎是什么。这有点像一种推动，我们知道这不好，但“总比他们不用好”。

最好的例子是 Coinbase，CEO Brian Armstrong 发了一封邮件说，“每个人都需要加入进来使用 AI 工具，如果一周内有人不使用，我就会找他谈话。”然后，我记得一周后的周六，他解雇了一名工程师。你知道吗？这又是一个高薪工作，我们说的是年薪 30-40 万美元的基础工资，外加股票期权等等。他们收到了信息，每个人都开始使用了。

你回到你的问题，一方面，这是一种推动。看，我觉得这有点……可能会有争议，但你有没有想过，为什么大公司喜欢进行那种代码风格面试、算法面试，这和实际工作毫无关系？我们知道事实就是这样，并且对此有很多批评，他们已经做了 20 年了。但关键是，它会筛选出特定类型的人。它会筛选出那种聪明、愿意忍受绝对的 [口误，可能指 BS 或其他] 来获得这份工作的人。这个人，你知道，他们会提前两个月学习 AI，花两三个月学习代码，这在工作中毫无意义，但你还是做了。你进去了，这个人会忍受 [口误，可能指 BS 或其他] 来保住工作。

所以 Token Maxing 发生在大型公司，人们也在忍受这种 BS。看，他们中的很多人很聪明，他们会从中最大化利用。有些人会构建酷炫的东西。我认为这是大科技的现实。所以，我们正处于一个奇怪的境地，大科技公司有点比初创公司更奇怪，你知道，初创公司没人关心 Token Maxing。他们关心的是构建东西，你知道，使用任何有意义的东西。人们会关心成本。
<details>
<summary>Original English</summary>

**Gergely Orosz**: yeah, so don't forget like the reason token maxing is probably a thing is like let's just go back to six months ago where I I I was at a I was at a CTO like dinner conference whatever like a bunch of CTO's gather CTO level people this this was in Amsterdam and we had like like a bunch of people and there we were talking and and one of the CTO's like the the the Amazon of the Netherlands there there's a e-commerce company was saying like hey like everyone like I have a problem like engineers on my team are really skeptical of AI and they're not really using it. The AI tools, don't forget this was before Opus 4.5 and those models were were out. They were not as as productive. We had uh we we already had a cursor and and the like and they subscribed. They're like they're just not using it that much on existing code bases, right? And and next to them uh the head of the Dutch National Bank said like, "Oh, we don't have that problem. Our engineers are using it because our our mission is to regulate this thing. So, we need to understand it." And they're kind of motivated. And there was this time where experienced engineers were kind of holding off because if you had an existing codebase and use AI cursor whatever on it was mildly useful if that even and these engineers were like why should I use a tool if it doesn't help me refactor it doesn't find the bug it doesn't do what I need to do and leadership saw they're not really using it and they kept hearing you know the likes of Antrophic for example was already saying how they're writing a lot of their code with with cloth code uh and it just keeps increasing and andropics, you know, like revenue is going up like this. So those leaders are kind of they might be confusing correlation and and and you know, like which one comes first, but they're like, well, we should be using it more because probably good things will happen and thus bad things will happen if we don't use it. So the whole targeting and measuring things, it actually came from leadership wanting, we want our engineers to use faking AI. I don't care what it is. And it it was a bit of a push like we know this is bad but it's it's better than them using it. Best example is Coinbase where uh Brian Armstrong the CEO just like fired an engineer or he sent an email saying everyone like needs to get on board and use AI tools and whoever doesn't use it in a week I'll have a conversation with them and then I think a week later on Saturday he fired an engineer and you know like this again high paying job like we're talking base salary like three 400k,000 per per year uh and then both equity and everything on top of it like they got the message everyone just started to just you know like use it and you back to your question. So on on one there there's a push and look I feel it's a little bit like this is going to be controversial but have you ever wor wondered why big tech loves to do lead code style interviews algorithmical interviews which have nothing to do with the job and and we know it's the case and there's a lot of criticism for this and they've been doing this since since like 20 years but here's the thing it selects for a specific type of person. It selects for the person who's smart and willing to put up with absolute [inaudible] to get the job. And this person, you know, they will study two months pre AI, two months or three months of lead code, which again makes no sense on the job, but you do it. You get in there and this person will be putting to put up with [inaudible] that makes absolute no sense to keep the job. So token maxing happens at large companies and people are putting up with this BS. And look, a lot of them are smart and they will make the most of it. some of them will build cool stuff. Um it's it's the reality I think of big tech. So we're in this weird place where big tech is a bit weirder than startups where you know no one cares about tokenaxing. They care about like just building stuff and you know use whatever makes sense. Don't people will care about the cost.

**Host**: Yeah.

**Gergely Orosz**: But going back to your question like like you know like is is it making us productive as as a whole like individually it's it certainly is and as teams we're kind of like a bit question mark because we should be moving faster and there are a few companies that do. Entrophic is a good example, but a bunch of companies are like not it's it's it seems it's hard to retrofit all this AI into like the way we have been working.

**Host**: Yeah. Uh, one of my favorite studies from last year was the meter study where they uh did a blind test of uh people and their expectations of productivity, right? And basically the the end result was they felt 20% more productive, but their demonstrated results was actually they were 20% less productive on average.

**Gergely Orosz**: Yes. But that that study was very interesting because they

**Host**: it was very small sample size.

**Gergely Orosz**: It was 30 people and there was one outlier uh who actually was way more

**Host**: Anthony we we interviewed him on the

**Gergely Orosz**: pod. Yeah.

**Host**: Yeah. Yeah. So he was the one productive AI engineer

**Gergely Orosz**: but anyway, so uh, actually my theory is that uh, something that I've seen on my team is that I've been enabling coding agents for the rest of my team who are non techchnical right and uh, you as the engineer may not be more much that much more productive because and you can be more productive if you uh attend AIE but uh, if you actually enable your non-coding uh, your your non-coding collaborators to code, actually they are more productive because they don't have to wait for you right? And that's that like unlock of like oh suddenly you have serverless developers basically uh, and I think I think that's that organizational coding thing is different than studying pull request level productivity for the individual developer.

**Gergely Orosz**: yeah, and and the thing that still I still remember to this date I I talked with Simon Willis I think in 2024 so two years after Chad GPT came out and he was Simon Wilson top commenter on hacker news or he's he's

**Host**: that's his that's not his title man top commenter on hacker What the [inaudible]

**Gergely Orosz**: No, he's

**Host**: creative, Django, top blogger. Yeah. Uh, prompt injections. Uh, yeah.

**Gergely Orosz**: Yeah. He's actually not talk. I'm sure he's the most submitted block cuz he blocks so much like like and he's

**Host**: but he told me back then he said like this thing AI is is just so hard to to get good at. He's like there's no manual. And he's like, I've been doing it back then for two years and I'm still I'm still figuring out what works and what doesn't. I keep changing my workflows. And I think that's something that is a bit hard for us. Two things about AI that for any of us engineers is hard to understand. One is it just takes a long time to get good at it and you need to keep doing it. And the second thing is understanding the theory will not make you better at using the tools which is an absolute mind [inaudible] honestly because we're so used to you know you understand how the compiler works, how assembly works. Okay, you will now be more efficient if you want to write low-level code because you know how it works. But what with these things I mean you can of course it's helpful to understand how how the the architecture underlying works attention the different the the different probability sets etc etc but it will not help you get a sense for how you can use it and then once you figure out how you can be more productive if you're if you're inside of a team again it kind of breaks and you have to relearn again but but the more effort you put into it it like it's clear that it's it's working it's helpful and I think it it's the teams I'm seeing and getting more value out of it. Low ego, open to learning, open to leaving your priors behind. The word priors I have not used forever and I feel we're in this stage where like just just leave your priors behind. Just have an open mind like don't leave your experience behind but you know be open to it.

**Host**: Yeah. Zooming out a little bit. How is the role of the software engineer changing?

**Gergely Orosz**: I think it's always this was always coming but AI is just just speeding it up. uh even before AI a few it's interesting I see like startups in many ways venture funded startups are kind of front running what the industry will be catching up because venture funed startups are about fast growth um doing mo moving fast with smaller teams because smaller teams mean smaller comps even preai so a lot a lot of these venture funed startups start to expect a lot wider range of roles from engineers for example devops as a whole inside VC funded companies from the mid210s every engineer was kind of like responsible for the code they deployed but like more traditional companies they had more money more sorry more less pressure they kind of have dedicated devops teams and some of those things so in in the industry like the software engineer is now becoming like the kind of the tester role has collapsed into software engineer we most companies don't have dedicated testers very very few do devops collapse into here uh and now we're starting to have the product role also starting to come so a lot of companies even like in 2022 before AI starts to hire for product engineers that's happening faster and I think the the last push that AI is doing is even for early career engineers there's a lot more seniority expected or or senior like things planning about things knowing about the business so I I I think the role is expectations are are higher teams are also getting smaller everywhere I talked with someone at John Deere 200 person uh 200 year old company sorry uh you know like they do tractors and and all all that stuff and and inside of that company, one of their their VP of engineering was telling me how they're actually seeing that their two pizza teams are now just one pizza teams inside of that company. It's the reality partially because of these tools.

**Host**: So, my joke used to be I am a one pizza team because I eat a lot of pizza, but uh, depends how much pizza you eat.

**Gergely Orosz**: Uh, there's so I'm sorry to interrupt. I don't know if I cut you off in some critical point. Uh, there's a comment saying I've heard it twice even among this audience where a lot of people are saying that oh uh, you're no longer an engineer, everyone's an engineering manager now and you've been an engineering manager and I wonder if you agree with that or if you have a different take, you know, because basically you're the the the the common analogy is that you're no longer a software engineer, you're just managing engineering agents, right?

**Gergely Orosz**: Yeah, if you've been a manager before that is an absolute [inaudible] so so here here's the thing the like Yes, you are a manager without all the things that no one wants to become a manager for the the when you become an engineering manager. Hands up if you are or have been an engineering manager, right? Hands up if you actually if you've not been and you want to be one

**Host**: about 15 20%.

**Gergely Orosz**: All right, you come and talk to me afterwards. I I'll tell there's a hand up there. I'll talk you out of it. So, so what you think you become an engineering manager to like help people's career, maybe have higher salary, higher impact, all you know there can be a lot of dynamics but the reality is is is you you become more removed from the product and you have to deal with people problems and the thing with with agents is you don't have to deal with people drama, people problems, conflict between your team. I mean unless the next generation of agents starts to fight with each other. I think that'll be something but you actually you you do have to orchestrate but it's more like a tech lead role or or or experienced engineer where where you're like mentoring uh, mentoring engineers but you don't have the people management. You don't need to worry about the personal problems. So it's actually a lot more kind of empowering. And I was talking with uh, the podcast was was just out yesterday with with DHH uh, creator of Ruby on Rails who said, you know, people told him like, okay, it's it's like managing things and he's not excited about managing agents, but it feels it's more like a mech suit where you have like you can do seven things at once, you can do a lot faster and you're in control and that's more what it feels like. So there's orchestration, yes, but it's very different to management. And also the the really really bad thing or honestly shitty thing about management if if you make it into management which makes it hard also rewarding later when you you tell yourself at least this thing is you start a project with all these people under you you know congratulations you've got 10 people wonderful and you start a project and in 6 months you will see some results of the decision that you made with agents it's just so much faster so the the feedback loop is faster so I I think it's it's not much of it except for the orchestration and and and for that everyone's going to have their own flavor. Some people will will have the tendency to like run multiple agents and they're good at this or we good at it. Some people just do like two agents. Michelle Hashimoto, I interviewed him. He has two agents. He always has one agent running. No, he has one background agent that he doesn't. That's it. He's like two is enough for me. Great.

**Host**: Yeah. Yeah. Uh, we're figuring out the patterns. Um, uh, I want to hit you on large tech infra. uh, this is something that I think both of us are very excited by by uh, good infra which is a very niche uh, interest. What are you seeing?

**Gergely Orosz**: it's wild to see how much of the so I said that from externally a lot of companies a lot of big tech companies especially the ones are spending a bunch on AI and have platforms and all that you're not seeing too much like more come out like Uber is a good example I'm not seeing too many more features come out of Uber or new products launcher and they're like but what's going on they are really investing in AI but when you look inside there's a whole lot of buzz they are rebuilding their complete IM infra you know they're and I'm not talking about they're buying cursor or or cloud code or all that they're doing that as well but they're completely they're building their own own custom background coding agents that is integrated into their monor repo they are are having uh, their own MCP gateway that is is now integrated into service discovery their on call tooling is being retoled their internal code review system is like like categorizing based on risk. They are like and Uber is one example but all everyone else Airbnb intercom meta Microsoft even midsize companies are just building so much internal improp and I was asking to myself like why on one end this feels like such a waste but when I worked at Uber for four years I realized they spend so much on on internal platform there's two reasons one is honestly it's a it's a lowrisk way to get good with AI uh, to be hands-on and these companies want to be hands-on but maybe you shouldn't start with shipping AI features no one wants into your codebase. Second of all, because these these companies have such so much code that never fit in a context window, by building custom solutions and just basic basic wagons, that kind of stuff, they will have better results than off-the-shelf vendors. So, they already have a win. And number three, honestly, is anything that has AI in it gets funded. So, there's this joke of if you're in the developer platform team and you're asking for more headcount, like good luck with that. Oh, developer platform. Oh, but say that you want to get two extra headc count for agent experience. Done. H. So, so there's that part as well. But, but all

**Host**: agent experience is just a CLI

**Gergely Orosz**: pretty much. But all these come inside there's so much buzz and so much work. Everyone's building their own custom system. So, I'm kind of wondering how long this will take, but I think for next year this is going to happen. So, if you either have friends or if you're work if you're working at a company, you'll see. But talk with with friends at other large companies and you will probably see you are all building the same thing. If you're at a large company and you're not already building an MCP gateway, what are you even doing?

**Host**: Yeah. Um, actually a lot of these topics are exactly the things I cured for tomorrow. Uh, it's just fantastic to have you as the closing keynote for today because uh, it's, it's like an appetizer for tomorrow. We have talks about MCP gateway and all these sort of AI architecture and infra things and I do think like uh, infra like taking AI infra seriously as a company is uh, very mis not that well un understood and right now you just kind of learn by example from people because there's not really like a textbook or anything like about it. So the way I think about this because again from if you just kind of step out and we love to criticize big tech of how they're wasting money here and there and by the way we love to criticize Google and I'm kind of thinking to myself like hang on what if Google ex actually executed well like do we want that and you know they would kill all the startups but but what they're doing makes makes sense and Shopify is an example where I'm like huh I'm starting to get why it makes sense to do all this stuff. So Shopify in 2021 they were the first company to have access to a GitHub copilot. What happened is the the head of engineering fartoir heard about GitHub copilot being developed internally inside of GitHub and he pinged Thomas Dunca the CEO of GitHub at the time and said hey Thomas I heard you guys are doing C-pilot and he's like yeah we are it's internal. He's like I I'd like to get access to it. He's like yeah but it's not for sale. He's like no no no you don't understand. I I didn't ask if it's for sale. we would like to roll it out to all of Shopify and in return we will give you feedback for 3,000 people for you know as honest feedback all the time and so they got it a year before it was out anywhere and they incurred a lot of churn. It wasn't that great initially and and they went through all of this stuff and then Shopify was the first company to on board to like a bunch of other tools and they gave unlimited budget and they're spending so much time ironing out bugs. But the reason they're doing it, this is what like made me click is they are trading off churn and expense and spending a lot more money to be at the forefront of this. They are a few months ahead or six months ahead of their competition and for them it's worth it. It's not worth it for anyone else, right? If you're if you're at a company where your business is like something something physical and you don't care like yeah, just just wait out it it'll come. But for a lot of us in the tech industry this turn is worth it. Plus what Farhan told me is like because he actually told me he's kind of worried about the cost now. But he was like look like it's still worth it because if it would look silly if I said you cannot have these tools, how would I hire the best?

**Host**: So it's it's innovation, recruitment and it kind of makes sense when you think about it. And the weird thing everyone is doing it at the same time. So it looks silly but it, it's rational.

**Gergely Orosz**: Uh, my next podcast is with Mikuel Parkin the CTO of Shopify and uh, the sheer amount of machine learning that they do and infra that they set up for their customers makes me want to be a customer. You know, that's that's like the best uh, endorsement I can give. Um, I'm going to get meta a little bit and talk about pragmatic engineer. Uh, you and I kind of startedish in COVID. Uh, you just left Uber. Uh, how has it been growing? What, what are the main stats that you're proud of that uh, you'd like to share with the world? Yeah. So I I started pragmatic engineer I I I a joke that if it wasn't for co I I would probably never have started the this thing because what happened with co is uh, Uber had layoffs and most of the tech industry was doing great but Uber was not and my team uh, was hit by layoffs and then we we had to disperse the remaining people at other teams because our mission no longer made sense and it was just like a the morale was low my morale was low so I was like let me take a break. I wanted to write some books. Swix was writing his book the the coding career.

**Host**: Yeah, some of you have read it. I've met some of you.

**Gergely Orosz**: Yeah. and and that that's how we met there. And then uh, my plan was to write a book and then start start up some startup something something platform engineer control C, control V from what Uber was doing inside and that's actually almost all Uber su Uber startups it's it's amazing temporal is is is from there.

**Host**: if I by the way, if I did not start AI engineer I would have started platform engineer.

**Gergely Orosz**: that that would have been the industry conference.

**Host**: yeah, love it. And then I start I started the pragmatic engineer uh, a year after I left Uber. It was just an experiment. Um, I figured no one Substack was taking off. No one was writing about software engineering in-depth and I just acted all confident saying pretended that I I knew what I was doing. The first article was about Uber's platform and program split that no one had written about publicly before and it's a it's a free article. You can you can now check it out. Uh, and it was like when you feel product market fit, that's what I felt almost immediately. The first week before I published anything, just a confident Twitter post, I had 100 people pay upfront $100 for the whole year, which I was like, whoa, I have published anything. In six weeks, I was at a,000 people paying for this thing that didn't exist before, which was my old Uber base salary back back in Amsterdam. And it just kept going up. So like I I figured like when you find product market fit, this is like outside of like there's this rule like if you find product market fit, just keep doing what you're doing. So for me, I just kept writing that one article. I got all these interview requests, collaborations, podcast. I just said no to all of them because I knew the most important thing was to do what makes it successful, which is that one article. And later it turned into two articles. And for two years, this is all I did, just two articles. And after two years, I looked up and I was like, huh, like this is actually working. People like doing it. I like doing it. There's a future in that. And that's when I decided I actually want to turn this into a business that I don't burn out because for two years every vacation I went to I was working 50 60 hours. I was always thinking I was writing I I couldn't really let go. So I started to grow the team a little bit. Uh, I I Ellen Bird the first secondary researcher Ellen she's ex x ex uh.

**Host**: she's here right?

**Gergely Orosz**: Ellen's not here. Um, Jessica is who who just joined uh, later.

**Host**: Yeah.

**Gergely Orosz**: And then uh, so now it was two of us. Uh, and I started a podcast year and a half ago because I talked with so many people. I figured it was a bit of a shame to to not have it. So, the primatic engineer became the number one paid technology newsletter about four months after starting. It stayed there for three years. Now, semi analysis has

**Host**: Dylan versus uh, you guys. Um, yeah. No, congrats on your success. Uh, I think you're also a leading tech voice in Europe which I think you're sort of proudly sort of uh, upholding that over here which I would really wanted to feature. Thank you for your support for AIE. And uh, everyone thank you. Good. Awesome. Thanks, man.

</details>

### AI 对软件工程师角色的影响

**主持人**: 是的，我们正在摸索模式。嗯，我想和你聊聊大型科技的基础设施。嗯，这是我俩都非常兴奋的一个领域，良好的基础设施，这是一个非常小众的兴趣。你有什么看法？
<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. Uh, we're figuring out the patterns. Um, uh, I want to hit you on large tech infra. uh, this is something that I think both of us are very excited by by uh, good infra which is a very niche uh, interest. What are you seeing?

</details>

**Gergely Orosz**: 看到有多少公司，尤其是那些在大力投资 AI 并拥有相关平台和一切的大型科技公司，外面看是这样。但你没有看到太多新的东西出来。像 Uber 是个好例子，我没看到 Uber 推出太多新功能或新产品，但他们却在大量投资 AI。当你审视内部时，你会发现充满了各种喧嚣。他们正在重建他们完整的基础设施。我说的不是他们购买 Cursor 或 Cloud Code 之类的东西，他们也在做，但他们正在完全重建。他们正在构建自己的自定义后台编码代理，这些代理已集成到他们的单体仓库中。他们拥有自己的 MCP 网关，现在已集成到服务发现中。他们的应急响应工具正在被重塑。他们的内部代码审查系统正在根据风险进行分类。Uber 是一个例子，但其他所有公司，Airbnb、Intercom、Meta、Microsoft，甚至中型公司都在构建大量的内部工具。我一直在问自己，为什么一方面这感觉像一种浪费，但当我在 Uber 工作了四年，我意识到他们会在内部平台投入如此之多。有两个原因。

一是，老实说，这是通过 AI 获得实践经验的低风险方式，并且可以动手操作。而这些公司想要动手操作，但也许你不应该从向代码库中交付未经检验的 AI 功能开始。

二是，因为这些公司拥有太多的代码，这些代码永远无法放入一个上下文窗口。通过构建自定义解决方案和基础的 [口误，可能指 Scaffold 或 Wagon] 之类的东西，他们将比现成的供应商获得更好的结果。所以，他们已经有了一个优势。

第三，说实话，任何包含 AI 的东西都能获得资金。所以，有一个笑话，如果你在开发者平台团队，并且你申请更多的人员编制，祝你好运。哦，开发者平台。但是，如果你说你想要两个人来处理“代理体验”，那就可以了。所以，也有这方面的原因。但所有这些都伴随着巨大的喧嚣和大量的工作。每个人都在构建自己的定制系统。所以我有点好奇这需要多长时间，但我认为到明年就会发生。所以，如果你有朋友，或者如果你在大公司工作，你会看到的。但和其他大公司的朋友聊聊，你很可能会发现你们都在构建同样的东西。如果你在大公司，而你还没有构建 MCP 网关，那你到底在做什么？
<details>
<summary>Original English</summary>

**Gergely Orosz**: it's wild to see how much of the so I said that from externally a lot of companies a lot of big tech companies especially the ones are spending a bunch on AI and have platforms and all that you're not seeing too much like more come out like Uber is a good example I'm not seeing too many more features come out of Uber or new products launcher and they're like but what's going on they are really investing in AI but when you look inside there's a whole lot of buzz they are rebuilding their complete IM infra you know they're and I'm not talking about they're buying cursor or or cloud code or all that they're doing that as well but they're completely they're building their own own custom background coding agents that is integrated into their monor repo they are are having uh, their own MCP gateway that is is now integrated into service discovery their on call tooling is being retoled their internal code review system is like like categorizing based on risk. They are like and Uber is one example but all everyone else Airbnb intercom meta Microsoft even midsize companies are just building so much internal improp and I was asking to myself like why on one end this feels like such a waste but when I worked at Uber for four years I realized they spend so much on on internal platform there's two reasons one is honestly it's a it's a lowrisk way to get good with AI uh, to be hands-on and these companies want to be hands-on but maybe you shouldn't start with shipping AI features no one wants into your codebase. Second of all, because these these companies have such so much code that never fit in a context window, by building custom solutions and just basic basic wagons, that kind of stuff, they will have better results than off-the-shelf vendors. So, they already have a win. And number three, honestly, is anything that has AI in it gets funded. So, there's this joke of if you're in the developer platform team and you're asking for more headcount, like good luck with that. Oh, developer platform. Oh, but say that you want to get two extra headc count for agent experience. Done. H. So, so there's that part as well. But, but all

**Host**: agent experience is just a CLI

**Gergely Orosz**: pretty much. But all these come inside there's so much buzz and so much work. Everyone's building their own custom system. So, I'm kind of wondering how long this will take, but I think for next year this is going to happen. So, if you either have friends or if you're work if you're working at a company, you'll see. But talk with with friends at other large companies and you will probably see you are all building the same thing. If you're at a large company and you're not already building an MCP gateway, what are you even doing?

</details>

**主持人**: 是的。嗯，实际上，很多这些话题正是我为明天准备的。嗯，你作为今天的闭幕主题演讲嘉宾真是太棒了，因为这就像是为明天准备的开胃菜。我们有关于 MCP 网关以及所有这些 AI 架构和基础设施的演讲。我认为，嗯，基础设施，就像公司认真对待 AI 基础设施一样，是一种……不太被理解的，现在你只能从人们那里通过例子来学习，因为真的没有像样的教科书或相关资料。所以，我的思考方式是，因为同样，如果你跳出这个圈子，我们喜欢批评大公司在这里那里浪费钱，顺便说一句，我们喜欢批评 Google，我当时想，“等等，如果 Google 真的执行得很好呢？我们想要那种结果吗？”你知道，他们会扼杀所有初创公司。但是，他们所做的有道理。Shopify 是一个例子，我当时想，“嗯，我开始理解为什么做所有这些事情是有道理的。”

所以，Shopify 在 2021 年，他们是第一家能够接触到 GitHub Copilot 的公司。发生的是，工程主管 Fartoir 听说了 GitHub Copilot 在 GitHub 内部开发的情况，他联系了当时的 GitHub 首席执行官 Thomas Dunca，说“嘿，Thomas，我听说你们在做 Copilot。”他说，“是的，我们在做，它是内部的。”他说，“我想获得它的访问权限。”他说，“是的，但它不卖。”他说，“不，不，不，你没明白。我不是问它是否出售。我们想把它推广给 Shopify 的所有人，作为回报，我们会为你提供 3000 人的反馈，总是提供诚实的反馈。”所以，他们在比任何人都早一年获得了它。他们遭受了很多用户流失。最初它并不那么好，他们经历了所有这些事情。然后 Shopify 成为了第一家采用一堆其他工具的公司，他们给了无限的预算，花了大量时间来解决 bug。但他们这样做的原因是，这让我明白了，他们正在权衡用户流失和成本，以及花费更多的钱来处于领先地位。他们比竞争对手领先几个月，或者六个月。对他们来说，这是值得的。对其他人来说，这可能不值得。如果你在一是一家公司，你的业务是实体产品，你不在乎，那好吧，就等着吧，它会来的。但对于我们科技行业中的很多人来说，这个转变是值得的。

此外，Farhan 告诉我，他告诉我他现在有点担心成本。但他又说，“看，它仍然是值得的，因为如果我说‘你们不能使用这些工具’，那会显得很傻，我怎么招聘最好的人才呢？”
<details>
<summary>Original English</summary>

**Host**: Yeah. Um, actually a lot of these topics are exactly the things I cured for tomorrow. Uh, it's just fantastic to have you as the closing keynote for today because uh, it's, it's like an appetizer for tomorrow. We have talks about MCP gateway and all these sort of AI architecture and infra things and I do think like uh, infra like taking AI infra seriously as a company is uh, very mis not that well un understood and right now you just kind of learn by example from people because there's not really like a textbook or anything like about it. So the way I think about this because again from if you just kind of step out and we love to criticize big tech of how they're wasting money here and there and by the way we love to criticize Google and I'm kind of thinking to myself like hang on what if Google ex actually executed well like do we want that and you know they would kill all the startups but but what they're doing makes makes sense and Shopify is an example where I'm like huh I'm starting to get why it makes sense to do all this stuff. So Shopify in 2021 they were the first company to have access to a GitHub copilot. What happened is the the head of engineering fartoir heard about GitHub copilot being developed internally inside of GitHub and he pinged Thomas Dunca the CEO of GitHub at the time and said hey Thomas I heard you guys are doing C-pilot and he's like yeah we are it's internal. He's like I I'd like to get access to it. He's like yeah but it's not for sale. He's like no no no you don't understand. I I didn't ask if it's for sale. we would like to roll it out to all of Shopify and in return we will give you feedback for 3,000 people for you know as honest feedback all the time and so they got it a year before it was out anywhere and they incurred a lot of churn. It wasn't that great initially and and they went through all of this stuff and then Shopify was the first company to on board to like a bunch of other tools and they gave unlimited budget and they're spending so much time ironing out bugs. But the reason they're doing it, this is what like made me click is they are trading off churn and expense and spending a lot more money to be at the forefront of this. They are a few months ahead or six months ahead of their competition and for them it's worth it. It's not worth it for anyone else, right? If you're if you're at a company where your business is like something something physical and you don't care like yeah, just just wait out it it'll come. But for a lot of us in the tech industry this turn is worth it. Plus what Farhan told me is like because he actually told me he's kind of worried about the cost now. But he was like look like it's still worth it because if it would look silly if I said you cannot have these tools, how would I hire the best?

</details>

**主持人**: 所以，这是创新、招聘，当你思考时，它似乎是有道理的。而且奇怪的是，每个人都在同时做这件事。所以它看起来很傻，但它是理性的。
<details>
<summary>Original English</summary>

**Host**: So it's it's innovation, recruitment and it kind of makes sense when you think about it. And the weird thing everyone is doing it at the same time. So it looks silly but it, it's rational.

</details>

**Gergely Orosz**: 嗯，我的下一个播客是与 Shopify 的 CTO Mikuel Parkin 交流。他们为客户提供的机器学习和基础设施数量之多，让我产生了想成为他们客户的念头。你知道，这是我能给出的最好的赞誉。嗯，我想稍微深入地谈谈 Meta 和 Pragmatic Engineer。嗯，你和我大概是在 COVID 期间开始的。嗯，你刚离开 Uber。嗯，它的发展如何？你感到骄傲的主要数据有哪些，你想与世界分享？

是的，我创办了 Pragmatic Engineer。我开玩笑说，如果不是因为 COVID，我可能永远不会创办这个东西，因为 COVID 发生时，Uber 进行了裁员，而大多数科技行业都在蓬勃发展，但 Uber 却不是。我的团队也受到了裁员的影响，然后我们不得不将剩余的员工分散到其他团队，因为我们的使命不再有意义，士气低落，我的士气也很低落，所以我就想，“让我休息一下吧。”我想写几本书。《The Coding Career》这本书就是 Swix 写的。
<details>
<summary>Original English</summary>

**Gergely Orosz**: Uh, my next podcast is with Mikuel Parkin the CTO of Shopify and uh, the sheer amount of machine learning that they do and infra that they set up for their customers makes me want to be a customer. You know, that's that's like the best uh, endorsement I can give. Um, I'm going to get meta a little bit and talk about pragmatic engineer. Uh, you and I kind of startedish in COVID. Uh, you just left Uber. Uh, how has it been growing? What, what are the main stats that you're proud of that uh, you'd like to share with the world? Yeah. So I I started pragmatic engineer I I I a joke that if it wasn't for co I I would probably never have started the this thing because what happened with co is uh, Uber had layoffs and most of the tech industry was doing great but Uber was not and my team uh, was hit by layoffs and then we we had to disperse the remaining people at other teams because our mission no longer made sense and it was just like a the morale was low my morale was low so I was like let me take a break. I wanted to write some books. Swix was writing his book the the coding career.

**Host**: Yeah, some of you have read it. I've met some of you.

</details>

**主持人**: 是的，你们中的一些人读过。我见过你们中的一些人。
<details>
<summary>Original English</summary>

**Host**: Yeah. and and that that's how we met there.

</details>

**Gergely Orosz**: 是的，我们就是这样认识的。然后，我的计划是写一本书，然后创办一家初创公司，做一些平台工程师的东西，Ctrl+C, Ctrl+V，复制 Uber 内部的做法。事实上，几乎所有的 Uber 初创公司都源于此，这真是太令人惊讶了，Temporal 就是从中出来的。
<details>
<summary>Original English</summary>

**Gergely Orosz**: And then uh, my plan was to write a book and then start start up some startup something something platform engineer control C, control V from what Uber was doing inside and that's actually almost all Uber su Uber startups it's it's amazing temporal is is is from there.

**Host**: if I by the way, if I did not start AI engineer I would have started platform engineer.

</details>

**Gergely Orosz**: 那本可能就是行业会议了。
<details>
<summary>Original English</summary>

**Gergely Orosz**: that that would have been the industry conference.

</details>

**主持人**: 是的，很喜欢。
<details>
<summary>Original English</summary>

**Host**: yeah, love it.

</details>

**Gergely Orosz**: 然后我创办了 Pragmatic Engineer，在我离开 Uber 一年后。最初只是一个实验。嗯，我当时觉得 Substack 正在兴起，但没有人深入撰写关于软件工程的文章，于是我就故作自信地声称我“知道我在做什么”。第一篇文章是关于 Uber 的平台和项目拆分，这是以前从未有人公开写过的，而且是一篇免费文章。你现在可以去看看。嗯，我几乎立刻就感受到了产品市场契合（product market fit）。在发布任何内容之前的第一个星期，仅仅凭一条自信的推文，就有 100 个人预付了 100 美元订阅一整年，当时我就想，“哇，我还没发布任何东西呢。”六周后，我有 1000 人为这个前所未有的事物付费，这相当于我以前在阿姆斯特丹的 Uber 的基本工资。然后它就一直增长。所以，我当时就想，当你找到产品市场契合时，这就是……有一个规则，如果你找到了产品市场契合，就继续做你正在做的事情。所以对我来说，我只是一直在写那篇文章。我收到了所有这些采访请求、合作、播客。我一一拒绝了，因为我知道最重要的事情是做能让它成功的事情，那就是那篇文章。后来它变成了两篇文章。两年里，我就只做了这两篇文章。两年后，我抬头一看，心想，“嗯，这东西确实在奏效。人们喜欢它。我喜欢做它。它有未来。”

于是我决定，我真的想把这件事变成一项事业，这样我就不会耗尽心力，因为这两年里，我每次度假都工作 50-60 小时。我总是在思考，我在写作，我真的放不下。所以，我开始稍微扩大团队。嗯，我请来了 Ellen Bird，她是第一个二级研究员，Ellen，她是前……
<details>
<summary>Original English</summary>

**Gergely Orosz**: And then I start I started the pragmatic engineer uh, a year after I left Uber. It was just an experiment. Um, I figured no one Substack was taking off. No one was writing about software engineering in-depth and I just acted all confident saying pretended that I I knew what I was doing. The first article was about Uber's platform and program split that no one had written about publicly before and it's a it's a free article. You can you can now check it out. Uh, and it was like when you feel product market fit, that's what I felt almost immediately. The first week before I published anything, just a confident Twitter post, I had 100 people pay upfront $100 for the whole year, which I was like, whoa, I have published anything. In six weeks, I was at a,000 people paying for this thing that didn't exist before, which was my old Uber base salary back back in Amsterdam. And it just kept going up. So like I I figured like when you find product market fit, this is like outside of like there's this rule like if you find product market fit, just keep doing what you're doing. So for me, I just kept writing that one article. I got all these interview requests, collaborations, podcast. I just said no to all of them because I knew the most important thing was to do what makes it successful, which is that one article. And later it turned into two articles. And for two years, this is all I did, just two articles. And after two years, I looked up and I was like, huh, like this is actually working. People like doing it. I like doing it. There's a future in that. And that's when I decided I actually want to turn this into a business that I don't burn out because for two years every vacation I went to I was working 50 60 hours. I was always thinking I was writing I I couldn't really let go. So I started to grow the team a little bit. Uh, I I Ellen Bird the first secondary researcher Ellen she's ex x ex uh.

**Host**: she's here right?

**Gergely Orosz**: Ellen's not here. Um, Jessica is who who just joined uh, later.

</details>

**主持人**: 她在这里对吗？
<details>
<summary>Original English</summary>

**Gergely Orosz**: Ellen's not here. Um, Jessica is who who just joined uh, later.

</details>

**Gergely Orosz**: Ellen 不在这里。嗯，Jessica 是后来加入的。
<details>
<summary>Original English</summary>

**Gergely Orosz**: And then uh, so now it was two of us. Uh,

</details>

**Gergely Orosz**: 然后，现在是我们两个人。嗯，我一年半前开始做播客，因为我采访了很多人。我当时觉得不把这些内容发出来有点可惜。所以，Pragmatic Engineer 在开始后的四个月内成为了一号付费科技通讯。它在那里保持了三年。现在，Semi Analysis…
<details>
<summary>Original English</summary>

**Gergely Orosz**: and I started a podcast year and a half ago because I talked with so many people. I figured it was a bit of a shame to to not have it. So, the primatic engineer became the number one paid technology newsletter about four months after starting. It stayed there for three years. Now, semi analysis has

**Host**: Dylan versus uh, you guys. Um, yeah. No,

</details>

**主持人**: Dylan 对比你们。嗯，是的。不，
<details>
<summary>Original English</summary>

**Host**: Dylan versus uh, you guys. Um, yeah. No,

</details>

**主持人**: 恭喜你的成功。嗯，我认为你也是欧洲领先的技术声音之一，我认为你在这方面得到了很好的维护，我真的很想在这里特别介绍你。感谢你对 AIE 的支持。嗯，大家，谢谢。
<details>
<summary>Original English</summary>

**Host**: congrats on your success. Uh, I think you're also a leading tech voice in Europe which I think you're sort of proudly sort of uh, upholding that over here which I would really wanted to feature. Thank you for your support for AIE. And uh, everyone thank you.

</details>

**Gergely Orosz**: 好的。太棒了。谢谢。
<details>
<summary>Original English</summary>

**Gergely Orosz**: Good. Awesome. Thanks, man.

</details>

### 软件工程师的未来角色与技能要求

**Gergely Orosz**: 是的，所以 Meta 的一些经理在绩效评估中确实会参考 Token 的使用情况，这和代码 diffs、工作影响或代码审查一样，是一个衡量一个人有多大帮助的数据点。但是，就像任何数据点一样，它可能被武器化。比如，一个表现不佳、影响力低且 Token 数量少的人，显然根本没有尝试。而一个表现优异、影响力高且 Token 数量多的人，显然是在创新，这是有益的。

在 Microsoft 也是一样，也有一个排行榜。我和人们交谈，他们说“太离谱了”，有些人只是运行自主代理来生成垃圾代码，说实话，仅仅是为了让那个数字上去。有时情况会变得很荒谬，因为 Meta 曾经有过这个排行榜，在一篇文章出来后就废除了它，因为它看起来很糟糕，他们就关闭了。但人们仍然在 Token Maxing，因为他们认为“这可能会发生，但你知道，我们是工程师，别忘了这些是高薪工作，对吧？你真的不想因为一些愚蠢的事情而失去工作，比如你的 Token 数量不够”。

但 Salesforce 有每月最低花费目标，我记得大约是 175 美元。所以人们会，你知道，在月初就 Token Max，以达到这个目标。所以，这很奇怪。它最初只是个笑话，几个月前，Token Maxing 真的只是人们疯狂地享受这个东西，并构建酷炫的东西。但在很多公司，它已经变成了一种文化上的怪事。所以，这是一个奇怪的时期。

我记得以前，当早期开发者生产力工具出现时，比如 Velocity 和 Pluralite Flow，它们会衡量代码行数和 QPRs（季度绩效回顾）数量。我们知道那很愚蠢，公司也会照此优化。但现在，像 Meta 和 Microsoft 这样顶尖的公司，竟然在激励人们做一些愚蠢的事情。
<details>
<summary>Original English</summary>

**Gergely Orosz**: So, inside of these companies specifically, I talked with a lot of people at at Meta. And again, this is not representative 100% of Meta, but they had this leaderboard where people showed up and they have like massive amounts of tokens and a lot of engineers got just scared, worried, so they started to token max to try to generate tokens. stories that I've heard first or well secondhand from these people who who who told me firsthand is for example instead of reading the documentation I will ask the agent to summarize it for me and ask questions even though it doesn't do a good job answering it but my token count goes up people just want to not be in the bottom 25% or bottom 50% for token count. where these things are measured inside of Microsoft again there's a leaderboard and I'm talking with people they're like it's ridiculous like how some people are just running autonomous agents to build junk honestly for the sake of having that number go up and and sometimes it gets ridiculous because like inside of Meta they had this leaderboard they got rid of it after an article came out and it looked amaz like just just like closed it down. that people are still token maxing by the way because there's this this thinking that it might have gone but you know we're engineers and don't forget these are highp paying jobs right that like you don't really want to lose a job over something stupid as like you didn't have INF token count and that's how it feels but inside Salesforce there's a target of minimum spend per month like I think it's like $175 between the things so like people are like again you kind of like you know beginning of the month like just token max to get there so it's it's it's weird and it started as a joke earlier like a few months ago token maxing was really just people like going crazy and enjoying this thing and building cool stuff. But it's kind of turned into in a lot of companies I think it's just a culturally weird thing. So it's a weird time to be in cuz I remember lines of code used to be when when early uh developer productivity tools came out like velocity and pluralite flow. They kind of measured lines of code and and number of QPRs and we know that was stupid and people kind of optimized for that at companies that did it. But it's it's almost like what now it's the top running companies like Meta and Microsoft who are incentivizing people just to do just stupid stuff honestly.

</details>

**主持人**: 是的，我们正在摸索模式。嗯，我想和你聊聊大型科技的基础设施。嗯，这是我俩都非常兴奋的一个领域，良好的基础设施，这是一个非常小众的兴趣。你有什么看法？
<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. Uh, we're figuring out the patterns. Um, uh, I want to hit you on large tech infra. uh, this is something that I think both of us are very excited by by uh, good infra which is a very niche uh, interest. What are you seeing?

</details>

**Gergely Orosz**: 看到有多少公司，尤其是那些在大力投资 AI 并拥有相关平台和一切的大型科技公司，外面看是这样。但你没有看到太多新的东西出来。像 Uber 是个好例子，我没看到 Uber 推出太多新功能或新产品，但他们却在大量投资 AI。当你审视内部时，你会发现充满了各种喧嚣。他们正在重建他们完整的基础设施。我说的不是他们购买 Cursor 或 Cloud Code 之类的东西，他们也在做，但他们正在完全重建。他们正在构建自己的自定义后台编码代理，这些代理已集成到他们的单体仓库中。他们拥有自己的 MCP 网关，现在已集成到服务发现中。他们的应急响应工具正在被重塑。他们的内部代码审查系统正在根据风险进行分类。Uber 是一个例子，但其他所有公司，Airbnb、Intercom、Meta、Microsoft，甚至中型公司都在构建大量的内部工具。我一直在问自己，为什么一方面这感觉像一种浪费，但当我在 Uber 工作了四年，我意识到他们会在内部平台投入如此之多。有两个原因。

一是，老实说，这是通过 AI 获得实践经验的低风险方式，并且可以动手操作。而这些公司想要动手操作，但也许你不应该从向代码库中交付未经检验的 AI 功能开始。

二是，因为这些公司拥有太多的代码，这些代码永远无法放入一个上下文窗口。通过构建自定义解决方案和基础的 [口误，可能指 Scaffold 或 Wagon] 之类的东西，他们将比现成的供应商获得更好的结果。所以，他们已经有了一个优势。

第三，说实话，任何包含 AI 的东西都能获得资金。所以，有一个笑话，如果你在开发者平台团队，并且你申请更多的人员编制，祝你好运。哦，开发者平台。但是，如果你说你想要两个人来处理“代理体验”，那就可以了。所以，也有这方面的原因。但所有这些都伴随着巨大的喧嚣和大量的工作。每个人都在构建自己的定制系统。所以我有点好奇这需要多长时间，但我认为到明年就会发生。所以，如果你有朋友，或者如果你在大公司工作，你会看到的。但和其他大公司的朋友聊聊，你很可能会发现你们都在构建同样的东西。如果你在大公司，而你还没有构建 MCP 网关，那你到底在做什么？
<details>
<summary>Original English</summary>

**Gergely Orosz**: it's wild to see how much of the so I said that from externally a lot of companies a lot of big tech companies especially the ones are spending a bunch on AI and have platforms and all that you're not seeing too much like more come out like Uber is a good example I'm not seeing too many more features come out of Uber or new products launcher and they're like but what's going on they are really investing in AI but when you look inside there's a whole lot of buzz they are rebuilding their complete IM infra you know they're and I'm not talking about they're buying cursor or or cloud code or all that they're doing that as well but they're completely they're building their own own custom background coding agents that is integrated into their monor repo they are are having uh, their own MCP gateway that is is now integrated into service discovery their on call tooling is being retoled their internal code review system is like like categorizing based on risk. They are like and Uber is one example but all everyone else Airbnb intercom meta Microsoft even midsize companies are just building so much internal improp and I was asking to myself like why on one end this feels like such a waste but when I worked at Uber for four years I realized they spend so much on on internal platform there's two reasons one is honestly it's a it's a lowrisk way to get good with AI uh, to be hands-on and these companies want to be hands-on but maybe you shouldn't start with shipping AI features no one wants into your codebase. Second of all, because these these companies have such so much code that never fit in a context window, by building custom solutions and just basic basic wagons, that kind of stuff, they will have better results than off-the-shelf vendors. So, they already have a win. And number three, honestly, is anything that has AI in it gets funded. So, there's this joke of if you're in the developer platform team and you're asking for more headcount, like good luck with that. Oh, developer platform. Oh, but say that you want to get two extra headc count for agent experience. Done. H. So, so there's that part as well. But, but all

**Host**: agent experience is just a CLI

**Gergely Orosz**: pretty much. But all these come inside there's so much buzz and so much work. Everyone's building their own custom system. So, I'm kind of wondering how long this will take, but I think for next year this is going to happen. So, if you either have friends or if you're work if you're working at a company, you'll see. But talk with with friends at other large companies and you will probably see you are all building the same thing. If you're at a large company and you're not already building an MCP gateway, what are you even doing?

</details>

**主持人**: 是的。嗯，实际上，很多这些话题正是我为明天准备的。嗯，你作为今天的闭幕主题演讲嘉宾真是太棒了，因为这就像是为明天准备的开胃菜。我们有关于 MCP 网关以及所有这些 AI 架构和基础设施的演讲。我认为，嗯，基础设施，就像公司认真对待 AI 基础设施一样，是一种……不太被理解的，现在你只能从人们那里通过例子来学习，因为真的没有像样的教科书或相关资料。所以，我的思考方式是，因为同样，如果你跳出这个圈子，我们喜欢批评大公司在这里那里浪费钱，顺便说一句，我们喜欢批评 Google，我当时想，“等等，如果 Google 真的执行得很好呢？我们想要那种结果吗？”你知道，他们会扼杀所有初创公司。但是，他们所做的有道理。Shopify 是一个例子，我当时想，“嗯，我开始理解为什么做所有这些事情是有道理的。”

所以，Shopify 在 2021 年，他们是第一家能够接触到 GitHub Copilot 的公司。发生的是，工程主管 Fartoir 听说了 GitHub Copilot 在 GitHub 内部开发的情况，他联系了当时的 GitHub 首席执行官 Thomas Dunca，说“嘿，Thomas，我听说你们在做 Copilot。”他说，“是的，我们在做，它是内部的。”他说，“我想获得它的访问权限。”他说，“是的，但它不卖。”他说，“不，不，不，你没明白。我不是问它是否出售。我们想把它推广给 Shopify 的所有人，作为回报，我们会为你提供 3000 人的反馈，总是提供诚实的反馈。”所以，他们在比任何人都早一年获得了它。他们遭受了很多用户流失。最初它并不那么好，他们经历了所有这些事情。然后 Shopify 成为了第一家采用一堆其他工具的公司，他们给了无限的预算，花了大量时间来解决 bug。但他们这样做的原因是，这让我明白了，他们正在权衡用户流失和成本，以及花费更多的钱来处于领先地位。他们比竞争对手领先几个月，或者六个月。对他们来说，这是值得的。对其他人来说，这可能不值得。如果你在一是一家公司，你的业务是实体产品，你不在乎，那好吧，就等着吧，它会来的。但对于我们科技行业中的很多人来说，这个转变是值得的。

此外，Farhan 告诉我，他告诉我他现在有点担心成本。但他又说，“看，它仍然是值得的，因为如果我说‘你们不能使用这些工具’，那会显得很傻，我怎么招聘最好的人才呢？”
<details>
<summary>Original English</summary>

**Host**: Yeah. Um, actually a lot of these topics are exactly the things I cured for tomorrow. Uh, it's just fantastic to have you as the closing keynote for today because uh, it's, it's like an appetizer for tomorrow. We have talks about MCP gateway and all these sort of AI architecture and infra things and I do think like uh, infra like taking AI infra seriously as a company is uh, very mis not that well un understood and right now you just kind of learn by example from people because there's not really like a textbook or anything like about it. So the way I think about this because again from if you just kind of step out and we love to criticize big tech of how they're wasting money here and there and by the way we love to criticize Google and I'm kind of thinking to myself like hang on what if Google ex actually executed well like do we want that and you know they would kill all the startups but but what they're doing makes makes sense and Shopify is an example where I'm like huh I'm starting to get why it makes sense to do all this stuff. So Shopify in 2021 they were the first company to have access to a GitHub copilot. What happened is the the head of engineering fartoir heard about GitHub copilot being developed internally inside of GitHub and he pinged Thomas Dunca the CEO of GitHub at the time and said hey Thomas I heard you guys are doing C-pilot and he's like yeah we are it's internal. He's like I I'd like to get access to it. He's like yeah but it's not for sale. He's like no no no you don't understand. I I didn't ask if it's for sale. we would like to roll it out to all of Shopify and in return we will give you feedback for 3,000 people for you know as honest feedback all the time and so they got it a year before it was out anywhere and they incurred a lot of churn. It wasn't that great initially and and they went through all of this stuff and then Shopify was the first company to on board to like a bunch of other tools and they gave unlimited budget and they're spending so much time ironing out bugs. But the reason they're doing it, this is what like made me click is they are trading off churn and expense and spending a lot more money to be at the forefront of this. They are a few months ahead or six months ahead of their competition and for them it's worth it. It's not worth it for anyone else, right? If you're if you're at a company where your business is like something something physical and you don't care like yeah, just just wait out it it'll come. But for a lot of us in the tech industry this turn is worth it. Plus what Farhan told me is like because he actually told me he's kind of worried about the cost now. But he was like look like it's still worth it because if it would look silly if I said you cannot have these tools, how would I hire the best?

</details>

**主持人**: 所以，这是创新、招聘，当你思考时，它似乎是有道理的。而且奇怪的是，每个人都在同时做这件事。所以它看起来很傻，但它是理性的。
<details>
<summary>Original English</summary>

**Host**: So it's it's innovation, recruitment and it kind of makes sense when you think about it. And the weird thing everyone is doing it at the same time. So it looks silly but it, it's rational.

</details>

**Gergely Orosz**: 嗯，我的下一个播客是与 Shopify 的 CTO Mikuel Parkin 交流。他们为客户提供的机器学习和基础设施数量之多，让我产生了想成为他们客户的念头。你知道，这是我能给出的最好的赞誉。嗯，我想稍微深入地谈谈 Meta 和 Pragmatic Engineer。嗯，你和我大概是在 COVID 期间开始的。嗯，你刚离开 Uber。嗯，它的发展如何？你感到骄傲的主要数据有哪些，你想与世界分享？

是的，我创办了 Pragmatic Engineer。我开玩笑说，如果不是因为 COVID，我可能永远不会创办这个东西，因为 COVID 发生时，Uber 进行了裁员，而大多数科技行业都在蓬勃发展，但 Uber 却不是。我的团队也受到了裁员的影响，然后我们不得不将剩余的员工分散到其他团队，因为我们的使命不再有意义，士气低落，我的士气也很低落，所以我就想，“让我休息一下吧。”我想写几本书。《The Coding Career》这本书就是 Swix 写的。
<details>
<summary>Original English</summary>

**Gergely Orosz**: Uh, my next podcast is with Mikuel Parkin the CTO of Shopify and uh, the sheer amount of machine learning that they do and infra that they set up for their customers makes me want to be a customer. You know, that's that's like the best uh, endorsement I can give. Um, I'm going to get meta a little bit and talk about pragmatic engineer. Uh, you and I kind of startedish in COVID. Uh, you just left Uber. Uh, how has it been growing? What, what are the main stats that you're proud of that uh, you'd like to share with the world? Yeah. So I I started pragmatic engineer I I I a joke that if it wasn't for co I I would probably never have started the this thing because what happened with co is uh, Uber had layoffs and most of the tech industry was doing great but Uber was not and my team uh, was hit by layoffs and then we we had to disperse the remaining people at other teams because our mission no longer made sense and it was just like a the morale was low my morale was low so I was like let me take a break. I wanted to write some books. Swix was writing his book the the coding career.

**Host**: Yeah, some of you have read it. I've met some of you.

</details>

**主持人**: 是的，你们中的一些人读过。我见过你们中的一些人。
<details>
<summary>Original English</summary>

**Host**: Yeah. and and that that's how we met there.

</details>

**Gergely Orosz**: 是的，我们就是这样认识的。然后，我的计划是写一本书，然后创办一家初创公司，做一些平台工程师的东西，Ctrl+C, Ctrl+V，复制 Uber 内部的做法。事实上，几乎所有的 Uber 初创公司都源于此，这真是太令人惊讶了，Temporal 就是从中出来的。
<details>
<summary>Original English</summary>

**Gergely Orosz**: And then uh, my plan was to write a book and then start start up some startup something something platform engineer control C, control V from what Uber was doing inside and that's actually almost all Uber su Uber startups it's it's amazing temporal is is is from there.

**Host**: if I by the way, if I did not start AI engineer I would have started platform engineer.

</details>

**Gergely Orosz**: 那本可能就是行业会议了。
<details>
<summary>Original English</summary>

**Gergely Orosz**: that that would have been the industry conference.

</details>

**主持人**: 是的，很喜欢。
<details>
<summary>Original English</summary>

**Host**: yeah, love it.

</details>

**Gergely Orosz**: 然后我创办了 Pragmatic Engineer，在我离开 Uber 一年后。最初只是一个实验。嗯，我当时觉得 Substack 正在兴起，但没有人深入撰写关于软件工程的文章，于是我就故作自信地声称我“知道我在做什么”。第一篇文章是关于 Uber 的平台和项目拆分，这是以前从未有人公开写过的，而且是一篇免费文章。你现在可以去看看。嗯，我几乎立刻就感受到了产品市场契合（product market fit）。在发布任何内容之前的第一个星期，仅仅凭一条自信的推文，就有 100 个人预付了 100 美元订阅一整年，当时我就想，“哇，我还没发布任何东西呢。”六周后，我有 1000 人为这个前所未有的事物付费，这相当于我以前在阿姆斯特丹的 Uber 的基本工资。然后它就一直增长。所以，我当时就想，当你找到产品市场契合时，这就是……有一个规则，如果你找到了产品市场契合，就继续做你正在做的事情。所以对我来说，我只是一直在写那篇文章。我收到了所有这些采访请求、合作、播客。我一一拒绝了，因为我知道最重要的事情是做能让它成功的事情，那就是那篇文章。后来它变成了两篇文章。两年里，我就只做了这两篇文章。两年后，我抬头一看，心想，“嗯，这东西确实在奏效。人们喜欢它。我喜欢做它。它有未来。”

于是我决定，我真的想把这件事变成一项事业，这样我就不会耗尽心力，因为这两年里，我每次度假都工作 50-60 小时。我总是在思考，我在写作，我真的放不下。所以，我开始稍微扩大团队。嗯，我请来了 Ellen Bird，她是第一个二级研究员，Ellen，她是前……
<details>
<summary>Original English</summary>

**Gergely Orosz**: And then I start I started the pragmatic engineer uh, a year after I left Uber. It was just an experiment. Um, I figured no one Substack was taking off. No one was writing about software engineering in-depth and I just acted all confident saying pretended that I I knew what I was doing. The first article was about Uber's platform and program split that no one had written about publicly before and it's a it's a free article. You can you can now check it out. Uh, and it was like when you feel product market fit, that's what I felt almost immediately. The first week before I published anything, just a confident Twitter post, I had 100 people pay upfront $100 for the whole year, which I was like, whoa, I have published anything. In six weeks, I was at a,000 people paying for this thing that didn't exist before, which was my old Uber base salary back back in Amsterdam. And it just kept going up. So like I I figured like when you find product market fit, this is like outside of like there's this rule like if you find product market fit, just keep doing what you're doing. So for me, I just kept writing that one article. I got all these interview requests, collaborations, podcast. I just said no to all of them because I knew the most important thing was to do what makes it successful, which is that one article. And later it turned into two articles. And for two years, this is all I did, just two articles. And after two years, I looked up and I was like, huh, like this is actually working. People like doing it. I like doing it. There's a future in that. And that's when I decided I actually want to turn this into a business that I don't burn out because for two years every vacation I went to I was working 50 60 hours. I was always thinking I was writing I I couldn't really let go. So I started to grow the team a little bit. Uh, I I Ellen Bird the first secondary researcher Ellen she's ex x ex uh.

**Host**: she's here right?

**Gergely Orosz**: Ellen's not here. Um, Jessica is who who just joined uh, later.

</details>

**主持人**: 她在这里对吗？
<details>
<summary>Original English</summary>

**Gergely Orosz**: Ellen's not here. Um, Jessica is who who just joined uh, later.

</details>

**Gergely Orosz**: Ellen 不在这里。嗯，Jessica 是后来加入的。
<details>
<summary>Original English</summary>

**Gergely Orosz**: And then uh, so now it was two of us. Uh,

</details>

**Gergely Orosz**: 然后，现在是我们两个人。嗯，我一年半前开始做播客，因为我采访了很多人。我当时觉得不把这些内容发出来有点可惜。所以，Pragmatic Engineer 在开始后的四个月内成为了一号付费科技通讯。它在那里保持了三年。现在，Semi Analysis…
<details>
<summary>Original English</summary>

**Gergely Orosz**: and I started a podcast year and a half ago because I talked with so many people. I figured it was a bit of a shame to to not have it. So, the primatic engineer became the number one paid technology newsletter about four months after starting. It stayed there for three years. Now, semi analysis has

**Host**: Dylan versus uh, you guys. Um, yeah. No,

</details>

**主持人**: Dylan 对比你们。嗯，是的。不，
<details>
<summary>Original English</summary>

**Host**: Dylan versus uh, you guys. Um, yeah. No,

</details>

**主持人**: 恭喜你的成功。嗯，我认为你也是欧洲领先的技术声音之一，我认为你在这方面得到了很好的维护，我真的很想在这里特别介绍你。感谢你对 AIE 的支持。嗯，大家，谢谢。
<details>
<summary>Original English</summary>

**Host**: congrats on your success. Uh, I think you're also a leading tech voice in Europe which I think you're sort of proudly sort of uh, upholding that over here which I would really wanted to feature. Thank you for your support for AIE. And uh, everyone thank you.

</details>

**Gergely Orosz**: 好的。太棒了。谢谢。
<details>
<summary>Original English</summary>

**Gergely Orosz**: Good. Awesome. Thanks, man.

</details>