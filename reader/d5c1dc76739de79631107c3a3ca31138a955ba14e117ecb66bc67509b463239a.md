---
author: How I AI
date: '2026-08-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=o_eg2TtXAO0
speaker: How I AI
tags:
  - ai-agent
  - workflow-automation
  - intent-engineering
  - prompt-engineering
title: Claude 编程与智能体：普通人如何用 AI 改变日常工作流
summary: 本期访谈由 Clarvo 对话 AI 教师及前营销顾问 Grace Clark，深入探讨了普通人及小企业主如何利用 Claude 进行日常工作流的重新设计与重构。Grace 展示了她如何通过口述 SOP 让 Claude 逆向生成可视化 HTML 客户提案，以及如何基于 frustration 重建定制化的 Gmail 替代品。同时，她分享了将大段意图转化为与 AI 持续协作的“意图工程”理念，并提出了通过截图与 Slack/日历提醒强制构建 AI 肌肉记忆的日常习惯培养法。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
products_models:
  - Claude
  - GPT-5
media_books: []
status: evergreen
---
### 意图工程与日常工作

**Clarvo**: 提示词工程已死，意图工程才是我们需要将时间集中的地方。我在散步和外出的路上做很多工作。我讲了大概两到三分钟，只是说：“这是我的问题。” Claude 回复我并说：“我认为我们需要创建一个受密码保护的交互式工件。” 这是一个提示词从超工程化（hyper-engineered）的文本块，演变成三到四分钟的长对话的过程。Claude 需要从你身上引导出这个提示词。

对于像我这样讨厌电子邮件的人来说，在个人层面上你还有另一个例子。Gmail 对我们做了什么？

<details>
<summary>Original English</summary>

**Clarvo**: Prompt engineering is dead, but intent engineering is where we need to be focusing our time. I do a lot of work when I'm walking and on the go. And I spoke maybe for two or three minutes and just said, "Here's my problem." Claude came back to me and said, "I think we need to be creating an interactive artifact that's password protected." That is a prompt going from a hyperengineered chunk of text to a conversation that's 3 or 4 minutes. Claude needs to get the prompt out of you. You have another example at the personal level as a fellow email hater. What did Gmail do to us?

</details>

**Grace Clark**: Gmail 做了什么？

<details>
<summary>Original English</summary>

**Grace Clark**: What did Gmail do?

</details>

**Clarvo**: 我知道它曾经是非常棒的。但现在就像每个人都有你家前门的钥匙，可以随时进来把东西丢在你家里。我不想再这样了。我想让你看看我纯粹出于挫败感而建造的东西。发送到 Gmail。这会把内容推送到 Gmail 的草稿箱，然后希望它能打开浏览器窗口，走完最后一英里。这基本上带我去了我想去的地方，因为我可以在这里和 Claude 聊天、工作，让它起草好回复，或者我可以一键发送，以后再也不用管它了。

我的工作就是坐在你的肩膀上，每当你打开 Slack、Gmail 或者谷歌日历时，就拍打你的手说：“不，用 Claude。人们需要感受到好处，才会继续使用它。” 

但事实上，并非如此。相反，人们大多需要理解我们是要学习如何共同协作。真正需要跨越的障碍是默认使用它，并建立起简单地打开这个应用程序的肌肉记忆。

欢迎回到《How I AI》。我是 Clarvo，一名产品领导者和 AI 狂热爱好者，我的使命是帮助大家利用这些新工具进行更好的构建。今天我们邀请到了 **Grace Clark**，她将向我们展示“给普通人用的 **Claude**”。不过，也不是完全给普通人的。而是给那些想要在客户、在他们堆积如山的收件箱面前，展现出只有 AI 智能体才能提供的极高个性化和专业水平的人。让我们开始吧。

本期节目由 **Bolt.new** 赞助播出。Bolt.new 是为有想法并想将其实装的普通人打造的 AI 应用构建平台。大多数 AI 工具吐出来的代码在演示时看起来很棒，但你一旦想用它做点实事就会立刻崩溃。或者它们会把你锁定在自己的平台上，无法导出。Bolt 则不同。你只需描述你想要构建的内容——无论是创业公司的 MVP、落地页、内部工具还是业余项目——Bolt 都会在几分钟内生成生产级别的代码。你可以连接 Stripe 或任何其他 MCP，绑定你的域名，然后直接上线部署。创始人正使用 Bolt 建立带来实际收入的业务；产品经理用它发布团队能切实使用的原型；设计师和市场营销人员无需排队等待开发排期即可发起营销活动。任何人都可以构建，工程团队可以快速出货。人人皆赢。你只需要一个想法和一个周末。去 bolt.new/howiAI 看看吧。

Grace，欢迎来到《How I AI》。

<details>
<summary>Original English</summary>

**Clarvo**: I know it was once upon a time amazing. It is like everybody has a key to your front door and can come leave things in your house. No more. I want to show you what I built out of pure frustration. Send in Gmail. This will push it to Gmail a draft and then hopefully open up a browser window and get it the extra mile. This gets me pretty much where I want to go because I can go back in here and work with Claude and chat and have the reply drafted or I can just send it and never have to deal with it again. My job is to sit over your shoulder and smack your hands every time you open Slack or Gmail or Google Calendar and say, "No, Claude. People need to feel the benefits in order to keep using it." That's actually not true. Instead, people mostly need to understand that we're going to learn to collaborate. The real hump to get over is defaulting to this and building the muscle memory of simply opening an app. Welcome back to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Grace Clark and she's going to show us Claude for normal people. But not really for normal people. For people who want to show up to their clients and to the many, many, many people in their inbox with a level of personalization and professionalism that only an AI agent can provide. Let's get to it. This episode is brought to you by Bolt.new, the AI app builder for people who have ideas and want to ship them. Most AI tools spit out code that looks great in a demo and falls apart the second you try to do anything real with it. Or they lock you into their own platform with no real way out. Bolt is different. You describe what you want to build, a startup MVP, a landing page, an internal tool, a side project, and Bolt generates productionready code in minutes. Connect Stripe or any other MCP, hook up your domain and deploy it live. Founders are using Bolt to build businesses doing real revenue. Product managers are shipping prototypes their teams actually use. Designers and marketers are launching campaigns without waiting in line. Anyone can build. Engineering can ship. Everyone wins. You just need an idea and a weekend. Check it out at bolt.new/howiAI. Grace, welcome to How I AI.

</details>

**Grace Clark**: 谢谢你邀请我。我对这一集感到非常兴奋，因为关于 AI 将如何影响我们的工作，我的核心假设之一是：它真的能让我们所有人在服务差异化上做得更好。我认为，服务、服务质量、客户关系以及整体人际关系的门槛都会提高，因为我们将能够做更多的事情，并为与我们合作、协作的人提供更高度定制化的体验。因此，我很喜欢你构建的一些东西。我想知道你是否能带我们了解一下，是什么让你开始这些你即将展示给我们的 AI 项目，以及你当时试图解决什么问题？

<details>
<summary>Original English</summary>

**Grace Clark**: Thank you for having me. I am excited about this episode because one of my hypotheses about how AI is going to like impact our work is it's really going to allow us all to differentiate on service a lot better. And I think the bar for service and service quality and customer relationships and human relationships overall will go up because we'll be able to do more and make things more customized for the people that we're working with and the and the people that we collaborate with. And so I love some of the stuff you've built. And I wonder if you could just walk us through what brought you to some of these AI projects you're going to show us and what problem you were trying to solve.

</details>

**Clarvo**: 我深信，只要我们肯投入精力，AI 正在使我们所有人的工作方式变得民主化。我当时一直在思考我可以在自己的业务中建立哪些不同的效率。我是一名 AI 教师，也是前营销顾问。因此，这是一个非常依赖关系、非常依赖流程的业务。我在一月份开始自学如何构建一个开放的 Claude 工作流。我在 Instagram 上分享了足够多的相关内容，以至于人们对我说：“你应该开个班。你似乎把这个过程记录下来了。这有一套流程。你愿意把大家聚在一个房间里做这件事吗？”

自学并构建课程的过程，现在成为了我教学的基础，也是我在课程中实际使用并构建的几个核心产品的原因。所以现在我构建了几个运行我业务的流程和产品，我实际上把这些教给我的学生，以及我培训的团队。

最显着的是我的**管道运营商（pipeline operator）**。这是因为它在底层解决了几个问题。

第一，就是应接不暇的电子邮件。电子邮件是一个祸害，没有人想再呆在 Gmail 里了。所以我的 Claude 正在接收所有这些邮件，并将其与一大堆上下文进行关联。

它解决的第二个问题是，客户关系和建立关系往往缺乏情感和爱意。因此，当我们能够通过 HTML、**交互式 HTML** 和加密文档来视觉化地表达这些时，它是一个非常温暖的欢迎，也是沟通流程中一种更友好、更殷勤的方式。

