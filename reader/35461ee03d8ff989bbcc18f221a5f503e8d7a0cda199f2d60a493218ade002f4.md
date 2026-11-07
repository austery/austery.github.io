---
author: AI Engineer
date: '2026-11-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5SRjPT2Eo7A
speaker: AI Engineer
tags:
  - continual-learning
  - model-training
  - enterprise-ai
  - ai-agent
title: 企业为何应当训练专属 AI 模型：沉淀隐性知识与持续学习的路径
summary: Prime Intellect 的 Will Brown 探讨了企业级 AI 原生化的演进路径。他指出当前智能体仅依赖上下文学习和规则配置存在成本高与难以内化隐性知识的问题，主张企业应利用自身数据和部署轨迹将工作流与偏好直接训练进模型权重，通过评估体系、决策模型与夜间微调闭环实现持续学习与能力复利。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Will Brown
companies_orgs:
  - Prime Intellect
  - OpenAI
  - Paper Instruments
products_models: []
media_books: []
status: evergreen
---
### 迈向 AI 原生企业的新阶段
大家好，近来如何？我是 Will Brown，在 Prime Intellect 负责应用研究。希望大家在 AI 工程师大会上都过得愉快。这向来是我最喜欢的会议之一。看到每个人正在构建和从事的项目总是让人感觉非常酷，我觉得这是一个大家探讨未来样貌、开始洞察行业趋势、见证进展以及摸索哪些行得通、哪些行不通的平台。这也是我今天演讲想要探讨的主题：从我们当下正在做的事情出发，接下来会走向何方？我们一直在投入的工作，以及正在展开并指向我们认为企业层面上未来 AI 发展方向的那些研究是什么？因为在过去的数月、数年里，我们在智能体（agents）、界面和机器人等方面见证了许多非常亮眼的进展。但我认为接下来总会有更多新的突破。一切都在飞速向前推进，去设想、推测并为接下来的发展制定规划，这是一个令人兴奋的时刻。

<details>
<summary>Original English</summary>
Hey, how's it going? I'm Will Brown. I uh lead applied research at Prime Intellect and uh hope you are all having a a great AI engineer conference. This is always one of my favorites. Uh, it's always just so cool to see what everyone's working on and building and I feel like it is a place where people get to talk about what the future looks like and like start seeing the trends in the industry and seeing the progress and what works and what doesn't. Um, and that's kind of the theme I want to think about for this talk today is like what comes next from what we're doing right now and what are some of the things that we've been working on and also just been seeing and research that's unfolding that kind of points at what we think the future of AI might look like um at the organization level. uh because we've seen a lot of very cool progress in uh agents and interfaces and bots and things like that over the past uh several months, years. Uh but I there's always like there's always more coming. Things are just moving so fast and I think it's a very exciting time to just imagine and speculate and plan for uh what comes next.
</details>

不知是否有人还记得，早在 ChatGPT 早期，OpenAI 曾梳理过他们对通往 AGI 道路上 AI 发展不同阶段的框架设想。我认为我们沿着这一路径推进的速度比我们预想的要快。记得 18 个月前，我在纽约的 AI 工程师大会上发表过一场演讲，当时我们迎来了推理模型（reasoners），聊天机器人已经出现了一段时间，推理模型属于新鲜事物，但那时我们还没有真正的智能体。而如今，我们已经相当迅速地跨越了智能体和创新者阶段。接下来的问题似乎变成了：在企业组织层面会发生什么？一个组织真正成为“AI 原生”意味着什么？这不仅是指像初创公司那样大量使用智能体并用 Claude Code 构建一切，而是在大型企业规模上意味着什么？未来那些将智能体深度整合到组织全生命周期中的公司会是什么样子的？以及在通往那一目标的道路上，我们需要构建什么？

