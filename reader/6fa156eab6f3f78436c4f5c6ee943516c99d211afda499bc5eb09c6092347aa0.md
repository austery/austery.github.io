---
author: AI Engineer
date: '2026-08-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-jY2T2PiJBE
speaker: AI Engineer
tags:
  - model-context-protocol
  - agentic-web
  - generative-ui
  - decentralized-distribution
title: MCP Apps：开启智能体网页（Agentic Web）与去中心化应用分发的新时代
summary: 本访谈深度解析了模型上下文协议（MCP）在应用层（MCP Apps）的最新演进。创作者 Ido Salomon 和 Liad Yosef 共同探讨了如何通过 MCP 传输高动态、交互式 UI，重塑传统以文本为主的 AI 交互体验。他们指出，MCP Apps 的本质是开启“智能体网页”（Agentic Web），将传统的网页界面打散为 UI 原子并融入个人 AI 助理中，实现“一次编写，到处运行”的去中心化应用分发新范式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - Google
  - Shopify
  - Postman
products_models:
  - ChatGPT
  - Claude
  - Cursor
  - MCPY
media_books: []
status: evergreen
---
### 自我介绍与 MCP 现状

**Ido Salomon**: 嗨。大家好。我们是昨天才准备好这个演讲内容的，所以它可能有点“过时”了。我是 **Ido Sadan**（Ido Salomon），我是 **MCPY** 的创建者，同时也是 MCP 应用程序（MCP Apps）在 MCP 指导委员会中的共同创建者与维护者。如果你参加了昨天的分享，应该知道我还创建了 **Adam Craft**。

<details>
<summary>Original English</summary>

**Ido Salomon**: Hi. So, hi everyone. We built this talk yesterday, so it might be out of date. I'm Ido Sadan, I am the creator of MCPY and co-creator and maintainer of MCP apps in the MCP steering committee. I also created Adam Craft if you were in the talk yesterday.

</details>

**Adi**: 我是 **Adi**（Liad Yosef）。我和 Ido 一起在 MCPY 项目上工作。我同时也是 **MCP 应用程序规范（MCP Apps Spec）**的共同创建者和维护者，并且在最近共同创立了 **Aura**。Aura 是一个专注于**智能体网页（Agentic Web）**的研究实验室。我们稍后会具体讨论这个概念。

<details>
<summary>Original English</summary>

**Adi**: I'm the Adi. I work with Ido on MCPY. I'm also the co-creator and maintainer of the MCP apps spec and recently co-founded Aura, which is a research lab for the agentic web. And we're going to talk a little bit more about it later.

</details>

**Ido Salomon**: 事实上，MCP 应用程序已经悄然融入了我们的日常生活。你可能甚至都没有意识到这一点，但如今你在 **ChatGPT**、**VS Code** 以及 **Slack** 中所使用的所有那些极其精致、炫酷的应用，其底层其实都是基于 MCP 和 **MCP 应用程序规范**所构建出来的。

<details>
<summary>Original English</summary>

**Ido Salomon**: So, MCP apps are all around us. You might not even realize it, but all the fancy apps you have today in ChatGPT and VS Code and Slack are actually all based on MCP and the MCP app spec.

</details>

### 为什么需要 MCP Apps？

**Adi**: 如果我们稍微退后一步，问一个最根本的问题：我们为什么需要 MCP 应用程序？**MCPY** 或者说 MCP 应用程序背后的核心理念到底是什么？

当我们在使用各种聊天客户端与 AI 进行交互时，过去我们习惯于使用纯文本，因为这确实是一种非常自然的交互界面。然而，从传递大量复杂信息的角度来看，**纯文本其实是效率最差的沟通方式**，对吧？因为没有人想要去面对一堵堵由文字堆砌而成的“文字墙”。

事实上，这正是许多公司抗拒去构建 MCP 服务端（MCP Server）的主要障碍。这些品牌和企业并不希望自己在 AI 时代被降维打击，仅仅被简化为一个只提供文本数据的“文本数据库”。他们不想在这一过程中**失去自己的品牌标识与品牌个性**。他们辛辛苦苦地为自己的数据设计并构建了极佳的**用户体验（UX）**，当然不希望这些心血结晶在 AI 界面里看起来就像一堆冰冷混乱的文本格式。

所以，如果我们不这样做，而是让应用程序能够直接把它们的**用户界面（UI）**发送到聊天窗口中，那会怎么样？如果每一个服务、每一个品牌都能够直接将自己的用户界面无缝传递到用户的聊天会话中呢？

这样一来，我们就不必再去忍受刚才看到的那些凌乱无序的纯文本，而是可以直接让应用把包含自身品牌形象和专属 UI 组件发送到聊天会话里。我们一眼看过去就能清楚地知道：“哦，这中间的部分是 **Shopify** 的界面，这是 **Hugging Face** 的界面，这部分则是 **Monday** 的应用。”

