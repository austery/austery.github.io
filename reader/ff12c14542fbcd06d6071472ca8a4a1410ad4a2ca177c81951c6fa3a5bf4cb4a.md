---
author: Latent Space
date: '2026-06-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-rIAVuaRjOg
speaker: Latent Space
tags:
  - coding-agent
  - open-source
  - developer-tool
title: Amadou Wace 谈 Command Code 演进历程、Taste 机制与开源计划
summary: Amadou Wace 在访谈中回顾了从早期 CLI 与 LangBase 转向编程智能体 Command Code 的历程，介绍了基于元神经符号记录用户偏好的 Taste 机制、大模型在设计与色彩空间中的应用，并表示计划近期开源 Command Code。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Amadou Wace
companies_orgs:
  - Netlify
  - RapidAPI
  - Google
  - Airbnb
  - DeepSeek
products_models:
  - Command Code
  - LangBase
  - Corona CLI
  - GPT-3
  - GitHub Copilot
  - Taste One
  - Open Code
media_books: []
status: evergreen
---
<!-- chunk 1/5 -->

好的，我们现在在远程演播室，和 Amadou Wace 在一起。你好吗？

<details><summary>Original English</summary>
Okay, we are here in the remote studio with Amadou Wace. How are you?
</details>

>> 我挺好的。非常感谢你能邀请我。

<details><summary>Original English</summary>
>> I'm doing great. Thanks a lot for having me.
</details>

>> 是的，你和我早在 AI 出现之前就认识了。我们以前在 WordPress 社区都很活跃。除此之外，我都不记得最初是怎么知道你的了。大概就是一般的网络相关的事情吧。

<details><summary>Original English</summary>
>> Yeah, you and I have known each other since before AI. You were I were active in the WordPress community. I don't know how I first came across you beyond that. I think just general web stuff.
</details>

>> 可能是 DevRel（开发者关系），可能是 DevRel。我觉得是在你加入 Netlify 之前。

<details><summary>Original English</summary>
>> Maybe DevRel, maybe DevRel. I think you before you had joined Netlify.
</details>

>> 是的，但是你……你以前做过全职的 DevRel 吗？

<details><summary>Original English</summary>
>> Yeah, but you I Were you ever a professional DevRel?
</details>

>> 算是吧，我想我曾经领导过，比如我在 RapidAPI 当过一阵子 DevRel 副总裁。

<details><summary>Original English</summary>
>> Yeah, I think I used to lead like I was VP of DevRel at RapidAPI for a while.
</details>

>> 噢，对对对。是的，是的，是的。

<details><summary>Original English</summary>
>> Oh, that's right. That's right. Yes, yes, yes, yes.
</details>

>> 那可以说是最正规的 DevRel 了，对吧？

<details><summary>Original English</summary>
>> That is as professional as one gets, right?
</details>

>> 不，不，不，因为我一直觉得你像个独立创作者那一类的人。

<details><summary>Original English</summary>
>> No, no, no, cuz I always see you as like an independent creator type person.
</details>

>> 不，我……我在不少不同的地方工作过，跟 Google、跟 Airbnb。大体上，大体上我一直都是做开源的那种人，我发布了大概 300 多个开源代码仓库。

<details><summary>Original English</summary>
>> No, I like I worked at a bunch of different places with Google, with Airbnb. Mostly Mostly been like this open source guy where I have like published like 300 plus open source repositories.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 在那之后一切就都是表面形式了，你知道，我的开源工作带我去了很多地方，而且你知道，像你一样，我也创作很多内容，所以就成了 DevRel。

<details><summary>Original English</summary>
>> Everything is semantics after that, you know, my open source work took me places and you know, like you know, like you I create a lot of content, so DevRel.
</details>

### 从 Corona CLI、LangBase 到 Command Code

>> 是的，好的，那给我们讲讲通往 command code 的历程吧，然后我们还会重点介绍一下你最近做的一些工作。

<details><summary>Original English</summary>
>> Yeah, okay, so tell us about the path into command code and then you know, we're going to highlight some of the work you did recently.
</details>

>> 我觉得这个故事差不多是从 COVID 期间开始的，你知道，我基本上是做了一个 Corona CLI 的东西，后来火了。当时正值 COVID 高峰期。我经常出差，因为做 DevRel 之类的，然后我想是 Greg Brockman 和 Sam Altman 最终提前给了我 GPT-3 的访问权限。所以从那时起我就是一名 AI 工程师了，对吧？我做的第一件事，事实上我刚才还在看记录，那是 2020 年 7 月。Greg 给我发了条消息问：应用场景是什么？你打算用这个 API 做什么？我告诉他，我打算用来建议下一行代码，就像代码片段一样，对吧？这比 GitHub Copilot 出现早了一年零三个……一年多时间，对吧？

<details><summary>Original English</summary>
>> I think the story kind of starts at COVID, you know, I basically did a Corona CLI thing that went viral. So COVID was at its peak. I was traveling a lot being in DevRel and whatnot and I think Greg Brockman and Sam Altman ended up giving me access to GPT-3 early. So since then I've been an AI engineer, right? And the first thing I did, in fact, I was just looking at it. It was July 2020. And Greg sent me a message like what is the use case? What What are you going to use this API for? And I told him I'm going to suggest the next line of code like a code snippet, right? This is year and three more than a year before GitHub Copilot was a thing, right?
</details>

>> 嗯嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 于是我开始做这个叫 CLAI 的东西。我一直非常热衷于构建 CLI，所以你知道，就有了那个好玩的小副业项目 Cly，对吧？然后呃，我觉得那最终演变成了现在的 command code。我们简短的历程是，我们后来建了一个 AI 云。现在什么都是 AI 云了。它当时叫 LangBase。呃它发展得相当大，呃每月有 12 亿次智能体运行。后来还建了内存基础设施等等。现在我们有点像是转型到了这种认知中：世界上只有一种智能体，那就是编程智能体（coding agent）。它无所不能，对吧？那么，为什么要把这种能力隐藏在某些内存系统或某些基元之类的东西后面呢？在那个呃有 6 年历史的代码库中，它最终变成了我们称之为 command code 的东西，对吧？而 command code 实际上始于这样一种感觉：我个人使用 command code 的频率比使用其他编程智能体要高得多。然后几名团队成员也开始采用它。我们接着开始构建这个元神经符号模型，名字叫，你知道，

<details><summary>Original English</summary>
>> So I started building this thing called CLAI. I've always been a big fan of building CLI, so you know, silly side project Cly, right? And uh I think that has eventually became command code now. Like, you know, our short history is we ended up building an AI cloud. Now, everything is an AI cloud. It was called LangBase. Uh it grew quite big. Uh 1.2 billion agent runs a month. Ended up building an a memory infrastructure or whatnot. And now we've sort of like pivoted into this feeling that there is only one type of agent, and that is a coding agent. It can do it all, right? So, why hide that capability behind some memory system or some primitive or whatnot? In that uh 6-year-old old code base has eventually turned into this thing we call command code, right? And command code actually started with this feeling that I was using command code a lot more than other coding agents personally. And then a couple of team members started adopting it. And we started ending up building this meta-neuro-symbolic model called, you know,
</details>

>> [清喉咙]

<details><summary>Original English</summary>
>> [clears throat]
</details>

>> Taste One。它所做的事情是，像我对代码有很多经验。我想我已经写了差不多 27 年代码之类的，对吧？在发布了 300 多个开源项目之后，你就会对很多事情有自己的见解。而且我通常发现自己做的都是极其前沿的东西，所以根本没有 AI 智能体可以去阅读的文档之类的，对吧？所以在那个时候我觉得，你知道，我的见解比 LLM 实际能找到的东西或者你用 RAG 之类的能做到的东西更重要。所以，我最终把这种行为编码进了元神经符号呃神经符号架构中：如果你从我这里学到了什么，就为我记录下来，就像一项技能一样，对吧？我们开始把它称作 Taste（品味），对吧？比如你看到我非常偏好 pnpm，但是发布或本地链接 CLI 时却用 npm global link，对吧？它们就会学到，我在安装包和几乎所有其他事情上都偏好 pnpm，但当我在本地链接我的 CLI 时，我用的是 npm。所以，这些类型的事情和学习心得，

<details><summary>Original English</summary>
>> Taste One. The thing it does is like I have a lot of experience with code. Like, I've been I think writing code for 27 years or something, right? After publishing 300 plus open source projects, you get to have a lot of opinions on things. And I mostly find myself working on things that are super cutting edge, so there are no docs that an AI agent can go read or whatnot, right? So, at that time I feel like, you know, my opinions matter more than what an LLM can actually find or what you can do with rag or whatever. So, I ended up encoding this behavior uh in meta-neuro-symbolics uh neuro-symbolic architecture where if you learn something from me, document it for me like a skill, right? And we started calling it Taste, right? If you see me prefer pnpm a lot, but publish or link my local CLI with npm global link, right? They'd learn that I prefer pnpm for installing packages in almost every other thing, but when I'm linking my CLI locally, I'm using npm. So, these type of things and learnings
</details>

>> 以及[嗤笑声]最终演变成了 taste 文件，它们跟技能文件非常相似。你可以把它理解为 command code 会基于每个代码仓库自动向你学习。也就是你的团队，对吧？它会构建一个技能库，这个库相当精简，对吧？它们不像，你知道，并不是把所有东西都塞在里面。它记录的是它在你的工作中发现的重复偏好和模式，对吧？而且它可能来自许多不同的编程智能体之类的。当我们在……当你合并代码到 main 分支时，那就是我们可以触发分析你整体上的接受、编辑和拒绝内容的时机。

