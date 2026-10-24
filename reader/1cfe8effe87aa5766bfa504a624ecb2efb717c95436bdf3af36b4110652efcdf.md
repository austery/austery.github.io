---
author: AI Engineer
date: '2026-06-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ghJmWQCIHRM
speaker: AI Engineer
tags:
  - web-mcp
  - browser-automation
  - api-design
title: Agent-Ready Web：通过 WebMCP 为 AI 代理打造专属浏览器标准
summary: Google Chrome 团队的 Tara Agyemang 介绍了 WebMCP（Web Model Context Protocol），这是一项处于早期预览阶段的新型 Web 标准。它允许开发者通过声明式和命令式 API 为浏览器端的 AI 代理注册专属工具，让复杂的网页交互自动化，从而大幅简化用户操作，使现代网页不仅为人类服务，也为 AI 代理做好准备。
insight: ''
draft: true
series: ''
category: frontend
area: tech-engineering
project: []
people:
  - Tara Agyemang
companies_orgs:
  - Google
  - DeepMind
products_models:
  - Chrome
  - Gemini
media_books: []
status: evergreen
---
### Web MCP 背景与挑战

**Tara Agyemang**: 大家好，能清楚听到我的声音吗？好的，太棒了。让我们开始吧。所以，我们今天将要稍微聊一聊 **Web MCP**。出于好奇问一下，在座的有没有人已经体验过 Web MCP 了？只有少数几位。好的，很棒。这少数几位朋友你们已经抢占了先机，但对于在场的其他人，我们将更深入地探讨它的背景、它是如何运作的以及它能做些什么。我叫 Tara，我是 **Google** Chrome 团队的一员。我是一名开发者关系工程师（Developer Relations Engineer），今天我和几位 Chrome 团队的同事，以及 **DeepMind** 团队的人一起在这里。所以，如果你对 Web、AI 以及这两者的交集有任何想法，我们非常乐意在活动结束后在 DeepMind 的展位周围与大家交流。这也是我近期关注的重点。那么，我们就进入正题吧。

<details>
<summary>Original English</summary>

**Tara Agyemang**: Hello, hello. Hello, can you hear me okay? Okay, cool. Let's get started. So, we are going to be talking a little bit about Web MCP. Has anybody, just out of curiosity, has anybody already played around with Web MCP? Only a few people. Okay, great. Those few people, you have a bit of a head start, but for everyone else, we'll be going into a bit more of the background, how it works, what it does. So, my name is Tara. I am part of the Google Chrome team. Um I'm a developer relations engineer, and I'm here with a few of my colleagues from Google Chrome, alongside the DeepMind team, too. So, we'll be really interested to talking to you afterwards around the DeepMind booth, if you like have thoughts around web and AI and the intersection between the two. That is where my focus is these days. So, let's get into it.

</details>

**Tara Agyemang**: 过去几十年，我们一直在为人类的操作和人类的视觉构建万维网，并且一直试图为此进行优化。但如今，使用 Web 的不再仅仅是人类。我们有 AI 代理（Agents）在代替人类使用网页，并且我们看到越来越多代理正在使用网络。但问题是，为了在我们构建的网站上执行简单的操作，代理不得不做大量繁重的工作。

<details>
<summary>Original English</summary>

**Tara Agyemang**: The let's say past few decades, we have been building the web for human actions and human eyes, and we've been trying to optimize for that, but these days, it's not just humans that are using the web. We have agents using the web on the human behalf, too. And we are seeing an increasing number of agents using the web. But, the problem is the agents are having to do so much work to do simple actions on the sites that we've built.

</details>

### AI 代理浏览网页的现状痛点

**Tara Agyemang**: 给大家举个例子，这是我自己编写代码构建的一个网站，它是一个用于售票的演唱会网站。我们在侧边栏这里有一个 **Chrome** 面板里的 **Gemini**。假设你访问了这个网站并输入了这样一个提示词：你想买两张去 Afro Beats Festival 的门票。你向它提供了详细信息。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And just to give you a bit of an example of this, this is a a website that I've built coded, and it's a concert website for selling tickets for concerts. And we have Gemini in Chrome panel on the side here. And let's say you come along to this website and you've typed this prompt. You want to buy two tickets to the Afro Beats Festival. You've given it the details.

