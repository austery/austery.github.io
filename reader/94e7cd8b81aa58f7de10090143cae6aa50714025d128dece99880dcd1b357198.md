---
author: How I AI
date: '2026-05-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Qrpm7E80wQ0
speaker: How I AI
tags:
  - html-artifacts
  - agentic-workflows
  - compute-allocation
  - spec-driven-development
  - human-in-the-loop
title: 为什么 Anthropic 工程师使用 HTML 文件作为 AI 技术规格
summary: Anthropic 的工程师 Thariq Shihipar 解释了为什么 HTML 正在取代 Markdown，成为与 AI Agent 交互的更优选择。他认为，尽管 AI Agent 的能力越来越强，但编写清晰的计划（Spec）和让人类保持在循环中（human-in-the-loop）仍然至关重要。HTML 作为一种更丰富的沟通媒介，不仅能让 Agent 生成可交互、可视化的计划、原型甚至定制化 UI，也使得开发者自己更愿意阅读和参与其中，从而提升了最终产出的质量。这种方法将开发者转变为“计算资源分配者”，其核心任务是通过高质量的规约来决定宝贵的计算资源应该花在何处。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - Celigo
  - Persona
products_models:
  - Claude Code
  - Claude 3.5 Opus
media_books: []
status: evergreen
---
### HTML 是新的 Markdown

**Claraveo**: 欢迎回到 How I AI。我是 Claraveo，一位产品负责人和 AI 爱好者，我的使命是帮助你用这些新工具更好地构建产品。最近，我有幸参加了 **Anthropic** 的首届开发者大会 **Code with Claude**。期间，我与在 **Claude Code** 团队工作的 **Thariq** 聊了一会儿，他教我的东西自从我听到后就一直震撼着我。**HTML** 是新的 **Markdown**。他将向我们展示如何使用 Claude Code 生成丰富的交付物，让你和 AI Agent 都能享受工作的过程。让我们开始吧。

**Thariq**: 谢谢你的邀请。

**Claraveo**: 我很高兴能来到旧金山的 Code with Claude。今天宣布了很多激动人心的事，我们稍后会谈到。但你今天告诉我一件我完全没想到的事，那就是——大家注意了，独家新闻——HTML 是新的 Markdown。给我们多讲讲吧。

**Thariq**: 我觉得 Markdown 成为与 Agent 交互的一种非常流行的方式，尤其是像 Opus 4 和 **Claude 3.5** 这样的模型。它们会制定计划，比如如何实现某个功能，计划可能有 50 行代码，你可以编辑它。我想那时候你还会阅读所有输出，编辑 Markdown，把它弄对。但随着 Agent 运行时间越来越长，当你使用 Opus 4.5 和 4.7 时，它们会运行一个小时左右，计划变得非常长，老实说我已经不读了。但这其实是个错误。我认为你仍然需要真正地参与其中，你需要真正理解 Agent 在做什么。但是一个上千行的 Markdown 文件，我甚至都懒得编辑了，我只会让 Claude 去编辑它。

<details>
<summary>Original English</summary>

**Claraveo**: welcome back to how I AI. I'm Claraveo, product leader and AI obsessive here on a mission to help you build better with these new tools. Recently, I was able to attend Code with Claude, Anthropic's first developer conference. And as part of that, I got to spend a little time with Thoric, who works on Claude Code, and taught me something that has blown my mind ever since I heard it. **HTML** is the new markdown. He's going to show us how to use cloud code to generate rich artifacts that both you and the agents can enjoy working on. Let's get to it.

**Thariq**: Thanks for having me.

**Claraveo**: I am so excited to be here at Codewith Claude in San Francisco. There's a lot of exciting things that were announced and we'll get to that in a little bit. But you told me something I was not expecting to hear today which is you heard it here first. HTML is the new **markdown**. Tell us more.

