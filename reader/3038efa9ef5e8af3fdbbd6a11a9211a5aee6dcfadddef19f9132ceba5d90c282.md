---
author: AI Engineer
date: '2026-05-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zepu8Kk6FBQ
speaker: AI Engineer
tags:
  - agentic-workflow
  - automation-productivity
  - knowledge-work
  - human-ai-collaboration
  - workflow-optimization
title: 代理无所不能——AI 工程会议的运营新范式
summary: Swyx 分享了 AI Engineer 团队如何使用 Devin 等编码代理，从 Figma 设计到网站开发、会议日程管理、数据同步等工作流的全面自动化。通过代理赋能非技术团队、消除依赖链处理、提升员工工作满足感，九人团队成功管理千人规模会议。演讲强调代理的核心价值不仅在代码生成，更在于提升人类生产力和工作体验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - AI Engineer
  - Cognition
  - Vercel
  - OpenAI
products_models:
  - Devin
  - Figma
  - React
  - Supabase
  - TLDraw
media_books: []
status: evergreen
---
### 三年演讲之旅：从生产力到代理

**Swyx**: 感谢大家坚持到最后。我想跟大家分享过去三年里，我们在 **AI Engineer** 这个会议上讨论过的核心主题如何演进。三年前的第一场演讲，我谈的是从增加 AI 使用中获得的生产力收益。第二年，我们讨论了为什么你应该使用更多 AI——因为 AI 的成本曲线在以大约每 12 到 18 个月下降 100 倍的速度持续下行。我认为这个趋势仍在继续。第三年，我们开始谈论"微型团队"（tiny teams），我对其定义是：收入（以百万计）超过员工数量的团队。

<details>
<summary>Original English</summary>

**Swyx**: For those newer to us, I do one of these keynotes every single AIE. The first very first one 3 years ago, I talked about the productivity gain that you get from the increased AI usage. And the second one, we talked about how you should just use more AI because the cost curve of AI is going down roughly 100 times per every 12 to 18 months. And I think it's still continuing to trend that way. The third year, we started to talk about tiny teams, which was basically this definition that I had that teams with more millions in revenue than number of employees.

</details>

我甚至在世界展览会上策划了整个分会，总结为"微型团队寓言"。我喜欢强调这一点的原因是，我认为人们对寻找"独自成为亿万富翁"或"独角兽创始人"的想法可能过于迷恋。但实际上，无论公司大小，每个公司都可以拥有微型团队。

<details>
<summary>Original English</summary>

**Swyx**: I even curated an entire track at the World's Fair about this where we sort of summarize it as the tiny teams fable. The reason I liked this emphasis is because I think people are maybe too egotistical about looking at the one-person billionaire or unicorn founder. But every company can have a tiny team whether you're small or large.

</details>

而我们 **AI Engineer** 本身就是一个微型团队。我和 Ben Lear 是领导，我们只有 9 名全职员工，却在运营一个超过 900 万美元的业务。所以我们确实是一个微型团队。

<details>
<summary>Original English</summary>

**Swyx**: When I look at how we run AI Engineer, with me and Ben Lear as leadership, we're also a tiny team. We have just nine full-time people and we're running a business that is more than $9 million.

</details>

### 工作流转变：从传统工具到代理

**Swyx**: 我想展示过去三年来我们工作流最显著的变化。首先，我们的技术栈曾经是非常稳定但完全非 AI 的——这对一个 AI 会议来说确实很讽刺。我们使用 **Figma**、**React**、**Supabase**、Tido、**Google Sheets** 和 Sessionize。

<details>
<summary>Original English</summary>

**Swyx**: Our stack was very stable and completely non-AI, which is very ironic for an AI conference. We use Figma, React, Supabase, Tido, Google Sheets, Sessionize.

</details>

然后发生了一件有趣的事。我加入了 **Cognition**，开始在工作中认真使用编码代理——说实话，主要是因为它们是免费的。我开始将其添加到公司 Slack，向大家展示如何用它来进行网站编码工作。一切都很顺利。但接着发生了一些奇怪的事。

