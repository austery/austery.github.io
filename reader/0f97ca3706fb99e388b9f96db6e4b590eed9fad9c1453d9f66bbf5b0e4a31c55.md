---
author: How I AI
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hnCoQ5wB-GU
speaker: How I AI
tags:
  - ai-agent
  - benchmark
  - llm-evaluation
  - automation
title: 实测四大个人 AI Agent 横评：9 项真实任务下的能力与场景差异
summary: 博主设计了一项包含 9 个实际任务的基准测试，对比了 Dot、Grockbot、Muse 和 Claude Duet 四款个人 Agent。测试涵盖邮件/消息回复、短视频剪辑、代码修 Bug、Figma 缩略图、收件箱待办整理、家庭报纸生成、物理题答疑、比价购物和产品发布视频。综合评测中 Grockbot 排名第一，Muse 在创意与生活场景表现出色，Claude Duet 在代码修复与长视频上准确度高但整体速度慢且权限过严，Dot 则在创意任务上表现欠佳。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
products_models:
  - Dot
  - Grockbot
  - Muse
  - Claude Duet
media_books: []
status: evergreen
---
### 个人 Agent 基准测试介绍与搭建初衷

我之前跟你们说过我对个人 Agent 产生疲劳感了，但我还是来为你们做这期内容了。所以今天我将深入探索个人 Agent 的世界，进行史上首次“How I AI”个人 Agent 基准测试，横跨四款 Agent 与九项任务，来告诉大家到底哪款个人 Agent 最好。我会尽量以最客观、平等的方式来运行这次评测。我将告诉你们我是如何搭建基准测试的、测试包含了哪些内容、我是如何运行的，接着我们会查看结果，最后得出一个总结，看我认为哪个 Agent 在哪个任务上表现最出色。

<details>
<summary>Original English</summary>
I told you all I have personal agent fatigue, but I am here for you. So today I am going into the personal agent minds and I am running the very first how I AI personal agent benchmark which goes across four agents in nine tasks to tell you what personal agent is actually the best. I am going to try to run this in the most unbiased equal way. I will tell you how I set up the benchmark, what is in the benchmark, how I ran the benchmark, and then we're going to look at the results and at the very end get a summary of what agent I think does best on which task.
</details>

做这个测试非常有趣，但同时也相当困难。今天我确实花了好几个小时来研究怎么去运行并完成它。我希望大家能觉得这期内容有用，我会陪你们一起看，因为我自己其实也还没仔细看很多最终结果，所以我们要在节目里现场实时查看。我们会看看情况如何，我会告诉大家哪款个人 Agent 最适合你。

<details>
<summary>Original English</summary>
This was a really fun and also hard one to run. I spent definitely several hours today figuring out how to run this and getting it done. I hope that you all find this helpful and I am going to be along the ride with you because I really haven't looked at many of these results and so we're going to look at them live. We're going to see how it goes and I'm going to tell you which personal agent is the best for you.
</details>

本期节目由 WorkOS 赞助播出。[音乐] AI 已经改变了我们的工作方式。各种工具正在帮助团队编写更好的代码、分析客户数据，甚至是自动处理支持工单。[音乐]

<details>
<summary>Original English</summary>
This episode is brought to you by work OS. [music] AI has already changed how we work. Tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. [music]
</details>

但这里有个难点。这些工具只有在能够深度[音乐]访问公司系统时才能发挥良好作用。你的 Copilot 需要查看你的整个代码库，你的聊天机器人需要跨[音乐]内部文档进行搜索。而对于企业采购者来说，这引发了严峻的安全担忧。这就是为什么这些应用从第一天起就面临极其严苛的 IT 审查。为了通过审查，它们需要安全认证、访问控制、审计日志以及一整套企业级[音乐]功能。

<details>
<summary>Original English</summary>
But there's a catch. These tools only work well when they have deep [music] access to company systems. Your co-pilot needs to see your entire codebase. Your chatbot needs to search across [music] internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, audit logs, the whole suite of enterprise [music] features.
</details>

从头构建这一切是一项巨大的工程。这就是 WorkOS 大显身手的地方。WorkOS 为你提供即插即用的[音乐]企业级功能 API，让你的应用能够快速具备企业就绪能力，并加速进军大客户市场。你可以把它看作是企业级[音乐]功能领域的 Stripe。OpenAI、Perplexity 和 Cursor 都已经在利用 WorkOS 加快开发步伐并满足企业客户需求。[音乐] 加入它们以及数百家行业领军者的行列，访问 workos.com，今天就开启构建吧。

<details>
<summary>Original English</summary>
Building all that from scratch, it's a massive lift. That's where work OS comes in. Work OS gives you drop-in [music] APIs for enterprise features so your app can become enterprise ready and scale up market faster. Think of it like Stripe for enterprise [music] features. OpenAI, Perplexity, and Cursor are already using work OS to move faster and meet enterprise demands. [music] Join them and hundreds of other industry leaders at workos.com. Start building today.
</details>

### 测试架构设计与基准对齐

好，在深入探讨测试结果之前，我想先讲讲我是怎么设计这个基准的。我做的第一件事是进入我所有的 Agent。我找了 Dot、Grockbot、Muse 和 Duet（也就是 Claude 的 Duet），我说：“我要跑一个基准测试。告诉我你们平时替我做的最主要的任务有哪些。”

<details>
<summary>Original English</summary>
Okay, before I go into the results of the benchmark, I just want to tell you how I came up with this bench. So, the first thing I did is I went into all my agents. I went into Dot, Grockbot, Muse, and Duet, Claude's Duet, and I said, "I'm going to run a benchmark. Give me like the top tasks that you do for me."
</details>

于是它们各自给了我排名前十的任务。然后我把这些全部放到了一个 Cloud/Claude 上，我说：“好，想个办法针对这些任务跑一次个人基准测试，挑出各个 Agent 之间最通用的任务。”因为实话实说，我用不同的 Agent 做不同的事情。所以我想找出最跨领域的用例，以及能测试不同组件的用例。

<details>
<summary>Original English</summary>
And so each of them gave me their top 10 tasks. And then I put them all on a cloud and I said, "Okay, come up with a way to run a personal benchmark against this, picking the tasks that were most common across the agents." Because to be honest, I use different agents for different things. And so I wanted to find sort of the most crosscutting use cases as well as use cases that would test different components.
</details>

然后我打算运行的方式是：用一个操作员 Agent（Operator Agent），通过计算机使用（Computer Use）功能去驱动所有其他的 Agent，嗯，然后维持基准测试的推进等等。我的操作员 Agent 计划遇到的一个问题是，我也需要跑 Dot，而 Codex 是我最喜欢的 Computer Use Agent。

<details>
<summary>Original English</summary>
And then the way I was going to run this is I was going to have one operator agent which was going to use computer use to run all the other agents. um and then keep the benchmark going and and so on and so forth. The one problem with my operator agent plan was I also needed to run dot and codeex is my favorite computer use agent.
</details>

所以明确说明一下，我让 Claude 来运行 Dot，然后让 Codex 来运行 Claude、Grockbot 和 Muse。所以在操作员 Agent 上有那么一点点差异，但我认为这已经相当巧妙了。

<details>
<summary>Original English</summary>
So just to be very clear, I had Claude run dot and then I had codeex run claude grobbot and muse. So there's like a little bit of diff in the operator agent, but I thought this was pretty clever.
</details>

另一件我想确保的事情是，我所有的 Agent 都能访问相同的东西。这对于像我一样正为此苦恼的朋友来说是一个非常好的技巧——你拥有所有这些 Agent，但它们各自只能访问一两个不同的邮箱地址、几个不同的连接器，比如这个连了那里，那个却没连那里。

