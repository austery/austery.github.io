---
author: AI Engineer
date: '2026-10-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YqxpPI7YUjE
speaker: AI Engineer
tags:
  - code-review
  - ai-agent
  - software-factory
  - software-graph
title: 为什么单行代码变更可能破坏整个技术栈：Qodo 软件工厂中的代码审查瓶颈与上下文图谱
summary: Qodo 解决方案工程师探讨了 AI 软件工厂演进中代码审查阶段的瓶颈。演讲指出代码生成提速后，跨仓依赖等问题易引发严重事故，提出了结合软件依赖图谱、自定义规则与独立审查智能体进行审查及前置校验的方案。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Cole Gannaway
companies_orgs:
  - Qodo
  - Bitwarden
products_models:
  - MCP
media_books: []
status: evergreen
---
### 软件工厂的演进与审查瓶颈

>> 非常感谢大家来参加这场讨论。我一会儿可能还会邀请现场听众进行一些互动。我们很想了解大家对这些事情的看法。今天的目标是聊一聊我所代表的机构 Codo（Qodo），以及软件工厂是如何演进的。这是我们在行业中看到的一个趋势，许多 AI 原生或 AI 优先的公司正朝着这个方向发展。我认为大家对这类工厂的未来形态都有一个宏伟的设想，而我们相信 Codo 是其中至关重要的一部分，但并非全貌。因此，这里有我们所做的事情、我们专注的领域，也有处于我们范围之外的领域，我们会确保在这些方面解释清楚。

<details>
<summary>Original English</summary>
>> Well, thanks so much for showing up to this discussion here. I'll probably actually ask for a little audience participation as well. We'd love to get to know how you guys are thinking about things. The goal of today is to talk a little bit about Codo, which is the organization I'm representing, as well as how software factories have evolved. This is sort of what we're seeing in the industry where a lot of AI native or AI first companies are starting to head. I think everyone has a grand vision of where these factories can go, and we believe Codo is a critical part of that, not the complete picture of that. So, there's an element of what we do, where we specialize, and then areas that are outside and we'll make sure to be clear on some of that.
</details>

我先切入第一个值得展开探讨的部分。我是所谓的解决方案工程师，所以我的工作是与各家机构交流，探讨我们的产品或其他产品如何融入他们的工作流，并介绍 Codo 这个平台。我经常从客户那里听到的是，他们对于从工单一直走到生产环境感到非常兴奋。也就是从某人生成代码或者提出工单开始，能够一路将其直接推进下去；然而他们发现，在 PR（拉取请求）阶段或审查阶段，他们遇到了困难。这已经成了一个巨大的瓶颈。代码生成虽然我不会说已经彻底解决，但其发展速度绝对是我们前所未见的。因此，这成了一个大瓶颈。这也是为什么向人类、编码智能体或审查智能体提供尽可能多的上下文至关重要，以确保我们做出正确的决策。这实际上就是信任与验证层。

<details>
<summary>Original English</summary>
I'll I'll kind of hop into the first one that's worth kind of walking through. I'm what's called a solutions engineer, so I spend time with organizations talking through how our product or other products might fit into their workflows and teaching about Codo as a platform. What I often hear from customers is that they're super excited about going from ticket all the way to production. From somebody generating code or somebody coming up with a ticket and being able to push that all the way through, and what they're finding is at the pull request level or at the review stage, they're struggling. This has become a huge bottleneck. Code generation, I wouldn't say is solved, but it's definitely moving at a rate that we've never seen before. And so, this has been a big bottleneck. This is also where it's critical that we provide the human or the coding agent or the review agent with as much context as we can to make sure that we're making the right decisions. This is really the trust and verification layer.
</details>

所有其他组件仍然很有价值，但值得注意的是，今天我们将重点关注的就是这里的审查部分。

<details>
<summary>Original English</summary>
All the other components are still valuable, but just worth noting that's where we'll focus a lot today is on that review section here.
</details>

### 单行代码变更的爆炸半径与上下文图谱

我想举一个实际的例子。正如我提到的，代码生成不一定算彻底解决了，但当我们在看代码、创建功能以及尝试生成新代码和新功能时，我们经常会无意间遗漏一些东西。这就是一个例子，我们这里只有一个单行修改。这是在开源密码管理器 Bitwarden 上的，大家会注意到我们对数据模型只做了一行修改。如果我是开发者并看到这个，在我看来好像没问题，对吧？我会觉得这似乎是正确的改动，我就想给它重命名。我可能会直接合入它。我可能会去查看构建是否通过了、单元测试是否通过了，甚至 linter 检查是否都通过了。看起来这是我们需要的改动，也是我们想要的功能。

