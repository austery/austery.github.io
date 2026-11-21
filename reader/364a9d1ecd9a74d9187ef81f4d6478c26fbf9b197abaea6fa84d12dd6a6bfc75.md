---
author: AI Engineer
date: '2026-11-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=geMAe-PLJF4
speaker: AI Engineer
tags:
  - code-review
  - connectome
  - pull-request
  - developer-experience
title: 用果蝇大脑神经网络做代码审查：突破软件工程的代码审查瓶颈
summary: WorkOS 的 Nick Nisi 分享了将雄性果蝇全脑连接体模拟用于 JavaScript 代码审查的实验项目。他探讨了随着 AI 编程加速，人类审查成为瓶颈的现状，并提出了结合团队审查技能、分类模型与自动化工具的多层分流审查架构。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Nick Nisi
companies_orgs:
  - WorkOS
products_models: []
media_books: []
status: evergreen
---
### 代码编写变快后的新瓶颈：人类审查

[音乐]

>> 欢迎大家。感谢各位来听我的演讲。我叫 Nick Nisi，是 WorkOS 的软件工程师兼工程经理，负责带领开发者与智能体体验团队。这项工作非常有趣，我在那里做了很多好玩的事情。我们在现场设有展位，如果大家想跟我聊聊这次演讲或 WorkOS 本身，欢迎到楼下展位找我们。

但我今天想和大家聊聊我认为目前软件开发中面临的最大瓶颈。现在的代码编写速度比以往任何时候都要快，我们提交的 Pull Request（PR）也比以往任何时候都要多。但瓶颈随之出现。我们有健全的持续集成（CI），有代码检查（linting），还有智能体在上面运行并排查问题。但代码最终还是卡在那里等着我审查。于是，我变成了那个瓶颈。

<details>
<summary>Original English</summary>
[music]

>> Welcome. Thank you for coming to my talk. My name is Nick Nisi and I am a software engineer and engineering manager at WorkOS where I lead the developer and agent experiences team. Uh and it's a lot of fun and I do lots of really fun stuff there. Uh and at WorkOS we do have a booth here. So if you want to chat with me about this talk or about uh WorkOS itself, come down and see us uh downstairs. Uh but I want to talk to you about what I see as the big bottleneck in software development right now. Uh code is being written faster than ever. Uh and we are putting up more PRs than ever before. But there's a bottleneck there. We've got good CI, we've got linting, we've got agents running our [snorts] running like finding things on there. But it's just stuck waiting for me. So I I've become the the uh I've become the bottleneck.
</details>

希望这是一个我们能够解决的问题，而且我认为我们确实可以解决。这正是最核心的部分：如果我们已经不再亲手写代码了，为什么还需要人类来审查代码呢？当真正重要的是功能本身时，这种做法其实有点说不通。所以让我们稍微深入探讨一下。

正如我所说，我认为这个瓶颈是会被解决的。Claude、Codex 等工具已经解决了编写代码的问题。虽然我们依然参与其中，但我们扮演的角色变成了管理者、项目经理。我们拥有智能体，拥有 CI。过去我们一直用 CI 对 PR 执行常规检查；而现在，我们还有智能体在上面运行，比如 Graphite、Code Rabbit 等。如果 Graphite 给我的 PR 打了五分满分，我会很兴奋，而且相当确信它不会搞垮生产环境。

因此，看代码本身已经没那么重要了。我真正想知道的是：它到底有没有实现我预期的功能？

<details>
<summary>Original English</summary>
Uh and that is uh something that hopefully we can solve and I think that we really can. Um that's just the biggest piece of it. If we're not writing the code anymore, why do we need a human to review the code? Uh it doesn't quite make sense when the functionality is what matters. So let's uh dive into that a little bit. Um [snorts] like I said, I do think that this is a bottleneck that's going to be solved. Uh code Claude co- Claude Codex um etc. has solved the coding problem. Uh and we're still there, but we're managing it. We've become managers, project managers. Uh we've got agents and we've got CI. We've always had CI kind of doing checks on our pull requests. Uh and now we've got agents running on them as well. Graphite and Code Rabbit and other ones. If Graphite gives me a five out of five, I am excited and uh I'm pretty confident that I'm not going to break production. So um it doesn't matter as much to look at the code. What I really want to know is does it actually do what I expect it to do?
</details>

