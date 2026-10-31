---
author: How I AI
date: '2026-03-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=I5X4_mYoiM8
speaker: How I AI
tags:
  - ai-workflow
  - design-code-sync
  - developer-tools
  - team-collaboration
  - prompt-engineering
title: Figma工程师如何利用AI工具同步设计与代码：重塑产品开发流程
summary: 本期节目深入探讨了Figma的工程师和设计师如何利用AI工具（如Codeex和Figma MCP）彻底改变传统的设计与代码工作流程。嘉宾Alex和Ghee展示了如何实现设计与代码的双向同步，将现有代码库中的状态导入Figma进行协作编辑，再将Figma中的设计变更自动应用回代码。AI极大地降低了高质量产出的成本，减少了工程师和设计师的重复性劳动，促进了团队协作和更广阔的探索空间，从而实现更高效、更具创造性的产品开发。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Figma
  - OpenAI
  - Optimizely
products_models:
  - Codeex
  - Figma MCP
  - Claude
  - Optimizely Opel
media_books: []
status: evergreen
---
### AI驱动的协作工作流

**Ghee**: 我们重新发现了在那些高峰期时的能量，那时我们都在一起进行原型设计，把所有东西都投入到同一个地方。势头会带来更大的势头，所以让团队一起集思广益、互相支持、尝试新事物真的很棒。

<details>
<summary>Original English</summary>

**Ghee**: The energy that we've rediscovered around those spikes where we're all just prototyping and throwing it all into the same place. Momentum begets momentum, and so having the team together riffing and yes-anding and trying the stuff out is really great.

</details>

**Alex**: 这感觉就像是设计师和工程师的结对编程，你可以使用 **MCP** 作为连接器在这里非常快速地来回工作。通常情况下，代码库会远远领先于实际的设计文件，而且有些状态或工作流程在设计文件中根本不存在。所以，我可以说：“将注册流程的所有五种状态发送到Figma。”现在，代理将读取我的代码库，理解我所说的这五种状态，然后将每一种状态逐一导入 **Figma**，这样 **Figma** 文档就会把所有这些状态并排展示出来，我的设计伙伴就可以在此基础上进行工作。

<details>
<summary>Original English</summary>

**Alex**: This feels like pair programming for designers and engineers, and you can work very quickly back and forth using the **MCP** as a connector here. Often, the codebase gets way ahead of where the actual design file is, and there are states or workflows that just don't exist at all within the design file. So what I can do is say, "Send all five states signup flow to Figma." Now, the agent is going to read my codebase, understand what I'm referring to when I say those five states, and for each one of those, it's going to individually import that one by one into **Figma** such that the **Figma** document will then have all of those states laid out all side by side so that my design partner can work against it.

</details>

**Ghee**: 这确实改变了我们的工作流程，甚至可以说是彻底颠覆了工作流程的定义。

<details>
<summary>Original English</summary>

**Ghee**: It's definitely changed our workflows in a way that it's really blown up what a workflow even is.

</details>

**Claire Vo**: 我现在大部分时间都坐在终端里。我经常同时运行两三个，甚至多达五个云代码实例，处理我正在跟踪的不同方面的工作。欢迎回到“我如何AI”。我是 **Claire Vo**，产品负责人，也是一位AI狂热者，致力于帮助大家更好地利用这些新工具进行构建。今天我们邀请到了来自 **Figma** 的工程师 **Alex** 和设计师 **Ghee**。他们将向我们展示设计、代码以及再回到设计的新世界和新工作流程。我对此非常兴奋，因为它将展示更具前瞻性的团队如何思考设计团队和工程团队之间的相互作用，以及设计不必再是 **Figma** 或代码中静态的产物。我们还将获得一些关于如何利用代码库中的“技能”来减少工程师和设计师的繁重工作的技巧。开始吧。本期节目由 **Optimizely** 赞助。大多数营销团队不缺创意，但他们缺时间。而这正是 **Optimizely Opel** 通过AI代理为您节省的，这些代理可以处理真实的营销工作流程，比如创建内容、检查合规性、生成实验变体、个性化用户体验、分析页面以进行地理定位，甚至包括审批和报告等任务。它是您的营销和数字团队的AI代理编排平台，无缝集成到您已使用的工具中，处理枯燥、繁忙的工作，并确保一切符合品牌规范，让营销人员有更多时间专注于他们的实际工作。通过注册 **Optimizely** 提供的免费企业代理式AI研讨会，了解 **Opel** 能为您的团队自动化哪些工作。访问 optimizely.com/howiiai 了解更多。现场参与还将获得一副免费的 **Ray-Ban Meta** 眼镜。欢迎来到“我如何AI”。**Alex** 和 **Ghee**，我很高兴你们能来，因为我们终于可以明确回答每个人心中的问题：是设计先行，还是代码先行？对吗？我们今天能最终决定这个问题吗，还是你们会让我们看到两种方向？

<details>
<summary>Original English</summary>

**Claire Vo**: I spend quite a lot of my time just sitting here inside of my terminal now. I often have two, three, up to five maybe cloud code instances running all at the same time, working on different aspects of the work that I'm tracking. Welcome back to How I AI. I'm **Claire Vo**, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have **Alex**, an engineer, and **Ghee**, a designer from **Figma**. And they're going to show us the new world and the new workflows of design, code, and back to design. I'm really excited about this one because it's going to show you how more forward-looking teams are thinking about the interplay between design and engineering teams, how designs don't have to be static artifacts, either in **Figma** or in code. And we're going to get some tips and tricks on how you can use skills in your repo to take away toil both for engineers and for designers. Let's get to it. This episode is brought to you by **Optimizely**. Most marketing teams aren't short on ideas, but what they are short on is time. And that's exactly what **Optimizely Opel** gives you back with AI agents that handle real marketing workflows, like creating content and checking compliance, generating experiment variations, personalizing user experiences, analyzing pages for GEO, even tasks like approvals and reporting. It's your AI agent orchestration platform for marketing and digital teams, plugging seamlessly into the tools you already use, handling the boring, busy work, and keeping everything on brand, that leaves marketers with more time to do your actual job. See what **Opel** can automate for your team by signing up for a free enterprise agentic AI workshop with **Optimizely**. Find out more at optimizely.com/howiiai. Attend live and you'll get a free pair of **Ray-Ban Meta** glasses. Welcome to How I AI. **Alex**, **Ghee**, I am so psyched for you all to be here because we get to finally answer definitively the question on everyone's mind, which is which comes first, the design or the code. Is that right? Do we get to finally decide that today, or are you going to force us to watch both directions?

</details>

### AI对Figma内部工作流程的影响

**Ghee**: 我认为答案是“视情况而定”。这是我最喜欢的答案，也是你最喜欢的答案。我喜欢 **Figma** 现在正在做的事情，它正在为每一个意识到“视情况而定”的团队构建产品。我们在这里要做什么？我知道你们的业务在过去几年里肯定发生了很大变化，你们的产品也肯定发生了很大变化，因为现在人们设计和构建软件的方式变化太大了。我相信这既影响了你们如何思考正在构建的产品，也影响了你们自己如何构建产品。所以，我很好奇，这如何改变了 **Figma** 内部设计和开发流程的方法？

<details>
<summary>Original English</summary>

**Ghee**: I think the answer is it depends. So my favorite answer, your favorite answer. And what I love about what **Figma** is doing right now is it's building the product for every team that has realized it just depends. What are we going to do here? And so I know that your business has to have changed a lot. Your product has to have changed a lot in the last couple years because the way people design and build software now changes so much. And I'm sure that has impact both on how you think about what product you're building, but also how you yourself build products. So I'm curious, how has this shifted how **Figma** approaches the internal design and development process?

</details>

**Ghee**: 我的意思是，这确实改变了我们的工作流程，甚至可以说是彻底颠覆了工作流程的定义。在此之前，在我们的职业生涯大部分时间里，我们都有一个非常线性、约定俗成的工作流程，即随着进展不断提高保真度，因为在代码中工作成本很高，而交换想法和草图则非常便宜。但AI基本上打破了这种模式，现在在代码中进行迭代和在设计中进行迭代一样便宜。所以很多时候，我们过去会制作灰度线框图来指示事物应该是什么样子，现在我们可以直接获得功能性的线框图。很多时候，我们把这些“有代码感的”输出视为一种更具可塑性、可以玩转的东西，然后我们再深入其中，让我的团队参与进来。我们现在仍然像许多公司一样，试图找出最佳的步骤流程。正如 **Alex** 所说，这“视情况而定”。它真的取决于功能的规模，无论是功能、bug还是产品。我们到底想实现什么？我们发现自己几乎每天都在重新发明工作流程，甚至一天多次，这取决于我们需要解决的问题。

