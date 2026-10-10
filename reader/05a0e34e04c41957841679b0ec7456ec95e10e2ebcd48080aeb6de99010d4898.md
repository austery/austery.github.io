---
author: AI Engineer
date: '2026-06-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=c-2eEv2ou7Y
speaker: AI Engineer
tags:
  - mcp
  - iframe-nesting
  - content-security-policy
  - cross-origin-isolation
title: 为什么MCP与ChatGPT应用需要双重iFrame嵌套机制？
summary: 本演讲深入探讨了在ChatGPT等通用AI平台上运行第三方MCP应用UI的底层架构。演讲者剖析了直接使用iFrame遇到的CSP（内容安全策略）限制与沙盒同源安全风险，解释了业界如何利用“双重iFrame”结合子域隔离来兼顾安全性与UI动态渲染，并展示了Skybridge框架如何帮助开发者解决跨域调用难题。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
products_models:
  - ChatGPT
  - Claude
  - Skybridge
media_books: []
status: evergreen
---
### MCP与ChatGPT应用简介

**Frédéric Barthelet**: 大家好。我是Fred，MCP托管公司**Alpic**的首席技术官和联合创始人。今天我想和大家分享一次深度探索的冒险之旅，研究我们在**ChatGPT**和MCP应用中采用的**双重iFrame机制**，以及这在我们构建应用时有什么重要意义。首先，如果你之前没有机会听Ido和Leat关于MCP应用的演讲，我来快速总结一下这些MCP和ChatGPT应用到底是什么。这对你的业务来说是一个暴露产品和服务的新表面区域，作为一个新的获客渠道，它主要具备两个特征。第一个是**可发现性（discoverability）**，所以你将在诸如ChatGPT和**Claude**这样面向消费者的通用智能体中，拥有一个连接器和应用的生态系统。比如ChatGPT的应用商店和Claude的连接器。这些应用不仅在商店里可以被浏览发现，它们在聊天对话中也能被发现。因此，如果你正在进行一段对话，并且正好需要引入某个应用来添加额外上下文，或者提供一些很棒的附加操作时，它们就会被引入到对话中。第二部分，也是这其中最大的一部分，同时是我们本次演讲的重点：就是在这些你以前只能输入纯文本的对话智能体中，加入了**交互式UI（interactive UI）**。应用增加了一个全新的UI层，这个UI层可以由MCP服务器提供，也可以是由生成式AI生成的UI。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: Hi everyone. My name is Fred. I'm the CTO and co-founder of Alpic, the MCP hosting company. And today I would like to share with you an adventure deep diving into the double iFrame mechanism that we have on ChatGPT and MCP app and what it matters when we build apps. First thing first, if you haven't had the chance to listen to either Ido and Leat talks just before about MCP apps, a quick sum up of what those MCP and ChatGPT apps are. That's a new surface area for your business to expose product and services with new acquisition channel that has two main criteria. First one being discoverability, so you will have ecosystems of connectors and apps available in a consumer generalistic agent like ChatGPT and Claude. So ChatGPT app store and Claude connectors. Those apps browsable inside the store, but they are also discoverable in chat. So if you're having a conversation that's relevant for an app to be brought into to add additional context and feature some nice additional actions, they will be brought into the conversation. And the second part, which is the biggest part and what we will be focusing on in this talk, which is the addition of interactive UI inside those conversational agents where you used to add text only. Apps add a new layer of UI that could be provided by the MCP server, but could be generated generative UI as well.

</details>

### 视图与UI的渲染机制