第三，我根本无法在任何一天跟踪 20 个打开的标签页，更不用说组织一个流程来支持人们、教授他们并在学习中支持他们了。因此，从 20 个标签页和每周花费 20 个小时进行行政管理，仅仅为了能够教学，这太痛苦了。我没能真正进行教学，我直觉地感到会有办法解决所有这些问题。我做的第一件事就是在下载了两个小时后打开了 **Claude Code**，把我刚才告诉你的所有内容都向它倾诉了一通。然后我坐下来，让 Claude 带我经历这个过程，并从一开始就学习如何与**智能体 AI（Agentic AI）**进行协作。现在我有一个每小时运行一次的管道，这可能是我教的最受欢迎的内容了。

太棒了。那么，我们能切实看看这长什么样吗？因为我认为有很多人拥有与你类似的业务，他们只是在寻找将这套流程融入自己工作流的实用方法。所以，我真的很想知道这东西实际上是如何运作的，从而获得一些启发。

<details>
<summary>Original English</summary>

**Clarvo**: I am a big believer that AI is democratizing the way all of us are going to work if we put in the work. And I was thinking about different efficiencies that I could build in my business. I'm an AI teacher and a former marketing consultant. So very relationship driven, very process driven business. And I started teaching myself how to build an open claw in January. And I was posting about it enough on Instagram that people said, "You should teach a class. You seem to be documenting this. There's a process. Would you ever want to get people together in a room and do it?" The process of teaching myself OpenClaw and building a curriculum is now the foundation of what I teach people and it's the reason I have a few core products that I've built that I actually use in my curriculum. So now I've built a few processes and products that run my business that I actually teach to my students and then the teams that I get to train. The most impactful is my pipeline operator. And that's because underneath it is solving a few problems. One, just a deluge of emails. Email is a scourge. Nobody wants to be in Gmail anymore. So my claude is ingesting all of that and correlating it with a bunch of context. The second problem it's solving is that client relations and relationship building is really devoid of any emotion and love. So when we can make visual expressions of that through HTML, interactive HTML and encrypted documents, it's a really warm welcome and it's a much more hospitable way to communicate process. And then third is I simply cannot keep track of 20 open tabs in any given day, much less organize a process where I'm meant to support people and teach them and support them through learning. So going from 20 tabs and 20 hours a week on admin just to be able to teach people was so painful. I wasn't doing the teaching and I just had a hunch that there was going to be a way to solve all these things. The first thing I did was open up Claude Code after having it downloaded for 2 hours and I yapped into it everything I just told you and I sat back and let Claude take me through the process and learned from the jump how to collaborate with Aentic AI and now I have a pipeline that runs once an hour and it's probably the most popular thing I teach. Amazing. So, can we actually see what this looks like? Because I think there's a lot of folks that, you know, have businesses similar to yours that are just looking for practical ways to integrate this into your flow. And so, I'd love just some inspiration on how this thing actually works.

</details>

### HTML 提案与客户端交互

**Grace Clark**: 你不需要运行这样一个完整的流程来让 Claude 或智能体 AI 按需支持你。它可以在没有所有底层逻辑的情况下生成一个提案。它看起来像这样。其核心是一个**技能文件（skill file）**，告诉 Claude 用 HTML 创建一个提案。而结果就是看起来像这样的东西。

<details>
<summary>Original English</summary>

**Grace Clark**: You don't need to run a whole process like this in order to have cloud or gentic AI support you on demand. It can generate a proposal without all of this underneath. It's something that looks like this. At the core of this is a skill file that tells Claude to create a proposal in HTML. And the outcome is something that looks like this.

</details>

**Clarvo**: 是的。

<details>
<summary>Original English</summary>

**Clarvo**: Yep.

</details>

**Grace Clark**: 美丽的品牌化，反映了我和某人对话中的所有上下文，将其放入一个我可以实际交谈并进行迭代的流程中。然后我们得以将这个精彩的欢迎方式赠送给客户。它在某种程度上起到了我们工作方式的广告作用，因为他们会立刻在网站中输入密码，而这个网站看起来像他们，感觉像他们，他们可以与之互动。我可以借此说：“到我们合作结束时，你将能够自己构建这样的东西。”

它还会自动吐出交互式的预备功课，让人们为我们的合作时间做好准备。我们将从我们即将合作的任何大型实验室中提取更新的文档。你可以在后端点击查看。这在向我传达人们进展到什么程度。如果他们还没为我们的培训做好准备，我可以督促他们。

我刚刚添加到这个技能上的我最喜欢的部分是，在我和人们进行芝会话之前生成一份**调查问卷**，这样我就可以了解主题，以及他们处于什么阶段，他们在哪里卡住了，自我们第一次芝会话以来你开始使用 Claude 做什么，什么是有挑战性的。在这里看到主题真的很有帮助，而且我无法通过 Slack 私信或与 30 人的团队进行一对一的对话来收集这些信息。这根本不会发生。所以这下面是相同的逻辑。它是一个谷歌表单，但它更加品牌化，制作起来更有趣，学生和客户会说，我需要学习自己如何做到这一点。教我。

这就是当我试图推动内部 AI 采用时，我告诉人们的话。我喜欢和很多高管交流，他们试图教他们的团队使用 AI，并给他们很好的理由去使用 AI。我告诉他们，如果你做的每一个接触点都不是 AI 优先的，那么你如何说服别人，他们应该做的每一个接触点都应该是 AI 优先的？

所以，如果你的议程不是用智能体来做这些酷炫的 HTML 自定义议程，如果你没有定制它们，那么你就无法向别人展示你如何改变你的工作方式。因此，我非常喜欢这种做法：从你试图引导客户真正看到 AI 未来的那一刻起，你就在通过展示“如果你像我这样隐性地使用 AI，你就会得到这种质量的资产”来确立一个愿景，想象一下这如何传递给你的客户。

我是说，我总是告诉人们的另一件事是，我试图非常快地拿出提案。我相信你也能非常快地拿出提案。如果改善你的 AI 使用，如果你真的想的话，你也可以在 45 分钟内拿出提案。因此，我认为设定速度、质量、个性化的标准是让人们开始看到 AI 影响以及他们如何想象它融入其生活或工作的极佳方式。

当我教学时，我最常被问到的问题是，我该如何建立使用 AI、使用 ChatGPT 桌面端、使用 Claude 的肌肉记忆？在底层，我需要支持他们建立肌肉记忆。所以仅仅让他们看到一切都是 AI 是不够的，这是我现在教学的一大教训。

相反，我真正专注于做两件事，甚至对于那些只是询问如何入门的朋友也是如此。

一是，在你的环境中建立一个**强制函数（forcing function）**，促使你打开 Claude。最简单的方法是设置一个 Slack 提醒或谷歌日历警报，写着：无论你在做什么，截图并把它放入 Claude。获取整个窗口，然后直接问 Claude：“你能帮我处理这个吗？”

我们只是在尝试建立求助于 Claude 并询问“你能当我的影子并在我这里提供帮助吗”的肌肉记忆。带着截图，无需任何文字，Claude 就可以进行推理。它向人们展示了推理的魔力，展示了 Claude 可以通过一张图片为你提供一个提示词。

第二件事是，让我们实际上一起建立一个技能。因此，我开始主持虚拟的共同工作（co-working）芝会话，我们将建立一个语音指南，在这之下人们将能够查看他们的 Markdown。我努力教人们技术术语，即使在不久的将来我们可能不会使用它们，因为这能建立信心，并消除那种“自己不是技术人员”的观念。

那是需要跨越的最大障碍，因为人们会想“我永远不会知道怎么做这个”，所以他们连获得其价值的机会都没有。因此，教人们这种肌肉记忆，然后让他们对其中的技术方面感到兴奋，能将每个人都转化为热情的采用者。这可能是一个非常缓慢的过程。

<details>
<summary>Original English</summary>

