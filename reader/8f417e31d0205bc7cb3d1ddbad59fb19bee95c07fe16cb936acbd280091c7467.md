---
author: Latent Space
date: '2026-03-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mMbPEf4V_hE
speaker: Latent Space
tags:
  - ai-agent
  - enterprise-ai
  - context-engineering
  - data-governance
  - identity-layer
title: Box 首席执行官 Aaron Levie：为什么每个 AI Agent 都要有一个 'Box'
summary: Box 首席执行官 Aaron Levie 与 Latent Space 探讨了 AI Agent 在企业级落地面临的挑战。他指出，Agent 并非万能药，企业需要通过“上下文工程”重新设计工作流，解决身份、权限和数据治理等核心基础设施问题。他强调，每个 Agent 都需要一个受控的存储空间（Box）来处理复杂的现实数据，而 Agent 时代的到来将使技术性、高能动性的人才更加稀缺。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Aaron Levie
  - Jeff Huber
  - Brian Chesky
companies_orgs:
  - Box
  - OpenAI
  - Anthropic
  - Chroma
products_models:
  - Claude
  - GPT-4
  - Gemini
  - Box AI
media_books: []
status: evergreen
---
### 代理时代的到来：从编写代码到指挥 Agent

**Aaron Levie**: 现在的情况是，你不再是自己在写代码，而是与一个 **Agent** 对话，由它去执行，你顶多负责审核。甚至连审核可能都不再是你的核心工作。真正发生的变化是，我们正在改变自己的工作方式，以使 Agent 在这种模式下更加高效。**Agent 并没有适应我们的工作方式，本质上是我们适应了 Agent 的工作逻辑。** 整个经济体都必须经历同样的进化。

<details>
<summary>Original English</summary>

**Aaron Levie**: like you don't write code. You talk to an agent and it goes and does it for you and you maybe at best review it. That's even probably like like largely not even what you're doing. What's happening is we are changing our work to make the agents effective in that model. The agent didn't really adapt to how we work. We basically adapted to how the agent works. All of the economy has to go through that exact same evolution.

</details>

**Aaron Levie**: 目前，对于那些尽早介入并习惯这种模式的团队来说，这是一种巨大的资产和优势，因为你会看到**复利回报**。但对于大多数公司来说，真正完成部署还需要相当长的时间。

<details>
<summary>Original English</summary>

**Aaron Levie**: Right now, it's a huge asset and an advantage for the teams that do it early and that are kind of wired into doing this cuz you'll see compounding returns, but that's just going to take a while for most companies to actually go and get this deployed.

</details>

### 企业文件的力量：Agent 的新燃料

**Aaron Levie**: 我们建立了一个平台来帮助企业管理他们的文件，包括权限、共享和协作。这些文件包含企业极其重要的信息：合同、研究材料、营销信息、备忘录。以前，这些数据主要是给人类看的。但人类只有在处理具体任务时才会与文件互动，然后文件就会被束之高阁。

<details>
<summary>Original English</summary>

**Aaron Levie**: Well, the thing that that we get super excited about that I think is probably, you know, should be relatively obvious is we've we've built a platform to help enterprises manage their files and their their corporate files and the permissions of who has access to those files and the sharing and collaboration of those files. And all those files contain really really important information for that enterprise. It might have your contracts, it might have your research materials, might have marketing information, might have your memos. All that data obviously has, you know, predominantly been used by humans...

</details>

**Aaron Levie**: 突然之间，有了 **AI Agent**，所有这些数据都变成了源源不断的答案来源。它包含了新员工入职所需的项目信息，包含了销售人员与客户交谈时所需的准确信息，包含了产生下一个功能的路线图信息。**每个 Agent 都要有一个“Box”**，这将成为这个时代的标语。

<details>
<summary>Original English</summary>

**Aaron Levie**: And all of a sudden uh with the power of AI and AI agents, all of that data becomes extremely relevant as this ongoing source of of answers to new questions of data that will transform into into something else that that produces value in your organization... every agent needs a box.

</details>

### 身份与安全：Agent 时代的“硬模式”

**Aaron Levie**: 我们将拥有比人类多出几个数量级的 Agent。那么，在企业中使这些 Agent 有效运作所需的基础设施是什么？如何确保它们受到良好的治理？如何确保它们只对你的信息做安全的事情？会有极其疯狂的**安全事件**发生，比如通过**提示词注入（Prompt Injection）**攻击 Agent，进而渗透进 CRM 系统窃取数据。

