---
author: How I AI
date: '2026-05-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hQFEAZK__q0
speaker: How I AI
tags:
  - internal-tools
  - design-prototyping
  - ai-in-design
  - design-systems
  - product-development
title: Stripe内部AI工具变革产品设计流程：ProtoDash Studio实践分享
summary: Stripe设计经理Owen Williams在本期播客中分享了他们如何利用内部AI工具**ProtoDash Studio**彻底改变产品设计流程。该工具结合了Stripe的设计系统和AI能力，使得设计师和产品经理能够快速创建高保真原型，有效解决了传统设计工具在数据看板、多状态和复杂交互原型制作上的痛点。ProtoDash Studio不仅提升了设计效率和协作质量，还赋予了更多非设计师参与原型构建的能力，推动了内部工具在优化工作流程中的巨大价值。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Owen Williams
  - Claire Vemp
  - Dan Nelson
  - Ryan
  - Sera
companies_orgs:
  - Stripe
  - Celigo
  - Data Bricks
  - PayPal
  - Ollipop
  - Launch Darkly
  - Shopify
  - OpenAI
  - Figma
products_models:
  - Vzero
  - Cursor
  - Claw Code
  - ProtoDash
  - ProtoDash Studio
  - Celigo Aura
  - Radar
media_books: []
status: evergreen
---
### 介绍ProtoDash

**Owen Williams**: 我的梦想是，我想要一个像 **Vzero** 但速度很快的东西。我们内部有所有这些非常酷的工具。我们可以将不同的数据源连接在一起。为什么我不能直接在浏览器中做到这一点？我为什么需要 **Cursor**？

<details>
<summary>Original English</summary>

**Owen Williams**: My dream was I want something that's like **Vzero** but fast. We have all of these tools internally that are really cool. We can connect different data sources together. Why can I not just do this in my browser? Like why do I need **Cursor**?

</details>

**Claire Vemp**: 你看到很多设计师在使用它，但可能更多的是产品经理（PMs）。

<details>
<summary>Original English</summary>

**Claire Vemp**: You're seeing a lot of designers use it but maybe even more PMs.

</details>

**Owen Williams**: 我开始看到产品经理（PMs）使用它，然后有点紧张。天哪，产品经理们在设计。这会发生什么？原型化一个数据仪表盘有多痛苦？它包含了所有的交互、所有的过滤器、所有的状态、不同的状态、零数据、大量数据。在 **Figma** 中几乎不可能做到这一点。

<details>
<summary>Original English</summary>

**Owen Williams**: I started seeing PMs use it and got a little nervous. Oh my goodness. PMs designing. It's like what's going to happen? is that how painful is it to prototype a data dashboard with all its interactions, all its filters, all its states, different states, zero data, a bunch of data. It is nearly impossible to do that in **Figma**.

</details>

**Claire Vemp**: 这有点像一个非常具有变革性的东西，因为突然之间我坐在这些设计评审会议上，它非常有说服力，以至于我在想，这是真正的产品还是我正在看一些假的东西？

<details>
<summary>Original English</summary>

**Claire Vemp**: It's sort of been this very transformative thing because all of a sudden I'm sitting in these design reviews and it's so convincing that I'm like, is this the real product or am I looking at something fake?

</details>

**Claire Vemp**: 欢迎回到《How I AI》。我是 **Claire Vemp**，产品负责人和AI痴迷者，肩负着帮助你们更好地利用这些新工具进行构建的使命。今天我请到了 **Stripe** 的设计经理 **Owen Williams**，他将向我们展示他是如何为他们内部的设计原型“vibe code”了他自己的“vibe coding”平台。这是我见过的最令人印象深刻的内部工具之一，也是重新思考你的产品如何用工具构建产品的绝妙方式。让我们开始吧。本集由 **Celigo** 赞助。如今，每家公司都希望AI能改进工作方式。最快的方法是将其直接构建到日常业务流程中，自动化员工入职、保持客户数据准确、管理订单和库存，或解决财务和运营问题。当AI存在于工作流程中时，它可以在各个系统中更新记录、触发审批、分配工作并启动下一步。这就是团队如何将AI投入运营并带来可衡量成果的方式。**Celigo** 使这成为可能。现在有了 **Celigo Aura**，这从未如此简单。**Celigo Aura** 让你通过自然语言访问整个平台，连接你的系统并将意图转化为行动。所有这些都在你的掌控之下。像 **Data Bricks**、**PayPal** 和 **Ollipop** 这样的公司依赖 **Celigo** 来大规模运行关键业务运营。准备好将AI投入运营了吗？请访问celigo.com/howiAI。**Owen**，感谢你加入《How I AI》。

<details>
<summary>Original English</summary>

**Claire Vemp**: Welcome back to How I AI. I'm **Claire Vemp**, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have **Owen Williams**, design manager at **Stripe**, and he's going to show us how he vibecoded his own vibe coding platform for their internal design prototypes. It is one of the most impressive internal tools I have seen and such an awesome way to rethink how your product builds products with tools. Let's get to it. This episode is brought to you by **Celiggo**. Every company today wants AI to improve how work gets done. The fastest way is building it directly into everyday business processes, automating employee onboarding, keeping customer data accurate, managing orders and inventory, or resolving finance and operations issues. When AI lives inside the flow of work, it can update records, trigger approvals, route work, and kick off the next step across systems. That's how teams operationalize AI and deliver measurable results. **Celigo** makes this possible. And now with **Celigo Aura**, it's never been easier. **Celiggo Aura** gives you access to the entire platform through natural language, connecting your systems and turning intent into action. All of it under your control. Companies like **Data Bricks**, **PayPal**, and **Ollipop** rely on **Celigo** to run critical business operations at scale. Ready to operationalize AI? Visit celigo.com/howiAI. That's celi g.comhow i aai. Oh, and thanks for joining how I AI.

</details>

**Owen Williams**: 嘿，我很高兴来到这里。

<details>
<summary>Original English</summary>

**Owen Williams**: Hey, I'm happy to be here.

</details>

**Claire Vemp**: 我知道你抽出几分钟时间，从你的第二个孩子的育儿假中来。所以，我感谢你给我们时间。我喜欢你将要向我们展示的是，我们之前在录制前开玩笑说，如何制作那些看起来不像通用 **Tailwind** 靛蓝“slop”的原型。那么告诉我，你面临的问题是什么，以及你是如何得出这个解决方案的。

<details>
<summary>Original English</summary>

**Claire Vemp**: I know that you're stepping away for a few minutes from parental leave with your second. So, I appreciate you giving us the time. And what I love about what you're going to show us is how to we were joking before we started recording. How to get prototypes that don't look like generic **Tailwind** indigo slop. So tell me about tell me the problem you're facing and kind of how you came to this solution that you came to.

</details>

**Owen Williams**: 我是一名设计经理。所以，我参加了很多设计评审会议，现在 **Stripe** 的所有设计师都在玩这些工具。他们正在探索。他们正在尝试，我认为 **Vzero** 在内部非常受欢迎。我们有许多其他工具，他们坐在那里尝试用这些工具构建 **Stripe** 的体验。就像你说的，他们最终得到了这种奇怪的“恐怖谷”效果，像 **Tailwind**，我们内部称之为靛蓝模糊。所以，我会称之为模糊“slop”。他们做得非常好，但他们不了解你的设计系统，对吗？

<details>
<summary>Original English</summary>

**Owen Williams**: You know, I'm a design manager. So I'm I'm sitting in a lot of design reviews and all of the designers at **Stripe** right now are like playing with these tools. They're exploring. They're like, you know, trying I think, you know, **Vzero** is pretty popular internally. We have a bunch of other them uh different tools and like they're sitting there like trying to build the **Stripe** experience in these tools and kind of like what you're saying, they end up with this like weird uncanny valley like **Tailwind** we call um like the Indigo like blur internally. So like blural slop is what I would call them. And like they do a really really good job but they don't know about your design system, right? So,

</details>

**Claire Vemp**: 是的。

<details>
<summary>Original English</summary>

**Claire Vemp**: y

</details>

**Owen Williams**: 我在这些设计评审会议上，我就在想，为什么仪表盘看起来很奇怪？它非常打破沉浸感。导航很奇怪，或者字体不对。对这些设计师没有恶意。我理解。但是我在想，我们有一个设计系统，这个东西非常可预测。这些工具应该了解它，然后我们就可以像通过这些构建块一样非常可靠地构建仪表盘。所以，我基本上最终开始了这项工作，我想说这可能已经有18个月了，像所有这些东西，一个“兔子洞”，内部构建了一个我们称之为 **ProtoDash** 的原型工具，大量的设计师都在使用它，然后实际上让我惊讶的是，现在产品经理比设计师更多地在使用它，这真的很有趣，我稍后可以更多地谈谈。它的作用是，它使获得一个仪表盘一样的环境，一个非常逼真的仪表盘变得非常容易，而无需过多考虑。所以，它基本上是一组 **Cursor** 规则。你知道，它是一堆 **React** 代码，用于设置导航和像浏览器界面以及一些路由，让你在框架中拥有原型，所有这些都意味着你可以跳入 **Cursor** 或 **Claw Code** 或任何地方，然后你可以说我想要用这个、这个和这个构建一个仪表盘页面，它就知道如何做得很好。我会说它在大多数时候能让你达到90%的程度。别误会我，它仍然会犯错误。它会制作“slop”，但它能让你达到90%，设计师就是为此而来的。他们是高水准的工匠。他们可以从那里进行改进。看到人们构建了什么真的很有趣。我可以向你展示几个例子，但它有点像是一个非常具有变革性的东西，因为突然之间我坐在这些设计评审会议上，它非常有说服力，以至于我在想，这是真正的产品还是我正在看一些假的东西？所以，这是一个很酷的变化。

<details>
<summary>Original English</summary>

**Owen Williams**: I'm in these design reviews and I'm like, why does the dashboard look weird? Like, it's very immersionbreaking. Like the nav is odd or like the fonts are off. And no, no foul to these designers. Like I I get that. Um, but I was kind of thinking like we have a design system like this thing is very predictable. These tools should know about it and then we can like construct the dashboard from those bu building blocks like pretty reliably. Um, so I basically ended up starting on this like I would say it's been maybe 18 months now um rabbit hole like all of these things um building a prototyping tool internally that we call **ProtoDash** and um a large number of designers are using it and then actually the thing that surprises me is it's actually more PMs than designers these days um which is really interesting and I can talk about that a bit more later and what it does is it makes it basically like really easy to get a dashboard like environment like a very realistic dashboard um without having to think about it much. Um so what it is is it's basically like a bundle of **Cursor** rules. It's you know a bunch of **React** that like sets up the navigation and the like chrome and some routing to like let you have the prototype in the frame and all of those things mean you can like jump into **Cursor** or **Claw Code** or whatever and you can be like I want to build a dashboard page with this this and this and it like knows how to do a pretty good job. I would say like it gets you there like 90% of the way most of the time. Don't get me wrong, it still makes mistakes. It will make slob, but it gets you, you know, 90% and like, you know, designers, that's what they're here for. Like that they are high craft. They can like then refine it uh from there. And it's been really interesting to see what people have built. Like I can show you walk you through a couple of examples, but it's it's sort of been this like very transformative thing because all of a sudden I'm sitting in these design reviews and like it it's so convincing that I'm like is this the real product or am I looking at like something fake? And so that's kind of a cool change to see happening.

</details>

**Claire Vemp**: 我很好奇你是否可以向我们介绍一下这是谁构建的？是你构建的吗？你是怎么构建的？它的组成部分是什么？我知道你有 V1 和 V2 版本。所以也许你可以向我们介绍一下。

<details>
<summary>Original English</summary>

**Claire Vemp**: I'm curious if you just walk us through how who's who who built this? Did you build this? How did you build it? What are the components? And I know you had like V1 and V2. So maybe you can walk us through through that.

</details>

### 构建ProtoDash的经验

**Owen Williams**: 也许先介绍一下我的背景。我在 **Stripe** 领导开发人员相关领域，我的背景实际上是工程学。我实际上是朝着错误的方向转变的。我感觉对于一个设计经理来说，你通常会觉得是一个设计师，人们通常会走向另一个方向。我总是对我的角色有工程学倾向，我总是认为这是一种超能力。所以当我思考我的团队时，我实际上喜欢招聘我称之为技术设计师的人，他们通常在面试中就足够了解。我问他们是否觉得足够了解命令行以至于可以大胆操作？请注意，这是AI时代之前的事情。这总是让我兴奋，就是即使你不知道如何编码，但能够理解足够多的东西，让你自信地去摸索和实验。这总是赋予设计师超能力。

<details>
<summary>Original English</summary>

**Owen Williams**: Maybe like some context on me actually. So I uh I lead the like developer sort of space at **Stripe** and my background is actually engine engineering based and I actually switched in the wrong direction. I feel like for a design manager you feel like a designer usually people go the other way. Um I always had like an engineering slant to my roles and I always kind of considered it a superpower. So when I would think about like my teams, I actually loved hiring kind of technical designers I would call it where they understood enough often in the interviews. I'm like do you feel like you can uh you know know enough terminal to be dangerous? This is preAI just to be clear. Um and that was something that always got me excited is like even if you are I don't know like not able to code but able to understand enough to feel confident like messing around and experimenting. It always gave designers superpowers.

</details>

