---
author: AI Engineer
date: '2026-07-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pWXUkLP9uWM
speaker: AI Engineer
tags:
  - automated-scientific-discovery
  - recursive-self-improvement
  - artificial-superintelligence
  - gpu-optimization
title: 走向自动化科学研究：尤里卡机器与递归自我改进的未来
summary: 本文探讨了由 Recursive AI 首席执行官 Richard Socher 提出的自动化 AI 研究愿景。文章阐述了技术演进的指数特征，分析了科学研究受限于人力带宽的现实瓶颈，并详细介绍了“尤里卡机器”的四大基石。同时，通过 NanoChat、NanoGPT 及 CUDA 内核优化等实证，展示了递归自我改进（RSI）如何驱动下一代技术革命。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Recursive AI
  - Nvidia
products_models:
  - NanoChat
  - NanoGPT
media_books: []
status: evergreen
---
### 进化驱动：技术演进的指数逻辑

从生物演化到技术革命，**开放式演化**（Open-ended Evolution: 无固定终点且持续产生新颖性的演进过程）始终是推动世界发展的主导力量。回顾历史，人类通过开发狩猎、农耕及现代工业技术，不仅极大地提升了全球经济总量，也维系了庞大人口的生存与繁荣。正如投资人 **Marc Andreessen** 在其**《技术乐观主义者宣言》**（Techno-Optimist Manifesto）中所指出，**技术**是经济增长的唯一源泉，任何物质层面的生存和发展挑战，最终都可以通过更先进的技术得到解决。这种演化进程在现代已进入加速通道，其变化幅度在单一生命周期内便清晰可见：从莱特兄弟实现人类首次受控动力飞行，到阿波罗计划将人类送上月球，仅仅跨越了 66 年。在这一时代背景下，我们正处于一个关键的节点——我们错过了探索地球的黄金时代，也尚未迎来探索群星的太空时代，但我们恰逢其时，能够见证并亲手构建足以重塑人类智力边界的 AI 系统。

<details>
<summary>Original English Source</summary>

All right. Hello everyone. Really excited to be here. It's a big room. Very very cool conference so far. I want to talk to you today about something that's been on my mind for many many years. This is actually the first time I talk about it, sort of my version of going to Mars. And that is the Eureka machine. A machine that will eventually invent pretty much all future inventions for humanity. And the way we're going to get there is by taking a step back and thinking about what else has given us a lot of really incredible inventions, namely evolution, and how that leads us to automating research and pushing the scientific frontier forward. And this is a joint work with a lot of amazing folks at Recursive.com and even some folks at AIX Ventures. And some of these slides are actually inspired by and taken partially from one of my co-founders at Recursive, Tim Rocktäschel.

So, why do I talk about evolution and why is it so important? I think basically evolution is this like open-ended process that has gotten us to a lot of different things that we really like. It started in biology, it's moving to science, technology, and eventually AI. And I think it can inspire us in a lot of different ways to build better AI systems as well. In fact, whenever we take out and there's this famous saying, "Whenever I fire a linguist, my accuracy goes up." I think that's true for machine translation back in the day. And it may be true that we should fire all the AI engineers that are here and have them mostly manage an actual AI engineer that is AI and works on AI. And so that may be one of the conclusions of this talk. And I think most of us are going to be excited about it cuz it means that we'll all become managers of such an AI rather than having to do the nitty-gritty ourselves.

All right. So, let's start with evolution, right? The really, really big picture, 3 and 1/2 billion years or so. This is kind of the incredible process that has led from, you know, simple bacteria and plants and fish and amphibians and so on to, after many billions of years, us. So, That's a good starting point. That gives us some indication that evolutionary processes can do pretty amazing things, right? But now, let's zoom in and go maybe down to a few million years. There, we can also see how in a very first primitive ways, technological evolution has basically increased the world's sort of product in terms of monetary value. It's a little bit harder to estimate in the beginning, but we can see these sort of sequences of exponentials. And most exponentials eventually become S curves. They flatten out, but humanity has done pretty well by basically developing many of these very basic technologies, hunting, farming, but then also thinking about science, the scientific method in the early days of the Enlightenment, and then of course the Industrial Revolution.

