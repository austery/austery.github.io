---
author: AI Engineer
date: '2026-05-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LMbeDEQO6QM
speaker: AI Engineer
tags:
  - mcp
  - agentic-web
  - web-primitives
  - browser-api
  - ai-ui
title: 你的 AI 代理是无限画布：重塑网页体验
summary: 本演讲探讨了如何将现有的网页原语（如 CSS、JavaScript、Web API）与 AI 代理深度结合，利用 Model Context Protocol (MCP) 和 Web MCP，将网站转变为交互式、无限画布式的代理体验，超越传统的文档阅读器限制。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - W3C
  - Anthropic
products_models:
  - MCP
  - Web MCP
  - Web Animations API
  - Firefox DevTools
media_books: []
status: evergreen
---
### 代理与网页的交互性重构

演讲者 **Rachel Lee** 拥有丰富的 web 标准制定与开发者工具开发经验（曾就职于 Mozilla、W3C、Microsoft Edge 团队及 React 团队）。她目前专注于 AI 初创公司与 LLM 的网页与 UI 交互研究，并撰写《**The Agentic Web**》简报。她的核心动机源于维护自己 2006 年创立的一个 web 漫画档案网站，面对现有网页架构的陈旧与 404 问题，她希望不仅能修复它，更能使其“面向代理（Agent-future-proof）”。她强调，开发者应“在观众所在的地方与其相遇”，如今观众正转向代理，因此将网站重构为代理可用的格式至关重要。

<details>
<summary>Original English Source</summary>
Hi there. I am Rachel Lee, Rachel Lee Neighbors, Neighbors like Nearest Neighbors, but not spelled that way. I have worked on the standards that powers today's web today's web with Mozilla on Firefox DevTools, the W3C on web standards like the Web Animations API. I've even been a PM on Microsoft's Edge browser, and you may know me from my pandemic babies on the React team, react.dev and reactnative.dev. All right, so I've spent the last 3 years consulting with AI startups and LLM / big browser companies, some of whose logos you may recognize, most of whom you will not, on all things web, AI, and UI. Recently, I've just become newly minted principal developer experience engineer at a rise.

In this case, my web comics site, the archive site that I put together at like 2010 said, "Okay, you're good there. I got to go now." And it's starting to get 404s, starting to get some broken images. Maybe I shut down some clusters here and there, and it's like, "Oh dear, the CDN has failed." Anyway, it needed some repair, and I was like, "Well, don't just repair it, make it future-proof." If everyone is working in agencies these days, let's meet them where they are. I'm always meeting my audience where they are, and I still get fan mail from the women who grew up with my comics, so maybe I can get them to try out agents, too.
</details>

### 浏览器作为无限画布

Rachel 认为，浏览器远非仅仅是一个文档阅读器，尽管许多 CSS 专家倾向于强调其文档属性。相反，浏览器是一个**无限画布**（Infinite Canvas），能够渲染视频、音频以及任何现代 Web API 所支持的交互内容。她一直致力于拓展网页的能力边界，例如参与开发 **Web Animations API**（W3C 标准）。通过现有的网页原语，我们可以将现有的网站能力转化为代理可以消费的交互体验，从而赋予代理更强大的操控感。

<details>
<summary>Original English Source</summary>
When I got into the web, I believed that the browser is not just a document reader, despite what the CSS wonks will try to get you to believe. It is an infinite canvas that can render anything, not just documents, but video, audio, whatever you need, there's an API for it, and I have been working to that end on the web ever since. I worked on that Web Animation API with the W3C creating such insane demos as the interactive Alice in Wonderland, uh and generally made the web do things that it was not supposed to do. Uh And now I write about how agents and AI are changing how we browse and consume content on my little newsletter, uh The Agentic Web. And I do a fair bit of move shenanigans with agents myself. This is uh ASA, it stands for Anti-Social Social Agent. It's an MCP app that lets you use Twitter and BlueSky next to each other without actually having to visit the sites or be subjected to other people's algorithms. Anyway, check it out if you like it. Uh I'm here today to show you how, with the power of the browser's primitives that already exist and have already been specked out right now, you can turn your agent into an infinite canvas, or at least get your website into agents, one way or the other.
</details>

### MCP 的两种传输架构：STDIO 与 HTTP

在构建 **MCP**（Model Context Protocol）服务时，理解不同的传输协议（Transports）至关重要。
*   **STDIO** (Standard Input/Output)：通常作为本地进程运行，由客户端派生。虽然 MCP 规范常采用这种方式，但它往往涉及复杂的命令行配置，这对非开发者用户而言并不友好。
*   **HTTP**：运行在 Web 服务端，通过 HTTP POST 请求通信。它非常适合 Serverless 架构（如 Vercel、Cloudflare 的边缘函数）。对于终端用户，使用 HTTP 服务端的工具更加直观，仅需在客户端设置中输入 URL 即可建立连接。

