---
author: AI Engineer
date: '2026-09-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=v42opQpCy60
speaker: AI Engineer
tags:
  - design-engineering
  - human-in-the-loop
  - ai-assisted-design
  - prompt-engineering
  - design-system
title: 以形容词的速度构建设计：重塑 AI 时代的人机协作与审美控制
summary: Impeccable 创作者 Paul Bakaus 深入探讨了 AI 时代设计与工程边界的消融。针对设计中‘直接像素操作层级过低’与‘端到端黑盒生成导致审美趋同’的双重困境，他提出以‘形容词与动词’作为人机交互的语义锚点，通过为模型注入专业设计系统的上下文规则，实现既非全自动也非纯手动的精准审美放大与多轮迭代工作流。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Impeccable
  - Claude
  - GPT-5
media_books: []
status: evergreen
---
### 破局设计与工程边界：AI 时代的设计语言与协作重构

在现代软件研发中，**设计工程师**（Design Engineer: 兼具视觉审美与前端代码实现能力的跨界角色）的崛起正深刻改变传统协作模式。传统由产品经理定义需求、设计师在设计软件中出图、经过多轮评审后再转交工程师编码的**瀑布流交付流程**（Waterfall Handoff: 线性且割裂的传统设计到开发传递方式）在当前敏捷与 AI 驱动的环境下已逐渐瓦解。设计师正在深入代码层，工程师也开始直接涉足界面设计，两者之间的边界正变得愈发模糊。

然而，在 AI 编程工具（如 **Claude Code**、**GitHub Copilot**、**Cursor**、**Codex** 等）广泛普及的背景下，工程师与设计师在使用相同模型时往往会得到截然不同的输出质量。这一差距的核心并不在于底层模型的能力，而在于缺乏一套**共享的设计沟通语言**。以 **Impeccable** 为代表的设计增强工具，其核心目标正是构建一套能够让工程师与 AI 顺畅交流的语义桥梁，使代码脚手架不仅能提升开发效率，更能使开发者与 AI 协同产出具备专业设计品质的界面。

<details>
<summary>Original English Source</summary>

Cool. Let's get this going. Welcome everyone. Thanks for coming. My name is Paul and I'm going to try to save you from the midday slump. So, let's see if we can do that.

Okay. So this cold open of this talk will make a lot more sense if you know what Impeccable is. But if you don't know what it is, it's a design skill that turns your coding harness into a better designer and hopefully you into a better designer. And you can try it out. It works across all harnesses: Claude Code, GitHub Copilot, Cursor, Codex, etc. And this talk is really about my approach to how to build this tool as opposed to the tool itself.

Let's get started with a pretty typical website. This is an intentionally very basic website and I want to give you that one as context to what I'm going to show you next. It's an okay website, it's not great, it's pretty bland, but at least it has some color, some something.

Now here is the command "make the workflow section bolder" with Impeccable installed. Now, it's not perfect. There are some problems with this. For example, the section numbers that you have there, that's a very typical AI slop tell that GPT loves to do, and Claude actually loves to do as well, and it sometimes creeps in. So I wouldn't say this is perfect by any means, but I think it's bolder than before.

A lot of people install Impeccable, try it out, and then they ask me: "Well, I don't know, maybe it could be placebo, maybe the model is good enough in itself, right? Not sure if it actually works." Well, let's compare it. This is exactly the same project, GPT-5 on Extra High, same exact prompt without Impeccable. There is a slight difference, I would say, but you be the judge. The before and after is pretty different, and I'm going to talk about why that is and what the approach is.

Designing at the speed of adjectives. To get the elephant out of the room: they are not just adjectives, they're also verbs. But some of them are adjectives.

First off, the role of the engineer and the designer are blurring. I've seen more people become design engineers than ever. Designers are moving into code, engineers are moving into design, and vice versa. Some of the best comments I get from people who walk up to me and say like, "Well, Impeccable gives me this shared language of design that everybody can communicate now in." But really, these worlds are all colliding in my opinion, and the typical handoff is kind of broken. The waterfall process of starting with PM, then going into design, then the handoff and critique process, and then ultimately the engineer builds it—that thing is just not real anymore. I think that's starting to collapse very quickly in small and large companies.

</details>

### 拒绝两极化困境：在像素微操与黑盒生成之间寻找控制权平衡

当前在借助数字化工具开展设计工作时，行业往往陷入两种极端的体验困境：

