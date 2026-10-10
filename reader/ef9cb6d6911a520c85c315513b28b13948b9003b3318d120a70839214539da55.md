---
author: How I AI
date: '2026-10-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kz5Cpomk3HA
speaker: How I AI
tags:
  - generative-ui
  - connector-ecosystem
  - enterprise-workflow
  - site-plugins
title: OpenAI 开发者日现场实录：ChatGPT Sites 与连接器生态，从应急指挥看板到生成式 3D 游戏
summary: 在 OpenAI 开发者日（DevDay）特别节目中，How I AI 主持人 Claire Vo 与 Sites 产品负责人 Kat 深度探讨了全新发布的 ChatGPT Sites 及其插件与连接器生态。Kat 演示了内部应急指挥看板、跨团队数据权限隔离、自动化音乐工作流以及通过技能分发的可协作生成式 3D 地牢探索游戏，展现了从个人专属软件到企业生产级基础设施的全新 AI 原生应用形态。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Kat
  - Claire Vo
companies_orgs:
  - OpenAI
products_models:
  - ChatGPT
  - Codex
media_books: []
status: evergreen
---
### 开场引入与 Sites 插件功能概览

**Kat**: 我们今天正式上线了 **Sites**（站点）插件功能。有了这项功能，任何人都可以访问你的站点，并使用与其连接的插件。换句话说，你在该站点上只能查看属于你自己的数据。如果我和我的团队成员共享这个功能，他们在各自的站点上会看到不同的数据吗？所有人访问的是同一个站点，但显示的内容会根据每个团队的角色而有所不同。它就像魔法一样连接起来，完全不需要像 **API 密钥** 这样繁琐复杂的配置。例如，有时候你想用 **ChatGPT** 或 **Codex** 构建一些东西，并认为自己需要 **Notion API** 或 **Slack API**。弄清楚这些神奇的 API 是怎么回事真的很有趣。因为每个人的思考方式都不一样，有时候我想按天或按周查看 **Google Calendar**（谷歌日历），而当我出差时，我又会用不同的方式来组织我的日程。在这些情况下，我会为那一周专门搭建一个站点，出差结束后再将其删除。那么，有哪些有趣的方式可以利用网站的基础设施层面，而这些可能是大多数人根本想不到的呢？

<details>
<summary>Original English</summary>

**Kat**: We launched the site plugin feature today . With this feature, anyone can visit your site and use the connected plugins . In other words, you can only view your own data on that site. If I share this feature with my team members, will they see different data on their respective sites? Everyone views the same site, but the content is displayed differently depending on each team's role . It connects like magic without the need for complex settings like API keys. For example, there are times when you want to build something using ChatGPT or Codex and think you need the Notion API or Slack API . It's really fun figuring out what these magical APIs are. Since everyone thinks differently, there are times when I want to view Google Calendar on a daily or weekly basis , and when I go on business trips, I organize my schedule differently . In those cases, I set up the site for that week, and then delete it again once the business trip is over. What are some interesting ways to leverage the infrastructure aspects of a website that most people might not even think of ?

</details>

**Claire**: 欢迎收看今天在 **OpenAI Developer Day**（开发者日）现场录制的 **How I AI**。今天，与我们在一起的是站点产品负责人 **Kat**。

<details>
<summary>Original English</summary>

**Claire**: Welcome to How I AI at today's OpenAI Developer Day . Today, we are joined by Kat, a website product leader.

</details>

**Kat**: 是的。

<details>
<summary>Original English</summary>

**Kat**: yes .

</details>

**Claire**: 我刚才给 Kat 看了几个我之前搭建的网站，我发现我们使用网站的方式真的非常相似。我非常期待看到这个站点产品到底是什么，以及它是如何在工作中被使用的。让我们先从业务用途开始，然后逐步过渡到那些虽然没那么实用、但更加有趣的应用。

<details>
<summary>Original English</summary>

**Claire**: I showed Kat a few of the websites I made earlier , and I noticed that our way of using websites is really similar . I am really looking forward to seeing what the website is and how it is used in work . Let's start with business uses and gradually move on to less useful but more interesting applications .

</details>

### 深入实战：Decider 团队的应急响应指挥看板

**Kat**: 太棒了。那么，让我给你展示一个我创建的网站。它还有一些其他的用法。这个站点当然非常适合业务用途，但它也可以用于许多其他非常有趣的场景。在 **OpenAI** 内部，我们使用该站点已经有一年多一点的时间了，并且我们在两个月前正式在内部推出，获得了爆炸性的反响。你在今天的开幕主题演讲中看到的所有幻灯片，也全部是用这个站点创建的。你刚才看到的是一个 **ChatGPT** 站点，我们正将其用于各种各样的目的。

我接下来要向你展示的是我们团队——**Decider** 团队使用的应急指挥概览面板。由于这是演示内容，请注意不要过度将其用于索引。我不得不删除了一些内容，因为那些涉及具体的故障事件。虽然内部也有类似的站点，但我专门创建了这个新站点来展示给你。

今天，我们发布了 **Sam Altman** 在主题演讲中提到的插件和站点功能。借助此功能，任何人都可以访问你的站点并使用已连接的插件，同时你只能查看属于你自己的数据。该功能已在企业工作区（**Enterprise Workspace**）中提供。当你登录该站点时，系统会提示你批准连接。我连接了 **Notion**、**Slack** 和我的日历。然后这个程序会检查我的所有数据，并询问我是否要批准所有连接器。

在检查我批准了哪些 Slack 频道时，如果我批准了所有 Site 相关的 Slack 频道（例如 Site 私有频道和 Site 反馈频道），系统就会判定我属于 Site 团队的 Slack。于是系统会显示：“好的，你在 Site 团队，我将向你展示所有与站点相关的内容。”就这样，并将其命名为 **Site Incident Command**（站点应急指挥部）。然后，它会展示在该时间点发生的所有事件的时间线。

我之所以创建这个程序，是因为作为一名产品经理，我花很多时间和团队在一起，但由于开会以及频繁出差，我缺乏时间和他们一起详细审查事件，而且在内心深处，我其实也不想这样做。我不想悄悄跟在后面催问：“这起案件进展如何？”我不想催促他们，我希望他们能够在没有我干预的情况下独立解决问题。

然而，使用这个插件真的很棒，因为你可以对进展一目了然，遵循排障手册（**Runbook**），逐分钟查看正在发生的事情。它还提供了一个时间线，你可以点击每一个条目查看“现在正在发生什么？”，并能看出谁在负责。这个插件还显示了负责该案件的团队成员以及我们使用的所有工具。我将其设置为从 Notion 导入排障手册和应急响应指南等。如果你愿意，你也可以直接在 Notion 中打开手册和指南。这只是我们如何利用插件和站点的一个例子，我们还在以更多样化的方式使用它们。我们使用该平台来管理团队成员的休假离岗日程，同时也利用了音乐共享等有趣的功能。

<details>
<summary>Original English</summary>