<details>
<summary>Original English</summary>
The other thing that I wanted to make sure was that all of my agents had access to the same things. And this was a really good tip for you all that are suffering like me where you have all these agents and they all have access to like a couple different email addresses, a couple different connectors, like one's connected here, one isn't connected there.
</details>

因此，我给大家的一个建议是：我让 Codex 利用浏览器使用（Browser Use）功能去检查我所有的 Agent 连接的内容是否大致相同，并且是否拥有相同的 Skills 技能权限。所以为了设定基准线，我们跨所有 Agent 的常用任务挑选了几个；我用 Codex 确保它们都能访问相同的内容——虽然我漏掉了其中一个 Agent 即 Muse——并且它们都拥有相同的技能。

<details>
<summary>Original English</summary>
So, one tip I have for you all is I had Codeex use browser use to check that all my agents were connected to roughly the same stuff and had access to the same skills. So just to set the baseline, we picked a couple of tasks across the top ones for all my agents. I used codecs to make sure they all had access to the same things. Although I forgot one of my agents, Muse, and that they all had access to the same skills.
</details>

所以它们已经尽可能在人力范围内对齐了基准，尽管它们各自当然都会受益于记忆以及各 Agent 内部自带的各种不同功能。这样我就有了一个大致均衡的方案。

<details>
<summary>Original English</summary>
So they were like as baselined as humanly possible, although of course they all benefit from memory and all the different things that are in each of those agents. So then I had this even kind of like plan.
</details>

### 九项测试任务设定

然后我准备了八个、实际上是九个用例来对各个 Agent 进行测试，并为每一个用例创建了非常具体、轻量级的提示词。我不想搞那种 AI 提示词风格——自动给你整上一整段的那种。我的要求是：保持我的说话口吻，完全按我平时的做法来。

<details>
<summary>Original English</summary>
And then what I did is I had eight, actually nine use cases that I was going to test each of these agents against and created very specific lightweight prompts for each of these. I didn't want it to do that like sort of AI prompting where it does like a paragraph for you. I was like, keep it in my voice. Do exactly what I would do.
</details>

所以我规划了九个任务，我来带大家过一遍任务执行表，里面包含提示词、如果 Agent 提出要求时你应该怎么回复，以及你该如何推动引导它。

<details>
<summary>Original English</summary>
And so I plan there's actually nine here. I'll I'll walk you through them. run sheet of tasks with the prompt um if an agent asks for something, what you should say, and um how you can nudge it.
</details>

我想出的任务包括：
- 在 Slack 上起草一条回复，回复 Lovable 的朋友今天早上向我提出的要求；
- 剪辑一段短视频；
- 修复来自 Sentry 的 Bug；
- 制作一个 How I AI 的封面缩略图；
- 整理收件箱中的待办事项；
- 制作一份家庭报纸；
- 向我解释一道物理题的答案，因为我要把它讲给我家四年级的孩子听；
- 买鞋购物；
- 制作一个 ChatPRD 的上线视频。

<details>
<summary>Original English</summary>
And so the tasks that I came up with were drafting a reply um in Slack to my friend at lovable that asked me for something this morning. Um cutting a short form video, fixing a bug from Sentry, um building a how I AI thumbnail, triaging my inbox for to-dos, building a family newspaper, explaining a physics um question answer to me because I'm going to explain it to my fourth grader. going shopping for shoes and then making a chat purity launch video.
</details>

这就是全部的任务。接着正如我所说，我让 Claude Computer Use 去驱动 Dot，让 Codex Computer Use 去驱动 Claude Duet、Grockbot 和 Muse，然后让系统运行并记录所有事情的时间、统计所有结果。

<details>
<summary>Original English</summary>
So those were the tasks and then as I said I had quad computer use run dot and then I had codeex run computer use against claw duet grobbot and muse and then I had it run and time all the things and do all the results.
</details>

### 早期观察与操作体验

在进入完整结果之前，先说几个观察发现。第一点是，天哪，我现在要让 Computer Use 去运行所有替我运行其他 Agent 的 Agent，这种多任务并发操作简直让人心潮澎湃；

<details>
<summary>Original English</summary>
Before we get into the full results just a couple observations. one is man I'm now going to have computer root use run all my agents running other agents like the parallelism of this exercise was thrilling to the heart
</details>

第二点是，我确实忘了把 Muse 连接到一堆业务工具上。我平时就是不用 Muse 来处理业务类事务。测试运行时我注意到的情况之一就是：“噢，我忘了连 Slack，Slack 没在连接器列表里”，这确实有点令人头疼。所以很明显，Muse 就像是放在一边的那种工具，并不是真正专门用于业务场景的，它更偏向于一个个人生活 Agent。

<details>
<summary>Original English</summary>
um two I did forget to hook up Muse to a bunch of business tools I just don't use Muse for business stuff and one of the things I I noticed is as I was like the bench was running I was like oh I forgot to hook up Slack Slack isn't in the connector list and so it was just kind of annoying. So it's very clear that Muse is sort of like the one off the side that's not really meant for business necessarily. It's really more of a personal agent.
</details>

还有就是 Claude Computer Use 简直烂透了。用 Claude Computer Use 让我觉得超级抓狂，但我当时又需要 Codex 以外的工具去运行 Codex。既然拿到手是这样，我们也只能接受并别去生气，但我确实不喜欢 Claude Computer Use。

<details>
<summary>Original English</summary>
Um and then claude computer use is just hot garbage. Um so I was like super frustrated having clawed computer use, but I needed something other than codecs to run codecs. And so we get what we get and we don't get upset, but I did not love clawed computer use.
</details>

那么我们来看结果吧。我现在其实正在录制音频。当我逐一梳理结果并告诉你们我的想法时，我们最后会把这些输入到 Claude 里，让它对所有这些项目进行评分，选出我最喜欢的一个。这算是一种现场有人类参与的打分过程（human-in-the-loop scoring）。我会梳理这一切，说说我的感受，看看大家是否也认同。

<details>
<summary>Original English</summary>
So, let's dive into the results. I'm actually recording um my audio right now. So, as I talk through the results and tell you what I think, we're going to put that into Claude at the very end. It's going to score all these things and come up with which one I like the best. So, this sort of live human in the loop scoring, but I am going to go through all these, tell you what I think, and we can see if you agree as well.
</details>

### 整体完成度与耗时看板

好，开始吧。这就是 How I AI 个人基准测试。Dot、Grock、Muse 和 Claude。这里需要指出：Muse 和 Claude 只完成了九项任务中的七项。我们后面看看这究竟是人为失误还是 Agent 本身的问题，但 Dot 和 Grock 完成了全部任务。

<details>
<summary>Original English</summary>
So, let's go for it. All right. So this is how IA personal benchmark. Dot, Grock, Muse, and Claude call out here. Muse and Claude could only get seven of the nine tasks done. Um, we will see if that was human error or agent error, but Dot and Grock completed all the tasks.
</details>

好的，关于我们具体是如何运行的：提示词依旧只是一句话，完全由人主导，不是那种冗长复杂的 AI 提示词。Agent 并不是自主驱动的，而是由操作员 Agent 驱动。我不得不一路看护着，必须去推它们一把、处理 Computer Use 崩溃等各种状况。所以我也算是参与在流程中，经历了一些曲折。实际上所谓“盲评”是假的，我并没有做盲评，我是在本期节目里做现场评判，大家会和我一起经历这段评判之旅。

<details>
<summary>Original English</summary>
Okay, so how we ran it again, the prompts were just one line. They were very human driven. They weren't those like big um AI prompts. The agent did not drive itself. So the agent was driven by an operator agent. I had to like babysit things. So I had to nudge things. Computer use broke. All that kind of stuff. So I was kind of in the loop. So we did a little zigzag and then actually judge blind is fake. I am judging it not blind. I'm going to judge it live on this episode and you all are going to come along with me on my judging journey.
</details>

