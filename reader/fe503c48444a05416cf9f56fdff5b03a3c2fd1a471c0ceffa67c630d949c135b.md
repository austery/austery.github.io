---
author: AI Engineer
date: '2026-06-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hCMrEfPG2Yg
speaker: AI Engineer
tags:
  - generative-ui
  - mcp-protocol
  - interface-design
  - human-agent-collaboration
  - software-architecture
title: 超越组件：为 MCP 应用构建生成式 UI 的演进之路
summary: 本文探讨了 UI 界面从静态组件到声明式 UI，再到实时生成的生成式 UI 的演进历程。作者强调了模型能力的爆发如何重塑前端开发，并指出模型上下文协议 (MCP) 是生成式 UI 安全交付的核心机制，最终展望了从单一组件向人机协作画布转变的未来。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Ruben Casas
  - Andrej Karpathy
companies_orgs:
  - Postman
  - Anthropic
  - Netflix
  - Vercel
  - OpenAI
products_models:
  - ChatGPT
  - GPT-5.2
  - Claude
  - Opus 4.5
  - MCP
  - JSON Render
  - Excalidraw
media_books: []
status: evergreen
---
### 界面设计的奇点：从“穷人版编码”到高保真生成

回顾 2022 年 11 月，我们与 AI 的交互还停留在初级阶段：在 **ChatGPT** 中请求创建一个组件，然后手动执行复制粘贴，这种反复修正的过程被戏称为“穷人版编码”。然而，随着 2025 年底 **GPT-5.2** 和 **Opus 4.5** 等关键模型的发布，UI 领域迎来了一个难以置信的拐点。这些模型不仅能够处理复杂的长程任务，更具备了极高的 **UI 高保真生成能力**。

一个典型的案例是：当你仅用一句提示词要求模型重写博客时，它不仅完成了任务，还自发地创造了一个带有模糊动画效果的搜索框，并原生支持了**无障碍访问**（Accessibility）。这标志着我们正式跨越了“代码能运行就行”的阶段，进入了 AI 编写的前端代码在质量和审美上全面超越资深工程师的时代。面对这种现实，界面的范式正被迫从静态向动态迁移。

<details>
<summary>Original English Source</summary>

Hello everybody. So, I know I am the person standing between you and your lunch. And but this is going to be a very interesting talk that combines the the previous two talks into the future. And that's what I want to talk about today.

So, back in November 2022, what we used to do was we used to go to ChatGPT and ask ChatGPT to create a component. And we would just copy paste. You have to ask reply in code blocks. Then, you know, again, fix it, repeat. And this is what I call the poor man's by coding. And we have come a long way. It kind of worked. It was very exciting. You could get models to could actually build some UI for you. And I'm sure that was not going to write better code than me, right?

And then things improved very very rapidly, very very fast. What happened last year, and if you are aware of what happened in the the the last months of 2025 was this acceleration, an incredible inflection point where things changed. And it will go down in the history books as things changed very fast all at once. And this is in part because of the release of two very important models, which were 5.2 ChatGPT, sorry. It was yeah, a GPT 5.2 and Opus 4.5. And they were not just very good at most of the task, long horizon tasks. They were also very good at high fidelity UI generation. And they were producing very good working UI. Sometimes thoughtful, sometimes really really good. And also very fast.

Now, I experienced this when I tried one of these models, tried to rewrite my my blog. I know people have used this in a more creative ways, but I just tried, you know, a single prompt, rewrite my blog. And then it did this, which I didn't ask for. It created a nice nice search box with a blur animation, with accessibility out of the box. And then that's when I realized that in the space of of 3 years from when ChatGPT was released to today, we went from you know, few lines of code is great. It can it runs. Oh. And now it can write better front-end code than me. And you know, I I don't mind. No no ego. It's just reality.

So, here's the question. If these models are so good at writing UI code, why are we still stuck in this mainly old paradigm of mostly static UI? And where is where is that Jarvis moment that we've been talking about earlier? Where are my floating UI windows that appear and disappear? And why we not there yet?

</details>

### 新计算机的交互危机：聊天窗口是最终形态吗？

