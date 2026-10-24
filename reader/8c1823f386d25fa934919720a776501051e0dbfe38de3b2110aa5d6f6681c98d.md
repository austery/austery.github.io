---
author: How I AI
date: '2026-06-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZoBfQZ5utQk
speaker: How I AI
tags:
  - open-weight-models
  - model-evaluation
  - cost-efficiency
  - coding-agents
title: GLM 5.2 深度评测：开源模型能否以 3.36 美元挑战 Opus 级编码能力？
summary: 本文深度评测了智谱 AI 的开源模型 GLM 5.2。通过代码库探索、前端设计重构和长时间自主 Bug 修复三个真实场景，验证了其接近 Opus 级别的推理能力。评测显示，该模型在 HTML/CSS 设计和后端自主任务上表现出色，但在 React/TypeScript 编写上存在明显短板。最终以 3.36 美元处理 600 万 Token 的成本，证明了开源模型在特定场景下对商业 API 的替代潜力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Z.AI
  - Open Router
products_models:
  - GLM 5.2
  - Claude Opus 4
  - GPT-5.5
media_books: []
status: evergreen
---
### 开源模型的成本革命：GLM 5.2 的定位与价值

如果我告诉你，你可以用极低的成本获得 **Opus** 级别的推理能力，你会怎么想？这正是我们今天要测试的 **GLM 5.2**。这是我们一系列开源模型评测的开篇，旨在回答一个核心问题：我们是否应该继续向 Anthropic 和 OpenAI 支付“税”，还是可以本地运行这些模型并获得相同的结果？

**GLM**（General Language Model）由北京初创公司 **Z.AI** 发布，是一款**开源权重模型**（Open-Weight Model）。这意味着训练好的模型权重可以公开下载，允许你在自己的硬件上运行、用自己的数据进行微调，并检查其内部工作机制。虽然许可证各有不同，不一定完全免费，但关键在于你可以**自托管**。如果你有一台高配的 Mac Studio，完全可以在本地运行 GLM 5.2。开源模型的核心优势在于：一是成本低廉，运行自己的推理远比 Anthropic 或 OpenAI 的 API 费用便宜；二是摆脱供应商锁定，当某个供应商改变 API 条款时，你可以轻松切换。

为什么 GLM 5.2 值得关注？据 AI 社区传闻，它提供了接近 Opus 或 GPT-5 级别的智能，但成本仅为零头，且支持自托管。如果这是真的，那将是一个重大突破。前沿实验室的超智能模型正变得越来越昂贵，而开源模型在编码等昂贵用例上正迎头赶上，这绝对值得关注。

<details>
<summary>Original English</summary>

What if I told you you could get Opus level reasoning at a fraction of the cost? That's what we're going to see and test today when I take a look at GLM 5.2. This is our first of many reviews of OpenWeight and Open source models to see if we should all be paying the tax to anthropic and OpenAI or if we can run these models locally and get the same results. Let's dive in.

GLM stands for general language model and this is a model that's put out by the Beijing based startup Z.AI. So yes, this is a Chinese trained model. Now this model is open weight. You may have heard that term before but not exactly known what it means. And all it means is that the trained model weights are publicly available for download which allows you to run it on your own hardware. You can fine-tune that model on your own data and you can kind of inspect how it works. Now, the licenses for open weight models kind of depends. So, it doesn't necessarily mean you can use it quote unquote for free. But why this matters for GLM 5.2 is you can self-host this. So, let's say you have one of those chunky Mac studios at home where you want to run some models locally. You could potentially run GLM 5.2 locally. You can fine-tune it, which means you can adapt it to your purpose. And then the thing that people really love about these openweight models is they're cheap. You can run your own inference and so it can be much more affordable than API cost from anthropic or open AAI and two you're not logged into a vendor so if a specific vendor changes their API terms you can actually change what provider you use.

