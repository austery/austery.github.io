---
author: AI Engineer
date: '2026-07-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=GgLQ02aO-hs
speaker: AI Engineer
tags:
  - task-model-separation
  - ai-programming
  - prompt-optimization
  - eval-automation
  - last-mile-learning
title: 将任务与模型分离的不合理有效性：DSPy 框架深度解析
summary: Maxime Rivest 和 Isaac Miller 介绍了开源框架 DSPy，其核心理念是将 AI 任务的定义（specs、code、evals）与模型及实现细节分离。通过函数式编程思想，DSPy 使 AI 程序可复用、可组合、可测试，并支持自动优化。演讲涵盖了从个人发票提取到企业级应用（如 Shopify 成本降低 550 倍）的案例，并展望了 DSPy Flex 和定性学习等未来方向。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - DSPy
  - Shopify
  - MIT
  - Berkeley
products_models:
  - DSPy
  - DSPy Flex
media_books: []
status: evergreen
---
### 函数式 AI 编程

**[Maxime Rivest]**: 哇。Isaac，我自己，以及整个 **DSPy** 社区都非常感激今天能来到这里，与大家探讨 AI 编程、DSPy，以及将任务与模型、其框架和所有实现细节分离开来的不合理有效性。当你思考编程时，如果我们想频繁重复某个任务，我们会把它做成一个函数。我们相信，对于 AI 程序也应如此。函数非常棒。函数是可复用的、可组合的、可测试的，并且是可优化的。要创建一个函数，你需要给它一个名字，定义一些输入和输出，然后在其中实现一些逻辑。你可以数千次地复用你的函数。你可以优化它，也可以将它组合成更大的程序。函数的一个真正优点在于，你还可以将其打包并分发，其他人只需了解其顶层的约定就能使用它，并将其视为一个黑盒。DSPy 将所有这些特性带给了 AI 程序。DSPy 是一个开源的 Python 软件，正如我所说，它能让你将这些特性带入你的 AI 工作流和 AI 程序中，并为你提供了所需的所有工具。

<details>
<summary>Original English</summary>

**[Maxime Rivest]**: Wow. Isaac, myself, all of the DSPy community are so grateful to be here today to get to talk to you about AI programming DSPy and the unreasonable effectiveness of separating the task from the model, its harness, and all of the implementation details. When you think about it, in programming, if we want to repeat the tasks often, we make it a function. We believe the same should be true for AI programs. Functions are awesome. Functions are reusable, composable, testable, and optimizable. To make a function, you give it a name. You define some inputs, some outputs, and then you have some implementation logic inside of it. You get to reuse your functions thousands of times. You can optimize it, but you can also compose it into bigger programs. One of the really nice things about functions is that you can also package it and distribute it and someone else can use it and they just need to know about the contract on top of it to use it and they can treat it as a black box. DSPy brings all of these properties to AI programs. And so DSPy is an open source software in Python that lets you, like I said, bring these properties to your AI workflows and AI programs. And it gives you all of the toolings you need to do that.

</details>

### 为何需要分离

**[Maxime Rivest]**: 为什么你需要这个？嗯，在过去三年里，我们领域发明了很多术语。它发展得很快。我们每隔一周就有新模型出现。我们有新技术、新策略。如果你像我一样，你会想尝试所有这些。但这些在不同时间点出现的新具体技术，真的能对你的任务、你的工作有帮助吗？嗯，这些都只是实现策略，而你想把它们放在一个清晰的约定里。如果你为你的重复性 AI 任务定义了一个输入接口和一个输出接口，你就可以在内部进行探索。你会获得很大的灵活性。让我们把它具体化到 AI 上。我发现的第一个 AI 程序是在我接触 DSPy 时，我农场有一些发票，我想提取它们来做税务。我想从中提取税额。我做的另一个 AI 程序是，在我电脑的键盘上，我有一个小命令，它能读取我的键盘快捷键，读取我的剪贴板，然后为我纠正语法。有时我还想为了清晰度而重写。所以我有另一个程序，它接收文本，为了清晰度重写它，然后放回我的键盘上，这是一个命令，这样我就可以有很大的灵活性，并在其中将其带到不同的地方。我可以随心所欲地更改它。一个新模型出现，我就可以更改它。这非常容易，因为我的接口是固定的。我会跳过那个例子。