<details>
<summary>Original English</summary>
I want to give a a practical example. Um, as I mentioned, code generation's not necessarily solved, but when we're looking at code and when we're creating features and when we're trying to generate new code, new features, we can often miss things that we're not trying to. So, this is an example where we have just a one-line change. This is on Bitwarden, which is a open-source password manager, and you'll notice that we have just one line change to our data model. If I was a developer and I saw this, it seems good to me, right? I'm going to say this seems like the right change. I wanted it to rename it. I would probably merge it. I would probably look and see that the build passed, that unit tests passed, maybe even my linters passed. It seems like this is a change that we needed. This is a feature that we wanted.
</details>

批准它吧。所以我很好奇，或许大家可以举手表决一下，当你们谈到代码审查或检查变更时，情况是怎样的？我猜想大家有一大堆工具。当它们全给你打上绿色的勾时，是否就意味着可以上线了，还是说在你们那里实际情况是怎样的？也许大家可以举个手，比如有多少人合入过一个 PR，心里却想着：“呃，看着还行吧，但不能 100% 确定，我并没有看完全部代码行。”大概举一下手？是的。

<details>
<summary>Original English</summary>
Let's Let's approve it. So, I'm curious, maybe just from like a show of hands, but like how are you guys when you're talking about code review or review changes? I would imagine you have a bunch of tools. When they all give you green checks, does that mean it's good to go or what does that What does that look like for you guys? Maybe a show of hands, like how many have merged a PR that they were like, "Uh, it seems good to me. Not 100% sure. I I didn't look at all the lines of code." Uh, maybe just a raise of hands. Yeah.
</details>

没错。所以这里的每个人，我想现场几乎所有人都会觉得：“我们不可能去看变更的每一行代码，所以我们依赖这些工具。”市面上有很多优秀的工具。值得注意的是，并非所有工具都是一样的构造，也并非所有上下文都是一样的构建方式。在我们刚才那个会直接合入的例子中，我们会漏掉爆炸半径，或者说遗漏由此可能引发的影响。这一行代码变更可能会影响多个代码仓库。在这个例子中，我再次用 Bitwarden 作为一个演示说明性的例子，我们有一个后端服务器，它可能连接着 Web 客户端，可能连接着移动端或 iOS 设备，还可能连接着 MCP 服务器或 CLI。大家会发现，这一行代码改动会波及所有这些组件。所以这种情况通常是在生产环境中才被发现，对吧？比如出现了一个缺陷、用户案例受阻，或者是 Web 应用崩溃了。因此，我们非常希望能尽可能早地发现这个问题。

<details>
<summary>Original English</summary>
Right. So, every everyone here, I think, just about everyone here is like, "We can't look at all the lines of code that have changed. So, we rely on these tools." There's a bunch of great tools out there. Worth noting, not all tools are built the same and not all uh context is built the same. In this example that we would have just merged, we would have missed the blast radius or the effect that this can happen. This one line of code change can affect multiple repos. In this example, again, I'm using Bitwarden as as a sort of an illustrative example, we have a back-end server that could be connected to web clients, that could be connected to mobile or iOS devices, it could be connected to MCP servers or CLI. And you'll notice that all of these components are affected on that one line of change. So, this is typically found in production, right? Like maybe a bug or a user story or the web app crashes. And so, we'd love to be able to catch this as early as possible.
</details>

在这里，**上下文才是王道**。

<details>
<summary>Original English</summary>
Context is king here.
</details>

Codo 能做的一件事——我认为这一点非常重要——就是为你团队当前正在处理的代码仓库构建出一个**软件图谱**。它会自动将其构建出来，并且还会构建出一个集成界面。因此，不仅是——如果我们仅仅说 Bitwarden 服务器连接到了 Bitwarden Android，却没有说明具体连接的实际组件是什么，你可能会感到失望，或者这并没有那么大的价值。所以这是一个巨大的领域：如果我们在构建软件工厂，如果我们不去看每一行代码，我们如何将这些信息提供给我的智能体、提供给我的审查智能体，以便能够将其考虑在内？

