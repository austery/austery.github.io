---
author: Anthropic
date: '2026-04-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=INGOC6-LLv0
speaker: Anthropic
tags:
  - cybersecurity
  - llm-code-generation
  - vulnerability-detection
  - autonomous-research
  - ai-for-good
title: AI赋能网络安全：Claude Mythos Preview与Project Glasswing开启软件防御新纪元
summary: 本文深入探讨了AI在网络安全领域的革命性潜力，重点介绍了Claude Mythos Preview模型在代码生成和漏洞发现方面的卓越能力。通过Project Glasswing，OpenAI正与关键组织合作，利用AI提升软件安全性，防范日益增长的网络威胁，旨在共同构建一个更安全的数字未来。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - Claude Mythos Preview
media_books: []
status: evergreen
---
### 软件漏洞的普遍性与开发者日常

大多数日常使用软件的人，并不会过多地去思考软件中的“**bug**”（缺陷）。他们更不会去设想，一旦他们所依赖的软件突然变得不那么安全时，会发生什么。而对于软件开发者而言，处理这些潜在的安全风险是他们每天都要面对的现实。软件本身就一直存在各种**缺陷**与**漏洞**，这一点并非新鲜事。对普通用户而言，这些bug在大多数情况下是难以察觉的，因为一旦被发现，它们通常会被修复。

<details>
<summary>Original English</summary>

Most people who use software
every day don't think about bugs.
They don't think about
what can happen if the software
that they depend upon
suddenly is less secure.
That's something that software developers
have to deal with every single day.
Software has always had flaws
and vulnerabilities.
That's not new.
For an average person,
the bugs are, by and large,
not something they notice
on a daily basis, because if they do,
they get fixed.

</details>

### 关键漏洞的放大效应与LLM驱动的网络安全革新

然而，每隔一段时间，会出现一些**漏洞**，它们会产生真实且严重的影响，其危险性被数倍放大。这种情况可能源于一个单独的bug，它悄无声息地渗透进**共享软件**中，而这款软件被成千上万的**不同产品或网站**广泛使用。一个原本孤立的问题，就这样在全球范围内被成倍地放大。历史上，发现并修补这些漏洞一直是一个缓慢、耗时且成本高昂的过程。如今，随着**大型语言模型（LLM）**能够编写代码，并且其水平能媲美顶尖的软件开发者，它们同样能被用来**发现bug**并**利用软件漏洞**，其效率不亚于顶尖的攻击者。这些模型所具备的能力，正从网络安全的角度**提高了门槛**，既能赋能防御者，也可能赋能攻击者。

<details>
<summary>Original English</summary>

But then every so often,
there are vulnerabilities
that have real severe impacts.
Like one single bug
that works its way into shared software
that many, many, many
different products or websites use.
One issue just gets
magnified out around the world.
Historically, finding
and patching vulnerabilities
has been a slow, time-consuming,
and expensive process.
If LLMs are now able to write code,
at the level of some of the greatest
software developers in the world,
it can also be used to find bugs
and exploit that software
equally effectively.
These models have capabilities
which are raising the bar
from a cybersecurity point of view
with their ability to help defenders
as well as potentially help adversaries.

</details>

### Claude Mythos Preview：AI驱动的网络安全新飞跃

我们近期开发了一个名为“**Claude Mythos Preview**”的新模型。在项目早期，我们便清晰地认识到，该模型在**网络安全能力**方面将会有显著的提升。虽然模型的能力增长呈现出一种**高加速的指数级曲线**，但在这一曲线上，存在着一些尤其重要的**关键节点**。而“Claude Mythos Preview”正是沿着这个指数曲线，实现了一个**尤为显著的飞跃**。我们并未专门训练它以精通网络安全，而是将其训练得在**编写代码**方面表现出色。然而，作为精通代码能力的**副产品**，它也同样擅长网络安全相关的任务。目前我们正在实验的这个模型，在**识别bug**方面，已基本达到**专业人类开发者**的水平。这对我们来说非常有益，因为这意味着我们可以**更早地发现更多漏洞**，并**及时修复**它们。

<details>
<summary>Original English</summary>

We recently developed a new model,
Claude Mythos Preview.
Early on, it was clear to us
that this model
was going to be meaningfully better
at cybersecurity capabilities.
There's a high accelerating exponential,
but along that exponential,
there are points of significance.
Claude Mythos Preview
is a particularly big jump
along that point.
We haven't trained it
specifically to be good at cyber.
We trained it to be good at code,
but as a side effect
of being good at code,
it's also good at cyber.
The model that we're experimenting with
is by and large as good
as a professional human at identifying bugs.
It's good for us
because we can find
more vulnerabilities sooner
and we can fix them.

</details>

### 漏洞链式利用与模型的自主性

更进一步，该模型还具备**将多个漏洞串联起来**的能力。这意味着，即使是两个单独存在、各自影响力有限的漏洞，该模型也能够将其组合，创建出能够产生**高度复杂结局**的**利用链**，有时甚至能串联起三、四、乃至五个漏洞。我们认为，该模型之所以能够出色地完成这项任务，是因为我们注意到它表现出**高度的自主性**。它在**追寻长周期任务**方面表现得更为出色，这些任务类似于**人类安全研究员**在一整天的工作中所进行的探索。

<details>
<summary>Original English</summary>

It has the ability to chain
together vulnerabilities.
What this means
is you find two vulnerabilities,
either of which doesn't really get you
very much independently,
but this model is able to create exploits
out of three, four,
sometimes five vulnerabilities
that in sequence
give you some very sophisticated
end outcome.
And we think that this model
can do this really well
because we noticed that this model
is very autonomous.
It's just generally better at pursuing
really long-range tasks
that are kind of like the tasks
that a human security researcher
would do throughout the course
of an entire day.