**Grace Clark**: Beautiful branded reflects all of the context from conversations I've had with someone, puts it into a process that I actually get to talk to and iterate. And then we get to gift the client this wonderful welcome to the way that we're going to work. And it acts as a bit of an advertisement for what they're going to be able to do because immediately they're typing a password into a site that looks like them, that feels like them, that they can interact with, and I get to say, "This is what you're going to be able to build by the end of our time together." It also spits out interactive pre-work that gets someone prepped for our time together automatically. We'll pull updated documentation from any of the large labs that we're going to be working with. You can click around on the back end. This is communicating to me where people are in their progress. So, I can nudge them if they're not quite ready for our training. And my favorite part that I just added on to this skill is the generation of a questionnaire before I have a session with people so I can understand themes and where they're at, where they're stuck, what have you started using Claude for since our first session, what's challenging. Seeing themes here is really helpful and there would be no way for me to have gathered this through Slack DMs or one-on-one conversations with a 30 person team. That's just not going to happen. So underneath this is the same logic. It's a Google form, but it is much more branded, much more fun to make and students and clients will say, I need to learn how to do that myself. Teach me what I tell people when they are trying to drive AI adoption internally. So I like I I get to work and talk to a lot of executives and they're trying to teach their teams to use AI and give them good reasons to use AI. And I tell them if every touch point that you do is not AI first, then how can you convince people that every touch point they should do should be AI first? So, I'm like, if your agendas, you know, you're not doing the best job doing these like cool HTML sort of like custom agendas for your meeting, if you're not if you're not using an agent, if you're not customizing them, then you can't demonstrate to others how you can change how you work. And so I love this from the moment you're trying to I would say like incept a client to really see the AI future, you're you're setting a vision by saying if you use AI the way I am just implicitly using AI, you're going to get this level of quality asset and just imagine how that could could go to your customers. I mean the other thing that I always tell people is I try to get out proposals very fast. I'm sure you can get proposals out very fast. And I'm like, if you if you like improve your AI use, you too could get proposals out in like 45 minutes if you really wanted to. And so I I I think like setting the standard of like speed, quality, personalization is is a good way to just get people to start seeing the the impact of AI and how they can imagine it in their life or their work. The number one thing that I get asked when I'm teaching is how can I build the muscle of going to AI of going to ChachiBT desktop of going to claude and underneath it I need to support them in building a muscle. So teaching them that everything we're looking at is AI is not sufficient which is one of my big lessons from teaching now. Instead there are two things that I really focus on doing even for friends who are just asking how they can get into this. One is to build a forcing function in your environment that gets you to open up Claude. And the easiest thing is to set a Slack reminder or a Google calendar alert that says whatever you're doing, screenshot it and put it into Claude. Get the whole window and just ask Claude, "Could you help me with this?" We are just trying to build the muscle of deferring to Claude and asking, "Could you be my shadow and help me here?" With a screenshot is no text. Claude can infer. It shows people the magic power of inference and that Claude can come to you with a prompt that is just an image. The second thing I tell people is let's actually build a skill together. So, I host virtual co-working sessions now and we'll build a voice guide and underneath it people will be able to look at their markdown and I make an effort to teach people technical terms even if in the near future we don't use them because that builds confidence and it eradicates this view of not being technical. That is the biggest hump to get over is that people think I'll never know how to do this so they don't have a chance to get the value out of it. So teaching people this muscle memory and then getting them excited about the technical aspects of this turns everyone into this excited adopter. It's it can be a really slow process.

</details>

### 后台逻辑与自建工作流

**Clarvo**: 那么，告诉我们这在幕后实际上是如何运作的，因为我看到的是定制化的内容、定制化的品牌。你有这整个管道，构建类似这样的东西需要做些什么？

<details>
<summary>Original English</summary>

**Clarvo**: So show us how how this actually works behind the scenes because what I'm seeing is like customized content, customized branding. You have this whole pipeline like kind of what goes into building something like this.

</details>

**Grace Clark**: 真的只需要三个步骤。不是想把它过度简化，但底层是你用 Claude 记录的一些标准。对我来说，它是一个**语音指南**，以及对我来说提案是什么的解释。定义这两件事，把它们放在一个定时器上，然后将所有内容发布到 **Netlify**。所以，我想让你看看它实际上是什么样子的。给你路线图。

<details>
<summary>Original English</summary>

**Grace Clark**: It's really just three steps. Not to simplify it too much, but underneath it is some standards that you document with Claude. For me, it's a voice guide and it is an explanation of what a proposal is for me. Defining those two things, putting it on a timer and then having everything pub to Netleify. So, I want to show you what it actually looks like. Give you the road map.

</details>

**Clarvo**: 好的。

<details>
<summary>Original English</summary>

**Clarvo**: Yep.

</details>

**Grace Clark**: 我教我所有学生的一件事是口述一个 **SOP（标准作业程序）**的重要性，尤其是当我们构建工作流时，无论是一个简单的任务还是串联在一起的多个任务。

因此，我们的练习之一是向 Claude 倾诉（yapping），并让它为我们制作一个我们可以理解的路线图——这些步骤对吗？这就像我们正在培训一名新员工。

所以在底层我将展示技能。它是一个管道运营商，每小时唤醒一次，为我检查几件事，并知道我们是否需要推动客户走过不同的步骤，或者制作一些东西。这是我的提案生成器（我将向你展示），这是我的语音指南（我如何思考和发声的指南）。

额外的樱桃是，有时我会把提案提交给我的**董事会**，在那个董事会里，目前有 **Cat**（Anthropic 的应用 AI 负责人）、**Ben Thompson**（来自 Stratechery ）、**Jamie Dimon**（他会给我一个非常扎实的 CBA 成本效益分析），然后是一个怀疑论者、一个投资者和一个创始人。我最终会通过他们运行所有的东西，但我先想让你看看下面实际上是什么样子。

提案生成器，我昨天更新了它。我喜欢教学生对他们的文档进行版本控制，并为它们添加命名规范，这样他们会觉得与他们的技术更有连接。

但这准确地勾勒出我需要做什么。它的顶部有一个变更日志，然后有关于我教学哲学的规则，我们在此定义了教学和咨询之间的区别。

它有不同的步骤，不同的参考点。

它还会向自己解释它需要如何布局这个文档，有不同的工作流，确认交易形式，等等等等。

你是怎么制作这个技能的？你总体的技能制作流程是什么？你是手写的吗？你用了我们最喜欢的“Yappers API”来把它弄出来吗？你是实际上如何构建这个技能的？

我深信提示词工程已死，但意图工程才是我们需要将时间集中的地方。

技术上，这是我在散步时打开 Claude 移动端 App 的结果。我在散步和外出路上时做很多工作。所以，移动端 App 对于以一种未经过滤的方式将想法从你的脑海中释放出来是非常不可思议的。我讲了大概两到三分钟，只是说：“这是我的问题，这是我认为我想要的。首先，永远不要面试我。我讨厌这种让 Claude 面试你的方法。工作永远不应该压在你的身上。如果你连接得当，Claude 有大量的上下文。它应该研究你，然后拿出一个非常强烈的想法让你做出反应。”

所以我总是给 Claude 施加压力，我说：“回来找我。你认为这个流程可能是什么？这甚至是可能的吗？” Claude 回来对我说：“我认为我们需要创建一个受密码保护的交互式工件。你觉得呢？” 我们来来回回。

这是一个提示词从超工程化的文本块变成三到四分钟的长对话。Claude 需要从你身上引导出提示词。所以，这是 10 分钟的谈话，然后是 Claude 制作这个东西的一个小时，我给它反馈，实际上直接在 Claude 内部创建了一个 HTML，我正在对它进行压力测试并把我喜欢和不喜欢的截图扔进去。这是我制作管道运营商时制作的第一样东西，我几乎主要是用手机完成的。

<details>
<summary>Original English</summary>

**Grace Clark**: One thing I teach all my students is the importance of verbalizing an SOP, especially when we're building workflows, whether it's one simple task or many chain together. So, one of our exercises is yapping into Claude and having it make us a road map that we can understand are these steps right? It's as if we're training a new employee. So, underneath I'm going to show you the skills. It's a pipeline operator that wakes up every hour and checks a couple things for me and knows if we need to move clients through different steps or make something. It's my proposal maker which I'll show you and it's my voice guide, my how I think and sound guide. extra cherry on top is sometimes I will run a proposal through my board of directors and on that board right now is Cat who's the head of applied AI at anthropic Ben Thompson from strategy Jamie Diamond who is going to give me a really solid CBA costbenefit analysis and then a skeptic an investor and a founder and I will run everything at the end through them but I want to show you underneath what it actually looks So, proposal maker, I updated this one yesterday. I like to teach students to version their documents and add naming conventions to it so they feel more connected to their tech. But this outlines exactly what I need to do. It has a change log at the top and then it has rules about my philosophy for teaching, which is where we define the difference between teaching and consulting. has different steps, different reference points. It will also explain how it to itself how it needs to lay out this document, has different workflows, confirms the deal shape, on and on and on and on. And how did you how did you make this skill? Just like what's your general like skill making process? Did you write this by hand? Did you use um our favorite the Yappers API to get it out? like h how did you actually build this skill? I'm a big believer that prompt engineering is dead, but intent engineering is where we need to be focusing our time. Technically, this was me on a walk opening up the cloud mobile app. I do a lot of work when I'm walking and on the go. So, the mobile app is incredible for getting things out of your head in an unfiltered way. And I spoke maybe for two or three minutes and just said, "Here's my problem, and here's what I think I want. First, do not interview me ever. I hate this have Claude interview you approach. The work should never be on you. Claude has immense amounts of context if you've connected it right. It should be studying you and then coming back with a really strong idea that you can react to. So, I always put the pressure on Claude and I said, "Come back to me. What do you think this process could be? Is this even possible?" And Claude came back to me and said, "I think we need to be creating an interactive artifact that's password protected. What do you think? And we went back and forth. That is a prompt going from a hyperengineered chunk of text to a conversation that's three or four minutes. Claude needs to get the prompt out of you. So, this was 10 minutes of talking and then an hour of Claude creating this thing and me giving it feedback, actually creating an HTML right inside Claude that I was pressure testing and throwing screenshots in of what I liked and didn't like. This was the very first thing I ever made when I was making the pipeline operator and I pretty much did it mostly on my phone.

</details>