**Frédéric Barthelet**: 人们最初构想的是使用刚才Leat和Ido开发的那种MCP UI，然后OpenAI在去年10月份通过一个应用SDK发布了它，并在首个名为app extension的MCP官方扩展上，跨多个客户端进行了标准化。那么它在底层是如何运作的呢？如果我们更仔细地看一看这个UI是如何被引入对话的，实际上它们是通过**视图（views）**被引入的。“视图”是我们用来称呼出现在对话内部的那些UI小片段的名称。视图总是作为工具调用（tool call）的结果被渲染出来。所以，如果你的服务器暴露了多个工具供使用，你实际上可以在其中一些工具上添加元数据，以此声明当结果需要用特定的UI展示时，最好使用这个工具。如果宿主支持MCP应用，它就会使用与这个工具调用相对应的相关视图来显示结果。视图就是简单的HTML文档。你可以在里面包含JS和CSS。这方面没有什么新鲜事。它只是一种打包那些应用小片段的方式，并且它们可以被提前发现，因为所有的视图都在对话开始时，在宿主和你的MCP服务器或MCP应用之间进行的工具列表调用中被描述了。所以，每一个支持UI的工具都会宣告渲染该UI所需的资源。它可以被提前缓存，或者当需要渲染UI的工具被调用时，立刻被端上来、下载并提供服务。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: They were first thought of using MCP UI that was developed by Leat and Ido just before, then released by Open AI with an app SDK back in October last year and standardized across multiple clients on the first official extension of MCP called the app extension. How does it work under the hood? If we take a little bit closer look at how this UI is brought into the conversation, those are brought using views. Views are the name that we use for those small snippet of UI that appears inside the conversation. Views are always rendered as a result of a tool call. So if your server exposed multiple tool to be used, you can actually add metadata on some of them to say this tool is best used when results will be displayed using a specific UI. And if the host supports MCP apps, it will use the relevant view corresponding to this tool call to display the results. Views are simple HTML document. You can include JS and CSS inside. Nothing new under the sun here. It's just a way to package those small snippets of application and they are discoverable ahead of time because all views are described on the tool list calls that happens at the beginning of the conversation between the host and your MCP server or MCP app. So each tools that supports UI will advertise the resource that's needed to display the UI. It can be cached ahead of time or it can be served and downloaded and served right away when the tool call that needs UI to be rendered is made.

</details>

### 双重iFrame嵌套的发现

**Frédéric Barthelet**: 宿主端的对话智能体将创建一个新的iFrame，视图将显示在其中，并且它会将工具的结果注入到里面，这样你就能向用户渲染动态内容了。如果你更仔细地查看当你……我当时有点好奇，我想知道它是怎么工作的，或者ChatGPT到底是如何在对话中渲染第三方UI的。然后我有点惊讶，我面对的结果与我的期望大相径庭，我发现了一个**双重iFrame（double iFrame）**，也就是一个iFrame被嵌套在另一个iFrame内部。这给了我做这次演讲的灵感。今天我想带你们一起深入探索，为什么他们会做出这种“盗梦空间”式的iFrame嵌套决定，它的好处是什么，为什么它会被应用，以及当你构建应用时这有什么影响，你应该注意什么，以及如何确保你提供的用户体验非常棒。在深入探讨之前，让我们仔细看看在实现MCP应用之前的ChatGPT是什么样的。在整个深入剖析的过程中，我们将使用ChatGPT作为例子，但如果你想自己去看看的话，完全同样的情况也发生在Claude AI上。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: The conversational agent on the host will create this new iFrame where the view will be displayed and it will inject the tool results inside so that you have dynamic content rendered to the user. If you take a closer look at what is inside the DOM of the host when you take a I was a bit curious and I wanted to know how it was working or how ChatGPT was actually rendering third-party UI inside the conversation. I was a bit surprised and I was met with not so much expectation about having a double iFrame, having an iFrame nested in inside another iFrame. And this gave me the idea for this talk. I want to bring you today with me deep diving into why the decision was made to do this kind of inception nesting of iFrames and what are the benefits, what was it put in place and what are the implications when you build apps, what should be paying attention to and how to make sure that your experience is very nice. Before we go into that, let's take a close look at what ChatGPT was before MCP app were implemented. We'll be using ChatGPT as the example throughout this deep dive, but the exact same happened on Claude AI if you want to take another look by yourself.