**Kat**: great. Then, let me show you a website I created . There are a few other ways to use it. The website is, of course, excellent for business use , but it can also be utilized for many other really fun purposes . At OpenAI, we have been using the website for a little over a year , and we officially launched it two months ago, receiving an explosive response internally. All the slides you saw in today's keynote speech were also created using the website . What you just saw was a chat GPT site. We are using it for various purposes . What I am about to show you is the incident command overview used by our team, the Decider team. Since this is demo content, please be careful not to overuse it for indexing . I had to delete some content because it was incident-related . Although there are similar sites , I created this new site to show you . Today, we released the plugins and site features that Sam mentioned in his keynote speech . With this feature, anyone can access your site and use connected plugins , while you can only view your own data. This feature is available in Enterprise Workspace . When you log in to this site, you will be prompted to approve the connection . I connected Notion, Slack, and my calendar. Then this program examines all my data and asks if I want to approve all connectors . When checking which Slack channels I approve, if I approve all Site Slack channels, such as the Site Private Channel and Site Feedback Channel, I assume that I belong to the Site Team Slack. So, "Okay. You're on the site team . I'll show you all the site-related content ." Say that, and name it Site Incident Command. Then, it displays the timeline of all incidents that occurred at that point in time . The reason I created this program is that, as a product manager, I spend a lot of time with my team , but due to meetings and traveling to various places, I lack the time to examine incidents in detail with them , and I also do not want to. I was quietly watching from behind, asking, "How is this case progressing?" I do n't want to rush you. I want them to solve it on their own without my interference . However, using this plugin is really great because you can grasp your progress at a glance , follow the runbook , and check what is happening minute by minute . It also provides a timeline, and you can click on every item to see "What is happening right now ?" You can tell who is in charge . This plugin also shows the team members in charge of the case and all the tools we use . I have set it up to import runbooks, response guides, etc. from Notion . If you want, you can also open runbooks and guides in Notion. This is just one example of how we utilize plugins and the site , and we are using them in many more diverse ways. We use this platform to manage team members' out-of-office schedules and also utilize fun features such as music sharing.

</details>

**Claire**: 本期节目由 **Merge** 赞助播出。开发 AI 产品很容易，但其他一切都很困难。与团队和客户使用的工具建立连接、让智能体在拥有适当权限的情况下执行任务，并以稳定且经济高效的方式在生产运行环境中维护一切，这些都至关重要。

大多数团队都试图自己解决这些环节。最终，你非但没有专注于真正重要的核心开发，反而陷入了集成、授权配置、路由以及底层基础设施的泥潭中。Merge 是面向生产级 AI 的基础设施层。连接数千种工具，支持智能体在工具内部安全地开展工作，并优化模型路由和成本。你不需要自己构建或拥有这一切。OpenAI、**Dropbox** 和 **Ramp** 都已经在利用 Merge 快速构建 AI。访问 merge.dev/howiai 即可免费开始开发。

<details>
<summary>Original English</summary>

**Claire**: This episode was produced with the sponsorship of Merge. Developing AI products is easy , but everything else is difficult. It is important to connect with the tools used by teams and customers, enable agents to perform tasks with appropriate permissions , and maintain everything in the operating environment in a stable and cost-effective manner . Most teams try to solve these parts themselves. Ultimately, instead of focusing on the truly important development, you end up getting bogged down in integration, authorization settings, routing, and the underlying infrastructure . Merge is an infrastructure layer for production AI. Connect to thousands of tools, support agents to work securely within tools , and optimize model routing and costs . You do not need to build or own all of this yourself . OpenAI, Dropbox , and Ramp are already using Merge to build AI quickly . Visit merge.dev/howiai to start developing for free .

</details>

### 连接器架构解析与跨团队数据权限隔离

**Claire**: 是的，所以我想先暂停一下，向大家解释一下这一点。特别是当 Sites 刚刚推出时，很多人认为：“太好了，现在我终于有一个地方可以存放符合我审美的代码了。”我认为你当时也是这么想的。在大多数情况下，这些代码都是原型或静态资产，比如 HTML 格式的 **PRD**（产品需求文档）或幻灯片。但是，我想向大家展示的是，**连接器**（Connectors）可以用作数据源。就我个人而言，我喜欢在应用程序中使用实时更新的数据。例如，当你想在 ChatGPT 或 Codex 上构建某些东西，而有人说“我需要 Notion API”、“我需要 Slack API”或“我需要 **Snowflake** 数据”时，你只需要问：“我该怎么做？”直接发问即可。我喜欢弄清楚像这样具有魔法般的指令：我该怎么做？

<details>
<summary>Original English</summary>

**Claire**: Yes, so I would like to pause for a moment and explain it to you . Especially when Sites first came out, many people thought, " Great, now I have a place to put code that captures my sensibility ." I think that is what you thought . And in most cases, that code was a prototype or a static asset, such as an HTML PRD or a slide. However, what I want to show you is that connectors can be used as data sources . Personally, I like using data that is updated in real time in the app . For example, when you are trying to build something on ChatGPT or the Codex and someone says, " I need the Notion API," " I need the Slack API," or " I need Snowflake data," you just ask, " How can I do that?" You can just ask . I like figuring out magical commands like this. What should I do?

</details>

**Kat**: 是的。

<details>
<summary>Original English</summary>

**Kat**: yes .

</details>

**Claire**: 我可以在站点上使用连接器吗？我该如何实现这一点？这种情况就会发生。

<details>
<summary>Original English</summary>

**Claire**: Can I use the connector on the site ? How can I do this? This can happen.

</details>

**Kat**: Sites 和 Codex 的优势恰恰就在这里。开发 Sites 的初衷之一，就是我们需要一个空间将软件保存在某个地方。Sites 负责处理所有的部署工作，并通过与 Codex 集成来构建整个站点。Codex 令人惊叹的地方在于它能准确把握用户的意图。我们会深入分析用户请求以理解其深层含义。例如，如果你说：“请创建一个可以导入 Notion 文档并将其与日历进行交叉引用的网站”，Codex 就会判定最好使用连接器。特别是如果你说：“我正在构建一个用于团队协作的网站”，它可能会问：“你想使用插件连接器吗？”你可以提出这样的问题，或者在网站构建完成后，展示工作流程并请求反馈。或者，你可以采用“自带连接器”（**Bring Your Own Connector**）的方式。例如，我可以使用插件来构建站点吗？

<details>
<summary>Original English</summary>

**Kat**: The advantage of Sites and Codex lies right here. One of the reasons for developing Sites is that we needed a space to store software somewhere . Sites handles all deployments and builds the entire site by integrating with the Codex . The amazing thing about Codex is that it accurately grasps the user's intent . We deeply analyze user requests to understand their meaning . For example, if you say, "Please create a website that can import Notion documents and cross-reference them with a calendar, " Codex determines that it is better to use a connector. In particular, if you say, "I am building a website for team collaboration, " would it ask, " Would you like to use the Plugin Connector?" You can ask questions like this, or after building the website, show the work process and request feedback. Alternatively, you can use the method of "bring your own connector ." For example, can I build a site using plugins?

</details>

**Claire**: 在共享此功能时，我想确认一下我的理解是否正确。如果我将其分享给整个团队，其他团队成员会继承各自团队的连接器并看到与我不同的数据吗？

<details>
<summary>Original English</summary>

**Claire**: And when sharing this feature, I want to check if I understand it correctly. If I share it with the entire team, will other team members inherit their respective team's connectors and see different data than I do ?

</details>

**Kat**: 是的，每个团队都会看到不同的数据。例如，如果你与你的 Site 团队成员共享此应急指挥面板，你们会看到类似的内容。但是，如果你与 OpenAI 的其他团队共享，你看到的内容将取决于你所属的团队。根据不同的团队（例如 Codex 团队或 Identity 团队），系统会显示专门针对该团队的数据。

<details>
<summary>Original English</summary>

**Kat**: Yes, each team will see different data. For example, if you share this incident command with your site team members, you will see similar content. However, if you share with other OpenAI teams , you will see different content depending on the team you belong to . Depending on the team, such as the Codex team or the ID team, data specialized for that team is displayed.

</details>

**Claire**: 这对于连接到数据仓库的数据团队或财务团队来说似乎特别有用。在处理敏感数据时，承担不同角色和职责的人非常喜欢这个工具。这是因为访问站点的用户直接在自己的权限范围内检索数据。它连接得非常迅速，就像魔法一样，完全不需要复杂的 API 密钥设置。

<details>
<summary>Original English</summary>

