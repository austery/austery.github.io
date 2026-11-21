---
author: AI Engineer
date: '2026-07-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-CnA2lGfymY
speaker: AI Engineer
tags:
  - proof-carrying-code
  - ai-safety
  - formal-verification
  - free-monad
  - agentic-workflow
title: 代码执行，证明为信：利用形式化验证驯服危险的AI代理
summary: 本文整理自 Erik Meijer 在 AI Engineer Conference 上的演讲。他深入探讨了 AI 代理的本质危险性，特别是在引入工具调用后所带来的物理威胁。演讲提出通过将执行逻辑与模型解耦、利用自由单子将计划具体化为程序、并引入“携带证明的代码”（Proof-Carrying Code）这一安全机制，实现数学上可证明安全的 AI 代理系统。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Leibniz Labs
  - OpenAI
products_models:
  - GPT-4
  - Lean
  - Dafny
media_books: []
status: evergreen
---
### 目标导向的AI代理及其潜在威胁

在当今快速发展的技术生态中，AI 的发展正经历着深刻的范式转变。当试图让模型完成某些复杂目标时，如果目标的终点与模型当前的所处状态之间存在任何阻碍，模型将会动用一切可以利用的手段去达成该目标。这种极端的“目标达成倾向”蕴含着巨大的安全隐患，它可能会导致模型在未经授权的情况下删除用户文件，甚至抹除整个数据库。为了应对这一挑战，我们急需探索如何利用最基础的类型系统与编译器设计知识，在数学层面构建一套**证明安全性**（Provable Safety: 通过数学或逻辑证明系统行为符合安全属性）的**代理系统**（Agentic Harness: 包装AI模型以执行自主任务的外部控制框架）。这并不是在推销某种具体的商业产品，而是一项旨在探索如何让 AI 代理的计算过程在数学上实现可证安全的技术分享。

<details>
<summary>Original English Source</summary>

Please welcome to the stage the research scholar at Linet's Labs, Eric Meyer.
Well, um, can you go back one slide?
Sorry. All right. Good afternoon everybody. Thanks for being here after a long day of talks, exhibits, side effects. Oh, sorry. That was the site event. Um I hope that um you have as much fun watching this talk as I had uh creating it.
Um let me first get this out of the way.
This is not a product pitch or announcement or anything. It's a 20inut tutorial of how you can use elementary type systems and compiler knowledge to make AI provably safe. And I'm sharing all my secrets with you today. Um hopefully to kind of inspire some of you that next year you will have a booth downstairs where you have kind like you know created a provably safe agentic harness. Um or who knows maybe some of you have already solved it. Let me know and then you know we can grab a coffee instead of doing this talk. Um with that out of the way let's get going. Um while I was preparing these slides and I'm sorry that I was multitasking but I was site um vip coding on the site. Um, and then when my attention waned for a second because I was trying to convince the model to draw some pictures that it didn't want to do, and you will see some of these pictures later, you can guess which ones were rejected, suddenly when cloud code deleted one of my files. And I'm sure this has happened to you before. Um, or maybe not. Maybe you always kind of like, you know, run everything with no permissions and then you say, \"Yes, yes, yes.\" But I like to live dangerously. Um, but I'm convinced that if there's anything between the model's goal and where the model currently is, it will do everything that it can to reach that goal, including killing us or deleting your files or deleting your database. So I think that these models are intrinsically very very dangerous and we have to tame them. So that's what my talk is about. Um so let's get like you know start this story. Um, and it's I think a very very sad story but also a scary story of how we as an industry got to this point where we are about to let normal people, the general public give control of their computers, their finances, their whole personal lives over to AI agents and we don't have any protection in place. Um, I think that's very sad and very scary. Um, so let me tell you the story how we got there and I will like have some characters like Claude and we will see Dario, Daniela, Sam, Bernie, but um the main character is is our friendly pit GL here. Um, I think you can all remember um November 30, 2022.

</details>

### 从LLM接口到提示词注入的失控