Now why should you be paying attention to GLM 5.2? Well, this is what I'm hearing from the breathless AI bros, and I guess again I am a breathless AI brother, is that GLM 5.2 is getting people sort of opus level intelligence or GPT5 whatever intelligence for a fraction of the cost and the ability to be self-hosted. If this is true, this is a very big deal. As we've seen, we can't always rely on the big model providers for consistent model access. And these hyper intelligent models from the frontier labs are getting very very expensive. And so any models where open weights models are catching up to the intelligence of open AI models, anthropic models, especially for coding use cases which can be quite expensive is something to pay attention to.

</details>

### 技术规格与基准表现：百万 Token 上下文与 Opus 级编码能力

GLM 5.2 拥有一个**百万 Token 的上下文窗口**，这非常充裕。但一个限制是它仅支持**文本输入和输出**，无法处理或生成图像。尽管如此，它具备现代模型应有的所有能力：**推理/思考模式**、流式输出、函数调用、上下文缓存、结构化输出以及 **MCP** 支持。从基准测试来看，在 **Frontier、SUI、Post Train Bench 和 SU Marathon** 等榜单上，它正逼近 Opus 并超越 GPT-5.5。在 **Swebench Pro** 上，它与 GPT-5.5 持平，几乎达到 **Claude Opus 4.8** 的水平，并明显击败 **Gemini 3.1 Pro**。外部基准测试表明，这是一个具备足够智能来攻克最困难编码问题的模型。简而言之，你可以获得一个能检查内部构造的开源权重模型，以更低的成本本地或通过自选供应商运行推理，而其编码能力与 Opus 4 相当。

<details>
<summary>Original English</summary>

Now, let's look at the benchmarks and capabilities of the model and then I'm going to dive right into actually using them. So, a couple of things you should know about GLM 5.2 just to pay attention to is its context window is big. It has a million token context window. So, that's sufficient. But one limitation is it only takes text in and only takes text out. So, you can't put an image, you can't get out images. It is a text-to-text model. That is one constraint of this model. That being said, it has all the capabilities that you should expect from a modern-day model interface. It has reasoning or thinking mode. It can stream its outputs. It can call functions. It can do context caching to make things more efficient. And it can output structured output and use MCPS. So, at the end of the day, this is a very capable model with the right ergonomics that we've gotten used to.

Now, what do we see from the market benchmarks on this model? So, as you see here on Frontier, SUI, Post Train Bench, and SU Marathon, it's inching up there to Opus and right above GPT 5.5 on a lot of these benchmarks. And if you look at Swebench Pro, you can see it's about on par with GPT 5.5 and almost up to Claude Opus 4.8, certainly beating Gemini 3.1 Pro. So, if you look at it against these models that we've all come to know and love, it's in the arena. It's definitely worth testing out. And the external benchmarks say this is a model with enough intelligence to attack some of our hardest coding problems. So, what I'm telling you is you can get this openweight model where you can inspect how it's actually built. You can run it locally or at least more cost-efficiently on your own inference or your selected provider's inference and it's going to code just as well as Opus4.

</details>

### 实操配置指南：在 Cursor 和 Claude Code 中接入 GLM 5.2

如何将 GLM 5.2 集成到你的编码工作流中？首先，你需要选择一个模型提供商。我使用的是 **Open Router**，这是一个统一的接口，可以访问多种商业和开源模型。注册 Open Router 账户、绑定信用卡并设置 API 密钥后，就可以开始配置了。

**在 Cursor 中配置**：进入 Cursor 设置，点击 Models 标签。你需要做两件事：第一，将 Open Router 的 API 密钥填入 OpenAI API Key 字段并启用；第二，将 OpenAI Base URL 覆盖为 `openrouter.ai/v1/cursor`。然后，在模型列表中添加自定义模型 `z-ai/glm-5.2`。完成后，在 Cursor 的聊天界面中就能看到并选择 GLM 5.2 了。

**在 Claude Code 中配置**：首先，将 Open Router 的 API 密钥和基础 URL（`openrouter.ai/api`）添加到你的 Shell 配置文件（如 `.zshrc` 或 `.bashrc`）中，并清除默认的 Anthropic API 密钥。其次，编辑 Claude Code 的 `settings.json` 文件，将模型更改为 Open Router 上的 GLM 5.2 字符串。完成这两步后，所有 Claude Code 会话都会通过 Open Router 路由请求，并使用 GLM 5.2 模型。对于 Codex 等其他工具，流程类似：找到提供商，切换 API 密钥，并将所有模型调用路由到新模型。

