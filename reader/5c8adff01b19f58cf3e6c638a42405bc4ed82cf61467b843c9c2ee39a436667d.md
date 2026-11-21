---
author: AI Engineer
date: '2026-08-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Z-c11pV_uvU
speaker: AI Engineer
tags:
  - agentic-ai
  - anti-patterns
  - context-management
  - multi-agent-systems
  - prompt-engineering
title: Claude认证架构师考试：智能体工程的反模式实战指南
summary: 加州大学伯克利分校的Frank Coyle教授深入解析Anthropic新推出的Claude认证架构师考试。他通过六大生产场景，重点剖析智能体工程中的常见反模式：从循环控制与停止原因、上下文隔离、子任务压缩到多智能体协作中的群体思维陷阱，为智能体AI职业发展提供实用导航。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
products_models:
  - Claude
media_books: []
status: evergreen
---
### 实验哲学与反模式思维

在深入考试细节之前，我想先分享我的核心哲学。正如艺术家**Sister Corita Kent**所言："没有什么是错误，没有赢也没有输，只有创造。"底线就是不断实验、实验、再实验。你不仅要阅读，更要动手实践。当你创造东西时，很多时候会失败——**托马斯·爱迪生**说过："我没有失败，我只是找到了10000种行不通的方法。"

这引出了**设计模式运动**（Design Patterns Movement: 20世纪90年代初伴随面向对象编程兴起的解决方案模板体系）的核心洞见。当时我们为对象建立了模式，如今我们为智能体建立模式，但同样重要的是**反模式**（Anti-patterns: 应当避免的常见错误做法）。理解什么不该做，恰恰是引导你走向正确做法的关键。

<details>
<summary>Original English</summary>

So, this is a quote from a woman named Sister Corita Kent. "Nothing is a mistake. There's no win and no fail. There's only make." Bottom line here is experiment, experiment, experiment. Not only should you read, but you should do. You should make stuff. Now, what happens when you make stuff? A lot of times things don't work. Thomas Edison said, "I have not failed. I've only found 10,000 ways that don't work."

And what I want to emphasize here is that what this shows us are something that in the design patterns movement, which came around in the early 1990s with object-oriented programming, we had patterns for objects. We now have patterns for agents, but there's also anti-patterns. And I think anti-patterns are a key to understanding what you should not do because understanding what you should not do is the key to leading you to what you should do.

</details>

### 考试概览与五大领域

**Claude认证架构师考试**（Claude Certified Architect Exam: Anthropic推出的官方认证，2026年3月发布）是全新的认证体系。它基于场景、限时、有监考，面向Claude生态系统的企业开放，个人可支付99美元参加，每6个月一次。考试虽为选择题，但基于现实约束和真实场景设计。

考试覆盖**五大领域**：**智能体架构**（Agentic Architecture: 智能体系统的整体设计与组织）占27%；**Claude Code配置**（如何配置系统与工作流）占20%；**提示工程**（Prompt Engineering: 结构化输出、JSON应用）；**工具设计**（Tool Design: 工具的设计与集成）与**模型上下文协议集成**（Model Context Protocol Integration: 标准化上下文交换协议）；以及**上下文管理与可靠性**（Context Management and Reliability: 上下文窗口的维护与系统稳定性）。考试提供六个生产场景，随机抽取四个作为出题核心。

<details>
<summary>Original English</summary>

So, a little bit about the Claude Certified Exam, released in March, so it's brand new. It is based on scenarios. It is timed. It is proctored. It is available to companies in the Claude ecosystem, the Anthropic ecosystem, but individuals can pay $99 and take the exam once every 6 months. And it's not just multiple-choice questions. It is multiple-choice, but they are based on realistic constraints and realistic scenarios.

