---
author: How I AI
date: '2026-10-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zF-J3rMbzZw
speaker: How I AI
tags:
  - prototyping
  - design-system
  - model-context-protocol
  - vibe-coding
  - developer-tools
title: Reddit 如何基于设计系统与 MCP 构建高保真原型工具 Reddit Proto
summary: Reddit 首席 UX 工程师 Blair Metcalf 介绍了专为设计师与产品经理打造的原型工具 Reddit Proto。该工具屏蔽底层 Git 复杂性，结合设计系统、登录真实数据与 Cursor，并通过自定义 MCP（Model Context Protocol）打通 Figma、代码与 PRD，大幅缩短产品原型验证到工程落地的链路。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Blair Metcalf
  - Claire Vo
companies_orgs:
  - Reddit
products_models:
  - Reddit Proto
  - Cursor
  - Figma
  - Firecrawl
media_books:
  - How I AI
status: evergreen
---
### 引言与背景

>> 如今，设计与产品之间的距离非常大。如果让每个人都成为构建者，他们就能轻松通过 vibe coding 开发新功能与新产品。因此，我们打造了一个脚手架（harness），它使用我们的设计系统以及所有的组件和 UX 模式，让所有设计师和产品经理都在既定轨道上前进。这样一来，你可以产生成千上万个想法并进行评审，然后挑选其中一个，再把精力投入其中并最终推向生产环境。
<details><summary>Original English</summary>
>> Now, the distance between design and product is wide. If we made everyone a builder, they could vibe code new features and products easily. And so, we made a harness that uses our design system and all of our components, UX patterns, [music] and it keeps all the designers and product managers on rails. And so, this way that you can make a million ideas, they can be reviewed, and then you can pick one, and then that's where we spend our time, and that's what goes into prod.
</details>

>> 我还没听说过有谁会说：“好的，直接放开权限，让你接入生产数据并完成渲染。”
<details><summary>Original English</summary>
>> I have not heard anybody say, "Okay, go ahead and let you off into your production data and render that."
</details>

>> 我们之所以这样做，是因为 Reddit 拥有个性化数据。但如果设计师全都在 Figma 里做模拟图，然后再拿去给领导层看，领导层看了就会觉得：“这跟我有什么关系？”而且你不需要花 9 个月的时间把它推到生产环境才能看它是否有效。这节省了大量时间，大家可以去忙别的事情。所以，如果你用真实数据制作出这种真实的现实级原型，他们就能对新功能进行实际测试。搜索就是一个极佳的例子，就像在《How I AI》里那样，它能识别出播客。它拉取这些真实数据，发送给 LLM 进行排序，然后你就可以测试这套设计了。
<details><summary>Original English</summary>
>> why that we do this is because Reddit has personalized data. But if designers are mocking everything in Figma, and then they show that to leadership, leadership's going to look at that and be like, "This isn't relevant to me." And you don't have to take 9 months to get that into prod, see if that works. It saves so much time, and everybody can work on other [music] things. And so, if you make one of these real-world prototypes with real data, they'll put it through the paces of like some new feature. Search is like a is a great example to like how I AI. And it knew the podcast. [music] Like, it's pulling that real data, it sends it to an LLM, ranks it, and then [music] you can test out that design.
</details>

>> 是设计师做的原型最多，还是产品经理做的原型最多？到底谁做的原型最多？
<details><summary>Original English</summary>
>> Are designers prototyping the most, or product managers prototyping the most? Like, who is prototyping the most?
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

>> 欢迎回到《How I AI》。我是 Claire Vo，一名产品负责人和 AI 痴迷者，我的使命是帮助大家用这些新工具更好地进行构建。今天，我们请到了 Reddit 的首席 UX 工程师 Blair Metcalf，他将向我们展示 Reddit Proto——这是他们为产品经理、设计师以及其他所有人量身打造的原型脚手架，能把他们的想法转化为接近生产环境的原型，并分享给公司内的任何人。对于任何对设计系统、原型设计以及如何在不接触 GitHub 的情况下打造高质量产物感兴趣的人来说，这期内容都非常精彩。让我们马上开始。本期节目由 Firecrawl 赞助呈现，它能为你的 AI Agent 提供来自网络及更多渠道的数据。你的 Agent 可以搜索并抓取网页，同时通过单一连接访问 Alexandria 快速扩张的超过 1 亿个索引源和 200 多家数据提供商的资源库。
<details><summary>Original English</summary>
>> Welcome back to How I AI. I'm Claire Vell, product leader and AI obsessive, here on a mission to help you build better with these new tools. Today, I Blair Metcalf, principal UX engineer at Reddit, and he's going to show us Reddit Proto, their custom harness for product managers, designers, and anyone else to get their ideas into a production-like prototype they can share with anybody in the company. This is an awesome one for anybody interested in design systems, prototyping, and how to make high-quality things without exposing GitHub. Let's get to it. This episode is brought to you by Fire Crawl, [music] which gives your AI agents data from the web and beyond. Your agents can search and scrape the web while accessing Alexandria's rapidly expanding library of over a hundred million index sources [music] and more than 200 data providers all through one connection.
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

>> 将 Firecrawl 连接到 ChatGPT 或 Claude，即可查找人员及其工作邮箱、挑选梦幻橄榄球阵容，或为下一次营销活动分析趋势。Firecrawl 正在为超级智能打造资料库，将更多世界知识引入你已在使用的工具中。
<details><summary>Original English</summary>
>> Connect Firecrawl to ChatGPT or Claude to find people and their work emails, pick your fantasy football lineup, or analyze trends for your next marketing campaign. Firecrawl is building the library for super intelligence, bringing more of the world's knowledge into the tools you already use.
</details>

>> [音乐]
<details><summary>Original English</summary>
>> [music]
</details>

>> 访问 firecrawl.dev/howiai 即可开始。Blair，欢迎来到《How I AI》，感谢你的加入。
<details><summary>Original English</summary>
>> Go to firecrawl.dev/howiai to get started. Blair, welcome to How I AI. Thanks for joining.
</details>

>> 谢谢，很高兴来到这里。
<details><summary>Original English</summary>
>> Thanks. I'm glad to be here.
</details>

### 构建 Reddit Proto 的初衷与工作流

