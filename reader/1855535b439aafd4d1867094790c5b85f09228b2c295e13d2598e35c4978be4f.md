---
author: Latent Space
date: '2026-04-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ATt7QJgt-2k
speaker: Latent Space
tags:
  - agent-orchestration
  - software-factory
  - llm-evals
  - mcp-protocol
  - product-strategy
title: Notion 的 AI 进化论：从自定义 Agent 到软件工厂的深度对谈
summary: Notion 联合创始人 Simon Last 与工程负责人 Sarah Sachs 深度解析 Notion 的 AI 战略。对谈涵盖了从 2022 年至今的五次架构重构、自定义 Agent 的设计哲学、“软件工厂”的自动化愿景，以及如何在模型快速迭代中保持工程敏捷性。他们强调了 Evals（评估框架）作为 AI 核心竞争力的重要性，并探讨了 AI 如何改变软件工程师的定义。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Simon Last
  - Sarah Sachs
companies_orgs:
  - Notion
  - OpenAI
  - Anthropic
products_models:
  - Custom Agents
  - Claude 3.5 Sonnet
  - GPT-4o
  - MCP
media_books: []
status: evergreen
---
### 开场：对 CLI 与 MCP 的看好

**Simon Last**: 广义上讲，我非常看好 **CLI（命令行界面）**。在特定环境下，我也依然看好 **MCP（模型上下文协议）**。我认为特别是当你想要一种轻量级的狭义 **Agent** 时，MCP 非常棒。

<details>
<summary>Original English</summary>

**Simon Last**: Broadly speaking, I'm really bullish on CLIs. I'm still bullish on MCPs in a certain environment. I think in particular, MCP is really great for when you want sort of like a narrow lightweight agent.

</details>

**Sarah Sachs**: 我认为确实有很多使用场景是你不需要一个带有计算运行时的完整编程 Agent 的，而且你也希望权限管理更严密。**MCP** 本质上拥有非常强大的权限模型，你唯一能做的就是调用工具。MCP 就是那种简单有效的东西，而且表现相当不错。**Notion** 致力于成为人们进行企业工作的最佳**记录系统（System of Record）**。因此，只要其他人还在使用 MCP，我们就会一直支持它。无论我们的观点如何，我们都在 MCP 上投入了大量精力，并正在组建一支非常棒的团队。

<details>
<summary>Original English</summary>

**Sarah Sachs**: I think there's definitely a lot of use cases where you don't want like a full coding agent with a compute runtime and also you want it to be like more tightly permissioned. MCP inherently has a really strong permission model. Like all you can do is call the tools. MCP is just like the dumb simple thing that works and it's pretty good. Notion is dedicated to being the best system of record for where people do their enterprise work. So we will always support our MCP in so far as other people are using MCPs, right? So regardless of our perspective, we've put a lot of effort into our MCP and we have a fantastic team that we're building.

</details>

### 欢迎来到 Latent Space 播客

**Alessio**: 在开始今天的节目之前，我有一条简短的消息要告诉听众。谢谢大家。如果你们没有选择点击并收听我们的内容，我们就无法为你们带来你们显然想要的 **AI 工程**、科学和娱乐内容。几乎每天都有赞助商联系我们，但幸运的是，你们中足够多的人订阅了我们，让我们在没有广告的情况下保持可持续发展，我们也希望保持这种状态。但我只求大家帮一个小忙：你能做的最强大且完全免费的事情就是点击那个**订阅按钮**。这是我唯一对你们的要求，这对我和我努力工作的团队来说意味着一切。如果你这么做了，我保证我们将永远努力把节目做得更好。现在，让我们开始吧。嘿，大家好，欢迎来到 **Latent Space** 播客。我是 **Kernel Labs** 的创始人 Alessio，和我在一起的是 *Latent Space* 的编辑 **swyx**。

<details>
<summary>Original English</summary>