如果代码审查依然存在，我认为它存在的理由也将会发生改变。我不认为它存在的目的还是为了让我点个赞表示“好的，我批准这篇 PR”，尽管这仍是其中的一部分。它更重要的意义在于把上下文重新带回给人类，告诉人类：这里提交了什么改动，以及这项改动为什么与你息息相关。那将是最关键的部分。但它不再是让人去反复确认 Reptile 有没有遗漏什么只有人类才能发现的东西，因为我不再相信还存在“只有人类才能发现”这种情况了。

但在我们进一步探讨之前，先退一步，来聊聊“Bug”。

软件中的“Bug”这个词，源于 1947 年我生日那天（尽管头发有点花白，但我当时可没出生）在一台继电器里发现的一只真正的蛾子，它当时干扰了正在运行的程序。这就是该词的由来。现在快进到 2026 年，我打算用一只“Bug”（虫子）来找出我软件里的 Bug。

那么，让我们唤醒这只果蝇，把它接入“黑客帝国”（矩阵），让它运转起来。

<details>
<summary>Original English</summary>
Uh and if code review does stick around, I think that it's just going to change like the reasoning why it's sticking around. I don't think that it's going to be for me to give a thumbs up, yes I approve this even though that is a part of it. It's more going to be to bring the context back to the human to say here's the change that is being proposed and why it matters to you and that's going to be the most important piece of it, but it's not going to be please go make sure that Reptile didn't find uh didn't miss something that a human could find cuz only a human could find it cuz I don't believe that that's the case anymore. Uh but before we dive into that more, let's take a step back and uh talk about bugs. Uh so the term bug in software came from a literal moth that was found in a relay uh that was disrupting a program that was running uh way back in on my birthday in uh 1947 although despite the greys I wasn't around then. Um and that's where the term came from. Now skip ahead to 2026 and I'm going to use a bug to find bugs in my software. So let's wake up our fly. Let's bring him into the matrix and let's get him going.
</details>

### 用果蝇连接体审查 JavaScript

为了做到这一点，我们把它连接进来。我们会看到它的连接体（connectome）以及神经元的放电。我并不是第一个这么做的人，实际上之前已经有人做过好几次了。如果你经常上网，会发现很多人都在“折磨”这只可怜的果蝇：他们让它去玩《毁灭战士》（Doom），这挺有趣的，也很酷；他们还让它玩《节奏光剑》（Beat Saber）之类的游戏。

如果你觉得让这只可怜的果蝇心智活在矩阵里已经算是一种折磨，那你肯定会更反感我对它做的事情：我让它审查 JavaScript 代码。审遍 JavaScript 所有的代码以及它那些“美妙”的惯用法。

>> [叹气]

>> 呃。我还记得以前自己看这些代码时的样子。

那么，让我们重新把它插上电，教它学习如何做代码审查。

<details>
<summary>Original English</summary>
Now to do that we'll connect him in. We'll see his uh connectome and his neurons firing. Now I'm not the first one to do this. The this is actually been done several times before. Uh if you've been on the internet, lots of people are torturing this poor fly. They're making it play Doom uh which is a lot of fun, pretty cool. Uh they're also doing things like making it play Beat Saber or do things like that. Uh now if you think that this is torture to this poor fly's mind in the matrix, uh then you're really going to dislike what I did to it. I made it review JavaScript. All of JavaScript and its lovely lovely idioms.

>> [sighs]

>> Ugh. I remember when I used to look at this code. Uh so let's plug it back in and let's make it learn some code review.
</details>

我们来谈谈这张图表究竟是什么。这被称为**连接体**（connectome），它是雄性果蝇大脑的真实神经元网络。研究人员在电子显微镜下，通过将这个大脑切片数千次并拍照，极其精细地对神经元进行逐一扫描，然后将这 176,000 个神经元之间的所有连接全部连通，构建出了 630 万个连接和超过 1.25 亿个突触。

