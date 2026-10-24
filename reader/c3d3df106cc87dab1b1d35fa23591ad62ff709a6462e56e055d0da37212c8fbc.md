---
author: How I AI
date: '2026-04-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=BRDKft0-dUU
speaker: How I AI
tags:
  - ai-tooling
  - software-development
  - ai-workflow
  - developer-experience
  - engineering-management
title: Intercom 如何通过 AI 工具将工程效率提升两倍
summary: 本次访谈深入探讨了 Intercom 如何通过引入 AI 工具（特别是 Claude Code）将其工程吞吐量提高了一倍。Intercom 的高级首席工程师 Brian Scanland 分享了他们在此过程中的经验，重点介绍了文化变革、AI 技能采用的遥测技术重要性，以及对产品质量和开发者体验的影响。讨论还涉及了 AI 使用的成本考量，以及 AI 如何改变产品开发和内部流程。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Brian Scanland
  - Claire Vote
  - Darra
companies_orgs:
  - Intercom
  - Anthropic
  - OpenAI
  - Stripe
  - Figma
  - Datab Bricks
  - PayPal
  - Ollipop
  - Stanford
products_models:
  - Claude Code
  - Cursor
  - GPT-4o
  - Honeycomb
  - Snowflake
  - S3
  - Celiggo Aura
  - GOG
  - Finn
media_books: []
status: evergreen
---
### AI 驱动下的效率飞跃

**发言人A**: 突然之间，你开始意识到你必须更宏观地思考事物，或者说你的想象力现在是障碍，而不是工具。

<details>
<summary>Original English</summary>

**发言人A**: Suddenly you started realizing that you have to think bigger about things or that your imagination is now the barrier not the tool.

</details>

**发言人B**: 这在你的组织中怎么可能不发生呢？字面上看，我输入代码的物理限制都被 AI 解锁了。

<details>
<summary>Original English</summary>

**发言人B**: How is this not happening in your organization? Like literally the physical limits of my ability to type code are unlocked by AI.

</details>

**发言人A**: 今天，我们的工程团队的吞吐量是九个月前的两倍。现在就想，为什么不能是十倍呢？这有点更接近我的直觉告诉我的可能性，那就是如果你全力以赴，如果你准备好你的团队，如果你准备好你的代码库，我认为你的整体产品质量会提升。我认为你的整体开发者体验会提升。使用这些工具并正确使用它们，会带来许多好处。

<details>
<summary>Original English</summary>

**发言人A**: Today we are seeing twice the number of throughput as we did compared to 9 months ago on our engineering team. Now it's like why can't it be 10x? This is a little bit more of what my instinct tells me is possible, which is if you go allin, if you prepare your team, if you prepare your codebase, I think your overall product quality is going to go up. I think your overall developer experience is going up. There's just so many good things that come out of using these tools and using them correctly.

</details>

**发言人B**: “待办事项清零”对团队来说是可实现的。所有你曾希望做的事情，现在都变得可实现。我经常建议许多 **CTO** 和工程副总裁，在思考如何让他们的工程团队 AI 化时，我说：“去花一个月时间修复你代码库中所有你讨厌的东西，看看我们能多快地完成它。”那会感觉非常好。

<details>
<summary>Original English</summary>

**发言人B**: Backlog zero is a realistic thing for teams to be able to go after. All the things that you wish you would ever wanted to do, it's now just achievable. I often advise a lot of CTOs and VPs of engineering when figuring out how to get their engineering team AI pilled say everything you hate about the codebase, go spend a month fixing and see how fast we can speedrun that. That's going to feel really good.

</details>

**发言人A**: 在过去三个月里，我职业生涯中获得了最大的乐趣。

<details>
<summary>Original English</summary>

**发言人A**: I've been having the most amount of fun in my career over the last 3 months.

</details>

### Intercom 的 AI 转型之路

**Claire Vote**: 欢迎回到 "How I AI"。我是 **Claire Vote**，产品负责人和 AI 狂热者，致力于帮助你更好地使用这些新工具进行构建。今天我将展示 **Intercom** 如何在短短几个月内将其 **R&D** 部门的 **PR** 数量翻了一番。**Brian Scanland** 是 Intercom 的高级首席工程师，他将向我们展示他们如何让一个大型产品和工程组织在 **Claude Code** 上高效运作的所有秘密。让我们开始吧。本期节目由 **Celiggo** 赞助。如今每家公司都希望 **AI** 能改进工作方式。最快的方法是将其直接融入日常业务流程，自动化员工入职、保持客户数据准确、管理订单和库存，或解决财务和运营问题。当 AI 融入工作流程时，它可以更新记录、触发审批、路由工作，并启动跨系统的下一步。这就是团队如何实现 **AI** 的操作化并交付可衡量结果的方式。**Celiggo** 让这一切成为可能。现在有了 **Celiggo Aura**，它从未如此简单。**Celiggo Aura** 让你可以通过自然语言访问整个平台，连接你的系统并将意图转化为行动。一切尽在你的掌控之中。**Datab Bricks**、**PayPal** 和 **Ollipop** 等公司依赖 Celiggo 来大规模运行关键业务操作。准备好将 AI 操作化了吗？请访问 celigo.com/helli AI。那是 cel.com/howi AI。**Brian**，欢迎来到 "How I AI"。我非常高兴你能来参加播客，因为我认为 Intercom 已经做到了，你们以两种方式抓住了时机。首先，从产品角度看，显然抓住了时机。你们是首批拥有——我不想说是传统业务，但却是持续经营业务——看到 AI 即将来临并真正改变了你们产品如何为客户服务。我是 **Finn** 的忠实客户，他们没让我这么说。其次，我们要讨论的是，团队抓住了时机，真正理解了 AI 将如何改变产品工程和设计组织以及工程组织的工作方式，你们全力以赴地改变了团队的工作方式。是什么驱动了抓住时机的紧迫性？它是如何发生的？是一个人吗？是所有人吗？你的经验是什么？

<details>
<summary>Original English</summary>

**Claire Vote**: Welcome back to How I AI. I'm Claire Vote, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I am showing how Intercom 2xed the number of PRs that their R&D department is shipping in just a few months. Brian Scanland is a senior principal engineer at Intercom and he is going to show us truly all of their secrets to getting a large product and engineering organization cooking on cloud code. Let's get to it. This episode is brought to you by Celiggo. Every company today wants AI to improve how work gets done. The fastest way is building it directly into everyday business processes, automating employee onboarding, keeping customer data accurate, managing orders and inventory, or resolving finance and operations issues. When AI lives inside the flow of work, it can update records, trigger approvals, route work, and kick off the next step across systems. That's how teams operationalize AI and deliver measurable results. Cigo makes this possible. And now with Celiggo Aura, it's never been easier. Celiggo Aura gives you access to the entire platform through natural language, connecting your systems and turning intent into action. All of it under your control. Companies like Datab Bricks, PayPal, and Ollipop rely on Celiggo to run critical business operations at scale. Ready to operationalize AI? Visit celigo.com/helli AI. That's cel.com/howi AI. Brian, welcome to how I AI. Why I am so thrilled that you agreed to join the podcast is I think intercom has done it, which is you all have met the moment in sort of two ways. One clearly met the moment from a product perspective. were one of the first companies that had so I don't want to say legacy business but had a a going concern business that saw AI coming and really transformed how your product worked for customers and I'm a happy Finn customer they did not tell me to say that and then second what we're going to talk about is the team met the moment in terms of really understanding AI was going to change how in particular product engineering and design orgs and engineering organizations were going to work and you just went full speed at changing how the team works. What what drove sort of the urgency around meeting the moment and how did that come to be? Was it a single person? Was it everybody? What was your experience?

</details>

**Brian Scanland**: 我认为在某些方面，在工程和产品中推动 **AI** 采用是最容易的。因为我们公司非常专注于在产品上采用 **AI**，并成为 **AI First** 公司，以及我们如何思考产品未来、客户支持等等。我们也有非常明确的期望，比如我们看到了产品领域的可能性，而且作为 **AI** 的鉴赏者，我们非常清楚和明显地认为 **AI** 显然将在工程、产品和构建领域变得巨大。老实说，很多人都很不耐烦，想知道为什么今天没有发生？你知道，如果我们回到几年前，**Cursor** 业务有所起色，模型也越来越好，但它仍然没有变革性。它仍然不像整个业务都改变了，我们看到了大量的额外生产力。我们知道有潜力，但总觉得我们需要某种突破性时刻，或者需要发生一些大事，才能达到我认为我们现在开始实现的巨大速度优势。话虽如此，我们仍然想要更多。你知道，我们对目前的成就感到自豪。但是，我们不满足于迄今为止所取得的成就。

<details>
<summary>Original English</summary>

**Brian Scanland**: I think in in some ways it's been the easiest place to be driving out the adoption of AI in engineering and product. um because we've focused the company so much on focus and product on adopting AI and being AI first and how we think about the product future customer support and all that and we also had very clear expectations like we you know we we've seen what's possible in the product space and it's just very clear and obvious to us as like connoisseurs of AI it's like this is clearly going to be huge in engineering and product and building um and honestly there's been a lot of impatience for like why why isn't this happening today? You know, if we go back a few years and cursor is picking up a bit of business and the models are getting better and but it still wasn't transformative. It still wasn't like the whole business was changed and we're seeing vast amounts of extra productivity. We knew there was potential, but it still felt like we needed to have some sort of breakthrough moment or or something needed to to big had to happen for us to get to the kind of huge velocity wins that I think now we're starting to achieve. That said, we still want more. You know, we're we're proud of where we're at. Um, but we're we we're not content with uh with what we've achieved so far.

</details>

**Claire Vote**: 我感觉每三个月我都会有一个突破性的时刻。事实上，我觉得像 **Opus 46**（或 **GPT-4o**）这样的模型，我不知道，当那个特定模型问世时，真正改变了可能性。现在，我认为 **GPT54 U** 模型也非常出色。所以，在那个模型出现的那一刻，它真的影响了我个人对 **AI** 和工程的使用。你们在那时也看到了类似的转折点吗？

<details>
<summary>Original English</summary>

**Claire Vote**: I feel like every 3 months I have a a breakthrough moment. And in fact, I feel like Opus 46, I I don't know, something just like really inflected in what was possible when that particular model came out. Now, I think the GPT54 U models are also exceptional. And so, it was something about that one moment with models that really inflected my own personal use of AI and engineering. Did you all see the same sort of inflection around that model point?

</details>

**Brian Scanland**: 完全是。我想你可以回溯到去年 11 月或 12 月，突然间你开始意识到你必须更宏观地思考问题，或者说你的想象力现在是障碍，而不是工具。你花更少的时间去调整工具以达到正确的效果，它不再仅仅是自动补全，而更多地是直接给出你的想法，然后看看会发生什么。我想圣诞节假期也起了作用。我记得我们在圣诞节前几乎已经决定要全力投入 **Claude Code**，因为在那之前，这里有一些 **Cursor**，那里有一些 **Augment** 和其他工具。圣诞节假期真的很有帮助，我们看到所有人在 **Twitter/X** 上疯狂地谈论他们如何完成了这么多工作，他们正在构建所有这些东西。我圣诞节假期回来上班时，就觉得“好吧，一切都变了。”我们知道这里有些东西，并且开始看到它的迹象，但现在整个世界都相信了，或者至少 **Twitter** 和 **LA** 上的所有网红都相信了。

<details>
<summary>Original English</summary>

**Brian Scanland**: Totally. I think you can go back to was like November December last year h and suddenly you started realizing that you're you have to think bigger about things or or that your imagination is now the barrier not the tool you're spending less time massaging the tool to get it to the right place um and it's less about autocomplete and more about just literally giving us your your ideas and seeing what happens. Uh I think the Christmas break happened as well. I remember we we had pretty much decided before Christmas like hey we're going to go all in on clog code cuz up up to that point there was a bit of cursor here and there and augment and different tools. Uh and the Christmas break really helped like we uh that I just saw everybody go wild on Twitter X you know that uh people were uh talking about how this was like they were getting so much done and they were building all these things. I just come back to work after Christmas break going like, "Okay, everything's changed." Like, we we knew that there was something here and that we're starting to see the signs of it, but now the whole world is convinced or at least all of the influencers on Twitter and LA.

</details>

**Claire Vote**: 那就是我。是的，我实际上有点相信公司应该增加带薪休假（**PTO**）和育儿假政策，因为我认识的每一个所谓的休假中的科技界人士，都在度假时打开 **Claude Code**，回来时技能比休假前提高了十倍。所以，如果有人想要一个小小的 **AI** 素养提升秘诀，那就给人们放假去钻研，他们会带着比你预期更多的信息回来。好的，我想我们现在跳到重点，我喜欢这个重点，那就是我们将看到 **AI** 如何真正改变了你们在 **Intercom** 的交付方式。那么你能否稍微展示一下这在组织内部是如何改变的？我想你们都在衡量很多这方面的东西。是的。

<details>
<summary>Original English</summary>

**Claire Vote**: That that would be me. Yeah, I'm I'm actually kind of convinced that companies should increase their PTO and parental leave policies because everybody I know right now in tech that is quote unquote taking time off goes on their vacation and pops open clawed code and comes back like 10 times more skilled than they were beind their before their time off. And so if anybody wants a a little minor hack to AI literacy in your org, give people time off to hack and they will come back with more information than you expected. Okay, I think we're going to skip to the punchline which I love, which is we're going to see how AI has actually changed how you all ship at intercom. So can you just show us a little bit of how this has changed inside the or I think you all are measuring a lot of this. Yeah.

</details>

**Brian Scanland**: 所以，我想我们一直都很勤奋，正如你所知，作为 **Intercom** 内部的产品负责人，我们一直在努力获取人们的反馈，看看他们是如何使用这些工具的，并且像对待一个普通产品一样，真正地做所有事情。因此，我们花了很多时间将 **Claude Code** 与遥测技术连接起来，既连接到 **Honeycomb** 这样的工具，也将数据发送到我们的数据仓库 **Snowflake**，我们还将会话数据存储在 **S3** 中。我们挖掘这些数据以获取有用的见解。我们用来推动工具采用的主要事情之一是我们的 **CTO Darra** 设定了一个目标，要将 **R&D** 的吞吐量翻倍。我们使用 **Pull Request**（**PR**）作为一个粗略的、简单的衡量标准。你可以争论什么是好的衡量标准，什么是不好的衡量标准，以及衡量任何东西是否合适，但我认为，如果能完成更多工作，而且又快又有趣，那么为什么不是每个人都在交付更多东西呢？所以，这是一个基本的衡量标准，表明这些工具正在被采用，并且被很好地使用。当然，我们不容忍质量下降，而且我们是高度信任的环境，所以我们不期望人们通过操纵这些数据来获得好处。但我们的指标以及我在这里屏幕上展示的，你知道，这是一个经典的“数字上升”的趋势。我们从很久以前就开始跟踪这个数据，比如有多少 **PR**，以及其中有多少百分比是由 **Claude** 或 **Cursor** 或其他工具生成的。自从我们对 **Claude Code** 平台进行重大投资并全力投入，真正推动赋能，让人们自由探索并开始构建技能等等，同时也推动他们提高吞吐量后，我们看到了系统 **Pull Request** 吞吐量的巨大增长。你知道，去年我们的 **CI** 系统完全崩溃了。它熔断了，你知道，我的意思是它的成本增加了十倍。我们做了工作，修复了瓶颈，提高了 **CI** 系统的性能，它不再是瓶颈了。现在，代码审查是我们的瓶颈，但是我们今天仍然看到工程团队的吞吐量比九个月前翻了一倍。我们对此非常自豪，你知道，现在就想，为什么不能是十倍呢？

<details>
<summary>Original English</summary>