**Claire**: It seems like it would be particularly useful for data teams or finance teams connecting to a data warehouse. People with various roles and responsibilities really like this tool when handling sensitive data . This is because users visiting the site directly retrieve data within that range. It connects instantly, like magic, without complex settings like API keys.

</details>

**Claire**: 你通常使用哪些连接器来构建应用？

<details>
<summary>Original English</summary>

**Claire**: Which connectors do you usually use to build something ?

</details>

**Kat**: 嗯，我通常只是访问协作站点或团队协作空间。我经常使用 **Slack**、**Notion**、**Google Drive**、**Google Calendar** 等。目前该工具中集成了大约 60 个连接器，我们还在不断添加更多。我目前正在审核并改进我愿望清单上的几个连接器。

<details>
<summary>Original English</summary>

**Kat**: Well, I simply access a collaboration site or team collaboration space . I use Slack, Notion, Google Drive, Google Calendar, etc. a lot. There are currently about 60 connectors integrated into the tool, and we are continuously adding more . I am reviewing and improving a few connectors on my wish list .

</details>

**Claire**: 你是自己创建这些连接器并将它们当作小型微应用（**Micro-apps**）来使用，还是用它们来替换现有的连接器？

<details>
<summary>Original English</summary>

**Claire**: Do you create these connectors yourself and use them like small micro-apps , or do you use them to replace existing connectors?

</details>

**Kat**: 两者皆有。随着我与越来越多的人交流，我看到了非常多元化的光谱。有些人创建小型原型仅仅为了发布给自己使用的简单功能，或者开发高度个性化的软件。你可以利用“属于你自己的插件”或“属于你自己的连接器”，这一事实正好能让你自由调整它们，以契合你的思维模式和团队的工作风格。完全没有必要受制于死板僵化的框架。

由于 Sites 是一个基于 Web 的平台，它可以以任何方式进行调整。随着团队规模的扩大，你可以添加和更新功能，以适应不断变化的情况。因此，也有人利用 Sites 来构建自己的专属工具并开展深入开发。Sites 默认提供 **OneData**，支持 **R2 存储桶**，并允许部署所有功能。它实际上拥有非常丰富的功能，包括协同编辑功能。

<details>
<summary>Original English</summary>

**Kat**: Yes, it is both . As I talk to more people , I can see a truly diverse spectrum . Some people create small prototypes to release simple features just for themselves, or develop personalized software . The fact that you can utilize 'your own plugins' or 'your own connectors' is precisely what allows you to freely adjust them to fit your mindset and your team's work style . There is no need to be bound by a rigid mold. Since Sites is a web-based platform, it can be adjusted in any way . As the team grows , you can add and update features to adapt to changing circumstances . Therefore, there are also people who utilize Sites to build their own tools and proceed with in-depth development. Sites provide OneData by default, support R2 buckets , and allow deployment of all features. It actually has a wide variety of features, including a collaborative editing function .

</details>

**Claire**: 是的，我觉得能考虑到我的大脑运作方式与其他人不同这一点真的很酷。例如，我可能想以不同的方式查看一天或一周的 Google Calendar，或者当我出差时，我想把所有事情都安排得完全不同。因此，我会创建该周所需的站点，周末一到就将它们删除。这真的非常方便。

<details>
<summary>Original English</summary>

**Claire**: Yes, I think it's cool that I can consider the fact that my brain works differently from other people's. For example, I might want to view my Google Calendar for a day or a week in a different way , or I might want to organize everything differently when I go on a business trip . So, I create the sites needed for that week , and delete them when the weekend comes . It's really convenient .

</details>

### Sites 作为开发基础设施与 MCP 插件托管

**Claire**: 让我们简要谈谈将 Sites 作为基础设施来使用。你刚才简要提到了 Sites 的组成部分。虽然创建网站本身很棒，但有哪些有趣的方式可以利用站点在基础设施层面的能力，而这些是大多数人根本想不到的？

<details>
<summary>Original English</summary>

**Claire**: Let me briefly talk about using Sites as infrastructure . You just briefly mentioned the components of Sites . While creating websites is great, what are some interesting ways to utilize the infrastructural aspects of sites that most people wouldn't even think of ?

</details>

**Kat**: Sites 的出色之处在于它旨在存储使用 Codex 构建的软件。因此，当我们以前使用 Codex 构建网站时，曾遇到一个问题：在 Codex 构建的文件保存到本地之后，用户必须手动执行 **DevOps** 部署任务。所以我们想：“好的，那么我们将负责这部分工作，接管从本地机器提取文件并保存到某处的最后一步。”我后来发现，人们不仅将 Sites 用于构建网站，还将其用于插件开发、数据托管和运行试用。这是因为 Sites 是一个非常强大的基础设施工具。因此，今天我们宣布支持通过 Sites 托管 **MCP**（Model Context Protocol）插件，并使其可在网站上直接使用。随着 Sites 不仅可以作为网站构建工具，还可以作为基础设施来使用，我们预计将形成一种良性循环。

<details>
<summary>Original English</summary>

**Kat**: The great thing about Sites is that it is designed to store software built with the Codex . So, when we built a website using Codex , there was a problem where users had to perform DevOps tasks manually after the files built by Codex were saved locally . So we thought, "Okay, then we will handle that part and take care of the final step of fetching the file from the local machine and saving it somewhere ." And I found out that people are using Sites not only for building websites but also for plugin development, data hosting, and running trials. This is because Sites is a really powerful tool . So today we announced that we support hosting the MCP plugin through Sites and making it available for use on websites. As Sites becomes available not only as a website building tool but also as an infrastructure, we expect a kind of virtuous cycle to be formed.

</details>

### 个人定制化软件：利用 Reddit 自动化与 Spotify 打造工作流

**Claire**: 太棒了。到目前为止，我们已经深入讨论了事件应急管理、基础设施和工作生产力，现在让我们转向我们俩都面临的一个共同痛点：因为孩子，我们的推荐算法完全乱套了。如果你拥有一个完美整洁的 **Spotify** 播放列表，或者干净的 Hulu/Netflix 观看列表，我真的会非常羡慕。然而，我们根本做不到这一点。所以，你能和我讲讲你的 Spotify 被其他家庭成员接管的情况吗？

<details>
<summary>Original English</summary>

**Claire**: great. So far, I have talked at length about incident management, infrastructure, and work productivity, but now let's move on to the problem we are both facing: the issue that algorithms have become a mess because of the children . I'm really envious if you have a perfect and neat Spotify playlist or a Hulu or Netflix watchlist . However, we cannot do that. So, could you tell me about a situation where your Spotify was taken over by another family member?

</details>

**Kat**: 好的，没问题。我的 Spotify 完全被孩子们霸占了。当然，里面偶尔会有迈克尔·杰克逊的歌，但大部分都是 **Bluey**（布鲁伊）和《芝麻街》。所以我创建了一个收集孩子们听的音乐的网站。我想让这个网站对移动端友好，为了实现这一点，我写了几个 Markdown 文件，并告知站点操作人员我偏好的构建方式。目标是打造一个适配手机的移动网站。我希望这个应用使用起来非常非常简单。

而且我想通过浏览 Reddit 上的热门播放列表，了解现在流行什么音乐、大家都在给什么歌曲投票，从而发现新音乐。事实上，我真的很不擅长跟上音乐潮流。我工作很忙，是两个孩子的母亲，还参与了幼儿园家长教师协会（PTA），所以我的生活非常忙碌琐碎。但我真的很喜欢在工作时听音乐。因此，我查看了人们在 Reddit 上分享的音乐类型，并添加了自动化功能。我将它设置为每周一早上 8 点自动运行，为我生成专属播放列表。播放列表看起来就像这样。我们放一下听听看？所以，这是在 Spotify 上运行的，我也从 Spotify 获取音乐。

