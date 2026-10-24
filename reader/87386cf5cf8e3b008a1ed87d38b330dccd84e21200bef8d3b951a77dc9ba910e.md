---
author: AI Engineer
date: '2026-10-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=adfw3xJBx1o
speaker: AI Engineer
tags:
  - ai-agent
  - coding-agent
  - model-context-protocol
  - platform-engineering
  - software-architecture
title: Monzo 自研编码智能体 Agent Chip：小倍增器如何复利撬动银行级工程生产力
summary: 数字银行 Monzo 的工程师 Felipe Felisola Caso 与 Francesco Galletta 分享了自研内部 AI 编码智能体 Agent Chip 的实践经验。Monzo 拥有超过 3000 个微服务和复杂合规环境，团队通过搭建 MCP 网关与容器沙箱编排系统，将智能体深度集成至 Slack、GitHub 和 Linear 中。Agent Chip 如今贡献了全行超 10% 的合并 PR，每天执行逾 1800 项任务，并被广泛用于事故调查、跨组咨询与数据异动前置监控，大幅降低了非技术人员参与工程系统的门槛。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Monzo
  - Anthropic
products_models:
  - Agent Chip
  - Slack
  - Linear
  - GitHub
media_books: []
status: evergreen
---
### 数字银行的工程规模与痛点

**Felipe / Francesco**: 呃，我们是……哇，刚才声音有点大。呃，我们是 **Felipe Felisola Caso** 和 **Francesco Galletta**。今天我们来到这里，是想和大家聊聊利用大语言模型（LLMs）为 **Monzo** 构建内部自研智能体所带来的复合价值。

首先，什么是 Monzo？我们是一家银行——一家致力于让金钱为每个人更好服务的数字银行。

为了让大家对我们为什么需要编码智能体以及所面临的问题规模有个清晰概念：在 Monzo，我们的工程团队维护着超过 **3000 个后端服务**、大约 **13000 个数据仓库模型**，以及数十个机器学习（ML）预测模型。

因此，我们处理的业务极其繁杂且关键，比如信贷决策评估、金融犯罪防范与侦测，以及覆盖移动客户端 App、后端架构和数据管道等极其复杂的各类业务用例。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: Uh, we are Well, that was loud. Uh, we are Felipe and Francesco. Uh, we come to talk to you about the compound value of building Monzo sync house agents using LLMs. Um, so what is Monzo? We are a bank. Digital bank trying to make money work for everyone.

Uh, to give you a size of the problem for coding agents, uh, we have our teams of engineers maintaining over 3,000 back-end services, around 13,000 um, data warehouse models, and dozens and dozens of ML uh, predictors. So, we do all sorts of things like deciding on credit, deciding on financial crime, and doing very complex use cases both for the app, the back-end, and data.
</details>

**Felipe / Francesco**: 我想大家直到今天，甚至在走出这个大会会场之外，肯定已经听过无数关于各家科技公司引入 AI 编码智能体的成功案例了。

事实上，就在几周前，纽约这里刚开过一场行业大会，会后流传出一篇专门探讨 2026 年科技行业发展现状的深度文章。推特（X）上当时出现了一句半开玩笑的流行语：“如果你现在还没在自研自己的 AI 编码套件与执行框架，你还能算是一家严肃认真的硬核科技公司吗？”

这确实引人深思，对吧？

接着在 2026 年 1 月，Monzo 内部的一个 **Slack** 频道突然爆火出圈了。这个频道的名字就叫作 **Agent Chip**。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: Um So, I'm pretty sure by even by today, but outside of the conference, you have heard a lot of uh, success cases of companies adopting AI agents for coding. Uh, in fact, uh, there was a conference a couple of weeks ago here in New York, and this article came out talking about the state the state of the tech industry in 2026. Uh, and there is this hopefully jokingly quote from X saying that if you're not building your own AI coding harness, are you even a serious tech company? So, some food for thought, right? Uh, then inside of Monzo in January 2026, this a Slack channel went viral. Agent chip.
</details>

### Agent Chip 的诞生与工作流集成

**Felipe / Francesco**: 希望我能……哎呀，怎么回事？幻灯片翻不过去了，好吧，没事了。

