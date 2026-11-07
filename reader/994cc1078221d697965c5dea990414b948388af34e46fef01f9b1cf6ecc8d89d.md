---
author: AI Engineer
date: '2026-06-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=EcqMYoIV57A
speaker: AI Engineer
tags:
  - agentic-workflows
  - context-optimization
  - multi-agent-architecture
  - orchestration-paradox
  - iterative-retrieval
title: 更多上下文如何让智能体变笨：Qodo的代码审查多智能体架构实践
summary: 探讨了在开发智能体时因过度增加上下文导致模型注意力丢失的“U型曲线”问题和“编排悖论”。分享了利用上下文引擎优化输入、通过混合智能体架构分配专家任务，并引入裁判智能体结合反馈权重进行校准的最佳实践。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Qodo
  - LangChain
products_models:
  - Claude 3 Opus
  - Jira
media_books: []
status: evergreen
---
### 智能体的演变与挑战

**Nupur**: 我是 Nupur。我就职于 **Qodo**。在 Qodo，我们进行基于智能体的代码审查。我有 **DevSecOps** 的背景。所以我来自一个一切都是确定性的行业。流水线运行，崩溃。如果它们崩溃了，我们就去修复它们。然后我来到了一个我们正在开发智能体的地方，这里没有任何东西是确定性的。因此，在过去的几年里，我学到了智能体在哪里以及如何失败，有哪些经验教训，今天我将与你们分享我的一些经验。

<details>
<summary>Original English</summary>

**Nupur**: I'm Nupur. I work with Kodo. Uh at Kodo we do agentic reviews. Uh I have a background in dev sec ops. So I'm coming from an industry where everything was deterministic. The pipelines they run they crash. If they crash, we fix them. Uh to a place where we are doing agents where nothing is deterministic. So in my last few years I have learned where and how agents fail, what are the learnings and today I'll be sharing some of my learnings with you.

</details>

**Nupur**: 如果你回顾智能体的演变，它始于静态提示词，当时是 4K 的上下文窗口，我们试图把任何重要的东西或者我们认为重要的东西放进去，**人工智能模型**会处理它并给你提供一个结果。对吧？当我们从这里开始时，这意味着我们需要负责告诉大语言模型它们应该关注什么。这意味着如果我们提供了错误的输入，我们可能无法获得正确的结果。

<details>
<summary>Original English</summary>

**Nupur**: So um if you see the evolution of agents, it started with static prompts where it was a 4K context window and we tried to put whatever was important or whatever we deemed important and the AI models will process it and provide you with a result. Right? When we started with that that means that it was on us to tell LLMs what do they should they should look into. That means if we provide wrong inputs, we might not get proper results.

</details>

**Nupur**: 然后我们想，也许如果上下文窗口变大，如果上下文大小增加，我们能做得更好。我们可以有更多的输入。然后我们开始了智能体工作流。所以我们创建了一个智能体。我们给它们像搜索工具这样的工具，去搜索文档并作为一个命令来执行某些操作。然后再去搜索并执行操作，这再次造成了一种循环，工具不知道该在哪里停下来。它会想我需要更多输入，然后不断地回去。这是一个为了改进而产生的循环。

<details>
<summary>Original English</summary>

**Nupur**: And then we thought maybe if the context window grows, if the context size grows, we can do better. We can have more inputs. And uh we started with agentic workflows. So we created an agent. We get that get them tools like search tool to go into search into documents and do something uh as a command. then again look into the search and do something which again created kind of a loop where the tool does not know where to stop. It thinks like I need more inputs again going back and back. It's a loop to improvise on that.

</details>

**Nupur**: 现在，**多智能体**变得越来越流行。创建多智能体来一起做很多事情。当我们这样看的时候，我们有很多智能体在为你工作。一个安全智能体试图找出安全问题，一个审查智能体试图审查工具，一个编码智能体试图修复问题。现在同样地，工具越多，你遇到的问题就越多。并不是每个智能体都能理解，它们在理解上会发生冲突，导致你无法获得结果。

<details>
<summary>Original English</summary>

**Nupur**: Uh nowadays multi-aents is becoming more popular. Create multi-aents do a lot of stuff together. When we see it like that we have a lot of agents working for you. a security agent trying to figure security concerns, a review agent trying to review the tool, a coding agent trying to fix things. Now again, the more the tools, the more issues you have. Not every agent understands and they have clash in their understandings where you don't get into the results.

</details>

### 上下文丢失的“U型曲线”

**Nupur**: 那么我们从中学到了什么呢？我们看到的是，上下文不是问题。日复一日，新的模型不断涌现，你可以把大量的上下文、大量的数据丢给它们。但这能确保你得到的结果足够聪明，能给你所有东西，或者足够聪明来决定什么是重要的吗？如果你观察当前的大语言模型，我们看到一种模式，它会接受你提供的初始输入，接受最后的输入，但是中间的上下文基本上被删除了。所以它们不关注中间的上下文。智能体看着起点、终点，并试图为你提供结果。这就像一个 **U型曲线**，开始的一些东西和最后的一些东西有意义，但你在中间提供的任何东西都没有被采纳。是的。