嗯，我不知道你能不能听清。这也是我第一次听到这首歌。因为它是昨天刚添加进来的，我很高兴整整一周都能听这首歌。它绝对不是 Bluey，绝对不是 Bluey。

<details>
<summary>Original English</summary>

**Kat**: Yes, that's good. My Spotify is taken over by kids. Of course, there are Michael Jackson songs, but most of them are Blue and Sesame Street. So I created a website that collects music children listen to . I wanted to make this website mobile-friendly , so to achieve this, I wrote several MD files and informed the site operators of my preferred approach. The goal was to create a mobile-friendly website . I wanted this app to be very, very easy to use . And I wanted to look through Reddit's popular playlists to find out what music is popular and what people are voting for, so that I could discover new music . Actually, I'm really bad at keeping up with music trends . I am busy with work, a mother of two , and also involved in the kindergarten parent-teacher association, so I am very hectic . But I really like listening to music while working. So I looked at what kind of music people share on Reddit and added an automation feature. I set it to run every Monday morning at 8 a.m. to create a playlist for me . The playlist looks like this. Shall we play it? So, this is running on Spotify. I also get music from Spotify . Hmm, I'm not sure if you can hear me clearly. This is my first time hearing this song. Since it was added yesterday, I'm glad I can listen to it all week. It's definitely not Blue. It's definitely not Blue.

</details>

**Claire**: 啊，我都不知道 Spotify 原来可以作为一个插件来使用！我可以搜索它的曲库并在我想要的自定义界面中播放吗？它是这样运作的吗？

<details>
<summary>Original English</summary>

**Claire**: Ah, I didn't know Spotify could be used as a plugin . Can I search the catalog and play it in my desired custom interface ? Does it work that way?

</details>

**Kat**: 是的，没错。我目前直接将 Spotify 用作播放器。我为工作笔记本重新制作了这个应用，但我也把它安装在家里电脑上使用。运行它需要占用一定的计算机资源，所以你必须开着笔记本电脑来运行它，但那没关系，反正我工作时本来就一直开着电脑。我把 Spotify 当作音乐播放器应用，不过你也可以将它与 **Apple Music** 结合使用。

<details>
<summary>Original English</summary>

**Kat**: yes . yes. I am currently using Spotify as a player . I remade this for my work laptop, but I've also installed it on my home laptop and am using it. You need to use computer resources to run it. So you have to turn on the laptop to run it, but that's okay. Since I use it while working anyway. I use Spotify as my music player app. However, you can also use it in conjunction with Apple Music .

</details>

**Claire**: 我的电脑里存了大量的音乐。所以，请根据 Apple Music 为我生成一个播放列表。每个星期一运行。

<details>
<summary>Original English</summary>

**Claire**: I have a lot of music on my computer . So, please create a playlist based on Apple Music . Every Monday.

</details>

**Kat**: 每个星期一。

<details>
<summary>Original English</summary>

**Kat**: Every Monday.

</details>

**Claire**: 还有没有其他实用的集成应用是大家可能想要了解的？你最喜欢这一个吗？

<details>
<summary>Original English</summary>

**Claire**: Are there any other useful integration apps that people might want to check out? Do you like this the best?

</details>

**Kat**: 嗯……我得看一下列表。嗯……Gmail、日历……

<details>
<summary>Original English</summary>

**Kat**: well. I'll have to check the list. Hmm, hmm... Gmail Calendar.

</details>

**Claire**: 啊，我似乎显得有点古怪了。“不，我只需要一个在工作时听的播放列表。”你似乎是这么想的。

<details>
<summary>Original English</summary>

**Claire**: Ah, I seem a bit eccentric. " No, I just need a playlist to listen to while doing work ." It seems like that is what you think.

</details>

**Kat**: 是的，没错。

<details>
<summary>Original English</summary>

**Kat**: yes that's right.

</details>

**Claire**: 好吧，我不太确定。今天是开发者日，所以我连续工作了 24 个小时。嗯，稍后我们再去寻找其他点子并搭建站点。首先，我想向大家展示一个你和我共同创建的游戏和网站的例子，然后聊聊我们截然不同的实现思路。在今天的开发者日上，大家似乎都在热烈讨论像 **Astra** 这样的模型在制作 3D 游戏或各类游戏方面有多么出色。在我看来，该模型最大的优势有两点：第一，它能够以极快的速度产出高质量的结果；第二，网站创造了一个可以与他人分享想法并进行协作的空间。然而，人们在思考游戏可以是什么样子、以及如何利用 Coda 和网站的各种概念来创造酷炫事物方面，思维似乎还不够开阔。所以，请向我展示你的游戏，我也会解释我是如何构思我的游戏的。

<details>
<summary>Original English</summary>

**Claire**: All right. I'm not sure . Today is Developer Day, so I worked 24 hours straight . Hmm, let's look for other ideas later and build a site. First, I would like to show you an example of a game and a website that you and I created together , and then talk about our different approaches . It seems like there is a lot of talk at today's Developer Day about how good models like Astra are for making 3D games or various kinds of games . In my opinion, the biggest advantages of this model are two things. First, it is the ability to produce high-quality results very quickly . Second, the website has created a space where you can share ideas and collaborate with others . However, it seems people are n't thinking creatively enough about what games could look like and how they can create cool things by utilizing the various concepts of Coda and the website . So, please show me your game and I will explain how I approached it .

</details>

### 生成式 3D 游戏开发：通过技能分发地牢与实时推理

**Kat**: 我创建这个站点已经有一段时间了。我想向你展示该站点的强大功能，同时也想向你展示人们是如何分享这个站点的。我注意到最近大家经常在分享网站。我做好了这个，现在有了一个可以上传的地方，人们可以分享他们创造的内容，而且它也有一个专属 URL。所以，我想通过这种方式将社区连接起来。我对这部分非常好奇，而且我仍在尝试各种不同的想法。我认为稍后分享出来，看看大家如何利用它会很有趣。

嗯，总之，我做的是迄今为止发布的最大规模的用户生成地牢探索游戏。你可以进入游戏畅玩，还可以选择你想要的角色。你也可以选择 Codex 宠物，或者创造属于你自己的宠物。

<details>
<summary>Original English</summary>

**Kat**: It has been a while since I created this site. I wanted to show you the powerful features of the site, and I also wanted to show you a little bit of how people share the site . I've noticed that people share websites a lot these days . I made this . Now there is a place to upload it , and people can share what they have created . There is a URL, too. So, I wanted to connect the community in this way . I am very curious about this part, and I am still trying out various things . I think it will be fun to share this later and see how people utilize it . Um, anyway , what I made is the largest user- created dungeon exploration game released so far. You can enter the game and play, and you can choose the character you want . You can also choose Codex pets, or create your own .

</details>

**Claire**: 哦，我们可以在这里添加像素艺术（**Pixel Art**）吗？

<details>
<summary>Original English</summary>

**Claire**: Oh, can we add pixel art here ?

</details>

**Kat**: 我会添加一个像素艺术集成功能。

<details>
<summary>Original English</summary>

**Kat**: I will add a pixel art integration feature.

</details>

**Claire**: 好的，非常感谢！

<details>
<summary>Original English</summary>

**Claire**: Okay, thank you.

</details>

**Kat**: 你进入地牢，四处漫游，斩杀像泰迪熊之类的怪物。我玩这个游戏真的很菜，所以我很快就被吃掉了。我想我应该叫 Astra 陪我一起玩。必须得这样，我真的必须找帮手了。好的，所以我做的是——这里是阿拉莫广场（**Alamo Square**），就在这里，这是彩绘女士（**Painted Ladies**）。你看到彩绘女士了吧？我要阵亡了。

