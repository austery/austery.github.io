---
author: AI Engineer
date: '2026-07-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=7JgIS42mz7U
speaker: AI Engineer
tags:
  - software-security
  - ai-coding
  - memory-safety
  - vulnerability-detection
title: AI漏洞末日与默认安全：重构智能时代的软件信任链
summary: 随着前沿AI模型在漏洞挖掘与利用能力的指数级提升，软件安全正面临前沿大模型的严峻挑战。本文基于Corridor联合创始人Jack Cable的演讲，深入剖析了AI自主编码带来的安全隐患与上下文局限，阐述了CISA“默认安全”的核心原则，并提出了应对“漏洞末日”的三大政策建议，呼吁通过内存安全语言重构与自主防护体系来保障软件供应链的终极安全。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Corridor
  - CISA
  - Anthropic
products_models:
  - Mythos
  - Fable
  - Cursor
  - Claude Code
media_books: []
status: evergreen
---
### AI漏洞浪潮与开发模式的颠覆

在软件工程的历史演进中，**AI辅助编码工具**（AI coding tools）正在以超越以往任何软件类别的速度实现爆发式增长。根据Stack Overflow去年的统计数据，约有84%的开发者已将AI编码工具融入日常工作流，30%到40%的企业也在积极鼓励使用AI编码助手。然而，这一变革在极大地提升开发效率的同时，也带来了一个被称为**“漏洞末日”**（Bug Apocalypse）的严峻安全挑战。

前沿人工智能大模型（Frontier models）在漏洞发现与自动利用方面的表现日新月异。以Anthropic发布的**Mythos**和**Fable**模型为例，这些模型不仅具备极强的单点代码分析能力，更能自主执行复杂的**攻击链**（Attack chains）。这意味着，防御者面对的不再是静态的漏洞库，而是能够自动完成“发现-验证-利用”全流程的AI对抗网络。

与此同时，软件开发生命周期（SDLC）本身的自主化程度也在发生本质转型。现在的AI辅助开发已不再局限于传统的**代码自动补全**（Auto-complete），甚至超越了在**Cursor**或**Claude Code**等工具中与开发者进行单次交互的阶段。开发团队开始通过Slack等平台直接唤醒多个后台运行的自主智能体（Autonomous agents），实现大规模的异步并行开发。当AI成为默认的代码撰写者时，系统的攻击面正在以肉眼可见的速度急剧膨胀。正如Corridor的联合创始人兼CEO **Jack Cable**（曾任美国网络安全和基础设施安全局 CISA 的资深技术顾问）所指出的，防御者必须采用同等强度的AI赋能技术来强化自身系统，否则将在前沿大模型驱动的攻防对抗中迅速失去主导权。

<details>
<summary>Original English Source</summary>

```text
Hey there, I'm Jack Cable and today I'm going to be talking about the effects of the AI bug apocalypse. As you may have seen, frontier models are getting better than ever before at discovering and exploiting vulnerabilities in our software. Right, this is leading to what many are calling a bug apocalypse where we're finding more and more vulnerabilities, particularly in the open-source libraries that power um all of the software we rely upon. Right, so today I want to break down what exactly is happening and how defenders can get ahead of the exploitation that is occurring.

As far as my background, right now I'm the co-founder and CEO at Corridor, a company I started about 18 months ago focused on securing AI coding. Before this, I served as a senior technical advisor in government at CISA, the Cybersecurity and Infrastructure Security Agency, where I worked with top software companies to help them build their products to be more secure by design. I'm also an ethical hacker. I got into the top 100 rank of hackers on when I was in high school. I studied computer science at Stanford. So I've seen firsthand how these simple, you know, repeat classes of vulnerabilities can be introduced and exploited and have been um close participant right in many of the the most recent um advancements and seeing just what this means uh for both our adversaries as well as defenders.

Just to set the stage, right, as everyone here knows, I imagine AI coding tools are scaling faster than any software category in history. Cursor, Copilot Code um grow exponentially and with that, right, also comes these improvements in how frontier models can find and exploit vulnerabilities. Um so we're seeing, right, both ends of the equation shifting. On one hand, um models can do better job finding vulnerabilities. On the other hand, our attack surfaces are growing immensely, right, as AI becomes the default code writer.

Um so, what I want to explore in this talk, right, is how do we balance that? How do we make sure that we're not going to have immensely more vulnerabilities than we've ever had before, right? And just to to give some sense, right, I'll move myself here of um some of the statistics, right, um pulled some from last year where about 84% of developers were using AI coding tools, 30 to 40% of companies encouraging use of AI coding assistants. That was from Stack Overflow, right? I don't I haven't seen the latest numbers this year, but what I would expect once those come out, right, is that is the vast, vast majority of developers and companies who are using coding agents, right? And part of this is the increasing level of autonomy by which these coding agents are being used. It's no longer, you know, auto complete, often it's not even a developer synchronously within cursor. Um right, when we do our own development, right, now it's um spinning up agents from within Slack or wherever folks are working and having many agents run at once in the background. Um this is a tremendous shift in how software is being built, um and at the same time, right, like I mentioned, the frontier models are getting significantly better. Um and you can look at it from, you know, pretty much any part of the cyber attack chain, ranging from finding vulnerabilities where models can, you know, now do do, you know, significantly better than even I could, and you know, I've I've reported hundreds of vulnerabilities to various companies.

Um so, everything from finding vulnerabilities to exploiting them. Uh this is a chart here that comes from Anthropic, right, showing Mythos compared to a number of um other models that they and others have put out. Um and we can see that we're we're seeing quite rapid advancements in models' capabilities, right, And and particularly to execute more kind of autonomous attack chains.
```