**Owen Williams**: 我要说的是，一直令人沮丧的是，我不知道用什么词来形容，达到那个技术水平真的很难，对于很多设计师来说，如果你没有深入研究Web开发，就会觉得，天哪，这是 npm，vite 是什么？这个东西是什么？等等。所以，我理解为什么很多人不知道如何做，现在AI完全改变了这一点，对吧？因为现在你可以直接跳进 **Cursor**、**Claw Code** 或任何地方，然后直接问：git 是怎么工作的？这实际上是我必须给设计师带来的最大心态转变，就是，a. 不再害怕命令行，b. 如果你觉得需要使用 npm，你可以直接问，你甚至不需要知道命令。所以，是的，凭借我的工程背景，我以一种非常务实的方式看待这个问题，我想，我如何才能降低入门门槛？我如何才能让设计师可能只需要知道 `npm run dev` 就可以了，而它就能正常工作？他们不需要了解 **React** 或 **React Router** 或任何这些东西。所以，第一个版本是一个非常基础的东西，它是一个路由器，一堆我们的设计系统组件，我们的设计系统叫做 **Sale**，然后它与 **Sale** 有一个 **MCP** 集成，所以内部有一个 **MCP** 服务器，然后只是一堆规则，我会很快展示出来。

<details>
<summary>Original English</summary>

**Owen Williams**: The thing I'll say that was always frustrating is like that I don't know what the right word for this would be like the jump to that technical level is really hard like for a lot of designers like I don't know if you didn't steep yourself in web development it's like oh my god this is npm like what is vit what is this thing blah blah blah and so you know I get why a lot of people didn't know how now AI totally changed that right because now you can just like jump into **Cursor** core code, whatever, and just be like, how does git work? And that's actually been the biggest mindset shift I've had to like give designers is um a not being afraid of the terminal anymore, and b if you're like, I need to use npm, you can just ask like you don't even need to know the commands. And so, yeah, with my engineering background, I was sort of looking at the problem in a very pragmatic way where I was like, how can I lower the barrier to entry on this? like how can I make it that uh a designer maybe only needs to know about mpm rundev and that's it and it just works like they don't have to know about **React** or **React Router** or any of these things um so the first version was a very basic like uh you know it's a it's a router it's a bunch of our design system components so our design system is called **Sale** and then it was a **MCP** integration with **Sale** so there's an **MCP** server internally for that and then just like a bundle of rules that I'll flash up really quickly. So

</details>

**Owen Williams**: 是的，当你跳到 **Cursor** 时，会有一堆捆绑的规则，这些规则基本上教 **Cursor** 如何使用项目以及按什么顺序做什么。所以，如果用户粘贴一个 **Figma** 链接，你应该在编写任何代码之前检查 **Sale MCP** 服务器。然后，我不知道，有一些常见的痛点和它应该避免的事情，如果 **MCP** 服务器不可用它应该做什么。大型语言模型（LLMs）是如此有用，它们会在不存在设计系统时，不告诉你就能想象出整个设计系统。所以所有这些事情，你知道，我通过各种实验，逐渐摸索出来。这意味着设计师、产品经理或任何人都可以非常快速地在 **Cursor** 中打开这个文件夹，然后说“帮我制作一个显示这个的原型”，然后它就能呈现出我们期望的精美和质量。像 **Stripe** 对我们所有的体验都有很高的质量标准。还有一点，如果你带着一个看起来很糟糕的真实原型去参加这些评审，那简直是，“我们肯定能做得更好。”所以这正是它所帮助的。

<details>
<summary>Original English</summary>

**Owen Williams**: yeah, when you when you would jump to **Cursor**, there would be a bunch of bundled rules that basically taught **Cursor** how to use the project and like what to do in what order. So like if a user pastes a **Figma** link, you should, you know, check the **Sale MCP** server before writing any code. And then like I don't know, there's some common like pain points and things it should avoid, what it should do if the **MCP** server is unavailable. LLMs are so helpful. they will just like imagine the entire design system without telling you when it's not there. So like all of these things, you know, I'd like sort of whittleled down through my various um experiments. And this means that like a a designer or a PM or anybody can very quickly like open this folder in **Cursor** and just be like help me make a prototype that shows this and it just comes out like beautiful and to the quality bar that we expect. Like **Stripe** has a really high quality bar for all of our experiences. And that's the other thing. It's like you're going to these reviews with a real prototype and it looks bad. It it's just like surely we can do better. And so that's what this sort of like helps with.

</details>

**Claire Vemp**: 但是看这个，这是人们在本地运行的东西。所以他们把它拉下来，在本地运行，进行修改，然后在会议中，他们只是从自己的本地机器上展示吗？

<details>
<summary>Original English</summary>

**Claire Vemp**: But looking at this, this is something that people are running locally. So they're pulling this, they're running it locally, they're making the changes, and then in the meeting, are they just presenting sort of off their local machine?

</details>

**Owen Williams**: 实际上是混合的。很酷的是，最初我们是本地运行的。你只需要运行 `npm run whatever`，但我们有 devbox 基础设施。我想你之前和 Minion 团队谈过，所以你可能听说过。

<details>
<summary>Original English</summary>

**Owen Williams**: So it's a mix actually. What's really cool is um so initially we had like it was running locally. You would just like run `npm run whatever` but we have devbox infrastructure. I think you talked to the minion folks previously so you probably heard about that. Um

</details>

**Claire Vemp**: 所以像 dev boxes 在高层次上只是让你在内部以某种状态在互联网上获得一个服务器。

<details>
<summary>Original English</summary>

**Claire Vemp**: and so like dev boxes at a high level just let you just get a server on the internet in a certain state internally.

</details>

**Owen Williams**: 现在设计师只需要访问一个URL，比如 go/protodash，它就会创建一个 devbox。两分钟内就能准备好。他们所要做的就是把它连接到 **Cursor**。所以它看起来像是在本地运行，但实际上不是。它已经配置好了，他们甚至不需要运行 npm。这实际上是我最喜欢的魔术，因为它就是能用。所以这些的好处是你得到了一个URL。这样你就可以在设计评审中说“只要去这个URL”，而且我可以说，在设计评审中可以点击东西是我最喜欢的。我喜欢设计评审。我是一个非常喜欢窥探别人工作的人。但在过去五年里，它一直被淹没在演示文稿中，对吧？比如在你的 **Figma** 中给我看一个 JPEG，所有这些东西。当有人过来，说“好，我不再分享屏幕了。这是我的原型。这是背景。我们来过一遍，然后给出反馈。”能够做到这一点一直是我最重要的目标，就是我再也不想看到幻灯片了。**Stripe** 的另一位设计领导 **Dan Nelson** 经常说“演示而非备忘录”，我觉得这就是我们能做到的方式。

<details>
<summary>Original English</summary>

**Owen Williams**: Um so now designers can just go to a like URL. It's like go/protodash and it just creates one. It's like ready to go in two minutes and all they have to do is like just connect to it in **Cursor** and so it looks like it's running locally. It's not. It's already configured. They didn't even have to run npm. That's actually like my favorite magic trick is it just works. Um and so those like the benefit of those is you get a URL. And so you can be in the design review and be like just go to this and like can I just say being in a design review where I can click things is my favorite. Like I I love design reviews. I'm a very like nosy person who loves seeing what people are working on those kinds of things. But like for maybe the last five years it's been like drowning in presentations, right? Like show me a JPEG in your **Figma**, like all of these things. And it's like how magic is it when somebody comes and they're like, "Okay, I'm not going to screen share. Here's my prototype. Here's the context. Let's just like go through it and give feedback." And so being able to do that has been like the probably my number one goal is like I never want to see a slideshow again. It's like demos not memos is something that uh **Dan Nelson**, another design leader at **Stripe**, talks about a lot and I'm like this is the way that we can do that. So

</details>

### 数据驱动原型的重要性

**Claire Vemp**: 我觉得这很有趣，特别是对于像 **Stripe** 这样的产品，它是一个非常数据和可视化密集的产品。我以前在 **Launch Darkly** 的设计团队中就说过，两年前当AI和这种原型设计真正兴起时，我说，原型化一个数据仪表盘有多痛苦？它包含了所有的交互、所有的过滤器、所有的状态、不同的状态、零数据、大量数据。

<details>
<summary>Original English</summary>

**Claire Vemp**: what I think is interesting about this, especially for a product like **Stripe**, is it's such a data and visualizationheavy product and I used to tell this to my design team at **Launch Darkly**, you know, two years ago when AI and this kind of prototyping was really coming out. I said, how painful is it to prototype a data dashboard with all its interactions, all its filters, all its states, different states, zero data, a bunch of data.

</details>

**Owen Williams**: 在 **Figma** 中几乎不可能做到。

<details>
<summary>Original English</summary>

**Owen Williams**: It is imp nearly impossible to do that in **Figma**

</details>

**Claire Vemp**: 而且我们正在构建大量的仪表盘，作为设计师来说，这是一种很棒的体验，你知道，我正在看你的仪表盘，如果你不介意的话，把它拉上来。

<details>
<summary>Original English</summary>

**Claire Vemp**: and we were building a lot of dashboards and what a great kind of experience as a designer to, you know, I'm looking at your your dashboard if you don't mind pulling it up.

</details>

**Owen Williams**: 是的。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah,

</details>

**Claire Vemp**: 这家公司做得还不错。你知道，我们喜欢那近五十万美元的总交易额。

<details>
<summary>Original English</summary>

**Claire Vemp**: this is a company that's not doing too bad. you know, we love that almost half a million dollars in gross volume,

</details>

**Owen Williams**: 但是如果你想要零状态呢？如果你想要，你知道，只有一天一笔交易的公司呢？

<details>
<summary>Original English</summary>

**Owen Williams**: but what if you want the zero state? What if you want the, you know, the company with

</details>

**Claire Vemp**: 没错。

<details>
<summary>Original English</summary>

**Claire Vemp**: one transaction a day?

</details>

**Owen Williams**: 完全正确。所以我觉得设计师能够在代码中用数据进行原型设计，既能让你制作更有趣的原型，又能让你推动底层数据和用例的边界，使其更实用。没错。以前，即使只是，我不知道，要将所有各种状态放入 **Figma** 文件中，所需的工作量简直是令人发指。即使你考虑国际化，这也是其中之一。这也是我最喜欢的一点。

<details>
<summary>Original English</summary>

**Owen Williams**: Exactly. And and so I think the ability to prototype with data in code as a designer both lets you make more interesting prototypes and lets you push the edges of the underlying data and use cases to make it more practical. Well, that's it. And like before it was like even just I don't know the amount of effort it would be to get all the various states into a **Figma** file was just like unhinged. Even like if you think about internationalization is one of them. That's my favorite as well.

</details>

**Claire Vemp**: 就像，哦，现在是荷兰语了。好吧。它看起来很糟糕，因为它又长又乱。

<details>
<summary>Original English</summary>

**Claire Vemp**: It's like oh it's in Dutch now. Okay. It looks terrible like cuz it's all long and stuff.

</details>

**Owen Williams**: 或者商业模式是我痴迷的一个。我可以很快地展示出来，你可以非常迅速地说我想看到一个初创公司在一个企业中，它就能做到。

<details>
<summary>Original English</summary>

**Owen Williams**: Or the business model is the one that I'm obsessed with. I can actually flash this one up really quickly where you know you can just very quickly be like I want to see a startup in an enterprise and it just it just does it.

</details>

**Claire Vemp**: 我喜欢这个。

<details>
<summary>Original English</summary>

**Claire Vemp**: I love that.

</details>

**Owen Williams**: 你可以在这里再添加一个，比如“混乱的数据”，它就能做到。我认为这就是变革性的地方，就是“向我展示真实用户会如何看待这个”是直到最近都非常困难的事情。

<details>
<summary>Original English</summary>

**Owen Williams**: You know you could add an additional one here that's like messy data and it will just do it. And I think that's the transformative thing is like show me how real users will see this is something that was really hard until recently.

</details>

**Claire Vemp**: 呃，我不想暴露年龄，但我喜欢告诉人们我以前要如何跋山涉水才能到我的 CSS。

<details>
<summary>Original English</summary>

**Claire Vemp**: Well, and I don't want to show my age, but I like to tell people when I used to have to walk uphill both ways to my CSS, like,

</details>

**Owen Williams**: 对。

<details>
<summary>Original English</summary>

**Owen Williams**: right,

</details>

**Claire Vemp**: 以前有个小作坊，专门做 Lorem Ipsum 文本生成器。

<details>
<summary>Original English</summary>

**Claire Vemp**: there used to be a cottage industry of um Lauram Ipsum text generators

</details>

**Owen Williams**: 只是为了放一些假文本进去。

<details>
<summary>Original English</summary>

**Owen Williams**: just for putting even just fake copy in.

</details>

**Claire Vemp**: 这就像我还在 **Photoshop** 中做网页设计的时候。所以你知道，我只是…

<details>
<summary>Original English</summary>

**Claire Vemp**: This is like when I was making web designs in **Photoshop**. So right you know and and I just

</details>

**Owen Williams**: 那些日子。

<details>
<summary>Original English</summary>

**Owen Williams**: those were the days

</details>

**Claire Vemp**: 你们这些设计师，如果你们没有经历过这些，你们不知道自己有多幸运。

<details>
<summary>Original English</summary>

**Claire Vemp**: you do not know designers out there please if you have not experienced this you do not know how spoiled you are that you can

</details>

**Owen Williams**: 我有一段时间没见过 Lorem Ipsum 了。

<details>
<summary>Original English</summary>

**Owen Williams**: I have not seen Lauram Ipsum in a while I'm

</details>

**Claire Vemp**: 很长一段时间了。我以前是 Lorem Ipsum 的用户，后来我开始用 Hipster IPS，那是在它最终结束的时候。