<details><summary>Original English</summary>
and [snorts] that eventually ended up becoming taste files, which are very similar to skill files. You can think of it like command code automatically learns from you on a per repository basis. So, your team, right? And it builds a library of skills, which is quite less verbose, right? They're not like, you know, everything is not in there. It's like things that it sees as like repeated preferences and patterns across your work, right? And it could be coming from so many different coding agents or whatnot. When we When you merge something into main, that is when we can trigger what were your accepts, edits, and rejects overall.
</details>

### 开源模型与工具调用困境

>> 但这不是我们今天在这里要谈的。你知道科技界任何事情都有个好笑的现象：你以为会走红或者会被采纳的东西从来都不会火。而你基本上只是，你知道，随口忽略掉、觉得“谁在乎开源模型？”的东西，反而成了大事，对吧？今天是 5 月 25 日。就在大概整整 25 天前，大家都在谈论 DeepSeek 有多好。也有很多人在说 DeepSeek 有多差，以及为什么大家都在说它那么好。所以我当时处于这样一种阵营：我……我需要做出决定，看 DeepSeek V4 Pro 是否真的和 Opus 一样好，对吧？

<details><summary>Original English</summary>
But, that's not what we are here to talk about. You know how the silly thing about anything in tech is the thing that you think will go viral or will get adopted never does. And the thing you basically just, you know, off the cuff ignore like, "Who cares about open models?" It becomes a thing, right? So, it is 25th of May today. And about literally 25 days ago everybody was talking about how DeepSeek is so good. And there were a lot of people talking about how DeepSeek is so bad and why are people saying that it is so good. So, I was in the in the camp of I I need to make a decision on if DeepSeek V4 Pro is actually as good as Opus, right?
</details>

>> 当时我们每天处理大约几十亿个 token 左右。现在我们的量比那时多了差不多 100 倍。我最终发现了这个我称之为工具混淆（tool confusion）的现象，非常奇怪。我们已经能够搞清楚如何确定性地为开源模型或开放模型修复工具调用（tool calling）问题。这是一件非常了不起的事情，很多人一直在通过 command code 尝试它。我也把其中的很多内容完全开源了。你可以……你可以直接把它实现到任何编程测试框架中。因为，你知道，以我的性格，觉得这并没有那么重要，对吧？所以，是的，告诉我你想让我把这个话题讲多深。我非常兴奋想聊聊这个。

<details><summary>Original English</summary>
And we are doing anywhere from like, you know, a couple billion tokens a day at that time. We are like 100 times more than that now. I ended up discovering this thing that I call tool confusion, which is very odd. We have been able to figure out how to deterministically fix tool calling for open source models or open models. It's been such an amazing thing that a lot of people have been trying it out through a command code. And I also made a bunch of that like completely open. You can You can go and implement this in any coding hardness. Because, you know, me being me, this is not that important, right? So, yeah, let me know how how deep you want me to go into that topic. I'm very excited to talk about it.
</details>

>> 好啊，我觉得我们可以直接切入正题。我想你有一篇很火的帖子想分享。还有，我觉得给那些可能只习惯使用 OpenAI 的人界定一下这个问题，对吧？他们做……他们不知道什么是工具调用问题。

<details><summary>Original English</summary>
>> Yeah, I think we can get dive right into it. I think you have a viral post that you want to share. And also, I think frame the problem for people who maybe are only used to open AI, right? They did they don't know what a tool calling problem is.
</details>

>> 可以这样理解：从我们的整个理念来看，就是 command code，对吧？你应该能够指挥（command）你的 LLM 去做任何你想让它们做的事情，对吧？那正是……那就是我们要追求的方向，对吧？第一件事是构建 taste，这样我们就能引导模型朝正确的方向走。然后下一个最好的事情发生了，你知道，程序员不再写代码了。那么，我们该从谁身上学习 taste 呢，对吧？于是，我们开始从模型那里学习 taste，因为模型正在写代码。如果你在 Claude、在 GPT、在 DeepSeek 上消耗十亿个 token，你会发现跨不同全栈系统的整个技术栈中存在很多差异，比如 DeepSeek 出于某种原因不太擅长 Go 语言代码。所有这些，我开始称它们为变体（variations）。

<details><summary>Original English</summary>
>> Think of it like this from our whole vibe is command code, right? You should be able to command your LLMs to do whatever you want them to do, right? That is that is the way we are going for, right? First thing was to build taste so we can steer models in the right direction. And then the next best thing happened, you know, programmers stopped writing code. So, who are we going to learn taste from, right? So, we started learning taste from models because models are writing code. If you spend a billion tokens on Claude, on GPT, on DeepSeek, you discover a lot of discrepancies across the stack in different full stack systems like DeepSeek is not that good at Go code for some reason. And all of those, I started calling them variations.
</details>

>> 我们在这些变体中发现了一种确定性的模式。因此，当你在运行一个编程智能体时，工具调用在非常基础的事情上就像是，你知道，如果你正尝试运行一个 bash 或 shell 工具去探索某些东西，比如你正试图列出目录有哪些，你正试图通读许多不同的文件。用户提问了一个问题，你知道，可能是关于你的……这个仓库里的身份验证是怎么构建的。

<details><summary>Original English</summary>
And we discovered a deterministic pattern across those variations. So, when you're running a coding agent, tool call on a very basic thing is like, you know, if you're trying to run a bash or shell tool to discover something like you are trying to list what the directories are, you're trying to read through a bunch of different files. User has asked about a question about, you know, maybe your how is authentication built in this repository.
</details>

>> 而你的编程智能体此时正在试图利用内置的一堆工具弄明白：我需要列出所有文件，阅读其中的一堆，探索它们，然后回答用户，

<details><summary>Original English</summary>
And your coding agent is right now trying to figure out with a bunch of tools that are pre-cooked in that I need to list all the files, read a bunch of them, explore them, and then answer the user,
</details>

>> [嗤笑声]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 所以，很多开源模型现在表现出来的……我觉得它们不知怎么地就在工具调用上很拉跨，对吧？而且这种模式并不是说范围特别宽泛，对吧？它像是，你知道，当呃是针对 DeepSeek 特有的。DeepSeek V4 Pro 有这种奇怪的大男子主义气质（alpha male energy），无论它发给你什么，它都认为那是正确的做法。如果它呃如果它发给你错误的工具调用 schema，而你回传了一个 Zod 错误，它根本不理你。在十亿个 token 里面，它平均会把同样的事情重复大约 56 次。你会觉得：“你为什么……它为什么要那么做？”对吧？

<details><summary>Original English</summary>
>> So, what of what what a lot of open models are doing is I think they somehow suck at tool calling, right? And the pattern is not like super broad, right? It is like, you know, when uh is very specific to DeepSeek. So, DeepSeek V4 Pro has this weird alpha male energy where whatever it sends you, it thinks that that is the right thing to do. And if you uh if it is sending you wrong schema of the tool calls, and you send back a Zod error, it doesn't listen to you. It would repeat that same thing for like 56 times on average in a billion tokens. Where you'll be like, "Why are you Why is it doing that?" Right?
</details>

<!-- chunk 2/5 -->

>> 为什么——为什么它们不听报错呢？我原以为这是个很常见的功能，比如以前 Instructor 就会这么做。

<details><summary>Original English</summary>

>> Why don't Why don't they listen to the errors? I I thought that's like a very common thing. Like, Instructor used to do that.
</details>

>> 我也毫无头绪。你看，作为一名程序员，我会觉得如果我的工具调用失败了，我只需要返回某种 schema，比如 Zod 的错误提示，只要 LLM 足够聪明，对吧？

它就会搞定它，对吧？我的直觉是——这可能是一个争议性观点——因为它们是……

我觉得很多这类开源模型是在这样一个系统里构建或训练出来的：它们是从数据中学习的，而它们认为这些数据质量极高。比如，它们是从比自己更优秀的模型或类似来源那里学习的，对吧？它们的训练逻辑就是：无论被告知什么，那都是对的、正确的。所以它们的本性就是：无论我告诉你什么，也都是正确的，所以别想着来纠正我。

这……再次强调，其中很大一部分感受是基于感觉（vibe-based）的。

我发现这点是因为……这其实是件很微不足道的小事。比如，我也在我的帖子中分享过了。你介意我分享一下吗？比如分享一下屏幕之类的？

<details><summary>Original English</summary>

>> I have no idea. Like, you know, as a programmer, I would think that, you know, if my tool call is failing, all I have to do is send some schema back, like Zod error, and an LLM that is smart enough, right?

And it will just do it, right? My gut feeling is it might be a hot take the because they are

I think a lot of these open models are built or trained in a system where they are learning from data,

which they consider really high quality. Like, they're learning from a better model than them or something like that, right? And their training is whatever you are being told is right, it's correct. So, their entire nature is whatever I am telling you is also correct, so don't try to correct me.

This is Again, quite [clears throat] a lot of this is vibe-based.

And I discovered this because like it's it's a silly thing. Like, for example, I shared it in my post as well. Do you mind if I share it? Like, share the screen or something?
</details>

>> 没事，你请便。我觉得你得……我们录制前测试过这个。这些是要给观众看的，我们在聊的时候他们也可以去查那条推文。只要确保你放大屏幕就行，显而易见。

<details><summary>Original English</summary>

>> No, go ahead. I think you you have to I got to do we try tested this before you recorded it. These are to for people to look at. They can look up the tweet while

we're talking as well. Uh just make sure you zoom in, obviously.
</details>

### 开源模型的工具调用修复逻辑

>> 好。

这就是那篇帖子，对吧？当时我的状态就像是在说：你知道吗，我刚刚发现了 DeepSeek 为何以及如何能超越 Opus 4.7。

这里说的是 Opus 4.7，不是 4.6，4.6 是更好的模型，对吧？

所以，我们发现的情况是：比如它在发入……当你有一个比如 shell 工具，它包含一些本应是可选的参数或实参时，它会在上面发送一些奇怪的东西，比如一个空对象或者一个不该出现的 null，而极其严格的 Zod 就会直接报错并把错误抛回去。