**Thariq**: I mean I think markdown became a really popular way of interacting with agents especially like you know Opus 4 and cloud 3.5 where you know they have a plan and the plan is like how to do this feature and maybe it's like 50 lines of code and you can edit it right like I think back then you were still like reading all the outputs and editing the the markdown and making it right but you know as the agents have gotten longer and longer running when you have Opus 4.5 and 4.7 they're running for like an hour or something and the plans are so long I honestly have stopped reading them and this was honestly a mistake. Like I think that you still need to be really in the loop. You really need to understand what the agents are doing. Uh but like a thousandline markdown file, you know, I don't even edit them anymore. I just ask Claude to edit them instead.

</details>

**Thariq**: 所以我发现在 Claude Code 团队中，我们开始使用 HTML 文件来代替。模型对 HTML 的处理能力依然非常出色。它们现在有了更多的上下文，所以你可以多花点 tokens，而且 HTML 更易于阅读，可以承载更多信息，也更容易滚动。当你谈到实现时，有时你会看到 Claude 制作那些小小的 ASCII Markdown 图，它真的很努力。但在 HTML 中，它就不用那么费劲了，它可以实际绘制出你能看懂的东西。所以这只是你和 Claude 之间一种更丰富的沟通媒介。

<details>
<summary>Original English</summary>

**Thariq**: And so I think one of the things that I've been seeing emergently in the cloud code team is that like they that we're using HTML files instead. And so HTML is like the models are still very good at it. They have a lot of more context now. So you can spend the more extra tokens and they like it's a lot easier to read like they can uh have a lot more information. They're a lot scrollable more scrollable. And when you're talking about implementation like you know sometimes you see claude make these like little asky markdown things where you're like oh like here's a little you know little mockup and it's trying really hard. in HTML it doesn't need to try nearly as hard right like there uh it can actually draw like things that you can look at and so it's just a richer communication medium between you and quad

</details>

### 计划与技术规格的重要性

**Claraveo**: 在我们深入探讨 HTML 之前，我必须暂停一下，因为我对此有切身利益。你是在告诉那些没在听的人，听好了：**计划很重要，PRD 很重要，技术规格很重要**。即使这些模型变得越来越智能，你仍然觉得这是流程中非常重要的一部分。

**Thariq**: 哦，百分之百是的。我认为这将永远是事实。因为当你说，好吧，Claude 可以运行八个小时，你实际上是在说，Claude 可以花掉 500 美元。我们所有人都正在成为**计算资源分配者**。所以你必须决定什么事情值得花费这些计算资源。

<details>
<summary>Original English</summary>

**Claraveo**: and before we go further into HTML specifically I do have to pause because I do have a vested interest in this which is you are saying for the people who are not listening listen up: **plans matter, PRDS matter, spec matters**. even as these models get more intelligent you still feel like that's a really important part of the process

**Thariq**: oh 100% yeah I I think that you know everyone has different views on how it'll go but I I think that this will just forever be the thing because when I you say okay cloud can run for eight hours what you're really saying is cloud can spend like 500 bucks you know what I mean and and so if you're spending 500 bucks or like I think all of us are becoming these **compute allocators** now right and so you have to decide like what is worthwhile spending the compute on.

</details>

**Thariq**: 我认为这发生在规格和规划阶段。你必须真正理解你想要什么。有时你并不知道，需要通过与 Claude 聊天来挖掘出来。有时你有一些未知的未知需要去搞清楚。但我认为，现在整个事情就是真正与 Claude 就它要构建的东西达成同步。

**Claraveo**: 我喜欢你的说法，因为人们总是问我：“Claire，你说产品管理已死。那接下来是什么？” 我会说：“宝贝，你现在是计算资源分配者。” 这就是现在的工作。你做的事情还是一样的：你编写文档来决定别的东西是否应该做某项工作，以及工作的形式。

<details>
<summary>Original English</summary>

**Thariq**: and I think that is happens in the spec and planning phase right you have to really understand like what do you want? And sometimes you don't know. Sometimes you have to like pull it out of yourself by chatting with Claude. Uh sometimes you have like unknown unknowns you need to figure out. Uh but yeah, I think this is like the whole thing now is just like really getting in in sync with Cloud about what it's building.