**安德烈·卡帕斯**（Andrej Karpathy）曾提出一个深刻的洞察：我们正拥有一台“新计算机”，但目前的交互方式就像是在直接面对 70 年代的终端。尽管我们拥有了超人工智能，却尚未发明出成熟的界面语言。目前的现状是，几乎所有 SaaS 公司都盲目地在主页塞入一个**聊天窗口**（Chat Box）。虽然聊天是目前可用的过渡方案，但它绝非 UI 的最终形态。

另一种竞争性的思路是**超级应用**（Super App）模式，如 **ChatGPT** 或 **Claude**。通过 **MCP**（Model Context Protocol）协议，我们不再需要在每个独立应用中嵌入聊天框，而是让第三方 UI 直接在 AI 代理的环境中渲染。这种“一统天下”的模式解决了界面的碎片化问题。然而，比“UI 在哪里运行”更关键的问题是“模型在生成什么”。目前的生成范式正经历从**静态组件**到**声明式描述符**（如 JSON 或 YAML）的跃迁。

<details>
<summary>Original English Source</summary>

So, my name is Ruben Casas. I am a staff engineer at Postman. And I've been looking at UI and generative UI for the past year, and I've been working with MCP apps as well. And today I want to show you what we're doing today and where we're going in the future.

So, the news are we have a new computer. And as Andrej Karpathy put it, interacting with this new computer is like talking to the terminal. You have direct access to this operating system. And the GUI has not been invented yet. It's like we are in the '70s, where everything was just text. And we have a super intelligence, but we don't have a mature interface language. And today we are still trying to figure out what is this new interface for for this computer.

And people ask, is it chat? I'll show you what we're what we're doing today. And actually this was a very recent tweet last week, where people were complaining that most SaaS companies have been adding chat to their their homepages, and everybody's just putting chat everywhere. And and that's that's fine. I don't have a problem with chat. It's not the final UI. It's okay for now. But the question is, if it's not chat, then then what is the interface for this computer?

On the other hand, as we have seen with MCP apps, is there [clears throat] is another thought, which is we will have one app or super app to rule them all. And this is where MCP apps comes in, where instead of putting all of these chat windows into your homepages and and to every single app that you use, we will have a super app like ChatGPT or Claude or Gemini, where you will be interfacing with most of the the UI and the websites that we have today. And this is good. This is the way we using MCP apps today to to render third-party UI inside one agent environment.

Now, these two options both could be valid. And and I believe these are part of the evolution towards finding out what is that new interface for that computer. And to be honest, I don't know which one is going to be the the final one. Consumers will tell us. But one thing is that these are two different questions. The question is where does the UI runs? In this case, is it third-party UI, a super app, or in this case, chat everywhere?

But most interesting is what is the model generating. And this is what I want to talk about today in terms of how are we generating this UI? And we have seen this. We have mostly static, declarative, and generative UI.

</details>

### 从静态注册到声明式平衡：UI 生成的技术路径

目前大多数 AI 代理仍采用**静态组件**（Static Components）模式。在这种架构下，AI 仅作为协调者，通过 **MCP** 调用预定义的工具。开发者预先编写好组件，代理则负责生成参数和数据 props 传递给客户端进行渲染。这与过去 20 年的 UI 开发逻辑本质相同，只是数据源变为了模型。例如 **AGUI 协议**和 **Goose** 的自动可视化工具，都是通过匹配数据类型来套用预设的图表组件。

进阶阶段是**声明式 UI**（Declarative UI）。这种模式下，代理不再直接传参，而是生成一个**描述符**（Descriptor，通常是 JSON 或 YAML）。类似于 **Netflix** 长期使用的服务器驱动 UI（Server-Driven UI）架构，描述符定义了界面的结构，由专门的渲染引擎翻译成最终 UI。这种方式在灵活性与一致性之间达成了完美的平衡：它既能保证设计系统（Design System）的统一性和预测性，又能通过减少生成的 Token 数量来降低成本并提升速度。**Vercel** 开发的 **JSON Render** 正是这一路径的佼佼者。

<details>
<summary>Original English Source</summary>

