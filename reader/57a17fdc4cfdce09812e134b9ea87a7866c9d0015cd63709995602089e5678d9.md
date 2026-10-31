---
author: AI Engineer
date: '2026-08-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=RmS5s6Wbin4
speaker: AI Engineer
tags:
  - personal-ai
  - cloud-infrastructure
  - vibe-coding
  - security-sandbox
  - durable-objects
title: Gadgets：重构云基础设施，实现真正安全的个人化AI协同编程
summary: Cloudflare Workers 创始人 Kenton Varda 探讨了个人 AI 协同编程对传统云基础设施的挑战，并展示了名为 Gadgets 的新型应用开发平台。该平台基于 null-origin iframe 沙箱和 durable objects 架构，实现了对 AI 生成代码的安全隔离与状态共用，解决了个人定制软件的合规与安全漏洞难题。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cloudflare
products_models:
  - Cloudflare Workers
  - workerd
media_books: []
status: evergreen
---
### 重构分发悖论：为何传统云架构无法承载个人化 AI 编程

传统的软件分发模式建立在一种“象牙塔式”的单向传递机制上。**开发者**在顶层构建单一版本的应用，将其部署到云端服务器，再将这个特定的版本分发给成千上万的**用户**。然而，这种一刀切的中心化模式无法满足长尾化的个性化需求。当用户提出新的功能诉求时，产品经理会将需求整理入 Jira，最终这些需求往往被无休止地搁置。即使开发者试图去满足所有的特殊案例，代码库也会迅速堆积大量的条件分支语句，导致项目演变为难以维护的灾难。为了从根本上摆脱“为了支持新功能而不得不重构整套插件系统，进而导致开发周期无限拉长”的恶性循环，我们需要一种由 AI 驱动的新型替代方案。

在 AI 时代，理想的画卷是：开发者仅提供应用的基础版本，而用户若需要个性化功能，可直接吩咐其专属的 **AI 代理**（AI Agent）为自己实时编写并植入专属的局部功能。然而，过去 15 年来由 Apple 和 Google 主导的移动生态，在安全防范的借口下设置了极其严苛的签名审查机制，甚至导致在某些地区安装未经签署的自定义软件比购买武器还要困难。虽然 Web 生态为我们提供了一个可以自由构建的避风港，但过去 25 年沉淀下来的经典**云架构**（Cloud Architecture：以服务器为中心、多租户共享单一运行实例的分布式软件架构）依然是背道而驰的——它要求所有用户运行同一个被官方赐福的、无法进行客户端修改的软件实例，彻底阻断了个人化定制的可能。

<details>
<summary>Original English Source</summary>
My key point is personal AI codegen breaks traditional cloud infrastructure. And to clarify what I mean about that, the word personal here is doing a lot of work. It's loadbearing as cloud would say. My point is that if we want to see this future where everyone has personal apps and can personalize the apps that they run, the infrastructure we're using today for software in general is not the right thing and we need something completely different.

To explain what I mean, think about the way that software is produced and distributed today. You have a developer in an ivory tower who builds an app and then sends it down to the users who use the app. Many of them are happy with it, but some of them are not. Some of them say, "This app needs some additional features for my use case," and so they go to the developer and they say, "Oh great developer, will you please grant my feature request? Your app is literally unusable without it." And so then the developer's representative, the product manager, takes these feature requests and files them into Jira where they are never seen again.

But sometimes the product manager sees a feature request and says, "Ah, I want that too," and then that feature request goes onto the road map and the developer works on it. The developer is implementing all these features that each one is only used by a small subset of users, and each one is adding all these if statements to their code and making things messy. They don't like it because the codebase is becoming a mess and each of these features is really kind of boring to implement.

And so the developer says, "Ah, I know what I need to do. We need a rewrite. We need a new architecture that has a plug-in system." And then every one of these features can be a plug-in and it can be nice and clean and easy to build, and the core can stay clean. And so the developer goes off and starts working on the new architecture with the plug-in system. And there are still feature requests coming in and the developer says, "Well, we can't do those features yet because we need the plug-in system. This will be so much easier once we have the plug-in system. And if we do it now, we're just delaying that and we'll just have to redo it later anyway." And so the years go by and the new architecture is not ready yet and none of the features are being implemented and people are saying, "What are they doing? This developer has given up their product." and everybody is sad.