更进一步，如果我们不仅仅把这当作一种简单的可视化展示，而是希望它能够完全实现交互呢？我们希望用户能够在这个界面上与 **Hugging Face** 等服务进行实际的交互操作，并且让 **Hugging Face** 在后台真正执行相应的业务逻辑。

<details>
<summary>Original English</summary>

**Adi**: And if we take a step back and we ask, why do we need MCP apps? What's the idea behind MCPY or MCP apps? So, when we work with chats, when we chat client clients, we used to text because that's the natural interface, but text is really the worst way to convey a lot of information, right? Because we don't want walls of text. And actually, this is the main blocker from companies to build an MCP server. They don't want to be reduced to a textual database. They don't want to lose their brand identity in the process. They don't want their data that they work so hard on um building the UX for to look something like this. So, instead of this, what if the apps could just send their UI to the chat, right? What if every service and every brand could just send their user interface to the chat? So, instead of us looking at something like this, we could just have the apps send their own identity, their own UI chunks into the chat, and then we take a look and we see, \"Okay, yeah, I know this is Shopify in the middle. I know this is Hugging Face. I know this is Monday.\" And what if we don't want to do it only as a visualization? We also want to do it interactive. So, we want the users to be able to actually interact with Hugging Face, for example. And for Hugging Face to actually do something with it.

</details>

### 演进历程与生态体系

**Ido Salomon**: 没错，正如我们所说，有了 **MCPUI**，我们就不需要再去凭空想象未来了。我在去年 5 月创建了 **MCPUI** 项目，它本质上就像是**在 MCP 之上运行交互式应用程序的开放协议**。所以，它解决的不仅仅是如何在网络上进行 UI 的传输，更定义了这些用户界面和应用程序如何与运行它们的宿主环境（Host）进行实时双向通信。

就在几个月前，我们与 **Anthropic** 和 **OpenAI** 达成合作，共同创建了 MCP 的官方扩展，也就是我们今天所说的 MCP 应用程序（MCP Apps）。它是基于 **MCPUI**、**MCP SDK** 以及该领域内的其他现有解决方案整合而成的。

它的发布非常酷。起初是由 **Claude** 和 **VS Code** 率先提供了官方支持，但到现在，显然 **OpenAI** 和其他许多主流的 AI 平台也已经全面采纳并支持了这一协议。

<details>
<summary>Original English</summary>

**Ido Salomon**: So, we don't have to imagine the future as we said with MCPUI, which I created in May last year, and took that, which is essentially like an open protocol for interactive applications over MCP. So, it's not only how you transmit UI, but also how that UI, that application communicates with the host. And just a few months ago, we partnered with Anthropic and OpenAI to create the official extension to MCP, which we call MCP apps based on MCPUI, MCP SDK, and other solutions in the field. Their launch was pretty cool with Claude and VS Code supporting it to begin with, but now obviously also OpenAI and others have adopted it.

</details>

**Adi**: 是的，早在大概一年前，**MCPUI** 就迎来了一批非常早期的开拓型采用者，比如 **ElevenLabs**、**Shopify** 和 **Postman**。这些公司是最早开始相信这个规范、相信这个愿景并提供技术支持的先驱者。

同时，**Goose** 也在当时迅速跟进并支持了它。这里面还有一个非常有趣的趣闻：今天 **Block** 刚刚发布了他们基于 MCP 应用程序构建的**智能体商业解决方案（Agentic Commerce Solution）**。所以你可以看到，一年前 Goose 还是第一个支持 MCPUI 的客户端，而如今这个规范已经成为了 Block 商业产品线中的核心组成部分。

到了今天，我们拥有了多得多的客户端来支持 **MCPUI**。包括大家熟知的 **Cursor**、**GitHub Copilot** 以及 ChatGPT，都已经全面支持了 MCP 应用程序。

你们现在所熟知的许多 **ChatGPT 应用程序**，实际上都是基于 MCP 应用程序构建而成的。甚至 **OpenAI 官方也极力推荐使用 MCP 应用程序作为首选协议来开发 ChatGPT Apps**。

此外，还有 **Postman** 等许多平台，当然也包括 **Claude**，都已经全面支持了 MCP 应用程序。与此相伴的是，我们身边已经建立起了一个极其庞大的开发者社区，对吧？人们开始为 MCP 应用程序编写各种各样的插件，开发与不同智能体（Agents）的集成接口，甚至推出了关于如何构建 MCP 应用程序的专业课程。

这些都是专门为 MCP 应用程序开发的集成生态。我们可以很自豪地说，我们拥有一个非常活跃的社区。

目前有一个名为 **X-apps**（或 `x-apps`）的开源仓库，这就是存放 MCP 应用程序核心代码的地方。任何开发者都可以直接访问这个仓库，提交 PR，提出关于如何进一步扩展和改进这个规范的想法。

同时，我们在 MCP 指导委员会内部成立了一个专门的工作组，每隔三周就会召开一次会议。我们会针对协议的未来发展方向进行深入研讨，探讨如何让这个规范不仅能够服务于那些科技巨头和大型应用，也能够切实惠及更广泛的开源社区。所以，这是一个由 Anthropic、OpenAI 以及 MCP 应用程序协议的所有合作伙伴共同参与的、完全公开透明的开放工作组。