* **底层像素直接操纵**（Direct Manipulation: 在 Figma、Webflow 等工具中手动微调外边距、内边距与间距等微观数值）：这种交互模式的抽象层级过低，极度耗费精力，且难以发挥现代 AI 代理的自动化协作潜力；
* **全自动代理生成**（Full Agentic Generation: 仅给出一句粗略提示词便期望 AI 端到端完成全部设计）：这种方式极易生成缺乏灵魂的“AI 垃圾”（AI Slop）。从 2022 年前后泛滥的紫色渐变，到如今由 Frontier 模型生成的**克劳德米色**（Claude Beige: 泛指大量使用浅米色背景、Instrument Serif 衬线字体与斜体的固定套路模板），使得产品设计滑向**算法优衣库化**（Algorithmic Uniqlo: 指算法生成内容导致的高度同质化、缺乏辨识度的视觉平庸现象）。

要打破这种低效微操与审美同质化的双重困局，关键在于探索**人机协同**（Human-in-the-Loop: 确保人类判断力在关键决策节点介入系统的控制模式）的最佳介入高度。我们需要的是一种既不陷入像素级琐碎配置，又不将控制权完全让渡给黑盒模型的交互层次，在恰当的抽象高度对生成过程施加精准引导。

<details>
<summary>Original English Source</summary>

When it comes to the actual work of design, I feel like there's right now kind of two worlds that you can play in.

Either it's direct manipulation sort of like in the pixel space, right? So you're in Figma and you're manipulating margins, paddings, whatever it is. Or you're in Webflow or you're in some other tool where you're directly manipulating the final output or the design. Now that's fine, but then you feel like you're getting behind because everybody else is like agentic and going crazy with loops and loop-maxing, right?

And now you're going on the other extreme, which is simply telling your agent: "Please design this for me" or "Please build this." But it feels like to me at least there's this middle ground that we haven't explored enough. Like what is the exact level of control? How can we insert the human in the loop at the exact right time?

This came to mind—it's a pretty popular tweet a while ago about centering a div with Opus. Yes, not a great use of Opus, but you know it kind of speaks to that problem. It's like: okay, well when do we use which tool? When is which tool adequate to do what job?

In my opinion, right now for most work, the direct manipulation of padding, margins, spacing and so on is actually at an elevation that's too low. And on the other hand, if you go fully agentic, you get web pages like this that you would get in like 2022. Everybody here can point out the typical AI slop patterns. But the purple gradients were actually way beyond that; there are no purple gradients anymore in most frontier models. Now we just get this, and it kind of wears a different suit, as Claude would say. But it really is slop as well, it's just a moving target.

So now we have what I call Claude Beige. We have these Instrument Serif fonts, we have italics. And it's not necessarily a bad design, it's just everything that comes out of Claude design looks that way. And when everything looks the same, you kind of get Algorithmic Uniqlo, as I call it. So also not great.

</details>

### 设计无法一键达成：多轮迭代、情感语境与设计语汇的语义锚定

在设计工程实践中，必须确立一个核心认知：**设计无法通过单次提示一蹴而就**（You cannot one-shot design）。高质量、具备实效的设计必然是**富语境**（Context-Rich: 深度结合业务目标、目标受众与品牌调性）且**多轮迭代**（Multi-Shot Iteration: 伴随多方反馈与渐进式推敲的演进过程）的产物。无论是独立开发者还是大型团队，用户的真实反馈与利益相关者的多样化偏好都决定了设计过程本质上是一个探索性的非线性收敛过程，无法单纯通过向代理下达宽泛指令来解决。

当非专业设计人员尝试指导设计时，往往因为缺乏精确的设计语汇而陷入沟通僵局。进行有效设计沟通的前提，是首先明确关键的视觉与情感边界：
* **情感疆域**（Emotional Territory: 产品旨在传达的核心心理感受与基调）；
* **负向禁区**（Anti-Goals: 明确产品绝对不能呈现出的质感与视觉体验）；
* **参照系与受众**（Reference & Audience: 具体的对标基准与真实使用场景）。

为了让开发者能够跨越专业词汇壁垒，Impeccable 将设计意图提炼为高层级的**形容词与动词指令集**（如 `bolder`、`quieter`、`distill`、`polish`、`denser`、`harden` 等）。例如，`harden`（加固）并非单纯指代代码防御，而是指确保设计在多端响应式、不同性能设备及边缘场景下均能保持稳健运行；`distill`（提炼）则代表对冗余元素的克制化精简。

<details>
<summary>Original English Source</summary>

Now here's my first hot take of today's session: You cannot one-shot design.