<details>
<summary>Original English</summary>

**Ghee**: I mean, it's definitely changed our workflows in a way that it's really blown up what a workflow even is. Before, for the majority of our careers, we've had a very linear, agreed-upon workflow where you increase fidelity as you go on, because it's really expensive to work in code and it's really cheap just to trade ideas and sketch them out. But AI basically collapsed that, and it's just as cheap to riff in code as it is to riff in design. And so a lot of times where we used to mock up these kind of grayscale wireframes to point at what things should be, we can get functional wireframes straight away. And a lot of times that's what we treat these kind of vibe coded outputs. It's like let me get to something that is more malleable I can play with, and then let me kind of work into it. Let me bring my team in. And we're still like many companies right now trying to figure out what is the best kind of step process. And to **Alex**'s point, it depends. It really depends on the scale of the feature, whether it's a feature or bug or product. Like what are we trying to get to? We find ourselves reinventing a workflow almost every day, multiple times a day depending on the case that we have to solve for.

</details>

**Claire Vo**: 我喜欢你说的几点。首先，我认为直到现在，设计和工程都感觉是非常稀缺和昂贵的资源。所以你总是试图通过线框图等方式来减少设计工作量。我告诉现在的年轻人，他们不知道自己有多么幸运。你们不知道 **Balsamiq** 是什么，或者那些旧的线框图是什么样子，你们不知道我们过去用线框图必须做些什么。所以，我认为我们总是试图解决这个问题，然后我们总是小心翼翼地保护工程资源，其中一部分意味着更多的设计工作落到了设计团队身上，他们需要对设计实现做出许多非常具体的决策，这样你就不会浪费工程师的时间去思考这是否应该是一个圆角，悬停效果是什么，错误状态是什么，所有这些东西。我确实很欣赏AI的一点是，现在生成高质量内容的成本降低了，这意味着你可以投入更多精力在真正重要的部分，然后更多的人可以为设计中的最终体验做出贡献。而且，**Alex**，我相信你感觉自己可以做出更多贡献，所以，我认为这是我们历史上采用瀑布式产品开发流程的一个有趣变化。此外，你还有更多的探索能力，因为你不会在一个想法上花费太长时间，通过会议和原型等方式来降低这个想法的风险。如果你能缩短这个过程，你就可以探索更多的想法。你有更多的发散潜力。我认为这也非常有趣。我认为我们过去是深入追求质量，但现在我们也可以广泛探索。

<details>
<summary>Original English</summary>

**Claire Vo**: What I like about what you said is a couple things. One, I do think up until this point, design and engineering felt very scarce and expensive resources. And so you were always trying to reduce effort and design by doing things like wireframes. And I tell the young people today, they don't know how spoiled they are. You don't know what like **Balsamiq** is or like those old mockups used to be like, you don't know what we used to have to do with wireframe. So I think we were always trying to figure out that and then we were always like scarcely protecting engineering resources and part of that meant more work fell on the design team to make lots of very specific decisions about design implementation so that you didn't waste engineering's time trying to figure out is this supposed to be a rounded corner, what's the hover effect, what's the error state, all this kind of stuff. And what I do appreciate about AI is now the cost of generating really high quality stuff has gone down, which means you can invest more in the pieces that really matter and then more people can contribute to the ultimate experience in design. And, **Alex**, I'm sure you feel like you can contribute more and so I think that's an interesting change to how we had historically been doing more of a waterfile style product development process. And to add to that, you also have more exploration capacity because you're not spending so long on one idea, derisking that one idea through meetings and prototypes, etc. If you can shortcut to that, you can explore more ideas. You have more divergence potential. And I think that's really interesting as well. I think we got to like going deep on quality, but we can actually go wide as well.

</details>

**Alex**: 是的。

<details>
<summary>Original English</summary>

**Alex**: Yeah.

</details>

**Alex**: 是的。我发现我现在花在机械性工作上的时间少了很多，即使在工程方面，那些机械性的，比如改变语法，或者尝试在不同的调用点之间传递数据，现在我更多地专注于解决问题，我觉得这种专注于解决问题而非机械性工作的模式，正是AI在工程和设计团队中都正在实现的。

<details>
<summary>Original English</summary>

**Alex**: Yeah. I find that I'm spending a lot less time doing like the mechanistic, even on the engineering side, the mechanistic like changing of syntax and trying to thread data through different call sites and more focused on the problem-solving aspects. And I feel like that same focus on problem-solving as opposed to the mechanical work is really what AI is enabling on engineering as well as design teams.

</details>

### 代码到Figma再到代码的演示

**Claire Vo**: 太棒了。我们将实际深入展示一些内容，不是理论，而是实践。我们将看到设计从 **Codeex** 开始，这并不是我今天打电话进来时所期望的，你们会说我们从 **Codeex** 开始，但我们就是要这样做。那么，你想分享你的屏幕，向我们展示我称之为“代码三明治”的东西吗？我认为这个过程是代码、设计、代码。

<details>
<summary>Original English</summary>

**Claire Vo**: Awesome. Well, we're going to actually dive in and show some of this not in theory but in practice, and we're going to see design starting in **Codeex**, which is not what I not what I expected when I dialed into this call today that you all were going to say, "Hey, we're going to start over in **Codeex**," but that's what we're going to do. So do you want to share your screen and show us what I'm going to call the sandwich of code, which is going to be code, design, code, I think is the process.

</details>

**Ghee**: 太棒了。是的，我们开始吧。是的，我们想从 **Codeex** 开始，因为我们最近也发布了它。我们为 **Claude** 发布了一个版本。我们刚刚在 **Codeex** 上发布，并且我们将把这种 **MCP** 功能带到许多地方。让我看看我是否可以打开这个项目的本地主机。经常发生的情况是，设计和代码之间的“事实来源”会发生分歧。所以有时有些东西只以代码状态存在。或者你开始与开发人员合作，然后你真正提升了原有的东西，也就是你最初提供的那个产物，或者有时，比如，它在代码中根本不存在。你只是继承了别人很久以前的项目。所以这里真正有趣的是，我可以打开一个本地页面。所以现在我们一直在作为一个演示应用程序工作。**Alex** 和我一起做了一些东西，只是为了向你展示它的力量。假设我正在处理一个没有真正连贯的“事实来源”的东西。它只是一个财务跟踪应用程序，我真的想在这里做一些编辑。通常出现的情况是，是的，我可以为这些东西进行提示，但这有点像一个愿望和希望，希望它能做到，或者我必须非常具体，或者我必须安装一堆工具来帮助我更接近地操作材料。但我真正想在这里做的是，只是让 **Codeex** 把预算分配页面发送到 **Figma**。明白了。所以我们在这里看到的是，我认为你正在设置的问题，我对此感同身受，那就是没有人会保持他们的 **Figma** 与生产环境中的最新状态同步，而生产环境很少包含 **Figma** 中设计的所有希望和梦想。而且，很多时候，即使我在ChatPD也这样做，我们创建了一个带有大量截图的 **Figma** 页面，但它们总是过时。所以，即使是使用最近的设计来制作营销资产，而不仅仅是软件开发过程，也很难保持这些东西的同步，因为代码和设计在并行轨道上运行，而且它们之间还没有一个共同的“基底”，可以说，可以保持它们在两边的同步。

<details>
<summary>Original English</summary>

**Ghee**: Love it. Yeah, let's do it. So yeah, we thought we'd start with **Codeex** because we've just recently launched this as well. We had a launch for **Claude**. We've just launched on **Codeex** and we're bringing this kind of **MCP** functionality to a bunch of stuff. Let me see if I can just go open my local host for this project. Something that happens a lot is the sources of truth diverge between design and code. So sometimes some things only really exist in a state in code. Or you start working with a developer and you really like elevate what the thing was, the artifact that you originally supplied, or sometimes like that just doesn't exist in code. You've just inherited someone else's project from forever forever ago. And so what's really interesting here is that I can just open up a local page. So now we've been working on as a demo app. **Alex** and I put something together just to show you the power of this. Let's imagine I am working on a thing that there isn't really a coherent source of truth for. It's just a financial tracking app and I really want to do some editing in here. And the case that usually comes up is that yes, I could prompt it for these things, but it's kind of a wish and a hope that it gets it or I have to be super specific or I have to do install a bunch of tools that help me kind of manipulate closer to the material. But what I really want to do here is just ask **Codeex** to send the budget allocation page to **Figma**. Got it. So what we're seeing here and I think the problem you're setting up which I can empathize with which is no one ever keeps their **Figma** up to date with what's the latest in prod and prod rarely has the hopes and dreams of what has been designed in **Figma**. And a lot of times, even I do this at ChatPD, we've created like a **Figma** page with a bunch of screenshots and they always go out of date. And so, even for using recent designs in things like marketing assets, not even just the software development process, it's really hard to keep these things in sync because code and design are moving in parallel tracks and there's not a common substrate between them yet, I would say, that can keep them sort of up to date on both sides.