<details>
<summary>Original English</summary>

**Adi**: Yeah, and there are a lot of early adopters to MCPUI. 11 Labs, Shopify, Postman. Those were one of the first first companies to support it back like a year ago. They were the one believing in this spec, in this vision. And Goose also supported it. And it's a it's a funny anecdote because today Block released their agentic commerce solution that is based on MCP apps. So, a year ago Goose was the first client to support MCPUI, and now it is part of Block's product uh product. And today we have a lot more clients that are supporting MCPUI. We We Cursor, and we have co-pilot and GitHub ChatGPT support MCP apps. ChatGPT apps that you know are actually based on MCP apps and open eye actually recommend using MCP apps as the protocol to build ChatGPT apps. Postman and a lot more and obviously Cloud supports MCP apps. But we also have a lot large community around it, right? So people start to to build plugins to MCP apps and um integrations to different agents and also courses on how to build MCP apps. This is by integration for MCP apps. So we have a lot community around it. Um There's a repo X app which is the repo for MCP apps where everyone can just come and propose PRs and ideas of how to how to extend this spec and we have a work group in the MCP committee and we're convening every 3 weeks. We have a tri-weekly meeting on the future of the protocol and how to make the spec not just serve the bigger apps but also the community. So it's an open working group with Anthropic, Open AI and all the partners in in the MCP apps protocol.

</details>

### 核心概念：如何传输 UI？

**Ido Salomon**: 好的，那么让我们来深入了解一下 MCP 应用程序的几个核心概念。

第一个，也是最显而易见的问题是：我们到底**如何通过 MCP 协议传输用户界面（UI）**？

如果我们看看 Claude 在几个月前的交互方式，当我向 AI 提问时，在最理想的情况下，它会向我的 MCP 服务端发起请求，然后服务端会返回一个纯文本的响应。这种交互体验显而易见是次优的，不够理想。

那么，如果我们希望获得比纯文本更好的交互体验，应该怎么做？

现在，我们可以利用 MCP 协议中现有的基础原语——也就是**资源（Resource）**，来返回 HTML 内容。因为 Claude 支持 MCP 应用程序规范，所以它能够直接获取这些 HTML 数据，并在前端将其渲染为一个高度交互式的应用界面。例如，可以直接在聊天框里呈现出世界上最棒的音乐原声带播放列表。

但是，如果你不仅想看，还想要实现更深层次的交互，该怎么办？这个界面看起来确实很棒，它展示了音乐列表，但如果我想把其中一首歌标记为收藏呢？我需要实际的交互，我需要应用程序和宿主环境之间进行实时的数据通信。

<details>
<summary>Original English</summary>

**Ido Salomon**: Okay, so let's look at a few of the core concepts of MCP apps. The first and most obvious one is how do we even transmit UI over MCP? So if we look at this example of Cloud like you know agent times like a few months ago and I would ask something best case scenario it would reach out to my MCP server and it would get back a textual response which is obviously suboptimal. So let's say I do want to get some something better. So now I can use existing MCP primitives like a resource and now return HTML. And I can take that HTML and since Cloud supports MCP apps it can turn it into an interactive application of the best soundtrack in the world. And what if you wanted to be really interactive, right? This is nice because it shows the best soundtrack in the world. What if I want to favorite one of the songs there? I want interaction. I want communication between the

</details>

**Ido Salomon**: 所以，当用户在界面上点击那个“收藏”按钮时，**MCP 应用程序规范实际上将这套交互流程标准化了**。

这里发生的变化是，当用户点击按钮时，应用程序并不是直接向自己的后端服务（比如 Spotify 的后端）发送请求，而是向当前的宿主环境（Host）发送一条消息：“嘿，用户点击了某个按钮。请对此进行处理。我建议你调用 Spotify 的 MCP 服务端中所提供的对应工具。”

此时，决策权回到了宿主环境手中。宿主环境能够全权决定下一步该怎么做，从而牢牢掌控了业务流的主导权。在这个例子中，宿主环境可以选择直接调用对应的收藏工具。而 **MCP 应用程序规范的作用就是标准化这一系列的交互通信流**。

<details>
<summary>Original English</summary>

**Ido Salomon**: app and the host. So, when the user clicks on the favorite button, MCP apps actually standardizes this flow. So, instead of the app sending a message to to the backend, to Spotify's backend, it's actually sending a message to the host saying, \"Hey, user clicked a button. Do something with it. I recommend you to call a tool in Spotify's MCP server.\" And the host decides what to do. The host keeps this control of the flow. In this case, the host can decide to actually call the favorite favorite tool. And MCP apps standardizes this flow.

</details>

### 交互与架构深度解析

**Adi**: 好的，俗话说眼见为实。那么让我们直接来看一个在 Claude 里的具体示例。