**Alessio**: Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis. But fortunately, enough of you actually subscribe to us to keep all this sustainable without ads and we want to keep it way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you. And it means absolutely everything to me and my team that works so hard to bring the Latent Space to you each and every week. If you do it, I promise you we'll never stop working to make the show even better. Now, let's get into it. Hey everyone, welcome to the Latent Space podcast. This is Alessio, founder of Kernel Labs, and I'm joined by swyx, editor of Latent Space.

</details>

**swyx**: 大家好，大家好。我们回到了 Alessio 为我们搭建的美丽工作室，今天和我们在一起的是来自 **Notion** 的 Simon 和 Sarah。欢迎你们。

<details>
<summary>Original English</summary>

**swyx**: Hello. Hello. We're back in the beautiful studio that Alessio has set up for us with Simon and Sarah from Notion. Welcome.

</details>

**Simon & Sarah**: 谢谢邀请。

<details>
<summary>Original English</summary>

**Simon & Sarah**: Thanks for having us.

</details>

### 自定义 Agent 的漫长研发路

**swyx**: 祝贺最近的发布。**自定义 Agent（Custom Agents）**，它终于来了。感觉如何？

<details>
<summary>Original English</summary>

**swyx**: congrats on the launch recently. Custom agents. Finally, it's here. How's it feel?

</details>

**Sarah Sachs**: 我们发布东西比较慢。它在 **Alpha** 阶段已经有一段时间了。当它处于 Alpha 阶段时，有一组人负责确保它达到生产标准，而另一组人已经在开发下一个产品了。所以有时这些发布会有种“延迟的满足感”。提醒自己曾经付出的努力挺不错的，因为我们习惯于超前两三个里程碑，因为你必须如此，不能自满。但看到人们理解了这东西为何有用，感觉非常好。现在的 AI 工具用户教育比两三年前容易多了，大家能理解了。这次发布在免费试用和转化率方面是我们最成功的。不过，还有很多东西要建。

<details>
<summary>Original English</summary>

**Sarah Sachs**: We ship things slowly. So, it had been in alpha for a little bit and at the point at which is it's in alpha. Um, there's a group of people that are making sure it's ready for prod and then there's a group of people working on the next thing. So, sometimes some of these launches are a bit delayed satisfaction. So, it's quite nice to remind yourself all the work you did because we do have a habit of like being two or three milestones ahead just because you have to be, you know, you can't get complacent. Um, but it's been great that people understood how this is helpful. And I think that's just easier in general building AI tools today than it was two, three years ago. People kind of get it. And so that user education um there's just it was our most successful launch in terms of free trials and converting people and things like that. It was really successful. So yeah, but there's a lot to build.

</details>

**Simon Last**: 这对我来说绝对超级兴奋，因为这大概是我们第四五次重构它了。

<details>
<summary>Original English</summary>

**Simon Last**: it was definitely super exciting for me because it's probably the fourth or fifth time that we rebuilt that.

</details>

**swyx**: 你们从 2022 年就开始做这个了对吧？

<details>
<summary>Original English</summary>

**swyx**: And I mean, you've been building this since like 2022.

</details>

**Simon Last**: 是的。就在 2022 年底我们获得 **GPT-4** 访问权限时，我们最早的想法之一就是：“好，让我们做一个 **Assistant（助手）**。”当时还没有 **Agent** 这个词。我们想给它 Notion 的所有工具权限，让它在后台帮我们干活。然后我们尝试了很多次，但当时时机太早了。

<details>
<summary>Original English</summary>

**Simon Last**: Yeah. I mean, like it was even right when we got access to like GPT-4 in late 2022. One of the first ideas we had is like, oh, okay, let's make an agent that we use the word assistant at the time. There wasn't really the word the word word agent yet, but oh, we'll give it access to all the tools that notion can do and then it will run in the background like like do work for us. And then we just tried that many times and it just was too early.

</details>

### 为何“时机太早”？早期的工程阵痛

**swyx**: 我必须让你详细说说。什么叫“太早”？当时什么行不通？

<details>
<summary>Original English</summary>

**swyx**: I need to force you to like double click on that. What is too early? What didn't work?

