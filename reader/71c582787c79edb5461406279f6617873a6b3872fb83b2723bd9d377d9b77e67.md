---
author: AI Engineer
date: '2026-04-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=juoNbJiZUi0
speaker: AI Engineer
tags:
  - llm-challenges
  - autonomous-agents
  - code-generation
  - model-rot
  - developer-tools
title: LLM代码生成挑战与PostHog Wizard的解决方案
summary: 本次访谈探讨了大型语言模型（LLM）在代码生成方面遇到的挑战，包括模型衰败、架构不当、路径选择怪异、人类错误以及安全隐患。演讲者Denilo分享了PostHog Wizard如何通过提供最新文档（RAG）、使用“模型飞机”作为参考、对代理进行“面包屑式”引导、进行运行时事后询问以及精细化工具控制等策略，来克服这些问题，确保LLM能够生成可靠且用户满意的集成代码。访谈强调了纯文本和结构化数据在未来LLM应用中的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - PostHog
  - Anthropic
products_models:
  - PostHog Wizard
  - Claude agent SDK
media_books: []
status: evergreen
---
### 导言

**Denilo**: 早上好。

<details>
<summary>Original English</summary>

**Denilo**: Good morning.

</details>

**Denilo**: 谁害怕机器人？害怕机器人。害怕机器人。

<details>
<summary>Original English</summary>

**Denilo**: Who's afraid of robots? Afraid of robots. Afraid of robots.

</details>

**Denilo**: 嗯，我不害怕机器人，因为它们已经多次让我碰壁了。它们再也无法给我带来痛苦了。这就是我想在这个美好的早晨告诉你们的。感谢大家来和我一起。所以，我的名字是 Denilo。我在 **Post Hog** 工作，我制作 **Post Hog Wizard**。

<details>
<summary>Original English</summary>

**Denilo**: Uh, I'm not afraid of robots because they have already bloodied my nose so many times. There is no more pain that they can give to me. And that is what I want to tell you about on this fine morning. Thanks for coming to hang with me. So, my name is Denilo. I work at Post Hog and I make the Post Hog Wizard.

</details>

**Denilo**: 而 Post Hog Wizard 做的一件非常奇怪的事情是，它跳过了你生命中永远无法挽回的两小时痛苦，并将它们变成了 8 分钟的伪娱乐。

<details>
<summary>Original English</summary>

**Denilo**: And the very strange thing that the post hog wizard does is it skips two hours of misery that you will never get back in your life and it hands it back to you as 8 minutes of pseudo entertainment.

</details>

**Denilo**: 现在，我们是如何做到的呢？

<details>
<summary>Original English</summary>

**Denilo**: Now, how do we get away with this?

</details>

**Denilo**: 我们每个月有 15,000 人运行这个向导，作为回报，他们得到了一个有效的 **Post Hog** 集成，并且他们实际上很喜欢。

<details>
<summary>Original English</summary>

**Denilo**: We're talking 15,000 people every single month run this wizard and in exchange for their trouble, they get a Post Hog integration that works and that they actually like.

</details>

**Denilo**: 我们是怎么做到的？我今天会告诉你们所有细节。而且，为了强调这一点，这确实有效，在过去的 6 小时内，我们收到了 **Blue Sky** 和 **Twitter** 上两条未被提示的帖子，人们对此感到非常满意。

<details>
<summary>Original English</summary>

**Denilo**: How do we do it? I'm going to tell you all about it today. And just to underscore the point that this actually works within the last 6 hours, we get two unprompted posts on Blue Sky and Twitter where people are actually happy.

</details>

**Denilo**: 现在，这应该很可怕，对吧？我那里有一个机器人。它在为人们写代码。

<details>
<summary>Original English</summary>

**Denilo**: Now, this should be terrifying, right? I got a robot out there. It's writing code for people.

</details>