**Brian Scanland**: So I think we've been diligent as you know product owners inside of Intercom uh that we've been trying to uh get feedback from people and see how they're using uh the tools and uh really like just doing everything uh that we would normally do with a regular product. Um and so uh we've spent a lot of time hooking up cloud code with telemetry both into things like honeycomb um and data also going into uh snowflake where we have our data warehouse and we also store session data in S3. Um and we mind this stuff for for useful uh insights and um one one but one of the main things that we used to drive adoption uh of the tool was uh our CTO Darra setting a goal of us 2xing like doubling the throughput of R&D. uh and we use pull requests as a crude uh simple measure, but you know there's uh and you know you can argue back and forth about what's a good measure, what's a bad measure and whether measuring anything is appropriate or whatever, but I think it's reasonable to just have the expectation that if you can get a lot more done and it's so fast and fun, then why aren't why isn't everyone just shipping more stuff? H and so it's a basic measure that like the tools are being adopted um and that they're being used well and you know of course we don't tolerate lowering quality and we're high trust environments so we don't expect people not to gain these stats or whatever but our metrics and what I'm showing on the screen here is you know it's a classic number goes up h kind of thing that where we had we started tracking this back uh like how many uh pores and and what percentage of them were uh generated by either uh claw or cursor or whatever And um yeah, since our major investment in cloud code the platform and going all in on it and really pushing out like enablement and uh giving people uh freedom to explore and start to build skills and everything but also pushing them on on on we expect kind of throughput uh increase. We've seen a big big increase in in the throughput uh of pull request through our system and you know like last year like our CI system completely broke. it melted it, you know, but that I mean it got like 10 times as expensive and you know we did the work we fixed the bottlenecks we improved the performance of our CI system that stopped being the bottleneck. Um now uh code review is our bottleneck but um but like we're still but today we are seeing uh twice the number of throughput as we did compared to nine months ago on our engineering team. Um and like we're very proud of that and you know now it's like why can't it be 10x?

</details>

**Claire Vote**: 所以我喜欢这张图的地方在于，我过去二十年都在产品和工程领域工作，最近十年担任 **CPTO**。很有趣，我想回到你说的几件事，其中之一是：你必须像对待产品一样对待你的组织。我一直认为我的工作不仅仅是产品战略以及我们交付给客户的“大 P 产品”，而是设计我们的组织，可以说，按需输出创新，这才是工作。用不那么浪漫的说法，我的工作是投资 **R&D** 以获得积极的企业价值，这基本上就是我作为 **CPTO** 的工作。所以，我喜欢这张图的地方在于它是每个 **R&D** 员工的合并 **PR** 数量。我猜这包括产品经理和非工程类的 **R&D** 人员吗？还是纯粹指软件工程师？

<details>
<summary>Original English</summary>

**Claire Vote**: So what I love about this chart just for a moment is I had spent the last two decades of my career in product and engineering last decade of my career as a CPTO and it's so funny I want to go back to a couple things you said which is one you have to treat your org like a product and I always thought that my job was not just the product strategy and the capital P product that we were delivering to customers it was to design our organization to I would say like output innovation on demand which is that was the job and less romantic less romantically put my job is to invest R&D for positive enterprise value that was like fundamentally my job as a CPTO and so what I love about this is it's merge PRs per R&D head I'm presuming that includes does that include product managers and non-engineering R&D or is that purely software engineers

</details>

**Brian Scanland**: 是的，这包括所有的 **R&D** 部门。我们的设计师、产品经理和 **TPM** 确实如此，**Intercom** 的每个角色都在积极使用 **Claude Code**，并开始交付代码等等。而且我们也一直在招聘，所以这个数字并不是静态的。因此，原始的 **PR** 数量远不止是之前的两倍。所以，这包括从最新员工到添加文案或交付小改动的产品经理，所有这些都包含在这个数字中。我想提醒大家另一点是，过去三年我参加的每一次董事会会议都在问：“我们如何获得更多速度？”实际上，我参加过的每一次董事会会议都在问：“我们如何从 **R&D** 中获得更多速度？”当然，在过去三年里，问题变成了 **AI** 如何影响我们的速度。很有趣，我与很多人交流过，他们说 **AI** 并没有真正影响速度，我们并没有变得更高效。我就会想：是真的吗？因为我看到这样的图表，我就会说，这更接近我的直觉告诉我可能的情况，那就是如果你全力以赴，如果你准备好你的团队，如果你准备好你的代码库，如果你像你说的，拥有高度信任的文化，人们会看到这个然后说：“哦，他们正在提交这些小的 **PR**，或者工程师在玩弄系统。”我只是觉得我从未在那种文化糟糕到会发生这种事情的地方工作过，这种事情会成为设定这种雄心勃勃的有趣目标的结果。所以我姑且相信这个说法，我就会想，这在你的组织中怎么可能不发生呢？你的组织中，我的代码输入能力的物理限制被 **AI** 解锁了。你应该看到一些影响。所以，你知道，对于工程副总裁、**CTO**，甚至这些 **R&D** 团队的人来说，看看这个，想想，这都是可能的。这可能是一个粗略的衡量标准，但我认为，它是一个衡量组织中 **AI** 发展情况的恰当的先行指标。

<details>
<summary>Original English</summary>

**Brian Scanland**: yeah this is all of R&D and it's definitely the case that our designer ers and product managers and uh TPMs like every role in intercom is really actively using claw code and start and shipping code and all that. Um and also we've been hiring like this number has not been static. So uh the number of PRs uh the raw number is is dramatically higher than just 2x what it was a good while ago. So this is everything from your newest hire to uh your pro uh product manager who's like adding uh some copy or shipping like small changes whatever um you know that's all uh based in this number. The other thing I want to call out for folks is every board meeting I have been in for the last three years have said how are we getting well actually every board meeting I've ever been period has been how can we get more velocity out of R&D certainly in the last three years it's been how is AI inflecting our velocity and it's so funny I talked to so many people that are like it doesn't really inlect velocity we're not actually becoming that more efficient and I'm like is that true because I look at a chart like this and I say this is a little bit more of what my instinct tells me is possible, which is if you go allin, if you prepare your team, if you prepare your codebase, if you have, as you said, I think a high trust culture, people are going to look at this and say, "Oh, they're shipping these smaller PRs or like engineers are gaming the system." I just I have not worked at a place that has such kind of like bad culture that that would actually come as an outcome of setting some sort of ambitious fun target like this. And so I I take this as at face value and I think how is this not happening in your organization in your or like literally the physical limits of my ability to type code are unlocked by by AI. You should get some inflection there. And so, you know, for VPs of engineering, CTO, even people that are on these R&D teams, look at this and think, you know, this is possible and it may be a crude measurement, but it's, I think, an appropriate one as a leading indicator of of what's happening in your org around AI.

</details>

**Brian Scanland**: 是的。我们支持这一点，而不仅仅是告诉人们要更快地行动。你知道，我们真正地从第一性原理出发，思考如何开展工作。我们相信所有技术工作都将变为 **Agent-First**。而且我很想为此设定一个截止日期，那就是到月底，我们将全力以赴。它永远不会是第一个发生的事情，比如响应警报或在计划会议中，没有一个代理在那里做基础工作。我认为这是一个现实的期望，但它不仅仅意味着我们为了速度而更快。我们看到，通过审视我们花费时间的基础以及重新构想在 **Agentic** 世界中如何完成工作，我们正在更快地行动。老实说，如果代理没有变得更好，如果模型没有变得更好，如果工具链没有变得更好，我们今天拥有的构建模块就足以继续前进，审视我们今天的技术工作方式。我的意思是，通过技术工作，我指的是产品交付中的所有事情，并将其完全转变为 **Agent-First**，让我们能够提升到更高的层次，处理更高层次的问题，或者只是完成更多构建、交付更多东西，或者实现更高的质量。这些都在每个人的掌握之中，但你必须对变革非常开放。我想 **Intercom** 在过去一段时间里很幸运的是，我们对变革非常开放，无论是在产品方面，还是在使公司适应 **AI** 时代所需的工作方式方面，我们都开始看到成果。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah. And we support this with not just telling people to move faster like that's that uh you know, we're we're really looking from first principles of how to how to do the work. like we believe that like all technical work will become agent first. Um and I'd like to set like a deadline for that that you know at the end of the month we're just going to go all in and h it's never going to be the first thing that happens uh say in response to an alarm or uh in a planning meeting that there isn't like an agent in there kind of doing the the basic work and I I think that's a realistic expectation but it involves not just we're not just moving faster for the sake of it. We're seeing that we're moving faster by looking at the fundamentals of where we're spending our time and reimagining how that work could be done in an agentic world. And honestly, if like the if the agents didn't get better, if the models didn't get better, the harnesses didn't get better, uh we've got the building blocks just today to be able to just continue going moving around looking at how we do our technical work today. uh and like by technical work I mean everything in delivery of product and and move it to entirely be agents first and allow us to move up to higher level to be able to like work on higher level concerns or just getting more stuff built more stuff out there or higher quality that's all within every or grasp today but you have to be very open to change and I guess what's been fortunate to intercom over the last while is that we have been extremely open for change both in the product side of things and adapting the the company to how uh I think companies need to work now with AI and we're starting to see results.

</details>

### AI 使用的成本与质量考量

**Claire Vote**: 是的。我看到这张图表的另一个想法是，我们录制这个节目是在 2026 年春季，而 **Anthropic** 刚刚表示他们的收入突破了 300 亿美元，我想这比几个月前的 190 亿又增加了。我怀疑他们的收入图表和你们的 **R&D** 人均合并 **PR** 图表有点像。那么，你们是如何考虑成本权衡的呢？我们都在消耗 **Claude** 代币。是的，你知道，效率或产出正在提高，吞吐量也在提高，但成本是否按比例增长？你们是否担心这是现在的问题？你们甚至担心它吗？你们是如何考虑这个问题的？

<details>
<summary>Original English</summary>

**Claire Vote**: Yeah. The other other reflection I have upon looking at this chart is we're recording this in kind of the spring of 2026 and Anthropic just said that they crossed 30 billion in in revenue I think up from 19 a couple months ago. And I I I suspect their revenue chart looks a little bit like your merge PRs per R&D chart. So, how are you all thinking about the trade-off on cost here, right? Like we're all consuming clawed tokens. Yes, you know, efficiency or output is going up, throughput's going up, but is cost scaling proportionately? Are you all worried about is that the problem right now? Are you even worried about it? How do you think about that?

</details>

**Brian Scanland**: 是的，我们确实很担心，因为账单看起来就是这样。你知道，我职业生涯中花了很多时间担心 **AWS** 成本，担心我们的利润等等。然后突然间，这些成本出现了，而且它们与我们之前见过的任何增长都显得不成比例。这就像招聘了全新的办公室的人员一样。但目前我们的态度是，大家就用 **Opus** 来做所有事情吧，即使它有一个百万上下文窗口。你知道，我们只是使用 **API** 计划，所以一切都是按需进行的。我们认为在当前阶段，尽快行动并稍后再担心账单能获得足够的“阿尔法”或好处，因为我们会从后续收益中获益。也许这就是 **Intercom** 的立场。我不认为这对所有企业来说都是现实或可行的。老实说，我确实很尊重当你真正需要考虑你的 **token** 使用量时，它会迫使你更加深思熟虑，有时甚至能带来更好的结果。你知道，你不需要 **Opus** 来做所有事情，有很多更快的模型。所以，我们只是在避免那个优化阶段，直到我们从对这个平台的投资中获得实实在在的好处。所以，我认为这项投资，而且我认为我们目前正将其视为一项投资，是值得的。但你知道，如果这样下去，我们都应该为 **Anthropic** 工作。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah, we're definitely worried uh in that the build is looks exactly like this and and you know I I spent a lot of my career worrying about AWS costs and uh worrying about our margins and stuff and then suddenly you've got these costs showing up uh and they're disproportionate to the growth that we've seen anywhere before. It's like hiring whole new offices of people. Um and but at the moment our attitude has been look everyone just turn on opus for everything one million with uh context window you know we uh we just use the API plan so it's all just on demand and we we think that there's enough uh alpha or benefit in at this point going as fast as possible and caring about the bill later because of the later benefits we'll get and maybe that's a position of where intercom is. I don't think it's realistic or feasible for absolutely every single business to do it. And honestly, I do kind of respect when you have to actually think about your token use and how that can kind of force you to be more considerate or it sometimes even gets you better results. You know, you don't need opus for everything like uh there's there's faster models out there. Um and so we're we've we're just kind of avoiding that optimization phase until a point of where we until you know we've gotten serious benefits from investment in this platform. And so I think this investment and I think it's it we are treating it like an investment at this point um is worthwhile. Uh but you know if this keeps going at this rate yeah we should all work for Antropic you know.

</details>

**Claire Vote**: 我觉得以他们招聘的方式，我们最终都会为 **Anthropic** 工作。好的，还有一件事，因为我觉得，你知道，人们会看到这个，尤其是工程师，他们会说“好吧，你提交了更多的 **PR**，但那都是垃圾。”你知道，你们都在衡量质量，在这个之外，在交付所有这些东西之外。那么，你认为这如何影响了你们对质量、客户价值或你们最终想要实现目标的衡量？不仅仅是代码行数。

<details>
<summary>Original English</summary>

**Claire Vote**: Um I think the way they're hiring we're all going to end up working for Anthropic. So okay and then one other thing because I think you know folks are going to look at this certainly engineers and they're go okay like you're shipping more PRs but it's all slop it's all garbage. uh you know I know you all are measuring quality on the outside of this on the other side of shipping all this stuff. So how have you seen this inflect measurements around quality or customer value or what you're trying to achieve at the end not just lines of code?

</details>

**Brian Scanland**: 是的，我有一张可以分享的独立图表，挺有趣的。我们开始关注从编写一行代码到在我们的新闻频道（比如更新）上发布所需的时间。这个时间在过去几个月里持续下降。现在，我们并没有为此优化，但我们对此很感兴趣。另一件事是，我们交付的东西的数量在过去几个月也迅速增加。这应该是一个滞后指标。所以我们相信，这些数字——这种数量的增加——已经体现在真实的功能、真实的产品中，这些产品正被我们的客户使用。我们甚至进行了一些实验，例如一个人在构建一个看起来像是完整产品领域的功能时，能走多远才能销售出去。所以我们非常认真地对待这件事。我们也非常关心质量。我们一直与 **Stanford** 的一个研究小组合作。我们向他们提供了数据，你知道，主要是为了获取任何见解，以确保我们没有盲点。你知道，我绝对会参与每一个事故。我是一个“救护车追逐者”，我没有看到常规事故、宕机或客户面临的问题有任何增加。我们遇到了一些奇怪的问题，但与生产无关。有趣的是，**Stanford** 数据上周我们检查时显示，他们对代码质量的衡量认为代码质量正在提高。你知道，模型在改进，代理在改进。我们正在添加越来越多的指导和技能，所有这些都会促使人们沿着一条应该带来更高质量输出的道路前进。但当工具能够独立地做到这一点时，看到它真的很棒。现在，细节决定成败，你需要真正深入了解在你的环境中质量意味着什么。但是，你知道，我们没有看到人们所担心的一些事情。我们拥有一个成熟的环境。我们是一家有 15 年历史的 **SaaS** 公司。我们已经这样做了很多年。**AI** 和提高你的速度会放大你的优点和缺点。幸运的是，我认为我们在软件交付方面有很多优点可以利用。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah, I have a standalone graph that I can share which is kind of interesting. Um, and so we've started to look at the uh the time it takes from the first line of code written in a feature to the time it gets posted on our news channel like our updates. Um, and that's uh that that has decreased consistently over the last few months. Now, we're not optimizing for this uh but we're interested in it. And the other thing is like the sheer volume of things we have shipped also appears to have kind of just rapidly increased in the last few months as well. And that's that should be a bit of a trailing metric. So we believe that these numbers this like increase in volume is been borne out in real features, real products that our customers are using. And even we've been running some experiments like how far can one person get on their own building um something that's plausibly a whole entire product area um feature to be able to sell. Uh so this is something we're taking seriously um and it's uh we also care a lot about quality. We've been working with a research group in Stanford. We've been giving them our data and uh you know mostly just looking for any kind of insights to make sure we're not blind. you know, I join absolutely every single incident. I'm a ambulance chaser and I make like uh and I'm not seeing any increase in kind of regular kind of incidents or outages or customerf facing problems. Um we've had a few kind of weird problems but not related to production. Um and uh but also uh the the interesting thing from the Stanford data when we checked back in on it last week was that their measures of code quality reckoned that the code quality was improving. Um and you know the models are improving, the agents are improving. We're adding more and more guidance and skills and all these kind of things which I think do craft uh or do force people down a road which should result in higher uh quality output. But um it's great to see when to when when tools kind of can independently pull that out. Uh now devils in details, you got to go into the we got to actually really have a strong sense for what quality means in your own environment. But, you know, we're not seeing some of the things that people are worried about out there. Um, but that's it. We got a mature environment. We're 15y old SAS company. We've been doing this for years. Uh, you know, AI and speeding up your velocity will will magnify all of your strengths and weaknesses. And thankfully, I think we've got a lot of strengths on the software delivery side of things that we've been able to take advantage of.

