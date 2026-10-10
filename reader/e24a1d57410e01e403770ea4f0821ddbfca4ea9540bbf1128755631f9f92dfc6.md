---
author: AI Engineer
date: '2026-07-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=8oyalrfwgjw
speaker: AI Engineer
tags:
  - recursive-language-model
  - context-management
  - code-base-analysis
  - agentic-workflow
  - externalized-context
title: 探索递归语言模型在大型代码库中的上下文管理与应用
summary: 本文探讨了递归语言模型（RLM）的概念，重点阐述了如何将RLM应用于处理超大型代码库的挑战。文章介绍了现有解决方案，如搜索、语义搜索和上下文压缩，并提出了核心思想：将上下文管理外化到可编程执行环境，使模型能够编写代码来动态检查、切片和计算相关块值。最后通过实践演示了如何利用RLM作为记忆层，实现对大型项目进行根本原因分析或仓库上岸等复杂任务的自动化工作流。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 探索大型代码库的RLM概念

今天，我们将探讨**RLM（递归语言模型）**的概念，以及如何将这些概念应用于更大的代码库。我的名字是 **Shashi**，我是 **Superagentic AI** 的创始人。首先要明确的是，**RLM论文**是由 **MIT** 和其他朋友发表的，你可以阅读完整的论文。但本次分享的目的是教你如何将RLM的概念融入你自己的工作流程中，以实现你自己的工具（harnesses）。

<details>
<summary>Original English</summary>
Hello and welcome to this online track talk for the AI engineer world fair 2026. Today we're going to explore the concept of RLM also known as recursive language models and how we can use those concepts or larger code bases. My name is Shashi. I a founder of super aentic. First of all, let's be clear that RLM paper has been published by MIT and friends. As you can see, there's a full paper. You can read about it. But the purpose of this talk is how you can use the concepts of RLM and you can use into your own workflow to implement your own harnesses.
</details>

### 大型代码库的上下文管理挑战

首先，我们面临的问题是什么？如果你使用编码代理处理较小的仓库或单体仓库（monorepos），它们表现非常好。但如果你尝试用**大型上下文**处理单体仓库时，你知道存在一个上下文问题：随着上下文的增长，性能会下降，如果你正在处理单体仓库，这个问题会变得更糟。在本次分享中，我们将看到我们选择了代码库，并且RLM的概念与更大的代码库是相关的。

<details>
<summary>Original English</summary>
First of all, what's the problem? If you're using the coding agents for smaller repos or monorepos, they works exceptionally well. But if you have ever tried it with the monorepos with the large context you know there's a context problem as the context grows the performance degrade and if you're working with the monorepo this problem get worse. In this talk we will see we selected the code base and the concept of RLMs are relevant for the larger code bases.
</details>

### 解决大型代码库的现有方法

如果你使用过编码代理，你可能已经看到了其他编码代理工具为了解决这个问题采取的不同方法。最常见的做法是使用像 **grab** 这样的工具进行搜索。基本上，存在一个文件系统，而编码代理工具会利用这些工具进行搜索。第二种方法是你可能见过**语义搜索或本地搜索**。这里的想法是你可以通过代码进行搜索并整理上下文。另一种方法是将长上下文压缩，然后你可以使用上下文的摘要版本，市场上也有一些内存解决方案可以用来持久化为编码代理存储记忆。

<details>
<summary>Original English</summary>
If you have used the coding agents then you probably saw that there are different approaches that other coding agent harnesses have been taken to solve this problem. Most common approach is searching using the tools like grab. So basically there's a file system and the coding agent harnesses search using these tools. The second approach you probably seen that the semantic search or the local search. So idea here is basically you can search through the code and curate the context. Another approach is the long context get compressed and you can use the summarized version of the context and there are some memory solutions available in the market as well that you can use to persist the memory for the coding agent.
</details>

### RLM的核心思想：外部化上下文管理

RLM的核心论点是，你需要将**上下文管理外化到可编程执行环境**中。这意味着你应该有一个独立的专用环境，让模型可以在其中运行。在这种情况下，例如你的整个代码库被视为模型可以操作的数据。然后，模型可以编写代码来检查、切片并计算相关的块值，你就可以将这些值输入到主上下文窗口中。

<details>
<summary>Original English</summary>
Core thesis of the RLM is you need to externalize the context management into programmable execution environment. Meaning you should have a separate dedicated environment so that model can operate on that. In this case for example your whole repository is treated as a data that model can operate on. Then model can write the code to inspect slice and compute the relevant chunks value you can then feed into the main context window. So basically rather than putting everything into the model's context create a separate dedicated environment give them a coding agent or ripple and then model write the code to curate the context that can be used into the main.
</details>