<details>
<summary>Original English</summary>
Um, and so I don't know if any of you remember back in the early chatbt days, OpenAI had kind of spelled out their framing of like what are the different stages of AI progress on the road to AGI. Um, and I think we've moved along this faster than we thought we would. uh we like I remember 18 months ago I was uh here in New York at a engineer and giving a talk where we had gotten reasoners and chat bots had been around for a while and reasoners were like the new thing but we didn't really have agents yet. Um, and now we've climbed pretty quickly through uh agents and innovators. And the question next seems to be, okay, what happens for organizations? Like what does it mean for an organization to truly like be AI native, not just as like a a startup that uses a lot of agents and builds everything with cloud code, but like at the like large enterprise scale? um what do companies of the future look like that involve uh like deep integration of agents throughout the life cycle of the organization um and what do we need to build on the path there
</details>

### 开源模型与企业制度性知识的沉淀
先介绍一点关于 Prime 的背景情况：围绕模型的训练、部署和持续改进，尤其是针对开源模型和开源工具链，我们构建了许多不同的 AI 基础设施产品。我们涵盖了许多业务，大致等同于大型实验室内部所做的事项，这些构成了我们的产品。我们之所以做这些，是因为我们设想了一个似乎正迅速到来的未来：开源模型变得唾手可得，可以在组织自身的工作流、数据以及运行环境中进行训练和部署，并能随着组织的发展一同成长，从而在利用前沿实验室模型的同时，实现制度性知识以及由工作流、数据、人员和流程带来的制度性优势的持续复利。因此，本次演讲将讨论我们如何看待这一演进过程：在 AI 原生企业中，训练扮演着怎样的角色？它如何与前沿模型共存？以及我们认为哪种形态能真正为人们释放最大的价值，它的样貌究竟如何？

<details>
<summary>Original English</summary>
uh so a bit about prime just for some backdrop um we build a lot of different things around AI infrastructure for training deploying and continuously improving uh models and especially open source models uh and open source tooling and so we do a lot of things And like we roughly do the sorts of things that you would do inside of a big lab. And these are our products. And the reason we do this is because we are imagining a future that is coming pretty quickly it seems where open source models are readily available to train and deploy on your own workflows on your own data in your own harnesses and can be the sorts of things that organizations can have grow with them over time that allow compounding their institutional knowledge, their institutional advantage from their workflows, from their data, from their people and their processes uh in addition to uh using the models from the Frontier Labs. And so this talk will be a bit about how we see that evolving and unfolding where like what is the role of training in AI native enterprise? How does this coexist with the frontier models? Uh and like what do we think is going to be the version of this that really unlocks the most value for people and what does it look like?
</details>

组织内部拥有海量的知识，而且组织成立的时间越久、体系越成熟，从未被记录下来的隐性知识就越多。固然有些东西被书面记录下来了，比如代码库、电子邮件和操作流程，其中部分非常明确，就像“你必须这么做”、“这个系统是这样运作的”这类硬性规则。但很多东西其实存在于员工的脑海中，存在于邮件字里行间、会议纪要以及人员之间的沟通网络中。比如很多公司在纸面上有一张组织架构图，但还有另一张由“谁在真正做决策”、“变革在公司内部如何被推行”、“什么样的指令容易生效”构成的实际架构图。长期待在公司的人逐渐积累起了这类认知：“事情大致是这么运作的，摩擦点通常出现在这些环节。”在很多情况下——我认为这正是企业级 AI 的一大机遇所在——许多普通员工所处的位置，并不足以让他们去改变组织中出现的问题，因为并没有人把这些明确阐述出来，也没有人站在全局视角俯瞰组织内发生的一切并指出：“这里的效率很低，本可以改进；这个问题在这么多不同团队中反复出现，却没人意识到某个团队其实早就找到了解决方案。”而智能体非常擅长处理这类事情：智能体在梳理大量非结构化文本数据、发现这类模式并将其转化为有用成果方面能力极强，能够指出：“这个工作流存在问题，它在浪费时间且效率低下，本可以换一种方式进行。”