</details>

**Sarah Sachs**: 在 **Function Calling（函数调用）** 出现之前，我们尝试与顶级实验室以及 **Fireworks** 合作，针对 Notion 的函数进行微调。那是我刚加入的时候，加入是因为他们需要一个经理，好让 Simon 能去度假。

<details>
<summary>Original English</summary>

**Sarah Sachs**: We were find like before function calling came out, we were trying to fine-tune with the Frontier Labs and with Fireworks like a function calling model on notion functions. This is right when I joined. I joined because um we needed a manager. Simon was needed to be able to go on vacation. So uh that's that's around when I joined. So you can speak much more to it.

</details>

**Simon Last**: 是的，我们在不同时期与 **Anthropic** 和 **OpenAI** 都建立了合作伙伴关系。最初尝试时甚至还没有“工具”的概念。我们设计了自己的工具调用框架，然后尝试微调模型让它进行多轮对话。但开箱即用的效果并不好，模型太笨了，**上下文长度（Context Length）**也太短了。我们在这个问题上碰壁了很久。虽然总能看到成功的曙光，但从未觉得它足够鲁棒，能成为一个有用且令人愉悦的产品。直到去年初 **Claude 3.5**（注：此处原文可能指 Claude 2 或 3 系列）发布，那是一个大的突破，我们开始开发去年发布的 Agent。自定义 Agent 也是类似的能力，只是花的时间更长，因为我们希望在它后台运行时把可靠性提升到更高的水平。

<details>
<summary>Original English</summary>

**Simon Last**: Yeah, we did partnerships at both Anthropic and OpenAI at different times uh to try to at the time the I mean when we first tried there wasn't even a concept of like tools yet. We we sort of designed our own like like tool calling framework and then we tried to fine-tune the models to to use it over multiple turns. Um and because it it didn't work well out of the box I think. Yeah, the models are just too dumb and the context length was also way too short. Yeah. Um and yeah, we just kind of banged our head against it for a long time. Uh unfortunately, it was always like there was always like sort of glimmers that it was working, but um it never felt quite robust enough to be like a useful, delightful thing. Um until I would say uh the big unlock was probably like Sonnet 3.5 early last year and that's when we started working on our agent, which we shipped last year. Um and then and then uh uh custom agents kind of a similar capability and that that one just took longer because we we just wanted to get the reliability up a lot higher because it's actually running in the background

</details>

**Sarah Sachs**: 还有权限管理的产品界面。你需要理解这个自定义 Agent 被分享到了哪个 Slack 频道，它有权访问哪些文档，管理员如何理解这些权限分配……这些产品设计也经历了多次推倒重来。

<details>
<summary>Original English</summary>

**Sarah Sachs**: and the product interface of like permissions and understanding you know this custom agent is shared in a slack channel with X group of people and has access to documents that are surfaced to Y group of people and the intersect of X versus Y might not be whole and so how do you build the product around making sure administrators understand that permissioning took multiple swings.

</details>

### “顺流而下”：AI 时代的产品哲学

**swyx**: 归根结底都是 **RBAC（基于角色的访问控制）**。我很好奇，当模型表现不佳时，你们如何制定产品路线图？既要期待模型会以合理的速度变强，又要服务好现有的庞大用户群。

<details>
<summary>Original English</summary>

**swyx**: Everything is RBAC at the end of the day. Yeah. I'm curious like when the models are not working, how do you inform the product road map of like, okay, we should probably build expecting the models to be better at some reasonable pace, but at the same time, we need to, you know, you had a lot of customers in 2022. It's not like you were a new company with like no user base.

</details>

**Simon Last**: 这是一个平衡。你既想保持 **AGI** 导向，前瞻性地为未来的趋势构建；又想发布有用的东西。所以我们采用“组合拳”方式：维护已发布的功能，优化表现良好且即将成熟的功能，同时保留几个“疯狂”的项目。

<details>
<summary>Original English</summary>

