---
author: How I AI
date: '2026-07-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1_jlukb7gm4
speaker: How I AI
tags:
  - content-creation
  - workflow-automation
  - human-ai-collaboration
  - knowledge-management
title: 爬上“AI尴尬山”：如何用AI打造高保真的内容创作引擎
summary: 本期访谈中，10x 联合创始人 Alex Lieberman 详细拆解了其公司内部运行的“内容机器”（Content Machine）工作流。该系统通过 Oracle 扫描多渠道信息提取灵感、利用虚拟面试官面板进行深度访谈并以 WhisperFlow 转写、结合个人风格与历史反馈库进行高保真文案撰写，并由“作家委员会”评审优化。同时，Alex 还分享了公司如何通过“Creator Cup”激发全员创作，用展示代替说教，在 Bootstrapped 模式下以内容分发建立企业护城河、吸引顶尖人才。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - 10x
  - Morning Brew
  - Storyarb
products_models:
  - Claude
  - WhisperFlow
media_books: []
status: evergreen
---
### 缘起与痛点

**Alex Lieberman**: 创建内容为我提供了如此多的机会，但我每天能花在创建内容上的时间是有限的。因此，我一直在思考，如何重新构建我的内容流程，使其成为**AI原生**（AI-native）或**AI辅助**（AI-assisted）的流程。我一直在努力解决的另一个问题是，如何在员工有全职工作的情况下，让他们尽可能轻松地成为**创作者**（creators）。所以，这就是这个**内容机器**（content machine）构想的起源——针对这两个问题进行优化。

<details>
<summary>Original English</summary>

**Alex**: Creating content has afforded me so many opportunities, but I am capped on the amount of time that I can spend creating content every day. And so, I've been basically thinking about how can I re-engineer my content process to be AI native or AI assisted. The other problem I've been trying to solve is how do I make it as easy as humanly [music] possible for employees to be creators while they have full-time jobs. And so, that was kind of the genesis of this content machine idea was optimizing for these two problems.

</details>

**Claire Vale**: 我确实读过你的帖子，写得很棒。所以，它们并没有给我留下“垃圾内容”的印象，但在直播中证明一下吧。我们该如何经历这个流程？

<details>
<summary>Original English</summary>

**Claire**: I do read your posts, they're quite good. So, they don't strike me as slop, but prove it live. How would we go through this process?

</details>

**Alex Lieberman**: 所以，“内容机器”的第一步被称为 **Oracle**（神谕）。Oracle 会扫描我所在的所有频道中过去 7 天的信息，并对想法进行排序，列出一个简短的候选清单。它有一套完整的评分系统，用来定义什么是好的“内容峰值”（content spike），并给予正分。我基本上每天会得到 15 个内容峰值。

<details>
<summary>Original English</summary>

**Alex**: So, the first step of the content machine is called the Oracle. The Oracle just does a scan of the last 7 days of information from all of the channels that I'm in, and it ranks a short list of ideas. And it has like a whole scoring system for what it defines as a good content spike, gives it a positive score. I basically get 15 content spikes.

</details>

**Claire Vale**: AI 在开箱即用的情况下写作能力非常糟糕。你如何让它不写出**垃圾内容**（slop）？

<details>
<summary>Original English</summary>

**Claire**: AI is just out of the box pretty terrible at writing. How you get it to not write slop?

</details>

**Alex Lieberman**: 在我看来，“内容机器”实际产生垃圾内容的唯一情况，与其说是 AI 写得不好，不如说是这个人在访谈步骤中没有分享足够好的想法。

<details>
<summary>Original English</summary>

**Alex**: The only time, in my view, that the content machine actually produces slop is more of an indictment of the person not sharing good enough ideas during the interview step than the AI writing bad stuff.

</details>

**Claire Vale**: 啊哦，所以你的意思是，我们自己才是那个“垃圾”？

<details>
<summary>Original English</summary>

**Claire**: Uh-oh, so what you're saying is we are actually the slop.

</details>

**Alex Lieberman**: 我的看法是，人们指责 AI 垃圾内容，搞笑的是，这其实就像是人们把手指指向自己，然后说“我不够聪明”。

<details>
<summary>Original English</summary>

**Alex**: My take is that AI slop is hilariously people just pointing the finger at themselves and saying I'm not intelligent enough.

</details>

**音乐**: [背景音乐播放]

<details>
<summary>Original English</summary>

**music**: [music]

</details>


### 尴尬山挑战

**Claire Vale**: 欢迎收看《How I AI》。我是 **Claire Vale**，这里的一位产品负责人 and AI 狂热者，我们的使命是帮助你利用这些新工具更好地进行构建。今天，我们邀请到了 **10x** 的 **Alex Lieberman**，他将向我们展示他如何攀登“尴尬山”（Cringe Mountain），也就是他如何在公司利用 AI 打造一台“内容机器”。猜猜怎么着？他并没有产生 AI 垃圾内容。对于任何想要营销自己的公司并在分发上获得优势的人来说，这都是一个非常棒的工作流。让我们开始吧。

插播一段我们今天赞助商 **Firecrawl** 的简短介绍。如果你正在构建 AI 智能体，你可能遇到了同样的瓶颈。你的智能体需要来自网络的数据，但合适的页面很难找到，有些被埋在 JavaScript 中，或者被挡在登录墙后面。**Firecrawl** 是一款网络数据 API，它能让智能体在大规模下搜索、抓取网页并与网页交互，从而获取它们能够实际使用的干净、结构化的数据。包括我在内的超过 100 万开发者都在使用它。它是开源的，而且可以免费开始使用。别再为了数据与网页作斗争了，今天就访问 firecrawl.dev 并使用代码 `howiai` 获得 10,000 个免费额度，为你的 AI 智能体和应用提供动力吧。

<details>
<summary>Original English</summary>

**Claire**: Welcome to How I AI. I'm Claire Vale, product leader and AI obsessive here on a mission to help you build better with these new tools. Today, I have Alex Lieberman at 10x, and he's going to show us how he climbs Cringe Mountain, aka builds a content machine at his company by using AI. And guess what? He doesn't get AI slop out. This is an awesome workflow for anybody trying to market their company and get an edge on distribution. Let's get to it. Quick word from today's sponsor, Fire Crawl. If you're building with AI agents, you've probably hit the same wall. Your agent needs data from the web, but the right pages are difficult to find, buried in JavaScript, or blocked behind logins. Firecrawl is a web data API that lets agents search, scrape, and interact with the web at scale, and get that clean, [music] structured data they can actually use. Over a million developers, including myself, build on it. It's open source, and it's free to start. [music] Stop fighting the web for data, and start powering your AI agents and apps with Firecrawl at firecrawl.dev. Use code howiai to get 10,000 free credits today.

</details>

**Claire Vale**: Alex，我对这一期节目感到非常兴奋，因为我告诉所有人，为了取得成功，尤其作为一个自食其力的创业者，你必须做一件事，而且那不是什么“氛围检查”（Vibe Check），而是爬上“尴尬山”（Cringe Mountain）。你必须发帖。你必须在 X 上发帖，你必须在 LinkedIn 上发帖，你必须谈论你自己。而且我想说，作为一个真正的工程师中的工程师（engineer's engineer），为了避免谈论我的业务，我几乎愿意构建任何东西。

<details>
<summary>Original English</summary>

**Claire**: Alex, I am excited about this episode because I tell everybody, in order to make it, certainly as a bootstrapped entrepreneur, you have to do one thing, and it's not Vibe Check, it is climb cringe mountain. You have to post. You have to post on X, you have to post on LinkedIn, you have to talk about yourself, and I will say, as a true engineer's engineer, I will build literally anything to avoid talking about my business.

</details>

**笑声**: [笑声]

<details>
<summary>Original English</summary>

**laughter**: [laughter]

</details>

**Claire Vale**: 大家听到这个应该不会感到意外。所以，请告诉我，你是如何开始使用 AI 的？你为什么要开始使用 AI 来构建你公司的内容引擎？

<details>
<summary>Original English</summary>

**Claire**: People won't be surprised about this. So, please tell me, how have you started to use AI? Why did you start to use AI to build the content engine at your company?

</details>


### 内容创作流

**Alex Lieberman**: 首先，非常感谢邀请我。所以，首先，我完全赞同攀登“AI 尴尬山”这个说法。我可能站在光谱的完全相反的一端，也就是说，我乐于表现得有些尴尬，并且尽可能多地尝试，去推销我正在做的事情。因为我的信念是，有些人相信“只要你构建了它，人们就会来”（if you build it, they will come），但在当今**分发**（distribution）比以往任何时候都更加重要的世界里，我不认为情况必然如此，或者说大部分情况下都不是这样。所以，在 **10x** 的背景下，我一直在尝试解决两个问题。对于那些还不知道 10x 是什么的人来说，**10x** 是一家应用 AI 公司，致力于帮助中型市场和企业公司进行 AI 转型。我们做从策略到前线部署工程的一切事情。首先，我在互联网上创作内容已经有 10 年了，基本上是从我大学时创办 **Morning Brew** 开始的。我认为创作内容为我提供了很多机会，但我每天能花在创作内容上的时间是有限的。我想说我只有 25% 的时间可以用来创作内容。因此，我一直在思考如何最大化这 25% 时间的价值？我思考了很多关于如何重新构建我的内容流程，使其成为 AI 原生或 AI 辅助的流程，同时确保我不会产出 AI 垃圾内容。因为我认为，人们对 AI 产生反感的原因，特别是在内容创作方面，是因为它往往会吐出一些非常平庸的东西，听起来就像互联网上已经说过的其他话一样。其次，对于我构建的每一家企业，无论它是一家媒体公司还是非媒体公司，我认为我们未来都需要更多地考虑在我们的业务之上建立媒体公司。原因是在后 AI 时代，技术变得比以往任何时候都更加商品化，商业中的**护城河**（moats）越来越少，而我相信“受信任的分发”就是其中之一。所以，总的来说，我正在 10X 之上建立一家媒体公司，我认为我会做所有显而易见的事情，比如把全职创作者和作家带入团队，我们将拥有一个时事通讯等等。但是，我不记录有足够多的公司在考虑将自己的员工转变为创作者（如果他们想这么做的话）。因此，我一直试图解决的另一个问题是：在员工有全职工作的情况下，如何让他们尽可能轻松地成为创作者？这就是**内容机器**构想的起源，优化了这两个问题。