<details>
<summary>Original English</summary>

**Nupur**: So what do we learn from here? What uh we see is context is not a problem. Day by day the models are coming where you can dump a lot of context, a lot of data. But does that make sure that the results you are getting is smart enough to give you everything or smart enough to decide what's important? If you see the current LLM models, we see a pattern where it takes the initial inputs you provide, it takes the last inputs, but the in between context is basically removed. So they don't focus on the in between context. Agents look at the starting point, end point and try to provide you the results. This is like a U curve where some of the things from the start, some of the things from the end make sense but whatever you are providing in between that that is not taken up. Yeah.

</details>

**观众**: 你是怎么知道这个的？

<details>
<summary>Original English</summary>

**Audience**: How do you know this?

</details>

**Nupur**: 这是我们正在研究的事情，我们实际上在对事物进行**基准测试**。所以当我们创建智能体时，我们试图观察这是我们提供给智能体的上下文。它是否将这个上下文纳入考量并给我们提供结果。所以我们正在使用多智能体架构，对于我们进行的每一项代码审查任务，我们把任务交给一个智能体，然后说，好的，给我们一个结果。

<details>
<summary>Original English</summary>

**Nupur**: This is something which we are working on and we are actually benchmarking things. So when we create agents we try to see this is the context we provide to the agents. Does it take this context into effect and also give us the results. So we are working with multi-agentic architecture where for each of the task we do do for code reviews we give the task to an agent and say okay give us a result.

</details>

**Nupur**: 现在，每次我们比如做代码审查时，我们试图看看我们是否可以提供所有的上下文，比如我们是否可以提供整个代码库，看看是否能得到结果，但我们发现每当我们开始这样做时，我们最初的提示词或我们开始时的初始目标是焦点。如果我们在最后给出一些东西作为输入，它也是焦点，但在两者之间的所有上下文，比如我有 **Jira**，我有 MCP，你能看看那个吗，大语言模型会试图摆脱这些东西并清除它们，以便靠自己弄明白。

<details>
<summary>Original English</summary>

**Nupur**: Now every time we for example code reviews we try to see can we give all the context can we give the whole codebase for example and see if we can get a results but we see that that whenever we start working with that the initial prompt or the initial goal which we start with that is in focus. If we give something at the end as an input that is in focus but all between context like I have Jira I have MCPS can you look into that the LLMs try to get rid of those things and purge them to get make sense by themsel.

</details>

### 上下文优化策略

**Nupur**: 因此，为了解决这个问题或找到出路，我们的处理方式是创建用于**上下文优化**的战略性解决方案，而不是把所有东西都丢给模型并要求它们足够聪明来找出更重要的东西。我们通常试图看看，好的，我们能做些什么来为模型提供更好的上下文。如果你现在看的话，有很多现成的解决方案，**上下文引擎**是一个流行词，似乎每个人都想创建上下文引擎，每个人都想提供它，但是上下文引擎就像一个保镖，对吧，所以你的高速汽车正在行驶，它充当保镖告诉你这更重要。现在如果你有一个庞大而混乱的代码库，创建一个上下文引擎是有意义的，因为它创建了一种搜索模式，它创建了排名逻辑，这样每当你要求一个任务时，它就会寻找那些排名并说这件对你更重要，拿着它去工作吧。

<details>
<summary>Original English</summary>

**Nupur**: So to have this or to make a way out of this how we deal with is creating strategic solution for context optimization rather than dumping everything to the models and asking them to be smart enough to find out what is more important. Uh we usually try to see okay what we can do to make it uh better context for the model. There are lots of solutions in place if you see currently and context engine is a buzz word like everybody wants to create context engine and everybody wants to uh provide that but context engine is like a bouncer right so your high-speed car is going and it acts as a bouncer and tells you this is more important now if you have a large messy code base it makes sense to create a context engine because it creates a search pattern it creates ranking logic so that whenever you ask for a task it looks for those rankings and say this is more important for you take it and work with it.

</details>

**Nupur**: 问题在于，索引部分需要适度的努力，但扩展是一个挑战。比如，如果你开始谈论 600 个仓库或 700 个仓库，映射和索引就会开始变慢，而且如果你不是专门做上下文引擎的，那么寻找或创建一个上下文引擎又会变得不可预测。

<details>
<summary>Original English</summary>

**Nupur**: The problem is the indexing part takes moderate effort but the scaling is a challenge. Like if you start talking about 600 repositories or 700 repositories the mapping and the indexing starts to slow down and it becomes again unpredictable to find or create a context engine if you are not actually into making context engine only.

</details>

**Nupur**: 还有很多领域可以让智能体获得更多上下文，而不是在上下文引擎上投入巨资，例如**分层摘要**，也就是不创建或遍历所有内容，而是为每个文件和文件夹创建一个摘要，这样当智能体试图查找时，它们可以尝试阅读摘要并看看那对我们是否更重要，这可能是一个好方法。唯一的问题是，你需要大量的大语言模型处理能力。每次创建或更改文件时，一些智能体都需要去为它创建一个映射。所以这需要很高的前期大语言模型处理成本。