<details>
<summary>Original English</summary>
Um, and so organizations have lots of knowledge and like the longer an organization's been around and the kind of more established it is, the more implicit knowledge there is that kind of doesn't ever get written down. Um, there are things that do get written down. There's code bases, there's emails, there's processes. Some of these are very explicit. They're like rules of like you must do this, this thing works like that. But a lot of things kind of live in people's heads and they live in between the lines of emails, of the meeting notes, of the kind of who talks to who. Like a lot of companies will have like a a on paper org chart and then a real org chart of like who actually makes decisions and like how does change get adopted throughout the company, what sorts of mandates are likely to take effect. Uh and people have kind of built up this knowledge from being at companies for a long time of like oh this is kind of how things work. This is where the friction points are. And I think in many cases uh and I think this is really one of the big opportunities for AI at the organizational level is is that many individual people are kind of not in a position where they can change the things that are broken in an organization. Um because no one is actually spelling it out. No one is is like taking a bird's eye view of looking at everything that happens in an organization and saying hey this over here is inefficient. This could be better. this thing keeps happening across all these different teams, but nobody's figured out that the solution has actually been discovered by that team. And these are the sorts of things that like agents are great for. Like agents are very capable at combing through large amounts of textual data that's unstructured and finding these kinds of patterns and turning them into something useful uh and and surfacing them as like, okay, this workflow has a problem because it is wasting time and it's inefficient and it could be different instead.
</details>

### 从规则到模式：为什么上下文学习不够用
然而，我们并不希望这只是一次性的行为，而是希望它逐渐成为组织广泛应用 AI 的通用方式：智能体既能获得所需的上下文，又能够反哺并改进智能体本身以及组织本身。我们希望智能体更像我们的工作同事，但人类同事是在工作中不断学习的，而智能体的学习方式则相对原始，主要依赖上下文学习（in-context learning）。通常的形式就像是有人编写的技能文件（skill file），或者由智能体查阅代码库，但它们并没有真正获得人类员工所具备的组织层面的潜在隐性知识。因此，它们经常需要重复学习，反复去摸索同一件事，消耗大量的输入 Token。如今人们逐渐意识到，缓存命中率下的输入成本已经成为诸多智能体成本的核心瓶颈。即便你获得了极高的缓存命中率并降低了缓存成本，每当重新执行一个工作流时，依然必须重新处理大量的输入。为了克服这一点，人们自然希望能够将更多内容直接固化到模型中，尤其是那些很难写成死板规则的内容。

<details>
<summary>Original English</summary>
Um, and we don't want to just do this once though. We want this to kind of become the way that organizations adopt AI broadly where uh, agents are able to get the context they need, but also they're able to improve both the agents themselves as well as the organizations. And we want agents to be more like our co-workers, but um, human co-workers learn on the job. Agents learn in relatively primitive ways through like in context learning. Um, and this typically looks like them kind of having a skill file written by somebody or like looking around a codebase, but they don't get the institutional level latent knowledge that human employees really do. Um, and so they relearn a lot. They have to rediscover things. They spend a lot of input tokens. And I think nowadays people are realizing that like cash to input is like the bottleneck in many agent costs. Um, and even if you do get great cash rates and cash costs go down, you still have to like reprocess a lot of input to redo a workflow every single time. Um, and so to get around this, you kind of want to be able to bake in more into the model, especially for things that are harder to write down as rules.
</details>

我喜欢从**规则与模式**的光谱，以及概念上**代码与数据**的对比来思考这个问题。很多东西以代码形式存在，比如技能文件、操作规则大致属于此类；但像偏好、摩擦点、启发式经验和趋势，这些本质上全是数据。机构依托庞大的数据在运转，组织中的员工能够隐性地领会这些数据，模型却从未真正有机会学习它们，我们认为这正是阻碍它们成为真正同事的瓶颈所在。

<details>
<summary>Original English</summary>
So I I like thinking about the spectrum from like rules to patterns as well as like conceptually like code versus data. And so lots of things live as like code and like skills are kind of like this, rules are kind of like this. But things like preferences and friction and heruristics and trends, these are all data and institutions have so much data that they are like running on and the employees of the organization implicitly learn that models never really get a chance to learn. And this is the sort of thing that we see as blocking them from becoming true co-workers.
</details>