**Denilo**: 如果它做得不好怎么办？嗯，我们已经了解了它可能做得不好的所有方式。我将告诉你们这些糟糕的工作是如何发生的。我将告诉你们一些策略，你们可以用来确保你们的自主编码代理也能做正确的事情。好了，我们从简单的一项开始。我们遇到了**模型衰败**（model rot）。

<details>
<summary>Original English</summary>

**Denilo**: What if it's doing a bad job? Well, we learned all the ways that it could do a bad job. I'm going to tell you the ways that those bad jobs happen. I'm going to tell you some strategies that you can use so that your autonomous coding agents do the right thing as well. All right, let's start with the easy one. We got model rot.

</details>

**Denilo**: 训练一个模型需要花费大量时间，但关键的不是时间。是钱，对吧？你不会像 **Anthropic** 那样，在周末随便训练一个模型，对吧？这是一笔严肃的资本支出。

<details>
<summary>Original English</summary>

**Denilo**: Now, training a model takes a lot of time, but it's not even the time. It's the it's the money, right? You're not screwing around as anthropic training a model on a weekend as a lark, right? This is serious capital expense.

</details>

**Denilo**: 而这带来的权衡是，模型会一直存在，不再代表现实，对吧？它们只是世界和网络的快照，就像 6、8、12、18 个月前那样。

<details>
<summary>Original English</summary>

**Denilo**: And the trade-off with this is that the models sit there no longer representing reality, right? They are a snapshot of the world and the web as it was, you know, 6 8 12 18 months ago perhaps.

</details>

**Denilo**: 这对很多事情都有用，但如果你是一个快速发展的软件项目，而且有很多快速发展的软件项目，那么这种权衡就是模型不再知道发生了什么。所以，你必须处理模型衰败。这相当直接。你可能以前处理过这类事情。

<details>
<summary>Original English</summary>

**Denilo**: Now, this is useful for many things, but if you're a fastmoving software project, and there are loads of fastmoving software projects, the trade-off of this is that the model doesn't know what the hell is going on anymore. So, you got to deal with model rot. Now, this is fairly straightforward stuff. You've probably dealt with this sort of thing before.

</details>

**Denilo**: 有没有人对如何处理模型衰败有定论？有什么猜测吗？看到一些人在摇头。那是什么？

<details>
<summary>Original English</summary>

**Denilo**: Does anyone here have a conviction about how you deal with model rot? Any guesses? Seeing some shaking heads. What's that?

</details>

**听众**: RAG。

<details>
<summary>Original English</summary>

**Listener**: Rags.

</details>

**Denilo**: RAG 很好。虽然，我得说，就目前的**上下文窗口**（context windows）而言，你无法超越直接将一大堆 markdown 文件塞进上下文并修补其中的漏洞。

<details>
<summary>Original English</summary>

**Denilo**: Rags is good. Although, I'll tell you what, with the context windows being what they are at this point, you can't beat just shoving a bunch of markdown files into the context and patching the holes.

</details>

**Denilo**: 这正是我们用 Post Hog Wizard 所做的——我们有来自 postto.com 的最新文档，我们允许代理进行选择。我们说：“嘿，你在做什么？你在这里集成什么？我们检测到了什么？”代理可以使用工具进行查找，从一个菜单中选择新鲜的、最新的 markdown，然后将其直接放入其上下文中，完成工作，正确地做事。

<details>
<summary>Original English</summary>

**Denilo**: And this is exactly what we do uh with the Postthog Wizard is that we have documentation that is fresh, hot off the presses on postto.com and we allow the agent to make a selection. We say, "Hey, what are you doing? What are you integrating right here? What have we detected?" And the agent can use tools to go out, pick from a menu of fresh hot markdown that it can then just slide right into its context, get the job done, do things correctly.

</details>

**Denilo**: 现在，这一切的催化是什么呢？是一年前，人们开始向他们非常原始的代理询问，比如：“好吧，光标，我想让你为我集成 Postto。”

<details>
<summary>Original English</summary>