<details>
<summary>Original English</summary>

**Claire Vemp**: a long time I used to be a Lauram Ipsum I use hipster IPS that was like when finally ended

</details>

**Claire Vemp**: 但我以前不得不把那些东西粘贴进去。你会写 `$$$` 的价格，你会写 `10 xxx`，因为你不知道要在仪表盘里放多少假的金额。你不断地拖拽和复制相同的组件。而我现在只是觉得，通过这种实时原型设计的变革，你可以设计出更有趣的东西，并让它们更快地触及现实，这正是我们都想要的。

<details>
<summary>Original English</summary>

**Claire Vemp**: um but I used to have to paste that stuff in you would do dollar dollar prices you would be like10 xxx because you didn't know what the fake dollar amount is you to put in a dashboard. You were dragging and copying the same components. And I just think now with this this transformation in terms of live prototyping, you can design more interesting things and, you know, have them touch reality a little sooner, which is what we all want.

</details>

**Owen Williams**: 是的。而且还有多步骤流程，对吧？通常你只是展示一个 JPEG，也许第二个 JPEG 就像“这是这个，一切都很好”，但是错误状态是什么？你还能在页面上做什么？对吧？我参加的所有设计评审中，他们都会问“那个按钮是做什么的？”而他们只是坐在那里，这没什么，但现在我们实际上可以构建出经过深思熟虑的东西，页面上的所有东西都非常有意图，并且也向你展示了路径，对吧？就像你通常在 **Figma** 文件中需要做的工作量。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. And also like the multi-step flow is the other thing, right? It's like often you're just showing like there's one JPEG and maybe a second one where it's like here's this and this everything's great, but like what are the error states? Like what other things can you do on the page? Right? Like I'm in all these design reviews where they're like what does that button do? and they're like just there and that's that's okay, but it's also like now we can actually build stuff that's just really like well thought through and like everything that's there is very intentional um and like shows you the path as well, right? Like the amount of work you have to do in a **Figma** file often to like

</details>

**Owen Williams**: 我不知道，如果我想到像工作流构建器这样的东西，你必须获取登录页面，然后是任务和工作流构建器，然后是编辑。实际上我只想展示最后一点，但你需要上下文。现在我们可以连接原型，并重复使用你已经拥有的部分，顺便说一下，因为它都在生产中。它看起来大部分都是一样的。然后你就可以玩它，并一次性地把它全部排序出来，这真的很酷。

<details>
<summary>Original English</summary>

**Owen Williams**: I don't know if if I imagine something like a workflow builder, it's like you have to get the landing page and then like the job and the workflow builder and then the edit. It's like actually I only wanted to show the end bit but you need the context. Well, now we can wire up a prototype and like reuse the bits once you've got them, by the way, because it's all in production. It mostly looks the same. Then you can like play with it and like really sequence it all out at once, which is really cool.

</details>

**Claire Vemp**: 好的，让我们回到原型构建器。所以你构建了这个 **React** 应用程序，它可以在本地运行，也可以在这些 dev box 中运行，但后来你决定更进一步。

<details>
<summary>Original English</summary>

**Claire Vemp**: Well, and let's get back to the prototype builder. So, you built this, you know, **React** app that could run either locally or in these dev boxes, but then you decided to take it a step further.

</details>

### ProtoDash Studio的诞生

**Owen Williams**: 是的。所以我想，我看到的最大挑战是，我们有一个非常庞大的单体仓库，让它在你的笔记本电脑上运行有点麻烦，**Cursor** 和 **Claw Code** 以及所有这些工具让它变得容易很多，但它有点慢。它有点烦人，就像你之前提到的，你也不能很轻易地分享URL，诸如此类。我能分享另一件事吗？我可能会猜测，当你是一名公司的软件工程师时，你会得到一个像18英寸 **MacBook Pro** 巨兽，可以在本地运行任何东西。而设计师并不总是能得到这样的机器。所以我觉得这是另一个障碍。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. So I think like the biggest challenge that I've seen so like just to just to level with you is we have a like very large monor repo and it's like getting that running on your laptop is a little fiddly and like **Cursor** and **Claw Code** and all of these tools make that a lot easier but it's like a little bit slow. It's like a bit annoying and like you alluded to earlier you also like I don't know you you can't share the URL very easily like those kinds of things. Can I share one other thing? I I might hypothesize, which is when you're a software engineer in a in a in a company, you get issued the like

</details>

**Claire Vemp**: 18寸 **MacBook Pro** 巨兽可以本地运行任何东西。而设计师并不总是能得到这台机器。所以我认为这是另一个障碍。

<details>
<summary>Original English</summary>

**Claire Vemp**: 18inch **MacBook Pro** behemoth that can run anything locally. And designers don't always get the machine. And so I think that's another barrier.

</details>

**Owen Williams**: 是的，我很庆幸我们做对了。我想一年半前当这种情况开始发生时，设计师在许多方面被内部视为工程师。据我所知，我相信所有设计师现在都得到了强大的 **MacBook Pro**。我想我现在的机器是64GB的，我不能说我在任何其他工作中拥有过这样的机器。他们会说：“哦，你打开 **Figma**，你可以有10GB内存。”

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah, that's something I can I just say uh we thankfully got right. Like I think when this started happening a year and a half ago, um designers started being considered like engineers in many ways internally and uh I as far as I remember I believe all designers are now getting like the meaty **MacBook Pro**. Like I think I'm on like a 64 gig machine right now which is like I can't say that I've had that at any other job. They're like, "Oh, you open **Figma**, you can have 10 gigs of RAM." Like

</details>

**Claire Vemp**: 是的，祝你好运。

<details>
<summary>Original English</summary>

**Claire Vemp**: yeah, good luck.

</details>

**Owen Williams**: 我喜欢它。我叫它“大男孩”。

<details>
<summary>Original English</summary>

**Owen Williams**: I I love it. I call mine um big boy.

</details>

**Claire Vemp**: 是的。我告诉我的。

<details>
<summary>Original English</summary>

**Claire Vemp**: Yeah. And I tell my

</details>

**Owen Williams**: 这本书是。

<details>
<summary>Original English</summary>

**Owen Williams**: the chunk book is

</details>

**Claire Vemp**: 是的，“大块头”。我喜欢，“你能帮我拿一下大男孩吗？”

<details>
<summary>Original English</summary>

**Claire Vemp**: yeah chunk I like can you go grab me big boy and

</details>

**Owen Williams**: 是的。好吧，所以，有很多挑战，要在一个大型的单体仓库在本地运行。那么你做了什么来解决这个问题？

<details>
<summary>Original English</summary>

**Owen Williams**: yeah top okay so so um lots of challenges with running you know big monor repo locally I so what did you what did you do to solve that problem

</details>

**Owen Williams**: 所以我想要的是，我的梦想是，我想要一个像 **Vzero** 一样，但对我们来说速度很快的东西，一个非常有主见的工作流程，用于构建基于 **Stripe** 的原型。我知道这非常具体，但就像，你知道，我们内部有所有这些非常酷的工具。你知道，我们可以将不同的数据源连接在一起。为什么我不能直接在浏览器中做到这一点？我为什么需要 **Cursor**？所以，我采用的框架是，好的，我有一个非常酷的 **React** 网站模拟器，或者说原型工具。我能否以某种方式封装它，让你仍然可以使用 **Cursor**？那些人在 LLM 训练方面做得非常好，他们为你提供了所有的选项等等。但现在我希望能够在其上层构建一个东西，让你可以在浏览器中构建它。所以你不需要任何应用程序。我只想在网上说我想尝试这个东西。所以我最终构建了一个额外的层，叫做 **ProtoDash Studio**。它几乎100%在 dev boxes 中使用。所以你访问一个URL，它会创建它。大约需要一分钟，然后你就可以访问你的 devbox URL。我只是在本地运行它，以便今天能让直播演示顺利进行。但当你访问它时，你基本上每次启动它都会看到你正在处理的东西。所以你有了你的原型。我这里有一个有趣的，你可以通过奇怪的方式输入 **Stripe** 测试卡号。然后你还可以看到 vibe 原型设计反馈，因为我认为这所有一切最酷的另一件事是，你可以从其他人那里获取灵感，对吧？你可以看到他们在构建什么以及他们原型设计的方法。我看到的东西，我会在一分钟内向你展示一个真实的原型，一些设计师构建的。我想他们复制了我们 **Radar** 产品（欺诈检测产品）的全部功能，然后在 **ProtoDash** 中使用它来模拟不同的业务模型，就像你说的，但也尝试新想法，他们有一个非常酷的基线。但你能做的另一件事是，你可以随时混搭任何人的原型，对吧？我认为这就像 **Figma** 的优点，除了这个你可以获取代码，然后非常容易地开始玩他们的东西，这真的很酷。所以这里真正引人注目的东西不是主屏幕，我只是想谈谈它，你现在可以来到这里。所以，你知道，想象我们有一个这样的支付分析原型，你不必去打开我的 **Cursor** 窗口，然后在这里开始提示，然后希望它能设置好。你现在可以打开嵌入式 LLM，然后你就可以继续在那里工作。所以你可以说我想为我的原型添加一个新的变体，其中有一个聊天行图。你不需要在你的机器上做任何事情，你只是访问了一个URL，然后你要求它。它会在浏览器中完全构建它，这真的很酷。

<details>
<summary>Original English</summary>

**Owen Williams**: so what I wanted like my dream was I want something that's like **Vzero** but for us like a really opinionated workflow for like building **Stripe**based prototypes and I know that's like very specific, but it's like, you know, we have all of these tools internally that are really cool. Um, you know, we can connect different data sources together. Why can I not just do this in my browser? Like, why do I need **Cursor**? And so, the the framework I approached it with was like, okay, I have this really cool like **React** uh site emulator, I guess, or like prototyping tool. Could I wrap that somehow in a way where it's like you can still use **Cursor** if you want to? like those those folks are really good at like LLM training and like giving you all the options and blah blah blah, but like now I want to be able to layer on a thing where you can just build it in your browser. So you don't have to go into you don't need any app. I just want to like go on the web and be like I want to try out this thing. Um and so what I ended up building was this um sort of extra layer called **ProtoDash Studio**. And so this is like almost 100% used in dev boxes. So you go to like a URL, it creates it. It takes about like a minute and then you get to go to your devbox URL. I'm just running it locally so that like the live demo gods appease us today. But when you go to it, you basically whenever you spin it up, you see the things that you're working on. So you have your prototypes. I I have a fun one here where you get uh fun ways to enter like the **Stripe** test card number uh in weird ways. And then you can also see like the vibe prototyping feed cuz I think the other thing that's really cool about like the way that this is all going is one you can take inspiration from other people right you can see like what they're building and their approach to prototyping like the amount of stuff I've seen I'll show you a real prototype in a minute um uh that a bunch of designers built like I think they replicated the entire functionality of our **Radar** product the fraud fraud detection product in **ProtoDash** and then they used that to like emulate different business models like you say but also like try new ideas and like they have this really cool baseline but the other thing you can do is you can like remix anybody's prototype at any time right like I think that's something that's great about like **Figma** except with this you can take that like code and just like start playing with their thing really easily which I think is really cool so the really like the compelling thing in here was not so much the home screen I just wanted to talk about it is you can come in here now so You know, imagine we have this like payments analytics prototype instead of having to like go and open my **Cursor** window and like start prompting here and like hope that it's going to be set up now. You can just open the embedded LOM and you can just keep sort of start working there. So you can say I want to add a new variant of my prototype where there chat a line chat. You didn't have to like do anything on your machine. and you just went to a URL and you asked for it. Um, and it will go ahead and build it entirely in browser. Um, which is really cool.

</details>

**Claire Vemp**: 快问快答。人们会问这个问题。

<details>
<summary>Original English</summary>

**Claire Vemp**: Quick quick question. People are going to ask this.

</details>

**Claire Vemp**: 你是怎么构建的？你是怎么构建的？给我一点构建组件的小提示。

<details>
<summary>Original English</summary>

**Claire Vemp**: How did you build this? Like what is the give me like some like little sniff components of how you built this?

</details>

**Owen Williams**: 呃，大概是对着 **Claw Code** 咆哮了18个月吧。

<details>
<summary>Original English</summary>

**Owen Williams**: Um, like yelling at **Claw Code** for 18 months or something.

</details>

**Claire Vemp**: 好的，很好，就这样。

<details>
<summary>Original English</summary>

**Claire Vemp**: Okay, great. There you go.

</details>

**Owen Williams**: 嗯，这是一个混合体，我没有手写很多代码。我认为拥有工程背景让它得以实现，对吧？因为我知道我需要实现什么以及如何构建正确的架构。

<details>
<summary>Original English</summary>

**Owen Williams**: Um, it's a mixture like and I don't I I definitely handwrote some code but not much. Like I think having the engineering background made it work, right? Because I know what I need to achieve and like how to get the architecture right.

</details>

**Owen Williams**: 但很大程度上就像，好吧，我只是会一直做下去，看看我能走多远。它开始时是“我能做点什么让我能做到这一点吗？”，然后变成了“天哪，它成功了！我要继续添加功能。”实际上，构建这样一个内部工具的真正酷之处在于，它不需要达到生产级别，你懂我的意思吗？如果它坏了，也没关系。它不需要担心登录。它只是在你的 dev box 上运行，所以没问题。所以我的回旋余地可能比你发布到生产环境要大得多。但这只是一个尝试新事物、探索并看看我能走多远的问题。所以让我们看看。它正在添加一个变量，所以它应该很快显示出来。我认为对我来说真正酷的是看到这里出现了不同类型的用户。哦，它现在要自测了。