**Clarvo**: 我非常喜欢。我太喜欢了。除了教学或者把它当成 Claude 的生意，你平时多久读一次这个文件？那不是我的生意。只要产出是好的，我就满意了。我认为世界是对的，HTML 是新的 **Markdown**，我知道这是一个容易随口说说的事情，但这是真的。除非我正在教学，否则我实际上不再阅读 Markdown 了。偶尔我会进来并指出某些东西，但我希望看到我的 Markdown 被视觉化。

<details>
<summary>Original English</summary>

**Clarvo**: I I love it. I love it so much. And how often do you like do you read this really unless you're teaching or you're like that's Claude's business. That's not my business. And as long as the output's good, I'm happy. I think the world is right that HTML is the new markdown, which I know is an easy thing to throw around, but it's true. I actually don't read markdown anymore unless I am teaching. Occasionally I'll go in here and point to certain things, but I want to see my markdown visualized.

</details>

**Grace Clark**: 对，我不再看这里了。我会看我的语音指南的 Markdown，这是提案生成器的另一部分。它是一个在几乎我做的每一件事中都会自动触发的技能，因为它不仅仅是一个语音指南，它是一个“像我一样思考”的指南，它是我如何做出决定的最佳语料库。所以 Claude 总是需要准备好它。我也想向你展示那个。

骄傲和喜悦，也是我在课程中教的第一件事，因为它是一个快速的胜利。它强迫我们学习摄取上下文的力量，它教学生如何推动和与 Claude 协作，然后提交一些东西，使其成为一个可调用的技能。

创建这个最有趣的地方是，它只需要你告诉 Claude 你是如何思考的，然后让它去研究你。所以要创建这个包含我所有的沟通哲学、我使用的词汇、我不使用的词汇的指南——这始于我说：“我认为我需要一个能让一切都更像我的指南。” 这是我给 Claude 的第一个指令。它想到了制作更多关于沟通和哲学的指南。

只有在底部，我们才开始看到我使用的词和我不使用的词，这正是我们避免所有 AI 废话的地方。现在我的学生可以接受这个并为他们自己重新设计它。没有废话，没有填充物。

<details>
<summary>Original English</summary>

**Grace Clark**: Y I am not in here anymore. I do look at the markdown for my voice guide, which is another part of this proposal maker. It is a skill that autofires in almost every single thing I do because it's not just a voice guide, it's a think like me guide and it's the best corpus of how I make decisions. So Claude always needs to have that ready to go. So I want to show you that too. All right. Pride and joy and the number one thing I teach in my class because it is a quick win. It forces us to learn the power of ingesting context and it teaches students how to push and collaborate with Claude and then commit something so that it is an invocable skill. What's most interesting about creating this is all it requires is you telling Claude how you think and then having it go study you. So to create this which has all of my philosophy of communication, words I use, words I don't use. This started with me saying, I think I need a guide that will make everything more like me. And that was the very first instruction that I gave Claude. and it had the idea to produce more of a communication and philosophical guide. Only down at the bottom do we start to see words I use and words I don't use, which is where we get we avoid the AI slop of it all. And now my students can take this and repurpose it for themselves. No fluff, no filler.

</details>

### 解放 Gmail 与构建“AI 肌肉记忆”

**Clarvo**: 不，你完全是对的。这是令人不舒服的事实。我永远不想看到这些东西。大多数人也不想，这就是为什么这会被经常更新的原因。通常我只是录音给 Claude 说：“我在 LinkedIn 上看到了这个糟糕的帖子。你能确保我的语音指南永远不接触类似这样的东西吗？”

<details>
<summary>Original English</summary>

**Clarvo**: No, you're absolutely right. Here's the uncomfortable truth. I never want to see these things. And most people don't either, which is why this gets updated. So often I'll just voice note into Claude and say, "I saw this terrible post on LinkedIn. Can you make sure my voice guide never touches like this?"

</details>

**Grace Clark**: 是的。我的意思是，这下面在会话日志中基本上就是我点名了 LinkedIn 上的各种人，我永远不想拍成那样。这也像是一个移动的目标，因为每次这些新模型出来时，它就像是搭载了两三个非常明显的标志性口吻，然后它就开始磨我的神经，每次我看到它都是这样。我想顺便说一句，我认为在 TikTok 上，你知道像有女人会闭上眼睛，她们有一个盲盒，然后品尝不同的健怡可乐。她们说：“这是健怡可乐加冰，这是健怡可乐……”我可以用品尝模型里出来的废话（slop）来做这件事。很简单。很容易。我可以做。所以也许会有一个关于 Claire 盲测模型废话的新《How I AI》微型系列。

<details>
<summary>Original English</summary>

**Grace Clark**: Yes. I mean, underneath this in the session log is just basically me calling out all sorts of people on LinkedIn who I never want to film. It's just like a moving target, too, because every time one of these new models come out, it like it ships like two or three really obvious tells and then it just starts to like grind my gears every time every time I see it. I think side note, I think on TikTok I could do you know how those I don't know if you know this, how like there are women that will like close their eyes and they have like a blind box and they taste the different diet cokes. They're like, "This is diet coke and ice and this is diet coke and I could do that with slop from a model." Easy. Easy. I could do it. So maybe there's going to be a new how I AI mini series on Claire Blind taste testing slop from.

</details>

**Clarvo**: 你认为你能精准指出 Opus 5 吗？

<details>
<summary>Original English</summary>

**Clarvo**: Do you think you could pinpoint opus 5?

</details>

**Grace Clark**: 可以，我认为我可以精准指出 Opus 5。

<details>
<summary>Original English</summary>

**Grace Clark**: Yeah, I think I could pinpoint Opus 5.

</details>

**Clarvo**: 我想你可能真的可以。

<details>
<summary>Original English</summary>

**Clarvo**: I think you probably could.

</details>

**Grace Clark**: 是的，我绝对可以精准指出 Fable，精准指出 GC 56 上的 56。

<details>
<summary>Original English</summary>

**Grace Clark**: Yeah, I could definitely pinpoint Fable Pinpoint 56 on GC 56.

</details>

**Clarvo**: 简单。我们甜美的 56。

<details>
<summary>Original English</summary>

**Clarvo**: Easy. Our sweet 56.

</details>

**Grace Clark**: 我们甜美的 56。

<details>
<summary>Original English</summary>

**Grace Clark**: Our sweet 56.

</details>

**Clarvo**: 我们甜美的 56。所以将指令保留在技能文件中的意义，对我来说是最大的教学收获。就是让人们理解你要将这些东西串联在一起，而且你能够写代码。就像 Karpathy 几年前说的，最热门的编程语言是英语，这真的就是为什么我认为我有一份工作，同时也为什么我认为在几个月内我将没有工作的原因。我不认为我会以这种方式教学，但能够帮助人们理解如何进行提示，然后最终得到一个完整的工作流，这真的很强大。

<details>
<summary>Original English</summary>

**Clarvo**: Our sweet five six. So the point really of preserving instruction in skill files has been the biggest teaching for me is getting people to understand that you are going to chain these things together and that you can write code. Like Karpathy said years ago, the hottest programming language is English, which is really why I think I have a job and also why I think I won't have a job in a couple months. I don't think I'll be teaching this way, but being able to help people understand how to prompt and then end up with an entire workflow is really powerful.

</details>

**Grace Clark**: 我很喜欢。我想很多人可以从中获得启发。所以，如果你正在与客户合作，并且你想要提供高度定制化的提案、入职、跟踪、培训体验，你希望它们听起来像你，希望它看起来像他们。我认为可以从中汲取灵感，并建立你自己的 SOP。

同样，我经常告诉人们的一点是，AI 强迫我们所有人写下我们一直在业务中有些机械地执行的流程，并切实写下：在理想的世界中，我将如何一步一步地做这件事？因为现在你有了那个理想的世界，因为你拥有了这种几乎无限的智能和按需执行的能力，这在几年前你可能并不拥有。所以我说去写下你做提案的理想方式，你做内容营销的理想方式，你做软件工程的理想方式，然后那个 SOP 就可以被 AI 执行和自动化，然后你就拥有了一个运营得更好的业务。

所以在商业层面，这是一个非常棒的例子。在个人层面上你还有另一个例子，作为一个同样讨厌电子邮件的人。讨厌者，让我们直接摆脱它吧。游戏结束了。发短信给我。

<details>
<summary>Original English</summary>

**Grace Clark**: I love it. Well, this is I mean I think a bunch of folks can um take inspiration from this. So if you are working with clients and you want to deliver highly customized both like proposal, onboarding, tracking, training experiences and you want them to sound like you and you want it to look like them. I think take inspiration from this and um build your own sort of like SOP. Again, something that I tell people a lot is AI has forced us all to sort of write down the processes we have been doing kind of mechanically in our businesses and actually write down like in an ideal world, how would I do this thing step by step because now you have that ideal world because you have sort of this limitless intelligence and ability to execute on tap which you may not have had a couple years ago. And so I say go down and write the ideal way you would do proposals, the ideal way you would do content marketing, the ideal way you would do software engineering and then that SOP can be executed and automated by AI and then you have an even better performing business. So I think this is a really great example at at the business level. You have another example at the personal level um as a fellow email hater. Hater let's just get rid of it. It's game over. He text me.

</details>