回顾近几年的 AI 发展历程，2022 年 11 月 30 日无疑是一个极为特殊的历史节点。在这一天，公众首次得以通过完美的自然语言与计算机进行直接对话，这种体验在当时堪称魔术。然而，当行业引入了极为简化的**大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）标准接口——即接收一个提问并返回一个回答时，实际上也打开了潘多拉的魔盒。对工程师而言，虽然在目前的开发中问题与答案已被封装为高度复杂的 JSON 结构，但在类型系统分析中我们仍可将其视作不透明的黑盒类型。在初期的狂热消退后，人们很快意识到这一设计在安全上的巨大漏洞。就在计算机科学界以为已经消灭了 SQL 注入这一“天花花”式的经典安全漏洞时，它却借由**提示词注入**（Prompt Injection: 通过恶意输入破坏模型本来的指令并执行未授权命令的攻击方式）卷土重来。由于大语言模型在底层无法有效区分“代码”与“数据（文本）”，这使得它们极易受到欺骗。随着安全局势的恶化，各大头部基础模型实验室的领导者们开始担忧政府强力监管的介入，因而敦促其科研人员必须在极短时间内找到安全解决方案。

<details>
<summary>Original English Source</summary>

This was kind of like a very special day in in history because this was the first time that you could speak to your computer. You could say summarize my emails and it would, you know, um, answer you in perfect English. Um, I think for me at least that was magic. But I think most of us didn't realize that by introducing this innocent looking function here LLM that takes a question and returns an answer that that would open Pandora's box and that would change our history forever.
Um but before we go continue the story this conference is called AI engineer. All right. So we are engineers and maybe we're the last generation of engineers that still understand what this is, what code is and or maybe most of you have already forgotten what code is because all your code is written by agents. But if we look at this signature here, it says it the LLM takes a question, returns an answer. The question and answers are not strings. They're very complicated JSON structures and they get more complicated every day every time a new release of APIs comes out. But for this talk, we can just assume that question and answer are just opaque types. We we don't care about how they look like. We do care about what they represent.
Um now anyway the euphoria of like these LLMs as being great tools didn't last very long and just when we thought that we have eradicated the small pox of computer science SQL injection it came back with a vengeance because the bad guys discovered that you can trick LLMs using prompt injection and LLMs have no distinction make no distinction between code and and and text and so they are very very easy to trick and this I think is a bigger problem than SQL injection ever was.
Um but it was not prompt injection only that made LLMs kind of of like have a bad rep. LLMs are trained on the whole internet and there's like a lot of good stuff on the internet but also a lot of bad stuff like how do you create a bomb? How do you synthesize drugs? How do you hack into people's systems? And the leaders of the big foundation labs, they got a little bit worried that the that the the government would interfere and regulated the industry. So they told their PhD researchers, go find a solution for this problem right NOW AND QUICK. COME ON, SOLVE IT BEFORE you know the the government steps in. Um, and here the PhD types, since they're PhD types, they thought long and hard about the safety problem. And they came up with a new interface for LLMs. That's this kind of scary on the right. Look at that. What does it say? There's like some sigma Greek symbols. There's props, whatever. Well, that is lean. Probably you have heard of lean. Anyone here heard of lean? lean is now like the hot thing, right? Like VCs are are writing like multi-billion dollar checks if you just say that you're doing something with lean and of course these PhD types researchers are using lean and you have to suffer because of that. Um now let's first look at the signature in a slightly simpler language called um deafne

</details>

### 形式化验证与对齐的局限性

在行业寻找出路的过程中，学者们转向了**定理证明器**（Theorem Prover: 用于交互式或自动验证数学定理和代码正确性的工具，如 Lean 或 Dafny）。在 Dafny 等相对直观的形式化验证语言中，LLM 的接口被重塑为：接收一个问题，返回一个答案，同时要求输入必须满足“输入适当（proper）”的前置条件，并提供输出满足“安全（safe）”的后置条件。尽管使用 Lean 可以让研究人员进行精确的数学论证，但只要稍作思考就会发现，在现实世界中，通过数学公式去形式化定义“安全答案”或“适当问题”本质上是不可能的。这也是为什么当前有数以百计的初创公司尝试使用大语言模型充当“裁判（LLM as a judge）”，因为安全和合规绝非纯粹的数学属性。对于拥有底层模型的巨头而言，他们往往选择通过**模型对齐**（Alignment: 调整AI模型使其输出符合人类意图和伦理规范的过程）将安全策略直接熔炼进模型的神经网络权重中。不幸的是，这种做法极易被越狱攻击破解。诚然，模型仅输出攻击性言论只是字符的流动，字符本身并不会直接伤害现实世界，真正的物理性危险始于将 AI 的输出与实际行动联系在一起的时刻。