</details>

**Tara Agyemang**: 为了实现这个目标，AI 代理必须做海量的工作。所以，它很可能会去解析 HTML，因为通常代理会遍历整个 DOM 树仅仅是为了理解你的页面上到底在发生什么。然后，它会查看无障碍树（Accessibility Tree）来理解你 HTML 页面的结构。接着，它可能会对页面进行截图，分析那些在 HTML 和无障碍树中无法看到的各种元素。然后再下一步，它可能会去测量它需要向下点击多远、横向点击多远、它需要点击的具体元素的确切位置在哪里，最后它才会去点击那个元素。正如你们所见，这个过程相当漫长，而且可能非常脆弱。我甚至都不想去猜测你为了完成这套操作刚刚消耗了多少个 Token。这肯定是个巨大的数字。经历了所有这些步骤之后，也许你的广告正好在页面顶部加载了出来，把你所有的内容都向下推了，导致你的 AI 代理最终甚至连正确的位置都点不到。

<details>
<summary>Original English</summary>

**Tara Agyemang**: The AI agent has to do so much work to make this happen. So, it'll probably look at the HTML because usually the agents will pass the entire DOM just to understand what's happening on your page. Then it will look into the accessibility tree just to understand the structure of your HTML page. Then it maybe it'll take a screenshot of the page, analyze all the different elements that couldn't see in the HTML and the accessibility tree. And then maybe it will measure how far down it needs to click, how far across, where the exact element that it needs to click, and then it'll click that element. And as you can see, this process is quite long. It can be brittle, and I don't even want to guess at how many tokens you probably just used trying to do this. It's probably a lot. And then after all that, maybe your ad has loaded at the top of the page, pushed all your content down, and your AI agent couldn't even click the right place in the end.

</details>

### WebMCP 的前置条件：无障碍与性能

**Tara Agyemang**: 确实有太多需要考虑的问题了，但在我们深入探讨这项拟议的 Web 标准之前，值得一提的是，通过首先优化 Web 的基础建设，你就能取得很大成效。让你的网站对所有人都是无障碍的（Accessible），这就意味着它默认也是对 AI 代理无障碍的。所以，如果你能优化你的语义化 HTML（Semantic HTML），如果你能专注于稳健的无障碍标准，如果你能提升页面性能、让它加载得非常快、考虑到那些核心网页指标（Core Web Vitals），并且在你网站中提供非常优秀的用户体验流程，那么你在打造一个“为代理准备好的网站”（Agent-ready website）这条路上就已经成功了一半。只有当这些基础都已经落实到位，开始考虑 Web MCP 才有意义。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, there's so much to think about, but before we go into this proposed web standard, it's worth mentioning that you can do so much by improving web foundations first. So, making your site accessible for everyone makes it accessible to AI agents by default. So, if you improve your semantic HTML, if you focus on robust accessibility standards, and if you improve your page performance, make it load really quickly, think about those core web vitals, and then improve really good user experience flows through your site, you're already halfway to getting an agent-ready website. And it's only once you have those in place that it makes sense to start thinking about Web MCP.

</details>

### 什么是 Web MCP 

**Tara Agyemang**: 如果你还不太了解，**Web Model Context Protocol (Web MCP)** 是一项拟议的 Web 标准，它赋予你将网站的功能定义为供 AI 代理使用的结构化工具的能力。你可能听到过有人将其比作是 AI 代理交互中的 **USB-C 接口**。这是因为，你相当于给了 AI 代理一份它可以使用的工具和能够执行的操作的“菜单”，而不是让任何代理去瞎猜你的网站到底是干嘛的。也正因如此，我们看到 WebMCP 显著提升了代理浏览你网站时的性能和可靠性。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, if you're not already aware, the Web Model Context Protocol is a a proposed web standard, and that gives you the ability to define your site's capabilities as structured tools for your AI agents to use. And so, you might have heard references to this as the USB-C of AI agent interactions. And that's because it instead of any agent guessing what your website does, you're kind of giving the AI agent a menu of tools that it can take of tools that it can use and actions that it can take. And so, because of this, we're seeing that WebMCP significantly improves the performance and the reliability of agents navigating your website.