<details>
<summary>Original English</summary>

So, how do you actually get GLM5 in your coding stack? Let's say you're completely new to all this openweight model stuff and you want to figure out how to run these in cla or in cursor. I'm going to show you cloud code and cursor. It basically applies to codecs as well. I'm just going to give you those two examples because I think that's going to cover most of your use cases. So, first you need to choose where you're going to get your model from. And I'm still using a hosted API version of GLM 5.2. My little laptop's not going to run this thing locally. And so, I've chosen to use Open Router, which is a unified interface for getting access to a lot of different models, both commercial and open weight and open source. So, I signed up for an open router account. And then all you need to do after you've signed up for an open router account, give them your credit card, set a limit if you want to, and just set up an API key. So, I set up an API key and now I have access to this model via open router.

Okay, setting GLM 5.2 up in cursor is super easy, though it took me truly about 30 minutes to figure out the nuance here. No one has documented it. We'll put in the blog post and the show notes for you. But all you have to do is go into your cursor settings and click the models tab. And then you need to do two things. First, you need to put your API key from Open Router here in the OpenAI API key field and toggle that on. And then secondarily, you need to override openai base URL with this very specific URL. So it's open router.ai/v1/cursor. I could not find anything for a really long time that told me it had to be /cursor, but it is /cursor. And you need to toggle that change on. The second thing you need to do is add Z-IGLM-5.2 to your models. So you simply click view all models, you add a custom model, you add that field in and you will be able to access this model.

There is luckily a little bit more instruction on how to do this for cloud code. And so there is this page on open router the docs page that shows you how to connect claude to open router and then I'll show you how to connect your specific model for cloud code. It's pretty simple as well. You need to get your open router API key and that URL which they have here and you need to add to your shell profile. So for people who are not super technical who have just cla coded their way into terminal, your shell profile is the file that manages your settings in the terminal. It's going to like instantiate a bunch of environment variables. It's going to set a bunch of settings. And so you need to edit your shell profile. It's usually zrc or bash rc depending on what profile you use. And add these lines right here to that file. You can also, this says open it in nano. If you're not feeling fancy, you can just find this file in your finder or in your file directory and open it in whatever code editor of choice and add these lines which include your open router API key, the base URL which does not contain /cursor. It's just open router.ai/ API and your off token here. And then you clear the default off token for anthropic. The second thing you need to do is edit your quad settings.json which is includ settings.json. You can open up again in whatever code editor you want and change your model to the GLM 5.2 string from open router. So here I've put it in. And so with those two things, any cloud code session that I open up will have the open router API key. It will route all requests through that open router API key and it will set the model to GLM 5.2. There's a very similar process that you'd follow for codeex, but the TLDR of setting up your cursor cla codeex with a new open weights model is to find a provider, switch out your API key and route all your model calls to that new model.

</details>

### 实战测试一：代码库探索与架构可视化

第一个测试是评估模型探索现有代码库的能力。我让它分析 Chat PRD 代码库，描述其架构和近期发布的功能。它完成得相当快，并给出了一个很好的概览：这是一个 Next.js 全栈应用，架构清晰，并准确指出了过去六周我们主要在做 Chat v2 稳定性、计费、Lenny 推广以及安全与依赖管理。这非常准确且快速。

接下来，我让它将分析结果转化为一个 HTML 页面，以可视化方式展示应用架构和路线图。它创建了一个包含架构概览、核心产品支柱、近期发布列表和未来路线图的页面。最让我印象深刻的是，它准确捕捉到了我们品牌色——Chat PRD 粉，而不是像 GPT 那样给出难看的绿色和海军蓝，或像 Claude 那样总是给出橙色。它甚至正确地指出了我们正在进行的集成合作、企业级运动、成本与性能优化以及知识检索等方向，这与我们的实际工作完全吻合。这是我第一次在 Claude Code 中运行开源权重模型，结果相当令人满意。

<details>
<summary>Original English</summary>