然后它又会一次又一次地收到同样的结果。同样的工具调用，对吧？

因此，我最终没有把那个错误抛回去，而是去修复了它，对吧？刚开始只是大约 3200 行代码，包含了 4 种修复规则。可以把这种修复逻辑想象成数据库迁移（database migrations）。你知道，每个文件对应一个迁移。所以我最终创建了修复文件。比如如果你看到像这样的情况：你知道，它本该输出我实际需要的数组，却输出了 JSON 字符串类型的数据，那我就可以确定性地把它修正为一个数组，对吧？当我这么做的时候，我不仅会把结果返回，还会顺带返回一条备注、一个提示、一个修复提示，说明“你知道吗，你本该给我发送这种类型的数据，不过无论如何，这是执行结果”。这就像你在教某人开车一样。

他们眼看就要撞上另一辆车了。你不会先去给他们讲怎么做才对，而是会先尽力把他们救下来，然后再解释你刚才为什么要救他们，对吧？比如他们一开始本应该怎么做。我认为很多这类模型非常喜欢这种修复逻辑，因为我们看到的是，一旦你把带有修复逻辑的结果发过去，紧随其后的第三次工具调用就恢复正常了。

而不是……而且它突然之间就变得超级聪明。它理解了，比如“好吧，我拿到了想要的结果，接下来我要这么做”。这种情况在很多不同的地方也都有体现。比如，它试图读取一个文件，却没有给出偏移量——即你是想从这个文件的顶部还是底部读取 100 行。

于是我就做个自主判断，比如：好吧，这是它第一次读取这个文件，那就给它这个文件的前 100 行，对吧？然后它很快就会意识到：“噢，我实际上是想读取一个日志文件，所以需要最后 100 行”，这样它就能非常轻松地理会过来，而不会出现平均 50 次以上的工具调用失败。

像这样的事情对开发者来说本该是非常显而易见的，但现状是很多开发者其实在使用 Claude Code。

他们去 hack 自己的设置，改掉基础 API 端点和 API 密钥，试图把 Claude Code 用作开源模型的测试环境（harness）。

而 Claude Code，呃，他们把很多错误隐藏在 Control-O 背后，对吧？所以你甚至都不知道每个 session 会有 50 多次工具调用失败。

你只是坐在那里纳闷：“噢，为什么 DeepSeek 这么慢？”

而他们对于不去修复这个问题有着既得利益。比如，他们不在乎开源模型。他们的编程智能体本来就不是为了开源模型打造的。

所以这不仅对他们十分有利，而且 Twitter 上普遍的声音就是：“噢，它真棒”以及“噢，它太烂了，超级慢”。

所以我感觉这最终总是变成了工具调用的 harness 问题，而不是模型本身的实际问题。比如，它可能就像这种事情一样微不足道：当它发送文件读取路径时，对吧？

它会莫名其妙地生成某种 markdown 链接。

而这是完全可以确定性修复的，对吧？这样你就不必在这上面浪费你的 token 或做类似的事了，对吧？是的，我觉得就是……

你请讲。

<details><summary>Original English</summary>

>> Yes.

So,

this was the post, right? So, this was me being like, you know,

I just discovered why and how DeepSeek can outperform Opus 4.7.

So, this is Opus 4.7, not 4.6. 4.6 is a better model, right?

So,

and the thing that we discovered was like it was sending in whe- you have some tool like a shell tool and it has some parameters or arguments that should be optional, it would send some weird thing on that like an empty object or or a null where it is it doesn't belong and Zod being super strict would just trip up and send back that error.

And it will get back the same result again and again. Same tool call, right?

So instead of sending back that error, I ended up repairing that, right? It started with just like 3, 3,200 lines of four repairs. Think of it this repair logic like, you know, database migrations. You know, you have one migration per file. So I ended up creating repair files. Like if you see something like this where, you know, it is emitting, you know,

JSON strings type of data when I actually wanted an array, I can determinately deterministically fix that to an array, right? And when I do that, I will not only just send back the result,

I will also send back a note, a hint, a repair hint that, you know, you should have sent me this type of data, but here is the result anyway. Think of it like you're teaching somebody how to drive a car.

And they're about to, you know, hit another car. Instead of telling them what to do correctly, you'll first try to save them

and then you will explain like why you saved them, right? Like what they should have done in the first place. I think a lot of these models

really like this repair logic because what we saw is the moment you send the result with the repair logic, right after that the third tool call

is fixed.

Instead of, you know, and it it all of a sudden becomes super smart. It understands like, okay, I got the result what I was looking for and I'm I'm going to do this. And it shows up in so many different places as well. Like for example, it is trying to read a file and it is not giving you the offset of are you trying to read the 100 lines from the top or at the bottom of this file.

So, I just make a judgment call like, okay, it's

the first time it's going to read that file, so let's give it the first 100 files of first 100 lines of that file, right? And then it realizes very quickly, oh, I I was actually trying to read a log file and then needed the last 100 and it can very easily understand instead of, you know, those 50 plus on average tool call failures.

And something like this should be very obvious to developers, but what's happening is a lot of developers actually use cloud code.

They hack their, you know, change the base API endpoint and the, you know, API key and they try to use cloud code as the hardness for open models.

And cloud code, uh, you know, you know, they hide a lot of the errors behind control O, right? So, you don't even know that, you know, you have like 50 plus tool call failures plus per session.

You you're just sitting there and you're like, oh, why is DeepSeek so slow?

And they are they it's in their vested interest to not fix that. Like, why they don't care about open models.

They didn't build their coding agent for open models.

So, it works out really well for them, but for the common thing that the common team across Twitter is, oh, it's so good and oh, it's so bad, it's super slow.

So, it

I feel like this always ends up being a tool call hardness issue

than, you know, an actual model issue.

Like, it's it's it can be as silly as something like this. When it's sending the read file path, right?

It would create some markdown link and it for no reason at all.

And this is super deterministically fixable, right? So, you don't have to like waste your tokens on it or anything like that, right? Yeah, I think that's

and

Go ahead.
</details>

>> 嗯，我是说，我认为去研读数据并真正审视你刚才所说的那些内容，我觉得这真的很有帮助。深入思考……我想知道是只有 DeepSeek 表现出这类情况，还是这只是开源模型普遍存在的一个诀窍？

<details><summary>Original English</summary>

>> Well, I mean I I think the reading the data and actually looking at like what you actually said and I think it's it's really helpful. Being thoughtful

like

I wonder if it's only DeepSeek that's like showing this kind of stuff or is it just a general open models trick?
</details>

### 从 DeepSeek 扩展到更多模型与数据规模

>> 是的，我觉得首先——同样也是出于我本人的习惯——我起初以为这只是 DeepSeek 独有的。后来我查看了我们过去 30 天的日志，发现 Kimi 也完全在做一模一样的事情。

接着我们修复了 Kimi 模型，又修复了 MiniMax 模型，现在我们在数千亿的 token 中拥有大约 16000 种不同的修复变体。我们目前的处理量在 6000 亿 token 左右。

而关于那些工具调用失败的数据，超级、极其重要。

总体而言，这让一个原本基本完全无法使用的模型（比如 DeepSeek V4 Flash），变成了真正能与强手竞争的东西，对吧？

而且，在我推送了这个更新时，这更像是一种直观感受上的验证（vibe check）。我们的投资人之一，Tom Preston-Werner 基金（PW）的管理合伙人（GP），他就说：“你做了什么？为什么 DeepSeek V Flash……V4 Flash 现在表现超级稳健了？”模型的整个感觉完全变了。它开始以一种不同的方式处理事情。我不知道你有没有见过这种情况，但如果你运行任何开启了权限确认的编程智能体，模型实际上会变笨。

而如果你在完全绕过权限确认的情况下运行它们，它们的表现会好得多。即使你耐着性子一次次点击“是”、“是”、“是”、“接受”之类的确认，你也会发现由于权限阻断或类似机制带来的迟滞，模型最终会被带偏方向。也许模型本身在训练时并不是这样的，但对于模型而言情况就是如此。如果它们遇到的工具调用错误少得多，它们就会更有创造力。

它们可以做很多探索，并且能够持续运行更长时间。比如我们的一位用户，我记得他一个人在 DeepSeek 上就消耗了大概 700 亿 token。我之前查看过他的数据，他把我们的用量统计页面都刷崩了。

我们就是这么发现他的。

他说：“我经常用 Command Code 运行 DeepSeek，连续跑 12 个多小时的长会话。”我个人都还没这么干过，对吧？

所以，我认为当极少数的工具调用发生……发生极少数的工具错误、工具混淆时，

这种修复逻辑在整体上能让开源模型达到何种优异程度，确实会让你大为震撼。

<details><summary>Original English</summary>

>> Yeah, I think the first thing again me being me, I thought

this is just DeepSeek. Then I looked at our, you know, logs for last 30 days and Kimi is doing exactly the same thing.

Then we fixed the Kimi models and we fixed

MiniMax models and now we have like 16,000 different repair

you know, variations across hundreds of billions of tokens. We are doing anywhere from 600 billion tokens right now.

And the data on failure of those tool calls super super important.

In overall, this goes from

a model that was practically completely not useful like DeepSeek V4 flash

to something that can actually compete with this, right? Like

and this is like more of a vibe check when I pushed out this update. One of our investors, Tom Preston-Werner's fund, PW

their GP, he was like, "What did you do? Why is DeepSeek V flash

V4 flash super solid now?" Like the vibe of the model completely changes. It starts doing things

in a different way. I don't know if you've seen this, but like if you run any coding agent with permissions on the models are actually dumber.