<details>
<summary>Original English</summary>
Um one of the things that uh Codo will do and I think uh is is really important is build out a software graph of the repositories that your team is working on today. This will build it out automatically and it'll also build out an integration surface. So, not just uh you'd be disappointed or uh it wouldn't be as valuable if we said just Bitwarden server was connected to Bitwarden Android, but not what the actual components are that are connected. And so, this is a huge area of if we're building the software factory, if we're not looking at every line of code, how do we get this to my agent to my review agent uh to be able to take this into account?
</details>

### 自定义规则与独立审查智能体

另一件值得指出的事情是，并非所有事情都纯粹是功能性的。有些会涉及更资深的审查者、自定义规则，甚至可能涉及一些品味，以及我们如何从过去犯过的错误中吸取教训？所以，比如当我们回到这里的软件工厂时，我们有人类进行审查，但是否有办法将那位人类审查者带回到代码智能中，带回到审查层中，而不是让它每次都成为瓶颈，大家能理解这个思路吗？

<details>
<summary>Original English</summary>
Another thing that's worth uh calling out is like not everything is uh is is purely functional. Some are going to be a bit more senior-level reviewers, custom rules, maybe a bit of taste that's involved, and how are we learning from some of our past mistakes? Um so, when we go back to like the software uh factory for example here, we have a human that reviews it, but is there a way that we can bring that human reviewer back into the code intelligence, back into the review layer, rather than it just being every time that's the bottleneck, if that makes sense?
</details>

所以在当前这个示例中，我们可以添加一条自定义规则，上面写着：“嘿，如果要修改关于公共 API 的任何内容，我们必须确保要么添加一个弃用标记，要么对它进行更深入一点的审查。”

<details>
<summary>Original English</summary>
So, in this example here, we have a custom rule that we can add, which says, "Hey, if we're going to change anything about public APIs, we want to make sure that we add either a deprecation flag or we review this a bit more."
</details>

此外，我们非常希望在 PR 之前、在代码生成之前就拥有这些信息。因此，在我们生成任何一行代码之前，既然知道如果做出某些改动可能会产生潜在的下游影响，我们是否有机会提前引入这些信息？这些就是大家可以看到的领域，在这个例子中，我们有了一个 MCP 服务器，我们有了代码库的积累智慧，我们获得了那些可能存在的自定义规则或隐性知识，在将代码推送上去之前很久，就把所有这些全部注入到我们的编码智能体中。这并不能保证它绝对不会犯错，对吧？我想任何人都会说我们想要二次核对，但这给了我们一个好得多的机会，也更有把握在第一次尝试时就把事情做对。

<details>
<summary>Original English</summary>
Additionally, we'd love to have this information pre-PR, pre-code generation. So, is there an opportunity for us to bring this information in before we've ever generated line of code knowing that we have potential downstream effects if we make some of these changes. These are some of the areas you can see that in this example we've got an MCP server, we've got code base wisdom, we're getting those custom rules or or tribal knowledge that might exist, bring all that into into our coding agent long before we're pushing it up. That doesn't guarantee that it's not going to make mistakes, right? I think any anybody would say that we want to double check, but this gives us a much better opportunity and a much better shot at making it right on the first try.
</details>

这里值得指出的是，我认为许多机构在考虑：我是否应该直接使用 Cloud Code（Claude Code）或者我的实现智能体来直接做审查？这个审查阶段确实掌握一些信息，但其中部分信息在实际的生成阶段其实也是有价值的。同样值得注意的是，实现智能体正在做很多其他与审查无关的事情。虽然上下文窗口正在变大，但这并不意味着东西不会被埋没，也不意味着不会发生幻觉。因此，这里有调试、有实现、有探索代码库，而审查智能体则拥有我们想要使用的一套特定上下文。大家会注意到右侧这里，我们可能还有空间去关注其他事情。所以，不仅是我们看到的那些代码库智慧或图谱，我们甚至可以引入更多可能针对特定运行或特定审查定制的信息，我们可能有余力来容纳这些内容。

<details>
<summary>Original English</summary>
Worth calling out here, I think many organizations are thinking should I just use cloud code or my implementation agent to just do the review. This review stage has some information, but some of this is actually valuable in the actual generation stage. It's also worth noting that an implementation agent has a bunch of other things that it's doing that are not related to review. And context windows are getting bigger, but that doesn't mean that things don't get buried, that doesn't mean things don't get hallucinated. And so there's debugging, there's implementation, there's exploring the code base versus a review agent has a specific set of context that we want to use. And you'll notice here on the right we potentially have some room to focus on other things as well. So, not just the code base wisdom that we saw or the graph, we can even bring in more information that might be custom to this specific run or this specific review that we have potentially some room for as well.
</details>

