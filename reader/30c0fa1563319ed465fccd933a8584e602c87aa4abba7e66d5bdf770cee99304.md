---
author: AI Engineer
date: '2026-10-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LQW_Wvqhp04
speaker: AI Engineer
tags:
  - agentic-software-factory
  - code-confidence
  - lean-software
  - independent-verification
  - cognitive-surrender
title: 代码充沛与信心匮乏：构建面向智能体时代的企业软件工厂
summary: Sonar 首席执行官 Tariq Shaukat 指出，AI 智能体带来代码量激增，但“人在回路”无法规模化，且面临认知投降与长任务错误复合等限制。企业需要借鉴精益制造理念，通过明确意图、导轨引导、独立验证与审计证据四要素公式，工程化构建可交付信心的智能体软件工厂。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Tariq Shaukat
  - Satya Nadella
companies_orgs:
  - Sonar
  - Toyota
  - Meta
  - PayPal
products_models:
  - SonarQube
  - Sonar Vortex
  - Claude Mythos
media_books: []
status: evergreen
---
### 制造业的质量革命与精益启示
>> 呃，我是 Tariq Shakir。正如大家刚才听到的，我是 Sona 的首席执行官。我们今天来这里是想探讨一下，我们一直以来是如何帮助企业构建真正适用于大型机构的软件工厂。我觉得从考察现实中的工厂切入会是一个有趣的角度，因为我们懂得如何建造实体工厂。对于在座那些稍有白发、经历过那个时代的人来说，大家或许还记得 20 世纪 80 年代。在 80 年代，你能找到性能非常好的汽车。但如果你看一下这里的图片，并且回忆起那个时期，那些车各个部件的拼合其实并不那么严丝合缝，对吧？不同的部件之间会留下很大的缝隙。它们确实是非常好的车，但就是没能达到原本应有的那种运行状态。后来，丰田、特别是雷克萨斯推出了一则广告。广告里展示了一件极其简单的事：一颗滚珠轴承顺着这辆车的接缝滚过。这在当时算得上是一场革命，因为它表明你确实可以制造出一辆严丝合缝、完全契合的汽车。不再是过去那种为了产量而生产、造出来再去修修补补的陈旧思维模式，而是真正转变成一种专注于一次就做好交付、杜绝返工、追求客户满意度的全新思维。

<details>
<summary>Original English</summary>
>> Uh I My name is Tariq Shakir. I am the CEO of Sona, as you just heard. And we're here to talk today about how we have been um helping companies build software factories that actually work for enterprises. And I thought it'd be an interesting way to start to start looking at actual factories cuz we know how to build actual factories. And for those of you who have a little bit of the gray hair and all of this sort of thing, you may uh remember the 1980s. And in the 1980s, you could find cars that were really good cars. But if you look at the picture here and if you remember those times, the cars like didn't quite fit together perfectly. Right? You'd have different pieces that would leave big gaps. It would be really good cars that just didn't kind of work the way they were supposed to. And then uh Toyota and particularly Lexus came out with a commercial. And it showed something very simple, which was a ball bearing running across the seams of this car. And it was kind of revolutionary at the time because it showed that you could actually build a car that fit together perfectly. And instead of building for volume and building and then fixing the old mindset, you could actually have a mindset focused on ship it right, on no rework, on customer happiness.
</details>

这并非单一维度的转变。当时发生的事情是，人们真正开始以不同的视角审视工厂。他们开始着手设计并建造那些旨在输出高品质产品的工厂。其中有许多原则我认为在今天依然能引起共鸣：
第一，**质量优先于数量**。
第二，**修复系统本身**，而非仅仅针对眼前看到的个别表象对症修补。
第三，**面向可制造性进行设计**，而不是先各自设计轮毂、清洗水壶或其它部件，之后再寄希望于它们能刚好拼合在一起。
第四，**问题出现时立刻解决**，而不是把皮球踢到后面、留到最后才去处理。
第五，**全员赋能**。任何一线员工都能拉停产线，而不仅仅是主管有权这么做。

<details>
<summary>Original English</summary>
And there was not This was not a single change. What happened was that people really started thinking about the factories differently. They started engineering a building factories that were engineered to deliver quality. And there's a number of different pieces that I think still resonate today. The first is you prioritize quality instead of volume. The second is that you fix the system, not just individual symptoms that you see. The third is that you design for something that can be built as opposed to designing the wheels and designing the washer bottles and whatever it is and then hoping it fits together. You solve problems as they occur as opposed to kicking the can down the road and fixing it at the end. And you empower everybody. Anyone could stop the line, not just the boss.
</details>