And if you run them without, you know, the complete bypass of permissions, they do much better. Even if you like sit through those yes yes yes accept or whatnot, you will see that, you know, the model ends up getting steered in the wrong direction because of the slowness of permission blocks or whatnot. Maybe that's not how the models are trained or whatnot, but it's it's the same thing with models. Like if they are seeing a lot less tool call errors, they are much more creative.

They are they can explore a lot and they can continue a lot longer. Like one of the our users has actually done like I think 70 billion tokens on Deep Seek. I was looking at his data. He broke our usage page.

That's how we discovered him.

And he's like, "I constantly run Deep Seek with Command Code for 12-plus hour-long sessions." I personally have not done that, right?

So, when I think a lot less tool calls are happening

tool errors are tool confusion is happening.

This repair logic kind of blows you away like, you know, how good open models can be overall.
</details>

>> 是的，那真的很吸引人。我的意思是，我想知道你还有什么其他发现吗？这方面有后续的工作在进行吗？你看，距离你做这件事已经过去一小段时间了。

呃，你做了一些泛化。呃，在这个领域有正在进行的工作吗，或者说，你知道，你是否基本上在不断地从 Command Code 中提炼出类似的见解？

<details><summary>Original English</summary>

>> Yeah, that's a really fascinating. I mean, I guess

what else have you found? Is is there is there is there ongoing work? You know, it's been a it's been a little bit since you've done this.

Uh you've generalized a bit. Uh is there ongoing work in in this area or uh you know, are you sort of

basically constantly spinning out insights like this from Command Code?
</details>

>> 是的，这就好比……首先发生的一件事是，我认为就目前市面上的情况而言，我们可能是 DeepSeek 使用量最大的编程智能体。

因此，

我们在 DeepSeek 上运行着极其庞大的推理量。所以很多人……

<details><summary>Original English</summary>

>> Yeah, it's like So, one of the first thing that happened was I think we might be the most used coding agent out there right now for Deep Seek.

So,

we are doing so much inference on Deep Seek. So, a lot of people
</details>

<!-- chunk 3/5 -->

### 修复大模型的设计粗糙感（Design Slop）

其实还艾特了 DeepSeek 研究团队的一帮人。为了证明这一点，其实我们推出了一个 Go 计划，每月只需 1 美元，你就可以获得大约 6 亿 token 的 DeepSeek 专业版免费额度。就是为了证明开源模型其实非常非常厉害，而且他们正在迎头赶上，对吧？我觉得这产生了一定的影响，我觉得可以说，DeepSeek 看到他们也可以降低价格，做同样的事情，向人们展示他们的模型其实非常非常优秀。

<details>
<summary>Original English</summary>
actually tagged a bunch of people on Deep Seek research team. And to prove this, actually, we launched a Go Plan with just $1 per month to you can do like 600 million tokens of Deep Seek free for pro in it. Just to prove like open models are actually really really good and they are catching up, right? And I think that kind of percolated to I I I think I would it wouldn't be too far to say that Deep Seek saw that they can discount their prices and do the same and show people that their models are actually really really good.
</details>

但同时，我也看到很多来自不同 coding agent harness 公司的人被艾特到这条推文里，比如，“这东西是在做那件事吗，对吧？”也有很多人可以很容易地把整套东西放进 prompt 里，让它自己去修复，对吧？诸如此类的事情。不过，最近发生的最有趣的事情之一是，我们已经能够将同样的方法应用于“设计粗糙感”（design slop）。你知道，就像所有大语言模型都会生成的那个靛青紫色渐变的东西？

<details>
<summary>Original English</summary>
But also, I saw a lot of people from different coding agent harness companies being tagged in this tweet like, you know, like is is this thing doing that, right? There's like also by a very people can easily just put this entire thing into a prompt and get by to fix itself, right? So, things like that. But, one of the most interesting things that just recently happened was we have been able to apply the same thing to design slop. You know, like you know, that indigo purple gradient thing that all LLMs do?
</details>

>> 我想 Mario Zechner 现在就有一条正在病毒式传播的帖子是关于这个的。基本上，如果你……你熟悉 Mario Zechner 吗？

<details>
<summary>Original English</summary>
>> I think Mario Zechner has a current viral post about it right now. Basically, if you if Are you familiar with Mario Zechner?
</details>

>> 知道，知道，知道。

<details>
<summary>Original English</summary>
>> Yeah, yeah, yeah.
</details>

>> 呃对，他如果你去他的个人资料，他有一个关于设计粗糙感的例子。

<details>
<summary>Original English</summary>
>> Uh yeah, he if you go to his profile, he has an example of design slop.
</details>

>> 就是这样，对吧？我觉得大家都心知肚明。我其实很喜欢紫色。而且我想指出的是，正在发生的是靛蓝粗糙感（indigo slop），而不是紫色粗糙感。对吧？但是，但是我们发现的是，在我们处理的数千亿个 token 中，我们可以部署相同的模型来修复设计粗糙感。我们查看了数据，发现我们显然与一群非常有设计品味的出色设计师聊过。

<details>
<summary>Original English</summary>
>> There you go, right? I think everybody just knows So, I love the purple color. And I would like to point out that it's the indigo slop that is happening, not the purple slop. Right? But, but what we have found is we can deploy the same model to fixing design slop across the hundreds of billions of tokens that we have done. We looked at the numbers and we found that obviously we chatted with a bunch of amazing designers with amazing design taste.
</details>

我们发现这其实是一个非常类似的问题。大多数大模型所做的事情只有有限的几种。如果你能给它们某种组合式框架，比如修复它们的设计思维，同样的逻辑也适用，对吧？例如，这里可能有 10 条主要规则，你可以把它们放进一个 skill 文件或者随便什么地方。你会看到你的设计变得更好了。我们在不同的商业或开源大模型中都看到了这种重复的效果。

<details>
<summary>Original English</summary>
And we found out that it is also very similar a problem. There's a finite set of things that most LLMs do. And if you can give them like a compositional framework of sorts, like you can repair their design thinking, the same thing applies, right? Like for example, these are like probably 10 big rules you can put them in a skill file or anything. And you will see your design get better. We've seen this repeated across different LLMs, commercial or open, whatsoever.
</details>

这在某种程度上是相同的修复工具逻辑，对吧？就比如你基本上是在指导你的编码智能体：你知道，你不要做这个、这个、这个、这个和这个。如果它做了，你就会确定性地去修复它。比如在这里你可能会觉得非常不错的一件事就是，第一个就是这种“工作模式优先组合”（work pattern first composition）。当你让一个模型去给我设计这个仪表盘时，它们通常不会去思考该设计背后的意图，它们就只是扔给你那种一排三个卡片、左侧或顶部有一条边框之类的粗糙设计。这是非常普遍的现象。

<details>
<summary>Original English</summary>
It's the same repair tool logic of sorts, right? Like you You basically guiding your coding agent that, you know, you're not going to do this, this, this, this, and this. And if it does, you are deterministically fixing it. Like one of the things that you might find really good here is first one was this the work pattern first composition where when you ask a model go and design me this dashboard they generally do not think about the intention behind that design and they just uh slop you with that, you know three cards in a row and, you know, one border on the left side or top side or what not. That's a pretty common thing.
</details>

如果你给它们一个非常简单的框架，比如我们在寻找什么类型的展示界面，实际上就只有这七种模式，它们就会表现得非常非常出色。还有诸如……

<details>
<summary>Original English</summary>
Uh if you give them a very simple framework of, you know, what type of surface area are we looking for, which is literally just these seven patterns, they do really, really well. And things like
</details>

>> 这七种模式是从哪里来的？是……是你刚想出来的吗？

<details>
<summary>Original English</summary>
>> Where Where are these seven patterns from? Is Did you just come up with it?
</details>

>> 是的，我和许多不同的设计师聊过。

<details>
<summary>Original English</summary>
>> Yeah, I talked to a bunch of different designers.
</details>

>> 呃，我只是想知道是否有这样一本书或者其他什么，对。这是大家都心知肚明的传统知识（lore）吗？

<details>
<summary>Original English</summary>
>> Uh I'm just wondering if there's like a book or some, you know, yeah. Is this like lore that people just know?
</details>

### 设计思维框架与 OKLCH 色彩空间

>> 人……人们，我认为你可以这样想：当一个设计师在设计仪表盘时，他们在思考这是一个监控界面，对吧？比如我们试图去监控，这就是背后的意图，对吧？根据我们与一群优秀设计师的交流，他们就是这样工作的。我们想，如果能把这个做成一个 `/design` 技能，看看大模型会如何自我修复。我们还发现了一些非常非常有意思的事情，比如我个人不用 OKLCH，但显然大语言模型非常擅长它。

<details>
<summary>Original English</summary>
>> Pe- People I think you could you could think of it like, you know, when a designer is designing a dashboard they're thinking about this is a monitor surface, right? Like we're trying to monitor That is the intention behind this, right? And this is across the chats we had with a bunch of amazing designers, this is how they work. And we thought if we could turn this into a slash design skill see how the limbs will repair themselves. We also discovered something really, really we're like I personally don't use OKLCH, but apparently LLMs are really good at it.
</details>

如果你看到它们使用 HSL 或类似的东西，它们其实无法在 HSL 中很好地快速控制亮度，但在人眼看来，非常非常容易看出比如这个颜色和那个颜色看起来不一样。但如果你强制大语言模型使用 OKLCH，与其他任何东西相比，它们都能非常非常好地控制调色板。很多我的设计师朋友也是这么做的。他们喜欢易于……

<details>
<summary>Original English</summary>
And if you see them using HSL or something they are they they they they don't actually are able to control the lightness in HSL very quickly, but on to human eye it's very, very easy to see like this color and this color do not look the same. But if you force an LLM to use OKLCH, they can control the colors palette really really well compared to any of other things. And this is what a lot of my designer friends do as well. They love easy to
</details>