**Denilo**: Now, what happened to spur all of this was that a year ago, people started asking their very primitive agents like, "All right, cursor, I want you to integrate Postto for me."

</details>

**Denilo**: 而它会做得一团糟，对吧？它只是在编造键名。它在编造模式。它在发明不存在的 API。而且，这不是我们的错。我们什么都没做，但这是我们的问题。所以，找出我们如何为代理提供正确、最新的上下文，以便它能做正确的工作，这是我们如何让人们对 Wizard 为他们所做的事情感到满意的一部分。好了。

<details>
<summary>Original English</summary>

**Denilo**: And it would do a terrible job, right? It's just it's making up keys. It is making up patterns. It is inventing APIs that don't exist. And it is it's not our fault. Like we didn't do anything, but it was our problem. So figuring out ways that we could serve correct upto-date context to the agent so that it would do the correct job is part of how we get people posting happy about what the wizard did for them. All right.

</details>

### 架构问题

**Denilo**: 现在，这些模型，我的意思是，显然它们一直在抓取各种项目。我猜不是所有的项目都有很好的架构，因为这些代理在构建项目时做出的一些决定非常奇怪。

<details>
<summary>Original English</summary>

**Denilo**: Now, these models, I mean, clearly they've been scraping every kind of project out there. And I have to guess that not all of them had great architecture because some of the decisions that these agents make when they're putting a project together are very strange.

</details>

**Denilo**: 嗯，那么你该怎么办？你如何处理代理对如何构建某事的看法可能在技术上是可行的，但并非完全理想的事实？嗯，我和 **Post Hog Wizard** 团队的伙伴们一起，维护着我们称之为“**模型飞机**”（model airplanes）的车队。

<details>
<summary>Original English</summary>

**Denilo**: Uh, and so what do you do? How do you deal with the fact that an agent's conception of how to put something together may be technically like workable but not exactly ideal? Well, me and my homies on the Post Hog Wizard team, we maintain a fleet of what we call model airplanes.

</details>

**Denilo**: 这些是已经实现了 Post Hog 的项目。它们涵盖了多种框架和多种语言。但使它成为“模型飞机”的是，我们没有在那里部署一个完整的、标准的生产应用程序。我们拥有的是更精简的东西。一种真实应用程序的仿制品。

<details>
<summary>Original English</summary>

**Denilo**: And these are projects that have Post Hog implemented in them. They've got them across a bunch of frameworks, a bunch of languages. But what makes it a model airplane is that we don't have an entire proper production application going in there. What we have is something much thinner. Something that is a similacrim of a real application.

</details>

**Denilo**: 但例如，登录功能不起作用。或者更确切地说，登录功能对任何事情都有效。你可以在密码字段中输入任何你想要的东西，你就可以登录。但是登录是“Oshshaped”（形状奇怪），这意味着我们可以提供这些模型飞机给代理，然后代理就知道，哦，太好了。当出现登录时，这是一个放置特定事件跟踪的好地方，当你想要跟踪登录和身份验证时可以使用。

<details>
<summary>Original English</summary>

**Denilo**: But for example, the O doesn't work. Or rather, the O works for anything. You can just put whatever you want in the password field and you're going to be able to log in. But the O is Oshshaped which means that we can provide these model airplanes to the agent and then the agent knows, oh cool. So when O shows up, this is a great place to put the particular event tracking that one would want to use when they wanted to track login and identity in post.

</details>

**Denilo**: 因此，通过维护一个不像真实生产应用程序那么复杂的东西，这意味着它也更节省 token，你得到的是一个集成正确形状的模式，模型和代理能够始终如一地完成它。

<details>
<summary>Original English</summary>

**Denilo**: And so through the maintenance of a thing that isn't quite as elaborate as the real production application, which means also of course it is more token efficient, what you get is the correct shape of an integration as a pattern that the model and agent are able to complete consistently every time.

</details>

### 路径限制

