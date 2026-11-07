---
author: Internet of Bugs
date: '2026-04-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=urkVFZAhz3U
speaker: Internet of Bugs
tags:
  - cybersecurity
  - responsible-disclosure
  - compute-costs
  - ai-safety
  - vibe-coding
title: Claude Mythos 的危险神话：Anthropic 斥资数亿的公关秀
summary: 本文深度解析了 Anthropic 发布的“Project Glasswing”及其背后的 Claude Mythos 模型。作者指出，所谓“因过于强大而拒绝发布”本质上是 AI 行业惯用的公关策略。通过拆解其找虫成本发现，其安全突破更多源于数千万美元的算力投入而非模型能力的质变。文章警示，AI 虽然能优化特定安全场景，但距离真正的“AI 软件工程师”仍有巨大鸿沟。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - HackerOne
products_models:
  - Claude Mythos
  - Project Glasswing
  - ChatGPT-5
  - Devin
media_books: []
status: evergreen
---
### 饥饿营销：被神话的“Claude Mythos”与危险论调

AI 评论界似乎再次陷入了集体疯狂。这次的焦点是 **Anthropic** 宣布的一项名为“**Project Glasswing**”的计划，以及其底层模型 **Claude Mythos**。官方声称该模型极其强大且危险，因此决定不向公众发布。这种论调在社区中引发了极端对立：一方认为这是负责任的表现，保护了网络安全；另一方则嗤之以鼻，认为这不过是一场公关噱头。

事实上，这两者皆有道理，但最核心的真相往往被掩盖了：模型本身的性能可能是整件事中最不相关的部分。随着 AI 公司为了维持投资现金流的持续注入，这种通过“由于过于强大而无法发布”来博取关注的手法正变得越来越普遍。这不仅是吸引注意力的技巧，更是 AI 公司在烧钱竞赛中维持热度的救命稻草。

<details><summary>Original English Source</summary>
So, the AI commentator community seems to have lost its ever-loving mind. Again. This time, it's about a new announcement about Anthropic's new "Project Glasswing" and the underlying Claude Mythos model that they say they're not releasing because they say it's too powerful. Some people are saying this is incredibly dangerous and it's very good that Anthropic is holding off on the release, and other people are saying this is just a publicity stunt. Here's the reality: Both of those things are true. Well, to an extent. Kind of. We'll get into it. One thing is, the model itself is probably the least relevant part of the whole thing. And the publicity stunt part? We've been seeing a lot of this particular attention grabbing technique lately. I'm sure it's only going to be getting worse as the AI companies get more desperate to keep up the investment dollars flowing so they can be shoveled into the fire.
</details>

### 负责任披露 vs. 公关操弄：行业惯用的狼来了故事

**Anthropic** 宣称 Claude Mythos 在发现和利用漏洞方面过于出色，甚至能重塑网络安全，因此必须联合各大科技巨头共同保护关键软件。然而，这种“先造神、再藏神”的模式在业内早已屡见不鲜。**OpenAI** 曾通过少数受选者提前体验 **ChatGPT-5** 并通过他们的口赞誉其神奇，结果在公测后因缺乏客观一致的好评而不得不收回言论；类似的案例还有号称“首位 AI 软件工程师”的 **Devin**，其演示视频后来被证实存在严重的夸大其词。

如果一个公司真的担心安全影响，最负责任的做法应该是遵循**负责任的披露**（Responsible Disclosure: 安全专家发现漏洞后先通知厂商并协助修复，待修复完成后再对外公布）原则，秘密地协助修复这些漏洞，而不是在漏洞尚未完全解决时大肆宣扬模型有多么“危险”。**Anthropic** 的做法显然违背了这一原则，这进一步印证了其公关动机高于安全考量的本质。

<details><summary>Original English Source</summary>
The short version is: Anthropic announced that they have this new model they're calling Mythos, but they say it's too dangerous to release it to the public. It is so good at finding and exploiting bugs, they say, that they "believe it could reshape cybersecurity" so they created something they're calling "Project Glasswing" in conjunction with a bunch of big tech firms quote: "in an effort to secure the world's most critical software" unquote. Bragging about an AI product that you haven't actually released is a pretty common pattern. OpenAI let a select few people have early access to ChatGPT-5, and many of them reported how fantastic it was! And then they had to walk it back after it was released. A similar thing happened with DEVIN the so-called "first AI software engineer" where they released some demo videos and quotes from people that they had handpicked to show it to, and then the demos turned out to have been greatly exaggerated. If it was really as dangerous as they're saying, then a responsible company - unlike Anthropic - would just shut the hell up about it until all the bugs the new AI had found had been fixed. That's called "responsible disclosure".
</details>