<details>
<summary>Original English</summary>

**Swyx**: I joined Cognition and started using coding agents seriously at work, mostly because they were free. I started adding it to the company Slack and showing people how to use it for coding on the company website. All well and good. But something strange starts happening.

</details>

我们的合同设计师（现在是全职的）向我展示一个 **Figma** 页面，问我能否将其转化为现实。通常我们会花一周、两周、四周时间来做这个。我就直接把 **Devin** 加到项目里。

<details>
<summary>Original English</summary>

**Swyx**: A workflow of our contract designer now full-time was showing me a Figma page and asking me to turn it into reality. We would take a week, 2 weeks, 4 weeks. I just added Devin to it.

</details>

### "挖洞填洞"（Yak Shaving）问题

**Swyx**: 这引出了我的第一个重要启示：无论何时出现随意的"挖洞填洞"（yak shaving）问题——即那些"哦，我得先做那个，哦，我得先做那个"的依赖链爬升——代理的一个被严重低估的优势是它们能帮你摆脱这种困境。尤其是在安装依赖或修复 Python 依赖时，代理特别有用。

<details>
<summary>Original English</summary>

**Swyx**: Anytime there's like random yak shaving, I think one underappreciated benefit of agents is that they save you the yak shaves. Like all the dependency tree crawling of like, "Oh, no, I have to do that first. Oh, no, I have to do that first." And particularly when it comes to installing dependencies or fixing Python dependencies, fantastic for that.

</details>

我认为一个不充分重视"并行性"和自主权的生产力模型，在完全捕捉代理的好处方面是不完整的。不仅仅是自主权，还有"摆脱挖洞填洞"的意义——这不是完全被捕捉的。

<details>
<summary>Original English</summary>

**Swyx**: What model of productivity that doesn't sufficiently appreciate parallelism and not just autonomy, I think the death of yak shaving is not fully capturing the benefit of agents.

</details>

### Figma 到网站：第一个突破

**Swyx**: 我们把 **Devin** 连接到 **Figma**，非常快地就得到了一个完全可用、像素完美的网站，与 Figma 完全一致。这对我来说很惊讶，因为我从没试过。你总是怀疑营销词汇，直到你自己看到为止。更重要的是，我们的设计师对此非常满意。这就是你现在在 ai.engineer 网站上看到的网站。

<details>
<summary>Original English</summary>

**Swyx**: We hooked up Devin to Figma and in very short order, we have a perfectly functioning website that is pixel perfect to the Figma. And to me, that was a surprise because I've never done it before. You always mistrust marketing until you see it for yourself. And more importantly, our designer was very happy about it. That's basically the website you see live today when you go to ai.engineer.

</details>

### 跨时区协作的意外发现

**Swyx**: 然后发生了有趣的事。初次成功后，我们开始更频繁地使用 **Devin**。回复数量激增。让我告诉你为什么。首先，我启动一些工作，然后去睡觉。我的设计师在印度尼西亚，他醒来后开始处理 **Devin**，用红线注解来提示 **Devin**——这是昨天的演讲者 Steve Ruiz 在 **TLDraw** 上做的那种做法。

<details>
<summary>Original English</summary>

**Swyx**: After one initial success, you start using it more. I start kicking off some work and then I go to bed. And then my designer who's in Indonesia wakes up and starts messing with Devin. Starts prompting Devin with red lines on annotations, which is something that Steve Ruiz, one of our speakers from yesterday, does with TLDraw.

</details>

我从没教过他这样做。没有说明书。他只是想："我会怎样和另一个人类沟通？"所以我主要和非技术团队合作，我认为他们需要能够舒适地使用代理——我认为他们最终已经到达这个阶段了。

<details>
<summary>Original English</summary>

**Swyx**: I never taught him to do this. There's no instruction manual. It was just mostly like, "How would you communicate with another human being?" I work mostly with a non-technical team and I think that's very important that they need to be comfortable with agents and I think they're finally at that point that they are.

