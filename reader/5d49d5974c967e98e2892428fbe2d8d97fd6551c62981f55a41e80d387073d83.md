---
author: a16z
date: '2026-04-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=dvt_74kV-RM
speaker: a16z
tags:
  - ai-agent
  - software-architecture
  - compute-economics
  - enterprise-software
  - api-design
title: AI Agent 时代的到来：Aaron Levie 谈软件架构、集成与算力经济学
summary: 本场访谈深入探讨了 AI 能力扩散的周期，提出软件将从“为人构建”转向“为 Agent 构建”的范式转移。Aaron Levie 与主持人辩论了 Agent 在企业级集成中的潜力和风险、权限管理的演进，以及未来几年最核心的议题——算力预算与 Token 经济学。内容涵盖了从 SAP 的行业壁垒到“计算机使用”新范式的深度见解。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Box
  - Anthropic
  - OpenAI
  - SAP
  - Salesforce
  - Microsoft
  - Workday
  - JP Morgan
products_models:
  - Claude Code
  - GPT-4o
  - Box CLI
  - MCP
media_books: []
status: evergreen
---
### AI 能力的扩散与领域知识

**Aaron Levie**: **AI 能力**的扩散所需要的时间，将比硅谷的人们意识到的要长。

<details>
<summary>Original English</summary>

**Aaron Levie**: The diffusion of AI capability is going to take longer than people in Silicon Valley realize.

</details>

**主持人**: 认为你可以通过“**凭感觉写代码（vibe code）**”一路搞定像 **SAP** 这样的系统，这简直是荒谬的。所有的领域知识，并不仅仅体现在某种编排良好的数据层中。

<details>
<summary>Original English</summary>

**Host**: It's just absurd to think you're going to vibe code your way to like SAP. All of that domain knowledge, it's not just represented in some well orchestrated data layer.

</details>

**Aaron Levie**: 未来几年，**工程计算预算**的讨论将是最疯狂的一个话题。

<details>
<summary>Original English</summary>

**Aaron Levie**: The engineering compute budget conversation is going to be the most wild one in the next couple years.

</details>

**主持人**: 目前最大的问题是，每个人都在试图弄清楚这一切的**经济账**，而他们对机会规模的判断至少偏差了一个数量级。如果你拥有的 **Agent（智能体）** 数量是人类的一百倍或一千倍，那么你的软件就必须是为 Agent 构建的。

<details>
<summary>Original English</summary>

**Host**: The biggest problem right now is everybody is trying to figure out the economics of all of this when they're off by at least an order of magnitude on how big the opportunity is. If you have a hundred or a thousand times more agents than people, then your software has to be built for agents.

</details>

### 为 Agent 构建软件的新范式

**Aaron Levie**: 人们在抽象层面会说，“现在你是在向 Agent 做营销，你就像一个 API，你有一个很好的 **IDL（接口定义语言）**。” 我实际上认为这几乎是完全错误的。

<details>
<summary>Original English</summary>

**Aaron Levie**: People in the abstract say things like, "Now you're marketing to agents that you're like an API. You've got a good IDL." I actually think that's almost exactly wrong, which is—

</details>

**主持人**: 哇，这可是播客界的重磅新闻。

<details>
<summary>Original English</summary>

**Host**: Wow, this is breaking podcast news.

</details>

**Aaron Levie**: 如果你开始想象我们都必须**为 Agent 构建软件**，我想大家对这一点都很清楚，对吧？这个趋势正在发生，即我们现在花在思考工具的 **Agent 接口**上的时间，和思考人类接口的时间一样多。当然，我们这么做的原因是我们的假设：如果你拥有的 Agent 数量是人类的一百倍或一千倍……

<details>
<summary>Original English</summary>

**Aaron Levie**: If you start to imagine that we all have to build software for agents, I think we're like all clear on that, right? So like that trend is happening which is like we spend as much time now thinking about the agent interface to our tool as we do the human interface. Sure. And the reason we're doing that is because our hypothesis would be that if you have a hundred or a thousand times more agents than people—

</details>

**主持人**: ……那么你的软件就必须是为 Agent 构建的。那么这些 Agent 与你的系统交互的方式是什么？它将通过 **API**、**CLI** 或 **MCP**（模型上下文协议）等等。目前看来，正在兴起且在效能方面相当成功的范式是：如果你给一个**编程 Agent** 访问你的 **SaaS 工具**的权限，给它访问你的知识工作流和上下文的权限，这就会变成一种**超级力量**。这不仅仅是 Agent 能够读取某些数据、理解某些信息，它实际上可以编代码或者通过 API 来完成它试图实现的任何任务。

这种范式似乎正在产生复利效应。这就是 **Claude Code** 现象，也是 **OpenAI** 正在酝酿的东西——超级应用、Perplexity、计算机控制等等。我实际上认为这作为这一切的最终表现形式是有道理的。

<details>
<summary>Original English</summary>

**Host**: —then your software has to be built for agents. And then what is the way that those agents are going to interact with your system? It's going to be through an API or a CLI or MCP or whatever. And the paradigm that appears to be taking off and is quite successful so far in terms of efficacy is what if you give a coding agent access to your SAS tools and a coding agent access to you know your knowledge work sort of workflows and context and that kind of becomes this superpower which is it's not just like the agent is not only capable of reading some data understanding some information it can actually code its way or uses APIs through whatever task it's trying to achieve. That appears to be like a paradigm that is starting to compound. And you know that was the that's the Claude Code phenomenon. That's the whatever OpenAI is kind of cooking up, with the super app, Perplexity, computer control etc. And I actually think it kind of makes sense as the ultimate manifestation of this stuff.

</details>

### 算法思维与抽象层的演进

**Aaron Levie**: 我认为你是对的，这在理论上是说得通的。

<details>
<summary>Original English</summary>

**Aaron Levie**: I think I mean I think you're right. It makes sense in a theoretical way. Yeah.

</details>

**主持人**: 但在实践中，我们必须非常小心。我想说的是，对于绝大多数有工作的人来说，**算法思维（Algorithmic thinking）** 真的非常、非常、非常难。

<details>
<summary>Original English</summary>

**Host**: But in a practical way, we have to be really careful in that the way to say it is algorithmic thinking is really really really hard for the vast majority of people who have jobs.

</details>

**Aaron Levie**: 是的。

<details>
<summary>Original English</summary>

**Aaron Levie**: Yeah.

</details>

**主持人**: 最简单的理解方式是，如果你走进任何一个人，要求他们为自己必须做的某件事画一个**流程图**，他们大概率画不出来。

<details>
<summary>Original English</summary>

**Host**: And so the easiest way to think about it is if you were to go into any person and ask them to create a flowchart for a particular thing that they have to go do, they would probably fail at producing that flowchart.

</details>

**Aaron Levie**: 没错。

<details>
<summary>Original English</summary>

**Aaron Levie**: Yep.

</details>