>> 这就是我们发明 OKLCH 的原因，对吧？因为他们意识到……我的意思是，每次色彩理论有所发展，我们也必须更改 CSS 函数，这在学习 CSS 时有点让人恼火。

<details>
<summary>Original English</summary>
>> they That's the reason we invented OKLCH, right? Because they did We realized I mean every time color theory advances, we also have to change the CSS functions, which is mildly annoying for learning CSS.
</details>

>> 是的，但那种感觉挥之不去，就好像我昨晚刚写过这个。这是昨晚的内容。我想这附近某处有关于设计粗糙感的内容。因为这是新写的，所以我在费力找它在哪。我们只有大约 24 篇参考文档、10 个设计坏味道（design smells），以及我们在不同设计师身上看到的 7 种模式。当我们设计了一堆不同的落地页并让那些设计师看时，他们大概只需要 1.5 秒就能认出：“噢，这是 AI 做的，而这是有人类审视过的。”对吧？

<details>
<summary>Original English</summary>
>> So, yeah, but it it's I can't shake this feeling, but it's like I actually wrote about this just last night. This is from last night. Like I think they're they're the design slop thing somewhere here. Like this is new, so I'm struggling to find where that is. They We only have like 24 reference documents, 10 you know, design smells, and seven patterns that we saw across different designers. And when we designed a bunch of different landing pages and got those designers to look at them, it takes about 1.5 seconds for them to spot, "Oh, this is from AI and this is somebody human looked at it." Right?
</details>

所以，当把他们指出的差异写下来时，发现它们全都是可以通过确定性方式修复的模式。比如你可以把 HSL 转换为 OKLCH，或者你可以强制大模型去这么做，对吧？这感觉就像你能修复 90% 的设计粗糙感。这并不是能力差距，它更像是一种契约差距（contract gap），即你的 harness 告诉大模型要做什么，与你的用户所说的内容之间的差距。用户总是会说：“修复我的设计，让它更漂亮，让它更吸睛，”或者类似的话。

<details>
<summary>Original English</summary>
So, the differences that they spotted, when we wrote them down, they are just deterministically fixable patterns. Like you can convert HSL into OKLCH, or you can force an LLM to do that, right? And it's like a feels like you can fix 90% of design slop, which is not a capability gap. It's more like a contract gap in what your hardness is telling an LLM to do versus what your user is saying. User is always going to say, "Fix my design, make it prettier, make it pop," or something like this.
</details>

如果你能给它们一个框架，说明一个真正优秀的设计师的设计品味是怎样的，它们就会选择这种类型的配色方案，它们在开始实现落地页之前就会思考意图。这里的意图是什么，对吧？这是一个简短的契约，但它会让你的设计粗糙感变得非常非常微小。我大概会补充这一点，对吧？是的。

<details>
<summary>Original English</summary>
If you can give them a framework of this is what the design taste of a really good designer is like, they will pick this type of color scheme, they will pick they will think about intent before starting to implement that landing page. What is the intent here, right? It's a short contract, but it's makes your design slope really, really minimal. I would I would probably add, right? Yeah.
</details>

### 让编程智能体学会设计师的思维

>> 我觉得这是一个非常好的概述。对于那些还不了解的人来说，Aman 实际上在设计方面也有很大的发言权。我甚至并不能完全了解你所做过的一切，但你知道，当你在设计与代码的交汇点发表想法时，我肯定会倾听。

<details>
<summary>Original English</summary>
>> I think this is a really good overview. And and for those who don't know, like Aman actually has a lot of authority also on the design side. I actually don't even super know everything that you've done, but you know, I I I definitely will listen when you have thoughts on the intersection of design and code.
</details>

>> 非常感谢。我……我觉得我想成为一名设计师。我以前从来没有真正擅长过它，你知道，比如我不会画草图或任何类似的事情，但我认为我有一种感觉，现在很多人几乎能够构建任何东西。而我们现在正在根据设计来区分好作品和坏作品。因此，让每一个使用编程智能体的构建者都能够像设计师一样去设计，是我非常重视的事情，对吧？

<details>
<summary>Original English</summary>
>> Thanks a lot. I I I feel like I I wanted to be a designer. I was never really that good at it, you know, like I couldn't sketch or anything, but I think this is this is a feeling that I have like a lot of people are right now able to build just about anything. And we are now differentiating between good work and bad work based on their design. So, enabling every builder using a coding agent to be able to design like a designer is something that is very close to my heart, right?
</details>

>> 是的，我认为这……我认为我们大家都越来越成为通才了。肯定有一些以前不敢做的事情，我现在会用 AI 去尝试。看起来你想给我们展示 command code，是吧？请继续。

<details>
<summary>Original English</summary>
>> Yeah, I think that's some I think we're all a lot becoming more generalist. And there's definitely things that would not dare to do previously that I that I'll now try with AI. Like yeah, that's look at it looks like you want to show us command code, yeah? Go ahead.
</details>

>> 是的，就像……例如，这是我们文档的落地页，对吧？作为一名开发者，我本不会费心去创建所有这些东西，对吧？但是当我把它输入给我们的设计技能时——所以 command code 现在附带了一个打包好的 `/design` 技能，其中预先内置了所有这些参考资料。就像我昨晚刚在调整我们的优惠活动，比如 2.6 版有五折优惠。

<details>
<summary>Original English</summary>
>> Yeah, it's it's like for example, this is the landing page of our documentation, right? As a developer, I would not have gone through the trouble of creating all of this, right? But when I fed that to our design skill, so command code now comes up with a comes bundled with a slash design skill, which has like these all of these references in there cooked pre-cooked in. Like I was just last night fixing our deals that we have like going 2.6 is you know, 50% off.
</details>

所以我给它发了一张非常基础的截图，里面全是乱糟糟的东西，而这就是它转换成的样子。在我看来，它看起来非常非常漂亮。我觉得，好吧，这感觉就像……你知道，就像一张可以打印出来的票据，你知道，在……我不知道，像电影票或者什么优惠票据，它基本上理解了这东西背后的意图，并尝试重新创造出那种设计。而我作为一名程序员，仅仅告诉它：这里有一个优惠，这是数据，直接加到我们的文档里就行，对吧？因此，提供这样一个框架，你知道，这不像工具调用（tool calling）或任何东西。这更像是一个非常优秀的思维框架，让大模型拥有……

<details>
<summary>Original English</summary>
So, I fed that a very basic screenshot of, you know, all of this mess, and this is what it converted into. In it to me it looks really really good. I'm like, okay, this is this feels like, you know, like a ticket that you could print up you know, on a I don't know, like a cinema ticket or what not in from deal that it basically understood the intention behind this thing and tried to to recreate that design. When I as a programmer only told it, here's a deal, here's the data, just add that to our docs, right? So, giving that framework of you know, this is not like tool calling or anything. It's like a really nice framework of thinking that LLMs have
</details>

<!-- chunk 4/5 -->

把这种能力内置进去。

<details><summary>Original English</summary>
this capability cooked in.
</details>

它们能够非常、非常好地梳理自己的思路。只要你给它们提供思考那些事情的正确方式，它们就能做得非常、非常出色，对吧？我们在工具调用上做的事情也是同理，基本上同样的概念也适用于……你知道的，设计。我们团队现在有一位成员正在和一个安全人员社区合作。

<details><summary>Original English</summary>
They can organize their thoughts really really well. They can design really really well if you just give them the right way to think about those things, right? Same thing uh we did with our tool calling, same same concept basically applies to uh you know, design. And one of our team members right now is working with a community uh of security people.
</details>

他们认为同样的问题也可以应用到安全领域。比如你去查看日志，发现这是安全方面最常见的模式，这就是正在酝酿的情况；然后它们可以对你的软件包之类的内容应用自动修复，让大语言模型在遵循你关于“绝不写糟糕的安全……糟糕或薄弱的安全代码”的指导方针上，变得非常、非常连贯。

<details><summary>Original English</summary>
They think that the same problem can be applied to security as well. Like you look through the logs and you figure out that this is the most common pattern security-wise, this is what is uh brewing up and they can apply automatic fixes to your packages or what not and make LLMs really really kind of like coherent on following your guidelines of never write bad secure bad or like poor secure code.
</details>

>> 是的，我觉得……

<details><summary>Original English</summary>
>> Yeah, I think
</details>

>> 比如那是我们大家都想变得更聪明了解的一点。你能给我们概括一下人们应该了解的那些差异化特性吗？因为我觉得这就是你一直在做的其中之一。嗯，你知道，taste 确实是你绝对在重点打造拥有的东西。你目前仍然在追求做自己的模型，还是说你主要就是打算做面向开源模型的最佳 CLI？

<details><summary>Original English</summary>
>> Like that's something that we all want to like get smarter on. Can you give us like a overview of just like the differentiators that that uh people should be aware of because I think like this is one of them that's like that you've been working on. Um you know, taste is is something that you're you're you're you're definitely focusing on on owning. Are you still pursuing your own models or are you are you mostly just going to be like the best CLI for open models?
</details>

### 开源模型与 Taste 机制

>> 是的，我……目前我们算是有两个方向。这个东西，再次说明，它就像一个 CLI，对吧？它是一个成熟的代码智能体，能做你所期望任何代码智能体能做的一切事情。它既支持商业模型，也支持开源模型。只是说我们在开源模型市场中找到了我们的 PMF，比……你知道的，Claude 实际上对工具调用非常、非常宽容。所以即使你的代码智能体运行环境出了差错，它也能意识到“噢，我收到了这个错误”，并且能够自行修复。而开源模型就不是这种情况了。

<details><summary>Original English</summary>
>> Yeah, I there are like two directions right now that we sort of own. Uh this thing is again this is like a CLI, right? It it is like full-fledged coding agent does everything that you can expect any coding agent to do. It has both uh you know, commercial models or open models. It's just that that we have found our PMF of source in the open models market more than you know, Claude is actually really really lenient with two calls. So even if you know, your coding agent harness messes up, it can figure out that oh, I'm I'm being sent this error and can fix itself. Not the case with uh you know, uh open models,
</details>