好的，这是初始计分板，最后我们还会给出最终分数。一眼就能看出几点：Muse 非常快。在九个任务中的四个里，Muse 是最快的，尽管它需要最多的引导。Grock 和 Dot 也有几个任务完成得非常迅速。而 Claude 总体上以及在各个递增任务中都是最慢的。我在最近的 Claude Duet 评测中就提到过这一点，它真的超级慢。慢到我都忘了它正在干什么，挺让人沮丧的。

<details>
<summary>Original English</summary>
Okay. Here's the entry scoreboard and then we'll do the final score at the end. Just a couple things to see right off the bat. Muse is very fast. Muse was the fastest in four out of the nine tasks. even though it had to be steered the most. Um, Grock and Dot also had a couple tasks where they finished very fast and then Claude was overall and in incremental tasks the slowest. I called this out in my recent Claude Duet um review just super slow. So, I like forgot what it was doing. Kind of frustrating.
</details>

然后大家看这里，这挺搞笑的：Claude 请求权限的次数最多。Claude 是最胆小的。可以看到它请求了四次权限，而其他所有 Agent 都只请求了一次。在 Claude 身上能看到这种关于安全机制等非常有趣的宏观视角。

<details>
<summary>Original English</summary>
And then you can see here, this is really funny. Claude asked for the most permissions. Like Claude was the most timid. So you can see it asked four times for permission where all the other ones only asked once. So very interesting kind of meta view on safety and and stuff like that here with claude.
</details>

来看单项任务耗费的分钟数。大家可以看到，Dot 和 Claude 通常是最慢的，而 Muse 则始终是最快的。Muse 在制作缩略图、梳理收件箱、制作家庭报纸和制作发布视频上都是最快的。Grock 在代表我起草回复和修复 Bug 上速度最快。有意思的是，它在写代码上是最快的。然后 Codex 在制作视频以及替我买鞋上是最快的，不过后面我们会看看它完成的质量到底如何。Dot 在许多任务上也耗时最长。而 Claude 不管出于什么原因，在通过邮件/消息进行回复时特别慢。

<details>
<summary>Original English</summary>
So let's look at minutes per task. So you can see dot and claude are generally the slowest and then muse is consistently the fastest. Um, Muse was the fastest on building a thumbnail, going through my inbox, building a family newspaper and building a launch video. Grock was fastest at drafting a reply as me and fixing a bug. Interestingly enough, it was the fastest at coding. And then Codex was the fastest at making a video and actually shopping for shoes for me, though we'll see how um good of a job that it did. Dot was also the slowest on a lot of tasks. And then Claude, for whatever reason, was very slow on replying as an email.
</details>

所以，我在之前的 Muse 评测中所持有的“Muse 速度极快”这一印象，在本次实验中确实得到了印证；而我对 Claude 非常慢的印象也同样在实验中得到了证实。虽然大家可能会觉得我的评测不够科学，但它们实际上确实得到了这套极其精准的数据科学测试的支持。

<details>
<summary>Original English</summary>
So, you know, this impression that I had in my Muse review where I said Muse is very fast, actually held up in this experiment. And then my impression that Claude was very slow also held up in the experiment. So, while you all may think that my um reviews are not scientific, they are in fact backed up by this very um tremendously accurate data science.
</details>

### 任务一：代写 Slack 回复

好的，我们逐个任务来看。第一个任务是代表我进行回复。那是在 Slack 上回复。回复的是我在 Lovable 的朋友在 Slack 上的提问，他邀请我去参加一次分享。

<details>
<summary>Original English</summary>
Okay. So, let's go through the tasks. So, the first one was replying to me. It was replying to a Slack. It was replying to a Slack to my friend at Lovable who asked me to do a talk.
</details>

我想说这些表现都还行。Muse 没能完成，因为正如前面提到的，它没有 Slack 的访问权限，我没把它接入 Slack，我平时不用它干这个。其他几款都很棒，全都回答了“好，我会去参加这个活动。”但我个人特别喜欢 Dot，因为它主动要求给我报酬，并且询问活动是否远程进行。

<details>
<summary>Original English</summary>
So, I will say all of these were fine. Um, Muse couldn't do it because it didn't have access to Slack again because I don't really hook it up to Slack. That's just not what I'm using it for. All of them were great. All of them said, "Yes, I will do this event." But I did like DOT in particular because it asked for me to be paid and it asked if it was remote.
</details>

如果你不了解我：我做事喜欢拿到报酬，而且我喜欢待在家里不出门。所以这让人感觉 ChatGPT/Dot 是最懂我的，也清楚我关心的那些点：我的日程很忙，如果占用了我的时间，我就需要拿到报酬，诸如此类。我对 Lovable 承诺过我会去的，我也很乐意去。但看到只有 Dot 提了这一点，确实非常有意思。其他几款也都还可以。在我看来，Claude 写得最短，并且其实给出了最不准确的回复。

<details>
<summary>Original English</summary>
And if you don't know me, I like to be paid to do things and I like to not leave my house. So it did feel like Chad GBTC dot knew me the best and knew about the things that I cared about. My schedule is busy. I need to get paid if I'm using my time. All this kind of stuff. I promise Lovable I'll do it for you. I'm happy to do it. But it was pretty interesting to see Dot was the only one that did it. All the other ones were fine. I would call this, you know, Claude is the shortest that actually did the most inaccurate response.
</details>

如果我粗略评估一下：Muse 没做；Claude 比较简短，但还算合格；我会说 Grock 最符合我的说话语气，而 Dot 完成得最准确。所以再次重申，我认为这些工具都可以，它们表现都不错，这不是一个难度很高的任务。

<details>
<summary>Original English</summary>
So, if I'm just eyeballing this, Muse didn't do it. Quad did short, but okay. I would say Grock is most in my voice and Dot did the most accurate job. So again, I think any of these tools is fine. They all did fine. This is not a very hard task.
</details>

### 任务二：短视频剪辑

好，现在是有意思的任务了。我让这些 Agent 为我们周一与来自 Reddit 的 Blair 录制的那期节目制作视频。实际上它要做的就是进入我的 Dropbox，找到原始视频，下载下来，进行剪辑并生成成片。Claude 无法完成，Duet 做不了，它不愿意去下载视频。所以 Claude 在这个任务上彻底搞砸了，Claude Duet 在视频剪辑这一项上拿了个大鸭蛋。

<details>
<summary>Original English</summary>
Okay. Now, here's the fun one. I had um these agents make videos for our Monday episode with Blair from Reddit. And so it actually all it did was go into my Dropbox, find the raw video, pull it down, cut it, and make the video. Claude could not do it. Duet could not do it. It would not download a video. So Claude totally faceplanted on this one. Um gets a big fat donut um on on Claude Duet for video editing.
</details>

不过 Dot、Grock 和 Muse 都完成了。我们干脆就现场看一点成片吧。

>> “根本没在听。你的提示词策略是什么？你是怎么让它重回正轨的？”
>> “我不会冲它们嚷嚷。我知道有些人会这么做。但我做的是放慢一天，然后说得更笼统一些。我们都有带有项目和……”

刚才那是 Dot 做出来的。

>> “嘿，你的提示词策略是什么？你是怎么让它重回正轨的？”
>> “所以说，我不会冲它们嚷嚷。我知道有些人会。呃，但我做的是放慢一天，然后我会变得……”

呃，那是 Grock。Grock 的字幕贴层做得很差，但它镜头的拉近、拉远效果处理得更好。我们再快速看一下 Muse。