**Simon Last**: Yeah. I mean, I think there's always the balance of, you know, like you want to be AGI pled and thinking ahead and building for where things are going. Uh but also you want to be like shipping useful things and so we always try to like like keep a balance there. You know, we we try to take like a portfolio approach. You know, we're always working on multiple projects and and we're always trying to work on, you know, maintaining things where they've already shipped like like shipping new things that are like eminently working well and make them really good and and then we want to always have a few projects that are a little bit crazy.

</details>

**Sarah Sachs**: 过去三年半的尝试中，什么改变了？大多数人会说模型推理能力变强了。这只是部分原因。我认为让 Notion 脱颖而出的是两项关键技能：一是**不要逆流而上**。你要快速意识到你是在挑战模型能力的极限，还是因为没提供正确的信息或基建没搞好。这本身就是一种直觉技能。二是要看清“河水流向何方”，即使现在效果还不完美，也要开始构建产品，等能力到位时我们已经准备好了。有时这看起来很反直觉，比如在工具调用模型还不存在时就尝试微调它。诀窍在于不要死磕太久，但要意识到那里有潜力。我们在视频会议纪要功能出来之前，也尝试过好几个版本的语音转文字。

<details>
<summary>Original English</summary>

**Sarah Sachs**: Why what what changed over the three and a half years of trying it, right? Because most people always say like it didn't work yet, then reasoning models came, then it worked. I was like, okay, let's go a little bit. I mean, that's part of it, but I think the other part of it that I actually think is really what will set notion apart for every new capability is we have like two skills that are crucial when it comes to frontier capabilities. One is not letting yourself swim upstream. So like quickly realizing if you're just pressing against model capabilities versus not exposing the model to the right information, not having the right infrastructure set up. That in of itself is a skill of intuition. And then the second is to see okay you're not swimming upstream. Which direction is the river flowing? And what is like how do we think ahead about the product and start building it even if it's not great yet so that when it is there we're ready for it, right? And like those can sometimes feel like counterintuitive things like we can be trying to fine-tune a tool calling model when they don't exist yet. And the the trick is to not do that for too long, but realize that there was something there. And we've had a lot of things which like um were just like not swimming in the right direction with the streams. I think we had multiple versions of transcription before we got meeting notes, right?

</details>

### “软件工厂”与未来的工程师

**swyx**: 18 个月后，人们会觉得哪些东西是理所当然的？

<details>
<summary>Original English</summary>

**swyx**: I'm curious what are things today that maybe in 18 months people will like, "Oh, obviously this was gonna work."

</details>

**Simon Last**: 有一个方向变得越来越清晰，那就是**编程 Agent**。一切皆是编程 Agent。最令人兴奋的是，你的 Agent 可以自我引导生成软件和能力，并进行调试和维护。我们正在思考的另一个类别是**“软件工厂”（Software Factory）**。这个词很多人都在用，基本意味着构建一个尽可能自动化的工作流，用于开发、调试、合并、评审和维护代码库和服务，内部有一群 Agent 协同工作。

<details>
<summary>Original English</summary>

**Simon Last**: I think one thing that's becoming more clear is I think like like coding agents are the kernel DGI sort of everything is a coding agent. I think that's sort of one one direction. Um, and then yeah, the exciting thing about that is sort of your agent can sort of bootstrap its own software and capabilities and actually debug and maintain them. And so, yeah, we're we're we're thinking a lot about that. And then, yeah, like like another category of things that I'm really excited about is like uh we call the software factory. Lots of people are using this this this sort of word. Um, basically just means can you create sort of like a as automated as possible a workflow for developing, debugging, merging, reviewing, and maintaining a codebase and a service where there's a bunch of agents working together inside and like like how does that work?

</details>

**swyx**: 会不会有一天 Notion 就不需要软件工程师了？

<details>
<summary>Original English</summary>

**swyx**: Is there a day there are no software engineers at Notion?

</details>