在这次演示中，我们就是把代码审查交给了它，而它就是未来取代我们代码审查员工作的对象。我并没有对它做太多其他改动。我教它运行起来，让它跑通并试玩了一阵，然后就没再碰它。除了用于保留记忆的一小部分神经元之外，我没有修改任何其他神经元。我稍后会详细解释我都做了什么，但基本上，我已经让它能够记住什么是好代码、什么是坏代码。

<details>
<summary>Original English</summary>
So this diagram itself, let's talk about what it actually is. This is called a connectome and it's the actual neurons of a male fruit fly brain that they meticulously scanned one by one under an electron microscope by slicing this brain thousands of times and taking photographs of it and then wiring up all of the connections between those 176,000 neurons to create 6.3 million connections and over 125 million synapses. That's what we're passing our code reviews to in this demo and that's what's going to be taking our jobs as code reviewers. I didn't really change anything else about it. I taught it to run, got it working, played around with it. And then I didn't touch it. I didn't change any of the neurons except for a small subset of them that I'm using to retain memories. And I'll dig into what I did, but I basically have it remembering what's good and what's bad code.
</details>

你可能会好奇，它一只果蝇怎么能看得懂什么是代码？其实它不懂。但它有**感器**（sensilla），也就是它身上类似微小毛发的结构，充当它的嗅觉器官。我利用 AI——具体来说是用了一个名为 Jev 的系统一模型来充当它的鼻子，针对正在审查的代码提出 30 个客观公正的问题。随后，它将这些信息作为一种“气味”输入给大脑。我们实际上是把代码变成了字面意义上的“代码坏味道”（code smells）。

然后，这种输入会去比对果蝇关于好代码与坏代码的记忆。在进入待审的 PR 之前，它已经在代码库的代码上接受过训练，知道这是好代码还是坏代码。我稍后会解释具体运作机制。

在训练中，如果被判定为好代码，它就会闻到类似糖水的气味；如果是坏代码，它就会闻到非常苦的味道，因而感到害怕并不想靠近。接着，指导程序会在其上进行强化，赋予它这种“味觉”。因此，这只虫子实质上具备了判断代码好坏的品味，并以此为依据展开行动。

<details>
<summary>Original English</summary>
So, you might be wondering how does it know what code is? It's a fly. Well, it doesn't. It has sensilla which is like little hairs on it that act as its nose. And I use AI, specifically I use Jev, a system one model, to act as its nose and ask 30 questions that are non-biased about the code that it's reviewing. And then it passes that to the brain as a smell. So, we're taking our code and turning it into literal code smells. Then that goes against the memory that the fly has about what's good and what's bad code. Before it gets to a pull request that it's reviewing, it's been trained on the code in the pull request and it know or sorry, in the code base and it knows is this good code? Is this bad code? And I'll explain how that works. And then if it's if it was trained as good code, it got like a sense of smelling sugar water and if it's bad code, it got a very bitter smell and so it's afraid of that and doesn't want to go near it. And then a teacher reinforces that over it to give it this taste. So, effectively the bug has a taste of is this good or bad code and goes from there.
</details>

随着各种浓度的气味进入——毕竟每个代码差异（diff）都不一样——它体内会分泌出不同的激素，好的激素或坏的激素，比如多巴胺，用来重新连接神经元之间的通路，进而决定它要表现出怎样的行为。

随后它会进行投票表决：要么给出反馈说，仅凭这种气味就让我觉得这是一个好的 PR；要么给出相反结论，认为应该提出修改意见，因为代码把它吓坏了。它经常被吓坏。

所有这一切最终就类似一个故意设计了键冲突的哈希表，我们通过测试把这些值写入进去。

>> [喷笑]