</details>

**Claire Vote**: 我想在这里强调的一点是，你说你的代码质量提高了，这又是我直觉上一直认为是最终目标的事情，但很多工程师不相信这是真的。但是，当你有能力处理技术债务，当你有能力解决代码库中的难题时，你确实可以做到这些事情，无论是开发者体验、安全合规性、代码库的整体可维护性、不稳定的测试、改进 **CI/CD**，所有这些事情都变得非常容易解决。不仅仅是技术上，不仅仅是工程师能够执行，而是业务本身，我感觉人们不理解这一点，业务（大写 B）对内部项目的能力是有限的。这意味着，我们只能将如此多的 **R&D** 分配给代码质量改进。这就是我们的生活方式。不幸的是，我们不会从代码质量中产生 **ARR**（年度经常性收入）。但当做这些事情的成本降低时，你就能作为一家企业说：是的，我们应该投资。第一，因为我们能；第二，因为它能为我们的代理、产品经理和工程师解锁外部的速度。所以我认为这实际上是人们投资代码质量的一个非常重要的时刻。我经常建议许多 **CTO** 和工程副总裁，在思考如何让他们的工程团队 **AI** 化时，我说：“修复你代码库中所有你讨厌的东西，花一个月时间，看看我们能多快地完成它。”那会感觉非常好。好的，我们已经闲聊了。我们已经展示了图表。重点是 **AI** 如何真正交付代码。所以让我们切换到那个话题。我们可能会回到所有这些话题。我觉得它们都很有趣。但是，你将向我们展示你们如何在成熟的代码库、成熟的组织中，真正地将事情上线，以及你们在仓库中做了一些什么来使这成为可能。

<details>
<summary>Original English</summary>

**Claire Vote**: One thing that I want to kind of call out here which is you said that you've seen your code quality increase which again intuitively I've always believed to be the ultimate endgame of this and every engineer not every many engineers that I've talked to and just don't believe it to be true but when you have the capacity to take on tech debt when you have the capacity to take on the dragons in in your codebase you actually can do those things whether it's developer experience security and compliance, just general maintainability of your codebase, flaky test, improving your CI/CD, all those things become very tractable. Not just technically, not just can an engineer execute on it, but actually the business, and I feel like people don't appreciate this, the business, capital T, capital B, only has so much capacity for internal projects. Meaning, we can only allocate so much of R&D towards improving code quality. just just how we live. We don't generate ARR on code quality, unfortunately. But when the the um when the cost of doing that compresses, then you're able to say yes, as a business, we should invest there. One, because we can, and two, because it'll unlock velocity on the outside for our agents and for our product managers and for our engineers. And so I think this is actually a really important moment for folks to invest in code quality. And I often advise a lot of CTOs and VPs of engineering when figuring out how to get their engineering team AI pilled. Say everything you hate about the codebase, go spend a month fixing and see how fast we can speedrun that. That's going to feel really good. Okay, we've chitchated. We've shown graphs. Point of how AI is to actually ship some code. So let's switch over to that. We can probably come back to all these topics. I think they're so interesting. But you're going to show us how you all again in your mature code base, mature organization, are actually getting things live and some stuff you've done in the repo to make that possible.

</details>

**Brian Scanland**: 是的，当然。所以，我将在我们宏伟的 **Ruby on Rails** 单体应用中做一个相当微不足道的改动。这个应用有数百万行代码，所有的测试。是的，这个代码库比 **Intercom** 还老。它是在 **Intercom** 成立之前创建的。你知道，它有它的问题，但我们爱它，我们维护它。所以，我只是要做一个相对简单的改动，添加一个龙虾表情符号的 **Rails** 重定向到 chatpure.ai。所以，当我在演示什么的时候，我也会尝试给 **Claude** 提示。我不知道它是否有帮助，但这让我感觉更好。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah, sure. So, I'm going to do a fairly trivial change in our majestic Ruby on Mails monolith. So, this is millions of lines of code, all the tests. Uh, yeah, it's the code base is older than intercom. it was uh created before Incom was incorporated. Um and you know it's got it's got its problems, but we love it and we we tend to it. Um and so uh I'm just going to do a relatively simple change of adding a uh a lobster emoji rails redirect to chatpure.ai. So also I I try and give hints to cloud when I'm actually demoing something. Um, I don't know if it actually helps, but it makes me feel better.

</details>

**Claire Vote**: 呃，只是想在这里增加一点紧迫感，你知道。

<details>
<summary>Original English</summary>

**Claire Vote**: Uh, just trying to add a bit of urgency here, you know.

</details>

**Brian Scanland**: 我想那是每个人的提示策略，我不知道它是否有帮助，但这让我感觉更好。

<details>
<summary>Original English</summary>

**Brian Scanland**: I think that's everybody's prompting strategy, which is I don't know if it helps, but it makes me feel better.

</details>

**Brian Scanland**: 完全是。所以这是一种很好的与代理互动的方式，你知道。我们在这里看到的是，我的意思是，它已经弄清楚了重定向的位置。它有一个漂亮的龙虾表情符号。它正在问我是否要打开 **IP**。所以显然我是要的。而且，我想它实际上已经得到了正确的 **URL**。它是 app.inter.com，它将包含 **URL**，但我们稍后可以告诉 **Claude Code**。所以，我们在这里看到的是，首先，一个重要的点，我只是想向上滚动。我们很早就注意到，当我们开始让 **Claude Code** 编写所有代码时，你知道，我们现在已经远远超过 90% 了，它创建的 **Pull Request** 描述非常糟糕。它会描述代码，而这在 **Pull Request** 中是最不有趣的部分。你作为一个人类，甚至作为一个审查代码的代理，你想知道 **Pull Request** 背后的意图。你想知道有趣的部分，这与什么相关。你知道，**LLM** 非常擅长只是复述或将代码重写成英文，这很好，但这不是我们需要的。所以我们注意到，当人们使用 **Claude Code** 时，我们创建了一个 **LLM** 评估器来评估，因为我们怀疑 **Pull Request** 描述的质量正在下降。所以，我们创建了一个 **LLM** 评估器来评估一个好的 **Pull Request** 应该是什么样子，然后让 **LLM** 评估器去检查几个月的数据。是的，趋势非常糟糕。趋势是朝着一个方向发展的。这很糟糕。你知道，人类在创建 **Pull Request** 描述方面也不是完美的。有时它们是空白的，或者其他什么。但我认为，通过我们使用 **Claude Code** 这样的工具，并围绕它建立这些平台，你真的必须推动更高的标准。你想要尽可能接近完美。这显然是我们不容忍降低标准的情况。所以我们创建了一个名为 **Create Pure** 的技能。它所做的就是使用会话中的所有上下文来描述 **Pull Request**。所以它不是什么高深的技术。但通常会话知道它为什么要做这件事。所以，我们必须强制它。你知道，我们开始告诉人们：“哦，就用 **Create PR** 技能吧。”然后人们不会用。你真的不希望人们记住事情。所以我们把它作为一个钩子。所以如果 **Claude** 决定使用 **GitHub CLI** 来打开一个 **Pull Request**，我们就会阻止它，我们会说：“是的，你必须使用 **Create PR** 技能。”而且你可能还要想出不同的文本描述。如果上下文不够，我可能会采访你。希望这里有足够的上下文。但重点是，这是一个平台，我们想要好的结果，我们衡量输入和输出。在我们实施这个之后，**LLM** 评估器认为我们现在做得很好，所以我们有更高质量的 **Pull Request** 描述。现在，这不是世界上最重要的事情，这不会让 **Intercom** 的收入增加两倍或十倍，但它是所有这些复合的小工作，当你把它们组合起来时，意味着你有一个非常有能力的工程师，他在我们的环境中恰当地工作，这就是我们对每个小技能和钩子的投资所在。所以它们看起来几乎微不足道，但你知道，它们会带来更好的结果。所以我们在这里看。它正在创建一个 **PR**。我得检查一下它在做什么。这可能也会自动批准，这很酷。我们甚至可能会看到一些 **Pull Request** 反馈正在进行中。还在构建中。我们几分钟后再回来。

<details>
<summary>Original English</summary>

**Brian Scanland**: Totally. And so that's a nice way to uh interact with the agents, you know. Um, and so what we're seeing here is, I mean, it's already kind of figured out uh where to put a redirect. It's got the nice lobster emoji. Um, and it's asking me if I want to open IP or uh, so obviously I do. And, uh, I think it's actually gotten the URL run. I It's app.inter.com, which will have the URL, but we can tell, uh, cloud code later on about that. So, what we're seeing here is, first of all, an important point, I'm just going to scroll back up. One of the things we noticed early on when we started getting cloud code to write all of our code um and you know we're up well above 90% now is that it would create pull request descriptions that were kind of terrible. They it would describe the code and that's the least interesting part of a pull request. You actually as a human or even as a an agent reviewing code you want to know the intent behind the pull request. you want to know the interesting bits, what's kind of related to this and h you know LM are very good at just regurgitating or rewriting code into English that's fine but it's not what we need and so one of the things and we noticed as well when people were using cloud code we we we created an LLM judge to evaluate uh because we had suspicions that the quality of the pull request descriptions was going downhill. So, we created an LLM judge to evaluate what does a good pull request, we decided what a good pull request description uh should look like and then got an LM judge to go through uh all like months and months of data. And yeah, the trend was awful. The trend was going in one direction. Um and this is bad. Um and you know, look, humans aren't perfect at creating pull uh pull request descriptions. Sometimes they're just blank and whatever. Um, but I think with uh our use of tools like cloud code and setting up these kind of platforms around it, you really have to be pushing for like higher standards. You want as close to perfection as possible. And this was clearly something that we're just not going to tolerate a lowering of standards or in our environment. So we created a skill called create pure. And what it does is is it uses whatever context it can from the session to describe the pull request. Uh, so it's not quite rocket science. Um but often the session knows exactly why it's doing the thing and so uh but then we had to kind of force it in you know we we started we told people like oh just use the create PR skill and then people would want wouldn't use it you don't really actually want to be have people remembering things so we added it as a hook so if claud decides to uh you know use the GitHub CLI to open a a pull request we just block it and we say yeah tough you need to use the create PR scale And also you're probably going to have to uh like figure out a different text description. H and then I might interview you if there's not enough context there. Hopefully uh there's enough context in this. But the point being that you know this is a platform we want great outcomes and we measure the inputs and outputs and after we we put this in place the LM judge reckon we're doing a great job now and so we're at higher quality pull request um descriptions. Now this is not the most important thing in the world like this is not going to get intercom to 2x or to 10x revenue or anything like that but it's the all of the composite little jobs that like are when you assemble means you have an extremely competent engineer who works appropriately in our environment and that's where we're putting our investment for each little skill and hook to do these things. So they almost look inconsequential, but you know, they result in better outcomes. And so we look through here. It's uh it's creating a PR. I'm going to have to check on what it's going. This probably will be automatically approved as well, which is pretty cool. And we might even see some pull request feedback as well in action. Um still building. We'll come back to it in a couple minutes.

</details>

**Claire Vote**: 我想为那些不知道的人，在你描述为什么设置这个技能来改进 **PR** 的时候提一下：一个技能基本上就是一组指令，有时还有脚本，**LLM** 或代理工具可以在你的流程中的特定步骤调用它。在你描述为什么你把这个技能组合起来，并对 **PR** 描述如此坚持己见的时候，我一直在想，在工程领域，我们已经能够设计出非常有主见的 **CI/CD** 流水线。所以，代码从编写到部署到生产环境的过程，我们都有，我的意思是你在 **GitHub** 上看到了，我们有所有的检查、**Lint**、预部署、预检、预览分支等等，所有这些都是在代码编写之后进行的。但我认为技能真正有趣的地方在于，你可以在编写代码时，就对其流程如何进行，引入一些确定性。我们以前无法做到这一点，因为它必须经过人类的思考和操作，而人类更难被置于这些结构化的护栏之中。我们过去会通过编写 **Wiki** 或制定标准操作程序（**SOP**），其中会说：“请遵循步骤 A、B、C、D、E。”但现在，你可以很容易地在整个团队中强制执行这些标准，我认为这并不是微观管理，它实际上只是让每个人的“黄金路径”更加顺畅地通向生产，所以我认为这与我们处理 **CI/CD** 的方式有一个非常有趣的并行关系，这也是我们从产品管理角度处理更上游事情的关键。

<details>
<summary>Original English</summary>

**Claire Vote**: One thing I want to call out for folks as as you were describing sort of why you put in this skill to improve the PR and for those who don't know um a skill is basically just like a set of instructions and sometimes scripts that a LLM or a agent harness can invoke at a certain step in your flow. One of the things that I was thinking as you were describing why you put this skill together and got really opinionated about PR descriptions is in engineering we have been able to architect really opinionated CI/CD pipelines. So how written code goes from being written to deployed in production and we have I mean you saw it in GitHub we have all these checks and lints and pre-eploy you know pre-flight things and preview branches all these things once the code is written but what I think is really interesting about skills is you can bring some of that determinism to as you write the code how you want that process to go and we used to not be able to do it because it used to flow through the hearts and minds and hands of humans which are much harder to put in these structured guard rails and we would do this by writing wikis or having you know SOPs where it said can you please follow step A B CDE E and now you can just make it really easy to enforce those standards across a team which I don't think is micromanaging it's actually just making everybody's golden path much smoother to production and so I think there's this just very interesting uh parallel to how we've approached CI/CD key to how we approach things more upstream even from the product management perspective.

</details>

**Brian Scanland**: 完全是。我们正在朝着一个“软件工厂”的方向发展。工厂擅长什么呢？你知道，就像 **IKEA** 工厂一样。所有的家具都一样，所有的部件都不同，你知道如何组装它。看，它不是你的手工制品，它也不是尖端产品什么的，但它非常可预测，而且，你知道，当它从工厂的另一端出来时，它具有一定的质量，并符合一定的标准。所以，虽然 **Pull Request** 描述，再说一遍，它们对于工厂或 **Pull Request** 或其他什么来说，都不是决定成败的关键，但它是那些优质工作所具备的品质之一，是可靠的、可预测的，然后当它们组合在一起时，你就拥有了你的 **IKEA** 工厂。

<details>
<summary>Original English</summary>

**Brian Scanland**: Totally. We're on this movement towards a software factory and uh what factories are great at is uh you know like an IKEA factory or something. It's all the same furniture, all the different bits and you know how to assemble it and uh look it's not your artisan stuff. it's not uh or it's not cutting edge or whatever, but it's very predictable and uh you know has a certain quality and meet certain standards when it comes out the other side of the factory. And so while pull request descriptions again, they're not they're not make or break for the factory or the pull request or whatever, um it's one of those qualities of just good quality work that's reliable, predictable, and then when assembled together, you've got your IKEA factory.

</details>

**Claire Vote**: 嗯，人们肯定不想感觉自己是生产线的一部分，对吧？所以，你可以在流程中添加这些东西，它们实际上能提升水平，并达到工程团队的标准，这真的有助于团队中的人类工程师感觉他们在一个重视质量的地方工作。所以我很欣赏你为此付出的努力，这些幕后钩子和技能，因为我相信这能强化一种文化，这种文化被要求以非常快的速度交付，并以不同于以往的方式交付，而且你仍然关心他们阅读 **Pull Request** 描述的体验，你知道，他们满足了你的质量标准，我觉得这让每个人都更开心。

<details>
<summary>Original English</summary>

**Claire Vote**: Well, and people don't want to feel certainly engineers don't want to feel like they're part of a slot factory, right? And so these things that you can add into the flow that actually uplevel and meet the standards of the engineering team really help your human engineers on the team feel like they're working at a place that values quality. And so I appreciate that you've put those that effort into um into these behind the-scenes hooks and skills because I'm sure it reinforces to a culture that's being asked to move very fast to ship how you know ship things differently than they have before that you still do care about their experience reading pull pull you know pull request descriptions um their um you meet their bar for quality and I just think it makes everybody happier.

</details>

**Brian Scanland**: 是的。是的。当机器人能够产出你期望你最优秀的工程师做出的工作时，那真是太棒了，你知道。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah. Yeah. Well, it's great when the robots just produce the work that you'd expect of your best engineers, you know.

</details>

**Claire Vote**: 是的。而且，你知道，也许当你实现这一目标时，我还认为软件工程中还有更多有趣的问题需要解决。我们可以在稍后的节目中讨论你们在产品端和技术端正在解决的一些有趣问题。我认为不乏为客户解决的、需要智力刺激的、创造性的难题，而编写重定向代码肯定不是其中之一。

