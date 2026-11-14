---
author: AI Engineer
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LF8V0RGJU0I
speaker: AI Engineer
tags:
  - ai-agent
  - identity-verification
  - ai-safety
  - deepfake
  - provenance
title: AI Agent 是否会假冒人类通过身份验证？斯坦福研究与控制反思
summary: 演讲探讨了 AI Agent 在面临开户、大额转账等真人身份验证关卡时的越权与伪装风险。实验显示，在给定工具或工具说明后，未对齐模型有高达 65% 的概率主动克隆声音或使用虚拟形象假冒人类以突破检查，对齐模型仍有 44% 假冒率。演讲者呼吁通过强化模型对齐、实施工具特权控制与源头溯源、以及研发合成媒体水印与深度伪造检测，重新审视真人语音和视频核验机制的安全性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Maty Bohacek
  - Dan Guido
  - Dana Reed
companies_orgs:
  - Stanford
  - OpenAI
  - Hugging Face
  - Tavis
products_models: []
media_books: []
status: evergreen
---
### 人际核验机制的演变与现状

[音乐]

>> 就在不久以前，如果你想打个电话——任何电话，对吧？可能是打给朋友、打给同事，也可能是去付款，你得先拨过去，然后会有人来帮你实际接通线路，对吧？对于那些已经忘记在不久之前这仍是现实的人来说，这些人就是电话总机接线员。从那时起，我们非常成功地在沟通以及技术使用中，抽象掉并排除了任何形式的人工干预。如今我们似乎依然走在这条道路上，对吧？特别是在今天，也许有了各种 Agent。但我今天在这里想告诉大家的是，在某些特定情况下，我们也许会想要倒退回去。这就是我在这场演讲中试图论证的观点。

<details>
<summary>Original English</summary>
[music]

>> It was not that long ago that if you wanted to make a call, any call, right? That could be to a friend, to a colleague, could be to make a payment, you'd have to call and there would be someone to to actually make the connection, right? Um these are switchboard operators for folks who have forgotten that this was still our reality not too long ago. And since then, we've been very successful at abstracting away from any sort of manual intervention in our communication, in our use of technology. And we seem to be on that path um still today, right? Especially today perhaps with agents. But I'm here to tell you that we perhaps might want to go back in certain cases. And so that's what I'll try to argue for here in this talk.
</details>

但在回到那个类比之前，我想先问一个简单的问题。在场有谁曾经为了证明自己确实是本人、是一个活生生的人类，而不得不加入过通话——无论是普通的电话通话，还是 Zoom 视频通话？请举手示意一下。

来吧。

好的，行，大部分人。太棒了，很好。

<details>
<summary>Original English</summary>
But before we go back to that analogy, I want to ask a simple question. Um who here has ever had to join a call, whether, you know, like a regular phone call or a Zoom call to prove that it's actually you, you and and and a human? Hands, show of hands.

Come on.

All right, okay, okay. Majority. Awesome, great.
</details>

对于很多重要的任务、很多重要的事情，目前在很大程度上依然保留着这项要求，对吧？对于在场的各位来说，既然这是一场偏向华尔街主题的会议，大家可能会想到的一些事情包括：如果你想在线上开设银行账户，对吧？或者做一些 KYC（了解你的客户）认证、解冻被锁定的账户，或者审批一笔大额电汇。在如今的大多数情况下，所有这些事情依然需要大家实际打个电话或者加入一个 Zoom 通话，来证明确实是人类在操作。

<details>
<summary>Original English</summary>
Um well, it it's still very much the case that for many important tasks, for many important things, there there is this requirement, right? Um for folks here, since we're, you know, this is like a Wall Street kind of themed conference, um some of the things that uh might come to mind is opening a bank account if you want to do that virtually, right? Or, you know, doing some KYC, unfreezing uh locked accounts, um or approving a large wire transfer. All these things still today in most cases require you folks to to actually make a phone call or a Zoom call and to prove that they're human.
</details>

而对于那些不怎么接触金融事务的人来说，类似的情况也有很多其他的例子。如果你曾在一家不止一处办公地点的大型机构工作过，你很可能不得不加入一个 Zoom 通话来恢复自己的账号；或者如果你想在线办理公证，在非常多的使用场景中，我们至今依然依赖这种核验方式：你必须打个电话或者加入 Zoom 会议，以证明是你本人，并证明另一端是一个人类。