### 智能体时代带来的生产力剧变
我为什么要谈论这些？因为现代软件开发实际上全盘吸收了所有这些原则。如果思考一下我们当下是如何构建软件的，以及什么被奉为最佳实践，其中大量的术语和实践正是源于丰田生产方式的理念。敏捷开发、看板、SRE 领域的错误预算、持续集成……这些概念在某种程度上都源于“我们该如何构建行之有效的工厂”这一构想。到目前为止，这在软件开发领域运转得非常出色。然而，正如我们所知——如果大家不理解这一点，今天也不会坐在这里——智能体正在改变游戏规则。随着智能体对规则的重构，一些反常的现象开始出现。首先，这是上个月发表的一项研究，探讨的是在软件开发生命周期中引入异步智能体所带来的影响。我相信在座很多人都已经见过了：编写的代码行数出现了爆发式增长，**激增了 2450%**；提交次数也有所上升。所以就产量而言，代码的生成现在变得轻而易举且极度充沛。顺便提一句，越来越多的人——我相信在这个房间里的很多人也在思考：“好吧，既然代码生成如此容易且充沛，那我该如何将其自动化？我该如何构建智能体软件工厂来帮助实现这种自动化和规模化？”我们刚刚完成了所谓的开发者代码现状调查，下个月会正式发布，这里先给大家做个小小的预告：在今天接受我们访谈的开发者中，有 5% 的人表示他们正在运行智能体软件工厂；但有 34% 的人预计一年内会这么做，而在金融服务行业这一比例高达 39%。因此，大家都在思考究竟该如何构建这种下一代工厂。

<details>
<summary>Original English</summary>
Now, why am I talking about this? It's actually because modern software development actually embraced all of these principles. If you think about how we build software today, what is considered best practice, a lot of the terms and the practices came from that idea of a Toyota production system. Agile, Kanban, error budgets if you're in the SRE world, continuous integration, these ideas all kind of sprung from this notion of how do we build factories that work. And it's worked really well for us in software development so far. But agents, as we all know, you wouldn't be sitting here if you didn't understand that agents are changing the game. And as agents are changing the game, weird things start to happen. First of all, this is research that was published last month of the effect of implementing asynchronous agents in your development life cycle. And I'm sure many of you have seen this. You have an explosion of the number of lines of code written up 2,450%. You have an increase in the number of commits. So, the volume, code creation is now easy and it is now abundant. And by the way, more and more people, I'm sure many people in this room are saying, "Okay, if it's easy and abundant, how do I automate it? How do I build factories, agentic software factories that help automate and scale this?" And today, we just finished our what we call state of code developer survey. It'll be out next month, but this is a little preview. Today, 5% of developers that we spoke to say that they're running agentic software factories, but 34% said in a year they expect to and 39% in financial services. So, people are thinking about how do you actually build these next generation factories.
</details>

这里面存在一些隐患。首先是安全风险，智能体在帮你构建产品方面非常出色，但同样也可以极其高效地用来实施入侵、发起攻击、挖掘漏洞、找出质量缺陷等等。因此，正当我周末准备这份演讲内容时——这算是一点来自丰田生产方式的“准时制”——萨提亚·纳德拉在 X 上发布了这篇文章。如果您还没读过，我认为这是一篇每个人都应该深刻领会的好文章。他在文中谈及的要点之一是企业内部模型的内部人员风险。他强调的一点是，需要建立一种围绕强大的确定性系统设计、人工控制措施以及可靠的操作规程所构建的工程化遏制与治理方法。这深深地引起了我的共鸣，因为我们所目睹的正是一场软件工厂设计、或者更宽泛地说软件开发领域的范式转变：我们需要通过工程化的手段，在智能体软件工厂中构建出能够带来信心与质量的系统。

<details>
<summary>Original English</summary>
And there's a a couple of gotchas in here. Security risk, the agents can work really well to help you build stuff. It can also work really well to help you hack stuff, help you attack stuff, find vulnerabilities, find quality issues, etc. And so, as I was writing this um presentation kind of over the weekend, a little just-in-time again from the Toyota production system, um Satya Nadella posted this article on X. If you haven't read it, I think it's a great article that I think everyone uh should internalize. But one of the things he was talking about insider risk of models inside of companies. And one of the things that he talked about was the need for an engineering approach to containment and governance built around strong deterministic system design, human controls, and reliable operating procedures. And this really [clears throat] resonated with me because what we are seeing is a paradigm shift in software factory design or software development, let's call it more broadly, that we need to engineer, we need to build systems that engineer confidence and quality into agentic software factories.
</details>