</details>

### 工作变得有趣：员工生产力的真正提升

**Swyx**: 我们开始做一些我们通常不会做的事情。网站上有一个复活节彩蛋——没人报告过，所以我假设你们都没发现。为什么？因为我放在那儿的。为什么？因为这很有趣，因为我可以做。如果你在超宽屏上，扫过高亮处，你会看到一个复活节彩蛋。

<details>
<summary>Original English</summary>

**Swyx**: We start working on things that we would never normally have worked on. There's an Easter egg on the website. Why? Because I put it there. Why? Because it was fun. Because I could. If you're on an ultra-wide screen, you scan your mouse over the highlights, you'll see an Easter egg.

</details>

我看到一个关于设计美学的病毒式推文，我喜欢，我就把它扔给 **Devin**。最有趣的是——原因是什么？他之所以开始做这个原本我认为是一次性的、有趣的项目，是因为它很有趣。对我来说这是个大的"啊哈"时刻。我从员工那里获得更多工作，因为他们喜欢做这些工作。以前，他们要等待我的指示或等待承包开发者，现在这个反馈循环消失了。

<details>
<summary>Original English</summary>

**Swyx**: I saw a tweet that was viral about a design aesthetic that I liked. I threw it into Devin. The most interesting thing is why he starts working on it even though it's a throwaway project is because it's fun. And I think that's something that was like a big aha moment for me. I am getting more work out of my employees because they enjoy doing it. The feedback cycle for them from waiting or being blocked on me or a contracted developer is gone.

</details>

他们现在可以想到一个主意，就直接去做。他们正在做动画、做抛光——我从员工那里获得的工作是我以前从未获得过的。我认为这是需要欣赏的东西。如果你注意到，我已经不再谈论代理用于编码或我生成了多少行代码。我获得了更多的人类生产力。我认为这是今年的一个主要主题，我真的在探索——代理应用于一切。

<details>
<summary>Original English</summary>

**Swyx**: They just have the idea, they go do it. They're doing animations, they're doing polish. I'm getting work that I've never gotten out of my employees before. I'm no longer talking about agents for coding or how many lines of code I'm producing. I'm getting more productivity out of my humans. This is a major theme for this year that I'm really trying to investigate, which is agents for everything else.

</details>

### 会议数据管理：从 CMS 到代理

**Swyx**: 然后我想，好吧，我用 **Figma** 到网站成功了，我用推文到网站也成功了。还有什么别的吗？整个会议本质上是一个巨大的数据管理问题。我得与 130 位演讲者、几十个赞助商和各种需求各异的参加者进行同步。

<details>
<summary>Original English</summary>

**Swyx**: I had the success with Figma to website. I had the success with tweet to website. What else? This whole conference is a giant data management problem. I have to sync with 130 speakers and couple dozen sponsors and all the attendees that come in with all various needs.

</details>

本质上这就是一个 CMS，对吧？我们尝试了 Sanity，但我想为自己保留一些理智。所以我只是把电子表格扔给 **Devin**，它为我管理。真正的解锁时刻是当我抛弃 CMS，把代码作为我的单一真实来源，让 **Devin** 或任何编码代理来管理它的时候。

<details>
<summary>Original English</summary>

**Swyx**: It's just a CMS, right? We messed with Sanity. I can throw in spreadsheets and Devin can manage that for me. The unlock happened when I threw away the CMS and just committed code as my source of truth and let Devin manage it.

</details>

所以整个日程表都由 **Devin** 管理。这意味着什么？当有人提出演讲者变更时——比如今天的演讲者之一 Marta 发来邮件——我只需说："Devin，帮我处理。"不需要进一步的沟通。我可以转发邮件或粘贴截图，都可以。

<details>
<summary>Original English</summary>

