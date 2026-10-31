---
author: Latent Space
date: '2026-06-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DcvgPEApHT8
speaker: Latent Space
tags:
  - continual-learning
  - reinforcement-learning
  - distributed-training
  - ai-agent
title: Trajectory 创始人 Ronuk 访谈：持续学习（Continual Learning）将如何重塑 AI 智能体
summary: 本文是 Trajectory 创始人 Ronuk 的深度访谈录。Ronuk 回顾了他在 Windsurf 及 Google DeepMind 的经历，分享了 Windsurf 被谷歌收购的幕后故事，并深入探讨了 Trajectory 的核心愿景：通过自主研发的 SDPO 算法以及开源的分布式 LoRA 训练框架，将“持续学习”这一关键能力带到法律、金融等非代码领域，构建能够动态进化的下一代 AI 智能体。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Trajectory
  - Google DeepMind
  - OpenAI
  - Harvey
  - Nvidia
products_models:
  - Windsurf
  - Nemotron 3 Super
  - Gemini
  - sui 1
media_books: []
status: evergreen
---
### 引入与 Windsurf 早期回忆

**Len**: 好的。我们现在在远程录音室里，和来自 **Trajectory** 的 **Ronuk** 进行交流。祝贺你们的产品发布，并欢迎来到 **Len Space**。

<details>
<summary>Original English</summary>

**Len**: Okay. Uh we are in the remote studio with Ronuk from Trajectory. Congrats on your launch and welcome to Len Space.

</details>

**Ronuk**: 非常感谢。是的，很高兴能与你交流。谢谢你邀请我来。

<details>
<summary>Original English</summary>

**Ronuk**: Thanks so much. Yeah, great to be chatting with you. Thanks for having me on.

</details>

**Len**: 是的。嗯，我想我们在你还在 **Windsurf** 的时候应该没有太多交集，但显然我和 Windsurf 团队的 **Varun** 以及其他成员关系很近。看到你经历了 **Google DeepMind** 的那段旅程，并带着对下一步发展以及**持续学习（continual learning）**的如此强烈的信念走出来，真的很令人惊讶。

<details>
<summary>Original English</summary>

**Len**: Yeah. Um I don't think I I like we like quite over overlapped when when you were at Windsurf but obviously I was close to the windsurf uh team Verun and the other guys and it's really surprising to see that uh you know you have sort of gone through that journey at deep mind and come out uh with such a strong thesis on what's next and continue learning.

</details>

**Ronuk**: 是的。不，坦白说，在 Windsurf 的那段时光非常棒。回想起来真疯狂，甚至仅仅在两年前，世界看起来还是如此不同。我依然记得我们第一次发布 Windsurf 的时候，那时 **Sonnet 3.5** 刚刚推出，我们正在尝试它的各种能力和功能。我清晰地记得有一次，我们启动了 IDE，构建好了智能体（agent），然后大家开始围在 Varun 身边。他让智能体去制作一个 **2048** 游戏，那只是个无聊的小游戏。我们看着那个智能体，它居然一次性就成功把游戏写出来了。那真是一次令人震撼的体验。当然，现在每个人都体验过这种神奇了，但当时能够在那个房间里，亲手构建第一批这样的系统并亲眼见证，感觉真的很奇妙。之后能够顺着那股浪潮进入 DeepMind 以及后面的经历，也超级酷。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. No, it's it was a great time honestly at at Windsurf and it's crazy to think that even two years ago the world just looks so different. I I still remember when we first launched Windsurf, it was like Sonnet 3.5 had just come out and we're playing around with the capabilities and everything. Um, and I distinctly remember there's one time where we had started the IDE, we had built the agent out and everything and then we all started like circling around Verun and he was like he told the agent to like make 2048 and it was just like silly game whatever. We like we saw the agent and it just like first shot made the game and that was like that mind-blowing experience. I mean obviously now everyone's experienced it but getting to to build the first systems like see that in the room it was just so magical at the time and then obviously getting to ride that wave to to now deep mine and everything it was super cool.

</details>

**Len**: 我认为 **Codeium** 还有后来的 Windsurf 在产品工程（product engineering）和模型训练（model training）方面都有一些交叉。你进入这个领域之前的背景是什么样的？

<details>
<summary>Original English</summary>

**Len**: I think Kodium and then Windsurf had a bit of a mix of like product engineering and model training. what was your background like coming into this?

</details>

### 个人背景与 sui 1 模型研发

**Ronuk**: 是的，我当时刚刚在**斯坦福大学（Stanford）**完成了我的硕士学位。在人工智能领域做研究已经有相当长的一段时间了。实际上，我也是在那里结识了我的联合创始人们。我们真的是在斯坦福大一入学的第一周认识的，这非常棒，我们稍后可以聊聊这个故事。毕业后，我加入了 Codeium。其实我当时也有机会去谷歌工作，参与 **Gemini** 的后训练（post-training），那是当时普遍的选择。但我见到了 Codeium 的团队，我意识到这一切都取决于团队，取决于快速行动的能力。在 Windsurf 亲眼见证这一切是令人难以置信的。所以我赌了一把，加入了这个团队，当时它还叫 Codeium。我当时有一个信念，那就是要么是数学，要么是代码——某种结构化的信息将带领我们实现 AI 的下一次飞跃。事实证明，代码在经济上也更具可行性。这就是我加入团队的基本经过。我最初是在那里负责研究工作。所以刚开始我们是在 Windsurf 训练自动补全模型，就像在 Codeium 插件里做的那样。后来我们开始意识到，我们不仅从用户的“接受/拒绝”或输入中获取了大量的用户信号，而且直接从智能体那里获得了更丰富的信号。比如，人们是如何构建整个网站、整个应用的？因此，我们致力于构建我们自己的基座模型（foundation model），以捕捉所有这些用户信号，并真正为 Windsurf 解锁飞轮效应。于是我开始开发这个名为 **sui 1** 的模型。你可能已经看到，现在有 Cognition 正在开发的后续迭代版本，比如 sui 1.5 和 sui 2。这也是公司的重大突破之一，因为我们拥有如此海量的数据。我们能够针对所有这些用户信号进行后训练，进而击败了前沿模型（frontier models）。这一切都发生得非常快，因为在这之后，谷歌和 Cognition 的收购就发生了，我记得大概是在那之后 35 天左右。所以这非常有趣。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah, so I had just finished up my masters at Stanford. Been doing research in in AI for for quite a bit of time. That's actually where my I met my co-founders as well. Uh we we met like literally first week of freshman year at Stanford, which is super awesome. We can get to that story after. So then I joined Kodium. I actually had the option to go to Google for to work on Gemini post training. That was kind of the status quo. But I met the team there and I was I I realized just it's it's all about the team. It's all about moving fast and getting to see that at Windsurf. It was incredible. So took the vet on that team, joined one back when it was called Kodium. And I had this thesis that it was either going to be math or coding, some sort of structured information that gets us to the next leap in AI. And it turns out that coding is a lot more economically viable as well. And so that's basically how I joined the team. I started on on the research side there. So initially we were training autocomplete models at windsurf like back in the kodium extension. Afterwards we started to realize okay we're getting so much user signal not just like accept reject or what people are typing in the code but actually from the agent right and like how are you building these entire websites entire apps and and so we sought out to build our own foundation model to capture all of that kind of user signal and and really get the flywheel unlock for windsurf. And so I started working on this model called sui 1. Uh you might have seen now there's like later iterations like sui 1.5 and 2 cognition is working on and this was the kind of major unlock for the company as well is we had all this massive data. Um we were able to post train on all of that user signal uh and now beat the frontier. Um so that all happened and it was it was super fast cuz then right after that all the Google and cognition acquisition happened I think like 35 days after or something. So that was that was super fun.