但 taste 这个东西依然存在。它基本上可以说是这样运作的。这是我经常看到的一个场景。当我在使用某个东西时，“请使用 TypeScript”。它却在用 TSE。我想要你用 tsup，对吧？它在用某种别的测试框架，而我更喜欢 Vitest。要让你的代码智能体去做你一开始就想完成的事情，中间会有非常多的来回反复。

<details><summary>Original English</summary>
but the taste thing is uh still there. Like it basically sort of like works like this. This is a very common uh site that I have. When I'm using something, please use TypeScript. It's using TSE. I I want you to use TS uh TS up, right? It's using some different framework of testing. I prefer Vitest. And it's like a lot of you know, back and forth in getting your coding agent to do what you wanted done in the first place.
</details>

但是在有 taste 的情况下——taste 就像是一个元神经符号模型。比如我有很多……根据反馈，我尽量把它很好地隐藏在文档的某个地方，这样开发者就不用去阅读那里非常傻瓜式的内容了。

<details><summary>Original English</summary>
But with taste as taste is like a meta neuro symbolic model. Like I have a lot of uh I tried to like based on the feedback I've hidden it very well in docs somewhere. So you know, developers don't have to go and read the really silly things there.
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 对吧？也就是我们关注的整个 KL 散度循环。比如一个大语言模型如果已经了解了某件事，它就不应该出现在你的 skill 或者 taste 文件里。那完全是没有用的上下文，对吧？所以它基本上在做所有这些奇妙的事情，一旦你真正浏览完——链接在哪儿？——一旦你真正看完了所有这些内容，一旦你用 command code 构建了一个 CLI、一个 API 或者是前端项目，它实际上就会学会许多规则，并且会自动为你进行管理。

<details><summary>Original English</summary>
>> Right? The entire KL divergence loop that we look at. Like if an LLM already knows about something, it should not end up in your you know, skill or taste file. That is absolutely useless context, right? So it basically does all of this weird thing where once you actually go through Where is the link? Once you actually just go through all of this, once you have built a CLI or an API or a front-end project with command code, it actually ends up learning a bunch of those rules that are automatically managed for you.
</details>

举例来说，如果你之前用 Commander 来构建 CLI，而现在在这个特定项目中你开始使用 Meow，它就会为你替换掉它。整个理念就是你的技能会被自动学习和自动管理，并且它们是完全透明的。它们存放在你的代码仓库中，而不是在我们的模型里。所以你在每一次 PR 中都在审查它。你在看着它，比如“是的，我不想保存类似这样的内容等等”。而且它们永远不会过时。

<details><summary>Original English</summary>
So for example, if you are using Commander for building CLIs and now in this particular project you start using Meow, it will replace that for you. The entire idea is that your skills are being automatically learned and automatically managed and they're absolutely transparent. They are in your repository, not in our model. So, you're reviewing it in every PR. You're looking at like, "Yeah, I don't want to you know, save something like this or what not." And they're never stale.
</details>

我觉得很多人遇到的很多问题，都是因为他们一开始坐下来写时，agent.md 或者 cloud.md 里面包含了一些错误的信息。这是我们在宣布 500 万美元种子轮融资时我讨论过的一点：很多开发者坐下来的时候，去考虑规则之类的内容时，他们考虑的都是宏大的东西，对吧？

<details><summary>Original English</summary>
A lot of issues that I feel a lot of people face are because their agent.md or cloud.md has some wrong information when they sat down. Uh this is like one thing I discussed when we launched we announced our, you know, $5 million seed, that a lot of people when they sit down, they think of the rules or what not. They think in the terms of grandiose things, right?
</details>

规则就像是……实际上放大来看。这就是我们的 skill 或 rules 文件与我们的 TS 文件之间的区别，对吧？这是你自己写下来的内容。而 TS 则是不断从你的提示词或你的编辑中学习到的内容，它们为你存储在同一个 Markdown 文件中，对吧？更新则是发生在你记起来要去更新的时候。在大多数情况下，我看到我们作为人类坐下来，往往会做这种宏大的事情。比如“使用这个，我总是偏好那个等等”。

<details><summary>Original English</summary>
Rules are like, you know, like actually zoom in. So, this is like the difference between our skill or rules file or our TS file, right? This is what you are writing down. And TS is what is continuously being learned from your prompts or your edits and they're being stored in the same markdown file for you, right? And updates are when you remember to do it. In most of the times I've seen we we as humans we sit down and we do this grandiose thing. Like, you know, use this. I always prefer that or what not.
</details>

而 TS 是许多微观的决策，而不是太宽泛的内容。比如你在做这件事时，在你运行 up/pr Q 命令时，有时 Emmet 更倾向于……基本上就是从 main 分支拉取最新代码，变基，在一个分支上提 PR，然后再切回 main 分支。这就是我的 PR 工作流程。但我的 PR 文件里并不是这么写的。所以它会自动去修正它，对吧？因为它看到我一次又一次地切回 main 分支。它就会觉得，“好的，这对它来说只是一行内容，但它改善了我的工作流程，而且不需要我自己去费心打理。”

<details><summary>Original English</summary>
And TS are a lot of micro decisions, not too broad. When you are doing this, when you are running up/pr Q command, sometimes Emmet prefers that, you know, you basically fetch the latest from main, rebase it, send a PR on a branch and then go back to the main branch. That is what my PR workflow is. That is not what my PR file says. So, it automatically goes and fixes it, right? That I it has seen me go back to the main branch again and again. It's like, "Okay, it's just one liner for it, but improves my workflow without me having to take care of it."
</details>

而且随着时间的推移，它的复利累积效应非常明显。比如我看过其中一个人的代码，他用 command code 构建了一个安卓应用。现在他就觉得，自己能够非常、非常迅速地构建出更多的安卓应用。这都是同一回事，但它是在你构建这些东西的过程中向你学习这种技能，对吧？

<details><summary>Original English</summary>
And over, you know, over the time it basically compounds a lot. Like if you have one of the guys I was looking at his code, he built one Android app with command code. And now he's like, you know, I'm able to build more Android apps very, very quickly. It's it's the same thing, but it is learning the skill from you as you build those things, right?
</details>

>> [轻哼笑]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 随着时间的推移，我们看到它变得非常有帮助。就在下方某处，我们针对 70 多位开发者进行了一项研究，他们因为大语言模型做出不同的决定、偏离方向，而不得不去编辑文件的次数，或者他们去引导大语言模型——比如“不要这么做，不要用这个，API 的这部分不要用 TRPC 之类的，改用 Hono 或者别的”——他们发现自己编辑或引导的次数下降了。

<details><summary>Original English</summary>
>> And over the time we've seen like, you know, uh it becomes really helpful. Like somewhere down there, we ran a study with like 70-plus developers, and the number of times that they had to go edit files because their LLM made a different you know, the scene took a different turn, or steered their LLM like, "Yeah, don't do this. Don't use this. Don't use TRPC or something and use Hon or whatever for this part of API." They found that their number of edits or steers went down,
</details>

### Taste 与 Skill 的区别

>> 那么请允许我提几个澄清问题。是的。在官网上它被称为一个模型，但随后你又说它可以在系统等之间进行迁移。它是一个……它是一套文件系统吗？显然这是一种记忆形式。它和 skills 相比如何？我应该更倾向于用 skills 吗？我能把它们并排一起使用吗？有所有这些疑问。

<details><summary>Original English</summary>
>> So So let me ask some clarifying questions. Yeah. You On the website it says a model, but then you also say it's like portable uh between systems and stuff. Like is it a Is it Is there a system of files? Like obviously this is a a form of memory. How does it compare with skills? Do I Should I prefer skills? Can I use them side by side? There's all these questions.
</details>

>> 对，对，对。有一点是，我其实很多次被问到这个问题。我写过一篇专门讨论此事的博文。skills 对比 taste，对吧？区别是什么？在最基础的层面，taste 是最高阶的位，它负责管理你的 skills 和 rules。Taste 就是这样一种自动引擎，它在为你创建技能，确保它们不过时，当然你也可以自己去编辑它们。而且总体而言，它实际上看起来是这样的——在看过……我想截至目前我可能已经用 command code 构建了 70 多个 CLI。

<details><summary>Original English</summary>
>> Yeah, yeah, yeah. So one thing is I actually got this question so many times. I have like a written a like a blog post on it. Uh skills versus taste, right? What is the difference? The At the very basic layer, taste is the highest order bit, which is managing your skills and rules. Skill Taste is this automatic engine of sorts that is that is creating skills for you, making sure they're not stale, and you can obviously go edit them yourself as well. It And overall, it actually looks like this, like after looking at I think I probably have built more than 70 CLIs with command code so far.
</details>

这就是我构建 CLI 的全部 taste。就这么点内容，对吧？所以它知道，比如说，我使用 pnpm 仅构建依赖项；它知道我总是倾向于从 0.0.1 开始。就像是那些微小细碎的事情。

<details><summary>Original English</summary>
And this is the entirety of my taste for building CLIs. This little thing, right? So, it knows that for example, I use PNPM only build dependencies thing. It knows that I always prefer starting from 0.0.1. It's like those silly little things.
</details>

而这就像是……我所需要做的全部事情就是执行这个 `npx taste pull`。顺便提一下，我们也有 taste 这个包，对吧？太好了。是的。它就是拉取这个特定的文件，放进你的代码仓库中，然后你要做的全部事情就是向任何代码智能体提出要求，让它遵循我构建 CLI 的 taste。