<details>
<summary>Original English</summary>

**Owen Williams**: But largely it was just like okay, I'm just going to keep going on this and see how far I can get. Um and it beca this started as a like could I make something that lets me do this and then became a oh my gosh it works. I'm just going to keep adding features. Um, and what's really cool actually about building a tool like this for like internal use is it doesn't have to be like production grade, you know what I mean? Like if it breaks, it's kind of fine. It doesn't need to worry about like login. Like there's, you know, it's just running on your dev box. So that's fine. And so I have a lot more leeway maybe than like if you were shipping to production. Um, but it just it was just a a matter of like trying new things and like exploring and just seeing how far I could get. And so let's see. It's It's working on adding a vera in here, so it should show up pretty quickly. And what's I think like been really cool for me to see is like seeing the different types of users that have shown up in here. Oh, it's going to self test now.

</details>

**Claire Vemp**: 太刺激了。

<details>
<summary>Original English</summary>

**Claire Vemp**: That's exciting.

</details>

**Owen Williams**: 这很刺激。

<details>
<summary>Original English</summary>

**Owen Williams**: This is exciting.

</details>

**Owen Williams**: 是的，通常如果它在 dev box 上，你不会看到这个，因为你实际上并没有连接到 dev box，但看着它运行也挺有趣的。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah, it uh so usually if it was on a dev box, you wouldn't see that cuz you don't actually connect to the dev box, but it's kind of fun to watch it drive.

</details>

**Claire Vemp**: 是的。

<details>
<summary>Original English</summary>

**Claire Vemp**: Yep.

</details>

**Owen Williams**: 所以，它正在截屏并检查自己的工作，我非常喜欢。这是一个非常酷的演示。

<details>
<summary>Original English</summary>

**Owen Williams**: So, it's taking a screenshot and checking its work, which I really love. Um, so this is like a really cool demo.

</details>

**Claire Vemp**: 你真的让 **Claw Code** 说“别犯错”。

<details>
<summary>Original English</summary>

**Claire Vemp**: You really let **Claw Code** make no mistakes.

</details>

**Owen Williams**: 是的。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah.

</details>

**Owen Williams**: 差不多吧，如果你想想我一开始说的，**Stripe** 非常重视质量，我们的质量标准非常高。我想，拥有一个非常有主见的构建这些原型的方式，意味着我们能做到这一点。所以，如果我发给它一个 **Figma** 链接，我说“实现这个”。

<details>
<summary>Original English</summary>

**Owen Williams**: Well, pretty much like if you think about I said at the top I was like **Stripe** really cares about like quality and our quality bar is really high. I think like having a really opinionated way to build these prototypes means that we can do this. So like if I

</details>

**Claire Vemp**: 别犯错。是的。

<details>
<summary>Original English</summary>

**Claire Vemp**: send it a **Figma** link, I'm like implement this make no mistakes. Yeah.

</details>

**Owen Williams**: 它至少能够看到原型，查看浏览器控制台，截屏并迭代它，直到它变得非常好，并且可以请求反馈。现在它完成了。我们这里有这个变体栏。所以你可以尝试不同的东西。这是我的折线图演示。瞧。它就像去切换了它。我认为能够非常快速地从你的浏览器中做到这一点非常酷。我什么都不用做。它就在那里。

<details>
<summary>Original English</summary>

**Owen Williams**: Um, it's able to like at least see the prototype, like look at the browser console, like take screenshots and like iterate on it to the point where it gets it pretty good and can ask for feedback. And so now it finished. We have this variant bar here. So you can like try different things. Um, so here's my line chart demo. Tada. It like went and swapped it out. And like I think it's pretty cool to be able to very quickly do that from your browser. Like I don't have to do anything. It's just there.

</details>

**Owen Williams**: 本集由 **Cursor** 赞助。如果你一直在看《How I AI》，你已经知道了。**Cursor** 是我最喜欢的用AI编码的方式。无论我是用计划模式构建雄心勃勃的功能，在编辑器中直接查看AI生成的差异，还是启动云代理来多线程处理我们的路线图，我都会选择 **Cursor** 作为我最喜欢的多模型编码平台。比自己用 **Cursor** 构建更好的是，我喜欢与 Bugbot 合作修复代码安全和质量的PR，并且已经开始依赖 **Cursor** 的自动化代理来保持我们的代码库干净。不只是我。最雄心勃勃的团队也喜欢 **Cursor**，包括 **Stripe**、**OpenAI** 和 **Figma** 的工程师。准备好构建更多了吗？我们为《How I AI》的听众提供50美元的 **Cursor** 积分。请访问chatpardd.ai/howiAI/howiAI 领取你的积分。那就是通过访问chatpprd.aii/howiAI 获得50美元的 **Cursor** 积分。

<details>
<summary>Original English</summary>

**Owen Williams**: This episode is brought to you by **cursor**. If you all have been watching How I AI, you already know this. **Cursor** is my favorite way to code with AI. Whether I'm using plan mode to build out an ambitious feature, reviewing AI generated diffs right in my editor, or kicking off cloud agents to multi-thread our road map, I reach for **cursor** as my favorite multimodel coding platform. Even better than building myself in **Cursor**, I love collaborating with Bugbot to fix PRs for code security and quality and have begun relying on **Curser's** automated agents to keep our code base clean. It's not just me. The most ambitious teams love **Cursor**, too, including engineers at **Stripe**, **OpenAI**, and **Figma**. Ready to build more? We're giving $50 in **Cursor** credit to How I AI listeners. Claim your credits at chatpardd.ai/howi. AI/howi AI. That's $50 in **cursor** credits by going to chatp prd.aii/howi aai.

</details>

**Claire Vemp**: 我喜欢这个。我确实想再次提醒大家，对于那些可能没有看到底部变体栏的人。**Claw Design** 中也有一个非常类似的功能。所以现在当你提示 **Claw Design** 创建一个原型时，它会问你想要多少种变体？作为一个在许多许多AB测试公司工作过，并创办过AB测试初创公司的人，我觉得“哦，我的时代终于来了，你知道，20年后。”

<details>
<summary>Original English</summary>

**Claire Vemp**: I love this. And I do want to just call out again for folks that maybe aren't watching this variant bar in the bottom. There's also a very similar feature in **Claw Design** of this. So **Claw Design** will now when you prompt it to create a prototype, it says how many variations do you want? as someone who like worked at many many AB testing companies and did an AB testing startup, I'm like, "Oh, my time had finally arrived, you know, 20 years later."

</details>

**Claire Vemp**: 但它会创建多个变体，让你选择。另一件我认为你可能想玩弄数据的事情是，它给你设计模式。所以你可以说“极致设计”，比如。

<details>
<summary>Original English</summary>

**Claire Vemp**: But it'll create multiple variants and let you select. The other thing that I think maybe you'll want to play you you kind of play with with data is it gives you um kind of like modes of the design. So you could be like extreme design like

</details>

**Claire Vemp**: 你让AI在设计系统上走多远，这可能是你会玩弄的东西，因为我认为这种原型工具的一个好处是，我以前绝不会这样设计，但这样也挺有趣的。

<details>
<summary>Original English</summary>

**Claire Vemp**: how far are you letting letting the um the AI go with the design system might be something you play with because one of the benefits I do think of um this prototyping tools and I'm curious what you think as a a designer that works on a very opinionated codebase is the happy accidents of I would have never designed that but that's kind of interesting.

</details>

**Owen Williams**: 是的。我认为你需要留有足够的余地，让这些时刻出现，因为我认为这是一个真正的好处。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. And you want to leave enough leeway, I think, for for those moments to come out because I think it's a real benefit.

</details>

**Owen Williams**: 是的，我想这就是让我兴奋的地方，你可以说“**Claude**，给我制作八个非常不同的变体”，它就会开始运作，然后你可以从每个变体中选取部分。这实际上是我想做的下一项任务，我想是构建一个类似“疯狂八分”模式的东西，它会吐出八个设计，然后你选择其中的部分。它对设计系统不那么严格。坦率地说，我最喜欢用它做一些傻事。比如我给你展示的这个4242模式。它就像，好吧，设计系统能做什么？我还有另一个原型，我在想，我能让表情符号在仪表盘中像下雨一样吗？我不知道。所以，但这里的意思是，如果你想继续推动它，你可以。另外，我们还内置了另一个功能，这就是主观性发挥作用的地方，你不必只使用我们的设计系统。所以在嵌入式工具中有一个小的规则选择器。你可以让 LLM 访问 **Tailwind**。我必须在设计系统规则中加入“不要使用 **Tailwind**，除非被告知”的刺耳规则，这实际上非常有趣。但如果你打开它，它就是一个预先主题化的设计系统版本。所以它有像“ride blur”之类的东西。然后你就可以说我想做一些生成性的东西，对吧？因为我认为设计系统的问题是你可以制作列表视图、图表之类的东西，但做一些全新的东西就更难了，所以它就是为此而存在的。另一个你可能已经看到的东西，它被称为“agentation”，我们有一个我们内部构建的版本。我不想说“哈哈哈，我们是第一个”，但也许我在这里会稍微得意一下。你还可以直接与画布互动，给 AI 反馈。所以想象一下，我们有一个带有许多图表的支付分析原型。你可以点击这个小的“anotype AI”按钮，然后切换到选择器模式，然后你可以说，我不知道，比如让这里的工具提示悬停时带有帮助文本。然后你就可以为 AI 添加一堆评论，让它直接在页面上修复。这是另一件事，我以前在 **Cursor** 中会抓狂，比如“请修复类名为 82F 的元素”，现在能够直接选择东西并给出反馈，然后让 AI 修复十条反馈，这真的很令人兴奋。所以，你知道，在这里给表格添加更多内边距。然后我就会把这个发给 AI，它就会处理它们，它会说“好的，这条评论，这条”，然后就完成了。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah, I think that's like where I get excited is you can just be like, **Claude**, make eight variants of this thing that are very different and like it will cook and then you can sort of like take bits from each of them. Um, that's actually something I kind of want to it's my next quest I think is building in like a crazy eights mode almost like it just spits out eight designs and you choose the pieces. It's not super rigid with the design system. In fact, frankly, like my favorite thing with this is just doing silly stuff. Like I I showed you this 4242 mode. It's like, okay, what can the design system do? I had another prototype where I was like, can I just make emojis rain in the dashboard? I don't know. Um so, um but like the idea there being like if you want to keep pushing it, you can. And then the other thing actually that we have built in, and this is where the opinionated part comes through, is you don't have to just use our design system. So there's a little like rules selector in the sort of embedded thing. You can like sort of grant the LLM access to **Tailwind**. Uh the amount of like shouty rules I have to have in the design system rule that's like do not use **Tailwind** unless you're told to is actually deeply amusing. But if you would turn that on, it's like a pre- themed version of our design system. So it's got like the ride blur and that kind of thing. And so then you can be like I want to do generative stuff, right? cuz I think the issue with the design system is it's like you can make list views and charts and like whatever but doing something net new is harder and so that's there for that reason. The other thing that I think you would have seen is it called agent agentation out there uh we have our like own version that we had built internally I don't want to be like ahaha first uh but maybe a little bit I will here where you can also like interact with the canvas directly to give the AI feedback. So imagine um you know we have this payment analytics prototype with a bunch of charts on it. Um you can click this little anotype AI button and swap into the like selector mode and be like I don't know uh let's say let's make the tool tip here hover hoverable with helper text in it. And then you can like I don't know add a bunch of comments for the AI to fix like right on the page. That's the other thing like I used to lose my mind in **Cursor** being like the element with class name 82F please fix this and being able to just select something and like give the feedback and then hit like like hawk 10 pieces of feedback to the AI to fix is really exciting. So you know add more padding to the table here. And so I'll send this off to the AI and it will just work through them like it'll it'll be like okay this comment this one um and like do that.

</details>

**Owen Williams**: 另外，在那之前你能做的事情，还有很多我想给你看。

<details>
<summary>Original English</summary>

**Owen Williams**: And the other thing that you can do before that there's so many things I wish I could show you.

</details>

**Claire Vemp**: 我不着急。

<details>
<summary>Original English</summary>

**Claire Vemp**: I'm not in a rush.

</details>

**Owen Williams**: 我喜欢。实际上你可以从那一步退回来。想象一下你正在进行设计评审，对吧？你正在展示一个原型，不同的公司有不同的传统，但在 **Stripe** 常见的是，你会分享你的屏幕，然后发送一个 Google 文档链接，里面有一个表格，就像“在我进行时给我反馈”，结果它变成了一个充满截图的垃圾场，试图解释这个东西。我们构建了一个设计评审模式。所以你可以跳入评论区。你可以点击“开始评审”，然后分享一个URL。然后大家都可以像普通人一样评论。

<details>
<summary>Original English</summary>

**Owen Williams**: I love it. Um is actually you can take a step back from that. Imagine you're like doing a design review, right? You're showing a prototype and at different companies there are different traditions, but something that's common at **Stripe** is you will like show you share your screen and then you'll like send a Google doc link with like a table at it that's like give me feedback as I go and it ends up being this like dumping ground of like screenshots and like trying to explain the thing. Something that we built was design review mode. So, you can jump into a comment section. You can click start review and then like share a URL. Um, and then like everybody can comment as like a normal human.

</details>

**Claire Vemp**: 哦，看。AI 终于把它弄坏了。

<details>
<summary>Original English</summary>

**Claire Vemp**: Oh, look. The AI broke it finally.