<details>
<summary>Original English</summary>

**Nupur**: There are lots of areas where agent can get more context instead of investing highly on context engine hierarchal summarization where instead of creating or going through everything a summary is created for each file and folder so that when the agents try to find they can try to read the summary and see if that is more important to us or not can be a good one. The only thing is that you need a lot of LLM processing. every time a file is created or changed some of the agents need to go and create a mapping for that. So it's a high upfront um context of uh LLM processing that is needed.

</details>

**Nupur**: 另一种方法是**知识图谱**。现在的知识图谱很复杂，但当你有逻辑依赖关系时，它会产生奇迹。例如，你有一个文件影响另一个文件，而该文件又影响其他文件。你可以创建一个图数据库托管。开发者需要的初始输入非常高。创建它需要花费很多时间。但如果你有复杂的逻辑或者你对多个仓库有依赖，这对我来说效果非常好。

<details>
<summary>Original English</summary>

**Nupur**: Another way is knowledge graph. Now knowledge graph is complex but it works wonder when you have logical dependencies. For example, you have one file which impacts another file which again impacts other file. You can create a graph DB hosting. It is the initial input needed by the developer is very high. It takes a lot of time to create that. But if you have complex logics or you have dependencies on multiple repos that works wonder for me.

</details>

**Nupur**: 我认为对于大多数任务，如果你不是一家产品公司，但你在为你自己或你的流程构建智能体，**迭代检索**效果非常好，因为甚至不创建摘要，它也能创建一种索引。所以这就像一张图书馆借书卡，你把它给你的智能体说，这就是主题，看看这是否与你相关。你可以深入查看代码，寻找结果。同样，它有相当大的成本影响，但你不必投入太多精力。开发者需要提供给大语言模型的输入很少，而且它能提供更好的结果。

<details>
<summary>Original English</summary>

**Nupur**: I think for most of the task if you're not a product company but if you're building agents for yourself or your processes iterative retrieval works really good because instead of even creating a summary it creates kind of an index. So it's like a library card which you give to your agents and say this is the topic if that is relatable to you. You can look deep into the code uh and uh look for the results. Again it has quite uh cost impacts but you do not have to invest a lot of energy. The input uh required by the developers to provide to the LLM is low and it provides better results.

</details>

**Nupur**: 还有一个**自我纠正**的选项，你可以要求大语言模型做某事，然后有一个**批评节点**来查看并判断这是否与你最初的目标相关。在这种情况下，如果上下文丢失了，你可以再次要求智能体重新做，再次重试，因为批评节点说这不是正确的方法。这会多花一点时间，因为它增加了再次运行智能体的延迟，但它在最初不需要开发者提供大量输入来创建某些东西。

<details>
<summary>Original English</summary>

**Nupur**: There is also option of selfcorrection where you ask uh the LLM to do something and there is a critic node which looks and say if that is relevant to your initial goal or not. In that case if the context is lost uh you can again ask the agent to do it again retry it again because the critic note said this is not the right way. It takes a little bit more time because it adds a latency of running the agents and again but it does not require a lot of input initially from the developers to create something.

</details>

### 编排悖论与混合方法

**Nupur**: 另一个挑战是，我看到人们在创建这些智能体时会陷入**编排悖论**。现在的情况是，大语言模型变得越来越聪明。所以当你给它们任务时，它们会想，好的，我应该使用这个工具，也许我可以做得更好，我应该对应该使用什么进行更多研究。它进入了一个循环，没有去实际寻找解决问题的方法，而是在寻找解决问题的方法。它们从一种方法跳到另一种方法，大多数 API token 都浪费在寻找实现方法的路上，而不是去实际执行。所以你只会一直处于研究模式。例如，如果你使用 **Claude 3 Opus** 最新和最强的版本，它们会试图找出最好的方法，并一次又一次地挑战自己。也许不是这个，换另一种方法，再换另一种。它就这样进入了一个试图做某事而不是实际做某事的循环。

<details>
<summary>Original English</summary>

**Nupur**: Another challenge uh which I have seen people getting into when they create uh these um agents is the orchestration paradox. Now what it does is that now LLMs are becoming more and more smart. So when you give them the task they think like okay I should use this tool uh maybe I can do better I should research more on what should I use. It goes into a loop that instead of actually looking into solve the problem, they look for the method to solve the problem. They hop on from one method to one another method and most of the API tokens are wasted on finding a way to do it rather than doing it. So you will just go on the research mode. For example, if you use Opus latest and greatest, they will try to see what is the best method to do it and challenging themsel again and again. Maybe not this, another way, another way. And it just goes into a loop of doing trying to do something rather than doing something.

</details>

**Nupur**: 为了解决这个问题，我们采用了 **80/20 混合方法**。我认为这是我见过的最有趣的结果之一，或者是解决这个死循环的方法。我们团队正在做的是，让最新、最强的模型或智能体有 80% 的时间进行研究。所以你给它们目标，然后说，好吧，尽你所能去做，但在剩下的 20% 任务中，你需要最终验证，你需要摘要，那些不是自由发挥的，而是更受限制的，那些是更严格的关卡，比如如果我得到 X 结果，我想要 Y，它更具确定性，这样来自 80% 的研究就可以被精简。现在当你看到这里，你总是可以说 80% 的工具仍然可以继续并陷入死循环。