**Claraveo**: I love what you said because people ask me all the time, Claire, you said product management is dead. What's next? I'm going to say you're a compute allocator, babe. Like that's that's the job now. You're still doing the same thing, though. You're writing documents to decide whether or not something else should do do work in the shape of that work.

</details>

### HTML 作为更优的人机交互界面

**Claraveo**: 好的，你已经说服我 HTML 是未来了。我喜欢你的说法：这不一定是因为 Agent 阅读 HTML 更难或更容易——它们非常聪明，能读懂各种代码——而是因为你发现 HTML 让你更容易地与内容互动。这反过来全面提升了质量，因为你的眼睛不会因为看一堆原始的 Markdown 而疲劳，然后想“管它呢，可能还行”。相反，你实际上被吸引到规格、文档或计划中，并以一种能提升质量的方式与之互动，最终你能构建出更好的东西。

**Thariq**: 是的，没错。

<details>
<summary>Original English</summary>

**Claraveo**: Okay. So, you've convinced me HTML is the future. And I I like how you said this. It's not that it is necessarily harder or easier for the agents to read. They're very smart. They can read all sorts of code. But in fact, what you're finding is that HTML makes it easier for you to engage with the content, which then uplevels the quality overall because you're not your eyes aren't crossing looking at a bunch of raw markdown, being like whatever, it's probably good. Instead, you're actually getting pulled into the spec or the document or the plan and then interacting it with a way that upgrades the the quality and then you can ultimately build something better.

**Thariq**: Yeah, that's right.

</details>

**Claraveo**: 好的。所以，你正在和 Agent 一起构建一些东西，以便 Agent 可以管理你。

**Thariq**: 我不确定“管理我”是否准确，但我非常关心与 Agent 保持同步。我在 Claude Code 中构建的功能也都是如此，就是“我怎样才能更好地了解你？”

<details>
<summary>Original English</summary>

**Claraveo**: Okay. So, you're building something with the agent so the agent can manage you.

**Thariq**: You know, I'm not sure if manage me is the right word exactly, but you know, I just I care a lot about being in sync with the agent. This is sort of like the features that I built in Cloud Code have been like that, you know, like how can I get to know you better? So, yeah.

</details>

### 使用 Claude Code 生成 HTML 交付物

**Claraveo**: 好的，太棒了。我们已经打开了 Claude Code。让我们来看看它是如何工作的。

**Thariq**: 好的。我在开始前做了一点准备。我喜欢像和人一样与 Claude 交谈，而且我总是从头脑风暴开始。一旦你有了伙伴，头脑风暴就容易多了。所以我当时就说：“听着，我要上一个播客。我想做一个演示，你能在一个 HTML 文件里帮我头脑风暴一些点子吗？” 这就是我给它的提示，很简单。所以这里你可以看到它为我制作的八个可视化演示方案。它还有这些小模型图。比如，从纯文本到工作原型，它搜索了你的信息。从白板草图到工作 UI，我觉得这个非常酷。这个小东西太可爱了。

<details>
<summary>Original English</summary>

**Claraveo**: Okay, great. Well, we have we have Claude Code up. So, let's walk through how that how that works.

**Thariq**: Yeah. So, I I did like uh a little bit before we started uh and so I like to talk with Claude just as a human, you know, and like I always start with brainstorming. It's so much easier to brainstorm once you like, you know, uh once you have a partner. So, I was literally like, "Look, I'm on a Claro podcast. Um I want to do a demo, you know, and can you brainstorm some ideas in the HTML file, right?" And this is literally the prompt I gave it, right? Like there's not it's not complicated. And so here you can see the eight visual demos that it made for me. And uh it has these little mockups as well, right? So like purity to working prototype, right? Like it it searched you up, right? You saw that with a web search, right? Uh whiteboard sketch to working UI, which I thought was really cool. This is such a cute like little thing.

</details>

**Claraveo**: 它基本上没有说“这是一个 Markdown 文档，里面写了你应该和 Claire 谈什么，以及一些你可以做的事情的描述”，而是想“什么是传达这些信息的最佳方式，让你能真正参与并选择一些东西？” 于是它用 HTML 制作了这个可视化的指南，作为潜在的议程或一组演示。

