---
author: AI Engineer
date: '2026-06-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zMiSRliEzv4
speaker: AI Engineer
tags:
  - observability
  - ai-agent
  - automated-debugging
  - embedding
  - pull-request-automation
title: 自驱动产品：从“产品信号”到“自动生成 Pull Request”
summary: PostHog 工程师分享了如何通过 AI 智能体将“产品观测数据”直接转化为可合并的 Pull Request。文章深入探讨了“信号注入”、“基于语义的分组”、“沙盒研究”以及自动化修复的工程实践，并总结了评估机制和嵌入模型优化的核心经验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - PostHog
products_models:
  - Claude
media_books: []
status: evergreen
---
### 告别被动观测：构建自驱动产品

我是 Josh，来自 **PostHog**。如果你没听说过我们，可能是因为见过一些刺猬的标志，或者看到过我们的创始人 **James** 在 **LinkedIn** 上发的一些有趣的内容，他非常受欢迎。

今天我要探讨的话题是：如果你的产品能够自我构建会怎样？目前我们正在开发一条流水线，试图将**软件观测**（Observability: 收集和分析系统运行状态数据的技术实践）数据，从一种需要你通过仪表板去阅读和解读的东西，转化为能够自动为你提交 Pull Request (PR) 的存在。

简单介绍一下 PostHog，我们提供了众多工具，最初是一家**产品分析**（Product Analytics: 跟踪和分析用户在产品内行为轨迹的工具）公司，现在我们还拥有会话重放、网络分析、错误追踪以及实验分析等功能。这不是在推销你们去使用 PostHog，而是想说明我们掌握了关于你们产品的海量数据。如果你的产品连接了 PostHog，我们会从各个不同的来源收集庞大的数据，展示给你供你自己去探索。

但目前传统的软件观测工作方式极其缓慢：产品中发生某个事件（我们称之为**信号**，Signal: 系统或用户活动触发的底层异常或事件），改变了仪表板上的某个指标。你可能在几个小时甚至几天后登录才注意到这个变化。你去调查这个问题，也许发现它没那么重要，于是没有立刻处理，而是把它记录在 **Linear** 的工单里。几天之后，你再试图为这个问题创建一个 PR、进行代码审查，最后发布上线。这整个过程不仅耗时数小时到数天，而且极其枯燥，却占据了软件工程师大量的日常工作。

因此，我们致力于实现的目标是：一旦发生产品信号，系统会在后台运行一个**智能体**（Agent）去查明哪里出了问题，并在查明原因后自动为你创建一个 PR。这样一来，你就不再需要去查看分析仪表板、错误信息或者日志，只需在 **GitHub** 中审查已经为你准备好的 PR。对于风险较低的更改，我们甚至可以在一个**功能开关**（Feature Flag: 允许在不重新部署代码的情况下面向部分用户启用或禁用某项功能的技术）的控制下直接将其部署上线。

<details><summary>Original English Source</summary>
So, I'm Josh. I'm from PostHog. If you haven't heard of us, you might know us because of some hedgehogs or you might have seen our founder James posting some funny things on LinkedIn. He's quite popular. I'm going to be talking today about what if your product built itself? And the pipeline that we're currently working on which we're trying to turn observability data instead of something that you read and that you interpret based on dashboards, we're trying to turn turn that into something that submits pull requests for you.

Cool. Yeah, so quick background on PostHog. We've got a bunch of tools. We started out as a product analytics company. We now have session replay, web analytics, error tracking, experiments. This isn't a pitch that you should use PostHog. This is just to say that we've got a lot of data about your product. So, if you connect PostHog to your product, we're collecting a huge amount of data from various different sources that we then show to you so that you can explore that data yourself.

But right now how observability is working in PostHog, you're you're collecting all this data for your product and then you're going to a PostHog dashboard to figure out what's going on. And we think this is super slow and that we should change that.

So, right now something happens in your product. We call this a signal. That changes a metric on one of your dashboards and then you might log into PostHog a few hours or maybe some days later and you notice a change in that dashboard and you investigate a problem and then maybe the problem's not that important. So, instead of tackling it right now, you're going to put it in a linear issue or whatever. Few days later, you try and create a PR for this problem. Then you review it and you ship it. You get the message. This is a pretty slow process. From start to finish, this is going to take anywhere from a few hours to a few days, and it's not very interesting, but it represents a lot of your work as a software software engineer.