The five domains. There are five domains that are covered and they give you the percentages of each. So, agentic architecture, 27%. Claude code, how to configure the Claude code system and workflow, 20%. How to doing prompt engineering, structuring your output, using JSON all over the place. Tool design. Model context protocol integration. These are topics that you should understand and know whether you're going to take the exam or not. This is going to help you get ready for whatever the agentic world is going to throw at you. And then there's going to be contact management and reliability. So these are the areas of the kind of questions you're going to run into.

Then there are and they provide you with six production scenarios and your the exam will randomly choose four and all the questions will be centered around the four that they choose.

</details>

### 循环：智能体计算的新范式

在深入场景之前，我想指出一个关键现象：每个人都在谈论**循环**（Loops: 智能体系统中反复执行直至满足条件的控制结构）。**Boris Cherney**说他不写代码，他的工作是写循环；**Peter Steinberger**（Open Claw大师）说："我不再编码了，我只设计循环来提示你的智能体。"

但循环真的是新事物吗？并非如此。回到计算的早期，编程语言爆发式增长，Fortran、COBOL之间争论不休。**Böhm和Jacopini**在1966年证明：一个语言要实现**图灵完备**（Turing Complete: 能计算任何计算机可计算的问题），只需要三样东西——顺序执行语句、if-then条件判断、以及循环。加上循环，你就拥有了图灵可计算性。如今，我们在智能体世界见证了它的复兴。此前我们只有序列——提示、条件判断，但现在我们有了循环，这正是智能体技术令人兴奋的力量所在。

<details>
<summary>Original English</summary>

Now, here's something that I like to point out. Everybody's talking about loops, right? The loop is the new thing. Boris Cherney says he doesn't write code, but his job is to write loops. And Peter Steinberger master of Open Claw says, "I don't code anymore. I just design loops that prompt your agents."

So, loops are the new big thing, right? Well, no, they're not. Back in the day, early days of computing, we had programming languages were exploding. We had Fortran, we had COBOL, and there were big fights. My programming language is better than yours. It can do more. No, it can't. We can do this. Böhm and Jacopini, 1966 proved that if you want a language to be Turing complete, which means can compute anything that computers are possibly able to compute, then you need only three things. The ability to write statements sequentially, okay? To have if-then conditionals, and the third piece is the loop. If you add the loop, you have Turing computability. And now we are seeing this being resurrected in the agentic world with the focus on loops, cuz up to now we've had sort of sequences. You have prompts, you have maybe if-then, but now we have a loop. And now this is what's giving us the power. This is where the agentic stuff is getting very exciting.

</details>

### 场景一：客户支持解决智能体与停止原因

第一个场景是**客户支持解决智能体**（Customer Support Resolution Agent: 自动处理客户问题的循环系统）。这里的反模式是：让智能体自由行动、获取响应后直接使用。正确做法是使用**停止原因**（Stop Reason: Claude Code中每次交互后返回的状态标记，指示模型为何停止生成）进行循环控制。

让我展示一段代码：这是一个`while true`循环。第一个代码块调用模型，传入**消息**（Messages: 上下文窗口中的提示序列）。关键在于理解：**大语言模型**（Large Language Model: 基于海量文本训练的AI系统）本身无法执行任何工具，它只是一个概率性的下一个词预测器。但它能理解工具的功能，并设置好参数，让你的代码去执行。第二个代码块检查停止原因——如果是"工具使用"（Tool Use），就运行工具并获取响应。然后循环继续，模型看到成功运行后结束循环。

在获得答案后，你有机会引入**人在环路**（Human in the Loop: 人工审核机制）。检查置信度，如果良好则保留，否则升级给人工处理。另一个必须检查停止原因的情况是**令牌耗尽**（Token Exhaustion: 上下文窗口容量用尽导致生成中断）——此时响应基于不完整信息，必须采取行动。

<details>
<summary>Original English</summary>

I'm start with scenario one, customer support resolution. So here we have a loop operating and the I'm going to jump to the anti-pattern. What you don't want is just to let the agent go and do something and get the response back and use it, okay? What you want to do is you want to loop with something called the stop reason. So I'm going to show you a little code here.