>> 我非常兴奋能邀请你上节目的原因之一是，我认为最顶尖的团队在回答“我们如何在产品设计与工程流程中使用原型”这个问题时，最终给出的答案往往是：“我们直接自己搭一套装备吧。我们要构建属于自己的原型脚手架，让它完全契合我们团队的运作方式。”那些做到这一点的团队——这并非遥不可及——确实为团队释放出了一些神奇的力量。所以，请带我们了解一下这到底是什么，以及你们为什么要构建它？
<details><summary>Original English</summary>
>> Well, one of the reasons why I was so excited to have you on the show is I feel like the best teams, their answer to what are we how are we going to use prototyping in our product design engineering flow is eventually to decide, you know, we're just going to build our own our own rig here. We're going to build our own prototyping harness and it's going to give us exactly what we need for exactly how our team operates. And the folks that do that and it is not impossible to do, unlock some magic in the team. So, walk me through what this is and why you built it.
</details>

>> 我们想要创新、加快节奏，并更快地将新功能送到用户手中。所以我们构建了一个脚手架，它整合了我们的设计系统、所有组件和 UX 模式，让所有设计师和产品经理都能在轨道内行事。这样你就可以做出成千上万个想法，接受评审，然后挑出其中一个，那就是我们集中精力投入的地方，也是最终上线到生产环境的内容。
<details><summary>Original English</summary>
>> We wanted to innovate, go faster, and get new features into users' hands. And so, we made a harness that uses our design system and all of our components, UX patterns, and it keeps all the designers and product managers on rails. And so, this way that you can make a million ideas, they can be reviewed, and then you can pick one, and then that's where we spend our time, and that's what goes into prod.
</details>

>> 我现在看到的是 Reddit 移动端应用或移动网页的一个小型渲染效果。请告诉我，你们团队内部的人具体是如何进入这里并实际进行设计的？你认为它有什么独特之处？我的意思是，它包含了设计系统，但除此之外，你们为什么构建它，以及你们搭建这个脚手架的方法究竟有什么超级独特的地方？
<details><summary>Original English</summary>
>> So, what I'm looking at right now is a little render of the the mobile app or the mobile site um for for Reddit. So, tell me how how would somebody come to this inside your team and actually design something? What do you think is is unique? I mean, it has the design system, but what else, you know, why did you build this and what is super unique about how you approached the the harness that you built?
</details>

>> 当我们开始与设计师协作时，我们希望一开始把所有的 Git、文件结构这些东西全部遮蔽起来。所以我们实际上做了一个桌面端应用，能直接带你进入一个新项目，你加载脚手架模板（boilerplate），给它命个名，然后就直接来到了这个 vibe coding 的环境。你可以在任何喜欢的 IDE 中工作，它会把应用的起始状态设定好。我们把这个应用看作整个世界，随着大家不断添加新功能，它就像一座山，我们把这座山吸收融合进来，成为每个人的新起点。
<details><summary>Original English</summary>
>> When we started working with designers, we wanted to start off you skating all of Git, what the file structure is. And so, we actually made an app on your desktop that just gets you right into a new project and you would load the boilerplate and name it and then you would end up here in a vibe coded environment. You can work in any IDE you like and it sets up like what the app's a starting point. And we think of that app is like, you know, this is the whole world and as people add new features, it's kind of like a mountain and we absorb that mountain and it's everyone's starting point.
</details>

>> 也就是说，第一，如果我是设计师或产品经理，我不需要考虑诸如“我是否克隆了仓库？我是不是在某个分支上？我是不是在本地运行？”之类的问题。你们做了一个轻量定制应用，上面写着启动一个项目，高高兴兴地给项目命个名，然后你们包揽了所有复杂的底层脚手架工作。那么，这个脚手架会把应用置于某个特定状态吗？作为设计师或产品经理，进入这个脚手架后能获得哪些便利？
<details><summary>Original English</summary>
>> So, one, if I'm a designer or product manager, I don't have to think about like am I cloning the repo, am I on a branch, am I running locally? You've created a little custom app that says to start a project. Happy happy. Um you name that project and then you all do the hard work of like a baseline scaffold. And then does that scaffold put the app in a specific state? Like what are the kind of convenience things that you get when you land with this scaffold as a designer or product manager?
</details>

>> 没准，正是这样。对，我刚才展示了如何创建新项目。它在后台克隆 Git，但你完全不需要了解这些。我们回到那个屏幕，你直接就可以开始写代码。你开箱即得的东西是各种功能示例。每个产品开发团队都会做这些事情：向产品中添加新功能并进行探索。下面还有其他小玩意，比如导航控制。你可以修改导航，也可以禁用导航，因为有些利益相关者点击得太频繁，而你并不想让他们乱点。
<details><summary>Original English</summary>
>> That's right. Yeah, so I just showed like how you create a new project. It's cloning the get. You don't need to know any of that. We'll go back to that screen and you'll just start coding. And the things that you get right out of the bat are examples of like features. And this is what every product development team does. They're going to add new features to the product and they're explorations. There's other doodads under here of like navigation. Um you can change the navigation. You can prevent navigation because some stakeholders click too much and you don't want them to click.
</details>

>> [笑声]
<details><summary>Original English</summary>
>> [laughter]
</details>

>> 我们有像……
<details><summary>Original English</summary>
>> We have like
</details>

### 控制器、真实数据与 Cursor 交互

>> 是的，一切都是可控的。你可以更换设备、切换主题，比如切到暗黑模式，你可以测试可能遇到的每一种状态。甚至包括身份角色，比如谁是版主（moderator）。Reddit 拥有复杂的用户生态。然后这里最棒的小玩意在于：你可以使用已登录的用户数据，这样你就能知道自己的设计是否真正行得通。这对各类实时数据流非常有帮助。比如如果你想做搜索功能，你直接就可以在这里执行搜索。在录制之前，我刚在这随便玩了一下，我就想知道我能不能通过这些批注添加搜索功能？令人惊讶的是，我真的做到了。我在上面评论：“制作相关的输入预选建议（typeaheads）、热门及近期社区等。”然后在下面写道：“整体方向是使用已登录的 Reddit 数据，并在用户在搜索框输入时提供真实的预选建议。”接着我把它发送给 Cursor，它当场就 vibe code 出来了。当时我只是闹着玩的，结果惊呆了，它居然成功运行了。
<details><summary>Original English</summary>
>> Yeah, and then so everything is controllable. You can change the device, the theme and so you can switch to dark and you can test out every every um every state that you can get in. Even like who is a moderator. And so Reddit has complex user ecosystem. And then the nice the the nicest doodad here is that you can then use signed in data and so you'll know if your design works. This this helps with all kinds of real-time data feed. So, like if you wanted to do search, you can actually do search right here. And before we we we started this, I was just playing around and I was wondering could I add search with these annotations? And surprisingly, I was able to I commented here, "Make relevant type aheads, trending recent communities, etc." And then down here, I said overall direction using the signed-in Reddit data and real type aheads as user types in the search box. And then I sent that to Cursor and it vibe coded it on the spot. And this was just playing around. I was stunned. It worked.
</details>