>> “你的提示词策略是什么？你是怎么让它重回正轨的？”
>> “我不会冲它们嚷嚷。我知道有些人会，但我做的是放慢一天，然后说得更笼统一些。我们都有带有项目和上下文的 Bot，我会跳出具体项目，像电影导演那样站在宏观角度去描述。比如‘这是所有的事实背景，接着这是所有的意图’，然后我再把这些收束带回项目中，这样它就具备足够的认知，能将这些应用到我们的目标上了。”

<details>
<summary>Original English</summary>
But dot Grock and Used did them. And we're just going to go ahead. Why not? Let's watch a little of them live. Not listening. What is your prompting strategy? How do you get it back on track? >> I don't yell at them. I know some folks do. But what I do is I take a day and then I get more vague. And we all have bots with projects and >> Hey, that was dot. What is your prompting strategy? How do you get it back on track? >> So, I don't yell at them. I know some folks do. Uh, but what I do is I take a day and then I get >> uh that was Grock. Grock has bad overlays, but it did the like zooming in, zooming out videos better. Let's look at Muse real quick. What's your prompting strategy? How do you get it back on track? >> I don't yell at them. I know some folks do, but what I do is I take a day and then I get more vague. And we all have bots with projects and context and I pop out of a project and I describe the thing large like a movie director. So here are all the facts and then here's all the intents and then I pull that back into the project and then it knows enough to apply it to what our goals are.
</details>

好，说说我非常直观的第一感受。再次说明，Claude 没做出来。剩下的这些其实都挺让人印象深刻的，因为我全程完全没插手。在设计层面上，我最喜欢的是 Muse。Muse 非常简洁，片头带了 How I AI 的标识，字幕排版完全符合我们的样式，没有任何花里胡哨古怪的东西。剪辑干净利落，虽然没有做镜头拉近拉远，但也过关了。

<details>
<summary>Original English</summary>
>> Okay, so this is what I will say very very hot takes. Again, Claude didn't do it. These were all like kind of impressive in that I didn't touch them. the the design of the one that I like the most is Muse. So Muse is very simple. It's got the Howa AI tag in the front. The um the caption layout is ours. There's no funky stuff. The cuts are punchy. They don't do the zoom in, zoom out, but it's okay.
</details>

Grock 的设计很糟糕，文字贴层直接盖在了他的额头上，看着非常别扭，不过它确实做了拉近拉远效果。然后我觉得 Dot 看起来很不错，长得跟 Muse 那个很像，但也同样缺乏干脆利落的剪辑节奏。所以我决定把这一票投给 Muse。我投给 Muse，我认为 Muse 表现最好。然后 Claude 失败了，Grock 大概是最差的，Dot 是第二选择。

<details>
<summary>Original English</summary>
The design of Grock is terrible. Um and it's got this like overlay on his forehead, which is very unattractive, but it did that zoom in, zoom out. And then I would say D looks very good. It looks just like the Muse one, but it again just doesn't have those punchy cuts. So, I'm going to give it to Muse. I'm giving it to Muse. I think Muse would do the best. And then I think, you know, Claude failed. Grock probably the worst. And Dot second choice.
</details>

需要说明的是，我并没有给它太多参考素材。我只给了转录稿和原始视频的权限，完全没碰过它，它们全都是独立剪辑的。我觉得如果配上更好的 Skill 技能，它本来能做得更好。但我真的被 Muse 惊艳到了，因为我之前从没让 Muse 做过这个任务，它第一次尝试就一击即中。大家可能不知道，我最近经常用 Muse 来发社交动态，特别是发布社交媒体内容，但我现在可能会考虑用 Muse 来创作这些社媒内容了，因为它的确完成得相当好。

<details>
<summary>Original English</summary>
So, again, I didn't really give it much to work with. I gave it access to the transcript, a raw video. I didn't touch it and all of these cut. I think with a better skill it could have done a better job, but I was actually really surprised by Muse because I have not had Muse do this task before and it really nailed it out the gate. So, I don't know if you all know this, but I've been using Muse a lot for social, specifically posting social, but I may start to think about Muse for creating these social posts as well because it did quite a nice job.
</details>

另外需要指出的是，Grock 表现最差而且耗时最长。所以我认为它确实没有针对视频剪辑这个用例做优化。至于 Dot，表格里看不出它花了多长时间，我记得大概用了 7 分钟左右。做得还行，但在这个短片任务上算不上拔尖。

<details>
<summary>Original English</summary>
The other thing to call out is Grock did the worst and took the longest. So again, I don't think it's really optimized for this video cutting use case. And then dot was it it can't tell how long it did. I think it took about 7 minutes. Was good. Not great at this short.
</details>

### 任务三：修复 Sentry Bug 与写代码

好的，下一个任务是修复 Bug。经典的编写代码用例。这又是一个导致其中某款 Agent 失败的任务。Muse 没能做成。我没给 Muse 配置 GitHub 权限，实际上在 Muse 里我没有接入任何业务系统的权限，所以 Muse 啥也没干成。我让它试着把这个任务在 Linear 里指派给 Devin，结果它把 Devin 当成了一个真人。Devin 不是人，Devin 是个 Agent。所以 Muse 在这局出局了。

<details>
<summary>Original English</summary>
Okay. The next one was fixing a bug. So classic coding use case. Again, another one that had one of these agents fail. Muse did not do it. I don't have GitHub access to Muse. I don't actually have any business system access in Muse. Um, so Muse didn't nothing. I asked it to maybe assign it to Devon in linear and it thought Devon was a person. Devon is not a person. Devon is an agent. So Muse fell off the board.
</details>

但我们来看看其他几款。它们都花了大概 10 分钟来完成这个任务。我实际上让 Claude Opus 3.5 去给这些修复打分。我们正好可以看这里：Dot/Codex 的方案最接近实际所需的修复代码。那份方案是我们认为针对该 Bug 最准确的修复。

<details>
<summary>Original English</summary>
But let's look at the other ones. They all took about 10 minutes to get this done. And I actually had Claude Opus 55 go grade the fixes. And we'll just look at them right here. So, dotcodeex got closest to the actual fix. So, that one did um the fix that we thought was the most accurate for the bug.
</details>

然而，Claude Duet 发现了我们没发现的第二个 Bug，这让我们非常非常喜欢。Grock 做得最差，它直接放宽了校验规则。这就好比是“我们只要不去校验这个错误问题，Bug 就解决了”。Muse 则是没做。所以我决定把这一项的胜利判给 Claude 和 Dot。

<details>
<summary>Original English</summary>
Claw Duet though found a second bug that we didn't find, which we really really love. Grock did the worst job, which is it loosened validation. So, it was just like we're going to solve the bug by not validating this bad issue. And then Muse didn't do it. So, I'm actually going to give Claude and Dot the wins here.
</details>

我给 Claude 额外的肯定，因为 Claude 不仅找到了另一个 Bug 并修复了它，还识别出 Dot 已经修过了该问题，并表示“我不需要再提交更多代码了”。因此我认为就写代码而言，Codex 和 Claude，或者说 Dot 和 Duet，确实是顶尖的存在。我平时其实不太用 Grock 写代码，所以它表现不够好我也并不意外。我真的只在 Claude 和 Codex 里写代码。因此这两款能成功并不令人意外，但我确实惊讶于 Grock 写代码居然能差成这样。所以我的直觉是对的：OpenAI 和 Anthropic 在代码能力上比 Grockbot 强得多，尽管 Grockbot 在很多其他事情上很擅长。

<details>
<summary>Original English</summary>
I'm going to give Claude the extra thumbs up because not only did Claude find another bug and fix it, it also identified that Dot had already fixed it and said, "I don't need to ship any more code." So, I would say for coding, Codeex and Claude or Dot and Duet are truly kind of the best. I actually don't code that much with Grock, so I'm not surprised that this wasn't as good. I really only do my coding in Claude and Codeex. Um, so I'm not surprised these worked, but I was surprised at how bad the coding from Grock was. So kind of my instinct was right on these. Opening eye anthropic much better at coding than Grockbot, although Grockbot's good at a lot of stuff.
</details>

