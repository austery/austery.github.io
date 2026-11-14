---
author: AI Engineer
date: '2026-11-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZJjRgvjhq3M
speaker: AI Engineer
tags:
  - financial-services
  - wealth-management
  - plugin-architecture
  - mcp-connections
  - audit-logging
title: OpenAI 金融服务研讨会：ChatGPT for Work 与 Codex 在财富管理中的应用及插件架构解析
summary: OpenAI 应用 AI 工程团队在面向金融服务的研讨会中，展示了如何利用 ChatGPT for Work 和 Codex 处理金融数据与财富管理案例。 演讲者介绍了内置数据、模型微调及成果物生成能力，并重点讲解了插件架构如何通过 MCP 连接实现系统回写与审计日志存储，以满足合规需求。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - ChatGPT for Work
  - Codex
media_books: []
status: evergreen
---
<!-- chunk 1/12 -->

### 开场与团队介绍

大家早上好。很高兴看到即使是节假日，这里也来了这么多人。今天是周一上午 9 点整。我是 Stephan Fabri，来自 OpenAI 的应用 AI 工程团队，旁边是 Oliver，我们在现场的观众席里还有另一位团队成员 Dom。所以在会议期间，如果你不想公开提问，也可以找我们的第三位同事交流。

<details><summary>Original English</summary>
[music]

So hello everyone. Uh glad that you know there's quite a crowd here even if it's holiday. It's Monday morning. It's 9:00 a.m. So I'm Stephan Fabri. I'm part of the open AAI the applied AI engineering team alongside Oliver and also we have in a crowd another part of uh our team Dom. So feel free during the session you know if you don't want to ask ask question we also have a third man that you can leverage.
</details>

今天的环节是一个时长两小时的研讨会，形式会是互动的。稍后大家会更详细地实际使用 ChatGPT for Work 和 Codex。我们非常想向大家展示我们的产品在金融服务领域的能力：你如何将金融数据、大语言模型、AI 智能与正确的输出形式融合在一起，来助力日常业务。今天我们打算更多聚焦在一个财富管理的案例上，因为我们知道现场有很多人来自资产管理公司和投资银行，所以我们认为这可能会是一个有趣的案例。

<details><summary>Original English</summary>
So today's session is going to be a two-hour workshop so it's going to be interactive you are going to use chib work and codeex more into the detail later and we really want to kind of show you the capabilities um of like our product within the financial services space. How can you merge, you know, financial data, you know, LLM, AI, intelligence, and the right output to put everything together to help like your day-to-day business. So, today we're going to focus more on a wealth management case given like you know, we know in the crowd there are a lot of people coming from asset manager, investment banks. So, we thought that um this could be like an interesting case.
</details>

给大家介绍一点背景：我们团队主要侧重于与客户互动。我们整天都在与像你们这样的一些人共事，真正去帮助理解：我该如何将这个模型落地到自己公司投入生产，并从中发掘出最大的价值。因此，你在我们这里投入的每一美元，我们的任务都是切实帮你实现从中提取价值的最大化。无论这涉及运营、智能体，还是代码编程生产力，这大致就是我们的日常工作，并且我们团队主要负责纽约这边的金融机构。关于我就介绍这些，交给你，Oliver。

<details><summary>Original English</summary>
So to give you a little bit of a background like uh our team focus mostly on interacting with clients. So we spend all our days working with like some of you guys helping really to understand you know how can I transform like put this model into production at my company and extract the maximum possible value. So for each dollar that you invest with us, our task is really to help you maximize the value extract from it. So no matter if it's operation, if it's an agent, if it's like a code coding productivity, that's more or less our day-to-day and our team covers mostly like the financial institution here in New York. So that's about me, Oliver.
</details>

是的，我在同一个团队工作，在金融服务领域、资产管理公司以及投资银行也都有很长的从业背景，但我骨子里是个构建者。所以今天我们也想聊聊如何基于该平台进行构建，并向大家展示这里的用例。很高兴能提供帮助，我与大客户合作，现场大概有几位是我之前见过的。所以如果大家来找我们，想通过 API 或 Codex 解决问题，我们就是合适的人选。

<details><summary>Original English</summary>
Yeah, I'm working in the same team also long history in financial services, asset managers and also investor in banking but I'm a builder at heart. So today we want to talk about also how to build with the platform um and show you the use case here but yeah happy to help um I work with big customers um in the room probably a couple of people I have seen already. So if you approach us want to solve a problem with the API or with codeex yeah we are the right people.
</details>

### 工作空间访问与日程安排

在继续之前，能否请大家扫描这个二维码并填写你的信息，主要是电子邮件地址。原因是我们要为你开通 OpenAI 内部特定工作空间的访问权限。这样你就能获取这些金融数据，并且在本次研讨会期间拥有无限制的 Token 配额。此外，我们还开启了超快模式。这是针对我们最新模型的一个特定模式，涵盖 6.1 soul 和 six Astra，平均生成速度可达每秒 300 个 Token。我认为对于研讨会来说，这能让大家更便捷、更快速地去创建内容。稍后我还会展示这个二维码，但请务必填写，这非常重要，否则你将无法获得访问权限。

<details><summary>Original English</summary>
So before continuing I can I ask you to scan this QR code and put your uh information is mostly the email address. The reason is because we want to give you access to a specific works uh workspace um within OpenAI. So you're going to get access to the financial data and you're going to have unlimited token for the session. Plus we also enable the ultraast mode. So is a specific like mode for like our latest model. So 6.1 soul and six Astra that reaches like a 300 token per second on average. So I feel that like for a workshop makes it easier to like you know create something in a faster way. So I'm going to show the QR code later but please uh it's really important otherwise you're not going to get access.
</details>

>> 也提醒一下现场的同事，如果你现在需要或者稍后进场，可能就是坐在那里的各位。我们需要这个来获取访问 ChatGPT for Work 网站的权限，基本上这就是我们所需要的。

<details><summary>Original English</summary>
>> So just maybe our colleague in the room also if you need it now you come later maybe just people sitting there. So we need that to get access to the sh GBT work website basically. So that's what we need.
</details>

大致预览一下今天的日程。这是一个暂定安排，实际可能会有些超时或穿插调整。我们先会就金融服务版的 ChatGPT for Work 以及整个生态系统做个快速介绍；接着我们会花 10 分钟着重进行环境配置，确保大家都能访问金融服务版的 ChatGPT for Work；然后会有两个主要环节，都将由 Oliver 主持，第一部分我们会更多关注 Work，接着我们会转向 Codex；最后我们留出了大约 20 分钟，主要用于提问、交流整体反馈，以及探讨该领域正在发生的变化，解答大家可能提出的任何问题，无论是在编码层面还是在更多行业层面的。

<details><summary>Original English</summary>
So um just kind of a preview of the session today. This is kind of like a tentative schedule. So probably we're going to like go over and mix and match a little bit. But we're going to give you a quick introduction uh on like chibi for work uh work for financial services and like kind of like more the ecosystem. Then we're going to spend 10 minutes focusing a little bit more on the setup making sure that all of you guys can access um judg work for financial services and then we're going to have kind of like two main session that I'm going to be led by Oliver like the first one where we're going to focus more on work and then we're going to move to codeex and finally um we kept like 20 minutes mostly like for question and kind of like general feedback and like about uh you know what's going on in the space and you know whatever question that you might have like both on the coding and also like more on the industry wise.
</details>

### 面向金融服务的产品与内置数据

现在让我们快速介绍一下我们的服务。大家可能知道，我们主要有三个核心界面、三个主要的接触面。ChatGPT 是大家熟知的原始版本；ChatGPT for Work 基本上更侧重于知识工作者，它能运行智能体，支持插件，但并不像 Codex 那样，Codex 更多是面向工程类任务的。这就是我们目前提供的三个交互界面，正如刚才提到的，我们今天会先聚焦在 ChatGPT for Work，然后再讲 Codex。

<details><summary>Original English</summary>
So let's now go to a quick introduction on our services. So as you probably know we have three main interfaces three main surfaces that we use. Chajibbt that is like you know the original one we have chibbity work that is basically something that it's more focused for knowledge workers so it's like you know it can run agent it can work it works with plug-in but it's not really like codeex that is more meant for like engineering type of task. So these are the three surfaces that right now we are offering and as already mentioned we're going to focus on chargibility work first and then codeex.
</details>

我们在 ChatGPT for Work 和面向金融服务的产品中所做的，基本上是尝试打造一款面向企业的产品。虽然底层模型是一样的，但产品本身是专门针对金融服务类用户进行了微调定制的。这款产品主要有三个组成部分：首先是数据。我们有一些内置数据，我认为质量相当高；同时你也可以直接在 ChatGPT 内访问其他第三方数据供应商，因此智能体可以直接与这些数据源交互，没有任何额外阻碍。其次，我们着重推动了模型的发展，并针对特定的金融业务类型进行了训练，比如并购、股票研究等等。第三个组成部分是成果物（Artifacts）。基本上，最近几个月我们大力增强了模型实际制作演示文稿、制作电子表格的能力，并且能够利用历史示例中的参考模板，将其重现并用于当前的分析之中。

<details><summary>Original English</summary>
So what we did is basically within the charge work and charge financial services we tried to create a product that is enterprise focused that basically it's fine-tuned like the model is the same but the product itself is fine-tuned for the specific like financial services type of user. So there are like three main component to this product. So first of all the data. So it's we have some like built-in data that I think it's they're high quite high quality but also we you can access to other third party data vendor directly within uh chachbt so the agent can interact directly with the data sources without any um overhead. Then second we really like pushed [clears throat] our model and trained them on specific financial um type of work. So like you know we can think about like you know M&A equity research and so on so forth. And third component is the are the artifacts. So basically we really pushed in the in the recent months the capability of our model to actually build presentation build spreadsheet and also being able to leverage like reference template that from like you know historical example you know and reproduce them like with the for the current analysis.
</details>

是的，我补充一句。在接下来的实验操作中，第一部分将真正聚焦在金融服务专用的 ChatGPT 插件上。它位于 Web 界面，基本上就是网页端，稍后我们会展示所有的功能。因为如何使用金融数据是一方面，这是其中的一个优势，但同样还有特定的提示词指令方法来将信息呈现在图表中、进行某些核验，以及标注数据来源。如果大家参与接下来的实验，看到这些内容会非常重要，这就是我们要展示的特定领域解决方案。

<details><summary>Original English</summary>
So yeah maybe just to add to it. So in the in the labs what we do now the first part will really focus on this plug-in share GBT for financial services. So it sits in the web surface the website basically and then we show all the feature because how to use a financial data is one thing that's like a one benefit here but also there's certain ways or actually in instructs the prompt to present it the information in a chart or use also some verification and also have some annotations where the data comes from. So all that if you hang out for the lab will be very important to see and that's sort of the domain specific solution we to showcase.
</details>

我们先从内置数据开始讲起，这也是我们想让大家接入这个特定版本的原因，因为金融服务版目前只对企业端开放。这些是产品内置集成的部分供应商，我们与 Canalyst/Alphasense (Lupa)、LSEG (Elsag)、PitchBook、Crunchbase 等供应商建立了合作。大致说明一下开箱即用的内容：我们有 SEC 申报文件，有行情数据。行情数据当然是有延迟的，大概有 15 分钟的延迟，但你依然能获取准实时的行情数据；此外还有新闻，以及非上市公司的资料和财报电话会议纪要。这里的主要区别在于，这些数据源是真的管线化接入到了产品中。这不仅仅是把原始数据输送进来，我们还对数据库进行了专门的微调处理，以确保模型能够轻松使用这些数据。我们观察到模型在实际摄取此类数据方面有了明显的改善，因为我们把数据封装成了一种不仅仅是原始数据集、而是更适合 LLM 处理的格式。

<details><summary>Original English</summary>
So let's start a little bit like with um the building data and that's why we want to on board you to this specific version because charge for financial services is only available like on the enterprise side. So these are some of the vendor that are built in within the product. So we like had partnership with like the Lupa, Elsag, Pitchbook, Crunchbase and other vendor. And basically to give you an idea like of like what's available out of the box, we have like SEC feelings, we have market data. Market data of course are delayed. So uh I think there is a 15 minutes delayed but still you have like real-time market data. you have news and like we also have like you know private company profiles and earning calls transcript and the main difference here is that these data sources are like really piped into the product. So it's not just like the row data that is entering but like we did like a specific fine-tuning of of the databases to make sure that like this these data are easy to to be consumed by the model. So what we've seen is like like a nice improvement on like how the model is actually able to ingest this data because we kind of like wrap it in in a format that is like not not just like you know the row data set but it's more um fitted for the LLM.
</details>

>> 是的，我也补充一点。我自己其实在公司内部也做过类似的事情，如果把所有的 SEC 归档文件抓取下来并对数据进行规模化处理，其实是相当困难的，你必须确保能抓取到新的信息。我在一个资产管理案例中做过这个，但我认为这里真正独特的地方在于，你拥有这些运行中的智能体来收集这些数据，我们有金融数据提供商……

<details><summary>Original English</summary>
>> Yeah. So maybe just one thing to add. I mean I have done something similar myself actually inside the company and it's quite hard if you pull down all the SEC files and you have it scale the data you have to make sure you grab the new information I mean I have done it in a in an asset management case but I think what's really here unique is basically you you have those agents running collecting this data we have the financial data pro providers
</details>

<!-- chunk 2/12 -->

在我们这里运行，但你背后也必须有一层上下文层，它实际上足够高效来提供服务，而这往往是一个技术挑战。所以这也是我们稍后可以向你们展示的内容。这差不多就是产品内部所包含的东西。现在这里有一些技术解决方案可以高速提供这些能力，然后再进一步看看如何利用这些数据来创建分析，比如我们的团队，我们的产品团队所做的就是专门针对金融任务构建了几个插件。具体来说，我们可以谈谈投资银行的那个和股权研究的那个。因此，在这些插件内部，我们在 open eye 所定义的插件有点像技能库加上 MCPS，而我们所构建的就是，我们与顶尖的投资银行、顶尖的资产管理公司、顶尖的股票研究员合作，构建出那种最灵活但也最切合实际的插件，就像你可以真正用来作为分析基线的技能一样。所以我们不仅在金融服务领域看到，而且我们发现的是，当我们提供特定的技能时，这些技能就提供了一个很好的基线。比方说，你是一名想要简化其——咳——他们工作的股权研究员，你实际上可以做的就是直接开箱即用该技能。背后已经有了大量的工作，然后基于使用该技能来创建比如定时任务，基本上创建一个试图复现你目标的流水线，你以此作为基线，并在此基础上尝试改进，尝试根据你的品味进行定制，并添加目前缺少的所有细微部分，但我们看到的是，这类插件提供了一个强大的基线，所以你不需要从零开始，你是从基于行业知识构建出来的东西开始，然后假设 80% 已经就绪，接着你根据自己的具体需求、具体见解等等添加你的 20% 定制化内容。

<details><summary>Original English</summary>
that work with us but also you have to way have a context layer behind it that actually is efficient enough to serve it and that's often a technical challenge. So that's what we can show you also later. That's a sort of what the product has inside. Now it's there's some technical solution for providing that at speed and then like moving a little bit more on like you know how to leverage this data to create analysis like what our team our product team did is like build several plugins specifically for financial tasks. So specifically we can talk about the uh the investment banking one and autary research one. So within these plugins there that is like what we define uh at open eye as a plug-in is kind of like a library of skills plus MCPS and what we built is like we we partner with like top investment banking, top asset management, top equity researcher to build the kind of like most flexible but also most like realistic plugins like skills that you can actually leverage as a baseline for your analysis. So what we've seen not only in the area of like financial services but what we when is that when we provide specific skills these skills present like a good baseline. So let's say that you are an equity research it wants to streamline uh his [clears throat] them their job what you can do is literally like take the the skill out of the box. there's been a lot of work behind it and then based on using that skill to create like you know a schedule job to create like basically a pipeline that try to reproduce what you're aim to and you use that as a baseline and on top of that you try to improve you try to customize to your taste and adding all the beats that are currently missing but what we've seen is that like these type of plugins [snorts] provide like a strong blaze line so you don't have to start from zero you start from like something that is built out of industry knowledge and then let's say that the 80% is there and then you add your 20% customization based on like your specific needs, your specific like view and so on so forth.
</details>

最后再次说明，这些就是一些已经开箱即用的用例。这些用例稍微偏向投资银行一些。我们今天将更多地关注资产管理方面。如果你想想制作演示材料的准备、收益分析、估值、LBO 建模，所有东西都是开箱即用的，而且这挺有意思的，因为即使是我自己，我来自资本市场背景，我不得不与少数来自投资银行讨论估值的人进行互动，仅仅利用这个插件，在本地运行几个示例，就能够让我稍微跟上进度，去理解客户所谈论的产品和背后的问题。这就是关于在金融服务方面所做努力的初步介绍。我们现在要转向更偏构建的部分。最后提醒一下，请在这里填写您的详细信息。这非常非常重要，我在这里稍等一分钟，确保每个人都填好了。

<details><summary>Original English</summary>
So finally again these are like some of the use cases that are already out of the box. You know these are a little bit more skewed on the investment bank. We're going to work today more on the asset management. If you think about you know pitchbook prep uh preparation, earning analysis, valuation, LBO modeling, uh everything comes out of the box and it's uh quite interesting because even myself like I I come from like a background in in capital markets and I had like to like interact with few people from investment banking talking about valu valuation and just like leveraging this plug-in like running few example locally was able like to bring me a little bit up to speed to understand um you know the product the the the problem behind um what the clients were talking about. So let's this is kind of like a little bit like the initial presentation about like you know what's the effort on uh the financial services. We are now going to move to the more like building part. And as a final reminder please add your details here. It's really really important and I'm gonna stay here for a minute making sure that everyone has it.
</details>

>> 是的，也许我认为现在切换过去是个好时机，我来向大家稍微展示一下我们现在动手操作的内容，大家正好可以确认一下能够访问该网站，并且能够登录进入 shb work。

<details><summary>Original English</summary>
>> Yeah, maybe I think it would be good point um when we switch I will show you a little bit what we're doing hands on now that you can just confirm you can access the site and then also be able to log in into shb work.
</details>

>> 好的。有人在输入数据（比如电子邮件地址）时遇到问题吗？我认为这是个好兆头。所以我们现在可以切换到有趣的部分了。这就是我们要在构建部分使用的网站。请大家随时扫码，如果提示输入验证码，验证码就在那里，但在理论上那应该就是你扫描的二维码。

<details><summary>Original English</summary>
>> Yeah. Anyone has having problem putting the data in like the email address? I think it is a good sign. So we can now switch to the fun part. Um so this is actually the website we're going to use for the building part. So please um um feel free to scan it and if the it ask for a code the code is there but it should be in theory that you write QR.
</details>

### 金融服务工作流与扩展开发

>> 是的，在切换之前我们也许稍微等一下，因为我们今天时间很充裕。也许只是确保每个人都能访问它，然后我可以稍微讲一讲内容，并且也向你们展示一些技术细节。我们要做的就是，我们看到了 shb work for financial service 中一些不错的开箱即用功能。因此，你们不仅有数据，还有某种定制的用例。所以第一部分，我们考虑了 shbd for financial service 能为财富顾问业务带来什么好处。因此，我想我们要做的以及在这里展示的是，你究竟如何能让这个过程更高效，因为归根结底，你希望更多地与你的顾问沟通。现在，你可不希望团队花时间在处理、准备、分析投资组合，弄清楚发生了什么，解释原因，准备会议，也许还要为客户准备一份幻灯片来解释为什么投资组合中会发生这些变动、需要做些什么才能使其重新平衡。因此，第一部分确实就是这个用例。你把这款面向金融服务的 shed GBT 产品带给你的财富顾问团队，他们基本上可以加速你的工作流。所以它是团队中的终端用户工具。我的意思是，根据我的经验，通常他们也有非常不同的工作流程或不同的工作方式。所以它是可定制的，我们会带你走通这个用例：一位客户，发生了一次投资组合变动，你希望全程准备好损益表或投资组合归因，然后向客户展示该怎么做才能使其恢复平衡。这就是用例一，我们在那里提供了一些提示词，然后，我不知道在场的有谁……噢，有一个问题。