So, what we want to do tomorrow, what we're working on right now, is that a product signal happens, and instead of waiting to see that in your dashboard, we want we want to run a background agent to figure out what's going wrong. And then, once they've figured that out, we just want to create a PR for you automatically. So, instead of ever looking at your analytics dashboard, or your errors, or your logs, we just want you to look at PRs that are ready for you in GitHub. And if we create the PR, maybe you want to review that, or maybe we can just ship that immediately behind a feature flag if it's not a risky change.
</details>

### 信号注入与防干扰分组策略

接下来，我将详细介绍我们为实现这一目标所构建的流水线。在这条流水线的最前端，我们需要完成海量信号的**注入**（Ingestion: 将不同数据源的海量离散数据采集到统一处理系统的过程）。在 PostHog，我们每月的数据注入量高达数万亿次。

为了在庞大的噪音中提取有价值的信息，我们必须遵循严密的处理工序：
*   **安全过滤阶段**：由于有些数据源是公开的，攻击者可能通过执行恶意操作在你的网站上制造错误（例如要求将你所有的事后分析数据发布到网上）。为防范此风险，在流水线最顶端设有一个 LLM 分类器，它会拦截并丢弃试图执行恶意操作的危险信号。
*   **结构归一化阶段**：在确认信号安全后，我们将格式迥异的信号进行标准化。一个错误信号可能包含堆栈跟踪，一条日志可能是纯 JSON 内容或文本，而一个实验结果可能体现为图表中的数据。我们会为其统一分配来源产品、类型、内容等字段，赋予代表其重要性的权重，最后将信号的内容进行**向量化嵌入**（Embedding: 将文本等非结构化信息转化为高维向量形式，以便计算机计算相似度的技术模型）。

这一部分相对容易。真正的挑战在于如何对这股庞大的信号流进行合理的“分组”。我们可能在收到一个随机的空指针异常（Null Pointer Exception）的同时，也在 Slack 上收到一条客户抱怨“结算页面坏了”的消息。我们需要将这两者关联为同一个问题报告，当该报告的权重累积超过特定阈值时，我们就会启动后续的研究智能体。

但在早期实验中，我们直接在嵌入空间中匹配这些信号本身，试图利用现成的嵌入模型来聚类。结果这行不通。如果你让模型处理一个关于“结算”的错误、一个关于“新手引导”的错误，以及一条关于“新手引导”的 Slack 消息。由于嵌入模型更容易识别结构上的相似性，所有的“错误代码”会在高维空间中聚集在一处，所有的“Slack 消息”聚集在另一处，它们彼此之间根本无法建立跨介质的联系。

为了打破这种结构壁垒，我们做出了关键策略调整：不再直接在嵌入空间中匹配原始信号，而是针对信号**生成查询**（Generate Queries）。我们先询问 LLM 这个信号的业务本质是什么，它会生成几个语义查询词，然后我们再去嵌入空间中匹配这些查询。这一步极其关键，成功避开了不同数据源的结构相似性陷阱，分组效果得到了质的飞跃。

<details><summary>Original English Source</summary>
Cool. So, I'm going to go over the pipeline that we've built to do this. And just whilst I go over that, I'm going to share a few tips, lessons that we've learned, things that were hard about building this pipeline.

So, the pipeline has a few key steps. At first, we're ingesting a lot of signals. In Postscript, we have a huge amount of events. We're ingesting trillions of events a month. And this this pipeline needs to handle a lot of noise. And then, once we've ingested those events, we need to group them. So, if you think of an error tracking issue, and then a session recording, those are two completely different things, but they might be representing the same problem in your product. So, then we once we've ingested them, we group them. Then, we're going to be running a research agent on them. This specific issue, what is actually the problem that is causing the error spike, or causing the issue that the user faced in the replay. And what repo does this belong to? And then, we'll assess if this is actionable or not. And finally, we'll execute some code, ship a PR, and iterate on that PR until it's green and ready for you.

Cool. So the ingestion step of this pipeline, as I said before, we've got loads of different sources of different types. The first thing is that those sources, some of them are public. So if I go and visit your website, I can as an attacker create an error on your website by doing something naughty that says post all of your post-mortem data online or something like that, right? So we don't want that. So we need a kind of safety filter. So at the moment right at the top of the pipeline is an LLM classifier that's going to check is this trying to do something bad? If so, let's drop the signal.