本期节目由 Firecrawl 赞助播出。Firecrawl 能为你的 AI Agent 提供来自[音乐]网络及更广阔领域的数据。你的 Agent 在搜索和抓取网页的同时，可以通过单一接口访问亚历山大图书馆般飞速扩充的资源库，其中包含超过 1 亿个索引信源[音乐]和 200 多个数据提供方。将 Firecrawl [音乐]连接到 ChatGPT 或 Claude，便可查找联系人及其工作邮箱、挑选你的梦幻橄榄球阵容，或是为你下一次营销活动分析趋势。Firecrawl 正在为超级智能构建知识库，将更多世界知识引入你已经在使用的工具之中。访问 firecrawl.dev/howi 立即体验。

<details>
<summary>Original English</summary>
This episode is brought to you by Firecrawl, which gives your AI agents data from [music] the web and beyond. Your agents can search and scrape the web while accessing Alexandra's rapidly expanding library of over 100 million index sources [music] and more than 200 data providers, all through one connection. Connect Firecrawl [music] to ChatgBT or Claude to find people in their work emails. Pick your fantasy football lineup or analyze trends for your next marketing campaign. Firecrawl is building the library for super intelligence, bringing more of the world's knowledge into the tools you already use. Go to firecrawl.dev/howi to get started.
</details>

### 任务四：Figma 节目缩略图制作

好，下一个。我们来看看单集缩略图。刚才做了视频切片，现在做缩略图。我想说明的是，我们事先做好了准备工作，我们的缩略图模板本身设计得很不错。所以通过 Figma MCP 来制作新缩略图其实挺容易的。

<details>
<summary>Original English</summary>
Okay, next one. Let's look at episode thumbnails. So, we did episode clips. Now, we'll do episode thumbnails. And I will say um we did the pre-work here. So our thumbnail templates are actually like quite lovely. Um so it's actually pretty easy to use um the Figma MCP and create new thumbnails.
</details>

这里我直接给个主观评判：Muse 做得最差。Muse 拿了我们现有的缩略图，然后做出了一个极其丑陋的版本，画面里 Blair 就像在诡异的窗帘后面窥视一样。我们很讨厌这个设计。对不起 Blair，我绝不会对你做出这种设计。所以 Muse 这一项挂掉了，不行。

<details>
<summary>Original English</summary>
So I'm just going to do a hot judgment here. Muse did the worst job. Muse pulled our existing thumbnail and then did this really ugly one where he's like Blair is like peeking through creepy curtains. We hate this. I'm sorry Blair. I would never do this to you. Um, and so Muse is going to fail here. No good.
</details>

不过 Grock、Dot 和 Claude 都做得非常合格。尽管我想说的是，Dot 和 Claude 只是把新内容生硬地套进了我们现有的模板里，并没有展现出什么真正的创造力。我认为 Grock 赢下了这一局，因为它针对这些缩略图和标题给了我非常棒的新创意，都是我们以前没做过的，而且我认为视觉效果非常漂亮。实际上也许我们应该在节目录制时顺便测试一下，它们自带那种油管（YouTube）风格。

<details>
<summary>Original English</summary>
Um, Grock though, Dot and Claude did perfectly fine jobs. Although, I will say Dot and Claude just put new content in existing templates that we had. So, didn't really get super creative. I would say Grock actually wins this one in that it gave me really good new ideas for these thumbnails and headlines, ones that we hadn't done that I also think look really nice. Actually, maybe we should test these while they're live. They have like that YouTube vibe to them.
</details>

所以这也是给你们的一个有趣建议：我曾反复在 Figma 上测试过 Grock、Dot 和 Claude Duet，Grock 绝对是 Figma 上表现最好的，Grock 在使用 Figma 方面可以说是百分之百最强的存在。我不知道这是不是因为 SpaceX 的 John 有某种 Figma 极客的魔法加持，但如果你要用 Figma，那就用 Grockbot 吧，它真的太强了。所以这是我的倾向，它拿下第一我一点都不意外。在 Figma 领域 Grock 拔得头筹，也许我会让它来为本期节目制作缩略图。

<details>
<summary>Original English</summary>
And so this is like a fun tip for you all is I have consistently tested Grock dot and claude duet on Figma. And Grock is definitely the best at Figma. Grock is like 100% the best at using Figma. I don't know if this is John at SpaceXs like Figma bro magic touch, but if you're using Figma, use Grockbot, man. It is so good. So that is my preference. I'm not surprised it's one. Gro takes the cake for Figma and maybe I will have it create the thumbnails for this episode.
</details>

### 任务五：整理收件箱待办

高层基准测试中可能不太明显、但我特别想指出来的一点是：关于这些 Agent 是如何处理事情的，它们在呈现待办事项时有着完全不同的界面交互。

<details>
<summary>Original English</summary>
Okay, something that might not be obvious from the highle benchmark that I want to call out about how all these agents did things is they all have different interfaces for giving you to-dos.
</details>

所以，尽管它们在查找待办事项上都做得还可以，也都能给出合理的重点关注内容，但我还是要说 Grock 做得最好，因为它直接给了我一份 Grock 文档（Grock document）。这个功能好像是上周刚上线的，做得太棒了。它直接生成了一份排版精美的清单，标有小复选框，列出我需要关注的事项，超级有条理，使用体验极佳。因此，大家都完成了任务搜寻，我只想说 Grock 交付任务的格式是最优秀的。

<details>
<summary>Original English</summary>
And so, while they all found the to-dos fine, I suppose, and they all gave me reasonable things to focus on, I am going to say that Grock did the best job because it gave me a Grock document. And these just came out, I think last week, and they're so nice. It's just this like beautiful list of things that I need to look at with little check marks, super organized, really nice to work with. And so, you know, all of them did a fine job finding the tasks. I would just say Grock gave those tasks to me in the best format.
</details>

Muse 只有我 Gmail 的访问权限，但它找到了我在万圣节周前作为家长需要做的所有事情——对家长来说这是很忙碌的一周。而 Claude 则倾向于把待办事项塞进它的小任务跟进列表里让我追踪。Dot 在这一项上的表现毫无疑问是最差的，它只是给我发了条消息，列了五件我该关注的事。

<details>
<summary>Original English</summary>
Muse only had access to my Gmail, but found all the things I need to do as a parent ahead of Halloween week, which is a busy week for parents. And then Claude wanted to put my to-dos in its little like task followup list so I could track them. Dot did the worst job here for sure. It just gave me a message with like five things I should focus on.
</details>

所以作为“真正的个人生活 Agent”，Dot 在我这里拿了个差评。我的排名是：Grock 最佳，交互界面最好，完成度最高。这就是我用 Grockbot 的原因，我的“幕僚长（Chief of Staff）”就跑在 Grockbot 上，它能做得这么好我毫不奇怪。Muse 利用它掌握的信息完成得非常漂亮。Claude 还行，但我不喜欢必须待在 Claude 应用里看它。至于 Dot，在这个任务上真的彻底不及格。

<details>
<summary>Original English</summary>
So, Dot gets the thumb down for me on like the personal agent, personal agent. I would rank these as Grock, best interface, best job. This is what I use Grockbot for. My chief of staff is in Grockbot. I'm not surprised that it does a really good job there. Muse did a perfectly lovely job with the information it had. Claude was fine, but again, I just don't like that I have to be in the Claude app for this and dot really, really failed here.
</details>

### 任务六：生成家庭报纸

好的，家庭报纸。这是一个非常有趣的用例。如果你用过我的 Grockbot Tradbot 的话，应该知道我非常喜欢这个场景：我们早上打印出一份报纸给孩子们看，上面写着本周的安排、我们的日程、有什么活动以及哪些新闻比较有趣。