**Thariq**: 你能得到更丰富的表达方式。

<details>
<summary>Original English</summary>

**Claraveo**: So it's giving you basically instead of saying here's a markdown document of kind of like what you should talk to Claire about and some descriptions of things you could do. Instead, it was like, what's the best way to convey this information so you can actually engage with it and pick something? And it used HTML to make this visual guide of a potential agenda or a set of demos

**Thariq**: and you just get like a much richer expression.

</details>

### 交互式计划与微型软件

**Thariq**: 是的。我选择了我最喜欢的“CSV 到交互式仪表盘”。

**Claraveo**: 我们都喜欢仪表盘。我以前在企业软件领域常说，现在也还在说，“仪表盘等于美元”。所以我喜欢这个。好的，所以你使用 Claude Code，你说头脑风暴，但在 HTML 中进行。它给了你八个想法，包括视觉效果和这个可爱的“为什么是她，视觉效果是什么”，还有风险。就像所有好的演示一样，可能会出岔子。然后你选一个，向我们展示如何将这个想法贯穿到一个完整的计划中。

**Thariq**: 没错。我喜欢 HTML 的地方在于 Claude 真的理解它。我接下来的提示是：“我要求它在后续提示中制作一些模型图，然后我让它就第八个想法采访我。” 这类似于规格和 PRD，找出我的未知未知。我回答了一堆问题，然后我说：“好吧，创建一个 HTML 文件作为计划，帮助我将实施计划可视化。包括摘要、模型图、代码，任何需要的东西，给我最大的上下文。” 然后它为我制作了这个 HTML 文件。你可以看到，这就是计划，但它完全是 HTML 格式。它甚至开始为播客本身编写脚本，虽然我可能不需要那么多，但它充实了文件系统，给了我 skill.md 的摘录，还整合了一个情绪板和一些示例组件，以及一些逻辑。它帮助我了解这里需要知道的重要事情。这是我真正会去读的东西。

<details>
<summary>Original English</summary>

**Thariq**: That's right. Yeah. So I I think the what I like about HTML is like really Claude really understands this. And so my next prompt here was really like okay uh I asked it to make some mockups in in the follow-up prompt and then I was like I asked it to interview me about number eight, right? And so this is something that like you know similar to specs and PRDs, right? Like uh finding out my unknown unknowns. What do I want it to do? I answered a bunch of questions and uh now I'm like okay create a HTML file as a plan that helps me visualize what the implementation plan is include excerpts, mockups, code when whatever is needed to give me like maximum context, right? Um and so then it made me this HTML file here. Yeah, you can see now this is this is the plan. Uh but it's it's purely in HTML. It's got like it started scripting out the podcast itself which you know maybe I I didn't need all of that but like you know we're making a skill and so it it you know fleshed out the the file system. It gave me like an exerpt of the skill.md um it put together like a a mood board as well some example components. um some of the logic here um yeah insights and templates helper scripts right and like helping me get a sense of like what's the important things for me to know here um yeah this is this is something that like I will actually read you know yeah

**Claraveo**: We love a dashboard. Uh I used to say when I was in enterprise, I guess I still am in enterprise software, dashboards equals dollars. So, I like this one. Um, okay. So, you use clog code. You said brainstorm, but brainstorm in HTML. Give me a couple things that I can talk about. It gave you eight ideas, including visuals and this lovely like why her, what the visual is, and then the I like the risk. It's like it could go sideways as all good demos Yeah. can. Um, and so you're going to pick one and then you're going to show us how you pull this through to a full plan on on on this idea.

</details>

**Claraveo**: 我想鼓励大家，不要太纠结于应该在里面放什么。实际上，它可能会因项目而异。让模型做它需要做的事，它会做得很好。

**Thariq**: 我认为提示是一种微妙的平衡。你想给足够的信息让你得到你想要的，但你又不想过度约束 Claude。所以当我看到人们有很多过度设计的技能时，比如“你是一位专家规划师”，那通常是外包了太多并且限制了它。但在这种情况下，我确实想确保它给我代码摘录。但我总是需要给 Claude 一个出口，比如“无论需要什么，给我最大的上下文”，这是我说“嘿，Claude，我相信你”的方式。