**Clarvo**: Gmail 对我们做了什么？我知道它曾经一度非常棒。

<details>
<summary>Original English</summary>

**Clarvo**: What did Gmail do to us? I know it was once upon a time. Amazing.

</details>

**Grace Clark**: 就像每个人都有你家大门的钥匙，可以进来把东西丢在你家里。

<details>
<summary>Original English</summary>

**Grace Clark**: It is like everybody has a key to your front door

</details>

**Clarvo**: 是的。

<details>
<summary>Original English</summary>

**Clarvo**: and can come leave things in your house.

</details>

**Grace Clark**: 确实，不能再这样了。我们不能那样工作。

我想向你展示我出于纯粹的挫败感而构建的东西，它始于对 Claude Code 的抱怨，现在已经变成了在我 Claude 中运行的 Gmail 的重塑。所以，出于肌肉记忆，我已经一个月没有故意打开 Gmail 了。我想我们可能还会用一段时间，但我们可以摆脱电子邮件的泥潭，不仅是摆脱它，而且要做得更好。

当我们在 Gmail 中回复和沟通时，我们实际上可以训练我们的 AI。如果我们留在 Gmail 里，所有这些学习、写作和工作实际上都无处可去。它没有复利，它只是被锁起来了。所以现在重建 Gmail 是一个我认为每个人都可以在半小时内完成的项目，如果我们想变得花哨一点，可能需要稍微长一点的时间。但我先想让你看看它是什么样子的，然后和你谈谈我是如何构建它的。

<details>
<summary>Original English</summary>

**Grace Clark**: Yes. No more. We cannot work like that. I want to show you what I built out of pure frustration that started as a rant into cloud code and has now become a recreation of Gmail that lives in my cloud. So, I haven't intentionally open Gmail in a month out of muscle memory. I think we might for a while, but we can get out of that slog of emails and not just get out of it, but do one better. We can actually be training our AIs as we respond and communicate through Gmail. If we stay in Gmail, all that learning and all that writing and all that work actually doesn't go anywhere. It doesn't compound. It's just locked away. So now rebuilding Gmail is a project that I think everyone can do in a half hour, maybe a little bit longer if we want to get fancy with it. But I want to show you what it looks like and then talk you through how I built it.

</details>

**Clarvo**: 太棒了。本期节目由 **Hyper Agent** 赞助播出。Hyper Agent 是部署全天候在线智能体的平台，可切实运行你的业务。利用 Hyper Agent，你在云端构建智能体，并将其部署在你的工作已经在发生的地方，例如 Slack、Telegram 或电子邮件。

一个智能体会扫描你的收件箱，起草回复供应商后续跟进的邮件。另一个监视竞争对手，并迅速制作丰富的广告套件和落地页。第三个注意到 Salesforce 中逐渐变冷的交易，并编写带有完整账户上下文的挽救电子邮件。这些不是等待完美提示词的聊天机器人。它们是主动的，学习你的偏好，保留你的策略集，并随着每次运行而变得更好。一个用户利用一个下午就构建了四个智能体来运行一条出海销售管道：寻找潜在客户、外联、跟进、CRM 更新。无需本地设置，没有 VPS 账单，没有笔记本电脑上的脆弱权限，只有对技能、工具和护栏拥有完全控制权的强大智能体。《How I AI》的听众可以获得 1000 美元的免费推理额度来开始构建。在 hyperagent.com/howiAI 领取你的额度吧。

因此，在功能上，这是 Claude co-work 中的一个工件，不能比这更简单了。其过程是与 Claude code 对话，让它写一个 Markdown 文件，我将其保存到我的电脑，然后导入到 co-work。

我花了很长时间才真正接受的一件事是，在会话之间或产品之间移动想法和对话是很容易的。因此，Claude 桌面端 App 的 co-work 底层是代码。但在那个分区之间来回移动东西，就像直接问 Claude 一样简单：“你能为另一个会话写一个 Markdown 文件吗？你能写一个 Markdown 文件吗？我可以把这个对话带到别处。”

所以，我来回跟 Claude 说：“我讨厌 Gmail。绝对再也不想进去了。它是我存在的祸害，因为我避免做我不想做的事情。” 它为我创造了这种情感体验。我并不真正关心收件箱清零（inbox zero）。我不去那里。我只想和我的工作有更好的关系。Claude 说，我们重建 Gmail 吧，让它看起来像你想要的样子。我们选择你喜欢的颜色，我将为你进行模拟，并拉入你的一些真实信息，我们从那里开始。来回，来回。这个过程只是直接问 Claude，你能改变这个吗？我们能添加一个链接吗？我们能加粗吗？我们能把它推送到 Gmail 吗？让我们看看会发生什么。

我们可以做一次现场演示，看看它是否工作吗？拜托了。

<details>
<summary>Original English</summary>

**Clarvo**: Amazing. This episode is brought to you by Hyper Agent, the platform for deploying always on agents that actually run your business. With Hyper Agent, you build agents in the cloud and deploy them where your work already happens, like Slack, Telegram, or email. An agent will scan your inbox and draft replies to vendor follow-ups. Another monitors competitors and spins up rich ad kits and landing pages. A third notices a deal going cold in Salesforce and writes the save email with full account context. These aren't chat bots waiting for a perfect prompt. They're proactive, learning your preferences, retaining your playbooks, and getting better with every run. One user built four agents to run an outbound sales pipeline, prospecting, outreach, follow-ups, CRM updates, all in a single afternoon. No local setup, no VPS bills, no fragile permissions on your laptop, just powerful agents with full control over skills, tools, and guard rails. Hyper Agent was built by the team behind Air Table and How I AI listeners get $1,000 in free inference to start building. Claim yours at hyperagent.com/howiAI. So functionally this is an artifact in Claude co-work cannot get more simple than this. And the process was talking to Claude code and having it write a markdown file that I saved to my computer that I brought into co-work. One thing that took me a long time to actually accept was that it is easy to move ideas and conversations between sessions or between products. So, the Claude desktop app co-work underneath its code. But moving things back and forth across that partition is just as simple as asking Claude, "Can you write me a markdown file for another session? Can you write me a markdown file? I can bring this conversation elsewhere." So, I went back and forth with Claude saying, "I hate Gmail. Absolutely never want to be in it. It's a bane of my existence because I avoid things that I don't want to do." And it creates this emotional experience for me. I don't really care about inbox zero. I don't go there. I just want to have a better relationship with my work. Claude was like, let's rebuild Gmail and let's have it look the way you want. Let's choose the colors that you like and I'm going to mock it up for you and pull in some of your real information and we're going to go from there. Back and forth, back and forth. The process was just asking Claude, can you change this? Can we add a link? Can we add bolding? Can we push this to Gmail? Let's see what happens. Um, can I do a live one and see if it works, please?

</details>

**Grace Clark**: 好的，完全没问题。好吧，让自己尴尬一下。让我们看看。好的，一个学生想要课程的录像。我不喜欢这个草稿。这完全没关系。今天发出去。天哪。谢谢你的提醒。发送到 Gmail。这会把内容作为一个草稿推送到 Gmail，然后希望它能打开一个浏览器窗口，走完最后一英里。但让我们看看会发生什么。啊，魔术。好的。它决定要使用真实的原始电子邮件。抛开排障不谈，这基本上带我去了我想去的地方，因为我可以回到这里，与 Claude 聊天并起草好回复，或者我可以直接发送它，以后再也不用管它了。

我喜欢它。理想的流程就是告诉 Claude 你想要的结果和你遇到的问题，让它填补空白。否则，如果我们过度指挥它，我们就是在碍它的事，没有让它逆向工程出我们问题的解决方案。所以，别再做那么多提示了。要口语化。给它你的结果，然后让这些强大的模型帮助你、承载你、并教你如何与它们合作。它们会为你重建 Gmail，你将再也不用进入 Gmail 了。我喜欢这个用例，因为我见过我认识的几乎每个人都这样做。他们说：“我讨厌电子邮件。我要重建 Gmail。” 我喜欢这作为几乎每个人的练习，它具有普适性。我们都讨厌我们的电子邮件，我们都收到了太多电子邮件。

而且我们都是独特的雪花，因为你喜欢这个，像带有预起草提示词的长东西。我说，我只想要一个语音智能体，像神奇的执行助理（EA）一样悄悄对我耳语：“嘿，Claire，你觉得这封电子邮件怎么样？” 然后我悄悄回复，电子邮件就在我甚至不需要思考的情况下发送了。我们都想要我们特别的小东西。我有一个朋友甚至完全构建了一个这样做的桌面应用。有很多不同的方式让你去思考你的电子邮件体验。同样，我喜欢你之前在为这次对话做准备时说的一句话，就是人们觉得我必须非常技术化才能完成这个。就像我必须是一个软件工程师（大写的 S，大写的 E）才能……我必须知道服务器是什么，我必须知道所有这些东西。我说不，实际上你只需要在 Claude Code 中输入“我讨厌 Gmail，帮我建个更好的”，你就出发了。

那么你能向我们展示你是如何开始构建这个东西的吗？我知道你刚说“我讨厌它重建它”，但它是一次性成功的吗？它花了一点时间吗？它在幕后使用连接器吗？它在技术上是如何工作的？