**主持人**: 所以在任何组织中，比如制定一个营销计划，有 50 个营销人员在一个巨大的产品线上工作，可能只有一个人理解并能记录下这个流程图。

<details>
<summary>Original English</summary>

**Host**: There. So within any organization, you know, say doing a marketing plan and there's 50 marketing people working on a giant product line, one person probably understands and could document the flowchart.

</details>

**Aaron Levie**: 100%。

<details>
<summary>Original English</summary>

**Aaron Levie**: 100%.

</details>

**主持人**: 所以如果你把这些 Agent，或者把这种协作工具放在人们面前去创造这些东西，他们向它解释该做什么的能力是非常有限的。

<details>
<summary>Original English</summary>

**Host**: So if you put one of these agents or you put this coworking tool in front of people to create these things, their ability to explain to it what to do is really really limited.

</details>

**Aaron Levie**: 100%。但是，如果这成为了你与计算机交互的**新方式**，你只需要循环往复地去适应它呢？

<details>
<summary>Original English</summary>

**Aaron Levie**: 100%. But what if that becomes the new way you have to interface with computers and you just have to cycle that through.

</details>

**主持人**: 那么你基本上只是在开发下一层**抽象层**。在历史上，每一层抽象层都是由组织内高技能、非常专业的个人开发的。然后他们构建的小部分就变成了人们执行特定任务的小工具。有些人能够把它们缝合在一起，有些人则不能。但这在以前的回形针和图钉时代发生过，在我们接下来的任何行动中也同样会发生。

<details>
<summary>Original English</summary>

**Host**: Well then you're basically just developing the next abstraction layer for how people interact. And the developing an abstraction layer has historically at each level of the abstraction layer been a highly skilled very specific individual within an organization developing that. And then the little parts that they build just become little toollets in the world of people doing particular tasks. And some people are able to stitch them together and some can't. But that happened with paper clips and thumbtacks before and it's going to happen with whatever we do next.

</details>

### 从电子表格到 Agent 的历史轮回

**Aaron Levie**: 我认为本质上永恒的部分是，工作只是往上走了一个台阶，你学到了一套新的技能。这就是为什么我认为这没什么不同，只是现在你获得的**杠杆作用**显然是巨大的。

最近有一个很火的推文，是关于 **Anthropic** 的一名增长营销人员。你们看到了吗？基本上就他一个人，当时他正在使用 **Claude Code**，基本上自动化了原本需要 5 到 10 个不同岗位的人才能完成的工作。我觉得这很有趣的原因是，你必须是一个**系统思想者（systems thinker）** 才能做到这一点。显然，他已经具备了足够的技能来完成这件事。但这确实代表了未来这些工作会变成什么样：想象一下在未来的经济中，每个人的身边都有一个无限量供应的工程师池，可以自动化任何你想做的事情。

我同意你必须找到一种方式，把你的工作看作一个系统才能成功。也许 Agent 随着时间的推移会越来越擅长引导你朝着那个方向发展。但理所当然地，你会开始尝试自动化大量的重复工作，比如：“为什么我不把谷歌广告中有效的关键词提取出来，移植到 Facebook 上，确保它们被复制，然后根据市场的新信号进行调整？”

<details>
<summary>Original English</summary>

**Aaron Levie**: I think basically the timeless part is the job just moves up a rung and you learn a new set of skills and that's why I actually don't think anything about this is any different. It's just now the leverage you get is obviously fantastic. There was this viral kind of tweet that went around which was the Anthropic growth marketer. Did you guys see this? It's basically one person and he was using Claude Code at the time to basically automate what maybe five or 10 people would have done in various kind of silo jobs. And I think the reason why it's interesting is yeah you had to have been a systems thinker to be able to accomplish that. So like clearly he already was technical enough to be able to pull that off. But it did kind of represent what would each of these jobs look like if you had imagine you had X job in the economy and right next to that person was an infinite pool of engineers that could automate whatever that person wanted and what would that job look like in the future as a result of that automation that now is possible. Yes, I agree that you'd have to find a way to think through your job as a system to be able to pull that off. Maybe the agent gets better and better over time at being able to like nudge you in that direction. But it does sort of stand a reason that like you will start to try and automate a lot of that kind of work of like, well, why don't I take like the keywords that are working in Google Adwords and then port them over to Facebook and make sure that those are replicated and then take in the new signal from what's happening in the market.

</details>

**主持人**: 那是一个巨大的飞跃。我们先说一件事。

<details>
<summary>Original English</summary>

**Host**: That's a big leap. Like so one thing first.

</details>

**Aaron Levie**: 我差点就说服你了。你刚才还在微微点头，然后我说了些过头的话。

<details>
<summary>Original English</summary>

**Aaron Levie**: I almost had you. You were nodding a little bit and then I said something that went too far.

</details>

**主持人**: 以那个 Anthropic 的增长人员为例，那是一个需求无限且供应无限的工作。这并不是一份困难的工作。让我们换个例子，想象一下如果你是澳洲一家加油站的老板……

<details>
<summary>Original English</summary>

**Host**: The Anthropic growth person as an example like that's a job where demand is infinite and frankly supply is infinite. This is not a difficult job. So let's instead say the guy that runs the petrol pump in Australia right now is amazing.

</details>

**Aaron Levie**: 好的，好的。那么换成是一个推广 600 美元个人电脑的营销人员，看看你怎么对抗 **Neo**。那才是一份真实的工作。

<details>
<summary>Original English</summary>

**Aaron Levie**: Right. Right. So like instead be the $600 PC marketing person and see how you can do against the Neo. That's a real job.

</details>

**主持人**: 行吧，我们需要一个更好的例子。但这里面确实有些非常有趣的东西。让我举个“老年人”的例子：我的表姐，顶级名校 MBA毕业，刚参加工作时正处于计算机化的前夕。她在研究生院时还没用过**电子表格（spreadsheet）**，然后电子表格出现了，但她不是那种会操作表格的人。于是公司告诉她：你想雇多少实习生就雇多少。所以她工作的头一年，基本上就是在监督一整屋子的“Agent”。

<details>
<summary>Original English</summary>

**Host**: All right, fine. We need a better example. But there is really interesting. Let me do an old person example like my cousin, MBA elite school, joined her first job right on the cusp of computing. She actually didn't use a spreadsheet in grad school and then a spreadsheet showed up but she wasn't a spreadsheet person so instead they told her hire as many interns as you want and so her first year on the job she supervised essentially a whole room of agents.

</details>

**Aaron Levie**: 明白了。

<details>
<summary>Original English</summary>

**Aaron Levie**: Yeah.

</details>

**主持人**: 那些大学生——不是字面意思上的我，但也是像我一样的年轻人——进来后包揽了所有的电子表格工作。

<details>
<summary>Original English</summary>

**Host**: And the kids who was me not literally but they were in college came and just did all the spreadsheeting.

</details>