</details>

### Web MCP 实战：迷宫游戏演示

**Tara Agyemang**: 让我们来看看它的实际操作。希望今天 Gemini 能对我好一点。这是一个由我们 Chrome 开发者关系团队（Chrome DevRel）构建的迷宫逃脱游戏。在侧边这里，我们有一个 Chrome 扩展程序。我稍后会给你们看它的链接。这个是模型上下文工具检查器（Model Context Tool Inspector）。我们正在使用这个，这是一个存活在你侧边栏里的标准的 Chrome 扩展程序，它列出了它在你网站上找到的所有工具。目前，它只能看到一个工具，那就是“开始迷宫游戏”（start maze game）工具。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, let's see it in action. Hopefully, Gemini treats me well today. So, this is the maze escape game built by our team in Chrome DevRel. And just on the side here, we have a Chrome extension. Um I'll show you a link to that afterwards. But, this is the model context tool inspector. And so, we're using this This is a standard Chrome extension extension that lives in your side panel, and it lists out all the tools that it finds on your website. So, at the moment, it only has one It can only see one tool, and that's the start maze game tool.

</details>

**Tara Agyemang**: 在最底部这里，它提供了两种与页面交互的选项。你可以像普通用户那样通过输入提示词让 AI 代理进行交互，或者你也可以在底部直接调用工具，但我们今天先不看后者。这个特定的迷宫游戏其实非常独特，因为你实际上无法通过在用户界面（UI）上点击来浏览它。你只能通过 AI 工具来使用这个应用。所以，让我们在这里开始一个全新的迷宫游戏。你还可以在侧边选择你的模型。我们这里就继续使用 Gemini 1.5。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And then at the bottom down here, it gives you two options to interact with the page. So, you can interact via a prompt like a user would prompt normally via the AI agent, or you can call tools directly at the bottom, but we won't be looking at that one today. So, this specific maze game is actually more unique in that you actually can't browse it by clicking around the UI. You can only use this app with the AI tooling. So, let's start a new maze game here. You can also choose your model on the side. So, let's stick with the Gemini 1.5.

</details>

### 代理如何调用工具

**Tara Agyemang**: 你会发现在底部，当你发送一个提示词时，它会给你反馈所有的信息。所以，这条新的要求开始新迷宫游戏的提示词发出去后，AI 代理（在我们的例子中是 Gemini）调用了那个名为 `start game` 的工具。工具本身返回了这些信息，然后 AI 读取了它并给了我这个回复。现在我们有了我们的迷宫，你会注意到在这个页面上，我们在这个页面的作用域内有了一系列新工具，而之前的页面只有一个工具。在这个页面，我们有一堆工具来帮我们导航穿过迷宫。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, you'll see that at the bottom, when you send a prompt, it gives you all the information. So, the new prompt prompt to start a new maze game, and the AI agent, Gemini in our case, has called that tool start game. The tool itself has returned this information, and then the AI has read that and given me this response. And so, now we have our maze, and you'll notice that on this page, we have a bunch of new tools in the scope of this page, whereas the previous page only had that one tool. This page, we've got a bunch of tools to help us navigate the maze.

</details>

**Tara Agyemang**: 在这个迷宫里，你可以使用东南西北这四个方向来移动。你可以“查看”一下，看看你在迷宫中的什么位置，以及哪些方向是开放的。然后，在导航这个迷宫时，你还可以捡起物品、丢弃物品或使用物品。如果我输入一些提示词，我可以让它先向下移动，然后向右。AI 代理应该会读取我的提示词，将它与特定的工具匹配——在这个例子中是 `move`（移动）工具。它提取了我说的向下和向右的方向，将其映射到了东南西北的方向体系中，然后把这个发送给我们在页面上注册的那个工具，接着就成功向下和向右移动了。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, in this maze, you can move around with the north, south, east, west directions. You can look to see where you are in the maze and which directions are open. And then, you can pick up items, drop items, use items as you navigate this maze. And if I pop in some prompts, I can see that I can move down, then maybe after that, then right. The AI agent should use my prompt, match it to the specific tools, so in this case, the move tool. It's taken my direction of down and right, matched that to the north, south, east direction, and sent that off to the tool that we have registered on this page, and then it's moved it down and right.