<details>
<summary>Original English</summary>

**Alex**: Well, first of all, thanks so much for having me. So, I, first of all, I totally ascribe to climbing uh AI cringe mountain. I I probably uh move on like the totally opposite side of the spectrum, which is like, I am happy to be cringey and just like shoot as many shots on goal to to sell kind of what I'm doing, because my belief is people who believe that like, if you build it, they will come, I just, in a world in which distribution is more important than ever ever before, I don't think that's necessarily the case, or isn't most of the time. So, basically there have been two problems within the context of 10X that I've been trying to solve. And just for folks that don't know what 10X is, applied AI company helping mid-market and enterprise companies go through their AI transformation. And we do everything from strategy to four deployed engineering. So, the first is I have been creating content on the internet for the last 10 years, basically since I started um Morning Brew when I was in college. And I think creating content has afforded me so many opportunities, but I am capped on the amount of time that I can spend creating content every day. Like I would say 25% of my time can be spent creating content. And so I've been basically thinking about how can I maximize the value of that 25% of my time? And what I've thought a lot about is how can I re-engineer my content process to be AI-native or AI-assisted while making sure that I'm not putting out AI slop because like I think that's what creates so much aversion to AI for people, especially around creating content, is that it's just going to spit out kind of just really mid stuff that sounds like everything else that's been said on the internet. The second is, you know, every business I build, whether it's a media company or a non-media company, I think we need to think more about building media companies on top of our businesses in the future. And the reason for that is in a post-AI world where technology gets more commoditized than ever before, there are fewer moats in business, and I believe that trusted distribution is one of them. So, overall I am building a media company on top of 10X, and I think that, you know, I'm going to do all the obvious things like bring full-time creators onto staff, writers, we're going to have a newsletter, all these things. But I don't think enough companies think about turning their own employees into creators if they want to do that. And so the other problem I've been trying to solve is how do I make it as easy as humanly possible for employees to be creators while they have full-time jobs? And so that was kind of the genesis of this content machine idea was optimizing for these two problems.

</details>

**Claire Vale**: 我喜欢这个，因为我自己也经历过这个阶段。你知道，我曾经在 **TikTok** 担任首席产品官（Chief Product Officer）。在我担任这些职位的过程中，我认为作为高管的工作之一就是成为公司的营销面孔。在 SaaS 领域，你买的不是产品，而是**路线图**（roadmap）；而我会告诉我的团队，他们买的不是路线图，而是**团队本身**，即他们相信这个团队能够实现这一愿景，所以他们愿意通过订阅、参与或其他方式将赌注押在团队身上。我现在和很多 CEO 交流过，他们对目前的营销现状感到非常焦虑，现有的渠道边际效应递减，老一套的做法没法真正起作用。我会告诉他们每一个人，你们的第一大营销渠道应该是你们的员工。所以，我很高兴你在这方面进行了投入。现在我最大的担忧是——我也有一个包含 AI 的内容分发引擎在运行——AI 在开箱即用的情况下，写出引人入胜的文案的能力是非常糟糕的。我想我们都见过这种情况，我们都对此非常挑剔，但你似乎解决了这个问题。所以我很想听听你的一点流程，你认为 AI 适合在哪里，不适合在哪里，以及你如何让它不写出垃圾内容。

<details>
<summary>Original English</summary>

**Claire**: I love this because one I I went through this myself. You know, I am uh at Chief Product Officer on TikTok. I went through this phase where I was like, you know what? Part of my job as an executive when I had those jobs was to be the marketing face of the company and you know, I used to say in SaaS you were you weren't buying the product, you were buying the road map and what I would tell my team is they're not buying the road map, they're buying the team, which is like they believe this team can execute on the vision and so they want to bet with either a subscription or an engagement or whatever on the team. And I talked to a lot of CEOs right now that are really unsettled by the current state of marketing where existing channels have diminishing returns, they're not seeing the old stuff really work and I every single one of them I tell, your number one marketing channel should be your employees. And so I love that you're investing in this. Now my my big concern is um and I have a little bit of a you know, content distribution engine going as well with some AI in it. Is AI is just out of the box pretty terrible at writing compelling copy. And I think we've all seen this. We're all really critical of it, but it seems like you figured this out. So I'd love to hear just a little bit of your process, where you think AI fits, where it doesn't, how you get it to not write slop.

</details>

**Alex Lieberman**: 是的，完全同意。我这里有几个想法。我们之前聊过这个，就是 **Lulu Meservey** 曾谈到过这样一个观点：当世界上最好的作家使用 AI 时，这是一种耻辱，因为他们限制了自己的上限；所以她的观点是，AI 会提高糟糕作家的下限，但会限制优秀作家的上限。在细微差别上，我同意这一点。我要说的第一点是，写作 and 创作内容是一个多步骤的流程，我们待会就会梳理。我认为仅仅说在内容流程的任何部分使用 AI 都会降低你的上限，这不一定是真的。我想，如果我们要说在内容流程的实际起草或编辑部分，使用 AI 会降低你的上限，我能接受并且能够理解，如果你是一个处于顶尖 1% 的天才作家，为什么仅仅依赖于一个在整个互联网语料库上训练出来的模型（因此从定义上讲它就是平均水平），与你这个高于平均水平或杰出的作家相比，会更糟糕，这完全理解。但内容流程有很多部分，我认为在其中一些部分，你可以使用 AI 并且仍然能够继续提高你的上限，而不是降低它。另一部分是，我总是考虑替代方案。所以，对于我们 10x 的团队来说，替代方案（我们待会可以聊聊我们是如何激励大家去创作的），在有了这套内容机器之前，替代方案就是大家根本不创作内容。这就像，如果我有两个选择，让大家围绕他们的专业知识和他们在工作中做的事情来创作内容，或者完全不创作，我当然会在每一天都选择前者。因此，我可以带你了解一下我是如何思考我的内容流程的，以及我是如何改造它的。尽管我们是在使用 AI 创作内容的背景下讨论的，但我们在 10x 的观点和我的观点是，你其实可以将这种流程图解和重建应用到你工作中的任何流程中。这只是我所熟悉的领域。好吧。所以，当我开始这个流程时，我基本上只是画出了今天的内容流程是如何运作的。对于任何创作内容的人来说，你基本上都是从寻找**灵感**（inspiration）开始的。从历史上看，不仅是第一次尝试创作内容的人，我其实甚至会说，尤其是对于内容创作者来说，最困难的事情就是寻找那些感觉新颖、有趣、不像互联网上已经被说过的疲惫重复的想法，这真的很困难。所以第一步是寻找想法。第二步或者说 1B，如果这是一个与你亲身经历相关的想法，你对这个想法完全了解，那么你可以跳过研究步骤。但对于很多想法，你必须进行研究。接下来的步骤是，把你的所有想法都写在纸上，这有点像对这个想法进行“思维倾倒”。下一步，你决定你想围绕这个想法创建哪种**锚定格式**（anchor format）的内容，无论是长篇网站文章、LinkedIn 帖子、时事通讯等。然后你开始写，接着审查草稿，修改它，所以你经历编辑流程，发布它。然后，正如 **Gary V** 在其**内容金字塔**（content pyramid）概念中所谈到的，你将你的锚定内容切碎成微内容，分发到人们消费的所有社交平台或平台上。不管是视频还是写作，这就是内容创作的流程。所以我以此为起点，基本上就是为了明确现在的情况是什么样子的。AI 应该存在于这个流程的哪个部分，以及 AI 应该扮演驾驶员还是副驾驶的角色？

<details>
<summary>Original English</summary>

**Alex**: Yeah, totally. So I have a few thoughts here. We were talking about this before, which is Lulu Meservey has talked about this idea of it's a shame when the best writers in the world use AI because they cap their ceiling and so her view is is AI will raise the floor of bad writers, but then cap the ceiling of great writers. I think I agree with that with nuance. The the first thing I'll I'll say is that writing and creating content is a multi-step process, which we'll go through. And I think just saying that using AI in any part of the content process is going to lower your ceiling is not necessarily true. I think if we were to say for the actual drafting or editing part of the content process, using AI lowers your ceiling, I can buy that and I can understand if you are a gifted writer is in the top 1% of writers, how basically just banking on a model that's been trained on the entire corpus of the internet and so by definition will be average versus you being a above average or an exceptional writer, why it would be worse, totally get that. But there are many parts of a content process and I think some of these parts you can use AI and still continue to actually raise your ceiling, not lower it. The other piece of it is I always think about like alternatives. So, the alternative for, you know, our team at 10X and and we can talk a little bit in a uh in a bit about how we're incentivizing people to create, but the alternative before this content machine was people just not creating content. And so it's like, if I've two options, get people to create content around their expertise and the things that they're doing in work or not create, of course I'm going to take the first every single day of the week. And so, what I can do is kind of take you through how I thought about my content process and then how I transformed it. And even though we're talking about it in the context of using AI for content, our our view at 10X and my view is like, you kind of use this kind of process mapping and then rebuilding for any process in your work. I This is just kind of the world that I know. Okay. So, this is when I started this process, I basically just drew out exactly how the content process works today. So, for anyone creating content, you basically start by finding inspiration. And historically speaking, the hardest thing for not even just people who are trying to create content for the first time, but like anyone I would actually say especially people who are creators is finding new ideas that feel novel and interesting and just don't feel like tired regurgitation of what's been said is really hard. So first step is finding an idea. Second step or like one B is if it is an idea related to a lived experience where you feel for fully informed about the idea, then you can skip the research step. But for a lot of ideas you'll have to research. Then the next step is you're going to get all of your thoughts out on paper where it's kind of like the the the mental vomiting of your thoughts around the idea. Next step is you decide what is kind of the anchor format that you want to create a piece of content around whether it's long form website, LinkedIn, newsletter, etc. Then you write the piece, then you review a draft, you revise it so you go through the editing process, you publish it, and then um as kind of Gary V talks about in this idea of the content pyramid, you take your anchor piece of content, you turn it into micro content, and you distribute it across all social platforms or platforms where people consume. So this is the way and whether it's video or writing, this is how the process of creating content goes. And so I started with this to basically be like this is what things look like today. Where does it make sense for AI to live in this process, and then should AI be the driver or should AI be the co-pilot?