**Aaron Levie**: 是的。但接下来的几年里，神奇的事情发生了：她和她的同龄人都变成了会操作电子表格的人。

<details>
<summary>Original English</summary>

**Aaron Levie**: Yeah. But then what happened magically over the next couple years was she and her cohort all became the spreadsheet people.

</details>

**主持人**: 没错。那种“你是银行经理或工作两年的员工，就意味着有一群人帮你做表格”的想法消失了，整个**抽象层**上移了。在这些实习生出现之前的旧工作是，你坐在那里，拿着计算器（比如 HP 计算器）为某个并购交易计算模型，在必须拿出投屏简报或去见客户之前，你只能完成两次迭代。突然之间，他们自己就能完成 30 次迭代。

所以我认为我们现在对待 Agent 的阶段，就像是那个你认为需要 50 个人的阶段。目前的抽象层使得我们将任务拆解得非常细碎，由一个超级聪明的人来协调。很快，这一切都会崩塌并融合，最终会形成一种技能集，或者一段代码——管它叫“营销类 Agent”吧。

你可以问它营销方面的事情，并让它去执行。我对于“去执行”这一点持保留意见，直到 AI 中那些不可复现、随机的元素消失。因为“做事”的代价会变得非常昂贵，然后我们就会陷入“**人机回环（Human in the loop）**”的讨论。

但我感觉，现在我和那些尝试用 AI 做事的人交谈，就像在感恩节晚餐上跟我表姐聊天一样。她才工作六个月，而我已经在使用电子表格了，我心想：“我不知道这为什么这么难，你应该直接用这个工具。”

<details>
<summary>Original English</summary>

**Host**: Yeah. And then this idea that you being a manager in a bank or just two years in meant you had a cadre of people doing spreadsheet. No, the whole abstraction layer moved up. And the old job before those interns was you sat there with basically calculators and an HP calculator figuring out the model for some M&A deal or whatever and you only got to do like two iterations before you had to put out the pitch deck or just go to the customer or the client or whatever and then all of a sudden they're doing 30 iterations themselves. But I think where we are with agents is just at this step where you think you need 50 and the abstraction layer is such that we're dividing up in these really small pieces with one super smart person coordinating them all and pretty soon that whole thing is just gonna collapse on each other and there is just going to be like a skill set amount of code call it an agent that is like marketingish. And you'll be able to ask it marketing stuff. And then the next step will be and have it go do things. I'm a little skeptical of the until the whole like non-reproducible, non-random element of this AI stuff goes away, the doing stuff is going to get very costly and so then you get into the human in a loop discussion and all of that. But I think we're just at that exact I feel like when I talk to people trying to do stuff that we're right at I feel like I'm at Thanksgiving dinner talking to my cousin six months in her job when I'm using a spreadsheet already and I'm like I don't know why this is so hard. You should just use one—

</details>

**Aaron Levie**: 然后两年后，她也开始用了。

<details>
<summary>Original English</summary>

**Aaron Levie**: —and then two years later she's doing it.

</details>

**主持人**: 我认为现在你必须是一个绝对的“火箭科学家”兼增长营销人员，才能创建 42 个 Agent 并让它们全部运转起来。但那部分“火箭科学”很快就会蒸发掉。到那时，你谈论的就是一整块被掏空的**领域专长**。

<details>
<summary>Original English</summary>

**Host**: And I think this right now you have to be an absolute you have to be a rocket scientist and the growth marketing person to create 42 agents and spin them all up and do all of this stuff. But the rocket science part of it just is going to evaporate in very short order and then you're talking about wow there's a giant chunk of domain expertise that—

</details>

**Aaron Levie**: ……又回到了领域专家手中。

<details>
<summary>Original English</summary>

**Aaron Levie**: —it goes back to the domain expert.

</details>

### 计算机使用（Computer Use）：不仅仅是生成代码

**Aaron Levie**: 我想对你刚才说的另一面提出看法。我觉得人们很容易认为“这些 Agent 会编写代码并执行 X 任务”。

<details>
<summary>Original English</summary>

**Aaron Levie**: So I actually think something that you said I'll take the other side of which is I think it's very tempting to be like these agents are going to code and do X. Yeah.

</details>

**主持人**: 但我认为我们正在朝着相反的方向发展。起初，我们会拿一个 SaaS 软件，然后加入 AI。

<details>
<summary>Original English</summary>

**Host**: But I think we're going the opposite way. So I think actually where we started was we'd like take like a piece of SAS software and we'd add AI. Yeah.

</details>

**Aaron Levie**: 那就是所谓的“AI 赋能（AI enabled）”。那是使用代码完成这类事情的极端版本。但现在我们实际在做什么？我们发现 SaaS 软件依然是 SaaS 软件，而 Agent 像人类一样把它当作计算机来**使用**，因为它其实非常擅长这个。我想说，我们从编写代码开始……

<details>
<summary>Original English</summary>

**Aaron Levie**: And then that's like the new kind of like AI enabled. So that's like the extreme version of using code for these types of things. But now what are we actually doing? We're like okay the SAS software is still SAS software and the agent uses it as a computer because like it's actually very good at that. So I'd say like we started with code—

</details>

**主持人**: ……然后我们转向了终端（Terminal），那里的代码更少。

<details>
<summary>Original English</summary>

**Host**: —then we went to the terminal which is actually less code. Yeah.

</details>

**Aaron Levie**: 而今年将是“**计算机使用（Computer Use）**”之年。没错，它们更像是像人类一样使用计算机，而不是生成代码。这感觉非常像是一个中间台阶。我实际上来自生成代码的世界，但我认为这种方式正在变少，而不是变多。

<details>
<summary>Original English</summary>

**Aaron Levie**: And now this year is going to be the year of computer use. Yes. So it's almost like they're much more like humans using computers than them generating code. And that feels like very much like this mezzanine step. Yeah. And I actually come from like the generating code type of the world. Like I would argue that that's happening less, not more.

</details>

**主持人**: 对我来说，无论是计算机使用、API 调用，还是即时编写代码，我可能错误地把它们都归为了同一个大类。

<details>
<summary>Original English</summary>

**Host**: Yeah. I think to me whether it's computer use, API use, or writing code on the fly, I kind of maybe erroneously put that all in one blank category.

</details>

**Aaron Levie**: 它们非常不同。

<details>
<summary>Original English</summary>

**Aaron Levie**: They're very different.

</details>

**主持人**: 确实非常不同。但我们正在开发一个 Agent，它会自主判断：是应该使用现有技能，使用 Box 的现有工具，还是应该**编写代码**来解决问题。它在任何时刻执行这三者之一的能力是非常有用的。因为有时你就是想执行某种特定的操作，而即时写一段代码来完成它会更快，我们不可能预先考虑到每个人对文档的所有需求。所以模型足够强大，能够为特定用例即时编写代码，这成了一个惊人的特性。尽管也许 90% 的情况下它应该只使用现有的工具。

<details>
<summary>Original English</summary>