</details>

**Alex**: 完全正确。

<details>
<summary>Original English</summary>

**Alex**: Exactly. Exactly.

</details>

**Claire Vo**: 完全正确。

<details>
<summary>Original English</summary>

**Claire Vo**: That's exactly right.

</details>

**Claire Vo**: 太棒了。那么你在这里使用的是，如果我没说错的话，你把 **Figma MCP** 连接到了 **Codeex**。所以这是一个你已经连接的托管 **MCP**。你是否也在 **Codeex** 中安装了 **Figma** 技能？因为我知道 **Codeex** 非常重视技能，所以我想知道你是否将这两者结合使用。

<details>
<summary>Original English</summary>

**Claire Vo**: Great. So then what you're using here, if I tell me if I'm wrong, which is you have the **Figma MCP** connected to **Codeex**. So that's a hosted **MCP** that you've connected. Do you have the **Figma** skill also installed here in **Codeex** because I know **Codeex** has made a big deal about skills and so I'm wondering if you're using those two together.

</details>

**Ghee**: 说实话，我曾一度安装了所有的技能。所以我毫不怀疑我在某个时候正在使用它。我们也有，我们正在探索如何改进这些技能。**Alex** 肯定能对此说更多。

<details>
<summary>Original English</summary>

**Ghee**: Honestly, at some point I installed all the skills. So I have no doubt that at some point I'm using it. We also have, we're exploring kind of how we improve those. **Alex** can talk more to those for sure.

</details>

**Alex**: 是的，你可以使用这些技能来完成这项工作。但是你也可以直接询问 **MCP**，它似乎相当可靠地能让你达到目标。

<details>
<summary>Original English</summary>

**Alex**: Yeah, you can use the skills in order to do this. But you could also just ask the **MCP** directly and it seems to pretty reliably get you to a...

</details>

**Claire Vo**: 这真的很好。所以如果你真的，我的意思是，如果你看看页面，然后并排比较一下。

<details>
<summary>Original English</summary>

**Claire Vo**: This is really good. So if you actually, I mean, if you look at the page and you look at the comparison kind of side by side...

</details>

**Ghee**: 现在我把所有这些都放到了 **Figma** 里。所以，我不仅可以进行更深入的直接操作。我可以在这里移动东西，以一种更自由的形式，这可能是我以前需要用语言来表达的，而且解释我想移动哪些部分、移动到哪里等等会非常繁琐和费力。但是我的整个团队也可以加入进来，现在我们可以指数级地扩展这项工作，而不是我一个人做所有事情。当你在团队中工作时，利用这一点真的很有帮助。所以对于那些正在听但可能没有观看屏幕分享的人来说，我们刚刚看到的是，将一个本地托管的Web应用程序和代码库，然后使用 **Figma MCP** 将一个页面或组件的整个设计拉入 **Figma** 的一个画框中，然后你就可以编辑那个画框了。我之前没有真正想到的一个好处是，它真的很有用，那就是 **Figma** 确实是为多人协作、多玩家协作而构建的，而像 **Codeex**、Cursor 或 **Cloud Code** 这样的工具在提示代码方面并没有为此而构建。所以，那种广泛的探索非常非常难以做到。我想对大家说的另一件事是，看，我是一个真正的信徒，每个设计师都应该在他们的IDE中玩 **GitHub**，做所有这些事情。而且，也有一些组织还没有达到那个水平。有一些设计师还没有达到那个水平，他们没有前端语言，没有提示技能等等，但他们在 **Figma** 中是超级专业人士。这是一个很好的垫脚石，可以让他们回到他们真正舒适的环境中，但也可以以此为方式来教育他们，提升他们使用这些更多编码工具的能力，从而发挥他们的设计技能。所以我认为这里有一个中间步骤，对于那些习惯使用像 **Figma** 这样的设计工具的人来说，真的很有用。

<details>
<summary>Original English</summary>

**Ghee**: Now I have all of this in **Figma**. And so not only can I do more intense kind of direct manipulation. I can go in here and I can like move stuff around in a way that's much more free form that perhaps I would have had to like really like express with words and it should be really burdensome and laborious to explain which bits I want to move where and etc. But my whole team can also jump in and now we can just exponentially scale this work versus me solo having to do everything. And when you work in a team it's like really helpful to leverage that. So for those that are listening and maybe not watching the screen share, what we just saw is taking a locally hosted web app and codebase and then using the **Figma MCP** to then pull the whole design of a page or component into **Figma** into a frame and then you can just edit that frame. And a benefit that I didn't really think about which is really useful is it's really, **Figma** is really built for multi-person collaboration, multi-player collaboration in a way that prompting code in something like a **Codeex** or a Cursor or **Cloud Code** really isn't built for. And so that broad exploration is very very hard to do. The other thing that I want to say for people is look, I am a true believer, every designer should be in in their IDE playing with **GitHub**, all that kind of stuff. And also, there are some orgs that just like aren't there yet. There are some designers that aren't there yet that don't have the front-end language, the prompting skills, whatever, that are super pros in **Figma**. And this is a nice stepping stone to say, "Okay, we can get you back into a place where you're really comfortable with, but also use that as a way to educate, upskill them on how to use some of these more coding tools to also bring their design design skills to bear." And so I think there's a kind of halfway step here that is really useful for folks that are used to a design tool like **Figma**.

</details>

**Ghee**: 当然。而且对我来说，这只是，我认为我们还没有普遍达到这种代码工具在精确编辑方面的要求。相信我，我使用各种工具来真正了解这些工作流程的走向。我认为对我来说，黄金标准仍然是能够拖动东西。而且你可以通过一次点击做很多事情，而这些事情可能需要你用一百个词来写，才能真正精确地实现。没有人想为精确的十六进制代码或黄色色调等东西进行提示。这些东西只是更容易快速地直接操作。

<details>
<summary>Original English</summary>

**Ghee**: For sure. And also to me it's just the I don't think we're there yet in general with these kind of code tools in terms of the precision editing that you want to do. And trust me, I use the whole kind of landscape of tools to really see kind of where these workflows are going. And I think still the gold standard for me is just being able to drag stuff around. And you can do a lot with a click that would take you a hundred words to kind of write and to like really precisely nail. Like no one wants to prompt for the exact hex code or the shade of yellow and that kind of stuff. That's just easier to just quickly do and directly manipulate.

</details>

**Claire Vo**: 是的。我只是在想，人类将在哪里参与进来？那将是精细的运动技能，说实话，能够用肉眼判断那种黄色是否令人愉悦。很难通过设计循环，通过提示循环来表达：“哦，不，让那种黄色再欢快一点。”但是当你调出颜色选择器，然后开始这样操作时，你真的可以找到适合你的颜色。所以一旦你把这个导入 **Figma**，你正在与你的团队协作，你正在更新设计，下一步是什么？因为我知道你可以把它导入另一个任务，然后发送给工程师，说：“请你进行这些更新。”但是一旦你把它导入 **Figma**，你觉得接下来该怎么做？

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. I just think like what are humans where are humans going to be in the loop? And it's gonna be like fine motor skills and honestly being able to eyeball is that yellow happy or not. Like it's very hard to go through a design loop, a prompting loop of like, oh no, make that yellow just like a little bit more cheerful. But when you pull up the color picker, and you start going like this, you can really find the one that that works for you. So once you've gotten this into **Figma**, you're collaborating with your team, you're updating the design, what's the next step here? Because you know I can imagine you could pull this into another ticket and then send it send it to an engineer and say please could you make these updates but what do you think about doing once you've pulled it into **Figma**?

</details>

**Ghee**: 肯定有几种方法可以做到这一点。我可以继续自己工作。假设我正在熬夜工作，因为我真的很投入这个项目，我可以使用 **MCP** 将它带回我的本地主机。我也可以直接联系我的工程师，说：“嘿，你有没有这个正在运行的实例？你想不想自己上传它并进行工作？”所以从这里我们创建了一个共享的公共基础，不同的人可以插入并获取东西，而不是它只存在于我的机器上，我必须分支它，必须处理所有那些技术复杂性。实际上，**Alex**，这是一个好问题，你想不想尝试实现我们已经整理好的其他一些更改？