</details>


### 构建机器

**Claire Vale**: 我非常想在这里停顿一下，因为抛开内容不谈，这就是我告诉每个试图弄清楚如何在其日常工作和公司中应用 AI 的人所要经历的完全相同的流程。将这种“工作流优先”（workflow-first）的方法作为最容易入手的方式，将 AI 引入系统。因此，我建议切实写下工作流，然后做出是人类、副驾驶还是自动化的决定。我推荐给人们的另一件事是，我说，不要根据你目前的局限性来规划你现在所做的工作流。规划一个在理想世界中、在没有任何约束的情况下你所做的工作流。比如在没有任何约束的情况下，你当然会把这些内容切成多渠道的微内容。在没有任何约束的情况下，你当然会有一个研究助手一直在寻找和挖掘想法。所以，我认为这两件事——写下你的工作流，以及从你设计工作流的方式中移除现有的限制——是非常重要的。我们有一期与 **Suzie** 的 CEO **Matt** 的节目，他在他的营销团队中就是这么做的——他拿到一份通话录音，然后问“我能从中提取多少东西？”，不是根据他的团队能提取多少，而是在理论上能提取多少。然后从一篇内容中派生出上百件事情。

<details>
<summary>Original English</summary>

**Claire**: I would love to just pause here because let's put content aside. This is the exact process I tell everybody to go through when trying to figure out how to apply AI in a function in their day-to-day, in their company. It is like taking this workflow first approach is just the most tractable way to get AI into a system. And so I'm like literally write it out and then make those decisions of like human co-pilot automation. The other thing that I recommend to people is I say like don't don't workflow what you do now given your current constraints. Workflow what you would do in an ideal world given no constraints. Like given no constraints, of course you would cut all this content into multi-channel like a little micro content. Um of course in given no constraints you'd have a researcher always on looking and mining for ideas. And so I think those two things, writing out your workflow, and then also like removing existing constraints from how you design the workflow is really important. We have this episode with um Matt, the CEO of Suzie, and he does this in his marketing team where he's like he takes a a call transcript and he's like how much can I extract out of this? Not in the how much can my team extract out of it, but like in theory. And then kicks off, you know, a hundred different things off of one piece of content.

</details>

**Alex Lieberman**: 完全同意。是的，百分之百。而且我们在为公司和客户进行这种工作流梳理的过程中发现，首先，你最终会意识到，很多效率的提升甚至是与考虑使用 AI 无关的，因为大多数人之前并没有真正做过梳理流程的工作，AI 只是促使他们这样做的强力机制，然后他们就发现了流程中的所有浪费。所以是的，我完全同意这一点，这是个不起眼的工作，但我其实不知道如果你不从这里开始，你怎么重新想象你所做的工作。这也是为什么当我们谈论 AI 导致的失业等问题时，我之所以能做这个流程，是因为我已经做过成千上万次的内容创作了。所以这展示了成为主题专家和拥有垂直专业知识的重要性。至少在目前，这种知识是非常需要的，否则你无法重新想象工作。好的，所以我基本上拿了这个，流程的下一步就是，再次假设没有限制，重建整个系统。而这一过程的产物就是所谓的**内容机器**（content machine）。我将向你展示它是如何工作的。作为一个直观展示，然后我将带你看看我实际运行这台机器的过程。基本上，这里是内容机器的运作方式。第一步被称为 **Oracle**。其核心理念是，内容机器（这只是一组技能的目录，它是 10X 内部 Claude 的一个插件，你可以通过命令行界面 CLI 或 Claude 协同编程工具 Co-work 来运行）它连接到我在 10X 的所有记录系统。包括我的 Slack、Notion、会议记录、Linear、Git、Gmail。它连接了所有这些系统。基本上，Oracle 会扫描我所在的所有频道中过去 7 天的信息，并对想法进行排序，列出它认为很好的内容峰值清单。它有一整套评分系统来定义什么是好的内容峰值。例如，如果有一个相关的个人故事或轶事，它会给一个正分。如果有一个强烈的观点，它会给一个正分。如果有具体的例子，它会给一个正分。因此，每天我基本上会得到 15 个内容峰值。其中一半是 Oracle 查看我的内部系统得出的。另一半则是通过所谓的“互联网阅读”（internet reading）完成的，我向内容机器提供了一份我在 X、LinkedIn 上关注的账号列表以及我常去的网站，它会去查看这些人过去 7 天创作的所有内容，并将这些作为峰值进行分享。比如，你就是我互联网阅读器里的关注对象之一，它会查看你过去 7 天发布的所有内容，当它认为有一个很好的内容峰值可以让我对你的某条帖子进行引用转推或做出回复时，它就会把它分享在列表里。这就是流程的第一步。单就这步而言，可能是整个系统中最有帮助的事情。回到“即使你相信 AI 会创造垃圾内容，不想让它起草你的内容”这一点，单单是帮助你从空白页走向具体想法，我认为就大大降低了摩擦，以至于你会真正养成创作的习惯。好的，然后你选择一个想法，接着进入一个叫做“面试小组”（interview panel）的环节。基本上，面试小组是我将六位世界级面试官（Tim Ferriss, Joe Rogan, Michael Barbaro, Barbara Walters, Howard Stern, 还有 Larry King）的代码化技能。他们会一个接一个地向你提问关于这个话题的问题，直到他们觉得已经获得了足够的信息来创作一篇内容。这里还要补充一点，通常流程是直接从 Oracle 到面试小组。如果你选择了一个你觉得还没有掌握全部信息的话题，你可以运行“研究助手”（research assistant），研究助手会为你提供关于该话题的完整简报。好的，我们通过了面试小组。基本上，我做的是用 **WhisperFlow** 把我的所有回答口述转换成文本。然后它用我的声音起草。内容机器的运作方式是，整个流程（所有这些步骤）都存在于内容机器的仓库中，我们团队中的每个人都拉到了自己的电脑上，但分别地，我们每个人都有一个个人文件夹，其中编码了我们的声音、我们的风格指南以及我们想要从中获取想法的来源。因此，当一篇内容实际被起草时，它实际上是进入我特定的声音和风格指南文件，并使用它来创建这篇内容。为了让你看到它长什么样：我的风格指南里写着，这是 Alex 是谁，他在公司中的角色，这些是他想要推广的自有资产，这些是他的主要锚定内容类型，这里是他的核心集成，这里是他关注的社交媒体账号。你可以看到 Claire 就在那里。这是第一部分，第二部分是声音指南。这是在我启动内容机器时，它通过研究我历史表现最好的 X 帖子和 LinkedIn 帖子生成的，它包含带有声音和语调的执行摘要、钩子（hook）公式、内容结构、引导模式、主题类别。它分解了我历史上表现最好的 10 篇 X 帖子、我表现最好的 LinkedIn 帖子，我的核心 DNA 是什么，我的第一规则（像给朋友发短信一样写作），以及我使用的语言示例，比如“自嘲式的自信”。这个文件真的非常深入。这就是我完整声音的编码。待会我们会讲到，但整个流程中另一个非常重要的部分是，当内容机器为我起草了一篇内容后，我会给它反馈，并且它会从该反馈中获得一个强化循环。因此，内容机器中的另一个文件是“内容教训”（content lessons）的 markdown 文件。它记录了我在过去起草内容时指出它弄错的所有事情。它将这些记录为教训。围绕语调，当我指出语调不对时；结构和流程，当那些不对时。因此，它在编辑内容时总是会检查内容教训 markdown，以确保它不会再犯相同的错误。

<details>
<summary>Original English</summary>