### RLM作为记忆层与软件工程类比

这是一种被证明非常有效的上下文管理技术，也可以用作你编码代理的**记忆层**。让我用一个简单的类比来总结这一点：想象你是一名首席软件工程师，被分配到一个拥有巨大代码库的新项目。假设这是一个单体仓库（monorepo）。这位首席工程师如何处理代码？与其逐行阅读代码，工程师可能会检查代码库、做一些笔记，了解项目的依赖关系和结构。如果某些东西没有被仓库的工程师理解，他可能会向另一位工程师或专家寻求一些想法。RLM中的这些概念同样适用于大型项目，比如文件、文档、文本和配置文件，因为仓库有很多东西，而**可编程的Ripple**就像一个笔记本，工程师可以对代码库做笔记供研究；他可能使用其他技术，或者编写脚本从仓库中搜索某些内容。如果他卡住了，他会向另一位工程师或专家提问，这就是LLM查询。

<details>
<summary>Original English</summary>
Could be also be used as a memory layer for your coding agents. Let me summarize this giving you a simple analogy. Imagine you are a lead software engineer and assigned to the new project with a huge code base. Imagine that's a monorepo. How does that lead engineer deals with the code? So rather than reading line of code line by line engineer probably inspect the code base make some notes see what are the project's dependencies how it is structured if something else uh is not understood by the repository engineer probably asked to another engineer or expert to get some ideas and the same concepts applied in RLM so large project like the files and docs and texts and configs because repository has a lot of things and the programmable ripple it's kind of a notebook that engineer makes a note about the codebase that can be used researching he may be using other techniques or maybe it's writing some script to search something from the repo and then if he stucks then he ask another engineer or specialist where it come to the LLM query and LLM query is basically ally asking another model environment to get an answer from and once they get answer then the loop continues and at the end it returns the clean note synthesis. So the recursion part here is engineer ask another specialist using LLM query that can be one question or that can be number of questions. So this is where the recursion comes in picture. Loop is basically your repo as your context and then the model writes the ripple code to get some relevant context that returns the bounded observation and if we if loop needs more information it passes through the llm query where it ask another language model or another system to get the response return the value and continue the loop. and the loop get terminated until we get a final results.
</details>

### 代码库与书籍的本质区别

我们为什么讨论代码库而不是像书籍或词典那样的“大上下文”？代码库有目录、测试文件、导入、依赖项、配置等，它不仅仅是文本，它是一种**结构化数据**，模型需要理解和推理这些文本。这就是我选择使用代码作为场景来证明RLM概念的原因。

<details>
<summary>Original English</summary>
Why we talking about the code base and not the big context in terms of like other things for example books or dictionaries is different? It has directories, it has test, it has some imports, it has dependencies, it has tests, it has pictures, it has configuration files. So the codebase is not only just um the text, it is a structured data and the model need to understand and reason over the text. That's why I chose this scenario to use a code basis to prove these concepts of RLM.
</details>

### 自研RLM代码与实践演示

现在，让我们切换到我们创建的 **SuperagentAI** 库中的 **RLM Code**。你可以看到 RLM 代码的落地页，这里只是一个研究游乐场，你可以试验RLM的概念。我们有文档供你参考，还有一个完全开源的项目 GitHub 仓库，你可以使用和玩耍。

<details>
<summary>Original English</summary>
Now let's switch the gear and talk about our own library that we created at super agentai called RLM code. You can see RLM codes landing page here where this is just a research playground where you can the concepts of RLM. We have um documentation that you can take a look and there's a the GitHub repository. It is completely open source project that you can use it and play with it.
</details>

### 实验环境与RLM工作流程演示

我们已经实现了一个叫做 **RLM mode** 的东西。我们是直接使用现有的 RLM，没有在RLM的想法和论文之上添加任何内容。我们使用了递归调用、Ripple执行的相同概念。然而，你可以用本地模型运行它，也可以用云端模型运行它，你还可以接入任何你选择的可观测性框架。这为RLM提供了极大的灵活性。

为了演示这一点，我们创建了一个源代码仓库，你可以使用MIT的RLM论文和RLM代码来亲自尝试这个概念。我们将看到这些文件在实践中是如何运作的：上下文是如何创建的、Python Ripple是如何编写代码的，以及它如何传递给LLM查询，以及我们如何获得最终结果。这部分将在直播演示中展示。