</details>

### 惊心动魄的谷歌收购幕后

**Len**: 是的，我们做过好几期围绕这个话题的节目，因为这纯粹是一个大家普遍感兴趣的话题。在那发生的那一天，你有什么样的感受和看法？

<details>
<summary>Original English</summary>

**Len**: Yeah, we've done episodes around that just because it's a matter of just general interest. Uh what what is your take on that day that it happens?

</details>

**Ronuk**: 是的，当时真的太疯狂了。我实际上不知道有没有人讲过这个故事，但请听我道来。我当时是在研究侧，如果你还记得那个时候，大家都以为 **OpenAI** 会收购 Windsurf——因为当时新闻都报道了，各种消息都满天飞。然后，我们突然收到首席技术官（CTO）**Douglas** 发来的短信，他说：“明天早上来这家酒店的会议室见我，别告诉任何人。”我当时觉得这也太可疑了。但我们还是去了，我完全以为会见到 **Sam Altman** 或类似的人，对吧？我以为这会是一场“尘埃落定、准备庆祝”的聚会。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah, it was it was crazy. I actually don't know if anyone's told this story, but go ahead. So I I guess yeah I was on the research side and then if you remember at the time like we everyone thought that OpenAI would acquire Wind Surf like the the news had come out and everything and and so like we we get a a text before from our CTO Douglas and he's just like meet me in this hotel conference room like tomorrow morning and don't tell anyone else. I'm like this is so suspicious but we go over there and like I fully expected it to be uh like Sam Alman or something right and it was going to be okay. You thought you were going to like it was like it's closed like party time, you know?

</details>

**Len**: 没错，我也以为是那样。因为当时所有新闻都泄露了，说 OpenAI 将要收购我们。所以，我们去了那里，本以为会看到 OpenAI，结果我们到了之后，视频通话里居然是 **Demis Hassabis**，还有谷歌和 DeepMind 的高管们。我们当时就想：“好吧，看来我们要去谷歌了。”一切发生得极快。那是周四早上，就在当天，我们上交了 Windsurf 的工牌和电脑，第二天周五我们就已经作为正式员工坐在谷歌/DeepMind 的办公室里了。

<details>
<summary>Original English</summary>

**Len**: Yeah. Yeah. I mean, I thought like the news like everything had been leaked that it was going to be open AI acquiring us. And so I Yeah. We go there, we thought it would be open AI and then we go there and it's it's like Demis on the call and then like all of the like deep mind Google people. And so we're like, "Okay, I guess we're going to Google then." And it all it all just happened super fast. Like that was on a Thursday morning. Uh that same day we just we gave up like all of the like badges, computers to win surf and then the following day we were at Google like full employees or like at Deep Mind

</details>

**Ronuk**: 确实，就是快得令人难以置信，而且新闻我记得是在周五早上出来的。所以，是的，所有事情都在那一周内发生了。

<details>
<summary>Original English</summary>

**Ronuk**: and so it just it was just like insanely fast and and like the news came out I think Friday morning. So uh yeah, it all just happened that week.

</details>

**Len**: 是的，然后 **Cognition** 在周一买下了剩下的部分。

<details>
<summary>Original English</summary>

**Len**: Yeah. And then Cognition bought the rest on Monday.

</details>

**Ronuk**: 是的，没错。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah, exactly.

</details>

**Len**: 是的（笑）。非常非常疯狂。听到 Demis 亲自参与了这个交易，真的很酷。我知道当时有几位谷歌的高层，比如 **Sergey Brin** 在推动这件事。显然，这在一定程度上是一次人才收购（acquihire），但我想他们也必须向团队展示愿景。当时大概有 30 个人左右吧，去沟通“你们在 DeepMind 要做什么”。

<details>
<summary>Original English</summary>

**Len**: Yeah. [laughter] Uh yeah, very very crazy. And uh it's very cool to hear that Demis was involved in the deal. I I know that like I think there was like several people like senior people like Sergey um pushing for it and obviously like it it's kind of like a aqua hire but also I think they had to just pitch the team. There was like 30 people or something on like okay what are you doing at Deep Mind?

</details>

**Ronuk**: 是的，当时涉及了很多高管。Sergey 也是其中之一，他是对 Windsurf 最感到兴奋的核心人物。实际上，他还在后来发布的 **Antigravity** 发布视频里担任了主角。我认为对于谷歌和 DeepMind 来说，他们也开始意识到，仅仅拥有顶尖的模型是不够的，你还需要知道用户实际上在如何使用产品，需要看到所有这些反馈信号——就是我们在 Windsurf 捕捉到的所有信号，并能够真正闭环。所以，我们去了 DeepMind，推出了 Antigravity，并有机会为 **Gemini 3** 的研发做出了贡献。看到一家拥有海量算力的巨头公司能够真正做些什么，并真正利用最前沿的技术，这真的很棒。而且我认为现在大家开始意识到，你不能只在离线基准测试（benchmarks）上进行训练，或者一味扩大人工标注的数据规模。你必须真正理解人们在现实世界中是如何使用产品的，尤其是随着 AI 在现实应用场景中变得越来越普遍。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah it was um there were a lot of execs involved. So Sergey as well he's he's like the main guy that was super excited about Windsor. Um, he was actually on I don't know if you saw the anti-gravity launch video that came out, but uh he was a a main character in that as well. And and I think for Google and DeepMind, they're also starting to realize that you need to not just own really stellar models, but you also need to know what users are actually doing with products and like seeing all of that signal, all the stuff that we were capturing at Windsurf and being able to like really close that loop. And so then, you know, we we went over to Deep Mind and launched anti-gravity got to contribute to Gemini 3 as well. And it was really awesome like to see what a powerhouse of a company with a ton of compute can actually do and and really really leverage just like cutting edge technology. And I think now everyone's starting to realize that you can't just train on like offline benchmarks or like scaling up human labelled data. You really need to understand like what people are doing in the real world especially as AI is becoming more and more prominent for real world use cases.

</details>

**Len**: 是的，完全赞同。我的意思是，这个论点在今天显然得到了印证，即使是 **Cursor** 和 **xAI** 也在做类似的交易。

<details>
<summary>Original English</summary>

**Len**: Yeah, totally. I mean and that thesis clearly is panning out today even with Cursor and XAI doing a similar deal.

</details>

**Ronuk**: 没错，就是这样。

<details>
<summary>Original English</summary>

**Ronuk**: Exactly. Yeah.

</details>

### 创立 Trajectory 的愿景

**Len**: 那么，我很乐意把时间快进到你做出决定的一刻。你知道，你在 DeepMind 有一份非常舒适的工作。我确信他们付给你数百万美元让你做你正在做的事情。是在哪一个瞬间，你觉得：“好吧，不行，是时候离开去创立这家公司了”？

<details>
<summary>Original English</summary>

**Len**: So, yeah, I'm happy to fast forward to when was the moment you decided, you know, you have a Kushy job at Deep Mind. I'm sure they are paying you like millions of dollars to just do what you're doing. Um, where's the moment you're like, "Okay, no, like you know, it's uh it's time to go start this thing."

</details>