**Host**: They're very different. But what we have an agent that we're working on where it just makes a determination whether it should use an existing skill, it should using an existing tool from Box, or it should write code to solve that problem. And its ability to do any one of those three at any moment ends up being incredibly useful because sometimes there's just some specific operation you want to be able to do where writing code to be able to do that operation is just faster and we don't have to we can't possibly pre-plan for every thing that anybody would ever want to do on their documents. And so the fact that the the model is good enough to also write code on the fly for that use case ends up just being like an amazing property even though maybe 90% of the things that it's going to do should just be using an existing tool.

</details>

### 消费层与记录系统的错位

**Aaron Levie**: 随着时间的推移，事情往往会整合。比如人们的 iPhone 上可能只有七个应用，或者只有七个常用的 SaaS 应用。

<details>
<summary>Original English</summary>

**Aaron Levie**: Over time there's like literally like seven apps on her iPhone there's seven SAS apps we end up like over time these things tend to consolidate.

</details>

**主持人**: 但 iPhone 上只有七个应用的问题在于人类不想一遍又一遍地学习新东西。作为一个人类，我没有足够的心理带宽去学习那么多应用。但一个使用工具和 API 并且能编写代码的 Agent，并没有我们人类这样的限制。

<details>
<summary>Original English</summary>

**Host**: But the seven apps on the iPhone is a issue of humans don't want to learn these things over and over again and so I as a human I don't have the mental bandwidth to learn that many apps but an agent that is going to use tools and APIs and be able to code things doesn't have any of the same constraints that we have.

</details>

**Aaron Levie**: 确实，你可以说有很多事情要做，你可以把界面做得足够通用。

<details>
<summary>Original English</summary>

**Aaron Levie**: Well you could argue that there's just so many things to do and you can make interfaces sufficiently general.

</details>

**主持人**: 我很喜欢你刚才说的。我们达成一致了。软件演进中有一点非常有趣：比如我整天都在用 **SAP**，我在财务部门工作。我必须生成所有这些报表，然后有人跑过来说，我想要一份这种视角、那种切片的报表，我就傻眼了，“天哪，我不知道该怎么做”。我现在得去翻遍 SAP 的帮助系统去寻找方法。AI 非常擅长的一点是，它可以比人类更好地导航那片功能区域。帮助文档都在那里，这只是一个寻找并映射语言的问题。

在过去的 25 年里，人类一直是挖掘软件能力的瓶颈。我这辈子在飞机上坐在别人旁边，经常听人说：“我怎么才能让 PowerPoint 实现 X 功能？”

<details>
<summary>Original English</summary>

**Host**: Let me I think I like what you said then because I'm back. We're back. Okay, we're aligned. No, but I think there's something super interesting here which I do really really like which is that where software has evolved, you know, like I use SAP all day. I work in finance. I have to go and generate all these reports and then somebody shows up and says I want a report that does this view slice this way and I'm like oh god I don't know how to make that right and like now let me go wade through the SAP help system and try to find it. One thing that let's just say AI could be very good at is it actually can navigate that surface area much much better. the help is all there and so it's a matter of finding it mapping language and humans have been a bottleneck in tapping the past 25 years of software capabilities. I mean like I spent my life sitting next to people on airplanes saying how can I make PowerPoint do X?

</details>

**Aaron Levie**: “直接去看功能区（Ribbon）啊！”

<details>
<summary>Original English</summary>

**Aaron Levie**: "Just go to the ribbon!"

</details>

**主持人**: 看着别人在 Word 里的项目符号和编号上痛苦挣扎，或者试图在 Excel 里做一个双轴图表——那简直像火箭科学一样难，几乎没人会做，但又非常普遍。所以这种阻抗不匹配，本质上是一个**人类用户界面**的问题。

<details>
<summary>Original English</summary>

**Host**: Well and you know it was because it hurt physically hurt to watch somebody suffering with bullets and numbering in Word or trying to figure out you know like oh let me just make a two-sided a two axis graph in Excel which like is rocket science like almost no one can do that but yet it's super common and so that impedance mismatch was a human user interface.

</details>

**Aaron Levie**: 我完全认同在**消费层（consumption layer）**的说法。即完美的、流动的 UI 或消费层。但我感觉后端，即那些**记录系统（systems of record）**，它们可能会收敛到某种通用的 API 集，它们会相互连接。这似乎是未来的发展方向。

<details>
<summary>Original English</summary>

**Aaron Levie**: I totally buy it on the consumption layer I totally buy it which is like the the perfectly fluid like UI or consumption layer I just feel the backend like the systems of record it'll probably converge into like some database like some generic set of APIs like that they'll connect to and like that seems to be the direction it's going.

</details>

### 集成挑战与“首席信息官的恐惧”

**Aaron Levie**: 整个周末我都在实现我的 **Nano Cloud** 机器人。刚开始时，就像是在为所有东西构建集成。

<details>
<summary>Original English</summary>

**Aaron Levie**: Well like so I spent all weekend like implementing my nano cloud bot and when you first start out it's like you're building an integration for everything.

</details>

**主持人**: 好的，办公效率。但当你面对一个拥有全球供应链、涉及 30 个不同系统的 75 项信息的公司时，这确实需要 Agent 具备某种我们目前为止任何架构都无法提供的“马力”。但你刚才描述的，正是软件 50 年来一直在做、并且会继续做下去的事情。我有一个朋友曾是退伍军人事务部（VA）的 CIO，他所有的时间都花在了将 VA 的那 75 个系统粘合在一起。这全是**集成冗余**。

<details>
<summary>Original English</summary>

**Host**: Okay, fine. Work productivity and then an SAP system and so there's an infinite amount of complexity when you get to okay some company that has a global supply chain and they're dealing with 75 pieces of information across you know 30 different systems that does require a certain amount of horsepower from the agent that is just we've I mean we just haven't been able to get from any architecture up until now. But that what you just described is literally what it has been doing for 50 years and will continue to do which is you know I have a friend who was the CIO of the VA and he spent his time on was gluing those 75 VA systems together and it's all just integration redundancy.

</details>

**Aaron Levie**: 非常适合集成。我完全同意。

<details>
<summary>Original English</summary>

**Aaron Levie**: Perfect for integration. Yeah. This I totally agree. Okay, great.

</details>

**主持人**: 对于集成来说，这些东西是最棒的。但这就是集成，对吧？字面意思上就是我如何缝合这两个系统。

<details>
<summary>Original English</summary>

**Host**: For integration, these things are the best, but it's integration, right? It's literally how do I stitch these two systems.

</details>

**Aaron Levie**: 但现在正在发生的事情是，这变成了**按需集成（integration on demand）**。

<details>
<summary>Original English</summary>

**Aaron Levie**: But now the thing that I think is happening is it's kind of like integration on demand.

</details>

**主持人**: 这是我在系统中的新查询需求，IT 团队没有预先写好。现在我需要它在运行时发生。