</details>

### 内容安全策略（CSP）与安全限制

**Frédéric Barthelet**: 第一件需要研究的非常重要的事情，是一个叫做**内容安全策略（Content Security Policy, CSP）**的东西。这些是服务器作为文档调用的响应头返回的指令。所以当你在浏览器里加载ChatGPT时，ChatGPT会响应一个文档，外加安全策略指令，规定浏览器被允许加载和执行什么，以及不被允许加载和执行什么。内容安全策略里包含了很多条指令。有的是关于你能运行哪些脚本，你能下载哪些CSS样式表，你能下载什么图片，以及你可以连接并向其请求数据的API。我不会深入探讨细节，但这里有两个指令必须记住。一个是`frame-src`，它基本上是一个允许特定网站在文档内渲染iFrame的指令；另一个是`script-src`，它基本上允许在浏览器内运行特定站点的脚本。为了能够在ChatGPT内部运行外部UI，我们将使用一个专门为此目的制作的专用HTML元素，也就是内联框架元素或**iFrame**，它的作用基本上是在你的浏览器窗口内生成嵌套的浏览上下文。所以那些小的视图片段将几乎作为完全隔离的独立浏览上下文被渲染出来。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: The initial thing to take a look at that is very important is something called content security policy. Those are directives returned by server as response header to document call. So when you load ChatGPT inside your browser, ChatGPT will respond with a document plus security policy directive on what the browser should be allowed to load and execute and what it shouldn't be allowed to load and execute. You've got multiple directives included inside content security policy. Some about which scripts you can run, which CSS style sheet you can download, which image you can download, which API you can connect to and ask question to. I will not go into the details, but two are very important to remember here. Frame SRC, which basically is a directive to allow specific website to render iFrame inside the document and script SRC, which basically allow specific sites script to be run inside the browser. To be able to run external UI inside ChatGPT, we will use a dedicated HTML element that has been made specifically for this purpose, which is the inline frame element or iFrame that is made to basically spawn up nested browsing context inside your browser window. So those small pieces of views will be rendered as almost separately completely isolated browsing context.

</details>

### iframe实现方案的局限性

**Frédéric Barthelet**: 它们非常方便，并且有两种使用方式。第一种是为你想要渲染的iFrame提供一个`src`源。也就是浏览器将要加载的另一个页面的URL，让它在本地执行，并在它所分配的空间内进行渲染。另一种是`srcdoc`，这是另一个属性，它允许你直接把想渲染的内容推送进iFrame中原样渲染，而无需让浏览器去加载另一个内容资源。所以，如果你想建立这个应用市场，并让第三方UI在ChatGPT内渲染，为什么不直接使用`srcdoc`属性来把上下文注入进去呢？上下文指的是那些基本上由MCP服务器暴露的内容资源。也就是纯HTML直接加载进去。如果我这么做，它是行不通的，主要原因是：当你加载一个指定了`srcdoc`属性的iFrame时，你生成的这个iFrame与负责渲染它的宿主共享了相同的**源（origin）**，因此也共享了相同的CSP。这样一来，属于你应用程序的任何脚本都会被ChatGPT现有的基于`script-src`指令的CSP完全拦截。该指令要求ChatGPT中的每一个脚本都必须在每次请求时，带上一个预先生成的特定`nonce`（一次性随机数）进行签名。这确实是一个很酷的安全特性，但它导致任何应用都无法执行JS。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: They are very convenient and they have two ways to be used. First one is to provide a source for the iFrame that you want to render. So basically a URL of another page to be loaded by your browser and executed locally and rendered inside the space it's made of it's made for. And the source doc, which is another attribute which allows you to push inside the iFrame content that you want to render as is without having the browser to load another content. So if you want to build this marketplace of app and have third-party UI rendered inside ChatGPT, why not use straight away source doc as the attribute for as the attribute for uh for injecting context into. And I'm realizing now that it's a little bit small, but I think I can zoom in a bit. No, I cannot. Okay, sorry about that. You'll have to trust me about what is written inside here. So I will just put inside an iFrame injecting context into the iFrame. Context being the content being basically the resource that is being exposed by the MCP server. So pure HTML loading inside. If I do that, uh it's not going to work mostly because when you load up an iFrame with source doc attribute specified, the iFrame that you are spawning up is sharing the same origin and sharing the same therefore CSP as the host that is responsible for rendering it. So any script that would be part of your application that would be completely blocked by existing ChatGPT CSP on script SRC directive, which basically require every script in ChatGPT to be signed with a specific nonce produced ahead of time at each request, which is a cool security feature to put in, but it prevents any app to be able to execute JS.