它从训练中获得的每一个结果都是一种味觉反馈。这些记忆赋予了它辨别代码好坏的品味。如果测试产生了一个 Bug，它就会收到痛苦的苦味多巴胺惩罚，从而削弱促使它靠近的连接通路；如果是一件好事，它就会得到糖水，激发奖励性多巴胺，进而削弱促使其回避的通路，随后它会吐出舌头（口器），做出想要大快朵颐的样子。

如果它伸出舌头，就意味着“闻起来不错”，这就是果蝇给我们传达的通过信号；反之，如果没有伸出舌头甚至缩了回去，那就说明那是我们应该避免的代码。

<details>
<summary>Original English</summary>
And then it just like as the smells come in in different levels because, you know, every coder diff is different, it's going to get different hormones sent to it, either good hormones or bad hormones that, um, uh, like dopamine that, uh, wires like how the neurons are going to connect with each other and then what behavior it's going to display. And then it'll vote and it'll say, yes, the smell alone makes me think that this is, uh, a good, uh, PR. Otherwise, no, I think that changes should be made because I'm terrified of this code. It's terrified a lot. And all of that just like ends up being like a hash table, uh, where the keys collide on purpose, uh, and we use testing to, um, to write those values.

>> [snorts]

>> So, every result that it gets from that training is a taste. And so, the memories give it a taste of what's good and what's bad code. Uh, if the test produces a bug, it gets a bitter punishment dopamine, uh, and that weakens the lit cell wires between the approach. And if it's a good thing, it gets sugar, which, uh, fires reward dopamine, uh, and that weakens the wires to avoid, and then the tongue will come out as if it wants to slurp that up. Uh, if the tongue comes out, smells good to me. That's, uh, that's the indicator that we get from the fly. And otherwise, if, uh, it doesn't come out and it retracts, uh, then that is something that we should avoid.
</details>

我对此做了测试。当时我真正担心的一点是：果蝇大脑在这个过程中会不会变得多余？我不希望变成全由 Jev 在判断好坏，而果蝇只是充当一个解释含义的道具。但实际情况并非如此。如果我移除那些记忆神经元，它就会彻底失控，无法做出正确反应。因为它对什么是好代码、什么是坏代码，以及是什么导致了苦味或甜味没有任何记忆，所以它无法表现得体。它的行为会完全错乱，在不该伸出舌头时伸出来，整体上根本无法工作。因此，果蝇的大脑确实在承担处理计算，并在思考代码的好与坏。

<details>
<summary>Original English</summary>
So, uh, I tested this and like the thing that I was really worried about was making the fly brain kind of redundant in this, right? I don't want it to just be like it's Jev that's saying it's good or bad and then the fly is just there to interpret what that means. That's not what's actually happening. If I remove those memories, then it totally freaks out and doesn't do the right thing because it has no recollection of like what's good and what's bad code and what caused a bitter, uh, bitter taste uh, versus a sweet taste, and so it won't behave correctly. It'll scramble everything. The tongue will come out when it shouldn't, uh, and it overall just doesn't work. So, the, um, the fly brain is actually doing the processing on this and it's thinking about what's good and what's bad code.
</details>

### 现场互动：你比果蝇更聪明吗？

>> [喷笑]

这次演讲的题目叫“你比果蝇更聪明吗？”，所以我们现场观众一起来玩个游戏。请大家准备好，我们点击这个按钮来进行抽取。我们从果蝇的真实代码库中随机挑选三个文件。

请大家举手表决：你会批准代码中的这个修改吗？如果你会批准这项修改，请举手。

现场没有人举手。要么是大家没参与，要么是大家都不想批准。那我就记录为我们要对它要求修改（Request Changes）。

我们来看看果蝇的反应：在果蝇闻起来，这味道不错。那么我们来看看真实情况是什么：这是一个 Bug。果蝇判断错了。目前看来开局不太妙。

<details>
<summary>Original English</summary>
>> [snorts]

>> So, the name of this talk was are you smarter than a fruit fly? So, we're going to play a game as an audience. Uh step right up. Let's go ahead and uh hit this button and draw. We're just going to pick three random files from the actual code base uh for this fruit fly. And show of hands, would you approve this change in the code? Raise your hand if you would approve of this change. No hands raised. That's either no participation or we're not going to. So, I'll say that we are uh going to request changes in this. Let's see what the fruit fly did. It smells good to the fruit fly. So, let's see what the actual response was. It's a bug. The fruit fly was wrong. Not looking good so far.
</details>