假设我是一名产品经理，我想要快速了解一下我们用户漏斗（Funnel）的最新状态。在过去，我会去问 Claude：“目前的漏斗状态如何？”

在几个月前的旧世界里，我得到的会是一个纯文本的回复。假设我们的底层分析服务是 **PostHog**，Claude 会请求 PostHog 服务端，获得文本形式的漏斗数据。虽然这些数据在事实上是完全正确的，但在实际使用中它几乎没有什么价值。我的意思是，我要怎么快速地从这一大堆冰冷枯燥的数据里一眼看出当前的业务现状？我必须耐心地去阅读，而这正是我最不想做的事，这真的很令人头疼。

但幸运的是，因为现在 PostHog 服务端和作为宿主的 Claude 都已经支持了 MCP 应用程序规范，我现在只需要简单地对它说：“展示给我看（Show me）。”

现在，我们不再会得到那一长串让人望而生畏的文本块，而是可以获得一个极其直观且实用的**交互式微件（Interactive Widget）**，这与你在 PostHog 官方后台里看到的体验完全一致。有了这个微件，你只需要扫一眼，就能对当前的业务状态了如指掌。

正如你所看到的，这个微件带有 PostHog 标志性的品牌设计。所以，你其实是在 ChatGPT 或 Claude 内部，直接享受到了 PostHog 原汁原味的产品体验。

但这还没完。正如我们所说，MCP 应用程序协议本质上是一个**双向交互式的通信协议**。所以，我不仅能够直观地看到并进行交互，我还可以做更多事情，比如让它为我解释一下“什么是漏斗？”——因为我可能甚至都不知道漏斗的具体定义。

此时，AI 依然不需要扔给我一大堆文字解释。借助于 MCP 应用程序的支持，它可以从 Claude 那里直接以生成式 UI（Generative UI）的形式呈现答案。它会在对话中实时以流式（Streaming）的方式渲染 HTML 内容。通过这种方式，我能获得极其生动直观的学习和交互体验。

这不仅在视觉上非常美观，帮助我更好地理解概念，而且它是**完全可交互的**。当我们提到“可交互”时，意味着在界面上的每一次点击，都能帮助我直接与宿主环境进行沟通。

比如，我想深入了解漏斗中某一个具体步骤的数据，我可以直接在图表里点击那个步骤。因为它是基于 MCP 应用程序规范构建的，它能直接将我的点击操作转化为 Prompt 发送给背后的 AI 模型：“请为我详细解释一下这个具体的步骤。” 这样一来，我就能不断向前推进我的工作流。这就是一个非常典型且直观的实际应用场景。

那么，它的底层架构到底是如何工作的呢？

首先，一切都始于我们的输入（Prompting），我们在对话框中输入请求。我们向 AI 询问漏斗的数据，这时一个**工具调用（Tool Call）**被发送了出去。因为我们的 MCP 服务端支持 MCP 应用程序，所以这个工具调用实际上是与某一个特定的**资源（Resource）**绑定在一起的。

如果你去看底部的代码，其实它非常简单，就是一个带有一些特定前缀的资源。我们获取这个资源，代码逻辑非常直观，仅仅是把带有 HTML 数据的资源返回，这就完成了服务端的逻辑。

接下来，这个资源会被宿主环境（Host）所解析和消费。在实际开发中，这些资源为了优化体验通常会被提前预加载。不过你也可以简单地把它想象为是实时获取并解析的。这部分 HTML 内容会被传递给同样支持 MCP 应用程序的宿主。

在宿主前端，如果你看 **MCP UI SDK**，它本质上就是一个 React 组件或者 Web Component。它能够接收这个资源，并接收一个**回调函数（Callback）**——这正是我们实现前面提到的双向通信协议的关键。随后，宿主会在一个安全的**沙箱（Sandbox）**中将其渲染出来。

所以，这绝非单纯的视觉渲染，你完全可以进行点击操作。那么，点击时会发生什么呢？

当我们点击界面上的元素时，它会通过那个回调函数，将事件一路向上传递。AI 模型接收到这个点击事件后，可以根据事件内容，决定是发起一个新的工具调用、请求一个新的资源，还是执行其他任何能帮助用户完成智能体工作流（Agentic Flow）的操作。

<details>
<summary>Original English</summary>