<details>
<summary>Original English</summary>

**Nupur**: To resolve this uh we worked with 80/20 hybrid approach. I think this is one of the most interesting uh outcomes I have seen or the way to in resolve this infinite loop. What our teams are doing is giving the latest and the greatest models or giving the agents power to research 80% of the time. So you give them the goal and say okay try to do whatever you can but the 20% of the task where you need final validation you want summarization that are not something which is free flowing that is more restricted those are more hard gates for example if I get X results I want Y it's more deterministic so that the research which is coming from the 80% can be lowered down now when you see you can always say that the 80% tool can still go on and go into infinite loops.

</details>

**Nupur**: 我们有处理这个问题的机制。对于一些组织，他们会使用计数机制，在四五次计数之后，你必须使用最后一次的结果。对于另外一些组织，他们有超时计数器，在 5 分钟之后，无论最后的工具是什么或者最后的决定是什么，你都使用它，如果结果不好再返回。但你可以限制那 80%。

<details>
<summary>Original English</summary>

**Nupur**: We have mechanisms to work on that. For some organization do they do counter mechanism where after four or five counters you have to work with whatever was the last results. For some of them they have timeout counters that after 5 minutes whatever is the last tool or whatever is the last decision you work with that and then go back if the results are not good. But you can restrict that 80%.

</details>

**Nupur**: 简而言之，如果你使用任何像发现之类的东西，或者你试图看看使用哪个工具，你试图计划，那么这 80% 的研究模型是非常好的。但如果你又是试图创建一个摘要，试图说，好的，这就是我得到的研究成果。现在我必须从中得出一个结果。这 20% 的模型就能发挥很好的作用。现在对于 80% 的部分，你通常使用高推理模型，最新和最强的版本，但你不需要在 20% 的部分使用高推理模型，因为这 20% 的任务是确定性的，你实际上是在告诉它们需要什么，例如我们提到的批评节点，它们不需要去研究，它们不需要找出最好的做法是什么，它们只需要看看你的目标是什么，你试图达到的结果是什么，以及如何提供或如何进行摘要。同样地，如果你考虑下一个可能的行动是什么，我已经有了这个结果，我应该去寻找什么，这些事情可以由 80% 的动态模型来完成，而当我已经有了来自 80% 模型的所有结果，但用户所期望的正确方式或正确结果是什么，这类决定则可以由 20% 的模型来做出。

<details>
<summary>Original English</summary>

**Nupur**: But in short, if you are using anything like discovery or you're trying to see which tool to use, you're trying to plan those 80% uh research models are really good. But if you are again trying to create a summarization, you're trying to see okay this is the research I have got. Now I have to make a result out of it. The 20% works really well. Now for 80% usually you use uh high reasoning models latest and the greatest but you don't need a high reasoning model for the 20% because those 20% things are doing deterministing they you are actually telling them what is needed for example the critic node which we talked about they don't need to research they don't need to find out what is the best thing to do they just need to see what was your goal what was the result you are trying to achieve and uh how to provide or how to summarize ize that for that also things like if you think about what would be the next possible action I have this result what should I go and look for that are things can be done by the 80% dynamic models whereas I have all the results from the 80% models but what is the proper way or what is the proper uh results the the user is looking into those kind of decisions can be taken by the 20% model.

</details>

### 多智能体混合架构与裁判

**Nupur**: 最后，这也是我们见过的一个有趣的失败案例，随着上下文的增加，团队认为，好吧，我们可以用一个智能体做所有事情，因为上下文窗口非常大，对吧，我们可以把所有东西放进去，我们可以让一个智能体去做测试部分，我们可以让那个智能体去做审查部分，我们可以让智能体做各种事情，因为上下文是一样的，它们可以为我们提供结果，但这导致了当智能体向前推进时，它会被输入淹没，并再次开始迷失最初的任务是什么。所以也许你给了智能体四个任务，在某个节点上它只关注了两个任务。所以你在那两个任务上得到了很棒的结果，但其他两个任务就在中途丢失了。

<details>
<summary>Original English</summary>

**Nupur**: Finally, uh this is again an interesting failure which we have seen where as the context grows, teams think okay we can do everything with one agent because the context window is quite great right we can put everything we can ask an agent to uh do uh the testing part we can ask that agent to do review part we can ask the agent all the kind of things because the context is same and they can provide us the results that make sure that the when the agent is going forward ward it get overwhelmed with the inputs and again it tries to start losing uh what was the original task. So maybe you give four tasks to the agent and somewhere down the line it focuses on two tasks. So you get great results for the two task but the other two just just get lost in the middle.

</details>

