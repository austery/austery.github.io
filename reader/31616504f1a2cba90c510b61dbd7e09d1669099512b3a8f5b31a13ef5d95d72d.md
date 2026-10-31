---
author: Latent Space
date: '2026-03-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jTEqdoB_mmo
speaker: Latent Space
tags:
  - context-engineering
  - ai-agents
  - software-engineering-evolution
  - llm-reliability
  - coding-agents
title: 在煮担担面中聊透 Context Engineering：HumanLayer 创始人 Dex Horthy 访谈录
summary: HumanLayer 创始人 Dex Horthy 在《In-Context Cooking》节目中，边下厨边分享了其在 AI 上下文工程（Context Engineering）领域的深度见解。他探讨了模型能力的边界、‘愚蠢区’（Dumb Zone）的规避、AI 工程师的直觉培养，以及软件工程师角色如何从‘编写代码’向‘促成代码生成’转型的趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Dex Horthy
companies_orgs:
  - HumanLayer
  - NASA
  - Replicate
  - Y Combinator
products_models:
  - Claude
  - Gemini
  - GPT-4
  - HumanLayer Agentic IDE
media_books: []
status: evergreen
---
### 混乱但确定的开场：担担面与上下文工程

**Alan**: 看看那酱汁，完全融合在一起了。我敢肯定模型实验室会喜欢这个答案。虽然现在场面有点混乱，但这很有趣。嘿大家，欢迎来到《In-Context Cooking》，在这个节目里，我们会品尝一道菜，然后尝试在极少帮助的情况下复刻它。我是 **Alan**，今天我们请到了一位非常特别的嘉宾，他是**上下文工程（Context Engineering）**背后的男人，**HumanLayer** 的创始人兼 CEO，**Dex Horthy**。欢迎你，Dex。

<details>
<summary>Original English</summary>

**Alan**: Look at that. Look at that sauce. Fully incorporated. I'm sure the model labs love that. That's the answer. This is getting chaotic, dude. This is fun. Hey guys, welcome to In Context Cooking, a show where we take one dish, taste it, and try to recreate it with minimal help. My name's Alan, and today we have a very special guest, the man behind context engineering, Dex Hory, founder and CEO of Human Layer. Welcome, Dex.

</details>

**Dex Horthy**: 哥们，我太兴奋了。

<details>
<summary>Original English</summary>

**Dex Horthy**: Dude, I'm so stoked to be here.

</details>

**Alan**: 我总是先问这个：如果按 1 到 10 分评分，你给自己的厨艺打几分？1 分是糟糕，10 分是惊艳。

<details>
<summary>Original English</summary>

**Alan**: Yeah, I mean I always start off with this. So on a scale of 1 to 10, how would you rate yourself as a cook? One being bad, 10 being amazing.

</details>

**Dex Horthy**: 我会给自己打 7 或 8 分。我现在不怎么做饭了，但我做饭是因为它很有趣。这种遵循一个既非常**确定（deterministic）**又有点**混乱（chaotic）**的过程的想法非常有意思。

<details>
<summary>Original English</summary>

**Dex Horthy**: I would put myself at like a seven or eight. I don't cook that much anymore. And I do it because it's kind of like fun. I the idea of just following a process which is very deterministic uh but also kind of chaotic is is uh is a lot of fun.

</details>

**Alan**: 没错，我们喜欢那种带着确定性的混乱。看着面前这些食材，你能猜到我们要尝试做哪道菜吗？

<details>
<summary>Original English</summary>

**Alan**: yeah, we like that chaotic but with um certainty. Looking at these ingredients we have before us, do you have any guesses of the dish we're going to try and make?

</details>

**Dex Horthy**: 显然是某种面条。我看到了青江菜。但我对面食了解不多，很期待看到我们要做的。

<details>
<summary>Original English</summary>

**Dex Horthy**: I mean, clearly we're doing some sort of noodle. I see some bok choy. Um, I'm But yeah, I I I don't know a lot about noodle dishes, so I'm excited to see what we got.

</details>

**Alan**: 我们今天要尝试的是**担担面**。

<details>
<summary>Original English</summary>

**Alan**: Yeah. So, the dish we'll be trying today is dandan noodles.

</details>

**Dex Horthy**: 噢，太棒了，我喜欢担担面。

<details>
<summary>Original English</summary>

**Dex Horthy**: Oh, nice. I love dandon noodles.

</details>

### 从 NASA 实习生到上下文工程的提出者