嗯，我所做的是允许人们创建属于他们自己的房间。因此，我在这里放置了使用名为 **Dungeon Site** 技能的操作说明。我可以分发它，人们也可以直接进去玩，不过我会快速演示一下如何使用它。你只需要设置一个地牢，并添加 Dungeon Site 技能。基本上，Dungeon Site 技能指定了房间大小、玩家位置等等要素。你还可以输入控制指令。然后，利用 Astra，你可以指定任何你想要的内容，比如你想置身于月球表面，或者火山内部。

嗯，我今天早上做的是……我儿子正在看《怪奇物语》（**Stranger Things**）动画。于是我做了一个《怪奇物语》主题的地牢房间。呃，我全部搞定了，这是《怪奇物语》地牢房间里最长的一个房间。空心月球（Hollow Moon），我也做了类似的东西。所有这些都是我自己想出来的。好了，我们实际进去玩一下吧？

<details>
<summary>Original English</summary>

**Kat**: You go into the dungeon, wander around, and kill things like teddy bears . I am really bad at this game . So I get eaten quickly . I guess I should ask Astra to play with me . That. I have to. I really have to. Okay. So, what I did is, this is Alamo Square. Um, right here is the Painted Ladies You see the Painted Ladies, right? I'm going to die now. Um, what I did was allow people to create their own rooms . So, I put the instructions for using a skill called Dungeon Site here. I can distribute it, or people can go and play it, but I'll give you a quick demonstration of how to use it. You just need to set up a dungeon and add the Dungeon Site skill . Basically, the Dungeon Site skill specifies the room size, player position, and things like that . You can also input controls. Then, using Astra, you can specify whatever you want, like wanting to be on the moon's surface or inside a volcano . Um, what I did this morning... my son was watching. Uh, um , the Straanger Things animation. So, I made a Straanger Things-themed dungeon room. Uh, I pulled it all off. It's the longest room among the Straanger Things dungeon rooms . Hollow Moon I also made things like that. I came up with all of this myself . Alright, shall we actually go in and play?

</details>

**Claire**: 在加载的时候我问你一个问题。你是将这个添加到现有游戏中，还是在创建一个全新的游戏？

<details>
<summary>Original English</summary>

**Claire**: Let me ask you a question while it loads. Are you adding this to an existing game , or are you creating a new game?

</details>

**Kat**: 不，我是在创建一个新房间。我创建这个功能的主要初衷是让人们分享属于他们自己的房间。然后我可以把它添加到我的地牢房间里。我把它做成了纯本地模式。然后系统询问我是否要创建一个通往另一个地牢的开放房间。呃，我拒绝了，并让他们结束游戏。我想把它用于演示。呃，但那是技能中的一个功能，所以你会遇到类似的问题。你想做这个吗？“嗯，这是可能会继续做下去、也可能不会做下去的事情吗？”我的意图是给这个古老的地牢探索游戏增添这种体验：大家分享自己的房间，一起玩，互相交流，感叹‘这太好玩了’。我很好奇是否还有其他人有兴趣像我一样进行构建。

<details>
<summary>Original English</summary>

**Kat**: No, I am creating a new room . My main intention in creating this feature is for people to share their own rooms . Then I could add it to my dungeon room. I made it local-only. And then they asked if I wanted to create an open room leading to another dungeon . Uh, I said no and told them to end the game . I wanted to use it for a demo. Uh, but that is a feature in the skills . So you will get questions like that. Would you like to make this? "Hmm, is this something that might continue or might not ? My intention is to add that kind of experience to the oldest dungeon exploration game, where people share their rooms, play together, talk to each other, and say, 'This is really fun.' I'm curious if there are others interested in building like me.

</details>

**Claire**: 看来你很有野心。我听说你今天打算开一场直播。我会在 Twitter 上发布链接。一旦直播开始，我认为这真的非常有趣——这是一种分发游戏使用技能的新途径。我以前从未听说过这样的用户体验。说‘你可以进入这个游戏去建造一些东西’，与说‘如果你下载了这个技能，Codex 就会自动把它构建到游戏中’是完全不同的。

我认为可能有很多人像我一样，在一个窗口中保持打开 Codex 浏览器并持续使用，就像你在另一个窗口中通过 Kodak 使用应用程序一样。因此，我认为这种分发与应用程序交互所需技能的模式非常有趣，无论它是否用于游戏。

<details>
<summary>Original English</summary>

**Claire**: It seems like you have ambitions. I heard you're starting a live stream today . I'll post the link on Twitter. Once the live stream starts, I think this is really interesting—it's a method of distributing skills for game usage . I've never heard of a user experience like this before. Saying, 'You can go into this game and build something,' is completely different from saying, 'If you download this skill, the Codex will automatically build it into the game.' I think there are probably many people like me who keep the Codex browser open in one window and use it continuously, just like how you use an app through Kodak in another window. So, I think this model of distributing the skills needed to interact with an app is quite interesting, whether it's for a game or not .

</details>

**Claire**: 我好奇的另一件事是，例如，如果我们这样做，这间屋子里的 20 个人每个人都添加一个房间。我们如何知道人们是否真的在使用它？我们如何确定人们是否真的在向站点添加内容？你是否在考虑数据分析（**Analytics**）层面？

<details>
<summary>Original English</summary>

**Claire**: Another thing I'm curious about is, for example, if we do this, the 20 or so people in this room each have their own Let's assume we add a room. How can we know if people are actually using it ? How can we determine if people are actually adding content to the site ? Are you considering the analytics aspect?

</details>

**Kat**: 不，作为一名应用开发者，我没有这类信息。我只能使用基础的分析工具，基本上就只有访问量和流量统计。在未来，我计划大幅增强分析能力，以检测和调查激增的流量，并实现更主动的分析。然而，作为开发者，我并不知道是谁在创造和使用这项技术。

所以……我所期待的是利用 Twitter 通过标签进行分享。例如：“大家好，我正在做类似这样的东西。”我就是这么说的。就像在推荐酷炫网站时一样。“你喜欢酷网站使用这种方式吗？”这就是我要问的。如果你在社交平台上提到我或艾特我，我就会自然增长。我不确定，但我喜欢自然形成的社区。我不认为社区需要以强行追求通用人工智能（AGI）的方式来构建，我只想和大家面对面接触。虽然我可能有点老派。

<details>
<summary>Original English</summary>

**Kat**: No, as an app developer, I don't have that kind of information. I can only use basic analytics tools . Basically, just visit counts and traffic. In the future, I plan to significantly enhance analytics capabilities to detect and investigate surging traffic and enable more proactive analysis . However, as a developer, I don't know who is creating and using this technology . So... what I'm hoping for is to use Twitter to share via hashtags. For example , "Hello, I'm making something like this." That's what I'm saying. Just like when introducing cool websites. Do you like that cool websites use this method ? "That's what I'm asking . And if you mention or tag me, I grow naturally. I'm not sure, but I like a natural community. I don't think a community needs to be formed in an Artificial Intelligence (AGI) way . I just want to meet people in person. I might be a bit old-fashioned, though.

</details>

**Claire**: 随着 AI 采用率的提高，企业的安全风险和合规要求也随之增加。新的合规框架、审计项目和供应商不断涌现，但团队规模并没有随之扩大。大多数合规工具都承诺实现自动化，但实际上，你仍然必须手动处理一切——寻找屏幕截图、验证控制措施，并在审计季临近时手忙脚乱地补救。**Vanta** 则截然不同。他们的智能体方法——Vanta 值得信赖的平台——旨在与你共同成长，而不是阻碍你的发展。

凭借 400 多个集成和 1,400 多个自动化测试，Vanta 全年收集证据并监控安全控制，将审计准备时间缩短了 82%。此外，你可以从任何地方访问 Vanta 智能体。无论你的团队成员每天使用 Vanta，还是使用 Claude，或者使用像 Cursor 这样的工具，都没有问题。你需要证明吗？超过 16,000 家快速增长的公司，如 Ramp、**Writer** 和 **Harvey**，都在通过 Vanta 快速扩张，同时节省大量时间和资源。收听本节目的听众访问 vanta.com/howiai 即可享受 1,000 美元的专属折扣。请访问 vanta.com/howiai 领取你的 1,000 美元优惠。