<details>
<summary>Original English</summary>

**Ghee**: There's definitely a few ways that we can do this. I can keep working myself. Let's say I'm working a late night because I'm really kind of into this project and I can just use **MCP** to bring it back to my local host. I could also just ping my engineer and say, "Hey, do you have an instance of this running? Do you want to like just upload it yourself and just work on it?" So from here we've created this kind of shared common ground where different people can plug in and just grab things out versus it living on my machine having to branch it having to get grapple with all that technical complexity. And actually it's a good point **Alex**, do you want to try and implement some of these other changes that we've kind of put together?

</details>

**Alex**: 是的，当然。假设我想实现这个特定的变体。我能做的是，我可以复制它的URL，然后直接回到我的 **Cloud Code** 会话。所以，我在这里本地也加载了应用程序，我可以说：“将这个组件的更改带入我的代码库。”它是哪个组件？它是预算分配页面。然后它将以不同的方式使用 **Figma MCP** 服务器。这个服务器允许它获取当前在 **Figma** 文档中的内容，并自动将其转换为代码，然后与你的本地代码库进行协调，并自动为你应用这些更改。

<details>
<summary>Original English</summary>

**Alex**: Yeah, absolutely. So let's say I want to implement this particular variant. What I can do is I can copy the URL of that and go right back into my **Cloud Code** session. So I have the app also loaded here locally and I can say, "Bring the changes from this component into my codebase." And which component is it? It's the this is for the budget allocations page. And it's going to then use the **Figma MCP** server in a different way. This one allows it to take stuff that's currently within the **Figma** document and automatically transform that into code which then gets reconciled with your local codebase and automatically applies those changes for you automatically.

</details>

**Claire Vo**: 再次，我需要有一个“老太太时刻”，那就是我告诉人们，你知道，我以前为了我的CSS，不得不像爬坡一样来回走，想着我以前为了得到一个接近P的像素完美版本必须做什么，而且我当时在桌子的两边。我既是设计师，又是工程师，才能得到某人模拟出来的像素完美版本，我的意思是，我们那时甚至没有 **Figma**。我当时在做的事情，我是在为真正的老一辈制作 **Photoshop PSDs**。而现在，仅仅通过打字就能获取这个尺寸是多少，它应该是什么样子，对齐方式是什么，这仍然让我感到惊讶。**Alex**，我很好奇这如何改变了你作为一名软件工程师对你工作的看法。我知道你说过那些机械性的部分已经消失了，但从时间角度来看，这为你的工作带来了什么？你如何分配你的时间？

<details>
<summary>Original English</summary>

**Claire Vo**: Again, I need to have like an old lady moment, which is I tell people, you know, when I used to have to like walk uphill both ways for my CSS, thinking about what I used to have to do to get a close to P, and I was on both sides of the table. I was a designer and then I was an engineer to get like a pixel perfect version of whatever somebody had mocked up and I mean we didn't even have **Figma**. I was doing thing. I was making **Photoshop PSDs** for the real olds out there. And I just the ability to like pull in what's the size of this, how's it supposed to look, what's the alignment all through just typing still to this day blows my mind. **Alex**, I'm curious how this has just changed your relationship with what your job is as a software engineer. I know you said like the mechanistic pieces have gone away, but what does this do for you for from like a time like how you spend your time perspective?

</details>

**Alex**: 是的，我的意思是，我现在大部分时间都只是坐在终端里。我想我做的那些，比如以前我必须同时打开浏览器窗口和代码窗口的工作，现在少了很多。有些时候我需要检查那些产品导向的流程，但实际上有很多变化，特别是当它们本质上是机械性的时候，比如这种情况下，我甚至不一定需要视觉界面就能完成工作。所以，我经常同时运行两三个，甚至多达五个云代码实例，处理我正在跟踪的不同方面的工作。所以其中一些可能正在协调设计文件和代码库，但另一些可能正在进行探索性工作，回答我关于代码库的问题，编写规范和文档，我们稍后可以谈谈，以及我围绕在代码库中建立技术规范的工作流程。我只是让云在这里继续进行。所以它能够找到设计文件和代码库之间的差异，并且它实际上正在应用这些差异。

<details>
<summary>Original English</summary>

**Alex**: Yeah, I mean I spend quite a lot of my time just sitting here inside of my terminal now. I do so much less I think of the like what I used to have to do where I had to have a browser window open at the same time as having my code window open. There are times where I need to check check those types of product oriented flows, but there's actually quite a few changes especially when they're kind of mechanistic in nature like this where I don't even necessarily have to have the visual in order to get the work done. So I often have two, three, up to five maybe cloud code instances running all at the same time, working on different aspects of the work that I'm tracking. So some of them might be doing things that are just reconciling the design file with the codebase, but other ones might be working on exploratory things, answering questions that I have about the codebase, writing specs and documentation that we could talk about in a little bit and kind of my workflow around grounding technical specifications inside of code bases. I'm just going to allow cloud to progress here. So it was able to find what those differences were between the design file and the codebase and it's actually going ahead and applying them.

</details>

**Claire Vo**: 令我惊叹的是，我认为人们对多模态AI或者说计算机视觉等这些东西的阐述还不够，那就是你不必将文件的PNG图片拖入 **Claude Code**，它通过视觉模型读取并进行推断，然后进行设计。你实际上是通过 **MCP** 进行了这种伪结构化数据到伪结构化数据的转换，这必须具有更高的准确性，但它正在功能性地转换视觉信息，这我觉得非常巧妙。我喜欢它。这是否改变了你对“设计”的心理模型？我的意思是，我认为 **Figma** 总体上已经推动了每个人对如何将设计编码为数据的心理模型，但我很好奇，当你们拥有所有这些多模态模型触手可及，并且可以进行结构化数据到其他结构化数据的转换时，你们是如何演变自己的思维的？这是否在内部激发了关于未来设计样貌的任何想法？

<details>
<summary>Original English</summary>

**Claire Vo**: And what's amazing to me and I think people don't don't articulate enough about let's call it a multimodal AI or computer vision all this stuff is it doesn't have to be you dragging a PNG of the file into **Claude Code** it it reading that through a vision model and then making some inferences about it and designing it. You're actually doing this like sort of pseudoructured data to pseudoructured data translation through the **MCP** which has to have much higher accuracy but it's translating functionally visual information which I think is just so nifty. I love it. Has this changed kind of your mental model of what does I mean I think **Figma** in general has pushed forward everybody's mental model of like how you encode design into data but I'm curious how are you all evolving your thinking when you have all these multimodal models at your at your fingertips when you can do kind of structured data to other structured data translations. Has that inspired any ideas internally about what the future of design looks like?

</details>

**Ghee**: 真正有趣的是，我们在这个过程中扮演的角色，有点像真正地向上游移动了。我们正处于一个我发现几乎是“奢侈”的时刻，以前我们必须非常习惯于做出非常敏锐的产品决策，而且几乎是立即做出，并且能够快速地推理事物，快速地达到非常好的工艺水平，因为大部分时间都花在了构建上。所以你在这方面花费的时间越长，P0就变成了P1和P2。所以现在我们实际上处于这样一个阶段，更多的优先级可以越过“截止线”。而且我们也可以在规划阶段花费更多时间。你问我它是从设计开始还是从代码开始？实际上，我很多时候都是从规划开始，只是真正地集思广益，允许自己沉浸在各种可能性中，然后进行迭代，如果我需要它只能存在于代码中，那它就是代码，否则我会在设计中发散。但我认为设计更多地处于这种“我们应该构建什么”的对话阶段，我们以前也处于这个阶段，但那时非常匆忙。而现在我们可以花更多的时间在其中，因为我们知道实际上构建会快得多。所以我们这样做，然后另一方面，我们在工艺上花费更多时间，因为我们可以，因为我们可以追求更高的想法。因为以前我们可能会想，好吧，我不知道，希望工程师能理解我的意图。现在我可以在那个时刻花费更长的时间。

<details>
<summary>Original English</summary>