</details>

### 负责任的发布与Project Glasswing：共筑数字安全长城

显而易见，如此强大的模型能力，若落入不法分子之手，可能造成**巨大危害**。因此，我们决定**不广泛公开发布**此模型。我们深知，未来将有更多、更强大的模型出现，无论是来自我们公司还是其他机构。因此，我们必须制定一个**应对策略**。为此，我们启动了**Project Glasswing**（玻璃之翼计划）。该计划旨在与众多负责维护**全球关键代码**的组织建立伙伴关系，将模型提供给他们。通过这种方式，我们能够让他们了解如何利用此类模型来**降低风险**并**保护大众**。通过**率先向这些软件开发者提供先进工具**，相当于给我们所有人一个**集体性的先发优势**。这使我们能够发现以往无法察觉的问题，并**更快速地修复它们**。

<details>
<summary>Original English</summary>

Obviously, capabilities in a model
like this could do harm
if in the wrong hands,
and so we won't be
releasing this model widely.
More powerful models are going to come
from us and from others,
and so we do need a plan
to respond to this.
That's why we're launching
what we're calling Project Glasswing,
where we partner
with a number of the organizations
that power some of the world's
most critical code
to put the model into their hands
to allow them
to look at how they can use models
like this to bring down risk
and protect everyone.
And by giving these software developers
advanced tools before anyone else,
it gives all of us
a collective headstart.
It allows us to find things
that we couldn't find before,
and it helps us fix these things
much more quickly.

</details>

### 实战漏洞挖掘：开源系统安全检测成果

通过与合作伙伴的协作，我们在**几乎所有主流平台**上都发现了漏洞。在过去几周内，我发现的**bug数量**，已经超过了我**一生中发现的总和**。我们利用该模型扫描了大量**开源代码**，首要的目标是**操作系统**，因为它们构成了**整个互联网基础设施**的基石。

*   **OpenBSD**: 我们发现了一个存在了**27年**的bug，攻击者只需向任何OpenBSD服务器发送少量特定数据，即可导致其**崩溃**。
*   **Linux**: 我们发现了一些**权限提升漏洞**，这意味着一个**没有权限的用户**，只需在自己的机器上运行某个特定二进制文件，就能**把自己升级为管理员**。

对于我们发现的每一个bug，我们都已通知了**软件维护者**。他们已经**修复了这些问题**，并**部署了补丁**，从而确保运行该软件的用户**不再易受这些攻击的威胁**。

<details>
<summary>Original English</summary>

Working with our partners,
we've been finding vulnerabilities
across essentially every major platform.
I found more bugs
in the last couple of weeks than I found
in the rest of my life combined.
We used the model to scan
a bunch of open-source code
and the thing that we went for first
was operating systems
because this is the code that underlies
the entire internet infrastructure.
For OpenBSD,
we found a bug that's been present
for 27 years, where I can send
a couple of pieces of data
to any OpenBSD server
and crash it.
On Linux, we found a number
of vulnerabilities
where, as a user with no permissions,
I can elevate myself to the administrator
by just running some binary on my machine.
For each of these bugs,
we told the maintainers
who actually run the software about them,
and they went and fixed them
and have deployed the patches
so that anyone who runs this software
is no longer vulnerable to these attacks.

</details>

### 开发者赋能与国家安全：软件安全乃社会安全之基

对于那些**孜孜不倦地维护软件**的开发者而言，一个能够帮助他们**发现自身代码中潜在漏洞**，并在这些漏洞被利用之前就**完成修复**的模型，无疑是一个**无价的工具**。我们已与**美国政府**的官员进行了沟通，并主动提出合作，共同**评估这些模型的风险**，并**协助抵御其潜在威胁**。我们如今生活的方方面面都**依赖于软件**。“软件吞噬了世界”，我们生活的每一个**模拟化方面**，都以某种方式在**数字领域**得到了体现。因此，我们**日常生活**的运行，都建立在我们能够**信赖**其背后**驱动系统**的理念之上。

**网络安全**，即是我们**社会的安全**。因此，**促进行业间的合作**，共同**构建更强大的防御能力**至关重要。**没有哪个单一组织**能够看到全局并独立解决这个问题。这绝非一蹴而就的短期项目，它需要**数月，甚至数年**的持续努力。但我真心希望，在这一切完成后，我们能够达到一个**新的安全水平**，使**全球的软件、客户数据、金融交易以及关键基础设施**都比以往**更加安全**。

<details>
<summary>Original English</summary>

For a developer who tirelessly
maintains software,
a model that can help them
discover vulnerabilities in their own code
and fix them before they can be exploited,
that is an invaluable tool.
We've spoken to officials
across the US government,
and we've offered to work with them
and collaborate to assess the risks
of these models and to help defend
against the risks of these models.
Everything that we do in our lives now
depends on software.
Software ate the world.
Every analog aspect of our life is
somehow represented in the digital domain.
And so all of our daily lives run
on the idea that we can rely on
the systems that power them.
Cybersecurity is the security
of our society.
It is essential that we come together
and work together across industry
to help build
better defensive capabilities.
No single organization
sees the whole picture
and can tackle this on their own.
This is not going to be done
as part of a few week program.
This is going to be the work
of certainly months, perhaps years.
But what I do hope
is at the end of this,
we can be in a position
where the world's software,
its customer data,
its financial transactions,
its critical infrastructure
are safer than they were before.

</details>