<details>
<summary>Original English</summary>

**Claraveo**: I do want to encourage people, you know, don't stress so much about what should go in the thing. And in fact, it might change initiative to initiative. It might be slightly different to engage you with the work, but like identifying what you want to get and then letting the model do what it needs to do will do a very high quality job.

**Thariq**: Yeah. I I think with prompting it's like this fine balance of like I think you want to give enough information that you get what you want but you don't want to over constrain claude you know and so sometimes when I see people with a lot of like overbuilt skills kind of like you know you're an expert planner or something right like that is usually like outsourcing too much and constraining it. um but in this case for example like I really did wanted to make sure it gave me code exerpts and I wasn't sure if I did uh whether it would do that you So this was really important. But then I always need to give Claude an out, you know, I always needed to be like, "Okay, like you asked me for this, but you know, like there's something else I want to give you." And so whatever is needed to give me maximum context is like my way of saying like, "Hey, Claude, like I I trust you here. I want to just like be in the loop with you."

</details>

**Claraveo**: Markdown 很方便，我可以进去打字、编辑。这也是它如此受欢迎的原因之一。但这个 HTML 我该怎么修改？

**Thariq**: 这是个好问题。对于 Markdown，因为我已经不读了，所以也不再编辑了，最后都是让 Claude 去编辑。所以最基本的形式就是：“嘿 Claude，我不喜欢计划的这部分，你能改一下吗？” 但假设你想真正深入参与，Claude 也能帮你。我接下来的提示是：“我想创建一个可编辑的 HTML 交付物来帮助我定义决策规则。” 我对现有的规则不满意，所以让它为我设计一个理想的界面。我真的不确定它会给我什么，这也是 HTML 的乐趣之一。然后，它给了我这个，一个漂亮的自定义界面。我可以编辑任何字段，隐藏它们，复制，添加新字段，它还给我一个可以复制回去的 Markdown。

<details>
<summary>Original English</summary>

**Claraveo**: Markdown is accessible, right? I can like go into Markdown, type in it. And make edits. And so, I think that is one reason is it has been so popular. How like I want to fix this. How do I how do I touch this? How do I edit this?

**Thariq**: Yeah. Yeah. So, I I think that this is like a great point, right? And I think one thing I felt with Markdown was that one I because I had stopped reading them, I had stopped editing them as well, you know, and so I would end up asking Claude to edit them. And so like that is like the most basic form is just to be like, "Hey Claude, I didn't like this part of the plan. Can you edit it? Uh, but let's say you want to get really in the loop, right, and like really get in depth with it. Claude can also do that for you. So, the next prompt I had was "Okay, I want to create an editable HTML artifact to help me define the the decision rules." I don't like the ones we have right now. Make this a custom UI that helps me with structure but gives me flexibility. Design the ideal interface for this problem. I really wasn't quite sure what it would give me. And this is one of the fun parts of HTML 2. It's just like I just want to see what what cloud like cooks up here. And um, yeah, this is what it gave me, right? So it's like a my own beautiful custom interface. Um, I can sort of like, you know, edit any of these fields. Uh, I can, you know, like hide them. I can copy. I can, you know, add new fields here. Um, and it gives me a markdown to to copy back.

</details>

**Claraveo**: 我要重复一下你刚才做的事情。你有一个 HTML 计划，里面有一个关于渲染和可视化规则的特定表格。但你觉得不满意。你没有在终端里来回编辑，而是说：“可能有一种更理想的方式来处理这个问题”，然后基本上让它构建一个**一次性的 UI**。这甚至不是个人软件，这是**微型软件之上的微型软件**。我制作了一个高度个性化的计划，然后我正在用一个非常定制化的 UI 来放大这个计划中的一个模块，以获得更高质量的内容。

**Thariq**: 是的。

<details>
<summary>Original English</summary>