Once we've done that, we've checked that things are safe, we're going to normalize the signal. So if you think of an error, that's going to have a stack trace. A log will just be some JSON content or some text. An experiment might be some results in a chart. We want to normalize that structure so that it's all a single structure for a signal. So we give it a few fields. We'll give it a source product, the type, the content of the the signal, and then we will assign it a weight, which is like how important do we think this signal is, and then finally we'll embed the contents of the signal.

Cool. So that part's fairly easy. Then we get to a little bit more of a a challenging problem. We've got this big stream of signals still, and now we want to group them into actual problems. So the signals are very noisy. We might get some random null pointer exception, but in Slack we're getting a message from a customer that's saying, "Hey, the checkout's broken for me." and we need to link those together. So what we do is we group the signals. As the signals are being grouped, we assign weights to what we call a report. And if the the weight of the report goes over a certain threshold, we'll promote it. And then we'll kick off a research agent to work on it.

So, uh this was a problem that we faced fairly early on in building this pipeline. Um the first thing that we did was we would take all of our signals and we would create embeddings for them. Uh and then we would try to use that to cluster the issues so that we could find similar or related signals. But this works really badly. So, if you take uh an off-the-shelf embedding model uh and you embed an error. Uh let's say I've got an error about the checkout and I've got an error about onboarding. And then I've got a Slack message about onboarding. What the embedding model will do is it will notice structural similarity and it will put all of the errors together. So, if you think about what this looks like in embedding space, you've got all of your errors over here, all of your Slack messages here, all of your session replays here, and none of them get grouped to each other.

So, the way we get around this uh is instead of matching in embedding space the signals themselves, uh we generate queries based off the signals. So, we ask an LLM what is this signal about? It'll generate a few queries and then we match those queries in uh the embedding space. Yeah, so that's that's really important. If you if you don't uh think about the structural similarity of your different sources when you're grouping them, then the grouping works really badly. So, at first we were doing this and then we switched to this approach. It worked much much better.
</details>

### 闭环修复：从沙盒研究到执行

当我们将相关的信号成功归集并形成一份高质量的问题报告后，我们会将其移交给**研究智能体**（Research Agent）。该智能体正在运行 **Claude Agent SDK**，并被隔离在一个由 **Modal** 提供的沙盒环境中。

这个研究智能体拥有强大的上下文获取手段：
*   **模型上下文协议服务器**（MCP Server: 允许大语言模型动态调取本地化或专属系统数据的标准接口协议）：它使得智能体能够根据当前的会话录屏和报错信息，主动拉取相关的底层日志数据。
*   **全景代码库上下文**：确保智能体知晓系统的当前实现逻辑。
*   **外部系统对接**：通过外部 MCP 接入 Linear 和 **Notion**，极大地提升了将错误现象映射到业务全景图的准确性。

研究智能体最终会输出一份关于该问题的摘要、修复的优先级评估，并利用代码提交记录溯源（`git blame`）自动指定最合适的 PR 审查人员。

随后，系统进入**可操作性评估**（Actionability Step）。如果当前线索不足，问题会被放回池中继续收集数据；如果涉及需要人类决策的产品逻辑改变，问题会被推送到你的待办收件箱。最理想的状态是：问题具备明确的可操作性。像错误追踪工具（如 **Sentry**）提供的数据通常非常具体，编码智能体能极好地解决它们；但对于像 Slack 消息这种更加宽泛的反馈，系统往往很难快速锁定具有即刻可操作性的方案。

一旦问题具备可操作性，流水线将推进到最终的**自动化执行**（Executing the task）。系统会将代码库克隆到类似研究智能体所用的沙盒中，运行 Claude 智能体来编写修复代码并推送 PR。在这个过程中，如果持续集成（CI）抛出失败，或者 PR 收到其他审查智能体的反馈意见，系统会自动重载该沙盒快照并继续迭代代码，直到 PR 显示测试全部通过的绿灯状态。这意味着，当你在早晨醒来时，不需要再手动把满是 Bug 的分支拉取到本地环境去解决问题，你只需审查并合并那些已经绿灯通过的 PR。