<details>
<summary>Original English</summary>

**Claire**: As AI adoption increases, so do corporate security risks and requirements. New frameworks, audits, and vendors keep multiplying, but team sizes are n't growing. Most compliance tools promise automation , but in reality, you still have to handle everything manually—finding screenshots, verifying controls, and catching up late when audit season approaches. Vanta is different . Their agent approach— Vanta's trusted platform—is designed to grow with you, not hinder your growth . With over 400 integrations and more than 1,400 automated tests, Vanta collects evidence and monitors controls year-round, reducing audit readiness time by 82% . Plus, you can access Vanta agents from anywhere . Whether your team members use Vanta every day, or Claude or It doesn't matter if you use other tools like Cursor. Do you need proof? Over 16,000 fast-growing companies, such as Ramp, Writer, and Harvey, are growing rapidly while saving time and resources through Vanta . If you are listening to my broadcast, you can get a $1,000 discount by visiting vanta.com/howiai . Get your $1,000 discount at vanta.com/howiai.

</details>

**Claire**: 噢，我也应该谈谈我制作的那款游戏。你们公布了 **UltraFast**，而我很幸运地获得了提前测试的机会。真正酷炫的是，我制作了一款与 UltraFast 非常相似的 3D 游戏。那是一个 2x3 的游戏，一个 3D 房间游戏。游戏是在一艘月球飞船内部进行的，里面住着三个非常可爱的 3D 角色：**Pip**、Astra 以及另一个 Astra。我不太记得名字了，但我肯定记得 Pip。每个人都有自己的房间，预测未来的功能真的很酷。

比如输入：“我输了。例如，Pip 需要一张双层床。”如果你输入这句话，Astra 就会以超高速做出双层床。还有：“秋天来到了 Momo 的花园。”如果你输入这句，树叶就会飘落；“春天来到了 Momo 的花园”，花儿就会盛开；“让我们进入水中”，一只巨大的水母就会出现；“让我们消除重力”，如果你输入这个，又会有一只水母出现。就像这样，一切都开始浮现在脑海中。所以我认为我们真的快要实现了。你不仅可以创建 3D 游戏（你做得很棒，去试试吧），分发它们（你已经搞定了，对吧），甚至还能将它们无缝集成。速度极快，真的太快了。

我大概花了一千美元，我觉得这真是一种浪费。孩子们吵着说：“请把水母变成草裙舞舞者吧！请让它像小水母一样跳芭蕾舞！也请做一只小鸡！”他们就是这么提要求的。所以我想：‘孩子们，我们纯粹是在烧钱。’我就是这么说的。它的速度快了 8 倍，但正如 Sam Altman 所说，成本也贵了 6 倍。不过，随着这些模型变得越来越聪明、越来越快，想象一下生成式 UI（**Generative UI**）会是什么样子——不再像当前 SaaS 模式那样以枯燥乏味的方式按部就班弹出表单或小组件。我认为游戏的生成式 UI 将会非常有趣，它会变得超级酷。

<details>
<summary>Original English</summary>