So here we have while loop. It's a while true, it's a loop. We're looping right here, okay? So the first little block is where we call the model, okay? And we pass it the messages. The messages are essentially the sequence of prompts that exist in the context window, okay? And we are asking the and we have a prompt and we have the context and we have a tool. And we're asking the LLM to do something with this tool and help us out. The problem is the LLM can't do anything. It is just a probabilistic next word predictor. It can't execute tools. So what it does though is it can figure out if you point it to a tool, it can figure out how to set things up so that you or your code can execute it. So it's important to understand that the LLM is not executing these tools. It can't do anything except talk back to you, very intelligently sometimes, but all it can do is talk back to you.

So when it finishes this task and has a result which is basically here is I've I know what you want. I know what the tool can do. Here's how I It sets up the parameters that can then be or that then used to actually execute the tool. So, the second block you see why did the LLM come back to us? That's our stop reason. Tool use. Oh, okay. We've stopped because the LLM it wants to use the tool. So, let's just run the tool. So, that's what the second block is. Run tool, the response is what the LLM said, and it's basically the parameters that it has extracted from the data that you provided it. Okay? Then it executes that. Then it goes back. That then it continues. Continues means the LLM sees it and says, "Oh, successful run. So, okay." Come back down. We're not running a tool anymore. We're end the end of our loop. Bingo.

Now, then we take the answer, and this is an opportunity for you to have a human in the loop potentially. You check the confidence. If it looks good, you keep it. If you don't, then you escalate to a human. So, now there's another reason why you need to make sure you check your stop reason. One of the stop reasons may be you have run out of tokens, and this response is based on partial when the LLM had to stop. And it's going to give you a response, but if you have run out of tokens, then you need to take action.

</details>

### 场景二与三：Claude Code配置与多智能体研究系统

第二个场景是**Claude Code代码生成**。Claude Code引入了**CLAUDE.md文件**（Markdown格式的规则配置文件，存放项目级指令）的概念。Anthropic推荐三级配置：项目顶层一个、项目文件夹内一个、目录级别可再指定。这样形成**层级化规则集**（Hierarchical Rules: 从项目到目录逐层细化的控制指令），控制系统如何响应。

第三个场景是**多智能体研究系统**（Multi-Agent Research System: 多个智能体协作完成研究任务的架构）。核心问题是如何让智能体分头工作并合理汇总答案。反模式是：创建一个加载了所有工具的单一智能体。这就像你雇了一个木匠，结果他带着水管工、电工的工具上门说"我什么都能干"——你可能更想要一个专业的木匠。这呼应了**函数式编程**（Functional Programming: 强调函数单一职责的编程范式）的理念：函数应该只做一件事。让每个智能体专注于一件事，配备一两个工具，这就是成功的关键——**专业化，不要过载**。

另一个关键点是：**不要让智能体的上下文溢出到主上下文**。上下文意味着令牌，令牌意味着金钱。上下文越多，LLM给出答案时就越混乱。即使有一百万令牌的上下文窗口，也不要把所有东西都塞进去——限制输入才能获得更准确的系统。

<details>
<summary>Original English</summary>

Next scenario. Code generation with Claude. So, Claude code has this concept of the Claude MD file, a markdown file, where you put all the things you wanted to know. What Anthropic recommends is you have three levels of Claude. One that you have at the top level of your project, the other that you have in inside your sort of the project folder, and then within directories you can also specify. So, the idea is to have a hierarchical set of rules that can then control how the system is going to respond.