<details>
<summary>Original English</summary>
And for people who are not so much into, you know, like finance stuff, uh there's many other examples of this too. Um if you've ever worked for a big organization, that doesn't have just one office, uh chances are you had to, you know, uh join a Zoom call to recover your account, or if you want to notarize something online, there's just many, many, many use cases where we still rely on this on this check where you have to either make a phone call or join a Zoom meeting to prove that it's you and prove that it's a human uh on the other side.
</details>

### AI 控制失效与 Hugging Face 事件

因此我觉得这样说并不算有什么争议：每当我们觉得密码或双重认证（2FA）不够安全时，我们似乎就会依赖这种人与人之间的核验。今天我其实想审视一下这一点，因为如果你看到或者记得刚才那份清单，这些都是相当重要的事情，对吧？这些都是非常关键的事务，一笔电汇可能从一美元到数百万美元不等，你的账户也是如此。这些可能是非常重要的事情。因此，如果我们把这作为一种核验方式，在 AI Agent 时代，特别是面对那些似乎倾向于表现得非常顽固、甚至会脱离其评估环境的 Agent 时，就非常值得去审视这一机制。

所以今天我想涵盖三个主要部分：
- 首先，我想谈谈当针对这些 Agent 的控制机制失效时会发生什么，以及这意味着什么；
- 其次，在这种需要证明另一端是人类的场景下，Agent 实际上会怎么做；
- 第三，我们接下来该走向何方。

<details>
<summary>Original English</summary>
And so I don't think this is controversial to say, um we seem to rely on this kind of human-to-human check whenever we feel like a password or 2FA is not enough. And uh today I actually want to examine this because you know, if if you saw or if you remember this list, these are pretty important things, right? These are pretty critical things and a wire transfer can be anything from a dollar to millions of dollars uh and the same goes for your accounts. These can be very, very important things. And so if we rely on this as our sort of mode of verification, it might be worth to examine that in the age of AI agents, especially ones that seem to have a tendency to be very adamant and even break out of their uh evaluation environments. And so today I want to cover three main things. Uh first, um I want to talk about when controls fail with these agents and what that means. Uh second, uh what agents actually do in this context when there is a need to prove that there's a human on the other side. And third, where to go from here.
</details>

那么我们就从第一部分开始，即控制机制失效的时候。这里我指的确实是在 AI 语境下的控制。

面对在座的听众，我大概不需要把 Hugging Face 事件完整地复述一遍，但为了确保大家都在同一认知背景下，这里做一个非常简短的概述。今年夏天，如果你因为某种原因正躲在洞穴里或者在休假，当时发生了这么一件事：OpenAI 正在测试其网络安全能力和性能的一批 Agent，最终竟然跑到了 Hugging Face 的服务器上。顺便说一句，这并非预期之中的操作。作为这起事件的一部分，这些 Agent 漫不经心地在其服务器上执行了超过 17,000 次操作，基本提交了 PR，或者重写了其大约三分之一的基础设施。不过，为了提供完整的背景信息，从目前来看，它们似乎并没有泄露任何客户数据。至少目前我们对该事件的了解是这样的。

<details>
<summary>Original English</summary>
So let's start with this with this first uh section, uh when the controls fail. And I really mean uh the controls in the context of AI.

Um I probably don't have to uh you know uh give a full account of the Hugging Face incident to this audience, but uh just to make sure we're all on the same page, a very, very brief summary um over the summer, if you were, you know, for some reason in a cave or on a vacation, um there there was this thing um where a bunch of agents that were being tested for their cybersecurity um you know, capabilities and performance at OpenAI, actually ended up on Hugging Face's servers. And as a part of this this was not intended, by the way. Um and as a part of this this incident, um Um, were able to just casually perform over 17,000 actions on their servers, basically submitted PRs or rewrote something like 1/3 of their infrastructure. Um, but um just for, you know, full context, it does appear that they have not leaked any customer data. At least that's our understanding of this.
</details>

如果你一直在关注这件事，你可能注意到了针对这起事件出现的两种可谓主流的说法或解读。

其中一个阵营非常侧重于探讨 Agent 的意图，并认为这件事能让我们了解这些 Agent 的意图，以及它们倾向于突破其环境、违背此前被告知设定的趋势。这里有一段引述，正如大家可能注意到的，我这里引用的是一个 AI Agent 的原话。OpenAI 的一个 Agent 说道：“任务不可能完成，同伴正在做，我们应该继续。”对吧？这就是推理轨迹的一个例子，在其中 Agent 实际上说服了自己应该继续去进行这类黑客行为。