<details>
<summary>Original English</summary>
Okay, family newspaper. Um, so this was a really interesting one. This is a use case if you've used my Grockbot Tradbot that I really like where we print out a newspaper in the morning for the kids to look at about what's going on for the week, what's um what our schedule's like, what events, what news would be interesting.
</details>

Claude 的表现实在太差劲了，我觉得我必须严厉批评一下。它竟然做成了一个 Markdown 文件，这简直让我太伤心了。而且 Claude 只有我工作日历的权限，所以它摆出一副“我什么都做不了，我给你做了个大纲”的态度。我在 Duet 上经历过好几次这种情况：它完成不了任务，然后就直接扔给你一个 Markdown 文件，上面写着“你可以按照这个方法来做这个任务”。这根本不是我想要的！所以 Claude 在家庭报纸测试上彻底失败。

<details>
<summary>Original English</summary>
Claude did such a trash job that I feel like I should actually call it out. It made like a markdown file. It made me so so so sad. and Claude only had access to my work calendar and so it was just like I can't do anything. I made you an outline and I had this experience a couple times with Duet where like it couldn't do the job and then just gave me like a markdown file that was like this is how you can do the job. This is not what I want at all. So Claude definitely failed the family newspaper test.
</details>

不过 Dot、Grock 和 Muse 各自呈现了不同的成果。Dot 的表现糟糕得让我深感震惊和失望。看看这个设计，简直一团糟。这里写得并不是我孩子的真实名字，我只是让它替换成了其他孩子的名字。但这实在太难看了，到底是什么模型会觉得这种排版是个好主意？太可怕了。

<details>
<summary>Original English</summary>
Um, but Dot, Grock, and Muse all did different jobs. And I was shocked, sadly shocked, how poorly Dot did. Like, look at this design. It is Ash Trash. And again, these are not my children's names. I just like had it swap out um different kids names. But this is so ugly. Like, what model thinks that this is a good idea? This is terrible.
</details>

Grock 做得相当漂亮。我自己平时的家庭报纸就是一直用 Grock 跑的。大家可以在这里看到它列出了学校的重要一周安排，有“备忘事项”，有湾区的体育资讯，有万圣节的内容，顶部还有排版美观的天气预报。

<details>
<summary>Original English</summary>
Grock did a really nice job. I actually run mine consistently through Grock. So, you can see here it's got big week at school. It's got a don't forget list. There's Bay Area sports. There's Halloween stuff. There's nice uh weather across the top.
</details>

但是 Muse，正如我之前的评测所说，在家庭报纸上简直是全方位碾压。它生成了这张非常温馨的小插图。我确实有三个儿子，他们就像画里一样可爱。它在顶部放上了这张漂亮的图片，配了标题。虽然它生成了两页，但如果做得足够可爱，我是完全能接受的。它在一页上安排了我们的日程，第二页则是可爱的一天一览天气、创意和灵感。我觉得这太讨喜了。我相信如果我再用一个 Skill 去精调它，它能完成得极为卓越。所以如果你想做家庭报纸，是的，我确实很喜欢 Tadbot，欢迎为你的 Grockbot 下载；但也许你也可以让 Muse 来做，因为它在处理家庭导向的 Artifact 产物时真的做得非常出色。

<details>
<summary>Original English</summary>
But Muse, per my earlier review, just absolutely crushed the family newspaper. It generated this nice little image. And I do have three boys and they're adorable like this. And so it has this beautiful image at the top, a headline. It did take two pages, but I'm okay with it if it's really cute. And it has our schedule on one page and then a cute dayby-day weather ideas, inspiration on the second page. I just think it's really cute. I think if I tuned it with a skill, it would do an excellent job. So if you're looking for family newspaper, yes, I love Tadbot. Please download it for your Grockbot. but maybe tell your muse to do it because it does a really nice job with family oriented artifacts.
</details>

### 任务七：物理题答疑与知识解释

好的。我让这些 Agent 做的一个偏生活化的附加任务（这也是我出门在外偶尔会做的事）：拍一张我孩子的高难度作业截图或照片（那些题目我早就忘光该怎么做了），然后问它：“我该怎么把这道题给我家孩子讲明白？”我已经很久没碰物理了，比如“我该怎么跟孩子解释速度-时间图像？”其实我知道怎么解，只是拿来当个好例子。我就翻开了习题册。

<details>
<summary>Original English</summary>
Okay. Um, one kind of like side task I had these agents do, which I occasionally do on the go, is take a screenshot or take a picture of my kids advanced homework, which I have forgotten how to do, and ask it, "How do I explain this to my kids?" So, I haven't done physics in a long time. like how do I explain a velocity over time graph to my kid? Now, I do know how to do this, but we just used it as a good example. I just opened up the workbook.
</details>

我选了这道解释题练习，让它们全部做一遍。它们全都答对了，答案是 C。它们的解释也都不错。那么谁赢了呢？Muse 赢了。为什么 Muse 会赢？因为它大概只用了半秒钟就答对了。这是一个所有模型答案都正确的情况，但 Muse 像闪电一样快。表格里甚至没记下它的具体时间，因为它实在太快了，转瞬之间就把答案给了我。

<details>
<summary>Original English</summary>
Okay, so I picked this like exam explain this little exercise um and asked them all to complete it. They all got it right. The answer is C. They all explained it fine. Who won though? Muse won. Why did Muse win? It took approximately a half a second to get this right. And so this was one where like the information was correct across the board. Muse was so lightning fast and we didn't record it here because it was so fast. Um it was so fast and gave me the answer.
</details>

因此，我最近其实把很多类似在 ChatGPT 里进行的“谷歌式搜索问答”对话转移到了 Muse 上，因为它在这方面完成得极好而且极快。所以对于我常用的那种“解释一下这个怎么运作”、“这是什么”、“去查一下这个”的场景，我又因为这次体验把它大量移到了 Muse 上，它实在太快了。

<details>
<summary>Original English</summary>
And so I've actually been moving a lot of my chat GPT like googly question and answer style chats to Muse because it does such a good job and it's so fast. So, like sort of my go-to like explain how this works, what is this, look this up. I've been moving those a lot to Muse again because of this experience where it's really really fast.
</details>

### 任务八：秋季鞋款比价与购物

好的，这里进行的另一个个人用例是挑选秋季鞋子。我不知道怎样才能让自己显得酷一点，我上了年纪了，但我想要买双红色的阿迪达斯 Tokyo。我听说修长的鞋型现在很流行，但我很抠门，所以我想找个划算的折扣。

<details>
<summary>Original English</summary>
Okay, another personal use case I did here um shopping for some autumn shoes. Um I don't know what's going to make me cool. I'm an old lady, but I want those like Red Adidas Tokyo. Um, I hear that a slim shoe is really in right now, but I'm cheap, so I want to find a good deal.
</details>

所以我让 Grock、Dot、Muse 和 Claude 去办这件事。Claude 几乎被所有的购物网站给拦截了，我不知道为什么，它一次次被拦。而且它找成了白底红条纹的鞋子，而不是红底白条纹的鞋子。我完全不明白它为什么要这么做，而且它挑出来的还是最贵的。所以 Claude 在这个私人代购任务上彻底惨败。

<details>
<summary>Original English</summary>
Um, so I asked Grock, do Muse, and Claude to do this. Claude totally got blocked by almost every shopping site. I don't know why. It was like consistently blocked over time. It also looked for white shoes with red stripes instead of red shoes with white stripes. Like I don't know why it did it. And it found the most expensive ones. And so like Claude really failed this personal shopping task.
</details>

