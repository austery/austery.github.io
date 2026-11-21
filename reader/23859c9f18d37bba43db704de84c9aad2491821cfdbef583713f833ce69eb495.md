---
author: AI Engineer
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=WWIFiQi9U4w
speaker: AI Engineer
tags:
  - ai-agent
  - sandbox
  - security-boundary
  - code-execution
title: 所有 AI Agent 框架唯一达成的共识：沙箱执行边界
summary: Daytona 开发者体验工程师 Mislav 指出，各大 Agent 框架对 Agent 定义与工作流各持己见，却在代码执行上共同走向独立沙箱隔离。框架与模型均易替换，唯有执行边界深刻影响系统架构，应先于框架做出抉择。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 跨框架集成的共性模式与争鸣

>> 感谢各位的到来。我叫 Mislav，是 Daytona 的一名开发者体验工程师。在过去这一年里，我在那里的主要任务和目标就是把 Daytona 集成到基本所有沙箱能派上用场的地方，因为我们 Daytona 就是一家沙箱提供商。这些场景涵盖了 Agent 框架、编码 Agent 运行测试脚手架、工作流工具、开发者产品等等类似的东西。在这一过程中，我注意到一个一直在重复出现的模式，它让我停下来思考了一些事情，并最终促成了今天这场演讲。

<details>
<summary>Original English</summary>
>> Thank you all for being here. My name is Mislav. I'm a developer experience engineer at Daytona. And for the last year, my main my main task and goal there was to integrate Daytona basically everywhere where where Sandbox makes sense because we at Daytona are Sandbox provider. And these are spanning from agent frameworks, coding agent harnesses, workflow tools, development developer products and stuff like that. And during this process, I noticed the pattern that was repeating all the time and it may be it made me stop a bit, think about some things that eventually led to this talk.
</details>

在这张幻灯片上我需要大家的帮助。有人能猜出这是哪个 AI Agent 框架吗？如果有人想猜一下的话——LangChain、LangGraph、Google ADK……好的。

<details>
<summary>Original English</summary>
So yeah, I would need your help on this slide. Does anyone have a guess which AI agent framework is this? If somebody has a guess, LangChain, LangGraph, Google ADK. Okay.
</details>

好吧，就算是 LangChain 吧。但这里最核心的一点是：大家刚才提到的任何一个答案，基本上都是说得通且完全成立的。为什么我会这么说？因为在将 Daytona 集成到这些 AI Agent 框架的过程中，我发现自己几乎很难区分它们之间与 Daytona 相关的代码贡献部分。

<details>
<summary>Original English</summary>
Okay, let let's say LangChain, but the the main thing about this is that whatever you you told can basically be correct and defensible. Why do I say that? It's because during the integration of Daytona into these AI agent frameworks, there I noticed that they I can barely differentiate the Daytona related code contribution part between these.
</details>

在其中的一些框架里，你把它作为一个工具（tool）来集成；在另一些框架里，你是作为一个外部插件来集成，通过安装它来让你的 Agent 具备沙箱能力；而在另一些框架中，你则是继承沙箱客户端类，去调用一些框架内部的 API。但拨开表象看本质，所有这些方式底层调用的都是相同的三行代码：**创建沙箱**、**在沙箱内运行某些代码或任务**，以及**删除沙箱**。

<details>
<summary>Original English</summary>
So in some of these you integrate as a tool, in others you integrate as external plugin that you can install to you know, make your agent use Sandbox capabilities. In other ones, you extend the Sandbox client class and do some internal framework API stuff. But the hood all all of these ways speak the three same lines. So it's sandbox creation, running some code or task inside the sandbox, and sandbox deletion.
</details>

这其实挺不可思议的，因为这些框架大多彼此处于竞争关系，而且它们在某些基础事物或概念上几乎达不成共识。我这么说是什么意思呢？举例来说，它们甚至对什么是 Agent 都无法达成一致：LangGraph 把 Agent 定义为一个可遍历的图；CrewAI 框架把 Agent 定义为一群各自独立做事的角色扮演 Agent；OpenAI 的 Agent SDK 将 Agent 定义为围绕 LLM 模型的一个循环；而例如 Cloud Agent SDK 则是直接提供一个完整的成品，你拿来就用并拥有全部功能，没有任何定制空间。