So, the first thing I'm going to do is just see how good it is at exploring an existing codebase and telling me a little bit about it. So, I'm in the chat pd codebase and I'm just going to say here, this is the chat PRD codebase. Please explore it and tell me a little bit about its architecture and the most recent things we have been shipping on this codebase. So this is going to go through my codebase and we're just going to explore how good it is at independently auditing, reviewing, and understanding the structure of a codebase from zero. This is one of the most common tasks that you would do as a software engineer is really getting oriented. And it's a good reflection of its ability to run autonomously, its ability to use its context window effectively, and its general sense as a software engineer. It was actually pretty fast and it came back with a pretty good overview. So, it is a next app. It's got the full stack. It's got a nice architecture here of what it looks like. It's talked about different integrations we have and what we've been shipping in the last six week, which is our chat v2 stability. Absolutely. And then some billing and Lenny promo stuff that we've been working on as well as security and dependency hygiene. So this is actually pretty correct. It was very fast and very accurate.

Let's make it something that we can visualize a little bit more and see if it does a good job communicating agent to human. And we all know that this is the year of HTML. So I'm going to say turn this into an HTML page that can communicate the overall architecture of the app and give a sense of the upcoming road map. You can use whatever components you want to make this look good and communicate to me the end developer the major pieces of the architecture and product strategy. Give me a page to pull up when it's ready to review. Okay, it's creating this HTML page for me. It's told me to approve the HTML. I'm going to pull it over cuz it does not look bad, you guys. Um, so this is the chat purity architecture and road map review. Right out the gate, it's like slop adjacent. We have blurpal on here. That's that blue purple indigo color that we love, but it's not ugly. So, let's take a look at the content. Well, at the high level, it does look correct. Wow, we've merged almost 3500 PRs. We've done a lot of PRs. It's giving me a good overview of the core pieces. Oh, this is really great. This is the anatomy of a chat turn. So how the core piece of our application actually works, some product pillars which are our chat, our integrations, documents and collaboration as well as billing which also sounds correct. And then it's given me a list of recently shipped things and then road map and direction. This is actually the piece where I'm most uh impressed. One, this looks real cute and it got the chat PRD pink which not all models get. GPT wants to give me these like ugly green and navy colors. Claude wants to give me clawed orange all the time. But look at this GLM gaming chat PR pink. I'm very happy. And so it's given me what we're working on in flight. And then let's see what it suggests should be up next for our road map. Integrations partnership and enterprise motion cost and performance and then knowledge and retrieval. Spoiler alert, these are actually the things that we're working on and a couple conventions about writing our code. Um, which is quite nice. So, I don't know guys, this is pretty good. This is the first time I've run an open weights model inside Claude Code and I have to say I am quite happy about it.

</details>

### 实战测试二：前端设计重构与品牌一致性

第二个测试是让 GLM 5.2 重新设计我们网站“How I AI”的头部 Hero 区域。这个区域有现成的设计系统，是检验模型能否匹配现有设计风格而非生成全新设计的绝佳测试。它给出了一个计划并执行了。结果如何？我不讨厌它，但也不算特别喜欢。我喜欢的是，它按要求将“AI Workflows”作为更好的行动号召，并添加了漂亮的悬停效果。它还加入了一些元数据和价值主张，比如目标用户、更新频率和剧集数量。侧边栏的“收听节目”小部件被设计得更像一个播放器，集成了 YouTube、Spotify 和 Apple Podcasts 的链接。不过，侧边栏播放器的颜色过于鲜艳和宽大，与我们的设计系统不太协调。我给了它反馈，让它重新调整。第二次迭代使用了更低调的黑色行动号召，但左右存在一些不平衡。尽管如此，考虑到它的速度和成本，这个结果并不令人失望。它几乎和 Cursor 的 Composer 一样快。我认为，只要模型有良好的审美，我们并不总是需要使用最昂贵的模型。GLM 5.2 在设计工作上表现相当不错，特别是当你有 `design.md` 或其他设计指南作为锚点时。

<details>
<summary>Original English</summary>