<details>
<summary>Original English</summary>

**[Maxime Rivest]**: Why do you want that? Well, we have been inventing a lot of terms in our fields in the last three years. It's growing fast. We have new models coming every other week. We have new techniques, new strategies. And if you're like me, you want to try all of them. But will any of these new specific techniques coming out at a different time really help on your task, on your job? Well, these are all just implementation tactics and you want to put them inside of clear contract. If for your repeated AI task you define an input interface and an output interface, you get to play in the internals. You get a lot of agility. Let's make it concrete for AI. So my first AI program I made when I discovered DSPy was that I had some invoices from my farm and I wanted to extract them to do my taxes. I wanted to extract the tax values from there. Then another AI program I did is that on my keyboard in my computer, I have a little command that reads my keyboard shortcuts, read my clipboard, and will correct the grammar for me. Sometimes I actually wanted to also rewrite for clarity. So I have another program that takes text, just rewrites it for clarity, put it back on my keyboard, and that's a command, and then I can like have a lot of agility and bring it different places inside of that. I can change it however I want. A new model comes up and I can change that. It's super easy because my interface is fixed like that. I'll skip that one.

</details>

### 宏大目标与核心三要素

**[Maxime Rivest]**: 但它们并不局限于非常简单的事情和小型输入输出。你可以用 AI 程序做非常宏大的事情。所以在这个例子中，你可以拥有你的整个收件箱，当一封新邮件进来时，你想撰写一封新的回复草稿。我们可以在 DSPy 中使用 **RLM（递归语言模型）** 来实现。这个想法来自我们的社区，或者更像是我们可能都在做的代理工程或氛围编码。你可以给它一个规范和一个代码仓库，然后得到一个 PR。这些都是可重复的任务。正如我一直告诉你的，当你固定了那个边界，你就可以专注于上层的“如何做”，然后在内部，你可以通过一个简单的提示进行一个小型对话。你可以基于那个提示进行集成。代理出现了，你就把它改成代理。工具被发明出来，你就添加工具，然后我们进入循环工程。你也可以把它放在里面。外部的任何东西都不会改变你的集成，其他任何东西也不会改变。当你有了这样一个硬边界，你也可以开始自动优化。

<details>
<summary>Original English</summary>

**[Maxime Rivest]**: But they're not restrained to very easy things and small input outputs. You can be very ambitious with AI programs. So in this examples, you could have your entire inbox and a new email coming in and you want to compose a new drafted reply. We can do that in the DSPy with RLM recursive language models. This is an idea that came from around our community or more like things we probably all do agentic engineering or vibe coding. You can give it a spec a repository and you get a PR. Those are repeatable tasks. And so as I have been telling you when you fix that boundary you can focus on the how on the top and then inside of it you can have a little chat with just a simple prompt. You can integrate on that prompt. Agents come out you change it to be an agent. Tools gets invented you add tools and then we get into loop engineering. You put that inside of it too. Anything on the outside of it doesn't change your integration and anything else doesn't change. And when you have such a hard boundary, you can also start to automatically optimize.

</details>

**[Maxime Rivest]**: 但是，仅凭那个简单的签名，你如何自动优化呢？这还不够。这不足以指定你的任务。甚至在 **ChatGPT** 出现之前，DSPy 的创建者就已经开始思考这个想法：你需要三样东西来指定你的任务。如果你拥有这种语言和用编程语言表达任务的能力，你就可以开始自动优化并将实现细节委派出去。所以，第一是“应该发生什么”。这是指令。我一直在向你们展示的签名就是其中的一部分。在屏幕上，你看到了一个 DSPy 真实脚本的开头。你在顶部设置你的模型。你配置它，它完全独立于这里的签名，在这里你有自然语言指令来提取所有税款，如果字迹难以辨认则输出零。然后你说，我将给你一个输入，它将是一个字符串，我希望你给我一个输出，它将是一个字符串和一个浮点数。这是用自然语言表达我的需求。如果你想想看，这是非常强大和高效的。如果你有一个朋友过来和你玩棋盘游戏，你给他们指令，他们就准备好玩了。但如果你想做像 **AlphaGo** 或 **AlphaZero** 那样的事，你告诉他们你只能从例子中学习，那你将度过一个漫长的夜晚。

<details>
<summary>Original English</summary>