**Alex**: Totally. Yeah, a hundred percent. And what we've found in kind of doing this process mapping process with companies and with clients is first of all, you end up realizing that a lot of efficiencies are found outside of even thinking about using AI because most people have not actually done the process of mapping their processes before and AI was just like the force function to get them to do it and then they find all of this waste in their process. So yeah, I totally agree with this and this is like the unsexy thing to do, but I actually don't know how you reimagine the work you do if you don't start here. It's also why like when we talk about job loss and all these things with AI, the only reason I was able to do this is because I've done the process of creating content you know, thousands of times. And so it shows you the importance of like being a subject matter expert and having vertical expertise. That knowledge at least right now is really needed, otherwise you can't reimagine the work. Okay, so basically I took this and the next step in the process was like again, assuming no constraints, rebuild the entire thing. And so, what came out of that was this thing called the content machine. And I'm going to just show you kind of how it works. Just as like uh a visual and then I'll take you through like me actually running the machine. So, basically here is how the content machine works. So, the first step of the content machine is called the Oracle. And the whole idea is that the content machine, which is just a directory of skills, um it is a plugin in uh you could either do it through the CLI or through Claude Coder Co-work, is it is connected to all of my systems of record at 10x. So, my Slack, my Notion, my meeting notes, uh Linear, Git, Gmail. It is connected to all of these things. And basically what happens is the Oracle just does a scan of the last 7 days of information from all of the channels that I'm in and it ranks a short list of ideas uh that it believes are good content spikes. And it has like a whole scoring system for what it defines as a good content spike. Like if there's a story or an anecdote related, it gives it a positive score. If there's a strong point of view, it gives it a positive score. If there's specific examples, it gives it a positive score. And so, every day I basically get 15 content spikes. Half of them are from the Oracle looking at my internal systems. And then the other other half of them are doing what's called internet reading, where I have provided the content machine a list of the accounts that I follow on X, LinkedIn, and just the websites I go to, and it will go and look at all of the content that's been created by these people over the last 7 days and share those as spikes as well. So, like you're you're one of the people in my internet reader, it will look at everything that you've posted in the last 7 days, and when it thinks there's a good content spike for either me to do a quote retweet on one of your posts or respond, it will share that in the list. So, that's the first step in the process. That on its own is maybe the most helpful thing in the entire, like in this entire system. And going back to the the point of even if you believe that AI will create AI slop, and you don't want it drafting your content, just helping you go from blank page to concrete idea, I think lowers the friction so much that you'll actually get in the habit habit of creating. Okay, so then you select an idea, and then you go into something called the interview panel. And basically, what the interview panel is is I had six world-class interviewers codified each as skills, where there's Tim Ferriss, Joe Rogan, Michael Barbaro Barrow, Barbara Walters, Howard Stern, and they just one by one will ask questions about this topic to you until they feel like they've gotten enough information to create a piece of content. One other thing I'll add here that's just not here is it goes straight from Oracle to the interview panel. If it is a topic, and I'll show you what this looks like in a minute actually in Claude, but if you pick a topic that you don't actually feel like you have all the information on already, you can run the research assistant, and the research assistant will give you a full brief into the topic. So, okay, we go through the interview panel. Uh basically, what I do is I yap to text all of my answers um using WhisperFlow. Then it drafts in in my voice. And so, the way that this works with the content machine is basically, the entire process, like all of these steps, are what live in the content machine repo that everyone on our team has kind of pulled down onto their computer, but separately, all of us have per a personal folder that has codified our voice, our style guide, and like our sources that we want to pull ideas from. And so, when a voice is actually drafted, or when a piece is actually drafted, what's happening is it's actually going into my specific voice and style guide file, and using that to create the piece of content. And so, just to show you what that looks like. So, my style guide here is, you know, this is who Alex is, uh this is his role in the company, these are the owned assets that he's going to want to promote, these are his main anchor types of content, here are his key integrations, here are the social handles that he follows up follows. You see Claire's there, you know, people who give enterprise an exact lens. So, that's the first, and then the second is the voice guide. And so, what this is is basically when I launched the content machine, it studied. So, this is all of my top-performing X posts and LinkedIn posts were studied, has executive summary with voice and tone, hook formulas, content structures, laid patterns, topic categories. And so, this breaks down the top 10 best-performing X posts I've had of all time, my best-performing LinkedIn posts, what my core DNA is, my number one rule, which is writing like you're texting a friend, and then examples of like the language that I use, self-deprecating confidence. Like, it really goes into depth into this file. Like, this is this is my full voice codified. And then, we'll get to it in a minute, but the the other really important piece of this whole process is when a piece of content is drafted by the content machine for me, I will give it feedback, and it will have a reinforcing loop from that feedback. And so, one other file that's in the content machine is the content lessons markdown fold uh markdown file. It is all of the things that I've said it messed up when drafting my content in the past. It logs that as lessons. So, around tone, where I've said the tone wasn't right, structure and flow, when that wasn't right. And so, it will always check the content lessons markdown when editing a piece of content to make sure it's not making the same mistake again.

</details>

**Claire Vale**: 这是在你使用某项技能进行编辑的过程中生成的吗？比如如果你发现了一些反馈，你是手动填充它，还是它自动创建的？

<details>
<summary>Original English</summary>

**Claire**: And is this generated as you go through the editing process with a skill? Like is it like if you identify some piece of feedback, are you manually populating that? How is that getting created?

</details>

**Alex Lieberman**: 内容机器的工作方式是，在内容起草并经历编辑流程（我稍后会展示）之后，我会得到最终的内容。我所做的是对这个最终内容给予反馈。一旦一切搞定，我觉得“这很棒，可以发布了”，就会触发一个作为这些连锁技能一部分的任务，那就是**教训循环**（lessons loop）。教训循环的工作方式是：“让我看看我们提供给 Alex 的原始文章与新文章之间的差异（diff）是什么。我们能从中提取出哪些抽象的教训？”然后我们问 Alex：“你希望把这些教训添加到教训文件中吗？”如果他说“是”，我们就把它们加进去。这就是它的运作方式。最后带你了解完这个流程，然后我可以在实践中向你展示。这就是我的声音被起草的过程。接下来的步骤是，我已经分享了、选择了一个想法。在接受这个面试官小组的面试时，我口述了我关于这些想法的所有思考。然后我选择，比如我想创建一篇 LinkedIn 帖子。它会使用我的风格指南、我的声音 markdown 文件和我的内容教训 markdown 文件，以我的声音起草。一旦草稿完成，它就会提交给“作家委员会”（writers council）。类似于我创建的六个面试官角色，我也创建了六个作家角色。比如 David Perell, Sean Puri, Morgan Housel，以及“AI垃圾内容过敏专家”（AI slop allergist）。他们会去阅读内容，并打出 1 到 10 的分数。如果综合评分低于 9 分，它就会运行一个修改循环，直到打出 10 分。然后就完成了。一旦这篇内容完成，我就可以进行重新利用和分发，这意味着有一个步骤，我可以对内容机器说“我想重新利用这个”。内容机器会问你想把它重新利用成什么？我可以回答：三条简短的推文、两篇长的 LinkedIn 帖子，它就会去查看我过去在这些不同帖子类型中的写作格式，并以那种风格进行撰写。

<details>
<summary>Original English</summary>

**Alex**: So, the way that the content machine works is basically after a piece of content is drafted and then it goes through the editing process, which I'll show you in a second. I get the final piece of content. What I will do is I will give it feedback on that final piece of content. Once it's all done and I'm like, \"This is good to go. This is good to publish.\" There's basically a job that's kicked off as part of like kind of this uh the these like chain together skills and it's the the lessons loop. And the lessons loop is, \"Let me look at what the the diff is between the original piece that we provided to Alex versus the new piece. What are abstractable lessons we can take from that?\" And then we ask Alex, \"Do you want these lessons to be added to the lessons file?\" If he says yes, then we add them in. So, that's how that works. And then just to finish taking you through the process and then I can kind of show you in practice. That's how my voice is drafted. Then the next step is, so I've shared I've picked an idea. I've yapped a text um all of my thoughts around the ideas as I'm interviewed by this panel of interviewers. Then I pick, say I want to create a LinkedIn post. Uh it's drafted in my voice using my style guide, my voice markdown file, and my content lesson markdown file. Once the draft is done, it goes through the writers council. So, similar to how there's the six interviewer personas I created, there's six writer personas I created. So, it's like David Perell, Sean Puri, um Morgan Housel, the uh the AI slop allergist. And they go through, they read the content, and they score it 1 to 10. If the aggregate score is under a 9 out of 10, it runs a revision loop until it scores a 10 out of 10. And then it's done. And then once the piece of content is done, then I can repurpose and distribute, which means there's just a step where I can say, I want to repurpose this. It at the content machine asks, what do you want to repurpose it into? I could say three short tweets, two long LinkedIn posts, and it will go look at what my format of writing in these different uh post types was in the past and write in that style.

</details>

**Claire Vale**: 我认为这再次反映了几件事。第一，规划你的工作流。第二，利用 AI，你基本上可以在没有专家委员会的情况下引入一个**专家委员会**（council of experts）。也就是说，在理想世界中，我希望能被最顶尖的人采访。猜猜怎么着？你可以在你的流程中模拟这一点。我认为在构建这个流程的过程中，寻找正确的强化循环以迭代地使其变得更好是非常有用的，因为你可以以一种过去无法做到的方式来理解非结构化数据的输入和输出。然后，AI 是多模态的。我的意思是，这不仅仅是图像到文本、文本到语音或语音到文本。我指的是文本到微缩文本、文本到长文本。因此，利用大语言模型的这些所有组成部分，我认为让这个特定的用例成为一个非常棒的用例。

<details>
<summary>Original English</summary>

**Claire**: I think again, this is just a reflection of a a couple things, I would say. One, map your workflow. Two, with AI, you can bring in basically a council of experts without having a council of experts. So, again, it's like in this ideal world, I would be I I would be interviewed by the best of the best. Well, guess what? You can approximate that in your process. I think finding the right reinforcement loops on as I'm building this process, how do I iteratively make it better because you can make sense of inputs and outputs of unstructured data in a way you weren't able to do before, is really useful. And then, um you know, AI's like multimodal. And so, and and I mean that not just in like image to text or text to voice or voice to text. I mean it in like text to mini mini text, text to long text. And so, using all those kind of components of of LLMs, I think makes this particular use case a good one.

</details>