**Ronuk**: 是的，显然那次收购总价是 20 亿美元，我们去了 DeepMind。然后我决定放弃收购带来的所有优渥报酬去创立 Trajectory，这完全归结于一个原因。显然，我们一直在见证代码领域的这些创新以及现实世界的实际应用，但现在非常清楚的是，在每一个其他领域，我们也将迎来同样的爆发，比如法律、医疗、金融。它们都将像过去几年的代码领域一样，获得极大的赋能。但另一方面，在经历这种转型的同时，现在的 AI 虽然显然非常强大，但它的行为方式和任何其他软件一样是极其静态的。也就是说，你昨天使用的模型，明天还会犯同样的错误。你在任何产品中所做的所有纠错和编辑，实际上都被浪费掉了。我意识到，虽然有一些技术（例如我们在 sui 1 做的，或者 Cursor Composer 甚至 **Cloud Code**）开始围绕产品和人们在现实世界中的实际操作来构建模型，从而形成了一种让他们能够保持领先的“复利循环”（compounding loop）——而这正是我想要带给每一家公司的能力，也就是人们现在所说的持续学习。于是，我和我的联合创始人们聚在了一起。我提到过他们来自斯坦福，我们在大一入学第一周的数学课上认识，他们后来在研究界也做出了非常棒的成果。**Michael** 在 DeepMind 工作了很长时间，专注于机器人技术，曾参与 Gemini 1.5 机器人版本的发布，并领导着那里的一个思维团队（thinking team）。而 **Arjun** 在苹果公司（Apple）参与 **Vision Pro** 项目很长时间，致力于核心交互模型的设计与训练，并在首发当天将其推向了所有 Vision Pro 用户。所以，在某种程度上，我们所有人都在研究 AI 如何与现实世界进行交互——无论是通过代码、机器人技术还是 AR/VR。我们意识到，持续学习是实现这一目标的终极范式：你如何将人类置于反馈环路中？如何围绕他们构建这种能够自主不断学习和成长的智能？我认为这将是 AI 的下一个重大解锁，即捕获现实世界的实际使用数据并将其发扬光大。

<details>
<summary>Original English</summary>

**Ronuk**: I Yeah, obviously the acquisition for was for $2 billion and went over to Deepine and then I decided to give up all the acquisition money to start trajectory and it all came down to so I obviously we've been having all of these innovations and coding and and seeing that real world usage, but it's very clear now that we're getting that explosion for every single other domain, right? like legal, healthcare, finance, they're all going to be supercharged in the way that coding was for the last few years. And the other part though is as we're getting this kind of transformation, it's still that AI like it's it's obviously very powerful, but it kind of acts like any other software uh in that it's very static. Uh like the model that you used yesterday, it's going to be the same model making the same mistakes tomorrow. All of those corrections you gave it, the edits like in any product is all just being put to waste. And and I think I realized that okay there are a few technologies like we did at su 1 like cursor composer even cloud code uh that are starting to build the model around the product and what people are actually doing in the real world and this is that compounding loop that allows them to pull ahead that is what I want to bring to every single company that power of continual learning as people now refer to it and and so you know I I got together with my co-founders I mentioned they're from Stanford we we at in the math class in in first week of freshman year and uh they went on to do awesome stuff in the research world as well. So Michael was at deep mind working on he was in deep mind proper for a long time working on robotics there. So he was on the Gemini 1.5 robotics release and uh leading a thinking team there and then Arjun was on the vision pro for a long time. He he was working on the core interaction models and training those shipped those day one to to all the vision pro users. Um and so in some way or another all of us were kind of working on how AI interacts with the real world right through either coding robotics with ARVR. And we realized continual learning is kind of the ultimate like paradigm to do that is like how do you have humans in the loop? How do you build this intelligence around them that is constantly learning and growing on its own? And I think that's going to be the next major unlock of AI is is capturing all this real world usage and and really going with it.

</details>

**Len**: 听到这些非常令人兴奋，而且大体上非常正确。这很奇妙，因为你们三个人去了这么杰出的不同公司。这简直就像是你们提前计划好的一样，你们说：“好吧，我们先分开一段时间，然后再聚到一起。”那么，既然你们决定致力于解决这个问题，你们的方法是怎样的？我知道持续学习是很多人关注的热门话题，但人们从不同的角度切入，有的人主张直接将知识训练进模型权重（weights）中，有的人则主张只保留一堆 Markdown 文件里的技能等等。你如何看待持续学习中的这些流派，以及你们所选择的道路？

<details>
<summary>Original English</summary>

**Len**: Yeah, I think that's very exciting to see. I think broadly very true. It's weird because all three of you went to such like notable companies. It's almost like you planned this like you're like, "Okay, we'll split up for a while and then we'll come back together." Yeah. So, so okay, you you decide to work on this problem and I guess what's the approach like you know like I I think continue learning is a hot topic among a lot of folks, but I think people approach it from different angles from like the train it into the weights versus just have a bunch of skills and markdown files or whatever. you really see Laura recently just I guess like just just tell people more about like maybe with the schools of thought in continued learning and and the one that you're choosing.

</details>

### 持续学习平台与 Harvey 合作案例

**Ronuk**: 确实。我认为从客户的角度来看待这个问题会很有帮助，而不是光谈论支撑这一点的研究和技术。以像 **Harvey** 这样的公司为例。他们拥有大量复杂的法律工作流，智能体在其中需要研究文档，然后修改合同条款。与代码领域不同，在代码中，技术受众可以很容易地引导智能体走向正确的方向，我们对错误也相对宽容；但对于法律这样的领域，做到 80% 的正确率就等于零。在许多领域，他们拥有非常专业的专家操作数据。当智能体尝试某项任务而失败，用户不得不介入并修正它，完成剩下的 20% 时，这就是我们可以用来学习的极具价值的信号。实际上，我可以分享我的屏幕，展示我们与 Harvey 合作的一些工作。不过，在此之前，我们为所有这些公司构建的，宏观上是一个持续学习的平台。我们基本上收集所有的数据、所有专家的交互轨迹（traces）和智能体的表现，并将其提炼为一种单一的格式，我们称之为“**轨迹（trajectory）**”。它本质上是创建评估（evals）、裁判（judges）、模拟环境等所有训练所需组件的基石数据。然后，我们能够创建一个端到端的自助式平台，用于优化智能体、模型和整个框架系统。目前，我们从模型开始。对于每家公司来说，这是最主要的核心竞争力——能够拥有在各自前沿领域更快、更便宜、更出色的自定义模型。我可以分享我们与 Harvey 合作的一些成果，这非常令人兴奋。Harvey 非常关心的一点是，作为受监管行业，他们希望拥有主权智能（sovereign intelligence）。因此，我们与 Harvey 以及 **Nvidia** 合作，训练了 **Nemotron 3 Super**，以在他们关心的许多法律工作流中达到帕累托前沿（Pareto frontier）。在此我可以快进展示，我们实际上成功捕捉到了 Harvey 实验室的数据集以及他们的很多专业法律工作流。他们关心的指标包括：问题识别、分析、解释、引用、参考、完整性、覆盖率等。所有这些工作都有专业的律师助理和律师在公司内部进行关键任务的操作。通过我们的模型，我们能够全面提升这些维度的指标。而且非常酷的一点是，与前沿模型相比，Nemotron 是一个便宜得多、速度也快得多的模型。当你在大范围内向成百上千甚至数十万用户部署时，这一点至关重要。因此，这对于法律领域来说是非常令人兴奋的成果，也是我们在平台上能够实现的。另一个令人兴奋的部分是，因为我们将此构建为一个高度可扩展的平台，我们能够获取不同格式的数据源，而无需任何前线部署（forward-deployed）的工作，并真正提升模型性能。一个很好的证明是：刚开始我们与几家公司合作——目前的合作伙伴包括 **Clay**、Harvey、**Rogo**、**Decagon** 等。第一次合作时，我们花了大约三个月的时间来设置整个系统，就像边飞边建飞机一样。而现在，我们可以在一个月内为 Harvey 训练出一个模型；而在上周，我们入驻了一位新客户，在短短一周内，我们就训练出了模型并让飞轮运转了起来。所以，亲眼见证持续学习在实践中是如此强大，真的很酷。我们显然才刚刚开始，我希望能够为每一个推动前沿知识工作的公司提供支持。