### 将组织知识注入模型权重
于是便出现了一个问题：哪些内容该放入上下文，哪些内容该固化进模型权重？其中的部分逻辑在于，知识需要“争取”进入权重的资格，事物并不会立即直接写入权重。但如果你观察每一代新模型的演进，模型变得更强并非因为提示词写得更好，而是因为实验室对它们进行了更多的训练。训练是有用的，训练是行之有效的，训练正是我们看到现有进展的原因。模型大体上是在海量数据上训练出来的，目的是逼近实验室所预期的、在各组织中具有高价值且可重复的工作流程。

<details>
<summary>Original English</summary>
Um, and so there is a question of like okay, what goes in context? What goes in the way? And part of it is you kind of need to earn it. Like things don't just go in the weights right away. But if you if you see kind of every new generation of models, the models get better not because the prompt is better, but because they train them more. Like training is useful. Training works. Training is why we see the progress we do. And the models roughly are like trained on lots of data that is aiming to approximate things that makes that that the labs expect will be like high value repeatable workflows uh at organizations.
</details>

当前模型获取能力的流程虽然行得通，也是模型变强的方式，但如果你把它具体拆解开来，会发现其效率相对低下。举例来说，模型要学会极其精通地组合使用某些 Salesforce 工具，通常的路径是：某个懂得这些工具如何使用的人正在找工作，可能他们之前在某家使用这些工具的公司工作过，现在正在浏览专家网络平台赚点外快，并将自己的专业知识分享给专家网络公司的某位工作人员；这家网络公司的人获取人类的这些数据后，再转交给负责创建强化学习（RL）环境的人；随后，缺乏这门专业知识的销售人员将该强化学习环境卖给实验室的研究人员，而这位研究人员本身同样不是该领域的专家；研究人员对环境进行微调，将其放入训练流水线，最终接入下一代前沿模型的训练轮次中。通过这种类似“传话游戏”的过程，模型才辗转获得了最初那位人类的部分知识。这一流程环节极多，而且相对封闭隐秘。各阶段之间彼此交流，但真正掌握专业知识的人既没有监督训练过程，也无法像人们日常调试编程智能体那样，直接决定模型如何被训练。

<details>
<summary>Original English</summary>
Um and I like this like I think there's a a process that currently it works. It's how the models get better but if you like spell it out it's relatively inefficient. So like the way that a model would learn how to get really good at like using some combination of like Salesforce tools for example let's say is someone who knows how those tools get used has to be looking for work uh and maybe they previously worked at a place that were using these tools and now they are uh browsing kind of expert network sites to make some money in their free time and they are sharing their knowledge to someone who works at an expert network company. this person at this network company will then turn this uh take this data from the human and uh pass it to someone else whose job is to create RL environments. This RL environment might get sold then to by someone who doesn't have this expert knowledge to a researcher at a lab who also really isn't the expert in the domain who then will be refining it to put it into a training pipeline uh to go into the next frontier model run to make a model that has kind of through this like game of telephone gotten some knowledge of that human originally. But there's so many steps in this pipeline and it's a relatively secret pipeline. Like people people talk at across two stages of it, but like the human who knows this thing is not supervising the training run is not really directly inputting like how the model gets trained in the way that a human could if they were doing it for their coding agent that they're working with day-to-day.
</details>

因此，我们看到的机遇以及希望发展的方向，就是弥合这一鸿沟。就像我们在使用编程智能体时，每次都要提示类似的事情、嘱咐它们不要重复同样的错误一样，你完全可以通过这种方式来训练模型：向模型传达要求，它们便能持久地习得这些知识，而不仅仅是在 `AGENTS.md` 文件里多加一行规则——那类规则随着不断累积，最终往往需要频繁重构。尽管你依然可以做一些规则维护，但在很多时候，你真正需要传达的是情境化的偏好，例如指出：“在当前场景下，你刚才的做法并不完全符合我的要求，我更倾向于这么做。”我们希望系统能将这些反馈沉淀为持久的知识，而训练正是实现这一点的高效途径，因为你所提供的数据形态与实际训练流水线所需的数据非常契合。

