---
author: Internet of Bugs
date: '2026-05-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=AkadGXzDqBw
speaker: Internet of Bugs
tags:
  - recursive-self-improvement
  - super-ai
  - autoresearch
  - ai-hype
title: 递归自我改进是幻觉：破除 autoresearch 与超级 AI 的迷思
summary: 软件工程师 Carl 深入拆解，指出近期关于 AI 递归自我改进及 autoresearch 工具的炒作存在严重误读。作者阐述了递归自我改进在理论上虽是科幻构想，但与当前 AI 能力存在鸿沟：AI 仅能完成简单的代码微调，尚不具备理解人类复杂任务评价标准、解决 AI 能力‘锯齿状’分布及进行自主深度研究的能力，呼吁大众冷静看待此类 AI 耸人听闻的标题。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - autoresearch
  - Claude Code
media_books:
  - Hitchhiker's Guide to the Galaxy
status: evergreen
---
### 递归自我改进的幻觉：技术炒作与科幻构想

关于 **递归自我改进**（Recursive Self-Improvement: AI通过创造更智能的AI来迭代升级）的讨论最近在 AI 领域十分活跃，这主要源于近期发布的一款 AI 工具。目前的情况很明确：要么许多人根本不了解这个概念的真实含义，要么他们完全不在乎其内涵，只是为了获取点击量。作为一名自 80 年代末就深耕软件行业的从业者，我非常担心那些没有时间或技术背景去深入理解 AI 的大众，会被这些愚蠢的标题误导。被点击诱饵党放大的那种世界观简直是无稽之谈。

递归自我改进在理论上或许是可能的，至少在 sci-fi（科幻）构想中是这样。然而，这仅仅是一个思维实验，目前没有任何实际证据表明它能够发生，更别提正在发生了。尽管那些炒作所谓 autoresearch 工具的人试图让你相信它正触手可及，但真正的递归自我改进是指：人类创造一个比人类更聪明、或者至少在 AI 研究方面比人类更出色的 AI，然后这个 AI 创造出更新、更聪明的 AI，以此类推。Doomers（悲观论者）正是利用这一逻辑，声称这种机制会产生超越人类理解的超级 AI。如果非要寻找这种逻辑的现实参考，它几乎就是《银河系漫游指南》（Hitchhiker's Guide to the Galaxy）系列故事的开端。

<details>
<summary>Original English Source</summary>

All right, so today I'm going to talk about non-recursive not self-improvement. The idea of AI recursive self-improvement is a key concept in a lot of what will happen with AI in the future kind of scenarios. There's been a lot of chatter about it recently because of an AI tool that was recently released and it's made it quite clear that either many people have no idea what recursive self-improvement actually means or they don't care what it means and are just trying to use it to get more clicks. As usual, I'm concerned that people who don't have the skills or time to understand in detail what's going on with AI will see the stupid headlines and they'll get the wrong idea. And, of course, as usual, that would be bad because the worldview that those headlines in the click-baiters amplify is utter bullsh---------. 

The concept of recursive self-improvement didn't belong in that essay, because unlike much of the totally unhinged Doomer crap, recursive self-improvement might actually be possible, maybe, at least theoretically. However, it's just a sci-fi thought experiment, and there's no actual evidence yet, it could really happen, and it's certainly not happening now. Despite what these people hyping autoresearch would lead you to believe, the idea of how to recurse self-improvement is that people make an AI that's smarter than humans, or at least better at AI research than humans, and that AI creates newer even smarter AI, which in terms creates another AI even smarter than that one, and so on and so forth. This is the rationale that the Doomers used to try to justify super-AI by claiming it will be so far beyond our understanding, because it was built by an AI smarter than an AI that's smarter than an AI that's smarter than an AI that's smarter than an AI that's smarter than an AI that's smarter than an AI that's smarter than an AI that's smarter than an AI that's smarter than us, or something of that effect, you get the idea. To get some concept of how seriously you should take this idea, this is literally the inciting incident of the Hitchhiker's Guide to the Galaxy series.

</details>

### autoresearch 的真面目：性能优化循环

当前备受炒作的 autoresearch 工具完全不是递归自我改进。它实际上是一个非常简单的工具。你给它一段代码，并设定一个用于衡量事物好坏的指标，然后它就在循环中运行：对代码进行微调，运行指标检测。如果指标改善了，就保留更改；如果没有改善，就回滚到上一版本。这个过程不断循环，直到你停止它，或者耗尽了你的 AI token 预算。

在我职业生涯中，我编写过大量实现此类功能的代码（只不过没有 AI）。例如，当你在编写处理网络传输的代码时，通常需要分配一块固定内存作为缓冲区来存储数据。问题在于：你应该分配多大的缓冲区？你通常会编写一段循环测试各种缓冲区大小的代码，运行基准测试并记录结果，以找到最大性能的缓冲区大小。autoresearch 本质上是该过程的“AI赋能”版本。它确实比你自己编写测试代码更方便，但它仅仅是一个性能调整工具，而且并不复杂。

<details>
<summary>Original English Source</summary>