</details>

**Tara Agyemang**: 因为它是一个 AI 代理，所以它能理解很多不同的东西。比如，我可以直接说：向右，向上，或者再向右一次。我们试试这个。AI 代理看到了“uh”发音代表右边，把这映射为方向，然后使用这些信息调用了移动工具。并且因为它是 AI 代理，它可以不断地重复调用同一个工具，直到它认为完成了需要做的事情。所以我甚至可以说：“完成这个迷宫”（complete the maze）。然后 AI 代理就会利用所有可用的工具，不断在迷宫里移动去拾取物品，并在需要时使用物品，因为它拥有可用工具里的所有信息。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And because it's an AI agent, it can understand a whole bunch of different things. So, I could just say, right, up, maybe right again. Let's try that. And so, the AI agent has seen that uh sounds for right, mapped that to the direction, and then called the move tool with those information. And because it's an AI agent, it can just keep repeating the same tool tool calls until it thinks that it's done what needs to be done. So, I could even say, complete the maze. And then the AI agent should use all the tools available to just keep moving around the maze to pick up items, to use the items when it needs to because it has all the information in the tools available.

</details>

**Tara Agyemang**: 这个特定的提示词并不是最高效的，所以有时候你会看到它一路往回走到起点，然后再重新往前走。但是，你对提示词优化的越好，代理就越知道如何以最高效的方式完成迷宫。比如，如果你只说：“出口在右下角”，它在生成到达那个方向的指令时就会更加高效。我在这里就不继续演示这个了，因为完成这个迷宫可能需要相当长的时间。

<details>
<summary>Original English</summary>

**Tara Agyemang**: This specific prompt was not the most efficient, so sometimes you'll see it'll go backwards all the way to the start and then go forwards again. But, the more that you refine the prompt, the better the agent knows how to complete the maze in the most efficient way. For example, if you just say, the exit is in the bottom right corner, it'll be more efficient in its instructions to get to that to that direction. So, I won't I won't continue this cuz it can take quite a while to complete this maze.

</details>

### Web MCP 的潜力与用户旅程的简化

**Tara Agyemang**: 如果我们回到幻灯片这儿，这就是我刚才提到的模型上下文工具检查器。这是我们 Chrome DevRel 团队构建的 Web 扩展程序。那里的二维码，如果你想去 Chrome Web Store 看看它在哪的话可以扫一下，但任何人都可以使用并从 Web Store 下载它。从本质上说，WebMCP 解锁了使用 Web 的全新方式，让你的用户无需再花大量时间去搞明白那些复杂的网站到底该怎么用。

<details>
<summary>Original English</summary>

**Tara Agyemang**: But, if we go back to the slides here, so this is the model context tool inspector that I mentioned. So, this is the web extension that our team in Chrome DevRel built. The QR code there is is if you want to see where that is in the Chrome Web Store, but anyone can use that and grab it from the Web Store. But, essentially, WebMCP kind of unlocks this new approach to using the web where your users don't have to spend a lot of time trying to figure out how to use more complicated sites.

</details>

**Tara Agyemang**: 他们可以自主规划他们的工作流。比如，他们可以选择先用普通方式浏览你的网站一会儿，然后把控制权交给他们的 AI 代理，让代理代为执行接下来的步骤。随后，你的用户可以随时介入重新接管控制权，再次以他们平时习惯的方式浏览你的网站。这种能够简化用户旅程、让人们的操作变得更轻松的能力，正是这项新标准引起巨大兴趣和兴奋的主要原因之一。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And they can figure out their own workflow. So, they can choose to browse your website the normal way for a bit, then they can hand over control to their AI agent, and the AI agent takes steps on their behalf. And then your user can come in at any time to take control again and browse your site again the way they normally would. And so, that ability to simplify user journeys and make those user journeys for people easier has been a large part of the reason we've seen interest and excitement in this new standard.