>> 好，我想为正在听播客或者刚才可能遗漏了部分内容的观众梳理一下。首先，你们把功能做成了配置项（configuration）。基本上就是在受限的原型内部，拥有开启或关闭功能的开关能力。你们还可以对原型本身进行配置，比如关闭像导航这类功能的交互性。我很喜欢这一点，因为如果是一个全功能的原型，人很容易漫无目的地到处乱点。
<details><summary>Original English</summary>
>> Okay, so I just want to kind of like walk this through for folks that that are listening or maybe miss some of this. So, first of all, you have like features as configuration. Basically, like the ability to toggle on or off features inside this constraint prototype. Um you have the ability to configure the prototype itself in terms of like turning off the interactivity of features like navigation. I love this because if it is a fully like featured sort of prototype, you can kind of go anywhere with it.
</details>

>> 嗯嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 但这能让产品经理或设计师进行限制，明确指出“这就是我希望你关注的部分”。你显然可以在不同设备之间切换，但你还可以在不同的用户画像视图之间切换，我觉得这非常有趣。另外，我希望大家不要错过这一点：如果我理解有误请纠正我，看起来你们在初始化时是用 Mock 数据搭好脚手架，但随后可以用自己的账号登录，并在原型中直接渲染生产环境的数据。这以前我从没听别人这么用过，我认为这非常巧妙。我常听大家谈论 Mock 数据，我们之前有一期很棒的节目讲过使用 JSON 作为原型的数据支撑，通过修改 JSON 而不是直接去修改原型里硬编码的数据。但我从没听谁说过：“去吧，直接让你接入生产数据并完成渲染。”这让大家在测试新功能时有了极其灵活的数据集可用。
<details><summary>Original English</summary>
>> Um but this is letting a product manager designer sort of constrain and say like this is the piece that I want you to pay attention to. Um you can obviously switch between devices, but you can also switch between persona views, which I thought was very interesting. And then I want to make sure people did not miss that this. One of the things that looks like you do, and correct me if I'm wrong, is you scaffold it with mocked data, but then you can log in with your account and render production data in the the prototype as well. And so, this is not a tactic that I've heard people use before, which I think is really really clever. I've heard a lot about mocked data. Um we have a great episode about using JSON as the backing for your prototypes and updating the JSON instead of updating kind of like hard-coded data in your prototype. But I have not heard anybody say, "Okay, go ahead and let you off into your production data and render that," which gives you a much more flexible set of data to work with when you're testing new features.
</details>

>> 没错。是的，这是个聪明的技巧，我们的团队就像一群魔术师。我们之所以这么做，是因为 Reddit 拥有高度个性化的数据。但如果设计师全都在 Figma 里做模拟图并拿去汇报，领导层看到就会想：“什么？这跟我根本无关啊。”所以，如果你做出了这种带有真实数据的现实级原型，他们就会在体验新功能时动真格地全面测试它。搜索就是一个极佳的例子，因为他们会希望看到具体的搜索结果。我刚才试过了，我输入类似“How I AI”，它就能识别出播客。它拉取这些真实数据，发送给 LLM 进行排序，然后你就可以测试这套设计了。这次的设计我压根没花时间精细调整，但设计师随后完全可以去丰富落地页、输入预选和搜索结果。你不需要花 9 个月的时间把它推进到生产环境才能检验是否奏效。这节省了太多时间，每个人都可以把精力放在其他事情上。
<details><summary>Original English</summary>
>> Right. Yeah, it's it's a clever trick. Our our team is like a bunch of magicians. And the reason why that we do this is because, you know, Reddit has personalized data. But if designers are mocking everything in Figma and then they show that to leadership, leadership's going to look at that and be like, "What? This isn't relevant to me." So if you make one of these real-world prototypes with real data, they'll put it through the paces of like some new feature. Search is like a is a great example because they're going to want the search results. I think I already did it. I said like how I A I. And it knew podcast. Like it's pulling that real data. It sends it to an LLM, ranks it, and then you can test out that design. This This design, I didn't spend any time on it. Um but a designer could then populate the landing, the type-aheads, and and the results. And you don't have to take 9 months to get that into prod, see if that works. It saves so much time, and everybody can work on other things.
</details>

>> 关于做修改这部分，根据你刚才展示的内容我推测一下：你们有一种基于 Prompt 的机制，但它本质上只是把 Prompt 转交给 Cursor，对吗？
<details><summary>Original English</summary>
>> And then to make modifications to it, just because I'm I'm kind of inferring based on what you've showed us, you have sort of like a prompt-based thing, but that's ultimately just kicking prompts over to Cursor. Is that right?
</details>

>> 没错。是的，这个流程的起步是一个出人意料的工作流。不过一旦我写好了这些批注，我只要点击“发送给 Cursor”，它就会生成一个文件。接着我只需要告诉 Cursor“应用批注”，它就会提取代码中的位置、批注内容以及整体方向来启动修改。凭借这种精准度，你几乎不需要什么额外培训，就能定向针对任何界面区域（surface）、复合结构（composite）或组件添加真实数据。
<details><summary>Original English</summary>
>> That's right. Yeah, so the way that this kicked off was I this is a surprising workflow. But once I showed these annotate Once I wrote the annotations, I just said send a cursor, and it writes a file, and then I just tell Cursor apply annotations, and it takes the location in the code, the annotation, and the overall to kick it off. And you can with that specificity, you can target any surface, any composite, any component, and add real data to it with very little training.
</details>

### 部署、共享与规模化管理

>> 明白了。所以如果我在这个原型上点击某个东西并在上面写下一段批注，这个原型已经预先丰富了上下文，包含了“代码大致在这个位置、这个组件大致是什么、用户的具体修改诉求是什么”。因此，它就像是在这个代码仓库中发出了一次极具针对性的编辑请求。这是真实的代码仓库，还是一个专门用来做原型的近似镜像仓库？
<details><summary>Original English</summary>
>> Got it. So if I click something in this prototype and write an annotation on it, the prototype has already been enriched with This is like roughly where the code is. This is roughly what this component is. This is what the request is from the user. And so, it's like a very targeted um edit request in this repo. Is this the real repo or is this like a an approximate repo that's just for prototypes?
</details>