<details>
<summary>Original English</summary>

**Host**: It's my new query in the system that the IT team didn't pre-wire. Now I need it to happen at runtime.

</details>

**Aaron Levie**: 让我说两句。我刚才待在一个满是 CFO 和 CIO 的房间里。当我提到类似观点时——虽然没有你想象的那么乐观，但我说的是“现实主义”——结果有六个人跑过来对我说：“你疯了，你已经失去了我的信任。” 因为……

<details>
<summary>Original English</summary>

**Aaron Levie**: So, okay. So, the reason I just was in a room filled with a bunch of CFOs and CIOS and they all looked at me when I said something along these lines, although not as optimistic as you can imagine, but they just realism. No, it caused like six of them to come running up afterwards and say, "You're insane. You've lost all credibility with me." Because it's—

</details>

**主持人**: 等等，具体是什么？是 Agent 会做集成这件事吗？

<details>
<summary>Original English</summary>

**Host**: Wait, wait, what? What specifically that the the agents are going to do integration?

</details>

**Aaron Levie**: 没错。他们认为集成是个会变得容易得多的问题。

<details>
<summary>Original English</summary>

**Aaron Levie**: That the integration is a problem that will get a lot easier. Yes.

</details>

**主持人**: 他们反对这个观点？

<details>
<summary>Original English</summary>

**Host**: They were against that.

</details>

**Aaron Levie**: 不，没人反对其实用性。但他们的恐惧在于，不仅释放了 Agent 自身，还让普通人类也能做集成。如果你让人们随意创建新的集成，你基本上就是在说：“请搞垮我的**记录系统**吧。”

这种“在系统 27 和系统 38 之间创建个新 API”的想法，对于生成报表来说可能没问题，因为如果那个人想错，那是他自己的事。但你不能……

<details>
<summary>Original English</summary>

**Aaron Levie**: No, one's against practical, but their fear is like unleashing not just the agents themselves but humans to do integration because you put people creating new integrations and you just say please break my system of record. Oh yeah. And so this idea that you just create like a new API between you know system 27 and system 38 and then that might be fine for a report because if that person wants to be wrong that's their business but you're not—

</details>

**主持人**: 我认为在接下来的几年里，我们会有一个**只读版本**。

<details>
<summary>Original English</summary>

**Host**: I think I think we have a readonly version of this for a number of years before—

</details>

### Box CLI 与 Agent 的身份难题

**Aaron Levie**: 我们刚刚推出了官方的 **Box CLI**。谢谢你点赞了那条推文。

<details>
<summary>Original English</summary>

**Aaron Levie**: We actually have so we just rolled out the official box CLI. Thank you for the liking the tweet on that.

</details>

**主持人**: 我用过了，有一些反馈，回头聊。

<details>
<summary>Original English</summary>

**Host**: I've used it. I have some feedback. We'll talk about—

</details>

**Aaron Levie**: 欢迎所有反馈。这真的很有趣。我们内部有过争论：如果你给 **Claude Code** 这个 Box CLI，你现在就可以通过自然语言与你的整个 Box 系统交互。由 Opus 或 4o 作为编排者来执行一系列操作，这简直让你大开眼界。你可以说：“把桌面上这个文件夹全部上传到 Box”，它就能成。或者“处理这个文件夹里的所有文档”，它也能行。

然后我们开始思考：假设你有一家拥有 5000 名员工的公司，每个人都有权访问某些共享库，比如工程文档、营销资产。如果每个人都运行着带有 CLI 的 Agent，哇，我们现在面临一些非常有趣的新挑战：比如你怎么协调？你可能每小时会请求系统一万次。不是性能问题，而是你怎么确保某人在试图执行写操作时，另一个人没有意外地把文件从一个文件夹移动到另一个文件夹，或者有人正在试图删除某些东西？这些**失控运行的 Agent**，将是每个 CFO、CIO 抓耳挠腮的新大问题。

<details>
<summary>Original English</summary>

**Aaron Levie**: I'll take all the feedback. But it's a really interesting thing. So we had these all these debates internally of like okay you give Claude code the box CLI and you can now interact with your entire box system via natural language and you get the horsepower of Opus or 4o being the orchestrator of doing a bunch of operations and it's like it's like you know blows your mind. I guess I'll get some feedback, but it blows your mind in some ways because you could just be like, upload this entire folder from my desktop into box and it'll work or process all these documents in this folder and it'll work. And it's amazing. And then we started thinking through like well let's say you were a company with with you know 5,000 employees and everybody had access to some shared repository like you know engineering documentation and you know marketing assets or whatever and everybody had running with the CLI. Wow. We now have some really interesting new challenges which is like how do you coordinate you know possibly the fact that you might be hitting the system like you know 10,000 times an hour or something. Not from a like a performance standpoint but just like how do you make sure that people didn't move like a file from one thing accidentally from one folder to another folder while the other person was trying to do a write operation and somebody else was trying to delete something because you have these agents running wild. This is going to be like the new big question that every CFO, CIO, etc. is running around trying to with their hair on fire.

</details>

**主持人**: 这正是我遇到的问题。我玩了一下你的示例，创建一个营销计划目录，突然间我就陷入了某种无限循环，疯狂创建目录。

<details>
<summary>Original English</summary>

**Host**: There's just that's exactly what I ran into which is I played around with your example which is create a marketing plan directory or something and like all of a sudden I'm like in some loop creating directories—

</details>

**Aaron Levie**: 它会尽可能久地运行下去。

<details>
<summary>Original English</summary>

**Aaron Levie**: It's going to go on as long as it can.

</details>

**主持人**: 对吧？我在想 Box 对嵌套目录的限制是多少，因为我快要撞线了。

<details>
<summary>Original English</summary>

**Host**: Right? And I was like I wonder what the limit is on box for nested directories because I'm about to hit it.

</details>

**Aaron Levie**: 实际上，我们也会很快发现这个限制。

<details>
<summary>Original English</summary>

**Aaron Levie**: Actually we're gonna find out too.

</details>

**主持人**: 没错。但我觉得很多人的直觉是去建立一套新的控制层之类的。但实际情况恰恰相反。举个例子：当我们使用这些个人 Agent 时，我们会给它们我们的 **API Key**，给它们我们的电子邮件地址。然后人们会问：“但我怎么阻止它乱来？”

所以现在大家的做法是：给它一个**专属电话号码**。没错，我甚至给我的 Nano Claw 办了张专属信用卡。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. Yeah, but it it does feel to me that that a lot of the intuition is to like build a new layer of controls and whatever. But what's actually happening on the ground is the opposite. So I'll give you an example. Like when we all picked up a lot of these personal agents, we would like give them our API keys. Yeah. We would give them our email addresses and then they would kind of access those things and they're like, "Oh, but how can I stop it from like whatever?" And so what everybody's doing now is you give it its own phone number. Yep. I actually gave my Nano Claw its own credit card came in.