Many people want to, and maybe we'll get there eventually. I just don't think it's possible at the current moment, maybe not ever. I think in order to build something that really looks and feels great and is effective design, you need to have something that's context-rich, which has been informed by what you're trying to do, what your audience is, what you're trying to build. And also it will have to be multi-shot. You will have to iterate on your design.

Even if you're a solopreneur—and if you're not a solopreneur, you might have different people who have different opinions, users have opinions—design is messy. It's a process, and wishing it away and just saying like "Solve this problem for me, agent" will not, unfortunately, solve your problem.

Now the other problem is if you don't know the language of design, or if your stakeholders don't know the language of design, it gets really frustrating really quickly too. If you've ever designed something, you kind of know this experience, and the inner feeling builds up...

So really what you have to ask first is: What's the emotional territory? What should this never feel like? What's the reference? What's the audience? These are all really important questions to figure out. You can't go to a human design studio, even if it's the best design studio in the world, go to a design director and say like: "You know what, I want to design for my brand," and the design director nods, says "Got it," and then walks away. That doesn't make any sense. They obviously have to figure out what it is that you're trying to build and what you're trying to get out of it.

Importantly, even on the 2026 version of AI slop—the quickly vibe-coded page—nobody decided anything here. You just one-shotted this, nobody decided anything on this page. It's maybe competent, but completely empty.

So my thesis that I make here, and what I've been trying to build over the last couple of months, is a tool that gives you just the amount of control needed to steer your agent in the right direction with adjectives and verbs.

And these are the types of words I'm talking about: words like make this bolder, make this quieter, distill this (basically simplification), polish this, make it denser, or harden this. "Harden," for instance, would mean make sure that this design works across the board—maybe the performance is bad on certain devices, maybe it's not responsive.

These are words that we use in the world of design. And I noticed when seeing two people attempt the exact same task—one is an engineer who's never really touched design at all, and the other one is a designer—there's a stark difference, even when they use the same model and same harness, in the output that they're getting based on the language that they use. So, I've been trying to put that language, basically compress it into a skill and into a system to be able to express yourselves better.

You could have a baseline, but then you make it bolder and the agent actually knows what "bolder" in your context means. You make it quieter, it knows what it means. You distill, and it knows what it means.

</details>

### 注入领域语义：将“形容词”转化为可执行的设计系统规则

如果直接向未经微调的通用大语言模型下达“让界面更大胆”（Make it bolder）的指令，模型由于缺乏领域约束，往往会根据训练数据中的模糊关联自由发挥，随机引入杂乱的渐变色、高光玻璃拟态或霓虹色彩，从而破坏既有的视觉规范。

在 Impeccable 中，这些形容词被定义为德语概念中的 **Leitwort**（主导词: 被赋予特定领域深度与系统性内涵的核心语汇）。系统在底层为每个词汇注入了严谨的设计学解释与工程约束：

1. **结构性增强而非装饰性堆砌**: “更大胆”被严格约束为对**视觉层级**（Hierarchy: 信息重要性的权重呈现）、**尺度对比**（Scale: 字体与间距的大小反差）以及**果断排版**（Decisive Typography: 具备力量感的字体排印风格）的调整，坚决禁止随意增加未经定义的渐变或发光特效；
2. **内嵌反思与自我检验**: 在指令加载体系中包含明确的自省准则（例如：“向他人展示你的成果并声明这是由 AI 做出的‘更大胆’效果，如果对方对此毫不怀疑，说明你的改造失败了”），促使代理在执行修改后对自身设计决策进行二次校准；
3. **保持设计系统一致性**: 确保所有风格化增强均在现有样式令牌与组件约束之内发生，不破坏整体设计的一致性与可维护性。

<details>
<summary>Original English Source</summary>

But then: bolder how? What does "bolder" mean in the context of your project? That's a really important question because, as you could tell at the beginning of the demo in the cold open, when you just ask GPT or Claude or whatever to "make this bolder," it doesn't know anything about what you mean. Now it has its own sense of reference of what "bolder" could mean, but it will do whatever it wants, right? It will invent new colors, it will invent new gradients. It doesn't matter what it actually means.

In Impeccable, it's not gradients, not glass, not neon, but actually hierarchy, scale, decisive type—things that don't break your design system and adequately raise the attention that the user would put on it.

This is an actual sentence from the file that is loaded when you say "bolder" in Impeccable: "Show someone your work and say AI made this bolder. If they believe you, you failed." This is something that we actually instruct the agent to do for themselves, and then the agent oftentimes reflects and is like: "I don't know, I think I did some bad work here."