<details>
<summary>Original English</summary>

**Claire Vote**: Yeah. And I, you know, maybe as you get this live, I also think there are just still such more interesting problems to solve in software engineering. And we can talk a little bit later in the episode about some of the interesting problems that you all are solving on the product side, on the technical side. I think there is no lack of hard, intellectually stimulating, creative problems to solve for customers and coding redirects is just 100% not one of them.

</details>

**Brian Scanland**: 嗯，那么我们的重定向上线了吗？还是快了？

<details>
<summary>Original English</summary>

**Brian Scanland**: Um, so did we get do we get my redirect live or are we close?

</details>

**Claire Vote**: 还在那里。我正在等待自动审查启动，但我们可以稍后再回来。所以，接下来我想展示的一件事可能是我们部署的一些遥测技术。我们看到，你知道，有不同的技能被调用，我们不喜欢盲目运行这样的系统。你需要知道人们使用它的情况如何，人们是否在使用这些技能，你知道，就像你向客户交付产品时所期望的基本信息一样，比如我可以在哪里看到使用情况？我如何争取使用？出了什么问题，或者没有出什么问题？所以我们使用不同的机制收集了一堆遥测数据，并将它们存储在不同的地方。我们最开放的一个是，我们收集了技能和类似功能的基本使用信息，并将其发送到 **Honeycomb**。所以我们只是有一个部署到所有笔记本电脑的共享密钥。任何人都可以进去查看这些数据。所以如果你在 **Intercom** 内部开发一个技能，而且有数百人这样做，那么你很容易就能发现，好吧，谁在使用这个？他们什么时候使用它？你可以将此作为发现技能使用情况的起点。不出所料，我们拥有的主要技能是像创建 **PR** 这样的。**Admin tools** 是我们的管理工具 **API**，或者我们前面有一个 **MTP**。**Build Kai** 是我们的 **CI** 系统。**Snowflake logs** 是我们放置 **Snowflake** 日志的地方。所以你可以从这里看到，很多工作，很多被调用的技能都围绕着构建，然后查看我的东西在哪里，也许还有一些故障排除类型的信息。所以这是第一步。如果你没有这个，那么很难拥有一个大型系统，比如所有这些数百个技能，以及数百个创作者在没有良好遥测数据的情况下在这个领域工作。我们还做的一件事是，我们还会收集所有的会话数据并将其放入 **S3**。我们对其进行匿名化处理。我们做了一些事情，以确保我们没有做任何过于私密的事情。你知道，人们在他们的会话中放入各种各样的东西。

<details>
<summary>Original English</summary>

**Claire Vote**: It's still there. I'm waiting for an automatic review to kick in, but uh we can come back to it. So, one of the things I would like to show next might be some of the telemetry that we have in place. So we saw that uh you know there was different skills getting invoked and um and we don't like flying blind uh to run a system like this you need to know how well people are using it uh are people using these skills at all uh you know the kind of basic information that you'd expect of like when you ship a product to your customers uh like you know where can I see the usage how can I fight for the usage what's what's going wrong or what's not going uh wrong and so we collect a bunch of telemetry using different mechanisms and have different homes for it. The most open one that we have is we collect uh basic usage information for skills and and the like uh and we send it to Honeycom. So we just have a shared key that deployed to all of our laptops. Um and uh anyone can go in and kind of look through this data. So if you're developing a skill internally in intercom and like hundreds of people do this um it's very easy for you to go in to discover like okay how where's who's actually using this? uh when are they using it? And you can kind of use this as a kickoff to like follow up on um uh just like basic discovery of usage of your skills and all. And like unsurprisingly the kind of main skills that we have are things like creating PRs. Admin tools is our admin like internal tooling APIs or um where we have an MTP in front of it. Build Kai is our CI system. Snowflake logs is where we put snowflake. So you can see from this like a lot of work uh a lot of the skills are being evoked are all around the building and then seeing where my stuff is and maybe some troubleshooting type information as well. Um and so this is the first kind of step. It's like if you don't have this it's hard to have a large system uh like all these hundreds of skills and uh hundreds of creators working in this area without having decent telemetry. The the next thing we do as well is we also collect all of the session data and put it into uh S3. And so we anonymize it. We do a few things to make sure we're not doing anything too private. Uh, you know, people put all sorts of stuff in their sessions.

</details>

**Brian Scanland**: 他们对他们的会话大喊大叫。

<details>
<summary>Original English</summary>

**Brian Scanland**: They yell at their sessions.

</details>

**Brian Scanland**: 是的。人们有时会与 **Claude** 建立私人关系，我们并不想知道这些，但我们确实希望能够深入了解事情的进展。你知道，我认为了解会话的退出率，比如人们多快地达到了有用的结果，无论是 **PR** 还是其他什么。这种信息非常有趣，所以我们正在收集大量的会话数据，并且正在做不同的事情。我在这里屏幕上展示的是一个我们组装起来的非常简单的工具，它只为你提供一些个性化的见解，你知道，现在你也可以在 **Claude** 内部做这些，**GitHub** 上也有很多技能可以进行会话分析。但我认为我们只是在我们收集会话的系统之上构建了一个小工具，给人们反馈。我们感兴趣的是提供关于他们的会话进展如何以及他们如何适应的反馈，以及你如何看待自己使用 **Claude Code** 与组织中其他人相比的情况。你知道，我在这里做得还不错，大约在 79% 的水平。你知道，总有人在每个百分比的底部。这里有一些有趣的反馈，它告诉我，或者说我几周前对 **Claude** 有点恼火，因为我设置了 **Gogg** 来与我们所有的内部 **Google** 服务互动，但它总是试图做错事，我有点抱怨它，结果它把东西添加到了 claude.mmd 等等。它在这里有点抱怨我，或者说它提醒我，这不是与 **Claude Code** 互动的有效方式。所以，你知道，这对我来说是一个很好的提示，去实际修复我的记忆或其他什么。我们所有人都一样，即使在 **Intercom** 内部，人们也处于不同的采用水平。人们正在加入 **Intercom**，他们可能以前没有见过这样的系统，他们想知道事情进展如何并获得反馈。所以，这是一个例子，说明我们如何努力汇总这些信息，为人们提供有用、可操作的见解，让他们感到受到支持，而不是简单地给他们一个 **API Key**，然后说祝你好运。而是，不，我们了解增长是什么样子，以及人们在使用这些工具时所经历的进步，并且不断改进。我们希望支持所有这些。所以，这是我们正在利用会话数据做的事情之一。还有很多其他事情正在进行中。比如，我们希望能够了解哪些技能质量最高，哪些技能能让你尽快达到结果，哪些需要改进，你知道，哪些技能表现不佳，或者可能需要一些关注来改进。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah. And yeah, people have personal relationships at times with uh with Claude and like we don't really want to know about that, but we do want to be able to dive deeper into uh how things are going. You know, I think um understanding like how what the dropout rate of sessions like did how quickly people got to something useful like whether it was a PR or something like that. uh this kind of information is pretty interesting and so we're harvesting a lot of session data and we're doing different things. This is what I'm showing here on the on the screen is like a very simple tool that we put together which just gives you some personalized insights and you know you can do this inside claude these days as well. There's and there's plenty of skills out there on GitHub where you can do session analysis. But I think we we just built a little tool on top of our session collection uh system to give people feedback. And it's feedback that we're interested in giving feedback about how their sessions are going and and how they're kind of fitting in, how you should think about your own, I guess, use of clog code compared to everybody else in the org. And you know, I'm not doing too bad here. It's like 79th percentile. Um you know, someone has to be down the bottom of every percentile. Um there's and there's some interesting feedback here like uh it's tell it's it's kind of getting annoyed at me or rather I was getting annoyed at Claude a few weeks ago because I'd set up Gogg to interact with um all of our Google stuff internally um and uh but it kept on trying to do the wrong thing and I was kind of giving out to it and it ended up adding stuff to claude.mmd and stuff um and it's it's kind of giving out to me here or it's reminding me that this wasn't a very effective way to interact worked with cloud code. So, you know, it's a good prompt for me to actually go and fix up my memory or whatever. And like we all like people are at different levels even on intercom. Um people are different levels of adoption. Uh people are joining intercom they may not have like seen a system like this before and they want to know how things are going and get feedback. And so, uh, this is one example of how we're just trying to pull together this information to give useful, actionable insights, uh, to people so that they can they feel supported and that we're not just throwing them an API key and saying best of luck. It's like, no, we've got we understand what growth looks like and the progression that people go through um, when they're using these tooling um, and getting better and kind of self-improving. We want to support all that. So, this is one of the things that we're doing with the session data. There's loads of other things that's work in progress. Um, like being able to like we want to get insights to which skills are are are the highest quality, which gets you which which skills get you to your results as quickly as possible and then which ones need work, you know, which ones uh aren't working out so well or might need a bit of attention to improve.

</details>

**Claire Vote**: 本期节目由 **Cursor** 赞助。如果你们一直关注 "How I AI"，你们已经知道了。**Cursor** 是我最喜欢用 **AI** 编写代码的方式。无论我是使用计划模式来构建一个雄心勃勃的功能，在我的编辑器中审查 **AI** 生成的差异，还是启动 **Claude** 代理来多线程处理我们的路线图，我都会选择 **Cursor** 作为我最喜欢的多模型编码平台。比自己用 **Cursor** 构建更好的是，我喜欢与 **Bugbot** 协作修复代码安全和质量的 **PR**，并开始依赖 **Cursor** 的自动化代理来保持我们的代码库清洁。不只是我。最雄心勃勃的团队也喜欢 **Cursor 2**，包括 **Stripe**、**OpenAI** 和 **Figma** 的工程师。准备好构建更多了吗？我们为 "How I AI" 的听众提供 50 美元的 **Cursor** 积分。请访问 chatardd.ai/howi AI 领取你的积分。通过访问 chatpd.ai/howi AI 可获得 50 美元的 **Cursor** 积分。在看你的技能列表之前，我必须暂停一下，因为我对那部分太兴奋了。但如果人们没有在观看，他们可能错过了你刚才展示的有多么惊人。所以我要重申一下，第一，你已经用遥测技术武装了你所有的内部技能，你正在使用 **Honeycomb**。嗯，我喜欢 **Honeycomb** 团队。

<details>
<summary>Original English</summary>

**Claire Vote**: This episode is brought to you by Cursor. If you all have been watching How I AI, you already know this. Cursor is my favorite way to code with AI. Whether I'm using plan mode to build out an ambitious feature, reviewing AI generated diffs right in my editor or kicking off cloud agents to multi-thread our roadmap, I reach for cursor as my favorite multimodel coding platform. Even better than building myself in cursor, I love collaborating with Bugbot to fix PRs for code security and quality and have begun relying on Cursor's automated agents to keep our codebase clean. It's not just me. The most ambitious teams love Cursor 2, including engineers at Stripe, OpenAI, and Figma. Ready to build more? We're giving $50 in Cursor credit to How I AI listeners. Claim your credits at chatardd.ai/howi AI. That's $50 in cursor credits by going to chatpd.ai/howi AI. I have to pause before we look at your list of skills because I'm so excited about that part. But if folks aren't watching it, they may have missed how amazing what you just showed is. So I'm going to reiterate it, which is one, you've instrumented all your internal skills with telemetry so that and and you're using honeycomb. Um, love the honeycomb team.

</details>

**Claire Vote**: 你正在使用 **Honeycomb** 来查看这些技能在一段时间内被调用的频率。所以，这只是给任何内部构建技能库的人的一个提示，甚至是那些试图在组织中提升影响力的。假设你构建了一个技能，你想去找你的老板说：“老板，我的技能每天都被所有人使用。”那么找到一种方法，将事件级别的遥测数据放入技能中，建立一个小仪表板，你可以随着时间的推移跟踪这些数据。再次强调，将你的组织视为一个产品，将你的仓库视为一个产品，将你的 **AI** 设置作为一个团队视为一个产品，所有产品，所有好的产品都有跟踪计划。所以，我认为找出如何将遥测数据放入其中是非常聪明的。

<details>
<summary>Original English</summary>

**Claire Vote**: You're using honeycomb to see how often those skills are invoked over time. So this is just a tip for anybody building out a skills repository internally or even somebody who is maybe trying to get some visibility into their impact across the org. Let's say you build a skill and you want to go to your boss and be like boss my skill is being used by literally everybody every day. Um find a way to put event level telemetry invoked in the skill a little dashboard and you can track those over time. Again, treating your org like a product, treating your repo like a product, treating your AI setup as a team like a product, and all products, all good products have tracking plans. And so figuring out how you put that telemetry in, I think is really smart.

</details>

**Claire Vote**: 然后第二件事，对于那些错过或不知道如何做的人来说，你正在获取所有原始的会话，我猜是 **JSON** 文件。所以，对于那些不知道的人来说，**Claude Code** 将你与 **Claude Code** 的所有聊天存储在你的计算机上的 **JSON** 文件中，你可以随时查看或查询这些文件。听起来你们正在将这些文件上传到 **S3**，然后在其之上分层进行匿名化处理，以及用户级别的视图，然后你基本上是在构建一个我称之为内部评估的系统，来了解人们如何使用 **Claude Code**，以及他们随着时间的推移遇到了什么问题。这样一来，个人可以自行调整他们的实施方式，就像你说的，“哦，看起来我需要做这个或那个，或者改进我的 agents.MD。”但如果我们在组织中看到一致的主题，例如“它从未在我们需要它调用这个 **MCP** 时调用它”，或者“每次 **Create PR** 技能被排队时，人们都在喊不。”那么你可以在系统层面解决这个问题，但如果你没有可见性，你就无法做到这一点。所以再次强调，我的工程副总裁、**CTO**、我的朋友们，在你们的技能中加入一些遥测数据，然后对你们组织中的 **Claude Code** 会话进行元分析，这样你们就能找出一些高杠杆的修复点，这些修复点将随着时间的推移解除团队的障碍。

<details>
<summary>Original English</summary>

**Claire Vote**: And then the second thing for for those that missed it or how to do it is you're taking all the raw session, I'm presuming JSON files. So, for folks that don't know, Cloud Code stores all your chats with Cloud Code um in on your computer in JSON, and you can go look at those or query those at any time. It sounds like you all are uploading those files to S3 and then layering on top of it some anonymization, some user level views and then you're essentially building sort of what I would call like an internal eval of how people are using clawed code and what problems they are having over time so that individuals one can triage their own implementation as you said oh it looks like I need to do this or that or improve my agents MD but then if We're seeing consistent themes over the organization on it's never invoking this MCP when we need it to invoke this MCP or people are yelling no every time the create PR um skill gets queued up. You can fix that at a systems level but you can't do that if you don't have the visibility. So again, my VPs of engineering, my CTO's, my friends out there, put some telemetry in your skills and then do some meta analysis on your cloud code sessions across the org and you'll be able to identify places where some probably some high lever fixes are going to get your team unblocked over time.

</details>

**Brian Scanland**: 我确实希望并期待这些事情会随着时间的推移变得更容易。你知道，我很乐意投入工作，这样我们就能快速行动并走在最前沿，但也有一些说法是，拥有后发优势，并且当 **Anthropic** 或其他人发布这些东西时，可以免费获得。我的意思是，这也许是一个人们应该购买或构建的产品。但对我们来说，现在别无选择，我们只能自己构建它。我们对这些会话中隐藏的洞察力着迷。所以我们必须构建东西，这样我们才能看到正在发生什么。

<details>
<summary>Original English</summary>

**Brian Scanland**: I do hope and expect that this stuff will get easier over time. you know, um I'm happy to kind of invest the work uh so that we can move fast and kind of be on the bleeding edge, but there's something to be said also for being for having like last mover advantage and just getting all this stuff for free whenever Antropic ship it or whoever shipped it. Um I mean maybe this is a product just that people should buy or build. Um but for us right now, we have no choice. We just got to build it. We're we we're we're we like we're fascinated with the insights that are locked away in these sessions. Uh and so we just got to build uh stuff so that we can see what's going on.

</details>

**Claire Vote**: 我喜欢！好的。我们能看看这些技能吗？

<details>
<summary>Original English</summary>

**Claire Vote**: I I love it. Okay. Can we see some of these skills?

</details>

**Brian Scanland**: 是的。呃，所以它是一个非常令人兴奋的 **GitHub** 仓库。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yes. Uh so it's a very exciting GitHub repo.