<details><summary>Original English</summary>
And this is like as all I have to do is I have to do this NPX taste pull. We have the taste package as well, by the way, right? Nice. Yep. It's And it just pulls this particular file, puts it in your repository, and then all you have to do is ask any coding agent and follow my taste of building CLIs.
</details>

然后让它“为我构建一个能够实现这个、这个、这个以及那个的 CLI。然后在最后，展示对 taste 的合规情况”。任何大语言模型都会直接逐一查看整个清单，并能够明白我本来应该使用这个，我本来应该在交互式内容中使用 clack 等等。效果非常好。接着，当你开始在它的基础上持续构建，并且你对每个项目进行修改——每个 CLI 都有别于其他 CLI。

<details><summary>Original English</summary>
And build me a CLI that does this, this, this, and that. And then by the end, show the taste compliance. And it would go Any LLM would just go through all this list and be able to figure out I I was supposed to use this. I was supposed to use clack for interactive things or whatnot. It works out really well. And then when you start continuously building on top of it, and you change every project Every CLI is different from other CLIs.
</details>

这个具体的 taste 就会在那个特定的仓库中发生变化，对吧？反正它本来就存放在你的 Git 仓库里，对吧？是的。所有这些都是自动创建的，但是你可以……是的，你也可以自己进入并编辑它。它是一个 Markdown 文件。

<details><summary>Original English</summary>
This taste of sorts changes in that particular repository, right? So, it lives in your Git repo anyway, right? Yeah. And all of this was automatically created, but you can Yeah, you can come in and edit it yourself as well. It's a markdown file.
</details>

>> 那么置信度我猜也是由大语言模型生成的，对吧？所以，如果你……

<details><summary>Original English</summary>
>> Then the confidence, I guess, is LLM generated as well, right? So, if you
</details>

>> 是的，但是……不过……

<details><summary>Original English</summary>
>> Yeah, but like But
</details>

<!-- chunk 5/5 -->

比如

如果你

<details><summary>Original English</summary>like

if

you</details>

>> 总是这样做，那它就是 1，你知道的。

<details><summary>Original English</summary>>> always

do

it,

it's

one,

you

know.</details>

是的。

<details><summary>Original English</summary>Yeah.</details>

>> 大概是这样。

<details><summary>Original English</summary>>> Something

like

this.</details>

>> 是的。

<details><summary>Original English</summary>>> Yeah.</details>

>> 比如我们实际遇到的问题是……

这里有个有趣的故事，早期我们其实试图把它隐藏起来。

他们觉得，如果我们不向你展示学到的内容，只是让你对比 Claude code 和 command code，开发者们就会有这种惊叹时刻，觉得：“哇，这太棒了。”

呃，他们不知道学到了什么。但我们遇到的问题是，我们不知道如何合并不同的 taste 文件。

这是一件极其……呃，依赖人工的事情。

你可以把它想象成 15 位不同的工程师在一个拥有 1000 个不同 GitHub 分支的 GitHub 仓库上工作。

在所有那些 taste……不同分支中，taste 文件差异太大了。当你把它合并回 main 分支时，我们无法判断你想保留什么或不想保留什么，对吧？所以我们把它做得非常、非常透明。顺便说一句，这是在他们的呃 skills 出现之前。

这是去年十月的事了，对吧？

当时还没有 skills 的概念。只有 API、CLI 和 MCP。我们最终创建了这个，然后，你知道的，skills 这套东西就出现了。

所以……

如果你作为一个人在写东西，我觉得你大概可以直接写置信度分数为 1。你知道自己在说什么，对吧？

如果是从你这里学来的东西，有些确实很好，有些则不然。比如，我总会有这个本地选项，我不想让它出现在我的 help 命令中，因为这是一个用于调试本地……呃，你知道的，调试我本地 API 设置的选项。所以基本上那是件我个人绝不会去写进 skill 文件里的学习心得。对我来说它太细微了，对吧？但它能捕捉到这样细小的事情并解决掉，这真的很棒，对吧？呃，我在我们 Discord 社区里看到的一件事——在所有的那个工具混淆修复器（tool confusion fixer）之后社区火爆起来了——很多人在做的事情是：他们用像 Opus 或 GPT 5.5 这样非常高质量的 LLM 构建一个项目，对吧？

他们构建出一个 taste 文件，然后他们使用……你知道的，超便宜的模型，利用那个 taste 文件在那个项目上继续构建更多东西。

<details><summary>Original English</summary>>> Like

the

the

problem

 we

 actually

 hit

 was





The

 funny

 story

 there,

 we

 actually

 tried





to

 hide

 this

 early

 on.





They're

 like,

 if

 we

 don't

 show

 you

 the





learnings,

 and

 we

 just

 made

 you

 compare





Claude

 code

 versus

 command

 code,

 and





people

 developers

 had

 like

 this

 wow





moment,

 like,

 "Oh

 wow,

 this

 is

 so

 good.





Um

 they

 didn't

 know

 what

 was

 being





learned.

 But

 the

 problem

 we

 hit

 is

 we





don't

 know

 how

 to

 merge

 different

 taste





files.





It

 is

 extremely

 uh

 a

 human

 endeavor.





Think

 of

 it

 like

 15

 different

 engineers





working

 on

 a

 GitHub

 repository

 with





thousand

 different

 GitHub

 branches.





And

 taste

 files

 are

 so

 different

 in

 all





those

 taste





different

 branches.

 And

 when

 you're





merging

 that

 back

 into

 the

 main,

 we





cannot

 judge





what

 you

 want

 to

 keep

 or

 what

 you

 don't





want

 to

 keep,

 right?

 So

 we

 made

 it

 very





very

 transparent.

 And

 this

 is

 before





their

 uh

 skills

 existed,

 by

 the

 way.





This

 is

 from

 last

 October,

 right?





There

 was

 no

 concept

 of

 skills.

 There





was





APIs,

 CLIs,

 and

 MCPs.

 And

 we

 ended

 up





creating

 this

 and

 then,

 you

 know,

 the





skills

 thing

 came

 around.





So





if

 you

 as

 a

 human

 are

 writing

 something,





I

 think

 you

 you

 can

 just

 probably

 write





confidence

 score

 of

 one.

 You

 know

 what





you're

 talking

 about,

 right?





If

 something

 is

 being

 learned

 from

 you,





some

 of

 it

 is

 really

 good,

 some

 of

 it

 is





not.

 Like

 for

 example,

 I

 always

 have





this

 local

 option

 which

 I

 don't

 want

 to





show

 up

 in

 my

 help

 commands

 because

 this





is

 a

 option

 for

 debugging

 local





uh

 you

 know,

 setup

 of

 my

 APIs.

 And

 so





basically

 that's

 a

 thing

 I

 will

 never





personally

 go

 and

 write

 this

 learning

 in





a

 skill

 file.

 It's

 just

 too

 minor,





right?

 Uh

 for

 me.

 But

 it's

 really

 good





that,

 you

 know,

 uh

 it

 picks

 up

 on

 small





things

 like

 this





and

 works

 it

 out,

 right?

 Uh

 one

 of

 the





things

 that

 I've

 seen

 in

 our

 Discord





community

 which

 is

 blowing

 up

 uh

 after





all

 of

 the,

 you

 know,





tool

 confusion

 fixer





is

 a

 lot

 of

 people

 what

 they're

 doing

 is





they're

 building

 one

 project

 with

 a





really

 high

 quality

 LLM

 like

 Opus

 or

 GPT





5.5,

 right?





They're

 building

 a

 taste

 file

 and

 then





they're

 using





you

 know,

 super

 cheap

 models

 to





continuously

 build

 on

 that

 more,

 you





know,

 project

 with

 that

 taste

 file.</details>

### 开源计划与路线图

>> 是的，我的意思是，我认为那个系统对我来说挺行得通、讲得通的。太酷了。我觉得这是一个非常棒的概述。你知道的，如果大家感兴趣，显然可以去查查你们的信息，呃，进一步交流。呃，你们在这个领域已经构建了相当长一段时间了，看到你们这样聚焦在代码编写这个用例上真的很酷。显然我自己也对代码编写相关的 AI 智能体越来越感兴趣了。还有什么结束语吗？大家还可以期待哪些其他事情？

<details><summary>Original English</summary>>> Yeah,

 I

 mean,

 I

 I

 I

 think

 that's

 a





that's

 a

 system

 that

 kind

 of

 works

 makes





sense

 for

 me.

 Cool.

 I

 mean,

 I

 think

 it's





a

 great

 overview.

 You

 know,

 if

 people





are

 interested

 they

 can

 they

 can





obviously

 look

 you

 up

 and

 uh

 chat

 more.





Uh

 you

 guys

 you

 guys

 have

 been

 building





for





a

 good

 while

 in

 in

 the

 space

 and

 like

 uh





it's

 really

 cool

 to

 see

 that

 you're

 sort





of

 honing

 in

 on

 uh

 this

 coding

 use

 case.





I

 I

 have

 also

 obviously

 become

 more





interested

 in

 coding

 uh





AI

 agents

 for

 my

 for

 myself

 as

 well.

 Any





final

 words?

 Any

 other





things

 that

 that

 people

 can

 look

 forward





to?</details>

我也许可以稍微分享一点关于我们的路线图是什么样的，我们接下来要走向哪里，对吧？

所以，我们非常、非常快就会把 command code 开源。

我希望我们能在旧金山的 AI 工程师大会（AI engineering conference）上宣布这件事。

呃，如果我能解决掉那个已有六……六年历史的仓库里的小毛病的话。

这背后的想法是……

<details><summary>Original English</summary>I

 can

 probably

 share

 just

 a

 little

 bit





about

 what





uh

 our

 road

 map

 looks

 like,

 where

 we

 are





headed

 next,

 right?





So,

 we

 are

 going

 to

 open

 source

 command





code





very

 very

 soon.





I'm

 hoping

 we

 can

 announce

 that

 on

 the