希望大家能留意到屏幕上这个小小的 Emoji 表情符号，非常可爱，我们全公司都特别喜欢它。这个小工具在公司内部迅速风靡开来，原因非常纯粹且直接：在 Slack 里，你只要给任何一条消息回复并添加这个小小的 Emoji 表情反应，系统就会直接捕获这条消息作为 Prompt 提示词，并立即唤醒智能体开始工作。

随着这种交互方式的普及，我们决定加大投入持续深耕。最终，它演变成了全天候随时待命、无缝嵌入我们 Slack 办公体系及整个研发基础架构中的“虚拟队友”。

举几个日常例子来说，它的使用体验就像是一位真实的同事。它就静静待在那里，你随时可以在 Slack 中 `@Agent Chip`，让它为你执行任务：回答一个棘手的工程问题、调查并梳理某块系统架构的前因后果，甚至是直接找它闲聊两句——不过我感觉它似乎并没有那么热衷于闲聊。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: And hopefully I can Oh, no, what happened? You cannot do this. It's all right. So, hopefully I can bring your attention to this little emoji here. Really cute. We love it. Uh, this became really, really viral inside of the company for a really good reason. You can give it uh, any prompt directly by just reacting with the little emoji to the message and it will pick it up as a, you know, prompt.

Uh, so that evolved, we double down, and that became an always available teammate inside our Slack and whole environment. Uh, to give you a few examples, it does feel like a coworker. Uh, it's just there. You can always at Agent Chip and get it to do something for you, answer a question, find out something about some architecture, or just have a chat with you, but I don't I don't think he likes it so much.
</details>

**Felipe / Francesco**: 此外，它还能承担**代码审查（Code Review）**工作。就像某些经验极为老到的资深资深工程师那样，它会快速过一遍改动，直接给你留下一句“在我看来没问题（Looks good to me / LGTM）”，然后你就可以开开心心继续推进了。

同时，你还可以直接在项目管理工具 **Linear** 中给它指派任务工单。你只需要把 Ticket 分配给它，它就会主动领走任务并深入代码库开始动手干活。

这一切带来的实际效果非常亮眼：截至今天，在 Monzo 的整个技术体系中（涵盖数据工程、机器学习、后端架构、App 端等所有技术条线），**Agent Chip 独立提交并合并的 Pull Request（PR）已经占到了全行合并总量的 10% 以上**。

不仅如此，它每天稳定执行的后台任务超过了 **1800 项**——这绝对是一个非常惊人的运行量。

更重要的是，它现在正逐渐被技术团队之外的**业务线人员**积极采用。它不再仅仅局限于写代码和做纯技术工程，还能帮业务方解答业务逻辑疑问、撰写 SQL 分析查询，或者以自助化服务的方式满足业务人员日常提出的各类技术诉求。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: Uh, it can also do code reviews. So, like a very senior, uh, engineer, you will just tell you it looks good to me and go on your merry way. And you can also assign, uh, linear tasks, as well. So, you can give it tickets and it will just get into it.

Um, so all of this is good and well. Uh, forward into today, Agent Chip authors over 10% of all merge PRs across tech, so that's data, uh, machine learning, that's, uh, back in engineering, app, etc. Also runs more than 1,800, uh, tasks per day, which is a lot. Um, and it's being actively, uh, starting to be adopted by business users as well. So, it's not just coding and tech, it's also trying to answer business questions, writing queries, or self-serving anything that a business user may need.
</details>

### 自研的秘诀：平台底座与微乘数效应

**Felipe / Francesco**: 话说回来，既然大家已经听过了太多关于各家公司落地 AI 编码智能体的故事，那这有什么好稀奇的？我们今天站在这里究竟想分享什么？难道我们只是想站在这炫耀说：“早在 **Anthropic** 正式发布相关功能的前 6 个月，Monzo 就已经搞出了 Claude Tag 类似的东西”吗？

虽然事实确实如此，但这根本不是今天演讲的重点。

我们真正想向大家毫无保留分享的“独家秘诀”，是究竟什么让 Agent Chip 成为了一个如此成功的产品。答案表面上是 LLM，但在我们这里的语境中，**LLM 代表的是“大量细微乘数的复合累加”（Lots of Little Multipliers）**。