<details>
<summary>Original English</summary>
Um, and so what we see as an opportunity and kind of also where we would hope to go is like to close this gap and to allow the person who the same way that when we work with our coding agents, we're prompting them like the same things every time, telling them to like not repeat the same mistakes. Um, this is how you could train models. You can tell the models things uh and they will learn these things durably, not just as like a line in your agents MD which kind of accumulates and then you have to refactor it all the time. You can do some of that, but a lot of times what you really want is you're giving kind of contextual preference. You're saying in this setting, this thing that you did was not exactly what I wanted and I would have preferred this instead. And we'd want systems that can compound this into like durable learning. Uh, and training is a very effective way of doing this because the shape of data you're giving there is quite close to what you would want uh from like an actual training pipeline.
</details>

学习的方式有若干种：有由人类完成的学习；有在脚手架（harness）层借助技能与记忆实现的方式；也有散布在整个组织的文件系统和数据库中、通过工具和代码检索的知识；此外就是模型本身，虽然它们具备非常广博的世界知识，但相信大家在使用知识截止日期较久远的基础模型时都经历过沮丧感——你很难跟模型流畅探讨过去 6 个月内的新闻，它们不得不每次在上下文中重新理解世界模型，这导致它们无法像讨论更久远的事情那样自如应对。因此，企业为了从模型中榨取最大的价值，我们设想它们会越来越希望模型能够从直觉层面真正理解组织内部正在发生的事情，而这正是需要通过训练来实现的。

<details>
<summary>Original English</summary>
And so there's there's several different types of learning. There's things that people do. There's things that you can do at the harness layer with skills and memory. Uh there's knowledge that just lives uh throughout an organization in file systems and databases uh that you retrieve uh with with tools and with code. Uh then there's the models themselves which have this really broad world knowledge but like we all have I'm sure experienced uh frustration when using a model whose like cut off of knowledge is like a while back and like you can't really talk to the models about the news of the past 6 months nowadays like they don't really they have to go like relearn a world model in context every single time and this just does not allow them to really operate as fluently as they can discuss things that happened longer ago. And so organizations to get the most value out of models, we imagine they will want to increasingly have models that really understand what is going on in the organization at an intuitive level. And this is the sort of thing that you want to train for.
</details>

### 持续学习的工程化落地：评测与决策模型
那么该如何达成这一目标？一个组织从持有“利用自身数据训练模型”的抽象想法，到真正落地，其路径是怎样的？我认为一个极其实用的切入点是将评测（evals）本质上作为**测试用例**。在软件代码领域，围绕测试、生命周期以及软件开发生命周期（SDLC）已经达到了成熟的阶段，通常能够确保代码库长期健康发展，而智能体正帮我们分担大量的此类工作。对于大多数组织而言，我认为最切合实际的持续学习形态，就是将模型视同为一个代码库：你可以围绕它建立生命周期，为其添加测试用例、引入新功能以及积累资产。在使用智能体的过程中，最初你会收集调用轨迹（traces），这些轨迹中包含你的提示词以及对模型输出的反馈。仅仅通过使用这些模型的过程，你就在不断积累构建评估所需的资产。过去制作评测体系往往比较繁琐，许多组织不愿手动去做；但值得庆幸的是，智能体正在迅速成熟，我们已经可以用机器来为我们承担大部分评估的清洗与构建工作，尤其是当我们进一步针对构建稳健且利于学习的评测规范对智能体进行训练之后。

<details>
<summary>Original English</summary>
Um, and so how do you get there? Like what is the road for an organization to go from like having this idea in the abstract of like we're going to train models on our data to actually getting there? And I think one really useful starting point is eval as essentially test cases. I think like with code we've gotten to a point of maturity around like testing and life cycles and software development life cycles for ensuring that uh code bases grow healthily over time usually and agents are doing so much of this work for us. And the version of continual learning that I I think is like most practical for most organizations is just treating a model kind of like a codebase where it is the sort of thing that you can have a life cycle around, you can add test cases to, you can add features to, you can add uh assets to and this is the sort of thing that the process of using agents like initially you collect traces. These traces have your prompts and they have your feedback to things that models did. And this just from the process of using these models, you are accumulating the assets you need to create evals. It's just that making evals historically has been a little bit painful and a lot of organizations have not necessarily wanted to do it manually. But the agents are quite quickly getting to the to the point where thankfully we we have robots that can can do a lot of the eval curation for us, especially as we train them more on the best practices of making evals in ways that are robust and amendable to learning.
</details>