<details>
<summary>Original English</summary>
Now let's switch the gear and talk about our own library that we created at super agentai called RLM code. You can see RLM codes landing page here where this is just a research playground where you can the concepts of RLM. We have um documentation that you can take a look and there's a the GitHub repository. It is completely open source project that you can use it and play with it.
</details>

### 实时演示：RLM工作流程的闭环

我们现在来做一个 **RLM** 和 **RLM Code** 的直播演示，看看它如何在更大的代码库中运作。我这里有一个代码仓库我已经检查过了，让我们打开它进入编辑器，以便我们能看到里面有什么。你可以看到一个演示目标，我们在这里使用 RLM 代码作为演示，然后有一些你可以自己遵循的说明。基本上你有一个 **readme文件**，你可以用它来配合你的本地模型，或者我们将用 Gemini。我们会尝试这个脚本看看发生了什么。

<details>
<summary>Original English</summary>
So I have a code repositories here I have checked out and let's open it into the editor so that we can see what's inside it. So as you can see there's a demo target which is um we are using RLM code source as a as a demo here and then we have some instructions that you can follow along um yourself. So basically you have a readme file that you can use to use with your local model or so we are going to use with the Gemini. So we will try this script and see what happened.
</details>

### 运行结果与可观测性追踪

现在你可以看到我们正在使用 **Docker** 作为沙箱。如果你看到 Docker 容器刚刚启动了，就是为了这个 RLM。回到我们的执行部分，你可以看到执行已经完成了。在这个执行中，你基本上在第一步可以看到模型编写了你可以看到这里的 Ripple 代码。然后它构建了证据，之后它还向 LLM 查询发送了一些提示（prompt），得到了结果，最后给出了最终答案。在这里，你可以看到所有这些步骤都回到了最终答案。这里你可以看到它做了两次工具调用，以及为这个模型使用了多少 tokens，你可以在这里看到。好消息是，你可以在 RLM 代码仓库中看到所有这些追踪信息。例如，你可以看到所有的运行记录，这就是我们刚刚做的运行。你可以看到所有的会话和所有的可观测性数据，你可以将其接入任何你选择的可观测性平台。

<details>
<summary>Original English</summary>
So right now you can see we're using the docker as a sandbox. If you see the docker container has been just started for this RLM. And now coming back to our execution you can see that execution had just finished. And in this execution what you have seen basically in the first step model has written the ripple code that you can see here. And then it's built the evidence and after that it also made the calls to the LLM query with some prompt and got the result back and after that it gives the final answer. And as you can see here we can have all this all the step coming back to the final answer. And here you can see the it made the two tool calls and how many the tokens is used for this model that you can see it here and the good thing is that you can see all these traces in the RLM code repositories. So for example you can see all the runs. This is the run that we just did. You can see all the sessions and all the observability that you can plug it into any of your obser favorite observability platform.
</details>

### 实验环境与模型连接

我们还可以使用这种类似编码代理风格的实验性工具，你可以在这里尝试同样的事情。首先，让我们连接到 **Gemini** 模型。你可以使用 `connect` 命令连接到 Gemini 模型，指定一个提供者（provider）和模型名称。现在你已经连接上了。你还可以运行 `doctor` 命令查看一切是否正常。看起来 `Dr. Command` 发现了一些警告，但这与深度代理 ADK 和其他框架有关，与本次演示无关。有趣的部分在于，基本上你是发送提示词（prompt）。

<details>
<summary>Original English</summary>
So this is the CLI path we just demonstrated but we also have this um kind of coding agent style experimental harness where you can try the same thing. So first of all let's connect with the Gemini model. So you can connect with the Gemini model using the command connect. You can you can have a provider and the model name. Now you are connected. So you can also run the doctor command and see if everything is okay. Seems like Dr. Command found some warning. But this is related to deep agent ADK and other frameworks which is not relevant to this demo. And an interesting part where we will be saying is basically you are sending the prompt.
</details>

### 观察RLM循环的完整流程

现在，我们运行命令并提出问题，指定预算，这样我们就不会在这个运行中花费太多。但一旦你这样做，你可以看到你的最大步数、递归深度，它完成了这次运行，并返回结果。我们还可以看到这个东西进入研究实验室，我们可以看到这个 Spin 已经完成，可以看到一些奖励。我们还可以看到轨迹（trajectory），这是非常重要的一部分，我们可以看到所有的 RLM 循环，例如 Ripple 和代码和最终输出。我们还可以看到它开始和结束时的事件。你可以玩弄这个 **RLM 代码终端用户界面**，它有点像一个工具（harness），你可以在这里试验你的 RLM 想法。