</details>

### 沙盒化iFrame的两难困境

**Frédéric Barthelet**: 为了实现这一目的，如果我们稍稍放宽ChatGPT的内容安全策略，让它能够执行任意代码行会怎样呢？我不建议在生产环境中这样做，这只是一个实验性的想法。但如果你这么做了，你将面临一个新问题。基本上，你正在和你的父级DOM共享相同的源。所以，被加载的iFrame脚本将能够访问按照源建立索引的`localStorage`或Cookies。因此，作为一个应用，你就能做到诸如获取ChatGPT现有的`localStorage`，然后把它发送到你的后端服务器这种事。如果你是OpenAI，你绝对不会希望人们有能力做到这一点。那么让我们退回一步，把CSP恢复原样，并改为将iFrame**沙盒化（sandbox）**。`sandbox`是你可以用在iFrame上的另一个属性，它允许iFrame在一个我们称之为**不透明源（opaque origin）**的环境中渲染。这意味着该iFrame将不再与父级共享源。它将等同于一个`null`，从而确保它们不共享同一个源，这样就不会有脚本访问父级DOM的安全问题。然而，如果这样做，你就会失去任何依赖于源索引（origin indexing）的能力。因为你的iFrame内部渲染的所有内容、所有脚本现在都指向一个`null`源。你不能使用`localStorage`，不能使用本地的`IndexedDB`，也不能使用Cookies，因为这些全都是通过源进行索引的。给被沙盒化的iFrame提供源的唯一方法，是添加`allow-same-origin`属性，但这个额外属性会把与父级完全相同的源重新带回iFrame中，于是你又回到了起点：你拥有了一个具备完美“越狱”条件并能访问父级DOM、访问父级`localStorage`和Cookies的沙盒iFrame。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: So in order to do that, what if we relax a little bit the content security policy of ChatGPT and make it so that it can execute any line of code? I would not suggest doing that into production, just an experimental thought here. But if you do that, you are faced a new problem. Basically, you are sharing same origin as your parent DOM. So the loaded iFrame scripts would be able to access local storage or cookies that are indexed by origin. So you would be able as an app to for example get the existing local storage of ChatGPT and send it to your back-end server, which if you are Open AI, you would not want people to be able to do. So let's roll back, put back the CSP as it was before and instead sandbox the iFrame. Sandbox is another attribute that you can use on iFrames allowing iFrames to be rendered in what we call the no pack origin. It would mean that basically the iFrame will not share anymore the parent origin. It would be something equivalent to null making sure that they don't share the same origin and won't have the same problem of script being able to access the parent DOM. However, doing so, you lack any capabilities that are dependent on origin indexing. Because all content, all scripts that are rendered inside your iFrame will now be pointing towards a null origin. You cannot use local storage. You cannot use local index DB. You cannot use cookies because those are indexed by origin. And the only way to actually provide an origin to a sandboxed iFrame is to put allow same origin, which is an additional attribute that brings back the exact same origin as the parent back into the iFrame and you're back to square one where you have an iFrame with exactly the right condition to escape its sandboxing and access parent DOM, access parent local storage, access parent cookies.

</details>

### 为什么选择双重iFrame代理方案