</details>

**Owen Williams**: 你知道吗？没关系。这只是内部工具。

<details>
<summary>Original English</summary>

**Owen Williams**: And you know what? It's fine. It's just internal tooling.

</details>

**Claire Vemp**: 我喜欢。它可能还会尝试自我修复，因为它能看到。就是这样。

<details>
<summary>Original English</summary>

**Claire Vemp**: I love it. Well, it's probably going to like try and self fix it because it can see it. This is the thing. Um,

</details>

**Owen Williams**: 它自己修复了。我现在要切换回评论功能。所以想象一下你想要进行设计评审。你会收到所有反馈，就像评论一样。这个过滤器怎么了。所以让我们试着想象一下，你想要参加一个设计评审。你把URL分享给会议室里的领导，然后你收到了反馈。你不需要 Google 文档。哦，看，我的评论发送了七次。没关系。所以你收到了设计领导的所有这些反馈，现在你想要回顾一下，并得到一个总结。我想。AI 在这方面非常擅长。在这种情况下，我不小心发送了很多次，但你会得到一个详细的设计评审总结在顶部。然后你实际上可以进入评审模式，逐步查看，然后说“这里的过滤器模式不对。请添加三个选项。”我不知道这是否现实，但无论如何。然后它会将其添加到队列中，你可以直接发送给AI来修复，就像设计评审结束后立即修复一样。它会说“我修复了 **Katie D** 的反馈，你可以把它发给她。”这就像我最喜欢的事情，对吧？因为设计师必须跟进。设计评审后有很多额外的繁琐工作要做，能够说“我修复了那个。这是收据”的帖子真是太棒了。

<details>
<summary>Original English</summary>

**Owen Williams**: there it goes. It self fixed it. I'm going to switch back to that commenting thing now. Uh so imagine you want to do a design review. Um you get all your feedback as like comments like what's um with this filter. So let's try and imagine you're like wanting to go to a design review. You share the URL with like the leaders in the room and you get, you know, your feedback. You don't want the Google doc. Um oh look, my comment did send seven times. That's fine. Um, so you get all these pieces of feedback from your design leaders and now you want to like go through and just like get a summary of it, I guess. So one AI is really good at that. So in this case, I accidentally send this a bunch of times, but you would get like a detailed summary of the design review at the top. And then you could actually enter like review mode and step through and be like, the filter pattern isn't right here. Please add three more options. I don't know if that's realistic, but whatever. Um, and then that will add it to a queue that you can just send to the AI to fix like straight off the back of the design review and it will be like, I fixed **Katie D's** feedback for you and you can send this to her. And it's like my favorite thing to just like right cuz designers have to follow up. Like there's all this extra busy work that you have to do after a design review and being able to be like, I fixed that. Here's the receipts thread is amazing.

</details>

**Claire Vemp**: 有一件事我需要说，作为你给我展示的这个东西的回顾性分析，就是，是的，我想很多人会看到这个，然后觉得“Vzero 已经足够好了，或者这个已经足够好了”，但我认为最有趣的是，你说得对，我领导过设计团队，我是一个特定类型的设计领导者。

<details>
<summary>Original English</summary>

**Claire Vemp**: One thing I I want to say as a sort of step back analysis of what you're showing me which is yeah I think a lot of people are going to watch this and be like man you know like **Vzero** is good enough or this is good enough and I I think what is so interesting is you are right I've led design teams I am a specific kind of design leader

</details>

**Claire Vemp**: 而且设计文化、评审文化、构建文化，公司与公司之间是如此不同，对吧，完全不同。你知道，我以前会组织一个叫做“产品工艺星期五”的活动。我希望每个人都能花三个小时来讨论我们正在构建的一切。

<details>
<summary>Original English</summary>

**Claire Vemp**: and design cultures review cultures building cultures are so different company to company yes right completely different um you know I used to run this thing called Product Craft Friday. I wanted three hours with everybody on what we were building across everything.

</details>

**Claire Vemp**: 然后我们会创建这些叫做“氛围检查”的东西，我们会把最新的作品都拖到 **Figma** 画板的一个地方。

<details>
<summary>Original English</summary>

**Claire Vemp**: And then we would create these things called vibe checks where we would all drag the most recent work into one spot in the **Figma** board

</details>

**Claire Vemp**: 然后看看它，说：“这些都看起来像是来自同一个产品吗？”

<details>
<summary>Original English</summary>

**Claire Vemp**: and then look at it and say, "Does this all look like it's from the same product?"

</details>

**Claire Vemp**: 因为很多时候它不是。

<details>
<summary>Original English</summary>

**Claire Vemp**: Because a lot of times it did not.

</details>

**Owen Williams**: 是的。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah.

</details>

**Claire Vemp**: 我觉得那不是任何人会构建的产品。它就像设计室里的“氛围检查”。但是。

<details>
<summary>Original English</summary>

**Claire Vemp**: And I think that is not a product that anybody's going to build is like the vibe check in the design room. But

</details>

**Owen Williams**: 他们可以，你只需要这样做。但后来你，我就像“你刚刚构建了它”。所以。

<details>
<summary>Original English</summary>

**Owen Williams**: and they can you can just do it. But then you I'm like you just build it. And so

</details>

### 内部工具的价值

**Claire Vemp**: 我认为人们现在真的低估了构建内部工具的价值。并不是说要取代你从外部购买产品的年收入。

<details>
<summary>Original English</summary>

**Claire Vemp**: I think people really underestimate the value of building internal tools right now. Not to as I said like replace the ARR of a product you would buy externally.

</details>

**Owen Williams**: 对。不是那个。它能如此精确地与你的团队文化和节奏相匹配，以至于它真的被使用了。对。你实际上得到了更高的质量。

<details>
<summary>Original English</summary>

**Owen Williams**: Right. It's not that. It's so it can be so precisely matched to the culture and cadence of your team that it actually gets used. Right. You actually get higher quality.

</details>

**Owen Williams**: 是的。就像，好吧，我们实际上可以用非常令人满意的方式微调我们的工作方式。就像，你知道，为内部工具团队配备人员一直都很困难。我以前有过几个这样的团队，**Stripe** 喜欢构建定制工具，但是要为像一个奇怪的设计评审工具之类的东西获取资源，以前是绝不可能发生的。而现在我们可以通过构建工具并把它们交给人们来完全改变我们的工作方式。我喜欢这个，因为虽然我一直在做这个，但我的整个想法是，任何人都可以贡献。如果设计评审有问题，我们就可以改进它。所以实际上我从设计师那里收到了惊人的多的拉取请求，我非常喜欢。这让我很高兴。我心想：“是的，你们应该改变文化。这就是我在这里试图做的。”所以我对这种事情感到兴奋，因为它赋予了人们力量，让他们觉得设计评审没有效果，就像我们能做什么，我不知道什么不存在但应该存在。我不想使用 Google 文档。我不想使用这个东西。所以它很相似，即使是那些使用这个的产品经理，你实际上可以做的一件事是，你可以直接把一个 PD 从 Google 文档中扔到聊天里，它就能访问 Google 文档。它知道怎么做，然后它就能接受它并构建它。我认为把入门门槛降低到如此之低简直是不可思议的魔力。很多人会说：“天哪，我被卡住了，因为我没有设计师。”通常，我是一个产品经理。我有一个产品经理，我们一起处理一些 **MCP** 相关的事情。这相对较新，所以我们还没有配备合适的人员。但是现在他可以以一种非常高质量的方式去探索事物。我们仍然会进行设计评审等等，但他可以自己解决问题，这也是一个全新的事情。我能说在这样一个非常公开的播客中，我开始做这个时感受到的第一个感觉是，我开始看到产品经理们使用它，然后有点紧张。天哪，产品经理们在设计。这会发生什么？但是实际上，看到他们拥有工具来正确地构建看起来像 **Stripe** 的东西，并且能够探索他们的想法，以及实际上也给他们提供了可视化工具来做这件事，这让我非常兴奋。我认为对产品经理来说最困难的事情是，他们通常无法将他们想要的东西具象化。这实际上让他们在与自己的设计师沟通方面做得更好，而且用户体验研究也完全不同。他们可以在漏斗的早期测试他们的想法，就像“我有一个想做的事情。好的，我怎么做呢？”我可以构建一个原型，然后去找一些用户，让他们点击它，而不需要一个带有交互区域的复杂 JPEG。所以，看到这种变化真的非常酷。我实际上觉得我现在喜欢产品经理用户了。起初我感到恐惧，但现在我觉得不，这让关系变得更好。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. It's like, okay, we can actually nudge the way that we work in really satisfying ways. Like, you know, staffing internal tools teams has always been hard, actually. Like, I've had a few of those teams and like **Stripe** loves building custom tools, but like getting resources to build a weird design review tool for like whatever would have never happened before. And now we can just like completely uh evolve the way we work by just like building tools and like giving them to people. And something that I love about this as well is like while I've been working on it, my whole thing has been like anybody can contribute. Like if if the design reviews thing is not right, like let's just evolve it. And so I I actually get pull requests from designers like a surprising amount and I I love it so much. It makes me happy. I'm like, "Yeah, you should just evolve the culture. Like that's kind of what I'm trying to do here." Um and so like I get excited about that kind of thing because it's it's very empowering to be like design reviews aren't working. like what could we I don't know what doesn't exist that should exist. I don't want to use Google Docs. I don't want to use this thing. And so um it's similar like even with the the PMs who are using this like something that you can actually do is you can just dump in a a PD into the chat from Google Docs and it just it can go and access Google Docs. It knows how to do that and like then it can take it and just build it. And I think like making that barrier to entry that low is just incredibly magic. like the amount of people who are like, "Oh my god, like I am blocked because I don't have a designer." Usually, like I'm I'm a PM. I have a PM I work with on um I don't know, let's say like **MCP** stuff. It's relatively new, so we haven't staffed it properly yet. Well, now he can like go and explore things in a really like high quality way. And we'll still design review it and all of that, but like he can unblock himself, which is like a whole new thing as well. Like I will I can I just say in the safety of this like very public podcast the the first feeling I had when I started making this was um I I started seeing PMs use it and got like a little nervous oh my goodness PM's designing. Uh it's like what's going to happen? Um, but it's actually just been thrilling to see like them having the tools to like build things that look like **Stripe** in the right way and like being able to explore their ideas and actually also give them the um like the visual tools to do it. Like I think the hardest thing for PMs is often they can't like manifest the thing that they want to. It actually makes them better at communicating with their own designer, but also UXR is completely different. like they can test their idea a lot earlier in the funnel where it's like I have this thing I want to do. Okay, how am I going to do that? I can build a prototype and like just go and talk to some users and make them click it without it being an elaborate JPEG with like interactive zones everywhere. So, it's it's really cool to see that changing. And I actually I think I love the PN user now. Like at first I had that terror and now I'm like no, this is like making the relationship better.

</details>

**Claire Vemp**: 我想，也许我还会再补充一点，那就是你的对话，我猜，更多地变成了“我们来谈谈工作和我的构建，以及如何让它变得更好”，而不是一直争论我们是否应该为 **MCP** 配备设计师，或者其他什么，这已经。

<details>
<summary>Original English</summary>

**Claire Vemp**: I you know maybe I'll add one more thing to that which is your conversations I'm guessing turn more into let's talk about the work and the thing I built and how can it be better than perpetual arguments over whether we should staff a designer on the **MCP** or something else which has

</details>

**Claire Vemp**: 这已经是我们生活的一部分了，就像有多少对话都围绕着谁应该参与项目，而不是实际的工作和我们来讨论这些，我确信这让每个人都特别。

<details>
<summary>Original English</summary>

**Claire Vemp**: been our life for like how many conversations are going to who should be on the project versus here's the actual work and let's discuss that and I'm sure that makes everybody especially

</details>

**Owen Williams**: 这也让他们更容易为其辩护，对吧？就像，好吧，这是我们目前系统能做的，但我们需要推动它，超越现在所能做到的。所以，看到这种对话也在改变真的很有趣。就像，嘿，这是我们现有的可以做到的，但我们需要一个设计师来帮助我们提升这种体验。所以，这也在让大家更容易地说同样的语言，另一点是，我在开发者体验领域从事非常技术性的工作，那里的东西非常密集，非常像我们一直在做的这个 webhook 项目，有七个步骤，已经一年了，非常复杂，有很多移动部件和状态等等。现在我们实际上可以全部展示出来，而不是试图解释 webhook 是如何工作的，以及所有这些不同的东西。所以，看到这种变化也真的很有趣。嗯，我们应该尝试快速构建一些随机的东西吗？

<details>
<summary>Original English</summary>

**Owen Williams**: just makes it easier for them to also advocate for it right? It's like, okay, this is what we can do with the current system, but like we need to we need to push it more and like go beyond what is just like capable now. And so it's it's been really interesting to see how that's like changing the conversation, too. It's like, hey, here's here's like what we can do with what we have off the shelf, but we need a designer to help us elevate this experience. And so like it's also making it easier to talk the same language as the other thing is like I work on very technical things in the developer experience space where it's like really dense and like super like we we've been working on this like web hooks thing with like seven steps for like a year now and it's like very complicated and there's all these moving parts and states and whatever and now we can actually just show them all as opposed to like trying to have to explain how web hooks work and like all this different stuff. So, it's been really interesting to see how that's changed as well. Um, I have we should we just like try and like build something random really quickly like full like

</details>

**Claire Vemp**: 加速一下。

<details>
<summary>Original English</summary>

**Claire Vemp**: speedun something

</details>