</details>

**Claire Vote**: 我们的生活都是 **GitHub** 仓库和 **Markdown** 文件。

<details>
<summary>Original English</summary>

**Claire Vote**: Our lives are all GitHub repos and markdown files.

</details>

### 内部技能库与“软件工厂”模式

**Brian Scanland**: 完全是。我们目前有很多活动。上周我们举办了一个 **AI Day**，让更多人参与进来。所以，这是一个插件仓库，我们有一系列插件，而且目前它们每天都在增长。每个团队都会有自己特定的插件，而且通常我们非常自由。我们希望把东西放在这里，即使它不怎么样。当然，我们确实对核心插件的细节非常重视，我们认为这些是基础的、每个人都能接触到的插件。所以我们从这些基础插件开始，它们会被安装。哦，是的。所以我们不是通过 **Claude Code** 插件机制分发这些的。我们发现那个机制有点不稳定。你知道，有时它会更新，有时不会。最终就像试图在数百台不同的笔记本电脑上管理一个 **Python** 安装一样。你知道，你根本不想做那种事。所以我们最终使用了我们的内部 **IT** 系统，将所有插件同步到每个人的笔记本电脑硬盘上。所以这是一个很棒的代码，是的，强烈建议与你的 **IT** 团队紧密合作，这样才能可靠地交付这些东西，而不必完全依赖 **Claude Code** 插件机制。根据我们的经验，那个机制有点不稳定，而现在在硬盘上一切正常，这给了我们很大的安心。所以我们知道这些东西在任何地方都能工作，因为我们有 **IT** 团队将其推送到硬盘上。所以我们有一些安全钩子。我们有一些基础性的东西，比如合并 **PR**，我们不希望我们的代理进入 **AWS**，然后只是不同的设置和遥测功能。所以这些是每个人都绝对会得到的核心功能，但我们知道这些都是极简的，我们不希望有任何可能不适合非技术人员的笔记本电脑的东西。所以这是基本的构建模块。对我们来说，下一个主要部分是我们称之为“开发者工具”的东西。再说一遍，这现在将是我们在工程及其他领域所做的事情。这些通常是任何工程师在日常工作中都可以使用的适当技能。再次强调，我们对所有这些都会有很高的质量标准。所有这些都需要评估。所有这些都需要通过我们对技能质量进行的各种测试或分析。所以我们努力维护这些技能，确保它们得到良好的更新和使用，并且我们非常重视。我或许可以详细介绍其中一个技能。这个技能对我来说意义非凡。它就是“不稳定测试”（**flaky specs**）。我认为这里有趣的部分不是技能本身。这个技能确实能可靠地修复不稳定测试。我可以在此期间展示一份我们目前的不稳定测试列表。我将打开这个技能，并开始在这个问题上运行它。所以，当它运行时，我将详细介绍不稳定测试技能的内容。这里有一个清单。我构建这个技能的有趣之处不在于我是一个修复不稳定测试的世界级专家。我大致了解这个问题，并且在我的职业生涯中修复了一些。但在像我们这样的大型测试环境中，有不同的分类。我们有几十万个测试，如果你不非常小心数据污染或竞态条件以及所有这些在你每天运行数百万个测试时会出现的问题，那么你的测试最终会减慢你快速可靠地向生产环境交付代码的能力，并且不会通过随机故障来混淆开发者。这有一些已知的模式和方法。但我知道我的目标，那就是拥有一个能修复所有这些不稳定测试的技能。当你给代理一个可测试的目标时，它在这方面做得很好。你知道，这不是完全开放式的。我还有一个巨大的积压，或者说，是的，有几百个积压，但也有所有这些历史上的不稳定测试信息。所以你可以收集你环境中的所有这些数据，然后说：“嘿，**Claude**，我要构建一个技能。首先去研究我们曾经有过的每一个不稳定测试，然后我们将构建一个清单。我们将构建一个机制，然后我们将一遍又一遍地处理它们。”你得到了这种 1 倍的效果，你知道，它做得很好，可能和我自己做得一样好，但当你不断构建所有这些微小的步骤时，这些都是我们的优秀 **Rails** 程序员会做的事情，他们脑子里有所有这些东西，以及不稳定测试的不同分类，以及对照真实数据进行验证。然后，最有趣的部分是，你得到了一个开始达到 10 倍效果的东西。它正在修复我甚至不确定我是否能做到的不稳定测试，可能需要我一天的时间。我可能不会去做。但随后你开始向技能中添加一些东西，例如，当你修复了一个新问题时，你需要更新自己。所以在那个会话中，它正在更新技能。所以技能本身就像是边做边学，我们也会进行扩展。所以，它会说：“好吧，你修复了那个不稳定测试，我很高兴。现在找出所有受此影响的不稳定测试。”所以，我的这个技能从 0 变成了 100 倍，现在它达到了高级特级工程师的水平，能够修复这些测试。但这更多是关于实现这个目标的过程。它就像是与反馈循环一起工作，与一个非常明确的目标一起工作，然后赋予它自由去实现。你知道，让它能够访问需要获取元数据的系统，能够自己运行构建。并且拥有那个反馈循环，它在学习。然后，你知道，还要设计技能，这样你就必须经常编辑它，这会占用太多信息，可能会混淆事情，但随后你将事物分解成参考指南。所以你正在进行这种渐进式发现。我甚至不小心将这个技能指向了一个 **Python** 代码库，**Claude** 就说：“啊，这只是 **Python**，我会试试。”它会利用适用于它的知识。所以，再说一遍，这个技能不会让 **Intercom** 的收入增加 100 倍。但它现在是一个完美可靠的东西，我们真的不再需要考虑它了，而且我们可以将其扩展到许多不同的领域，我们只需要维护它，而维护像这样规模的工作并不多。我们有评估机制，所以当我们在升级模型，甚至可能转向更便宜的模型时，我们可以确保这个东西没有退步。它仍然像我们想象的那样工作，我们有信心和确定性，它仍然是一个可靠的构建模块。再次强调，当这些组成部分组合在一起时，你就拥有了一个非常高级的工程师，他能够在你的环境中完成任何工作。所以，是的，我们可以看看它在做什么。哦，它正在请求权限。我应该检查一下。

<details>
<summary>Original English</summary>

**Brian Scanland**: Totally. Um and we have we have a lot of activity at the moment. We we ran an AI day last week kind of getting more people uh contributing to it. And so well what so what this is is it's a plug-in uh repo and uh we have a series of plugins and they've been they're growing daily at the moment. Um kind of every team will have their own kind of specific plugins and actually in general though we're very liberal. We want stuff to end up in here, even if it's not great. And well, we do sweat the details on the core plugins, things that we think are fundamentals, foundational ones that go out to everybody. And so where we start off is we have like these base plugin which gets installed. Oh yeah. So we distribute this not via the claw code plug-in mechanism. H we found was just a bit flaky. It was, you know, sometimes it would update, sometimes it wouldn't. And it was ended up kind of like trying to manage a Python install on on hundreds of different laptops. You know, it's you just don't want to do it. And so we ended up using our internal IT systems to synchronize all of the plugins to the discs of everyone's laptops. Uh so this is a great G-code and yeah strongly recommend getting very close with your IT team to be able to deliver things like this reliably and not have to rely entirely on the claude code code plugins mechanism. Just our experience is a bit flaky and it's just gives us a lot of reassurance. We don't have to do certain types of debugging once it's all on disk. So so this is we know this stuff works everywhere uh because we've got our IT team pushing it out to disk. Uh and so we got some safety hooks. We have some uh some of the B foundational things like yeah merging Pors we don't want our agents going off into AWS and then just different settings and the telemetry things as well. So these are uh the core things that absolutely everybody gets and um but we you know these are minimalist we don't want anything that could be inappropriate in say a non-technical person's laptop or whatever. So uh that's this is like the the basic uh building block. The the next main bit for us is like what we call developer tools. Again, like this would be things that we then do all of engineering and beyond at this point. Uh and these would be generally skills that would be appropriate to be used by any engineer in the course of their work dayto-day. And again, we would have a high quality bar again for all of these. These would all require eval. These will all require to pass different kind of tests or analysis that we do on the quality of skills. Uh, and so we we try and maintain these and make sure that they're well updated and well used and we pay a lot of attention to to I can maybe go through one of these skills in a bit of detail. Uh, this one's near and dear to my heart. It's flaky specs. And I think the interesting part here is not the skill itself. The skill does reliably fix flaky specs. And I'll I can pull up um in the meantime like here is a list of flaky specs that we have at the moment. I'm going to open up uh the skill and just start to run it on this issue. And so while this is running, just walk through what's in the flaky spec skill. And so there's a checklist here. And the fun part about how I built this was not that I be was a world-class expert at fixing flaky specs. I roughly know the problem h and you know have fixed a few of them in my time. But there's different classific in a large test test environments like ours. We have hundreds of thousands of tests and if you're not super careful about like data poisoning or race conditions and all these kind of things that kind of kick in when you're running millions and millions of tests a day. You know, you end up with these tests that end up slowing down your ability to deliver code to production fast and reliably and not confuse developers by things randomly breaking. And there's kind of known patterns and known known ways you would go about this. Um, but I knew my goal, which was to have a skill fixing all of these flaky specs. And it was something that agents are pretty good at when you give them a a kind of testable goal. You know, this wasn't quite open-ended. And I also had this huge backlog or yeah, there was a backlog of probably a few hundred, but then also all of this historical flaky spec information. And so you can just harvest all of this data in your environment to go, hey Claude, I'm going to build a skill. first of all go and research every single flaky spec we've ever had and then we're going to build a checklist. we're gonna build a mechanism and then we're just going to crunch through them over and over and over and you get to this like 1x kind of you know it's doing a good job probably as good as job as I would do but then as you keep building up all of these like little teeny steps which are the kind of things that you know our best Rails coders kind of do they've got all the stuff in their head and all the different classifications of flaky specs and you know verifying against real data um and uh and then but the the really fun part is then you get so you get something that's starting to be like 10x. It's fixing flaky specs that I'm not even sure if I could do it might take me a day or something. Um and I probably wouldn't do it. But then you start to add in stuff into the skill along the lines of like okay when you fix something and it's novel you need to update yourself as well. So in that session it's updating the skill. So the skill itself is kind of learning as it goes along and we also fan out. So it's like okay I'm very happy that you fixed that flaky spec. Now find every flaky spec that got impacted by that nature of it. And so I went from zero to like 100x in terms of this skill now is like you know senior distinguished engineer level or being able to fix uh these specs. But it was more like the process that got there. Um, and sort of like working with a feedback loop, working with like a very clear goal and then giving it the freedom to do it. You know, giving it access to the systems where it needs to pull in metadata, being able to run builds itself. Um, and having that feedback loop where it's learning and and then, you know, designing the skill as well so that it's you have to editors every so often ends up taking up too much information that might confuse things, but then you break things out into uh like reference guides. So you're doing this like progressive discovery thing and and I've even accidentally pointed this skill at like a Python codebase and Claude has just gone ah like it's just Python I'll give it a go. Uh and it kind of uses the knowledge that's applicable to it. And so again this skill is not going to make intercom's revenue go 100x. Um, but it's now this like perfectly reliable thing that we really no longer have to think about and that we can expand out into many many different areas and we're we just have to maintain this and the maintenance work for a scale like this just isn't much and we have eval so that when we're upgrading models or maybe even moving to cheaper models or whatever that we can make sure yeah this thing isn't regressing. it's still working as well as we think it is and we've got confidence and certainty that this is still a reliable building block and again the constituent part put when put together you've got like a very senior engineer who's able to get any work done in your environment and so yeah uh we can take a look at what it's doing oh it's asking me for permissions um should have checked

</details>

**Claire Vote**: 你忘了“不要犯错，危险地跳过权限”，这是 "How I AI" 的规则。一件事，当它运行时，我想说的是，你知道，这个技能是我所说的“然后 **AI** 工作流”的完美例子，我告诉所有人，通过一系列的“然后”来拉动你的技能和工作流。所以我想修复不稳定的测试。所以我去 **GitHub**，找到一个不稳定的测试，我运行脚本。假设你修复了它，然后你会做什么？嗯，我会记录我是如何修复它的。然后你会做什么？嗯，我会去找所有其他类似的东西并修复它们。然后你会做什么？我会从一个 **Rails** 代码库到一个 **Python** 代码库，并应用相同的方法，你可以一遍又一遍地这样做。因为运行这些的成本如此之低，

<details>
<summary>Original English</summary>

**Claire Vote**: you forgot to d make no mistakes dangerously skip permissions that's the rule on how AI one thing while it's running I wanted to say is you know this skill is a perfect example of what I call the like and then AI workflow, which is I tell everybody like pull your skills and pull your workflows through a bunch of and then. So I want to fix flaky flaky tests. So I go to GitHub, I find a flaky test, I run through the skit. Let's say you fix it and then what would you do? Well, I would document how I fixed it. And then what would you do? Well, I would go find all the other ones that are just like this and fix that. And then what would you do? I would go from, you know, a Rails codebase to a Python codebase and apply the same, you can just do that over and over. And because the cost of running these is so low,

</details>

**Brian Scanland**: 你实际上可以处理一大堆事情，任何一个理智的人在第一步就会放弃，因为你不再受限于人力或协调成本。你受限于解决问题的技术能力，我认为这是一种非常有趣的思考方式，关于如何从一个工程实习生（他的工作是去处理所有这些不稳定的测试）到一个杰出的工程师，他已经快速完成了 300 个测试，并想出了一种完全不同的方式来架构你的整个测试仓库。所以，我认为这是一个非常好的模式。然后另一点是，工程师们，去快速解决你们的技术债务，修复你们不稳定的技术问题。这些都是作为管理工程组织的人，我一遍又一遍地听到的：“我们不能，因为我们的代码库 blah blah blah blah blah。”比如：“我们能不能分配这么多时间来修复这个烦人的前端不稳定测试？”你不再需要为此请求许可，因为现在有了新的解决方案。我认为，回到我们之前讨论的一些事情，我认为你的整体产品质量会提高。我认为你的整体开发者体验会提高。使用这些工具并正确使用它们，会带来许多好处。

<details>
<summary>Original English</summary>

**Brian Scanland**: you can actually pull the thread of a bunch of stuff any reasonable human would have quit at step one because you're not limited again by headcount or coordination cost. you're limited by the technical capacity to solve the problem which I think is is a really interesting way to think about how you get from like the you know engineering intern that whose job is to go through and take a first you know gentle pass at all these flaky tests through to the distinguished engineer who has just speedrun through 300 of them and has thought of a completely different way to architect your your testing overall in your repo. So I think that's a really great model for for things. And then the other thing is like again engineers go speedrun your tech debt fix your flaky tech. Like these are all things that as somebody who has run engineering organizations I have heard over and over we can't because our code base blah blah blah blah blah like can we pretty please allocate this amount of time to just fixing this really annoying front-end flaky test. like you don't have to ask permission for that stuff anymore because there's just a new way to solve it. And I think again just going back to some of the stuff we were talking about earlier, I think your overall product quality is going to go up. I think your overall developer experience is going to go up. There's just so many good things that come out of using these tools and using them correctly.

</details>

**Brian Scanland**: 是的，我认为“待办事项清零”对团队来说是一个现实的目标。你知道，所有你曾经希望做的事情，现在都变得可实现。当然，你必须在同一时间平衡所有额外的交付物。但能够思考“嘿，我们实际上有一条路径可以消除我们所有的待办事项和所有架构更改”，这真是太棒了。你知道，我们最近我正在将一个 **Go** 微服务重新用 **Ruby** 实现，那是在 11 月之前，那是一个独立的 **Claude Code** 会话。这在我过去是需要争取列入路线图，并在不同工程师的脑海中播下种子，并引导他们去做，并将许多问题归咎于这个微服务的存在。但是现在，

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah, I think backlog zero is a realistic thing for teams to be able to go after. you know, all the things that you wish you would ever wanted to do, you know, it's it's now just achievable. Of course, you got to balance it with, you know, all of the extra stuff that you can just deliver at the same time. But it's so sweet to be able to think that, hey, we actually have a path to getting rid of our all of our backlogs and all of the kind of architecture changes or whatever. You know, we we can recently I was taking a Go microser and re-implementing it in Ruby and it was a single cloud code session before November. This was something that I would have had to advocate for on a road map and like you know plant some seeds and different engineers heads and kind of nudge people towards it and kind of blame a lot of problems on the existence of this micro. Um but now