So this new autoresearch tool that everyone is hyping up, it's not that at all. It's a pretty simple tool. You give it access to some code, you give it a way to measure a number that indicates whether things are getting better or worse, and then it just runs in a loop, and it makes some tweak to the code that you give it, it runs the measurement, and if the measurement is better, it keeps the change, and if the measurement isn't better, it rolls it back to the previous version. Does this over and over and loop until you stop it, or you burn through all your AI token budget, which can happen pretty quick in this scenario. I have written a ton of code that does this kind of thing in my career, minus the AI. For example, anytime you're working on code that does network transfers, there's always a fixed amount of memory that gets allocated as a buffer to hold the data that came from the network during processing. Question always arises: how big a buffer should you allocate? So you write some code that loops through various buffer sizes, runs a benchmark & records the results for each. When it's done, assuming your benchmark was good, you'll know what to set the buffer size to for maximum performance. Another research is basically an AI-enabled version of that. It's more convenient than having to code for yourself what values you want the tool to experiment with, but it's just a performance-changing tool, and it's not a particularly sophisticated one at that.

</details>

### 通向超级 AI 的深渊：核心能力鸿沟

为了启动递归自我改进，AI 必须能做到以下三点，而目前它连第一点都做不到。

首先，它必须**写出超越人类的代码**。许多人误以为 coding agents（如 **Claude Code**: 一种 AI 编程代理工具）写代码比人类更好，这其实是一个误区。AI 的能力在于写代码的速度快，而非质量高。在相对较短的时间内，它能写出比人类更多的功能代码，但这并不意味着代码质量本身超越人类。遗憾的是，基准测试和标准化考试几乎都是基于短时间的产出，这恰好是生成式 AI 的强项，但这种能力距离启动递归自我改进还差得远。

其次，AI 必须具备理解并创造 **评估指标** 的能力，以衡量自身修改是否真正使其在“任何人类所学之事”上变得更好。当前 AI 的能力是“锯齿状”（Jagged）的：在某些领域（如象棋、围棋）极强，而在处理未训练参数外的异常情况时（如自动驾驶车辆无法理解警察的手势）极弱。我们尚且无法解决这个“锯齿问题”，最先进的 AI 对此更是毫无头绪。

最后，递归自我改进需要 AI 提出**模拟人工大脑的新方法**，而非仅仅微调现有的神经网络。我们已经看到这种微调无法带我们走向 **通用智能**（General Intelligence）。正如一位 AI 研究者所言，我们正在从“规模化时代”转向“研究时代”，而递归自我改进要求 AI 在这项前沿研究中比人类更出色。目前，AI 能做到的仅仅是在人类定义的指标下微调一个简单的 Python 脚本。因此，请深呼吸，忽略这些耸人听闻的标题。

<details>
<summary>Original English Source</summary>

Understand that this isn't nearly sufficient. In order for recursive self-improvement to even start, an AI would first have to code better than humans, not better than the average human, not better than the best human, but better than the best possible human. An AI, despite what everyone seems to say, cannot write better code than the average professional human coder. A lot of people get this wrong, so let me be very clear. What today's AI can do is write code faster than a human, not better. A lot of people that say that coding agents like Claude Code can write code better than humans, and many professional programmers have said that AI's can write code better than they can, but that's only true if time is an important factor. AI can write more code and more functional code in an hour than any human can write in an hour, but that doesn't mean that the code is better than a human could write. It just means that it's better given a relatively short amount of time. And you'll notice that benchmarks and standardized tests are pretty much all intended to produce results in a relatively short amount of time. That's why generative AI is so good at benchmarks. But that's nowhere near good enough to kick off recursive self-improvement. And the programming part is just the easiest part for an AI to do. I spend a lot of time on this channel talking about the difference between training an AI to play a game like chess or go, or even the computer security hacking version of Capture the Flag, and training an AI for general intelligence, also known as "anything and everything a human has ever learned how to do." 

That's the second thing that AI has to be able to do for recursive self-improvement to work. It has to be able to understand and create better than any human the criteria for measuring whether the changes being made to an AI make it better or worse at anything and everything a human has ever learned to do. No one and nothing has any idea how to do that. A phrase often used in discussing AI functionality these days is "jagged," the idea that if you could graph how good AI's are at everything, there would be some things that AI's are a lot better than humans like chess or go, and the graph for those things would be really high. And then other things, the AI's are way worse than humans at, like recognizing when they're operating outside the parameters that they've been trained for, like in those videos where the self-driving cars keep ignoring hand signals from police officers directing traffic. The graph for those things would be really, really low. And so the whole graph would look jagged with big spikes up and big drops down. We have no idea how to fix the jagged problem. And the best AI's that we built have even less of an idea how to fix it than we do. But we're not done yet because the third thing that an AI would have to do for recursive self-improvement is to come up with new and better ways of simulating how an artificial brain should work. Not tuning the neural networks we have now. We're already seeing that's not going to get us much closer to general intelligence. As an AI researcher recently said, we're moving from the age of scaling to the age of research, and recursive self-improvement requires the ASB better than we can be at that new research. And right now, the best than AI can do is tune up a single simple Python script after being given a human defined metric for judging what better or worse means. This is not a step toward recursive self-improvement, which means it's not a step towards super AI. So take a deep breath, ignore the headlines, send this video to anyone you know that's freaked out about super AI getting closer. And above all, let's be careful out there.

</details>