<details>
<summary>Original English</summary>

**Ronuk**: Totally. So I think it's helpful to actually like we've been talking about just like the research and and stuff that like enables this. I think it's useful to think about this from the customer's perspective. So take a company like Harvey for example. They they have a ton of complex legal workflows where agents are trying to research documents and then redline a contract. And unlike coding where we can obviously a technical audience can just like guide the agent in the right direction, we're able to be tolerant to mistakes for a field like legal like getting 80% of the way there is the same thing as zero. And and this is for a lot of fields where they have very expert data of what people are doing. Maybe an agent attempts something and then the user needs to go and correct it and get the rest of the 20% of the way there. That's that useful signal that we're able to learn off of. So actually we uh we I I can share my screen and show some of the work we've been doing with Harvey. But uh I guess before I get there, the the high level of what we've built for all of these companies _ is a platform for continual learning. We we essentially take all of the data, all of the expert traces, the agents and distill it into one format which is what we call the trajectory. And it's basically all of the data that is needed to then create the evals, the judges, the environments, everything, all the components that you would need for training. And then we're able to create that end to-end loop of a self-s serve platform to optimize the agent, the model, the harness, everything. Right now, we're starting with the model. And that's what the the major kind of alpha is for every company is being able to own models that are faster, cheaper, better at the frontier. And so I can share some of what we've done with Harvey, which is really exciting. One of the the main things that Harvey really cares about is obviously they're a regulated industry. They want to have sovereign intelligence as well. Um and so we partnered with Harvey and Nvidia in order to train Neatron 3 super _ in order to get to the paro frontier. a lot of the legal workflows that they care about. I can actually fast forward over here where we were actually able to capture with along with Harvey's lab _ data set a lot of their expert legal workflows. And so um the things that they care about for example are issue spotting, analysis, explanation, citation, reference, completeness coverage _ etc. and all of these things the they have sort of like parallegals and lawyers _ going in-house and working on mission critical tasks and so with our model we were actually able to improve these sort of metrics across the board and then also the the really cool part is Neimatron is a drastically cheaper and faster model than the frontier and this matters at scale when you're deploying to not just a few users hundreds and thousand hundreds of thousands of users across the board. And so this is something that's very exciting for the legal domain and something that we're able to do on our platform. The other exciting part is because we're building this I think essentially like every company has their data sources in different formats. We're able to build this as a scalable platform that gets all of that data without any kind of forward deployed work and really improve the model. And _ the cool kind of proof point is we started out with working with a couple companies. Our _ current partners are Clay, Harvey, Rogo, Dakugon, Mor. The first engagement, it took like three months to like set up the entire thing. We're kind of building the airplane as it was flying and now we're able to train a model with Harvey in under a month. and then onboarded a new customer and within a week we were able to train a model and really get the flywheel going. _ So it's _ it's really cool to see just like how powerful continual learning is in practice. We're obviously just getting started and I want to be powering kind of every company that _ is pushing the frontier and knowledge work.

</details>

### 开源模型与中美 AI 差距

**Len**: 是的。恭喜你们。我有一些看法。首先，我想你们是我遇到的第一个使用 Nemotron 3 Super 的团队。关于这个基座模型，与通常人们选择的比如某个中国开源模型相比，你有什么评价？

<details>
<summary>Original English</summary>

**Len**: Yeah. Yeah. Congrats on this. I mean a couple observations. First, I think you're the first team doing this I've encountered using Neimotron 3 Super. Any comments on them as a base model versus you usually, you know, people who choose like one of the Chinese models?

</details>

**Ronuk**: 是的。我的意思是，看到开源社区的蓬勃发展真的很棒。显然，中国在模型方面做得非常好。我记得当初我们在 Windsurf 的时候——

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. Yeah. I I mean, so I think it's really awesome to see the open source community just in general. Like obviously China has been like killing it with models. I remember back when we were at Windsurf

</details>

**Len**: 是的，**Qwen**（千问）现在被公认是一个非常强大的后训练模型——

<details>
<summary>Original English</summary>

**Len**: Yeah. 31 is now known to be a post train of

</details>

**Ronuk**: 是的，我想回到 2024 年那会儿，开源模型还非常落后。你可能有一些 Qwen 模型，还有 **DeepSeek 2**，但它们当时看起来并没有那么有希望。然后突然之间，**DeepSeek-V3** 问世了，每个人都惊呼：“哇，他们正在使用最前沿的范式！”他们显然向世界展示了 **GRPO**（群体相对策略优化）。我认为从那以后，差距一直在被不断拉近。美国或者西方世界还有很多工作要做，显然目前我们还没有像 Kimi 那样拥有一万亿参数的模型，以及像 GLM 和 DeepSeek 这样令人惊叹的模型。我认为我们在那种超大尺寸的模型上还没有完全赶上。但是你已经可以看到，比如一年前 OpenAI 在西方发布的 **gpt-2**（或类似模型）是当时最好的基座模型之一。而自那以后，Nemotron 已经变得明显更好了。请记住，这是一个 12B（120 亿参数）的模型，与它的尺寸相同。因此，随着时间的推移，英伟达正在投入巨资，西方世界也正在准备迎接更多优秀的开源模型，这对于法律、金融、医疗等领域非常重要。我们希望能够领先于这一趋势，并真正使其成为我们平台中强大的部分。

<details>
<summary>Original English</summary>

**Ronuk**: well and I think back then like before in like 2024 or so like open source was so far behind and you had like some Quen models you had Deepseek 2 and it just like didn'\''t seem promising and then all of a sudden Deepseek V3 comes out and everyone is like wow the they'\''re using Frontier Paradigms they obviously open source or like showed the world GRPO and I think since then the gap has and closing and closing over time. I think America or the the western world has some work to do still like obviously having one trillion parameter models like Kimmy like and and amazing models like GLM and Deepseek. Uh I don'\''t think we'\''re quite there yet for that size of model. Uh but you can already see like um I mean GP2s was kind of one of the best base models a year ago that OpenAI put out in the Western world. Like since then, Neatron has gotten significantly better. And keep in mind, this is a 12V model, so same size as GP2s. And and so I think as time goes on, like Nvidia is investing a ton of money. The the world is _ is gearing up for I think a lot more open source models in the Western world as well. _ which does matter like for legal, for finance, for healthcare. And and so I think this will be a leading paradigm. And so we wanted to be ahead of the curve and and really make that a powerful part of our platform.

</details>

**Len**: 明白了，我相信英伟达听到这个会很高兴的。

<details>
<summary>Original English</summary>

**Len**: Got it. I'm sure Nvidia will be happy to to hear that.

</details>

### 持续学习的数据清洗挑战

**Len**: 另外——

<details>
<summary>Original English</summary>

**Len**: Uh the other

</details>

**Ronuk**: 对，我觉得另一件事是，对我来说，为什么大家没有尝试所谓的在线模型或持续学习，一个普遍问题在于数据的清洗与处理（data curation）。在这里，数据清洗的解决方案是什么？

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. I I think the other thing also is I so for me the general question of like why people haven't pursued you know let...

</details>

