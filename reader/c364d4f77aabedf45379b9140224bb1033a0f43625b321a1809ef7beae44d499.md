---
author: AI Engineer
date: '2026-06-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4uFVSLgD2Q4
speaker: AI Engineer
tags:
  - agentic-loop
  - observability
  - sandboxing
  - state-management
title: 生产环境中的AI Agent：OpenGov如何构建与规模化OG Assist
summary: 本文详细介绍了OpenGov在生产环境中构建和规模化AI Agent系统（OG Assist）的实战经验。团队放弃了LangGraph，全面转向基于TypeScript Effect库的自研Agent循环，实现了高细粒度的并发控制、日志追踪和错误处理。同时，文章探讨了Google的A2A协议应用、隔离安全沙箱机制、长上下文滚动摘要管理，以及运行时的生成式UI设计，为企业级Agent的落地提供了系统化的技术参考。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenGov
  - Google
products_models:
  - OG Assist
  - Effect
  - LangGraph
media_books: []
status: evergreen
---
### 场景破局：OG Assist 的诞生与前端交互革命

在企业级服务领域，如何将 AI 智能体平滑地融入复杂的业务流是一个巨大的挑战。**OpenGov** 是一家致力于让政府更加高效和负责任的软件公司，其销售的**企业资源计划**（Enterprise Resource Planning: 组织关键业务流程的管理系统）软件涵盖了预算编制、采购、资产管理和许可审批等极其细分的模块。为了提升用户在复杂系统中的操作效率，团队推出了 **OG Assist**。

OG Assist 表现为嵌入在所有产品顶部导航栏中的一个全局按钮。所有的底层产品套件和产品团队都围绕这个按钮构建了相应的工具和技能。例如，当用户在 utility billing（公用事业计费）产品页面中点击该按钮，OG Assist 就会启动并提示：“嘿，我是来为你解答关于费率代码（rate codes）的问题的。”在聊天界面中，用户能够直接与 Agent 对话，而 Agent 会通过调用特定工具，去查询该模块内的具体数据。

不仅如此，我们还赋予了 Agent 识别屏幕内容的能力。用户可以询问它：“屏幕上显示了什么？你能帮我高亮显示下一步可以执行的操作吗？”此时，Agent 会启动思考流程，确认当前可用的工具，并直接在页面上高亮标出可点击的元素，为用户进行详细讲解。这种将 Agent 深度整合进前端交互的体验，彻底改变了用户与企业级软件的交互方式。

<details>
<summary>Original English Source</summary>

Hi everyone. My name is Gabe de Mesa. I'm an engineer here at OpenGov and today we're going to be talking about agents in production, specifically how OpenGov built and scaled OG Assist. Uh so um this presentation is going to be jam-packed with just so much good stuff. Uh we're going to talk about uh AI agents. We're going to talk about our harness. We're going to talk about um evals, observability, traces. We're going to talk about um tools and skills. Um It's There's going to be a lot of good stuff in here. We're going to talk to you guys about uh what we do at OpenGov and how we operate at the scale that uh we operate at um in production, so you'll be able to see a real use case and workload uh with AI agents. Um so without further ado, let's get started.
Okay, agenda. So just really quickly going to go through uh high-level what we're going to talk about today. Uh I'm going to tell you guys a little bit about OG Assist and what uh OpenGov is. I'm going to tell you guys the origin story of how this all kind of came to be. Uh we're going to talk about OG Assist's uh big bet on effect. Uh a little bit into our core agent loop. Uh we're going to talk about the A2A protocol, evals, and sandboxing. We're going to talk about how we manage long context. We're going to talk about um monitoring, observability, how we collect feedback uh and how we iterate on that feedback. We're going to lastly uh also talk about tools and skills and how at OpenGov uh we use um AI not only externally uh that we uh serve to customers, but also internally to improve our development workflows.
Just a little bit about me before we go any further. My name is Gabe. I'm a software engineer here at OpenGov. I work on the AI agents team and I'm one of the folks that helped build OG Assist and some of the systems that you guys will be seeing today.
So, a little bit about OpenGov. OpenGov is a software company on a mission to power more effective and accountable government. So, OpenGov sells ERP software. That's things like budgeting, procurement, asset management, and permitting. And we were founded about 14 years ago and what's cool is um we have this thing called OG Assist and OG Assist is this little button on the top of all of our products in the in the navigation bar. And what's cool is all of our product suites and product teams have built tools and skills in order to power this button. So, for example, if I open up this this if I click this button and I open up OG Assist, it says, "Hey, I'm going to ask about rate codes, which is very specific to utility billing, the current product that I'm in." And you can see that inside of this kind of chat interface, I'm able to speak to an agent and the agent is able to make tool calls in order to look up information against data inside of that suite. So, it's really cool to be able to kind of first-party create these experiences through the capability that we've built called OG Assist.
Okay, so just a quick story about how this all came to be. So, a little while back we we we saw that AI was really starting to take off and a principal uh spun up this new team called the AI agents team and asked me to join. And um instantly I said yes and OG Assist started to to grow and we started to integrate OG Assist into all our products. And uh not only our back-end capabilities, but also our front-end capabilities as well. So, you'll see that one of the capabilities that we give the agent is it's able to um see what's on the screen and and see and and and and take action on what's on the page. So, you could see that uh I'm asking the agent here, "Hey, hey, what's on the screen? Can you maybe highlight uh some of the next steps that I could take?" So, you can see that the agent here is thinking. It's saying, "Okay, what tools do I have available to use?" And "Hey, let me go and highlight something that you could actually click on and and tell you more about it." So, just another capability of OG Assistant. Just a little short story about how this all came to be.