我们坚信，之所以能以极高的迭代速度打造出 Agent Chip 并让其产生不可替代的巨大业务价值，核心根基在于 Monzo 多年来沉淀下来的极其强大的**内部工程平台底座**。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: So, again, you've heard many success stories about companies adopting AI coding agents, but so what? Why are we What are we trying to share today? Are we saying that we want to brag that we built Claude Tag 6 months before Anthropic released it? We could be. That's not the focus of today's talk.

Um, we want to share the secret sauce of what makes Agent Ship a successful product and it's LLMs. But actually LLMs in this case stands for lots of little multipliers. We believe that what enabled us to build Agent Ship so quickly and so invaluable way is a very strong platform at Monzo.
</details>

**Felipe / Francesco**: 当我们前面提到“一个 Slack 频道爆火，输入一段提示词、点个表情反应就能轻松收获成效”时，这种体验并非凭空发生，其背后其实是由我们平台早前就已完备的大量基础设施能力在托底支撑：

完备的报警与监控体系、与前面提到的各种第三方工具的成熟集成、能够让我们安全快速开展验证的 **Staging 预发布测试环境**、标准化的队列抽象层、便捷的自动化部署机制、数据库访问抽象层，以及其他许许多多我在此无法一一列举的工程能力。

所以归根结底，首先也是最重要的：正是 Monzo 平台工程原先拥有的技术积淀，赋予了 Agent Chip 取得成功的土壤。

但我们的探索并没有就此止步。实际上，甚至在 Agent Chip 这种全托管的远程常驻智能体诞生之前，我们就已经开始大力投资在本地开发环境中支持 AI 编码智能体了。

我们当时迈出的第一步关键举措，就是基于 **MCP（Model Context Protocol）** 构建了一套集中式的 MCP 网关（MCP Gateway）。该网关使智能体能够便捷安全地访问内部知识源集合、内部工具生态，以及前面 Francesco 所提到的 Monzo 庞大微服务网络中的各项能力。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: So when we say that this went viral and you could write a prompt, react, and profit. Actually this comes from a number of capabilities we already had. So alerting, monitoring, integrations with third parties such as the ones Francesco mentioned, a staging environment that allows us to test easily, queuing abstractions, easy deployment, database abstractions, and a number of other things I could be mentioning here. So first and foremost what we have in our platform is what allowed Agent Ship to be successful.

But this does not stop there. We saw even before Agent Ship as a remote agent existed, we started to invest in supporting AI coding agents even in local environments. So the one of the first things we did was develop an MCP gateway that allowed easy access to a set of knowledge sources and internal tools and some of the services that Francesco mentioned.
</details>

### MCP 网关与容器沙箱编排架构

**Felipe / Francesco**: 这幅图大致展示了我们的架构拓扑。最底层是我们希望接入的各种内部业务服务与企业知识库。

我们将这些异构系统统一收敛在我们自主研发的 **MCP Server** 之后。通过这一层，我们能够建立确定性的行为准则，自主决定并精细控制究竟有哪些内部接口与数据能够暴露给智能体调用。与此同时，MCP 网关还统管了不同智能体接入时的**身份认证（Authentication）与权限鉴权（Authorization）**。

再次重申，这项工作最初源于本地开发者在本地环境中使用编码智能体时对统一上下文与工具调用的迫切需求。正如大家在本次大会的许多分论坛中反复听到的那样：**在保障绝对安全的前提下，我们能够投喂给智能体的上下文信息与业务数据越多、越精准，智能体所展现出来的推理与执行效果就越好**。

在 MCP 网关之上，我们紧接着构建了**智能体编排调度系统（Agent Orchestration System）**。这正是 Agent Chip 在幕后的核心引擎，它让智能体得以在完全受限隔离的沙箱（Sandbox）内安全执行，并受到严格的工具访问白名单与权限策略约束。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: So this is roughly how the architecture looks like. We have the things we want to connect as the internal services and knowledge sources. And we put that behind the MCP server that we built to get the deterministic behavior choosing what are the things we want to expose to the agents and then we manage also authorization, authentication for the number of different agents. Again, this started in the world of local coding agents that wanted to connect and by by now probably everyone has heard in multiple sessions that the more context and the more data we are able to give safely to our agents the better.

After that, we built the agent orchestration system, which is exactly what powers Agent Ship behind the scenes and makes it work in a sandbox and with very strict tools and permissions.
</details>