<details>
<summary>Original English</summary>
And this this is pretty weird because most of these frameworks are competitors and they barely agree on some fundamental things or concepts. What do I mean by that? So for example, they don't even agree on what what an agent is. For example, LangGraph defines an agent as a traversable traversable graph. CrewAI framework defines agents as, you know, bunch of role-playing agents that do do stuff on their own. OpenAI agent SDK is defining agent as a loop around LLM model. And for example, Cloud Agent SDK ships the whole wholly finished product that you just like use and have all full capabilities, no customization.
</details>

此外，它们实现的语言也有所不同，主要是在 Python 和 TypeScript 之间。而且它们在“谁负责指定 Agent 该做什么、决定 Agent 的行为”上也无法达成一致。例如在 Mastra 或 LangGraph 中，你需要显式地定义 Agent 的工作流和轨迹；而在 CrewAI 中，Agent 则会自行做事，自己做决定去达成最终目标。

<details>
<summary>Original English</summary>
Also they differ in between the languages they are implemented in, mostly between Python and and TypeScript. And they also don't agree on who who's in charge of specifying what an agent does, agent behavior. For example, in Mastra or or LangGraph you explicitly define your agent workflows and trajectories, while for example in CrewAI agents do things on their own and they decide on their own to achieve the end goal.
</details>

### 代码执行环境与三种隔离层级

当像这样的公司——基本上在任何事情上都意见不合的公司——在某一件事上达成了共识，这大概就不仅是一种风潮，而是一种刚需了。那么它们为什么会在这件事上达成一致呢？正如我常说的，无论你用 AI Agent 做什么有用的事情，最终都会走到这样一个阶段：你的 Agent 需要执行某种代码，或者需要拥有 shell 访问权限。接下来的问题就是：这将在哪里发生？在什么样的执行环境中进行？

<details>
<summary>Original English</summary>
And yeah, when companies like or companies like this that don't agree on basically anything agree on something that probably isn't just a fashion, it's a necessity. So why why they agree do they agree on this thing? So as I like to say, whenever you're doing something with your AI agents that's useful, you eventually come up to the state where your agent agent needs to execute some kind of a code or needs to have shell access. And the next question is where where will this happen in which execution environment?
</details>

我认为在这些环境中基本上存在三种可能的隔离类型，现在让我们简要梳理一下：

**第一种**是最基础的，大概也是大家本地在开发 Agent 时所使用的那种。你会定义某种命令白名单；你还会收到一些审批提示，比如 Claude 会问你：“嘿，你确定要运行这个命令吗？”——虽然可能我们大多数人直接点“是”，连它说了什么都不看；此外你还可以添加一些拦截钩子（interception hooks）。

<details>
<summary>Original English</summary>
So I would say are basically three types of possible isolation in these environments, and let's now have a brief overview around these. So, number one is the most basic one, and it's probably the one you're using locally when development with your agent. So, you define certain allow list of commands. Uh you also get some approval prompts where you know Claude asks you, hey, are you sure you want to run this command? Although probably most of us just click yes and don't don't even read what does he say. And you can also add some interception hooks.
</details>

但这种做法的问题在我看来是很明显的。当你允许你的 Claude Agent 通过 `python -c` 运行 Python 命令时，它实际上可以打开任意套接字、修改文件系统、执行代码，或者基本上做任何事情——这很可能是你在后台没有想到的。你本质上只是定义了模型“应该”使用什么，却没有限制模型“实际可以”使用什么。如果模型被攻破了，我想大家都能感知到，你实际上是为它打开了后门，让它可以在你的本地设备上执行恶意命令。

<details>
<summary>Original English</summary>
But the problem at this approach is I would say the obvious. Uh so, when you allow your Claude agent to run Python command with Python uh dash C, he can literally open any sockets, uh modify a file system, execute code, or do basically everything uh which you probably don't think about in in in the background. And you essentially defined what your model should use, but you didn't define what your model can actually use. And if the model is compromised, you can, I guess, sense that you essentially opened backdoors for it to to, let's say, do malicious commands on your local device.
</details>