</details>

### Web MCP 与 MCP 的区别

**Tara Agyemang**: 我想停一下，先回答一下某些人可能会有的疑问。那就是：**Web MCP** 和 **MCP** 到底有什么区别？你大可把它们看作是互为补充的关系。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, I want to pause for a minute just to address the question that some people have. And that's what is the difference between Web MCP and MCP. But you can kind of see them as being complementary to each other.

</details>

**Tara Agyemang**: MCP 使得 AI 代理能够连接到服务器端的应用程序，你需要自己去搭建服务以便代理访问，然后代理就能随时随地访问这些信息。而 Web MCP 不同，它更像是受到 MCP 的启发而诞生的。我喜欢把它比作 JavaScript 是如何受到 Java 启发的一样。简而言之，Web MCP 是 MCP 体系中“工具”（tools）部分的具体实现。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, whereas Web So, whereas MCP enables AI agents to connect to applications on the server side, and you'd need to set up your own service for the agent to access, and then the agent can access the information anywhere, anytime, Web MCP is different in that it's kind of inspired by MCP. I like to think of it of as how JavaScript is inspired by Java. And that's in short, Web MCP is the implementation of the tools part of the MCP.

</details>

**Tara Agyemang**: 因此，Web MCP 允许工程师为浏览器内的 AI 代理提供工具。它非常有针对性，专门为客户端特性设计。所以，你必须保持浏览器窗口打开，Web MCP 才能起作用，接着你就能用它帮助你的代理与浏览器进行交互。也就是说，所有的工具都驻留在浏览器中。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And so, Web MCP allows engineers to provide tools to in-browser AI agents. And it's very specific for the client-side features. So, you have to have your browser window open for Web MCP to work, and then you can use it to help your agent interact with the browser. So, all of the tools live in the browser.

</details>

### Web MCP 的实际应用场景

**Tara Agyemang**: 你可以想象出它的很多种不同类型的应用场景。试想一下那些极其复杂、要求用户执行很多步骤的网站，比如预订机票，或在普通的购物网站上筛选商品，或是填写繁杂的医疗或财务表单，亦或是用来触发那些隐藏在页面中需要被修复的问题。或者就像我一样，你只是在一个普通的购物网站上，想找一个正好能装下手机的黑色人造皮革手拿包，相比于去挨个点选那些小小的过滤条件，你只想直接让你的 AI 代理帮你搞定。

<details>
<summary>Original English</summary>

**Tara Agyemang**: But you can imagine this for quite a few different types of use cases. So, imagine those websites that are really complicated and have a lot of steps that a user needs to take, maybe like booking a flight or filtering products on a normal shopping website, or filling in complicated medical forms or financial forms, or to trigger fixes that need to be hidden on a page, that are hidden on a page. Or if you're like me, you're just on a normal shopping site and you're trying to find the right black faux leather clutch bag that can fit your mobile phone in, and instead of going through all the little filters, you just want to ask your AI agent to do it for you.

</details>

**Tara Agyemang**: 这里有大量的例子可以说明，任何用户都可以请求他们正在使用的任意 AI 代理代为完成这些事情。于是，用户就无需手动去操作了。他们不需要挨个填写输入框，不需要逐个勾选复选框，在这些场景下使用 Web MCP 意味着你能让用户的这些操作变得容易得多。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, these are a bunch of examples where any user can ask whatever AI agent they are using to complete these things on their behalf. So, the user doesn't have to manually do this. And they don't have to fill in each input, they don't have to select each checkbox, and using Web MCP in these cases can mean that you can make those actions much easier for users.

</details>

### Declarative API 与 Imperative API

**Tara Agyemang**: 让我们来看看这些 API。Web MCP 提出了两种实现方法。我们有声明式 API（Declarative API）和命令式 API（Imperative API）。我们先从声明式 API 开始。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, let's look at the APIs. Web MCP proposes two approaches for implementation. So, we've got the declarative API and the imperative API. Let's start with the declarative API.