**Simon Last**: 这取决于你如何定义“软件工程师”。我们正处于一个连续的光谱上。三年前人们手写所有代码，后来有了自动补全，再后来有了行级填充 Agent，现在我们进入了 Agent 执行长程任务的阶段，它们可以调试、修复、验证并提交 PR。人类的角色更多地转向**观察和维护外部系统**。这是一项艰巨的工程挑战，我们只是在不断提升抽象层级。

<details>
<summary>Original English</summary>

**Simon Last**: what does it mean to be a software engineer? I mean, I think the way things are going is like we're on some continuum where if if you look back 3 years ago, humans were typing all the code and then we had autocomplete. You're typing a little less of the code. we had sort of like filling agents filling lines and now we're getting into like agents doing longer range tasks where you can debug and implement a fix and then verify it works and you know get your get your PR even like like merge and deployed. I think we're sort of just moving up the abstraction ladder and then the human role becomes more about observing and maintaining the outer system. There's a stream of agents flowing through like merging PRs what's going off the rails like what do I need to approve? Is there like a learning or memory mechanism that that works? So it's kind of a hard engineering problem. There's a, you know, there's a lot to do there. I think we're just sort of moving up the stack.

</details>

**Sarah Sachs**: 去年夏天，Notion 的每位工程师都经历了一场“身份危机”。一位工程负责人说，这就像每个管理者都会经历的转变：突然意识到你写代码的能力不再那么重要，取而代之的是**委派能力**和上下文切换能力。虽然这更像管理，但也有一个关键区别——它依然是极其深度的技术活。管理人类是模糊的，你不能把人类团队当作一个严密的系统来处理；但对于一组 Agent，你可以。这实际上是一个非常有趣的技术设计问题。

<details>
<summary>Original English</summary>

**Sarah Sachs**: I think every software engineer at Notion this summer went through like this um shear um one of our engineering leads at the company called it like every software engineer is going through the the identity crisis that every manager goes through where all of a sudden they realize their ability to write code is less important than their ability to delegate and context switch and I think that that is a transition out of being a software engineer but yeah there's a critical difference to being a manager which is that like It is actually very deeply technical. The problem of you know humans are very like like like fuzzy and you you can't like treat a team of humans like a like a rigorous system where like you know PRs like like flow through and can be in like a blocked status and then what happens when they're blocked right with a set of agents you actually can do that and and I think it's actually there's a lot of interesting technical rigor that that goes into that. It's a it's a technical design problem ultimately.

</details>

### Notion 不是“套壳”，是“数据狗”

**Sarah Sachs**: 我经常向面试者展示“Agent Lab”的观点。现在越来越多的人明白 Notion 不仅仅是一个“套壳”。起初我们构建的某些功能确实是套壳，但这并不能驱动收入，也不是用户真正需要的。Notion 之于大模型，就像 **Datadog** 之于 AWS。没有云存储，Datadog 就无法存在。AWS 也有 CloudWatch 这种产品，但 Datadog 是理解人们如何通过指标进行**可观测性分析**的专家。而我们是理解人们如何进行**协作**的专家。

<details>
<summary>Original English</summary>

**Sarah Sachs**: I show that thesis to so many candidates. Um, and by the way, like in the beginning, parts of what we build are rappers on functionality that works well, but that's not really the most um I would say that's not the product that that drives revenue and that's not necessarily always what users need. The analogy that I've been coming back to is data dog in AWS. Yeah. So, uh data dog could not exist without cloud storage, right? that it's kind of fundamental that that works. Um, and AWS has like a cloudatch product, but Data Dog is an expert on understanding how people want observability on the products they launch. And we're experts on understanding how people want to collaborate and that's really where our expertise lies.

</details>

**Simon Last**: Notion 一直非常横向。我们的任务是平衡两个对立的力量：一是倾听客户想要我们构建什么，这是一个很宽泛的切片；二是思考如何将这些需求分解为优雅的**原语（Primitives）**。我们要保持系统整洁且易用。

<details>
<summary>Original English</summary>