>> 针对你刚才问的所有问题，我可以进入批注面板，把它们清空，然后输入“把这里改成斜体”。你可以非常精准地针对具体细节进行修改。它会调用我们所有的设计系统 Token、组件等。而且这是货真价实的。我前面展示的那个 Launchpad，会把它直接部署在我们的基础设施上。它底层使用的是 Kubernetes，本质上就像一个内部版 Vercel。因此你根本不需要操心任何部署问题，直接就可以分享。你可以在内部分享，它会复制 URL；你也可以向外部分享，其他人扫码即可。经过一些安全验证后，它就直接出现在手机上了。它是一个 PWA，这些是我已经安装的应用，你可以像在电脑上一样随意点击浏览并进行检查。
<details><summary>Original English</summary>
>> So, yeah, everything that you asked, I can go into the annotations. I can clear these and I can say make this italics. And so, you can target very specific things. It'll use all of our design system tokens, components, etc. And then this is the real thing. Um that launchpad that I showed earlier, it deploys it on our infra. And so, it basic It uses in It uses Kubernetes. It's basically like an internal Vercel. Um and so, then you don't have to worry about any deployment and you can share it. You can share it internally. It'll copy the URL. Or you can share it externally and you can like scan that. You go through some security and then now it's on your phone. And so, then that is a PWA. And these are these are apps that I've already installed and you can click around them as if you were on desktop and you can check.
</details>

>> 明白了。我刚才就很纳闷你们在内部是如何共享这些原型的？你们是直接给链接或发二维码，大家就能打开并试玩你的原型吗？是这样运作的吗？
<details><summary>Original English</summary>
>> Got it. So, that's the way that you I was I was curious. So, how do you share these prototypes internally? Are you just able to give links to people or QR codes and then they can pull up and and play with your prototype? Is that how it works?
</details>

>> 这正是我们目前正在推进的部分，进展非常顺利。在内部，你可以在 Slack 等工具上快速分享 URL。我们有一个集中展示所有人原型的仪表板。目前上面大约有 700 个原型。这里的问题在于它无法规模化，那个列表没法扩展。因此我们现在正在研发一个支持强大搜索的控制台。这样你就能搜到其他人的原型、了解他们在哪些业务领域工作、查看相关人员以及标签——比如某个功能被标记为“搜索”或“增长”。然后你可以按原型类型筛选，我们接下来会拓展到 iOS 和 Android。此外你还可以浏览属于自己的原型，查看你所属的团队。这将成为所有人快速发现谁在做什么的途径，并为领导层提供极佳的可见性。
<details><summary>Original English</summary>
>> This is a piece that we're working on right now and it's it's going into great places. Internally, you can share this URL quickly like on Slack. And we have we have a dashboard that just keeps everyone's prototypes. Right now, there's about 700. The problem with this is it doesn't scale. That list doesn't scale. And so, what we're working on now is a very searchable console. So, you can find people's prototypes, what areas they work in, um people, tags if that if that feature was like labeled, um you know, search or growth. And then you can go into prototype types. We're going to go into iOS, Android. And then you can also go through your prototypes. And so, what teams you work on. This would be the way that everybody can just discover quickly who's working on what and like gives a visibility to leadership.
</details>

>> 这些原型全都是公开的吗？原型是默认公开还是默认私有？我只是很好奇。
<details><summary>Original English</summary>
>> And are all of these prototypes public? Are our prototypes public by default or private by default? I'm just curious.
</details>

>> 对，在公司内部它们全是默认公开的。不过之后……
<details><summary>Original English</summary>
>> Right. Yeah, so internally they're all public. Um but then like
</details>

>> 确实。我们需要增加私有功能，应该加一些机制以便大家能秘密搞一些创新项目（skunk works）。
<details><summary>Original English</summary>
>> Yeah. We we need to add that. We should add some so you can work under the and skunk works.
</details>

>> 没错，悄悄进行。不过我也挺喜欢“一切默认公开”的理念，你可以随时看到别人在倒腾些什么。我很想知道谁做的原型最多？是设计师做的最多，还是产品经理做的最多？到底谁在做最多的原型？
<details><summary>Original English</summary>
>> Yeah, under under the radar. I don't know. I kind of like this idea of like everything's public. You can kind of see what people are are messing around with. I'm I'm curious who is prototyping the most. Like are designers prototyping the most or product managers prototyping the most? Like who is prototyping the most?
</details>

>> 是设计师和产品经理的混合。在 UX 和产品团队中，我们的采纳率达到了 100%。但也有一些令人意想不到的角色涌现出来：比如一位视觉设计师成了我们最出色的原型制作者之一；一位动效设计师也成了最顶尖的原型创作者之一。看起来这些人就像是优秀的导演，他们拥有巨大的全局视野与上下文（huge context），能够把所有事情清晰描述出来。他们毫无包袱，勇于尝试，从不担心失败。但总体来说是两者的混合，在超过 150 人的规模里，设计与产品之间的分布几乎可以说是对半开。
<details><summary>Original English</summary>
>> Yeah, so it's a mix of designers and product. Um we have 100% adoption in UX and product. But there are like some surprising folks that show up. Like a visual designer turned out to be one of our best prototypers. An animator turned out to be one of our best prototypers. And what it seems like is these people are like great directors. They have huge context. They can describe all of the things. Um they they are vulnerable and they try things without like worry of failing. Um but yeah, it's it's a mix. It's almost a perfect mix over design and product over 150 people.
</details>

>> 本期节目由 Firecrawl 赞助呈现，它能为你的 AI Agent 提供来自网络及更多渠道的数据。你的 Agent 可以搜索并抓取网页，同时通过单一连接访问 Alexandria 快速扩张的超过 1 亿个索引源和 200 多家数据提供商的资源库。将 Firecrawl 连接到 ChatGPT 或 Claude，即可查找人员及其工作邮箱、挑选梦幻橄榄球阵容，或为下一次营销活动分析趋势。Firecrawl 正在为超级智能打造资料库，将更多世界知识引入你已在使用的工具中。访问 firecrawl.dev/howiai 即可开始。我可以想象这如何改变了想法的生成方式，而且我也看到许多团队正在转向这种以原型为导向的设计需求模式。我好奇的是，这如何改变了设计的评审方式？你们如何给反馈？大家如何进行迭代？又是如何协作的？
<details><summary>Original English</summary>
>> This episode is brought to you by Firecrawl, [music] which gives your AI agents data from the web and beyond. Your agents can search and scrape the web while accessing Alexandria's rapidly [music] expanding library of over 100 million indexed sources and more than 200 data providers all through one connection. Connect Firecrawl [music] to ChatGPT or Claude to find people and their work emails. Pick your fantasy football lineup or [music] analyze trends for your next marketing campaign. Firecrawl is building the library for superintelligence, bringing more of the world's knowledge into the tools you already use. Go to firecrawl.dev/howiai to get started. I can imagine how this changes how ideas are generated um and I and I see a lot of teams moving to this more like prototype style um requirements for designs. What I'm curious is how has this changed how designs are reviewed? Like how do you give feedback? How do people make iterations? How do they collaborate?
</details>