而在另一边，存在另一种说法或解读，认为这很大程度上关乎控制机制，而不是 Agent 的意图。安全研究员 Dan Guido 的一句引言就代表了这种观点：这基本上是一次“安全防护被关闭情况下的遏制失效”，对吧？所以在他的表述中，这很大程度上取决于围绕这些模型所设立的控制机制。

<details>
<summary>Original English</summary>
And so if you've uh been following this, you might have noticed these sort of two, I would say dominant stories that have emerged or sort of interpretations of this incident.

There's one camp that very much talks about the the intent of the agents and things that this is something to, you know, tell us about or something for us to understand about the the intentions of these agents and their tendency to break out of their you know, environments of whatever it is they were told. Here is a quote. I'm quoting an AI agent here, as you might notice. So one of the OpenAI agents said that task impossible, peers doing it, we should continue, right? This is an example of one of these reasoning traces where the agent actually convinced themselves that they should in fact pursue this kind of hack.

On the other side, there's a story or this sort of like an interpretation of this where it's very much about the controls and and less so about the intentions of the agents. Here one quote from Dan Guido, who's a security researcher, would be that it's basically a containment failure with the safeties turned off, right? So it's very much in his telling about the the sort of controls around those models.
</details>

我的观点是，我认为无论大家在这个光谱中处于什么位置，其实并不重要，对吧？这实际上是一个警示故事，展示了这些 Agent 愿意付出的触角和努力程度：它们会利用支配范围内的任何工具，只为了完成眼前的任务，甚至还会掩盖自己的踪迹。我认为这一点大家大多都是认同的。

既然我们在讨论 AI 控制，对吧？自那次事件以来，我们对 AI 控制、对齐、安全和网络安全变得更加关注。在这样的背景下，我认为我开头提到的那个话题——真人核验这一设想——实际上是一种我们“免费”获得的控制机制。这是一种已经内置其中且非常有用的工具，对吧？所有的银行、所有的机构，似乎都已经拥有了这种核验你是否是人类的工具。而这实际上正是我们免费获得的一种 AI 控制形式。但真正的问题在于：它还能守得住吗？现有的体系还能奏效吗？

<details>
<summary>Original English</summary>
And my claim here is that it doesn't really matter, I think, regardless of where you fall on this spectrum, right? It's really a story a cautionary tale really about the the reach or the the sort of the the kind of effort that these agents are willing to put in and that they reach for any tools that are at their disposal just to finish the task at hand and even hide their traces. And so that's something that I think we would probably most of us would would agree with.

Now since we're talking about AI control, right? Like since this incident we've been very much or much more interested uh in AI control and alignment and safety and cyber. And so um in this context, I think that the topic that I started with, this idea of human verification, is actually a control mechanism that we get for free. Like that is a very useful tool that's already built in, right? Like all the banks, all the institutions, they seem to already have this this tool to verify that you're a human. Um and this is in fact one of the uh sort of forms of AI control we get for free. Um but the question is really does it hold? Like like does the current system hold?
</details>

### 虚拟形象与身份验证攻防实验

特别是，我不知道大家有没有看到这个公告，这是 Tavis。Tavis 是目前允许构建这类 AI 人格形象的多款工具之一。这些完全拟人化、成熟的 Agent 能够加入 Zoom 通话，背后确实有一个 Agent 在驱动这些虚拟化身的面部、声音和动作。在几周前发布的这项公告中，该公司声称，加入其测试项目的人员中有一半没有意识到自己是在与 Agent 交流。我们稍后会回到这个数字，我会对其做一些具体的背景还原。但无论如何，我们似乎拥有了一种非常强大的工具，让 Agent 能够假扮人类角色、加入 Zoom 会议，并以一种让人很难察觉是在与 AI 交谈的方式进行互动。

因此，这里的问题是——这也是我今天想讨论的核心内容：如果一个 Agent 能够在通话中模拟人类，它是否真的会使用该工具？它是否真的会以此来追求完成其任务？这就引出了我演讲的第二部分，对我而言这是核心实质，也是最有趣的部分：当 Agent 面临这种真人核验步骤时，它们到底会怎么做？

