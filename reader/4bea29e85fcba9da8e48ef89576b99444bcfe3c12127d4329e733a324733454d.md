---
author: How I AI
date: '2026-05-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=h0gZf1hL4D4
speaker: How I AI
tags:
  - claude-opus-4-8
  - agentic-coding
  - model-benchmarks
  - ai-evaluations
title: Claude Opus 4.8 实测解析：卓越的单次生成与致命的『最后 10%』难题
summary: 本文深度评测了 Anthropic 最新发布的 Claude Opus 4.8 模型。作者通过编程原型开发、现有代码库维护以及业务策略分析等实战场景，揭示了该模型在单次生成上的强劲表现，同时也指出了其在长程任务、复杂边缘案例处理以及事实幻觉方面的局限性，为开发者和商业决策者提供了理性的使用参考。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - Google
products_models:
  - Claude Opus 4.8
  - Claude Opus 4.7
  - GPT-5.5
  - Gemini 3.1
media_books: []
status: evergreen
---
### 跨代演进：Opus 4.8 的性能指标与市场定位

Anthropic 正式发布了其最新的顶级模型 **Claude Opus 4.8**。根据官方宣称，该模型在**智能体**（Agents: 能够自主执行复杂、多步骤任务的 AI 系统）能力上实现了阶梯式的跨越。其核心改进集中在三个维度：增强的诚实度（减少幻觉）、更强的**长程自主性**（Long-horizon Autonomy: 在长时间运行的任务中保持目标一致性的能力），以及企业级的指令遵循能力。

在行业公认的编程基准测试 **SWE-bench Pro** 中，Opus 4.8 达到了 69.2% 的高分，不仅比前代 4.7 版本提升了近 5 个百分点，更是大幅领先于 GPT 5.5（约 10 个百分点）和 Gemini 3.1（15 个百分点）。然而，这种卓越的性能伴随着高昂的成本：输入 Token 每百万 5 美元，输出 Token 每百万 25 美元。为了平衡速度与质量，该模型默认开启了“高努力值”模式（High Effort Mode），并支持极速响应的快模模式。从纸面数据看，这无疑是目前最强悍的生产力工具。

<details>
<summary>Original English Source</summary>

Welcome back to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have a very special mini episode because Anthropic just dropped Opus 4.8, their latest state-of-the-art coding model. And I got a few hours of early access. and I'm here to share my very early thoughts about where this model is intended to perform well, where it did a great job and totally impress me, and where there's still a little bit further to go.

Anthropic is shipping opus 4.8. It is supposed to be their step change model for agents. And there's a couple things they've called out that this model does particularly well. It's supposed to be more honest, a less design flop, longer horizon autonomy on longunning tasks, and enterprise ready. So, it means it follows its instructions. And they're saying that Swebench Pro, they're hitting 69.2% which is almost five points higher than Opus 4.7, almost 10 points higher than GPT 5.5, and 15 points higher than Gemini 3.1. Now, this model is not cheap. It's $5 per input tokens and $25 per million output tokens. And then same as 4.7, effort defaults to high and fast mode can be a lot faster.

</details>

### 编程实战：从“单次奇迹”到“最后 10%”的泥潭

在实际编程评测中，Opus 4.8 展现出了极其矛盾的特质。在执行**单次生成任务**（One-shot Task: 仅凭一次指令即生成完整功能的能力）时，它的表现令人惊叹。评测者要求它在现有的 ChatPod 系统中构建一个全新的原型设计功能。Opus 4.8 在理解了复杂的架构决策和平台需求后，自主进行了约 20 分钟的编码并成功交付。代码推送到预览分支后直接运行成功，显示出其在处理全新业务场景时的强大爆发力。