So AI seems to present a new alternative to this. What if the developer could create their app, the first version of their app, give it to the users, and the users if they need a new feature could ask their AI agent to write that feature just for them, add it to the app? Then everyone gets the features they need. No one is bogged down in everyone else's features, and the developer gets to keep the core app nice and clean and beautiful.

But there's a problem with this, which is that none of the infrastructure we build software on today is like remotely designed for this. You've got Apple and Google for the past 15 years gatekeeping their systems to the point where there's like five companies that can build mobile apps now because everyone else has been banned. And it's almost like easier in the United States to buy a gun than it is to get access to your own phone to install unsigned software. You go to Google and you say, "I want to install unsigned software." And now they're going to say, "Oh, whoa, hold on, buddy. You seem upset. You should go home and think about this. If you still want that unsigned software in 24 hours, then you can come back and talk to us."

Fortunately, we have a workaround for all of that, which is the web. On the web, everyone can build whatever they want. And it turns out it's fine. It's not the security disaster that Apple and Google keep telling us would happen. So you can build whatever you want on the web, but there's a different problem on the web, which is that for the past 25 years of cloud architecture we've been running in the wrong direction. When you distribute a web app, you run it on your own server, put it on your server, and then users send requests to your server where the one version of your app, the one blessed version runs for every single user. And so that's convenient for developers. That's why we've done it, so the developer can make sure things stay updated and everyone's on the same version. But it obviously means that users cannot customize their apps.

So last year vibe coding comes along and we have all these vibe coding platforms out there, and most of them are targeting web apps because that's the easy thing to target, but they're all targeting this existing infrastructure which is actually like not the right way to do it. We need something entirely different. And hence my point.
</details>

### 从文档到小组件：重塑云时代的协作与共享范式

针对现有基础设施的缺陷，我们需要引入一种类似于办公套件的全新范式。在 Google Docs 中，用户管理的是成百上千个文档，而在这种新型的 **Gadgets 架构** 中，用户拥有的则是被称为 **小组件**（Gadgets: 包含独立代码和局部状态的微型应用运行实例）的自包含应用。每一个 Gadget 都是一个拥有独立代码库和私有数据的软件实例。为了将应用逻辑与协作逻辑解耦，**Gadgets 架构** 将协同共享模型下沉至基础设施平台层实现，而不是像传统应用那样在业务代码中堆砌复杂的权限系统。

在这种设计下，当用户通过“蓝图”（Blueprints）实例化一个小组件（例如一个看板、白板或幻灯片工具）时，该实例仅对应单一的数据主体（如单个幻灯片文稿）。如果需要创建另一份文稿，则生成一个新的 Gadget 实例。每个 Gadget 的共享与访问控制均由底层平台直接托管。用户只需点击生成分享链接，平台就会确保数据流的隔离与安全分发。这样一来，应用本身的代码无论被 AI 如何修改，都绝无可能因逻辑设计失误而泄露其他用户的敏感数据。

<details>
<summary>Original English Source</summary>
So what I want you to understand about this environment is this is not like your typical vibe coding environment where you're deploying apps to a web page. This is, you need to think about more like an office suite. So think about Google Docs. You open Google Docs, you have a bunch of documents, hundreds, maybe thousands of documents. You open one, you edit it, you share it with people. This is the same thing except instead of documents, you have gadgets. And each gadget is an application with code. They can all be different code.

I have an app here which is like a collaborative whiteboard app. This is a one-shot prompt. I have an app here to help me filter Spanish email. So I made a little app to help me do that. A gadget. I have a gadget to help me sort pull requests that I need to review on GitHub. And those are things that I just vibe coded from scratch.