**[Maxime Rivest]**: But how can you automatically optimize with just that simple signature? This is not enough. This is not enough to specify your task. And even before ChatGPT came out, the creator of DSPy had started to land on this idea that you need three things to specify your task. And if you have this language and this ability to express your task in a programming language, you can start to automatically optimize and delegate away the implementation details. So the first one is what should happen. This is instructions. The signatures that I've been showing you are part of that. Here on the screen, you see the beginning of a real script in DSPy. You set your model at the top. you configure that and it's fully independent of the signatures here where you have natural language instruction to extract all taxes and if it's illegible to output zero then you say it I'm going to give you an input it's going to be a string I want you to give me an output and it's going to be a string and a float this is natural language expressing my needs this is very powerful and efficient if you think about it if you have a friend over coming to play a board game with you and You give them the instructions and they're ready to play. But if you want to do like AlphaGo or AlphaZero and you tell them you're just going to learn from example, you're going to have a long night.

</details>

**[Maxime Rivest]**: 然后，第二是“必须发生什么”。你有一些约束条件，它们必须被遵守，必须被强制执行。最好的方法是用代码。所以，我希望你看到第三行、第四行。你有 `self.extract` 和 `self.recheck`。你可以看到我们在 `extract_taxes` 上做了一个预测，并且在 `extract_taxes` 上做了一个思维链。第一个是一个普通的程序。第二个让它进行一些推理。现在我把它们放在 `forward` 方法内部，你可以看到在 `if not bread_tax` 中。这是我的一个要求：如果我第一个简单的普通程序没有提取到我的税款，我希望你带着更多的推理重新运行。我的意思是，我必须把税弄对。我的另一个要求是，如果值低于零，就抛出异常，我想把它展示给人类。我不想让它通过。这不会改变。即使我有了 **AGI**，我也希望它不会犯错。但无论预测器中是什么，如果它们犯了这些错误，我仍然希望这些事情是真实的。

<details>
<summary>Original English</summary>

**[Maxime Rivest]**: And then the second one is what must happen. There are some constraints you have that they have to be listened to. They have to be enforced. The best way to do that is with code. So I want you to go to the third line, a fourth line. You have self extract and self recheck. You can see we're doing a predict on the extract taxes and we're doing a chain of thought on the extract taxes. The first one is a vanilla program. The second one makes it do some reasoning. Now I'm taking them inside in the forward and you can see in the if not bread tax. This is a requirement I have that if my first simple vanilla program doesn't extract my taxes, I want you to rerun with more reasoning. I mean, I got to get my taxes right. And then another requirement I have is if the value is below zero throw, I want to show that to a human. I don't want to let you go. This will not change. Like even if I have AGI, I would hope it doesn't make mistake. But whatever is in the predictor, if they make these mistakes, I still want these things to be true.

</details>

**[Maxime Rivest]**: 所以，最后一个是“好的结果看起来像什么”。当我年轻的时候，我和父亲在农场，我问他：“你怎么知道这棵树是枫树？”他无法告诉我。他无法给我关于如何知道这棵树是枫树的指令。他当然也无法给我关于如何知道这棵树是枫树的代码。所以随着时间的推移，通过例子，我学会了如何知道一棵树是枫树。但这并不仅限于对植物进行分类。它也适用于你规范中的所有长尾，那些更潜在的东西。这有时是你为什么需要实习，为什么会有导师和学员的原因。你看到很多例子，有很多成功行为的长尾，你必须看到并学习。现在你拥有了所有这些，你完全表达了。你拥有了所有这三种语言，你可以把它们放在一起。你有了规范、代码和评估。现在你的目标被完全指定了。所以你可以开始优化。你可以使用像 **Japa** 这样的东西来处理你的指标和你的程序。你可以开始优化了。在 DSPy 的初期，芯片还不存在。模型还不够好，无法优化。所以我们使用代码来寻找少量示例，以使基础模型以正确的方式行动。然后模型变得更好了，所以我们可以自动优化指令。在未来，我们开始能够越来越多地从实现细节中解放出来，并将其委派出去。最终，我们在 DSPy 中的希望是，你可以坚持所有这些，然后新闻和实现细节将为你自动化。Isaac 将向你们详细介绍过去一年发布的内容、我们现在发布的内容以及我们所有的未来计划。谢谢。

<details>
<summary>Original English</summary>