另一个实用的例子是近几周由 Jev 引发并席卷业界的决策模型（decision model）热潮，以及与之类似的路由（routing）机制。大家对成本优化充满热情，因为大家都发现每个月在云服务上耗费巨额资金是常有的事，因此需要弄清何时应当调用更便宜的模型。我认为人们已经意识到这类逻辑需要运行在脚手架层，同时它的特性与决策模型十分相似。我之所以把两者放在一起谈，是因为它们针对的是标签明确、有标准答案的场景，让人类或其他智能体有机会给出反馈。你可以让大模型和小模型执行相同的任务，判断小模型表现是否与大模型相当；如果是，这就转化成了一条数据，表明对于此类任务我们可以更多地路由给小模型。对于旨在模拟人类在特定情境下做出判断的决策模型也是同理。这是一种极佳的可标注操作：人类可以进行审批，就像我们有时在 Claude Code 中审核工具调用一样（不过我想大多数人已经开启了自动接受工具调用）。但在工具安全性之外更定制化的场景下，每个组织都会有自己的规则和偏好，这些正是可以沉淀到决策模型中的内容。这是一种非常具有可行性的持续学习形态，许多团队明天就可以直接接入并立即看到价值。

<details>
<summary>Original English</summary>
Um, and so I think another useful uh example here is the decision model craze that has kind of been taking the world by storm in the past couple weeks with with Jev and also the parallels around routing and people being very excited about cost optimization because we see that like it's possible to spend very large amounts of money on cloud every month and we figure out like when should we use a cheaper model. Um, and this is the sort of thing that I think people are recognizing needs to kind of live in the harness. Um, but it also is a an attribute that looks relatively similar to uh decision models. And the reason I bring both these up together is because there's things with very clear labels where there's a right answer. And there's an opportunity for a human or another agent to give feedback. You can have the big model and a small model do the same task, judge whether the small model was as good as the big model. If so, then we this is now data of like for this kind of thing, we can start routing to the small model more. Same for a decision model that's learning to kind kind of mimic the way that a human in a certain situation would make a judgment. Uh this is a great labelable action um where the human might be doing the approval the same way that like we approve our tool calls in cloud code sometimes but I think most people have turned on like auto uh tool acceptance um but every organization for more bespoke things that aren't just about like tool security are going to have their own rules and preferences and these are the sorts of things that you could then compound into a decision model and so this is like a very believable form of continual learning that a lot of people could just plug in tomorrow and uh see immediate value from
</details>

更为广泛地来看，我们在 Prime Intellect 所开展的大量工作，正是与那些希望推进更具雄心训练项目的组织合作：将模型在生产环境中运行高并发用例所产生的轨迹，转化为融合真实与合成数据的丰富且稳健的环境，以捕捉运行长周期智能体所面临的实际复杂任务。只要配备充足的编排能力、配套工具并引入人在回路（human-in-the-loop），智能体在将这些调用转化为足够支撑训练的丰富环境方面极具价值。而且随着每一代开源和闭源模型的更新，这个过程的自动化程度越来越高。这意味着我们迎来了一个契机：通过让智能体负责数据清洗、构建供人类表达意图的交互界面，能够将我们现有的日常操作直接自然地演变为自我改进的闭环。

<details>
<summary>Original English</summary>
um but more broadly what we see people wanting to do and this is a lot of the work that that we do at Prime Intellect is working with organizations that are looking to do relatively ambitious training projects around turning uh their traces from deploying a model in production for a high volume use case into rich robust environments that are blended real and synthetic that kind of capture the complexity of the real task they want to be using longunning agents for. and agents are very useful with sufficient orchestration around them, sufficient tooling and humans in the loop at turning these into environments that are uh rich enough to train in. Um, and we see that this is getting more and more automated with with every new generation of open and closed models. And this means that we have an opportunity to start having this whole thing of taking the stuff that we're already doing and turning it into a self-improvement loop just kind of fall out magically from applying agents to curation of the data and creating interfaces for humans to to give signal about what they want.
</details>