</details>

### 默认安全与内存安全革命

在建立这种心理防线后，具体的防御策略不应流于表面的“打地鼠”式修补，而必须回归**“默认安全”**（Secure by Design）的系统性重构。事实上，即使是像Mythos这样先进的前沿AI大模型所发掘的漏洞，绝大多数也并非全新漏洞。MITRE列出的“已知被利用漏洞”（Known Exploited Vulnerabilities）目录显示，缓冲区溢出等经典漏洞类型在业内已存在数十年，而防范它们的手段也早已成熟。

要从根本上消除这些顽疾，最有效的途径是全面转向**内存安全语言**（Memory-safe languages：能够自动管理内存，消除缓冲区溢出等安全缺陷的编程语言，如 Rust、Go）。非内存安全语言（如 C、C++）在底层逻辑上无法提供原生保护，而约60%到70%的软件漏洞本质上都可以通过改用内存安全语言来完全避免。

业界对此已积累了扎实的实证数据。**谷歌**（Google）、**微软**（Microsoft）以及**亚马逊**（Amazon）等科技巨头，甚至包括Linux内核社区，都在积极用Rust重构其关键的基础设施代码。以谷歌的Android系统为例，其内存安全漏洞的占比已从2019年的约75%大幅降低至2022年的30%左右。令人瞩目的是，谷歌并没有对存量代码进行全面重写，仅仅是确保**所有新写入的代码**采用内存安全语言，便取得了如此显著的防护成效。

这说明，防御者应当摒弃将数百万美元砸在开源库零散补丁上的低效做法，转而通过一次性重构（One-time rewrite）建立高壁垒的系统安全性。只要在底层获得了程序设计的数学与编译期保证，即使未来的AI模型变得再聪明、其漏洞挖掘能力再强，也将无法在物理机制上攻破这些经过内存安全重构的系统防线。

<details>
<summary>Original English Source</summary>