Moving right along, we have a multi-agent research system. So, here we're going to have the problem is how do I get my agents to go off and do stuff and bring the answers back in a reasonable way? The anti-pattern you have one agent and you load it up with tools, all right? So, I like to think about you know, you hire somebody to come to your house, you hire a carpenter to come to the house, and the guy shows up with plumbing tools, carpenter tools, electrical tools. He says, "I can do anything." Well, maybe you don't want this guy, maybe you want a professional carpenter. So, that's the kind of idea. And this kind of back takes us back to some of the functional programming ideas that functions should be do one thing. And if you can get your agents to do one thing, you with maybe one or two tools available to it, then that's going to be a win, and that's going to help you with this exam. So, specialize, don't overload.

The other part of this is don't let your agents context spill over into the main context because context means tokens, tokens mean money, and the more context you have, the more confused the LLM is going to be in giving you an answer. So, even though oh, a million token context window, I can put everything in there. No, no, don't put everything in there. Limit what's going to go in there because then you're going to get a much more accurate system.

</details>

### 多智能体协作中的群体思维陷阱

关于**专业化子智能体**（Specialized Sub-agents: 专注于单一任务的辅助智能体），这里有一个具体例子：**评论者智能体**（Critic Agent: 负责审查和评估其他智能体输出的智能体）。假设你运行了一些任务，现在想让一个智能体审查结果。你只需要给它解决问题所需的信息——这里只传递**主张**（Claim: 解决方案的陈述）和**证据**（Evidence: 支持主张的数据），但不传递产生主张的思考过程。

为什么？因为当多个智能体协作交流时，存在**群体思维**（Group Think: 群体趋向一致意见而丧失独立思考的现象）的倾向——所有智能体似乎都会退化到同一个想法。就像在聚会上，除了你大家都想吃披萨，但为了不扫兴你只好随大流。智能体似乎也以同样的方式运作。所以，给每个智能体**只分一片**——每个智能体得到自己的那一份，这样结果才能准确。

<details>
<summary>Original English</summary>

So, here's an example of a specialized sub agents. You're giving it so, this would be the critic. So, let's say you've run some stuff. Now, you want to get an agent to look at what's happened. What you want to do is just give it what it needs to solve that critic problem. I'm only giving it here the we're passing it the claim and the evidence. So, this is your claim is sort of how we're going to solve the problem. Here's the evidence, but we're not giving it the thought processes that went in to creating this claim. Why?

When you get a bunch of agents together collaborating and talking to each other, there's a tendency to have group think. And all the agents seem to kind of devolve into one idea. I mean, it's like, you know, you're in a group, you know, you're at a party, and everybody wants pizza except you, but then people talk you into you know, you don't want to spoil the party, so you'll go along. And it seems that agents kind of work in the same way. So, you're going to return basically, you're going to give each agent only a slice. I didn't think about the pizza analogy, but yes. Every agent gets its own slice, and it should come through.

</details>

### 场景四：开发者生产力与上下文隔离

第四个场景是**开发者生产力**。反模式是：让每个子任务把完整输出倾倒入主线程，挤占上下文——这会导致上下文无界增长，是糟糕的做法。正确做法是**隔离子任务输出**（Subtask Isolation: 将子任务的输出限制在独立上下文空间中），并**压缩长会话**（Session Compaction: 对长时间运行的会话进行上下文压缩）。

这里有一个模式示例：让智能体扫描日志并生成问题摘要。使用**上下文分叉**（Context Fork: 将智能体分叉到独立线程，其产生的令牌不会污染主上下文）。智能体在分叉线程中思考、添加令牌，但不会回流污染主上下文。然后你只把摘要（而非全部细节）加入主上下文。

最后一个有趣的机制是**令牌计数检查**（Token Count Check: 监控当前上下文令牌数量的方法）。你可以设置阈值——比如超过150,000个令牌时，运行**压缩算法**（Compaction Algorithm: Anthropic提供的上下文压缩机制）。虽然我不确定具体实现方式，但压缩功能确实存在。顺带一提，我注意到街上有人分发一本小册子，作者是**Sam Bagwell**，书中提到他的公司提供自定义上下文压缩逻辑——你可以扩展他的基类，实现自己的数据压缩方案，这为整个领域提供了有趣的视角。