### 动态界面与人在回路的反馈闭环
这也是我自己在个人配置中反复尝试的一个想法，我认为它未来会成为与模型交互的主流界面。你在部分机器人中已经能看到端倪，尤其是现在模型非常擅长实时编写代码的情况下：这种小部件卡片（widget card）功能，我认为是一种极为实用的动态 UI 形式，在引导人类做出决策方面非常有效。它们类似于工具调用审批机制，但更加个性化、更具针对性，同时也规避了管理混乱的问题——比如后台跑着 20 个不同的机器人，你必须记住哪个在哪里、由谁来整理这一切；人们有时会纠结是需要一个机器人还是多个，拥有一个觉得很好，但随后想要两个，接着就变成了 20 个，我们似乎在单线程与多线程智能体之间来回摆动。但我们真正想做的是**做决策**：我们给智能体提供想法，让它们顺着思路执行，并在需要抉择时回来找我们。智能体理应在何时寻求人类决策上做出明智选择；如果智能体能够为我们动态生成即时界面，让我们极其直接地向其提供所需信息，这不仅比人类艰难阅读长篇对话去寻找“问题到底在哪里”要符合人机工程学得多，它在本质上也是 Jev 风格决策模型在人类这一侧的对应形态，同时能够产出完美的数据。

<details>
<summary>Original English</summary>
Um, this is a idea that I've been for my own setup been like playing around with a lot that I think will become a a popular interface for interacting with models more in the future. You're seeing it a little bit in some of the bots, but I think it especially now that models are good at like writing code on the fly. These kind of widget card features that are like I think a very practical form of dynamic UI that are also really useful for eliciting human decisions. So, they're kind of like the the tool call approval thing, but much more personalized, much more specific, and also kind of get around the problem of like, okay, you have 20 different bots that are going, and you have to remember which ones are where, and who is curating all this for you, and then people are like, do you want one bot? And then you're like, oh, one's great, but I actually want two. Then you have two, then you have 20. And I think we kind of are oscillating back and forth between this the single stream and the multiream agent threads. But what we really want to do are make decisions. We want to give ideas to the agents, let them run with the ideas and then come back to us when we need to make decisions. And the agents hopefully should make good choices about when to bring us decisions. And if agents can create interfaces on the fly for us that allow us to very directly give them the information they need. One, this kind of is much more ergonomic for us as humans uh than like uh reading trying to parse through a long thread message to see like, okay, where was the question? It's also kind of like the human dual side of the the decision model uh Jev style. Uh but it also is perfect data.
</details>

我们一直在探索将此作为训练模型的一种手段，通过这类自然界面获取人类输入，让这一反馈闭环运转起来。人类输入直接充当标签，由于目标极其明确，模型可以直接据此进行自我改进，这规避了大家常听到的奖励欺骗（reward hacking）等诸多问题。那些问题同样值得解决，但我们认为这是解决许多难题的极为实用的切入点。这并不需要应用到技术栈中的每一个模型上，它可以部署在编排层模型或决策模型中，但它是让偏好与隐性知识在模型权重中开始产生复利的一个切入点。

<details>
<summary>Original English</summary>
And so it's a setting where we've been experimenting with this as a way of training models to kind kind of get this feedback loop going from having human input with these kinds of natural interfaces be the sort of thing that directly acts as a label and is the sort of thing that you that a model can directly improve on because there is a very explicit target. uh and it gets around a lot of the problems that we kind of hear about in reward hacking and whatnot. Those things are worth addressing too, but like this is like where we see a very useful starting point being for a lot of these problems. And this can be done doesn't have to be with every model in your stack. It can be the orchestration layer models, it can be the decision models, but it is an entry point for kind of starting to have this compounding of preferences and latent knowledge happen in the models.
</details>