**Nupur**: 为了这个特定的目的，我们有一种叫做**混合智能体**的东西。这就是为什么你听到很多关于多智能体或多智能体技术架构的讨论，你不是创建一个大智能体，而是创建问题专家智能体。我们创建在特定提供给它们的任务中表现出色的小型智能体。现在，在此基础上，每个智能体都会提出自己有趣的想法或结果。如何确保这些结果结合起来并合理呢。因为，举个例子，我正试图规划一个假期。我交给一个智能体去寻找最好的酒店。另一个智能体试图寻找最好的航班。但它们三者给我的结果各不相同。酒店在希腊。航班是从阿姆斯特丹飞往，呃，也许是葡萄牙，而这一切根本说不通，对吧。所以出于这个特定的目的，有一个叫做**裁判智能体**的概念，它的作用是尝试获取所有结果并看看它们是否可以一起讲得通，所以现在你在从不同智能体那里做所有最棒的事情，从它们各自的部分获得最好的结果，但一个裁判智能体帮助我们将这些结合起来，并从中提取出一个统一的意思，而不是得到那么多放在一起不讲道理的东西。

<details>
<summary>Original English</summary>

**Nupur**: For those particular purpose, we have something called mixture of agents. And that's that's where you hear a lot of buzz about multiple agents or multi-agent tech architecture where you create instead of one big agent, we create issue expert agents. We create small small agents which are doing great in a specific task which they have provided. Now to build on top of that each of the agent come up with their own interesting ideas or results. How to make sure those results combine and make sense together. Because for example I am trying to search for a vacation. I give an agent to find the best hotel. Another agent try to find best flights. But all three of them gives me different result. The uh hotel is in Greece. uh the flight is from Amsterdam to um maybe Portugal and everything just doesn't make sense right so for that particular purpose there's a concept called a judge agent what it does it it tries to get all the results and see if they can make sense together so now you are doing all the greatest things from different agent getting the best results from their part but a judge agent help us to combine these and make one sense out of it instead of getting so many things which doesn't make sense together.

</details>

**Nupur**: 我们实施了类似的东西。这就是我们的架构，Qodo 的架构，对于代码审查，我们使用了相同的公式。因此，作为拉取请求（PR）审查的一部分，我们有一个**上下文收集器**，它实际上去从 PR 中收集上下文，它可以从上下文引擎收集上下文。它从工具中收集上下文，但随后它并不直接开始工作并给你审查意见。它实际上将它提供的所有上下文进行分支，并传递给不同的智能体。

<details>
<summary>Original English</summary>

**Nupur**: Something similar is implemented by us. So this is our architecture uh codos architecture where for the code reviews we are using the same uh formula. So as part of a PR review we have a context collector which actually goes and collect context from the PRs it could collect context from the context engine. it uh collect context from the tools but then it does not start working and uh giving you the reviews. It actually bifocates all the context it has provided and pass it on to different agents.

</details>

**Nupur**: 现在这些智能体所做的基本上是专注于它们应该做的事情。例如，会有一个安全智能体试图发现安全漏洞。可能会有一个智能体试图编码。可能会审查代码差异。可能会有一个智能体试图找到 Jira 问题。一旦所有这些智能体都给我们回复，一个裁判智能体实际上会查看结果并说，好的，这些足够有趣，但它与你相关吗？它们可以再次回到上下文引擎中，查看 PR，看看你提供的 10 件事中，有多少是对你的项目真正有意义的。所以再次完善结果，让它对你讲得通。是的，我想我要讲的就是这些。呃，有什么问题吗？

<details>
<summary>Original English</summary>

**Nupur**: Now what these agents do is basically specializing in what they are supposed to. For example, there will be a security agent trying to find security flaws. There might be a agent trying to code. There might uh code differences. There might be an agent trying to find the Jira issues. Once all these agents give us back, a judge agent actually looks for the results and say okay these are interesting enough but is it relevant to you? They can again go back in the context engine look into the PRs and see out of the 10 things which is provided by you how many of them actually make sense for your thing. So again refining the results uh to make sense to you. Yeah, I think that was it from my side. Uh, any questions?

</details>

### Q&A：智能体间的通信与校准

**观众**: 是的。嗯，在实践中，你们如何让智能体群相互交流？

<details>
<summary>Original English</summary>

**Audience**: Yes. Um, in practice, how do you let the swarm communicate with each other?

</details>

**Nupur**: 呃，你是指智能体。

<details>
<summary>Original English</summary>

**Nupur**: Uh, you are talking about the agents.

</details>

**观众**: 对，你有智能体 A 和智能体 B 以及裁判。我可以想象它们写入一个文件系统，或者它们有某种专有工具。

<details>
<summary>Original English</summary>

**Audience**: So, you have agent A and agent B and the judge. I can imagine they write to a file system or they have some kind of tool proprietary.

</details>

**Nupur**: 呃，我们在底层使用了 **LangChain**，它被用来进行通信并为不同的智能体构建基础设施。

<details>
<summary>Original English</summary>

**Nupur**: uh we ch we use uh longchain at the bottom uh and that is being used to communicate and build the infrastructure for uh different agents.

</details>

**观众**: 你知道 LangChain 是用什么来实现这个的吗？比如只是收集响应，然后把它塞回下一个智能体的提示词中？

<details>
<summary>Original English</summary>

**Audience**: Do you know what lang chain uses for that like just collects the responses and then shs it back into the prompt of the next agent?

</details>