<details>
<summary>Original English Source</summary>
Transports are how MCP servers communicate with agents. And there's a important difference between when you should use either of these. So, STDIO stands God, it sounds terrible when you read it out. Standard input output, you can call it studio. Like the Phil Collins song, cuz we're in England, okay? Studio. We're going to call it that for the rest of this talk. Unlike my German proofreader who was like, "I don't think you call it studio." I was like, "Dude, you want me to call it anything else? I think we're going to have problems." All right, so the server, it runs as a local process, it's spawned by the client. This is why when you're wiring up studio-based MCP app, it's always like a string of JSON with a bunch of command-line inputs that most of your users don't want to use, don't want to configure.

HTTP is a little different cuz we're running over the web. We are not touching with a 10-ft pole, by the way, any of the security or privacy concerns with either of these layers. That is beyond the scope of today's conversation. But HTTP, the server runs as a web service, it listens at an HTTP endpoint which you may be familiar with from API development, and communication happens via our best friend HTTP post requests, and it works well with serverless setups. You know, Vercel keeps and and Cloudflare keep trying to sell you those edge functions. Well, they got something to put in them now.
</details>

### MCP Apps：代理的交互式体验

Rachel 批评了单纯依赖文本交互作为代理界面的局限性，将其比作“星鱼设计”（starfish design）——即让用户进行所有繁重的发现工作。为了提升体验，她提出了 **MCP Apps** 的概念：通过将 HTML、CSS 和 JavaScript 打包为**单文件**（Single File），通过 MCP 工具直接在代理界面中嵌入交互式 UI。

她展示了 **get page** 工具的实际应用：该工具返回一个封装好的 MCP App（一个 sandboxed iframe），允许用户在代理中直接阅读漫画、导航甚至切换到文本阅读模式，无需离开对话窗口。构建这些应用需要注意：所有资源必须 Base64 嵌入或妥善配置 **CSP**（内容安全策略），且不具备本地存储能力。

<details>
<summary>Original English Source</summary>
It's been said that chat is the lowest common denominator of the user experience. That it is to the future of agentic experiences what the CLI was to software. My mother programmed in COBOL, and when at school they were making us click double-click on icons to access video games, she was like, we do not do that in this household. We open DOS and we do CD blah blah blah.exe. That is how programmers do things. But we all know that you don't do that on an iPhone, you tap and you point and grunt, right? So, this is probably a phase for us developers. There's a current what I call the chatbox landing page or starfish design because it sits there and it lets the user do all of the work. And you have to have a lot of context in your head when you land. You have to kind of know what this thing can do.

It's sort of like these text games were really popular back in the day, but I wouldn't want to have to do my taxes by being like, check mailbox. Is there mail? Whose house is this? That's not great. So, fortunately, we have MCP apps inline in agent rich media experiences created by bundling of HTML, CSS, and JavaScript into a single file. So, this is get page. Get page is my MCP tool baby, and I love it very much. This is it in action. It returns an MCP app. And check it out. I can show the commentary. I can show the comments. That's pretty cool. Those are available on the website. It's everything the website can do. It looks just as good as the website. You can navigate forward and backward. But the fun part is you go up here, you can click on text mode, and boom, it shows you the transcript. So, you could just read it if you wanted to. That'll come back later. So, yeah, it's like a little mini website. Comic reader, but it's using all the resources from the website.
</details>

### Web MCP：网页即迷你工具服务器

为了解决当前代理浏览网页时依赖截图和 DOM 解析（高消耗 token、 compute-intensive）的痛点，Rachel 介绍了 **Web MCP**。它允许网页页面直接通过 `navigator.modelContext.registerTools` 注册函数，使每个 HTML 页面成为一个迷你的 MCP 工具服务器。代理不再需要盲目猜测如何操作界面，而是可以直接调用网页原本就存在的 JavaScript 函数进行导航、数据转换或 API 调用。Rachel 指出，尽管 Web MCP 目前尚未完全标准化，且与正式 MCP 规范有所差异，但它开启了“网页即工具”的全新范式，利用浏览器原生 API（Speech、Animation、Audio、Canvas 等）为代理打造沉浸式交互体验。

<details>
<summary>Original English Source</summary>
Big and small browsers are shipping with agents built right into them. Sadly, they still struggle with navigating websites because they rely on taking screenshots and guessing how to use the navigation or traversing the DOM, which burns tokens chewing up XML, which is really not a great use. Both of these are compute-intensive cuz you're using visual models or you're just eating a bunch of HTML to find out where the next URL is. Wouldn't it be great if they just had a way to call the same functions and links you already have in your JavaScript directly from the page that they're visiting? Well, with Web MCP, they can do just that. It makes every HTML page a mini MCP tools server. However, I just want to point out that Web MCP is to MCP as a JavaScript is to Java. Inspired by riding the hype wave of But if you actually look under the hood, it's taking inspiration. It is not a one-to-one compliance with the MCP spec. It's really just like tools for agents in your browser, yo.
</details>