**第二种**更高级的选择，是把所有这些代码执行转移到像 V8 或 QuickJS 这样的嵌入式引擎运行时中。这种方法更好一些，因为你有了一定的网络和文件系统隔离。但这种方式的缺陷可能更加微妙。比方说，你的 Agent 拥有访问某些工具的权限，比如查询数据库或发送邮件；你的 Agent 可能会生成一个调用这些工具的 Python 脚本，而你把这个脚本放在嵌入式运行时里执行。但问题在于，你的 Agent 在该运行时内部调用的这些工具，实际上是在你这台设备上、在那个运行时之外跑的。所以从本质上讲，恶意 Agent 可以借由这些工具来行动——不是直接执行，而是通过这些工具——这大概是大多数人没有考虑到的。

<details>
<summary>Original English</summary>
Second most more advanced option is shifting all of this coding execution stuff inside embedded engine runtimes like V8 or QuickJS. And this approach is better because you have certain network and file system isolation. But the quirk with this approach is probably even more, you know, subtle because, let's say, your agent has access to certain tools like query database or send email. And your agent will probably generate a Python script which uses these tools, and you will execute this script inside this embedded runtime. But the problem is that these tools that your agent will call inside that runtime will actually run on your device outside that runtime. So basically your maliciously malicious agent can act through these tools, not directly but through these tools, which most of people like probably don't think about.
</details>

正如所说的那样，你隔离的只是 Agent 生成的胶水代码，但并没有真正隔离实际的工具调用。比如 Agent 可以利用发邮件工具或数据库查询工具来执行它的某些恶意命令；再比如如果你有一个删除数据库的工具，你可以体会到用这种方法会带来怎样的麻烦。

<details>
<summary>Original English</summary>
And as it says it you isolate the glue code that your agent generates but you're not actually isolating the actual tool tool calls. So for example, agent can use these email sending tool or database query tools to perform some of its malicious commands. For example, also if you had delete database tool you you can sense how can you get into problems with this approach.
</details>

**第三种**也是推荐的做法，就是为此类用途使用一台独立的计算机或虚拟机（VM）。你通过 API 与这个虚拟机交互，控制它的生命周期，或者在里面执行任何操作；并且这个虚拟机绝不会触及或干扰你的本地基础设施、网络、文件系统等。这种方法最棒的地方——也是为什么它是最佳方法的原因——就包含在最后一句话中：**应用环境被攻破并不等同于应用本身被攻破**。

<details>
<summary>Original English</summary>
And the third one and recommended approach is to use a separate computer or VM for these kind of purposes. And yeah, you interact with this VM via API, control its life cycle or do any kind of stuff inside it. And this VM never touches or interferes with your local infrastructure, network, file system, etc. And the best part of this approach and why is it the best approach is contained in this last sentence compromise the app is not compromise the app is not a compromise app.
</details>

我这么说的意思是：在前两种方法中，一旦你的工具调用失控，或者你的 Agent 通过你批准的 Python 命令失控，那么这一步被攻破就实打实地意味着你的整个应用被攻破了，可能会造成极大的危害。但在这一步中，你可以在沙箱里运行全世界最糟糕的代码，它也不会干扰你的应用逻辑；你直接丢弃那个沙箱，重新启动一个新的就行。

<details>
<summary>Original English</summary>
What do I mean by that is because in prior two approaches when your tool calls misbehave or you your agent misbehaves through let's say Python command you approved that compromise step is is literally compromising your whole application and can you know make really bad stuff. But in this step you can run the most the worst code on the planet inside a sandbox and it can't interfere with your application logic. You can just throw out that sandbox and spin up another one.
</details>

### 行业演进趋势与沙箱使用形态的变化

为了证明我不是在这信口开河，这里有证据展示了 AI 框架正在迈进的方向：
- 在 2026 年 4 月，CrewAI 移除了本应在你设备本地执行代码的 `code interpreter` 工具，目前它们指向了专用的沙箱服务。
- AG2 也废弃了旧的本地代码执行器，现在引入了全新的 `sandbox code tool` 类，显式要求你定义想要在何种环境中去使用它。
- Cloud Agent SDK 默认就使用沙箱，不过那是一种特殊的沙箱，更偏向于进程级别的沙箱隔离，比如你在 Linux 机器上借助 Bubblewrap 这类工具实现的方式。
- OpenAI 的 Agents SDK 拥有支持一些沙箱提供商的原生沙箱 Agent，同时也支持 Docker，不过它也允许你在知晓其明确列出的缺陷的前提下进行本地代码执行；Mastra 的情况与之类似。