>> 好的。是的，这部分也是我们目前正在推进的。简而言之，这些原型会直接进入领导层评审。领导层亲自使用它们、逐项点击，你能得到实时的反馈。你会从 Slack 收到反馈，但我们希望加入直接在原型上进行实时评论的功能。这样就有了那些批注，这些批注可以直接作为评论，也可以直接触发下一次构建构建。
<details><summary>Original English</summary>
>> Right. Yeah, and so this is a part that we're working on also, but long story short, these go into like leadership reviews. Leadership uses them, clicks through them, and you know, you're getting feedback live. You're getting feedback in Slack, but we want to add, you know, you can comment live on the prototype. And so you have those annotations. Those annotations can be kicked off, they could be comments, they could kick off another build.
</details>

>> 嗯嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 如果某位领导只是想说“做一下这个调整”，片刻之间就能实时生效。此外，刚才提到的控制台也有用于评论的模块。这些功能都在陆续推出。
<details><summary>Original English</summary>
>> If a leader just wants to say like make this change, it could it could be live momentarily. Um but then um you know, like that console, it also has a place for commenting. These are all things that are coming.
</details>

### 对研发效能的影响：即时对齐

>> 明白了。那么你觉得这带来了哪些改变？是研发速度（velocity）吗？还是质量？或者说是工艺（craft）？你觉得它对你们构建产品的方式最大的冲击体现在哪里？
<details><summary>Original English</summary>
>> Got it. And so do you feel like this has What What does this changed in terms of you know, is it velocity? Is it quality? Like craft? What do you Where do you feel like the impact to how you build products has been felt the most?
</details>

>> 是即时对齐（instant alignment）。如果你采用高工艺水平的系统，所有的研发速度都会自然涌现，因为你通过真实数据与领导层达成了对齐，评审的是真实的设计系统组件。没有人会卡在某个隐藏的陷阱上，也不会在一处细枝末节上钻牛角尖（rat hole），领导能迅速予以批准。这种一致性会传达给每个人。大家都清楚自己正迈向的北极星指标是什么，这就是即时对齐。
<details><summary>Original English</summary>
>> It's instant alignment. And so if you use systems with high craft, all the velocity like comes because you have, you know, alignment with leadership using real data, reviewing real design system components that nobody's hanging up on like a a gotcha and they don't rat hole on a detail, and they can quickly approve it. That goes out to everyone. Nobody Everybody knows like the North Star that they're heading towards, but it's it's instant alignment.
</details>

### 工程交接与 Figma MCP：从原型到 PRD 与代码

>> 那么，这套原型是如何交接给工程团队的呢？
<details><summary>Original English</summary>
>> And then how does this get handed off to engineering?
</details>

>> 没错，这是最核心的关键拼图，即：你能否将这些代码直接推向生产环境？这里我草拟了一个虚拟功能，就是把帖子保存到文件夹里。那么，有没有一种方式能让我们选中某个组件，复制示例 Prompt，然后把它带入生产环境？在刚才的 Launchpad 下，我们还可以启动一个新项目来制作“功能胶囊”（feature capsule）。具体做法是：你复制 Figma 中的位置，切换到 Figma MCP，选择“从 Figma 创建”，它就会生成我们称之为“功能胶囊”的东西。它做的事情非常丰富：它利用 Figma MCP 遍历整个设计系统，将其映射到我们已知的生产代码中。它还将 CI 审查反馈和工程师的反馈一并融入到了这个 MCP 当中。现在它正在分析所有这些 Figma 画框和组件，然后输出一份 PRD。我会确认：“是的，这正是你所看到的内容。”然后继续。随后它会生成这份 PRD。这些文档可以变得非常庞大。这里我们只是选了一个特定的画框，但你完全可以覆盖多个界面。我们尝试过把所有杂七杂八的东西都塞进去（the kitchen sink），但后来我们退回来了，重新回归到专注于高保真 UI。在这里你就得到了生成的 PRD，它会说明“用户目标是什么、验收标准是什么”，并深入到具体细节，附带 Figma 的链接。一旦完成，我点击接受并继续。把这个文件保存在本地，然后我们把它发送给 Cursor。
<details><summary>Original English</summary>
>> Right. Yeah, this is the big puzzle piece here, which is that like, you know, can you take this code and send it to prod. Um so here I've I've um sketched out a fake feature. Um it's just like saving posts to folders. And so, would there be a way that we could select a component and then copy the example prompt and take this into prod? So, under this um launchpad, we can also start a new project where we make a feature capsule. So, what you do is you copy the location in Figma. You go over to Figma MCP, you create from Figma, and it's going to make this thing that we call a feature capsule. And what it does is it takes a lot of things. It uses Figma MCP, it goes through all of the design system, maps it to what we know is in prod. It has also incorporated, you know, CI review feedback and engineer feedback into this MCP. And then now it's analyzing all of those uh Figma frames, components, and it'll spit out a PRD. And so, I'm going to say, "Yes, this is what you're looking at." I'll continue. And then it'll generate this PRD. These can get really large. This We just selected a specific frame. Uh but you could do many surfaces. We've tried the kitchen sink, but we kind of backed We're We're going back to just like high-fidelity UI. And so, here you've got your generated PRD, and it'll say like, "This is what the user goal is. This is the acceptance criteria." It'll get into details here. Links to the the Figma. And then uh once it's done, I'll accept and continue. And you you save this file locally, and then we'll send that to Cursor.
</details>

>> 你能再深入讲讲吗？如果有人也想自己做一套这样的东西——这里面大部分是你自己搭建的，还是怎么演进到这一步的？因为这真的很有意思：从一个 Figma 链接和画框链接出发，一路生成 PRD，最后变成 Cursor 可以执行的内容。请跟我们详细说说这是怎么构建出来的。
<details><summary>Original English</summary>
>> Can you explain Go go a little deeper. Somebody wanted to build this themselves Is this a lot of this you built yourself, or like how did you get here? Cuz this is really interesting. It's going from a Figma link um and frame link all the way through PRD, and then something that your cursor can execute. So, just like walk us through how it got built.
</details>

>> 好的。我们最开始是基于 Reddit Proto 设计系统建立的。
<details><summary>Original English</summary>
>> Right. So, we started with the Reddit proto design system.
</details>

>> 嗯嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 我们把所有的颜色和排版字体都固化到了设计系统中。接着我们读取生产代码，并在二者之间建立了映射。这里有所有按钮的尺寸规格。我们使用了 Code Connect，确保所有东西都连接在一起。这是一个让人大开眼界的震撼瞬间（whiz-bang moment），你会惊呼：“我这看的是个啥？”
<details><summary>Original English</summary>
>> And so, we have all of the colors and typography baked into our design system. And then we read prod and we mapped the two. Um so here you have all of the button sizes. And so we use code connect and we know that those are everything is connected. This is kind of the whiz-bang moment where like you're like, "What am I looking at?"
</details>