**Len**: 是的，完全是这样。我认为这里有趣的地方在于，每个公司存储他们使用数据的方式都略有不同，对吧？你的系统基本上包含两件事。第一，智能体在产品中做什么？比如在 Cursor 中，它们显然是在编写代码、运行命令；而在营销（GTM）工作流中，智能体可能是在创建表格或丰富列数据。这是容易的部分，可以表示为 OpenAI 的“工具调用/工具响应”（tool call / tool response）格式。然而，有趣的部分是，用户在产品中还做了哪些其他操作？例如，在 Windsurf 中，用户可能会在智能体编写完代码后修改代码。他们会说：“嘿，实际上在智能体生成网站后，我想要把这个按钮放在左边”，或者“我想要用这种方式设计类结构”。这些都是在产品交互中发生的非常有用的信息。我认为当人们想到在线学习或持续学习时，他们首先想到的是“接受/拒绝”或“点赞/点踩”这类二元信号。事实证明，这些信号实际上噪声极大。你可以想一想，你上一次在 Cursor 或是 Cloud Code 里点赞或点踩是什么时候？几乎没有过，对吧？大家往往都是基于直觉（vibe）接受一切。所以，这些信号实际上相当嘈杂。真正有用的是那些方向性的信号——比如用户说“嘿，你应该往这个方向走”，或者直接修改智能体的一些尝试。这种模式在任何产品中都是通用的。在法律工作流中也是如此：智能体尝试做一些研究，然后修改一些条款，或创建 Excel 表格；之后律师回过头来，可能因为智能体遗漏了某些东西而不得不做更多的研究，然后修改合同的某些部分。因此，现在的难点在于：你如何收集所有这些数据，然后将它们压缩成适合训练的格式？在这方面，我们一直在开发两个非常令人兴奋的东西。一个是纯粹的基础设施问题：我们找到了一种方法来获取所有防区信息，并构建了一条**自动研究管线（auto research pipeline）**，能够将用户行为的向量转换为评估（evals）、裁判（judges）和模拟环境。但另一个令人兴奋的部分，则是持续学习背后的实际算法。为此，我们最近发布了一项非常酷的研究，展示了我们如何扩展 **SDPO**（Self-Distillation Policy Optimization，自蒸馏策略优化）。如果你对这个不太熟悉，我可以简单作个高层级的介绍。对于强化学习（RL）来说，目前的领先的后训练范式是：智能体去探索世界很多次，最后获得一个奖励信号（reward signal）。这个信号可能来自裁判，或者来自生产环境；然后你利用这个数值来进行更新，判断整个交互轨迹是好是坏。这在目前非常有效，所有的前沿模型都是用强化学习训练出来的。但它在持续学习的新世界中并不能很好地工作。原因在于，强化学习将现实世界中所有这些有用的纠错和编辑信息全部压缩成了单一的一个数字，这实际上是把信息漏掉了。而自蒸馏（self-distillation）做了一件非常酷的事情。它的核心原理是：通常的蒸馏是指你有一个“学生”模型（通常是较弱的模型）和一个“教师”模型（较强的模型），你把教师的知识蒸馏给学生。但自蒸馏的精妙解锁在于，你实际上不需要一个更聪明的外部教师。你的学生模型可以是目前最聪明的模型，而为了让它作为教师时更聪明，我会把一些特权信息（privileged information）或暗示（hint）放入教师的上下文（context）中。这样，我就突然拥有了一个稍微更聪明一些的“教师”状态来引导学生。在实践中，这看起来像下面这个例子：假设智能体被问到“我的飞往纽约的机票多少钱？”，智能体查找了一些信息，但最后给出了错误的机票信息。现在，因为在生产环境中我们拥有用户的隐式纠错数据，我们可以返回并给教师模型一个“聪明的暗示”。然后，我们让学生模型的对数概率（log probs）与教师模型包含暗示后的输出相匹配。这样，我们就能引导模型，这不仅仅是给予一个二元的奖励，而是利用真实的文本信息真正引导模型走向正确的方向。这是 SDPO 的巨大解锁。

<details>
<summary>Original English</summary>

**Len**: Yeah. Yeah, totally. So I think the the interesting thing here is like every company is storing their usage their their data in slightly a different way, right? And you have this entire system of basically _ two things. One, what are agents doing in a product? _ so you can imagine for cursor they're obviously like writing code, they're running commands. _ and then for like I don'\''t know a GTM workflow, it could be that the agents creating tables or enriching columns and then so that's the easy part. That'\''s like in a open AAI like tool call tool response format. The interesting part though is what are all of the other things that users are doing in a product. And so at Windsor for example this was users are modifying the code after an agent. They'\''re saying like hey I actually wanted this button on the left after the agent wrote a website or like I wanted this class structure this way. That'\''s all the very useful information that'\''s happening in a product. I I think when people think about like online learning, continual learning, they'\''ll first think of like like accept reject or thumbs up, thumbs down, like some of those like kind of binary signals. _ It turns out that that'\''s actually like very noisy. You can imagine like when is the last time you put a thumbs up thumbs down in cursor or cloud code never, right? And everyone'\''s kind of vibe accepting everything. So it turns out those signals are actually quite noisy. But it what is useful is all the directions of like the user is saying hey you should have gone this way or like modifying some of the attempts of the agent. And the cool part about this is this works in any product. So _ for a legal workflow it'\''s the same thing. the agent attempts to do some research and then write some red lines or create an Excel spreadsheet and then afterwards the lawyer goes back and maybe has to do some more research because the agent missed something and that sort of taste and then again also like modifying some of the contracts and so now the tricky part is how do you take all this data and then condense it into the right format to train on and so there'\''s a couple of really exciting things here that we'\''ve been working on. One is just purely an infrastructure question. When we figured out a way to take all this information and build an auto research pipeline that is now able to take like whatever these vectors are of what the user is doing and make those into judges into Eval'\''s environments. _ but the other exciting part is the actual algorithms behind continual learning. Um, one of the other really cool things I'\''ll just go ahead and make share my screen again _ that we released very recently is scaling updo self distillation policy optimization. So if you'\''re not familiar with this I can give the high level real quick. So for RL basically the way RL works and that'\''s kind of the leading post training paradigm is you have an agent and it goes and explores the world a bunch of times and then at the end of the day you get a reward signal. It could be a judge, it could be like something from production and then you basically take that number and then use that to update and say like hey this entire tra trajectory was really good. this entire trajectory is really bad and then it learns from that. So it works pretty well. Obviously all of our frontier models that we see today are trained on RL but it doesn'\''t really work for this new world of _ continual learning. The reason is RL it'\''s still taking all of this kind of useful information from the real world like I mentioned all the corrections and everything and putting it into just one number which is really broken. And so what self distillation does which is really cool is takes or I guess the high level here is we start out with a student roll out. So if you'\''re familiar with distillation in general it'\''s you have a student that is usually a less smart model and then a teacher which is a smarter model and you'\''re basically saying okay let me distill all the smart stuff from the teacher into the student. The cool unlock with self-distillation is you don'\''t actually need a smarter teacher. Your student could be the smartest model, but to make the teacher smarter, I'\''m actually going to take some privileged information or a hint _ and put that into context of the teacher and now I have a suddenly slightly smaller smarter model that I can fit into. So in practice, what this looks like, let's take this example here where we have an agent, it'\''s asking or a user ask like how much is my flight ticket to New York? we have the agent like look up some stuff _ and then we we actually get like the wrong ticket information. Now we can actually go back because from production we have some hidden information and we can say actually _ let me give the teacher a smart hint. Then we match the student log props to that _ teacher information and then suddenly we'\''re able to take not just like a binary reward but truly like actual text and guide the model in that direction. So this is a huge unlock of STPO

</details>

### 突破性的 SDPO 算法原理