AI

 engineering

 conference

 in

 SF.





Uh

 if

 I

 can

 work

 out

 the

 quirks

 of

 six





or

 six

 years

 old,

 you

 know,

 repository.





The

 idea

 behind

 that

 is</details>

>> 六年历史？等等，稍等。六年历史？噢，因为你们它之前是一个 CLI。是的，我懂这些。是的。

<details><summary>Original English</summary>>> Six

 years

 old?

 Wait,

 hang

 on.

 Six

 years





old?

 Oh,

 because

 you're

 it

 was

 a

 CLI





before.

 Yeah,

 I

 get

 stuff.

 Yeah.</details>

>> 是的，我从大约 2020 年就开始构建它了，对吧？

呃，它在去年变成了一个产品。而我曾跟所有人，以及他们的母亲、兄弟姐妹说过，这绝不会成为我的产品，对吧？所以，事情的发展还挺逗的。呃，总之，我们要把它开源了。这背后的想法是，我想让 command code 变得完全可魔改（hackable）。

呃，我一直在这方面非常、非常努力地工作。呃……

我的背景也是做这个的。比如我曾在 WordPress 核心团队待了大约 13 年。

呃，Matt Mullenweg 现在其实是我们的天使投资人之一。当他听说我们要开源 command code 时，他就主动联系了。所以……

这就是……想法是，无论我们的商业模式走向何方，你都应该能够修改 command code 的任何部分，对吧？

而我现在非常认同的另一个想法是，我们不会把它变成由 1500 个模型组成的大杂烩，让你来决定拿它们做什么，对吧？

我觉得就像……你知道的，大概有三种不同的哲学，对吧？呃，一种就像 Windows，任何游戏都能在上面运行。你知道，我觉得 Open Code 就是那样。每个模型都能配合 Open Code 使用。一种就像 Linux，你自己写驱动，就像 Pi。你可以用 Pi 构建任何东西，对吧？呃，对于 Command Code，我所想的和团队某种程度上正在追求或迈向的方向是，你知道的，把它打造成像 Apple 那样。它会拥有最好中的最好的模型，包括开源和闭源的。

它不会包含所有的模型，但它会以任何方式都是可魔改的，所以如果你想的话，你就能够放进你自己的本地模型，或者做任何事情，对吧？所以，这就是我们的方向，比如我们马上就要开源它了，非常、非常迅速。

呃，非常、非常快。所以，是的，对此非常兴奋。

<details><summary>Original English</summary>>> Yeah,

 I've

 been

 building

 it

 for

 like





since

 2020,

 right?





Uh

 it

 became

 a

 product

 last

 year.

 And

 I





told

 everybody

 and

 their,

 you

 know,





mothers

 and

 brothers

 and

 that

 this

 will





never

 be

 my

 product,

 right?

 So,

 funny





how

 you

 know,

 things

 work

 out.

 Uh





anyway,

 so

 we

 are

 open

 sourcing

 it.

 The





idea

 behind

 that

 is

 I

 want

 to

 make





command

 code

 completely

 hackable.





Uh

 I've

 been

 working

 very

 very

 hard

 on





that.

 Uh





my

 background

 is

 also

 in

 this

 thing.





Like

 I've

 spent

 like

 13

 years

 in





WordPress

 core.





Uh

 Matt

 Mullenweg

 is

 actually

 one

 of

 our





angels

 now.

 When

 he

 heard

 that

 we

 are





open

 sourcing

 command

 code,

 he

 reached





out.

 So,





it's

 it's

 The

 idea

 is

 you

 should

 be

 able





to

 modify

 any

 part

 of

 command

 code





irrespective

 of

 where

 our

 business

 model





is

 headed,

 right?





And

 the

 other

 idea

 that

 I'm

 super





subscribed

 to

 right

 now

 is

 that

 we

 will





not

 turn

 this

 into

 a

 soup

 of,

 you

 know,





1,500





you

 know,

 models

 that

 you

 decide

 what





you

 do

 with

 them,

 right?





I

 think

 of

 it

 like,

 you

 know,

 so

 there





are

 there

 are

 like

 three

 different





philosophies,

 right?

 Uh

 one

 is

 it's

 like





Windows

 and

 every

 game

 works

 with

 it.





You

 know,

 I

 think

 Open

 Code

 is

 like





that.

 Every

 model

 works

 with

 Open

 Code.





One

 is

 like

 Linux

 where





you

 build

 your

 own

 drivers

 like

 Pi.

 You





can

 build

 anything

 with

 Pi,

 right?





Uh

 with

 Command

 Code

 what

 I'm

 thinking





and

 what

 the

 team

 kind

 of





is

 going

 for

 or

 towards

 is,

 you

 know,





build

 it

 like

 Apple.

 It

 will

 have

 the





best

 of

 the

 best

 models,

 both

 open

 and





closed.





It

 will

 not

 have

 every

 model,





but

 it

 will

 be

 hackable

 in

 any

 way,

 so





you

 would

 be

 able

 to

 put

 in

 your

 local





model

 if

 you

 wanted

 to

 or

 whatever,





right?

 So,

 that's

 where

 we

 are

 headed





like

 we're

 about

 to

 open

 source

 it

 very,





very

 quickly.





Uh

 very,

 very

 soon.

 So,

 yeah,

 pretty





excited

 about

 that.</details>

>> 好的，太棒了。很期待。开源总是一件好事。促进竞争，我想说。呃，你知道的，我想起来实际上 DeepSeek 宣布过他们打算在某个时间点做 DeepSeek code。所以，呃，但你知道，显然他们只会做 DeepSeek 的东西。

<details><summary>Original English</summary>>> Okay,

 excellent.

 Looking

 forward

 to





that.

 Open

 source

 is

 always

 good.





Follow

 competition,

 I'll

 say.

 Uh

 you





know,

 I

 I

 I

 was

 reminded

 that

 actually





Deep

 Seek

 announced

 that

 they're

 going





to

 do

 Deep

 Seek

 code

 at

 some

 point.





So,

 uh

 but,

 you

 know,

 obviously

 they'll





only

 do

 Deep

 Seek

 stuff.</details>

>> 关于这件具体的事情，很多评论都在说，比如，你知道的……呃，他们在艾特 DeepSeek 的人，问为什么你们不做自己的 code？

<details><summary>Original English</summary>>> So

 many

 of

 the

 comments

 on

 this





particular

 thing

 were

 about

 like,

 you





know,

 uh

 they

 were

 tagging

 Deep

 Seek





people,

 why

 are

 you

 not

 building

 your





own

 code?</details>

>> 对，对，对，他们宣布了。

<details><summary>Original English</summary>>> Yeah,

 yeah,

 yeah,

 they

 announced

 it.</details>

>> 然后他们……是的，在那之后他们确实，你知道，大概一周之后或什么时候，他们宣布我们正在为此招聘或什么的。所以，这很合理，对吧？但是，他们将只会支持 DeepSeek。3.7 max 出来的时候是目前 Command Code 上使用量第二大的模型。才出了两三天，对吧？

所以，是的。

<details><summary>Original English</summary>>> And

 then

 they

 Yeah,

 they

 did

 after

 that





like,

 you

 know,

 maybe

 a

 week

 later

 or





something,

 they

 announced

 that

 we

 are





hiring

 for

 that

 or

 whatnot.

 So,

 it

 makes





sense,

 right?

 But,

 they

 will

 only

 be

 for





Deep

 Seek.

 When

 to

 3.7

 max

 is

 the

 second





most

 used

 model

 on

 Command

 Code

 right





now.

 It's

 just

 two

 or

 three

 days

 old,





right?





So,

 yeah.</details>

>> 太酷了。

<details><summary>Original English</summary>>> Cool.</details>

>> 我们拭目以待。

<details><summary>Original English</summary>>> We'll

 see

 how

 it

 goes.</details>

>> 我们拭目以待。好的，那就祝一切顺利。呃，很高兴能聊聊，了解一下，你知道的，正在发生的一切。呃，我我我确实认为这里有一些挺好的想法，大家不管在做什么项目都可以借鉴。所以，我想呃这就是为什么我们要办这个播客，就是呃向大家学习，并努力对所有这些事情形成一份共同的、我想说是共享的知识。

<details><summary>Original English</summary>>> We'll

 see

 how

 it

 goes.

 Okay,

 well,

 all





the

 best.

 Uh

 it's

 great

 to

 catch

 up

 and





get

 a

 sense

 of

 like,

 you

 know,





everything

 going

 on.

 Uh

 I

 I

 I

 definitely





think

 there's

 some

 like





good

 ideas

 here

 that

 people

 can

 take





regardless

 of

 what

 project

 they

 work

 on.





So,

 I

 think

 uh

 that's

 why

 we

 do

 the





podcast

 is





uh

 learning

 from

 everyone

 and

 try

 to





have

 a

 common

 I

 guess

 shared

 knowledge





of

 all

 these

 things.</details>

>> 绝对是这样。

而且我会继续分享越来越多的内容。我认为每个人都可以学习。这不仅仅是……你知道的，你不一定非要在 command code 里使用这个想法。你只要想，就可以在任何代码 harness（测试/运行框架）中使用它，对吧？

只要我们都在进步，对吧？

是的。

好的，就到这里。

太棒了。

<details><summary>Original English</summary>>> Most

 definitely.





And

 I'll

 continue

 sharing

 more

 and

 more.





I

 think

 everybody

 can

 learn.

 It's

 not





just,

 you

 know,

 you

 don't

 have

 to

 use





this

 idea

 and

 comment

 code.

 You

 can

 just





use

 it

 in

 any

 coding

 harness

 that

 you





want,

 right?





As

 far

 as

 we

 are

 all

 improving,

 right?





Yeah.





Okay,

 that's

 it.





Awesome.</details>