>> 噢是的，太真实了。
<details><summary>Original English</summary>
>> Oh, yeah, exactly.
</details>

>> 眼前呈现的是我们在 RPL（Reddit Product Language）体系中所知晓的每一个单独的 Token、组件、界面区域和用户旅程。在这张图里，这一个 Token 分别映射到了 Figma、GitHub 中的 iOS 代码仓库以及原型代码仓库中。这里还能识别出某些平台上该 Token 的实际字面值是否存在差异。我们拿到这些信息后，再将它映射到生产代码。我们提交 PR，有些通过了 CI 审查，有些没有通过，我们收集所有工程师的反馈并反哺迭代。基本上就是从一张映射图开始，经历尝试、失败、迭代，并通过反馈不断完善 MCP。
<details><summary>Original English</summary>
>> This right here is is every single token, component, surface, journey that we know of across RPL, Reddit product language. And so here this one token is mapped into Figma into iOS in the GitHub and into the prototyping GitHub. And here it is picked out that there may be uh difference in the actual literal values in the token on some platforms. And so what we we then take that and we map it to prod code. We submit PRs that do and don't get through CI reviews and like we take all of the the engineer feedback and that iterates back. So basically you start with a map and then you try, fail, iterate and you refine the MCP through feedback.
</details>

>> 明白了。这是你们团队自己构建的 MCP？
<details><summary>Original English</summary>
>> Got it. And And this is an MCP that you've built?
</details>

>> 嗯……对，是整个团队。
<details><summary>Original English</summary>
>> Mhm. Well, uh the team. Um
</details>

>> 好的，我说的就是你们整个团队。那么这个 MCP 里有哪些工具？比如“组件在哪里”、“设计 Token 是什么”这些吗？
<details><summary>Original English</summary>
>> Okay. Yeah, I meant you the the you know, the collective the collective you. And what are some of the tools in that MCP? Is it like where's the component? What's the design token?
</details>

>> 没错。这里我们连接了这个名为 proto MCP ultra 的工具，它基本上是在监测你喂给它什么输入，然后去寻找对应的 Token、组件和示例代码，以此编写出符合生产规范的代码。这就是代码最终的样子。虽然我不能直接展示生产代码，但……
<details><summary>Original English</summary>
>> That's right. Yeah, so right here we got it hooked up this proto MCP ultra and it it's basically like looking for um what are you feeding it? And and then it's finding tokens, components, and examples to write that prod shaped code. This is what the code ends up looking like. I can't show the code but like
</details>

>> 当然理解。
<details><summary>Original English</summary>
>> course.
</details>

>> 但事实胜于雄辩，它能顺利通过所有的 Git 审查……
<details><summary>Original English</summary>
>> just proof in the pudding like it goes through all the get reviews.
</details>

>> 明白。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 并为你打出一个构建包，方便你在自己的设备上进行测试。
<details><summary>Original English</summary>
>> Um and makes a build for you to test out on um on your device.
</details>

>> 好的，我想确保大家没有漏掉这个流程：你们团队基本上打造了一个 MCP，用来将任意输入——在这个例子中输入可能是一个 Figma 画框——转化为在生产环境里去发现正确的 Token、设计系统组件和代码片段等内容。这样当你在生成原型风格的代码时，它就能尽可能地接近生产环境，因为它是通过这个 MCP 完成了系统性的遍历映射。
<details><summary>Original English</summary>
>> Okay, so I want to make sure that people don't don't miss this process, which is you all have built an MCP basically to translate any input and in this instance that input might be like a Figma frame into discovering the correct tokens, design system components, code snippets, whatever based in production. So that when you're generating prototype style code, it is as close to production as you can reasonably get because it's done this traversal kind of like through this MCP.
</details>

>> 是的，完全正确。在刚才的示例中，我们是从 Figma 走到生产代码。我们也尝试过直接从原型过渡到生产代码。但我们认为当前这种方式能非常精准地结合高保真 Figma 与高保真架构。它确实是通过一张映射图来实现这一切的。
<details><summary>Original English</summary>
>> Yeah, that's right. Yeah. And so in this example, we're going from Figma to prod. We have tried out going from prototypes to prod. But we think that this is like a very like accurate way of getting like high-fidelity Figma, high-fidelity architecture. Uh but yeah, it's doing that through a map.
</details>

### PRD 的价值与设计系统的“罗塞塔石碑”

>> 你知道我是个极度拥护 PRD 的人。你觉得 PRD 真的能带来不同吗？
<details><summary>Original English</summary>
>> You know I'm a PRD girl. Do you feel like the PRD makes a difference?
</details>

>> 是的，它实际上承载着很大的分量。当我们最初讨论时，之所以加入这一步，是因为那是与工程团队交接的契机。
<details><summary>Original English</summary>
>> Yeah, it's it actually carries a lot of weight. And so when we started talking, the reason why we added this is because that was the handoff
</details>

>> 嗯嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 这样你就能清晰界定范围、所有的用户目标和工作流。没错，这是极其完美的交接物，它包含了所有的上下文。
<details><summary>Original English</summary>
>> with engineering. And so then you clearly define your scope, all of the user goals, and you know, workflows. Yeah, it's it is it is the perfect handoff. It has all the context.
</details>

>> 大家听到了吧，PRD 是最完美的交接方式，继续写起来！我真的很喜欢这个思路。我觉得大家应该从中汲取的经验不仅在于“你能否构建自己的原型系统并让它贴合团队的构建习惯”，还在于你可以向技术背景较弱的伙伴隐藏 vibe coding 和原型制作的复杂性，同时后台仍然可以运行在类似 Heroku 这样的环境里。此外，构建这种基于设计系统的便捷封装 MCP 是个非常聪明的做法，因为很多时候如果不加限制，你只是任由 LLM 在代码库里胡乱摸索、碰运气找它自以为找得到的东西。
<details><summary>Original English</summary>
>> I mean, you heard it here, folks. The PRD is the perfect handoff. Keep making them. Um I I really I really love this. I mean, I think what folks should take away from this is not just can you build your own prototyping system and can you make it form fit to how your team likes to build things. Um you can hide away some of the complexity of vibe coding and prototyping from your less technical friends um while still running it in something like Heroku in the background. And then uh the idea of building sort of convenience method um design system-based MCPs is a really clever one because a lot of times you're just leaving these LLMs to kind of flail about in the code and find what they think they can find.
</details>