<details><summary>Original English</summary>
>> Yeah maybe we wait a little bit before we switch because we have a lot of time today. Um maybe just make sure everyone can access it and then I can talk a little bit also about the content and I show you also some um technical details. So what we'll do we we saw some of the nice out ofthe-box features in um shb work for financial service. So you have data but also sort of customized use cases. So the first part we thought what would be the benefit for a wealth advisor business with shbd for financial service. So I think what we want to do and show here how can you actually make this process more efficient because at the end of the day you want to talk talk to your advisor more. Now, you don't want to uh have a team that's working, preparing, analyzing portfolios, figuring out um what happened, explaining it, preparing the meeting, um preparing um maybe also for the customer a deck that explains why were those changes happening in the portfolio, what needs to be done to bring it back in balance. So, the first part is really the use case. You bring this product shed GBT for financial service to your wealth advisor teams and they can basically accelerate your workflows. So it's an enduser tool in the team. I mean often in my experience also have very different work workflows or different way of working. So it's customizable and we walk you through this use case. a customer there's a portfolio change happening and you want to go all the way preparing um the P&L or the portfolio attribution and then showing the customer what to do to bring it back into balance. So that's the use case number one and um we provide a couple of prompts there and then I don't know who in the room is oh is a question
</details>

好的，我们会解决那个问题的。那很正常。是的。

<details><summary>Original English</summary>
So yeah, we will fix that. Um, that's normal. Yeah.
</details>

>> 开始吧。

<details><summary>Original English</summary>
>> Let's go.
</details>

>> 那么，我会去处理这个。你可以继续讲。那个网站就是最新那张幻灯片上的，对吧？

<details><summary>Original English</summary>
>> So, uh, I'm going to work on it. You can keep going. So, like is the website like the the latest slide, right?
</details>

>> 我想是 shbt work 那个网址。是的。我的同事会处理它，我来多解释一下。对于在场的各位，我不知道，我们这里有几个人。大家的背景是什么？我的意思是，你们是开发者、构建者、工程师、AI 专家？现场有谁更偏向于技术角色，正在从事开发、构建某些东西？我们有相当……我看不全，但差不多有一半人吧。因此，对于那些更偏实操和技术的学员，我现在也想解释一下工作坊的第二部分，一旦我们给你们开通了权限，实际上是在我们的服务中，在 codec 这一侧，即桌面端解决方案。codeex 也可以供终端用户、业务用户、知识工作者使用，但在这种情况下，我们希望对它进行更多定制，因为假设你们公司成功部署了 CHB financial service，并且满足了业务用户的需求。但随之而来的问题是，我该如何扩展它？我该如何把自己的数据接入进去？我该如何对其进行定制？

<details><summary>Original English</summary>
>> The shbt work you I think. Yeah. So, my colleague work on it and I will do a little bit more to explain it. So, and maybe for the people in the room here, I don't know. We have a couple people. What's what's your background? I mean, you're like a developer, builder, engineer, an AI exp who is like more in a technical role, developing, building something in in the room. So, we have quite I can't see it fully, but yeah, it's a half maybe. So I think for those people that are more hands-on and technical now and I want to explain also the second part of the workshop once we get your access is actually in our service in the codec side the desktop solution the codeex would be also it can be used by end users business users knowledge workers but this in this case we want to do a little bit more customization of it because let's assume you you deploy CHB financial service in your company successfully and it meets the business users need. But then the question is how can I extend it? How can I make my data coming with it? How can I customize it?
</details>

所以在工作坊的第二部分，我们考虑基本上有两种做法。你可以说，我们构建一个自定义应用程序。我拿到一个 open AI 的 API 密钥。我们来做一些 Web UI。用 codex 配合 Web UI 也很容易实现。我把它部署在我的公司里，然后，是的，我就有了典型的软件开发生命周期；这算是路径 A，或者是路径 B，你基本上会考虑：噢，我企业内部的用户已经在用 shed GBT for work 了，他们大多数人已经有了 codeex，为什么不把我业务所拥有的这种需求保留在这个生态系统之内呢？

<details><summary>Original English</summary>
So the second part of the workshop we thought there are two there basically two ways of doing it. You could say let's build a custom application. I get an open AI API key. Let's do some web UI. It's easy to do also with codex and web UI. I deployed in my company and then yeah I have the typical software development life cycle or is this path A or path B is you basically think about it oh my users have already in the enterprise shed GBT for work they already have codeex most of them why don't you keep sort of this need that I have for my business inside this ecosystem
</details>

所以在第二部分中，我们基本上会探索，作为一名内部开发者，使用 codeex 创建技能、插件和插件扩展你会做些什么。我稍后会解释它是什么，以便真正实现一个可以驻留在该界面内的完整应用程序。基本上借助于那些东西，我将带大家了解那些东西是什么，你基本上可以自定义工作流。我的意思是，我想大家现在可能都知道技能是什么了。它是一种标记，为你提供更多的定制化并且可重用。但当你真正想要连接你的数据时，你需要 MCP，需要一些工具，你需要定义所有这些。那就是插件派上用场的地方。现在的插件相对来说更重量级一些，你可以在其周围进行定制。所以我们在那里创建一个插件，有了插件之后，它可以存在于桌面端，它也可以存在于

<details><summary>Original English</summary>
So like we explore in the second part basically what would you do as an internal developer using codeex to create a skill a plug in and a plug-in extension. I explain what it is in a bit to actually implement a full application that could sit inside the surface. So basically with that with those things I will walk you through what those things are. you can customize basically the workflows. I mean, everyone I think probably knows now what a skill is. Um, it's a markup that provides a little bit more customization for you and reusable. But then once you actually want to connect your data, you need an MCP, you need some tools, you need to define all that. And then that's where you have a plugin. Now the plugin is sort of a little bit heavier and you can customize it around it. So we create a plugin there and then with a plugin it can lifts on a desktop it can live also in the
</details>

<!-- chunk 3/12 -->

网站，然后我们最近刚刚公布的，其实是在 DevDay 上的插件扩展（plug-in extensions）。所以我们最终所做的，实际上也对 UI 做了一点定制，这样你就可以定制界面来契合你的使用场景。比如我们有一位顾问会在网页端使用面向金融服务的 shbdt，但你实现的工作流实际上也可以置于桌面应用程序中，所以我们正在探索这个。

<details><summary>Original English</summary>website and then what also we just recently announced is actually on dev day plug-in extensions. So what we do at the end we also actually customize the UI a little bit so you can customize the surface to fit your use case. So we have an advisor that would use shbdt for financial service in the web but the workflow you implement can actually also be sitting in the in the desktop application and then so we exploring that</details>

>> 等一下。

<details><summary>Original English</summary>>> one second</details>

>> 不行。

<details><summary>Original English</summary>>> no</details>

>> 好的。

<details><summary>Original English</summary>>> okay</details>

>> 好了，我们快搞定了［笑声］。所以我得多讲两句，或许我可以给你讲一遍，所以你能不能在……我或许也可以展示一下内容。是的。

<details><summary>Original English</summary>>> so we get there [laughter] so so I have to talk more and probably I can talk you through it so maybe can you do it um on a um I can show maybe the content also Yeah.</details>

>> 是的。是的。不过我觉得有趣的部分是，在这个工作坊中，一旦我们让大家获得访问权限，我们就会去做；如果你现在弄不出来也不用担心，这个网站稍后也是可用的。这实际上是探讨：作为一家内部已经拥有这些平台的企业里的开发者，我会怎么做？我是否能稍微避开或减少我部署应用程序的工作量？不，那是个很巧妙的想法，我认为那正变得可行。

<details><summary>Original English</summary>>> Yeah. Yeah. So, but just I think the interesting part is we did do in this workshop once we get access to it to you and don't worry if you can't get it out we the website is available later also. It's really what would I do as an developer with a company an enterprise that already has this platforms inside the company and can I avoid a little bit my work or reduce my work to deploy applications? No, that's a neat idea I think that becomes possible.</details>

>> 那个，问个问题，关于你提到的内置工具，比如文字记录、备案文件以及那里的各种其他数据，我猜 harness 具备某种感知能力。仅仅是因为 harness 和 skills 就位了，还是说你们对模型做了什么？只是有点好奇是什么让它变得好上这么多的。派对麦克风也是开着的。

<details><summary>Original English</summary>>> So, just a question uh about the uh built-in tools you mentioned like uh transcripts and filings and all that sort of uh other data that you have there and that you I guess the harness has some awareness. Is it just that the the harness and skills are there or is there something that you did to the model? Just any kind of curious what what is makes it so much better. The party mic is on as well.</details>

### 工作坊设置与功能介绍

>> 好的。对于没有完整链接的人，那是工作坊的访问代码。你能访问到吗？请来个人确认一下它能用。

<details><summary>Original English</summary>>> Okay. So, just for the people that have not the full link, um that's a workshop access code. Can you get to it? So, someone just confirm it works.</details>

>> 好的。你看，搞定了。［笑声］

所以也许顺便解释一下我们在这里的工作坊底层使用的是什么。那实际上是 sites 功能，即托管网站的能力，它相当容易，而且在这个例子中它实际上是一个公开的 veite。非常适合用来构建美观且实用的 UI。

所以我稍等一会儿，让大家都能进入工作坊的设置环节。

<details><summary>Original English</summary>>> Okay. You see, fix it. [laughter]

So maybe also explaining um what we use under the hood for the workshop here. So that's actually um the sites feature the capability to host a website and it's quite u easy and in this case it's a public veite actually. So what's very neat um to create nice looking um functional UIs actually.

So just I just wait a little bit that everyone is um can get to the workshop setup.</details>

>> 如前所述，我们也在发送用于访问工作区的邮件，应该马上就到了。

<details><summary>Original English</summary>>> We are also sending the emails for um accessing the the workspace as mentioned before it should come up.</details>

>> 是的。在我们进行的同时，我想我们这里为大家准备了小水瓶之类的东西，不是给所有人，而是给今天参与的人。为了增加一点趣味性，一旦你在房间里成功注册——我看到现场已经有相当多的人了。这是用 sites 应用创建的。所有成功进入该网站的人，都已经获得了 100,000 的虚拟资金。为了好玩，当然我们都知道市场总是有涨有跌，现在可能稍微跌了一点。但如果你完成这些步骤，就会获得额外资金，然后在今天结束时，在工作坊结束时，我们想看看排名前三的人。是的，他们肯定能拿到一些水瓶。这只是为了好玩，稍微保持一下趣味性。

不过回到网站这边，因为我想我们看到大家现在都已经进去了。我基本上想指出的第一点是，我们确实需要访问面向金融服务的 shed GBT，基本上就是这里的这个网站，你可以看到上面有金融数据，也能看到插件——面向金融服务的 shed GBD。我同事负责的就是帮大家完成这一步的入职配置，当你能够访问这个面向金融服务的 sht 网站，以及我们在演示文稿中展示的金融数据后，你就可以随意按照“核心功能”（core capabilities）下的说明操作了。

你可以在这里设置一次，我们有一个小 zip 文件，里面放了一些客户示例等的数据。这完全是财富管理的业务场景：我该如何帮助我的顾问提高效率？然后我绝对建议大家，各个子部分都可以自行尝试。如果你对投资组合问题、研究或图表更感兴趣，可以随意自行开始其中的任何一个板块；当你在操作中遇到任何问题时，也请在现场举手，我们很乐意提供协助。它真正展示了该产品主要功能的亮点。

对于那些更热衷于构建的人，我想有个要求是你的桌面上必须安装有 codecs。所以对于还没安装的人，你可以去安装它。我认为那是第二部分，而且我觉得大家可以随意选择。我的意思是，如果你更想去了解这个产品在做什么、开箱即用的功能有哪些，那么在访问网站后留在“核心功能”即可；但借助 codeex，我认为这就是我早些时候说的那个构想：我们现在如何在一个企业中利用 AI 原生工具来开发应用程序、工作流等等。

这里会带你了解 skill 插件，我们在这里也做了一个 MCP 用例，用来增强我们在前一部分所做的工作流。然后我一定要强调的是，去尝试一下插件扩展。至于什么是插件扩展，我只想稍微解释一下：我想大家现在都知道有各种方式可以通过 skills 来扩展 AI harnesses，而这里的插件算是稍微重量级一点的，你看它的结构，它包含 skills，包含一个 MCP 服务器，包含工具配置，然后你可能还有一个 UI，以你想要的方式将其呈现在表面上。这很酷。

这就是我提到的那一点，但我真正想说的是，现在这也是可能的：基本上你有 shed GBT，或者桌面端的 CEX 应用程序，你看到这里高亮的区域，你实际上可以根据你的财富管理业务可能与 codeex 或 chat GBT 进行的对话来定制它。也就是说，你可以设定如果我输入某个特定内容，且它属于某种特定文件类型，它就会突然弹出一个由你控制、由你部署的 UI 扩展，使其更加定制化。实际上这有一些例子。

所以是的，我想强调这些就是我们可以……大家可以随意继续进行。已经装有 codex 的人请先从 setup 开始，还在等待网站访问权限的人，请先从那边的 setup 开始。

是的，刚才其实有一个很重要的提问。面向金融服务的 shedgbt 目前完全运行在我们的 shedgbt 工作网页界面中。这以后可能会改变，但目前那是唯一的访问途径。基本上我的意思是，我见过有些企业两者都有——他们有网页端的 GBT 工作环境，也有 codec，两者兼备，甚至知识型用户也是两者都用。所以你得把它们稍微拼接在一起。未来可能会有所改变，但目前它就在那里，不过这并不影响。你实际上可以在桌面上扩展插件，但也可以在 share GBT 工作站点上进行，现在插件也存在于那里。所以你在两边都有选项。

目前，插件扩展——也就是 UI 的定制——实际上只存在于桌面端，所以目前在网页端还无法实现，但这很可能会推出，我们的网站上也确实说明了它即将上线。大家心里有数就行，这里的一切都很新，各个界面提供的能力也各不相同，留意到这一点就好。

现在，如果你是一个真正的构建者，说“嘿，我现在想通过 CLI 来获取金融数据”，因为 Codex 也有类似于 CLI 的工具，你想把它放进流水线里，你目前是无法真正访问这些数据的，或者说基本上目前还没有提供。所以正如之前提到的，在这里由你掌控，你可以选择模型，我们建议你选择 Astra 或 6.1 Soul；如果你点击速度选项，你可以选择超快速（ultra fast），这会让你的体验好上很多。

然后是的，照着提示词操作就行，跟着提示词走，我的意思是通过阅读来了解一下这个产品到底为你提供了什么。所以我的意思是面向金融服务的 shibbity，我想当你进入这个市场……

<details><summary>Original English</summary>>> Yeah. So, while we do it, um I want to also I think we have little um like bottles or something for everyone here and um not for everyone, for the people that participate today. And to make it a little bit fun um we actually once you're able to be um signed up in the room and I see we already have quite a few people there. Um so this is also created with um the sites application. So, everyone who was able to get into the um website um got 100,000 virtual money already. So, to make it a little fun and of course we all know the market always moves up and down and it goes up uh maybe a little bit down now. But if you complete the steps um you get additional funding and then um at the end of the day we want at the end of the workshop we want to see um the top three people. Yeah. And um they get some bottles for sure. So to make a little fun, it's a little bit uh to keep it interesting.

But um so for for the website now because I think we see people are in there now. So what I want to um basically point out so the first thing we really need to have access to shed GBT for financial services and um that's basically the website here and you can see you have financial data and you can see the plug-in um shed GBD for financial services. So that's sort of the thing my colleague works on onboards you and when you have access to this website which sht for financial services and in the financial data um that we showed in the presentation um you are free to go and follow the instructions under core capabilities.

No. So you can say setup once and um we have a little bit a zip file to have some data there for the customer example and etc. So it's really the wealth management use case. How can I help my advisor to be faster and then I definitely would recommend um each of the subsections you can do on your own. So if you're interested more portfolio questions, uh research or charting, um feel free to start one of those sections yourself and then um when you do it and have any question, please raise your hand also in the room. We want to help you there. Um and it shows really the highlights of the the main features of the product here.

And then for the people that are more interested in in sort of building um I think it is a question you have to have codecs on your desktop. No. So so for the people that aren't you can install it. Um I think that's the second part and I I think it feel free. I mean if you rather want to envision that product more what is the product doing? What are the out of the box capabilities? stay in the core capabilities once you have access the website but with codeex um I think that's the idea what I was saying earlier how can we develop maybe with an AI native tool in an enterprise applications now workflows etc so and then here um we walks you through the skill plugin um we're doing also an MCP use case here to augment this workflow we do on the first side and then um I definitely want to highlight try out the plug-in extension and I think what's a plug-in extension I just want to explain it a little bit um I think we I think people know now there are ways of extending um AI harnesses with skills and the plug-in is sort of little bit heavier and you see the structure it has skills and has an MCP server It has a tool configuration and then you also have an UI probably to surface it in a way how you want it. That's cool.

That's the one thing I mentioned but it's sort of what I want to say is also possible. Now it's basically you have the shed GBT or the desktop the CEX application and you see this highlighted areas here. You could actually customize it depending on the conversation that maybe your wealth management business has with codeex or chat GBT. No. So you could say if I type in a certain thing and it's a certain file type suddenly it pops out a UI an extension that you control and can deploy and make it more custom. No. And there are some examples actually.

So yeah, I want to highlight those are the things um we could um if feel free to proceed there. So the people that have already codex start with setup once and the people that still get access to the website um please start with um the setup once there.

Yeah, there was a question actually which is important. So, so shedgbt for financial services lives exclusively in our shedgbt work web interface. No, so that might could change but right now it's the only way to access that. No. So you basically I mean you have sort of I mean I have seen enterprises that have the webs GBT work, they have the codec, they have both and even knowledge who users have both. Um so you have to patch it together a little bit. It might change in the future but right now it sits there but it doesn't it doesn't matter. You can actually extend plugins on a desktop but also on the share GBT work site. Now the plugins live there too. So you have the options there and currently plug-in extensions the customization of the UI actually lives only on the desktop side now so you cannot do it yet in the web but it will be probably it's actually on our website explained that is coming up um and so just be aware of it um it's all pretty new here and um the surfaces provide different capabilities just be aware of it and right now if you like a real builder and say hey I want to get the financial data with a CLI now because Codex has also like CLI you want to put it in a pipeline you're not able to actually access the data now yeah or it's basically not provided yet so as mentioned before here whilst you're in charge you have you can select the model we suggest you to go with either Astra or 6.1 Soul and if you can click on the on the speed you can pick ultra fast that is going to make like your life much better so and yeah it's just the promps you follow the promps and I mean you're learning by reading a little bit what the product actually provides for you so I mean the shibbity for financial services I think when you go on this market</details>

<!-- chunk 4/12 -->

### 金融数据本体与插件机制

历史市场数据以及研究报告，大家现在能看到其中一些关键特性。正如 Stefano 所说，我们专注于让产品更加契合——不是微调（fine-tuned），而是调谐（tuned）到大家的用例中。现在大家都收到邮件、登录进了正确的工作区，并且可以使用……在工作区操作了，太棒了，进展几乎完全符合我的预期。

<details><summary>Original English</summary>

 the

 the

 historical

 market

 data





and

 also

 research

 you

 see

 some

 of

 the





key

 features

 now

 that

 sort

 of

 as

 Stefano





said

 um

 we

 focus

 on

 to

 get

 that

 in

 the





product

 more

 tuned

 not

 fine-tuned

 but





tuned

 to

 your

 use

 cases

 now





so

 everyone

 has

 the

 email

 has

 logged





into

 the

 correct

 workspace





and

 can

 use

 like

 ch

 work

 fantastic

 went





almost

 as

 as

 mostly

 as

 I

 would

 have.

</details>

>> 是的。所以我的意思是，也许对于那些只想听的人，我可以同步做两件事。但有任何问题的话，我们更希望能为大家解答疑问，所以请随时提问。好的。

<details><summary>Original English</summary>

>> Yeah.

 So

 I

 mean

 I

 I

 maybe

 for

 the

 people





that

 just

 want

 to

 listen

 I

 can

 do

 it

 in





parallel

 also

 a

 couple

 things.

 Um

 but





any

 question

 I

 think

 we

 rather

 want

 to





help

 you

 with

 questions

 so

 feel

 free.





Yeah

</details>

>> 你提到了针对金融服务的特定配置。针对金融服务的特定配置，它是否有另一层本体（ontology layer）？你们还构建了什么？我觉得之前有人问过一个问题，但我没太理解答案：除了模型本身之外，你们具体还做了哪些事情？