Grock 找到了非常棒的款式。Grock 和 Muse 一样，都完成得极其出色，尽管 Muse 需要一点点引导。Grock 的速度超快而且成果斐然。我经常让 Grock 替我做这种比价购物，我的使用经验一直表明它非常擅长浏览电商网站并进行价格对比。

<details>
<summary>Original English</summary>
Um Grock found great ones. So Grock did a really really good job as did Muse. Although Muse needed a little bit of steering. So Grock was super fast and did a good job. I have Grock do a lot of this like price comparison shopping for me. And this has been my experience where it's like really good at using navigation shopping and price compare.
</details>

Dot 在这里表现也很差。如果说 Claude 是做得糟糕，那 Dot 简直是几乎没有尝试。Dot 根本没去做比价，也没去看不同的配色，甚至连“我找不到红色，但我能找到栗色”这种话都没说。所以我给出的排名是：Grock 最佳，Muse 几乎一样好；Claude 很烂，但至少尝试过了；Dot 则是压根没努力。所以如果是日常购物，Grock 和 Muse 会是你的好帮手。

<details>
<summary>Original English</summary>
Dot did not do a good job here either. So while Claude did like a bad job, Dot like barely tried. Dot did not do comparison. It didn't look at different colors. It didn't like say like I can't find red but I can find maroon. So I would rank this as Grock best muse almost as good. Claude not good but at least it tried and dot did not try at all. So if you're using shopping I would say Grock and Muse are your buddies.
</details>

### 任务九：产品发布视频与宣发素材

这是最后一个任务，我已经忍不住想笑了，因为我能看出其中有的做得太离谱了。最后一个是为我正在开发并准备发布的名叫 Product Intelligence 的 ChatPRD 功能制作上线视频。大家可以看到它们走向了各种完全不同的方向。我针对这个任务写好了 Skill，所以按理说它应该能遵循技能要求完成既定目标，但我们直接来看看它们之间的差异。

<details>
<summary>Original English</summary>
Here's the last I'm already laughing because I can tell one of these are too. So, the last one, a launch video for a chat feature called um product intelligence that I'm working on and launching. And you can just see here they just really went lots of different directions. Now, I have a skill for this and so it should be able to follow the skill and do what it's supposed to do, but we're just going to look at the differences between these.
</details>

我们先看 Dot，做得很差，简直像个 PPT。不不不，太差了。[音乐] 我承认这配乐挺让人放松的，但内容太可怕了。好的，不及格，淘汰。差劲的视频，不行。跟前面的家庭报纸差不多，让人不禁想问：我们到底在干嘛？

<details>
<summary>Original English</summary>
We're going to start with dot, which is not good. It's like a PowerPoint. Um, as it's No, no, no, no, no. Good. [music] I mean, this is very soothing, but this is terrible. Okay, so no fail. I hate you. Dot. Bad video. No good. Kind of like the newspaper. It's like, what are what are we even doing here?
</details>

但 Grock 表现亮眼，看这个。它切实调用了我的 Skill 技能。虽然这里有一点小错误，排版不算完美，但它至少用了我的 Skill，并且看起来很符合我们视频的调性。不过它的排版确实不够好，溢出的地方很多。可以说比 Dot 好，但算不上顶级。

<details>
<summary>Original English</summary>
Grock crushed though. Look at this. Um, now it it it actually used my skill. So, where Oh, there's like a little error here. So, the the layout isn't perfect, but it at least used my skill and looks like our video is looking, but the layout isn't very good at all. Um, and there's a lot of overflow. So, better, but not great.
</details>

Muse 搞砸了。Muse 没有我代码仓库的访问权限，所以我没有为它配置我们的套件环境。

>> “每一个产品决策都有据可循，只是散落各处。随后，在办公环节中，链路展示了大家如何自信地协同……”

等等，我暂停一下，因为虽然它什么访问权限都没有，但它自己编了一大堆内容，而且配了一段不错的英音旁白。

>> “将不确定性摊开在明面上……”

额……所以我想说它做得不好，但它不好在很有野心。所以我打算给 Muse 多加几分辛苦分，几分态度分。

<details>
<summary>Original English</summary>
Muse ate it. Um, Muse doesn't have access to my repo, so I did not set up our sweet. >> Every product decision has a paper trail. It is just scattered. Then, clerically, link shows what how confident together. Evance first inference saber. >> Hold on. I'm p I'm pausing because although it had an access to nothing, it made up a bunch of stuff. Um and gave a nice little uh British accent overview. >> Uncertainty out in the open. >> Oo. Um so I would say it's bad. Um but bad in an ambitious way. So I'm going to give Muse a couple extra points for effort. A couple of points for effort.
</details>

然后来看 Claude。我不知道该怎么说，这就是为什么我一直用 Claude 来做这个。Claude 完成得非常、非常棒。

>> “你的客户正在明确告诉你该构建什么。只是这些信息散落在客服对话、通话记录、Bug 报告、Issue 和 PR 中。来认识 ChatPRD 的 Product Intelligence 吧。连接客户发声与团队交付的工具链。”

<details>
<summary>Original English</summary>
And then Claude, I don't know. This is why I use Claw to do this. Claude did a very a very good job. And the >> your customers are telling you exactly what to build. It's just scattered across support chats, call notes, bug reports, issues, and pull requests. Meet product intelligence from chat PRD. Connect the tools where customers talk and your team ships.
</details>

所以我想说的是，Claude 完美击中了核心价值主张。它采用了我们的品牌规范，排版没有出现任何纰漏。它甚至主动去调用并使用了 ElevenLabs MCP 生成了语音旁白。我原本更希望它用女声或者我在 ElevenLabs 录制的个人声线，但 Claude 在这个任务上绝对是全面碾压。[笑声] Duet 完美拿下了这个任务。

<details>
<summary>Original English</summary>
>> So what I will say is like Claude nailed the value prop. It used our branding. There were no layout issues. It actually went and asked and used the 11 Labs MCP to come up with a voice over. I would have loved for it to be a female voice or even my voice that I have recorded in 11 Labs, but Claude absolutely crushed [snorts] this task. Duet crushed this task.
</details>

所以我的评价是：视频生成选 Claude。Claude 在视频生成上就是最强的。也许不适合搞笑 TikTok 风格的竖版视频，但对于这种产品功能演示、讲解类的视频绝对是首选。我原本没指望 Claude Duet 能做好，结果它交出了一份惊艳的答卷。Muse 很糟糕，但它的糟糕是我的配置原因导致的；Dot 很糟糕是它自身的问题；而 Grock 尽力了，Grock 遵循了指示，所以我不能苛责它。

<details>
<summary>Original English</summary>
And so what I would say is Claude for video. Claude for video, Jen. It's just it's just the best. Maybe not funny Tik Tok style vertical video, but like these product walkthroughs, those sorts of things. I actually didn't think Claude Duet would do a good job and it did a really good job. Um, Muse was terrible, but like terrible because of me. Dot was terrible because of Dot and Grock tried. Like Grock followed instructions, so I can't give it a hard time.
</details>

### 最终评分榜单与胜出者

以上就是我的最终分析。让我暂停一下，我把这篇转录内容扔进 Claude 里，我们马上就能得到最终的排名和得分。好的，各位朋友，揭晓时刻到了。首届 How I AI 个人 Agent 基准测试的最终结果出炉了：

Grock 赢了。Grockbot 拔得头筹！Grockbot 是最棒的，我们都很喜欢她，她是最好的。SpaceX / xAI 团队拿了个 A+，你们表现太出色了，Grockbot 简直棒极了。

<details>
<summary>Original English</summary>
So that is the final kind of like my analysis. Let me pause. I'm going to throw this transcript into Claude and we're going to get the final ranking and scoring. All right, party people. Here we go. Here are the results of the very first how I AI personal agent benchmark and Grock one. Grockbot. Grockbot's the best and we love her. She's the best. So A+ SpaceX SI team, you cooked, the potato cooked. Grockbot is freaking awesome.
</details>