**[Maxime Rivest]**: So the last one is what good looked like. And when I was young, I was on the farm with my dad and I asked him, "How do you know that this tree is a maple?" And he couldn't tell me. He couldn't give me the instruction on how to know this tree is a maple. And he certainly couldn't give me code on how to know this tree is a maple. And so through time with example I learned how to know that a tree is a maple. But this is not limited to things like classifying plants. It's also for all of the long tails in your specifications that are things that are more latent. These are sometimes a reason why you would do internship and you would have a mentor and a mentee. You're looking at a lot of examples and there are long tales of successful behaviors that you have to see and learn. Now that you have all of these, you have express fully. You have all these three languages you can put together. You have the specs, the code, and the evals. And now your goal is fully specified. And so you can start optimizing. You can use things like Japa on your metrics and on your program. And you can start optimizing. At the beginning of the DSPy, the chip didn't exist. The models were not good enough to optimize. And so we were using code to find few shots examples to make the base models act in the proper way. Then models got better and so we could automatically optimize instruction. And in the future we are starting to be able to be liberated more and more from the implementation details and delegate that away. And at the end our hope in the DSPy is that you can stick to all of that and then just the news and the implementation details will be automated for you. Isaac will talk to you a lot more about what has been released in the last year, what we're releasing now, and all of the future plans we have. Thank you.

</details>

### 企业级应用与成本效益

**[Isaac Miller]**: 谢谢，Max。所以，我们给了你们一个关于规范、代码和评估的相当抽象的概述，但这些并不仅限于学术领域。它们被一些最大的企业用于生产，并获得了巨大的收益。我们看到在企业中使用 DSPy 有两个主要好处。首先，你的实现变得更便宜。当你在实现上具有灵活性时，你可以利用“苦涩的教训”来搜索不同的解决方案，找到能廉价解决你问题的方法。你可以利用这一点扩展到以前用更昂贵的实现无法实现的数据规模。**Shopify** 的成本降低了 **550 倍**。他们能够做到这一点，是因为他们从一个昂贵的模型转向了一个便宜的模型，但他们可以保持相同的评估，继续迭代内部的业务逻辑，并尝试新事物。这里有三个很棒的案例研究，你们应该在演讲结束后去看看。它们提供了很多关于如何在你自己的企业中做到这一点的细节。

<details>
<summary>Original English</summary>

**[Isaac Miller]**: Thanks, Max. So, we've given you a pretty big abstract overview of specs, code, and evals, but these aren't things that are just restricted to the academic sphere. These are used in production by some of the biggest enterprises for massive gains. And we see two main benefits when you use DSPy in the enterprise. First is that your implementation becomes cheaper. When you're flexible to what the implementation is, you can use the bitter lesson to search over different solutions, find something that solves your problem cheaply. And you can use this to scale to data sizes that weren't possible with a more expensive implementation. Shopify 550 times cheaper. They're able to do that because they went from an expensive model to a cheap model, but they could keep the same evals, keep iterating on their business logic inside, and try new things. There's three awesome case studies here, and you should check them out after the talk. They give you a lot of details on how you can do this in your own enterprise.

</details>

### DSPy 生态系统与新技术

**[Isaac Miller]**: 现在，你想要在 DSPy 生态系统中构建的部分原因是，我们不断添加新技术供你尝试。重要的是要知道，我们添加的这些技术都不一定能解决你的问题，因为那是你的工作。我们能做的是为你解决一些子问题，使你的实现更容易。例如，**Alex Zang**，一位 **MIT** 的博士生，发表了一篇名为“递归语言模型”的论文。递归语言模型是一种解决某些长上下文程序的方法。你猜怎么着？我们可以把它引入 DSPy，让你尝试，看看它是否对你的长上下文任务有帮助。也许会有，也许不会。但关键是，它只有一行代码，你的签名保持不变。这才是最重要的。一切保持不变，你可以看看这是否能解决你的问题。就在过去一年里，我们有很多这样的例子，来自 DSPy 社区内部和周边的人。我们有 RLM。我们有 **Jeepa**，这是一个来自 **Berkeley** 的令人难以置信的提示优化器。还有 Better together multiodule gpo。所有这些令人难以置信的研究创新，你只需身处 DSPy 生态系统，就可以在你的实现中尝试它们。

<details>
<summary>Original English</summary>