### 落地案例与持续训练机制
今天我刚添加了一个近期的案例：来自一家名为 Paper Instruments 的公司，他们是我们的一位朋友，使用了我们的一些工具来开展这项工作。他们花费了 30 万美元训练了一个模型，在电子表格和演示文稿等知识工作处理上达到了帕累托前沿最优（pareto-frontier optimal）。对于一个机构来说，这相当于一名员工量级的投资——你可以选择雇佣一名软件工程师，也可以选择训练一个模型；如果你在更长周期内不断沉淀知识，这项成本还可以分摊展开。这种方式正变得越来越具有现实可行性，并且已成为许多组织当前迫切希望实践的路径。随着人们逐渐认识到这一模式的价值，看到开源模型已经足够优秀，并且能够通过将特定领域的知识、运行脚手架和环境转化为训练场景，让开源模型变得更加卓越与高度个性化，这种需求的月环比增长趋势非常明显。

<details>
<summary>Original English</summary>
Um, and so I think there's a recent example today, I just added this uh earlier from a company called a paper instruments that uh they use some of our tooling to do this. They're they're friends of ours. Um, but they trained a model for uh 300K that is kind of paro frontier optimal for knowledge work for things like spreadsheets and slides. And it's like an employee scale investment for an org to do. Uh where like you could like go hire a software engineer or you could like train a model. Um and you can also spread this out over a longer period of time if you're kind of compounding the knowledge over time. But it's the sort of thing that is increasingly becoming quite practical. Uh and is the sort of thing that a lot of organizations we see wanting to do now and we kind of see the trend of how much more the demand for this is growing month after month. uh as people start recognizing one the value of this and how kind of the the open models are good enough that you can get them to be much better and also much more personalized by turning your knowledge for your domain, your harness, your environment into a training setting for them.
</details>

这自然而然地形成了一个学习闭环。这也是我们在内部正在推进的一个原型项目，设想人们在实际生产中落地持续学习的真实方案：你可以收集调用轨迹，每天夜间查看系统提出的实验建议，审视被标记为异常或问题的事项，然后在夜间启动一轮训练任务。或许白天的推理算力在支撑企业的智能体运行，而到了夜间员工很少使用时，便可以将这部分算力转而用于模型训练。我们认为这是一种非常自然的实现路径，各机构很快就能藉此真正实现模型权重的持续学习，并将自身积累的知识不断沉淀为智能体越来越强大的能力。

<details>
<summary>Original English</summary>
Um but also it's the sort of thing that naturally lends itself to a a learning loop. And so this is a a prototype of something we're doing internally around kind of how we're imagining people can really deploy continual learning in the world which is that you can have traces you can start collecting these and you can then like every night see the proposed experiment look at the things that have been flagged as issues and kick off a training run for the night. Maybe your inference capacity in the day is serving your agents at night employees are not using them as much and you can use that capacity for training instead. And so this is a very natural way that we see organizations able to like quite soon actually do for real continual learning in the weights of the models and start compounding their knowledge into uh better and better capabilities for their agents.
</details>

这大体就是我们预见诸多努力最终汇聚的终局。这其中包含许多要做的事情：首先是梳理出你的工作流程，然后创建技能规则，建立评测体系，做好流量路由，最终逐步追求规模效应，沉淀企业与机构内部数据所带来的复利，使整个组织以长期不断迭代演进的方式实现高度的自我改进。

这就是我今天分享的内容。如果还有时间的话我可以回答提问……看来没有问答时间了。我们在 Prime 正在大力推进这方面的工作，其中很大一部分是开源和公开的，我们通过博客和社交平台发布相关内容。同时我们也与许多企业开展合作，团队正在招聘与扩张。如果大家希望交流合作，欢迎随时取得联系。谢谢大家。［掌声］

<details>
<summary>Original English</summary>
Um and so this is kind of the where we see a lot of this culminating towards there's so many things you do. First you discover your workflow, you uh create skills, you make evals, you do routing and then eventually you start to want to get the economies of scale, get the compounding benefits that have come from the data inside of your companies, your organizations, and and have the organizations become increasingly self-improving in ways that uh get better and better over time. Um, that's what I got. Uh, I can maybe take questions if there's any time like I don't know. No questions. Um, and uh, yeah, we're at Prime. We are working a lot of this stuff. A lot of it is open source and public and we uh, blog about it and tweet about it, but also we work with companies and we're hiring and growing and so get in touch if you want to get in touch. Thanks. [applause]
</details>