**Alan**: 好的。我读到过你从 17 岁就开始编程，曾在 **NASA** 的**喷气推进实验室（JPL）**实习。一个高中生是怎么在那样的顶级实验室获得实习机会的？

<details>
<summary>Original English</summary>

**Alan**: Okay, great. Because we do have some chili oil here. I've read that you've started coding since you're 17 and you had an internship at NASA for the Jet Propulsion Lab. Yeah. So, like how does a high school kid end up getting an internship at this very prestigious lab?

</details>

**Dex Horthy**: 他们当时有一个高中实习计划。那是在我高三后的暑假，他们把我们安排在当地一所大学空着的宿舍里。人们之所以想探索月球南极，是因为那里有些极深的陨石坑，里面有**冰**。月球非常干燥，但在这些陨石坑里，有从未被阳光照射过的水。

<details>
<summary>Original English</summary>

**Dex Horthy**: Uh, so they do have they had this high school internship program where it was like they would take for a summer it was like summer after my junior year. Yeah. And they just like put us up in dorms at a local like university that was kind of empty. And so there's the reason why people want to go explore the south pole of the moon is because there's like craters there that are so deep that there is like frozen ice there. The moon's very dry, but in these craters there's there's uh water that has never been hit by sunlight...

</details>

**Dex Horthy**: 我们的任务是想办法去收集样本并进行研究。问题是陨石坑非常深，大多数漫游车无法进入。我们基本上是在构建一些**寻路算法**。当时我 17 岁，还没有计算机科学学位，所以我们写了一个非常稚嫩的 **Dijkstra 算法**实现，根据漫游车的能力约束来寻找最短路径。

<details>
<summary>Original English</summary>

**Dex Horthy**: And so it's like oh we really want to go see what's in that ice and collect samples and study it. problem is very very deep craters and so like most of the rovers can't do it and so we had to like we were basically like building some like pathf finding algorithms... I was 17 I didn't have a CS degree like so we built a very naive implementation of Dystra's algorithm to like find the shortest path according to some like constraints of what the rover could do.

</details>

**Alan**: 那是一个伟大的开始。现在我们来聊聊上下文工程。你是如何想到这个术语的？据 **Swix** 说，很多人（包括 **Gemini**）最初以为是 **Andrej Karpathy** 提出来的。

<details>
<summary>Original English</summary>

**Alan**: great yeah I mean that's a great start... How did you get into context engineering? I feel like, you know, coining the term... According to Swix, there are there are many people who who uh Gemini thinks it was Andre Karpathy.

</details>

**Dex Horthy**: 好吧，那是一个非常合理的猜测。我当时在为 AI 工程师构建开发工具。我跟所有能联系上的优秀创始人和工程师聊天，告诉他们：“嘿，我们正在做一个能帮你构建更好 **Agent** 的东西。”

<details>
<summary>Original English</summary>

**Dex Horthy**: Okay. I mean, that's a very valid guess. yeah. So, basically I was building like dev tools for AI engineers. Okay. And uh what happened was I like talked to all the best founders and engineers and founding engineers that would like take my call and I was like, "Hey, we're making this thing that helps you build better agents."

</details>

**Dex Horthy**: 我发现，那些向企业交付真实、可靠 AI 系统的顶尖工程师，他们的构建方式与普通开发者完全不同。正如 Swix 在一条推文里说的，前 1% 的构建方式与剩下的 99% 差异巨大。有很多流行的开源框架，大家在公开场合都在用，但当你去看真实可靠的系统是如何构建时，那是完全不同的世界。

<details>
<summary>Original English</summary>

**Dex Horthy**: And the problem was was that when I talked to all these people who were shipping like real AI to the enterprise like reliable systems... it was like an old tweet from uh from like Swix actually was this idea of like the way the top 1% build is so different from the bottom 99%. You have all your like indie hackers and like open source frameworks that are very very popular... and then you go see how real people are building stuff and getting reliability and it's completely different.

</details>

**Alan**: 你认为这种差异的原因是什么？

<details>
<summary>Original English</summary>

**Alan**: why do you think there's such a discrepancy?

</details>

**Dex Horthy**: 我认为这是“想构建可靠软件的人”与“想构建酷炫 Demo 的人”之间的区别。**激励机制（incentives）**不同。如果一个东西 80% 的时间是正确的，做 Demo 没问题；但如果你想卖给大公司并每年收费 10 万美元，它必须是**防弹级（bulletproof）**的。我把学到的东西写了下来，一共 12 章，其中只有一章是关于**上下文工程**的，但那是唯一火出圈的一个。