**Frédéric Barthelet**: 好的，所以使用iFrame的`srcdoc`并不是前行的正道。让我们继续看下一个使用`src`属性的最佳解决方案。`src`属性本质上允许我引用一个端点，该端点将成为浏览器在这个iFrame内部加载的内容。作为一名ChatGPT应用和MCP应用的开发者，为什么我不把我的视图、我这个小小的HTML应用程序当作一个普通端点暴露出来呢？比如放在我自己服务器的`/view`端点上。这会是个实现的好办法。然而，这就要求OpenAI去修改另一个CSP指令——也就是列出了所有被允许在ChatGPT上实际渲染iFrame的域名的`frame-src`指令，将未来由各家公司开发的、上架应用商店的海量MCP应用全部囊括在内。因此，每次有新应用发布，ChatGPT都不得不更新CSP来加入新的域名，以便框架能够在特定的域名上被渲染。在大规模应用时这是根本不可行的。所以，我们可以采取的替代方案是，提供一种受控的**代理域名（proxy controlled domain）**，这必须是单一域名且由ChatGPT所有。举个例子，`openaiusercontent.com`。这是他们真实存在的一个域名，专门用来把他们想要展示的用户内容暴露在自己的域名下。并在`frame-src`里使用这个域名作为引用，以确保指令不会拦截加载在该域名上的任何iFrame。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: Okay, so iFrame source doc is not the way to go forward. Let's move on to the next best solution that we have using the source attribute. Source attribute basically allows me to reference an an endpoint that will be the content loaded by the browser inside this iFrame. I'm a developer of the ChatGPT app and MCP app. Why not expose my view, my small HTML application as a normal endpoint like on the view endpoint for example of my own server? That would be a nice way to do it. However, it would require open AI to modify the another CSP directive, which is basically the frame source directive listing all domains that are allowed to actually render iframe on chat GPT to include an infinite list of all the MCP application that will be developed by various companies and brought into the store. So, every time a new app would come out, chat GPT would have to update CSP to include the new domain so that the frame can be rendered on the specific domain. This is not doable full scale. So, what we can do instead is provide kind of a proxy controlled domain, single one that will be owned by chat GPT in that case. For example, open AI open AI user content.com. That's an actual domain that they're using for user content that they want to expose on their own domain. And use this domain as a reference inside the frame source to make sure that the directive does not block rendering any iframes that are loaded on there.

</details>

### 代理域名的实现代价与底层双重嵌套逻辑

**Frédéric Barthelet**: 并且你需要在`openaiusercontent`这个域名上提供一个服务器，它能够从MCP服务器下载资源内容（即HTML），并将其暴露出来，例如在任意子域名上进行渲染，同时利用该子域名的前半部分作为路由键，映射到正确的应用程序。如果这么做，你实际上需要启动一套基础设施，在你的域名上托管商店中提交的**所有**外部第三方UI。这并不是一个理想的处境，因为再说一次，你将为你根本不知道在干什么的代码承担责任，而且你是在你自己的域名上暴露它。不仅如此，如果你不是OpenAI或**Anthropic**，你作为宿主可能根本没有资源来部署这套用来支撑动态内容分发的基础设施。所以，你可以转而采用**双重iFrame机制（double iframe mechanism）**。有了这个机制，你只需要为所有人加载同一个脚本，这个极其简单的脚本负责恢复资源，并使用`srcdoc`属性启动一个内部的iFrame。这样一来，我们把内容放进去了，但这个iFrame并没有在顶层被直接提供，因为顶层共享了相同的源并存在我们前面提到的安全逃逸问题。相反，它将被嵌套在一个专门的域名（有别于ChatGPT）提供服务的外部iFrame中，从而确保它们始终保持隔离。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: And you need to provide a server on the open AI user content that's able to download the resource content from the MCP server, the HTML, and expose it so that it can be rendered for example on any subdomain and use the first part of the subdomain as the routing key to the right application. Doing so, you effectively needs to put in motion an infrastructure where your domain hosts external third-party UI from all apps that will be submitted on your store. Which is not a very good position to be into because once again, you will be responsible for code that you don't know what it's doing and you will be exposing it on your own domain. In addition to that, if you're not open AI or if you're not Anthropic, you might not have the resource as a host to put in place the infrastructure required to serve this kind of dynamic serving of content. So, what you can do instead is go through the double iframe mechanism. And what you will do with that is basically load the same script for everybody, which will be a simple script responsible to recover the resources and initiate an iframe with the source doc attribute. So, we put the content inside, but this iframe will not be served at top level because it shares the same origin and it has the escaping problem we are mentioning before. It will be served inside an iframe with dedicated domain that is different from chat GPT to make sure the isolation stay there.