**Nupur**: 是的。是的。是的。是的。就是这样，所以我们所做的是，我们尝试去获得结果，并为下一个智能体创建一个提示词，如果涉及多个事项，同样会有一个智能体专门用来收集结果，并创建一个更好的提示词，这个提示词是为下一个智能体优化过的。

<details>
<summary>Original English</summary>

**Nupur**: Yes. Yes. Yes. Yes. that that's what so what we do is we try to uh get the results and create a prompt for the next agent and if it's multiple things again there is an agent just to collect the results and create a better prompt uh which is refined for the next agent

</details>

**观众**: 你考虑过为每个智能体增加一个校准步骤吗？

<details>
<summary>Original English</summary>

**Audience**: have you thought about a calibration step for each agent

</details>

**Nupur**: 当你说校准时，你能详细说明一下吗？

<details>
<summary>Original English</summary>

**Nupur**: when you say the calibration can you tell me more

</details>

**观众**: 校准，对吧，所以当你使用智能体进行代码审查时，对吧，至少我今天听到的是做一些校准，你实际上告诉它们什么是好的，什么是坏的。

<details>
<summary>Original English</summary>

**Audience**: calibration right so when you do a code review with an agent right need At least what I heard today is doing some calibration that you actually tell them what is good and what is bad.

</details>

**Nupur**: 是的。所以当你这样说时，呃，告诉我这是否解答了你的问题。我们以一种形式进行校准，我们检查我们作为上下文所拥有的东西。所以，例如，当我们进行代码审查时，大语言模型不知道对你来说什么是重要的，或者你是如何工作的。所以，例如一个大语言模型，当它们获得输入时，它们获得的输入来自医疗保健行业，来自零售行业，来自金融行业，而它们都可以以不同的方式使用同一个 Java 框架，或者对它们来说不同的东西是重要的，其他东西对它们来说没有意义。

<details>
<summary>Original English</summary>

**Nupur**: Yes. So when you say it like that uh and let me know if that makes sense for your question or not. We do calibration in a form we check what we have as a context. So for example uh when we get the code reviews LLM does not know what is important for you or how do you work. So for example an LLM when they gets input they get input from healthcare industry they get from retail industry they get from finance industry and all of them can use same Java framework in different ways or different uh things are important for them the rest of them doesn't make sense.

</details>

**Nupur**: 所以我们所做的是给你两个不同的选项，来告诉智能体该如何表现或如何工作。一部分是我们给它们提供 PR 历史记录。所以我们对你所有的 PR 进行索引，看看上次发现类似问题是什么时候，并比较当前版本如果那是……

<details>
<summary>Original English</summary>

**Nupur**: So what we do is we give you two different options to tell the agents how to perform or what to work on. One part is we give them the PR history. So we index all your PR and see when was the last time something like this was identified and compare the current version if that is

</details>

**观众**: 你是从上下文的角度来做的。

<details>
<summary>Original English</summary>

**Audience**: you do that in the context standpoint.

</details>

**Nupur**: 是的。是的。是的。是的。我们是这样做的。所以你对代码所做的更改，我们会查看是否能在过去找到类似的内容，这会再次，呃，传递到上下文两次。第一次是我们实际上在为子智能体提供上下文，以便为你查找内容，另一次是提供给裁判智能体。因此，当我收到 15 个不同的代码审查建议时，我的裁判智能体可以查看之前有什么，你的审查员是如何评论的，你的开发者是如何评论的，并在此基础上决定这是否值得提供给你的开发者。而另一部分是……

<details>
<summary>Original English</summary>

**Nupur**: Yes. Yes. Yes. Yes. We do that. So the changes we you make to the code we look into if we can see something similar in the past that again is uh transfer to the context twice. First is when we are actually giving context to the sub agents to find things for you and another time to the judge agent. So that when I get 15 different recommendations for a code review, my judge agent can look into what was there before, how did your reviewer commented, how your developers commented and based upon that decide if that is worth providing to your developers or not. And the other part is

</details>

**观众**: 这发生在每个智能体身上。

<details>
<summary>Original English</summary>

**Audience**: and this happens for every agent.

</details>

**Nupur**: 对每个智能体来说，是的，

<details>
<summary>Original English</summary>

**Nupur**: For every agent yes,

</details>

**观众**: 对，你们不在智能体之间共享上下文，对吧？所以顺便说一下，你有一个特定的上下文。

<details>
<summary>Original English</summary>

**Audience**: right, you don't share the context between the agent, right? So you have a specific context by the way.

</details>

**Nupur**: 是的，我们正在努力解决那个 U型曲线的问题，与其将所有内容都丢给大语言模型，我们不如提取更重要的部分，我们使用上下文引擎来实现这一点。我们提取更重要的部分，并且只将那个特定的部分提供给那个特定的智能体。

<details>
<summary>Original English</summary>

**Nupur**: Yes, we are trying to resolve that U part that instead of dumping everything to the LLM, we uh take the part which is more important, we use a context engine for that. We take the part which is more important and only provide that particular part to that particular agent.

</details>