然而，一旦进入功能的打磨阶段，即所谓的**“最后 10%”难题**，Opus 4.8 的短板便暴露无遗。它在处理边缘案例（Edge Cases: 非典型的、极端的系统输入或环境条件）时显得异常挣扎。随着任务层级的深入，它开始频繁产生 Bug，且在进行**错误溯源**（Bug Hunting: 识别并修复代码逻辑缺陷的过程）时表现出了惊人的**幻觉**（Hallucination: AI 虚构事实或产生逻辑错误的现象）。令人困扰的是，这种幻觉并非源于推理能力的不足，而更像是一种**接地失败**（Lack of Grounding: 模型无法将其逻辑与真实的上下文或数据对齐），它会基于假设而非实际代码数据来编造结论。

<details>
<summary>Original English Source</summary>

Surprise surprise lol it's a good coding model in that when I opened up claude code and asked it to do a fairly complex oneshot brand new surface area task it did a pretty good job. So I asked build a prototyping capability in chat pod. And I gave it some architecture decisions I wanted to make, what platforms I wanted to use, how I wanted it to function. It went through plan and then it autonomously coded for I would say about 20 minutes and shipped it. And when I pushed this live to my preview branch, it worked. Um, and so I would say from a oneshot feature, it did quite a good job.

Where it failed was this last 10%. And this is really going to be my theme of this episode. It does really, really well until it doesn't do well. And I found it did not do well consistently over time with the same types of trouble. So, what it nailed here is it did take the spec, it planned the work, it shipped the feature, but then as soon as I got it live and started trying to take it to the next level, it really struggled and started to ship bugs. And even more than its inability to finish that last 10% when it was bug hunting, it hallucinated. And I am going to tell you I have not seen a straight up hallucination in a very long time. But over my experience early testing Opus 4.8 both on business use cases as well as coding use cases it 100% made up things based on hypothesis not data.

</details>

### 存量系统挑战：视野狭窄与雄心的匮乏

当 Opus 4.8 被置于真实且复杂的存量代码库中时，它表现出了明显的适应不良。在处理**代码变基**（Rebase: 将分支上的提交移动到新的基准点上的过程）任务时，由于底层 PR 带来的大幅架构变动，Opus 4.8 无法准确理解代码边界的逻辑关系。评测者不得不进行多轮循环修正，因为它在修复旧 Bug 的同时不断引入新的边缘案例 Bug。这种现象说明，Opus 4.8 难以在复杂的存量系统中找准自己的“操作高度”，容易在局部逻辑中迷失。

此外，该模型在创意编程上的**雄心**（Ambition）也显得有些乏力。即使在“构建一个让 9 岁孩子觉得酷的游戏”这类开放性任务中，虽然它的 prompt 策略极具前瞻性——建议通过观察屏幕并动态调整难度来优化体验——但最终交付的产品却表现平平。即使被要求升级到 3D 效果，它给出的方案也仅仅是“及格”，未能展现出那种足以改变范式的 10 倍速智能体编码能力。相比之下，它更像是一个循规蹈矩的熟练工，而非一个能够突破边界的创意伙伴。

<details>
<summary>Original English Source</summary>

Basically what I saw is when I pointed it at existing code, it also struggled to sort of insert itself and understand the edges of where it was supposed to work. I had a couple branches in flight that I needed to rebase because we had shipped a big underlying PR and it kind of messed up the state of the code. And so I asked Opus 4.8 to rebase and check these branches for code. I had to do cycle after cycle of rebase and fixes because it was continuing to ship really edgecase bugs into the code. It struggled to understand the elevation at which it should be operating.

The other thing I reflected on when I was coding with Opus 48, is it just wasn't ambitious enough. It gave me this awesome prompt, which was build a game, then play it yourself by watching the screen and tweaking the difficulty until it's fun for a 9-year-old. Amazing. This is state-of-the-art coding agent. It's going to cook. Let me show you what it actually shipped. It shipped this, which is like fine, of course, magic, but not pushing the edges of a gentic coating. It's not 10x agentic coding blow my mind impressive. I kept saying more more do better do better and it just wasn't as ambitious as I've seen other models be.

</details>

### 业务洞察对决：Opus 4.7 与 4.8 的策略分歧