<details>
<summary>Original English</summary>

**Dex Horthy**: I think there's a difference between like people who want to build like reliable software and people who want to build a cool demo. I think that's the incentives are different. The incentives of like okay if this is right 80% of the time that's fine. It'll look good on the demo... but if you want to go sell something to a real company... it's got to be much more uh bulletproof. So, I learned all this stuff and I was like, damn... So, I wrote down everything that I learned and I called it among other like there was 12 chapters. There was only one of them was really about context engineering.

</details>

### AI 时代的 Slop 与可靠性

**Alan**: 你最近在纽约有一个叫《No Vibes Allowed》的演讲，反响很好。其中提到了 **Slop** 这个词，你如何定义它？

<details>
<summary>Original English</summary>

**Alan**: Yeah. Cuz you had a couple AI engineering talks that um even recently right in New York. No vibes allowed was it the title that you know had had some good reception. One thing that was very commonly said even I think Swix had a talk about it was about slop and I'm kind of slop. How do you define slop?

</details>

**Dex Horthy**: 这个词已经演化了。现在它可以指代任何低成本、生搬硬套或衍生出来的、没有投入太多心血的东西。最常见的例子就是有人用 AI 写了一份 10 页的文档，自己都没读过，里面全是垃圾。

<details>
<summary>Original English</summary>

**Dex Horthy**: I mean it's kind of fun. The word has kind of evolved... I think of just like any like loweffort or like contrived or derivative thing that is like someone didn't put a lot of effort into. Yeah, it's obviously most common when someone just like uses AI to write a 10page document that they didn't read and is like full of garbage.

</details>

### 上下文工程的边界：从 40% 规则到直觉

**Alan**: 随着模型上下文窗口越来越大，上下文工程的手艺在过去一年有什么变化吗？

<details>
<summary>Original English</summary>

**Alan**: How have you seen the craft of context engineering change over the past, I guess, year? We had much smaller context uh windows uh but then now we have a lot larger ones and so probably the needs change.

</details>

**Dex Horthy**: 有两个竞争性的观点。一方面，随着模型变强，你不需要做那么多上下文工程就能获得同样的质量。但另一方面，我看到一些精通上下文工程的人，他们在旧版模型（如 Opus 4.0）上就能获得别人在 4.5 上才有的效果。

<details>
<summary>Original English</summary>

**Dex Horthy**: Well, so I think there's two competing things here, right? There's this idea of like as the models get better, you don't have to do as much context engineering to get the same quality of results... but I know a bunch of engineers who got really good at context engineering and they were getting the same results from Opus 4.0 and Opus 4.1.

</details>

**Dex Horthy**: **Opus 4.5** 对那些不想花时间学习如何使用模型的人来说就像是 **AGI**。但总有一些问题是处于模型能力边缘的，你需要通过上下文工程来确保它能可靠地一次又一次正确执行。

<details>
<summary>Original English</summary>

**Dex Horthy**: It's like Opus 4.5 is AGI uh for people who didn't want to put in the time to learn how to do it... there will always be a thing that the model can like only kind of get right reliably. Like you find a thing that's right on the boundary of the model's capabilities and you figure out how to get it right over and over and over again.

</details>

**Alan**: 你提到的**“愚蠢区”（Dumb Zone）**或死区是指什么？

<details>
<summary>Original English</summary>

**Alan**: You mentioned I think in the most recent AI engineering talk about what was it the dead zone where it's like the dumb zone.

</details>

**Dex Horthy**: 愚蠢区的概念是一种经验法则。对于新手，我建议当上下文窗口用到 **40%** 时，就要开始考虑收尾或者进行有意识的**引导性压缩（steered compaction）**。如果你没有这种直觉，就把 40% 作为你的安全线。

<details>
<summary>Original English</summary>

**Dex Horthy**: You got the dumb zone right here... the idea with the dumb zone is also like it's kind of meant to be a rule of thumb... training wheels is like when you get to 40% start thinking about wrapping it up or like like doing a like you know intentional steered compaction to where you want to be... if you don't know and you haven't developed the intuition, then like I tell people like shoot for 40% if you're learning.

</details>

**Alan**: 那么人们该如何培养这种直觉呢？

<details>
<summary>Original English</summary>

**Alan**: Gotcha. And so like how does someone even like get familiar and build this intuition?

</details>