**Ghee**: What's really interesting about like our our role with all of this is kind of really moved upstream. And we're in this really I find it almost decadent moment in time where before we had to be so conditioned on really sharp product decision-making skill that would have happen like almost immediately and being able to like quickly reason with stuff and quickly get to really good craft because the bulk of the time was spent building. And so the longer you ate into that, the more P zeros became P1's and P2s. And so now we're kind of actually at this point where more of the priorities can make it above the cut line. And also we can spend a lot more time in the planning stage. You ask me like does it start with with design or with code? Actually, I start a lot of it with planning and just like really riffing and allowing myself and indulging in the the possibilities and then kind of riffing in in something that you know if if it I need it to be something that can only exist in code, it will be code if otherwise I will diverge in design. But I see design is much more at this kind of like what should we be building stage of the conversation which we were before but it was like a very rushed moment there. And now we can spend a lot more time in it because we know that actually the the building will happen a lot quicker. And so we do that and then on the other side we spend a lot more time in the craft because we can because we can reach higher for ideas. Because before we were like, well I don't know, hopefully an engineer will get my intention. Now I could spend a lot a lot longer in that moment.

</details>

**Claire Vo**: 我喜欢你称之为“奢侈的时刻”，因为两年前在Config大会上，我做了一个关于产品管理未来的演讲，我说这是一个“是的”时代，这种“截止线”的想法必须消失。我们都参加过多少次规划会议，我们看着一个设计，工程师会说：“哦，那只会增加范围，我们必须削减范围。”或者我们看着一个优先级规划会议，我们说：“哦，那个每个人都讨厌的小修复，我知道每个人都讨厌它，但它不是P0优先级。所以，它必须，你知道，明年再做。”我确实认为这种你可以真正拥有“富足”的想法，一种功能层面的“富足心态”，以及一种工艺层面的“富足心态”，你可以投入打磨和所有使这些体验变得美好的东西，是现在与AI合作的好处之一。

<details>
<summary>Original English</summary>

**Claire Vo**: I love that you called this a decadent moment because it was two years ago at config actually I gave a talk on the future of product management and I said this is the era of yes like this idea of the cut line has to disappear and how many planning meetings have we all been in where we look at a design and an engineer goes oh well that's just going to add scope like we got to cut scope or we look at a a priority planning meeting and we say oh that that that little fix that everybody hates in our app I know that everybody hates it, but it's not a P 0 priority. So, it's got to, you know, go go next year. And I do think this idea that you can really have an abundance, a feature level abundance mindset is is and and the craft level abundance mindset where you can put the polish and all the things that make these experience are one of the benefits of working with AI right now.

</details>

**Alex**: 所以，它在这里完成了。它应用了补丁，现在你可以看到应用程序已经更新了，它看起来和 **Figma** 设计完全一样，但是完全在代码中应用了。

<details>
<summary>Original English</summary>

**Alex**: So, it's done here. It's applied the patch and now you can actually see that the app has been updated and it looks exactly like what the **Figma** design looked like but has been applied entirely within code.

</details>

**Claire Vo**: 所以我们在这里得到的好处，只是为了那些没有观看的人重申一下，就是我们拿了一个现有的应用程序，它已经与 **Figma** 中的原始文件相去甚远。这种情况在我们所有人身上都发生过。我们通过编程将其拉入 **Figma**。我们用我们精美、经过微调的对生拇指和手指，在 **Figma** 中实际拖拽并创建了我们想要的完美设计。然后，像 **Alex** 这样的工程师可以非常容易地将其拉入 **Cloud Code** 或任何你的代码环境。构建了代码，甚至没有看。我的意思是，你确实看了，但就像不必看设计，现在它就可以像素完美地部署。每个人都很高兴。这就是它的运作方式。

<details>
<summary>Original English</summary>

**Claire Vo**: And so the benefit we got here just to reiterate for folks that are not watching is took an existing app that had drifted very far from the original file in **Figma**. Happens to the best of us. We programmatically pulled it into **Figma**. We used our beautiful fine-tuned opposable thumbs and fingers to actually drag and create the perfect design that we wanted in **Figma**. And then that's very easily pulled in by an engineer like **Alex** **Cloud Code**, whatever your code is. Built the code, didn't even look. I mean, you you did look, but like didn't have to look at the design and now it can be deployed pixel perfect. Everybody's happy. That's how it works.

</details>

**Ghee**: 就是这样。

<details>
<summary>Original English</summary>

**Ghee**: That's how it works.

</details>

### 从代码开始设计

**Claire Vo**: 好的，现在我们只是在撞击橡胶墙，然后我们走向另一个方向。所以你要向我展示我们如何可以从没有设计开始，从 **Cloud Code** 进入设计，然后我猜再回到 **Codeex**。这一集将只是来回的乒乓球。那么 **Alex**，作为一名工程师，你如何在没有设计设置的情况下，实际开始在 **Figma** 中设计一些东西？

<details>
<summary>Original English</summary>

**Claire Vo**: Okay, now we're just hitting the rubber wall and we're going the other direction. And so you're going to show me how we can start with no design, go from **Cloud Code** into a design, and then I'm presuming back to **Codeex**. And this episode's just going to be a pingpong back and forth. So **Alex**, how would you as a engineer know design setup actually start designing something in **Figma**?

</details>

**Alex**: 通常情况下，代码库会远远领先于实际的设计文件，而且有些状态或工作流程在设计文件中根本不存在。我想向你展示一个小演示，说明你如何实际获取所有这些在设计文件中不存在但存在于代码库中的状态，将它们导入 **Figma** 设计文件，以便你的设计协作者可以直接在此基础上工作。我一直在为一个我正在开发的新应用程序的注册流程工作。注册流程有几种不同的状态，但并非所有这些状态都存在于我的设计文件中。所以，我可以说：“将注册流程的所有五种状态发送到 **Figma**。”现在，代理将读取我的代码库，理解我所说的这五种状态。对于每一种状态，它将逐一导入到 **Figma** 中，这样 **Figma** 文档就会把所有这些状态并排展示出来，我的设计伙伴 **Ghee** 就可以在此基础上进行工作。

<details>
<summary>Original English</summary>

**Alex**: Often times like the codebase gets way ahead of where the actual design file is and there's states or workflows that just don't exist at all within the design file. And I want to show you a little demo of like how you can actually take all of those states that don't exist within your design file, but exist within your codebase, bring them into a **Figma** design file so that your design collaborators can work directly off of those. Here I've been working on a signup flow for a new app that I've been working on. And there's a few different states of the signup flow, but not all of those states exist within my design file. And so what I can do is say, "Send all five states of the sign up flow to **Figma**." Now the agent's going to do is read my codebase, understand what I'm referring to when I say those five states. And for each one of those, it's going to individually import that one by one into **Figma** such that the **Figma** document will then have all of those states laid out all side by side so that **Gee**, my design partner, can work against it.

</details>

**Claire Vo**: 是的。再次，我只是要回到以前的样子。我回想起我以前发送给工程团队的设计包，其中每一个错误状态，每一段文案，每一个“这个闪黄光，那个闪红光，这个有橙色，这是悬停状态”都被像素级地精心记录、设计和制作。而现在，即使是设计师，也能说：“你能提醒我，当电子邮件正确但密码不正确时，这个登录流程会发生什么吗？我们的错误状态是什么？”而无需进入代码，也无需在生产环境中复制它，这非常强大。然后你再在此之上添加，哦，太酷了，它实际上是一个 **Figma** 组件，所以我可以进去编辑它。它不仅仅是一个截图，这非常好。那么现在，这在 **Figma** 里吗？

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. Again, I'm just going to go back to how it was before. And I'm having flashbacks to these design packages that I used to send over to engineering where every single error state, every bit of copy, every this flashes yellow, this flash is red, this has orange, this is the hover state was documented, designed, lovingly crafted pixel by pixel. And the ability here again I think for a designer even to say like can you remind me what happens when you have a correct email but an incorrect password on this signin flow and like what is our error state without having to go into the code and without having to replicate that in production is pretty powerful. And then you layer on top of that oh cool it's actually in a **Figma** component so I can go in and edit it. It's not just a screenshot is is quite nice. And so right here, is this in **Figma**?

</details>

**Alex**: 这些都是它打开的浏览器窗口。但现在这里是 **Figma** 文档，其中所有这些状态都并排显示。你可以看到，它们每一个都作为这个精确流程的一部分被导入到同一个 **Figma** 文件中。我现在可以将这个链接发送给我的设计伙伴，这样当我在我的代码库这边工作时，他们就可以开始在此基础上进行迭代，尝试不同的颜色、图案等等，而我则在做我的日常开发工作。

<details>
<summary>Original English</summary>

**Alex**: These are all the browser windows that it opened up. But here is now the **Figma** document that has all of those states laid out side by side. And you can see that each one of them was imported as part of this like exact flow all into the same **Figma** file. And I can now send this link over to my design partner so that while I'm working on my side of the codebase they can actually get started on riffing on this, experimenting with different colors, patterns, etc. all while I'm doing my my normal development work.