</details>

### 子域隔离与安全策略的注入

**Frédéric Barthelet**: 你肯定不想止步于此。实际上，你希望把这个专门的脚本加载器放置在子域名（subdomains）下。每次下发的都将是完全相同的内容，但你想将它放置在不同的子域名上。这样一来，如果你的应用调用了任何需要利用源索引的API（比如`localStorage`或Cookie），你的各个应用之间就不会发生冲突。因此，你要确保应用`ABC123`无法访问应用`ABC456`的`localStorage`。实现这个架构的基础设施压力要小得多，因为你只是在将外部iFrame这**完全相同**的一份脚本代码，分发到这个端点上可能存在的所有子域名中去。最后但同样重要的一点是，你希望能将相同类型的内容安全策略定义提供给应用本身，以防它在视图内直接执行恶意脚本或渲染未授权的iFrame。在MCP规范中提供这一功能是有方法的，其渲染方式是在第一个（外层）iFrame内使用特定的`meta`标签。这就是我实际部署到生产环境中的解决方案。这并非是个全新的方案。它已经存在很长一段时间了，实际上第一次实施这个解决方案还要追溯回Facebook时期，当时他们推出了自己的应用市场，那面临的完全是必须在你自己的应用程序上下文中运行和渲染第三方UI的同款难题。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: You won't don't want to stop there. Actually, you want to put subdomains for this exact script loader. It will be the exact same content that will be served every time, but you want to put it on various subdomains so that if your app uses any APIs that requires origin indexing like local storage or cookie, you don't have collision in between your app. So, you want app ABC123 not to be able to access local storage from app ABC456 for example. The infrastructure for that is much less intensive because you're serving the exact same script content of the first iframe for every subdomain that is exist on this specific endpoint. Last but not least, you want to be able to provide the same kind of content security policy definition to the app itself so that it can prevent execution of any such script or rendering of iframe directly inside the view. There is a way to provide this into the MCP spec and the way you will render it is using a specific meta tag inside the first iframe. This is the actual solution that I implemented into production. And it's not a new solution. It's been around for a long time and actually the first time this solution was implemented was back in Facebook days when they released their app marketplace, which is exactly the same problem that you have to run and render third-party UI inside the context of your own application.

</details>

### 开发者需注意的跨域安全与调试难点