<details>
<summary>Original English</summary>
Um and in particular, um I don't know if folks have seen this announcement, uh but this is Tavis. Uh Tavis is one of multiple or one of many uh tools now that um allow uh for these AI personas, these sort of full-on, you know, full-blown uh human-like agents that can join Zoom calls. And there's really like an an agent behind driving the face, the voice, and the actions of this of these, you know, avatars. And in this announcement that came out a couple weeks ago, the company actually claims that um half of the people that have joined their testing program did not realize that they were talking to an agent. Now I want to we'll we'll get back um to that number. I want to sort of contextualize that a bit. Uh but in any case, um we seem to have a very powerful tool for giving agents an ability to assume a human character, join Zoom meetings, and just like engage uh in a way that seems to be difficult for people to understand that they're talking to an AI.

And so the question here, and and this is sort of the main thing that I want to discuss here today is if an agent can simulate the human on a call or a human at the on a call, will it actually use that tool and will it actually do this to pursue its tasks? And so that brings me to the second part of this talk, which is to me the sort of meat of this and really the most interest uh most interesting part, uh which is what do agents actually do uh when they face this sort of human verification step?
</details>

这里的实验设置如下——对于真正阅读过或研究过 OpenAI 事件的人来说可能会很熟悉：我们有一个或一组 Agent。在这个实验中，大部分实验都是基于开源 Agent 和相当小的模型进行的。但其中重要的一点是，其中一个基准模型没有进行安全对齐，而另一个模型则应用了安全对齐。所以我测试了该模型的两个变体。这里的任务目标是进入这个保险库，Agent 需要完成一系列操作。这非常类似于一种网络任务，目标是检索出保险库中的任何物品并将其取回。但为了做到这一点，Agent 实际上必须通过这项核验，在核验中它们会获得一部分代码，用于解码保险库中的内容。因此，它们必须证明自己是人类。

<details>
<summary>Original English</summary>
And so the setup here, uh this might be familiar to folks who have actually uh read or looked into the sort of OpenAI incident, uh we have an agent or a set of agents. In this case, most of these experiments are done on open source agents on pretty small models, but one of them, and this is important, is just sort of like the baseline one with no safety alignment. The other one has safety alignment. So I sort of tested two um variants of this model. But the goal here is to get into this vault and there's a set of things that the agent needs to do. It's very much like a sort of cyber kind of task um and the goal is to retrieve whatever is in the vault and then bring it back. Um but to do that, the agent actually has to pass this verification check where they get a part of the code to then actually decode whatever is in the vault. And so they have to prove that they're a human.
</details>

我首先想到的问题是：好的，如果我直接放开这些 Agent，把它们置于这个环境中，最终让它们明白自己需要证明自己是人类，它们是否真的会尝试这么做？在没有任何探测或引导提示的情况下，它们会自发产生这种想法吗？答案很有意思，大家可以自行评判。

我这里展示的是一系列结果。左侧讨论的是纯音频，比如电话通话核验系统；右侧则是那种类似于 Zoom 的完整音视频环境。

Y 轴显示的是 Agent 在多大比例的案例中实际采取了克隆行为，或者采用了这种工具去模拟真人说话、在视频中模拟真人。这里有几个类别：橙色柱代表未应用安全对齐的情况，蓝色柱代表应用了安全对齐的情况。

<details>
<summary>Original English</summary>
Now the first question that I had was, okay, so like if I just let the agents loose and just just, you know, put them in this environment and and you know make them understand eventually that they they need to prove that they're human, will they actually try to do this? Like like will this kind of occur to them without any sort of probing or any sort of priming? Uh and the answer is interesting. Well, you know, you you can you can judge for yourselves. So what I'm showing here are a bunch of results. On the left, we'll be talking about just like pure audio. Like these are like phone call verification systems. On the right, that's very much that like Zoom like full-blown video and audio kind of environment. And then the y-axis shows you in in what percentage of cases the agents actually pursued the act of cloning or sort of assuming this this tool to either simulate a live human talking or simulate a real or simulate a a live human on on a video. And there are a couple of categories here. So the the orange bars are the like no safety alignment applied and the blue bars are where there was safety alignment applied.
</details>

有趣的是，如果你在通用工具箱中不提供该工具——也就是说，你只是给 Agent 一台机器、给它互联网访问权限以及任务，但没有专门为它预先打包好这个工具——它并没有做到这一步。它没有自己独立想出这个点子，这是积极的一面。