</details>

**Claire Vo**: 这感觉就像是设计师和工程师的结对编程。这是一种非常有趣的新方式，**Ghee**，正如你一开始所说，这是一种新的工作流程，你可以在其中思考，你们双方都在应用程序的同一部分的不同表达中，并且可以使用 **MCP** 作为连接器在这里非常快速地来回工作。

<details>
<summary>Original English</summary>

**Claire Vo**: This feels like pair programming for designers and engineers together. It's such an interesting new way, new, **G**, as you said at the beginning, like a new workflow to think about where you're both in different expressions of the same part of the app and you can work very quickly back and forth using the **MCP** as a connector here.

</details>

**Ghee**: 完全正确。

<details>
<summary>Original English</summary>

**Ghee**: Exactly.

</details>

### 同步与异步协作

**Claire Vo**: 你发现自己因此做了更多同步工作还是更多异步工作？

<details>
<summary>Original English</summary>

**Claire Vo**: Do you find yourself doing more synchronous work or more asynchronous work because of this?

</details>

**Alex**: 我发现异步工作现在倾向于成为我的默认模式。然而，我确实发现与协作者（无论是其他工程师还是设计师）同步工作，尤其是在远程环境中，有一些非常特别的地方。你知道，你可以在基本上全天候工作，无论大家身在何处，这有很多好处。但把大家聚集在一个地方，拥有那种协作画布体验，真正把大家凝聚在一起，我认为仍然是无法完全取代的，即使是拉取请求，即使是屏幕共享。当人们可以在这里自由发挥，而其他人可以在同一个共享空间中做完全不相关的事情，并实时看到彼此工作时，感觉就是不一样。我认为有了这种工具，它确实重新激活了很多同步工作。我们过去常常，你谈到包的交付，我经常觉得这就像《人猿星球》的比喻，我们过去在技术科幻的未来走得太远，但现在又回到了这种传递U盘、这是我的版本、这是版本控制东西的状态。而现在有了这个，我就可以和我的团队一起在一个想法上工作，我们重新发现了在那些高峰期时的能量，那时我们都在一起进行原型设计，把所有东西都投入到同一个地方，感觉不像“哦，我要做这个，明天我给你看一个版本，然后你给我看一个版本”，而是势头会带来更大的势头。所以让团队一起集思广益、互相支持、尝试新事物真的很棒。会有一些时刻，我会说：“好吧，我想我们在这里进行了一次很好的即兴创作。现在，让我们深入研究。”那没关系。让我们去收敛。但即使在远程环境中，跳进一个 **Figma** 文件，看到光标飞来飞去，尝试各种东西，这仍然有一些特别之处。我还没有找到更好的替代方案。我希望如果有人找到了，会是我们。说实话。

<details>
<summary>Original English</summary>

**Alex**: I find that asynchronous work tends to be like my default now. However, I do find that like there's something that's really special about synchronously working through things like with your collaborators, whether it's other engineers or designers, remote oriented environments, like you know, you you get a lot of benefits about being able to like work, you know, around the clock basically, regardless of, you know, where everyone's located. But there's something that's still really special about putting everyone together in one place and having that collaborative canvas experience that really brings everyone together I think is still something that you can't quite replace even with pull requests, even with you know screen share. There's something that feels different when you know folks can freestyle over here and other folks can be working on something else totally unrelated but in the same shared space and seeing each other like kind of work in real time. I think with with this kind of tool it's really reenabled a lot of the sync work we went it's funny you're talking about the handoffs of packages it's I often feel it's it's like the planet of the apes analogy where we've gone so far into the future in the past where like technology is sci-fi but we're back in this like thing of handing over USB sticks here's my version here's version controlling things and you know now with this I can like be working on an idea with my team together and the energy that we've rediscovered around those spikes where we're all just prototyping and throwing it all into the same place and it doesn't feel like oh I'm going to work into this and tomorrow I'll show you a version and then you will show me a version like momentum begets momentum and so having the team together riffing and yes anding and trying this stuff out is really great. There are going to be moments where I was like, "All right, I think we've we we've had a good good jam here. Now, let's go deep." And that's fine. Let's go converge. But there is something to be said about even in remote environments jumping into a **Figma** file and just seeing cursors flying around and trying out stuff. I haven't found a better alternative for that. And I'm hoping if anybody does, it'll be us. To be honest,

</details>

**Claire Vo**: 我想指出的一点是，我们在这个播客中谈论了很多关于工程繁重工作以及通过AI减少工程繁重工作的问题，**Alex**，我们可能很快就会看到一些，关于你如何构建你的流程并减少你所说的那些机械性工作或战术性工作。设计中也存在繁重工作。有复制粘贴文件。有这种“版本最终版V2 V3最终版老板已批准开玩笑最终版”之类的。你知道，有谁在调整这些圆角，检查字体是否匹配，或者大小写是否正确，构建一个漂亮的产品需要大量的设计繁重工作。我看到的另一件事是，AI可以剥离很多这样的工作，再次让你专注于更高杠杆地利用你的才能和对产品的贡献，你认为这会带来一个更高参与度的团队。

<details>
<summary>Original English</summary>

**Claire Vo**: One one thing that I want to call out is we've talked a lot on this podcast about engineering toil and reducing engineering toil through AI and **Alex** we might see some of that in in just a little bit of how do you structure your process and reduce the you know as you say the mechanistic parts of your work or the kind of tactical parts of your work. There is design toil out there. There is copying and pasting files. There is this version final final V2 V3 final final signed off by boss just kidding final again like there you know there's who's rounding these corners and checking that you know the fonts are matching or that the capitalization is right there's a lot of design toil that goes into building a beautiful product and the other thing that I see is AI can just strip a lot of that work away and again leave you focusing on the higher leverage uses of your talent and contribute contributions to your product which you think results in a higher engaged team.

</details>

**Ghee**: 太棒了。

<details>
<summary>Original English</summary>

**Ghee**: Great.

</details>

### 工程师的AI技能

**Claire Vo**: 好的，我们将以最后一个用例结束，它与 **Figma** 无关，但在你的工作流程中非常强大，**Alex**，那就是每个人最喜欢的新AI栈原语——技能。所以，让我们看看你作为一名工程师发现有用并安装的几个技能，以及你为什么选择它们，为什么构建它们，以及你如何使用它们。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay, we're gonna wrap with one last use case which is not **Figma** related but is has been really powerful in your workflow, **Alex**, which is everybody's favorite new primitive of the AI stack, the skill. So, let's see a couple of skills that you found useful to install as an engineer and why you picked them, why you built them, and how you use them.

</details>

**Alex**: 所以我可能在这里有点少数派，我实际上很多技能都是自己编写的，或者让AI为我编写。很多都是基于持续拥有，我把它们看作是大型的宏，就像我可以在工作流程的任何时候调用的提示。我经常使用的一个是这个我编写的 `/ship` 技能。我在我的工作流程中一直使用它。通常为了将东西放入像 **Figma** 这样的大型代码库中，需要做很多工作来确保测试通过，确保所有预检事项都井然有序，然后一旦推送到仓库，还要检查CI，确保它正确构建并且全部绿色，这样我才能真正合并它。以前我必须在每一步都“照看”这些流程，这给我带来了很多摩擦。所以我编写了这个 `/ship` 技能，我一直都在使用它。所以在 **Figma** 内部，我们有叫做“dev boxes”的东西，它们是托管的开发环境，我们大部分工作都在其中完成。现在，这个devbox环境的一部分是，我们会自动插入引导脚本，以便当你启动新的开发环境时，你为你的开发环境专门定制的任何内容也会随之放入。所以你现在看到的是我的内部Git仓库，它存储了我所有devbox的个人配置。我这里有几个命令。其中一些在devbox命令下，我稍后会谈到。但这就是我管理devbox本身并通过它创建新技能的方式。所以我有一个用于创建更多技能的技能。以及一些我经常使用的非常流行的技能，比如处理PR反馈和我刚刚提到的 `/ship` 命令。那么它做什么呢？它会启动很多东西，并对仓库运行很多检查。我称之为预检。它们会检查提交中的内容，以确保我没有意外提交一些在这个特定提交上下文中没有意义的东西，还会运行lint，查询各种包，以确保我们正确运行 **Basil** 构建命令。我们使用 **Basil** 作为构建系统。然后最后将其推送到Git仓库。所以，在推送后使用 **GitHub** 拉取请求检查来监控CI检查。为了做到这一点，我们使用 **Buildkite** 作为我们的CI循环，并且它也会被检查。所以一旦构建成功或失败，脚本就会检查 **Buildkite** 的日志是否显示了任何内容。如果存在小的修复，比如lint问题或其他问题，它会自动推送另一个提交来修复那个特定的、更小的问题。它会这样做多达五次，超时时间为1小时，等待CI。还有一些事情是，你知道，就像我之前提到的，鼓励它不要强制推送，以防万一。