</details>

**Tara Agyemang**: 如果你有一个普通的 HTML 表单，你只需要向 HTML 添加几个属性，就能让它运作起来。在这里我们有工具名称和工具描述，然后你的浏览器会自动生成一个 JSON schema（模式），AI 代理就可以读取它，并把表单字段作为工具的参数来使用。这展示了这个 HTML 表单所生成的 JSON schema 大概是什么样子。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, if you have a normal HTML form, you can just add a few attributes to the HTML to get this to work. So, we've got the tool name and tool description here, and then your browser will automatically generate a JSON schema that the agent can use to read using the form fields as parameters for the tool. So, here's an example of what the JSON schema would look like for this form HTML.

</details>

**Tara Agyemang**: 另外还有一大堆其他的属性可以被使用。比如有一个 `agent-invoked` 的布尔值属性，通过它你可以分辨出你的表单到底是由 AI 代理填写的，还是由人类填写的。而且还有很多类似的更具体的属性可以被用在这些场景中。但总的来说，当你拥有一个标准的表单元素时，你就会想使用声明式 API。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And there are a whole bunch of other attributes that can be used. So, there's like um an agent invoked Boolean attribute, so you can tell whether your form was filled in by a agent or if it was filled in by a human. And there's lots of like more specific attributes that can be used for things like that, too. But essentially, you want to use the declarative API when you have a standard form element.

</details>

**Tara Agyemang**: 但当你遇到更复杂的情况时，你就需要退回到命令式 API。在这里，你可以为更复杂的、可能包含多步骤的 UI 流程注册和定义你自己的自定义工具。来看这个例子。在底部，我们有这个 `register tool`（注册工具）函数。当你用这样一个对象去调用 `register tool` 时，你需要手动去创建你自己的 Schema，就像我们在声明式 API 中自动生成的那种一样。你要给工具命名并提供描述，而且你要确保描述写得非常详尽，这样 AI 代理才能确切地知道什么时候应该调用这个工具。

<details>
<summary>Original English</summary>

**Tara Agyemang**: But when you have something more complicated, that's where you want to go back to the imperative API. So, this is where you can register and define your own custom tools for when you have more complex, maybe multi-step UI flows. So, here is an example. So, at the bottom, we have this register tool function. And when you call register tool with an object like this, you need to manually create your own schema similar to the one that we had in the declarative API that was generated. You name your tool and give it the description, and you want to make sure you have really descriptive descriptions that enable the AI agent to know when it should be calling this tool.

</details>

**Tara Agyemang**: 然后，你还有一个 `execute` 代码块，这本质上就是你调用常规 JavaScript 的地方。所以，也许你已经有正在使用的现成函数，你可以直接在这里面调用，或者做一个轻量级的封装。在这个“添加待办事项”的例子中，你可以做比如验证和修剪文本输入的操作，然后你创建 DOM 元素或 DOM 节点，并将它们添加到你的页面上。最后，你需要返回一些信息给 AI 代理，告诉它执行的情况——比如如果一切都成功执行了，代理就可以利用这个信息来进行下一步动作。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And then, you have the execute block, which is essentially where you call normal JavaScript. So, maybe you already have functions that you're using that you can call in here, maybe do a light wrapper. In this add to do item example, you can like validate and trim text input, for example, and then you create the DOM elements or DOM nodes and add them to your page. And then, you want to return some information to the AI agent so it knows what happened if everything happened successfully so it can use that information for its next steps.

</details>

**Tara Agyemang**: 这就是那两种 API。命令式 API 可能是被使用得最多的一个，因为人们通常会有更复杂的 UI 流程想让代理去完成。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, those are the two APIs. The imperative API is probably the one that's most used because people have more complex UI flows that it wants the agent to complete.

</details>

### 复杂应用演示：购票流程自动化