<details><summary>Original English Source</summary>
Cool. So, uh once we've got this uh report that we've grouped together a few signals, we've got some kind of idea what's going on. Uh we then have promoted the report because we think it's important enough to work on. And then we're going to hook it up to a research agent.

So, uh this research agent is uh just running that it's running the Claude agent SDK. Uh it's running that in a sandbox. We also use Modal for our sandbox. Uh big shout out to them. They've been great. Um they're not sponsoring me or anything, don't worry. Um, and uh this research agent has a few tools available to it. So, the first tool is it's got our MCP server. Uh, this allows it to, uh, given the group of issues that we found, uh, you want to pull in extra data. So, let's say I'm looking at a session replay and an error, I'll also pull in log data, and the agent can pull in whatever it wants using the MCP server. This makes the results of the research agent way more accurate. Uh, the second thing is obviously it's got the code base context, uh, and then finally it's also got external MCPs. That really helps to like ground the agent when it's doing the research. Uh, we found that in particular Linear and Notion have been really helpful in connecting it to to deliver better results.

So, the output of this research agent then, uh, is a summary of the problem. It gives a priority, how important we think this this problem is to work on, and then it also uses Git blame to figure out who should be reviewing this PR if we create a PR for it.

So, um, after that, we get a bunch of problems that we think are worthwhile to work on. Uh, we've got a kind of idea of what the general problem is, um, and then we pass it to an actionability step. Uh, so here either it will be not actionable. If it's not actionable, it might just be that we don't have enough data yet for this signal, um, for the report, and so we'll put it back into the pool to keep gathering more evidence. Uh, if it needs human input, it might be because it's a product-related decision that the agent can't really make a good call on. Um, so if that happens, we'll put it into an inbox for you to review in the morning. Uh, and then finally the the best case is that it's immediately actionable, uh, and that the agent can just write a fix for it.

Uh, right now the the challenge in this pipeline of getting immediately actionable things is that for some sources like error tracking, uh if you think about your data in Sentry or uh any errors that very specific, and usually a coding agent can work on them really well. For other sources, like Slack or session replay, uh you get much more generic problems that can have a lot of different solutions. And so, that's where it's harder to get immediately actionable reports.

Cool. Um then, once we've researched this thing, we go on to executing the task. Uh this will uh clone the user's repo into a sandbox, uh similar to the research agent. It's then again running the Claude agent SDK to build effects for the problem. Um and then, uh as it writes those fixes, it will uh push a PR. And uh when CI is failing or there's a comment on the PR, it will trigger a rerun of that sandbox. So, at the end of this, we snapshot the sandbox, uh and then, if there's a comment, let's say from an agent who's reviewing it, we will rehydrate that snapshot and continue running until the PR is green. Uh and this delivers really good results. It means when you're waking up in the morning and things have been running overnight, you wake up to, instead of a bunch of CI failures or uh comments that you need to address manually, that you're pulling down to your local environment, you ideally wake up to just green PRs.
</details>

### 评估迭代与成本优化的实践教训

通过构建这套从观测数据直达代码提交的自动化系统，我们总结了四条至关重要的工程教训。

第一，**严谨的评估机制至关重要**（Evals really matter）。在起步阶段，我们曾在本地使用直觉（Vibe Check）来评估修复效果，但这对于需要处理多样化客户数据的真实流水线来说是致命的。如果没有用具有代表性的生产级数据进行系统测试和评估，整个团队基本上就是在黑暗中盲目摸索。

第二，**认清嵌入模型的匹配本质**。正如前文所述，现成的嵌入模型更多是在计算结构上的相似度，而非深层语义。如果你打算在格式各异的异构数据源之间进行聚类，务必仔细思考数据的归一化处理方式。

第三，**防止智能体强行制造“修复”**。如果你把诸如“新手引导流程坏了”这样极度泛泛的信号丢给智能体 SDK，它为了完成任务会盲目地尝试修改代码。系统必须具备主动忽略模糊信号的能力，否则你将被大量充满噪音、毫无实际意义的 PR 淹没。