So, now we can zoom even further, and no worries, we're eventually going to get to Nanochat and actual auto research and what we're doing. It's a very, very quick zoom. And now we can zoom down to last few thousands of years. And what we're seeing there is that with more technology, we were able to sustain more people, right? So, when we're working on pushing that frontier forward, we're very certain that that will lead to more human flourishing, right? And especially in the last few hundred years, we're seeing this incredible explosion in the population of people because of technology. And the evolution that it brings. And in many cases, that evolutionary process is run by us, so it's sort of conscious. But there are sort of interesting inspirations that we can take from that as we're thinking about the evolution of AI in the next cycles.

In fact, and I might not agree with everything with Marc Andreessen, but he is very smart and we agree on a lot of things. And so I think he wrote this really great techno-optimist manifesto in which he, I think, correctly points out that the only perpetual source of growth for the entire economy, a lot of people worry about AI taking jobs and things like that, but the truth is it will very, very likely increase the economy massively and that will benefit benefit a lot of us. And so the perpetual source of growth is technology. In fact, we can go even further and say that there's no material problem, and again, it's not sort of psychological problems and things like that, but no material problems that cannot be solved with even more technology. Right? For problem of starvation, we invented the green revolution, darkness, light, cold, indoor heating, heat, air conditioning, and the list goes on. So, I think we can kind of realize that this evolutionary process has been going on for a very long time and continues to make a huge amount of progress.

</details>

在确立了技术作为增长核心的共识后，我们需要审视科学假设的迭代机制，并解决研究带宽不足的深层矛盾。

### 科学选择：从进化论到人力的极限

科学理论的发展同样遵循达尔文式的演化规律。正如科学哲学家 **Karl Popper** 所阐述，理论的筛选过程是一场残酷的竞争，只有最能经受住严苛实证检验的假说才能生存。然而，传统的科研模式正面临物理极限。科幻作家 **Stanisław Lem** 在数十年前就敏锐地预言：科学知识的指数级增长终将因为研究人员数量的匮乏而停滞。当今科学领域细分极其严重，导致每个微小分支的研究带宽不断收缩，无法获得充足的人力资源去穷尽所有探索路径。为了突破人类生理极限对科学进步的制约，我们必须实现研究本身的自动化，也就是构建能够自主进行科学发现的系统——**尤里卡机器**（Eureka Machine: 旨在自主发现科学规律、发明新技术的一体化AI系统）。

<details>
<summary>Original English Source</summary>

In fact, the progress is so fast that there can within one lifetime be a major, major shift. Right? If you're born in 1900, then 3 years, when you're 3 years old, the first human ever was able to, thanks to the Wright brothers, kind of have sustained motored flight. And then about 60-ish years later, in 1969, humans flew all the way to the moon, right? So, that within one lifetime, humanity went from like no one can fly for a very long time other than sort of gliding down a hill or something, no one can really fly to we all fly to the moon, right? And so, for us, I think, what that means is we're probably, and I sometimes say this, we're like too late to explore Earth, we're too early to explore the stars, but we're right on time to build an AI that could actually do what flying did for some in one lifetime due to intelligence. We can build and move from AI being worse at everything that we do to possibly being better at any specific task that we do. Right? And that will probably be our our 60-year time frame, and because everything moves faster, it might only be 30 years or so.

So, then, there's an interesting connection between technology and science and theory, right? Like sometimes the application comes first, and then we develop the theory later, and then improve at the technology. Sometimes the theory comes first, and from that we can build new kinds of technologies. And so, it's very helpful to think a little bit about the philosophy of science, and no better to be inspired there than Karl Popper, wrote that just like in other types of evolution, when we choose a theory, we also choose one that is best in competition with other theories. Of course, you need if you wanted LLMs to do that, they need to find them, you need web search, for instance. But, in the theory that best holds its own, it's one that, just like evolution, has a certain natural selection process, right? It proves itself, and there is also a sort of survival of the fittest going on in scientific theories. And in fact, a lot of science, according to Popper, is basically us proposing a new theory hypothesis or explanation or description and then subjecting it to rigorous empirical testing. That is the essentially evolutionary pressure of scientific theories.