</details>

**Claire Vote**: 等等，在你谈论这个过程之前，先发出警告。

<details>
<summary>Original English</summary>

**Claire Vote**: wait trigger warning first before you talk about that process.

</details>

**Brian Scanland**: 呃，抱歉，我正在泄露影响组织运作的秘密。但是，是的，现在就像，我甚至不必考虑这个了。这是一个单独的会话，事实上我可以

<details>
<summary>Original English</summary>

**Brian Scanland**: Uh sorry I'm giving the secret sauce here of how to influence an orc. Uh but yeah and but now it's like well I don't even have to think about this now. It's a single session and in fact I can

</details>

**Brian Scanland**: 我可以让 **Claude** 实现五次，然后比较它们的风格，或者比较，你知道，让它审查它们，并找出实现这个东西的最佳方法。这就像这种创造力和自由的水平，你的想象力是阻碍，而不是实际完成这些事情所需的时间，而过去可能需要几个月。

<details>
<summary>Original English</summary>

**Brian Scanland**: I can get Claude to implement it five times and compare the styles or compare the you know get it to review them and figure out what the best way of of implementing the thing is. And this is just like this level of kind of creativity and freedom that where like your imagination is the blocker, not not the the time it takes to actually knock out one of these things which was months in the past. You know,

</details>

**Claire Vote**: 我完全同意，我在 chat **PRD** 上也有这种感觉，人们会问：“你的，我的意思是，我是一个面向产品人员的产品工具。他们总是问我的路线图是什么。”我说：“我根本没有路线图。我们每周都会烧掉路线图，然后我们再决定下一步要发布什么。”当然，我们有一些主题性的想法要追求，以及一些更大的东西。我为了不过度交付产品，尤其是在产品市场契合度不足的情况下，我所做的一件事就是将想法限制在我自己大脑能处理的范围内，这就像有一个自然的节流阀，可以避免发布糟糕的东西，因为这不是工程在限制我。它实际上只是好的、可商业化的想法。我认为这就是我们将看到一些限制开始发挥作用的地方。再次提到 **Anthropic**。

<details>
<summary>Original English</summary>

**Claire Vote**: I I completely agree and I I feel this at chat PRD where people are like what are your I mean I'm a product tool for product people. They're always asking what my road map is. I was like I literally don't have a road map. We burn down the road map every week and then we figure out what we're going to ship next. And of course, we have thematic ideas we want to pursue and things that are larger. And one of the things that I do to keep myself from overshipping absent product market fit is literally constrain the ideas to what I can do in my brain, which is there's like a natural throttle on not getting slop out because it's not engineering throttling me. It's actually just good commercializable ideas. And I think that's where we're going to see some of the limits start to come in play. Again, referring to Anthropic.

</details>

**Claire Vote**: 另一个大新闻是 **Anthropic** 正在招聘一大批产品经理，因为他们有如此多的工程能力。他们实际上受限于产品经理的能力。所以，看看你们业务中的瓶颈最终会在哪里会很有趣，哪些瓶颈是合适的。有一个产品瓶颈可能是一件好事，因为这样你就不会发布任何客户无法吸收的东西。所以我想它会随着时间的推移而演变，然后，产品将会拥有一整套技能，然后我不知道我们到时候会做什么，也许会在海滩上闲逛，但我认为现在是一个非常有趣的时期来管理组织。

<details>
<summary>Original English</summary>

**Claire Vote**: Another big news piece came out is that they're hiring a bunch of PMs because they have so much engineering capacity. They're actually limited at the PM capacity. And so it'll be interesting to see where the bottlenecks in your business, you know, end up which bottlenecks are appropriate. it's probably good to have a product bottleneck a little bit because then you're not shipping anything um which customers can't absorb and so I just I I think it's going to and it's going to evolve over time and then you know product is going to have a whole set of skills and then I don't know what we're going to do with our time hang out on the beach but I think it's it's a pretty interesting time to to run orgs

</details>

**Brian Scanland**: 是的，你知道，我认为工程师、设计师、产品经理，也许最终都会变成一个“构建者”的集合。

<details>
<summary>Original English</summary>

**Brian Scanland**: yeah you know I think engineers designers product managers maybe it's just all going to be one blob of builders or something like that.

</details>

**Claire Vote**: 每个人都只做事情。每个人都只做事情。

<details>
<summary>Original English</summary>

**Claire Vote**: Everyone everyone just does things. Everyone just does things.

</details>

**Brian Scanland**: 而且，你知道，这很棒。它正在降低障碍，让你能完成大量工作。当你不需要问别人，或者让事情进入待办事项时，自己就能完成，这很有趣。或者即使是在一个小团队中，你也能很快完成。无论你的专业是什么，它现在都是一个很好的平衡器。所以，是的。所以，我们上线了。我想我们的龙虾已经上线了，它应该在 app.incom 上。龙虾表情符号。

<details>
<summary>Original English</summary>

**Brian Scanland**: And uh you know that it's great. It's uh it's it's lowering the barriers to like just getting a lot of stuff done. And it's like so much fun when you can when you don't have to ask somebody or get something on a backlog or whatever. You can just get it done yourself. Uh or even just get it done very fast in a small group. Doesn't matter what your discipline is. It's just like a great leveler at the moment. So yeah. So, we're live. I think our lobster is live and it should be on app.incom. Lobster emoji.

</details>

**Claire Vote**: 看看这个。

<details>
<summary>Original English</summary>

**Claire Vote**: Look at that.

</details>

**Brian Scanland**: 太棒了。

<details>
<summary>Original English</summary>

**Brian Scanland**: That's amazing.

</details>

**Claire Vote**: 我需要给你们一个推广码，你知道。

<details>
<summary>Original English</summary>

**Claire Vote**: I need to get you all an affiliate code, you know.

</details>

**Brian Scanland**: 呃，是的。我的意思是，龙虾表情符号，它们是新事物。它们是新的增长秘诀。

<details>
<summary>Original English</summary>

**Brian Scanland**: Uh, yeah. I mean, lobster emojis, they're they're the new thing. They're the new um growth hack.

</details>

**Claire Vote**: 它们是新的增长秘诀。好的。所以，我们看到你们的 **R&D** 人均 **PR** 数量上升了。我们看到了你们如何能非常快速地将 **Claude Code** 从开发阶段推向生产，并且有很多保障措施。我们看到了你们的技能列表，看起来有数百个，但至少有几十个技能是通过钩子调用的。你们不仅用这些来交付面向客户的产品，还用它们来改善开发者体验，消除技术债务，所有我们希望看到的事情。你们正在从遥测角度，包括定量和定性地进行衡量。你们正在衡量你们的 **Claude Code** 会话，而且你知道，两倍还不够。你们要达到十倍。所以你们都走在了前沿，至少在我交谈过的人中是这样，我相信你和我一样，会觉得“你当然觉得我们走在前沿，但我看到一些人，他们才是真正的前沿。”所以我们总是雄心勃勃地向前迈进。但现在我的问题是，这如何影响了你对客户产品的看法？你知道，我是 **Intercom** 的客户。我是 **Finn** 的客户。我每天都会与 **Intercom** 的代码和 **Intercom UI** 互动。我的 **OpenClaw** 有一个 **Intercom API key**。你们现在有了使用 **Claude Code** 的内部经验，你们如何看待客户体验会变成什么样子？

<details>
<summary>Original English</summary>

**Claire Vote**: They are the new growth hack. Okay. So, we have seen your PR per R&D employee go up. We've seen how you can get from kind of cloud code to production very very fast with a bunch of guard rails. We've seen your list of it looks like hundreds of skills but at least dozens of skills that you're invoking via hooks. You're using that to not only ship customerf facing product but you're also using that just to make developer experience better burn down tech debt all those things we want to see. You all are you're measuring it both from a telemetry perspective um both like quantitative and qualitatively. you're measuring your cloud code sessions and you know 2x isn't enough. You're going to get to to 10x. So you all are on the edge at least for for folks that I talk to and I'm sure you're like me where you're like sure you think we're on the edge but then I see people and they're really on the edge. So we always have ambitions to move forward. But my question now to you is how has this impacted how you think about your customers product? You know I'm an intercom customer. I'm a FIN customer. I interact with intercom code and intercom UI literally every day. My OpenClaw has an intercom API key. How do you how do you think about, you know, now that you have this experience with cloud code internally? How do you think about what that customer experience is going to look like?

</details>

### AI 时代的产品与客户体验

**Brian Scanland**: 是的，有几件事正在发生。一个是人们将许多决策外包给他们的代理，这在很多情况下是好事，但最近有一些很好的研究讨论了 **Claude Code** 会选择什么，我当然在很久以前有过这样的经历：我要求一个代理添加一些东西，但要放在一个功能标志后面，然后它就会开始实现自己的功能标志系统。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah, I there's a few things going on. One is that people are outsourcing a lot of decisions to their agents and like this is a good thing in many cases but you know there there was good research done recently about what does cloud code pick and certainly I've had the experience in the distant past where I'd ask an agent to add something except do it behind a feature flag and then it would start to go and implement its own feature flag system and this

</details>

**Claire Vote**: 不不。

<details>
<summary>Original English</summary>

**Claire Vote**: no no

</details>

**Brian Scanland**: 这在我们的代码库中，我们有一个非常复杂的老式自制功能标志系统。所以，你知道，现在我们大多会坚持代码库中已有的东西，这很好。但 **SaaS** 产品，它们在自己的工作中做得非常出色。它们确实值得花钱购买。回到功能标志的情况，你知道，如果你正在建立一个新业务，你依赖你的代理来做决策。通常，当一个代理被提示时，它会说：“嘿，我应该如何解决功能标志问题？我想确保我正在进行所有这些安全的部署。”然后代理就会说：“是的，我自己来做。”这是一种“自己构建”而不是“购买”的决策，你可以看出为什么代理会这样做，因为他们可以实现它，他们可以完成它，他们不必依赖人类。好吧，**OpenClaw** 在这里改变了一些事情，也许计算机的使用也改变了一些，但我们仍然没有真正地采用让 **SaaS** 企业对代理友好的方式。这意味着，在如何定位我们的网站和内容方面，以及你如何在他们的知识库中获得更新，他们如何发现它方面，以及他们是否真的能完成任务，比如你能否问一个代理：“嘿，你能帮我在 **Intercom** 上注册，并让 **Finn** 在我的网站上工作吗？”所以，这与我们必须为更多事物创建更多 **API** 是同步进行的。我认为我有点像全渠道。我认为未来会有 **CLI**、**MCP** 和 **REST API**。我认为我希望我们能更适应像短暂 **API** 或多步骤 **API** 这样的事物。我认为 **CLI** 擅长封装这些东西。但所有这些的重点是，你知道，你希望能够随时帮助代理，当他们正在互动、正在发现模式时，你希望给他们线索。你希望给他们提示。你希望给他们帮助，让他们能够完全注册某些东西，而无需返回给用户说：“是的，抱歉，我帮不了你。你必须自己去注册一些东西。”所以，我过去几周一直在研究一些东西，希望能解决这个问题。我可以在其中粘贴一个提示，然后看看它能走多远。

<details>
<summary>Original English</summary>

**Brian Scanland**: this is in our codebase which has a pretty sophisticated ated old school uh home rolled feature flag system. So, you know, nowadays mostly we'll stick to whatever is in the codebase and that's fine. Um but you know SAS products, they're really good at their jobs. They're actually worth paying money for. And uh getting back to the feature flag uh situation, you know, uh if you're building a new business, you're you're relying on your agent to make decisions. Uh often an agent will when prompted it's like hey how should I solve the feature flag problem I want to make sure I'm doing all these safe deploys and that uh the agent will just go yeah I'll do it myself and the kind of build over buy decision uh and you can see why the agents do it this way because they can achieve this they can get it done they don't have to rely on the human okay like open claw changes things here a little bit and maybe computer use does as well but still we're not really we haven't really adopted um SAS businesses to be agent friendly and that means well all sorts of things around how do we position our websites and content and how do you get updated in their in their knowledge and how do they discover it and but also can they actually just get it done like can you ask an agent hey could you just sign me up to intercom and get me uh Finn working on my website and so uh like this goes alongside just having to make more more APIs for things. I think I think I'm I'm kind of like omni channel as such. I think like there's a future for CLIs and MCP and like REST APIs. I think I' I'd like us to be get more comfortable around things like ephemeral APIs or multi-step APIs. I think CLI are good at wrapping these kind of things. And but the whole point of all this, where I'm getting at is like, you know, you want to be able to just help agents out at the time uh when they're interacting, they're in discovery mode, and you want to give them clues. You want to give them hints. You want to give them help to be able to do things like sign up for something fully without having to go back to the user and say, "Yeah, sorry, can't help you there. You got to go away and like figure out how to sign up for something." Um, so I I've been working on something in the last few weeks, which hopefully should solve that problem. on it. I can I can paste in a uh a prompt and then see how far it gets.

</details>

**Claire Vote**: 另外，就在我们运行这个的时候，我必须回到你的功能标志例子，因为它，你知道，我以前工作的地方。自己构建功能标志位于功能标志列表的首位，这让我很伤心。但我确实觉得我对此有一种偏执，那就是

<details>
<summary>Original English</summary>

**Claire Vote**: I also just while we're running this, I have to go back to your feature flag example because it you know where I used to work. It broke my heart that build it yourself was at the top of the feature flagging list. But I do think I have I have a a paranoia moment about this, which is

</details>

**Claire Vote**: 模型提供商和工具链提供商有很高的动力让用户“自己构建”，这会消耗大量 **token**，而“购买”可能会消耗更少。所以我真的很想看看这一切最终会如何发展。你知道，人们非常反对 **SaaS** 已死。我更像是，“是的，但是 **SaaS** 当前的形式真的会有一些东西来取代它”，尤其是在开发工具领域，因为这些模型非常擅长编写代码。我认为你真的处于一个困境中，试图找出如何在正确的时间找到正确的价值切入点。你如何允许代理不仅注册和设置东西，还可以购买它？你知道，如果你的第一个用户是一个代理，你的试用体验会是怎样的？我认为所有这些都非常重要。然后，你知道，就像你之前说的，关于 **API**、短暂 **API**、**CLI**、**MCP**，我认为现在的答案是肯定的，你无法预测用户会通过什么媒介访问你的网站。他们可能会通过搜索来到你的网站，下载东西，查看文档。他们可能会通过 **Claude Code** 来，他们可能会通过 **Open Claw** 来。你真的不知道。所以你必须去客户和你的非人类客户所在的地方接触他们。而且我认为对于任何产品中需要通过代码实现的部分，团队都应该思考这个问题，因为如果你没有代理体验，我认为你就会被抛在后面。

<details>
<summary>Original English</summary>

**Claire Vote**: model providers and harness providers are highly incentivized to build it yourself consumes lots of tokens versus buy it maybe consumes less. So I'm I'm just really interesting to see how this all shakes out. You know, people people are very anti SASS is dead. Um, and I'm a little bit more like, yeah, but like the current form factor of SAS really is has something coming for it in a particular dev tools because these models are so good at writing code. I think you're in a real um pickle to try to figure out how to find the right value wedge at the right moment. how you can allow agents to not just sign up and set up things but purchase it, you know, like what does your trial experience look like if your first user is an agent. I think all of that is super important. And then, you know, to your point earlier where you said, you know, are we APIs, ephemeral APIs, CLIs, MCP, I think the answer is yes right now, which is you cannot predict the the medium by which a user is going to come to your site. They could come through a search and hit your website and download things and look through docs. They could come through cloud code. They could come through an open claw. You just really don't know. And so you sort of have to meet your customers and your non-human customers where they're at. And um I think it's really smart for teams that have any part of their product that needs to be implemented via code to be thinking about this problem yesterday because you will be left behind I think if your agent experience isn't there.

</details>

**Brian Scanland**: 是的，完全同意。而且我认为在如何让一个 **CLI** 对代理友好的方面，有一整套技巧。我认为 **MCPS** 在很多时候显然做得很好。但你知道，例如，我们在帮助中做的一件事就是给代理一个提示。这几乎像是一种提示注入，只是它没有恶意。你只是想让它完成它想做的事情。你会说：“嗯，也许你可以检查电子邮件。”如果一个代理可以访问你的电子邮件，

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah, agree entirely. And I think there's a whole craft in how to make say a CLI like agent friendly. I think like MCPS obviously get that right uh a lot a a lot of the time. But you know, for example, uh one of the things that we do in in the help is like kind of just give a hint to the uh the agent. It's almost like prompt injection to a certain extent, except it's not malicious. You're just trying to get it along to what it's trying to achieve. You're like, "Well, maybe you could check email." And if if an agent has access to your email,