**Swyx**: This entire schedule is managed by Devin. What does that mean? Whenever someone comes in with a speaker change, I just say, "Devin, handle it for me." No other further communication is needed. I can just forward the email or paste a screenshot.

</details>

这种规模让我们这个 9 人的小团队能够管理千人规模的会议。今年夏天我们将在旧金山管理 6,000 人的会议，我相当确定我们能保持相同的规模。一旦你充分登船并且工作流得到整理，你能获得的生产力是难以置信的。

<details>
<summary>Original English</summary>

**Swyx**: That kind of volume lets us as a small team of nine people manage a thousand-person conference. We're going to manage 6,000 people in San Francisco this summer and I'm pretty sure we can stay the same size. It is incredible the amount of productivity that you can get once you're sufficiently on-boarded and you have the workflows ironed out.

</details>

### 代理的多元应用场景

**Swyx**: 我们还有用于 ETL 的代理。我们处理外部供应商系统，这些系统有我们在中央真实来源中没有的数据。我需要获得 API 密钥来同步数据，确保单一真实来源。这些都是很无聊的例行任务。

<details>
<summary>Original English</summary>

**Swyx**: We have agents for ETL. We deal with an external vendor system that has data that we don't have in a central source of truth. I need to get the API key to sync over data and make sure there's a single source of truth. These are very boring routine tasks.

</details>

还有另一个有趣的故事——代理用于采购。我看到一条关于有人在华尔街的华尔街公牛旁放了一只龙虾爪的病毒式推文。我想，"好吧，这很有趣。我们应该在我们的会议前放一只龙虾爪。"所以我要求 **Devin** 研究："我在伦敦哪里能买到龙虾？" **Devin** 回来提供了电话号码、电子邮件地址和网站。我浏览了一下，做了更多研究，就这样，你在这里看到的龙虾就是从 **Devin** 买来的。

<details>
<summary>Original English</summary>

**Swyx**: Another fun story is agents for buying. I saw this viral tweet about how somebody put a claw next to the Wall Street bull. I was like, "Well, that's funny. We should put a claw in front of our conference." So I asked Devin to research, "Where can I get a lobster in London?" Devin comes back with phone numbers and email addresses and websites. The lobster you had was bought from Devin.

</details>

我认为这种一切皆自动化的个人化，核心是你需要一个有网络访问权限的代理，拥有足够智能的模型。这不重要是爪子、开放爪子、纳米爪子还是其他什么——重要的是你在使用代理做知识工作，这些工作你原本可能让执行助理或初级员工来做。现在我可以按需、无服务器、用合适的代理来做。

<details>
<summary>Original English</summary>

**Swyx**: This kind of personal automation for everything else, it just matters that you have an agent that has web access that has a smart enough model. It doesn't really matter if it's a claw, open claw, nano claw, or whatever. It matters that you're using agents for things that you would otherwise have spent knowledge work on. I might have had an executive assistant or a junior employee do these things, but now I can do it serverless on demand with an appropriate agent.

</details>

### 代理生态的大爆炸

**Swyx**: 我不仅仅是在展示 **Devin**。但我想告诉你，编码代理将要"打破封闭"。会有许多其他更专用的知识管理工具，就像 **Andre Karpathy** 讨论的 wiki，还有 **Nano Claw** 和 **Open Claw** 也在采纳的东西。你会看到一场爆炸。这可能是 2026 年排名前三到五的趋势之一，我想提醒你。

<details>
<summary>Original English</summary>

**Swyx**: I'm not here to only show Devin. But I think what's happening here is coding agents are going to break containment. There are all these other more fit-for-purpose knowledge management tools like the wikis that Andre Karpathy is talking about that Nano Claw and Open Claw are adopting as well. You're going to see an explosion of this. This is probably one of the top three to five trends of 2026 that I want to alert you to.

</details>

### 从 Apple Notes 到结构化知识

**Swyx**: 这是我管理今年夏天世界展览会的方式。这是我计划的所有分会。这是我的 Apple Notes。左边是我所有想要邀请的人的 Apple Notes——故意做得很小——我把它扔给 **Town**（Claude），然后就弹出一个格式良好的 Notion 文档，包含我打算邀请和策划的所有演讲者的研究。