<details><summary>Original English</summary>

>> you

 mentioned

 the

 specific

 setup

 for





financial

 aid.

 uh

 you

 had

 mentioned

 uh





with

 the

 specific

 setup

 for

 financial





services

 has

 does

 it

 have

 another





ontology

 layer

 like

 what

 else

 have

 you





built?

 I

 think

 there

 was

 a

 question





asked

 earlier

 I

 didn't

 quite

 get

 the

 get





the

 answer

 what

 specific

 things

 you

 had





done

 beyond

 the

 model

 itself.

</details>

我认为就像我之前提到的，真正关键的是数据本体（data ontology）。这不仅仅是像 API 调用那样把数据源连接起来。实际上，我们对数据本体进行了调整，以便模型能够极其轻松地获取和提取正确的信息；此外，对于每种类型的数据源，都有一套关于什么是相关信息、什么是不相关的上下文定义。

举例来说，关于 10-K 或 10-Q 文件，这不仅仅是提供文件本身，还要说明文件内部各项内容具体代表什么。我认为在数据层面上，这是一个关键的区别点。而且不仅是集成的内置数据源，对于我们合作的插件也是如此，比如如果有权限可以登录的数据提供商，原理是完全一样的。所以这不仅仅是获取数据，而是以正确的格式获取包含正确内容的数据。

<details><summary>Original English</summary>

So

 I

 think

 like

 what

 I

 mentioned

 before





is

 really

 like

 the

 data

 ontology.

 So





it's

 not

 just

 like

 connecting

 the

 data





sources

 as

 if

 you

 know

 it

 would

 be

 like





you

 know

 an

 API

 call.

 We

 actually

 the





data

 ontology

 has

 been

 changed

 in

 order





to

 make

 it

 like

 extremely

 easy

 for

 the





model

 to

 get

 extract

 the

 right





information

 and

 also

 there

 is

 like

 kind





of

 a

 context

 of

 like

 for

 each

 type

 of





data

 source

 what's

 relevant

 what's

 not.





So

 if

 you

 think

 about

 10ks

 or

 10

 QS

 like





is

 not

 just

 like

 providing

 the

 file

 but





is

 also

 explaining

 you

 know

 what

 is

 what





within

 the

 file.

 I

 think

 that's

 kind

 of





the

 on

 the

 data

 point

 that's

 the

 kind

 of





like

 key

 differentiator

 and

 also

 when





when

 like

 not

 just

 from

 the

 integrated





data

 sources

 but

 also

 from

 like

 the





plug-in

 that

 we

 partner

 with

 like

 uh





data

 provider

 that

 you

 can

 login

 into

 if





you

 have

 access

 that's

 the

 same

 concept.





So

 it's

 not

 just

 getting

 the

 data

 is





actually

 getting

 data

 with

 the

 right





contents

 in

 the

 right

 format.

</details>

>> 对。另外当我们谈到插件时，当然，如果你看这些技能（skills），最终它们就像是一些 Markdown 文件和模板，但背后融入了真实的专家知识。我们与金融机构合作了很长时间，在构建这款产品时，我们挑选了一批顶尖投资银行等合作伙伴共同合作，以此验证产品的质量。所以，这确实是我们构建的专业知识，用于将模型转变成能够供金融专家使用的产品。所以……

<details><summary>Original English</summary>

>> Yeah.

 And

 also

 when

 we

 talk

 about





plugins

 um

 these

 plugins

 is

 not

 of





course

 like

 at

 the

 end

 like

 if

 you

 look





at

 the

 skills

 are

 kind

 of

 like

 some





markdown

 files

 some

 templates

 but





there's

 been

 like

 there's

 actual

 expert





knowledge

 we've

 been

 like

 partnering





with

 financial

 institution

 for

 quite

 a





long

 time

 and

 when

 we

 built

 this

 product





we

 had

 like

 a

 selected

 number

 of

 partner





like

 top

 investment

 banking

 and

 so

 on

 so





forth

 that

 we

 worked

 with

 in

 order

 to





validate

 the

 quality

 of

 the

 product.

 So





it's

 is

 literally

 like

 the

 the

 the

 kind





of

 knowledge

 that

 we

 build

 to

 put

 to





transform

 like

 like

 the

 model

 into

 a





product

 that

 can

 be

 used

 by

 like





financial

 experts.

 So

</details>

>> 是的。没错。所以我觉得，如果自己来做的话，比如说“我想自己规模化地构建上下文层和本体”，而现在我们必须摄取的数据量相当庞大。虽然你可以通过智能体处理公开数据并在可扩展的产品中实现它，同时接入数据提供商，并且有许多方法确保它找到正确的数据。我想我们其实有几篇博客文章介绍了背后的数据架构。关于我们使用哪些开源服务，内容非常有趣。但这说明我们积累了大量专有知识，基本上就是为十亿级用户高效构建上下文；驱动这款产品的底层逻辑也是完全一样的。

所以我想这可能涉及工程层面以及上下文工程（context engineering）。目前它还是一个早期产品，我想大家会看到我们如何对其进行演进。目前它运行在 GPT Work 上，还不支持通过 CLI 访问。好的，让我们拭目以待未来的发展。

<details><summary>Original English</summary>

>> yeah.

 Yeah.

 So

 I

 I

 think

 um

 there

 I

 mean





if

 I've

 just

 talked

 about

 it

 before

 if





you

 do

 it

 yourself

 I

 mean

 you

 say

 I

 want





to

 do

 the

 context

 layer

 the

 ontology





myself

 at

 scale

 and

 it's

 quite

 large





data

 now

 we

 have

 to

 ingest

 now

 so

 you





can

 do

 it

 in

 an

 scalable

 product

 with





agents

 like

 doing

 public

 data

 but

 also





have

 the

 data

 providers

 and

 there's

 a





lot

 of

 ways

 of

 making

 sure

 it

 finds

 the





right

 data.

 So

 I

 think

 um

 we

 actually





have

 a

 couple

 um

 blog

 post

 how

 our

 data





architecture

 is

 behind.

 Now

 there's





something

 interesting

 what

 services

 we





use

 open

 source

 services

 but

 I

 think

 it





shows

 you

 there's

 a

 lot

 of

 know

 how

 we





build

 actually

 for

 billion

 users





basically

 like

 a

 context

 efficiently

 no





and

 so

 that's

 the

 same

 thing

 that's





under

 the

 hood

 powering

 this

 product

 no





so

 I

 think

 it's

 maybe

 the

 engineering





side

 now

 and

 the

 context

 engineering

 um





right

 now

 it's

 it's

 an

 early

 product

 and





I

 think

 you

 will

 see

 how

 we

 involve

 it





now

 but

 also

 lives

 on

 GBT

 work

 for

 now





not

 via

 CLI

 and

 yeah

 let's

 see

 how

 the





world

 goes

 here

</details>

>> 有没有办法访问你们开发的这些更底层的数据结构？比如你们构建的本体或者图结构（graph）？

<details><summary>Original English</summary>

>> is

 there

 any

 way

 to

 access

 some

 of

 these





more

 primitive

 data

 structures

 that

 you





guys

 have

 developed

 like

 if

 you

 have





ontologies

 or

 like

 a

 graph

</details>

>> 底层的内容实际上是无法直接访问的。因为这是一款面向知识型用户、而非纯工程师的产品。不过抛开过多细节不谈，本质上每个数据集在接入时都会与提供方深入沟通，以真正理解提供该数据的最佳方式，而且主要在于对数据集的理解。所以这不仅仅是数据本身，而是搞清楚什么才是相关的信息。举个简单的例子，比如在接入市场价格与收益率数据时，需要解释所有这些细节，例如如果想执行某种操作或提取特定信息，该如何避免基本的误解等等。

<details><summary>Original English</summary>

>> so

 like

 no

 what's

 under

 the

 hood

 it's





not

 really

 accessible





uh

 because

 this

 is

 like

 a

 product

 meant





a

 little

 bit

 more

 for

 the

 knowledge

 user





not

 the

 pure

 engineer

 but

 uh

 I

 think





it's

 without

 enter

 too

 many

 the

 details





is

 literally

 like

 each

 data

 set

 was

 like





on

 boarded

 with

 the

 kind

 of

 like





provider

 to

 really

 understand

 like





what's

 the

 best

 way

 to

 serve

 it

 and

 also





it's

 it's

 mostly

 like

 the

 understanding





of

 the

 data

 set.

 So

 it's

 not

 just

 like





it's

 literally

 like

 you

 know

 what's

 the





information

 like

 what's

 the

 relevant





information.

 So

 how

 you

 know

 like

 a





simple

 example

 like

 you

 know

 when

 you

 on





board

 market

 prices

 versus

 return

 like





explaining

 all

 these

 detail

 on

 like

 you





know

 if

 you

 want

 to

 do

 this

 operation

 if





you

 want

 to

 extract

 this

 information





don't

 like

 how

 to

 avoid

 like

 basic

 uh





misconception

 and

 so

 on

 so

 forth.

 So

</details>

>> 你们刚才谈到 10-K 和 10-Q 的嵌入（embedding）时，后端是否有使用自定义的嵌入之类的技术？

<details><summary>Original English</summary>

>> did

 you

 did

 you

 guys

 when

 you

 were





talking

 about

 10K

 and

 10

 Q





sort

 of

 embedding

 did

 you

 guys

 have

 like





custom

 embeddings

 and

 stuff

 is

 that

 is





that

 at

 the

 back

 end

 of

 this?

</details>

>> 不，没有。完全就是我们创建数据集，并以模型容易调用的方式对数据进行预处理——可以把它理解为一种工具调用（tool call），不过是针对该数据集专门定制的工具调用。所以，不用担心这个。

<details><summary>Original English</summary>

>> No

 no no

 no

 it's

 it's

 literally

 like

 we





create

 the

 data

 set

 and

 like

 pro





pre-process

 the

 data

 in

 a

 way

 that

 the





model

 can

 access

 easily

 like

 think

 about





like

 a

 kind

 of

 a

 tool

 call

 but

 like

 a





really

 customized

 tool

 call

 for

 that





data

 set.

 So,





no

 worries.

</details>

### 插件交互与自定义 UI

>> 是的。我正在演示给大家看。我现在在操作提示词（prompts）。如果你在网站上，直接复制提示词输入到产品中即可。然后大家看到这里的图标，能看到它实际上已经调用了插件。可以这样理解：插件是在提示词中进行提示的。我在提示词中提示使用面向金融服务的产品，所以它目前遵循插件概念；然后大家能看到底层实际使用的金融数据，以及在这个插件内部发生的工具调用。所以目前它确实是一个插件概念，而底层我们提供了一个具备可扩展性的后端。

<details><summary>Original English</summary>

>> Yeah.

 I

 mean,

 I'm

 just

 showing

 you.

 I





mean,

 I'm

 doing

 now

 the

 poms.

 Now,

 if





you're

 on

 the

 website,

 you

 just

 copy

 the





pom,

 put

 it

 in

 the

 product

 and

 um

 and





then

 also

 when

 you

 when

 you

 see

 now

 the





icons

 here.

 So,

 you

 see

 a

 little

 bit

 um





is

 actually

 picked

 up

 the

 plugin.

 So,





think

 about

 it.

 The

 plugin

 is

 a

 way





that's

 hinted

 in

 the

 prompt.

 Um

 I

 hinted





in

 the

 prompt

 to

 use

 shbt

 for

 financial





services.

 So

 it

 follows

 a

 plug-in





concept

 currently

 and

 then

 um

 you

 can





see

 actually

 the

 financial

 data

 that's





under

 the

 hood

 used

 and

 the

 internal





tool

 calls

 basically

 in

 this

 plug-in





happening.

 So

 it's

 really

 um

 like

 a





plug-in

 concept

 right

 now

 and

 then

 um





yeah

 under

 the

 hood

 we

 provides

 a

 back





end

 basically

 that's

 scalable.

</details>

从极高层次对这款产品进行概述：我认为这非常棒，因为这基本上就是每位知识型用户（比如股票研究分析师）将要使用的交互界面。但在第二部分中，我们还要探讨如何添加插件。我们都知道现有的这些数据源是不够的，大家可能拥有内部工具和内部数据集。大家可以使用自己的技能来构建自己的插件，尤其是像我们之前提到的，完成最后一层的定制。因此作为工程师，你可以构建出这种工具，然后作为插件在 ChatGPT for Work 中使用。

这样一来，你的最终用户、知识型用户就拥有了这个底座。也就是说，这是一个非常强大的基准，涵盖了如何与数据交互、如何开展特定的财务分析，以及如何生成像 Excel、PowerPoint 这样的输出；同时你可以添加一个定制层，通过具体的工具、具体的数据集以及公司特有的逻辑，使其变得独一无二。

<details><summary>Original English</summary>

So

 I

 would

 say

 like

 to

 give

 you

 like

 the





really

 high

 level

 view

 of

 this

 product.





I

 think

 it's

 really

 cool

 because

 you





know

 this

 is

 basically

 the

 interface





that

 like

 every

 like

 knowledge

 user

 like





the

 equity

 research

 analyst

 is

 going

 to





use.

 But

 what

 we

 are

 also

 going

 to

 do

 in





the

 second

 part

 is

 like

 thinking

 about





how

 can

 you

 add

 plugins

 like

 uh

 we

 all





know

 that

 you

 know

 these

 data

 sources





are

 not

 enough.

 They're

 like

 you're





probably

 gonna

 have

 like

 internal

 tools.





You're

 gonna

 have

 internal

 data

 set.

 You





can

 build

 your

 own

 plug-in

 with

 your

 own





skill

 like

 especially

 as

 we

 mentioning





before

 like

 you

 want

 to

 do

 the

 last





layer

 of

 customization.

 So

 as

 an





engineer

 as

 like

 you

 can

 build

 this

 tool





that

 then

 like

 you

 can

 use

 as

 a

 plug-in





in

 charge

 for

 work.

 So

 your

 end

 user





your

 knowledge

 user

 is

 going

 to

 have





this

 as

 a

 base.

 So

 let's

 say

 this

 is





like

 a

 really

 strong

 baseline

 on

 how

 to





interact

 with

 data,

 how

 to

 build

 like





specific

 financial

 analysis,

 how

 to





produce

 like

 output

 like

 Excel,





PowerPoint,

 but

 you

 can

 add

 a





customization

 layer

 that

 your

 company

 or





like

 with

 like

 the

 specific

 tools

 with





specific

 data

 set

 with

 specific

 logic

 is





going

 to

 make

 it

 unique.

 So

</details>

>> 对，补充说明一下，大家也可以自己动手操作。这展示了金融服务产品内部发生的底层工具调用，虽然无法完全访问那里的上下文，但第二部分是可定制的 UI。我们最近推出了智能 UI，现在获取响应时，基本上会通过返回内容得到一个经过更针对性调谐的 UI 回答，这就是其中一个例子。这同样也是插件所提供的功能。因此它具备相应的上下文：当我询问关于收入的问题时，你希望以特定形式呈现，可能是一个表格加一个图表，这些都是附加的功能。

如果是直接使用原生的基座模型，它不一定会自动以这种方式呈现，通常需要自己动手处理。所以我只是想强调所有这些带来差异的细节，因为它已经具备了一定的上下文，知道如何去呈现数据，尽管它并不是一个微调模型。好的。

<details><summary>Original English</summary>

>> yeah,

 so

 just

 point

 out

 I

 mean

 you

 you





do

 it

 yourself

 also

 um

 but

 I

 think

 it





shows

 you

 the

 underlying

 tool

 calls





happening

 in

 the

 sharp

 financial

 service





you

 don't

 have

 the

 full

 access

 to

 the





sort

 of

 the

 context

 there

 but

 the

 second





part

 is

 um

 this

 customizable

 UI

 so

 so





there

 I

 mean

 we

 had

 just

 recently





intelligent

 UI

 basically

 yeah

 now

 when





you

 get

 in

 response

 you

 basically

 have

 a





more

 um

 tuned

 UI

 answer

 basically





through

 the

 response

 now

 and

 this

 is

 one





example

 here

 and

 that

 is

 something

 that





the

 plug-in

 provides

 too

 and

 so

 it

 has





this

 context

 when

 I

 ask

 questions

 about





revenue

 that

 you

 want

 to

 see

 it

 in

 a





certain

 way

 and

 maybe

 as

 a

 table

 and

 the





chart

 so

 those

 are

 the

 things

 that

 are





addition

 so

 if

 you

 use

 a

 the

 Astra

 model





out

 of

 the

 box

 it

 would

 not

 do

 it





necessarily

 automatically

 like

 that

 now





you

 have

 to

 basically

 do

 it

 yourself

 so





I

 just

 want

 to

 point

 All

 those

 little





things

 that

 make

 a

 difference

 um

 because





it's

 already

 a

 little

 bit

 um

 not

 it's





not

 fine-tuned

 model

 but

 it's

 sort

 of





has

 context

 how

 to

 present

 data.

 Yeah.

</details>

[哼笑]

我们查看一下这里的进度。好的，我看到 Mike、Zack 和 Cool Deep……[笑声]……进展顺利。

对了，如果想使用不同的界面，这个也可以通过移动端访问。不仅仅支持桌面端，也可以通过移动端应用访问。

<details><summary>Original English</summary>

[snorts]





We

 check

 the

 pogus

 here.





Okay.

 I

 see

 Mike,

 Zack,

 and

 Cool

 Deep





[laughter]





doing

 well.





Oh,

 and

 this

 one

 is

 also

 accessible

 by





mobile

 in

 case

 uh

 you

 know

 you

 want

 to





do

 use

 a

 different

 interface.

 This

 is





not

 just

 like

 desktop.

 It's

 is

 also

 from





like

 the

 mobile

 app

</details>

<!-- chunk 5/12 -->

works.

<details><summary>Original English</summary>
works.
</details>

>> 对。所以，我觉得这是我想指出的一个点。市场价格功能会非常棒，因为［笑声］我知道我基本上……嗯，现在你必须在这个界面/工作面上操作。所以如果我现在提问，给出历史市场价格，嗯，对，我觉得如果有 API 的话会非常棒，但正如面对数据提供商时一贯的情况那样，你必须小心这里的授权许可运作方式。但在这种情况下，嗯，这基本上……嗯，比如非常重要的一件事，你想以简便的方式了解市场价格。而且如果我在内部构建它的话，也有机会承担起这项工作，因为你们都有那些内部系统。然后做一个扩展，一个插件——抱歉，一个插件，也许可以放在 ChatGPT Work 中，然后也可以在桌面端运行，并且现在完全能实现这一点，因为你们已经拥有数据库，可以访问内部数据，然后，对，也许可以使用相同的可视化效果，然后除了现成的产品之外再提供一个扩展……

<details><summary>Original English</summary>
>> Yeah. So, I think that's like the one thing I want to point out. market prices would be awesome because [laughter] I know I'm I'm basically uh right now you have to be in in the surface here. So if I ask the question now give me the historical market prices and um yeah I think that would be really neat to have an API but as is always like with data providers you have to be careful uh how the licensing works here but yeah in this case um it's basically um like a very important thing you want to know the market prices in an easy way and there would be also an opportunity if I built it in-house um to take that on because you all have those internal systems and then have an extension a plug-in sorry a plugin that sits maybe in chat GBT work and then also on the desktop side and does exactly that now because you have already databases access to internal data and then yeah maybe use the same um visualizations and then um provide an extension besides a product that's out of the
</details>

是的，它……嗯，这需要花一点时间。所以即使是这里的小幅调用也需要几分钟。因此如果你没有耐心，嗯，并且想走得更快一点，呃，你知道如何切换模型，或者你基本上……实际上，你知道你可以怎么展示，比如你点击左边这个微小的闪电图标……

<details><summary>Original English</summary>
Yeah, it's um it takes a little bit. So even the little pumps here a couple minutes. So if you impatient um and you want to go a little faster uh you know how to change the model or you basically the actually you know what you can show like if you click on this uh little thunder on the left
</details>

>> 你可以走……噢，不行吗？噢，不行。

<details><summary>Original English</summary>
>> you can go oh doesn't oh doesn't
</details>

>> 不行，噢，只有在 61 Soul 上才可以。如果你选 61 Soul 的话……我还以为这里允许使用 Ultra Fast 呢。