But we also have this concept over here of blueprints. And a blueprint is someone made a gadget and they decided that it was useful and they took a blueprint of it, which is just taking the code, exporting the code without the data, which they can then share with someone else, and then other people can instantiate gadgets from these blueprints. So we have like a document editor app here, a Kanban board, and a slide builder.

So this slide builder was built by my colleague Philip here who's a product manager at Cloudflare, and of course these days all product managers are also prolific engineers. So he vibed this in an afternoon I believe, but if I instantiate this gadget I get this nice little slide deck. It has things I can edit and so on. And if I shared it, it would work well.

So an important point here is that when I instantiate this app, it is only for one slide deck. If I want multiple slide decks, I make multiple instances of the gadget, one for each. And the reason for that is that all gadgets are shareable and you can collaborate with other people on them, and the sharing model is implemented by the platform instead of by the app itself. So if I click up here, I get sort of a share dialogue kind of like a Google Docs share dialogue. I can create a share link and send it to people. And because each gadget is just the one thing that you want to share, that means that the platform can implement the sharing model and the access control such that the gadget itself can't possibly get that wrong.
</details>

### 安全的双端沙箱：彻底免疫 AI 生成代码的越权漏洞

当允许 AI 代理自由读写和重构应用代码以支持定制化功能（例如为幻灯片组件自动生成 SVG 渲染代码或居中对齐排版）时，安全风险将呈指数级上升。AI 写入的代码可能无意中引入 **跨站脚本攻击**（Cross-Site Scripting: 攻击者在网页中注入恶意脚本的安全漏洞）漏洞。为了在根本上杜绝该风险，**Gadgets 架构** 采用了前后端双沙箱的极致安全隔离方案：

* **前端沙箱化**: 整个 Gadget 的用户界面全部强制在一个 **无源 iframe 沙箱**（Null-origin iframe sandbox: 浏览器中禁用同源策略且不携带任何域凭证的安全沙箱机制）中运行。通过极其严苛的 **内容安全策略**（Content Security Policy: 限制资源加载与执行以防御注入攻击的浏览器安全机制），彻底阻断了它与外部世界以及父级框架的数据通信，使其无法读取任何全局 Cookie 或敏感本地存储。
* **双向通信通道**: 前端沙箱与父框架之间仅允许通过限制性的 `postMessage` 通道传递数据，并在此之上封装了 **Cap'n Proto RPC** 系统，将序列化的请求转发回服务端的 Durable Objects。
* **服务端微沙箱**: Gadget 的服务端代码同样运行在 Cloudflare Workers 的动态沙箱中，该沙箱被剥夺了任意访问互联网的权限，仅被允许对专属于该实例的 Durable Object 进行状态读写。

在这种彻底的无源隔离架构下，即使 AI 编写的代码中包含了恶意的 JavaScript 注入，攻击脚本既无法外发任何敏感数据，也无法访问任何宿主环境的凭证，从而使传统的 XSS 安全缺陷在物理层面上失效，为 AI 的自由创作提供绝对安全的保障。

<details>
<summary>Original English Source</summary>
So I'm going to go over to actually another instance of the same slides app. This is the slides I originally wrote for this talk, which yesterday I decided these slides were trash and I threw them all away and rewrote it. But the reason they're bad is entirely my fault. It's not Philip's fault. It's not the software's fault. But this can still serve as an example to demonstrate some of what you can do on this platform.

So if I click on here, I can see the conversation. And of course, I didn't edit the slides myself by hand. I asked the agent to make them for me, right? And every app in this platform automatically integrates with agents so that you can do that. And so what I did is I gave Claude a link to this document, this Google doc where I had described all of the gadgets that I wanted or all the slides that I wanted in my presentation. And crucially though, this is the interesting point. I said, "If you need to add any new features to the slides app itself to support some of these slides, feel free to do so." And it did.