```text
So, as we think about adversaries who are using these models, right? They're not just going to be discovering vulnerabilities, but they're going to be automating every part of the attack process. So, it's our job, right? As defenders to understand, okay, what are the points where we can make software systems more resilient to all of these attacks. Right? And to me, this brings back a lot of the work that I was doing in government around the the secure by design initiative, right? Um and so so the overall question, right? That I'm worried about is how can we make sure that frontier AI models aren't introducing exponentially more vulnerabilities over time, right? Um even pre-AI, we've had this you know, uh heavy increase in common, relatively simple classes of vulnerabilities that are being exploited by adversaries. AI is making this significantly easier, right? So, I think the only way that we're going to to win as defenders is if we use the the same techniques, right? To harden our systems. Um and I would say that there is good news here, right? That a lot of the vulnerabilities, pretty much all of the vulnerabilities that even frontier AI models are finding aren't anything new. Yes, it's new that uh given vulnerability was found in a you know, specific file with with a piece of software, but that vulnerability class um isn't necessarily novel. Um and and we can actually use that to our advantage, and I'll I'll get into that.

Um right? So so overall, um the the thesis here is that um right? We are seeing both attackers get more tools in their toolkit, and the same time, the way in which software is being built is fundamentally changing. Um so so really the question then becomes how can we apply AI to shore up on software systems?

Um right, and I want to to take a quick detour um to some of the secure by design work that that I I kicked off with with others in government. Um right, this is a paper that we put out in March of 2023. So, just as you know, LLMs were starting to become more readily available, but um right, their application in coding at that time wasn't much more than, you know, auto complete. And while that's useful, it wasn't necessarily the step change that we have now. Um and what we focused on kind of laying out with this vision, right, was this idea that it it isn't really rocket science when it comes to preventing vulnerabilities in software, right? While it's true that it's hard to build a perfectly secure system, we do know how to build systems that are fundamentally more resilient to common classes of vulnerabilities. Um and and just to, you know, make this concrete, um this is a set of vulnerability classes coming from MITRE. It's the uh top classes that are um exploited in CISA's known exploited vulnerabilities catalog, right? And if you go down this list, you'll you might notice, right, that pretty much all of these are basic types of vulnerabilities that not only have we known about for decades, but we've known how to prevent at scale for decades, right? Uh take buffer overflows, right, number two on that list. Um and by the way, these are the same vulnerabilities that models like Mythos are finding in software. Um and buffer overflows were first documented um about um I believe 30-plus years ago, right? Um so we've had uh documented instances of how to find and exploit these vulnerabilities, and we also now have languages that are memory safe, right? Languages like Rust, Go, pretty much any language um that that's not C or C++ um is built in a way such that it's impossible to introduce memory safety vulnerabilities, right? They have guarantees that prevent those from being introduced.

So we have techniques by which we can prevent them and yet they continue getting introduced over and over again, right? So so let's look at memory safety for instance. There's you know the statistics range but approximately 60 to 70% of vulnerabilities in products written in memory unsafe languages can be completely prevented using memory safe languages, right? And this is you know based on CV data out there and not only that right we've seen a lot of companies Google, Microsoft, Amazon even you know open source software the Linux kernel is being rewritten in parts in rust. We've seen real evidence that by shifting to memory safe languages you can reduce overall vulnerabilities, right? On the right here is a chart from Google showing the rate of memory safety vulnerabilities over time in the Android operating system. What's interesting right is that this isn't even you know they're they're not even necessarily rewriting code in a memory safe language. They're just writing new code in a memory safe language and even then right the percent of memory safety vulnerabilities has dropped quite dramatically from you know about 75% in 2019 to maybe 30% in 2022. So to me that's personally quite exciting, right? Because it means that's not a given that we're going to continue having these basic vulnerabilities over and over again, right? And in part of the you know high-level policy conversation I think as a result has to be not just how can we deploy these frontier models to find one-off vulnerabilities in software that is something that we should be doing but at the same time, right, I don't want to miss out on opportunities to make our software fundamentally more secure. Right, we could pour millions of dollars into essentially playing whack-a-mole with vulnerabilities and patching them one-off in some of the open-source libraries that we all rely on, or we could do a one-time rewrite, for instance, to move some of these critical libraries into a language like Rust, right? And then that will pay dividends for years to come. So this is really at the core of how I'm thinking about this, right? Is what are some of the fundamental changes that companies, that open-source developers can be making that can reduce exploitation both by models today, right, and models to come. Cuz the advantage, right, of doing a rewrite, for instance, is that if you have some of these fundamental guarantees, then even if the models get smarter, right, Rust has programmatic guarantees such that we know that memory-safe D vulnerabilities in no circumstances won't be possible to be introduced or discovered. Right
```

</details>

### AI自主编码的隐患与上下文局限

然而，在AI代理程序高度自治的今天，大模型本身在编码过程中也在频繁引入新的漏洞。学界评估大模型编码缺陷的**Backsbench**基准测试（由苏黎世联邦理工学院 ETH Zurich 和加州大学伯克利分校 UC Berkeley 的研究者共同建立）表明，即使是市面上最优秀的大模型，在编写代码时引入安全漏洞的概率依然高达20%到40%。

这种现象的底层成因主要有两个维度。首先，AI模型是在人类既有的开源代码库上进行训练的，而人类历史上的代码本就充满了各种安全缺陷；其次，也是更关键的一点，现代软件开发中的漏洞正逐渐从“单行代码错误”演变为高度复杂的**上下文关联缺陷**（Contextual issues），例如涉及企业内部特定业务逻辑的**越权漏洞**（Authorization bugs）。