And I'm going to describe briefly this one. So, we have um to start with the the static components way of running running UI, which is what most agents do today. The agent is just an orchestrator. The agent makes a tool call via MCP apps or direct agent tool call. Then we will have some parameters and data passed to predefined static components that have been created by developers. And this is very similar to what what we have been doing for the past 20 years with with UI. And then the client renders the component. And if you see here, it's very similar to just getting a server to send some data, and then the UI will be rendered by the client. But in this case, the agent will be generating that data and the props to to do this. And some examples that we have today are the AGUI protocol. They have an SDK when you can register a client tool that maps to a React component. The tool call will receive some props. Those props will be mapped to a static component that then will be rendered to to the user.

Another example is Goose. Goose is a an MCP client where you can try most of the MCP features. And Goose has this really interesting feature called Goose Auto Visualizer, where you can just pass any type of data to Goose, and Goose will try to match that data, organize it, and then pass it to a set of predefined components that the Goose team have created. In this case, we have a few interesting components that you can use to visualize your data. So, that's the static way. That's the most common way of generating UI today.

But I have seen an evolution recently where we call now declarative UI. And declarative UI takes it to the next level. So, we will still have some predefined static components that developers build, and it contains your design system and all these components that you have. But instead of the agent just passing the props and the data, the agent uses a descriptor that could be either JSON or YAML. Or I've seen Python as well with with fast MCPs, where they have a a descriptor in Python that maps to these predefined static components. And then you have this translation rendering engine that takes those descriptors and converts them into the final UI.

How is this different? Well, in this case, it is more dynamic. They are still static components, but it's more personalized. And you if you look at this and you think that this might look familiar as well, it's because it is not new. Netflix has been doing this for a long time since the the personalization and server during UI era, where when you go to the Netflix homepage, you will get a UI that is completely personalized to you. But that's still mapped to the Netflix components and UI elements.

Another very good um tool that I've seen recently is JSON Render. JSON Render is being built by Vercel. And it is a way to map your components using JSON and also YAML. They released the YAML support recently. And create all of these very dynamic, very good UI interactions that you can use today. But now JSON Render still, they say, is constrained to your static components. And yes, they're still static components. The LLM is not generating these components. The LLM is generating the JSON. However, I think in at this point in time, declarative generative UI is probably the perfect balance today in terms of flexibility and consistency. Because you would still want your design system. You still want to have uh, predictability of what the UI is going to be generated, also faster and also potentially cheaper at this point. Uh, so you don't create and use a lot of tokens to create the UI.

</details>

### 安全沙箱与实时生成：MCP 作为 UI 交付的标准协议

更极致的形态是**生成式组件**（Generative Components）。既然模型已经精通 React、JavaScript 和 CSS，为什么不让它们在运行时按需生成代码？作者在 **Postman** 进行了一项实验：创建一个天气 Agent，它不仅调用 API，还会实时生成独一无二的 HTML 和 CSS 界面。这种模式虽然极具想象力，但面临着严峻的安全挑战——我们绝不能直接运行模型生成的第三方代码。

这就是 **MCP Apps** 如此关键的原因。它提供了一个完美的**沙箱机制**（Sandbox），通过双层 iFrame 实现了代码的安全隔离。更重要的是，**Anthropic** 的 **Visualizer** 功能在战略上选择了 MCP 而非自研私有渲染架构，这证明了 MCP 协议作为 UI 交付标准的强力地位。它原生支持身份验证、工具调用和消息传递，是目前动态、实时生成 UI 的最佳交付载体。

<details>
<summary>Original English Source</summary>

But as I mentioned at the beginning, why why are we still stuck here? And what's the next level? I think the next level will be uh, generative components. And generative components uh, goes into like the the premise I I put at the beginning where the models are good at writing front-end code. They are good at writing React. They're good at React creating in JavaScript, CSS. And the question is why we don't let them just write that on demand at runtime. What could possibly go wrong with that, right?

This model um, of generating the UI uses the agent capabilities. And in this case, you can also use a tool call, but instead of calling this uh, layout rendering engine, you can call the same model with reverse sampling or you can call another model that will generate the HTML, CSS, JavaScript on demand and then it will be passed to the client. I did this experiment um, I work at Postman on this experiment where I created uh, this weather agent that goes to the API, the weather API. It creates a joke. It creates the HTML, CSS, JavaScript, all in one tool call. And you get presented with this random but very uh, imaginative UI where everything is created by the agent. There is no component. There is no translation.