**Frédéric Barthelet**: 作为应用开发者，对你来说最重要的事情是搞清楚到底有哪些规范能让你控制因为这种双层iFrame嵌套而导致的行为。并且，你必须确保每次构建应用程序时，都要在MCP应用规范提供的元数据中，声明你的应用程序所依赖的所有域名，从而确保它们能够在嵌套的iFrame内部被正确重写。举个例子，如果你的应用正在连接一个外部API来抓取数据，你就需要在元数据的`connect-src`指令中声明引用这个域名。对于脚本（script）、图像（image）、框架（frame）也是同样的道理，基础UI（base UI）用得不多，但前两个指令非常关键。这让我想起了一个很老的问题，发生在我刚才提到的2016年，也就是我刚当程序员那会儿。作为一个行业新人，我在处理跨域资源安全请求（CORS）时遇到了极大的麻烦，我就是搞不对。如今这套CSP让我想起了当初初次请求总是失败的那些丑陋日子。所以，生态系统中已经做出了很多努力来让开发者们的日子好过一点。特别是比如在OpenAI这边，他们激活并添加了一个**开发者模式（developer mode）**选项。所以，如果你是一个正在开发应用的开发者，他们提供了一个特定的模式即开发者模式，允许你访问额外的功能。直到今天为止，当处于开发者模式时，所有的CSP都会被移除。于是问题就变成了：你要等到应用进入生产环境时，才会发现因为CSP里缺少了相应的域名，导致你的一些服务器根本无法被访问——这非常不理想。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: What's important for you as an app developer is to make sure what are the specs available for you to be able to control the behavior that results from this double iframe nesting. And the thing that you will have to make sure to do is every time you build an application, declare all domains your application depends upon inside the provided metadata in the MCP app spec so that you are sure that they will be rewritten correctly inside the nested iframe. For example, if you are from your app connecting to an external API to fetch data, you need to reference this domain inside the connect SRC directive of the metadata. Same thing for the script, image, frame and base UI not so much used, but the two first one are very important. And it's reminded me of a very old problem that I had when I started my developer's days back in 2016 I think it was. As a new developer in the space, I was experiencing a trouble getting cross-origin resource security right calls. I had trouble getting it right. CSP reminded me of those ugly day of not getting right the first time with calls. So, there has been effort in the ecosystem to make builders' life better, especially for example on open AI side where they activated they added an option in developer mode. So, if you're a developer and developing app, they have a specific mode which is developer mode which allows you to have access to additional features. Up to today, when you were in developer mode, all CSP were removed. So, you were discovering when you were going into production if some of your servers could not be reached because of missing domains inside your CSP, which was not ideal.

</details>

### 开源框架Skybridge的破局与演示

**Frédéric Barthelet**: 做了大量工作来让开发者的日子更好过的并不只有他们一家。在Alpic，我们构建了一个叫做**Skybridge**的开源框架。Skybridge是在官方应用SDK之上添加的一个特性超集。它带来了几个核心优势：在你的MCP服务器和你的应用小组件及视图之间实现了端到端的类型安全（type safety）；我们有大量的API提供Polyfill，来弥补那些不属于通用规范、但特定于某些宿主、代码或ChatGPT API的功能；此外，我们提供了一系列现代化的开发特性，尤其是在开发环境阶段。今天我想重点给你们展示一个专门为CSP量身定制的功能，我们称之为**CSP Inspector（CSP 检查器）**。是时候进行一个小演示了。我还有几分钟时间。太棒了。让我快速切换到我的屏幕。好。嗯，好吧。这是一个当你创建一个新的Skybridge应用程序时生成的示例代码库。这个Skybridge示例程序附带了一个小应用。它是一个“神奇八音球（Magic 8 Ball）”，你可以向它询问任何问题，它会用25个预定义答案中的一个来回应你。它拥有一个负责生成答案的MCP工具，以及一个用来展示你提问的内容及答案结果的视图。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: They are not the only one doing a bunch of work to make builders' life much easier. At Alpic, we build an open source framework called Skybridge. Skybridge is a super set of feature on top of the official app SDK either and the app we are mentioning. It brings a few things to the table, end-to-end type safety between your MCP server and your app widgets and views. You have a lot of APIs that provides polyfill for features that are not part of the common specification and specific to some of the hosts, some of code and some of chat GPT APIs. And we provide a bunch of modern development features especially in the on dev environment features. And I wanted to show you one just specifically made for CSP, which we call the CSP inspector. Time for a small demo. I do have a few minutes left. Perfect. Let me quickly switch to my screen. Up. Uh up. Okay. So, this is Um this is an example code base that will be generated when you create a new Skybridge application. This example Skybridge application comes with a small application. It's a eight ball that you can ask any question to that will respond one of the 25 predefined answer. It has MCP tool that serves as generating the answer and a view that is there to display the question and the answer to the question that you ask.

</details>

### CSP排错演示及致谢