**Denilo**: 好了。所以，除了奇怪的架构之外，代理还可以找到一条奇怪的路径来解决问题空间。每月有 15,000 次集成，它可能会找到 15,000 种完成 Post Hog 集成的方式。

<details>
<summary>Original English</summary>

**Denilo**: All right. So in addition to weird architecture, the agent can find a weird path through the problem space. And with 15,000 integrations per month, it might find 15,000 ways to get a post hog integration done.

</details>

**Denilo**: 虽然这满足了我们已经实现了自动集成的要求，但它会给我们带来非常奇怪的支持负担，因为我们将有太多不同的方式来设置 Post hog。就像，这到底是什么？我该如何理解它？这在规模上会是个问题。这会是一些“学徒魔法师”式的东西。

<details>
<summary>Original English</summary>

**Denilo**: And while this would satisfy the requirements of we've automated integration, it would leave us with a very strange support burden because we would have too many different ways that Post hog was set up. It's like what what what the hell is this? How do I make sense of this? Right? This would be a problem at scale. This would be some sorcerers apprentice stuff.

</details>

**Denilo**: 所以，为了限制即兴发挥，我们所做的是“**面包屑式**”（breadcrumb）地引导代理。我们不会事先确切地告诉代理我们要做什么。你知道，也许你以前也见过这种情况，即使你使用命令行代码，如果你告诉他们你想去的地方，它可能会在头四个任务中挖一个命令行代码形状的洞，然后在第五个任务时变得非常粗糙，对吧？这不符合我们的情况。

<details>
<summary>Original English</summary>

**Denilo**: So to limit improvisation, what we do is breadcrumb the agent. We don't tell the agent upfront exactly what we're going to do. You know, maybe you've seen this before even when you're using clawed code is that if you tell them exactly where you want to go, it might make a claw code shaped hole through the first four tasks and then just get really rock polishy with the fifth, right? And this is not what we want for our case.

</details>

**Denilo**: 所以，我们所做的一件事是，我们一开始甚至几乎不告诉代理我们在做什么。我们甚至不提我们正在做一个 Postto hugg 集成。我们从类似这样的问题开始：“这个项目中有哪些文件具有有趣的业务价值？你能找到看起来像登录页面或 Stripe 界面，或者可能表明某人即将流失的东西吗？”

<details>
<summary>Original English</summary>

**Denilo**: And so one of the things that we do is we start off barely even telling the agent that this is what we're doing. We don't even mention really that we're doing a Postto hugg integration. We start with something like where are the files with interesting business value in this project? Can you find something that looks like a login or a Stripe interface or something that might indicate someone's about to churn?

</details>

**Denilo**: 对吧？我们去寻找那些能对某人业务产生影响的文件。有趣的是，这些业务相关的东西在代码中留下了巨大的印记。因此，我们可以非常可靠地检测到这类东西。

<details>
<summary>Original English</summary>

**Denilo**: Right? We go looking for the files that would be responsive to impact in somebody's business. And the funny thing is that business stuff casts a huge shadow in code. And so we can very reliably detect this kind of stuff.

</details>

**Denilo**: 从那里开始，我们说，好的，这里有一些很棒的文件。这些文件中有哪些有趣的事件在发生？现在不要写任何代码。让我们来思考一些我们可能想在这里加入的酷事件。它们可能是什么？所以我们列出了这些。我们得到事件名称。我们得到这些事件的描述。然后我们只是把它们塞进一个小文件里。

<details>
<summary>Original English</summary>

**Denilo**: Now from there we say okay here are some cool files. What are the interesting events going on in those files? Don't write any code right now. Just let's think about some cool events that we might want to sprinkle through here. What might those be? So we make a list of these. We get the event names. We get the descriptions for those events. And we just tuck them into a little file.

</details>

**Denilo**: 这是一切的开始，对吧？我们甚至不一定知道我们要去哪里。所以下一个面包屑是，好的，让我们开始实际实现 Post Hog。我们现在知道了一堆事件，并且我们已经仔细考虑了这些事件可能是什么。现在我们有了文档和其他一切，我们可以根据我们关心的框架和语言随时加载。因此，我们可以可靠地进入其中，开始修改人们的文件。而这些修改再次不是愚蠢的。嗯，他们对此并不生气。