</details>

**Aaron Levie**: 希望只是你在 CVS 药店买的那种 Visa 借记卡。

<details>
<summary>Original English</summary>

**Aaron Levie**: Hopefully just a Visa debit card that you bought at CVS.

</details>

**主持人**: 没，我给它办了专属的 Gmail 账号。你可以登录进去，而 Gmail 实际上有整套的 **RBAC（基于角色的访问控制）权限**。所以你可以辩论说，我们实际上已经内置了很多这类权限系统。你必须把它当作一个**独立的人**来对待。

<details>
<summary>Original English</summary>

**Host**: All the money, but I gave it its own Gmail account which you can log into and then Gmail actually has all of these arback permissions. So you could make an argument that you know we've actually built in a lot of these permission systems. You have to treat it like a human as a separate human and then instead of like building another off layer—

</details>

### Agent 的安全、隐私与“提示词注入”

**Aaron Levie**: 好吧，那我能瞬间拆穿这个观点吗？这对个人效率来说很棒，但我们在企业中会遇到的问题是：假设我有一个 50 人的团队，是让每个人都拥有一个 Agent 在同一个共享空间协作吗？我有 50 个人类和 50 个 Agent。

我对我的 Agent 有完全的监督权，但如果我的 Agent 与别人的 Agent 协作，由于它们在共享，结果我的 Agent 意外获得了我不该访问的资源权限，而这个自主运行的 Agent 正在处理别人的信息。

<details>
<summary>Original English</summary>

**Aaron Levie**: Okay now can I instantly take do a take down of this element that we're going to run into? Okay so that is fantastic for personal productivity and the question that we're going to run into is in an enterprise let's say I have a 50 person team of something—should everybody basically will we have a hundred people now collaborate basically 50 humans and then 50 agents in that same shared space and do I have I obviously have complete oversight over my agent but what if my agent collaborates with somebody else and then accidentally gets access to some resource because they were sharing with that other person and I'm not supposed to have access to that resource and now this autonomous sort of stateful agent is running around working on somebody else's information.

</details>

**主持人**: 默认的端到端论据是你像对待人类一样对待它们……

<details>
<summary>Original English</summary>

**Host**: The default end to end argument is you treat them like human beings and—

</details>

**Aaron Levie**: 这行不通。你不能完全把它们当人看，因为对于人类同事，你不能随便翻看他的 Slack 频道，你不能以他的身份登录，你不能时刻监视他。他们在现实世界中对自己的执行负责。Agent 搞砸了，你不会被惩罚；但 Agent 做的任何事，你都有全部责任。你确实有完全的监督权，而且你可能需要这种监督权。

Agent **没有隐私权**。所以会有这种无法像对待真人那样清晰划分的情况。我需要能给它们授权，但也需要能随时以它们的身份登录并说：“不不不，你把整件事搞砸了，我要撤销所有操作。” 但如果我能以它们的身份登录，它们如何在现实世界中与他人合作并保持机密或安全？所以，它依然是你本人的**延伸**。几乎无法避开“它是你本人的延伸”这一点。

<details>
<summary>Original English</summary>

**Aaron Levie**: —it doesn't work. So you can't fully treat them like humans because here's the thing and with regular humans you don't get to look at the Slack channel of the person that that is working with you or working for you. You don't get to log in as them. You don't get to oversee them. They are accountable for their own set of execution in the real world. You don't get penalized for what how they screw up the agent. You have all the liability of whatever they're doing. you do have complete oversight and you're probably going to need to have that complete oversight. They have no right to privacy. So, so there's going to be these some of these breakdowns that aren't as clean as just treat them like a person because I need to be able to kind of I need to be able to give access to something to them, but I also need to be able to like log in as them at some point and be like, "No, no, you [ __ ] up the whole thing and I need to undo it all." But if I can log in as them, how could they have operated in the real world working with other people and keeping anything, you know, confidential or secure or whatever? So, it really is still an extension of you. It's like almost impossible to get around them being an extension of you.

</details>

**主持人**: 我不觉得这在逻辑上必然成立。比如对于我的员工，我可以以他们的身份登录，我可以获取他们的邮件……

<details>
<summary>Original English</summary>

**Host**: I I I just doesn't logically follow. Yeah, maybe. But, for example, um for my employees, I can log in as them. I can get access to their email.

</details>

**Aaron Levie**: 但你不会真的这么做。你不会因为他们发了一封邮件就日常登录他们的账号。除非有诉讼之类的。

<details>
<summary>Original English</summary>

**Aaron Levie**: You don't though. You don't you don't. Yeah. No, in like in a if you get like sued. You're not logging in. You're not logging in as them on a regular basis because they sent one email.

</details>

**主持人**: 难道 Agent 的理想运行模式不是一样的吗？

<details>
<summary>Original English</summary>

**Host**: Isn't the right operating model with an agent the same thing?

</details>

**Aaron Levie**: 风险要大上一千倍。这些东西随时会泄露你的信息。只要被诱导（prompted），它们会很乐意给某人发封邮件。

你认为最终状态是，这些东西依然是这些“邋遢”的计算机，因此它们永远……

<details>
<summary>Original English</summary>

**Aaron Levie**: The risk is like a thousand times greater. Like these people like they will just leak your information whenever they want. Like they will happily just go and send some email to somebody because they got prompted. You think the terminal state is that these things are still these sloppy computers and therefore they will always—

</details>

**主持人**: 我不喜欢“邋遢（sloppy）”这个词，除非是在口语意义上。

<details>
<summary>Original English</summary>

**Host**: I don't like the word sloppy. Um unless we're saying it very in a colloquial sense. Um but like—

</details>

**Aaron Levie**: ……它们永远无法保密信息。

<details>
<summary>Original English</summary>

**Aaron Levie**: —they'll never be able to contain information. They'll never—

</details>

**主持人**: 我认为，让 **Context Window（上下文窗口）** 里的东西保持秘密——比如你告诉它“不要透露窗口中的 X 信息”——这是一个非常难解决的问题。

<details>
<summary>Original English</summary>

**Host**: Um so we're like I think the ability for you to keep the something in the context window a secret like as in like you tell it do not reveal X thing in the context window. I think that's a very hard problem to solve.

</details>

**Aaron Levie**: 所以，如果任何东西进入了那个上下文窗口，理论上你就应该假设它会被“**提示词注入（prompt ejected）**”出来。我不确定我们目前有解决办法。

如果我知道你新 Agent 的邮箱地址，我给它发邮件。它是一个助理，但我可以通过社会工程学攻击它，比攻击人类容易 10 倍。你很难保证那个 Agent 在访问你的并购文档时还能保持安全。

<details>
<summary>Original English</summary>

**Aaron Levie**: Let's so then so then thus if anything can ever enter that context window because they have access to a resource then in theory you should assume it can be you know prompt ejected out of the context window. And I don't know that we know of a way to solve that at the moment. Like that's like and so so if I know your new agent's, you know, email address and I email it like it's an assistant, but like I can social engineer it 10 times easier than a human, like it'll be hard for you to pull off that that agent is now also has access to your like M&A documents and stuff.