<details>
<summary>Original English</summary>
So for what we did now we run the command and we ask the question we specify the budget so that we don't not spending too much uh on this run. But once we do that as you can see your maximum steps recursion depth and it completed it this run and coming back with the results. We can also see that this thing into the research lab where we can see this spin has been completed. We can see some rewards. We can also see the trajectory which is important part where we can see the all the RLM loop for example the ripple and the code and the final output. So and also we can see the events when it started and when it ended. So you can play around with this RLM code terminal user interface which is kind of harness and you can experiment your RLM ideas in here.
</details>

### 总结与未来应用方向

总而言之，我们刚刚看到的是：我们的上下文已经被加载了。我们编写了一些 Ripple 代码来提取一些片段。我们也调用了元素查询（element query）来从另一个模型获取更多上下文。这就是**递归**发挥作用的地方，我们得到了最终结果，并且得到了以 JSONL 格式存储的追踪信息，你可以将其导入任何你选择的可观测性平台。我们还看到了这些结果来自不同的文件。你可以查看可用的源代码。

在现实中，AI工程师如何将这些概念应用？例如，如果你处理大型源代码并想进行**根本原因分析（root cause analysis）**、仓库的**上岸（onboarding）**或一些不熟悉的仓库，这里有一些用例可以借鉴RLM的概念。基本上你可以根据自己的需求设计自己的工具，从而捕获整个轨迹：包括规划、编码、观察、子调用、预算和最终输出。

<details>
<summary>Original English</summary>
In a nutshell, what we just saw basically our context has been loaded. We have some ripple code written to extract some snippets. We also saw the element query has been called to get some more context from another model. This is where the recursion comes in picture and we got the final result and we got the traces in JSONL format that you can import it into the any of the observability platform of your choice and we also saw this results coming from different files. You can take a look at the source code that will be available uh for you. Let's talk about the real thing how AI engineer could use this concepts in the real life and there are few things for example if you're dealing with the large source code and you want to for example root cause analysis or on boarding of the repositories or some unfamiliar repos. So there are few use cases you can from here and probably try to use RLM concepts over there. Basically you can design your own harness um based on your needs. So that should capture the whole trajectory all these things like the planning coding observation sub call budget and the final output.
</details>

### 行业应用与RLM的渗透趋势

最后，关于RLM概念的使用和应用。我最近在 X 上看到了很多帖子说，**RLM的概念**正在被用于一些专有领域，比如使用 **RLM概念**作为底层技术来构建**托管代理动态工作流（managed agent dynamic workflows）**。他们已经在他们的代理工具中实现了或使用了 RLM。我最近看到 **CodeX harness** 正在编写 Ripple 中的 Python 代码来整理上下文，这是 RLM的一种形式。我也看到了像 Clouds Manage Agents 或 Gemini Managed Agents 这样的模型，它们本质上都是 RLM 的概念。基本上，你可以将工具放在沙箱里进行操作，然后你可以做这些事情。关于动态工作流的最新进展是，一个代理在接收到任务后，可以同时看到多个具有独立沙箱的代理协同工作并返回最终结果，其核心思想基本上都来自于 RLMs。虽然很多软件工厂的概念可能正在使用 RLM，但我们还不确定。然而，一些来自 **Anthropic** 的云代码工程师在 X 上表示他们已经使用了 RLM 的概念。你可以将这个 RLM 概念应用到你的大型上下文仓库中。如果你有任何问题，随时可以联系我。最后，非常感谢大家收看我的分享。

<details>
<summary>Original English</summary>
Now coming back to the final point about RLM concepts and where it's been used. I have recently came across a lot of the post on X saying the RLM concepts have been being used into some of the proprietary things like the managed agent dynamic workflows using the RLM concepts under the hood. So they have implemented one or more for RLM inside their agent harnesses. Recently I saw that the codeex harness is writing the Python Python code in the ripple that you can see to curate the context that is one form of RLM I have seen myself and obviously the clouds manage agents or Gemini managed agents they're all kind of concepts of RLM so basically you can get the harness in the sandbox and then you can do the stuff and the recent things about the dynamic workflows where one agent given the given the task you can spot on multiple agents that have their separate sandboxes. They can work together and give back the final results and the idea is basically generally coming from the um RLMS. A lot of software factories concepts are probably using the RLMs but we are not sure yet. However, some of the cloud code engineers from anthropic has accepted on X that they have used concepts of RLM. You can use this RLM concept on your large context repository. And if you have any questions then feel free to reach out to me. And finally, thank you so much for listening to my
</details>