<details>
<summary>Original English</summary>

**Denilo**: And this is the start of things, right? Like we don't even know where we're going necessarily. And so the next breadcrumb is like, okay, let's start to actually implement Post Hog. We now know a bunch of events and we've really thought carefully about what those events might be. And now we have documentation and everything which we can load uh at whim according to the framework and language that we care about here. And so we can reliably go in there and start to make modifications to people's files. And the modifications are once again not stupid. um and and they're not mad about it.

</details>

### 人类错误与安全

**Denilo**: 好的。现在，我们可以做所有能让代理成功的周到工作，但对我们代理结果的最大威胁是我们自己。我们是渺小的生命。我们的大脑里只有一点点肉。而且我们也有上下文限制。我们无法真正量化它。它取决于我们多久前喝过咖啡，以及那天早上是否吃过早餐。我们的上下文不仅是有限的，而且是零碎的。

<details>
<summary>Original English</summary>

**Denilo**: Okay. Now, we can do all of the thoughtful stuff that we can to make the agent successful, but the biggest threat to our agent outcomes is ourselves. We're we're feeble little beings. We got a little bit of meat right here locked inside of our heads. And we have a context limit, too. We can't really quantify it. And it varies by how long ago we had some coffee and if we had breakfast that morning.

</details>

**Denilo**: 我们会记得上周实现的东西，也会忘记上个月的东西。所以我们正在做出改变，我们正在编辑代码，我们正在改进我们的代理正在处理的东西，有时我们会丢掉真正重要的东西。

<details>
<summary>Original English</summary>

**Denilo**: Our context is not just limited but fragmentaryary. There's stuff that we remember implementing last week and there's stuff that we forgot from last month. And so we're making changes and we're editing code and we're evolving the stuff that our agent is working around and sometimes we are dropping things that really matter.

</details>

**Denilo**: 所以曾经有过一个时候，我们有一个 MCP（主控制程序）工具指令与另一个工具相矛盾。代理就像，老兄，我不知道该怎么办。你把我置于一个不可能的境地。嗯，我们遇到过一种情况，我们告诉它，嘿，有一个工具你绝对需要使用来完成这个设置。代理正在接近，好的，酷。让我们使用这个工具。等等，MCP 没有这个名字的工具。

<details>
<summary>Original English</summary>

**Denilo**: And so there was a point where we had an MCP uh tool instruction that was contradictory to a different tool. And the agent is like, man, I don't know what to do here. You you you're putting me into an impossible spot. Um we had um a situation where we were telling it, hey, there's a tool that you definitely need to use to conclude this setup. And the agent's getting there, all right, cool. Let's let's use the tool. Wait, the the MCP does not have a tool by this name.

</details>

**Denilo**: 我们谈论的是数百次运行都因为这个缺失的工具而失败。那里发生了什么？所以，如果我们不问，我们就不会知道。因此，你可以做的一件非常方便且相对廉价的事情是，在推理时对你的代理刚刚发生的事情进行一点点事后询问。

<details>
<summary>Original English</summary>

**Denilo**: And we're talking like hundreds of runs going with this missing tool. And what's going on there? So if we didn't ask, we wouldn't know. And so one of the things that you can do that is really handy and fairly cheap is a little bit of inference time interrogation of what just happened with your agent.

</details>

**Denilo**: 所以，在每次运行结束时，在停止钩子处，我们问一个非常简单的问题。我们正在做一点用户研究，但用户在这种情况下是一个机器人。我们问机器人用户：“嘿，为了让你这次运行成功，我们还能做些什么？”然后它会告诉我们，这就是我们发现的原因，哦，我们没有给你访问工具的权限，所以没有工具。嘿，你收到了这些相互矛盾的指令。