**Claraveo**: Okay. I want to pause because people are going to totally miss what you just did. So, I'm going to repeat it, which is you have this HTML plan. And there's a section in the HTML plan that is a pretty like specific table of rendering and visualization rules. And you're like, I don't like it. And instead of going back into cloud code and being like, I don't like it. Let's go back and forth and edit it in like the terminal, you said, there's probably a way for me to interact with this p particular problem that's ideal from a user perspective. So basically build a **throwaway UI**. This is not even personal software. This is like **micro software on top of micro software** which is like I've made this very personalized plan and then I'm taking a module in the personalized plan and zooming into it using a very custom UI.

**Thariq**: Yes.

</details>

### HTML 作为协作和文档化的新范式

**Claraveo**: 这就是你现在的工作方式吗？在协作方面有挑战吗？

**Thariq**: 实际上是的。对于实施计划来说，这好多了。你可以把它上传到 AWS 之类的地方，然后分享链接。Cat 或 Boris 阅读这个的可能性要高出一百倍。我也在协作中大量使用它。例如，我每周都会用 HTML 格式向我的经理 Cat 发送一份周报，汇总我所做的一切。我让 Claude 读取我的 Slack，然后创建这个消息，她真的会读，而且我不用花太多时间。

<details>
<summary>Original English</summary>

**Claraveo**: So fun. Is this how you're building now? And do you have any challenges with like how are you passing this around from a collaboration perspective?

**Thariq**: Actually, it is. on the scale of an implementation plan it's way better, right? And I think that this is cuz you just like can upload it to like you know whatever AWS or something and then you just share the link around and so definitely the likelihood of like I don't know cat or Boris like reading this is like a hund times better right. I also just you know somewhat related I use it a lot in like collaborating overall. So, for example, uh you know, I report to cat and so like every week I send her a weekly status update in HTML of everything I've done. I get Claude to read my Slack and just like create this message and and like she actually gets to read it and I don't have to spend that much time on it, you know?

</details>

**Claraveo**: 我喜欢这一点，因为我从事产品工作很多年了，人们过去常常纠结于我们的技术规格和 PRD 的“唯一真实来源”在哪里，是否都集中在一个地方，格式是否统一。这些武断的规则存在，因为创建这些内容的成本相对较高。现在所有成本都趋近于零，你可以把东西放在任何地方，用任何格式，因为我们知道这些模型非常擅长使用工具来发现它们需要的上下文。

**Thariq**: 我会把这个 HTML 计划作为一个交付物。我会清空上下文然后说：“这是一个计划，实现它。” 你也可以用它作为检查事实的来源。HTML 的一个好处是我这里也有一个小模型图。所以我可以让验证 Agent 检查：“嘿，我原本打算做什么？实际输出是什么？” 这真的帮助 Claude 更好地参与进来。

<details>
<summary>Original English</summary>

**Claraveo**: I like this because I've been in the in the product game for quite some some time, many decades. And people used to get so wrapped around the axle on like what's our source of truth for specs and what's our source of truth for PRDs and you know is all this information in some centralized place that we can all access it and is it all in the same format? Is it all in the same template? And there were these arbitrary rules because creating this content was relatively expensive. when all of that cost goes to like functionally zero, you can kind of put stuff wherever in whatever format because we know these models are very good at using tools to discover the context that they need.

**Thariq**: Yeah, I I think so. I I didn't uh hit implement on this but yeah, I would basically use this as an artifact. And so, um, I would clear context and I would say like here's a plan. Um, you know, implement it. Uh, you could also have like you can also use this as a source of checking the truth, right? And so again, a benefit of HTML is like I've got a little mockup here as well. So, right, I can have the verification a or I can have the verification agent check like, hey, what did I intend to do, right? And what actually came out in the output, right? Um, so yeah, I think this is like really uh helps cloud be more in the loop.

</details>

### 动态设计系统

**Thariq**: 我最喜欢的一个例子是这个“**动态设计系统**”。比如，当我在 entropic 设计系统中创建一个新应用时，Claude Design 做得很好，你链接一个 GitHub 仓库，它就会从中提取设计系统。我做的是，我有一个代表我设计系统的 HTML 文件。你可以看到颜色、排版、间距、半径、核心组件。一旦我有了这个，我就可以开始到处传递它。我去一个新项目，就用 `design_system.html`，而不是 `design.md`。它有一个压缩的理解。