**Adi**: Okay, so seeing is believing. So, let's see an example from Claude. Yeah. Uh so, let's say that I'm a product manager to understand the status of my funnel. So, I would go to Claude and I would ask what's the status? In the again, old world of a few months ago, uh I would get back the textual response. Let's say that it's PostHog. So, it reached out to the PostHog server, got back the textual response. It's factually correct, but it's useless. I mean, how do I even take that and understand quickly what's going on? I would have to read, which I don't want to do. Uh and it's pretty challenging. Uh but luckily, because both PostHog server and Claude as a host support MCP apps, I can just say, \"Show me.\" And now, instead of getting that block of text, I can actually get something useful, uh which is this interactive um widget that you would get, you know, on the PostHog uh uh server. And when you have that, you can at a glance see what's going on. And as you can see, it's branded PostHog. So, you're actually getting the PostHog experience within ChatGPT or Claude, etc. Uh but it doesn't really end there. As we said, MCP apps is also like an interactive photo call. So, not only can I see and and interact with it, I can also do stuff like ask him to explain what a funnel is. I might not even know that. So, again, instead of getting that huge wall of text explaining what a funnel is, I can just get this generative UI answer from Claude, which uses MCP apps. It streams like the HTML inside, and now I can get this nice interactive experience of learning. And not only is it visually nice and helps me understand, but it's also fully interactive. And when we say interactive, it actually means that clicking it would help me communicate with the host. So, let's say that I want to understand like a particular step in the funnel. Uh I just go and I click on it, and since it's an MCP app, it can send a prompt back to the uh model and say, \"Okay, explain this specific step to me.\" And I can advance the flow. Uh so, this is a like an example of of how that uh looks. So, how does it actually work? If you look at the architecture of it, uh so, we started by prompting. So, we type something in. Uh we asked for the funnel information. A tool call went out. Since our server supports MCP apps, that tool call is actually linked to a resource. And if you look at the uh code here, then, you know, it's it's it's just a resource with a uh some prefix. Uh we take that. It's pretty simple code. I could just add the but it's still the the resource with the HTML, and you're done. Uh that resource is then um consumed by the host. In practice, it's usually consumed beforehand, like it's preloaded. Uh but imagine that it's just consumed in real time. That same HTML then passed to the host that also supports MCP apps. MCP apps basically if you look at the MCP UI SDK, just a React component or a web component that just accepts that resource plus a callback which is how we implement that communication protocol as I said earlier. And renders it in a sandbox. So, like we said, not only is it presentational, I can click. So, what happens when I click? So, we click on it, it sends back through that callback the event all the way up. The model takes that event and then it can send out a tool call or call a resource or anything else that's completing the agentic flow.

</details>

### 智能体网页的哲学愿景

**Ido Salomon**: 这一架构实际上为整个互联网带来了一种全新的哲学和全新的愿景。

未来，我们不再需要将互联网视作一个个必须通过浏览器打开的标签页（Tabs）或独立的服务。相反，我们正在通过我们**专属的个人 AI 助理（Personal Assistants）**来消费整个互联网的价值。

这到底意味着什么？

这意味着，如果我想去完成某项任务，例如策划一场结婚纪念日活动。在过去，我必须在浏览器里同时打开 20 个标签页，然后竭尽全力向每一个独立的服务去表达和传递我的意图。这意味着我必须去和每一家公司的后台系统或用户界面进行繁琐的交互。为了策划一个纪念日，我不得不分别向 **Google Calendar**、**Amazon**、**Booking.com** 传递我的意图，而且我还得在 Booking 和 Amazon 之间反复跳转。

最关键的是，**这些网页展示给我的 UI 中，有 99% 的内容是我根本不需要的**。因为这些 UI 根本不认识我，它们完全没有任何关于我个人的上下文信息（Context）。

但如果，我们能够把这些复杂的用户界面**打碎成一个个最基础的“UI 原子”（UI Atoms）**呢？

然后，让这些 UI 原子直接被我的个人 AI 助理进行动态的重新组合与呈现。因为我需要的不是那些庞杂冰冷的原始网页，我需要的仅仅是那些能帮我解决问题的 UI 原子本身。

如果能够实现这一点，让我的 Claude、ChatGPT 或者 OpenCloud 能够直接通过 **MCPUI** 来使用这些 UI 原子，我们就能获得极其流畅的体验。

我的主动式 AI 助理会告诉我：“我知道你即将迎来一个纪念日。而且，它不会生硬地展示来自 Google Calendar 的冷冰冰的数据，而是直接在当前对话中渲染出一个 Google Calendar 的交互小卡片。”

对于用户而言，这非常棒，因为我熟悉 Google Calendar 的交互，而且我信任 Google 的服务。对于 Google 而言也同样是一件好事，因为它们在非自有平台上依然**保留了其品牌标识与品牌个性**。对于 AI 宿主平台同样极具价值，因为他们完全不需要自己去从零开发这些复杂的功能。

这种合作模式甚至能走得更深。比如当我在与 Amazon 交互时，Amazon 不需要被降维成一串纯文字的商品列表。我能直接在聊天框里看到具有 Amazon 品牌设计的界面。我能在完全不离开我的 AI 助理的前提下，直接在对话框里完成整个购物和支付流程。

**这就是“智能体网页”（Agentic Web）的本质**。这正是我们未来消费和使用互联网的方式。因为我的 AI 助理拥有最完整的、关于我个人的上下文。它自己知道什么时候应该去调用 booking.com 的地图服务，而我作为用户，甚至完全不需要去关心底层到底调用了哪家服务，对吧？