### 面向智能体软件工厂的五大瓶颈
为了开始付诸实践，我认为看清我们当下所面临的局限至关重要。这里的难点究竟在哪里？我想着重指出其中的五大挑战：
第一个难点是：**人在回路无法规模化**。这在当前这个会场里可能算不上多大争议，但实际上我接触过的几乎每一家公司，当我问他们“你们的 AI 治理策略是什么”时，他们列举了各种措施后都会说：“但别担心，我们有人在回路把关。”然而“人在回路”的症结在于，正如我刚才提到的，虽然代码行数激增了 2450%、代码提交量增加了 240%，但同一项研究显示，**版本发布量仅增加了 30%**。我们还没弄明白如何从规模化产出跨越到规模化交付。这需要自动化，需要全新的工具。更重要的是，现在我每天都能看到一个概念——相信在座许多人同样深有体会——即所谓的**认知投降**。就在几个月前完成的一项研究探讨了人类同意 AI 意见的频率：结果发现，当 AI 正确时，人类有 93% 的几率表示赞同；而**当 AI 出现错误时，人类仍有五分之四的概率表示赞同**。对吧？所以问题不仅在于“人在回路需要提高速度”，而是这种机制在智能体时代实际上已经失效了。这是第一个难题。

<details>
<summary>Original English</summary>
So, to start doing that, I think it's important to understand the limitations that we're facing. So, what's the hard thing about this? And there's five that I'm going to call out. The first is that human in the loop doesn't scale. And this may be, I don't know, to this room it may not be all that controversial, but every virtually every company I talk to, I say, "What's your AI governance strategy?" And they give me all the stuff and they say, "But don't worry, we have humans in the loop." And the problem with humans in the loop, as I mentioned earlier, 2,450% increase in lines of code, 240% increase in commits, but the same study showed only a 30% increase in releases. We haven't figured out how to scale from producing stuff to shipping stuff. There's automation needed, there's new tools needed, and really importantly, this is a concept that really I I see it every day now, and I'm sure many of you do as well, uh called cognitive surrender. Uh and this study was done just a couple months ago, and it looked at how often do humans agree with AI? And it turns out they agree with AI when AI is right 93% of the time. And four out of five times they agree with it when the AI is wrong. All right? So, it's not that human in the loop is Yeah, we just need to make things faster. It's actually that it doesn't work in the agentic era. So, that's problem one.
</details>

第二个难题在于：**智能体在大型复杂代码库中表现吃力**。它们非常非常聪明，但你必须理解代码库内部的运转机制才能对其展开工作。左边是一项关于代码转换的研究，它展示了当代码库规模在 10,000 行代码时，智能体能够达到 91% 的正确率；

>> [clears throat]

>> 但是当规模扩大到哪怕仅 50,000 行时——我相信现场所有人平时处理的代码库都远比这个庞大得多——在尝试转换这 50,000 行代码时，其准确率就发生了雪崩。类似地，另一项研究考察了在大型复杂代码库上完成相同任务需要消耗多少 Token，结果其差异达到了 **30 倍**——不是 30%，而是 30 倍。究其原因，是因为智能体将海量的 Token 都耗费在了尝试理解如何导航代码库、探索代码结构等事情上。这有点像如果我想从洛杉矶前往这里，假如随机选一个起点：碰巧选在怀特普莱恩斯，我就能非常快地到达纽约；但如果选在阿尔伯克基，就会耗费我大量的时间和极高的成本。智能体面临的完全是同样的情况。

<details>
<summary>Original English</summary>
Problem two is that agents struggle with large complex code bases. They're very very smart, but you need to understand what happens in a code base in order to work on it. The left-hand side is a study that was done on code translation, and what it shows is that
>> [clears throat]
>> the agents were able to get it right 91% of the time when the code base was 10,000 lines of code. And by the time it got to even 50,000, and I'm sure everyone in this room operates off of much bigger code bases than this, but when it was trying to translate 50,000, the accuracy collapsed. Similarly, another study looked at um how many tokens does it take on a large complex code base to complete the same task, and the variance was 30x, not 30%, but 30x, and the reason is because it the agent spends a huge amount of their tokens trying to understand how to navigate the code base, the structure of the code base, things like this. And it's kind of like if I'm trying to go from uh from LA to here, and if I pick a random starting point. If I happen to pick White Plains, I will get to New York pretty quickly. If I pick Albuquerque, it's going to take me a long time and a lot of cost. Same thing happens with agents.
</details>