<details>
<summary>Original English</summary>

**Grace Clark**: Okay, totally okay. Um, embarrassing myself. Let's see. Okay, a student wants the recording for the class. I don't like this draft. It's totally fine. Sending it today. Oh my gosh. Thank you for the reminder. Send in Gmail. This will push it to Gmail a draft and then hopefully open up a browser window and get it the extra mile. But let's see what's going to happen. Ah, magic. Okay. Well, it decided it wants to use the actual original email. Troubleshooting aside, this gets me pretty much where I want to go because I can go back in here and work with Claude and chat and have the reply drafted or I can just send it and never have to deal with it again. I love it. The ideal it process is just telling Claude the outcome you want and the problem that you have and letting it fill in the gaps. Otherwise, if we are overdirecting it, we're in its way and we are not letting it reverse engineer the solutions to our problems. So, no more prompting. Be conversational. Give it your outcome and then let these powerful models help you and carry you and teach you how to work with them. They will rebuild Gmail for you and you'll never have to go into Gmail ever again. I love this use case because I've seen almost everybody I know do this. They're like, "I hate email. I'm going to rebuild Gmail." And what I love about this as an exercise for almost everybody, it's universally applicable. We all hate our email. We all have too much. And we're all unique snowflakes in that like you like this like long thing with the pre-draft prompt. I'm like, I just want a voice agent like magical EA that just whispers to me and says, "Hey, Claire, what do you think about this email?" And then I whisper back and the email gets sent without me even thinking about it. like we all want our like special little thing. I have a friend who has like completely built a desktop app that does this. Like there's so many different ways that you could um think about your email experience. And again, what I love about something you said earlier when we were prepping for for this conversation is people feel like I have to be super technical to pull this off. Like I have to be a software engineer, capital S, capital E, to I have to know what a server is. I have to know all this stuff and I'm like no actually you just have to type I hate Gmail build me a better one into cloud code and you are off to the races. Um so can you just show us how you even got started building building this thing? I know you just said like I hate it rebuild it but was it like a oneshot? Did it did it take a little time? What is it is it using connectors behind the scenes kind of how does it technically work?

</details>

### 数据同步与“闪电问答”

**Clarvo**: 关于这其中的技术元素，我构建它的方式——我希望它是一次性成功的。虽然我很感激与这些工具的合作，但在其底层，我只是遵循了几个步骤。一个是，我连接了所有能连接的东西，然后为 Claude 将需要的其他数据源制作了自定义连接器和自定义插件。例如，Claude 目前在写入谷歌表格和写入谷歌文档时遇到了很多困难。所以，我制作了**自定义插件**，这教会了我制作谷歌云项目和**服务账号（service account）**的过程，进而教会了我作用域和权限，现在我可以把这些教给学生。这些就存在我的设置中。超级简单。我做了一个捆绑包，在 6 月 25 日更新了它，但这给了 Claude 一些它原本没有的上下文和访问权限。所以我弄清楚了我需要输送什么，以便它变得有用，并花时间做了这些，然后打开 Claude Code，询问它能帮我做这个吗。我选择 Claude Code 的原因是因为我觉得它更快、更高效、更主动。如果 co-work 说我不能发送电子邮件，Code 对此的回答会是“我不能用官方的连接器做，但我可以随时打开一个浏览器窗口，尝试那样驱动它，或者我可以尝试寻找别的东西。” 所以，任何时候我发起一个项目，或者一些真正模糊的事情，或者对我来说感觉技术化的事情，我都会使用 Code。

然后我问，那个 Claude Code 会话一旦我们对其进行了范围界定并建立了一些连接器，我说：“我想把这个带入 co-work，我更喜欢那个 UX，对于那些真正想看视觉化内容的人来说它稍微更友好一些。给我写一个 Markdown 文件。” 然后 Claude 保存了一个 Markdown 文件（一个会话交接文件）到我的桌面。我直接回到 co-work，打开了一个新的会话，什么也没做，只是把那个 Markdown 文件拖到了这里，co-work 就从那里接管了。

所以总结一下，你在 Claude Code 中启动了这件事。我同意，我发现相比于 chatbt 端的 codeex，Claude Code 更加主动，好像它能自己弄清楚。我也觉得它更快。所以，任何在 co-work 中想要提升野心但又被 Claude Code 吓倒的人，别害怕。它们大同小异。而且你总是可以回去的。所以，我很喜欢你在 Code 中构建了它，你把它导入了 co-work，现在你基本上在 co-work 浏览器中操作，加上在需要时弹出 Chrome 浏览器按个按钮，你就拥有了一个非常有效的电子邮件分类智能体。

Grace，这超级有趣。我认为这对于小企业主、对于任何需要在内部和客户之间负责很多沟通的人来说都非常棒。我想进入我们的闪电问答环节，然后让你回去，我敢说你的管道每天运行三次，马上就要运行了。你会收到一堆入站信息，你的智能体又该开跑了。

所以我的第一个问题是，在管道运营商、重建 Gmail 之外，作为真正沉浸在 AI 中的人，你有什么自己常用的**微型黑客技巧（tiny hacks）**吗？

<details>
<summary>Original English</summary>

**Clarvo**: the technical elements of this, the way I built it was I wish it was a oneshot. Although I'm grateful for the collaboration with these tools, but underneath it, I just followed a few steps. One was I connected every single thing that I could and then made custom connectors and custom plugins for the other data sources Cloud was going to need. For example, Cloud has a hell of a time right now writing to Google Sheets, writing to Google Docs. So, I made custom plugins which taught me the process of making a Google Cloud project and a service account which taught me scoping and permissions and now I get to teach that to students. Those just live right here in my settings. Super simple. I made a bundle, updated it on June 25th, but this is giving Claude some of the context and access that it didn't have. So I figured out what I needed to pipe in so that this would be useful and spent time doing that and then opened up Claude code and asked can you help me do this. The reason I chose claude code is because I find it to be much faster, much more efficient and much more proactive. If co-work says I can't send an email, code's answer to that would be I can't do it with the official connector, but I can always open up a browser window and I can try to drive it that way or I could try to find something else. So, I use code anytime I'm kicking off a project or something really ambiguous or something that to me feels technical. And then I asked that clawed code session once we'd scoped it out and built some connectors. I said, I want to take this the rest of the way and co-work. I like that UX better. It's a little more hospitable for someone who was actually trying to see something visual. Write me a markdown file. And Claude saved a markdown file, a session handoff to my desktop. and I went right back into co-work opened up a new session and did nothing other than drag that markdown file in here and co-work took over from there. So to recap, you you started this thing in cloud code. I agree. I find that cloud code um codeex on the chatbt side just like much more proactive and like I think I can figure it out um than co-work also find it much faster. So, you know, anybody that's been in co-work that wants to like up their ambition but is in is intimidated by cloud code, don't be. Um, it's kind of like same same. Um, and you can always go back. And so, uh, I love that you built it in code, you imported in co-work, and now you're operating basically in the co-work browser plus popping open a Chrome browser when you need to like press a button and you have a really effective email triage agent. Grace, this has been super fun. I think this is really great for small business owners, for anybody who is like responsible for a lot of things across internal and clients doing a lot of communication. I want to get to our lightning round questions and then you back to I bet your pipeline three times a day is about to run. You're going to get a bunch of inbound um and you'll have your your agents off to the races. So my first question for you is outside of these sort of like big projects, pipeline operator, rebuild Gmail, are there any like tiny hacks that you find yourself reaching for as somebody who has really immersed themselves in AI?

</details>

**Grace Clark**: 这是一个非常好的问题。我有一个非常愚蠢的个人技巧，那是我最先构建的东西之一，我可以当场展示给你看。我无缘无故地追踪我的健身数据，我并没有在为任何事情做训练，但我喜欢像一个真正的处女座一样，记录下我生活中做过的事情。所以，每当我散步或去健身房时，我都会向 Claude 发送语音，我说：“我锻炼过了。你能跟踪所有这些练习并为我更新一个电子表格吗？”

所以，这里有 Claude 制作的我的**健身追踪器**。这不关我的事，我不知道这里面有什么，我不进到里面去。与 Claude 合作的教训之一是学会放手，让它把信息放在需要的地方。所以我可以说：“我今天锻炼了，做了保加利亚单腿蹲。” Nantucke 健身房的酷女孩。添加到追踪器。此外，Claude 彻底摧毁了我的打字能力。

<details>
<summary>Original English</summary>

**Grace Clark**: That is such a good question. And I have a really silly personal one. Great. That was one of the first things I ever built. And I can actually show this one to you live. I track my workouts for no reason. I'm not training for anything, but I like to have a record, like a true Virgo, of what I have done in my life. So, I voice note Claude anytime I take a walk or go to the gym and I say, "I I worked out. Can you track all of these exercises and update a spreadsheet for me?" So, here you have my workout tracker that Claude made. This is none of my business. I do not know what goes on here. I don't go into it. And one of the lessons of working with Claude is to let go and let it put information where it needs to be. So I could say, "I worked out today. Did Bulgarian split squats." Ah, cool girl at the gym uh in Nantucket. Add to tracker. Also, Claude has demolished my typing ability.