And basically that was a very short run through the history of open-ended evolution which hopefully makes us all realize that more science lead to more technology which will lead to more growth which lead to more human flourishing. And so that then begs the question does it make sense for us to try to just scale up and spend a lot of our resources as humanity to scale up scientific discovery in order to lead to this flourishing. When you double click into that you kind of realize which Stanisław Lem already realized a long time ago that the exponential growth of science will actually be at some point halted by the lack of people working on it, right? There's so many niche subfields now in all the different areas of science that is very hard to get a million people to work on that particular thing. And so as a result of this incredible widening of the scope he says the number of people focusing on any single section of it has decreased. And that then leads us to really thinking about how could we automate this and automate scientific discovery and that then leads us to what I call the Eureka machine.

</details>

为了具象化尤里卡机器的运行逻辑，我们需要剖析其内部的架构设计与基础设施支撑。

### 四大基石：尤里卡机器的系统架构

**尤里卡机器**并非单一的算法，而是一个高度协同的工程系统，由以下四个核心支柱共同构成：
* **存量知识检索**: 整合人类已发明的所有技术与文献，提供完备的先验背景。
* **高维数据观测**: 实时采集并注入所有可测量的科学实验与物理世界数据。
* **高保真沙盒模拟**: 在无法直接测量的领域，构建极速的数字孪生模拟器。只要某一系统可被模拟，AI 就能在其中进行验证、迭代并求解。
* **物理实验室闭环**: 在虚拟世界的探索终点，通过物理或工业实验室（Physical Lab）在现实世界运行真实实验，完成闭环验证。

在这四根支柱之上，运行着一个**智能体集群**（Agent Swarm: 协同工作以解决复杂问题的多智能体系统）。为了支撑这个庞大的智能体集群，现有的基础设施层必须重构。以 **You.com** 为例，专门为大语言模型打造的搜索引擎不再提供针对人类的“十条蓝色链接”，而是提供能够支撑 AI Agent 读取数千个长文本片段的高带宽工具。只有重构技术栈的每一层，才能为超级智能提供坚实的基石。

<details>
<summary>Original English Source</summary>

This is basically our attempt at trying to build a machine that automates the process of scientific discoveries. And in fact I like in a couple months I'll have a book coming out on this exact idea and so I'll just give you a super high-level highlight of how such a Eureka machine could be built for basically everything from physics, chemistry, biology, neuroscience, medicine, economics, astrophysics and so on. And there are essentially four pillars that are all extremely important to this machine. One is, of course, you have to understand what knowledge is already out there, what things humanity has already invented. You have to get all the scientific measurement data into, as in the second pillar, this machine. Then, for things that you cannot yet measure, we don't yet know, you should try to then build simulations. Anything you can simulate, you can verify, and you can then solve with AI. And if all else fails, or at the very end of these processes, you still need to have some kind of physical industrial like lab that actually can run real experiments in the real world.

And on top of all of this, you'll have a basically an agent swarm that will deal with all of these different sources of knowledge and data and experimentations and and rewards. And in terms of, you know, the foundational model of knowledge, of course, we also, you know, basically is is a good example of how every single technology we've built so far, especially in AI, but also before that, the internet, browsers, GPUs, and so on, we can rethink, and there are a lot of startups possible in rethinking every single one of the layers of technology as infrastructure for superintelligence. And at you.com, for instance, we work on web search for LLMs, right, and agents and so on. And that actually is quite different, right? Agents can read thousands of very long snippets, rather than just 10 blue links with like a very short snippet. And so, you can rethink each of these different layers of technology that we've built for people, and rebuild them for AI in order to use them as tools to then build a superintelligence. Now, that is essentially the sort of why. Like we want to build superintelligence in order to automate science.