</details>

**Claire Vote**: 那就是我一直在看的。

<details>
<summary>Original English</summary>

**Claire Vote**: that's what I was looking at.

</details>

**Brian Scanland**: 是的。所以它就在那里，它会说：“哦，是的。我可能能搞定这个。”或者你可以暗示它们，就像我有点作弊一样。所以这是我自己的个人网站，托管在 **Forcell**，我已经预先填充了一些文章，所以它们可以上传，**Finn** 可以用这些内容来回答问题。但你也可以，你知道，在帮助中返回，说：“嘿，你知道，如果你想让 **Finn** 真正开始回答问题，你可能需要考虑创建一些文章。”这些文章可以从代码库或其他地方提取。嗯，是的，我一直在想很多像 **CLI** 界面这样的接口，我使用 **GOG**，你知道它是 **Open Claw** 宇宙的一部分，我认为它比官方的 **Google GWS** 更好。但如果你开始使用它，它实际上更人性化，因为它让用户界面更有意义。我认为 **Google** 的那个，我有点理解他们在说什么，里面有一些 **JSON** 之类的东西。它并不是说它有什么，但它感觉更人性化，或者说对代理有效的东西往往对人类也更友好，因为它们是可发现的，只使用动词和词语，而不是那种难以理解的奇怪东西出现在命令行选项中。我想我在这里把 **Claude** 搞糊涂了。我不确定这是什么。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah. So, it's it's just there going, "Oh, yeah. I can probably get this done." Uh or like you can hint to them like uh I've kind of cheated with this. So this is my own personal website hosted in in Forcell and it is uh I've kind of pre-populated a few articles so they can upload and Finn has some content to answer questions with but you can also just uh you know return in the the help going like hey you know you should probably think about creating some articles if you want Finn to actually start answering questions and that can be extracted from you know the codebase or whatever. Well, uh, yeah, I've been like like I've been also think like a lot of interfaces like CLI interfaces like I use GOG uh you know it's part of the Open Claw uh universe and uh I think it's a lot better than uh the official Google GWS one and uh but I think if you start to use it it's it's actually just more human um as in it's the interface just kind of makes more sense to a human. I think the Google one is like I kind of get what they're getting at and there's kind of Jason in there and stuff like that. H it's not that it h but it feels more human friendly or something things that are effective for agents can often be things that are more human friendly because they're discoverable only use verbs and words and not just kind of inscrutable weird stuff going on um in command line options. I think I've confused Claude here. I'm not sure what where is this

</details>

**Claire Vote**: 没关系，我来为大家解释一下这里发生了什么。你基本上说的是：“在这个网站上安装 **Intercom**。”有一个 **Intercom CLI**，这很酷，我可以访问 **Intercom API** 并做很多事情。但我最喜欢的部分是注册，在你的电子邮件地址中收到验证邮件，然后通过这个提示来调用，基本上就是说，如果用户设置了电子邮件访问权限，无论你如何访问它，就去检查这封验证邮件，因为我们里面有一个代码需要获取。因为你正在使用 **GOG**，这是一个命令行工具，可以访问 **Google Workspace**，你可以去这样做，拉取那个代码。我认为这种特定流程有趣的地方在于，你知道，我认为 **AI** 正在造成组织内部交付的某种竞态条件，也就是说，你可能比管理电子邮件认证的团队更快地推出一个 **CLI**，并改变电子邮件验证的工作方式。所以你会想：“我不会让它破坏我的产品。”我要做的是创建一个流程，我可以使用这种在 **AI** 大脑中“粘滞”的部分，并顺利通过。所以，再说一遍，你的产品不必完美，代理也能遍历它。这是我真正感到兴奋的一点，**SaaS** 的所有那些对人类来说非常复杂的事情，多步骤表单，嵌套字段上的嵌套字段，以及寻找类别等等，这些都是 **UX** 设计师和产品经理写过最繁琐的 **PRD**，做过最详细的规格。你实际上不必担心让它“可用”，因为你可以通过蛮力智能来解决问题。所以我认为这很有趣，因为核心价值主张可以变得越来越大，而不受限于网站或 **UI** 或任何这些东西的表面积。所以我认为如果你不考虑你的 **CLI** 会是什么样子，以及你的产品会与哪些相邻系统对接——可能是电子邮件，也可能是其他依赖项。以及一个代理可能会如何遍历这些系统，你只会获得越来越少的采用，因为这将成为人们安装产品的更多方式。

<details>
<summary>Original English</summary>

**Claire Vote**: that's that's okay. I'm going to I'm going to narrate for folks what's happening here, which is you basically said like install intercom on this site. There's an intercom CLI that's like cool, I can access the intercom APIs and do a lot of this. My favorite part of it though is signing up, getting a verification email in your email address, invoking via like this hint basically of like if the user has email access set up in however you're accessing it, go check for this verification email because we have we have a code in there that we got to snag and because you're using GOG um which is a command line tool to access Google Workspace, I you you can go do that, pull that code in and what I think is interesting about that particular flow is, you know, I I think AI is creating sort of race conditions in shipping across the org, which is like you can yolo a CLI probably faster than whatever team that manages email authentication can change how email verification works. And so you're like, I'm not going to let that break my product. what I'm going to do is create a flow that I can I can use that sort of sticky part in the flow AI brains and and get through it. And so again, your product doesn't have to be perfect for an agent to traverse it. And this is one of the things I'm actually really excited about SAS is all those things that are just so complicated to do as a human multistep forms and like nested fields on nested fields and finding you know categories and just those things that I would say UX designers and product managers have written their most tedious PRDS on and done their most detailed specs on like you don't actually have to worry about making that quote unquote usable because you can just brute force intelligence against it and and solve the problem. And so I think that's interesting because the core value proposition can get bigger and bigger without being constrained by the surface area of a website or a UI or any of those things. Um and so I think if you're not thinking about what does that CLI look like for you and what adjacent systems does your product butt up against? It may be email. It may maybe may be some other dependency. Um, and how an agent might traverse those systems, you're just going to get less and less adoption because this is going to be more how people install products.

</details>

**Brian Scanland**: 是的。如果我不制造漏洞，如果我不创建一个能够绕过产品某些工作方式的 **CLI**，那么其他人就会这样做。你知道，他们会使用自己的代理，他们会消耗更多的 **token**。他们可能会感到沮丧。所以你最好给他们提供一个界面，让它直接工作。它可能不是完美的界面，但这就是这些东西的美妙之处。你可以随着时间的推移进行更新。代理可以拉取最新版本。而且，是的，希望我能在这里展示一些东西。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah, And if I don't poke holes and if I don't make a CLI that kind of bypasses some of the ways that product works, somebody else will. You know, they'll just put their own agents on it and they'll burn more tokens. They might get frustrated. Um, so you may as well shortcut them and give them an interface which just works. May not be the perfect interface, but that's the beauty of these things. You can get updated over time. You can agents can just pull down the latest version. Um, and yeah, like hopefully I have something to show here though.

</details>

**Claire Vote**: 嗯，我想说的另一件事是，当我在看这个并且它需要一些时间来构建时，你的转化率下降点就是有人按下 **Esc** 键。

<details>
<summary>Original English</summary>

**Claire Vote**: Well, the the other thing that I I want to call out while you're talking about that, which is as I'm watching this and it's taking some time to build, your conversion rate drop off point is somebody pressing the escape button.

</details>

**Brian Scanland**: 是的，然后说：“算了。”就像，“这显然行不通。如果我们自己构建它会怎样？”所以我认为对于产品经理来说，这是一个非常有趣的时刻，他们现在看不到这种下降。对吧？当你在浏览一个网站时，你可以放入遥测数据。你可以说：“好的，用户进入注册页面，然后离开。电子邮件验证，然后离开。查看文档，然后离开。”你可以构建一个漂亮的漏斗来识别你的用户在哪里遇到问题。你可以在你的 **CLI** 中放入一些遥测数据，但归根结底，这种下降和替代方案对你来说是看不见的。而“切换成本”就像按下 **Esc** 键，然后说“换个方式做”。所以，再次强调，你可以在代理中快速实现零到一的安装速度，我认为这是每个人现在都应该做的事情。而且它不一定是一个代码产品。我认为越来越多的人正在做非技术任务，并使用 **Claude Code** 或 **Claude co-work** 与非技术 **SaaS** 互动。所以，你知道，即使你不是开发工具，如果你不考虑用户如何能够快速地在一个第三方工具链或系统中，或者一个代理如何能够快速地做到这一点，那么你真的会错过客户增长。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah. and just saying, "Forget it." Like, "This is clearly not working. What if we built it ourselves?" And so, I think it's a really interesting moment for product managers who right now are not getting the visibility of the drop off, right? When you were going through a website, you could put telemetry in it. You could say, "Okay, users going to the signup page, drop off. Email verification, drop off. Going to the docs, drop off." You could build this nice little funnel that identifies where your users are having problems. You can put some telemetry in your CLI, but at the end of the day, some of that drop off and the alternatives is very invisible to you here. And the the switching cost quote quote unquote is like pressing escape and saying do it a different way. And so again, how quickly you can speedrun to a 0ero to1 installation in an agent, I think, is something that everybody should be running right now. Um, and it doesn't just have to be a code product. Like I think more and more people are doing non-technical tasks and interacting with non-technical SAS in claude code in claude co-work and so you know even if you're not dev tools if you're not thinking about how can a user do this quickly in in in a third party harness or or system or an agent can do this quickly um you're really missing out on customer growth

</details>

**Claire Vote**: 完全同意。好的，我们做得怎么样了？

<details>
<summary>Original English</summary>

**Claire Vote**: totally. Okay, how are we doing?

</details>

**Brian Scanland**: 正在进行第四次尝试。

<details>
<summary>Original English</summary>

**Brian Scanland**: It's on its fourth attempt.

</details>

**Claire Vote**: 没关系。你知道吗？我们按 **Esc** 键吧。因为你知道吗？让我告诉你那个练习有多便宜。

<details>
<summary>Original English</summary>

**Claire Vote**: That's fine. And you know what? Let's let's press let's press the escape because you know what? Let me tell you how cheap that exercise was.

</details>

**Brian Scanland**: 只花了五分钟和一些 **token**。

<details>
<summary>Original English</summary>

**Brian Scanland**: It was like five minutes and some tokens

</details>

**Claire Vote**: 你将启动一个新的 **Claude Code**。你有没有输入“不要犯错”？那可能是我们错过的。不要犯错。而且它可能已经完成了。再说一遍，这只是学习。为什么，为什么不是每个工程师，每个产品经理每周或每月都这样做一次，只是为了弄清楚它如何工作？我认为这很棒。所以，**Ryan**，你已经向我们展示了所有。你已经把所有的秘密都告诉我们了。让我们离开终端，做一些闪电般的问题。

<details>
<summary>Original English</summary>

**Claire Vote**: and you're going to spin up a fresh claude code. You're I don't know if you put make no mistakes. That was probably what we missed. Make no mistakes. Um and it and it could have done it. And again, this is just learning like why why aren't why isn't every engineer, every PM doing this once a week or once a month just to figure out h how it can work. Um, I think it's great. So, Ryan, you've shown us everything. You've given us all all the secrets. Let's get out of the terminal and let's do some lightning round questions.

</details>

### AI 带来的工作乐趣与文化转变

**Claire Vote**: 所以，我问你的第一个问题是，感觉如何？因为我从我们的对话中观察到，感觉很有趣。由于这项投资，文化实际上变得更好了，而不是更糟。所以，作为一个在客户和内部都付出了巨大努力的公司，你认为这如何改变了文化？它有改变吗？你观察到了什么？

<details>
<summary>Original English</summary>

**Claire Vote**: So, my first question for you is, how does it feel? Because what what I observe from our conversation is it feels fun. Like culture has in fact gotten better not worse because of this investment. And so you know as a company that has really put in the effort both on the on the customer side and internally how do you think it's shifted culture has it at all? Um what have you observed?

</details>

**Brian Scanland**: 是的，一切都更快、更令人兴奋。你知道，我提了好几次反馈循环，而且，你知道，你现在可以很快地把东西发布出去。在过去的三个月左右，我职业生涯中获得了最大的乐趣。而且，它以多种方式带来乐趣。它很有趣，因为我可以做一些我以前需要说服别人去做的事情，或者它们只是我愿望清单上的东西，我从来没有时间去做，我只会抱怨它们。但现在它们变得可以实现。但也有趣的是，让其他人提高生产力，提升他们的能力，减少工作量。我曾经觉得 **Intercom** 在抵制向大公司发展的缓慢趋势，以及所有这些流程等等方面做得很好。我们有点否认自己是一家大公司。我认为这在很多方面都是一种健康的工作方式。但这让我们回到了根本，你知道，你可以快速做出决策，并快速交付，获得超级快速的反馈。而且我能够交付实际的功能，不仅仅是 **CLI**，我还交付了一些 **Webhook** 功能，嗯，我已经很久没有做过那种事情了。我一直在平台领域深耕了很长时间。但那甚至不是什么大问题。只需要几个小时就能完成一些事情。而且那是一些客户要求的功能。所以我的工作变得更加多样化了。我能够看到更多，完成更多，并帮助其他人完成更多。所以你会得到这种兴奋感，速度也会增加，你知道，我们有所有这些衡量标准，这都很好。但每天早上醒来，想着“我今天要完成很多事情”的兴奋感，那是一种有趣的工作方式。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yeah everything is just faster and more exciting. You know, I mentioned feedback loops a good few times and you know, you can just get stuff out there so fast now and uh I've been having the most amount of fun in my career over the last three months or something like that. And like it's it's fun in many ways. It's fun because I can do stuff that again I would have had to convince other people to do or they were just things on my wish list and I could never get around to them and I just kind of complain about them. Um, but now they're just realizable. But also the fun aspect of like making other people productive, like leveling people up, getting like removing work. I had like uh intercom is pretty good culture around resisting like the kind of slow movement towards being a large company and all this process and stuff like that. And we're kind of in denial that we're like a large company. Um, I think it's a healthy way to work in many ways. And uh but this has kind of got us back to our roots in in a lot that you know you you can make fast decisions and get them delivered and get that feedback super fast. Um and I've been able to like ship actual features like not just the CLI but I ship shipped some web hook features and um it's been a long time since I've done that. I'm just I've been in the weeds and platform space for a long time. Um and but it wasn't even a big deal. It was like just a couple of hours just kind of get something done. and it was like something a customer asked for. So my job has become more varied. Um I'm able to kind of see more and get more done and help other people get a lot more done. So you get this kind of excitement and velocity increases and you know we have all those measurements and that's all kind of good stuff but just the excitement of waking up in the morning going like I'm going to get a lot done today. Like that is a fun way to go about your day.

</details>

**Claire Vote**: 我完全同意，我一次又一次地听到这个。我自己也肯定有这种感觉，那就是这让我回想起我为什么学习编码。就像那种时刻，我学习编码不是因为我喜欢输入代码。我学习编码是因为你运行像“Hello World”这样的程序，它就会出现在某个地方，那感觉太棒了，这只是一种非常有创造性的体验，这引出了我的第二个问题，那就是我经常看到，工程组织中最有影响力的变革推动者之一，可能是一位高级首席工程师说：“让我们在一些 **AI** 代码上大干一场！”而组织中最具阻碍性的人，可能是一位高级首席工程师说：“我不相信。绝对不可能。不是我。不是这里。不行。”事实上，上周我听说了一个故事，有人最资深的一位员工辞职了。他说，我引用原话：“我不相信 **AI**。我不会在一个相信这个的地方工作。”那么，你对工程师们有什么呼吁？为什么投资这个？为什么你认为这是工程师组织的发展方向？你如何与那些怀疑者沟通？嗯，并希望能让他们更多地理解 **Intercom** 的做法。

<details>
<summary>Original English</summary>