<details><summary>Original English</summary>
>> no oh only on 61 soul if you go on 61 soul I thought like ultra fast was allowed here.
</details>

>> 好的。太棒了。就用那个。真的很出色。

<details><summary>Original English</summary>
>> Okay. Fantastic. Use that. It's really beautiful.
</details>

>> 是的。是的。我……我的意思是，在 Open 工作的好处就是你可以使用 Ultra Fast。［笑声］

<details><summary>Original English</summary>
>> Yeah. Yeah. I I mean the the benefit of working at Open you can use ultra fast. [laughter]
</details>

>> 不，它在网页端应该也是可以运行的。

<details><summary>Original English</summary>
>> No, it should be working also on the web.
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 噢，对。我的意思是我……我现在选对了模型。所以，对。所以，对，选 Ultra 吧。嗯，而且我觉得正如我刚才所说的，在 OpenAI 工作的优势就在于，你平时正常的工作中实际上可以大量使用 Ultra，嗯，而且实际上我觉得这是天壤之别。我认为，嗯，如果这能对每个人变得更加普及/易于获取，嗯，这简直是……我的意思是，有多少人可能有时都在等待某些智能体工作，然后你在这期间并行做几件事，但是现在，现在我认为，是的，我非常赞赏它，嗯，而且我想指出的是，它在日常工作中非常有用。对，

<details><summary>Original English</summary>
>> Oh yeah. I mean I I did the right model now. So yeah. So yeah, do ultra. Um and also I think I'm just what I said the benefit of working in openi you can actually use ultra for your normal work a lot um and it's actually I think it's a day and night I think um if if this becomes sort of more accessible for everyone um it's just I mean I mean how many people probably waited sometimes for some agent work and then you do some couple things in parallel but now now I think yeah I I really appre appreciate it and um and I think um want to point out it's it's it's very helpful doing your work. Yeah,
</details>

### 模型效率、成本与架构策略

>> 我想说，关于这个话题，呃，引入很多我们与客户进行的讨论：我认为在过去的三个月里，Token 效率和 Token 成本可能一直是最优先考虑的事项。所以当然，现在你知道我们正在谈论 Astra，那是我们的顶级性能模型，但你能观察到的是，当然如果你正在从零构建全新的东西、一个全新的代码库，你在做研究，那么使用最强大的模型会给你带来优势；但当你构建更偏向重复性、可重复的任务时，只要构建了正确的上下文，你就能获得顶级模型的性能。所以如果你构建了正确的 Skill，更详细地向模型解释你所期望的内容，呃，那么即便是利用像 Luna，甚至像 61、6.1 Soul 这样的模型，其实际上极其出色，确实能给你带来顶级的性能表现。所以你不必总是去选用最昂贵的模型、最顶尖的模型。我们所见过的常见模式确实是：你可以考虑以恰当的方式构建这些 Skill，这将会最大化［清嗓子］性能表现，这是一种常见模式；或者如果你在更偏向多智能体的架构设置中工作，我们看到的是协调器（orchestrator）可能需要是其中最聪明的智能体，但单个子智能体并不需要都用 Astra，你可以切换到像 Terra、像 Luna 这样的模型，依然基本上能获得整体结果的 95%。所以当然，要进行所有这些衡量，关键在于用例本身，在于建立评测（evals），在于实际度量你所做工作的性能；但你知道，Astra 更多是用于完全全新的研究、全新的代码库，而其他模型，尤其是 Luna——那是我们最便宜的模型，比如我记不清……凭记忆想不起具体价格了，但它极其便宜。

<details><summary>Original English</summary>
>> I would say like on this topic uh bringing a lot of like discussion that we had with clients I think like token efficiency and token cost is like I think for the last three months has been like probably the main priority. So of course right now you know we are talking about Astra so that is like our top performing model but what you observe that is that of course if you're building something completely new a new codebase you're doing research using the most powerful model gives you a hedge but when you're building something like more like a repeating uh repeatable task you can get top level top model performance if you build the right context. So if you build the right skill that explains more in details you know what you expect to the model uh then even leveraging model like Luna or even like 61 6.1 sold is actually is extremely good can really give you the top of of the performance. So you don't have to go for like the most expensive model always the state-of-the-art model. What we've seen as a common pattern is really like you can think about like building the skills in a proper way that is going to maximize [clears throat] the performance and this is like a common or if you're working in more like multi- aent setup what we've seen is that the orchestrator needs to be like probably like the smartest of the agent but the single sub agent don't need to be like the Astra you can switch to something like Terra something like Luna and still get like basically 95% of the overall uh result. So of course to do all this measurement it's about the use cases about like kind of like building evals is about actually measuring the performance of what you're doing but you know Astra is more like for what is like completely new research new codebase but also the other models especially even Luna that is our cheapest like I don't remember like out of my like by heart like the the price but is is extremely cheap
</details>

我们已经看到，只要搭配正确的 Skill，它就可以被充分利用，并生成极高质量的内容，从报告到分析皆是如此。只是你需要使用正确的 Skill，并确保在正确的 Skill 下，性能表现确实能达到你的预期。但这是我们在各领域看到的非常棒的策略，用来实际优化成本。尤其是如果你考虑到，比方说你正在针对你的整个客户群运行这种财富管理礼宾服务，无论在成本方面还是在所需时间方面，规模都会迅速扩大；而使用像 Luna 这样的模型，配合恰当的 Skill 组合，确实能帮助你缓解这类问题。抱歉。

<details><summary>Original English</summary>
We've seen it like that with the right skills can be leveraged and produce extremely high quality content from like you know reports to analysis. It's just that like you need to use the right skill and make sure that with the right skill the performance is actually matching your expectation. But that's a great strategy that we've seen working across the board you know for actually optimizing the cost. Especially if you think that like let's say that you are running like this like wealth management conser concurge on like your kind of like entire universe of client that scales up pretty quickly both in terms of like cost and also in time time needed like using models like Luna that with the right set of skills can really like help you uh mitigate this kind of problem. Sorry.
</details>

>> 对。不，我觉得对，我认为关于……我的意思是模型迭代得很快，而且还会有更多模型推出，但对，很多时候，我的意思是每次我们拥有一个模型时，我也认为你必须弄清楚你目前的精力投入程度（effort level）大致如何，因为各项能力有时……现在它们在价位与能力之间的定位有所不同，所以我认为我基本上在目前的日常中大量使用 6.1 Soul，然后我能有条件奢侈地使用 Ultra。然后，但我认为有时当我创建工作坊的网站时，嗯，所以这一切当然都是用 Astra 创建的，嗯，甚至更高级的 Live Room 视图我想也是。对，那些基本上是我交托给 Astra 的任务。嗯，我就让它跑着。我是在周五那天让它跑的，之后它生成回来了，然后我只是用 Soul 对网站做了一点微调，因为它更快、效率更高。而且对，我认为每次有新模型出现时，摸清各项能力和精力投入程度非常重要。嗯，对，这总是在变化。我不能说我们不能……

<details><summary>Original English</summary>
>> Yeah. No, I think yeah, I think the point about I mean the models are changing quickly and there are more models coming but yeah it's often I mean every time we we have a model also I think you have to figure out what's your effort level sort of now because the capabilities sometimes sit differently now the price point versus um the capabilities so I think I'm I'm basically in my day right now I'm using a lot 6.1 soul and then I can have the luxury to use ultra of And then but I think ever sometimes when I created the workshop actually the website um so this all was created of course with Astra and um even the more advanced live room view I think. Yeah, those are the things I handed off to Astra basically. Um, I let it run. I I was on Friday. I let it run and it came back after that and then I just fine-tune it a little bit more the website with um soul because it was quicker and more efficient and yeah, I think it's very important every time a new model comes figure out the capabilities, the effort level. Um, and yeah, it's it's always changing. I cannot say we can't
</details>

>> 我想说，当你们进行各项练习时，想问你们的问题会是：对于你们目前在日常中如何使用这类产品和模型，大家有什么初步的想法吗？以及你们认为局限性或潜力分别是什么？有没有人想针对使用这类产品分享一些独到见解/即兴想法？

<details><summary>Original English</summary>
>> I would say like let's while you know while you go through um the various exercises like the question for you would be like any initial thoughts on like you know how are you using this model right now this type of product and models within your like day-to-day and what do you think are the limitation or the potential anyone wants to like hot takes on um using this type of product.
</details>

没有人。

<details><summary>Original English</summary>
No one.
</details>

### 构建者视角与插件架构

>> 好的。行。我们稍后再提更多问题。不过，所以我觉得当我第一次看到这个产品时——我的意思是，我们在内部较早就见过了——嗯，我说：“好的，太棒了。［笑声］但我还需要稍微多一点的内容。”所以也许我们可以转向一下。嗯，这个产品已经存在了，而且我认为它绝对是面向知识工作者的。但让我们从构建者（builders）的角度来思考。我对它有些热情，因为我的经验绝对也偏向构建端这一边。而且嗯，嗯，我想再稍微谈谈插件。所以我觉得插件架构，或者说内部包含什么的文件夹结构，在这里得到了很好的描述。你看这些 Skill、MCP 服务器——它通过工具连接到外部，然后你有一些 UI 组件，可以在使用插件期间被渲染；而用于金融服务的 ChatGPT Work 就是一个插件。所以，然后基于那样的架构你接下来能做的事情——这也许是转向更多构建者视角的过渡——就是提出一种以某种方式把所有这些不同部分组合在一起、充分利用这一切的架构。所以，这算是一张架构图，嗯，因为你必须问这样一个问题：你的界面/工作面（surface）是什么？所以当我说界面/工作面时，我们有 ChatGPT Work，它位于网页端；我们有本地运行的 Codec；或者我们在桌面端本地也有……嗯，然后作为构建者，我的意思是大家现在通常都能使用 Codec，但我看到这实际上在更多地走向知识工作者，未来两种用例在 UI 上可能会有更多的相似之处。因此，你在桌面上拥有它，而且在 Codec 中你可以做更多的事情，因为现在你可以……

<details><summary>Original English</summary>
>> Yeah. Okay. We'll have later a little bit more questions. But so, so I think when I when I saw the first time the product, I mean, we have it seen internally earlier. Um, I said, "Okay, great. [laughter] But I need a little bit more." So maybe we can pivot. Um, this product is there and it's I think definitely geared to the knowledge worker. But let's think about the builders. So I have a little passion for it because my experience is definitely in the building side also and um um I I want to go a little bit um on on the plugins again. So so I think the plug-in architecture sort of the folder structure what's inside and plug in um is nicely described here. So you see the skills MCP server which connects to something outside also via tools and then you have some UI components that could be rendered doing usage of the plug-in and JGBT work for financial service is a plug-in. So, and then um the the thing that you can do then with an architecture like that and that's maybe a segue now to go more on the builder side is come up with an architecture that leverage all that in a in a in a way that sort of brings all those different pieces together. So, this is sort of an architecture diagram um because you have to ask the question what's your surface. So when I say service, we have shed GBT work. We have which sits in the website. We have codeex which sits locally or we have also the shed locally in the desktop. Um and then as a builder I mean we all have now access usually with codecs but I see this actually coming to the knowledge workers more and then there will be probably more similarity in the UI for both um use cases in the future. So you have it on your desktop and you can do a lot more in codeex because now you can
</details>

<!-- chunk 6/12 -->

### 插件与本地 MCP 定制

实际上是安装一个本地 MCP。现在你可以通过代码、非常便捷地通过提示词来创建一个 MCP 服务器，它也许可以连接到你的内部证券投资组合数据库，或者也许是客户数据库，或者 Salesforce 也可能用在里面等等。但随后你就在那里构建它。作为开发者，你通常在那里会有一个原型。现在你基本上连接到你的本地网站之类的，并且你运行着一个 codex，它连接到该 MCP。不过你还想使用插件基础设施。因此插件基础设施位于 sht 托管中。我也许顺便指出来一下。所以如果你现在想在 shed GBT work 中获取自己的插件，你可以安装一个插件创建器。是的。所以你可以安装这个插件，当你安装了这个插件，你也可以在 JGBT workite 中安装插件。所以那是另一种定制它的方式，在桌面端你也可以做同样的事情。我不知道我是不是把你说糊涂了。但这基本上去思考这个交互界面，并且你有不同的途径来定制它。所以只要留意到，网页端的插件创建器是一种选择，然后在你的桌面端，当然你可以安装并接入。如果你有用户，你可以想出一种企业机制，把这些插件随你的 codeex 部署一起分发出去，不是吗？所以我们有类似于管理业务，每个人都会拿到 codex 以及对 shbt work 的访问权限，你可以摸清由企业管理的带有插件的文件夹结构是什么，然后通过你现有的机制来部署，那是一个巨大的好处。我的意思是，如果我现在自己构建一个应用程序，我必须操心如何登录，如何确保我的访问控制到位。所以如果你在企业内部私下构建一个应用程序，需要相当长的时间才能发布并获得批准。但如果你是在一个已经获批、正在运行且受管理的界面中构建它，你就可以接入进去。对吧。所以这算是在这里做个推介。所以是的，我们随后会使用一些 OpenAI 插件基础设施。在这个案例中，SHBT 金融服务可以访问我们的上下文数据，我们在其中拥有财务数据等。它仍然仅位于网页服务中。你无法使用 CLI。然后接下来的事情是，你会在你的插件中通过一个工具调用来连接你的数据库。那将是另一个 MCP，或者你以不同的方式来实现，并且你可以使用身份验证等手段，确保它以某种企业托管的方式连接到 OpenAI 托管环境，所有这些都是可以做到的。所以这算是进行稍微更多定制的一种方式，但你依然停留在这一套东西里面。我想我对此感到非常兴奋，现在有了所有这些选择。我的意思是，我喜欢自己构建智能体并进行托管，但在企业中要让它获得批准往往非常困难，如果你能够借助现有的东西，而且如果你在 codex 中拥有它，实际上会有一些护栏策略可以防止插件跑出沙盒之外。现在这个沙盒位于 codeex 中，你在那里拥有某些控制手段，然后如果我部署代码，我只需要想出一种企业批准的方式来让我的插件得到部署。对吧，所以这算是……我认为这是一个值得探索的绝妙想法，而且未来只会变得更好。

<details><summary>Original English</summary>

install a local MCP actually. Now you can create with code very with promps an MCP server that maybe goes to your internal security portfolio database or client database maybe or Salesforce could be also there used etc. But then you build it there. You have a pro you have a prototype usually as a developer there. Now you basically connect to your local website sort of and you have a codex running and it connects to the MCP but um you you also want to use a plug-in infrastructure. So the plug-in infrastructure sits in sht managed. So I also maybe just point it out. So if you want to get now your own plugins in shed GBT work um you can install a plug-in creator. Yeah. So you can install this plugin and when you install this plugin you can also install plugins in the JGBT workite. So that's another way of customization it and the same thing you can do on the desktop side. I I don't know if I confuse you. It's but it's basically think about the surface and you have different avenues to customize it. So just be aware the website plug-in creator is one option and then in your desktop of course you can install and plug in and if you have users you could figure out an enterprise mechanism to deploy those plugins with your codeex deployment no so we have um like a management business everyone gets codex and also access to shbt work you can figure out what's the folder structure with the plugins that's managed by the enterprise and then deploy through your existing mechanism and that that's a huge benefit. I mean if I would build now an application myself I have to worry about how to log in how to make sure my access control is there. So if you build an application on the side in enterprise it takes quite a time to get it out and approved. But if you build it in an in surface that's already approved and running and managed you can hook in. No. So that's sort of the plug here. So yeah, we would then use some of the OpenAI plugin um plug-in infrastructure. In this case, the SHBT financial services access to our context data where we have financial data etc. It still sits in the web service only. You can't use the CLI. And then the next thing is you would connect in your plug-in with an tool called your databases. and that would be another MCP or you do it um like in a different way and you can use authentication etc and making sure it's sort of an enterprise managed way of connecting it to the OpenAI hosted environment and all that can be done. So this would be sort of one way of doing a little bit more customization but you stay in this thing and I I think I I can just I'm very excited about all those options now. I mean I I love to build agents myself and host it, but to get it out approved in an enterprise is often very hard and if you can leverage something and also um if you have it in codex there are some um guard rails policies that can actually prevent that a plugin can go outside of the sandbox. Now the sandbox is sits in the codeex you have sort of controls there and then if I deploy code I just have to figure out an enterprise approved way to get my plug-in deployed. No, so that's sort of the I think it's a neat idea to explore and it can only get better in the future.

</details>

>> 是的。而且我认为，当我们谈论企业管控时，比如保持在……你知道，chibbity work 的这个界面内，以及哪种插件可以部署给哪位员工，这确实是非常普遍的需求。所以这里提供所有的企业管控，因此你确实可以管控访问权限，谁能访问数据、谁能访问插件等等。所以我感觉，我感觉 Oliver 刚才提到的这一点非常关键，特别是如果 charg work 是面向你的用户的最终界面，将一个想法、一个原型转化为一种真正能被你的最终产品……最终用户使用的部署插件，这比我们过去习惯的方式要快得多。我们有一个问题。

<details><summary>Original English</summary>

>> Yeah. And I and I think that like when we talk about enterprise control like staying like within [snorts] you know this surface of chibbity work and like which plug-in can be deployed to which employee is like really common request. So all the enterprise control here available so you can really control the access control who access the data who access the plug-in and so on so forth. So this I feel I feel that like what Oliver was mentioning is really like here especially if charg work is your final surface for your users the like transforming like an idea a prototype into a kind of like deployed plug-in that can actually be used by your end your end product um end user it's like much faster than what like we're used to. We have a question.

</details>

>> 所以你必须有服务器。

<details><summary>Original English</summary>

>> So you have to have server. [sighs]

</details>

>> 这取决于插件。所以这取决于插件，取决于你需要做什么，比如插件甚至可以是你所知道的一组技能（skills）。

<details><summary>Original English</summary>

>> So depends on the plug-in. So it depends on the plug-in depends like what you need to do like a plugins could even be like a a set of skills that you know.

</details>

>> 是的。那么到那时你就必须创建一个像 MCPlay 那样的插件。

<details><summary>Original English</summary>

>> Yeah. Then then you will have to create like a plugin like an MCPlay.

</details>

>> 没错。

<details><summary>Original English</summary>

>> Exactly.

</details>

>> 并且还要管理身份验证。

<details><summary>Original English</summary>

>> And also to manage the authentic authentication.

</details>

### Skill 与 Plugin 的区别及扩展机制

>> 对。对。所以，也许因为现在考虑到在这个世界中这是一个平台——我认为它已经是了——在这些术语下该在何时做什么。所以首先是一个 skill。我们有一些标记文件。我会用自然语言创建几个标记文件，说明该做什么，而且我认为现在在 codeex 的一些帮助下创建一个 skill 也相当容易，然后它有点像是一种复用提示词或者知识的可复用方法，不是吗？我认为这目前在 codec 端是可用的，所以如果你是一名开发者，我们通常使用 skills 来更快地进行开发。

<details><summary>Original English</summary>

>> Yeah. Yeah. So so so maybe because now think about in this world where this is a platform which I think it is already what to do when in those terms. So so first of all a skill. So we have like some markup files. So I would create in natural language um like maybe a couple markup files what to do and I think also it's like quite easy now to create a skill with some help from codeex also and then it's sort of it's a reusable u method of reusing prompts I would say or knowledge no and and I think that's available currently on the codec side so if you have a developer we're using skills usually to develop faster

</details>

它目前在网页端实际上是不可用的。但随后有趣的部分在于，plugin 就是你所说的那样，使用 skill 我无法真正进行企业集成。我在工作流中获得了一些可复用性，我可以进行扩展并在全公司范围内共享。但 plugin 则是涉及：“噢，现在我必须进行系统对系统的身份验证，或者我也许想代表用户来操作。”对吧，你必须为实际登录到你 codeex 端的用户进行身份验证。因此，这就是为什么 plugins 将是一个软件包，里面具备各项能力，也许还有一些你想复用的 skills。但接着正如你所指出的，我需要一些代码，我需要一些逻辑，我需要某种方式来获取用于身份验证的凭证等等。所以，这就是这里的 plugin。这就是一个插件。你之前也看到了文件夹结构。

<details><summary>Original English</summary>