**Ronuk**: 我们在算法的扩展和优化上做了一些非常令人兴奋的改进。自蒸馏在学术界有很多案例，但没有人真正能够将其扩展并应用到真实世界的工业场景中。我们在 MARO 推出的一款出色的真实行为基准测试 **Apex Agents** 上进行了训练，结果显示在这些工作流上取得了非常惊人的提升。例如，模型的收敛速度提升得快得多。相比于通常的 GRPO 风格训练，自蒸馏能够明显更快。我们在博客文章中也展示了这一点。我们还做了一些修改，以便能够在真实的脱机策略（off-policy）数据上进行训练，即生产环境中的真实数据，而不是仅从当前模型生成的在线数据，这使得它对现实世界的场景更具鲁棒性。

<details>
<summary>Original English</summary>

**Ronuk**: and we've done some very exciting kind of modifications and scaling it up. It's been done in a lot of academic cases but no one's actually been able to scale it up to real world use cases. So we started training on Apex agents which is a an awesome benchmark that Maror put out which is modeling a lot of real world behavior and we're able to see very amazing gains on some of these workflows. So for example also the convergence rate just like goes up way faster. This is normal _ gpo style training and then we're able to obviously be way faster. So this is this on our blog post as well. It's very awesome to see and we do some modifications as well to training on real off policy data which is like what happens in production not necessarily from your current model and making it a lot more robust to real world use cases.

</details>

**Len**: 是的，这确实是项令人难以置信的工作。我简直无法相信，你们作为一个只有三个人的初始团队，居然能够一边开发产品，一边发布如此高水平的学术研究。

<details>
<summary>Original English</summary>

**Len**: Yeah, that's this is incredible work. I can't believe you basically shipped like research alongside of your products and it's a it's a team of three.

</details>

**Ronuk**: 实际上我们现在已经有 11 个人了。我们一直在快速成长。我们——

<details>
<summary>Original English</summary>

**Ronuk**: Well, so I actually we we have 11 of us now. So we've been growing really fast. We uh

</details>

**Len**: 确实。你们有非常漂亮的办公室。

<details>
<summary>Original English</summary>

**Len**: Yeah. You have a nice office.

</details>

**Ronuk**: 是的，哈哈。我认为，为了在这个领域构建真正棒的东西，我们必须将自己定位为一家“产品公司加研究实验室”。因为我认为这需要最前沿的研究——目前的算法还不足以实现真正的持续学习。所以这是我们探索的重点。但同时，这也需要深度理解客户并构建出色的交互界面。目前，还没有人真正为“每天都在变得更聪明的智能”设计出合适的产品界面。我认为这里有很多非常有趣的界面交互问题。但我们的团队真的很棒，我们从 OpenAI、Meta Super Intelligence、Amazon AGI 招募了令人惊叹的研究团队，当然还有来自 DeepMind 和 Apple 的联合创始人。我们也在大力发展产品团队。我们有来自 **Stripe** 的成员，他们正在构建大量的后端 SDK；还有来自 **Figma** 的成员，负责深入思考并设计这些交互界面。因此，我认为要实现这个目标，必须在产品和研究两个维度上同时发力。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. Yeah. Yeah. Um I I think in order to build something really awesome in this space, we we think of ourselves as a product company and a research lab. _ because I think it requires cutting edge research. The current algorithms aren't quite there yet to get to true continual learning. And so that's a lot of what we're exploring. But then it also requires deeply understanding customers and like building a good interface. No one's really made the product for when intelligence is just getting smarter every single day. And I think there's a lot of very interesting interface questions here. So, but the team is really awesome. We we've hired an amazing research team from OpenAI, from Meta, Super Intelligence, from Amazon AGI, and then obviously co-founders from from Deep Mind and Apple. And then also really growing out the product team as well. So, we we have someone on the team from Stripe who is building a lot of backend SDKs and then _ someone from Figma as well. _ really thinking about these interfaces and designing them. So I I think it's a concerted effort across both product and research to get here.

</details>

**Len**: 是的。让我们深入探讨更多核心知识产权（IP），因为我不想打断你。你刚刚谈到了 SDPO 的一些精彩内容。你们还有像“轨迹发布五日谈（5 Days of Trajectory）”这样的活动，这真的是一次非常强劲的发布。我想这是我在这个领域见过的最棒的发布之一。来，继续说，不要管我，哈哈。

<details>
<summary>Original English</summary>

**Len**: Yeah. Let's go through more of the core IP because I don't want to cut you short. You you were just getting into some good stuff with SDPO. You have like this like 5 days of trajectory which is also like very very strong launch. I think one of the strongest I've ever seen, you know, in in this space. _ Yeah, keep going. Like don't let me [laughter]

</details>

### 开源分布式 LoRA 训练架构

**Ronuk**: 好的。我想我可以再分享一个成果。这很有意思，我们在研究和产品上做了这么多，能够在我们的“五日谈”中向世界展示这些真的太棒了。在 Trajectory，我们的目标是真正赋能每一个公司步入持续学习的世界。当你能够将一个产品推向几百个用户，然后其后台的智能随着时间的推移自主增长，这是一种令人兴奋的体验。因此，我们做的另一件令人兴奋的事情是开源了一个**持续学习训练栈（continual learning training stack）**。这是与伯克利大学的 **SkyRL** 实验室以及 **Anyscale** 合作完成的。基本上，在此之前的训练模式非常线性。如果你曾经用 **Slurm** 或者常见的训练集群启动过一个任务，你就会知道：你启动一个任务，它开始分配资源，启动 GPU 以进行采样和训练，运行整个训练任务 the life cycle，然后释放资源。这是训练的常规运作方式。但问题是，对于持续学习来说，你并没有明确的“启动”和“停止”阶段。你可能在同一时间运行着多个并发的任务。因此，正常的训练范式在这里就失效了。这与几家分布式 **LoRA** 基础设施公司持有的观点非常相似。而我们的贡献是使这套系统对每一个公司开源。正常的任务生命周期是：设置、采样、训练、清理。而我们的 **Continual LoRA** 做的是：与其像这样线性地跑任务，不如把它们堆叠在一起，设立一个专门的训练池（training pool）和一个专门的采样池（sampling pool），然后并行地运行这些任务。结果非常酷。我们在不同尺度的实验上运行了它。你可以看到，即使在扩大实验规模时——比如两个并发任务——我们也能将实际耗时（wall clock time）减半。当并发数上升到 4 个、8 个任务时，我们依然能够非常好地处理并发。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. Yeah. Um I guess I can share one more as well. And _ yeah, it was super fun. like we've just been doing so much across research and product and so it's really awesome to to be able to showcase that to the world in in our 5 days of trajectory. So I I can share one more as well is _ I mean our our goal is trajectory is to really empower every single company to just like get to the world of continual learning. It's such an exciting unlock when you can just put a product out there to a couple hundred users and now the intelligence just grows over time. And so one of the other exciting things we did is is open sourcing a training stack for continual learning. And so this is _ in conjunction with Sky RL _ Berkeley's Sky RL lab _ in any scale as well. And so so basically the the high level here is up until now with training it's very much like a linear like if you're ever kicked off a run with like slurm or or one of these like normal training clusters it's like you kick off a job it like starts to spin up a bunch of resources spin up the GPUs in order to do the sampler do the training and then you run the entire life cycle of the training job and then spin it down. This is like normally how training works. The problem is with continual learning, you don't really have like training explicitly starting and stopping. You're probably running concurrent jobs at the same time. And so the normal training paradigm start to break apart. This is also very similar to the thesis like _ like thinking machines like a few of these other like distributed Laura _ sort of companies infrastructure has had. Our contribution is to make this open source _ for every company. One of the things here is like okay so this is like normal life cycle of a job is like set up you do a bunch of sampling training and then clean up. What continuous Laura does is say hey instead of a bunch of linear jobs like this I can actually stack things together have one dedicated pool for training and one dedicated pool for sampling and then now I can start to put all of these pieces together and run jobs in parallel. And so the results are really cool. We ran this on several different scale up of experiments. And you can see that _ across the board, even as you scale up experiments, so like two concurrent jobs, we're able to cut the wall clock time in half. As this goes up to four jobs, eight jobs, we're able to run concurrency really well. And