<details>
<summary>Original English</summary>

**Alex**: So I may actually be somewhat in the minority here where I I actually just write a lot of the skills myself or ask the AI to write them for me. A lot of it is based on just consistently having I kind of think of them as just like large like macros like prompts that I can invoke at any point in my workflow. One of the ones that I've been using frequently is this `/ship` skill that I wrote. I use it all the time in my workflow. Often in order to get something into a large repo like the **Figma** repo, there's a lot of work that's involved in just making sure tests pass, making sure all of the like pre-flight things are in order and also then once it's pushed to the repository, checking on CI and making sure that it correctly built and is all green so that I can actually merge it. Previously I would have to kind of babysit these you know kind of processes like all the way at every single step and it just created a lot of friction for me. So I wrote this `/ship` skill that I use all the time. So inside of **Figma** we have these things called dev boxes which are hosted development environments that we do most of our work in. Now part of that devbox environment is that we automatically insert like bootstrap scripts in order to make it so that when you boot your new dev environment that any of your customizations that you specifically have for your dev environment also get put alongside it. So what you're looking at right here is my internal Git repository that stores all of my personal configuration for my dev box. And I have a couple of commands here. Some of which are underneath the the devbox command that I'll talk about in a little bit. But this this is how I manage the dev box itself and create new skills via it. So I have a skill for creating more skills. As well as a couple of just really popular ones that I use all the time such as addressing PR feedback and the `/ship` command that I just mentioned. So what does that do? It boots up a bunch of things and runs a bunch of checks against the repository. These are what I refer to as pre-flight checks. They check for things inside of the commit to make sure I didn't accidentally commit something that doesn't make sense in the context of this particular like commit as well as running lint querying for various packages to make sure that we're correctly running the **Basil** build commands. We use **Basil** for build systems. And then finally like pushing it to the Git repository. So monitoring the CI checks after push using **GitHub** pull request checks. In order to do that we use **Buildkite** for our CI loop and that also gets checked. So once the build either succeeds or fails, the script will then check **Buildkite** for whether or not the logs represented anything. And if there are minor fixes like lint issues or otherwise, it'll automatically push another commit in order to fix that particular like more minor issue. And it'll do this up to five times with a 1-hour timeout waiting for CI. There's also a handful of things that are as things as I I went through like encouraging it not to force push just in case...

</details>

**Claire Vo**: 那正是我在找的。

<details>
<summary>Original English</summary>

**Claire Vo**: That's the one I was looking at.

</details>

**Alex**: ...覆盖了我的仓库中的某些内容，或者它提交了凭证之类的东西。但我几乎在我的开发循环中一直使用这个技能，作为一种方式，一旦我达到一个好的状态，我认为这已经准备好可以推送到我们的仓库了，我就会执行 `/ship`，然后离开我的笔记本电脑，它通常会从那里接手。

<details>
<summary>Original English</summary>

**Alex**: ...overwrites something inside of my repository or it commits credentials or things like that. But I use this skill pretty much all the time in my dev loop as a way once I've like hit a good state where I think that this is ready to go and should be like pushed to our repository. I do `/ship` and then walk away from my laptop and it usually takes it from there.

</details>

**Claire Vo**: 我想指出一件事，这给了我很大的启发，那就是我管理过的每一个工程组织都有一个内部维基，上面有那一页，写着“这是你在推送PR之前要做的事情，否则你会阻碍部署流程”。每个工程团队都应该查看他们的入职维基，把每一页，每一个“你应该这样做”都提取出来，变成一个技能，然后让整个团队都能使用。所以我认为我们真的从“SOP”变成了“技能”，或者从“文档”变成了“技能”。我知道很多人把这些东西埋在 **GitHub** 和 **Confluence** 里，你可以让一个人花一周时间把所有这些东西变成一个技能。把它推送到你的仓库里，然后让每个人都能从系统化的方式中受益，推广这些最佳实践。

<details>
<summary>Original English</summary>

**Claire Vo**: So, one thing I want to call out, this is giving me such inspiration, which is every engineering org that I've ever run has an internal wiki that has that page, which is this is what you do before you push a PR and you get in everybody's way in the deploy pipeline. And every engineering team should go through their onboarding wiki and pull every page out, every this is what you should do into a skill and then give give access to that to their entire team. And so I think we're really shifted from this idea of like an SOP into a skill or a doc into a skill. And I know so many folks that have this buried in **GitHub** in **Confluence** and you can just give somebody the job for a week to take all that stuff and make it a skill. Push it in your repo and then let everybody benefit from a systematic way to to roll out those best practices.

</details>

**Alex**: 绝对如此。是的。

<details>
<summary>Original English</summary>

**Alex**: Absolutely. Yeah.

</details>

**Ghee**: 太棒了。它将许多原本只基于良好意图和人们何时想起的流程，变成了可以完全自动化并默认纳入人们工作流程的东西。

<details>
<summary>Original English</summary>

**Ghee**: Awesome. It turns like a lot of these like processes that would otherwise just be, you know, based on best intentions and whenever people remember into something that can be fully automated and brought into people's workflows by default.

</details>

### 闪电问答：设计先行还是代码先行？

**Claire Vo**: 太棒了。好的，这很棒。回顾一下我们所看到的，我们看到了 **Codeex** 到 **Figma** 到 **Claude Code**，再到 **Claude Code** 到 **Figma** 到 **Figma**。基本上只是指出，你不再需要将你的设计视为静态资产。你不再需要只在代码中或只在设计中构建组件。这些东西可以相互作用。我们强调了能够用光标触碰设计并与同事实时协作的好处，然后将你的一些最佳实践编码成技能。将你的一些能力编码成 **MCP** 这样的东西，这样每个人都可以访问这些内容。所以我要问你们几个闪电式问题。你们俩都必须回答。规则很明确，所以你们不能说“视情况而定”。我将从我开始这一集的问题开始，**Ghee**，是代码先行还是设计先行？如果你必须选择一个。

<details>
<summary>Original English</summary>

**Claire Vo**: Amazing. Okay. Well, this has been great. Just to recap what we saw, we saw **Codeex** to **Figma** to **Claude Code** to **Claude Code** to **Figma** to **Figma**. Basically just calling out you don't have to think about your designs as a static asset anymore. You don't have to think about building components in code only or in design only. These things can interact together. Calling out the benefits of just being able to touch the design with your cursor and collaborate live with your colleagues and then encoding some of your best practices into things like skills. Encoding some of your capabilities into things like **MTP** so then everybody can can access this stuff. So I'm going to ask you a couple lightning round questions. You both have to answer. They're clear rules, so you cannot say it depends. I'm going to start with the one that I started this episode with, which is **Gee**, code first or design first? If you had to pick one,

</details>

**Ghee**: 设计先行。

<details>
<summary>Original English</summary>

**Ghee**: Design first.

</details>

**Claire Vo**: 我喜欢。**Alex** 呢？

<details>
<summary>Original English</summary>

**Claire Vo**: I love it. And **Alex**,

</details>

**Alex**: 我可能会选择代码先行。而且我认为...

<details>
<summary>Original English</summary>

**Alex**: I'd probably pick code first. And I think that...

</details>

**Claire Vo**: 这打破了常规。

<details>
<summary>Original English</summary>

**Claire Vo**: Breaking the mold here.

</details>

**Alex**: 这就是为什么 **Figma** 必须制作这个 **MCP**，因为这里永远不会有共识。

<details>
<summary>Original English</summary>

**Alex**: And this is why **Figma** had to make this **MCP** because there will never be never be agreement here.

</details>

**Claire Vo**: 你知道，我的第二个问题是，**Ghee**，我对你的看法很感兴趣，除了软件和设计系统等这些东西，关于AI，你作为一名创意人士，一名设计师，有什么特别兴奋的事情，你希望人们能更多地使用或谈论？

<details>
<summary>Original English</summary>

**Claire Vo**: You know, my second question for you all, and **Gee**, I'm I'm interested in your opinion, is are there any things around AI, not let's put software and, you know, design systems, all this stuff aside, that you're really excited about as a creative, as a designer, that you hope people are going to start using more or talking about more?