<details>
<summary>Original English</summary>

**Denilo**: So, at the end of every run, uh, right at the stop hook, we ask a very simple question. We're doing a little bit of user research, but the user is, in this case, a robot. And we ask the the robot user, hey, what could we have done better to set you up for success in this run? And then it tells us, and that's how we found out like, oh, we we didn't give you permission to access the tool, and so there was no tool. Hey, you've got these contradictory directives um

</details>

**Denilo**: 没有这种持续的询问。哦，一个好例子是，我们一直在给它 JavaScript 的指令，而它正在处理一个 Python 项目。嗯，当然，非常嗯，不令人沮丧，但你知道，我们会那样识别它。嗯，所以人类错误，大事。你必须问才能找出答案。

<details>
<summary>Original English</summary>

**Denilo**: without this ongoing interrogation. Uh oh, a good one is that we kept giving it instructions for JavaScript and it was a Python project that it was working in. Um, of course, very um well, not frustrating, but you know, we would identify it that way. Um, so the human error, big deal. You have to ask to find out.

</details>

**Denilo**: 现在，你还需要担心一些**鬼把戏**（shenanigans），因为在别人的机器上运行代理需要大量的信任，对吧？我们有一个机器人，它可能做任何事情，我们不想做一些坏的或破坏性的事情来损害用户的项目。我们不想让他们陷入更糟糕的境地。

<details>
<summary>Original English</summary>

**Denilo**: Now, there's also shenanigans that you got to be concerned about here because running an agent on someone else's machine demands a huge amount of trust, right? We we've got this robot that could do anything potentially and we don't want to do something uh bad or destructive to the user's project. We don't want to put them in a worse spot.

</details>

**Denilo**: 嗯，在我们向导的早期版本中，它实际上会读取 .env 文件，这是进行写入所必需的，对吧？你不能盲目地写入文件。这只是这些代理工作方式的一种机制，但将人们的 .env 内容发送到云端，然后就像，好吧，酷。它就坐在你不知道的某个日志里，这也不是理想的做法。

<details>
<summary>Original English</summary>

**Denilo**: Um, and one of the early versions of our wizards would actually just read .env files, which is necessary to do writes, right? You can't just write blind to a file. It's just one of the mechanics of how, you know, these agents work, but it's also not ideal to be sending people's EMV contents up to a cloud and just like, all right, cool. That's sitting in someone's damn log that you don't know about.

</details>

**Denilo**: 嗯，这显然是个坏消息，但当你设计这些东西时，你对工具的使用有细粒度的控制，对吧？你可以决定，好的，这些工具是可以的，这些类型的读取是可以的，这些类型的读取是不可以的。所以，我们严格限制了代理在处理任何 .env 文件时所能做的事情。然后我们能够为它构建一个工具，它可以做两件事。它可以检查一个键是否存在？这个键存在吗？它可以向一个键写入一个新值，仅此而已。

<details>
<summary>Original English</summary>

**Denilo**: Um, so this was obviously bad news, but when you're designing these things, you have fine grain control over tool usage, right? You can decide, all right, these tools are okay, these kinds of reads are okay, these kinds of reads are not okay. So, we really locked down what the agent was allowed to do around anything that was an ENV file. And then we were able to build it a tool that could do two things. It could check the presence of a key. does this key exist?

</details>

**Denilo**: 没有关于这个 .env 文件的推理。因此，结果是，我们不再接触这些东西了。但是，伙计，你正在把这些机器人放到任何人的电脑上。你必须留意这些鬼把戏，因为即使你解决了你承诺要解决的问题，你也可能以一种让你看起来像个……的方式来解决它。

<details>
<summary>Original English</summary>

**Denilo**: And it could write to a key a new value and that was it. There was nothing that was going up in terms of inference for this EMV file. And so as a result, we were no longer touching this stuff. Uh but again, man, you you are setting loose these robots on anybody's computer. You got to keep an eye on these shenanigans because even if you're kind of solving the problem you promised you'd solve, you might be doing it in a way that makes you look like an