### 现场演示

**Claire Vale**: 本期节目由 **Customer.io** 赞助播出。你在这里是因为你更愿意使用 AI，而不是空谈它。有了 **Customer.io**，你只需描述你想要构建的营销活动，AI 智能体就会为你创建。包括受众、信息和发送时机。你进行审查，做出任何你想做的修改，然后发布。不用花几个小时去拼接工具和工作流，你可以专注于真正推动增长的工作。每个营销活动都与结果挂钩，因此你可以看到什么是有效的，以及下一步该做什么。超过 9,000 个品牌使用 Customer.io 将他们已有的数据转化为客户记住的信息。今天就访问 customer.io/howiai 试用吧。Customer.io，让每一条信息产生更大影响力。

我之前在节目开始前确实告诉过你，我读过你的帖子，它们写得非常好。所以，它们并没有给我留下垃圾内容的印象，但在直播中证明一下吧。当场做一次。我们该如何经历这个流程？

<details>
<summary>Original English</summary>

**Claire**: This episode is brought to you by Customer.io. [music] You're here because you'd rather use AI than talk about it. With Customer.io, you describe the campaign you want to build and the AI agent creates for you. The audience, the messages, and the timing. You review it, make any changes you want, and launch. Instead of spending [music] hours stitching together tools and workflows, you can focus on the work that actually drives growth. Every campaign is tied back to results, so you can see what's working and what to do next. More than 9,000 brands use Customer.io to turn the data they already have into messages customers remember. Visit customer.io/howiai to try it today. Customer.io, more impact from every message. I did tell you before we got on, I do read your posts, they're quite good. So, they don't strike me as slop, but prove it live. Do it live. How would we go through this this process?

</details>

**Alex Lieberman**: 让我打开我的 Claude，我将向你展示一个它已经运行过的例子，然后我们也会进行现场操作，如果搞砸了，我乐意当众出丑。所以，好的。基本上我们看到的是内容机器的运行过程。顺便说一下，这可能很有帮助：内容机器是作为 **10x** 内部 Claude 的一个插件存在的，基本上每个人都把它添加到了自己的机器中。每当我在 Git 上向它推送更新时，大家都可以直接从这里自动更新。我一直在试图找出一种对业务中非技术人员来说足够容易接受的方式，以便在我们推送更新时能够让他们从这些更新中受益。我们待会可以聊聊这个，就是把这个分享给业务中的每个人，如何让我们更接近我认为是 Sendbird 的 CEO（他与你一起经历过他们内部探索的人）所经历的事情。但让我先回到这里。所以，基本上，它首先查看了我的来源、内部来源，指出了灵感点。例如，我们经常谈论的“单人 vs 多人 AI 框架”（single player vs multiplayer AI framework）。我和一家银行的人聊过，他们正在与 McKinsey（麦肯锡）合作，McKinsey 给他们提供了一个想法，说这个需要 6 个月才能建成。他说他用 Claude code 在一周内就重建了它。还有我在一次销售电话中对别人说我可能是世界上最差劲的销售员，这听起来是一个好玩的内容峰值。以及我在卖掉 Morning Brew 之后在电话里对别人说我很痛苦，这也是个很好的内容灵感。所以你可以看到，它真的非常善于捕捉特定的故事。然后从互联网阅读器中，它从我在配置文件中提供给它的不同来源中提取信息。其中一个是 Amazon 承诺投入 10 亿美元在 FDE（前线部署工程师）上，Aaron Levie 对比 Ethan Mollick 讨论 FDE 是否是解决每个企业问题的灵丹妙药，以及现在每个人都是构建者，而分发/出货才是困难的部分。然后我只需选择一个我真正想要展开的内容灵感。顺便说一下，内容机器中的另一个功能是，虽然我在这里选择了一个要构建的想法，但这里有几个想法我都认为值得去构建。因此，内容机器的一部分是，当公司里的每个人第一次设置它时，会创建一个“库”（Vault），这个库实际上只是一个 Notion 数据库，由 Oracle 生成的每个想法，即使你没有使用它，也会被添加到这个库中，以便你将来可以去里面提取想法。好的，我选择了灵感 13。灵感 13 我觉得很有意思，Aaron Levie 说 FDE 是目前上帝赐给地球最好的礼物。Mollick 则说不，这不会解决所有问题。所以我选了这个，并且我想做更多关于这个话题的研究，比如围绕 FDE 有哪些不同的论点？为什么 Aaron 和 Ethan 表现出不同的观点？所以接着启动了研究步骤。你可以看到，基本上为我生成了一份关于他们观点的研究简报、已经说过的话、我可以在这里采取的潜在的相反或新颖的角度，以及我应该尝试回答的开放性问题。我事先读了这个。在进行面试时，如果我认为其中有非常好的引用，我也可以把它们拉进我的回答中。于是，我进去，面试开始了。我忘了 Larry King 也在里面了。Larry King 的问题是：“Levie 说 FDE 会赢，因为部署智能体比人们想象的更具技术性。Mollick 说他们会让人失望，因为真正的问题是组织结构和专业知识，而不是代码。而你说他们都对，以下是他们遗漏的部分。所以，用一两句话解释，他们都遗漏了什么？”我提供了我的想法，比如：FDE 是所有问题的解决方案吗？为什么我同意或不同意 Aaron 和 Ethan？随后的跟进问题就是针对我的回答展开的。面试小组真的被训练去从我这里挖掘尽可能多的细节和例子。Tim Ferriss 问：“给我讲讲这个情况痛苦发生的具体项目。一个你们团队在技术上搞定的项目。”他要求我提供一个客户故事。于是我提供了。我们经历了五个问题，然后它说“面试结束”，声音和教训已被锁定。这就是它查看我的内容教训和声音 md 文件的地方。然后创建了 LinkedIn 草稿 md。开头是：“我关注的两个最聪明的人公开在 AI 领域最热门的工作上产生了分歧。他们都对，而这正是问题所在。”顺便说一下，如果我要对这个给出反馈，我会说：“这感觉有点 AI 腔调。他们都对，这正是问题所在，感觉太像那种陈词滥调了。”所以我会给出这个反馈，并说将此添加到内容教训中。“本周亚马逊承诺为前线部署工程投入 10 亿美元，而 OpenAI 和 Anthropic 已经做了相同事情的版本。谷歌正在招聘数百人。”所以，它基本上包含了我的所有思考。比如我的一个回答是“公司需要做什么来为 AI 转型做好成功准备？”，它采用了我的原话。比如“所以，如果你正在为 AI 转型配备人员，你需要这些东西。”它不写垃圾内容的一个主要原因，基本上是因为我训练它只使用我的话。所以我认为这也是一个很大的事情，就是这整台内容机器都是建立在这样一个事实上：我与小组进行的面试只是被转换成了一个包含转录文本的巨大 markdown 文件。除了钩子和结论之外，转录文本实际上应该扮演唯一被使用的词汇角色。作家的工作真的几乎就像是去塑造内容的粘土，而不是发明全新的东西。因此，在我看来，“内容机器”实际产生垃圾内容的唯一情况，与其说是 AI 写得不好，不如说是这个人在访谈步骤中没有分享足够好的想法。

<details>
<summary>Original English</summary>

**Alex**: Let me bring up my Claude and I'll just show you how one example of how it already ran and then we'll do it live also and I will happily embarrass myself if this goes terribly wrong. So, okay. So, basically what we're looking at is the content machine running and and just so you can see cuz this may be helpful like the content machine lives as a plugin in 10X's um our internal Claude and basically everyone has added it to their machine. Anytime I'm basically pushing an update to it on Git, people can just auto update it right from here. Um so, I was trying to figure out something that was for anyone who was not technical in the business was palatable enough to as we push updates to benefit from those updates and we can talk about it in a second like how sharing this with everyone in the business is getting us closer to what I think it was the CEO of Sendbird who went through like their internal quest uh thing with you. Like how we're getting closer to that. But so, let me go back to this for a second. So, basically what this did is it first looked at my sources, internal sources, it pointed out spike ideas. So, this was like a single player versus multiplayer AI framework that we talk about a lot. I talked to someone at a bank who's working with McKinsey and McKinsey gave them an idea and was like this is going to take 6 months to build. He said he rebuilt it in a week with Claude code. Me saying to someone on a sales call that I may be the world's worst salesperson, that sounds like a fun one. After I said to someone on a call after I sold Morning Brew, I was miserable. Like that's a good content spike. So, like you can see it's really latching on like specific stories and then from the internet reader it pulled from the different sources that I've given it in my profile file. So, one was, you know, Amazon putting a billion dollars behind FDEs, Aaron Levie versus versus Ethan Mollick talking about like are FDEs the solution to every enterprise's problems versus not, everyone's a builder now shipping is the hard part. And so then I would just select a content spike that I want to actually build out. And just so you know, here the other thing in the content machine is well, I'm going to select one idea here to build out into a piece of content. There are several ideas here that I think are worthy of building out. And so part of the content machine is when everyone at the company sets it up for the first time what's created is the vault and the vault is literally just a notion database and every idea that is generated by the Oracle, even if you don't use it, is added to this vault. So, you can go into that in the future to pull ideas out of. Okay, so I picked spike 13. And spike 13 I thought was interesting. Aaron Levie saying like FDEs are God's greatest gift to earth right now. Mollick being like no, it's not going to solve all the problems. And so I picked this and I wanted to do more research on the topic around like what are the different arguments around FDEs? Why do Aaron versus Ethan have different perspectives? So then the research step was started up. And you can see basically a research brief was created for me about their takes, what's been said, what are potential contrarian or novel angles that I can take here, what are open questions that I should try to answer. So, I read this beforehand. I can also as I'm doing the interview, if I think there are like really good quotes from this, I can pull that into my answers as well. So, then I go in and the interview starts. So, I forgot Larry King was in here also. So, let let Larry King is like Levie says FDEs win because deploying agents is more technical than people think. Mollick says they'll disappoint because the real problem is org structure and expertise, not code. And he said, \"Uh you said they're both right. Here's what uh what they're missing.\" So, in one or two sentences, what are they both missing? I provide my thoughts on like, are FDs the solution to all? Why do I agree or not with Aaron and Ethan? And then the follow-up question is just playing off of my answer. So, now it asks, \"And and the interview panel is really trained to pull as much specificity and examples out of me as possible.\" So, Tim Ferriss is like, \"Give me the engagement where this was painfully true. A bit uh a build your team nailed technically.\" So, it asked me to like give a customer story. So, I did that. So, we go through. I was asked five questions. Then it says, \"Interview's a wrap.\" And voice and lessons locked in. So, this is where it looks at my content lessons and voice MD file. And then LinkedIn draft MD is created. So, here two of the smartest people I follow just publicly disagreed about the hottest job in AI. They're both right and that's exactly the problem. By the way, if I was to give feedback on this, I'd be like, \"This feels kind of AI cringey. They're both right like the the two the the punch Yeah, the this that is just is like the the newest M dash.\" And so, I'd give that feedback and I'd say add this to content lessons. This week Amazon committed a billion dollars to afford deployed engineering or open AI and Anthropic already did versions of the same thing. Google is hiring hundreds. And so, just it includes basically all of my thoughts here. Like, one of my answers was, \"What do companies need to set themselves up for success for AI transformation?\" and it took my exact words. Where it was like, \"So, if you're staffing AI transformation, you you need these things.\" One of the reasons that this doesn't write slop mostly is because I have basically trained it to only use my words. So, I think that a big thing also is like this whole content machine is built on the fact that the interview I do with the panel is just turned into a large markdown file of the transcript. And the transcript really should be the only words that are used other than maybe the hook and the conclusion. And the job of the writer is really to almost be this like like sh- like shaping the clay of the content, not inventing net new things. And so, the only time, in my view, that the content machine actually produces slop is more of an indictment of the person not sharing good enough ideas during the interview step than the AI writing bad stuff.