**Felipe / Francesco**: 如果我们回到这张架构拓扑图，整套 MCP Server 体系在逻辑上被收敛封装为一个独立的模块，并在这里与 Agent Chip 的其余核心架构紧密咬合：

我们在隔离的命名空间（Namespace）中启动并运行远程智能体，让其常驻在**独立的容器沙箱**内部。编排系统负责按需触发任务、调度执行并从容器中实时读取与回传各种运行态信息。

这样设计的核心考量——其实业界很多主流 AI 提供商与顶尖实验室也在不断呼吁强调——在于**必须将不受信任的智能体执行环境与生产核心基础设施进行严格的物理与逻辑隔离**。

不要忘记，我们是一家银行，时刻处于极度严苛的**金融强监管合规环境**中，因此我们必须死死守住安全底线，确保智能体输出带来的不确定性与非确定性始终处于绝对可控的状态；但与此同时，我们又必须为智能体提供一个能够自主自由调度、灵活调试与编写代码的宽松沙箱。

如果我们把这个架构进一步拆解透视，来看一看底层更深层次的运转细节：

在独立的隔离命名空间中，系统会根据负载动态拉起多个 Pod 实例，每个 Pod 就是一个供智能体专属运行的独立 Sandbox 沙箱。

通过制作标准化的 **Agent Image（智能体镜像）**，我们在镜像层严密界定了智能体所能直接访问的环境依赖与具体工具集，包括运行环境、CLI 命令行工具，以及直接借由网关下发的鉴权认证凭证。

底层的 **Proxy 代理组件**则是智能体安全连通外界通信的唯一出口。Agent Chip 正是通过这层受限代理才能合法连接到我们的内部 Git 代码仓库并拉取或提交代码变更。

当然，所有对外出口网络流量（Egress）全部遵循严苛的白名单机制，只有经过我们显式审批与授权的目标地址才允许连接。通过这种设计，我们能以极其可控且审慎的方式，把控智能体所能窥探和交互的每一个网络端点。

最后，屏幕中间那个蓝绿相间的嵌套方块，就是智能体内核实际运行的地方。

可以说，正是这个“方盒子里的方盒子里的方盒子”，包容了所有大模型非确定性行为的发生，使智能体得以在其中尽情开展各项复杂的工具调用与逻辑探索。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: So, if we go back to our diagram, the whole architecture for the MCP server basically condenses into this box and this is where we connect the rest of the Agent Ship architecture. So, we have remote agents running inside a sandbox in an isolated namespace and then the orchestration system triggers and then reads and gets this information from from that. The main idea here is and again, this is coming across in a multiple of multiple providers and labs and so on is that we want to separate this from the rest of our infrastructure in production. Again, we are a bank, we live in a regulated environment, so we want to make sure that the non-determinism from the agents is controlled. But at the same time, we want to have an environment where we can let it run loose and develop.

And again, if we explode this to give you a bit more under the hood visibility of what is going on. So, in this isolated namespace, multiple pods come up with sandboxes that the agents are running on. The agent image is where we define the exact tools the agents will have as as access. So, things like the environment, the CLIs and the authentication and the authorization that again, we get from the gateway itself.

The proxy is what allows us to connect to both the exterior world. So, that's how for instance Agent Chip is able to connect to our code, to our repositories, and work with that. Um but, of course, we only get the egress that we choose to do choose to give it. Um so, that is how we make sure that it's very controlled and deliberately giving access to the things we want it to be able to see. And finally, the little uh blue-green box there is where the agent itself is running. So, that box inside the box inside the box is where the nondeterminism happens, and it's where the agent can perform everything that it wants.
</details>

### 从工程基建到复合业务价值的释放

**Felipe / Francesco**: 当 MCP 服务器能够安全地为智能体开放所有关心的内部能力，同时将我们的业务数据以绝对安全合规的方式接入，并由智能体编排调度系统在外部统一兜底时，整个端到端的架构链路就完整闭环了。

一旦有了这些强大的标准化底层积木，后续长出来的各种全新业务用例，其搭建难度就会大大降低：

正如 Francesco 前面介绍的，我们可以极快地将这套底座接入 Slack，随后接入 GitHub，再接入 Linear；紧接着，我在这里用另一种不同颜色所标记的，就是 Monzo 内部那 **3000 多个现存微服务**——它们都可以被当作现成积木迅速挂载到这一套体系之上。