因此，我们很快就会迎来这样一个时代性的转变：传统的网站将逐渐蜕变、解构成一个个微小的 UI 原子，并无缝嵌入到用户的个人 AI 助理中。

随着这一转变，**全新的交互思维（Interaction Mindset）**也将应运而生。因为当我在 Shopify 的 MCP 应用中点击某个按钮时，Shopify 将不再控制我的整个用户旅程，控制权转移到了 AI 宿主手中。没有任何一家单一的应用程序能够像以前那样完全绑架和控制用户的整个行为路径。Amazon 将无法追踪和监控我的全局浏览行为，因为所有交互都将通过聊天界面进行，这带来了极佳的审计性（Auditability）与隐私保护。

**MCP 应用程序规范通过定义三层控制权（Three Levels of Control）将这种全新的用户旅程交互标准化了**。应用程序可以通知聊天框有事件发生，也可以请求聊天框运行某段 Prompt，然后将后续的执行权完全交还给聊天框。

MCP 应用程序将这种交互流程变成了标准。这就是未来我们在应用、聊天界面和用户之间将会看到的**全新软件交互流（New Software Flow）**。

在刚刚过去的 2026 年，我们在标准化 MCP UI 方面取得了惊人的进展。而接下来的时间里，它将加速成为全球公认的用户界面交互标准。

<details>
<summary>Original English</summary>

**Ido Salomon**: And this architecture actually brings a new philosophy or a new vision to the web. So, instead of us thinking of the web as tabs or services that we need to consume using a browser, we're now consuming it using our own personal assistants, right? What does it mean? It means that if I want to accomplish a task, for example, plan a um anniversary. So, up until now I had to open 20 tabs in the browser and I had to try to convey my intent to each of those services. And by saying conveying my intent, it means that I have to interact with the dashboards or the UIs of those companies. So, just to plan an anniversary, I need to convey my intent to Google Calendar and Amazon and Booking and Booking again and Amazon again and all and I don't need 99% of the UI that is shown there because this UI doesn't know me. It doesn't have the context on me. What if we could just take these UIs and just break them into atoms? And those atoms can be composed by my own personal assistant, right? Because I don't need the the UI. I need those atoms. So, if we can take these atoms and have my cloud or ChatGPT or OpenCloud just use them using MCP UI, we can have this flow. So, my proactive assistant can say, \"Yeah, I know. I see that you have an anniversary coming and instead of just showing me data from Google Calendar, it can display a Google Calendar chunk. Now, for me it's good because I know Google Calendar, I trust Google. For Google it's good because it maintains their brand and identity and for the host it's good because they don't need to develop these capability themselves. And it goes even deeper because if I'm interacting with Amazon, instead of Amazon being reduced to just a list of items or or text, I can see Amazon. I can I can know that this is this is Amazon and I can complete my entire flow without even leaving my assistant. And this is the agentic web. This is how we're going to consume the web because my assistant will have the context on me. It It will know to pull the the map from booking.com. I don't need to know that, right? So, this is going to be the shift that we're going to see very soon where websites are going to shift into small chunks of UIs inside inside personal assistants. Um [snorts] and with that come new interaction mindset because um if I click on something in the Shopify's MCP app, then Shopify doesn't control my journey anymore. The host does. Um and no application will control the user journey anymore. So, Amazon won't be able to know to see my flow. It everything will go through the chat for auditability. Um and MCP apps actually standardizes it by defining this three level of control over the user journey. So, an app can notify the chat that something happened or an app can actually ask the chat to run a prompt and and releasing all responsibility to the chat. So, MCP apps actually standardizes it and this is the new software flow, the new flow of interaction that we're going to see between applications, the chats, and the users. Um in 2026, we had we had an amazing year of standardizing MCP UI and 2026 is going to be the year where it's going to be a global standard for UI.

</details>

### 协议演进与未来路线图

**Adi**: 是的，没错。

<details>
<summary>Original English</summary>

**Adi**: Yeah.

</details>

**Ido Salomon**: 但它依然在高速演进中，目前有非常多的工作正在推进。即便在过去的几个月里，社区也已经贡献和提出了许多新的特性与提案。

所以，大家现在依然有非常充足的时间和空间，去加入并共同影响这一协议的未来走向。

你们可以直接访问 **X-apps**。官方的 SDK 和协议规范都托管在那个仓库下。它是隶属于官方的模型上下文协议（Model Context Protocol）开源组织之下的。我们稍后会展示一个 QR 码，所以大家现在不需要特意去拍照记录。

使用 X-apps 规范开发最酷的地方在于，因为该规范是由我们直接负责日常维护和迭代的，所以**规范中的任何最新改动都会立刻同步反映在 SDK 当中**。也就是说，如果你使用了我们的 SDK，你就能自动在第一时间获取到所有最新发布的特性。

这是我们目前正在重点跟进的一些议题。非常欢迎大家随时加入进来，提交你们的贡献。

那么，下一步的路线图是什么？我们正在规划一系列非常激动人心的新特性。

第一个我们被社区频繁问到的功能是**可复用视图（Reusable Views）**。