So what I have up here is the ChatPD website, but specifically our how II landing page and blog where we put every single episode and a summary of those episodes up on our chat PRD blog. So, this is a pretty highly trafficked part of our site. And we redesigned this a couple times using AI, but I want to do it again. And there's a specific piece of this page I don't really love, which is this header section. And so, we're going to have GLM 5.2 just make a pass at redesigning this header section. And let's see how it does. So, I'm going to say here, let's redesign the header hero section of the How I AI landing page where all the How I AI blogs are the part that says AI workflows and stories from the experts through the cursor credit claim. I want to redesign it so it is higher quality design. It is a better call to action to workflows and it helps with anything we need on SEO. Design whatever you like. Looking forward to what you make. Now, I've told it to redesign this hero section. It's going to run it through this new model, and we're going to see if its ability to redesign even a small section of the page will give us AI slop or if it will give us something a little higher quality. And the reason I like to test on the chatd marketing site is it has an existing design system and there are specific things that we really like to see in chaturd design. So this will be a good test to see whether or not it can match to an existing design system versus generating a completely novel design like we saw in the architecture overview.

Okay, it says it has a plan and executed that plan. Let's look at it. You know, I don't hate it. I don't quite love it yet, but it's not bad. What do I like about it? Well, I like the fact that the AI workflows as requested are a much better call to action. It also has this nice hover effect on it. I do like that it put sort of some metadata here and some value propositions on who it's for, how frequently we drop, and how many episodes we have. And I do really like this little sidebar widget um that makes the listen to the show, the calls to action to YouTube, Spotify, and podcasts, Apple Podcasts, look a little bit more like a player. I'm not sure what this little square in the corner is. And then I do think this copy here is it might be what it was before, but looks pretty good. I would just say I don't love fully all these colors in the sidebar player. So, I'm going to give it that feedback and say I really like this except for the listen to the show sidebar. YouTube, Spotify, and Apple Podcast are very bright buttons. They're super overwhelming and they're very wide for the text that's in it. I think this component could look a lot higher quality and a lot better for our specific design system. Can you take another pass? Let's see what it comes up with. But I will say for the speed and for certainly the cost, this does not make me unhappy. And I think we would all question how much intelligence do we need to put towards this specific problem. And as long as the model has good taste, I don't need to be fancy and use the most expensive one. So, I would say just first glance, first pass. GLM 5.2 is pretty good at design stuff. And maybe we should all be switching over to it, especially if you're anchoring in something like a design.md or other design guideline or design system where the model can really anchor on it. I do like this a little bit better. It went with a sort of black uh call to action, a lot more subtle and a lot smaller, but there's some misbalance between the left and right. But again, it's pretty fast. In fact, it's almost as fast as Composer is, which is a model by Cursor that I use really frequently. And so, I think this is pretty good. And I would definitely put GLM 5.2 in the rotation for design work.

</details>

### 实战测试三：长时间自主 Bug 修复与成本核算

最后一个也是最复杂的测试是长时间自主运行的任务。GLM 5.2 被宣传为具有很强**自主性**的模型，能够处理长时间运行的任务。我给了它一个常见任务：拉取过去 72 小时的 Sentry 错误和 Vercel 日志，并基于观察到的 Issue 构建一个优先级的 Bug 修复计划。这个任务在我录制播客的 30-45 分钟内一直在运行。它首先构建了一个待办计划，执行了工具调用和 MCP 调用，读取了输出，甚至请求我授权访问 Vercel。然后它开始整合一个 HTML 格式的计划。

然而，在编写 TypeScript 时它遇到了严重困难，出现了大量错误。这让我一度非常失望，因为 React/TypeScript 是我使用这些模型 98% 的用例。但最终它成功编译了。它从两个来源拉取了数据，构建了一个包含 20 个 Sentry 错误、5 个 Vercel 日志信号和 14 个计划修复的优先级计划，并以一个漂亮的暗色模式 Canvas 呈现。它甚至给出了两个 P0 级问题，并提供了按事件量排序的详情和运行时日志信号。最终的计划非常清晰，看起来就像是 Cursor 原生的一部分，还提供了建议的修复顺序。虽然它在编写 React 代码时速度较慢，但最终产出的 Bug 修复计划质量极高，这正是我需要的。