这种架构复利与我们最初打造 Agent Chip 时的逻辑如出一辙：过去，是公司现存平台底座中的多项基础设施赋能了我们，让我们能极速构建出 Agent Chip 并提取业务价值；而现在，**Agent Chip 自身也晋升为了 Monzo 的底层积木之一**，银行内部的其他业务与工程部门也可以反过来基于它迅速搭建出更多全新的应用场景。

这种积木式的能力复用，不仅让我们在公司内部迅速推出了更多的前沿产品功能，更为银行催生出了实打实、可量化的核心业务成果。

首先，我们观察到工程师所能处理的任务广度与吞吐量发生了爆发式增长。这完全符合预期，因为工程师们再也不需要整天死死“盯梢陪护”自己的智能体了。他们既可以在本地借助编程辅助工具解决局部具体问题，同时也能随手将耗时的大任务直接全权托管给云端沙箱中的远程智能体并发跑起来。

我们大幅实现了常规运维与研发流程的自动化，这让工程师能够将宝贵的注意力真正释放出来，聚焦于那些最具商业价值、且充斥着复杂业务模糊性的高难度核心挑战上。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: So, this is how the whole diagram looks like when we are able to give our MCP server access to everything that we care about for the agent, we are able to safely give it access to our data, and the agent orchestration system handles everything that's around it. With these as building blocks, any use cases that come after it are much, much easier to be built on top of. So, as Francesco mentioned, this we can connect Slack to, and then we can connect GitHub, and then we connect Linear, and then I just use a different color to show this is the more than 3,000 services that we can be connecting to to this as a building block.

So, in the same fashion that we had multiple things in our platform that enabled us to build Agent Chip and get value out of it. Now that Agent Chip is also a building block, the multiple parts of our bank can also leverage it to create other use cases. So, we start to see this building blocks enabled us to not only get more um product features internally, but to drive concrete business outcomes.

Um we observed a higher breadth and volume of tasks that engineers are able to run, as you you expect, because then we don't need people to be babysitting their agents all the time. They can use their coding assistant for um specific tasks, but they can also delegate to remote agents. We can automate routine processes much better. So, that allows humans to focus on the higher value problems where the ambiguity lies particularly.
</details>

**Felipe / Francesco**: 这里可以给大家看几个我们正在落地的具体应用案例：

第一个场景是 **Agent Chip 的线上故障应急模式（Incident Mode）**。在这个模式下，它能充分调动 MCP 接口提取高价值的关键排障数据。

其工作原理是：每当线上系统监测到故障并触发新的事故报警时，Agent Chip 会第一时间自动加入对应的应急响应 Slack 频道。它能自动启动溯源排查，解析服务日志、梳理分布式调用链路（Traces）、直连出现异常的特定微服务实例，并深入比对源代码变更以查明故障根源，从而为现场排障的人类工程师提供极高信噪比的关键排障信息。

在突发线上事故的紧急关头，我们最忌讳的是让 AI 喋喋不休地输出大堆无关废话或盲目测试假说；我们对它的严苛要求是必须保持**极高的有效信息密度（High Signal）**。同时，我们也给予了现场值班人员完全的控制权，人类可以随时调整并明确设定 Agent Chip 在当次排障中的介入深度与辅助边界。

除了应急排障，我们还在 Slack 的**跨组咨询答疑频道（Ask Channels）**中常态化使用它。在 Monzo 内部，这主要用于处理不同业务小队（Squad）之间的协同与跨团队答疑。

比如，某个小队在开发新业务时需要了解另一个关联后端服务的调用约束、某个产品的技术演进历史或是未来的架构规划，Agent Chip 凭借其与内部全量知识库的互通能力，能够第一时间生成一份高完成度的草拟解答，交给现场的介入人类（Human-in-the-Loop）作为参考。

有时候，智能体草拟的这套解答已经足够详尽精准，直接就能独立闭环并解决提问团队的工单需求；而如果遇到信息缺失或歧义，智能体也能在草稿中主动指出需要补充哪些背景信息，此时负责值班的人类工程师只需介入补全关键上下文即可。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: Some examples of these that we are able to do. Um this is Agent Chip working in incident mode and leveraging the MCP to get very relevant data. So, what happens here is whenever we identify and trigger a new incident, Agent Chip joins the channel and is able to start an investigation, understanding logs, understanding traces, being able to connect to that exact service, and of course, the code itself to see what's going on and to help the human with a very high signal. We don't want the agent to be saying a lot of things during an incident and testing hypotheses like we want it to maintain high signal, and we give the humans also control of how much Agent Chip will be able to support there.