</details>

---

### 技术跃迁：基于 Effect 的自研 Native Agent 循环

在构建 OG Assist 核心引擎的技术架构选型上，团队最初使用的是 **LangGraph**（一个用于构建循环多智能体应用的框架）。这在项目早期是可行的，但随着业务场景的爆发和开发团队的扩张，框架封装太深、难以精细化控制的问题逐渐显现。为了彻底掌握 Agent 运行机制的绝对控制权，OpenGov 的智能体团队做出了一个极其关键且充满远见的决策：全面押注 **Effect**（TypeScript 的一个开源函数式编程库），并迁移到完全自研的 **Effect Native Agent Loop**。

Effect 类似于 TypeScript 领域的 **Zod**（模式验证库），但它的功能要丰富得多。它原生内置了强大的错误处理机制、日志记录、链路追踪（traces）以及极具优势的结构化并发控制。迁移到自研循环后，Effect 的这些优秀特性直接在底层打通，为团队在微服务架构下快速构建新服务提供了坚实的支撑。

在代码实现上，我们使用 Effect AI 包来实例化语言模型和聊天接口。得益于 Effect 强大的**依赖注入**（Dependency Injection: 将对象所需的依赖项传递给该对象的设计模式）能力，我们可以非常轻松地热插拔不同的底层语言模型，并精细地调控每一次模型调用与流式文本输出。这不仅彻底释放了模型的潜力，也为未来的技术迭代保留了极高的灵活性。

<details>
<summary>Original English Source</summary>

So, the big bet on Effect. Um so, I really wanted to include this slide because um here on the Agents team, we made a huge bet to um to to bet on Effect. And suffice to say it's paid off in dividends. Um we write Effect. So, Effect is this library for TypeScript. It's open source and it helps you write better um TypeScript code. Uh you know, it's got a lot of uh stuff baked in it like a a schema similar to like Zod, if you've ever used that. It's also got um things for error handling, uh for logging, for traces, for uh it's just got so much in there. It really helps write better code and structure your code better and uh helps with architecture, spinning up new services for uh and and for us on the Agents team, really helping uh design and build the the core agent loop. So, you'll see throughout this presentation sprinkled in um how Effect on our team uh has paid off in dividends. So, we we really love Effect here at OpenGov and we encourage other folks to try it out and um yeah, let's keep going.
The Effect Native Loop. So, originally we were on LangGraph and that was fine until the team really started to scale uh and our use cases started to evolve. So, we decided to move over to our own kind of Effect Native Agent Loop to have full regency over this Agent Loop such that if we have complex use cases or features that we need to build, we could kind of get in we we had full control of the of the Agent Loop. And not only that, but now we're fully on Effect. So, all the cool things you get with Effect is now propagated throughout the entire Agent Loop, like the tracing, structured concurrency, the logging, everything is more fine-grained control, and it it really allows us to really unlock the full potential uh having our own Agent Loop from the ground up. Um so, another thing I wanted to mention is on the left side, you'll see a code example. This is really the basics of the Effect Loop that we're using. Uh we're using this thing called the Effect AI package, and in that package, there's this thing called um there's a chat and a language model. So, with the chat, you can instantiate like an a chat, for example, and then you could stream text using um that that kind of stream text function, you could pass in a prompt. And what's cool is uh with a language model under the hood uh of since we're kind of doing dependency injection, we could pass in a different language model if we were to uh hot swap to another one, for example. So, really just having full control of our own Agent Loop just kind of gives us all the levers, and it really just unlocks the full capabilities of the model, and uh for the team as well, to have full agency over this this loop.

</details>

---

### 规范与安全：A2A 协议与隔离沙箱机制

在多智能体协作和执行安全方面，OpenGov 引入了行业领先的规范和隔离技术。首先，团队采用了 Google 创立的 **A2A协议**（Agent-to-Agent Protocol: 智能体间相互通信的开放协议）来规范化定义 Agent 的路由与发现机制。