**Tara Agyemang**: 如果我们回到我之前那个手写的（Vibe Coded）演示，我在这里添加了几个工具。在演示中有几个精选活动（featured events），然后所有的活动都在下面列出，接着你可以进入单独的演唱会页面购买门票。我注意到这个演示跟 Gemini 3.1 配合得更好，所以我打算试试这个模型。假设我们想买这些音乐节之一的票，咱们买 Summer Vibes Festival 的门票吧。Summer Vibes Festival。呃，我看看，买两张 VIP 门票。因为只有 VIP 才配得上我。发送这个提示词。

<details>
<summary>Original English</summary>

**Tara Agyemang**: But if we go back to my Vibe Coded demo, I have added a few tools here. So, we have a few featured events in the demo, and then all of the events available down here, and then you can go in and purchase tickets for an on an individual concert page. So, I have noticed that this works much better with Gemini 3.1, so I'm going to try that one. If we wanted to buy tickets to one of these festivals, let's buy tickets to the Summer Vibes Festival. Summer Vibes Festival. Uh let's see, two VIP tickets. Cuz VIP only for me. Send that prompt.

</details>

**Tara Agyemang**: AI 发现了“搜索演唱会”（search concerts）这个工具，它调用了该工具去通过名称搜索特定的演唱会，工具返回了该演唱会的信息，包括这个演唱会的 ID。随后它调用了第二个工具“打开演唱会页面”（open concert page）并传入了演唱会 ID，这成功打开了 Summer Vibes Festival 的页面，而这个新页面有它自己独立的工具。这有个工具叫“购买门票”（purchase ticket），它在这第三次工具调用中执行了操作，传入了数量 2 以及区域名称。然后我们就收到了一条小通知说：“哦，你已经买好票了。你花了 356 英镑。太棒了，我会把它记在 Google 的信用卡上。”

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, the AI saw the tool search concerts, which it has called to find the specific concert via the concert name, and the tool returned the information about the concert including the ID for that concert. Then it has called the second tool open concert page with the concert ID, and that has opened the Summer Vibes Festival page, and then this new page has separate tools. This one here called purchase ticket, and it's called that in the third tool call here with a quantity two and section name, and then we've got a little notification saying, "Oh, you've bought your tickets. You spent £356. Great, I'll put that on the Google's credit card."

</details>

**Tara Agyemang**: 但你也可以看到，在每一个步骤里它都更新了 UI，以确保用户也能看到究竟发生了什么。所以，你始终都要确保你的 UI 与正在发生的工具调用保持同步。你看我们这里选好了 VIP，也选好了数量，然后在真实的场景中，它会跳转到某个结账页面。你可能希望让你的用户手动去完成那最后一步，这样他们才能清楚自己花的是真金白银。我们先点退回。

<details>
<summary>Original English</summary>

**Tara Agyemang**: But you can see as well like in each step, it's updated the UI to make sure the user can also see what's happening. So, you also you always want to make sure that your UI is in sync with the tool calls that are happening. So, we've got the VIP selected, we've got the quantity selected, and then in real life it would go through to some checkout page. You'll probably want your user to manually do that step so they know that they're spending real money. Let's hit back.

</details>

### 如何体验与参与反馈

**Tara Agyemang**: 如果你有兴趣体验一下，那你最好先了解一下 Web MCP 目前的状态。我们仍然处于早期预览阶段。这个 API 是非常实验性的。它随时会变。实际上过去几周它一直都在变。所以我今天演示的代码下周可能就不一样了。但这正是因为我们希望人们去试用它。我们渴望收到反馈。我们想知道使用这个 API 最好的方式究竟是什么。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, if you're interested in trying this out, it's probably worth just understanding the status of where we're at with Web MCP. So, we're still in early preview stage. This API is very experimental. It will change. It has been changing over the past few weeks. And so, the code that I've shown might be different next week. But that's because we want people to try it out. We want feedback. We want to know the best way to use this API.

</details>

**Tara Agyemang**: 如果你有兴趣这么做，这里有一些设置步骤。Web MCP 在 Chrome 146 及以上版本中可用。我建议使用 Chrome Canary 版本，这样你可以把各种环境分离开来。否则在普通的 Chrome 里，你必须去开启一些实验性标记（flags）。你可能并不想在日常使用的浏览器里去动这些。一旦你装好了 Chrome Canary，你需要通过在 URL 里输入这个标志来启用 Web MCP 测试标志。接着，去 Chrome Web Store 安装我之前提到的那个 Model Context Tool Inspector 扩展程序。这样你就可以玩起来、调试并观察你的工具到底在做些什么。