An adjective is a *Leitwort*. A *Leitwort* is a German term, and Matt Pocock actually talked about this recently, who also makes some really excellent skills. This is stolen from one of his tweets, but I really think it makes a lot of sense. These are words that you basically imbue with meaning, that you infuse with meaning, and they mean something. They already mean something to the model, but then you translate this into the area that you're interested in, and the right altitude really shifts.

Now, I don't think you can solve any problems at that altitude alone; that's super important too. There is still room for the very beginning—for instance, if you just want exploratory work and you just want to get something on the screen, or you just want the last amount of polish. I don't think right now AI is good enough to replace humans for the last 5%, 10%, maybe even 20% of the work to get it from good to great. But it does actually make it better.

</details>

### 全流程语义注入与审美边界：从 Overdrive 实验到不可自动化的品味

构建有效 AI 工具的前提是对专业工作流的深度解构。设计工作流高度复杂且呈非线性特征，完整的介入链路覆盖了多个关键阶段：
* **初始化与形状塑形**（Initialization & Shaping: 确立产品框架与核心交互形态）；
* **精细化打磨与多轮演进**（Crafting & Iteration: 借助动词与形容词引导界面进化）；
* **加固与抛光**（Harden & Polish: 确保性能、响应式表现与微观视觉细节）；
* **设计资产沉淀与债务清理**（Design Debt Cleanup: 规范回流至设计系统）。

在探索设计表现力边界时，Impeccable 实验性地推出了名为 `overdrive` 的高能量指令（例如辅助生成极端复杂的**视界着色器**：Event Horizon Shader）。此类极限指令展示了在特定场景下激发 AI 创造力的可能性，但也引发了社区对“一键全自动设计”的诉求。

然而，对于“完全自动化设计”的设想必须保持清醒的拒绝。**审美与品味无法在实验室中凭空合成**（Taste cannot be lab-grown）。品味本质上由文化背景、个人经历、具体语境与历史伤痕所塑造。工具的核心使命是实现**工艺放大**（Amplified Craft: 利用智能工具磨砺并放大人类自身的审美感知），而非消除人类的判断。AI 能够承担从及格到良好的提效工作，但从“优秀”迈向“卓越”的最后 10% 到 20% 关键决策，始终依赖于人类对语境的深刻洞察与审美品味。

<details>
<summary>Original English Source</summary>

I've built tools for more than 20 years—I guess I'm dating myself here—but whenever I build a tool, I actually map the workflow first. I think about what is the actual workflow of the target user that I'm trying to help. And the workflow of design is not linear, it's messy, has many different stages, there are different people involved.

And so I kind of mapped every part of the process and thought about: What are the injection points along that route and how can we help along that route?

So you start with initialization, with the shaping process of design. You go over to crafting, to iterating with all these verbs and adjectives, and then to the actual harden and polish phase, and finally you kind of bring it back to your design system, you do some tech debt cleanup, design debt cleanup.

Now, here's one example of a command that I wasn't actually sure about shipping, and it's called `overdrive`. I basically built this command in Impeccable that tries to create something completely over the top, and it was kind of like half of a joke maybe. But people absolutely are rabid about this thing and they love it.

This is not one-shotted. This is a realistic event horizon shader that I've built for my shader library Radiant Shaders. But I did actually use the `overdrive` command for this to overdrive it even more and make it more ridiculous. So sometimes I come up with these commands I'm not sure about, I test them with the community, and once it sticks, I realize there are more people who are getting joy out of this.

An adjective with nothing behind it is just a nicer prompt. So you really have to tell the agent what you mean by the word that you're using. It has so many different meanings within its training materials that you really have to tell it.

Now here's another thing: I've gotten so many requests for an automatic way of using Impeccable. It's so frustrating. At least once a week somebody tweets at me saying like: "You know what would be cool? Just let Impeccable do all the work by itself. I don't have to decide on any command anymore." That's not the point. The point is to give you a way to steer what you want to end up with. It's never going to be a tool to one-shot design. That's not the intent. There's a pull request standing out right now that I'm going to close because of that. There is no auto, and there will be no auto in my opinion.

This is a bit awkward maybe for some of the next speakers, but I think taste cannot be amplified—sorry, I think taste *can* be amplified. I call this amplified craft. I think you can work with tools to sharpen your taste and bring out more of your taste. I really do not think it can be lab-grown. Taste by definition is contextual, it's cultural, it's scars. And once everybody replicates the same thing, it starts to become really muddy and we don't think of it as taste anymore. That's my opinion, and I know this is a hotly contested topic. But I'm not trying to solve taste with my tools.

That's what I got. This was about finding the right level of control for design. Thank you very much, and I think I have time for a few questions if you have any. Thank you.

</details>