**Owen Williams**: 演示。我在想，构建一个“黑色星期五网络星期一”仪表盘可能会很有趣。

<details>
<summary>Original English</summary>

**Owen Williams**: demo. I'm thinking like it might be interesting to build like a Black Friday Cyber Monday dashboard.

</details>

**Claire Vemp**: 太棒了。开始吧。

<details>
<summary>Original English</summary>

**Claire Vemp**: Great. Let's do it.

</details>

### 即时原型演示

**Owen Williams**: 好的，让我们构建一个 BFM。它会知道那是什么吗？我们拭目以待。

<details>
<summary>Original English</summary>

**Owen Williams**: Okay, let's let's build a BFM. Is it going to know what that is? We'll see. I'll see

</details>

**Claire Vemp**: 一个宠物店的仪表盘，在页面顶部显示实时销售图表。一个显示最新销售额的滚动条。

<details>
<summary>Original English</summary>

**Claire Vemp**: dashboard for a pet store showing live sales on a chart at the top of the page. A ticker with the latest sales and

</details>

**Claire Vemp**: 它还应该有什么呢？我不想让它太复杂。

<details>
<summary>Original English</summary>

**Claire Vemp**: what else shouldn't it have? I don't want to over complicate it. Uh

</details>

**Owen Williams**: 表现最好的产品。

<details>
<summary>Original English</summary>

**Owen Williams**: top performing products.

</details>

**Claire Vemp**: 是的，你和我想的一样。趋势很明显。

<details>
<summary>Original English</summary>

**Claire Vemp**: Yeah, you have the same thought as me. Uh trending bright.

</details>

**Claire Vemp**: 看看这个。仍然有效。仍然是产品。

<details>
<summary>Original English</summary>

**Claire Vemp**: Look at this. Still got it. Still got it as a product.

</details>

**Owen Williams**: 我们一起构建。确保数据是实时真实的。我们要全力以赴，看看它会做什么。

<details>
<summary>Original English</summary>

**Owen Williams**: We're building together. Uh, make sure the data is realistic in real time. And this is we're going to full yolo this and see what it does.

</details>

**Claire Vemp**: 好的。现在它正在加载，我必须说，作为一个现在有两个小宝宝的父母，我们得让你用语音模式。

<details>
<summary>Original English</summary>

**Claire Vemp**: Okay. And now while it's loading, I have to say as a now parent of two with a little baby, we got to get you voice mode

</details>

**Owen Williams**: 在这上面。

<details>
<summary>Original English</summary>

**Owen Williams**: on this.

</details>

**Owen Williams**: 是的，这确实是一个好点子，因为它改变了我的生活，仅仅是能够。

<details>
<summary>Original English</summary>

**Owen Williams**: I I Yes, that's actually a good point because it has that changed my life is just being able to like

</details>

**Owen Williams**: 我不知道。首先我要说，iOS 内置的语音转写功能，每次我使用它都会让我觉得很疯狂。我就像，“你怎么会听不懂基本的句子？”

<details>
<summary>Original English</summary>

**Owen Williams**: I don't know. First of all, I'll say the voice transcription built into iOS, it's like makes me feel insane every time I use it. I'm like, how do you not understand basic sentences?

</details>

**Claire Vemp**: 但是，你那个“**Clawed** 语音模式”，即使宝宝哭闹，你轻声细语，它也能完美捕捉。

<details>
<summary>Original English</summary>

**Claire Vemp**: But then like you the **clawed** voice mode, like you can have a baby screaming and whisper in it and it still nails it.

</details>

**Owen Williams**: 是的。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah.

</details>

**Claire Vemp**: 所以，我确实需要添加那个。这实际上真的很有趣，就像，也许可以描述一下这个东西是如何工作的，当我们看着它运行时。在底层，现在实际发生的是，就像我说的，它正在构建仪表盘。它正在调用我们的 **Sale MCP** 服务器。所以这就像设计系统正在获取所有内容，并解决问题。所以它就像“我需要什么组件来构建那个东西？”“我将如何构建页面？”“我将使用哪个模板？”

<details>
<summary>Original English</summary>

**Claire Vemp**: So, I do need to I do need to add that. This is actually really interesting though, like as maybe a way to describe how this thing works as we watch it cook. The the under the hood, what's actually happening right now is like I said, it's building the dashboard. It's calling our **Sale MCP** server. So that's like the design system like getting all of the content and like sort of working through the problem. So it's like what components do I need to to build that thing? Um how will I structure the page? What template will I use?

</details>

**Owen Williams**: 它会想办法把它们拼凑起来，希望能做出一些漂亮的东西。我们拭目以待。它正在努力。我们看到它已经创建了一个页面，所以我们看看它会变成什么样。你是否能够将那些 **Cursor** 规则基本上转换成这个系统的工作方式，以遵循相同的模式，还是你做了不同的事情？

<details>
<summary>Original English</summary>

**Owen Williams**: Um and then it's like going to figure out how to cobble them together and hopefully make something beautiful. We'll see at the end. It's working on it. We're seeing it made a page already and so we'll see where it winds up. And were you able to just translate those basically those **Cursor** rules into how this system works to kind of follow some of the same patterns or was there something different you did?

</details>

**Owen Williams**: 是的，非常相似。我想它可能更有主见一些，对吧？所以它有额外的工具。它内置了像浏览器工具。它还有很多额外的东西，比如你可以通过与它聊天，将原型部署到一个永久的 URL。所有这些便利功能。你也可以说“检查你的工作”，它也会这样做。但大致上是一样的。我的很多规则可能有点大胆，比如针对 **Figma** 文件。这真的很有趣，就像试图，我想每个人都还在弄清楚这个世界是如何变化的。坦率地说，我想我来自工程界，所以我更倾向于用文字来描述我想要构建的页面，但设计师想要制作一个 **Figma**，然后将其翻译。我完全理解，但 **Figma** 和画布对于这些工具来说仍然相当困难。所以很多规则都像是一些疯狂的事情，比如让 **Cursor** 动作，抱歉，不是 **Cursor**，是让 **Figma** 正确地动作。因为它会说：“哦，这里有1000个 **Tailwind** 样式，还有这个我不知道为什么从头开始构建的随机组件。”或者像是匹配我们内部组件的最大问题是匹配 **Figma** 中的东西。就像，如果你看到这个东西，就让它不是那个。我感觉我在写这些规则时很疯狂。但一旦你有了它们，它就能很好地工作。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah, it's pretty similar. I think it's probably a little bit more opinionated, right? So there's additional tools that this has. It's like got built-in like browser tools. Um it's got like a bunch of extra things like you can um deploy the prototype to a like permanent URL by chatting with it. Like all of those types of like nicities. You can also be like check your work and it will um but it's largely the same. A lot of my rules it might be a little spicy are like for **Figma** files. It's been really interesting like trying to I think like everybody's still figuring out how this changes in this world. Like frankly, I think I come from the engineering world, so I'm like it's easier for me to use words to like describe the page I want to build, but like designers want to make a **Figma** and then translate it, which I totally get, but like **Figma** and like a canvas is pretty hard for these tools still. And so a lot of the rules are like insane things to like make **cursor** act, sorry, not **cursor**, make **Figma** act correctly. Um because it will be like, "Oh, here's a thousand **Tailwind** styles and like this random component I built from scratch for some reason." Um or like uh matching the biggest one is like matching our internal components to like the thing in **Figma**. Like if you see the thing that looks like this, make this not that. Like I feel insane writing these rules. But like once you've got them, it works pretty well. So

</details>

**Claire Vemp**: 我觉得你说的很有趣。你说，作为一个工程师，我觉得用这种方式提示会得到更好的结果。而设计师则说不。我觉得作为一个设计师，我曾和一个朋友谈论 **Claw Design**，我们都得出了完全相反的结论。我说：“我使用 **Claw Design**，我觉得它在营销和品牌风格设计方面做得相当不错，但在UI方面则一塌糊涂。”

<details>
<summary>Original English</summary>

**Claire Vemp**: I think what you said is really funny. As you said, like as an engineer, I feel like prompting it this way is gets a better result. And designers like no I feel like as a designer I was talking to a friend about **claw design** and we both came to completely opposite conclusions. I said, "I use **cloud design** and I think it's actually pretty good at marketing and brand kind of style design work and I think it's garbage garbage at UI."

</details>

**Claire Vemp**: 他是一名营销人员，他说：“我觉得它在UI方面做得相当不错，但在营销方面则一塌糊涂。”我当时就想，我们俩都只懂自己领域的知识。他们无法识别别人领域的“slop”。所以我觉得看到人们在这些生成中识别出什么，以及他们如何使用这些东西，这取决于他们带来的观点，这真的很有趣。

<details>
<summary>Original English</summary>

**Claire Vemp**: And he is a a marketer and he was like, I think that it's pretty good at UI work and garbage at marketing. And I was like, we just both know what we're talking about in our own domains. They like cannot recognize the slop in others. And so I think it's really funny to see what people identify in these generations and how they use stuff just depending on the point of view they bring.

</details>

**Owen Williams**: 没错，这就是问题所在。我不想设定一个期望，认为这能解决所有问题。如何平衡所有这些工作一直很有趣。我如何确保这个工具足够“危险”？它能达到80%的水平。但这种品味，这种技艺，我认为这就是设计师将永远存在的原因。他们知道如何提升体验。这个东西知道如何使用组件。这些组件设计得很好，但它不会是完美的。我们需要引导它们。

<details>
<summary>Original English</summary>

**Owen Williams**: Well, that's that's the thing. And it's like I I don't think I don't want to set an expectation this will solve everything. Like it's been interesting trying to like balance that with all of this work. Like how can I make sure that the um the tool knows enough to be dangerous like it gets to 80%. But like that taste, that craft is like that's why designers will always exist in my opinion. Like they they know how to elevate the experience. Like this thing knows how to use the components. The components are welldesigned, but like it's not going to be perfect. And like we are here to steer them.

</details>

**Claire Vemp**: 是的。我想，嘿，嘿，嘿，**Proto Dash**，那是一个大图表。

<details>
<summary>Original English</summary>

**Claire Vemp**: Yeah. I'm like, you know, hey, hey, hey, **Proto Dash**, that's a that's a big old chart.

</details>

**Owen Williams**: 是的。不，但这是一个非常棒的演示。我喜欢它。就像页面第一次迭代弹出来一样。它就像，如果我构建一个图表，它的高度是整个浏览器那么高呢？

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. Well, no, but this is this is a really great demo. I love it. It's just like sh first iteration of the page popped up. It's like what if I built a chart that's the entire height of the browser.

</details>

**Claire Vemp**: 是的，为什么不呢？

<details>
<summary>Original English</summary>

**Claire Vemp**: Yeah, why not do it?

</details>

**Owen Williams**: 但这很有趣。我当然用了“blow”。它确实喜欢“blow”。它完成了90%的工作，或者说80%的工作，只用了一个非常模糊的提示，就像“给我一个 BSM 仪表盘，带一个滚动条和一些图表”，它就做到了。我没有。但现在是迭代部分。所以这是一个很好的实时演示。现在你可以说抓住这个图表，跳回到这里，然后说图表太高了。它应该是一个狭窄的跨页图表，它就会修复它。

<details>
<summary>Original English</summary>

**Owen Williams**: But it's interesting to look at this. I of course used blow. It does love a good blow. Um it got 90% of the way or I would say 80% of the way there with a very vague prompt like it was like give me a BSM dashboard with a ticker and some charts and it did it. I didn't um and but now is like sort of the iteration part. And so this is a good probably like live demo. Now you could say like grab this chart, jump back into here and say the chart is way too tall. It should be a narrow page spanning chart and just like it will fix it.

</details>

**Claire Vemp**: 好的，你需要加入你所有规则中的另一件事是，如果你向下滚动，天哪，天哪，天哪，一个表情符号。我知道，我在 **Cursor** 中有一个规则，用于我实际在工具上工作时，我显然需要把它放进工具中，因为我快疯了。

<details>
<summary>Original English</summary>

**Claire Vemp**: Well, the other thing you might need to put into your overall rules is if you scroll down, boy oh boy oh boy does an emoji. I know it the I have a rule in **cursor** for my like when I'm working on the actual tool that I clearly need to put in the tool because like I lose my mind.

</details>

**Owen Williams**: 这不是我期望看到的。

<details>
<summary>Original English</summary>

**Owen Williams**: This is not what I would expect to see in

</details>

**Claire Vemp**: 但看那个。图表修复了，对吧？我用我们内置的“给我看看这个元素”的 LLM 工具指着它，我说“修复这个”，它就修复了图表，而我根本不需要描述它。

<details>
<summary>Original English</summary>

**Claire Vemp**: but look at that. The chart is fixed, right? I like pointed at it with the built-in like look at this element for me LLM tool that we have and I said fix this and it fixed the chart without me having to describe it.

</details>

**Owen Williams**: 页面是实时的。别误会我，它不像我见过的最漂亮的东西，但现在你可以迭代它，并在此基础上构建。它看起来像 **Stripe** 的风格。

<details>
<summary>Original English</summary>

**Owen Williams**: Um and the the page is live. Like don't get me wrong, it's like not the most beautiful thing I've ever seen, but it's now you could like iterate on it and like build up from there. It looks like stripish.

</details>

**Owen Williams**: 嗯，它用了正确的，它没有用 Comic Sans。

<details>
<summary>Original English</summary>

**Owen Williams**: Um it uses the right it didn't use comic sands.

</details>

**Claire Vemp**: 嗯。好了。

<details>
<summary>Original English</summary>