>> 没错，完全就是这样。很多人常说模型会产生幻觉，在写代码时乱写。而我们的观点一直都是：你的目标到底是什么？你的上下文是什么？去看设计系统，去看最终状态的形态，然后再从那里进行精细化调整。这正是那个使用“功能胶囊”的 MCP，它正在询问我应该把代码写在哪个位置。
<details><summary>Original English</summary>
>> Yeah, that's exactly it. Like, you know, um folks say that bots hallucinate. They hallucinate writing code. And our opinion has always been like, well, what what's your goal? What's the context? And you look at the design system, you look at the end state shape, and then we refine from there. But uh yeah, this is this is the um this is the MCP using that feature capsule and asking me where it should which where it should write the code.
</details>

>> 太神了。它基本上可以把代码写进主应用、写进原型或者你指定的任何地方。
<details><summary>Original English</summary>
>> Mhm. Amazing. And it could write that code basically in in the app or in a prototype or whatever you might want.
</details>

>> 目前它把代码写在一个平行的同级仓库（sibling repo）中，以保证生产代码仓库的干净。随后它会进行迭代，并发起一个草稿 PR（draft PR）。接着会有人审查这个 PR，最终可能通过，也可能不通过。
<details><summary>Original English</summary>
>> It's right now it's writing it in a sibling repo uh to keep uh prod clean. And then it'll iterate and then it'll send off a draft PR. And then yeah, and then that'll get reviewed and may or may not go through.
</details>

>> 也许能过，也许过不了。你能再退回到那个“罗塞塔石碑”（Rosetta Stone）界面吗？我不希望大家错过刚才那个惊艳的展示——你们对设计系统内发生的一切进行了精美的可视化。你们当时为什么决定做这个？
<details><summary>Original English</summary>
>> May or may not. And then can you go back to the Rosetta Stone because I don't want people to miss this amazing thing that you had, which is you have this like nice visualization of what's going on in our design system. Right. Why did you all decide to build this?
</details>

>> 理论上的思路是：我们如何把设计系统装进一个脚手架中，再把这个脚手架接入 MCP？我们做过好几次尝试，大家最大的疑问是：“我根本不知道里面都包含了什么。”于是我说：“那我们做一个可视化验证。”如果我能顺藤摸瓜，亲眼看到某个头像组件（Avatar）拥有这些颜色、被用在这些界面中、是这些工作流的一部分，我就可以在视觉上验证：我知道这个脚手架以及随后的 MCP 确实掌握了所有的组成部分。
<details><summary>Original English</summary>
>> Well, so the theory was how do we get the design system into a harness and then the harness goes into an MCP. And we had made several attempts and the number one thing was, well, I don't know if what's in there. And so I was like, well, this is a visual verification. And if I can hunt down and see that I know that a avatar has these colors and is used in these surfaces and is a is a part of these workflows, I can visually verify ah, well, I know that the harness and therefore the MCP has all of the parts.
</details>

>> 你的大脑就是这么运转的吗？因为你觉得“我能轻松把它可视化出来”，而我看了心想：“老兄，你能把这玩意儿可视化成啥样啊？这看着就像一堆模糊的光晕光环。”告诉我，这就是 Blair 大脑里的思考方式吗？
<details><summary>Original English</summary>
>> So, it's just like kind of and and is this how your brain works because you're like, oh, I can easily visualize. I'm like, you can visualize what, man? It's like a bunch of fuzzy auras over here. So, tell me, like is this just is this what what what is inside Blair's brain?
</details>

>> 这……好吧，这是整个团队大脑集思广益的产物。当时我试图向大家解释：“你需要一个位于一切上游的单一事实来源（SSOT）。”当我展示这个界面时，大家就会觉得：“我知道东西全在里面了。”这对团队来说是一种直观的视觉验证。
<details><summary>Original English</summary>
>> This is Well, yeah, the collectively this was what it was in the team's brain. But this was like, you know, I was trying to explain this to people like, you need a single source of truth that's upstream from everything. Um you know, and then when I would show this, people were like, I know it's in there. It was a visual verification for the team. Yeah.
</details>

>> 我太喜欢了，非常美观，看着很舒缓。不过可能还需要加点音乐。
<details><summary>Original English</summary>
>> I I love it, and it's very beautiful. It's very soothing. It needs a little It needs a little music, though.
</details>

>> 你会放什么音乐？
<details><summary>Original English</summary>
>> What would you play?
</details>

>> 我不知道，放点颂钵音疗（sound bath）之类的音乐吧。
<details><summary>Original English</summary>
>> I don't know. I don't know some some some sound bath bathy kind of stuff.
</details>

>> 哈哈，好主意，来点 Brian Eno 的氛围音乐。
<details><summary>Original English</summary>
>> Oh, there you go. Yeah, some Brian Eno.
</details>

>> 没错，完全赞同。我太喜欢这个了。我给所有人快速总结一下：我们看到了 Reddit Proto，这是一款专为产品经理和设计师打造的原型工具，默认对内部公开，任何人都能查看，部署在内部云端，支持通过配置进行控制，连接到 Cursor，并配备了一个经过深思熟虑、经过审计与情境化设计的系统，整个脚手架通过一个自定义 MCP 访问该系统。
<details><summary>Original English</summary>
>> Exactly. Exactly. Um I love this. I just want to recap for everybody. Okay, so we saw Reddit proto, purpose-built prototyping tool for product managers, designers, public by default, anybody can open these, deployed sort of in your cloud, some controls via config, connection to um cursor, and then a really thoughtful, audited, and contextualized design system that's accessible to this whole harness via a custom MCP.
</details>

>> 总结得太精辟了。没错，这就是我们所做的事情。
<details><summary>Original English</summary>
>> Nailed it. Yeah, that That is what we do.
</details>

### 快问快答与结尾

>> 小菜一碟，轻轻松松。这真的很震撼，我的脑子现在都在飞速运转。我也要好好琢磨琢磨这套体系我能自己搭出多少，因为我认为这会彻底改变我对某些设计系统问题的思考方式。趁我还在回味，我们进入快问快答环节。如果你准备好了，第一个问题：最近在非工作、非原型的场景下——可能也算工作，但只要不是原型设计——有哪些你非常喜欢的 AI 使用案例？
<details><summary>Original English</summary>
>> No big deal. Easy peasy. Um this is really I just my my head is spinning. I'm going to swirl on like how much of this I think I can build because I think it would really change how I think about some of my um design system problems. As I noodle on this, let's go to some lightning round questions. Um if you're ready, one is just what are some non work, non-prototyping Maybe not non-work, but like what are some non-prototyping use cases that you're really loving AI for these days?
</details>