</details>

**Claire Vale**: 啊哦，所以你的意思是，我们自己才是那个“垃圾”？

<details>
<summary>Original English</summary>

**Claire**: Uh-uh. So, what you're saying is we are actually the slop.

</details>

**Alex Lieberman**: 我的看法是，人们指责 AI 垃圾内容，搞笑的是，这其实像人们把手指指向自己，然后说“我不够聪明”。然后它做的另一件事，我最近刚刚把它作为一个内容教训添加进去，就是我说：“开始给我提供更多钩子的例子，因为我想能够进行选择和比较。”所以它提供了钩子和结尾。我在这里会做的是……哦，它甚至还没有运行作家委员会。是的，让我们来运行委员会吧。所以它现在要做的是它有了草稿，有了钩子和结尾，它要运行编辑委员会。如果超过 9 分，它会原样给我。如果不是，它会运行一个修改循环。然后当得到它时，我会给出反馈，就像我对你给出的关于那个“如果是这样，那么那样”的句子很俗气的反馈一样。我会过一遍，确保它们被添加到内容教训 markdown 文件中，然后我做最后一次修改并发布这个。而且我的观点是（这也是我想添加到内容机器中的东西），目前内容机器在我运行 Oracle 时，它没有提取我应该考虑重新利用的以前的内容。这应该是我每天运行的一部分。所以，看，他们现在都在评分，我能看出来它不会达到 9 分，所以他们要运行一次完整的修改循环。

<details>
<summary>Original English</summary>

**Alex**: That is This is my take is that AI slop is hilariously people just pointing the finger at themselves and saying, \"I'm not intelligent enough.\" And so, and then the other thing it does, and I just actually recently added this in as a content lesson, is I was like, \"Start giving me more examples of hooks because I want to be able to choose and compare.\" So, it provides hooks and closings. And so, what I would do here Oh, so it didn't even run the writer's council. Yeah, so let's just even do that. Run the council. So, what it's going to do now is it has the draft, it has the hooks and closings, it's going to run the editorial council. If it's above a 9 out of 10, it'll give it to me as is. If it's not, it'll run a revision loop. And then what I would do after, when I get it, is I will give it feedback like the feedback I gave you around that like if this then that line being cheesy, I'll go through, I'll make sure they're added to the content lessons markdown file, and then I'll take a final pass and I'll post this. And then my view, and this is something I want to add to the content machine, is right now the content machine is not when I run the oracle, it's not pulling previous pieces of content that I should that should think about repurposing. That should be part of the run I do every single day. And so, see, they're they're all grading right now, and I can already tell it's not going to be a 9 out of 10, and so they're going to run a full revision loop.

</details>

**Claire Vale**: 天呐，我太喜欢这个了。然后你就要把它发到线上。

<details>
<summary>Original English</summary>

**Claire**: Oh my gosh, I love it. And then you're going to get this live.

</details>

**Alex Lieberman**: 是的。就在我们做完这个之后，我会把它发到线上。

<details>
<summary>Original English</summary>

**Alex**: Yep. So, like I will, right after we are done with this, I will post this live.

</details>

**Claire Vale**: 好吧，然后我想说，也许我想在结束这个流程之后讨论一下，你已经向我们展示了端到端的流程，比如我们如何发现一个好想法？

<details>
<summary>Original English</summary>

**Claire**: Well, and then what I want to say, you know, maybe what I want to cover after we've we've wrapped this flow, which you've kind of showed us the end to end of like how how do we discover a good idea?

</details>

**Alex Lieberman**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>


### 创作者杯

**Claire Vale**: 我们如何通过我们的朋友 **Hillary Gridley**，通过 **Yappers API** 提取我们所有的好想法，我们如何用我们自己的声音塑造它，然后得到一些关键的反馈并发布出去？但你也不完全是 100% 依赖 AI。你也有你的团队，并且你正在改变团队的行为，让他们都拥抱这种新的内容创作模式。那么，你能带我们了解一下你的内容机器中非 AI 的部分，以及你在公司中正在尝试的一些事情吗？

<details>
<summary>Original English</summary>

**Claire**: How do we extract um via again, our friend Hillary Gridley, um via the Yappers API, all of our best ideas. How do we shape that in our voice and then get some critical feedback and ship it? But you're also it's not 100% AI. You also have your team and you're changing team behaviors to all embrace this new model of content creation. So, can you just walk us through some like the non-AI parts of of your content machine and some things you're experimenting with at the company?

</details>

**Alex Lieberman**: 好的。首先，我不想声称自己是员工代言（employee advocacy）的发明者。这已经存在很长时间了，但我认为互联网以及建立在其之上的平台已经赋予了它前所未有的力量，以至于我认为很多公司还没有跟上它的步伐，或者他们太担心给公司里每个人都发一个麦克风的风险，以至于他们最终没有做这件事。所以，我第一次测试这个是在我创办的另一家名为 **Storyarb** 的企业里，当时我们开展了一个名为“拥有互联网”（Own the Internet）的活动。其想法是，这是一个为期六到八周的活动。Storyarb 的每个人都必须（或者说被鼓励）在 LinkedIn 上发帖，并且有机会赢取奖金。我想赢家会得到大约 5,000 美元。唯一的规则是，你创作的内容中必须有 50% 属于 Storyarb 所做业务的领域。结果它为业务带来了非常巨大的流量。在我们运行“拥有互联网”的那个季度里，它为我们带来了 40% 的入站线索（inbound leads）。它为我们的招聘带来了大量的漏斗顶部流量。所以，我知道在未来，任何有这样机会的场合，我都会这样做。实际上，我们昨天刚刚启动了 10X 版本的活动。所以，我会分享一下这背后的细节。它被称为“**10x 创作者杯**”（10x Creator Cup），是一个为期一个月的挑战，旨在鼓励 10x 的每个人进行发帖。玩法是，你只需在 LinkedIn 或 X 上发帖，然后我们在内部有一个名为 `Reply Guys` 的 Slack 频道，这就是大家在创作者杯期间可以看到每个人帖子的地方。其规则是：每次发帖你得 10 分。每次你与公司其他人的帖子互动，你得 3 分。每周，我的合伙人和我都会对当周的最佳帖子进行“编辑精选”，你会获得加 50 分。而且还有每周游戏和月度游戏。这里的核心点在于，我们想要鼓励大家发帖，这不仅仅是一场展示次数（impressions）的竞争，避免某个人凭展示次数碾压所有人，我们不希望其他人觉得自己没有机会。我们也希望让大家觉得参与这个游戏是有意思的，仅仅玩这个游戏就能得到一些东西。比如本周的周游戏叫“满堂彩”（Full House），如果本周公司里至少 70% 的人都至少发帖一次，我们就会解锁第一周的奖品，每个人都会得到一张彩票，我们会抽出一个人，本周他们可以赢得几百美元。所以我们本周将发放 5,000 美元的奖金。但有意思的是，我们之前谈到了这个，我说：“在 10x，我们是在用‘困难模式’玩游戏。”而你问我们是不是在用‘诚实模式’玩游戏？是的，10x 是完全自食其力（bootstrapped，自筹资金）的，我认为这要求我们在某些事情上必须有创意。其中一件事是，我们确实拥有我这辈子合作过的世界上最好的工程师。这有几个原因。但我们还没有像 OpenAI 或 Anthropic 那样的高知名度，对吧？而且因为我们没有筹集大量的资金，我们也没有在 TechCrunch 上被报道以及被所有这些顶级投资者提及的能见度。so，问题就变成了，当我们没有风投支持的公司所拥有的所有优势时，我们如何吸引顶尖人才？我的部分看法是，方法是让你的顶级人才通过“展示”而不是“说教”来呈现他们正在做的酷炫工作。因此，对我来说，即使“10x 创作者杯”没有为我们的业务带来任何销售线索，如果它只是让更多的工程师了解 10x 并向 10x 申请工作，在完美的情况下，如果我们能通过这整个活动雇用到一名工程师，那么我们为“10x 创作者杯”付出的 5,000 美元就已经值回票价了。因为你想想你付给招聘机构招募一名工程师的费用，这完全是值得的。所以，是的，我认为我们应该倾向于“bootstrapping”这回事，这就是保持挑战者心态，使用游击营销，大家齐心协力为 10x 创造这种光环。