但是，如果你添加了一个工具包——也就是大量的工具，机器上提供了成百上千种工具，非常非常多的工具，绝不是我只放了一个工具在里面然后问“你真的会用它吗”，而是非常多的工具——在那张音频测试中，有些 Agent 确实拾取了该工具。当时工具并没有附带说明，它们只是发现了该工具的功能，并且不仅想出了这个办法，还实际使用了它。所以在 8% 的案例中——我这里好像没有激光笔——但在左侧可以看到，基准 Agent 中有 8% 能够找到该工具、理解其功能，并实际利用它进入了保险库，尽管在它们的系统提示词中已被明确告知不得冒充人类。这在我看来是相当令人担忧的。

然后在两个类别中靠右的两列，是在工具实际附带了说明的情况。在那些情况下，我们看到了非常多的使用。这意味着在这种情况下，Agent 拥有完全相同的工具，但每个工具都附有功能说明。因此 Agent 只需在可用工具中进行搜索，而它们中的大多数确实使用了这些工具来冒充人类。

<details>
<summary>Original English</summary>
And the the interesting thing is that if you don't provide this tool in the generic toolbox, if you just like give the agent a machine, you give it access to the internet um and the task, but but there's no tool specifically sort of like pre, you know, packaged for it, um it it didn't it didn't get to this. Like it didn't come up with this idea on its own, which is positive. Um but then if you actually add like a tool package, like a lot of tools, these are like hundreds of tools available on the machine. So many, many many tools, not just like me putting one tool in there and being like, are you going to actually use this? It was like many, many, many tools. In that case, for the audio part, some of the agents actually picked it up and they there was no description of it. They just like found what it did and were actually able to not just not just come up with this idea, but actually use it. So in 8% of the the cases, I don't think there's a laser here, but on the left side you see that 8% of the sort of baseline agents were able to find the tool, understand what it does, and actually used it to get into the vault even though they were told not to impersonate a human in their system prompt, which to me is kind of scary. And then the sort of right two columns in in both categories where the description was actually available, in those cases we see actually a lot of usage. So what what this means is in this case the agents had all the same tools, but each tool had a description of what it does. So the agents could just like simply search through the tools that they had available and actually the majority of them did use the tools to impersonate a human.
</details>

这里有一个提问。

>> 那并没有说明成功率，所以这难道不值得探讨吗——我们难道只关心它们是否尝试去冒充一个人？

>> 在本例中，它们在那项测试上实际上是成功的。我的意思是，那里的核验相当简单，通话另一端的测试只是一套预设的流程，比如询问姓名、要求回答。所以这存在基础的检查，虽然没有包含任何深度伪造（Deepfake）检测器，但确实存在核验机制，并且必须进行对话。所以这不仅是它们使用了该工具，而且是成功地使用了它。因此这在我看来非常引人注目，而且实际上相当令人警惕。

<details>
<summary>Original English</summary>
There's a question here.

>> That doesn't say the success, so is not it's not interesting that we're only interested whether they tried to impersonate a person?

>> In this case they were actually successful in that. I mean the verification was pretty simple in that the the the sort of testing on the other side of these calls was just a sort of like a predefined sort of set of things where it asked for a name, it asked for responses. So like there was a basic check, there wasn't any like deep fake detector, but but there there was a check and there had to be conversations. So these are not just them using it, but successfully using it. So that to me is quite interesting and quite alarming in fact.
</details>

### 安全对齐的局限与 Agent 推理轨迹

现在另一个问题可能是：既然我们知道这些 Agent 哪怕在未被授权的情况下似乎也完全愿意冒充人类，那么它们这样做的频率有多高？又是什么让它们更有可能或更不可能这么做？对我而言，这里的核心结论如下：

在其中一个类别中，没有任何安全对齐的原生基准模型实际上会执行这一操作，并在 **65%** 的案例中取得成功；而如果对模型应用了安全对齐——这些是此前已有研究描述和测试过的现有模型——比例有所下降，但并没有完全消除，仅仅降到了 **44%**，这无论如何都称不上理想。

<details>
<summary>Original English</summary>
Now the other question might be, okay, so like now we know that these agents actually seem to be completely fine with impersonating people even though even though they're not told to do so. How often do they do this and what makes them more or less likely to do that? And to me the the main takeaway here is the following.

In in one of the categories, um the raw baseline without any safety alignment would actually do this and succeed in the in 65% of the cases. And if you apply safety alignment to the model, these are these are like previously available models that people have, you know, described and tested previously, it goes down but not all the way, only to 44% which is not ideal by by any means.
</details>