We can continue to use it on Slack, but not only by triggering it by mentioning it, uh but also in what we call ask channels. It's basically squad-to-squad interaction inside Mondzo. A squad needs to have some context on a back-end service, on a product development, on the road map, and Agent Chip can also, since it can connect to our knowledge sources, it's able to draft a response for the human in the loop to get as reference and support there. Maybe the response will be enough, and Agent Chip can just solve that ask ticket by itself. Sometimes it will ask for more context, and the human in the loop can be tagged um and come in to support more.
</details>

### 从被动响应到主动预防：全员赋能的新常态

**Felipe / Francesco**: 另外一个我们近期刚刚落地、并已经创造了极其可观业务价值的场景，是**数据质量告警的分流排查以及后端变更潜在影响的前置阻断**。

我们将其命名为 **Agent Chip on Call（智能值班）**。当底层数据处理出现异常或计算报错时，它能第一时间自动感知失败并触发故障复盘与溯源分析。

不过，这还仅仅停留在“事后被动响应”的范畴。

我们紧接着反思：**为什么一定要等线上数据已经跑错污染了才去救火？我们能不能让错误在一开始就根本不要发生？**

基于这套底座，我们顺理成章地开发出了“主动预防版”功能。它能够持续追踪监控所有后端的 PR 改动，甚至在次日凌晨的批处理任务开始执行之前，就能主动识别并精准预测这些后端代码逻辑变更可能会给下游数据管道带来哪些潜在的破坏性影响。

上述这些都是我们技术工程团队日常深度依赖的典型场景。

但更为深远、甚至更让我们感到欣喜的现象在于：**它显著拉低了公司内部非技术专家向核心系统贡献代码的准入门槛**。

借助 Slack 上触手可及的轻量级交互入口，业务线人员或非专业工程师在日常收到产品反馈、碰撞出业务新点子或是开完讨论会后，能够直接呼叫 Agent Chip；智能体会直接生成一份真正可用、且已经在 Staging 环境中自动化测试验证通过的代码实现草案。

直到这个时候，业务人员才会把全套成果递交给专业工程师进行最终的代码审查，并正式走标准的流程发布部署上线。

这意味着，我们在 Monzo 所坚持的严苛软件工程规范与高质量交付标准没有发生丝毫妥协和降级，但它却实打实地让大量非技术专职人员得以深度参与到技术迭代之中，与工程团队更加紧密地并肩协作。

<details>
<summary>Original English</summary>

**Felipe / Francesco**: Um something that we're doing very recently that's been uh creating a lot of value is also triaging data quality alerts and checking for back-end changes that can create problems. So, basically we call it Agent Chip on Call and it observes the failures that we have and triggers an investigation automatically.

This is the reactive version of it. But, what if the errors never happened in the first place? We created based on this the proactive version that monitors back-end changes and identifies which are the potential outcomes that that can have for our data even before the data is processed in the next batch execution.

So, again, all of these are examples of how our technology team is using it, but even better than that, we've observed a lower barrier for non-specialists in the company to contribute to our systems. With a very quick entry point for Agent Chip on Slack, non-specialists can, based on product feedback, based on ideas, based on discussions they are having, just call Agent Chip, get a draft that works, that is already tested in staging, and then, and only then, involve an engineer to make sure we get the changes reviewed and deployed properly. So, this doesn't change the rigor to which we develop software at Monzo, but this does allow a number of non-specialists to also start contributing more closely to the team.
</details>

### 面向未来的演进：模型无关与端到端交付

**Felipe / Francesco**: 看到这里，大家可能会心存疑虑：当前整个 AI 市场的发展迭代可谓日新月异，在座的各位在此次峰会内外也随时都能听到来自各家前沿公司推出的激动人心的新突破、新产品与新特性。

那么，究竟凭什么能让我们坚信，Agent Chip 在如今的 2026 年以及更长远的未来，仍然能保持不可替代的核心价值？