这在某种程度上就涉及到：**编写代码的智能体，我们不需要由它来给代码打分**。第一，我们有了更多的可用上下文窗口。

<details>
<summary>Original English</summary>
So, this kind of goes into the agent that wrote the code, we don't need him grading the code. One, we have more context window available.
</details>

第二点是我们要确保它们是相互独立的。这可以体现在底层使用的大语言模型上，比如是 Anthropic、是 OpenAI，还是开源权重模型。我们能否利用多个模型来尝试消除其中的一些偏见？另一点则是测试套件或运行框架（harness）。如果运行框架是同一个，我们在那里可能会产生偏见。

<details>
<summary>Original English</summary>
The other is we want to make sure that these are independent. So, that can be things like uh the LLM that's being used under the hood, whether it's Anthropic, whether it's OpenAI, whether it's open weight models. Can we leverage multiple models to try to get rid of some of that bias? Another is the harness. If the harnesses are the same, we could have some bias there.
</details>

我们非常希望能替换掉所有这些组件，甚至可以构建对抗性审查器，让它们有能力审查同一份代码，看看在发现的问题上是否存在差异。如果我们发现的是同样的问题，那大概率是一个强信号，表明事实确实如此；如果我们发现的问题完全不同，那可能就值得进一步调查了。

<details>
<summary>Original English</summary>
We would love to be able to swap out all of these or even make adversarial reviewers um that have the ability to look at the same code and see if there's differences in what we're finding. If we find the same thing, probably high signal that that's that's true. If we find completely different things, then it might be worth further investigation.
</details>

### 从事后复盘到组织智慧的自动化沉淀

太棒了。最后一点，我们如何获取这个具体例子的信息，并确保类似问题不再发生？我知道和我合作的许多机构都会做复盘审查（postmortem reviews），这些非常有价值。我们会从中吸取教训。很多时候我们学到的东西与代码毫无关系，而是与我们必须推行的组织架构变动或流程变更相关。但对于代码层面的变更，我们如何将其带回来，并以自动化的方式将那些实际的隐性知识沉淀为每个人都能使用的组织知识呢？这也是一个巨大的领域。

<details>
<summary>Original English</summary>
Awesome. And then lastly, how do we take this information from this specific example and make sure that it doesn't happen again? Uh I know a lot of organizations that I work with will do postmortem reviews and these are valuable. They'll we learn from it. Often we learn things that don't have anything to do with code, but have to do with organizational changes or process changes that we need to do. But for the code level changes, how do we bring that back in and make that actual tribal knowledge a organizational knowledge that everyone can use goes in automated fashion. And this is a this is a huge area as well.
</details>

大家可以在这里的示例中看到，例如 Codo 根据 PR 上的评论建议了一条规则。这样一来，我们就可以返回去，并在未来的每一个 PR 中应用该规则。大家还会看到，因为我们拥有软件图谱信息，我们能看出那一行代码变更的爆炸半径非常大，我们就可以向审查者（无论是人类还是另一个智能体）标出这一点，确保大家对这里审查得更仔细一些。

<details>
<summary>Original English</summary>
You can see in this example here uh Codo, for example, suggesting a rule based on a comment on a PR. So, that way we can go back and now apply that rule to every PR in the future. Uh you'll also see that because we have that software graph information, we can see the blast radius of that one line of code change was large, we can flag that to the reviewer, whether that's a human or another agent, to make sure that we're looking at this a bit closer.
</details>

因此，我想至少从高层次的视角展示一下我们所讨论的内容。每个软件工厂中都涉及到很多事情。上下文才是王道。那么，我们能否获取正确的数据和正确的信息？我们能否应用那些我们可能已有的规则或标准，或者我们想要从中学习的规则？然后我们能否利用 MCP、CLI 在 PR 之前进行检查？在 PR 阶段能捕获问题固然很好，但如果我们能够更早地捕获它，那么也许我们就能在代码生成阶段将其拦下，或者有能力从那里进行修复。我稍后会现场演示一点，但我只想至少展示一下我们的思路，以及我们看到客户是如何构建他们的软件工厂的。