</details>

在具备了尤里卡机器的基础系统架构后，如何让系统实现从人工调试到自主进化的跨越，成为了攻克智能奇点的核心挑战。

### 机器自决：递归自我改进的实证

要实现真正意义上的超级智能，最有效的方法是让 AI 能够自主迭代与升级。回顾 AI 的发展史，当研究者用端到端学习和反向传播算法取代人工设计的语言规则时，系统性能迎来了爆发式增长。这表明，**每一次用学习系统取代人工干预，技术都会产生巨大的跨越**。然而，目前的许多方法（如部分小模型微调）只是弱自我改进。真正的**递归自我改进**（Recursive Self-Improvement: 智能体通过诊断自身缺陷并重写自身代码，在无外部干预下实现持续自我升级）要求系统具备“自知之明”，能够全面访问包括预训练、强化学习和评估套件在内的完整工具箱，并在新版本中重构自身。

Recursive AI 团队在没有 CUDA 专家的情况下，利用自主研究系统在 GPU 优化等三个硬核基准上取得了突破：
* **小聊天模型优化（NanoChat）**: 仅用 5 分钟的训练时间，在一天内将 Bits per Byte (BBB) 评估指标从社区极限的 0.93 降至 0.91。系统自主发现了哈希双字词与三字词嵌入技术，并通过可学习的门控机制将其融入注意力路径。
* **极速 NanoGPT 训练（NanoGPT Speedrun）**: 将业内优化了一年多的训练基准时间进一步缩短了 2.0 秒以上，达到了 70 秒的行业顶尖水平。
* **CUDA 内核超越**: 系统在短短几天内探索并设计出了全新的 **CUDA 内核**，性能超越了 Nvidia 官方基准测试网站上的最佳纪录，且未产生任何奖励作弊（Reward Hacks）。

<details>
<summary>Original English Source</summary>

And to me, that will be the next big step function change in in humanity and technology as we know it. Now, how do we actually build it? I think the best way to build it is to have it built itself, right? We moved as a field and especially natural language processing for instance, which I've worked on for many years. We moved from not having linguists. This feels like ancient, you know, BC history, but before ChatGPT, we moved from having linguists tell us a bunch of things about language and then training statistical models on top of that. And when we allowed neural networks to actually automate learning those features with word vectors and other neural network architectures and back-to-back and end-to-end learning and backpropagation, we basically were able to get much bigger improvements. Then we did a bunch of architecture engineering. Now a bunch of people at least are working on a unified architecture, but even that unified architecture has a lot of manual processes. And so, it's clear over and over again in AI that when we take out a manual process and we replace it with a learned system, improvements will follow. And so, that's why I think we should try to build a supermachine by having an RSI that builds itself. And the beauty is that only now AI can actually do this because AI is code and AI can code now.

This ability to really code in longer and longer time horizons has really only happened in the last like 6 to 8 months. And that now enables such an RSI to work on itself, to develop almost a certain sense of self-awareness of its own shortcomings and then fix those shortcomings. And then once we have that machine that has gotten really, really good at doing research in AI itself, we can then use it to do AI research for a lot of other things in other scientific fields. And so at a high level it's quite easy, right? We have three steps: ideation, implementation, and validation of ideas. That's true for basically almost every scientific field. And so to end maybe on some very specific examples, we have built this first kind of version of such a Eureka machine and we wanted to just show that it works on some small samples that a lot of people know and are aware of. And so we basically started with three things that show you and give you a very first glimpse of an and sort of simple proof points of what such a machinery can do. And that was basically better training, faster training, and better kernels for Nvidia GPUs.

The first one, NanoChat, I'm sure many of you have heard of it. A lot of people think that's already recursive self-improvement and it's kind of a weak form in the sense that usually when you do auto research, it's not recursive self-improvement, right? True recursive self-improvement is when you have an AI that has a sense of self-awareness of its own shortcomings, full access over everything in its arsenal from pre-training to RL training and harnesses and everything, and then actually updates that entire system in the next version of itself. Now you can also take such a system and just ask it to improve some other process, some other AI, like a small NanoChat run where you can train something in 5 minutes. And that is really exciting and it's an important milestone, but it's not actual RSI. So here we basically showed three examples of such an auto research system and what it can do and after a very very short time it essentially was able to outperform many different teams and teams that also use other AI research.