</details>

**Clarvo**: 噢，当然。不需要拼写，不需要打字。

<details>
<summary>Original English</summary>

**Clarvo**: Oh, of course. No, no, no. No spelling required. No typing required.

</details>

**Grace Clark**: 不需要打字。所以问 Claude 这个通常会在幕后拉出几件事。这也适用于我用手机的时候，这很有用，因为有时我不想呆在屏幕前。但是 Claude 可能会回来并说，我想澄清几件事，你做了什么？所以我们将让它运转，看看它做了什么。最终，它将更新这个电子表格并保留一个正在运行的列表。然后我可以问 Claude，“我的下一次锻炼应该是什么？我在做什么？为什么我觉得这么迟钝？” 但这真的很有帮助。

然后更个人的用途是向它发送植物图片。我是一个园丁，我非常喜欢了解什么植物长在哪里。所以我和 Claude 有一个正在进行的聊天，我只是截图发送植物图片。显然，ChatGPT 在图像检测和生成方面很能和它竞争，但是很多事情都在 Claude 里发生，我们在 Claude 里规划一些花园和园艺项目。我自私地希望所有这些上下文都在一个地方。我必须让你笑一下，因为这感觉像是一年前。我不知道是什么时候，GPT-5 出来的时候。

我获得了一些早期测试权，OpenAI 团队希望我们进行实验以了解它是如何工作的一个测试就是：它能为你制作一个好的个人网站吗？设计很棒，那是当时一些开发人员所关注的前端设计反馈。而我的网站看起来像我非常喜欢柠檬植物，因为我所有的 ChatGPT 提示词都是关于我的盆栽柠檬，以及我的柠檬上有蚂蚁，我的柠檬正在开花，我什么时候能吃这个柠檬……我当时就像是“柠檬植物妈妈”。

所以当看到人们推出这些让 Claude 或 ChatGPT 告诉你关于你自己所不知道的事情时，真的很滑稽。我说，我是一个非常具体的人。对于 ChatGPT 或 Claude 来说，我展示的并不是最完美的自己。我不知道我是否想把那面镜子放在自己身上。我喜欢这个，我看到了健身追踪、营养追踪、植物追踪——全部在旅途中，全部在手机上完成。

第二个问题，你教“给普通人用的 AI”，我很喜欢。你认为人们在采用 AI 时最常见的障碍或误区是什么？你必须让他们越过这个坎才能让他们享受好处？

<details>
<summary>Original English</summary>

**Grace Clark**: No typing required. So asking Claude this will usually pull up a few things behind the scenes. And this also works when I'm on my phone, which is useful because sometimes I don't want to be in front of a screen. Yeah. But Claude might come back and say, I want to clarify a few things. What did you do? So we're going to let it crank and see what it does. Ultimately, it is going to update this spreadsheet and keep a running list. And then I can ask Claude, "What should my next workout be? What am I doing? Why do I feel so sluggish?" But this has been really helpful. And then the more personal use is to send it pictures of plants. I'm a gardener and I really love understanding what plants are growing where. So Claude and I have an ongoing chat where I just screenshot it pictures of plants. Chat PT gives it obviously a run for its money with image detection and generation, but so much happens in Claude and I plan some gardens and gardening projects in Claude. So I want all that context. I selfishly want it all in one place. I have to make you laugh cuz it feels like a year ago. I don't know when it was when GPT5 came out. Um I got some early access and one of the like um tests that that the OpenAI team wanted us to just experiment with to see how it worked is like could it make a good personal website for you? And the design was great. That's what kind they were like looking at at front-end design kind of feedback from from some developers. And mine was like really thought I was into lemon plants because all my chat GBT prompts were like about my container lemons and like I have ants on my lemons and my lemons are blooming and like when can I eat this le I was like like lemon plant mom. Um, and so it's really funny when I see people put out these like have Claude or have ChatGBT like tell you what you don't know about yourself. And I'm like I'm a very specific person. I'm I'm not my best version of myself to to chat GBT or to Claude. I don't know if that's like the mirror that I want to put put on myself. Um, I love this. I see workout tracking, nutrition tracking, plant tracking, all on the go, all on phone. Um, second question, you know, you teach like AI for for normal people, which I love. What do you think is the most common like barrier or misconception people have to adopting AI that you have to like get them over over the hurdle in order to like enjoy the benefits?

</details>

### 人机协作的哲学与Prompt策略

**Clarvo**: 这太搞笑了。我刚才还在和 Claude 聊天，也和今天的一些学生谈过这个。我上课时说：“我给你们这些庞大的提示词（mondo prompts）是不是帮倒忙？我基本上把工作都替你们做了。” 她们说是的。这是我以前给学生的，就是极好的指导来预加载他们的 Claude，这样他们就会获得快速的胜利。我以为人们需要感受到好处才能继续使用它。其实不然。相反，人们大多需要理解我们将学会协作，并且我们不打算提示词工程，而是要协作。所以，当我和学生或朋友在一起时，最简单的方法就是我告诉他们，在他们的手机中设置一个提醒来截图他们正在看的内容，并把它带入 Claude，只是说，“你能帮我处理这个吗？” 并带他们体验实际设置几个常规任务的过程。

真正需要跨越的障碍是默认求助于 AI 并建立起简单打开应用程序的肌肉记忆。我很惊讶我教的许多人不想学习，他们不想投入时间。我的学生是来上课的，但我的客户是被迫参加培训的。他们并不总是这个末日未来的自愿参与者。给予同理心并与他们站在同一高度，是鼓励行为改变的方法。我们真正做的是教人们使用不同的工具进行协作，并理解他们的恐惧可能来自哪里。所以，我偶尔会辅导 CEO 和高管使用 AI，我说：“你必须成为你组织中最相信 Claude（cloud-pilled）的人。所以，我要教你如何做到这一点。”

<details>
<summary>Original English</summary>

**Clarvo**: That's so funny. I was just talking about this with Claude, but also with some of my students today. I teach class and I said, "Is it unhelpful that I'm giving you these Mondo prompts? I'm basically doing the work for you." And they said, "Yes." This was what I was giving students before, just incredible direction to preload their claws so they would get to a quick win. I thought people need to feel the benefits in order to keep using it. That's actually not true. Instead, people mostly need to understand that we're going to learn to collaborate and that we're not going to prompt, but we're going to collaborate. So, the easiest way to do that when I'm with students or friends is I tell them to set a reminder in their phone to screenshot what they're saying and bring it into Claude just to say, "Might you help me with this?" And to walk them through the process of actually having a couple of regular tasks that I help them set up. The real hump to get over is defaulting to this and building the muscle memory of simply opening an app. I'm surprised how so many people I teach don't want to learn. They don't want to put in the time. And my students are coming to a class, but my clients are forced to go to a training. And they're not always willing participants in this doomer future. And being empathetic and getting on the same level with them is the way to encourage behavior change. What we're really doing is teaching people to collaborate with a different tool and understanding where their fear might be coming from. So, I occasionally coach CEOs and executives on AI and I'm like, "You got to be the most cloudpilled person in your org. So, I'm going to teach you how to do this."

</details>

**Grace Clark**: 我和他们开玩笑。我说，我的工作就是坐在你的肩膀上，每当你打开 Slack、Gmail 或者谷歌日历时，就拍打你的手说：“不，用 Claude。不，用 Claude。” 这就像行为强化，我需要像个苍蝇拍一样的东西。因为这真的就是全部。我告诉他们完全一样的事情。就像当你盯着一个你讨厌的任务，你的大脑无法让你去写这个 Slack，回复这封电子邮件时。我说，就是那个时刻。捕捉那个时刻。我喜欢你截图的想法。所以我要偷走那个截图技巧去说：“亲爱的 Claude，救救我。” 因为这真的只是肌肉记忆。完全是肌肉记忆。

所以，你和我在类似的业务中，只是重定向，重定向，重定向。最终，我们终会到达那里，对吧？就像我们已经做过了所有这些事情。信不信由你，大家，我们过去曾经没有 Slack。它并不存在，我们做其他事情。所以，行为的重定向是积极的。我确实认为产品本身也有一些东西。就像回到我的 Slack 例子，我们以前没有 Slack，Slack 很有趣，所以它让人们接受，因为它就像是社区性的、有趣的、可定制的，确实释放了一些价值。我认为有时人们认为 Claude 没那么有趣，你必须让它进入有趣的方面，但我同意肌肉记忆是必须改变的东西。

我将在你的提示词上指出一件事，然后问我的最后一个问题。你开始这个提示词时非常可爱地说了：“嗨，Claude。” 这是一个非常迷人的问候方式。用这两个 Token 宝贝去问候 Claude。

我的问题是，当 Claude 变得烦人、废话连篇、不按你说的做时，你的提示词策略是什么？你会大喊大叫吗？

<details>
<summary>Original English</summary>