>> 在录这个播客之前，我正在为我们整个团队制作游戏卡牌。这上面画的人就是当初协助启动整个 Reddit Proto 项目的功臣。我们正在给团队里的所有成员制作“玩家卡牌”，卡牌背面印着他们所有的属性数据。这里面很棒的地方在于，你必须像导演一样去引导它，让它符合品牌风格，最后每个人都能实实在在地拿在手里。
<details><summary>Original English</summary>
>> Before this podcast, I was working on um I was working on making playing cards for the whole team. And so, this is like this is the person who who helped start the the whole Reddit proto uh project. And so, we're making a play like a players uh all the players on the team, and then you have like all their stats on the back. And what's nice about this is like you have to like direct this and get it into like brand, and um yeah, and then everybody will have it in their hand.
</details>

>> 确实，能制作出这种高质量的创意实体物品太有趣了。而且这些卡牌品质极高、超级可爱，风格也非常统一。你是用什么工具生成的？制作流程是怎样的？
<details><summary>Original English</summary>
>> I know. It's so fun to be able to make like creative physical goods that are high quality. I mean, again, and these are like very high quality, super cute, and and consistent. What What did you use to generate these? Like how did What was the process?
</details>

>> 我尝试了好几个地方。我先用我的 Bot，向它描述每个人，大致即兴发挥一下每个人的角色特征。然后我把这些输入给 Gemini。Gemini 本来可以表现得更好，但最终 ChatGPT 生成的插画效果最完美。接着我把它放进 Cursor 里，调用高端模型进行生成，并通过一个 Markdown 文件来管理 Prompt，确保所有卡牌都保持一致的美学风格。这套工作流程确实花了不少心思。
<details><summary>Original English</summary>
>> Yeah, so I I bounced around a bunch of places, um, but with my bots, I described everyone and I kind of just like ad-libbed. This is their like, you know, this is their persona. And then I actually took that I took that to Gemini. Gemini could have per performed better, but like, uh, ChatGPT ended up making the the illustration that was perfect. I took that into Cursor and generated on a high model. And then that used like a a markdown file to use the prompt that kept them all in the same aesthetic. Yeah, it was it was it was quite a workflow.
</details>

>> 太喜欢了，超级有才。在节目快要结束时竟然藏了这么一段干货满满的“How I AI”。好，最后一个问题，这是我必问每个人的常规问题：当你的 MCP 没有响应、当 Claude 开始固执己见，或者不管面对的是哪个 AI，当它不听使唤时，你的 Prompting 策略是什么？你如何让它重回正轨？
<details><summary>Original English</summary>
>> Oh, I love it. Super super genius. I mean, a hidden how I AI at the very very end of this episode. Okay, my my last question I ask everybody this. When your MCP is not replying, when Claude is being obstinate, well, you know, whoever it is. When AI is not listening, what is your prompting strategy? How do you get it back on track?
</details>

>> [轻笑] 我不会对它们大吼大叫，我知道有些人会这么做。我的做法是放一放，隔一天再说，并且我会把提示词写得更加模糊（get more vague）。我们都有带有项目和上下文的 Bot，我会跳出那个项目，从宏观层面去描述这件事情。就像一个电影导演一样，先列出所有事实，再说明全部意图。接着我再把这些内容拉回到项目中，此时它就拥有了足够的理解，能够将其应用到我们设定的目标上。本质上，就是做一个提供更宏观、更模糊而非过度具体的优秀导演。
<details><summary>Original English</summary>
>> So, [snorts] I don't yell at them. I know some folks do, uh, but what I do is I take a day and then I get more vague. And we all have like bots with like projects and context, and I pop out of a project and I describe the thing large. Yeah. Like, uh, like a movie director. So, here all the facts and then here is all the intents. And then and then I pull that back into the project and then it knows enough to apply it to what what our goals are. But essentially, I become a better director that is more vague, not specific.
</details>

>> 我很赞同。我常告诉很多人：减少对 AI 的过度提示（under prompt your AI）。这往往比事无巨细的提示词有效得多。这个建议太棒了，是我们之前从没听过的观点。Blair，今天的内容真的非常有趣，信息密度极高，给那些正在探索如何改进原型脚手架、思考为什么需要自建工具的团队带来了极多启发，也给那些希望更好地利用设计系统构建接近生产级代码的设计师和产品经理提供了很多思路。
<details><summary>Original English</summary>
>> I like that. I I do tell a lot of people just like under prompt your AI. It's It's a lot more effective than than over prompting. Uh, that's that's a good one. That's one we haven't heard yet. Well, Blair, this has been really interesting, very very dense, and I think a lot of great ideas for teams out there looking to think about how they can improve their own prototyping harness, why they might build their own, and even just designers and product out managers out there that want to get better at using design systems to build production-like code.
</details>

>> 太棒了。谢谢你邀请我，我们非常期待把这些新功能尽快送到用户手中。
<details><summary>Original English</summary>
>> Awesome. Yeah, thanks for having me. We're really excited to get these features in the users' hands.
</details>

>> 太棒了。我们在哪里可以找到你？大家能为你提供什么帮助？
<details><summary>Original English</summary>
>> Awesome. Well, where can we find you, and how can we be helpful to you?
</details>

>> 我在 LinkedIn 上。不在 LinkedIn 上的时间我都在亲近大自然、享受生活（touching grass）。如果你想来 Reddit 工作，欢迎随时在 LinkedIn 上联系我。如果你遇到了类似的难题，我也非常友好，很乐意帮助大家。
<details><summary>Original English</summary>
>> I'm on LinkedIn, and when I'm not on LinkedIn, I'm touching grass. If you want to work at Reddit, feel free to reach out to me on LinkedIn. If you got any puzzles like this, I'm also really friendly. I love helping folks.
</details>

>> 太好了。感谢参加《How I AI》。
<details><summary>Original English</summary>
>> Amazing. Well, thanks for joining How I AI.
</details>

>> 谢谢。
<details><summary>Original English</summary>
>> Thanks.
</details>

>> 非常感谢大家的观看。如果你喜欢本期节目，请在 YouTube 上点赞并订阅，或者在评论区留下你的想法。你也可以在 Apple Podcasts、Spotify 或你常用的播客应用中收听本节目。请考虑为我们留下评分和好评，这能帮助其他人发现这个节目。你可以在 howiaiipod.com 查看我们所有的往期节目并了解更多信息。我们下期再见！
<details><summary>Original English</summary>
>> Thanks so much for [music] watching. If you enjoyed the show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. [music] You can see all our episodes and learn more about the show at howiaiipod.com. See you next time.
</details>