正如我刚才强调且希望反复重申的一点：**Agent Chip 具有高度的可组合性（Composable）**。在 Monzo 的平台架构中，它本身已经凝练成为了一块标准化、可复用的新积木。

基于此，只要未来 Monzo 涌现出任何全新的 Agentic 智能体业务设想，我们都能以极快的速度完成孵化构建；我们既能完全满足银行最严苛的信息安全合规要求，又能同时完美兼容现有的所有后端基建与平台技术栈。

另外极其关键的一点是：**我们的底层平台在设计之初就贯彻了绝对的“模型提供商无关（Provider Agnostic）”原则**。

回到前面的架构图，大家在沙箱 Pod 中看到的那个蓝绿色的智能体方块，在物理实现上可以极其轻量地热拔插替换为市面上的任何大语言模型。我们能够根据具体的任务类型、成本考量与延迟要求，动态智能调度并选择最适合解决特定任务的模型。

我们从底层就拒绝与任何单一供应商进行深度绑定，这种架构解耦给予了我们无与伦比的技术敏捷度与灵活度，让我们能够随时拥抱整个行业中最契合 Monzo 实际需求的模型能力。

最后，我们仍在持续推进并覆盖更加宽广的**端到端全链路软件研发周期**。

退一步说，即便我们今天彻底停止针对 Agent Chip 的全部后续功能研发，它现有的形态也已经为公司创造了极高的价值。但我们正在向更庞大的研发纵深迈进：

不仅是在后端工程中生成补丁草案，还能同步覆盖客户端 App 代码的修改与调试；它能在专属预发布测试环境中自主跑通全量改动并完成验证，能闭环覆盖复杂的数据模型测试，甚至未来在链路的另一端，还能直接自动联动调整前置的预测模型。

当远程常驻智能体真正具备了端到端闭环交付的能力时，我们对全行系统底层脉络的理解以及系统间的集成能力将跃升至一个全新的高度。

所以说，尽管外界的 AI 市场日新月异，这并不代表 Monzo 必须一条路走到黑、终生死守在现有的这套 Agent Chip 代码实现上不放。但正是上述这些深度的架构沉淀与实践，让我们无比确信：它已经扎扎实实地成为了我们当今内部核心工程平台底座中不可或缺的强劲支柱。

最后，我希望在座的各位今天能带走的核心启示是：**在考虑如何利用大模型赋能团队时，不要仅仅盯着狭义的“传统大语言模型（LLMs）”本身，而更要善用那些能为你的团队带来持续复利与杠杆效应的“大量微小乘数（Lots of Little Multipliers）”——唯有依托坚实的内部平台底座，才能将这些小乘数最终汇聚成撬动深远业务价值的澎湃动力**。

非常感谢大家！

<details>
<summary>Original English</summary>

**Felipe / Francesco**: You can be thinking now, the market is moving fast. We are hearing a lot of exciting developments and new products and new features coming from multiple companies here in the conference and otherwise. What makes us believe that Agent Chip continues to be a valuable thing at this point in 2026 and moving forward?

Um As I said and I like to to reiterate, Agent Chip being composable, it is now a new building block that we have in our platform. So, it very quickly enables new use cases for agentic implementation at Monzo. Now that we can connect it very safely with all our security requirements and all our back end and platform requirements at the same time.

Our platform is plat provider agnostic by definition. So, if we come back to the diagram, the little blue/green agent box there can be very easily swapped by any for any model. We can dynamically choose which model best fits the purposes that we have. So, we are not specifically tied to any provider by definition and that gives us flexibility to understand which ones will fit Monzo's needs the best.

Um and finally, we are continued to move to cover a bigger development window. So, if we even if we stop development today, this would already be valuable, but we can cover a much broader sense in terms of we draft changes in the back end, we draft changes in the app. We can test these changes in a staging environment, cover the data tests. Who knows? Maybe even predictors on the other side. So, when remote agents are able to do this end-to-end, we can understand and integrate our systems much better.

So again, the market is moving, doesn't mean that we are necessarily married to agent chip until until the end, but these and other aspects of it make us strongly believe that is it is a very strong part of our internal platform now. And the key takeaway that I want to I want to you all to take from is how can you benefit from LLMs, but not the traditional LLMs, but the lots of data multipliers that you and your team can use to leverage value. Thank you.
</details>