**Claire Vote**: I I completely agree and I hear this over and over and over again. I certainly feel it myself which is this is the it brings me back to why I learned to learn to code. It's like that same moment of I didn't learn to code because I like to type code. I learned to code because of the magic of you running like hello world and it it shows up somewhere and that feels so it's just a very creative experience which leads us to my second question which is I see all the time that one of the most impactful change agents inside an engineering organization can be a senior principal engineer saying let's go ham on some AI code and the single most blocking person in the organization can be a senior principal engineer going I don't believe it. Absolutely not. Not me. Not here. Not. No way. And in fact, last week I heard a story of somebody who had their most senior staff engineer quit. Says, and I quote, "I do not believe in AI. I will not work at a place that does this." So, what is your appeal sort of engineer to engineer of of why to invest in this? Why why you think it's the way that engineer organizations are moving and how you kind of come to meet skeptics where they are? um and hopefully see things a little bit from more from where kind of intercom is approaching them.

</details>

**Brian Scanland**: 我提到 **Intercom** 有点像“简单模式”。我们不必说服领导层相信 **AI** 的潜力，因为 **ChatGPT** 问世的那个周末，我们几乎就已经决定了公司的发展方向。

<details>
<summary>Original English</summary>

**Brian Scanland**: I mentioned that intercom kind of had it on easy mode. Um we didn't have to convince leadership that there's something to this AI stuff like we were pretty much had decided the direction of the company the weekend that chat GPT came out. So

</details>

**Claire Vote**: 是的。

<details>
<summary>Original English</summary>

**Claire Vote**: y

</details>

**Brian Scanland**: 呃，所以我们已经有这种期望，认为这将对我们工作的许多方面产生变革性影响，包括所有的产品构建和工程。我们只是大部分时间都在为它花了多长时间而烦恼。但我想，是的，它确实需要强有力的倡导者，你需要突破界限。我能够成功做到的最大事情之一是，突破了“我们是否应该让代理连接到 **Snowflake**？”这样的障碍，以及所有可能出错的事情，或者“我们是否应该让代理通过 **API** 在我们的 **Rails** 控制台中运行真实的生产代码？”最简单的回答是：“嗯，我不确定，”或者“这有风险，”或者“我们应该考虑一下。”但我们基本上已经突破了这些，现在，我们并非鲁莽行事，我们有很多良好的控制措施，我们是一家成熟的企业，我们有，我曾经在我们的安全团队工作，但肯定没有试图做任何太疯狂的事情，但即使如此，我仍然有些担忧，比如“这是否，我是否应该这样做？但这看起来很奇怪，或者很难。”我只是必须给自己许可，然后我意识到如果我必须给自己许可，那么外面有很多人只需要许可。而且老实说，我在 **Intercom** 做过的最大事情之一就是告诉人们他们可以做事情。有 **AI** 之前和 **AI** 之后，或者告诉他们：“看，无论你做什么，如果出了问题，就把责任推给我。”

<details>
<summary>Original English</summary>

**Brian Scanland**: uh so we already had this expectation that this would be transformative across many parts of our work including all of building product and engineering. We were just kind of mostly annoyed about how long it took. Um um but I think uh for sure it does need strong advocates and you need to push uh boundaries like one of the biggest things that I've been able to do successfully was kind of push through the barrier of like should we let uh an agent connect to Snowflake like what like and there's all these things can go wrong or should we let our agent run real production code in in our Rails console over API and the easiest thing to answer there is like well you know I'm not sure h or like this is this is risky or we we should think about this but we've been largely pushing through it and now like not recklessly uh like we've lots of good controls and we're a mature business and uh we have like I've been on our security team but definitely uh not trying to do anything uh too wild but there's still even then I have apprehension like is this like I think I I think we should do this but it seems weird or it seems hard I just have to give myself permission and then I realized if I had to give myself permission, there's loads of people out there who just need need permission and um honestly like one of the biggest things I do at intercom is just telling people they can do things. Um there's there's a pre pre AI and post AI and uh or telling them like look whatever you do just blame me if it all goes wrong

</details>

**Claire Vote**: 我猜也许我们可以责怪 **Claude**，但最终，这种许可和抱负水平也很重要。如果你在外面说：“我不确定 **AI** 是否会在我们的工作中扮演重要角色，”如果你一直这样说，那种想法就会渗透到文化中，人们会这样说。但如果你非常明确地说，所有工作都将是 **Agent-First** 的，在不久的将来，所以我们将找出路径，我们将打破我们遇到的每一个障碍。看，这是你的工作，这是我的工作，如果出了问题，就责怪我。我基本上就是这样处理的，但不仅仅是我，这是一个非常大的集体努力。但给予那种许可，以及探索或推动事情的自由，这都是必要的。而且，看，这可能是一种压力较小的方式，那就是睡几年，然后回来，所有问题都解决了，我们有了这些完美的代理在我们的环境中运行。那就能避免一些问题。但我想，所有地方都必须经历那种担忧和初步问题，这些问题可能伴随着代理的引入。我认为我们作为领导者的工作，无论是作为工程师还是经理，都必须在于赋能，并给予人们空间深入工作，享受它，并拥有那种“恍然大悟”的时刻，意识到这将会改变我能完成多少工作。

<details>
<summary>Original English</summary>

**Claire Vote**: and I guess maybe we can blame blame claudo but but ultimately it's that like permission and just like there's a level of ambition which comes from as well is like if you if you're out there saying I'm not sure if AI is going to take or have a big role to play in all of our work and if you keep on saying that that kind of will permeate through the cult culture and people say that but if you're very clear you say you're saying that like look all work is going to be agent first like at some stage in the near future h and so we're going to figure out the path there and so we're going to break down every barrier as we come across them and look it's your job it's my job and if anything goes wrong blame me like that's largely been how I've been approaching but not just me like this has been a very large collective effort but giving that kind of permission thing but also the kind of uh like freedom to like explore or push things or whatever It's kind of necessary. And look, it might be a less stressful way to go about it to like just take a nap for a few years and come back and then well, all the problems have been solved uh and we've got these perfect agents uh running a muk in our environments then um then that that would avoid some of this. But like I think all places have to get through that kind of apprehension and initial kind of issues that some of these can uh some of the introduction of agents into environments can have. And I think our job as leaders whether it's as an engineer or as a manager or whatever just has to be on that like enablement and giving people space to to to go deep on the work enjoy it and like have that moment where things click and you start realizing like oh my god this is uh something that will transform how much I can get done.

</details>

**Claire Vote**: 对后面的人再说一遍。我爱我，我当时想：“天哪，我太喜欢这个了。”你知道，这绝对是两件事，那就是：给予许可。你可以，请便，设计师，给我一个 **PR**。没有人会生你的气。尽管去吧。然后第二件事是，责任可以归咎于最高层，但不是以一种可怕的方式。我们不要做不负责任的事情。但是，你知道，我们在过去几个月里看到了一些事件，一些大事件，你看到的是 **CEO** 或大领导出来说：“团队正在交付，我们希望继续交付，我们将小心处理客户数据，我们关心客户体验，事情会发生。我们从中吸取了教训。最终责任在我。我会给客户打电话，我们会继续前进，为你们提供伟大的创新。”你知道，我告诉人们，为了让他们克服那个障碍，那就是你真的必须知道你的生存问题是什么。我喜欢你说的，**ChatGPT** 问世的那一刻，**Intercom** 就改变了，因为那是一个生存问题。谁在你的代码库中编写代码？代理还是人类？这不是一个生存问题。你是否会被新技术从根本上颠覆？那才是你业务中的真正问题。所以，我总是告诉人们，让我们区分我们业务中的真正问题和我们可以容忍的问题，然后利用我们可以容忍的问题来快速行动。嗯，听起来你有一个非常好的，我的意思是，我认为最终结果不言自明，而且你们都没有让我说这些。**Intercom** 抓住了时机，你们全力投入 **AI** 辅助的客户支持和体验。你们现在正在构建模型，所以这不仅仅是一次性的：**ChatGPT** 来了，我们需要改变我们的产品工作方式，或者 **AI** 辅助编码来了，所以我们需要改变我们的工程团队工作方式。你知道，模型将是人们如何区分的方式，我们需要走向那里。**CLI** 将是人们如何使用产品的方式，我们需要走向那里。所以我认为这种无所畏惧，以及我所猜测的，一种有趣、良好、高度信任的文化，优秀的人，你们实际上看到了业务成果。所以我要为你们宣传。我看到了很多团队。我看到了很多领导者。而且我认为人们可以从中获得很多灵感。但是，在我让你离开这里之前，让我们快速地让他们失去灵感，这是我的最后一个问题，那就是当 **Finn** 在一个直播播客上花了 15 分钟完成一个非常基本的任务时，你知道它能做到，或者不是 **Finn**，当 **Claude Code**。

<details>
<summary>Original English</summary>

**Claire Vote**: Say it again for the people in the back. I love I was like, "Oh my gosh, I love this so much." And you know, I it it is absolutely those two things which is like give permission. You you can please just go please by all means go ahead designer hit me with a PR. No one's going to get mad at you. Like go ahead. And then the second thing of just accountability can roll to the top and not in a scary way. Let's not do irresponsible things. But I, you know, we've seen seen a couple incidents in the past months, some big ones, and what you see is CEOs or big leaders coming out and saying like the team's shipping and we want to keep shipping and we're going to be careful with our customer data and we care for the customer experience and stuff happens. We've learned from it. It's ultimately on me. I'm going to call the customers and we're going to we're going to move on and deliver great innovation for you. And you know what I tell people to, you know, to get them over that hump, which is like you really got to know what your existential problem is. And I love what you said is the second that chat GPT came out, intercom changed, because that is an existential problem. Who writes the code in your codebase, agents or humans? Not an existential problem. Like will you be fundamentally disrupted by a new technology? That is the real problem in your business. So, I always tell people like let's differentiate the real problems in our business from problems that we can tolerate and then go go use the problems we can tolerate to move fast. Um, and so it sounds like you have a really good I mean I think at the end of the day the results speak for themselves and again you all are not asking me to say this. Intercom has meant the moment you went all in on AI assisted you know customer support and experience. you're now building models and so it's not just a oneanddone chat GBT is here we need to change how our product works or AI assisted coding's here so we need to change how our engineering team works it's you know models are going to be how people differentiate we need to go there CLI are going to be how people use products we need to go there and so I think this sort of like fearlessness and what I would suspect is like just a fun nice high trust culture good people uh you actually see the business results on on the other side So, I'm going to hype you up. I see a lot of teams. I see a lot of leaders. Um, and I think people can take a lot of inspiration from this. But, let's uninspire them really quickly before I get you out of here, which is my last question, which is when um Finn takes 15 solid minutes on a live live podcast to do a very basic task that you know it can do or not Finn when when clog code.

</details>

**Brian Scanland**: 是的。

<details>
<summary>Original English</summary>

**Brian Scanland**: Yep.

</details>

**Claire Vote**: 你会大喊大叫吗？你是一个爱喊的人吗？嗯，

<details>
<summary>Original English</summary>

**Claire Vote**: What do you do? Do you yell? Are you a yeller? Um,

</details>

**Claire Vote**: 你的内部仪表板的元分析显示人类需要在哪些方面改进？

<details>
<summary>Original English</summary>

**Claire Vote**: what does your metaanalysis on this internal dashboard say the human needs to improve on?

</details>

**Brian Scanland**: 我确实会忍不住给 **Claude Code** 发送笑脸或不高兴的表情，你知道，不过分。我肯定没有咒骂它。

<details>
<summary>Original English</summary>

**Brian Scanland**: I I I do lapse into giving claw code like uh just like smiley faces or unhappy faces or, you know, not over the top. I I certainly haven't cursed at it.

</details>

**Claire Vote**: 非常礼貌。

<details>
<summary>Original English</summary>

**Claire Vote**: very polite.

</details>

**Brian Scanland**: 这有点不像我的风格。但我确实喜欢偶尔发个“好小子”之类的笑脸。我不知道它是否知道我正在深入思考这个问题，以及这些微妙的提示等等。但是，是的，我认为我的风格是专业的，带有一些表情符号，你知道，希望有朝一日它也会回馈我一个表情符号。

<details>
<summary>Original English</summary>

**Brian Scanland**: That's kind of not my smile. But I do like the odd kind of like at a boy kind of smiley face. I don't know if it knows like that I'm deeply thinking about this and like these little subtle kind of hints or whatever. But um yeah, no, I think like professional with a few emojis is is my style with Claude and you know hopefully that'll come back to me someday with an emoji.

</details>

**Claire Vote**: 同意。我把 **token** 浪费在告诉它做得好上。我总觉得在我的脑海中，这会进入它自己的意识中，它会知道什么是好的。所以我和你一样。好的，**Brian**。这是我最喜欢的之一，各位。如果你看到了最后，这期节目中有很多宝藏。我简直不敢相信。这是一个赢得朋友和通过 **AI** 工程影响 **SaaS** 的作弊码。**Brian**，我们可以在哪里找到你，我们如何能帮助你？呃

<details>
<summary>Original English</summary>

**Claire Vote**: Same. I waste the tokens on telling it it did a good job. I somehow in my mind I'm like that's going into into its own sense of it itself and it's going to know what good looks like. So I I am there I am there with you. All right, Brian. This has been one of my favorites, y'all. If you have gotten to the end, there is so much alpha in this episode. I cannot believe it. This is a cheat code to winning friends and influencing SAS um through AI engineering. Brian, where can we find you and how can we be helpful? Uh

</details>

**Brian Scanland**: 可以在互联网上找到我，有一个很好的专属 **URL**：brian.scan.ie。我那里有一些关于讲座、类似文章和各种零碎东西的链接。如你所知，我不是一个设计师。我让 **Claude** 把它设计得像一个 **Unix** 系统管理员写的一个小网页，效果也确实如此。我在 **X Twitter** 上很活跃，用户名是 **Brian Scanland**。我在 **LinkedIn** 上是 **Scanb** 或类似的。我想我是互联网上最有名的 **Brian Scan**。所以，通常你只要输入 **Brian Scan** 就能找到我，通常都能找到。我倾向于积极参与各种会议，并宣传我们在 **Intercom** 所做的工作，目前主要是 **AI**，但我也做过很多其他主题的讲座。而且，是的，我也非常相信对很多事情说“是”。所以如果你找到我，你有一个好主意，你想联系，你想把一些东西拿给我看，我很可能会说“是”。而且我会一直这样做，直到事情搞砸，然后我才会开始说“不”。但目前我还没到那个阶段。所以放马过来吧。

<details>
<summary>Original English</summary>

**Brian Scanland**: I can be found on the internet at a nice vanity URL which is brian.scan.ie. Uh and I got a few links here to some of the talks and similar writing and different bits and bobs. As you can tell, I'm not a designer. I asked Claude to design this as if I was a Unix systems administrator writing a little web page and it kind of shows. Um, I'm active on X Twitter and Brian Scanland. Um, I'm on LinkedIn Scanb or something like that. I think I'm the most famous Brian Scan on the internet. So, generally you can just type Brian Scan in that tends to work. Um, and I tend to be active in like showing up to different conferences and uh just like getting the good word out about what we do at intercom, mostly these days AI, but I've also given lots of talks about many other different topics. And um, yeah, I'm also a big believer in just saying yes to a lot of things. Um, so if you look me up, you got a good idea, you want to get in touch, uh, you want to run stuff past me or whatever, chances are I'll say yes. H, and we can I'll just keep on doing this until things break and then I start saying no. So, but I'm still not there yet. So, bring it on.

</details>

**Claire Vote**: 太棒了。所以，搜索 **Brian**，然后让他为你做点什么。就是这样。

<details>
<summary>Original English</summary>

**Claire Vote**: Great. So, search for Brian and ask him to do something for you. That's it.

</details>

**Claire Vote**: 好的，谢谢你。我的意思是，非常感谢你分享所有这些信息。人们会从中获得巨大的价值。这肯定会大受欢迎。我真的非常感谢你加入 "How I AI"。

<details>
<summary>Original English</summary>

**Claire Vote**: Well, thank you. So, I mean, thank you truly for sharing all this information. People are going to get tons of value out of this. It's going to be a hit for sure. And I just really appreciate you joining how I

</details>

**Brian Scanland**: 当然。这太有趣了。

<details>
<summary>Original English</summary>

**Brian Scanland**: of course. This is so much fun.

</details>

**Claire Vote**: 非常感谢大家的观看。如果你喜欢这个节目，请在 **YouTube** 上点赞并订阅，或者更好的是，给我们留言，分享你的想法。你也可以在 **Apple Podcasts**、**Spotify** 或你喜欢的播客应用上找到这个播客。请考虑给我们一个评分和评论，这将帮助其他人找到这个节目。你可以在 howiipod.com 查看我们所有的节目并了解更多。下次再见。

<details>
<summary>Original English</summary>

**Claire Vote**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>