Claude read all the code for the app and read my doc and said, "Yes, actually, let's see. Slide three needs a strikethrough formatting. That's not implemented. We can add that. Some of the slides require things to be centered. And you know, I guess Philip's design taste is too good for centering text. But my more pedestrian taste called for some centering. And that's okay. Claude can add that." More interestingly, slides five and six here, I asked for this like really crappy diagram of the cloud, right? And the app didn't support sort of like arbitrary diagrams. It supported, you know, box diagrams and arrows and such, but not an arbitrary drawing like this. And so Claude said, "Okay, that's okay. We can add a feature. We'll add a feature that allows you to insert a bunch of SVG. Just paste it into this box here. And now it becomes part of the slide."

And now that's not very useful for any human, but it was perfectly useful for Claude who then generated the SVG. Now, at this point, you might be looking at this and saying, "That's a little scary. SVG can contain JavaScript. Are there XSS bugs here?" And the answer to that is it doesn't really matter because of the way this environment is set up.

So the UI that you see for the app here is running inside a null origin iframe sandbox with content security policy set so that it basically cannot talk to anything, any of the rest of the world, can't access any cookies, so on. The only thing it can do is post message to the parent frame and through that post message channel we set up a Cap'n Proto RPC session which forwards onto the server and all the way back to the server code for this gadget, which is this code here, which is written as a durable object on Cloudflare workers. And basically that means this server code runs in a dynamic worker sandbox on the server side where it too is prevented from talking to any of the rest of the world. So now we've set up this environment where there's a vibecoded client and a vibecoded server. They can only talk to each other and produce the UI for the user. And so if you have an XSS bug, it actually doesn't end up mattering because these can't leak anything. They're prevented from doing so. And basically there is no security bug you can have in this code that matters. And that makes it safe to go and do things.
</details>

### 轻量化与去数据库设计：基于 Durable Objects 的离线运行时

整个 **Gadgets 架构** 深度依托于 Cloudflare Workers 无服务器计算环境。该系统彻底摒弃了繁重的 Docker 容器化设计以及传统的集中式数据库体系，全面转向轻量化、亚毫秒级启动的**边缘计算对象**（Durable Objects: 结合了强一致性存储与单例执行特性的微型有状态计算单元）。所有的应用状态和协作逻辑直接驻留在 Durable Objects 的内存与持久化存储中，带来了极高的并发性能与近乎为零的静态托管成本。

更重要的一点是，这套系统完全支持在本地无网状态下运行。通过开源的 Workers 运行时 **workerd**，Gadget 能够顺畅地在用户的本地笔记本电脑上提供全套服务，并可以与 Home Assistant 和 Spotify 等本地生态无缝对接，非常适合用于离线智能家居自动化等长尾场景，将云端架构与本地运行时的界限彻底抹平。

<details>
<summary>Original English Source</summary>
So everything you see here is built on, everything except for the LLM is built on Cloudflare workers. A lot of people don't know this but you can actually build complex apps on workers. There are no containers involved here. There's just dynamic workers. There's no database involved. It just uses durable objects.

And furthermore, all of this is actually running locally on my laptop, which is why it doesn't matter that the internet didn't work because this is all running on workerd, which is our open source runtime. A lot of people don't know this. The Cloudflare workers runtime is open source. You can self-host it. And I'm excited about that because we have in here a Home Assistant connector and a Spotify connector. And I want to run this in my basement and use it to do home automation tasks.

So this is where though I have to give a little bit of an apology. A couple of months ago when I submitted the proposal for this talk, this was like a side project I was working on and the plan was I was going to come here and I was going to present it and then I was just at the end of the talk going to yeet it onto GitHub so that everyone could go and download and play with it themselves. In the last couple of weeks, there's been a lot of excitement inside Cloudflare and this has become a more serious project. And so last Thursday, Sven, our CTO, pulled me into a room and said, "Kenton, I don't think you should yeet this. I don't think this is yeet material. I think we need to be more careful and disciplined and intentional about how we release this. So, let's hold it off for a few weeks." And I was pretty upset about that because I promised in the abstract that I was going to open source it, but sorry. That's not happening today. It will happen soon though. And I wish the silly counter worked because GPT makes some silly counters, but oh well, it's not a big deal. And that's all I got.
</details>