</details>

### 标准、演进与算力经济学

**主持人**: 这不就是现在 AI 的现状吗？

<details>
<summary>Original English</summary>

**Host**: But isn't this like literally all of AI right now?

</details>

**Aaron Levie**: 哪一部分？

<details>
<summary>Original English</summary>

**Aaron Levie**: Which part?

</details>

**主持人**: 就是我们拥有这些共享系统，我们使用共享上下文的智能。

<details>
<summary>Original English</summary>

**Host**: I mean, the fact that we've got these shared systems that we use the intelligence for that have shared context.

</details>

**Aaron Levie**: 这就是为什么目前它们只能以“你本人”的身份工作。我们还不知道如何让它们不以“你本人”的身份工作。

解决这个问题的挑战在于，你可以诱骗 Agent 泄露信息。这就是为什么让它们拥有自己的资源、能够完全自主决策，目前还没能实现。

<details>
<summary>Original English</summary>

**Aaron Levie**: But this is why they're working as you effectively right now and we don't yet know how to make them not work as you. And then solving this problem though like the issue will be like you will just be able to trick the agent to reveal information. So then that's why like having them have access to their own resources where they can fully make their own decisions is not yet something that we've been able to pull off.

</details>

**主持人**: 解决你的问题有一个完美的例子：我们已经在**开源（open source）** 浪潮中经历过这一切。开源的模式是：东西都在那，你选着用。当时没人争论，因为当时圈子小得多。但很快大家都意识到了问题：如果你经营一家大公司，你不能让员工随便把开源源码复制到你的商用产品里。这里有许可问题、质量问题等等。于是所有这些规范都建立起来了。

我们现在的争论只是新技术发展过程中一个非常有趣的现代产物。在开源时代，我们是在一个这么大的会议室里讨论 Windows 或 Office 能用多少开源代码，互联网上没人知道我们在讨论这个。而现在这种关于“未来走向何方”的讨论是公开且宏大的，每个人都在试图冲向终点。

实际上需要发生的是：人们直接去动手构建。我们需要**标准**。

<details>
<summary>Original English</summary>

**Host**: But there's a perfect example for solving your problem which is we already lived through this with open source. The model for open source was it's all there and you just use it and you pick and choose. And then like nobody debated it because the world was much smaller then and we weren't all on X doing podcasts when this was all happening. But then quickly everybody realized all the problems you were just talking about. Like if you're running a big company, you can't have some person just go copy in a bunch of source code from open source into your commercial product like that. There was a whole licensing problem, a whole quality a whole bunch of stuff. And so all these norms got developed. The debate that we're happening right now is just is this really interesting modern artifact of how new technologies develop, which is this is all happening in real time. during open source like we met in a conference room this big and debated how much open source we could use in Windows or office right and nobody in the internet knew we were having this debate it was a very and it I think it's just so interesting that not just this the debate about specifics but this whole notion of where is this heading is happening in writ large and everybody is just trying to get to the end state. Like way way way more like in a sense more quickly than we can actually reach the end state. And so what really needs to happen is people just need to go build. We need standards.

</details>

**Aaron Levie**: 我认为我们对最终状态的直觉不同。

<details>
<summary>Original English</summary>

**Aaron Levie**: I think I think we've got different intuitions on the end state.

</details>

**主持人**: 有一种端到端的论点是，这些东西最终会收敛到和人类一样的**可靠性**，就像我们看待自动驾驶一样。在这种情况下，你会使用与保护人类相同的机制：考虑内部威胁、考虑人会被收买、考虑人会犯错，然后建立操作流程。这是一种直觉。

<details>
<summary>Original English</summary>

**Host**: One could make an end to end argument that these things actually converge on the same type of reliability as a human being, which is exactly how we view like self-driving. And in that case, you use the exact same mechanisms that we use to protect with human beings. like you consider insider threat, you consider the fact that people can be bought off, you consider the fact that people make mistakes and you build and that's operational processes. So, so one intuition is like that will be the end state.

</details>

**Aaron Levie**: 确实。但我要说的是我们现在的处境。我们正在进行战略对冲，因为我们要为 Agent 构建，我们喜欢让 **Open Claw** 拥有 Box 账号的想法。

我只是说目前在地面上，我们还不知道如何给它一个并购数据室并完全安全地运行。企业客户会先封闭一切，直到事情变得理智。与此同时，个人开发者和初创公司会移动得快得多，因为他们没有什么可以炸掉的。

<details>
<summary>Original English</summary>

**Aaron Levie**: Yeah. Well, the point is like I'm JUST SAYING I'M TALKING ABOUT WHERE we're at now. I actually I don't know that we disagree on the end state and by the way like strategically we're hedging because we're going to build Asian users and we're like I love the idea of open claw having a box account and it operates and it's like twice as many accounts. Exactly. THIS IS GREAT. I'm just saying on the ground right now, we don't yet know how to give it an M&A data room to fully securely be able to. But part of what's going to happen is you're we're going to go through this phase where like the enterprise customers are just going to like close everything off until there's some sense of sanity in all of this and then but in the meantime the individual and specifically the developers have such a big—the startups will start to move much much faster than enterprises because they just don't have any of these problems.

</details>

### 计算预算：下一场疯狂的对话

**主持人**: 这就是为什么 AI 能力的扩散会比硅谷预想的长。因为初创公司可以从零开始，没有任何风险。但如果你去摩根大通，问他们如何设置 **Nano Claw** 来自动化业务，那之间会有一个巨大的代差。

目前 SaaS 厂商正在经历“SaaS 末日”般的混乱，因为他们卖的其实是智能和领域专长。而 Agent 只想买数据，它们想要无限的数据访问权限，但这从未是 SaaS 厂商的商业模式。

<details>
<summary>Original English</summary>

**Host**: Which is why the diffusion of AI capability is going to take longer than people in Silicon Valley realize because what's happening is like we see startups that can start from the ground up without any of the risks that we're talking about because they have nothing to blow up and so we look at that as the trajectory that we're on and then you go to like JP Morgan and you're like how are you going to set up NanoClaw to actually automate your business anytime soon and it's like oh okay there's going to be like a little bit of a gap there. The current SAS vendors who are all struggling in this SAS apocalypse weirdness, they don't really sell the line of business data they actually sell this intelligence and domain expertise in this whole system and the agent side of things wants to only buy the data now and they only want to license the data and they want to have unlimited access to the data but they've actually never really enabled that.

</details>

**Aaron Levie**: 华尔街对这一切的**经济学**判断完全错了。他们用线性增长曲线来看待收入，试图证明 GPU 和 **Token（代币）** 的支出是合理的，就好像我们还处在旧世界。这就像 PC 刚出现时，人们认为 PC 市场是有限的，因为他们只把算力消耗看作有限的东西。