So, let's double click into some of these. Nano chat is really exciting example. Basically, you train a very small chat model in less than 5 minutes and you basically want to have it get to the best possible bits per byte number. And so, the whole community had worked on this for quite some time and got to 0.93 and after training this for a little more than a day or two, we basically got it down to 0.91. Which is pretty exciting. Now, it wouldn't be that exciting if all it did was just find a couple of hyper parameters and tune them carefully, but it actually did find truly interesting novel ideas like hash bi-grams and tri-gram embeddings and tables for those and mixing that into various value paths of the intention through variety of learned gates. Another one nano GPT speed run. Obviously, speed is very important. So, here we're able to work on this again, apply the system and after very short amount of time it got better than people working often together with the AI for over a year on this very on this benchmark and made the whole thing another two seconds over two seconds faster at 70 seconds. And again, discovering very interesting ideas in the process.

And then the third one is CUDA kernels. Of course, we all care about not burning through our GPU budgets too quickly and trying to be very efficient. I think in general it's actually kind of shocking how inefficient a lot of mixture of expert models still are running very large clusters that cost billions of dollars and then only have like 30% or so utilization. So a lot of work that's ongoing in the world to improve that and different fields or different groups of people are various different stages of that. But long story short, lots of different CUDA kernels are used during training and testing and here we basically again took that system and after a couple days it discovered better kernels than the leader boards best on the Nvidia benchmark website by again quite quite a sizable margin across all the different categories of those kernels. And while we are pretty good at AI and we actually in the team didn't have any particular CUDA kernel experts who just spent their entire careers writing good kernels. But still, you know, we do just enough to make sure and work together with Nvidia to make sure that there no reward hacks here and other issues. But actually found that eventually these all checked out and were indeed pretty much all the different kernels found the best solutions there.

</details>

递归自我改进不仅在工程细节上得到证实，更在宏观维度上拉开了通往未来智能探索的序幕。

### 升维跃迁：多维智力空间与上限

递归自我改进（RSI）构成了下一代技术发展的 **S曲线**（S-curve: 描述技术从缓慢起步、爆发增长到最终成熟扁平的 sigmoid 轨迹）。当旧的技术曲线逐步扁平化时，新曲线将以指数级叠加的方式在其顶部展开。针对“智能的发展终有边界”这一担忧，从数学与系统建模的角度看，**智能并非一维的单一标量，而是一个由 10 个核心子空间交织而成的 volumetric 复合高维拓扑空间**。当前人类技术所触及的智能水平，相较于这个多维智能空间的绝对物理上限，依然微小得如同沧海一粟。跨越所有的维度去逼近这个物理极限，正是尤里卡机器与递归自我改进系统在未来数十年中所肩负的历史使命。

<details>
<summary>Original English Source</summary>

And so with that I hope I could convince you that indeed RSI could be that next big S-curve an exponential that gets layered on top of previous exponentials and that should help us with not just AI but eventually science and then all of technology and then allowing many more people to flourish on our planet. And so maybe I'll end on this note here, which is a lot of people wonder how much longer I can go, right? Every exponential eventually flattens out and it's actually quite hard to know like when we even talk about exponential growth in the eye, what does that even mean? There are many different, I call them spaces of intelligence and we won't have time to go into all of all of these, but as soon as you actually try to define multiple different dimensions of each of these 10 spaces that make up this complex sort of volumetric thing that is intelligence, you'll realize that there's still so much more to go. Like on the upper bounds of intelligence, we're still astronomically far away from reaching those and across pretty much every single one of these dimensions and the spaces that they make up. So, if any of that is interesting and you want to help us build that, we'd love to hear from you. Thank you.

</details>