</details>

**Len**: 为什么 8 个并发的时候曲线又往上走了呢？

<details>
<summary>Original English</summary>

**Len**: how come how come eight goes up?

</details>

**Ronuk**: 我也可以在这里分享我的屏幕。让我们过一下这里。

<details>
<summary>Original English</summary>

**Ronuk**: I can also share it here. Let me let's walk through here. So

</details>

**Len**: 好的。

<details>
<summary>Original English</summary>

**Len**: okay. Oh

</details>

**Ronuk**: 好的。这套机制的工作方式是：上面是串行训练运行（serial training run），你在固定数量的 GPU 上运行一系列采样和展开（rollouts）任务，这意味着你必须将作业一个接一个地顺序运行。而使用 Continual LoRA，如果是单任务完成速度，它实际上确实会慢一点——如果你只关心“让第一个任务以最快的速度跑完”，那你应该采用完全串行的方式，因为所有的资源重置都投向了那一个任务。但对于持续学习来说，你关心的是“让所有这些任务在运行中不断学习”。而且，数据往往不是以这种完美的顺序到来的，而是成批到来的。比如，你从生产环境中获得了新数据，现在你需要让第四个任务突然占用更多的资源。这使它变成了一个动态得多的工作负载。你可以看到，在这里，8 个并发运行的总耗时，大约只相当于串行运行 3 个任务的时间。这还没有完全推向极致。我们目前正在将其扩展到 16 个并发运行，并扩大模型尺寸（测试中是较小的模型，现在我们正在将其应用到 23B 到 35B 参数的模型上）。而且非常酷的一点是，这完全不会降低模型的表现。它依然运行相同的算法，我们在任何常规模型上都能看到相同的性能提升。我们还希望使其变得非常即插即用。我们在 SkyRL 平台上提供了一些关于如何开始使用它的说明，这非常令人兴奋。

<details>
<summary>Original English</summary>

**Ronuk**: yeah. Okay. So the way this works is okay so up here is like serial training run right like you're doing a bunch of sampling rollouts whatever but if you have a fixed set of GPUs then you have to run the job sequentially after another with continual Laura so it is actually slower per training job _ like if you just care about like I just want run one to finish as fast as possible then you should be doing like completely serially because all the resets are going towards that but with continual learning what you care about is just like let me have all of these runs like learning on the job. It also might be that like data is coming in not quite sequentially like this but maybe in batches right you get new data from production now you need to have like run four suddenly take up more resources. So it turns into a lot more of a dynamic workload and you can start to see here like like eight concurrent runs for example it takes about the same time as like sequentially like three jobs would take. And so this also scales out like we didn't fully push the bounds of this in this blog post. _ We're _ currently scaling this up to like 16 concurrent runs and scaling up to this was also on like smaller models as well like scaling this up to like 235bs. And _ and the really cool part is obviously like this doesn'\''t degrade performance whatsoever. It's still the same algorithms. We're able to see the same gains with any any sort of normal model. And _ and we wanted to also make this very plug-and-play. So we we have some kind of instructions here of just how to get started using it in Skyall which is really exciting. So

</details>

**Len**: 是的，作为一个操作系统（OS）爱好者，看到这里出现非常类似的调度问题——比如饥饿（starvation）、抢占式调度（preemptive scheduling）等词汇，觉得非常有意思。你一旦上过系统的课程，就会开始将它应用到每一个类似的问题领域中。

<details>
<summary>Original English</summary>

**Len**: yeah it's really funny as a operating systems fan like that you see like very similar like scheduler type problems starvation preemptive scheduling all these kinds of terms like you just take a normal OS class you like then you start applying it to every every problem domain like this.

</details>

**Ronuk**: 没错，完全如此。我认为在过去，模型训练很大程度上是一个科学研究问题，人们大多从科研的角度去解决它，而不在意所有这些分布式系统层面的创新。但突然之间，训练正在变得更加“生产化”（production-ready）。Trajectory 的终极目标是，每一家公司都能够持续开启自己的训练运行、不断学习并更新，这也要求我们以系统级或工程化的思维来构建训练栈。所以这只是个开始，我认为分布式计算领域的很多见解都可以应用到这里。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. Yeah. Exactly. I I think it's almost like training up until now has been a very research problem and I think people have attacked it from a researchy perspective where you don't care about all of these like kind of distributed systems innovations. _ and suddenly now like training is becoming more production right _ like the end goal of trajectory is that every company can be kicking off their own training runs like continuously learning updating and that also requires a training stack that is built with a systems level or engineering kind of mindset and so so this is just kind of the beginning but I think there's so many different insights from distributed computing that can be applied to here

</details>

### Trajectory 的未来产品路线与 Act 2

**Len**: 明白了。在这期节目播出的时候，你们的“五日谈”应该已经结束了。还有其他整体的技术赌注或方向想向观众透露的吗？

<details>
<summary>Original English</summary>

**Len**: got it by the time this comes Oh, you will have _ sort of finished your your 5 days. Any other sort of overall tech bets or directions that you want to hint the audience towards?

</details>

**Ronuk**: 是的，当然。我们产品目前的现状是，我们能够获取公司所有的嘈杂信息——即用户在产品中所做的一切有价值的信号，进行模型训练，重新上传，并提供可观测性（observability）和评估（evals）。但目前，这些主要还是技术栈中独立的组件，很多时候我们还在辅助管理和发起训练。我们下一步的重点，我们称之为公司的“**第二幕（Act 2）**”，是让这套系统对客户而言更加透明和易于理解。提供合适的可观测性工具，提供合适抽象级别的评估工具；第二，是给予客户控制权。我们希望让产品经理（PM）——比如管理一个智能体产品的 PM——能够清晰地看到：“嘿，我们的智能体在这些地方做得很好，但在这些区域仍然会失败。”接着，他们需要做的就是修改模型、调整各个组件，明天醒来，他们就拥有了一个更加聪明、并在生产环境中完全处于可观测状态的模型。所有这些都应该完全由客户掌控。这是下一个阶段的任务。在这之后，最令人兴奋的部分是，目前我们正在与我提到的那些原生 AI 公司合作，像 Clay、Harvey、Decagon、Rogo。不久的将来，我们将开始与科技巨头合作，你可以想象类似 **Airtable** 和 **Notion** 这样的公司。在此之上的下一个阶段，是进入《财富》500 强企业。为了到达那里，我们需要实现真正的持续学习：比如仅仅拥有一个可观测层，比如在沃尔玛（Walmart），我们观察用户在做什么，所有的手动流程是什么，然后开始分析：“嘿，或许今天使用一个现成的商用模型是行不通的，但我现在可以观察到用户究竟在做什么，理清模式，构建一个能够驱动模型的智能体，完美契合这个工作流。”你可以想象，任何公司的前端产品都应该从用户身上动态学习并不断自我更新。为了实现这一点，战术上我们从模型开始，但很快我也希望改进系统外壳（harness）、提升技能库、甚至可能构建记忆层（memory layer）。我认为所有这些的结合，才是持续学习的完整解决方案。你也提到了这一点，我也认为所有这些都超级重要，尤其是它们之间的相互作用——目前没有人真正知道如何协同优化系统外壳与模型。我认为这里面有非常有趣的研究空间。这些都是我们非常兴奋能切入的领域。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah, totally. So, this where we're at with the product right now is we're able to take all the kind of noisy information from a company like all the valuable signal of what people are doing in a product, be able to train the model and then re-upload that and then have that like observability, the evals, all of those things. But right now it's still kind of like these single components of the stack and a lot of these things like we are we are kind of like managing or or looking at like kicking off the training runs. The next step after this is one I like it kind of what we think of as act two of the company is I want to make this legible to the customer. So just like the right observability tools, the right abstraction levels for evals and then second give them control. So like I I want to have the customer say like a PM should that's like managing an agent product should be able to say hey okay here's where my agent is really good here are the areas where it's still failing and now all I have to do is just like modify the model modify like all of the pieces and suddenly tomorrow I wake up and I have a smarter model that I can see in production all of those things like should be in control of the customer. So that's the next phase. _ and then after that the most exciting part is right now we're working with these AI native companies I mentioned Clay Harvey Deca Gun Rogo _ soon we'll be working with the kind of tech incumbents you can imagine like the air table notion those sort of companies the stage after that is fortune 500 and in order to get there we need to get to true continual learning that I can just have just the observability layer right like I'm observing let's say in Walmart like what are users doing what are all of the manual kind of process es and then start to say, hey, okay, maybe a model isn't even possible today if you were to just use an off-the-shelf sort of model, but I can now observe exactly what users are doing. I can start to see the patterns, build out an agent to harness a model that all works perfectly for that workflow. And now you can imagine any sort of company, their front using product should just dynamically be learning from their users and constantly updating. in order to get here as well tactically we're starting with the models but very soon I I want to be also improving the harness improving skills doing maybe even the memory layer as well I think all of those in conjunction are the continual learning solution yeah I know you mentioned that at the beginning as well and I I think all of those are super important and also the interplay between the two like no one really knows what it means to train the har like optimize the harness and the model together right and I think there's very interesting research there and what that looks like so these are all very exciting areas that We're we're like super stoked to get into.