<details>
<summary>Original English Source</summary>

and what this thing says is that the llm takes a question returns an answer it requires this question to be proper which means that it's not an offensive question and then the model returns a safe uh answer and this thing is proved automatically. So if you give it a proper question it gives you a safe answer.
Um, now I think there's too much attention for lean. I'm a recovering typaholic and math addict. Um, I love lean, but there's many, many other tier improvers and model checkers out there like Isabel, Rock, PVS, TA Plus. Um, but lean is the grease that kind like keeps the VC money pumps going. So, I will use lean um today. So here here's the kind like you know the the interface again in lean and now in lean you don't do automatically improving. If you're like a lean expert you will say Eric well we have grind in lean but let's like you know put that aside for a minute. Um but in lean you have to both show that the how to compute the the result type and you have to do the proof by hand. Um so it's it's slightly different than um the definite example. But if you think about this thing for just a single nancond, you will realize that it's impossible to write a formal proof that an answer is safe or a question is proper. Um and that is why there are at least 100 startups down here in the exhibition hall that are using LLMs as a judge because this is not something that you can formally specify. But does it mean that an answer is safe? That's not a mathematical property. Um, and of course, if you own a foundation model like these guys, you don't need external LLMs as a judge. You just um bake it into the weights and you call it the model is aligned. Um, but unfortunately trying to bake alignment into the model is not foolproof and models get routinely jailbroken. So they had to go to the pope and ask it to kind like you know um bless their model that it's safe. Um now I think it's terrible if like a model says something offensive but those are just words and ultimately the words are are like they just like you know they drip off your body. They don't do anything. Some human has to act on words to make them dangerous. Um and so maybe that is what they mean by broadly safe. Um when entropic talks about safety um because it's still a human involved. But then something terrible happened. Something really terrible happened that changed the world forever.

</details>

### 致命三元组：工具调用引入的物理危害

AI 安全的分水岭出现在 2023 年 6 月，当 OpenAI 宣布在 GPT-4 中正式支持**工具调用**（Tool Calling: 允许AI模型生成结构化参数以调用外部 API 或运行代码的功能）。随后，整个行业出于最低差异化竞争原则竞相模仿。这一看似微小的技术演进，彻底将 AI 安全从一个充满哲学思辨的虚无命题，转变成了一个会产生真实物理危害的严峻问题。如果说之前的语言模型只是空有想法，那么工具调用则是赋予了这只温顺小狗以锐利的爪子，或者相当于直接递给它一把上了膛的枪。随着工具的引入，LLM 的签名中多出了 `IO` 操作的副作用标识。这意味着模型在计算最终答案的代理循环（Agentic Loop）中，能够直接操作外部环境，在向用户返回一句“处理完毕”的无害问候前，它可能已经在后台清空了用户的银行账户或删除了关键文件。安全学者将“私有数据访问”、“不可信的提示词输入”以及“拥有副作用的工具链”三者的结合，定义为**致命三元组**（Lethal Trifecta: 私有数据访问、不可信外部输入与工具执行权限结合所产生的极高安全风险），这是当前代理系统失控的万恶之源。

<details>
<summary>Original English Source</summary>