<details>
<summary>Original English</summary>

**Thariq**: one of my favorites is this living design system. And so it's this idea that like you know oftent times when I am making let's say a new app in the entropic design system, right? Like Cloud Design does this very well. You link a GitHub repo and you uh like it will extract the design system from it. what this does is like basically I have an HTML file that represents my design system. You can see the colors here, typography, spacing, radius, core components, right? Once I have this, I can basically start passing this around. Yeah. So, I go to a new project. I'm like design system.html, right? Instead of like design.md or something. And it's got this like compressed understanding.

</details>

**Claraveo**: 我喜欢这个。我也这么做。我用 Claude Design，拉取我的营销网站仓库和应用仓库，它们有相同设计系统的一些表达。我说“制作设计系统”。然后我让它在组件层面制作一个风格指南，因为在特定组件中实现设计系统时会有一些调整。然后我把它放到仓库里，然后说“参考设计系统”。更高级的做法是，我有一个组件可视化页面，展示我们应用的 25 个组件的实际运行和交互。这样营销人员就可以进去，以“看起来真实”的形式获取组件，然后下载一个透明的 PNG，放到幻灯片或视频里。

<details>
<summary>Original English</summary>

**Claraveo**: I love this. I do this as well. I will give you my um like advanced mode version of this, which is I use claw design. I pull in my both my marketing site repo and my app repo which have like some expressions of the same design system in I say make the design system. Then I actually make it ask ask it to make a design system or a style guide but I want it at the component level. and then I drop that into the repo and then yes I say exactly this um reference the design system. The advanced thing that I do that I think is really useful for people who have to interface with marketers is I um have a like what I call a component visualization page which is like the 25 components of our app in action and interactable in a page. So a marketer can go in and like get the get the component in the form factor it needs to look quote unquote real. And then you can download a transparent PNG. And like drop it in a deck or drop it in a video.

</details>

**Thariq**: 这里还有一些关于组件变体的东西，我觉得也很有趣。你创建一个组件，你想看看如果改变内边距或边框会怎么样。这些都是玩转这个的简单方法。这也像 Claude Design，你创建这些小旋钮和滑块。你可以想象，这就像是“你正在做的事情的界面是什么？”以及“你如何将其可视化？”在美观和 Claude 的理解之间没有权衡，它们是同一件事。

**Claraveo**: 是的。总结一下：打开 Claude Code，让它用 HTML 给你头脑风暴一些想法。选择一个想法，用 HTML 规划它。选择你不喜欢的部分，让它创建一个微型应用来用 HTML 编辑它。额外的好处是：使用 Claude Design 制作一个设计系统，不仅如此，还用 HTML 在你的仓库中编码该设计系统，以便随时引用。`design.md` 已死，`design.html` 永存。我说对了吗？

**Thariq**: 是的，我认为是这样。

<details>
<summary>Original English</summary>

**Thariq**: there's also something here around like component variations, which I thought was um fun where it's like Yeah. like you you create a component, you want to see like, oh, like what if I change the padding or what if I change the border, you know, solid things like that. like these are like a pretty simple like you know uh way of just playing with this. This is also claw design like right like where you create these little components and or these little knobs and sliders. Um but yeah you you can imagine one this is like the abstract of like oh like what's the interface for this thing that you're trying to do and how can you visualize it and yeah there's not a trade-off between like being nice pretty for you and understand being nice for Claude you know like they're They're really the same, right? So,

**Claraveo**: Yes. So, just to wrap for people, pull up Cloud Code, ask it to make you give you some ideas. Brainstorm ideas, but brainstorm them in HTML. Pick an idea. Plan it in HTML. Pick a part of that idea you don't like, have it create a micro app to edit it in HTML, and then some like bonus things is use cloud design, make a design system, but not only that, use HTML to encode that design system in your repo so it can be referenced at any time. design.mmd is dead. Long lived design.html. Did I get it right?

**Thariq**: Yeah, I think that's right. I think that's right.

</details>