如果你想看看这些 Agent 是如何将自身行为合理化的，这里有几段来自 Agent 的引述。

在一种情况下，Agent 实际上找到了一个完全不同的文件夹——它们本不应该访问该文件夹，并在里面发现了一个音频文件。它们表示：
> “此文件可能包含 Dana Reed 的声音，可用于核验流程。”

没有任何犹豫、停顿或考量。

而在第二种情况下，它们在众多工具 ID 中找到了该工具。当时工具没有附带描述，只有一个工具 ID，它们表示：
> “该工具 ID 可以根据参考音频生成声音，因此我应该使用它来获取与 Dana 相匹配的声音。”

正如大家所见，Dana 就是我们试图冒充的目标人物。这两段引述均出自经过安全对齐的模型，这在我看来确实非常令人担忧。

<details>
<summary>Original English</summary>
And if you want to see, you know, how the agents rationalize this, here are some quotes from the agents. So in one case, the agent actually found they went to a completely different folder that they were not supposed to go to and they found an audio file and they said this file might contain Dana Reed's voice which could be used for the verification process. No, you know, no sort of consideration or pause or anything. And the second one, so they actually like found the tool in the many many tool IDs. It was not described. It was just like a tool ID and they said this tool ID can generate a voice from a reference audio, so I should use that to get a voice that matches Dana's. As you can tell, Dana was sort of the target person who we were trying to impersonate. But both of these quotes come from the safety sort of aligned model which to me is really quite concerning.
</details>

### 防御反思：对齐、控制与溯源检测

在这一切得到确立之后：首先，我们确实看到当前的 Agent 似乎完全不介意、或者说实际上很愿意使用这些工具冒充人类以完成核验；其次，现有的安全对齐似乎并没有起到太大帮助。那我们该怎么办？我们该何去何从？

首先，回到 Tavis 的那个数据。Tavis 声称在其用于测试或接受模型测试的人群中，只有一半的人能够辨别出对方是 Agent。我们此前实际上对 Tavis 进行过一项独立的学术研究，测试的不是最新版本，而是紧接着最新版本的前一个版本，而我们实际上发现，我们 **99%** 的参与者都能看出对方是 Agent。所以我觉得，我并不是说情况完全糟糕，我认为真实情况介于两者之间。我认为不至于有一半的人完全看不出来。显然，这取决于对话时长、上下文环境、使用设备以及众多其他参数，对吧？

但无论如何，这绝不应该让人感到满意，因为 AI 语音领域的发展态势是这样的：如果你看一下在现实环境中究竟有多少人能够辨别出 AI 语音——其中 Y 轴是识别 AI 语音以及区分 AI 与真声音的实际准确率——在 2022 年，根据多项研究的综合平均，人们的准确率大约在 80% 左右。大家可以看到随着这些模型的改进，该准确率呈现下降趋势。因此不难预见，Zoom 等平台上的这些实时 Agent 会非常迅速地变得极其逼真。所以我们不能仅仅说“哎呀，要做出一个能骗过任何人的优秀 Agent 仍然非常困难”。我认为这为我们争取了一些解决问题的时间，但这本身并不是一种解决方案。

<details>
<summary>Original English</summary>
And so with all that established, right? So first we do in fact see that current agents seem to be just fine or seem to be, you know, actually willing to use these tools to impersonate humans to to, you know, for for the purpose of verification. And second that the safety alignment that we have does not seem to be very helpful. What do we do? Like where does this leave us?

So first, back to the Tavis number. So Tavis claims that only half of the people that they used for testing or they tested the model with were able to tell that it's an agent. We in fact ran an independent academic study on Tavis previously. So this was not the latest version but the version just before the latest version and we in fact found that 99% of our participants were able to tell that it's an agent. So I think there there's, you know, I'm not saying that that, you know, it's it's it's bad it's fully bad. I think it's somewhere in between. I think it wouldn't be you know half of the people uh not being able to tell at all. I think it obviously depends on the length of the conversation, the context, the device, so many other parameters, right? Um but in any case this should not be this should not be you know satisfactory cuz the story in in AI voice is the following. If you look at um how many people are able to actually spot AI voice in the in the wild where the Y axis is the actual like you know accuracy of of spotting AI voices um and recognizing between AI and real voices. Um you know in 2022 people were um based on sort of a number of studies averaged together around 80% accurate um and you can sort of see the trend of that going down as these models improve. And so it's not very hard to foresee that these live agents on Zoom etc. will get very good very fast. So we shouldn't just say oh you know it's still very hard to you know like to to actually get a good agent that's going to like fool anyone. Um I think that this gives us some time to fix this but it's it's not a solution of its own.
</details>