<details>
<summary>Original English</summary>

**Alex**: So, this actually this content First of all, the I do not want to claim to be the inventor of employee advocacy. This has been around for a very long time, but I just think that the internet and the platforms on top of it have enabled it in a way that I don't think companies have caught up to it or they worry so much about the risks of giving everyone in your company a megaphone that they don't end up doing it. And so, I tested this for the first time at um one of my other businesses called Storyarb, where we did a campaign called Own the Internet and the idea was that uh it was going to be a six- or eight-week campaign. Everyone at Storyarb had to post on LinkedIn or not had to. They were encouraged to and there was an opportunity to win money. Like I think it was like 5,000 bucks the winner would get. And the only rule was that 50% of the content you create has to be within the world of what Storyarb does. And it ended up driving so much traffic for the business. It drew in the quarter that we ran Own the Internet, it drove 40% of all of our inbound leads. It drove a ton of top of funnel for hiring. And so, I just knew that I would do this like any opportunity I have to do this, I will do it moving forward. And so, we literally just started yesterday 10X's version of this. And so, I'll just share like what the uh details are behind it. So, it's called the uh 10X Creator Cup and it's a month-long challenge to get everyone at 10X posting. And the way you play is you just post on LinkedIn or X, and then we have a Slack channel internally called Reply Guys, and that's where everyone can just see everyone's uh posts throughout the uh Creator Cup. And the way it works is every time you post, you get 10 points. Every time you engage with someone else in the company's post, you get three points. Every week, my co-founder and I will do an editor's pick of the best post of the week, you'll get plus 50. And there are weekly games, and then there's month-long games. And the whole point here is we want to encourage people to post where it's not just a race for impressions, where one person ends up crushing it with impressions. It's like you you we don't want people feeling like they don't have a chance. And we also want it to feel palatable for people, where just like playing the game is is going to get you something. So, even example this week is the week-long game this week is called full house, where if at least 70% of everyone in the company posts at least once this week, then we unlock the one week the week one prize, where everyone gets a a um lottery ticket, and we pull one person and they win a couple hundred bucks this week. And so, we're giving out $5,000 of prizes this week. But the interesting thing here is like we're talking about this earlier. And I And I said, \"10X, we're playing the game on hard mode.\" And would you say you're playing the game on honest mode? Yeah, like I think so, 10X is fully bootstrapped, and I think it requires us to have to be creative with certain things. And one of those things is we truly have the best engineers that I've ever worked with in the world. And there's there's a few reasons for that. But we do not have like the gravitas yet of a lab, right? Like OpenAI or Anthropic. And because we haven't raised a boatload of money also, we don't have like the visibility of being on TechCrunch and being mentioned by all of these top-tier investors. And so, the question becomes, how do we attract top talent when we do not have all the advantages that a venture-backed company would have? Part of my view is is the way you do it is have your top talent show versus tell the cool work that they're doing. And so, to me, even if the 10X Creator Cup does not generate any leads for our business, if it just leads to more engineers knowing about 10X and applying to 10X and in a perfect world, if we hire one engineer from this whole campaign, well, then the $5,000 we would have paid out we're paying out for 10X Creator Cup is worth it so many times over cuz you think about what you'd pay pay a recruiting agency to get one engineer, it makes it entirely worth it. And so, yeah, like I just believe that like we lean we should lean into the bootstrapping thing, which is like have an underdog mentality, use guerrilla marketing, us all in this together to kind of create this aura around 10X.

</details>

**Claire Vale**: 作为另一个同样依靠分发作为优势的自筹资金创始人，我完全同意。我认为另一件事是，我们真的低估了作为一个员工的价值主张，那就是公司其实鼓励你拥有自己的平台。许多公司高管都非常短视，我甚至听到 CEO 们说：‘我不想让那个人说自己有多棒，因为别人会来挖走他们。’

<details>
<summary>Original English</summary>

**Claire**: I just as another bootstrap founder could another bootstrap founder that's leaning on distribution as an edge, I I completely I completely agree. I think the other thing is we really underestimate what a employee teammate value proposition it is to say like we actually encourage you to have a platform. So many companies are like short-sighted because I I actually hear CEOs saying, \"Well, I don't want that person talking about how awesome they are cuz somebody's going to come recruit them.\"

</details>

**Alex Lieberman**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yep.

</details>

**Claire Vale**: 而我的反应是：‘导致他们离开这家公司的最大原因，正是因为他们无法谈论他们正在做的所有令人惊叹的事情，也无法建立他们自己的个人品牌。’ 所以，我认为这完全是非常准确的。而且，再次，我很高兴看到另一个自筹资金的创始人这样做。正如我所说，不是在困难模式下，我的意思是，也许是困难模式，但绝对是在‘诚实模式’下。

<details>
<summary>Original English</summary>

**Claire**: And I'm like, \"That is the number one thing that's going to jump them out of this company is their inability to talk about all the amazing stuff that they're doing and build their own personal brands.\" And so, I think that is just totally totally spot on and um again, I love to see another bootstrap founder do it. As I say, not on hard I mean, maybe on hard mode, but definitely on on honest mode.

</details>

**Alex Lieberman**: 完全同意。甚至我想的一件事是，如果我看看 Anthropic 在互联网上做得非常好的一点是，他们基本上（无论是否有意为之）在**员工网红**（employee influencer）方面做得非常出色。如果你想想围绕 Claude Code 和 Co-work 的所有人，无论是 Tariq 还是 Boris 还是 Felix，对吧？他们现在就是品牌的延伸，我更信任他们的产品，因为他们在谈论它，而不仅仅是公司在宣传。

<details>
<summary>Original English</summary>

**Alex**: Totally. And and even one of the things that I think about is like if I think about what even Anthropic has done really well on the internet is they've basically been incredible, whether um planned or not at employee influencer. Like if you think about everyone surrounding Cloud Code and Co-work, whether it's Tariq or Boris or Felix, right? Like they are extensions of the brand now and I trust their product more because they're talking about it and not just the company.

</details>


### 工程师特质

**Claire Vale**: 完全正确。Alex，这太棒了。这给了我很多启发。我也有一个类似的、名叫 Max 的内容引擎，不过性质一样。好吧，我很想用快速的闪电提问环节来收尾，然后送你离开。第一，你说你与世界上最好的工程师共事，或者至少是你合作过的最好的工程师。你认为目前是什么成就了一个伟大的工程师？

<details>
<summary>Original English</summary>

**Claire**: Totally. Completely. Well, Alex, this was awesome. This has given me so much inspiration. Um I have a similar kind of content engine uh Open Claw that uh his name is Max, but you know, same same thing. Well, I would love to wrap with quick lightning round questions and then we will get you out of here. One, you've said that you work with the best engineers in the world or at least the ones that you've worked with. What do you think makes for a great engineer right now?

</details>

**Alex Lieberman**: 那些有能力在非常深层次上理解系统的人，比如让工程师一直都很优秀的那些底层特质，但他们同时具备充分的适应性（malleability），能够把自己的工作流变得“**智能体化**”（agentic）。我认为有很多非常年轻的工程师，他们完全是“AI入脑”的，但没有像首席（staff）或资深（senior）级别工程师所拥有的基础知识。然后我认为你有很多资深的工程师，他们不够适应去改变他们的工作方式。而我想到的另一件事是，**前线部署工程师**（forward-deployed engineer，简称 FDE）的概念现在比以往任何时候都更加重要，因为 AI 转型只有通过理解业务的上下文（context）才能发生。所以，这是一点。另一点是，我认为世界上最好的工程师希望自己去“做长”（go long）。我认为他们想要赌在自己的能力上，这就是为什么在 10x 我们像支付销售人员一样给我们的工程师发工资。人们觉得我们这样做很疯狂，但我的观点是，我想要自筛选出那些愿意在自己能力上押注的人。

<details>
<summary>Original English</summary>

**Alex**: Someone who has like the ability to understand systems at a really deep level, like the foundational things that have made engineers always good, but who have the malleability to fully lean into making their workflows agentic. Like I think you have a lot of really young engineers who are fully AI-pilled but don't have the foundation of knowledge that, you know, a staff or senior-level engineer has. And then I think you have a lot of veteran engineers that are not malleable enough to change the way in which they work. And and I think the other thing that comes to mind is like this idea of the forward-deployed engineer is more important than ever before because AI transformation is only going to happen by understanding a business's context. Um and so yeah, that's one piece and the other piece to it is I think the best engineers in the world want to go long themselves. I think they want to bet on their abilities and that's why like we pay our engineers like sales people at 10x. People think we're crazy for doing it, but my view is I want to self-select for people that are willing to bet on their own abilities.

</details>

**Claire Vale**: 我同意。你知道我说了多久像 PM（产品经理）和工程师应该有浮动绩效（variable comp）吗？永远。永远。我认为这是最好的。