<details>
<summary>Original English</summary>

**Tara Agyemang**: And if you're interested in doing that, these are a few steps to get set up. So, Web MCP is enabled in Chrome version 146 upwards. I recommend using Chrome Canary just so you can keep things separate. Otherwise, in the normal Chrome, you have to enable experimental flags. And you might not want to do that on your normal your normal browser. Once you have Chrome Canary, you'll need to enable the Web MCP testing flag with by putting this flag in your URL. And then install the Model Context Tool Inspector extension from the Chrome Web Store that I mentioned earlier. Just so you can play around and debug and see what your tools are doing.

</details>

**Tara Agyemang**: 然后，我推荐大家看看这两个资源。第一个是我们的主博客文章，它提供了关于 Web MCP 早期预览计划的信息。如果你在那里注册了，你就能获取我们所有的初始文档。而且你能得到关于这个计划的额外信息、最佳实践的指导、所有的实现细节（你在测试时可能想用到这些），以及全部的 API 信息。这是第一个资源；第二个是所有工具的 GitHub 代码仓库。所以，检查器工具在这儿。我们也把所有的演示 Demo 都放上去了，你可以看到那个迷宫游戏的演示代码已经开放上线，大家可以直接去把玩。大概有六七个不同的演示你可以尝试，而且还有一个命令行测试工具（eval CLI tool）可以用来帮助你从今天开始就在你自己的网站上测试你的 Web MCP 工具。

<details>
<summary>Original English</summary>

**Tara Agyemang**: Then, uh these are the two resources that I recommend taking a look at. So, this is our main blog post that gives you information on the early preview program for Web MCP. So, if you sign up there, you get access to all of our initial documentation. And you get extra information about the program, information on best practices, implement all the extra implementation details that you you might want to use while you're testing it out, and all of the API information. That is the first one, and the second one is the GitHub repository of all the tools. So, we've got the inspector tool here. We've got all the demos, so you can see the maze demo code is live there for you can to play around with. There's about six, seven different demos you can try out, and there's an eval CLI tool you can use to help you start testing your own sites in the Web MCP tools on your own sites today.

</details>

### 总结与展望

**Tara Agyemang**: 刚才提到我们还在早期预览阶段。那是因为我们正在征集反馈意见。去试试吧。告诉我们你的想法，如果你遇到了任何摩擦点，如果你发现了任何 Bug。我们非常希望了解到这些，这样我们才能不断迭代这个 API，并最终推进到下一阶段，让 Web MCP 走向更多的用户。

<details>
<summary>Original English</summary>

**Tara Agyemang**: So, I mentioned we're still in early preview. That's cuz and we're looking for feedback. So, try it out. Let us know what you think, if you have any friction points, if you find any bugs. We'd love to know that so we can keep iterating on this API, and eventually move onto the next stage and start getting Web MCP in front of more users.

</details>

**Tara Agyemang**: 最后总结一下，AI 代理已经开始在使用 Web 网络了。我们不需要再妥协于当今这种消耗大量 Token、极其脆弱的屏幕抓取流程。取而代之的是，我们可以使用 Web MCP 工具，将每一个网站变成面向代理的高性能 API，同时继续为我们网站的人类用户打造不可思议的用户体验。既然现在大家已经了解了这些工具和背景知识，请去尝试一下，就在今天开始，试着让你的网站为 AI 代理做好准备（agent-ready）吧。非常感谢大家。

<details>
<summary>Original English</summary>

**Tara Agyemang**: But to wrap up, AI agents are already using the web. We don't have to settle for these token-heavy, brittle screen-scraping processes that we have today. Instead, we can use Web MCP tools to turn every website into a high-performance API for agents, and at the same time build incredible user experiences for the users of our sites. So, now that you have the tools and the context, please give it a go, and try making your agent try making your website agent ready today. Thank you very much.

</details>