在后端，每一个 Agent 都会关联一张包含其名称、描述及元数据的 **Agent卡片**（Agent Card: 包含智能体名称、功能描述及元数据的数据结构）。通过这一严谨的 Spec 契约，前端与后端能够高度对齐地去生产与消费各种 Agent 服务，极大地促进了跨团队的协作效率。同时，结合 A2UI 扩展，Agent 还能在聊天界面中直接按需输出自定义的前端 UI。

在涉及生产安全的敏感场景下，我们设计了双重防护壁垒：
* **人机协同 (Human in the loop)**：当 Agent 试图调用需要特定权限的工具或执行具有副作用的 mutating 变更操作时，系统会确定性地中断执行流，并弹出一个审批 UI。人类可以直接选择“同意”或“拒绝”本次操作，确保敏感控制权永远掌握在人类手中。
* **沙箱隔离 (Sandboxing)**：如果 Agent 需要执行用户临时编写的未知代码，或者执行文件创建任务，所有操作都会被限制在动态创建的 **沙箱**（Sandboxing: 隔离的临时执行空间）内。例如在 AI Engineer Conference 2026 现场演示中，当用户要求 Agent 编写代码并编译生成一份可以直接下载的 PDF 报告时，这一系列高危动作均在沙箱中安全运行并自动销毁，彻底隔离了生产系统可能面临的安全隐患。

<details>
<summary>Original English Source</summary>

Another thing I wanted to mention is the agent-to-agent protocol. So, here on the agents team we've had a lot of success with this protocol. So, this protocol being the protocol that Google created. Um kind of an open protocol for agents to intercommunicate, but um we found this very useful for uh defining our agent routes. So, for example, in the back end and our model and our schema to follow this kind of agent protocol. So, we modeled So, for example, there's this thing called an agent card which you see here and it's got the name of the agent, a description, etc., right? And having this kind of rigorous protocol, this rigorous spec really helped drive our development and drive alignment because, you know, all we had to do was um align with this spec and follow this spec and we knew that this was kind of the contract that our front end and back end would both consume and and produce. So, um this uh I would say also has been uh very helpful for us. And And what's really cool is A2A has a lot of extensions, right? So, you could extend the protocol uh add in like metadata. Uh there's also A2UI. Um so, lots of fun stuff uh with A2A protocol, but uh this is kind of what's worked for us. So, just sharing that with with you folks.
Feedback and evals. ... Humans in the loop. So, this is a really cool feature we built where we deterministically interrupt the agent loop if there is a tool call approval required. So, if an agent tries to make a tool call that it needs human approval for, it'll show this UI and the human uh can click accept or reject. So, explicitly rejecting or explicitly accepting, uh the action that the agent is trying to make. And this ensures that, uh you know, we're building trust and also ensuring that, uh you know, we're being safe, especially when the agent's trying to do a mutating operation and always always always making sure that, um humans are in the driver's seat.
Sandboxing. So, another thing that we, uh worked on, um kind of similar to the safety slide we just saw was, um whenever an agent tries to execute code or tries to create files, it does so in a sandbox. So, we gave our agents sandboxes such that it could spin up these sandboxes on demand and it could use those sandboxes to honestly write code, execute code, create files and it's kind of this safe ephemeral isolated space such that the agent can can can take action in there and not and we don't have to worry about uh any risk to you know our our production systems. Um and it's it's really cool cuz they also get uh tied uh tear down at the end so um in this example I said, "Hey, create a PDF uh for the folks of the AI Engineer Conference 2026." And um allow me to download it so I could share it with them. And you could see that the agent created this really cool PDF inside of that sandbox. So just really wanted to cover the sandbox feature and just give you a brief kind of overview of of sandboxing.

</details>

---

### 上下文与调优：长上下文管理、生成式 UI 与可观测性

随着用户与 Agent 交互的深度增加，长上下文管理和系统可观测性成为了系统能否稳定支撑生产规模的决定性因素。在**长上下文管理**（Long Context Management）上，传统的直接拼接历史消息极易导致模型超出 Token 限制，或者因为长文本注意力分散而“遗忘”关键指令。

为了解决这一痛点，我们设计了 **滚动摘要**（Rolling Summarization）机制。当对话轮次超过设定阈值后，系统会自动对较早的消息生成滚动摘要，同时仅保留最近的 $N-5$ 或 $N-10$ 条原始消息。当用户在第 100 轮对话中突然提起：“记得我们最开始讨论的那个问题吗？”，Agent 便可以通过内存组件检索 recall 滚动摘要，在降低 Token 开销的同时完美重现初始的上下文。

在前端交互的敏捷性上，我们利用预先在客户端注册的 UI 元语（primitives），实现了**生成式UI**（Generative UI: 运行时根据上下文动态生成的界面）。当用户需要 Agent 撰写文章并提供示例主题时，Agent 可以在运行时动态地为用户渲染出一个定制表单。用户无需离开聊天框即可直接在表单中勾选选项，这种高度情境化的交互让体验变得非常个性化。