<details>
<summary>Original English</summary>
So, wanted to show this at least from a a uh you know, high-level view of what we're talking through. There's a bunch of things involved in each software factory. Context is going to be king. So, can we get the right data, the right information? Can we apply those rules or standards that we may already have or ones that we want to learn from? And then can we check this pre-PR using MCP CLI like there's great things to catch at the PR level. However, if we could have caught it earlier, then maybe we could have caught it at the code gen stage or have ability to remediate and go from there. Um I'll show a little bit of this live, but I just wanted to at least show some of what we're thinking, how we've seen customers building out their software factories. Um
</details>

想知道目前为止大家有没有什么问题？我很乐意停顿一下，不过对大家来说这看起来是怎样的？您刚才是在举手吗？

<details>
<summary>Original English</summary>
curious if there's any questions so far. I'm I'm happy to pause, but um what what does this look like for you guys? Were you Were you raising your hand?
</details>

### 现场互动：需求意图偏差与周期性审查

>> 是的。

<details>
<summary>Original English</summary>
>> Yeah.
</details>

>> 好，请讲。

<details>
<summary>Original English</summary>
>> Yeah, go for it.
</details>

>> 那么，在 PR 阶段——

<details>
<summary>Original English</summary>
>> So uh during the PR stage
</details>

>> 好的。

<details>
<summary>Original English</summary>
>> Yeah.
</details>

>> 我们会进行一次审查。或者说，我和智能体一起进行审查。我告诉智能体：“嘿，我想修改 XYZ。我想加载一些关于代码库的问题，之前是什么……”然后我会进去补充一些文档。基本上就像你所说的那样，它会在软件工厂的下一次运行中被应用。

<details>
<summary>Original English</summary>
>> Uh we go through a review. Or I go through a review with the agent. I tell the agent, "Hey, I want to change XYZ. I want to load some questions about the code base, what was Um and then I go in and I fill in some documentation. Basically what you're saying where it'll get applied on the next run of the factory.
</details>

>> 是的。

<details>
<summary>Original English</summary>
>> Yes.
</details>

>> 所以，你们现在把所有那些都做进去了，对吧？

<details>
<summary>Original English</summary>
>> Uh so you're you're doing all that then, right?
</details>

>> 没错。是的，我们能够将其引入进来。所以我刚才展示的只是我们所做功能的部分示例，我主要聚焦在软件图谱和自定义规则上。我们还可以引入很多其他内容，比如工单系统之类的。

<details>
<summary>Original English</summary>
>> Yep. Yeah, we're able to to bring in So I'm I'm showing just some some examples of what we do and I'm kind of focusing on the software graph and the custom rules. Uh we can bring in a bunch of other things like ticketing systems, things like that as well.
</details>

>> 你是否发现大部分客户甚至在代码编写出来之前，在意图层面就存在问题？

<details>
<summary>Original English</summary>
>> Do you find that most of your clients have problems with intent on before the code gets even written?
</details>

>> 是的。如果我们回到这里关于工单的这个环节，对吧？可能工单写得并不是特别好。你指的是这个意思吗？

<details>
<summary>Original English</summary>
>> Yeah. So if we go back to this section here on the uh the ticket right here, right? Maybe the ticket isn't written super well. Is that Is that kind of what you're describing?
</details>

>> 可能是，或者——

<details>
<summary>Original English</summary>
>> Maybe or
</details>

>> 好的。

<details>
<summary>Original English</summary>
>> Okay.
</details>

>> 或者是无论为了生成实现阶段而产出的上下文是什么，这两者之间的关联缺少了真正的意图，所以它学到了错误的东西。

<details>
<summary>Original English</summary>
>> whatever context is produced to generate the implementation aspect. Um the linkage between those two is missing the real intent and so it's learning the wrong the wrong thing.
</details>

>> 引导它。对它进行引导。所以你的意思是智能体会开始偏离，比如我认为很多人都经历过这些智能体的**过度工程化**问题：我让它做一件事，结果它现在就像是要从头把所有东西全重写一遍。你描述的是这种类似的情况吗？甚至可能……

<details>
<summary>Original English</summary>
>> Guiding it. Guiding it. So you're saying like the agent can then start going like I think one of the that maybe a lot of people experience is the over-engineering of some of these agents where I asked it to do one thing and it's now like recreating everything from scratch. Is that kind of what you're describing there? And maybe even
</details>