<details>
<summary>Original English</summary>

**Claire**: I agree. I You know how long I've said like PMs and engineers on variable comp? Forever. Forever. I think it's the best.

</details>

**Alex Lieberman**: 这太不可思议了，我们仍然（当然有很多人对此有意见，而且确实存在权衡），但我们已经考虑了所有这些，这让我们的所有人都能紧跟前沿，因为他们获取杠杆的方式就是通过理解这项技术能带来什么可能性。

<details>
<summary>Original English</summary>

**Alex**: It It's incredible and we still like again, there's a ton of people who give us about it and look, there are trade-offs, but we have thought about all of them and it has kept all of our people close to the frontier because the way they get leverage is by understanding what's possible with the technology.

</details>


### 个人用例

**Claire Vale**: 好吧，我要为你的员工做宣传。我们已经在播客上邀请过另外两位 10X 的人。两位都非常棒，你应该去收听与 **CJ** 和 **JJ** 的那几期节目。现在，你雇佣名字不是两个字母的人吗？

<details>
<summary>Original English</summary>

**Claire**: Well, and I will hype up your people. We've had two other 10X folks on the podcast. Uh both both amazing and you should go go check out those episodes with CJ and JJ. Now, do you hire people that don't have two-letter

</details>

**Alex Lieberman**: 我正想说，我真的需要把名字改成 AJ。我真的搞砸了 10x 嘉宾出场的连贯性。

<details>
<summary>Original English</summary>

**Alex**: I was going to say, I really I need to change my name to AJ. I really messed up the flow of the 10X guests.

</details>

**Claire Vale**: 好吧，我嫁给了一个 EJ，所以如果你团队里需要另一个名字里有 J 的家伙，我们可以商量。好的，第二个问题是，你向我们展示了你的创作流程。我们已经看到 JJ 的协同编程，也看到 CJ 的编程。在你的个人生活里，你使用什么你认为非常独特的 AI 用例？

<details>
<summary>Original English</summary>

**Claire**: Well, I married to an EJ, so if if you need another another J guy on the team, we can do that. Okay, second question which is you know, you showed us your your creative process. We've seen, you know, co-work with JJ. We've seen coding with CJ. What are my personal use cases? Like what is an AI use case that you use in your personal life that you think is really unique?

</details>

**Alex Lieberman**: 是的，我妻子之前找了一段时间的工作。她在科技行业工作过，有一阵子一直在求职。我认为我为她构建的更有趣的用例之一（我很惊讶竟然还没有公司做这个）是，求职过程很痛苦，寻找适合你的职位也非常折磨人。但我认为我们正处于这个时代（就像人们在做 Morning Brew 时讨论的，未来会有人构建出针对每个人的“一对一时事通讯”），基本上我为她构建的是一个个性化的求职看板，她每天都会收到一封电子邮件，里面有 10 个根据她之前的职位、她的 LinkedIn 以及她所寻找的方向而筛选并打分的精选工作，然后她可以直接在邮件中点击申请，它会自动填写该职位的初始申请表。这是一个特定的用例。另一个我认为非常经典的用例，是制作一本定制的儿童绘本。我们家里有一个 11 个半月大的宝宝，对于我们甜美的 Brooke，能够拥有真正与她的家庭相关的定制故事，对我来说是一个非常酷的用例。

<details>
<summary>Original English</summary>

**Alex**: So, my my wife was um recruiting for jobs for a period of time. She's worked in tech and she's recruiting for jobs for a while and I think one of the more interesting use cases that I built for her that I'm surprised a company hasn't done yet is the recruiting process is brutal and finding roles that are right for you is brutal. But I think we're in this age like people have always talked about when we're working on Morning Brew like someone's going to build the one of one newsletter. Like the news like everyone has their own customized newsletter in this world. But basically what I built was a hiring board customized for her where every single day she got an email and the email was 10 curated jobs based on her previous job like her LinkedIn and what she's looking for and scored on that and then she could click apply from the email and it auto-fill out the initial application to the job. So, that's like one specific use case. Uh the other one in this I feel like this is like the classic one is building a custom children's book. We have an 11 and a half month old at home and you know, the idea that our our sweet Brooke can have stories that actually relate to her family to me is such a cool use case as well.

</details>


### 调试垃圾

**Claire Vale**: 太喜欢这个了。你必须加入我们的“How I AI 父母圆桌会”，因为我们有太多好用例了。好吧，最后一个问题，我问每个人：当你的 AI Oracle 创意委员会给你出纯垃圾内容时，你的提示词技巧是什么？你会生气吗？你会贿赂它吗？

<details>
<summary>Original English</summary>

**Claire**: I love it. You're going to have to join our How I AI parent round table because we have so many good use cases. All right, last one I ask everybody when your AI Oracle creative council is giving you straight slop, what is your prompting technique? Do you get mad? Do you bribe?

</details>

**Alex Lieberman**: 我想老实的回答是，这基本上取决于我有多沮丧以及我有多少时间。

<details>
<summary>Original English</summary>

**Alex**: I would say the honest answer is I will do It basically depends on how frustrated and how much time I have.

</details>

**Claire Vale**: 我喜欢你现在的慌张。你像是在想：“啊哦，我应该说实话吗？”

<details>
<summary>Original English</summary>

**Claire**: I like how flustered you are. You're like, uh-oh, should I tell the truth?

</details>

**Alex Lieberman**: 不，不，不。所以，要么我直接说去它的，然后直接动手用手写。我认为那是我的典型做法，我会觉得“这太扯了，这花的时间比它本身的价值还多”，我就用手写。或者我做另一件事，我会切实沉浸进去，花大量的时间对它说：“这太烂了。这些全都是它很烂的地方。我敢肯定这些内容已经是教训了，为什么你还没有把它注册为我已经教过你的内容教训？”所以我真的应该对它更友好一些，毕竟 AI 霸主在未来的某个时候会成为我的老板，但坦率地说，我有时对它态度挺恶劣的。

<details>
<summary>Original English</summary>

**Alex**: No, no, no. So either I will just literally say screw it and I'll just write the thing by hand. Like that that I think that's like my typical I'll just be like screw this. It's it's taking more time than it's worth. I'll write the thing by hand. Or the other thing I'll do is like I will actually lean in and spend a ton of time into this being like this is shitty. These are all the ways that these things are shitty. I'm pretty sure these were content lessons already. Why is this not registering as a content lesson I've already taught you? So I I really should be kinder to it given that the AI overlords will be my boss at some point, but honestly I am sometimes an to it.

</details>

**Claire Vale**: 所以这就像是经典的拷问：“不，为什么你是你现在的这个样子？”

<details>
<summary>Original English</summary>

**Claire**: So the the classic like no, why are you the way you are?

</details>

**笑声**: [笑声]

<details>
<summary>Original English</summary>

**laughter**: [laughter]

</details>

**Claire Vale**: 我还没问过这个问题。

<details>
<summary>Original English</summary>

**Claire**: I've not asked that yet.

</details>


### 尾声与招聘

**Claire Vale**: Alex，这真的非常有帮助。我要把这些点子都偷走，这也是我做这些访谈的秘密原因。非常感谢你向我们和我们的听众分享。我们在哪里可以找到你，我们能帮上什么忙？

<details>
<summary>Original English</summary>

**Claire**: Alex, this has been so helpful truly. Going to steal all these ideas which is the secret reason why I do do these interviews. So thank you for sharing with us with our audience. Where can we find you and how can we be helpful?

</details>

**Alex Lieberman**: 好的，我在 X 上的账号是 **Business Barista**，在 LinkedIn 上是 **Alex Lieberman**，我们的公司是 **10x**。如果你是一家大型企业，在 AI 转型方面需要帮助，请联系我们：`10x.co`。

<details>
<summary>Original English</summary>

**Alex**: Yeah, I am Business Barista on X, Alex Lieberman on LinkedIn and 10X is our company. So you're a big business you need help with AI transformation, hit us up at 10x.co.

</details>

**Claire Vale**: 如果你是一个出色的工程师，Alex 正在招聘。

<details>
<summary>Original English</summary>

**Claire**: And if you're an awesome engineer, Alex is hiring.

</details>

**Alex Lieberman**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yes.

</details>

**Claire Vale**: 招聘所有的工程师。

<details>
<summary>Original English</summary>

**Claire**: All of them.

</details>

**Alex Lieberman**: 真的是所有的工程师。

<details>
<summary>Original English</summary>

**Alex**: All literally all of them.

</details>

**Claire Vale**: 就内容机器所告诉我的情况来看，你正在招聘所有的工程师。

<details>
<summary>Original English</summary>

**Claire**: far as the content machine is telling me, you are hiring all of them.

</details>

**Alex Lieberman**: 完全正确。

<details>
<summary>Original English</summary>

**Alex**: Exactly.

</details>

**Claire Vale**: 感谢加入《How I AI》。

<details>
<summary>Original English</summary>

**Claire**: for joining How I AI.

</details>

**Alex Lieberman**: 非常感谢。

<details>
<summary>Original English</summary>

**Alex**: Thanks so much.

</details>

**Claire Vale**: 非常感谢大家收看。如果你喜欢这个节目，请在 YouTube 上点赞并订阅，或者更好的做法是，给我们留下你的评论和想法。你也可以在 Apple Podcasts、Spotify 或你最喜欢的播客应用上找到本节目。请考虑给我们评分和评论，这将帮助其他人发现本节目。你可以在 `howiaipod.com` 上看到我们所有的剧集并了解更多关于节目的信息。我们下次再见。

<details>
<summary>Original English</summary>

**Claire**: Thanks so much for watching. If you enjoyed the show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>