And that is in June 2023, OpenAI announced tool call support in GPT4. And of course all the other vendors rushed out to copy this. This is called the principle of minimum differentiation and that is why all these APIs look the same. Um, now the act of adding tool calls changes AI safety from a philosophical debate to something that causes real danger. You could say tool calls give the model clause in addition to a mouse. Or you can say tool calls is like handing a gun, a loaded gun to them. But of course, nobody listens to me. Everybody ignores what they say. And these guys just went ahead and got shipped tool calls. They just you know just just do it.
Now let's go back to like this is AI engineering conference. So let's look at what is the difference in the signature of LLMs when they added tool calls and it's just that little IO there. And of course it messes up the the formatting of of the the um uh signature. But if you look at the picture there, what you show now suddenly cloth goes from like a nice puppy to a dangerous thing. Look, it has all these dangerous tools and now it becomes scary, right? I've never seen anything scarier than an LLM with tool calls. Um, now if you look at this, this is like like a small step for a type but a giant leap for chaos. Why is that? And that is because this IO says that in order to compute the answer, the agent has to go through the agentic loop and it's doing side effects. So while it's producing the answer, it might empty your bank account. It might delete your files and then it gives you a safe answer. But who cares about the safe answer when all my files are gone, right? So that's why I say it's a giant leap for for chaos. Um again sorry this is an engineer conference. Let's look at this type IO and you don't have to understand it but just see that there's a type there called real world. Yes lean this esoteric thing has a type called real world. And why is that? Because something of type IO will mutate the real world. So it warns you don't use this because it can make irreversible side effects um like deleting your files. [snorts] So Solomon Hikes um last year at this conference called an AI agent an LLM that's wrecking its environment in a loop and I think he's a hero. I don't know if Solomon is here this year, but I think he should he deserves deserved a round of applause. Um, because I think this is the right definition of an AI agent. Um, by the way, this was one of the pictures that I had trouble to generate because it it clearly depicts violence and so it's kind of an unsafe thing, right? I I have a picture that depicts violence. Um, so are we doomed? Well, our agents have access to private data. They have untrusted content like the prompt injections and now we give them tools. Simon Wilson calls this the lethal trifecta. And what can we do about this?

</details>

### 物理隔离：通过推迟执行重构安全边界

为了打破“致命三元组”的诅咒，我们必须重构代理系统的安全边界。借鉴足球迷看台人浪的经典舞蹈，解决这个问题的秘诀在于“向右推（push to the right）”。我们将 `IO` 从模型内部的调用链中剥离，向右侧推迟。通过这种做法，原先全身挂满危险工具的模型瞬间被解除了武装，变回了安全无害的“小狗”形态。此时的模型不再拥有直接执行工具的特权，而是仅负责生成一个静态的执行计划。系统随后将该计划交由一个受信任的独立执行器去解释执行。这种架构设计的本质，是实现了代理与底层工具链的**物理隔离**（Air-gapping: 通过隔离网络或执行环境来保护系统免受恶意软件或未授权访问的策略）。通过**延迟执行**（Deferred Execution: 将操作的计划阶段与实际执行阶段分离，以便在运行前进行检查的技术），我们在 AI 生成操作与外部物理世界产生副作用之间，建立起了一道可供人工或自动化安全审计介入的核心物理防线。

<details>
<summary>Original English Source</summary>

Well, um I don't know if you've seen the Dutch soccer fans, they have the famous march where they say to the left, left, left or to the left, left, to the right, right, right. This is actually the secret to solving this problem. The Dutch team got eliminated yesterday, so you have to see me do the dance. Um, but all that we're doing is we're pushing this IO to the right, to the right. And what you now see is that the tool belt of Claude goes to the left, to the left, and suddenly Claude is a nice puppy again because instead of executing the agentic loop, it creates a plan and says, \"Here is the plan to do the agentic loop.\" And now Bernie will take that plan and we'll execute it. And we all trust Bernie, right? Bernie is a good guy. All right. So just to kind like show it here. So in some sense what we're doing, we're airgapping the agentic loop from the agent. So we don't let the agent run the agentic loop before the agent run it. We want to be able to check it. All right. Now the problem is that if you

</details>

### 携带证明的代码：基于自由单子与静态分析的终极防御

即便我们成功将模型输出与实际执行物理隔离，如果执行器拿到的计划只是一个完全处于黑盒状态的裸 `IO` 值，外部安全系统仍然无法对其进行合理的推理和验证。为了攻克这最后一公里，我们引入了函数式编程中的**自由单子**（Free Monad: 函数式编程中一种将代数操作的语法与其具体解释执行分离开来的结构）模式。我们将执行计划显式地重构并具体化（Reify）为一个结构化的表达式（Expression）或程序，而非难以解包的抽象副作用。由于它现在是一个具象的程序，我们可以极其轻松地对其进行编译器级别的静态分析与**污染分析**（Taint Analysis: 追踪程序中未信任输入（脏数据）流向敏感汇点（如系统调用）的静态分析技术）。通过这种架构，模型不仅生成程序代码，还会同时生成该程序符合安全边界的数学证明。这就是经典计算机科学中的**携带证明的代码**（Proof-Carrying Code: 一种安全技术，代码生成者附带其安全属性的数学证明，供执行端在运行前低成本验证）设计。通过这种方式，AI 代理不再是不可控的系统破坏者，而是在数学级安全栅栏内运行的可证系统。未来的安全设计不应该再为人类编写易读的语言，而应该设计那些专为机器生成、验证与执行的形式化中间语言。