</details>

### 代码的价值衰减

**Denilo**: 好了。现在，这是大事。这是奇怪的一点，因为我们整个职业生涯都通过编写代码获得了回报。我们写代码。我们写更多的代码。我们写聪明的代码。哦，我这里有一个结构。这个东西能用。这个东西很可靠。这个东西很复杂，但性能非常好。我们必须通过编写代码来解决这个问题。如果我们能通过编写代码解决这个问题，一切都会很棒，对吧？

<details>
<summary>Original English</summary>

**Denilo**: All right. Now, this is the big one. This is the weird one because our whole careers we have been rewarded by writing the code. We write the code. We write more more code. We write the clever code. Oh, I got a structure in here. This thing works. This thing is reliable. This thing is elaborate, but the performance is really good. And man, we just got to code the out of this thing. If we code our way out of this problem, everything's going to be great, right?

</details>

**Denilo**: 这不再是我们生活的世界了。关于代码的一件非常有趣的事情是，如果你今天写了一些你认为很好的代码，而明天一个新的模型发布了，你写的代码的价值就完全一样了。如果说有什么不同的话，它可能还在下降。对吧？代码一直是一种贬值资产。你写了它，你可能把它送到世界上时已经有点腐烂了，因为你有一些技术债务，你必须在某个时候处理它。但与此同时，你按时发货了。你做了你必须做的事情。

<details>
<summary>Original English</summary>

**Denilo**: That is not the world that we live in anymore. And a very funny thing about code is that if today you have written some code that you think is good and tomorrow a new model drops, the code that you wrote has the exact same value. If anything, it might be declining a bit. Right? Code has always been a depreciating asset. You write it, you might ship it into the world a little bit rotten because you got some tech debt and you got to deal with that. at some point, but meanwhile you shipped on time. You got what you had to do.

</details>

**Denilo**: 让每个人都开心的向导 90% 是 markdown 文件，8% 是用于交付和处理 markdown 文件的工具，然后其余的是代理的“**代理 the agent**”（agent harness）之类的东西，对吧？**纯文本散文**（Plain text pros）是我们现在很多价值所在的地方。

<details>
<summary>Original English</summary>

**Denilo**: The wizard that makes everybody so happy is 90% markdown files, 8% tools for delivering and processing markdown files, and then the rest is like agent harness stuff, right? Plain text pros is where so much of our value now lives.

</details>

**Denilo**: 当你今天写出优秀的散文，明天一个更好的模型发布时，它将能够利用这些散文做更多的事情。所以，代理就像一个章鱼，对吧？它可以扭动。它可以挤进狭窄的角落。它可以围绕问题进行机动。你不想过度限制代理完成问题的能力。除了我们谈过的鬼把戏之外，对吧？

<details>
<summary>Original English</summary>

**Denilo**: When you write great pros today and tomorrow an even better model drops, it's going to be able to take that pros and do even more with it. And so an agent is an octopus, right? It can wrigle. It can squeeze into tight corners. It can maneuver itself around problems. You do not want to overconstrain the agent in its ability to get problems done. Aside from the shenanigan stuff as we talked about, right?

</details>

**Denilo**: 所以，与其思考， man，我该如何为这个代理的行为搭建框架？不如思考，我该如何退后一步，如何给它足够的信息，以及我该如何安排我给它的信息的顺序，以便它能做我想让它做的事情，并在过程中让人们满意。

<details>
<summary>Original English</summary>

**Denilo**: So instead of thinking about like man, how can I scaffold the hell out of the behavior of this agent? It's about saying how do I step back, how do I give it enough information and how do I sequence the information that I give it so that it does the thing that I want it to do and it makes people happy in the process.

</details>

**Denilo**: 所以这就是我从机器人弄疼我鼻子中学到的。我看到时钟，还有几分钟时间。有人对构建这个让人们开心的机器人这个奇怪的冒险有疑问吗？