在后端的运维和调优方面，Effect 带来了原生开箱即用的**链路追踪**（Tracing）能力。每一个 Effect 函数都会自动打上 Span 标签并串联起来，使我们能够对各服务间的调用耗时、瓶颈和故障进行交叉比对。结合 CI 流程中的**自动化评估**（Automated Evals: 在持续集成中运行的自动化准确率测试）以及前端的“赞/踩”用户反馈机制，我们得以进行高速的迭代优化。最后，AI 的价值不仅体现在外部客户产品上，更大幅提升了 OpenGov 内部的开发效率。通过在团队内部深度集成 Claude 和 Cursor 智能体，我们的代码阅读、编写和评审效率得到了极大的提升，达成了开发速度的飞跃。

<details>
<summary>Original English Source</summary>

Long context. So um inside of Ogie Assist, we have hit many hurdles like with especially with legacy models now like with uh token limits or just way too much just completely overloaded with context especially as conversations get longer. So we found that having some sort of um rolling summarization was more effective than you know always stuffing in the latest and most recent uh messages uh rather just you know give like a running summary after n number of messages and uh maybe you only want the like n minus five most recent messages or n minus 10 most recent messages, right? Um and it may be that you're only talking about a specific topic now, but you may want to refer to uh context earlier like a hundred messages above, then um it uh that's where kind of the the memory component comes in cuz when you have this rolling summary of a a really long conversation, then you could do recall over that uh summarization. And um you know, if you ask the agent, "Hey, remember that thing that we talked about?" then the agent within the thread will be like, "Yeah, I do know what you were talking about. I have kind of this short little tidbit." And it can, you know, follow up and and and do more kind of with that uh summary rolling summary in mind. So, that's kind of how we handled long context and memory, and it's worked pretty well for us. So, uh just wanted to share a little bit about that and how we've uh solved the long context problem.
UI on the fly. So, um in this example, I said to the agent, "Hey, generate me a long essay, but give me some examples about what the essay could be about." So, what's really cool is the agent had this primitive registered uh uh this form, and it was able to build out this form for me at runtime and give me some options of what I could choose from. So, it feels very personal and it feels very kind of in the moment that it's able to to give me these options just at runtime. So, um this is kind of just a short little um thing I wanted to include here about generative UI and how we uh are able to render UIs on the fly.
You can't scale what you can't see. So, um this uh this kind of section is about tracing uh and observability. Really, what's cool about Effect is you kind of get tracing out of the box. Um you know, when you use these effect functions, they all get kind of tagged automatically with like these spans, and kind of the span gets picked up and feeds into these traces so that you can kind of get these kind of drill downs of these function calls. So, here's an example of a trace from the effect team. I have it linked. You could see that like, "Hey, when you hit this API, go to this endpoint, to this handler." And you know, etc. And it takes And what what's really cool is you could profile all your traces, right? So, this takes a total of this many seconds and you can see where the bottleneck is here. If there's a failure, you can cross-reference data across services. So, really, really important, especially working in agentic systems where we're we're integrating with other teams and other APIs and other um other platform capabilities. So, what's cool with effect is you get all this tracing out of the box and it really makes building this agentic experience, debugging it, and maintaining it just a breeze.
Tools and skills. So, uh not only did we make a big bet on effect, but we also made a big bet on tools and skills. So, we believe that tools and skills are really all you need. And in this case, you could see on the left, we have this tool called get dad joke. And this is kind of the effect way and kind of the building blocks of how we do things here at OpenGov, but you know, this is pulled from the effect website, but you could see, "Hey, this is how you make a tool." And then you add it to a tool kit, which is a collection of tools, and then you can register this this tool kit with the with the language model. So, for example, if you had a prompt that said, "Hey, generate some dad jokes about pirates." Well, guess what? The agent has a tool uh that can help get a dad joke. So, um really, this is the the building blocks of how we did tools and eventually skills and really just is has paid off wonderfully for for our organization. So, um really recommend trying out this effect AI package from uh effect and um just trying out building out your own tools and skills.
Developer velocity. So, not only do we build agents for our customers, but we also use agents um here internally uh in OpenGov. So, we uh use a lot of Claude and Cursor uh and it's just really been a game-changer for our team. Um it's funny because we're building tools and skills for customer-facing uh agents and and that has been great, but we're also building them internally as well to help accelerate our development workflows. So, things like Claude, Cursor, Claude agents, they really help accelerate how we read, write, review code and and ship. Um so, it's it's just been such an accelerate. So, definitely just wanted to mention that uh before we wrap up. That's it. Thanks so much for watching. You've made it to the end. Let's build agents that ship to production.

</details>