<details>
<summary>Original English</summary>

Fourth scenario, developer productivity. So, the anti-pattern. Let every subtask dump its full output into the primary thread, crowding out the context. Again, this is what we're I was just talking about. This is bad. Let the context grow unbounded. Bad, right? For the reasons we just talked about. You want to isolate your subtask output, and you want to compact long sessions. I'm going to take a second to talk about that. So, here's an example of a pattern. You want to have your agent look at the logs and create a summary of where the problems are in the log. So, here's your task, scan all the logs for error.

Context fork. So, you're forking the agent into a like a separate thread where whatever the agent does and thinks and adds tokens to does not come back and pollute the main context. Now, you see here what happens, then you take this summation, and then you add that summation without all the other stuff into the overriding context. Now, this last little block is kind of interesting, I think. Because you can check your token count, and you can determine how big the token count is. And if you can set some limit and you know, if you have more than 150,000 tokens, then what you want to do is you can run a compact. So, Anthropic and Claude have these compaction algorithms that take this giant context and compact it in some way, shape, or form. Not quite sure how the implementation is of that, but there is compaction.

Now, a little side effect a little side channel I've been walking around when you walk outside, you see these guys handing out these books. Okay? Anybody see these guys handing out these but take them. This is actually a pretty good little book. In fact, I was looking at it last night and one of the things it had in it was this is by this guy Sam Bagwell. I have no connection I didn't even know Sam, but it there's a online page 32. It says his company provides custom logic for compression of context. So, he's got an and you can write your own. He's got a he's got he you can extend his base class and have your own compression of your data, whatever you think is important. So, I think that's kind of an interesting spin on this whole thing.

</details>

### 持续集成与批量模式优化

关于**Claude Code持续集成**（Continuous Integration: 自动化构建和测试的软件开发实践），反模式是：在流水线中总是使用**交互模式**（Interactive Mode: 需要人工确认的对话式操作）。这会导致Claude停下来询问"你想这样做吗？我能获得许可吗？"——应该配置为直接运行到底。

另一个实用技巧是**批量模式**（Batch Mode: 异步处理提示的工作方式）。你可以把提示和工作放入批处理，以**减少50%的令牌成本**，结果在24小时内返回。所以，如果你要去午睡、度假或休息一天，用批量模式运行任务，就能节省开支。

<details>
<summary>Original English</summary>

Cloud code for continuous integration anti-pattern: Always have interactive modes in a pipeline. Well, no no no cuz interactive modes mean Cloud will stop and ask you, "You want to do this? You want to do that? Can I have permission for that?" So, there are ways to set it up so that it'll just run straight through, okay?

The other tip that I'll give you here is there's something called the batch. So, you can take your prompts, you can take your work, and you can put them in a batch and for 50% fewer token cost you will get the result they promise in at least 24 hours. So, if you're going to go take a nap, you're going to go on vacation, you're going to go out, take a day off, run your stuff in batch mode, and you're going to have a less to pay.

</details>

### 结语：只有创造

最后，记住：没有什么是错误，没有赢也没有输，没有考试，只有创造。你去做、去创造，就会成功。如果你想联系我，我在Berkeley的邮箱是coil，也可以查看我的网站co-supreme AI——我是个爵士乐迷，网站以**John Coltrane**的《Love Supreme》命名。

<details>
<summary>Original English</summary>

All right, I've only got a few minutes left, few seconds left, but I want to conclude with this. Remember, nothing is a mistake. There's no win, there's no fail, there's no exam, only make. You do it and you make it and you're going to succeed. If you want to reach out to me, reach out to me coil at Berkeley, look at my websites. I got a website co-supreme AI. I'm a big jazz fan and I named this website after John Coltrane, Love Supreme, if you know that song, great. Anyway, that's my story and I'm sticking to it and I'm about to zero time.

</details>