大家可以注意到，它们并不是在增加沙箱支持——它们原本就支持沙箱——它们正在做的是**删掉所有替代方案**。

<details>
<summary>Original English</summary>
And to back up this that I'm not just talking you know some nonsense here's the proof like the direction of frameworks the direction that AI frameworks are moving at. So in April 2026, Crew AI removed the code interpreter tool, which essentially did uh local code execution on your device. And they now point to dedicated sandbox services. AG 2 also retired their old local coding executors and now have this new sandbox code tool class [snorts] that explicitly requires from you to define the environment where you want to use this. Cloud agent SDK is by default using sandbox, but it is special only sandbox. What do I mean by that? It's like a process level sandboxing which you can do for example with tools like bubble wrap on Linux machines. Open AI agents SDK has this sandbox agent which has native you know support for some of the sandbox provider integrated inside and also for Docker, but it also allows you local code execution with you know transparently listed flaws of this approach and it's similar to with Mastra. And you can notice that they are not adding sandboxes. They already had them, but they are deleting all the alternatives.
</details>

在 AI Agent 框架向绝对隔离方向演进的同时，这些沙箱的实际使用形态也在发生转变。起初，当最初的 Agent 刚开始演化并进入视野时，沙箱大多被用作短生命周期的机器：你的 Agent 按需拉起它，在里面运行一些代码或任务，然后就关掉它。但后来随着模型能力变得更强，人们意识到完全可以把整个 Agent 迁入沙箱，将其作为执行运行时直接在沙箱内部跑起来，并赋予它访问文件系统、网络调用等几乎一切权限。

<details>
<summary>Original English</summary>
And parallelly with this shifts in AI agents frameworks direct isolation direction basically there also happen a shift between how these sandboxes are actually used. So firstly when first agent started to you know evolve and got into picture the sandboxes were mostly used as short-lived machines where your agent was would spin it up on demand, run some code or task inside it and shut it down. But then when the models became more capable, the people realized they could literally shift hold the agent and run it inside the sandbox as the execution runtime and give it access to file system, network calls and basically everything.
</details>

而到了最近，又有了一种新的转变：人们意识到如果能够并发运行成千上万个这样的执行环境，就可以做很多非常有趣的事情，特别是在强化学习、微调、后训练、基准测试方面；你还可以在解决某些问题时为它们衍生出不同的子 Agent，诸如此类。

<details>
<summary>Original English</summary>
And since recently there's also a shift where people also like understood that if they can run thousands of these execution environments concurrently, they can do really interesting stuff, especially regarding reinforcement learning, fine tuning, post training, benchmarks, you can also spawn different sub agents for while solving some problems and stuff like that.
</details>

### 可替换项与架构不可逆项：重新审视“选哪个框架”

现在回到最开始的问题。AI 框架在执行环境和边界上的这一整套演进，让我重新思考起那个我和大家可能经常被问到的常见问题：“我到底该选哪个框架？”基于刚才这整个故事，我认为这在本质上问错了问题。

<details>
<summary>Original English</summary>
And yeah, now back to the to the question. So this whole shift from AI frameworks regarding execution environments and boundary made me also rethink the common question which me myself and I probably a lot of you are asked like which framework should I pick? And based on the this whole story, I think this is essentially the wrong question.
</details>

我为什么这么说？因为大家在框架之间对比的大多数特性，其实都是**可替换的**，而且换起来相当容易。而那些没那么容易替换的东西，大家在选择开发技术栈之前，通常甚至都不会纳入考量。

我说的“可替换”具体是指什么？
- **框架本身是可替换的**：如果多个框架使用相同的语言，你基本上可以互相切换。你只需把重构任务交给编码 Agent，开发者平时一直在干这种事。
- **模型和提示词是可替换的**：虽然针对特定模型微调过系统提示词等情况切换起来会棘手一点，但这只需进行一些微调和回归测试，完全是可以做到的。
- **缺失的特性是可替换的**：有时候大家会基于某个框架有、另一个框架没有的功能来选框架。但如今你完全可以靠氛围编码（vibe code）把缺失的功能手搓出来，或者给框架挂一个外部插件就行。