**Dex Horthy**: 每周和 **Claude** 聊 70 个小时（笑）。你必须尽可能多地使用 AI，去犯错。我们开发了一个框架叫 **Research-Plan-Implement（研究-计划-执行）**。你要不断通过实战（put in the reps）来发现哪些问题是 AI 难以解决的，什么时候需要精细的上下文工程。

<details>
<summary>Original English</summary>

**Dex Horthy**: uh yeah talk to cloud for 70 hours a week. [laughter]... just use AI as much as possible. Make mistake... we developed this framework called like research plan implement... the only way to know how much context engineering to use on a given problem, I think, is um you just have to get some reps.

</details>

### 未来展望：从编写代码到促成代码

**Alan**: 对于 2026 或 2027 年，你对这个行业的变化有什么预判？

<details>
<summary>Original English</summary>

**Alan**: do you have predictions going into like 26 27 even the next you know couple years about how this industry will change that are top of mind?

</details>

**Dex Horthy**: 软件工程师的角色将继续演变。我不认为软件工程师会消失，但其角色将从“编写可运行的代码”转变为“**促成（cause）**可运行代码的产生”。

<details>
<summary>Original English</summary>

**Dex Horthy**: I don't believe the like software engineering is dead and there will be more no more no more coders. I think the the way I would describe it is like the role of the software engineer will change from like write working code to like produce working code or like cause working code to be produced.

</details>

**Dex Horthy**: 我最反感的是那些在 Twitter 上吹嘘自己消耗了多少 Token 或工作流有多并行的行为。**Coding（编码）**和 **Shipping（交付）**是有区别的。Coding 是让软件在你的机器上跑起来，而 Shipping 是将其投入生产环境、修复故障、长期维护。AI 还没完全解决 Shipping 的问题。我们的公司叫 **HumanLayer**，就是因为我们关注人类在其中的高杠杆作用。

<details>
<summary>Original English</summary>

**Dex Horthy**: And one of my biggest pet peeves is the people who run around Twitter talking about how much like cloud code they spent and how many tokens they did... stop we need to talk less about how much like code we produce... there's a difference between coding and shipping. Coding is like making the software work... Shipping is like getting it into prod fixing the things that are broken maintaining it over time... our company is called human layer because we used to do human in the loop but now it's a little bit more like I think about it as like what is the high lever things for humans to do and like what is the things that we can like leverage AI for.

</details>

### 最终评测：美味胜过卖相

**Alan**: 好的，我们要进入最后装盘阶段了。虽然场面一度有点失控。

<details>
<summary>Original English</summary>

**Alan**: Okay. I'm in the assembling stage right now... Yeah, but no rush, of course.

</details>

**Dex Horthy**: 我的卖相肯定没你的好看，但味道才是最重要的。如果好吃，我愿意吃这世界上最丑的“Slop”。

<details>
<summary>Original English</summary>

**Dex Horthy**: My plating is not going to look as good as yours, but we're going to figure it out. Yeah, taste is all that matters. This is why I love cooking for myself, because I like I don't want to have to care what it looks like. I'll eat I'll eat the ugliest slop in the world if it's delicious.

</details>

**Alan**: 让我们尝尝。干杯。

<details>
<summary>Original English</summary>

**Alan**: Let's give it a try. Let's give it a taste... Cheers.

</details>

**Dex Horthy**: 唔，这个味道很均衡，风味融合得很好。

<details>
<summary>Original English</summary>

**Dex Horthy**: I really like the like something about this one is like it's more well-rounded. It just like the flavors all come together in a nice way.

</details>

**Alan**: 裁判给 Dex 的作品稍高的评价。虽然食材一样，但 Dex 的面肉比（Ratio）更合适，风味更足。

<details>
<summary>Original English</summary>

**Alan**: So, I give Dex the slight win here. They all use the same ingredients... but I just like the texture and the flavor. And also, I really like the the extra protein.

</details>

**Dex Horthy**: 我拿掉了一些面条，因为我想要更多的猪肉。这就是赢得任何烹饪比赛的秘诀（笑）。你可以去 Twitter 找我 **@DexHorthy**，或者关注我们即将推出的 **Agentic IDE**：humanlayer.dev。

<details>
<summary>Original English</summary>

**Dex Horthy**: I took a bunch of noodles out. I was like, I want I want more pork. I want the ratio... I'm on Twitter, Dexorthy... and then we are we just rebuilt our product from scratch. It's an agentic IDE. It's uh coming out soon and uh you can go sign up at human layer.dev.

</details>