**Simon Last**: notion has always been super horizontal and our our task has always been to sort of balance these two somewhat opposing forces of like we're listening to our customers and what they want us to build. It's a broad slice. And then also we're thinking about like okay, how do we decompose what they want into nice primitives that are that are really nice to use and will will get us like as much bang for the buck as possible and then you know maintain the whole system make it all like like super clean and nice to use.

</details>

### 极致的 Evals：Notion 的“最后大考”

**Sarah Sachs**: 我们在 **Evals（评估）** 和模型行为理解团队投入了大量人力。如果人们说 Evals 仅仅代表质量，那是不够的，这就像说测试不仅仅是单元测试一样。我们有相当于单元测试的回归测试，它们必须在 CI 中通过。还有产品级评估，比如某个用户旅程必须达到 80% 或 90% 的通过率才能发布。

<details>
<summary>Original English</summary>

**Sarah Sachs**: I think it's a real issue when people say evals and it's just like that's quality. That's like unit I mean it's like saying testing. It's not just unit tests, right? So, we have the equivalent of unit tests, regression tests, those live in CI. Those have to pass a certain percent you know within some stocastic error rate. Then we have as you're building a product eval of these aren't passing right now and this is launch quality. So we have a report card and we need to on these categories you know be at 80 or 90% of all of these user journeys to launch

</details>

**Sarah Sachs**: 最有趣的是我们所谓的“前沿评估”或“天花板评估”，我们主动追求只有 30% 的通过率。过去两三个月里，我们与 Anthropic 和 OpenAI 合作，因为我们的评估已经饱和了，除了“没有变差”之外无法提供更多见解。这不仅对合作伙伴没帮助，对我们看清未来方向也没帮助。我们花了很多时间思考 **“Notion 的最后大考”（Notion's Last Exam）** 长什么样。我们有专门的数据科学家和**模型行为工程师（MBE）**全职负责这些只有 30% 通过率的评估。

<details>
<summary>Original English</summary>

**Sarah Sachs**: and then what we have what we call frontier or headroom eval where we actively want to be at 30% pass rate and that's actually been a effort that we took in partnership with enthropic and open AI in the past maybe two or 3 months because we actually hit a point where our evals were saturated and we weren't able to really give insightful feedback other than it wasn't worse and not only is that not helpful for our partners it's not helpful for us to understand where the stream is going. And so we spent a lot of time thinking about what notion's last exam looks like, right? Not just humanity's last exam, Notion's last exam. And um there's a lot of, you know, dreams about what that would look like. Notion's last exam is a big thing inside the company, and we have people full-time staffed to it exclusively. We have a data scientist, a model behavior engineer, and an full-time um evals engineer just dedicated to the evals that we pass 30% of the time.

</details>

**swyx**: 什么是 **MBE**？

<details>
<summary>Original English</summary>

**swyx**: What is an MBE?

</details>

**Sarah Sachs**: **模型行为工程师**。这个职位最初叫数据专员。一年半前，Simon 还在白板前教他们怎么用 GitHub。现在，他们不仅手动检查代码，主要工作是构建能为自己编写评估或 LLM 裁判的 Agent。这个角色混合了数据科学家、产品经理和提示词工程师。我们坚信这是一种独立的职业路径，你不需要工程背景也能胜任，我们欢迎这些“异类”。

<details>
<summary>Original English</summary>

**Sarah Sachs**: A model behavior engineer. Model behavior engineers started with a title data specialist before I joined when they were working with Simon on like uh Google Sheets and like Simon just needed someone to look through Google Sheets and say yes, no, this looks bad, this looks good. Right? And so we hired people with kind of diverse linguistics background. And over time we've built a whole team um with a manager who's now kind of reinventing what that role is with coding agents. So they used to be kind of manually inspecting code. Now they're primarily building agents that can write evals for themselves or LLM judges. moving forward it's this mix of like data scientist PM and prompt engineer because there's craft in understanding like even like what models can and can't do things how do we define like that headroom how do we define like what a good journey is um is this model better or not why is this failing there's some qualitative work, but then there's also like a lot of instinct and taste to it and that's not necessarily software engineering and so we have like very firm conviction and we have had for a number of years now that that is its own career path and we have always welcomed the misfits so to speak. So we really firmly believe that you don't need an engineering background to be the best at this job and that's what's quite unique about this particular role.