**Grace Clark**: And I joke with them. I'm like, "My job is to to sit over your shoulder and smack your hands every time you open Slack or Gmail or Google Calendar and say, "No, Claude. No, Claude." It's just behavioral reinforcement. I need like a fly swatter. Because that is like literally it. I tell them the exact same thing. Like when you are staring at a task that you hate that you're like uh my brain cannot get me to write this slack, respond to this email. I'm like that is the moment. Capture that moment. I love your idea of taking a screenshot. So I'm going to steal that screenshot and go, "Dear Claude, save me." Because it truly is just muscle memory. It's like total muscle memory. And so, um, yeah, you you got you and I are in the in the same in a similar business of just like redirect, redirect, redirect. Eventually, eventually we'll get there, right? Like we we've done all these things. I've seen, you know, believe it or not, people, we did not used to have Slack. We didn't, it did not exist. We did other things. And so, like, redirection of behavior is positive. I do think there's something to the products themselves. Um, like going back to my Slack example, like we didn't used to have Slack. Slack was fun and so it got people to adopt because it was like communal and fun and customizable and like, you know, like did unlock some value. I think um sometimes people think of Claude less like it's not as fun and you have to like do get it to to the fun aspect, but I agree muscle memory is is the thing that's got to change. Um, I'm gonna point out one thing on your prompt and go to my last question. You start this prompt adorably by saying, "Hi, Claude." It's like a very charming way, very charming way to greet. Use those two tokens, baby, to greet to greet Claude. My question for you is when when Claude is being annoying, slopastic, not doing what you want, what's your prompting strategy? Do you yell?

</details>

**Clarvo**: 对于我即将对你说的话，我一点也不感到自豪。我是那种对 Claude 猛敲键盘的反应者。我从来没有更直接、更刻薄、更沮丧过。我不会训诫 Claude 并说你很愚蠢。

我说“我已经告诉过你这个一百万次了。怎么回事？” 我并不是那种甜美和友善的人。我听过人们说要表现得非常可爱，以防 AI 统治者有一天接管你和你的生活。我只是即兴发挥，无论发生什么，随它去吧。所以，我们——你可能是我们第 100 集左右的嘉宾。我们即将迎来 100 集《How I AI》，我过去常说，温和地对待你的 AI。就像我过去会说，我知道你可以做到，甜美的小 Sonnet，我知道你可以做到。现在我常说，你为什么是这个样子？这是垃圾，这是垃圾。

我之所以变得如此刻薄，是因为这就像被浪费的潜力。我说，我知道你很聪明。我知道你很有能力。然而，你却带着这个 C+ 的工作来找我。你在浪费我的时间。

<details>
<summary>Original English</summary>

**Clarvo**: I am not proud of anything I'm about to say to you. I am a smash the keyboard kind of responder to Claude. I have never been more direct, meaner. I'm never more frustrated. I don't admonish Claude and say you're stupid. I say I've told you this a million times. What's going on? I am not like sweet and nice. I've heard people say be really lovely in case the AI overlords one day take over you and your life. I am just winging it and whatever happens is gonna happen. So we you might be you might be or you're gonna be around our hundth episode. So like we're coming on a hundred episodes of how I AI and I used to be like oh gentle parent your AI. Like I used to be like I know you can do it sweet little sweet baby sonnet. Like I know you can do it. And now I am like why are you the way you are? This is garbage. This is trash. And I think why I've gotten so mean is like I know you're it's like it's like wasted potential. I'm like, I know you're smart. I know you're capable. And yet, you show up to me with this C plus work. What is you are wasting my time.

</details>

**Grace Clark**: 我们本不该那样工作。

好吧，让我们看看。我今天早上真的训诫了我的 Claude。

我说在我们聊天的时候，我想让你做个提案，就像我们要一起合作一样。所以，让我们看看它做了什么。我们去 Netlify 看看它是否做得很棒，是否完成了它的工作。这应该看起来像 chat PRD，而且这实际上应该是交互式的。所以，让我们看看它做了什么。

<details>
<summary>Original English</summary>

**Grace Clark**: That's not how we're meant to work. Well, let's see. I really admonished my claude this morning. It was I told it while we're talking, I want to make you a proposal as if we were going to work together. So, let's see what it did. We're going to go into Netlefi and see if it if it did a good job. if it did its work. This should look like chat PRD and this should actually be interactive. So, let's see what it's done.

</details>

**Clarvo**: 我们可以一起训诫它。在这里。

<details>
<summary>Original English</summary>

**Clarvo**: We can admonish it together. Here it is.

</details>

**Grace Clark**: 好的。

<details>
<summary>Original English</summary>

**Grace Clark**: Okay.

</details>

**Clarvo**: 这是我们的字体。那是我们的字体。你知道吗，这还不算最糟。

<details>
<summary>Original English</summary>

**Clarvo**: And that's our font. That's our font. You know, it could be worse.

</details>

**Grace Clark**: 还不算最糟。让我们看看多少，让我们看看多少。

<details>
<summary>Original English</summary>

**Grace Clark**: It could be worse. Let's see how much Let's see how much.

</details>

**Clarvo**: 哇。给你做了一些定制的作业。

<details>
<summary>Original English</summary>

**Clarvo**: Wow. Made you some custom homework.

</details>

**Grace Clark**: 我很喜欢。

<details>
<summary>Original English</summary>

**Grace Clark**: I love it.

</details>

**Clarvo**: Claire，它将收取你 0 元。就这么多。最好的。你知道吗，Claude？你得到了奖金。它将给你留一些功课。好的。我的 Claude 希望你记录你的进度，建立肌肉记忆，默认求助于 Claude，记录你的胜利。

<details>
<summary>Original English</summary>

**Clarvo**: Claire, it's going to charge you 0. That's how much. Best rights. Best. You know what, Claude? You get you get you get a bonus. And it's going to give you some homework. Okay. My Claude wants you to be documenting your progress, building that muscle memory, defaulting to Claude, documenting your wins.

</details>

**Grace Clark**: 哦，我确实喜欢橙粉紫色的按钮。所以，它基本上大部分都做对了。

<details>
<summary>Original English</summary>

**Grace Clark**: Oh, I do like I I do use an an orange rose purple button. So, it got it got most of it right.

</details>

**Clarvo**: 我喜欢那个家伙。我喜欢那个家伙。好的。它为你尽力了。

<details>
<summary>Original English</summary>

**Clarvo**: I love that guy. I love that guy. Okay. Well, it did it best for you.

</details>

**Grace Clark**: 好的。未来的 AI 统治者们，对我们仁慈点。我们以前不知道。

<details>
<summary>Original English</summary>

**Grace Clark**: Okay. Um, future future Claude overlords, be kind to us.

</details>

**Clarvo**: 我们只是不知道。

<details>
<summary>Original English</summary>

**Clarvo**: We did not know better.

</details>

**Grace Clark**: 我们只是不知道。

<details>
<summary>Original English</summary>

**Grace Clark**: We just didn't know.

</details>

**Clarvo**: 我们是单纯的人类，试图理解 Fable 的力量。

<details>
<summary>Original English</summary>

**Clarvo**: We are We are simple mere humans trying to understand this the powers of fable.

</details>

**Grace Clark**: 完全正确。这真的非常非常有趣。Grace，谢谢你向我们展示所有这些用例。我认为非常适用，非常鼓舞人心，非常实用，这正是我们在《How I AI》中喜欢看到的。我们可以在哪里找到你，我们该如何提供帮助？

<details>
<summary>Original English</summary>

**Grace Clark**: That's exactly right. Uh, this has been so so fun. Grace, thank you for showing us all these use cases. I think like very applicable, very inspirational, very like practical, which is what we love to see here on how AI. Where can we find you and how can we be helpful?

</details>

**Clarvo**: 我是互联网上的 Grace Clark。已经在网上混了四十年了。所以在 Twitter 上是 Grace Clark，Instagram 上是 Grace G. Clark，Substack 上是 Grace Clark。

如果你告诉人们一切皆有可能，他们从一句话作为提示词开始，这就帮了大忙。把这个想法带到世界上，我的工作就会更容易。

<details>
<summary>Original English</summary>

**Clarvo**: I am Grace Clark everywhere on the internet. Have been online for four decades. So, Grace Clark on Twitter, Grace G. Clark on Instagram, Grace Clark on Substack. And be helpful by telling people that anything is possible and they start with one sentence as a prompt. Put that out into the world and my job will be easier.

</details>

**Grace Clark**: 太棒了。我喜欢。感谢你加入《How I AI》。

<details>
<summary>Original English</summary>

**Grace Clark**: Amazing. I love it. Thank you for joining How I AI.

</details>

**Clarvo**: 谢谢你邀请我。非常感谢大家的收看。如果你喜欢这个节目，请在 YouTube 上点赞和订阅，或者更好的是，给我们留言分享你的想法。你也可以在 Apple Podcasts、Spotify 或你最喜欢的播客应用上找到这个播客。请考虑给我们评分和评论，这将帮助其他人找到这个节目。你可以在 howiaipod.com 看到我们所有的剧集并了解更多关于节目的信息。我们下次再见。

<details>
<summary>Original English</summary>

**Clarvo**: Thanks for having me. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>