**[Isaac Miller]**: Now, part of the reason why you want to build in the DSPy ecosystem is that we're constantly adding new techniques for you to try. And it's important to know none of these techniques we add will definitely solve your problem because that's your job. What we can do is we can solve sub problems for you that make your implementation easier. For instance, Alex Zang, a PhD student at MIT, came out with this paper called recursive language models. Recursive language models are a way to solve some kinds of long context programs. And guess what? We can bring this in to DSPy for you to try see if it helps your long context tasks. Maybe it will, maybe it won't. But the thing is, it's one line and your signature stays the same. That's what's important here. Everything gets to stay constant and you get to see if this solves your problem or not. And we've had a number of examples of this just in the last year from people building in and around the DSPy community. We've had RLMs. We've had Jeepa which is an incredible prompt optimizer out of Berkeley. Better together multiodule gpo. All these are incredible research innovations that you get to try in your implementation just by being in the DSPy ecosystem.

</details>

### DSPy Flex 与定性学习

**[Isaac Miller]**: 我们在 DSPy 4 中还有更多即将推出。今天我很兴奋地想和你们谈谈其中的两个：**DSPy Flex** 和 **定性学习**。DSPy Flex 是一种新型模块。在 DSPy 中，当我们让你优化事物时，它从少量示例开始，然后变成提示，现在正在变成代码。对于你想要实现的任何函数，你实际上可以随着时间的推移学习一个框架来解决那个函数。这完全是自定义的。只要它能解决你的业务问题，你就不关心实现。因为你已经定义了规范、代码和评估这三个核心部分，所以你创造了衡量的方法。

<details>
<summary>Original English</summary>

**[Isaac Miller]**: And we have more coming in DSPy 4. I'm excited to talk to you about two of those today. DSPy Flex and Qualitative Learning. DSPy Flex is a new kind of module. In DSPy, when we let you optimize things, it started with few shot examples, then it became prompts, and now that's becoming code. for any function that you want to implement. You can actually learn a harness over time to solve that function. And this is completely custom. And you don't care about the implementation as long as it solves your business problem. What you've created ways to measure because you've defined the three core parts of specs, code, and evals.

</details>

**[Isaac Miller]**: 我兴奋地想谈的第二件事是定性学习。AI 工程中最困难的问题之一就是构建评估。这很困难有几个原因。一是对于任何现实世界的问题，定义“好的结果看起来像什么”都非常具有挑战性。第二是，当你定义“好”时，很多时候你不得不丢失细节。一封邮件是好是坏，它所包含的信息远少于你知道那封邮件需要改变什么才能改进。第三是，每当你创建一个“山丘”和一个数据集时，你实际上是在试图为现实创建一个代理。如果我们能反过来利用现实来自动告知我们的评估呢？定性学习要问的是，我们如何减少这种问题？我们如何减少辅助？这目前还是一个研究问题。但我们相信，模型现在已经足够好，可以解释环境中存在的任何文本反馈，并将其转化为评估和一个模型可以攀登的“山丘”。因此，当你从生产环境、其追踪、用户行为、产品分析中获得更多反馈时，它会问你，是模型在问你关于数据应该如何表示的问题。当你这样做时，模型可以随着时间的推移迭代地优化这个“山丘”，并继续攀登它，以解决你实际的业务问题。

<details>
<summary>Original English</summary>

**[Isaac Miller]**: The second thing I'm excited to talk about is qualitative learning. One of the hard hard problems in AI engineering is building evals. And there's a few reasons why this is hard. One is that defining what good looks like is really challenging for any real world problem. The second is that when you define good often times you have to lose detail. If an email is good or bad contains a lot less information than if you know what could change in that email in order to improve. And the third is that whenever you create a hill and a data set, you're really trying to create a proxy for reality. What if instead we could use reality to inform our evals automatically? What qualitative learning asks is how do we decrease this question? How do we decrease assistance? And it's a research question right now. But what we believe is that models are now good enough to interpret whatever textual feedback is present in the environment and convert that into evals and a hill that the model can climb. And so as you get more feedback from production, its traces, its user actions, its product analytics, it's asking you, it's the model asking you questions about how data should be represented. As you do this, the model can iteratively refine the hill over time and continue climbing it to solve your actual business problem.

</details>

### 最后一英里学习与 AGI