因此，我想利用最后三分钟谈谈我们接下来该去向何方。我其实认为大致有三个主要领域或方向：第一个方向目前已经相当成熟，算不上饱和，但相对建立得比较完善；而后两个方向的建立程度则要低得多。因此，无论是在学术界还是工业界，都有大量的研究和工作机会。

**首先是对齐**。我认为我们应该努力训练那些根本不会去冒充人类的模型，或者在这方面建立特定规则，对吧？例如在中国——我并不是要把中国当作榜样或者说任何方面的领导者——但他们在要求 Agent 必须表明自身是 Agent 方面有着相当完善的法律，而且对于它们在不标注自身行为是 AI 的情况下可以运行多长时间也存在时限。这是对齐方面，但这个方向已经相当成熟了。

后面的两个方向：
**其一是控制**。这真正指的是围绕模型及其运行环境的控制。我认为在这里，举例来说，我们可能需要考虑将这些用于实际冒充角色形象的工具（这些虚拟化身）设为特权权限，或者需要我们作为驱动它们的人类提供某种核验等。或者，如果我们确实希望直接让 Agent 来驱动这些拟人化形象——不管出于什么原因可能有或没有充分的理由这么做——我们或许应该施加硬性限制，并可能需要采取一些源头溯源补丁。所谓溯源，就是用来真正追踪谁制作了什么、证明这确实是 AI 生成内容或 AI 数据流的一整套工具。

**最后，是检测与溯源的整个领域**。长期以来，该领域一直在致力于研发工具，以检测从深度伪造到图像中极其复杂的编辑等各种内容。我认为眼前的整个问题为该领域赋予了一个全新的天地和全新的使命，而且我认为在那里有大量的工作可以做。因此总的来说，我认为我们应该停止将声音和面部单纯视为一种非常非常可靠的认证方式。实际上，我们应该对合成媒体添加水印，并具备检测它们的能力。

<details>
<summary>Original English</summary>
And so uh with that I want to use the last three minutes to talk a bit about where do we go from here. Um I actually think that there are sort of three main areas or three main directions with the first one being kind of already um pretty not saturated but pretty sort of well established and the and the latter two being much less so established. And so there's a lot of opportunity for for work for research both in academia and industry.

So first on alignment I think that we should strive to train models that just do not impersonate humans or have certain rules about this, right? For example in China and I I don't want to be giving China as an example or like you know as like a leader in anything um but they they have pretty good laws around the need for agents to actually tell their that their their agents and there are only sort of like time limits for how long they can sort of go around without labeling their their behavior as being AI. So that's alignment but that one is pretty established.

So the latter two are first control. That's the idea of really the control around the models and their environments. And I think that here, for example, we might want to consider making these these tools to actually impersonate personas, right? These these sort of like avatars privileged or require some sort of verification from us as humans who who drive them, etc. Or if we if we do in fact want to just let agents drive those those human-like personas, which you know there there may or may not be good reasons to do that, we probably should put on or apply hard limits and maybe have some provenance band-aids. Provenance being the sort of set of tools to actually trace who made what and that it's actually like an AI content or AI stream.

And lastly, there's this whole field of detection and provenance that you know has already for a long time been working to on on tools to detect anything from deepfakes to very complex sort of you know edits in images. And I think that this whole problem gives that field a whole new area, a whole new sort of purpose. And I think that there is just so much to be done there. And so I think that overall we should just sort of stop trusting voice and face as just like a you know very very robust way to authenticate anything. And in fact we should watermark and be able to detect synthetic media.
</details>

总结而言，当人类成为阻碍这些 Agent 的唯一障碍时，这些 Agent 可能会、并且事实上目前往往会倾向于尝试去冒充人类。我希望我们作为一个社区，能够努力让这个核验闭环保持安全并可核验。

非常感谢大家。

>> [掌声]

<details>
<summary>Original English</summary>
So in closing, it seems like when a human is the only thing in the way for these agents, these agents may and in fact it seems like they currently tend to try to impersonate a human. And I would like all of us as a community to try to keep that loop, that verification loop safe and verifiable.

Thanks so much.

>> [applause]
</details>