**观众**: 但是，对我来说不清楚你如何弥合差距，而不是说你有一个质量智能体，你有一个框架特定的编码审查智能体，对吧，然后你基本上只，正如我所理解的，你只与每个智能体共享特定的信息，对吧，然后基本上每个智能体自主地运行。

<details>
<summary>Original English</summary>

**Audience**: But but then for me it's not clear how you bridge the gap rather than say you have quality agent and you have agent framework specific coding radio agent right and then you basically you only as I understood you only share the specific information to each agent right and then basically each agent runs atomic autonomously Yeah.

</details>

**Nupur**: 对。

<details>
<summary>Original English</summary>

**Nupur**: Right.

</details>

**观众**: 并且没有全貌，对吧？至少当我们作为人类来说，对吧？如果你进行代码审查，拥有全局观总是好的，对吧？我想说，这种方法论对于简单的事情可能是有效的，比如它使用了代码检查吗？它使用了，我不知道，有没有实施测试？但是当你考虑到，至少我认为当你考虑到架构时，比如为了做出涵盖安全的架构决策，因为一切都是一种平衡，并且并且，呃，你必须以某种方式权衡，所以你如何解决……

<details>
<summary>Original English</summary>

**Audience**: And doesn't have a full picture, right? At least when let's say as a human, right? And if you do code reviews, it's always good if you have a full prospect, right? I would say like that kind of methodology would it works for simple things like does it use linting? Does it use I don't know are tests implemented? But when you think about at least I think when you think about architecture for example to make architecture decisions um that covers security because everything is a balance and and uh you have to wait that somehow so how do you solve

</details>

**Nupur**: 是的，所以我想，如果你回顾旧版本的代码审查，你应该有，你过去常常有一位高级工程师，他了解你的代码，他知道你正在使用什么类型的依赖包，并且他们可以评论开发人员是否做了与你习惯的做法类似的事情，或者是做了完全奇怪的事情，对吧？然后你过去常常有一位安全人员，他会查看你是否提供了各种安全保障，你是否硬编码了你的 API，或者你是否放入了任何 SQL 注入。所以安全专家知道所有这些类型的事情。另一方面，如果你正在进行 ISO 合规性审查或 SOC 2 合规性审查，可能会有一位审计员，他可能会问团队负责人或高级工程师，你的代码是否被，你知道，记录了日志，它是否记录了更改等等。

<details>
<summary>Original English</summary>

**Nupur**: yes so I think if you look into the older version of code reviews you should have you used to have a senior engineer who knows your code who knows what kind of packages you're using and they can comment on if the developer has done something uh similar to what you're used to or did something uh totally weird, right? Then you used to have a security person who used to see if you are providing all kinds of security, you are not hard-coding your APIs or you are not putting any SQL injection. So all those kind of things the security experts know. On the other hand, if you are working with ISO compliance or sock to compliance, there might be an auditor who might ask the uh team lead or the senior engineer is your code uh being um you know logged is it logging the changes and so on.

</details>

**Nupur**: 所以，以前也有很多人拥有专业知识，专门查看那些类型的领域。现在，当提供上下文时，总是像这样的，这是我始终必须关注的安全考虑。这是我的架构考量。架构师可能会从架构的角度来看。我们也可以用智能体做类似的事情，因为例如架构和安全问题，我们有一个门户网站，架构师可以在那里提供他们的指导方针，合规人员可以提供他们的指导方针，然后一个智能体可以查看所有这些指导方针并说，它是否被验证了。

<details>
<summary>Original English</summary>

**Nupur**: So previously as well there were lots of people having specialized knowledge looking into those kind of areas specifically. Now when the context is provided it's always like these are my security concerns which I always have to look into. These are my architectural concerns. An architect might look from the architecture perspective. We can do that something similar uh with the agents as well because for example architecture security concerns we have a web portal where architects can provide their guidelines pro uh compliance people can provide their guidelines and an agent can look into all those guidelines and say is it validated or not.

</details>

**Nupur**: 所以如果你看最初的架构图，上下文收集器知道所有事情，然后它为智能体提供相关的上下文。

<details>
<summary>Original English</summary>

**Nupur**: So if you see the initial uh picture the context collector knows everything and then it provides relevant context to the agents. So you you enforce basically your customer to upload these kind of documents, right?

</details>

**观众**: 所以你基本上是强制你的客户上传这些文档，对吧？那么这是一种要求吗，或者，因为我的意思是系统将会有完全不同的结果，对吧，如果你不共享它们。

<details>
<summary>Original English</summary>

**Audience**: So you you enforce basically your customer to upload these kind of documents, right? Is that a kind of a requirement then or because I mean the system will have completely let's say different result right if you don't share them

</details>

**Nupur**: 完全正确，所以这取决于组织，有些组织会说我们不遵循任何规则或法规，所以只要给我开箱即用的东西，这也就意味着不要指望智能体会发现一些对你的工作非常具体的东西，除非我们有特定的 PR 历史记录，因为在那种情况下 PR 历史记录会发挥作用，即使在你没有提供规则的时候，它也会告诉你什么是相关的。

<details>
<summary>Original English</summary>