It's not actually available in the web side right now. But then the interesting part is a plugin is what you said is with a skill I can't do really an enterprise integration. I have some reusability um in the workflow that I can scale and then can share it across the company. But the plugin is where oh now I have to authenticate systemto system or maybe I want to do on behalf of the user. No, you have to sort of authenticate um for the user that's actually logged in into your codeex side. So, so that's why the plugins will be a package where you have the capabilities maybe also some skills that you want to reuse. But then to your point, I need some code, I need some logic, I need to have some way of getting my credentials for authentication, etc. So, that's a plug in here. That's a plugin. And you saw the folder structure before.

</details>

然后它使用 MCP 连接，并且其中也包含一个 UI 组件部分。有一个应用 UI 标准，类似于通过插件来实现所有 UI 组件的一种方式，然后所有这些东西基本上可以打包压缩在一个包里，那就是一个插件。所以我认为 plugins 是最强大的，因为它们包含了所有东西的超集。然后正如我之前提到的，一旦你实际进入该界面——如果我回到插件扩展上——我想给你们展示一下，我认为这是一个有助于理解的好例子，因为我之前也很难理解什么是扩展，但在这里也许更加直观，所以我认为这是一个例子，我的意思是，你看这大致是你熟悉的 GBT 界面，但在左下角，你可以看到有一种方式可以添加你自己的图标，基本上就是你自己的应用挂钩（app hook）。然后一旦你点击它，现在这就全由一个你可以控制的插件来管理了。因此，妙处在于不仅仅是那个小图标你可以定制。你可以定制界面的不同部分。因此我们可以定制设置，我们可以定制导航，然后也可以想一想：我的意思是，如果我现在进入一家企业，为了完成我的工作我不得不访问五个不同的网站，我其实不想那么做。我想留在我最喜欢的工具里，它由 AI 驱动，有望拥有非常出色的前沿模型，而且我可以在其中针对我的工作流展开对话，而无需离开它。所以我希望做到的是，作为最终用户我在做我的工作，但随后它弹出来，它知道上下文：“噢，我现在有一件特殊的事情，关于获取……也许准备一个客户会议，比如准备客户会议。”所以它在对话中知晓这一点，并会为此弹出我的定制 UI。现在也许你的业务部门向你询问某件你想更快完成的事情，或者你想从内部系统查看该客户画像的某个指标。这就是你现在可以做到的，而且你不必离开这个界面。所以我想让你们大致了解这些概念所处的位置，如果你们能从这次会话中带走这一认知，那就已经非常棒了。

<details><summary>Original English</summary>

And then it uses MCP connections and there's also uh a UI component part of it. There's an app UI standard like sort of a way of doing all UI components with a plug-in and then all those things can be zipped up basically in a in a package and that's a plug-in. So it's really I would say the plug-in are most powerful because they contain the super set of everything. And then what I mentioned before is um once you actually in the surface so if I go back to the plug-in extensions and I think I want to give you I think this is I think a good example to understand it because I had also a hard time to understand what is an extension but here it's maybe more visually so I think this an example so I mean you see that's sort of the surface you're familiar with GBT but on the bottom left. You see there's a way of adding your own icon, your own app hook basically. And then once you click it, now this is all now managed by a plug-in that you can control. So, and the beauty is it's just not just this little icon there you can customize. You can customize uh different parts of the surface. So we can customize the settings, we can customize the navigation and then also think about it. I mean it's I if I go now in in in an enterprise and I have to go to five different websites to my job. I don't want to do that actually. I want to stay in my favorite tool which is AI powered has a very good frontier model hopefully um and I can have my conversation for my workflow and I don't have to leave it. So what I would like to do is I have my I'm doing my work as a end user but then it pops up it knows a context. Oh I have now something specialty around getting um maybe an ad u like a client meeting like a client meeting and have to prepare. So it knows in the conversation and it will pop up my customized UI for that. Now maybe the that your W business asked you about a certain thing you want to do quicker or you want to see a certain metric from an internal system for this customer profile. That's what you can do now and you don't have to leave the surface. So that's a I think I want to give you sort of an idea where those concepts sit and um if you take that away from the session that would be already awesome.

</details>

好的。有什么问题吗？好的。那我可能切换到我的可视化演示中，我设置好了 codec 端。现场可能也有一个问题。额，谁……

<details><summary>Original English</summary>

Yeah. So any questions? Yeah. So maybe I switch in in my visualization I set up the codec side. So would be a question also in the room. Um, who

</details>

<!-- chunk 7/12 -->

已经在本地运行 Codex 了？好的，我明白了。是的，挺多的。

<details><summary>Original English</summary>
has

 uh

 Codex





running

 locally

 already?

 Okay,

 I

 see.





Yeah,

 like

 a

 fair

 amount.
</details>

>> 是的，现在 CHP 应用的 codex 也是同一个界面。所以，是的。

<details><summary>Original English</summary>
>> Yeah,

 codex

 of

 CHP

 app

 right

 now

 where





it

 they're

 the

 same

 surface.





So,





yeah.
</details>

所以我现在就跟着操作一下，因为现在对我来说更多的是构建一个插件。是的。现在所有事情都成了一个问题。所以，是的，我认为这需要一些时间。所以即使使用 Ultra，因为我认为即使你使用 Ultra，你也必须构建代码并编译——或者不是编译，而是在本地运行它。是的。

<details><summary>Original English</summary>
So

 I

 will

 just

 play

 along

 a

 little





bit

 because

 now

 it's

 more

 um

 building

 a





plugin

 for

 me.





Yeah.

 And

 everything

 becomes

 just

 a





problem

 nowadays.

 So,





Yeah,

 I

 think

 it

 will

 take

 some

 time.

 So





even

 with

 Ultra

 because

 I

 think

 even

 if





you

 use

 Ultra,

 you

 have

 to

 build

 code





and

 compile

 or

 not

 compile

 but

 run

 it

 on





locally.

 Yeah.
</details>

### 本地算力与云端环境

所以也许这也是一件事，嗯，因为我经常这样做，当然是为了像这样的研讨会。这基本上……嗯，我现在是在我的台式机上工作。所以我可以多打开几个共享对话，再做一个项目，也许再创建一个插件之类的。但是是的，我认为你真正想要扩展的，基本上是智能体运行的地方，或者说基本上你想要拥有一个云环境。所以那是另一件非常有用的事情。

<details><summary>Original English</summary>
So

 maybe

 that's

 also

 one

 thing

 um





because

 I'm

 doing

 a

 lot

 like

 this

 of





course

 for

 like

 workshops

 like

 that.





It's

 basically





um

 sort

 of

 I'm

 on

 working

 on

 my

 desktop





now.

 So

 my

 I

 can

 have

 a

 couple

 more

 shed





conversations

 open

 and

 do

 another





project

 with

 maybe

 create

 another

 plugin





or

 something

 like

 that.

 But

 yeah,

 I





think

 you

 really

 want

 to

 scale

 um





basically

 where

 where

 basically

 the

 uh





the

 agent

 runs

 or

 basically

 you

 want

 to





have

 a

 cloud

 environment.

 So

 that's





another

 thing

 that's

 very

 useful.
</details>

嗯，我现在也为金融服务做了很多这种应用安全（appsec）扫描。所以这是一个非常常见的用例，是的，即使在台式机上，你占用了一个大型代码库，做某种应用安全检查，它现在也会占用你的本地算力，所以你希望把它转移到远端。所以在这种情况下，如果你有很多任务在运行，嗯，我认为是的，我们在那方面有一些开箱即用的能力，但你也可以自定义算力或 codex 实际运行的位置。现在在这种情况下，codex 是在本地运行的，即使模型很快，它也需要时间，或者说它花费的时间取决于我的笔记本电脑有多少性能。不是的。所以，但是是的，如果企业内部也能拥有那些基础设施组件就好了，在企业内部你基本上可以轻松启动和生成算力。不是吗，然后你把任务交接过去，基本上你等工作完成了再回来看。是的。

<details><summary>Original English</summary>
Um

 I'm





doing

 also

 for

 financial

 service

 a

 lot





of

 um

 this

 appsac

 security

 scanning





right

 now.

 So

 it's

 a

 very

 common

 use





case

 and

 yeah

 it

 takes

 even

 on

 a

 desktop





you

 have

 occupied

 a

 large

 repo

 and

 you





do

 like

 sort

 of

 a

 appseac

 inspection

 it





clocks

 your

 compute

 locally

 now

 so

 you





want

 to

 move

 that

 sort

 of

 to

 a

 so

 remote





site

 now

 so

 this

 case

 also

 if

 if

 you





have

 a

 lot

 of

 tasks

 running

 um

 I

 think





yeah

 we

 have

 a

 couple

 capabilities

 out





of

 the

 box

 there

 but

 also

 you

 can





customize

 it

 where

 actually

 the

 compute





or

 the

 codeex

 runs

 now

 in

 this

 case

 the





codex

 runs

 locally

 which

 takes

 even

 if





the

 model

 as

 fast.

 It

 takes

 time

 or

 it's





it

 takes

 as

 much

 time

 as

 my

 laptop

 has.





No.

 So,

 but

 yeah,

 it

 would

 be

 good

 to

 to





have

 those

 infrastructure

 components





also

 inside

 an

 enterprise

 where

 you





basically

 can

 easily

 spin

 and

 spawn





compute.

 No,

 and

 then

 um

 you

 hand

 over





task

 and

 um

 it's

 basically

 um

 you

 come





back

 when

 the

 work

 is

 done.





Yeah.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 技能市场与工件模板

>> 是的。所以这里有几个角度。是的，这个想法实际上特别是关于插件以及底层的技能，真正的想法不是让每个人都拥有不同的技能，而是去构建类似于一个市场，并在各个团队之间共享它们，这也与我们之前提到的更像是模板的内容相吻合。因此工件模板可以是一个网站，可以是一个 PowerPoint 演示文稿，也可以是一个 Excel。我们所看到的是，甚至在插件内部，你也可以构建添加一些历史示例作为文件，然后插件将以此作为参考。所以假设我们在为了这种情况需要创建一篇研究报告的语境下，比如针对你的私人财富客户，你实际可以做的是，也许提供几个历史示例，然后在技能内部要求将其作为参考，当然你可以修改它们，但这个想法实际上是要尽可能地具有可重用性。

<details><summary>Original English</summary>
>> Yeah.

 So

 the





there

 are

 a

 couple

 of

 couple

 of

 angles





here.

 Yes,

 the

 idea

 is

 really

 especially





with

 plugins

 and

 like

 you

 know

 and

 the





skills

 underneath

 is

 really

 like

 to





create

 not

 not

 to

 have

 everyone

 with





different

 skill

 but

 to

 actually

 build





like

 kind

 of

 a

 marketplace

 and

 share





them

 across

 teams

 and

 that

 works

 also





with

 what

 we

 were

 mentioning

 before

 that





is

 more

 like

 the

 templates.

 So

 artifact





templates

 could

 be

 like

 a

 website,

 could





be

 a

 PowerPoint

 presentation,

 it

 could





be

 an

 Excel.

 What

 we've

 seen

 is

 that





like

 you

 want

 to

 have

 like

 we

 even





within

 the

 plugins

 you

 can

 build

 some





like

 add

 some

 kind

 of

 historical

 example





as

 files

 and

 then

 like

 the

 the

 plug-in





will

 use

 that

 as

 a

 reference.

 So

 let's





say

 that

 we

 are

 in

 the

 context

 of

 like





you

 know

 piece

 of

 research

 that

 needs

 to





be

 created

 for

 this

 case

 like

 the

 your





you

 know

 private

 you

 know

 private

 wealth





clients

 what

 you

 can

 do

 is

 actually





maybe

 provide

 like

 few

 historical





example

 and

 then

 like

 ask

 like

 within





the

 skill

 to

 use

 that

 as

 a

 reference





then

 of

 course

 you

 can

 modify

 them

 but





like

 the

 idea

 is

 really

 like

 to

 be

 as

 as





reusable

 as

 possible.
</details>

因为我们知道格式非常重要，这就是为什么即使它并不真正与其中的财务方面相关，我们在工件创建上也投入了大量精力。所以如果你可能看到了，在过去的六个月里，我们模型的能力不仅能生成正确的电子表格，而且能实际以最高水平的格式化标准来排版电子表格，以符合投资银行的标准，这方面真的提升很大。所以我们有几个基准可以展示给你，但我认为最好的例子就是你自己去尝试。如果你有一些现成的模板、电子表格、演示文稿或 PDF，只要试着说，好的，用这篇新的分析，按照这种输出来构建，你将会看到输出可能会非常出色，然后当然这就是最后一公里，你可能需要稍微自定义一下技能，比如指出这里有几个细节不正确，但如果你在技能中提到了这一点，那么在下一次迭代中它们就会变正确。

<details><summary>Original English</summary>
So

 because

 like

 we





we

 know

 that

 like

 format

 matters

 a

 lot





and

 that's

 why

 like

 uh

 even

 if

 doesn't





really

 like

 connects

 to

 the

 financial





aspect

 of

 it

 like

 we

 we

 put

 a

 lot

 of





effort

 like

 in

 artifact

 creation.

 So

 if





you

 probably

 seen

 like

 over

 the

 last

 six





months

 the

 capabilities

 of

 our

 model

 to





produce

 not

 just

 correct

 you

 know

 a





spreadsheet

 but

 to

 actually

 format





spreadsheet

 in

 like

 highest

 possible





level

 of

 like

 formatting

 that

 like

 is





matching

 like

 investment

 banking





standard

 really

 went

 up.

 So

 we

 have

 like





several

 benchmark

 we

 can

 show

 you

 but

 I





think

 that

 like

 the

 best

 example

 is

 like





try

 it

 yourself.

 If

 you

 have

 like

 some





template

 or

 spreadsheet

 presentation

 PDF





that

 you

 want

 that

 you

 have

 and

 just

 try





to

 say

 like

 okay

 with

 this

 new

 piece

 of





analysis

 like

 build

 it

 in

 in

 this

 output





you're

 going

 to

 see

 that

 probably

 uh

 the





output

 is

 going

 to

 be

 quite

 strong

 and





then

 of

 course

 that's

 the

 last

 mile





where

 you

 probably

 going

 to

 have

 like

 to





customize

 the

 skill

 a

 little

 bit

 to

 say





like

 hey

 these

 are

 couple

 of

 details





that

 are

 not

 correct

 but

 like

 if

 you





mention

 it

 in

 the

 skill

 then

 at

 the

 next





iteration

 are

 going

 to

 be

 correct.
</details>

所以是的，最棒的部分是拥有可共享的技能，因为你也希望对它们进行某种微调。所以另一个有趣的点是，技能在不同类型的模型、不同的模型家族之间是否可以复用？答案是，如果我们在 charge 家族内部移动，是的。所以想法是，可能如果你从 5 跨越到 6，也就是跨度一年的这种跃升，你需要一些调整，但理论上在增量更新之间，[喷鼻息声] 我们看到的情况通常是你需要更少的具体规范，因为模型正变得越来越聪明，但这些技能往往具有相当的可复用性，维护成本也算合理，不至于太高。所以，嗯……

<details><summary>Original English</summary>
So

 yes,

 the

 best

 part

 is

 like

 having





sharable

 skills

 because

 you

 also

 want

 to





kind

 of

 keep

 fine-tuning

 them.

 So





another

 like

 interesting

 point

 is

 that





are

 the

 skill

 reusable

 between

 different





type

 of

 model

 different

 families

 of





model

 like

 the

 answer

 is

 that

 like

 if

 we





move

 within

 charge

 families

 yes.

 So

 the





idea

 is

 that

 probably

 you

 know

 if

 you





move

 from

 like

 you

 know

 five

 to

 six

 so





like

 a

 year

 a

 year

 uh

 kind

 of

 like

 jump





you

 need

 some

 adjustment

 but

 in

 theory





like

 between

 incremental

 updates

 like





the

 [snorts]





what

 we've

 seen

 is

 that

 usually

 you

 need





less

 the

 specification

 because

 the

 model





are

 getting

 smarter

 and

 smarter

 but





these

 skills

 tends

 to

 be

 quite

 reusable





and

 like

 the

 cost

 of

 maintenance

 is

 is





kind

 of

 reasonable.

 not

 to

 elevate

 it.





So

 um
</details>

### 技能管理与收敛

>> 是的，我认为技能实际上也可能成为一个无底洞。因为技能的可复用性以及后续的维护，我见过一些客户有点失控，搞出大量的技能，然后团队之间很难共享，你不得不对它进行某种标准化，所以这更像是一个组织层面的问题。但我认为如果你想，比如说作为应用构建者，我更倾向于做成插件，因为作为部署你也能对其进行控制，并且可以把它打包得更完整一些。如果我们身处前台或者像一些量化人员，他们每个人在自己的 codex 上基本上都有技能。所以接下来的问题是，如果你们团队中有两个人做类似的事情，他们都在创建一个技能，你如何确保它是可复用的？

<details><summary>Original English</summary>
>> yeah

 I

 think

 yeah

 maybe

 the

 skill

 can

 be





a

 rabbit

 hole

 also

 actually

 so

 because





yeah

 I

 think

 the

 skill

 reusability

 and





then

 also

 maintain

 it

 um

 I

 have

 seen





some

 customers

 go

 a

 little

 wild

 a

 lot

 of





skills

 and

 then

 the

 teams

 I

 mean

 it's





difficult

 to

 share

 and

 you

 have

 to





standardize

 it

 sort

 of

 so

 this

 is

 more





like

 an

 organizational

 problem

 but

 I





think

 if

 you

 want

 to

 like

 say

 you

 like





an

 app

 builder

 I

 would

 rather

 lean

 to





plug

 in

 because

 you

 control

 also

 as

 a





deployment

 and

 can

 package

 it

 a

 little





bit

 more.

 If

 I

 I

 mean

 we're

 sitting

 on

 a





font

 office

 or

 like

 some

 quant

 I

 mean





they

 have

 everyone

 has

 skills

 on

 their





on

 the

 on

 their

 codeex

 basically.

 So

 I





think

 the

 question

 is

 then

 if

 two

 people





in

 your

 team

 do

 similar

 things,

 they're





creating

 a

 skill,

 how

 can

 you

 make

 sure





it's

 like

 reusable,

 you

 know?
</details>

所以我认为，当你有几个团队成员，他们发现自己实际上在做一个类似的任务，可能带有一点可变性时，我强烈建议在你的团队中实际删减一些技能，因为它很难维护。我最近实际上建议过一个客户，我认为你们的技能太多了。我的意思是，也许试着对核心能力给出一个好的定义。如果你做投资组合分析，或者做某种交易分析，把那个保留为一项技能，但不要在你工作流中的每件事上都建技能，因为那样会变得很难维护。

<details><summary>Original English</summary>
So

 I

 would





say

 um





if

 it's

 a

 sort

 of

 when

 you

 have

 a

 couple





team

 members

 and

 they're

 figuring

 out





actually

 do

 a

 similar

 task

 maybe

 with

 a





little

 bit

 optionality,

 I

 think

 it's





highly

 recommended

 to

 actually

 remove





some

 skills

 in

 your

 team

 because

 it's





difficult

 to

 maintain.

 And

 I

 I

 actually





advised

 a

 customer

 recently

 that

 I

 think





you

 have

 too

 many

 skills.

 I

 mean

 maybe





just

 try

 to

 come

 up

 with

 a

 good

 like





like

 like

 a

 definition

 of

 the

 core





capabilities.

 If

 you

 do

 like

 an





portfolio

 analyszis

 or

 you

 do

 some





trading

 analyszis

 thing

 um

 keep

 that

 as





a

 skill

 but

 not

 for

 everything

 in

 your





workflow

 because

 it

 becomes

 kind

 of

 hard





to

 maintain
</details>

而且还有你刚才提到的那一点，你仍然需要针对模型重新测试。因为如果你与我们合作，其中一个潜在的好处是你也可以访问早期预览模型，当与我们建立合作关系时，因为这样你就可以看到当你使用某些提示词时，会对你的业务产生什么影响，你也可以提前进行测试，确保上线后它的行为符合相同的预期。但是的，我的建议是，如果你想管控好它，就坚持使用那些确实经过构建者深思熟虑、明确应该被封装起来的技能。如果看到太多人拥有太多技能，实际上也会拖慢处理速度。所以这并没有一个简单的直接答案，但你必须对其进行管理。这是我的建议。是的。

<details><summary>Original English</summary>
and

 also

 the

 point

 what

 you





had

 is

 um

 you

 still

 have

 to

 retest

 with