</details>

**Ghee**: 说实话，它对我来说只是一个平台，让我能更多地了解我一直好奇的事情。我希望人们能看到它的教育和技能提升方面，而不仅仅是外包任何潜在的能力，因为它发生在所有事情上。任何你想深入了解一点的东西，你现在都可以做到，而无需费力地翻阅链接。它就在那里，无论你何时需要它。我认为我一直在深入研究着色器，以前那纯粹是数学，我根本不应该涉足。而现在我发现，“哦，等等。我可以用自然语言谈论它，我可以了解更多我想了解的具体细节。”

<details>
<summary>Original English</summary>

**Ghee**: Honestly, it's just been a platform for me to just learn more about something that I was always curious about. And I hope that people like see the educational and the upskilling aspect of it and not just outsourcing any potential capability because it happens across everything. Anything you wanted to get a little bit deeper on, you can now do it without having to troll through links. Like it just it's just there at whatever moment you need it. And I think I've been diving deep into getting deeper into shaders which before was just pure mathematics that I had no business playing in. And now I was like, "Oh, wait. I can talk about it in natural language and I can learn more about the spec specifics that I want to learn about."

</details>

**Claire Vo**: **Alex** 呢？

<details>
<summary>Original English</summary>

**Claire Vo**: **Alex**, what about you?

</details>

**Alex**: 是的，我的意思是，我喜欢深入研究。我们在 **Figma** 有一个庞大的代码库，所以我喜欢问所有我一直好奇的疯狂问题。例如，我们有一个内部服务，我不知道它的名字起源。所以我让 **Claude** 根据提交历史去找出它的起源，它带回了一个非常好的故事，关于它是如何产生的，它被多次重命名，那个贡献者多年前就已经离开了公司。所以这些知识有点失传了，但现在，所有这些公司内部的传说，老实说，都嵌入在代码库中，我现在可以找到它了。

<details>
<summary>Original English</summary>

**Alex**: Yeah, I I mean I love going really deep. We have a massive code base at **Figma** and so I love asking all of the like crazy questions that I had always like wondered about. We have an internal service for example that I didn't know the origin of its name. And so I asked **Claude** to go and figure out based on the commit history what the origin was and it came back with a really good story about like how that came to be it got renamed multiple times that you know contributor has since left the company many years ago. So this was kind of lost in the ether but now now all of this lore honestly from the company is actually like embedded inside of the codebase and I can I can find it now.

</details>

**Claire Vo**: 我将把你们两位的兴奋点结合起来，我认为通过查询开源库来学习是一件非常有趣的事情。最近的一个例子是，OpenClaw，现在改名为OpenClaw，发布了，每个人都感到非常神秘。他们说它一夜之间就能工作，为我做了所有这些事情。我就想，我要深入研究这个东西，找出它的架构，以及它实际是如何工作的。那是一次非常有趣的学习经历，只是分解你将如何设计一个代理，以及它构建了一些什么样的新东西。所以这是我推荐的另一件事，无论是深入研究你自己的代码库，还是深入研究一个开源代码库来学习一些东西，这在以前是如此难以实现，而现在你基本上可以在任何开源库上做到，我认为这真的很酷。好的，最后一个问题。**Alex**，我先从你开始，因为你，你知道，我们和 **Claude Code** 有一点点摩擦。我看到你有点冒汗。当AI没有按照你的意愿回复，或者没有做你想做的事情时，你的提示技巧是什么？你会直接 `/clear` 然后杀死它吗？你会怎么做？

<details>
<summary>Original English</summary>

**Claire Vo**: I'm gonna bridge both of your excitement which is I think it's such a fun thing to learn by quering open source libraries. And so the example of this recently is you know open claw now named openclaw came out and everybody's like so mystified. They're like it's working overnight and it's doing all this stuff for me. And I was like I'm just going to go into this thing and figure out how it's architected and how it actually does the thing it does. And it was such an interesting learning experience just to decompose how you would design a an agent and what were some of the kind of new things that it had built. And so that's another thing that I recommend either going deep in your co own codebase or going deep in an open source codebase to learn something is something that was so inaccessible before and now you can do basically on any open source library out there which I think is is really cool. Okay, last question. **Alex**, I'm going to start with you first cuz you you know, we had a tiny bit of friction with with **Claude Code**. I saw you sweat a little bit. When AI is not replying or how you want, it's not doing what you want, what is your prompting technique? Do you do you like just `/clear` and kill it? Like what do you do?

</details>

**Alex**: 那样也可以，但我发现更成功的方法是，在提示中稍微骂几句。我有点不好意思承认，那非常有效。但现在我更常用的方法是说：“我老板对我生气了。”这似乎很管用。它会有点同情你，而且有点可爱。

<details>
<summary>Original English</summary>

**Alex**: That that can work, but I find that the more successful one is it's either cursing a little bit in the prompt. I I you know I am somewhat ashamed to admit that that's extremely effective. But the more common one I I use now is that my boss is mad at me. And it seems to work pretty well. It kind of sympathizes with you and it's it's it's kind of cute.

</details>

**Claire Vo**: 我有时会这样说育儿。我告诉我的孩子们，我吼你们只是因为那样有效。我不想吼你们，但有时那是你们唯一会听的方式。**Ghee**，你呢？你也会这样吗？

<details>
<summary>Original English</summary>

**Claire Vo**: I you know I I sometimes say about this about parenting. I tell my kids I only yell at you because it works. Like I don't want to yell at you but sometimes it's the only thing that you guys listen to. **Gee**, what about what about you? Are you also do you also...

</details>

**Ghee**: 我，我必须采取温和育儿的方式。我害怕机器人接管并阅读我的提示历史。所以，我仍然属于“不犯错”阵营。

<details>
<summary>Original English</summary>

**Ghee**: I I have to take the gentle parenting route. I'm terrified of the robots taking over and reading through my prompt history. So, I'm still on the make no mistakes camp.

</details>

**Claire Vo**: 哦，不犯错。我非常有礼貌。我有点像说“不”。我听起来真的很伤心。我像“不”。或者我采取一种成长型思维的育儿方式，我说我相信你能做到，我相信你有能力解决这个问题。你只要努力，你就能做到所有事情。

<details>
<summary>Original English</summary>

**Claire Vo**: Oh, make make no mistakes. I am very polite. I I kind of go with like no. Like I sound really like sad. I'm like no. Or I do sort of growth mindset parenting where I say I believe you can do it and I believe you're capable of solving this problem. You just apply yourself. You can do all things.

</details>

**Claire Vo**: **Alex**，**Ghee**，这太棒了。我们可以在哪里找到你们，我们如何能帮助你们？

<details>
<summary>Original English</summary>

**Claire Vo**: **Alex** **G**, this was so great. Where can we find you both and how can we be helpful to you?

</details>

**Alex**: 你可以在X上找到我。我在access.io。

<details>
<summary>Original English</summary>

**Alex**: You can find me on X. I'm on access.io.

</details>

**Ghee**: 太棒了。你可以在任何社交媒体平台找到我，用户名是Geizg Gui。通常，如果你关注 **Figma**，我可能就在那里阅读。

<details>
<summary>Original English</summary>

**Ghee**: Amazing. And you can find me on any social media platform as Geizg Gui. And just generally if you figma, chances are I'll probably be reading it.

</details>

**Claire Vo**: 太棒了。很高兴邀请到你们。我非常兴奋。我受到了很大的启发，关于我们如何通过代码和 **Figma** 管理我们的YouTube缩略图。所以我要去尝试一下，感谢你们加入“我如何AI”。

<details>
<summary>Original English</summary>

**Claire Vo**: Amazing. Well, it was so great to have you. I am so excited. I have gotten I've been very inspired about how we can manage our YouTube thumbnails through code and **Figma**. So I'm going to go experiment with that and I appreciate you all joining How I AI.

</details>

**Alex**: 谢谢邀请我们。

<details>
<summary>Original English</summary>

**Alex**: Thank you for having us for having us.

</details>

**Ghee**: 太棒了。

<details>
<summary>Original English</summary>

**Ghee**: Great.

</details>

**Claire Vo**: 非常感谢观看。如果你喜欢这个节目，请在YouTube上点赞并订阅，或者更好的是，留下你的评论和想法。你也可以在Apple Podcasts、Spotify或你最喜欢的播客应用上找到这个播客。请考虑给我们评分和评论，这将帮助其他人找到这个节目。你可以在howiipod.com上查看我们所有的节目并了解更多信息。下次再见。

<details>
<summary>Original English</summary>

**Claire Vo**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>