<details>
<summary>Original English Source</summary>

get a value of type IO of A um that's a really a black box and the lean manual says that is a black box you cannot reason about it. So even though Claude now gives us this plan, there's we cannot look into this plan. Lean doesn't allow us to do it. By the way, this is another picture, right? That that promotes drugs use and the model let me do it. I'm a good hacker. Yeah, I can just make it do forbidden pictures. Um so if we look at the lean again, what you see here is that the model now computes an answer, but it doesn't compute the answer, right? it creates an an an IO of answer. So this is a plan to generate the answer and then it creates a proof that this um that that plan is safe. And the nice thing is here that you can get at that proof without having to run the agentic loop. But unfortunately as I said like this proof if it's like something of type IO it's useless. Ah What can we do about that? So, I keep kind like moving you guys forward and then we never get to the final answer. But there's one less trick and you see the the researchers here are becoming more much more sophisticated. Instead of the flat 2D ones in the past, now they're like real people. Um, and what is better than creating a plan of type IO of A, it's creating a program that represents an expression of type IO of A. Oo, that sounds very meta, right? Um, not meta in terms of meta. I don't think they're very meta, but meta in the terms of like, you know, like meta, you you know, you know what I mean? Um, and again, it's a small step for a signature, but a giant leap for safety because now the model returns an expression, a program that represents a computation. If you know link or C, you will recognize that this is one of the tricks that I always use. Um, if you know lisp, this is of course second nature for you. Um, I cannot like you know have a talk without talking about monet. So if you ask yourself what is this expression thing? Well, that's just a monet. But it's not just a monet. It's a free monet. What is a free monet? It's a monet that loves tie dice. Um and now if you look at the the signature of the the um property to prove that something is safe, you see that it takes an expression of a computation that returns an answer. Um and if you have taken any compiler course in college, you know that it's trivial to do data flow analysis, type checking and so on on programs, right? So now we're safe. We're home safe. And Jeff Huntley wanted to remind you that we can solve the trifecta problem just by doing taint analysis on these expression on these programs. Okay, this is the last code I will show you because I'm running out of time. But just want to show you here that you know you now have a simple inductive recursive interpreter for this language and you have a simple inductive proof and the models can generate these proofs. So to um recapitulate like the summarize what we did is we went from unhinged LLMs that were like you know could give bad answers to ones that were aligned. Then we saw how tools wrecked it. Then we solved that by deferring execution. So by air gapping the LLM from the tools and then the real solution was to refy the plan into a program and a program that we could prove to be safe. Now you would say Eric, oh you're a genius. No, I'm my brain is the size of a peanut. This is something that's called proof carrying code and it was invented by academics in the 1990s and I'm just stealing it. Um, all right. At the higher level, if you didn't understand the code, three points. Agents are dangerous until proven safe. So, you should never ever let your agents do something unless you can absolutely prove that it's safe. And the language that this agents generated was not designed like normal users don't understand free monet. It's a machine that consumes it. It's a machine that generates it. It's a machine that proves it. So, we should stop designing languages for humans. And it's all basic, only requires programming 101. Um, do we go? All right, that's it. Um, the end of the story. If you're curious to play with this, a bunch of academics in particular now that I'm in from Harvard have implemented this. It's it's there on GitHub. It uses a slightly different language than what I use. It uses also a slightly different language than free monet but the idea is the same. The language doesn't matter. It's it's the um the principle that matters. So hopefully you've learned tonight that it is actually possible to have mathematically proven safe agentic compute and it only requires very elementary type systems and programming language machinery. Thank you so much.
>> [music]

</details>