So there is of course a problem with this approach. Uh, and the problem with this approach is uh, if we don't trust third-party code, well, we should not trust um, code that has been generated by LLMs and then just present it to the user. Uh, generative UI and and this level of generative UI needs a distribution model. And this distribution model requires a boundary, requires containment and requires a sandbox, which is what we were talking about earlier. This is what I think MCP apps matter a lot because MCP apps are the best uh, delivery mechanism uh, for generative UI. We have the features provided by MCP, including authentication and tool calling and message passing between the UI and the agent. Uh, it's sandboxed by default with that double iFrame. Is the default for third-party UI delivery today. Does this become the standard?

And one interesting thing is it's not just for for third-party UI. It can also be used for first-party UI. And this is why I think what Anthropic is doing with the the visualizer feature is very interesting strategically speaking because they could have just created their own rendering um, and an architecture mechanism for delivering this in interaction in in cloud, but they decided to go with MCP apps because MCP apps provide most of those um, features that I mentioned earlier uh, out of the box. So if Anthropic decided to use MCP apps for their first-party UI, uh, you can ask yourselves why cannot we do the same? It is um, a very very strong protocol. And especially when the UI is being generated on the fly by the agents, by the the code uh, coding models, then is the best um, mechanism for delivery.

</details>

### 协作式画布：超越单一组件的未来想象

目前的生成式 UI 仍处于“收音机时代”。正如早期电视节目只是“对着相机的广播剧”一样，我们目前的想象力还局限在把旧技术搬入新媒介。未来的生成式 UI 将超越单一的组件呈现，演变为一种**人类与代理的协作体验**。

**Excalidraw MCP App** 是这种未来的先驱。它不仅是一个绘图输出工具，更创造了一个**共享产出物**（Shared Artifact）。在这个画布上，人类可以与 AI 代理共同编辑一个动态空间：你可以通过自然语言要求 AI 修改架构图，也可以直接动手拖拽调整。这种双向互动的画布模式打破了“Agent 只是编排器”的局限，让 AI 真正成为创意过程中的协作伙伴。未来的界面将是深度个性化且具备协作属性的“无限画布”，我们正处于重塑新计算机交互逻辑的起跑线上。

<details>
<summary>Original English Source</summary>

Now, today is probably not the final form. And people keep saying is chat the final form? Is MCP apps the final form? We're still we're still trying to figure this out. And the obvious future is probably too obvious. And we said about where is my Jarvis? Where is my floating windows? And if you think about it, that's the obvious things thing that people would think how we would look like if we were generating or creating a new uh, user interaction. But what I think is we don't have enough imagination yet. And and this analogy I heard recently is very interesting when when uh, radio came out in the 30s, um, the the the first um, sorry, the the TV came out, the first uh, TV shows were radio shows with cameras because they could not imagine what you could do with this new technology. So this new technology that we have today is very similar when television came out and we are still in the radio era where we don't know all the amazing things that we will do in the future with this new media, with this new power that we have with the with the new computer. And we can see that we cannot even imagine what it's going to look like.

Uh, of course this is a speculative, but what do I think is actually going to happen is we are going to be moving uh, beyond components and more towards a collaboration uh, through human agent collaboration. If you haven't heard about the Excalidraw MCP app, uh, definitely check it out because the Excalidraw MCP app is not just for um, output and visualization of diagrams. The Excalidraw MCP app does something very interesting, which it creates a a shared artifact. It creates a canvas where a human and an agent can collaborate together into a shared space where you can go back and forth with the agent and ask, you know, change this, but you can also click around, modify the UI the way that you are used to. And that becomes the new way of interacting, the new way of experiencing the the agent um, powers.

And and at the moment again, we are very constrained to our imagination. And and I believe these agents are very very powerful for just to just use them as a orchestrator and a delivery mechanism to show me some visualizations. So I believe beyond components, it will be the future of generative UI will be more a collaborative experience where yes, we will have some generative UI, but that UI is going to be super personalized and it's going to be collaborative. So we we are still early. Um, we don't have the answer. People say, you know, what is what is the future of the user interaction, the user interfaces? We don't know yet. But we can shape that future uh, and create this uh, new computer. And that's me. Thank you so much uh, for listening to this.

</details>