第三个重要概念：**误差会复合累积**。这是来自 METR 的一项研究，大家可以在他们的官网上找到。他们评估的是智能体在完成人类可执行任务方面的有效性，所采取的衡量方式是看其能否完成需要人类花费 X 个小时的任务。大家可以看到，他们公布的最新版本 Claude Mythos preview 能够很好地完成耗费人类 16 个小时的任务。这确实非常出色，但小字说明中包含一个重要的前提条件：**这是在 50% 的准确率基准下**。如果把准确率要求调高到 80%，这条曲线就会大幅平缓，因为在执行长时间运行的任务时，误差会不断复合。如果每个单项任务的准确率为 95%，到了第 20 个步骤时，整体准确率就只剩下了 36%。对吧？所以这也是我们在软件工厂中必须应对的又一难题。

<details>
<summary>Original English</summary>
Errors compound. This is another important concept. This is a study out of meter and meter looks at and you can find this on their website. They look at how effective are agents at completing tasks that humans can do. And the way they look at this is can you complete a task that takes X number of hours. So you can see here the Claude Mythos preview which is the latest version that they've published was good at completing tasks that take a human 16 hours. Okay, so that's really good but there's an important caveat in the fine print here which is this is at 50% accuracy. When you add it when you dial up the accuracy to 80% it the curve flattens substantially because as you do long running tasks errors compound. If you have 95% accuracy on each task by the time you're at 20 steps, you have 30 36% accuracy. Right? And so that is another issue we have to deal with in software factories.
</details>

我在这里列出的或许是最具冲击力的一个标题，即第四点：**大语言模型是不可靠且追求奖励的裁判**。正如大家所知，我们总会遇到这样的疑问：“难道就不能直接问大模型吗？”因此人们也一直在对此进行研究。左边展示的成果来自 PayPal AI 研究实验室，他们在这个月刚发表了一篇论文，发现在所谓的“完全一致的重复测试”中，根据模型和具体场景的不同，有 **7% 到 17% 的判定结论发生了改变**。面对完全相同的问题，有 7% 到 17% 的概率会得出不同的答案。此外，如果开始提出质疑——这是来自 Meta 的一项最新研究——只要进行非常简单的反问：“你确定吗？”，它在 7% 到 34% 的情况下就会改变原先的想法，这同样取决于具体的模型。所以向 AI 裁判询问两次，你很可能会得到不同的答案。

<details>
<summary>Original English</summary>
Probably the most aggressive headline I put in here is is this fourth point that LLMs are unreliable reward seeking judges. Um as you know, so the question that we always get is well can't you just ask an LLM? And so people have been studying this as well and this is all again the first on the left hand side is from PayPal AI's research lab. They published a paper this month actually and found that between depending on the model and the situation between 7 and 17% of verdicts change across what they called identical replications. Ask the same question, got a different answer between 7 and 17% of the time. And if you start challenging, this is a study out of meta now. If you start challenging the LLM, are you sure? Very simple challenge. It'll actually change its mind 7 to 34% again depending on the model. So you ask the AI judge twice and you may get a different answer.
</details>

最后一点，我不会在此过多赘述，因为我认为这对大家来说显而易见：随着漏洞利用时间窗口逼近于零，我们进行响应的能力面临着极大的挑战。因此，我们认为**防御必须是软件工厂在设计时就内置的要素**，必须通过工程化手段深深融入到工厂之中。

<details>
<summary>Original English</summary>
And then lastly and I won't dig into this one too much cuz I think it's probably self-evident to everyone as the time to exploit near zero, the ability for us to respond is incredibly challenged. And so, prevention is something that we believe the software factory has to bake in to the design. Has to engineer into the factory.
</details>