**Claire Vemp**: Um there we go.

</details>

**Owen Williams**: 但是的，我想很快谈谈的另一件事是我没有向你展示的，那就是你也可以在这里改变保真度。就像我只是想念的是，给我像等宽字体，这样你就知道你看到的是假的东西。当然，它不起作用。

<details>
<summary>Original English</summary>

**Owen Williams**: But yeah, the the other thing I wanted to quickly talk about though that I didn't show you is um you can also change the fidelity in here. Like something else that like I just miss is like just give me like monospace fonts so that you know you're looking at something fake. Um, of course it didn't work.

</details>

**Claire Vemp**: 你能请务必打开黑白模式吗？这让我想起了我的早期设计师时代。它没有做到。没关系。

<details>
<summary>Original English</summary>

**Claire Vemp**: Will you will you pretty please turn on black and white mode? This is this is like bringing me back to my It didn't do it. That's fine.

</details>

**Owen Williams**: 它没有做到。

<details>
<summary>Original English</summary>

**Owen Williams**: It didn't do it.

</details>

**Claire Vemp**: 好的。但这让我想起了我真正的 OG 设计师时代。我以前这样做。你们，你们都必须非常老才能欣赏这个。所以，我们以前在 **Photoshop** 中做这些设计。

<details>
<summary>Original English</summary>

**Claire Vemp**: Okay. But this is bringing me back to my like truly OG designer days. I used to do this. You all you have to be very old to appreciate this. So, we used to do these designs in **Photoshop**,

</details>

**Owen Williams**: 对吧？

<details>
<summary>Original English</summary>

**Owen Williams**: right?

</details>

**Claire Vemp**: 你知道，你会得到这些长长的可滚动的东西，你会手工处理圆角，所有这些东西。

<details>
<summary>Original English</summary>

**Claire Vemp**: And, you know, you get these like long scrolly things, you're, you know, rounding corners by hand, all this stuff.

</details>

**Owen Williams**: 是的。

<details>
<summary>Original English</summary>

**Owen Williams**: Yes.

</details>

**Claire Vemp**: 然后我以前教我的设计师的一个技巧是，我说：“把整个东西灰度化，然后寻找对比度。”

<details>
<summary>Original English</summary>

**Claire Vemp**: And then one of the tricks I used to teach my designers is I said, "Gayscale the whole thing and look for contrast."

</details>

**Owen Williams**: 是的。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah.

</details>

**Claire Vemp**: 你构建了它。

<details>
<summary>Original English</summary>

**Claire Vemp**: And you built it.

</details>

**Owen Williams**: 是的。它只是一种模式。我喜欢它，因为它就像，好吧，我们甚至没有谈论过这个，但是这些工具有一个挑战，就是现在我把高保真度的东西带到了每次评审中。这可能有点令人不安。我实际上在 **Stripe** 之前在 **Shopify** 工作过，我们在 **Shopify** 所做的一件事，用来表示“正在进行中”或“仍在弄清楚”的工作，就是我们会把字体改成 Comic Sans，这既令人深感痛苦，但同时你也能立即视觉上知道，这还没完成。我喜欢这个。所以，拥有这些内置模式，我们可以非常清楚地看到它还没有完成，或者像我的，或者说等宽字体是我最喜欢的，就是很明显这不是仪表盘，但你明白了。就像它有80%的完成度，这真的很酷，所以它内置了。另外，这实际上是最初原型工具的核心，现在在一个视觉环境中，但你可以非常容易地模拟不同的 **Stripe** 状态。所以，我不知道，你想覆盖某个导航部分，或者你想显示沙盒横幅，或者隐藏导航。你可以在你的原型中做到所有这些。所以这些都是以前很难做到的事情。实际上，商户名称也是我最喜欢的。就像你正在做用户体验研究，你想假装成 Uber，让他们沉浸其中。你只需要写下 Uber 这个词，它就在那里，这真的很酷。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. It's just a mode. Like this is I I love it because it's like okay there is we didn't even talk about this but like one challenge with these tools is like now I'm bringing high fidelity stuff to every review. It can be a little unnerving like I actually so I I worked at **Shopify** uh before **Stroke** and something that we did at **Shopify** to signify like work in progress or like still figuring things out is we would change the fonts to comic sense which was like both like deeply painful but also you knew visually like immediately you're like this is not done. um which I love. And so like having these built-in modes we can I guess like see very clearly that it's not done or like like my or Monospace is my favorite is just like clearly this is not the dashboard but like you get it. It's like 80% of it um is really cool and so that's built in. And then the other thing is like this is this is the core of the original prototyping tool and now in like a visual setting but you can emulate different states **stripe** really easily. So, um I don't know, you want to override a certain nav section or um you want to show the like sandboxes banner or hide the nav. Like you can do all of that in your prototype. And so these are like things that would have been otherwise hard. Actually, merchant name is my favorite too. It's like you're doing UXR and you want to pretend for Uber to like get them into the immersion. Like you can just write the word Uber and it's there, which is which is really cool.

</details>

**Claire Vemp**: 嗯。

<details>
<summary>Original English</summary>

**Claire Vemp**: Um

</details>

**Claire Vemp**: 我喜欢。我在想你的 **Shopify** Comic Sans 的例子，我在想，“哦，这就是香醋核。”你知道，还记得以前的。

<details>
<summary>Original English</summary>

**Claire Vemp**: I love it. I'm thinking about your your **Shopify** comic sands example and I'm like, "Oh, it's balsamic core is what it is." You know, remember the old

</details>

**Owen Williams**: 是的，我有点想要那个在这里，就像最终的目标一样，我们能否构建抽象的低保真东西，然后构建像也许是“Boss ARAMing”模式才是正确的描述方式。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah, I kind of wanted I kind of want that in here is like the goal eventually like can we build abstracted like lowfi stuff and like build like maybe boss araming mode is the right way to describe.

</details>

**Claire Vemp**: 你知道，你知道，如果你知道，你知道。好的，这真是太不可思议了。那么，对于那些坚持到这里的朋友们，简单回顾一下，你构建了一个相当高保真的复制应用程序，任何人都可以下载，在本地或 dev box 中运行，里面有一堆 **Cursor** 规则。你把它变成了一个基于网络的交互式原型工具，里面有一堆，我认为这就是诀窍，一堆控制功能，既可以控制你的设计流程，以便在特定组件上获取反馈，审查它们，处理它们，也可以控制你的原型的不同状态，你知道这些状态在设计团队中都很有用。然后你就可以发布有趣的东西和工作中的东西。然后。

<details>
<summary>Original English</summary>

**Claire Vemp**: You know, you know, if you know, you know. Okay, this has been so incredible. Well, just to recap for folks that have made it this far with us, you built a pretty highfidelity replica app that anybody could pull down, run locally or in a dev box, had a bunch of **Cursor** rules. You turn that into a web hosted interactive prototyping tool with a bunch of I think this is the the the trick. A bunch of controls both for how your design process works in terms of getting feedback on specific components, reviewing them, processing them, and different states of your prototype that you know are useful across the design team. And you can just ship fun things and work things. And then

</details>

**Owen Williams**: 是的。

<details>
<summary>Original English</summary>

**Owen Williams**: yeah,

</details>

**Claire Vemp**: 你看到很多设计师在使用它，但可能更多的是产品经理。所以，人们正在做的事情以及使用的工具正在真正改变。

<details>
<summary>Original English</summary>

**Claire Vemp**: you're seeing a lot of designers use it, but maybe even more PMs. So, the stuff that people are doing and the tools that are using it is really changing.

</details>

**Owen Williams**: 是的。我的意思是，我们还有两分钟可以给你看另一个东西吗？还有一件事。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. I mean, do we have like two minutes to show you one more thing? There's one more thing. Well, like

</details>

**Claire Vemp**: 还有一件事，伙计们。

<details>
<summary>Original English</summary>

**Claire Vemp**: there's one more thing, y'all.

</details>

**Owen Williams**: 还有一件事。我想展示一个原型，这是两名设计师内部使用这个工具构建的。**Ryan** 和 **Sera**，他们一直在构建整个 **Radar** 产品，这是一个欺诈检测产品，对他们来说，他们基本上一直在开发全新的功能，并且能够真正展示从旅程的每个点开始的整个多步骤流程。就像，好吧，我们在 **Stripe** 主页上，你看到一个这样的横幅，然后你看到一个潜在欺诈风险的列表视图，以及原因和数据和动画，所有这些都正常工作，你可以添加一个节点。嗨，它会工作。你甚至可以跳入规则，看看发生了什么原因。能够做到这种非常非常高保真度的东西，就像“这就是仪表盘的精确工作方式”，这也改变了交付方式。**Radar** 这项工作的交付方式令人着迷，因为它就像他们真的有一个原型的拉取请求，我看到一个工程师正在处理，我就像，这在我作为设计经理的职业生涯中从未发生过。他们就像，“哦，就用原型作为事实的来源吧。”能够拿起它，然后说所有组件都是一样的。需要做一些转换，但他们可以直接拿去用，这是一个巨大的变化。所以，拥有这种精确度，而不需要再次暴露年龄，像用红线标记 **Photoshop** 文件，或者所有那些东西，这真的不可思议。现在他们可以直接检查元素并查看内边距。

<details>
<summary>Original English</summary>

**Owen Williams**: One more thing. I wanted to show this prototype that um two designers built internally just like using the tool. Um, so **Ryan** and **Sera**, they've been building like the entire they work on the **Radar** product which is like fraud detection and like for them they've been basically like working on net new features and being able to like actually show the entire multi-step flow from every point of the journey like okay we're on **Stripe** home you see a banner that's like this then you see a list view of like potential fraud risk and like here are the reasons and like here's the data and the animations and like it's all working like you can add a node. Hi, and it will work. You can even like jump into the rules and see what reason something happened. Like being able to do this like really really high fidelity like here is the exact way the dashboard will work also changes the handoff like the handoff for this this piece of work on **Radar**. It's been fascinating because it's like they literally have a pull request of a prototype that I have I see an engineer working on and I'm like this has never happened ever in my career as a design manager. like them and and they're like, "Oh, just use the prototype as the source of truth." And like being able to just pick that up and be like all of the components are the same. There's some translation to do, but like they can just take it and do that is a huge change. And so like having that level of like preciseness and not having to like show my age again like red line a **Photoshop** file or like some all of that stuff is is really incredible. Like now they can just inspect element and look at the padding.

</details>

**Claire Vemp**: 我喜欢。我喜欢。到处都是原型。好的。

<details>
<summary>Original English</summary>

**Claire Vemp**: I love it. I love it. H prototypes everywhere. Okay.

</details>

**Claire Vemp**: 你让我大开眼界。现在我也想要一个这样的。嗯，我会说我用过的一个技巧，因为我也构建了一个非常类似的复制应用程序。

<details>
<summary>Original English</summary>

**Claire Vemp**: Uh you've blown my mind. Now I want one of these. Um I will say one one trick that I've also use something like this for because I built a very similar kind of like replica app.

</details>

**Owen Williams**: 酷。

<details>
<summary>Original English</summary>

**Owen Williams**: Cool.

</details>

**Claire Vemp**: 我把每个组件都做成可下载的 PNG，这样我们就可以在营销素材中使用它。

<details>
<summary>Original English</summary>

**Claire Vemp**: Is I make every component a downloadable PNG so that we can use it in marketing assets.

</details>

**Owen Williams**: 哦，这很好。所以，你知道，你会截屏多少次？

<details>
<summary>Original English</summary>

**Owen Williams**: Oh, that's good. So, you know, like how many how many often are you screenshotting stuff

</details>

**Claire Vemp**: 我想，我需要一个真实的例子，比如一个企业级的 PRD，或者这个组件，或者这个。所以，我就像，每个元素都可以下载为 PNG，然后你可以把它放到幻灯片里之类的。

<details>
<summary>Original English</summary>

**Claire Vemp**: and I'm like, I need a real example of like an enterprise, you know, PRD or this component with this. So, then I just like everything every element you can download as a PNG and then you can drop it into slides and stuff.

</details>

**Owen Williams**: 我能说一句吗？在处理这类工具时，最糟糕也是最幸运的事情是，我把它做得足够好，以至于我觉得它使用起来很神奇，但同时我还有90个其他的想法想添加，而且我可以直接添加。每天我都想：“如果我这样做呢？”然后我做了，我就像，“什么？”

<details>
<summary>Original English</summary>

**Owen Williams**: Can I just say like the worst and best cursed thing working on these types of tools like I've gotten it far enough where I'm like, "Wow, this is like magical to use is like I just have like 90 other ideas I want to add and I can just add them." Like every day I'm like, "What if I just did this?" And then I do it and I'm like, "What?"

</details>

**Claire Vemp**: 是的。你可以将你的意志强加给你的团队客户，而不是担心你真正的客户反馈。

<details>
<summary>Original English</summary>

**Claire Vemp**: Yeah. And you can just impose your will on your teammate customers as opposed to like have to worry about your real customer feedback.

</details>

**Owen Williams**: 哇。对。就像，让我们改变我们所有人的工作方式。

<details>
<summary>Original English</summary>

**Owen Williams**: Whoa. Right. Like let's just let's just change the way we all work. Like

</details>

**Claire Vemp**: 但它确实加速了那个过程，对吧？就像如果我们可以。

<details>
<summary>Original English</summary>

**Claire Vemp**: But it does speed up that process, right? Like if we can

</details>