**Claire**: Oh, and I should talk about the game I made. You announced UltraFast , and I got the opportunity to test it a little early . The really cool thing is that I made a 3D game that is very similar to UltraFast. It is a 2x3 game. There was a 3D room game. It was a game played inside a lunar spacecraft, and three very cute 3D characters lived there: Pip, Astra, and another Astra . I don't remember the names well, but I definitely remember Pip . Each had their own room, and the feature to predict the future was really cool. "I lost. For example, Pip needs a bunk bed." " If you type that, Astra will make a bunk bed at super high speed. Also, autumn has come to Momo's garden." "If you type that, the leaves fall , and spring has come to Momo's garden." "If you type '...', flowers bloom, and let's go into the water." "If you type '... " a giant jellyfish appears, and let's remove gravity. It was like this: if you typed "...", another jellyfish would appear . Then, everything starts to come to mind. So I think we are really almost there. Not only can you create 3D games ( you made quite well, so give it a try ), distribute them (you've already taken care of that, right), and even integrate them. Really fast, really fast. I spent something like a thousand dollars, and I thought it was a real waste. The children said, " Please make the jellyfish into a hula dancer." Please let me dance ballet like a baby jellyfish . Please make chicken too. That's what they said . So I thought, 'Guys, we're just wasting money .' That's what I said. It's 8 times faster, but as Sam said, it's 6 times more expensive. Well, but as these models become increasingly smarter and faster , imagine what generative UI will look like—in a somewhat tedious way, like the current SAS method, where forms proceed as desired or widgets appear . I think the game's generative UI will be really interesting . It's going to be pretty cool .

</details>

**Kat**: 太酷了。你正在暗示一些非常深刻有趣的事情。我很喜欢你说话的方式，就像当孩子们提出要求时，你爽快地说：“好的，那我们马上把它做出来。”你是在本地开发这款游戏的，对吧？

<details>
<summary>Original English</summary>

**Kat**: That's cool. You are hinting at something really interesting . I liked the way you spoke, as if saying, "Okay, then let's make it," when children asked for something . You developed this game locally, right ?

</details>

**Claire**: 在本地开发的。

<details>
<summary>Original English</summary>

**Claire**: Locally.

</details>

**Kat**: 我们在站点上正在试验的功能之一，就是将推理结果直接引入站点本身的功能。

<details>
<summary>Original English</summary>

**Kat**: One of the things we are experimenting with on the site is a feature to bring inference results into the site itself.

</details>

**Claire**: 是的，这正是我想问的！

<details>
<summary>Original English</summary>

**Claire**: Yes, that is exactly what I was going to ask .

</details>

**Kat**: 是的。它允许你直接向 ChatGPT 发出请求。我们之所以打造这个功能，是为了让你能够进入设计模式并向 ChatGPT 请求各种任务。我们目前也在试验这个站点小组件。因为目前它是一个非常简单的功能，例如你可以说：“你正看着我调试，因为这个功能运行不正常，对吧？”你可以在这里操作，然后我们再返回 ChatGPT。

<details>
<summary>Original English</summary>

**Kat**: yes . And it allows you to make requests to ChatGPT . The reason we are creating this is to allow you to enter a design mode and request various tasks from ChatGPT . We are also currently experimenting with this site widget . Since it is a very simple function right now, for example, "You are watching me debug because this function is n't working properly, right ?" "You could say that. You can do that here. Then we are returning to ChatGPT .

</details>

**Claire**: 是的。我们正在通过将推理功能集成到站点中，研究融合用户推理的方法。我认为，如果想玩游戏的人可以直接呈现他们自己的推理，那将会非常有趣。例如，想象一下给孩子们零花钱让他们在游戏中尽情购买想要的东西，孩子们可以直接提出要求，比如‘请给我一张双层床’，或者‘请给我一张能变成章鱼的床’。他们可以进行这样的对话。

<details>
<summary>Original English</summary>

**Claire**: Yes. We are researching ways to incorporate user reasoning by integrating reasoning features into the site . I think it would be really interesting if people who want to play games could directly present their own reasoning . For example, imagine giving children allowance to buy as much as they can for games , and the children directly request things like, 'Please give me a bunk bed,' or 'Please give me a bed that turns into an octopus.' They could have conversations like that.

</details>

**Kat**: 不过你可能还没有完全理解我的意图。假设有孩子，但他们已经有了零花钱。妈妈的 Kodak 订阅费会被消耗多少呢？嗯，我们将采用一个 500 分钟的套餐方案。这就像一个家庭套餐，是所有家庭成员都可以使用的通话时间配额。是的，针对 Kodak。

<details>
<summary>Original English</summary>

**Kat**: You probably don't understand my intention yet, though. Let's say there are children, but they already have allowance. How much of Mom's Kodak subscription fee could be spent? Hmm, we are going to use a 500-minute plan . It's like a family plan . It is call time that all family members can use. Yes, for Kodak.

</details>

**Claire**: 是的，我认为引入推理功能将会非常有趣。实时的。是的，那绝对会非常吸引人。

<details>
<summary>Original English</summary>

**Claire**: Yes, I think introducing reasoning features would be really interesting. In real-time . Yes, it will be really interesting.

</details>

**Kat**: 作为一名开发者，我从两个角度来看待它：我是能将我所想象的东西带给全世界，还是能为公司将其落地实现。这真的……太有趣了。基础设施的要求将会不断增加。你必须非常谨慎地选择是支持 Insights，还是部署到云端并由自己管理底层基础设施。这是一个极其有趣的部分。另一个好玩的方面是能够创造性地实现以前无法制作的事物。我投身技术领域就是因为我想成为一名游戏开发者。我的梦想曾是成为一名设计师。

我记得一篇非常可爱的报纸报道。我朋友的母亲在当地一家报纸工作，过去常常采访我们所有人来写专栏。我当时 13 岁，我想成为一名游戏开发者。我意识到，真正将好点子变成现实需要巨大的技术能力和创造力。在过去三到六个月中，开发新模型最有趣的部分就是能够真正创造出我想制作的好玩事物。

我制作的项目之一是一个实时素描应用，你在画布上涂鸦，Astra 会在上面进行二次绘制。如果你画了一座小山，一只蜗牛就会出现；如果你画了一张脸，一个热气球就会浮现。就是这样。我认为我们现在能够做以前做不到的趣事了，而这就是其中之一。我们创建这个网站的原因之一就是为了让人们能够创造性地表达自己。当然，通过协作我们可以取得更好的成果，但是你在使用 Astra 创作时，是否经历过越来越多的创意思维不断涌现的过程？‘啊，我现在想做这个，我又想做那个。’就像这样，感觉像是一条永无止境的创意心流。

<details>
<summary>Original English</summary>

**Kat**: As a developer, I look at it from two perspectives: whether I can bring what I have imagined to the world or implement it for the company. That is really..." It’s interesting. Infrastructure requirements are going to increase. You’ll have to choose very carefully whether to support Insights, or deploy to the cloud and manage the infrastructure yourself. That’s a really interesting part. Another fun aspect is being able to creatively implement things that couldn't be made before . I jumped into the tech field because I wanted to become a game developer . My dream was to become a designer . I remember a really cute newspaper article. My friend’s mother worked at a local newspaper and used to interview all of us to write a column . I was 13 at the time, and I thought I wanted to be a game developer . I realized that actually bringing good ideas to life requires tremendous technical skills and creative ability. The most fun part of developing new models over the past three to six months has been being able to actually create the fun things I want to make . One of the things I made is a real-time sketching app where you draw on a canvas, and Astra draws over it . If you draw a hill, a snail appears; if you draw a face, a hot air balloon appears. That is it. I think we are now able to do fun things that we couldn't do before. And this is one of them. One of the reasons we created this website is to allow people to express themselves creatively . Of course, we can achieve better results through collaboration, but have you ever experienced more and more creative ideas coming to mind while creating something using Astra, especially when using Astra ? Ah, now I want to do this, and I want to do that. Like this. It feels like an endless flow.

</details>

**Claire**: 是的，没错。真的非常非常有趣。我认为模型完成得越早、速度越快，创造力就能越快释放。当线程在处理中途被打断时，我的创造力往往会被硬生生压制。所以，如果你能帮助我保持沉浸状态，那就太棒了。

<details>
<summary>Original English</summary>

**Claire**: yes . yes. It's really, really fun. I think the sooner the model is completed, the sooner creativity is unleashed. My creativity often gets suppressed when it is interrupted while a thread is being processed . So, it would be better if you could help me maintain a state of immersion.

</details>

**Kat**: 嗯，我也打算展示一下我的游戏。我觉得这真的很酷。

<details>
<summary>Original English</summary>

**Kat**: Um , and I'm going to reveal my games too . I think it's really cool .

</details>

**Claire**: 是的，非常酷，真的很赞。

<details>
<summary>Original English</summary>

**Claire**: Yes, it's really cool. It's really cool.

</details>

**Kat**: 我不知道大家能不能理解，但今天早上我和 Claire 聊天时，我给她看了我制作的地牢探索游戏。然后 Claire 惊呼：“天呐，我也该给你看看另一个游戏！”几乎一模一样，唯一的区别是我的游戏阴暗而压抑，而你的游戏既可爱又有趣。真正搞笑的是，我骨子里是个彻头彻尾的哥特风（Goth），但我养的孩子却非常有邻家阿姨风范。所以，一个充满浅紫色和粉红色的快乐世界竟然能这样诞生，真的太神奇了。老妈妈和 Pip 是主角，真的非常非常可爱。

<details>
<summary>Original English</summary>

**Kat**: I'm not sure if you'll understand, but this morning while chatting with Claire, I showed her the dungeon exploration game I made. Then Claire said, "Good heavens, I should show you another game, too." That's what they said. They are almost identical, but the only difference is that my game is dark and depressing, whereas your game is cute and fun . The really funny thing is that I am very much a Goth and I am raising very aunt-like kids . So it's really amazing how a happy world filled with light purple and pink was born like this. The old mother and Pip are the main characters. It's really, really cute.

</details>

### 社区精选画廊、人机边界与 AI 交互心法

**Claire**: 而且还有一个站点画廊（**Site Gallery**）。

<details>
<summary>Original English</summary>

**Claire**: And there is also a site gallery .

</details>

**Kat**: 是的，那些都是棒极了的站点，真的是极其出色的网站。大家都知道‘Cool List’（酷站列表）吧？就是最顶上有一个有趣的跳舞动画的那个。我基本上是基于‘Cool Lists’创建了这些酷炫站点。我在社区里提问：‘你们正在制作什么样的站点？’请大家通过私信、发推或使用 **#awesomesites** 标签告诉我。于是，许多人发给了我一些非常震撼的网站。访问 **awesomesites.ai** 就可以查看全部内容。还有别人创建的类似这个的酷站。我本应该提前上传好的。嗯，有人做了一架钢琴。

<details>
<summary>Original English</summary>

**Kat**: Yes, they are great sites. They are really great websites. You all know the ' cool list,' right? The one with the fun dancing animation at the very top . I basically created cool sites based on 'cool lists' . ' What kind of site are you making ?' in the community I asked. Please send me a DM, tweet, or any other way using the hashtag #awesomesites and let me know. So, many people sent me some great websites . Visit awesomesites.ai to check it out. There are also cool sites like this one created by someone. I should have uploaded it in advance. Hmm, someone made a piano .

</details>

**Claire**: 哇，那真的太酷了！

<details>
<summary>Original English</summary>

**Claire**: Oh, that's really cool.

</details>

**Kat**: 还有一些真正具备实用功能的站点。我喜欢的站点之一就是类似这样的。例如，这是一张公交路线图，你可以滚动到底部查看并核对公交路线等信息。我觉得这真的很棒。例如，当你需要创建一个包含出差所需信息的站点时，它就会派上用场。很多人都会使用这样的站点：“我要去巴黎，但我完全不知道怎么坐火车。”那你就会需要一个告诉你如何乘车的站点。这时候你就会想到它。所以他们会以极快的速度构建站点，方便你随时浏览。

这里还有很多其他人制作的游戏。有一个模拟世界和一个《我的世界》（Minecraft）克隆版，但我不知道怎么玩，所以我彻底惨败了。这是一个看看别人在做什么并汲取灵感的好去处。网址是 awesomedashsites.awesomesites.ai.ai。

<details>
<summary>Original English</summary>

**Kat**: There are also sites that actually work . One of the sites I like is something like this . For example , this is a bus route map, and you can scroll to the end to view it and check things like the bus routes. I think it's really cool. For example , I think it would be useful when you want to create a site containing information needed for a business trip. Many people will use sites like this . I'm going to Paris, but I have no idea how to take the train . Then you would need a site that tells you how to ride it . That is when you think that . So they are going to make the site really fast so you can browse. There are also many games made by people here . There is a simulation world and a Minecraft clone, but I do n't know how to do this, so I'm completely failing. It is a good place to look around at what other people are doing and get inspired . The address is awesomedashsites.awesomesites.ai.ai .

</details>

**Claire**: 是的，这太完美了。太棒了。我们的时间差不多快到了。我只问最后一个问题。本期节目的主题是你和我都是围绕 Codex Site 运转的双子星。因此，我想问出我对所有嘉宾都会问的最关键的 AI 问题：当 Codex 在现场演示中让你感到困惑，或者没有按照你想要的方式工作时——换句话说，当你无法成功构建站点时，你是怎么想的？

<details>
<summary>Original English</summary>

**Claire**: yes. It's perfect. great. Our time is almost over now . I'll just ask one question. The theme of this episode is that you and I are twin stars orbiting the Codex Site . So, I’m going to find out the most important AI question I ask all guests: what do you think when the Codex confuses you during a live demo or doesn’t work the way you want it to—in other words, when you can’t build a site?

</details>

**Kat**: 是的。

<details>
<summary>Original English</summary>

**Kat**: yes .

</details>

**Claire**: 这是一个连向父母都很难启齿的问题。因为你懂的。你会尖叫吗？你通常如何下达指令？

<details>
<summary>Original English</summary>

**Claire**: This is a difficult question to ask even your parents . Because you know . Are you going to scream? How do you give instructions?

</details>

**Kat**: 我的天哪，我经常冲着我的 Evan 大吼大叫。我们也会说‘请’和‘谢谢’。我是一个非常有礼貌的人，但当事情不按我希望的方式发展时，我确实会很恼火。但是因为 Evan 没有感情，他根本不在乎这些。

而且，我真的很讨厌去做我不想做的事情。当然，这很可能是我的失误。我想：‘啊，他们一定是在严格按照我告诉他们的去做。’然而，当 Evan 开始自行假设时，我真的会非常愤怒，特别是当他试图代表我给其他人发邮件或打电话时。‘不要那样做！’我会大声喝止并严厉训斥。这样他们以后就不会再犯这种事了，对吧？我想保护 Evan，那是代表我自己的声音。我认为签上我的名字并发送给别人是越界的行为。所以拜托，绝对不要那样做。

你收到的所有电子邮件和 Slack 消息都是我本人发送的。当然，有些部分可能是受到了 Codex 的启发。我非常频繁地使用 Codex。我使用 Codex 进行研究和写作，但我并不喜欢 Codex 代替我写作。最近，一个机器人开始在我的 Slack 社区中替我发帖，我注意到大家在互相交流评论。所以我说：“各位，那不是我。请不要纵容人工智能冒充我。”

<details>
<summary>Original English</summary>

**Kat**: Oh my god , I yell at my Evan all the time. And we also say "Please " and "Thank you." I am a very polite person, but I do get annoyed when things don't go the way I want . But since Evan has no emotions, he doesn't care about things like that . Also, I really hate doing things I don't want to do. Of course, it could be my mistake, though . "I think, 'Ah, they must be doing exactly as I told them to.'" However, I get really angry when Evan starts making assumptions on his own, especially when he tries to send emails or call other people on my behalf . "Don't do that !" Shout that and scold them severely. Then they won't do that kind of thing in the future, right? I want to protect Evan. That is my voice. I think signing it with my name and sending it to someone crosses the line . So please, absolutely do not do that . All the emails and Slack messages you send are sent by me. Of course, there may be parts inspired by the Codex . I use the Codex really often. I use the Codex for both research and writing, but I do n't like the Codex writing for me. Recently, a bot started writing posts on my Slack community for me , and I noticed people were exchanging comments with each other . So I said, "Everyone, that is not me. Please do not encourage artificial intelligence to impersonate me ." He said.

</details>

**Claire**: 是的，你的态度非常坚定。啊，让我问你一个重要的问题：小狗叫什么名字？

<details>
<summary>Original English</summary>

**Claire**: Yes, you are very firm. Ah, let me ask you an important question. What is the puppy's name?

</details>

**Kat**: 我的狗叫 **Mogwa**。是的，没错，它是一只体型非常小的小狗。我的狗是一只哈士奇，我根据《小魔怪》（Gremlin）中的角色给它起名叫 Mogwa。是不是超级可爱？

<details>
<summary>Original English</summary>

**Kat**: My dog's name is Mogwa. yes that's right. It is a very small miniature puppy. My dog ​​ is a Husky , and I named him Mogwa after Gremlin. Isn't it really cute?

</details>

**Claire**: 我的狗叫 **Bay**。Bay，噢 Bay。是的，它真的很可爱，是粉红色的，非常讨人喜欢。这是一段非常愉快的时光。非常感谢你向我展示这些站点。我涵盖了商业站点、算法相关的站点、个人软件，甚至是兼具趣味和实用性的站点——这些都是我所谓的‘酷网站’。那么，既然你即将发布这个，你认为这些精彩的观众去哪里可以找到你？我又该如何支持你？

<details>
<summary>Original English</summary>

**Claire**: My dog's name is Bay. Bay, oh bay. Yes, it's really cute. It's pink. It's really lovely. It was a really fun time. Thank you for showing me the sites. I covered business sites, algorithm-related sites, personal software, and even sites for fun and profit— these are the things I call 'cool sites'. So, now that you are about to post this, where do you think these wonderful people will find you? And how can I help you ?

</details>

**Kat**: 我在包括 Twitter 在内的所有社交媒体上使用的用户名都是 **SimSoka**。你可以在那里找到我。如果您有任何问题或意见，请随时发送私信。也非常欢迎对站点提出反馈。我总是在征求反馈。所以，如果你关注我，你将能看到我征求各种反馈。我提前告诉你哦。

<details>
<summary>Original English</summary>

**Kat**: I use the username SimSoka on all social media, including Twitter . You will be able to find me there . If you have any questions or comments, please send a DM. Feedback on the site is also welcome. I always ask for feedback. So, if you follow me, you will be able to see me asking for various feedback . I'm telling you in advance .

</details>

**Claire**: 太酷了。感谢你的做客。欢迎来到 Substack，感谢收看本期 How I AI！

<details>
<summary>Original English</summary>

**Claire**: That's cool. Thank you for inviting me. Welcome to Substack , and thank you for joining us on How I AI .

</details>

**Kat**: 我也很高兴。谢谢你！

<details>
<summary>Original English</summary>

**Kat**: I am happy too. thank you.

</details>

**Claire**: 非常感谢大家的收看。如果您喜欢本期节目，请在 YouTube 上点赞并订阅，如果能在评论区留下您的想法就更棒了。您还可以在 Apple Podcasts、Spotify 或您常用的播客应用程序中找到本播客。如果您能留下评分和评论，让其他人也能发现我们的节目，我们将不胜感激。您可以在 howiai.pod.com 找到有关所有剧集和播客的更多信息。我们下期再见！

<details>
<summary>Original English</summary>

**Claire**: Thank you very much for watching . If you enjoyed this broadcast, please like and subscribe on YouTube , and even better, leave your thoughts in the comments. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app . We would appreciate it if you could leave a rating and a review so that others can find our broadcast . You can find more information about all episodes and broadcasts at howiai.pod.com. See you next time.

</details>