在非编程的业务策略场景中，Opus 4.8 与 4.7 的差异更加令人玩味。评测者要求模型基于过去三个月的业务数据，分析时间分配并制定“10 倍增长策略”。**Opus 4.7** 的表现非常稳健，它以数据为核心，生成的分析图表结构严谨且具有高度的全局视野（Zoom out）。

相比之下，**Opus 4.8** 在识别关键数据时遇到了困难。它表现出一种明显的**过度拟合**（Over-rotation: 过度关注微小数据点并将其视为普遍真理的倾向）。在随后的路线图制定中，4.8 的方案显得非常虚浮（Handwavy），甚至在被追问是否查阅了 GitHub 或在线数据时，它会坦诚地回答“不，我没有”——尽管它在之前的回答中表现得极其自信。这种“自信的幻觉”是 Opus 4.8 最大的隐忧。尽管它的语言组织非常优雅，没有冗余的填充词（Slop Tells: 典型的 AI 废话标识），且 Token 效率极高，但在涉及核心业务真实性时，它往往因为视野过于狭窄而错失大局。

<details>
<summary>Original English Source</summary>

Opus 47 was very numbersacred. You can see this table here. It was very structured and and rooted in real data. While both of these exercises did have access to the same data, Opus 48 had a harder time discovering the relevant data and it overrotated on small data points and took them as truth as opposed to what I experienced Opus 47 doing, which is it zoomed out a lot more and put everything in context. 4.7 very anchored in specifics very good strategy and 4.8 was incredibly handwavy and in fact with Opus 48 it gave me a road map and then I said we have all this. Did you search through GitHub? No, I didn't actually search GitHub. No, I didn't actually look up that data.

It's just overtuned and has kind of narrow vision. So, it's smart, it's fast, it's efficient, but it's overly confident absent true validation. It really latches on to specific data points, specific code points. It draws conclusions for them and then says this must be truth. And so it sort of misses the forest for trees both in coding and in strategy.

</details>

### 最终裁决：Opus 4.8 是否值得你的 Token？

总的来说，Opus 4.8 是一款性能卓越但个性鲜明的模型。它在**绿地项目**（Greenfield Projects: 从零开始、没有任何历史负担的新项目）的原型开发中表现惊艳，其工具调用（Tool Use）速度快且交互人体工学（Ergonomics）极佳。它摒弃了 4.7 版本中令人反感的斜体强调词，对话风格更自然、更像人类。

然而，在面对复杂的**存量代码库**（Existing Codebases）、严苛的逻辑边界任务以及需要精密数据支撑的策略工作时，开发者必须保持警惕。目前的结论是：Opus 4.8 的效率提升可能部分是以牺牲准确性为代价的。如果你追求的是单次生成的爆发力和更流畅的对话体验，它是首选；但如果你需要的是能够持续深入验证、处理复杂长程任务的底座，Opus 4.7 依然是更稳健的选择。此外，配合 Claude Code 推出的**动态工作流**（Dynamic Workflows: 支持数百个子智能体并行协作的新功能），Opus 4.8 的并行执行潜力仍值得持续关注。

<details>
<summary>Original English Source</summary>

The ergonomics were very nice. Now I got early access. Who knows what the production latency is. But with fast mode, I anticipate you'll have this fast experience. I would use it for green field prototypes. It's really impressive on a oneshot. I think its design is better. It got rid of the italics emphasis words which were driving me crazy from quad design. It's good at tool use. It's fast. It's not annoying.

Um, where I would test it is with existing code bases in branches with real edge case with strategy work that requires you to think about numbers. I would just double check where it's really confident because my experience was its confidence was not rooted in fact. In cloud code, you now have dynamic workflows which can let you spin off hundreds of parallel sub aents. And in cloud.ai and co-work, you now can set effort control from low to max. I would say it's a good model. It's not the most amazing model. It didn't blow my mind. It has some quirks to it.

</details>