云服务刚出现时也一样，人们认为云只是把每年 6 万台服务器业务搬到别人的数据中心，然后平分价格。没人想到人们会消耗一千倍的资源。华尔街这种“固定收入蛋糕”的**零和思维**简直让我发狂。

<details>
<summary>Original English</summary>

**Aaron Levie**: Wall Street's all wrong about the economics and the problem and all that stuff. They're viewing the world of revenue as sort of this linear step literally linear growth curve and trying to justify all the expense when people are going to create like this was the problem with PCs. People viewed PCs as a finite market because they just viewed the consumption of MIPS as some finite thing and they didn't think what would happen if we put all those MIPs on every desktop. And the same thing happened with the cloud which was people looked at the cloud and they said, "Oh, we're going to take all of the the server business," which was like 60,000 units a year, and we're just going to move it to someone else's data center, right? And nobody went, "Oh, people are going to use a thousand times as much resource." And that's exactly I mean that's the thing that it just drives me absolutely bonkers that the Wall Street models have this fixed revenue pie—zero sum thinking.

</details>

**主持人**: 让我给你举个例子。我做投资 10 年了，投资组合里有 240 家公司。在过去的六个月里，每一个基础设施公司的业务都呈**渐近线式增长（asymptotic）**。为什么？因为现在编写的软件比以往任何时候都多。有了更多的软件，有了更多的 Agent，算力资源的消耗就会大幅增加。当每个人的手机都成为 AI 的巨大消费者时，消耗量会增加十亿倍。

<details>
<summary>Original English</summary>

**Host**: Let me give you an example of this. I've been in for investing for 10 years now I probably have a portfolio of 240 companies. Every single one of them has gone asymptotic in the six months and you're like, "Okay, why is this?" It just turns out there's so much more software being written now than ever has been before. And so with more software, with more agents, there's going to be a lot more consumption of computer resources. So once everybody's phone and on device is consuming AI, the amount of it is going to go up by a billion.

</details>

**Aaron Levie**: 未来几年，**工程计算预算**的讨论将是最疯狂的。你该把多少工程支出分配给 Token？根据推特上的说法，可能是 1%，也可能是 100%。

CFO 们必须知道答案。虽然他们总是想知道那些没有答案的事情。如果计算成本是你工程团队成本的两倍，那会吞掉你所有的 **EPS（每股收益）**。

<details>
<summary>Original English</summary>

**Aaron Levie**: The engineering compute budget conversation to me is going to be just like the most wild one in the next couple years. It's just like how much should you allocate of your engineering expense to tokens. And what CFOs have to literally they actually have to know the answer to. I understand they have to know but CFOs always want to know the answers to things that don't have answers. R&D is somewhere between 14 to 30% of revenue of any public technology company. The difference between compute being 2x the cost of your engineering team or 3% more is all your EPS.

</details>

**主持人**: 我完全愿意为了这个高度牺牲掉几个 CFO。

<details>
<summary>Original English</summary>

**Host**: I'm perfectly willing to sacrifice a few CFOs at the altit of this.

</details>

**Aaron Levie**: 这就是好片段。但原因是我们正试图预测我们现在根本不知道的事情。这在互联网带宽、真空管、晶体管、程序员身上都发生过。曾几何时，人们认为程序员会吞噬每家公司。

但我们从未有过这样一个节点：组织中的每个终端用户都有**完全弹性**的能力，去代表他们启动资源。

<details>
<summary>Original English</summary>

**Aaron Levie**: I want that. That's a good clip by the way. But the reason is because again this is trying to know what we just don't know right now. And this has happened with internet bandwidth. It happened with vacuum tubes. It happened with transistors. It has happened with every technology. There was a time when programmers were going to swallow every company. But I don't think we've ever had a point where every end user in an organization has sort of a completely elastic ability to spin up a resource on their behalf.

</details>

### 最终的晶体管时刻

**主持人**: 随着时间的推移，这种预算焦虑会消失。你必须做贝尼奥夫（Benioff）式的计算：如果你每年付给一名企业销售人员 100 万美元，你必须问他的工具值多少钱。如果你付给工程师 X 美元，那么他们的工具绝对值得投入。

大数法则会解决这个问题。最终会有足够的工程师，使用这么多算力，这会变成常态。我们只是处于过渡期，两年前大家还以为 AI 只是个聊天机器人，结果他们错了。

<details>
<summary>Original English</summary>

**Host**: This is all going to go away. There's absolutely no doubt that this just goes away. And the biggest reason it does is because you you have to do the Benioff kind of math which is if you're paying an enterprise salesperson a million dollars a year you have to ask how much is their tool worth. And if you're paying an engineer X dollars a year well at some point their tooling is worth—it's absolutely worth it. I think law of large numbers solves this because eventually you have enough engineers, they're using this much compute, but like we're in a transition phase where like most people thought, the two-year ago level of spend on AI, which is a chatbot. But they were wrong.

</details>

**Aaron Levie**: 就像你嘲笑的真空管。曾几何时，人们认为整个达科他州都会被真空管仓库覆盖，人们得穿着旱冰鞋在过道里穿梭更换真空管，才能打赢二战。然后有人发明了**晶体管**。

我们在这一切中也会迎来**晶体管时刻**。可能是供应量的增加，也可能是算法的根本性变革，或者是硬件的改变。目前每个人都盯着 Token 看，这很奇怪，就像当年 IBM 盯着 MIPS（每秒百万条指令）看一样。直到有一天，IBM 意识到他们每年卖出更多的 MIPS，但单价却更低。他们在一条下降曲线上，因为制造 MIPS 的速度比收钱的速度还快。

这种情况绝对会再次发生，我保证。

<details>
<summary>Original English</summary>

**Aaron Levie**: Like the vacuum tube thing you made fun of. But there was a time when they thought that all of the Dakotas would be covered in vacuum tube warehouses and people on roller skates would be running up and down the aisles replacing vacuum tubes just so we could fight World War II. And then someone said hey how about a transistor. And we are going to have a transistor moment with all of this. It might just be more supply, but it also might be an actual algorithmic fundamental change. It's just this I think it's particularly weird that everybody has just gotten to token. which is the same thing that happened with IBM and mainframes. People were on MIPS and then one day the reality was IBM was selling more MIPS for fewer dollars every year. And they were still pricing their mainframes by MIPS until it got pointed out to them that they were on a decreasing curve because they were making MIPS faster than they can charge for. And that's what's going to happen guaranteed.

</details>

**主持人**: 太棒了。听起来你很清楚自己在说什么。

<details>
<summary>Original English</summary>

**Host**: Love it. That was great. sound like it sounds really great to sound like I know what I'm making.

</details>

**Aaron Levie**: 保证成真。我其实真的相信。

<details>
<summary>Original English</summary>

**Aaron Levie**: Guaranteed. I actually probably believe it.

</details>