the

 models

 now

 because

 um

 what

 we

 what





is

 one

 benefit

 maybe

 if

 you

 work

 with

 us





is

 also

 you

 can

 access

 to

 the

 early





preview

 models

 now

 so

 when

 you

 have

 a





relationship

 for

 us

 because

 then

 you

 can





see

 also

 what's

 impacting

 your

 business





when

 you

 have

 certain

 promps

 and

 and





also

 and

 you

 can

 test

 it

 early

 now

 and





make

 sure

 when

 it's

 live

 then

 you





actually

 make

 sure

 that

 it's

 the

 same





expected

 behavior

 now

 but

 yeah

 my

 advice





is

 if

 you

 want

 to

 control

 it

 stick

 to





skills

 you

 have

 a

 builder

 that

 actually





thought

 about

 it

 what

 should

 be

 like





encapsulated

 encapsulated

 no

 and

 then

 if





you

 see

 too

 many

 people

 have

 too

 many





skills

 it

 can

 also

 slow

 down

 actually





the

 processing

 so

 Um

 it's

 not

 as

 like

 a





straight

 answer

 there

 but

 you

 have

 to





manage

 it.

 It's

 my

 recommendation.

 Yeah.
</details>

### API 用例向插件的演进

>> 我认为作为我们看到的大趋势，我们团队主要关注 API 用例。也就是那些你明确知道要使用 Response API 的用例。所以……像是一个不同的、第四个界面。但我加入 OpenAI 已经有几个月了。在这么短的时间内你已经看到的是，以前许多只有在你实际编写代码、使用 API 和 API 密钥时才能打包的用例，现在完全可以在插件内部重新创建。举个例子，可能稍微超出了财富管理的范围，我们在几个月前构建了一个内部用例，关于如何创建一份高级金融研究报告。你可以将其想象为深度研究（deep research），但专门针对金融类问题，使用的是 API。所以它类似于一个

<details><summary>Original English</summary>
>> I

 think

 as

 a

 as

 a

 general

 trend

 that





we've

 seen

 is

 that

 uh

 um

 so

 our

 team





mostly

 focuses

 on

 API

 use

 cases.

 So

 uh





use

 cases

 that

 like

 where

 you

 know





you're

 going

 to

 use

 response

 API.

 So

 um





eating

 like

 a

 different

 an

 like

 a

 fourth





surface.

 But

 I've

 been

 an

 open

 eye

 for





like





few

 months

 now.

 And

 what

 you've

 seen





already

 in

 like

 this

 kind

 of

 a

 short





period

 is

 that

 lot

 of

 use

 cases

 that





before

 were

 only

 able

 we

 were

 only

 able





to

 package

 if

 you

 were

 able

 if

 you

 were





like

 actually

 writing

 code

 using

 API

 and





API

 keys.

 Now

 they

 can

 be

 perfectly





recreated

 like

 um

 within

 uh

 with

 the





plug-in.

 So

 we

 to

 give

 an

 example

 guys





is

 a

 little

 bit

 outside

 of

 the

 world





management.

 We

 built

 few

 months

 ago

 like





an

 internal

 use

 case

 of

 like

 how

 to

 to





create

 an

 advanced

 piece

 of

 financial





research.

 So

 what

 you

 can

 think

 about





like

 as

 a

 deep

 research

 but

 specifically





for

 finan

 for

 financial

 type

 of

 problems





using

 uh

 the

 API.

 So

 it

 was

 like

 kind

 of





an
</details>

<!-- chunk 8/12 -->

### 多 Agent 协同与插件化

对多个 Agent 进行编排。从宏观架构来看，它的原理其实非常直观。首先有一个我们称之为规划器（planner）的角色，基本上就是一个接收问题并将其拆解成若干子问题的 Agent；针对每个子问题，它会创建一个子 Agent，让其以独立的方式展开调研；然后会有一个我们称之为审查 Agent（critique agent）或反馈 Agent 的角色，它负责收集所有这些独立调研的输出，汇总在一起，并核验各项结论之间是否存在冲突。

<details><summary>Original English</summary>orchestration of like multiple agents. So the like the schematics was pretty simple like on a high level. So you have what we call a planner. So basically an agent that ingest the question and split the question between like sub sub question and for each sub question create basically a sub agent that is going to investigate in an independent manner and then there's going to be kind of like what we call a critique agent a feedback agent that is basically taking all the output from these different independent uh research putting them putting them together validating that there is no not conflict if there is conflict between different findings.</details>

如果不同结论之间存在冲突，它会自动创建新的子 Agent 来调查这种矛盾，一直持续到最终报告达到相应质量并解答了所有想要涵盖的问题为止。所以，可以把它看作是子 Agent 的编排，一种高度动态的通用编排。现在大家完全可以做到这一点，实际上 Dom 就通过插件复现了完全相同的用例，也就是 Deep Research。对于客户来说，这种方式的可用性要高得多，因为首先，终端用户不需要离开当前界面跳转到另一种产品中，直接停留在 Codex 即可；他们可以实时看到子 Agent 正在做什么、在调研什么，你甚至可以为用户构建专门的界面来了解运行状况。而且凭借目前的多 Agent 能力，你可以直接在 Codex 中查看一切、完成一切，并且不必为了它新建一个代码库，只需创建一个插件并发布到 Codex 中即可。

<details><summary>Original English</summary>It uh creates automatically new sub agent to investigate this like this like kind of contradiction you know till a moment where like we the final report reaches like the quality and answers all the question that you want to cover. So really think about like an orchestration of sub agent and like kind of like a general orchestration that is really dynamic. Right now you can do we like actually Dom recreated that same use case using a plug-in talking about the deep research and that is way more usable for clients because first of all you know the end user doesn't have to leave the the interface to actually like you know enter like a different type of product that it can just stay in codeex it can actually visualize like what are the sub agents doing, what are investigating, you can create even a specific uh interface for the user to like understand what's going on. And with the current like multi- aent capabilities like you can really see everything in Codex, do everything in CEX and deploy you know instead of having like creating a new codebase just create a plug-in and ship it into Codex. So</details>

>> 为什么会想……所以我想我们可以问问作者本人。

<details><summary>Original English</summary>>> why would why would you want to So I think we can ask the author.</details>

>> 对。

<details><summary>Original English</summary>>> Yeah.</details>

>> 没错。另外还有 Matthew、Zack 和 Cohen，我觉得你们目前处于领先地位。这很有意思，看看最终结果如何吧，不过这里的竞争确实很激烈。

<details><summary>Original English</summary>>> Yeah. And also there's a Matthew and Zack and Cohen. I think you guys are leading here. I mean it's a fun thing. I mean let's see at the end. So but it's a tough race here.</details>

### 从独立应用到 Codex 原生工作流

>> 好的。关于我们在哪里、为什么以及何时会使用插件能力，通常最初的例子是股票的基本面深度研究（fundamental deep research for equities）。那是我之前构建的一个应用程序，探讨在这个领域如何以专业级的质量开展高度并行、经过验证的工作。它最终调用了大量的编排逻辑，意味着整个流程中包含大量的确定性与非确定性负载，并且当时是一个独立应用。后来逐渐清晰的一点是，很多从事这类工作的人并不会专门打开一个个独立的一次性应用来做这些事，他们开始把这些工作发生的地方统一起来，而那个地方恰好就是 Codex 或工作环境。因此，把功能整合到这一交互界面就变得非常合情合理。至于后续如何重构，关键在于：我能否利用 Codex 的各项能力——包括它的子 Agent 能力，以及它引导动态 Agent 结构以接入插件并连接到不同数据源的能力，而不用自己去构建那些定制化连接？

<details><summary>Original English</summary>>> Uh yeah. So when it comes to where and why and when we would use plug-in capabilities typically the the original example of that the fundamental deep deep research for equities uh was an application that I built about how to do deep parallel validated work in terms of that space out of professional quality. It ended up leveraging a significant amount of orchestration. It meant like a lot of deterministic nondeterministic workloads within that process and it was a standalone application. What started to make a lot of sense is that a lot of the people doing that work weren't going to standalone individual one-off applications to do that work. They started consolidating where that work happened and that happened to be in codeex or jetp work. So it makes a lot of sense to bring that surface area and then the choice of how that how we want to like rebuild that came down to the fact of can I leverage the capabilities of codeex including its sub aent capabilities including its ability to direct dynamic cap uh agent structures to allow plugins and connected to different data sources instead of building these bespoke connections and</details>

于是，将其打造为插件的思路就非常说得通了：专门利用并复用大语言模型能力来处理诸如动态工具调用等任务，特别是遵循模型本身的处理逻辑。我们称之为分布内工具调用（in-distribution tool calling）。正是这一点让工具调用变得更快、更准确。所有这些因素结合在一起，明确了这样一个方向：不再构建孤立的 Agent，而是把这些功能融入到一套工作流中——可以根据你想构建的把关卡点选择硬性或软性工作流——并把 Codex 作为主要的操作界面和产品载体。所以我基本上就是把一个老式的、经过大量手动微调的应用程序（它在某些节点使用大语言模型，在其他节点使用传统的确定性任务负载），整合到了 Codex 原生流程中。这完全是出于用户的易用性考虑：你不需要再去访问单独托管的网站，它变成了本地生成的；它可以根据需求进行定制，用户基本上可以说“我想改用这些数据源，我需要这些类型的卡点来保障质量”。因此，它不再是预定义应用里的黑盒，而是一个伴随用户演进的流程。

<details><summary>Original English</summary>it started to make a lot of sense to say hey this works as a plug-in specifically focused on utilizing and reusing the LM capabilities to handle things like dynamic tool calling specifically that in line with how models do that. So we call that ind in distribution tool calling. It's one of the things that makes things faster and more accurate in terms of how those tools happen. So all these things happen to line up to like make sense of like instead of building the standalone agent, build this functionality into a set of a of a workflow, a hard or soft workflow depending on the gates you want to build as and then use codecs as the main surface area, the product area for that. So I was basically taking an old school style really manually tuned application that was using large language models in some nodes and traditional terministic workloads others and consolidating them into a codeex native process which specifically for the use and ease of the user which is you don't have to go to this one hosted site. It becomes locally generated. It becomes customizable based on their needs. They can basically add hey these are the data sources I want to use instead. These are the types of gates so I have like quality bar gates. So it started to become less of a black box in this predefined application and more this evolving process that made sense to live alongside the consumer.</details>

>> 多谢 Dom。

<details><summary>Original English</summary>>> Thanks D.</details>

### 开源 Harness 与企业级可定制性

>> 好的。我可能还要为在场的构建者补充一点。我认为在底层架构上，我们的 Codex Harness 基本上是开源的。我觉得这也是一个巨大的竞争优势，因为你基本上可以完整访问源码——也就是运行我今天所展示内容的底层代码；你可以在桌面端以托管产品形式运行它，就像大家在这里看到的一样；但与此同时，你也可以通过 SDK 将其迁移到服务端或 App Runner，有程序化的方式来实现这一点。当然，你同样拥有完全相同的构建能力。大家可以看到这些插件，它基本上成了一种接入现有系统的方式，目前显然获得了广泛的关注。当你要实现我同事刚才提到的这种调研工作流时，它为你提供了多种选择：也许最初是由业务技术人员、量化人员或研究人员快速搭建出来的，但随后你希望将其扩展为服务端的应用程序。此时该怎么办？如何把已完成的工作扩展到整个团队？你可以借助 Codex SDK 将其接入真实的界面中（如果需要的话）。这只是一种思维方式，它变得非常灵活，让你可以自由复用成果并决定未来在何处托管。

<details><summary>Original English</summary>>> Yeah. So so I just have to maybe add to the builders here also a little bit. So I think under the hood I think we have the codex harness which is open source here basically. So that's also a big competitive advantage I think because you have basically the full access to the source code which running basically what I showed today here and then you run it on the desktop that's one option with a manage product and that's what you see here it's basically but then also you can take that and move it with an SDK to the server side or an appunner there's a way of doing that programmatically And then of course you have the same builder capabilities. You have you see you have the plugins that it's basically um becomes a way where you can plug hook into an existing system that definitely has a lot of traction now and um gives you multiple choices when you have this research workflow what my colleague just mentioned maybe created very quickly. Maybe a business tech or quant or a researcher has be able to do it. But then you want to scale it to an application on the server side. What do you do? How can you take the work you did already and scale it to the team? So you can take that and with the codex SDK you can hook it up in a real interface also if you need to. No, but you don't it's just a way that you think about it. It becomes very fluid where you can reuse your work and where you host it in the future.</details>

好。我们快速确认一下时间。我们还有 40 分钟。最后大概留 15 分钟提问，还是……

<details><summary>Original English</summary>Yeah. So, let's quick check time. We have 40 minutes. Yeah. Maybe 50 minutes at the end question or</details>

>> 对，我们最后会留大约 15 分钟进行问答，不过大家随时可以打断提问。

<details><summary>Original English</summary>>> Yeah, we're going to have like 50 minutes Q&A at the end, but feel free to interrupt at us any time.</details>

那我就继续围绕 Codex 稍微展开讲讲，补充更多背景，说明为什么我们认为它是一款出色的产品。正如我们提到的，Codex 的骨干底座（即 App Runner 等组件）是完全开源的，因此即便要在企业内部部署该产品，它也提供了极高的透明度。大家可以清楚地看到，第一方应用本身当然是专有的，但后台运行的引擎完全开源。所以它不仅透明，而且完全可定制。我认为这是个非常有趣的角度。在企业内部，你可以根据自身需求定制 App Runner，进而调用第一方界面。只要需要任何程度的定制，它都能支持。

<details><summary>Original English</summary>So I would you know keep talking a little bit on Codex just to give a little bit more context on like why we think it's a great product and as as we mentioned like the backbone of Codex so the uprunner and uh is a completely open source so even for more like to deploy this product within enterprise it gives like a lot of transparency to see exactly you know the first party app of of course is proprietary but like the engine that is run running behind is fully open source. So yeah it's not just transparent but it's also fully customizable. So uh I think that's kind of like really interesting um angle. So within enterprise you can actually choose to customize the uprunner that then is going to leverage the first party interface to your needs. If you need any level of a customization it's there.</details>

此外，我们认为与其他类型的界面相比，还有一个核心区别：我们的模型本身就是在该 Harness 中训练出来的。模型经历过大量的预训练和后训练，而在后训练阶段，它使用的正是我们自己的 Harness。因此，我们的模型虽然经过训练可以适配多种不同的 Harness，但在这一特定环境中能榨取更多性能。原因其实很直接：在训练阶段，模型就已经接触过这套代码库了。尤其是最近谈到多 Agent 能力时，正如 Dom 刚才提到的，越来越多的工作流（尤其是最先进的工作流）都在利用子 Agent，基本上由 Agent 自身来决定何时需要子 Agent、何时不需要。当然，如果你切换到所谓的超级模式（ultra mode，不是 ultra fast），我们就会促使 Agent 更多地利用这些子 Agent 分发调度能力。特别是在与子 Agent 协同工作时，Codex 能够提供好得多的性能，而且除此之外，在后台运行的还有……

<details><summary>Original English</summary>Additionally like what we think compared to you know other type of interfaces is literally that um our model are trained within with this harness. So our model you know you know there's a lot of pre-training and post- trainining but when we think about post- trainining the postraining is is leveraging like our own harness. So the our model basically are trained to work you know within like multiple harnesses but specifically on this one they're going to squeeze more performance for this kind of like trivial reason because they like within the training phase they're already exposed to to this codebase. So especially like recently if we think about all the multi- aent capabilities so what Dom was mentioning so more lots of like workflows the most advanced one are leveraging like sub agents and the basically we the agent itself is taking care of like deciding when a sub agent is needed and when it's not. Of course, if you move like uh within what we call the ultra, not ultra fast, the ultra mode, basically there like we are pushing the agent to leverage a little bit more these sub agent uh spudging capabilities. But especially when working with sub agents working sub aent codeex provides like a a much better performance and on top of that what you have on on the background is a</details>

<!-- chunk 9/12 -->

### 压缩模式与长运行任务

压缩模式（compaction mode）。所以压缩模式基本上就是一个辅助模型，它会获取当前对话的上下文并不断进行压缩，以此去除冗余，将大小控制在限制范围内，而且它是一个非常高质量的模型。我们在研究类任务中看到的，尤其是那些需要极长上下文的任务里，压缩模式确实让我们能够解决需要更长上下文的问题。所以这基本上让我们在所谓长运行任务（long running task）中表现得极其出色。

<details><summary>Original English</summary>compaction mode. So compaction mode is basically nothing but like a secondary model that is going to take the context of the current conversation and keep it compacting in order like to remove like the redundancies keep that the um the size you know within the the limits and it's a really high quality model. So what we've seen and this is a little bit more in what we've seen kind of like in the research type of task where like an extremely long context is needed. Compaction mode really allowed us to solve problem where like much longer context uh were required. So this basically allowed us to perform extremely well in what we call the long running task.</details>

我们团队经常会与对冲基金和自营交易公司合作。比如我自己做过的一个例子，我拿了一篇量化金融方面的论文，关于布朗运动和期权定价的，我直接让模型——我们当时说的甚至还不是 Astro，那是几个月前，大概是 5.5——在 Codex 内部复现论文的代码库，也就是复现论文的代码库，生成数值结果，看看它们是否与论文提到的内容相吻合。这个任务运行了几个小时，如果没有压缩模式，它是根本不可能运行下去的。两个小时后，我感到挺震撼的，模型竟然能够完整重现这个非常偏量化的代码库，包含随机布朗运动模拟，以及在此之上的模型校准。这基本上是一个没有压缩模式就无法完成的任务。压缩模式首先已经可以通过 API 使用了，但如果你使用 Codex harness，它在 harness 里也是直接可用的，你甚至都不需要多想。

<details><summary>Original English</summary>So um like we as a team we will frequently work with hedge funds and prop trading firms. So as an example I that I run myself is that I took like one of the papers from like quant finance like you know brownie emotion and like option pricing and I literally asked the model and we are not even talking about Astro it was like few months ago so it was like 5.5 to within codeex just replicate the the codebase of the mo of the paper so basically replicate the codebase of the paper generate the numerical result and try to see if they match what this what the paper mentioned. So there is like a task that you know it I think it ran for a couple of hours and where like it would have been impossible to run without compaction mode and then for example after two hours I was kind of kind of impressed that the model was able to fully reproduce this like you know really quant heavy codebase with like you know stoastic barium motion simulation calibration of models on top of that and that was like basically a task that without compaction mode is not achievable and compaction mode is already available first also via API but you know if you use the codeex arness is available in the arness and you don't even have to think about it</details>

### 插件扩展与 UI 集成

是的，我这边也在并行跑，我想有些人已经输入了提示词。它正在运行，目前基本上正在创建插件扩展。在右侧你可以看到在这个示例中，我自定义的 UI 是如何接入到界面当中的。这只是一个小例子，但输入提示词确实非常容易。它向你展示了一些 UI 选项。如果看我们的网站，其实能看到更多例子，展示了像 Figma 或 Adobe 这样的合作伙伴如何创建了更偏向于应用程序的东西，让你可以在其中做更复杂的事情。但我真的认为——我已经说过很多次了——我认为这大概就是行业目前的发展方向。你把它更多地看作一个 AI 平台，我想要接入其中，然后它基本上就是一个市场，企业内部也有自己的市场。当然，这是我个人的看法，但我在这里看到了强烈的相似之处。我认为作为构建者，你只需将其视为一个可以利用的机会。

<details><summary>Original English</summary>yeah so I mean I'm running in par I think the promps some of people have done it um yeah it's running um creating the basically the plug-in extension right now um yeah it's basically um you see on the right side the way of in this example, my customized UI could be hooked up into the surface. So, it's like a small example only, but yeah, it's it's pretty easy, of course, just to prompt. Um, but yeah, it shows you some UI options there. And then, um, if you look at our website, there are a lot more examples actually how our partners like Figma or Adobe have created a little bit more an app now where you can do a more complex thing. But I I really think I mean I have said it many times is I think that's where probably the industry is moving to now. You think about this more you have an AI platform and I want to plug in in that and then it's basically a marketplace and enterprises have their own inside and I think that's my personal view of course um but I see a strong resemblance here and um yeah it's I think it's a builder you have to just take as an opportunity you know to take advantage of. Yeah.</details>