像 **Autodesk** 这样的公司，它们拥有非常庞大且繁重的专业应用（例如要在界面中实时进行复杂的 3D 渲染）。它们显然不希望在聊天会话中每一次交互都去从头重新渲染整个 3D 场景，因为这不仅极其耗时，而且效率非常低下。

在最初的 MVP（最小可行性产品）阶段，我们只能采用这种低效的重绘方式。但目前，我们正在积极探索一种新的设计：或许我们可以从服务端传递某种特定的**唯一标识符（Identifier）**，从而帮助 AI 模型直接在已有的视图上进行局部增量更新，而不需要重新创建视图。

此外，另一个正在推进的重要方向是……

<details>
<summary>Original English</summary>

**Ido Salomon**: But, it's still evolving. There's a lot of stuff going on. Even in these past few months, these are some of the things that are already in or already contributed or proposed uh, by the community. Uh, so you still have a lot of time and a lot of room to influence how this future will look like. Uh, so you can go to X apps. Uh, that's the official SDK and spec is also hosted there. It's under the official model context protocol uh, repository. There will be a QR code later. Uh, so you don't have to to uh, to uh, photograph it. Uh, and also um, the the cool thing about using X apps in particular is that because it's maintained by us directly, uh, all changes to the spec are immediately uh, reflected in the SDK. So, if you use that SDK, then you automatically get all the new stuff out of the back. Uh, these are some of the issues that we have. So, please feel free to come and uh, contribute. So, what's next? Um, there's a bunch of stuff coming up. Uh, the first thing uh, that we get a lot of uh, uh, of asked for is kind of reusable views. So, if you have uh, um, companies like Autodesk that have really heavy apps like they have in, you know, the entire 3D render there. They don't want to keep re-rendering that over and over again because it just it takes time, it's inefficient. Uh, that is the way that we had to do it uh, for the MVP. But we are working on thinking of maybe we can pass some identifier from the server uh, in a way that would help the model actually keep updating the same view. Uh, the other way to do this is

</details>

**Adi**: 另一个方向是**应用工具（App Tools）**。如果你听说过 **Web MCP**——这是 Google 提出的一套关于智能体如何与 Web 视图进行交互的规范。在 MCP 应用程序中，我们其实已经将它标准化为了 **App Tools**。

在之前展示的流程中，主要是用户在应用界面中进行操作，然后由应用向宿主发送数据。但是，如果反过来，宿主环境或者聊天界面想要主动向应用发送指令呢？

比如，用户在对话框里写下一句话：“请帮我把这个表单填了。” 随后聊天界面就会自动为用户填写应用卡片中的表单。为了实现这一目标，MCP 应用程序对这种双向控制流进行了标准化，我们称之为**视图工具（View Tools）**。这一特性目前已经写入了技术规范中，并且很快就会正式发布。

同时，我们也在深入研究**生成式 UI 光谱（Generative UI Spectrum）**。

在光谱的一端是**预定义 UI（Predefined UI）**。这就是目前的 MCP 应用程序，它就像一个黑盒沙箱（iframe），能够完整稳定地渲染像前面例子中 Spotify 播放列表那样的特定 UI。

但是在这个光谱中，我们也支持其他不同的技术路线，例如**声明式 UI（Declarative UI）**，比如基于 JSON 的渲染（JSON Render）或 **A2UI**。在这些规范中，应用服务端仅仅返回关于如何构建用户界面的结构化指令，而具体的 UI 渲染工作则完全交给宿主聊天界面来完成。

在光谱的最另一端，则是**完全生成式 UI（Fully Generative UI）**。

如果你了解 Claude Artifacts（或类似功能），MCP 应用程序实际上对于 UI 的具体生成方式是完全保持中立（Agnostic）的。你可以直接让 Claude 为你实时生成一个全新的用户界面，而这在底层其实正是基于 MCP 应用程序协议实现的。换句话说，虽然它表面上呈现的是生成式 UI 的体验，但其底层的通信支柱依然是 MCP 应用程序。我们目前正致力于与这些不同标准的互操作性（Interoperability）。

就在前几天，我们刚刚发布了一份技术指南，详细阐述了 **A2UI、生成式 UI 标准以及作为行业标准的 MCP 应用程序之间如何实现互操作**。比如，一个服务端应该如何编写 A2UI 指令并将其发送给 Gemini，同时又能够将其无缝包装成一个 MCP 应用程序发送给 ChatGPT。

MCP 应用程序的一大核心优势在于它**无处不在的支持度**。它几乎可以在任何主流平台上运行。你只需要编写一次，它就既能运行在像 **LibreChat** 这样的开源客户端中，也能直接无缝运行在 ChatGPT 当中。你在两个不同的平台上看到的，完全是基于同一套代码库渲染出来的用户界面。这真的非常酷。是的。

<details>
<summary>Original English</summary>