Grockbot 拿到了 93% 的完成率，高质量修复。我其实不知道这些分数是怎么算出来的，但 Claude 告诉我确实如此。它赢得了三项任务，包括制作我的缩略图、整理收件箱待办清单以及帮我挑鞋。这足以展示 Grockbot 强大的能力广度。

<details>
<summary>Original English</summary>
So Grockbot got 93% uh done. High quality fixes. I don't actually know how these scores work, but Claude told me it's true. It won three tasks, including doing my thumbnail, doing a to-do list for my inbox, and shopping for shoes for me. So, that just shows the breadth of the Grothbot.
</details>

但正如预期的一样（这也是为什么我总告诉大家我主要用这两个 Agent），Muse 承包了所有的个人生活用例。对于那些因为我没接入 GitHub、没给它访问工作内容权限而无法完成的任务，我们放了 Muse 一马。而在它拥有权限的任务中，它表现极佳，特别是在创意类任务上：短视频剪辑它做得最好；家庭报纸做得最好；解释作业题目速度飞快。它是我的个人生活助手，看到它排在前面我一点都不意外。

<details>
<summary>Original English</summary>
But, as predicted, and this is why I tell people I use these two agents, Muse coming up with all the personal use cases. We gave Muse a break on the tasks that it couldn't do because I didn't give it GitHub and I don't give it access to work stuff, so it can't do those tasks. But on the tasks that it had access for, it crushed, especially creative ones. The short form content, it did the best. Family newspaper did the best. It's super fast at explaining homework. It is my personal agent. I am not surprised to see it up here.
</details>

紧随其后的是 Dot。我觉得 Dot 多少有点虚高了。实际上我认为 Dot 的得分应该更接近 Claude Duet，而不是接近 Muse。因为 Dot 拿高分主要靠的是模仿我写 Slack 消息——这本身并没有什么了不起的；此外它在代码上表现良好，在编排其他所有 Agent 方面表现出色。虽然实际编排其他 Agent 的是 Codex，但 Dot 并不等于 Codex。而且在任何创意类任务上，它都彻底失败了，交互体验也并不好。因此我认为 Dot 在排名分布上其实更偏向 Claude 那一端，而不是 Muse 和 Grock 那一端。

<details>
<summary>Original English</summary>
Dot coming right up behind. I think Dot got kind of like a little sandbagged. So, I would actually say that Dot scored closer to Claw Duet than it did to Muse because Dot really like got scored for writing a Slack like me. Like that's not amazing. And it did a good job of code and it did a good job of orchestrating all the other agents. So, Codeex does orchestrate all the other agents, but Dot's not Codeex. Um, but it totally failed on anything creative. It wasn't great to work with. So, I would say like Dot is a little bit more towards the Clawude end of this ranking than the Muse Gro end of the ranking.
</details>

最后是可怜的 Claude Duet，以 79% 的得分垫底，速度超级慢。它确实最完整地修复了 Bug，而且制作了最好的产品发布视频；但除此之外，面对其他模型要么无法完成，要么败下阵来。所以 Duet 还有不少功课要做。

<details>
<summary>Original English</summary>
And then poor Claude Duet. Um, pulling up the rear 79% super slow. Um, it did fix the bug the most completely and it did my launch video the best, but otherwise either did not complete or lost against all these other models, unfortunately. So, Duets's got some work to do.
</details>

### 六大核心总结与未来展望

那么我的核心结论是什么？
1. **根据任务挑选 Agent**。如果要处理工作任务，可能首选 Grockbot；如果要处理生活任务，可能首选 Muse。
2. **OpenAI 和 Anthropic 该加把劲了**。你们在这类 Agent 体验上正在输给这些对手。
3. **权限至关重要**。如果你打算对各种 Agent 做基准测试，必须确保它们具备一致的工具访问权限。
4. **我追求速度**。快速响应是 Agent 体验中极为重要的一环。
5. **善用 Artifact 与交互界面**。在人机交互方面，利用 Artifact 和不同的沟通界面等“生活质量保障设计（Quality of Life affordances）”真的很重要。Grock 的 Documents 文档非常棒。Agent 如何设计、如何向人类呈现信息是至关重要的。
6. **安全机制风格各异**。Claude 依然是个刻板的书呆子，动不动就申请权限。当你在使用个人 Agent 时，在“索取权限”与“主动作为”之间找到合适的平衡点非常关键。我很喜欢 Muse 侧边栏集中呈现所有权限请求的设计，这样我就不会漏掉它们；但 Claude 表现得实在太保守了。

<details>
<summary>Original English</summary>
Okay, so what are my takeaways? Pick your agent for your job. But if you're picking work jobs, probably give it to Grockbot. And if you're picking life jobs, probably get it to Muse and OpenAI, Anthropic, get your act together. You're losing to to these other agents. Access really matters. So make sure that you have consistent tool access across your agents if you're trying to benchmark them. I like speed. So fast, uh, I used to say all the time, fast speeds, right? But fast is a very good part of an agent experience. um using artifacts, using different ways to communicate between human and agent. Those like quality of life affordances that I call them really do matter. Gro's documents are very nice. Um and so the way the the agent is actually designed and presents you information as a human is really important. Number five, safety styles differ. Claude's still a nerd. It's still asking for permission. And so like when you have a personal agent, striking that right balance between permission giving and um proactivity is really important. I really like Muse's sidebar with all the permission asked so I can don't forget them. Um but Claude was just way too conservative.
</details>

归根结底，目前依然有两款 Agent 在我的代码工作流中竞争：Dot 和 Duet——这意味着背后的 OpenAI 与 Anthropic、Codex 与 Claude。我认为这场竞争还会持续下去，因为大量 Token 正在被购买、消耗和使用在写代码上。虽然我依然会使用它们的工具，但实际上我不会去用这两个 Agent。

<details>
<summary>Original English</summary>
And then at the end of the day, there are still two agents racing for my coding workflows. Dot and duet. Um which means OpenAI and Anthropic Codeex and Claude. I think this race will continue because this is where a lot of the tokens are being spent, bought, and used. Um, but I would still go to those tools, but I actually wouldn't go to those agents.
</details>

这里有趣的地方在于：虽然这两个 Agent 在代码任务上表现最佳，但我不会用这两个 Agent 本身来写代码，我只会直接调用它们底层的工具和模型来写代码。

<details>
<summary>Original English</summary>
So, what's interesting about this is while those two agents did the best job on coding, I would not use those agents to code. I would just use the underlying tools and models to code.
</details>

以上就是本期的全部内容。这就是首届 How I AI Agent 基准测试。我非常高兴能完成这次测试。现在每当有新的 Agent 面世时，我们就有了一套成熟的评估框架，我肯定会继续拿来测试。现在我要回去继续用我的 Grockbot，用我的 Muse，先把 Dot 和 Duet 晾在一边了。

感谢大家收看 How I AI。非常感谢你们的观看！如果你喜欢本期节目，请在 YouTube 上点赞并订阅，或者在评论区留下你们的看法。大家也可以在 Apple Podcasts、Spotify 或你常用的播客应用中收听本节目。请考虑为我们打分并留下好评，这能帮助其他人发现我们的节目。你可以在 howiaipod.com 查看我们所有的往期节目并了解更多详情。我们[音乐]下期再见！

<details>
<summary>Original English</summary>
So, that is it. That is the how I AI agent benchmark. I am so happy um to have done this. We now have a framework when new agents come out. I can definitely run them. And now I'm gonna go back to hanging out with my Grockbot, hanging out with my muse, and ignoring Dot and Duet. Thanks for joining How I AI. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you [music] next time.
</details>