那么成本是多少？通过 Open Router 查看使用情况，我处理了约 600 万 Token，花费了 **3.36 美元**，缓存命中率为 72%。大部分 Token 消耗在 Cursor 中那个 45 分钟的长时间任务上。与 Opus 或 GPT-5.5 的成本相比，这简直是“白菜价”。因此，我会继续在 Cursor 和 Claude Code 中使用它，看看它是否能处理我的大部分任务，甚至可能考虑购买更多硬件来本地运行。

<details>
<summary>Original English</summary>

Let's wrap with a much more complicated use case though which is a longrunning autonomous use case. So part of how GLM 5.2 has been advertised is that it is a very agentic model that is capable of handling very longrunning autonomous tasks and solving those over time very similar to the claims about opus and GPT 5.5 or whatever. And so I gave it a common task that I like to give a lot of my longrunning models, which is pulling issues and error logs and then making a plan for fixing those error logs and ultimately shipping those fixes themselves. And so before I started this podcast, I started with this specific prompt, which is pull the last 72 hours of century errors and versel error logs and build a prioritized plan of bug fixes based on observed issues. And so this has been running the entire time I've been recording this podcast, probably about 30 45 minutes, even though you all will get a much shorter cut of this episode. And you can see here it did the thing that most models do, which is it built a to-do plan. It ran tool calls and MCP calls. It read the output. It actually asked me to off into versel. So that was great. It ran several versell calls. And now it is putting together a plan in HTML I believe for us to review and decide if these are the priorities for chat purity.

Okay. quick intermediary peak from the reasoning minds. It is really struggling to write TypeScript. So while it can do a long running task, it is having some TypeScript errors. So we may be sitting here for a while waiting for it to write the plan as opposed to its intelligence on getting the plan. So hold tight. We will be right back and I will give you my opinion whether all this waiting was worth it. Oh my god, guys. It really is having trouble writing JavaScript right now. I can't. So, so okay, we got over the hurdle of it can write HTML. Is very good at writing HTML. The HTML and CSS is welldesigned and looks good. I think it can query tools and look at data very well, but I don't think it can write React, which is 98% of what I do with these models. So, if this is a failure state, we're going to have some trouble. Oh, it compiled cleanly. I spoke too soon. I just had to complain to the model gods. And we are back. It's going to clean this up and hopefully show me its plan on how to fix all the errors in chat beardy.

Okay, here we are. It pulled the last 72 hours from both sources and built a prioritized plan in a canvas. I can open. Here is my canvas. Again, it does not look bad. I love that it's for an engineer. So, they made it in dark mode. It says we have 20th century errors, five versell log signals, 14 planned fixes, and then gave me two P zeros. Not happy about that. This is something that was not coming through on um the signal to noise ratio on some of our Sentry issues. So, we will fix that. And then we need to look at this. I think this is a legacy Google Drive integration, but we will take a look at that as well. It's given me events by volume and then um runtime log signals and whether or not they are high severity or low severity and then gave me this beautiful prioritized fix plan. Y'all, I was really disappointed by its speed in writing React, but this is exactly what I need. This is super helpful. It even looks like it's supposed to be part of cursor, which I really love. And I can go through and start to rock through these fixes. It even gave me suggested sequencing. I'm not mad. So, I spoke too soon being disappointed about the performance on this longrunning task. I actually think it's pretty good and I think I'm going to ship all these fixes.

So, what's my takeaway with GLM 5.2? It's good. I would use it for front-end work. I would use it for longrunning backend tasks. And the test that we were testing is how much did it cost me? And if you pull up Open Router and your usage on this API key, I spent $3.36 on about 6 million tokens. Cash rate was pretty good at 72%. I spent most of those tokens on that 45-minute longrunning task in cursor to find all my issues in century and versel and just a few in claude code. But if you compare this to the cost of an opus or a GPT 5.5, this is a steal. So I think I'm going to keep it running in cursor for a while. Think I'm going to keep it running in cloud code for a while. I'm going to see if it can handle most of my tasks and maybe I'll have to buy some more hardware and start running this stuff locally.

</details>