<details>
<summary>Original English</summary>

**Aaron Levie**: we're going to have some order of magnitude more agents than people. That's inevitable. It has to happen. So then the question is what is the infrastructure that's needed to make all those agents effective in the enterprise? Make sure that they are well governed. Make sure they're only doing safe things on your information... There's going to be just incredibly spectacularly crazy security incidents that will happen with agents because you'll prompt inject an agent and sort of find your way through the CRM system and pull out data that you shouldn't have access to.

</details>

**Aaron Levie**: 目前我们还处于“简单模式”，即 Agent 就是你，它代表你进行认证，拥有你所拥有的一切权限。而“硬模式”是 Agent 自主运行，人们偶尔检查。这种情况下，如何给它们授予资源访问权限而不大幅增加安全风险？我们需要一个**身份层（Identity Layer）**。Agent 不享有隐私权，因为它们没有法律责任，创建 Agent 的人必须承担责任。

<details>
<summary>Original English</summary>

**Aaron Levie**: So far, we've been in easy mode. We've hit the easy button with AI which is the agent just is you... The hard mode is agents are kind of running on their own. People check in with them occasionally. They're doing things autonomously. How do you give them access to resources in the enterprise and not dramatically increase the security risk... Agent doesn't deserve any privacy because because it's you know it can't fully be autonomously operated and it doesn't have any legal you know kind of you know responsibility.

</details>

### AI 编程 vs. 企业知识：为什么 Agent 还没完全起飞？

**Aaron Levie**: 很多人在问，为什么 AI 编程已经起飞了，而在其他领域还没看到同样的效果？如果你对比一下，就会发现 AI 编程拥有最完美的条件：代码库对工程师是开放的，它是纯文本输入输出，模型经过了海量训练，开发者本身就是 AI 的日常用户。

<details>
<summary>Original English</summary>

**Aaron Levie**: Why is that taken off and and we're not yet fully seeing it everywhere else? Well, like if you just like enumerated the list of properties that AI coding has and then compared it to other knowledge work... Generally speaking, you bring on a new engineer, they have access to a large swath of the codebase... It's a fully text in text out you know medium... Obviously the models are super trained on that data set.

</details>

**Aaron Levie**: 但在其他经济领域，你会遇到无数阻碍。比如你是金融行业的银行家，你只能接触到极少部分的数据。为了完成工作，你必须到处找人沟通。现实中的信息媒介不只是文本，还有视频会议、口头交谈。**Agent 的本质不是掉进去就能自动完成一切的“万灵药”，你必须重新设计（Re-engineer）你的工作流。**

<details>
<summary>Original English</summary>

**Aaron Levie**: Every other part of the economy has like like six to seven headwinds relative to that list. You go into a company, you're a banker in financial services, you have access to like a tiny little subset of the total data that's going to be relevant to do your job... this is not the panacea that people were hoping for of the agent drops in just automates her life. like you have to basically re-engineer your workflow to get the most out of agents.

</details>

### 上下文工程与“上下文腐烂”

**Aaron Levie**: 我们整天思考的就是 **“上下文腐烂”（Context Rot）** 问题。有人曾认为无限上下文窗口能解决一切，但在现实中，成本太高了。你不可能让模型阅读 5000 份可能相关的文档。

<details>
<summary>Original English</summary>

**Aaron Levie**: 100% we we all we think about is is the context rot problem... someone was like was like well infinite context windows will solve all of these problems and cuz you'll just you'll just give the context window like all the data... first of all it would just it would just simply cost too much like we just can't give the model like the 5,000 documents that might be relevant...

</details>

**Aaron Levie**: 即使你有 20 万个 Token 的窗口，面对一个拥有 1000 万份文档的企业语料库，那也只是杯水车薪。这就是为什么**搜索系统和数据库层**必须非常稳健。模型需要具备判断力，知道什么时候搜索到了错误的信息，什么时候应该回过头去检查，什么时候该放弃任务。这种**判断力（Judgment）**是模型需要具备的新能力。

<details>
<summary>Original English</summary>