<details>
<summary>Original English</summary>

**Denilo**: So this is what I know from the robot bloody my nose. I see on my clock here, I got a couple minutes left. Does anyone have questions about the strange adventure of building this robot that makes people happy?

</details>

**听众**: 请讲。

<details>
<summary>Original English</summary>

**Listener**: Shoot.

</details>

**Denilo**: 是的。

<details>
<summary>Original English</summary>

**Denilo**: Yeah.

</details>

**听众**: 那是如何组织的？

<details>
<summary>Original English</summary>

**Listener**: Is that how is that structured?

</details>

**Denilo**: 哦，当然。所以我们为向导提供上下文的方式是使用从我们的上下文服务生成的**技能文件**（skill files）。因此，该上下文服务将获取所有这些模型飞机，将它们展平成一个单一的 markdown 文件，然后将它们包含在技能文件中作为参考。因此，我们始终可以访问模型可以处理的完整模型飞机。

<details>
<summary>Original English</summary>

**Denilo**: Oh, sure. So the way that we drive context for the wizard is we use skill files that are generated from our context service. And so that context service is going to take all of those model airplanes, flatten them into a single markdown file and then include them as a reference in the skill file. And so we always have access to the full model airplane which the model can gp and otherwise churn through.

</details>

**Denilo**: 只是不同的技能。

<details>
<summary>Original English</summary>

**Denilo**: I just different skill.

</details>

**听众**: 哦，当然。

<details>
<summary>Original English</summary>

**Listener**: Oh, sure.

</details>

**Denilo**: 所以，是的，这只是包含在技能中的补充内容的一部分。所以，我们发现我们可以将各种有用的输入包含在技能文件中。所以我们有文档，它是纯文本散文，但我们也包含了模型飞机，这样它就能看到成功集成的形状，并且它将所有这些作为完成工作的一部分进行引用。

<details>
<summary>Original English</summary>

**Denilo**: So, yeah, this is just part of the supplemental content that is included in the skill. And so, what we found was there was a range of useful input that we could include as part of the skill file. So we've got documentation which is plain text pros but then we also include the model airplane so that it can see the shape of a successful integration and it references all of that as part of getting the job done.

</details>

**听众**: 是的。

<details>
<summary>Original English</summary>

**Listener**: Yeah.

</details>

**Denilo**: 是的。射击代理，比如……

<details>
<summary>Original English</summary>

**Denilo**: Yeah. Shooting agents like

</details>

**听众**: 哦，当然。所以这使用了 **Claude agent SDK**，我们将其包装在 CLI 中。所以你只需运行一个命令，然后我们通过登录 Post Hogs 为你提供免费推理。我们有一个 **LLM 网关**，我们可以代表你支付所有 token 的费用。嗯，这很混乱，因为有时 Claude 代码会将 O 信息存储在我们意想不到的地方，然后它就会对人们不起作用。

<details>
<summary>Original English</summary>

**Listener**: Oh sure. So this uses the claude agent SDK which we then wrap inside of a CLI and so you just run a single command and then we give you free inference by logging into Post Hogs. We've got this LLM gateway where we could cover all of the tokens on your behalf. Um which was a whole zoo because sometimes clawed code would store O information in a place that we weren't expecting and then it would just break for people.

</details>

**Denilo**: 嗯，这就像，这是早期作为一项服务进行的。是的。还有什么我可以告诉你的吗？

<details>
<summary>Original English</summary>

**Denilo**: Uh it's it's early days for doing this as kind of a service. Yeah. Anything else I can tell you?

</details>

**Denilo**: 那么，我将退出下一位演讲者的位置。感谢大家的参与。很高兴见到你们。祝你们度过愉快的一天。

<details>
<summary>Original English</summary>

**Denilo**: Well, then I'm going to scoot out of the next speaker's way. Thank you for hanging out. It's great to see you. Have yourself a great rest of your day.

</details>