### 代码信心公式与落地实践
基于对这些问题的思考，我们梳理出了所谓的**代码信心公式**。它本质上探讨的是：你该如何构思并构建一座软件工厂，来交付我们所有人都渴望的成果——即我们能够感到有信心的结果？不是盲目信任，而是让我们能够感到踏实、能够底气十足地向管理层、客户、股东、CEO 以及董事会交代“是的，我相信这座工厂运转良好”的成果。我们认为这包含四个核心要素：
第一个要素是**对意图有清晰明确的界定**。如果你不知道自己想构建什么，就无法告知智能体去构建什么，自然也无法得到预期的结果。
第二个要素是**导轨（guide rails）**。我们非常明确地称之为导轨，而不是防护栏（guard rails）。防护栏的作用是防止车辆冲出道路，而导轨的作用是帮助你保持在路线上。我认为智能体需要的是持续细微的轻推，以此来引导和规范这些智能体的行为。
第三部分是**验证**。这种验证必须是独立的、全面的，并且要做到问题就地修复，而不是一味地往后拖延。
最后是**证据**。做到“信任但需验证”，并明确这一过程有凭有据，且具备一致性、可审计性与可重复性。我们将这些要素相乘，是因为我们见过很多缺失其中某一环的情况；而一旦有一项为零，整体的信心就会归零。如果你做到了前面所有事情但唯独缺乏证据，信心值就会归零，你对产出结果便无法建立起信心。

<details>
<summary>Original English</summary>
So, as we've thought through this, we have um written down what we call the code confidence formula, which is basically how do you build How do you think about a software factory that delivers what we all want, which is outcomes that we can feel confident in, right? Not outcomes we can trust, not blind trust or anything like that, but outcomes that we can feel comfortable with or we can sit and tell our executives, our customers, our shareholders, our CEOs, our boards that yes, I believe this factory is working well. And we think there's four components to this. The first is being crystal clear about the intent. If you don't know what you're trying to build, you can't tell the agent what to build, and you will not get the outcome you want. The second is guide rails. And we very specifically talk about guide rails, not guard rails. Guard rails prevent something from going off the road. Guide rails help keep you on it. And I think what agents need are the small nudges to guide and govern those agents. The third part is verification that needs to be independent, thorough, and issues fixed as opposed to just cans kicked down the road. And then lastly, evidence. Trust, but verify. Trust, but understand that it was done with proof. Uh that is consistent, audible, and repeatable. And we multiply these together because we've seen a number of situations where one of these elements is missing. And if it's zero, the confidence goes to zero. If you do all of this, but don't have evidence, you go to zero. You don't have confidence in the outcome.
</details>

因此，我们坚信工厂设计必须具备这四项要素。在我们帮助客户与合作伙伴搭建这些软件工厂的过程中——我不打算逐一过遍这张页面上的每个方框——我们非常注重如何在左下角紫色区域明确捕获意图、如何设置防护导轨、如何以全面且独立的方式执行验证，以及如何生成审计证据。通过这种方式，我们看到了显著的成效。这些是我们客户的真实业务反馈：
首先关注意图与导轨层面。针对意图和导轨，我们推出了一款名为 Sonar Vortex 的产品，它提供意图设定与导轨约束，并在智能体闭环内部开展即时验证，再次对智能体进行实时校准纠偏。当我们在大型复杂代码库中为执行长期任务的智能体提供这种上下文信息时：

>> [snorts]

>> 我们看到 **Token 成本降低了 36%**。因为这就相当于把它的起点直接放在了怀特普莱恩斯，让它从一开始就极为接近正确答案，并辅助它理解整体架构脉络，无需在已知事实上白白消耗 Token。同时，**提交中的问题减少了 92%**。对吧？所以成本不仅更加低廉，而且能够以更好的产出进入后续的验证阶段。这完全归功于我们在过程中不断对智能体进行轻推引导，使其始终保持在正轨上。

<details>
<summary>Original English</summary>
So, we really think about factory design is requiring these four elements. And I'm going to And as we put together factors, as we help customers, I'm not going to walk through every box on this page, but as we help our customers and partners build these software factories, we're very deliberate about how do you get the intent, bottom left-hand side in purple. How do you put the guardrails in place? How do you do verification in a way that's thorough and independent? And how do you produce the evidence? And by doing this, we see amazing results. So, these are real results now from our from [snorts] our customers. The first one is focusing on intent and guardrails. And intent and guardrails, we have a product called Sonar Vortex, which gives intent guardrails and in the agentic loop starts to do verifications, again nudging the agents. And what we see when we provide agents in long-running and large complex code bases with long-running tasks uh with >> [snorts] >> this information is a 36% reduction in token cost because you're putting it in White Plains, you're actually you're putting it close to the answer, you're helping it understand the map. You don't have to burn tokens on things we already know. And 92% reduction in issues in the commit. Right? So, it's cheaper and we can get a better outcome to go into that verification stage. This is again all because we're nudging the agent to keep on track.
</details>