</details>

**Len**: 这是否意味着值得仅仅把代码作为一个可验证的领域来关注，还是说你们对领域是不做限制的？因为你们也接了法律和其他行业。

<details>
<summary>Original English</summary>

**Len**: Is it worth focusing on coding alone as a verifiable domain or are you un unopinionated because you got legal or you got the other stuff?

</details>

**Ronuk**: 对。我的看法是，就像我们过去两年在代码领域所见证的爆发一样，这将在每一个公司和每一个领域发生。所以我们的论点基本上是：代码虽然发展极快，但让我们去加速其他行业，首先帮它们达到代码领域目前的水平，然后通过持续学习真正改变所有的行业。这就是为什么我们最初就选择与不同垂直领域的公司合作，以确保我们的平台是完全领域无关（agnostic）的。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. So for us, I mean I I think that just like we saw in coding for the last 2 years, I think that's going to happen for every single company and and every single domain. So our thesis was basically okay like coding is moving super fast. let's accelerate the rest of these industries to first just get to where coding is, but then after that like truly transform all of them with continual learning. So that's why we're starting with also companies in different verticals to also build our platform so that it's agnostic to whatever domain you're in.

</details>

**Len**: 好的，非常酷。极具雄心。在与你交谈之后，我终于更加理解了你们的愿景，希望听众们也能感受到这一愿景的宏大。人们应该去哪里尝试你们的产品，或者在招聘等方面，你们在寻找什么样的人？

<details>
<summary>Original English</summary>

**Len**: Okay, cool. Like very ambitious. I I I think I finally get it more after talking to you and hopefully people listening along can can get a sense of the scope of the vision as well. Where should you should people point to for _ trying stuff out? _ you know, what are you looking for in terms of hiring that anything like that?

</details>

**Ronuk**: 是的，当然。我们将快速扩张，能够见证这一点非常令人兴奋。我想说，老实说，整个研究界最活跃的地方依然是 Twitter，所以可以在那里关注我们的动态。另外，我希望大家也能够积极参与进来，为我们构建的东西感到兴奋。我感觉当我们在 Windsurf 的时候，见证开发者使用编码智能体并与之保持共鸣是至关重要的。对我们来说也是一样，我希望与客户如何使用我们的产品以及持续学习研究的发展保持高度共鸣，并在这一领域贡献我们的一些创新。我们目前最主要的两个招聘方向是研究团队（我们正持续扩建它）和产品团队。我们希望不断增强我们平台的鲁棒性，将其规模从 5 家客户扩展到 15、20 甚至 50 家。所以，是的，这是我们的下一个前沿。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. Yeah, for sure. No, so we're going to be growing really fast and it it's exciting to see that. I would say like honestly the the main place where all of the the research world lives on is Twitter and so following along on there and _ no and and I like I want people to also like engage and be excited about what we're building. I I felt like when we were at Windsurf again like doing _ just like seeing how developers were using coding agents and like being able to be really in tune with that _ it was super important and and for us that's the same way like I want to just be in tune with like how customers are using our product and how how continual learning research is is kind of scaling up and us being able to _ at least contribute some innovations to that field and and we're going to be I think like the two areas for us are obviously see like research and and growing that team and product as well. We we want to be really robustifying our platform, scaling it up to not just five customers but 15 20 50 very soon. So, _ yeah, that that's kind of the next frontiers.

</details>

### 商业化进展与行业展望

**Len**: 你们目前已经拥有的 5 家非常优秀的客户，对很多人来说都是极佳的品牌背书。我很兴奋能听到和看到更多关于你们的消息，大家也一定去关注你们。我想我也邀请了你参加我的会议 **AIE**（AI Engineer Conference），我们正在设立一个持续学习专题分会场。我以前做这个决定时非常谨慎，我当时觉得我不确定这个领域是否已经准备好了。但看到你们以及其他致力于持续学习的团队的工作，我认为时机已到。即使我们可能不完全确定最终的产品会是什么样子，但我认为已经有足够的生产环境测试案例在落地了。

<details>
<summary>Original English</summary>

**Len**: You got five very good customers in there that are extremely good logos for a lot of people. _ Uh yeah, I'm excited to hear more and and see more, you know, and people can check you out for sure. I think I've also invited you to my conference _ AIE where we are doing a continual learning track. I was very cautious about doing it. I was like, I don'\''t know if the field is ready. But with you guys and some of the other folks also working on continue learning, I think it's time. Even though if we don't exactly know what the end products will look like, I think there's enough test cases where like Yeah. like people are trying to put this in production already.

</details>

**Ronuk**: 是的，我认为现在就是属于持续学习的时代，这真的非常令人兴奋。我也很激动能参加这次盛会。

<details>
<summary>Original English</summary>

**Ronuk**: Yeah. I I think it now is the time of continual learning and so it's super exciting. I I'm very excited to be at the the fair.

</details>

**Len**: 好的，祝贺你们，这次发布太精彩了。说真的，执行得太棒了。作为一个懂点市场营销的人，我真的被深深打动了。

**Ronuk**: 非常感谢，这对我意味着很多，尤其是从你嘴里说出来。是的，哈哈。

<details>
<summary>Original English</summary>

**Len**: Yeah. Yeah. All right. Congrats. Amazing launch. seriously like so well executed. I'm I'm actually like very very impressed as like someone on the marketing side, right? Like
**Ronuk**: I'm like man that means a lot coming from you. Yeah. [laughter]

</details>

**Len**: 我觉得，这简直为如何发布一个产品实验室（products lab）树立了新的标杆。再次祝贺，很期待看到更多成果。

<details>
<summary>Original English</summary>

**Len**: I'm like okay like this is like the bar now for like how to launch a products lab, you know? So yeah, congrats and excited to see more.

</details>

**Ronuk**: 非常感谢。谢谢你抽空交流，这真的超级有趣。

<details>
<summary>Original English</summary>

**Ronuk**: Thank you so much. Yeah, thanks for taking the time to chat. This is super fun.

</details>