**Owen Williams**: 我不知道。我脑海中一直有一个想法，我曾经尝试过，但当时层次太多了，就是让我克隆一个仪表盘URL。比如给一个仪表盘URL，克隆整个东西，它就会在这里面，然后你就可以非常，我不知道，你收到了客户反馈，我想修复这个bug，砰，这是它的原型，去修复它。

<details>
<summary>Original English</summary>

**Owen Williams**: I don't know. Uh one idea I've had in the back of my head for a while that I tried at one point and was just like too many layers at the time was like just let me clone a dashboard URL. like give a dashboard URL clone the whole thing and it'll be in here and like then you can very I don't know you've got customer feedback I want to fix this bug boom here's the prototype for it go and fix it

</details>

**Owen Williams**: 所以我想我们正在接近那个境界，你拥有一个非常引人注目的环境副本，并且可以更快地演变它，而无需担心破坏事物，或者，你知道，所有产品传统的边界。所以，是的，我发现它非常令人兴奋。但我有时不得不阻止自己。我就像，“停止，停止添加东西。”

<details>
<summary>Original English</summary>

**Owen Williams**: and so I think like we're nearing that where like you can have this like pretty compelling faximile of your environment and like much more rapidly invol evolve it without like worrying about just like breaking things or um you know all of the like traditional boundaries of the product. So, it's Yeah, I find it I find it very exciting. I just have to stop myself sometimes, though. I'm like, stop stop adding things.

</details>

**Claire Vemp**: 好的。说到停止添加东西，我也得让你走了。小家伙快要出生了。所以，我们要进行一轮闪电问答。好吧，两个闪电问答。我要让你走了。我的第一个问题是，这是我的假设，但每次育儿假都像人们在“vibe coding”一样。他们只是抱着一个宝宝，另一只手拿着一个爪子，做着事情。你是不是在育儿假期间使用AI？告诉我真相。

<details>
<summary>Original English</summary>

**Claire Vemp**: All right. And speaking of stop adding things, I know I have to get you out of here, too. The little one soon. So, we're going to do one lightning round. Well, two lightning round questions. I'm going to get you out of here. My first one is this is my hypothesis, but every parental leave is what like people are spending vibe coding. They're just spending their parental leave holding a baby in one arm. You're holding a claw in the other and making stuff happen. Are you AIing through your parental leave? Tell me the truth.

</details>

### AI与育儿假

**Owen Williams**: 是的。这很有趣，因为这是我的第二个孩子。我的第一个孩子。我感觉这些东西那时候还不存在。而这次就完全不同了，对吧？你只需要从手机里给 **Claw Code** 发送一个提示，所有这些东西。所以他会睡在我身上，我就像，“你能做一个这样的应用程序吗？”是的，我至少做了一个应用程序。我想如果我能找到浏览器窗口，我可以很快地把它闪现出来。这是所有时间里最像爸爸做的事情，但就像一个应用程序，你可以拍下比如你买了一辆昂贵的自行车或电视的收据。它有点像 Expensifier。然后拍下产品照片，然后它基本上会将序列号保存到应用程序中。首先，谁会保存这些东西？你什么时候买的，从哪里买的？下载手册。然后它就在那里。就像我在这个日期以这个价格买了它。这是手册。因为我有一个想法，就是你买了一件好东西，然后大概18个月后它可能会坏。你就会想，我是在哪里买的？我永远也找不到收据。

<details>
<summary>Original English</summary>

**Owen Williams**: Yes. I It's so funny cuz like uh this is my second child. My first kid. I feel like these things were nent and didn't really exist. This time it's like so different, right? Like you can just yeet a prompt into **cloud code** from your phone and like all of this stuff. So, he'll be like asleep on me and I'm just like, "Can you make an app that does this?" And like, "Yeah, I made I made at least one app. I think I uh can flash it up really quickly if I can find the browser window." Um, that's basically like this is the most dad thing of all time that you would ever want, but like a app where you take a photo of like say you buy something expensive like a bike or a TV. Um, you take a photo of the receipt. It's like Expensifier sort of. Um, and then of the product and then it basically like saves the serial number in the app. First of all, who saves this stuff? When you bought it, from where, right? Downloads the manual. Uh, and then just like you have it there. It's like I bought this on this date for this much. Here's the manual. Um, because I have this thing where it's like you buy something nice and then like two, I don't know, 18 months later it might break. You're like, where did I get that? I can never find the receipt ever.

</details>

**Claire Vemp**: 好的。所以，是的。

<details>
<summary>Original English</summary>

**Claire Vemp**: Okay. And so, yeah,

</details>

**Claire Vemp**: 我喜欢这个。我要在这里提出一个功能请求，因为你的孩子会慢慢长大，那些子宫自行车很贵。

<details>
<summary>Original English</summary>

**Claire Vemp**: I love this. Let me I'm gonna do a feature request here because your kids will get older and those womb bikes are expensive.

</details>

**Owen Williams**: 哦，它们确实很好。

<details>
<summary>Original English</summary>

**Owen Williams**: Oh, they're so good though.

</details>

**Claire Vemp**: 它们确实很好。但总有一天，第二个孩子用完后。你会在三年后想要一个提醒来卖掉这个东西。

<details>
<summary>Original English</summary>

**Claire Vemp**: And they're so good. But at some point after kid number two is done with it. You're going to want like 3 years later a reminder to sell this thing.

</details>

**Owen Williams**: 哦，那是个好主意。我喜欢那个。就像，是的，两年后提醒我，我不再需要这个了。

<details>
<summary>Original English</summary>

**Owen Williams**: Oh, that is a good idea. I like that. It's like, yeah, remind remind me in two years I don't need this anymore.

</details>

**Claire Vemp**: 两年后提醒我。这东西需要从车库里搬出来，然后搬到别的地方。

<details>
<summary>Original English</summary>

**Claire Vemp**: Remind me in two years. This thing needs to get out of the garage and um somewhere else.

</details>

**Owen Williams**: 那是 Jean。是的。

<details>
<summary>Original English</summary>

**Owen Williams**: That is Jean. Yes.

</details>

**Claire Vemp**: 好的，谢谢。我需要完成它。但是。

<details>
<summary>Original English</summary>

**Claire Vemp**: Well, thank you. I need to finish it. But

</details>

**Claire Vemp**: 还有，当保修期到期时。是的。

<details>
<summary>Original English</summary>

**Claire Vemp**: also like when the warranty expires. Yep.

</details>

**Claire Vemp**: 如果它需要任何维护。

<details>
<summary>Original English</summary>

**Claire Vemp**: If it requires any maintenance.

</details>

**Owen Williams**: 好的，这是我开始这个的另一个原因，因为我在保修期方面有过不好的经历，就像它在保修期结束前三天坏了，但那段时间我有一个孩子。

<details>
<summary>Original English</summary>

**Owen Williams**: Well, that was the other reason I started this is I had a bad experience with a warranty where like it broke probably 3 days before the warranty was up, but I had a kid during that time.

</details>

**Claire Vemp**: 是的。

<details>
<summary>Original English</summary>

**Claire Vemp**: Yeah.

</details>

**Owen Williams**: 我知道，如果我提前一周知道，我就会迅速给公司发邮件。所以这就是我做的原因。

<details>
<summary>Original English</summary>

**Owen Williams**: And I, you know, if I had had a week's notice, I would have been like quickly emailing the company. So that's why I did it.

</details>

**Claire Vemp**: 你需要加入我运营的家庭“Live Love Claw”Slack 群。

<details>
<summary>Original English</summary>

**Claire Vemp**: You need to join the family live love claw slack that I run

</details>

**Claire Vemp**: 那里都是父母在努力弄清楚如何使用AI和Open Claw以及所有这些东西来做真正的事情。好的，我要去。

<details>
<summary>Original English</summary>

**Claire Vemp**: that's all just parents trying to figure out how to use AI and open claw and all these things to do real stuff. Okay, I'm going to

</details>

**Owen Williams**: 我显然需要更多的副业项目，不是吗？

<details>
<summary>Original English</summary>

**Owen Williams**: I clearly need more side projects, don't you?

</details>

**Claire Vemp**: 显然。好的，**Owen**，这太棒了。最后一个问题。当AI不听话时，当你低声说：“别犯错。”

<details>
<summary>Original English</summary>

**Claire Vemp**: Clearly. Okay, **Owen**, this has been amazing. Uh, last question. When AI is not listening, when you're whispering, you're like, "Make no mistakes.

</details>

**Claire Vemp**: 我的宝宝在哭。别犯错。”当它不听话时，你的提示策略是什么？

<details>
<summary>Original English</summary>

**Claire Vemp**: My baby's crying. Make no mistakes." When it's not listening, what is your prompting strategy?

</details>

**Owen Williams**: 呃，全部大写。不。

<details>
<summary>Original English</summary>

**Owen Williams**: Uh, all caps. No,

</details>

**Claire Vemp**: 没关系。

<details>
<summary>Original English</summary>

**Claire Vemp**: that's fine.

</details>

**Owen Williams**: 我会大声喊叫很多。我想我只是尽量做到非常具体。我的职业道路迂回曲折。我曾经从事内容工作，然后变得非常具体，这很有帮助。然后，我学会了，好吧，我给你这个建议。我发现，一旦我发出了第一个咆哮的提示，就该重置会话并重新开始。就像上下文窗口满了。进展不顺利。重新开始。一旦我觉得想骂脏话，就重新开始。

<details>
<summary>Original English</summary>

**Owen Williams**: I do a lot of shouting. Um, I think I I just try and be really specific. Like I I came my I have a lot of meandering career paths. I had a content background at one point and like just being specific upfront helps a lot and then like uh I have I have learned okay actually I'll I'll give you this piece of advice. I find if I as soon as I've sent the first shouty prompt, it's time to like reset the like slashcle and start again. Like the context window is full. It's not going well. Start again. As soon as I feel like swearing in there, like start again.

</details>

**Claire Vemp**: 我觉得这也适用于育儿，我心想，如果大声说话没用，我就不会那样做了，伙计们。

<details>
<summary>Original English</summary>

**Claire Vemp**: I feel like this is also applicable again to parenting children where I'm like, if being loud didn't work, I wouldn't do it, guys.

</details>

**Owen Williams**: 我知道。但这很有趣。我想，我必须重新训练我的大脑，对吧？作为一个构建过很多东西的人，你有时会陷入沉没成本谬误。你会想：“我肯定能让它工作。”但通常情况下，扔掉它，重新开始。

<details>
<summary>Original English</summary>

**Owen Williams**: I know. But it's like such a funny I think it's like I had to retrain my brain, right? Like as somebody who has built a bunch of stuff, you get that like sunk cost fallacy at some point. You're like, "Surely I'll get this to work." But like often just throwing it away and starting again.

</details>

**Claire Vemp**: 是的。

<details>
<summary>Original English</summary>

**Claire Vemp**: Yeah.

</details>

**Owen Williams**: 我喜欢这个。**Owen**，这太有趣了。我们能在哪里找到你，我们能帮到你什么？

<details>
<summary>Original English</summary>

**Owen Williams**: I love this. Owen, this has been so fun. Where can we find you and how can we be helpful?

</details>

**Owen Williams**: 我在 **Twitter** 上。我们还在说那个吗？我说那个。呃，**Twitter**。用户名很短。这就是我不能离开的原因。呃，我也有我的网站，Owen Williams。那只是域名，但在 MS 之前加个点就行了。嗯，天哪，我们怎么能帮你？就像只是构建很酷的设计工具。我们实际上非常相信这个原型设计的东西，所以我们正在招聘一个，我不知道怎么形容，但就像一个设计工程师类型的人来推动这些事情。我们认为它将改变我们构建的方式，所以我们正在招聘这样的人，这样我就不必把它当作我的另一份工作来做了。嗯，所以请加入我们。如果你是那种喜欢编码也喜欢设计东西的怪人，呃，给我发个私信。我很乐意谈谈。

<details>
<summary>Original English</summary>

**Owen Williams**: I'm on **Twitter**. Do we still say that? I say that. Uh **Twitter**. Very short username. Um that's why I can't leave. Uh, and I I'm also on my website, Owen Williams. That's just the domain name, but dot before the MS and it works. Um, and gosh, how can you help me? How like just build cool design tools. We're actually like this prototyping thing. We believe in it so much that we're hiring a like I don't know how to describe it, but like a design engineery type person to like drive this stuff. Like we think it's going to transform the way that we build and so we're hiring that kind of person so I don't have to build it as my other job. Um, so please join us. If you're like the kind of weirdo like that maybe that likes to code and also likes design stuff, uh, send me a DM. I' I'd love to talk.

</details>

**Claire Vemp**: 喜欢。好的，谢谢你。谢谢你加入《How I AI》。

<details>
<summary>Original English</summary>

**Claire Vemp**: Love it. Well, thank you. Thank you. Thank you for joining How I AI.

</details>

**Owen Williams**: 是的。谢谢你邀请我。

<details>
<summary>Original English</summary>

**Owen Williams**: Yeah. Thank you for having me.

</details>

**Claire Vemp**: 非常感谢您的收看。如果您喜欢本节目，请在 **YouTube** 上点赞并订阅，或者更好的是，留下您的评论和想法。您也可以在 **Apple Podcasts**、**Spotify** 或您最喜欢的播客应用程序上找到本播客。请考虑给我们留下评分和评论，这将帮助其他人找到本节目。您可以在howiipod.com查看我们的所有剧集并了解更多关于本节目的信息。下次再见。

<details>
<summary>Original English</summary>

**Claire Vemp**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on **YouTube**, or even better, leave us a comment with your thoughts. You can also find this podcast on **Apple Podcasts**, **Spotify**, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>