>> 我们处理问题的方法完全不对。可能纯粹就是……

<details>
<summary>Original English</summary>
>> We're approaching the problem incorrectly. It just could be
</details>

>> 完全错误。所以甚至不是过度工程化，而是纯粹搞错了。是的。对于 Codo（Qodo），我甚至可以在这里现场演示一点。如果我进入系统，我们集成了诸如 Jira 工单或 Linear 工单之类的工具，然后这些内容会进入每一个 PR 审查中。比如如果我打开这一个，大家可以看到这里我们直接将工单链接了进去。

<details>
<summary>Original English</summary>
>> Totally incorrect. So not even over-engineering just just just wrong. Yeah. So Coda I can maybe even show a little bit of this live here. If I go in we've got integrations with things like Jira tickets or linear tickets and then these will go into every PR review. So if I go to like this one for example, you can see here we'll link in tickets directly into it.
</details>

>> 哇。

<details>
<summary>Original English</summary>
>> Wow.
</details>

>> 当你从深色模式切换到浅色模式时，确实会觉得眼前一亮。大家可以看到这里有验收标准，然后如果我返回到审查——如果我回到这里，你会看到我们实际上会根据刚才看到的那个工单**标出需求缺口**。所以当我们讨论 Codo 时，我们不仅关注那些表面事项，更在审查我们是否完成了工单要求？我们是否真正深入到了细节中？因为我们可以在 PR 之前做这项审查，所以我们实际上可以引导智能体。通常我们与客户合作时的做法是：建议定期运行审查。因此我们经常会在里面放置一个技能（skill），声明在生成代码达到大约 25%、50%、75% 的进度节点时，执行一次审查以确保我们走在正确的轨道上。正如我之前提到的，上下文窗口会开始缩减，所以像这种情况，如果我切到这个界面，这个专门的审查智能体在某种程度上可以充当管理智能体，引导智能体避免走偏、避免过度工程化或出现类似问题。这有助于回答刚才那个问题吗？

<details>
<summary>Original English</summary>
>> When you go when you go from dark mode to light mode you really get you get blasted there. You can see there's acceptance criteria in here and then if I go back to the review if I go back here you'll see that we actually will highlight requirements gaps based on that ticket that we just saw. So this is when we're when we're talking Coda we're not looking at just those things but we're looking at are we completing the ticket? So are we actually going down that that rabbit hole? And because we can do this review PR pre-PR we can actually guide the agent. So typically what we'll do when we work with clients is we'll say run a review periodically. So we'll often put a skill in there which says as we're generating code about at your 25% your 50% your 75% mark go ahead and run a review make sure we're on the right path. As I mentioned that context window earlier starts to shrink and so like this is one of those things where if I go to this one this specialized review agent can act as almost a manager agent in this way of guiding the agent from doing the wrong thing or over engineering it or things like that. Did that help answer that question there?
</details>

后续如果有需要，我们可以进一步讨论。好的。太棒了。还有其他问题或想法吗？只是随口问问。好的。太棒了。

<details>
<summary>Original English</summary>
And then maybe maybe further that we need to talk through it. Okay. Cool. Any other questions, comments? Just curious here. Okay. Awesome.
</details>

我们稍后会在楼下的展位——Codo 的展位上。我很乐意和大家进一步探讨。我认为我们的很多客户都在朝这个方向迈进：即如何让这个软件工厂运转起来？而至少我们平台正在解决的关键环节就是审查阶段。我们如何为人类提供尽可能多的信息？我们如何将这个上下文层、代码智能与智慧层引入到审查智能体中，使其尽可能精准？因此，我认为我们接下来的发展层面在于：哪些改动可以在无需人类审查的情况下直接合入。我认为今天大家已经在这样做，而我们希望明确哪些应该直接合入、哪些不应该。所以，关于爆炸半径的信息在系统中都是随时可查的。

<details>
<summary>Original English</summary>
We'll be at the booth downstairs the the code of booth. I'm happy to talk through it with you guys further. I think a lot of our our clients are getting towards this how do we make this software factory run and the critical section that at least our platform is solving for is that review stage. How do we give the human as much information? How do we bring this context layer this code intelligence and wisdom layer into the review agent to make it as accurate And so then I'd say that the next layer of where we're going is what ones can be merged without a human looking at it. I think today people are already doing that. We'd love to know which ones that we should which ones that we should not. And so that that blast radius information is available there.
</details>