**Adi**: Um, app tools, which is something uh, if you've heard of web MCP, which is Google standard of how agents will interact in with web views. So, in MCP us, we actually standardize it into app tools. So, up until now we saw the flow where users does something in the app and the app talks to the host. But what if the host or the chat wants to speak to the app? If the user writes something, uh, fill out this form for me and the chat will fill out the form for the user. So, MCP apps actually standardizes this this flow which we call view tools. That's actually that's in the spec right now. It's also it's going to be released very soon. And we're working on this generative UI spectrum where you have predefined UI. That's MCP apps. That's like the black box iframe that renders all trace UI in that example. But you also have other things on this spectrum like declarative UI like JSON render or A2UI. These specs that say yeah, the the app just returns an instructions on how to build the UI, but the chat will actually build the UI. And you have fully generative UI on the other end of the spectrum. And if you know cloud apps, yeah, MCP apps is agnostic to the way the UI is generated. And if you know cloud apps imagine feature where you can just ask cloud to generate a UI for you. That's actually based on MCP apps. So, this is an MCP app behind the scenes, but it supports generative UI. So, we're working on interoperability with those other standards. And actually just a few days ago we released a guide on how to do A2UI versus a generative UI standard and MCP apps which is the standard. How to do interoperability. How can a server can write A2UI and ship it to Gemini, but also wrap it as an MCP app to ship to ChatGPT and vice versa. An MCP app is supported everywhere. So, it can run everywhere. If you build it once, it runs in Libra Chat which is an open source MCP app supported in ChatGPT. That's the same app that you're seeing the same code base that runs in in both which is pretty cool. Yeah. Yeah.

</details>

### 分发革命与参与共建

**Ido Salomon**: 这绝不仅仅是一项单纯的技术升级或是一个很酷的新特性。这代表了**一种全新的应用分发方式（An entirely new way to distribute applications）**。

如果我们把时间往回拨几个月，当时有人统计过，**ChatGPT 单个平台就拥有高达 8 亿的周活跃用户**，这已经占到了全球总人口的 10%。这简直是不可思议的奇迹。

如果对比传统的万维网（Web），互联网大概花了整整 13 年的时间才积累到同样规模的用户量。

而如果看看最近这几个月的发展，我们实际上见证了用户量在极短时间内暴增了超过 10 亿。这意味着我们现在所面对的，是 **Apple App Store 刚发布时总潜在市场（Total Addressable Market）的整整 170 倍**。

所以，MCP 应用程序真的已经是无处不在了。如今在 Claude、OpenAI 等大厂的客户端里，你都可以直接使用它。

那么，对于开发者来说，应该如何着手开始呢？

你可以直接去克隆我们的示例，去访问 **X-apps** 仓库。如果你是客户端/宿主平台的开发者，也可以直接去阅读 X-apps 的文档或者访问 MCP 协议的官方网站。

<details>
<summary>Original English</summary>

**Ido Salomon**: So, this isn't just a technology or a cool feature. This is an entirely new way to distribute applications. So, if you look just a few months back then someone said that ChatGPT in particular has 800 million weekly users which is 10% of the entire world population. That's insane. So, if you think about the web in general, it took around 13 years to get to that number of users. So, if you look at that and you think that in the last few months we actually had a growth of over 1 billion. Just that we have like 170 times the total addressable market of the Apple App Store when it launched. So, MCP apps are everywhere. So, actually to list them, it is called cloud, open AI, etc. It's already there. So, how do you get started? You can clone those you can go to the X apps. As a host also go to X apps or the MCP website.

</details>

**Adi**: 欢迎大家访问我们的官方仓库。

<details>
<summary>Original English</summary>

**Adi**: Please visit the official repo.

</details>

**Ido Salomon**: （笑）

<details>
<summary>Original English</summary>

**Ido Salomon**: [laughter]

</details>

**Adi**: 访问 **X-apps 仓库**以参与到我们的共建中来。谢谢大家。

<details>
<summary>Original English</summary>

**Adi**: The X apps repo to get involved. And yeah.

</details>

**Ido Salomon**: 让我们一起拥抱全新的网页生态吧，它真的棒极了。有了 MCP 应用程序，你只需要编写一次代码，就能让它在世界的任何一个角落完美运行。

<details>
<summary>Original English</summary>

**Ido Salomon**: So, embrace the new web. It's awesome. With MCP apps you can write once and run it everywhere.

</details>

**Adi**: 未来的前景一片光明。虽然我们现在还不能完全说达到了“Travis”式的完美高度，但有了 MCP 和 MCP 应用程序的加持，我们已经离那个理想的未来无比接近了。

<details>
<summary>Original English</summary>

**Adi**: And the future is looking bright. Not quite Travis, but with MCP and MCP apps we're close.

</details>

**Ido Salomon**: 稍后欢迎大家随时来找我们面对面交流。

<details>
<summary>Original English</summary>

**Ido Salomon**: And come talk to us afterwards.

</details>

**Adi**: 好的，非常感谢大家。

<details>
<summary>Original English</summary>

**Adi**: Yeah, thank you.

</details>