### 算力堆砌的“幻觉”：漏洞挖掘的真实成本分析

AI 公司最擅长的一种欺骗手段是将“投入的资金与努力”伪装成“模型的原生能力”。例如，**Anthropic** 宣称其模型发现了 **OpenBSD**（一种极其安全的操作系统）中的拒绝服务漏洞，但代价是运行了上千次、耗费了约 2 万美元的算力；在 **FFmpeg** 上的找虫成本也高达 1 万美元。如果我们将这一成本推广到其声称发现的数千个漏洞中，总投入可能高达数千万甚至上亿美元。

对比之下，全球最大的漏洞赏金平台 **HackerOne** 每年的总支出约为 8000 万到 9000 万美元。而 **Project Glasswing** 仅为合作伙伴提供的算力赠送就达 1 亿美元。研究表明，如果将同样的算力和时间花费在更小、更便宜的**开源模型**上，也能得到类似的结果。这意味着，Claude Mythos 所谓的“神迹”并非源于某种不可思议的智慧进化，而仅仅是由于它拥有极高的试错预算。**Anthropic** 本该说“我们投入巨资让互联网更安全”，但他们却选择了更有煽动性的说法：“看我们的模型多危险，你们必须对此感到敬畏”。

<details><summary>Original English Source</summary>
AI companies have started trying to get you to confuse effort and money for model ability. They took some of the more celebrated bugs that Anthropic says the new model found and they tested them on small, cheap, open-weight models, and got very similar results. That's a very strong evidence that the new model isn't the real story here. So here's an excerpt from an Anthropic blog post about the denial of service bug they found in OpenBSD. They say that the bug was found after a thousand runs at a cost of around twenty thousand dollars. Likewise they spent ten thousand dollars to find a bug in FFmpeg. The biggest bug hunting program in the world, HackerOne, spends something like eighty to ninety million dollars a year total. "Project Glasswing" is spending 125% of that just in compute for their partner companies. Anthropic should absolutely be commended for that. But they're not saying "we spent a ton of money making Internet safer for you" they're saying "look how dangerous and powerful our new model is - you should be in AWE of it" and that's just not the reality here.
</details>

### 封闭博弈与通用工程：AI 的安全“边界”

**Anthropic** 刻意回避了一个事实：这种基于明确成功标准（如“是否发现漏洞”）的离散任务，与人类日常处理的含糊不清的现实世界问题之间存在巨大鸿沟。训练 AI 寻找漏洞更像是在教它下**国际象棋**（Chess: 具有明确规则和获胜条件的封闭博弈），这与通用的**软件工程**完全是两回事。英国 AI 安全研究所对该模型的“**夺旗赛**”（Capture the Flag: 网络安全竞赛）测试也印证了这一点：虽然它在有明确规则的 hacking 任务中表现出色，但这种表现并不意味着它具备了通用软件构建的能力。

对于普通用户来说，这意味着我们可能会迎来一段频繁收到系统更新和漏洞新闻的动荡期，因为新工具的发布必然会引发一波修复浪潮。从好的方面看，AI 确实为对抗所谓的“**氛围编程**”（Vibe Coding: 指依赖直觉而非严谨逻辑进行的编码，往往会产生大量安全漏洞）提供了新武器。但这绝非万能钥匙，它能有效识别缓冲区溢出或权限提升等经典漏洞，但对于逻辑错误、数据损坏、同步错误或糟糕的用户界面等深层问题，AI 依然束手无策。

<details><summary>Original English Source</summary>
There is a big difference between discrete tasks with well-defined success criteria and the ambiguities that we as humans deal with all the time. This is much more like the way that an AI is taught to be good at chess than it's training for human equivalent general intelligence. The AI Security Institute in the UK ran it against a number of their "Capture the Flag" scenarios. It did pretty well, but these are more like playing chess or go than general software building. Expect a lot of security updates for your phones, tablets and laptops for a while. It also means that - finally - AI has given us something that might help counteract all the nightmare security holes that vibe coding is creating. It's not a silver bullet though. Finding and preventing things like buffer overruns or remote access is great, but there are a lot of other kinds of bugs that aren't so easy to look for, like logic errors, data loss, or synchronization errors. We're still a very long way from a "true AI software engineer".
</details>