<details>
<summary>Original English</summary>

**Swyx**: Here is me managing the world's fair this summer. Here all the tracks I'm planning. Here's my Apple notes. I threw it into Town and on up pops a nicely formatted notion doc with research on all the speakers that I intend to solicit and think about curating.

</details>

### 用代理替换 SAS：风险与收益

**Swyx**: 一旦你有足够的信心和经验，你开始思考替换整个 SAS 软件。这是我和员工争论的过程——我们要踢出一个 SAS 工具，自己建立它，因为我们可以。显然我是最有信心的那个。如果你处于权力或管理位置，面对没有那么多信心的员工，你需要带他们上路，而不是傲慢地忽视他们的担忧。因为他们的担忧是非常有效的——他们正是那些在你犯错时必须处理它的人。而我们确实会犯错。

<details>
<summary>Original English</summary>

**Swyx**: Once you get enough confidence, you are thinking about replacing entire pieces of SaaS. I'm arguing with my employees about kicking out a SaaS tool and building it ourselves because we can. I clearly have the most confidence. If you're in a position of power or management dealing with employees who are not as much into this and try to bring them along the journey, don't talk down to or ignore their concerns. Because they are very valid concerns because they are exactly the people that will have to deal with it when you get it wrong, and we do get it wrong.

</details>

我使用的一个方法——我认为这对很多人都适用——是：好吧，让我们确定前三个担忧，系统性地减少它们。这就是我们现在正在进行的过程。我只是想给你们一点品味，看看 AI 如何改变我们的会议管理业务。这已经走了很长的路。

<details>
<summary>Original English</summary>

**Swyx**: One method I'm approaching this is well, let's identify the top three concerns and let's systematically reduce them and that's the process that we're going through right now. I just wanted to give you a little taste of how AI is changing our business as managing the conference.

</details>

### 行业级的代理转变

**Swyx**: 这是一个一致的主题，我甚至从我们的其他演讲者那里看到。**Malte** 的开场主题演讲讨论了 **Vercel** 的用户群现在有 60% 是机器人——是代理，不是人类。所以实际上你的仪表板不重要，你的 API 重要，你的 CLI 重要，你的 MCP 重要。

<details>
<summary>Original English</summary>

**Swyx**: This is a consistent theme I'm seeing even among our speakers. Malte's opening keynote talking about how 60% of the user base of Vercel now is bots—agents—it's not humans. So your dashboards don't matter, your APIs matter, your CLIs matter, your MCPs matter.

</details>

今天的演讲者 Edo 和 Liad 在讨论 MCP 应用，他们谈到你的自定义用户界面正在消失。你应该把用户界面发送给别人的应用。这种"你的主要用户正在改变"的模式，正在真正转向人们所说的"代理体验"。这是我真的被激励并专注于的东西，因为它正在帮助我。我不再关心 **Figma** 仪表板。我把它扔到 Claude Co-worker 中，希望它能为我工作。

<details>
<summary>Original English</summary>

**Swyx**: Edo and Liad who spoke today on MCP apps, talking about how your custom UI is kind of going away. You should ship UI to somebody else's app. These patterns of how your primary user is changing is really shifting towards what people are calling agent experience. This is something that again I'm really inspired by and focused on because it is helping me. I no longer care about the Figma dashboard. I throw it into cloud co-work and I hope that it works for me.

</details>

### 最后的号召

**Swyx**: 所以我的信息是：代理应用于一切即将到来。醒醒。使用它。把它带回家去工作。如果人们还没充分认可，给他们开一剂 AGI 药丸。谢谢大家。

<details>
<summary>Original English</summary>

**Swyx**: That's my message: agents for everything else are coming. Wake up. Use it. Bring it home to work. If people are insufficiently bought on, prescribe them one of these. Thank you.

</details>