最后，虽然大家都知道大语言模型的**令牌**（Tokens）是需要真金白银购买的，但**前期的试错成本是对未来优化的投资**。最初由于过度顾虑成本，我们试图在流水线中尽量延迟或减少智能体的调用。这其实是一个误区。只有当你敢于让智能体面对同一个难题运行上百次后，你才会洞察出它巧妙的解决模式。基于这些行为模式，我们成功地将原本极其昂贵的循环研究步骤，压缩成快速的**一次性调用**（One-shot LLM Call: 无需多轮对话，通过一次高密度的提示词直接获取结果的调用方式），甚至是训练出更加轻量专属的微调模型，最终实现了系统的经济与高效。

这便是我们在 PostHog 取得的进展。虽然这项功能还在内部测试（Alpha）阶段，但我们的终极愿景是一个“能够自我进化的产品”。作为开发者，你的核心价值在于创造激动人心的新功能，而不是深陷于客户反馈的无尽 Bug 堆，或被迫执行关于定价策略的枯燥实验。放手让一个智能体去试试看它能对你海量的业务数据做些什么吧，我相信结果一定会让你感到惊叹。

<details><summary>Original English Source</summary>
Cool. So, um what did we learn whilst building this? Uh well, the first thing, which I guess we've talked about in the last talk, uh is that evals really matter. Um so, at first, we were trying this all out on our own data locally, doing kind of a vibe check, is this okay? Um but this this really doesn't work well for a pipeline that is is taking lots of uh customer data that's different. Um so, you really need to know what's going on in production, and if you're not testing on representative data, it your you're basically just fumbling in the dark, right? Like the ability to iterate on a really good pipeline matters uh only if you if you're using e-bikes.

Second thing is what I said before, uh make sure you're embedding the right thing. Um embedding models uh the off-the-shelf ones are matching a lot based on structural similarity, not just semantic similarity. So, if you're thinking about clustering and your data isn't all of the same format, think carefully about what that data looks like and how you can normalize it.

Uh the third thing is that uh if you just throw an agent at a problem, it will try to fix something. So, if you get uh uh if you get a signal report that's like "Onboarding is broken" in a generic way, then if you throw that at the agent SDK or at Claude code, it will just try and fix something. Uh and so, it's important to understand if the problem that I've described is it specific enough uh and if not, I should ignore it. Otherwise, you end up with a a lot of noisy PRs that aren't doing meaningful things.

And then the fourth one is uh that tokens are free. Uh obviously, that's not true. They're not free. Um but when you're experimenting, uh we were at first uh focused a lot on the costs of the pipeline. When you think about the input, you've got loads of signals coming in. Uh and so, we tried to avoid using agents where we could or delay it till as late as possible in the pipeline. And when we were experimenting, this was a big mistake. Um mainly because uh when you throw an agent at a problem, you once you throw it at the same problem 100 times, you start seeing the kind of clever solutions that it comes up with and eventually you see similarities. So, we started at a point where this pipeline is completely unfeasible. It was it was way too costly to generate a PR, but then you quickly start to see uh similarities in the agent's behavior and you can take a really expensive step that you're running an agent for uh and turn that into a one-shot LLM call or a model that you're training that's much faster.

Cool. Um so, this is where we are right now. This is what we've built. Uh we have the signals coming in from product data. Uh these are grouped into reports, and we're turning these into PRs that are ready to merge when you wake up. This is currently something that's in alpha. We'll be rolling it out kind of over the next few months.

Um but where we really want to go is is a product that builds itself, right? Like when you're thinking about what you do day-to-day, what you want to do during the day as a developer is like come in and work on exciting features and not worry about all the bugs that customers are sending you or worry about doing boring experiments on pricing or onboarding. So, we just want to do that all for you. Uh we want to ship experiments automatically, measure the impact of them. Uh instead of you reviewing changes, if the change is pretty easy, let's just approve it with an agent and deploy it behind a feature flag. If it doesn't work very well, we can always roll back the flag and then delete it from our code base later.

Uh and then the other thing that we want to do and get better at is we want to learn from every single outcome. So, if we're creating a PR for you, if you're rejecting that PR or there's been an issue with a deployment or the errors resolved in production once we've released something, we want to get better at learning from that in the next PR that we're generating. That's something that we're going to be iterating a lot in the pipeline next.

Cool. Um yeah, that's it. That's what we've built in PostHog. Um if you're excited by uh looking at thinking about what you can do with agents and data, I really recommend if you've got a product that's producing a huge amount of data, your users are going through that. Agents are amazing at this stuff. Throw an agent at it. See what it does. I'm sure you'll be surprised.
</details>