好，来看下一个。在这段 PKCE 代码中，如果你会批准这项改动，或者会拒绝这项改动……抱歉，如果你会批准这项改动，请举手。

好的，看到有人举手了。那我就选批准。果蝇也选择了批准。太棒了，这确实是一次无害的代码改动，完全没问题。

最后一个。针对这次改动，如果你会批准，请举手。

有一票。

>> [笑声]

好吧，我认为我们大概率会拒绝这项改动。果蝇会拒绝它吗？

哦，是的，果蝇觉得有异味。果然是个 Bug！

全场观众三发全中，果蝇三发两中。表现相当不错。显然，大家确实比果蝇更聪明，恭喜各位！

<details>
<summary>Original English</summary>
All right, next one. Uh in this PKCE code, would you raise your hand if you would approve this change or if you would reject this change? Oh, sorry. If you would approve this change, raise your hand. Okay? See some hands. I'll go with approve. The fly will also approve. Cool. It was a harmless change. All good. Last one. Uh on this change, raise your hand if you would approve this change. One.

>> [laughter]

>> All right. Yeah, I think this is probably we're going to reject this change. Does the fly reject it? Ooh, yeah. Something stinks. Bug. All right. So, the room went three for three. The fly went two for three. That's pretty good. Uh obviously, you'll you all are smarter than a fruit fly. Congratulations.
</details>

但果蝇的表现其实已经相当好了。在我测试它的时候，它的准确率大概能达到 88%。所以综合来看，当一只果蝇有 80% 的概率能做对时，这还值得耗费你的时间吗？或者说，80% 的时候它总是正确的。这是个好问题。

那我们来用真实代码试一下。我在这里粘贴一个 PR，这是提给我自己的一个扩展插件的。

这是我自己批准了的改动，但我们来看看果蝇是否也认同。我现在把它发送给 Jeff。它正在运行测试，读取并抓取数据，希望在现场演示中系统能配合我。如果不配合也没关系，我有备用方案。

我们切换到备用方案。备用系统显示无法判断，在这个改动上也没能做出区分。没关系。

大家可以在线访问 fruitfly.review 亲自运行并试玩。不过，你大概率不会真想用一只果蝇来测试自己的代码。

<details>
<summary>Original English</summary>
Uh but the fruit fly was pretty good. It got uh it got it right about 88% of the time when I was testing it. So, um overall, is it worth your time when a fruit fly can do it 80% of the time? 80% of the time it's correct all the time. Um that's that's a good question. So, let's try it on a on something real. Let me paste in a uh a pull request here. Uh and this one is just to one of my pie extensions. Um and it's something that I approved, but let's see if the fruit fly agrees with that as well. So, I'm sending it to Jeff. And it's going to do a test. Um read that and fetch it and hopefully things cooperate with me in a live demo. But, if they don't, that's okay. I have a backup. We'll go with the backup. And it can't tell. So, the backup didn't uh didn't make a distinction either on this change. Um that's okay. Uh you can run this yourself at fruitfly.review uh online and play with it. But, you probably don't want to actually use a fruit fly to test your code.
</details>

在这段代码测试中，我给它安排了比刚才演示中难度大得多的测试。

>> [喷笑]

有 96% 的概率，它能正确捕获第一个例子并提出修改意见；面对一个极具迷惑性的错误时，它也有 98% 的概率提出修改。所以大多数时候它确实有效，能够找出问题。当然，它毕竟只是一只果蝇，无法进行交流，也根本不知道 JavaScript 到底是什么，所以它不会告诉你应该怎么去改，它只会说：“我觉得这味道怪怪的，换作我可不会通过。”

那么，如果连果蝇都能把代码审查做得马马虎虎过得去，为什么还要人类来做呢？这就是问题所在。