**[Isaac Miller]**: DSPy 专注于这类最后一英里的问题。我们有一个非常强大的研究生态系统，并与他们密切合作。这部分美妙之处在于，我们可以看到应用 AI 工程中发生的问题。我们定义它们，构建基准，然后用技术解决它们，然后我们将结果民主化给所有人，因为它是开源、开放的研究。现在，一个常见的问题是，当我们拥有 AGI 时会发生什么？嗯，即使我们拥有一个极其智能的模型，这个模型也不会知道如何解决你的问题。它不会知道如何完成你的任务或了解你的上下文。所以，这种最后一英里学习的类型试图问，我们如何高效地进行这种学习？智能与全知是非常不同的。如果你让 **阿尔伯特·爱因斯坦** 帮你处理邮件，他可能会问“什么是邮件？”但如果你有 AGI，它会知道如何处理你的邮件。尽管如此，它不会知道如何实际解决你的问题，并与你需要互动的人进行互动。如果不随着时间的推移学习这个上下文，它就不会理解你的人际关系。

<details>
<summary>Original English</summary>

**[Isaac Miller]**: And DSPy focuses on these kinds of last mile problems. We have a really strong research ecosystem and we collaborate really closely with them. And that's part of the beauty is that we can see the problems that happen in applied AI engineering. Sol define them, build a benchmark and then solve them with techniques and then we get to democratize the results of that to everyone because it's open-source open research. Now, one common question is what happens when we have AGI? Well, even when we have an incredibly smart model, the model won't know how to solve your problems. It won't know how to do your tasks or have your context. And so this genre of last mile learning is trying to ask how do we efficiently do this learning intelligence is very different from being all knowing. If you were to ask Albert Einstein to help you with your emails, he'd probably ask what's an email. But if you AGI will know how to do your emails. Nevertheless, it won't know how to actually solve your problem and interact with the people you need to interact with. It won't understand your relationships without learning this context over time.

</details>

### 总结与行动号召

**[Isaac Miller]**: 自 2022 年以来，DSPy 一直专注于规范、代码和评估这三个核心思想，所有这些都被定义为一个程序化接口。我们当然随着时间的推移而发展，新技术令人难以置信。我们已经从进化少量示例发展到提示，再到现在的框架，现在也在随着时间的推移进化你的评估。但是，对于任何这些新技术，你需要问的是，它们如何帮助你解决更困难的问题或更好地解决你自己的问题？你应该以数据驱动的方式问这个问题。你应该看看这项新技术，说，我如何将它应用到我现有的业务问题上？你应该定义你的问题，并让你的提示、模型和代码对你需要它们解决的问题负责。当你以这种方式构建，拥有灵活的实现时，你所解锁的是这个房间里所有人不断发明的所有技术的生态系统。你解锁了这里每个人的集体智慧，大家一起分享技术。所以，如果你想构建可靠的 AI 软件，我鼓励你来了解一下 DSPy。我们完全是开源的，开放研究，我们在这里通过构建可靠的软件来帮助你解决问题。我们有一个 Discord 服务器，你应该加入。当你提出下一个技术时，你应该把它贡献给 DSPy。我们可以帮助你分发它，让这个很棒的技术对所有人都可用。谢谢。

<details>
<summary>Original English</summary>

**[Isaac Miller]**: Since 2022, DSPy has been focused on these three core ideas of specs, code, and evals, all defined as a programmatic interface. We've certainly evolved over time, and new techniques are incredible. We've gone from evolving few shots to prompts to now harnesses and now evolving your evals over time, too. But what you need to ask for any of these new techniques is how do they help you solve harder problems or solve your own problems better? And you should ask this question in a datadriven manner. You should look at this new technique say how can I apply this to the business problem that I have? You should define your problem and you should hold your prompts, models, and code accountable to the problem that you need them to solve. And what's awesome about when you build in this way where you have flexible implementations, what you unlock is you unlock the ecosystem of all the techniques that anyone in this room is constantly inventing. You unlock access to the collective intelligence of everyone here, all sharing techniques together. So, if you want to build reliable AI software, I encourage you to come check out DSPy. We're completely open-source, open research, and we're here to help you solve your problems by building reliable software. We have a Discord that you should come join. And when you come up with the next technique, you should come contribute it to DSPy. And we can help you distribute it and make this awesome technique available for everyone. Thank you.

</details>