**Aaron Levie**: I have 10 million documents... I'm at 50 million pages of information and I have 60,000 tokens. Like holy [ __ ] this is like how do I bridge the 50 million pages of information with you know the couple hundred that I get to work with... and that judgment is like a really new thing that the model needs to be able to have. It's like when should it give up on a task cuz cuz you just don't it just can't find the thing.

</details>

### 知识图谱 vs. 简单的 Wiki 模式

**Aaron Levie**: 关于**知识图谱（Knowledge Graphs）**，这总是一个能引发宗教战争的话题。很多人陷入了“图谱崇拜”，认为一切都必须用图谱表示。但也有很多人主张简单的 Markdown 文件和 Wiki 模式。

<details>
<summary>Original English</summary>

**Aaron Levie**: because a lot of people get graph religion and they're like everything's a graph like of course you have to represent as a graph... and then there's there's a lot of people who are like well you don't need it and both are right.

</details>

**Aaron Levie**: 我认为图谱结构应该是在 Agent 的“大脑”中自然生成的，就像在人类大脑中一样。这是一种更强大的图谱，因为它会随着时间演化。我们的搜索系统并不卷入这种 religious war（宗教战争），我们乐意接入别人的图谱。

<details>
<summary>Original English</summary>

**Aaron Levie**: I think I think the actual graph structure is emergent in the mind of the agent in the same way it is in the mind of the human and that's a more powerful graph because it actually evolve over time.

</details>

### 创始人模式：在 AI 海啸中求生

**Aaron Levie**: 我会授权（Delegate）掉 90% 的工作。但对于涉及公司生死的**存在性（Existential）**部分，比如关键的架构决策、AI 功能决策，你无法按传统意义去授权。你会感觉到那股 **AI 海啸**，如果做错两三个决策，一年后你就可能出局。这种创始人能量会自动把你吸引到这些决定公司未来的关键环节中。

<details>
<summary>Original English</summary>

**Aaron Levie**: 90% of the work that happens at Box is fully, you know, fully delegated... then there's this part that is like the existential part of the business which is if we don't do this right, we're out of business... like you can just see how the AI tsunami could wipe you out if you make just two, three, four, five wrong decisions in this space.

</details>

### 个人生产函数：保持反馈回路

**Aaron Levie**: 很多人问我的生产函数是什么。其实就是我读很多 Twitter，看业务中遇到的各种问题，并在内部实践与外部讨论之间建立一个**飞轮（Flywheel）**。我把学到的东西扔出去，获得反馈，再带回公司。

<details>
<summary>Original English</summary>

**Aaron Levie**: I'm getting to see the all the problems that we are running into constantly and I'm trying to uh be a little bit of a create a flywheel between what we're doing internally what what what then we talk about uh getting a feedback loop on that and seeing other people's you know experiences of what they're doing bring that back into the business...

</details>

**Aaron Levie**: 对我来说，**“公开构建”（Building in Public）**是极其自然的事。我年轻时曾因为想在实习期间写博客而被取消了实习资格，因为他们觉得我不够专业。但我认为连接外部世界与 Box 的工作是我的职责所在。

<details>
<summary>Original English</summary>

**Aaron Levie**: Anyway I I only say that to say that like like to me just like you know building in public is just like a natural is a natural thing. And so I so I just you know go through the day we we deal with interesting problems. I tweet about them. I get information back in the process.

</details>

### 最后的忠告：不要停止学习编程

**Aaron Levie**: 当有人说“你不需要学习编程”时，我总是觉得很好笑。事实上，**技术岗位是受保护程度最高的职业类别**，因为事情只会变得越来越技术化。我们这些既能写代码又能像挥舞魔法棒一样驾驭 AI 的人，效率会比普通人高出千倍。

<details>
<summary>Original English</summary>

**Aaron Levie**: I actually think like that is like still one of the most protected job categories because things are only getting more technical... there's a bunch of us who are like just in that sweet spot of like we can code and we can wield AI a thousand times more effectively than you can.

</details>

**Aaron Levie**: 未来的代码量会增加 10 到 100 倍。一旦 Agent 开始把一切都转化为软件，工程能力将变得空前重要。

<details>
<summary>Original English</summary>

**Aaron Levie**: but no matter what there's going to be 10 to 100 times more code. So I think you can be very long engineering right now as just a you know purely on the dimension of of software is going to become increasingly more important once agents are are you know turning everything into software.

</details>