<details>
<summary>Original English</summary>
Um now in this code, um I did give it a lot of hard a lot harder of tests than uh what I showed here.

>> [snorts]

>> Uh 96% of the time it would correct correctly uh catch the first example here uh where it would request changes. At 98% of the time uh a very plausible mistake, it would uh also request changes on that. So, it is working most of the time where it can find issues. Of course, it's a fruit fly, it can't communicate and it doesn't know what JavaScript actually is, so it's not going to tell you how to change it. It's just going to say, "This smells funny to me. I don't think I would accept that." So, if the fruit fly can do the code review moderately well, then why are humans still doing it? That's the question.
</details>

### 构建无人介入的自动化分流审查架构

从这次实验中我们了解到：它基本上能够识别出改动了什么、理清条件判断、发现被删除的逻辑等诸如此类的简单问题，引导你避开这些坑，帮我们把好方向。当然，Reptile、Code Rabbit 以及所有这些工具都能做得比它好得多。但是，没有任何工具知道背后的“原因”。而我认为这正是人类将永远掌握主导权的关键所在：我们需要理解为什么代码会被改动，或者更具体地说，为什么功能会发生变化。

那么我们该怎么做？如果我们打算把人类从审查流程中解放出来，首先可以只将那些确实需要人工介入的 PR 上报给人类，而让其余所有 PR 直接通过。关于具体怎么做，我有一些想法。

首先是**团队审查技能**（team review skill）。我在 WorkOS 带领开发者体验（DX）团队，如果某个代码审查被标记分配给了我们（比如我们在 GitHub 上使用 code owners 功能），那么就应该有一个由我们团队共同维护的审查脚本或技能，它基本上涵盖了 WorkOS 开发者体验工程师审查代码时所需满足的最低要求。这是我们需要严谨维护、追踪并确保正常运行的东西。

<details>
<summary>Original English</summary>
Um what we've learned from this uh is basically it can figure out what's changed, uh figure out conditionals, removed logic, um Um, you know, simple issues like that and it can steer you away from that and it can kind of keep us on track. Of course, Reptile, Code Rabbit, all of those can do it much better. Um, but nothing knows why. And I think that that's the important thing that humans will always have a uh hand on because we need to understand why code is actually being changed or why functionality is changing more specifically. So, how do we do that? If we were to take humans out of the review process, um, we can start by just escalating to the ones uh escalating the ones that need our reviews and letting everything else pass. And I've got some ideas about how we might do that. Uh, the first one is a team review skill. So, uh I lead the DX team at WorkOS and if a code review is tagged with us, like we use code owners on GitHub, uh if it's tagged with us, there should be a reviewer script or skill that we maintain as a team that is basically like the bare minimum of what a DX engineer at WorkOS would be reviewing for. And it's something that we meticulously keep up uh and keep track of and make sure it's working correctly.
</details>

如果 PR 通过了这一步，就可以进入下一个环节：某种分类器模型。这可以是 Jev、Clef、其他工具，或者是某种轻量级模型，由它来执行检查：这项改动是否过于复杂？它是否真的实现了它声称要实现的功能？这会不会带来重大风险？它可以对此赋予不同的权重。

在假定它通过了所有这些检查之后，就可以把它交给自动化审查工具，比如 Reptile、Code Rabbit、Codo 等今天在场的所有优秀公司产品。

到这一步，系统会做出决策：如果上述任何一个环节失败，就将其上报给人类；如果一个都没失败，那它很可能是一个可以安全自动合并的 PR，我们就不需要再去打扰其他人类同事，从而能够更快地发布软件。

如果真的出了问题，我们可以回顾整个经过，对整个流程进行审计，看看是不是可以改进团队审查技能以便下次捕获，或者修正某个自动化代码审查工具；但更重要的是，我们可以利用 AI 来修复代码并继续前进。