>> 是的。我想说的是，当我刚加入 OpenAI 时，很多人还在使用 Codex CLI，因为大多数有工程背景的人都习惯了命令行界面。而我已经看到，极其专业的技术人员转向第一方应用、并且几乎不再离开 Codex 应用的比例越来越大。作为一个前量化人员[清嗓子]，我依然会做一些实验，以前我的 Jupyter notebook 总是开着，而现在它也已经集成在 Codex 里面了。所以我们真正认为、也是我们想要传达的信息之一，就是即便作为技术人员，Codex 也是一个非常出色的界面，你在 Codex 里可以获得所需的一切界面。然后作为技术人员，你可以创建插件，并将这些插件交付给有业务知识但非技术背景的用户。得益于企业级管控，你将插件投入生产环境的方式可以相当精简规范。你甚至可以在几周而不是几个月内为最终用户提供极其强大的工具。我认为特别是在金融服务领域，需要进行大量的数据摄取，每次可能都会有新的数据源、需要更改的内容或是需要做的新分析。这种全新的、基于 AI 的方法将极大地帮助提升生产力，就像我们看到 2025 年开始在代码编写方面发生的变化一样——大家都在谈论工程端那著名的 10 倍、100 倍生产力提升。我们这里的目标是将这种加速能力同样带给知识工作者。我认为这就是该产品背后的愿景，而金融服务由于融合了工件（artifacts）、数据源以及技术分析，感觉上是一种非常直接的契合。不过……对不起。

<details><summary>Original English</summary>>> Yeah. And I I would say that uh when when I joined OpenAI, a lot of people were still using Codex CLI as like you know mo most of people like you know coming from an engineering background like we're all used to CLI and I've seen that the percentage of like extremely technical people moving to the first party app and almost never leaving codeex as an app is getting like bigger and bigger. So uh as a former [clears throat] quant I still do around some experiment and right now like I used to have like my Jupyter notebook always open right now like is also already like within codex. So what we really think and I think one of the message that we want to pass is really like even as a technical person codeex is an amazing surface and it's getting like all the you know kind of surface within codeex that you need and then you can as a technical person create plugins and ship those plugins to your like knowledge but non-technical users and the the way that you can actually put put this plug-in in production is can be quite stream streamlined thanks to enterprise control and you can even you can give like really powerful tool to your end user in like weeks instead of month and I think that especially for financial services where like lot of data ingestion is needed every time there's maybe like a new data source something that needs to be changed like a new analysis needs to be done this this new approach this new like AI based approach is going to like really help maximize the productivity in a way that we've seen you know starting in 2025 for coding so that the famous like we all all heard like 10x 100x productivity on the engineering side our objective here is like to bring that booster also to the knowledge workers so that's kind of I think the the vision behind the product and financial services thanks to this like mix of like artifacts, data sources like and technical analysis feels like um kind of like an immediate match. But while sorry</details>

### 行业拓展与自下而上的数据构建

>> 大家对我们目前涵盖的所有这些话题有什么问题吗？

<details><summary>Original English</summary>>> any question on all this topic that we covered so far</details>

>> 我知道我们今天是来讨论金融服务的，但你们是否看到这种情况在其他行业发生？是因为金融服务的数据相当结构化吗？你们构建了本体层（ontology layer）。OpenAI 是否在医疗领域做这些？还有其他行业在发生这种情况吗？

<details><summary>Original English</summary>>> I know we are here to discuss financial services but do you see that happening in other industries? Is it the financial services because the data is quite structured? You build the ontology layer. Is open AI doing that for healthcare? Is something else happening? So,</details>

>> 答案是肯定的。我们正在多个垂直领域开展工作，医疗保健绝对是重中之重，在研究方面也是最大的优先级之一。另一个我们接触很多的是网络安全。网络安全正在发生翻天覆地的变化，在这个领域，除了我们提供的更针对网络安全的模型——我们的产品叫 Daybreak——我们基本上也同样构建了一个插件。这和之前的概念是一样的，核心理念就是你的网络安全团队不需要是 AI 专家团队，至少一开始不需要。所以基本上，我们为你提供模型，提供开源的 harness 来配合使用，同时我们还为你提供插件，比如用于进行静态资产扫描的插件，它针对我们的模型进行了微调。这有助于帮你建立基线，从而开箱即用利用模型、harness 和插件来运行一切。实际上我们有一个技能库（library of skills），能帮你完成从扫描到最终审查和打补丁的所有工作。不过[笑声]我们重点还是在金融服务上，但我们的关注点确实跨越了多个行业。当然，有些行业的好处更容易衡量，比如金融、网络安全、医疗保健和通用的科研，而在其他行业用例可能没有那么广泛。

<details><summary>Original English</summary>>> so the answer Okay, the answer is yes. So, um we are working on multiple uh verticals and healthcare is definitely um uh one of the most priority the biggest priorities also in terms of like research. Um I would say that the other one that we get exposed a lot is cyber security. cyber security is change is dra drastically changing and in the space for example aside of like the more the more like cyber security specific model that we offer like our offering is called daybreak um is also we also like basically build again a plug-in and what and again it's the same concept as as before the idea is that like your cyber security team doesn't need to be an AI expert team or at least at the beginning so we bas Basically, you know, we provide you the model, we provide the the ARS, the open source ARS uh to work with, but we also provide you like a plug-in for like, for example, for doing like assets uh static asset scanning that is going to is tuned on our model. So, it's going to help you create that baseline in order that like you know out of the box you can like models, harness, plugins to run everything. Actually we have like a library of skills that helps you to do everything from the scanning to the the final like review and patching. But you know this is not [laughter] we're focusing more financial services but our focus is really like across industries. Of course there are industry where like the benefit is like easy to measure finance cyber security healthcare research in general and others where like use cases like are not as broad. So</details>

>> 所以我认为对于平台扩展的构建者而言，更多的是数字化原生企业，或者说是通常在寻找新途径来分发其解决方案的软件提供商。我们团队与他们合作得更多。我认为我们今天来到这里，也是因为在纽约见到了金融服务机构。正如你所说的结构化数据，它本身很适合应用 AI。现在 AI 与他们的数据结合，而在那些公司里，打破数据孤岛往往很困难，那么在缺少上下文、本体等都不具备的情况下，你究竟该如何利用所有这些数据呢？所以我有时看到的策略是：跨所有数据存储建立一个恰当的上下文层需要耗费大量时间，那为什么不从现在开始自下而上进行呢？自下而上的方式就是，你拥有 Codex 的基础架构，然后团队自下而上地连接所有数据源，随着时间推移逐步构建起这种上下文，与此同时逐步推进数据架构的现代化。这样一来，AI 就会非常高效。我认为我们在公司内部有这个便利条件，我们没有那些遗留系统的包袱，已经拥有了这个上下文层。你能做到的事情简直令人惊叹。

<details><summary>Original English</summary>>> so I think it's for the extending platform builder. It's more I think our digital native businesses or like you would say sort of software providers that you usually look for new avenues to sort of distribute also their solutions now. So I think our team works sort of with them a lot more. I think what we are here because we in New York also met financial services. I think it's what you say it's a structured data is it it lends to itself to use actually AI. Now AI is sort of um with their data and I think it's kind of always hard to sort of have those data silos in those companies and then how can you actually leverage all this data in a context which is not there. It's not ontologies etc. is not there. So sometimes I think what I see as a strategy is sort of you have a it's it will take so much time to proper context layer across all the data stores but why don't we start from the bottom up too now so bottom up would be you have sort of the shb work of codex and then you have teams that basically connecting bottom up to all the data sources and build sort of this context over time while you modernize your data architecture over time. So it's sort of the AI would be super efficient and I think we have the luxury internally. We don't have those legacy things. We have this context layer already. It's it's amazing what you can do</details>

<!-- chunk 10/12 -->

作为一支劳动力，如果它真正被释放出来的话。但是你必须自下而上，然后再自上而下，这会需要更多的时间让你真正去规模化实现。是的。

<details><summary>Original English</summary>
then as a workforce if it's actually unlocked. But you have to bottom up and then top down will take more time for you actually to do it at scale. Yeah.
</details>

那么来看看。嗯，Co、Matthew 和 Zakia，我想我们有这个，我的屏幕保护程序……我还想讲一件事，我想嗯，可能也要提一下，嗯，所以当你在 Codex 内部安装比如任何扩展时，不，我想这里也必须……也许你实际上会有一些代码随后运行在别人的桌面上，对吧，或者你在网站里运行它，对吧。所以在我们的安全团队中，我们与他们进行了很多讨论，嗯，你如何能确保它们不会造成任何危害？我的意思是，必须有某种沙盒，而且我认为嗯，也许理解 Codex 的沙盒机制是一个非常重要的概念，因为这是实际走这条路的另一个好处。因为比方说你有一个插件必须进行工具调用（tool call），所以你想限制该工具能从 URL 访问哪里。你总是必须有多重控制。你想从企业级控制、网络安全、端点检查开始，但是一旦你在一个平台上有了一个应用程序，你也想在它内部拥有控制。

<details><summary>Original English</summary>
So let's see. um co Matthew and Zakia I think we have this my screen saver I want to talk one more thing I I think um it's probably to to mention also um so when you install like sort of any extension inside a codeex no I think there's also you have to maybe you actually have some code running then on the desktop of someone else no so or you have it in the website no so in our security teams we have a lot of discussion with them and um how can you make sure they don't do any harm I mean there must be some sandbox and I think um maybe just sandboxing with codeex is a very important concept to understand because it's another benefit to go actually go this way because let's say you have a plugin that has to do a tool call so you want to limit where the tool can go from an URL you You always have to have multiple controls. You want to start with your enterprise controls, networking security, endpoint inspections, but once you have a an application on a platform, you want to have also controls inside there.
</details>

所以 Codex 实际上提供了呃策略，嗯管理在企业管理员端的 config toml 配置文件，但也会在你进行部署时下发，而在这些方面你可以决定，好的：我不想让这个插件能访问某个网站，对吧；并且我想确保某些事情也只能在我的工作区完成。比方说一个团队在企业内部开发了某些东西，但它不能比如访问一个敏感的项目文件夹。

<details><summary>Original English</summary>
So the codeex provides actually uh policies um the config files toml that are managed on an administrator site as an enterprise but also push down when you do a deployment and in those sides you can decide okay I I don't want to get that this plugin can go to a certain website no and I want to make sure certain things can be only done also on my workspace let's say a team develops inside an enterprise something but it could not go like to maybe like an sensitive project folder.
</details>

现在，你实际上可以通过 Codex 内部的策略、企业策略来限制，对吧，限制本地可以通过 Codex 客户端访问什么，以及什么网络、什么 URL，嗯甚至某些人可以操作什么插件。我认为理解这一点很重要。有一种精细的方式来实现这一点，而那基本上就是你在这里也能看到的配置。它是 custom config toml。所以这是你们的企业管理员会为不同的团队在企业层面上统一界定一次的东西。它会下发下去，并且拥有我刚才提到的所有那些东西。安全沙盒机制，因为托管在 Codex 客户端内部的任何内容都将在其中运行。你仍然必须自己去保护工具等，但我认为这已经是这种架构的一个优势了。

<details><summary>Original English</summary>
Now, so you can limit actually um with policies inside codeex an enterprise policy. No, what is can be accessed locally via the codeex client and also what network what URLs um maybe what even plugins certain people can do. And I think that's important to understand. There's a sophisticated way to do that and and that's basically the configuration that you can see also here. It's the custom config toml. So this is something your enterprise administrator would define once on an enterprise level for different teams. It pushes it down and it has all those things I just mentioned. the security sandboxing because it will run whatever it's hosted inside the codeex client will run inside that you still have to protect tools etc yourself but I think that's already a benefit um for this architecture
</details>

然后接下来的事情是，我们都知道这有点困难。我的意思是，安全团队走到了最左端，我们想要、我们想要做嗯任何敏感操作，但随后业务用户说：“嘿，太慢了，我总是得点击‘请转到此插件，转到此网站’”。而且我认为嗯，这里独特的也是我们有一个呃就像做一个 Guardian 的方式，就像我们实际上可以在涉及关键还是非关键时把决策稍微自动化一点，而这也是一种确保当你使用 Codex 设置时，它能够在安全作为策略所需要的与最终用户的便利或舒适之间取得平衡的方式。这有助于确保何时是敏感的，何时是不敏感的，我是否需要进入这个工作区文件夹。所以我认为强调这一点也非常重要，因为我认为这是你现在构建插件时也必须向你的用户解释的事情。

<details><summary>Original English</summary>
and then the next thing is we all know that it's sort of difficult to I mean the security team goes all the way left we want to we want to we we want to do um um like any sensitive operations but then the business user says hey it's so slow I always have to click please go to this plugin go to this website and and I think um what also it's unique here we have a uh like the way of doing a guardian like we can actually um automate a little bit the decision- making when it's critical or not critical and this is sort of a way also to make sure when you use a codex setup it's sort of balancing what security needs as a policy but also what's convenient or comfortable for the end user and this helps to make sure when it's sensitive and when it's not sensitive do I need to go to this workspace folder or not so I think that's very important also to highlight because I think this is the thing you have to also explain your users now when you build plugins
</details>

### 提问环节与礼品赠送

>> 不，是的，就像基本上我们合作的每一个大型机构，他们都会为审批权限定制呃配置。所以这确实是一个……通常当我们讨论在整个企业中部署 Codex 时，这是我们讨论的第一个重点。再说一次，这其中有很大的灵活性。还有其他问题吗？

<details><summary>Original English</summary>
>> no yeah like and basically every every big institution we work with they will customize uh the configuration for approval permission. So that's like a really like usually when we talk about like deploying codex across the enterprise that's the first like point that we discuss about and like again there is a big flexibility there. Any other question?
</details>

>> 那么，可能差不多快结束了。我想我们是不是应该……

<details><summary>Original English</summary>
>> So, so maybe maybe almost the end. I think should we
</details>

>> 发出我们的邀请，然后再问一些问题，如果你呃……Co、Matthew 和 Zack，我想呃领奖者……像所有优秀的技术公司一样，我们带来了一点周边礼品。

[笑声]

<details><summary>Original English</summary>
>> get our invite and then maybe ask some question if you uh co Matthew and Zack I think uh the leading as every good tech company we brought a little bit of merch.

[laughter]
</details>

那么，我们是不是应该说，Co、Matthew 和 Zach 是获得今天早上从办公室拿来的、印有 OpenAI 品牌的神奇水瓶的人。

[笑声]

所以，如果你、如果你还在这里的话，来看看。否则的话……那么先从呃 Coin 开始吧，我不知道怎么准确发音。

<details><summary>Original English</summary>
So, like should we say that Co, Matthew, and Zach are the one getting an amazing water bottle branded OpenAI

[laughter]

picked this morning from the office. So,

[laughter] if you if you're still here, let's see. Otherwise, so let's start like uh Coin. I don't know how to pronounce it correctly.
</details>

>> 对，上来吧。

<details><summary>Original English</summary>
>> Yeah. Come up.
</details>

>> 到这上面来。对。

<details><summary>Original English</summary>
>> Come up here. Yeah.
</details>

>> 是的，感谢你回答问题。它不是太难。所以……

<details><summary>Original English</summary>
>> Yeah. Thanks for answering the question. It was not too hard. So
</details>

>> 对，那么也许……

<details><summary>Original English</summary>
>> yeah. So maybe
</details>

>> 介绍一下你自己。

<details><summary>Original English</summary>
>> tell me about you.
</details>

>> 好的。我叫 Um，我在荷兰做数据工程师。嗯，所以看到这里的听众也挺有趣的。我去过伦敦的 AI Engineer。嗯，我也期待在这里认识很多人，看看大家在这里做些什么，特别是在金融行业。嗯，关于我就这些。是的。

<details><summary>Original English</summary>
>> Yeah. So uh my name is Um I'm working as a data engineer in the Netherlands. Um so it's pretty interesting to see also the crowd over here. I've been to AI engineer in London. Um and looking forward also to meet a lot of people over here and to see what people are doing here especially in the financial industry. Um that's about me. Yeah.
</details>

>> 你是来自哪家公司？

<details><summary>Original English</summary>
>> And you are from company
</details>

>> Data。我们是一家咨询公司，呃对，在全球开展业务，我在荷兰部门工作。

<details><summary>Original English</summary>
>> data. So we are consultant company uh yeah working worldwide and I'm working for the for the Dutch uh section.
</details>

>> 谢谢你。

<details><summary>Original English</summary>
>> Thank you.
</details>

>> 谢谢你。

<details><summary>Original English</summary>
>> Thank you.
</details>

>> 然后我们有 Matthew。是的，太棒了。对，你现在也得说点什么了。[笑声]

<details><summary>Original English</summary>
>> Then we have Matthew. Yeah. Awesome. Yeah. You have to also say something now. [laughter]
</details>

>> 我希望这很有趣。

<details><summary>Original English</summary>
>> I hope it was fun.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 好的，噢，谢谢。这太棒了。呃我叫 Matt。呃公司是 x1wealth.com，我们正在构建一个 AI 原生家族办公室。所以，我在用 Codex 做大量的事情，这非常有帮助。

<details><summary>Original English</summary>
>> Yeah. Oh, thank you. This was this was awesome. Uh my name is Matt. Uh company's x1wealth.com and we're building an AI native family office. So, I'm doing a ton with codeex and this is very helpful.
</details>

>> 非常感谢。

<details><summary>Original English</summary>
>> Appreciate it.
</details>

>> 我觉得 AI 原生听起来非常棒。我想我 [笑声] 会投资那个。

<details><summary>Original English</summary>
>> I think an AI native sounds very good. I think I [laughter] would invest in that.
</details>

>> 是的，太酷了。好的，谢谢。然后最后一位，Zach。

好的。

<details><summary>Original English</summary>
>> Yeah. Cool. Yeah. Thank you. Then last one, Zach.

Okay.
</details>

>> 对，上来吧。

<details><summary>Original English</summary>
>> Yeah. Come up.
</details>

>> 嗨。我是 Zach。我是 Clockworks 的创始人，我构建利用 AI 探索我们以前无法做到的新事物的应用程序。我主要关注开发主题，但是你知道，我总是在寻找新机会。所以……

<details><summary>Original English</summary>
>> Hi. So, I'm Zach. I'm the founder of the Clockworks and I build apps that use AI to explore new things that we haven't really been able to do before. I focus mostly on development topics, but you know, I'm always looking for new opportunities. So,
</details>

>> 谢谢你。

<details><summary>Original English</summary>
>> thank you.
</details>

>> 我有一个，是的，很好。对，我有一个想法。所以我认为留给你的作业是在……[笑声] 构建一个插件扩展并将其发布在应用市场或插件市场上。是的。

<details><summary>Original English</summary>
>> I have a Yeah, good. Yeah, I have an idea. So I think the homework is for you by [laughter] to build a plug-in extension and put it on the marketplace or plug in. Yeah.
</details>

>> 你认识能帮我们推进通过它的人吗？

<details><summary>Original English</summary>
>> Do you know anyone that can help us push it through?
</details>

>> 噢，你已经在那里了。所以……

<details><summary>Original English</summary>
>> Oh, you already there. So
</details>

>> 是的，他、他、他懂的。

<details><summary>Original English</summary>
>> yeah, he's he's he gets it.
</details>

>> 是的。所以是的，这也是另一件事。所以我的意思是，现在有了所有的市场，所以你必须稍微提交一下，因为它也可以面向外部客户。但我认为，如果你这样看的话，我认为这对大家来说是一个信号——我的意思是，现在这也许是 B 到 B2B 外部市场，但也不要忘记内部企业也是同样的概念。是的，但我认为这确实是一个信号，你必须利用正在涌现的分发渠道。也就是新兴的分发渠道，我们都在应用商店看到过它，看到它有多么具病毒式传播效应。所以基本上可以把它看作是另一种方式，当然如果是公开的话会有安全审查，所以我们只需要确保它顺畅、安全、可靠，并且符合正确的分类，不过是的，我认为它是一个信号，这就是 [笑声] 我想说的。是的。