接下来进入验证阶段，我们起步就是一家专注验证的公司，这也是我们审视世界的视角。我们持有非常明确的观点：独立的验证必须覆盖全部问题类型，同时兼具精确性与成本效益。能够在 CPU 上跑的就利用 CPU，需要 GPU 算力的场景再动用 GPU。因此我们采用确定性混合方法，在此基础上融入智能体混合方法，由此构筑起我们所认为的验证黄金标准。当我们落地这一体系时——我们的产品名为 SonarQube——我们近期调研了 1000 多家客户并询问：“在智能体编码过程中，你们多久会遇到这类问题？”这里的统计结果表明，SonarQube 用户比非用户更有可能看到非常积极的成效：如果在全流程中部署了这种黄金标准验证，**认为 AI 编程对代码安全性产生高度积极影响的概率高出 81%**，对产品上市时间产生积极影响的概率高出 34%，在减少服务宕机频率方面的认可度高出 76%。

<details>
<summary>Original English</summary>
Then you get to verification, and we started life as a verification company. This is how we see the world as through a verification lens, and we have a very strong point of view that independent verification has to cover the full range of issues that is both precise and cost-effective. Right? Use CPUs when you can use CPUs, need GPUs GPUs when you need GPUs. So, we look at deterministic mixture methods, and then you add in agentic mixture methods, and it comes up with what we think is the a gold standard of verification. And what we see is when you apply this, our product is called SonarQube. So, we talked to our customers, over 1,000 customers recently, and we said, "Are you How likely are you or how often have you seen these issues from a gentle coding?" And the the statement to read here is SonarCube users are X% more likely than non-users to have seen a very positive impact. So, 81% more likely to have seen to believe that AI coding has had a very positive impact on code security if you have that gold standard ver- verification. 34% more likely to have seen an impact on time to market, 76% on outage frequency.
</details>

因此，回到“我们如何建立交付信心”这一命题：我们所见证的是，如果将这些模块整合在一起，并将高标准的验证作为工厂的一等公民进行构建，你实际上就是在建立信心，并能切实看到成效——更强的安全性、更有把握的上市周期，以及停机故障的减少和系统可靠性的提升。当然，正如我前面强调的，这一切必须以证据为支撑。确保项目能够通过质量门禁；确保符合屏幕上列出的诸多标准与缩写规范——无论是内部运营管控中的 IT 全般控制，还是汽车软件领域的 MISRA 标准，亦或是这里列出的其它规范。拿出扎实的证据，才能让你高枕无忧，才能赋予你大步向前推进的底气。归根结底，这就是我们对未来挑战的思考：**代码将变得极度充沛，而信心依然极其匮乏**。当我们展望软件开发的未来时，我们自身的目标、以及我们认为每个人都应确立的目标，就是如何交付信心。未来的工厂必须具备交付信心的能力。非常感谢大家！我们在会场展区那边设有一个醒目的大型红色展位，非常期待能与大家就这些话题展开更多交流。非常感谢，祝大家上午愉快！

>> [applause]

<details>
<summary>Original English</summary>
So, again, as I come back to how do we have confidence to ship, what we're seeing is that if you put these pieces together and you build verification incredibly strongly as a first-class citizen in the factory, you are actually building confidence and you're seeing results, better security, more confident in time to market, improved or reduction in number of outages, improved reliability. And, of course, as I mentioned, you have to do this with evidence. Make sure you pass the quality gate. Make sure whatever There's lots of acronyms up here, whichever ones you need to pass, whether that is your IT general controls inside of your internal controls and operations, whether that's MISRA if you're building cars, or any of the other ones that are on here, producing the evidence is what lets you sleep at night. It's what gives you confidence that you can move forward. So, that, in essence, is how we think about the challenge of the future, that code is abundant, that confidence is scarce, and really the goal that we have and that we think that everyone should have as we think about the future of software development is how do we deliver confidence. And the factories of the future need to be able to deliver confidence. So, with that, I want to say thank you to everybody. We have a big booth, it's a big red booth on the floor right over that way and would love to talk to you more about all of this. Thank you very much, have a great morning. >> [applause]
</details>