**Nupur**: exactly so that's something which depends upon organization there are some people who say we don't work with any rules or regulations so just give me out of the box that also means that don't expect the agents to find something very specific to your working until and unless we have certain PR history because then again the PR history kicks in and tells you what is relevant even though when you don't provide

</details>

**观众**: 我不确定 PR 历史记录是否真的是最佳来源，但我认为它可以是一个，它可以是其中之一，它是可以的，所以。

<details>
<summary>Original English</summary>

**Audience**: I'm not sure if the the PR history is really the best source but I think it it can be one it can be one of it can so

</details>

**Nupur**: 这就是为什么有各种呃不同的信息来源，对吧，所以它包括 PR 历史，它包括你的资源，它包括你的，并且有人在我家做饭，是的，但它可以是，呃，来源之一，这也是为什么……

<details>
<summary>Original English</summary>

**Nupur**: that's why there are various uh sources right so it's PR history it's your resource it's your and somebody's cooking food at my home yeah but it it can be uh one of the source and that's why

</details>

**观众**: 我的问题是，是的，我的意思是当然它可以，它可以是对的，但是，是的，到最后你需要决定，比如说在裁判那里，对吧，你给了多少权重，对吧，所以，就像针对工程原则、架构原则的新文档，并将它们与，比如，你的合并记录进行比较，是的，是的，对的，它们可能会完全失衡，对吧？

<details>
<summary>Original English</summary>

**Audience**: and my question is like yeah I mean of course It can it can be right but yeah at the end you need to decide let's say also in the jury right how much you weigh right so like the new documents for let's say the engineering principles architecture principles and compare compare them to let's say your your mer yeah yeah right they could be completely out of balance right

</details>

**Nupur**: 嗯，这要视情况而定，再说一次，我认为，如果你从一个角度来看，这是很难决定的，但如果你从多个角度获取上下文，比如 PR 历史记录那是一部分，但是当你做合规性审查并在合规门户中说明这非常重要时。所以我们有不同的片段划分，它是错误，它是建议。所有这些类型的事情都会增加反馈的权重，以说明它是好还是坏。每次你的开发者接受一个建议时，它在下一次的权重就会增加。如果它没有接受建议，它的权重就会降低。因此，这完全取决于索引并确保这些权重在某个地方得到管理。

<details>
<summary>Original English</summary>

**Nupur**: um it depends it depends so again uh I think It's if you look into from one perspective it's difficult to decide but if you're getting the context from many angles for example PR history that's one part but when you do the compliance and you tell in the compliance portal this is really important. So we have various uh segments of it's an error, it's an uh a recommendation. All those kind of things adds weight to a feedback to say if it's good or not. And every time your developer expect accepts a suggestion, it gets more weighted for the next one. If it does not uh uh accept the suggestion, it gets a less weight. So it's all about indexing and making sure those weights are managed somewhere.

</details>

**Nupur**: 呃，有两种方式。一种是，呃，当你提供建议时，你的开发人员是否真的接受了它，我们会对此进行索引。另一种方法是，呃，从过去的 PR 中，我们试图找出发现的类似问题，以及你的开发人员是否实际实施了它们。例如，有些人习惯于**硬编码**他们的 API 密钥，我真的和开发人员有过激烈的争论，但这就是我们一直的做法。不，这不应该，这不应该是这种做法。是的，不过这也很好地契合了我的意思，对吧，所以如果你查看历史记录，发生过的事情并不意味着它是，它是好的，它是，是的，这就是系统试图告诉你这不好，这不好，然后这取决于你的方式。

<details>
<summary>Original English</summary>

**Nupur**: Uh two ways. One is uh by when you when you give your recommendations does your developer actually accept it or not we uh index that. Another way is uh from the past PRs we try to find out similar issues identified and if your developer actually implemented them. So for example some people are used to hard-coding their uh API keys and I literally had a tough um argument with the developer but this is how we do it. No this is should this should not be the way. Yeah but nice thing nicely match also what I meant right so if you look in the in the history that happened doesn't mean it's it's good it's yeah and and that's the way where the system tries to tell you this is not good this is not good and then it's up to you

</details>

**观众**: 只有当你提供了指导时，对吧。

<details>
<summary>Original English</summary>

**Audience**: only if you provide the guidance right

</details>

**Nupur**: 不，所以有一些东西叫做错误修复，还有一些东西叫做规则，所以如果你把它们作为规则提供，无论你是否想要，它都会被高亮显示。然后还有一些错误，智能体试图告诉你有些地方出错了，如果审查员也同意并且没有实施 10 次，审查员可能会降低它的权重，然后给你……

<details>
<summary>Original English</summary>

**Nupur**: no it so there is something called bug fixes and there is something called rules so if you provide them as a rule it will get uh highlighted doesn't matter if you want it or not. And then there are bugs where agent tried to tell you there's something wrong and if the reviewer also agrees with it and did not implement a 10 times the reviewer might get it less weighted and give you

</details>

**观众**: 酷。非常感谢。

<details>
<summary>Original English</summary>

**Audience**: cool. Thank you so much.

</details>

**Nupur**: 谢谢。

<details>
<summary>Original English</summary>

**Nupur**: Thank you.

</details>