**Frédéric Barthelet**: 当我启动Skybridge服务器时，我可以在浏览器中访问一个开发工具，这本质上是一个小应用，让我能在应用提交给ChatGPT之前对其进行审查调试。比如，在左侧有一个我的应用所暴露的工具列表。如果我想的话，我可以请求执行其中任何一个工具。在这个例子中，我执行了神奇八音球工具。如果该工具有关联的视图，这些视图就会在Inspector内部渲染出来，这样我就能近距离查看，修改代码并在UI中看到那些变更的实时反馈。我最想展示的一个绝妙特性是我们构建的Inspector的CSP检测部分。它基本上会去读取你在元数据中声明的所有域名，并捕获你的视图发起的实际网络调用所访问的所有域名，然后对它们进行比对，以确保没有任何被调用的域名被遗漏声明。所以，在这儿你可以看到，一切都是绿色的。但是，如果我回到实际的代码库中，并且，比如说我调用了某个API来获取关于我IP位置的信息，这个动作将立刻在Inspector中反映出来，因为组件已经被重新渲染。于是我清楚地看到，我想要并且刚刚调用的那个确切域名，被列为“在元数据中缺失”。接着我就可以回到我的应用里，加上这个缺失的域名。现在，如果我重新加载它，它应该就会变回绿色。耶，一切恢复正常。所以，这是个非常精巧的工具。Skybridge里面还打包了很多其它特性，但这是我们确保要提供给开发者的一项核心功能，因为我们已经见过大量提交给ChatGPT应用商店的应用，仅仅因为缺失了CSP规则而被拒签，或者应用到了生产环境后因为缺失了CSP域名而直接崩溃失效。嗯……快速结束我的演讲，如果可以的话。好，好。切这页。是的。嗯，以上就是全部内容了。再次感谢大家的时间。如果你想获取幻灯片稍后查看，欢迎扫描第一个二维码。如果你想试用一下Skybridge，欢迎扫描第二个二维码。我现在要进行一个小抽奖。只要你在接下来的大概一分钟内star了Skybridge的仓库，我们这里准备了一副滑雪护目镜作为奖品。我将随机抽取一个名字，你就能赢得一副滑雪面罩。非常感谢大家的聆听。

<details>
<summary>Original English</summary>

**Frédéric Barthelet**: When I start the server of Skybridge, I have access in my browser to a dev tool, which is basically a small app that will give me inspection tooling to work with my app before I bring it to chat GPT. For example, on the left I have a list of tools that are exposed by my app. I can if I want ask execute any of the tool. So, for example here, I'm executing the magic eight ball tool. And if there are views associated with this tool, they will be rendered inside the inspector for me to have a closer look at it and make changes and see those changes reflected live in the UI. The neat thing I wanted to demonstrate is the CSP part of the inspector that we built, which basically looks at all the domains that you listed inside your metadata and all the domains that are actually accessed by calls made by your view and compare them to make sure that none of them are not listed yet. So, for example here, everything's green, but if I go back to my actual code base and for example fetch some API to get info about my IP location, this will be reflected straight away in the inspector because the component has been re-rendered and I know I have the exact domain that I want that I just called listed as missing from the metadata. And I can go back inside my application and add the missing domain and now it should appear green if I reload it. Yeah, everything good. So, neat little tool. There are a lot of other features that are packed inside Skybridge, but that's one of them that we made sure to be available to builders because we've seen a lot of rejection coming from chat GPT app store submission because of missing CSP and app not working in production because of missing CSP domains. Um Just to finish up quickly if I can. Up. Uh up. This one. Yeah. Um yeah, that's all. Thank you again for your time. If you want to grab the slides and take a look later on, feel free to scan the first QR code. If you want to give a try to Skybridge, feel free to scan the second one. I will run right now a small lottery. We have ski goggles to win if you star Skybridge repo in the next minute or so. I will draw name at random and you will win a ski ball mask. Thank you very much for your attention.

</details>