<details>
<summary>Original English</summary>
Um, if it passes that, then it can move on to the next thing. Some kind of classifier. This could be Jev or Clef or something else or some lightweight model, excuse me, that is doing uh a check to see, you know, is this too complex? Is it actually doing what it says it's going to do? Will this cause significant risk? It can do like different uh weights on that. But assuming it passes all of that, then it can give it to an automated reviewer like Reptile, Code Rabbit, uh Codo, all of the the fantastic companies that are here today. And then, from there, it decides. If any of those failed, escalate that to a human. If none of those failed, it's probably a safe PR to merge on its own and we don't have to bother another human. We can get software shipped in faster. If something does break, we can review what happened, uh audit the this whole thing, see if maybe we can fix the team review skill to catch it or fix one of the automated code reviewers to catch it uh the next time. But more importantly, we can use AI to fix the code uh the uh and go forward from there.
</details>

然后，系统会向人类提供一份总结性答复，说明这项改动为何发生、具体改动了什么。究竟是业务逻辑发生了变化？还是尝试过其他备选方案后将其放弃了？等等。

但我认为接下来的核心步骤在于各团队去管理这项技能：在其中记录发生了哪些变更、作为一个团队应当如何去审查代码，并以此来判定某些内容是否需要升级上报给团队成员进行检查。

最后一点，在生成总结时，如果我们不再那么关心代码本身，而只关心它是否确实达到了我们的预期，我们就会需要某种证明或验证手段。为了证明智能体确实完成了验证工作，你可以让它生成截图、录屏，附上测试结果或命令输出；编写并提供冒烟测试供我运行并查看输出结果；或者直接为我提供易于复现的途径，以便在需要时进行人工测试。随着我对其他验证方式愈发信任，人工测试的需求也会逐渐减少。

<details>
<summary>Original English</summary>
And then, deliver back a summarized response to the human as to why this change happened uh and you know, what it was. Is it business logic that's changing? Uh were there all alternatives that were tested and discarded? Uh etc. But, the main thing is I think uh as a next step is teams managing that skill where they can keep track of what's changed, uh how they would review these skill or review code as a as a team, and then use that to decide if something should be escalated to someone on that team to check. And then, of course, on the last thing when it's summarizing, uh if we don't care about the code so much anymore and we only care about does this actually do what we uh expect it to do, we're going to want some kind of proof of that or some kind of verification. And so, you can prove that the agents actually like did the work to verify this by having it create screenshots, videos, uh put test results or command outputs on there. Write and provide smoke tests that I can run and it and see the outputs of that as well. Or just give me easy ways to replicate this so that I can do some manual testing if I need to, uh and that will slowly diminish as I trust these other methods to go.
</details>

这种审查大概会长成这个样子。对于 DX 团队来说，它可能会注明：“这是人类会关注的范畴；而这些是会让人们停下来并要求修改的情况。”

系统就可以据此进行审查。这很大程度上取决于你团队的预期、关注点以及涵盖的职责范围。DX 团队显然与平台团队不同；比如我对动物相关的配置文件一无所知。因此，不同团队会有各自不同的关注重点。针对所修改的内容，不同团队可以各自管理相应的维度，最终就是否需要上报给人工介入做出结论。

说到这里，我诚挚邀请大家亲自尝试一下。你可以访问 fruitfly.review 在线运行你自己的 PR，也可以在那里查看演示幻灯片和相关参考资料。欢迎大家前去体验，也欢迎到 WorkOS 的展位来找我交流。

<details>
<summary>Original English</summary>
So, that review might look something like this. For the DX team, uh it might say like, "This is anything that a human uh would look at, and these are things that would a human would stop and say, 'No, we need to request changes on from there.'" And so, it can just kind of do that review based on that. This would be very uh dependent on what your team expects, what your team's looking for, what your team covers. You know, a DX team is going to be different from a platform team. Um I'm not going to know any what to do with the animal files, for example. Uh and so, we're going to have different different things that we're going to look at and focus on. And depending on what we're changing, uh those teams can manage different aspects of it and come to a conclusion as to whether we actually need to escalate this to a human in the loop. And with that, uh I invite you to try this out. You can go run your own pull request there at fruitfly.review. You can also see the slides there and uh any uh references. So, check it out and uh come see me at the Work OS booth.
</details>