</details>

### 构建“软件工厂”：Notion 的宏大远景

**swyx**: 你们正在建造的“软件工厂”是什么样子的？

<details>
<summary>Original English</summary>

**swyx**: What is the design of the software factory that you're building?

</details>

**Simon Last**: 我们在尝试很多不同的思路。终极目标是设计一个需要最少人为干预，同时能维持你所关心的不变性的系统。这里有几个关键点：一是**规范层（Specification Layer）**，你可以直接提交 Markdown 文件。Notion 就是规范天然的家。它可以是一个页面数据库，既可读又可视。另一个关键组件是**自验证循环**。你需要非常强大的测试层。当出现 Bug 时，它如何流入系统？是否有子 Agent 负责处理？它如何生成 PR？PR 如何被评审和合并？这就是流程的流向。

<details>
<summary>Original English</summary>

**Simon Last**: Yeah. I mean I think we're trying a lot of different things. I mean ultimately you want to design a system that requires as little human intervention as possible but like still maintaining the invariance that that you care about. So yeah, we're exploring a lot of different ideas there. I mean I think I can talk about like a few things I think are important there. Like one thing I think is really important is um having some kind of like specification layer. You can just commit markdown files. That works pretty well. It's nice to be notion man. I'm just saying like the spec like the natural home for specs is notion. It can be a database of pages. Yeah. I mean it needs to be something that is you know human readable and and viewable and I think that's pretty key. Another really key component is like the the self-verification loop. You need a really really good testing layers basically. And that's a really deep uh problem, but but getting that right, you know, and then and then it's kind of like the workflow of like what happens when there's a bug, how does it flow into the system? Like is it like a sub agent working on it? How does it make a PR and how does that get reviewed and merge and then you know, so there's like the the flow or process.

</details>

### 管理 Agent：从 70 条通知到 5 条

**swyx**: 你提到人们可以组合 Agent。

<details>
<summary>Original English</summary>

**swyx**: And I'm curious how you think about composibility of these things.

</details>

**Simon Last**: 有两种组合方式。一种是通过数据原语：一个 Agent 向数据库写入，另一个 Agent 遍历数据库。这种异步方式非常有效。另一种是耦合方式，我们在 Agent 设置中允许它调用任何其他 Agent。前几天我帮公司内部的一位同事解决了一个问题：他为市场团队构建了 30 多个自定义 Agent，处理各种任务。但他每天会收到 70 多条“Agent 被卡住”的通知。显而易见的解决方案是做一个**“管理者 Agent”（Manager Agent）**。它作为这 30 个 Agent 之间的抽象层，负责观察和监督。现在他每天只需要处理 5 条通知，管理者 Agent 会帮他调试和修复大部分问题。

<details>
<summary>Original English</summary>

**Simon Last**: Yeah. So I mean there's there's two ways you can compose. One way is by using like the data primitives. So you can, you know, you could give you have one agent uh be writing to the database and there's another agent that's walking the database. So that's that's one way that they can coordinate that's like a little bit more decoupled and works really well. Or you you can couple them. So I I think it's actually not released yet releasing it like next week is uh in the settings for an agent you can give access to invoke any other agent. I just I I helped uh someone internally the other day they had they had built like over 30 custom agents for for our go to market team doing all kinds of different things. Literally over 30 of them. And and now I'm getting 70 over 70 notifications per day with just the agents are blocked on various things. Uh and then I was like, "Oh, okay, cool." You know, the obvious thing to do there is to make a manager agent, right? that's going to sort of be another abstraction layer in between your your 30 agents. Uh so yeah, we we set them up with like a manager agent and then has access to invoke all the other agents and it's sort of like like watching and observing them and then it sort of yeah just creates a layer of abstraction. So instead of 70 notifications per day, it's like like five and then and then the manager agent can help like debug and fix any any problems with the