例如，前述的Opus 46模型在编写智能合约时，曾因忽视上下文业务逻辑引入了一个漏洞，最终导致数百万美元被盗。由于这些漏洞直接与企业私有的业务架构和威胁模型（Threat model）相关联，即使模型拥有再强大的通用智能，在缺乏特定上下文信息的情况下，也极易写出不安全的代码。

为了应对这一挑战，软件工程团队正从“自动补全”向在Cursor和Claude Code等IDE中进行同步开发的“智能体阶段”迈进，并在未来6到12个月内，实现由AI代理来主导绝大部分的代码审查（Code review）。对于企业安全团队而言，单纯的禁止和阻断是不可行的，因为开发提速的商业诉求永远是第一优先级。唯一的出路是设计强有力的安全护栏（Guardrails），让AI代码在合并前通过自动化的检测机制，为工程团队的敏捷开发保驾护航。

<details>
<summary>Original English Source</summary>

```text
and all of this comes in the context, too, of the fact that AI is increasingly capable at, of course, both writing code and then introducing vulnerabilities. You might have seen a couple months ago one example where Opus 46, right, by all accounts a very smart model, introduced a vulnerability in a smart contract that led to a couple million dollars being stolen, right? So so while the models are very smart and capable, often times security is very contextual. And the model just might not have the context in order to know that it's introducing a vulnerability, right? And this is reflected in academic benchmarks. One, for instance, here, Backsbench, you can find that at backsbench.com by researchers at ETH Zurich, UC Berkeley, uh finds that even the best models introduce vulnerabilities about 20 to 40% of the time when writing code. Right? Um and this shouldn't necessarily come as a surprise. Um for one, right? Models are trained on all of the world's existing code, and humans haven't been great at not introducing vulnerabilities in code in the past. But two, right? Increasingly, and this kind of lines up with some of what we're seeing among our customers, is that the vulnerabilities being introduced are often and less so the basic one-liner vulnerabilities, and more so contextual issues. Right? Things like authorization bugs that require an in-depth understanding of a company's business logic. Um and that's something, right? Even if the model's very smart, it's not being trained on your company's proprietary information or how your own um kind of, you know, threat model works. Um and that is why, you know, I believe we're still seeing quite a high rate of vulnerability introduction um even by um, you know, by by all accounts very intelligent models.

Um so so let's now think about, okay, given that the vast majority of software development is being done with AI, how can we make sure that AI is capable of writing secure-by-design software? Right? And part of this is a shift we're seeing in the level of autonomy um that AI is um now given when it comes to software development tasks. Right? We're kind of moving up this ladder that started with auto-complete to you know, agents within Cursor, Claude Code that can synchronously produce code, to now increasingly these autonomous agents that can work for an hour, hours at a time, and produce quite large code changes. Of course, the next step then becomes agents that are reviewing code. Um and we we at Quarter believe that, you know, within the next 6 to 12 months, the majority of code that is being shipped will be reviewed uh not by human but by AI. Um I think that's just a kind of natural consequence of the rate at which companies need to move, given that code review is not is now the bottleneck and I don't think we're going to accept that for very long. Um so really, right, our perspective at Corridor is around preventing vulnerabilities before the pull request, um as well as giving visibility into how AI coding tools are being used. Um and I think that's really essential, right, is that security cannot be the blocker when it comes to companies accelerating their development, right? Um acceleration is always going to win out. Um so when we talk to security teams, the conversation is less around should you allow your, you know, development teams access to coding agents? The answer is obviously yes, right? It's more around how can you do that with guardrails in place, right? Because what we're seeing is that without guardrails, yes, the coding agents can introduce vulnerabilities, um and in order to get to a point where, you know, development can be more autonomous, that code can start to be reviewed um by AI and merged in without as much human oversight, we really need to have tooling in place that allows security teams to have that assurance, um and to to give the blessing to their their engineering team to accelerate.
```

</details>

### 地缘竞争、开源生态与国会政策建言

从国家政策与地缘政治竞争的宏观视角来看，前沿大模型的管制正成为攻防博弈的新战场。此前，美国政府针对Mythos和Fable等模型实施了严格的出境限制。然而，Jack Cable与Mikayla Gyalcsamis等安全专家曾联名向白宫致信，呼吁放开此类限制。其核心论据在于，这类**双重用途模型**（Dual-use models）对防御者的正面赋能效用要远超其被滥用的风险。