在我看来，大概唯独名为“持久化执行（durable execution）”的功能不太一样——这在部分框架里有提供。这个功能由于会牵扯到底层架构等因素，没那么容易在一下午时间靠 Claude 氛围编码就能复现出来。但其他东西，比如我刚才提到的评测（Evals）、链路追踪（tracing）、记忆（memory），你都可以轻松自己实现，或者直接外挂一个现成工具。

你也可以更换沙箱提供商，因为我们所有沙箱服务讲的都是同一种语言：创建、在内部跑点东西、然后删除——尽管各个提供商在特性和性能表现上有所不同。

<details>
<summary>Original English</summary>
Why do I say that? That's because some of most of the items that you compare frameworks between are swappable and you know, can be easily done. And stuff that's not that easily swappable is normally or often not even considering to the picture between before choosing you know, development stack. So what do I mean by swappable? For example, you can essentially swap between if your multiple frameworks use same language, you can essentially swap between frameworks with you know, you give your coding agent a task and it's like a refactor and developers do it all the time. Second one is you can also swap between models and prompts. This can be a bit more trickier if you're you know, fine tuned to you fine tune your system prompts and stuff to certain model, but it requires some fine tuning and regression testing and it's I mean completely doable. Same with missing features. So sometimes people decide on which framework to choose based on some features that one framework has, another doesn't. But nowadays, yeah, you can essentially vibe code missing feature or just plug it as an external plugin for certain framework. I would say this probably doesn't only count for the feature called durable execution which some frameworks provide. That's kind of not that easy to you know replicate and vibe code in an afternoon with cloud because it affects the architecture and stuff, but all of the others like I mentioned here Evals tracing a memory you can easily you know implement by yourself or just plug in an external tool. And you can also swap the SAMOX provider because all of us speak the same language so all of us speak, create, run some stuff inside and delete. Although I mean some of us have distinct features and different performances.
</details>

而你**无法轻易更改或后期替换**的，正是这里我想提的执行隔离策略。也就是决定你的代码到底是在本地运行，还是使用外部沙箱。

为什么这个难以随意替换？原因在于它决定了你的整个系统架构，以及你如何去开发系统的其余部分。比如在开发某种工具时，如果你设想采用第一种方案、所有东西都在本地跑，那你写的所有工具都会调用宿主机或应用进程环境，不加隔离地使用本地文件系统等等。

问题在于大多数人在概念验证（POC）阶段都是从这种做法起步的，但不幸的是一路沿用到了生产环境，并且再也没有回头去重构它。等到坏事发生时，往往为时已晚；而在某些时候，我所说的“坏事”很可能是足以彻底摧毁你产品的严重灾难。

<details>
<summary>Original English</summary>
And the stuff you can't change easily or swap later is the execution partial I would mention in here. So that's like deciding will you run your ex coding stuff locally or will you use external sandbox. Why you can swap this easily? Well the reason is that this defines your whole arc system architecture and how do you develop other parts of your system. For example when you're developing some kind of a tools if you're guessing that you will use first approach where everything runs locally then you write all of your tools to use your host or app process environments using your file system without separation and stuff like that. And problem is that most of the people start with this approach as a POC phase but unfortunately continue all up until the production stuff and they don't come back to it and then when well bad stuff happens it's probably too late and some of the times by bad stuff I mean something that can literally kill your product.
</details>

因此，我希望通过这次演讲传达的是：大家在决定选择哪款框架之前，或许应当优先考虑选择最佳的执行边界。正如我最后想让在座各位从这场演讲中记住的那样：框架各执己见，而执行边界……

>> 在座各位从这场……

<details>
<summary>Original English</summary>
And that's why I would like to say from this talk that you should probably consider picking up the execution choosing the best execution boundary before deciding which framework you should pick. And as I as I like to say it then send that side would maybe like for you all of here to remember out of this talk is frameworks are opinions and the boundaries

>> all of here to remember out of this
</details>