</details>

### 定价与价值：让客户花得值

**swyx**: 你们用 **Credits（点数）** 代替了直接的 Token 计费。

<details>
<summary>Original English</summary>

**swyx**: How do you design pricing, value based pricing based on the task and things like that?

</details>

**Sarah Sachs**: 我们必须建立一个高于 Token 的抽象。因为我们的微调开源模型运行在 GPU 上，网页搜索的定价也不同，如果托管沙盒，成本又不一样。此外，服务等级也不同。我们从一开始就致力于确保客户得到公平的交易。我们不想仅仅靠这些点数赚大钱，而是让客户为合理的内容付费。同时，我们销售的是企业级 SaaS，所以点数包可以享受折扣，这有助于销售流程。

<details>
<summary>Original English</summary>

**Sarah Sachs**: So, they are um the credits and payment structures associated with the token usage. reason that we had to make it not just throughput of tokens is that it's not always priced that way. Like our um fine-tuned open source models are served on GPUs, web search is priced differently. You know, if we were to host sandboxes, those are priced differently. So, we had to think of an abstraction above tokens. And it's also not just tokens, it's the token model um and serving tier trade-off, right? we wanted to um from the get-go commit to making sure that customers were getting the fair deal, not necessarily that we were making a ton of money off of it, but that customers were paying for what was reasonable. And also, you know, we're selling enterprise SAS, so if we sell credit packs, then you get discounts if you're an enterprise and you buy a certain amount of credit packs and things like that. So it also just helped the sales motion um work a little bit easier.

</details>

**Sarah Sachs**: 我们不希望这变成一种浪费。如果我们能让 Agent 确定性地执行代码调用 CLI，那是一次性成本；而如果让模型一遍又一遍地与 MCP 集成，不断支付重复的 Token 费用，那就既不经济也不稳定。我们提供“自动（Auto）”模型选择，它不是最廉价笨拙的模型，而是最适合当前任务的模型。就像 Robo-advisor（机器人投顾）一样，我们在帮用户做最优选。

<details>
<summary>Original English</summary>

**Sarah Sachs**: particularly because our custom agents are using usage based pricing. We think of pricing as like the barrier of entry for use of our product and we're quite committed to making sure that it's not wasteful. Um not just because it's a bad deal for our customers, but it's also bad business. if we can have our agents properly execute code that calls on CLI deterministically, it's a one-time cost, right? versus constantly having a language model integrate with an MCP over and over and over and paying those like repeated token fees. what's actually been hard for us is to convince people that auto is not just our cheapest, dumbest model, but actually the model that's best for the task that you want to do.

</details>

### 结语：协作才是核心

**swyx**: 这个深度交流太棒了。你们两人的配合非常默契。

<details>
<summary>Original English</summary>

**swyx**: Cool. Uh well, thank you so much. This is such a great deep dive. Actually, the chemistry between you two is amazing.

</details>

**Sarah Sachs**: 记得有一次你强烈提醒我：我们的工作不是建立最好的 Agent 实验平台，而是建立最好的**协作场所**。我们的工作不是造最好的穿戴设备去捕捉会议纪要，而是提供一个让会议纪要发挥最大价值的地方。

<details>
<summary>Original English</summary>

**Sarah Sachs**: That kind of reminds me, I remember once you very strongly reminded me, our job is to not make the best harness for agentic work. Our job is to be the best place where people collaborate. It's like our job isn't to build the best wearable to capture meeting notes. Our job is to build the best place where meeting notes live, right?

</details>

**Simon Last**: 是的，让其他人把数据接入我们，这完全没问题。

<details>
<summary>Original English</summary>

**Simon Last**: Yeah. So, basically, you're saying everyone else can just pipe to you and that's fine, right? Yeah.

</details>

**swyx**: 谢谢你们。

<details>
<summary>Original English</summary>

**swyx**: Thank you.

</details>