当前，闭源前沿模型与开源模型之间的代差正在通过**知识蒸馏**（Distillation attacks）等技术手段迅速被抹平，对手早已通过各种管道获得了极强的AI自动化攻击能力。在这种背景下，美国国会及相关决策机构应当重点采取以下三大行动：

1. **阻断增量风险**：制定并推广开发规范，确保政府和企业在开发新系统时，从源头上使用内存安全语言写出“默认安全”的代码。
2. **重塑开源基石**：由于开源软件是对手进行漏洞漏洞挖掘和武器化测试的天然演练场，必须由政府和私营企业共同注资，系统性地对关键开源基础库进行Rust化重构，彻底终结“打地鼠”的补丁模式。
3. **培育开源模型生态**：积极扶持本土**开放权重模型**（Open-weight models）的良性发展，允许企业针对特定系统进行精细化微调（Fine-tuning），以此建立由本土技术主导的安全防御生态。

通过这些举措，防御方才有可能将大模型从潜在的破坏性武器转化为筑牢数字空间安全长城的战略盾牌。

<details>
<summary>Original English Source</summary>

```text
Um I I want to close with some of the policy perspective, right? And um this is in part tied to the recent export controls on Mythos and Fable models, right? As part of a letter uh led by Mikayla Gyalcsamis, um where we urged the White House to lift the export controls on these models. And the perspective there is that the benefit to defenders far outweighs the risk, right? These are very powerful and let's face it, right, dual-use models that can both be used to secure systems and also um to exploit them. Uh to Anthropic's credit, they have done a lot of work with the Fable release, right, to have some safeguards in place such that um they're more skewed towards defenders than than adversaries. Um but this is also coming in the face of, right, increasingly powerful open-weight models. Um you've probably seen, you know, documented um distillation attacks um where open-weight model providers can train on the output of um closed-weight models and that um as a result is quickly shrinking the, you know, timeline between when a frontier closed-weight model comes out and when open-weight models catch up to that. Um so whether we like it or not, right, adversaries already have access to incredibly powerful models um and they're already using them today to exploit systems, right? So to me it becomes more question of how can we rapidly um get the kind of capabilities in the hands of defenders and I think that requires having these models be more widely available.

Um one cool thing I had the opportunity of doing a couple weeks ago was testifying to uh the US Congress um on the, you know, risks of both uh frontier models as well as AI coding. Um my recommendations had a couple elements, right? One was to prevent vulnerabilities in new code going forward. I think this is something that both every company as well as the US government should be focusing on and making sure that as development accelerates, right, security isn't being left behind there. Um second is to harden the open-source foundation. Um this is incredibly important, right, especially since open-source software is going to be the kind of proving ground for a lot of adversaries, right, who want to test out these models and exploit vulnerabilities they find due to, right, the exact nature that's open-source. So, so you can just go and run a very smart model on them and in all likelihood find many novel vulnerabilities. Um so, so I think both the US government, but then private companies as well have a responsibility to help shore this up. And like I mentioned, right, it's not just about one-off, um you know, vulnerability discoveries or patches. It really has to be more systemic and start to get into um rewrites that can fundamentally reduce the risk of vulnerabilities that can be found whether by models today or in the future. Um and then the last area of my recommendations were to foster an ecosystem of American weight made open-weight models, right? I think in order for us to stay competitive here, it can't just be closed-weight models alone, right? Um there's a number of reasons here, you know, one of those is that for many companies, while there's a place for for closed-weight models, you also might want to do things like fine-tuning models. Um and that is only possible with an open-weight model. Um so, so I think it is really essential, right, that um we have frontier open-weight models coming out of the United States. We haven't seen as much of that to date, um but I think that's a critical element of American competitiveness when it comes to AI.

Um so, so that those were my overall recommendations, right? And of course, all of this is in the context of these increasingly powerful models. The hearing was, I believe, a few days before, you know, um Mythos and Fable came out. Um and then, of course, all of the um export control um actions that were taken. Um so, this is an incredibly rapidly evolving space, but I think that's why it's all the more important to go back to the basics, right? What are the fundamental controls that can protect against um any vulnerabilities that can be discovered by models today or in the future? And I think that's where we really ought to be spending our time using these models um to make our systems more resilient. Um, so that's my talk. Um, happy to be reached. My email's here and thanks everyone for tuning in.
```

</details>