<details><summary>Original English</summary>
>> Yeah. So yeah, this is also another thing. So I mean with all the um marketplaces now so there's a little bit you have to submit it because it can go also to external customers but I think if if you see it like this this is I think a signal for people I mean this is maybe B to B2B outside marketplace now but also don't forget the internal enterprise thing is the same concept yeah but I think it's really a signal where you have to leverage the distribution channels that are sort of emerging. So the emerging distribution channels and and we have seen it all with the app store and all how viral it is now. So basically think it is another way and of course the SM review if it's public now so and we just have to make sure it's smooth and safe and secure and it fits the right category now but yeah it's a I think yeah just it's a signal that's [laughter] what I want to say. Yeah.
</details>

>> 是的。我知道那……我认为这也是开源代码库的魅力所在，我想说的是，再次强调，今天我们更多地涵盖了你知道的我们的产品层面，所以像 Codex、ChatGPT……但我们也与客户进行了大量互动，致力于定制用例的工作，具体来说比如在 API 用例上。当然那稍微更复杂一些，有许多主题我们可以讨论，但我们开展的大量合作实际上是去理解用例，帮助带来最佳实践，因为我们是我们产品的第一个内部用户，我们确实也与行业内的许多人交流。所以例如，正如我们之前提到的，evals 这个神奇的词，我认为是比如最重要的一个。所以简直就是帮助客户去理解如何针对正确的问题设计正确的 eval。问题总是在于，我们谈论提升生产力，但尤其是当你想上线生产环境时，你需要有一种方法来实际衡量你的产品的性能。再次强调，当我们在谈论特定的聊天线程时，在那里你不需要任何 eval，但当你构建你的智能体时，那就是必须的了。例如你……

<details><summary>Original English</summary>
>> Yeah. I know that's I think is that's also the beauty of an open source code base and I would say that like again today we cover more like you know our product surface so codeex charg work but we do also a lot of interaction with clients when working on bespoke use cases and specifically like on uh API use cases like of course that's a little bit more complicated and there's a lot of topics that we can discuss but like a lot of the engagement that we do is actually understanding uh the use cases helping like you know bring best breast practices because we are the first user internal user of our product we do speak with a lot of people in the industry. So for example as we like mentioned before this magic word evals I think is like the most important one. So literally like helping clients you know understanding you know how to design the right eval for the right problem and the question is always like you know we talk about you know boosting productivity but especially when you want to go to production you need to have a way to measure like actually the performance of your product and it's you know again when we're talking about like specific you know chat thread like there you don't need any valves but when you build your agents then it's needed And for example you
</details>

<!-- chunk 11/12 -->

### 评估与自动研究工作流

了解这方面的最佳实践，比如如何构建评估（evals），了解在评估数据集中，性能为何无法达到要求，诸如此类——你知道，可能不是模型的问题，而是关乎如何改进套件（harness）、提示词以及与工具的连接；有时也确实是模型的局限性，所以我们也会反哺给研究团队，去了解我们的模型在哪些地方遇到了瓶颈，在哪些地方即便处于完美的环境中表现也不符合预期；理想情况下，得益于各位的反馈，在下一次模型迭代中这些问题就会得到解决或改善。不好意思，我们这边有一个提问。

<details><summary>Original English</summary>
 know best practices there on like how to build evals understanding like out of an evals data set the performance why the performance is not meeting the requirement you know what the kind of like you know probably like it's not about the model it's about how to improve the arness the prompting the connection with the tools and sometimes it's also like a model limitation so we also connect back to research to understand like where our model are hitting the limits where they're not behaving even if in the perfect environment as expected and ideally you know thanks to your feedback at the next model iteration that is is kind of fixed or improved. We have a question sorry.
</details>

>> 是的。关于评估这个话题，我很想知道，从评估的普及度、对基础概念的理解，甚至深入到像自动研究（auto research）这类更高级的工作流主题来看，您对目前市场的成熟度有什么看法？

<details><summary>Original English</summary>
>> Yes. So on the topic of evals, I was quite curious to see where what your perspective is in terms of the market's maturity in terms of adoption of evals and understanding of the fundamentals and even going into advanced topics or more advanced topics like auto research type of workflows.
</details>

>> 好，这是一个相当宏大的问题。让我们先从评估谈起。我想说的是，评估通常是最主要的阻碍因素，因为构建评估——这也只是我个人的看法，所以也很乐意听听大家不同的想法。其复杂性源于评估通常融合了大量的业务知识，这些知识来自于 SME，也就是领域专家（subject matter experts），但实际上评估却是由工程师构建的。因此，要组建一个兼具领域专家和工程师的交叉团队来构建评估，并非易事。

<details><summary>Original English</summary>
>> Okay, so this is a pretty big question. Let's start with the evals. Uh I would say that evils are the most usually the blocker because building evils and this is my personal perspective. So happy to uh hear like different thoughts. The complexity comes from the fact that evals usually incorporates a lot of like business business knowledge. So coming from uh SMMES so subject matter experts and actually they are built by engineers. So uh it's having you know the intersection of like a team that has like subject matter experts and engineers to build evals is not trivial.
</details>

所以我通常一直——当然这里也有我的个人偏好，因为在我之前的工作中我是所谓的量化研究员——对我来说，每当你构建一个智能体，评估都是最重要的一环，因为如果不去衡量性能，就无法进行优化。这不仅仅是像一行代码那样说“我有自己的评估，达到了70%”，还要去理解背后的底层指标，比如首先要知道我们在哪些方面表现良好，在哪些方面表现欠佳等等。所以我认为评估确实是非常困难的一部分，但这不是因为技术本身有多高深，而是因为你基本上需要把专业专长融入到工程创建的数据集中。

<details><summary>Original English</summary>
So usually I always and again here there is a bias because in my previous job I was like what is called a quantitative researcher like for me whenever you build an agent evals is the most important piece because you cannot do optimization if you don't do not measure the performance and it's not just you know like the one line of like oh I'm you know I have my evils and it's like 70% there but it's also understanding the underlying metrics of like you you know first of all like you know where are we performing well where are we are not performing well and so on so forth so I think like evas is like a really hard part but it's not because it's a difficult technology is because like you need to basically put like expert like expert expertise within like kind of like an engineering created data set
</details>

那么关于这方面的最佳实践，简而言之，我认为始终要从简单的做起。不要一开始就用大语言模型充当裁判（LLM as a judge）。先从简单的开始，然后再增加复杂性，否则你永远分不清究竟是评估的质量不够好，还是智能体的质量不够好。所以对我来说，这就是一种最佳实践。还有我们在使用大模型作为评估工具时经常建议的一个“秘诀”：不要让它给出1到5的打分或评级，始终让它回答“是”或“否”，这样效果要好得多；尽量把1到5分的评价拆解为真或假。

<details><summary>Original English</summary>
so then best practices there like to keep it short I think like always like start simple Don't don't start with the LLM as a judge. Start simple and then add complexity because otherwise like you'd never understand if like the quality of your evals is not good enough or the quality of like the agent is not good enough. So that's for me like the like kind of like best practice and one kind of cheat code that we always suggest when you use LLM as an agent don't ask to rank one to five to score one to five always ask yes or no it's much better try to decompose that one to five into a true or false
</details>

而且顺便宣传一下，我们最近也发布了决策 API（Decision API），所以你完全可以使用一个基于 o1 的优秀模型，它能极快地告诉你“是”或“否”，并给出围绕该答案的概率与置信度。因此我认为决策 API 的很多潜在应用场景实际上都可以在评估中发挥作用。这是第一部分。

<details><summary>Original English</summary>
and you know like right now like doing some promotion we also release like the decision API so you can have literally a model that you know it's quite good is based on out of Luna and it's going to tell you like you know you know quickly super quickly yes or no and the probability and the kind of the confidence around that answer so I see that like a lot of possible application for a decision API uh could be actually within the evils so that's the first part
</details>

第二部分是自动研究，这是一个非常宏大的课题。我认为这确实是今年才开始显现出重大突破的方向。我所看到的是，而且也有基准测试证明，我们在去年就已经具备了非常优秀的编程能力，但我们的模型，特别是在数学能力上，近期有了显著的提升，尤其是随着 o1 和相关版本的推出。因此我认为，尤其是从量化的视角来看，编程与数学研究的结合，真正使这种更偏向自动研究的任务成为了可能。

<details><summary>Original English</summary>
second part is auto research it is like a really big topic it is um something that uh I think really started significant this here and uh what I've seen is that like and there are benchmarks so like we reach really good coding capabilities already last year but like our model specifically really like improved on the mathematical capabilities more recently especially with like Astra and 5.6 six. So I think like especially from a kind of quant perspective like the intersection of coding and math research really allows you for this like more auto research task.
</details>

举例来说，自动研究任务之一就是我之前提到的复现论文。当然，其中会有不同层级的复杂性，但尤其是当你考虑到某个想要提升的特定指标——也就是我们人工智能术语中所说的“爬山算法”（hill climb）——我们在 Codex 中提供了所谓的“目标模式”（goal mode）。基本上在目标模式下，你必须指定目标是什么，而且这个目标最好是一个具体的数字或分数。

<details><summary>Original English</summary>
So I would suggest like for you for example like one of the auto research task was what I mentioned before replicating a paper. So of course like there are different level of like complexity there but what we have especially if you think about one specific metric that you want to improve to hill climb as we say in AI terms like we have what is called the goal mode in codeex. So basically a goal mode is basic you have to specify you know what's the target and it's better to have like kind of a target that is like a number a score.
</details>

举一个简单的例子：你拥有这个智能体，拥有这套评估数据集和基准，让它尝试校准提示词以最大化该智能体的性能。在此过程中，智能体紧盯目标，并不断迭代提出新的想法和假设。当然，这算是最简化的一种自动研究模式，但我们今年早些时候公布的一些数学成果，就是使用 Codex 中的目标模式得出的，实际上针对其中一项成果，我们还公开发布了所用的提示词。

<details><summary>Original English</summary>
Uh one example to keep it simple is you know like try you have this agent you have this EVAS data set this benchmark try to calibrate the prompt in order to maximize the performance of the of the agent and what happens there is that the agent looks at the target and then keeps iterating on like new ideas and new hypothesis. Of course, this is kind of like the the kind of like most s simplistic kind of like auto research mode, but like some of the result that we published also like in terms of mathematics early this year were you were created using goal mode in uh in codeex actually for one of those we also published the prompt.
</details>

所以如果你对这个领域感兴趣，阅读我们当时为了证明那个定理——其实是一个猜想，现场若有数学家请见谅——所提供给 Codex 的公开提示词，我认为会是非常非常有趣的内容，因为它向你展示了更多多智能体和子智能体方法的逻辑。

<details><summary>Original English</summary>
So I think like if you're interested in the space reading actually the public prompt that we gave to Codex in order to prove that theorem it was a conjecture uh there is a different sorry for the mathematician in the room. Um I think that's the most interesting like really interesting piece of content because like shows you a little bit more the logic of like this because like multi- aent and sub aent approaches.
</details>

比如特别是在做研究任务时，你可能会用到深度模式（ultra mode），届时你将切实看到智能体会自动利用子智能体在后台并行开展一些独立的研究工作，然后再将它们合并并进行迭代。所以我想说，这两点是进入评估和自动研究非常好的切入点；而且我不想低估它，即便它看似简单，我们实际上正是利用目标模式取得了重大的成果。所以它非常强大。

<details><summary>Original English</summary>
So um like for example like especially when you do research task you're you're probably going to use ultra uh mode then you're going to really see that the agent is going to leverage like the sub agent automatically to actually like run some independent piece of research in parallel then like merge them and iterate. So I would say that you know these are the two really good entry point for evils and auto research and I don't want to understate like even if it's simple like we actually use goal mode to achieve like significant results. So um it's quite powerful.
</details>

>> 是的，我也为目标模式点赞。是的，我认为在半年以前，你还得操心提示词该怎么写，操心如何编排智能体以及所有这些琐事。而现在你后退一步，真正需要思考的是智能体的目标究竟应该是什么。我认为这非常强大，因为模型本身将更有能力自动完成这一切，取代我们过去做的、以及目前仍部分手动在做的事情。因此我非常推崇、也非常赞成目标模式。

<details><summary>Original English</summary>
>> Yeah. Plus one on goal mode. Yeah. I think I think yeah just half a year ago you had to worry about the prompt and you had to worry about how to orchestrate the agents and all this stuff. So now I you move back now you you really have to think about what should the agent do as a goal and I think that's very powerful because I mean the models will be more capable to actually do all that than automatically what we used to do what we do still partially manually and I think I highly recommend plus one on the goal mode
</details>

另外，今天我们基本上展示了 ChatGPT 金融服务插件，但我们的团队——包括我的同事 Dom——真正专注于与金融服务客户或各类金融科技公司合作，推动其在大规模场景下的落地，解决那些棘手难题；我们团队也能在评估中带来许多细致的考量。所以我们随时都在，只是希望确保大家能够在大规模场景中充分利用我们的模型和平台。今天的内容相对简单，但如果大家有任何业务场景，欢迎与我们接洽，我们很乐意与您合作。

<details><summary>Original English</summary>
and also I think today we had chativity financial services plugin basically shown but I think our team really I mean also my colleague Dom we're focusing with financial service customers or any fintech etc to actually implement it at scale and also those difficult problems and there's a lot of nuances in the evaluations that our team brings so we're not going away we just want to make sure you leverage our models and the platform at the scale I mean this was more simpler today but approach us if you have any use cases happy to work with you
</details>

>> 是的，我非常想强调的是，这实际上是一个双向的交流。所以，如果您已经与 OpenAI 建立了合作关系，请联系您的客户总监，我们非常欢迎各种反馈；确保这些技术不仅停留在漂亮的演讲层面，而是能真正在各位的公司落地运行，也是我们职责的一部分。所以，我们随时提供支持。大家还有其他问题吗？好的。

<details><summary>Original English</summary>
>> yeah know I really want to stress the fact that it's kind of like a twod directional conversation. So, you know, if you already have a relationship with OpenAI, please, you know, hit your account director like feedbacks are more than welcome and also it's part of our job really making sure that, you know, it's not just nice presentation, but actually it's going to work at your own companies. So, um that's really like, you know, we are here. But any other question?

Okay.
</details>

### 系统集成与插件回写

>> 我想问一个问题。

<details><summary>Original English</summary>
>> One of the questions I have.
</details>

>> 谢谢。我想问的问题是，在刚才的演示过程中，提到了很多只读类型的能力和插件。我很想了解，就团队接触过的客户或所构建的技能而言，是否有真正向系统或记录系统（system of records）进行回写的用例？

<details><summary>Original English</summary>
>> Thank you. Uh, one of the questions I have is uh during the presentation there was a lot of um uh readonly skills and plugin curious for uh the clients or any skills that you've seen that actually writes back into the system or like system of records that uh the team has been building with.
</details>

>> 问得好。我想 Dom 会有更好的解答。

<details><summary>Original English</summary>
>> That's a good question. I think Dom has a has a even better answer.
</details>

>> 好的。大家好，我到前面来。是的。关于插件架构，以及它们能够且应当如何与更大的系统进行交互，这里面有……

<details><summary>Original English</summary>
>> Yeah. Hey, I'll come up here. Uh, yeah. So, when it comes to plug-in structures, uh, and how they can and should be interacting with larger systems, there's a
</details>

<!-- chunk 12/12 -->

有几种方法可以做到这一点。呃，这也取决于你想构建什么样的东西。所以如果我正在构建一个功能完备的插件扩展，我其实只是把 codex 用作编排系统，但那些工具和进程完全可以存储到远程位置，并与那些系统进行交互。最简单的方法是与本地文件系统交互。所以如果你告诉它，嘿，在这个我正在界定范围的项目里，它可以写回这些进程；或者你给模型下达指令，比如工具的输出是这个，而某个 skill set 的指令是说，嘿，把这个持久化保存在这个位置。呃，你会在 codex 内部看到很多持久化结构。它在处理长上下文方面已经变得非常非常擅长，实际上就是利用其本地文件系统作为那种记录点。话虽如此，一旦你从传统的只读插件或 skill set 转入功能完备的扩展操作，比如我让它去与中央服务器通信，我让它去启动一个数据库，或者至少作为工具的一部分连接到特定数据库。所以比如我们做的很多用例中，我们刚做了一个围绕代理投票的，能够真正去定义你的代理投票系统，它实际拥有什么、发送给什么。就像即使插件所处的接触面是 codex，真正的记录源也是这个通过插件扩展之一连接的应用服务器。它会说，嘿，写出这份报告，写出调查结果，写出日期，写出各种来源，并写回到这个端点的数据库，而那个数据库供给他们的生产应用系统，那个系统是在 codex 之外的。所以从用户角度看，操作系统是 codex；呃，从管理角度和法务审查角度看，操作系统是在 codex 之外。因此扩展和 MCP 允许你灵活决定那些不同的操作系统在哪里，以及记录系统在哪里。呃，你可以要么把那部分卸载给 codex 并保持本地化，要么你可以构建工具，并通过在需要的地方相当轻松地放置 MCP，将这些途径构建到特定的比如 MCP 和 OAuth 相关的权限集中。

<details><summary>Original English</summary>
couple ways to do that. Uh, and it depends on like what you're trying to build. So if I'm building a fullblown like plug-in extension, I'm really just orchestr I'm using the codeex as the orchestration system, but those tools and processes can absolutely store to remote locations and to interact with those systems. The easiest way to do that is to interact with the local file system. So if you tell it, hey, within this project where I'm scoping this out, it can it can write back to these processes or you give it instructions for the model to actually like the output of the tool is this and the output of the or the instruction of a skill set is to say, hey, persist this in this location. Uh you'll see a lot of persistent structuring uh within codeex. It's gotten really really good at handling long context by effectively utilizing its local file system as like that point of record. That being said, once you move from a traditional like readonly plugin or skill set into a full-blown extension oper operation, like I tell it to go talk to the central server, I tell it to go spin up a database or at least connect to the specific database as part of a tool. So like the a lot of the use cases that we do, we just did one around proxy voting, being able to actually go define your proxy voting systems, what it actually had what it sent to. was like even though the plugin in the surface area was codeex the actual source of record was this app server that was connected via one of the plug-in extensions it says hey write this report write the findings write the date write the the sources back to this end of it database and that database feeds the like their production application system which is outside of codeex so operating system from a user perspective is codeex uh operating system from an administration perspective and from the legal review perspective was outside of codeex so the extensions MCPS allow you to be flexible where the those different operating systems are and where the systems record are. Uh and you can either offload that to the codeex and keep things local or you can build the tools and build those avenues into particular like MCP and OOTH related you know permission sets by pretty easily dropping an MCP where you need to.
</details>

是的，我想说那里的另一个常见用途实际上是，特别是当你进行需要被审计的特定产品流程时，就像他提到的代理投票，拥有那种标准化的——就像我们经常构建的——那种标准化的日志，它将允许技术用户不仅理解分析的最终结果，而且能理解每一个决定、每一项是如何做出的。比如这种扩展日志就是我们往往频繁存储的内容，尤其是在像金融服务这样高度监管的行业框架下，能够将每个决定追溯到数据源及其背后的逻辑，在某种程度上是至关重要的。通常例如当我们生成这个工件作为输出时，出于这个原因，作为流程和插件的一部分，我们也会存储完全可审计的日志。

<details><summary>Original English</summary>
Yeah, I would say like another like common use there is really like to especially when you're doing like specific product um processes that needs to be kind of like audited like he was mentioning proxy voting having like kind of like a standardized like what we frequently build like kind of a standardized like logs that will allow like you know a technical user to understand you know not just the end of the analysis but how every decision every like piece of was done that's for example Like this extended log is something that we tend to store frequently and especially you know in a highly regulated framework like um industry like financial services being able to back trace every decision to the data source and the logic behind it was kind of like kind of a crucial and they like usually for example when we produce this artifact as output we also store like logs that are fully auditable for this reason as part of like the process and the plug-in.
</details>

也许最后一个问题。

<details><summary>Original English</summary>
One last question maybe.
</details>

>> 我想我们现在差不多要结束了，或者

<details><summary>Original English</summary>
>> I think we almost at the end now or
</details>

>> 是的，我们还有大约五分钟时间。

<details><summary>Original English</summary>
>> Yeah, we are like five minutes out.
</details>

>> 好的，谢谢大家。感谢大家现在花时间和我们在一起。然后请联系我们，谢谢，祝大家大会过得愉快，谢谢大家的到来。非常感谢大家。

<details><summary>Original English</summary>
>> Yeah, thank you. Thank you for spending time with us now. And then please reach out for us and thanks have a good good uh conference and thanks for coming. Thank you so much guys.
</details>